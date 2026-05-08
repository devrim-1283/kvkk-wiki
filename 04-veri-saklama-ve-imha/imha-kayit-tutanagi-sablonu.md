---
Doküman / Document: İmha Kayıt Tutanağı Şablonları / Destruction Record Templates
Bölüm / Section: 04-veri-saklama-ve-imha
Sahip / Owner: KVKK Sorumlusu / KVKK Officer
Onaylayan / Approved by: Hukuk Müdürü + Bilgi Güvenliği Yöneticisi / Legal Director + Information Security Manager
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş / Annual + triggered
İlgili Mevzuat / Legal Reference: Reg. Art. 7(3), 7(4); KVKK Art. 12
---

## English

# Destruction Record Templates

## 1. Record Obligation

Reg. Art. 7(3): "All operations relating to the erasure, destruction or anonymization of personal data shall be recorded, and these records, excluding other legal obligations, shall be retained for **at least three years**."

The record is the formal document showing the destruction method, scope, responsible parties and evidence. Destruction performed without a record **is deemed not performed** for the purposes of the burden of proof.

Reg. Art. 7(4): "The data controller is obliged to explain the methods applied for erasure, destruction and anonymization in the relevant policy and procedures."

## 2. Minimum Content

The following fields must be present in every record:

| Field | Description |
|-------|-------------|
| Record No | Internal unique identifier (year/sequence e.g. 2026/IMHA-0142) |
| Record Type | Periodic / Data Subject Request / Triggered / Vendor |
| Date of Operation | Date and time of destruction |
| Place of Operation | Physical location or system name |
| Data Category | Which personal data category (inventory reference) |
| Legal Reason | Under which KVKK Art. 5/6 condition was data processed; which condition's cessation triggered destruction |
| Scope (Count/Medium) | Records affected, medium (DB/file/server/medium) |
| Method | Erasure / Destruction / Anonymization — sub-method (DELETE, physical shredding, k-anonymity, etc.) |
| Standard Reference | Applied technical standard (NIST 800-88, DIN 66399, etc.) if any |
| Evidence Type | Hash, log, photo, certificate |
| Third-Party Transfer | Was data transferred? Was notification made? |
| Vendor | Vendor name + certificate no if external destruction service |
| Preparer (Executor) | Person executing destruction (name, title, signature) |
| Verifier | Information Security independent verification (name, title, signature) |
| Approver | KVKK Officer (name, title, signature) |
| Legal Approval | Legal Director (name, title, signature) |
| Retention Period | Minimum retention of the record (at least 3 years) |
| Annexes | System log, photo, certificate, hash list |

## 3. Record Numbering Scheme

```
[YEAR]/[METHOD]/[SEQUENCE]
example: 2026/IMHA-0142
         2026/PER-0007 (Periodic Destruction)
         2026/TLP-0023 (Data Subject Request)
```

## 4. Record Retention

- Retention: Reg. Art. 7(3) — at least 3 years. Internal standard: 5 years.
- Format: Electronically signed PDF + system audit log.
- Location: Secure archive under KVKK Officer control (limited access, logged).
- Metadata: Record no, date, category, owner — searchable index.

---

## 5. General Record Template

```
══════════════════════════════════════════════════════
PERSONAL DATA DESTRUCTION RECORD
══════════════════════════════════════════════════════

Record No          : ____________________________
Record Type        : [ ] Periodic     [ ] Data Subject Request
                     [ ] Triggered    [ ] Vendor Destruction
                     [ ] Other: __________________________

Date/Time          : ____/____/______ — ___:___
Place              : ______________________________
                     (Physical address or system name)

──────────────────────────────────────────────────────
1. SCOPE INFORMATION
──────────────────────────────────────────────────────
Data Category      : __________________________________
                     (Inventory Item No: __________)
Data Subject Group : __________________________________
                     (Employee / Customer / Candidate /
                      Supplier / Visitor / Other)
Legal Reason —
Processing Cond.   : KVKK Art. ____ / ____
                     Reason for cessation of condition:
                     _________________________________
Record Count       : _________ records
Date Range         : ____/____/____ — ____/____/____
Medium             : [ ] Active database
                     [ ] Backup (rotation / cold)
                     [ ] Paper document
                     [ ] Magnetic medium (HDD/Tape)
                     [ ] SSD/Flash medium
                     [ ] Optical medium
                     [ ] Cloud object storage
                     [ ] Log/SIEM
                     [ ] Other: __________________

──────────────────────────────────────────────────────
2. APPLIED DESTRUCTION METHOD
──────────────────────────────────────────────────────
Main Method        : [ ] Erasure (Reg. Art. 8)
                     [ ] Destruction (Reg. Art. 9)
                     [ ] Anonymization (Reg. Art. 10)

Sub-Method         : ____________________________________
                     (DELETE/UPDATE, degauss, shredding,
                      incineration, sanitize, crypto-shred,
                      k-anonymity, generalization, etc.)

Applied Standard   : ____________________________________
                     (NIST 800-88 Purge/Destroy,
                      DIN 66399 P-4/P-5/P-7,
                      DoD 5220.22-M, ISO 27040, etc.)

Method Selection
Rationale          : ____________________________________

──────────────────────────────────────────────────────
3. EVIDENCE AND VERIFICATION
──────────────────────────────────────────────────────
Hash Evidence      : Annex-1 (separate file)
                     SHA-256 hash count: __________
System Log         : Annex-2 (separate file)
                     Log System: ____________________
                     Job ID: _________________________
                     Start: __:__:__  End: __:__:__
Visual Evidence    : [ ] Yes (Annex-3) — photo/video
                     [ ] No
Vendor Certif.     : [ ] None
                     [ ] Yes: ____________________ no
                     Vendor: ____________________

──────────────────────────────────────────────────────
4. THIRD-PARTY TRANSFER
──────────────────────────────────────────────────────
Transferred Third
Parties            : [ ] None
                     [ ] Yes: __________________________

Notification to
Third Party        : [ ] Done (Date: __/__/____)
                     [ ] Pending
                     [ ] Not applicable
Third-Party
Confirmation       : [ ] Received (Date: __/__/____)
                     [ ] Pending

──────────────────────────────────────────────────────
5. RESPONSIBLE PARTIES AND SIGNATURES
──────────────────────────────────────────────────────
Preparer (Executor)
  Name             : ____________________________
  Title / Unit     : ____________________________
  Date             : ____/____/______
  Signature        : ____________________________

Verifier (Information Security — independent)
  Name             : ____________________________
  Title / Unit     : ____________________________
  Date             : ____/____/______
  Signature        : ____________________________

KVKK Officer Approval
  Name             : ____________________________
  Title            : KVKK Officer
  Date             : ____/____/______
  Signature        : ____________________________

Legal Approval (Legal Director)
  Name             : ____________________________
  Title            : Legal Director
  Date             : ____/____/______
  Signature        : ____________________________

──────────────────────────────────────────────────────
6. RETENTION AND ARCHIVING
──────────────────────────────────────────────────────
Record Retention
Period             : At least 3 years (Reg. Art. 7(3))
                     Internal standard: 5 years
Archive Location   : __________________________________
Archive Number     : __________________________________

══════════════════════════════════════════════════════
ANNEXES
══════════════════════════════════════════════════════
[ ] Annex-1: Hash list (SHA-256)
[ ] Annex-2: System log output
[ ] Annex-3: Photo/video evidence
[ ] Annex-4: Vendor destruction certificate
[ ] Annex-5: Third-party notification/confirmation letter
[ ] Annex-6: Data subject application and response (if any)
[ ] Annex-7: Method technical instruction/runbook output
══════════════════════════════════════════════════════
```

