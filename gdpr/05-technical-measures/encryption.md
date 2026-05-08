---
title:
  en: "Encryption - At Rest, In Transit, KMS, BYOK, Crypto-Shredding, PQC, Pseudonymisation"
  tr: "Şifreleme - Atılım, Taşıma, KMS, BYOK, Kripto-Yok Etme, PQC, Pseudonimizasyon"
section: "05-technical-measures"
document_type: "control_policy"
control_id: "TECH-CRY-01"
owner:
  primary: "CISO"
  secondary: "Cryptography Lead / Cloud Architecture"
review_cycle: "annual"
last_review: "2026-05-08"
next_review: "2027-05-08"
classification: "Internal"
language: ["en", "tr"]
references:
  - "GDPR Art. 4(5), 32(1)(a), 34(3)(a), Recital 26, Recital 83"
  - "ISO/IEC 27002:2022 control 8.24"
  - "ISO/IEC 18033 series, ISO/IEC 19790"
  - "NIST SP 800-57, FIPS 140-3, FIPS 197 (AES)"
  - "NIST FIPS 203 (ML-KEM), FIPS 204 (ML-DSA), FIPS 205 (SLH-DSA)"
  - "RFC 8446 (TLS 1.3), RFC 9106 (Argon2), RFC 8032 (EdDSA)"
  - "ENISA Recommendations on Cryptographic Algorithms and Key Sizes"
---

## English

# Encryption and Pseudonymisation

## 1. Purpose

GDPR Article 32(1)(a) names "the pseudonymisation and encryption of personal
data" as the first illustrative measure. Article 34(3)(a) makes encryption a
factor that may exempt a controller from notifying data subjects of a breach
where the encrypted data is "unintelligible to any person who is not
authorised to access it." This document specifies the controller's
cryptographic baseline.

Pseudonymisation is defined in Article 4(5): "the processing of personal data
in such a manner that the personal data can no longer be attributed to a
specific data subject without the use of additional information, provided that
such additional information is kept separately and is subject to technical and
organisational measures to ensure that the personal data are not attributed
to an identified or identifiable natural person."

## 2. Scope

This policy applies to:

- All personal data processed by the controller and its processors.
- All systems, services and storage media holding personal data.
- All communication channels carrying personal data, internal or external.
- All cryptographic key material across the lifecycle.

## 3. Data Classification Tiers

| Tier | Examples | Encryption Requirement |
|------|----------|------------------------|
| T1 - Public | Marketing assets | None |
| T2 - Internal | Internal documents | Encrypted at rest on managed storage |
| T3 - Confidential | Personal data (Art. 6 lawful basis) | Encrypted at rest and in transit, KMS-managed key |
| T4 - Restricted | Special-category data (Art. 9), criminal data (Art. 10), payment data, authentication secrets | Encrypted at rest and in transit, key separation, HSM-protected master key |
| T5 - Secret | Cryptographic master keys, root tokens | HSM, dual control, never extractable |

## 4. Encryption at Rest

### 4.1 Required Algorithms

- Symmetric: AES-256-GCM (preferred); AES-256-CTR with HMAC-SHA-256;
  ChaCha20-Poly1305 acceptable.
- Disk encryption: LUKS2/aes-xts-plain64 (Linux), BitLocker AES-XTS-256
  (Windows), FileVault 2 (macOS), full-volume encryption on mobile.
- Database transparent encryption: AES-256 with KMS-managed master keys.
- Object storage: server-side encryption with KMS-managed keys for T3-T5.
- Application-layer encryption: required for T4-T5 fields (column / field
  level) regardless of database TDE.

### 4.2 Backups and Snapshots

All backup media (`backup-recovery.md`) inherit the source classification and
are encrypted at the same or stronger level. Cross-region replication uses
server-side encryption tied to a region-local KMS key.

### 4.3 Removable Media and Endpoints

- Endpoint disk encryption mandatory and verified by EDR.
- USB / removable media: encrypted with hardware AES; non-encrypted media
  blocked by DLP (`dlp.md`).
- Mobile device storage encryption enforced by MDM with attestation.

## 5. Encryption in Transit

### 5.1 TLS

- TLS 1.3 only on new endpoints.
- TLS 1.2 with the following ciphers minimum: ECDHE-ECDSA-AES256-GCM-SHA384,
  ECDHE-RSA-AES256-GCM-SHA384, ECDHE-ECDSA-CHACHA20-POLY1305,
  ECDHE-RSA-CHACHA20-POLY1305.
