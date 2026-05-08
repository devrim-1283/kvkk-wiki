---
Doküman / Document: Aktarım Etki Değerlendirmesi (TIA) ve Aktarım Onay Formu / Transfer Impact Assessment (TIA) and Transfer Approval Form
Bölüm / Section: 07-aktarim
Sahip / Owner: KVKK Sorumlusu / KVKK Officer
Onaylayan / Approved by: Hukuk Müdürü + Bilgi Güvenliği Yöneticisi (KVKK Komitesi onayı) / Legal Director + Information Security Manager (KVKK Committee approval)
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş / Annual + triggered (new transfer, regulatory change, recipient country law change)
İlgili Mevzuat / Legal Reference: KVKK Art. 5, 6, 8, 9; Personal Data Protection Board Decision No. 2024/959 dated 04.06.2024
---

## English

# Transfer Impact Assessment (TIA) and Approval Form

## 1. Purpose of the Form

This form is designed to be completed **before** every **personal data transfer** (domestic and cross-border) the Company will perform. The form ensures:

- Clear identification of the legal basis for the transfer (Art. 5/Art. 6 + Art. 8/Art. 9),
- Recording which path (adequacy / appropriate safeguard / occasional) is used in cross-border transfers,
- Assessment of recipient country law and practice (for cross-border),
- Definition and implementation of supplementary measures,
- Maintaining the KVKK Committee approval chain.

## 2. Form Types

| Form | Use |
|------|-----|
| Form A | Domestic Transfer Approval Form |
| Form B | Cross-Border Transfer — Adequacy Path |
| Form C | Cross-Border Transfer — Appropriate Safeguard Path (Standard Contract / BCR / Undertaking / Agreement) |
| Form D | Cross-Border Transfer — Occasional Case Path |

A **unified form** is presented below; the relevant sections are filled in per transfer type.

---

## 3. Transfer Approval Form — Unified

```
═══════════════════════════════════════════════════════════════
PERSONAL DATA TRANSFER ASSESSMENT AND APPROVAL FORM
═══════════════════════════════════════════════════════════════

Form No                : ____________________________________
Form Date              : ____/____/______
Form Owner (Unit)      : ____________________________________
Transfer Type          : [ ] Domestic   [ ] Cross-border

──────────────────────────────────────────────────────────────
1. GENERAL TRANSFER DEFINITION
──────────────────────────────────────────────────────────────
Purpose of Transfer    : ______________________________________
                         ______________________________________
Business Process Owner : ______________________________________
Data Controller        : [COMPANY NAME A.Ş.]
Recipient (Title)      : ______________________________________
Recipient Address      : ______________________________________
Recipient Country      : ______________________________________
Recipient Status       : [ ] Controller (C)
                         [ ] Processor (P)
                         [ ] Joint Controller
Transfer Frequency     : [ ] One-off
                         [ ] Periodic (day/week/month/year)
                         [ ] Continuous (real-time / API)
Transfer Duration      : __________________________
Transfer Method        : [ ] API
                         [ ] File transfer (SFTP/FTPS)
                         [ ] Email / KEP
                         [ ] Cloud hosting (provider: ____)
                         [ ] Remote access (with auth.)
                         [ ] Physical media
                         [ ] Other: ____________________

──────────────────────────────────────────────────────────────
2. DATA SCOPE
──────────────────────────────────────────────────────────────
Data Categories        : ______________________________________
                         ______________________________________
                         (Inventory Item No: ____________)
Data Subject Groups    : [ ] Employee [ ] Candidate [ ] Customer
                         [ ] Supplier officer
                         [ ] Visitor
                         [ ] Other: ____________________
Data Sensitivity       : [ ] General
                         [ ] Special category (Art. 6)
                         [ ] Children's data
Approx. Record Count   : ____________________________________
Data Volume            : ____________________________________

──────────────────────────────────────────────────────────────
3. LEGAL BASIS — Art. 5/Art. 6 PROCESSING CONDITION
──────────────────────────────────────────────────────────────
Processing Condition   : KVKK Art. ____/____  ____________________
                         (Condition: explicit consent/contract
                          performance/legal obligation/legitimate
                          interest/...)
Sustainability of
condition              : Valid throughout transfer? Yes/No
Disclosure             : [ ] Done (version: __________)
                         [ ] To be updated
                         [ ] N/A (rationale: __________)

──────────────────────────────────────────────────────────────
4. DOMESTIC TRANSFER (Form A — only if domestic)
──────────────────────────────────────────────────────────────
Art. 8 Transfer Cond.  : KVKK Art. ____/____
Contract Type          : [ ] Data Processor Agreement (DPA)
                         [ ] Transfer Agreement (C-C)
                         [ ] Joint Controller Arrangement
                         [ ] Mandated by law — no contract
Contract No / Date     : ____________________________________
DPA Min. Elements      : [ ] Complete (checklist: yurtici-aktarim.md §7)
Sub-processor present  : [ ] No [ ] Yes (list annex: __________)

──────────────────────────────────────────────────────────────
5. CROSS-BORDER TRANSFER PATH (only if cross-border)
──────────────────────────────────────────────────────────────
[ ] (Tier 1) Adequacy Decision (Art. 9/1)
    List date/version   : ____________________________________
    List link/reference : ____________________________________
    Scope of decision (country/sector/international
    organization): ___________________________________________

[ ] (Tier 2) Appropriate Safeguard (Art. 9/4)
    [ ] (a) Agreement + Board authorization
        Authorization date/no: __________________________________
    [ ] (b) Binding Corporate Rules
        Approval date/no : ___________________________________
    [ ] (c) Standard Contract
        Type             : Type __ (C-C / C-P / P-P / P-C)
        Signature date   : ____/____/______
        Notification date
        (within 5 b.d.)  : ____/____/______
    [ ] (ç) Written undertaking + Board authorization
        Authorization date/no: __________________________________

[ ] (Tier 3) Occasional Case (Art. 9/6)
    Case applied         : (a)/(b)/(c)/(ç)/(d)/(e)/(f)
    Rationale for
    occasional nature    : _________________________________
                           _________________________________
    Information given (for a): [ ] Yes [ ] N/A

──────────────────────────────────────────────────────────────
6. RECIPIENT COUNTRY ASSESSMENT (for cross-border)
──────────────────────────────────────────────────────────────
Recipient Country      : ____________________________________

Data Protection Law    : [ ] Comprehensive
                         [ ] Limited
                         [ ] None / Minimal
Independent Authority  : [ ] Yes [ ] No
Data Subject Rights    : [ ] Effective [ ] Limited [ ] None
Judicial Protection    : [ ] Yes [ ] Limited [ ] None
International Treaty   : [ ] EU GDPR-compatible
                         [ ] Council of Europe Convention 108
                         [ ] APEC CBPR
                         [ ] Other: ____________________

PUBLIC AUTHORITY ACCESS RISK
Intelligence Access    : [ ] Low [ ] Medium [ ] High
Law Enforcement Access : [ ] Low [ ] Medium [ ] High
Disproportionate Risk  : [ ] Low [ ] Medium [ ] High
Description            : _________________________________

──────────────────────────────────────────────────────────────
7. SUPPLEMENTARY MEASURES
──────────────────────────────────────────────────────────────
TECHNICAL
[ ] End-to-end encryption
[ ] At-rest encryption (AES-256)
[ ] Transit encryption (TLS 1.2+)
[ ] Key management (KMS/HSM, BYOK)
[ ] Pseudonymization
[ ] Data minimization (only required fields)
[ ] IP filtering / VPN
[ ] DLP
[ ] Other: ____________________________________________

CONTRACTUAL
[ ] Standard contract (Tier 2-c)
[ ] Annex protocol (no deviation from contract)
[ ] Notification of access requests (where local law permits)
[ ] Audit right
[ ] 24-hour breach notification clause
[ ] Sub-processor approval requirement
[ ] Other: ____________________________________________

ORGANIZATIONAL
[ ] Need-to-know access
[ ] Training (at recipient)
[ ] Logging + audit
[ ] Destruction commitment on contract termination
[ ] Other: ____________________________________________

──────────────────────────────────────────────────────────────
8. SUB-PROCESSOR CHAIN
──────────────────────────────────────────────────────────────
Recipient using
sub-processors?        : [ ] No [ ] Yes
Sub-processor list     : Annex (if any)
Sub-processor approval
structure              : [ ] None [ ] General approval
                         [ ] Specific approval (prior notice)
Sub-processors
abroad?                : [ ] No [ ] Yes (country list: __)

──────────────────────────────────────────────────────────────
9. RESIDUAL RISK AND DECISION
──────────────────────────────────────────────────────────────
Risk Assessment        :
  Affected count       : __________________________
  Data sensitivity     : Low / Medium / High
  Transfer frequency   : Low / Medium / High
  Recipient country risk: Low / Medium / High
  Effectiveness of
  supplementary measures: Low / Medium / High

Residual Risk Level    : [ ] Low [ ] Medium [ ] High

DECISION               : [ ] Transfer approved
                         [ ] Transfer not approved
                         [ ] Additional measures required —
                             reassess.

──────────────────────────────────────────────────────────────
10. VERBİS UPDATE
──────────────────────────────────────────────────────────────
[ ] VERBİS updated
    Update date        : ____/____/______
    Recipient group    : ____________________________________

──────────────────────────────────────────────────────────────
11. APPROVALS
──────────────────────────────────────────────────────────────
Preparer (Business Unit Owner)
  Name                 : ____________________________________
  Title / Unit         : ____________________________________
  Date                 : ____/____/______
  Signature            : ____________________________________

Information Security Approval
  Name                 : ____________________________________
  Date                 : ____/____/______
  Signature            : ____________________________________

Legal Approval
  Name                 : Att. ______________________________
  Date                 : ____/____/______
  Signature            : ____________________________________

KVKK Officer Approval
  Name                 : ____________________________________
  Date                 : ____/____/______
  Signature            : ____________________________________

KVKK Committee Approval (mandatory for high-risk transfer)
  Date                 : ____/____/______
  Decision No          : ____________________________________

──────────────────────────────────────────────────────────────
12. ANNEXES
──────────────────────────────────────────────────────────────
[ ] Contract PDF
[ ] DPA PDF (domestic C-P)
[ ] Standard contract + annexes (cross-border)
[ ] Sub-processor list
[ ] Disclosure notice (versioned)
[ ] Explicit consent proof output (if any)
[ ] Authority notification confirmation (if any)
[ ] Previous TIA (if renewal)
═══════════════════════════════════════════════════════════════
```