---

## 6. Sample Record 1 — Paper Document Destruction by Shredder

```
══════════════════════════════════════════════════════
PERSONAL DATA DESTRUCTION RECORD
══════════════════════════════════════════════════════

Record No          : 2026/PER-0007
Record Type        : [X] Periodic
Date/Time          : 12/05/2026 — 10:30
Place              : Headquarters — HR Archive (B-Block B1)

──────────────────────────────────────────────────────
1. SCOPE INFORMATION
──────────────────────────────────────────────────────
Data Category      : CVs of candidates rejected during hiring
                     (Inventory Item No: HR-04)
Data Subject Group : Job candidate
Legal Reason —
Processing Cond.   : KVKK Art. 5/2-(f) Legitimate interest
                     Cessation reason:
                     2-year maximum retention period expired
Record Count       : 1,142 files
Date Range         : 01/01/2024 — 30/04/2024
Medium             : [X] Paper document

──────────────────────────────────────────────────────
2. APPLIED DESTRUCTION METHOD
──────────────────────────────────────────────────────
Main Method        : [X] Destruction (Reg. Art. 9)
Sub-Method         : Cross-cut shredder (micro-cut)
Applied Standard   : DIN 66399 P-5
Method Selection
Rationale          : Application files containing personal
                     data on paper; destruction without
                     recovery risk required.

──────────────────────────────────────────────────────
3. EVIDENCE AND VERIFICATION
──────────────────────────────────────────────────────
Hash Evidence      : N/A (paper medium)
System Log         : N/A
Visual Evidence    : [X] Yes — Annex-3 (3 photos:
                     before-during-after)
Vendor Certif.     : [X] None (in-house shredder)

──────────────────────────────────────────────────────
4. THIRD-PARTY TRANSFER
──────────────────────────────────────────────────────
Transferred Third
Parties            : [X] None

──────────────────────────────────────────────────────
5. RESPONSIBLE PARTIES AND SIGNATURES
──────────────────────────────────────────────────────
Preparer           : Ayşe DEMİR — HR Specialist
Verifier           : Mehmet KAYA — Information Security Specialist
KVKK Officer       : Selin YILDIZ — KVKK Officer
Legal Approval     : Att. Ahmet ÖZ — Legal Director

──────────────────────────────────────────────────────
6. RETENTION AND ARCHIVING
──────────────────────────────────────────────────────
Retention Period   : 5 years
Archive Location   : KVKK Archive — Cabinet 03 / Folder 14
Archive Number     : KVKK-ARS-2026-0007

══════════════════════════════════════════════════════
ANNEXES
══════════════════════════════════════════════════════
[X] Annex-3: 3 photos (before/during/after)
[X] Annex-7: HR-PROC-005 Candidate File Destruction Instruction v2.1
══════════════════════════════════════════════════════
```

---

## 7. Sample Record 2 — HDD Degausser + Physical Shredding

