---
Doküman / Document: Şifreleme Politikası ve Anahtar Yönetimi Standardı / Encryption Policy and Key Management Standard
Bölüm / Section: 05-teknik-tedbirler
Sahip / Owner: Kripto Mühendisliği / CISO / Crypto Engineering / CISO
Onaylayan / Approved by: BT Direktörü + KVKK Komitesi / IT Director + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş (algoritma deprecation, yeni standart, ihlal) / Annual + triggered (algorithm deprecation, new standard, breach)
İlgili Mevzuat / Legal Reference: Law No. 6698 KVKK Art. 12; Personal Data Security Guide — "Encryption"; PCI DSS v4.0 for payment cards; BDDK regulations for banking (where applicable)
İlgili Standart / Standard: ISO/IEC 27001:2022 A.8.24 (Use of Cryptography); NIST SP 800-57 (Key Management); NIST SP 800-175B; NIST FIPS 140-3 (Cryptographic Modules); NIST FIPS 197 (AES); NIST FIPS 186-5 (Digital Signatures); NIST FIPS 203/204/205 (Post-Quantum Cryptography — ML-KEM, ML-DSA, SLH-DSA); IETF RFC 8446 (TLS 1.3); IETF RFC 7525 (TLS Recommendations BCP); Mozilla TLS Configuration; eIDAS (internationally recognized signatures)
---

## English

# Encryption

## 1. Purpose

Standardizes the protection of personal data with cryptographic controls **at-rest**, **in-transit**, and where applicable **in-use**. The operational implementation of the control highlighted under "Encryption" in the KVKK Personal Data Security Guide.

## 2. Encryption Requirement Based on Data Classification

| Class | Definition | At-Rest | In-Transit | In-Use |
|-------|-------|---------|------------|--------|
| Top Secret | Special-category (KVKK Art. 6), cardholder data (PAN), authentication secrets | **Mandatory** (field-level + DB/Disk) | **Mandatory** (TLS 1.3, internal mTLS) | **Mandatory** if possible (CSE, confidential computing) |
| Confidential | General personal data, trade secrets | **Mandatory** (DB/Disk) | **Mandatory** (TLS 1.2+) | Recommended |
| Internal | Operational data without personal data | Recommended | **Mandatory** (TLS 1.2+) | Not required |
| Public | Web content, etc. | Integrity (signature/hash) | TLS recommended | – |

Classification ties to the Data Classification Policy under [00-yonetisim](../00-yonetisim/).

## 3. Approved Algorithms (as of 2026)

### 3.1. Symmetric

| Algorithm | Mode | Key | Use | Status |
|-----------|-----|---------|----------|-------|
| AES | GCM | 256 bit | Preferred (AEAD) | Approved |
| AES | GCM | 128 bit | General | Approved |
| AES | CBC + HMAC-SHA256 | 256 bit | Legacy compatibility | Approved (GCM preferred for new design) |
| ChaCha20-Poly1305 | – | 256 bit | Mobile/IoT, AEAD | Approved |
| 3DES | – | – | – | **Forbidden** |
| RC4 | – | – | – | **Forbidden** |
| DES | – | – | – | **Forbidden** |
| AES | ECB | – | – | **Forbidden** (deterministic, pattern leakage) |

### 3.2. Asymmetric

| Algorithm | Size | Use | Status |
|-----------|-------|----------|-------|
| RSA | ≥ 3072 bit | Signature, key wrapping | Approved (ECC preferred for new systems) |
| ECDSA | P-256 / P-384 | Signature | Approved |
| Ed25519 | – | Signature | Approved (preferred) |
| ECDH | P-256 / P-384 / X25519 | Key exchange | Approved |
| RSA | < 2048 bit | – | **Forbidden** |
| DSA | – | – | **Forbidden** |

### 3.3. Hash and KDF

| Algorithm | Use | Status |
|-----------|----------|-------|
| SHA-256 / SHA-384 / SHA-512 | General hash, HMAC | Approved |
| SHA-3 family | New systems | Approved |
| BLAKE2/3 | Fast hash (internal) | Approved |
| Argon2id | Password hashing | Approved (preferred) |
| bcrypt (cost ≥ 12) | Password hashing | Approved |
| scrypt | Password hashing | Approved |
| PBKDF2-HMAC-SHA256 (≥ 600k iter) | Legacy system migration | Temporarily approved |
| HKDF | Key derivation | Approved |
| MD5 | – | **Forbidden** |
| SHA-1 | – | **Forbidden** (including HMAC in new design) |

