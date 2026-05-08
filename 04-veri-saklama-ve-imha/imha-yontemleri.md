---
Doküman / Document: İmha Yöntemleri ve Ortam Bazlı Uygulama Matrisi / Destruction Methods and Medium-Based Application Matrix
Bölüm / Section: 04-veri-saklama-ve-imha
Sahip / Owner: Bilgi Güvenliği Yöneticisi / Information Security Manager
Onaylayan / Approved by: KVKK Sorumlusu + Hukuk Müdürü / KVKK Officer + Legal Director
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş / Annual + triggered (new technology, new data category, post-breach)
İlgili Mevzuat / Legal Reference: Reg. Art. 7, 8, 9, 10; Data Security Guide (Technical Measures); NIST SP 800-88 Rev.1 (reference); ISO/IEC 27040 (reference)
---

## English

# Destruction Methods and Medium-Based Application Matrix

## 1. Introduction

The Regulation's umbrella concept of "destruction" covers three distinct methods (Reg. Art. 4(1)/c). Each method has different **legal effect**, **application threshold** and **evidence obligation**. Method selection is not arbitrary; the structure of the medium, the nature of the data, the technical capacity of the data controller and data processor, and the reversibility risk are evaluated together (Reg. Art. 7(5)).

```
                       DESTRUCTION (umbrella)
                          |
        +-----------------+-----------------+
        |                 |                 |
     ERASURE          DESTRUCTION        ANONYMIZATION
     (Reg. Art. 8)    (Reg. Art. 9)      (Reg. Art. 10)
        |                 |                 |
Inaccessible to      Inaccessible to    Permanently removing
relevant users        anyone, irretriev-  the personal nature
and unusable          able and unusable   from the data
```

## 2. Method 1 — Erasure (Reg. Art. 8)

### 2.1. Definition

Rendering personal data inaccessible and unusable in any way for **relevant users**. The yardstick here is the "relevant user"; the person responsible for technical storage or backups (system administrator, backup operator) is excluded.

### 2.2. Application Forms

- **Row deletion in database (DELETE):** Active data row is deleted. A separate plan is needed for copies remaining in backups and logs.
- **Combination of soft-delete + hard-delete:** First the row is marked "deleted" (in integrated apps for referential integrity), then physically deleted via a retention job. Soft-delete alone is **NOT** erasure within the meaning of Reg. Art. 8.
- **File delete + overwrite of free space:** Not sustainable; trace and recovery risks exist. **Secure delete** tools should be used in enterprise environments.
- **Cloud object delete + version cleanup:** Version history must also be deleted for versioned objects.
- **Authorization removal (access-focused erasure):** Accepted only for data held under the special responsibility of the data controller; the data subject's access is removed.
- **Record redaction/masking:** Applied when only specific fields, not the entire row, of visual/written documents must be removed. This method is treated as **partial erasure** depending on record type.

### 2.3. Common Mistakes

- Active table deleted, backup forgotten — still accessible in backup.
- Moved to "Recycle Bin" / "Trash" — user can restore, erasure incomplete.
- Moved to another table as passive data — re-accessible, not erasure.
- Hidden only in UI — kept in backend, the relevant user can still access.
- Soft-delete deemed permanent — no hard-delete plan.

## 3. Method 2 — Destruction (Reg. Art. 9)

### 3.1. Definition

Rendering personal data inaccessible, irretrievable and unusable in any way by **anyone**. The threshold is higher: it covers backups, log fragments, physical media.

### 3.2. Application Forms

- **Physical media destruction:** HDDs/SSDs/USBs/CDs/magnetic tapes are physically shredded, melted, incinerated.
- **Magnetic medium degauss:** Erasure of data from magnetic disks by a strong magnetic field. **Not suitable** for SSDs (does not affect NAND structure).
- **Cryptographic shredding (crypto-shredding):** If data was written encrypted with AES-256, destroying only the encryption key practically destroys the data. Most practical method for cloud, distributed environments and large backups.
- **Destruction of all backups:** Backups kept under rotation are destroyed when rotation completes after a destruction request; if rotation end is not awaited, the backup key is destroyed.
- **Tape (magnetic tape) destruction:** Degauss + physical cutting.
- **Paper document destruction:** Approved shredder (Cross-cut DIN P-4 or P-5 minimum, P-7 for classified documents); incineration for special documents.

