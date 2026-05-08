---
Doküman / Document: Tedarikçi (Üçüncü Taraf) Yönetimi ve Veri İşleyen İlişkileri Politikası / Vendor (Third Party) Management and Data Processor Relations Policy
Bölüm / Section: 06-idari-tedbirler
Sahip / Owner: Satınalma Direktörü + KVKK Sorumlusu + Hukuk Müşaviri / Procurement Director + KVKK Officer + Legal Counsel
Onaylayan / Approved by: KVKK Komitesi + Üst Yönetim / KVKK Committee + Senior Management
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş (önemli ihlal, yeni mevzuat, tedarikçi çıkış/giriş) / Annual + triggered (significant breach, new legislation, vendor exit/entry)
İlgili Mevzuat / Legal Reference: Law No. 6698 KVKK Art. 12 (joint and several liability of the data controller with the data processor), Art. 8 (domestic transfer), Art. 9 (cross-border transfer), Art. 4 (general principles); Data Controller - Data Processor distinction (KVKK Publication No:106 - June 2025); Turkish Code of Obligations (liability provisions); Law No. 6502 on Consumer Protection (where applicable)
İlgili Standart / Standard: ISO/IEC 27001:2022 A.5.19 (Information Security in Supplier Relationships), A.5.20 (Addressing Information Security within Supplier Agreements), A.5.21 (Managing Information Security in the ICT Supply Chain), A.5.22 (Monitoring, Review and Change Management of Supplier Services), A.5.23 (Information Security for Use of Cloud Services); ISO/IEC 27036 series; ISO/IEC 27701:2019 (PII Processor); NIST CSF 2.0 GV.SC, ID.SC; SOC 2 Type II; CSA Cloud Controls Matrix (CCM); GDPR Art. 28 (Processor)
---

## English

# Vendor (Third Party) Management

## 1. Purpose

To define the framework for consistently managing third parties accessing personal data and other critical information **as data controller**, or processing on our behalf, through contracts + audit + monitoring + exit chain to protect this data with KVKK and information security obligations.

The relationship between **Data Controller - Data Processor** in KVKK Publication No:106 (June 2025) and the Personal Data Security Guide is bound by **contract**. If a vendor contract does not exist or does not contain the minimum elements, the data controller is **primarily** liable in case of breach.

## 2. Core Principles

1. **From Classification to Approval:** No vendor can access personal data without completing KVKK / information security assessment.
2. **Data Controller - Data Processor Distinction:** **Role** clearly defined for each vendor (data controller / data processor / joint data controller).
3. **Minimum Elements in Contract:** Elements required by the KVKK Regulation + additional protection clauses.
4. **Instruction Limit:** The data processor processes only within the **written instructions** of the data controller.
5. **Transparent Sub-Processor:** Pre-approval and transparency of subcontractors.
6. **Audit Right:** Our or third-party auditor's right to audit the vendor.
7. **Exit Management:** Return or destruction of data at end of contract, with proof of return.
8. **Continuous Monitoring:** Relationship doesn't end with signing; annual and risk-triggered monitoring.

## 3. Vendor Type / Classification

### 3.1. Data Processing Type

| Type | Definition | Example |
|-----|-------|-------|
| **Data Controller (Independent)** | Vendor processes for its own purpose; we are data controller, they are also data controller | Bank (payment), shipping company, public authority (formal reporting) |
| **Joint Data Controller** | We jointly determine the processing purpose | Joint market research (KVKK Publication No:106 example), joint customer program |
| **Data Processor** | Processes on our behalf, by our instruction | SaaS provider (CRM, ERP, HR), cloud storage, call center outsource, IT support |

### 3.2. Risk Classification (Criticality)

| Class | Criterion | Example | Approval |
|-------|--------|-------|------|
| **A — Critical** | Special-category data / 100K+ records / critical infrastructure | Health data processor, banking core | KVKK Committee + Senior Management |
| **B — High** | General personal data 10K+ / high business criticality | CRM, HR SaaS, payment | KVKK Committee |
| **C — Medium** | Limited personal data / standard business | Marketing automation, helpdesk SaaS | KVKK Officer |
| **D — Low** | No personal data or minimum | Coffee machine, stationery | Procurement standard |

## 4. Lifecycle

```
1. Vendor Need Definition (Business Unit)
2. Risk and Classification (Procurement + KVKK Officer)
3. Due Diligence (Pre-contract Assessment)
4. Contract Negotiation and Signature
5. Onboarding and Access Activation
6. Operational Management and Continuous Monitoring
7. Annual (or quarterly) Review
8. Incident Management and Breach Notification
9. Contract Renewal or Exit
10. Data Return / Destruction + Access Closure
```

## 5. Due Diligence (Pre-Contract Assessment)

### 5.1. KVKK Compliance Questionnaire (Filled by Vendor)

Minimum questions:

1. Will it be a data controller or data processor under KVKK?
2. Is there a VERBİS registration obligation; if so, registration number?
3. Has it appointed a KVKK Officer / DPO, contact information?
4. How are out-of-purpose use prohibitions enforced?
5. Retention period policies?
6. Where will personal data be stored (country, city, data center)?
7. Is there cross-border transfer? To which country, by which mechanism?
8. Subcontractor list + classification?
9. Personnel training and confidentiality undertaking process?
10. ISO 27001, ISO 27701, SOC 2 Type II certification? Scope?
11. Has there been a data breach in the last 1-2 years?
12. What is our notification SLA in case of breach?
13. Penetration test frequency and last result summary?
14. Bug bounty program?
15. Annual internal + external audit reports?
16. Insurance (cyber liability, professional indemnity)?
17. End-of-contract data return/destruction process and evidence?
18. Exit strategy (data portability, vendor lock-in)?

### 5.2. Document and Certificate Request

