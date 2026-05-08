---
title: "Transparency and Consent — Ten Worked Examples"
title_tr: "Şeffaflık ve Onay — On Uygulamalı Örnek"
section: "03-transparency-consent"
language: ["en", "tr"]
status: "approved"
version: "2.2.0"
last_review: "2026-04-15"
next_review: "2026-10-15"
owner: "Data Protection Officer"
classification: "Internal"
related_articles: ["GDPR Art. 5", "GDPR Art. 6", "GDPR Art. 7", "GDPR Art. 9", "GDPR Art. 13", "GDPR Art. 14", "GDPR Art. 21"]
related_guidelines: ["EDPB Guidelines 5/2020", "EDPB Guidelines 1/2018", "EDPB Guidelines 03/2022"]
tags: ["examples", "scenarios", "transparency", "consent"]
---

## English

### Example 1 — E-commerce Sign-Up + Marketing Opt-In

**Scenario.** A user signs up for an Acme Retail account at acme.eu/signup. The form collects email, password, name, and shipping address. There is an optional "I'd like to receive product recommendations and offers by email" checkbox.

**Lawful bases.**

- Account creation, password storage, address: Article 6(1)(b) contract.
- Marketing email: Article 6(1)(a) consent, only if the box is ticked.

**Layer 1 notice (inline at the form).**

> By creating an account you agree to our [Terms]. We process your name, email, password, and address to create and manage your account and to ship orders (contract). For full details and your rights, read our [Privacy Notice]. **☐ Send me product recommendations and offers by email.** You can withdraw at any time using the link in any email.

**Compliance traps.**

- Pre-checking the marketing box is invalid (EDPB 5/2020).
- Bundling marketing into the terms-of-service checkbox is invalid (Art. 7(2)).
- Conditioning account creation on marketing consent is invalid (Art. 7(4)).

**Consent record stored** with timestamp, notice version, IP, user agent, and the exact text shown.

### Example 2 — Employee Onboarding

**Scenario.** Acme Holdings Europe B.V. hires a new employee.

**Lawful bases — none of which are consent.**

- Article 6(1)(b) contract — for processing necessary to perform the employment contract.
- Article 6(1)(c) legal obligation — for tax, social security, occupational health filings.
- Article 6(1)(f) legitimate interest — for IT security, performance management.
- Article 9(2)(b) employment law condition — for occupational health.

**Why not consent?** Imbalance of power between employer and employee makes consent presumptively invalid (EDPB 5/2020 §21). The employee cannot say no without consequence.

**Layer 1 notice.** In the offer letter, with link to full Employee Privacy Notice on the intranet. Acknowledged in writing on first day.

**Special category data** (occupational health) is processed under Article 9(2)(b) and (h), not consent.

### Example 3 — CCTV at Office Premises

**Scenario.** Acme operates CCTV at perimeter, entrances, reception, loading bay.

**Lawful basis.** Article 6(1)(f) legitimate interest. A balancing test (LIA) is documented dated 2025-11-08.

**Why not consent?** Visitors and employees cannot meaningfully refuse if access to the premises is conditional. Legitimate interest is the operational basis.

**Disclosure.** Layered:

- Layer 1: signage at every entrance (controller, lawful basis, retention, DPO contact, full notice URL).
- Layer 3: full notice at acme.eu/privacy/cctv.

**Proportionality measures.** No audio. No coverage of bathrooms / private offices. Camera angles reviewed annually. 30-day retention. Replay only by Facilities Security with audit log.

### Example 4 — Call-Centre Recording

**Scenario.** Acme Customer Service records inbound calls for quality and training.

**Lawful basis options.**

- Article 6(1)(b) contract: not generally suitable, since recording itself is not necessary for the contract.
- Article 6(1)(f) legitimate interest: viable with LIA, with caller able to opt out.
- Article 6(1)(a) consent: simplest; caller chooses at start of call.

**Verbal Layer 1 notice.**

> "This call may be recorded for quality and training. Recordings are kept for 90 days. Press 1 to continue with recording, press 2 to speak with an agent without recording, or visit acme.eu/privacy for details."

**Compliance trap.** "By continuing on the line, you consent" is not a clear affirmative action. Provide a real choice.

### Example 5 — Mobile App Permissions

**Scenario.** Acme Mobile App asks for location, contacts, camera at various points.

**Treatment.**

- App-store-level permissions (iOS, Android) are the technical gating mechanism — these are not "GDPR consent" by themselves but their UX must align with GDPR.
- Just-in-time disclosures at each prompt explain why and how.
- For Apple ATT: separate prompt for cross-app tracking; treat as consent for advertising purposes.
- The app's privacy notice reflects all SDKs, including any analytics or advertising SDK.

