---
title:
  en: "Network Security - Segmentation, Zero Trust, NGFW/WAF/IDS, ZTNA, SASE"
  tr: "Ağ Güvenliği - Segmentasyon, Sıfır Güven, NGFW/WAF/IDS, ZTNA, SASE"
section: "05-technical-measures"
document_type: "control_policy"
control_id: "TECH-NET-01"
owner:
  primary: "CISO"
  secondary: "Network Engineering"
review_cycle: "annual"
last_review: "2026-05-08"
next_review: "2027-05-08"
classification: "Internal"
language: ["en", "tr"]
references:
  - "GDPR Art. 5(1)(f), 32(1)(b), 32(1)(d)"
  - "ISO/IEC 27002:2022 controls 8.20, 8.21, 8.22, 8.23"
  - "NIST CSF 2.0 PR.IR, DE.CM"
  - "NIST SP 800-207 Zero Trust Architecture"
  - "ENISA Handbook on Security of Personal Data Processing - Network Controls"
  - "OWASP Top 10 2021"
---

## English

# Network Security

## 1. Purpose

Network controls implement the confidentiality and integrity requirements of
GDPR Article 32(1)(b) by limiting where personal data can flow, who can reach
the systems holding it, and what happens when an unexpected actor attempts to
do so. This document codifies the controller's network architecture, segment
model, gateway controls and detection stack.

## 2. Architectural Principles

1. **Default deny** - all flows are denied by default and explicitly allowed
   per documented policy.
2. **Segment by trust and purpose** - networks are divided by business
   function and data sensitivity, not by physical convenience.
3. **Zero Trust** - no network is inherently trusted; identity and posture
   are evaluated on every request.
4. **Least exposure** - administrative interfaces are never exposed to the
   public internet.
5. **Encrypt by default** - mTLS internally, TLS 1.3 externally.
6. **Observable** - every flow has a corresponding telemetry record
   (`logging.md`).

## 3. Segment Model

| Segment | Contents | Trust | Ingress |
|---------|----------|-------|---------|
| Public DMZ | Edge load balancers, public WAF, content delivery | Untrusted | Internet (filtered, rate-limited) |
| Application | Stateless services, APIs | Low-trust until identity proven | DMZ via mTLS |
| Data | Databases, object storage, message brokers | Restricted | Application via mTLS only |
| Management | CI/CD, monitoring, IAM, KMS | Restricted | Bastion / ZTNA |
| Restricted | T4-T5 data systems, HR, finance, secrets | Highly restricted | ZTNA + AAL3 |
| Workforce | Employee endpoints | Low-trust | ZTNA outbound |
| OT / IoT | Operational technology where present | Isolated | One-way / strict broker |

Cross-segment communication requires:

- Documented data flow.
- Explicit firewall rule with ticket trace.
- mTLS on all internal channels.
- Logged at the egress and ingress device.

## 4. Zero Trust (NIST SP 800-207)

The Zero Trust Architecture is implemented through:

- **Policy Decision Point (PDP)** - centralised policy engine evaluating
  identity, device posture, location, time and behavioural risk score.
- **Policy Enforcement Point (PEP)** - identity-aware proxies, service mesh
  sidecars and ZTNA gateways.
- **Continuous evaluation** - posture is re-evaluated periodically and on
  context change.
- **Micro-segmentation** - service-to-service authorisation independent of
  network position.
- **Strong identity** - workload (mTLS / SPIFFE) and human (AAL2 / AAL3) per
  `authentication.md`.

## 5. Perimeter Controls

### 5.1 Next-Generation Firewall (NGFW)

- Stateful inspection with application identification.
- Geo-IP filtering for management interfaces.
- Threat intel-driven IP blocklists refreshed at least daily.
- All rules tied to a ticket and reviewed quarterly.
- Deny-by-default outbound from sensitive segments to the internet.

### 5.2 Web Application Firewall (WAF)

- In front of every public web application and API gateway.
- Rule sets:
  - OWASP CRS baseline.
  - Vendor-managed rules for emerging zero-days.
  - Application-specific rules tuned and reviewed monthly.
