---
Doküman: Şifreleme Politikası ve Anahtar Yönetimi Standardı
Bölüm: 05-teknik-tedbirler
Sahip: Kripto Mühendisliği / CISO
Onaylayan: BT Direktörü + KVKK Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (algoritma deprecation, yeni standart, ihlal)
İlgili Mevzuat: 6698 sayılı KVKK m.12; Kişisel Veri Güvenliği Rehberi — "Şifreleme"; Banka kartları için PCI DSS v4.0; Bankacılık için BDDK düzenlemeleri (uygulanabildiği yerlerde)
İlgili Standart: ISO/IEC 27001:2022 A.8.24 (Use of Cryptography); NIST SP 800-57 (Key Management); NIST SP 800-175B; NIST FIPS 140-3 (Cryptographic Modules); NIST FIPS 197 (AES); NIST FIPS 186-5 (Digital Signatures); NIST FIPS 203/204/205 (Post-Quantum Cryptography — ML-KEM, ML-DSA, SLH-DSA); IETF RFC 8446 (TLS 1.3); IETF RFC 7525 (TLS Recommendations BCP); Mozilla TLS Configuration; eIDAS (uluslararası geçerli imza)
---

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
