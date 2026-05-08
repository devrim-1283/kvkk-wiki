---
title:
  en: "Destruction Record Template"
  tr: "İmha Kaydı Şablonu"
section: "04-retention-erasure"
document_type: "form_template"
regulation: "GDPR (EU 2016/679)"
articles:
  - "Art. 5(1)(e) — Storage limitation"
  - "Art. 5(2) — Accountability"
  - "Art. 30 — Records of processing activities"
related_standards:
  - "NIST SP 800-88 Rev. 1"
  - "DIN 66399 / ISO 21964"
  - "ISO/IEC 27001:2022 (A.5.33, A.8.10)"
language: "en, tr"
last_reviewed: "2025-05-01"
review_cycle: "annual"
owner: "Data Protection Officer"
status: "approved"
classification: "internal"
---

## English

# Destruction Record Template

A destruction record is the audit-grade evidence that personal data has been securely and irreversibly destroyed. Each destruction event — automated cycle, ad-hoc execution, decommissioning, paper shred, processor confirmation — must produce a record using this template (or a system-generated equivalent that captures the same fields).

## 1. Form

> Use one form per batch. A "batch" is a coherent destruction event (one cycle, one media type, one processor, one paper-bin pickup). High-volume automated cycles may aggregate at the cycle level with a sampled per-record audit trail.

### 1.1 Header

| Field | Value |
|---|---|
| Destruction Record ID | `DR-YYYY-NNNN` |
| Date of destruction (start) | YYYY-MM-DD HH:MM TZ |
| Date of destruction (completion) | YYYY-MM-DD HH:MM TZ |
| Cycle reference (if applicable) | `CYCLE-YYYY-QN` |
| Linked DSAR reference (if applicable) | `DSAR-YYYY-NNNN` |
| Linked exception reference (if applicable) | `EXC-YYYY-NNNN` |
| Classification | Internal / Confidential / Restricted |

### 1.2 Subject of destruction

| Field | Value |
|---|---|
| Data category (per Retention Schedule) | e.g., Payroll records 2014 |
| Number of records / volume | e.g., 1,250 records / 8 GB / 12 boxes |
| Source system(s) | e.g., HRIS production, HRIS backup, paper archive Section 3 |
| Lawful trigger | e.g., Retention period expired (10 years) |
| Retention rationale (basis for prior retention) | e.g., German tax law § 147 AO |

### 1.3 Method

| Field | Value |
|---|---|
| Method | Database row delete / Crypto-shred / Secure overwrite / Degauss / Paper shred / Physical destruction |
| NIST level | Clear / Purge / Destroy |
| Standard / specification | e.g., NIST SP 800-88 Purge; DIN 66399 P-5 |
| Tool / supplier | e.g., `pgsql DELETE`; AWS KMS key destruction; Iron Mountain on-site shredder |
| Tool version / firmware | e.g., PostgreSQL 15.3; KMS API v2; truck #INFOSEC-7 |

### 1.4 Operators

| Field | Value |
|---|---|
| Operator (executed by) | Name, role, employee ID |
| Witness (where required) | Name, role, employee ID |
| Approver (Data Owner) | Name, role |
| DPO sign-off (where required) | Name, signature, date |

### 1.5 Verification

| Field | Value |
|---|---|
| Verification method | e.g., Sample row read; KMS audit log; sector sample; supplier certificate |
| Verification result | Success / Anomaly (with detail) |
| Verification evidence (reference) | Path to evidence: log file, screenshot, certificate PDF |

### 1.6 Backup handling

| Field | Value |
|---|---|
| Backups in scope? | Yes / No |
| Backup encryption status | Encrypted with key under controller management / Not encrypted |
| Backup erasure approach | Crypto-shred / Lifecycle expiry / Restriction + later expiry |
| Key destruction reference | KMS event ID, timestamp |
| Expected expiry of remaining ciphertext | YYYY-MM-DD |
| Compensating controls during residual retention | e.g., Read access disabled; processor restriction confirmed |

### 1.7 Recipient / processor / sub-processor notification

| Field | Value |
|---|---|
| Recipients in scope (Art. 19)? | Yes / No |
| List of recipients notified | Name, contact, notification date |
| Acknowledgement received? | Yes / No / Date pending |
| Sub-processors propagated? | Yes / No / N/A |
| Processor destruction certificate(s) | Reference + evidence path |

### 1.8 Anomalies and remediation

