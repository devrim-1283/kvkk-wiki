---
title:
  en: "Artificial Intelligence and Large Language Models"
  tr: "Yapay Zekâ ve Büyük Dil Modelleri"
section: "10-special-topics"
document_id: "ST-AI-001"
owner: "DPO Office / AI Governance / CISO"
classification: "Internal"
version: "1.0"
last_review: "2026-05-08"
next_review: "2027-05-08"
language: ["en", "tr"]
references:
  - "EU AI Act — Regulation (EU) 2024/1689"
  - "GDPR Art. 5, 6, 9, 13, 14, 22, 25, 32, 35"
  - "GDPR Recitals 71, 75"
  - "EDPB Opinion 28/2024 on certain data protection aspects related to the processing of personal data in the context of AI models"
  - "EDPB Statement 03/2024 on data protection and AI"
  - "OWASP Top 10 for Large Language Model Applications (2025)"
  - "NIST AI Risk Management Framework (AI RMF 1.0, 2023)"
  - "ISO/IEC 42001:2023 — AI management system"
  - "ISO/IEC 23894:2023 — AI risk management"
  - "ISO/IEC 23053:2022 — Framework for AI systems using ML"
  - "Italian Garante — ChatGPT decisions (2023, 2024)"
  - "CNIL — AI plan and several recommendations (2023–2025)"
  - "Hamburg DPA — LLM training data opinion"
---

## English

### 1. Two regulatory layers

AI systems that process personal data sit at the intersection of two layers:

- **GDPR** — applies whenever personal data is processed at any stage (training, evaluation, inference, output).
- **EU AI Act (Regulation 2024/1689)** — applies to AI systems and general-purpose AI models placed on the market or put into service in the EU, regardless of whether personal data is processed.

The two regimes are complementary, not alternative. EDPB Statement 03/2024 reaffirms that compliance with one does not displace the other.

### 2. AI Act risk classification

The AI Act establishes four risk classes plus a general-purpose AI model regime:

| Class | Examples | Obligations |
|-------|---------|------------|
| Prohibited (Art. 5) | Subliminal manipulation, exploitation of vulnerabilities, social scoring by public authorities, real-time remote biometric ID in public spaces by LE (subject to narrow exceptions), emotion recognition in workplaces and education, untargeted scraping of facial images from internet/CCTV, biometric categorisation inferring sensitive attributes, predictive policing based on profiling | Banned |
| High-risk (Art. 6, Annex III) | Biometric ID and categorisation, critical infrastructure, education, employment, essential services and benefits eligibility, law enforcement, migration/asylum/border, justice/democratic processes, plus AI as safety component of products | Conformity assessment, risk management, data governance, technical documentation, transparency, human oversight, accuracy/robustness/cybersecurity, registration in EU database |
| Limited risk (Art. 50) | Chatbots; emotion-recognition or biometric categorisation systems in non-prohibited cases; deepfake generation | Transparency to users |
| Minimal risk | Spam filters, video games | Voluntary codes of conduct |
| GPAI models (Art. 51–55) | Foundation models like GPT-class, Llama-class, Claude-class | Transparency, copyright compliance, GPAI summary; systemic-risk models additionally: model evaluations, incident reporting, cybersecurity |

### 3. AI Act application timeline (key dates)

- 2 February 2025: prohibitions and AI literacy obligations apply.
- 2 August 2025: GPAI rules and governance start.
- 2 August 2026: most other obligations including high-risk start.
- 2 August 2027: high-risk AI as product safety component fully applies.

The controller plans roadmap accordingly, especially for any high-risk classifications.

### 4. GDPR principles applied to AI

| Principle | AI translation |
|-----------|----------------|
| Lawfulness | Lawful basis at every stage: training, fine-tuning, evaluation, inference, output use |
| Fairness | Bias testing across demographics; mitigation; transparency about residual fairness limits |
| Transparency | Inform data subjects of training-data role, inference logic at meaningful level (Art. 13(2)(f), 14(2)(g), 15(1)(h)) |
| Purpose limitation | Specify purposes for the model and resist scope creep |
| Data minimisation | Train on the minimum necessary; pseudonymise where possible; consider synthetic data |
| Accuracy | Model output that concerns a person is personal data; right to rectification engages |
| Storage limitation | Retention rules apply to training data and inference logs |
| Integrity and confidentiality | Security tailored to AI-specific threats |
| Accountability | Documentation, governance, oversight |

### 5. Lawful basis for training

Training a model on personal data requires a lawful basis. Common options:

- **Consent (Art. 6(1)(a))**: clean but rarely scalable for general-purpose corpora.
- **Contract (Art. 6(1)(b))**: where training is necessary for the contract — e.g. on the customer's own data, with documented purpose limitation.
- **Legal obligation (Art. 6(1)(c))**: rare for AI training.
- **Legitimate interest (Art. 6(1)(f))**: requires a specific Legitimate Interest Assessment showing the necessity of using personal data, the proportionality, and the absence of less-intrusive alternatives. EDPB Opinion 28/2024 sets a high bar.

For Article 9 special-category data, an Article 9(2) basis is additionally required. Most commonly (a) explicit consent (rare for training corpora) or (e) made manifestly public (highly contested for scraped social media). EDPB Opinion 28/2024 stresses caution.

### 6. Web-scraped training data

Many foundation models are trained on web-scraped corpora. Legal posture:

- Personal data on the open web remains personal data.
- "Manifestly made public" (Article 9(2)(e)) does not apply broadly to scraped content.
- Hamburg DPA position (2023) suggested LLM weights may not always store personal data identifiably; subsequent EDPB Opinion 28/2024 disagrees in part: parameters of a model can constitute personal data when individuals can be identified from outputs.
- Italian Garante's 2023 ChatGPT order required transparency, age gating, opt-out, and other measures.
- The transparency obligation under Art. 13/14 applies to data not collected from the data subject (Art. 14); LLMs have struggled with this.

Operational rule: do not assume web-availability legitimises training. Conduct an LIA, restrict scraping to clearly public-interest content where possible, exclude high-risk categories, and provide an opt-out and rectification path for affected individuals.

### 7. Model output as personal data

EDPB Opinion 28/2024 affirms that model outputs that name an individual or describe identifiable attributes are personal data. This means:

- Article 16 rectification applies to false outputs about a person (the "I asked the LLM about you and it said X falsely" problem).
- Article 17 erasure applies in principle, although technical implementation is hard for parameters; the controller may need to retrain or apply targeted unlearning techniques where feasible.
- Article 22 may apply if the output drives a significant decision.

The controller establishes a process for receiving and acting on rectification requests for outputs.

### 8. Article 22 — automated decision-making

Article 22(1) gives the data subject the right not to be subject to a decision based solely on automated processing, including profiling, which produces legal effects or similarly significantly affects them. Exceptions:

- (a) necessary for entering into or performance of a contract;
- (b) authorised by EU/MS law providing suitable safeguards;
- (c) explicit consent.

Even in exception cases, the controller must implement safeguards: at least the right to human intervention, to express the data subject's point of view, and to contest the decision (Article 22(3)).

For special categories, Article 22(4) restricts to (a) explicit consent or (g) substantial public interest with safeguards.

Recital 71 provides additional context: meaningful human review, regular checks for accuracy and bias, prevention of discriminatory effects.

### 9. Transparency obligations

Articles 13(2)(f), 14(2)(g), and 15(1)(h) require the controller to inform the data subject of:
- the existence of automated decision-making, including profiling;
- meaningful information about the logic involved;
- the significance and the envisaged consequences for the data subject.

EDPB and supervisory authority guidance interprets "meaningful information about the logic" as not requiring proprietary algorithms but requiring an honest functional description: what inputs are used, what kinds of inferences are drawn, where the limitations lie, what role human review plays.

### 10. AI Act high-risk obligations

For high-risk AI systems (Annex III):

- Risk management system across the lifecycle (Art. 9).
- Data governance and management (Art. 10): training, validation, test data with appropriate quality, representativeness, statistical properties; bias examination; data minimisation.
- Technical documentation (Art. 11) and Annex IV.
- Record-keeping / automatic logs (Art. 12).
- Transparency to deployers (Art. 13).
- Human oversight (Art. 14).
- Accuracy, robustness, and cybersecurity (Art. 15).
- Conformity assessment (Art. 43).
- Registration (Art. 49) in the EU database.
- Post-market monitoring (Art. 72) and serious incident reporting (Art. 73).

Roles: provider (develops and places on market), deployer (uses), importer, distributor. Most controllers as deployers carry obligations under Art. 26.

### 11. ChatGPT / Claude / Gemini employee usage policy

Employees inevitably use commercial LLMs for work. Without governance, prompts may include:
- customer personal data;
- employee data;
- trade secrets;
- regulated content (health, legal advice).

Operational policy:

| Item | Rule |
|------|------|
| Approved tools | Only listed tools with enterprise contracts and DPAs (e.g. ChatGPT Enterprise, Claude for Enterprise, Gemini for Workspace, Copilot for Microsoft 365) |
| Prohibited tools | Free consumer tiers; tools without DPA; uncontrolled APIs |
| Permitted prompts | Public-information research, code assistance on non-sensitive code, drafting non-sensitive text |
| Prohibited prompts | Customer personal data, employee personal data beyond the user's own, Article 9 special-category data, trade secrets, source code with secrets, regulated client matter |
| Output handling | Verify factual claims; do not paste output into customer-facing artefacts without review |
| Logging | Enterprise tier with retention controls |
| Training | Mandatory annual; case studies of leaks |
| Detection | DLP rules to detect personal data in prompts where feasible; anomaly detection |
| Incident | Treat prompt leakage as a potential breach; investigate per `08-breach-management` |

### 12. Prompt leakage and exfiltration risks

Categories of leakage:

| Risk | Description |
|------|-------------|
| User prompt leakage | Confidential data in a prompt persisted by the model provider, possibly used for training |
| Model output leakage | The model outputs verbatim or near-verbatim training data containing personal data |
| Cross-tenant leakage | A multi-tenant model returns one tenant's data to another |
| Side-channel leakage | Latency, embedding patterns, or other signals reveal private information |
| Memory leakage | Long-context or memory features retain data beyond the intended session |
| Plugin leakage | Tools and plugins call external systems; data flows out |

Mitigations:
- Prefer enterprise contracts with no-training commitments.
- Self-host or use private deployments for highly sensitive workloads.
- Strict prompt scrubbing before sending to providers.
- DLP integration.
- Vendor security reviews including known evaluations of memorisation and leakage.

### 13. OWASP Top 10 for LLM Applications (2025)

OWASP Top 10 for LLM Applications 2025:

1. **LLM01: Prompt Injection** — direct or indirect injection of instructions that override the system prompt.
2. **LLM02: Sensitive Information Disclosure** — model divulges PII, proprietary data, secrets.
3. **LLM03: Supply Chain** — risks in models, datasets, and dependencies.
4. **LLM04: Data and Model Poisoning** — adversarial training data or fine-tuning.
5. **LLM05: Improper Output Handling** — passing model output to downstream systems without sanitisation.
6. **LLM06: Excessive Agency** — agents with too much capability or autonomy.
7. **LLM07: System Prompt Leakage** — exposure of system prompts that may contain sensitive logic.
8. **LLM08: Vector and Embedding Weaknesses** — embedding inversion, retrieval data leakage.
9. **LLM09: Misinformation** — hallucinated or low-quality outputs.
10. **LLM10: Unbounded Consumption** — denial-of-service / cost exhaustion.

Each maps to GDPR concerns: LLM02, LLM07, LLM08 implicate confidentiality of personal data; LLM04 implicates accuracy and integrity; LLM09 implicates accuracy and rectification rights.

### 14. NIST AI RMF

NIST AI RMF 1.0 (2023) structures AI risk management around four functions: GOVERN, MAP, MEASURE, MANAGE. It is aligned with risk-based principles in the AI Act and complementary to GDPR Article 35 DPIA. Many controllers use NIST AI RMF as the operational backbone for AI governance, with mapping to AI Act and GDPR obligations.

### 15. ISO/IEC 42001

ISO/IEC 42001:2023 is an AI Management System standard, structured like ISO 27001. It covers:
- AI policy and objectives;
- planning of AI risks and opportunities;
- support (resources, competence, awareness, communication, documented information);
- operation;
- performance evaluation;
- improvement.

Certification provides assurance to deployers, regulators, and customers. Many enterprises pursue 27001 + 42001 + (where applicable) 27701 jointly.

### 16. On-prem and private deployment

For sensitive workloads, options include:
- on-premises model hosting (open-weights models like Llama, Mistral);
- private cloud deployment (Azure OpenAI Service with private endpoints; AWS Bedrock with private endpoints; GCP Vertex AI);
- dedicated tenancy with no-training commitments;
- inference at the edge.

Private deployment reduces transfer-mechanism complexity and gives the controller more control. It does not eliminate compliance obligations: lawful basis, transparency, accuracy, security all apply.

### 17. DLP for AI

Data loss prevention adapted to AI:
- inspection of outbound prompts;
- redaction or block of detected personal data;
- vendor-side controls (Azure Content Filters, vendor PII detectors);
- prompt taxonomy: low / medium / high risk;
- routing: high-risk prompts only to private deployments;
- audit log of prompts and responses for security review.

