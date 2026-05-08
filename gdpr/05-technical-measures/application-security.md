---
title:
  en: "Application Security - Privacy by Design, Secure SDLC, OWASP, Threat Modelling, SAST/DAST/SCA, SBOM, Pen Test"
  tr: "Uygulama Güvenliği - Tasarımdan Gizlilik, Güvenli SDLC, OWASP, Tehdit Modelleme, SAST/DAST/SCA, SBOM, Pentest"
section: "05-technical-measures"
document_type: "control_policy"
control_id: "TECH-APPSEC-01"
owner:
  primary: "CISO"
  secondary: "Head of Engineering"
review_cycle: "annual"
last_review: "2026-05-08"
next_review: "2027-05-08"
classification: "Internal"
language: ["en", "tr"]
references:
  - "GDPR Art. 5, 24, 25, 32"
  - "ISO/IEC 27002:2022 controls 8.25, 8.26, 8.27, 8.28, 8.29, 8.30"
  - "NIST CSF 2.0 PR.PS, ID.RA, PR.DS, DE.CM"
  - "NIST SSDF (SP 800-218)"
  - "OWASP ASVS 5.0, OWASP Top 10 2021, OWASP API Top 10 2023, OWASP LLM Top 10 2025, OWASP SAMM"
  - "Microsoft STRIDE; LINDDUN privacy threat modelling"
  - "EO 14028 SBOM guidance; CycloneDX, SPDX"
---

## English

# Application Security and Privacy by Design

## 1. Purpose

GDPR Article 25 mandates "data protection by design and by default": the
controller must implement appropriate technical and organisational measures
"both at the time of the determination of the means for processing and at
the time of the processing itself." Article 32 extends this to security
throughout the processing lifecycle. This document codifies the secure
software development lifecycle (SSDLC) and the engineering controls that
implement those obligations.

## 2. Privacy by Design Principles

Operational principles applied at every design step:

1. **Proactive not reactive** - the privacy harm and security weakness are
   anticipated and prevented before they occur.
2. **Privacy as the default setting** - no action is required from the data
   subject to obtain a privacy-preserving default.
3. **Privacy embedded into design** - not a bolt-on.
4. **Full functionality** - positive sum: privacy and functionality together.
5. **End-to-end security** - the data is protected from the first point of
   collection to deletion.
6. **Visibility and transparency** - subject to verification.
7. **Respect for user privacy** - keep the user-centric focus.

These map directly to GDPR Article 25(2) "by default" requirements: only
necessary data processed, only necessary purposes, only necessary retention,
only necessary access.

## 3. Secure SDLC

Each phase has explicit privacy and security gates:

### 3.1 Requirements
- Privacy use cases captured alongside functional requirements.
- Lawful basis identified for each new processing activity (`02-ropa/`).
- Data classification noted for every field.
- Triggers for DPIA evaluated (`06-organizational-measures/dpia.md`).
- Security and privacy acceptance criteria written into stories.

### 3.2 Design
- Threat modelling (Section 4).
- LINDDUN privacy threat modelling on personal-data flows.
- Architecture review with security architect.
- Cryptographic design referenced to `encryption.md`.
- Identity and authorisation design referenced to `access-control.md` and
  `authentication.md`.

### 3.3 Build
- Secure coding standards (OWASP ASVS 5.0).
- Pre-commit hooks blocking secrets and high-severity SAST findings.
- Code review by a non-author for every merge.
- Pair / mob programming on T4-T5 components recommended.

### 3.4 Test
- SAST in CI - blocking on critical, gating on high.
- SCA on every build.
- DAST in nightly pipeline against staging.
- IaC scanning on infrastructure changes.
- Container image scanning at build and at registry pull.
- Unit tests covering security cases.

### 3.5 Release
- Manual approval for production (separation of duties with build engineer).
- Cryptographic signing of artefacts.
- SBOM generated and stored for every release.
- Change record with privacy impact summary.

### 3.6 Operate
- Runtime application self-protection where applicable.
- Continuous vulnerability scanning.
- Continuous compliance monitoring.
- Telemetry to SIEM (`logging.md`).
- Incident response readiness (`08-breach-management/`).

