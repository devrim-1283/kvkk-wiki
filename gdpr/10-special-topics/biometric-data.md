---
title:
  en: "Biometric Data Processing"
  tr: "Biyometrik Veri İşleme"
section: "10-special-topics"
document_id: "ST-BIO-001"
owner: "DPO Office / Security Engineering"
classification: "Internal"
version: "1.0"
last_review: "2026-05-08"
next_review: "2027-05-08"
language: ["en", "tr"]
references:
  - "GDPR Art. 4(14) — Definition of biometric data"
  - "GDPR Art. 9(1) — Special categories of personal data"
  - "GDPR Art. 9(2)(a), (b), (g), (h), (i), (j) — Bases for processing"
  - "GDPR Recital 51 — Biometric for unique identification"
  - "GDPR Art. 35 — DPIA"
  - "EDPB Guidelines 5/2022 on the use of facial recognition technology in the area of law enforcement"
  - "EDPB Guidelines 3/2019 on processing of personal data through video devices (Section 5)"
  - "Article 29 WP — WP193 (Opinion 3/2012 on developments in biometric technologies)"
  - "CNIL — Reference framework on biometric access control in the workplace (2019, updated)"
  - "ICO — Biometric data guidance"
  - "EU AI Act — Articles 5(1)(c), 5(1)(g), 5(1)(h)"
---

## English

### 1. Definition

Article 4(14) GDPR defines biometric data as personal data resulting from specific technical processing relating to the physical, physiological, or behavioural characteristics of a natural person, which allow or confirm the unique identification of that natural person, such as facial images or dactyloscopic data.

The legal trigger of Article 9 special-category status is the *purpose* of unique identification, not the data type alone (Recital 51). A photograph used illustratively is not Article 9 data; the same photograph fed into a face-matching algorithm to identify the person becomes Article 9 data when the algorithm operates.

### 2. Categories

| Category | Examples |
|----------|---------|
| Physical | Fingerprint, palm print, iris, retina, vein pattern, face geometry, hand geometry, ear shape |
| Physiological | DNA, voiceprint (when used as biometric), heartbeat |
| Behavioural | Keystroke dynamics, gait, signature dynamics, mouse-movement biometrics |

Behavioural biometrics are recognised by EDPB and SAs but with case-by-case analysis: continuous keystroke biometrics in workplace are typically Article 9 special category when used for identity assurance.

### 3. When is biometric data Article 9 special category?

Article 9(1) catches biometric data "for the purpose of uniquely identifying a natural person". Recital 51 confirms photographs are not automatically Article 9; only when processed through a specific technical means allowing unique identification.

The split:

| Use | Article 9 status |
|-----|-----------------|
| Photograph in HR file for identification by a human | Not Article 9 unless paired with biometric technology |
| Same photograph in a face-matching system for door access | Article 9 |
| Voice recording of a customer support call | Not Article 9 (call quality) |
| Same voice recording analysed to authenticate identity | Article 9 |
| Fingerprint used for time-and-attendance | Article 9 |
| Fingerprint stored as evidence of consent (one-time) | Article 9 |
| CCTV recording of entrance | Generally not Article 9 |
| Same CCTV with facial recognition layered on top | Article 9 (the recognition output) |

### 4. Lawful bases under Article 9(2)

Processing of biometric data is prohibited unless an Article 9(2) exception applies:

| Article 9(2) | Provision | Practicality for biometric |
|-------------|-----------|---------------------------|
| (a) | Explicit consent | Possible for opt-in biometrics in customer settings; problematic for employees due to consent imbalance |
| (b) | Necessary for employment, social security, social protection law | Only where Member State law specifically authorises; rare for routine biometric access |
| (c) | Vital interests where data subject incapable of consent | Rare; medical emergencies |
| (d) | Legitimate activities of foundations / associations / NGOs | Limited |
| (e) | Made manifestly public by data subject | Narrow |
| (f) | Establishment, exercise, defence of legal claims | Forensic |
| (g) | Substantial public interest, on basis of EU/MS law, proportionate, safeguards | Public-sector identification, anti-money-laundering, border control |
| (h) | Preventive or occupational medicine, healthcare | Healthcare biometric authentication for clinicians |
| (i) | Public health | Pandemic-related identification |
| (j) | Archiving / scientific research / statistics, with safeguards | Research biobanks |

