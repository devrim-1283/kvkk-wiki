---
Document / Doküman: Article 5 Principles & Article 6 Lawful Bases — with LIA Template / Madde 5 İlkeleri ve Madde 6 Hukuki Dayanaklar — LIA Şablonu ile
Section / Bölüm: 01-core-concepts
Owner / Sahip: Data Protection Officer (DPO) / Veri Koruma Görevlisi
Approved by / Onaylayan: General Counsel / Genel Hukuk Müşaviri
Version / Versiyon: 1.0
Effective / Yürürlük: 2026-05-08
Review / Gözden Geçirme: Annual + triggered / Yıllık + tetiklenmiş
Legal Reference / İlgili Mevzuat: GDPR Art. 5, 6, 7, 9, 10; EDPB Guidelines 05/2020 on consent; EDPB Guidelines 02/2019 on contract (Art. 6(1)(b)); ECJ Bara (C-201/14), Planet49 (C-673/17), Meta Platforms (C-252/21)
---

## English

### 1. Purpose

This document defines the **principles** of processing under Article 5 GDPR and the **lawful bases** under Article 6, including operational guidance, the conditions for valid consent (Article 7), the doctrine that lawful bases generally cannot be switched mid-stream, and a Legitimate Interests Assessment (LIA) template. It is the gateway control: no processing exists in the company without a documented lawful basis.

### 2. Article 5 — Principles Relating to Processing

#### 2.1 Lawfulness, Fairness, and Transparency (Art. 5(1)(a))
Processing must have a lawful basis (Art. 6, plus Art. 9(2) for special categories), be fair (no deception or unjustified detriment), and be transparent (Art. 12–14 notices accessible).

#### 2.2 Purpose Limitation (Art. 5(1)(b))
Data collected for specified, explicit, and legitimate purposes; not further processed in a manner incompatible with those purposes. Compatibility test (Art. 6(4)): link between purposes; context of collection; nature of the data; consequences for data subjects; safeguards. Further processing for archiving in the public interest, scientific or historical research, or statistics with Art. 89(1) safeguards is presumed compatible.

#### 2.3 Data Minimization (Art. 5(1)(c))
Adequate, relevant, and limited to what is necessary for the purposes. Operational rule: justify each field; remove fields that are "nice to have" but not necessary.

#### 2.4 Accuracy (Art. 5(1)(d))
Accurate and, where necessary, kept up to date. Inaccurate data must be erased or rectified without delay.

#### 2.5 Storage Limitation (Art. 5(1)(e))
Kept in a form which permits identification for no longer than necessary. Implement retention schedules; review trigger events (e.g., end of contract + statutory periods).

#### 2.6 Integrity and Confidentiality (Art. 5(1)(f))
Processed in a manner that ensures appropriate security, including protection against unauthorized or unlawful processing and accidental loss, destruction, or damage. See Article 32.

#### 2.7 Accountability (Art. 5(2))
Controller is responsible for, and must be able to demonstrate, compliance with the principles. This is the meta-principle that makes everything else evidentiary.

### 3. Article 6 — Lawful Bases (closed list)

Processing of ordinary personal data is lawful only if at least one of the following applies:

#### 3.1 Consent (Art. 6(1)(a))
Data subject has given consent for one or more specific purposes. Conditions in Art. 7 apply (see Section 5). Withdrawal must be as easy as giving (Art. 7(3)). Default-on or pre-ticked boxes invalid (Planet49 C-673/17).

#### 3.2 Contract (Art. 6(1)(b))
Necessary for the performance of a contract to which the data subject is party, or to take steps at the data subject's request prior to entering into a contract. EDPB Guidelines 02/2019: "necessary" is strict — not merely useful. Behavioral advertising rarely qualifies.

#### 3.3 Legal Obligation (Art. 6(1)(c))
Necessary for compliance with a legal obligation to which the controller is subject. Must be a Union or Member State law, sufficiently clear, with a clear public-interest objective. Examples: tax records, AML KYC, employment law records.

#### 3.4 Vital Interests (Art. 6(1)(d))
Necessary to protect the vital interests of the data subject or another natural person. Generally life-or-death situations. Should not be used where another basis applies.

