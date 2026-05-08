---
Doküman / Document: KVKK ve Bilgi Güvenliği İç Denetim Standardı / KVKK and Information Security Internal Audit Standard
Bölüm / Section: 06-idari-tedbirler
Sahip / Owner: İç Denetim Yöneticisi / Denetim Komitesi / Internal Audit Manager / Audit Committee
Onaylayan / Approved by: Denetim Komitesi + Yönetim Kurulu / Audit Committee + Board of Directors
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık / Annual
İlgili Mevzuat / Legal Reference: Law No. 6698 KVKK Art. 12 (compliance obligation); KVKK Personal Data Security Guide — "Periodic and/or Random Internal Audits"; CMB audit and tendered audit frameworks (where applicable); BDDK / CMB internal audit legislation (sectoral)
İlgili Standart / Standard: ISO/IEC 27001:2022 Clause 9.2 (Internal Audit), Clause 9.3 (Management Review); ISO/IEC 27701:2019; ISO 19011:2018 (Auditing Management Systems); IIA — Institute of Internal Auditors Standards (IPPF); COBIT; NIST CSF 2.0 GV.OV (Oversight); ISACA IS Audit Standards
---

## English

# Internal Audit — KVKK and Information Security

## 1. Purpose

To independently and systematically verify that KVKK and information security compliance **operates as designed**; to surface deficiencies; to track corrective and preventive actions (CAPA); and to provide assurance to management and the KVKK Committee. The operational arm of the "Periodic Internal Audit" measure of the KVKK Personal Data Security Guide.

Internal audit is **independent and objective**; the internal auditor reports separately from the audited process organizationally (Audit Committee / Board of Directors).

## 2. Governance

### 2.1. Structure

```
Board of Directors
   └── Audit Committee (3+ independent members)
         └── Internal Audit Manager (CAE — Chief Audit Executive)
               └── Internal Audit Team (KVKK / IT / Process auditors)
```

### 2.2. Internal Audit Charter

The internal audit charter, approved by the Board of Directors, includes at minimum:

- Mission, scope, authority.
- Independence and objectivity.
- Resources (people, budget).
- Right of access (to every system, document, person).
- Reporting line.
- Compliance with standards (IIA / ISO 19011).
- Annual plan and reporting obligation.

### 2.3. Competencies

Annual development plan for internal audit team:

- KVKK / GDPR certification (CIPP/E or local equivalent).
- ISO 27001 LA / 27701 LI certification.
- CISA (Certified Information Systems Auditor) / CIA (Certified Internal Auditor).
- Sectoral expertise (banking, health, etc.).

## 3. Annual Internal Audit Plan

### 3.1. Risk-Based Plan

The annual plan is prepared based on risk assessment results:

- **High-risk areas:** annual full audit.
- **Medium-risk areas:** audit every 2 years.
- **Low-risk areas:** every 3 years or sampling.

### 3.2. Typical Annual KVKK Audit Topics

| Topic | Frequency |
|------|--------|
| KVKK Policy and document set currency | Annual |
| Data inventory accuracy (sampling) | Annual |
| VERBİS records currency | Annual |
| Privacy notice field check (web, application, registration form) | Annual |
| Explicit consent record sampling | Annual |
| Retention and Destruction — periodic destruction records | Annual |
| Data subject application SLA (30 days) | Annual |
| Data breach record system and 72-hour notification | Annual |
| Vendor contracts and due diligence evidence | Annual |
| Cross-border transfer bases | Annual |
| DPIA records and approval chain | Annual |
| Personnel training completion evidence | Annual |
| Confidentiality undertaking signature status | Annual |
| Cookie management system | Every 2 years |
| Marketing consents (IYS) | Annual |
| Special-category data access audit | Annual |
| Automated decision processes | Annual |

### 3.3. Typical Annual Information Security Audit Topics

| Topic | Frequency |
|------|--------|
| Access management (IAM, JML, RBAC, quarterly review) | Annual |
| Authentication (MFA scope, password, SSO) | Annual |
| Encryption (algorithm, key management, HSM/KMS) | Annual |
| Network security (segmentation, FW rules, perimeter) | Annual |
| Log management and SIEM scope | Annual |
| Backup and restore drill | Annual |
| Data masking / test environment | Annual |
| DLP and leak prevention | Annual |
| Application security (S-SDLC, SAST/DAST, penetration test) | Annual |
| BCP / DR drill | Annual |
| Incident management (IR runbook, KPI) | Annual |
| Cloud security (CSPM, IAM, public bucket) | Annual |
| Endpoint and mobile security | Annual |
| Patch management SLA | Annual |
| Physical security (data center, office) | Every 2 years |
| Vendor right of audit usage | Annual |

