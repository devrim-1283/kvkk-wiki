---
Doküman / Document: Politikalar ve Prosedürler — Doküman Yönetimi Standardı / Policies and Procedures — Document Management Standard
Bölüm / Section: 06-idari-tedbirler
Sahip / Owner: KVKK Sorumlusu / CISO (Bilgi Güvenliği Politikaları için) / KVKK Officer / CISO (for Information Security Policies)
Onaylayan / Approved by: KVKK Komitesi + İlgili Direktör + Üst Yönetim (üst seviye için Yönetim Kurulu) / KVKK Committee + Relevant Director + Senior Management (Board of Directors for top-level)
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş (mevzuat değişikliği, organizasyonel değişim, ihlal) / Annual + triggered (regulatory change, organizational change, breach)
İlgili Mevzuat / Legal Reference: Law No. 6698 KVKK Art. 12; KVKK Personal Data Security Guide — "Corporate Policies"
İlgili Standart / Standard: ISO/IEC 27001:2022 Clause 5.2 (Policy), 7.5 (Documented Information), Annex A.5.1, A.5.2; ISO/IEC 27701:2019; NIST CSF 2.0 GV.PO; NIST SP 800-53 PM-1
---

## English

# Policies and Procedures

## 1. Purpose

Defines the **policy set**, **document lifecycle**, **approval chain**, and **publication/access** rules that the organization must have for KVKK compliance and information security. The operational implementation of the measure required under "Corporate Policies" in the KVKK Personal Data Security Guide.

## 2. Document Types and Hierarchy

| Level | Type | Example | Approver | Period |
|--------|-----|-------|-----------|------|
| 1 | Top-Level Policy (Charter / Manifesto) | KVKK Policy, Information Security Policy | Board of Directors | 2 years |
| 2 | Policy | Access Management, Retention, Vendor | Senior Management + KVKK Committee | 2 years |
| 3 | Standard | Encryption Standard, Logging Standard | Director + CISO | 1-2 years |
| 4 | Procedure / Working Instruction | Joiner-Leaver Procedure | Process Owner + KVKK Officer | 1 year |
| 5 | Template / Form / Checklist | Data Processor Contract Template | Legal + KVKK Officer | 1 year |

**Rule:** Lower-level documents cannot conflict with the upper level. The lower level is revised when conflict is detected.

## 3. Minimum Policy Set (Data Controller — 500+ Employees)

### 3.1. Top-Level

1. **KVKK Policy** — Top-level document setting out the company's approach, principles, responsibilities and data subject rights regarding personal data processing.
2. **Information Security Policy** — Organizational approach within the CIA triad framework, responsibility, acceptable use, compliance.

### 3.2. KVKK / Privacy Focused

3. **Privacy Notice Standard** — Content, language, publication channel for the obligation under Art. 10.
4. **Explicit Consent Management Policy** — Consent collection, recording, withdrawal processes.
5. **Retention and Destruction Policy** — Compliant with KVKK Art. 7 and Destruction Regulation.
6. **Data Subject Application Management Procedure** — Application channel under Art. 11/13, identity verification, SLA.
7. **Data Breach Management Procedure** — Detection, containment, notification, recording.
8. **Data Transfer Policy** — Domestic and cross-border transfer rules, Art. 9.
9. **VERBİS Management Procedure** — Responsibility for keeping the registry current.
10. **Cookie Policy** — Website cookies, categories, opt-in/out.
11. **Marketing Communications Policy** — KVKK + Electronic Commerce Law (IYS) compliant.
12. **Employee Privacy Policy** — How employee data is processed, monitoring practices.
13. **CCTV / Camera Policy** — Image recording purpose, duration, sharing.
14. **Personal Data Impact Assessment (DPIA) Standard** — When and how it's done.

### 3.3. Information Security — Operational

