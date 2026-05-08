---
Doküman / Document: Ağ Güvenliği Politikası ve Standardı / Network Security Policy and Standard
Bölüm / Section: 05-teknik-tedbirler
Sahip / Owner: Ağ Güvenliği Lideri / CISO / Network Security Lead / CISO
Onaylayan / Approved by: BT Direktörü + KVKK Komitesi / IT Director + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş (mimari değişiklik, yeni saldırı tipi, ihlal) / Annual + triggered (architecture change, new attack type, breach)
İlgili Mevzuat / Legal Reference: Law No. 6698 KVKK Art. 12; Personal Data Security Guide — "Ensuring Cybersecurity"
İlgili Standart / Standard: ISO/IEC 27001:2022 A.8.20 (Networks Security), A.8.21 (Security of Network Services), A.8.22 (Segregation of Networks), A.8.23 (Web Filtering); NIST CSF 2.0 PR.PS, PR.IR; NIST SP 800-207 (Zero Trust Architecture); CIS Controls v8 #12, #13; ENISA Network Security Guidelines
---

## English

# Network Security

## 1. Purpose

Standardizes the layered protection of all network flows containing/carrying personal data against unauthorized eavesdropping, unauthorized access, lateral movement of malware, and service disruption.

## 2. Design Principles

1. **Zero Trust:** No traffic is trusted **by network location**. Every connection is accepted after identity + device + context verification (NIST 800-207).
2. **Segmentation:** The network is partitioned logically/physically to limit blast radius.
3. **Microsegmentation:** Application / workload-level control inside the data center; "default deny" on east-west traffic.
4. **Personal Data Location Visible:** Network location of every system containing personal data is mapped to CMDB and data inventory, labeled.
5. **Defence in Depth:** Perimeter → DMZ → internal network → application segment → data segment — control at each transition.
6. **Least Privilege Access (Network):** Every network flow whitelisted; default deny.
7. **Detection + Prevention + Response:** No reliance on a single layer of control; passive detection + active prevention combined.

## 3. Network Segmentation

### 3.1. Logical Zones

```
┌─────────────────────────────────────────────────┐
│ Internet                                        │
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
   [App-Web]    [App-Service]   [Management]
       │             │             │
   [App-DB]     [App-DB]       [Bastion / PAM]
       │             │             │
   ┌───┴─────────────┴─────────────┴───┐
   │ Common Services: DNS, NTP, Audit  │
   └────────────────────────────────────┘
   ┌────────────────────────────────────┐
   │ Personal Data High Sensitivity    │
   │ (special-category, financial,     │
   │ card) — Separate VLAN/VPC, strict │
   │ access                            │
   └────────────────────────────────────┘
```

### 3.2. Zone Definitions

| Zone | Traffic | Properties |
|-------|--------|------------|
| Edge | Internet → Company | DDoS, anti-bot, geo-block, rate limit |
| DMZ | Internet ↔ Service | WAF, reverse proxy, API gateway |
| App-Web | DMZ ↔ Application | Frontend applications, public API consumers |
| App-Service | Internal services | Backend, microservices |
| App-DB | DB server | Only access from App-Service |
| High Sensitivity | Special/financial/health | Separate VLAN/VPC, additional IPS, strict ACL |
| Management | OOB management | Bastion + PAM, jump host |
| OT/IoT | Production devices | Completely separate VLAN, one-way data diode if possible |
| Guest Wi-Fi | Guests | Fully isolated, internet-only |

### 3.3. Microsegmentation

- Inside the data center, **service-to-service** rules are based on **application identity** (instead of firewall IP).
- Kubernetes: NetworkPolicy + Cilium / Calico, "default deny" at the pod level, allow as needed.
- Cloud: Security Group / NSG + Service Endpoint / Private Link, zero internet-based access.

## 4. Perimeter Security

### 4.1. Next-Generation Firewall (NGFW)

- L3-L7 inspection, TLS inspection (per policy, privacy balance — see §10), application identification.
- HA pair (active-passive or active-active), multiple ISPs.
- Policy: all rules **with ticket + approval**, documented. Emergency changes recorded with justification within 24 hours.
- Periodic rule cleanup (annual) — unused rules removed.
- Logs to SIEM (real time).

### 4.2. WAF (Web Application Firewall)

- All externally accessible applications **behind WAF**.
- OWASP CRS (Core Rule Set) 4+ rules, plus organization-specific rules.
- IP reputation, bot mitigation, JSON/XML parse, GraphQL inspection.
- Minimum protection: SQLi, XSS, RCE, LFI/RFI, SSRF, deserialization.
- TLS termination + mTLS to backend.
- Start in "Detect" mode, **switch to "Prevent" mode within 30 days**; "permanent detect" is dangerous.

