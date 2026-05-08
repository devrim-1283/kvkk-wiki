---
Doküman / Document: Kişisel Veri İşleme Envanteri (KVKİ) Hazırlama Rehberi / Personal Data Processing Inventory (KVKİ) Preparation Guide
Bölüm / Section: 02-envanter-ve-sicil
Sahip / Owner: KVKK Sorumlusu / KVKK Officer
Onaylayan / Approved by: Hukuk Müdürü + KVKK Komitesi / Head of Legal + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş (yeni süreç, yeni sistem, M&A, mevzuat değişikliği) / Annual + triggered (new process, new system, M&A, legislative change)
İlgili Mevzuat / Legal Reference: 6698 sayılı KVKK m.5, m.6, m.7, m.10, m.12, m.16 / Law No. 6698 (KVKK) Art. 5, 6, 7, 10, 12, 16; Veri Sorumluları Sicili Hakkında Yönetmelik MADDE 4(h), 5(ç), 5(d), 9 / Regulation on the Data Controllers' Registry Art. 4(h), 5(ç), 5(d), 9; Aydınlatma Tebliği MADDE 4-5 / Disclosure/Information Notice Communiqué Art. 4-5; Saklama ve İmha Yönetmeliği MADDE 5 / Regulation on the Erasure, Destruction and Anonymisation of Personal Data Art. 5
---

## English

# Personal Data Processing Inventory (KVKİ) Guide

## 1. Definition and Legal Basis

### 1.1 Definition

Article 4(1)(h) of the Regulation on the Data Controllers' Registry defines the Personal Data Processing Inventory (KVKİ — Kişisel Veri İşleme Envanteri) as follows:

> "The inventory in which data controllers detail the personal data processing activities they carry out in connection with their business processes, by associating those activities with the purposes of processing, the data category, the recipient group to which the data is transferred and the data subject group, and by setting out the maximum period required for the purposes for which the personal data is processed, the personal data envisaged to be transferred to foreign countries, and the measures taken regarding data security."

This definition produces, word by word, the mandatory columns of the inventory rows:

| Element of the definition | Corresponding inventory column |
|---------------------------|--------------------------------|
| business processes | Process name, business unit |
| purposes of processing | Processing purpose |
| data category | Data category (identity, contact, finance, etc.) |
| data subject group | Data subject group (employee, customer, visitor, etc.) |
| recipient group of transfer | Recipient/recipient group (domestic + cross-border) |
| maximum period | Retention period |
| transfer to foreign countries | Cross-border transfer column |
| security measures | Technical and administrative measures |

### 1.2 Legal Basis and Context

| Legal provision | Meaning |
|-----------------|---------|
| Reg. Art. 5(ç) | "Information disclosed to the Registry in registration applications is prepared **on the basis of** the Personal Data Processing Inventory." |
| Reg. Art. 5(d) | The Registry information based on the inventory is the basis for the disclosure obligation, data subject requests, and determining the scope of explicit consent. |
| Reg. Art. 9(2) | Information on purpose, category, person group, recipient and cross-border transfer disclosed to the Registry is communicated using VERBİS headings, on the basis of the inventory. |
| Reg. Art. 9(5) | The retention-and-destruction policy used to determine and track the maximum period is prepared **on the basis of** the inventory. |
| Erasure-Destruction Reg. Art. 5 | The retention-and-destruction policy is prepared **in accordance with the personal data processing inventory**. |

**Conclusion:** KVKİ is the operational core of the KVKK compliance framework. Disclosure (information notice), explicit consent, retention-destruction, transfer, and data subject responses are all fed by the inventory.

## 2. Inventory Content — Mandatory Fields

An inventory row represents one **process × one data subject group** combination. If the same process involves more than one person group (e.g., "candidate" + "reference provider" in recruitment), each combination becomes a separate row.

### 2.1 Minimum Column Set