### 3.3. NIST 800-88 Classification (Reference)

| Class | Definition | Use |
|-------|------------|-----|
| Clear | Overwrite using standard software | Low confidentiality, medium reused |
| Purge | Render irretrievable via hardware or cryptographic technique | Mid-high confidentiality, medium can be reused |
| Destroy | Physical shredding, incineration, melting | High confidentiality or medium not reused |

In Turkish law, the concept of **Destruction (Reg. Art. 9)** corresponds to NIST's **Purge** and **Destroy** levels. "Clear" alone is insufficient for destruction.

## 4. Method 3 — Anonymization (Reg. Art. 10)

### 4.1. Definition

Rendering personal data unable to be associated with an identified or identifiable natural person, even when matched with other data. The data leaves the personal data status; KVKK no longer applies.

**Critical:** Anonymization must produce **true anonymity** with respect to reversibility and matching. Removing only direct identifiers (name, national ID number) is not enough; combinations of quasi-identifiers (age, postal code, profession, gender) carry re-identification risk.

### 4.2. Pseudonymization is NOT Anonymization

Pseudonymization is replacing direct identifiers with another key while the linkage data **continues to be retained at the data controller**. This is personal data, not anonymous. It cannot be used for destruction within the meaning of Reg. Art. 10; it is valuable only as a **processing safeguard**.

### 4.3. Anonymization Techniques

| Technique | Description | Strength | Data Utility |
|-----------|-------------|----------|--------------|
| **Generalization** | Raising a specific value to a more general category (e.g. "age 27" → "age range 20–29") | Medium | High |
| **Suppression** | Complete deletion of a specific field | High | Medium |
| **Noise addition** | Adding controlled noise to numerical values | Med-High | High (for stats) |
| **Permutation** | Swapping field values across records | Medium | Medium |
| **Tokenization (non-reversible)** | Replacing direct identifier with surrogate; **anonymization if mapping table is destroyed** | High | High |
| **k-anonymity** | Each row resembles at least k-1 other rows (quasi-identifier combination) | Medium | High |
| **l-diversity** | Sensitive attribute takes at least l different values within the k-anonymous group | High | Medium |
| **t-closeness** | Distribution of sensitive attribute within k-anonymous group is within distance "t" of the original distribution | High | Med-Low |
| **Differential privacy** | Mathematical noise added to query outputs; presence/absence of an individual indistinguishable | Very High | Low-Medium |

### 4.4. Re-Identification Risk Assessment

Anonymization must always be done with risk assessment:

```
+----------------------------------------+
| 1. Mapping the dataset                 |
| - Direct identifiers                   |
| - Quasi-identifiers                    |
| - Sensitive attributes                 |
+----------------------------------------+
                 |
                 v
+----------------------------------------+
| 2. Threat model                        |
| - Who can access? (internal/external)  |
| - Which side data can match?           |
| - Motivation and cost                  |
+----------------------------------------+
                 |
                 v
+----------------------------------------+
| 3. Three-risk assessment               |
| - Singling out                         |
| - Linkability                          |
| - Inference                            |
+----------------------------------------+
                 |
                 v
+----------------------------------------+
| 4. Technique selection and application |
+----------------------------------------+
                 |
                 v
+----------------------------------------+
| 5. Outcome verification                |
| - Re-identification testing            |
| - Attack scenario simulation           |
+----------------------------------------+
                 |
                 v
+----------------------------------------+
| 6. Is residual risk acceptable?        |
+----------------------------------------+
            |               |
         yes|             no|
            v               v
        Publish        Strengthen
                       technique
```

If residual risk is not acceptable, the data is **not anonymous** and continues to be processed under KVKK.

## 5. Medium-Based Application Matrix

### 5.1. Paper Medium

| Data Type | Method | Standard | Evidence |
|-----------|--------|----------|----------|
| General office documents | Cross-cut shredder | DIN 66399 P-4 | Destruction record + daily log |
| Personnel file, contract | Cross-cut shredder | DIN 66399 P-5 | Destruction record + 2-person signature |
| Health report, financial | Micro-shredder + incineration | DIN 66399 P-7 | Destruction record + 3-person signature + photo evidence |
| High sensitivity (national ID lists) | Incineration | — | Record + footage of incineration site |
| Vendor destruction service | Certified third-party destruction (NAID AAA recommended) | — | Vendor destruction certificate + record |

