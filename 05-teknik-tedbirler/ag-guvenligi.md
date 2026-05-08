---
Doküman: Ağ Güvenliği Politikası ve Standardı
Bölüm: 05-teknik-tedbirler
Sahip: Ağ Güvenliği Lideri / CISO
Onaylayan: BT Direktörü + KVKK Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (mimari değişiklik, yeni saldırı tipi, ihlal)
İlgili Mevzuat: 6698 sayılı KVKK m.12; Kişisel Veri Güvenliği Rehberi — "Siber Güvenliğin Sağlanması"
İlgili Standart: ISO/IEC 27001:2022 A.8.20 (Networks Security), A.8.21 (Security of Network Services), A.8.22 (Segregation of Networks), A.8.23 (Web Filtering); NIST CSF 2.0 PR.PS, PR.IR; NIST SP 800-207 (Zero Trust Architecture); CIS Controls v8 #12, #13; ENISA Network Security Guidelines
---

# Ağ Güvenliği

## 1. Amaç

Kişisel veriyi içeren / taşıyan tüm ağ akışlarının yetkisiz dinlenmeye, yetkisiz erişime, kötü amaçlı yazılımın yatay hareketine, hizmet kesintisine karşı katmanlı biçimde korunmasını standardize eder.

## 2. Tasarım İlkeleri

1. **Zero Trust:** Hiçbir trafiğe **ağ konumuna göre** güven verilmez. Her bağlantı kimliği + cihazı + bağlamı doğrulanarak kabul edilir (NIST 800-207).
2. **Segmentasyon:** Patlama yarıçapını sınırlamak için ağ mantıksal/fiziksel olarak parçalanır.
3. **Mikrosegmentasyon:** Veri merkezi içinde uygulama / iş yükü düzeyinde kontrol; doğu-batı trafiğinde "default deny".
4. **Kişisel Veri Lokasyonu Görünür:** Kişisel veri içeren her sistemin ağ konumu CMDB ve veri envanteri ile eşli, etiketli.
5. **Defence in Depth:** Çevre (perimeter) → DMZ → iç ağ → uygulama segmenti → veri segmenti — her geçişte kontrol.
6. **Least Privilege Access (Network):** Her ağ akışı whitelisted; default deny.
7. **Dinleme + Tespit + Müdahale:** Tek kontrol katmanına güvenilmez; pasif tespit + aktif önleme birlikte.

## 3. Ağ Bölümlemesi

### 3.1. Mantıksal Bölgeler

```
┌─────────────────────────────────────────────────┐
│ İnternet                                        │
└────────────────────┬────────────────────────────┘
                     │
              [Edge / DDoS / Anti-bot]
                     │
┌────────────────────┼────────────────────────────┐
│  DMZ (Public Reverse Proxy / WAF / API Gateway) │
└────────────────────┼────────────────────────────┘
                     │
       ┌─────────────┼─────────────┐
       │             │             │
   [App-Web]    [App-Service]   [Yönetim]
       │             │             │
   [App-DB]     [App-DB]       [Bastion / PAM]
       │             │             │
   ┌───┴─────────────┴─────────────┴───┐
   │ Ortak Servisler: DNS, NTP, Audit  │
   └────────────────────────────────────┘
   ┌────────────────────────────────────┐
   │ Kişisel Veri Yüksek Hassasiyet    │
   │ (özel nitelikli, finansal, kart)  │
   │ — Ayrı VLAN/VPC, sıkı erişim     │
   └────────────────────────────────────┘
```

### 3.2. Bölge Tanımları

| Bölge | Trafik | Özellikler |
|-------|--------|------------|
| Edge | Internet → Şirket | DDoS, anti-bot, geo-block, rate limit |
| DMZ | Internet ↔ Servis | WAF, reverse proxy, API gateway |
| App-Web | DMZ ↔ Uygulama | Frontend uygulamalar, public API tüketicileri |
| App-Service | İç servisler | Backend, mikroservis |
| App-DB | DB sunucu | Sadece App-Service'ten erişim |
| Yüksek Hassasiyet | Özel/finansal/sağlık | Ayrı VLAN/VPC, ek IPS, sıkı ACL |
| Yönetim | OOB management | Bastion + PAM, jump host |
| OT/IoT | Üretim cihazları | Tamamen ayrı VLAN, tek yönlü data diode mümkünse |
| Misafir Wi-Fi | Misafirler | Tamamen izoleli, internet-only |

