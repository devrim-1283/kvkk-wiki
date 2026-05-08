---
title:
  en: "DPIA - Article 35 Triggers, 11-Section Template, ISO 29134, Prior Consultation"
  tr: "VKD - Madde 35 Tetikleyicileri, 11-Bölümlü Şablon, ISO 29134, Ön Danışma"
section: "06-organizational-measures"
document_type: "procedure_template"
control_id: "ORG-DPIA-01"
owner:
  primary: "DPO"
  secondary: "CISO, Project / Product Owners"
review_cycle: "annual"
last_review: "2026-05-08"
next_review: "2027-05-08"
classification: "Internal"
language: ["en", "tr"]
references:
  - "GDPR Art. 24, 25, 35, 36, 39(1)(c), Recitals 75, 84, 89-95"
  - "EDPB Guidelines on DPIA (WP248 rev.01, endorsed by EDPB)"
  - "EDPB Article 36 prior consultation guidance"
  - "ISO/IEC 29134:2017 Privacy Impact Assessment"
  - "ENISA Recommendations for SMEs on DPIA"
  - "National DPA mandatory and exempt lists (e.g., CNIL, BfDI, AEPD, ICO)"
---

## English

# Data Protection Impact Assessment (DPIA)

## 1. Purpose

GDPR Article 35(1) requires a DPIA where a type of processing, in particular
using new technologies, is "likely to result in a high risk to the rights
and freedoms of natural persons." Article 35(7) sets the minimum content.
Article 36 requires prior consultation of the supervisory authority where a
DPIA indicates that processing would result in a high risk in the absence
of measures taken by the controller to mitigate the risk.

The DPIA is a forward-looking risk-management instrument and a privacy-by-
design tool (Article 25), not a compliance afterthought.

## 2. Mandatory Triggers

Article 35(3) lists three baseline triggers; supervisory authorities have
published mandatory and exempt lists. The controller treats the following
as triggers, requiring a DPIA:

1. **Systematic and extensive evaluation** of personal aspects, including
   profiling, on which decisions are based that produce legal effects or
   similarly significantly affect the data subject (Art. 35(3)(a)).
2. **Large-scale processing** of special categories of data (Art. 9) or
   personal data relating to criminal convictions and offences (Art. 10)
   (Art. 35(3)(b)).
3. **Systematic monitoring of a publicly accessible area on a large scale**
   (Art. 35(3)(c)).
4. **Use of new technologies** including AI, biometrics, IoT.
5. **Innovative use** of established technology in a new context.
6. **Children's data** processed beyond strictly necessary website
   functioning.
7. **Employee monitoring** (DLP, surveillance, productivity tracking,
   location tracking).
8. **Data matching** combining data sets that originate from different
   processing operations.
9. **Behavioural advertising or tracking** at scale.
10. **Processing data subjects who cannot easily exercise rights** (mental
    capacity, vulnerable groups, asylum seekers).
11. **Cross-border transfers** to non-adequacy countries combined with
    sensitive purposes.
12. **Processing that prevents data subjects from exercising a right or
    using a service or contract**.

Apply the EDPB nine-criteria heuristic: where two or more apply, treat as
high risk and conduct a DPIA. Single-criterion cases assessed on context.

## 3. When Performed

- **Before** the processing starts. DPIA is a planning instrument.
- **Refresh** when:
  - The risk evolves materially.
  - The controller changes scope, purpose or technology.
  - A breach involving the processing reveals an underestimated risk.
  - At least every two years for high-risk processing in operation.

## 4. Roles

| Role | Responsibility |
|------|----------------|
| Project / product owner | Initiates the DPIA; provides description; owns risk treatment |
| DPO | Advises (Art. 39(1)(c)); reviews; signs off; advises on prior consultation |
| CISO | Provides security risk perspective and TOM review |
| Legal | Lawful basis, contract, regulatory analysis |
| Data subject representatives | Consulted where appropriate (Art. 35(9)) |
| Processors / sub-processors | Provide assistance (Art. 28(3)(f)) |
| Approver | Senior business owner accountable for the residual risk |

## 5. ISO/IEC 29134 Alignment

ISO/IEC 29134:2017 provides a globally consistent process. The controller
maps Article 35 to ISO 29134 phases:

