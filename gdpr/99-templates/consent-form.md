---
title:
  en: "Consent Form Templates"
  tr: "Acik Riza Form Sablonlari"
section: "99-templates"
owner: "DPO / Legal"
version: "1.0"
last_review: "2026-05-08"
next_review: "2026-11-08"
classification: "Internal"
languages: ["en", "tr"]
keywords:
  en: ["consent", "Article 4(11)", "Article 7", "withdrawal"]
  tr: ["acik riza", "Madde 4(11)", "Madde 7", "geri cekme"]
---

## English

# Consent Form Templates

Three templates for distinct purposes: (A) marketing consent, (B) third-country transfer consent under Article 49(1)(a), (C) consent for profiling/automated decision-making under Article 22(2)(c) or special category consent under Article 9(2)(a).

All comply with Article 4(11) (freely given, specific, informed, unambiguous, by clear affirmative act) and Article 7 (demonstrable, separable, withdrawable, granular). EDPB Guidelines 05/2020 followed; Planet49 (C-673/17) reflected.

### Common requirements (apply to all consent forms)

- No pre-ticked checkboxes.
- Granular per purpose; no bundling.
- Plain language; reading age 12-14 typical.
- Identity of controller and any joint controllers stated.
- Specific purposes listed.
- Right to withdraw stated, with mechanism described, and equally easy as giving.
- Consequences of withdrawal explained.
- Duration of consent stated, with refresh approach.
- Where children's consent under Article 8: parental consent verification required if under age of consent.
- Consent receipt logged: timestamp, identifier, purposes, scope, version of notice referenced.

---

## Template A — Marketing Consent

**Form version:** [version]
**Date:** [YYYY-MM-DD]
**Controller:** [name]
**Contact:** [privacy@example.com]
**Purpose:** Direct marketing communications by [channels].

### Consent statement

I would like to receive marketing communications from [Controller] through the following channel(s):

- [ ] Email
- [ ] SMS
- [ ] Telephone
- [ ] Postal mail
- [ ] In-app notifications

I can change my preferences or withdraw at any time by:

- Clicking the unsubscribe link in any email.
- Replying STOP to any SMS.
- Contacting [privacy@example.com].
- Updating settings in my account.

Withdrawing does not affect lawful processing carried out before withdrawal.

I have read the [Privacy Notice version X dated YYYY-MM-DD].

Signature / electronic confirmation: ___________________________
Name: __________________________________________________________
Date: __________________________________________________________

### Internal logging fields

| Field | Value |
|-------|-------|
| Consent ID | [UUID] |
| Data subject identifier | [hashed identifier] |
| Channels selected | [list] |
| Notice version referenced | [version] |
| Source UI | [URL or screen] |
| Timestamp | [ISO-8601] |
| IP and device (where appropriate) | [data] |
| Withdrawal timestamp (if any) | [ISO-8601] |
| Withdrawal channel | [channel] |

---

## Template B — Third-Country Transfer Consent (Article 49(1)(a))

**Form version:** [version]
**Date:** [YYYY-MM-DD]
**Controller:** [name]
**Contact:** [privacy@example.com]
**Recipient country:** [country]
**Recipient organization:** [name]
**Purpose of transfer:** [purpose]

### Notice before consent

The European Commission has [or has not] adopted an adequacy decision for [country]. [State country status: adequate / not adequate.] Where there is no adequacy decision, the level of data protection in [country] may be lower than in the EU. Specific risks include:

- Government access to data under [law name and brief description].
- Limited individual remedies in [country].
- Possible onward transfers to third parties.

### Consent statement

I have read the above information about the transfer to [country]. I explicitly consent to the transfer of my personal data described below to [recipient name] in [country] for the purpose of [purpose].

Categories of data transferred:

- [list specific categories]

Duration of transfer: [duration]

I understand that I can withdraw this consent at any time by [mechanism]. Withdrawal will not affect lawful processing already carried out. I understand that withdrawal may mean we cannot continue providing [the service / a part of the service].

Signature: _______________________________________________________
Name: ___________________________________________________________
Date: ___________________________________________________________

### Notes

- Article 49 derogations are narrow. Use only when no transfer instrument under Article 46 is feasible and the transfer is occasional. EDPB Guidelines 04/2018 emphasize strict interpretation.
- For systematic transfers, use SCCs (Decision 2021/914) or other Article 46 safeguards instead, supported by a TIA (Schrems II).
- For employment relationships, consent is rarely freely given; prefer Article 49(1)(b) (contract necessity) only in narrow cases or transfer instruments.

---

## Template C — Consent for Profiling / Automated Decision-Making

**Form version:** [version]
**Date:** [YYYY-MM-DD]
**Controller:** [name]
**Contact:** [privacy@example.com]
**Type of processing:** [profiling / automated decision-making with legal or similarly significant effect]

### Notice before consent

We use automated processing as described below.

- **Logic involved:** [plain-language explanation of the algorithm or scoring approach]
- **Significance and consequences:** [e.g. determines pricing, eligibility for credit]
- **Categories of data used:** [list]
- **Sources of data:** [list]
- **Safeguards:** human review available on request; right to express your point of view; right to contest the decision (Article 22(3)).

### Consent statement

I consent to [Controller] applying the automated processing described above to my data for [purpose].

I understand that I can:

- Withdraw consent at any time by contacting [privacy@example.com] or via my account settings.
- Request human review at [contact].
- Express my point of view and contest the decision.
- Without affecting lawful processing carried out before withdrawal.

If processing involves special category data (Article 9):

- [ ] I explicitly consent under Article 9(2)(a) to the processing of [specify special category data] for [purpose].

Signature: _______________________________________________________
Name: ___________________________________________________________
Date: ___________________________________________________________

### Notes

- Article 22(2)(c) requires explicit consent for solely automated decision-making with legal or similarly significant effects unless 22(2)(a) (necessary for contract) or 22(2)(b) (authorised by Union or MS law) apply.
- Article 9(2)(a) requires explicit consent for special category data processing.
- SCHUFA (C-634/21) confirmed scoring upstream of human decision can itself be Article 22(1) processing.
- Maintain robust safeguards under Article 22(3): right to obtain human intervention, express point of view, contest decision.

### Implementation guidance for all forms

1. **UI design:**
   - Clear visual hierarchy.
   - No dark patterns.
   - Equal prominence between accept and reject paths.
   - No "agree to all" without granular alternative.

2. **Recording:**
   - Immutable consent log.
   - Reference to specific notice version.
   - Identifier of data subject.

3. **Withdrawal:**
   - Equally easy: same number of clicks; no friction; no deceptive language.
   - Confirmation of withdrawal.
   - Update suppression lists where relevant.

4. **Refresh:**
   - Define cadence (e.g. every 12-24 months for marketing).
   - Re-consent triggered by material change to purposes or recipients.

5. **Children:**
   - Article 8 — verify parental consent for children under the applicable age (13-16 by member state).
   - Use age-gating and parental verification per industry standards.

6. **Audit:**
   - Sample consent records quarterly.
   - Verify alignment with notice version and processing activity.

---

## Türkçe

# Açık Rıza Form Şablonları

Farklı amaçlar için üç şablon: (A) pazarlama açık rızası, (B) Madde 49(1)(a) altında üçüncü ülke aktarımı açık rızası, (C) Madde 22(2)(c) altında profil oluşturma/otomatik karar verme veya Madde 9(2)(a) altında özel kategori açık rızası.

Tümü Madde 4(11) (özgürce verilmiş, belirli, bilgilendirilmiş, açık, açık olumlu eylemle) ve Madde 7 (kanıtlanabilir, ayrılabilir, geri çekilebilir, ayrıntılı) ile uyumludur. EDPB Kılavuzu 05/2020 izlenmiştir; Planet49 (C-673/17) yansıtılmıştır.

### Ortak gereksinimler (tüm rıza formlarına uygulanır)

- Önceden işaretli kutu yok.
- Amaç başına ayrıntılı; paketleme yok.
- Sade dil; tipik 12-14 okuma yaşı.
- Veri sorumlusunun ve müşterek veri sorumlularının kimliği belirtilmiş.
- Belirli amaçlar listelenmiş.
- Geri çekme hakkı belirtilmiş, mekanizma açıklanmış ve vermek kadar kolay.
- Geri çekmenin sonuçları açıklanmış.
- Rıza süresi belirtilmiş, yenileme yaklaşımı.
- Madde 8 altında çocuk rızası: rıza yaşının altındaysa ebeveyn rıza doğrulama gereklidir.
- Rıza makbuzu kayıtlı: zaman damgası, tanımlayıcı, amaçlar, kapsam, atıfta bulunulan metin sürümü.

---

## Şablon A — Pazarlama Açık Rızası

**Form sürümü:** [sürüm]
**Tarih:** [YYYY-AA-GG]
**Veri sorumlusu:** [ad]
**İletişim:** [privacy@example.com]
**Amaç:** [Veri sorumlusu] tarafından [kanallar] aracılığıyla doğrudan pazarlama iletişimi.

### Rıza beyanı

[Veri sorumlusu]'ndan aşağıdaki kanal(lar) üzerinden pazarlama iletişimleri almak istiyorum:

- [ ] E-posta
- [ ] SMS
- [ ] Telefon
- [ ] Posta
- [ ] Uygulama içi bildirimler

Tercihlerimi her zaman değiştirebilir veya geri çekebilirim:

- Herhangi bir e-postadaki abonelikten çık bağlantısını tıklayarak.
- Herhangi bir SMS'e DURDUR yanıt vererek.
- [privacy@example.com] ile iletişime geçerek.
- Hesabımdaki ayarları güncelleyerek.

Geri çekme, geri çekmeden önce gerçekleştirilen hukuka uygun işlemeyi etkilemez.

[YYYY-AA-GG tarihli sürüm X Aydınlatma Metnini] okudum.

İmza / elektronik onay: ___________________________
Ad: ____________________________________________
Tarih: __________________________________________

### İç günlük alanları

