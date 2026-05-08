---
title:
  en: "Vendor Management - Article 28 DPA, Sub-processors, Due Diligence, Full Template"
  tr: "Tedarikçi Yönetimi - Madde 28 DPA, Alt-İşleyiciler, Durum Tespiti, Tam Şablon"
section: "06-organizational-measures"
document_type: "policy_template"
control_id: "ORG-VEN-01"
owner:
  primary: "DPO"
  secondary: "CISO, Head of Procurement, General Counsel"
review_cycle: "annual"
last_review: "2026-05-08"
next_review: "2027-05-08"
classification: "Internal"
language: ["en", "tr"]
references:
  - "GDPR Art. 24, 28, 29, 32, 44-49, Recitals 81, 108"
  - "EDPB Recommendations 01/2020 on supplementary measures (post-Schrems II)"
  - "European Commission SCCs Decision (EU) 2021/914"
  - "ISO/IEC 27002:2022 controls 5.19, 5.20, 5.21, 5.22, 5.23"
  - "ISO/IEC 27036 series (supplier relationships)"
  - "ISO/IEC 27701:2019, ISO/IEC 27018:2019"
  - "NIST CSF 2.0 GV.SC"
---

## English

# Vendor and Processor Management

## 1. Purpose

GDPR Article 28(1) requires the controller to use only processors that
provide "sufficient guarantees to implement appropriate technical and
organisational measures" so that processing meets GDPR requirements and
ensures the protection of data subject rights. Article 28(3) requires a
written contract or other binding act with prescribed mandatory clauses.
This document codifies the lifecycle, due diligence and contractual baseline,
and provides a full DPA template aligned to EU practice.

## 2. Vendor Classification

| Tier | Trigger | Examples |
|------|---------|----------|
| V1 - Critical | Hosts, processes or has continuous access to large-scale or special-category personal data; failure has high impact | Cloud IaaS / PaaS, payroll provider, customer support platform, payment processor |
| V2 - High | Processes personal data; some failure resilience exists | Email security, CRM, analytics with PII |
| V3 - Standard | Limited or sampled personal data | Productivity SaaS, office tools |
| V4 - Low | No personal data, minimal access | Office supplies, facilities |

Tier determines the depth of due diligence and ongoing oversight.

## 3. Lifecycle

### 3.1 Sourcing
- Business case includes data processing assessment.
- ROPA pre-entry sketch.
- Initial DPIA scoping (`dpia.md`).
- Vendor longlist and evaluation criteria.

### 3.2 Due Diligence
- Security questionnaire (CAIQ, SIG, or internal equivalent).
- Certifications - ISO/IEC 27001 (mandatory for V1-V2), ISO/IEC 27701, ISO/IEC
  27018 for cloud, SOC 2 Type II, PCI DSS where applicable, ISO 22301.
- Penetration test summary (last 12 months).
- Bug bounty / responsible disclosure programme.
- Architecture and data flow diagrams.
- Sub-processor list with locations.
- Data location and transfer mechanism (`07-international-transfers/`).
- Insurance evidence (cyber, professional liability).
- Financial stability where engagement is critical.
- Reference checks for V1 / V2.
- Privacy track record (regulator decisions, public incidents).

### 3.3 Contracting
- Master agreement.
- Data Processing Addendum (Section 6 template) with mandatory Article 28
  clauses.
- Standard Contractual Clauses (Decision 2021/914) for transfers to
  inadequate countries; Transfer Impact Assessment performed and stored.
- Information security schedule.
- SLA and service credits.
- Exit and transition plan.

### 3.4 Onboarding
- Provision identities with least privilege (`05-technical-measures/access-control.md`).
- Vendor workforce training acknowledgement (`training.md`).
- Network and system integration security review.
- Add to ROPA (`02-ropa/`).

### 3.5 Operation
- Continuous monitoring - security ratings (BitSight, SecurityScorecard or
  equivalent) for V1-V2.
- SLA review monthly for V1, quarterly for V2, annually for V3.
- Incident reporting per DPA.
- Sub-processor change notifications.
- Periodic DPIA refresh on material change.
- Annual or risk-based on-site or virtual audit right exercised for V1.

### 3.6 Renewal
- Re-execute due diligence at renewal.
- Update DPA with current SCC version, Schrems II supplementary measures
  status, and current sub-processor list.

### 3.7 Exit
- Triggered by decision to terminate, vendor failure, or end of contract.
- Data return in agreed format and timeline.
- Certified destruction of vendor copies (`05-technical-measures/backup-recovery.md`
  Section 9).
- Access decommissioned.
- Documentation update; record retained.

## 4. Continuous Oversight

| Control | V1 | V2 | V3 | V4 |
|---------|----|----|----|----|
| Annual DPA refresh | Yes | Yes | Yes | If applicable |
| Security ratings monitoring | Daily | Weekly | Monthly | Optional |
| Sub-processor approval | Strict | Strict | Notice | n/a |
| Pen test review | Annual | Annual | Optional | n/a |
| Audit right | Yes (annual) | Yes (every 2 years or on cause) | On cause | n/a |
| Tabletop participation | Yes | Optional | n/a | n/a |
| Exit drill | Yes (every 2 years) | Optional | n/a | n/a |

## 5. Sub-processor Regime

- The DPA distinguishes between general written authorisation (with notice
  and objection right) and specific written authorisation.
- A sub-processor list is published to the controller with locations and
  purposes.
- Notice period for new or replaced sub-processors is at least 30 days
  (V1 / V2) or 60 days for high-risk additions.
- The controller may object on reasonable grounds; objection process
  defined in the DPA.
