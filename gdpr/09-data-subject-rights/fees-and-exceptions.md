---
title:
  en: "Fees, Exceptions, and Derogations to Data Subject Rights"
  tr: "İlgili Kişi Haklarında Ücretler, İstisnalar ve Sapmalar"
section: "09-data-subject-rights"
document_id: "DSR-FEE-001"
owner: "Data Protection Officer / Legal"
classification: "Internal"
version: "1.0"
last_review: "2026-05-08"
next_review: "2027-05-08"
language: ["en", "tr"]
references:
  - "GDPR Art. 12(5) — Free of charge; manifestly unfounded or excessive"
  - "GDPR Art. 15(3)–(4) — Copy and rights of others"
  - "GDPR Art. 17(3) — Erasure exemptions"
  - "GDPR Art. 23 — Restrictions"
  - "EDPB Guidelines 01/2022 — Right of access §169–§186"
  - "CJEU C-307/22 FT v DW — Subject access free of charge regardless of motive"
  - "CJEU C-154/21 RW — Right to know recipients (named, not just categories, on request)"
---

## English

### 1. Article 12(5) — the rule of free, the exception of fee or refusal

Article 12(5) sets the default: information and communications under Articles 13 and 14, and any communication and any actions taken under Articles 15 to 22 and 34, are provided free of charge. The exception is narrow: where requests are manifestly unfounded or excessive, in particular because of their repetitive character, the controller may either:

(a) charge a reasonable fee taking into account the administrative costs of providing the information or communication or taking the action requested, or

(b) refuse to act on the request.

In both cases the controller bears the burden of demonstrating manifest unfoundedness or excessiveness (Article 12(5) sentence 2). EDPB Guidelines 01/2022 paragraphs 169–186 set a high bar.

### 2. What is "manifestly unfounded"

EDPB 01/2022 §178 explains that "manifestly unfounded" requires the request to be clearly without merit, taking into account the right being exercised and the surrounding circumstances. Examples that may qualify:

- The requester is not seeking to exercise a right but to harass the controller (evidence: pattern of abusive language, threats).
- The requester is not the data subject and has no legitimate basis for representation; the request is a fishing expedition.
- The data subject has explicitly stated that they do not actually want the data (e.g. on social media).

Examples that do not qualify, even though they may be inconvenient:

- The data subject is unhappy with the controller and the request is part of a dispute.
- The data subject's purpose is to support a legal claim against the controller (CJEU C-307/22 FT v DW: motive is not a relevant factor for charging or refusing).
- The request is awkward to satisfy because the controller has bad data architecture.
- The request is voluminous because the controller processes a lot of data about the requester.

### 3. What is "excessive"

EDPB 01/2022 §175 frames excessiveness as concerning the frequency or volume of repetitive requests. Examples:

- A second identical access request three weeks after a complete prior response, with no change in circumstances.
- A pattern of requests structured to consume controller resources rather than to obtain information.

Examples that do not qualify:

- A second access request because the requester noticed missing categories in the first response.
- A request for several rights (access + rectification + erasure) in the same letter.
- A request that touches many systems because the requester has used many products.

### 4. Decision protocol for fees / refusals

| Step | Action |
|------|--------|
| 1 | Handler raises a draft "manifestly unfounded or excessive" assessment with evidence. |
| 2 | DPO reviews. Any decision to charge or refuse must have DPO sign-off. |
| 3 | The reasons are documented in the case file and quoted in the response. |
| 4 | The fee, if charged, must be reasonable: itemised, reflecting actual administrative cost, and capped. |
| 5 | The response informs the data subject of the right to complain to the SA and to seek a judicial remedy. |

The DPO publishes an annual review of all fee/refusal decisions, with the rate as a KPI. A rate above 5% triggers root-cause review.

### 5. Article 15(4) — rights of others

Article 15(4) provides that the right to obtain a copy under 15(3) shall not adversely affect the rights and freedoms of others. EDPB 01/2022 §155–§168 explains:

- Where the data also concerns another natural person, the controller weighs the rights and freedoms of that person against the requester's right of access.
- The default is to redact rather than refuse.
- Categories of "others" include: other employees mentioned in performance reviews; counterparties in correspondence; informants in compliance investigations; minors named in adult requests; victims in incident records.
- The controller may not refuse to provide a copy entirely on the basis of others' rights unless redaction would render the response meaningless.
- Trade secrets and intellectual property may justify refusing to disclose source code, model parameters, or algorithmic logic — but not the data itself or the meaningful information about logic required by Article 15(1)(h).

### 6. Article 17(3) — exemptions to erasure

Erasure under Article 17(1) does not apply to the extent that processing is necessary:

(a) **For exercising the right of freedom of expression and information.** Examples: journalistic archives, academic research, public-interest reporting. The controller documents the public-interest assessment and the proportionality of retention.

(b) **For compliance with a legal obligation which requires processing by Union or Member State law.** Examples: tax retention (commonly 5–10 years depending on jurisdiction); social security records; AML/KYC retention; employment records under labour law; healthcare retention. The controller cites the specific legal provision.

(c) **For reasons of public interest in the area of public health.** Examples: pharmacovigilance, epidemic surveillance, public health registries.

(d) **For archiving purposes in the public interest, scientific or historical research, or statistical purposes** in accordance with Article 89(1), in so far as erasure is likely to render impossible or seriously impair the achievement of those purposes. Safeguards under Article 89 must be in place (pseudonymisation, access controls).

(e) **For the establishment, exercise or defence of legal claims.** Examples: ongoing or threatened litigation; defending against a complaint; claims under limitation periods. The controller distinguishes credible legal-claims need from speculative retention. EDPB 9/2022 and ICO guidance both warn that this exemption is misused.

When relying on an exemption, the controller:

- restricts processing of the retained data to the exempt purpose only;
- documents the basis with reference to the legal provision or the public-interest assessment;
- sets a date when the exemption will end and erasure will proceed, where determinable;
- communicates clearly to the data subject which data is retained, why, and for how long.

### 7. National law derogations under Article 23

Article 23 allows EU and Member State law to restrict the scope of the obligations and rights provided in Articles 12 to 22 and Article 34, when such a restriction respects the essence of the fundamental rights and freedoms and is a necessary and proportionate measure in a democratic society to safeguard:

- national security;
- defence;
- public security;
- the prevention, investigation, detection or prosecution of criminal offences;
- other important objectives of general public interest of the Union or of a Member State, in particular an important economic or financial interest;
- the protection of judicial independence and judicial proceedings;
- the prevention, investigation, detection and prosecution of breaches of ethics for regulated professions;
- a monitoring, inspection or regulatory function;
- the protection of the data subject or the rights and freedoms of others;
- the enforcement of civil law claims.

Common Member State derogations to be aware of:

| Member State | Example derogation |
|--------------|-------------------|
| Germany | BDSG §29 — restrictions for journalistic, scientific, archival purposes; §32–§37 — sectoral restrictions |
| France | Loi Informatique et Libertés Title IV — restrictions for ongoing investigations, financial supervision |
| Spain | LOPDGDD §23 — restrictions for the AEAT (tax administration) and other public bodies |
| Ireland | Data Protection Act 2018 §60–§61 — investigations and journalism |
| Italy | Codice Privacy Art. 2-undecies — judicial functions, defence, weapons control |
| Türkiye (KVKK) | Article 28 — full exclusion (national security, criminal prevention, judicial functions); Article 28/A — partial restrictions |

Where a derogation is invoked, the controller cites the specific national provision, restricts only what the provision restricts, and informs the data subject to the extent the derogation permits.

### 8. The KVKK comparator

For requesters resident in Türkiye, KVKK Article 11 provides parallel rights, with operational rules in the KVKK Communiqué on Procedures and Principles of Application. KVKK requires the response within 30 days. KVKK Article 13(3) also permits a fee where requests require disproportionate effort, with the fee schedule set by the KVK Board.

The controller maintains a single bilingual response process so that a data subject who has data both in EU and TR systems gets one coherent answer.

### 9. Reasonable fee calculation

Where a fee is charged, the methodology must be:

- **Itemised**: hours of handler time × an internal rate, reproduction costs, postage, sworn translation if requested.
- **Reasonable**: not punitive, not designed to deter.
- **Capped**: a publicly known maximum.
- **Proportionate**: fee for delivering data should not exceed the cost of producing it.
- **Transparent**: the requester sees the calculation, not just the total.

Routine subject access requests are virtually always free; fees occur in narrow excessive-repetition cases.

### 10. Documentation

For each fee or refusal decision:

- the request and case file;
- the evidence relied upon (prior responses, repetition pattern, evidence of harassment);
- the DPO's written assessment;
- the response letter sent;
- any subsequent SA correspondence or complaint;
- the outcome.

### 11. Frequently encountered patterns

#### 11.1 The persistent claimant

A former customer in dispute with the controller files identical access requests every six weeks, each producing no new data. After two complete responses, the controller may reasonably treat further identical requests as excessive — but the response must still document the assessment and offer a route back if circumstances change.

#### 11.2 The very large dataset

A long-standing customer with 12 years of activity asks for a copy of all data. The volume itself is not a basis to charge; the controller invests in tooling and may invoke the Article 12(3) extension. EDPB 01/2022 §170 confirms that volume is not in itself a basis for fee or refusal.

#### 11.3 The third-party data problem

A request reveals a record where the requester is interleaved with another natural person (e.g. a complaint filed by a colleague). The controller redacts the colleague's identifying data under Article 15(4) and provides the remainder.

#### 11.4 The legal-claim retention

A data subject requests erasure shortly after announcing intent to sue. The controller may rely on Article 17(3)(e) for data relevant to the threatened claim, but must not extend the retention beyond what is genuinely necessary. The exemption is per-record, not blanket.

#### 11.5 The lawful obligation retention

A data subject requests erasure of order data still within the tax retention window. Article 17(3)(b) applies. The controller restricts the data, sets a deletion date matched to the legal retention period, and erases on schedule.

### 12. KPI

| KPI | Target |
|-----|--------|
| Refusal rate (Article 12(5) refusals as % of total requests) | < 1% |
| Fee-charged rate | < 0.5% |
| SA complaints overturning a refusal | 0 |
| Average time to issue a refusal letter | < 14 days |

### 13. Continuous training

The DPO trains DSR handlers annually with anonymised real cases including borderline calls. The training reinforces that the law presumes free, the law presumes compliance, and the burden is on the controller.

---

## Türkçe

### 1. Madde 12(5) — ücretsizlik kuralı, ücret veya ret istisnası

Madde 12(5) varsayılanı belirler: Madde 13 ve 14 altındaki bilgi ve iletişimler ile Madde 15 ila 22 ve 34 altında alınan herhangi bir iletişim ve eylem ücretsiz sağlanır. İstisna dardır: talepler özellikle tekrarlayan nitelikleri nedeniyle açıkça asılsız veya aşırı olduğunda, veri sorumlusu ya:

(a) bilginin veya iletişimin sağlanması veya talep edilen eylemin yapılmasının idari maliyetlerini dikkate alarak makul bir ücret talep edebilir, ya da

(b) talep üzerinde işlem yapmayı reddedebilir.

Her iki durumda da veri sorumlusu açıkça asılsızlığı veya aşırılığı gösterme yükünü taşır (Madde 12(5) cümle 2). EDPB Rehberi 01/2022 paragraflar 169–186 yüksek bir çıta belirler.

### 2. "Açıkça asılsız" nedir

EDPB 01/2022 §178, "açıkça asılsız"ın talebin, kullanılan hak ve çevreleyen koşullar dikkate alındığında açıkça hak iddiası olmaması gerektiğini açıklar.

Nitelik kazanabilecek örnekler:

- Talep eden bir hakkı kullanmaya çalışmıyor, veri sorumlusunu rahatsız ediyor.
- Talep eden ilgili kişi değildir ve temsil için meşru bir dayanağa sahip değildir.
- İlgili kişi veriyi gerçekten istemediğini açıkça belirtmiştir.

Nitelik kazanmayan örnekler:

- İlgili kişi veri sorumlusundan memnun değil ve talep bir anlaşmazlığın parçası.
- İlgili kişinin amacı veri sorumlusuna karşı bir hukuki talebi desteklemektir (CJEU C-307/22 FT v DW: amaç ücret veya reddetme için ilgili bir faktör değildir).
- Talep yerine getirmesi zor.
- Talep, veri sorumlusu talep eden hakkında çok veri işlediği için hacimli.

### 3. "Aşırı" nedir

EDPB 01/2022 §175 aşırılığı tekrarlanan taleplerin sıklığı veya hacmi olarak çerçeveler.

### 4. Ücret / ret için karar protokolü

| Adım | Eylem |
|------|-------|
| 1 | İşleyici, kanıtla bir "açıkça asılsız veya aşırı" değerlendirmesi taslağı oluşturur. |
| 2 | VKK inceler. Ücret talep etme veya reddetme kararının VKK onayı olmalıdır. |
| 3 | Nedenler dosyada belgelenir ve yanıtta alıntılanır. |
| 4 | Ücret talep ediliyorsa makul olmalıdır: kalemli, gerçek idari maliyeti yansıtan ve sınırlı. |
| 5 | Yanıt, ilgili kişiyi DM'ye şikayet etme ve adli çözüm arama hakkı konusunda bilgilendirir. |

VKK, tüm ücret/ret kararlarının yıllık incelemesini KPI olarak oran ile yayınlar. %5'in üzerindeki bir oran kök neden incelemesini tetikler.

### 5. Madde 15(4) — başkalarının hakları

Madde 15(4), 15(3) altında kopya alma hakkının başkalarının hak ve özgürlüklerini olumsuz etkilememesi gerektiğini düzenler. EDPB 01/2022 §155–§168 açıklar:

- Veri başka bir gerçek kişiyi de ilgilendirdiğinde, veri sorumlusu o kişinin hak ve özgürlüklerini talep edenin erişim hakkına karşı tartar.
- Varsayılan reddetmek değil, redakte etmektir.
- "Başkaları" kategorileri arasında performans incelemelerinde belirtilen diğer çalışanlar, yazışmalardaki karşı taraflar, uyumluluk soruşturmalarındaki muhbirler vardır.
- Veri sorumlusu, başkalarının hakları temelinde bir kopya sağlamayı tamamen reddedemez.
- Ticari sırlar ve fikri mülkiyet, kaynak kodu, model parametreleri veya algoritmik mantığı ifşa etmeyi reddetmeyi haklı kılabilir — ancak verinin kendisini veya Madde 15(1)(h) tarafından gerekli mantık hakkında anlamlı bilgiyi reddetmez.

### 6. Madde 17(3) — silmeye istisnalar

Madde 17(1) altındaki silme, işleme aşağıdakiler için gerekli olduğu ölçüde uygulanmaz:

(a) **İfade ve bilgi özgürlüğü hakkını kullanmak için.**

(b) **Birlik veya Üye Devlet hukuku tarafından gerektirilen yasal bir yükümlülüğe uymak için.** Örnekler: vergi saklama (yargı yetkisine bağlı olarak yaygın olarak 5–10 yıl); sosyal güvenlik kayıtları; AML/KYC saklama; iş hukuku altında çalışma kayıtları; sağlık saklama. Veri sorumlusu özel hukuki hükmü belirtir.

(c) **Kamu sağlığı alanındaki kamu yararı nedenleriyle.**

(d) **Madde 89(1)'e uygun olarak kamu yararı, bilimsel veya tarihsel araştırma veya istatistiksel amaçlar için arşivleme** amaçları için, silme bu amaçların gerçekleştirilmesini imkansız hale getirme veya ciddi şekilde bozma olasılığı varsa.

(e) **Hukuki taleplerin kurulması, kullanılması veya savunulması için.**

Bir muafiyete dayanırken, veri sorumlusu:

- saklanan verinin işlenmesini yalnızca muaf amaca kısıtlar;
- temeli hukuki hüküm veya kamu yararı değerlendirmesi atıfla belgeler;
- belirlenebilir olduğunda muafiyetin biteceği ve silmenin devam edeceği bir tarih belirler;
- ilgili kişiye hangi verinin saklandığını, neden ve ne kadar süreyle saklandığını açıkça iletir.

