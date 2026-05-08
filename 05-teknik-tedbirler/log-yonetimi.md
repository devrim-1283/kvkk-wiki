---
Doküman / Document: Log Yönetimi, SIEM ve Olay İzleme Politikası / Log Management, SIEM and Event Monitoring Policy
Bölüm / Section: 05-teknik-tedbirler
Sahip / Owner: SOC Lideri / CISO / SOC Lead / CISO
Onaylayan / Approved by: BT Direktörü + KVKK Komitesi / IT Director + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş (yeni log kaynağı, mevzuat, tespit gap) / Annual + triggered (new log source, regulation, detection gap)
İlgili Mevzuat / Legal Reference: Law No. 6698 KVKK Art. 12; Personal Data Security Guide — "Personal Data Security Monitoring", "Information Security Incident Management"; Law No. 5651 (Internet legislation) on the Regulation of Publications on the Internet and Combating Crimes Committed Through These Publications and the related Regulation (hosting/internal content provider log retention obligation)
İlgili Standart / Standard: ISO/IEC 27001:2022 A.8.15 (Logging), A.8.16 (Monitoring Activities), A.5.7 (Threat Intelligence); NIST CSF 2.0 DETECT (DE.AE, DE.CM, DE.DP); NIST SP 800-92 (Guide to Computer Security Log Management); MITRE ATT&CK; SANS SOC playbook framework; ENISA SIEM guidelines
---

## English

# Log Management, SIEM and Monitoring

## 1. Purpose

Defines an integrated framework of log + SIEM + detection + response for the collection, protection, analysis, detection of, and response to **every security-relevant event that has occurred, attempted to occur, or is suspicious** in personal data processing environments. The technical foundation of KVKK Art. 12's "preservation" and "detection in case of breach" obligations.

## 2. Definitions

| Term | Definition |
|-------|-------|
| Log | Event record of a system or application. |
| Telemetry | Broadly, event + metric + trace data. |
| SIEM | Security Information and Event Management — collection, normalization, correlation, alarm. |
| SOAR | Security Orchestration, Automation, Response — playbook automation. |
| UEBA | User and Entity Behavior Analytics — behavioral anomaly detection. |
| WORM | Write Once Read Many — immutable storage. |
| Threat Intel | Threat intelligence, IOC, TTP. |

## 3. Events to Log

### 3.1. Identity / Authentication

- Successful/failed login (user, IP, user agent, location, MFA status).
- Password change, reset, recovery flow.
- MFA challenge, failed MFA, push fatigue.
- Federation assertion (SAML/OIDC).
- Token generation, refresh, revocation.

### 3.2. Authorization

- Privilege elevation (sudo, runas, AssumeRole, PIM eligible → active).
- Changes in role/group membership.
- IAM policy add/remove.
- Access denial (DENY).
- Out-of-policy access attempt.

### 3.3. Personal Data Access Events

- SELECT from tables containing personal data (user, query summary, row count; query text — values masked).
- Personal data export / download (user, target, file, row count).
- Personal data printing.
- Sending email containing personal data (large attachment, bulk send).
- DDL on personal data table (CREATE/ALTER/DROP/TRUNCATE).
- Bulk delete/update.
- Bulk read via API.

### 3.4. System Administrator Activities

- Service start/stop.
- Configuration change.
- New account creation.
- Log clearing/stopping — **critical alarm**.
- Time change — **critical alarm**.
- Backup/restore operation.
- Key use (KMS/HSM).

### 3.5. Network and Perimeter

- Firewall: permitted/denied traffic.
- WAF: rule trigger.
- IDS/IPS: all alerts.
- VPN/ZTNA: connection.
- DNS query response.
- Proxy URL access.

### 3.6. Application Events

- Error messages (sanitized so as not to contain personal data).
- Payment, registration, account creation, account deletion, data subject request.
- Explicit consent record changes.
- Configuration changes.

### 3.7. Other

- Antivirus / EDR event.
- Backup success/failure.
- Approaching certificate expiry.
- DLP event.

## 4. Log Content — Personal Data Minimization

