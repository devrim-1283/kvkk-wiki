---
title:
  en: "Logging and Monitoring - Auditable Events, SIEM/UEBA, Retention, GDPR Proportionality"
  tr: "Loglama ve İzleme - Denetlenebilir Olaylar, SIEM/UEBA, Saklama, GDPR Orantılılığı"
section: "05-technical-measures"
document_type: "control_policy"
control_id: "TECH-LOG-01"
owner:
  primary: "CISO"
  secondary: "SOC Lead, DPO"
review_cycle: "annual"
last_review: "2026-05-08"
next_review: "2027-05-08"
classification: "Internal"
language: ["en", "tr"]
references:
  - "GDPR Art. 5(1)(c), 5(2), 30, 32(1)(d), 33, 88"
  - "ISO/IEC 27002:2022 controls 8.15, 8.16, 8.17"
  - "NIST CSF 2.0 DE.CM, DE.AE, DE.AE-2, DE.AE-7"
  - "NIST SP 800-92 Guide to Computer Security Log Management"
  - "ENISA Handbook on Security of Personal Data Processing"
  - "EDPB Guidelines 9/2022 on personal data breach notification"
---

## English

# Logging and Monitoring

## 1. Purpose

Logging produces the evidence needed to satisfy Article 5(2) accountability,
to detect and investigate incidents under Article 32(1)(d), and to support
breach notification under Article 33. Logging itself processes personal data
(IP addresses, user IDs, behavioural events) and must therefore comply with
data minimisation (Article 5(1)(c)), purpose limitation (Article 5(1)(b)),
storage limitation (Article 5(1)(e)) and Article 88 where employee monitoring
is involved.

## 2. Auditable Event Catalogue

Every system in scope of ROPA produces logs covering at minimum:

### 2.1 Authentication
- Login success and failure with reason code.
- MFA challenge issued, accepted, denied.
- Session creation, refresh, revocation.
- Account lockout and unlock.
- Password change, recovery and admin reset.
- Token issuance, refresh, revocation.

### 2.2 Authorisation and Access
- Privilege elevation request, approval, use.
- Access denied (resource, action).
- Role / group membership change.
- Sharing change on documents and data sets.
- Export, download, large query of personal data.

### 2.3 Data Operations
- Read, write, delete, restore on personal data records (sampled or full
  depending on tier).
- Bulk operation triggers.
- Schema and configuration changes affecting personal data.
- Cryptographic operations on T4-T5 keys.
- Data subject right execution (access, rectification, erasure, portability)
  per `09-data-subject-rights/`.

### 2.4 Administrative
- Account create, modify, disable, delete.
- Permission change, policy change, rule change.
- System configuration change.
- Patch install and rollback.

### 2.5 Security Events
- IDS / IPS detection.
- WAF block / challenge.
- DLP block / alert.
- EDR detection, quarantine, isolation.
- Anti-malware events.

### 2.6 Reliability
- Service start, stop, crash.
- Backup start, success, failure
  (`backup-recovery.md`).
- Restore execution and outcome.
- Capacity threshold breaches.

## 3. Log Field Standard

Every event includes at minimum:

| Field | Notes |
|-------|-------|
| `timestamp` | RFC 3339 UTC with milliseconds |
| `event_id` | Unique within the source system |
| `correlation_id` | Carries through the request chain |
| `event_type` | From the catalogue above |
| `actor.subject_id` | Pseudonymous user / service ID |
| `actor.session_id` | If applicable |
| `actor.source_ip` | Hashed at rest where source IP is not strictly needed |
| `target.system` | Application or system name |
| `target.resource` | Resource identifier where applicable |
| `action` | Verb (read, write, delete...) |
| `outcome` | success / failure / denied |
| `reason` | Failure or denial reason |
| `data_subject_scope` | Where the action concerns personal data |

Logs do not contain:

- Cleartext passwords, tokens, API keys, MFA codes.
- Cleartext payment data (PAN, CVV).
- Article 9 special-category data unless absolutely necessary; if necessary
  the field is masked or pseudonymised.
- Full request / response bodies for personal-data endpoints by default.

## 4. Integrity

Article 5(2) accountability and Article 32(1)(b) integrity require logs to
be tamper-evident:

- **Append-only / WORM** - production logs landed in storage configured for
  append-only with object-lock retention.
