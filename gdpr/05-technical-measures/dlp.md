---
title:
  en: "Data Loss Prevention - Endpoint, Network, Cloud (CASB), EU PII, Employee Privacy Balance"
  tr: "Veri Sızıntısı Önleme - Uç Nokta, Ağ, Bulut (CASB), AB PII, Çalışan Gizliliği Dengesi"
section: "05-technical-measures"
document_type: "control_policy"
control_id: "TECH-DLP-01"
owner:
  primary: "CISO"
  secondary: "DPO, HR Lead"
review_cycle: "annual"
last_review: "2026-05-08"
next_review: "2027-05-08"
classification: "Internal"
language: ["en", "tr"]
references:
  - "GDPR Art. 5(1)(a), 5(1)(c), 5(1)(f), 6(1)(f), 32(1)(b), 88"
  - "ISO/IEC 27002:2022 controls 8.12, 8.16, 8.23"
  - "NIST CSF 2.0 PR.DS-3, DE.CM-3"
  - "ENISA Handbook on Security of Personal Data Processing"
  - "EDPB Opinion 2/2017 on data processing at work"
  - "National labour law and works council frameworks (Article 88)"
---

## English

# Data Loss Prevention (DLP)

## 1. Purpose

DLP detects and prevents unauthorised exfiltration of personal data and other
sensitive content. It supports Article 32(1)(b) confidentiality and integrity
and Article 5(1)(f) integrity and confidentiality. Because DLP processes
employee activity data, it must also satisfy Article 5(1)(a) lawfulness,
fairness and transparency, Article 5(1)(c) data minimisation, Article 6(1)(f)
balancing where the lawful basis is legitimate interests, and Article 88
where national law sets specific rules on workforce processing.

## 2. Scope

DLP covers four channels:

1. **Endpoint** - workstations, laptops, mobile devices.
2. **Network** - HTTPS traffic via secure web gateway, email gateway.
3. **Cloud / SaaS** - through a Cloud Access Security Broker (CASB).
4. **Discovery** - data-at-rest scanning of file shares, cloud storage,
   collaboration platforms and code repositories.

Coverage applies to all systems and devices on which the controller's data
may be processed.

## 3. Discovery Programme

Before policy enforcement, the controller must know where personal data
lives. The discovery programme:

- Inventories shared drives, document repositories, collaboration platforms,
  cloud buckets, code repositories, ticket systems, BI / data lakes,
  endpoints.
- Classifies content using:
  - Pattern matching for structured PII.
  - Exact data match (EDM) using hashed reference indices for known data
    sets (HR, customer, payroll).
  - Document fingerprinting for sensitive templates.
  - Machine learning classifiers for unstructured T4 data.
- Tags discovered assets with classification labels.
- Reports identified misplacements (Article 9 data outside the secure
  enclave, customer PII in public buckets, secrets in code).
- Feeds the data map and ROPA accuracy review.

Discovery runs continuously with a full sweep at least quarterly.

## 4. EU PII Identifier Library

The DLP engine carries a curated identifier library covering EU member
states. Examples:

| Country / Identifier | Pattern Notes |
|----------------------|---------------|
| **NL - BSN (Burgerservicenummer)** | 9 digits, 11-test (elfproef) |
| **DE - Steuerliche Identifikationsnummer** | 11 digits, weighted check digit |
| **FR - INSEE / NIR** | 13 digits + 2 control |
| **ES - DNI / NIE** | 8 digits + control letter; X/Y/Z prefix for NIE |
| **IT - Codice Fiscale** | 16 alphanumerics |
| **BE - Rijksregisternummer** | 11 digits, modulo-97 |
| **PL - PESEL** | 11 digits, weighted check digit |
| **PT - NIF** | 9 digits, modulo-11 |
| **SE - Personnummer** | 10/12 digits, Luhn |
| **DK - CPR-nummer** | 10 digits |
| **AT - Sozialversicherungsnummer** | 10 digits |
| **IE - PPS Number** | 7 digits + 1-2 letters |
| **HU - TAJ szam** | 9 digits |
| **CZ - Rodne cislo** | 9-10 digits, encodes DOB |
| **RO - CNP** | 13 digits |
| **EU - IBAN** | Country-specific; modulo-97 |
| **EU - SWIFT/BIC** | 8 or 11 chars |
| **EU - VAT** | Country-specific; checksum |
| **Passport (multi-country)** | Format per ICAO 9303 |
| **EHIC (European Health Insurance Card)** | 20 digits |

