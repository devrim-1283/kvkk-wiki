---
Doküman: Kimlik Doğrulama Politikası ve Standardı
Bölüm: 05-teknik-tedbirler
Sahip: IAM Ekip Lideri / CISO
Onaylayan: BT Direktörü + KVKK Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (yeni IdP, yeni MFA faktörü, breach trendi)
İlgili Mevzuat: 6698 sayılı KVKK m.12; Kişisel Veri Güvenliği Rehberi — "Kullanıcı Hesap Yönetimi", "Şifreleme"
İlgili Standart: ISO/IEC 27001:2022 A.5.16, A.5.17, A.8.5; NIST SP 800-63B (Digital Identity — Authentication); NIST CSF 2.0 PR.AA-3, PR.AA-5; OWASP ASVS V2 (Authentication); FIDO Alliance specs (FIDO2/WebAuthn)
---

# Kimlik Doğrulama

## 1. Amaç

Sistemlere erişim talep eden kullanıcı, servis veya cihazın **gerçekten iddia ettiği kimlik olduğunu** kanıtlayan kontrolleri tanımlar. KVKK m.12 kapsamında "yetkisiz erişimi engelleme" hedefinin kimlik tarafını oluşturur.

## 2. Tanımlar

| Terim | Tanım |
|-------|-------|
| Authenticator | Kullanıcının kimliğini ispatlamada kullandığı şey (parola, donanım anahtarı, biyometri, push, OTP). |
| Faktör | Bilgi (knowledge), sahip olma (possession), nitelik (inherence). |
| MFA | İki veya daha fazla **bağımsız** faktörle kimlik doğrulama. |
| AAL | Authenticator Assurance Level (NIST 800-63B; AAL1, AAL2, AAL3). |
| IdP | Identity Provider — merkezi kimlik sağlayıcı (Entra ID, Okta, Keycloak vb.). |
| SSO | Single Sign-On — bir oturumla birden çok uygulamaya erişim. |
| FIDO2/WebAuthn | Phishing'e dayanıklı asimetrik kriptografi tabanlı kimlik doğrulama. |
| Adaptive Auth | Risk skoruna göre faktör/yöntem seçen dinamik politika. |

## 3. Çok Faktörlü Kimlik Doğrulama (MFA)

### 3.1. MFA Zorunluluk Matrisi

| Erişim Senaryosu | MFA | Faktör Tercihi |
|------------------|-----|-----------------|
| Yönetici / ayrıcalıklı hesap (her seferinde) | **Zorunlu** | FIDO2 (donanım) **veya** authenticator app push + number matching |
| Uzaktan erişim (VPN, ZTNA, Citrix, RDS) | **Zorunlu** | FIDO2 / authenticator app |
| Kişisel veri içeren tüm uygulamalar | **Zorunlu** | Authenticator app + cihaz uyumluluğu |
| Tüm kurumsal kullanıcı (genel) | **Zorunlu (kademe halinde 2026 sonu)** | Authenticator app |
| Müşteri/ilgili kişi self-service portal | Tavsiye edilir; kritik aksiyon (parola değişimi, veri indirme) için **zorunlu** | TOTP / push / WebAuthn |
| API kullanıcısı | mTLS + kısa ömürlü token (statik MFA değil) | mTLS / signed assertion |

### 3.2. Phishing-Resistant MFA Önceliği

NIST SP 800-63B AAL3 ve CISA önerileri doğrultusunda, **SMS OTP ve sesli arama OTP yüksek riskli kabul edilir** ve aşağıdaki durumlarda kullanılamaz:

- Tüm yönetici hesaplar.
- Kişisel veri içeren üretim sistemlerine erişim.
- Yurt dışından kurumsal kaynağa erişim.

Tercih sırası: **FIDO2/WebAuthn (donanım anahtarı / passkey) > Authenticator app + number matching > Authenticator app push (number matching olmadan) > TOTP > SMS OTP (sadece son seçenek, kısa süreli geçiş için).**

### 3.3. Push Fatigue Karşı Önlemleri

- **Number matching** zorunlu.
- Kullanıcı konumu/cihaz/uygulama bilgisi push ekranında gösterilir.
- 3 başarısız push'tan sonra hesap kilidi.
- Aynı kullanıcının kısa sürede çoklu push isteği SOC alarmı.