| Document | Class A | Class B | Class C |
|-------|---------|---------|---------|
| ISO 27001 certificate | Mandatory | Mandatory | Recommended |
| ISO 27701 certificate | Mandatory | Recommended | Optional |
| SOC 2 Type II report | Mandatory (annual) | Recommended | Optional |
| Penetration test summary report | Mandatory (annual) | Mandatory (every 2 years) | Recommended |
| Cyber insurance policy | Mandatory | Mandatory | Optional |
| KVKK compliance questionnaire response | Mandatory | Mandatory | Mandatory |
| Financial statement / creditworthiness | Mandatory | Mandatory | Recommended |
| BCP/DR plan | Mandatory | Mandatory | Optional |
| Subcontractor list | Mandatory | Mandatory | Recommended |
| Data flow diagram | Mandatory | Mandatory | – |

### 5.3. Site / Remote Assessment

- Class A: annual on-site or video site audit.
- Class B: at least 1 video meeting per year + documentation review.
- Class C: questionnaire may suffice.

### 5.4. Score and Approval

- 0-100 score (per item weight + answer score).
- Threshold: ≥85 for A, ≥75 for B, ≥60 for C.
- Below-threshold vendor: either conditional approval with improvement plan (90 days) or rejection.

## 6. Data Processor Contract — Minimum Elements

KVKK Art. 12 and KVKK Personal Data Security Guide requirements + international good practice.

### 6.1. Mandatory Clauses

```
1. PARTIES and SUBJECT
   1.1. Definition of Data Controller (us) and Data Processor (vendor).
   1.2. Purpose of the Contract: <scope of services>.
   1.3. The Data Processor may process personal data only within the
        scope of this Contract and the written instructions of the Data
        Controller.

2. DATA SUBJECT TO PROCESSING (Annex-1 Data Flow)
   2.1. Categories of data processed.
   2.2. Data subjects (groups of data subjects).
   2.3. Processing purposes.
   2.4. Processing periods.
   2.5. Processing methods.
   2.6. Transfer (if any) destinations.

3. INSTRUCTION LIMIT
   3.1. The Data Processor cannot process outside instructions.
   3.2. If the Data Processor believes the instruction is unlawful,
        it shall promptly notify the Data Controller in writing.
   3.3. The Data Processor cannot use, copy, share with third parties
        the personal data for its own purposes.

4. CONFIDENTIALITY
   4.1. The Data Processor guarantees that all personnel with access
        to personal data have signed a confidentiality undertaking
        and receive regular training.
   4.2. Training and undertaking records are presented on request.

5. SECURITY MEASURES
   5.1. The Data Processor provides the technical and organizational
        measures defined in KVKK Art. 12 and the Personal Data Security
        Guide.
   5.2. Minimum technical measures are listed in ANNEX-2.
   5.3. Controls must be at least equivalent to ISO 27001 / ISO 27701 /
        SOC 2 standards.

6. SUB-PROCESSOR
   6.1. The Data Processor subjects the use of subcontractors to the
        prior written consent of the Data Controller.
   6.2. The current sub-processor list is provided in ANNEX-3.
   6.3. Sub-processor changes are notified to the Data Controller at
        least 30 days in advance; the right to object is reserved.
   6.4. The Data Processor is obligated to enter into a written contract
        providing the same minimum protection as this Contract with the
        sub-processor.
   6.5. The Data Processor is liable for the actions of the sub-processor
        as if its own.

7. TRANSFER (DOMESTIC / CROSS-BORDER)
   7.1. Domestic transfer can be made with the written consent of the
        Data Controller.
   7.2. Cross-border transfer is made only with one of the legal
        mechanisms of KVKK Art. 9 (adequacy decision / standard contract
        / binding corporate rules / explicit consent).
   7.3. Transfer destination, method, legal basis are specified in the
        contract annex.

8. SUPPORT FOR DATA SUBJECT RIGHTS
   8.1. The Data Processor refers a data subject application within
        the scope of KVKK Art. 11 to the Data Controller; does not
        respond itself.
   8.2. Provides the necessary information/action support for the Data
        Controller's response to the application without charge and
        without delay (maximum 5 business days).

9. DATA BREACH NOTIFICATION
   9.1. The Data Processor reports any data breach suspicion to the
        Data Controller within 24 hours at the latest.
   9.2. Minimum content of notification: time, affected data category,
        number of data subjects, measures taken, ongoing risk.
   9.3. Provides full support to the Data Controller's process of
        reporting to the KVKK Authority within 72 hours; delay or
        incomplete information constitutes vendor default.

10. ASSISTANCE OBLIGATION
    10.1. The Data Processor provides assistance to the Data Controller
          in processes such as DPIA, KVKK Authority audit, data mapping.

11. RIGHT OF AUDIT
    11.1. The Data Controller or its authorized independent auditor has
          the right to perform an audit at the Data Processor's
          facilities, systems and documents with reasonable advance
          notice.
    11.2. Annual SOC 2 Type II / ISO 27001 audit reports may be requested;
          this alone does not eliminate the right of audit.
    11.3. Audit is planned according to reasonable measures, access to
          trade secrets is within the scope of NDA.
    11.4. The Data Processor presents 30/60/90 day CAPA plan for audit
          findings.

12. RETENTION, RETURN and DESTRUCTION
    12.1. The Data Processor stores personal data only during the
          Contract.
    12.2. When the Contract terminates, at the discretion of the Data
          Controller, (a) returns all data, or (b) destroys by secure
          method, and presents destruction record.
    12.3. All copies including backups are within the scope of
          destruction; data kept under legal retention obligation
          excluded.
    12.4. Return / destruction is completed within 30 days of contract
          termination at the latest.

13. INDEMNITY AND INSURANCE
    13.1. The Data Processor is liable for the administrative fine,
          compensation, court costs arising from the KVKK breach in
          proportion to its own fault.
    13.2. The Data Processor declares that it has a valid cyber liability
          insurance; policy limit added to the contract.

14. ASSIGNMENT / EXCEPTION
    14.1. The Contract cannot be assigned without the written consent
          of the Data Controller.
    14.2. Data cannot be transferred to another vendor without the
          end of services.

15. TERM AND TERMINATION
    15.1. Contract term: <years>
    15.2. The Data Controller may terminate immediately in case of
          severe breach.

16. APPLICABLE LAW / COMPETENT COURT
    16.1. Laws of the Republic of Turkey.
    16.2. <City> Courts and Enforcement Offices are competent.

ANNEXES
   ANNEX-1: Data Flow Diagram + Data Categories
   ANNEX-2: Minimum Technical and Organizational Measures List
   ANNEX-3: Approved Sub-Processor List
   ANNEX-4: Cross-Border Transfer Mechanism (if applicable)
```