Logging is not "take everything". Logs themselves are an **environment of personal data**.

### 4.1. Forbidden / Restricted Content

- Password, OTP, secret, API key, certificate private key — **never**.
- Full card number (PAN) — **never**; at most BIN + last 4.
- CVV/CVC — **never**.
- Turkish ID number, health data plaintext — **masked** or hashed.
- Email body, message content — **none unless required**.
- Call recordings — only purpose-fit + KVKK notice + retention period.

### 4.2. Recommended Content

- Event time (UTC + timezone).
- Event type (taxonomy).
- Actor (user/service/system) — username + user ID.
- Target (resource/system/record reference).
- Result (success/failure + reason code).
- Context (IP, user agent, session ID, correlation ID).
- For sensitive data, **reference** (record ID), not value.

### 4.3. Sanitization

- Application logs, automatic PII redaction at SDK level.
- Regex-based scanner sanitizes during ingestion (Turkish ID, IBAN, card).
- Log alarm + remediation in "couldn't catch it" cases.

## 5. Log Integrity

Logs are an asset where an attacker may modify them and cover their tracks. Integrity is mandatory.

### 5.1. Controls

- **Centralized collection** — the host generating the log differs from where it is stored.
- **WORM storage** — written log cannot be modified/deleted during retention period (S3 Object Lock — Compliance Mode, Azure Immutable Blob, Glacier Vault Lock).
- **Hashing & Signing** — each particle hashed during ingest, periodically signed (Merkle tree recommended).
- **Separate authority** — log administrator and system administrator are different persons (segregation of duties).
- **Time synchronization** — all systems NTP synced, at least 100ms tolerance.
- **Full transmission** — only transit buffer on the host; alarm when send fails.

### 5.2. Breach Detection

- Log flow interruption → alarm within 5 minutes.
- Break in hash chain → critical alarm + IR.
- Attempt to delete logs by unauthorized person → critical alarm + IR.

## 6. SIEM Architecture

### 6.1. Components

```
Sources → Collector (Beats/Fluentd/Vector/syslog) → Pipeline (parse/enrich/sanitize) →
   → Hot tier (search, dashboard, alarm — 90 days) →
   → Warm tier (long search, cheaper — 1 year) →
   → Cold/Archive (WORM, end of retention — 2-7 years)
```

### 6.2. Normalization

- Use ECS (Elastic Common Schema) or OCSF (Open Cybersecurity Schema Framework).
- All sources translated to the same fields.

### 6.3. Enrichment

- User context (department, location, sensitivity level).
- IP → geolocation, ASN, threat intel.
- Device → compliance status.
- Asset → CMDB (does it contain personal data, which system).

### 6.4. Correlation

- Rule-based (Sigma, vendor format).
- Behavioral (UEBA — user/entity baseline).
- Threat-intel matching.
- Multi-stage attack detection (e.g., failed brute force → successful login → privilege elevation → data read).

### 6.5. Detection Content — Canonical Use Cases (KVKK-focused)

| Use Case | Trigger | Severity |
|----------|-------|----------|
| Unauthorized personal data access | User SELECT on out-of-RBAC table | Critical |
| Bulk personal data exfiltration | Outbound > 100 MB / short time / less-known domain | Critical |
| Log deletion/stop | Audit service stopped, log file rm | Critical |
| Privileged session out-of-hours | Admin → personal data DB outside business hours | High |
| Push fatigue | 10+ MFA push within 5 min | High |
| Atypical travel | Same user in two countries within 1 hour | High |
| Card data in log | Regex trigger PAN plaintext log | Critical |
| Backup failure | Backup job fail + 24 hours no retry | High |
| Certificate expiry | < 7 days | High |
| New IAM role with personal data privilege | Provisioning event | Medium |
| Anomalous API call volume | Endpoint baseline +5σ | Medium |
| Successful login from malicious IP | Threat intel hit | Critical |
| Cleartext HTTP → personal data application | Prod TLS bypass | High |
| New service account + critical privilege | Provisioning + privilege | High |
| Bulk DELETE/UPDATE on dataset | DML threshold | High |