### 3.4. Post-Quantum Cryptography (PQC)

NIST standardized FIPS 203 (ML-KEM, formerly Kyber), FIPS 204 (ML-DSA, formerly Dilithium), and FIPS 205 (SLH-DSA, formerly SPHINCS+) in 2024. Our PQC roadmap:

- **2026:** Hybrid (X25519 + ML-KEM-768) key exchange pilot — TLS 1.3, VPN.
- **2027:** ML-DSA pilot for signing in critical PKI hierarchy.
- **2028+:** New certificate generation fully hybrid/PQC.
- **Crypto agility:** No application may hard-code algorithm names/parameters in code (config + abstraction layer).

## 4. At-Rest Encryption

### 4.1. Disk-Level (FDE)

- All laptops and mobile devices mandatorily encrypted with BitLocker (Windows) / FileVault (macOS) / LUKS (Linux), enforced via MDM.
- Server/virtual machine disks: cloud provider's default disk encryption + customer-managed key (CMK/BYOK) additionally.
- USB/storage media: hardware encrypted (FIPS 140-3 Level 2+) or software encryption mandatory before transfer.

### 4.2. Database (TDE — Transparent Data Encryption)

- SQL Server / Oracle / PostgreSQL (pgcrypto / TDE add-on) / MySQL InnoDB Tablespace Encryption — all data and log files at the DB level AES-256.
- Key kept in HSM / KMS, DB only knows the key reference.
- TDE alone is not enough; **field-level encryption** is additionally applied to critical columns containing personal data.

### 4.3. Field-Level (Column-Level)

Fields like card number, Turkish ID number, IBAN, health data, biometric template are also encrypted at the **application or DB level**.

- Application-side encryption (CSE — Client-Side Encryption): even the DB administrator cannot see plaintext.
- The authority to decrypt is restricted within the application by RBAC + audit.
- If required for searching, applied with **deterministic encryption** (AES-SIV) or **searchable encryption** (with re-identification risks evaluated).

### 4.4. Object Storage (S3 / Blob / GCS)

- SSE-KMS / Customer-Managed Key mandatory.
- BYOK / HYOK optional (high sensitivity).
- Bucket policy rejects unencrypted upload (`s3:x-amz-server-side-encryption` enforcement).
- Versioning + Object Lock (WORM) active for critical data.

### 4.5. Backup Encryption

- Backup files **always** generated encrypted.
- Backup key kept in a **separate** key chain from the production system (ransomware criterion).
- See [yedekleme.md](yedekleme.md).

### 4.6. Email and File Sharing

- Attachments containing personal data in email body are **labeled** (Sensitivity Label) and **automatically encrypted** when sent (Microsoft Purview / Azure RMS / S/MIME).
- Password+SMS second channel mandatory for external sharing.

## 5. In-Transit Encryption

### 5.1. TLS Configuration

| Parameter | Value |
|-----------|-------|
| Minimum version | TLS 1.2 (1.3 preferred, 1.3 mandatory for public endpoints — by year-end) |
| Forbidden | SSLv2, SSLv3, TLS 1.0, TLS 1.1 |
| Cipher Suite (TLS 1.3) | TLS_AES_256_GCM_SHA384, TLS_AES_128_GCM_SHA256, TLS_CHACHA20_POLY1305_SHA256 |
| Cipher Suite (TLS 1.2) | ECDHE-ECDSA-AES256-GCM-SHA384, ECDHE-RSA-AES256-GCM-SHA384, ECDHE-ECDSA-CHACHA20-POLY1305 (only these or equivalent) |
| Forbidden Cipher | RC4, 3DES, NULL, EXPORT, CBC-only mode (legacy exception), MD5, SHA-1 |
| HSTS | Mandatory, max-age ≥ 31536000, includeSubDomains, preload recommended |
| Certificate | RSA 2048+ or ECDSA P-256+; SHA-256+ signature |
| OCSP Stapling | On |
| Session Resumption | TLS session ticket; ticket key rotated every 24 hours |
| Forward Secrecy | Mandatory (ECDHE) |

### 5.2. mTLS (Mutual TLS)

**mTLS mandatory** for internal service-to-service traffic (on all endpoints carrying personal data). Enforced by Service Mesh (Istio, Linkerd, Consul Connect) or cloud-native mTLS.

### 5.3. VPN / ZTNA

