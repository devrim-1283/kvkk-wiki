---
title:
  en: "Data Subject Rights — End-to-End Procedure"
  tr: "İlgili Kişi Hakları — Uçtan Uca Prosedür"
section: "09-data-subject-rights"
document_id: "DSR-PROC-001"
owner: "Data Protection Officer"
classification: "Internal"
version: "1.0"
last_review: "2026-05-08"
next_review: "2027-05-08"
language: ["en", "tr"]
references:
  - "GDPR Art. 12(1)–(8) — Modalities for the exercise of rights"
  - "GDPR Art. 11 — Processing not requiring identification"
  - "GDPR Art. 15–22 — Individual rights"
  - "EDPB Guidelines 01/2022 on data subject rights — Right of access"
  - "EDPB Guidelines 4/2019 on Article 25 — Data Protection by Design and by Default"
  - "Recital 64 — Identity verification"
---

## English

### 1. Purpose

This procedure defines the end-to-end workflow for receiving, verifying, processing, deciding, responding to, and archiving any data subject rights (DSR) request under Articles 12 to 22 GDPR. It is mandatory for all employees and contractors of the controller and binding on processors via Article 28(3)(e) clauses.

### 2. Article 12 — modalities

Article 12(1) requires the controller to provide information and communications relating to the exercise of rights in a concise, transparent, intelligible, and easily accessible form, using clear and plain language, in particular for any information addressed specifically to a child. Article 12(2) requires the controller to facilitate the exercise of rights, and 12(3) sets the one-month deadline (extendable by two months for complexity or volume).

This procedure operationalises those obligations.

### 3. Channels for receiving requests

The controller accepts DSR requests through any channel a reasonable person might use:

- **Postal mail** to the registered address of the controller.
- **Email** to the dedicated mailbox `dsr@<controller-domain>` and any other published channel.
- **In-person** at any physical office during business hours; staff record the request and forward to the DPO immediately.
- **Web form** at `<controller-website>/privacy/rights`.
- **Telephone** to the published privacy hotline; the agent records the request in writing and confirms it back to the requester.
- **Authenticated in-app** flow inside the controller's products.
- **Through the controller's representative** (Article 27) for non-EU controllers.
- **Through a third party** acting on behalf of the data subject (lawyer, advocacy organisation, family member with valid mandate).

A request received in any reasonable form must not be rejected for being on the "wrong" channel. The receiving employee is obliged to forward it to the DPO. Failure to forward is a disciplinary matter.

EDPB 01/2022 §52 emphasises that channel availability must not become a hidden obstacle. Channels that exist only in fine print, or behind authentication that the requester does not have, do not count.

### 4. Triage

Within 2 working days of receipt, the DPO office triages each request. Triage outputs:

| Output | Description |
|--------|------------|
| Case ID | `DSR-YYYY-NNNN` |
| Right(s) invoked | Art. 15 / 16 / 17 / 18 / 19 / 20 / 21 / 22; multiple possible |
| Requester role | Data subject directly / Authorised representative / Lawyer / Other |
| Identity verification path | Tier 1 / 2 / 3 / 4 (see `sla-workflow.md`) |
| Initial scope | Estimate of records, systems, controllers involved |
| Joint controller? | If yes, identify other controller and notify per JCA |
| Processor involvement | Which processors hold relevant data |
| Statutory deadline | Receipt date + 1 month |
| Extension assessment | Initial view on whether 12(3) extension may be needed |

The triage is recorded in the DSR case management system. The acknowledgement letter is dispatched within the same 2-working-day window (see `response-letter-templates.md`).

### 5. Identity verification

#### 5.1 Principle

Article 12(6) permits the controller to request additional information necessary to confirm identity where there are reasonable doubts concerning the identity of the natural person making the request. Recital 64 confirms that the controller should use all reasonable measures to verify identity, in particular in the context of online services and online identifiers. EDPB 01/2022 §70 stresses proportionality: identity verification must be proportionate to the risk of disclosure to the wrong person, must not be used to discourage legitimate requests, and must not result in over-collection of personal data.

#### 5.2 Risk-tiered verification

The procedure uses four tiers (detailed in `sla-workflow.md`):

| Tier | Use case | Verification |
|------|---------|--------------|
| 1 | Authenticated session inside our product | Existing session is sufficient; no additional ask |
| 2 | Email channel where requester writes from email address on file | Reply-to verification with one factor (e.g. last 4 digits of customer ID, last invoice month) |
| 3 | Email/postal where requester is unknown to us, or claims sensitive identifiers | Two factors from a defined list; never a copy of national ID by default |
| 4 | High-risk: special-category data, very large dataset, deceased subject's heir, lawyer acting for someone | Documented verification including ID document review (with redaction) and lawyer's mandate |

#### 5.3 What we do not ask for