| # | Column | Description |
|---|--------|-------------|
| 1 | Process ID | Unique identifier (e.g., HR-001, CUS-002) |
| 2 | Process name | Operational name (e.g., "Candidate Recruitment") |
| 3 | Business unit | Owning unit (e.g., "Human Resources") |
| 4 | Process owner | Name, title, e-mail |
| 5 | Data subject group | Employee, candidate, customer, prospect, supplier employee, visitor, child, etc. |
| 6 | Data category | Identity, Contact, Finance, Special-category (health, criminal record, etc.), Customer Transaction, Transaction Security, Location, Visual/Audio, Professional Experience, Legal Proceeding, Marketing, Risk Management |
| 7 | Personal data items | Detailed list: name-surname, T.R. ID number, date of birth, IBAN, IP address, medical report, etc. |
| 8 | Special category (Y/N) | Does it fall within KVKK Art. 6? |
| 9 | Processing purpose | Specific, explicit, legitimate purpose (KVKK Art. 4(2)/c). Multiple purposes are split or written together with care. |
| 10 | Legal ground | KVKK Art. 5(2)(a-f), Art. 6(2)-(3), or **Explicit Consent** (Art. 5(1) / Art. 6(2) first sentence) |
| 11 | Collection method | Automated / non-automated / mixed; channel: web form, paper application, mobile app, call center, partner, camera, etc. |
| 12 | Storage medium | Electronic (database, file server, e-mail, cloud), Physical (cabinet, archive), Mixed |
| 13 | Internal recipients | Which units it is shared with |
| 14 | Domestic recipient / recipient group | Authorised public bodies, business partners, suppliers, law firms, auditors, etc. |
| 15 | Cross-border transfer (Y/N) | Is there transfer? |
| 16 | Foreign recipient | Company name, country (e.g., Microsoft Azure, Ireland) |
| 17 | Legal basis for cross-border transfer | KVKK Art. 9: adequacy decision / standard contract / binding corporate rules / undertaking + Board permit / occasional cases / explicit consent |
| 18 | Retention period | Numerical (e.g., "10 years from the end of the employment relationship") |
| 19 | Retention rationale | Legislative reference (Turkish Code of Obligations (TBK), Turkish Commercial Code (TTK), Tax Procedure Law (VUK), Social Security Institution (SGK) Law, etc.) or business need + statute-of-limitations analysis |
| 20 | Destruction method | Erasure / Destruction / Anonymisation |
| 21 | Destruction period | Periodic destruction schedule (max. 6 months) |
| 22 | Technical measures | Encryption, access logs, MFA, network segmentation, penetration testing, etc. |
| 23 | Administrative measures | Training, confidentiality undertaking, access authorisation, contractual provisions, etc. |
| 24 | Risk level | Low / Medium / High / Critical (special category + large volume → high/critical) |
| 25 | Related information notice | Reference or link |
| 26 | Explicit consent required? | Y/N + rationale |
| 27 | Last update date + updater | Version tracking |

> Note: Per Reg. Art. 9(4), if a retention period is prescribed by law it is taken; otherwise the **longest** of the various periods is used.

### 2.2 Legal Ground Catalogue (KVKK Art. 5/Art. 6)

When writing an inventory row, **a single, explicit legal ground must be set per purpose**. Explicit consent is treated as a last resort; if any other legal ground exists, explicit consent is not taken.

**General personal data (KVKK Art. 5(2)):**
- (a) Expressly provided for in laws
- (b) Protection of a person who is unable to express consent due to actual impossibility
- (c) Directly related to the conclusion or performance of a contract
- (ç) Fulfilment of a legal obligation
- (d) Made public by the data subject themself
- (e) Establishment, exercise or protection of a right
- (f) Legitimate interest, provided that fundamental rights and freedoms are not harmed

**Special-category personal data (KVKK Art. 6(3)):**
- Health and sexual life → public health protection, preventive medicine, medical diagnosis, treatment and care, planning and management of health services and financing (by persons under a duty of confidentiality)
- Other special-category data → in cases provided for by law

## 3. Inventory Build Methodology

### 3.1 Five-Stage Approach

```
1. Process Discovery → 2. Data Flow Mapping → 3. Legal Analysis → 4. Validation → 5. Versioning
```

#### Stage 1 — Process Discovery

**Three parallel information channels:**

| Channel | Method | Output |
|---------|--------|--------|
| Interview | 60-90 min structured interview with unit managers | Process map draft |
| System scan | CMDB, AD, AWS/Azure inventory, SaaS console list | List of systems holding data |
| Survey | Structured form for process owners (Google Forms, MS Forms) | Standard answers per process |

**Sample interview questions:**
1. Which person groups' data do you process in your function?
2. Which systems are used (in-house, SaaS, outsourced)?
3. How is data collected (form, API, paper, voice recording, CCTV)?
4. With which other unit, public body, or supplier do you share data?
5. Do you have cross-border transfers? (If your SaaS servers are abroad, yes.)
6. How long do you retain the data, and why?
7. Have you previously experienced a data breach, loss, or unauthorised access?

#### Stage 2 — Data Flow Mapping

Produce a **data-flow diagram** per process:

```
[Collection Source] → [Active System(s)] → [Backup/Archive] → [Transfer Recipients] → [Destruction]
```

For each arrow: which data is moving, who has access, with which security measure.

#### Stage 3 — Legal Analysis

Together with the Legal Department for each process:
- Confirmation that purposes are specific, explicit, legitimate (KVKK Art. 4)
- Determination of the legal ground (Art. 5/Art. 6)
- Alignment of retention periods with legislation
- Determination of transfer regime (Art. 8/Art. 9)
- Assessment of explicit consent requirement

#### Stage 4 — Validation Workshop

Process owner + KVKK Officer + Information Security + Legal review draft inventory rows together. Typical workshop time: 30-45 min per process.

#### Stage 5 — Versioning

The inventory is kept in a version-controlled system (Git, OneDrive history, OneTrust audit trail). Last update date and updater are mandatory per row.

### 3.2 Workshop Output Template

```
Workshop:        [Process Name]
Date:            YYYY-MM-DD
Participants:    [Name, Role]
Decision:        [Approved / Revision required]
Open items:
  - [Legal ground confirmation needed]
  - [Awaiting Legal opinion on retention period]
Action list: ...
```

