---
title: "Consent Management Platform — Specification, IAB TCF v2.2, Logging, Audit"
title_tr: "Onay Yönetim Platformu — Spesifikasyon, IAB TCF v2.2, Loglama, Denetim"
section: "03-transparency-consent"
language: ["en", "tr"]
status: "approved"
version: "2.5.0"
last_review: "2026-04-15"
next_review: "2026-10-15"
owner: "Data Protection Officer + Marketing Operations"
classification: "Internal"
related_articles: ["GDPR Art. 4(11)", "GDPR Art. 6(1)(a)", "GDPR Art. 7", "GDPR Art. 13", "ePrivacy Directive Art. 5(3)"]
related_guidelines: ["EDPB Guidelines 5/2020 on consent", "EDPB Guidelines 03/2022 on dark patterns", "IAB Europe TCF v2.2 Specification", "CNIL Cookies and Trackers Guidelines"]
tags: ["cmp", "cookies", "tcf", "consent-records", "audit-logs", "eprivacy"]
---

## English

### 1. What a CMP Must Do

A Consent Management Platform (CMP) is the operational engine for cookie and tracking-technology consent. It must:

1. Display a compliant consent notice (banner or modal) on first visit and on material change.
2. Offer purpose-specific, granular consent — not "Accept All" alone.
3. Default all non-essential consents to off.
4. Make "Reject" as easy as "Accept" (no dark patterns).
5. Persist consent across sessions and devices where the user is identifiable.
6. Allow withdrawal at any time, accessible from a persistent privacy preferences link.
7. Record each consent decision in an immutable, queryable log.
8. Block all non-essential technologies until consent is given.
9. Reflect the user's choice in real time across first-party and third-party tags.

### 2. Cookie Categories

| Category | Purpose | Lawful Basis | Default |
|----------|---------|--------------|---------|
| Strictly necessary | Session management, load balancing, security, accessibility | Art. 6(1)(b) and (f); ePrivacy Art. 5(3) exemption | On (consent not required) |
| Functional (preferences) | Language, region, theme, accessibility settings | Art. 6(1)(a) consent (in most cases) | Off |
| Analytics / performance | Site usage analytics, A/B testing, error tracking | Art. 6(1)(a) consent | Off |
| Marketing / advertising | Ad targeting, retargeting, conversion tracking | Art. 6(1)(a) consent | Off |
| Social media | Embedded social widgets that set third-party cookies | Art. 6(1)(a) consent | Off |

Important: classification depends on the actual technology, not vendor claims. Many "analytics" tools also do advertising, in which case consent must cover both.

### 3. Banner / Modal Design Requirements

#### 3.1 Mandatory Elements (per EDPB 03/2022 and CNIL guidance)

- Clear identification of the controller.
- Plain-language summary of cookie purposes.
- Granular per-category controls (off by default).
- Equally prominent **Accept all** and **Reject all** buttons (or **Continue without accepting**).
- A "Save my choices" button when granular preferences are set.
- A persistent way to revisit choices (typically a small "Cookie preferences" link in the footer).
- Link to full cookie notice / privacy policy.

#### 3.2 Anti-Patterns Forbidden by EDPB Guidelines 03/2022

- Visual nudging (large green "Accept" button vs. small grey "Reject" link).
- Hidden Reject behind multiple clicks.
- "Continue browsing means consent."
- Pre-ticked category boxes.
- Color and contrast asymmetry between Accept and Reject.
- Banner covering the page until consent given for non-essential cookies.
- "Legitimate interest" toggles defaulted on for advertising vendors (per CNIL and DPC guidance).

#### 3.3 Acceptable Designs

| Design pattern | Compliance |
|----------------|-----------|
| Two equally-styled buttons "Accept all" / "Reject all" plus "Customise" | Compliant |
| One-layer "Accept all" / "Customise (granular toggles)" / "Reject all" | Compliant |
| Two-layer banner with first layer offering "Accept all," "Reject all," "Show preferences" | Compliant |
| Pay-or-OK model (free service with cookies vs. paid no-cookie service) | Conditional — under scrutiny; depends on Member State and EDPB Opinion 08/2024; treat as high-risk |

### 4. IAB TCF v2.2

The Transparency and Consent Framework version 2.2 (effective from 2024) is the primary technical standard for sharing consent state with third-party advertising vendors.

Key features of v2.2:

- "Reject all" must be on the first layer, equally prominent as "Accept all."
- "Legitimate interest" claims for advertising are removed from purposes 3, 4, 5, 6 (limited LI use).
- Vendor count must be visible on the first layer.
- Withdrawal pathway must be clear.
- The Global Vendor List (GVL) version is logged.