### 3.7 Decommission
- Data archival or deletion per `04-retention-erasure/`.
- Media sanitisation per `backup-recovery.md` Section 9.
- Removal of credentials, keys, accounts.
- Documentation update.

## 4. Threat Modelling

Two complementary methodologies:

### 4.1 STRIDE (Security)
- Spoofing
- Tampering
- Repudiation
- Information disclosure
- Denial of service
- Elevation of privilege

### 4.2 LINDDUN (Privacy)
- Linkability
- Identifiability
- Non-repudiation
- Detectability
- Disclosure of information
- Unawareness
- Non-compliance

LINDDUN is run for any new system processing personal data, with output
feeding the DPIA when triggered.

Threat models are stored alongside code, reviewed at each major change, and
referenced from the design record.

## 5. OWASP Coverage

### 5.1 OWASP Top 10 2021 (Web)
A01 Broken Access Control; A02 Cryptographic Failures; A03 Injection;
A04 Insecure Design; A05 Security Misconfiguration; A06 Vulnerable and
Outdated Components; A07 Identification and Authentication Failures;
A08 Software and Data Integrity Failures; A09 Security Logging and Monitoring
Failures; A10 SSRF.

### 5.2 OWASP API Security Top 10 2023
API1 BOLA; API2 Broken Authentication; API3 BOPLA; API4 Unrestricted Resource
Consumption; API5 BFLA; API6 Unrestricted Access to Sensitive Business Flows;
API7 SSRF; API8 Security Misconfiguration; API9 Improper Inventory Management;
API10 Unsafe Consumption of APIs.

### 5.3 OWASP LLM Top 10 2025
LLM01 Prompt Injection; LLM02 Sensitive Information Disclosure; LLM03 Supply
Chain; LLM04 Data and Model Poisoning; LLM05 Improper Output Handling;
LLM06 Excessive Agency; LLM07 System Prompt Leakage; LLM08 Vector and
Embedding Weaknesses; LLM09 Misinformation; LLM10 Unbounded Consumption.

### 5.4 ASVS Levels
- L1 - opportunistic baseline. Public marketing surfaces.
- L2 - applications handling sensitive personal data (default for in-scope).
- L3 - high-risk: payment, health, special categories, critical infrastructure.

Compliance level documented per system; gaps tracked.

## 6. Static and Dynamic Analysis

### 6.1 SAST
- Scans on every PR.
- Languages covered align with the codebase.
- Findings tracked in the security backlog with SLA:
  - Critical: 7 days
  - High: 30 days
  - Medium: 90 days
  - Low: best effort
- Suppressions require justification, owner and review date.

### 6.2 SCA
- Manifest and lockfile scanning at build time.
- License compliance check.
- Direct and transitive dependency CVEs surfaced.
- SLA same as SAST; auto-PRs for routine bumps.

### 6.3 DAST
- Authenticated scans against staging weekly.
- API spec-driven scanning where OpenAPI / GraphQL schemas exist.
- High and critical findings block release until remediated or risk-
  accepted by CISO.

### 6.4 IAST and Runtime
- Where supported, runtime instrumentation correlates SAST findings with
  exercised code paths during testing to reduce false positives.

### 6.5 Container and IaC
- Image scanning at build, registry, and admission.
- IaC scanning (Terraform, CloudFormation) catches misconfiguration before
  deployment.
- Policy as code (OPA / Conftest) enforces architectural standards.

## 7. SBOM and Software Supply Chain

- SBOM generated for every release in CycloneDX or SPDX format.
- SBOM stored alongside the artefact and signed.
- Vulnerabilities matched against SBOM continuously; alerts tied to release
  inventory.
- Build pipelines reproducible where feasible; SLSA level documented per
  system.
- Provenance attestations for build-system-produced artefacts.
- Vendor SBOMs requested as part of due diligence
  (`06-organizational-measures/vendor-management.md`).

## 8. Secrets Management

- Centralised secrets manager (HashiCorp Vault / cloud secret manager / KMS-
  backed).