## 4. Typical Process List for Our Company

For a 500+ employee data controller, a minimum scope:

### 4.1 Human Resources

| ID | Process |
|----|---------|
| HR-001 | Candidate recruitment and CV management |
| HR-002 | Onboarding and personnel file creation |
| HR-003 | Payroll and salary payments |
| HR-004 | Performance evaluation |
| HR-005 | Training and development |
| HR-006 | Leave and attendance tracking |
| HR-007 | Occupational health and safety (medical reports, accidents) — special category |
| HR-008 | Discipline and ethics investigation |
| HR-009 | Exit and personnel archive |
| HR-010 | Employee references provided |

### 4.2 Customer and Sales

| ID | Process |
|----|---------|
| CUS-001 | Customer registration and account opening |
| CUS-002 | E-commerce order management |
| CUS-003 | Invoicing and collection |
| CUS-004 | Customer complaints and feedback |
| CUS-005 | Call center (voice recording) |
| CUS-006 | Marketing, campaign and newsletter (compliance with İYS — Message Management System) |
| CUS-007 | CRM and 360° customer profile |
| CUS-008 | Loyalty and rewards programme |

### 4.3 Operations and Logistics

| ID | Process |
|----|---------|
| OPR-001 | Supplier management (supplier employee data) |
| OPR-002 | Delivery and logistics (courier, recipient data) |
| OPR-003 | Procurement and contract management |

### 4.4 Information Technology and Security

| ID | Process |
|----|---------|
| IT-001 | Identity and access management (IAM/AD) |
| IT-002 | Logging and SIEM |
| IT-003 | Backup and disaster recovery |
| IT-004 | Cloud service providers (cross-border transfer) |
| IT-005 | Call center software integration |
| IT-006 | Cookies and digital tracking |

### 4.5 Physical Security and Administration

| ID | Process |
|----|---------|
| PHY-001 | CCTV (closed-circuit camera system) |
| PHY-002 | Visitor management (entry log, badge) |
| PHY-003 | Physical archive management |
| PHY-004 | Internal audit and compliance |

### 4.6 Legal and Compliance

| ID | Process |
|----|---------|
| LEG-001 | Legal disputes and litigation management |
| LEG-002 | Ethics hotline (whistleblowing) |
| LEG-003 | KVKK data subject request management |
| LEG-004 | Data breach management |

### 4.7 Finance

| ID | Process |
|----|---------|
| FIN-001 | Accounting and current accounts |
| FIN-002 | Tax declarations |
| FIN-003 | Banking and payment systems |

### 4.8 Marketing and Communication

| ID | Process |
|----|---------|
| MKT-001 | Website analytics and cookies |
| MKT-002 | Social media and campaign management |
| MKT-003 | İYS (Message Management System) — commercial electronic messages |

> A typical inventory for a 500+ employee organisation contains **80-150 rows**. A count below 50 indicates incomplete discovery.

## 5. Versioning, Ownership and Change Management

### 5.1 Version Numbering

Semantic versioning: `MAJOR.MINOR.PATCH`
- MAJOR: Architectural change (new column, new process family)
- MINOR: Addition of a new process row, meaningful revision of an existing row
- PATCH: Typo fixes, small updates

### 5.2 Dual Ownership Model

Two owners per row:
- **Process owner (business unit):** responsible for content accuracy
- **KVKK Officer:** responsible for legal compliance and VERBİS reflection

### 5.3 Change Triggers

| Trigger | Action |
|---------|--------|
| Launch of a new process | Inventory row before processing begins + VERBİS update |
| Onboarding of a new system/SaaS | Data flow, transfer, cross-border check; inventory update |
| New supplier (data processor) | Update transfer column + sign DPA |
| Legislative change | Re-evaluate legal ground and retention period for affected rows |
| Organisational change (merger, transfer, M&A) | Full inventory review |
| Data breach | Update measures column for the affected process |

> Reg. Art. 13: notification within **7 days** of any change in registered VERBİS information. Inventory updates are therefore not "end-of-month" work; they happen as soon as the process changes.

## 6. Tooling Recommendations

### 6.1 Excel/CSV (Entry level)

- **Pros:** Low cost, fast start, broad access.
- **Cons:** Weak version control, multi-user collisions, no automatic reminders.
- **Recommendation:** Single master copy on OneDrive/SharePoint, read-only sharing, pull-request style for changes.

### 6.2 KVKK / Privacy Software

| Tool | Suitability |
|------|-------------|
| OneTrust Data Mapping | Large enterprise, certification need |
| BigID | Sensitive data discovery + inventory |
| Local Turkish vendors (Lostar, KVKK Manager, etc.) | Local support, KVKK-aligned templates |
| Confluence + JIRA | Internal wiki + ticket integration (mid-scale) |

### 6.3 CMDB Integration

If IT keeps a CMDB system list, map the "storage medium" column of inventory rows to system IDs and set alerting when the system side changes.

## 7. Common Mistakes and Controls