- **Hash chain** - each batch of events hashed (SHA-256) and chained to the
  previous; chain root signed daily by the SIEM signing key.
- **Signing** - cryptographic signature on closed daily archives stored in
  the audit vault.
- **Time source** - all systems sync from a redundant authoritative time
  source (NTPv4 or NTS); drift > 100 ms triggers an alert.
- **Quarterly integrity audit** - verify chain and signatures across a
  random sample.

Log access by administrators is itself logged to a separate tenant; SoD
prevents the same identity from administering and reviewing.

## 5. Centralisation - SIEM and UEBA

- All in-scope systems forward logs to the SIEM (with reliable delivery and
  buffering for transient outages).
- Forwarders authenticate with mTLS or a signed token.
- The SIEM normalises to a common schema.
- UEBA modules apply behavioural baselines to detect:
  - Credential stuffing and password spray.
  - Impossible travel.
  - Privilege misuse.
  - Anomalous data exfiltration patterns.
  - MFA fatigue.
  - Insider risk indicators (combined with DLP signals from `dlp.md`).
- Detection content is version-controlled, peer-reviewed, mapped to MITRE
  ATT&CK techniques.
- Detection efficacy reviewed monthly.

## 6. Retention

The retention schedule balances Article 5(1)(e) storage limitation with
investigation and legal needs. Logs are personal data; the schedule is
declared in `04-retention-erasure/` and the privacy notice
(`03-transparency-consent/`).

| Log Class | Retention | Rationale |
|-----------|-----------|-----------|
| Authentication and access | 12 months hot, 24 months cold | Investigation, breach response |
| Privileged session recording | 24 months | High-impact events; statute of limitations |
| Application personal-data audit | 24 months | Accountability, data subject claims |
| Security detection | 12 months hot, 24 months cold | Pattern analysis |
| Network flow | 90 days hot, 12 months sampled cold | Storage proportionality |
| OS / system | 6 months | Reliability troubleshooting |
| DLP events | 24 months | Investigations, employment law |
| Critical financial systems | 5 years | Tax / commercial law |
| Logs containing Art. 9 data | 6 months unless legal obligation longer | Data minimisation |

After retention expiry, logs are deleted automatically. Deletions are
themselves logged (immutable audit). Selective deletion to honour erasure
requests is performed through pseudonymisation of subject identifiers within
the index, with the full record removed at the next rotation; the procedure
is documented in `09-data-subject-rights/`.

## 7. Proportionality and Article 88

Logging that captures employee activity (in particular DLP, ZTNA session
recording, browser proxy logs) is high-risk monitoring. The controller:

- Performs a DPIA (`06-organizational-measures/dpia.md`) before deployment.
- Limits collection to fields strictly necessary for security, fraud
  prevention or legal obligation.
- Excludes content of personal communications outside the controller's
  legitimate scope (banking, healthcare, social - see `network-security.md`).
- Discloses logging in the employee privacy notice
  (`03-transparency-consent/`) with the lawful basis (typically Article 6(1)(f)
  legitimate interests after balancing test or Article 6(1)(c) where required
  by law).
- Consults works council / employee representatives where required by national
  law (Article 88 + collective agreements).
- Restricts access to logs containing employee activity to the SOC and
  authorised investigators; standard managers cannot browse.

## 8. Access to Logs

- Read access is granted role-based (`access-control.md`).
- Forensic access requires AAL3 plus a documented investigation case ID.
- Bulk export of logs for analytics is pseudonymised at source.
- Sharing logs with vendors or processors requires DPA coverage
  (`06-organizational-measures/vendor-management.md`).

## 9. Detection Engineering

- Detections written in a code-reviewed format (Sigma, KQL, SPL, OPA).
- Each detection has:
  - Unique ID.
  - Description and threat reference.
  - False-positive notes.
  - Severity.
  - Response playbook reference (`08-breach-management/`).
- Detection coverage map published quarterly aligned to MITRE ATT&CK and
  risk register.
- Purple-team exercises validate detections at least twice per year.

## 10. Incident Linkage

When a detection escalates to an incident:

- The SIEM creates a case with all related events and supporting evidence.
- Investigators add notes, IOCs and timeline.
- The case feeds the breach process under Article 33 / 34
  (`08-breach-management/`).
- Closure includes a CAPA captured in `06-organizational-measures/internal-audit.md`.

## 11. KPIs