- Site-to-site VPN: IPsec IKEv2, AES-256-GCM, ECDH P-256 minimum.
- Remote-access VPN: WireGuard or OpenVPN with TLS 1.3 + MFA.
- ZTNA: user + device + MFA + application-based, mTLS in the background.

### 5.4. SSH

- SSH protocol 2.
- Key-based access (password access forbidden in prod).
- Key type: ed25519 (preferred) or RSA 3072+.
- Certificate-based SSH (HashiCorp Vault SSH CA / Smallstep) preferred.
- Idle timeout 15 min, root login deny.

### 5.5. TLS Even on Connections Not Containing Personal Data

Even on the internal network, **enforced TLS** rather than **opportunistic TLS**. Many breach incidents have occurred on data paths left unencrypted under the assumption that the "internal network is safe."

## 6. Key Management

### 6.1. Key Lifecycle

```
Generate → Store → Distribute → Use → Backup → Rotate → Revoke → Destroy
```

### 6.2. Generation

- Only **cryptographically secure RNG** used (within HSM; OS DRBG as fallback; RFC 4086).
- Generating keys within applications forbidden; KMS/HSM is invoked.

### 6.3. Storage

| Location | Use |
|-------|----------|
| HSM (FIPS 140-3 Level 3+) | Root keys, certificate authority (CA) signing keys |
| Cloud KMS (AWS KMS, Azure Key Vault — HSM SKU, GCP Cloud HSM) | Application data encryption keys (DEK), envelope encryption (with KEK) |
| Vault (HashiCorp Vault, CyberArk) | Secret, password, API key, short-lived credentials |
| Application memory | Only at the moment of use, "memory protected" if possible (not LSASS; mlock, secure enclave) |
| Cleartext on disk | **Forbidden** |
| Code repository | **Forbidden** (gitleaks/trufflehog blocking in CI) |
| Environment variable (.env) | Development only; KMS/Vault integration in production |

### 6.4. Hierarchy (Envelope Encryption)

```
HSM (Master Key)
   ├── KEK — Key Encryption Key (KMS)
         ├── DEK — Data Encryption Key (application)
               └── Data (AES-GCM)
```

A separate DEK for each data item; can be stored together with the data in encrypted form with the KEK. Key rotation is performed at the KEK level; data re-encryption is not required.

### 6.5. Rotation

| Key Type | Rotation Frequency |
|--------------|------------------|
| TLS server certificate | ≤ 90 days (ACME/automation) |
| Code signing certificate | 1–3 years (HSM-bound) |
| KEK (KMS) | Annual automatic |
| DEK | No re-encrypt; KEK rotation sufficient |
| API key (service) | ≤ 180 days |
| Service account secret | ≤ 90 days, automatic |
| SSH key | On personnel departure, on breach |
| HSM master | 5 years (with ceremony) |

**Emergency rotation** — performed immediately on any leak suspicion; impact analysis reported.

### 6.6. Separation of Duties

- Key generation, key use, key backup performed by **different people**.
- "M-of-N" (e.g., 3-of-5) ceremony: in physical ceremony for root key generation, recordings are taken, digital + wet signatures, vault.
- Key administrator and audit log administrator are different persons.

### 6.7. BYOK / HYOK

- **BYOK (Bring Your Own Key):** Key generation/import on our side, use in cloud. Suitable for most enterprise scenarios.
- **HYOK (Hold Your Own Key):** Key on our side, the cloud provider only accesses with the necessary minimum to perform encrypted operations. Preferred when there are sovereignty / jurisdiction concerns.
- Key access logs kept on **our side** in both models.

### 6.8. Key Destruction (Crypto-Shredding)

- The destruction of a dataset can only be ensured by **secure destruction** of the DEK belonging to that data (compliant with KVKK Art. 7 / Destruction Regulation, integrated with [04-veri-saklama-ve-imha](../04-veri-saklama-ve-imha/)).
- DEK destruction evidence = system log indicating that all key replicas, including backups, have been zeroized + destruction record.
- Crypto-shredding does **not replace** physical destruction + degausser processes; it is applied in parallel.

## 7. Application-Level Encryption Practices