| Mistake | Correction |
|---------|-----------|
| Legal ground written as "consent" although another ground exists | Explicit consent is last resort; pick the appropriate clause |
| Retention period written as "as needed" | Specific, numerical period + rationale required |
| Cross-border transfer column blank although SaaS is abroad | Verify SaaS server locations, clarify yes/no |
| "All employees access" | Role-based access on a need-to-know basis |
| Information notice misaligned with inventory | Quarterly alignment check is mandatory (see envanter-bakim.md) |
| Multiple purposes squeezed into one row | Recommended to split when legal grounds differ per purpose |
| Risk level not stated | Risk assessment required for all rows |

## 8. Inventory Maturity Model

| Level | Definition | Typical indicator |
|-------|------------|-------------------|
| 1 - Initial | Listed in Excel | 30+ rows but columns incomplete |
| 2 - Structured | All mandatory columns filled | VERBİS notification submitted |
| 3 - Operational | Quarterly review active | Process-owner-signed |
| 4 - Integrated | Disclosure + consent + retention text generated from inventory | Single source of truth |
| 5 - Optimised | Auto-link with CMDB/SaaS, real-time monitoring | Live data-flow map |

Target maturity: **Level 4 (Integrated)** within 18 months. Level 5 is optional.

## 9. Checklist (New Process)

- [ ] Process ID assigned (per internal naming convention)
- [ ] Process owner identified and accepted
- [ ] All 27 columns completed
- [ ] Legal ground selected from KVKK Art. 5/Art. 6 clauses
- [ ] Retention period justified by legislation or limitation analysis
- [ ] Domestic and cross-border recipients listed
- [ ] If cross-border, legal basis determined (Art. 9)
- [ ] Information notice prepared or linked to existing one
- [ ] If consent required, text and collection channel ready
- [ ] Technical and administrative measures filled in, confirmed by InfoSec
- [ ] Risk level set (special category + large volume → minimum high)
- [ ] VERBİS update planned (7 days)
- [ ] Aligned with retention-destruction policy
- [ ] Version number and updater logged

## 10. Annexes

- Template: [envanter-sablonu.md](./envanter-sablonu.md)
- VERBİS Registration: [verbis-kayit-rehberi.md](./verbis-kayit-rehberi.md)
- Exception Assessment: [verbis-istisna-degerlendirmesi.md](./verbis-istisna-degerlendirmesi.md)
- Maintenance: [envanter-bakim.md](./envanter-bakim.md)

---

## Türkçe

# Kişisel Veri İşleme Envanteri (KVKİ) Rehberi

## 1. Tanım ve Hukuki Dayanak

### 1.1 Tanım

Veri Sorumluları Sicili Hakkında Yönetmelik MADDE 4(1)(h)'de Kişisel Veri İşleme Envanteri şu şekilde tanımlanmıştır:

> "Veri sorumlularının iş süreçlerine bağlı olarak gerçekleştirmekte oldukları kişisel veri işleme faaliyetlerini; kişisel veri işleme amaçları, veri kategorisi, aktarılan alıcı grubu ve veri konusu kişi grubuyla ilişkilendirerek oluşturdukları ve kişisel verilerin işlendikleri amaçlar için gerekli olan azami süreyi, yabancı ülkelere aktarımı öngörülen kişisel verileri ve veri güvenliğine ilişkin alınan tedbirleri açıklayarak detaylandırdıkları envanteri" ifade eder.

Bu tanım kelime kelime envanter satırlarının zorunlu sütunlarını üretir:

| Tanım unsuru | Envanter sütununa karşılık |
|--------------|---------------------------|
| iş süreçleri | Süreç adı, iş birimi |
| kişisel veri işleme amaçları | İşleme amacı |
| veri kategorisi | Veri kategorisi (kimlik, iletişim, finans vb.) |
| veri konusu kişi grubu | Veri konusu kişi grubu (çalışan, müşteri, ziyaretçi vb.) |
| aktarılan alıcı grubu | Alıcı/alıcı grubu (yurt içi+yurt dışı) |
| azami süre | Saklama süresi |
| yabancı ülkelere aktarım | Yurt dışı aktarım kolonu |
| güvenlik tedbirleri | Teknik ve idari tedbirler |

### 1.2 Hukuki Dayanak ve Bağlam

| Mevzuat hükmü | Anlamı |
|---------------|--------|
| Yön. M.5(ç) | "Sicil başvurularında Sicile açıklanacak bilgiler Kişisel Veri İşleme Envanterine **dayalı olarak** hazırlanır." |
| Yön. M.5(d) | Aydınlatma yükümlülüğü, ilgili kişi başvuruları ve açık rızanın kapsamının belirlenmesinde **envantere dayalı** Sicil bilgileri esas alınır. |
| Yön. M.9(2) | Sicile açıklanacak amaç, kategori, kişi grubu, alıcı, yurt dışı aktarım bilgileri envantere dayalı olarak VERBİS başlıkları kullanılarak iletilir. |
| Yön. M.9(5) | Azami sürenin belirlenmesi ve takibi için saklama-imha politikası **envantere dayalı** olarak hazırlanır. |
| Saklama ve İmha Yön. M.5 | Saklama ve imha politikası **kişisel veri işleme envanterine uygun olarak** hazırlanır. |