- TLS 1.0, 1.1 and SSL 3.0: disabled at every layer.
- HSTS with `max-age >= 31536000; includeSubDomains; preload` for public
  domains.
- OCSP stapling enabled where supported; certificate transparency monitored.

### 5.2 Internal Service Communication

- mTLS between services in production.
- Mesh certificates rotated automatically (max 24 hours TTL).
- SPIFFE / SPIRE or equivalent for workload identity.

### 5.3 Email

- Opportunistic TLS by default; MTA-STS published with `enforce` mode.
- DMARC `p=reject`, SPF, DKIM aligned and signed by all sending services.
- Sensitive attachments (T4-T5) encrypted with PGP, S/MIME, or password-
  protected envelope using out-of-band shared secret.

### 5.4 VPN and Tunnels

- IPsec IKEv2 with AES-256-GCM and ECDH P-384 or X25519.
- WireGuard with current parameters.
- SSL VPN deprecated; replaced by ZTNA (`network-security.md`).

## 6. Key Management

### 6.1 Generation

- Keys generated within FIPS 140-3 validated HSMs or cloud HSM-backed KMS.
- Random source: NIST SP 800-90A approved DRBG.
- Asymmetric minimums: RSA-3072, ECDSA P-256, Ed25519, X25519, ECDH P-384.

### 6.2 Storage

- Master keys never leave the HSM in cleartext.
- Data encryption keys (DEKs) wrapped by KEKs in the HSM.
- Envelope encryption pattern enforced for cloud storage.
- Local key caches in services purged on rotation.

### 6.3 Rotation

| Key Class | Maximum Lifetime | Action on Rotation |
|-----------|------------------|--------------------|
| TLS server certificate | 90 days (ACME) | Re-issue, deploy, log |
| mTLS workload certificate | 24 hours | Auto via mesh |
| Database TDE master | 1 year | Re-wrap, no re-encrypt of data |
| Application data encryption key | 1 year | Re-wrap; lazy re-encryption on read |
| Backup encryption key | 1 year | New key for new backups |
| API signing key | 6 months | Dual-key window for clients |
| User password hash | n/a (rotation prohibited) | Re-hash on login if scheme upgraded |

### 6.4 Access Control to Keys

- Use of master keys requires AAL3 authentication.
- Separation of duties between key generation, key approval and key use.
- Logging of every cryptographic operation (key id, principal, action,
  timestamp, source).
- Quarterly review of key access entitlements.

### 6.5 BYOK and HYOK

- **BYOK** (Bring Your Own Key) - customer or controller imports key material
  into the cloud KMS; key wrapped by HSM; cloud provider operates the key but
  cannot recover it without the customer's import key.
- **HYOK** (Hold Your Own Key) - the controller retains the key in its own
  HSM; cloud provider proxies cryptographic calls. Considered for T5 data
  flowing to multi-tenant cloud services and where Schrems II / Article 46
  transfer impact assessments require it.
- Decision criteria documented per system in the encryption register; aligned
  with `07-international-transfers/`.

## 7. Crypto-Shredding (Right to Erasure)

Crypto-shredding satisfies Article 17 erasure for systems where physical
overwrite is impractical (object storage, immutable backups):

1. Each data subject (or each erasable scope) is associated with a unique
   data encryption key (DEK).
2. Erasure deletes (and rotates) the DEK in the KMS.
3. The encrypted data becomes mathematically inaccessible.
4. Erasure operation logged to the immutable audit store, with a verification
   record that the DEK no longer exists in any HSM partition or backup.

Crypto-shredding does not replace deletion at primary storage where deletion
is feasible. It is used where:

- Data lives on WORM media.
- Multiple legal holds prevent partial deletion.
- Legacy systems lack record-level delete.

The data subject is informed in the response that erasure has been completed
through cryptographic destruction of access (`09-data-subject-rights/`).

## 8. Post-Quantum Readiness

The cryptographic register is being audited for quantum vulnerability. Plan
of record:

- Maintain a complete cryptographic asset inventory (`technical-controls-checklist.md`).
- Track NIST FIPS 203 (ML-KEM, key encapsulation), FIPS 204 (ML-DSA, lattice
  signatures) and FIPS 205 (SLH-DSA, hash-based signatures).