| Metric | Target |
|--------|--------|
| In-scope systems forwarding logs | 100 % |
| Log delivery reliability (no gap > 5 min) | >= 99.9 % |
| Mean time to detect (MTTD) critical | <= 15 minutes |
| False-positive rate (high-severity alerts) | < 10 % |
| Logs failing integrity verification | 0 |
| Retention compliance audit findings | 0 |
| DPIA completion before high-risk monitoring deployment | 100 % |

## 12. Mapping

| Requirement | ISO 27002:2022 | NIST CSF 2.0 |
|-------------|----------------|--------------|
| Logging | 8.15 | DE.CM-1 |
| Monitoring activities | 8.16 | DE.CM-1 |
| Clock synchronisation | 8.17 | PR.PS-2 |
| Detection processes | n/a | DE.AE-2 |
| Information security event reporting | 6.8 | RS.CO-2 |

---

## Türkçe

# Loglama ve İzleme

## 1. Amaç

Loglama, Madde 5(2) hesap verebilirliği, Madde 32(1)(d) kapsamında olayların
algılanması ve soruşturulması ve Madde 33 kapsamında ihlal bildirimi için
gereken kanıtı üretir. Loglama kendi başına kişisel veri işler (IP adresleri,
kullanıcı kimlikleri, davranışsal olaylar) ve bu nedenle veri minimizasyonu
(Madde 5(1)(c)), amaç sınırlaması (Madde 5(1)(b)), saklama sınırlaması
(Madde 5(1)(e)) ve çalışan izleme söz konusu olduğunda Madde 88 ile uyumlu
olmalıdır.

## 2. Denetlenebilir Olay Kataloğu

ROPA kapsamındaki her sistem en azından şunları kapsayan loglar üretir:

### 2.1 Kimlik Doğrulama
- Sebep koduyla giriş başarısı ve başarısızlığı.
- MFA istemi verildi, kabul edildi, reddedildi.
- Oturum oluşturma, yenileme, iptal.
- Hesap kilitlenmesi ve açılması.
- Parola değişimi, kurtarma ve yönetici sıfırlaması.
- Token ihracı, yenileme, iptal.

### 2.2 Yetkilendirme ve Erişim
- Ayrıcalık yükseltme talebi, onay, kullanım.
- Erişim reddi (kaynak, eylem).
- Rol / grup üyeliği değişimi.
- Belgeler ve veri kümeleri üzerinde paylaşım değişimi.
- Kişisel verinin dışa aktarımı, indirilmesi, büyük sorgu.

### 2.3 Veri Operasyonları
- Kişisel veri kayıtlarında okuma, yazma, silme, geri yükleme (katmana göre
  örneklenmiş veya tam).
- Toplu işlem tetikleyicileri.
- Kişisel veriyi etkileyen şema ve konfigürasyon değişiklikleri.
- T4-T5 anahtarlarda kriptografik işlemler.
- `09-data-subject-rights/` uyarınca veri sahibi hakkı yürütümü (erişim,
  düzeltme, silme, taşınabilirlik).

### 2.4 Yönetimsel
- Hesap oluşturma, değiştirme, devre dışı bırakma, silme.
- İzin değişikliği, politika değişikliği, kural değişikliği.
- Sistem konfigürasyon değişikliği.
- Yama yükleme ve geri alma.

### 2.5 Güvenlik Olayları
- IDS / IPS algılaması.
- WAF engelleme / zorluk.
- DLP engelleme / uyarı.
- EDR algılama, karantina, izolasyon.
- Anti-malware olayları.

### 2.6 Güvenilirlik
- Servis başlatma, durdurma, çökme.
- Yedek başlatma, başarı, başarısızlık (`backup-recovery.md`).
- Geri yükleme yürütümü ve sonucu.
- Kapasite eşik aşımları.

## 3. Log Alanı Standardı

Her olay en azından şunları içerir:

| Alan | Notlar |
|------|--------|
| `timestamp` | Milisaniyeli RFC 3339 UTC |
| `event_id` | Kaynak sistem içinde benzersiz |
| `correlation_id` | İstek zinciri boyunca taşınır |
| `event_type` | Yukarıdaki katalogdan |
| `actor.subject_id` | Pseudonim kullanıcı / servis kimliği |
| `actor.session_id` | Geçerliyse |
| `actor.source_ip` | Kaynak IP kesinlikle gerekli değilse atılımda hashlenmiş |
| `target.system` | Uygulama veya sistem adı |
| `target.resource` | Geçerliyse kaynak tanımlayıcısı |
| `action` | Fiil (oku, yaz, sil...) |
| `outcome` | başarı / başarısızlık / reddedildi |
| `reason` | Başarısızlık veya reddetme sebebi |
| `data_subject_scope` | Eylemin kişisel veriyle ilgili olduğu yer |