**Sonuç:** KVKİ, KVKK uyum çatısının operasyonel kalbidir. Aydınlatma, açık rıza, saklama-imha, aktarım, ilgili kişi başvurusu cevabı — hepsi envanterden beslenir.

## 2. Envanter İçeriği — Zorunlu Alanlar

Bir envanter satırı **bir süreç × bir veri konusu kişi grubu** kombinasyonunu temsil eder. Aynı süreçte birden fazla kişi grubu varsa (örn. işe alım sürecinde "aday" + "referans veren"), her kombinasyon ayrı satır olur.

### 2.1 Asgari Kolon Seti

| # | Kolon | Açıklama |
|---|-------|----------|
| 1 | Süreç ID | Tekil tanımlayıcı (örn. IK-001, MUS-002) |
| 2 | Süreç adı | Operasyonel adı (örn. "Çalışan Adayı İşe Alım") |
| 3 | İş birimi | Süreç sahibi birim (örn. "İnsan Kaynakları") |
| 4 | Süreç sahibi | Adı, unvanı, e-postası |
| 5 | Veri konusu kişi grubu | Çalışan, çalışan adayı, müşteri, potansiyel müşteri, tedarikçi çalışanı, ziyaretçi, çocuk, vb. |
| 6 | Veri kategorisi | Kimlik, İletişim, Finans, Özel nitelikli (sağlık, ceza mahkumiyeti vb.), Müşteri işlem, İşlem güvenliği, Lokasyon, Görsel/işitsel, Mesleki deneyim, Hukuki işlem, Pazarlama, Risk yönetimi |
| 7 | Kişisel veri öğeleri | Detay liste: ad-soyad, T.C. kimlik, doğum tarihi, IBAN, IP adresi, sağlık raporu vb. |
| 8 | Özel nitelikli veri (E/H) | KVKK m.6 kapsamına giriyor mu? |
| 9 | İşleme amacı | Belirli, açık, meşru amaç (KVKK m.4(2)/c). Birden fazla amaç ayrı satıra bölünür ya da çoklu amaç olarak yazılır. |
| 10 | Hukuki sebep | KVKK m.5(2) bentleri (a-f), m.6(2)-(3) bentleri ya da **Açık Rıza** (m.5(1) / m.6(2) ilk cümle) |
| 11 | Toplama yöntemi | Otomatik / Otomatik olmayan / Karma; kanal: web formu, kağıt başvuru, mobil app, çağrı merkezi, iş ortağı, kamera vb. |
| 12 | Kayıt ortamı | Elektronik (veritabanı, dosya sunucusu, e-posta, bulut), Fiziksel (dolap, arşiv), Karma |
| 13 | Veri aktarımı yapılan iç birim | Hangi birimlerle paylaşılıyor |
| 14 | Yurt içi alıcı / alıcı grubu | Yetkili kamu kurumları, iş ortakları, tedarikçiler, hukuk büroları, denetçiler, vb. |
| 15 | Yurt dışı aktarım (E/H) | Aktarım var mı? |
| 16 | Yurt dışı alıcı | Şirket adı, ülke (örn. Microsoft Azure, İrlanda) |
| 17 | Yurt dışı aktarım hukuki temeli | KVKK m.9: Yeterlilik kararı / Standart sözleşme / Bağlayıcı şirket kuralları / Taahhütname + Kurul izni / Arızi haller / Açık rıza |
| 18 | Saklama süresi | Sayısal (örn. "İş ilişkisi sona ermesinden itibaren 10 yıl") |
| 19 | Saklama süresi gerekçesi | Mevzuat referansı (TBK, TTK, VUK, SGK Kanunu vb.) ya da iş ihtiyacı + zamanaşımı analizi |
| 20 | İmha yöntemi | Silme / Yok etme / Anonim hale getirme |
| 21 | İmha periyodu | Periyodik imha takvimi (azami 6 ay) |
| 22 | Teknik tedbirler | Şifreleme, erişim logu, MFA, ağ segmentasyonu, sızma testi, vb. |
| 23 | İdari tedbirler | Eğitim, gizlilik taahhütnamesi, erişim yetkilendirme, sözleşme hükümleri, vb. |
| 24 | Risk seviyesi | Düşük / Orta / Yüksek / Kritik (özel nitelikli + büyük hacim → yüksek/kritik) |
| 25 | İlgili aydınlatma metni | Atıf veya bağlantı |
| 26 | Açık rıza gerekli mi? | E/H + gerekçe |
| 27 | Son güncelleme tarihi + güncelleyen | Versiyon takibi |

> Not: Yön. M.9(4) gereği, mevzuatta bir saklama süresi öngörülmüş ise o süre, yoksa farklı sürelerden **en uzunu** esas alınır.

### 2.2 Hukuki Sebep Tabanı (KVKK m.5/m.6)