We do not, by default, ask for:
- a copy of the national ID card or passport;
- biometric data;
- information not already on file with us;
- documents that are disproportionate to the request.

If a copy of an ID document is genuinely necessary (Tier 4), we explain why, accept redaction (cover everything except name + photo), retain the copy only as long as necessary to verify, and delete with audit trail. EDPB 01/2022 §72 confirms ID copies are an exception, not a default.

#### 5.4 Article 11 — processing not requiring identification

If the controller's processing genuinely does not allow identification of the requester from the data held, Article 11 applies: the controller may inform the requester of this and, unless the requester provides further information, the controller is not obliged to comply with Articles 15 to 20. This is rare in practice and must not be invoked to evade rights where identification is in fact possible.

### 6. Scope determination

For each request, the DPO determines:

- Which systems hold personal data of the requester (using the ROPA inventory and account-to-system mapping).
- Which processors must be queried under Article 28(3)(e).
- Which related natural or legal persons appear in those records (their rights under Article 15(4), 17, etc.).
- Which retention rules apply (legal holds, statutory retention).
- Which categories of data are involved (Article 9 special categories require additional care).

The scope memo is recorded in the case file.

### 7. Legal review

For complex cases, the DPO consults Legal:

- requests from claimants in litigation;
- requests where Article 23 national law derogations may apply;
- requests where data of third parties is interleaved with the requester's data;
- erasure requests where Article 17(3) exemptions are claimed;
- requests touching trade secrets, intellectual property, or competing rights.

Legal review is documented in the case file. Privileged advice is marked accordingly.

### 8. Decision

The DPO records the decision with reasons. The decision is one of:

| Outcome | Meaning |
|---------|---------|
| Grant in full | The right is exercised as requested |
| Grant in part | The right is exercised partially; the rest is refused with reasons |
| Refuse | The right is refused with reasons |
| Deny under Article 12(5) | Request is manifestly unfounded or excessive; refusal or fee |
| Defer | A statutory exemption (e.g. legal hold) suspends; revisit on schedule |

Refusals are reviewed by the DPO; partial responses are reviewed where the refusal element is material.

### 9. Response

The response is delivered:

- Through the channel the requester chose, unless they specified another.
- In the language they used, with bilingual response where appropriate.
- In writing or electronically as appropriate; orally if the requester so requests and identity is verified (Article 12(1)).
- For Article 15 access, accompanied by the categories of data, sources, recipients, retention, rights, and a copy of the data being processed (12(1) sentence 2 and 15(3)).
- For Article 20 portability, in a structured, commonly used, machine-readable format (e.g. JSON, CSV).

A response that meets the deadline but is incomplete is treated as a partial response and remains open in the system.

### 10. Article 19 — notification to recipients

After Article 16, 17, or 18 actions, the controller communicates the rectification, erasure, or restriction to each recipient to whom the personal data have been disclosed, unless this proves impossible or involves disproportionate effort. The data subject may ask for the list of recipients; we provide it unless an applicable exemption applies.

### 11. Article 12(3) extension

The one-month deadline may be extended by a further two months where necessary, taking into account the complexity and number of the requests. Within the original one month the controller must inform the requester of the extension and the reasons for it. The reasons must be specific to the case, not boilerplate.

### 12. Free of charge — and the exceptions

Article 12(5) makes responses free of charge. Where requests are manifestly unfounded or excessive, in particular because of their repetitive character, the controller may either charge a reasonable fee or refuse to act. The burden of demonstrating manifest unfoundedness or excessiveness is on the controller (Article 12(5) sentence 2). EDPB 01/2022 §183 cautions that the bar is high; it is not a tool to deter rights exercise. See `fees-and-exceptions.md` for the framework.

### 13. Right of complaint

Every response (including refusals) informs the requester of the right to lodge a complaint with the supervisory authority and the right to a judicial remedy.

### 14. Closure and archive

When the response is dispatched and any follow-up is closed, the case is archived. The case file retains:

- the original request;
- triage and identity verification artefacts;
- scope memo;
- legal review (if any);
- decision memo;
- response artefact (PDF of letter, JSON of portability data, etc.);
- evidence of dispatch and acknowledgement;
- audit log of system actions taken.

Retention of the case file follows section `12-legal-archive` rules: typically the longer of 3 years from closure or any applicable statute of limitations for related claims. Personal data of the requester within the case file is itself subject to data protection — specifically, retention beyond minimal necessary periods must be justified.

### 15. Special situations

#### 15.1 Deceased persons