### 3.4. Annual Plan Approval

- CAE prepares the plan draft.
- KVKK Officer, CISO, IT Director, Legal provide opinions.
- Audit Committee approves.
- Board of Directors informed.

## 4. Audit Process Steps

### 4.1. Planning

- Topic, scope, target, criteria, resources, timeline.
- Risk assessment.
- Audit questions and test procedure draft.
- Pre-notification to affected teams (except random/spot audit).

### 4.2. Fieldwork

- Document review.
- Interviews.
- System review (application, log, config).
- Sampling (random / risk-based).
- Test procedure application.
- Finding / evidence collection.

### 4.3. Reporting

- Findings categorized.
- Root cause analysis.
- Risk assessment.
- Corrective and preventive action recommendation.
- Process owner response (management response).
- Formal report publication.

### 4.4. Follow-up

- CAPA action plan record.
- Monthly / quarterly follow-up.
- Verification after action closure.
- Reporting open actions to Audit Committee.

## 5. Test Procedures (Examples)

### 5.1. Data Inventory Accuracy

**Goal:** To verify that the inventory accurately reflects actual processing activities.

**Test:**
1. 20 records randomly selected from the inventory.
2. Interview with process owner for each record.
3. Record vs. actual activity comparison:
   - Are data categories correct?
   - Is the retention period applied in practice?
   - Are transfers consistent with what's listed?
   - Is the legal basis still valid?
4. 10 records randomly selected from production, matched with the inventory; are there processes outside the inventory?

**Finding examples:**
- "Marketing automation CRM not in inventory but actively used."
- "Health data tagged as 'general personal data' in inventory, special-category flag not set."
- "Retention period documented as 2 years, in reality not deleted for 5 years."

### 5.2. Privacy Notice Field Check

**Test:**
1. Website main page, registration form, payment, cookie banner — is the privacy notice accessible?
2. Does the privacy notice contain Art. 10 elements (identity, purpose, legal basis, transfer, rights)?
3. Is there a privacy notice within the mobile application?
4. Does the call center initial announcement contain a KVKK privacy notice?
5. Does the physical form (store, event) contain a privacy notice?

### 5.3. Explicit Consent Record Sampling

**Test:**
1. 30 explicit consents randomly selected from the last 3 months.
2. For each:
   - Is the consent timestamp, IP, user agent recorded?
   - Is the consent free (no package/condition)?
   - Is the consent specific (purpose-specific)?
   - Was the privacy notice shown before consent?
   - Is withdrawal as easy?
3. The withdrawal request implementation time in the record is measured.

### 5.4. Vendor Contract Review

**Test:**
1. 10 contracts sampled from Class A/B vendors.
2. For each contract:
   - Is the data processor contract signed?
   - Are minimum elements (instruction, confidentiality, sub-processor, breach notification, audit, termination) present?
   - Is the cross-border transfer mechanism specific?
   - Has annual SOC 2 / ISO 27001 report been received?
3. Contract + implementation consistency (e.g., matching of sub-processor list as contract annex with actual vendor records).

### 5.5. Periodic Destruction Records

**Test:**
1. Quarterly destruction periods (January / April / July / October) determined according to the Retention and Destruction Policy.
2. The last 4 periods of destruction records:
   - Signature chain (owner + witness + KVKK Officer).
   - Number of records destroyed, category.
   - Destruction method (delete / destroy / anonymize).
   - Backup destruction flow.
3. If crypto-shred used, key zeroize record.

### 5.6. Data Subject Application SLA

**Test:**
1. Application records from the last 12 months (KVKK Officer CRM).
2. 20 applications randomly:
   - Application date → response date duration.
   - Was 30-day SLA exceeded?
   - Does the response contain Art. 13 elements?
   - Is the rejected application's reason legal?
   - Is the application evidence / document chain complete?

### 5.7. Data Breach Record System

**Test:**
1. Recorded breach/near-miss incidents from the last 12 months.
2. For each incident:
   - Detection time → KVKK Committee notification → 72-hour Authority notification chain.
   - If 72 hours exceeded, is the justification reasonable?
   - Has notification been made to the affected data subject (if required)?
   - Is root cause analysis + lessons learned documented?
3. Reporting culture of near-miss incidents is evaluated.

### 5.8. MFA Coverage Validation

**Test:**
1. List of admin / personal data application accessing users from IdP.
2. MFA enrollment status of each user.
3. MFA registered ≠ MFA enforced — is the policy actually active?
4. Are there users using SMS OTP but who are admins?

### 5.9. Test Environment Production Data Scan

