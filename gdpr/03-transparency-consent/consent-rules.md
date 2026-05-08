---
title: "Consent Rules — Article 7, EDPB Guidelines 5/2020, and Operational Application"
title_tr: "Onay Kuralları — Madde 7, EDPB Kılavuz 5/2020 ve Operasyonel Uygulama"
section: "03-transparency-consent"
language: ["en", "tr"]
status: "approved"
version: "2.4.0"
last_review: "2026-04-15"
next_review: "2026-10-15"
owner: "Data Protection Officer"
classification: "Internal"
related_articles: ["GDPR Art. 4(11)", "GDPR Art. 6(1)(a)", "GDPR Art. 7", "GDPR Art. 8", "GDPR Art. 9(2)(a)", "GDPR Recitals 32, 42, 43"]
related_guidelines: ["EDPB Guidelines 5/2020 on consent", "EDPB Guidelines 03/2022 on dark patterns"]
tags: ["consent", "article-7", "edpb-5-2020", "withdrawal", "children", "article-8"]
---

## English

### 1. The Statutory Definition

Consent of the data subject (Article 4(11)) means *any freely given, specific, informed and unambiguous indication of the data subject's wishes by which he or she, by a statement or by a clear affirmative action, signifies agreement to the processing of personal data relating to him or her*.

The four prongs (freely given, specific, informed, unambiguous) plus the demonstration requirement (Art. 7(1)) and the withdrawal right (Art. 7(3)) form the core test for valid consent.

### 2. Prong One — Freely Given

**Test**: Does the data subject have a genuine choice, without detriment for refusal?

EDPB Guidelines 5/2020 identify four sub-tests:

#### 2.1 No Imbalance of Power

Consent is presumed not freely given where there is a clear imbalance between the data subject and the controller. The most cited example is the employer–employee relationship: an employer cannot rely on consent for processing employees' data, except in a narrow set of cases where genuine choice exists (e.g., taking a photograph for an internal newsletter that does not affect employment).

Public authorities processing the data of citizens face a similar presumption.

#### 2.2 No Conditionality

Article 7(4): When assessing whether consent is freely given, account must be taken of whether performance of a contract is conditional on consent that is not necessary for that performance. Consent for marketing cannot be a condition of a service unless the marketing is genuinely the service.

The "service-for-data" model (cookie walls that demand cookie consent for site access) was rejected by the EDPB and most national authorities. A user must have a real alternative — typically, a non-tracking version of the service, possibly behind a paywall.

#### 2.3 Granularity

If the controller seeks consent for several purposes (e.g., newsletter + product analytics + advertising), each purpose must be presented separately so the data subject can consent to one and refuse the others. Bundled consent ("I agree to be contacted for marketing, analytics, and partner offers") is invalid.

#### 2.4 No Detriment

Refusing consent must not lead to disadvantage. Withholding non-essential consents must not block access to a service or feature whose delivery does not require those consents.

### 3. Prong Two — Specific

Consent must be **purpose-specific**. The controller must:

- Specify each processing purpose.
- Seek separate consent for each.
- Reaffirm consent if the controller wants to use the data for a new, incompatible purpose.

### 4. Prong Three — Informed

The data subject must know, at minimum:

1. The identity of the controller.
2. The specific purpose for which consent is sought.
3. What types of data will be collected.
4. The right to withdraw consent.
5. Information on the use of automated decision-making (where applicable).
6. The risks of transfers to third countries without an adequacy decision (where applicable).

This information must be presented at the moment of consent, not buried in a separate policy. A link to the privacy notice supplements but does not replace it.

### 5. Prong Four — Unambiguous Indication by Clear Affirmative Action

Consent requires a positive act. EDPB and the CJEU (Planet49 judgment) make clear that:

- Pre-ticked boxes are not valid consent.
- Inactivity is not consent.
- Continuing to use a website is not consent.
- Closing a banner is not consent.
- Scrolling is not consent (per Planet49 reasoning extended in EDPB 03/2022).

Valid affirmative actions include:

- Ticking an unticked checkbox.
- Clicking a clearly labelled "I agree" button.
- Selecting "yes" in a binary choice where "no" is equally prominent.
- Verbally saying "yes" with recorded confirmation.

### 6. Article 7(1) — Demonstrability

The controller must be able to demonstrate that consent was given. For each consent decision:

- Who consented (data subject identifier).
- When (timestamp, time zone).
- What was the consent text shown (linked to a versioned policy).
- The mechanism (e.g., checkbox, button click).
- The IP address and user agent (for online consent), where useful.
- Whether and when consent was withdrawn.

These records must be retrievable years later when challenged.

### 7. Article 7(3) — Withdrawal as Easy as Giving

The data subject must be able to withdraw consent **as easily as it was given**. Practically:

- If consent was obtained by a single click in an app, withdrawal must be a single click in the app — not a postal letter.
- If consent was given via a web form, withdrawal must be reachable in similar steps via the web.
- If consent was given through a CMP cookie banner, withdrawal must be reachable from a persistent privacy preferences link.

The withdrawal right must be told to the data subject **before** consent is given (Art. 7(3) second sentence).

### 8. Special Categories (Article 9)

For special category data, Article 9(2)(a) requires **explicit consent**. EDPB interprets "explicit" to mean an additional layer above ordinary consent — typically, a written statement signed by the data subject (electronic signature acceptable), or an explicit two-step opt-in. A pre-checked box is doubly invalid for special-category processing.

### 9. Article 8 — Children's Consent

Where information society services are offered directly to a child, the child's consent is lawful only if the child is at least 16 years old. Member State law may provide a lower age, but not below 13.

| Member State | Age | Source |
|--------------|-----|--------|
| Default GDPR | 16 | Art. 8(1) |
| France | 15 | Loi Informatique et Libertés |
| Germany | 16 | BDSG |
| Ireland | 16 | Data Protection Act 2018 |
| Italy | 14 | Italian DPA Code |
| Netherlands | 16 | UAVG |
| Spain | 14 | LOPDGDD |
| United Kingdom | 13 | DPA 2018 (post-Brexit) |

Where the child is below the age threshold, parental consent is required. The controller must make reasonable efforts to verify parental consent, taking available technology into account (Art. 8(2)).

Reasonable efforts may include:

- Email confirmation to a parental email address.
- Credit-card or government-ID-based verification (for higher-risk processing).
- Postal verification.

The level of verification should be proportionate to the risk of the processing.

### 10. Consent in B2B Marketing

B2B marketing is not exempt from GDPR, but the ePrivacy Directive (Article 13(2)) allows soft opt-in for marketing of similar products to existing customers under specified conditions, and Member States have varying treatments. Always check local guidance.

In all cases:

- B2B marketing to a personal email address (e.g., name.surname@company.com) is regulated by GDPR.
- Marketing to a generic email address (e.g., info@company.com) is generally lower risk under GDPR but still requires fair processing.

### 11. Re-Consent: When You Need It

Re-consent (or reaffirmation) is required when:

- Consent text materially changes.
- Purposes are added or expanded (incompatible further processing).
- Recipient categories change in a way the original consent did not cover.
- Data subjects were originally consented under a now-deficient mechanism (e.g., pre-ticked boxes from before May 2018, or under a CMP later found non-compliant).
- A merger / acquisition transfers data to a controller with materially different processing.

Re-consent campaigns must use the same standard as initial consent — fresh, opt-in, granular.

### 12. Common Failure Modes

1. **Single "I agree to terms and privacy" checkbox covering processing for multiple purposes.** Fails granularity.
2. **"By continuing to browse, you accept cookies."** Fails affirmative-action requirement.
3. **Pre-ticked marketing checkbox at sign-up.** Fails affirmative action.
4. **Consent obtained under duress in employment context.** Fails freely given.
5. **Cookie banner with only "Accept" button or with "Reject" hidden behind several clicks.** Fails freely given (dark pattern under EDPB 03/2022).
6. **Withdrawal requires postal letter when consent was given by click.** Fails Art. 7(3).
7. **No record of what was consented to and when.** Fails Art. 7(1).
8. **"Consent" relied on for processing actually necessary for contract performance.** Wrong basis; should be Art. 6(1)(b).
9. **Children's age not verified; age below threshold without parental consent.** Fails Art. 8.

### 13. When Consent Is the Wrong Basis

Often, consent is *not* the right basis. Use the decision tree:

```
Is processing strictly necessary for performance of a contract with the data subject?
  Yes → Art. 6(1)(b) contract
  No  → Is there a legal obligation requiring this processing?
         Yes → Art. 6(1)(c) legal obligation
         No  → Is there a vital interest (life-or-death) at stake?
                Yes → Art. 6(1)(d) vital interests
                No  → Are you a public authority acting in public interest?
                       Yes → Art. 6(1)(e) public interest
                       No  → Is there a legitimate interest that outweighs the data subject's rights?
                              Yes → Art. 6(1)(f) legitimate interest (run LIA)
                              No  → Consent (Art. 6(1)(a)) is the only remaining basis — verify the four prongs
```

### 14. Consent Lifecycle Checklist

- [ ] Consent text drafted in plain language at the appropriate reading level.
- [ ] Consent text version-controlled with effective date.
- [ ] Each purpose has its own consent control.
- [ ] Default state is "off" (no pre-ticked).
- [ ] Withdrawal mechanism is easy to access and at least as easy as giving.
- [ ] Pre-consent disclosures meet "informed" standard.
- [ ] Parental verification mechanism for under-age users.
- [ ] Demonstrability records meet Art. 7(1).
- [ ] Re-consent triggers identified.
- [ ] CMP / consent platform tested quarterly.

---

## Türkçe

### 1. Yasal Tanım

İlgili kişinin onayı (Madde 4(11)), *ilgili kişinin kendisine ilişkin kişisel verilerin işlenmesine bir beyan veya açık onaylayıcı bir eylemle, özgürce verilen, belirli, bilgilendirilmiş ve kuşku götürmeyen biçimde anlaşma anlamına gelen herhangi bir irade beyanı*'dır.

Dört unsur (özgürce verilen, belirli, bilgilendirilmiş, kuşkusuz) artı kanıtlama gerekliliği (Madde 7(1)) ve geri çekme hakkı (Madde 7(3)) geçerli onay için temel testi oluşturur.

### 2. Birinci Unsur — Özgürce Verilmiş

**Test**: İlgili kişinin reddetmesi durumunda zarar görmeden gerçek bir seçeneği var mı?

EDPB Kılavuz 5/2020 dört alt test belirler:

#### 2.1 Güç Dengesizliği Yok

İlgili kişi ve veri sorumlusu arasında açık bir dengesizlik olduğunda onayın özgürce verilmediği varsayılır. En çok atıfta bulunulan örnek işveren-çalışan ilişkisidir: bir işveren, gerçek seçimin var olduğu dar bir dizi durum dışında (örn. istihdamı etkilemeyen iç bülten için fotoğraf çekmek), çalışan verilerinin işlenmesi için onaya dayanamaz.

Vatandaşların verilerini işleyen kamu otoriteleri benzer bir varsayımla karşı karşıyadır.

#### 2.2 Koşulluluk Yok

Madde 7(4): Onayın özgürce verilip verilmediği değerlendirilirken, sözleşmenin ifasının söz konusu ifa için gerekli olmayan bir onaya bağlı olup olmadığı dikkate alınmalıdır. Pazarlama onayı, pazarlama gerçekten hizmetin kendisi olmadıkça hizmetin koşulu olamaz.

"Hizmet karşılığı veri" modeli (site erişimi için çerez onayı talep eden çerez duvarları) EDPB ve çoğu ulusal otorite tarafından reddedildi. Kullanıcının gerçek bir alternatifi olmalıdır — genellikle, hizmetin izleme yapmayan bir sürümü, muhtemelen ücretli bir duvarın arkasında.

#### 2.3 Ayrıntılılık

Veri sorumlusu birden fazla amaç için onay arıyorsa (örn. bülten + ürün analitiği + reklam), her amacın ayrı sunulması gerekir, böylece ilgili kişi birine onay verip diğerlerini reddedebilir. Paketlenmiş onay ("Pazarlama, analitik ve ortak teklifler için iletişime kabul ediyorum") geçersizdir.

#### 2.4 Zarar Yok

Onayın reddedilmesi dezavantaja yol açmamalıdır. Zorunlu olmayan onayların verilmemesi, teslimi bu onayları gerektirmeyen bir hizmet veya özelliğe erişimi engellememelidir.

### 3. İkinci Unsur — Belirli

Onay **amaca özgü** olmalıdır. Veri sorumlusu:

- Her işleme amacını belirtmelidir.
- Her biri için ayrı onay aramalıdır.
- Veri sorumlusu veriyi yeni, uyumsuz bir amaç için kullanmak istiyorsa onayı yeniden alır.

### 4. Üçüncü Unsur — Bilgilendirilmiş

İlgili kişi en azından şunları bilmelidir:

1. Veri sorumlusunun kimliği.
2. Onayın aranma amacı.
3. Hangi tür verilerin toplanacağı.
4. Onayı geri çekme hakkı.
5. Otomatik karar verme kullanımı hakkında bilgi (uygulanabilirse).
6. Yeterlilik kararı olmaksızın üçüncü ülkelere aktarım riskleri (uygulanabilirse).

Bu bilgi onay anında sunulmalı, ayrı bir politikaya gömülmemelidir. Gizlilik bildirimine bağlantı, ek olarak hizmet eder ancak yerini almaz.

### 5. Dördüncü Unsur — Açık Onaylayıcı Eylemle Kuşkusuz İrade Beyanı