### 18. Explainability

Article 13(2)(f), 14(2)(g), 15(1)(h) require meaningful information about the logic. For complex models:
- functional description rather than weights;
- key features used in inference;
- typical scenarios where the model performs well or poorly;
- limits and known failure modes;
- routes to human review.

For high-risk under AI Act, additional documentation is mandated. Local explanations (LIME, SHAP) for individual decisions support data subject rights.

### 19. DPIA for AI

DPIA mandatory under Article 35 for:
- systematic and extensive evaluation of personal aspects (profiling) producing legal/significant effects;
- large-scale processing of special categories;
- systematic monitoring of public spaces;
- new technologies — AI is on every Member State SA's blacklist for this criterion.

The DPIA addresses:
- model lifecycle (training data, evaluation data, ongoing inference);
- bias and fairness;
- accuracy and limitations;
- security threats (prompt injection, model extraction, membership inference, model inversion);
- transparency;
- rights handling (rectification of outputs, erasure where feasible);
- consultation with stakeholders;
- residual risk and acceptance.

### 20. Records of processing for AI

ROPA entries for AI activities should include:
- model name, version, provider;
- training data sources and lawful basis;
- inference inputs (prompts) and outputs;
- recipients;
- transfers (often to US providers; transfer mechanism noted);
- retention of prompts and outputs;
- automated decision-making flag and Article 22 analysis if applicable.

### 21. Vendor due diligence

For each AI vendor:
- DPA with no-training commitments where required;
- transfer mechanism;
- model card / system card with risk disclosures;
- evaluation reports (capability, safety, fairness);
- incident notification SLA;
- audit rights or third-party assurance reports;
- data processing locations;
- secure development lifecycle evidence;
- penetration testing including AI-specific tests.

### 22. Specific risks and patterns

#### 22.1 Customer support chatbots

Often Article 22 if they decide on refunds, eligibility, support priority. Provide human escalation; document the logic; bias-test on customer demographics.

#### 22.2 CV screening

High-risk under AI Act (Annex III). Article 22 typically. Bias testing required across protected characteristics. Right of objection from candidates.

#### 22.3 Fraud detection

Often legitimate interest under GDPR; high-risk under AI Act if used for essential services. Article 22 applies for refusal decisions; provide human review.

#### 22.4 Generative content

Transparency to users (Article 50 AI Act): synthetic content must be marked. Personal data in generated content is the controller's responsibility.

#### 22.5 Coding assistants

Risks: source code containing personal data sent to providers; output containing memorised personal data. Use enterprise tier; restrict on highly sensitive repositories; configure with code-only retention.

#### 22.6 Document and email summarisation

Personal data in documents enters the model context. Use enterprise tier with no-training; retention controls; access logs.

### 23. Children and AI

AI Act prohibits AI systems that exploit vulnerabilities of children. AI services directed to children require Article 8 GDPR consent regime. Profiling of children for advertising or significant decisions is restricted.

### 24. Worker representation

For AI systems used in employment context (recruitment, performance, monitoring), Member State labour law often requires consultation with worker representatives or works councils prior to deployment. Article 88 GDPR layered with Member State law.

### 25. KVKK and Türkiye context

KVKK uygulanır. KVK Kurulu, AI sistemleri için kararlar yayımlamaktadır ve ChatGPT'ye karşı belirli yaptırımlar (Türkiye'de erişim kısıtlamaları dahil) tarihsel olarak bildirilmiştir. Türkiye'nin kendi AI politikası belgesi (Ulusal Yapay Zeka Stratejisi 2021–2025) yönergeler sağlar.

KVKK Madde 4 ve Madde 5, AI işleme için tabandır; Madde 11 hakları AI sistemlerinin çıktıları için geçerlidir.

### 26. Incident response specific to AI

AI-specific incident scenarios:
- model extraction attack (someone steals the model via API);
- training data extraction (membership inference, attribute inference);
- prompt injection that exfiltrates data;
- backdoor or poisoning of fine-tuning data;
- model degradation producing systematic errors;
- agentic system taking unauthorised actions.

Each scenario interacts with the breach management procedures in section `08-breach-management`. The DPIA pre-defines response runbooks.

### 27. Documentation pack