Practical reality: in private-sector workplace and consumer contexts, the realistic bases are (a) explicit consent (with strict freedom-of-consent test) and (g) substantial public interest where Member State law underwrites it. (b) employment is narrow and rarely covers private-employer biometric attendance.

### 5. EDPB 5/2022 and the law enforcement context

EDPB Guidelines 5/2022 address facial recognition by law enforcement. While addressed to the LED (Directive 2016/680), the analytical framework — necessity, proportionality, least intrusive — informs all biometric deployments. Key principles:

- Real-time biometric identification in public spaces is the most intrusive form.
- Even retrospective identification needs strong justification.
- Mass population enrolment is presumptively excessive.
- Independent oversight is necessary.

### 6. Mandatory DPIA

Biometric processing is on the EDPB's "must DPIA" list (EDPB 4/2017 nine criteria, sufficient if two apply, biometric routinely satisfies multiple). Member State SAs (CNIL, AEPD, Garante, BfDI, KVKK) publish blacklists where biometric DPIAs are mandatory.

The DPIA must address:
- the specific biometric modality and why it was chosen;
- the alternative-least-intrusive analysis (Section 7);
- whether template or raw is used and the rationale (Section 8);
- enrolment process and revocation;
- error rates (FAR, FRR, equal error rate);
- demographic bias analysis;
- retention and disposal;
- access controls;
- security architecture (where keys live, where matching occurs).

### 7. Alternative least-intrusive assessment

Before any biometric deployment, the controller assesses whether a less-intrusive alternative would meet the operational need. The assessment is documented:

| Need | Less-intrusive alternatives |
|------|---------------------------|
| Workplace door access | Card, PIN, mobile-app token, FIDO2 key |
| Workplace time and attendance | Card, app check-in, geofencing, manager attestation |
| Customer authentication | Password + MFA, app push, hardware token, behavioural risk scoring |
| Border control | Document inspection, e-passport chip read |
| Healthcare clinician access | Smart card with PIN, mobile push |
| Sports stadium access | Ticket scan, mobile wallet |

If a less-intrusive alternative meets the need, biometric is not lawful — the necessity component of proportionality fails. CNIL has consistently rejected biometric attendance on this basis (numerous decisions 2018–2024). EDPB 3/2019 §73 endorses this analysis.

### 8. Template vs. raw

Where biometric processing is justified, processing template data is far less intrusive than raw images. A template is a one-way mathematical representation; reversing to the original image is computationally infeasible. Practical patterns:

- **On-device template, never centralised**: Apple Face ID model. The biometric never leaves the device; the controller only learns "match passed".
- **Encrypted template on smart card held by user**: card carries enrolment; matching at terminal; no central database.
- **Centralised encrypted template database**: higher risk; requires strong key management, segregation, and DPIA-approved safeguards.
- **Raw image storage**: presumptively unlawful unless strict and specific necessity proven.

The DPIA must justify the chosen architecture against the user-controlled template baseline.

### 9. Demographic fairness and bias

Biometric systems exhibit accuracy variation across demographic groups (notably age, gender, skin tone). NIST FRVT studies have repeatedly demonstrated this. Article 5(1)(d) accuracy and Article 22 anti-discrimination overlay GDPR with fairness obligations.

The controller:
- requests vendor performance documentation by demographic group;
- conducts an internal validation against the actual user population;
- monitors error rates in production by group;
- has a documented escalation when error patterns emerge;
- ensures non-biometric fallback exists for any user the system fails to enrol or authenticate.

### 10. Workplace biometric — practical guidance

CNIL's reference framework on workplace biometric access control (2019, updated) is the European reference. Key constraints:

- Permitted only with documented strict need (high-security area, regulated environment, safety-critical access).
- Template stored under user control (smart card or device) preferred.
- Never used for time-and-attendance (CNIL repeatedly rejects).
- Works council consultation.
- DPIA.
- Employees must be told a non-biometric alternative is available without penalty.