Envanter satırı yazılırken **her amaç için açık ve tek bir hukuki sebep** belirlenmelidir. Açık rıza son çare olarak değerlendirilir; başka bir hukuki sebep varsa açık rıza alınmaz.

**Genel kişisel veri (KVKK m.5/2):**
- a) Kanunlarda açıkça öngörülmesi
- b) Fiili imkansızlık nedeniyle rızasını açıklayamayacak kişinin korunması
- c) Sözleşmenin kurulması veya ifasıyla doğrudan ilgili olması
- ç) Hukuki yükümlülüğün yerine getirilmesi
- d) İlgili kişinin kendisi tarafından alenileştirilmiş olması
- e) Bir hakkın tesisi, kullanılması veya korunması
- f) Meşru menfaate dayalı, ilgili kişinin temel hak ve özgürlüklerine zarar vermemek kaydıyla

**Özel nitelikli kişisel veri (KVKK m.6/3):**
- Sağlık ve cinsel hayat → kamu sağlığının korunması, koruyucu hekimlik, tıbbi teşhis, tedavi ve bakım hizmetlerinin yürütülmesi, sağlık hizmetleri ile finansmanının planlanması ve yönetimi (sır saklama yükümlülüğü altındakiler)
- Diğer özel nitelikli veriler → kanunlarda öngörülen hallerde

## 3. Envanter Çıkarma Metodolojisi

### 3.1 Beş Aşamalı Yaklaşım

```
1. Süreç Keşfi  →  2. Veri Akışı Haritalama  →  3. Hukuki Analiz  →  4. Doğrulama  →  5. Versiyonlama
```

#### Aşama 1 — Süreç Keşfi

**Üç paralel kanaldan bilgi toplama:**

| Kanal | Yöntem | Çıktı |
|-------|--------|-------|
| Mülakat | Birim yöneticileri ile 60-90 dk yapılandırılmış mülakat | Süreç haritası taslağı |
| Sistem taraması | CMDB, AD, AWS/Azure inventory, SaaS console listesi | Veri tutan sistem listesi |
| Anket | Süreç sahiplerine yapılandırılmış form (Google Forms, MS Forms) | Süreç başına standart cevaplar |

**Mülakat soruları (örnek):**
1. Sürecinizde hangi kişi gruplarına ait veri işliyorsunuz?
2. Hangi sistemler kullanılıyor (in-house, SaaS, dış kaynak)?
3. Veri nasıl alınıyor (form, API, kağıt, ses kaydı, CCTV)?
4. Hangi verileri başka bir birim, kurum veya tedarikçi ile paylaşıyorsunuz?
5. Yurt dışına veri aktarımınız var mı? (SaaS sunucuları yurt dışındaysa evet)
6. Verileri ne kadar süre saklıyorsunuz? Neden?
7. Geçmişte yaşanan veri ihlali, kayıp veya yetkisiz erişim oldu mu?

#### Aşama 2 — Veri Akışı Haritalama

Süreç başına **veri akış diyagramı** çıkarın:

```
[Toplama Kaynağı] → [Aktif Sistem(ler)] → [Yedek/Arşiv] → [Aktarım Alıcıları] → [İmha]
```

Her ok için: hangi veriler hareket ediyor, kim erişiyor, hangi güvenlik tedbiriyle korunuyor.

#### Aşama 3 — Hukuki Analiz

Her süreç için Hukuk Müdürlüğü ile birlikte:
- Amaçların belirli, açık, meşru olduğunun teyidi (KVKK m.4)
- Hukuki sebebin tespiti (m.5/m.6)
- Saklama sürelerinin mevzuatla uyumlandırılması
- Aktarım rejiminin tespiti (m.8/m.9)
- Açık rıza gerekliliği değerlendirmesi

#### Aşama 4 — Doğrulama Atölyesi

Hazırlanan envanter satırlarını süreç sahibi + KVKK Sorumlusu + Bilgi Güvenliği + Hukuk birlikte gözden geçirir. Tipik atölye süresi: süreç başına 30-45 dk.

#### Aşama 5 — Versiyonlama

Envanter, sürüm kontrollü bir sistemde tutulur (Git, OneDrive sürüm geçmişi, OneTrust kayıt geçmişi). Her satır için son güncelleme tarihi ve güncelleyen kişi zorunludur.

### 3.2 Atölye Çalışması Çıktı Şablonu

```
Atölye: [Süreç Adı]
Tarih: YYYY-AA-GG
Katılımcılar: [İsim, Rol]
Karar: [Onaylandı / Revizyon gerekli]
Açık konular:
  - [Hukuki sebebin teyidi gerekiyor]
  - [Saklama süresi için Hukuk görüşü beklenecek]
Aksiyon listesi: ...
```

## 4. Şirketimiz İçin Tipik Süreç Listesi

500+ çalışanlı bir veri sorumlusu için minimum kapsam:

### 4.1 İnsan Kaynakları