#### 3.5 Public Task (Art. 6(1)(e))
Necessary for the performance of a task carried out in the public interest or in the exercise of official authority vested in the controller. Mostly relevant to public bodies; private bodies only when delegated by law.

#### 3.6 Legitimate Interests (Art. 6(1)(f))
Necessary for the purposes of the legitimate interests pursued by the controller or by a third party, except where such interests are overridden by the interests or fundamental rights and freedoms of the data subject which require protection of personal data, in particular where the data subject is a child. Not available to public authorities for tasks performed in the exercise of their duties. Requires a documented Legitimate Interests Assessment (LIA).

### 4. Selecting the Right Lawful Basis

| Scenario | Likely basis | Notes |
|---|---|---|
| Pay an employee | Contract (Art. 6(1)(b)) + Legal obligation (Art. 6(1)(c)) for tax / social security | Multiple bases possible per dataset/purpose. |
| Send transactional email confirming order | Contract (Art. 6(1)(b)) | Marketing not contractual. |
| Send marketing email to existing customer | Legitimate interests (Art. 6(1)(f)) + ePrivacy soft opt-in (where Member State law allows) | Always provide unsubscribe; honor objection (Art. 21(2)). |
| Send marketing email to non-customer | Consent | Opt-in required. |
| Maintain CCTV for security | Legitimate interests | LIA required; signage and notices. |
| Customer KYC for AML | Legal obligation | Specify the law. |
| Health insurance enrollment | Legal obligation + special category (Art. 9(2)(b)) | Member State law key. |
| Personalized product recommendations | Legitimate interests (with caution) or consent | Context-sensitive; consider data minimization. |
| Cookies for analytics or advertising | Consent (ePrivacy + GDPR) | Strictly necessary cookies exempt. |

### 5. Article 7 — Conditions for Consent

- (1) Demonstrability — controller must be able to demonstrate consent was given.
- (2) Form — clear, plain, distinguishable from other matters; separate consent for separate purposes.
- (3) Withdrawal — must be as easy to withdraw as to give; data subject informed prior to giving.
- (4) Conditional service — conditioning a service on consent for unnecessary processing is a strong indicator that consent is not freely given.

EDPB Guidelines 05/2020:
- "Freely given" — no power imbalance, no detriment, no bundling.
- "Specific" — granular per purpose.
- "Informed" — identity of controller, purpose, types of data, right to withdraw, automated decision-making.
- "Unambiguous" — clear affirmative action; silence, pre-ticked boxes, or inactivity is not consent.

### 6. The Switching-Bases Rule

As a general rule, **lawful bases cannot be swapped mid-stream**. If the original basis fails (e.g., consent withdrawn), the controller cannot retroactively rely on legitimate interests to keep processing.

Exceptions / nuance:
- For new, distinct processing, a new basis may apply.
- Compatibility test under Art. 6(4) may permit further processing for compatible purposes.
- Always document the rationale.

### 7. Legitimate Interests Assessment (LIA) Template

Use this template for every Article 6(1)(f) reliance.