**Test:**
1. With DLP discovery tool, test/dev databases + storage scan.
2. Are there Turkish ID / IBAN / card no regex matches?
3. Root cause + remediation period for matches.

### 5.10. Training Evidence

**Test:**
1. LMS report: annual refresh completion rate.
2. 30 random new starters:
   - Was onboarding training completed (first 7 days)?
   - Is the confidentiality undertaking signed?
   - Is the knowledge test pass (≥80%)?

## 6. Finding Classification

| Class | Definition | Action SLA |
|-------|-------|-------------|
| **Critical** | Legislative violation, high personal data leak risk, severe financial/reputation loss | 30 days |
| **High** | Major control deficiency, KVKK compliance impact medium-high | 60 days |
| **Medium** | Improvement needed in control effectiveness | 90 days |
| **Low** | Good practice recommendation, opportunity | 180 days |

## 7. Report Format

### 7.1. Standard Report Sections

1. **Executive Summary** (1 page) — scope, period, result, critical findings.
2. **Audit Information** — scope, criteria, period, team.
3. **Methodology** — sampling, test procedure.
4. **Findings** — for each finding: finding, root cause, risk, evidence, recommendation, management response.
5. **Positive Observations** — good practices.
6. **Annual Trend** — progress relative to the previous year.
7. **Conclusion and Overall Assessment** — compliance level, maturity score.
8. **Annexes** — evidence references (confidential, stakeholder-specific).

### 7.2. Finding Template

```
Finding No: KVKK-2026-001
Class: High
Process: Privacy Notice Management
Finding: In the website mobile view, the privacy notice link is under the
       hidden menu, the data subject's access is practically blocked.
Root Cause: KVKK Officer review flow not included in mobile design update.
Risk: KVKK Art. 10 privacy notice obligation, EU GDPR Art. 12 (transparency).
Evidence: Screenshots (Annex-3), test device list.
Recommendation:
   1. Privacy notice should be accessible in max 2 taps in all views.
   2. KVKK Officer review mandatory CI gate for design changes.
Management Response (Marketing Director):
   "In mobile design, the link will be moved to the footer. CI gate added in Q3.
    Action Owner: <name>. Date: <date>."
Target Closure: <date>
Verification: Re-test, screenshot evidence.
```

## 8. CAPA (Corrective and Preventive Action) Tracking

- A CAPA is opened for each finding.
- Tracked in ITSM / GRC tool (ServiceNow, Archer, OneTrust, etc.).
- Action owner, target date, progress percentage, verification evidence.
- Monthly reporting.
- Open critical action over 90 days escalated to Audit Committee.
- For repeating findings, **root cause repetition** analysis.

## 9. Relationship with External Audit

### 9.1. Certification Audit

- ISO 27001 certification annual surveillance + recertification every 3 years.
- ISO 27701 (PIMS) optional, strengthens KVKK compliance.
- SOC 2 Type II — evidence value for international B2B customers.

### 9.2. Sectoral Audit

- BDDK audit (banking).
- CMB audit (publicly traded companies).
- Ministry of Health audit (health sector).
- KVKK Authority audit (every sector; risk-based).

### 9.3. Customer Audit

- Corporate customers send "vendor security questionnaire" or perform site audit.
- Internal audit reports are used as evidence in preparation for these audits.

### 9.4. Independent KVKK Audit

- Independent law firms / consulting firms (OneTrust, BSI, Deloitte, PwC, KPMG, EY) can provide annual KVKK compliance audit.
- Comparison with internal audit results → assurance is strengthened.
- Cost-benefit analysis evaluated annually.

## 10. Management Report Template

Top-level annual report content for KVKK Committee and Board of Directors:

```
1. SCOPE
   - Audit Year: 2026
   - Audited Processes: 14
   - Total Person-Days: 320
   - Number of Findings: 47 (Critical 3, High 11, Medium 24, Low 9)

2. COMPLIANCE LEVEL
   - KVKK Compliance Maturity Score: 78/100 (Competent)
   - Previous Year: 72/100 (+6 points)
   - Target: 85/100 (2027)

3. SUMMARY OF CRITICAL FINDINGS
   3.1. <finding>
   3.2. <finding>
   3.3. <finding>

4. ACTION STATUS
   - Open Action: 18
   - This Year Closed: 41
   - 90-Day Past Due: 2 (escalated)

5. SECTORAL AND REGULATORY TRENDS

6. RISK PROFILE CHANGE

7. RECOMMENDATIONS (FOR SENIOR MANAGEMENT)

8. NEXT YEAR'S PLAN
```

## 11. Maturity Model