1. Preparation - scope, plan, resources.
2. Performance - assessment of necessity, proportionality, risks, controls.
3. Reporting - DPIA report; consultation; sign-off.
4. Monitoring - implementation of measures; review; refresh.

## 6. DPIA Template (11 Sections)

### Section 1 - Identification
- DPIA reference number.
- Project / processing name.
- Owner and team.
- DPO and CISO contacts.
- Date of initiation, target completion, decision date.
- Status (draft / under review / approved / rejected).
- Linked ROPA entry (`02-ropa/`).

### Section 2 - Description of the Processing (Art. 35(7)(a))
- Processing operations and purposes.
- Categories of data subjects.
- Categories of personal data, including any Article 9 / Article 10 data.
- Recipients - internal and external (processors, third parties).
- Cross-border transfers and mechanisms (`07-international-transfers/`).
- Retention period (`04-retention-erasure/`).
- Technical and organisational environment - systems, locations, providers.
- Data flow diagram.

### Section 3 - Necessity and Proportionality (Art. 35(7)(b))
- Lawful basis under Article 6 (and 9 / 10 where applicable).
- Why this purpose cannot be achieved with less data, less retention or
  less identifying data.
- Compliance with data quality, accuracy, transparency, minimisation,
  storage limitation.
- Information provided to data subjects (`03-transparency-consent/`).
- Means for exercising rights (`09-data-subject-rights/`).
- Compliance with processor obligations (`vendor-management.md`).

### Section 4 - Consultation
- Whether and how the views of data subjects (or their representatives) are
  sought (Art. 35(9)).
- Outcomes; if no consultation, justification recorded.
- Whether processors and other stakeholders consulted.

### Section 5 - Risk Identification (Art. 35(7)(c))
For each identified risk to data subjects:
- Risk source (threat).
- Risk event (impact on confidentiality, integrity, availability, lawful
  use).
- Affected data subjects.
- Severity (1-4) and rationale.
- Likelihood (1-4) and rationale.
- Inherent risk = severity x likelihood.
- LINDDUN privacy threats considered (`05-technical-measures/application-security.md`).

Use the four-level scale per ENISA: Low, Medium, High, Very High.

### Section 6 - Existing Controls and Their Effectiveness
- Mapping to controls in `05-technical-measures/` and
  `06-organizational-measures/`.
- Evidence of effectiveness (audit, test, certification).
- Gaps.

### Section 7 - Additional Measures (Art. 35(7)(d))
For each significant residual risk:
- Proposed measure.
- Owner.
- Target date.
- Expected risk reduction.
- Residual risk after measure.

### Section 8 - Residual Risk Assessment
- Final residual risk per risk item.
- Overall residual risk - low, medium, high.

### Section 9 - DPO Opinion (Art. 35(2), 39(1)(c))
- DPO assessment of compliance, advice, dissents (if any).
- Where DPO advice is not followed, the controller's reasoning recorded.

### Section 10 - Prior Consultation Determination (Art. 36)
- If overall residual risk remains high after measures, the controller
  consults the supervisory authority before processing.
- Documentation prepared in line with EDPB guidance:
  - Roles of all parties (controllers, processors, sub-processors).
  - Purposes and means.
  - Measures and safeguards.
  - DPO contact.
  - DPIA itself.
  - Any further information requested by the authority.
- The supervisory authority's written advice (within statutory period,
  typically 8 weeks extendable by 6) implemented before processing starts.

### Section 11 - Approval and Sign-off
- Owner.
- DPO.
- CISO.
- Senior accountable executive.
- Date.
- Conditions of approval (if any).
- Re-review trigger.

## 7. Sample Risk Catalogue (non-exhaustive)

- Re-identification of pseudonymised data.
- Unauthorised access (insider, external).
- Excessive scope of access (least-privilege failure).
- Loss of availability (ransomware, regional outage).
- Inaccurate / outdated personal data leading to harm.
- Onward disclosure beyond purpose.
- Unlawful international transfer.
- Profiling producing biased outcomes.
- Lack of transparency / dark patterns.
- Inability to exercise rights.
- Excessive retention.
- Vendor failure or sub-processor change without notice.
- Children's vulnerability.
- Surveillance impact on privacy of employees.

