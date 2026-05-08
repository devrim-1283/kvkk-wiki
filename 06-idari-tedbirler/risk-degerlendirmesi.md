---
Doküman / Document: Kişisel Veri Etki Değerlendirmesi (DPIA / PIA) ve Risk Yönetimi Standardı / Personal Data Impact Assessment (DPIA / PIA) and Risk Management Standard
Bölüm / Section: 06-idari-tedbirler
Sahip / Owner: KVKK Sorumlusu + Risk Yönetimi / KVKK Officer + Risk Management
Onaylayan / Approved by: KVKK Komitesi + Üst Yönetim / KVKK Committee + Senior Management
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş (yeni proje, yeni teknoloji, mevzuat değişikliği) / Annual + triggered (new project, new technology, regulatory change)
İlgili Mevzuat / Legal Reference: Law No. 6698 KVKK Art. 4 (general principles — proportionality), Art. 6 (special category), Art. 12 (data security); KVKK Authority Guides; GDPR Art. 35 (DPIA — comparative framework)
İlgili Standart / Standard: ISO/IEC 29134:2017 (Privacy Impact Assessment); ISO/IEC 27005:2022 (Information Security Risk Management); ISO 31000:2018 (Risk Management); NIST Privacy Framework; NIST CSF 2.0 GV.RM, ID.RA; ENISA "Recommendations on Shaping Technology Risks"; CNIL PIA Methodology
---

## English

# Personal Data Impact Assessment (DPIA / PIA) and Risk Assessment

## 1. Purpose

To enable systematic assessment of high-risk personal data processing activities **before they begin**, subjecting them to a proportionality test, identifying risks and mitigating them with measures, and submitting them for KVKK Committee approval. The operational arm of the proportionality principle of KVKK Art. 4; the natural result of the KVKK Authority's **risk-based compliance** approach.

> While the KVKK text does not explicitly regulate DPIA like GDPR Art. 35, the general principles of KVKK Art. 4 and the obligation of Art. 12 effectively render **high-risk processing without risk assessment** non-compliance before the Authority. Therefore, DPIA is an inseparable part of **good governance and compliance evidence**.

## 2. Definitions

| Term | Definition |
|-------|-------|
| **DPIA / KVED** | Data Protection Impact Assessment. |
| **PIA** | Privacy Impact Assessment (broad privacy assessment). |
| **Risk** | Combination of the likelihood of a particular threat occurring and the impact arising. |
| **Residual Risk** | Risk remaining after measures are taken. |
| **Risk Appetite** | The level of risk management is willing to accept. |
| **Threat** | An event that may cause harm. |
| **Vulnerability** | A weakness that the threat may exploit. |
| **Measure** | A control aimed at reducing risk. |

## 3. When is DPIA Mandatory?

DPIA is mandatory if one of the following **triggers** exists:

### 3.1. High-Risk Scenarios (KVKK Authority Guides and GDPR WP29 recommendations)

1. **Systematic and large-scale profiling / evaluation** — credit scoring, insurance risk score, employee performance algorithm.
2. **Automated decision-making** — KVKK Art. 5/2(f) "provided that it does not harm the fundamental rights and freedoms of the data subject" — but DPIA if there may be impact on rights and freedoms.
3. **Special-category data processing (KVKK Art. 6)** — health, biometric, genetic, criminal conviction, union, religion, etc.
4. **Children's data** — under 18.
5. **Employee monitoring (continuous, broad scope)** — broad DLP, camera, GPS, keyboard/screen capture.
6. **Large-scale public area monitoring** — CCTV network, public face recognition.
7. **New technology adoption** — AI/ML, biometrics, IoT, blockchain, AR/VR.
8. **Combination of multiple datasets** (data combination) — sector market, profile enrichment.
9. **Automated decision regarding contracting / service provision to a person.**
10. **Cross-border transfer** — especially to countries without adequacy decision.
11. **Health, finance, education sector** — high-sensitivity sectoral.
12. **Processing of customers / employees for monitoring purposes.**

### 3.2. Trigger Table

| Trigger | DPIA |
|-------|------|
| New project, includes personal data | Risk screening; DPIA if high-risk |
| Existing process new technology | DPIA |
| New vendor (Class A) | Due diligence with DPIA component |
| Cross-border transfer new country | DPIA |
| New employee monitoring tool | DPIA |
| AI/ML model going to production | DPIA |
| Regulatory change impact | Existing DPIA review |
| After significant breach | DPIA review of affected process |

