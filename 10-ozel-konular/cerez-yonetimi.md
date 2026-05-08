---
Doküman: Çerez ve Benzeri İzleme Teknolojileri Yönetimi
Bölüm: 10-ozel-konular
Sahip: KVKK Sorumlusu + Pazarlama + Web/Dijital
Onaylayan: Hukuk Müdürü + KVKK Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + Kurul Çerez Rehberi güncellemelerinde
İlgili Mevzuat: 6698 sayılı KVKK m.5; 5651 sayılı Kanun; KVKK "Çerez Uygulamaları Hakkında Rehber" (Haziran 2022); IAB TCF v2.2; ePrivacy Yönergesi (karşılaştırma)
---

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
