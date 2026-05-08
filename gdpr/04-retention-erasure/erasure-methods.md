---
title:
  en: "Erasure Methods"
  tr: "Silme Yöntemleri"
section: "04-retention-erasure"
document_type: "technical_standard"
regulation: "GDPR (EU 2016/679)"
articles:
  - "Art. 5(1)(e) — Storage limitation"
  - "Art. 17 — Right to erasure"
  - "Art. 25 — Data protection by design and by default"
  - "Art. 32 — Security of processing"
  - "Recital 26 — Anonymisation vs. pseudonymisation"
related_standards:
  - "NIST SP 800-88 Rev. 1 — Guidelines for Media Sanitization"
  - "ISO/IEC 27040:2024 — Storage security"
  - "DIN 66399 — Office machines and data destruction"
  - "ISO/IEC 21964 — Destruction of data carriers (ex-DIN 66399)"
language: "en, tr"
last_reviewed: "2025-05-01"
review_cycle: "annual"
owner: "Information Security"
co_owner: "Data Protection Officer"
status: "approved"
classification: "internal"
---

## English

# Erasure Methods

This document defines the technical methods used to erase personal data securely under GDPR. It is the operational complement to the Retention Policy and the Retention Schedule.

## 1. Conceptual framework

### 1.1 Erasure ≠ deletion-from-UI

A deletion that only hides data from the user interface is **not** erasure under GDPR. Personal data persists in:
- Production database (rows still present, "deleted" flag set).
- Replication targets (read replicas, BI warehouses).
- Backups, snapshots, archive logs.
- Caches (CDN, application, browser).
- Search indexes (Elasticsearch, OpenSearch).
- Logs (application, audit, access).
- Off-site backups (tape, cold storage).
- Email, ticketing, collaboration tools (forwarded copies).
- Local copies on endpoints.
- Paper printouts.

**True erasure** addresses each persistence layer.

### 1.2 NIST SP 800-88 Rev. 1: Clear, Purge, Destroy

The industry standard for media sanitisation defines three levels:

| Level | Definition | Use case |
|---|---|---|
| **Clear** | Logical techniques sanitising data in all user-addressable storage locations against simple non-invasive recovery (e.g., overwrite, factory reset). | Devices to be reused within the same control boundary. |
| **Purge** | Physical or logical techniques rendering recovery infeasible even with state-of-the-art laboratory techniques (e.g., cryptographic erase, secure erase, degaussing for magnetic media). | Devices leaving the control boundary; storage of sensitive personal data. |
| **Destroy** | Physical destruction making the storage media unusable as media (e.g., shredding, incineration, melting, pulverisation). | Storage that contained special-category personal data; end-of-life media; high-risk environments. |

The Schedule maps each data category to a recommended NIST level.

### 1.3 Anonymisation vs pseudonymisation (Recital 26)

| Property | Anonymisation | Pseudonymisation |
|---|---|---|
| Reversibility | Irreversible | Reversible with additional information |
| GDPR scope | Out of scope (no longer personal data) | In scope (still personal data) |
| Risk-based test | "Means reasonably likely to be used" by the controller or any other person to identify | Identifying information held separately under technical/organisational measures |
| Use case | Statistical archive, public data release | Reduced risk in processing while keeping reversibility option |

**Anonymisation is a form of erasure** when it satisfies Recital 26 — the data is no longer personal data and need not be deleted.

**Pseudonymisation is *not* erasure**. Pseudonymous data is still personal data; only the identification linkage is partitioned.

### 1.4 The "reasonably likely" test (Recital 26)

A dataset is anonymous only if re-identification by any reasonably likely means — by the controller or any other person — is not possible. Consider:

- Singling-out attacks (one record uniquely identifiable).
- Linkability (same individual identifiable across two datasets).
- Inference (attribute can be inferred with significant probability).

Use Article 29 WP Opinion 05/2014 on Anonymisation Techniques as the assessment framework.

## 2. Method catalogue

### 2.1 Database row deletion

| Aspect | Detail |
|---|---|
| Description | SQL `DELETE` (or equivalent) of rows containing personal data. |
| Strength | Operational; preferred for active databases. |
| Weakness | Soft-delete patterns (`is_deleted` flag) do **not** count. Tombstones, MVCC versions, and WAL/redo logs may retain data temporarily. |
| Mitigation | Vacuum/compaction, point-in-time-recovery (PITR) window expiry, encryption-at-rest with crypto-shredding for backups. |
| Verification | Query the row by primary key; expect zero results. Compare row count before/after. |
| Audit evidence | Database audit log entry, ticket reference, operator ID, timestamp. |

### 2.2 Logical (in-place) overwrite — NIST Clear

| Aspect | Detail |
|---|---|
| Description | Overwriting all addressable sectors with a fixed pattern, random data, or zeros. |
| Strength | Effective for HDDs, USB sticks, removable drives. |
| Weakness | Ineffective on SSDs (wear-levelling means the OS-visible sectors are not the only place data lives). |
| Tools | `dd if=/dev/urandom of=/dev/sdX bs=1M`, `shred -n 1 -z`, vendor secure-erase utilities. |
| Verification | Sample-read sectors; verify pattern. |
| When to use | Reuse within same control boundary, low-sensitivity data. |

### 2.3 Cryptographic erase — NIST Purge

| Aspect | Detail |
|---|---|
| Description | Destruction of the encryption key used to encrypt the data, rendering ciphertext unrecoverable. |
| Strength | Instantaneous; works on SSDs, cloud storage, encrypted volumes. |
| Pre-requisite | Data must have been encrypted from inception with a key under the controller's management. |
| Key management | Document the key destruction event; ensure no key escrow / backup retains the key. |
| Verification | Hardware key destruction certificate; KMS audit log; cryptographic proof of key destruction. |
| When to use | Backups, cloud storage, cold storage, distributed file systems. |

### 2.4 ATA Secure Erase / NVMe Format / Sanitize commands — NIST Purge

| Aspect | Detail |
|---|---|
| Description | Manufacturer-implemented firmware command that sanitises all user-accessible storage. |
| Strength | Effective for SSDs and self-encrypting drives. |
| Weakness | Some implementations are flawed; verify per drive model. |
| Tools | `hdparm --security-erase`, `nvme format -s1`, vendor utilities. |
| Verification | Drive returns "sanitize complete" status; sample-read sectors. |
| When to use | Drive reissue, drive return to vendor. |

### 2.5 Degaussing — NIST Purge (magnetic only)

| Aspect | Detail |
|---|---|
| Description | Strong magnetic field that randomises magnetic domains on tape or HDD platter. |
| Strength | Effective for magnetic media. |
| Weakness | Ineffective on flash, optical media. Renders the drive unusable. |
| Tools | NSA-EPL-listed degaussers. |
| Verification | Witnessed; degausser produces a per-cycle log. |
| When to use | High-sensitivity HDDs and tapes prior to decommissioning. |

### 2.6 Physical destruction — NIST Destroy

| Aspect | Detail |
|---|---|
| Description | Shredding, pulverisation, incineration, melting. |
| Strength | Highest assurance. |
| Standards | DIN 66399 / ISO 21964 — security levels P/T/E/F/H/O for paper and electronic media. P-7 / H-7 / E-5 / T-7 are highest assurance. |
| Verification | Witnessed by Information Security; supplier provides destruction certificate with serial numbers and dates. |
| When to use | Special-category data, end-of-life, regulated environments. |

### 2.7 Anonymisation

| Aspect | Detail |
|---|---|
| Description | Irreversible removal of identifiability. |
| Techniques | Generalisation, suppression, k-anonymity (k≥5 typical, k≥10 for sensitive), l-diversity, t-closeness, differential privacy. |
| Test | Re-identification by any reasonably likely means impossible. |
| Documentation | Anonymisation methodology, residual-risk assessment, DPO sign-off. |
| When to use | Long-term retention for analytics, research; alternative to deletion. |

### 2.8 Pseudonymisation (NOT erasure but referenced for completeness)

| Aspect | Detail |
|---|---|
| Description | Replacement of identifiers with tokens; mapping table held separately. |
| Risk reduction | Significant (Recital 28); part of supplementary measures under Schrems II. |
| Erasure interaction | Erasure of mapping table = effective anonymisation of the residual dataset. |
| When to use | Risk reduction during processing; staged path to anonymisation. |

## 3. Application by data type

| Data type | Recommended method (default) | Recommended method (sensitive) |
|---|---|---|
| Active production DB row | Row delete + vacuum + PITR expiry | + crypto-shred backups |
| Encrypted backups (cloud) | Crypto-shred (delete key) | Crypto-shred + lifecycle expiry |
| Unencrypted backups | Re-encrypt for crypto-shred path; or wait expiry under restriction | Physical destruction at expiry |
| HDD (decommission) | NIST Purge (secure erase) | NIST Destroy (shred) |
| SSD (decommission) | Crypto-shred + NVMe sanitize | NIST Destroy (shred) |
| Tape (decommission) | Degauss | Degauss + shred |
| Paper | DIN 66399 P-4 (general) | P-7 (sensitive) |
| Endpoint device | Crypto-shred + NIST Clear | NIST Destroy |
| Email mailbox | Mailbox deletion + retention policy | + e-discovery purge |
| Cloud SaaS data | Vendor erasure procedure + processor certificate | + crypto-shred at processor |
| Search index | Document delete + index reindex | + offline rebuild |
| Cache | TTL expiry + force purge | + warm-cache invalidation |
| Log streams | Log lifecycle expiry | + immutable log + key destruction |

## 4. Cloud erasure considerations

### 4.1 Object storage (S3, GCS, Azure Blob)

- Use **versioning** with care: previous versions persist after a "delete" unless versioning is disabled or lifecycle expires versions.
- Use **lifecycle rules** for automatic expiry.
- Use **object lock / immutable storage** only with a defined retention; understand it blocks erasure during the lock period.
- Use **server-side encryption with customer-managed keys (SSE-KMS / CMEK)** to enable crypto-shredding by destroying the key.
- Confirm the provider's deletion latency in the DPA (e.g., 30–90 days for soft-delete in some platforms).

### 4.2 Managed databases

- Drop, then verify automated backups are also expired or crypto-shredded.
- Read replicas inherit deletes via replication; verify lag and confirm.
- Logical backups (`pg_dump`, `mysqldump`) must be tracked separately.

### 4.3 SaaS processors

- Article 28 contract must include erasure obligation and certificate.
- Verify sub-processor propagation (the SaaS provider's own backup vendor).
- Request **deletion log access** during DSAR responses.
- Track SaaS-vendor "trash" / "recycle bin" auto-expiry windows.

### 4.4 Multi-region replication

- Erasure must propagate to all regions.
- Document replication topology.
- Verify per-region erasure for global services (e.g., user is in EU, but data is replicated to US disaster-recovery region; the US copy must also be erased).

## 5. Backup erasure strategy

### 5.1 The problem

A pure "delete from production + delete from backup" pattern collapses when:
- Backups are immutable (ransomware protection, compliance hold).
- Backup tapes are off-site and not individually addressable.
- Backups span multiple processors and geographies.

### 5.2 Recommended pattern: crypto-shred + lifecycle expiry

1. **Encrypt all backups** with per-backup-set keys, ideally with hierarchical KMS structure (per-tenant, per-period).
2. **Delete the key** for the relevant scope when erasure is required (per tenant, per data subject, per period).
3. **Restrict** processing of any backup that may contain the data subject's residual record (Art. 18 — restriction of processing).
4. **Allow lifecycle expiry** of the encrypted ciphertext.
5. **Document** in the destruction record.

### 5.3 Pattern: graveyard list

For implementations where per-record crypto-shredding is infeasible:

- Maintain a "graveyard list" of erased identifiers.
- On any restore, immediately re-apply the erasure (re-delete) before resuming production access.
- Document the restore-erase procedure.

### 5.4 Pattern: short backup retention

The simplest mitigation: reduce backup retention to the minimum operationally and legally required. A 30-day backup window means erasure becomes effective within 30 days for most production workloads.

## 6. Paper destruction

| DIN 66399 level | Particle size | Use |
|---|---|---|
| P-1 | ≤2,000 mm² | Public information |
| P-2 | ≤800 mm² | Internal information |
| P-3 | ≤320 mm² | Sensitive information |
| P-4 | ≤160 mm² | Personal data (default) |
| P-5 | ≤30 mm² | Sensitive personal data |
| P-6 | ≤10 mm² | Special-category personal data |
| P-7 | ≤5 mm² | Highly classified |

Defaults:
- General office output: P-4 minimum.
- HR / financial / contracts: P-5.
- Medical / biometric / criminal record: P-6 or P-7.

Procedure:
- Locked shred bins in office locations.
- Witnessed destruction or certified destruction service.
- Destruction certificate retained per `destruction-record.md`.

## 7. Verification and assurance

| Activity | Frequency | Evidence |
|---|---|---|
| Sample destruction record review | Quarterly | DPO report |
| Sample drive sector verification post-Purge | Each batch | Secure erase log |
| Vendor certificate review | Each engagement | Vendor certificate |
| Crypto-shred KMS audit | Quarterly | KMS audit log; key absence proof |
| Backup expiry verification | Per cycle | Backup index report |
| Erasure propagation spot-check | Monthly | DPO sample audit (DSAR fulfilment) |

## 8. Common errors

| Error | Why it fails | Correction |
|---|---|---|
| "Quick format" of disk | Filesystem metadata wiped, data sectors intact | Use NIST Purge or Destroy |
| "Move to trash" / "Recycle bin" | Trash is just a soft-delete folder | Empty trash + verify backend deletion |
| Setting `is_deleted = true` flag | Data still present and reportable | Replace with row delete + audit. |
| Unmounting volume | No data alteration | Use sanitisation tooling. |
| Reformatting SSD | May not touch all blocks due to wear-levelling | Use cryptographic erase + sanitize. |
| Destroying tape without degaussing | Magnetic data may remain on shredded fragments | Degauss before shred. |
| Crypto-shredding without key destruction proof | Key may persist in KMS audit / backup | Require destruction certificate from KMS provider. |
| Anonymisation that allows re-identification | Still personal data | Apply Recital 26 test rigorously. |

## 9. Decision flow

```
Is the data on:
├── Live production database?
│   └── Row delete → vacuum → PITR expiry → confirm replicas
├── Encrypted backup?
│   └── Crypto-shred key → restrict processing → await ciphertext lifecycle expiry
├── Unencrypted backup?
│   └── Plan migration to encrypted; meanwhile restrict + expire ASAP
├── HDD (physical)?
│   └── Reuse: NIST Clear/Purge | Decommission: NIST Purge or Destroy
├── SSD (physical)?
│   └── Crypto-shred + NVMe sanitize | Decommission high-risk: NIST Destroy
├── Tape (magnetic)?
│   └── Degauss + (Destroy if special-category)
├── Paper?
│   └── DIN P-4 default; P-5/P-6/P-7 by sensitivity
├── SaaS?
│   └── Vendor erasure procedure + certificate + sub-processor propagation
└── Cache/index?
    └── Force purge + invalidate + reindex if needed
```

---

## Türkçe

# Silme Yöntemleri

Bu belge, GDPR kapsamında kişisel verilerin güvenli biçimde silinmesi için kullanılan teknik yöntemleri tanımlar. Saklama Politikası ve Saklama Çizelgesinin operasyonel tamamlayıcısıdır.

## 1. Kavramsal çerçeve

### 1.1 Silme ≠ UI'dan kaldırma

Verileri yalnızca kullanıcı arayüzünden gizleyen bir silme, GDPR kapsamında silme **değildir**. Kişisel veriler şunlarda kalmaya devam eder:
- Üretim veritabanı (satırlar hâlâ mevcut, "silindi" bayrağı ayarlandı).
- Çoğaltma hedefleri (okuma replikaları, BI ambarları).
- Yedekler, snapshot'lar, arşiv logları.
- Önbellekler (CDN, uygulama, tarayıcı).
- Arama indeksleri (Elasticsearch, OpenSearch).
- Loglar (uygulama, denetim, erişim).
- Site dışı yedekler (bant, soğuk depolama).
- E-posta, talep yönetimi, işbirliği araçları (iletilmiş kopyalar).
- Uç noktalardaki yerel kopyalar.
- Kâğıt çıktılar.

**Gerçek silme** her kalıcılık katmanını ele alır.

### 1.2 NIST SP 800-88 Rev. 1: Clear, Purge, Destroy

Medya sanitasyonu için endüstri standardı üç seviye tanımlar:

| Seviye | Tanım | Kullanım |
|---|---|---|
| **Clear** | Tüm kullanıcı tarafından adreslenebilir depolama konumlarındaki verileri basit invaziv olmayan kurtarmaya karşı sanitize eden mantıksal teknikler (örn. üzerine yazma, fabrika sıfırlaması). | Aynı kontrol sınırı içinde yeniden kullanılacak cihazlar. |
| **Purge** | Son teknoloji laboratuvar teknikleriyle bile kurtarmayı uygulanamaz hale getiren fiziksel veya mantıksal teknikler (örn. kriptografik silme, güvenli silme, manyetik medya için demanyetizasyon). | Kontrol sınırını terk eden cihazlar; hassas kişisel veri depolaması. |
| **Destroy** | Depolama medyasını medya olarak kullanılamaz hale getiren fiziksel imha (örn. parçalama, yakma, eritme, toz haline getirme). | Özel kategori kişisel veri içeren depolama; ömür sonu medya; yüksek riskli ortamlar. |

Çizelge her veri kategorisini önerilen NIST seviyesine eşler.

### 1.3 Anonimleştirme - takma adlandırma (Resital 26)

| Özellik | Anonimleştirme | Takma adlandırma |
|---|---|---|
| Geri çevrilebilirlik | Geri çevrilemez | Ek bilgi ile geri çevrilebilir |
| GDPR kapsamı | Kapsam dışı (artık kişisel veri değil) | Kapsamda (hâlâ kişisel veri) |
| Risk temelli test | Kontrolör veya başka bir kişi tarafından "makul olarak kullanılması muhtemel araçlar" | Tanımlama bilgisi teknik/organizasyonel önlemler altında ayrı tutulur |
| Kullanım | İstatistiksel arşiv, kamu veri yayını | Geri çevrilebilirlik seçeneğini koruyarak işlemede risk azaltma |

**Anonimleştirme bir silme biçimidir**, Resital 26'yı karşıladığında — veri artık kişisel veri değildir ve silinmesi gerekmez.

**Takma adlandırma silme *değildir***. Takma adlı veri hâlâ kişisel veridir; yalnızca tanımlama bağlantısı bölünmüştür.

### 1.4 "Makul olarak muhtemel" testi (Resital 26)

Bir veri seti yalnızca, makul olarak muhtemel herhangi bir araçla — kontrolör veya başka bir kişi tarafından — yeniden tanımlama mümkün değilse anonimdir. Düşünün:

- Tek tek seçme saldırıları (bir kayıt benzersiz olarak tanımlanabilir).
- Bağlanabilirlik (aynı birey iki veri setinde tanımlanabilir).
- Çıkarım (öznitelik anlamlı olasılıkla çıkarılabilir).

Değerlendirme çerçevesi olarak Madde 29 ÇG Görüşü 05/2014 Anonimleştirme Teknikleri'ni kullanın.

## 2. Yöntem kataloğu

### 2.1 Veritabanı satır silme

| Yön | Detay |
|---|---|
| Açıklama | Kişisel veri içeren satırların SQL `DELETE` (veya eşdeğeri) işlemi. |
| Güç | Operasyonel; aktif veritabanları için tercih edilir. |
| Zayıflık | Yumuşak silme kalıpları (`is_deleted` bayrağı) sayılmaz. Tombstone'lar, MVCC sürümleri ve WAL/redo logları veriyi geçici olarak tutabilir. |
| Hafifletme | Vakum/kompaksiyon, point-in-time-recovery (PITR) penceresi sona erme, yedekler için kripto-parçalama ile depo şifrelemesi. |
| Doğrulama | Birincil anahtar ile satırı sorgula; sıfır sonuç bekle. Önce/sonra satır sayısını karşılaştır. |
| Denetim kanıtı | Veritabanı denetim log girdisi, talep referansı, operatör kimliği, zaman damgası. |

### 2.2 Mantıksal (yerinde) üzerine yazma — NIST Clear

| Yön | Detay |
|---|---|
| Açıklama | Tüm adreslenebilir sektörleri sabit bir desen, rastgele veri veya sıfır ile üzerine yazma. |
| Güç | HDD'ler, USB çubukları, çıkarılabilir sürücüler için etkilidir. |
| Zayıflık | SSD'lerde etkisiz (aşınma dengeleme, OS-görünür sektörlerin verinin yaşadığı tek yer olmadığı anlamına gelir). |
| Araçlar | `dd if=/dev/urandom of=/dev/sdX bs=1M`, `shred -n 1 -z`, satıcı güvenli silme yardımcıları. |
| Doğrulama | Örnek-okuma sektörler; deseni doğrula. |
| Ne zaman | Aynı kontrol sınırı içinde yeniden kullanım, düşük hassasiyet veri. |

### 2.3 Kriptografik silme — NIST Purge

| Yön | Detay |
|---|---|
| Açıklama | Veriyi şifrelemek için kullanılan şifreleme anahtarının imhası, şifreli metni kurtarılamaz hale getirir. |
| Güç | Anlık; SSD'ler, bulut depolama, şifrelenmiş birimlerde çalışır. |
| Ön koşul | Veri başlangıçtan itibaren kontrolörün yönetimi altındaki bir anahtarla şifrelenmiş olmalıdır. |
| Anahtar yönetimi | Anahtar imha olayını belgele; anahtar emanet/yedekte anahtar tutmadığından emin ol. |
| Doğrulama | Donanım anahtar imha sertifikası; KMS denetim logu; anahtar imhasının kriptografik kanıtı. |
| Ne zaman | Yedekler, bulut depolama, soğuk depolama, dağıtılmış dosya sistemleri. |

### 2.4 ATA Secure Erase / NVMe Format / Sanitize komutları — NIST Purge

| Yön | Detay |
|---|---|
| Açıklama | Tüm kullanıcı erişilebilir depolamayı sanitize eden üretici uygulamalı bellenim komutu. |
| Güç | SSD'ler ve kendi kendini şifreleyen sürücüler için etkilidir. |
| Zayıflık | Bazı uygulamalar kusurludur; sürücü modeline göre doğrulayın. |
| Araçlar | `hdparm --security-erase`, `nvme format -s1`, satıcı yardımcıları. |
| Doğrulama | Sürücü "sanitize tamamlandı" durumu döndürür; örnek-okuma sektörler. |
| Ne zaman | Sürücü yeniden verme, sürücüyü satıcıya iade. |

### 2.5 Demanyetizasyon — NIST Purge (yalnızca manyetik)

| Yön | Detay |
|---|---|
| Açıklama | Bant veya HDD plakasında manyetik alanları rastgele hale getiren güçlü manyetik alan. |
| Güç | Manyetik medya için etkilidir. |
| Zayıflık | Flash, optik medyada etkisizdir. Sürücüyü kullanılamaz hale getirir. |
| Araçlar | NSA-EPL listesi demanyetizatörler. |
| Doğrulama | Tanıklı; demanyetizatör döngü başına log üretir. |
| Ne zaman | Devre dışı bırakmadan önce yüksek hassasiyet HDD'ler ve bantlar. |

### 2.6 Fiziksel imha — NIST Destroy

| Yön | Detay |
|---|---|
| Açıklama | Parçalama, toz haline getirme, yakma, eritme. |
| Güç | En yüksek güvence. |
| Standartlar | DIN 66399 / ISO 21964 — kâğıt ve elektronik medya için P/T/E/F/H/O güvenlik seviyeleri. P-7 / H-7 / E-5 / T-7 en yüksek güvencedir. |
| Doğrulama | Bilgi Güvenliği tarafından tanıklı; tedarikçi seri numaraları ve tarihlerle imha sertifikası sağlar. |
| Ne zaman | Özel kategori veri, ömür sonu, düzenlenmiş ortamlar. |

### 2.7 Anonimleştirme

| Yön | Detay |
|---|---|
| Açıklama | Tanımlanabilirliğin geri çevrilemez kaldırılması. |
| Teknikler | Genelleme, baskılama, k-anonimlik (k≥5 tipik, hassas için k≥10), l-çeşitlilik, t-yakınlık, diferansiyel gizlilik. |
| Test | Makul olarak muhtemel herhangi bir araçla yeniden tanımlama imkânsız. |
| Belgeleme | Anonimleştirme metodolojisi, artık-risk değerlendirmesi, DPO onayı. |
| Ne zaman | Analitik, araştırma için uzun vadeli saklama; silmeye alternatif. |

### 2.8 Takma adlandırma (silme DEĞİL ancak bütünlük için referans)

| Yön | Detay |
|---|---|
| Açıklama | Tanımlayıcıların token'larla değiştirilmesi; eşleme tablosu ayrı tutulur. |
| Risk azaltma | Anlamlı (Resital 28); Schrems II kapsamında tamamlayıcı önlemlerin parçası. |
| Silme etkileşimi | Eşleme tablosunun silinmesi = artık veri setinin etkili anonimleştirilmesi. |
| Ne zaman | İşleme sırasında risk azaltma; anonimleştirmeye aşamalı yol. |

## 3. Veri türüne göre uygulama

| Veri türü | Önerilen yöntem (varsayılan) | Önerilen yöntem (hassas) |
|---|---|---|
| Aktif üretim DB satırı | Satır silme + vakum + PITR son | + yedek kripto-parçalama |
| Şifrelenmiş yedekler (bulut) | Kripto-parçalama (anahtar sil) | Kripto-parçalama + yaşam döngüsü son |
| Şifrelenmemiş yedekler | Kripto-parçalama yolu için yeniden şifrele; veya kısıtlama altında son bekle | Son tarihinde fiziksel imha |
| HDD (devre dışı bırakma) | NIST Purge (güvenli silme) | NIST Destroy (parçala) |
| SSD (devre dışı bırakma) | Kripto-parçalama + NVMe sanitize | NIST Destroy (parçala) |
| Bant (devre dışı bırakma) | Demanyetize | Demanyetize + parçala |
| Kâğıt | DIN 66399 P-4 (genel) | P-7 (hassas) |
| Uç nokta cihazı | Kripto-parçalama + NIST Clear | NIST Destroy |
| E-posta posta kutusu | Posta kutusu silme + saklama politikası | + e-discovery temizleme |
| Bulut SaaS verisi | Satıcı silme prosedürü + işleyen sertifikası | + işleyende kripto-parçalama |
| Arama indeksi | Belge silme + indeks yeniden indeksleme | + çevrimdışı yeniden oluşturma |
| Önbellek | TTL son + zorla temizleme | + sıcak önbellek geçersiz kılma |
| Log akışları | Log yaşam döngüsü son | + değişmez log + anahtar imha |

## 4. Bulut silme hususları

### 4.1 Nesne depolama (S3, GCS, Azure Blob)

- **Sürümleme** dikkatli kullanın: önceki sürümler "silmeden" sonra kalır, yaşam döngüsü sürümleri sona erdirmez veya sürümleme devre dışı bırakılmazsa.
- Otomatik son için **yaşam döngüsü kuralları** kullanın.
- Yalnızca tanımlanmış saklama ile **nesne kilidi / değişmez depolama** kullanın; kilit süresi boyunca silmeyi engellediğini anlayın.
- Anahtarı imha ederek kripto-parçalamayı etkinleştirmek için **müşteri tarafından yönetilen anahtarlarla sunucu tarafı şifreleme (SSE-KMS / CMEK)** kullanın.
- DPA'da sağlayıcının silme gecikmesini onaylayın (örn. bazı platformlarda yumuşak silme için 30–90 gün).

### 4.2 Yönetilen veritabanları

- Bırakın, ardından otomatik yedeklerin de süresinin dolduğunu veya kripto-parçalandığını doğrulayın.
- Okuma replikaları çoğaltma yoluyla silmeleri devralır; gecikmeyi doğrulayın ve onaylayın.
- Mantıksal yedekler (`pg_dump`, `mysqldump`) ayrı izlenmelidir.

### 4.3 SaaS işleyenleri

- Madde 28 sözleşmesi silme yükümlülüğü ve sertifika içermelidir.
- Alt-işleyen yayılımını doğrulayın (SaaS sağlayıcının kendi yedek satıcısı).
- DSAR yanıtları sırasında **silme log erişimi** isteyin.
- SaaS satıcısı "çöp" / "geri dönüşüm kutusu" otomatik son pencerelerini izleyin.

### 4.4 Çoklu bölge çoğaltması

- Silme tüm bölgelere yayılmalıdır.
- Çoğaltma topolojisini belgeleyin.
- Küresel hizmetler için bölge başına silmeyi doğrulayın (örn. kullanıcı AB'de, ancak veri ABD felaket-kurtarma bölgesine çoğaltıldı; ABD kopyası da silinmelidir).

## 5. Yedek silme stratejisi

### 5.1 Sorun

Saf bir "üretimden sil + yedekten sil" kalıbı şu durumlarda çöker:
- Yedekler değişmez (fidye yazılım koruması, uyumluluk bekletme).
- Yedek bantları site dışı ve ayrı ayrı adreslenemez.
- Yedekler birden fazla işleyen ve coğrafyaya yayılır.

### 5.2 Önerilen kalıp: kripto-parçalama + yaşam döngüsü son

1. Tüm yedekleri **per-yedek-set anahtarlarıyla şifreleyin**, ideal olarak hiyerarşik KMS yapısıyla (kiracı başına, dönem başına).
2. İlgili kapsam için silme gerekli olduğunda **anahtarı silin** (kiracı başına, ilgili kişi başına, dönem başına).
3. İlgili kişinin artık kaydını içerebilecek herhangi bir yedeğin işlenmesini **kısıtlayın** (Md. 18 — işleme kısıtlaması).
4. Şifrelenmiş şifreli metnin **yaşam döngüsü son**unu bekleyin.
5. İmha kaydında **belgeleyin**.

### 5.3 Kalıp: mezarlık listesi

Kayıt başına kripto-parçalamanın uygulanamadığı uygulamalar için:

- Silinen tanımlayıcıların "mezarlık listesi" tutun.
- Herhangi bir geri yüklemede, üretim erişimine devam etmeden önce silmeyi anında yeniden uygulayın (yeniden silin).
- Geri yükleme-silme prosedürünü belgeleyin.

### 5.4 Kalıp: kısa yedek saklama

En basit hafifletme: yedek saklamayı operasyonel ve hukuken gerekli minimuma azaltın. 30 günlük yedek penceresi, çoğu üretim iş yükü için silmenin 30 gün içinde etkili olduğu anlamına gelir.

## 6. Kâğıt imhası

| DIN 66399 seviye | Parçacık boyutu | Kullanım |
|---|---|---|
| P-1 | ≤2,000 mm² | Kamu bilgisi |
| P-2 | ≤800 mm² | İç bilgi |
| P-3 | ≤320 mm² | Hassas bilgi |
| P-4 | ≤160 mm² | Kişisel veri (varsayılan) |
| P-5 | ≤30 mm² | Hassas kişisel veri |
| P-6 | ≤10 mm² | Özel kategori kişisel veri |
| P-7 | ≤5 mm² | Yüksek gizlilik |

Varsayılanlar:
- Genel ofis çıktısı: minimum P-4.
- İK / finansal / sözleşmeler: P-5.
- Tıbbi / biyometrik / sabıka: P-6 veya P-7.

Prosedür:
- Ofis konumlarında kilitli parçalama kutuları.
- Tanıklı imha veya sertifikalı imha hizmeti.
- `destruction-record.md` başına imha sertifikası tutulur.

## 7. Doğrulama ve güvence

| Faaliyet | Sıklık | Kanıt |
|---|---|---|
| Örnek imha kayıt incelemesi | Üç ayda | DPO raporu |
| Purge sonrası örnek sürücü sektör doğrulaması | Her parti | Güvenli silme logu |
| Satıcı sertifika incelemesi | Her görev | Satıcı sertifikası |
| Kripto-parçalama KMS denetimi | Üç ayda | KMS denetim logu; anahtar yokluğu kanıtı |
| Yedek son doğrulaması | Döngü başına | Yedek indeks raporu |
| Silme yayma anlık denetim | Aylık | DPO örnek denetim (DSAR yerine getirme) |

## 8. Yaygın hatalar

| Hata | Neden başarısız | Düzeltme |
|---|---|---|
| Diskin "hızlı formatı" | Dosya sistemi metaverisi silindi, veri sektörleri sağlam | NIST Purge veya Destroy kullan |
| "Çöpe taşı" / "Geri dönüşüm kutusu" | Çöp sadece yumuşak silme klasörüdür | Çöpü boşalt + arka uç silmesini doğrula |
| `is_deleted = true` bayrağı ayarlama | Veri hâlâ mevcut ve raporlanabilir | Satır silme + denetim ile değiştir. |
| Birim sökme | Veri değişikliği yok | Sanitasyon araçları kullan. |
| SSD yeniden formatlama | Aşınma dengeleme nedeniyle tüm blokları etkilemeyebilir | Kriptografik silme + sanitize kullan. |
| Demanyetize etmeden bandı imha | Manyetik veri parçalanmış parçalarda kalabilir | Parçalamadan önce demanyetize et. |
| Anahtar imha kanıtı olmadan kripto-parçalama | Anahtar KMS denetiminde / yedekte kalabilir | KMS sağlayıcısından imha sertifikası gerektir. |
| Yeniden tanımlamaya izin veren anonimleştirme | Hâlâ kişisel veri | Resital 26 testini titizlikle uygula. |

## 9. Karar akışı

```
Veri nerede:
├── Canlı üretim veritabanı?
│   └── Satır silme → vakum → PITR son → replikaları onayla
├── Şifrelenmiş yedek?
│   └── Anahtar kripto-parçala → işlemeyi kısıtla → şifreli metin yaşam döngüsü son bekle
├── Şifrelenmemiş yedek?
│   └── Şifrelemeye geçişi planla; bu arada kısıtla + en kısa sürede son
├── HDD (fiziksel)?
│   └── Yeniden kullan: NIST Clear/Purge | Devre dışı: NIST Purge veya Destroy
├── SSD (fiziksel)?
│   └── Kripto-parçala + NVMe sanitize | Yüksek risk devre dışı: NIST Destroy
├── Bant (manyetik)?
│   └── Demanyetize + (Özel kategori ise Destroy)
├── Kâğıt?
│   └── DIN P-4 varsayılan; hassasiyete göre P-5/P-6/P-7
├── SaaS?
│   └── Satıcı silme prosedürü + sertifika + alt-işleyen yayma
└── Önbellek/indeks?
    └── Zorla temizleme + geçersiz kıl + gerekirse yeniden indeksle
```