### 5.2. Magnetic Disk (HDD)

| Scenario | Method | Standard |
|----------|--------|----------|
| Reuse | DoD 5220.22-M (3-pass) or NIST 800-88 Clear | Destruction log, hash evidence |
| Reuse — high sensitivity | NIST 800-88 Purge — degausser | Degausser calibration record + record |
| End of life | Physical shredding (shredder, crusher) | Photo evidence + record |
| End of life — encrypted disk | Key destruction + dismantle | Key destruction log + record |

### 5.3. SSD (NAND/Flash)

> **Critical:** Degausser is ineffective on SSDs; software overwrite is also not guaranteed due to wear-leveling. Only safe paths are physical destruction or the device's own **secure erase / sanitize** command (TCG Opal, NVMe sanitize).

| Scenario | Method | Standard |
|----------|--------|----------|
| Reuse | Device's sanitize command (NVMe Format with crypto-erase, ATA Sanitize) | NIST 800-88 Purge |
| End of life | Physical destruction (chip-level shredder) | Photo evidence + record |

### 5.4. USB Memory, SD Card, Optical Media

| Medium | Method |
|--------|--------|
| USB / SD card (NAND) | Sanitize + physical destruction |
| CD / DVD / Blu-ray | Optical shredder (P-7 equivalent for classified) |
| Magnetic tape (LTO) | Degausser + physical cutting |

### 5.5. Cloud Environment

| Scenario | Method |
|----------|--------|
| IaaS / VM disk | Cloud provider disk delete + provider's "secure deletion" policy evidence (DPA + certificate) |
| Object storage (S3, blob, GCS) | Object delete + version history delete + lifecycle rule + (if Object Lock) end retention |
| Managed database | Record delete + transaction log cleanup + backup destruction calendar |
| Backup (managed) | Provider backup destruction commitment + retention policy + crypto-shredding (if BYOK) |
| SaaS app | Destruction commitment from provider (DPA "termination data deletion" clause) + provider destruction certificate |

> **Crypto-shredding** is the most practical method for cloud: keys are kept in HSM/KMS; when data is to be destroyed, the key is destroyed; data becomes mathematically inaccessible. Key management must be kept independent.

### 5.6. Database

| Scenario | Method |
|----------|--------|
| Active row | DELETE / UPDATE (personal field NULL/anonymous) |
| Personal data in audit log | Log row anonymization + retention job |
| Transaction log | Database maintenance plan, log truncation, old WAL/redo log cleanup |
| Backup files | Destruction within backup rotation; backup key destruction if needed |
| Replication | Retention jobs run on read replicas as well; replication lag added to period calculation |
| Materialized view, index, full-text search | Rebuilding all derived structures after delete operations |

#### 5.6.1. SQL Example (PostgreSQL — Hard Delete + Audit)

```sql
BEGIN;

INSERT INTO kvkk_imha_audit (
    islem_id, tablo_adi, satir_id, islem_tarihi, gerekce, sorumlu, hash
) VALUES (
    gen_random_uuid(), 'musteri', :musteri_id, now(),
    'Periodic destruction — retention period expired', :sorumlu_id,
    digest(:musteri_id::text || now()::text, 'sha256')
);

DELETE FROM musteri WHERE id = :musteri_id;

COMMIT;
```

The audit record answers "what, when, who, why." The hash proves records were not subsequently altered.

### 5.7. Log Files

Logs typically contain personal data (IP, username, national ID, phone, email). In addition to log retention policy:

- **Structured logs (JSON, structured):** Personal fields are masked/erased on retention.
- **Unstructured logs (text):** The log file is fully deleted at end of retention.
- **SIEM:** Tied to index retention policy; old indexes are auto-deleted.
- **Logs in backups:** Destroyed together with backup rotation.

## 6. Method Selection Decision Tree