### 7. Madde 23 altında ulusal hukuk sapmaları

Madde 23, AB ve Üye Devlet hukukunun Madde 12 ila 22 ve Madde 34'te sağlanan yükümlülüklerin ve hakların kapsamını kısıtlamasına izin verir.

| Üye Devlet | Örnek sapma |
|------------|------------|
| Almanya | BDSG §29 — gazetecilik, bilimsel, arşiv amaçları için kısıtlamalar |
| Fransa | Loi Informatique et Libertés Başlık IV — devam eden soruşturmalar için kısıtlamalar |
| İspanya | LOPDGDD §23 — AEAT (vergi idaresi) için kısıtlamalar |
| İrlanda | Veri Koruma Yasası 2018 §60–§61 — soruşturmalar ve gazetecilik |
| İtalya | Codice Privacy Madde 2-undecies — yargısal işlevler |
| Türkiye (KVKK) | Madde 28 — tam dışlama; Madde 28/A — kısmi kısıtlamalar |

### 8. KVKK karşılaştırması

Türkiye'de ikamet eden talep edenler için KVKK Madde 11, KVKK Başvuru Usul ve Esasları Tebliği'ndeki operasyonel kurallarla paralel haklar sağlar. KVKK 30 gün içinde yanıt gerektirir. KVKK Madde 13(3) ayrıca taleplerin orantısız çaba gerektirdiği durumlarda bir ücreti, KVK Kurulu tarafından belirlenen ücret tarifesiyle izin verir.

### 9. Makul ücret hesaplaması

Ücret talep edildiğinde metodoloji:

- **Kalemli**: işleyici saatleri × iç oran, çoğaltma maliyetleri, posta, talep edilirse yeminli tercüme.
- **Makul**: cezalandırıcı değil, caydırıcı tasarlanmamış.
- **Sınırlı**: kamuya açık maksimum.
- **Orantılı**: veri teslim ücreti üretim maliyetini aşmamalıdır.
- **Şeffaf**: talep eden hesaplamayı görür, sadece toplamı değil.

### 10. Belgeleme

Her ücret veya ret kararı için:

- talep ve dosya;
- güvenilen kanıt;
- VKK'nın yazılı değerlendirmesi;
- gönderilen yanıt mektubu;
- sonraki DM yazışmaları veya şikayetler;
- sonuç.

### 11. Sıkça karşılaşılan örüntüler

#### 11.1 Israrcı talep eden

Veri sorumlusuyla anlaşmazlığı olan eski bir müşteri her altı haftada bir aynı erişim taleplerini sunar.

#### 11.2 Çok büyük veri kümesi

12 yıllık etkinliği olan uzun süreli bir müşteri tüm verilerin bir kopyasını ister. Hacim kendi başına ücret talep etme temeli değildir.

#### 11.3 Üçüncü taraf veri sorunu

Bir talep, talep edenin başka bir gerçek kişiyle iç içe olduğu bir kayıt ortaya çıkarır.

#### 11.4 Hukuki talep saklaması

Bir ilgili kişi dava niyetini açıkladıktan kısa süre sonra silme talep eder. Veri sorumlusu, tehdit edilen talep için ilgili veri için Madde 17(3)(e)'ye dayanabilir.

#### 11.5 Yasal yükümlülük saklaması

Bir ilgili kişi hâlâ vergi saklama penceresi içindeki sipariş verisinin silinmesini talep eder. Madde 17(3)(b) uygulanır.

### 12. KPI

| KPI | Hedef |
|-----|-------|
| Reddetme oranı | < %1 |
| Ücret talep etme oranı | < %0,5 |
| Reddetmeyi bozan DM şikayetleri | 0 |
| Reddetme mektubu gönderme ortalama süresi | < 14 gün |

### 13. Sürekli eğitim

VKK, sınır vakaları dahil anonimleştirilmiş gerçek vakalarla DSR işleyicilerini yıllık eğitir.