```
LIA — Legitimate Interests Assessment

1. Identification
   1.1 Processing activity: ___________________________________
   1.2 Controller (and joint controller if any): _____________
   1.3 BU owner: ____________________
   1.4 Date: ____________________
   1.5 Reviewers: DPO ___________________ ; GC ___________________
   1.6 ROPA reference: ____________________

2. Purpose Test — Is there a legitimate interest?
   2.1 Describe the interest pursued by the controller or third party.
   2.2 Is it lawful, ethical, real, and present (not speculative)?
   2.3 What benefits arise (to the controller, third parties, the data subject, the public)?
   2.4 Could the purpose be achieved by another lawful basis?
       Answer: Yes / No. If yes, prefer the other basis.

3. Necessity Test — Is the processing necessary?
   3.1 Is processing necessary, or is there a less intrusive alternative?
   3.2 Have you minimized data fields?
   3.3 Have you minimized retention?
   3.4 Are pseudonymization / encryption applied?

4. Balancing Test — Do the data subject's rights override?
   4.1 Reasonable expectations of the data subject:
       - Existing relationship?
       - Manner of collection?
       - Communication?
   4.2 Nature of the data:
       - Special categories or criminal data → not available; rely on Art. 9(2) / 10.
       - Particularly sensitive (e.g., financial, location) — heightened scrutiny.
   4.3 Possible impacts on the data subject:
       - Material impact (financial, employment, opportunity)?
       - Non-material impact (chilling effect, embarrassment, profiling stigma)?
   4.4 Vulnerable individuals (children, employees, patients, beneficiaries)?
   4.5 Mitigations:
       - Easy and prominent right to object.
       - Data minimization.
       - Pseudonymization / encryption.
       - Strict access controls.
       - Short retention.
       - Transparent privacy notice.

5. Conclusion
   5.1 Does legitimate interest prevail? Yes / No.
   5.2 If Yes, document the safeguards and proceed; communicate via Art. 13/14 notice.
   5.3 If No, do not process under Art. 6(1)(f); choose another basis or do not proceed.

6. Approvals and Review
   6.1 BU owner sign-off: ____________________ Date: ________
   6.2 DPO opinion: ____________________ Date: ________
   6.3 GC sign-off: ____________________ Date: ________
   6.4 Review trigger: change of purpose, scale, data, vendor, jurisdiction.
   6.5 Next scheduled review: ____________________
```

### 8. Documentation — Per ROPA Entry

For each ROPA entry the controller documents:

- Purpose(s).
- Lawful basis (Article 6 paragraph and sub-paragraph).
- Where applicable, special category condition (Article 9(2)) or criminal data authorization (Article 10).
- LIA reference if Art. 6(1)(f) used.
- Consent capture mechanism if Art. 6(1)(a) used.
- Retention period.
- Recipients.
- Transfer mechanism.

### 9. Common Pitfalls

- Defaulting to "consent" because it feels safest — when consent is not freely given, the basis collapses and so does the processing.
- Treating "legitimate interests" as a catch-all without an LIA.
- Assuming "contract" covers analytics or marketing (rarely "necessary").
- Switching from "consent" to "legitimate interests" after consent is withdrawn.
- Bundling many purposes into a single consent.
- Failing to evidence consent (no record, no version of the notice, no timestamp).
- Forgetting to publish a meaningful description of legitimate interests in the Article 13/14 notice.

### 10. Operational Controls

- New processing intake gate enforces lawful basis selection.
- LIAs are stored in a central repository, indexed by ROPA entry.
- Consent records held in an immutable log with: timestamp, version of notice, mechanism, scope, IP/device hash if applicable, and withdrawal events.
- Periodic audit by Internal Audit verifies lawful basis assertion against actual processing observed in systems.

---

## Türkçe

### 1. Amaç

Bu belge, GDPR Madde 5 kapsamındaki işleme **ilkelerini** ve Madde 6 kapsamındaki **hukuki dayanakları** tanımlar; operasyonel rehberlik, geçerli rıza koşulları (Madde 7), hukuki dayanakların genel kural olarak yarı yolda değiştirilemediği doktrini ve bir Meşru Menfaat Değerlendirmesi (LIA) şablonu sunar. Geçit kontrolüdür: şirkette belgelenmiş hukuki dayanağı olmadan hiçbir işleme yoktur.

### 2. Madde 5 — İşlemeye İlişkin İlkeler

#### 2.1 Hukuka Uygunluk, Adillik ve Şeffaflık (Md. 5(1)(a))
İşleme bir hukuki dayanağa (Md. 6, özel kategoriler için Md. 9(2)) sahip olmalı, adil olmalı (aldatma veya haksız zarar vermemeli) ve şeffaf olmalıdır (Md. 12–14 metinleri erişilebilir).

#### 2.2 Amaç Sınırlaması (Md. 5(1)(b))
Veriler belirli, açık ve meşru amaçlarla toplanır; bu amaçlarla bağdaşmayan biçimde daha sonra işlenemez. Uyumluluk testi (Md. 6(4)): amaçlar arasındaki bağlantı; toplama bağlamı; verinin niteliği; ilgili kişiler için sonuçlar; güvenceler. Md. 89(1) güvenceleri ile kamu yararına arşivleme, bilimsel veya tarihsel araştırma ya da istatistik için ileri işleme uyumlu kabul edilir.