- Sub-processors bound back-to-back with the same data protection
  obligations as the processor.
- Onward transfer chain documented for Schrems II compliance.

## 6. Full Data Processing Addendum (DPA) Template

The following template is suitable for an EU-based controller engaging an
EU or non-EU processor. Drafting notes are bracketed `[ ]`.

```
DATA PROCESSING ADDENDUM (DPA)

This Data Processing Addendum ("DPA") is entered into between:

CONTROLLER: [Legal Name], registered address [address], legal entity
identifier [LEI / company number]

PROCESSOR: [Legal Name], registered address [address], legal entity
identifier [LEI / company number]

(each a "Party" and together the "Parties")

This DPA is incorporated into and forms part of the [Master Services
Agreement / Services Agreement] dated [date] (the "Principal Agreement").
In the event of conflict between this DPA and the Principal Agreement, this
DPA prevails on matters of personal data protection.

1. DEFINITIONS
   1.1 Terms in capitals not defined herein have the meaning given in
       Regulation (EU) 2016/679 ("GDPR").
   1.2 "Affiliate" means an entity Controlling, Controlled by, or under
       common Control with a Party.
   1.3 "Sub-processor" means any third party engaged by the Processor to
       process Personal Data on behalf of the Controller.
   1.4 "Standard Contractual Clauses" or "SCCs" means the Module 2 (or
       Module 3 where the Controller is itself a processor) of the Annex
       to Commission Implementing Decision (EU) 2021/914.
   1.5 "Personal Data Breach" has the meaning given in Article 4(12) GDPR.
   1.6 "Schedule" means a schedule attached to this DPA.

2. SCOPE AND ROLES
   2.1 The Processor processes Personal Data on behalf of the Controller in
       order to perform the services described in the Principal Agreement.
   2.2 The Parties are respectively the Controller and the Processor in
       the meaning of Article 4 GDPR. The Controller acknowledges that any
       Affiliate of the Controller using the services on its account
       authorises the Controller to enter into this DPA on its behalf.

3. SUBJECT-MATTER, DURATION, NATURE, PURPOSE, CATEGORIES (Art. 28(3))
   3.1 The subject-matter, duration, nature and purpose of processing,
       categories of Personal Data and categories of Data Subjects are
       set out in Schedule 1 (Processing Description).

4. PROCESSOR OBLIGATIONS
   4.1 The Processor shall process Personal Data only on documented
       instructions from the Controller, including with regard to
       transfers, unless required to do so by Union or Member State law;
       in such a case, the Processor shall inform the Controller of that
       legal requirement before processing, unless that law prohibits
       such information on important grounds of public interest.
   4.2 The Processor shall ensure that persons authorised to process the
       Personal Data have committed themselves to confidentiality or are
       under an appropriate statutory obligation of confidentiality.
   4.3 The Processor shall take all measures required pursuant to
       Article 32 GDPR. The technical and organisational measures are
       set out in Schedule 2 (TOMs). The Processor may update its TOMs
       at any time, provided the level of protection is not reduced.
   4.4 The Processor shall not engage another processor (Sub-processor)
       without prior specific or general written authorisation as set
       out in clause 7.
   4.5 The Processor shall, taking into account the nature of the
       processing, assist the Controller by appropriate technical and
       organisational measures, insofar as this is possible, for the
       fulfilment of the Controller's obligation to respond to requests
       for exercising data subject rights under Articles 12-22 GDPR.
   4.6 The Processor shall assist the Controller in ensuring compliance
       with the obligations pursuant to Articles 32 to 36 GDPR taking
       into account the nature of processing and the information
       available to the Processor.
   4.7 At the choice of the Controller, the Processor shall delete or
       return all the Personal Data to the Controller after the end of
       the provision of services relating to processing, and delete
       existing copies unless Union or Member State law requires storage
       of the Personal Data.
   4.8 The Processor shall make available to the Controller all
       information necessary to demonstrate compliance with the
       obligations laid down in Article 28 GDPR and allow for and
       contribute to audits, including inspections, conducted by the
       Controller or another auditor mandated by the Controller, as
       further set out in clause 9.
   4.9 The Processor shall immediately inform the Controller if, in its
       opinion, an instruction infringes the GDPR or other Union or
       Member State data protection provisions.

5. CONTROLLER OBLIGATIONS
   5.1 The Controller is responsible for the lawfulness of the
       processing it requires the Processor to perform, including
       providing all required information to data subjects and
       maintaining a valid lawful basis under Article 6 GDPR (and where
       relevant Article 9 / 10 GDPR).
   5.2 The Controller shall provide instructions in a way capable of
       being recorded.
   5.3 The Controller may issue further written instructions during
       the term of this DPA. The Processor may charge a reasonable fee
       for instructions outside the standard service scope.

6. SECURITY OF PROCESSING (Art. 32)
   6.1 The Processor implements the technical and organisational
       measures set out in Schedule 2 to ensure a level of security
       appropriate to the risk, taking into account the state of the
       art, costs of implementation, and the nature, scope, context and
       purposes of processing.
   6.2 The Processor regularly tests, assesses and evaluates the
       effectiveness of those measures and produces evidence on
       request.

7. SUB-PROCESSORS (Art. 28(2), (4))
   7.1 The Controller hereby grants the Processor general written
       authorisation to engage Sub-processors. The current list of
       Sub-processors is set out in Schedule 3.
   7.2 The Processor shall inform the Controller of any intended
       changes concerning the addition or replacement of Sub-processors
       at least thirty (30) days in advance, giving the Controller the
       opportunity to object on reasonable grounds related to data
       protection.
   7.3 If the Controller objects, the Parties shall negotiate in good
       faith. If no agreement is reached within thirty (30) days, the
       Controller may terminate the affected services without penalty,
       and the Processor shall provide reasonable transition assistance.
   7.4 The Processor shall impose on each Sub-processor data protection
       obligations no less protective than those in this DPA, including
       in respect of confidentiality, security and audit.
   7.5 The Processor remains fully liable to the Controller for the
       performance of the Sub-processor's obligations.

8. INTERNATIONAL TRANSFERS (Art. 44-49)
   8.1 The Processor shall not transfer Personal Data outside the EEA
       except in accordance with this clause and Schedule 4.
   8.2 Where the Processor or a Sub-processor is established in a third
       country not benefiting from a Commission adequacy decision, the
       Parties incorporate the Standard Contractual Clauses (Decision
       2021/914) Module 2 (controller-to-processor) or Module 3
       (processor-to-processor) as applicable, with options selected and
       annexes completed in Schedule 4.
   8.3 The Processor confirms that, prior to such transfer, it has
       conducted a Transfer Impact Assessment ("TIA") and adopted any
       supplementary technical, contractual and organisational measures
       necessary to ensure an essentially equivalent level of protection
       as required by EDPB Recommendations 01/2020. A summary of the TIA
       and the supplementary measures is provided in Schedule 4.
   8.4 The Processor shall promptly inform the Controller if it becomes
       unable to comply with its obligations under the SCCs, including
       in case of binding requests for disclosure of Personal Data
       received from public authorities of the third country, and
       challenge such requests where lawful and meaningful.

9. AUDIT RIGHT (Art. 28(3)(h))
   9.1 The Controller may conduct audits, including inspections, of the
       Processor's compliance with this DPA at the Controller's expense
       (unless the audit reveals material non-compliance, in which case
       the Processor bears the cost). Audits shall be:
       (a) on at least thirty (30) days' written notice (immediate notice
           in case of incident);
       (b) during normal business hours;
       (c) limited to relevant facilities, systems and records;
       (d) conducted in a manner that does not unreasonably disrupt the
           Processor's operations.
   9.2 The Processor may satisfy the audit obligation by providing
       up-to-date independent third-party certifications (ISO 27001, ISO
       27701, ISO 27018 for cloud, SOC 2 Type II, PCI DSS) and the most
       recent penetration test summary, except in case of:
       (a) a confirmed Personal Data Breach affecting the Controller;
       (b) instruction from a competent supervisory authority;
       (c) reasonable suspicion of material non-compliance.
       In any of those cases, an on-site or virtual audit may be
       performed.
   9.3 Auditors shall be subject to confidentiality obligations.

10. PERSONAL DATA BREACHES (Art. 33)
    10.1 The Processor shall notify the Controller of a Personal Data
         Breach without undue delay and in any event within seventy-two
         (72) hours of becoming aware. The notification shall include the
         information required under Article 33(3) GDPR to the extent
         known, and shall be supplemented as further information becomes
         available.
    10.2 The Processor shall reasonably cooperate with the Controller in
         investigation, mitigation and notification to supervisory
         authorities and data subjects, and shall not make any public
         statement about the incident concerning the Controller's data
         without the Controller's prior written consent (unless required
         by law).
    10.3 The Processor shall maintain a register of breaches affecting
         the Controller's Personal Data and provide entries on request.

11. DATA SUBJECT REQUESTS (Art. 12-22)
    11.1 The Processor shall, taking into account the nature of the
         processing, by appropriate technical and organisational
         measures, assist the Controller in responding to requests from
         data subjects exercising rights under Articles 15 to 22 GDPR.
    11.2 The Processor shall not respond directly to data subjects
         except as instructed by the Controller or required by law, and
         shall promptly forward any such requests received to the
         Controller.

12. RECORDS OF PROCESSING (Art. 30(2))
    12.1 The Processor maintains records of all categories of processing
         activities carried out on behalf of the Controller and provides
         them on request.

13. RETURN AND DELETION
    13.1 At the choice of the Controller, on termination of the
         provision of services, the Processor shall delete or return all
         Personal Data to the Controller and delete existing copies
         unless Union or Member State law requires storage. The
         Processor shall provide written confirmation of deletion within
         thirty (30) days of completion.

14. LIABILITY
    14.1 Liability under this DPA is governed by the Principal
         Agreement, save that nothing in this DPA limits any right or
         remedy of a data subject under Article 82 GDPR.

15. TERM
    15.1 This DPA is effective from the Effective Date of the Principal
         Agreement and remains in force for as long as the Processor
         processes Personal Data on behalf of the Controller, plus any
         period required by clause 13.

16. GOVERNING LAW
    16.1 This DPA is governed by the law of the Principal Agreement,
         except that the SCCs incorporated in clause 8 are governed in
         accordance with their own terms.

17. SCHEDULES
    Schedule 1 - Processing Description (Art. 28(3))
    Schedule 2 - Technical and Organisational Measures (Art. 32)
    Schedule 3 - List of Sub-processors
    Schedule 4 - International Transfers and SCCs

Signed for and on behalf of the Controller:
   Name:     Role:     Signature:     Date:

Signed for and on behalf of the Processor:
   Name:     Role:     Signature:     Date:
```