```
+---------------------------------+
| Destruction obligation arose    |
+---------------------------------+
              |
              v
+---------------------------------+
| Is the data valuable in         |
| anonymous form for analytics?   |
+---------------------------------+
        |                |
     yes|             no|
        v                v
+--------------+   +-----------------+
| Reg. Art. 10 |   | Will the data   |
| Anonymization|   | medium be       |
|              |   | reused?         |
+--------------+   +-----------------+
                        |          |
                    yes|        no|
                        v          v
              +--------------+  +--------------+
              | Reg. Art. 8  |  | Reg. Art. 9  |
              | Erasure      |  | Destruction  |
              | (relevant    |  | (physical/   |
              |  user        |  |  crypto      |
              |  access      |  |  destruction)|
              |  removed)    |  +--------------+
              +--------------+
```

## 7. Evidence Management

For every destruction operation:

- **Record:** Per the [imha-kayit-tutanagi-sablonu.md](imha-kayit-tutanagi-sablonu.md) template.
- **Hash evidence:** SHA-256 digest of the deleted record's identity is taken; the data itself is not retained, only the hash.
- **Photo/video:** For physical destruction.
- **System log:** Start/end timestamps of the operation, executing user, job ID.
- **Vendor certificate:** If a third-party destruction vendor is used.
- **Chain of custody:** Chain showing the hands the medium passed through until destruction.

## 8. Risk Scenarios and Countermeasures

| Risk | Countermeasure |
|------|----------------|
| Data destroyed in active system stayed in tape backups for years | Backup rotation period reflected in policy; made practical via backup key destruction |
| Cloud provider did "soft-delete" and reserved data | "Hard-delete" commitment in DPA; provider destruction certificate |
| Production data left in test environment | DLP + environment segmentation + masking obligation |
| DoD wipe done on SSD, data remained | Only sanitize/destroy for SSD; DoD wipe banned |
| Weak anonymization, re-identification possible | Annual re-identification test; quasi-identifier list |
| Pseudonymization deemed anonymous | Pseudonymization does not remove from KVKK scope; table makes this clear |
| No destruction record, evidence missing | Automated record generation (templated from job output) |
| Data exists in multiple copies (replication, cache) | Full data map before destruction; simultaneous destruction of all copies |

---

## Türkçe

# İmha Yöntemleri ve Ortam Bazlı Uygulama Matrisi

## 1. Giriş

Yönetmeliğin imha tanımı üç ayrı yöntemi kapsar (Yön. m.4(1)/c). Her yöntemin **hukuki sonucu**, **uygulama eşiği** ve **kanıt yükümlülüğü** farklıdır. Yöntem seçimi keyfi değildir; ortamın yapısı, verinin niteliği, veri sorumlusu ile veri işleyenin teknik kapasitesi ve geri döndürülebilirlik riski birlikte değerlendirilir (Yön. m.7(5)).

```
                        İMHA
                          |
        +-----------------+-----------------+
        |                 |                 |
      SİLME           YOK ETME       ANONİM HALE GETİRME
      (Yön. m.8)      (Yön. m.9)        (Yön. m.10)
        |                 |                 |
İlgili kullanıcılar   Hiç kimse        Verinin kişisel
için erişilemez       için erişilemez   nitelikten
ve tekrar             ve geri           kalıcı olarak
kullanılamaz          getirilemez       çıkarılması
```

## 2. Yöntem 1 — Silme (Yön. m.8)

### 2.1. Tanım

Kişisel verilerin **ilgili kullanıcılar** için hiçbir şekilde erişilemez ve tekrar kullanılamaz hale getirilmesi işlemidir. Burada ölçü "ilgili kullanıcı"dır; teknik olarak depolanmadan veya yedeklenmesinden sorumlu kişi (sistem yöneticisi, yedek operatörü) bu tanımın dışındadır.

### 2.2. Uygulama Şekilleri

