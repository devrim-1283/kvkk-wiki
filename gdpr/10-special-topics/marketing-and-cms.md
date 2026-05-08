---
title:
  en: "Marketing, Profiling, and Customer Relationship Management"
  tr: "Pazarlama, Profilleme ve Müşteri İlişkileri Yönetimi"
section: "10-special-topics"
document_id: "ST-MKT-001"
owner: "DPO Office / Marketing Operations"
classification: "Internal"
version: "1.0"
last_review: "2026-05-08"
next_review: "2027-05-08"
language: ["en", "tr"]
references:
  - "GDPR Art. 6, 7, 21, 22"
  - "GDPR Recitals 47, 70, 71"
  - "ePrivacy Directive 2002/58/EC, Articles 6, 13"
  - "ePrivacy Directive 2002/58/EC, Article 13(2) — soft opt-in"
  - "EDPB Guidelines 8/2020 on the targeting of social media users"
  - "EDPB Guidelines 03/2022 on deceptive design patterns"
  - "EDPB Statement 1/2025 on Consent or Pay"
  - "Schrems II (CJEU C-311/18)"
  - "CJEU — Meta Platforms Ireland Ltd v Bundesverband (C-446/21, 4 July 2023)"
  - "CJEU — TC Medical Air Ambulance Agency (C-21/23, 11 July 2024)"
---

## English

### 1. Two regimes overlap

Direct marketing in the EU operates under two overlapping regimes:

- **ePrivacy Directive (2002/58/EC) Article 13** for unsolicited communications (email, SMS, automated calling systems) regardless of whether the recipient is a natural person.
- **GDPR** for the underlying processing of personal data and for any profiling.

Both apply simultaneously. ePrivacy is the lex specialis for the channel; GDPR governs the processing.

### 2. Consent vs. soft opt-in (ePrivacy Article 13)

| Channel | Default rule | Soft opt-in available? |
|---------|-------------|----------------------|
| Email — to existing customer for own similar goods/services | Soft opt-in (Article 13(2)) | Yes, with conditions |
| Email — prospect | Prior consent | No |
| SMS | Prior consent (most Member States); soft opt-in mirrors email in some | Limited |
| Automated calling | Prior consent | No |
| Postal mail | Outside ePrivacy; under GDPR Article 6 (typically (f)) | n/a; opt-out right |
| Social-media DMs / push notifications | Treated as unsolicited communication; consent typical | Limited |
| Live agent calls | Outside ePrivacy Article 13 in many states; but national TPS / DNCL applies | n/a |

Soft opt-in conditions (Article 13(2)):
- recipient is an existing customer;
- contact details obtained in the context of a sale;
- marketing is for the controller's own similar goods or services;
- recipient was given a clear and free opportunity to object at the time of collection and in every subsequent message;
- the recipient did not initially refuse the use.

The "similar" test is interpreted narrowly. Selling the customer a hotel stay does not authorise marketing them mortgages.

### 3. Consent standard for marketing

Where consent is required:
- specific (separate from terms of service);
- granular per channel;
- granular per controller (if a third party is also marketing through the same form);
- prominent equal-weight reject;
- no pre-ticked boxes;
- withdrawable as easily as given;
- record kept (Article 7(1) burden of proof).

CJEU Meta C-446/21 (July 2023) confirmed that for behavioural advertising on a social platform, consent is required even where Article 6(1)(b) or (f) might initially appear available — necessity is narrowly construed for advertising.

### 4. Profiling

Article 4(4) defines profiling. Profiling is processing and is subject to GDPR's regular tests. Recital 71 emphasises measures to ensure fair and transparent processing for profiling.

Where profiling produces legal or similarly significant effect (e.g. credit scoring affecting loan eligibility, pricing changes affecting which products are offered), Article 22 applies and the data subject has rights to human intervention, expression of view, and contestation.

Marketing-grade profiling (segmentation for "people who like outdoor brands") is generally not Article 22 because the effect is not significant; but it remains processing requiring lawful basis and transparency.

### 5. Article 21 — right to object

Article 21(2) gives an absolute right to object to processing for direct marketing purposes, including any related profiling. Once objected, processing for that purpose stops. This is unconditional — no balancing test, no compelling-legitimate-grounds defence.

In every marketing communication, the right must be made explicit and one-click easy. Multi-step opt-out flows attract regulatory scrutiny.

### 6. Adtech and Schrems II

Adtech ecosystems (programmatic, retargeting, audience syndication) involve:
- Many controllers and processors.
- Real-time bidding (RTB) data flows that move personal data in milliseconds to many parties.
- Frequent transfers to third countries, especially the US.