### 11. Customer biometric (mobile, banking)

For customer-facing biometric (mobile banking face/fingerprint, online identity verification):

- The operating-system biometric (Face ID, Android BiometricPrompt) keeps the biometric on-device; the controller never receives biometric data, only a binary signal. This is the safest pattern.
- KYC/onboarding face-matching where the controller compares a live selfie to a document photo is biometric processing under Article 9; the controller must have a clear basis (consent, often complemented by AML/CFT obligations under Member State law).
- Liveness detection that does not store templates is less intrusive than match-and-store.
- Retention: the matching artefact (selfie + document photo + match score) should be retained only as long as legally necessary; AML laws often impose 5–10 years.

### 12. EU AI Act intersections

- Real-time remote biometric identification in publicly accessible spaces by law enforcement is prohibited subject to narrow exceptions (Article 5(1)(h)).
- Predictive policing based on profiling is prohibited (Article 5(1)(d)).
- Untargeted scraping of facial images from internet or CCTV to build databases is prohibited (Article 5(1)(e)).
- Emotion recognition in workplace and education is prohibited (Article 5(1)(f)).
- Biometric categorisation systems that infer sensitive attributes (race, political opinion, religion, sexual orientation) are prohibited (Article 5(1)(g)).
- Biometric identification systems are typically high-risk (Annex III), triggering AI Act obligations in addition to GDPR.

### 13. Children's biometric data

Particular caution. Schools using biometric attendance or canteen payment have been subject to ICO and CNIL enforcement. Where biometric is used at all, parental consent is required for under-16 (or higher per Member State), with a non-biometric alternative for any family that prefers.

### 14. Documentation pack

For each biometric deployment, the controller maintains:

- DPIA;
- Article 9(2) basis and supporting documentation;
- Alternative-least-intrusive assessment;
- Vendor due diligence (technology, accuracy across demographics, security architecture, data flow);
- Architecture diagram (where templates live, where matching happens, key management);
- Enrolment script (how the data subject is informed, how consent is captured);
- Withdrawal / unenrolment procedure;
- Audit log of access to template store;
- Incident plan covering biometric breach (which under EDPB 9/2022 typically triggers Article 34 communication);
- Performance monitoring.

### 15. Breach considerations

A breach of biometric data has unique severity: biometrics cannot be re-issued. Article 34 communication is almost always required. The DPIA explicitly acknowledges this and reflects it in the architecture (e.g. encrypt with HSM, derive irreversible templates, never store raw).

### 16. KVKK comparator

KVKK Article 6 treats biometric and genetic data as special category, with explicit consent or specific Article 6(3) exceptions required. KVKK Board has issued decisions consistent with EDPB analysis on workplace biometric attendance.

### 17. Closure principle

The default for biometric data is "no". The default is overcome only by a documented case showing necessity, proportionality, and the absence of less-intrusive alternatives, with strong technical safeguards and an Article 9(2) basis. Every biometric processing the controller operates is on the controller's biometric register, reviewed annually.

---

## Türkçe

### 1. Tanım

GDPR Madde 4(14), biyometrik veriyi, bir gerçek kişinin fiziksel, fizyolojik veya davranışsal özelliklerine ilişkin spesifik teknik işlemeden kaynaklanan ve o gerçek kişinin benzersiz tanımlanmasına izin veren veya bunu teyit eden kişisel veri olarak tanımlar (yüz görüntüleri veya daktiloskopik veri gibi).

Madde 9 özel kategori durumunun yasal tetikleyicisi, yalnızca veri türü değil, benzersiz tanımlama *amacıdır* (Resital 51). Açıklayıcı olarak kullanılan bir fotoğraf Madde 9 verisi değildir; aynı fotoğraf kişiyi tanımlamak için yüz eşleştirme algoritmasına beslendiğinde algoritma çalıştığında Madde 9 verisi olur.

### 2. Kategoriler