---

## 4. Sample 1 — EU SaaS Provider (Marketing Automation)

```
═══════════════════════════════════════════════════════════════
PERSONAL DATA TRANSFER ASSESSMENT AND APPROVAL FORM
═══════════════════════════════════════════════════════════════

Form No                : TIA-2026-0042
Form Date              : 12/04/2026
Form Owner (Unit)      : Digital Marketing Department
Transfer Type          : [X] Cross-border

──────────────────────────────────────────────────────────────
1. GENERAL TRANSFER DEFINITION
──────────────────────────────────────────────────────────────
Purpose of Transfer    : Marketing automation (email, push,
                         SMS) and segmentation analytics for
                         e-commerce customers.
Business Process Owner : Marketing Director
Data Controller        : [COMPANY NAME A.Ş.]
Recipient (Title)      : Acme Marketing Cloud Ltd.
Recipient Address      : Dublin, Ireland
Recipient Country      : Ireland (EU Member)
Recipient Status       : [X] Processor (P)
Transfer Frequency     : [X] Continuous (real-time API)
Transfer Duration      : Contract term (3 years + renewal)
Transfer Method        : [X] API + cloud hosting
                         Provider: Acme cloud, EU region

──────────────────────────────────────────────────────────────
2. DATA SCOPE
──────────────────────────────────────────────────────────────
Data Categories        : Name, email, phone, order history,
                         behavior data, segment
                         (Inventory Item No: ECOM-08, MKT-03)
Data Subject Groups    : [X] Customer
Data Sensitivity       : [X] General
Approx. Record Count   : 1.2 million active customers
Data Volume            : ~50 GB / month growth

──────────────────────────────────────────────────────────────
3. LEGAL BASIS — Art. 5/Art. 6 PROCESSING CONDITION
──────────────────────────────────────────────────────────────
Processing Condition   : KVKK Art. 5/1 — Explicit Consent
                         (For marketing purpose)
Sustainability of
condition              : Consent revocable; if withdrawn,
                         deletion at provider also ensured
Disclosure             : [X] Done (Version: 2026-Q1 v3.2)

──────────────────────────────────────────────────────────────
5. CROSS-BORDER TRANSFER PATH
──────────────────────────────────────────────────────────────
[X] (Tier 2) Appropriate Safeguard (Art. 9/4)
    [X] (c) Standard Contract
        Type             : Type 2 (C → P)
        Signature date   : 10/04/2026
        Notification date: 14/04/2026 (3 business days)

──────────────────────────────────────────────────────────────
6. RECIPIENT COUNTRY ASSESSMENT
──────────────────────────────────────────────────────────────
Recipient Country      : Ireland

Data Protection Law    : [X] Comprehensive (GDPR + Data
                         Protection Act 2018)
Independent Authority  : [X] Yes (DPC — Data Protection
                         Commission)
Data Subject Rights    : [X] Effective
Judicial Protection    : [X] Yes (including CJEU)
International Treaty   : [X] EU GDPR
                         [X] Convention 108

PUBLIC AUTHORITY ACCESS RISK
Intelligence Access    : [X] Low
Law Enforcement Access : [X] Low (strong judicial oversight)
Disproportionate Risk  : [X] Low
Description            : Provider has US parent. Data in EU
                         region; US parent's access restricted
                         in contract.

──────────────────────────────────────────────────────────────
7. SUPPLEMENTARY MEASURES
──────────────────────────────────────────────────────────────
TECHNICAL
[X] At-rest encryption (AES-256)
[X] Transit encryption (TLS 1.3)
[X] BYOK — key at Company
[X] Data minimization (only required fields)
[X] Pseudonymization (user ID hashed)

CONTRACTUAL
[X] Standard contract (Type 2)
[X] Annex protocol — US parent access limit
[X] Notification of access requests
[X] Audit right (annual)
[X] 24-hour breach notification clause

ORGANIZATIONAL
[X] Need-to-know
[X] Destruction of all data within 30 days of contract end

──────────────────────────────────────────────────────────────
8. SUB-PROCESSOR CHAIN
──────────────────────────────────────────────────────────────
Sub-processor list     : 4 entries (3 EU + 1 US CDN)
Sub-processor approval : Specific approval (prior notice)
                         + 14-day objection right
US CDN Risk Note       : Static content only; no PII

──────────────────────────────────────────────────────────────
9. RESIDUAL RISK AND DECISION
──────────────────────────────────────────────────────────────
Risk Assessment:
  Affected count       : 1.2 million
  Data sensitivity     : Medium
  Transfer frequency   : High (continuous)
  Recipient country risk: Low
  Effectiveness        : High

Residual Risk Level    : [X] Low

DECISION               : [X] Transfer approved

──────────────────────────────────────────────────────────────
10. VERBİS UPDATE
──────────────────────────────────────────────────────────────
[X] VERBİS updated 15/04/2026
    Recipient group    : Foreign marketing service provider

──────────────────────────────────────────────────────────────
11. APPROVALS
──────────────────────────────────────────────────────────────
Preparer               : Elif YAVUZ — Marketing Director
Information Security   : Mehmet KAYA — Inf. Sec. Manager
Legal Approval         : Att. Ahmet ÖZ — Legal Director
KVKK Officer           : Selin YILDIZ — KVKK Officer
KVKK Committee         : 14/04/2026, Decision No: 2026/12
═══════════════════════════════════════════════════════════════
```