15. **Access Management Standard** — RBAC, JML, PAM (see [05-teknik-tedbirler/erisim-kontrolu.md](../05-teknik-tedbirler/erisim-kontrolu.md)).
16. **Authentication Standard** — MFA, password, SSO.
17. **Encryption Standard** — Algorithm, key management.
18. **Network Security Standard** — Segmentation, perimeter, ZTNA.
19. **Backup and Business Continuity Standard** — RPO/RTO, restore test.
20. **Logging and Monitoring Standard** — Logging, SIEM, retention.
21. **DLP / Data Leakage Prevention Standard**.
22. **Application Security / S-SDLC Standard**.
23. **Mobile and Remote Work Policy** — BYOD, MDM.
24. **Clean Desk — Clean Screen Policy** — Physical privacy.
25. **Social Engineering and Phishing Policy** — Training, simulation, reporting.
26. **Incident Management (IR) Procedure** — RB-01..RB-12 runbook set.
27. **Change Management Policy** — CAB, emergency change.
28. **Acceptable Use Policy (AUP)** — Employee behavior, internet, social media.

### 3.4. Vendor and Third Party

29. **Vendor Management Policy** — Classification, due diligence, monitoring.
30. **Data Processor Contract Standard Clauses** — Minimum elements, right of audit.
31. **Cloud Service Use Policy** — Approved provider list, data location.

### 3.5. HR and Training

32. **Onboarding and Departure Policy (KVKK Linkage)** — Personnel file, confidentiality undertaking, access closure on departure.
33. **Personnel Training and Awareness Program** — Annual curriculum.
34. **Discipline Policy — Information Security Violations** — Violation classes and sanctions.

### 3.6. Governance

35. **KVKK Committee Working Procedures** — Members, meeting, decision.
36. **Risk Management Policy** — Risk appetite, scoring.
37. **Internal Audit Charter and Annual Plan** — Independence, scope.
38. **Policy and Document Management Policy** — This document.

## 4. Policy Lifecycle

```
Trigger (new risk / regulation / gap)
   → 1. Draft (Owner team)
   → 2. Stakeholder Review (Legal, IT, HR, KVKK Officer, relevant business unit)
   → 3. Senior Management / Committee Approval
   → 4. Publication (intranet, email announcement, training)
   → 5. Implementation (operational steps)
   → 6. Monitoring & Measurement (KPI, audit)
   → 7. Periodic Review (≤2 years)
   → 8. Revision / Withdrawal
```

## 5. Standard Policy Template (Sections)

The following sections are present in every policy document:

1. **Title + Meta Information** (version, owner, approver, effective date, review date).
2. **Purpose** — The problem solved by the policy.
3. **Scope** — Which persons, systems, locations are included.
4. **Definitions** — Disputed / technical terms.
5. **Roles and Responsibilities** — RACI.
6. **Policy Provisions** — What must and must not be done.
7. **Exceptions** — Exception request process.
8. **Measurement / KPI** — Effectiveness indicators.
9. **Non-Compliance and Sanctions** — Reference to discipline process.
10. **Related Documents** — Upper/lower policies, legislation.
11. **Revision History** — Date, change summary, approver.

## 6. Approval Chain

| Document Type | Prepared By | Review (mandatory) | Approver | Publication |
|--------------|------------|-------------------|------------|-------|
| Top-Level Policy | KVKK Officer / CISO | Legal + Full Committee + Senior Management | Board of Directors | Intranet + General announcement |
| Policy (Level 2) | Owner team | Legal + KVKK Officer + CISO + Relevant Director | KVKK Committee + Senior Management | Intranet + email |
| Standard | Technical team + CISO office | KVKK Officer + Relevant Director | CISO + Relevant Director | Intranet |
| Procedure | Process Owner | Process stakeholders + KVKK Officer | Relevant Manager | Intranet |
| Template / Form | Process Owner | Legal + KVKK Officer | KVKK Officer | Intranet |

Approval is documented with e-signature or wet signature; evidence PDF + meta-data in archive.

## 7. Publication and Communication

- **Publication Channel:** Intranet policy library (Confluence / SharePoint, etc.) — single authoritative source.
- **Version Information:** At the top of each document and in the file name (e.g., `KVKK-Policy-v2.0-2026.pdf`).
- **New Publication:** Company-wide email + departmental notification. 30-minute briefing for critical policy.
- **Translation:** Original Turkish + English available (for international subsidiaries).
- **Accessibility:** Publication format adjusted for accessibility standards (WCAG 2.1 AA).

## 8. Versioning Rule