### 3.4. MFA Bypass Yasaktır

- "Trusted device — 30 gün MFA atla" gibi seçenekler kapatılır (yalnızca düşük riskli SaaS senaryolarında, KVKK Sorumlusu onayıyla, max 7 gün).
- Service account'lar için MFA atlanmaz; mTLS / managed identity kullanılır.

## 4. Single Sign-On (SSO) ve IdP

### 4.1. Tek Kimlik Otoritesi

Tüm kurumsal kimlikler **tek bir IdP'de** (Entra ID / Okta / Keycloak / Auth0 vb.) yönetilir. Uygulamalar mümkün olduğunca **SAML 2.0 veya OpenID Connect (OIDC)** ile bu IdP'ye federe edilir.

### 4.2. Federasyon Yararları

- Joiner/Mover/Leaver tek noktadan kontrol edilir.
- MFA, koşullu erişim, adaptive auth politikaları **tek yerde** uygulanır.
- Şifre tabanlı saldırı yüzeyi azalır (kullanıcı uygulama parolası tutmaz).
- Loglar tek yerde — SIEM korelasyonu kolaylaşır.

### 4.3. SAML / OIDC Uygulama Standartları

- SAML imza algoritması en az **RSA-SHA256** veya **ECDSA-SHA256**. SHA-1 yasak.
- SAML response içinde audience, recipient, NotOnOrAfter doğrulaması zorunlu.
- OIDC: PKCE (Proof Key for Code Exchange) **public client** için zorunlu. Implicit flow yasaktır.
- ID token doğrulama: imza + issuer + audience + nonce.
- Refresh token ROTATE on use, sızıntı tespitinde tüm zincir iptal.
- Token ömürleri: access token ≤ 60 dk, refresh token ≤ 30 gün (kullanım yoksa daha kısa).

### 4.4. Conditional Access / Adaptive Authentication

Risk skoruna göre dinamik politika örnekleri:

```
IF user IN "Admins"
   AND signin_country NOT IN ("TR", "DE", "GB")
THEN block

IF resource = "Customer-Data-App"
   AND device_compliant = false
THEN require_MFA + block_download

IF risk_level = "high" (atypical travel, leaked credential)
THEN require_password_change + require_MFA + notify_SOC

IF login_time NOT IN business_hours AND user IN "Privileged"
THEN require_PIM_elevation_approval
```

## 5. Parola Politikası (NIST SP 800-63B Uyumlu)

### 5.1. Filozofi Değişimi

KVKK Veri Güvenliği Rehberi'nin "güçlü parola" yaklaşımı ile **NIST 800-63B-4** (modernize edilmiş) yaklaşımı uyumludur. Modern yaklaşımın özü:

- **Uzunluk** > karmaşıklık.
- **Periyodik zorla değiştirme** etkisiz; yalnızca **şüphe halinde** zorla değiştir.
- **Sözlük + breach corpus** kontrolü zorunlu.
- Karmaşıklık zorlaması (büyük/küçük/sayı/özel) yerine, parola güçlüğü **gerçek entropi** ile ölçülür.

### 5.2. Standart Parola Kuralları

| Parametre | Kural |
|-----------|-------|
| Minimum uzunluk (kullanıcı) | 12 karakter |
| Minimum uzunluk (yönetici) | 16 karakter (FIDO2 ile birlikte) |
| Maksimum uzunluk | En az 64 karakter desteklenmeli |
| İzin verilen karakterler | Tüm yazdırılabilir Unicode + boşluk (passphrase teşviki) |
| Karmaşıklık zorunluluğu | **Yok** (sözlük kontrolü ile ikame edilir) |
| Sözlük kontrolü | En sık 100k parola listesi + kurum adları + kullanıcı adı varyasyonları |
| Breach corpus kontrolü | Have I Been Pwned API veya offline breach database |
| Parola tarihi | Sızıntı / şüphe / ayrıcalıklı dönüşüm haricinde **zorla değişim yok** |
| Ayrıcalıklı parola tarihi | 90–180 gün; vault yönetimde otomatik rotasyon |
| Parola hint / soru | Yasak |
| Açık metinde gönderim | Yasak (ne SMS, ne e-posta) |
| Parolayı kopyala-yapıştır | Serbest (parola yöneticisi teşviki) |
| Hash | Argon2id (tercih) / bcrypt (cost ≥ 12) / scrypt; SHA-1, MD5, plain SHA-2 yasak |
| Salt | Hesap başına benzersiz, ≥ 16 byte |
| Pepper | İsteğe bağlı; uygulanırsa HSM/KMS'de tutulur |

### 5.3. Yeni Parola Belirleme Akışı

1. Kullanıcı önerilen parola yöneticisi (Bitwarden, 1Password kurumsal vb.) ile kasada üretir.
2. Form, 800-63B kurallarına uygun parolaya **anında geri bildirim** verir (zayıf/bilinen → reddet).
3. Parola hash'lenir (Argon2id), DB'ye yalnızca hash + salt yazılır.
4. Olay loglanır (kişi, zaman, IP, kullanıcı agent), parola değeri loglanmaz.

### 5.4. Parola Sızıntısı Yanıtı

- IdP, breach feed ile entegre. Eşleşme tespit edilirse hesap "force change" işaretine çekilir.
- Kullanıcı yeniden giriş yaptığında parola değişimi + tüm aktif oturum iptal + SIEM olayı.

## 6. Hesap Kilitleme ve Brute-Force Koruması

| Olay | Eşik | Aksiyon |
|------|------|---------|
| Başarısız parola denemesi | 10 (rolling 15 dk) | 15 dk soft lock + CAPTCHA |
| Başarısız MFA denemesi | 5 (rolling 10 dk) | 30 dk lock + SOC alarmı |
| Şüpheli IP / ASN | – | IP rate limit, ASN bazlı block (botnet) |
| Aynı kullanıcı 5 farklı ülke | < 1 saat | Otomatik password reset force + MFA challenge |
| Bilinen breach paroladan giriş başarılı | 1 | Hesap dondur + manuel verify + zorunlu reset |

Hesap kilidi **otomatik açılır** (zaman tabanlı); kalıcı kilit yalnızca SOC analizi sonrası uygulanır.

## 7. Service Account ve API Key Yönetimi

### 7.1. Service Account İlkeleri

- Her servis hesabı **bir uygulamaya / bir göreve** atıdır; paylaştırma yasak.
- İnsan adına ekli olamaz; ekip / sistem sahibi atanır.
- Mümkünse **kullanılmaz**: yerine managed identity (Azure MI, AWS IAM Role, GCP Workload Identity Federation, Kubernetes ServiceAccount + OIDC).
- Statik secret zorunluysa **vault** üzerinde, otomatik rotasyon (≤ 90 gün), kısa ömürlü token üretimi.
- Servis hesabı interactive login **kapalıdır** (Deny logon locally / no shell).

### 7.2. API Key Standartları

- API key uzunluğu en az 256 bit entropi (32 byte rastgele, base64url).
- Anahtar **hash** olarak DB'de tutulur; düz metin yalnızca üretim anında bir kez gösterilir.
- Anahtar başına: scope, rate limit, IP allowlist, geçerlilik süresi (≤ 1 yıl, prod için ≤ 180 gün).
- Anahtar rotasyonu otomatik veya program zamanlı.
- Anahtar sızıntı tespiti için kod deposu tarama (gitleaks, trufflehog) CI'da zorunlu.

### 7.3. OAuth 2.0 / OIDC Müşteri Tipleri

- **Confidential client** (sunucu): client secret kasada, Authorization Code Flow + PKCE.
- **Public client** (SPA, mobil): client secret yok, Authorization Code + PKCE zorunlu.
- **Machine-to-machine:** Client Credentials Flow + mTLS zorunlu.

## 8. Federe Kimlik ve Dış Kullanıcı

### 8.1. B2B (Tedarikçi/Danışman)