### 6.6. UEBA

- User baseline: typical login time, location, device, accessed datasets.
- Deviation → "anomalous score" → SOC trigger.
- Foundational building block for insider threat detection.

## 7. Retention Period

| Log Type | Hot | Warm | Cold/Archive | Total |
|----------|-----|------|--------------|--------|
| Identity / authorization | 90 days | 1 year | 4 years | **5 years** |
| Personal data access | 90 days | 1 year | 4 years | **5 years** |
| System administrator | 90 days | 1 year | 1 year | **2 years** (5 years for critical) |
| Network / firewall | 90 days | 9 months | – | **1 year** |
| WAF | 90 days | 9 months | – | **1 year** |
| Application | 90 days | 9 months | – | **1 year** |
| Backup | 90 days | 1 year | 4 years | **5 years** |
| Law No. 5651 (if hosting provider) | – | – | – | Per law **2 years** to 10 years per relevant regulation |
| PCI scope (if applicable) | 90 days online | – | 1 year archive | 1 year (PCI minimum) |

> End of retention period **automatic destruction** — manual extension only for active investigation / legal hold and with justification.

## 8. Law No. 5651 Framework

If our activity is "hosting provider" or "internal content provider":

- Access and traffic information are kept for the period defined by law.
- Integrity is preserved within retention period, can be transmitted electronically upon authority request.
- Ensuring the **accuracy, integrity, and confidentiality** of stored information is the obligation of the hosting provider.
- Logs in this scope are managed with **separate access** from KVKK personal data logs; owner is Legal + CISO.

## 9. SOC Operations

### 9.1. Shift Structure

- 7/24 monitoring (depending on organization size).
- 3 shifts (08-16, 16-00, 00-08), Tier-1 / Tier-2 / Tier-3 + Threat Hunting.
- Shift handover form, open tickets, ongoing incidents, escalation chain.

### 9.2. Escalation Chain

```
Tier-1 (triage, false positive elimination) → Tier-2 (analysis, IOC, containment) →
   → Tier-3 (deep forensic, lateral movement, comprehensive IR)
   → CISO + KVKK Officer (possibility of personal data breach) → KVKK Committee → Management
```

### 9.3. Ticket Lifecycle

- New → Triage → Confirmed True / False → Containment → Eradication → Recovery → Closed → Lessons Learned.
- MTTD, MTTR measured for each ticket.

## 10. Runbooks (Example Titles)

Standard format for each runbook: trigger, fast diagnosis, contain, eradicate, recover, evidence collection, KVKK Committee notification threshold.

- **RB-01 Suspected Unauthorized Personal Data Access**
- **RB-02 Data Exfiltration**
- **RB-03 Ransomware**
- **RB-04 Phishing — User Provided Credentials**
- **RB-05 Web Defacement**
- **RB-06 Privilege Escalation + Lateral Movement**
- **RB-07 Backup Failure + Failed Restore Test**
- **RB-08 PAM Break-Glass Use**
- **RB-09 SaaS Account Takeover (BEC)**
- **RB-10 DDoS**
- **RB-11 Suspicious SaaS DLP Event**
- **RB-12 Lost/Stolen Device**

## 11. Evidence and Forensics

- When an incident is detected, "evidence preservation" kicks in:
  - RAM dump of the affected system (if possible).
  - Disk image (dd, F-Response, EnCase).
  - Log snapshot — immutable copy.
  - Network capture (PCAP) — relevant window.
- Chain of custody document signed, evidence storage locked/encrypted.
- Reference to NIST IR 8444 / ISO 27037 for usability in legal process.

## 12. KVKK Committee Notification Threshold

Coordinated with breach management (08):

- **Within 24 hours from detection of suspected personal data breach**, the KVKK Committee is informed.
- Following confirmed breach, preparation for notification to the Authority within **72 hours** (KVKK Art. 12(5)).
- KVKK Officer, Legal, CISO are permanent members of the response team.

## 13. Threat Intelligence

