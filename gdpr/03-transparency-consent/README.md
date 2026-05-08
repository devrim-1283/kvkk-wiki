---
title: "Transparency and Consent — Section Overview"
title_tr: "Şeffaflık ve Onay — Bölüm Genel Bakış"
section: "03-transparency-consent"
language: ["en", "tr"]
status: "approved"
version: "2.1.0"
last_review: "2026-04-15"
next_review: "2026-10-15"
owner: "Data Protection Officer"
classification: "Internal"
related_articles: ["GDPR Art. 5(1)(a)", "GDPR Art. 6(1)(a)", "GDPR Art. 7", "GDPR Art. 8", "GDPR Art. 12", "GDPR Art. 13", "GDPR Art. 14"]
related_guidelines: ["EDPB Guidelines 1/2018 on transparency", "EDPB Guidelines 5/2020 on consent", "EDPB Guidelines 03/2022 on dark patterns"]
tags: ["transparency", "consent", "privacy-notice", "cmp", "article-13", "article-14", "article-7"]
---

## English

### Purpose of this Section

Transparency (Article 5(1)(a)) and lawful consent (Article 7) are the most visible privacy obligations: they determine what users see, what they can choose, and what they can object to. Failures here are also the most reported to supervisory authorities, because they manifest in cookie banners, sign-up flows, and email opt-ins that data subjects encounter every day.

This section provides:

1. Operational templates for the privacy notice (Articles 13–14) — including layered notices for web, mobile, employee, call-centre, and CCTV contexts.
2. A 30+ item privacy notice checklist mapped to GDPR articles and EDPB guidance.
3. A consent rules document grounded in Article 7 and EDPB Guidelines 5/2020 on consent.
4. A consent management platform (CMP) specification covering IAB TCF v2.2, granular cookie consent, and audit-ready logging.
5. Worked examples spanning ten common scenarios.

### Files in This Section

| File | Purpose |
|------|---------|
| `privacy-notice-template.md` | Articles 13–14 mandatory content; layered notice patterns; three full notices (customer signup, employee, CCTV). |
| `privacy-notice-checklist.md` | 30+ items mapped to GDPR articles and EDPB transparency guidelines. |
| `consent-rules.md` | Article 7 four-prong test (freely given, specific, informed, unambiguous), withdrawal, children, EDPB 5/2020 guidance. |
| `consent-management-platform.md` | CMP requirements, IAB TCF v2.2, cookie consent granularity, consent record schema, audit logs. |
| `examples.md` | Ten scenario-based walkthroughs from e-commerce signup to health-practice patient onboarding. |

### Why Transparency and Consent Get So Much Enforcement Attention

Supervisory authorities prioritise transparency and consent for three reasons:

1. **Visible to data subjects.** Most other GDPR obligations (ROPA, TOMs, vendor governance) are invisible to the public. Transparency and consent are the user-facing surface, and complaints are concrete: "the cookie banner did not let me say no."
2. **Easy to test.** A regulator can open the website and see whether the banner is compliant in five minutes. They cannot inspect the ROPA in five minutes.
3. **Cumulative impact.** Each visit of each user multiplies the affected population. A non-compliant cookie banner on a popular site touches millions of data subjects per month, generating proportionally large fines.

The published enforcement record bears this out: the largest fines in 2023–2025 were predominantly transparency- and consent-related (Meta, TikTok, Yahoo!, Criteo, Google).

### What This Section Does Not Cover

The boundaries of this section are deliberate:

- **Lawful basis selection (Article 6).** Covered in `01-core-concepts/lawful-basis.md`. Transparency disclosures depend on already having selected the right basis; this section assumes that selection is complete.
- **Data subject rights workflows.** Covered in `09-data-subject-rights/`. This section establishes what users are told about their rights; the rights mechanics live elsewhere.
- **Marketing campaign segmentation, targeting, and execution.** Operational marketing rules; this section establishes only the consent layer.
- **Email deliverability, SPF/DKIM/DMARC.** Engineering and operational concern; consent records here are necessary but not sufficient for deliverable email programmes.
- **Cookie scanner / vendor list governance.** Covered in `10-special-topics/cookies-and-tracking.md`.

### Key Principles

#### Transparency

The transparency principle requires that processing be lawful, fair, and transparent (Art. 5(1)(a)). Articles 12, 13, and 14 give the principle teeth:

- Article 12: information must be concise, transparent, intelligible, and easily accessible, in clear and plain language.
- Article 13: information to be provided where personal data are collected from the data subject.
- Article 14: information to be provided where personal data have not been obtained from the data subject.

EDPB Guidelines 1/2018 elaborate further: notices must be free of charge, prominent, written for the relevant audience (children should get a child-friendly notice), and must not "drown" the data subject in legalese.

#### Consent

Consent under Article 4(11) is "any freely given, specific, informed and unambiguous indication of the data subject's wishes by which he or she, by a statement or by a clear affirmative action, signifies agreement to the processing of personal data relating to him or her."

Article 7 imposes additional requirements:

- The controller must be able to demonstrate that consent was given (Art. 7(1)).
- A request for consent in a written declaration concerning other matters must be clearly distinguishable, intelligible, and in clear and plain language (Art. 7(2)).
- The data subject has the right to withdraw consent at any time, and withdrawal must be as easy as giving consent (Art. 7(3)).
- When assessing whether consent is freely given, account must be taken of whether performance of a contract is conditional on consent that is not necessary for that performance (Art. 7(4)).

EDPB Guidelines 5/2020 are the authoritative reading. They forbid pre-ticked boxes, make clear that "cookie walls" are problematic, prohibit bundled consent, and require granular opt-in for each distinct purpose.

#### Children's Consent (Article 8)

Where information society services are offered directly to a child, the child's consent is lawful only if the child is at least 16 years old (or such lower age, not below 13, as Member State law provides). Where the child is below the age threshold, processing is lawful only if and to the extent that consent is given or authorised by the holder of parental responsibility over the child (Art. 8(1)).

The controller must make reasonable efforts to verify in such cases that consent is given or authorised by the holder of parental responsibility (Art. 8(2)).

### Relationship to Other Sections

- `02-ropa/` — every entry that informs Article 13/14 disclosures.
- `04-retention-erasure/` — retention disclosures in the privacy notice.
- `06-organizational-measures/training.md` — staff training on transparency and consent UX.
- `09-data-subject-rights/` — withdrawal of consent and objection workflows.
- `10-special-topics/cookies-and-tracking.md` — applied transparency and consent to cookies.

### Reading Order

| Role | Recommended Order |
|------|-------------------|
| DPO | All five files in order. |
| Marketing operations / CRM lead | `consent-rules.md`, `consent-management-platform.md`, `examples.md`. |
| Web / mobile product team | `privacy-notice-template.md` (Section 3 channel-specific), `consent-management-platform.md`, `examples.md`. |
| HR | `privacy-notice-template.md` (Section 6.2), `consent-rules.md` (Section 2.1), `examples.md` (Examples 2 and 9). |
| Customer service operations | `privacy-notice-template.md` (Section 3.4), `examples.md` (Example 4). |
| Facilities / Security | `privacy-notice-template.md` (Section 3.5 and 6.3), `examples.md` (Example 3). |
| Engineering | `consent-management-platform.md` (Sections 4–6 and 9), `examples.md` (Examples 5 and 6). |
| Legal | `privacy-notice-checklist.md`, `consent-rules.md`, `examples.md`. |
| Internal audit | All five files; cross-reference with `02-ropa/`. |

### Distinctions That Trip Up Most Programmes

| Distinction | Right framing |
|-------------|---------------|
| "Privacy notice" vs. "consent" | The notice is mandatory transparency for ALL processing. Consent is one of six lawful bases under Art. 6 — and not the right one for most processing. |
| "Cookie consent" vs. "GDPR consent" | Cookie consent under ePrivacy Art. 5(3) applies to storing or accessing information on the user's terminal. It maps to GDPR consent for processing the resulting personal data, but the obligation also applies even if no personal data is involved. |
| "Consent" vs. "agreement to terms" | A user clicking "I agree to the Terms" is not giving GDPR consent. Consent must be specific to the processing purpose and separately demonstrable. |
| "Implied consent" | Not a thing under GDPR. Consent must be a clear affirmative action. |
| "Soft opt-in" for marketing | An ePrivacy concept (Art. 13(2) of the Directive). Allows marketing of similar products to existing customers under conditions, in some Member States. Does not displace GDPR transparency. |
| "Legitimate interest" for advertising | Highly contested. EDPB and many DPAs reject LI for behavioural advertising. Use consent. |

