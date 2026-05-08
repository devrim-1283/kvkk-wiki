---
title:
  en: "Cookies, Tracking, and Online Identifiers"
  tr: "Çerezler, İzleme ve Çevrimiçi Tanımlayıcılar"
section: "10-special-topics"
document_id: "ST-COOK-001"
owner: "DPO Office / Web Engineering"
classification: "Internal"
version: "1.0"
last_review: "2026-05-08"
next_review: "2027-05-08"
language: ["en", "tr"]
references:
  - "ePrivacy Directive 2002/58/EC, Article 5(3) (as amended by 2009/136/EC)"
  - "GDPR Art. 6, 7 — Lawful basis and consent"
  - "GDPR Recital 30 — Online identifiers as personal data"
  - "EDPB Guidelines 5/2020 on consent under GDPR"
  - "EDPB Guidelines 03/2022 on deceptive design patterns in social media platform interfaces (deceptive/dark patterns)"
  - "EDPB Statement 1/2025 on consent or pay (Pay or OK)"
  - "CNIL Guidelines and Recommendations on cookies and other tracers (2020, updated 2024)"
  - "ICO Guidance on the use of cookies and similar technologies"
  - "Planet49 (CJEU C-673/17) — pre-ticked boxes invalid"
  - "TC IAB / TCF v2.2 (2023)"
  - "Schrems II (CJEU C-311/18) — third-country transfers"
---

## English

### 1. Legal architecture

The use of cookies and similar technologies is governed by Article 5(3) of the ePrivacy Directive 2002/58/EC (as amended), implemented in national law (e.g. PECR in the UK, Telekommunikation-Telemedien-Datenschutz-Gesetz in Germany, French CPCE Article 82, Turkish Electronic Communications Law/CMK secondary legislation). The ePrivacy rule applies regardless of whether the data accessed by the cookie is personal data.

When the data accessed or stored by a cookie is personal data, the GDPR also applies. Recital 30 of the GDPR confirms that online identifiers (cookies, IP addresses, device IDs, advertising IDs) may be personal data when combined with other information. EDPB 5/2020 confirms that for non-strictly-necessary cookies, the only valid basis under ePrivacy is the user's prior consent, and that this consent must meet the GDPR Article 4(11) and Article 7 standards.

### 2. The two ePrivacy categories

Article 5(3) creates two regimes:

| Category | ePrivacy basis | Notes |
|----------|---------------|-------|
| **Strictly necessary** for the provision of a service explicitly requested by the user | Exempt from consent | Narrow: load-balancing, session management to keep a user logged in, basket persistence, accessibility preferences, security cookies that detect repeated authentication failures |
| **All others** | Prior consent | Includes analytics, advertising, retargeting, A/B testing, social-media plugins, content personalisation, fraud prevention beyond strictly necessary, third-party widgets that load before consent |

EDPB 5/2020 §62 emphasises that "strictly necessary" is not a marketing label but a legal test: necessary for the service the user requested, not for the controller's commercial purposes.

### 3. Consent standard

Consent under GDPR must be:

- **Freely given**: no detriment to refusal; no cookie wall (see below); no consent-or-pay structures absent the conditions set in EDPB Statement 1/2025.
- **Specific**: per purpose (analytics, marketing, personalisation are separate purposes).
- **Informed**: clear identification of the controller, the purpose, the categories of data collected, retention, and recipients including third countries.
- **Unambiguous indication by a clear affirmative act**: a click on "Accept all" is fine; pre-ticked boxes are invalid (Planet49 C-673/17); continuing to scroll is not consent.
- **Withdrawable at any time** with no detriment, as easily as it was given.

EDPB 5/2020 §80 reaffirms that there must be a "Reject all" option of equal prominence to "Accept all". If accept is one click and reject takes three clicks through nested settings, the consent is invalid.

### 4. Banned dark patterns (EDPB 03/2022)

EDPB Guidelines 03/2022 list deceptive design patterns. The following are prohibited:

| Pattern | Description |
|---------|------------|
| Asymmetric prominence | Accept button visually dominant; reject hidden or styled to look secondary |
| Confusing wording | "We respect your privacy" framing without honest reject option |
| Manipulative phrasing | "Stay safe online by accepting cookies" |
| Forced action | Cookie wall that blocks the entire content unless cookies accepted |
| Bait and switch | Reject button leads to a granular settings page that re-presents accept |
| Continuity trap | "Save preferences" that defaults to accept when user only adjusted some |
| Pre-ticked boxes | Invalid per Planet49 |
| Conflated purposes | One toggle for analytics + advertising + sharing |
| Stacked categories | "Performance and personalisation" hiding distinct purposes |
| Repeated nudge | Re-prompting users who rejected, to wear them down |
| Visually hidden controls | Light-grey-on-white reject text |

The CMP must be tested for these patterns at every release. The DPO has the standing right to require changes.

### 5. Cookie wall illegality

A cookie wall — where access to a service is conditional on accepting non-strictly-necessary cookies — invalidates consent in most cases. EDPB 5/2020 §40 states: "in order for consent to be freely given, access to services and functionalities must not be made conditional on the consent of a user to the storing of information, or gaining of access to information already stored, in the terminal equipment of a user." Member State enforcement (CNIL, AEPD, Garante) consistently finds cookie walls unlawful.

### 6. Consent-or-Pay (Pay or OK)

EDPB Statement 1/2025 addresses "consent or pay" models. Where freely given consent is to be relied upon, the alternative offered must be a genuine, equivalent service for a reasonable price, and the existence of the paid alternative must not by itself negate freedom of consent. The statement is restrictive: most consent-or-pay implementations on news sites and social platforms have been challenged. Implement only with DPO and Legal sign-off, with documented evidence that the conditions are met.

### 7. CMP architecture

A compliant Consent Management Platform (CMP) must:

1. **Block scripts before consent**: no third-party tag, pixel, or analytics script may fire before consent is captured. The CMP runs first; tag managers (GTM) load tags conditionally on the CMP's consent state.
2. **Layered notice**: short banner with the purposes, controller, and the prominent equal-weight Accept and Reject buttons. A second layer with granular per-purpose toggles and per-vendor visibility.
3. **Per-purpose toggles**: at minimum: strictly necessary (always on, not toggleable); functional/preferences; analytics/measurement; marketing/advertising; personalisation/content profiling.
4. **Vendor list**: each third-party vendor named with link to their privacy notice; for IAB TCF v2.2, the global vendor list referenced.
5. **Consent record**: timestamped, stored, retrievable for evidence (Article 7(1) burden of proof).
6. **Withdrawal**: a persistent, clearly-labelled link on every page (commonly "Cookie preferences" in the footer).
7. **Refresh / re-prompt**: not more often than every 6 months for users who rejected, and only when there is a material change in the cookie set.
8. **Geographical handling**: detect user region; apply ePrivacy + GDPR rules in the EEA, Switzerland, UK; apply local rules elsewhere; never rely on geo-detection to weaken EU users' protections.

### 8. IAB TCF v2.2

IAB Europe's Transparency and Consent Framework (TCF) v2.2 (2023) is a widely used technical standard, but its compliance status is contested. The Belgian APD found in 2022 that the TCF in its earlier form did not comply with GDPR; subsequent versions have made improvements. Use of TCF must be paired with substantive compliance assessment by the DPO, not as a substitute. The IAB Europe Consent String alone does not by itself prove valid consent.

### 9. Strictly necessary cookies — practical examples

| Use case | Strictly necessary? |
|----------|---------------------|
| Session ID for logged-in user | Yes |
| Basket contents on e-commerce | Yes |
| Form-state persistence during checkout | Yes |
| CSRF token | Yes |
| Load-balancer / sticky session | Yes |
| Cookie-consent state itself | Yes |
| Language preference if user actively chose | Yes |
| First-party analytics with no profiling, IP truncated, server-side | Likely no — unless user-requested service feature requires it |
| Bot detection / fraud prevention | Strictly necessary only to the extent strictly necessary; document narrowly |
| A/B testing | No |
| Heatmaps / session recording | No |
| Personalisation based on prior behaviour | No |

