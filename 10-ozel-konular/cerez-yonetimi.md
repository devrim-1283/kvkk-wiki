---
Doküman / Document: Çerez ve Benzeri İzleme Teknolojileri Yönetimi / Cookie and Similar Tracking Technologies Management
Bölüm / Section: 10-ozel-konular
Sahip / Owner: KVKK Sorumlusu + Pazarlama + Web/Dijital / KVKK Officer + Marketing + Web/Digital
Onaylayan / Approved by: Hukuk Müdürü + KVKK Komitesi / Head of Legal + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + Kurul Çerez Rehberi güncellemelerinde / Annual + on Authority Cookie Guide updates
İlgili Mevzuat / Legal Reference: Law No. 6698 (KVKK) Art. 5; Law No. 5651; KVKK "Cookie Practices Guide" (June 2022); IAB TCF v2.2; ePrivacy Directive (comparative)
---

## English

# Cookie and Similar Tracking Technologies Management

## 1. Purpose and Scope

This document defines the management - in line with KVKK and the Authority's Cookie Practices Guide (June 2022) - of cookies (HTTP cookies), local storage, session storage, IndexedDB, fingerprinting, SDK trackers, and pixel technologies used on our websites, mobile apps, and digital properties.

## 2. Legal Framework

### 2.1. KVKK and Authority Guide

- **KVKK Art. 5:** General reference to processing conditions - cookies are tools of personal data processing.
- **KVKK Cookie Guide (June 2022):** Cookie types, legal grounds, CMP requirements, privacy notice standard.
- **Law No. 5651:** Hosting/content provider obligations (traffic logs - some cookies are traffic data).

### 2.2. General Principle

> If personal data is processed via cookies, **all KVKK principles apply** - disclosure, legal ground, proportionality, explicit consent (if required), cross-border transfer rules.

## 3. Cookie Categories

### 3.1. Strictly Necessary Cookies

**Definition:** **Absolutely required** for the basic operation of the site. Service cannot be provided if disabled.

**Examples:**

- Session cookie.
- Cart/shopping persistence.
- Form-input transient storage.
- CSRF token.
- Load balancing.
- Persistence of cookie preference (paradox: the cookie that records the preference is itself necessary).

**Legal ground:** KVKK Art. 5(2)(c) (formation/performance of contract) or Art. 5(2)(f) (legitimate interest).

**Explicit consent?** **Not required.** But disclosure is mandatory.

### 3.2. Performance / Analytics Cookies

**Definition:** Measurement of site usage - visitor count, bounce rate, page durations.

**Examples:**

- Google Analytics (GA4).
- Yandex Metrica.
- Matomo, Plausible (privacy-friendly options).
- Hotjar (heatmaps, session replay - risky).

**Legal ground:** Generally requires **explicit consent**. If anonymous measurement (IP masking, no user-identity tracking) is used, legitimate interest may be considered; the Authority's posture, however, leans toward consent.

**Explicit consent?** **Generally yes.**

### 3.3. Functional Cookies

**Definition:** Preferences - language, region, theme, font size, UI personalization.

**Legal ground:** Explicit consent or legitimate interest (usability). The Authority's guide leans toward **consent**.

**Explicit consent?** **Yes (recommended).**

### 3.4. Targeting / Advertising Cookies

**Definition:** Behavior tracking, profiling, personalized advertising, retargeting.

**Examples:**

- Google Ads, DoubleClick.
- Meta Pixel (Facebook/Instagram).
- TikTok Pixel.
- LinkedIn Insight Tag.
- Twitter/X Pixel.
- Criteo, RTB House.

**Legal ground:** **Explicit consent mandatory.**

**Explicit consent?** **Yes, definite.**

### 3.5. Social Media Cookies

**Definition:** Embedded video (YouTube), share buttons (Facebook, X), embedded posts.

**Legal ground:** Explicit consent (typically loads third-party cookies).

**Explicit consent?** **Yes.**

## 4. CMP (Consent Management Platform) Requirements

### 4.1. Authority Guide Expectations

A CMP - cookie consent management platform - must provide:

| Feature | Description |
|---------|-------------|
| Prior consent | Cookies must not start before consent. Only strictly necessary cookies on by default. |
| Granular choice | Per-category accept/reject. "Accept all" + "Reject all" + "Manage preferences". |
| "Reject" with equal ease | If "Accept All" is present, an equally prominent "Reject All" is required. Dark patterns forbidden. |
| Easy withdrawal | An always-accessible "My Cookie Preferences" link (footer). |
| Recording | Each consent recorded with timestamp, IP, user choices. |
| Retention | Consent record retained at least 3 years (proof). |
| Versioning | Renew consent if the CMP version changes. |

### 4.2. Recommended CMP Solutions

| Solution | Notes |
|----------|-------|
| OneTrust | Enterprise - KVKK + GDPR + IAB TCF |
| Cookiebot | Automatic scanning + inventory |
| Usercentrics | Cross-domain consent |
| Iubenda | Mid-size friendly |
| Self-hosted (custom) | Full control - requires team capacity |

### 4.3. Banned Dark Patterns

- "Accept" only button; "Reject" buried/below the fold.
- Long extra menu when "Reject" is clicked.
- Default acceptance on click into pop-up.
- Treating closure of pop-up as acceptance.
- "Accept to continue" forcing.
- Psychological pressure via color/visual difference.

> **Authority's tendency to sanction:** These patterns are violations of both KVKK and consumer law.

## 5. Cookie Privacy Notice

### 5.1. Minimum Content

The cookie privacy notice must include the following per KVKK Art. 10 + Cookie Guide:

1. **Data controller identity** - trade name, address, contact.
2. **What is a cookie** - brief definition.
3. **Categories used** - the 5 classes above.
4. **Purpose of each cookie** - why used.
5. **Third-party cookies** - who, what purpose, cross-border transfer or not.
6. **Retention period** - per cookie.
7. **Legal ground** - which paragraph of Art. 5(2) or explicit consent.
8. **Data subject rights** - reference to Art. 11.
9. **Cookie preference management** - link.
10. **Withdrawal method via the CMP.**

### 5.2. Placement and Visibility

- "Cookie Policy" link in website footer.
- CMP banner on first visit - clearly visible.
- "My Cookie Preferences" link accessible on every page.
- In mobile apps, in app settings menu.

### 5.3. Cookie Inventory Table

The privacy notice presents a **cookie inventory table**:

| Cookie Name | Owner | Type | Purpose | Duration | Legal Ground |
|-------------|-------|------|---------|----------|--------------|
| `_session_id` | Our company | Strictly necessary | Session management | Session | Performance of contract |
| `_ga` | Google | Performance | Analytics | 2 years | Explicit consent |
| `_fbp` | Meta | Targeting | Pixel tracking | 90 days | Explicit consent |
| `theme_pref` | Our company | Functional | Theme preference | 1 year | Explicit consent |

> The table is updated **monthly** by automatic scan (Cookiebot/OneTrust).

## 6. Third-Party Cookies and Cross-Border Transfer

### 6.1. Risk

Third-party cookies (Google, Meta, TikTok) transfer data to **foreign servers**. KVKK Art. 9 (cross-border transfer) applies.

### 6.2. Legal Ground for Cross-Border Transfer

- If an adequacy decision exists for the country, transfer is straightforward.
- If not: Standard Contract (SCC), binding corporate rules, explicit consent.
- In practice: **Explicit consent** is collected via the cookie banner + cross-border transfer information in the notice.

### 6.3. Transfer Transparency

For each third party, the cookie policy lists:

- Company name + country of establishment.
- Categories of data transferred.
- Purpose of transfer.
- Link to the third party's privacy policy.
- Known data retention policy.

## 7. Mobile Application Equivalent

In mobile apps, instead of cookies:

- SDK trackers (Firebase Analytics, Adjust, AppsFlyer, Branch).
- Advertising IDs (IDFA, GAID).
- Push tokens.
- Local storage / Keychain / Shared Preferences.

The same CMP principles apply:

- First-launch consent screen.
- Per-category selection.
- Withdrawal from settings.
- Apple ATT (iOS) and Google Privacy Sandbox compatibility in parallel.