- No secrets in source control. CI scans and pre-commit hooks block.
- Application reads secrets at runtime via short-lived tokens or workload
  identity.
- Secret rotation:
  - Application secrets: maximum 90 days.
  - Database passwords: maximum 90 days.
  - Service account keys: 90 days unless replaceable by workload identity.
  - Third-party API tokens: rotate per vendor policy and on personnel change.
- On compromise: revoke, rotate, audit usage, post-incident review.

## 9. API Security

- Versioned APIs with deprecation policy.
- Authentication on every endpoint (no implicit zero-auth routes).
- Authorisation evaluated against the requested object (BOLA prevention).
- Rate limiting per identity, per endpoint, per IP.
- Input validation against published schemas.
- Output validation for personal data exposure (returning only what is
  asked).
- Pagination caps to prevent unbounded enumeration.
- Idempotency keys for write operations.
- Logging per `logging.md` with redaction of sensitive fields.

## 10. Mobile and Frontend

- Certificate pinning where the threat model justifies it.
- Secure storage on device for credentials (Keychain / Keystore).
- Jailbreak / root detection where high-impact data is stored locally.
- Subresource integrity for third-party scripts.
- Strict Content Security Policy.
- Cookies: `Secure`, `HttpOnly`, `SameSite=Lax`/`Strict` per case.
- HSTS with preload.
- Referrer Policy strict-origin-when-cross-origin.
- Permissions Policy restricting unused browser capabilities.

## 11. AI / LLM Components

For systems integrating LLMs or autonomous agents:

- Prompt injection mitigations - input segregation, structured tool use,
  policy enforcement on outputs.
- Sensitive information disclosure controls - retrieval scoping, tenant
  isolation, output redaction.
- Tool / function calling restricted to the minimum necessary, with strong
  authorisation on each tool invocation.
- Logging of prompts, retrievals, tool calls and responses with retention
  reviewed for personal data minimisation.
- Output handling - never trust model output; validate before downstream
  action; treat output as untrusted input.
- Supply-chain controls on model weights, fine-tuning data, embeddings.
- Evaluation and red-team for the OWASP LLM Top 10.

## 12. Penetration Testing

- Annual pen test by a qualified independent provider for each in-scope
  application and infrastructure perimeter.
- Additional pen test on every major change (architecture change, new
  authentication system, new public surface, mergers and acquisitions).
- Scope agreed in writing; rules of engagement documented; data handling
  conditions enforced (`07-international-transfers/` if test data crosses
  borders).
- Findings remediated per SLA above; retest performed.
- Results filed in `11-audit-compliance/evidence/`.
- Bug bounty programme considered for public-facing services.

## 13. Acceptance Testing for Privacy

Before go-live for processing involving personal data:

- Confirm data minimisation in production schemas.
- Confirm retention rules in operational deletion jobs.
- Confirm consent / lawful basis enforcement at point of capture.
- Confirm data subject right paths function end-to-end
  (`09-data-subject-rights/`).
- Confirm logging proportionate and tamper-evident (`logging.md`).
- Confirm encryption (`encryption.md`).
- Confirm vendor / processor coverage where applicable
  (`06-organizational-measures/vendor-management.md`).

## 14. KPIs

| Metric | Target |
|--------|--------|
| Critical SAST findings remediation within SLA | >= 95 % |
| SCA critical / high vulnerabilities open > SLA | 0 |
| Releases with signed SBOM | 100 % |
| Threat models for in-scope systems | 100 %, refreshed yearly or on change |
| Pen test findings remediated within SLA | >= 95 % |
| Secrets in source control | 0 |
| LINDDUN executed for new personal-data systems | 100 % |
| ASVS L2 coverage for in-scope systems | 100 % |

## 15. Mapping

| Requirement | ISO 27002:2022 | NIST CSF 2.0 |
|-------------|----------------|--------------|
| Secure development life cycle | 8.25 | PR.PS-1 |
| Application security requirements | 8.26 | PR.PS-1 |
| Secure system architecture and engineering | 8.27 | PR.PS-1 |
| Secure coding | 8.28 | PR.PS-1 |
| Security testing in development | 8.29 | PR.PS-1 |
| Outsourced development | 8.30 | PR.PS-1, GV.SC |