### 10. Third-country pixels and Schrems II implications

Many tracking technologies (Google Analytics, Meta Pixel, TikTok Pixel, Microsoft Clarity, LinkedIn Insight Tag) involve transfers of personal data to the US. After Schrems II (CJEU C-311/18, July 2020) and the EU-US Data Privacy Framework (2023), transfers are possible only if:

- The recipient is on the DPF list (verify on dataprivacyframework.gov);
- Or SCCs are in place plus a Transfer Impact Assessment that addresses US surveillance laws (FISA 702, Executive Order 12333);
- Or other Article 46 mechanism;
- And the controller has assessed risk and applied supplementary measures where necessary.

CNIL, Datenschutzbehörde Austria, Garante, and AEPD have all taken enforcement against unconfigured Google Analytics (DSB Austria decision 2022, CNIL 2022). Practical guidance:

- Server-side analytics with IP truncation and no user IDs may be acceptable.
- Default Google Analytics (now GA4) without configuration is high risk.
- IAB TCF "consent" does not on its own legitimise the transfer; transfer mechanism is a separate analysis.
- Document the TIA in section `07-international-transfers`.

### 11. Mobile apps and SDKs

The same rules apply on mobile. Each SDK is a vendor; each has a purpose; consent is required for non-strictly-necessary SDKs. Apple's App Tracking Transparency (ATT) and Google's Privacy Sandbox are platform-level controls; they do not replace ePrivacy/GDPR consent.

App store privacy labels must accurately reflect actual data flows. Discrepancies have been the basis for enforcement.

### 12. Connected TV, IoT, and other surfaces

ePrivacy applies to all "terminal equipment". Smart TVs, set-top boxes, voice assistants, connected cars, and IoT devices are within scope. Consent UX must be adapted to the modality (no dark patterns by being on a TV remote).

### 13. Children

Where the audience includes children (a service directed to children, or a general service with significant child use), special care is needed:

- Article 8 GDPR rules on consent and parental authorisation for information society services to children.
- Member State age thresholds vary (13–16); the controller applies the highest applicable.
- UK ICO Age Appropriate Design Code provides additional standards.
- Profiling of children is to be avoided wherever possible (Article 22 + Recital 38).

### 14. Documentation and audit

Maintain:

- **Cookie register**: every cookie / tracker in use, name, purpose, category, retention, vendor, third-country flag.
- **CMP configuration record**: versioned, with date of change and reason.
- **Consent log samples**: anonymised statistics on accept/reject rates, per region.
- **Vendor due diligence**: DPA, security questionnaire, transfer mechanism, sub-processor list per vendor.
- **Re-audit cadence**: quarterly cookie audit (automated scan + manual review of top pages).

### 15. Enforcement landscape (selected)

| Authority | Notable decisions |
|-----------|------------------|
| CNIL | Repeated fines (Google, Amazon, Meta, TikTok) for accept/reject asymmetry |
| Garante (IT) | Google Analytics decision 2022; cookie wall sanctions |
| AEPD (ES) | Cookie audit guidance and fines |
| Belgian APD | TCF decision and remediation order |
| ICO (UK) | Cookie compliance audits of major UK websites |
| KVKK | Increasing scrutiny of cookies under KVKK Article 5 |

### 16. Operational checklist (developer-facing)

- [ ] No third-party scripts in the page <head> before CMP loads.
- [ ] CMP loads from same origin (no race condition).
- [ ] Reject button at least visually equal to Accept.
- [ ] No pre-ticked toggles in the layered settings.
- [ ] Cookie register matches what the page actually sets (verified by automated audit).
- [ ] Consent state propagates to GTM, gtag, fbq, etc.
- [ ] Server-side fallbacks do not collect data the user rejected.
- [ ] Withdrawal link present in footer of every page.
- [ ] Privacy notice references cookie-specific notice with the cookie register.