| Level | Definition |
|--------|-------|
| 1 — Initial | Ad-hoc, direct response to breach |
| 2 — Repeatable | Some processes documented, person-dependent |
| 3 — Defined | Policies documented, audit performed |
| 4 — Managed | KPIs measured, continuous improvement |
| 5 — Optimized | Predictive control, automation widespread |

Target: Level 4 (Managed) within 2 years.

## 12. Independence and Ethics

- The internal auditor is organizationally separate from the audited process.
- Annual conflict of interest declaration.
- Gift / benefit policy.
- Bound by IIA Ethics Rules.
- Whistleblower hotline managed outside audit; but findings can be recorded.

## 13. Checklist

- [ ] Is the Internal Audit Charter approved, ≤24 months current?
- [ ] Is the annual audit plan risk-based, Audit Committee approved?
- [ ] Does the CAE have an independent reporting line?
- [ ] Is the team competence (certification, experience) sufficient?
- [ ] Are §3.2 and §3.3 topics included in the annual plan?
- [ ] Are test procedures documented, standardized?
- [ ] Are finding classifications and SLAs defined?
- [ ] Is the report template standard, management response mechanism working?
- [ ] Does the CAPA tool track all actions?
- [ ] Are 90-day past due critical actions escalated to Audit Committee?
- [ ] Is the annual management report being prepared?
- [ ] Is there a coordination mechanism with external audit (ISO, SOC, KVKK)?
- [ ] Is the independent KVKK compliance audit option evaluated annually?
- [ ] Is the maturity score being measured, with annual trend tracking?
- [ ] Is root cause repeat analysis done for repeating findings?
- [ ] Is the ethics / conflict of interest declaration taken annually?

## 14. Common Mistakes

- Audit reduced to "yes/no" form, evidence weak.
- Sampling small (5 records), statistically insufficient.
- Management response not filled or evaded.
- Action closure marked "closed" without evidence.
- Same recurring finding year over year, root cause not solved.
- KVKK and information security audits performed without coordination.
- Sectoral additional regulations not included in audit scope.
- Independence violation (auditor in former role in audited area).
- Excessive trust in external audit reports without internal testing.
- Audit results staying only in formal report, not converting to training/communication.

---

## Türkçe

# İç Denetim — KVKK ve Bilgi Güvenliği

## 1. Amaç

KVKK ve bilgi güvenliği uyumunun **tasarlandığı gibi işlediğini** bağımsız ve sistematik biçimde doğrulamak; eksiklikleri ortaya çıkarmak; düzeltici-önleyici aksiyonları (CAPA) takip etmek; yönetime ve KVKK Komitesi'ne güvence sağlamak. KVKK Veri Güvenliği Rehberi'nin "Kurum İçi Periyodik Denetim" tedbirinin operasyonel ayağıdır.

İç denetim **bağımsız ve nesnel**dir; iç denetçi denetlediği süreçten organizasyonel olarak ayrı raporlar (Denetim Komitesi / Yönetim Kurulu).

## 2. Yönetişim

### 2.1. Yapı

```
Yönetim Kurulu
   └── Denetim Komitesi (3+ bağımsız üye)
         └── İç Denetim Yöneticisi (CAE — Chief Audit Executive)
               └── İç Denetim Ekibi (KVKK / BT / Süreç denetçileri)
```

### 2.2. İç Denetim Tüzüğü

İç denetim tüzüğü, Yönetim Kurulu onaylı, asgari aşağıdakileri içerir:

- Misyon, kapsam, yetki.
- Bağımsızlık ve nesnellik.
- Kaynak (insan, bütçe).
- Erişim hakkı (her sistem, doküman, kişiye).
- Raporlama hattı.
- Standartlara uyum (IIA / ISO 19011).
- Yıllık plan ve raporlama yükümlülüğü.

### 2.3. Yetkinlikler

İç denetim ekibi yıllık geliştirme planı:

- KVKK / GDPR sertifikası (CIPP/E veya yerel benzeri).
- ISO 27001 LA / 27701 LI sertifikası.
- CISA (Certified Information Systems Auditor) / CIA (Certified Internal Auditor).
- Sektörel uzmanlık (bankacılık, sağlık vb.).

## 3. Yıllık İç Denetim Planı

### 3.1. Risk-Bazlı Plan

Yıllık plan, risk değerlendirmesi sonucuna göre hazırlanır:

- **Yüksek riskli alanlar:** yıllık tam denetim.
- **Orta riskli alanlar:** 2 yılda bir denetim.
- **Düşük riskli alanlar:** 3 yılda bir veya örnekleme.

### 3.2. Tipik Yıllık KVKK Denetim Konuları

| Konu | Sıklık |
|------|--------|
| KVKK Politikası ve doküman seti güncellik | Yıllık |
| Veri envanteri doğruluğu (örnekleme) | Yıllık |
| VERBİS kayıtlarının güncelliği | Yıllık |
| Aydınlatma metni saha kontrolü (web, başvuru, kayıt formu) | Yıllık |
| Açık rıza kayıt örneklemesi | Yıllık |
| Saklama ve İmha — periyodik imha tutanakları | Yıllık |
| İlgili kişi başvuru SLA (30 gün) | Yıllık |
| Veri ihlali kayıt sistemi ve 72 saat bildirim | Yıllık |
| Tedarikçi sözleşmeleri ve due diligence kanıtı | Yıllık |
| Yurt dışı aktarım dayanakları | Yıllık |
| DPIA kayıtları ve onay zinciri | Yıllık |
| Personel eğitim tamamlama kanıtı | Yıllık |
| Gizlilik taahhütname imza durumu | Yıllık |
| Çerez yönetim sistemi | 2 yılda bir |
| Pazarlama izinleri (İYS) | Yıllık |
| Özel nitelikli veri erişim audit | Yıllık |
| Otomatik karar süreçleri | Yıllık |

### 3.3. Tipik Yıllık Bilgi Güvenliği Denetim Konuları

| Konu | Sıklık |
|------|--------|
| Erişim yönetimi (IAM, JML, RBAC, çeyreklik review) | Yıllık |
| Kimlik doğrulama (MFA kapsamı, parola, SSO) | Yıllık |
| Şifreleme (algoritma, anahtar yönetimi, HSM/KMS) | Yıllık |
| Ağ güvenliği (segmentasyon, FW kuralları, perimeter) | Yıllık |
| Log yönetimi ve SIEM kapsamı | Yıllık |
| Yedekleme ve restore tatbikatı | Yıllık |
| Veri maskeleme / test ortamı | Yıllık |
| DLP ve sızıntı önleme | Yıllık |
| Uygulama güvenliği (S-SDLC, SAST/DAST, sızma testi) | Yıllık |
| BCP / DR tatbikat | Yıllık |
| Olay yönetimi (IR runbook, KPI) | Yıllık |
| Bulut güvenliği (CSPM, IAM, public bucket) | Yıllık |
| Endpoint ve mobil güvenlik | Yıllık |
| Patch yönetimi SLA | Yıllık |
| Fiziksel güvenlik (veri merkezi, ofis) | 2 yılda bir |
| Tedarikçi denetim hakkı kullanımı | Yıllık |

### 3.4. Yıllık Plan Onay

- CAE plan taslağını hazırlar.
- KVKK Sorumlusu, CISO, BT Direktörü, Hukuk görüş bildirir.
- Denetim Komitesi onaylar.
- Yönetim Kurulu bilgilendirilir.

## 4. Denetim Sürecinin Adımları

### 4.1. Planlama

- Konu, kapsam, hedef, kriter, kaynak, takvim.
- Risk değerlendirme.
- Denetim soruları ve test prosedürü taslak.
- Etkilenen ekiplere ön bildirim (rastgele/spot denetim hariç).

### 4.2. Saha Çalışması (Fieldwork)

- Doküman incelemesi.
- Görüşmeler (interview).
- Sistem inceleme (uygulama, log, konfig).
- Örnekleme (random / risk-bazlı).
- Test prosedürü uygulama.
- Bulgu / kanıt toplama.

### 4.3. Raporlama

- Bulgular kategorize edilir.
- Kök neden analizi.
- Risk değerlendirmesi.
- Düzeltici ve önleyici aksiyon önerisi.
- Süreç sahibi cevabı (yönetim cevabı).
- Rapor formal yayını.

### 4.4. Takip (Follow-up)

- CAPA aksiyon planı kayıt.
- Aylık / çeyreklik takip.
- Aksiyon kapanma sonrası doğrulama.
- Açık aksiyonların Denetim Komitesi'ne raporlanması.

## 5. Test Prosedürleri (Örnekler)

### 5.1. Veri Envanteri Doğruluğu

**Hedef:** Envanterin gerçek işleme faaliyetlerini doğru yansıttığını doğrulamak.

**Test:**
1. Envanterden 20 kayıt rastgele seçilir.
2. Her kayıt için süreç sahibiyle görüşme.
3. Kayıt vs. gerçek faaliyet karşılaştırması:
   - Veri kategorileri doğru mu?
   - Saklama süresi pratikte uygulanıyor mu?
   - Aktarımlar listelenenle uyumlu mu?
   - Hukuki dayanak halen geçerli mi?
4. Üretimden 10 kayıt rastgele seçilir, hangi süreçte oluştuğu envanterle eşleştirilir; envanter dışı süreç var mı?