## 8. Lifecycle

1. Owner triggers DPIA via the privacy intake form.
2. DPO scopes within 5 business days.
3. Cross-functional working sessions (typically 2-3 over 2-4 weeks).
4. Draft for review.
5. Stakeholder review and risk treatment plan.
6. DPO opinion.
7. Approval (or rejection).
8. If high residual risk: prior consultation (Article 36).
9. Implementation of measures.
10. Post-implementation review and storage in DPIA register.

## 9. DPIA Register

The DPIA register holds:

- All DPIAs (draft, approved, rejected, retired).
- Linkage to ROPA entries.
- Risk treatment plans and status.
- Consultation records.

The register is sampled by internal audit (`internal-audit.md`).

## 10. Outputs and Storage

- DPIA report (PDF / signed).
- Working files (data flow diagrams, risk register, control mapping).
- Consultation evidence (data subject feedback, regulator correspondence).

Retention: life of the processing plus minimum 10 years.

## 11. Quality Criteria for a Defensible DPIA

- Specific to the actual processing - not boilerplate.
- Names risk to data subjects, not risk to the company.
- Quantifies severity and likelihood with rationale.
- Uses external context (similar processing, public incidents, court
  decisions).
- Lists mitigations with concrete owners and dates.
- Includes the DPO opinion with any disagreements.
- Reviewed and updated.

## 12. Common Failure Modes

- Performing the DPIA after the system is in production.
- Treating it as a checklist rather than an assessment.
- Failing to document the lawful basis under Article 6 (and 9 / 10).
- Not consulting data subjects or representatives where appropriate.
- Confusing pseudonymisation with anonymisation
  (`05-technical-measures/masking-anonymization.md`).
- Underestimating Schrems II issues for cross-border processing.
- Ignoring DPO advice without recording rationale.

## 13. KPIs

| Metric | Target |
|--------|--------|
| DPIAs completed before processing starts | 100 % |
| DPIAs refreshed every <= 2 years for high-risk processing | 100 % |
| Prior consultations submitted where required | 100 % |
| DPIA register accuracy at audit | 100 % |
| DPO opinion present on every DPIA | 100 % |

## 14. Mapping

| Requirement | GDPR | ISO 27001/2:2022 | NIST CSF 2.0 |
|-------------|------|------------------|--------------|
| DPIA | Art. 35 | 5.34 | GV.RM-1, ID.RA |
| Prior consultation | Art. 36 | n/a | GV.RM-1 |
| Privacy by design | Art. 25 | 8.27 | GV.PO-1, ID.RA |
| DPO advisory | Art. 39 | 5.31 | GV.RR |

---

## Türkçe

# Veri Koruma Etki Değerlendirmesi (VKD)

## 1. Amaç

GDPR Madde 35(1), bir işleme türünün, özellikle yeni teknolojiler
kullanarak, "gerçek kişilerin hak ve özgürlükleri için yüksek riskle
sonuçlanma olasılığı yüksek" olduğu yerde bir VKD'yi gerektirir. Madde 35(7)
asgari içeriği belirler. Madde 36, bir VKD'nin kontrolör tarafından riski
hafifletmek için alınan tedbirler olmadığında işlemenin yüksek riskle
sonuçlanacağını gösterdiği yerde denetim otoritesinin ön danışmasını
gerektirir.

VKD ileriye dönük bir risk yönetimi aracı ve tasarımdan gizlilik aracıdır
(Madde 25), uyumluluk düşüncesi sonrası değildir.

## 2. Zorunlu Tetikleyiciler

Madde 35(3) üç temel tetikleyiciyi listeler; denetim otoriteleri zorunlu ve
muaf listeleri yayımlamıştır. Kontrolör aşağıdakileri tetikleyici olarak
ele alır ve VKD'yi gerektirir:

1. Hukuki etkiler veya benzer şekilde önemli olarak veri sahibini etkileyen
   kararların temel alındığı, profilleme dahil kişisel yönlerin
   **sistematik ve kapsamlı değerlendirmesi** (Md. 35(3)(a)).
2. Özel veri kategorilerinin (Md. 9) veya cezai mahkumiyet ve suçlara
   ilişkin kişisel verilerin (Md. 10) **büyük ölçekli işlenmesi**
   (Md. 35(3)(b)).
