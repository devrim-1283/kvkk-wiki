---
title:
  en: "Landmark CJEU Judgments — Operational Reference"
  tr: "Onemli AAD Kararlari — Operasyonel Referans"
section: "12-legal-archive"
owner: "Legal / DPO"
version: "1.0"
last_review: "2026-05-08"
next_review: "2026-11-08"
classification: "Internal"
languages: ["en", "tr"]
keywords:
  en: ["CJEU", "case law", "Schrems", "Costeja", "Planet49", "Wirtschaftsakademie"]
  tr: ["AAD", "icithat", "Schrems", "Costeja", "Planet49", "Wirtschaftsakademie"]
---

## English

# Landmark CJEU Judgments

This reference compiles the most operationally significant Court of Justice of the EU (CJEU) judgments shaping GDPR interpretation. Each case is summarized with citation, holding, and operational impact.

### How to read this catalogue

| Field | Meaning |
|-------|---------|
| Case | Common name + case number (C-XXX/YY) |
| Year | Judgment year |
| Holding | One-paragraph summary of legal holding |
| Operational impact | Direct consequence for controllers / processors |
| Wiki link | Where the case is operationalised |

### International transfers

#### Schrems I — Maximillian Schrems v Data Protection Commissioner (C-362/14)

- **Year:** 2015.
- **Holding:** Invalidated the US Safe Harbor adequacy decision (2000/520/EC). Adequacy requires "essentially equivalent" protection. SAs must investigate complaints despite Commission decisions.
- **Operational impact:** Established the standard of review for adequacy decisions. Foundation for Schrems II.
- **Wiki link:** `07-international-transfers/adequacy.md`.

#### Schrems II — Data Protection Commissioner v Facebook Ireland and Maximillian Schrems (C-311/18)

- **Year:** 2020.
- **Holding:** Invalidated the EU-US Privacy Shield. SCCs remain valid but require case-by-case assessment of recipient country law. Where law fails the "European Essential Guarantees," supplementary measures or transfer suspension required.
- **Operational impact:** Mandates Transfer Impact Assessments (TIA), supplementary measures (encryption with EU-held keys, pseudonymisation, contractual additions). EDPB Recommendations 01/2020 operationalize the ruling. Successor framework: EU-US Data Privacy Framework (DPF, July 2023, Implementing Decision 2023/1795).
- **Wiki link:** `07-international-transfers/safeguards.md`.

### Right to be forgotten and search engines

#### Google Spain SL and Google Inc. v AEPD and Mario Costeja González (C-131/12)

- **Year:** 2014.
- **Holding:** Search engines are controllers. Data subjects have a right to request delisting under former Article 12(b) and 14(a) of Directive 95/46/EC, balanced against public interest in access.
- **Operational impact:** Foundation of Article 17 right to erasure and Article 21 right to object as applied to search engines. Triggered Article 17(3) exceptions (freedom of expression, public interest archives).
- **Wiki link:** `09-data-subject-rights/erasure.md`.

#### GC and Others v CNIL (C-136/17)

- **Year:** 2019.
- **Holding:** Search engine delisting obligations apply to special category data with stronger weighting toward delisting absent overriding public interest.
- **Operational impact:** Tightened Article 9 in delisting balancing tests.

#### Google v CNIL (C-507/17)

- **Year:** 2019.
- **Holding:** Right to be forgotten generally applies only to EU search engine versions. Member states may extend further by law.
- **Operational impact:** Geographic scope of delisting.

### Consent and cookies

#### Planet49 — Bundesverband der Verbraucherzentralen v Planet49 (C-673/17)

- **Year:** 2019.
- **Holding:** Pre-ticked checkboxes do not constitute valid consent under ePrivacy Directive 2002/58/EC and GDPR Article 4(11). Consent must be active, specific, informed, freely given. Information about cookie duration and third-party access required.
- **Operational impact:** Cookie banners must offer reject equally prominent to accept; no pre-ticking; granular per purpose; specific information.
- **Wiki link:** `03-transparency-consent/consent.md`.

#### Orange Romania v ANSPDCP (C-61/19)