---

## Türkçe

# Uygulama Güvenliği ve Tasarımdan Gizlilik

## 1. Amaç

GDPR Madde 25 "tasarımdan ve varsayılan olarak veri korumasını" zorunlu
kılar: kontrolör "işleme araçlarının belirlenmesi sırasında ve işlemenin
kendisi sırasında" uygun teknik ve organizasyonel tedbirleri uygulamalıdır.
Madde 32 bunu işleme yaşam döngüsü boyunca güvenliğe genişletir. Bu belge
güvenli yazılım geliştirme yaşam döngüsünü (SSDLC) ve bu yükümlülükleri
uygulayan mühendislik kontrollerini kodlar.

## 2. Tasarımdan Gizlilik İlkeleri

Her tasarım adımında uygulanan operasyonel ilkeler:

1. **Reaktif değil proaktif** - gizlilik zararı ve güvenlik zayıflığı oluşmadan
   önce öngörülür ve önlenir.
2. **Varsayılan ayar olarak gizlilik** - gizliliği koruyan bir varsayılan
   elde etmek için veri sahibinden eylem gerekmez.
3. **Tasarıma gömülü gizlilik** - sonradan eklenmez.
4. **Tam işlevsellik** - pozitif toplam: gizlilik ve işlevsellik birlikte.
5. **Uçtan uca güvenlik** - veri ilk toplama noktasından silmeye kadar
   korunur.
6. **Görünürlük ve şeffaflık** - doğrulamaya tabi.
7. **Kullanıcı gizliliğine saygı** - kullanıcı merkezli odaklanmayı koru.

Bunlar doğrudan GDPR Madde 25(2) "varsayılan olarak" gerekliliklerine
eşlenir: yalnızca gerekli veri işlenir, yalnızca gerekli amaçlar, yalnızca
gerekli saklama, yalnızca gerekli erişim.

## 3. Güvenli SDLC

Her aşama açık gizlilik ve güvenlik kapılarına sahiptir:

### 3.1 Gereksinimler
- Gizlilik kullanım senaryoları işlevsel gereksinimlerle birlikte
  yakalanır.
- Her yeni işleme etkinliği için yasal dayanak tanımlanır (`02-ropa/`).
- Her alan için veri sınıflandırması notu.
- VKD tetikleyicileri değerlendirilir (`06-organizational-measures/dpia.md`).
- Hikayelerde güvenlik ve gizlilik kabul kriterleri yazılır.

### 3.2 Tasarım
- Tehdit modelleme (Bölüm 4).
- Kişisel-veri akışlarında LINDDUN gizlilik tehdit modelleme.
- Güvenlik mimarıyla mimari inceleme.
- `encryption.md`'ye referansla kriptografik tasarım.
- `access-control.md` ve `authentication.md`'ye referansla kimlik ve
  yetkilendirme tasarımı.

### 3.3 Yapım
- Güvenli kodlama standartları (OWASP ASVS 5.0).
- Sırları ve yüksek ciddiyetli SAST bulgularını engelleyen pre-commit
  kancaları.
- Her birleştirme için yazar olmayan biri tarafından kod incelemesi.
- T4-T5 bileşenlerinde pair / mob programlama önerilir.

### 3.4 Test
- CI'da SAST - kritikte engelleyici, yüksekte kapı.
- Her yapımda SCA.
- Gece boru hattında staging'e karşı DAST.
- Altyapı değişikliklerinde IaC taraması.
- Yapım ve kayıt çekme zamanında konteyner görüntü taraması.
- Güvenlik durumlarını kapsayan birim testleri.

### 3.5 Yayım
- Üretim için manuel onay (yapım mühendisi ile görev ayrımı).
- Yapıların kriptografik imzası.
- Her yayım için SBOM üretilir ve saklanır.
- Gizlilik etki özetli değişim kaydı.

