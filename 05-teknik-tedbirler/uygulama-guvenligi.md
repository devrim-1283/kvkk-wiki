---
Doküman / Document: Uygulama Güvenliği ve Güvenli Yazılım Geliştirme Yaşam Döngüsü (S-SDLC) Standardı / Application Security and Secure Software Development Lifecycle (S-SDLC) Standard
Bölüm / Section: 05-teknik-tedbirler
Sahip / Owner: AppSec Lideri / CISO / AppSec Lead / CISO
Onaylayan / Approved by: BT Direktörü + Mühendislik Direktörü + KVKK Komitesi / IT Director + Engineering Director + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş (yeni framework, yeni saldırı tipi, ihlal, OWASP Top 10 güncellemesi) / Annual + triggered (new framework, new attack type, breach, OWASP Top 10 update)
İlgili Mevzuat / Legal Reference: Law No. 6698 KVKK Art. 12; Personal Data Security Guide — "IT Systems Procurement, Development, and Maintenance", "Penetration Testing"
İlgili Standart / Standard: ISO/IEC 27001:2022 A.8.25 (Secure Development Life Cycle), A.8.26 (Application Security Requirements), A.8.27 (Secure System Architecture and Engineering Principles), A.8.28 (Secure Coding), A.8.29 (Security Testing in Development and Acceptance), A.8.30 (Outsourced Development), A.8.31 (Separation of Development, Test and Production), A.8.32 (Change Management); OWASP Top 10 (2021), OWASP API Security Top 10 (2023), OWASP LLM Top 10 (2025), OWASP ASVS 4.0; NIST SSDF (SP 800-218); NIST SP 800-204; SLSA Framework; SAFECode; CIS Controls v8 #16
---

## English

# Application Security and S-SDLC

## 1. Purpose

Standardizes the systematic addressing of security at **every stage** of the lifecycle of all software developed or procured. All applications containing personal data are subject to this standard. The direct operationalization of the "IT Systems Procurement, Development, and Maintenance" section of the KVKK Personal Data Security Guide.

## 2. Design Principles

1. **Shift Left:** Security requirements addressed at design/code stage; **not** by post-production patching.
2. **Defense in Depth:** Layers so failure of a single control does not expose data.
3. **Secure by Default:** Default settings are most secure; needs to be "opened", not "closed".
4. **Privacy by Design:** Data minimization, purpose limitation, retention period automatically embedded in the design of applications processing personal data.
5. **Fail Secure:** "Deny by default" in error states.
6. **Trust No Input:** All external input (user, API, file, third party) is validated.
7. **Least Privilege (application):** Service, database, file system permissions minimum.
8. **Auditable:** Every security-relevant event logged (personal data minimized).
9. **Crypto Agility:** Algorithm/parameter from configuration, not code-embedded.
10. **Reproducible Build & Provenance (SLSA):** Production binary traceable, verifiable.

## 3. S-SDLC Phase by Phase

### 3.1. Requirements

- A new project/application starts with **KVKK Impact Assessment (DPIA)** (if high risk — see [06-idari-tedbirler/risk-degerlendirmesi.md](../06-idari-tedbirler/risk-degerlendirmesi.md)).
- Data inventory entry: which personal data, category, retention period, legal basis, transfer.
- ASVS level selection (typically Level 2; Level 3 for special-category or financial).
- Definition of access model and roles.
- Acceptance criteria (security acceptance criteria) written.

### 3.2. Design

- **Threat Modeling** mandatory (new service, critical change). With STRIDE / PASTA / LINDDUN (for privacy) methods.
- Architecture review — AppSec architect attends, personal data flow clarified (data flow diagram).
- Trust boundaries and crossings controls.
- Encryption points (at-rest, in-transit) designed.
- Logging design (including personal data minimization).
- Security evaluation of external dependencies (libraries, APIs, third parties).

### 3.3. Implementation

- Secure coding rules (language-specific guide: OWASP Cheat Sheet, language-specific secure coding standards — CERT, ESAPI, etc.).
- Pre-commit hook: secret scanning (gitleaks, trufflehog), formatter, lint.
- IDE-integrated security plugins (Snyk, SonarLint).
- Code review mandatory (peer + AppSec on files modified).

### 3.4. Test