### 6.2. Annex-2 Minimum Technical Measures List

Annex added to the contract; vendor provides minimum the following:

- Access control: RBAC, MFA, JML, quarterly review.
- Encryption: at-rest AES-256, in-transit TLS 1.2+ (1.3 preferred), HSM/KMS keys.
- Logging: identity, authorization, personal data access, log integrity.
- Backup: 3-2-1, immutable copy, restore test.
- IR: notification within 24 hours, runbook, post-mortem.
- Penetration test: annual.
- Personnel: mandatory training + confidentiality undertaking.
- Data segregation: logical/physical separation in multi-tenant environment.

### 6.3. Standard Contract Clauses (Cross-Border Transfer)

When the KVKK Authority publishes the "country providing adequate protection" list or the standard contract template in the future, the contract annex will be aligned with these standard clauses. Until that time:

- Explicit consent (may be insufficient; lacks continuity).
- KVKK Art. 9(2) "guarantees in writing the provision of adequate protection and obtaining the permission of the Authority" — undertaking + Authority permit process is conducted by legal team.

## 7. Onboarding and Access Activation

| Step | Owner | SLA |
|------|-------|-----|
| Contract signature and annexes | Legal + Procurement | – |
| Vendor personnel confidentiality undertaking | HR + Procurement | Before signing |
| Access request form (role-based, JIT) | Business Unit + IAM | 5 business days before activation date |
| Account creation + MFA | IAM | Activation -1 |
| Onboarding training + knowledge test | HR + KVKK Officer | First week |
| KVKK Officer adding to inventory | KVKK Officer | Contract signature + 7 days |
| VERBİS update (if necessary) | KVKK Officer | Before activation |

## 8. Operational Monitoring

### 8.1. Periodic

- Monthly SLA / KPI report (uptime, breaches, success rate).
- Quarterly vendor review (Class A); annual (B/C).
- Annual audit report (SOC 2 Type II / ISO 27001).
- Annual penetration test result sharing.
- Annual BCP/DR drill results.

### 8.2. Event-Based

- Vendor breach notification → 24 hour KVKK Officer review → KVKK Committee escalation threshold.
- Vendor side organization change (M&A, ownership, location change) → assessment.
- Sub-processor change → approval + contract update.

### 8.3. SLA / KPI Example

| KPI | Target | Reporting |
|-----|-------|-----------|
| System uptime | 99.9%+ | Monthly |
| Breach notification time | ≤24 hours | Per event |
| Data subject application support SLA | ≤5 business days | Per event |
| Annual penetration test | 1+ | Annual |
| Personnel training completion | 100% | Annual |
| Patch SLA (critical) | ≤7 days | Monthly |
| Access review | Quarterly | Quarterly |

## 9. Multi-Vendor Mapping

For complex ecosystems, **Data Flow Diagram** is mandatory:

```
Data Subject (Customer) 
     ↓ data entry
[Our Web Application]
     ├── [CDN — Cloudflare] (transit, log) ←—— data controller (for own log)
     ├── [Auth — Auth0] (identity) ←—— data processor
     ├── [DB — RDS PostgreSQL] (personal data at-rest) ←—— data processor (AWS)
     ├── [CRM — Salesforce] (customer relationship) ←—— data processor
     │      └── [Sub-processor — AWS] (Salesforce's infra)
     ├── [Communication — SendGrid] (email) ←—— data processor
     ├── [Analytics — Mixpanel] (usage) ←—— ?? (evaluate role)
     ├── [Payment — Iyzico] (card) ←—— independent data controller (card)
     └── [Call Center — XYZ] (support) ←—— data processor
              └── [Sub-processor — VoIP provider]
```

For each connection: role, legal basis, contract type, transfer mechanism, class.

This map is kept up-to-date in the VERBİS record and the inventory document under [02-envanter-ve-sicil/](../02-envanter-ve-sicil/).

## 10. Exit Management (Off-Boarding)

```
1. Exit Decision (no renewal / cancellation / change)
2. Exit Plan Preparation (T-90)
3. Data Migration Plan (if necessary to new vendor or to us)
4. Data Return / Destruction Request (written)
5. Return / Destruction Record (vendor signed)
6. Access Closure (T-0)
7. Certificate / Key Revocation
8. Removal from KVKK Inventory
9. Lessons Learned + Document Archive
```

If vendor delays or refuses to cooperate: legal process + KVKK Committee report + warning in next vendor selection.

## 11. Cloud Service Providers (Special Section)

Per ISO 27001 A.5.23 and the KVKK Personal Data Security Guide section "Storage of Personal Data in the Cloud":

### 11.1. Approved Cloud Provider List

- Approved list updated annually by the KVKK Committee.
- Use of providers outside the list is forbidden (shadow IT — see CASB, [05-teknik-tedbirler/dlp.md](../05-teknik-tedbirler/dlp.md)).

### 11.2. Cloud-Specific Controls

- Data location (region) bound by contract (domestic preferred).
- Customer-managed key (CMK / BYOK) mandatory for Class A.
- Sub-processor transparency (AWS, Azure, GCP subcontractors tracked from vendor page).
- Exit strategy (data portability) by contract.
- Cross-border transfer mechanism explicit.

### 11.3. Shared Responsibility Model

A **shared responsibility matrix** is added to the contract; clearly distinguishing which control is on us and which on the vendor. The cloud provider is responsible for infrastructure security, we are responsible for configuration and data layer (CIS Benchmarks, CSPM).

## 12. Scenarios Where We Are the Data Processor (Reverse)

If we **process data on behalf of another data controller** (e.g., providing SaaS to our customer):