- **Salted hash is not pseudonymization** — it cannot replace personal data minimization.
- When **deterministic encryption** is used, take measures against frequency analysis (e.g., danger for low-cardinality fields).
- **Format-Preserving Encryption (FPE — NIST SP 800-38G — FF1/FF3):** in fields where format must be preserved like card numbers; FF1 is recommended over FF3 (FF3 weakness was identified).
- **Tokenization:** See [veri-maskeleme-anonimlestirme.md](veri-maskeleme-anonimlestirme.md).
- **Confidential Computing:** Intel SGX/TDX, AMD SEV-SNP, AWS Nitro Enclaves for sensitive workloads; provider's "in-use" encryption guarantee is useful.

## 8. Sectoral Additional Requirements

### 8.1. Banking and Payments (PCI DSS v4.0 — where applicable)

- PAN storage forbidden (without justification). If stored: hash + salt, partial display (BIN + last 4); for full PAN, field-level encryption + TDE + HSM.
- CVV/CVC2/CAV2 cannot be stored under any conditions.
- HSM FIPS 140-3 Level 3+; PIN block ZPK transport.
- Manual Key Loading → Component / Key Splitting / Dual Control.

### 8.2. Health (Special Category — KVKK Art. 6)

- Field-level encryption mandatory.
- Decryption access only to "treating health personnel" + "explicit consent / framework exception".
- If HIPAA requirement exists, BAA + additional controls (for international business).

### 8.3. Children's Data

- For data identified as belonging to a minor, additional "data isolation" + separate key chain recommended.

## 9. Checklist

- [ ] Are all laptops/devices encrypted (FDE) and enforced via MDM?
- [ ] Is server disk encryption + DB TDE + field-level encryption applied on critical fields?
- [ ] Is HSM/KMS-based key management centralized (no keys in code)?
- [ ] Is the envelope encryption (KEK/DEK) hierarchy applied?
- [ ] Is the key rotation schedule documented and automatic?
- [ ] Is TLS 1.3 (or 1.2 + strict ciphers) on all external endpoints?
- [ ] Are HSTS, OCSP stapling, FS active?
- [ ] Is mTLS applied on internal personal data traffic?
- [ ] Are backups encrypted and on a separate key chain?
- [ ] Is the crypto-shredding process integrated with the destruction policy?
- [ ] Is CMK/BYOK applied in the cloud (for high-sensitivity)?
- [ ] Is separation of duties (key gen ≠ use ≠ audit) ensured?
- [ ] Is the PQC roadmap defined and the hybrid pilot started?
- [ ] Is secret scanning active in CI/CD for detection of leaked keys?
- [ ] Are key access logs defined as alarm rules in SIEM?
- [ ] Is algorithm deprecation tracked (annual review)?

## 10. Logging and Monitoring

- Key creation, use, rotation, import/export, destruction — KMS/HSM logs to SIEM.
- Anomalous key usage (unusual volume, unexpected client) high-priority alarm.
- Certificate expiry warning: 30, 14, 7, 1 days in advance — TLS expiry of a critical service is a major incident.

## 11. Breach Scenarios

- **Suspected key leak:** Relevant key immediately "disabled" + re-encrypt task plan for all dependent data + breach management (08).
- **Algorithm break (PQC quantum attack, etc.):** Crypto-agility plan executed, migration to hybrid/PQC algorithm accelerated.
- **Physical HSM breach:** HSM tamper-evident; on tamper detection, key zeroize, BCP activated, restore with the recovery key set previously stored offline.

---

## Türkçe

# Şifreleme

## 1. Amaç

Kişisel verinin **beklerken (at-rest)**, **taşınırken (in-transit)** ve duruma göre **kullanılırken (in-use)** kriptografik kontrollerle korunmasını standardize eder. KVKK Veri Güvenliği Rehberi'nde "Şifreleme" başlığı altında öne çıkarılan kontrolün operasyonel uygulamasıdır.

## 2. Veri Sınıflandırması Temelinde Şifreleme Zorunluluğu

| Sınıf | Tanım | At-Rest | In-Transit | In-Use |
|-------|-------|---------|------------|--------|
| Çok Gizli | Özel nitelikli (KVKK m.6), kart sahibi verisi (PAN), kimlik doğrulama sırrı | **Zorunlu** (alan-seviyesi + DB/Disk) | **Zorunlu** (TLS 1.3, mTLS dahili) | Mümkünse **zorunlu** (CSE, confidential computing) |
| Gizli | Genel kişisel veri, ticari sır | **Zorunlu** (DB/Disk) | **Zorunlu** (TLS 1.2+) | Önerilir |
| Dahili | Operasyonel veri, kişisel veri içermeyen | Önerilir | **Zorunlu** (TLS 1.2+) | Gerekli değil |
| Kamuya Açık | Web içeriği vb. | Bütünlük (imza/hash) | TLS önerilir | – |