- **MAJOR.MINOR** (e.g., 2.1).
- **MAJOR** — Purpose, scope or important provision of the policy changed.
- **MINOR** — Description, example, minor revision.
- Annual review may produce a minor version.
- Each version a separate record; reversible.

## 9. Old Version Management

- The old version is moved to "ARCHIVE" folder, the new version is published.
- Employees acting on old version is prevented (old version explicitly stamped "invalid").
- In possible legal investigation / audit cases, the old version is kept for 5 years.
- Within 30 days following version change, all employees confirm read of the new version (for critical policy).

## 10. Periodic Review

### 10.1. Annual Triggers

- Legal change (KVKK, secondary legislation, sectoral regulation).
- Organizational change (organization, M&A, new line of business).
- Technological change (new cloud, new IdP, new AI system).
- Breach or near-miss incident.
- Independent audit finding.
- KVKK Authority decision / sectoral guide refresh.

### 10.2. Review Flow

1. KVKK Officer announces annual schedule (Q1).
2. Each document owner opens their document for review.
3. If change required, draft updated, stakeholder review.
4. Approval chain triggered.
5. Publication + communication.
6. Review completion report to Committee.

## 11. Exception Management

- Exceptions can be **written, justified, time-limited, with compensating controls, approved**.
- Exception form: who, why, which clause, compensating control, duration (≤180 days), risk owner, KVKK Officer opinion.
- Exception register kept; annual review.
- Exception accumulation signals need for policy revision.

## 12. Non-Compliance and Sanctions

- Non-compliance is evaluated according to the Discipline Policy.
- Classification:
  - **A — Intentional / Severe:** Data disclosure, intentional access violation → up to termination and legal process.
  - **B — Negligence / Repeated:** Written warning + mandatory training.
  - **C — Mistake / First time:** Training reminder.
- For vendor non-compliance, contract clause is triggered.
- KVKK Officer informs the Committee in case of breach.

## 13. Policy Template (Markdown — short example beginning)

```markdown
---
Document: <title>
Owner: <team / person>
Approver: <committee>
Version: 1.0
Effective: YYYY-MM-DD
Review: <date>
Legal Reference: ...
Standard: ...
---

# 1. Purpose
# 2. Scope
# 3. Definitions
# 4. Roles and Responsibilities
# 5. Policy Provisions
# 6. Exceptions
# 7. Measurement
# 8. Non-Compliance and Sanctions
# 9. Related Documents
# 10. Revision History
```

## 14. Document Management System (DMS) Expectations

- Version control, audit trail, access control.
- Embedded approval workflow.
- Automatic review reminders (90, 30, 7 days in advance).
- "Read" record (for critical policies).
- Search (full-text), tag / category.
- Old version archive (read-only).
- Typical candidates: Confluence + Comala Workflow, SharePoint + Power Automate, GitOps approach (Markdown + git PR review + CI publishing).

## 15. KPI

- Policy currency (≤24 months): target 100%.
- Annual review completion: 100%.
- "Read" rate (new starter, within orientation week): 100%.
- "Read" rate within 30 days after critical policy revision: ≥95%.
- Number of open exceptions: trend tracking (target decrease per year).
- Number of non-compliance events: monthly trend.

## 16. Checklist

- [ ] Are KVKK Policy and Information Security Policy present, ≤2 years current?
- [ ] Are the 38 documents listed in §3 present (justified if scope is not appropriate)?
- [ ] Do all documents conform to the standard template (version, approver, effective date)?
- [ ] Is the approval chain documented?
- [ ] Is the DMS audit trail active?
- [ ] Has the annual review schedule been published?
- [ ] Are old versions kept in the archive for 5 years?
- [ ] Is the exception register current, time-bound, with compensating controls?
- [ ] Are "read" records 100% for new starters?
- [ ] Is the critical policy revision communicated to employees?
- [ ] Are the original Turkish + English versions consistent?
- [ ] Is the policy hierarchy conflict check done annually?
- [ ] Are the KPIs reported annually, presented to the KVKK Committee?
- [ ] Does the Discipline Policy include classification of information security violations?
- [ ] Is there a "vendor compliance with our policies" clause in vendor contracts?

## 17. Common Mistakes