- This time, as the "data processor", we have the necessary contract + audit rights + IR notification obligations of the customer.
- The KVKK Officer keeps a bidirectional inventory (us as processor vs. us as controller).
- ISO 27701 (PII Processor) certification is a marketing advantage + compliance evidence for this role.

## 13. Discipline and Sanctions

- If vendor breaches the contract: written warning → improvement plan → non-compliance → termination.
- In severe breach (data leakage, confidentiality), immediate termination + compensation + notification to KVKK Authority.
- A vendor blacklist is kept; vendor will not be re-engaged on similar breach.

## 14. Annual Vendor Management Report

Annual to KVKK Committee:

- Total vendor count / class-based distribution.
- New added / removed vendors.
- KVKK compliance questionnaire completion rate.
- Contract renewal rate.
- Vendor side incidents / breaches.
- Annual audit results.
- Open CAPA actions.
- Total annual spend (classification-based).
- Cross-border transfer inventory summary.
- Trend analysis (sector + ours).

## 15. Checklist

- [ ] Is the vendor policy ≤24 months current?
- [ ] Are all vendors classified (A/B/C/D), inventoried?
- [ ] For Class A/B, is a Data Processor Contract signed, containing the minimum elements?
- [ ] Is the contract template Legal + KVKK Officer approved, latest update within 12 months?
- [ ] Is the sub-processor list transparent, change notification mechanism working?
- [ ] Is the cross-border transfer mechanism specific for each vendor (Art. 9 basis)?
- [ ] Is the data flow diagram current, paired with inventory?
- [ ] Is confidentiality undertaking and training mandatory in vendor onboarding?
- [ ] Is the vendor's KVKK Officer / DPO contact recorded?
- [ ] Is the breach notification SLA (24 hours) written in the contract?
- [ ] Are annual SOC 2 / ISO 27001 reports collected, reviewed?
- [ ] Are penetration test reports collected annually?
- [ ] Is quarterly (Class A) / annual (B/C) review performed, recorded?
- [ ] Is the cloud provider list approved, BYOK policy applied?
- [ ] Is the exit process data return/destruction record standard?
- [ ] Are lessons learned recorded after vendor breach?
- [ ] Is the vendor blacklist mechanism defined?
- [ ] Is cyber liability insurance requested (Class A/B)?
- [ ] Are the vendor contract assignment, sub-contractor, termination clauses clear?
- [ ] Is the VERBİS record current with vendor changes?

## 16. Common Mistakes

- "Standard service contract" signed, no KVKK / data processor additional protocol.
- Sub-processor list not kept; vendor changes subcontractor, we are not informed.
- Trusting cloud provider's "datasheet" and not realizing our own configuration responsibility.
- Cross-border transfer legal basis unclear; no Art. 9 compliant mechanism.
- Access not closed after vendor leaves (old user account active).
- Data return/destruction record not taken; data lying on vendor's side for years.
- Audit clause of the contract abstract; practical audit cannot be performed.
- Breach on vendor's side — our 72-hour KVKK Authority deadline counts down but vendor delays with "investigating".

---

## Türkçe

# Tedarikçi (Üçüncü Taraf) Yönetimi

## 1. Amaç

Kişisel veri ve diğer kritik bilgileri **veri sorumlusu sıfatımızla** korumak için, bu veriye erişen veya bizim adımıza işleyen üçüncü tarafların KVKK ve bilgi güvenliği yükümlülüklerini sözleşme + denetim + izleme + çıkış zinciriyle tutarlı şekilde yöneten çerçeveyi tanımlar.

KVKK Yayını No:106 (Haziran 2025) ve Kişisel Veri Güvenliği Rehberi'nde "Veri Sorumlusu - Veri İşleyen" arasındaki ilişki **sözleşmeye** bağlanır. Tedarikçi sözleşmesi yoksa veya asgari unsurları taşımıyorsa, ihlal halinde veri sorumlusu **birinci derece** sorumludur.

## 2. Temel İlkeler

1. **Sınıflandırmadan Onaylamaya:** Hiçbir tedarikçi, KVKK / bilgi güvenliği değerlendirmesi tamamlanmadan kişisel veriye erişemez.
2. **Veri Sorumlusu - Veri İşleyen Ayrımı:** Her tedarikçi için **rolü** açık tanımlanır (veri sorumlusu / veri işleyen / müşterek veri sorumlusu).
3. **Sözleşmede Asgari Unsurlar:** KVKK Yönetmeliği'nde aranan unsurlar + ek koruma maddeleri.
4. **Talimat Sınırlaması:** Veri işleyen, yalnızca veri sorumlusunun **yazılı talimatı** çerçevesinde işler.
5. **Şeffaf Alt-İşleyen:** Alt yüklenicilerin önceden onaylanması ve şeffaflığı.
6. **Denetim Hakkı:** Bizim veya üçüncü taraf denetçinin tedarikçiyi denetleme hakkı.
7. **Çıkış Yönetimi:** Sözleşme bitiminde verinin iade veya imhası, dönüş kanıtı.
8. **Sürekli İzleme:** İlişki imzayla bitmez; yıllık ve risk-tetikli izleme.

## 3. Tedarikçi Tip / Sınıflandırma

### 3.1. Veri İşleme Tipi

| Tip | Tanım | Örnek |
|-----|-------|-------|
| **Veri Sorumlusu (Bağımsız)** | Tedarikçi kendi amacı için işliyor; biz veri sorumlusu, o da veri sorumlusu | Banka (ödeme), kargo şirketi, kamu kurumu (resmi raporlama) |
| **Müşterek Veri Sorumlusu** | İşleme amacını birlikte belirliyoruz | Ortak yürütülen pazar araştırması (KVKK Yayını No:106 örneği), ortak müşteri programı |
| **Veri İşleyen** | Bizim adımıza, talimatımızla işliyor | SaaS sağlayıcı (CRM, ERP, IK), bulut depolama, çağrı merkezi outsource, BT destek |

### 3.2. Risk Sınıflandırması (Kritiklik)

| Sınıf | Kriter | Örnek | Onay |
|-------|--------|-------|------|
| **A — Kritik** | Özel nitelikli veri / 100K+ kayıt / kritik altyapı | Sağlık verisi işleyen, bankacılık çekirdeği | KVKK Komitesi + Üst Yön. |
| **B — Yüksek** | Genel kişisel veri 10K+ / iş kritikliği yüksek | CRM, IK SaaS, ödeme | KVKK Komitesi |
| **C — Orta** | Sınırlı kişisel veri / standart iş | Pazarlama otomasyon, helpdesk SaaS | KVKK Sorumlusu |
| **D — Düşük** | Kişisel veri yok veya minimum | Kahve makinesi, kırtasiye | Satınalma standart |

## 4. Yaşam Döngüsü

```
1. Tedarikçi İhtiyacı Tanımlama (İş Birimi)
2. Risk ve Sınıflandırma (Satınalma + KVKK Sorumlusu)
3. Due Diligence (Pre-contract Assessment)
4. Sözleşme Müzakere ve İmza
5. Onboarding ve Erişim Aktivasyonu
6. Operasyonel Yönetim ve Sürekli İzleme
7. Yıllık (veya çeyreklik) Review
8. Olay Yönetimi ve İhlal Bildirimi
9. Sözleşme Yenileme veya Çıkış
10. Veri İade / İmha + Erişim Kapatma
```

## 5. Due Diligence (Sözleşme Öncesi Değerlendirme)

### 5.1. KVKK Uyum Anketi (Tedarikçi Doldurur)

Asgari sorular:

1. KVKK kapsamında veri sorumlusu mu, veri işleyen mi olacak?
2. VERBİS kayıt yükümlülüğü var mı; varsa kayıt no?
3. KVKK Sorumlusu / DPO atadı mı, irtibat bilgisi?
4. İşleme amacı dışında kullanım yasakları nasıl uygulanır?
5. Saklama süresi politikaları?
6. Kişisel veriyi nerede saklayacak (ülke, şehir, veri merkezi)?
7. Yurt dışı aktarım var mı? Hangi ülkeye, hangi mekanizma ile?
8. Alt yüklenici listesi + sınıflandırması?
9. Personel eğitim ve gizlilik taahhütname süreci?
10. ISO 27001, ISO 27701, SOC 2 Type II sertifikası var mı? Kapsamı?
11. Son 1-2 yıl içinde veri ihlali oldu mu?
12. İhlal halinde bizim bildirim SLA'mız nedir?
13. Sızma testi sıklığı ve son sonuç özeti?
14. Bug bounty programı var mı?
15. Yıllık iç + dış denetim raporları?
16. Sigorta (cyber liability, professional indemnity)?
17. Sözleşme bitiminde veri iade/imha süreci ve kanıtı?
18. Çıkış stratejisi (data portability, vendor lock-in)?

### 5.2. Belge ve Sertifika Talebi

| Belge | Sınıf A | Sınıf B | Sınıf C |
|-------|---------|---------|---------|
| ISO 27001 sertifikası | Zorunlu | Zorunlu | Tavsiye |
| ISO 27701 sertifikası | Zorunlu | Tavsiye | Opsiyonel |
| SOC 2 Type II raporu | Zorunlu (yıllık) | Tavsiye | Opsiyonel |
| Sızma testi özet rapor | Zorunlu (yıllık) | Zorunlu (2 yılda 1) | Tavsiye |
| Cyber sigorta poliçesi | Zorunlu | Zorunlu | Opsiyonel |
| KVKK uyum anket cevabı | Zorunlu | Zorunlu | Zorunlu |
| Mali tablo / kredibilite | Zorunlu | Zorunlu | Tavsiye |
| BCP/DR planı | Zorunlu | Zorunlu | Opsiyonel |
| Alt-işleyen listesi | Zorunlu | Zorunlu | Tavsiye |
| Veri akış diyagramı | Zorunlu | Zorunlu | – |

### 5.3. Saha / Uzaktan Değerlendirme

- Sınıf A: yıllık on-site veya video saha denetimi.
- Sınıf B: yılda en az 1 video toplantı + dokümantasyon review.
- Sınıf C: anket yeterli olabilir.

### 5.4. Skor ve Onay

- 0-100 skor (her madde ağırlık + cevap puanı).
- Eşik: A için ≥85, B için ≥75, C için ≥60.
- Eşik altı tedarikçi: ya iyileştirme planıyla şartlı onay (90 gün) ya da ret.

## 6. Veri İşleyen Sözleşmesi — Asgari Unsurlar

KVKK m.12 ve KVKK Veri Güvenliği Rehberi gerekleri + uluslararası iyi uygulama.

### 6.1. Zorunlu Maddeler