### 3.6 İşlet
- Geçerli olduğu yerde çalışma zamanı uygulama öz koruması.
- Sürekli zafiyet taraması.
- Sürekli uyumluluk izleme.
- SIEM'e telemetri (`logging.md`).
- Olay müdahalesi hazırlığı (`08-breach-management/`).

### 3.7 Hizmet Dışı Bırakma
- `04-retention-erasure/` uyarınca veri arşivleme veya silme.
- `backup-recovery.md` Bölüm 9 uyarınca ortam temizliği.
- Kimlik bilgileri, anahtarlar, hesapların kaldırılması.
- Belge güncellemesi.

## 4. Tehdit Modelleme

İki tamamlayıcı metodoloji:

### 4.1 STRIDE (Güvenlik)
- Taklit
- Müdahale
- Reddetme
- Bilgi açıklama
- Hizmet reddi
- Ayrıcalık yükseltme

### 4.2 LINDDUN (Gizlilik)
- Bağlanabilirlik
- Tanımlanabilirlik
- Reddedememe
- Algılanabilirlik
- Bilgi açıklama
- Farkındasızlık
- Uyumsuzluk

LINDDUN kişisel veri işleyen herhangi bir yeni sistem için çalıştırılır;
çıktısı tetiklendiğinde VKD'yi besler.

Tehdit modelleri kodla birlikte saklanır, her büyük değişiklikte incelenir
ve tasarım kaydından referans verilir.

## 5. OWASP Kapsamı

### 5.1 OWASP Top 10 2021 (Web)
A01 Bozuk Erişim Kontrolü; A02 Kriptografik Hatalar; A03 Enjeksiyon;
A04 Güvensiz Tasarım; A05 Güvenlik Yanlış Konfigürasyonu; A06 Zafiyetli ve
Eski Bileşenler; A07 Tanımlama ve Kimlik Doğrulama Hataları; A08 Yazılım
ve Veri Bütünlüğü Hataları; A09 Güvenlik Loglama ve İzleme Hataları;
A10 SSRF.

### 5.2 OWASP API Security Top 10 2023
API1 BOLA; API2 Bozuk Kimlik Doğrulama; API3 BOPLA; API4 Kısıtlanmamış
Kaynak Tüketimi; API5 BFLA; API6 Hassas İş Akışlarına Kısıtlanmamış Erişim;
API7 SSRF; API8 Güvenlik Yanlış Konfigürasyonu; API9 Uygunsuz Envanter
Yönetimi; API10 API'lerin Güvensiz Tüketimi.

### 5.3 OWASP LLM Top 10 2025
LLM01 Prompt Enjeksiyonu; LLM02 Hassas Bilgi Açıklama; LLM03 Tedarik
Zinciri; LLM04 Veri ve Model Zehirleme; LLM05 Uygunsuz Çıktı İşleme;
LLM06 Aşırı Yetki; LLM07 Sistem Prompt Sızıntısı; LLM08 Vektör ve Embedding
Zayıflıkları; LLM09 Yanlış Bilgi; LLM10 Sınırlanmamış Tüketim.

### 5.4 ASVS Seviyeleri
- L1 - fırsatçı temel. Genel pazarlama yüzeyleri.
- L2 - hassas kişisel veri işleyen uygulamalar (kapsam dahili için
  varsayılan).
- L3 - yüksek risk: ödeme, sağlık, özel kategoriler, kritik altyapı.

Uyumluluk seviyesi sistem başına belgelenir; boşluklar izlenir.

## 6. Statik ve Dinamik Analiz

### 6.1 SAST
- Her PR'da taramalar.
- Kapsanan diller kod tabanıyla hizalı.
- Bulgular SLA ile güvenlik birikim listesinde izlenir:
  - Kritik: 7 gün
  - Yüksek: 30 gün
  - Orta: 90 gün
  - Düşük: en iyi çaba.
- Bastırmalar gerekçe, sahip ve inceleme tarihi gerektirir.