### Schedule 1 - Processing Description (skeleton)

- Subject-matter of processing
- Duration of processing
- Nature and purpose of processing
- Type of personal data
- Categories of data subjects
- Frequency of transfer (continuous / on demand)
- Retention period

### Schedule 2 - TOMs (skeleton, mapped to `05-technical-measures/`)

- Pseudonymisation and encryption
- Confidentiality, integrity, availability, resilience
- Restoration and recovery
- Regular testing
- Access control
- Logging and monitoring
- Incident response
- Vulnerability management
- Personnel
- Physical security

### Schedule 3 - Sub-processors

| Name | Service | Location | Date Added |
|------|---------|----------|------------|

### Schedule 4 - International Transfers

- Transfer mechanism (adequacy / SCC module / BCR / Article 49 derogation).
- SCC parameters (docking, dispute resolution, governing law, audit clause).
- TIA summary, supplementary measures.

## 7. Drafting Guidance

- Use Module 2 SCCs for controller-to-processor transfers; Module 3 if the
  controller is itself a processor.
- Include the Article 28(9) processor-to-sub-processor obligations in the
  back-to-back agreement.
- Where the processor is established in the UK / Switzerland, add the UK
  IDTA / Swiss FDPIC adaptations.
- Where the data is special-category (Article 9) or relates to children,
  document additional safeguards in Schedule 2.