Loglar şunları içermez:

- Açık metin parolalar, tokenlar, API anahtarları, MFA kodları.
- Açık metin ödeme verisi (PAN, CVV).
- Mutlaka gerekli olmadıkça Madde 9 özel nitelikli veri; gerekiyorsa alan
  maskelenmiş veya pseudonimleştirilmiş.
- Varsayılan olarak kişisel-veri uç noktalarının tam istek / yanıt gövdeleri.

## 4. Bütünlük

Madde 5(2) hesap verebilirliği ve Madde 32(1)(b) bütünlüğü, logların
müdahale-kanıtlı olmasını gerektirir:

- **Yalnızca ekle / WORM** - üretim logları nesne kilidi saklamayla yalnızca
  ekleme yapacak şekilde yapılandırılmış depolamaya iner.
- **Hash zinciri** - her olay grubu hashlenir (SHA-256) ve öncekine
  zincirlenir; zincir kökü SIEM imzalama anahtarıyla günlük imzalanır.
- **İmzalama** - kapatılmış günlük arşivler üzerinde denetim kasasında
  saklanan kriptografik imza.
- **Zaman kaynağı** - tüm sistemler yedekli yetkili bir zaman kaynağından
  senkronize olur (NTPv4 veya NTS); kayma > 100 ms uyarı tetikler.
- **Üç aylık bütünlük denetimi** - rastgele bir örnek üzerinde zinciri ve
  imzaları doğrula.

Yöneticilerin log erişimi ayrı bir kiracıya loglanır; GoA, aynı kimliğin hem
yönetip hem incelemesini engeller.

## 5. Merkezileştirme - SIEM ve UEBA

- Kapsamdaki tüm sistemler logları SIEM'e iletir (geçici kesintiler için
  güvenilir teslimat ve tamponlama ile).
- İletici mTLS veya imzalı tokenla kimlik doğrular.
- SIEM ortak şemaya normalleştirir.
- UEBA modülleri davranışsal temel çizgiler uygular ve şunları algılar:
  - Kimlik bilgisi doldurma ve parola sprey.
  - İmkânsız seyahat.
  - Ayrıcalık kötüye kullanımı.
  - Anormal veri sızıntı örüntüleri.
  - MFA yorgunluğu.
  - Iç tehdit göstergeleri (`dlp.md` DLP sinyalleriyle birleştirilir).
- Algılama içeriği sürüm kontrollü, peer review'lı, MITRE ATT&CK tekniklerine
  eşlenmiş.
- Algılama etkinliği aylık incelenir.

## 6. Saklama

Saklama programı Madde 5(1)(e) saklama sınırlamasını soruşturma ve yasal
ihtiyaçlarla dengeler. Loglar kişisel veridir; program `04-retention-erasure/`
ve gizlilik bildiriminde (`03-transparency-consent/`) beyan edilir.

| Log Sınıfı | Saklama | Gerekçe |
|------------|---------|---------|
| Kimlik doğrulama ve erişim | 12 ay sıcak, 24 ay soğuk | Soruşturma, ihlal müdahalesi |
| Ayrıcalıklı oturum kaydı | 24 ay | Yüksek etkili olaylar; zamanaşımı |
| Uygulama kişisel-veri denetimi | 24 ay | Hesap verebilirlik, veri sahibi talepleri |
| Güvenlik algılaması | 12 ay sıcak, 24 ay soğuk | Örüntü analizi |
| Ağ akışı | 90 gün sıcak, 12 ay örneklenmiş soğuk | Depolama orantılılığı |
| OS / sistem | 6 ay | Güvenilirlik sorun giderme |
| DLP olayları | 24 ay | Soruşturmalar, iş hukuku |
| Kritik finansal sistemler | 5 yıl | Vergi / ticari hukuk |
| Md. 9 verisi içeren loglar | Yasal yükümlülük daha uzun olmadıkça 6 ay | Veri minimizasyonu |