**Layer 1 at location prompt.**

> "Acme would like access to your location to suggest nearby stores. We do not share your location with advertisers. You can revoke this in Settings → Privacy → Location."

**Compliance trap.** Initialising analytics SDK before consent is given is a frequent violation. SDK init must be gated by the consent state.

### Example 6 — Cookie Banner (CMP)

**Scenario.** First visit to acme.eu.

**CMP behaviour.**

- All non-essential cookies blocked by default.
- Banner displayed at first visit, with three equally prominent buttons: **Accept all**, **Reject all**, **Customise**.
- Customise reveals five categories: strictly necessary (always on, greyed), functional, analytics, marketing, social. Each off by default.
- Save choices.
- Persistent footer link "Cookie preferences" allows return.
- Consent recorded with notice version, timestamp, IP truncated, user agent, IDs of vendors.

**TCF v2.2 string** generated and propagated to ad and analytics tags.

**Refresh.** After 12 months, banner re-displayed.

### Example 7 — Email Newsletter Sign-Up

**Scenario.** Standalone newsletter subscription form on acme.eu/newsletter.

**Lawful basis.** Article 6(1)(a) consent.

**Form layout.**

> [Email field]
>
> ☐ Yes, send me the Acme Weekly newsletter — product news, tips, and offers.
>
> [Subscribe button]

**Layer 1 notice (inline).**

> We will use your email to send the Acme Weekly newsletter. We process under your consent. Withdraw any time via the link in every email or at acme.eu/preferences. Full notice: acme.eu/privacy.

**Compliance traps.**

- Pre-ticked checkbox: invalid.
- Bundling with another consent (e.g., partner offers) without separate toggle: invalid.
- Failing to identify the controller in the consent context: invalid (insufficiently informed).

**Withdrawal.** One-click unsubscribe in every email and a preference centre. As easy as giving.

### Example 8 — Health Practice Patient Onboarding (Article 9)

**Scenario.** Dental practice in Amsterdam onboards new patients.

**Special category data.** Health data (treatments, conditions, medications, allergies).

**Lawful bases.**

- Article 9(2)(h) healthcare condition: for processing necessary for medical diagnosis, provision of healthcare or treatment, or management of healthcare systems and services.
- Article 6(1)(b) contract: for the patient-provider contract.

**Why explicit consent (Article 9(2)(a)) is *not* the operational basis.** Healthcare professionals routinely process health data under Article 9(2)(h) under professional secrecy obligations. Consent is unstable for clinical use because withdrawal would impair care.

**Notice.** Patient-friendly notice at first appointment, with controller, DPO, purposes, recipients (lab, insurer where applicable), retention (medical record retention typically 15–20 years per Member State law), rights, and complaint mechanism.

**Where consent IS used.** For ancillary purposes outside the clinical relationship — e.g., a patient newsletter with practice news (Article 6(1)(a)).

### Example 9 — HR Reference Checks (Article 14 Trigger)

**Scenario.** During recruitment, Acme requests references from a candidate's prior employer. The reference contains personal data about the candidate that Acme did not collect from the candidate directly.

**Article 14 applies.** Information must be provided to the candidate within one month, or at the time of first communication, or at first disclosure to a third party.

**Lawful basis.** Article 6(1)(f) legitimate interest of Acme to verify candidate suitability. LIA documented.

**Notice content (Layer 1, included in candidate privacy notice given at application).**

> If you proceed past the second interview stage, we may contact references you have nominated. We will record the reference and will not share it externally. The reference is retained until you start employment + 1 year, or 6 months from end of recruitment if you do not start. You can request access to the reference at any time. We do not contact references without your prior approval.

**Compliance traps.**

- Contacting references without telling the candidate: violates Article 14 timing.
- Asking references for special-category data: typically requires Article 9(2) condition.
- Retaining references indefinitely: fails retention principle.

### Example 10 — Vendor Employee Data Sharing

**Scenario.** Acme engages a marketing agency. To execute the contract, Acme shares the names, emails, and phone numbers of three Acme employees with the agency. The agency in turn provides Acme with the names and emails of its account team.

**Two flows.**

**Flow 1: Acme → Agency.**

- Acme is controller for its own employees' data.
- Sharing with agency for the limited purpose of running the engagement.
- Lawful basis: Article 6(1)(f) legitimate interest of Acme to manage the engagement.
- Article 13 information already given via Employee Privacy Notice (recipient categories include "service providers").

**Flow 2: Agency → Acme.**