- **Year:** 2020.
- **Holding:** Consent obtained via standardised contracts where data subject ticks a box can be valid only if active and informed; controller bears burden of proof.
- **Operational impact:** Reinforces Article 7(1) demonstrability.

### Joint controllership

#### Wirtschaftsakademie Schleswig-Holstein (C-210/16)

- **Year:** 2018.
- **Holding:** Operator of a Facebook fan page is a joint controller with Facebook for processing of visitor data (Insights).
- **Operational impact:** Triggered widespread review of social media presence by organizations. Article 26 joint controller arrangements required. Practical impact on plug-ins, embedded content, analytics.
- **Wiki link:** `06-organizational-measures/joint-controllers.md`.

#### Fashion ID (C-40/17)

- **Year:** 2019.
- **Holding:** Website embedding the Facebook "Like" button is a joint controller for collection and transmission of visitor data to Facebook (but not subsequent processing by Facebook).
- **Operational impact:** Embedded social plug-ins require explicit consent before loading; joint controllership regime.

#### Jehovan todistajat (C-25/17)

- **Year:** 2018.
- **Holding:** Religious community is a joint controller with members for door-to-door note-taking on residents.
- **Operational impact:** Joint controllership scope is broad — any party determining purpose and means.

### Personal data scope

#### Lindqvist (C-101/01)

- **Year:** 2003.
- **Holding:** Naming individuals on a personal webpage is processing of personal data within Directive 95/46/EC scope.
- **Operational impact:** Foundational on broad scope of "personal data."

#### Breyer v Bundesrepublik Deutschland (C-582/14)

- **Year:** 2016.
- **Holding:** Dynamic IP addresses are personal data when controller has reasonable means to identify the user.
- **Operational impact:** IP addresses and online identifiers are personal data — affects log retention, analytics, advertising.

#### Nowak v Data Protection Commissioner (C-434/16)

- **Year:** 2017.
- **Holding:** Examination scripts and examiner's comments are personal data.
- **Operational impact:** Broad personal data interpretation in education and HR.

### Data subject rights — judicial extensions

#### Bara v Casa Naţionala de Asigurari de Sanatate (C-201/14)

- **Year:** 2015.
- **Holding:** Public administration data transfers between authorities require informing data subjects (Article 14 transparency under Directive 95/46).
- **Operational impact:** Cross-public-authority data sharing must be transparent.

#### Buivids v Datu valsts inspekcija (C-345/17)

- **Year:** 2019.
- **Holding:** Recording and publishing video of police interrogation may fall under journalistic exemption depending on facts; controller-by-controller analysis.
- **Operational impact:** Tightens Article 85 journalism balancing.

#### Pankki S (C-579/21)

- **Year:** 2023.
- **Holding:** Right of access (Article 15) requires controller to provide information identifying who accessed data, where the data subject's own employee processes the data.
- **Operational impact:** Access logs must be available for access requests in employment scenarios.

#### Österreichische Post (UI v) (C-300/21)

- **Year:** 2023.
- **Holding:** Article 82 non-material damage requires actual damage proof; no de minimis seriousness threshold.
- **Operational impact:** Compensation claims for distress, anxiety viable.

### Surveillance and law enforcement interplay

#### La Quadrature du Net and Others (Joined Cases C-511/18, C-512/18, C-520/18)

- **Year:** 2020.
- **Holding:** General and indiscriminate retention of traffic and location data by electronic communications providers is contrary to EU law absent serious threat to national security; targeted retention permissible under safeguards.
- **Operational impact:** Limits ePrivacy data retention by member states; affects cooperation with law enforcement.

#### Privacy International (C-623/17) and SpaceNet/Telekom Deutschland (C-793/19, C-794/19)

- **Year:** 2020 and 2022.
- **Holding:** Reaffirmed limits on bulk data retention and access by intelligence services.
- **Operational impact:** Inputs into Schrems II essential equivalence assessments.

### Lead supervisory authority

#### Facebook Ireland Limited v Belgian DPA (C-645/19)