## 8. IAB TCF (Transparency and Consent Framework)

### 8.1. What Is It?

IAB Europe's standard consent framework. v2.2 is current. Provides interoperability with the ad ecosystem.

### 8.2. KVKK Compliance Note

- TCF v2.2 is GDPR-oriented; it does not **fully overlap** with KVKK (e.g., the "legitimate interest balancing" interpretation differs).
- When TCF is used, KVKK requirements apply as an **additional layer**:
   - Privacy notice in Turkish, with KVKK terminology.
   - Explicit-consent definition aligned with KVKK.
   - Cross-border transfer explained in Turkish.

### 8.3. Türkiye Adaptation

- Türkiye-specific banner inside the TCF interface (KVKK reference).
- Equality of "object to legitimate interest" + "withdraw consent" as TCF refusal.
- Records stored KVKK-compliant.

## 9. Implementation Steps (12-week plan)

| Week | Action | Owner |
|------|--------|-------|
| 1-2 | Existing cookie inventory (automated scan) | Web team |
| 2-3 | Third-party cookie scope | Marketing + IT |
| 3-4 | Cookie category classification | KVKK + Legal |
| 4-6 | CMP selection + integration | IT + Marketing |
| 6-7 | Cookie privacy notice revision | Legal + KVKK |
| 7-8 | Banner UX + dark pattern check | Design + KVKK |
| 8-9 | Mobile SDK audit | Mobile team |
| 9-10 | Test environment release + internal audit | KVKK |
| 10-11 | Production go-live | IT |
| 11-12 | Monitoring + tuning | KVKK |

## 10. Common Mistakes

| Mistake | Correct approach |
|---------|------------------|
| Banner with one "Accept" button | Equally visible "Reject" required |
| Loading cookies before banner shown | Non-essential cookies after consent only |
| GA4 default-on | Explicit consent + IP anonymize |
| 3rd-party pixel "on" by default | Trigger after consent |
| 10-year cookie lifespan | Reasonable duration (max 1-2 years) |
| No "Cookie Policy" page | Standalone page mandatory |
| Out-of-date cookie inventory | Automated monthly scan |
| No CMP in mobile app | Separate mobile permission flow |

## 11. KPIs

| KPI | Target |
|-----|--------|
| Banner display rate | 100% (first visit) |
| Consent record rate | 95%+ |
| "Reject all" rate | (observed - not policy) |
| Cookie inventory currency | < 30 days |
| Consent renewal on CMP version change | 100% |
| Cookie notice readability (Flesch) | B1+ Turkish |

## 12. Linked Sections

- `03-aydinlatma-ve-acik-riza/` - Privacy notice standard structure.
- `07-aktarim/` - Cross-border transfer scope.
- `02-envanter-ve-sicil/` - VERBİS reporting of cookie inventory.

## 13. Version History

| Version | Date | Change | Approval |
|---------|------|--------|----------|
| 1.0 | 2026-05-08 | First publication | KVKK Committee |

---

## Türkçe

# Çerez ve Benzeri İzleme Teknolojileri Yönetimi

## 1. Amaç ve Kapsam

Web sitelerimiz, mobil uygulamalarımız ve dijital varlıklarımızda kullanılan çerez (HTTP cookie), local storage, session storage, IndexedDB, fingerprinting, SDK izleyicileri ve piksel teknolojilerinin KVKK ve KVKK'nın Haziran 2022'de yayımladığı "Çerez Uygulamaları Hakkında Rehber" çerçevesinde yönetimini tanımlar.

## 2. Yasal Çerçeve

### 2.1. KVKK ve Kurul Rehberi

- **KVKK m.5:** Kişisel veri işleme şartlarına atıf — çerez de kişisel veri işleme aracıdır.
- **KVKK Çerez Rehberi (Haziran 2022):** Çerez tipleri, hukuki sebepler, CMP gereksinimleri, aydınlatma metni standardı.
- **5651 sayılı Kanun:** Yer ve içerik sağlayıcı yükümlülükleri (trafik kaydı zorunluluğu — bazı çerezler trafik bilgisi).