**Bulgu örnekleri:**
- "Pazarlama otomasyon CRM'i envanterde yok ama aktif kullanılıyor."
- "Sağlık verisi envantere `genel kişisel veri` olarak işlenmiş, özel nitelikli flag'i konmamış."
- "Saklama süresi 2 yıl yazılı, gerçekte 5 yıldır silinmiyor."

### 5.2. Aydınlatma Metni Saha Kontrolü

**Test:**
1. Web sitesi ana sayfa, kayıt formu, ödeme, çerez banner — aydınlatma erişilebilir mi?
2. Aydınlatma metni m.10 unsurlarını içeriyor mu (kimlik, amaç, hukuki sebep, aktarım, haklar)?
3. Mobil uygulama içinde aydınlatma var mı?
4. Çağrı merkezi başlangıç anonsu KVKK aydınlatma içeriyor mu?
5. Fiziksel form (mağaza, etkinlik) aydınlatma metni içeriyor mu?

### 5.3. Açık Rıza Kayıt Örneklemesi

**Test:**
1. Son 3 ayda alınan 30 açık rıza rastgele seçilir.
2. Her biri için:
   - Rıza zaman damgası, IP, kullanıcı agent kayıtlı mı?
   - Rıza özgür mü (paket/koşul yok)?
   - Rıza belirli mi (amaç-spesifik)?
   - Aydınlatma rıza öncesi gösterilmiş mi?
   - Geri çekme aynı kolaylıkta mı?
3. Geri çekme talebinin kayıttaki uygulanma süresi ölçülür.

### 5.4. Tedarikçi Sözleşmesi Review

**Test:**
1. Sınıf A/B tedarikçilerden 10 sözleşme örneklenir.
2. Her sözleşme için:
   - Veri İşleyen sözleşmesi imzalı mı?
   - Asgari unsurlar (talimat, gizlilik, alt-işleyen, ihlal bildirim, denetim, fesih) var mı?
   - Yurt dışı aktarım mekanizması belirli mi?
   - Yıllık SOC 2 / ISO 27001 raporu alınmış mı?
3. Sözleşme + uygulama tutarlılık (örn. alt-işleyen listesi sözleşme eki ile gerçek tedarikçi kayıt eşleşmesi).

### 5.5. Periyodik İmha Tutanakları

**Test:**
1. Saklama ve İmha Politikası'na göre belirlenmiş çeyreklik imha dönemi (Ocak / Nisan / Temmuz / Ekim).
2. Son 4 dönemin imha tutanakları:
   - İmza zinciri (sahip + tanık + KVKK Sorumlusu).
   - İmha edilen kayıt sayısı, kategori.
   - İmha yöntemi (silme / yok etme / anonim).
   - Yedeklerden imha akışı.
3. Crypto-shred kullanılıyorsa anahtar zeroize tutanağı.

### 5.6. İlgili Kişi Başvuru SLA

**Test:**
1. Son 12 ayda gelen başvurular kaydı (KVKK Sorumlusu CRM).
2. 20 başvuru rastgele:
   - Başvuru tarihi → cevap tarihi süresi.
   - 30 gün SLA aşıldı mı?
   - Cevap m.13 unsurlarını içeriyor mu?
   - Reddedilen başvuru gerekçesi yasal mı?
   - Başvuru kanıtı / belge zinciri tam mı?

### 5.7. Veri İhlali Kayıt Sistemi

**Test:**
1. Son 12 ayda kayıtlı ihlal/ramak kala olayları.
2. Her olay için:
   - Tespit zamanı → KVKK Komitesi bildirim → 72 saat Kurul bildirim zinciri.
   - 72 saat aşıldıysa gerekçe makul mü?
   - Etkilenen ilgili kişiye bildirim yapıldı mı (gerekiyorsa)?
   - Kök neden analizi + lessons learned dokümante mi?
3. Ramak kala olayların raporlanma kültürü değerlendirilir.

### 5.8. MFA Kapsam Doğrulama

**Test:**
1. IdP'den admin / kişisel veri uygulama erişen kullanıcı listesi.
2. Her kullanıcının MFA kayıt durumu.
3. MFA registered ≠ MFA enforced — politika gerçekten aktif mi?
4. SMS OTP kullanan ama yönetici olan kullanıcı var mı?

### 5.9. Test Ortamı Üretim Verisi Taraması

**Test:**
1. DLP discovery aracıyla test/dev veritabanları + storage taraması.
2. TC kimlik / IBAN / kart no regex eşleşmesi var mı?
3. Eşleşmeler için kök neden + remediation süresi.

### 5.10. Eğitim Kanıtı

