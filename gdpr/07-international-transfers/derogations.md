---
title:
  en: "Article 49 Derogations"
  tr: "Madde 49 İstisnaları"
section: "07-international-transfers"
document_type: "procedure"
regulation: "GDPR (EU 2016/679)"
articles:
  - "Art. 44 — General principle"
  - "Art. 49 — Derogations for specific situations"
key_guidance:
  - "EDPB Guidelines 2/2018 — Derogations of Article 49 under Regulation 2016/679"
  - "Recital 111, 112, 113"
language: "en, tr"
last_reviewed: "2025-05-01"
review_cycle: "annual"
owner: "Data Protection Officer"
co_owner: "Legal"
status: "approved"
classification: "internal"
---

## English

# Article 49 Derogations

## 1. Status

Article 49 derogations are the **last resort** in Chapter V. They apply only where:

- There is no Article 45 adequacy decision; and
- There are no Article 46 appropriate safeguards (or they cannot be put in place).

The EDPB Guidelines 2/2018 confirm this hierarchy. Derogations must be **narrowly construed** and not used routinely or as a back-door to avoid SCCs / BCRs.

## 2. The grounds

Article 49(1) lists the grounds:

| Ground | Description |
|---|---|
| (a) | The data subject has **explicitly consented** to the proposed transfer, after having been informed of the possible risks of such transfers due to the absence of an adequacy decision and appropriate safeguards. |
| (b) | The transfer is necessary for the **performance of a contract** between the data subject and the controller or the implementation of pre-contractual measures taken at the data subject's request. |
| (c) | The transfer is necessary for the **conclusion or performance of a contract concluded in the interest of the data subject** between the controller and another natural or legal person. |
| (d) | The transfer is necessary for **important reasons of public interest**. |
| (e) | The transfer is necessary for the **establishment, exercise or defence of legal claims**. |
| (f) | The transfer is necessary in order to **protect the vital interests** of the data subject or of other persons, where the data subject is physically or legally incapable of giving consent. |
| (g) | The transfer is made from a **register** which according to Union or Member State law is intended to provide information to the public and is open to consultation. |

Article 49(1) second subparagraph adds a residual derogation: where none of the above apply, transfer **may** take place if it is not repetitive, concerns only a limited number of data subjects, is necessary for compelling legitimate interests of the controller not overridden by the data subject's interests, and is **with notification to the supervisory authority and to the data subject**.

## 3. Common requirements

All derogations share characteristics:

### 3.1 Necessity

The transfer must be **strictly necessary** for the purpose. Convenient ≠ necessary. The exporter must be able to demonstrate that no less-intrusive means achieves the same purpose.

### 3.2 Specific situation / occasional and non-repetitive

Recital 111 confirms that derogations apply to **occasional** transfers. Repeated, regular, structural transfers must rely on Articles 45 or 46 instead. The EDPB Guidelines 2/2018 emphasise:

- "Occasional" → not regular, not pre-determined, not part of a routine process.
- "Non-repetitive" → not predictable in pattern.

A processor who systematically transfers customer data to a US sub-processor cannot rely on Article 49.

### 3.3 Documentation

Even though derogations are exceptional, the controller must document:

- The specific ground relied upon.
- The necessity assessment.
- The proportionality assessment.
- The information given to the data subject (where applicable).
- The risk briefing (especially for consent-based derogations).
- The DPO opinion.

## 4. Derogation by derogation

### 4.1 Article 49(1)(a) — Explicit consent

Conditions:

- **Explicit**: the data subject must have given a clear, specific affirmative action explicitly to a transfer to a specific third country / international organisation / specific processor.
- **Informed**: the data subject must be told:
  - The identity of the recipient(s).
  - The countries involved.
  - The purpose of the transfer.
  - **The specific risks** arising from the absence of adequacy and safeguards (e.g., government access, no equivalent redress).
- **Freely given**: imbalances of power matter (employees, public authority).
- **Withdrawable**: at any time, without detriment.

Pitfalls:

- Generic privacy-policy consent for "transfers to non-EU countries" is **not** explicit consent under 49(1)(a) — it is too vague.
- Bundling with broader consent fails the "specific" test.
- Pre-ticked boxes are invalid.
- Employees rarely give valid consent due to power imbalance (use 49(1)(b) or another mechanism).

### 4.2 Article 49(1)(b) — Performance of a contract with the data subject

Conditions:

- The contract is between the data subject and the controller.
- The transfer is **necessary** to perform the contract or pre-contractual steps **at the data subject's request**.

Pitfalls:

- "Necessary" is strictly construed. Mere convenience for the controller does not qualify.
- Onward / ancillary transfers (e.g., to a marketing analytics processor) usually fail necessity.
- Recital 111 confirms occasional nature.

Example: A user buying a product from an EU site asks for delivery to a third country. Sending the address to a non-EU shipper is necessary.

### 4.3 Article 49(1)(c) — Contract in the data subject's interest

Conditions:

- A contract concluded in the interest of the data subject between the controller and a third party.
- The transfer is necessary for the contract's conclusion or performance.

Example: An EU travel agency books a hotel reservation in a third country on behalf of a customer; transmitting the customer's identity and payment details to the hotel is necessary in their interest.

### 4.4 Article 49(1)(d) — Important reasons of public interest

Conditions:

- The public interest must be recognised in EU or member-state law (Recital 112).
- The interest is **important** — beyond ordinary public-policy considerations.

Examples:

- Tax-cooperation agreements between authorities.
- Customs cooperation.
- International transfers between data-protection authorities.
- Cooperation in fighting cross-border fraud or organised crime (subject to adequacy framework).

The Recital makes clear that this derogation does not apply to private-sector controllers' general public-interest claims; the public interest must be in EU / member-state law.

### 4.5 Article 49(1)(e) — Legal claims

Conditions:

- Necessary for the establishment, exercise, or defence of legal claims.
- Includes proceedings before public authorities (court, regulator, arbitral tribunal).
- Includes pre-action investigations.

Example: A data subject is sued in a third-country court; the EU-side controller transfers documents necessary for the defence.

Conflict zone: US e-discovery in foreign litigation. The EDPB Guidelines 2/2018 limit reliance: data must be necessary, proportionate, and minimised. Pseudonymisation should be applied where possible.

### 4.6 Article 49(1)(f) — Vital interests

Conditions:

- Necessary to protect the vital interests of the data subject or another person.
- The data subject is physically or legally incapable of giving consent.

Examples:

- Medical emergency where data must be sent to a non-EU hospital to save a life.
- Disaster response.

Narrowly construed: when the data subject can consent, this derogation does not apply.

### 4.7 Article 49(1)(g) — Public register

Conditions:

- The data is in a register intended to provide information to the public.
- The register is established by EU or member-state law.
- The transfer satisfies the conditions in the law for consultation.
- Only the relevant data is transferred (no whole-register dumps).

Examples:

- Land registry, commercial register, register of associations, vehicle register, etc.

### 4.8 Residual derogation (Article 49(1) second subparagraph)

Conditions (cumulative):

1. **Not repetitive.**
2. **Limited number** of data subjects.
3. **Compelling legitimate interests** of the controller, **not overridden** by data subject interests/rights/freedoms.
4. The controller has **assessed** all the circumstances surrounding the transfer.
5. The controller has **provided suitable safeguards** based on that assessment.
6. The controller has **informed the supervisory authority** of the transfer.
7. The controller has **informed the data subject** about the transfer and the compelling legitimate interests pursued.

This is the strictest derogation. Use only when no other ground applies and structural Article 46 transfer is genuinely impossible. The EDPB has emphasised that this is **not a workaround** for repetitive transfers.

## 5. Notification obligations

### 5.1 To the data subject

For (a), (b), (c), (e), (g): typically embedded in the privacy notice / consent flow.
For (f): notification post-event where possible.
For (d): per the underlying law / agreement.
For the residual derogation: **explicit** notification of the legitimate interests pursued.

### 5.2 To the supervisory authority

For the residual derogation: notification is **mandatory** before the transfer.

For the others: not required (unless under sectoral rules), but the SA may demand evidence in an audit.

## 6. Documentation per transfer

| Element | Required content |
|---|---|
| Ground | Specific Article 49 sub-paragraph. |
| Necessity assessment | Why no less-intrusive approach. |
| Proportionality assessment | Volume, sensitivity, frequency. |
| Public interest basis (if (d)) | Reference to law. |
| Consent record (if (a)) | Free, informed, explicit, withdrawable; risk briefing acknowledged. |
| Notification to SA (if residual) | Date, content, reference. |
| Notification to data subject | Date, content. |
| Limited safeguards applied | Encryption, minimisation, etc. (even derogations should minimise risk). |
| Approvals | Data owner, DPO, Legal. |
| Review trigger | Each transfer is logged; aggregated review. |

## 7. Common errors

| Error | Why it fails | Correction |
|---|---|---|
| Using 49(1)(a) for ongoing customer transfers | Not occasional; consent rarely qualifies | Use SCC + TIA |
| Treating 49(1)(b) as covering analytics | Not necessary | Use SCC + TIA |
| Generic "consent" in privacy policy as 49(1)(a) | Not explicit | Specific consent flow with risk briefing |
| Residual derogation used for routine flow | Repetitive, not occasional | Use SCC + TIA |
| Failing to notify SA on residual derogation | Mandatory step omitted | Always notify |
| Derogation without documentation | Accountability fail | Document fully |

## 8. Worked examples

### 8.1 Permissible: explicit consent for one-off transfer

Scenario: An EU user requests their account to be migrated to a non-EU sister service that is being launched. The user provides explicit, specific consent after being briefed on the risks.

Article 49(1)(a) applies. Document the consent, the briefing, the right to withdraw, and the one-off nature. If migration becomes a regular path for many users, switch to SCC.

### 8.2 Permissible: contract performance

Scenario: A user purchases a service from an EU controller and asks for delivery to a third-country address. Transmitting the address to the third-country shipper is necessary for the contract.

Article 49(1)(b) applies. Document the contract context.

### 8.3 Permissible: legal claims

Scenario: An employee files a wrongful-termination suit in a US court against the US parent of an EU subsidiary. The EU subsidiary transfers HR records to its US parent's lawyers for defence.

Article 49(1)(e) applies, narrowly. Apply minimisation and pseudonymisation where possible.

### 8.4 Not permissible: routine offshoring

Scenario: An EU controller routinely sends customer support tickets to a third-country call centre.

This is **not** occasional. Use SCC + TIA + supplementary measures, not Article 49.

### 8.5 Not permissible: marketing analytics

Scenario: An EU controller routinely sends user behaviour data to a third-country analytics provider.

Use SCC + TIA. Article 49(1)(b) is not satisfied — analytics is not "necessary for performance of the contract" with the user.

## 9. Public-register derogation in practice

Article 49(1)(g) applies to:

- Commercial registers (Handelsregister, Companies House, etc.).
- Land registers.
- Vehicle registers.
- Register of incumbrances.

Conditions:

- Public access by the register's nature.
- Transfer respects the consultation conditions in the law.
- Only relevant entries.

Bulk dumps for general purposes (data brokering, profiling) are **not** authorised.

## 10. Interaction with Schrems II

Article 49 was not directly addressed by Schrems II, but the EDPB stresses that the spirit of the judgment applies: a derogation cannot be used to bypass the obligation to ensure essentially equivalent protection. Where the destination country's regime would render Article 46 ineffective, a derogation does not "fix" the problem — it merely highlights the need to minimise data and apply technical safeguards.

## 11. Audit checklist

- [ ] Each derogation use is documented.
- [ ] Ground identified and justified.
- [ ] Necessity demonstrated.
- [ ] Specific (not generic) consent where 49(1)(a) used.
- [ ] Risk briefing attached to consent record.
- [ ] Residual derogation: SA notification done.
- [ ] No repetitive use of derogations for the same flow.
- [ ] DPO sign-off.
- [ ] Annual review by DPO.

---

## Türkçe

# Madde 49 İstisnaları

## 1. Statü

Madde 49 istisnaları V. Bölümdeki **son çare**dir. Yalnızca şu durumlarda uygulanırlar:

- Madde 45 yeterlilik kararı yok; ve
- Madde 46 uygun korumaları yok (veya yerine getirilemez).

EDPB Rehberleri 2/2018 bu hiyerarşiyi onaylar. İstisnalar **dar yorumlanmalı** ve rutin olarak veya SCC / BCR'lerden kaçınmak için bir arka kapı olarak kullanılmamalıdır.

## 2. Dayanaklar

Madde 49(1) dayanakları listeler:

| Dayanak | Açıklama |
|---|---|
| (a) | İlgili kişi, yeterlilik kararı ve uygun korumaların yokluğu nedeniyle bu tür transferlerin olası risklerinden bilgilendirildikten sonra önerilen transfere **açık olarak rıza vermiştir**. |
| (b) | Transfer, ilgili kişi ile kontrolör arasında **bir sözleşmenin ifası** veya ilgili kişinin talebi üzerine alınan ön-sözleşmesel önlemlerin uygulanması için gereklidir. |
| (c) | Transfer, kontrolör ile başka bir gerçek veya tüzel kişi arasında **ilgili kişinin yararına akdedilen bir sözleşmenin** akdi veya ifası için gereklidir. |
| (d) | Transfer, **önemli kamu yararı sebepleri** için gereklidir. |
| (e) | Transfer, **hukuki taleplerin kurulması, kullanılması veya savunulması** için gereklidir. |
| (f) | Transfer, ilgili kişinin fiziksel veya yasal olarak rıza veremediği durumlarda ilgili kişinin veya diğer kişilerin **hayati menfaatlerini korumak** için gereklidir. |
| (g) | Transfer, Birlik veya Üye Devlet hukukuna göre kamuya bilgi sağlamayı amaçlayan ve danışılmaya açık bir **sicilden** yapılır. |

Madde 49(1) ikinci paragrafı bir artık istisna ekler: yukarıdakilerden hiçbiri uygulanmadığında, transfer tekrarlanan değilse, sadece sınırlı sayıda ilgili kişiyi ilgilendiriyorsa, ilgili kişinin menfaatleri tarafından geçersiz kılınmayan kontrolörün zorunlu meşru menfaatleri için gerekli ise ve **denetim makamına ve ilgili kişiye bildirim ile** gerçekleşebilir.

## 3. Ortak gereksinimler

Tüm istisnalar özelliklerini paylaşır:

### 3.1 Gereklilik

Transfer amaç için **kesinlikle gerekli** olmalıdır. Uygun ≠ gerekli. İhracatçı, daha az müdahaleci hiçbir aracın aynı amacı sağlamadığını gösterebilmelidir.

### 3.2 Belirli durum / ara sıra ve tekrarlanmayan

Resital 111, istisnaların **ara sıra** transferlere uygulandığını onaylar. Tekrarlanan, düzenli, yapısal transferler bunun yerine Madde 45 veya 46'ya dayanmalıdır. EDPB Rehberleri 2/2018 vurgular:

- "Ara sıra" → düzenli değil, önceden belirlenmemiş, rutin sürecin parçası değil.
- "Tekrarlanmayan" → desende tahmin edilemez.

Müşteri verilerini sistematik olarak ABD alt-işleyenine transfer eden bir işleyen Madde 49'a dayanamaz.

### 3.3 Belgeleme

İstisnalar istisnai olsa bile, kontrolör belgelemelidir:

- Dayanılan belirli dayanak.
- Gereklilik değerlendirmesi.
- Orantılılık değerlendirmesi.
- İlgili kişiye verilen bilgi (geçerli olduğunda).
- Risk bilgilendirmesi (özellikle rıza temelli istisnalar için).
- DPO görüşü.

## 4. İstisna istisna

### 4.1 Madde 49(1)(a) — Açık rıza

Koşullar:

- **Açık**: ilgili kişi, belirli bir üçüncü ülkeye / uluslararası kuruluşa / belirli işleyene transfere açık olarak net, belirli olumlu eylem vermiş olmalıdır.
- **Bilgilendirilmiş**: ilgili kişiye şunlar söylenmelidir:
  - Alıcı(lar)ın kimliği.
  - İlgili ülkeler.
  - Transferin amacı.
  - Yeterlilik ve korumaların yokluğundan kaynaklanan **belirli riskler** (örn. hükümet erişimi, eşdeğer başvuru yok).
- **Özgürce verilmiş**: güç dengesizlikleri önemlidir (çalışanlar, kamu otoritesi).
- **Geri çekilebilir**: zarar olmaksızın herhangi bir zamanda.

Tuzaklar:

- "AB dışı ülkelere transferler" için genel gizlilik politikası rızası 49(1)(a) altında **açık** rıza değildir — çok belirsizdir.
- Daha geniş rıza ile paketleme "belirli" testini karşılamaz.
- Önceden işaretlenmiş kutular geçersizdir.
- Çalışanlar güç dengesizliği nedeniyle nadiren geçerli rıza verir (49(1)(b) veya başka bir mekanizma kullanın).

### 4.2 Madde 49(1)(b) — İlgili kişiyle sözleşmenin ifası

Koşullar:

- Sözleşme ilgili kişi ile kontrolör arasındadır.
- Transfer sözleşmeyi veya **ilgili kişinin talebi üzerine** ön-sözleşmesel adımları yerine getirmek için **gereklidir**.

Tuzaklar:

- "Gerekli" sıkı yorumlanır. Kontrolör için sadece kolaylık nitelik kazanmaz.
- İleri / yardımcı transferler (örn. pazarlama analiz işleyenine) genellikle gerekliliği karşılayamaz.
- Resital 111 ara sıra doğayı onaylar.

Örnek: AB sitesinden ürün satın alan bir kullanıcı üçüncü bir ülkeye teslim ister. Adresi AB dışı nakliyeciye göndermek gereklidir.

### 4.3 Madde 49(1)(c) — İlgili kişinin yararına sözleşme

Koşullar:

- Kontrolör ve üçüncü taraf arasında ilgili kişinin yararına akdedilen bir sözleşme.
- Transfer sözleşmenin akdi veya ifası için gereklidir.

Örnek: Bir AB seyahat acentesi, bir müşteri adına üçüncü bir ülkede otel rezervasyonu yapar; müşterinin kimliğini ve ödeme bilgilerini otele iletmek menfaatleri için gereklidir.

### 4.4 Madde 49(1)(d) — Önemli kamu yararı sebepleri

Koşullar:

- Kamu yararı AB veya üye devlet hukukunda tanınmalıdır (Resital 112).
- Menfaat **önemlidir** — sıradan kamu politikası düşüncelerinin ötesinde.

Örnekler:

- Otoriteler arasında vergi işbirliği anlaşmaları.
- Gümrük işbirliği.
- Veri koruma otoriteleri arasında uluslararası transferler.
- Sınır ötesi dolandırıcılık veya organize suçla mücadelede işbirliği (yeterlilik çerçevesine tabi).

Resital, bu istisnanın özel sektör kontrolörlerinin genel kamu yararı taleplerine uygulanmadığını netleştirir; kamu yararı AB / üye devlet hukukunda olmalıdır.

### 4.5 Madde 49(1)(e) — Hukuki talepler

Koşullar:

- Hukuki taleplerin kurulması, kullanılması veya savunulması için gereklidir.
- Kamu otoriteleri (mahkeme, düzenleyici, tahkim tribünali) önündeki süreçleri içerir.
- Eylem öncesi soruşturmaları içerir.

Örnek: Bir ilgili kişi üçüncü ülke mahkemesinde dava edilir; AB tarafı kontrolör savunma için gerekli belgeleri transfer eder.

Çatışma bölgesi: Yabancı davada ABD e-discovery. EDPB Rehberleri 2/2018 dayanmayı sınırlar: veri gerekli, orantılı ve minimize edilmiş olmalıdır. Mümkün olduğunda takma adlandırma uygulanmalıdır.

### 4.6 Madde 49(1)(f) — Hayati menfaatler

Koşullar:

- İlgili kişinin veya başka bir kişinin hayati menfaatlerini korumak için gereklidir.
- İlgili kişi rıza vermek için fiziksel veya yasal olarak yetersizdir.

Örnekler:

- Bir hayatı kurtarmak için verinin AB dışı hastaneye gönderilmesi gereken tıbbi acil durum.
- Felaket yanıtı.

Dar yorumlanır: ilgili kişi rıza verebildiğinde, bu istisna uygulanmaz.

### 4.7 Madde 49(1)(g) — Kamu sicili

Koşullar:

- Veri kamuya bilgi sağlamayı amaçlayan bir sicildedir.
- Sicil AB veya üye devlet hukuku tarafından kurulmuştur.
- Transfer hukukta danışma için koşulları karşılar.
- Yalnızca ilgili veri transfer edilir (tüm sicil dökümleri yok).

Örnekler:

- Tapu sicili, ticaret sicili, dernek sicili, araç sicili vb.

### 4.8 Artık istisna (Madde 49(1) ikinci paragraf)

Koşullar (birikimli):

1. **Tekrarlanmaz.**
2. **Sınırlı sayıda** ilgili kişi.
3. İlgili kişinin menfaatleri/hakları/özgürlükleri tarafından **geçersiz kılınmayan** kontrolörün **zorunlu meşru menfaatleri**.
4. Kontrolör transferi çevreleyen tüm koşulları **değerlendirmiştir**.
5. Kontrolör bu değerlendirmeye dayanarak **uygun korumalar sağlamıştır**.
6. Kontrolör transferi **denetim makamına bildirmiştir**.
7. Kontrolör ilgili kişiyi transfer ve takip edilen zorunlu meşru menfaatler hakkında **bilgilendirmiştir**.

Bu en katı istisnadır. Yalnızca başka bir dayanak uygulanmadığında ve yapısal Madde 46 transferi gerçekten imkânsız olduğunda kullanın. EDPB bunun tekrarlanan transferler için **bir geçici çözüm olmadığını** vurgulamıştır.

## 5. Bildirim yükümlülükleri

### 5.1 İlgili kişiye

(a), (b), (c), (e), (g) için: tipik olarak gizlilik bildirimi / rıza akışına gömülmüştür.
(f) için: mümkün olduğunda olay sonrası bildirim.
(d) için: temel hukuk / anlaşma başına.
Artık istisna için: takip edilen meşru menfaatlerin **açık** bildirimi.

### 5.2 Denetim makamına

Artık istisna için: bildirim transferden önce **zorunludur**.

Diğerleri için: gerekli değil (sektörel kurallar altında olmadıkça), ancak SA bir denetimde kanıt talep edebilir.

## 6. Transfer başına belgeleme

| Unsur | Gerekli içerik |
|---|---|
| Dayanak | Belirli Madde 49 alt paragrafı. |
| Gereklilik değerlendirmesi | Neden daha az müdahaleci yaklaşım yok. |
| Orantılılık değerlendirmesi | Hacim, hassasiyet, sıklık. |
| Kamu yararı dayanağı (if (d)) | Hukuka atıf. |
| Rıza kaydı (if (a)) | Özgür, bilgilendirilmiş, açık, geri çekilebilir; risk bilgilendirmesi onaylandı. |
| SA'ya bildirim (artık ise) | Tarih, içerik, referans. |
| İlgili kişiye bildirim | Tarih, içerik. |
| Uygulanan sınırlı korumalar | Şifreleme, minimizasyon vb. (istisnalar bile riski minimize etmelidir). |
| Onaylar | Veri sahibi, DPO, Hukuk. |
| İnceleme tetikleyici | Her transfer kaydedilir; toplu inceleme. |

## 7. Yaygın hatalar

| Hata | Neden başarısız | Düzeltme |
|---|---|---|
| Devam eden müşteri transferleri için 49(1)(a) kullanma | Ara sıra değil; rıza nadiren nitelik kazanır | SCC + TIA kullan |
| 49(1)(b)'yi analitiği kapsayacak şekilde ele alma | Gerekli değil | SCC + TIA kullan |
| 49(1)(a) olarak gizlilik politikasında genel "rıza" | Açık değil | Risk bilgilendirmesiyle özel rıza akışı |
| Rutin akış için kullanılan artık istisna | Tekrarlanan, ara sıra değil | SCC + TIA kullan |
| Artık istisnada SA'ya bildirim yapılmaması | Zorunlu adım atlandı | Her zaman bildir |
| Belgeleme olmadan istisna | Hesap verebilirlik başarısızlığı | Tam belgele |