### 2.2. Genel Prensip

> Çerez aracılığıyla kişisel veri işleniyorsa **KVKK'nın tüm ilkeleri uygulanır** — aydınlatma, hukuki sebep, ölçülülük, açık rıza (gerekiyorsa), yurt dışı aktarım kuralları.

## 3. Çerez Kategorileri

### 3.1. Zorunlu (Strictly Necessary) Çerezler

**Tanım:** Web sitesinin temel işlevi için **mutlaka gerekli**. Devre dışı bırakılırsa hizmet verilemez.

**Örnekler:**
- Oturum (session) çerezi.
- Sepet/alışveriş kaydı.
- Form girişi geçici saklama.
- CSRF token.
- Yük dengeleme.
- Çerez tercihinin kaydı (paradoks: tercihi kaydeden çerez de zorunludur).

**Hukuki sebep:** KVKK m.5/2-c (sözleşmenin kurulması/ifası) veya m.5/2-f (meşru menfaat).

**Açık rıza?** **Gerekmez.** Ancak **aydınlatma zorunlu.**

### 3.2. Performans / Analitik Çerezler

**Tanım:** Site kullanımının ölçülmesi, ziyaretçi sayısı, bounce rate, sayfa süreleri.

**Örnekler:**
- Google Analytics (GA4).
- Yandex Metrica.
- Matomo, Plausible (privacy-friendly seçenekler).
- Hotjar (heatmap, session replay — riskli).

**Hukuki sebep:** Genelde **açık rıza** gerekir. Anonim ölçüm (IP maskeleme, kullanıcı kimliği takibi yok) yapılıyorsa meşru menfaat değerlendirilebilir; ancak Kurul tutumu rıza yönündedir.

**Açık rıza?** **Genellikle evet.**

### 3.3. Fonksiyonel (Functional) Çerezler

**Tanım:** Tercihler — dil, bölge, tema, font boyutu, kullanıcı arayüzü kişiselleştirme.

**Hukuki sebep:** Açık rıza veya meşru menfaat (kullanım kolaylığı). Kurul rehberi bu alanı **rıza yönünde** öneriyor.

**Açık rıza?** **Evet (önerilir).**

### 3.4. Hedefleme / Reklam Çerezleri

**Tanım:** Davranış takibi, profilleme, kişiselleştirilmiş reklam, retargeting.

**Örnekler:**
- Google Ads, DoubleClick.
- Meta Pixel (Facebook/Instagram).
- TikTok Pixel.
- LinkedIn Insight Tag.
- Twitter/X Pixel.
- Criteo, RTB House.

**Hukuki sebep:** **Açık rıza zorunlu.**

**Açık rıza?** **Evet, kesin.**

### 3.5. Sosyal Medya Çerezleri

**Tanım:** Embedded video (YouTube), share butonları (Facebook, X), gömülü gönderiler.

**Hukuki sebep:** Açık rıza (genelde 3. taraf çerezi yüklenir).

**Açık rıza?** **Evet.**

## 4. CMP (Consent Management Platform) Gereksinimleri

### 4.1. Kurul Rehberi Beklentileri

CMP — yani çerez izin yönetim platformu — şu özellikleri sağlamalıdır:

| Özellik | Açıklama |
|---------|----------|
| Ön onay (prior consent) | Çerez kullanımı **rıza alınmadan** başlamamalıdır. Sadece zorunlu çerezler default açık. |
| Granüler seçim | Kategori bazında ayrı ayrı kabul/red. "Hepsini kabul et" + "Hepsini reddet" + "Tercihlerimi yönet". |
| "Reddet" eşit kolaylıkta | "Tümünü Kabul Et" butonu varsa **aynı seviyede** "Tümünü Reddet" butonu zorunlu. Karanlık desen yasak. |
| Kolay geri alma | Sayfada her zaman erişilebilir "Çerez Tercihlerim" bağlantısı (footer). |
| Kayıt | Her rıza zaman damgası, IP, kullanıcı tercihleri ile loglanır. |
| Saklama | Rıza kaydı en az 3 yıl (ispat yükü). |
| Versiyon yönetimi | CMP versiyonu değişirse rıza yenilenir. |