- **Veritabanında satır silme (DELETE):** Aktif veride satır silinir. Yedek ve loglarda kalan kopyalar için ayrı plan gerekir.
- **Soft-delete + hard-delete birleşimi:** Önce satır "deleted" işaretlenir (entegre uygulamalarda referans bütünlüğü için), sonra retention job ile fiziken silinir. Soft-delete tek başına Yön. m.8 anlamında silme **DEĞİLDİR**.
- **Dosya silme + boş alan üzerine yazma:** Sürdürülemez; iz ve geri kazanım riski vardır. Kurumsal ortamda **secure delete** araçları kullanılmalıdır.
- **Bulutta nesne silme + sürüm temizliği:** Versionlu objelerde sürüm geçmişi de silinmelidir.
- **Yetki kaldırma (erişim odaklı silme):** Sadece veri sorumlusu özel sorumlulukta tutulan veriler için kabul edilir; veri sahibinin erişimi kalkmış olur.
- **Kayıt karartma/maskeleme:** Sadece görsel/yazılı belgelerde tüm satırın değil belirli alanların kaldırılması gerektiğinde uygulanır. Bu yöntem kayıt türüne göre **kısmi silme** olarak değerlendirilir.

### 2.3. Tipik Hatalar

- Aktif tabloyu sildi, yedeği unuttu — yedekte hâlâ erişilebilir.
- "Recycle bin" / "trash" içine taşıdı — kullanıcı geri çekebilir, silme tamamlanmamış.
- Pasif veri olarak başka tabloya taşındı — tekrar erişilebilir, silme değil.
- Sadece UI'da gizledi — backend'de tutuluyor, ilgili kullanıcı yine erişebilir.
- Soft-delete kalıcı kabul edildi — hard-delete planı yok.

## 3. Yöntem 2 — Yok Etme (Yön. m.9)

### 3.1. Tanım

Kişisel verilerin **hiç kimse** tarafından hiçbir şekilde erişilemez, geri getirilemez ve tekrar kullanılamaz hale getirilmesi işlemidir. Eşik daha yüksektir: yedekleri, log içindeki parçaları, fiziksel medyayı kapsar.

### 3.2. Uygulama Şekilleri

- **Fiziksel ortam imhası:** HDD/SSD/USB/CD/manyetik bant fiziksel olarak parçalanır, eritilir, yakılır.
- **Manyetik ortam degauss:** Manyetik diskler için güçlü manyetik alan ile veri silme. SSD için **uygun değildir** (NAND yapısına etki etmez).
- **Kriptografik silme (crypto-shredding):** Veri AES-256 ile şifreli yazılmışsa, sadece şifreleme anahtarının imhası ile veri pratik olarak yok edilir. Bulut, dağıtık ortam ve büyük yedekler için en pratik yöntemdir.
- **Tüm yedeklerin imhası:** Yedek rotasyon takvimine göre bekletilen yedekler, yok etme talebi sonrası rotasyon tamamlandığında imha edilir; rotasyon sonu beklenmediğinde yedek anahtarı imha edilir.
- **Tape (manyetik bant) imhası:** Degauss + fiziksel kesme.
- **Kağıt belge yok etme:** Onaylı imha makinesi (Cross-cut DIN P-4 veya P-5 minimum, gizlilik dereceli belgeler için P-7); özel evrak için yakma.

### 3.3. NIST 800-88 Sınıflandırması (Referans)

| Sınıf | Tanım | Kullanım |
|-------|-------|----------|
| Clear | Standart yazılım ile veri üzerine yazma | Düşük gizlilik, ortam yeniden kullanılacak |
| Purge | Donanım veya kriptografik teknik ile geri getirilemez kılma | Orta-yüksek gizlilik, ortam yeniden kullanılabilir |
| Destroy | Fiziksel parçalama, yakma, eritme | Yüksek gizlilik veya ortam kullanılmayacak |

Türk hukukunda **Yok Etme** kavramı NIST'in **Purge** ve **Destroy** seviyelerine karşılık gelir. Sadece "Clear" yok etme için yetersizdir.

## 4. Yöntem 3 — Anonim Hale Getirme (Yön. m.10)

### 4.1. Tanım

Kişisel verilerin başka verilerle eşleştirilse dahi hiçbir surette kimliği belirli veya belirlenebilir bir gerçek kişiyle ilişkilendirilemeyecek hale getirilmesidir. Veri kişisel veri olmaktan çıkar; KVKK kapsamından çıkar.

**Kritik:** Anonim hale getirme, geri döndürme ve eşleştirme açısından **gerçek anonimlik** üretmelidir. Sadece doğrudan tanıtıcının (ad, T.C. kimlik no) kaldırılması yeterli değildir; quasi-identifier (yaş, posta kodu, meslek, cinsiyet) kombinasyonu ile yeniden tanımlanma riski vardır.