## 4. DPIA Process

```
1. Trigger (New project / change)
2. Risk Screening (Threshold Assessment) — DPIA needed?
3. Team Formation (process owner + KVKK Officer + CISO + Legal + IT)
4. Data Flow Mapping
5. Necessity and Proportionality Test
6. Threat & Risk Identification
7. Measure Design
8. Residual Risk Assessment
9. KVKK Officer Opinion
10. KVKK Committee Decision (Approval / Improvement / Rejection)
11. Implementation and Monitoring
12. Periodic Review
```

## 5. DPIA Template (Sections)

### 5.1. Executive Summary

- Project / process name.
- Process owner.
- Preparers.
- Preparation date.
- Result (approval status, conditions, residual risk level).

### 5.2. Process Description

- Process purpose (business goal).
- Beneficiaries (data subject groups).
- Service / process flow (high-level).
- Related systems and technologies.
- Data controller / data processor roles.

### 5.3. Data Flow

- Data categories (general + special-category).
- Data source (from data subject, from third party?).
- Processing steps (collection → use → storage → transfer → destruction).
- Data flow diagram (visual).
- Transfer destinations (domestic / cross-border).
- Retention periods.
- Destruction methods.

### 5.4. Legal Basis

- Which condition under KVKK Art. 5 (general) / Art. 6 (special category)?
- If taking explicit consent: showing that consent is free / informed / specific.
- Legal grounds such as establishment of contract, legal obligation, public interest documented.
- Cross-border transfer legal mechanism (Art. 9).

### 5.5. Necessity and Proportionality Test

KVKK Art. 4 proportionality test:

- **Is it suitable for the purpose?** Is the data necessary for the purpose collected?
- **Is it limited?** Can the same purpose be achieved with less data?
- **Is it proportional?** Is the data collection method, scope proportional?
- **Is it specific?** Is the purpose clear and understandable?
- **Is the retention period reasonable?**
- **Have alternatives been considered?** (Anonymous, synthetic, less sensitive).

### 5.6. Data Subject Rights

- Has the privacy notice been prepared?
- How is the explicit consent process?
- How are access, rectification, erasure, objection, portability, automated-decision-objection rights implemented?
- Is the application channel recorded?

### 5.7. Threat and Risk Identification

In LINDDUN (privacy) + STRIDE (security) frameworks:

| # | Threat | Impact | Likelihood | Risk Score | Measure | Residual Risk |
|---|--------|------|----------|------------|--------|------------|
| R1 | Unauthorized access to DB | Very High | Medium | **High** | MFA + RLS + audit | Low |
| R2 | Data controller out-of-instruction use (insider) | High | Low | Medium | DLP + UEBA + training | Low |
| R3 | Unauthorized access in cross-border transfer | Very High | Low | Medium | Standard contract + encryption + audit | Low |
| R4 | Algorithm misclassification | High | Medium | **High** | Human review + DPIA review + right of objection | Medium |
| ... | ... | ... | ... | ... | ... | ... |

### 5.8. Possible Impact on the Data Subject

- Material harm (loss, fraud).
- Non-material harm (embarrassment, discrimination, reputation loss).
- Service access blocking (automated decision).
- Privacy breach.
- Category / stigma resulting from profiling.
- Additional sensitivity for children.
- Additional sensitivity for special-category data.

### 5.9. Measures

| Category | Measure |
|----------|--------|
| Technical | Encryption, MFA, RLS, audit log, DLP, key management |
| Organizational | Training, undertaking, policy, audit, contract |
| Legal | Privacy notice, consent, contract terms, regulatory tracking |
| Procedural | Control points, 4-eyes, periodic review |
| Data Architecture | Minimization, anonymous/pseudonym, data quality, automatic retention |

### 5.10. Residual Risk and Approval

- Risk score remaining after measures.
- Comparison with risk appetite — is it acceptable?
- If unacceptable: additional measures / project redesign / cancellation.
- KVKK Officer opinion letter (in annex).
- KVKK Committee decision record (in annex).

### 5.11. Monitoring and Review

- Frequency of review (annual, quarterly).
- Events triggering review.
- KPIs.

## 6. Risk Score Matrix

### 6.1. Impact