### 4.2. Önerilen CMP Çözümleri

| Çözüm | Notlar |
|-------|--------|
| OneTrust | Enterprise — KVKK + GDPR + IAB TCF |
| Cookiebot | Otomatik tarama + envanter |
| Usercentrics | Cross-domain consent |
| Iubenda | Orta ölçek dostu |
| Self-hosted (custom) | Tam kontrol — ekip kaynağı gerekir |

### 4.3. Yasak Karanlık Desenler (Dark Patterns)

- Sadece "Kabul Et" butonu, "Reddet" buruşturulmuş/sayfa altında.
- "Reddet" tıklayınca uzun ek menü.
- Pop-up'a tıklayınca varsayılan kabul.
- Sayfa kapanma simgesini kabul saymak.
- "Sürmek için kabul edin" zorlaması.
- Renk/görünüm farkıyla psikolojik baskı.

> **Kurul yaptırım eğilimi:** Bu desenler hem KVKK hem Tüketici Hukuku ihlali sayılır.

## 5. Çerez Aydınlatma Metni

### 5.1. Asgari İçerik

Çerez aydınlatma metni KVKK m.10 + Çerez Rehberi gereği şunları içermelidir:

1. **Veri sorumlusu kimliği** — şirket unvanı, adres, irtibat.
2. **Çerez nedir** — kısa tanım.
3. **Kullanılan çerez kategorileri** — yukarıdaki 5 sınıf.
4. **Her çerezin amacı** — neden kullanılıyor.
5. **Üçüncü taraf çerezleri** — kim, hangi amaç, yurt dışı aktarım var mı.
6. **Saklama süresi** — her çerez için.
7. **Hukuki sebep** — m.5/2 hangi bent veya açık rıza.
8. **İlgili kişi hakları** — m.11 atfı.
9. **Çerez tercihini yönetim** — link.
10. **CMP üzerinden geri alma yöntemi.**

### 5.2. Yer ve Görünürlük

- Web sitesi footer'ında "Çerez Politikası" bağlantısı.
- İlk ziyarette CMP banner — açıkça görünür.
- "Çerez Tercihlerim" bağlantısı her sayfada erişilebilir.
- Mobil uygulamada uygulama ayarları menüsünde.

### 5.3. Çerez Envanteri Tablosu

Aydınlatma metninde **çerez envanteri tablosu** sunulur:

| Çerez Adı | Sahibi | Tipi | Amacı | Süre | Hukuki Sebep |
|-----------|--------|------|-------|------|--------------|
| `_session_id` | Şirketimiz | Zorunlu | Oturum yönetimi | Oturum | Sözleşmenin ifası |
| `_ga` | Google | Performans | Analitik | 2 yıl | Açık rıza |
| `_fbp` | Meta | Hedefleme | Pixel takip | 90 gün | Açık rıza |
| `theme_pref` | Şirketimiz | Fonksiyonel | Tema tercihi | 1 yıl | Açık rıza |

> Tablo otomatik tarama (Cookiebot/OneTrust) ile **aylık** güncellenir.

## 6. Üçüncü Taraf Çerezler ve Yurt Dışı Aktarım

### 6.1. Risk

Üçüncü taraf çerezler (Google, Meta, TikTok) verileri **yurt dışı sunuculara** aktarır. KVKK m.9 (yurt dışı aktarım) hükümleri uygulanır.

### 6.2. Yurt Dışı Aktarım Hukuki Sebebi

- Yeterlilik kararı varsa: o ülkeye aktarım kolay.
- Yoksa: Standart Sözleşme (SCC), bağlayıcı şirket kuralları, açık rıza.
- Pratikte: **Açık rıza** çerez bandı üzerinden alınır + yurt dışı aktarım bilgilendirmesi metinde.

### 6.3. Aktarım Şeffaflığı

Çerez politikasında her üçüncü taraf için:
- Şirket adı + bağlı olduğu ülke.
- Aktarılan veri kategorisi.
- Aktarım amacı.
- Üçüncü tarafın gizlilik politikası bağlantısı.
- Bilinen veri tutma politikası.