- Coordinate with `07-international-transfers/` for jurisdiction-specific
  considerations.

## 8. KPIs

| Metric | Target |
|--------|--------|
| V1 / V2 vendors with current DPA | 100 % |
| Sub-processor list current | 100 % |
| TIA performed for non-adequacy transfers | 100 % |
| Vendor incident notifications within DPA SLA | 100 % |
| Audit right exercises completed per plan | 100 % |
| Vendor exits with certified destruction | 100 % |

## 9. Mapping

| Requirement | GDPR | ISO 27002:2022 | NIST CSF 2.0 |
|-------------|------|----------------|--------------|
| Supplier relationships | Art. 28 | 5.19 | GV.SC-1 |
| Information security in supplier relationships | Art. 28 | 5.19 | GV.SC-3 |
| Addressing security in agreements | Art. 28(3) | 5.20 | GV.SC-4 |
| Managing ICT supply chain | Art. 28 | 5.21 | GV.SC-5 |
| Monitoring of supplier services | Art. 28 | 5.22 | GV.SC-7 |
| Information security for cloud services | Art. 28 | 5.23 | GV.SC-1 |

---

## Türkçe

# Tedarikçi ve İşleyici Yönetimi

## 1. Amaç

GDPR Madde 28(1), kontrolörün yalnızca işlemenin GDPR gereksinimlerini
karşılaması ve veri sahibi haklarının korunmasını sağlaması için "uygun
teknik ve organizasyonel tedbirleri uygulamak için yeterli garantiler"
sağlayan işleyicileri kullanmasını gerektirir. Madde 28(3), öngörülen zorunlu
maddelerle yazılı bir sözleşme veya başka bağlayıcı bir işlem gerektirir. Bu
belge yaşam döngüsünü, durum tespitini ve sözleşmesel temel düzeyini kodlar
ve AB uygulamasıyla hizalı tam bir DPA şablonu sağlar.

## 2. Tedarikçi Sınıflandırması

| Katman | Tetikleyici | Örnekler |
|--------|-------------|----------|
| V1 - Kritik | Büyük ölçekli veya özel-nitelikli kişisel veriyi barındırır, işler veya sürekli erişimi vardır; başarısızlığın yüksek etkisi vardır | Bulut IaaS / PaaS, bordro sağlayıcısı, müşteri destek platformu, ödeme işleyicisi |
| V2 - Yüksek | Kişisel veri işler; bir miktar başarısızlık dayanıklılığı vardır | E-posta güvenliği, CRM, PII'li analitik |
| V3 - Standart | Sınırlı veya örneklenmiş kişisel veri | Üretkenlik SaaS, ofis araçları |
| V4 - Düşük | Kişisel veri yok, asgari erişim | Ofis malzemeleri, tesisler |

Katman, durum tespitinin derinliğini ve sürekli denetimi belirler.

## 3. Yaşam Döngüsü

### 3.1 Kaynak Bulma
- İş gerekçesi veri işleme değerlendirmesini içerir.
- ROPA ön giriş taslağı.
- İlk VKD kapsam belirleme (`dpia.md`).
- Tedarikçi uzun listesi ve değerlendirme kriterleri.

### 3.2 Durum Tespiti
- Güvenlik anketi (CAIQ, SIG veya dahili eşdeğer).
- Sertifikasyonlar - ISO/IEC 27001 (V1-V2 için zorunlu), ISO/IEC 27701,
  bulut için ISO/IEC 27018, SOC 2 Type II, geçerli olduğunda PCI DSS, ISO
  22301.
- Sızma testi özeti (son 12 ay).
- Bug bounty / sorumlu açıklama programı.
- Mimari ve veri akış diyagramları.
- Konumlarla alt-işleyici listesi.
- Veri konumu ve aktarım mekanizması (`07-international-transfers/`).
- Sigorta kanıtı (siber, mesleki sorumluluk).
- Görev kritikse finansal istikrar.
- V1 / V2 için referans kontrolleri.
- Gizlilik geçmişi (düzenleyici kararları, kamu olayları).

### 3.3 Sözleşme
- Ana sözleşme.
- Zorunlu Madde 28 maddeleriyle Veri İşleme Eki (Bölüm 6 şablonu).
- Yetersiz ülkelere aktarımlar için Standart Sözleşme Maddeleri (Karar
  2021/914); Aktarım Etki Değerlendirmesi yapılır ve saklanır.
- Bilgi güvenliği eki.
- SLA ve servis kredileri.
- Çıkış ve geçiş planı.

