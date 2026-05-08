---
title:
  en: "Communication of a Personal Data Breach to the Data Subject"
  tr: "Kişisel Veri İhlalinin İlgili Kişiye Bildirilmesi"
section: "08-breach-management"
document_id: "BR-NOT-002"
owner: "Data Protection Officer / Communications Lead"
classification: "Internal — Restricted"
version: "1.0"
last_review: "2026-05-08"
next_review: "2027-05-08"
language: ["en", "tr"]
references:
  - "GDPR Art. 34 — Communication of a personal data breach to the data subject"
  - "GDPR Art. 12 — Transparent information and modalities"
  - "GDPR Recitals 86, 88"
  - "EDPB Guidelines 9/2022 on personal data breach notification under GDPR"
  - "EDPB Guidelines 01/2021 — Examples regarding personal data breach notification"
---

## English

### 1. The trigger — high risk to rights and freedoms

Article 34(1) GDPR requires the controller to communicate a personal data breach to the data subject without undue delay when the breach is likely to result in a "high risk to the rights and freedoms of natural persons". This is a stricter threshold than Article 33: a breach that triggers SA notification will not always trigger data subject communication.

The high-risk threshold draws on the same factors as the DPIA threshold under Article 35: scale, sensitivity, reversibility, identifiability, and the position of vulnerable groups. EDPB 9/2022 emphasises that the assessment is forward-looking — what is the realistic worst-case impact on individuals if the data is misused.

### 2. Examples that typically meet the high-risk threshold

EDPB 01/2021 and case practice point to the following non-exhaustive list:

- Disclosure of bank account numbers, payment card data, or other directly monetisable identifiers.
- Disclosure of health data, sexual orientation, or other Article 9 special categories.
- Disclosure of identity documents (passport, national ID) sufficient to enable identity theft.
- Loss of access to data critical to a person's well-being (e.g. medical records during treatment).
- Targeted disclosure that exposes a person to physical danger (e.g. domestic violence shelter resident addresses).
- Children's data combined with location or behavioural information.
- Government-issued credentials enabling impersonation.

### 3. Exemptions — Article 34(3)

Communication to the data subject is not required if any of the following apply:

(a) **Encryption rendering data unintelligible.** The controller has implemented appropriate technical and organisational protection measures, in particular those that render the personal data unintelligible to any person not authorised to access it, such as encryption, and those measures were applied to the data affected by the breach.

(b) **Subsequent measures.** The controller has taken subsequent measures which ensure that the high risk to the rights and freedoms of data subjects is no longer likely to materialise.

(c) **Disproportionate effort.** It would involve disproportionate effort. In such a case, there shall instead be a public communication or similar measure whereby the data subjects are informed in an equally effective manner.

EDPB 9/2022 §54 cautions that the encryption exemption requires modern, strong encryption with the key under exclusive control of the controller and not compromised in the breach. AES-256, in transit and at rest, with HSM-stored keys, is the credible baseline. Hashed-but-unsalted password leaks do not qualify.

The disproportionate-effort exemption requires public communication of equivalent reach. A press release on a low-traffic corporate website is insufficient when affected individuals are members of the public; affirmative outreach is generally required.

### 4. Decision matrix — to communicate or not

| Question | Answer | Path |
|----------|--------|------|
| Is the breach likely to result in a high risk to rights and freedoms? | No | No Article 34 communication; document rationale in Article 33(5) register |
| Yes, but is the affected data effectively encrypted with uncompromised keys? | Yes | Communication not required; document the encryption regime, key custody, and that no key compromise occurred |
| Yes, and have subsequent measures eliminated the high risk before harm could materialise? | Yes | Communication not required; document the subsequent measures and the basis for concluding risk has been mitigated |
| Yes, and would individual communication require disproportionate effort? | Yes | Use public communication of equivalent reach; document the proportionality reasoning |
| Otherwise | — | Communicate to each affected data subject without undue delay |

### 5. Timing

The Article 34 communication must be made "without undue delay". There is no fixed numeric deadline like the 72-hour SA window. EDPB 9/2022 states that timing should account for:

- the nature of the risk (immediate financial loss may require near-real-time alerting);
- whether the SA has issued any direction (an SA may require the controller to communicate under Article 34(4));
- the maturity of the controller's understanding of the breach (do not communicate prematurely with inaccurate facts);
- coordination with law enforcement (a brief delay can be justified to avoid prejudicing an investigation, but must be revisited frequently).

For most cases, communication within 7 days of awareness is appropriate; complex cases may justify 14–30 days with documentation of the reason.

### 6. Required content of the communication — Article 34(2)

The communication must:

- describe in clear and plain language the nature of the personal data breach;
- contain at least the information and measures referred to in points (b), (c), and (d) of Article 33(3) — DPO contact, likely consequences, measures taken or proposed.

EDPB 9/2022 reminds controllers that the language must be appropriate to the audience: children, elderly users, non-native speakers, and people with disabilities all require careful drafting and accessibility consideration.

### 7. Drafting standards

Each communication must:

1. Lead with what happened, in plain language, in the first paragraph.
2. State what data is affected, specifically.
3. State what the likely consequences are for the individual.
4. State the practical steps the individual can take (rotate password, monitor accounts, check credit, freeze credit file, contact bank, request new ID, etc.).
5. State what the controller has done.
6. Provide a contact route (DPO email, dedicated hotline, FAQ link).
7. Provide reference to the SA (right to lodge a complaint).
8. Be available in the language(s) of the affected data subjects, with translation where appropriate.
9. Be free of marketing content, brand-burnishing language, or attempts to deflect responsibility.
10. Be sent through a verified, durable channel.

Banned drafting patterns:

- "We take privacy very seriously" without substantive content.
- Burying the disclosure mid-document.
- Confusing reassurance with deception ("there is nothing to worry about" when there is something to worry about).
- Imposing waivers, releases, or terms-of-service changes inside the breach notice.

### 8. Channels

The channel should be:

- **Direct**: email, postal letter, in-app notification, secure messaging.
- **Verifiable**: the controller must be able to evidence delivery (mail logs, SMTP receipts, in-app read receipts, postal certificates).
- **Free of additional friction**: a click-to-acknowledge interstitial inside a paywalled service is not adequate as the primary channel.
- **Accessible**: WCAG-compliant for digital channels; large print or alternative formats on request.

Public communication under Article 34(3)(c) (disproportionate effort exemption) requires:

- prominent placement on the controller's main public web property;
- press release distributed to mainstream and relevant specialist outlets;
- duration sufficient to give affected persons reasonable opportunity to learn (commonly at least 30 days);
- archival page indexed and findable;
- complementary social-media announcements if a material part of the affected population uses those channels.

### 9. Coordination with the SA

Article 34(4) empowers the SA, after considering the likelihood of the breach resulting in high risk, to require the controller to do the communication, or it may decide that any of the conditions referred to in paragraph 3 are met. The controller should:

- not assume an exemption applies without evidencing the basis;
- file the Article 33 notification first or in parallel;
- be prepared to defend the exemption in subsequent SA correspondence;
- communicate to data subjects if the SA so directs, even if the controller initially concluded that an exemption applied.

### 10. Coordination with law enforcement

If a law enforcement agency is investigating the breach, the controller may delay public or individual notification only to the extent strictly necessary to avoid prejudicing the investigation, and only with documented agency request. The DPO must record the request and revisit the position regularly. Article 23 GDPR allows Member State law to restrict the Article 34 obligation in narrow circumstances; this is not a general licence to delay.

### 11. Re-victimisation and downstream harm

A poorly drafted breach notice can cause additional harm:

- repeating sensitive details unnecessarily in the message body;
- including personal data of other affected persons;
- using channels that themselves expose the individual (sending to a shared inbox);
- announcing too soon, before mitigation steps such as credential resets are in place;
- creating a phishable channel (a notice that resembles phishing trains people to click on phishing).

The communication should be designed to be clearly distinguishable from phishing: arrives from an authenticated domain, contains no clickable login links, points to known controlled URLs the recipient already knows, includes a callback identifier the recipient can verify by independently calling a published number.

### 12. Children and vulnerable groups

For children's data, the notice must be drafted to be understandable by the parent or guardian, with a child-readable annex if the child is the data subject. Vulnerable groups (e.g. residents of women's shelters, persons in witness protection, persons with cognitive disabilities) may require alternative or assisted channels. The DPO consults relevant social services or charities where appropriate.

### 13. Documentation

Every communication action must be documented:

- the text(s) issued, with version control;
- the channels used;
- the recipient list and delivery confirmations;
- the language(s) and the rationale for translation choices;
- the support call-volume and any patterns observed;
- the public communication artefacts (URLs, press release IDs, archived screenshots) where the disproportionate-effort exemption was relied upon.

This evidence sits in the Article 33(5) internal register and is available to the SA on request.

---

## Türkçe

### 1. Tetikleyici — hak ve özgürlüklere yüksek risk

GDPR Madde 34(1), ihlalin "gerçek kişilerin hak ve özgürlükleri açısından yüksek risk" oluşturma olasılığı bulunduğunda veri sorumlusunun kişisel veri ihlalini gecikmeksizin ilgili kişiye iletmesini gerektirir. Bu, Madde 33'ten daha katı bir eşiktir: DM bildirimi tetikleyen bir ihlal her zaman ilgili kişi iletişimini tetiklemez.

Yüksek risk eşiği, Madde 35 altındaki VKD eşiğiyle aynı faktörlerden yararlanır: ölçek, hassasiyet, geri döndürülemezlik, kimliklendirilebilirlik ve savunmasız grupların durumu. EDPB 9/2022, değerlendirmenin ileriye dönük olduğunu vurgular — verinin kötüye kullanılması durumunda bireyler üzerindeki gerçekçi en kötü senaryo etki nedir.

### 2. Yüksek risk eşiğini tipik olarak karşılayan örnekler

- Banka hesap numaraları, ödeme kartı verileri veya diğer doğrudan paraya çevrilebilir tanımlayıcıların ifşası.
- Sağlık verileri, cinsel yönelim veya diğer Madde 9 özel kategorilerinin ifşası.
- Kimlik hırsızlığını mümkün kılacak kimlik belgelerinin (pasaport, ulusal kimlik) ifşası.
- Bir kişinin esenliği için kritik verilere erişim kaybı (örn. tedavi sırasında sağlık kayıtları).
- Bir kişiyi fiziksel tehlikeye maruz bırakan hedeflenmiş ifşa (örn. kadın sığınağı sakini adresleri).
- Konum veya davranışsal bilgilerle birleştirilmiş çocuk verileri.
- Kimliğe bürünmeyi mümkün kılan resmi kimlik bilgileri.

### 3. Muafiyetler — Madde 34(3)

İlgili kişiye iletişim aşağıdakilerden herhangi biri geçerliyse gerekli değildir:

(a) **Verileri okunamaz hale getiren şifreleme.** Veri sorumlusu uygun teknik ve organizasyonel önlemleri uygulamış, özellikle kişisel verileri erişimi yetkili olmayan herhangi bir kişi için anlaşılmaz hale getiren önlemler (şifreleme gibi) ve bu önlemler ihlalden etkilenen verilere uygulanmıştır.

(b) **Sonraki önlemler.** Veri sorumlusu, ilgili kişilerin hak ve özgürlüklerine yüksek riskin artık gerçekleşme olasılığının olmamasını sağlayan sonraki önlemler almıştır.

(c) **Orantısız çaba.** Bu, orantısız çaba gerektirir. Böyle bir durumda, ilgili kişilerin eşit derecede etkili bir şekilde bilgilendirildiği bir kamu iletişimi veya benzeri bir önlem alınmalıdır.

EDPB 9/2022 §54, şifreleme muafiyetinin modern, güçlü şifreleme gerektirdiğini ve anahtarın veri sorumlusunun özel kontrolünde ve ihlalde tehlikeye girmemiş olması gerektiğini uyarır. HSM saklı anahtarlarla aktarımda ve dinlenmede AES-256 inandırıcı temeldir. Karılmamış şifre sızıntıları nitelik kazanmaz.

Orantısız çaba muafiyeti eşdeğer erişimde kamu iletişimini gerektirir.

### 4. Karar matrisi

| Soru | Cevap | Yol |
|------|-------|-----|
| İhlal hak ve özgürlüklere yüksek risk doğurur mu? | Hayır | Madde 34 iletişimi yok; Madde 33(5) kayıtta gerekçeyi belgeleyin |
| Evet, ancak etkilenen veri tehlikeye girmemiş anahtarlarla etkili biçimde şifreli mi? | Evet | İletişim gerekmez; şifreleme rejimini, anahtar saklamayı belgeleyin |
| Evet ve sonraki önlemler zarar gerçekleşmeden önce yüksek riski ortadan kaldırdı mı? | Evet | İletişim gerekmez; sonraki önlemleri belgeleyin |
| Evet ve bireysel iletişim orantısız çaba gerektirir mi? | Evet | Eşdeğer erişimde kamu iletişimi kullanın; orantılılık gerekçesini belgeleyin |
| Aksi takdirde | — | Her etkilenen ilgili kişiye gecikmeksizin bildirin |

### 5. Zamanlama

Madde 34 iletişimi "gecikmeksizin" yapılmalıdır. 72 saatlik DM penceresi gibi sabit sayısal bir son tarih yoktur.

Çoğu durumda, farkındalıktan itibaren 7 gün içinde iletişim uygundur; karmaşık vakalar nedeni belgelenerek 14–30 günü haklı kılabilir.

### 6. İletişimin gerekli içeriği — Madde 34(2)

İletişim:

- kişisel veri ihlalinin niteliğini açık ve sade bir dille açıklamalıdır;
- en azından Madde 33(3)(b), (c) ve (d) noktalarında belirtilen bilgi ve önlemleri içermelidir.

### 7. Taslak hazırlama standartları

Her iletişim:

1. İlk paragrafta sade dille ne olduğunu açıklamalıdır.
2. Hangi verilerin etkilendiğini özellikle belirtmelidir.
3. Birey için olası sonuçları belirtmelidir.
4. Bireyin alabileceği pratik adımları belirtmelidir.
5. Veri sorumlusunun ne yaptığını belirtmelidir.
6. Bir iletişim yolu sağlamalıdır.
7. DM'ye atıf yapmalıdır.
8. İlgili kişilerin dilinde mevcut olmalıdır.
9. Pazarlama içeriğinden, marka cilalama dilinden veya sorumluluğu saptırma girişimlerinden uzak olmalıdır.
10. Doğrulanmış, dayanıklı bir kanal üzerinden gönderilmelidir.

Yasaklı taslak desenleri:

- İçerik olmadan "Mahremiyeti çok ciddiye alıyoruz".
- İfşayı belge ortasına gömme.
- Güvence ile aldatmayı karıştırma.
- İhlal bildirimi içine feragatname veya hizmet şartları değişikliği koyma.

### 8. Kanallar

Kanal:

- **Doğrudan**: e-posta, posta mektubu, uygulama içi bildirim, güvenli mesajlaşma.
- **Doğrulanabilir**: veri sorumlusu teslimatı kanıtlayabilmelidir.
- **Ek sürtünmesiz**: ücretli hizmet içinde tıkla-onayla ara sayfa birincil kanal olarak yeterli değildir.
- **Erişilebilir**: dijital kanallar için WCAG uyumlu.

Madde 34(3)(c) altında kamu iletişimi:

- veri sorumlusunun ana kamu web mülkünde belirgin yerleşim;
- ana akım ve ilgili uzman kuruluşlara dağıtılan basın bülteni;
- etkilenen kişilere makul fırsat verecek süre (genellikle en az 30 gün);
- arşiv sayfası indekslenmiş ve bulunabilir;
- nüfusun önemli bir kısmı bu kanalları kullanıyorsa tamamlayıcı sosyal medya duyuruları.

### 9. DM ile koordinasyon

Madde 34(4), ihlalin yüksek risk doğurma olasılığını dikkate aldıktan sonra, DM'nin veri sorumlusundan iletişimi yapmasını isteyebileceğini veya 3. paragrafta belirtilen koşullardan herhangi birinin karşılandığına karar verebileceğini düzenler.

### 10. Kolluk kuvvetleriyle koordinasyon

Bir kolluk kuvveti ihlali soruşturuyorsa, veri sorumlusu kamuya açık veya bireysel bildirimi yalnızca soruşturmaya zarar vermekten kaçınmak için kesinlikle gerekli olduğu ölçüde ve yalnızca belgelenmiş kurum talebiyle erteleyebilir. Madde 23, dar koşullarda Madde 34 yükümlülüğünü kısıtlamaya Üye Devlet hukukuna izin verir.

### 11. Yeniden mağduriyet ve aşağı yönlü zarar

Kötü hazırlanmış bir ihlal bildirimi ek zarara neden olabilir:

- mesaj gövdesinde gereksiz yere hassas ayrıntıları tekrarlama;
- diğer etkilenen kişilerin kişisel verilerini içerme;
- bireyi maruz bırakan kanalları kullanma (paylaşılan gelen kutusuna gönderme);
- kimlik bilgisi sıfırlama gibi azaltma adımları yerleşmeden çok erken duyurma;
- oltalanabilir bir kanal yaratma.

İletişim, oltalamadan açıkça ayırt edilebilir olacak şekilde tasarlanmalıdır.

### 12. Çocuklar ve savunmasız gruplar

Çocuk verileri için bildirim ebeveyn veya vasi tarafından anlaşılır olmalıdır. Savunmasız gruplar alternatif veya destekli kanallar gerektirebilir.

### 13. Belgeleme

Her iletişim eylemi belgelenmelidir:

- yayımlanan metin(ler), sürüm kontrolüyle;
- kullanılan kanallar;
- alıcı listesi ve teslimat onayları;
- dil(ler) ve çeviri seçimleri için gerekçe;
- destek arama hacmi ve gözlenen örüntüler;
- kamuya açık iletişim yapıtları (URL'ler, basın bülten kimlikleri, arşivlenmiş ekran görüntüleri).

Bu kanıt, Madde 33(5) iç kayıtta yer alır ve talep üzerine DM'ye sunulur.