- Policy documents not updated for years, with statements conflicting with legislation.
- "Written but not implemented" — no KPI measurement.
- Employee doesn't know which policy is in effect (intranet clutter).
- No standard template — every policy in different language and structure.
- "Read" only formal, no comprehension test.
- Use of exceptions normalized outside policy.
- Old version mistakenly thought to be in effect and applied.
- No reference to policies in vendor contract, missing minimum elements.

---

## Türkçe

# Politikalar ve Prosedürler

## 1. Amaç

Kurumun KVKK uyumu ve bilgi güvenliği için sahip olması gereken **politika setini**, **doküman yaşam döngüsünü**, **onay zincirini** ve **yayınlama/erişim** kurallarını tanımlar. KVKK Veri Güvenliği Rehberi'nde "Kurumsal Politikalar" başlığı altında talep edilen tedbirin operasyonel uygulamasıdır.

## 2. Doküman Tipleri ve Hiyerarşi

| Seviye | Tip | Örnek | Onaylayan | Süre |
|--------|-----|-------|-----------|------|
| 1 | Üst Düzey Politika (Charter / Manifesto) | KVKK Politikası, Bilgi Güvenliği Politikası | Yönetim Kurulu | 2 yıl |
| 2 | Politika | Erişim Yönetimi, Saklama, Tedarikçi | Üst Yönetim + KVKK Komitesi | 2 yıl |
| 3 | Standart | Şifreleme Standardı, Loglama Standardı | Direktör + CISO | 1-2 yıl |
| 4 | Prosedür / Çalışma Talimatı | Joiner-Leaver İşlemi Prosedürü | Süreç Sahibi + KVKK Sorumlusu | 1 yıl |
| 5 | Şablon / Form / Kontrol Listesi | Veri İşleyen Sözleşme Şablonu | Hukuk + KVKK Sorumlusu | 1 yıl |

**Kural:** Alt seviye doküman, üst seviyeyle çelişemez. Çelişki bulunduğunda alt seviye revize edilir.

## 3. Asgari Politika Seti (Veri Sorumlusu — 500+ Çalışan)

### 3.1. Üst Düzey

1. **KVKK Politikası** — Şirketin kişisel veri işleme yaklaşımını, ilkelerini, sorumluluklarını ve ilgili kişi haklarını ortaya koyan üst düzey doküman.
2. **Bilgi Güvenliği Politikası** — CIA üçlüsü çerçevesinde kurumun yaklaşımı, sorumluluk, kabul edilebilir kullanım, uyum.

### 3.2. KVKK / Mahremiyet Odaklı

3. **Aydınlatma Metni Standardı** — m.10 yükümlülüğü için içerik, dil, yayın kanalı.
4. **Açık Rıza Yönetimi Politikası** — Rıza alma, kayıt, geri çekme süreçleri.
5. **Saklama ve İmha Politikası** — KVKK m.7 ve İmha Yönetmeliği uyumlu.
6. **İlgili Kişi Başvuru Yönetimi Prosedürü** — m.11/13 başvuru kanalı, kimlik doğrulama, SLA.
7. **Veri İhlali Yönetimi Prosedürü** — Tespit, sınırlama, bildirim, kayıt.
8. **Veri Aktarım Politikası** — Yurt içi ve yurt dışı aktarım kuralları, m.9.
9. **VERBİS Yönetimi Prosedürü** — Sicil güncel tutma sorumluluğu.
10. **Çerez Politikası** — Web sitesi çerezleri, kategorileri, opt-in/out.
11. **Pazarlama İletişimi Politikası** — KVKK + Elektronik Ticaret Kanunu (İYS) uyumlu.
12. **Çalışan Mahremiyet Politikası** — Çalışan verisinin işlenme şekli, izleme uygulamaları.
13. **CCTV / Kamera Politikası** — Görüntü kaydı amaç, süre, paylaşım.
14. **Kişisel Veri Etki Değerlendirmesi (DPIA) Standardı** — Ne zaman, nasıl yapılır.

### 3.3. Bilgi Güvenliği — Operasyonel