- **Year:** 2021.
- **Holding:** SAs other than the lead SA may bring proceedings before national courts for cross-border processing under specified conditions (Article 58, 60-66).
- **Operational impact:** One-stop-shop is not exclusive; concerned SAs retain enforcement competence in defined situations.

### Article 22 — automated decision-making

#### SCHUFA Holding (C-634/21)

- **Year:** 2023.
- **Holding:** Automated credit scoring resulting in a probability value that significantly drives bank decisions is itself an Article 22(1) automated decision.
- **Operational impact:** Reach of Article 22 extends to scoring upstream of human review where the score effectively determines outcome.

### Records of processing and accountability

#### Deutsche Wohnen / Berlin SA (C-807/21)

- **Year:** 2023.
- **Holding:** Article 83 fines may be imposed on a legal entity for personal data infringements directly without first attributing the infringement to a specific natural person; "undertaking" concept (EU competition law) applies.
- **Operational impact:** Corporate liability is direct; group turnover may be relevant for fine cap.

### National courts and CJEU referrals — recent themes

The CJEU continues to receive referrals on:

- Sensitive data inferences from processing (Article 9).
- Legitimate interests and direct marketing.
- Compensation thresholds under Article 82.
- Data retention by ISPs.
- AI training data and Article 5(1)(a).

### Citation conventions

Cite as: "Case C-XXX/YY [Common Name], judgment of [date], EU:C:YYYY:XXX." For Advocate General opinions, append "Opinion of AG [name], delivered [date]."

### Wiki cross-link summary

| Topic | Cases | Wiki section |
|-------|-------|--------------|
| International transfers | Schrems I, Schrems II | `07-international-transfers/` |
| Right to be forgotten | Costeja, GC and Others, Google v CNIL | `09-data-subject-rights/erasure.md` |
| Consent | Planet49, Orange Romania | `03-transparency-consent/consent.md` |
| Joint controllership | Wirtschaftsakademie, Fashion ID, Jehovan | `06-organizational-measures/joint-controllers.md` |
| Personal data scope | Lindqvist, Breyer, Nowak | `01-core-concepts/definitions.md` |
| DSR — access | Pankki S | `09-data-subject-rights/access.md` |
| Compensation | Österreichische Post | `11-audit-compliance/sanctions-fines.md` |
| Article 22 | SCHUFA | `10-special-topics/automated-decision-making.md` |
| Corporate liability | Deutsche Wohnen | `11-audit-compliance/sanctions-fines.md` |
| Lead SA | Facebook IE v BE DPA | `00-governance/one-stop-shop.md` |

---

## Türkçe

# Önemli AAD Kararları

Bu referans, GDPR yorumunu şekillendiren en operasyonel açıdan önemli Avrupa Adalet Divanı (AAD) kararlarını derler. Her dava atıf, karar ve operasyonel etki ile özetlenmiştir.

### Bu katalog nasıl okunur

| Alan | Anlam |
|------|-------|
| Dava | Yaygın ad + dava numarası (C-XXX/YY) |
| Yıl | Karar yılı |
| Karar | Hukuki kararın bir paragraflık özeti |
| Operasyonel etki | Veri sorumluları / işleyenler için doğrudan sonuç |
| Wiki bağlantısı | Davanın operasyonel hale getirildiği yer |

### Uluslararası aktarımlar

#### Schrems I — Maximillian Schrems v Data Protection Commissioner (C-362/14)

- **Yıl:** 2015.
- **Karar:** ABD Safe Harbor yeterlilik kararını (2000/520/EC) geçersiz kıldı. Yeterlilik "esasen denk" koruma gerektirir. SA'lar Komisyon kararlarına rağmen şikayetleri soruşturmalıdır.
- **Operasyonel etki:** Yeterlilik kararları için inceleme standardını belirledi. Schrems II'nin temeli.
- **Wiki bağlantısı:** `07-international-transfers/adequacy.md`.

#### Schrems II — Data Protection Commissioner v Facebook Ireland ve Maximillian Schrems (C-311/18)