### Top-Level Compliance Numbers To Track

The Privacy Steering Committee should see the following metrics every month:

- Number of distinct privacy notices in production.
- Date of last review for each.
- Number of consent records captured in the period (and by category).
- Reject-all rate vs. accept-all rate (a sudden divergence suggests UX change).
- Number of consent withdrawals processed.
- Average time-to-respond on a privacy-notice change.
- Number of supervisory authority complaints related to transparency or consent.

### Acronyms Used in This Section

| Acronym | Expansion |
|---------|-----------|
| CMP | Consent Management Platform |
| TCF | Transparency and Consent Framework (IAB Europe standard for cookie consent signalling) |
| GVL | Global Vendor List (the IAB-maintained list of vendors using TCF) |
| LIA | Legitimate Interest Assessment (per Art. 6(1)(f)) |
| DPF | Data Privacy Framework (the EU–US transfer mechanism replacing Privacy Shield) |
| ATT | App Tracking Transparency (Apple's user permission for cross-app tracking) |
| ePrivacy | The ePrivacy Directive (2002/58/EC), which governs cookies and tracking on terminal equipment |
| EDPB | European Data Protection Board |
| ICO | UK Information Commissioner's Office |
| CNIL | Commission nationale de l'informatique et des libertés (French DPA) |

---

## Türkçe

### Bu Bölümün Amacı

Şeffaflık (Madde 5(1)(a)) ve hukuka uygun onay (Madde 7), gizlilik yükümlülüklerinin en görünür olanlarıdır: kullanıcıların ne göreceğini, neyi seçebileceklerini ve neye itiraz edebileceklerini belirlerler. Bu alandaki başarısızlıklar denetim otoritelerine en çok bildirilenlerdendir çünkü ilgili kişilerin her gün karşılaştığı çerez banner'larında, kayıt akışlarında ve e-posta tercih kontrollerinde kendini gösterir.

Bu bölüm aşağıdakileri sağlar:

1. Gizlilik bildirimi için operasyonel şablonlar (Madde 13–14) — web, mobil, çalışan, çağrı merkezi ve CCTV bağlamları için katmanlı bildirimler dahil.
2. GDPR maddeleri ve EDPB rehberliğine eşlenen 30+ maddelik gizlilik bildirimi kontrol listesi.
3. Madde 7 ve onaya ilişkin EDPB Kılavuzu 5/2020'ye dayanan onay kuralları belgesi.
4. IAB TCF v2.2, ayrıntılı çerez onayı ve denetime hazır loglama kapsayan onay yönetim platformu (CMP) spesifikasyonu.
5. On ortak senaryoyu kapsayan uygulamalı örnekler.

### Bu Bölümdeki Dosyalar

| Dosya | Amaç |
|-------|------|
| `privacy-notice-template.md` | Madde 13–14 zorunlu içeriği; katmanlı bildirim kalıpları; üç tam bildirim (müşteri kaydı, çalışan, CCTV). |
| `privacy-notice-checklist.md` | GDPR maddeleri ve EDPB şeffaflık rehberliğine eşlenmiş 30+ madde. |
| `consent-rules.md` | Madde 7 dörtlü test (özgürce verilen, belirli, bilgilendirilmiş, açık), geri çekme, çocuklar, EDPB 5/2020 rehberi. |
| `consent-management-platform.md` | CMP gereksinimleri, IAB TCF v2.2, çerez onay ayrıntısı, onay kayıt şeması, denetim logları. |
| `examples.md` | E-ticaret kaydından sağlık kuruluşu hasta kabulüne kadar on senaryo bazlı uygulama. |

### Şeffaflık ve Onayın Bu Kadar Çok Yaptırım Dikkati Çekmesinin Nedeni

Denetim otoriteleri üç nedenle şeffaflık ve onaya öncelik verir:

1. **İlgili kişilere görünür.** Diğer GDPR yükümlülüklerinin çoğu (ROPA, TOM'lar, tedarikçi yönetimi) kamuya görünmezdir. Şeffaflık ve onay kullanıcıya yönelik yüzeydir ve şikayetler somuttur: "çerez banner'ı hayır dememe izin vermedi".
2. **Test etmesi kolay.** Bir düzenleyici web sitesini açıp banner'ın uyumlu olup olmadığını beş dakikada görebilir. ROPA'yı beş dakikada inceleyemez.
3. **Birikimli etki.** Her kullanıcının her ziyareti etkilenen nüfusu çarpar. Popüler bir sitede uyumsuz çerez banner'ı ayda milyonlarca ilgili kişiye dokunur ve orantılı olarak büyük cezalar üretir.

Yayınlanan yaptırım kaydı bunu doğrular: 2023–2025'in en büyük cezaları ağırlıklı olarak şeffaflık ve onay ile ilgiliydi (Meta, TikTok, Yahoo!, Criteo, Google).

### Bu Bölümün Kapsamadığı Konular

Bu bölümün sınırları kasıtlıdır:

- **Hukuki sebep seçimi (Madde 6).** `01-core-concepts/lawful-basis.md` dosyasında ele alınmıştır. Şeffaflık ifşaları, doğru sebebin halihazırda seçilmiş olmasına bağlıdır; bu bölüm seçimin tamamlandığını varsayar.
- **İlgili kişi hakları iş akışları.** `09-data-subject-rights/` dosyasında ele alınmıştır. Bu bölüm, kullanıcılara haklarına ilişkin neyin söylendiğini belirler; haklar mekaniği başka yerde yaşar.
- **Pazarlama kampanya segmentasyonu, hedefleme ve yürütme.** Operasyonel pazarlama kuralları; bu bölüm yalnızca onay katmanını belirler.
- **E-posta teslimatı, SPF/DKIM/DMARC.** Mühendislik ve operasyonel konu; buradaki onay kayıtları teslim edilebilir e-posta programları için gerekli ama yeterli değildir.
- **Çerez tarayıcı / tedarikçi listesi yönetimi.** `10-special-topics/cookies-and-tracking.md` dosyasında ele alınmıştır.

### Temel İlkeler

#### Şeffaflık

Şeffaflık ilkesi, işlemenin hukuka uygun, adil ve şeffaf olmasını gerektirir (Madde 5(1)(a)). Madde 12, 13 ve 14 bu ilkeyi diş gibi koruyucu hale getirir:

- Madde 12: bilgiler özlü, şeffaf, anlaşılır ve kolay erişilebilir olmalı, açık ve sade bir dilde sunulmalıdır.
- Madde 13: kişisel veri ilgili kişiden alındığında verilecek bilgiler.
- Madde 14: kişisel veri ilgili kişiden alınmadığında verilecek bilgiler.

EDPB Kılavuz 1/2018 daha fazla ayrıntı verir: bildirimler ücretsiz, belirgin, ilgili kitleye yönelik yazılmış olmalı (çocuklar için çocuk dostu bildirim verilmelidir) ve ilgili kişiyi hukukçu jargonu içinde "boğmamalıdır".

#### Onay

Madde 4(11) kapsamında onay, "ilgili kişinin kendisine ilişkin kişisel verilerin işlenmesine bir beyan veya açık onaylayıcı bir eylemle, özgürce verilen, belirli, bilgilendirilmiş ve kuşku götürmeyen biçimde anlaşma anlamına gelen herhangi bir irade beyanı"dır.

Madde 7 ek gereksinimler getirir:

- Veri sorumlusu, onayın verildiğini gösterebilmelidir (Madde 7(1)).
- Diğer hususlara ilişkin yazılı bir beyanda yer alan onay talebi, açıkça ayırt edilebilir, anlaşılır ve açık ve sade bir dilde olmalıdır (Madde 7(2)).
- İlgili kişi onayı her zaman geri çekme hakkına sahiptir ve geri çekme onay vermek kadar kolay olmalıdır (Madde 7(3)).
- Onayın özgürce verilip verilmediği değerlendirilirken, sözleşmenin ifasının söz konusu ifa için gerekli olmayan bir onaya bağlı olup olmadığı dikkate alınmalıdır (Madde 7(4)).

EDPB Kılavuz 5/2020 yetkili okumadır. Önceden işaretli kutuları yasaklar, "çerez duvarlarını" sorunlu hale getirir, paketlenmiş onayı yasaklar ve her ayrı amaç için ayrıntılı opt-in gerektirir.

#### Çocukların Onayı (Madde 8)

Bilgi toplumu hizmetleri çocuğa doğrudan sunulduğunda, çocuğun onayı yalnızca çocuk en az 16 yaşında ise (veya Üye Devlet hukukunun öngördüğü, 13'ten düşük olmayan yaşta) hukuka uygundur. Çocuk yaş eşiğinin altındaysa, işleme yalnızca ebeveyn sorumluluğunu elinde tutan kişi tarafından verilen veya yetki verilen onay ölçüsünde hukuka uygundur (Madde 8(1)).

Veri sorumlusu, bu durumlarda onayın ebeveyn sorumluluğunu elinde tutan kişi tarafından verildiğini veya yetki verildiğini doğrulamak için makul çaba göstermelidir (Madde 8(2)).

### Diğer Bölümlerle İlişki

- `02-ropa/` — Madde 13/14 ifşalarını besleyen her giriş.
- `04-retention-erasure/` — gizlilik bildirimindeki saklama ifşaları.
- `06-organizational-measures/training.md` — şeffaflık ve onay UX'i konusunda personel eğitimi.
- `09-data-subject-rights/` — onay geri çekme ve itiraz iş akışları.
- `10-special-topics/cookies-and-tracking.md` — çerezlere uygulanmış şeffaflık ve onay.

### Okuma Sırası

| Rol | Önerilen Sıra |
|-----|----------------|
| DPO | Beş dosyanın tamamı sırasıyla. |
| Pazarlama operasyonları / CRM lideri | `consent-rules.md`, `consent-management-platform.md`, `examples.md`. |
| Web / mobil ürün ekibi | `privacy-notice-template.md` (Bölüm 3 kanal özel), `consent-management-platform.md`, `examples.md`. |
| İK | `privacy-notice-template.md` (Bölüm 6.2), `consent-rules.md` (Bölüm 2.1), `examples.md` (Örnek 2 ve 9). |
| Müşteri hizmetleri operasyonları | `privacy-notice-template.md` (Bölüm 3.4), `examples.md` (Örnek 4). |
| Tesis / Güvenlik | `privacy-notice-template.md` (Bölüm 3.5 ve 6.3), `examples.md` (Örnek 3). |
| Mühendislik | `consent-management-platform.md` (Bölüm 4–6 ve 9), `examples.md` (Örnek 5 ve 6). |
| Hukuk | `privacy-notice-checklist.md`, `consent-rules.md`, `examples.md`. |
| İç denetim | Beş dosyanın tamamı; `02-ropa/` ile çapraz referans. |

### Çoğu Programın Tökezlediği Ayrımlar

| Ayrım | Doğru çerçeveleme |
|-------|--------------------|
| "Gizlilik bildirimi" vs. "onay" | Bildirim TÜM işleme için zorunlu şeffaflıktır. Onay, Madde 6 kapsamındaki altı hukuki sebepten biridir — ve çoğu işleme için doğru olan değildir. |
| "Çerez onayı" vs. "GDPR onayı" | ePrivacy Madde 5(3) kapsamında çerez onayı, kullanıcının terminalinde bilgi saklamaya veya bilgiye erişmeye uygulanır. Ortaya çıkan kişisel verinin işlenmesi için GDPR onayına eşlenir, ancak yükümlülük kişisel veri olmasa bile geçerlidir. |
| "Onay" vs. "şartlara onay" | "Şartları kabul ediyorum" tıklayan bir kullanıcı GDPR onayı vermiyor. Onay işleme amacına özel ve ayrı kanıtlanabilir olmalıdır. |
| "Zımni onay" | GDPR altında bir şey değil. Onay açık onaylayıcı bir eylem olmalıdır. |
| Pazarlama için "Yumuşak opt-in" | Bir ePrivacy konsepti (Direktif Madde 13(2)). Bazı Üye Devletlerde mevcut müşterilere benzer ürünlerin koşullar altında pazarlanmasına izin verir. GDPR şeffaflığını yerinden etmez. |
| Reklam için "Meşru menfaat" | Yüksek derecede tartışmalı. EDPB ve birçok DPA, davranışsal reklam için LI'yi reddeder. Onay kullanın. |

### Takip Edilecek Üst Düzey Uyumluluk Sayıları

Gizlilik Yönlendirme Komitesi her ay aşağıdaki metrikleri görmelidir:

- Üretimdeki ayrı gizlilik bildirimi sayısı.
- Her biri için son inceleme tarihi.
- Dönemde yakalanan onay kaydı sayısı (kategori bazında).
- Reddet-tümü oranı vs. kabul-et-tümü oranı (ani sapma UX değişikliğini gösterir).
- İşlenen onay geri çekme sayısı.
- Gizlilik bildirimi değişikliğinde ortalama yanıt süresi.
- Şeffaflık veya onay ile ilgili denetim otoritesi şikayet sayısı.

### Versioning Discipline

Every privacy notice and consent text is a versioned artefact. The discipline is:

- Each version has a human-readable version number (e.g., `v6.1`) and an effective date.
- Each version is immutably archived; old versions are retrievable for the longest applicable retention period.
- Each consent record references the version of the text shown at the moment of consent.
- A change log is maintained alongside the current notice, summarising what changed and why.
- Material changes prompt re-consent or re-display where required (per `consent-management-platform.md` Section 7).

This discipline allows the controller to defend, years later, that consent given on a specific date was given against a specific text — a frequent point of supervisory authority enquiry.

### Sürümleme Disiplini

Her gizlilik bildirimi ve onay metni sürümlenmiş bir eserdir. Disiplin şudur:

- Her sürümün insan okunabilir bir sürüm numarası (örneğin `v6.1`) ve yürürlük tarihi vardır.
- Her sürüm değiştirilemez biçimde arşivlenir; eski sürümler geçerli en uzun saklama süresi boyunca erişilebilirdir.
- Her onay kaydı, onay anında gösterilen metnin sürümüne atıfta bulunur.
- Mevcut bildirimin yanında değişiklik kaydı tutulur; neyin neden değiştiği özetlenir.
- Önemli değişiklikler gerektiğinde yeniden onay veya yeniden gösterimi tetikler (`consent-management-platform.md` Bölüm 7 uyarınca).

Bu disiplin, veri sorumlusunun belirli bir tarihte verilen onayın belirli bir metne karşı verildiğini yıllar sonra savunmasına olanak tanır — bu, denetim otoritesi sorgulamalarında sıkça karşılaşılan bir noktadır.

### Bu Bölümde Kullanılan Kısaltmalar

| Kısaltma | Açılım |
|----------|--------|
| CMP | Onay Yönetim Platformu (Consent Management Platform) |
| TCF | Şeffaflık ve Onay Çerçevesi (IAB Europe çerez onay sinyali standardı) |
| GVL | Global Tedarikçi Listesi (TCF kullanan tedarikçilerin IAB tarafından sürdürülen listesi) |
| LIA | Meşru Menfaat Değerlendirmesi (Madde 6(1)(f) uyarınca) |
| DPF | Veri Gizliliği Çerçevesi (Privacy Shield'ın yerini alan AB-ABD aktarım mekanizması) |
| ATT | Uygulama İzleme Şeffaflığı (Apple'ın çapraz uygulama izleme için kullanıcı izni) |
| ePrivacy | ePrivacy Direktifi (2002/58/EC), terminal ekipmanında çerezleri ve izlemeyi düzenler |
| EDPB | Avrupa Veri Koruma Kurulu |
| ICO | Birleşik Krallık Bilgi Komiserliği Ofisi |
| CNIL | Commission nationale de l'informatique et des libertés (Fransız DPA) |