GDPR does not apply to the personal data of deceased persons (Recital 27), but Member State law may extend protections (e.g. France's loi Informatique et Libertés Art. 84). The controller responds in accordance with applicable national law and any heir mandate.

#### 15.2 Children

Where the data subject is a child, requests are processed with extra care for the child's understanding. Parental or guardian rights may apply, balanced against the child's evolving capacity.

#### 15.3 Joint controllers

Under Article 26, the joint controllers' arrangement must designate a contact point. Even where one controller is designated, the data subject may exercise rights against either controller (Article 26(3)). Internal coordination must not delay the response.

#### 15.4 Processor-held data

Under Article 28(3)(e), the processor must assist the controller in fulfilling rights requests. The DPA defines the response time the processor commits to; the controller's overall deadline does not pause for the processor.

### 16. Quality control

The DPO reviews 100% of refusals and a 10% sample of granted responses each quarter. Findings feed into training and procedure updates.

### 17. Training

Every employee with customer contact receives annual DSR awareness training. Specialist DSR handlers receive deeper training including practical case studies. The DPO maintains the curriculum.

---

## Türkçe

### 1. Amaç

Bu prosedür, GDPR Madde 12 ila 22 kapsamındaki herhangi bir ilgili kişi hakları (DSR) talebinin alınması, doğrulanması, işlenmesi, karara bağlanması, yanıtlanması ve arşivlenmesi için uçtan uca iş akışını tanımlar. Veri sorumlusunun tüm çalışanları ve yüklenicileri için zorunludur ve Madde 28(3)(e) hükümleri aracılığıyla veri işleyenler için bağlayıcıdır.

### 2. Madde 12 — modaliteler

Madde 12(1), veri sorumlusunun hakların kullanılmasıyla ilgili bilgi ve iletişimleri özlü, şeffaf, anlaşılır ve kolay erişilebilir bir biçimde, açık ve sade bir dil kullanarak sağlamasını gerektirir. Madde 12(2) hakların kullanımının kolaylaştırılmasını gerektirir ve 12(3) bir aylık süreyi (karmaşıklık veya hacim için iki ay uzatılabilir) belirler.

### 3. Talep alma kanalları

Veri sorumlusu, makul bir kişinin kullanabileceği herhangi bir kanal üzerinden DSR taleplerini kabul eder:

- **Posta** — veri sorumlusunun tescilli adresine.
- **E-posta** — `dsr@<controller-domain>` özel posta kutusu ve yayımlanmış diğer kanallar.
- **Yüz yüze** — herhangi bir fiziksel ofiste mesai saatleri içinde.
- **Web formu** — `<controller-website>/privacy/rights`.
- **Telefon** — yayımlanmış mahremiyet hattı.
- **Kimlik doğrulamalı uygulama içi** akış.
- **Veri sorumlusunun temsilcisi** (Madde 27) aracılığıyla.
- **Üçüncü taraf** aracılığıyla (avukat, savunuculuk kuruluşu, geçerli vekaletli aile üyesi).

Makul herhangi bir biçimde alınan bir talep "yanlış" kanalda olduğu için reddedilmemelidir. Alıcı çalışan bunu VKK'ya iletmek zorundadır.

### 4. Triyaj

Alındıktan sonra 2 iş günü içinde VKK ofisi her talebi triyaj eder. Triyaj çıktıları:

| Çıktı | Açıklama |
|-------|----------|
| Dosya kimliği | `DSR-YYYY-NNNN` |
| Çağrılan hak(lar) | Madde 15 / 16 / 17 / 18 / 19 / 20 / 21 / 22; çoklu mümkün |
| Talep eden rolü | Doğrudan ilgili kişi / Yetkili temsilci / Avukat / Diğer |
| Kimlik doğrulama yolu | Aşama 1 / 2 / 3 / 4 |
| İlk kapsam | Kayıtların, sistemlerin, dahil veri sorumlularının tahmini |
| Ortak veri sorumlusu? | Evet ise diğerini belirleyin ve OVS'ye göre bilgilendirin |
| Veri işleyen katılımı | Hangi veri işleyenler ilgili veriyi tutuyor |
| Yasal son tarih | Alış tarihi + 1 ay |
| Uzatma değerlendirmesi | 12(3) uzatması gerekli olabilir mi |

### 5. Kimlik doğrulama

#### 5.1 İlke

Madde 12(6), talep eden gerçek kişinin kimliği konusunda makul şüpheler olduğunda veri sorumlusunun kimliği teyit etmek için gerekli ek bilgileri talep etmesine izin verir. Resital 64, veri sorumlusunun kimliği doğrulamak için tüm makul önlemleri kullanması gerektiğini teyit eder. EDPB 01/2022 §70 orantılılığı vurgular.

#### 5.2 Risk seviyeli doğrulama

| Aşama | Kullanım durumu | Doğrulama |
|-------|----------------|-----------|
| 1 | Ürünümüz içinde kimlik doğrulamalı oturum | Mevcut oturum yeterli |
| 2 | Dosyada bulunan e-posta adresinden gelen e-posta | Bir faktörlü cevap doğrulaması |
| 3 | Bilinmeyen talep eden veya hassas tanımlayıcı iddia | Tanımlanmış listeden iki faktör |
| 4 | Yüksek risk: özel kategori, çok büyük veri kümesi, vefat eden ilgili kişinin mirasçısı, başkası adına avukat | Kimlik belgesi incelemesi (redaksiyonla) ve avukat vekaleti dahil belgelenmiş doğrulama |

#### 5.3 Talep etmediğimiz şeyler

Varsayılan olarak istemediğimiz şeyler:
- Kimlik kartı veya pasaport kopyası;
- Biyometrik veri;
- Bizde mevcut olmayan bilgiler;
- Talep ile orantısız belgeler.

#### 5.4 Madde 11 — kimlik gerektirmeyen işleme

Veri sorumlusunun işlemesi gerçekten talep edenin kimliğinin tutulan verilerden tanımlanmasına izin vermiyorsa, Madde 11 uygulanır.

### 6. Kapsam belirleme

Her talep için VKK aşağıdakileri belirler:

- Hangi sistemler talep edenin kişisel verilerini tutar.
- Madde 28(3)(e) altında hangi veri işleyenlerin sorgulanması gerekir.
- Hangi ilgili gerçek veya tüzel kişiler bu kayıtlarda yer alır.
- Hangi saklama kuralları uygulanır.
- Hangi veri kategorileri dahildir.

### 7. Hukuk incelemesi

Karmaşık vakalar için VKK Hukuk'a danışır.

### 8. Karar

VKK kararı gerekçeleriyle kaydeder:

| Sonuç | Anlam |
|-------|-------|
| Tam kabul | Hak talep edildiği gibi kullanılır |
| Kısmi kabul | Hak kısmen kullanılır; geri kalanı gerekçelerle reddedilir |
| Ret | Hak gerekçelerle reddedilir |
| Madde 12(5) altında reddet | Açıkça asılsız veya aşırı |
| Erteleme | Yasal muafiyet askıya alır |

### 9. Yanıt

Yanıt:

- Talep edenin seçtiği kanal üzerinden teslim edilir.
- Kullandıkları dilde, uygun olduğunda iki dilli.
- Madde 15 erişim için, veri kategorileri, kaynaklar, alıcılar, saklama, haklar ve işlenen verinin bir kopyasıyla birlikte.
- Madde 20 taşınabilirlik için, yapılandırılmış, yaygın olarak kullanılan, makine tarafından okunabilir bir formatta (örn. JSON, CSV).

### 10. Madde 19 — alıcılara bildirim

Madde 16, 17 veya 18 eylemlerinden sonra, veri sorumlusu düzeltme, silme veya kısıtlamayı kişisel verilerin ifşa edildiği her alıcıya iletir.

### 11. Madde 12(3) uzatması

Bir aylık süre, taleplerin karmaşıklığını ve sayısını dikkate alarak gerektiğinde iki ay daha uzatılabilir. Orijinal bir ay içinde veri sorumlusu, talep edeni uzatma ve nedenleri hakkında bilgilendirmelidir.

### 12. Ücretsiz — ve istisnalar

Madde 12(5), yanıtların ücretsiz olduğunu belirler. Talepler açıkça asılsız veya aşırı olduğunda, özellikle tekrarlayan nitelikleri nedeniyle, veri sorumlusu ya makul bir ücret talep edebilir ya da işlem yapmayı reddedebilir.

### 13. Şikayet hakkı

Her yanıt (retler dahil) talep edeni denetim makamına şikayette bulunma ve adli çözüm hakları konusunda bilgilendirir.

### 14. Kapatma ve arşiv

Yanıt gönderildiğinde ve tüm takipler kapatıldığında, dosya arşivlenir.

### 15. Özel durumlar

#### 15.1 Vefat etmiş kişiler

GDPR vefat etmiş kişilerin kişisel verilerine uygulanmaz, ancak Üye Devlet hukuku korumaları genişletebilir.

#### 15.2 Çocuklar

İlgili kişi çocuk olduğunda, talepler çocuğun anlayışı için ekstra özenle işlenir.

#### 15.3 Ortak veri sorumluları

Madde 26 altında, ortak veri sorumluları düzenlemesi bir iletişim noktası belirlemelidir.

#### 15.4 Veri işleyenin tuttuğu veri

Madde 28(3)(e) altında, veri işleyen, hak taleplerinin yerine getirilmesinde veri sorumlusuna yardım etmelidir.

### 16. Kalite kontrolü

VKK her çeyrekte tüm retlerin %100'ünü ve verilen yanıtların %10 örneğini inceler.

### 17. Eğitim

Müşteri ile teması olan her çalışan yıllık DSR farkındalık eğitimi alır.