- Mümkünse misafir kullanıcı (B2B guest) IdP üzerinden eklenir.
- Sözleşme bitiş tarihiyle hesap **otomatik expire**.
- Misafir hesapların erişebileceği kaynak whitelist; default deny tüm tenant.
- Misafir oturumu için MFA zorunlu, yerel hesap parolasına izin verilmez (kendi tenant'ının federasyonu).

### 8.2. B2C (İlgili Kişi / Müşteri)

- Ayrı CIAM (Customer IAM) tenant — kurumsal IAM ile karıştırmayın.
- Kayıt sırasında e-posta + şifre + opsiyonel WebAuthn passkey.
- Sosyal giriş (Google, Apple) destekleniyorsa "minimum claim" alınır (aydınlatma metnine yansıtılır).
- Hesap silme self-service (KVKK m.11 hakları kapsamında) — bkz. 09-ilgili-kisi-basvurulari.

## 9. Cihaz Güvenliği ile Kimlik Bağlama

- Cihaz uyumluluğu (MDM/Intune): disk şifreli, AV güncel, OS güncel, jailbreak/root değil.
- Sertifika tabanlı cihaz kimliği (mTLS) kritik uygulamalarda.
- BYOD politikası ayrı (06-idari-tedbirler) ile birlikte; iş profili (Android Work Profile, iOS supervised) zorunlu.

## 10. Oturum Yönetimi

| Parametre | Değer |
|-----------|-------|
| Idle timeout (kişisel veri uygulaması) | 15 dakika |
| Idle timeout (genel kurumsal) | 60 dakika |
| Absolute session length | 12 saat (sonra yeniden kimlik doğrulama) |
| Session ID üretimi | ≥ 128 bit, kriptografik rastgele |
| Session cookie | HttpOnly, Secure, SameSite=Lax/Strict |
| Logout | Sunucu tarafında session invalidation, tüm cihazlardan logout opsiyonu |
| Concurrent session policy | Yönetici hesaplar için tek oturum; genel kullanıcı için izin verilir, her oturumun listelenmesi |

## 11. Self-Service ve Hesap Kurtarma

- Parola sıfırlama: kayıtlı e-posta + MFA + bilgi sorusu **değil** (NIST'e aykırı). Hesap kurtarma akışı en az MFA gücüne eşit olmalı.
- "Forgot MFA": kimlik doğrulama help desk üzerinden, video çağrı + ID belgesi (ofiste) + ikinci yöneticisi onayı (sosyal mühendisliğe karşı). Bu süreç loglanır ve SOC görür.

## 12. Loglanacak Kimlik Olayları

- Başarılı/başarısız giriş (kullanıcı, IP, kullanıcı agent, sonuç).
- MFA challenge sonucu.
- Parola değişimi/reset.
- Yeni cihaz kayıt.
- Kalıcı oturum (refresh) yenileme.
- Federation assertion.
- Yetki yükseltme.
- Hesap kilidi/kilit açma.
- Servis hesabı oluşturma/silme/secret rotasyonu.

## 13. Kontrol Listesi

- [ ] Tüm yönetici hesaplar phishing-resistant MFA ile mi giriyor?
- [ ] Uzaktan erişim için MFA zorunlu mu?
- [ ] SMS OTP yönetici/kritik için kapalı mı?
- [ ] SSO kapsamı %95+ mı (uygulama envanteri üzerinden)?
- [ ] Parola politikası NIST 800-63B uyumlu mu (uzunluk, breach kontrolü)?
- [ ] Parola hash algoritması Argon2id/bcrypt mi?
- [ ] Hesap kilitleme + brute-force koruma kuralları aktif mi?
- [ ] Service account'lar yerine managed identity kullanılıyor mu?
- [ ] API key rotation otomatik mi?
- [ ] Misafir hesap sözleşme bitiminde otomatik expire mi?
- [ ] Cihaz uyumluluğu kritik uygulama erişimi için zorunlu mu?
- [ ] Oturum timeout değerleri politikaya uygun mu?
- [ ] Tüm kimlik olayları SIEM'e gidiyor mu?
- [ ] Hesap kurtarma sosyal mühendisliğe karşı sıkılaştırıldı mı?
- [ ] Push fatigue savunmaları (number matching) aktif mi?

## 14. KPI ve Ölçüm

- MFA kapsam: %100 (yönetici, uzaktan, kişisel veri uygulamaları); genel %95+ (yıl sonu hedef).
- Parola sıfırlama oranı (helpdesk yükü): aylık takip, kullanıcı eğitimi tetikleyicisi.
- Phishing-resistant MFA oranı: %75+ (yıl sonu), %100 (2 yıl).
- Servis hesabına bağlı statik secret sayısı: aylık azalma trendi.
- Uyumsuz cihazdan erişim girişimi sayısı: SOC dashboard.