Belgian APD (TCF decisions 2022 onwards), Garante (Google decisions), and AEPD have made adtech a high-enforcement area. Operational rules:
- Inventory every adtech vendor; categorise as controller or processor or joint controller.
- Article 28 contract or joint-controller arrangement with each.
- Transfer mechanism for any non-EEA flow.
- TIA addressing US surveillance laws (FISA 702, EO 12333) for US transfers.
- DPF certification check for US recipients (dataprivacyframework.gov).
- Reduce vendor count where commercial sense allows.
- Disable behavioural advertising features on properties directed to children.

### 7. CMS and CDP architecture

Customer relationship management (CRM) and customer data platform (CDP) systems are the operational core:

- Single customer view: useful, but increases blast radius of any breach.
- Marketing consent fields: machine-readable, channel-specific, time-stamped, source-tagged.
- Consent provenance: where the consent was captured, what notice was shown.
- Withdrawal endpoint: real-time propagation to downstream systems.
- Suppression list: maintained centrally; respected globally; not transferred.
- Audit log of any user-data export to marketing tools.

### 8. Cookie consent and marketing consent

These are different consents:
- Cookie consent (ePrivacy) authorises storage / access on the device.
- Marketing consent authorises sending of marketing communications.

Many controllers conflate them. They must be tracked separately. A user may consent to analytics cookies but reject marketing email.

### 9. Email marketing operations

- Double opt-in is best practice (initial sign-up confirmed by clicking a link in a verification email). Some Member States (Germany under UWG, in some interpretations) effectively require it.
- Each email must contain:
  - sender identity;
  - physical address (CAN-SPAM-style requirement embedded in many Member State laws);
  - one-click unsubscribe (RFC 8058 List-Unsubscribe-Post recommended);
  - link to privacy notice;
  - confirmation that the recipient is on the list (e.g. "you are receiving this because…").
- Suppression on unsubscribe within 10 working days (commonly faster).
- Hard bounces removed; soft bounces tracked.
- Engagement-based pruning: long-inactive recipients re-permissioned or removed.

### 10. SMS and push

- Stricter rules in many Member States.
- Sender ID transparency.
- Easy STOP keyword opt-out.
- No SMS during night hours per local rules.
- Push notifications subject to OS-level permission plus marketing consent.

### 11. Personalised advertising on social platforms

EDPB Guidelines 8/2020 on targeting of social media users:
- Joint controllership analysis between platform and advertiser is common.
- Custom audiences uploaded to platforms involve transfer of personal data; processor or joint-controller relationship.
- Lookalike audiences derive from uploaded data; same scrutiny.
- Behavioural targeting requires consent on the platform side; the advertiser still bears responsibility for ensuring the targeting basis.
- Sensitive-category targeting (health, religion, political) is restricted by platform policies and by GDPR.

### 12. Special categories in marketing

Article 9 categories must not be inferred for marketing without an Article 9(2) basis. Inferring religion from purchase patterns to target halal products requires explicit consent; the inference itself is processing of special-category data.

EDPB 8/2020 explains that even where the inference is probabilistic, if it is used as if true, it is special-category processing.

### 13. Loyalty schemes and tiered pricing

- Loyalty data is personal; lawful basis: (b) contract for the loyalty programme participation; (a) consent for marketing dimensions.
- Free participation with marketing consent vs. paid alternative: subject to EDPB Statement 1/2025 conditions.
- Member State consumer law regulates loyalty schemes additionally.

### 14. Children

- Marketing to under-16 is heavily regulated. Many Member States (UK, Germany) have additional codes.
- Article 8 GDPR governs information-society services to children: consent age 16 default, may be lowered to 13 by Member State.
- ICO Age Appropriate Design Code restricts profiling and behavioural advertising to children.
- AI Act prohibits AI systems that exploit vulnerabilities of children.

### 15. Withdrawal and the right to be left alone

- Unsubscribe must be at least as easy as subscribe.
- Re-engagement attempts after withdrawal are unlawful (Article 21(3) plus Article 7(3)).
- Treat the suppression list as inviolable; transmit through every channel from CMS to ESP to ad networks.

### 16. Documentation pack for marketing

- Marketing privacy notice (Article 13) for each property.
- Consent capture screens versioned and archived.
- Vendor contracts (Article 28 or joint-controller) and DPIAs for high-risk vendors.
- Suppression list management runbook.
- Adtech inventory and TIA pack.
- Article 22 analysis for any decisioning that affects pricing, offers, or eligibility.
- AI Act assessment for any AI-driven targeting where applicable.

### 17. KVKK comparator

KVKK altında doğrudan pazarlama, açık rıza esasına dayanır. Türkiye'nin Ticari Elektronik İletiler Hakkında Yönetmelik İYS sistemini kurar — pazarlama gönderimleri için merkezi bir izin sistemi. KVKK ile İYS uyumu zorunludur.

### 18. KPIs

| KPI | Target |
|-----|--------|
| Time to honour unsubscribe | < 24 hours (channel propagation) |
| Marketing-without-consent complaints | 0 |
| Adtech vendor count | regular pruning |
| Children-data processing in marketing | 0 unintended |
| DPIA coverage of profiling | 100% of significant-effect profiling |

---

## Türkçe

### 1. İki rejim örtüşür

AB'de doğrudan pazarlama iki örtüşen rejim altında çalışır:

- **ePrivacy Direktifi (2002/58/EC) Madde 13** — istenmeyen iletişimler için (e-posta, SMS, otomatik arama sistemleri).
- **GDPR** — temel kişisel veri işleme ve herhangi bir profilleme için.

İkisi de aynı anda uygulanır.

### 2. Rıza vs. yumuşak opt-in (ePrivacy Madde 13)

| Kanal | Varsayılan kural | Yumuşak opt-in mevcut mu? |
|-------|-----------------|--------------------------|
| E-posta — mevcut müşteriye kendi benzer mal/hizmetler için | Yumuşak opt-in (Madde 13(2)) | Koşullarla evet |
| E-posta — potansiyel | Önceki rıza | Hayır |
| SMS | Önceki rıza (çoğu Üye Devlet) | Sınırlı |
| Otomatik arama | Önceki rıza | Hayır |
| Postayla | ePrivacy dışında; GDPR Madde 6 altında (genellikle (f)) | yok; itiraz hakkı |
| Sosyal medya DM'ler / push bildirimleri | İstenmeyen iletişim olarak değerlendirilir | Sınırlı |
| Canlı temsilci aramaları | Birçok Devlette ePrivacy Madde 13 dışında | yok |

Yumuşak opt-in koşulları (Madde 13(2)):
- alıcı mevcut bir müşteridir;
- iletişim bilgileri bir satış bağlamında elde edilmiştir;
- pazarlama veri sorumlusunun kendi benzer mal veya hizmetleri içindir;
- alıcıya toplama anında ve sonraki her mesajda itiraz etme açık ve ücretsiz fırsat verilmiştir;
- alıcı başlangıçta kullanımı reddetmemiştir.

"Benzer" testi dar yorumlanır.

### 3. Pazarlama için rıza standardı

- spesifik;
- kanal başına ayrıntılı;
- veri sorumlusu başına ayrıntılı;
- belirgin eşit ağırlıklı reddet;
- önceden işaretli kutular yok;
- verildiği gibi kolay geri çekilebilir;
- kayıt tutulmuş (Madde 7(1) ispat yükü).

CJEU Meta C-446/21 (Temmuz 2023), bir sosyal platformda davranışsal reklam için Madde 6(1)(b) veya (f) başlangıçta uygulanabilir görünebilse bile rızanın gerekli olduğunu teyit etti.

### 4. Profilleme

Madde 4(4) profillemeyi tanımlar. Profilleme işlemedir ve GDPR'nin düzenli testlerine tabidir.

Profilleme hukuki veya benzer şekilde önemli etki ürettiğinde (örn. kredi puanlama, fiyatlandırma değişiklikleri), Madde 22 uygulanır.

### 5. Madde 21 — itiraz hakkı

Madde 21(2), doğrudan pazarlama amaçlı işlemeye itiraz etme mutlak hakkı verir. İtiraz edildiğinde, o amaç için işleme durur. Bu koşulsuzdur — denge testi yok, zorunlu meşru gerekçe savunması yok.

### 6. Reklam teknolojisi ve Schrems II

Reklam teknolojisi ekosistemleri şunları içerir:
- Birçok veri sorumlusu ve veri işleyen.
- Kişisel veriyi milisaniyeler içinde birçok tarafa hareket ettiren gerçek zamanlı teklif (RTB) veri akışları.
- Üçüncü ülkelere, özellikle ABD'ye sık aktarımlar.

Operasyonel kurallar:
- Her reklam teknolojisi tedarikçisini envanterleyin.
- Her biriyle Madde 28 sözleşmesi veya ortak veri sorumlusu düzenlemesi.
- Herhangi bir AEA dışı akış için aktarım mekanizması.
- ABD aktarımları için ABD gözetleme yasalarını ele alan TIA.
- ABD alıcıları için DPF sertifika kontrolü.

### 7. CMS ve CDP mimarisi

Müşteri ilişkileri yönetimi (CRM) ve müşteri veri platformu (CDP) sistemleri operasyonel çekirdektir:

- Tek müşteri görünümü: yararlı, ancak herhangi bir ihlalin patlama yarıçapını artırır.
- Pazarlama rıza alanları: makine tarafından okunabilir, kanala özgü, zaman damgalı, kaynak etiketli.
- Rıza kaynağı: rızanın nerede yakalandığı, hangi bildirimin gösterildiği.
- Geri çekme uç noktası: aşağı yönlü sistemlere gerçek zamanlı yayılım.
- Bastırma listesi: merkezi olarak sürdürülen; küresel olarak saygı duyulan; aktarılmayan.

### 8. Çerez rızası ve pazarlama rızası

Bunlar farklı rızalardır:
- Çerez rızası (ePrivacy) cihazda saklamayı / erişimi yetkilendirir.
- Pazarlama rızası pazarlama iletişimi göndermeyi yetkilendirir.

### 9. E-posta pazarlama operasyonları

- Çift opt-in en iyi uygulamadır.
- Her e-posta şunları içermelidir:
  - gönderen kimliği;
  - fiziksel adres;
  - tek tıkla abonelikten çıkma;
  - gizlilik bildirimine bağlantı;
  - alıcının listede olduğunun teyidi.
- Abonelikten çıkmada 10 iş günü içinde bastırma.

### 10. SMS ve push

- Birçok Üye Devlette daha katı kurallar.
- Gönderen kimliği şeffaflığı.
- Kolay STOP anahtar kelime opt-out.
- Yerel kurallara göre gece saatlerinde SMS yok.
- Push bildirimleri OS düzeyi izin artı pazarlama rızasına tabi.

### 11. Sosyal platformlarda kişiselleştirilmiş reklam

EDPB Rehberi 8/2020:
- Platform ve reklamveren arasında ortak veri sorumluluğu analizi yaygındır.
- Platformlara yüklenen özel kitleler kişisel veri aktarımını içerir.
- Benzer kitleler yüklenen veriden türetilir.
- Davranışsal hedefleme platform tarafında rıza gerektirir.
- Hassas kategori hedefleme (sağlık, din, siyasi) platform politikaları ve GDPR tarafından kısıtlanmıştır.

### 12. Pazarlamada özel kategoriler

Madde 9 kategorileri Madde 9(2) temeli olmadan pazarlama için çıkarılmamalıdır.

### 13. Sadakat şemaları ve kademeli fiyatlandırma

- Sadakat verisi kişisel verdir; hukuki temel: sadakat programı katılımı için (b) sözleşme; pazarlama boyutları için (a) rıza.
- Pazarlama rızasıyla ücretsiz katılım vs. ücretli alternatif: EDPB Bildirimi 1/2025 koşullarına tabi.

### 14. Çocuklar

- 16 yaş altı pazarlaması ağır şekilde düzenlenmiştir.
- Madde 8 GDPR çocuklara bilgi toplumu hizmetlerini yönetir.
- ICO Yaşa Uygun Tasarım Kodu profilleme ve davranışsal reklamı çocuklara kısıtlar.
- AI Yasası çocukların zayıflıklarını sömüren AI sistemlerini yasaklar.

### 15. Geri çekme ve yalnız bırakılma hakkı

- Abonelikten çıkma en azından abonelik kadar kolay olmalıdır.
- Geri çekmeden sonra yeniden etkileşim girişimleri yasal değildir.
- Bastırma listesini ihlal edilemez kabul edin.

### 16. Pazarlama için belgeleme paketi

- Her mülk için pazarlama gizlilik bildirimi (Madde 13).
- Sürümlü ve arşivlenmiş rıza yakalama ekranları.
- Tedarikçi sözleşmeleri (Madde 28 veya ortak veri sorumlusu) ve yüksek riskli tedarikçiler için VKD'ler.
- Bastırma listesi yönetimi runbook'u.
- Reklam teknolojisi envanteri ve TIA paketi.
- Fiyatlandırmayı, teklifleri veya uygunluğu etkileyen herhangi bir karar verme için Madde 22 analizi.

### 17. KVKK karşılaştırması

KVKK altında doğrudan pazarlama, açık rıza esasına dayanır. Türkiye'nin Ticari Elektronik İletiler Hakkında Yönetmelik İYS sistemini kurar — pazarlama gönderimleri için merkezi bir izin sistemi. KVKK ile İYS uyumu zorunludur.

### 18. KPI'lar

| KPI | Hedef |
|-----|-------|
| Abonelikten çıkmayı yerine getirme süresi | < 24 saat (kanal yayılımı) |
| Rıza olmadan pazarlama şikayetleri | 0 |
| Reklam teknolojisi tedarikçi sayısı | düzenli budama |
| Pazarlamada çocuk verisi işleme | 0 istenmeden |
| Profillemenin VKD kapsamı | Önemli etkili profillemenin %100'ü |