- IOC feed (commercial + open — AlienVault OTX, MISP, abuse.ch, vendor).
- Sectoral sharing — CERT, sector ISAC.
- In-house IOC generation — extract IOCs from closed incidents, inject into searches.
- TIP (Threat Intelligence Platform) integration with SIEM/EDR/FW.

## 14. SOAR Automation

- Playbook automation in common scenarios:
  - Phishing URL report → sandbox → extract IOC → block FW/Proxy/Email.
  - Suspicious login → log out user session + force password change + MFA reset request.
  - EDR detection → isolate host + ticket + assign analyst.
- Automatic actions with approval chain (auto isolate yes, auto data deletion no).

## 15. Test and Validation

- **Atomic Red Team / Caldera** measures detectability of MITRE ATT&CK techniques annually (purple team).
- **Tabletop** exercises quarterly (CISO + HR + Legal + KVKK + Communications attend).
- **Trigger test** — positive test scenario for every new alarm rule.

## 16. KPIs

- MTTD (Mean Time To Detect) — target ≤ 1 hour (critical).
- MTTR (Mean Time To Respond) — target ≤ 4 hours (critical).
- False positive rate — ≤ 20%.
- Coverage: percentage of critical assets logged — 100%.
- Log latency — average ≤ 5 min.
- Resolved high incident count / total — monthly trend.
- Drill detection rate — 85%+.

## 17. Checklist

- [ ] Are all critical sources sending logs to SIEM? (Coverage ≥ 95%)
- [ ] Does log content apply personal data minimization (PII redaction)?
- [ ] Is log integrity protected with WORM + hash chain?
- [ ] Is time synchronization (NTP) on all systems?
- [ ] Is the log flow interruption alarm triggered within 5 min?
- [ ] Is the retention policy compliant with KVKK + Law No. 5651 + sectoral legislation?
- [ ] Is end-of-retention automatic destruction working?
- [ ] Is SOC 7/24 + escalation chain defined, KVKK Officer in IR team?
- [ ] Are runbooks updated annually + validated by drill?
- [ ] Is the KVKK Officer in the IR team, is the 24-hour threshold documented?
- [ ] Is UEBA + threat intel integrated with SIEM?
- [ ] Was Atomic Red Team / purple team performed annually?
- [ ] Is the forensic chain of custody procedure ready?
- [ ] If PCI/health/finance, are sectoral retention rules additionally applied?
- [ ] Are privileged log administrator + system administrator different persons?
- [ ] Is there no forbidden data such as card numbers, OTPs in logs (regex scan validation)?

---

## Türkçe

# Log Yönetimi, SIEM ve İzleme

## 1. Amaç

Kişisel veri işleme ortamlarında **gerçekleşen, gerçekleşmeye çalışılan ve şüpheli** her güvenlik açısından önemli olayın toplanması, korunması, analizi, tespit edilmesi ve müdahale edilmesi için bütünleşik bir log + SIEM + tespit + müdahale çerçevesi tanımlar. KVKK m.12'nin "muhafaza" ve "ihlal halinde tespit" yükümlülüklerinin teknik temelidir.

## 2. Tanımlar

| Terim | Tanım |
|-------|-------|
| Log | Bir sistem veya uygulamanın olay kaydı. |
| Telemetri | Geniş anlamda olay + metrik + iz (trace) verisi. |
| SIEM | Security Information and Event Management — toplama, normalizasyon, korelasyon, alarm. |
| SOAR | Security Orchestration, Automation, Response — playbook otomasyonu. |
| UEBA | User and Entity Behavior Analytics — davranışsal anomali tespiti. |
| WORM | Write Once Read Many — değiştirilemez depolama. |
| Threat Intel | Tehdit istihbaratı, IOC, TTP. |

## 3. Loglanacak Olaylar

### 3.1. Kimlik / Kimlik Doğrulama

- Başarılı/başarısız oturum açma (kullanıcı, IP, kullanıcı agent, lokasyon, MFA durumu).
- Parola değişimi, sıfırlama, kurtarma akışı.
- MFA challenge, başarısız MFA, push fatigue.
- Federation assertion (SAML/OIDC).
- Token üretim, refresh, iptal.