Saklama süresi sona erdiğinde loglar otomatik silinir. Silmeler kendileri
loglanır (değiştirilemez denetim). Silme taleplerini onurlandırmak için
seçici silme, indeks içindeki özne tanımlayıcılarının pseudonimizasyonuyla
gerçekleştirilir; tam kayıt sonraki rotasyonda kaldırılır; prosedür
`09-data-subject-rights/` altında belgelenir.

## 7. Orantılılık ve Madde 88

Çalışan etkinliğini yakalayan loglama (özellikle DLP, ZTNA oturum kaydı,
tarayıcı proxy logları) yüksek riskli izlemedir. Kontrolör:

- Dağıtımdan önce VKD yapar (`06-organizational-measures/dpia.md`).
- Toplamayı güvenlik, dolandırıcılık önleme veya yasal yükümlülük için
  kesinlikle gerekli alanlarla sınırlar.
- Kontrolörün meşru kapsamı dışındaki kişisel iletişim içeriğini hariç tutar
  (bankacılık, sağlık, sosyal - bkz. `network-security.md`).
- Çalışan gizlilik bildiriminde (`03-transparency-consent/`) yasal dayanak
  ile birlikte loglamayı açıklar (genellikle dengeleme testi sonrası Madde
  6(1)(f) meşru menfaat veya yasal gereklilikte Madde 6(1)(c)).
- Ulusal hukuk gerektiriyorsa işyeri konseyi / çalışan temsilcileriyle
  istişare eder (Madde 88 + toplu sözleşmeler).
- Çalışan etkinliği içeren loglara erişimi SOC ve yetkili soruşturmacılarla
  sınırlar; standart yöneticiler göz atamaz.

## 8. Loglara Erişim

- Okuma erişimi rol bazlı verilir (`access-control.md`).
- Adli erişim AAL3 artı belgelenmiş soruşturma vaka kimliği gerektirir.
- Analitik için logların toplu dışa aktarımı kaynakta pseudonimleştirilir.
- Tedarikçilerle veya işleyicilerle log paylaşımı DPA kapsamı gerektirir
  (`06-organizational-measures/vendor-management.md`).

## 9. Algılama Mühendisliği

- Algılamalar kod-incelenmiş bir formatta yazılır (Sigma, KQL, SPL, OPA).
- Her algılamanın:
  - Benzersiz kimliği.
  - Açıklaması ve tehdit referansı.
  - Yanlış-pozitif notları.
  - Ciddiyet.
  - Müdahale operasyon kitabı referansı (`08-breach-management/`).
- MITRE ATT&CK ve risk kayıt defterine hizalı algılama kapsamı haritası üç
  ayda bir yayımlanır.
- Mor takım tatbikatları yılda en az iki kez algılamaları doğrular.

## 10. Olay Bağlantısı

Bir algılama olaya yükseldiğinde:

- SIEM ilgili tüm olaylar ve destekleyici kanıtlarla bir vaka oluşturur.
- Soruşturmacılar notlar, IOC'ler ve zaman çizelgesi ekler.
- Vaka, Madde 33 / 34 ihlal sürecini besler (`08-breach-management/`).
- Kapanış, `06-organizational-measures/internal-audit.md` altında
  yakalanan bir CAPA içerir.

## 11. KPI'lar

| Metrik | Hedef |
|--------|-------|
| Log ileten kapsamdaki sistemler | %100 |
| Log teslimat güvenilirliği (5 dk üstü boşluk yok) | >= %99,9 |
| Kritik MTTD ortalama tespit süresi | <= 15 dakika |
| Yanlış-pozitif oranı (yüksek ciddiyetli uyarılar) | < %10 |
| Bütünlük doğrulamasında başarısız loglar | 0 |
| Saklama uyumluluğu denetim bulguları | 0 |
| Yüksek riskli izleme dağıtımı öncesi VKD tamamlama | %100 |

## 12. Eşleme

| Gereklilik | ISO 27002:2022 | NIST CSF 2.0 |
|------------|----------------|--------------|
| Loglama | 8.15 | DE.CM-1 |
| İzleme etkinlikleri | 8.16 | DE.CM-1 |
| Saat senkronizasyonu | 8.17 | PR.PS-2 |
| Algılama süreçleri | yok | DE.AE-2 |
| Bilgi güvenliği olayı raporlama | 6.8 | RS.CO-2 |