For each AI system:
- DPIA;
- Article 6 / Article 9 / Article 22 analysis;
- AI Act risk classification with reasoning;
- model / system card;
- ROPA entry;
- bias and fairness evaluation;
- transparency notice content;
- human oversight design;
- security tests;
- vendor contracts and assurance;
- incident scenarios and runbooks;
- post-deployment monitoring plan.

### 28. Quarterly AI governance review

The DPO and AI Governance lead jointly review:
- AI inventory completeness;
- new use cases (formal intake);
- DPIA backlog and refresh cadence;
- vendor list changes;
- incident learnings;
- regulatory developments;
- training records.

The output feeds the executive committee quarterly.

### 29. AI literacy obligation (AI Act Art. 4)

From 2 February 2025, providers and deployers of AI systems shall take measures to ensure, to their best extent, a sufficient level of AI literacy of their staff. The controller maintains:
- AI literacy curriculum;
- role-based modules (executives, technical staff, end-users);
- completion records;
- annual refresh.

### 30. Closure principle

AI systems amplify both capability and risk. The controller's posture is principled adoption: clear use cases, documented basis and impact, bounded autonomy, robust oversight, evidence on file. The default for any new AI use case is a structured intake (DPIA + AI Act classification + LIA where applicable) before deployment, and ongoing review thereafter.

---

## Türkçe

### 1. İki düzenleyici katman

Kişisel veri işleyen AI sistemleri iki katmanın kesişiminde oturur:

- **GDPR** — kişisel verinin herhangi bir aşamada işlendiğinde uygulanır.
- **AB AI Yasası (Düzenleme 2024/1689)** — AB'de pazara sunulan veya hizmete alınan AI sistemlerine ve genel amaçlı AI modellerine, kişisel verinin işlenip işlenmediğine bakılmaksızın uygulanır.

### 2. AI Yasası risk sınıflandırması

| Sınıf | Örnekler | Yükümlülükler |
|-------|----------|---------------|
| Yasak (Madde 5) | Subliminal manipülasyon, zayıflıkların sömürülmesi, kamu otoriteleri tarafından sosyal puanlama, kolluk tarafından kamuya açık alanlarda gerçek zamanlı uzak biyometrik kimlik, işyerlerinde ve eğitimde duygu tanıma, internetten/CCTV'den hedefsiz yüz görüntüsü kazıma, hassas özellikleri çıkarsayan biyometrik kategorizasyon, profillemeye dayalı öngörücü polislik | Yasaklı |
| Yüksek riskli (Madde 6, Annex III) | Biyometrik kimlik ve kategorizasyon, kritik altyapı, eğitim, istihdam, temel hizmetler ve fayda uygunluğu, kolluk, göç/sığınma/sınır, adalet/demokratik süreçler, ürünlerin güvenlik bileşeni olarak AI | Uygunluk değerlendirmesi, risk yönetimi, veri yönetişimi, teknik dokümantasyon, şeffaflık, insan denetimi, doğruluk/dayanıklılık/siber güvenlik, AB veritabanına kayıt |
| Sınırlı risk (Madde 50) | Sohbet robotları, deepfake oluşturma | Kullanıcılara şeffaflık |
| Minimum risk | Spam filtreleri, video oyunları | Gönüllü davranış kuralları |
| GPAI modelleri (Madde 51-55) | GPT, Llama, Claude sınıfı temel modeller | Şeffaflık, telif hakkı uyumluluğu, GPAI özeti; sistemik risk modelleri ek olarak: model değerlendirmeleri, olay raporlama, siber güvenlik |

### 3. AI Yasası uygulama takvimi (anahtar tarihler)

- 2 Şubat 2025: yasaklamalar ve AI okuryazarlığı yükümlülükleri uygulanır.
- 2 Ağustos 2025: GPAI kuralları ve yönetişim başlar.
- 2 Ağustos 2026: yüksek riskli dahil olmak üzere diğer yükümlülükler başlar.
- 2 Ağustos 2027: ürün güvenliği bileşeni olarak yüksek riskli AI tam olarak uygulanır.

### 4. AI'ya uygulanan GDPR ilkeleri