### 3.2. Yetkilendirme

- Yetki yükseltme (sudo, runas, AssumeRole, PIM eligible → active).
- Rol/grup üyeliğinde değişiklik.
- IAM policy ekleme/silme.
- Erişim reddi (DENY).
- Politika dışı erişim girişimi.

### 3.3. Kişisel Veri Erişim Olayları

- Kişisel veri içeren tablolardan SELECT (kullanıcı, sorgu özeti, satır sayısı; sorgu metni — değerler maskelenmiş).
- Kişisel veri export / indirme (kullanıcı, hedef, dosya, satır sayısı).
- Kişisel veri yazdırma.
- Kişisel veri içeren e-posta gönderimi (büyük ek, yığın gönderim).
- Kişisel veri tablosu üzerinde DDL (CREATE/ALTER/DROP/TRUNCATE).
- Toplu silme/güncelleme.
- API üzerinden bulk read.

### 3.4. Sistem Yöneticisi Etkinlikleri

- Servis başlatma/durdurma.
- Konfigürasyon değişikliği.
- Yeni hesap oluşturma.
- Log temizleme/durdurma — **kritik alarm**.
- Saat değişikliği — **kritik alarm**.
- Yedek/restore işlemi.
- Anahtar kullanımı (KMS/HSM).

### 3.5. Ağ ve Çevre

- Firewall: izinli/izinsiz trafik.
- WAF: kural tetiklenmesi.
- IDS/IPS: tüm uyarı.
- VPN/ZTNA: bağlantı.
- DNS sorgu yanıt.
- Proxy URL erişim.

### 3.6. Uygulama Olayları

- Hata mesajları (kişisel veri içermeyecek şekilde sanitized).
- Ödeme, kayıt, hesap oluşturma, hesap silme, ilgili kişi başvurusu.
- Açık rıza kayıt değişimleri.
- Yapılandırma değişiklikleri.

### 3.7. Diğer

- Antivirüs / EDR olay.
- Yedek başarı/başarısız.
- Sertifika sona erme yaklaşımı.
- DLP olay.

## 4. Log İçeriği — Kişisel Veri Minimizasyonu

Loglama "her şeyi al" değildir. Loglar başlı başına **kişisel veri ortamıdır**.

### 4.1. Yasak / Sınırlı İçerik

- Parola, OTP, secret, API key, sertifika özel anahtarı — **asla**.
- Kart numarası tam (PAN) — **asla**; en fazla BIN + son 4.
- CVV/CVC — **asla**.
- TC kimlik no, sağlık verisi düz metin — **maskeli** veya hash.
- E-posta gövdesi, mesaj içeriği — **gerekmedikçe yok**.
- Çağrı kayıtları — sadece amaca uygun + KVKK aydınlatma + saklama süresi.

### 4.2. Önerilen İçerik

- Olay zamanı (UTC + saat dilimi).
- Olay türü (taxonomy).
- Aktör (kullanıcı/servis/sistem) — kullanıcı adı + kullanıcı ID.
- Hedef (kaynak/sistem/kayıt referansı).
- Sonuç (success/failure + reason code).
- Bağlam (IP, kullanıcı agent, oturum ID, korelasyon ID).
- Hassas veri varsa **referans** (kayıt ID), değer değil.

### 4.3. Sanitization

- Uygulama logları, SDK seviyesinde otomatik PII redaction.
- Düzenli ifade tabanlı tarayıcı (TC kimlik, IBAN, kart) ingestion'da sterilizasyon.
- "Tutamadık" durumlarda log alarmı + remediasyon.

## 5. Log Bütünlüğü

Loglar saldırganın değiştirip izini kapatabileceği bir varlıktır. Bütünlük zorunludur.

### 5.1. Kontroller

- **Merkezi toplama** — log üreten ana makine ile saklanan yer farklıdır.
- **WORM depolama** — yazılan log, retention süresi boyunca değiştirilemez/silinemez (S3 Object Lock — Compliance Mode, Azure Immutable Blob, Glacier Vault Lock).
- **Hashing & Signing** — ingest sırasında her partikül hash'lenir, periyodik olarak imzalanır (Merkle tree önerilir).
- **Ayrı yetki** — log yöneticisi ile sistem yöneticisi farklı kişilerdir (görev ayrılığı).
- **Saat senkronizasyonu** — tüm sistemler NTP ile senkron, en az 100ms tolerans.
- **Tam taşıma** — ana makinede sadece transit buffer; gönderim başarısız olduğunda alarm.

### 5.2. İhlal Tespiti

- Log akış kesilmesi → 5 dakika içinde alarm.
- Hash zincirinde kopukluk → kritik alarm + IR.
- Yetkili olmayan kişi tarafından log silme girişimi → kritik alarm.

## 6. SIEM Mimarisi

### 6.1. Bileşenler

```
Kaynaklar → Toplayıcı (Beats/Fluentd/Vector/syslog) → Pipeline (parse/enrich/sanitize) →
   → Hot tier (arama, dashboard, alarm — 90 gün) →
   → Warm tier (uzun arama, daha ucuz — 1 yıl) →
   → Cold/Archive (WORM, retention sonu — 2-7 yıl)
```

### 6.2. Normalizasyon

- ECS (Elastic Common Schema) veya OCSF (Open Cybersecurity Schema Framework) kullan.
- Tüm kaynaklar aynı alanlara çevrilir.

### 6.3. Enrichment

- Kullanıcı bağlamı (departman, lokasyon, hassasiyet seviyesi).
- IP → coğrafi konum, ASN, threat intel.
- Cihaz → uyumluluk durumu.
- Asset → CMDB (kişisel veri var mı, hangi sistem).

### 6.4. Korelasyon

- Kural tabanlı (Sigma, vendor formatı).
- Davranışsal (UEBA — user/entity baseline).
- Threat-intel eşleştirme.
- Multi-stage attack tespiti (örn. başarısız brute force → başarılı giriş → yetki yükseltme → veri okuma).

### 6.5. Tespit İçeriği — Kanonik Use Case'ler (KVKK odaklı)

| Use Case | Tetik | Aciliyet |
|----------|-------|----------|
| Yetkili olmayan kişisel veri erişimi | Kullanıcı RBAC dışı tablo SELECT | Kritik |
| Toplu kişisel veri exfiltration | Outbound > 100 MB / kısa süre / az bilinen domain | Kritik |
| Log silme/durdurma | Audit servis durdurma, log dosyası rm | Kritik |
| Ayrıcalıklı oturum saat dışı | Admin → kişisel veri DB iş saati dışı | Yüksek |
| Push fatigue | 10+ MFA push 5 dk içinde | Yüksek |
| Atypical travel | Aynı kullanıcı 1 saatte iki ülke | Yüksek |
| Kart verisi log'da | Regex tetik PAN düz metin log | Kritik |
| Yedek başarısızlık | Yedek job fail + 24 saat retry yok | Yüksek |
| Sertifika sona erme | < 7 gün | Yüksek |
| Yeni IAM rol kişisel veri yetkili | Provisioning olay | Orta |
| Anormal API çağrı hacmi | Endpoint baseline +5σ | Orta |
| Kötü amaçlı IP'den giriş başarılı | Threat intel hit | Kritik |
| Şifresiz HTTP → kişisel veri uygulaması | Prod TLS bypass | Yüksek |
| Yeni servis hesabı + kritik yetki | Provisioning + yetki | Yüksek |
| Veri kümesinde toplu DELETE/UPDATE | DML threshold | Yüksek |

### 6.6. UEBA

- Kullanıcı baseline: tipik giriş saati, lokasyon, cihaz, eriştiği veri kümeleri.
- Sapma → "anomalous score" → SOC tetik.
- Insider threat tespitinin temel yapı taşı.

## 7. Saklama Süresi