#### 2.3 Veri Minimizasyonu (Md. 5(1)(c))
Amaçlarla yeterli, ilgili ve gereken kadarla sınırlı. Operasyonel kural: her alanı gerekçelendirin; "olsa iyi olur" ama gerekli olmayan alanları kaldırın.

#### 2.4 Doğruluk (Md. 5(1)(d))
Doğru ve gerektiğinde güncel tutulan. Hatalı veriler gecikmeksizin silinmeli veya düzeltilmelidir.

#### 2.5 Saklama Sınırlaması (Md. 5(1)(e))
Tanımlamaya izin veren biçimde gerekenden uzun saklanmamalıdır. Saklama planları uygulayın; tetikleyici olayları gözden geçirin (örn. sözleşme sonu + yasal süreler).

#### 2.6 Bütünlük ve Gizlilik (Md. 5(1)(f))
Yetkisiz veya hukuka aykırı işlemeye, kazara kayba, imhaya veya zarara karşı koruma dahil uygun güvenliği sağlayan biçimde işlenir. Bkz. Madde 32.

#### 2.7 Hesap Verebilirlik (Md. 5(2))
Veri sorumlusu ilkelere uyumdan sorumludur ve uyumu kanıtlayabilmelidir. Bu, diğer her şeyi kanıt temelli kılan üst ilkedir.

### 3. Madde 6 — Hukuki Dayanaklar (kapalı liste)

Sıradan kişisel verinin işlenmesi yalnızca aşağıdakilerden en az biri uygulandığında hukuka uygundur:

#### 3.1 Rıza (Md. 6(1)(a))
İlgili kişi bir veya daha fazla belirli amaç için rıza vermiştir. Md. 7 koşulları geçerlidir (bkz. Bölüm 5). Rıza geri çekme, vermek kadar kolay olmalıdır (Md. 7(3)). Varsayılan açık veya önceden işaretli kutular geçersizdir (Planet49 C-673/17).

#### 3.2 Sözleşme (Md. 6(1)(b))
İlgili kişinin taraf olduğu bir sözleşmenin ifası için veya sözleşmeye girmeden önce ilgili kişinin talebi üzerine adımlar atmak için gerekli. EDPB 02/2019 Rehberi: "gerekli" sıkı yorumlanır — yalnızca yararlı olması yetmez. Davranışsal reklam nadiren karşılar.

#### 3.3 Yasal Yükümlülük (Md. 6(1)(c))
Veri sorumlusunun tabi olduğu yasal yükümlülüğe uyum için gerekli. Açık kamu yararı amacı taşıyan, yeterince açık bir Birlik veya Üye Devlet hukuku olmalıdır. Örnekler: vergi kayıtları, AML KYC, iş hukuku kayıtları.

#### 3.4 Hayati Menfaatler (Md. 6(1)(d))
İlgili kişinin veya başka bir gerçek kişinin hayati menfaatlerini korumak için gerekli. Genellikle yaşam-ölüm durumları. Başka bir dayanak uygulandığında kullanılmamalıdır.

#### 3.5 Kamu Görevi (Md. 6(1)(e))
Veri sorumlusuna verilen kamu yararına bir görevin ifası veya resmi yetkinin kullanılması için gerekli. Çoğunlukla kamu kurumlarıyla ilgilidir; özel kurumlar yalnızca yasayla yetkilendirildiğinde.

#### 3.6 Meşru Menfaat (Md. 6(1)(f))
Veri sorumlusu veya üçüncü taraflarca güdülen meşru menfaatler için gerekli; meğer ki bu menfaatler ilgili kişinin kişisel verisinin korunmasını gerektiren menfaat veya temel hak ve özgürlükleri tarafından, özellikle çocuk olduğunda, üstün gelmiş olsun. Görevlerinin ifasında kamu kurumları için kullanılamaz. Belgelenmiş bir Meşru Menfaat Değerlendirmesi (LIA) gerektirir.

### 4. Doğru Hukuki Dayanağın Seçilmesi

| Senaryo | Olası dayanak | Notlar |
|---|---|---|
| Çalışana maaş ödeme | Sözleşme (Md. 6(1)(b)) + vergi/sosyal güvenlik için Yasal Yükümlülük (Md. 6(1)(c)) | Veri kümesi/amaç başına birden fazla dayanak mümkün. |
| Sipariş onaylayan işlem e-postası gönderme | Sözleşme (Md. 6(1)(b)) | Pazarlama sözleşmeye dahil değildir. |
| Mevcut müşteriye pazarlama e-postası gönderme | Meşru menfaat (Md. 6(1)(f)) + ePrivacy yumuşak opt-in (Üye Devlet hukuku izin verirse) | Daima abonelik iptali sağlanır; itiraz yerine getirilir (Md. 21(2)). |
| Müşteri olmayan kişiye pazarlama e-postası | Rıza | Opt-in gereklidir. |
| Güvenlik için CCTV | Meşru menfaat | LIA gerekir; tabela ve bildirimler. |
| AML için müşteri KYC | Yasal yükümlülük | Yasayı belirtin. |
| Sağlık sigortası kaydı | Yasal yükümlülük + özel kategori (Md. 9(2)(b)) | Üye Devlet hukuku kritik. |
| Kişiselleştirilmiş ürün önerileri | Meşru menfaat (dikkatli) veya rıza | Bağlama duyarlı; veri minimizasyonu değerlendirin. |
| Analitik veya reklam için çerezler | Rıza (ePrivacy + GDPR) | Kesinlikle gerekli çerezler muaf. |

### 5. Madde 7 — Rıza Koşulları

- (1) Kanıtlanabilirlik — veri sorumlusu rızanın verildiğini kanıtlayabilmelidir.
- (2) Şekil — açık, sade, diğer konulardan ayırt edilebilir; farklı amaçlar için ayrı rıza.
- (3) Geri çekme — vermek kadar kolay olmalı; ilgili kişi vermeden önce bilgilendirilmelidir.
- (4) Hizmete koşullu — bir hizmeti gereksiz işleme için rızaya bağlamak, rızanın özgürce verilmediğine güçlü göstergedir.

EDPB 05/2020 Rehberi:
- "Özgürce verilmiş" — güç dengesizliği, zarar, paketleme yok.
- "Belirli" — amaç başına ayrıntılı.
- "Bilgilendirilmiş" — veri sorumlusu kimliği, amaç, veri türleri, geri çekme hakkı, otomatik karar verme.
- "Net" — açık olumlu eylem; sessizlik, önceden işaretli kutular veya hareketsizlik rıza değildir.

### 6. Dayanak Değiştirme Kuralı

Genel kural olarak **hukuki dayanaklar yarı yolda değiştirilemez**. Orijinal dayanak başarısız olursa (örn. rıza geri çekildi), veri sorumlusu işlemeye devam etmek için geriye dönük olarak meşru menfaate dayanamaz.

İstisnalar / nüans:
- Yeni, ayrı bir işleme için yeni bir dayanak uygulanabilir.
- Md. 6(4) uyumluluk testi, uyumlu amaçlar için ileri işlemeye izin verebilir.
- Gerekçeyi daima belgeleyin.

### 7. Meşru Menfaat Değerlendirmesi (LIA) Şablonu

Her Madde 6(1)(f) dayanağı için bu şablonu kullanın.