### 6.2 SCA
- Yapım zamanında manifest ve lockfile taraması.
- Lisans uyumluluk kontrolü.
- Doğrudan ve geçişli bağımlılık CVE'leri yüzeye çıkarılır.
- SLA SAST ile aynı; rutin yükseltmeler için otomatik PR'lar.

### 6.3 DAST
- Staging'e karşı haftalık kimlik doğrulamalı taramalar.
- OpenAPI / GraphQL şemaları olduğunda API spec odaklı tarama.
- Yüksek ve kritik bulgular düzeltilene veya CISO tarafından risk kabul
  edilene kadar yayını engeller.

### 6.4 IAST ve Çalışma Zamanı
- Desteklendiği yerde, çalışma zamanı enstrümantasyonu test sırasında
  yürütülen kod yollarını SAST bulgularıyla ilişkilendirir, yanlış pozitifleri
  azaltır.

### 6.5 Konteyner ve IaC
- Yapım, kayıt ve kabulde görüntü taraması.
- IaC taraması (Terraform, CloudFormation) yanlış konfigürasyonu dağıtımdan
  önce yakalar.
- Kod olarak politika (OPA / Conftest) mimari standartları uygular.

## 7. SBOM ve Yazılım Tedarik Zinciri

- Her yayım için CycloneDX veya SPDX formatında SBOM üretilir.
- SBOM yapı ile birlikte saklanır ve imzalanır.
- Zafiyetler SBOM'a karşı sürekli eşleştirilir; uyarılar yayım envanterine
  bağlanır.
- Mümkün olduğunda yapım hatları yeniden üretilebilir; sistem başına SLSA
  seviyesi belgelenir.
- Yapım sistemi tarafından üretilen yapılar için kaynak beyanları.
- Sağlayıcı SBOM'ları durum tespitinin parçası olarak istenir
  (`06-organizational-measures/vendor-management.md`).

## 8. Sır Yönetimi

- Merkezi sır yöneticisi (HashiCorp Vault / bulut sır yöneticisi / KMS
  destekli).
- Kaynak kontrolünde sır yok. CI taramaları ve pre-commit kancaları engeller.
- Uygulama çalışma zamanında kısa ömürlü tokenlar veya iş yükü kimliği
  aracılığıyla sırları okur.
- Sır rotasyonu:
  - Uygulama sırları: azami 90 gün.
  - Veritabanı parolaları: azami 90 gün.
  - Servis hesabı anahtarları: iş yükü kimliği ile değiştirilebilir
    olmadıkça 90 gün.
  - Üçüncü taraf API tokenları: sağlayıcı politikasına göre ve personel
    değişikliğinde döndürülür.
- İhlalde: iptal et, döndür, kullanımı denetle, olay sonrası inceleme.

## 9. API Güvenliği

- Kullanım dışı bırakma politikası olan sürümlü API'ler.
- Her uç noktada kimlik doğrulama (örtük sıfır kimlik doğrulamalı rota yok).
- İstenen nesneye karşı değerlendirilen yetkilendirme (BOLA önleme).
- Kimlik, uç nokta, IP başına hız sınırlama.
- Yayımlanmış şemalara karşı girdi doğrulama.
- Kişisel veri maruziyetinde çıktı doğrulama (yalnızca istenenin
  döndürülmesi).
- Sınırlanmamış sayımı önlemek için sayfalama sınırları.
- Yazma işlemleri için idempotency anahtarları.
- `logging.md` uyarınca hassas alanların maskelenmesiyle loglama.

## 10. Mobil ve Frontend

- Tehdit modelinin haklı çıkardığı yerde sertifika sabitleme.
- Cihazda kimlik bilgileri için güvenli depolama (Keychain / Keystore).
- Yüksek etkili veri yerel olarak saklandığında jailbreak / root algılama.
- Üçüncü taraf scriptler için alt kaynak bütünlüğü.
- Sıkı İçerik Güvenlik Politikası.
- Çerezler: duruma göre `Secure`, `HttpOnly`, `SameSite=Lax`/`Strict`.
- Preload ile HSTS.
- Referrer Policy strict-origin-when-cross-origin.
- Kullanılmayan tarayıcı yeteneklerini kısıtlayan İzin Politikası.