```
══════════════════════════════════════════════════════
PERSONAL DATA DESTRUCTION RECORD
══════════════════════════════════════════════════════

Record No          : 2026/IMHA-0142
Record Type        : [X] Triggered (Hardware decommissioning)
Date/Time          : 18/05/2026 — 14:00
Place              : Data Center — Disk Destruction Room

──────────────────────────────────────────────────────
1. SCOPE INFORMATION
──────────────────────────────────────────────────────
Data Category      : HDDs removed from old ERP server disk
                     array (mixed: employee, customer,
                     financial)
                     (Inventory Item No: IT-12, IT-13)
Data Subject Group : Employee + Customer + Supplier
Legal Reason —
Processing Cond.   : Multiple — KVKK Art. 5/2-(c) contract
                     performance + (e) right establishment
                     + (f) legitimate interest
                     Cessation reason: Decommissioning of
                     legacy hardware after migration
Record Count       : ~TB per disk; total approx. 2.3 TB
Medium             : [X] Magnetic medium (HDD)

  Disk List:
  Serial No              Vendor    Capacity
  WD-WMC4M0H17832        WD        2 TB
  WD-WMC4M0H17855        WD        2 TB
  ST3000DM001-Z3T2HK1    Seagate   3 TB
  ST3000DM001-Z3T2HM2    Seagate   3 TB
  ... (8 disks total)

──────────────────────────────────────────────────────
2. APPLIED DESTRUCTION METHOD
──────────────────────────────────────────────────────
Main Method        : [X] Destruction (Reg. Art. 9)
Sub-Method         : 1) Magnetic erasure with degausser
                     2) Mechanical shredding (drive shredder)
Applied Standard   : NIST 800-88 Rev.1 Purge → Destroy
Method Selection
Rationale          : Hardware will not be reused; contains
                     sensitive data; multi-method ensures
                     irreversible destruction.

──────────────────────────────────────────────────────
3. EVIDENCE AND VERIFICATION
──────────────────────────────────────────────────────
Hash Evidence      : Hashes from pre-destruction disk
                     image — Annex-1 (control)
System Log         : Degausser device log — Annex-2
                     Device: Garner HD-3WXL
                     Calibration: 2026-04-01 (valid)
Visual Evidence    : [X] Yes — Annex-3:
                     - Before (serial visible)
                     - Degausser process
                     - After shredding (fragments)
Vendor Certif.     : [X] None (in-house device)

──────────────────────────────────────────────────────
4. THIRD-PARTY TRANSFER
──────────────────────────────────────────────────────
Transferred Third
Parties            : [X] Yes: ABC Logistics A.Ş. (legacy
                     delivery records were shared)
Notification       : [X] Done (20/05/2026 / KEP)
Confirmation       : [ ] Pending (commitment within 30 days)

──────────────────────────────────────────────────────
5. RESPONSIBLE PARTIES AND SIGNATURES
──────────────────────────────────────────────────────
Preparer           : Burak ÇELİK — Systems Administrator
Verifier           : Mehmet KAYA — Information Security Specialist
KVKK Officer       : Selin YILDIZ — KVKK Officer
Legal Approval     : Att. Ahmet ÖZ — Legal Director

──────────────────────────────────────────────────────
6. RETENTION AND ARCHIVING
──────────────────────────────────────────────────────
Retention Period   : 5 years
Archive Location   : KVKK Digital Archive (e-signed PDF)
Archive Number     : KVKK-ARS-2026-0142

══════════════════════════════════════════════════════
ANNEXES
══════════════════════════════════════════════════════
[X] Annex-1: Disk hash list (SHA-256)
[X] Annex-2: Degausser device log (CSV output)
[X] Annex-3: Photo/video evidence (3 timestamped items)
[X] Annex-5: Third-party (ABC Logistics) KEP notification
[X] Annex-7: IT-PROC-018 Disk Destruction Runbook v3.0
══════════════════════════════════════════════════════
```

---

## 8. Sample Record 3 — Cloud Database Erasure + Crypto-Shredding