### 4.2. Pseudonymization Anonimleştirme DEĞİLDİR

Pseudonymization (takma adlandırma); doğrudan tanıtıcılar yerine başka anahtar konulması, ancak bağlantı verisinin **veri sorumlusunda saklanmaya devam etmesi**dir. Bu kişisel veridir, anonim değildir. Yön. m.10 anlamında imha amacıyla kullanılamaz; sadece **işleme tedbiri** olarak değer taşır.

### 4.3. Anonimleştirme Teknikleri

| Teknik | Açıklama | Güç | Veri Faydası |
|--------|----------|-----|--------------|
| **Generalization** | Spesifik değerin daha genel kategoriye yükseltilmesi (ör. "27 yaş" → "20-29 yaş aralığı") | Orta | Yüksek |
| **Suppression** | Belirli alanın tamamen silinmesi | Yüksek | Orta |
| **Noise addition** | Sayısal değerlere kontrollü gürültü eklenmesi | Orta-Yüksek | Yüksek (istatistik için) |
| **Permutation** | Kayıtlar arası alan değerlerinin yer değiştirilmesi | Orta | Orta |
| **Tokenization (geri dönüşümlü değil)** | Doğrudan tanıtıcının takma değer ile değiştirilmesi; **eşleme tablosu imha edilirse** anonimleştirme | Yüksek | Yüksek |
| **k-anonimite** | Her satırın en az k-1 başka satıra benzemesi (quasi-identifier kombinasyonu) | Orta | Yüksek |
| **l-çeşitlilik** | k-anonim grubunda hassas özniteliğin en az l farklı değer alması | Yüksek | Orta |
| **t-yakınlık** | k-anonim grubunda hassas özniteliğin dağılımının orijinal dağılıma "t" mesafede olması | Yüksek | Orta-Düşük |
| **Diferansiyel gizlilik** | Sorgu çıktılarına matematik tabanlı gürültü; bireyin varlığı/yokluğu ayırt edilemez | Çok Yüksek | Düşük-Orta |

### 4.4. Yeniden Tanımlanma Riski Değerlendirmesi

Anonimleştirme her zaman risk değerlendirmesi ile yapılmalıdır:

```
+----------------------------------------+
| 1. Veri seti içeriğinin haritalanması  |
| - Doğrudan tanıtıcılar                 |
| - Quasi-identifier'lar                 |
| - Hassas öznitelikler                  |
+----------------------------------------+
                 |
                 v
+----------------------------------------+
| 2. Tehdit modeli                       |
| - Kim erişebilir? (iç/dış)             |
| - Hangi yan veri ile eşleştirebilir?   |
| - Motivasyon ve maliyet                |
+----------------------------------------+
                 |
                 v
+----------------------------------------+
| 3. Üç riskin değerlendirilmesi         |
| - Singling out (bireyi ayırma)         |
| - Linkability (eşleştirme)             |
| - Inference (çıkarım)                  |
+----------------------------------------+
                 |
                 v
+----------------------------------------+
| 4. Teknik seçimi ve uygulanması        |
+----------------------------------------+
                 |
                 v
+----------------------------------------+
| 5. Sonuç doğrulama                     |
| - Re-identification testi              |
| - Saldırı senaryosu simülasyonu        |
+----------------------------------------+
                 |
                 v
+----------------------------------------+
| 6. Risk kalıntısı kabul edilebilir mi? |
+----------------------------------------+
            |               |
        evet|            hayır|
            v               v
        Yayımla        Tekniği güçlendir
```

Risk kalıntısı kabul edilebilir değilse veri **anonim sayılmaz** ve KVKK kapsamında işlem görmeye devam eder.

## 5. Ortam Bazlı Uygulama Matrisi

### 5.1. Kağıt Ortam