| Kategori | Örnekler |
|----------|----------|
| Fiziksel | Parmak izi, avuç içi, iris, retina, damar deseni, yüz geometrisi, el geometrisi, kulak şekli |
| Fizyolojik | DNA, ses izi (biyometrik olarak kullanıldığında), kalp atışı |
| Davranışsal | Tuş vuruşu dinamiği, yürüyüş, imza dinamiği, fare hareketi biyometriği |

### 3. Biyometrik veri ne zaman Madde 9 özel kategoridir?

Madde 9(1), biyometrik veriyi "bir gerçek kişiyi benzersiz şekilde tanımlamak amacıyla" kapsar. Resital 51, fotoğrafların otomatik olarak Madde 9 olmadığını teyit eder; yalnızca benzersiz tanımlamaya izin veren spesifik bir teknik araçla işlendiğinde.

| Kullanım | Madde 9 durumu |
|----------|---------------|
| İK dosyasında insan tarafından tanımlama için fotoğraf | Biyometrik teknolojiyle eşleştirilmedikçe Madde 9 değil |
| Aynı fotoğraf kapı erişimi için yüz eşleştirme sisteminde | Madde 9 |
| Müşteri destek aramasının sesli kaydı | Madde 9 değil (çağrı kalitesi) |
| Aynı sesli kayıt kimliği doğrulamak için analiz edildi | Madde 9 |
| Zaman ve devam için kullanılan parmak izi | Madde 9 |
| Tek seferlik rıza kanıtı olarak saklanan parmak izi | Madde 9 |
| Girişin CCTV kaydı | Genellikle Madde 9 değil |
| Yüz tanıma katmanlı aynı CCTV | Madde 9 (tanıma çıktısı) |

### 4. Madde 9(2) altında hukuki temeller

Biyometrik veri işleme bir Madde 9(2) istisnası uygulanmadığı sürece yasaktır:

| Madde 9(2) | Hüküm | Biyometrik için pratiklik |
|-----------|-------|--------------------------|
| (a) | Açık rıza | Müşteri ortamlarında opt-in için mümkün; çalışanlar için rıza dengesizliği nedeniyle sorunlu |
| (b) | İstihdam, sosyal güvenlik için gerekli | Yalnızca Üye Devlet hukuku özellikle yetkilendirdiğinde |
| (c) | Hayati menfaatler | Nadir; tıbbi acil durumlar |
| (d) | Vakıfların / derneklerin / STK'ların meşru faaliyetleri | Sınırlı |
| (e) | İlgili kişi tarafından açıkça kamuya açık hale getirilmiş | Dar |
| (f) | Hukuki taleplerin kurulması, kullanılması, savunulması | Adli |
| (g) | Önemli kamu yararı, AB/ÜD hukuku temelinde | Kamu sektörü tanımlama, AML, sınır kontrolü |
| (h) | Önleyici veya mesleki tıp, sağlık | Klinisyenler için sağlık biyometrik kimlik doğrulama |
| (i) | Kamu sağlığı | Salgın ile ilgili tanımlama |
| (j) | Arşivleme / bilimsel araştırma / istatistik | Araştırma biyobankaları |

### 5. EDPB 5/2022 ve kolluk kuvvetleri bağlamı

EDPB 5/2022 Rehberi kolluk tarafından yüz tanımayı ele alır. LED'e (Direktif 2016/680) yöneltilmiş olsa da analitik çerçeve — gereklilik, orantılılık, en az müdahaleci — tüm biyometrik dağıtımlara bilgi sağlar.

### 6. Zorunlu VKD

Biyometrik işleme EDPB'nin "VKD yapılmalı" listesindedir.

VKD şunları ele almalıdır:
- spesifik biyometrik modalite ve neden seçildiği;
- en az müdahaleci alternatif analizi (Bölüm 7);
- şablon mu yoksa ham mı kullanıldığı ve gerekçesi (Bölüm 8);
- kayıt süreci ve iptal;
- hata oranları (FAR, FRR, eşit hata oranı);
- demografik önyargı analizi;
- saklama ve imha;
- erişim kontrolleri;
- güvenlik mimarisi.

### 7. Alternatif en az müdahaleci değerlendirme