15. **Erişim Yönetimi Standardı** — RBAC, JML, PAM (bkz. [05-teknik-tedbirler/erisim-kontrolu.md](../05-teknik-tedbirler/erisim-kontrolu.md)).
16. **Kimlik Doğrulama Standardı** — MFA, parola, SSO.
17. **Şifreleme Standardı** — Algoritma, anahtar yönetimi.
18. **Ağ Güvenliği Standardı** — Segmentasyon, perimeter, ZTNA.
19. **Yedekleme ve İş Sürekliliği Standardı** — RPO/RTO, restore test.
20. **Log ve İzleme Standardı** — Logging, SIEM, saklama.
21. **DLP / Veri Sızıntısı Önleme Standardı**.
22. **Uygulama Güvenliği / S-SDLC Standardı**.
23. **Mobil ve Uzaktan Çalışma Politikası** — BYOD, MDM.
24. **Temiz Masa — Temiz Ekran Politikası** — Fiziksel mahremiyet.
25. **Sosyal Mühendislik ve Phishing Politikası** — Eğitim, simülasyon, raporlama.
26. **Olay Yönetimi (IR) Prosedürü** — RB-01..RB-12 runbook seti.
27. **Değişiklik Yönetimi Politikası** — CAB, acil değişiklik.
28. **Kabul Edilebilir Kullanım Politikası (AUP)** — Çalışan davranışı, internet, sosyal medya.

### 3.4. Tedarikçi ve Üçüncü Taraf

29. **Tedarikçi Yönetimi Politikası** — Sınıflandırma, due diligence, monitoring.
30. **Veri İşleyen Sözleşmesi Standart Maddeleri** — Asgari unsurlar, denetim hakkı.
31. **Bulut Hizmeti Kullanımı Politikası** — Onaylı sağlayıcı listesi, veri yerleşimi.

### 3.5. İK ve Eğitim

32. **İşe Alım ve Ayrılık Politikası (KVKK Bağlantısı)** — Özlük dosyası, gizlilik taahhütnamesi, ayrılışta erişim kapama.
33. **Personel Eğitim ve Farkındalık Programı** — Yıllık müfredat.
34. **Disiplin Politikası — Bilgi Güvenliği İhlalleri** — İhlal sınıfları ve yaptırım.

### 3.6. Yönetişim

35. **KVKK Komitesi Çalışma Esasları** — Üyeler, toplantı, karar.
36. **Risk Yönetimi Politikası** — Risk iştahı, skorlama.
37. **İç Denetim Tüzüğü ve Yıllık Plan** — Bağımsızlık, kapsam.
38. **Politika ve Doküman Yönetimi Politikası** — Bu doküman.

## 4. Politika Yaşam Döngüsü

```
Tetik (yeni risk / mevzuat / gap)
   → 1. Taslak (Sahip ekip)
   → 2. Paydaş Review (Hukuk, BT, İK, KVKK Sorumlusu, ilgili iş birimi)
   → 3. Üst Yönetim / Komite Onayı
   → 4. Yayınlama (intranet, e-posta duyuru, eğitim)
   → 5. Uygulama (operasyonel adımlar)
   → 6. İzleme & Ölçüm (KPI, denetim)
   → 7. Periyodik Review (≤2 yıl)
   → 8. Revizyon / Geri Çekme
```

## 5. Standart Politika Şablonu (Bölümler)

Her politika dokümanında aşağıdaki bölümler bulunur:

1. **Başlık + Meta Bilgi** (versiyon, sahip, onaylayan, yürürlük, gözden geçirme tarihi).
2. **Amaç** — Politikanın çözdüğü sorun.
3. **Kapsam** — Hangi kişiler, sistemler, lokasyonlar dahil.
4. **Tanımlar** — Tartışmalı / teknik terimler.
5. **Roller ve Sorumluluklar** — RACI.
6. **Politika Hükümleri** — Yapılması ve yapılmaması gerekenler.
7. **İstisnalar** — İstisna talep süreci.
8. **Ölçüm / KPI** — Etkinlik göstergeleri.
9. **Uyumsuzluk ve Yaptırım** — Disiplin sürecine atıf.
10. **İlgili Dokümanlar** — Üst/alt politikalar, mevzuat.
11. **Revizyon Geçmişi** — Tarih, değişiklik özeti, onaylayan.

## 6. Onay Zinciri

