---
title:
  en: "Health Data Processing"
  tr: "Sağlık Verisi İşleme"
section: "10-special-topics"
document_id: "ST-HEALTH-001"
owner: "DPO Office / Clinical Information Officer"
classification: "Internal"
version: "1.0"
last_review: "2026-05-08"
next_review: "2027-05-08"
language: ["en", "tr"]
references:
  - "GDPR Art. 4(15) — Definition of data concerning health"
  - "GDPR Art. 9(1) — Special categories"
  - "GDPR Art. 9(2)(h), (i), (j), 9(3) — Health, public health, research, professional secrecy"
  - "GDPR Recital 35, 53, 54, 159"
  - "EDPB Guidelines 03/2020 on processing of data concerning health for scientific research in the context of the COVID-19 outbreak"
  - "EDPB Document on the Use of Cloud-Based Services by EU Institutions and Bodies (analogous principles)"
  - "EHDS — European Health Data Space (Regulation (EU) 2025/327)"
  - "HL7 FHIR R4/R5 — interoperability standard"
  - "ISO/IEC 27799 — Information security management in health"
---

## English

### 1. Definition

Article 4(15) GDPR defines data concerning health as personal data related to the physical or mental health of a natural person, including the provision of healthcare services, which reveal information about his or her health status. Recital 35 elaborates that this includes:

- information collected in the registration for, or provision of, healthcare services;
- a number, symbol, or particular assigned to a natural person to uniquely identify them for health purposes;
- information derived from the testing or examination of a body part or substance;
- information about disease, disability, disease risk, medical history, clinical treatment, or physiological or biomedical state.

The definition is broad. Insurance health questionnaires, fitness app data, occupational-medicine data, mental-health support records, vaccination records, and dietary requirements stated for medical reasons all qualify.

### 2. Genetic data and biometric data

Genetic data (Article 4(13)) and biometric data used for unique identification (Article 4(14)) are separate special categories with their own provisions. Where the same dataset includes both health and genetic, both regimes apply cumulatively. See `biometric-data.md` for biometric specifics.

### 3. Lawful bases under Article 9(2)

For health data, the principal Article 9(2) bases are:

(a) **Explicit consent** — high standard. Useful for elective health services and research enrolment but not for routine care where consent imbalance and necessity issues arise.

(h) **Preventive or occupational medicine, assessment of working capacity, medical diagnosis, provision of health or social care or treatment, management of health or social care systems and services**, on the basis of EU/MS law or contract with a health professional. This is the workhorse for clinical care.

(i) **Reasons of public interest in the area of public health**, such as protecting against serious cross-border threats to health, ensuring high standards of quality and safety of healthcare and of medicinal products and medical devices, on the basis of EU/MS law providing suitable safeguards.

(j) **Archiving in the public interest, scientific or historical research, statistics**, in accordance with Article 89(1).

Article 9(3) imposes that processing under (h) be conducted by, or under the responsibility of, a health professional or another person subject to an obligation of professional secrecy under EU/MS law or rules of national competent bodies.

### 4. Article 6 lawful basis (always required)

Article 9 unlocks the special category prohibition; Article 6 still must apply. For clinical care, common pairing is Article 6(1)(c) (legal obligation) or 6(1)(b) (contract with the patient) for the underlying processing, with Article 9(2)(h) for the special-category dimension.

### 5. Professional secrecy obligation

Article 9(3) and corresponding Member State law impose secrecy. Professional secrecy is not just a confidentiality posture; it is a legal duty backed by criminal sanction in many states (e.g. French Code Pénal Article 226-13, German StGB §203, Turkish TCK Article 257/258 / specific medical secrecy provisions).

The controller:
- documents who is bound by professional secrecy;
- ensures non-clinical staff who incidentally encounter health data sign equivalent confidentiality undertakings;
- segregates health data from non-clinical systems;
- restricts access to those bound by secrecy and with a clinical or operational need.

### 6. Roles in healthcare processing