| İhtiyaç | Daha az müdahaleci alternatifler |
|---------|--------------------------------|
| İşyeri kapı erişimi | Kart, PIN, mobil uygulama tokeni, FIDO2 anahtarı |
| İşyeri zaman ve devam | Kart, uygulama check-in, coğrafi bölge, yönetici tasdikli |
| Müşteri kimlik doğrulama | Parola + MFA, uygulama push, donanım tokeni |
| Sınır kontrolü | Belge incelemesi, e-pasaport çip okuma |
| Sağlık klinisyen erişimi | PIN'li akıllı kart, mobil push |
| Spor stadyumu erişimi | Bilet tarama, mobil cüzdan |

CNIL bu temelde biyometrik devam kayıtlarını sürekli olarak reddetmiştir.

### 8. Şablon vs. ham

Biyometrik işleme haklı kılındığında, şablon verilerini işlemek ham görüntüleri işlemekten çok daha az müdahalecidir.

- **Cihazda şablon, hiç merkezileştirilmemiş**: Apple Face ID modeli.
- **Kullanıcı tarafından tutulan akıllı karttaki şifrelenmiş şablon**.
- **Merkezileştirilmiş şifrelenmiş şablon veritabanı**: daha yüksek risk.
- **Ham görüntü saklama**: kesin gereklilik kanıtlanmadıkça yasaklı varsayılır.

### 9. Demografik adillik ve önyargı

Biyometrik sistemler demografik gruplar arasında doğruluk farklılığı sergiler.

### 10. İşyeri biyometrik — pratik rehberlik

CNIL'in işyeri biyometrik erişim kontrolü referans çerçevesi (2019, güncellenmiş) Avrupa referansıdır.

### 11. Müşteri biyometrik (mobil, bankacılık)

İşletim sistemi biyometriği (Face ID, Android BiometricPrompt) biyometriği cihazda tutar; veri sorumlusu hiç biyometrik veri almaz, yalnızca ikili sinyal alır. Bu en güvenli örüntüdür.

### 12. AB AI Yasası kesişimleri

- Kolluk tarafından kamuya açık alanlarda gerçek zamanlı uzak biyometrik tanımlama dar istisnalara tabi olarak yasaktır (Madde 5(1)(h)).
- Profillemeye dayalı öngörücü polislik yasaktır (Madde 5(1)(d)).
- Veritabanları oluşturmak için internetten veya CCTV'den hedefsiz yüz görüntüsü kazıma yasaktır (Madde 5(1)(e)).
- İşyerinde ve eğitimde duygu tanıma yasaktır (Madde 5(1)(f)).
- Hassas özelliklerden çıkarımda bulunan biyometrik kategorizasyon yasaktır (Madde 5(1)(g)).

### 13. Çocukların biyometrik verisi

Özel dikkat. Biyometrik devam kullanan okullar ICO ve CNIL yaptırımına tabi olmuştur.

### 14. Belgeleme paketi

Her biyometrik dağıtım için, veri sorumlusu sürdürür:

- VKD;
- Madde 9(2) temeli ve destekleyici belgeler;
- Alternatif en az müdahaleci değerlendirme;
- Tedarikçi durum tespiti;
- Mimari diyagramı;
- Kayıt komut dosyası;
- Geri çekme / kayıt iptali prosedürü;
- Şablon deposuna erişim denetim günlüğü;
- Olay planı;
- Performans izleme.

### 15. İhlal hususları

Biyometrik veri ihlalinin benzersiz şiddeti vardır: biyometrikler yeniden çıkarılamaz. Madde 34 iletişimi neredeyse her zaman gereklidir.

### 16. KVKK karşılaştırması

KVKK Madde 6 biyometrik ve genetik veriyi açık rıza veya spesifik Madde 6(3) istisnaları gerektirerek özel kategori olarak değerlendirir.

### 17. Kapanış ilkesi

Biyometrik veri için varsayılan "hayır"dır. Varsayılan yalnızca gerekliliği, orantılılığı ve daha az müdahaleci alternatiflerin yokluğunu gösteren belgelenmiş bir vakayla aşılır.