### 3.4 Onboarding
- Kimlikleri asgari ayrıcalıkla sağlar
  (`05-technical-measures/access-control.md`).
- Tedarikçi iş gücü eğitim onayı (`training.md`).
- Ağ ve sistem entegrasyon güvenlik incelemesi.
- ROPA'ya ekle (`02-ropa/`).

### 3.5 Operasyon
- Sürekli izleme - V1-V2 için güvenlik derecelendirmeleri (BitSight,
  SecurityScorecard veya eşdeğeri).
- V1 için aylık, V2 için üç aylık, V3 için yıllık SLA incelemesi.
- DPA başına olay raporlama.
- Alt-işleyici değişim bildirimleri.
- Maddi değişimde periyodik VKD tazelemesi.
- V1 için yıllık veya risk temelli yerinde veya sanal denetim hakkı
  kullanılır.

### 3.6 Yenileme
- Yenilemede durum tespitini yeniden gerçekleştir.
- DPA'yı güncel SCC sürümü, Schrems II tamamlayıcı tedbir durumu ve güncel
  alt-işleyici listesi ile güncelle.

### 3.7 Çıkış
- Sona erdirme kararı, tedarikçi başarısızlığı veya sözleşme sonu
  tarafından tetiklenir.
- Üzerinde anlaşılan formatta ve zaman çizelgesinde veri iadesi.
- Tedarikçi kopyalarının sertifikalı imhası
  (`05-technical-measures/backup-recovery.md` Bölüm 9).
- Erişim hizmet dışı bırakılır.
- Belge güncellemesi; kayıt saklanır.

## 4. Sürekli Denetim

| Kontrol | V1 | V2 | V3 | V4 |
|---------|----|----|----|----|
| Yıllık DPA tazelemesi | Evet | Evet | Evet | Geçerliyse |
| Güvenlik derecelendirmesi izleme | Günlük | Haftalık | Aylık | İsteğe bağlı |
| Alt-işleyici onayı | Sıkı | Sıkı | Bildirim | yok |
| Sızma testi incelemesi | Yıllık | Yıllık | İsteğe bağlı | yok |
| Denetim hakkı | Evet (yıllık) | Evet (her 2 yılda veya sebepte) | Sebepte | yok |
| Masa başı katılımı | Evet | İsteğe bağlı | yok | yok |
| Çıkış tatbikatı | Evet (her 2 yılda) | İsteğe bağlı | yok | yok |

## 5. Alt-İşleyici Rejimi

- DPA, genel yazılı yetkilendirme (bildirim ve itiraz hakkı ile) ve özel
  yazılı yetkilendirme arasında ayrım yapar.
- Alt-işleyici listesi konumlar ve amaçlarla kontrolöre yayımlanır.
- Yeni veya değiştirilen alt-işleyiciler için bildirim süresi en az 30 gün
  (V1 / V2) veya yüksek riskli ekler için 60 gündür.
- Kontrolör makul gerekçelerle itiraz edebilir; itiraz süreci DPA'da
  tanımlanır.
- Alt-işleyiciler işleyiciyle aynı veri koruma yükümlülüklerine aynı
  koşullarda bağlanır.
- Sonraki aktarım zinciri Schrems II uyumu için belgelenir.

## 6. Tam Veri İşleme Eki (DPA) Şablonu

Aşağıdaki şablon, AB ya da AB-dışı bir işleyici ile etkileşim kuran AB
merkezli kontrolör için uygundur. Düzenleme notları köşeli parantez `[ ]`
içindedir.

```
VERİ İŞLEME EKİ (DPA)

Bu Veri İşleme Eki ("DPA"), aşağıdakiler arasında akdedilmiştir:

KONTROLÖR: [Yasal Ad], kayıtlı adres [adres], yasal kuruluş tanımlayıcısı
[LEI / şirket numarası]

İŞLEYİCİ: [Yasal Ad], kayıtlı adres [adres], yasal kuruluş tanımlayıcısı
[LEI / şirket numarası]

(her biri "Taraf" ve birlikte "Taraflar")

Bu DPA, [tarih] tarihli [Ana Hizmet Sözleşmesi / Hizmet Sözleşmesi]'ne
("Ana Sözleşme") dahil edilmiştir ve onun bir parçasını oluşturur. Bu DPA
ile Ana Sözleşme arasında çelişki olması durumunda, bu DPA kişisel veri
koruma konularında üstündür.

1. TANIMLAR
   1.1 Burada tanımlanmamış büyük harfli terimler, Tüzük (AB) 2016/679
       ("GDPR")'da verilen anlama sahiptir.
   1.2 "İştirak", bir Tarafı Kontrol eden, onun tarafından Kontrol edilen
       veya onunla ortak Kontrol altında olan bir kuruluşu ifade eder.
   1.3 "Alt-işleyici", İşleyicinin Kontrolör adına Kişisel Veriyi
       işlemek için görevlendirdiği herhangi bir üçüncü tarafı ifade
       eder.
   1.4 "Standart Sözleşme Maddeleri" veya "SCC", Komisyon Uygulama Kararı
       (AB) 2021/914 Ekinin Modül 2'sini (veya Kontrolör kendi başına bir
       işleyici olduğunda Modül 3'ü) ifade eder.
   1.5 "Kişisel Veri İhlali", GDPR Madde 4(12)'de verilen anlama sahiptir.
   1.6 "Çizelge", bu DPA'ya ekli bir çizelgeyi ifade eder.

2. KAPSAM VE ROLLER
   2.1 İşleyici, Ana Sözleşmede tanımlanan hizmetleri yerine getirmek
       için Kontrolör adına Kişisel Veriyi işler.
   2.2 Taraflar, GDPR Madde 4 anlamında sırasıyla Kontrolör ve İşleyicidir.
       Kontrolör, hizmetleri kendi hesabında kullanan herhangi bir
       İştirakin Kontrolörü adına bu DPA'ya girmek için Kontrolöre yetki
       verdiğini kabul eder.

3. KONU, SÜRE, NİTELİK, AMAÇ, KATEGORİLER (Md. 28(3))
   3.1 İşlemenin konusu, süresi, niteliği ve amacı, Kişisel Veri türü ve
       Veri Sahibi kategorileri Çizelge 1 (İşleme Tanımı) içinde
       belirlenmiştir.

4. İŞLEYİCİ YÜKÜMLÜLÜKLERİ
   4.1 İşleyici, aktarımlar dahil olmak üzere yalnızca Kontrolörün
       belgelenmiş talimatlarıyla Kişisel Veriyi işler; Birlik veya Üye
       Devlet hukuku tarafından bunu yapması gerekmedikçe; bu durumda,
       İşleyici, bu hukuk önemli kamu yararı gerekçesiyle bu tür
       bilgilendirmeyi yasaklamadıkça, işlemeden önce Kontrolöre o yasal
       gerekliliği bildirir.
   4.2 İşleyici, Kişisel Veriyi işlemeye yetkili kişilerin gizlilikle
       kendilerini taahhüt ettiklerini veya uygun yasal bir gizlilik
       yükümlülüğü altında olduklarını sağlar.
   4.3 İşleyici, GDPR Madde 32 uyarınca gerekli tüm tedbirleri alır.
       Teknik ve organizasyonel tedbirler Çizelge 2 (TOM'lar) içinde
       belirlenmiştir. İşleyici, koruma seviyesi azaltılmadığı sürece
       TOM'larını istediği zaman güncelleyebilir.
   4.4 İşleyici, madde 7'de belirtildiği gibi önceden özel veya genel
       yazılı yetkilendirme olmaksızın başka bir işleyici (Alt-işleyici)
       görevlendirmez.
   4.5 İşleyici, mümkün olduğu ölçüde, işlemenin niteliğini dikkate
       alarak, GDPR Madde 12-22 kapsamında veri sahibi haklarının
       kullanımı taleplerine yanıt verme Kontrolör yükümlülüğünün
       yerine getirilmesi için Kontrolöre uygun teknik ve organizasyonel
       tedbirlerle yardımcı olur.
   4.6 İşleyici, işlemenin niteliği ve İşleyicinin elindeki bilgiler
       dikkate alınarak, GDPR Madde 32-36 kapsamındaki yükümlülüklere
       uyumun sağlanmasında Kontrolöre yardımcı olur.
   4.7 Kontrolörün seçimine bağlı olarak, İşleyici, işlemeye ilişkin
       hizmetlerin sağlanmasının sona ermesinden sonra tüm Kişisel
       Veriyi Kontrolöre siler veya iade eder ve Birlik veya Üye Devlet
       hukuku Kişisel Verinin saklanmasını gerektirmedikçe mevcut
       kopyaları siler.
   4.8 İşleyici, GDPR Madde 28'de belirtilen yükümlülüklere uyumu
       göstermek için gerekli tüm bilgileri Kontrolöre sağlar ve madde
       9'da daha ayrıntılı olarak belirtildiği gibi Kontrolör veya
       Kontrolör tarafından yetkilendirilmiş başka bir denetçi
       tarafından yürütülen denetimlere izin verir ve katkıda bulunur.
   4.9 İşleyici, kendi görüşüne göre bir talimatın GDPR'yi veya diğer
       Birlik veya Üye Devlet veri koruma hükümlerini ihlal ettiğini
       tespit ederse derhal Kontrolöre bildirir.

5. KONTROLÖR YÜKÜMLÜLÜKLERİ
   5.1 Kontrolör, veri sahiplerine gerekli tüm bilgileri sağlamak ve
       GDPR Madde 6 (ve geçerli olduğunda Madde 9 / 10) kapsamında
       geçerli bir yasal dayanak sürdürmek dahil olmak üzere İşleyiciden
       gerçekleştirmesini istediği işlemenin hukukiliğinden sorumludur.
   5.2 Kontrolör, kayda alınabilecek bir şekilde talimatlar verir.
   5.3 Kontrolör, bu DPA'nın süresi boyunca daha fazla yazılı talimat
       verebilir. İşleyici, standart hizmet kapsamı dışındaki talimatlar
       için makul bir ücret talep edebilir.

6. İŞLEME GÜVENLİĞİ (Md. 32)
   6.1 İşleyici, teknolojinin mevcut durumu, uygulama maliyetleri ve
       işlemenin niteliği, kapsamı, bağlamı ve amaçları dikkate alınarak
       riske uygun düzeyde güvenlik sağlamak için Çizelge 2'de
       belirlenen teknik ve organizasyonel tedbirleri uygular.
   6.2 İşleyici, bu tedbirlerin etkinliğini düzenli olarak test eder,
       değerlendirir ve denetler ve talep üzerine kanıt üretir.

7. ALT-İŞLEYİCİLER (Md. 28(2), (4))
   7.1 Kontrolör, bu suretle İşleyiciye Alt-işleyici görevlendirmek için
       genel yazılı yetki verir. Alt-işleyicilerin güncel listesi
       Çizelge 3'te belirtilmiştir.
   7.2 İşleyici, Alt-işleyicilerin eklenmesi veya değiştirilmesine
       ilişkin herhangi bir niyet edilen değişikliği en az otuz (30) gün
       önceden Kontrolöre bildirir ve Kontrolöre veri koruma ile ilgili
       makul gerekçelerle itiraz etme fırsatı verir.
   7.3 Kontrolör itiraz ederse, Taraflar iyi niyetle müzakere eder. Otuz
       (30) gün içinde anlaşma sağlanmazsa, Kontrolör cezasız olarak
       etkilenen hizmetleri sona erdirebilir ve İşleyici makul geçiş
       yardımı sağlar.
   7.4 İşleyici, gizlilik, güvenlik ve denetim açısından dahil olmak
       üzere her Alt-işleyiciye bu DPA'dakilerden daha az koruyucu
       olmayan veri koruma yükümlülükleri yükler.
   7.5 İşleyici, Alt-işleyicinin yükümlülüklerinin yerine getirilmesi
       için Kontrolöre tam olarak sorumlu kalır.

8. ULUSLARARASI AKTARIMLAR (Md. 44-49)
   8.1 İşleyici, bu madde ve Çizelge 4'e uygun olarak hariç olmak
       üzere AEA dışına Kişisel Veri aktarmaz.
   8.2 İşleyici veya bir Alt-işleyici, Komisyon yeterlilik kararından
       yararlanmayan üçüncü bir ülkede yerleşikse, Taraflar Çizelge 4'te
       seçilen seçenekler ve tamamlanan eklerle uygun olduğu üzere Modül
       2 (kontrolörden işleyiciye) veya Modül 3 (işleyiciden işleyiciye)
       Standart Sözleşme Maddelerini (Karar 2021/914) dahil eder.
   8.3 İşleyici, böyle bir aktarımdan önce bir Aktarım Etki Değerlendirmesi
       ("TIA") yürüttüğünü ve EDPB Tavsiyeleri 01/2020 tarafından
       gerektirildiği gibi esasen eşdeğer düzeyde koruma sağlamak için
       gerekli tamamlayıcı teknik, sözleşmesel ve organizasyonel tedbirleri
       benimsediğini teyit eder. TIA'nın özeti ve tamamlayıcı tedbirler
       Çizelge 4'te sağlanmıştır.
   8.4 İşleyici, üçüncü ülkenin kamu otoritelerinden alınan Kişisel
       Verinin açıklanması için bağlayıcı talepler dahil olmak üzere SCC
       kapsamındaki yükümlülüklerine uyamaz hale gelirse Kontrolöre
       derhal bildirir ve hukuki ve anlamlı olduğunda bu tür talepleri
       itiraz eder.

9. DENETİM HAKKI (Md. 28(3)(h))
   9.1 Kontrolör, Kontrolörün masraflarıyla (denetim maddi uyumsuzluk
       ortaya koyarsa İşleyici masrafı üstlenir) bu DPA'ya İşleyicinin
       uyumunun denetimlerini, incelemeler dahil olmak üzere
       gerçekleştirebilir. Denetimler:
       (a) en az otuz (30) gün önceden yazılı bildirimde (olay durumunda
           anında bildirim);
       (b) normal iş saatlerinde;
       (c) ilgili tesisler, sistemler ve kayıtlarla sınırlı;
       (d) İşleyicinin operasyonlarını makul olmayan şekilde aksatmayan
           bir şekilde gerçekleştirilir.
   9.2 İşleyici, aşağıdaki durumlar hariç güncel bağımsız üçüncü taraf
       sertifikasyonları (ISO 27001, ISO 27701, bulut için ISO 27018,
       SOC 2 Type II, PCI DSS) ve en son sızma testi özetini sağlayarak
       denetim yükümlülüğünü karşılayabilir:
       (a) Kontrolörü etkileyen onaylanmış bir Kişisel Veri İhlali;
       (b) yetkili bir denetim otoritesinden talimat;
       (c) maddi uyumsuzluğun makul şüphesi.
       Bu durumlardan herhangi birinde, yerinde veya sanal bir denetim
       yapılabilir.
   9.3 Denetçiler gizlilik yükümlülüklerine tabidir.

10. KİŞİSEL VERİ İHLALLERİ (Md. 33)
    10.1 İşleyici, gereksiz gecikme olmaksızın ve her durumda farkına
         varmasından sonra yetmiş iki (72) saat içinde bir Kişisel Veri
         İhlalini Kontrolöre bildirir. Bildirim, bilindiği ölçüde GDPR
         Madde 33(3) kapsamında gerekli bilgileri içerir ve daha fazla
         bilgi mevcut hale geldikçe tamamlanır.
    10.2 İşleyici, soruşturma, hafifletme ve denetim otoritelerine ve
         veri sahiplerine bildirimde Kontrolörle makul şekilde işbirliği
         yapar ve hukukun aksini gerektirmediği sürece Kontrolörün
         önceden yazılı onayı olmadan Kontrolörün verisine ilişkin olay
         hakkında kamuya açıklama yapmaz.
    10.3 İşleyici, Kontrolörün Kişisel Verisini etkileyen ihlaller
         kayıt defterini sürdürür ve talep üzerine girişleri sağlar.

11. VERİ SAHİBİ TALEPLERİ (Md. 12-22)
    11.1 İşleyici, işlemenin niteliğini dikkate alarak, uygun teknik ve
         organizasyonel tedbirlerle, GDPR Madde 15-22 kapsamında
         haklarını kullanan veri sahiplerinin taleplerine yanıt vermede
         Kontrolöre yardımcı olur.
    11.2 İşleyici, Kontrolör tarafından talimatlandırılmadıkça veya
         hukukun gerektirdiği şekilde olmadıkça veri sahiplerine
         doğrudan yanıt vermez ve aldığı bu tür herhangi bir talebi
         derhal Kontrolöre iletir.

12. İŞLEME KAYITLARI (Md. 30(2))
    12.1 İşleyici, Kontrolör adına yürütülen tüm işleme etkinliği
         kategorilerinin kayıtlarını sürdürür ve talep üzerine sağlar.

13. İADE VE SİLME
    13.1 Kontrolörün seçimine bağlı olarak, hizmetlerin sağlanmasının
         sona ermesinde, İşleyici tüm Kişisel Veriyi Kontrolöre siler
         veya iade eder ve Birlik veya Üye Devlet hukuku saklamayı
         gerektirmedikçe mevcut kopyaları siler. İşleyici, tamamlanmasından
         sonra otuz (30) gün içinde silmenin yazılı teyidini sağlar.

14. SORUMLULUK
    14.1 Bu DPA kapsamındaki sorumluluk Ana Sözleşme tarafından yönetilir;
         ancak bu DPA'daki hiçbir şey GDPR Madde 82 kapsamında bir veri
         sahibinin herhangi bir hak veya çaresini sınırlamaz.

15. SÜRE
    15.1 Bu DPA, Ana Sözleşmenin Yürürlük Tarihinden itibaren etkilidir
         ve İşleyicinin Kontrolör adına Kişisel Veri işlediği sürece
         artı madde 13 tarafından gerekli herhangi bir süre boyunca
         yürürlükte kalır.

16. GEÇERLİ HUKUK
    16.1 Bu DPA, Ana Sözleşme hukukuna tabidir; ancak madde 8'e dahil
         edilen SCC'ler kendi koşullarına uygun olarak yönetilir.

17. ÇİZELGELER
    Çizelge 1 - İşleme Tanımı (Md. 28(3))
    Çizelge 2 - Teknik ve Organizasyonel Tedbirler (Md. 32)
    Çizelge 3 - Alt-işleyiciler Listesi
    Çizelge 4 - Uluslararası Aktarımlar ve SCC'ler

Kontrolör adına imzalanmıştır:
   Ad:     Rol:     İmza:     Tarih:

İşleyici adına imzalanmıştır:
   Ad:     Rol:     İmza:     Tarih:
```