CMP signals:

- `gdprApplies` — boolean.
- `tcString` — encoded consent state.
- `cmpStatus` — loading state.
- `eventStatus` — user-facing event lifecycle.

When integrating, ensure that the IAB TCF API events drive **all** advertising tag firing. A tag manager with consent mode is required (e.g., GTM with consent mode v2 or equivalent).

### 5. Consent Record Schema

Every consent decision should produce a record with at least the following fields:

```yaml
consent_record:
  id: "cr_2026_05_08_a1b2c3d4"
  data_subject:
    id: "anonymous_user_xyz"  # or authenticated user ID
    type: "anonymous" | "authenticated"
  timestamp: "2026-05-08T14:23:11Z"
  timezone: "UTC"
  ip_address_truncated: "203.0.113.0/24"  # or hashed
  user_agent: "Mozilla/5.0 ..."
  cmp:
    name: "AcmeCMP"
    version: "v2.2.4"
    notice_version: "v6.1"
  notice_text_hash: "sha256:..."
  purposes:
    - id: "strictly_necessary"
      consented: true
      basis: "ePrivacy_5(3)_exemption"
    - id: "functional_preferences"
      consented: false
    - id: "analytics"
      consented: true
      vendor_specific:
        - "google_analytics_4"
        - "datadog_rum"
    - id: "marketing"
      consented: false
    - id: "social"
      consented: false
  tcf_string: "CPxxxxx..."  # if TCF in use
  withdrawal:
    withdrawn: false
    withdrawn_at: null
    withdrawn_via: null
  source:
    page_url: "https://acme.eu/checkout"
    referrer: "https://acme.eu/cart"
  retention:
    expires_at: "2027-05-08T14:23:11Z"  # 12 months default for online consents
```

### 6. Logging and Audit

The CMP must produce an immutable audit log with:

- Append-only storage.
- Cryptographic hashing of records (linked-list / Merkle).
- Independent retention from the live preference store.
- Retention aligned to the longest applicable statute of limitations and to demonstrate accountability under Art. 5(2) — typically 3–5 years.
- Export to CSV / JSON on supervisory authority request.

Sample audit query: "Show me every consent decision for user authenticated_id=12345 since 2024-01-01."

The log must answer:

- What did we ask?
- What did the user choose?
- When?
- Through which CMP version?
- Has the user changed or withdrawn the choice?

### 7. Refresh and Re-Consent

Re-display the banner (refresh consent) when:

- Notice text materially changes.
- New purposes or vendors are added that the previous consent does not cover.
- Consent is older than 12–13 months (CNIL guidance: refresh annually).
- The user clears their browser cookies (state is rebuilt; treat as new visitor).

### 8. Mobile App Consent

In-app consent has additional considerations:

- App store policies (Apple ATT, Google Play Data Safety) impose additional disclosure requirements.
- Consent must be re-obtainable from in-app settings.
- Apple ATT permission applies to use of the IDFA for cross-app tracking; this is separate from GDPR consent but often runs alongside it.
- SDK consent gating must be technically enforced (don't initialise the SDK before consent).

### 9. Server-Side and Backend Consent

Increasingly, advertising and analytics flow through server-side endpoints. CMP integration must propagate consent state to:

- Server-side Google Tag Manager.
- Customer data platform (Segment, RudderStack).
- Backend marketing automation.
- Data warehouse pipelines that feed advertising audiences.

If consent is withheld, the entire downstream chain must drop the data.

### 10. Vendor Due Diligence

Before integrating a CMP:

- Confirm IAB TCF v2.2 conformance (where applicable).
- Confirm CMP processes consent records as a processor under your DPA.
- Confirm log retention and immutability features.
- Confirm support for granular per-vendor consent.
- Confirm dark-pattern audits / certifications.
- Confirm performance impact and accessibility.
- Test on real devices and browsers, including assistive technology.

### 11. Testing Cadence

| Test | Frequency | Owner |
|------|-----------|-------|
| Banner displays on first visit | Quarterly | Marketing Ops |
| Reject-all path works as specified | Quarterly | DPO |
| Granular toggles match technical reality (no tags fire when off) | Quarterly | DPO + Engineering |
| TCF string decoded and validated | Quarterly | Engineering |
| Consent records exportable on demand | Annually + on demand | DPO |
| New vendor added → re-display banner | On change | Marketing Ops |
| Cross-browser, cross-device test (desktop, mobile, tablet) | Semi-annually | QA |
| Accessibility (screen reader, keyboard) | Semi-annually | Accessibility lead |

### 12. Common Failure Modes

1. Tags fire before consent is given (race condition).
2. "Legitimate interest" toggles default on for advertising vendors.
3. Reject-all hidden under "Customise."
4. Consent state not synchronised between devices for logged-in users.
5. CMP loaded after main analytics tag — analytics fires before consent.
6. Withdrawal path requires email — not as easy as giving.
7. Consent records do not include the version of the notice text.
8. Re-display logic broken; users never re-prompted after material change.
9. Cookie scanner out of date; new tags introduced without classification.
10. Mobile app consent gating relies on UI hiding only, not on SDK initialisation.

---

## Türkçe

### 1. Bir CMP Ne Yapmalıdır

Onay Yönetim Platformu (CMP), çerez ve izleme teknolojisi onayının operasyonel motorudur. Şunları yapmalıdır:

1. İlk ziyarette ve önemli değişiklikte uyumlu bir onay bildirimi (banner veya modal) görüntülemek.
2. Amaca özgü, ayrıntılı onay sunmak — sadece "Tümünü Kabul Et" değil.
3. Tüm zorunlu olmayan onayları varsayılan olarak kapalı yapmak.
4. "Reddet"i "Kabul Et" kadar kolay yapmak (karanlık desen yok).
5. Kullanıcı tanımlanabilir olduğunda onayı oturumlar ve cihazlar arasında saklamak.
6. Kalıcı bir gizlilik tercihleri bağlantısından erişilebilir, istediği zaman geri çekmeye izin vermek.
7. Her onay kararını değiştirilemez, sorgulanabilir bir logda kaydetmek.
8. Onay verilene kadar tüm zorunlu olmayan teknolojileri engellemek.
9. Kullanıcının seçimini birinci taraf ve üçüncü taraf etiketleri arasında gerçek zamanlı yansıtmak.

### 2. Çerez Kategorileri

| Kategori | Amaç | Hukuki Sebep | Varsayılan |
|----------|------|--------------|-----------|
| Kesinlikle gerekli | Oturum yönetimi, yük dengeleme, güvenlik, erişilebilirlik | Madde 6(1)(b) ve (f); ePrivacy Madde 5(3) muafiyeti | Açık (onay gerekmez) |
| İşlevsel (tercihler) | Dil, bölge, tema, erişilebilirlik ayarları | Madde 6(1)(a) onay (çoğu durumda) | Kapalı |
| Analitik / performans | Site kullanım analitiği, A/B testi, hata izleme | Madde 6(1)(a) onay | Kapalı |
| Pazarlama / reklam | Reklam hedefleme, retargeting, dönüşüm izleme | Madde 6(1)(a) onay | Kapalı |
| Sosyal medya | Üçüncü taraf çerezler ayarlayan gömülü sosyal widget'lar | Madde 6(1)(a) onay | Kapalı |

Önemli: sınıflandırma fiili teknolojiye bağlıdır, tedarikçi iddialarına değil. Birçok "analitik" aracı da reklam yapar; bu durumda onay her ikisini de kapsamalıdır.

### 3. Banner / Modal Tasarım Gereksinimleri

#### 3.1 Zorunlu Öğeler (EDPB 03/2022 ve CNIL rehberi uyarınca)

- Veri sorumlusunun açık kimliği.
- Çerez amaçlarının sade dilli özeti.
- Kategori başına ayrıntılı kontroller (varsayılan kapalı).
- Eşit derecede belirgin **Tümünü Kabul Et** ve **Tümünü Reddet** düğmeleri (veya **Kabul etmeden devam et**).
- Ayrıntılı tercihler ayarlandığında "Seçimlerimi kaydet" düğmesi.
- Seçimleri tekrar gözden geçirmek için kalıcı bir yol (genellikle alt bilgide küçük bir "Çerez tercihleri" bağlantısı).
- Tam çerez bildirimine / gizlilik politikasına bağlantı.

#### 3.2 EDPB Kılavuz 03/2022 Tarafından Yasaklanan Karşıt Desenler

- Görsel yönlendirme (büyük yeşil "Kabul Et" düğmesi, küçük gri "Reddet" bağlantısı).
- Reddi birden fazla tıklamanın arkasına gizlemek.
- "Gezinmeye devam etmek onay anlamına gelir."
- Önceden işaretli kategori kutuları.
- Kabul ve Reddet arasında renk ve kontrast asimetrisi.
- Zorunlu olmayan çerezler için onay verilene kadar sayfayı kapatan banner.
- Reklam tedarikçileri için varsayılan açık olan "Meşru menfaat" geçişleri (CNIL ve DPC rehberi uyarınca).

#### 3.3 Kabul Edilebilir Tasarımlar

| Tasarım deseni | Uyumluluk |
|----------------|-----------|
| Eşit stilli iki düğme "Tümünü Kabul Et" / "Tümünü Reddet" artı "Özelleştir" | Uyumlu |
| Tek katman "Tümünü Kabul Et" / "Özelleştir (ayrıntılı geçişler)" / "Tümünü Reddet" | Uyumlu |
| İlk katmanda "Tümünü Kabul Et", "Tümünü Reddet", "Tercihleri göster" sunan iki katmanlı banner | Uyumlu |
| Öde-veya-OK modeli (çerezli ücretsiz hizmet vs. çerezsiz ücretli hizmet) | Koşullu — incelemede; Üye Devlete ve EDPB Görüş 08/2024'e bağlı; yüksek risk olarak ele alınır |

### 4. IAB TCF v2.2

Şeffaflık ve Onay Çerçevesi sürüm 2.2 (2024'ten itibaren yürürlükte), üçüncü taraf reklam tedarikçileriyle onay durumunu paylaşmak için birincil teknik standarttır.

v2.2'nin temel özellikleri:

- "Tümünü Reddet" ilk katmanda olmalı, "Tümünü Kabul Et" ile eşit derecede belirgin olmalıdır.
- 3, 4, 5, 6 numaralı amaçlar için reklamcılığa yönelik "Meşru menfaat" iddiaları kaldırıldı (sınırlı LI kullanımı).
- Tedarikçi sayısı ilk katmanda görünür olmalıdır.
- Geri çekme yolu açık olmalıdır.
- Global Tedarikçi Listesi (GVL) sürümü loglanır.

CMP sinyalleri:

- `gdprApplies` — boolean.
- `tcString` — kodlanmış onay durumu.
- `cmpStatus` — yükleme durumu.
- `eventStatus` — kullanıcıya yönelik olay yaşam döngüsü.

Entegre ederken, IAB TCF API olaylarının **tüm** reklam etiketi tetiklemesini yönlendirdiğinden emin olun. Onay modu olan bir etiket yöneticisi gereklidir (örn. GTM ile onay modu v2 veya eşdeğeri).

### 5. Onay Kaydı Şeması

Her onay kararı en azından aşağıdaki alanları içeren bir kayıt üretmelidir:

```yaml
onay_kaydi:
  id: "cr_2026_05_08_a1b2c3d4"
  ilgili_kisi:
    id: "anonim_kullanici_xyz"
    tip: "anonim" | "kimliği_doğrulanmış"
  zaman_damgasi: "2026-05-08T14:23:11Z"
  saat_dilimi: "UTC"
  ip_adresi_kisaltilmis: "203.0.113.0/24"
  kullanici_araci: "Mozilla/5.0 ..."
  cmp:
    ad: "AcmeCMP"
    surum: "v2.2.4"
    bildirim_surumu: "v6.1"
  bildirim_metni_hash: "sha256:..."
  amaclar:
    - id: "kesinlikle_gerekli"
      onaylandi: true
      sebep: "ePrivacy_5(3)_muafiyeti"
    - id: "islevsel_tercihler"
      onaylandi: false
    - id: "analitik"
      onaylandi: true
      tedarikci_ozel:
        - "google_analytics_4"
        - "datadog_rum"
    - id: "pazarlama"
      onaylandi: false
    - id: "sosyal"
      onaylandi: false
  tcf_string: "CPxxxxx..."
  geri_cekme:
    geri_cekildi: false
    geri_cekildigi_tarih: null
    geri_cekme_yontemi: null
  kaynak:
    sayfa_url: "https://acme.eu/checkout"
    yonlendiren: "https://acme.eu/cart"
  saklama:
    son_tarih: "2027-05-08T14:23:11Z"
```

### 6. Loglama ve Denetim

CMP, şu özelliklere sahip değiştirilemez bir denetim logu üretmelidir:

- Yalnızca ekleme depolama.
- Kayıtların kriptografik karması (bağlı liste / Merkle).
- Canlı tercih deposundan bağımsız saklama.
- En uzun geçerli zamanaşımı süresine ve Madde 5(2) kapsamında hesap verebilirliği göstermek için uygun saklama — genellikle 3–5 yıl.
- Denetim otoritesi talebinde CSV / JSON'a aktarım.

Örnek denetim sorgusu: "2024-01-01'den bu yana authenticated_id=12345 kullanıcısının her onay kararını gösterin."

Log şu sorulara yanıt vermelidir:

- Ne sorduk?
- Kullanıcı ne seçti?
- Ne zaman?
- Hangi CMP sürümü üzerinden?
- Kullanıcı seçimi değiştirdi veya geri çekti mi?

### 7. Yenileme ve Yeniden Onay

Banner'ı yeniden gösterin (onayı yenileyin) şu durumlarda:

- Bildirim metni önemli değiştiğinde.
- Önceki onayın kapsamadığı yeni amaçlar veya tedarikçiler eklendiğinde.
- Onay 12–13 aydan eski olduğunda (CNIL rehberi: yıllık yenileme).
- Kullanıcı tarayıcı çerezlerini temizlediğinde (durum yeniden inşa edilir; yeni ziyaretçi olarak ele alınır).

### 8. Mobil Uygulama Onayı

Uygulama içi onayda ek değerlendirmeler vardır:

- Uygulama mağazası politikaları (Apple ATT, Google Play Veri Güvenliği) ek ifşa gereksinimleri getirir.
- Onay uygulama içi ayarlardan tekrar alınabilir olmalıdır.
- Apple ATT izni, IDFA'nın çapraz uygulama izleme için kullanımı için geçerlidir; bu GDPR onayından ayrıdır ancak çoğu zaman birlikte çalışır.
- SDK onay kapısı teknik olarak zorlanmalıdır (onaydan önce SDK'yı başlatmayın).

### 9. Sunucu Tarafı ve Arka Uç Onayı

Reklam ve analitik giderek sunucu tarafı uç noktalardan akıyor. CMP entegrasyonu onay durumunu şuralara yaymalıdır:

- Sunucu tarafı Google Tag Manager.
- Müşteri veri platformu (Segment, RudderStack).
- Arka uç pazarlama otomasyonu.
- Reklam kitlelerine besleyen veri ambarı pipeline'ları.

Onay verilmediyse, tüm aşağı akış zinciri veriyi düşürmelidir.

### 10. Tedarikçi Durum Tespiti

Bir CMP entegre etmeden önce:

- IAB TCF v2.2 uyumluluğunu doğrulayın (uygulanabilir yerlerde).
- CMP'nin DPA'nız altında veri işleyen olarak onay kayıtlarını işlediğini doğrulayın.
- Log saklama ve değiştirilemezlik özelliklerini doğrulayın.
- Tedarikçi başına ayrıntılı onay desteğini doğrulayın.
- Karanlık desen denetimleri / sertifikalarını doğrulayın.
- Performans etkisini ve erişilebilirliği doğrulayın.
- Yardımcı teknoloji dahil gerçek cihaz ve tarayıcılarda test edin.

### 11. Test Sıklığı

| Test | Sıklık | Sahip |
|------|--------|-------|
| Banner ilk ziyarette görüntülenir | Üç aylık | Pazarlama Ops |
| Reddet-tümü yolu belirtildiği gibi çalışır | Üç aylık | DPO |
| Ayrıntılı geçişler teknik gerçekle eşleşir (kapalıyken etiket çalışmaz) | Üç aylık | DPO + Mühendislik |
| TCF string'i çözüldü ve doğrulandı | Üç aylık | Mühendislik |
| Onay kayıtları talep üzerine aktarılabilir | Yıllık + talep üzerine | DPO |
| Yeni tedarikçi eklendi → banner yeniden göster | Değişiklikte | Pazarlama Ops |
| Çapraz tarayıcı, çapraz cihaz testi (masaüstü, mobil, tablet) | Altı aylık | QA |
| Erişilebilirlik (ekran okuyucu, klavye) | Altı aylık | Erişilebilirlik lideri |

### 12. Yaygın Başarısızlık Modları

1. Etiketler onay verilmeden önce çalışır (yarış koşulu).
2. Reklam tedarikçileri için varsayılan açık "Meşru menfaat" geçişleri.
3. "Özelleştir" altında gizli reddet-tümü.
4. Oturum açmış kullanıcılar için onay durumu cihazlar arasında senkronize değil.
5. CMP, ana analitik etiketinden sonra yüklenir — analitik onaydan önce çalışır.
6. Geri çekme yolu e-posta gerektirir — vermek kadar kolay değil.
7. Onay kayıtları bildirim metninin sürümünü içermiyor.
8. Yeniden gösterme mantığı bozuk; önemli değişiklikten sonra kullanıcılar yeniden istem almıyor.
9. Çerez tarayıcı güncel değil; sınıflandırma yapılmadan yeni etiketler tanıtıldı.
10. Mobil uygulama onay kapısı yalnızca UI gizlemeye dayanır, SDK başlatmasına değil.