Sınıflandırma, [00-yonetisim](../00-yonetisim/) altındaki Veri Sınıflandırma Politikası'na bağlıdır.

## 3. Onaylı Algoritmalar (2026 itibarıyla)

### 3.1. Simetrik

| Algoritma | Mod | Anahtar | Kullanım | Durum |
|-----------|-----|---------|----------|-------|
| AES | GCM | 256 bit | Tercihli (AEAD) | Onaylı |
| AES | GCM | 128 bit | Genel | Onaylı |
| AES | CBC + HMAC-SHA256 | 256 bit | Eski uyumluluk | Onaylı (yeni tasarımda GCM tercih) |
| ChaCha20-Poly1305 | – | 256 bit | Mobil/IoT, AEAD | Onaylı |
| 3DES | – | – | – | **Yasak** |
| RC4 | – | – | – | **Yasak** |
| DES | – | – | – | **Yasak** |
| AES | ECB | – | – | **Yasak** (deterministic, pattern leakage) |

### 3.2. Asimetrik

| Algoritma | Boyut | Kullanım | Durum |
|-----------|-------|----------|-------|
| RSA | ≥ 3072 bit | İmza, anahtar sarma | Onaylı (yeni sistemde ECC tercih) |
| ECDSA | P-256 / P-384 | İmza | Onaylı |
| Ed25519 | – | İmza | Onaylı (tercihli) |
| ECDH | P-256 / P-384 / X25519 | Anahtar değişimi | Onaylı |
| RSA | < 2048 bit | – | **Yasak** |
| DSA | – | – | **Yasak** |

### 3.3. Hash ve KDF

| Algoritma | Kullanım | Durum |
|-----------|----------|-------|
| SHA-256 / SHA-384 / SHA-512 | Genel hash, HMAC | Onaylı |
| SHA-3 ailesi | Yeni sistem | Onaylı |
| BLAKE2/3 | Hızlı hash (içsel) | Onaylı |
| Argon2id | Parola hashleme | Onaylı (tercihli) |
| bcrypt (cost ≥ 12) | Parola hashleme | Onaylı |
| scrypt | Parola hashleme | Onaylı |
| PBKDF2-HMAC-SHA256 (≥ 600k iter) | Eski sistem geçişi | Geçici onaylı |
| HKDF | Anahtar türetme | Onaylı |
| MD5 | – | **Yasak** |
| SHA-1 | – | **Yasak** (HMAC dahil yeni tasarımda) |

### 3.4. Post-Quantum Cryptography (PQC)

NIST 2024'te FIPS 203 (ML-KEM, eski adıyla Kyber), FIPS 204 (ML-DSA, eski adıyla Dilithium), FIPS 205 (SLH-DSA, eski adıyla SPHINCS+) standardize etti. Bizim PQC yol haritamız:

- **2026:** Hibrit (X25519 + ML-KEM-768) anahtar değişimi pilotu — TLS 1.3, VPN.
- **2027:** Kritik PKI hiyerarşisinde imza için ML-DSA pilotu.
- **2028+:** Yeni sertifika üretimi tamamen hibrit/PQC.
- **Crypto agility:** Hiçbir uygulama, algoritma adı/parametresini kod içine sabitleyemez (config + abstraction katmanı).

## 4. At-Rest Şifreleme

### 4.1. Disk-Seviyesi (FDE)

- Tüm dizüstü ve mobil cihazlar BitLocker (Windows) / FileVault (macOS) / LUKS (Linux) ile zorunlu şifreli, MDM ile uygulanır.
- Sunucu/sanal makina diskleri: bulut sağlayıcısının default disk şifrelemesi + ek olarak müşteri yönetimli anahtar (CMK/BYOK) kullanılır.
- USB/depolama medyaları: hardware encrypted (FIPS 140-3 Level 2+) veya iletim öncesi yazılım şifreleme zorunlu.

### 4.2. Veritabanı (TDE — Transparent Data Encryption)

- SQL Server / Oracle / PostgreSQL (pgcrypto / TDE eklentisi) / MySQL InnoDB Tablespace Encryption — DB seviyesinde tüm veri ve log dosyaları AES-256.
- Anahtar HSM / KMS'de tutulur, DB sadece anahtar referansı bilir.
- TDE alone yetmez; kişisel veri içeren kritik kolonlar için **alan-seviyesi şifreleme** ek olarak uygulanır.