Onay olumlu bir eylem gerektirir. EDPB ve CJEU (Planet49 kararı) açıkça şunu belirtir:

- Önceden işaretli kutular geçerli onay değildir.
- Hareketsizlik onay değildir.
- Bir web sitesini kullanmaya devam etmek onay değildir.
- Banner'ı kapatmak onay değildir.
- Kaydırma onay değildir (EDPB 03/2022'de genişletilen Planet49 mantığına göre).

Geçerli onaylayıcı eylemler şunları içerir:

- İşaretsiz bir kutuyu işaretlemek.
- Açıkça etiketlenmiş "Kabul ediyorum" düğmesine tıklamak.
- "Hayır"ın eşit ölçüde belirgin olduğu ikili bir seçimde "evet"i seçmek.
- Sözel olarak "evet" demek (kayıtlı onayla).

### 6. Madde 7(1) — Kanıtlanabilirlik

Veri sorumlusu, onayın verildiğini gösterebilmelidir. Her onay kararı için:

- Kim onayladı (ilgili kişi tanımlayıcısı).
- Ne zaman (zaman damgası, saat dilimi).
- Gösterilen onay metni neydi (sürümlü politikaya bağlı).
- Mekanizma (örn. kutu işaretleme, düğme tıklaması).
- IP adresi ve kullanıcı aracı (çevrimiçi onay için, yararlıysa).
- Onayın geri çekilip çekilmediği ve ne zaman.

Bu kayıtlar yıllar sonra itiraz edildiğinde geri alınabilir olmalıdır.

### 7. Madde 7(3) — Geri Çekme Vermek Kadar Kolay

İlgili kişi onayı **verdiği kadar kolay** geri çekebilmelidir. Pratikte:

- Onay bir uygulamada tek tıklamayla alındıysa, geri çekme uygulamada tek tıklama olmalıdır — posta mektubu değil.
- Onay web formuyla verildiyse, geri çekme web üzerinden benzer adımlarda erişilebilir olmalıdır.
- Onay bir CMP çerez banner'ı aracılığıyla verildiyse, geri çekme kalıcı bir gizlilik tercihleri bağlantısından erişilebilir olmalıdır.

Geri çekme hakkı, onay verilmeden **önce** ilgili kişiye anlatılmalıdır (Madde 7(3) ikinci cümle).

### 8. Özel Kategoriler (Madde 9)

Özel kategori veri için Madde 9(2)(a), **açık onay** gerektirir. EDPB "açık"ı sıradan onayın üzerinde ek bir katman olarak yorumlar — genellikle ilgili kişi tarafından imzalanmış yazılı bir beyan (elektronik imza kabul edilebilir) veya açık iki adımlı opt-in. Önceden işaretli kutu özel kategori işleme için iki kat geçersizdir.

### 9. Madde 8 — Çocukların Onayı

Bilgi toplumu hizmetleri çocuğa doğrudan sunulduğunda, çocuğun onayı yalnızca çocuk en az 16 yaşında ise hukuka uygundur. Üye Devlet hukuku daha düşük yaş öngörebilir, ancak 13'ten düşük olmamalıdır.

| Üye Devlet | Yaş | Kaynak |
|-----------|-----|--------|
| Varsayılan GDPR | 16 | Madde 8(1) |
| Fransa | 15 | Loi Informatique et Libertés |
| Almanya | 16 | BDSG |
| İrlanda | 16 | Veri Koruma Kanunu 2018 |
| İtalya | 14 | İtalyan DPA Kodu |
| Hollanda | 16 | UAVG |
| İspanya | 14 | LOPDGDD |
| Birleşik Krallık | 13 | DPA 2018 (Brexit sonrası) |

Çocuk yaş eşiğinin altındaysa ebeveyn onayı gereklidir. Veri sorumlusu, mevcut teknolojiyi göz önüne alarak ebeveyn onayını doğrulamak için makul çaba göstermelidir (Madde 8(2)).

Makul çabalar şunları içerebilir:

- Ebeveyn e-posta adresine e-posta onayı.
- Kredi kartı veya devlet kimliği tabanlı doğrulama (daha yüksek riskli işleme için).
- Posta ile doğrulama.

Doğrulama seviyesi işlemenin riskiyle orantılı olmalıdır.

### 10. B2B Pazarlamada Onay

B2B pazarlama GDPR'dan muaf değildir, ancak ePrivacy Direktifi (Madde 13(2)) belirli koşullar altında mevcut müşterilere benzer ürünlerin pazarlanması için yumuşak opt-in'e izin verir ve Üye Devletlerin farklı uygulamaları vardır. Her zaman yerel rehberi kontrol edin.

Tüm durumlarda:

- Kişisel bir e-posta adresine (örn. ad.soyad@sirket.com) B2B pazarlama GDPR ile düzenlenir.
- Genel bir e-posta adresine (örn. info@sirket.com) pazarlama genellikle GDPR altında daha düşük risklidir ancak yine de adil işleme gerektirir.

### 11. Yeniden Onay: Ne Zaman İhtiyacınız Var

Yeniden onay (veya yeniden teyit) şu durumlarda gereklidir:

- Onay metni önemli değiştiğinde.
- Amaçlar eklendiğinde veya genişletildiğinde (uyumsuz ileri işleme).
- Alıcı kategorileri orijinal onayın kapsamadığı şekilde değiştiğinde.
- İlgili kişiler başlangıçta artık yetersiz bir mekanizma altında onaylanmışsa (örn. Mayıs 2018 öncesi önceden işaretli kutular veya sonradan uyumsuz bulunan bir CMP).
- Birleşme / devralma veriyi önemli ölçüde farklı işleme yapan bir veri sorumlusuna aktardığında.

Yeniden onay kampanyaları başlangıç onayıyla aynı standardı kullanmalıdır — taze, opt-in, ayrıntılı.

### 12. Yaygın Başarısızlık Modları

1. **Birden fazla amaç için tek "Şartları ve gizliliği kabul ediyorum" kutusu.** Ayrıntılılıkta başarısız.
2. **"Gezinmeye devam ederek çerezleri kabul edersiniz."** Olumlu eylem gerekliliğinde başarısız.
3. **Kayıtta önceden işaretli pazarlama kutusu.** Olumlu eylemde başarısız.
4. **İstihdam bağlamında baskı altında alınan onay.** Özgürce verilmede başarısız.
5. **Sadece "Kabul Et" düğmesi olan veya "Reddet"in birkaç tık arkasına gizlendiği çerez banner'ı.** Özgürce verilmede başarısız (EDPB 03/2022 altında karanlık desen).
6. **Onay tıklamayla verildiğinde geri çekme posta mektubu gerektirir.** Madde 7(3)'te başarısız.
7. **Neye ne zaman onay verildiğinin kaydı yok.** Madde 7(1)'de başarısız.
8. **Sözleşme ifası için gerçekten gerekli olan işleme için "onaya" dayanılması.** Yanlış sebep; Madde 6(1)(b) olmalı.
9. **Çocukların yaşı doğrulanmamış; ebeveyn onayı olmadan eşik altı yaş.** Madde 8'de başarısız.

### 13. Onayın Yanlış Sebep Olduğu Durumlar

Çoğu zaman onay *doğru* sebep değildir. Karar ağacı:

```
İşleme, ilgili kişiyle bir sözleşmenin ifası için kesinlikle gerekli mi?
  Evet → Madde 6(1)(b) sözleşme
  Hayır → Bu işlemeyi gerektiren yasal bir yükümlülük var mı?
          Evet → Madde 6(1)(c) yasal yükümlülük
          Hayır → Hayati menfaat (yaşam-ölüm) söz konusu mu?
                  Evet → Madde 6(1)(d) hayati menfaatler
                  Hayır → Kamu yararı için hareket eden bir kamu otoritesi misiniz?
                          Evet → Madde 6(1)(e) kamu yararı
                          Hayır → İlgili kişinin haklarından üstün gelen meşru bir menfaat var mı?
                                   Evet → Madde 6(1)(f) meşru menfaat (LIA çalıştırın)
                                   Hayır → Onay (Madde 6(1)(a)) tek kalan sebep — dört unsuru doğrulayın
```

### 14. Onay Yaşam Döngüsü Kontrol Listesi

- [ ] Onay metni uygun okuma seviyesinde sade dilde hazırlandı.
- [ ] Onay metni yürürlük tarihiyle sürüm kontrollü.
- [ ] Her amacın kendi onay kontrolü var.
- [ ] Varsayılan durum "kapalı" (önceden işaretli değil).
- [ ] Geri çekme mekanizması erişimi kolay ve en azından vermek kadar kolay.
- [ ] Onay öncesi ifşalar "bilgilendirilmiş" standardını karşılıyor.
- [ ] Yaş altı kullanıcılar için ebeveyn doğrulama mekanizması.
- [ ] Kanıtlanabilirlik kayıtları Madde 7(1)'i karşılıyor.
- [ ] Yeniden onay tetikleyicileri belirlendi.
- [ ] CMP / onay platformu üç ayda bir test edilir.