---

## 5. Sample 2 — US CRM Provider (High Risk + Supplementary Measures)

```
═══════════════════════════════════════════════════════════════
PERSONAL DATA TRANSFER ASSESSMENT AND APPROVAL FORM
═══════════════════════════════════════════════════════════════

Form No                : TIA-2026-0058
Form Date              : 22/04/2026
Form Owner (Unit)      : Sales Operations Department
Transfer Type          : [X] Cross-border

──────────────────────────────────────────────────────────────
1. GENERAL TRANSFER DEFINITION
──────────────────────────────────────────────────────────────
Purpose of Transfer    : B2B customer relationship management
                         (CRM) — sales pipeline, opportunity
                         management, customer officer contact
                         records
Business Process Owner : Sales Operations Director
Recipient (Title)      : Globex Cloud CRM Inc.
Recipient Address      : San Francisco, CA, USA
Recipient Country      : USA
Recipient Status       : [X] Processor (P)
Transfer Frequency     : [X] Continuous
Transfer Duration      : 5 years (renewable)
Transfer Method        : [X] API + cloud hosting
                         Provider region: us-east-1

──────────────────────────────────────────────────────────────
2. DATA SCOPE
──────────────────────────────────────────────────────────────
Data Categories        : Customer officer name, title, business
                         email, business phone, sales call notes
                         (Inventory Item No: SLS-01)
Data Subject Groups    : [X] Customer (B2B officer — as
                         natural person)
Data Sensitivity       : [X] General
Approx. Record Count   : 38,000 individuals (B2B officers)
Data Volume            : ~5 GB / year

──────────────────────────────────────────────────────────────
3. LEGAL BASIS — Art. 5/Art. 6 PROCESSING CONDITION
──────────────────────────────────────────────────────────────
Processing Condition   : KVKK Art. 5/2-(f) — Legitimate Interest
                         (carrying out B2B sales process)
                         + KVKK Art. 5/2-(c) — Contract performance
                         (for existing contracted customers)
Disclosure             : [X] Customer officer disclosure
                         updated (Version: 2026-Q2)

──────────────────────────────────────────────────────────────
5. CROSS-BORDER TRANSFER PATH
──────────────────────────────────────────────────────────────
[X] (Tier 2) Appropriate Safeguard (Art. 9/4)
    [X] (c) Standard Contract
        Type             : Type 2 (C → P)
        Signature date   : 20/04/2026
        Notification date: 23/04/2026 (3 business days)

──────────────────────────────────────────────────────────────
6. RECIPIENT COUNTRY ASSESSMENT
──────────────────────────────────────────────────────────────
Recipient Country      : USA

Data Protection Law    : [X] Limited
                         (sectoral at federal level; CCPA/CPRA
                         at state level, Virginia VCDPA;
                         no general federal law)
Independent Authority  : [X] Limited (FTC sectoral)
Data Subject Rights    : [X] Limited
Judicial Protection    : [X] Limited (for foreigners)
International Treaty   : [ ] EU GDPR — N/A
                         [ ] Convention 108 — N/A
                         (EU-US Data Privacy Framework valid for
                          EU, not in scope of KVKK)

PUBLIC AUTHORITY ACCESS RISK
Intelligence Access    : [X] High (FISA 702, EO 12333)
Law Enforcement Access : [X] Medium (CLOUD Act effect)
Disproportionate Risk  : [X] High
Description            : US intelligence services have broad
                         power to access foreign data. Contractual
                         provisions may be insufficient; supplementary
                         technical measures critical.

──────────────────────────────────────────────────────────────
7. SUPPLEMENTARY MEASURES
──────────────────────────────────────────────────────────────
TECHNICAL
[X] At-rest encryption (AES-256)
[X] Transit encryption (TLS 1.3)
[X] BYOK — key in Company KMS in Turkey
    (provider has no access to its own key)
[X] Field-level encryption — sensitive fields (notes)
[X] Data minimization — only B2B business data (no
    private life, social media, photos)

CONTRACTUAL
[X] Standard contract (Type 2)
[X] Annex protocol:
    - Immediate notification to Company on US public
      authority access request (where local law permits)
    - Contractual obligation to object to access requests
    - Audit right (annual 3rd-party audit)
    - 24-hour breach notification
[X] Notification of access requests

ORGANIZATIONAL
[X] Need-to-know
[X] Access logs + Company SIEM integration
[X] Destruction within 30 days of contract end

──────────────────────────────────────────────────────────────
8. SUB-PROCESSOR CHAIN
──────────────────────────────────────────────────────────────
Sub-processor list     : 6 entries (5 US + 1 Ireland)
Sub-processor approval : General approval; 30-day notice +
                         objection right on each change
High-Risk Note         : There was an India support team;
                         contract requires prohibition of
                         India access for support.

──────────────────────────────────────────────────────────────
9. RESIDUAL RISK AND DECISION
──────────────────────────────────────────────────────────────
Risk Assessment:
  Affected count       : 38,000
  Data sensitivity     : Medium-High (B2B notes may
                         contain sensitive business info)
  Transfer frequency   : High (continuous)
  Recipient country risk: High
  Effectiveness        : High (BYOK + field encryption +
                         data minimization)

Residual Risk Level    : [X] Medium

DECISION               : [X] Transfer approved
                         Condition: annual TIA renewal +
                         3rd-party audit report submitted to
                         KVKK Committee.

──────────────────────────────────────────────────────────────
10. VERBİS UPDATE
──────────────────────────────────────────────────────────────
[X] VERBİS updated 24/04/2026
    Recipient group    : Foreign CRM service provider

──────────────────────────────────────────────────────────────
11. APPROVALS
──────────────────────────────────────────────────────────────
Preparer               : Murat ARSLAN — Sales Op. Director
Information Security   : Mehmet KAYA — Inf. Sec. Manager
Legal Approval         : Att. Ahmet ÖZ — Legal Director
KVKK Officer           : Selin YILDIZ — KVKK Officer
KVKK Committee         : 23/04/2026, Decision No: 2026/15
                         (high-risk transfer — committee approval required)

──────────────────────────────────────────────────────────────
12. ANNEXES
──────────────────────────────────────────────────────────────
[X] Standard Contract Type 2 + annex protocol PDF
[X] Sub-processor list v1.4
[X] Disclosure notice 2026-Q2
[X] Globex SOC 2 Type II report
[X] Globex DPA + Subprocessor list
[X] BYOK architecture diagram
═══════════════════════════════════════════════════════════════
```

---

## 6. Form Management Discipline

| Topic | Rule |
|-------|------|
| Form No | TIA-[YEAR]-[SEQUENCE] format |
| Trigger to prepare | New transfer, contract renewal, regulatory change, recipient change |
| Approval chain | Preparer → Information Security → Legal → KVKK Officer → (high risk) KVKK Committee |
| Retention | 10 years |
| Renewal | Annual or triggered |
| Storage | Electronically signed PDF under KVKK Officer control |
| Searchable index | Form no, date, recipient, country, status |
| Versioning | Renewal supersedes previous version, new version takes effect |

## 7. High-Risk Triggers

KVKK Committee approval is mandatory in the following cases (KVKK Officer single signature insufficient):

- Special category personal data transfer,
- Children's data transfer,
- Transfer affecting 100,000+ data subjects,
- Transfer to a high-risk country (disproportionate access by public authorities),
- Transfer to a new and untested provider,
- Large-scale marketing transfer based on legitimate interest instead of explicit consent,
- BCR approval process.

---

## Türkçe

# Aktarım Etki Değerlendirmesi (TIA) ve Onay Formu

## 1. Formun Amacı

Bu form; Şirket'in gerçekleştireceği her **kişisel veri aktarımı** (yurt içi ve yurt dışı) için **aktarım öncesinde** doldurulmak üzere tasarlanmıştır. Form aşağıdakileri sağlar:

- Aktarımın hukuki dayanağının (m.5/m.6 + m.8/m.9) net biçimde tespit edilmesi,
- Yurt dışı aktarımlarda hangi yolun (yeterlilik / uygun güvence / arızi) kullanıldığının kayıt altına alınması,
- Alıcı ülke hukuku ve uygulamasının değerlendirilmesi (yurt dışı için),
- Ek tedbirlerin tanımlanması ve uygulanmaya konulması,
- KVKK Komitesi onay zincirinin tutulması.

## 2. Form Türleri

| Form | Kullanım |
|------|----------|
| Form A | Yurt İçi Aktarım Onay Formu |
| Form B | Yurt Dışı Aktarım — Yeterlilik Kararı Yolu |
| Form C | Yurt Dışı Aktarım — Uygun Güvence Yolu (Standart Sözleşme / BCR / Taahhütname / Anlaşma) |
| Form D | Yurt Dışı Aktarım — Arızi Hâl Yolu |

Aşağıda **birleşik form** sunulmuştur; ilgili bölümler aktarım türüne göre doldurulur.

---

## 3. Aktarım Onay Formu — Birleşik

```
═══════════════════════════════════════════════════════════════
KİŞİSEL VERİ AKTARIM DEĞERLENDİRME VE ONAY FORMU
═══════════════════════════════════════════════════════════════

Form No                : ____________________________________
Form Tarihi            : ____/____/______
Form Sahibi (Birim)    : ____________________________________
Aktarım Türü           : [ ] Yurt içi  [ ] Yurt dışı

──────────────────────────────────────────────────────────────
1. AKTARIMIN GENEL TANIMI
──────────────────────────────────────────────────────────────
Aktarımın Amacı        : ______________________________________
                         ______________________________________
İş Süreci Sahibi       : ______________________________________
Veri Sorumlusu         : [ŞİRKET ADI A.Ş.]
Alıcı (Unvan)          : ______________________________________
Alıcı Adres            : ______________________________________
Alıcı Ülke             : ______________________________________
Alıcı Statüsü          : [ ] Veri Sorumlusu (VS)
                         [ ] Veri İşleyen (Vİ)
                         [ ] Joint Controller
Aktarım Sıklığı        : [ ] Tek seferlik
                         [ ] Periyodik (gün/hafta/ay/yıl)
                         [ ] Sürekli (real-time / API)
Aktarımın Süresi       : __________________________
Aktarımın Yöntemi      : [ ] API
                         [ ] Dosya transferi (SFTP/FTPS)
                         [ ] E-posta / KEP
                         [ ] Bulut barındırma (sağlayıcı: ____)
                         [ ] Uzaktan erişim (yetki ile)
                         [ ] Fiziksel medya
                         [ ] Diğer: ____________________

──────────────────────────────────────────────────────────────
2. VERİ KAPSAMI
──────────────────────────────────────────────────────────────
Veri Kategorileri      : ______________________________________
                         ______________________________________
                         (Envanter Madde No: ____________)
İlgili Kişi Grupları   : [ ] Çalışan [ ] Aday [ ] Müşteri
                         [ ] Tedarikçi yetkilisi
                         [ ] Ziyaretçi
                         [ ] Diğer: ____________________
Veri Hassasiyeti       : [ ] Genel
                         [ ] Özel nitelikli (m.6)
                         [ ] Çocuk verisi
Yaklaşık Kayıt Sayısı  : ____________________________________
Veri Hacmi             : ____________________________________

──────────────────────────────────────────────────────────────
3. HUKUKI SEBEP — m.5/m.6 İŞLEME ŞARTI
──────────────────────────────────────────────────────────────
İşleme Şartı           : KVKK m.____/____  ____________________
                         (Şart adı: açık rıza/sözleşme ifası/
                          hukuki yükümlülük/meşru menfaat/...)
Şartın Sürdürülebilir-
liği                   : Aktarım süresince geçerli mi? Evet/Hayır
Aydınlatma             : [ ] Yapıldı (sürüm: __________)
                         [ ] Güncellenecek
                         [ ] Uygulanmaz (gerekçe: __________)

──────────────────────────────────────────────────────────────
4. YURT İÇİ AKTARIM (Form A — sadece yurt içi ise)
──────────────────────────────────────────────────────────────
m.8 Aktarım Şartı      : KVKK m.____/____
Sözleşme Türü          : [ ] Veri İşleyen Sözleşmesi (DPA)
                         [ ] Aktarım Sözleşmesi (VS-VS)
                         [ ] Joint Controller Anlaşması
                         [ ] Mevzuat gereği — sözleşme yok
Sözleşme No / Tarih    : ____________________________________
DPA Asgari Unsurları   : [ ] Tam (kontrol listesi: yurtici-aktarim.md §7)
Alt-İşleyen Var mı     : [ ] Yok [ ] Var (liste eki: __________)

──────────────────────────────────────────────────────────────
5. YURT DIŞI AKTARIM YOLU (sadece yurt dışı ise)
──────────────────────────────────────────────────────────────
[ ] (Aşama 1) Yeterlilik Kararı (m.9/1)
    Liste tarihi/sürüm  : ____________________________________
    Liste linki/atfı    : ____________________________________
    Kararın hangi kapsamda olduğu (ülke/sektör/uluslararası
    kuruluş): ___________________________________________

[ ] (Aşama 2) Uygun Güvence (m.9/4)
    [ ] (a) Anlaşma + Kurul izni
        İzin tarihi/sayı: ___________________________________
    [ ] (b) Bağlayıcı Şirket Kuralları
        Onay tarihi/sayı: ___________________________________
    [ ] (c) Standart Sözleşme
        Tür             : Tip __ (VS-VS / VS-Vİ / Vİ-Vİ / Vİ-VS)
        İmza tarihi     : ____/____/______
        Kurum'a bildirim
        tarihi (5 iş g.): ____/____/______
    [ ] (ç) Yazılı taahhütname + Kurul izni
        İzin tarihi/sayı: ___________________________________

[ ] (Aşama 3) Arızi Hâl (m.9/6)
    Uygulanan bent      : (a)/(b)/(c)/(ç)/(d)/(e)/(f)
    Arızi niteliğin
    gerekçesi           : _________________________________
                          _________________________________
    Bilgilendirme yapıldı (a için): [ ] Evet [ ] Uygulanmaz

──────────────────────────────────────────────────────────────
6. ALICI ÜLKE DEĞERLENDİRMESİ (yurt dışı için)
──────────────────────────────────────────────────────────────
Alıcı Ülke             : ____________________________________

Veri Koruma Mevzuatı   : [ ] Var ve kapsamlı
                         [ ] Var ama sınırlı
                         [ ] Yok / Asgari
Bağımsız Otorite       : [ ] Var [ ] Yok
İlgili Kişi Hakları    : [ ] Etkin [ ] Sınırlı [ ] Yok
Yargısal Koruma        : [ ] Var [ ] Sınırlı [ ] Yok
Uluslararası Anlaşma   : [ ] AB GDPR uyumu var
                         [ ] Council of Europe Convention 108
                         [ ] APEC CBPR
                         [ ] Diğer: ____________________

KAMU OTORİTESİ ERİŞİM RİSKİ
İstihbarat Erişimi     : [ ] Düşük [ ] Orta [ ] Yüksek
Kolluk Erişimi         : [ ] Düşük [ ] Orta [ ] Yüksek
Disproportionate Risk  : [ ] Düşük [ ] Orta [ ] Yüksek
Açıklama               : _________________________________

──────────────────────────────────────────────────────────────
7. EK TEDBİRLER
──────────────────────────────────────────────────────────────
TEKNIK
[ ] End-to-end şifreleme
[ ] At-rest şifreleme (AES-256)
[ ] Transit şifreleme (TLS 1.2+)
[ ] Anahtar yönetimi (KMS/HSM, BYOK)
[ ] Pseudonymization
[ ] Veri minimizasyonu (sadece gerekli alanlar)
[ ] IP filtreleme / VPN
[ ] DLP
[ ] Diğer: ____________________________________________

SÖZLEŞMESEL
[ ] Standart sözleşme (Aşama 2-c)
[ ] Ek protokol (sözleşmeden sapma yok)
[ ] Notification of access requests (yerel hukuk izin verdiği ölçüde)
[ ] Audit hakkı
[ ] 24 saat ihlal bildirim hükmü
[ ] Alt-işleyen onay zorunluluğu
[ ] Diğer: ____________________________________________

ORGANİZASYONEL
[ ] Need-to-know erişim
[ ] Eğitim (alıcı tarafta)
[ ] Logging + denetim
[ ] Sözleşme sona erince imha taahhüdü
[ ] Diğer: ____________________________________________

──────────────────────────────────────────────────────────────
8. ALT-İŞLEYEN ZİNCİRİ
──────────────────────────────────────────────────────────────
Alıcı, alt-işleyen
kullanıyor mu?         : [ ] Yok [ ] Var
Alt-işleyen Listesi    : Eki (varsa)
Alt-işleyen Onay Yapısı: [ ] Yok [ ] Genel onay
                         [ ] Spesifik onay (önceden bildirim)
Alt-işleyenler
yurt dışında mı?       : [ ] Hayır [ ] Evet (ülke listesi: __)

──────────────────────────────────────────────────────────────
9. KALAN RİSK VE KARAR
──────────────────────────────────────────────────────────────
Risk Değerlendirmesi   :
  Etkilenen kişi sayısı: __________________________
  Veri hassasiyeti     : Düşük / Orta / Yüksek
  Aktarım sıklığı      : Düşük / Orta / Yüksek
  Alıcı ülke riski     : Düşük / Orta / Yüksek
  Ek tedbir etkinliği  : Düşük / Orta / Yüksek

Kalan Risk Seviyesi    : [ ] Düşük [ ] Orta [ ] Yüksek

KARAR                  : [ ] Aktarım onaylanır
                         [ ] Aktarım onaylanmaz
                         [ ] Ek tedbir gerekiyor — yeniden değerle.

──────────────────────────────────────────────────────────────
10. VERBİS GÜNCELLEMESİ
──────────────────────────────────────────────────────────────
[ ] VERBİS güncellendi
    Güncelleme tarihi  : ____/____/______
    Alıcı grubu        : ____________________________________

──────────────────────────────────────────────────────────────
11. ONAYLAR
──────────────────────────────────────────────────────────────
Hazırlayan (İş Birimi Sorumlusu)
  Ad Soyad             : ____________________________________
  Unvan / Birim        : ____________________________________
  Tarih                : ____/____/______
  İmza                 : ____________________________________

Bilgi Güvenliği Onayı
  Ad Soyad             : ____________________________________
  Tarih                : ____/____/______
  İmza                 : ____________________________________

Hukuki Onay
  Ad Soyad             : Av. ______________________________
  Tarih                : ____/____/______
  İmza                 : ____________________________________

KVKK Sorumlusu Onayı
  Ad Soyad             : ____________________________________
  Tarih                : ____/____/______
  İmza                 : ____________________________________

KVKK Komitesi Onayı (Yüksek riskli aktarım için zorunlu)
  Tarih                : ____/____/______
  Karar No             : ____________________________________

──────────────────────────────────────────────────────────────
12. EK BELGELER
──────────────────────────────────────────────────────────────
[ ] Sözleşme PDF
[ ] DPA PDF (yurt içi VS-Vİ)
[ ] Standart sözleşme + ekler (yurt dışı)
[ ] Alt-işleyen listesi
[ ] Aydınlatma metni (sürümlü)
[ ] Açık rıza ispat dökümü (varsa)
[ ] Kurum bildirim onayı (varsa)
[ ] Önceki TIA (yenileme ise)
═══════════════════════════════════════════════════════════════
```

---

## 4. Örnek 1 — AB SaaS Sağlayıcısı (Pazarlama Otomasyonu)

```
═══════════════════════════════════════════════════════════════
KİŞİSEL VERİ AKTARIM DEĞERLENDİRME VE ONAY FORMU
═══════════════════════════════════════════════════════════════

Form No                : TIA-2026-0042
Form Tarihi            : 12/04/2026
Form Sahibi (Birim)    : Dijital Pazarlama Müdürlüğü
Aktarım Türü           : [X] Yurt dışı

──────────────────────────────────────────────────────────────
1. AKTARIMIN GENEL TANIMI
──────────────────────────────────────────────────────────────
Aktarımın Amacı        : E-ticaret müşterilerine pazarlama
                         otomasyonu (e-posta, push, SMS)
                         ve segmentasyon analitiği.
İş Süreci Sahibi       : Pazarlama Müdürü
Veri Sorumlusu         : [ŞİRKET ADI A.Ş.]
Alıcı (Unvan)          : Acme Marketing Cloud Ltd.
Alıcı Adres            : Dublin, İrlanda
Alıcı Ülke             : İrlanda (AB Üyesi)
Alıcı Statüsü          : [X] Veri İşleyen (Vİ)
Aktarım Sıklığı        : [X] Sürekli (real-time API)
Aktarımın Süresi       : Sözleşme süresi (3 yıl + yenileme)
Aktarımın Yöntemi      : [X] API + bulut barındırma
                         Sağlayıcı: Acme bulut, AB region

──────────────────────────────────────────────────────────────
2. VERİ KAPSAMI
──────────────────────────────────────────────────────────────
Veri Kategorileri      : Ad-soyad, e-posta, telefon, sipariş
                         geçmişi, davranış verisi, segment
                         (Envanter Madde No: ECOM-08, MKT-03)
İlgili Kişi Grupları   : [X] Müşteri
Veri Hassasiyeti       : [X] Genel
Yaklaşık Kayıt Sayısı  : 1.2 milyon aktif müşteri
Veri Hacmi             : ~50 GB / ay artış

──────────────────────────────────────────────────────────────
3. HUKUKI SEBEP — m.5/m.6 İŞLEME ŞARTI
──────────────────────────────────────────────────────────────
İşleme Şartı           : KVKK m.5/1 — Açık Rıza
                         (Pazarlama amacı için)
Şartın Sürdürülebilir-
liği                   : Rıza geri çekilebilir; geri çekilirse
                         sağlayıcıdan da silinmesi sağlanır
Aydınlatma             : [X] Yapıldı (Sürüm: 2026-Q1 v3.2)

──────────────────────────────────────────────────────────────
5. YURT DIŞI AKTARIM YOLU
──────────────────────────────────────────────────────────────
[X] (Aşama 2) Uygun Güvence (m.9/4)
    [X] (c) Standart Sözleşme
        Tür             : Tip 2 (VS → Vİ)
        İmza tarihi     : 10/04/2026
        Kurum'a bildirim
        tarihi          : 14/04/2026 (3 iş günü)

──────────────────────────────────────────────────────────────
6. ALICI ÜLKE DEĞERLENDİRMESİ
──────────────────────────────────────────────────────────────
Alıcı Ülke             : İrlanda

Veri Koruma Mevzuatı   : [X] Var ve kapsamlı (GDPR + Data
                         Protection Act 2018)
Bağımsız Otorite       : [X] Var (DPC — Data Protection
                         Commission)
İlgili Kişi Hakları    : [X] Etkin
Yargısal Koruma        : [X] Var (CJEU dahil)
Uluslararası Anlaşma   : [X] AB GDPR
                         [X] Convention 108

KAMU OTORİTESİ ERİŞİM RİSKİ
İstihbarat Erişimi     : [X] Düşük
Kolluk Erişimi         : [X] Düşük (yargısal denetim güçlü)
Disproportionate Risk  : [X] Düşük
Açıklama               : Sağlayıcının ABD ana şirketi var.
                         Veri AB region'da; ABD ana şirketin
                         erişimi sözleşmede sınırlandırıldı.

──────────────────────────────────────────────────────────────
7. EK TEDBİRLER
──────────────────────────────────────────────────────────────
TEKNIK
[X] At-rest şifreleme (AES-256)
[X] Transit şifreleme (TLS 1.3)
[X] BYOK — anahtar Şirket'te
[X] Veri minimizasyonu (sadece gerekli alanlar)
[X] Pseudonymization (kullanıcı ID hash'lenmiş)

SÖZLEŞMESEL
[X] Standart sözleşme (Tip 2)
[X] Ek protokol — ABD ana şirket erişim sınırı
[X] Notification of access requests
[X] Audit hakkı (yıllık)
[X] 24 saat ihlal bildirim hükmü

ORGANİZASYONEL
[X] Need-to-know
[X] Sözleşme sona erince 30 günde tüm verinin imhası

──────────────────────────────────────────────────────────────
8. ALT-İŞLEYEN ZİNCİRİ
──────────────────────────────────────────────────────────────
Alt-işleyen Listesi    : 4 adet (3 AB + 1 ABD CDN)
Alt-işleyen Onay       : Spesifik onay (önceden bildirim)
                         + 14 gün itiraz hakkı
ABD CDN Risk Notu      : Sadece statik içerik; PII içermez

──────────────────────────────────────────────────────────────
9. KALAN RİSK VE KARAR
──────────────────────────────────────────────────────────────
Risk Değerlendirmesi:
  Etkilenen kişi sayısı: 1.2 milyon
  Veri hassasiyeti     : Orta
  Aktarım sıklığı      : Yüksek (sürekli)
  Alıcı ülke riski     : Düşük
  Ek tedbir etkinliği  : Yüksek

Kalan Risk Seviyesi    : [X] Düşük

KARAR                  : [X] Aktarım onaylanır

──────────────────────────────────────────────────────────────
10. VERBİS GÜNCELLEMESİ
──────────────────────────────────────────────────────────────
[X] VERBİS güncellendi 15/04/2026
    Alıcı grubu        : Yurt dışı pazarlama hizmet sağlayıcısı

──────────────────────────────────────────────────────────────
11. ONAYLAR
──────────────────────────────────────────────────────────────
Hazırlayan             : Elif YAVUZ — Pazarlama Müdürü
Bilgi Güvenliği Onayı  : Mehmet KAYA — Bilgi Güv. Yön.
Hukuki Onay            : Av. Ahmet ÖZ — Hukuk Müdürü
KVKK Sorumlusu Onayı   : Selin YILDIZ — KVKK Sorumlusu
KVKK Komitesi          : 14/04/2026, Karar No: 2026/12
═══════════════════════════════════════════════════════════════
```

---

## 5. Örnek 2 — ABD CRM Sağlayıcısı (Yüksek Risk + Ek Tedbirler)

```
═══════════════════════════════════════════════════════════════
KİŞİSEL VERİ AKTARIM DEĞERLENDİRME VE ONAY FORMU
═══════════════════════════════════════════════════════════════

Form No                : TIA-2026-0058
Form Tarihi            : 22/04/2026
Form Sahibi (Birim)    : Satış Operasyon Müdürlüğü
Aktarım Türü           : [X] Yurt dışı

──────────────────────────────────────────────────────────────
1. AKTARIMIN GENEL TANIMI
──────────────────────────────────────────────────────────────
Aktarımın Amacı        : B2B müşteri ilişki yönetimi (CRM)
                         — satış pipeline, fırsat yönetimi,
                         müşteri yetkilisi iletişim kayıtları
İş Süreci Sahibi       : Satış Operasyon Direktörü
Alıcı (Unvan)          : Globex Cloud CRM Inc.
Alıcı Adres            : San Francisco, CA, ABD
Alıcı Ülke             : ABD
Alıcı Statüsü          : [X] Veri İşleyen (Vİ)
Aktarım Sıklığı        : [X] Sürekli
Aktarımın Süresi       : 5 yıl (yenilenebilir)
Aktarımın Yöntemi      : [X] API + bulut barındırma
                         Sağlayıcı bölgesi: us-east-1

──────────────────────────────────────────────────────────────
2. VERİ KAPSAMI
──────────────────────────────────────────────────────────────
Veri Kategorileri      : Müşteri yetkilisi ad-soyad, unvan,
                         iş e-posta, iş telefonu, satış
                         görüşme notları
                         (Envanter Madde No: SLS-01)
İlgili Kişi Grupları   : [X] Müşteri (B2B yetkilisi —
                         gerçek kişi sıfatıyla)
Veri Hassasiyeti       : [X] Genel
Yaklaşık Kayıt Sayısı  : 38.000 kişi (B2B yetkilisi)
Veri Hacmi             : ~5 GB / yıl

──────────────────────────────────────────────────────────────
3. HUKUKI SEBEP — m.5/m.6 İŞLEME ŞARTI
──────────────────────────────────────────────────────────────
İşleme Şartı           : KVKK m.5/2-(f) — Meşru Menfaat
                         (B2B satış sürecinin yürütülmesi)
                         + KVKK m.5/2-(c) — Sözleşme ifası
                         (mevcut sözleşmeli müşteriler için)
Aydınlatma             : [X] Müşteri yetkilisi aydınlatma
                         metni güncellendi (Sürüm: 2026-Q2)

──────────────────────────────────────────────────────────────
5. YURT DIŞI AKTARIM YOLU
──────────────────────────────────────────────────────────────
[X] (Aşama 2) Uygun Güvence (m.9/4)
    [X] (c) Standart Sözleşme
        Tür             : Tip 2 (VS → Vİ)
        İmza tarihi     : 20/04/2026
        Kurum'a bildirim
        tarihi          : 23/04/2026 (3 iş günü)

──────────────────────────────────────────────────────────────
6. ALICI ÜLKE DEĞERLENDİRMESİ
──────────────────────────────────────────────────────────────
Alıcı Ülke             : ABD

Veri Koruma Mevzuatı   : [X] Var ama sınırlı
                         (federal düzeyde sektörel; eyalet
                         düzeyinde CCPA/CPRA, Virginia VCDPA;
                         genel federal yasası yok)
Bağımsız Otorite       : [X] Sınırlı (FTC sektörel)
İlgili Kişi Hakları    : [X] Sınırlı
Yargısal Koruma        : [X] Sınırlı (yabancılar için)
Uluslararası Anlaşma   : [ ] AB GDPR — N/A
                         [ ] Convention 108 — N/A
                         (AB-ABD Data Privacy Framework AB
                          için geçerli, KVKK kapsamında değil)

KAMU OTORİTESİ ERİŞİM RİSKİ
İstihbarat Erişimi     : [X] Yüksek (FISA 702, EO 12333)
Kolluk Erişimi         : [X] Orta (CLOUD Act etkisi)
Disproportionate Risk  : [X] Yüksek
Açıklama               : ABD istihbarat servislerinin yurt
                         dışı verilere geniş erişim yetkisi
                         var. Sözleşmesel hükümler yetersiz
                         kalabilir; ek teknik tedbirler kritik.

──────────────────────────────────────────────────────────────
7. EK TEDBİRLER
──────────────────────────────────────────────────────────────
TEKNIK
[X] At-rest şifreleme (AES-256)
[X] Transit şifreleme (TLS 1.3)
[X] BYOK — anahtar Türkiye'de Şirket KMS'inde
    (sağlayıcının kendi anahtarına erişimi yok)
[X] Field-level encryption — hassas alanlar (notlar)
[X] Veri minimizasyonu — sadece B2B iş verisi (özel
    yaşam, sosyal medya, foto göndermez)

SÖZLEŞMESEL
[X] Standart sözleşme (Tip 2)
[X] Ek protokol:
    - ABD kamu otoritesi erişim talebinde Şirket'e
      derhal bildirim (yerel hukuk izin verdiği ölçüde)
    - Erişim talebine sözleşmesel itiraz yükümlülüğü
    - Audit hakkı (yıllık 3rd party audit)
    - 24 saat ihlal bildirim
[X] Notification of access requests

ORGANİZASYONEL
[X] Need-to-know
[X] Erişim logları + Şirket SIEM entegrasyonu
[X] Sözleşme sona erince 30 günde imha

──────────────────────────────────────────────────────────────
8. ALT-İŞLEYEN ZİNCİRİ
──────────────────────────────────────────────────────────────
Alt-işleyen Listesi    : 6 adet (5 ABD + 1 İrlanda)
Alt-işleyen Onay       : Genel onay; her değişiklikte
                         30 gün önceden bildirim + itiraz hakkı
Yüksek Risk Notu       : Hint Hindistan destek ekibi vardı;
                         sözleşmede destek için hint
                         erişiminin yasaklanması talep edildi.

──────────────────────────────────────────────────────────────
9. KALAN RİSK VE KARAR
──────────────────────────────────────────────────────────────
Risk Değerlendirmesi:
  Etkilenen kişi sayısı: 38.000
  Veri hassasiyeti     : Orta-Yüksek (B2B notlar
                         hassas iş bilgisi içerebilir)
  Aktarım sıklığı      : Yüksek (sürekli)
  Alıcı ülke riski     : Yüksek
  Ek tedbir etkinliği  : Yüksek (BYOK + field encryption +
                         data minimization)

Kalan Risk Seviyesi    : [X] Orta

KARAR                  : [X] Aktarım onaylanır
                         Şart: yıllık TIA yenilemesi +
                         3rd party audit raporunun KVKK
                         Komitesi'ne sunulması.

──────────────────────────────────────────────────────────────
10. VERBİS GÜNCELLEMESİ
──────────────────────────────────────────────────────────────
[X] VERBİS güncellendi 24/04/2026
    Alıcı grubu        : Yurt dışı CRM hizmet sağlayıcısı

──────────────────────────────────────────────────────────────
11. ONAYLAR
──────────────────────────────────────────────────────────────
Hazırlayan             : Murat ARSLAN — Satış Op. Direktörü
Bilgi Güvenliği Onayı  : Mehmet KAYA — Bilgi Güv. Yön.
Hukuki Onay            : Av. Ahmet ÖZ — Hukuk Müdürü
KVKK Sorumlusu Onayı   : Selin YILDIZ — KVKK Sorumlusu
KVKK Komitesi          : 23/04/2026, Karar No: 2026/15
                         (yüksek riskli aktarım — komite onayı şart)

──────────────────────────────────────────────────────────────
12. EK BELGELER
──────────────────────────────────────────────────────────────
[X] Standart Sözleşme Tip 2 + ek protokol PDF
[X] Alt-işleyen listesi v1.4
[X] Aydınlatma metni 2026-Q2
[X] Globex SOC 2 Type II raporu
[X] Globex DPA + Subprocessor list
[X] BYOK mimari diyagramı
═══════════════════════════════════════════════════════════════
```

---

## 6. Form Yönetim Disiplini

| Konu | Kural |
|------|-------|
| Form No | TIA-[YIL]-[SIRA] formatı |
| Hazırlama tetikleyicisi | Yeni aktarım, sözleşme yenileme, mevzuat değişikliği, alıcı değişimi |
| Onay zinciri | Hazırlayan → Bilgi Güv. → Hukuk → KVKK Sorumlusu → (yüksek risk) KVKK Komitesi |
| Saklama süresi | 10 yıl |
| Yenileme | Yıllık veya tetiklenmiş |
| Saklama yeri | KVKK Sorumlusu kontrolünde elektronik imzalı PDF |
| Aramalı indeks | Form no, tarih, alıcı, ülke, durum |
| Versiyon | Yenileme önceki sürümü iptal eder, yeni sürüm yürürlüğe girer |

## 7. Yüksek Risk Tetikleyicileri

Aşağıdaki durumlarda KVKK Komitesi onayı şarttır (KVKK Sorumlusu tek imza yeterli değil):

- Özel nitelikli kişisel veri aktarımı,
- Çocuk verisi aktarımı,
- 100.000+ ilgili kişiyi etkileyen aktarım,
- Yüksek riskli ülkeye aktarım (kamu otoritesi disproportionate erişim),
- Yeni ve denenmemiş bir sağlayıcıya aktarım,
- Açık rıza yerine meşru menfaate dayanan büyük ölçekli pazarlama aktarımı,
- BCR onay süreci.