| Level | Definition | Example |
|--------|-------|-------|
| 5 — Very High | Irreversible harm to data subject; large-scale disclosure | Health data leaked to public |
| 4 — High | Significant harm; correction difficult | Turkish ID + card 100K records leaked |
| 3 — Medium | Correctable harm; temporary service interruption | Limited personal data (name-surname) leaked |
| 2 — Low | Minimal harm; quick correction | Logging deficiency noticed |
| 1 — Very Low | Negligible | Policy update delayed |

### 6.2. Likelihood

| Level | Definition |
|--------|-------|
| 5 — Very High | Actively occurring or imminent |
| 4 — High | Likely to occur within the year |
| 3 — Medium | Likely within 1-3 years |
| 2 — Low | Likely within 3-5 years |
| 1 — Very Low | Practically not likely |

### 6.3. Risk Score

```
Risk = Impact × Likelihood
```

| Score | Class | Action |
|------|-------|---------|
| 20-25 | Critical | IMMEDIATELY — project halted, senior management decision |
| 12-19 | High | Measure mandatory — within 30 days |
| 6-11 | Medium | Measure recommended — within 90 days |
| 1-5 | Low | Monitored — annual review |

### 6.4. Risk Appetite

Organization general risk appetite: KVKK breach-creating risk tolerated at **Low level**. High-Critical risk is not acceptable without explicit justification + senior management approval + compensating controls.

## 7. Management Roles

| Role | Responsibility |
|-----|-------------|
| Process Owner (Business Unit) | DPIA preparation request, content information provision, measure implementation |
| KVKK Officer | DPIA methodology, opinion letter, follow-up |
| CISO Office | Technical measure design, threat modeling |
| Legal | Legal basis, contract |
| IT / Architecture | Data flow, system integration |
| Risk Management | Score, consistency, corporate risk integration |
| KVKK Committee | Approval / rejection / conditional approval decision |
| Internal Audit | DPIA practice sample audit |

## 8. Risk Management Connections

DPIA is integrated into the organization's **holistic risk management** framework:

```
Strategic Risk (Senior Management)
   ↓
Operational Risk (Risk Management)
   ├── Information Security Risk Register (CISO)
   ├── Privacy/KVKK Risk Register (KVKK Officer) ← DPIA outputs go here
   ├── IT Risk Register
   ├── Vendor Risk Register
   └── Business Continuity Risk
```

Risk registers are reviewed quarterly. KVKK risks are added to corporate risk registers.

## 9. Quick Screening (Threshold) Template

Short form for the decision to start a DPIA (10 questions, 5 min):

```
1. Does the process include personal data? (Y/N)
2. Is there special-category data (Art. 6)? (Y/N)
3. Is there children's data? (Y/N)
4. Is the data subject count 10K+? (Y/N)
5. Is new technology (AI, biometric, IoT) used? (Y/N)
6. Is there automated decision / profiling? (Y/N)
7. Is employee / user monitoring being done? (Y/N)
8. Is there cross-border transfer? (Y/N)
9. Are multiple datasets being combined? (Y/N)
10. Is public area / public opinion monitoring done? (Y/N)

Number of YES:
   0-1: DPIA not required (simple risk screening sufficient)
   2-3: Light DPIA (short form)
   4+: Full DPIA
```

## 10. Typical DPIA Scenarios (Template Headings)

1. **New e-commerce platform** — customer registration, payment, profiling.
2. **Employee performance management system** — KPI tracking, automated suggestions.
3. **AI-based customer support chatbot** — chat logs, personal data disclosure.
4. **CCTV network upgrade** — new camera locations, face recognition feature.
5. **HR SaaS migration** — old system / new system transition, cross-border transfer.
6. **New biometric entry system** — fingerprint, iris.
7. **Marketing automation platform** — segmentation, behavior tracking.
8. **Health check-up program** — special-category data.
9. **Keyboard/screen monitoring tool** — high monitoring intensity.
10. **Education platform for children** — parental consent process.

## 11. Output Retention

- Completed DPIA document is **versioned** and in KVKK Officer portfolio.
- Retention: as long as the process is active + 5 years after.
- Access: KVKK Officer, CISO, relevant Director, Legal, Internal Audit.
- Ready in form presentable in KVKK Authority audit.

## 12. KPI

