---
Doküman: Uygulama Güvenliği ve Güvenli Yazılım Geliştirme Yaşam Döngüsü (S-SDLC) Standardı
Bölüm: 05-teknik-tedbirler
Sahip: AppSec Lideri / CISO
Onaylayan: BT Direktörü + Mühendislik Direktörü + KVKK Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (yeni framework, yeni saldırı tipi, ihlal, OWASP Top 10 güncellemesi)
İlgili Mevzuat: 6698 sayılı KVKK m.12; Kişisel Veri Güvenliği Rehberi — "Bilgi Teknolojileri Sistemleri Tedariği, Geliştirilmesi ve Bakımı", "Sızma Testi"
İlgili Standart: ISO/IEC 27001:2022 A.8.25 (Secure Development Life Cycle), A.8.26 (Application Security Requirements), A.8.27 (Secure System Architecture and Engineering Principles), A.8.28 (Secure Coding), A.8.29 (Security Testing in Development and Acceptance), A.8.30 (Outsourced Development), A.8.31 (Separation of Development, Test and Production), A.8.32 (Change Management); OWASP Top 10 (2021), OWASP API Security Top 10 (2023), OWASP LLM Top 10 (2025), OWASP ASVS 4.0; NIST SSDF (SP 800-218); NIST SP 800-204; SLSA Framework; SAFECode; CIS Controls v8 #16
---

# Uygulama Güvenliği ve S-SDLC

## 1. Amaç

Geliştirilen veya tedarik edilen tüm yazılımların yaşam döngüsünün **her aşamasında** güvenliğin sistematik olarak ele alınmasını standardize eder. Kişisel veri içeren tüm uygulamalar bu standarda tabidir. KVKK Veri Güvenliği Rehberi'nin "Bilgi Teknolojileri Sistemleri Tedariği, Geliştirilmesi ve Bakımı" bölümünün doğrudan operasyonelleştirilmesidir.

## 2. Tasarım İlkeleri

1. **Shift Left:** Güvenlik gereksinimleri tasarım/kod aşamasında ele alınır; üretim sonrası yamayla **değil**.
2. **Defense in Depth:** Tek bir kontrolün başarısız olmasının veriyi açığa çıkarmaması için katmanlar.
3. **Secure by Default:** Varsayılan ayarlar en güvenli; "açmak" gerekecek, "kapamak" değil.
4. **Privacy by Design:** Kişisel veri işleyen uygulama tasarımında veri minimizasyonu, amaç sınırlaması, saklama süresi otomatik gömülü.
5. **Fail Secure:** Hata durumlarında "deny by default".
6. **Trust No Input:** Tüm dış girdi (kullanıcı, API, dosya, üçüncü taraf) doğrulanır.
7. **Least Privilege (uygulama):** Servis, veritabanı, dosya sistemi yetkileri minimum.
8. **Auditable:** Güvenlik açısından önemli her olay loglanır (kişisel veri minimize).
9. **Crypto Agility:** Algoritma/parametre kod-gömülü değil, konfigürasyondan.
10. **Reproducible Build & Provenance (SLSA):** Üretim binary'si izlenebilir, doğrulanabilir.

## 3. S-SDLC Faz Faz

### 3.1. Gereksinim (Requirements)

- Yeni proje/uygulama, **KVKK Etki Değerlendirmesi (DPIA)** ile başlar (yüksek riskli ise — bkz. [06-idari-tedbirler/risk-degerlendirmesi.md](../06-idari-tedbirler/risk-degerlendirmesi.md)).
- Veri envanteri girişi: hangi kişisel veri, kategorisi, saklama süresi, yasal dayanak, aktarım.
- ASVS seviyesi seçimi (genelde Level 2; özel nitelikli veya finansal için Level 3).
- Erişim modeli ve roller tanımı.
- Kabul kriterleri (security acceptance criteria) yazılır.

### 3.2. Tasarım (Design)