| Doküman Türü | Hazırlayan | Review (zorunlu) | Onaylayan | Yayın |
|--------------|------------|-------------------|------------|-------|
| Üst Düzey Politika | KVKK Sorumlusu / CISO | Hukuk + Tüm Komite + Üst Yön. | Yönetim Kurulu | İntranet + Genel duyuru |
| Politika (Seviye 2) | Sahip ekip | Hukuk + KVKK Sorumlusu + CISO + İlgili Direktör | KVKK Komitesi + Üst Yönetim | İntranet + e-posta |
| Standart | Teknik ekip + CISO ofisi | KVKK Sorumlusu + İlgili Direktör | CISO + İlgili Direktör | İntranet |
| Prosedür | Süreç Sahibi | Süreç paydaşları + KVKK Sorumlusu | İlgili Müdür | İntranet |
| Şablon / Form | Süreç Sahibi | Hukuk + KVKK Sorumlusu | KVKK Sorumlusu | İntranet |

Onay e-imza veya ıslak imza ile belgelenir; kanıt PDF + meta-data arşivde.

## 7. Yayınlama ve İletişim

- **Yayın Kanalı:** İntranet politika kütüphanesi (Confluence / SharePoint vb.) — tek yetkili kaynak.
- **Sürüm Bilgisi:** Her dokümanın başında ve dosya adında (örn. `KVKK-Politikasi-v2.0-2026.pdf`).
- **Yeni Yayın:** Şirket geneli e-posta + departman bazlı bildirim. Kritik politika için 30 dakikalık brifing.
- **Çevirisi:** Türkçe asli + İngilizce mevcut (uluslararası iştirakler için).
- **Erişilebilirlik:** Engelli erişim standartları (WCAG 2.1 AA) için yayın formatı düzenlenir.

## 8. Versiyonlama Kuralı

- **MAJOR.MINOR** (örn. 2.1).
- **MAJOR** — Politikanın amacı, kapsamı veya önemli hükmü değişti.
- **MINOR** — Açıklama, örnek, küçük revizyon.
- Yıllık review minor versiyon üretebilir.
- Her sürüm ayrı kayıt; geri dönülebilir.

## 9. Eski Sürüm Yönetimi

- Eski sürüm "ARŞİV" klasörüne taşınır, yeni sürüm yayınlanır.
- Çalışanların eski versiyona dayanarak hareket etmesi önlenir (eski sürüm açıkça "geçersiz" damgalı).
- Adli soruşturma / denetim olası hallerinde eski sürüm 5 yıl saklanır.
- Versiyon değişimini takip eden 30 gün içinde tüm çalışanların yeni versiyonu okudum onayı (kritik politika için).

## 10. Periyodik Review

### 10.1. Yıllık Tetikleyiciler

- Yasal değişiklik (KVKK, ikincil mevzuat, sektörel düzenleme).
- Kurumsal değişiklik (organizasyon, M&A, yeni iş kolu).
- Teknolojik değişiklik (yeni bulut, yeni IdP, yeni AI sistem).
- İhlal veya ramak kala olayı.
- Bağımsız denetim bulgusu.
- KVKK Kurulu kararı / sektörel rehber yenilenmesi.

### 10.2. Review Akışı

1. KVKK Sorumlusu yıllık takvim açıklar (Q1).
2. Her doküman sahibi kendi dokümanını review için açar.
3. Değişiklik gerekiyorsa taslak güncellenir, paydaş review.
4. Onay zinciri tetiklenir.
5. Yayın + iletişim.
6. Komite'ye review tamamlanma raporu.

## 11. İstisna Yönetimi

- İstisna **yazılı, gerekçeli, süreli, telafi edici kontrollü, onaylı** olabilir.
- İstisna formu: kim, neden, hangi madde, telafi edici kontrol, süre (≤180 gün), risk sahibi, KVKK Sorumlusu görüşü.
- İstisna defteri tutulur; yıllık review.
- İstisna birikimi politika revizyon ihtiyacına işaret eder.

## 12. Uyumsuzluk ve Yaptırım

- Uyumsuzluk Disiplin Politikası'na göre değerlendirilir.
- Sınıflandırma:
  - **A — Kasıtlı / Ağır:** Veri ifşası, kasıtlı erişim ihlali → fesih ve hukuki süreç dahil.
  - **B — İhmal / Tekrarlı:** Yazılı uyarı + zorunlu eğitim.
  - **C — Hata / İlk:** Eğitim hatırlatması.
- Tedarikçi uyumsuzluğunda sözleşme maddesi tetiklenir.
- KVKK Sorumlusu, ihlal halinde Komite'yi bilgilendirir.

## 13. Politika Şablonu (Markdown — kısa örnek başlangıç)

```markdown
---
Doküman: <başlık>
Sahip: <ekip / kişi>
Onaylayan: <komite>
Versiyon: 1.0
Yürürlük: YYYY-MM-DD
Gözden Geçirme: <tarih>
İlgili Mevzuat: ...
İlgili Standart: ...
---

# 1. Amaç
# 2. Kapsam
# 3. Tanımlar
# 4. Roller ve Sorumluluklar
# 5. Politika Hükümleri
# 6. İstisnalar
# 7. Ölçüm
# 8. Uyumsuzluk ve Yaptırım
# 9. İlgili Dokümanlar
# 10. Revizyon Geçmişi
```

## 14. Doküman Yönetim Sistemi (DMS) Beklentileri

- Versiyon kontrolü, audit trail, erişim kontrolü.
- Onay akışı (workflow) yerleşik.
- Otomatik review hatırlatıcıları (90, 30, 7 gün öncesinden).
- "Okudum" tutanağı (kritik politikalar için).
- Arama (full-text), etiket / kategori.
- Eski sürüm arşivi (read-only).
- Tipik adaylar: Confluence + Comala Workflow, SharePoint + Power Automate, GitOps yaklaşımı (Markdown + git PR review + CI yayın).

## 15. KPI

- Politika güncellik (≤24 ay): hedef %100.
- Yıllık review tamamlanma: %100.
- "Okudum" oranı (yeni başlayan, oryantasyon haftası içinde): %100.
- Kritik politika revizyonu sonrası 30 gün içinde okudum oranı: ≥%95.
- Açık istisna sayısı: trend takibi (yıl başına azalış hedefi).
- Uyumsuzluk olay sayısı: aylık trend.

## 16. Kontrol Listesi

- [ ] KVKK Politikası ve Bilgi Güvenliği Politikası mevcut, ≤2 yıl güncel mi?
- [ ] §3'te listelenen 38 doküman mevcut mu (kapsamı uygun değilse gerekçeli)?
- [ ] Tüm dokümanlar standart şablona uyuyor mu (versiyon, onaylayan, yürürlük)?
- [ ] Onay zinciri belgeli mi?
- [ ] DMS audit trail aktif mi?
- [ ] Yıllık review takvimi yayınlandı mı?
- [ ] Eski sürümler arşivde 5 yıl korunuyor mu?
- [ ] İstisna defteri güncel, süreli, telafi edici kontrollü mü?
- [ ] "Okudum" kayıtları yeni başlayanlar için 100% mi?
- [ ] Kritik politika revizyonu çalışanlara duyuruluyor mu?
- [ ] Türkçe asli + İngilizce sürüm tutarlı mı?
- [ ] Politika hiyerarşisi çelişki kontrolü yıllık yapılıyor mu?
- [ ] KPI'lar yıllık raporlanıyor, KVKK Komitesi'ne sunuluyor mu?
- [ ] Disiplin Politikası bilgi güvenliği ihlali sınıflandırması içeriyor mu?
- [ ] Tedarikçi sözleşmelerinde "tedarikçinin politikalarımıza uyumu" maddesi var mı?

## 17. Yaygın Hatalar

- Politika dokümanları yıllarca güncellenmemiş, mevzuatla çelişen ifadeler.
- "Yazıldı ama uygulanmıyor" — KPI ölçümü yok.
- Çalışan hangi politikanın geçerli olduğunu bilmiyor (intranet karmaşası).
- Standart şablon yok — her politika farklı dilde ve yapıda.
- "Okudum" sadece formal, anlama testi yok.
- İstisna kullanımı politika dışı normalleşmiş.
- Eski sürüm yanlışlıkla geçerli sanılarak uygulanmış.
- Tedarikçi sözleşmesinde politikalara atıf yok, asgari unsurlar eksik.
