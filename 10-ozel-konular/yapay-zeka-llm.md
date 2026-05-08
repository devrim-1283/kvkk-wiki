---
Doküman / Document: Yapay Zeka ve Büyük Dil Modelleri (LLM) Kullanımı / Use of Artificial Intelligence and Large Language Models (LLMs)
Bölüm / Section: 10-ozel-konular
Sahip / Owner: KVKK Sorumlusu + CISO + AI/ML Lideri + Veri Bilim / KVKK Officer + CISO + AI/ML Lead + Data Science
Onaylayan / Approved by: Hukuk Müdürü + KVKK Komitesi + CTO / Head of Legal + KVKK Committee + CTO
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yarı yıllık (alan hızlı değişiyor) / Semi-annual (rapidly evolving area)
İlgili Mevzuat / Legal Reference: Law No. 6698 (KVKK) Art. 5, 6, 9, 11(g); EU AI Act (reference, not directly applicable); NIST AI RMF 1.0; OWASP Top 10 for LLM (2025); ISO/IEC 42001:2023; Türkiye National AI Strategy
---

## English

# Use of Artificial Intelligence and LLMs

## 1. Purpose

KVKK-compliant management of AI use - particularly large language models (LLMs) - within the company. The area requires a cautious approach due to its **rapidly changing** regulatory environment; a Türkiye AI Law similar to the EU AI Act is expected in the near future.

## 2. Use Scenarios

| Scenario | Risk Level | Legal Ground |
|----------|------------|--------------|
| Employee personal ChatGPT use (for work) | **High** (leakage) | Customer/other explicit consent; policy restriction |
| Corporate ChatGPT/Claude/Gemini Enterprise | Medium | DPA + contract |
| Customer service chatbot | Medium | Explicit consent + disclosure |
| Automated decisions (credit, recruitment screening) | **High** | DPIA + manual revision |
| LLM customer-comment summarization | Medium | Disclosure; cross-border transfer caution |
| AI-assisted coding (Copilot, Cursor) | Low-Medium | Code-leakage controls |
| LLM content generation (marketing) | Low | Content review |
| RAG over company documents Q&A | Medium | Access permissions + DLP |
| Meeting transcript + summary (Otter, Fireflies) | Medium-High | Explicit consent from participants |
| Personalization (recommendation system) | Medium | Disclosure + (where applicable) explicit consent |
| Real customer data in AI training | **Very High** | Explicit consent rarely sufficient; anonymize |

## 3. Employee ChatGPT/Claude/Gemini Use Policy

### 3.1. Risk

- Employee pastes customer data into a prompt -> data goes abroad.
- Trade secrets, code, financial information leaks.
- Personal account -> hard to audit.
- Some models may use prompts for training (unless turned off).

### 3.2. Policy Items

```
1. PROHIBITED to do work in a personal (free/Plus) account.
2. Only approved corporate accounts may be used:
   - ChatGPT Enterprise / Team
   - Claude for Work / Enterprise
   - Gemini Enterprise
   - Microsoft Copilot for M365
3. Pasting rules:
   - Personal data (T.R. ID, customer name, e-mail, phone) PROHIBITED
   - Trade secrets (contract, code, financial) PROHIBITED
   - Pseudonymized / anonymized data permitted
4. Output review:
   - LLM outputs must be verified before use in communications
   - Sensitive decisions cannot rely on LLM alone
5. Audit:
   - Use is logged on corporate tools
   - Anomaly detection (DLP integration)
6. Training:
   - 1 hour annual AI awareness training
   - Onboarding module for new starters
7. Violations:
   - 1st violation: warning + training
   - 2nd violation: discipline
   - Intentional data leakage: termination + criminal proceedings
```

### 3.3. Technical Controls

- DLP - filter personal data from prompts.
- Web filter - approved domains.
- EDR - application allowlisting.
- Endpoint usage analytics.

## 4. Corporate LLM Contracts

### 4.1. Checklist

| Item | Our Position |
|------|--------------|
| Data not used for training | **Mandatory** (contractual) |
| DPA / KVKK compliance clause | Mandatory |
| Standard Contract for cross-border transfer | Mandatory (foreign processor) |
| Audit log sharing | Mandatory |
| Retention | 30 days max (zero retention preferred) |
| Region selection | EU / Türkiye |
| Encryption (transit + rest) | TLS 1.3 + AES-256 |
| 24-hour breach notification | Mandatory |
| End-of-contract data deletion + certificate | Mandatory |
| Insurance + liability | Legal review |