### 17. KPIs

| KPI | Target |
|-----|--------|
| Reject-rate parity audits | Quarterly |
| Time-to-fix for dark-pattern findings | < 30 days |
| Cookie register vs. actual cookie scan delta | 0 unauthorised cookies |
| Re-prompt frequency for rejected users | <= every 6 months |
| Consent record retention | 24 months minimum, audit-aligned |

---

## Türkçe

### 1. Hukuki mimari

Çerezler ve benzeri teknolojilerin kullanımı, ulusal hukukta uygulanan ePrivacy Direktifi 2002/58/EC'nin (değiştirilmiş haliyle) Madde 5(3)'ü tarafından yönetilir (örn. UK'de PECR, Almanya'da TTDSG, Fransa CPCE Madde 82, Türk Elektronik Haberleşme Kanunu/CMK ikincil mevzuatı). ePrivacy kuralı, çerez tarafından erişilen verinin kişisel veri olup olmadığına bakılmaksızın uygulanır.

Çerez tarafından erişilen veya saklanan veri kişisel veri olduğunda, GDPR de uygulanır. GDPR Resital 30, çevrimiçi tanımlayıcıların (çerezler, IP adresleri, cihaz kimlikleri, reklam kimlikleri) diğer bilgilerle birleştirildiğinde kişisel veri olabileceğini teyit eder.

### 2. İki ePrivacy kategorisi

Madde 5(3) iki rejim oluşturur:

| Kategori | ePrivacy temeli | Notlar |
|----------|----------------|--------|
| **Kullanıcı tarafından açıkça talep edilen bir hizmetin sağlanması için kesinlikle gerekli** | Rızadan muaf | Dar: yük dengeleme, oturum yönetimi, sepet kalıcılığı, erişilebilirlik tercihleri, güvenlik çerezleri |
| **Diğer tümü** | Önceki rıza | Analitik, reklam, yeniden hedefleme, A/B testi, sosyal medya eklentileri, içerik kişiselleştirme, kesinlikle gerekli ötesinde dolandırıcılık önleme |

### 3. Rıza standardı

GDPR altında rıza:

- **Özgürce verilmiş**: reddetmenin zararı yok; çerez duvarı yok.
- **Belirli**: amaca göre.
- **Bilgilendirilmiş**: veri sorumlusu, amaç, veri kategorileri, saklama, üçüncü ülkeler dahil alıcılar açıkça tanımlanmış.
- **Açık olumlu eylemle açık şekilde belirtilen**: "Tümünü kabul et" tıklaması uygundur; önceden işaretli kutular geçersizdir (Planet49 C-673/17).
- **Verildiği gibi kolay geri çekilebilir**.

EDPB 5/2020 §80, "Tümünü reddet" seçeneğinin "Tümünü kabul et" ile eşit belirginlikte olması gerektiğini yeniden teyit eder.

### 4. Yasaklanmış karanlık örüntüler (EDPB 03/2022)

| Örüntü | Açıklama |
|--------|----------|
| Asimetrik belirginlik | Kabul düğmesi görsel olarak baskın; reddet gizli |
| Karıştırıcı ifade | "Mahremiyetinize saygı duyuyoruz" çerçeveleme |
| Manipülatif ifade | "Çerezleri kabul ederek çevrimiçi güvende kalın" |
| Zorlayıcı eylem | Kabul edilmedikçe içeriği engelleyen çerez duvarı |
| Yem ve değiştirme | Reddet düğmesi ayrıntılı bir ayar sayfasına götürür |
| Süreklilik tuzağı | Yalnızca bazılarını ayarladığında kabul varsayılan olan "Tercihleri kaydet" |
| Önceden işaretli kutular | Planet49'a göre geçersiz |
| Birleştirilmiş amaçlar | Analitik + reklam + paylaşım için tek geçiş |
| İstiflenmiş kategoriler | Farklı amaçları gizleyen "Performans ve kişiselleştirme" |
| Tekrarlanan dürtme | Reddedenleri yıpratmak için yeniden istek |
| Görsel olarak gizlenmiş kontroller | Beyaz üzerinde açık gri reddet metni |