- Rate limiting per route and per identity.
- Bot management with proof-of-work / behavioural challenges.
- Block list updated for credential stuffing campaigns observed in the wild.

### 5.3 DDoS Protection

- Anycast scrubbing at the edge for L3-L4 attacks.
- L7 rate limiting at WAF.
- Origin shielding so application origins never receive direct traffic.
- Run-book and contact tree maintained
  (`08-breach-management/`).

### 5.4 IDS / IPS

- Signature and anomaly engines on north-south boundaries and east-west
  critical zones.
- Tuned per segment to reduce noise.
- Alerts to SIEM (`logging.md`).

## 6. ZTNA and SASE

### 6.1 ZTNA (Zero Trust Network Access)

Replaces traditional VPN for workforce and third-party access:

- Identity-aware reverse proxy.
- Per-application micro-tunnels - users see only the apps they are entitled
  to.
- Continuous posture - device managed, disk-encrypted, EDR healthy, OS within
  patch window.
- Risk-based step-up to phishing-resistant MFA when posture or behaviour
  changes.
- Session recorded for AAL3 destinations.

### 6.2 SASE (Secure Access Service Edge)

Combines ZTNA, SWG, CASB and FWaaS in one cloud-delivered fabric for the
distributed workforce:

- Outbound traffic from endpoints to the internet routed via SWG with TLS
  inspection (see Section 8).
- SaaS posture and DLP via CASB (`dlp.md`).
- Branch and remote-site connectivity via SD-WAN with on-net policy
  enforcement.
- Single identity and policy plane.

## 7. Internal Service Mesh

- mTLS between services using short-lived certificates.
- Authorisation policies expressed declaratively, version-controlled,
  reviewed before merge.
- Egress controlled - services may reach only declared destinations.
- Mesh telemetry exported to SIEM and APM.
- Service identity verified by SPIFFE ID embedded in certificates.

## 8. TLS Inspection - Privacy Balance

TLS inspection (also called break-and-inspect) decrypts outbound TLS to apply
DLP, malware and policy controls. It can affect employee privacy and personal
data flowing through corporate infrastructure. The controller therefore
applies a privacy-balanced approach in line with GDPR Article 88 and national
labour law:

| Category | TLS Inspection | Justification |
|----------|----------------|---------------|
| Banking, healthcare portals, government services | Bypassed | Personal financial / health data; lawful basis insufficient |
| Personal webmail, social networks | Bypassed | Employee privacy; Article 88 |
| Corporate SaaS in scope of business | Inspected | Necessary for confidentiality and security |
| Unknown / uncategorised | Inspected | Risk-based |
| Categories under collective agreement | Per agreement | Workforce participation |

Inspection points are documented in the network architecture register and the
employee privacy notice (`03-transparency-consent/`). Inspected traffic and
captured artefacts are subject to the same retention controls as DLP
artefacts (`dlp.md`).

## 9. DNS and Resolution

- Internal split-horizon DNS for management names.
- DNSSEC validation enabled on resolvers.
- DoH / DoT for endpoint resolution to controller-operated resolvers.
- DNS firewall blocks known malicious and newly registered domains.
- DNS query logs retained per `logging.md`.

## 10. Email Gateway

- Inbound: SPF, DKIM, DMARC verification; sandbox detonation of attachments;
  URL rewriting and time-of-click checks.
- Outbound: DMARC alignment, DKIM signing, MTA-STS enforce.
- Anti-impersonation rules covering executive and finance look-alikes.
- Phishing-reported inbox triaged within 1 hour during business hours.

## 11. Wireless and Workplace Networks

- WPA3-Enterprise with EAP-TLS; certificate-based device authentication.
- Guest network logically isolated, internet-only, captive portal with
  acceptable-use acknowledgement.
- Rogue AP detection enabled.
- Network access control (NAC) places non-compliant devices into a remediation
  VLAN.

## 12. Configuration and Change Control

- Network device configurations stored in version control with peer review.
- Configuration drift monitored hourly; deviation triggers an alert.
- Change windows approved through CAB; emergency changes documented within 1
  business day.
- Annual review of segmentation effectiveness using internal red-team
  simulation.

## 13. KPIs