| İlke | AI çevirisi |
|------|------------|
| Hukuka uygunluk | Her aşamada hukuki temel: eğitim, ince ayar, değerlendirme, çıkarım, çıktı kullanımı |
| Adillik | Demografi arası önyargı testi; azaltma; kalan adillik sınırları hakkında şeffaflık |
| Şeffaflık | İlgili kişileri eğitim verisi rolü, çıkarım mantığı hakkında anlamlı bir düzeyde bilgilendir (Madde 13(2)(f), 14(2)(g), 15(1)(h)) |
| Amaç sınırlaması | Modelin amaçlarını belirt ve kapsam genişlemesine direnme |
| Veri minimizasyonu | Mümkünse minimum üzerinde eğit; mümkünse takma adlandır; sentetik veri düşün |
| Doğruluk | Bir kişiyle ilgili model çıktısı kişisel veridir; düzeltme hakkı devreye girer |
| Saklama sınırlaması | Saklama kuralları eğitim verisine ve çıkarım günlüklerine uygulanır |
| Bütünlük ve gizlilik | AI'ya özgü tehditlere uyarlanmış güvenlik |
| Hesap verebilirlik | Belgeleme, yönetişim, denetim |

### 5. Eğitim için hukuki temel

- **Rıza (Madde 6(1)(a))**: temiz ancak genel amaçlı külliyatlar için nadiren ölçeklenebilir.
- **Sözleşme (Madde 6(1)(b))**: eğitimin sözleşme için gerekli olduğu durumlarda.
- **Yasal yükümlülük (Madde 6(1)(c))**: AI eğitimi için nadirdir.
- **Meşru menfaat (Madde 6(1)(f))**: kişisel veri kullanma gerekliliğini, orantılılığı ve daha az müdahaleci alternatiflerin yokluğunu gösteren özel bir Meşru Menfaat Değerlendirmesi gerektirir. EDPB Görüşü 28/2024 yüksek bir çıta belirler.

### 6. Web kazınmış eğitim verisi

Birçok temel model web kazınmış külliyatlar üzerinde eğitilir.

- Açık webdeki kişisel veri kişisel veri olmaya devam eder.
- "Açıkça kamuya açık hale getirilmiş" (Madde 9(2)(e)) kazınmış içeriğe geniş şekilde uygulanmaz.
- İtalyan Garante'nin 2023 ChatGPT emri şeffaflık, yaş kapısı, opt-out ve diğer önlemleri gerektirdi.

### 7. Kişisel veri olarak model çıktısı

EDPB Görüşü 28/2024, bir bireyi adlandıran veya tanımlanabilir özellikleri tanımlayan model çıktılarının kişisel veri olduğunu doğrular.

### 8. Madde 22 — otomatik karar verme

Madde 22(1), ilgili kişiye, hukuki etki üreten veya kendisini benzer şekilde önemli ölçüde etkileyen, tamamen otomatik işlemeye dayalı bir karara tabi olmama hakkı verir.

### 9. Şeffaflık yükümlülükleri

Madde 13(2)(f), 14(2)(g) ve 15(1)(h), veri sorumlusunun ilgili kişiyi şu konularda bilgilendirmesini gerektirir:
- otomatik karar vermenin varlığı, profilleme dahil;
- ilgili mantık hakkında anlamlı bilgi;
- ilgili kişi için önemi ve öngörülen sonuçlar.

### 10. AI Yasası yüksek riskli yükümlülükler

Yüksek riskli AI sistemleri için (Annex III):

- Yaşam döngüsü boyunca risk yönetim sistemi (Madde 9).
- Veri yönetişimi ve yönetimi (Madde 10).
- Teknik dokümantasyon (Madde 11) ve Annex IV.
- Kayıt tutma / otomatik günlükler (Madde 12).
- Dağıtıcılara şeffaflık (Madde 13).
- İnsan denetimi (Madde 14).
- Doğruluk, dayanıklılık ve siber güvenlik (Madde 15).
- Uygunluk değerlendirmesi (Madde 43).
- Kayıt (Madde 49).
- Pazar sonrası izleme (Madde 72) ve ciddi olay raporlama (Madde 73).

### 11. ChatGPT / Claude / Gemini çalışan kullanım politikası

Çalışanlar kaçınılmaz olarak iş için ticari LLM'leri kullanır. Yönetişim olmadan, istemler şunları içerebilir:
- müşteri kişisel verileri;
- çalışan verileri;
- ticari sırlar;
- düzenlenmiş içerik (sağlık, hukuki tavsiye).