### 3.3. Mikrosegmentasyon

- Veri merkezi içinde **service-to-service** kuralları **uygulama kimliği** bazlı (firewall IP yerine identity).
- Kubernetes: NetworkPolicy + Cilium / Calico ile pod düzeyinde "default deny", ihtiyaca göre allow.
- Bulut: Security Group / NSG + Service Endpoint / Private Link, internet üzerinden erişim sıfır.

## 4. Çevre Güvenliği (Perimeter)

### 4.1. Next-Generation Firewall (NGFW)

- L3-L7 inspection, TLS inspection (politikaya göre, mahremiyet dengesi — bkz. §10), uygulama tanıma.
- HA çift (active-passive veya active-active), çoklu ISP.
- Politika: tüm kurallar **ticket + onay** ile, dokümante. Acil değişiklik 24 saat içinde gerekçeli kayda alınır.
- Periyodik kural temizliği (yıllık) — kullanılmayan kurallar kaldırılır.
- Logları SIEM'e (gerçek zamanlı).

### 4.2. WAF (Web Application Firewall)

- Tüm dış erişilebilir uygulamalar **WAF arkasında**.
- OWASP CRS (Core Rule Set) 4+ kurallar, ek kurum-özel kurallar.
- IP reputation, bot mitigation, JSON/XML parse, GraphQL inspection.
- Asgari koruma: SQLi, XSS, RCE, LFI/RFI, SSRF, deserialization.
- TLS termination + arka uça mTLS.
- "Detect" modunda başlat, **"Prevent" moduna 30 gün içinde** geçir; "permanent detect" tehlikeli.

### 4.3. DDoS Koruması

- L3/4 hacimsel + L7 uygulama katmanı koruması (Cloudflare, Akamai, AWS Shield, Azure DDoS, Imperva).
- BGP anycast / scrubbing center.
- Runbook hazır: tetikleyici eşik, devreye alma, kapatma.
- Yıllık tatbikat.

### 4.4. API Gateway

- Authentication (OAuth2/OIDC, mTLS, API key + key vault).
- Rate limit (kullanıcı, IP, endpoint).
- Schema validation (OpenAPI, JSON schema).
- Quota & throttling.
- Olay logu — kişisel veri içermeyecek şekilde.

## 5. Saldırı Tespit ve Önleme (IDS/IPS, EDR, NDR)

### 5.1. IDS/IPS

- Çevrede ve kritik segment giriş/çıkışlarında IPS sensörü.
- Signature + anomaly + threat-intel feed.
- Inline mode (IPS) kritik segmentlerde; "monitor only" yetersiz.
- Yönetimi merkezi, false positive loop ile düzenli rafineri.

### 5.2. NDR (Network Detection & Response)

- Doğu-batı trafik analizi (Vectra, Darktrace, ExtraHop, Corelight/Zeek).
- ML tabanlı anomali; lateral movement, data exfiltration örüntüleri.
- DNS, DHCP, SMB, RDP, LDAP analizi.

### 5.3. EDR (Endpoint Detection & Response)

- Tüm sunucu ve uç cihazda EDR ajanı (CrowdStrike, SentinelOne, Defender for Endpoint vb.).
- 24/7 SOC izleme.

### 5.4. Honeypot / Deception

- Kritik veri segmentinde fake host, fake share, fake credential — saldırgan triggering için.
- Honeypot dokunuşu **yüksek güvenli alarm** üretir.

## 6. Uzaktan Erişim

### 6.1. VPN