3. **Kamuya açık bir alanın büyük ölçekte sistematik izlenmesi**
   (Md. 35(3)(c)).
4. **Yeni teknoloji kullanımı** dahil AI, biyometri, IoT.
5. Yerleşik teknolojinin yeni bir bağlamda **yenilikçi kullanımı**.
6. Web sitesinin sıkı gerekli işleyişinin ötesinde işlenen **çocuk verisi**.
7. **Çalışan izleme** (DLP, gözetim, üretkenlik takibi, konum takibi).
8. Farklı işleme operasyonlarından kaynaklanan veri kümelerini birleştiren
   **veri eşleştirme**.
9. Ölçekte **davranışsal reklamcılık veya takip**.
10. **Hakkı kolayca kullanamayan veri sahiplerinin işlenmesi** (zihinsel
    kapasite, savunmasız gruplar, sığınmacılar).
11. Hassas amaçlarla birlikte yeterlilik dışı ülkelere **sınır ötesi
    aktarımlar**.
12. **Veri sahiplerinin bir hakkı kullanmasını veya bir hizmeti veya
    sözleşmeyi kullanmasını engelleyen işleme**.

EDPB dokuz kriter sezgisini uygulayın: ikisi veya daha fazlası geçerli ise,
yüksek risk olarak ele alın ve bir VKD yürütün. Tek kriter durumları bağlama
göre değerlendirilir.

## 3. Ne Zaman Yapılır

- İşleme başlamadan **önce**. VKD bir planlama aracıdır.
- Şu durumlarda **yenile**:
  - Risk maddi olarak gelişir.
  - Kontrolör kapsamı, amacı veya teknolojiyi değiştirir.
  - İşlemeyi içeren bir ihlal, hafife alınmış bir riski ortaya çıkarır.
  - Operasyonda yüksek riskli işleme için en az iki yılda bir.

## 4. Roller

| Rol | Sorumluluk |
|-----|------------|
| Proje / ürün sahibi | VKD'yi başlatır; tanım sağlar; risk işlemine sahiptir |
| DPO | Danışmanlık eder (Md. 39(1)(c)); inceler; onaylar; ön danışma konusunda danışmanlık eder |
| CISO | Güvenlik risk perspektifi ve TOM incelemesi sağlar |
| Hukuk | Yasal dayanak, sözleşme, düzenleyici analiz |
| Veri sahibi temsilcileri | Uygun olduğunda istişare edilir (Md. 35(9)) |
| İşleyiciler / alt-işleyiciler | Yardım sağlar (Md. 28(3)(f)) |
| Onaylayan | Kalan risk için hesap veren kıdemli iş sahibi |

## 5. ISO/IEC 29134 Hizalaması

ISO/IEC 29134:2017 küresel olarak tutarlı bir süreç sağlar. Kontrolör Madde
35'i ISO 29134 aşamalarına eşler:

1. Hazırlık - kapsam, plan, kaynaklar.
2. Yürütme - gereklilik, orantılılık, riskler, kontroller değerlendirmesi.
3. Raporlama - VKD raporu; danışma; onay.
4. İzleme - tedbirlerin uygulanması; inceleme; tazeleme.

## 6. VKD Şablonu (11 Bölüm)

### Bölüm 1 - Tanımlama
- VKD referans numarası.
- Proje / işleme adı.
- Sahip ve ekip.
- DPO ve CISO iletişim bilgileri.
- Başlatma tarihi, hedef tamamlama, karar tarihi.
- Durum (taslak / inceleniyor / onaylandı / reddedildi).
- Bağlı ROPA girişi (`02-ropa/`).

### Bölüm 2 - İşlemenin Tanımı (Md. 35(7)(a))
- İşleme operasyonları ve amaçları.
- Veri sahibi kategorileri.
- Madde 9 / Madde 10 verisi dahil kişisel veri kategorileri.
- Alıcılar - dahili ve harici (işleyiciler, üçüncü taraflar).
- Sınır ötesi aktarımlar ve mekanizmalar (`07-international-transfers/`).
- Saklama süresi (`04-retention-erasure/`).
- Teknik ve organizasyonel ortam - sistemler, konumlar, sağlayıcılar.
- Veri akış diyagramı.