- **Tehdit Modelleme** zorunlu (yeni servis, kritik değişiklik). STRIDE / PASTA / LINDDUN (gizlilik için) yöntemleriyle.
- Mimari review — AppSec mimarı katılır, kişisel veri akışı netleştirilir (data flow diagram).
- Trust boundary'ler ve crossing'lerin kontrolleri.
- Şifreleme noktaları (at-rest, in-transit) tasarlanır.
- Logging tasarımı (kişisel veri minimizasyon dahil).
- Dış bağımlılıkların güvenlik değerlendirmesi (kütüphaneler, API'ler, üçüncü taraf).

### 3.3. Geliştirme (Implementation)

- Secure coding kuralları (dil bazlı kılavuz: OWASP Cheat Sheet, dilin secure coding standardı — CERT, ESAPI vb.).
- Pre-commit hook: secret scanning (gitleaks, trufflehog), formatter, lint.
- IDE entegre güvenlik plugin'leri (Snyk, SonarLint).
- Code review zorunlu (peer + AppSec'ın değiştirdiği dosyalarda).

### 3.4. Test

- **SAST** her PR'da.
- **SCA** her PR + günlük yeniden tarama.
- **DAST** staging'de gece run.
- **IAST/RASP** mümkünse.
- **Secret scanning** her commit + history.
- **Container scanning** her image build.
- **Infrastructure-as-Code (IaC) scanning** (Checkov, Trivy, Terrascan).
- **License compliance** SCA içinde.
- **Manual security review** kritik feature için.

### 3.5. Deploy

- İmzalı artifact (Sigstore / cosign).
- Tag-based deployment, immutable image.
- Konfig farkı dökümante (IaC PR review).
- Canary / blue-green ile gradual rollout.
- Production'a giriş için "security gates" geçilmiş olmalı.

### 3.6. Operasyon

- Runtime izleme (RASP/EDR/WAF).
- Bağımlılık güncel (otomatik PR — Dependabot/Renovate).
- Patch SLA (kritik 7 gün, yüksek 30 gün).
- Periyodik sızma testi (yıllık + büyük değişikliklerde).
- Bug bounty (uygunsa).
- Olay senaryoları için runbook.

### 3.7. Decommission

- Veri imhası (KVKK m.7 — bkz. 04-veri-saklama-ve-imha).
- Anahtar imhası (crypto-shred).
- Dokümantasyon arşivi.
- DNS / sertifika temizliği.
- Erişim hesapları kaldırma.

## 4. Tehdit Modelleme

### 4.1. STRIDE

| Kategori | Anlam | Örnek |
|----------|-------|-------|
| **S**poofing | Kimlik taklidi | JWT signing key sızar |
| **T**ampering | Veri / kod tahrifi | Yetkisiz DB write |
| **R**epudiation | İnkar | Audit log eksik |
| **I**nformation Disclosure | İfşa | Hata mesajı stack trace |
| **D**enial of Service | Hizmet engelleme | Sınırsız regex backtracking |
| **E**levation of Privilege | Yetki yükseltme | IDOR, privilege escalation |

### 4.2. LINDDUN (Privacy)

Kişisel veri içeren sistemlerde STRIDE'a ek olarak:

- **L**inkability — iki kayıt aynı kişi mi anlaşılabiliyor?
- **I**dentifiability — anonim sayılan veride kişi belirlenebilir mi?
- **N**on-repudiation — kullanıcı bir eylemi inkar edememeli (gizlilikle çelişebilir; bağlama göre).
- **D**etectability — bilgi varlığının tespiti.
- **D**isclosure of information — yetkisiz ifşa.
- **U**nawareness — ilgili kişinin işlemden haberdar olmaması.
- **N**on-compliance — KVKK uyumsuzluk.

### 4.3. Süreç

1. Mimari diyagram + data flow diagram hazır.
2. Trust boundary çiz.
3. Her bileşen + akış için STRIDE/LINDDUN uygula.
4. Riskleri puanla (DREAD veya CVSS adapte).
5. Mitigation tasarla.
6. Artık riski Risk Owner kabul eder.
7. Doküman tehdit modeli — versiyon kontrollü (Markdown + diyagram).

## 5. OWASP Top 10 (2021) — Hızlı Kontrol Listesi

| # | Kategori | Anahtar Tedbir |
|---|----------|----------------|
| A01 | Broken Access Control | Her endpoint için authz kontrolü, IDOR testi, default deny |
| A02 | Cryptographic Failures | TLS, at-rest şifreleme, anahtar yönetimi (sifreleme.md) |
| A03 | Injection | Parametrik sorgu, ORM, input validation, output encoding |
| A04 | Insecure Design | Tehdit modelleme, secure design patterns |
| A05 | Security Misconfiguration | IaC, baseline, security header, error handling |
| A06 | Vulnerable & Outdated Components | SCA, patch SLA |
| A07 | Identification & Auth Failures | MFA, secure session, password policy |
| A08 | Software & Data Integrity Failures | Imza, dependency pinning, SLSA |
| A09 | Security Logging & Monitoring Failures | Logging tasarımı, SIEM |
| A10 | SSRF | Allowlist, metadata service block, network ACL |

## 6. OWASP API Security Top 10 (2023)

| # | Kategori |
|---|----------|
| API1 | Broken Object Level Authorization (BOLA / IDOR) |
| API2 | Broken Authentication |
| API3 | Broken Object Property Level Authorization |
| API4 | Unrestricted Resource Consumption |
| API5 | Broken Function Level Authorization |
| API6 | Unrestricted Access to Sensitive Business Flows |
| API7 | Server Side Request Forgery |
| API8 | Security Misconfiguration |
| API9 | Improper Inventory Management |
| API10 | Unsafe Consumption of APIs |

API gateway + uygulama içi authz + şema doğrulama + rate limit + envanter — bkz. §10.

## 7. OWASP LLM Top 10 (2025) — AI/ML Bileşenler

LLM/agentic özellik kullanan uygulamalar için ek katman:

- LLM01 Prompt Injection
- LLM02 Insecure Output Handling
- LLM03 Training Data Poisoning
- LLM04 Model Denial of Service
- LLM05 Supply Chain Vulnerabilities
- LLM06 Sensitive Information Disclosure (kişisel veri eğitim setine sızabilir)
- LLM07 Insecure Plugin Design
- LLM08 Excessive Agency
- LLM09 Overreliance
- LLM10 Model Theft

KVKK perspektifi: **eğitim/fine-tune verisi olarak kişisel veri kullanılması** ayrı hukuki dayanak gerektirir; m.4 ölçülülük + m.6 (özel nitelikli ise) ek koşulları + ilgili kişiye aydınlatma. AI sistemlerinin DPIA'sı **zorunludur**.

## 8. Bağımlılık Yönetimi (SCA)

- **Allowlist tabanlı** repository (paket sadece onaylı registry'den).
- **SBOM** (Software Bill of Materials) zorunlu — CycloneDX veya SPDX.
- Bilinen CVE'lere karşı SCA aracı (Snyk, GitHub Advanced Security, Trivy, OWASP Dependency-Check) günlük tarama.
- Otomatik dependency PR (Dependabot/Renovate) + bekleyen kritik 7 gün.
- "Pinned versions" — `^x.y.z` yerine `=x.y.z` (lockfile commit).
- Lockfile review zorunlu.
- Eski / abandoned paketler için exit planı.
- Typosquatting / dependency confusion karşı önlem (özel namespace, scope, internal registry).

## 9. Sırların Yönetimi (Secrets Management)

- **Kasada** (HashiCorp Vault, AWS Secrets Manager, Azure Key Vault, GCP Secret Manager).
- Kod, config, image içinde plaintext sırrı **yasak**.
- CI/CD secret değişkenleri masked + scope'lu.
- Pre-commit secret scanning + push protection (GitHub secret scanning).
- History'de bulunan sırlar **derhal döndürülür**, commit silinmesi yetmez.
- Kısa ömürlü kimlik bilgisi (managed identity / OIDC token) tercih edilir.
- Service account static secret yerine federated identity.

## 10. API Güvenliği

### 10.1. Authentication

- mTLS / OAuth2 / OIDC.
- API key sadece düşük riskli + IP allowlist + rate limit.
- JWT: imza algoritması whitelist (RS256/ES256/EdDSA), exp/aud/iss doğrulama, secret asla "none".

### 10.2. Authorization

- Endpoint başına authz kontrolü.
- Object-level (BOLA) — kayıt sahipliği test edilir.
- Property-level (BOPLA) — kullanıcı sadece izin verilen alanları okuyup yazabilir.

### 10.3. Input Validation

- Schema validation (OpenAPI, JSON schema, Zod, Pydantic).
- Whitelist tabanlı (kabul edilenleri tanımla, reddet diğerlerini).
- Length, type, range, format.

### 10.4. Output Handling

- Output encoding (HTML, JSON, URL).
- Hata mesajları açık değil — generic + tracking ID.
- Stack trace asla dış kullanıcıya.

### 10.5. Rate Limit

- Kullanıcı + IP + endpoint bazlı.
- Hassas endpoint (login, password reset) sıkı.
- Anomaly detection.

### 10.6. Envanter

- Tüm endpoint'ler katalogda.
- "Shadow API" tarama (trafiği olan ama dokümante olmayan).
- Eski sürümler decommission edilir; "zombie API" yasaktır.

## 11. Frontend / Browser

- CSP (Content Security Policy) sıkı.
- HTTP Security headers: HSTS, X-Content-Type-Options, X-Frame-Options/CSP frame-ancestors, Referrer-Policy, Permissions-Policy.
- Cookie: HttpOnly, Secure, SameSite.
- CSRF protection (synchronizer token / SameSite=strict + double submit).
- Subresource Integrity (SRI) third-party scriptler için.
- DOM-based XSS taraması.

## 12. SAST / DAST / IAST

| Araç | Aşama | Amaç |
|------|-------|------|
| SAST | PR / build | Kaynak kod taraması |
| DAST | Staging | Çalışan uygulama dış test |
| IAST | Test koşumu | Çalışan uygulama içsel görünüm |
| RASP | Production | Runtime savunma |
| SCA | PR / nightly | Bağımlılık zafiyetleri |
| Container | Build / registry | Image katman zafiyetleri |
| IaC | PR | Terraform/CFN/K8s manifest yanlışları |

CI gate kuralları:
- Critical / High zafiyet → build fail.
- Medium → ticket, sürüm öncesi kapanmalı.
- Low → backlog.
- Bekleyen istisna gerekçeli + onaylı + süreli.

## 13. Sızma Testi

### 13.1. Kapsam ve Sıklık

- Yıllık dış sızma testi (CREST/OSCP sertifikalı, bağımsız üçüncü taraf).
- Yıllık iç sızma testi.
- Büyük değişiklik / yeni mimari sonrası ek test.
- Kritik feature öncesi targeted test.
- KVKK Veri Güvenliği Rehberi — "Sızma testi alınması" tedbiriyle birebir.

### 13.2. Metodoloji

- OWASP Testing Guide / OWASP WSTG.
- PTES (Penetration Testing Execution Standard).
- NIST SP 800-115.

### 13.3. Bulgu Yönetimi

- CVSS v3.1 puanlama.
- Kapanma SLA: kritik 30 gün, yüksek 60 gün, orta 90 gün, düşük yıllık.
- Re-test gerektiren bulgular için doğrulama.
- KVKK Komitesine raporlama (özet, KVKK kapsamlı bulgu).

### 13.4. Red Team / Purple Team

- Yıllık red team egzersizi (gerçek dünya senaryosu).
- Tespit/yanıt (DETECT/RESPOND) test eder.
- Sonuçlar SOC tunning'e geri besler.

## 14. Bug Bounty

- Olgunluk seviyesi yeterli ise (sızma testleri rutinleşmiş, IR olgunlaşmış) public/private bug bounty.
- Platform: HackerOne, Bugcrowd, Intigriti.
- Scope, ödül cetveli, SLA önceden duyurulur.
- KVKK Komitesi onayı, hukuk safe harbor metni.

## 15. Üretim/Test/Geliştirme Ortam Ayrımı (A.8.31)

- Üç ortam fiziksel/mantıksal olarak ayrı (ağ, kimlik, anahtar).
- Üretim verisi test/dev'e yazılmaz (bkz. [veri-maskeleme-anonimlestirme.md](veri-maskeleme-anonimlestirme.md)).
- Geliştirici prod erişimi 0 (gerekirse JIT + 4-eyes).
- Veriler ortam etiketli (örn. test logo, banner).

## 16. Change Management (A.8.32)

- Tüm üretim değişikliği ITSM ticket + onay.
- Standart değişiklik (ön onaylı) hızlı yol.
- Acil değişiklik (P1) 24 saat içinde retro doküman.
- Rollback planı zorunlu.
- Üretim değişiklik penceresi yazılı.

## 17. Outsourced Development (A.8.30)

- Sözleşmede güvenlik gereksinimleri (SCA, SAST, secrets, code ownership, IP, IR).
- Tedarikçi kodu için kabul testi (üreticinin başarısı yetmez).
- Bizim erişim hakkımız (audit, kod inceleme).
- Bkz. [06-idari-tedbirler/tedarikci-yonetimi.md](../06-idari-tedbirler/tedarikci-yonetimi.md).

## 18. Logging ve İzleme (Uygulama Tarafı)

- Loglanan: kimlik doğrulama, yetki, hassas işlem, kişisel veri erişimi, hata.
- Loglanmayan: parola, secret, kart, OTP, sağlık verisi düz metin.
- Format: JSON yapısal, ECS/OCSF.
- Korelasyon ID her istek.
- Saklama (bkz. [log-yonetimi.md](log-yonetimi.md)).

## 19. Konteyner ve Bulut-Native

- Trusted base image (distroless, minimal).
- Non-root user, read-only fs, drop capabilities.
- Image imzalama (cosign), policy (Kyverno, OPA Gatekeeper).
- Network policy default deny.
- Service mesh mTLS.
- Secret olarak environment yerine projected volume + kasa entegrasyonu.
- Pod Security Standards (restricted) zorunlu.

## 20. Güvenlik Eğitimi (Geliştirici)

- Yıllık zorunlu güvenli kodlama eğitimi (rol bazlı: backend / frontend / mobile / DevOps / AI).
- "Capture the flag" yıllık etkinlik.
- Yeni başlayan onboarding'de modül.
- Olay sonrası "blameless post-mortem" + lessons learned tüm ekiple paylaşılır.
- Bkz. [06-idari-tedbirler/personel-egitimi.md](../06-idari-tedbirler/personel-egitimi.md).

## 21. Kontrol Listesi

- [ ] Yeni proje DPIA + tehdit modeli ile mi başlıyor?
- [ ] ASVS seviyesi proje gereksinim dokümanında belirli mi?
- [ ] CI'da SAST + SCA + secret scanning + container scan + IaC scan zorunlu mu?
- [ ] DAST staging gece koşumu var mı?
- [ ] Critical/High bulgular build fail ediyor mu?
- [ ] Patch SLA (kritik 7g, yüksek 30g) takip ediliyor mu?
- [ ] SBOM her release için üretiliyor mu?
- [ ] Bağımlılıklar lockfile'da pin'li mi?
- [ ] Sırlar kasada, kodda yok mu?
- [ ] API envanter güncel, shadow API tarama yapılıyor mu?
- [ ] Endpoint başına authz kontrolü test edilmiş mi (BOLA/BOPLA)?
- [ ] HTTP security headers tam set uygulanıyor mu?
- [ ] Yıllık dış + iç sızma testi yapılıyor mu?
- [ ] Üretim/Test/Dev ayrımı net, geliştirici prod erişimi 0 mı?
- [ ] Üretim verisi test'e maskeli yazılıyor mu?
- [ ] Yeni AI özelliği için LLM Top 10 + DPIA + ek aydınlatma var mı?
- [ ] Konteyner non-root + read-only + signed mi?
- [ ] Log içeriği kişisel veri minimize mi (sanitization)?
- [ ] Yıllık geliştirici güvenlik eğitimi tamamlandı mı?
- [ ] Outsourced development sözleşmesinde güvenlik maddeleri var mı?
- [ ] Bug bounty / responsible disclosure kanalı tanımlı mı?

## 22. Olgunluk Modeli (BSIMM/SAMM özeti)

Aşağıdaki seviyelere doğru ilerleyiş hedefimizdir:

- Seviye 1: Yıllık sızma testi, temel CI taramaları, secret kasası.
- Seviye 2: Tehdit modelleme, ASVS uyumlu test, SBOM.
- Seviye 3: Privacy by design entegre, AI risk yönetimi, SLSA Level 3, bug bounty olgun.

Yıllık review ile seviyemiz ölçülür ve yol haritası güncellenir.