- Deploy hybrid key exchange (X25519 + ML-KEM-768) on TLS 1.3 endpoints where
  the stack supports it - target Q4 2026 for customer-facing endpoints.
- Phase signature migration after FIPS 204 industry stabilisation - target
  2027-2028 for code-signing and document-signing pipelines.
- Apply "harvest now, decrypt later" risk treatment to long-lived secrets:
  data encrypted today that must remain confidential beyond 2030 receives
  hybrid encryption immediately.

## 9. Pseudonymisation (Art. 4(5))

### 9.1 Patterns

- **Tokenisation** - reversible mapping table held in a separate vault under
  stricter access; original value stored only in the vault.
- **Format-preserving encryption (FPE)** - FF1 / FF3-1; lookup integrity
  preserved in downstream systems.
- **Hashing with secret salt (HMAC)** - one-way for analytics; salt stored as
  a T5 secret; rotated only with full re-derivation plan.
- **K-record splitting** - identifying fields stored separately from
  behavioural fields; join key held under access control.

### 9.2 Effect Under GDPR

Pseudonymised data remains personal data while the additional information
exists. Pseudonymisation reduces risk and may strengthen lawful-basis tests
(Recital 28) but does not by itself satisfy anonymisation (Recital 26 - see
`masking-anonymization.md`).

### 9.3 Required Controls

- The mapping table or salt is held by a different team than the data
  consumers.
- Access to the mapping table is logged and reviewed quarterly.
- Combinations producing re-identification risk assessed before release.

## 10. Cryptographic Inventory

A central register lists every cryptographic dependency:

- System / service.
- Algorithm and parameter set.
- Key class (master, data, signing, transport).
- Key store (HSM partition, KMS key, certificate authority).
- Owner.
- Rotation schedule and last rotation.
- PQC migration status.

Owners attest to register accuracy quarterly. Internal audit samples the
register annually (`06-organizational-measures/internal-audit.md`).

## 11. KPIs

| Metric | Target |
|--------|--------|
| Personal-data systems with at-rest encryption | 100 % |
| External traffic on TLS 1.3 | >= 95 % |
| Internal traffic on mTLS | 100 % |
| Keys past rotation deadline | 0 |
| HSM-protected master keys | 100 % |
| PQC-ready public endpoints (hybrid) | >= 50 % by Q4 2026 |
| Crypto-shred verifications signed | 100 % of issued |

## 12. Mapping

| Requirement | GDPR | ISO 27002:2022 | NIST CSF 2.0 |
|-------------|------|----------------|--------------|
| Encryption | Art. 32(1)(a) | 8.24 | PR.DS-1 |
| Pseudonymisation | Art. 4(5), 32(1)(a) | 8.11 | PR.DS-2 |
| Key management | Art. 32(1)(a) | 8.24 | PR.DS-1 |
| Breach safe harbour | Art. 34(3)(a) | 5.27 | RS.AN |

---

## Türkçe

# Şifreleme ve Pseudonimizasyon

## 1. Amaç

GDPR Madde 32(1)(a) ilk örnek tedbir olarak "kişisel verilerin
pseudonimizasyonu ve şifrelenmesini" sayar. Madde 34(3)(a) şifrelemeyi,
şifrelenmiş verinin "erişim yetkisi olmayan herhangi bir kişi için anlaşılmaz"
olduğu durumlarda ihlali veri sahiplerine bildirme yükümlülüğünden kontrolörü
muaf tutabilecek bir faktör olarak tanımlar. Bu belge, kontrolörün kriptografik
temelini belirler.

Pseudonimizasyon Madde 4(5)'te tanımlanmıştır: "ek bilgi kullanılmadan
kişisel verilerin belirli bir veri sahibine atfedilemeyeceği şekilde işlenmesi;
söz konusu ek bilginin ayrı tutulması ve verilerin tanımlanmış veya
tanımlanabilir bir gerçek kişiye atfedilmemesini sağlayacak teknik ve
organizasyonel tedbirlere tabi tutulması koşuluyla."

## 2. Kapsam

Bu politika şunlara uygulanır:

- Kontrolör ve işleyicileri tarafından işlenen tüm kişisel veriler.
- Kişisel veri taşıyan tüm sistemler, hizmetler ve depolama ortamları.
- Kişisel veri taşıyan tüm iletişim kanalları, dahili veya harici.
- Yaşam döngüsü boyunca tüm kriptografik anahtar materyali.