| Öğe | Kural |
|-----|-------|
| Onaylı araçlar | Yalnızca kurumsal sözleşme ve VİS'leri olan listelenmiş araçlar |
| Yasaklı araçlar | Ücretsiz tüketici katmanları; VİS olmayan araçlar; kontrolsüz API'ler |
| İzin verilen istemler | Kamu bilgisi araştırması, hassas olmayan kod yardımı |
| Yasaklı istemler | Müşteri kişisel verisi, kullanıcının kendinin ötesinde çalışan kişisel verisi, Madde 9 özel kategori, ticari sırlar, sırlar içeren kaynak kodu |
| Çıktı yönetimi | Olgusal iddiaları doğrulayın; incelemeden müşteriye yönelik yapıtlara çıktı yapıştırmayın |
| Günlükleme | Saklama kontrolleri olan kurumsal katman |
| Eğitim | Yıllık zorunlu |
| Tespit | Mümkün olduğunda istemde kişisel veriyi tespit etmek için DLP kuralları |
| Olay | İstem sızıntısını potansiyel ihlal olarak değerlendirin |

### 12. İstem sızıntısı ve sızdırma riskleri

| Risk | Açıklama |
|------|----------|
| Kullanıcı istem sızıntısı | İstemdeki gizli veri model sağlayıcısı tarafından kalıcı, muhtemelen eğitim için kullanılır |
| Model çıktı sızıntısı | Model kişisel veri içeren eğitim verisini kelimesi kelimesine çıktılar |
| Çapraz kiracı sızıntısı | Çok kiracılı model bir kiracının verisini diğerine döndürür |
| Yan kanal sızıntısı | Gecikme, gömme örüntüleri özel bilgileri açığa çıkarır |
| Bellek sızıntısı | Uzun bağlam veya bellek özellikleri amaçlanan oturumun ötesinde veri tutar |
| Eklenti sızıntısı | Araçlar ve eklentiler harici sistemleri çağırır |

### 13. LLM Uygulamaları için OWASP Top 10 (2025)

1. **LLM01: İstem Enjeksiyonu**
2. **LLM02: Hassas Bilgi İfşası**
3. **LLM03: Tedarik Zinciri**
4. **LLM04: Veri ve Model Zehirlenmesi**
5. **LLM05: Yanlış Çıktı Yönetimi**
6. **LLM06: Aşırı Yetki**
7. **LLM07: Sistem İstem Sızıntısı**
8. **LLM08: Vektör ve Gömme Zayıflıkları**
9. **LLM09: Yanlış Bilgi**
10. **LLM10: Sınırsız Tüketim**

### 14. NIST AI RMF

NIST AI RMF 1.0 (2023), AI risk yönetimini dört işlev etrafında yapılandırır: GOVERN, MAP, MEASURE, MANAGE.

### 15. ISO/IEC 42001

ISO/IEC 42001:2023, ISO 27001 gibi yapılandırılmış bir AI Yönetim Sistemi standardıdır.

### 16. Şirket içi ve özel dağıtım

Hassas iş yükleri için seçenekler:
- şirket içi model barındırma (Llama, Mistral gibi açık ağırlıklı modeller);
- özel bulut dağıtımı;
- eğitim olmama taahhütleriyle özel kiracılık;
- uçta çıkarım.

### 17. AI için DLP

- giden istemlerin incelenmesi;
- tespit edilen kişisel verinin redaksiyonu veya engellenmesi;
- tedarikçi tarafı kontroller;
- istem taksonomisi: düşük / orta / yüksek risk;
- yönlendirme: yüksek riskli istemler yalnızca özel dağıtımlara;
- güvenlik incelemesi için istem ve yanıtların denetim günlüğü.

### 18. Açıklanabilirlik

Madde 13(2)(f), 14(2)(g), 15(1)(h) mantık hakkında anlamlı bilgi gerektirir.

### 19. AI için VKD

VKD, Madde 35 altında zorunludur:
- hukuki/önemli etki üreten kişisel yönlerin sistematik ve kapsamlı değerlendirmesi (profilleme);
- özel kategorilerin büyük ölçekli işlenmesi;
- kamuya açık alanların sistematik izlenmesi;
- yeni teknolojiler — AI bu kriter için her Üye Devlet DM'sinin kara listesindedir.

### 20. AI için işleme kayıtları

AI faaliyetleri için ROPA girişleri şunları içermelidir:
- model adı, sürümü, sağlayıcısı;
- eğitim verisi kaynakları ve hukuki temel;
- çıkarım girdileri (istemler) ve çıktıları;
- alıcılar;
- aktarımlar (genellikle ABD sağlayıcılarına);
- istem ve çıktıların saklanması;
- otomatik karar verme bayrağı ve uygulanabilirse Madde 22 analizi.

### 21. Tedarikçi durum tespiti