| Metric | Target |
|--------|--------|
| Public exposure of admin interfaces | 0 |
| Internal services on mTLS | 100 % |
| WAF false-negative rate (annual pen test) | <= 1 % |
| Mean time to block confirmed malicious IP | <= 15 minutes |
| Configuration drift open > 7 days | 0 |
| ZTNA enrolment coverage of remote users | 100 % |
| Segmentation policy violations open | 0 |

## 14. Mapping

| Requirement | ISO 27002:2022 | NIST CSF 2.0 |
|-------------|----------------|--------------|
| Network segregation | 8.22 | PR.IR-1 |
| Networks security | 8.20 | PR.IR-1 |
| Security of network services | 8.21 | PR.IR-1 |
| Web filtering | 8.23 | DE.CM-9 |
| Detection (IDS/IPS) | 8.16 | DE.CM-1 |

---

## Türkçe

# Ağ Güvenliği

## 1. Amaç

Ağ kontrolleri, kişisel verinin nereye akabileceğini, onu tutan sistemlere
kimin erişebileceğini ve beklenmeyen bir aktörün bunu denediğinde ne
olacağını sınırlayarak GDPR Madde 32(1)(b) gizlilik ve bütünlük gereksinimlerini
uygular. Bu belge, kontrolörün ağ mimarisini, segment modelini, ağ geçidi
kontrollerini ve algılama yığınını kodlar.

## 2. Mimari İlkeler

1. **Varsayılan reddet** - tüm akışlar varsayılan olarak reddedilir ve
   belgelenmiş politika başına açıkça izinlidir.
2. **Güven ve amaç bazında segment** - ağlar fiziksel kolaylığa göre değil, iş
   işlevi ve veri hassasiyetine göre bölünür.
3. **Sıfır Güven** - hiçbir ağ doğal olarak güvenilir değildir; her istekte
   kimlik ve duruş değerlendirilir.
4. **Asgari maruziyet** - yönetimsel arayüzler asla genel internete açılmaz.
5. **Varsayılan olarak şifrele** - dahili olarak mTLS, harici olarak TLS 1.3.
6. **Gözlemlenebilir** - her akışın karşılık gelen bir telemetri kaydı vardır
   (`logging.md`).

## 3. Segment Modeli

| Segment | İçerik | Güven | Giriş |
|---------|--------|-------|-------|
| Genel DMZ | Kenar yük dengeleyiciler, genel WAF, içerik dağıtım | Güvenilmez | İnternet (filtrelenmiş, hız sınırlı) |
| Uygulama | Durumsuz hizmetler, API'ler | Kimlik kanıtlanana kadar düşük güven | mTLS üzerinden DMZ |
| Veri | Veritabanları, nesne depolama, mesaj broker'ları | Kısıtlı | Yalnızca mTLS üzerinden Uygulama |
| Yönetim | CI/CD, izleme, IAM, KMS | Kısıtlı | Bastion / ZTNA |
| Kısıtlı | T4-T5 veri sistemleri, İK, finans, sırlar | Yüksek kısıtlı | ZTNA + AAL3 |
| İş Gücü | Çalışan uç noktaları | Düşük güven | Giden ZTNA |
| OT / IoT | Mevcutsa operasyonel teknoloji | İzole | Tek yön / sıkı broker |

Segmentler arası iletişim:

- Belgelenmiş veri akışı.
- Bilet izi olan açık güvenlik duvarı kuralı.
- Tüm dahili kanallarda mTLS.
- Çıkış ve giriş cihazında loglanır.

## 4. Sıfır Güven (NIST SP 800-207)

Sıfır Güven Mimarisi şunlar aracılığıyla uygulanır:

- **Politika Karar Noktası (PDP)** - kimlik, cihaz duruşu, konum, zaman ve
  davranışsal risk skorunu değerlendiren merkezi politika motoru.
- **Politika Uygulama Noktası (PEP)** - kimlik bilinçli proxy'ler, servis
  mesh sidecar'ları ve ZTNA ağ geçitleri.
- **Sürekli değerlendirme** - duruş periyodik olarak ve bağlam değişiminde
  yeniden değerlendirilir.