## 7. Mobil Uygulama Eşdeğeri

Mobil uygulamalarda çerez kavramı yerine:
- SDK izleyicileri (Firebase Analytics, Adjust, AppsFlyer, Branch).
- Reklam ID (IDFA, GAID).
- Push token.
- Local storage / Keychain / Shared Preferences.

Aynı CMP prensipleri uygulanır:
- İlk açılış izin ekranı.
- Kategori bazlı seçim.
- Ayarlardan geri alma.
- Apple ATT (iOS) ve Google Privacy Sandbox uyumu paralel.

## 8. IAB TCF (Transparency and Consent Framework)

### 8.1. Nedir?

IAB Europe'un standart consent framework'ü. v2.2 güncel sürüm. Reklam ekosistemiyle interoperability sağlar.

### 8.2. KVKK Uyumu Notu

- TCF v2.2 GDPR odaklıdır; KVKK ile **tam örtüşmez** (örn. KVKK'da "meşru menfaat dengesi" yorumu farklı).
- TCF kullanılıyorsa KVKK gereksinimleri **ek katman** olarak uygulanır:
   - Aydınlatma metni Türkçe ve KVKK terimleriyle.
   - Açık rıza tanımı KVKK ile uyumlu.
   - Yurt dışı aktarım Türkçe açıklanır.

### 8.3. Türkiye Adaptasyonu

- TCF arayüzünde "Türkiye" özel banner (KVKK referansı).
- Reddetme TCF'de "object to legitimate interest" + "withdraw consent" eşitliği.
- Kayıtlar KVKK uyumlu saklanır.

## 9. Uygulama Adımları (12 haftalık plan)

| Hafta | Aksiyon | Sahip |
|-------|---------|-------|
| 1-2 | Mevcut çerez envanteri (otomatik tarama) | Web Ekibi |
| 2-3 | Üçüncü taraf çerez kapsamı | Pazarlama + IT |
| 3-4 | Çerez kategori sınıflandırma | KVKK + Hukuk |
| 4-6 | CMP seçimi + entegrasyonu | IT + Pazarlama |
| 6-7 | Çerez aydınlatma metni revize | Hukuk + KVKK |
| 7-8 | Banner UX + dark pattern kontrolü | Tasarım + KVKK |
| 8-9 | Mobil SDK denetimi | Mobil ekip |
| 9-10 | Test ortamı yayını + iç denetim | KVKK |
| 10-11 | Üretim canlı | IT |
| 11-12 | İzleme + ayarlar | KVKK |

## 10. Tipik Hatalar

| Hata | Doğru Yaklaşım |
|------|----------------|
| "Kabul Et" tek butonlu banner | Eşit görünür "Reddet" zorunlu |
| Banner görünmeden çerez yükleme | Tüm non-essential çerezler rıza sonrası |
| GA4 default kabul | Açık rıza + IP anonymize |
| 3. taraf piksel "açık" başlangıç | Rıza sonrası tetikleme |
| Çerez ömrü 10 yıl | Makul süre (max 1-2 yıl) |
| "Çerez Politikası" yok | Tek başına ayrı sayfa zorunlu |
| Çerez envanteri güncel değil | Otomatik aylık tarama |
| Mobil uygulamada CMP yok | Mobil için ayrı izin akışı |

## 11. KPI'lar

| KPI | Hedef |
|-----|-------|
| Banner görüntülenme oranı | %100 (ilk ziyaret) |
| Rıza kayıt oranı | %95+ |
| "Tümünü Reddet" oranı | (gözlem — politika değil) |
| Çerez envanteri güncellik | < 30 gün |
| CMP versiyon değişiminde rıza yenileme | %100 |
| Çerez aydınlatma okunabilirlik (Flesch) | B1+ Türkçe |

## 12. Bağlantılı Bölümler

- `03-aydinlatma-ve-acik-riza/` — Aydınlatma metni standart yapısı.
- `07-aktarim/` — Yurt dışı aktarım kapsamı.
- `02-envanter-ve-sicil/` — Çerez envanterinin VERBİS bildirimi.

## 13. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi |
