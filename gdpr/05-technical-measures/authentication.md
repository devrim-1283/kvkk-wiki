---
title:
  en: "Authentication - MFA, NIST 800-63B, SSO, Service Account Hygiene"
  tr: "Kimlik Doğrulama - MFA, NIST 800-63B, SSO, Servis Hesabı Hijyeni"
section: "05-technical-measures"
document_type: "control_policy"
control_id: "TECH-AUTH-01"
owner:
  primary: "CISO"
  secondary: "Identity Team"
review_cycle: "annual"
last_review: "2026-05-08"
next_review: "2027-05-08"
classification: "Internal"
language: ["en", "tr"]
references:
  - "GDPR Art. 5(1)(f), 32(1)(b)"
  - "ENISA Handbook on Security of Personal Data Processing"
  - "NIST SP 800-63B (Digital Identity Guidelines, 2024 update)"
  - "ISO/IEC 27002:2022 controls 5.17, 8.5"
  - "FIDO2 / WebAuthn (W3C)"
  - "SAML 2.0, OpenID Connect 1.0"
---

## English

# Authentication

## 1. Purpose

Authentication establishes that a claimed identity is genuine before any
authorisation decision. This document defines authentication requirements
implementing GDPR Article 32(1)(b), aligned with ENISA's risk-based handbook
and the 2024 update of NIST SP 800-63B.

## 2. Assurance Levels

The controller maps every system to an Authentication Assurance Level (AAL)
following NIST SP 800-63B. The mapping is recorded in the application
register.

| Level | When Used | Required Authenticators |
|-------|-----------|-------------------------|
| AAL1 | Public marketing portal, low-risk reads | Single factor (password) acceptable; MFA recommended |
| AAL2 | Employee SSO, customer self-service portals, internal apps | MFA required; phishing-resistant recommended |
| AAL3 | Administrative consoles, production data, finance, HR, DPO tools, vendor consoles handling personal data | Phishing-resistant MFA required (FIDO2 / WebAuthn / smart card) |

A system processing Article 9 special-category data, Article 10 criminal data
or large-scale personal data is AAL3 by default.

## 3. Mandatory MFA Scope

MFA is mandatory for:

- All employee, contractor and intern human identities at SSO.
- All administrative and privileged access (AAL3, phishing-resistant only).
- All remote access (VPN, ZTNA, jump hosts).
- All access to systems holding personal data (in scope of ROPA).
- All customer-facing accounts in the data-subject portal where the account
  holds Article 9 data, financial data or full transaction history.

SMS one-time codes are not accepted for AAL3. SMS is permitted only as a
fallback for AAL2 customer accounts where no other channel exists; it does not
satisfy phishing resistance.

## 4. Password Policy (NIST SP 800-63B 2024)

The controller follows NIST SP 800-63B updated guidance and rejects legacy
"complexity theatre" rules.

**Required**

- Minimum length: 12 characters for human users; 16 for privileged; 24 for
  service accounts that cannot use workload identity.
- All ASCII printable, Unicode and spaces must be accepted.
- Block known-compromised passwords by checking submissions against a curated
  breach corpus on registration and change (list refreshed at least monthly).
- Block dictionary words, context-specific words (organisation name, product
  names) and repeats.
- Hash with Argon2id (RFC 9106), scrypt, or PBKDF2 with at least 600,000
  SHA-256 iterations and a 32-byte random salt per credential.
- Account lockout or rate-limit after 100 failed attempts per account or
  source IP; CAPTCHA optional but not a substitute.

**Prohibited**

- Mandatory periodic rotation. Rotation is required only on suspected
  compromise.
- Forced character composition rules (e.g., one uppercase + one number + one
  symbol).
- Password hints stored on the account.
- Knowledge-based authentication ("mother's maiden name") as a primary or
  recovery factor.
- Recovery via email-only when the account holds AAL3 data.

## 5. Phishing-Resistant Authenticators

Phishing-resistant means cryptographic binding between the authenticator and
the relying party such that a relayed credential cannot be reused at the real
service. Acceptable forms:

- FIDO2 / WebAuthn platform authenticators (passkeys).
- FIDO2 / WebAuthn roaming authenticators (security keys, e.g. YubiKey,
  TitanKey).
- Smart cards (PIV, CAC) with mutual TLS.
- Mobile-bound certificates with hardware-backed keys, channel-bound to the
  relying party.

OTP applications (TOTP) are not phishing-resistant but are accepted as the
second factor for AAL2 only.

## 6. Single Sign-On (SSO)

### 6.1 Federation Protocols

- **SAML 2.0** for legacy enterprise apps; signed assertions; signed responses;
  audience restriction; max NotOnOrAfter 5 minutes; encrypted assertions where
  the SP supports it.
- **OpenID Connect 1.0 / OAuth 2.1** for new applications; `code` flow with
  PKCE for public clients; `client_credentials` only for confidential server-
  to-server.
- JWT signature algorithms: RS256, ES256, EdDSA. `none` is rejected. HS256 only
  for symmetric internal channels with HSM-managed keys.

### 6.2 IdP Hardening

- IdP administrators are AAL3 with break-glass procedure.
- Admin actions logged to immutable store and reviewed weekly.
- Just-in-time provisioning with attribute mapping from HR.
- Conditional access policies enforce device posture, location and risk score.
- Federation metadata refreshed and signed; trust changes follow change
  control.
- Session lifetime: 8 hours for standard users, 4 hours for AAL3, 1 hour for
  privileged consoles. Idle timeout: 30 minutes for AAL3.
- Token replay protection - refresh token rotation enabled; token binding
  where supported.

### 6.3 Logout

- Single logout (front-channel and back-channel) where supported.
- Logout invalidates session at IdP and all federated SPs the user had active.

## 7. Service Account Hygiene

Service accounts are credentials used by software, not by humans. They are the
most common cause of large data breaches. The controller enforces:

- A registered owner (person and team) for every service account.
- A documented purpose recorded in the IAM directory.
- Workload identities (mTLS, SPIFFE, federated tokens, cloud IAM roles) in
  preference to static credentials.
- Where static credentials are unavoidable:
  - Stored in the secrets manager only.
  - Rotated automatically at most every 90 days.
  - Scoped narrowly (one purpose, one environment).
  - Never committed to source control. CI scans block commits.
- No interactive login. Service accounts cannot use SSO consoles.
- Anomaly detection monitors for unusual source IPs, locations, action
  patterns and time-of-day usage.

## 8. Customer Authentication

Customer-facing authentication implements:

- AAL2 minimum for any account holding personal data.
- Passkey (FIDO2 / WebAuthn) offered as primary; password + TOTP as fallback.
- Account recovery requires multi-channel verification (email + phone) and
  re-authentication of remaining factors before high-impact actions.
- Re-authentication required before:
  - Changing email or phone of record.
  - Adding or changing payment method.
  - Exporting personal data via the data-subject portal
    (`09-data-subject-rights/`).
  - Deleting the account.

## 9. Authentication Logging

Every authentication attempt produces a log entry containing at minimum:

- Identity (subject ID, not raw username where possible).
- Timestamp (UTC, RFC 3339, milliseconds).
- Outcome (success, failure, MFA challenge issued, MFA failure).
- Authenticator used.
- Source IP, ASN, country.
- User agent / device identifier.
- Risk score where issued.
- Correlation ID linking the session.

Logs are streamed to SIEM (`logging.md`). Detection rules cover impossible
travel, password spray, MFA fatigue, credential stuffing, anomalous service
account activity.

## 10. Anti-Automation and Abuse

- Bot management on public login flows.
- Rate limits per account, per source IP and per ASN.
- MFA fatigue protection - number matching for push, with click-to-approve
  disabled.
- Suspicious-login email and in-app notifications to users.
- Account lockout policies tested under tabletop scenarios twice a year.

## 11. KPIs and Metrics

| Metric | Target |
|--------|--------|
| Privileged accounts on phishing-resistant MFA | 100 % |
| Workforce accounts on MFA | 100 % |
| Customer accounts (AAL2 scope) on MFA | >= 90 % adoption |
| Static admin credentials | 0 |
| Service accounts with rotation overdue | 0 |
| Mean time to revoke compromised credential | <= 1 hour |
| Failed authentication anomaly alert MTTR | <= 4 hours |