- **SAST** on every PR.
- **SCA** on every PR + daily re-scan.
- **DAST** nightly run on staging.
- **IAST/RASP** if possible.
- **Secret scanning** on every commit + history.
- **Container scanning** on every image build.
- **Infrastructure-as-Code (IaC) scanning** (Checkov, Trivy, Terrascan).
- **License compliance** within SCA.
- **Manual security review** for critical features.

### 3.5. Deploy

- Signed artifact (Sigstore / cosign).
- Tag-based deployment, immutable image.
- Config diff documented (IaC PR review).
- Gradual rollout with canary / blue-green.
- "Security gates" must be passed before entry to production.

### 3.6. Operations

- Runtime monitoring (RASP/EDR/WAF).
- Up-to-date dependencies (automated PR — Dependabot/Renovate).
- Patch SLA (critical 7 days, high 30 days).
- Periodic penetration test (annual + on major changes).
- Bug bounty (if appropriate).
- Runbook for incident scenarios.

### 3.7. Decommission

- Data destruction (KVKK Art. 7 — see 04-veri-saklama-ve-imha).
- Key destruction (crypto-shred).
- Documentation archive.
- DNS / certificate cleanup.
- Removal of access accounts.

## 4. Threat Modeling

### 4.1. STRIDE

| Category | Meaning | Example |
|----------|-------|-------|
| **S**poofing | Identity impersonation | JWT signing key leaks |
| **T**ampering | Data / code tampering | Unauthorized DB write |
| **R**epudiation | Denial | Audit log missing |
| **I**nformation Disclosure | Disclosure | Error message stack trace |
| **D**enial of Service | Denial of service | Unbounded regex backtracking |
| **E**levation of Privilege | Privilege escalation | IDOR, privilege escalation |

### 4.2. LINDDUN (Privacy)

In systems containing personal data, in addition to STRIDE:

- **L**inkability — can two records be understood as the same person?
- **I**dentifiability — can a person be identified in supposedly anonymous data?
- **N**on-repudiation — user must not be able to deny an action (may conflict with privacy; depends on context).
- **D**etectability — detection of presence of information.
- **D**isclosure of information — unauthorized disclosure.
- **U**nawareness — data subject's lack of awareness of processing.
- **N**on-compliance — KVKK non-compliance.

### 4.3. Process

1. Architecture diagram + data flow diagram ready.
2. Draw trust boundaries.
3. Apply STRIDE/LINDDUN to each component + flow.
4. Score risks (DREAD or CVSS adapted).
5. Design mitigation.
6. Risk Owner accepts residual risk.
7. Document threat model — version controlled (Markdown + diagram).

## 5. OWASP Top 10 (2021) — Quick Checklist

| # | Category | Key Measure |
|---|----------|----------------|
| A01 | Broken Access Control | Authz check per endpoint, IDOR test, default deny |
| A02 | Cryptographic Failures | TLS, at-rest encryption, key management (sifreleme.md) |
| A03 | Injection | Parametric query, ORM, input validation, output encoding |
| A04 | Insecure Design | Threat modeling, secure design patterns |
| A05 | Security Misconfiguration | IaC, baseline, security header, error handling |
| A06 | Vulnerable & Outdated Components | SCA, patch SLA |
| A07 | Identification & Auth Failures | MFA, secure session, password policy |
| A08 | Software & Data Integrity Failures | Signature, dependency pinning, SLSA |
| A09 | Security Logging & Monitoring Failures | Logging design, SIEM |
| A10 | SSRF | Allowlist, metadata service block, network ACL |

## 6. OWASP API Security Top 10 (2023)

| # | Category |
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

API gateway + in-app authz + schema validation + rate limit + inventory — see §10.

## 7. OWASP LLM Top 10 (2025) — AI/ML Components

Additional layer for applications using LLM/agentic features:

- LLM01 Prompt Injection
- LLM02 Insecure Output Handling
- LLM03 Training Data Poisoning
- LLM04 Model Denial of Service
- LLM05 Supply Chain Vulnerabilities
- LLM06 Sensitive Information Disclosure (personal data may leak into training set)
- LLM07 Insecure Plugin Design
- LLM08 Excessive Agency
- LLM09 Overreliance
- LLM10 Model Theft