```
1. TARAFLAR ve KONU
   1.1. Veri Sorumlusu (biz) ve Veri İşleyen (tedarikçi) tanımı.
   1.2. Sözleşme'nin amacı: <hizmet kapsamı>.
   1.3. Veri İşleyen, kişisel verileri yalnızca bu Sözleşme kapsamı ve
        Veri Sorumlusu'nun yazılı talimatları dahilinde işleyebilir.

2. İŞLEME KONUSU VERİLER (Ek-1 Veri Akışı)
   2.1. İşlenen veri kategorileri.
   2.2. Veri konuları (ilgili kişi grupları).
   2.3. İşleme amaçları.
   2.4. İşleme süreleri.
   2.5. İşleme yöntemleri.
   2.6. Aktarım (eğer varsa) hedefleri.

3. TALİMAT SINIRI
   3.1. Veri İşleyen, talimat dışı işleme yapamaz.
   3.2. Talimatın hukuka aykırı olduğunu düşünüyorsa, Veri Sorumlusu'na
        derhal yazılı bildirim yapar.
   3.3. Veri İşleyen, kişisel verileri kendi amaçları için kullanamaz,
        kopyalayamaz, üçüncü taraflarla paylaşamaz.

4. GİZLİLİK
   4.1. Veri İşleyen, kişisel verilere erişebilen tüm personelinin
        gizlilik taahhüdü imzaladığını ve düzenli eğitim aldığını
        garanti eder.
   4.2. Eğitim ve taahhüt kayıtları talep halinde sunulur.

5. GÜVENLİK TEDBİRLERİ
   5.1. Veri İşleyen, KVKK m.12 ve Veri Güvenliği Rehberi kapsamında
        belirlenen teknik ve idari tedbirleri sağlar.
   5.2. Asgari teknik tedbirler EK-2'de listelenmiştir.
   5.3. Kontroller ISO 27001 / ISO 27701 / SOC 2 standartlarıyla en az
        eşdeğer olmalıdır.

6. ALT-İŞLEYEN (SUB-PROCESSOR)
   6.1. Veri İşleyen, alt yüklenici kullanımını Veri Sorumlusu'nun ön
        yazılı onayına tabi tutar.
   6.2. Mevcut alt-işleyen listesi EK-3'te yer alır.
   6.3. Alt-işleyen değişikliği, en az 30 gün önceden Veri Sorumlusu'na
        bildirilir; itiraz hakkı saklıdır.
   6.4. Veri İşleyen, alt-işleyenle bu Sözleşme'yle aynı asgari koruma
        sağlayan yazılı sözleşme yapmakla yükümlüdür.
   6.5. Veri İşleyen, alt-işleyenin eylemlerinden kendi eylemleri gibi
        sorumludur.

7. AKTARIM (YURT İÇİ / YURT DIŞI)
   7.1. Yurt içi aktarım Veri Sorumlusu'nun yazılı izni ile yapılabilir.
   7.2. Yurt dışı aktarım yalnızca KVKK m.9 hukuki mekanizmalarından
        biriyle (yeterli koruma kararı / standart sözleşme / bağlayıcı
        kurumsal kurallar / açık rıza) yapılır.
   7.3. Aktarım hedefi, yöntemi, hukuki dayanağı sözleşme ekinde
        belirtilir.

8. İLGİLİ KİŞİ HAKLARINA DESTEK
   8.1. Veri İşleyen, KVKK m.11 kapsamındaki ilgili kişi başvurusunu
        Veri Sorumlusu'na yönlendirir; kendisi cevap vermez.
   8.2. Veri Sorumlusu'nun başvuru yanıtlamasında gerekli bilgi/aksiyon
        desteğini ücretsiz ve gecikmeksizin sağlar (azami 5 iş günü).

9. VERİ İHLALİ BİLDİRİMİ
   9.1. Veri İşleyen, herhangi bir veri ihlali şüphesini en geç 24 saat
        içinde Veri Sorumlusu'na bildirir.
   9.2. Bildirim asgari içerik: zaman, etkilenen veri kategorisi, ilgili
        kişi sayısı, alınan tedbirler, devam eden risk.
   9.3. Veri Sorumlusu'nun KVKK Kurulu'na 72 saatlik bildirim sürecine
        tam destek verir; gecikme veya eksik bilgi tedarikçi temerrüdü
        sayılır.

10. YARDIM YÜKÜMLÜLÜĞÜ
    10.1. Veri İşleyen; DPIA, KVKK Kurulu denetimi, veri haritalaması
          gibi süreçlerde Veri Sorumlusu'na yardım sağlar.

11. DENETİM HAKKI
    11.1. Veri Sorumlusu veya yetkili kıldığı bağımsız denetçi, makul
          önbildirim ile Veri İşleyen'in tesislerinde, sistemlerinde ve
          dokümanlarında denetim yapma hakkına sahiptir.
    11.2. Yıllık SOC 2 Type II / ISO 27001 denetim raporları talep
          edilebilir; bu tek başına denetim hakkını ortadan kaldırmaz.
    11.3. Denetim makul ölçülere göre planlanır, ticari sırlara erişimi
          NDA çerçevesinde gerçekleşir.
    11.4. Denetim bulguları için Veri İşleyen 30/60/90 gün CAPA planı
          sunar.

12. SAKLAMA, İADE ve İMHA
    12.1. Veri İşleyen, kişisel verileri yalnızca Sözleşme süresince
          saklar.
    12.2. Sözleşme sona erdiğinde, Veri Sorumlusu'nun seçimine göre
          (a) tüm verileri iade eder, veya (b) güvenli yöntemle imha
          eder, ve imha tutanağı sunar.
    12.3. Yedekler dahil tüm kopyalar imha kapsamına dahildir; yasal
          saklama yükümlülüğü kapsamında tutulan veriler hariç.
    12.4. İade / imha en geç sözleşme bitiminden itibaren 30 gün içinde
          tamamlanır.

13. TAZMİNAT VE SİGORTA
    13.1. Veri İşleyen, KVKK ihlalinden doğacak idari para cezası,
          tazminat, dava giderlerinden kendi kusuru oranında sorumludur.
    13.2. Veri İşleyen, geçerli bir cyber liability sigortasına sahip
          olduğunu beyan eder; poliçe sınırı sözleşmeye eklenir.

14. DEVİR / İSTİSNA
    14.1. Sözleşme, Veri Sorumlusu'nun yazılı izni olmaksızın devredilemez.
    14.2. Hizmet bitimi olmadan veri başka bir vendor'a aktarılamaz.

15. SÜRE VE FESİH
    15.1. Sözleşme süresi: <yıl>
    15.2. Veri Sorumlusu, ağır ihlal halinde derhal feshedebilir.

16. UYGULANACAK HUKUK / YETKİLİ MAHKEME
    16.1. Türkiye Cumhuriyeti hukuku.
    16.2. <Şehir> Mahkemeleri ve İcra Daireleri yetkili.

EKLER
   EK-1: Veri Akış Diyagramı + Veri Kategorileri
   EK-2: Asgari Teknik ve İdari Tedbir Listesi
   EK-3: Onaylı Alt-İşleyen Listesi
   EK-4: Yurt Dışı Aktarım Mekanizması (uygunsa)
```

### 6.2. Ek-2 Asgari Teknik Tedbir Listesi