## 12. Mapping

| Requirement | NIST 800-63B | ISO 27002:2022 | NIST CSF 2.0 |
|-------------|--------------|----------------|--------------|
| Multi-factor for AAL2/3 | 4.2.2 / 4.3 | 8.5 | PR.AA-2 |
| Phishing resistance for AAL3 | 4.3 | 8.5 | PR.AA-2 |
| Password storage | 5.1.1.2 | 8.24 | PR.DS-1 |
| Authentication logging | 5.2.10 | 8.15 | DE.CM-1 |
| Session management | 7 | 5.17 | PR.AA-3 |

---

## Türkçe

# Kimlik Doğrulama

## 1. Amaç

Kimlik doğrulama, herhangi bir yetkilendirme kararı verilmeden önce iddia
edilen kimliğin gerçekliğini tespit eder. Bu belge, GDPR Madde 32(1)(b)
gereksinimlerini uygulayan ve ENISA risk temelli el kitabı ile NIST SP 800-63B
2024 güncellemesi ile uyumlu kimlik doğrulama gereksinimlerini tanımlar.

## 2. Güvence Seviyeleri

Kontrolör her sistemi NIST SP 800-63B'ye göre bir Kimlik Doğrulama Güvence
Seviyesi (AAL) ile eşler. Eşleme uygulama kayıtlarında tutulur.

| Seviye | Kullanım | Gerekli Kimlik Doğrulayıcı |
|--------|----------|----------------------------|
| AAL1 | Genel pazarlama portalı, düşük riskli okumalar | Tek faktör (parola) kabul; MFA önerilir |
| AAL2 | Çalışan SSO, müşteri self servis portalları, dahili uygulamalar | MFA zorunlu; phishing'e dayanıklı önerilir |
| AAL3 | Yönetim konsolları, üretim verisi, finans, İK, VKS araçları, kişisel veri taşıyan tedarikçi konsolları | Phishing'e dayanıklı MFA zorunlu (FIDO2 / WebAuthn / akıllı kart) |

Madde 9 özel nitelikli, Madde 10 cezai veri veya büyük ölçekli kişisel veri
işleyen sistem varsayılan olarak AAL3'tür.

## 3. Zorunlu MFA Kapsamı

MFA şunlar için zorunludur:

- Tüm çalışan, yüklenici ve stajyer insan kimlikleri SSO'da.
- Tüm yönetimsel ve ayrıcalıklı erişim (AAL3, yalnızca phishing'e dayanıklı).
- Tüm uzaktan erişim (VPN, ZTNA, jump host).
- Kişisel veri taşıyan sistemlere (ROPA kapsamında) tüm erişim.
- Veri sahibi portalında hesabın Madde 9 verisi, finansal veri veya tam işlem
  geçmişi taşıdığı tüm müşteri hesapları.

AAL3 için SMS tek seferlik kodlar kabul edilmez. SMS yalnızca başka kanal
bulunmadığında AAL2 müşteri hesapları için yedek olarak izinlidir; phishing'e
dayanıklılık sağlamaz.

## 4. Parola Politikası (NIST SP 800-63B 2024)

Kontrolör NIST SP 800-63B güncel rehberini izler ve eski "karmaşıklık
tiyatrosu" kurallarını reddeder.

**Zorunlu**

- Asgari uzunluk: insan kullanıcılar için 12 karakter; ayrıcalıklılar için 16;
  iş yükü kimliği kullanamayan servis hesapları için 24.
- Tüm ASCII yazdırılabilir, Unicode ve boşluklar kabul edilmelidir.
- Kayıt ve değişimde gönderimi seçilmiş bir ihlal külliyatına karşı
  kontrol ederek bilinen ele geçmiş parolaları engelle (liste en az ayda bir
  yenilenir).
- Sözlük kelimeleri, bağlama özgü kelimeler (organizasyon adı, ürün adları) ve
  tekrarları engelle.
- Argon2id (RFC 9106), scrypt veya en az 600.000 SHA-256 iterasyonlu PBKDF2 ve
  kimlik bilgisi başına 32 baytlık rastgele tuzla hash'le.
- Hesap veya kaynak IP başına 100 başarısız denemeden sonra hesap kilidi veya
  hız sınırı; CAPTCHA isteğe bağlı, yerine geçmez.

**Yasak**

- Zorunlu periyodik rotasyon. Rotasyon yalnızca şüpheli ihlalde gereklidir.
- Zorunlu karakter kompozisyonu kuralları (örn., bir büyük harf + bir rakam
  + bir sembol).
- Hesapta saklanan parola ipuçları.
- Birincil veya kurtarma faktörü olarak bilgi temelli kimlik doğrulama
  ("annenin kızlık soyadı").
- Hesap AAL3 verisi taşıdığında yalnızca e-posta ile kurtarma.

## 5. Phishing'e Dayanıklı Kimlik Doğrulayıcılar

Phishing'e dayanıklılık, kimlik doğrulayıcı ile dayanıcı taraf arasında
kriptografik bağ kurar; öyle ki röleli bir kimlik bilgisi gerçek hizmette
yeniden kullanılamaz. Kabul edilen formlar:

- FIDO2 / WebAuthn platform kimlik doğrulayıcılar (passkey'ler).
- FIDO2 / WebAuthn dolaşan kimlik doğrulayıcılar (güvenlik anahtarları, örn.
  YubiKey, TitanKey).
- Karşılıklı TLS ile akıllı kartlar (PIV, CAC).
- Donanım destekli anahtarlarla mobil bağlı sertifikalar, dayanıcı tarafa
  kanal bağlı.

OTP uygulamaları (TOTP) phishing'e dayanıklı değildir ancak yalnızca AAL2 için
ikinci faktör olarak kabul edilir.

## 6. Tek Oturum Açma (SSO)

### 6.1 Federasyon Protokolleri

- **SAML 2.0** eski kurumsal uygulamalar için; imzalı beyanlar; imzalı
  yanıtlar; hedef kitle kısıtlaması; azami NotOnOrAfter 5 dakika; SP
  destekliyse şifrelenmiş beyanlar.
- **OpenID Connect 1.0 / OAuth 2.1** yeni uygulamalar için; genel istemciler
  için PKCE'li `code` akışı; gizli sunucu-sunucu yalnızca
  `client_credentials`.
- JWT imza algoritmaları: RS256, ES256, EdDSA. `none` reddedilir. HS256
  yalnızca HSM yönetimli anahtarlarla simetrik dahili kanallar için.

### 6.2 IdP Sıkılaştırma

- IdP yöneticileri acil durum prosedürü ile AAL3'tedir.
- Yönetici eylemleri değiştirilemez depoya loglanır ve haftalık incelenir.
- İK'dan öznitelik eşleme ile just-in-time sağlama.
- Koşullu erişim politikaları cihaz duruşu, konum ve risk skorunu uygular.
- Federasyon meta verisi yenilenir ve imzalanır; güven değişiklikleri değişim
  kontrolünü izler.
- Oturum ömrü: standart kullanıcılar için 8 saat, AAL3 için 4 saat,
  ayrıcalıklı konsollar için 1 saat. Boşta kalma süresi: AAL3 için 30 dakika.
- Token tekrar koruması - refresh token rotasyonu açık; desteklendiği yerde
  token bağlama.

### 6.3 Çıkış

- Desteklendiği yerlerde tek çıkış (ön kanal ve arka kanal).
- Çıkış IdP'deki oturumu ve kullanıcının aktif olduğu tüm federe SP'lerdeki
  oturumları geçersiz kılar.

## 7. Servis Hesabı Hijyeni

Servis hesapları yazılım tarafından kullanılan kimlik bilgileridir, insan
tarafından değil. Büyük veri ihlallerinin en yaygın nedenidir. Kontrolör şunları
uygular:

- Her servis hesabı için kayıtlı bir sahip (kişi ve ekip).
- IAM dizininde kayıtlı belgelenmiş amaç.
- Statik kimlik bilgilerine kıyasla iş yükü kimlikleri (mTLS, SPIFFE, federe
  token'lar, bulut IAM rolleri) tercih edilir.
- Statik kimlik bilgileri kaçınılmazsa:
  - Yalnızca sır yöneticisinde saklanır.
  - Azami her 90 günde bir otomatik döndürülür.
  - Dar kapsamlı (bir amaç, bir ortam).
  - Asla kaynak kontrolüne işlenmez. CI taramaları işlemeyi engeller.
- Etkileşimli giriş yok. Servis hesapları SSO konsollarını kullanamaz.
- Anomali tespiti olağandışı kaynak IP'leri, konumlar, eylem örüntüleri ve
  günün saati kullanımı için izleme.

## 8. Müşteri Kimlik Doğrulama

Müşteri tarafı kimlik doğrulama:

- Kişisel veri taşıyan herhangi bir hesap için asgari AAL2.
- Passkey (FIDO2 / WebAuthn) birincil olarak sunulur; parola + TOTP yedek.
- Hesap kurtarma çoklu kanal doğrulaması (e-posta + telefon) ve yüksek etkili
  eylemlerden önce kalan faktörlerin yeniden doğrulanmasını gerektirir.
- Şu işlemlerden önce yeniden kimlik doğrulama gereklidir:
  - Kayıtlı e-posta veya telefonu değiştirme.
  - Ödeme yöntemi ekleme veya değiştirme.
  - Veri sahibi portalı üzerinden kişisel veri dışa aktarma
    (`09-data-subject-rights/`).
  - Hesabı silme.

## 9. Kimlik Doğrulama Loglama

Her kimlik doğrulama denemesi en azından şunları içeren bir log kaydı üretir:

- Kimlik (mümkünse ham kullanıcı adı yerine özne kimliği).
- Zaman damgası (UTC, RFC 3339, milisaniye).
- Sonuç (başarı, başarısızlık, MFA istemi, MFA başarısızlığı).
- Kullanılan kimlik doğrulayıcı.
- Kaynak IP, ASN, ülke.
- Kullanıcı aracısı / cihaz tanımlayıcısı.
- Verildiyse risk skoru.
- Oturumu bağlayan korelasyon kimliği.

Loglar SIEM'e akar (`logging.md`). Tespit kuralları imkânsız seyahat, parola
sprey, MFA yorgunluğu, kimlik bilgisi doldurma, anormal servis hesabı
etkinliğini kapsar.

## 10. Anti-Otomasyon ve Kötüye Kullanım

- Genel oturum açma akışlarında bot yönetimi.
- Hesap, kaynak IP ve ASN başına hız sınırları.
- MFA yorgunluğu koruması - push için sayı eşleme, tıkla-onayla devre dışı.
- Kullanıcılara şüpheli oturum açma e-postası ve uygulama içi bildirim.
- Hesap kilitleme politikaları yılda iki kez masa başı senaryolarda test
  edilir.

## 11. KPI ve Metrikler

| Metrik | Hedef |
|--------|-------|
| Phishing'e dayanıklı MFA'da ayrıcalıklı hesaplar | %100 |
| MFA'daki iş gücü hesapları | %100 |
| MFA'daki müşteri hesapları (AAL2 kapsamı) | >= %90 benimseme |
| Statik yönetici kimlik bilgileri | 0 |
| Rotasyonu gecikmiş servis hesapları | 0 |
| Tehlikeye giren kimlik bilgisini iptal etme süresi | <= 1 saat |
| Başarısız kimlik doğrulama anomali uyarısı MTTR | <= 4 saat |

## 12. Eşleme

| Gereklilik | NIST 800-63B | ISO 27002:2022 | NIST CSF 2.0 |
|------------|--------------|----------------|--------------|
| AAL2/3 için çok faktörlü | 4.2.2 / 4.3 | 8.5 | PR.AA-2 |
| AAL3 için phishing dayanıklılığı | 4.3 | 8.5 | PR.AA-2 |
| Parola depolama | 5.1.1.2 | 8.24 | PR.DS-1 |
| Kimlik doğrulama loglama | 5.2.10 | 8.15 | DE.CM-1 |
| Oturum yönetimi | 7 | 5.17 | PR.AA-3 |