### 4.2. Recommended Solutions

| Solution | KVKK Compliance Notes |
|----------|------------------------|
| OpenAI ChatGPT Enterprise / API | Zero retention option, EU region |
| Anthropic Claude (API + Enterprise) | EU/US region; not used for training by default |
| Microsoft Copilot for M365 | EU Data Boundary; tenant isolation |
| Google Gemini Enterprise | EU region; DLP integration |
| AWS Bedrock | Region control; data does not leave AWS |
| Azure OpenAI Service | EU/US; data inside Azure tenant |
| **On-prem (private)** | Llama 3, Mistral - data inside the company |

### 4.3. Cross-Border Transfer Analysis

An LLM API call = data transferred abroad.

- Standard Contract mandatory.
- TIA (Transfer Impact Assessment).
- Notify the Authority within 5 business days.

## 5. Personal Data Leakage in Prompts

### 5.1. Leakage Vectors

- "Write a response to this customer's complaint: [customer name + e-mail + issue]" -> all into the LLM.
- "Summarize this CV: [full CV]" -> personal data.
- "What are the risks in this contract: [parties + amounts]" -> trade secrets.

### 5.2. Prevention

- **Pre-prompt sanitization** - DLP integration.
- **Anonymization** before the prompt.
- **Pseudo IDs** - "Customer A" instead of a name.
- **Training** - employee awareness.

### 5.3. DLP Integration

- Scan prompts for personal data on egress.
- Block if detected + user feedback.
- Logging + UEBA anomaly detection.

## 6. DPIA Requirement

The Authority's guides recommend DPIA for high-risk processing. AI/LLM use requires a DPIA in:

- Automated decisions (e.g., recruitment, credit, pricing).
- Profiling (segment, churn).
- Wide scale (1M+ users).
- Sensitive categories (health, finance).
- New technology.
- Cross-border transfer.

### 6.1. DPIA Sections (AI Specific)

1. System definition (model, provider, data flow).
2. Processing purpose + necessity.
3. Legal ground.
4. Data category + source.
5. Algorithm explanation (model card).
6. Risks: bias, discrimination, leakage, hallucination.
7. Measures: human-in-the-loop, explainability, restriction.
8. Effect on data subjects + Art. 11(g).
9. Residual risk + acceptance.
10. Monitoring + renewal plan.

## 7. Model Card

A **model card** is published for each AI system:

```
Model Card - [System Name] v[X.Y]

1. General
   - Model: GPT-4 / Claude / Llama / etc.
   - Provider:
   - Region:
   - Version:

2. Purpose
   - Primary:
   - Side-effect possibilities:

3. Training Data (provider info)
   - Type:
   - Scope:
   - Cutoff date:

4. Performance
   - Test-set results:
   - Known weaknesses:
   - Hallucination rate (if measured):

5. Bias Assessment
   - Demographics tested:
   - Findings:

6. Limitations
   - Scenarios where the model should not be used:

7. KVKK Context
   - Legal ground:
   - Cross-border transfer:
   - DPIA reference:
   - Data subject rights (especially Art. 11(g)):

8. Monitoring
   - Performance metric tracking:
   - Re-evaluation date:
```

## 8. Explainability and Data Subject Rights

### 8.1. KVKK Art. 11(g)

> "To object to the emergence of a result against the person from analysis of processed data exclusively by automated systems."

**Our responsibility:**

- Disclose if there is automated decision-making.
- Communicate the main parameters.
- Offer manual revision.
- On candidate/customer request, provide a human decision.

### 8.2. Explainable AI (XAI) Approaches

- LIME, SHAP - explanation of model output.
- Decision path - tree-based models.
- Counterfactual - "what if a different input".
- LLM reasoning chain - Chain-of-Thought.

### 8.3. Transparency Standard

The explanation provided to the data subject:

- B1-level Turkish.
- Main inputs to the algorithm.
- Factors influencing the decision.
- Path to manual revision.
- KVKK Art. 11(g) right.

## 9. OWASP LLM Top 10 (2025)

OWASP's 2025 list for LLM application security:

| # | Risk | KVKK Relevance |
|---|------|----------------|
| 1 | Prompt Injection | Unauthorized data leakage |
| 2 | Insecure Output Handling | XSS, command injection |
| 3 | Training Data Poisoning | Bias, discrimination |
| 4 | Model Denial of Service | System security |
| 5 | Supply Chain Vulnerabilities | Third-party risk |
| 6 | Sensitive Information Disclosure | Direct KVKK breach |
| 7 | Insecure Plugin Design | Plugin abuse |
| 8 | Excessive Agency | Uncontrolled automated decisions |
| 9 | Overreliance | Hallucination |
| 10 | Model Theft | Intellectual property |

Internal drills + mitigation per risk.

## 10. NIST AI RMF 1.0

NIST AI Risk Management Framework:

### 10.1. Four Functions

- **Govern** - governance, policy, accountability.
- **Map** - context, risk mapping.
- **Measure** - measurement, testing.
- **Manage** - risk management, response.

### 10.2. Company Implementation

- AI governance committee (sub-group within KVKK Committee).
- AI inventory (systems, use cases).
- Risk-assessment matrix (per system).
- Continuous monitoring + reporting.

## 11. EU AI Act Readiness

The EU AI Act (in force 2024, enforcement 2026-2027) does not directly bind Türkiye, **however**:

- Turkish firms supplying products/services to the EU will be covered.
- The Türkiye AI Law is likely to follow a similar framework.

### 11.1. Risk Tiers (AI Act)

- **Prohibited** (subliminal manipulation, social scoring).
- **High-risk** (recruitment, credit, education, law) - strict obligations.
- **Limited** (chatbots, deepfakes) - transparency.
- **Low** - free.

### 11.2. Company Preparation

- AI inventory classification (prohibited / high / limited / low).
- Additional documentation for high-risk systems.
- Preparation for CE-like certification.
- User notice (chatbot + AI).

## 12. ISO/IEC 42001:2023

AI Management System (AIMS) standard. Framework similar to ISO 27001.

- AI policy.
- Roles and responsibilities.
- Risk assessment.
- Controls (164+).
- Annual audit.

> 12-24 month certification path depending on company size.

## 13. On-Premise / Private LLM

### 13.1. Advantages

- Data inside the company.
- No cross-border transfer.
- Easier regulatory compliance.
- Fine-tuning with private data possible.

### 13.2. Recommended Models

- Llama 3 (Meta - open weights).
- Mistral (Mixtral - open).
- DeepSeek, Qwen (license caution).

### 13.3. Infrastructure Cost

- Significant GPU investment (NVIDIA H100, A100).
- Continuous updates + security.
- Talent (MLOps).
- ROI analysis.

### 13.4. Hybrid Approach

- Sensitive workloads on-prem.
- General workloads on cloud LLM.
- Routing layer (LiteLLM, OpenRouter equivalents).

## 14. RAG and Access Control

### 14.1. RAG (Retrieval-Augmented Generation)

- Company documents in a vector DB via embeddings.
- LLM retrieves documents when answering.
- Sourced answers.

### 14.2. KVKK Compliance

- **Access filter** per user (only authorized documents).
- Audit log - who accessed which document.
- Sensitive content (personnel, health) in a separate index + restricted access.

### 14.3. Vector DB

- Pinecone, Weaviate, Qdrant, ChromaDB.
- Foreign provider = transfer.
- On-prem alternatives (Qdrant self-hosted, pgvector).

## 15. Common Mistakes

| Mistake | Correct approach |
|---------|------------------|
| Personal ChatGPT for work | Corporate tool + policy |
| Customer name in prompt | Pseudonymize |
| Zero-retention disabled on API call | Contract + setting |
| No DPIA | Mandatory for high risk |
| No model card | One per system |
| No explainability under Art. 11(g) | XAI + manual revision |
| No explicit consent for meeting transcript | Participants' consent |
| No RAG access filter | Per user authorization |
| No Standard Contract for foreign LLM | Authority notification mandatory |
| No hallucination control | Human approval for critical decisions |

## 16. KPIs

| KPI | Target |
|-----|--------|
| Approved corporate AI tool usage rate | 100% |
| Annual employee AI awareness training completion | 100% |
| DPIA completion (high-risk AI) | 100% |
| Model card publication | 100% |
| Zero retention on corporate AI contracts | 100% |
| DLP prompt-leakage block | 95%+ |
| AI inventory currency | < 30 days |
| Standard Contract notification for foreign LLMs | 100% |

## 17. Annual AI Governance Calendar

