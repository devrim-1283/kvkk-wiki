---
Doküman / Document: Veri Maskeleme, Tokenization, Anonimleştirme ve Pseudonymization Standardı / Data Masking, Tokenization, Anonymization and Pseudonymization Standard
Bölüm / Section: 05-teknik-tedbirler
Sahip / Owner: Veri Mühendisliği Lideri / KVKK Sorumlusu (anonimlik değerlendirme) / Data Engineering Lead / KVKK Officer (anonymization assessment)
Onaylayan / Approved by: BT Direktörü + KVKK Komitesi / IT Director + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş (yeni veri kümesi, yeni teknik, re-identification kanıtı) / Annual + triggered (new dataset, new technique, re-identification evidence)
İlgili Mevzuat / Legal Reference: Law No. 6698 KVKK Art. 7 (Erasure/Destruction/Anonymization), Art. 28 (anonymized data); Regulation on Erasure, Destruction or Anonymization of Personal Data; Personal Data Security Guide — "Data Masking"
İlgili Standart / Standard: ISO/IEC 27001:2022 A.8.11 (Data Masking); ISO/IEC 20889 (Privacy Enhancing Data De-identification Terminology and Classification of Techniques); ISO/IEC 27559 (Privacy-enhancing data de-identification framework); NIST SP 800-188 (De-Identifying Government Datasets); NIST IR 8053; ENISA "Pseudonymisation Techniques and Best Practices"; GDPR Recital 26 (anonymity test framework)
---

## English

# Data Masking, Tokenization, Anonymization and Pseudonymization

## 1. Purpose

Standardizes technical methods that respond to operational needs but provide a **privacy guarantee** in contexts where **the actual value** of personal data is not disclosed (test, development, training, analytics, log, BI, demo). Forms the technical foundation of the KVKK Art. 7 anonymization requirement and the framework for the masking obligation in test/dev environments.

## 2. Conceptual Distinction — Critical

| Concept | KVKK Status | Reversible? | For Whom |
|--------|--------------|--------------------------|----------|
| **Masking** | Still personal data (display layer) | Yes (original retained) | For limited view |
| **Tokenization** | Still personal data (token + map = re-identifiable) | Yes via vault | Payment/card, internal systems |
| **Pseudonymization** | Still personal data (KVKK scope **continues**) | Yes via key | Analytics, secondary use |
| **Anonymization** | KVKK **out of scope** (Art. 28) | **No** — irreversible | Public sharing, statistics |

**Critical warning:** Per GDPR Recital 26 and the KVKK Regulation, for data to be considered "anonymous" it must not be **re-linkable to the data subject by any reasonable means**. Removing only direct identifiers (de-identification) is **not anonymization** — re-identification risk still exists. Therefore, true anonymization is a high bar and requires formal risk assessment.

## 3. Data Masking

### 3.1. Types

| Type | Definition | Use |
|-----|-------|----------|
| **Static Data Masking (SDM)** | Permanent, masked once during production cloning, real value not returned in subsequent accesses | Test/dev/training environment |
| **Dynamic Data Masking (DDM)** | Data unchanged in production DB; query response returns masked/clear based on user privilege | Internal support/QA, unauthorized view |
| **On-the-Fly Masking** | Stream-based masking during transfer from production to test environment | DataOps pipeline |

### 3.2. Masking Techniques

| Technique | Example | Notes |
|--------|-------|--------|
| Character substitution | `0532-***-**67` | Visual format preserved; sufficient for UI |
| Hash | `SHA-256(email + salt)` | Irreversible but linkable |
| Tokenization | `42342342` → `tok_x9k2…` | Reversible on vault side |
| Shuffle | Column values shuffled across rows | Statistics preserved, row mapping broken |
| Substitution | Real name → fake name list | Format preserved |
| Nulling / Redaction | "REDACTED" | High info loss; insufficient for some tests |
| Date variance | ±N days random | Order preserved |
| Numeric variance | ±X% | Sum/average approximately preserved |
| Encryption (AES) | Encrypted column | For masked display in DB |
| FPE (Format-Preserving Encryption — FF1) | Card number cipher again 16 digits | Type-compatible applications |