- Site-to-site: IPsec IKEv2 (önerilen) veya WireGuard.
- Remote-access kullanıcı VPN: zorunlu MFA, sertifika tabanlı, kısa oturum.
- VPN sonlandırma noktası — DMZ'de, doğrudan iç ağa düşmez.
- Split tunneling kapalı (kişisel veri trafiği şirket gateway'inden).

### 6.2. ZTNA (Zero Trust Network Access)

VPN yerine kademeli olarak ZTNA tercih edilir (Zscaler ZPA, Cloudflare Access, NetSkope, Twingate, Tailscale Business). Avantajlar:

- Uygulama-bazlı erişim (ağ değil).
- Identity + cihaz + bağlam değerlendirmesi her istek için.
- Lateral movement riski azalır.

### 6.3. Bastion / Jump Host

- Sunuculara doğrudan SSH/RDP yok; sadece bastion üzerinden.
- Bastion kayıt + PAM + MFA.
- Bastion oturum kayıtları immutable (bkz. [erisim-kontrolu.md](erisim-kontrolu.md)).

## 7. DNS Güvenliği

- Tüm istemcilerde **şirket DNS'i** zorunlu (DHCP + GPO + MDM).
- DNS filtering (zararlı, phishing, kategori).
- DNSSEC iç bölgeler için aktif; dış sorgu DNS over TLS / over HTTPS (DoT/DoH) destekli, ama kontrol için iç DoH proxy.
- DNS log SIEM'e — DGA tespiti, exfil kanalı tespiti.

## 8. Kablosuz Ağ

- Kurumsal Wi-Fi: WPA3-Enterprise + 802.1X (radius + cihaz sertifikası).
- WPA2-Personal yasaktır.
- Misafir Wi-Fi: tamamen izoleli, captive portal, KVKK aydınlatma metni gösterimli.
- IoT/üretim: ayrı SSID + ayrı VLAN, internet erişimi yalnızca whitelisted host.

## 9. Email & Web Filtreleme

- E-posta gateway: SPF, DKIM, DMARC (p=reject hedefi), anti-phishing, sandbox detonation.
- URL rewrite + click-time analiz.
- Web filtreleme (Secure Web Gateway): kategori bazlı engelleme, malware blocking, file inspection.
- HTTPS inspection — bkz. §10.

## 10. SSL/TLS Inspection ve Mahremiyet Dengesi

TLS inspection trafiğin görünür hâle gelmesini sağlar; ama **çalışan mahremiyeti** ve **bazı veri aktarım yasakları** açısından dikkat ister.

### 10.1. Politika

- Şirket cihazlarında, şirket trafiğinde TLS inspection **uygulanır**.
- **İnceleme dışı tutulan kategoriler:** sağlık, bankacılık, hukuk hizmeti, kişisel e-posta, devlet portalı (KVKK m.4 ölçülülük). Cihaz bypass listesi yıllık review.
- Çalışana tek seferde + yıllık olarak yazılı bilgilendirme (BYOD politikası, Çalışan Mahremiyet Aydınlatma Metni — 06-idari-tedbirler).
- Misafir trafiği inceleme dışı.
- Inspect edilen trafikte saklanan içerik **minimize**; istisnasız log retention politikasına bağlı.

### 10.2. Sertifika Dağıtımı

- TLS inspection için kurumsal CA, MDM ile push edilir. Personal cihazlara push **yapılmaz** (BYOD'da iş profili izole).

## 11. SASE (Secure Access Service Edge)

Çoklu lokasyon + uzaktan çalışan model için SASE (SD-WAN + ZTNA + SWG + CASB + FWaaS) tek üretici / entegre çözüm tercih edilir. SASE benimsenmesi:

- Kontrol noktası bulutta, kullanıcının bulunduğu yere göre yakın PoP.
- Politikalar tek panelden, tüm modlar için (LAN, mobile, ev, ofis).
- Bulut SaaS erişimi loglanır (CASB).
- Bkz. [dlp.md](dlp.md) — CASB DLP entegrasyonu.

## 12. CASB (Cloud Access Security Broker)

- Onaylı SaaS uygulamaları envanterli, "shadow IT" tespit + raporu (aylık).
- Ayrıcalıklı SaaS (Salesforce, Workday, GitHub, Microsoft 365 vb.) için API tabanlı CASB — kullanıcı eylemleri görülür, anormallik alarmı.
- DLP politikaları SaaS içinde uygulanır.

## 13. Bulut-Spesifik Ağ Güvenliği

### 13.1. AWS

- VPC default → tüm route, sg, NACL gözden geçirilmiş.
- Private Link (Endpoint Service) ile S3, DynamoDB, Secrets Manager.
- Internet Gateway sadece public subnet'e.
- VPC Flow Logs → CloudWatch / S3 → SIEM.
- AWS WAF + Shield Advanced (kritik uygulama).
- IAM Network condition (aws:SourceVpc, aws:SourceIp).

### 13.2. Azure

- Hub-and-spoke; Azure Firewall hub'ta, NSG spoke'larda.
- Private Endpoint kişisel veri içeren PaaS için zorunlu (Storage, SQL, Cosmos).
- Bastion kullan, public IP RDP/SSH yok.
- DDoS Protection Standard.
- NSG Flow Logs → Log Analytics.

### 13.3. GCP

- Shared VPC + organization policy.
- Private Google Access + VPC Service Controls (kişisel veri exfil önleme).
- Cloud Armor + IAP.

## 14. Değişiklik Yönetimi

- Tüm ağ değişiklikleri ITSM ticket + onaylı.
- "Standart değişiklik" katalogu önceden onaylı, hızlı geçişli; her diğeri için CAB.
- Acil değişiklik (P1 olay) → 24 saat içinde retro doküman.
- Kural sahipliği zorunlu — sahibi olmayan kural 90 gün sonra kaldırılır.

## 15. Loglama

Aşağıdaki ağ logları **mutlak** SIEM'e gönderilir:

- Firewall: tüm izinli/izinsiz trafik (yüksek hacim için sample alınmaz; özellikle DENY mutlak).
- WAF: tüm tetiklenen kural + sınırlı sayıda payload örneği (kişisel veri minimize).
- VPN/ZTNA: bağlantı, oturum süresi, bayt, lokasyon.
- Proxy/SWG: URL, kategori, kullanıcı.
- DNS: sorgu, yanıt, müşteri.
- IDS/IPS: tüm uyarı.
- Cloud (VPC Flow, NSG Flow).

Saklama: kişisel veri içeren akıştaki loglar 1–2 yıl, kritik için 5 yıl. 5651 sayılı Kanun yer/erişim sağlayıcı yükümlülükleri ayrıca değerlendirilir (bkz. [log-yonetimi.md](log-yonetimi.md)).

## 16. Sızma Testi & Red Team

- Yıllık dış sızma testi (CREST/OSCP sertifikalı).
- Yıllık iç sızma testi (segmentasyon doğrulama dahil).
- Mor takım egzersizi yıllık.
- Bulgular CAPA ile takip; kritik 30 gün, yüksek 60 gün, orta 90 gün, düşük yıllık.
- Bkz. [uygulama-guvenligi.md](uygulama-guvenligi.md).

## 17. Tatbikatlar

- DDoS tatbikatı (yıllık).
- Ransomware lateral movement tatbikatı (yıllık).
- Kayıp/çalıntı dizüstü senaryosu (yarı yıl).
- Veri exfiltration tatbikatı + DLP/NDR algılama doğrulama.

## 18. Kontrol Listesi

- [ ] Kişisel veri içeren tüm sistemlerin ağ konumu CMDB'de etiketli mi?
- [ ] Kritik segmentler arası "default deny" + whitelist mi?
- [ ] Mikrosegmentasyon (uygulama-kimlik bazlı) uygulanıyor mu?
- [ ] Firewall HA, log SIEM'e, kuralların sahibi belli mi?
- [ ] WAF "prevent" modunda mı?
- [ ] DDoS koruması canlı + yıllık tatbikat var mı?
- [ ] Tüm uzaktan erişim MFA + cihaz uyumlu + ZTNA / sıkı VPN mi?
- [ ] Bastion + PAM ile sunucu erişimi izli mi?
- [ ] DNS filtering + DoH proxy aktif mi?
- [ ] Wi-Fi WPA3-Enterprise + 802.1X mi?
- [ ] E-posta SPF/DKIM/DMARC + sandbox aktif mi?
- [ ] TLS inspection politikası mahremiyet dengesi gözetiyor mu, bypass listesi yıllık review'da mı?
- [ ] Bulut özel endpoint + private link kişisel veri PaaS'larda zorunlu mu?
- [ ] CASB shadow IT envanteri aylık güncelleniyor mu?
- [ ] Tüm ağ logları SIEM'de, retention politika uyumlu mu?
- [ ] Yıllık iç + dış sızma testi yapıldı, bulgular kapatıldı mı?
- [ ] Segmentasyon yılda en az bir kez doğrulanıyor mu?
- [ ] Honeypot/deception kritik segmentte mi?

## 19. Olay Müdahalesi (Ağ Spesifik)

- C2 (command-and-control) trafiği tespiti → ana makine izole, EDR taraması, threat hunt.
- Lateral movement: anormal SMB/RDP/PsExec → segmentasyon doğrulaması, ele geçirilen hesabın tüm oturumları kapatılır.
- Veri exfiltration anomalisi (büyük outbound, az bilinen hedef): NDR alarmı → derhal block + DPO+CISO bilgilendirme.
- Misafir Wi-Fi'den iç ağa yönelik tarama → tamamen yalıtım denetlenir.