| Quarter | Action |
|---------|--------|
| Q1 | AI inventory update + risk classification |
| Q2 | DPIA review; new systems |
| Q3 | Renew employee awareness training |
| Q4 | Annual AI governance report (KVKK Committee) |
| Continuous | Track legislation (Türkiye AI Law, EU AI Act) |

## 18. Linked Sections

- `06-idari-tedbirler/` - AI awareness training.
- `07-aktarim/` - Cross-border transfer.
- `10-ozel-konular/musteri-pazarlama-cms.md` - Marketing profiling.
- `10-ozel-konular/bulut-hizmetleri.md` - Cloud LLM infrastructure.

## 19. Version History

| Version | Date | Change | Approval |
|---------|------|--------|----------|
| 1.0 | 2026-05-08 | First publication | KVKK Committee + CTO |

---

## Türkçe

# Yapay Zeka ve LLM Kullanımı

## 1. Amaç

Şirket bünyesinde yapay zeka (özellikle büyük dil modelleri / LLM) kullanımının KVKK uyumlu yönetimi. Bu alan **hızla değişen** mevzuat ortamı nedeniyle ihtiyatlı yaklaşım gerektirir; AB AI Act benzeri Türkiye düzenlemesi (Yapay Zeka Kanunu) yakın gelecek beklenmektedir.

## 2. Kullanım Senaryoları

| Senaryo | Risk Seviyesi | Hukuki Sebep |
|---------|---------------|--------------|
| Çalışanın kişisel ChatGPT kullanımı (iş için) | **Yüksek** (sızıntı) | Açık rıza müşteri/diğer; politika sınırlama |
| Kurumsal ChatGPT/Claude/Gemini Enterprise | Orta | DPA + sözleşme |
| Müşteri hizmeti chatbot | Orta | Açık rıza + aydınlatma |
| Otomatik karar (kredi, insan kaynağı eleme) | **Yüksek** | DPIA + manuel revize |
| LLM ile müşteri yorumu özet | Orta | Aydınlatma; yurt dışı aktarım dikkat |
| AI ile kod yazma (Copilot, Cursor) | Düşük-Orta | Kod sızıntısı denetimi |
| LLM ile içerik üretimi (pazarlama) | Düşük | İçerik kontrol |
| RAG ile şirket dokümanlarına soru-cevap | Orta | Erişim yetkisi + DLP |
| Toplantı transcript + özet (Otter, Fireflies) | Orta-Yüksek | Açık rıza katılımcılardan |
| Kişiselleştirme (öneri sistemi) | Orta | Aydınlatma + (varsa) açık rıza |
| AI eğitiminde gerçek müşteri verisi kullanımı | **Çok Yüksek** | Açık rıza nadiren yeterli; anonimleştirme |

## 3. Çalışan ChatGPT/Claude/Gemini Kullanım Politikası

### 3.1. Risk

- Çalışan müşteri verisi prompt'a yapıştırır → veri yurt dışı.
- Şirket sırrı, kod, finansal bilgi sızar.
- Hesap çalışan kişisel → audit zor.
- Bazı modeller prompt'u eğitime kullanabilir (kapatılmazsa).

### 3.2. Politika Maddeleri

```
1. Kişisel hesap (ücretsiz/Plus) ile iş yapma YASAK.
2. Sadece onaylanmış kurumsal hesap kullanılır:
   - ChatGPT Enterprise / Team
   - Claude for Work / Enterprise
   - Gemini Enterprise
   - Microsoft Copilot for M365
3. Yapıştırma kuralları:
   - Kişisel veri (T.C., müşteri ismi, e-posta, telefon) YASAK
   - Şirket sırrı (sözleşme, kod, finansal) YASAK
   - Pseudonymize / anonimleştirilmiş veri serbest
4. Çıktı denetimi:
   - LLM çıktısı doğrulanmadan iletişimde kullanılmaz
   - Hassas karar için tek başına dayanılmaz
5. Audit:
   - Kurumsal araçlarda kullanım log'lanır
   - Anomali tespiti (DLP entegrasyonu)
6. Eğitim:
   - Yıllık 1 saat AI farkındalık eğitimi
   - Yeni iş başlangıcında onboarding modülü
7. İhlal:
   - 1. ihlal: uyarı + eğitim
   - 2. ihlal: disiplin
   - Kasıtlı veri sızıntısı: iş akdi feshi + adli süreç
```

### 3.3. Teknik Önlemler