## 3. Veri Sınıflandırma Katmanları

| Katman | Örnekler | Şifreleme Gereksinimi |
|--------|----------|------------------------|
| T1 - Genel | Pazarlama varlıkları | Yok |
| T2 - Dahili | Dahili belgeler | Yönetilen depolamada atılımda şifreli |
| T3 - Gizli | Kişisel veri (Md. 6 yasal dayanak) | Atılımda ve taşımada şifreli, KMS yönetimli anahtar |
| T4 - Kısıtlı | Özel nitelikli veri (Md. 9), cezai veri (Md. 10), ödeme verisi, kimlik doğrulama sırları | Atılımda ve taşımada şifreli, anahtar ayrımı, HSM korumalı master anahtar |
| T5 - Sır | Kriptografik master anahtarlar, root tokenlar | HSM, çift kontrol, asla çıkarılamaz |

## 4. Atılımda Şifreleme

### 4.1 Gerekli Algoritmalar

- Simetrik: AES-256-GCM (tercih edilen); HMAC-SHA-256 ile AES-256-CTR;
  ChaCha20-Poly1305 kabul edilebilir.
- Disk şifreleme: LUKS2/aes-xts-plain64 (Linux), BitLocker AES-XTS-256
  (Windows), FileVault 2 (macOS), mobilde tam birim şifreleme.
- Veritabanı şeffaf şifreleme: KMS yönetimli master anahtarlarla AES-256.
- Nesne depolama: T3-T5 için KMS yönetimli anahtarlarla sunucu tarafı
  şifreleme.
- Uygulama katmanı şifreleme: veritabanı TDE'sinden bağımsız olarak T4-T5
  alanları (sütun / alan düzeyi) için gereklidir.

### 4.2 Yedekler ve Anlık Görüntüler

Tüm yedek ortamlar (`backup-recovery.md`) kaynak sınıflandırmasını miras alır
ve aynı veya daha güçlü düzeyde şifrelenir. Bölgeler arası çoğaltma, bölgeye
yerel KMS anahtarına bağlı sunucu tarafı şifreleme kullanır.

### 4.3 Çıkarılabilir Ortam ve Uç Noktalar

- Uç nokta disk şifrelemesi zorunlu ve EDR tarafından doğrulanır.
- USB / çıkarılabilir ortam: donanım AES ile şifrelenmiş; şifresiz ortam DLP
  (`dlp.md`) tarafından engellenir.
- Mobil cihaz depolama şifrelemesi MDM tarafından attestation ile uygulanır.

## 5. Taşımada Şifreleme

### 5.1 TLS

- Yeni uç noktalarda yalnızca TLS 1.3.
- Aşağıdaki şifrelerle asgari TLS 1.2: ECDHE-ECDSA-AES256-GCM-SHA384,
  ECDHE-RSA-AES256-GCM-SHA384, ECDHE-ECDSA-CHACHA20-POLY1305,
  ECDHE-RSA-CHACHA20-POLY1305.
- TLS 1.0, 1.1 ve SSL 3.0: tüm katmanlarda devre dışı.
- Genel alan adları için `max-age >= 31536000; includeSubDomains; preload`
  HSTS.
- Desteklendiği yerde OCSP stapling açık; sertifika şeffaflığı izlenir.

### 5.2 Dahili Servis İletişimi

- Üretimde servisler arasında mTLS.
- Mesh sertifikaları otomatik döndürülür (azami 24 saat TTL).
- İş yükü kimliği için SPIFFE / SPIRE veya eşdeğeri.

### 5.3 E-posta

- Varsayılan olarak fırsatçı TLS; `enforce` modunda yayımlanan MTA-STS.
- DMARC `p=reject`, SPF, DKIM hizalanmış ve tüm gönderici servisler tarafından
  imzalanmış.
- Hassas ekler (T4-T5) PGP, S/MIME veya bant dışı paylaşılan sırla parola
  korumalı zarf ile şifrelenir.

### 5.4 VPN ve Tüneller

- AES-256-GCM ve ECDH P-384 veya X25519 ile IPsec IKEv2.
- Güncel parametrelerle WireGuard.
- SSL VPN kullanım dışı; yerini ZTNA aldı (`network-security.md`).