### 4.3. DDoS Protection

- L3/4 volumetric + L7 application layer protection (Cloudflare, Akamai, AWS Shield, Azure DDoS, Imperva).
- BGP anycast / scrubbing center.
- Runbook ready: trigger threshold, activation, deactivation.
- Annual drill.

### 4.4. API Gateway

- Authentication (OAuth2/OIDC, mTLS, API key + key vault).
- Rate limit (user, IP, endpoint).
- Schema validation (OpenAPI, JSON schema).
- Quota & throttling.
- Event log — without containing personal data.

## 5. Intrusion Detection and Prevention (IDS/IPS, EDR, NDR)

### 5.1. IDS/IPS

- IPS sensors at perimeter and on entry/exit of critical segments.
- Signature + anomaly + threat-intel feed.
- Inline mode (IPS) on critical segments; "monitor only" insufficient.
- Centrally managed, regularly refined with false positive loop.

### 5.2. NDR (Network Detection & Response)

- East-west traffic analysis (Vectra, Darktrace, ExtraHop, Corelight/Zeek).
- ML-based anomaly; lateral movement, data exfiltration patterns.
- DNS, DHCP, SMB, RDP, LDAP analysis.

### 5.3. EDR (Endpoint Detection & Response)

- EDR agent on every server and endpoint device (CrowdStrike, SentinelOne, Defender for Endpoint, etc.).
- 24/7 SOC monitoring.

### 5.4. Honeypot / Deception

- Fake hosts, fake shares, fake credentials in critical data segments — for attacker triggering.
- Honeypot touch generates a **high-confidence alarm**.

## 6. Remote Access

### 6.1. VPN

- Site-to-site: IPsec IKEv2 (recommended) or WireGuard.
- Remote-access user VPN: mandatory MFA, certificate-based, short session.
- VPN termination point — in DMZ, does not directly drop into the internal network.
- Split tunneling off (personal data traffic goes through corporate gateway).

### 6.2. ZTNA (Zero Trust Network Access)

ZTNA is gradually preferred over VPN (Zscaler ZPA, Cloudflare Access, NetSkope, Twingate, Tailscale Business). Advantages:

- Application-based access (not network).
- Identity + device + context evaluation per request.
- Lateral movement risk reduced.

### 6.3. Bastion / Jump Host

- No direct SSH/RDP to servers; only via bastion.
- Bastion logging + PAM + MFA.
- Bastion session recordings immutable (see [erisim-kontrolu.md](erisim-kontrolu.md)).

## 7. DNS Security

- **Corporate DNS** mandatory on all clients (DHCP + GPO + MDM).
- DNS filtering (malicious, phishing, category).
- DNSSEC active for internal zones; external query DNS over TLS / over HTTPS (DoT/DoH) supported, but internal DoH proxy for control.
- DNS log to SIEM — DGA detection, exfil channel detection.

## 8. Wireless Network

- Corporate Wi-Fi: WPA3-Enterprise + 802.1X (radius + device certificate).
- WPA2-Personal forbidden.
- Guest Wi-Fi: fully isolated, captive portal, KVKK privacy notice displayed.
- IoT/production: separate SSID + separate VLAN, internet access only to whitelisted hosts.

## 9. Email & Web Filtering

- Email gateway: SPF, DKIM, DMARC (p=reject target), anti-phishing, sandbox detonation.
- URL rewrite + click-time analysis.
- Web filtering (Secure Web Gateway): category-based blocking, malware blocking, file inspection.
- HTTPS inspection — see §10.

## 10. SSL/TLS Inspection and Privacy Balance

TLS inspection makes traffic visible; but requires care regarding **employee privacy** and **certain data transfer prohibitions**.

### 10.1. Policy

- TLS inspection **applied** on company traffic on company devices.
- **Categories excluded from inspection:** health, banking, legal services, personal email, government portal (KVKK Art. 4 proportionality). Device bypass list reviewed annually.
- One-time + annual written notice to employees (BYOD policy, Employee Privacy Notice — 06-idari-tedbirler).
- Guest traffic excluded from inspection.
- Inspected traffic content is **minimized** in storage; subject to log retention policy without exception.

### 10.2. Certificate Distribution

- Corporate CA pushed via MDM for TLS inspection. **Not** pushed on personal devices (work profile isolated in BYOD).

## 11. SASE (Secure Access Service Edge)

For multi-location + remote work model, SASE (SD-WAN + ZTNA + SWG + CASB + FWaaS) integrated single-vendor / unified solution preferred. SASE adoption:

- Control point in the cloud, close PoP based on user's location.
- Policies from a single panel, for all modes (LAN, mobile, home, office).
- Cloud SaaS access logged (CASB).
- See [dlp.md](dlp.md) — CASB DLP integration.

## 12. CASB (Cloud Access Security Broker)

- Approved SaaS applications inventoried, "shadow IT" detection + report (monthly).
- API-based CASB for privileged SaaS (Salesforce, Workday, GitHub, Microsoft 365, etc.) — user actions visible, anomaly alarm.
- DLP policies applied within SaaS.

## 13. Cloud-Specific Network Security

### 13.1. AWS

- VPC default → all routes, sg, NACL reviewed.
- S3, DynamoDB, Secrets Manager via Private Link (Endpoint Service).
- Internet Gateway only to public subnet.
- VPC Flow Logs → CloudWatch / S3 → SIEM.
- AWS WAF + Shield Advanced (critical applications).
- IAM Network condition (aws:SourceVpc, aws:SourceIp).

### 13.2. Azure

- Hub-and-spoke; Azure Firewall in hub, NSG in spokes.
- Private Endpoint mandatory for PaaS containing personal data (Storage, SQL, Cosmos).
- Use Bastion, no public IP RDP/SSH.
- DDoS Protection Standard.
- NSG Flow Logs → Log Analytics.

### 13.3. GCP

- Shared VPC + organization policy.
- Private Google Access + VPC Service Controls (personal data exfil prevention).
- Cloud Armor + IAP.

## 14. Change Management

- All network changes via ITSM ticket + approved.
- "Standard change" catalog pre-approved, fast track; CAB for everything else.
- Emergency change (P1 incident) → retro document within 24 hours.
- Rule ownership mandatory — rules without owners removed after 90 days.

## 15. Logging

The following network logs are **absolutely** sent to SIEM:

- Firewall: all permitted/denied traffic (no sampling for high volume; especially DENY mandatory).
- WAF: all triggered rules + limited number of payload samples (personal data minimized).
- VPN/ZTNA: connection, session duration, bytes, location.
- Proxy/SWG: URL, category, user.
- DNS: query, response, client.
- IDS/IPS: all alerts.
- Cloud (VPC Flow, NSG Flow).

Retention: logs in flow containing personal data 1–2 years, 5 years for critical. Yer/access provider obligations under Law No. 5651 are evaluated separately (see [log-yonetimi.md](log-yonetimi.md)).

## 16. Penetration Test & Red Team

- Annual external penetration test (CREST/OSCP certified).
- Annual internal penetration test (including segmentation validation).
- Annual purple team exercise.
- Findings tracked with CAPA; critical 30 days, high 60 days, medium 90 days, low annually.
- See [uygulama-guvenligi.md](uygulama-guvenligi.md).

## 17. Drills

- DDoS drill (annual).
- Ransomware lateral movement drill (annual).
- Lost/stolen laptop scenario (semi-annual).
- Data exfiltration drill + DLP/NDR detection validation.

## 18. Checklist

- [ ] Are network locations of all systems containing personal data labeled in CMDB?
- [ ] "Default deny" + whitelist between critical segments?
- [ ] Is microsegmentation (application-identity based) applied?
- [ ] Firewall HA, logs to SIEM, rules with clear owners?
- [ ] Is WAF in "prevent" mode?
- [ ] DDoS protection live + annual drill?
- [ ] All remote access MFA + device compliant + ZTNA / strict VPN?
- [ ] Are server access via Bastion + PAM logged?
- [ ] DNS filtering + DoH proxy active?
- [ ] Wi-Fi WPA3-Enterprise + 802.1X?
- [ ] Email SPF/DKIM/DMARC + sandbox active?
- [ ] Does TLS inspection policy respect privacy balance, is the bypass list in annual review?
- [ ] Cloud private endpoint + private link mandatory on personal data PaaS?
- [ ] Is CASB shadow IT inventory updated monthly?
- [ ] Are all network logs in SIEM, retention policy compliant?
- [ ] Annual internal + external penetration test performed, findings closed?
- [ ] Is segmentation validated at least annually?
- [ ] Honeypot/deception in critical segment?

## 19. Incident Response (Network Specific)

- C2 (command-and-control) traffic detection → host isolated, EDR scan, threat hunt.
- Lateral movement: anomalous SMB/RDP/PsExec → segmentation validation, all sessions of compromised account closed.
- Data exfiltration anomaly (large outbound, lesser-known destination): NDR alarm → immediate block + DPO+CISO notification.
- Scanning from guest Wi-Fi to internal network → full isolation audited.

---

## Türkçe

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