Her AI tedarikçisi için:
- gerekli olduğunda eğitim olmama taahhütleriyle VİS;
- aktarım mekanizması;
- model kartı / sistem kartı;
- değerlendirme raporları;
- olay bildirim SLA'sı;
- denetim hakları;
- veri işleme yerleri;
- güvenli geliştirme yaşam döngüsü kanıtı;
- AI'ya özgü testler dahil sızma testi.

### 22. Spesifik riskler ve örüntüler

#### 22.1 Müşteri destek sohbet botları

Genellikle Madde 22 — geri ödemelere, uygunluğa, destek önceliğine karar verirlerse.

#### 22.2 CV taraması

AI Yasası altında yüksek riskli (Annex III). Genellikle Madde 22.

#### 22.3 Dolandırıcılık tespiti

Genellikle GDPR altında meşru menfaat; temel hizmetler için kullanılırsa AI Yasası altında yüksek riskli.

#### 22.4 Üretici içerik

Kullanıcılara şeffaflık (AI Yasası Madde 50): sentetik içerik işaretlenmelidir.

#### 22.5 Kodlama yardımcıları

Riskler: kişisel veri içeren kaynak kodu sağlayıcılara gönderilir; ezberlenmiş kişisel veri içeren çıktı.

#### 22.6 Belge ve e-posta özetleme

Belgelerdeki kişisel veri model bağlamına girer.

### 23. Çocuklar ve AI

AI Yasası, çocukların zayıflıklarını sömüren AI sistemlerini yasaklar.

### 24. İşçi temsilciliği

İstihdam bağlamında kullanılan AI sistemleri için (işe alım, performans, izleme), Üye Devlet iş hukuku genellikle dağıtımdan önce işçi temsilcileri veya işyeri konseyleriyle danışma gerektirir.

### 25. KVKK ve Türkiye bağlamı

KVKK uygulanır. KVK Kurulu, AI sistemleri için kararlar yayımlamaktadır ve ChatGPT'ye karşı belirli yaptırımlar (Türkiye'de erişim kısıtlamaları dahil) tarihsel olarak bildirilmiştir. Türkiye'nin kendi AI politikası belgesi (Ulusal Yapay Zeka Stratejisi 2021–2025) yönergeler sağlar.

### 26. AI'ya özgü olay müdahalesi

AI'ya özgü olay senaryoları:
- model çıkarma saldırısı (biri API üzerinden modeli çalar);
- eğitim verisi çıkarma (üyelik çıkarımı, özellik çıkarımı);
- veri sızdıran istem enjeksiyonu;
- ince ayar verisinin arka kapısı veya zehirlenmesi;
- sistematik hatalar üreten model bozulması;
- yetkisiz eylemler gerçekleştiren ajanlık sistemi.

### 27. Belgeleme paketi

Her AI sistemi için:
- VKD;
- Madde 6 / Madde 9 / Madde 22 analizi;
- Gerekçeli AI Yasası risk sınıflandırması;
- model / sistem kartı;
- ROPA girişi;
- önyargı ve adillik değerlendirmesi;
- şeffaflık bildirim içeriği;
- insan denetim tasarımı;
- güvenlik testleri;
- tedarikçi sözleşmeleri ve güvence;
- olay senaryoları ve runbook'ları;
- dağıtım sonrası izleme planı.

### 28. Üç aylık AI yönetişim incelemesi

VKK ve AI Yönetişim lideri ortaklaşa şunları inceler:
- AI envanter tamlığı;
- yeni kullanım durumları;
- VKD birikimi ve yenileme ritmi;
- tedarikçi listesi değişiklikleri;
- olay öğrenmeleri;
- düzenleyici gelişmeler;
- eğitim kayıtları.

### 29. AI okuryazarlığı yükümlülüğü (AI Yasası Madde 4)

2 Şubat 2025'ten itibaren, AI sistemlerinin sağlayıcıları ve dağıtıcıları, personellerinin yeterli düzeyde AI okuryazarlığına sahip olduğundan emin olmak için en iyi ölçüde önlemler alacaktır.

### 30. Kapanış ilkesi

AI sistemleri hem yetenekleri hem de riski büyütür. Veri sorumlusunun duruşu ilkeli benimsemedir: net kullanım durumları, belgelenmiş temel ve etki, sınırlı özerklik, sağlam denetim, dosyada kanıt. Herhangi bir yeni AI kullanım durumu için varsayılan, dağıtımdan önce yapılandırılmış bir alım (VKD + AI Yasası sınıflandırması + uygulanabilir olduğunda LIA) ve sonrasında devam eden incelemedir.