## 6. Anahtar Yönetimi

### 6.1 Üretim

- Anahtarlar FIPS 140-3 onaylı HSM'lerde veya bulut HSM destekli KMS'lerde
  üretilir.
- Rastgele kaynak: NIST SP 800-90A onaylı DRBG.
- Asimetrik asgariler: RSA-3072, ECDSA P-256, Ed25519, X25519, ECDH P-384.

### 6.2 Saklama

- Master anahtarlar HSM'den asla açık metin olarak çıkmaz.
- Veri şifreleme anahtarları (DEK) HSM'deki KEK'ler tarafından sarılır.
- Bulut depolama için zarf şifreleme deseni zorunlu.
- Servislerdeki yerel anahtar önbellekleri rotasyonda temizlenir.

### 6.3 Rotasyon

| Anahtar Sınıfı | Azami Ömür | Rotasyon Eylemi |
|----------------|------------|------------------|
| TLS sunucu sertifikası | 90 gün (ACME) | Yeniden ihraç, dağıt, logla |
| mTLS iş yükü sertifikası | 24 saat | Mesh üzerinden otomatik |
| Veritabanı TDE master | 1 yıl | Yeniden sarma, veri yeniden şifrelenmez |
| Uygulama veri şifreleme anahtarı | 1 yıl | Yeniden sarma; okumada lazy yeniden şifreleme |
| Yedek şifreleme anahtarı | 1 yıl | Yeni yedekler için yeni anahtar |
| API imza anahtarı | 6 ay | İstemciler için çift anahtar penceresi |
| Kullanıcı parola hash'i | yok (rotasyon yasak) | Şema yükseltildiyse girişte yeniden hash |

### 6.4 Anahtarlara Erişim Kontrolü

- Master anahtarların kullanımı AAL3 kimlik doğrulaması gerektirir.
- Anahtar üretimi, anahtar onayı ve anahtar kullanımı arasında görev ayrımı.
- Her kriptografik işlemin loglanması (anahtar kimliği, asıl, eylem, zaman
  damgası, kaynak).
- Anahtar erişim yetkilerinin üç aylık incelemesi.

### 6.5 BYOK ve HYOK

- **BYOK** (Kendi Anahtarını Getir) - müşteri veya kontrolör anahtar
  materyalini bulut KMS'ye içe aktarır; anahtar HSM tarafından sarılır; bulut
  sağlayıcı anahtarı işletir ancak müşterinin içe aktarma anahtarı olmadan
  geri alamaz.
- **HYOK** (Kendi Anahtarını Tut) - kontrolör anahtarı kendi HSM'sinde tutar;
  bulut sağlayıcı kriptografik çağrıları proxy'ler. Çok kiracılı bulut
  hizmetlerine akan T5 verisi için ve Schrems II / Madde 46 aktarım etki
  değerlendirmelerinin gerektirdiği yerde değerlendirilir.
- Karar kriterleri sistem başına şifreleme kayıt defterinde belgelenir;
  `07-international-transfers/` ile uyumludur.

## 7. Kripto-Yok Etme (Silme Hakkı)

Kripto-yok etme, fiziksel üzerine yazmanın pratik olmadığı sistemlerde
(nesne depolama, değiştirilemez yedekler) Madde 17 silme hakkını karşılar:

1. Her veri sahibi (veya her silinebilir kapsam) benzersiz bir veri şifreleme
   anahtarı (DEK) ile ilişkilendirilir.
2. Silme, KMS'deki DEK'i siler (ve döndürür).
3. Şifrelenmiş veri matematiksel olarak erişilemez hale gelir.
4. Silme işlemi değiştirilemez denetim deposuna loglanır; DEK'in herhangi bir
   HSM bölümünde veya yedeğinde artık var olmadığını belirten bir doğrulama
   kaydı ile.

Kripto-yok etme, silmenin uygulanabilir olduğu birincil depolamada silmenin
yerini almaz. Şu durumlarda kullanılır:

- Veri WORM ortamda yaşar.
- Çoklu yasal hold'lar kısmi silmeyi engeller.
- Eski sistemler kayıt düzeyinde silmeden yoksundur.

Veri sahibine yanıtta erişimin kriptografik imhasıyla silmenin tamamlandığı
bildirilir (`09-data-subject-rights/`).

## 8. Kuantum Sonrası Hazırlık