| Role | Typical position |
|------|-----------------|
| Hospital, clinic, GP practice | Controller for patient care |
| Independent specialist working in hospital | Often joint controller (see Article 26) |
| Public health authority | Controller for surveillance, registries |
| Health insurer | Controller for claim processing |
| Pharmaceutical manufacturer (post-marketing) | Controller for pharmacovigilance |
| Hospital cloud provider | Processor (Article 28) |
| Medical device manufacturer with telemetry | Controller for safety; potentially joint controller with clinic |
| Clinical research sponsor | Controller for the trial |
| Contract research organisation (CRO) | Processor for the sponsor |

Each role attracts its own documentation, contracts, and rights-handling responsibilities.

### 7. Electronic health records

Electronic health records (EHR) require:

- Interoperability via standards (HL7 FHIR R4/R5; openEHR; SNOMED CT for clinical terminology; LOINC for laboratory).
- Granular role-based access (clinician on the care team; not all clinicians; not administrative staff except billing).
- Break-glass procedure with audit trail for emergency access outside the normal authorisation set.
- Patient access, in accordance with both GDPR Article 15 and Member State patient rights law.
- Audit log of every access (who, when, what record, what action).
- Tamper-evident storage of clinical records.
- Long retention aligned to clinical record-retention rules (commonly 10–30 years; longer for paediatric and obstetric records).

### 8. European Health Data Space (Regulation (EU) 2025/327)

The EHDS Regulation (in force from 2025, applying in phases) creates:

- A primary-use framework giving patients enhanced rights to access and share their EHR cross-border.
- A secondary-use framework allowing access to health data for research, innovation, policy-making, and regulation, under Health Data Access Bodies in each Member State.
- Mandatory interoperability based on the European Electronic Health Record Exchange Format.
- Specific requirements for EHR system manufacturers (CE-marking-style conformity).

The controller plans for EHDS in its product and operational roadmap. Cross-references to Article 6 and 9 GDPR remain.

### 9. HL7 FHIR

HL7 FHIR is the dominant interoperability standard. Privacy considerations:

- Resources (Patient, Observation, MedicationRequest, etc.) carry personal data and identifiers; access controls must be at resource level.
- SMART on FHIR is a common authorisation pattern (OAuth 2.0 + OpenID Connect with health-specific scopes).
- Bulk data export has separate scope and risk profile.
- US-leaning resources sometimes carry assumptions inconsistent with GDPR (broad authorisation by default); configure with EU profiles.
- Sandbox / test environments must not contain real patient data without an Article 28 contract and DPIA.

### 10. Research processing

Research under Article 9(2)(j) and Article 89:

- Member State law often specifies additional requirements (research ethics committee approval, broad consent provisions).
- Pseudonymisation and other safeguards required by Article 89.
- Article 9(2)(j) does not displace ethics review; it operates alongside it.
- Subjects retain Article 15 rights, with limitations under Article 89(2) where exercise would seriously impair the research; the controller documents the impairment specifically.
- Informed consent for the underlying research is governed by clinical-trials regulations (e.g. Regulation (EU) 536/2014); GDPR consent and clinical-trial informed consent are distinct legal acts.

### 11. Genetic data

Article 4(13) genetic data is doubly protected. EDPB guidance and Member State sectoral law (e.g. France's bioethics law, Italy's authorisation regime) impose additional rules:

- Family-relevance: a genetic finding may concern relatives; the controller considers third-party impact.
- Long-tail consequences: inferences possible decades after collection.
- Consent for research vs. clinical use: distinct decisions.
- Direct-to-consumer genetic testing: subject to GDPR; many Member States additionally regulate it as a medical activity.

### 12. Insurance and employment

Health data processed by insurers requires specific Member State law authorisations (Article 9(2)(b), (g), (h) variations). Employer access to health data is highly restricted; occupational medicine is the channel, with Article 9(2)(h) and a documented clinical role. Employer line management does not get diagnoses; it gets fit-for-duty determinations only, where the law allows.

### 13. Telemedicine and connected devices

Telemedicine raises:

- Cross-border processing where the patient and clinician are in different countries — clinical license rules and GDPR transfer rules both apply.
- Recording of consultations: separate consent layer; default is non-recording.
- Connected medical devices: device manufacturer is controller for telemetry, often joint controller with the clinic.
- Edge processing vs. cloud processing: edge reduces transfer surface; cloud requires Article 28 + transfer assessment.

### 14. Digital health apps

Wellness and digital therapeutics apps:

- "Health data" applies broadly; even consumer-fitness data can be Article 9 if it reveals health status.
- App stores' privacy labels must accurately reflect data flows.
- Consent for processing of special-category data must meet the explicit-consent standard.
- DPIA mandatory.
- Strong logical and physical separation from advertising data flows.

### 15. Public health

Article 9(2)(i) covers public health. National examples include vaccination registries, epidemiological surveillance, and infectious-disease reporting. The controller (often a public health authority) operates under specific national law providing safeguards.

In private-sector contexts where the controller contributes data to public-health systems (employer testing during pandemic, occupational-health vaccine reporting), the controller documents the specific national legal basis.

### 16. Data subject rights specifics

| Right | Health-data specifics |
|-------|----------------------|
| Article 15 access | The patient is entitled to a copy of the medical record. National rules govern format and may require clinician-mediated explanation for certain content. |
| Article 16 rectification | Clinical opinion is generally not "rectified" by the patient; factual errors are. Member State patient-rights laws mediate. |
| Article 17 erasure | Heavily limited by retention obligations under Article 17(3)(b)/(c)/(h)/(i). Usually only clearly unnecessary data can be erased. |
| Article 18 restriction | Patient may restrict for legal claims; clinical operational use generally continues. |
| Article 20 portability | Increasingly supported by EHDS and FHIR. |
| Article 21 objection | Limited where processing is for healthcare or public-health purposes. |
| Article 22 automated decisions | Triage algorithms, eligibility decisions, and clinical decision-support require Article 22 analysis. Medical devices subject to MDR/IVDR overlay. |

### 17. Breach in healthcare

Health data breach is high-severity by definition. Article 34 communication is almost always required. ENISA scoring will routinely score "high" or "very high" for any breach affecting clinical content.

### 18. KVKK comparator

KVKK Article 6 treats health and sexual life data as special category. KVKK Communiqué on Health Data sets out specific safeguards. Kişisel Sağlık Verileri Yönetmeliği (Regulation on Personal Health Data) provides additional structure.

### 19. Documentation

For each healthcare processing activity:

- ROPA entry with Article 6 + 9 bases, retention, recipients, transfers.
- DPIA for clinical IT, EHR, telemedicine, research.
- Article 28 contracts with cloud and SaaS processors.
- Member State specific authorisations and ethics committee approvals.
- Clinical-records retention schedule by document type and patient group.
- Information notices to patients (Article 13) at point of registration and updated as services change.
- Breach scenarios pre-played for healthcare-specific patterns (ransomware on clinical systems, lost EHR-enabled tablet).

---

## Türkçe

### 1. Tanım

GDPR Madde 4(15), sağlığa ilişkin veriyi, sağlık hizmetlerinin sağlanması da dahil olmak üzere, bir gerçek kişinin fiziksel veya zihinsel sağlığına ilişkin ve sağlık durumu hakkında bilgi ortaya çıkaran kişisel veri olarak tanımlar.

Tanım geniştir. Sigorta sağlık anketleri, fitness uygulama verileri, mesleki tıp verileri, ruh sağlığı destek kayıtları, aşı kayıtları ve tıbbi nedenlerle belirtilen diyet gereksinimleri nitelik kazanır.

### 2. Genetik veri ve biyometrik veri

Genetik veri (Madde 4(13)) ve benzersiz tanımlama için kullanılan biyometrik veri (Madde 4(14)) kendi hükümleriyle ayrı özel kategorilerdir.

### 3. Madde 9(2) altında hukuki temeller

Sağlık verisi için temel Madde 9(2) temelleri:

(a) **Açık rıza** — yüksek standart.