| Field | Value |
|---|---|
| Any anomalies during destruction? | Yes / No |
| Description | Free text |
| Remediation plan | Owner, action, target date |
| DPO informed? | Yes / No / N/A |

### 1.9 Sign-off

| Role | Name | Signature | Date |
|---|---|---|---|
| Operator | | | |
| Witness (if required) | | | |
| Data Owner | | | |
| DPO (if required) | | | |
| Information Security (verification) | | | |

### 1.10 Retention of this record

This destruction record is retained for **at least 6 years** from the date of destruction (or longer where local audit / regulatory law requires) under the Audit and Accountability category of the Retention Schedule.

---

## 2. Worked examples

### 2.1 Example A — Paper shred (HR archive)

| Field | Value |
|---|---|
| Destruction Record ID | `DR-2025-0142` |
| Date of destruction (start) | 2025-04-15 09:30 CET |
| Date of destruction (completion) | 2025-04-15 11:10 CET |
| Cycle reference | `CYCLE-2025-Q2` |
| Classification | Restricted |
| **Subject of destruction** | |
| Data category | Job applications 2017 (unsuccessful applicants); CV photocopies and interview notes |
| Volume | 12 standard archive boxes (~ 720 dossiers) |
| Source system(s) | HR archive room B-104, shelves 11–14 |
| Lawful trigger | Retention period expired (6 months original retention; held under exception until 2018; ordinary retention expired 2017+1y, exception lifted 2018, batch swept in this cycle) |
| Retention rationale (prior) | Original: legitimate interest + legal claims (AGG § 15 — 6 months). Exception: pending audit reference. |
| **Method** | |
| Method | Paper shred (off-site mobile shredder) |
| NIST level | Destroy |
| Standard | DIN 66399 P-5 (≤30 mm² particle size) |
| Tool / supplier | "[Shredding Vendor Ltd]"; truck #SVL-219; certified ISO 21964-2 P-5 |
| Tool version | Mobile shredder model XYZ-500; calibration date 2025-02-10 |
| **Operators** | |
| Operator | Hans Müller, Facilities Coordinator, EID 4421 |
| Witness | Lena Bauer, HR Records Officer, EID 8821 |
| Approver (Data Owner) | Sabine Becker, HR Director |
| DPO sign-off | Yes (high volume, sensitive context) — Dr. F. Klein, 2025-04-16 |
| **Verification** | |
| Verification method | Witnessed loading; on-site shredding observed; supplier certificate received |
| Verification result | Success |
| Verification evidence | `/dpo/destruction/2025/DR-2025-0142/SVL-cert-219.pdf`; `/dpo/destruction/2025/DR-2025-0142/witness-form.pdf` |
| **Backups in scope?** | No (paper-only category) |
| **Recipients in scope?** | No |
| **Anomalies?** | No |
| **Sign-off** | All present and signed |
| **Notes** | Particle size sample-checked at 09:55 CET; conformant. |

### 2.2 Example B — HDD degauss + physical destruction (decommissioned servers)