| Veri Türü | Yöntem | Standart | Kanıt |
|-----------|--------|----------|-------|
| Genel ofis evrakı | Cross-cut shredder | DIN 66399 P-4 | İmha tutanağı + günlük log |
| Özlük dosyası, sözleşme | Cross-cut shredder | DIN 66399 P-5 | İmha tutanağı + 2 kişi imza |
| Sağlık raporu, finansal | Mikro-shredder + yakma | DIN 66399 P-7 | İmha tutanağı + 3 kişi imza + foto kanıt |
| Yüksek hassasiyet (TC No içeren toplu liste) | Yakma | — | Tutanak + yakma alanı görüntüsü |
| Tedarikçi imha hizmeti | Şirket dışı sertifikalı imha (NAID AAA önerilir) | — | Tedarikçi imha sertifikası + tutanak |

### 5.2. Manyetik Disk (HDD)

| Senaryo | Yöntem | Standart |
|---------|--------|----------|
| Yeniden kullanım | DoD 5220.22-M (3 geçiş) veya NIST 800-88 Clear | İmha logu, hash kanıtı |
| Yeniden kullanım — yüksek hassasiyet | NIST 800-88 Purge — degausser | Degausser kalibrasyon kaydı + tutanak |
| Kullanım dışı | Fiziksel parçalama (shredder, ezici makine) | Foto kanıt + tutanak |
| Kullanım dışı — şifreli yazılmış disk | Anahtar imhası + sökme | Anahtar imha kaydı + tutanak |

### 5.3. SSD (NAND/Flash)

> **Kritik:** SSD'de degausser etkisizdir; wear-leveling nedeniyle yazılım üzerine yazma da garanti vermez. Tek güvenli yol fiziksel imha veya cihazın kendi **secure erase / sanitize** komutudur (TCG Opal, NVMe sanitize).

| Senaryo | Yöntem | Standart |
|---------|--------|----------|
| Yeniden kullanım | Cihazın sanitize komutu (NVMe Format with crypto-erase, ATA Sanitize) | NIST 800-88 Purge |
| Kullanım dışı | Fiziksel imha (chip-level shredder) | Foto kanıt + tutanak |

### 5.4. USB Bellek, SD Kart, Optik Medya

| Ortam | Yöntem |
|-------|--------|
| USB / SD kart (NAND) | Sanitize + fiziksel imha |
| CD / DVD / Blu-ray | Optik shredder (gizlilik dereceli için P-7 eşdeğeri) |
| Manyetik bant (LTO) | Degausser + fiziksel kesme |

### 5.5. Bulut Ortamı

| Senaryo | Yöntem |
|---------|--------|
| IaaS / VM disk | Cloud sağlayıcı disk silme + sağlayıcının "secure deletion" politikasının kanıtı (DPA + sertifika) |
| Nesne depolama (S3, blob, GCS) | Object delete + version history delete + lifecycle rule + (Object Lock kullanılıyorsa) retention sona erdirme |
| Yönetilen veritabanı | Kayıt silme + transaction log temizliği + yedek imha takvimi |
| Yedek (managed backup) | Sağlayıcı yedek imha taahhütü + retention policy + crypto-shredding (anahtar BYOK ise) |
| SaaS uygulama | Sağlayıcıdan imha taahhüdü (DPA içinde "termination data deletion" maddesi) + sağlayıcının imha sertifikası |

> **Crypto-shredding** bulut için en pratik yöntemdir: anahtarlar HSM/KMS'te tutulur; veri silinmek istendiğinde anahtar imha edilir; veri matematik olarak erişilemez hale gelir. Anahtar yönetiminin bağımsız tutulması gerekir.

### 5.6. Veritabanı

| Senaryo | Yöntem |
|---------|--------|
| Aktif satır | DELETE / UPDATE (kişisel alan NULL/anonim) |
| Audit log içindeki kişisel veri | Log row anonimleştirme + retention job |
| Transaction log | Veritabanı bakım planı, log truncation, eski WAL/redo log temizliği |
| Yedek dosyaları | Yedek rotasyonu içinde imha; gerekirse yedek anahtarı imhası |
| Replikasyon | Read replica üzerinde de retention job çalıştırılır; replikasyon gecikmesi süre hesabına eklenir |
| Materialize view, index, full-text search | Silme operasyonları sonrası tüm türetilmiş yapıların yeniden inşası |

#### 5.6.1. SQL Örneği (PostgreSQL — Hard Delete + Audit)