### 3.3. Mandatory Rules for Test/Dev Environment

- **Production data cannot be written raw to test/dev.** It is a direct KVKK finding upon breach.
- At cloning time, **the output of the masking pipeline** is written to the test environment.
- Masking rules are versioned **per field with technique** (in code / config repo).
- When a new field is added, classification → masking rule is mandated via **CI gate**.
- Every data field appearing as "test data" is periodically checked for **does it have actual production value?** scan (DLP discovery).

### 3.4. Referential Integrity

- If a field like Turkish ID number is used in multiple tables, masking must be **deterministic** (same input produces the same masked output every time) — for JOINs to work.
- Format-preserving deterministic encryption (FF1) preferred.

### 3.5. Visual Masking (UI)

- On a call center representative's screen, card number `**** **** **** 1234`, telephone `0532 *** ** 67`.
- Authorized user views in single use, justified, audited via "verify" button.

## 4. Tokenization

### 4.1. Working Principle

```
Production system ────► Tokenization Service ────► Token (e.g., tok_AbC123)
       ▲                    │
       │                    ▼
   Only token        Token Vault (PAN ↔ Token map, HSM-protected)
       │                    ▲
       └─── Vault call ─────┘ (authorized system, audit)
```

- Production systems work with **tokens**; real value only in tokenization vault.
- Vault HSM-protected, access very narrowly authorized (reduces PCI scope).
- Token type:
  - **Format-preserving:** original format (card number length).
  - **Format-non-preserving:** completely random.
- All systems without access to the vault may be out of PCI scope (DSS scope reduction).

### 4.2. FPE vs Tokenization

| Criterion | FPE | Tokenization |
|--------|-----|--------------|
| Reversal | With key | With vault map |
| Format | Preserved | Can be preserved or not |
| Key distribution | Wider | None (vault single point) |
| Dependency | Key | Vault HA |
| Typical use | Encryption within DB + format requirement | Payment, scope reduction |

## 5. Pseudonymization

### 5.1. Definition

Direct identifier (name, ID, email) is replaced with a **pseudonym** (e.g., random ID or hash); mapping is kept in a separate, protected location. **Data is still within KVKK scope**, since it can be re-identified with the mapping.

### 5.2. Methods

- **Counter-based:** sequential database ID. Risk: ordering leaks information (record count, sequence).
- **Random ID:** UUID v4 / v7. Preferred.
- **Cryptographic hash:** SHA-256(value + salt). Salt leak = pseudonymization leak.
- **Keyed hash (HMAC-SHA256):** with a key; more secure.
- **Encryption:** With AES-GCM. Those without key access cannot re-identify.

### 5.3. Use Cases

- Analytical data warehouse / lakehouse: mapping access strictly limited, with KVKK Officer approval.
- Research, reporting.
- Cross-dataset joining (with the same pseudonym).
- Especially preferred in analytics working with special-category data.

### 5.4. Strengthening

- Mapping in HSM/vault.
- Pseudonymized value in log, never the real value.
- Pseudonym annual or per-record rotation (rotating pseudonym) possible.
- If quasi-identifiers (age, postal code, gender) are not additionally generalized / suppressed, pseudonymization alone may be insufficient (re-identification risk).

## 6. Anonymization

### 6.1. Anonymity Threshold

The KVKK Regulation states: "Anonymization; making personal data such that it cannot in any way be associated with an identified or identifiable natural person, even if matched with other data." **Practical test:** "An attacker cannot re-identify with reasonable resources, in reasonable time and cost."

### 6.2. Classical Techniques

#### 6.2.1. Suppression
Removing certain fields/records. Low-frequency records deleted.

#### 6.2.2. Generalization
Converting a specific value to a coarser category:
- Age 34 → "30-39"
- Postal code 06800 → "068**"
- Date 12.05.2026 → "2026-Q2"