- DLP — prompt'lara kişisel veri filtre.
- Web filtre — onaylı domainler.
- EDR — uygulama beyaz listesi.
- Endpoint kullanım analizi.

## 4. Kurumsal LLM Sözleşmeleri

### 4.1. Kontrol Listesi

| Madde | Şirketimiz Tutumu |
|-------|-------------------|
| Veri eğitime kullanılmaz | **Zorunlu** (sözleşmesel) |
| DPA / KVKK uyum klozu | Zorunlu |
| Yurt dışı aktarım Standart Sözleşme | Zorunlu (yurt dışı işleyen) |
| Audit log paylaşımı | Zorunlu |
| Saklama süresi | 30 gün max (zero retention tercih) |
| Region seçimi | AB / Türkiye |
| Şifreleme (transit + rest) | TLS 1.3 + AES-256 |
| İhlal bildirim 24 saat | Zorunlu |
| Sözleşme sonu veri silme + sertifika | Zorunlu |
| Sigorta + sorumluluk | Hukuk değerlendirmesi |

### 4.2. Önerilen Çözümler

| Çözüm | KVKK Uyum Notu |
|-------|----------------|
| OpenAI ChatGPT Enterprise / API | Zero retention opsiyonu, EU region |
| Anthropic Claude (API + Enterprise) | EU/US region; eğitim için kullanılmaz default |
| Microsoft Copilot for M365 | EU Data Boundary; tenant izolasyon |
| Google Gemini Enterprise | EU region; DLP entegrasyon |
| AWS Bedrock | Region kontrolü; veri AWS dışına çıkmaz |
| Azure OpenAI Service | EU/US; veri Azure tenant'ında |
| **On-prem (private)** | Llama 3, Mistral — veri Şirket içinde |

### 4.3. Yurt Dışı Aktarım Analizi

LLM API çağrısı = veri yurt dışına aktarım.
- Standart Sözleşme zorunlu.
- TIA (Transfer Impact Assessment).
- Kurul'a 5 iş günü içinde bildirim.

## 5. Prompt'a Kişisel Veri Sızdırma

### 5.1. Sızıntı Vektörleri

- "Şu müşterinin şikayetine cevap yaz: [müşteri ismi + e-posta + sorun]" → tüm bunlar LLM'e.
- "Bu CV'yi özetle: [tam CV]" → kişisel veri.
- "Bu sözleşmenin riskleri ne: [taraf isimleri + tutarlar]" → ticari sır.

### 5.2. Önleme

- **Pre-prompt sanitization** — DLP entegrasyon.
- **Anonimleştirme** önce, prompt sonra.
- **Pseudo ID** — kişi yerine "Müşteri A".
- **Eğitim** — çalışan farkındalık.

### 5.3. DLP Entegrasyon

- Prompt giderken kişisel veri tara.
- Bulursa engelle + kullanıcıya geri bildirim.
- Kayıt + UEBA anomali tespiti.

## 6. DPIA Zorunluluğu

KVKK Kurul rehberi yüksek riskli işleme için DPIA önerir. AI/LLM kullanımı şu durumlarda DPIA zorunludur:

- Otomatik karar (örn. işe alım, kredi, fiyatlama).
- Profilleme (segment, churn).
- Geniş ölçek (1M+ kullanıcı).
- Hassas kategori (sağlık, finans).
- Yeni teknoloji.
- Yurt dışı aktarım.

### 6.1. DPIA Bölümleri (AI Spesifik)

1. Sistem tanımı (model, sağlayıcı, veri akışı).
2. İşleme amacı + gereklilik.
3. Hukuki sebep.
4. Veri kategorisi + kaynak.
5. Algoritma açıklaması (model kart).
6. Risk: önyargı, ayrımcılık, sızıntı, halüsinasyon.
7. Tedbirler: human-in-the-loop, açıklanabilirlik, sınırlandırma.
8. İlgili kişi etki + m.11/g.
9. Kalan risk + kabul.
10. İzleme + yenileme planı.

## 7. Model Kart (Model Card)

Her AI sistemi için **model kart** yayımlanır:

```
Model Kart - [Sistem Adı] v[X.Y]

1. Genel Bilgi
   - Model: GPT-4 / Claude / Llama / vs.
   - Sağlayıcı:
   - Region:
   - Versiyon:

2. Amaç
   - Birincil:
   - Yan etki olasılıkları:

3. Eğitim Verisi (sağlayıcı bilgisi)
   - Tipi:
   - Kapsam:
   - Tarih sınırı:

4. Performans
   - Test seti sonuçları:
   - Bilinen zayıflıklar:
   - Halüsinasyon oranı (varsa ölçülmüş):

5. Önyargı (Bias) Değerlendirmesi
   - Test edilen demografi:
   - Bulgular:

6. Sınırlamalar
   - Kullanılmaması gereken senaryolar:

7. KVKK Bağlamı
   - Hukuki sebep:
   - Yurt dışı aktarım:
   - DPIA referansı:
   - İlgili kişi hakları (özellikle m.11/g):

8. İzleme
   - Performans metriği takibi:
   - Yeniden değerlendirme tarihi:
```

## 8. Açıklanabilirlik ve İlgili Kişi Hakları

### 8.1. KVKK m.11/g

> "İşlenen verilerin münhasıran otomatik sistemlerle analiz edilmesi suretiyle kişinin kendisi aleyhine bir sonucun ortaya çıkmasına itiraz etme."

**Bizim sorumluluğumuz:**
- Otomatik karar var mı, açıkla.
- Kararın temel parametreleri.
- Manuel revize seçeneği.
- Aday/müşteri talep ederse insan kararı.

### 8.2. Açıklanabilir AI (XAI) Yaklaşımları

- LIME, SHAP — model çıktısı açıklama.
- Karar yolu (decision path) — ağaç tabanlı modeller.
- Counterfactual — "ne olsaydı farklı sonuç gelirdi".
- LLM ile reasoning chain — Chain-of-Thought.

### 8.3. Şeffaflık Standartı

İlgili kişiye sunulacak açıklama:
- B1 düzey Türkçe.
- Algoritmanın temel girdileri.
- Karara etkili faktörler.
- Manuel revize yolu.
- KVKK m.11/g hakkı.

## 9. OWASP LLM Top 10 (2025)

LLM uygulama güvenliği için OWASP'ın 2025 versiyonu:

| # | Risk | KVKK Bağlamı |
|---|------|--------------|
| 1 | Prompt Injection | Yetkisiz veri sızıntısı |
| 2 | Insecure Output Handling | XSS, command injection |
| 3 | Training Data Poisoning | Bias, ayrımcılık |
| 4 | Model Denial of Service | Sistem güvenliği |
| 5 | Supply Chain Vulnerabilities | Üçüncü taraf risk |
| 6 | Sensitive Information Disclosure | KVKK ihlali doğrudan |
| 7 | Insecure Plugin Design | Eklenti istismarı |
| 8 | Excessive Agency | Otomatik karar kontrolsüz |
| 9 | Overreliance | Halüsinasyon |
| 10 | Model Theft | Fikri mülkiyet |

Her risk için iç tatbikat + mitigation.

## 10. NIST AI RMF 1.0

NIST AI Risk Management Framework — yapay zeka risk yönetimi:

### 10.1. Dört Fonksiyon

- **Govern** — Yönetişim, politika, hesap verebilirlik.
- **Map** — Bağlam, risk haritalama.
- **Measure** — Ölçüm, test.
- **Manage** — Risk yönetim, müdahale.

### 10.2. Şirket Uygulaması

- AI yönetişim komitesi (KVKK Komitesi içinde alt grup).
- AI envanteri (sistemler, kullanım amaçları).
- Risk değerlendirme matrisi (her sistem).
- Sürekli izleme + raporlama.

## 11. AB AI Act Hazırlığı

AB AI Act (2024 yürürlük, 2026-2027 zorunluluk) Türkiye'yi bağlamaz **ancak**:
- Türk firmaları AB pazarına ürün/hizmet veriyorsa kapsama girer.
- Türkiye AI Kanunu büyük olasılıkla benzer çerçeve alacak.

### 11.1. Risk Tabakaları (AI Act)

- **Yasak** (subliminal manipülasyon, sosyal puanlama).
- **Yüksek riskli** (işe alım, kredi, eğitim, hukuk) — sıkı yükümlülükler.
- **Sınırlı** (chatbot, derin sahte) — şeffaflık.
- **Düşük** — serbest.

### 11.2. Şirket Hazırlığı

- AI envanter sınıflandırması (yasak / yüksek / sınırlı / düşük).
- Yüksek riskli sistemler için ek dokümantasyon.
- CE benzeri sertifikasyona hazırlık.
- Kullanıcıya bildirim (chatbot + AI).