```sql
BEGIN;

INSERT INTO kvkk_imha_audit (
    islem_id, tablo_adi, satir_id, islem_tarihi, gerekce, sorumlu, hash
) VALUES (
    gen_random_uuid(), 'musteri', :musteri_id, now(),
    'Periyodik imha — saklama süresi doldu', :sorumlu_id,
    digest(:musteri_id::text || now()::text, 'sha256')
);

DELETE FROM musteri WHERE id = :musteri_id;

COMMIT;
```

Audit kaydı, "ne, ne zaman, kim, neden" sorularını cevaplar. Hash, kayıtların sonradan değiştirilemediğini ispatlar.

### 5.7. Log Dosyaları

Loglar genellikle kişisel veri (IP, kullanıcı adı, T.C. No, telefon, e-posta) barındırır. Log retention politikasına ek olarak:

- **Yapılı loglar (JSON, structured):** Kişisel alanların maskelenerek / silinerek saklanması.
- **Yapısız loglar (text):** Saklama süresi sonunda log dosyası tümüyle silinir.
- **SIEM:** Index retention politikasına bağlanır; eski indekslerin silinmesi otomatik.
- **Yedeklerdeki loglar:** Yedek rotasyon ile birlikte imha edilir.

## 6. Yöntem Seçim Karar Ağacı

```
+---------------------------------+
| Veri imha yükümlülüğü oluştu    |
+---------------------------------+
              |
              v
+---------------------------------+
| Veri analitik/raporlama için    |
| anonim halde değerli mi?        |
+---------------------------------+
        |                |
    evet|            hayır|
        v                v
+--------------+   +-----------------+
| Yön. m.10    |   | Veri ortamı/    |
| Anonim hale  |   | medya yeniden   |
| getirme      |   | kullanılacak mı?|
+--------------+   +-----------------+
                        |          |
                    evet|       hayır|
                        v          v
              +--------------+  +--------------+
              | Yön. m.8     |  | Yön. m.9     |
              | Silme        |  | Yok etme     |
              | (ilgili      |  | (fiziksel/   |
              |  kullanıcı   |  |  kripto      |
              |  erişimi     |  |  imhası)     |
              |  kalkar)     |  +--------------+
              +--------------+
```

## 7. Kanıt Yönetimi

Her imha işlemi için:

- **Tutanak:** [imha-kayit-tutanagi-sablonu.md](imha-kayit-tutanagi-sablonu.md) şablonuna uygun.
- **Hash kanıtı:** Silinen kaydın özet kimliği SHA-256 ile alınır; verinin kendisi tutulmaz, sadece hash.
- **Foto/video:** Fiziksel imha için.
- **Sistem logu:** Operasyonun başlangıç-bitiş zaman damgası, çalışan kullanıcı, işlemin job ID'si.
- **Tedarikçi sertifikası:** Şirket dışı imha tedarikçisi varsa.
- **Chain of custody:** Ortamın imha noktasına ulaşana kadar geçtiği elleri gösteren zincir.

## 8. Risk Senaryoları ve Önlemler

| Risk | Önlem |
|------|-------|
| Yedek tape'lerde imha edilen veri yıllarca kaldı | Yedek rotasyon süresi politikaya yansıtılır; yedek anahtar imhası ile pratikleştirilir |
| Bulut sağlayıcı "soft-delete" yaptı, veri rezerv edildi | DPA'da "hard-delete" taahhüdü; sağlayıcı imha sertifikası |
| Test ortamında üretim verisi kaldı | DLP + ortam segmentasyonu + maskeleme zorunluluğu |
| SSD üzerinde DoD wipe yapıldı, veri kaldı | SSD için sadece sanitize/destroy; DoD wipe yasaklanır |
| Anonimleştirme zayıf, re-identification mümkün | Yıllık re-identification testi; quasi-identifier listesi |
| Pseudonymization, anonim sayıldı | Pseudonymization KVKK kapsamından çıkarmaz; tablo bunu net belirtir |
| İmha tutanağı yok, kanıt eksik | Otomatik tutanak üretimi (job çıktısından template'lenir) |
| Birden fazla kopyada veri var (replikasyon, cache) | İmha öncesi tam veri haritası; tüm kopyaların eşzamanlı imhası |