Additional patterns: payment card (PAN with Luhn + IIN range), Schengen visa,
driving licence formats, national health identifiers, professional licence
numbers.

The library is reviewed and updated annually; new identifiers added on
expansion to a new market.

## 5. Policy Catalogue

DLP policies are tied to data classifications and recipients:

| Policy | Trigger | Action |
|--------|---------|--------|
| Bulk customer PII export | >= 1000 customer records to external destination | Block + alert + ticket |
| Special-category data leaving secure enclave | Health / biometric / political / etc. patterns | Block + alert + DPIA reference |
| Payment card to non-PCI scope | PAN to non-tokenised destination | Block |
| Source code to personal cloud | git push to non-corporate remote | Block |
| Secrets in commit | API key / private key patterns | Block at commit; alert if pushed |
| Bulk download from collaboration | > 1000 files in a session | Step-up MFA + alert |
| External email with payroll terms | Mass salary list patterns | Coach + require justification |
| USB to unencrypted device | Device class | Block |

Policies have severity, response, and link to the response playbook
(`08-breach-management/`).

## 6. Detection Logic

- Patterns combined with proximity context to reduce false positives (e.g.,
  IBAN must co-occur with name or DOB to be a match).
- EDM keeps reference data hashed in the engine; raw values never leave the
  source.
- ML classifiers tuned per business unit; quarterly review of false-positive
  / false-negative rates.
- Detection on encrypted channels via TLS inspection where permitted
  (`network-security.md` Section 8) - inspection bypassed for personal,
  banking, healthcare and government categories.

## 7. Response Workflow

| Severity | Response |
|----------|----------|
| Low (advisory) | Educational pop-up on endpoint, no block |
| Medium | Block, log, notify user, manager review |
| High | Block, log, ticket to SOC, manager + DPO informed |
| Critical | Isolate endpoint, account containment, breach assessment, possible Article 33 evaluation |

All triggers feed SIEM (`logging.md`) for correlation. False positives close
with reviewer comment and feed tuning.

## 8. CASB and SaaS Controls

The CASB layer:

- Inventories sanctioned and unsanctioned (shadow IT) SaaS use.
- Applies API-mode policies to sanctioned platforms (Microsoft 365, Google
  Workspace, Slack, Salesforce, GitHub, Notion, Box, etc.):
  - Public sharing scans and remediation.
  - External user inventory.
  - Anomalous download / mass-delete detection.
  - Malware scanning of uploaded files.
- Applies inline (proxy) controls to unsanctioned services - block, coach,
  or read-only.
- Maintains posture for misconfiguration drift (e.g., open S3 buckets,
  permissive sharing settings).

## 9. Endpoint DLP

- Agent on managed endpoints with low performance footprint.
- Controls:
  - Removable media policy (encrypted only or block).
  - Print control with watermarking for restricted documents.
  - Screen capture restrictions for high-classification windows.
  - Clipboard control between classifications.
  - Application-aware blocking of personal cloud sync agents.
- Roaming users covered identically through cloud control plane.
- Tamper protection - users cannot disable the agent.

## 10. Employee Privacy Balance (Article 88, Article 6(1)(f))

DLP processes employee activity data. The controller's lawful basis is
typically Article 6(1)(f) legitimate interests - protection of company data
and personal data of customers - subject to a balancing test. The balancing
documentation includes:

- Clear necessity statement.
- Least-intrusive design choices documented.
- Proportionality - personal communications excluded; categories like
  banking, healthcare, government services and personal social networks
  bypass inspection (`network-security.md`).
- Transparency - DLP coverage disclosed in the employee privacy notice
  (`03-transparency-consent/`).
- Safeguards - access to DLP artefacts limited to SOC and authorised
  investigators; managers do not have free access; AAL3 authentication
  required to view content.
- Retention - DLP event logs retained 24 months; raw captured content
  retained only while needed for an open investigation, then deleted or
  preserved under legal hold.
- Data subject rights - employees may exercise rights subject to legal
  exemptions where exercise would prejudice ongoing investigation.

National law may add stricter requirements:

- Works council consultation in DE, FR, NL, AT, IT, ES, others.
- Specific written instructions in some jurisdictions.
- Prior consultation with the DPA where DPIA shows residual high risk
  (Article 36).

A DPIA is mandatory before deployment or material change
(`06-organizational-measures/dpia.md`).

## 11. Data Subject Right Interaction

DLP-collected content may itself become subject to:

- Right of access - employees can ask whether DLP captured their content;
  responses subject to investigation exemptions in national law.
- Right to erasure - non-investigation content beyond retention window must
  be deleted.
- Right to restriction - while disputing accuracy or lawfulness.

Procedures captured in `09-data-subject-rights/`.

## 12. Vendor and Processor

DLP capability provided by a processor is governed by the DPA
(`06-organizational-measures/vendor-management.md`) including processing
location, sub-processors, retention and exit. Cross-border transfers comply
with `07-international-transfers/`.

## 13. KPIs

| Metric | Target |
|--------|--------|
| Endpoints with DLP agent healthy | >= 99 % |
| SaaS in CASB inventory | 100 % sanctioned, > 90 % visibility on shadow IT |
| False-positive rate (high severity) | < 5 % |
| Mean time to triage High event | <= 4 hours |
| DLP coverage misalignment (gap > 30 days) | 0 |
| Employee notice up to date | 100 % |
| DPIA completion before policy expansion | 100 % |

## 14. Mapping

| Requirement | ISO 27002:2022 | NIST CSF 2.0 |
|-------------|----------------|--------------|
| Data leakage prevention | 8.12 | PR.DS-3 |
| Monitoring activities | 8.16 | DE.CM-3 |
| Web filtering | 8.23 | PR.DS-3 |

---

## Türkçe

# Veri Sızıntısı Önleme (DLP)

## 1. Amaç

DLP, kişisel verinin ve diğer hassas içeriğin yetkisiz dışarı sızdırılmasını
algılar ve önler. Madde 32(1)(b) gizlilik ve bütünlüğü ile Madde 5(1)(f)
bütünlük ve gizliliği destekler. DLP çalışan etkinlik verisini işlediği için
ayrıca Madde 5(1)(a) hukukilik, adillik ve şeffaflığı, Madde 5(1)(c) veri
minimizasyonunu, yasal dayanağın meşru menfaat olduğu yerde Madde 6(1)(f)
dengelemesini ve ulusal hukukun iş gücü işlemesi üzerinde özel kurallar
koyduğu yerlerde Madde 88'i karşılamalıdır.

## 2. Kapsam

DLP dört kanalı kapsar:

1. **Uç nokta** - iş istasyonları, dizüstü bilgisayarlar, mobil cihazlar.
2. **Ağ** - güvenli web ağ geçidi üzerinden HTTPS trafiği, e-posta ağ
   geçidi.
3. **Bulut / SaaS** - bir Bulut Erişim Güvenlik Broker'ı (CASB) üzerinden.
4. **Keşif** - dosya paylaşımları, bulut depolama, işbirliği platformları ve
   kod depolarının dinamik olmayan veri taraması.

Kapsam, kontrolörün verilerinin işlenebileceği tüm sistemler ve cihazları
kapsar.

## 3. Keşif Programı