Kriptografik kayıt defteri kuantum zafiyeti için denetlenmektedir. Plan:

- Eksiksiz bir kriptografik varlık envanteri tut
  (`technical-controls-checklist.md`).
- NIST FIPS 203 (ML-KEM, anahtar kapsülleme), FIPS 204 (ML-DSA, kafes
  imzaları) ve FIPS 205 (SLH-DSA, hash tabanlı imzalar) izle.
- Yığının desteklediği yerde TLS 1.3 uç noktalarında hibrit anahtar
  değişimini (X25519 + ML-KEM-768) dağıt - müşteri tarafı uç noktalar için
  hedef 2026 Q4.
- FIPS 204 endüstri stabilizasyonundan sonra imza geçişini aşamalandır - kod
  imzalama ve belge imzalama hatları için hedef 2027-2028.
- Uzun ömürlü sırlara "şimdi topla, sonra çöz" risk işlemini uygula: bugün
  şifrelenmiş ve 2030'un ötesinde gizli kalması gereken veri hemen hibrit
  şifreleme alır.

## 9. Pseudonimizasyon (Md. 4(5))

### 9.1 Desenler

- **Tokenizasyon** - daha sıkı erişim altında ayrı bir kasada tutulan tersine
  çevrilebilir eşleme tablosu; orijinal değer yalnızca kasada saklanır.
- **Format koruyan şifreleme (FPE)** - FF1 / FF3-1; arama bütünlüğü alt akış
  sistemlerinde korunur.
- **Gizli tuzlu hash (HMAC)** - analitik için tek yönlü; tuz T5 sırrı olarak
  saklanır; yalnızca tam yeniden türetme planıyla döndürülür.
- **K-kayıt bölme** - tanımlayıcı alanlar davranışsal alanlardan ayrı saklanır;
  birleştirme anahtarı erişim kontrolü altında.

### 9.2 GDPR Kapsamında Etki

Pseudonimleştirilmiş veri, ek bilgi var olduğu sürece kişisel veridir.
Pseudonimizasyon riski azaltır ve yasal dayanak testlerini güçlendirebilir
(Resital 28) ancak tek başına anonimleştirmeyi karşılamaz (Resital 26 - bkz.
`masking-anonymization.md`).

### 9.3 Gerekli Kontroller

- Eşleme tablosu veya tuz, veri tüketicilerinden farklı bir ekip tarafından
  tutulur.
- Eşleme tablosuna erişim loglanır ve üç ayda bir incelenir.
- Yeniden tanımlama riski oluşturan kombinasyonlar yayım öncesinde
  değerlendirilir.

## 10. Kriptografik Envanter

Merkezi bir kayıt defteri her kriptografik bağımlılığı listeler:

- Sistem / hizmet.
- Algoritma ve parametre seti.
- Anahtar sınıfı (master, veri, imza, taşıma).
- Anahtar deposu (HSM bölümü, KMS anahtarı, sertifika otoritesi).
- Sahip.
- Rotasyon programı ve son rotasyon.
- PQC geçiş durumu.

Sahipler kayıt defteri doğruluğunu üç ayda bir beyan eder. İç denetim kayıt
defterini yıllık örnekler (`06-organizational-measures/internal-audit.md`).

## 11. KPI'lar

| Metrik | Hedef |
|--------|-------|
| Atılımda şifrelemeli kişisel-veri sistemleri | %100 |
| TLS 1.3'teki dış trafik | >= %95 |
| mTLS'teki dahili trafik | %100 |
| Rotasyon süresi geçmiş anahtarlar | 0 |
| HSM korumalı master anahtarlar | %100 |
| PQC hazır genel uç noktalar (hibrit) | 2026 Q4'e kadar >= %50 |
| İmzalı kripto-yok etme doğrulamaları | İhraç edilenlerin %100'ü |

## 12. Eşleme

| Gereklilik | GDPR | ISO 27002:2022 | NIST CSF 2.0 |
|------------|------|----------------|--------------|
| Şifreleme | Md. 32(1)(a) | 8.24 | PR.DS-1 |
| Pseudonimizasyon | Md. 4(5), 32(1)(a) | 8.11 | PR.DS-2 |
| Anahtar yönetimi | Md. 32(1)(a) | 8.24 | PR.DS-1 |
| İhlal güvenli liman | Md. 34(3)(a) | 5.27 | RS.AN |