(h) **Önleyici veya mesleki tıp, çalışma kapasitesinin değerlendirilmesi, tıbbi teşhis, sağlık veya sosyal bakım veya tedavinin sağlanması, sağlık veya sosyal bakım sistem ve hizmetlerinin yönetimi**, AB/ÜD hukuku veya bir sağlık uzmanıyla sözleşme temelinde. Klinik bakım için ana çalışma atı.

(i) **Kamu sağlığı alanındaki kamu yararı nedenleri**.

(j) **Madde 89(1)'e uygun kamu yararı, bilimsel veya tarihsel araştırma, istatistik için arşivleme**.

Madde 9(3), (h) altındaki işlemenin AB/ÜD hukuku altındaki mesleki gizlilik yükümlülüğüne tabi bir sağlık uzmanı veya başka bir kişi tarafından veya sorumluluğunda yapılmasını şart koşar.

### 4. Madde 6 hukuki temeli (her zaman gerekli)

Madde 9 özel kategori yasağını açar; Madde 6 hâlâ uygulanmalıdır. Klinik bakım için yaygın eşleştirme, temel işleme için Madde 6(1)(c) (yasal yükümlülük) veya 6(1)(b) (hasta ile sözleşme) ve özel kategori boyutu için Madde 9(2)(h)'dir.

### 5. Mesleki gizlilik yükümlülüğü

Madde 9(3) ve karşılık gelen Üye Devlet hukuku gizlilik dayatır. Mesleki gizlilik yalnızca bir gizlilik duruşu değildir; birçok Devlette cezai yaptırımla desteklenen yasal bir görevdir.

### 6. Sağlık işlemesindeki roller

| Rol | Tipik konum |
|-----|-------------|
| Hastane, klinik, aile hekimi muayenehanesi | Hasta bakımı için veri sorumlusu |
| Hastanede çalışan bağımsız uzman | Genellikle ortak veri sorumlusu |
| Halk sağlığı yetkilisi | İzleme, kayıtlar için veri sorumlusu |
| Sağlık sigortacısı | Talep işleme için veri sorumlusu |
| Farmasötik üreticisi (pazarlama sonrası) | Farmakovijilans için veri sorumlusu |
| Hastane bulut sağlayıcısı | Veri işleyen (Madde 28) |
| Telemetri ile tıbbi cihaz üreticisi | Güvenlik için veri sorumlusu |
| Klinik araştırma sponsoru | Deneme için veri sorumlusu |
| Sözleşme araştırma kuruluşu (CRO) | Sponsor için veri işleyen |

### 7. Elektronik sağlık kayıtları

EHR şunları gerektirir:

- Standartlar üzerinden birlikte çalışabilirlik (HL7 FHIR; openEHR; SNOMED CT; LOINC).
- Ayrıntılı role dayalı erişim.
- Denetim izi ile cam-kırma prosedürü.
- Hasta erişimi.
- Her erişimin denetim günlüğü.
- Klinik kayıtların kurcalamayı belirgin saklanması.
- Klinik kayıt saklama kurallarına hizalı uzun saklama (genellikle 10-30 yıl).

### 8. Avrupa Sağlık Veri Alanı (Düzenleme (AB) 2025/327)