- **Yıl:** 2020.
- **Karar:** AB-ABD Privacy Shield'i geçersiz kıldı. SCC'ler geçerli kalır fakat alıcı ülke hukukunun vaka bazında değerlendirilmesini gerektirir. Hukuk "Avrupa Temel Garantileri"ni karşılamadığında, ek tedbirler veya aktarım askıya alma gereklidir.
- **Operasyonel etki:** Aktarım Etki Değerlendirmelerini (TIA), ek tedbirleri (AB içi anahtarlarla şifreleme, takma adlaştırma, sözleşme eklemeleri) zorunlu kılar. EDPB Tavsiyeleri 01/2020 kararı operasyonalize eder. Halef çerçeve: AB-ABD Veri Gizliliği Çerçevesi (DPF, Temmuz 2023, Uygulama Kararı 2023/1795).
- **Wiki bağlantısı:** `07-international-transfers/safeguards.md`.

### Unutulma hakkı ve arama motorları

#### Google Spain SL ve Google Inc. v AEPD ve Mario Costeja González (C-131/12)

- **Yıl:** 2014.
- **Karar:** Arama motorları veri sorumlusudur. İlgili kişilerin eski Direktif 95/46/EC Madde 12(b) ve 14(a) altında silme talep etme hakkı vardır; erişimde kamu yararı ile dengelenir.
- **Operasyonel etki:** Madde 17 silme hakkı ve arama motorlarına uygulanan Madde 21 itiraz hakkının temeli. Madde 17(3) istisnalarını (ifade özgürlüğü, kamu yararı arşivleri) tetikledi.
- **Wiki bağlantısı:** `09-data-subject-rights/erasure.md`.

#### GC ve Diğerleri v CNIL (C-136/17)

- **Yıl:** 2019.
- **Karar:** Arama motoru silme yükümlülükleri, üstün kamu yararı yoksa silme lehine daha güçlü ağırlandırmayla özel kategori veriye uygulanır.
- **Operasyonel etki:** Silme dengeleme testlerinde Madde 9'u sıkılaştırdı.

#### Google v CNIL (C-507/17)

- **Yıl:** 2019.
- **Karar:** Unutulma hakkı genel olarak yalnızca AB arama motoru sürümlerine uygulanır. Üye devletler hukukla daha ileri uzatabilir.
- **Operasyonel etki:** Silme coğrafi kapsamı.

### Açık rıza ve çerezler

#### Planet49 — Bundesverband der Verbraucherzentralen v Planet49 (C-673/17)

- **Yıl:** 2019.
- **Karar:** Önceden işaretli kutular, ePrivacy Direktifi 2002/58/EC ve GDPR Madde 4(11) altında geçerli rıza oluşturmaz. Rıza aktif, belirli, bilgilendirilmiş, özgürce verilmiş olmalıdır. Çerez süresi ve üçüncü taraf erişimi hakkında bilgi gereklidir.
- **Operasyonel etki:** Çerez bantları reddetmeyi kabul kadar belirgin sunmalı; önceden işaretleme yok; amaç başına ayrıntılı; belirli bilgi.
- **Wiki bağlantısı:** `03-transparency-consent/consent.md`.

#### Orange Romania v ANSPDCP (C-61/19)

- **Yıl:** 2020.
- **Karar:** İlgili kişinin bir kutuyu işaretlediği standartlaştırılmış sözleşmeler yoluyla elde edilen rıza, yalnızca aktif ve bilgilendirilmiş ise geçerli olabilir; veri sorumlusu ispat yükümlülüğü taşır.
- **Operasyonel etki:** Madde 7(1) kanıtlanabilirliği güçlendirir.

### Müşterek veri sorumluluğu

#### Wirtschaftsakademie Schleswig-Holstein (C-210/16)

- **Yıl:** 2018.
- **Karar:** Bir Facebook hayran sayfası operatörü, ziyaretçi verilerinin (Insights) işlenmesinde Facebook ile müşterek veri sorumlusudur.
- **Operasyonel etki:** Organizasyonların sosyal medya varlığının yaygın incelemesini tetikledi. Madde 26 müşterek veri sorumlusu düzenlemeleri gereklidir. Eklentiler, gömülü içerik, analitik üzerinde pratik etki.
- **Wiki bağlantısı:** `06-organizational-measures/joint-controllers.md`.