Sözleşmeye eklenen ek; tedarikçi minimum aşağıdakileri sağlar:

- Erişim kontrolü: RBAC, MFA, JML, çeyreklik review.
- Şifreleme: at-rest AES-256, in-transit TLS 1.2+ (1.3 tercih), HSM/KMS anahtar.
- Loglama: kimlik, yetki, kişisel veri erişimi, log bütünlüğü.
- Yedek: 3-2-1, immutable kopya, restore test.
- IR: 24 saat içinde bildirim, runbook, post-mortem.
- Sızma testi: yıllık.
- Personel: zorunlu eğitim + gizlilik taahhüdü.
- Veri ayrımı: çoklu kiracı (multi-tenant) ortamda mantıksal/fiziksel ayırım.

### 6.3. Standart Sözleşme Maddeleri (Yurt Dışı Aktarım)

KVKK Kurulu'nun ileride "yeterli koruma sağlayan ülke" listesi yayınladığında veya standart sözleşme şablonu çıkardığında, sözleşme eki bu standart hükümlerle uyumlanır. Bu zamana kadar:

- Açık rıza (yetersiz olabilir; süreklilik yok).
- KVKK m.9(2) "yeterli korumayı yazılı olarak taahhüt eden ve Kurul'un izninin alınması" — taahhütname + Kurul izni süreci hukuk ekibi tarafından yürütülür.

## 7. Onboarding ve Erişim Aktivasyonu

| Adım | Sahip | SLA |
|------|-------|-----|
| Sözleşme imzası ve ekleri | Hukuk + Satınalma | – |
| Tedarikçi personeli gizlilik taahhütnamesi | İK + Satınalma | İmzadan önce |
| Erişim talep formu (rol bazlı, JIT) | İş Birimi + IAM | Aktivasyon tarihinden 5 iş günü önce |
| Hesap oluşturma + MFA | IAM | Aktivasyon -1 |
| Onboarding eğitim + bilgi testi | İK + KVKK Sorumlusu | İlk hafta |
| KVKK Sorumlusu kayıt envanterine ekleme | KVKK Sorumlusu | Sözleşme imzası + 7 gün |
| VERBİS güncellemesi (gerekirse) | KVKK Sorumlusu | Aktivasyondan önce |

## 8. Operasyonel İzleme

### 8.1. Periyodik

- Aylık SLA / KPI raporu (uptime, ihlal, başarı oranı).
- Çeyreklik tedarikçi review (Sınıf A); yıllık (B/C).
- Yıllık denetim raporu (SOC 2 Type II / ISO 27001).
- Yıllık sızma testi sonuç paylaşımı.
- Yıllık BCP/DR tatbikatı sonuçları.

### 8.2. Olay Bazlı

- Tedarikçi ihlal bildirimi → 24 saat KVKK Sorumlusu inceleme → KVKK Komitesi eskalasyonu eşiği.
- Tedarikçi tarafında organizasyon değişikliği (M&A, sahiplik, yer değişikliği) → değerlendirme.
- Alt-işleyen değişikliği → onay + sözleşme güncelleme.

### 8.3. SLA / KPI Örneği

| KPI | Hedef | Raporlama |
|-----|-------|-----------|
| Sistem uptime | %99.9+ | Aylık |
| İhlal bildirim süresi | ≤24 saat | Olay başına |
| İlgili kişi başvuru destek SLA | ≤5 iş günü | Olay başına |
| Sızma testi yıllık | 1+ | Yıllık |
| Personel eğitim tamamlama | %100 | Yıllık |
| Patch SLA (kritik) | ≤7 gün | Aylık |
| Erişim review | Çeyreklik | Çeyreklik |

## 9. Çoklu Tedarikçi Haritalaması

Karmaşık ekosistemler için **Veri Akışı Diyagramı** zorunlu:

```
İlgili Kişi (Müşteri) 
     ↓ veri girişi
[Bizim Web Uygulamamız]
     ├── [CDN — Cloudflare] (transit, log) ←—— veri sorumlusu (kendi log için)
     ├── [Auth — Auth0] (kimlik) ←—— veri işleyen
     ├── [DB — RDS PostgreSQL] (kişisel veri at-rest) ←—— veri işleyen (AWS)
     ├── [CRM — Salesforce] (müşteri ilişkisi) ←—— veri işleyen
     │      └── [Alt-işleyen — AWS] (Salesforce'un infra'sı)
     ├── [İletişim — SendGrid] (e-posta) ←—— veri işleyen
     ├── [Analitik — Mixpanel] (kullanım) ←—— ?? (rol değerlendir)
     ├── [Ödeme — Iyzico] (kart) ←—— bağımsız veri sorumlusu (kart)
     └── [Çağrı Merkezi — XYZ] (destek) ←—— veri işleyen
              └── [Alt-işleyen — VoIP sağlayıcı]
```

Her bağlantı için: rol, hukuki dayanak, sözleşme tipi, aktarım mekanizması, sınıf.

VERBİS kaydında ve [02-envanter-ve-sicil/](../02-envanter-ve-sicil/) altındaki envanter dokümanında bu harita güncel tutulur.

## 10. Çıkış Yönetimi (Exit / Off-Boarding)

```
1. Çıkış Kararı (yenileme yok / iptal / değişim)
2. Çıkış Planı Hazırlama (T-90)
3. Veri Migrasyon Planı (gerekirse yeni tedarikçiye veya bize)
4. Veri İade / İmha Talebi (yazılı)
5. İade / İmha Tutanağı (tedarikçi imzalı)
6. Erişim Kapatma (T-0)
7. Sertifika / Anahtar İptal
8. KVKK Envanterinden Çıkartma
9. Lessons Learned + Belge Arşivi
```

Tedarikçi geç kalırsa veya işbirliği yapmazsa: hukuki süreç + KVKK Komitesi raporu + bir sonraki tedarikçi seçiminde uyarı.

## 11. Bulut Hizmet Sağlayıcıları (Özel Bölüm)

ISO 27001 A.5.23 ve KVKK Veri Güvenliği Rehberi'nin "Kişisel Verilerin Bulutta Depolanması" başlığı uyarınca:

### 11.1. Onaylı Bulut Sağlayıcı Listesi

- Onaylı liste KVKK Komitesi tarafından yıllık güncellenir.
- Liste dışı sağlayıcı kullanımı yasak (shadow IT — bkz. CASB, [05-teknik-tedbirler/dlp.md](../05-teknik-tedbirler/dlp.md)).

### 11.2. Bulut-Spesifik Kontroller

- Veri yerleşimi (region) sözleşmeyle bağlanır (yurt içi tercihli).
- Müşteri yönetimli anahtar (CMK / BYOK) Sınıf A için zorunlu.
- Sub-processor şeffaflığı (AWS, Azure, GCP'nin alt yüklenicileri vendor sayfasından izlenir).
- Çıkış stratejisi (data portability) sözleşmeyle.
- Yurt dışı aktarım mekanizması belirgin.

### 11.3. Shared Responsibility Model

Sözleşmeye **shared responsibility matrisi** eklenir; hangi kontrol bizde, hangisi tedarikçide net ayrışır. Bulut sağlayıcı altyapı güvenliğinden sorumlu, biz konfigürasyondan ve veri katmanından (CIS Benchmarks, CSPM) sorumluyuz.

## 12. Veri İşleyen Olduğumuz Senaryolar (Tersine)

Eğer biz **bir başka veri sorumlusu adına** veri işliyorsak (örn. müşterimize SaaS sağlıyorsak):

- Bu sefer biz "veri işleyen" sıfatıyla, müşterinin gerekli sözleşme + denetim hakkı + IR bildirim yükümlülüklerimiz olur.
- KVKK Sorumlusu, çift yönlü envanter tutar (biz işleyen vs. biz sorumlu).
- ISO 27701 (PII Processor) sertifikası bu rol için pazarlama avantajı + uyum kanıtı.

## 13. Disiplin ve Yaptırım

- Tedarikçi sözleşmeyi ihlal ederse: yazılı uyarı → düzeltme planı → uyumsuzluk → fesih.
- Ağır ihlalde (veri sızıntısı, gizlilik) derhal fesih + tazminat + KVKK Kurulu'na bildirim.
- Tedarikçi kara listesi tutulur; benzer ihlalde tekrar tedarikçi alınmaz.

## 14. Yıllık Tedarikçi Yönetim Raporu

KVKK Komitesi'ne yıllık:

- Toplam tedarikçi sayısı / sınıf bazlı dağılım.
- Yeni eklenen / çıkarılan tedarikçi.
- KVKK uyum anketi tamamlanma oranı.
- Sözleşme yenileme oranı.
- Tedarikçi tarafı olaylar / ihlaller.
- Yıllık denetim sonuçları.
- Açık CAPA aksiyonları.
- Toplam yıllık harcama (sınıflandırma bazlı).
- Yurt dışı aktarım envanteri özeti.
- Trend analizi (sektör + bizim).

## 15. Kontrol Listesi

- [ ] Tedarikçi politikası ≤24 ay güncel mi?
- [ ] Tüm tedarikçiler sınıflandırılmış (A/B/C/D), envanterli mi?
- [ ] Sınıf A/B için Veri İşleyen Sözleşmesi imzalı, asgari unsurları içeriyor mu?
- [ ] Sözleşme şablonu Hukuk + KVKK Sorumlusu onaylı, son güncellemesi 12 ay içinde mi?
- [ ] Alt-işleyen listesi şeffaf, değişiklik bildirim mekanizması işliyor mu?
- [ ] Yurt dışı aktarım mekanizması her tedarikçi için belirli mi (m.9 dayanak)?
- [ ] Veri akış diyagramı güncel, envanterle eşli mi?
- [ ] Tedarikçi onboarding sürecinde gizlilik taahhüdü ve eğitim zorunlu mu?
- [ ] Tedarikçinin KVKK Sorumlusu / DPO irtibatı kayıtlı mı?
- [ ] İhlal bildirim SLA (24 saat) sözleşmede yazılı mı?
- [ ] Yıllık SOC 2 / ISO 27001 raporları toplanıyor, gözden geçiriliyor mu?
- [ ] Sızma testi raporları yıllık alınıyor mu?
- [ ] Çeyreklik (Sınıf A) / yıllık (B/C) review yapılıyor mu, kayıt var mı?
- [ ] Bulut sağlayıcı listesi onaylı, BYOK politikası uygulanıyor mu?
- [ ] Çıkış sürecinde veri iade/imha tutanağı standart mı?
- [ ] Tedarikçi ihlali sonrası lessons learned kaydı tutuluyor mu?
- [ ] Tedarikçi kara listesi mekanizması tanımlı mı?
- [ ] Cyber liability sigortası talep ediliyor (Sınıf A/B)?
- [ ] Tedarikçi sözleşmesi devir, alt-yüklenici, fesih hükümleri net mi?
- [ ] VERBİS kaydı tedarikçi değişimleri ile güncel mi?

## 16. Yaygın Hatalar

- "Standart hizmet sözleşmesi" imzalanmış, KVKK / veri işleyen ek protokolü yok.
- Alt-işleyen listesi tutulmuyor; tedarikçi alt yüklenici değiştiriyor, biz haberdar değiliz.
- Cloud sağlayıcının "datasheet"ine güvenip kendi konfigürasyon sorumluluğumuzu fark etmemek.
- Yurt dışı aktarımın hukuki dayanağı belirsiz; m.9'a uygun mekanizma yok.
- Tedarikçi ayrıldıktan sonra erişim kapanmamış (eski kullanıcı hesabı aktif).
- Veri iade/imha tutanağı alınmamış; veri tedarikçinin tarafında yıllarca yatıyor.
- Sözleşmenin denetim hakkı maddesi soyut; pratik denetim yapılamıyor.
- Tedarikçi tarafında ihlal — bizim KVKK Kurulu'na 72 saat süresi azalıyor ama tedarikçi "araştırıyoruz" diye geciktiriyor.