### Çizelge 1 - İşleme Tanımı (iskelet)

- İşlemenin konusu
- İşlemenin süresi
- İşlemenin niteliği ve amacı
- Kişisel veri türü
- Veri sahibi kategorileri
- Aktarım sıklığı (sürekli / talep üzerine)
- Saklama süresi

### Çizelge 2 - TOM'lar (iskelet, `05-technical-measures/`'a eşlenmiş)

- Pseudonimizasyon ve şifreleme
- Gizlilik, bütünlük, kullanılabilirlik, dayanıklılık
- Geri yükleme ve kurtarma
- Düzenli test
- Erişim kontrolü
- Loglama ve izleme
- Olay müdahalesi
- Zafiyet yönetimi
- Personel
- Fiziksel güvenlik

### Çizelge 3 - Alt-işleyiciler

| Ad | Hizmet | Konum | Eklenme Tarihi |
|----|--------|-------|-----------------|

### Çizelge 4 - Uluslararası Aktarımlar

- Aktarım mekanizması (yeterlilik / SCC modülü / BCR / Madde 49 istisnası).
- SCC parametreleri (docking, uyuşmazlık çözümü, geçerli hukuk, denetim
  maddesi).
- TIA özeti, tamamlayıcı tedbirler.

## 7. Düzenleme Rehberliği