```
══════════════════════════════════════════════════════
PERSONAL DATA DESTRUCTION RECORD
══════════════════════════════════════════════════════

Record No          : 2026/TLP-0023
Record Type        : [X] Data Subject Request
Date/Time          : 03/06/2026 — 16:45
Place              : AWS eu-central-1 — Production
                     database + S3 backup

──────────────────────────────────────────────────────
1. SCOPE INFORMATION
──────────────────────────────────────────────────────
Data Category      : E-commerce member account records
                     (Inventory Item No: ECOM-01)
Data Subject Group : One customer (Request No:
                     KVKK-BSV-2026-0214)
Legal Reason —
Processing Cond.   : Explicit consent withdrawn (KVKK Art. 5/1);
                     Contractual relationship ended;
                     Tax/commercial retention period exceeded.
                     Cessation reason: All processing
                     conditions ceased (Reg. Art. 12/1-a)
Record Count       : 1 customer profile + 47 order records
                     + 312 session/access logs
Medium             : [X] Cloud object storage (S3)
                     [X] Active database (RDS PostgreSQL)
                     [X] Log/SIEM (CloudWatch + ES)
                     [X] Backup (RDS automated snapshot)

──────────────────────────────────────────────────────
2. APPLIED DESTRUCTION METHOD
──────────────────────────────────────────────────────
Main Method        : [X] Erasure (Reg. Art. 8) — active
                     [X] Destruction (Reg. Art. 9) — backup
Sub-Method         : 1) DB: hard-delete (DELETE)
                        + audit record
                     2) S3: object delete + version delete
                        + lifecycle expiry
                     3) Log: PII fields nulled + index-based
                        retention
                     4) Backup: BYOK DEK (Data Encryption
                        Key) destruction — crypto-shredding
Applied Standard   : Cloud provider DPA (AWS) destruction
                     commitment; NIST 800-88 Purge (crypto)
Method Selection
Rationale          : Hardware destruction not possible in
                     cloud; practical destruction via key
                     destruction. Method and rationale
                     communicated to data subject.

──────────────────────────────────────────────────────
3. EVIDENCE AND VERIFICATION
──────────────────────────────────────────────────────
Hash Evidence      : Customer ID hash (SHA-256) —
                     Annex-1 (data itself not retained)
System Log         : - RDS general log (Annex-2)
                     - CloudTrail KMS API log (Annex-2)
                     - S3 access log (Annex-2)
                     Job ID: KVKK-PURGE-2026-0023
                     Start: 16:30:12 — End: 16:43:28
Visual Evidence    : [X] Yes — Annex-3 (KMS console
                     screenshot "Pending deletion" → "Deleted")
Vendor Certif.     : N/A (within AWS DPA)

──────────────────────────────────────────────────────
4. THIRD-PARTY TRANSFER
──────────────────────────────────────────────────────
Transferred Third
Parties            : [X] Yes:
                     - Logistics provider (delivery address)
                     - Payment service (payment tokens)
                     - Marketing automation SaaS provider
Notification       : [X] Done (03/06/2026 / KEP)
Confirmation       : [X] Logistics — received 05/06/2026
                     [X] Payment — received 04/06/2026
                     [ ] Marketing — pending (15 days)

──────────────────────────────────────────────────────
5. RESPONSIBLE PARTIES AND SIGNATURES
──────────────────────────────────────────────────────
Preparer           : Burak ÇELİK — Systems Administrator
Verifier           : Mehmet KAYA — Information Security Specialist
KVKK Officer       : Selin YILDIZ — KVKK Officer
Legal Approval     : Att. Ahmet ÖZ — Legal Director

──────────────────────────────────────────────────────
6. RETENTION AND ARCHIVING
──────────────────────────────────────────────────────
Retention Period   : 5 years
Archive Location   : KVKK Digital Archive (e-signed PDF)
Archive Number     : KVKK-ARS-2026-0023

══════════════════════════════════════════════════════
ANNEXES
══════════════════════════════════════════════════════
[X] Annex-1: Customer ID hash list (SHA-256)
[X] Annex-2: AWS system logs (RDS, CloudTrail, S3)
[X] Annex-3: KMS Pending Deletion → Deleted screenshot
[X] Annex-5: KEPs to 3 third parties + confirmations
[X] Annex-6: Data subject application (No: KVKK-BSV-2026-0214)
            and the controller's response letter
[X] Annex-7: IT-PROC-024 Cloud PII Purge Runbook v2.0
══════════════════════════════════════════════════════
```

## 9. Record Verification Checklist

Before signature, the KVKK Officer performs the following checks:

- [ ] Record number consistent with internal sequence
- [ ] Processing condition and cessation reason explicitly stated
- [ ] Data category one-to-one with inventory
- [ ] Record count and hash count consistent
- [ ] Method appropriate for medium type
- [ ] Applied standard referenced
- [ ] Evidence type (hash/log/photo/certificate) noted
- [ ] Third-party transfer checked; notification sent
- [ ] All 4 signatures present (Preparer, Verifier, KVKK Officer, Legal Director)
- [ ] Annexes complete
- [ ] Retention period and archive number assigned
- [ ] Electronic signature affixed

---

## Türkçe

# İmha Kayıt Tutanağı Şablonları

## 1. Tutanak Yükümlülüğü

Yön. m.7(3): "Kişisel verilerin silinmesi, yok edilmesi ve anonim hale getirilmesiyle ilgili yapılan bütün işlemler kayıt altına alınır ve söz konusu kayıtlar, diğer hukuki yükümlülükler hariç olmak üzere **en az üç yıl süreyle** saklanır."

Tutanak; imha yöntemini, kapsamını, sorumlularını ve kanıtlarını gösteren resmi belgedir. Tutanak olmaksızın yapılan imha, ispat yükümlülüğü açısından **yapılmamış sayılır**.

Yön. m.7(4): "Veri sorumlusu, kişisel verilerin silinmesi, yok edilmesi, anonim hale getirilmesi işlemiyle ilgili uyguladığı yöntemleri ilgili politika ve prosedürlerinde açıklamakla yükümlüdür."

## 2. Asgari İçerik

Her tutanakta aşağıdaki alanlar bulunmalıdır:

| Alan | Açıklama |
|------|----------|
| Tutanak No | Şirket içi tekil kimlik (yıl/sıra ör. 2026/IMHA-0142) |
| Tutanak Türü | Periyodik / İlgili Kişi Talebi / Tetiklenmiş / Tedarikçi |
| İşlem Tarihi | İmhanın yapıldığı tarih ve saat |
| İşlem Yeri | Fiziksel veya sistem adı |
| Veri Kategorisi | Hangi kişisel veri kategorisi (envanter referansı) |
| Hukuki Sebep | KVKK m.5/6 hangi şartı altında işleniyordu, hangi şartın sona ermesi imhayı tetikledi |
| Kapsam (Sayı/Ortam) | Etkilenen kayıt sayısı, ortam (DB/dosya/sunucu/medya) |
| Yöntem | Silme / Yok Etme / Anonim Hale Getirme — alt yöntem (DELETE, fiziksel parçalama, k-anonim, vb.) |
| Standart Atfı | Uygulanan teknik standart (NIST 800-88, DIN 66399 vb.) varsa |
| Kanıt Türü | Hash, log, foto, sertifika |
| Üçüncü Kişi Aktarımı | Veri aktarılmış mı? Bildirim yapıldı mı? |
| Tedarikçi | Şirket dışı imha hizmeti varsa tedarikçi adı + sertifika no |
| Sorumlu (Hazırlayan) | İmhayı uygulayan kişi (ad, unvan, imza) |
| Doğrulayan | Bilgi Güvenliği bağımsız doğrulama (ad, unvan, imza) |
| Onaylayan | KVKK Sorumlusu (ad, unvan, imza) |
| Hukuki Onay | Hukuk Müdürü (ad, unvan, imza) |
| Saklanma Süresi | Tutanağın asgari saklama süresi (en az 3 yıl) |
| Eki Belgeler | Sistem log, foto, sertifika, hash listesi |