KVKK perspective: **using personal data as training/fine-tune data** requires a separate legal basis; Art. 4 proportionality + Art. 6 (if special category) additional conditions + privacy notice for the data subject. DPIA for AI systems is **mandatory**.

## 8. Dependency Management (SCA)

- **Allowlist-based** repository (packages only from approved registries).
- **SBOM** (Software Bill of Materials) mandatory — CycloneDX or SPDX.
- Daily scanning against known CVEs with SCA tool (Snyk, GitHub Advanced Security, Trivy, OWASP Dependency-Check).
- Automated dependency PR (Dependabot/Renovate) + pending critical 7 days.
- "Pinned versions" — `=x.y.z` instead of `^x.y.z` (lockfile commit).
- Lockfile review mandatory.
- Exit plan for old / abandoned packages.
- Counter-measures against typosquatting / dependency confusion (private namespace, scope, internal registry).

## 9. Secrets Management

- **In a vault** (HashiCorp Vault, AWS Secrets Manager, Azure Key Vault, GCP Secret Manager).
- Plaintext secrets in code, config, image **forbidden**.
- CI/CD secret variables masked + scoped.
- Pre-commit secret scanning + push protection (GitHub secret scanning).
- Secrets found in history are **immediately rotated**, deleting commits is not enough.
- Short-lived credentials (managed identity / OIDC token) preferred.
- Federated identity instead of static service account secrets.

## 10. API Security

### 10.1. Authentication

- mTLS / OAuth2 / OIDC.
- API key only low-risk + IP allowlist + rate limit.
- JWT: signature algorithm whitelist (RS256/ES256/EdDSA), exp/aud/iss validation, secret never "none".

### 10.2. Authorization

- Authz check per endpoint.
- Object-level (BOLA) — record ownership tested.
- Property-level (BOPLA) — user can only read/write the allowed fields.

### 10.3. Input Validation

- Schema validation (OpenAPI, JSON schema, Zod, Pydantic).
- Whitelist-based (define accepted, reject others).
- Length, type, range, format.

### 10.4. Output Handling

- Output encoding (HTML, JSON, URL).
- Error messages not open — generic + tracking ID.
- Stack trace never to external user.

### 10.5. Rate Limit

- User + IP + endpoint based.
- Sensitive endpoint (login, password reset) strict.
- Anomaly detection.

### 10.6. Inventory

- All endpoints in catalog.
- "Shadow API" scan (those with traffic but undocumented).
- Old versions decommissioned; "zombie API" forbidden.

## 11. Frontend / Browser

- CSP (Content Security Policy) strict.
- HTTP Security headers: HSTS, X-Content-Type-Options, X-Frame-Options/CSP frame-ancestors, Referrer-Policy, Permissions-Policy.
- Cookie: HttpOnly, Secure, SameSite.
- CSRF protection (synchronizer token / SameSite=strict + double submit).
- Subresource Integrity (SRI) for third-party scripts.
- DOM-based XSS scanning.

## 12. SAST / DAST / IAST

| Tool | Stage | Purpose |
|------|-------|------|
| SAST | PR / build | Source code scanning |
| DAST | Staging | Running application external test |
| IAST | Test run | Running application internal view |
| RASP | Production | Runtime defense |
| SCA | PR / nightly | Dependency vulnerabilities |
| Container | Build / registry | Image layer vulnerabilities |
| IaC | PR | Terraform/CFN/K8s manifest issues |

CI gate rules:
- Critical / High vulnerability → build fail.
- Medium → ticket, must close before release.
- Low → backlog.
- Pending exception justified + approved + time-limited.

## 13. Penetration Test

### 13.1. Scope and Frequency

- Annual external penetration test (CREST/OSCP certified, independent third party).
- Annual internal penetration test.
- Additional test after major change / new architecture.
- Targeted test before critical features.
- One-to-one with the KVKK Personal Data Security Guide measure "Performing penetration test."

### 13.2. Methodology

- OWASP Testing Guide / OWASP WSTG.
- PTES (Penetration Testing Execution Standard).
- NIST SP 800-115.

### 13.3. Finding Management

- CVSS v3.1 scoring.
- Closure SLA: critical 30 days, high 60 days, medium 90 days, low annually.
- Validation for re-test required findings.
- Reporting to KVKK Committee (summary, KVKK-scoped findings).