- Kontrolörden işleyiciye aktarımlar için Modül 2 SCC'leri kullan; kontrolör
  kendisi bir işleyici ise Modül 3.
- Aynı koşullarda anlaşmaya Madde 28(9) işleyiciden alt-işleyiciye
  yükümlülüklerini dahil et.
- İşleyici Birleşik Krallık / İsviçre'de yerleşikse, Birleşik Krallık IDTA /
  İsviçre FDPIC adaptasyonlarını ekle.
- Veri özel-nitelikli (Madde 9) veya çocuklarla ilgiliyse, Çizelge 2'de ek
  güvenceleri belgele.
- Yetki alanına özgü hususlar için `07-international-transfers/` ile
  koordine et.

## 8. KPI'lar

| Metrik | Hedef |
|--------|-------|
| Güncel DPA'lı V1 / V2 tedarikçileri | %100 |
| Güncel alt-işleyici listesi | %100 |
| Yeterlilik dışı aktarımlar için yapılan TIA | %100 |
| DPA SLA içinde tedarikçi olay bildirimleri | %100 |
| Plana göre tamamlanan denetim hakkı kullanımları | %100 |
| Sertifikalı imhalı tedarikçi çıkışları | %100 |

## 9. Eşleme

| Gereklilik | GDPR | ISO 27002:2022 | NIST CSF 2.0 |
|------------|------|----------------|--------------|
| Tedarikçi ilişkileri | Md. 28 | 5.19 | GV.SC-1 |
| Tedarikçi ilişkilerinde bilgi güvenliği | Md. 28 | 5.19 | GV.SC-3 |
| Anlaşmalarda güvenliği ele alma | Md. 28(3) | 5.20 | GV.SC-4 |
| BİT tedarik zincirini yönetme | Md. 28 | 5.21 | GV.SC-5 |
| Tedarikçi hizmetlerinin izlenmesi | Md. 28 | 5.22 | GV.SC-7 |
| Bulut hizmetleri için bilgi güvenliği | Md. 28 | 5.23 | GV.SC-1 |