### 4.3. Alan-Seviyesi (Field-Level / Column-Level)

Kart numarası, TC kimlik numarası, IBAN, sağlık verisi, biyometrik şablon gibi alanlar **uygulama veya DB seviyesinde** ayrıca şifrelenir.

- Uygulama tarafı şifreleme (CSE — Client-Side Encryption): DB yöneticisi bile düz metni göremez.
- Şifre çözmek için yetki, uygulama içinde RBAC + audit ile sınırlandırılır.
- Aramada gerekiyorsa **deterministic encryption** (AES-SIV) veya **searchable encryption** ile (re-identification riskleri değerlendirilerek) uygulanır.

### 4.4. Object Storage (S3 / Blob / GCS)

- SSE-KMS / Customer-Managed Key zorunlu.
- BYOK / HYOK opsiyonel (yüksek hassasiyet).
- Bucket policy ile şifresiz upload reddedilir (`s3:x-amz-server-side-encryption` zorlaması).
- Versiyonlama + Object Lock (WORM) kritik veri için aktif.

### 4.5. Yedek Şifreleme

- Yedek dosyaları **her zaman** şifreli üretilir.
- Yedek anahtarı, üretim sistemi anahtarından **ayrı** key chain'de tutulur (ransomware ölçütü).
- Bkz. [yedekleme.md](yedekleme.md).

### 4.6. E-posta ve Dosya Paylaşım

- E-posta gövdesinde kişisel veri içeren ekler **etiketlenir** (Sensitivity Label) ve **otomatik şifreli** gönderilir (Microsoft Purview / Azure RMS / S/MIME).
- Dış paylaşımda parola+SMS ikinci kanal zorunlu.

## 5. In-Transit Şifreleme

### 5.1. TLS Konfigürasyonu

| Parametre | Değer |
|-----------|-------|
| Minimum sürüm | TLS 1.2 (1.3 tercih edilir, public endpoint için 1.3 zorunlu — yıl sonu) |
| Yasaklı | SSLv2, SSLv3, TLS 1.0, TLS 1.1 |
| Cipher Suite (TLS 1.3) | TLS_AES_256_GCM_SHA384, TLS_AES_128_GCM_SHA256, TLS_CHACHA20_POLY1305_SHA256 |
| Cipher Suite (TLS 1.2) | ECDHE-ECDSA-AES256-GCM-SHA384, ECDHE-RSA-AES256-GCM-SHA384, ECDHE-ECDSA-CHACHA20-POLY1305 (sadece bunlar veya eşdeğeri) |
| Yasak Cipher | RC4, 3DES, NULL, EXPORT, CBC-only mode (legacy istisna), MD5, SHA-1 |
| HSTS | Zorunlu, max-age ≥ 31536000, includeSubDomains, preload önerilir |
| Certificate | RSA 2048+ veya ECDSA P-256+; SHA-256+ imza |
| OCSP Stapling | Açık |
| Session Resumption | TLS session ticket; ticket key 24 saatte rotasyon |
| Forward Secrecy | Zorunlu (ECDHE) |

### 5.2. mTLS (Mutual TLS)