### 5. Çerez duvarı yasaklılığı

Bir çerez duvarı — kesinlikle gerekli olmayan çerezleri kabul etmeye bağlı bir hizmete erişim — çoğu durumda rızayı geçersiz kılar.

### 6. Rıza-veya-Öde (Pay or OK)

EDPB Bildirimi 1/2025 "rıza veya öde" modellerini ele alır. Özgürce verilmiş rızaya dayanılacaksa, sunulan alternatif makul fiyatla gerçek, eşdeğer bir hizmet olmalıdır.

### 7. CMP mimarisi

Uyumlu bir Rıza Yönetimi Platformu (CMP):

1. **Rıza öncesi komut dosyalarını engelle**: rıza yakalanmadan önce hiçbir üçüncü taraf etiket, piksel veya analitik komut dosyası çalışmamalıdır.
2. **Katmanlı bildirim**: amaçlar, veri sorumlusu ve belirgin eşit ağırlıklı Kabul ve Reddet düğmeleri içeren kısa pankart.
3. **Amaç başına geçişler**: en azından: kesinlikle gerekli (her zaman açık); işlevsel/tercihler; analitik/ölçüm; pazarlama/reklam; kişiselleştirme.
4. **Tedarikçi listesi**: her üçüncü taraf tedarikçi gizlilik bildirimine bağlantı ile.
5. **Rıza kaydı**: zaman damgalı, saklanmış, kanıt için alınabilir.
6. **Geri çekme**: her sayfada kalıcı, açıkça etiketlenmiş bağlantı.
7. **Yenileme / yeniden istek**: reddedenler için 6 aydan daha sık değil.
8. **Coğrafi yönetim**: AEA, İsviçre, Birleşik Krallık'ta ePrivacy + GDPR kuralları uygulanır.

### 8. IAB TCF v2.2

IAB Avrupa'nın Şeffaflık ve Rıza Çerçevesi (TCF) v2.2 (2023) yaygın olarak kullanılan bir teknik standarttır, ancak uyumluluk durumu tartışmalıdır. TCF kullanımı, VKK tarafından esaslı uyumluluk değerlendirmesiyle eşleştirilmelidir.

### 9. Kesinlikle gerekli çerezler — pratik örnekler

| Kullanım durumu | Kesinlikle gerekli mi? |
|-----------------|------------------------|
| Oturum açmış kullanıcı için oturum kimliği | Evet |
| E-ticaret sepetinde sepet içeriği | Evet |
| Ödeme sırasında form durumu kalıcılığı | Evet |
| CSRF tokeni | Evet |
| Yük dengeleyici / yapışkan oturum | Evet |
| Çerez rıza durumunun kendisi | Evet |
| Kullanıcı aktif olarak seçtiyse dil tercihi | Evet |
| IP kısaltılmış, sunucu tarafı, profillemesiz birinci taraf analitik | Muhtemelen hayır |
| Bot tespiti / dolandırıcılık önleme | Yalnızca kesinlikle gerekli olduğu ölçüde |
| A/B testi | Hayır |
| Isı haritaları / oturum kayıt | Hayır |
| Önceki davranışa dayalı kişiselleştirme | Hayır |

### 10. Üçüncü ülke pikselleri ve Schrems II etkileri

Birçok izleme teknolojisi (Google Analytics, Meta Pixel, TikTok Pixel, Microsoft Clarity, LinkedIn Insight Tag) kişisel verinin ABD'ye aktarımını içerir. Schrems II (CJEU C-311/18) ve AB-ABD Veri Mahremiyeti Çerçevesi'nden (2023) sonra, aktarımlar yalnızca:

- Alıcı DPF listesindeyse (dataprivacyframework.gov'da doğrulayın);
- Ya da SCC'ler ve ABD gözetleme yasalarını ele alan bir Aktarım Etki Değerlendirmesi yerinde;
- Ya da diğer Madde 46 mekanizması;
- Ve veri sorumlusu riski değerlendirip gerekli durumlarda ek önlemler uyguladığında mümkündür.

CNIL, DSB Avusturya, Garante ve AEPD'nin tümü yapılandırılmamış Google Analytics'e karşı yaptırım uyguladı.

### 11. Mobil uygulamalar ve SDK'lar

Aynı kurallar mobilde uygulanır. Her SDK bir tedarikçidir; her birinin bir amacı vardır; kesinlikle gerekli olmayan SDK'lar için rıza gerekir.

### 12. Bağlı TV, IoT ve diğer yüzeyler

ePrivacy tüm "terminal ekipmanı" için geçerlidir.

### 13. Çocuklar

İzleyici çocukları içerdiğinde, özel özen gereklidir. Madde 8 GDPR, çocuklara yönelik bilgi toplumu hizmetleri için rıza ve ebeveyn yetkilendirmesi kurallarını belirler.

### 14. Belgeleme ve denetim

Şunları sürdür:

- **Çerez kaydı**: kullanılan her çerez/izleyici, ad, amaç, kategori, saklama, tedarikçi, üçüncü ülke bayrağı.
- **CMP yapılandırma kaydı**: sürümlü, değişiklik tarihi ve nedeniyle.
- **Rıza günlüğü örnekleri**: bölge başına anonim kabul/reddetme oranı istatistikleri.
- **Tedarikçi durum tespiti**: tedarikçi başına VİS, güvenlik anketi, aktarım mekanizması, alt işleyen listesi.
- **Yeniden denetim ritmi**: üç aylık çerez denetimi.

### 15. Yaptırım manzarası (seçilmiş)

| Makam | Önemli kararlar |
|-------|----------------|
| CNIL | Kabul/ret asimetrisi için tekrarlanan cezalar (Google, Amazon, Meta, TikTok) |
| Garante (IT) | Google Analytics kararı 2022; çerez duvarı yaptırımları |
| AEPD (ES) | Çerez denetim rehberliği ve cezalar |
| Belçika APD | TCF kararı ve düzeltme emri |
| ICO (UK) | Büyük UK web sitelerinin çerez uyumluluk denetimleri |
| KVKK | KVKK Madde 5 altında çerezlerin artan denetimi |

### 16. Operasyonel kontrol listesi (geliştirici odaklı)

- [ ] CMP yüklenmeden önce sayfa <head>'inde üçüncü taraf komut dosyaları yok.
- [ ] CMP aynı kaynaktan yüklenir (yarış durumu yok).
- [ ] Reddet düğmesi en azından görsel olarak Kabul ile eşit.
- [ ] Katmanlı ayarlarda önceden işaretli geçiş yok.
- [ ] Çerez kaydı sayfanın gerçekten ayarladığıyla eşleşir.
- [ ] Rıza durumu GTM, gtag, fbq vb. ile yayılır.
- [ ] Sunucu tarafı yedekler kullanıcının reddettiği veriyi toplamaz.
- [ ] Geri çekme bağlantısı her sayfanın altbilgisinde mevcut.
- [ ] Gizlilik bildirimi çerez kaydını içeren çereze özel bildirimi referans alır.

### 17. KPI'lar

| KPI | Hedef |
|-----|-------|
| Ret oranı eşitlik denetimleri | Üç aylık |
| Karanlık örüntü bulguları için düzeltme süresi | < 30 gün |
| Çerez kaydı vs. gerçek tarama farkı | 0 yetkisiz çerez |
| Reddedenler için yeniden istek sıklığı | Her 6 ayda bir |
| Rıza kaydı saklama | En az 24 ay |