## 3. Tutanak Numaralandırma Şeması

```
[YIL]/[YÖNTEM]/[SIRA]
örnek: 2026/IMHA-0142
       2026/PER-0007 (Periyodik İmha)
       2026/TLP-0023 (İlgili Kişi Talebi)
```

## 4. Tutanak Saklama

- Saklama süresi: Yön. m.7(3) — en az 3 yıl. Kurum içi standart: 5 yıl.
- Saklama formatı: Elektronik imzalı PDF + sistem audit log.
- Saklama yeri: KVKK Sorumlusu kontrolünde güvenli arşiv (erişim sınırlı, log kayıtlı).
- Saklama metaverisi: Tutanak no, tarih, kategori, sorumlu — aranabilir indekste.

---

## 5. Genel Tutanak Şablonu

```
══════════════════════════════════════════════════════
KİŞİSEL VERİ İMHA TUTANAĞI
══════════════════════════════════════════════════════

Tutanak No:        : ____________________________
Tutanak Türü       : [ ] Periyodik     [ ] İlgili Kişi Talebi
                     [ ] Tetiklenmiş   [ ] Tedarikçi İmhası
                     [ ] Diğer: __________________________

İşlem Tarihi/Saati : ____/____/______ — ___:___
İşlem Yeri         : ______________________________
                     (Fiziksel adres veya sistem adı)

──────────────────────────────────────────────────────
1. KAPSAMA İLİŞKİN BİLGİLER
──────────────────────────────────────────────────────
Veri Kategorisi    : __________________________________
                     (Envanter Madde No: __________)
Veri Sahibi Grup   : __________________________________
                     (Çalışan / Müşteri / Aday / Tedarikçi
                      / Ziyaretçi / Diğer)
Hukuki Sebep —
İşleme Şartı       : KVKK m.____ / m.____
                     Şartın Sona Erme Sebebi:
                     _________________________________
Kayıt Sayısı       : _________ kayıt
Tarih Aralığı      : ____/____/____ — ____/____/____
Ortam              : [ ] Aktif veritabanı
                     [ ] Yedek (rotasyon / soğuk)
                     [ ] Kağıt belge
                     [ ] Manyetik medya (HDD/Tape)
                     [ ] SSD/Flash medya
                     [ ] Optik medya
                     [ ] Bulut nesne depolama
                     [ ] Log/SIEM
                     [ ] Diğer: __________________

──────────────────────────────────────────────────────
2. UYGULANAN İMHA YÖNTEMİ
──────────────────────────────────────────────────────
Ana Yöntem         : [ ] Silme (Yön. m.8)
                     [ ] Yok Etme (Yön. m.9)
                     [ ] Anonim Hale Getirme (Yön. m.10)

Alt Yöntem         : ____________________________________
                     (DELETE/UPDATE, degauss, parçalama,
                      yakma, sanitize, crypto-shred,
                      k-anonim, generalization, vb.)

Uygulanan Standart : ____________________________________
                     (NIST 800-88 Purge/Destroy,
                      DIN 66399 P-4/P-5/P-7,
                      DoD 5220.22-M, ISO 27040, vb.)

Yöntem Seçim
Gerekçesi          : ____________________________________

──────────────────────────────────────────────────────
3. KANIT VE DOĞRULAMA
──────────────────────────────────────────────────────
Hash Kanıtları     : Eki-1 (ayrı dosya)
                     SHA-256 hash adedi: __________
Sistem Logu        : Eki-2 (ayrı dosya)
                     Log Sistemi: ____________________
                     Job ID: _________________________
                     Başlangıç: __:__:__  Bitiş: __:__:__
Görsel Kanıt       : [ ] Var (Eki-3) — foto/video
                     [ ] Yok
Tedarikçi Sertif.  : [ ] Yok
                     [ ] Var: ____________________ no
                     Tedarikçi: ____________________

──────────────────────────────────────────────────────
4. ÜÇÜNCÜ KİŞİ AKTARIMI
──────────────────────────────────────────────────────
Aktarılan Üçüncü
Kişiler            : [ ] Yok
                     [ ] Var: __________________________

Üçüncü Kişiye
Bildirim           : [ ] Yapıldı (Tarih: __/__/____)
                     [ ] Bekliyor
                     [ ] Uygulanabilir değil
Üçüncü Kişi
Onayı/Teyidi       : [ ] Alındı (Tarih: __/__/____)
                     [ ] Bekliyor

──────────────────────────────────────────────────────
5. SORUMLULAR VE İMZALAR
──────────────────────────────────────────────────────
Hazırlayan (İmhayı Uygulayan)
  Ad Soyad         : ____________________________
  Unvan / Birim    : ____________________________
  Tarih            : ____/____/______
  İmza             : ____________________________

Doğrulayan (Bilgi Güvenliği — bağımsız)
  Ad Soyad         : ____________________________
  Unvan / Birim    : ____________________________
  Tarih            : ____/____/______
  İmza             : ____________________________

KVKK Sorumlusu Onayı
  Ad Soyad         : ____________________________
  Unvan            : KVKK Sorumlusu
  Tarih            : ____/____/______
  İmza             : ____________________________

Hukuki Onay (Hukuk Müdürü)
  Ad Soyad         : ____________________________
  Unvan            : Hukuk Müdürü
  Tarih            : ____/____/______
  İmza             : ____________________________

──────────────────────────────────────────────────────
6. SAKLAMA VE ARŞİVLEME
──────────────────────────────────────────────────────
Tutanak Saklama
Süresi             : En az 3 yıl (Yön. m.7(3))
                     Kurum standardı: 5 yıl
Arşiv Yeri         : __________________________________
Arşiv Numarası     : __________________________________

══════════════════════════════════════════════════════
EKİ BELGELER
══════════════════════════════════════════════════════
[ ] Eki-1: Hash listesi (SHA-256)
[ ] Eki-2: Sistem logu çıktısı
[ ] Eki-3: Foto/video kanıtı
[ ] Eki-4: Tedarikçi imha sertifikası
[ ] Eki-5: Üçüncü kişi bildirim/teyit yazısı
[ ] Eki-6: İlgili kişi başvuru ve cevap (varsa)
[ ] Eki-7: Yöntem teknik talimatı/runbook çıktısı
══════════════════════════════════════════════════════
```

---

## 6. Örnek Tutanak 1 — Kağıt Belge Shredder ile Yok Etme

```
══════════════════════════════════════════════════════
KİŞİSEL VERİ İMHA TUTANAĞI
══════════════════════════════════════════════════════

Tutanak No         : 2026/PER-0007
Tutanak Türü       : [X] Periyodik
İşlem Tarihi/Saati : 12/05/2026 — 10:30
İşlem Yeri         : Genel Müdürlük — IK Arşivi (B-Blok B1)

──────────────────────────────────────────────────────
1. KAPSAMA İLİŞKİN BİLGİLER
──────────────────────────────────────────────────────
Veri Kategorisi    : İşe alım sürecinde reddedilen aday CV'leri
                     (Envanter Madde No: IK-04)
Veri Sahibi Grup   : Çalışan adayı
Hukuki Sebep —
İşleme Şartı       : KVKK m.5/2-(f) Meşru menfaat
                     Şartın Sona Erme Sebebi:
                     2 yıllık azami saklama süresi doldu
Kayıt Sayısı       : 1.142 dosya
Tarih Aralığı      : 01/01/2024 — 30/04/2024
Ortam              : [X] Kağıt belge

──────────────────────────────────────────────────────
2. UYGULANAN İMHA YÖNTEMİ
──────────────────────────────────────────────────────
Ana Yöntem         : [X] Yok Etme (Yön. m.9)
Alt Yöntem         : Cross-cut shredder (mikro kesim)
Uygulanan Standart : DIN 66399 P-5
Yöntem Seçim
Gerekçesi          : Kağıt ortamda kişisel veri içeren
                     başvuru dosyaları; geri döndürme
                     riski olmaksızın yok etme zorunlu.

──────────────────────────────────────────────────────
3. KANIT VE DOĞRULAMA
──────────────────────────────────────────────────────
Hash Kanıtları     : N/A (kağıt ortam)
Sistem Logu        : N/A
Görsel Kanıt       : [X] Var — Eki-3 (3 adet foto:
                     öncesi-sırasında-sonrası)
Tedarikçi Sertif.  : [X] Yok (kurum içi shredder)

──────────────────────────────────────────────────────
4. ÜÇÜNCÜ KİŞİ AKTARIMI
──────────────────────────────────────────────────────
Aktarılan Üçüncü
Kişiler            : [X] Yok

──────────────────────────────────────────────────────
5. SORUMLULAR VE İMZALAR
──────────────────────────────────────────────────────
Hazırlayan         : Ayşe DEMİR — IK Uzmanı
Doğrulayan         : Mehmet KAYA — Bilgi Güvenliği Uzmanı
KVKK Sorumlusu     : Selin YILDIZ — KVKK Sorumlusu
Hukuki Onay        : Av. Ahmet ÖZ — Hukuk Müdürü

──────────────────────────────────────────────────────
6. SAKLAMA VE ARŞİVLEME
──────────────────────────────────────────────────────
Saklama Süresi     : 5 yıl
Arşiv Yeri         : KVKK Arşivi — Dolap 03 / Klasör 14
Arşiv Numarası     : KVKK-ARS-2026-0007

══════════════════════════════════════════════════════
EKİ BELGELER
══════════════════════════════════════════════════════
[X] Eki-3: 3 adet foto (öncesi/sırasında/sonrası)
[X] Eki-7: IK-PROC-005 Aday Dosyası İmha Talimatı v2.1
══════════════════════════════════════════════════════
```

---

## 7. Örnek Tutanak 2 — HDD Degausser + Fiziksel Parçalama