## 12. ISO/IEC 42001:2023

Yapay zeka yönetim sistemi (AIMS) standardı. ISO 27001 benzeri çerçeve.

- AI politika.
- Rol ve sorumluluklar.
- Risk değerlendirme.
- Kontroller (164+).
- Yıllık denetim.

> Şirket büyüklüğüne göre 12-24 ay sertifikasyon yolu.

## 13. On-Premise / Private LLM

### 13.1. Avantajları

- Veri Şirket içinde.
- Yurt dışı aktarım yok.
- Düzenleyici uyum daha kolay.
- Özel veriyle fine-tune mümkün.

### 13.2. Önerilen Modeller

- Llama 3 (Meta — açık ağırlık).
- Mistral (Mixtral — açık).
- DeepSeek, Qwen (lisans dikkat).

### 13.3. Altyapı Maliyeti

- GPU (NVIDIA H100, A100) yatırımı yüksek.
- Sürekli güncelleme + güvenlik.
- Yetenek (MLOps).
- ROI değerlendirmesi.

### 13.4. Hibrit Yaklaşım

- Hassas görevler on-prem.
- Genel görevler bulut LLM.
- Routing katmanı (LiteLLM, OpenRouter benzeri).

## 14. RAG ve Erişim Kontrolü

### 14.1. RAG (Retrieval-Augmented Generation)

- Şirket dokümanlarını embedding ile vector DB'de.
- LLM cevap verirken doküman çek.
- Cevap kaynaklı.

### 14.2. KVKK Uyumu

- Her kullanıcı için **erişim filtresi** (sadece yetkili dokümanlar).
- Audit log — kim hangi dokümana erişti.
- Hassas içerik (özlük, sağlık) ayrı index + sınırlı erişim.

### 14.3. Vector DB

- Pinecone, Weaviate, Qdrant, ChromaDB.
- Yurt dışı sağlayıcı = aktarım.
- On-prem alternatif (Qdrant kendi sunucu, pgvector).

## 15. Tipik Hatalar

| Hata | Doğru Yaklaşım |
|------|----------------|
| Çalışan kişisel ChatGPT'de iş | Kurumsal araç + politika |
| Prompt'a müşteri ismi | Pseudonymize |
| API çağrısı zero retention kapalı | Sözleşme + ayar |
| DPIA yapılmamış | Yüksek risk için zorunlu |
| Model kart yok | Her sistem için |
| m.11/g açıklanabilirlik yok | XAI + manuel revize |
| Toplantı transcript açık rıza yok | Katılımcı onayı |
| RAG erişim filtresi yok | Kullanıcı yetkisi bazlı |
| Yurt dışı LLM Standart Sözleşme yok | Kurul bildirimi zorunlu |
| Halüsinasyon kontrolü yok | İnsan onayı kritik karar |

## 16. KPI'lar

| KPI | Hedef |
|-----|-------|
| Onaylı kurumsal AI araç kullanım oranı | %100 |
| Çalışan AI farkındalık eğitim tamamlanma | %100 yıllık |
| DPIA tamamlanma (yüksek riskli AI) | %100 |
| Model kart yayım | %100 |
| Kurumsal AI sözleşme zero retention | %100 |
| DLP prompt sızıntı engelleme | %95+ |
| AI envanteri güncellik | < 30 gün |
| Yurt dışı LLM Standart Sözleşme bildirim | %100 |

## 17. Yıllık AI Yönetişim Takvimi

| Çeyrek | Aksiyon |
|--------|---------|
| Q1 | AI envanteri güncelleme + risk sınıflandırma |
| Q2 | DPIA gözden geçirme; yeni sistemler |
| Q3 | Çalışan farkındalık eğitimi yenileme |
| Q4 | Yıllık AI yönetişim raporu (KVKK Komitesi) |
| Sürekli | Mevzuat takibi (Türkiye AI Kanunu, AB AI Act) |

## 18. Bağlantılı Bölümler

- `06-idari-tedbirler/` — AI farkındalık eğitimi.
- `07-aktarim/` — Yurt dışı aktarım.
- `10-ozel-konular/musteri-pazarlama-cms.md` — Pazarlama profilleme.
- `10-ozel-konular/bulut-hizmetleri.md` — Bulut LLM altyapı.

## 19. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi + CTO |