## 11. AI / LLM Bileşenleri

LLM'leri veya otonom ajanları entegre eden sistemler için:

- Prompt enjeksiyonu hafifletme - girdi ayrımı, yapılandırılmış araç
  kullanımı, çıktılarda politika uygulaması.
- Hassas bilgi açıklama kontrolleri - geri alma kapsamı, kiracı izolasyonu,
  çıktı maskeleme.
- Araç / fonksiyon çağrısı her araç çağrısında güçlü yetkilendirme ile
  asgari gerekli olana sınırlanır.
- Prompt'ları, geri alımları, araç çağrılarını ve yanıtları kişisel veri
  minimizasyonu için saklama incelenmiş olarak loglama.
- Çıktı işleme - model çıktısına asla güvenme; alt akış eylemden önce
  doğrula; çıktıyı güvenilmez girdi olarak ele al.
- Model ağırlıkları, ince ayar verisi, embedding'ler üzerinde tedarik
  zinciri kontrolleri.
- OWASP LLM Top 10 için değerlendirme ve kırmızı takım.

## 12. Sızma Testi

- Kapsam dahili her uygulama ve altyapı perimetresi için nitelikli bağımsız
  sağlayıcı tarafından yıllık sızma testi.
- Her büyük değişiklikte ek sızma testi (mimari değişikliği, yeni kimlik
  doğrulama sistemi, yeni genel yüzey, birleşmeler ve devralmalar).
- Yazılı olarak kabul edilen kapsam; belgelenen katılım kuralları; uygulanan
  veri işleme koşulları (test verisi sınırı geçerse
  `07-international-transfers/`).
- Yukarıdaki SLA başına düzeltilen bulgular; yeniden test gerçekleştirilir.
- Sonuçlar `11-audit-compliance/evidence/` altında dosyalanır.
- Genel hizmetler için bug bounty programı değerlendirilir.

## 13. Gizlilik İçin Kabul Testi

Kişisel veri içeren işleme için canlıya almadan önce:

- Üretim şemalarında veri minimizasyonunu doğrula.
- Operasyonel silme işlerinde saklama kurallarını doğrula.
- Yakalama noktasında onay / yasal dayanak uygulamasını doğrula.
- Veri sahibi hakkı yollarının uçtan uca işlediğini doğrula
  (`09-data-subject-rights/`).
- Loglamanın orantılı ve müdahale-kanıtlı olduğunu doğrula (`logging.md`).
- Şifrelemeyi doğrula (`encryption.md`).
- Geçerli olduğunda sağlayıcı / işleyici kapsamını doğrula
  (`06-organizational-measures/vendor-management.md`).

## 14. KPI'lar

| Metrik | Hedef |
|--------|-------|
| SLA içinde kritik SAST bulguları düzeltme | >= %95 |
| SLA üzerinde açık SCA kritik / yüksek zafiyetler | 0 |
| İmzalı SBOM ile yayımlar | %100 |
| Kapsam dahili sistemler için tehdit modelleri | %100, yıllık veya değişimde yenilenir |
| SLA içinde düzeltilen sızma testi bulguları | >= %95 |
| Kaynak kontrolündeki sırlar | 0 |
| Yeni kişisel-veri sistemleri için yürütülen LINDDUN | %100 |
| Kapsam dahili sistemler için ASVS L2 kapsamı | %100 |

## 15. Eşleme

| Gereklilik | ISO 27002:2022 | NIST CSF 2.0 |
|------------|----------------|--------------|
| Güvenli geliştirme yaşam döngüsü | 8.25 | PR.PS-1 |
| Uygulama güvenliği gereksinimleri | 8.26 | PR.PS-1 |
| Güvenli sistem mimarisi ve mühendisliği | 8.27 | PR.PS-1 |
| Güvenli kodlama | 8.28 | PR.PS-1 |
| Geliştirmede güvenlik testi | 8.29 | PR.PS-1 |
| Dış kaynak geliştirme | 8.30 | PR.PS-1, GV.SC |