### Bölüm 3 - Gereklilik ve Orantılılık (Md. 35(7)(b))
- Madde 6 (ve geçerli olduğunda 9 / 10) kapsamında yasal dayanak.
- Bu amacın neden daha az veri, daha az saklama veya daha az tanımlayıcı
  veri ile gerçekleştirilemeyeceği.
- Veri kalitesi, doğruluk, şeffaflık, minimizasyon, saklama sınırlaması ile
  uyumluluk.
- Veri sahiplerine sağlanan bilgi (`03-transparency-consent/`).
- Hakların kullanımı için araçlar (`09-data-subject-rights/`).
- İşleyici yükümlülükleri ile uyumluluk (`vendor-management.md`).

### Bölüm 4 - Danışma
- Veri sahiplerinin (veya temsilcilerinin) görüşlerinin alınıp alınmadığı
  ve nasıl alındığı (Md. 35(9)).
- Sonuçlar; danışma yoksa, gerekçe kayıtlı.
- İşleyiciler ve diğer paydaşlarla istişare edilip edilmediği.

### Bölüm 5 - Risk Tanımlama (Md. 35(7)(c))
Veri sahiplerine yönelik tanımlanan her risk için:
- Risk kaynağı (tehdit).
- Risk olayı (gizlilik, bütünlük, kullanılabilirlik, hukuka uygun kullanım
  üzerindeki etki).
- Etkilenen veri sahipleri.
- Ciddiyet (1-4) ve gerekçe.
- Olasılık (1-4) ve gerekçe.
- İçsel risk = ciddiyet x olasılık.
- Değerlendirilen LINDDUN gizlilik tehditleri
  (`05-technical-measures/application-security.md`).

ENISA başına dört seviyeli ölçek kullanın: Düşük, Orta, Yüksek, Çok Yüksek.

### Bölüm 6 - Mevcut Kontroller ve Etkinlikleri
- `05-technical-measures/` ve `06-organizational-measures/` altındaki
  kontrollere eşleme.
- Etkinlik kanıtı (denetim, test, sertifikasyon).
- Boşluklar.

### Bölüm 7 - Ek Tedbirler (Md. 35(7)(d))
Her önemli kalan risk için:
- Önerilen tedbir.
- Sahip.
- Hedef tarih.
- Beklenen risk azaltma.
- Tedbir sonrası kalan risk.

### Bölüm 8 - Kalan Risk Değerlendirmesi
- Risk maddesi başına nihai kalan risk.
- Genel kalan risk - düşük, orta, yüksek.

### Bölüm 9 - DPO Görüşü (Md. 35(2), 39(1)(c))
- DPO uyumluluk değerlendirmesi, tavsiye, varsa muhalefet.
- DPO tavsiyesi takip edilmediğinde, kontrolörün muhakemesi kayıtlı.

### Bölüm 10 - Ön Danışma Belirlemesi (Md. 36)
- Tedbirlerden sonra genel kalan risk yüksek kalırsa, kontrolör işleme
  başlamadan önce denetim otoritesine danışır.
- EDPB rehberi doğrultusunda hazırlanan belgeler:
  - Tüm tarafların rolleri (kontrolörler, işleyiciler, alt-işleyiciler).
  - Amaçlar ve araçlar.
  - Tedbirler ve güvenceler.
  - DPO iletişim bilgileri.
  - VKD'nin kendisi.
  - Otorite tarafından istenen herhangi bir ek bilgi.
- Denetim otoritesinin yazılı tavsiyesi (yasal süre içinde, genellikle 6 ile
  uzatılabilir 8 hafta) işleme başlamadan önce uygulanır.

### Bölüm 11 - Onay ve Onaylama
- Sahip.
- DPO.
- CISO.
- Kıdemli sorumlu yönetici.
- Tarih.
- Onay koşulları (varsa).
- Yeniden inceleme tetikleyicisi.

## 7. Örnek Risk Kataloğu (kapsamlı değil)