- Agency is controller for its own employees' data.
- Acme receives the data as a controller (not processor) for the purpose of contract management.
- Article 14 applies: Acme must inform agency employees how Acme processes their data within one month or at first communication.
- Acme's vendor-employee notice covers this.

**Compliance traps.**

- Treating vendor employees as "no GDPR scope" because they are not data subjects of the contract: wrong; they are data subjects for their personal data.
- No retention period set for vendor-employee contact data: should be tied to the contract duration plus a reasonable limitation period.

---

## Türkçe

### Örnek 1 — E-ticaret Kayıt + Pazarlama Onayı

**Senaryo.** Bir kullanıcı acme.eu/signup adresinde Acme Retail hesabı için kayıt olur. Form e-posta, şifre, isim ve sevkiyat adresini toplar. İsteğe bağlı bir "E-posta ile ürün önerileri ve teklifler almak istiyorum" kutusu vardır.

**Hukuki sebepler.**

- Hesap oluşturma, şifre saklama, adres: Madde 6(1)(b) sözleşme.
- Pazarlama e-postası: Yalnızca kutu işaretlenirse Madde 6(1)(a) onay.

**Katman 1 bildirim (formda satır içi).**

> Hesap oluşturarak [Şartlar]ı kabul edersiniz. Adınızı, e-postanızı, şifrenizi ve adresinizi hesabınızı oluşturmak ve yönetmek ve siparişleri sevk etmek için işleriz (sözleşme). Tam ayrıntılar ve haklarınız için [Gizlilik Bildirimi]ni okuyun. **☐ E-posta ile ürün önerileri ve teklifler gönderin.** Her e-postadaki bağlantıyı kullanarak istediğiniz zaman geri çekebilirsiniz.

**Uyumluluk tuzakları.**

- Pazarlama kutusunu önceden işaretlemek geçersizdir (EDPB 5/2020).
- Pazarlamayı hizmet şartları kutusuna paketlemek geçersizdir (Madde 7(2)).
- Hesap oluşturmayı pazarlama onayına koşullamak geçersizdir (Madde 7(4)).

**Onay kaydı**: zaman damgası, bildirim sürümü, IP, kullanıcı aracısı ve gösterilen tam metin ile saklanır.

### Örnek 2 — Çalışan İşe Alımı

**Senaryo.** Acme Holdings Europe B.V. yeni bir çalışan işe alır.

**Hukuki sebepler — hiçbiri onay değildir.**

- Madde 6(1)(b) sözleşme — iş sözleşmesinin ifası için gerekli işleme.
- Madde 6(1)(c) yasal yükümlülük — vergi, sosyal güvenlik, iş sağlığı bildirimleri için.
- Madde 6(1)(f) meşru menfaat — BT güvenliği, performans yönetimi için.
- Madde 9(2)(b) iş hukuku koşulu — iş sağlığı için.

**Neden onay değil?** İşveren ve çalışan arasındaki güç dengesizliği onayı varsayımsal olarak geçersiz kılar (EDPB 5/2020 §21). Çalışan sonuç olmadan hayır diyemez.

**Katman 1 bildirim.** Teklif mektubunda, intranetteki tam Çalışan Gizlilik Bildirimine bağlantı ile. İlk gün yazılı olarak kabul edilmiştir.

**Özel kategori veri** (iş sağlığı), onay değil Madde 9(2)(b) ve (h) altında işlenir.

### Örnek 3 — Ofis Tesislerinde CCTV

**Senaryo.** Acme çevrede, girişlerde, resepsiyonda, yükleme alanında CCTV işletir.

**Hukuki sebep.** Madde 6(1)(f) meşru menfaat. 2025-11-08 tarihli bir dengeleme testi (LIA) belgelenmiştir.

**Neden onay değil?** Tesise erişim koşulluysa ziyaretçiler ve çalışanlar anlamlı şekilde reddedemez. Meşru menfaat operasyonel sebeptir.

**İfşa.** Katmanlı:

- Katman 1: her girişte tabela (veri sorumlusu, hukuki sebep, saklama, DPO iletişim, tam bildirim URL'si).
- Katman 3: acme.eu/privacy/cctv adresinde tam bildirim.

**Orantılılık önlemleri.** Ses yok. Tuvaletler / özel ofisler kapsanmıyor. Kamera açıları yıllık inceleniyor. 30 gün saklama. Yalnızca Tesis Güvenliği denetim logu ile tekrar oynatabilir.

### Örnek 4 — Çağrı Merkezi Kaydı

**Senaryo.** Acme Müşteri Hizmetleri kalite ve eğitim için gelen çağrıları kaydeder.

**Hukuki sebep seçenekleri.**

- Madde 6(1)(b) sözleşme: genellikle uygun değil, çünkü kayıt sözleşme için gerekli değildir.
- Madde 6(1)(f) meşru menfaat: LIA ile uygulanabilir, arayanın opt-out yapabilmesiyle.
- Madde 6(1)(a) onay: en basiti; arayan çağrı başında seçer.

**Sözlü Katman 1 bildirim.**

> "Bu çağrı kalite ve eğitim için kaydedilebilir. Kayıtlar 90 gün saklanır. Kayıtla devam etmek için 1'e basın, kayıtsız bir temsilciyle görüşmek için 2'ye basın veya ayrıntılar için acme.eu/privacy adresini ziyaret edin."

**Uyumluluk tuzağı.** "Hatta kalmaya devam ederek onay verirsiniz" açık onaylayıcı bir eylem değildir. Gerçek bir seçim sunun.

### Örnek 5 — Mobil Uygulama İzinleri

**Senaryo.** Acme Mobil Uygulama çeşitli noktalarda konum, kişiler, kamera ister.

**Tedavi.**

- Uygulama mağazası seviyesi izinler (iOS, Android) teknik kapı mekanizmasıdır — bunlar başlı başına "GDPR onayı" değildir ancak UX'leri GDPR ile uyumlu olmalıdır.
- Her istem için anlık ifşalar nedenini ve nasılını açıklar.
- Apple ATT için: çapraz uygulama izleme için ayrı istem; reklam amaçları için onay olarak ele alınır.
- Uygulamanın gizlilik bildirimi tüm SDK'ları yansıtır, herhangi bir analitik veya reklam SDK'sı dahil.

**Konum isteminde Katman 1.**

> "Acme yakın mağazaları önermek için konumunuza erişmek istiyor. Konumunuzu reklamcılarla paylaşmıyoruz. Bunu Ayarlar → Gizlilik → Konum'dan iptal edebilirsiniz."

**Uyumluluk tuzağı.** Onay verilmeden önce analitik SDK'yı başlatmak sık ihlaldir. SDK başlatma onay durumuyla kapatılmalıdır.

### Örnek 6 — Çerez Banner'ı (CMP)

**Senaryo.** acme.eu'ya ilk ziyaret.

**CMP davranışı.**

- Tüm zorunlu olmayan çerezler varsayılan olarak engellenir.
- İlk ziyarette banner gösterilir, üç eşit derecede belirgin düğme: **Tümünü Kabul Et**, **Tümünü Reddet**, **Özelleştir**.
- Özelleştir beş kategoriyi ortaya çıkarır: kesinlikle gerekli (her zaman açık, gri), işlevsel, analitik, pazarlama, sosyal. Her biri varsayılan kapalı.
- Seçimleri kaydedin.
- Kalıcı alt bilgi bağlantısı "Çerez tercihleri" geri dönüşe izin verir.
- Onay, bildirim sürümü, zaman damgası, IP kısaltılmış, kullanıcı aracısı, tedarikçi kimlikleri ile kaydedilir.

**TCF v2.2 string'i** üretildi ve reklam ve analitik etiketlerine yayıldı.

**Yenileme.** 12 ay sonra banner yeniden gösterilir.

### Örnek 7 — E-posta Bülten Kaydı

**Senaryo.** acme.eu/newsletter adresinde bağımsız bülten abonelik formu.

**Hukuki sebep.** Madde 6(1)(a) onay.

**Form düzeni.**

> [E-posta alanı]
>
> ☐ Evet, bana Acme Haftalık bültenini gönderin — ürün haberleri, ipuçları ve teklifler.
>
> [Abone Ol düğmesi]

**Katman 1 bildirim (satır içi).**

> Acme Haftalık bültenini göndermek için e-postanızı kullanacağız. Onayınız altında işliyoruz. Her e-postadaki bağlantıyla veya acme.eu/preferences'ta istediğiniz zaman geri çekin. Tam bildirim: acme.eu/privacy.

**Uyumluluk tuzakları.**

- Önceden işaretli kutu: geçersiz.
- Ayrı geçiş olmadan başka bir onayla paketleme (örn. ortak teklifler): geçersiz.
- Onay bağlamında veri sorumlusunu tanımlamamak: geçersiz (yetersiz bilgilendirilmiş).

**Geri çekme.** Her e-postada tek tıklamayla abonelikten çıkma ve bir tercih merkezi. Vermek kadar kolay.

### Örnek 8 — Sağlık Pratiği Hasta Kabulü (Madde 9)

**Senaryo.** Amsterdam'da diş kliniği yeni hastaları kabul eder.

**Özel kategori veri.** Sağlık verisi (tedaviler, durumlar, ilaçlar, alerjiler).

**Hukuki sebepler.**

- Madde 9(2)(h) sağlık koşulu: tıbbi tanı, sağlık hizmeti veya tedavi sağlama veya sağlık sistemleri ve hizmetleri yönetimi için gerekli işleme.
- Madde 6(1)(b) sözleşme: hasta-sağlayıcı sözleşmesi için.

**Neden açık onay (Madde 9(2)(a)) operasyonel sebep *değildir*.** Sağlık profesyonelleri, meslek sırrı yükümlülükleri altında Madde 9(2)(h) altında sağlık verisini rutin olarak işler. Onay klinik kullanım için kararsızdır çünkü geri çekme bakımı bozar.

**Bildirim.** İlk randevuda hasta dostu bildirim, veri sorumlusu, DPO, amaçlar, alıcılar (laboratuvar, uygulanabilirse sigorta), saklama (tıbbi kayıt saklama genellikle Üye Devlet hukukuna göre 15–20 yıl), haklar ve şikayet mekanizması ile.

**Onayın KULLANILDIĞI yer.** Klinik ilişki dışındaki yardımcı amaçlar için — örneğin, klinik haberleriyle hasta bülteni (Madde 6(1)(a)).

### Örnek 9 — İK Referans Kontrolü (Madde 14 Tetikleyici)

**Senaryo.** İşe alım sırasında Acme, adayın önceki işvereninden referans ister. Referans, Acme'nin doğrudan adaydan toplamadığı kişisel veriyi içerir.

**Madde 14 uygulanır.** Bilgi adaya bir ay içinde, ilk iletişim sırasında veya üçüncü tarafa ilk ifşada verilmelidir.

**Hukuki sebep.** Adayın uygunluğunu doğrulamak için Acme'nin Madde 6(1)(f) meşru menfaati. LIA belgelenmiştir.

**Bildirim içeriği (Katman 1, başvuruda verilen aday gizlilik bildiriminde).**

> İkinci görüşme aşamasını geçerseniz, gösterdiğiniz referansları arayabiliriz. Referansı kaydederiz ve harici olarak paylaşmayız. Referans, istihdama başlama + 1 yıl veya başlamazsanız işe alım sonu + 6 ay saklanır. Referansa istediğiniz zaman erişim talep edebilirsiniz. Önceden onayınız olmadan referansları aramayız.

**Uyumluluk tuzakları.**

- Adaya söylemeden referans aramak: Madde 14 zamanlamasını ihlal eder.
- Referanslardan özel kategori veri istemek: genellikle Madde 9(2) koşulu gerektirir.
- Referansları süresiz saklamak: saklama ilkesinde başarısız.

### Örnek 10 — Tedarikçi Çalışan Verisi Paylaşımı

**Senaryo.** Acme bir pazarlama ajansıyla anlaşır. Sözleşmeyi yürütmek için Acme, üç Acme çalışanının isimlerini, e-postalarını ve telefon numaralarını ajansla paylaşır. Ajans karşılığında Acme'ye hesap ekibinin isimlerini ve e-postalarını sağlar.

**İki akış.**

**Akış 1: Acme → Ajans.**

- Acme kendi çalışanlarının verisi için veri sorumlusudur.
- İlişkiyi yürütme sınırlı amacı için ajansla paylaşım.
- Hukuki sebep: Acme'nin ilişkiyi yönetme Madde 6(1)(f) meşru menfaati.
- Madde 13 bilgisi Çalışan Gizlilik Bildirimi aracılığıyla zaten verilmiştir (alıcı kategorileri "hizmet sağlayıcılar"ı içerir).

**Akış 2: Ajans → Acme.**

- Ajans kendi çalışanlarının verisi için veri sorumlusudur.
- Acme veriyi sözleşme yönetimi amacıyla veri sorumlusu (veri işleyen değil) olarak alır.
- Madde 14 uygulanır: Acme, ajans çalışanlarına Acme'nin verilerini nasıl işlediğini bir ay içinde veya ilk iletişimde bildirmelidir.
- Acme'nin tedarikçi çalışan bildirimi bunu kapsar.

**Uyumluluk tuzakları.**

- Tedarikçi çalışanlarını sözleşmenin ilgili kişileri olmadıkları için "GDPR kapsamı yok" olarak ele almak: yanlış; kişisel verileri için ilgili kişilerdir.
- Tedarikçi çalışan iletişim verisi için saklama süresi belirlenmemiş: sözleşme süresi artı makul bir sınırlama süresine bağlanmalıdır.