| Field | Value |
|---|---|
| Destruction Record ID | `DR-2025-0218` |
| Date of destruction (start) | 2025-05-22 13:00 CET |
| Date of destruction (completion) | 2025-05-22 17:45 CET |
| Cycle reference | `DECOM-2025-DC1-LOT-7` |
| Classification | Restricted |
| **Subject of destruction** | |
| Data category | Mixed: production database backups; CCTV recorder drives; legacy file server drives. Categories include customer transactions (encrypted at rest), CCTV (employee/visitor footage), and HR archives. |
| Volume | 38 HDDs (3.5" SAS, 1–8 TB each); total raw capacity ~ 142 TB |
| Source system(s) | Datacenter DC1, racks A12–A18; decommission lot #7 |
| Lawful trigger | Hardware decommissioning following migration to cloud + 90-day retention buffer expired |
| Retention rationale (prior) | Operational (system in use); decommission policy 90 days |
| **Method** | |
| Method | Step 1: NSA-EPL degausser (magnetic erasure). Step 2: industrial shredding (Destroy) |
| NIST level | Purge then Destroy |
| Standard | NIST SP 800-88 Purge (Step 1); DIN 66399 H-5 / ISO 21964 H-5 (Step 2) |
| Tool / supplier | Step 1: in-house Garner HD-3WXL; serial G-991. Step 2: "[Destruction Vendor GmbH]" mobile shredder; truck #DVG-44 |
| Tool version | Degausser firmware 4.21; calibration 2025-04-02 |
| **Operators** | |
| Operator | Tom Schmidt, Senior Sysadmin, EID 1102 |
| Witness | Maria Klein, Information Security Manager, EID 0521 |
| Approver | CIO (decommission lot approval) |
| DPO sign-off | Yes — Dr. F. Klein, 2025-05-23 |
| **Verification** | |
| Verification method | Per-drive degauss cycle log printed on the spot. Pre-destruction barcode reconciliation. Post-shred sample weight verification. Vendor certificate of destruction with serial-number list. |
| Verification result | Success — 38/38 drives accounted for; degauss log conformant; shred receipt acknowledged. |
| Verification evidence | `/dpo/destruction/2025/DR-2025-0218/garner-cycle-log.pdf`; `/dpo/destruction/2025/DR-2025-0218/DVG-cert-44.pdf`; `/dpo/destruction/2025/DR-2025-0218/serial-reconciliation.xlsx`; `/dpo/destruction/2025/DR-2025-0218/photos/` |
| **Backups in scope?** | These drives **were** the backup target. Replacement cloud backups exist with separate keys; not affected by this destruction. |
| Backup encryption status | Drives held LUKS-encrypted volumes; key still escrowed for 30-day rollback contingency, then crypto-shredded. |
| Backup erasure approach | Physical degauss + shred is the primary destruction; crypto-shred of escrowed key follows in 30 days as defence-in-depth. |
| Key destruction reference | Pending — `KMS-DESTROY-2025-0612` scheduled |
| **Recipients?** | No (no third-party disclosure of the data on these drives) |
| **Anomalies?** | One drive (serial S-2381) flagged as physically damaged on receipt; degauss skipped; sent direct to shredder. Documented under Anomaly Note A-1. |
| Remediation | None required; physical destruction supersedes degauss for unreadable media. |
| **Sign-off** | All present and signed |

### 2.3 Example C — Database row deletion + backup crypto-shred (DSAR fulfilment)

| Field | Value |
|---|---|
| Destruction Record ID | `DR-2025-0331` |
| Date of destruction (start) | 2025-06-10 10:15 CET |
| Date of destruction (completion) | 2025-06-10 10:42 CET (production); ongoing — backup expiry 2025-07-08 |
| Cycle reference | `DSAR-2025-0331` |
| Linked DSAR reference | `DSAR-2025-0331` |
| Classification | Restricted |
| **Subject of destruction** | |
| Data category | Customer profile + transaction history (single data subject) |
| Volume | 1 customer record + 47 order records + 312 event log records |
| Source system(s) | Customer DB (PostgreSQL primary `cust-db-prod-1`); read replica `cust-db-replica-2`; BI warehouse `analytics-warehouse`; Elasticsearch search index `cust-search-v3`; daily backups `s3://backups-eu-west-1/cust-db/` |
| Lawful trigger | Article 17 erasure request granted 2025-06-08 |
| Retention rationale (prior) | Performance of contract |
| **Method** | |
| Method | Production: row delete + vacuum. Replicas: replication-propagated delete + verification. Index: document delete. Cache: force purge. Backups: crypto-shred per-tenant key. |
| NIST level | Clear (production) + Purge (backups via crypto-shred) |
| Standard | NIST SP 800-88 Clear (production); Purge (backups) |
| Tool / supplier | `psql` script via change ticket CHG-44218; AWS KMS for backup keys; ElasticSearch DELETE API |
| Tool version | PostgreSQL 15.3; AWS KMS API; ES 8.11 |
| **Operators** | |
| Operator | DSAR automated runner job; supervised by DPO Operations team member Anna Petrov |
| Witness | N/A (DPO supervised) |
| Approver | DPO (DSAR approval) |
| DPO sign-off | Yes — A. Petrov on behalf of DPO, 2025-06-10 |
| **Verification** | |
| Verification method | Pre-deletion row count = 1 (customer); post-deletion row count = 0. Replication lag confirmed < 1s. Search index document missing. CDN cache invalidation confirmed. KMS audit log shows key disable + scheduled deletion in 7 days. |
| Verification result | Success in production. Backup ciphertext expiry pending (S3 lifecycle: 28 days, completion expected 2025-07-08). |
| Verification evidence | `/dpo/destruction/2025/DR-2025-0331/sql-output.log`; `/dpo/destruction/2025/DR-2025-0331/replication-check.txt`; `/dpo/destruction/2025/DR-2025-0331/es-delete-resp.json`; `/dpo/destruction/2025/DR-2025-0331/kms-audit-extract.csv`; `/dpo/destruction/2025/DR-2025-0331/cdn-invalidation-id.txt` |
| **Backups in scope?** | Yes |
| Backup encryption status | Encrypted with per-tenant CMK in AWS KMS |
| Backup erasure approach | Crypto-shred (KMS key disable + scheduled deletion) + S3 lifecycle expiry of ciphertext |
| Key destruction reference | KMS event `arn:aws:kms:eu-west-1:111111111111:key/abcd-1234-...` `DisableKey` 2025-06-10 10:35; `ScheduleKeyDeletion` 2025-06-10 10:36 (7 days pending window). |
| Expected expiry of remaining ciphertext | 2025-07-08 (S3 lifecycle) |
| Compensating controls during residual retention | Tenant-key disabled — even if ciphertext is read, decryption is impossible. Restore-job pre-flight check: blocks restore if tenant key is disabled. |
| **Recipients?** | Yes — payment processor and email service provider both received the data subject's data. |
| List of recipients notified | Stripe (payment processor) — notified 2025-06-10 11:00 via API + email; Mailgun (email) — notified 2025-06-10 11:05. |
| Acknowledgement received? | Stripe ack 2025-06-10 13:30 (case ref `STRIPE-PRIV-99214`); Mailgun ack 2025-06-11 09:00. |
| Sub-processors propagated? | Stripe confirmed sub-processor propagation. Mailgun: pending confirmation; reminder 2025-06-17. |
| Processor destruction certificate(s) | Stripe: `/dpo/destruction/2025/DR-2025-0331/stripe-cert.pdf`. Mailgun: pending. |
| **Anomalies?** | Mailgun acknowledgement of sub-processor propagation pending beyond 7 days — escalation to DPO 2025-06-18 if no response. |
| Remediation plan | Escalate via DPA contact Marsha Lee at Mailgun; tracker `ESC-2025-0019`. |
| **Sign-off** | All present and digitally signed (DocuSign envelope `DSE-2025-0331`) |
| **Notes** | This record links to DSAR ticket and to the data subject's response letter. Final close-out scheduled at backup expiry on 2025-07-08; entry will be amended at that time with KMS deletion confirmation timestamp. |

---

## Türkçe

# İmha Kaydı Şablonu

Bir imha kaydı, kişisel verinin güvenli ve geri çevrilemez biçimde imha edildiğine dair denetim sınıfı kanıttır. Her imha olayı — otomatik döngü, geçici uygulama, devre dışı bırakma, kâğıt parçalama, işleyen onayı — bu şablonu kullanarak (veya aynı alanları yakalayan sistem tarafından oluşturulmuş eşdeğeri) bir kayıt üretmelidir.

## 1. Form

> Parti başına bir form kullanın. Bir "parti" tutarlı bir imha olayıdır (bir döngü, bir medya türü, bir işleyen, bir kâğıt-kutu alımı). Yüksek hacimli otomatik döngüler döngü seviyesinde, örneklenmiş kayıt başına denetim izi ile toplanabilir.

### 1.1 Başlık

| Alan | Değer |
|---|---|
| İmha Kaydı Kimliği | `DR-YYYY-NNNN` |
| İmha tarihi (başlangıç) | YYYY-MM-DD HH:MM TZ |
| İmha tarihi (tamamlanma) | YYYY-MM-DD HH:MM TZ |
| Döngü referansı (geçerliyse) | `CYCLE-YYYY-QN` |
| Bağlı DSAR referansı (geçerliyse) | `DSAR-YYYY-NNNN` |
| Bağlı istisna referansı (geçerliyse) | `EXC-YYYY-NNNN` |
| Sınıflandırma | Dahili / Gizli / Kısıtlı |

### 1.2 İmhanın konusu

| Alan | Değer |
|---|---|
| Veri kategorisi (Saklama Çizelgesi başına) | örn. Bordro kayıtları 2014 |
| Kayıt sayısı / hacim | örn. 1.250 kayıt / 8 GB / 12 kutu |
| Kaynak sistem(ler) | örn. HRIS üretim, HRIS yedek, kâğıt arşiv Bölüm 3 |
| Yasal tetikleyici | örn. Saklama süresi sona erdi (10 yıl) |
| Saklama gerekçesi (önceki saklama dayanağı) | örn. Alman vergi hukuku § 147 AO |

### 1.3 Yöntem

| Alan | Değer |
|---|---|
| Yöntem | Veritabanı satır silme / Kripto-parçalama / Güvenli üzerine yazma / Demanyetize / Kâğıt parçalama / Fiziksel imha |
| NIST seviyesi | Clear / Purge / Destroy |
| Standart / şartname | örn. NIST SP 800-88 Purge; DIN 66399 P-5 |
| Araç / tedarikçi | örn. `pgsql DELETE`; AWS KMS anahtar imhası; Iron Mountain on-site shredder |
| Araç sürümü / bellenim | örn. PostgreSQL 15.3; KMS API v2; kamyon #INFOSEC-7 |

### 1.4 Operatörler

| Alan | Değer |
|---|---|
| Operatör (gerçekleştiren) | İsim, rol, çalışan kimliği |
| Tanık (gerektiğinde) | İsim, rol, çalışan kimliği |
| Onaylayıcı (Veri Sahibi) | İsim, rol |
| DPO onayı (gerektiğinde) | İsim, imza, tarih |

### 1.5 Doğrulama

| Alan | Değer |
|---|---|
| Doğrulama yöntemi | örn. Örnek satır okuma; KMS denetim logu; sektör örneği; tedarikçi sertifikası |
| Doğrulama sonucu | Başarı / Anomali (detayla) |
| Doğrulama kanıtı (referans) | Kanıt yolu: log dosyası, ekran görüntüsü, sertifika PDF |

### 1.6 Yedek işleme

| Alan | Değer |
|---|---|
| Yedekler kapsamda? | Evet / Hayır |
| Yedek şifreleme durumu | Kontrolör yönetimindeki anahtarla şifreli / Şifresiz |
| Yedek silme yaklaşımı | Kripto-parçalama / Yaşam döngüsü son / Kısıtlama + sonra son |
| Anahtar imha referansı | KMS olay kimliği, zaman damgası |
| Kalan şifreli metnin beklenen sonu | YYYY-MM-DD |
| Artık saklama sırasında telafi edici kontroller | örn. Okuma erişimi devre dışı; işleyen kısıtlaması onaylandı |

### 1.7 Alıcı / işleyen / alt-işleyen bildirimi

| Alan | Değer |
|---|---|
| Kapsamdaki alıcılar (Md. 19)? | Evet / Hayır |
| Bildirilen alıcı listesi | İsim, iletişim, bildirim tarihi |
| Onay alındı? | Evet / Hayır / Beklemede tarih |
| Alt-işleyenler yayıldı? | Evet / Hayır / Yok |
| İşleyen imha sertifika(ları) | Referans + kanıt yolu |

### 1.8 Anomaliler ve iyileştirme

| Alan | Değer |
|---|---|
| İmha sırasında herhangi bir anomali? | Evet / Hayır |
| Açıklama | Serbest metin |
| İyileştirme planı | Sahip, eylem, hedef tarih |
| DPO bilgilendirildi? | Evet / Hayır / Yok |

### 1.9 Onay

| Rol | İsim | İmza | Tarih |
|---|---|---|---|
| Operatör | | | |
| Tanık (gerekiyorsa) | | | |
| Veri Sahibi | | | |
| DPO (gerekiyorsa) | | | |
| Bilgi Güvenliği (doğrulama) | | | |

### 1.10 Bu kaydın saklanması

Bu imha kaydı imha tarihinden itibaren **en az 6 yıl** boyunca (veya yerel denetim / düzenleyici hukuk gerektirdiğinde daha uzun) Saklama Çizelgesinin Denetim ve Hesap Verebilirlik kategorisi altında saklanır.

---

## 2. İşlenmiş örnekler

### 2.1 Örnek A — Kâğıt parçalama (İK arşivi)

| Alan | Değer |
|---|---|
| İmha Kaydı Kimliği | `DR-2025-0142` |
| İmha tarihi (başlangıç) | 2025-04-15 09:30 CET |
| İmha tarihi (tamamlanma) | 2025-04-15 11:10 CET |
| Döngü referansı | `CYCLE-2025-Q2` |
| Sınıflandırma | Kısıtlı |
| **İmhanın konusu** | |
| Veri kategorisi | İş başvuruları 2017 (başarısız adaylar); CV fotokopileri ve görüşme notları |
| Hacim | 12 standart arşiv kutusu (~ 720 dosya) |
| Kaynak sistem(ler) | İK arşiv odası B-104, raflar 11–14 |
| Yasal tetikleyici | Saklama süresi sona erdi (orijinal 6 ay; 2018'e kadar istisna altında tutuldu; olağan saklama 2017+1y, istisna 2018'de kaldırıldı, parti bu döngüde toplandı) |
| Saklama gerekçesi (önceki) | Orijinal: meşru menfaat + hukuki talepler (AGG § 15 — 6 ay). İstisna: bekleyen denetim referansı. |
| **Yöntem** | |
| Yöntem | Kâğıt parçalama (site dışı mobil parçalayıcı) |
| NIST seviyesi | Destroy |
| Standart | DIN 66399 P-5 (≤30 mm² parçacık boyutu) |
| Araç / tedarikçi | "[Parçalama Tedarikçi Ltd]"; kamyon #SVL-219; sertifikalı ISO 21964-2 P-5 |
| Araç sürümü | Mobil parçalayıcı model XYZ-500; kalibrasyon tarihi 2025-02-10 |
| **Operatörler** | |
| Operatör | Hans Müller, Tesis Koordinatörü, EID 4421 |
| Tanık | Lena Bauer, İK Kayıt Görevlisi, EID 8821 |
| Onaylayıcı (Veri Sahibi) | Sabine Becker, İK Direktörü |
| DPO onayı | Evet (yüksek hacim, hassas bağlam) — Dr. F. Klein, 2025-04-16 |
| **Doğrulama** | |
| Doğrulama yöntemi | Tanıklı yükleme; on-site parçalama gözlendi; tedarikçi sertifikası alındı |
| Doğrulama sonucu | Başarı |
| Doğrulama kanıtı | `/dpo/destruction/2025/DR-2025-0142/SVL-cert-219.pdf`; `/dpo/destruction/2025/DR-2025-0142/witness-form.pdf` |
| **Yedekler kapsamda?** | Hayır (yalnızca kâğıt kategorisi) |
| **Alıcılar kapsamda?** | Hayır |
| **Anomaliler?** | Hayır |
| **Onay** | Hepsi mevcut ve imzalı |
| **Notlar** | Parçacık boyutu 09:55 CET'te örnek-kontrol edildi; uyumlu. |

### 2.2 Örnek B — HDD demanyetizasyonu + fiziksel imha (devre dışı bırakılan sunucular)

| Alan | Değer |
|---|---|
| İmha Kaydı Kimliği | `DR-2025-0218` |
| İmha tarihi (başlangıç) | 2025-05-22 13:00 CET |
| İmha tarihi (tamamlanma) | 2025-05-22 17:45 CET |
| Döngü referansı | `DECOM-2025-DC1-LOT-7` |
| Sınıflandırma | Kısıtlı |
| **İmhanın konusu** | |
| Veri kategorisi | Karışık: üretim veritabanı yedekleri; CCTV kaydedici sürücüleri; eski dosya sunucusu sürücüleri. Kategoriler müşteri işlemleri (depoda şifrelenmiş), CCTV (çalışan/ziyaretçi görüntüleri) ve İK arşivlerini içerir. |
| Hacim | 38 HDD (3.5" SAS, her biri 1–8 TB); toplam ham kapasite ~ 142 TB |
| Kaynak sistem(ler) | Veri merkezi DC1, raflar A12–A18; devre dışı bırakma lot #7 |
| Yasal tetikleyici | Buluta geçişin ardından donanım devre dışı bırakma + 90 günlük saklama tamponu sona erdi |
| Saklama gerekçesi (önceki) | Operasyonel (sistem kullanımda); devre dışı bırakma politikası 90 gün |
| **Yöntem** | |
| Yöntem | Adım 1: NSA-EPL demanyetizatörü (manyetik silme). Adım 2: endüstriyel parçalama (Destroy) |
| NIST seviyesi | Purge ardından Destroy |
| Standart | NIST SP 800-88 Purge (Adım 1); DIN 66399 H-5 / ISO 21964 H-5 (Adım 2) |
| Araç / tedarikçi | Adım 1: kurum içi Garner HD-3WXL; seri G-991. Adım 2: "[İmha Tedarikçi GmbH]" mobil parçalayıcı; kamyon #DVG-44 |
| Araç sürümü | Demanyetizatör bellenimi 4.21; kalibrasyon 2025-04-02 |
| **Operatörler** | |
| Operatör | Tom Schmidt, Kıdemli Sysadmin, EID 1102 |
| Tanık | Maria Klein, Bilgi Güvenliği Yöneticisi, EID 0521 |
| Onaylayıcı | CIO (devre dışı bırakma lot onayı) |
| DPO onayı | Evet — Dr. F. Klein, 2025-05-23 |
| **Doğrulama** | |
| Doğrulama yöntemi | Sürücü başına demanyetize döngü logu yerinde basıldı. İmha öncesi barkod mutabakatı. İmha sonrası örnek ağırlık doğrulaması. Seri-numara listesiyle tedarikçi imha sertifikası. |
| Doğrulama sonucu | Başarı — 38/38 sürücü hesaplandı; demanyetize log uyumlu; parçalama makbuzu onaylandı. |
| Doğrulama kanıtı | `/dpo/destruction/2025/DR-2025-0218/garner-cycle-log.pdf`; `/dpo/destruction/2025/DR-2025-0218/DVG-cert-44.pdf`; `/dpo/destruction/2025/DR-2025-0218/serial-reconciliation.xlsx`; `/dpo/destruction/2025/DR-2025-0218/photos/` |
| **Yedekler kapsamda?** | Bu sürücüler yedek hedefiydi. Yedek bulut yedekleri ayrı anahtarlarla mevcuttur; bu imhadan etkilenmemiştir. |
| Yedek şifreleme durumu | Sürücüler LUKS-şifrelenmiş birimler tutuyordu; anahtar 30 günlük geri alma olağanüstü durumu için emanette tutulur, ardından kripto-parçalanır. |
| Yedek silme yaklaşımı | Fiziksel demanyetize + parçalama birincil imhadır; emanetteki anahtarın kripto-parçalanması derinlemesine savunma olarak 30 gün sonra gelir. |
| Anahtar imha referansı | Beklemede — `KMS-DESTROY-2025-0612` planlandı |
| **Alıcılar?** | Hayır (bu sürücülerdeki verinin üçüncü taraf açıklaması yok) |
| **Anomaliler?** | Bir sürücü (seri S-2381) alındığında fiziksel olarak hasarlı işaretlendi; demanyetize atlandı; doğrudan parçalayıcıya gönderildi. Anomali Notu A-1 altında belgelenmiştir. |
| İyileştirme | Gerekli değil; okunamaz medya için fiziksel imha demanyetizasyonun yerini alır. |
| **Onay** | Hepsi mevcut ve imzalı |

### 2.3 Örnek C — Veritabanı satır silme + yedek kripto-parçalama (DSAR yerine getirme)

| Alan | Değer |
|---|---|
| İmha Kaydı Kimliği | `DR-2025-0331` |
| İmha tarihi (başlangıç) | 2025-06-10 10:15 CET |
| İmha tarihi (tamamlanma) | 2025-06-10 10:42 CET (üretim); devam ediyor — yedek son 2025-07-08 |
| Döngü referansı | `DSAR-2025-0331` |
| Bağlı DSAR referansı | `DSAR-2025-0331` |
| Sınıflandırma | Kısıtlı |
| **İmhanın konusu** | |
| Veri kategorisi | Müşteri profili + işlem geçmişi (tek ilgili kişi) |
| Hacim | 1 müşteri kaydı + 47 sipariş kaydı + 312 olay log kaydı |
| Kaynak sistem(ler) | Müşteri DB (PostgreSQL birincil `cust-db-prod-1`); okuma replikası `cust-db-replica-2`; BI ambarı `analytics-warehouse`; Elasticsearch arama indeksi `cust-search-v3`; günlük yedekler `s3://backups-eu-west-1/cust-db/` |
| Yasal tetikleyici | 2025-06-08'de kabul edilen Madde 17 silme talebi |
| Saklama gerekçesi (önceki) | Sözleşmenin ifası |
| **Yöntem** | |
| Yöntem | Üretim: satır silme + vakum. Replikalar: çoğaltma yayılan silme + doğrulama. İndeks: belge silme. Önbellek: zorla temizleme. Yedekler: kiracı başına anahtar kripto-parçalama. |
| NIST seviyesi | Clear (üretim) + Purge (kripto-parçalama yoluyla yedekler) |
| Standart | NIST SP 800-88 Clear (üretim); Purge (yedekler) |
| Araç / tedarikçi | `psql` script değişiklik talebi CHG-44218 üzerinden; yedek anahtarlar için AWS KMS; ElasticSearch DELETE API |
| Araç sürümü | PostgreSQL 15.3; AWS KMS API; ES 8.11 |
| **Operatörler** | |
| Operatör | DSAR otomatik koşucu işi; DPO Operasyon ekibi üyesi Anna Petrov tarafından denetlendi |
| Tanık | Yok (DPO denetimli) |
| Onaylayıcı | DPO (DSAR onayı) |
| DPO onayı | Evet — DPO adına A. Petrov, 2025-06-10 |
| **Doğrulama** | |
| Doğrulama yöntemi | Silme öncesi satır sayısı = 1 (müşteri); silme sonrası satır sayısı = 0. Çoğaltma gecikmesi < 1 sn onaylandı. Arama indeks belgesi eksik. CDN önbellek geçersiz kılma onaylandı. KMS denetim logu anahtar devre dışı bırakma + 7 gün içinde planlanmış silme gösteriyor. |
| Doğrulama sonucu | Üretimde başarı. Yedek şifreli metin son beklemede (S3 yaşam döngüsü: 28 gün, beklenen tamamlanma 2025-07-08). |
| Doğrulama kanıtı | `/dpo/destruction/2025/DR-2025-0331/sql-output.log`; `/dpo/destruction/2025/DR-2025-0331/replication-check.txt`; `/dpo/destruction/2025/DR-2025-0331/es-delete-resp.json`; `/dpo/destruction/2025/DR-2025-0331/kms-audit-extract.csv`; `/dpo/destruction/2025/DR-2025-0331/cdn-invalidation-id.txt` |
| **Yedekler kapsamda?** | Evet |
| Yedek şifreleme durumu | AWS KMS'te kiracı başına CMK ile şifrelenmiş |
| Yedek silme yaklaşımı | Kripto-parçalama (KMS anahtar devre dışı bırakma + planlanmış silme) + şifreli metnin S3 yaşam döngüsü sonu |
| Anahtar imha referansı | KMS olayı `arn:aws:kms:eu-west-1:111111111111:key/abcd-1234-...` `DisableKey` 2025-06-10 10:35; `ScheduleKeyDeletion` 2025-06-10 10:36 (7 gün bekleme penceresi). |
| Kalan şifreli metnin beklenen sonu | 2025-07-08 (S3 yaşam döngüsü) |
| Artık saklama sırasında telafi edici kontroller | Kiracı anahtarı devre dışı — şifreli metin okunsa bile şifre çözme imkânsız. Geri yükleme işi ön kontrolü: kiracı anahtarı devre dışıysa geri yüklemeyi engeller. |
| **Alıcılar?** | Evet — ödeme işleyici ve e-posta hizmet sağlayıcı her ikisi de ilgili kişinin verisini aldı. |
| Bildirilen alıcı listesi | Stripe (ödeme işleyici) — API + e-posta yoluyla 2025-06-10 11:00 bildirildi; Mailgun (e-posta) — 2025-06-10 11:05 bildirildi. |
| Onay alındı? | Stripe onayı 2025-06-10 13:30 (vaka ref `STRIPE-PRIV-99214`); Mailgun onayı 2025-06-11 09:00. |
| Alt-işleyenler yayıldı? | Stripe alt-işleyen yayılımını onayladı. Mailgun: onay beklemede; hatırlatma 2025-06-17. |
| İşleyen imha sertifika(ları) | Stripe: `/dpo/destruction/2025/DR-2025-0331/stripe-cert.pdf`. Mailgun: beklemede. |
| **Anomaliler?** | Mailgun alt-işleyen yayılım onayı 7 günden uzun beklemede — yanıt yoksa 2025-06-18'de DPO'ya eskalasyon. |
| İyileştirme planı | Mailgun'da DPA iletişim Marsha Lee aracılığıyla eskalasyon; izleyici `ESC-2025-0019`. |
| **Onay** | Hepsi mevcut ve dijital imzalı (DocuSign zarfı `DSE-2025-0331`) |
| **Notlar** | Bu kayıt DSAR talebine ve ilgili kişinin yanıt mektubuna bağlanır. Son kapanış 2025-07-08'de yedek son tarihinde planlandı; giriş o zaman KMS silme onay zaman damgasıyla değiştirilecek. |