- DPIA-required project / DPIA completed: target 100%.
- Average DPIA completion time: target ≤30 days.
- DPIA review completion rate (annual): 100%.
- Open DPIA actions (over 90 days): 0.
- Number of projects rejected as a result of DPIA: trend tracking.
- Post-DPIA breach rate: trend tracking (quality indicator).

## 13. Checklist

- [ ] Is the DPIA Standard documented, ≤24 months current?
- [ ] Is risk screening (threshold) integrated into the new project process?
- [ ] Is the trigger list current, compliant with KVKK Authority guides?
- [ ] Is the DPIA template standard, complete?
- [ ] Is the risk score matrix documented, calibrated?
- [ ] Is the risk appetite management approved?
- [ ] Is the team role assigned for each DPIA?
- [ ] Is the KVKK Officer writing independent opinion?
- [ ] Are KVKK Committee approval records archived?
- [ ] Is the implementation of measures tracked?
- [ ] Is there an annual DPIA review schedule?
- [ ] Are DPIA outputs being processed into the corporate risk register?
- [ ] Are there projects requiring DPIA that haven't been done (gap analysis)?
- [ ] Does the annual internal audit perform DPIA sampling?
- [ ] Is there a business unit representative in the DPIA team (so they're not ignored)?
- [ ] Are additional rights of objection designed for automated decision processes?
- [ ] Is LLM Top 10 additional assessment performed in AI/ML projects?

## 14. ISO 29134 Alignment

ISO 29134 PIA headings map to our template as follows:

| ISO 29134 | Our DPIA Template |
|-----------|----------------------|
| Necessity Justification | Necessity and Proportionality (§5.5) |
| Proportionality Assessment | Necessity and Proportionality + Measure design |
| Risk Assessment | Threat & Risk Identification (§5.7) |
| Mitigation Plan | Measures (§5.9) |
| Stakeholder Consultation | KVKK Committee + stakeholder review |

## 15. Common Mistakes

- Going live with high-risk project without DPIA.
- DPIA handled like "form filling", real threat modeling not done.
- Risk score lacking justification — indefensible in audit.
- Technical side of measure design uncontrolled, organizational/legal side weak.
- Residual risk not documented with management acceptance record.
- Skipping annual review, DPIA not updated despite process change.
- KVKK Officer opinion being cosmetic (no real independence).
- DPIA for AI/ML satisfying with classic template (LLM-specific threats missed).
- Vendor DPIA not included — pre-contract assessment incomplete.

---

## Türkçe

# Kişisel Veri Etki Değerlendirmesi (DPIA / PIA) ve Risk Değerlendirmesi

## 1. Amaç

Yüksek riskli kişisel veri işleme faaliyetlerinin **başlamadan önce** sistematik biçimde değerlendirilmesini, ölçülülük testinden geçirilmesini, risklerin tanımlanıp tedbirlerle azaltılmasını ve KVKK Komitesi'nin onayına sunulmasını sağlar. KVKK m.4 ölçülülük ilkesinin operasyonel ayağıdır; KVKK Kurulu'nun **risk-bazlı uyum** yaklaşımının doğal sonucudur.

> KVKK metni DPIA'yı GDPR Art. 35 gibi açıkça düzenlememekle birlikte, KVKK m.4 genel ilkeleri ve m.12 yükümlülüğü, **risk değerlendirmesinin yapılmadığı yüksek riskli işlemeleri** Kurul nezdinde defacto uyumsuzluk haline getirir. Bu yüzden DPIA, **iyi yönetişim ve uyum kanıtının** ayrılmaz parçasıdır.

## 2. Tanımlar

| Terim | Tanım |
|-------|-------|
| **DPIA / KVED** | Data Protection Impact Assessment — Kişisel Veri Etki Değerlendirmesi. |
| **PIA** | Privacy Impact Assessment (geniş gizlilik değerlendirmesi). |
| **Risk** | Belirli bir tehdidin meydana gelme olasılığı ile ortaya çıkacak etkinin birleşimi. |
| **Artık Risk** | Tedbir alındıktan sonra kalan risk. |
| **Risk İştahı** | Yönetimin kabul etmeye hazır olduğu risk düzeyi. |
| **Tehdit** | Zarara yol açabilecek olay. |
| **Zafiyet** | Tehdidin istismar edebileceği zayıflık. |
| **Tedbir** | Riski azaltmaya yönelik kontrol. |

## 3. DPIA Ne Zaman Zorunlu?

DPIA, aşağıdaki **tetikleyicilerden** biri varsa zorunludur:

### 3.1. Yüksek Risk Senaryoları (KVKK Kurum Rehberleri ve GDPR WP29 önerileri)

1. **Sistemli ve büyük ölçekli profilleme / değerlendirme** — kredi puanlama, sigorta risk skoru, çalışan performans algoritması.
2. **Otomatik karar alma** — KVKK m.5/2(f) "ilgili kişinin temel hak ve özgürlüklerine zarar vermemek kaydıyla" — fakat hak ve özgürlüklere etkisi olabiliyorsa DPIA.
3. **Özel nitelikli veri işleme (KVKK m.6)** — sağlık, biyometrik, genetik, ceza mahkumiyeti, sendika, din vb.
4. **Çocuk verisi** — 18 yaş altı.
5. **Çalışan izleme (sürekli, geniş kapsamlı)** — DLP geniş, kamera, GPS, klavye/ekran yakalama.
6. **Geniş ölçekli kamuya açık alanın izlenmesi** — CCTV ağı, kamuya yüz tanıma.
7. **Yeni teknoloji benimseme** — AI/ML, biyometri, IoT, blockchain, AR/VR.
8. **Birden fazla veri kümesinin birleştirilmesi** (data combination) — sektör pazarı, profil zenginleştirme.
9. **Bir kişiye karşı sözleşme yapma / hizmet sağlama kararının otomatik verilmesi.**
10. **Yurt dışı aktarım** — özellikle yeterli koruma kararı bulunmayan ülkelere.
11. **Sağlık, finans, eğitim alanı** — yüksek hassasiyetli sektörel.
12. **Müşterilerin / çalışanların izleme amacıyla işlenmesi.**

### 3.2. Tetikleyici Tablosu

| Tetik | DPIA |
|-------|------|
| Yeni proje, kişisel veri içeriyor | Risk taraması; yüksek riskli ise DPIA |
| Mevcut süreç yeni teknoloji | DPIA |
| Yeni tedarikçi (Sınıf A) | DPIA bileşenli due diligence |
| Yurt dışı aktarım yeni ülke | DPIA |
| Çalışan izleme aracı yeni | DPIA |
| AI/ML model üretime alma | DPIA |
| Mevzuat değişikliği etki | Mevcut DPIA review |
| Önemli ihlal sonrası | Etkilenen sürecin DPIA review |

## 4. DPIA Süreci

```
1. Tetik (Yeni proje / değişiklik)
2. Risk Taraması (Threshold Assessment) — DPIA gerekli mi?
3. Ekip Oluşturma (süreç sahibi + KVKK Sorumlusu + CISO + Hukuk + BT)
4. Veri Akış Haritalama
5. Gereklilik ve Ölçülülük Testi
6. Tehdit & Risk Tanımlama
7. Tedbir Tasarımı
8. Artık Risk Değerlendirme
9. KVKK Sorumlusu Görüşü
10. KVKK Komitesi Karar (Onay / İyileştirme / Ret)
11. Uygulama ve İzleme
12. Periyodik Review
```

## 5. DPIA Şablonu (Bölümler)

### 5.1. Yönetici Özeti

- Proje / süreç adı.
- Süreç sahibi.
- Hazırlayanlar.
- Hazırlama tarihi.
- Sonuç (onay durumu, koşullar, artık risk seviyesi).

### 5.2. Süreç Tanımı

- Süreç amacı (iş hedefi).
- Faydalanıcılar (ilgili kişi grupları).
- Hizmetin / sürecin akışı (üst düzey).
- İlgili sistemler ve teknolojiler.
- Veri sorumlusu / veri işleyen rolleri.

### 5.3. Veri Akışı

- Veri kategorileri (genel + özel nitelikli).
- Veri kaynağı (ilgili kişiden mi, üçüncü taraftan mı?).
- İşleme adımları (toplama → kullanım → saklama → aktarım → imha).
- Veri akış diyagramı (görsel).
- Aktarım hedefleri (yurt içi / yurt dışı).
- Saklama süreleri.
- İmha yöntemleri.

### 5.4. Hukuki Dayanak

- KVKK m.5 (genel) / m.6 (özel nitelikli) hangi şart?
- Açık rıza alıyorsa: rızanın özgür / aydınlatılmış / belirli olduğunun gösterilmesi.
- Sözleşmenin kurulması, yasal yükümlülük, kamu yararı vb. dayanaklar yazılı.
- Yurt dışı aktarım hukuki mekanizması (m.9).

### 5.5. Gereklilik ve Ölçülülük Testi

KVKK m.4 ölçülülük testi:

- **Amaca uygun mu?** Veri toplanan amaç için gerekli mi?
- **Sınırlı mı?** Daha az veriyle aynı amaca ulaşılabilir mi?
- **Ölçülü mü?** Veri toplama yöntemi, kapsamı orantılı mı?
- **Belirli mi?** Amaç açık ve anlaşılır mı?
- **Saklama süresi makul mu?**
- **Alternatifleri değerlendirildi mi?** (Anonim, sentetik, daha az hassas).

### 5.6. İlgili Kişi Hakları

- Aydınlatma metni hazırlandı mı?
- Açık rıza süreci nasıl?
- Erişim, düzeltme, silme, itiraz, taşınabilirlik, otomatik karara itiraz hakları nasıl uygulanır?
- Başvuru kanalı kayıtlı mı?

### 5.7. Tehdit ve Risk Tanımlama

LINDDUN (gizlilik) + STRIDE (güvenlik) çerçevelerinde:

| # | Tehdit | Etki | Olasılık | Risk Skoru | Tedbir | Artık Risk |
|---|--------|------|----------|------------|--------|------------|
| R1 | Yetkisiz erişim DB'ye | Çok Yüksek | Orta | **Yüksek** | MFA + RLS + audit | Düşük |
| R2 | Veri sorumlusu talimat dışı kullanım (insider) | Yüksek | Düşük | Orta | DLP + UEBA + eğitim | Düşük |
| R3 | Yurt dışı aktarımda yetkisiz erişim | Çok Yüksek | Düşük | Orta | Standart sözleşme + şifreleme + denetim | Düşük |
| R4 | Algoritma yanlış sınıflandırma | Yüksek | Orta | **Yüksek** | İnsan denetimi + DPIA review + itiraz hakkı | Orta |
| ... | ... | ... | ... | ... | ... | ... |

### 5.8. İlgili Kişi Üzerindeki Olası Etki

- Maddi zarar (kayıp, dolandırıcılık).
- Manevi zarar (utanç, ayrımcılık, itibar kaybı).
- Hizmet erişiminin engellenmesi (otomatik karar).
- Mahremiyet ihlali.
- Profil oluşturma sonucu kategori / damga.
- Çocuk için ek hassasiyet.
- Özel nitelikli veri için ek hassasiyet.

### 5.9. Tedbirler

| Kategori | Tedbir |
|----------|--------|
| Teknik | Şifreleme, MFA, RLS, audit log, DLP, anahtar yönetimi |
| İdari | Eğitim, taahhütname, politika, denetim, sözleşme |
| Hukuki | Aydınlatma, rıza, sözleşme şartları, mevzuat takibi |
| Süreçsel | Kontrol noktaları, 4-eyes, periyodik review |
| Veri Mimarisi | Minimizasyon, anonim/pseudonym, veri kalitesi, saklama otomatik |

### 5.10. Artık Risk ve Onay

- Tedbirler sonrası kalan risk skoru.
- Risk iştahıyla karşılaştırma — kabul edilebilir mi?
- Kabul edilemez ise: ek tedbir / proje yeniden tasarım / iptal.
- KVKK Sorumlusu görüş yazısı (ekte).
- KVKK Komitesi karar tutanağı (ekte).

### 5.11. İzleme ve Review

- Hangi sıklıkla review (yıllık, çeyreklik).
- Hangi olaylar review'u tetikler.
- KPI'lar.

## 6. Risk Skor Matrisi

### 6.1. Etki (Impact)

| Seviye | Tanım | Örnek |
|--------|-------|-------|
| 5 — Çok Yüksek | İlgili kişiye geri dönüşü olmayan zarar; geniş ölçekli ifşa | Sağlık verisi kamuya sızdı |
| 4 — Yüksek | Önemli zarar; düzeltme zor | TC kimlik + kart 100K kayıt sızdı |
| 3 — Orta | Düzeltilebilir zarar; geçici hizmet kesintisi | Sınırlı kişisel veri (ad-soyad) sızdı |
| 2 — Düşük | Asgari zarar; hızlı düzeltme | Loglama eksiği fark edildi |
| 1 — Çok Düşük | İhmal edilebilir | Politika güncelleme gecikti |

### 6.2. Olasılık (Likelihood)

| Seviye | Tanım |
|--------|-------|
| 5 — Çok Yüksek | Aktif olarak gerçekleşen veya çok yakın |
| 4 — Yüksek | Yıl içinde gerçekleşmesi olası |
| 3 — Orta | 1-3 yıl içinde olası |
| 2 — Düşük | 3-5 yıl içinde olası |
| 1 — Çok Düşük | Pratik olarak olası değil |

### 6.3. Risk Skoru

```
Risk = Etki × Olasılık
```

| Skor | Sınıf | Aksiyon |
|------|-------|---------|
| 20-25 | Kritik | DERHAL — proje durdurulur, üst yönetim kararı |
| 12-19 | Yüksek | Tedbir mecburi — 30 gün içinde |
| 6-11 | Orta | Tedbir önerilir — 90 gün içinde |
| 1-5 | Düşük | İzlenir — yıllık review |

### 6.4. Risk İştahı

Kurum genel risk iştahı: KVKK ihlal yaratan riski **Düşük seviyede** tolere eder. Yüksek-Kritik risk açıkça gerekçeli + üst yönetim onayı + telafi edici kontroller olmadan kabul edilemez.

## 7. Yönetimsel Roller

| Rol | Sorumluluk |
|-----|-------------|
| Süreç Sahibi (İş Birimi) | DPIA hazırlık talebi, içerik bilgisi sağlama, tedbir uygulama |
| KVKK Sorumlusu | DPIA metodoloji, görüş yazısı, takip |
| CISO ofisi | Teknik tedbir tasarım, tehdit modelleme |
| Hukuk | Hukuki dayanak, sözleşme |
| BT / Mimari | Veri akışı, sistem entegrasyon |
| Risk Yönetimi | Skor, tutarlılık, kurumsal risk entegrasyonu |
| KVKK Komitesi | Onay / ret / koşullu onay kararı |
| İç Denetim | DPIA tatbiki örnekleme denetimi |

## 8. Risk Yönetimi Bağlantıları

DPIA, kurumun **bütüncül risk yönetimi** çerçevesine entegredir:

```
Stratejik Risk (Üst Yönetim)
   ↓
Operasyonel Risk (Risk Yönetimi)
   ├── Bilgi Güvenliği Risk Kayıt (CISO)
   ├── Mahremiyet/KVKK Risk Kayıt (KVKK Sorumlusu) ← DPIA çıktıları buraya
   ├── BT Risk Kayıt
   ├── Tedarikçi Risk Kayıt
   └── İş Sürekliliği Risk
```

Risk kayıtları çeyreklik gözden geçirilir. KVKK riskleri, kurumsal risk kayıtlarına eklenir.

## 9. Hızlı Tarama (Screening / Threshold) Şablonu

DPIA başlatma kararı için kısa form (10 soru, 5 dk):

```
1. Süreç kişisel veri içeriyor mu? (E/H)
2. Özel nitelikli veri (m.6) var mı? (E/H)
3. Çocuk verisi var mı? (E/H)
4. İlgili kişi sayısı 10K+ mi? (E/H)
5. Yeni teknoloji (AI, biyometri, IoT) kullanılıyor mu? (E/H)
6. Otomatik karar / profilleme var mı? (E/H)
7. Çalışan / kullanıcı izleme yapılıyor mu? (E/H)
8. Yurt dışı aktarım var mı? (E/H)
9. Birden fazla veri kümesi birleştiriliyor mu? (E/H)
10. Halka açık alan / kamuoyu izleme var mı? (E/H)

EVET sayısı:
   0-1: DPIA gerekmez (basit risk taraması yeterli)
   2-3: Hafif DPIA (kısa form)
   4+: Tam DPIA
```

## 10. Tipik DPIA Senaryoları (Şablon Başlıkları)

1. **Yeni e-ticaret platformu** — müşteri kaydı, ödeme, profil oluşturma.
2. **Çalışan performans yönetim sistemi** — KPI takibi, otomatik öneri.
3. **AI tabanlı müşteri destek chatbot'u** — sohbet kayıtları, kişisel veri ifşası.
4. **CCTV ağı yenileme** — yeni kamera lokasyonları, yüz tanıma feature'ı.
5. **İK SaaS göçü** — eski sisteme/yeni sisteme geçiş, yurt dışı aktarım.
6. **Yeni biyometrik giriş sistemi** — parmak izi, iris.
7. **Pazarlama otomasyon platformu** — segmentasyon, davranış izleme.
8. **Sağlık check-up programı** — özel nitelikli veri.
9. **Klavye/ekran izleme aracı** — yüksek izleme yoğunluğu.
10. **Çocuğa yönelik eğitim platformu** — ebeveyn rıza süreci.

## 11. Çıktı Saklama

- Tamamlanmış DPIA dokümanı **versiyonlu** ve KVKK Sorumlusu portföyünde.
- Saklama: süreç aktif olduğu sürece + 5 yıl sonrası.
- Erişim: KVKK Sorumlusu, CISO, ilgili Direktör, Hukuk, İç Denetim.
- KVKK Kurulu denetiminde sunulabilir formda hazır.

## 12. KPI

- DPIA gereken proje / DPIA tamamlanan: hedef %100.
- Ortalama DPIA tamamlama süresi: hedef ≤30 gün.
- DPIA review tamamlanma oranı (yıllık): %100.
- Açık DPIA aksiyonları (90 gün geçmiş): 0.
- DPIA sonucu reddedilen proje sayısı: trend takibi.
- DPIA-sonrası ihlal oranı: trend takibi (kalite göstergesi).

## 13. Kontrol Listesi

- [ ] DPIA Standardı yazılı, ≤24 ay güncel mi?
- [ ] Risk taraması (threshold) yeni proje sürecine entegre mi?
- [ ] Tetik listesi güncel, KVKK Kurum rehberleriyle uyumlu mu?
- [ ] DPIA şablonu standart, eksiksiz mi?
- [ ] Risk skor matrisi yazılı, kalibre mi?
- [ ] Risk iştahı yönetim onaylı mı?
- [ ] Her DPIA için ekip rolü atanmış mı?
- [ ] KVKK Sorumlusu bağımsız görüş yazıyor mu?
- [ ] KVKK Komitesi onay tutanakları arşivli mi?
- [ ] Tedbirlerin uygulanması takip ediliyor mu?
- [ ] Yıllık DPIA review takvimi var mı?
- [ ] DPIA çıktıları kurumsal risk kaydına işleniyor mu?
- [ ] DPIA gereken ama yapılmamış proje var mı (gap analizi)?
- [ ] Yıllık iç denetim DPIA örneklemesi yapıyor mu?
- [ ] DPIA ekibinde iş birimi temsilcisi var mı (görmezden gelinmesin)?
- [ ] Otomatik karar süreçleri için ek itiraz hakkı tasarlanmış mı?
- [ ] AI/ML projelerinde LLM Top 10 ek değerlendirmesi yapılıyor mu?

## 14. ISO 29134 Hizalama

ISO 29134 PIA başlıkları bizim şablonla şu şekilde eşleşir:

| ISO 29134 | Bizim DPIA Şablonu |
|-----------|----------------------|
| Necessity Justification | Gereklilik ve Ölçülülük (§5.5) |
| Proportionality Assessment | Gereklilik ve Ölçülülük + Tedbir tasarımı |
| Risk Assessment | Tehdit & Risk Tanımlama (§5.7) |
| Mitigation Plan | Tedbirler (§5.9) |
| Stakeholder Consultation | KVKK Komitesi + paydaş review |

## 15. Yaygın Hatalar

- DPIA yapılmadan yüksek riskli proje canlıya alınması.
- DPIA "form doldurma" gibi ele alınması, gerçek tehdit modelleme yapılmaması.
- Risk skorunun gerekçesiz kalması — denetimde savunulamaz.
- Tedbir tasarımının teknik tarafının kontrolsüz, idari/hukuki tarafının zayıf kalması.
- Artık riskin yönetim kabul tutanağıyla belgelenmemesi.
- Yıllık review'ın atlanması, sürecin değişmesine rağmen DPIA'nın güncellenmemesi.
- KVKK Sorumlusu görüşünün cosmetic olması (gerçek bağımsızlık olmaması).
- AI/ML için DPIA'nın klasik şablonla yetinmesi (LLM-spesifik tehditler kaçırılır).
- Tedarikçi DPIA dahil edilmiyor — sözleşme öncesi değerlendirme eksik.