```
LIA — Meşru Menfaat Değerlendirmesi

1. Tanımlama
   1.1 İşleme faaliyeti: ___________________________________
   1.2 Veri sorumlusu (varsa müşterek veri sorumlusu): _____________
   1.3 İB sahibi: ____________________
   1.4 Tarih: ____________________
   1.5 İnceleyenler: VKG ___________________ ; GHM ___________________
   1.6 ROPA referansı: ____________________

2. Amaç Testi — Meşru bir menfaat var mı?
   2.1 Veri sorumlusu veya üçüncü tarafça güdülen menfaati tanımlayın.
   2.2 Hukuka uygun, etik, gerçek ve mevcut (spekülatif değil) mi?
   2.3 Hangi yararlar doğar (veri sorumlusuna, üçüncü taraflara, ilgili kişiye, kamuya)?
   2.4 Amaç başka bir hukuki dayanakla sağlanabilir mi?
       Yanıt: Evet / Hayır. Evetse diğer dayanağı tercih edin.

3. Gereklilik Testi — İşleme gerekli mi?
   3.1 İşleme gerekli mi, yoksa daha az müdahaleci alternatif var mı?
   3.2 Veri alanlarını minimize ettiniz mi?
   3.3 Saklamayı minimize ettiniz mi?
   3.4 Takma adlandırma / şifreleme uygulanıyor mu?

4. Denge Testi — İlgili kişinin hakları üstün geliyor mu?
   4.1 İlgili kişinin makul beklentileri:
       - Mevcut ilişki var mı?
       - Toplama biçimi?
       - İletişim?
   4.2 Verinin niteliği:
       - Özel kategoriler veya cezai veri → uygulanamaz; Md. 9(2) / 10'a dayanın.
       - Özellikle hassas (örn. finansal, konum) — artırılmış inceleme.
   4.3 İlgili kişiye olası etkiler:
       - Maddi etki (finansal, istihdam, fırsat)?
       - Manevi etki (caydırıcı etki, utanç, profilleme damgası)?
   4.4 Savunmasız bireyler (çocuklar, çalışanlar, hastalar, hak sahipleri)?
   4.5 Önlemler:
       - Kolay ve belirgin itiraz hakkı.
       - Veri minimizasyonu.
       - Takma adlandırma / şifreleme.
       - Sıkı erişim kontrolleri.
       - Kısa saklama.
       - Şeffaf aydınlatma metni.

5. Sonuç
   5.1 Meşru menfaat üstün geliyor mu? Evet / Hayır.
   5.2 Evet ise, güvenceleri belgeleyin ve devam edin; Md. 13/14 metniyle iletin.
   5.3 Hayır ise, Md. 6(1)(f) altında işlemeyin; başka dayanak seçin veya devam etmeyin.

6. Onaylar ve Gözden Geçirme
   6.1 İB sahibi onayı: ____________________ Tarih: ________
   6.2 VKG görüşü: ____________________ Tarih: ________
   6.3 GHM onayı: ____________________ Tarih: ________
   6.4 Gözden geçirme tetikleyicisi: amaç, ölçek, veri, tedarikçi, yargı yetkisi değişikliği.
   6.5 Sonraki planlanan gözden geçirme: ____________________
```

### 8. Belgeleme — ROPA Girdisi Başına

Her ROPA girdisi için veri sorumlusu şunları belgeler:

- Amaçlar.
- Hukuki dayanak (Madde 6 paragrafı ve alt paragrafı).
- Uygulanabilirse özel kategori koşulu (Madde 9(2)) veya cezai veri yetkilendirmesi (Madde 10).
- Md. 6(1)(f) kullanılıyorsa LIA referansı.
- Md. 6(1)(a) kullanılıyorsa rıza alma mekanizması.
- Saklama süresi.
- Alıcılar.
- Aktarım mekanizması.

### 9. Sık Karşılaşılan Tuzaklar

- En güvenli hissedildiği için varsayılan olarak "rıza"ya gitmek — rıza özgürce verilmediğinde dayanak çöker, işleme de.
- LIA olmadan "meşru menfaati" kapsayıcı olarak kullanmak.
- "Sözleşmenin" analitiği veya pazarlamayı kapsadığını varsaymak (nadiren "gerekli").
- Rıza geri çekildikten sonra "rıza"dan "meşru menfaate" geçmek.
- Birçok amacı tek bir rızaya paketlemek.
- Rızayı kanıtlayamamak (kayıt, metin sürümü, zaman damgası yok).
- Madde 13/14 metninde anlamlı meşru menfaat tanımı yayımlamamak.

### 10. Operasyonel Kontroller

- Yeni işleme giriş kapısı, hukuki dayanak seçimini zorlar.
- LIA'lar, ROPA girdisine göre indekslenmiş merkezi bir depoda saklanır.
- Rıza kayıtları, değiştirilemez bir günlükte tutulur: zaman damgası, metin sürümü, mekanizma, kapsam, varsa IP/cihaz hash'i ve geri çekme olayları.
- İç Denetim, sistemlerde gözlemlenen gerçek işlemeyle hukuki dayanak iddiasını periyodik olarak doğrular.
