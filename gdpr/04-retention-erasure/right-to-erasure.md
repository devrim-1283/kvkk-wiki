---
title:
  en: "Right to Erasure (Article 17)"
  tr: "Silme Hakkı (Madde 17)"
section: "04-retention-erasure"
document_type: "procedure"
regulation: "GDPR (EU 2016/679)"
articles:
  - "Art. 12 — Transparent information, communication, modalities"
  - "Art. 17 — Right to erasure ('right to be forgotten')"
  - "Art. 19 — Notification obligation regarding rectification, erasure, restriction"
  - "Art. 23 — Restrictions"
  - "Recital 65 — Right of rectification and erasure"
  - "Recital 66 — Right to be forgotten"
related:
  - "Google Spain SL, Google Inc. v AEPD, Mario Costeja González (C-131/12)"
  - "GC and Others v CNIL (C-136/17)"
  - "Google v CNIL (C-507/17) — territorial scope"
language: "en, tr"
last_reviewed: "2025-05-01"
review_cycle: "annual"
owner: "Data Protection Officer"
status: "approved"
classification: "internal"
---

## English

# Right to Erasure (Article 17)

This procedure governs the handling of erasure requests received from data subjects under Article 17 GDPR.

## 1. Legal basis

### 1.1 The right (Art. 17(1))

A data subject has the right to obtain erasure of their personal data **without undue delay** where one of the following applies:

| Ground | Description |
|---|---|
| (a) | The data is no longer necessary for the purposes for which it was collected or otherwise processed. |
| (b) | The data subject withdraws consent and there is no other legal ground for processing. |
| (c) | The data subject objects under Art. 21(1) and there are no overriding legitimate grounds, or objects under Art. 21(2) (direct marketing). |
| (d) | The data has been unlawfully processed. |
| (e) | The data must be erased to comply with a legal obligation in EU or member-state law to which the controller is subject. |
| (f) | The data was collected in relation to the offer of information society services to a child (Art. 8(1)). |

### 1.2 Exemptions (Art. 17(3))

The right does not apply to the extent processing is necessary for:

| Exemption | Description |
|---|---|
| (a) | Exercising the right of freedom of expression and information. |
| (b) | Compliance with a legal obligation requiring processing under EU or member-state law, or for the performance of a task carried out in the public interest or in the exercise of official authority. |
| (c) | Reasons of public interest in the area of public health (Art. 9(2)(h) and (i), Art. 9(3)). |
| (d) | Archiving in the public interest, scientific or historical research, or statistical purposes (Art. 89(1)). |
| (e) | Establishment, exercise, or defence of legal claims. |
| (f) | (Implicit) — limitation under Art. 23 (national security, defence, judicial independence, etc.). |

### 1.3 Notification (Art. 19)

Where the controller has disclosed the personal data to recipients, it shall communicate any erasure to each recipient unless this proves impossible or involves disproportionate effort. The controller shall inform the data subject about those recipients if requested.

### 1.4 Public availability (Art. 17(2))

Where the controller has made the personal data public and is obliged to erase, the controller shall, taking account of available technology and cost of implementation, take **reasonable steps**, including technical measures, to inform other controllers processing the data that the data subject has requested erasure of any links, copies, or replications.

### 1.5 Timeline (Art. 12(3))

- Acknowledge: as soon as possible.
- Substantive response: **within one month** of receipt.
- Extension: up to two further months for complex requests, with notice to the data subject within the first month explaining the reason.

### 1.6 No fee (Art. 12(5))

Free of charge unless requests are manifestly unfounded or excessive. Repeated identical requests, or requests with bad-faith intent, may attract a reasonable fee or refusal — both with documented justification.

## 2. Procedure

### 2.1 Receipt and acknowledgement

1. **Channels.** Erasure requests may arrive via:
   - Privacy email inbox (`privacy@[organisation]`).
   - Data subject rights portal.
   - Postal letter.
   - In-person or telephone request (recorded by recipient and confirmed in writing).
   - Customer service / support ticket (forwarded to DPO).

2. **Logging.** Every request is logged in the Data Subject Rights Register with:
   - Receipt date and channel.
   - Identifier(s) of data subject (name, email, customer ID).
   - Scope (all data, specific category, specific record).
   - Stated grounds (if provided).
   - Assigned case officer.

3. **Acknowledgement.** Within 5 business days of receipt, send an acknowledgement to the data subject confirming receipt and outlining the response window.

### 2.2 Identity verification

The controller must verify the requester's identity to avoid unauthorised disclosure or destruction. Recommended approach:

- **Existing customers.** Verify via account-bound channel (logged-in session, recovery email already on file, customer service phone authentication).
- **Non-customers / former customers.** Request additional verification proportionate to the risk; do not over-collect.
- **Authorised representatives.** Require evidence of authority (written authorisation, court order, parental responsibility).
- **Children.** Special care; verify identity of holder of parental responsibility if requesting on behalf of a child.

If identity cannot be verified, the controller may request additional information necessary to confirm identity (Art. 12(6)). The one-month clock pauses for the time the controller is reasonably awaiting such information.

### 2.3 Scope determination

Determine:

1. **What** personal data the request covers (all or subset).
2. **Where** the data resides (production DBs, backups, archives, processors, sub-processors, paper, third-country recipients).
3. **Whether** any of the Art. 17(3) exemptions apply, in whole or in part.
4. **Which** recipients have received the data (Art. 19).

### 2.4 Lawful basis review

Before erasing, evaluate whether one of the Art. 17(3) exemptions blocks erasure:

- **Tax / accounting / audit obligation.** Salary records, invoices, ledgers — typically retained for the statutory minimum (e.g., 10 years in Germany) and *cannot* be erased earlier.
- **Legal claims.** Where active or anticipated litigation exists, retention is justified for the limitation period.
- **Freedom of expression.** Editorial content, journalism. Apply Costeja and GC v CNIL principles.
- **Public interest archiving / research.** Subject to Art. 89 safeguards.
- **Public health.** Art. 9(2)(h) processing.

If an exemption applies in part, identify the **specific subset** retained and erase the rest. Do not refuse the entire request.

### 2.5 Erasure execution

Once the request is confirmed valid and not exempt:

1. **Production.** Delete or anonymise records in production systems per `erasure-methods.md`.
2. **Replicas.** Confirm replication propagated the deletion (read replicas, BI warehouse, search index).
3. **Caches.** Force purge (CDN, application, browser).
4. **Backups.** Apply backup erasure strategy (`erasure-methods.md` §5). Document residual retention and compensating controls.
5. **Logs.** Identify whether logs contain personal data; pseudonymise or delete per log lifecycle.
6. **Processors.** Notify each processor in writing; require written confirmation; track via DPA.
7. **Sub-processors.** Verify the processor has propagated.
8. **Third-country transfers.** Notify the recipient under Art. 19; verify per applicable Chapter V mechanism.
9. **Paper.** Locate and destroy under DIN 66399.
10. **Endpoints.** If personal data is on a specific employee's device, instruct sanitisation.

### 2.6 Notification to recipients (Art. 19)

For each recipient that received the data:
- Identify the recipient and the disclosure date.
- Send a written notification specifying the data to be erased.
- Track confirmation; escalate if no response within 14 days.
- Document in the Data Subject Rights Register.

### 2.7 Public availability (Art. 17(2))

If the personal data was made public:
- Identify all known mirror or copy locations (search engines, syndication partners, archive services).
- Send takedown / dereference requests where applicable (e.g., Google "Right to be forgotten" requests).
- Document reasonable steps taken.

### 2.8 Response to data subject

Within one month of receipt (or extended period), send a written response containing:

- Confirmation of erasure (and scope).
- Identification of any data not erased and the legal basis for retention.
- Information about recipients notified under Art. 19 (if requested).
- Right to lodge a complaint with the supervisory authority.
- Right to seek judicial remedy.
- Contact details for follow-up questions.

### 2.9 Record of action

Update the Data Subject Rights Register with:

- Disposition (granted / partially granted / refused).
- Date of completion.
- Categories erased.
- Categories retained (with legal basis).
- Recipients notified.
- Evidence of erasure (destruction record reference).
- Time-to-completion metric.

The record is retained per the Retention Schedule (typ. 3 years).

## 3. Refusal and partial refusal

### 3.1 Manifestly unfounded or excessive

If the request is manifestly unfounded or excessive (Art. 12(5)):

- Document the assessment criteria (frequency, content, intent).
- Choose: charge a reasonable fee, OR refuse.
- Provide reasons.
- Inform the data subject of the right to complain to the supervisory authority and seek judicial remedy.

### 3.2 Exempt data

For data exempt under Art. 17(3):

- Identify the specific exemption (legal obligation, legal claims, public interest, archiving, freedom of expression, public health).
- Identify the specific data and minimum retention.
- Erase any data outside the exemption.
- Restrict processing of the retained data to the exempt purpose only (Art. 18 may apply).
- Inform the data subject of the partial outcome and reasons.

### 3.3 Identity not verified

If identity cannot be verified after reasonable additional information requests:

- Refuse to act (cannot risk unauthorised destruction).
- Document the unverified identity assessment.
- Inform the data subject of the right to retry with additional verification.

## 4. Erasure propagation across systems

The "erasure radius" of a data subject's record:

```
Data Subject record
├── Primary database (production)
│   ├── Read replicas
│   ├── BI warehouse / data lake
│   ├── Search index
│   └── Cache layer (CDN, app)
├── Backups
│   ├── Hot backups (replica + snapshot)
│   ├── Cold backups (S3 Glacier, tape)
│   └── Disaster recovery region
├── Logs
│   ├── Application logs
│   ├── Audit logs
│   └── Access logs
├── Processors
│   ├── Email service provider
│   ├── Analytics provider
│   ├── CRM / Marketing automation
│   ├── Customer support (Zendesk, Intercom)
│   ├── Payment processor (per legal obligation, may not erase)
│   └── Cloud infrastructure (object storage, managed DB)
│       └── Sub-processors
├── Third-country recipients (Chapter V)
└── Paper / archive
```

Each branch requires a confirmed deletion or a documented justification for retention.

## 5. Special situations

### 5.1 Marketing erasure (Art. 21(2) + Art. 17(1)(c))

Direct marketing is the easiest case. The data subject's objection is **absolute**. Erasure is mandatory, with no balancing exercise. Add the contact to a suppression list (retained as proof of withdrawal, not as a marketing target).

### 5.2 Withdrawal of consent (Art. 17(1)(b))

Where consent was the lawful basis and is withdrawn, erasure is generally required unless another lawful basis applies. Note: legitimate interest cannot be relied upon to "rescue" data collected under consent.

### 5.3 Children's data

Children's data warrants heightened protection. Erasure of data collected when the user was a minor (under information society services) is grounded in Art. 17(1)(f). Apply minimum friction.

### 5.4 Public interest archiving (Art. 89)

Where data is retained for archiving in the public interest, scientific or historical research, or statistical purposes, the right may be restricted "in so far as the right referred to in [Art. 17(1)] is likely to render impossible or seriously impair the achievement of the objectives of that processing". Document the impossibility / serious impairment assessment. Apply pseudonymisation / aggregation to minimise retained personal data.

### 5.5 Free speech / journalism (Art. 17(3)(a) + Art. 85)

Member-state law balances data protection with freedom of expression. The Costeja decision and subsequent case law set principles for de-listing requests against search engines. In editorial contexts, the substantive content may persist while delisting attenuates discoverability.

### 5.6 Litigation hold

If the data is subject to active or reasonably anticipated litigation, the request is partially blocked under Art. 17(3)(e). Document the litigation hold scope and review periodically. When the hold lifts, erase the data within one month.

### 5.7 Technical impossibility

Rare. Document the specific technical impossibility, the compensating measures, and the expected resolution date. Examples:
- Immutable storage with regulatory retention (e.g., financial audit logs).
- Backup tapes off-site with no individual addressing.

In each case, apply Art. 18 restriction of processing and crypto-shred at next opportunity.

## 6. Quality assurance

| Activity | Frequency | Owner |
|---|---|---|
| Sample erasure request review | Monthly | DPO |
| Time-to-completion metric review | Quarterly | DPO |
| Recipient-notification verification | Monthly | DPO |
| Backup propagation audit | Quarterly | DPO + InfoSec |
| Processor erasure certificate review | Per request | DPO + Procurement |
| Annual procedure review | Annually | DPO |

## 7. Metrics and reporting

The DPO reports quarterly to the Executive Committee on:

- Volume of erasure requests received.
- Median and 95th percentile time-to-completion.
- Refusals (count, reasons).
- Partial fulfilments (count, reasons).
- Escalations (legal, supervisory authority involvement).
- Process-improvement findings.

## 8. Templates

### 8.1 Acknowledgement (within 5 business days)

> *Subject*: Acknowledgement of your erasure request — Reference [#####]
>
> Dear [Name],
>
> We confirm receipt of your request, dated [DATE], to erase personal data we hold about you under Article 17 of the GDPR.
>
> We will respond substantively within one month of receipt. If we need additional information to verify your identity or to clarify the scope, we will contact you.
>
> If your request is particularly complex, we may extend the response period by up to two further months and will inform you accordingly within the first month.
>
> [Reference number, contact details, supervisory authority complaint right.]

### 8.2 Identity verification request

> *Subject*: Identity verification for your erasure request — Reference [#####]
>
> Dear [Name],
>
> Before we can act on your request, we need to verify your identity to prevent unauthorised disclosure or destruction of personal data. Please provide:
>
> [Specific, proportionate verification — e.g., confirm your registered email address, last four digits of order ID, postal address on file].
>
> The one-month response period will resume once we have received the verification information.

### 8.3 Substantive response (granted)

> *Subject*: Outcome of your erasure request — Reference [#####]
>
> Dear [Name],
>
> Following your request dated [DATE], we have erased the personal data we held about you in accordance with Article 17 of the GDPR. Specifically, we have erased: [list categories].
>
> [If applicable: We have notified the following recipients of your erasure request: [list].]
>
> [If applicable: Some data has been retained on the following lawful basis: [explain].]
>
> You retain the right to lodge a complaint with the supervisory authority and to seek judicial remedy.

### 8.4 Substantive response (partial / refused)

> *Subject*: Outcome of your erasure request — Reference [#####]
>
> Dear [Name],
>
> Following your request dated [DATE], we have completed the erasure to the extent legally permissible. Specifically:
>
> - Erased: [list].
> - Retained: [list], because: [legal obligation / legal claims / archiving / public interest / freedom of expression / public health], for [period / until event].
>
> The retained data is restricted to the exempt purpose only. We will erase upon expiry / resolution.
>
> You retain the right to lodge a complaint with the supervisory authority and to seek judicial remedy.

---

## Türkçe

# Silme Hakkı (Madde 17)

Bu prosedür, ilgili kişilerden GDPR Madde 17 kapsamında alınan silme taleplerinin işlenmesini düzenler.

## 1. Hukuki dayanak

### 1.1 Hak (Md. 17(1))

Bir ilgili kişi, aşağıdakilerden biri uygulanırsa kişisel verisinin **gereksiz gecikme olmaksızın** silinmesini elde etme hakkına sahiptir:

| Dayanak | Açıklama |
|---|---|
| (a) | Veri, toplandığı veya başka şekilde işlendiği amaçlar için artık gerekli değildir. |
| (b) | İlgili kişi rızayı geri çeker ve işleme için başka hukuki dayanak yoktur. |
| (c) | İlgili kişi Md. 21(1) kapsamında itiraz eder ve geçersiz kılan meşru gerekçeler yoktur veya Md. 21(2) (doğrudan pazarlama) kapsamında itiraz eder. |
| (d) | Veri hukuka aykırı olarak işlenmiştir. |
| (e) | Kontrolörün tabi olduğu AB veya üye devlet hukukundaki bir hukuki yükümlülüğe uymak için veri silinmelidir. |
| (f) | Veri, çocuğa bilgi toplumu hizmetleri sunulmasıyla ilgili olarak toplanmıştır (Md. 8(1)). |

### 1.2 Muafiyetler (Md. 17(3))

Hak, işleme aşağıdakiler için gerekli olduğu ölçüde uygulanmaz:

| Muafiyet | Açıklama |
|---|---|
| (a) | İfade ve bilgi özgürlüğü hakkının kullanılması. |
| (b) | AB veya üye devlet hukukunda işlemeyi gerektiren bir hukuki yükümlülüğe uyum veya kamu yararı görevinin yerine getirilmesi veya resmi otoritenin kullanılması. |
| (c) | Halk sağlığı alanında kamu yararı sebepleri (Md. 9(2)(h) ve (i), Md. 9(3)). |
| (d) | Kamu yararı arşivlemesi, bilimsel veya tarihsel araştırma veya istatistiksel amaçlar (Md. 89(1)). |
| (e) | Hukuki taleplerin kurulması, kullanılması veya savunulması. |
| (f) | (Örtük) — Md. 23 kapsamında sınırlama (ulusal güvenlik, savunma, yargı bağımsızlığı vb.). |

### 1.3 Bildirim (Md. 19)

Kontrolör kişisel veriyi alıcılara açıkladıysa, herhangi bir silmeyi her alıcıya bildirir, bunun imkânsız olduğu veya orantısız çaba içerdiği durumlar hariç. Kontrolör, talep edilirse ilgili kişiye bu alıcılar hakkında bilgi verir.

### 1.4 Kamuya açıklık (Md. 17(2))

Kontrolör kişisel veriyi kamuya açıklamış ve silme yükümlülüğü altındaysa, kontrolör mevcut teknolojiyi ve uygulama maliyetini dikkate alarak, ilgili kişinin bağlantıların, kopyaların veya kopyalamaların silinmesini talep ettiğini veriyi işleyen diğer kontrolörlere bildirmek için teknik önlemler dahil **makul adımlar** atar.

### 1.5 Süre (Md. 12(3))

- Onay: mümkün olan en kısa sürede.
- Esaslı yanıt: alındığı tarihten itibaren **bir ay içinde**.
- Uzatma: karmaşık talepler için iki ay daha, ilk ay içinde ilgili kişiye sebep açıklaması bildirimi ile.

### 1.6 Ücretsiz (Md. 12(5))

Talepler açıkça temelsiz veya aşırı olmadıkça ücretsizdir. Tekrarlanan aynı talepler veya kötü niyetli amaçlı talepler, makul bir ücret veya reddi gerektirebilir — her ikisi de belgelenmiş gerekçe ile.

## 2. Prosedür

### 2.1 Alma ve onay

1. **Kanallar.** Silme talepleri şu yollarla gelebilir:
   - Gizlilik e-posta gelen kutusu (`privacy@[kuruluş]`).
   - İlgili kişi hakları portalı.
   - Posta mektubu.
   - Şahsen veya telefonla talep (alıcı tarafından kaydedilir ve yazılı olarak onaylanır).
   - Müşteri hizmetleri / destek talebi (DPO'ya iletilir).

2. **Kayıt.** Her talep İlgili Kişi Hakları Sicili'nde şunlarla kaydedilir:
   - Alındığı tarih ve kanal.
   - İlgili kişinin tanımlayıcı(ları) (ad, e-posta, müşteri kimliği).
   - Kapsam (tüm veri, belirli kategori, belirli kayıt).
   - Belirtilen dayanaklar (sağlanmışsa).
   - Atanmış vaka memuru.

3. **Onay.** Alındıktan sonraki 5 iş günü içinde, alındığını onaylayan ve yanıt penceresini özetleyen bir onay gönderin.

### 2.2 Kimlik doğrulama

Kontrolör, yetkisiz açıklama veya imhayı önlemek için talep edenin kimliğini doğrulamalıdır. Önerilen yaklaşım:

- **Mevcut müşteriler.** Hesaba bağlı kanal ile doğrulayın (oturum açılmış oturum, dosyada zaten bulunan kurtarma e-postası, müşteri hizmetleri telefon kimlik doğrulaması).
- **Müşteri olmayanlar / eski müşteriler.** Riskle orantılı ek doğrulama isteyin; aşırı toplama yapmayın.
- **Yetkili temsilciler.** Yetki kanıtı isteyin (yazılı yetkilendirme, mahkeme kararı, velayet sorumluluğu).
- **Çocuklar.** Özel özen; çocuk adına talep ediliyorsa velayet sorumlusunun kimliğini doğrulayın.

Kimlik doğrulanamazsa, kontrolör kimliği onaylamak için gereken ek bilgileri isteyebilir (Md. 12(6)). Kontrolörün makul olarak bu bilgiyi beklediği süre boyunca bir aylık saat duraklar.

### 2.3 Kapsam belirleme

Şunları belirleyin:

1. Talebin kapsadığı kişisel veri **ne** (tümü veya alt kümesi).
2. Verinin **nerede** bulunduğu (üretim DB'leri, yedekler, arşivler, işleyenler, alt-işleyenler, kâğıt, üçüncü ülke alıcıları).
3. Md. 17(3) muafiyetlerinden herhangi birinin kısmen veya tamamen uygulanıp uygulanmadığı.
4. Veriyi **hangi** alıcıların aldığı (Md. 19).

### 2.4 Hukuki dayanak incelemesi

Silmeden önce, Md. 17(3) muafiyetlerinden birinin silmeyi engelleyip engellemediğini değerlendirin:

- **Vergi / muhasebe / denetim yükümlülüğü.** Maaş kayıtları, faturalar, defterler — genellikle yasal minimum (örn. Almanya'da 10 yıl) için saklanır ve daha erken *silinemez*.
- **Hukuki talepler.** Aktif veya öngörülen dava varsa, sınırlama süresi için saklama gerekçelendirilir.
- **İfade özgürlüğü.** Yayın içeriği, gazetecilik. Costeja ve GC v CNIL ilkelerini uygulayın.
- **Kamu yararı arşivlemesi / araştırma.** Md. 89 koruyucu tedbirlerine tabi.
- **Halk sağlığı.** Md. 9(2)(h) işleme.

Bir muafiyet kısmen uygulanırsa, korunan **belirli alt kümeyi** tanımlayın ve geri kalanını silin. Tüm talebi reddetmeyin.

### 2.5 Silme uygulaması

Talep geçerli ve muaf olmadığı onaylandığında:

1. **Üretim.** `erasure-methods.md` başına üretim sistemlerindeki kayıtları sil veya anonimleştir.
2. **Replikalar.** Çoğaltmanın silmeyi yaydığını onayla (okuma replikaları, BI ambarı, arama indeksi).
3. **Önbellekler.** Zorla temizleme (CDN, uygulama, tarayıcı).
4. **Yedekler.** Yedek silme stratejisi uygula (`erasure-methods.md` §5). Artık saklama ve telafi edici kontrolleri belgele.
5. **Loglar.** Logların kişisel veri içerip içermediğini belirle; log yaşam döngüsüne göre takma adlandır veya sil.
6. **İşleyenler.** Her işleyene yazılı bildirim; yazılı onay isteyin; DPA ile takip edin.
7. **Alt-işleyenler.** İşleyenin yaydığını doğrulayın.
8. **Üçüncü ülke transferleri.** Md. 19 kapsamında alıcıya bildirim; geçerli Bölüm V mekanizması başına doğrulayın.
9. **Kâğıt.** DIN 66399 altında bul ve imha et.
10. **Uç noktalar.** Kişisel veri belirli bir çalışanın cihazındaysa, sanitasyonu talimatlandır.

### 2.6 Alıcılara bildirim (Md. 19)

Veriyi alan her alıcı için:
- Alıcıyı ve açıklama tarihini tanımlayın.
- Silinecek veriyi belirten yazılı bildirim gönderin.
- Onayı izleyin; 14 gün içinde yanıt yoksa eskalasyon yapın.
- İlgili Kişi Hakları Sicili'nde belgeleyin.

### 2.7 Kamuya açıklık (Md. 17(2))

Kişisel veri kamuya açıklanmışsa:
- Bilinen tüm yansıma veya kopya konumlarını tanımlayın (arama motorları, sendikasyon ortakları, arşiv hizmetleri).
- Geçerli olduğunda kaldırma / dereferans talepleri gönderin (örn. Google "Unutulma hakkı" talepleri).
- Atılan makul adımları belgeleyin.

### 2.8 İlgili kişiye yanıt

Alındıktan sonra bir ay içinde (veya uzatılmış süre içinde), şunları içeren yazılı bir yanıt gönderin:

- Silmenin onayı (ve kapsamı).
- Silinmemiş herhangi bir verinin tanımlanması ve saklamanın hukuki dayanağı.
- Md. 19 kapsamında bildirilen alıcılar hakkında bilgi (talep edilirse).
- Denetim makamına şikâyet etme hakkı.
- Yargısal çareye başvurma hakkı.
- Takip soruları için iletişim bilgileri.

### 2.9 Eylem kaydı

İlgili Kişi Hakları Sicili'ni şunlarla güncelleyin:

- Karar (kabul / kısmen kabul / reddedildi).
- Tamamlanma tarihi.
- Silinen kategoriler.
- Korunan kategoriler (hukuki dayanak ile).
- Bildirilen alıcılar.
- Silme kanıtı (imha kayıt referansı).
- Tamamlanma süresi metriği.

Kayıt Saklama Çizelgesine göre saklanır (tip. 3 yıl).

## 3. Reddetme ve kısmi reddetme

### 3.1 Açıkça temelsiz veya aşırı

Talep açıkça temelsiz veya aşırıysa (Md. 12(5)):

- Değerlendirme kriterlerini belgele (sıklık, içerik, niyet).
- Seçim: makul bir ücret talep et VEYA reddet.
- Sebepleri sağlayın.
- İlgili kişiyi denetim makamına şikâyet etme ve yargısal çareye başvurma hakkı konusunda bilgilendirin.

### 3.2 Muaf veri

Md. 17(3) kapsamında muaf veri için:

- Belirli muafiyeti tanımlayın (hukuki yükümlülük, hukuki talepler, kamu yararı, arşivleme, ifade özgürlüğü, halk sağlığı).
- Belirli veriyi ve minimum saklamayı tanımlayın.
- Muafiyet dışındaki herhangi bir veriyi silin.
- Korunan verinin işlenmesini yalnızca muaf amaca kısıtlayın (Md. 18 uygulanabilir).
- İlgili kişiyi kısmi sonuç ve sebepler hakkında bilgilendirin.

### 3.3 Kimlik doğrulanmadı

Makul ek bilgi taleplerine rağmen kimlik doğrulanamazsa:

- Hareket etmeyi reddedin (yetkisiz imha riskini alamayız).
- Doğrulanmamış kimlik değerlendirmesini belgele.
- İlgili kişiyi ek doğrulama ile yeniden deneme hakkı konusunda bilgilendirin.

## 4. Sistemler arasında silme yayma

Bir ilgili kişinin kaydının "silme yarıçapı":

```
İlgili kişi kaydı
├── Birincil veritabanı (üretim)
│   ├── Okuma replikaları
│   ├── BI ambarı / veri gölü
│   ├── Arama indeksi
│   └── Önbellek katmanı (CDN, uyg)
├── Yedekler
│   ├── Sıcak yedekler (replika + snapshot)
│   ├── Soğuk yedekler (S3 Glacier, bant)
│   └── Felaket kurtarma bölgesi
├── Loglar
│   ├── Uygulama logları
│   ├── Denetim logları
│   └── Erişim logları
├── İşleyenler
│   ├── E-posta hizmet sağlayıcı
│   ├── Analitik sağlayıcı
│   ├── CRM / Pazarlama otomasyonu
│   ├── Müşteri desteği (Zendesk, Intercom)
│   ├── Ödeme işleyici (hukuki yükümlülük başına silmeyebilir)
│   └── Bulut altyapısı (nesne depolama, yönetilen DB)
│       └── Alt-işleyenler
├── Üçüncü ülke alıcıları (Bölüm V)
└── Kâğıt / arşiv
```

Her dal, onaylanmış bir silme veya saklama için belgelenmiş bir gerekçe gerektirir.

## 5. Özel durumlar

### 5.1 Pazarlama silmesi (Md. 21(2) + Md. 17(1)(c))

Doğrudan pazarlama en kolay vakadır. İlgili kişinin itirazı **mutlaktır**. Silme zorunludur, denge alıştırması yoktur. Kişiyi bir baskı listesine ekleyin (geri çekilme kanıtı olarak saklanır, pazarlama hedefi olarak değil).

### 5.2 Rıza geri çekilmesi (Md. 17(1)(b))

Rıza hukuki dayanak olduğunda ve geri çekildiğinde, başka bir hukuki dayanak uygulanmadıkça silme genellikle gereklidir. Not: meşru menfaat, rıza altında toplanan veriyi "kurtarmak" için dayanılamaz.

### 5.3 Çocuk verisi

Çocuk verisi yüksek koruma hak eder. Kullanıcı reşit olmadığında (bilgi toplumu hizmetleri altında) toplanan verinin silinmesi Md. 17(1)(f)'de temellidir. Minimum sürtünme uygulayın.

### 5.4 Kamu yararı arşivlemesi (Md. 89)

Veri kamu yararı arşivlemesi, bilimsel veya tarihsel araştırma veya istatistiksel amaçlar için saklanıyorsa, hak "[Md. 17(1)] hakkın bu işlemenin amaçlarının elde edilmesini imkânsız kılması veya ciddi şekilde zayıflatması olası olduğu ölçüde" sınırlandırılabilir. İmkânsızlık / ciddi zayıflama değerlendirmesini belgeleyin. Korunan kişisel veriyi minimuma indirmek için takma adlandırma / toplama uygulayın.

### 5.5 İfade özgürlüğü / gazetecilik (Md. 17(3)(a) + Md. 85)

Üye devlet hukuku veri korumasını ifade özgürlüğüyle dengeler. Costeja kararı ve sonraki içtihat, arama motorlarına karşı listeden çıkarma talepleri için ilkeler belirler. Yayın bağlamlarında, esaslı içerik kalmaya devam edebilirken listeden çıkarma keşfedilebilirliği zayıflatır.

### 5.6 Dava bekletme

Veri aktif veya makul olarak öngörülen davaya tabiyse, talep Md. 17(3)(e) kapsamında kısmen engellenir. Dava bekletme kapsamını belgele ve periyodik olarak gözden geçir. Bekletme kalktığında, veriyi bir ay içinde sil.

### 5.7 Teknik imkânsızlık

Nadir. Belirli teknik imkânsızlığı, telafi edici önlemleri ve beklenen çözüm tarihini belgele. Örnekler:
- Düzenleyici saklama ile değişmez depolama (örn. finansal denetim logları).
- Site dışı yedek bantları, bireysel adresleme yok.

Her durumda, Md. 18 işleme kısıtlaması uygula ve bir sonraki fırsatta kripto-parçala.

## 6. Kalite güvencesi

| Faaliyet | Sıklık | Sahip |
|---|---|---|
| Örnek silme talebi incelemesi | Aylık | DPO |
| Tamamlanma süresi metriği incelemesi | Üç ayda | DPO |
| Alıcı bildirim doğrulaması | Aylık | DPO |
| Yedek yayma denetimi | Üç ayda | DPO + InfoSec |
| İşleyen silme sertifikası incelemesi | Talep başına | DPO + Tedarik |
| Yıllık prosedür incelemesi | Yıllık | DPO |

## 7. Metrikler ve raporlama

DPO Yönetim Komitesine üç ayda bir raporlar:

- Alınan silme taleplerinin hacmi.
- Ortanca ve 95. yüzdebirlik tamamlanma süresi.
- Reddetmeler (sayı, sebepler).
- Kısmi yerine getirmeler (sayı, sebepler).
- Eskalasyonlar (hukuk, denetim makamı katılımı).
- Süreç iyileştirme bulguları.

## 8. Şablonlar

### 8.1 Onay (5 iş günü içinde)

> *Konu*: Silme talebinizin onayı — Referans [#####]
>
> Sayın [İsim],
>
> [TARİH] tarihli, hakkınızda tuttuğumuz kişisel verileri GDPR'nin 17. Maddesi kapsamında silme talebinizi aldığımızı onaylarız.
>
> Alındıktan sonra bir ay içinde esaslı olarak yanıt vereceğiz. Kimliğinizi doğrulamak veya kapsamı netleştirmek için ek bilgiye ihtiyacımız olursa, sizinle iletişime geçeceğiz.
>
> Talebiniz özellikle karmaşıksa, yanıt süresini iki ay daha uzatabiliriz ve sizi ilk ay içinde buna göre bilgilendireceğiz.
>
> [Referans numarası, iletişim bilgileri, denetim makamı şikâyet hakkı.]

### 8.2 Kimlik doğrulama talebi

> *Konu*: Silme talebiniz için kimlik doğrulaması — Referans [#####]
>
> Sayın [İsim],
>
> Talebiniz üzerine harekete geçmeden önce, kişisel verilerin yetkisiz açıklanmasını veya imhasını önlemek için kimliğinizi doğrulamamız gerekiyor. Lütfen şunları sağlayın:
>
> [Belirli, orantılı doğrulama — örn. kayıtlı e-posta adresinizi, sipariş kimliğinin son dört rakamını, dosyada bulunan posta adresini onaylayın].
>
> Doğrulama bilgisini aldığımızda bir aylık yanıt süresi devam edecektir.

### 8.3 Esaslı yanıt (kabul edildi)

> *Konu*: Silme talebinizin sonucu — Referans [#####]
>
> Sayın [İsim],
>
> [TARİH] tarihli talebiniz üzerine, GDPR'nin 17. Maddesi uyarınca hakkınızda tuttuğumuz kişisel verileri sildik. Spesifik olarak şunları sildik: [kategorileri listeleyin].
>
> [Geçerliyse: Silme talebinizi şu alıcılara bildirdik: [listele].]
>
> [Geçerliyse: Bazı veriler şu hukuki dayanak ile saklanmıştır: [açıklayın].]
>
> Denetim makamına şikâyet etme ve yargısal çareye başvurma hakkını saklı tutarsınız.

### 8.4 Esaslı yanıt (kısmi / reddedildi)

> *Konu*: Silme talebinizin sonucu — Referans [#####]
>
> Sayın [İsim],
>
> [TARİH] tarihli talebiniz üzerine, hukuken izin verilen ölçüde silmeyi tamamladık. Spesifik olarak:
>
> - Silindi: [listele].
> - Korundu: [listele], çünkü: [hukuki yükümlülük / hukuki talepler / arşivleme / kamu yararı / ifade özgürlüğü / halk sağlığı], [süre / olay sona erene kadar].
>
> Korunan veri yalnızca muaf amaca kısıtlanır. Sona erme / çözümün ardından silindiğinizde sileceğiz.
>
> Denetim makamına şikâyet etme ve yargısal çareye başvurma hakkını saklı tutarsınız.