| Log Türü | Hot | Warm | Cold/Archive | Toplam |
|----------|-----|------|--------------|--------|
| Kimlik / yetki | 90 gün | 1 yıl | 4 yıl | **5 yıl** |
| Kişisel veri erişim | 90 gün | 1 yıl | 4 yıl | **5 yıl** |
| Sistem yöneticisi | 90 gün | 1 yıl | 1 yıl | **2 yıl** (kritik için 5 yıl) |
| Ağ / firewall | 90 gün | 9 ay | – | **1 yıl** |
| WAF | 90 gün | 9 ay | – | **1 yıl** |
| Uygulama | 90 gün | 9 ay | – | **1 yıl** |
| Yedek | 90 gün | 1 yıl | 4 yıl | **5 yıl** |
| 5651 (yer sağlayıcıysak) | – | – | – | Kanun gereği **2 yıl** ila 10 yıl arası ilgili düzenlemeye göre |
| PCI scope (uygulanırsa) | 90 gün online | – | 1 yıl arşiv | 1 yıl (PCI minimum) |

> Saklama süresi sonu **otomatik imha** — manuel uzatma yalnızca aktif soruşturma / hukuki tutma (legal hold) için ve gerekçeli.

## 8. 5651 Sayılı Kanun Çerçevesi

Eğer faaliyet kapsamımız "yer sağlayıcı" veya "iç içerik sağlayıcı" niteliğindeyse:

- Erişim ve trafik bilgileri kanunda tanımlı süre kadar saklanır.
- Saklama süresi içinde bütünlük korunur, yetkili merciin talebine elektronik ortamda iletilebilir.
- Saklanan bilgilerin **doğruluğunu, bütünlüğünü ve gizliliğini** sağlamak yer sağlayıcının yükümlülüğüdür.
- Bu kapsamdaki loglar, KVKK kapsamındaki kişisel veri logundan **ayrı erişim** ile yönetilir; sahibi Hukuk + CISO.

## 9. SOC Operasyonları

### 9.1. Vardiya Yapısı

- 7/24 izleme (kurum büyüklüğü gerektiriyor).
- 3 vardiya (08-16, 16-00, 00-08), Tier-1 / Tier-2 / Tier-3 + Threat Hunting.
- Vardiya devir formu, açık biletler, devam eden olaylar, eskalasyon zinciri.

### 9.2. Eskalasyon Zinciri

```
Tier-1 (triage, yanlış pozitif elemesi) → Tier-2 (analiz, IOC, sınırlama) →
   → Tier-3 (derin forensic, lateral movement, kapsamlı IR)
   → CISO + KVKK Sorumlusu (kişisel veri ihlali ihtimali) → KVKK Komitesi → Yönetim
```

### 9.3. Bilet Yaşam Döngüsü

- New → Triage → Confirmed True / False → Containment → Eradication → Recovery → Closed → Lessons Learned.
- Her bilet için MTTD, MTTR ölçülür.

## 10. Runbook'lar (Örnek Başlıklar)

Her runbook standart format: tetikleyici, hızlı tanı, konteyner, eradicate, recover, kanıt toplama, KVKK Komitesine bildirim eşiği.

- **RB-01 Yetkili Olmayan Kişisel Veri Erişim Şüphesi**
- **RB-02 Veri Exfiltration**
- **RB-03 Ransomware**
- **RB-04 Phishing — Kullanıcı Kimlik Bilgisi Verdi**
- **RB-05 Web Defacement**
- **RB-06 Yetki Yükseltme + Lateral Movement**
- **RB-07 Yedek Başarısız + Restore Test Başarısız**
- **RB-08 PAM Break-Glass Kullanımı**
- **RB-09 SaaS Hesap Ele Geçirme (BEC)**
- **RB-10 DDoS**
- **RB-11 Şüpheli SaaS DLP Olayı**
- **RB-12 Kayıp/Çalıntı Cihaz**

## 11. Kanıt ve Forensic

- Bir olay tespit edildiğinde "evidence preservation" devreye girer:
  - Etkilenen sistemin RAM dump'ı (mümkünse).
  - Disk imajı (dd, F-Response, EnCase).
  - Log snapshot — değiştirilemez kopya.
  - Network capture (PCAP) — ilgili pencere.