| ID | Süreç |
|----|-------|
| IK-001 | Çalışan adayı işe alım ve özgeçmiş yönetimi |
| IK-002 | İşe başlatma ve özlük dosyası oluşturma |
| IK-003 | Bordro ve maaş ödemeleri |
| IK-004 | Performans değerlendirme |
| IK-005 | Eğitim ve gelişim |
| IK-006 | İzin ve devam-devamsızlık takibi |
| IK-007 | İş sağlığı ve güvenliği (sağlık raporları, kazalar) — özel nitelikli |
| IK-008 | Disiplin ve etik soruşturma |
| IK-009 | İşten çıkış ve özlük arşivi |
| IK-010 | Çalışan referans verme |

### 4.2 Müşteri ve Satış

| ID | Süreç |
|----|-------|
| MUS-001 | Müşteri kayıt ve hesap açılışı |
| MUS-002 | E-ticaret sipariş yönetimi |
| MUS-003 | Faturalama ve tahsilat |
| MUS-004 | Müşteri şikayet ve geri bildirim |
| MUS-005 | Çağrı merkezi (sesli kayıt) |
| MUS-006 | Pazarlama, kampanya ve newsletter (İYS uyumu) |
| MUS-007 | CRM ve müşteri 360° profili |
| MUS-008 | Sadakat ve puan programı |

### 4.3 Operasyon ve Lojistik

| ID | Süreç |
|----|-------|
| OPR-001 | Tedarikçi yönetimi (tedarikçi çalışanı verisi) |
| OPR-002 | Teslimat ve lojistik (kurye, alıcı verisi) |
| OPR-003 | Satınalma ve sözleşme yönetimi |

### 4.4 Bilgi Teknolojileri ve Güvenlik

| ID | Süreç |
|----|-------|
| BT-001 | Kullanıcı kimlik ve erişim yönetimi (IAM/AD) |
| BT-002 | Loglama ve SIEM |
| BT-003 | Yedekleme ve felaket kurtarma |
| BT-004 | Bulut hizmet sağlayıcıları (yurt dışı aktarım) |
| BT-005 | Çağrı merkezi yazılım entegrasyonu |
| BT-006 | Çerez ve dijital takip |

### 4.5 Fiziksel Güvenlik ve İdari

| ID | Süreç |
|----|-------|
| FIZ-001 | CCTV (kapalı devre kamera sistemi) |
| FIZ-002 | Ziyaretçi yönetimi (giriş kaydı, kart) |
| FIZ-003 | Fiziksel arşiv yönetimi |
| FIZ-004 | İç denetim ve uyum |

### 4.6 Hukuk ve Uyum

| ID | Süreç |
|----|-------|
| HUK-001 | Hukuki uyuşmazlık ve dava yönetimi |
| HUK-002 | Etik ihbar hattı (whistleblowing) |
| HUK-003 | KVKK ilgili kişi başvuru yönetimi |
| HUK-004 | Veri ihlali yönetimi |

### 4.7 Finans

| ID | Süreç |
|----|-------|
| FIN-001 | Muhasebe ve cari hesap |
| FIN-002 | Vergi beyanı |
| FIN-003 | Banka ve ödeme sistemleri |

### 4.8 Pazarlama ve İletişim

| ID | Süreç |
|----|-------|
| PAZ-001 | Web sitesi analitiği ve çerezler |
| PAZ-002 | Sosyal medya ve kampanya yönetimi |
| PAZ-003 | İYS (İleti Yönetim Sistemi) ticari elektronik ileti |

> 500+ çalışanlı bir kuruluş için tipik envanter satır sayısı **80-150 arasıdır**. 50'nin altı çıkıyorsa keşif eksik kalmıştır.

## 5. Versiyonlama, Sahiplik ve Değişiklik Yönetimi

### 5.1 Versiyon Numaralandırması

Semantik sürüm: `MAJOR.MINOR.PATCH`
- MAJOR: Mimari değişim (yeni kolon, yeni süreç ailesi)
- MINOR: Yeni süreç satırı eklenmesi, mevcut satırın anlamlı revizyonu
- PATCH: Yazım düzeltmeleri, küçük güncellemeler

### 5.2 Çift Sahiplik Modeli

Her satır için iki sahiplik:
- **Süreç sahibi (iş birimi):** içerik doğruluğundan sorumlu
- **KVKK Sorumlusu:** hukuki uyum ve VERBİS yansımasından sorumlu

### 5.3 Değişiklik Tetikleyicileri

| Tetikleyici | Aksiyon |
|-------------|---------|
| Yeni süreç başlatılması | Süreç başlamadan önce envanter satırı + VERBİS güncelleme |
| Yeni sistem/SaaS devreye alınması | Veri akışı, aktarım, yurt dışı kontrolü; envanter güncelleme |
| Yeni tedarikçi (veri işleyen) | Aktarım kolonu güncelleme + sözleşme |
| Mevzuat değişikliği | İlgili satırlarda hukuki sebep ve saklama süresinin yeniden değerlendirilmesi |
| Organizasyonel değişim (birleşme, devir, M&A) | Tüm envanterin gözden geçirilmesi |
| Veri ihlali | Etkilenen sürecin tedbirler kolonunun güncellenmesi |