### 13.4. Red Team / Purple Team

- Annual red team exercise (real-world scenario).
- Tests detect/respond (DETECT/RESPOND).
- Results feed back into SOC tuning.

## 14. Bug Bounty

- If maturity level is sufficient (penetration tests routine, IR mature) public/private bug bounty.
- Platform: HackerOne, Bugcrowd, Intigriti.
- Scope, reward schedule, SLA pre-announced.
- KVKK Committee approval, legal safe harbor text.

## 15. Production/Test/Development Environment Separation (A.8.31)

- Three environments physically/logically separated (network, identity, key).
- Production data not written to test/dev (see [veri-maskeleme-anonimlestirme.md](veri-maskeleme-anonimlestirme.md)).
- Developer prod access 0 (JIT + 4-eyes if needed).
- Data labeled by environment (e.g., test logo, banner).

## 16. Change Management (A.8.32)

- All production changes ITSM ticket + approved.
- Standard change (pre-approved) fast track.
- Emergency change (P1) retro document within 24 hours.
- Rollback plan mandatory.
- Documented production change window.

## 17. Outsourced Development (A.8.30)

- Security requirements in contract (SCA, SAST, secrets, code ownership, IP, IR).
- Acceptance test for vendor code (vendor's success is not enough).
- Our right of access (audit, code review).
- See [06-idari-tedbirler/tedarikci-yonetimi.md](../06-idari-tedbirler/tedarikci-yonetimi.md).

## 18. Logging and Monitoring (Application Side)

- Logged: authentication, authorization, sensitive operation, personal data access, error.
- Not logged: password, secret, card, OTP, health data plaintext.
- Format: JSON structured, ECS/OCSF.
- Correlation ID per request.
- Retention (see [log-yonetimi.md](log-yonetimi.md)).

## 19. Container and Cloud-Native

- Trusted base image (distroless, minimal).
- Non-root user, read-only fs, drop capabilities.
- Image signing (cosign), policy (Kyverno, OPA Gatekeeper).
- Network policy default deny.
- Service mesh mTLS.
- Projected volume + vault integration instead of secret as environment.
- Pod Security Standards (restricted) mandatory.

## 20. Security Training (Developer)

- Annual mandatory secure coding training (role-based: backend / frontend / mobile / DevOps / AI).
- "Capture the flag" annual event.
- Module in onboarding for new starters.
- Post-incident "blameless post-mortem" + lessons learned shared with all teams.
- See [06-idari-tedbirler/personel-egitimi.md](../06-idari-tedbirler/personel-egitimi.md).

## 21. Checklist

- [ ] Does new project start with DPIA + threat model?
- [ ] Is the ASVS level defined in the project requirement document?
- [ ] Are SAST + SCA + secret scanning + container scan + IaC scan mandatory in CI?
- [ ] Is DAST staging nightly run?
- [ ] Do Critical/High findings build fail?
- [ ] Is the patch SLA (critical 7d, high 30d) tracked?
- [ ] Is SBOM produced for every release?
- [ ] Are dependencies pinned in lockfile?
- [ ] Are secrets in vault, not in code?
- [ ] Is API inventory current, is shadow API scanning done?
- [ ] Is per-endpoint authz testing done (BOLA/BOPLA)?
- [ ] Is the full set of HTTP security headers applied?
- [ ] Is annual external + internal penetration test done?
- [ ] Is the production/test/dev separation clear, developer prod access 0?
- [ ] Is production data masked when written to test?
- [ ] For new AI features, is there LLM Top 10 + DPIA + additional privacy notice?
- [ ] Is the container non-root + read-only + signed?
- [ ] Is log content personal data minimized (sanitization)?
- [ ] Is the annual developer security training completed?
- [ ] Are security clauses in the outsourced development contract?
- [ ] Is the bug bounty / responsible disclosure channel defined?

## 22. Maturity Model (BSIMM/SAMM summary)

Our progression target toward the levels below:

- Level 1: Annual penetration test, basic CI scans, secret vault.
- Level 2: Threat modeling, ASVS-compliant testing, SBOM.
- Level 3: Privacy by design integrated, AI risk management, SLSA Level 3, mature bug bounty.

Our level is measured with annual review and roadmap is updated.

---

## Türkçe

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