- Pseudonimleştirilmiş verinin yeniden tanımlanması.
- Yetkisiz erişim (içeriden, dışarıdan).
- Erişimin aşırı kapsamı (asgari ayrıcalık başarısızlığı).
- Kullanılabilirlik kaybı (fidye yazılımı, bölgesel kesinti).
- Zarara yol açan yanlış / güncel olmayan kişisel veri.
- Amaç dışı sonraki açıklama.
- Yasa dışı uluslararası aktarım.
- Önyargılı sonuçlar üreten profilleme.
- Şeffaflık eksikliği / karanlık desenler.
- Hakları kullanma yetersizliği.
- Aşırı saklama.
- Bildirim olmaksızın tedarikçi başarısızlığı veya alt-işleyici değişimi.
- Çocukların savunmasızlığı.
- Çalışanların gizliliği üzerinde gözetim etkisi.

## 8. Yaşam Döngüsü

1. Sahip, gizlilik alım formu üzerinden VKD'yi tetikler.
2. DPO 5 iş günü içinde kapsam belirler.
3. Çapraz işlevsel çalışma oturumları (genellikle 2-4 hafta üzerinde 2-3).
4. İnceleme için taslak.
5. Paydaş incelemesi ve risk işleme planı.
6. DPO görüşü.
7. Onay (veya reddetme).
8. Yüksek kalan risk varsa: ön danışma (Madde 36).
9. Tedbirlerin uygulanması.
10. Uygulama sonrası inceleme ve VKD kayıt defterinde saklama.

## 9. VKD Kayıt Defteri

VKD kayıt defteri tutar:

- Tüm VKD'ler (taslak, onaylı, reddedilmiş, emekli).
- ROPA girişlerine bağlantı.
- Risk işleme planları ve durumu.
- Danışma kayıtları.

Kayıt defteri iç denetim tarafından örneklenir (`internal-audit.md`).

## 10. Çıktılar ve Saklama

- VKD raporu (PDF / imzalı).
- Çalışma dosyaları (veri akış diyagramları, risk kayıt defteri, kontrol
  eşlemesi).
- Danışma kanıtı (veri sahibi geri bildirimi, düzenleyici yazışmaları).

Saklama: işleme ömrü artı asgari 10 yıl.

## 11. Savunulabilir Bir VKD için Kalite Kriterleri

- Gerçek işlemeye özgü - şablon değil.
- Şirkete yönelik riski değil, veri sahiplerine yönelik riski adlandırır.
- Gerekçeyle ciddiyet ve olasılığı niceliklendirir.
- Dış bağlam (benzer işleme, kamu olayları, mahkeme kararları) kullanır.
- Somut sahipler ve tarihlerle hafifletmeleri listeler.
- Herhangi bir anlaşmazlıkla DPO görüşünü içerir.
- İncelenir ve güncellenir.

## 12. Yaygın Başarısızlık Modları

- Sistem üretimde olduktan sonra VKD'yi yapma.
- Değerlendirme yerine kontrol listesi olarak ele alma.
- Madde 6 (ve 9 / 10) kapsamında yasal dayanağı belgelendirememe.
- Uygun olduğunda veri sahiplerine veya temsilcilere danışmama.
- Pseudonimizasyonu anonimleştirmeyle karıştırma
  (`05-technical-measures/masking-anonymization.md`).
- Sınır ötesi işleme için Schrems II sorunlarını hafife alma.
- Gerekçe kaydetmeden DPO tavsiyesini görmezden gelme.

## 13. KPI'lar

| Metrik | Hedef |
|--------|-------|
| İşleme başlamadan önce tamamlanan VKD'ler | %100 |
| Yüksek riskli işleme için <= 2 yılda yenilenen VKD'ler | %100 |
| Gerektiğinde sunulan ön danışmalar | %100 |
| Denetimde VKD kayıt defteri doğruluğu | %100 |
| Her VKD'de mevcut DPO görüşü | %100 |

## 14. Eşleme

| Gereklilik | GDPR | ISO 27001/2:2022 | NIST CSF 2.0 |
|------------|------|------------------|--------------|
| VKD | Md. 35 | 5.34 | GV.RM-1, ID.RA |
| Ön danışma | Md. 36 | yok | GV.RM-1 |
| Tasarımdan gizlilik | Md. 25 | 8.27 | GV.PO-1, ID.RA |
| DPO danışmanlığı | Md. 39 | 5.31 | GV.RR |