- **Mikro segmentasyon** - ağ konumundan bağımsız servis-servis yetkilendirme.
- **Güçlü kimlik** - iş yükü (mTLS / SPIFFE) ve insan (AAL2 / AAL3),
  `authentication.md` uyarınca.

## 5. Perimetre Kontrolleri

### 5.1 Yeni Nesil Güvenlik Duvarı (NGFW)

- Uygulama tanımlamalı durumlu inceleme.
- Yönetim arayüzleri için Geo-IP filtreleme.
- En az günlük yenilenen tehdit istihbaratı odaklı IP blok listeleri.
- Tüm kurallar bir bilete bağlıdır ve üç ayda bir incelenir.
- Hassas segmentlerden internete varsayılan-reddet giden.

### 5.2 Web Uygulama Güvenlik Duvarı (WAF)

- Her genel web uygulaması ve API ağ geçidinin önünde.
- Kural setleri:
  - OWASP CRS temel.
  - Yeni sıfır gün için sağlayıcı yönetimli kurallar.
  - Aylık ayarlanan ve incelenen uygulamaya özel kurallar.
- Rota ve kimlik başına hız sınırlama.
- Çalışma kanıtı / davranışsal zorluklar ile bot yönetimi.
- Vahşi doğada gözlemlenen kimlik bilgisi doldurma kampanyaları için
  güncellenmiş engelleme listesi.

### 5.3 DDoS Koruması

- L3-L4 saldırıları için kenarda anycast temizleme.
- WAF'ta L7 hız sınırlama.
- Uygulama orijinleri asla doğrudan trafik almasın diye orijin koruması.
- Operasyon kitabı ve iletişim ağacı tutulur (`08-breach-management/`).

### 5.4 IDS / IPS

- Kuzey-güney sınırlarında ve doğu-batı kritik bölgelerinde imza ve anomali
  motorları.
- Gürültüyü azaltmak için segment başına ayarlanmış.
- SIEM'e uyarılar (`logging.md`).

## 6. ZTNA ve SASE

### 6.1 ZTNA (Sıfır Güven Ağ Erişimi)

İş gücü ve üçüncü taraf erişimi için geleneksel VPN'in yerini alır:

- Kimlik bilinçli ters proxy.
- Uygulama başına mikro tüneller - kullanıcılar yalnızca yetkili oldukları
  uygulamaları görür.
- Sürekli duruş - cihaz yönetilen, disk şifrelemeli, EDR sağlıklı, OS yama
  penceresinde.
- Duruş veya davranış değiştiğinde phishing'e dayanıklı MFA'ya risk temelli
  yükseltme.
- AAL3 hedefleri için kayıt altına alınan oturum.

### 6.2 SASE (Güvenli Erişim Hizmeti Kenarı)

Dağıtık iş gücü için tek bir bulut sunumlu kumaşta ZTNA, SWG, CASB ve FWaaS'ı
birleştirir:

- Uç noktalardan internete giden trafik TLS incelemeli SWG üzerinden
  yönlendirilir (Bölüm 8).
- CASB ile SaaS duruşu ve DLP (`dlp.md`).
- SD-WAN ile şube ve uzak saha bağlantısı, ağda politika uygulaması.
- Tek kimlik ve politika düzlemi.

## 7. Dahili Servis Mesh

- Kısa ömürlü sertifikalar kullanan servisler arasında mTLS.
- Bildirimsel olarak ifade edilen, sürüm kontrollü, birleştirme öncesi
  incelenen yetkilendirme politikaları.
- Kontrollü çıkış - servisler yalnızca beyan edilen hedeflere erişebilir.
- Mesh telemetrisi SIEM ve APM'ye dışa aktarılır.
- Sertifikalara gömülü SPIFFE kimliği ile servis kimliği doğrulanır.

## 8. TLS İncelemesi - Gizlilik Dengesi

TLS incelemesi (kır ve incele), DLP, kötü amaçlı yazılım ve politika
kontrollerini uygulamak için giden TLS'yi şifresini çözer. Çalışan gizliliğini
ve kurumsal altyapıdan akan kişisel veriyi etkileyebilir. Bu nedenle
kontrolör, GDPR Madde 88 ve ulusal iş hukuku doğrultusunda gizlilik dengeli
bir yaklaşım uygular:

| Kategori | TLS İncelemesi | Gerekçe |
|----------|----------------|---------|
| Bankacılık, sağlık portalları, devlet hizmetleri | Atlanır | Kişisel finansal / sağlık verisi; yasal dayanak yetersiz |
| Kişisel web posta, sosyal ağlar | Atlanır | Çalışan gizliliği; Madde 88 |
| İş kapsamındaki kurumsal SaaS | İncelenir | Gizlilik ve güvenlik için gereklidir |
| Bilinmeyen / kategorize edilmemiş | İncelenir | Risk temelli |
| Toplu sözleşme kapsamındaki kategoriler | Sözleşmeye göre | İş gücü katılımı |

İnceleme noktaları ağ mimari kayıt defterinde ve çalışan gizlilik bildiriminde
(`03-transparency-consent/`) belgelenir. İncelenen trafik ve yakalanan
yapılar, DLP yapıları (`dlp.md`) ile aynı saklama kontrollerine tabidir.

## 9. DNS ve Çözümleme

- Yönetim adları için dahili split-horizon DNS.
- Çözücülerde DNSSEC doğrulama açık.
- Kontrolör tarafından işletilen çözücülere uç nokta çözümlemesi için DoH /
  DoT.
- DNS güvenlik duvarı bilinen kötü amaçlı ve yeni kayıtlı alan adlarını
  engeller.
- DNS sorgu logları `logging.md` uyarınca saklanır.

## 10. E-posta Ağ Geçidi

- Gelen: SPF, DKIM, DMARC doğrulama; eklerin sandbox patlatma; URL yeniden
  yazma ve tıklama anı kontrolleri.
- Giden: DMARC hizalama, DKIM imzalama, MTA-STS enforce.
- Yönetici ve finans benzeri taklitleri kapsayan anti-taklit kuralları.
- Phishing bildirilen gelen kutusu mesai saatlerinde 1 saat içinde triyaj
  edilir.

## 11. Kablosuz ve İş Yeri Ağları

- EAP-TLS ile WPA3-Enterprise; sertifika tabanlı cihaz kimlik doğrulaması.
- Misafir ağı mantıksal olarak izole, yalnızca internet, kabul edilebilir
  kullanım onayı içeren captive portal.
- Sahte AP tespiti açık.
- Ağ erişim kontrolü (NAC) uyumlu olmayan cihazları bir iyileştirme VLAN'ına
  yerleştirir.

## 12. Konfigürasyon ve Değişim Kontrolü

- Ağ cihazı konfigürasyonları peer review ile sürüm kontrolünde tutulur.
- Konfigürasyon kayması saatlik izlenir; sapma uyarı tetikler.
- Değişim pencereleri CAB onaylı; acil değişiklikler 1 iş günü içinde
  belgelenir.
- Dahili red-team simülasyonu kullanılarak segmentasyon etkinliğinin yıllık
  incelemesi.

## 13. KPI'lar

| Metrik | Hedef |
|--------|-------|
| Yönetim arayüzlerinin genel maruziyeti | 0 |
| mTLS'teki dahili servisler | %100 |
| WAF yanlış-negatif oranı (yıllık pentest) | <= %1 |
| Doğrulanmış kötü amaçlı IP'yi engelleme süresi | <= 15 dakika |
| 7 günden uzun açık konfigürasyon kayması | 0 |
| Uzaktan kullanıcıların ZTNA kayıt kapsamı | %100 |
| Açık segmentasyon politika ihlalleri | 0 |

## 14. Eşleme

| Gereklilik | ISO 27002:2022 | NIST CSF 2.0 |
|------------|----------------|--------------|
| Ağ ayrımı | 8.22 | PR.IR-1 |
| Ağ güvenliği | 8.20 | PR.IR-1 |
| Ağ hizmetlerinin güvenliği | 8.21 | PR.IR-1 |
| Web filtreleme | 8.23 | DE.CM-9 |
| Algılama (IDS/IPS) | 8.16 | DE.CM-1 |