```
══════════════════════════════════════════════════════
KİŞİSEL VERİ İMHA TUTANAĞI
══════════════════════════════════════════════════════

Tutanak No         : 2026/IMHA-0142
Tutanak Türü       : [X] Tetiklenmiş (Donanım hurdaya çıkma)
İşlem Tarihi/Saati : 18/05/2026 — 14:00
İşlem Yeri         : Veri Merkezi — Disk İmha Odası

──────────────────────────────────────────────────────
1. KAPSAMA İLİŞKİN BİLGİLER
──────────────────────────────────────────────────────
Veri Kategorisi    : Eski ERP sunucusu disk diziminden
                     çıkartılan HDD'ler (çalışan, müşteri,
                     finansal veriler dahil karma)
                     (Envanter Madde No: BT-12, BT-13)
Veri Sahibi Grup   : Çalışan + Müşteri + Tedarikçi
Hukuki Sebep —
İşleme Şartı       : Çoklu — KVKK m.5/2-(c) sözleşme
                     ifası + (e) hak tesisi + (f) meşru
                     menfaat
                     Şartın Sona Erme Sebebi: Sistem
                     migrasyonu sonrası eski donanımın
                     kullanım dışı çıkarılması
Kayıt Sayısı       : Disk başına ~~ TB; toplam veri
                     hacmi tahmini 2.3 TB
Ortam              : [X] Manyetik medya (HDD)

  Disk Listesi:
  Seri No                Üretici    Kapasite
  WD-WMC4M0H17832        WD         2 TB
  WD-WMC4M0H17855        WD         2 TB
  ST3000DM001-Z3T2HK1    Seagate    3 TB
  ST3000DM001-Z3T2HM2    Seagate    3 TB
  ... (toplam 8 disk)

──────────────────────────────────────────────────────
2. UYGULANAN İMHA YÖNTEMİ
──────────────────────────────────────────────────────
Ana Yöntem         : [X] Yok Etme (Yön. m.9)
Alt Yöntem         : 1) Degausser ile manyetik silme
                     2) Mekanik parçalama (drive shredder)
Uygulanan Standart : NIST 800-88 Rev.1 Purge → Destroy
Yöntem Seçim
Gerekçesi          : Donanım yeniden kullanılmayacak;
                     hassas veri içerir; çoklu yöntem ile
                     telafisi imkansız geri getirme.

──────────────────────────────────────────────────────
3. KANIT VE DOĞRULAMA
──────────────────────────────────────────────────────
Hash Kanıtları     : Disk öncesi disk imajından alınan
                     hash'ler — Eki-1 (kontrol amaçlı)
Sistem Logu        : Degausser cihaz logu — Eki-2
                     Cihaz: Garner HD-3WXL
                     Kalibrasyon: 2026-04-01 (geçerli)
Görsel Kanıt       : [X] Var — Eki-3:
                     - Disk öncesi (seri no görünür)
                     - Degausser işlem sırası
                     - Parçalama sonrası (parça hali)
Tedarikçi Sertif.  : [X] Yok (kurum içi cihaz)

──────────────────────────────────────────────────────
4. ÜÇÜNCÜ KİŞİ AKTARIMI
──────────────────────────────────────────────────────
Aktarılan Üçüncü
Kişiler            : [X] Var: ABC Lojistik A.Ş. (eski
                     teslimat kayıtları paylaşıldı)
Üçüncü Kişiye
Bildirim           : [X] Yapıldı (20/05/2026 / KEP yolu)
Üçüncü Kişi
Onayı/Teyidi       : [ ] Bekliyor (taahhüt 30 gün içinde)

──────────────────────────────────────────────────────
5. SORUMLULAR VE İMZALAR
──────────────────────────────────────────────────────
Hazırlayan         : Burak ÇELİK — Sistem Yöneticisi
Doğrulayan         : Mehmet KAYA — Bilgi Güvenliği Uzmanı
KVKK Sorumlusu     : Selin YILDIZ — KVKK Sorumlusu
Hukuki Onay        : Av. Ahmet ÖZ — Hukuk Müdürü

──────────────────────────────────────────────────────
6. SAKLAMA VE ARŞİVLEME
──────────────────────────────────────────────────────
Saklama Süresi     : 5 yıl
Arşiv Yeri         : KVKK Dijital Arşiv (e-imzalı PDF)
Arşiv Numarası     : KVKK-ARS-2026-0142

══════════════════════════════════════════════════════
EKİ BELGELER
══════════════════════════════════════════════════════
[X] Eki-1: Disk hash listesi (SHA-256)
[X] Eki-2: Degausser cihaz logu (CSV çıktı)
[X] Eki-3: Foto-video kanıtı (3 adet, zaman damgalı)
[X] Eki-5: Üçüncü kişi (ABC Lojistik) bildirim KEP'i
[X] Eki-7: BT-PROC-018 Disk İmha Runbook v3.0
══════════════════════════════════════════════════════
```

---

## 8. Örnek Tutanak 3 — Bulut Veritabanı Silme + Crypto-Shredding