#### Fashion ID (C-40/17)

- **Yıl:** 2019.
- **Karar:** Facebook "Beğen" düğmesini gömen web sitesi, ziyaretçi verisinin Facebook'a toplanması ve iletilmesi için müşterek veri sorumlusudur (fakat Facebook'un sonraki işlemesi için değil).
- **Operasyonel etki:** Gömülü sosyal eklentiler yüklemeden önce açık rıza gerektirir; müşterek veri sorumlusu rejimi.

#### Jehovan todistajat (C-25/17)

- **Yıl:** 2018.
- **Karar:** Dini topluluk, sakinler hakkında kapı kapı not alma için üyeleriyle müşterek veri sorumlusudur.
- **Operasyonel etki:** Müşterek veri sorumlusu kapsamı geniştir — amacı ve araçları belirleyen herhangi bir taraf.

### Kişisel veri kapsamı

#### Lindqvist (C-101/01)

- **Yıl:** 2003.
- **Karar:** Kişisel bir web sayfasında bireyleri adlandırmak, Direktif 95/46/EC kapsamında kişisel veri işlemedir.
- **Operasyonel etki:** "Kişisel veri" geniş kapsamı üzerinde temel.

#### Breyer v Bundesrepublik Deutschland (C-582/14)

- **Yıl:** 2016.
- **Karar:** Dinamik IP adresleri, veri sorumlusu kullanıcıyı tanımlamak için makul araçlara sahip olduğunda kişisel veridir.
- **Operasyonel etki:** IP adresleri ve çevrimiçi tanımlayıcılar kişisel veridir — günlük saklama, analitik, reklamcılığı etkiler.

#### Nowak v Data Protection Commissioner (C-434/16)

- **Yıl:** 2017.
- **Karar:** Sınav cevap kağıtları ve sınav görevlisinin yorumları kişisel veridir.
- **Operasyonel etki:** Eğitim ve İK'da geniş kişisel veri yorumu.

### İlgili kişi hakları — yargısal genişletmeler

#### Bara v Casa Naţionala de Asigurari de Sanatate (C-201/14)

- **Yıl:** 2015.
- **Karar:** Otoriteler arası kamu idaresi veri aktarımları, ilgili kişilerin bilgilendirilmesini gerektirir (Direktif 95/46 altında Madde 14 şeffaflık).
- **Operasyonel etki:** Çapraz kamu otoritesi veri paylaşımı şeffaf olmalıdır.

#### Buivids v Datu valsts inspekcija (C-345/17)

- **Yıl:** 2019.
- **Karar:** Polis sorgusunun video kaydı ve yayınlanması, gerçeklere bağlı olarak gazetecilik istisnası kapsamına girebilir; veri sorumlusuna göre analiz.
- **Operasyonel etki:** Madde 85 gazetecilik dengesini sıkılaştırır.

#### Pankki S (C-579/21)

- **Yıl:** 2023.
- **Karar:** Erişim hakkı (Madde 15), ilgili kişinin kendi çalışanı verisini işlediğinde, veri sorumlusunun kim erişti bilgisini sağlamasını gerektirir.
- **Operasyonel etki:** İstihdam senaryolarında erişim talepleri için erişim günlükleri mevcut olmalıdır.

#### Österreichische Post (UI v) (C-300/21)

- **Yıl:** 2023.
- **Karar:** Madde 82 manevi zarar fiili zarar kanıtı gerektirir; de minimis ciddiyet eşiği yoktur.
- **Operasyonel etki:** Sıkıntı, kaygı için tazminat talepleri uygulanabilirdir.

### Gözetim ve hukuk uygulama etkileşimi

#### La Quadrature du Net ve Diğerleri (Birleşik Davalar C-511/18, C-512/18, C-520/18)