| Alan | Değer |
|------|-------|
| Rıza ID | [UUID] |
| İlgili kişi tanımlayıcısı | [hash'lenmiş tanımlayıcı] |
| Seçilen kanallar | [liste] |
| Atıfta bulunulan metin sürümü | [sürüm] |
| Kaynak UI | [URL veya ekran] |
| Zaman damgası | [ISO-8601] |
| IP ve cihaz (uygun olduğunda) | [veri] |
| Geri çekme zaman damgası (varsa) | [ISO-8601] |
| Geri çekme kanalı | [kanal] |

---

## Şablon B — Üçüncü Ülke Aktarım Açık Rızası (Madde 49(1)(a))

**Form sürümü:** [sürüm]
**Tarih:** [YYYY-AA-GG]
**Veri sorumlusu:** [ad]
**İletişim:** [privacy@example.com]
**Alıcı ülke:** [ülke]
**Alıcı organizasyon:** [ad]
**Aktarım amacı:** [amaç]

### Rıza öncesi bilgilendirme

Avrupa Komisyonu [ülke] için bir yeterlilik kararı [almıştır / almamıştır]. [Ülke durumunu belirtin: yeterli / yeterli değil.] Yeterlilik kararı yoksa [ülke]'deki veri koruma seviyesi AB'dekinden daha düşük olabilir. Belirli riskler şunlardır:

- [Yasa adı ve kısa açıklama] altında hükümet veri erişimi.
- [Ülke]'de sınırlı bireysel çareler.
- Üçüncü taraflara olası sonraki aktarımlar.

### Rıza beyanı

[Ülke]'ye aktarım hakkındaki yukarıdaki bilgileri okudum. Aşağıda tanımlanan kişisel verilerimin [amaç] için [ülke]'deki [alıcı adı]'na aktarılmasına açıkça rıza gösteriyorum.

Aktarılan veri kategorileri:

- [belirli kategorileri listele]

Aktarım süresi: [süre]

Bu rızayı [mekanizma] yoluyla istediğim zaman geri çekebileceğimi anlıyorum. Geri çekme zaten gerçekleştirilen hukuka uygun işlemeyi etkilemez. Geri çekmenin [hizmeti / hizmetin bir parçasını] sağlamaya devam edemeyeceğimiz anlamına gelebileceğini anlıyorum.

İmza: ____________________________________________
Ad: ____________________________________________
Tarih: __________________________________________

### Notlar

- Madde 49 istisnaları dardır. Yalnızca Madde 46 altında bir aktarım aracı uygulanabilir olmadığında ve aktarım ara sıra olduğunda kullanın. EDPB Kılavuzu 04/2018 katı yorumu vurgular.
- Sistematik aktarımlar için SCC'ler (Karar 2021/914) veya diğer Madde 46 güvenceleri kullanın, TIA ile desteklenir (Schrems II).
- İstihdam ilişkileri için rıza nadiren özgürce verilir; dar vakalarda Madde 49(1)(b) (sözleşme zorunluluğu) tercih edin veya aktarım araçları.

---

## Şablon C — Profil Oluşturma / Otomatik Karar Verme Açık Rızası

**Form sürümü:** [sürüm]
**Tarih:** [YYYY-AA-GG]
**Veri sorumlusu:** [ad]
**İletişim:** [privacy@example.com]
**İşleme türü:** [profil oluşturma / hukuki veya benzer önemli etkili otomatik karar verme]

### Rıza öncesi bilgilendirme

Aşağıda tanımlandığı şekilde otomatik işleme kullanıyoruz.

- **Dahil olan mantık:** [algoritmanın veya puanlama yaklaşımının sade dil açıklaması]
- **Önemi ve sonuçları:** [örn. fiyatlandırmayı, kredi uygunluğunu belirler]
- **Kullanılan veri kategorileri:** [liste]
- **Veri kaynakları:** [liste]
- **Güvenceler:** talep üzerine insan incelemesi mevcut; bakış açınızı ifade etme hakkı; karara itiraz hakkı (Madde 22(3)).

### Rıza beyanı

[Veri sorumlusu]'nun [amaç] için verilerimde yukarıda tanımlanan otomatik işlemeyi uygulamasına rıza gösteriyorum.

Şunları yapabileceğimi anlıyorum:

- [privacy@example.com] ile iletişime geçerek veya hesap ayarlarım üzerinden istediğim zaman rızamı geri çekme.
- [iletişim] adresinden insan incelemesi talep etme.
- Bakış açımı ifade etme ve karara itiraz etme.
- Geri çekmeden önce gerçekleştirilen hukuka uygun işlemeyi etkilemeden.

İşleme özel kategori veri (Madde 9) içeriyorsa:

- [ ] [Belirli özel kategori veri] üzerinde [amaç] için Madde 9(2)(a) altında açıkça rıza gösteriyorum.

İmza: ____________________________________________
Ad: ____________________________________________
Tarih: __________________________________________

### Notlar

- 22(2)(a) (sözleşme için gerekli) veya 22(2)(b) (Birlik veya ÜD hukukunca yetkilendirilmiş) uygulanmadıkça hukuki veya benzer önemli etkili tamamen otomatik karar verme için Madde 22(2)(c) açık rıza gerektirir.
- Madde 9(2)(a) özel kategori veri işleme için açık rıza gerektirir.
- SCHUFA (C-634/21), insan kararının öncesindeki puanlamanın başlı başına Madde 22(1) işleme olabileceğini teyit etti.
- Madde 22(3) altında sağlam güvenceler sürdürün: insan müdahalesi alma, bakış açısı ifade etme, karara itiraz etme hakkı.

### Tüm formlar için uygulama rehberliği

1. **UI tasarımı:**
   - Net görsel hiyerarşi.
   - Karanlık desen yok.
   - Kabul ve reddet yolları arasında eşit belirginlik.
   - Ayrıntılı alternatif olmadan "tümünü kabul et" yok.

2. **Kayıt:**
   - Değiştirilemez rıza günlüğü.
   - Belirli metin sürümüne atıf.
   - İlgili kişi tanımlayıcısı.

3. **Geri çekme:**
   - Eşit derecede kolay: aynı tıklama sayısı; sürtüşme yok; aldatıcı dil yok.
   - Geri çekme onayı.
   - İlgili olduğunda bastırma listelerini güncelleyin.

4. **Yenileme:**
   - Sıklığı tanımlayın (örn. pazarlama için her 12-24 ay).
   - Amaçların veya alıcıların maddi değişikliği nedeniyle yeniden rıza tetiklenir.

5. **Çocuklar:**
   - Madde 8 — uygulanabilir yaşın altındaki çocuklar için (üye devlete göre 13-16) ebeveyn rızasını doğrulayın.
   - Sektör standartlarına göre yaş kapısı ve ebeveyn doğrulama kullanın.

6. **Denetim:**
   - Çeyreklik rıza kayıtlarını örnekleyin.
   - Metin sürümü ve işleme faaliyeti ile uyumu doğrulayın.