```
══════════════════════════════════════════════════════
KİŞİSEL VERİ İMHA TUTANAĞI
══════════════════════════════════════════════════════

Tutanak No         : 2026/TLP-0023
Tutanak Türü       : [X] İlgili Kişi Talebi
İşlem Tarihi/Saati : 03/06/2026 — 16:45
İşlem Yeri         : AWS eu-central-1 — Production
                     veritabanı + S3 yedek

──────────────────────────────────────────────────────
1. KAPSAMA İLİŞKİN BİLGİLER
──────────────────────────────────────────────────────
Veri Kategorisi    : E-ticaret üye hesap kayıtları
                     (Envanter Madde No: ECOM-01)
Veri Sahibi Grup   : Tek bir müşteri (Talep No:
                     KVKK-BSV-2026-0214)
Hukuki Sebep —
İşleme Şartı       : Açık rıza geri çekildi (KVKK m.5/1);
                     Sözleşmesel ilişki sona ermiş;
                     Vergi/ticari saklama süresi geçilmiş.
                     Şartın Sona Erme Sebebi: Tüm işleme
                     şartları ortadan kalktı (Yön. m.12/1-a)
Kayıt Sayısı       : 1 müşteri profili + 47 sipariş
                     kaydı + 312 oturum/erişim logu
Ortam              : [X] Bulut nesne depolama (S3)
                     [X] Aktif veritabanı (RDS PostgreSQL)
                     [X] Log/SIEM (CloudWatch + ES)
                     [X] Yedek (RDS otomatik snapshot)

──────────────────────────────────────────────────────
2. UYGULANAN İMHA YÖNTEMİ
──────────────────────────────────────────────────────
Ana Yöntem         : [X] Silme (Yön. m.8) — aktif sistem
                     [X] Yok Etme (Yön. m.9) — yedek
Alt Yöntem         : 1) DB: hard-delete (DELETE)
                        + audit kaydı
                     2) S3: object delete + version delete
                        + lifecycle expiry
                     3) Log: PII alanları null + indeks
                        bazlı retention
                     4) Yedek: BYOK DEK (Data Encryption
                        Key) imhası — crypto-shredding
Uygulanan Standart : Bulut sağlayıcı DPA (AWS) imha
                     taahhüdü; NIST 800-88 Purge (kripto)
Yöntem Seçim
Gerekçesi          : Bulutta donanım imhası mümkün değil;
                     anahtar imhası ile pratik yok etme
                     gerçekleştirildi. İlgili kişiye
                     yöntem ve gerekçe ile bilgi verildi.

──────────────────────────────────────────────────────
3. KANIT VE DOĞRULAMA
──────────────────────────────────────────────────────
Hash Kanıtları     : Müşteri ID hash'i (SHA-256) —
                     Eki-1 (verinin kendisi tutulmadı)
Sistem Logu        : - RDS general log (Eki-2)
                     - CloudTrail KMS API logu (Eki-2)
                     - S3 access log (Eki-2)
                     Job ID: KVKK-PURGE-2026-0023
                     Başlangıç: 16:30:12 — Bitiş: 16:43:28
Görsel Kanıt       : [X] Var — Eki-3 (KMS konsol ekran
                     görüntüsü "Pending deletion" → "Deleted")
Tedarikçi Sertif.  : N/A (AWS DPA kapsamında)

──────────────────────────────────────────────────────
4. ÜÇÜNCÜ KİŞİ AKTARIMI
──────────────────────────────────────────────────────
Aktarılan Üçüncü
Kişiler            : [X] Var:
                     - Lojistik tedarikçisi (sipariş adresi)
                     - Ödeme servisi (ödeme tokenları)
                     - Pazarlama otomasyon SaaS sağlayıcısı
Üçüncü Kişiye
Bildirim           : [X] Yapıldı (03/06/2026 / KEP yolu)
Üçüncü Kişi
Onayı/Teyidi       : [X] Lojistik — alındı 05/06/2026
                     [X] Ödeme — alındı 04/06/2026
                     [ ] Pazarlama — bekliyor (15 gün)

──────────────────────────────────────────────────────
5. SORUMLULAR VE İMZALAR
──────────────────────────────────────────────────────
Hazırlayan         : Burak ÇELİK — Sistem Yöneticisi
Doğrulayan         : Mehmet KAYA — Bilgi Güvenliği Uzmanı
KVKK Sorumlusu     : Selin YILDIZ — KVKK Sorumlusu
Hukuki Onay        : Av. Ahmet ÖZ — Hukuk Müdürü

──────────────────────────────────────────────────────
6. SAKLAMA VE ARŞİVLEME
──────────────────────────────────────────────────────
Saklama Süresi     : 5 yıl
Arşiv Yeri         : KVKK Dijital Arşiv (e-imzalı PDF)
Arşiv Numarası     : KVKK-ARS-2026-0023

══════════════════════════════════════════════════════
EKİ BELGELER
══════════════════════════════════════════════════════
[X] Eki-1: Müşteri ID hash listesi (SHA-256)
[X] Eki-2: AWS sistem logları (RDS, CloudTrail, S3)
[X] Eki-3: KMS Pending Deletion → Deleted ekran görüntüsü
[X] Eki-5: 3 üçüncü kişiye gönderilen KEP + alınan teyit
[X] Eki-6: İlgili kişi başvuru (No: KVKK-BSV-2026-0214)
            ve veri sorumlusunun cevap yazısı
[X] Eki-7: BT-PROC-024 Bulut PII Purge Runbook v2.0
══════════════════════════════════════════════════════
```

## 9. Tutanak Doğrulama Kontrol Listesi

İmha tutanağı imzaya çıkmadan önce KVKK Sorumlusu aşağıdaki kontrolleri yapar:

- [ ] Tutanak no şirket içi sıra ile tutarlı
- [ ] İşleme şartı ve şartın sona erme sebebi açıkça yazılmış
- [ ] Veri kategorisi envanter ile birebir uyumlu
- [ ] Kayıt sayısı ve hash adedi tutarlı
- [ ] Yöntem, ortam türüne uygun seçilmiş
- [ ] Uygulanan standart referans verilmiş
- [ ] Kanıt türü (hash/log/foto/sertifika) belirtilmiş
- [ ] Üçüncü kişi aktarımı kontrol edilmiş; bildirim yapılmış
- [ ] 4 imza tamam (Hazırlayan, Doğrulayan, KVKK Sorumlusu, Hukuk Müdürü)
- [ ] Eki belgeler eksiksiz
- [ ] Saklama süresi ve arşiv numarası verilmiş
- [ ] Elektronik imza atılmış