- **Yıl:** 2020.
- **Karar:** Elektronik iletişim sağlayıcıları tarafından trafik ve konum verilerinin genel ve ayrım gözetmeyen saklanması, ulusal güvenliğe ciddi tehdit yokluğunda AB hukukuna aykırıdır; güvenceler altında hedefli saklama izinlidir.
- **Operasyonel etki:** Üye devletler tarafından ePrivacy veri saklamasını sınırlar; hukuk uygulamasıyla işbirliğini etkiler.

#### Privacy International (C-623/17) ve SpaceNet/Telekom Deutschland (C-793/19, C-794/19)

- **Yıl:** 2020 ve 2022.
- **Karar:** İstihbarat servisleri tarafından toplu veri saklama ve erişim sınırlarını yeniden teyit etti.
- **Operasyonel etki:** Schrems II temel denklik değerlendirmelerine girdi.

### Öncü denetim otoritesi

#### Facebook Ireland Limited v Belçika DPA (C-645/19)

- **Yıl:** 2021.
- **Karar:** Öncü SA dışındaki SA'lar, belirtilen koşullar altında sınır ötesi işleme için ulusal mahkemelerde dava açabilir (Madde 58, 60-66).
- **Operasyonel etki:** Tek durak münhasır değildir; ilgili SA'lar tanımlı durumlarda yaptırım yetkisini korur.

### Madde 22 — otomatik karar verme

#### SCHUFA Holding (C-634/21)

- **Yıl:** 2023.
- **Karar:** Banka kararlarını önemli ölçüde yönlendiren bir olasılık değeriyle sonuçlanan otomatik kredi puanlaması, başlı başına Madde 22(1) otomatik kararıdır.
- **Operasyonel etki:** Madde 22 kapsamı, puanın etkili olarak sonucu belirlediği insan incelemesinin öncesindeki puanlamaya kadar uzanır.

### İşleme kayıtları ve hesap verebilirlik

#### Deutsche Wohnen / Berlin SA (C-807/21)

- **Yıl:** 2023.
- **Karar:** Madde 83 cezaları, ihlali önce belirli bir gerçek kişiye atfetmeden kişisel veri ihlalleri için tüzel kişiye doğrudan verilebilir; "teşebbüs" kavramı (AB rekabet hukuku) uygulanır.
- **Operasyonel etki:** Kurumsal sorumluluk doğrudandır; ceza tavanı için grup cirosu ilgili olabilir.

### Ulusal mahkemeler ve AAD sevki — son temalar

AAD aşağıdaki konularda sevkler almaya devam ediyor:

- İşlemeden hassas veri çıkarımları (Madde 9).
- Meşru menfaatler ve doğrudan pazarlama.
- Madde 82 altında tazminat eşikleri.
- ISP'lerce veri saklama.
- AI eğitim verisi ve Madde 5(1)(a).

### Atıf kuralları

Şöyle atıf yapın: "Dava C-XXX/YY [Yaygın Ad], [tarih] kararı, EU:C:YYYY:XXX." Hukuk Sözcüsü görüşleri için "[ad] HSY görüşü, [tarih] sunulan" ekleyin.

### Wiki çapraz bağlantı özeti

| Konu | Davalar | Wiki bölümü |
|------|---------|-------------|
| Uluslararası aktarımlar | Schrems I, Schrems II | `07-international-transfers/` |
| Unutulma hakkı | Costeja, GC ve Diğerleri, Google v CNIL | `09-data-subject-rights/erasure.md` |
| Açık rıza | Planet49, Orange Romania | `03-transparency-consent/consent.md` |
| Müşterek veri sorumluluğu | Wirtschaftsakademie, Fashion ID, Jehovan | `06-organizational-measures/joint-controllers.md` |
| Kişisel veri kapsamı | Lindqvist, Breyer, Nowak | `01-core-concepts/definitions.md` |
| DSR — erişim | Pankki S | `09-data-subject-rights/access.md` |
| Tazminat | Österreichische Post | `11-audit-compliance/sanctions-fines.md` |
| Madde 22 | SCHUFA | `10-special-topics/automated-decision-making.md` |
| Kurumsal sorumluluk | Deutsche Wohnen | `11-audit-compliance/sanctions-fines.md` |
| Öncü SA | Facebook IE v BE DPA | `00-governance/one-stop-shop.md` |