**Test:**
1. LMS rapor: yıllık tazeleme tamamlama oranı.
2. 30 yeni başlayan rastgele:
   - Onboarding eğitim tamamlandı mı (ilk 7 gün)?
   - Gizlilik taahhütnamesi imzalı mı?
   - Bilgi testi başarı (≥%80)?

## 6. Bulgu Sınıflandırması

| Sınıf | Tanım | Aksiyon SLA |
|-------|-------|-------------|
| **Kritik** | Mevzuat ihlali, kişisel veri sızıntısı riski yüksek, ciddi finansal/itibar kaybı | 30 gün |
| **Yüksek** | Önemli kontrol eksikliği, KVKK uyum etkisi orta-yüksek | 60 gün |
| **Orta** | Kontrol etkinliğinde iyileştirme gerekli | 90 gün |
| **Düşük** | İyi uygulama önerisi, fırsat | 180 gün |

## 7. Rapor Formatı

### 7.1. Standart Rapor Bölümleri

1. **Yönetici Özeti** (1 sayfa) — kapsam, dönem, sonuç, kritik bulgular.
2. **Denetim Bilgisi** — kapsam, kriter, dönem, ekip.
3. **Metodoloji** — örnekleme, test prosedürü.
4. **Bulgular** — her bulgu için: bulgu, kök neden, risk, kanıt, öneri, yönetim cevabı.
5. **Olumlu Gözlemler** — iyi uygulamalar.
6. **Yıllık Trend** — önceki yıla göre ilerleme.
7. **Sonuç ve Genel Değerlendirme** — uyum seviyesi, olgunluk skoru.
8. **Ekler** — kanıt referansları (gizli, paydaşa özel).

### 7.2. Bulgu Şablonu

```
Bulgu No: KVKK-2026-001
Sınıf: Yüksek
Süreç: Aydınlatma Yönetimi
Bulgu: Web sitesi mobil görünümünde aydınlatma metni linki hidden menü altında, 
       ilgili kişinin erişimi pratik olarak engelleniyor.
Kök Neden: Mobil tasarım güncellemesinde KVKK Sorumlusu review akışına dahil edilmemiş.
Risk: KVKK m.10 aydınlatma yükümlülüğü, AB GDPR Art. 12 (şeffaflık).
Kanıt: Ekran görüntüleri (Ek-3), test cihazı listesi.
Öneri: 
   1. Aydınlatma metni tüm görünümlerde max 2 dokunuşla erişilebilir olmalı.
   2. Tasarım değişikliklerinde KVKK Sorumlusu review zorunlu CI gate.
Yönetim Cevabı (Pazarlama Direktörü):
   "Mobil tasarımda link footer'a taşınacak. CI gate Q3'te eklenecek.
    Aksiyon Sahibi: <isim>. Tarih: <tarih>."
Hedef Kapanış: <tarih>
Doğrulama: Re-test, ekran görüntüsü kanıtı.
```

## 8. CAPA (Corrective and Preventive Action) Takibi

- Her bulguya bir CAPA açılır.
- ITSM / GRC aracında (ServiceNow, Archer, OneTrust, vs.) tutulur.
- Aksiyon sahibi, hedef tarihi, ilerleme yüzdesi, doğrulama kanıtı.
- Aylık raporlama.
- 90 gün geçmiş açık kritik aksiyon Denetim Komitesi'ne eskalasyon.
- Tekrarlayan bulgular için **kök neden tekrarı** analizi.

## 9. Dış Denetim ile İlişki

### 9.1. Sertifikasyon Denetimi

- ISO 27001 sertifikasyonu yıllık gözetim + 3 yılda bir yeniden belgelendirme.
- ISO 27701 (PIMS) opsiyonel, KVKK uyumunu güçlendirir.
- SOC 2 Type II — uluslararası B2B müşteriler için kanıt değeri.

### 9.2. Sektörel Denetim

- BDDK denetimi (bankacılık).
- SPK denetimi (halka açık şirketler).
- Sağlık Bakanlığı denetimi (sağlık sektörü).
- KVKK Kurum denetimi (her sektör; risk-bazlı).

### 9.3. Müşteri Denetimi

- Kurumsal müşteriler "vendor security questionnaire" gönderir veya saha denetimi yapar.
- Bu denetimlere hazırlık için iç denetim raporları kanıt olarak kullanılır.

### 9.4. Bağımsız KVKK Denetimi

- Bağımsız hukuk büroları / danışmanlık şirketleri (OneTrust, BSI, Deloitte, PwC, KPMG, EY) yıllık KVKK uyum denetimi sağlayabilir.
- İç denetim sonuçlarıyla karşılaştırma → güvence güçlenir.
- Maliyet-fayda analizi yıllık değerlendirilir.