EHDS Düzenlemesi (2025'ten itibaren yürürlükte, aşamalı olarak uygulanır) şunları yaratır:

- Hastalara EHR'lerine erişim ve sınır ötesi paylaşım için gelişmiş haklar veren birincil kullanım çerçevesi.
- Araştırma, yenilik, politika oluşturma ve düzenleme için sağlık verisine erişime izin veren ikincil kullanım çerçevesi.
- Avrupa Elektronik Sağlık Kaydı Değişim Formatına dayalı zorunlu birlikte çalışabilirlik.

### 9. HL7 FHIR

HL7 FHIR baskın birlikte çalışabilirlik standardıdır. Mahremiyet hususları:

- Kaynaklar (Hasta, Gözlem, İlaçRequest vb.) kişisel veri ve tanımlayıcılar taşır.
- SMART on FHIR yaygın bir yetkilendirme örüntüsüdür (OAuth 2.0 + OpenID Connect).
- Toplu veri ihracatı ayrı bir kapsam ve risk profiline sahiptir.

### 10. Araştırma işlemesi

Madde 9(2)(j) ve Madde 89 altında araştırma:

- Üye Devlet hukuku genellikle ek gereksinimler belirtir.
- Madde 89 tarafından gerekli takma adlandırma ve diğer güvenceler.
- Madde 9(2)(j) etik incelemeyi yerinden etmez.

### 11. Genetik veri

Madde 4(13) genetik veri iki katlı korunur.

- Aile uygunluğu.
- Uzun kuyruk sonuçları.
- Araştırma ile klinik kullanım için rıza.
- Doğrudan tüketiciye genetik test.

### 12. Sigorta ve istihdam

Sigortacılar tarafından işlenen sağlık verisi spesifik Üye Devlet hukuku yetkilendirmeleri gerektirir. Sağlık verisine işveren erişimi son derece kısıtlıdır.

### 13. Telemedikal ve bağlı cihazlar

- Hasta ve klinisyen farklı ülkelerde olduğunda sınır ötesi işleme.
- Konsültasyonların kaydedilmesi: ayrı rıza katmanı.
- Bağlı tıbbi cihazlar: cihaz üreticisi telemetri için veri sorumlusudur.

### 14. Dijital sağlık uygulamaları

İyilik ve dijital terapötik uygulamaları:

- "Sağlık verisi" geniş kapsamda uygulanır.
- Uygulama mağazası gizlilik etiketleri veri akışlarını doğru yansıtmalıdır.
- Özel kategori veri işleme rızası açık rıza standardını karşılamalıdır.
- VKD zorunlu.

### 15. Kamu sağlığı

Madde 9(2)(i) kamu sağlığını kapsar.

### 16. İlgili kişi hakları özellikleri

| Hak | Sağlık verisi özellikleri |
|-----|-------------------------|
| Madde 15 erişim | Hasta tıbbi kaydının bir kopyasına hak sahibidir. |
| Madde 16 düzeltme | Klinik görüş genellikle hasta tarafından "düzeltilmez"; olgusal hatalar düzeltilir. |
| Madde 17 silme | Madde 17(3)(b)/(c)/(h)/(i) altındaki saklama yükümlülükleriyle ağır şekilde sınırlandırılır. |
| Madde 18 kısıtlama | Hasta hukuki talepler için kısıtlayabilir. |
| Madde 20 taşınabilirlik | EHDS ve FHIR tarafından giderek daha fazla destekleniyor. |
| Madde 21 itiraz | Sağlık veya kamu sağlığı amaçları için işleme yapıldığında sınırlı. |
| Madde 22 otomatik kararlar | Triyaj algoritmaları, uygunluk kararları ve klinik karar destek Madde 22 analizi gerektirir. |

### 17. Sağlık hizmetlerinde ihlal

Sağlık verisi ihlali tanım gereği yüksek şiddetlidir. Madde 34 iletişimi neredeyse her zaman gereklidir.

### 18. KVKK karşılaştırması

KVKK Madde 6 sağlık ve cinsel hayat verisini özel kategori olarak değerlendirir. Kişisel Sağlık Verileri Yönetmeliği ek yapı sağlar.

### 19. Belgeleme

Her sağlık işleme faaliyeti için:

- Madde 6 + 9 temelleri, saklama, alıcılar, aktarımlarla ROPA girişi.
- Klinik BT, EHR, telemedikal, araştırma için VKD.
- Bulut ve SaaS veri işleyenleriyle Madde 28 sözleşmeleri.
- Üye Devlet özel yetkilendirmeleri ve etik komite onayları.
- Belge türü ve hasta grubuna göre klinik kayıt saklama programı.
- Hastalara bilgilendirme bildirimleri (Madde 13).
- Sağlık hizmetlerine özgü örüntüler için önceden oynatılmış ihlal senaryoları.