- Chain of custody belgesi imzalanır, kanıt saklama yeri kilitli/şifreli.
- Hukuki süreçte kullanılabilirlik için NIST IR 8444 / ISO 27037 referansı.

## 12. KVKK Komitesi Bildirim Eşiği

İhlal yönetimi (08) ile koordineli:

- **Kişisel veri ihlali şüphesi** tespit edildiği andan itibaren 24 saat içinde KVKK Komitesi bilgilendirilir.
- **Doğrulanmış ihlal** sonrası 72 saat içinde Kurul'a bildirim hazırlığı (KVKK m.12(5)).
- Müdahale ekibi içinde KVKK Sorumlusu, Hukuk, CISO sabit üye.

## 13. Threat Intelligence

- IOC feed (commercial + open — AlienVault OTX, MISP, abuse.ch, vendor).
- Sektörel paylaşım — CERT, sektör ISAC.
- Kurum içi IOC üretimi — kapatılan olaylardan IOC çıkar, aramaya enjekte et.
- TIP (Threat Intelligence Platform) ile SIEM/EDR/FW entegrasyonu.

## 14. SOAR Otomasyonu

- Yaygın senaryolarda playbook otomasyonu:
  - Phishing URL bildirimi → sandbox → IOC çıkar → block FW/Proxy/Email.
  - Şüpheli giriş → kullanıcı oturum kapat + parola force change + MFA reset talebi.
  - EDR detection → host isolate + ticket + analyst atama.
- Otomatik aksiyonlar onay zinciri ile (otomatik isolate olur, otomatik veri silme olmaz).

## 15. Test ve Doğrulama

- **Atomic Red Team / Caldera** ile MITRE ATT&CK tekniklerinin tespit edilebilirliği yıllık ölçülür (purple team).
- **Tabletop** egzersizleri çeyreklik (CISO + İK + Hukuk + KVKK + İletişim katılır).
- **Tetik testi** — her yeni alarm kuralı için pozitif test senaryosu.

## 16. KPI

- MTTD (Mean Time To Detect) — hedef ≤ 1 saat (kritik).
- MTTR (Mean Time To Respond) — hedef ≤ 4 saat (kritik).
- False positive oranı — ≤ %20.
- Kapsam: kritik varlıkların loglanma yüzdesi — %100.
- Log gecikmesi — ortalama ≤ 5 dk.
- Çözümlenmiş yüksek olay sayısı / toplam — aylık trend.
- Tatbikat tespit oranı — %85+.

## 17. Kontrol Listesi

- [ ] Tüm kritik kaynaklar SIEM'e log gönderiyor mu? (Kapsam ≥ %95)
- [ ] Log içeriği kişisel veri minimizasyonu uyguluyor mu (PII redaction)?
- [ ] Log bütünlüğü WORM + hash zinciri ile korunuyor mu?
- [ ] Saat senkronizasyonu (NTP) tüm sistemlerde mi?
- [ ] Log akışı kesilmesi alarmı 5 dk içinde tetikliyor mu?
- [ ] Saklama politikası KVKK + 5651 + sektörel mevzuata uyumlu mu?
- [ ] Saklama sonu otomatik imha çalışıyor mu?
- [ ] SOC 7/24 + eskalasyon zinciri belirli mi?
- [ ] Runbook'lar yıllık güncel + tatbikatla doğrulanmış mı?
- [ ] KVKK Sorumlusu IR ekibinde mi, 24 saat eşik yazılı mı?
- [ ] UEBA + threat intel SIEM'le entegre mi?
- [ ] Atomic Red Team / purple team yıllık yapıldı mı?
- [ ] Forensic kanıt zinciri (chain of custody) prosedürü hazır mı?
- [ ] PCI/sağlık/finans varsa sektörel saklama kuralı ek olarak uygulanıyor mu?
- [ ] Ayrıcalıklı log yöneticisi + sistem yöneticisi farklı kişiler mi?
- [ ] Kart numarası, OTP gibi yasaklı veri log'larda yok mu (regex tarama doğrulaması)?