## 10. Yönetim Raporu Şablonu

KVKK Komitesi ve Yönetim Kurulu'na yıllık üst düzey raporun temel içeriği:

```
1. KAPSAM
   - Denetim Yılı: 2026
   - Denetlenen Süreçler: 14
   - Toplam Adam-Gün: 320
   - Bulgu Sayısı: 47 (Kritik 3, Yüksek 11, Orta 24, Düşük 9)

2. UYUM SEVİYESİ
   - KVKK Uyum Olgunluk Skoru: 78/100 (Yetkin)
   - Önceki Yıl: 72/100 (+6 puan)
   - Hedef: 85/100 (2027)

3. KRİTİK BULGULARIN ÖZETİ
   3.1. <bulgu>
   3.2. <bulgu>
   3.3. <bulgu>

4. AKSİYON DURUMU
   - Açık Aksiyon: 18
   - Bu Yıl Kapanan: 41
   - 90 Gün Geçmiş Açık: 2 (eskalasyon edildi)

5. SEKTÖREL VE MEVZUAT TRENDLERİ

6. RİSK PROFİLİ DEĞİŞİMİ

7. TAVSİYELER (ÜST YÖNETİM İÇİN)

8. GELECEK YIL PLAN
```

## 11. Olgunluk Modeli

| Seviye | Tanım |
|--------|-------|
| 1 — Başlangıç | Ad-hoc, doğrudan ihlale tepki |
| 2 — Tekrarlanabilir | Bazı süreçler dokümanlı, kişiye bağlı |
| 3 — Tanımlı | Politikalar yazılı, denetim yapılır |
| 4 — Yönetilen | KPI'lar ölçülür, sürekli iyileştirme |
| 5 — Optimize | Öngörücü kontrol, otomasyon yaygın |

Hedef: 2 yıl içinde Seviye 4 (Yönetilen).

## 12. Bağımsızlık ve Etik

- İç denetçi, denetlediği süreçten organizasyonel olarak ayrı.
- Çıkar çatışması beyanı yıllık.
- Hediye / faydacılık politikası.
- IIA Etik Kuralları'na bağlı.
- Whistleblower hattı denetim dışı yönetilir; ancak bulguları kayda alınabilir.

## 13. Kontrol Listesi

- [ ] İç Denetim Tüzüğü onaylı, ≤24 ay güncel mi?
- [ ] Yıllık denetim planı risk-bazlı, Denetim Komitesi onaylı mı?
- [ ] CAE bağımsız raporlama hattına sahip mi?
- [ ] Ekip yetkinliği (sertifika, deneyim) yeterli mi?
- [ ] §3.2 ve §3.3'teki konular yıllık plana dahil mi?
- [ ] Test prosedürleri yazılı, standartlaşmış mı?
- [ ] Bulgu sınıflandırması ve SLA tanımlı mı?
- [ ] Rapor şablonu standart, yönetim cevap mekanizması işliyor mu?
- [ ] CAPA aracı tüm aksiyonları takip ediyor mu?
- [ ] 90 gün geçmiş kritik aksiyon Denetim Komitesi'ne eskalasyon ediliyor mu?
- [ ] Yıllık yönetim raporu hazırlanıyor mu?
- [ ] Dış denetim (ISO, SOC, KVKK) ile koordinasyon mekanizması var mı?
- [ ] Bağımsız KVKK uyum denetimi opsiyonu yıllık değerlendiriliyor mu?
- [ ] Olgunluk skoru ölçülüyor, yıllık trend takibi var mı?
- [ ] Tekrarlayan bulgular için kök neden tekrar analizi yapılıyor mu?
- [ ] Etik / çıkar çatışması beyanı yıllık alınıyor mu?

## 14. Yaygın Hatalar

- Denetim "evet/hayır" formuna indirgenmiş, kanıt zayıf.
- Örnekleme küçük (5 kayıt), istatistiksel olarak yetersiz.
- Yönetim cevabının doldurulmaması veya geçiştirilmesi.
- Aksiyonların kapanış kanıtı olmadan "kapatıldı" işaretlenmesi.
- Tekrarlayan aynı bulgu yıldan yıla, kök neden çözülmemiş.
- KVKK ve bilgi güvenliği denetimlerinin koordinasyonsuz yapılması.
- Sektörel ek mevzuatın denetim kapsamına alınmaması.
- Bağımsızlık ihlali (denetçi denetlediği alanda eski rolde).
- Dış denetim raporlarına gereğinden çok güvenip iç testin yapılmaması.
- Denetim sonuçlarının yalnızca formal raporda kalıp eğitim/iletişime dönmemesi.