#### 6.2.3. Aggregation
Group summaries instead of individual records.

#### 6.2.4. Perturbation / Noise Injection
Adding small random noise to numeric values.

#### 6.2.5. Microaggregation
Replacing each of a group of similar k records with the group average.

### 6.3. k-Anonymity

Each record must look the same as at least **k-1** other records on the quasi-identifier set. k=5 is a common threshold; k=10–20 recommended for sensitive data.

**Limitation:** If the **sensitive attribute** within the group lacks diversity (e.g., everyone has the same disease), k-anonymity is not enough.

### 6.4. l-Diversity

In each quasi-identifier class, the sensitive attribute must take at least **l** different values. Requires meaningful diversity.

### 6.5. t-Closeness

The intra-class distribution of the sensitive attribute must be close (≤ t Earth Mover's Distance) to the overall population distribution.

### 6.6. Differential Privacy

Modern gold standard. The impact of a person's presence/absence in a record on the output is mathematically bounded (ε — privacy budget). Used by Apple, Google, US Census.

- **Global noise** or **local noise** (LDP).
- Usable in aggregation queries and ML training.
- The smaller ε → higher privacy, lower utility.
- ε budget tracked; queries on a single dataset accumulate.

### 6.7. Synthetic Data

Generating new, synthetic records from a generative model (GAN, VAE, copula) that learns the **statistical properties** of the real dataset. If done correctly, it is anonymous, but:

- High-capacity models risk memorization (memorizing original records).
- For synthetic data **to be considered anonymous**, a privacy guarantee (e.g., DP-trained generator) is mandatory.

## 7. Re-identification Risk Assessment

A mandatory report **before** anonymized data is published / shared:

### 7.1. Risk Models (ISO/IEC 20889 / ISO/IEC 27559)

- **Prosecutor:** the attacker's pursuit of a specific known individual.
- **Journalist:** aims to identify a random individual.
- **Marketer:** large scale, what percentage are re-identified?

### 7.2. Questions to Ask

- What quasi-identifiers exist?
- What external data may the attacker have? (Voter list, social media, leaked DB, commercial marketing list.)
- What is the smallest equivalence class size? (k)
- How are sensitive attributes distributed? (l, t)
- Is the ML/aggregation output resistant to membership inference attack?
- Publication scale? (closed analytics, joint partner, public?)

### 7.3. Table: Acceptable Risk Threshold

| Publication Mode | Target k | DP ε (if any) | Approval |
|------------|---------|----------------|------|
| Internal analytics (strict access) | 5 | – | Data Owner |
| Controlled partner | 10 | ≤ 4 | KVKK Officer |
| Public | 20+ | ≤ 1 | KVKK Committee + external expert opinion |

### 7.4. Documentation

- Original dataset name before anonymization, owner, fields.
- Applied techniques and parameters.
- Risk assessment result, approval chain.
- Monitoring plan after publication (re-identification suspicion feedback).
- Retention: version considered anonymous out of KVKK Art. 28 scope; mapping/original record subject to Destruction Regulation.

## 8. Practical Scenarios

### 8.1. Scenario: Developer Test Dataset

- Production DB → DataOps masking pipeline → Test DB.
- Masking rules: Turkish ID FPE (deterministic), email substitution, date ±30 days, name/surname from fake-name list, sensitive data (health) fully synthetic.
- CI gate: "fail if no classification + masking rule for any new field".

### 8.2. Scenario: BI Analytics

- Pseudonymized customer ID + generalized age, postal code (5-digit), aggregate metrics.
- Mapping (pseudonym → real customer) in separate vault, accessible only with KVKK Officer approval.
- BI dashboards never display direct identifiers.

### 8.3. Scenario: ML Training Data

- If the model memorizes, can produce evidence of re-identification.
- Differential Privacy training (DP-SGD), federated learning, secure aggregation.
- Training data with minimum required fields.
- Annual model "memorization audit" (membership inference test).

### 8.4. Scenario: Academic / Open Data Publication

- Strictest controls. External expert opinion, k≥20, DP, high suppression.
- Post-publication re-identification incident monitoring.

## 9. Logging and Audit

- Masking jobs (input source, rule set version, output, record count).
- Vault access (tokenization, pseudonymization mapping).
- Anonymization process (before/after summary, parameters, risk report).
- Scans of data written to test environment (critical alarm if real PII found).

## 10. Checklist

- [ ] Are test/dev/training environments free of raw production data (verified with scanning)?
- [ ] Is the masking pipeline in code/config repo, versioned?
- [ ] When a new field is added, is classification + masking rule mandated via CI gate?
- [ ] Does deterministic masking preserve referential integrity?
- [ ] Is default UI display masked, with "verify" click audited?
- [ ] Is the tokenization vault HSM-protected, with strict access?
- [ ] Is pseudonymization mapping separate, protected, audited?
- [ ] Is it documented that pseudonymized data is also within KVKK scope?
- [ ] Is formal re-identification risk assessment performed before anonymous publication?
- [ ] Are k-anon, l-diversity, t-closeness, or DP parameters recorded?
- [ ] Is the DP ε budget tracked?
- [ ] Is synthetic data generated with privacy guarantees (memorization audited)?
- [ ] Is the anonymization approval chain (KVKK Officer / Committee) documented?
- [ ] Is DLP performing PII scanning in the test environment?
- [ ] Are anonymous version + original version + mapping lifecycles managed separately?

## 11. Common Mistakes

- "MD5 hash" for pseudonymization → broken with dictionary + brute force (especially for limited fields like Turkish ID).
- "I removed the name, it became anonymous" → re-identified by quasi-identifiers.
- "Let's pull a few records from production for fast debug" in test environment → KVKK violation.
- Masking only at the UI (real value in DB / logs) → leaks via log scraping.
- Standard access on tokenization vault → no scope reduction gain.
- Failing to evaluate that an additional information source could re-identify after the anonymous version is published.

## 12. Continuous Improvement

- Once a year, re-identification attempt with **internal red team / external expert** (on published anonymous datasets).
- Tracking new technical literature (especially privacy-preserving ML).
- When a re-identification incident/suspicion arises, immediately investigate + withdraw the publication.

---

## Türkçe

# Veri Maskeleme, Tokenization, Anonimleştirme ve Pseudonymization

## 1. Amaç

Kişisel verinin **gerçek değerinin** ifşa edilmediği bağlamlarda (test, geliştirme, eğitim, analitik, log, BI, demo) operasyonel ihtiyaca cevap veren ama **gizlilik garantisi** sunan teknik yöntemleri standardize eder. KVKK m.7 anonimleştirme zorunluluğunun teknik temelini ve test/dev ortamı için maskeleme zorunluluğunun çerçevesini oluşturur.

## 2. Kavramsal Ayrım — Kritik

| Kavram | KVKK Statüsü | Geri Döndürülebilir mi? | Kim için |
|--------|--------------|--------------------------|----------|
| **Maskeleme (Masking)** | Hâlâ kişisel veri (görüntüleme katmanı) | Evet (orijinal saklı) | Sınırlı görüş için |
| **Tokenization** | Hâlâ kişisel veri (token + map = re-identifiable) | Vault üzerinde evet | Ödeme/kart, dahili sistemler |
| **Pseudonymization (Müstear)** | Hâlâ kişisel veri (KVKK kapsamı **devam eder**) | Anahtarla evet | Analitik, yan kullanım |
| **Anonymization (Anonim)** | KVKK **kapsam dışı** (m.28) | **Hayır** — geri çevrilemez | Kamuya açık paylaşım, istatistik |

**Kritik uyarı:** GDPR Recital 26 ve KVKK Yönetmeliği'ne göre veri "anonim" sayılabilmesi için **makul bütün araçlarla bile** ilgili kişiye geri bağlanamaz olmalıdır. Sadece doğrudan tanımlayıcıyı kaldırmak (de-identification) **anonimleştirme değildir** — re-identification riski hâlâ vardır. Bu nedenle gerçek anonimleştirme yüksek bir bardır ve formel risk değerlendirmesi ister.

## 3. Veri Maskeleme

### 3.1. Türler

| Tür | Tanım | Kullanım |
|-----|-------|----------|
| **Static Data Masking (SDM)** | Kalıcı, üretim klonu sırasında bir kez maskelenir, sonraki erişimlerde gerçek değer dönmez | Test/dev/eğitim ortamı |
| **Dynamic Data Masking (DDM)** | Üretim DB'sinde veri değişmez; sorgu cevabı kullanıcının yetkisine göre maskeli/açık döner | İç destek/QA, yetkisiz görüş |
| **On-the-Fly Masking** | Üretimden test ortamına aktarım sırasında stream halinde maskeleme | DataOps boru hattı |

### 3.2. Maskeleme Teknikleri

| Teknik | Örnek | Notlar |
|--------|-------|--------|
| Karakter ikamesi | `0532-***-**67` | Görsel format korunur; UI'da yeterli |
| Hash | `SHA-256(email + tuz)` | Geri çevrilemez ama bağlanabilir |
| Tokenization | `42342342` → `tok_x9k2…` | Vault tarafında geri çevrilebilir |
| Shuffle | Kolon değerleri kayıtlar arasında karıştırılır | İstatistik korunur, satır eşlemesi bozulur |
| Substitution | Gerçek isim → sahte isim listesi | Format korunur |
| Nulling / Redaction | "REDACTED" | Bilgi kaybı yüksek; bazı testler için yetersiz |
| Date variance | ±N gün rastgele | Sıralama korunur |
| Numeric variance | ±%X | Toplama-ortalama yaklaşık korunur |
| Encryption (AES) | Şifreli sütun | DB içinde maskeli görüntüleme için |
| FPE (Format-Preserving Encryption — FF1) | Kart no şifresi yine 16 hane | Tip-uyumlu uygulamalar |

### 3.3. Test/Dev Ortamı için Zorunlu Kurallar

- **Üretim verisi test/dev'e ham yazılamaz.** İhlal durumunda doğrudan KVKK bulgusudur.
- Klonlama anında, **maskeleme boru hattının çıktısı** test ortamına yazılır.
- Maskeleme kuralları **alan listesi + alan başına teknik** olarak versiyonludur (kod / config repo'da).
- Yeni alan eklendiğinde, klasifikasyon → maskeleme kuralı **CI gate** ile zorunlu kılınır.
- "Test data" olarak gözüken her veri alanı periyodik olarak **gerçek üretim değeri var mı?** taraması ile kontrol edilir (DLP discovery).

### 3.4. Referansiyel Bütünlük

- TC kimlik gibi alan birden fazla tabloda kullanılıyorsa, maskeleme **deterministic** olmalıdır (aynı girdi her seferinde aynı maskeli çıktıyı üretir) — JOIN'lerin çalışması için.
- Format-preserving deterministic encryption (FF1) tercih edilir.

### 3.5. Görsel Maskeleme (UI)

- Çağrı merkezi temsilcisi ekranında kart numarası `**** **** **** 1234`, telefon `0532 *** ** 67`.
- Yetkili kullanıcı "doğrula" butonuyla tek seferde, gerekçeli, audit'li olarak görür.

## 4. Tokenization

### 4.1. Çalışma Prensibi

```
Üretim sistem ────► Tokenization Service ────► Token (ör. tok_AbC123)
       ▲                    │
       │                    ▼
   Sadece token       Token Vault (PAN ↔ Token map, HSM-protected)
       │                    ▲
       └─── Vault çağrı ────┘ (yetkili sistem, audit)
```

- Üretim sistemleri **token** ile çalışır; gerçek değer yalnızca tokenization vault'unda.
- Vault HSM'de korunur, erişim çok dar yetkili (PCI scope'u küçültür).
- Token tipi:
  - **Format-preserving:** orijinal formata sahip (kart numarası uzunluğu).
  - **Format-non-preserving:** tamamen rastgele.
- Vault'a erişimi olmayan tüm sistemler PCI scope dışında kalabilir (DSS scope reduction).

### 4.2. FPE vs Tokenization

| Kriter | FPE | Tokenization |
|--------|-----|--------------|
| Reversal | Anahtarla | Vault map ile |
| Format | Korunur | Korunabilir / korunmayabilir |
| Anahtar dağılımı | Daha geniş | Yok (vault tek nokta) |
| Bağımlılık | Anahtar | Vault HA |
| Tipik kullanım | DB içi şifreleme + format gereği | Ödeme, scope reduction |

## 5. Pseudonymization (Müstear)

### 5.1. Tanım

Doğrudan tanımlayıcı (isim, TC, e-posta) bir **müstear** (örn. rastgele ID veya hash) ile değiştirilir; mapping ayrı, korumalı bir yerde tutulur. **Veri hâlâ KVKK kapsamındadır**, çünkü mapping ile yeniden tanımlanabilir.

### 5.2. Yöntemler

- **Counter-based:** veritabanı sıralı ID. Risk: sıralama bilgi sızdırır (kayıt sayısı, sıra).
- **Random ID:** UUID v4 / v7. Tercihli.
- **Cryptographic hash:** SHA-256(value + tuz). Tuzun sızması = pseudonymization sızması.
- **Keyed hash (HMAC-SHA256):** anahtarla; daha güvenli.
- **Encryption:** AES-GCM ile. Anahtar erişimi olmayan, yeniden tanımlayamaz.

### 5.3. Kullanım Alanları

- Analitik veri ambarı / lakehouse: mapping erişimi sıkı sınırlandırılmış, KVKK Sorumlusu onayıyla.
- Araştırma, raporlama.
- Çapraz veri kümesi birleştirme (aynı pseudonym ile).
- Özellikle özel nitelikli veriyle çalışılan analitikte tercih edilir.

### 5.4. Kuvvetlendirme

- Mapping HSM/vault'ta.
- Log'da pseudonymized değer, gerçek değer asla.
- Pseudonym yıllık veya kayıt-bazlı dönüştürme (rotating pseudonym) mümkün.
- Quasi-identifier (yaş, posta kodu, cinsiyet) ek olarak generalize / suppress edilmediyse, pseudonymization tek başına yetersiz olabilir (re-identification risk).

## 6. Anonymization (Anonim Hale Getirme)

### 6.1. Anonim Sayılma Eşiği

KVKK Yönetmeliği "Anonim hale getirme; kişisel verinin başka verilerle eşleştirilse dahi hiçbir surette belirli veya belirlenebilir bir gerçek kişiyle ilişkilendirilemeyecek hâle getirilmesi" der. **Pratik test:** "Saldırgan, makul kaynaklarla, makul zaman ve maliyetle yeniden tanımlama yapamasın."

### 6.2. Klasik Teknikler

#### 6.2.1. Suppression (Bastırma)
Belirli alanları/kayıtları kaldırma. Düşük frekanslı kayıtlar silinir.

#### 6.2.2. Generalization (Genelleme)
Belirli değeri kaba kategoriye çevirme:
- Yaş 34 → "30-39"
- Posta kodu 06800 → "068**"
- Tarih 12.05.2026 → "2026-Q2"

#### 6.2.3. Aggregation
Bireysel kayıt yerine grup özetleri.

#### 6.2.4. Perturbation / Noise Injection
Sayısal değerlere küçük rastgele gürültü ekleme.

#### 6.2.5. Microaggregation
Benzer k kayıt grubunun her birini grup ortalamasıyla değiştirme.

### 6.3. k-Anonymity

Her kayıt en az **k-1** başka kayıtla quasi-identifier setinde aynı görünmeli. k=5 yaygın eşik; hassas verilerde k=10–20 önerilir.

**Sınırlama:** Eğer grup içindeki **hassas öznitelik** çeşitlilik göstermiyorsa (örn. herkes aynı hastalığa sahip), k-anonim yetmez.

### 6.4. l-Diversity

Her quasi-identifier sınıfında, hassas öznitelik en az **l** farklı değer almalı. Anlamlı çeşitlilik gerektirir.

### 6.5. t-Closeness

Hassas özniteliğin sınıf-içi dağılımı, genel popülasyon dağılımına yakın (≤ t Earth Mover's Distance) olmalı.

### 6.6. Differential Privacy

Modern altın standart. Bir kişinin kayıtta bulunup bulunmamasının çıktıya etkisi matematiksel olarak sınırlandırılır (ε — privacy budget). Apple, Google, ABD Census kullanır.

- **Globalde gürültü** veya **lokalde gürültü** (LDP).
- Aggregation queries ve ML eğitiminde kullanılabilir.
- ε ne kadar küçük → gizlilik o kadar yüksek, fayda o kadar düşük.
- ε bütçesi takip edilir; tek veri kümesinde sorgular birikim yapar.

### 6.7. Synthetic Data

Gerçek veri kümesinin **istatistiksel özelliklerini** öğrenen üretim modelinden (GAN, VAE, kopula) yeni, sentetik kayıtlar üretmek. Doğru yapılırsa anonim, ama:

- Model kapasitesi yüksekse memorization (orijinal kayıtların ezberlenmesi) riski.
- Synthetic data anonim **kabul edilebilmesi için** privacy guarantee (örn. DP-trained generator) zorunlu.

## 7. Re-identification Risk Değerlendirmesi

Anonimleştirilmiş veri yayınlanmadan / paylaşılmadan **önce** zorunlu rapor:

### 7.1. Risk Modelleri (ISO/IEC 20889 / ISO/IEC 27559)

- **Prosecutor:** saldırganın bildiği belirli bir bireyi arayışı.
- **Journalist:** rastgele bir bireyi tanımlamayı amaçlar.
- **Marketer:** geniş ölçekli, yüzde olarak ne kadar yeniden tanımlanır?

### 7.2. Sorulacak Sorular

- Hangi quasi-identifier'lar var?
- Saldırganın elinde dışsal hangi veriler olabilir? (Seçmen listesi, sosyal medya, sızdırılmış DB, ticari pazarlama listesi.)
- En küçük equivalence class size nedir? (k)
- Hassas öznitelikler nasıl dağılıyor? (l, t)
- ML/aggregation çıkışı membership inference saldırısına dayanıyor mu?
- Yayın ölçeği? (kapalı analitik, ortak çalışan, kamuya açık?)

### 7.3. Tablo: Kabul Edilebilir Risk Eşiği

| Yayın Modu | Hedef k | DP ε (varsa) | Onay |
|------------|---------|----------------|------|
| Dahili analitik (sıkı erişim) | 5 | – | Veri Sahibi |
| Kontrollü ortak | 10 | ≤ 4 | KVKK Sorumlusu |
| Kamuya açık | 20+ | ≤ 1 | KVKK Komitesi + dış uzman görüşü |

### 7.4. Belgeleme

- Anonimleştirme öncesi orijinal veri kümesi adı, sahibi, alanlar.
- Uygulanan teknikler ve parametreler.
- Risk değerlendirme sonucu, onay zinciri.
- Yayın sonrası izleme planı (re-identification şüphesi geri besleme).
- Saklama: anonim kabul edilen sürüm KVKK m.28 dışı; mapping/orijinal kayıt İmha Yönetmeliği uyumlu.

## 8. Pratik Senaryolar

### 8.1. Senaryo: Geliştirici Test Veri Kümesi

- Production DB → DataOps maskeleme pipeline → Test DB.
- Maskeleme kuralları: TC kimlik FPE (deterministic), e-posta substitution, tarih ±30 gün, ad/soyad fake-name listesinden, hassas veri (sağlık) tamamen sentetik.
- CI gate: "her yeni alan classification + masking rule yoksa fail".

### 8.2. Senaryo: BI Analitik

- Pseudonymized müşteri ID + generalized yaş, posta kodu (5'lik dilim), agregate metrikler.
- Mapping (pseudonym → gerçek müşteri) ayrı vault'ta, sadece KVKK Sorumlusu onayıyla erişim.
- BI dashboard'larda asla doğrudan tanımlayıcı yer almaz.

### 8.3. Senaryo: ML Eğitim Verisi

- Eğer model ezberlerse re-identification kanıtı oluşturabilir.
- Differential Privacy ile eğitim (DP-SGD), federated learning, secure aggregation.
- Eğitim verisi minimum gerekli alanlarla.
- Modelin "memorization audit"i (membership inference test) yıllık.

### 8.4. Senaryo: Akademik / Açık Veri Yayını

- En sıkı kontroller. Dış uzman görüşü, k≥20, DP, suppression yüksek.
- Yayım sonrası re-identification olayı izleme.

## 9. Loglama ve Audit

- Maskeleme job'ları (girdi kaynağı, kural seti versiyonu, çıktı, kayıt sayısı).
- Vault erişim (tokenization, pseudonymization mapping).
- Anonimleştirme süreci (öncesi/sonrası özet, parametreler, risk raporu).
- Test ortamına yazılan veri taramaları (gerçek PII bulunursa kritik alarm).

## 10. Kontrol Listesi

- [ ] Test/dev/eğitim ortamlarında ham üretim verisi yok mu (tarama doğrulamalı)?
- [ ] Maskeleme pipeline kod/config repo'da, versiyonlu mu?
- [ ] Yeni alan eklendiğinde classification + masking rule CI gate ile zorunlu mu?
- [ ] Deterministic masking referansiyel bütünlüğü koruyor mu?
- [ ] UI üzerinde varsayılan görüntü maskeli, "doğrula"ya tıklama audit'li mi?
- [ ] Tokenization vault HSM korumalı, erişim sıkı mı?
- [ ] Pseudonymization mapping ayrı, korumalı, audit'li mi?
- [ ] Pseudonymized verinin de KVKK kapsamında olduğu belgeli mi?
- [ ] Anonim yayın öncesi formel re-identification risk değerlendirmesi yapılıyor mu?
- [ ] k-anon, l-diversity, t-closeness veya DP parametreleri kayıtlı mı?
- [ ] DP ε bütçesi takip ediliyor mu?
- [ ] Synthetic data privacy garantisiyle üretiliyor mu (memorization auditli)?
- [ ] Anonimleştirme onay zinciri (KVKK Sorumlusu / Komite) belgeli mi?
- [ ] DLP ile test ortamında PII tarama yapılıyor mu?
- [ ] Anonim sürüm + orijinal sürüm + mapping yaşam döngüleri ayrı yönetiliyor mu?

## 11. Yaygın Hatalar

- "MD5 hash" ile pseudonymization → sözlük + brute force ile geri çözülür (özellikle TC kimlik gibi sınırlı alan).
- "İsmi sildim, anonim oldu" → quasi-identifier'larla tekrar tanımlanır.
- Test ortamında "production'dan birkaç kayıt çekelim, hızlı debug" → KVKK ihlali.
- Maskelemenin yalnızca UI'da yapılması (DB / loglarda gerçek değer var) → log scraping ile sızar.
- Tokenization vault'unda standart erişim → scope reduction kazancı yok.
- Anonim sürüm yayınlandıktan sonra ek bir bilgi kaynağıyla re-identification olabileceğini değerlendirmemek.

## 12. Sürekli İyileştirme

- Yıllık bir kez **iç red team / dış uzman** ile re-identification denemesi (anonim yayınlanmış veri kümeleri üzerinde).
- Yeni teknik literatür (özellikle privacy-preserving ML) takibi.
- Re-identification olay/şüphesi olduğunda derhal soruşturma + yayının geri çekilmesi.