## 8. İşlenmiş örnekler

### 8.1 İzin verilebilir: tek seferlik transfer için açık rıza

Senaryo: Bir AB kullanıcısı, başlatılan AB dışı kardeş hizmete hesabının taşınmasını ister. Kullanıcı riskler hakkında bilgilendirildikten sonra açık, belirli rıza verir.

Madde 49(1)(a) uygulanır. Rızayı, bilgilendirmeyi, geri çekme hakkını ve tek seferlik doğayı belgele. Taşıma birçok kullanıcı için düzenli bir yol haline gelirse, SCC'ye geçin.

### 8.2 İzin verilebilir: sözleşme ifası

Senaryo: Bir kullanıcı bir AB kontrolöründen hizmet satın alır ve üçüncü ülke adresine teslimat ister. Adresi üçüncü ülke nakliyecisine iletmek sözleşme için gereklidir.

Madde 49(1)(b) uygulanır. Sözleşme bağlamını belgele.

### 8.3 İzin verilebilir: hukuki talepler

Senaryo: Bir çalışan, AB iştirakinin ABD ana şirketine karşı ABD mahkemesinde haksız fesih davası açar. AB iştiraki savunma için ABD ana şirketinin avukatlarına İK kayıtlarını transfer eder.

Madde 49(1)(e) dar uygulanır. Mümkün olduğunda minimizasyon ve takma adlandırma uygula.

### 8.4 İzin verilemez: rutin offshoring

Senaryo: Bir AB kontrolörü müşteri destek taleplerini rutin olarak üçüncü ülke çağrı merkezine gönderir.

Bu **ara sıra değildir**. Madde 49 yerine SCC + TIA + tamamlayıcı önlemler kullan.

### 8.5 İzin verilemez: pazarlama analitiği

Senaryo: Bir AB kontrolörü kullanıcı davranış verilerini rutin olarak üçüncü ülke analitik sağlayıcısına gönderir.

SCC + TIA kullan. Madde 49(1)(b) karşılanmaz — analitik kullanıcıyla "sözleşmenin ifası için gerekli" değildir.

## 9. Pratik kamu sicili istisnası

Madde 49(1)(g) şunlara uygulanır:

- Ticaret sicilleri (Handelsregister, Companies House vb.).
- Tapu sicilleri.
- Araç sicilleri.
- Tasarruf hakkı sicili.

Koşullar:

- Sicilin doğası gereği kamu erişimi.
- Transfer hukukta danışma koşullarına saygı gösterir.
- Yalnızca ilgili girişler.

Genel amaçlar için (veri komisyonculuğu, profil oluşturma) toplu dökümler **yetkilendirilmemiştir**.

## 10. Schrems II ile etkileşim

Madde 49 Schrems II tarafından doğrudan ele alınmadı, ancak EDPB kararın ruhunun uygulandığını vurgular: bir istisna esasen eşdeğer korumayı sağlama yükümlülüğünü atlatmak için kullanılamaz. Hedef ülkenin rejiminin Madde 46'yı etkisiz kılacağı durumlarda, bir istisna sorunu "düzeltmez" — yalnızca veriyi minimize etme ve teknik korumalar uygulama gereksinimini vurgular.

## 11. Denetim kontrol listesi

- [ ] Her istisna kullanımı belgelendi.
- [ ] Dayanak tanımlandı ve gerekçelendirildi.
- [ ] Gereklilik gösterildi.
- [ ] 49(1)(a) kullanıldığında belirli (genel değil) rıza.
- [ ] Risk bilgilendirmesi rıza kaydına eklendi.
- [ ] Artık istisna: SA bildirimi yapıldı.
- [ ] Aynı akış için istisnaların tekrarlanan kullanımı yok.
- [ ] DPO onayı.
- [ ] DPO tarafından yıllık inceleme.