> Yön. M.13: VERBİS'te kayıtlı bilgilerde değişiklik halinde **7 gün** içinde bildirim. Bu nedenle envanter güncellemeleri "ay sonu işi" değildir; süreç değiştiğinde anlık güncellenmelidir.

## 6. Araç Önerisi

### 6.1 Excel/CSV (Başlangıç düzeyi)

- **Artıları:** Düşük maliyet, hızlı başlangıç, geniş erişim.
- **Eksileri:** Sürüm kontrolü zayıf, çok kullanıcılı çalışmada çakışma, otomatik hatırlatıcı yok.
- **Öneri:** OneDrive/SharePoint üzerinde tek master kopya, salt okunur paylaşım, değişiklik için pull request mantığı.

### 6.2 KVKK/Privacy Yazılımları

| Araç | Uygunluk |
|------|---------|
| OneTrust Data Mapping | Büyük kurum, sertifikasyon ihtiyacı |
| BigID | Hassas veri keşfi + envanter |
| Yerel Türk yazılımları (Lostar, KVKK Manager vb.) | Yerel destek, KVKK uyumlu şablon |
| Confluence + JIRA | İç wiki + ticket entegrasyonu (orta ölçek) |

### 6.3 CMDB Entegrasyonu

Bilgi İşlem'in CMDB'sinde sistem listesi varsa, envanter satırlarındaki "kayıt ortamı" kolonunu sistem ID'leriyle eşlemek; sistem tarafında değişiklik olduğunda uyarı kuralı kurmak.

## 7. Yaygın Hatalar ve Kontroller

| Hata | Düzeltme |
|------|----------|
| Hukuki sebep "rıza" yazılmış ancak başka hukuki sebep mevcut | Açık rıza son çaredir; uygun bent seçilir |
| Saklama süresi "ihtiyaç oldukça" yazılmış | Belirli, sayısal süre + gerekçe zorunlu |
| Yurt dışı aktarım kolonu boş, ancak SaaS yurt dışı | SaaS sunucu lokasyonları kontrol edilir, evet/hayır netleştirilir |
| "Tüm çalışanlar erişiyor" | Erişim yetkilendirmesi rol bazlı yapılır, prensip "need to know" |
| Aydınlatma metni envanter ile uyumsuz | Çeyreklik uyum kontrolü zorunlu (bkz. envanter-bakim.md) |
| Birden fazla amaç tek satıra sıkıştırılmış | Her amaç için hukuki sebep farklı olabileceğinden ayrı satır önerilir |
| Risk seviyesi belirtilmemiş | Tüm satırlar için risk değerlendirmesi zorunlu |

## 8. Envanter Olgunluk Modeli

| Seviye | Tanım | Tipik gösterge |
|--------|-------|----------------|
| 1 - Başlangıç | Excel'de listeleme | 30+ satır, ancak kolonlar eksik |
| 2 - Yapılandırılmış | Tüm zorunlu kolonlar dolu | VERBİS bildirimi yapılmış |
| 3 - Operasyonel | Çeyreklik gözden geçirme aktif | Süreç sahibi imzalı |
| 4 - Entegre | Aydınlatma + rıza + saklama metni envanterden üretiliyor | Tek kaynak doğruluk |
| 5 - Optimize | CMDB/SaaS ile otomatik bağ, gerçek zamanlı izleme | Veri akışı haritası canlı |

Hedef olgunluk seviyesi: **4 (Entegre)** içinde 18 ay. Seviye 5 isteğe bağlıdır.

## 9. Kontrol Listesi (Yeni Süreç)

- [ ] Süreç ID atandı (şirket içi naming convention)
- [ ] Süreç sahibi belirlendi ve onayladı
- [ ] Tüm 27 kolon dolduruldu
- [ ] Hukuki sebep KVKK m.5/m.6 bentlerinden seçildi
- [ ] Saklama süresi mevzuat veya zamanaşımı analiziyle gerekçelendirildi
- [ ] Yurt içi ve yurt dışı alıcılar listelendi
- [ ] Yurt dışı varsa hukuki temel belirlendi (m.9)
- [ ] Aydınlatma metni hazırlandı veya mevcut metne bağlantı verildi
- [ ] Açık rıza gerekiyorsa metni ve toplama kanalı hazır
- [ ] Teknik ve idari tedbirler doldurmuş, Bilgi Güvenliği teyit etti
- [ ] Risk seviyesi belirlendi (özel nitelikli + büyük hacim → minimum yüksek)
- [ ] VERBİS güncelleme planlandı (7 gün)
- [ ] Saklama-imha politikası ile uyumlu
- [ ] Versiyon numarası ve güncelleyen kayda geçti

## 10. Ekler

- Şablon: [envanter-sablonu.md](./envanter-sablonu.md)
- VERBİS Kayıt: [verbis-kayit-rehberi.md](./verbis-kayit-rehberi.md)
- İstisna Değerlendirme: [verbis-istisna-degerlendirmesi.md](./verbis-istisna-degerlendirmesi.md)
- Bakım: [envanter-bakim.md](./envanter-bakim.md)