Politika uygulamasından önce kontrolörün kişisel verinin nerede yaşadığını
bilmesi gerekir. Keşif programı:

- Paylaşılan sürücüleri, belge depolarını, işbirliği platformlarını, bulut
  kovalarını, kod depolarını, bilet sistemlerini, BI / veri göllerini, uç
  noktaları envantere alır.
- İçeriği şunlar kullanılarak sınıflandırır:
  - Yapılandırılmış PII için desen eşleme.
  - Bilinen veri kümeleri (İK, müşteri, bordro) için hashlenmiş referans
    indeksleri kullanan tam veri eşleme (EDM).
  - Hassas şablonlar için belge parmak izi.
  - Yapılandırılmamış T4 veri için makine öğrenmesi sınıflandırıcıları.
- Keşfedilen varlıkları sınıflandırma etiketleriyle etiketler.
- Tanımlanan yanlış yerleştirmeleri raporlar (güvenli alandan dışarıda Madde
  9 verisi, genel kovalardaki müşteri PII'si, koddaki sırlar).
- Veri haritasını ve ROPA doğruluk incelemesini besler.

Keşif sürekli çalışır, en az üç ayda bir tam tarama yapılır.

## 4. AB PII Tanımlayıcı Kütüphanesi

DLP motoru, AB üye devletlerini kapsayan seçilmiş bir tanımlayıcı kütüphanesi
taşır. Örnekler:

| Ülke / Tanımlayıcı | Desen Notları |
|--------------------|---------------|
| **NL - BSN (Burgerservicenummer)** | 9 hane, 11-test (elfproef) |
| **DE - Steuerliche Identifikationsnummer** | 11 hane, ağırlıklı kontrol hanesi |
| **FR - INSEE / NIR** | 13 hane + 2 kontrol |
| **ES - DNI / NIE** | 8 hane + kontrol harfi; NIE için X/Y/Z öneki |
| **IT - Codice Fiscale** | 16 alfanümerik |
| **BE - Rijksregisternummer** | 11 hane, modulo-97 |
| **PL - PESEL** | 11 hane, ağırlıklı kontrol hanesi |
| **PT - NIF** | 9 hane, modulo-11 |
| **SE - Personnummer** | 10/12 hane, Luhn |
| **DK - CPR-nummer** | 10 hane |
| **AT - Sozialversicherungsnummer** | 10 hane |
| **IE - PPS Number** | 7 hane + 1-2 harf |
| **HU - TAJ szam** | 9 hane |
| **CZ - Rodne cislo** | 9-10 hane, doğum tarihi kodlar |
| **RO - CNP** | 13 hane |
| **AB - IBAN** | Ülkeye özel; modulo-97 |
| **AB - SWIFT/BIC** | 8 veya 11 karakter |
| **AB - VAT** | Ülkeye özel; sağlama toplamı |
| **Pasaport (çok ülkeli)** | ICAO 9303 başına format |
| **EHIC (Avrupa Sağlık Sigortası Kartı)** | 20 hane |

Ek desenler: ödeme kartı (Luhn + IIN aralığı ile PAN), Schengen vizesi,
sürücü ehliyeti formatları, ulusal sağlık tanımlayıcıları, mesleki lisans
numaraları.

Kütüphane yıllık olarak incelenir ve güncellenir; yeni bir pazara
genişlemede yeni tanımlayıcılar eklenir.

## 5. Politika Kataloğu

DLP politikaları veri sınıflandırmaları ve alıcılarla bağlıdır:

| Politika | Tetikleyici | Eylem |
|----------|-------------|-------|
| Toplu müşteri PII dışa aktarımı | Dış hedefe >= 1000 müşteri kaydı | Engelle + uyar + bilet |
| Güvenli alandan ayrılan özel-nitelikli veri | Sağlık / biyometri / politik / vb. desenler | Engelle + uyar + VKD referansı |
| PCI kapsamı dışı ödeme kartı | Tokenize edilmemiş hedefe PAN | Engelle |
| Kişisel buluta kaynak kodu | Kurumsal olmayan uzaktan git push | Engelle |
| Commit'te sırlar | API anahtarı / özel anahtar desenleri | Commit'te engelle; push edildiyse uyar |
| İşbirliğinden toplu indirme | Bir oturumda > 1000 dosya | Adım MFA + uyar |
| Bordro terimleriyle dış e-posta | Toplu maaş listesi desenleri | Koçluk + gerekçe iste |
| Şifrelenmemiş cihaza USB | Cihaz sınıfı | Engelle |

Politikaların ciddiyet, müdahale ve müdahale operasyon kitabına bağı vardır
(`08-breach-management/`).

## 6. Algılama Mantığı

- Yanlış pozitifleri azaltmak için yakınlık bağlamıyla birleştirilmiş desenler
  (örn., bir IBAN'ın eşleşme olması için ad veya doğum tarihi ile birlikte
  bulunması gerekir).
- EDM motorda hashlenmiş referans veri tutar; ham değerler kaynağı asla
  terk etmez.
- İş birimi başına ayarlanmış ML sınıflandırıcılar; yanlış-pozitif /
  yanlış-negatif oranlarının üç aylık incelemesi.
- İzin verilen yerlerde TLS incelemesi yoluyla şifreli kanallarda algılama
  (`network-security.md` Bölüm 8) - kişisel, bankacılık, sağlık ve devlet
  kategorileri için inceleme atlanır.

## 7. Müdahale İş Akışı

| Ciddiyet | Müdahale |
|----------|----------|
| Düşük (öneri) | Uç noktada eğitici açılır pencere, engelleme yok |
| Orta | Engelle, logla, kullanıcıyı bilgilendir, yönetici inceleme |
| Yüksek | Engelle, logla, SOC'ye bilet, yönetici + DPO bilgilendirilir |
| Kritik | Uç noktayı izole et, hesap kapsama al, ihlal değerlendirmesi, olası Madde 33 değerlendirmesi |

Tüm tetikleyiciler korelasyon için SIEM'i besler (`logging.md`). Yanlış
pozitifler inceleyici yorumuyla kapanır ve ayar besler.

## 8. CASB ve SaaS Kontrolleri

CASB katmanı:

- Yetkilendirilmiş ve yetkilendirilmemiş (gölge BT) SaaS kullanımını
  envantere alır.
- Yetkilendirilmiş platformlara (Microsoft 365, Google Workspace, Slack,
  Salesforce, GitHub, Notion, Box, vb.) API modu politikaları uygular:
  - Genel paylaşım taramaları ve iyileştirme.
  - Dış kullanıcı envanteri.
  - Anormal indirme / toplu silme algılaması.
  - Yüklenen dosyaların kötü amaçlı yazılım taraması.
- Yetkilendirilmemiş hizmetlere satır içi (proxy) kontroller uygular -
  engelle, koçluk veya yalnızca okuma.
- Yanlış konfigürasyon kayması için duruşu sürdürür (örn., açık S3 kovaları,
  izin veren paylaşım ayarları).

## 9. Uç Nokta DLP

- Düşük performans ayak izi olan yönetilen uç noktalardaki ajan.
- Kontroller:
  - Çıkarılabilir ortam politikası (yalnızca şifreli veya engelle).
  - Kısıtlı belgeler için filigranlama ile yazdırma kontrolü.
  - Yüksek sınıflandırma pencereleri için ekran yakalama kısıtlamaları.
  - Sınıflandırmalar arası pano kontrolü.
  - Kişisel bulut senkronizasyon ajanlarının uygulama bilinçli engellenmesi.
- Roaming kullanıcılar bulut kontrol düzlemi üzerinden aynı şekilde
  kapsanır.
- Müdahale koruması - kullanıcılar ajanı devre dışı bırakamaz.

## 10. Çalışan Gizliliği Dengesi (Madde 88, Madde 6(1)(f))

DLP çalışan etkinlik verisini işler. Kontrolörün yasal dayanağı genellikle
Madde 6(1)(f) meşru menfaat - şirket verisinin ve müşterilerin kişisel
verisinin korunması - olup dengeleme testine tabidir. Dengeleme
belgelendirmesi şunları içerir:

- Açık gereklilik beyanı.
- Belgelenmiş en az müdahale eden tasarım seçenekleri.
- Orantılılık - kişisel iletişim hariç tutulur; bankacılık, sağlık, devlet
  hizmetleri ve kişisel sosyal ağlar gibi kategoriler incelemeyi atlar
  (`network-security.md`).
- Şeffaflık - DLP kapsamı çalışan gizlilik bildiriminde açıklanır
  (`03-transparency-consent/`).
- Güvenceler - DLP yapılarına erişim SOC ve yetkili soruşturmacılarla
  sınırlıdır; yöneticilerin serbest erişimi yoktur; içerik görüntülemek
  için AAL3 kimlik doğrulaması gerekir.
- Saklama - DLP olay logları 24 ay saklanır; ham yakalanan içerik yalnızca
  açık bir soruşturma için gerektiği sürece saklanır, ardından silinir veya
  yasal hold altında korunur.
- Veri sahibi hakları - çalışanlar, kullanımın devam eden soruşturmaya zarar
  vereceği yerde yasal muafiyetlere tabi olarak hakları kullanabilir.

Ulusal hukuk daha sıkı gereklilikler ekleyebilir:

- DE, FR, NL, AT, IT, ES ve diğerlerinde işyeri konseyi danışması.
- Bazı yetki alanlarında özel yazılı talimatlar.
- VKD'nin kalan yüksek riski gösterdiği yerde DPA ile ön danışma (Madde 36).

Dağıtım veya maddi değişiklik öncesi VKD zorunludur
(`06-organizational-measures/dpia.md`).

## 11. Veri Sahibi Hakkı Etkileşimi

DLP tarafından toplanan içerik kendisi şu konulara konu olabilir:

- Erişim hakkı - çalışanlar DLP'nin içeriklerini yakalayıp yakalamadığını
  sorabilir; yanıtlar ulusal hukuktaki soruşturma muafiyetlerine tabidir.
- Silme hakkı - saklama penceresinin ötesindeki soruşturma dışı içerik
  silinmelidir.
- Kısıtlama hakkı - doğruluk veya hukukiliği itiraz ederken.

Prosedürler `09-data-subject-rights/` altında yakalanmıştır.

## 12. Tedarikçi ve İşleyici

Bir işleyici tarafından sağlanan DLP yeteneği, işleme konumu, alt-işleyiciler,
saklama ve çıkış dahil DPA tarafından yönetilir
(`06-organizational-measures/vendor-management.md`). Sınır ötesi aktarımlar
`07-international-transfers/` ile uyumludur.

## 13. KPI'lar

| Metrik | Hedef |
|--------|-------|
| DLP ajanı sağlıklı uç noktalar | >= %99 |
| CASB envanterindeki SaaS | %100 yetkilendirilmiş, gölge BT'de > %90 görünürlük |
| Yanlış-pozitif oranı (yüksek ciddiyet) | < %5 |
| Yüksek olayı triyaj etme süresi | <= 4 saat |
| DLP kapsam hizalanmaması (boşluk > 30 gün) | 0 |
| Güncel çalışan bildirimi | %100 |
| Politika genişlemesinden önce VKD tamamlama | %100 |

## 14. Eşleme

| Gereklilik | ISO 27002:2022 | NIST CSF 2.0 |
|------------|----------------|--------------|
| Veri sızıntısı önleme | 8.12 | PR.DS-3 |
| İzleme etkinlikleri | 8.16 | DE.CM-3 |
| Web filtreleme | 8.23 | PR.DS-3 |