Dahili servis-servis trafiği için **mTLS zorunlu** (kişisel veri taşıyan tüm endpoint'lerde). Service Mesh (Istio, Linkerd, Consul Connect) veya cloud native mTLS ile zorlanır.

### 5.3. VPN / ZTNA

- Site-to-site VPN: IPsec IKEv2, AES-256-GCM, ECDH P-256 minimum.
- Remote-access VPN: WireGuard veya OpenVPN with TLS 1.3 + MFA.
- ZTNA: kullanıcı + cihaz + MFA + uygulama bazlı, mTLS arka planında.

### 5.4. SSH

- SSH protocol 2.
- Anahtar tabanlı erişim (parola erişimi prod'da yasak).
- Anahtar tipi: ed25519 (tercihli) veya RSA 3072+.
- Sertifika tabanlı SSH (HashiCorp Vault SSH CA / Smallstep) tercih edilir.
- Idle timeout 15 dk, root login deny.

### 5.5. Kişisel Veri İçermeyen Bağlantılarda Bile TLS

İç ağda bile **opportunistic TLS değil**, **enforced TLS**. Pek çok ihlal olayı, "iç ağ güvenli" varsayımıyla şifresiz bırakılan veri yolunda gerçekleşmiştir.

## 6. Anahtar Yönetimi

### 6.1. Anahtar Yaşam Döngüsü

```
Üret → Sakla → Dağıt → Kullan → Yedekle → Rotasyon → İptal → İmha
```

### 6.2. Üretim

- Sadece **kriptografik olarak güvenli RNG** kullanılır (HSM içi; OS DRBG yedek olarak; RFC 4086).
- Uygulama içinde anahtar üretmek yasak; KMS/HSM çağırılır.

### 6.3. Saklama

| Konum | Kullanım |
|-------|----------|
| HSM (FIPS 140-3 Level 3+) | Kök anahtarlar, sertifika otoritesi (CA) imza anahtarları |
| Cloud KMS (AWS KMS, Azure Key Vault — HSM SKU, GCP Cloud HSM) | Uygulama veri şifreleme anahtarları (DEK), envelope encryption (KEK ile) |
| Vault (HashiCorp Vault, CyberArk) | Secret, parola, API key, kısa ömürlü kimlik bilgisi |
| Uygulama belleği | Yalnızca kullanım anında, mümkünse "memory protected" (LSASS değil; mlock, secure enclave) |
| Düz metin diskte | **Yasak** |
| Kod deposu | **Yasak** (gitleaks/trufflehog CI'da blocking) |
| Ortam değişkeni (.env) | Sadece geliştirme; prod'da KMS/Vault entegrasyonu |

### 6.4. Hiyerarşi (Envelope Encryption)

```
HSM (Master Key)
   ├── KEK — Key Encryption Key (KMS)
         ├── DEK — Data Encryption Key (uygulama)
               └── Veri (AES-GCM)
```

DEK her veri öğesi için ayrı; KEK ile şifrelenmiş halde veriyle birlikte saklanabilir. Anahtar rotasyonu KEK seviyesinde yapılır; veri yeniden şifreleme gerekmez.

### 6.5. Rotasyon

| Anahtar Türü | Rotasyon Sıklığı |
|--------------|------------------|
| TLS sunucu sertifikası | ≤ 90 gün (ACME/automation) |
| Kod imza sertifikası | 1–3 yıl (HSM-bound) |
| KEK (KMS) | Yıllık otomatik |
| DEK | Re-encrypt yok; KEK rotasyonu yeterli |
| API key (servis) | ≤ 180 gün |
| Service account secret | ≤ 90 gün, otomatik |
| SSH anahtar | Personel ayrılışında, ihlalde |
| HSM master | 5 yıl (ceremony ile) |

**Olağanüstü rotasyon** — herhangi bir sızıntı şüphesinde derhal yapılır; etki analizi raporlanır.

### 6.6. Görev Ayrılığı (Separation of Duties)

- Anahtar üretim, anahtar kullanım, anahtar yedekleme **farklı kişiler** tarafından yapılır.
- "M-of-N" (örn. 3-of-5) ceremony: kök anahtar üretiminde fiziksel törende kayıt alınır, dijital + ıslak imza, vault.
- Anahtar yöneticisi ile audit log yöneticisi farklı kişi.

### 6.7. BYOK / HYOK

- **BYOK (Bring Your Own Key):** Anahtar üretim/import bizde, bulutta kullanım. Çoğu kurumsal senaryo için uygun.
- **HYOK (Hold Your Own Key):** Anahtar bizde, bulut sağlayıcı sadece şifreli işlemi yapacak gerekli minimumla erişir. Egemenlik / yargı yetkisi endişesi olduğunda tercih edilir.
- Her iki modelde de anahtar erişim logu **bizim tarafımızda** tutulur.

### 6.8. Anahtar İmha (Crypto-Shredding)

- Bir veri kümesinin imhası, yalnızca o veriye ait DEK'in **güvenli imhasıyla** sağlanabilir (KVKK m.7 / İmha Yönetmeliği uyumlu, [04-veri-saklama-ve-imha](../04-veri-saklama-ve-imha/) ile entegre).
- DEK imha kanıtı = yedek dahil tüm anahtar replikalarının zeroize edildiğine dair sistem logu + imha tutanağı.
- Crypto-shredding, fiziksel imha + degausser süreçleri **yerine geçmez**, paralel uygulanır.

## 7. Uygulama Seviyesi Şifreleme Pratikleri

- **Tuzlu hash sahte değildir** — kişisel veri minimizasyonu yerine geçemez.
- **Deterministic encryption** kullanıldığında frequency analizine karşı önlem (örn. düşük kardinalite alanları için tehlike).
- **Format-Preserving Encryption (FPE — NIST SP 800-38G — FF1/FF3):** kart numarası gibi format korunması gereken alanlarda; FF3 yerine FF1 önerilir (FF3 zayıflığı tespit edildi).
- **Tokenization:** Bkz. [veri-maskeleme-anonimlestirme.md](veri-maskeleme-anonimlestirme.md).
- **Confidential Computing:** Hassas iş yükleri için Intel SGX/TDX, AMD SEV-SNP, AWS Nitro Enclaves; sağlayıcının "in-use" şifreleme garantisi yararlı.

## 8. Sektörel Ek Gereksinimler

### 8.1. Bankacılık ve Ödeme (PCI DSS v4.0 — uygulanabildiği yerlerde)

- PAN saklama yasaktır (gerekçe yoksa). Saklanırsa: hash + tuz, kısmi gösterim (BIN + son 4), full PAN ise alan-seviyesi şifreleme + TDE + HSM.
- CVV/CVC2/CAV2 hiçbir koşulda saklanamaz.
- HSM FIPS 140-3 Level 3+; PIN bloku ZPK transport.
- Anahtar Manuel Yükleme → Component / Key Splitting / Dual Control.

### 8.2. Sağlık (Özel Nitelikli — KVKK m.6)

- Alan-seviyesi şifreleme zorunlu.
- Şifre çözme erişimi sadece "tedavi gören sağlık personeli" + "açık rıza/çerçeve istisnası" ile.
- HIPAA gereksinimi varsa BAA + ek kontroller (uluslararası iş için).

### 8.3. Çocuk Verisi

- Reşit olmadığı tespit edilen veri için ek "data isolation" + ayrı anahtar zinciri tavsiye.

## 9. Kontrol Listesi

- [ ] Tüm dizüstü/cihaz disk şifreli (FDE) ve MDM ile zorunlu kılınmış mı?
- [ ] Sunucu disk şifreleme + DB TDE + kritik alanlarda alan-seviyesi şifreleme uygulanıyor mu?
- [ ] HSM/KMS tabanlı anahtar yönetimi merkezi mi (kod içinde anahtar yok)?
- [ ] Envelope encryption (KEK/DEK) hiyerarşisi uygulanıyor mu?
- [ ] Anahtar rotasyon takvimi yazılı ve otomatik mi?
- [ ] TLS 1.3 (veya 1.2 + sıkı cipher) tüm dış endpoint'lerde mi?
- [ ] HSTS, OCSP stapling, FS aktif mi?
- [ ] mTLS dahili kişisel veri trafiğinde uygulanıyor mu?
- [ ] Yedekler şifreli ve ayrı anahtar chain'de mi?
- [ ] Crypto-shredding süreci imha politikasıyla entegre mi?
- [ ] Bulutta CMK/BYOK uygulanıyor mu (high-sensitivity için)?
- [ ] Görev ayrılığı (anahtar üretim ≠ kullanım ≠ audit) sağlanıyor mu?
- [ ] PQC yol haritası tanımlı, hibrit pilot başlatıldı mı?
- [ ] Sızdırılmış anahtarın tespiti için CI/CD'de secret scanning aktif mi?
- [ ] Anahtar erişim logları SIEM'de uyarı kuralı olarak tanımlı mı?
- [ ] Algoritma deprecation takibi yapılıyor mu (yıllık review)?

## 10. Loglama ve İzleme

- Anahtar oluşturma, kullanım, rotasyon, import/export, imha — KMS/HSM logları SIEM'e.
- Anormal anahtar kullanım (sıra dışı hacim, beklenmeyen istemci) yüksek öncelik alarmı.
- Sertifika sona erme uyarısı: 30, 14, 7, 1 gün öncesinden — kritik servisin TLS sona ermesi büyük olay.

## 11. İhlal Senaryoları

- **Anahtar sızıntısı şüphesi:** İlgili anahtar derhal "disabled" + tüm bağımlı veri için re-encrypt görev planı + ihlal yönetimi (08).
- **Algoritma kırılması (PQC kuantum saldırısı vb.):** Crypto-agility planı çalıştırılır, hibrit/PQC algoritmaya migrasyon hızlandırılır.
- **HSM fiziksel ihlal:** HSM tamper-evident; tampering tespitinde anahtar zeroize, BCP devreye, önceden offline saklanan recovery anahtar setiyle restore.
