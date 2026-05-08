---
Doküman: Kişisel Veri İşleme Envanteri (KVKİ) Hazırlama Rehberi
Bölüm: 02-envanter-ve-sicil
Sahip: KVKK Sorumlusu
Onaylayan: Hukuk Müdürü + KVKK Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (yeni süreç, yeni sistem, M&A, mevzuat değişikliği)
İlgili Mevzuat: 6698 sayılı KVKK m.5, m.6, m.7, m.10, m.12, m.16; Veri Sorumluları Sicili Hakkında Yönetmelik MADDE 4(h), 5(ç), 5(d), 9; Aydınlatma Tebliği MADDE 4-5; Saklama ve İmha Yönetmeliği MADDE 5
---

# Kişisel Veri İşleme Envanteri (KVKİ) Rehberi

## 1. Tanım ve Hukuki Dayanak

### 1.1 Tanım

Veri Sorumluları Sicili Hakkında Yönetmelik MADDE 4(1)(h)'de Kişisel Veri İşleme Envanteri şu şekilde tanımlanmıştır:

> "Veri sorumlularının iş süreçlerine bağlı olarak gerçekleştirmekte oldukları kişisel veri işleme faaliyetlerini; kişisel veri işleme amaçları, veri kategorisi, aktarılan alıcı grubu ve veri konusu kişi grubuyla ilişkilendirerek oluşturdukları ve kişisel verilerin işlendikleri amaçlar için gerekli olan azami süreyi, yabancı ülkelere aktarımı öngörülen kişisel verileri ve veri güvenliğine ilişkin alınan tedbirleri açıklayarak detaylandırdıkları envanteri" ifade eder.

Bu tanım kelime kelime envanter satırlarının zorunlu sütunlarını üretir:

| Tanım unsuru | Envanter sütununa karşılık |
|--------------|---------------------------|
| iş süreçleri | Süreç adı, iş birimi |
| kişisel veri işleme amaçları | İşleme amacı |
| veri kategorisi | Veri kategorisi (kimlik, iletişim, finans vb.) |
| veri konusu kişi grubu | Veri konusu kişi grubu (çalışan, müşteri, ziyaretçi vb.) |
| aktarılan alıcı grubu | Alıcı/alıcı grubu (yurt içi+yurt dışı) |
| azami süre | Saklama süresi |
| yabancı ülkelere aktarım | Yurt dışı aktarım kolonu |
| güvenlik tedbirleri | Teknik ve idari tedbirler |

### 1.2 Hukuki Dayanak ve Bağlam

| Mevzuat hükmü | Anlamı |
|---------------|--------|
| Yön. M.5(ç) | "Sicil başvurularında Sicile açıklanacak bilgiler Kişisel Veri İşleme Envanterine **dayalı olarak** hazırlanır." |
| Yön. M.5(d) | Aydınlatma yükümlülüğü, ilgili kişi başvuruları ve açık rızanın kapsamının belirlenmesinde **envantere dayalı** Sicil bilgileri esas alınır. |
| Yön. M.9(2) | Sicile açıklanacak amaç, kategori, kişi grubu, alıcı, yurt dışı aktarım bilgileri envantere dayalı olarak VERBİS başlıkları kullanılarak iletilir. |
| Yön. M.9(5) | Azami sürenin belirlenmesi ve takibi için saklama-imha politikası **envantere dayalı** olarak hazırlanır. |
| Saklama ve İmha Yön. M.5 | Saklama ve imha politikası **kişisel veri işleme envanterine uygun olarak** hazırlanır. |

**Sonuç:** KVKİ, KVKK uyum çatısının operasyonel kalbidir. Aydınlatma, açık rıza, saklama-imha, aktarım, ilgili kişi başvurusu cevabı — hepsi envanterden beslenir.

## 2. Envanter İçeriği — Zorunlu Alanlar

Bir envanter satırı **bir süreç × bir veri konusu kişi grubu** kombinasyonunu temsil eder. Aynı süreçte birden fazla kişi grubu varsa (örn. işe alım sürecinde "aday" + "referans veren"), her kombinasyon ayrı satır olur.

### 2.1 Asgari Kolon Seti

| # | Kolon | Açıklama |
|---|-------|----------|
| 1 | Süreç ID | Tekil tanımlayıcı (örn. IK-001, MUS-002) |
| 2 | Süreç adı | Operasyonel adı (örn. "Çalışan Adayı İşe Alım") |
| 3 | İş birimi | Süreç sahibi birim (örn. "İnsan Kaynakları") |
| 4 | Süreç sahibi | Adı, unvanı, e-postası |
| 5 | Veri konusu kişi grubu | Çalışan, çalışan adayı, müşteri, potansiyel müşteri, tedarikçi çalışanı, ziyaretçi, çocuk, vb. |
| 6 | Veri kategorisi | Kimlik, İletişim, Finans, Özel nitelikli (sağlık, ceza mahkumiyeti vb.), Müşteri işlem, İşlem güvenliği, Lokasyon, Görsel/işitsel, Mesleki deneyim, Hukuki işlem, Pazarlama, Risk yönetimi |
| 7 | Kişisel veri öğeleri | Detay liste: ad-soyad, T.C. kimlik, doğum tarihi, IBAN, IP adresi, sağlık raporu vb. |
| 8 | Özel nitelikli veri (E/H) | KVKK m.6 kapsamına giriyor mu? |
| 9 | İşleme amacı | Belirli, açık, meşru amaç (KVKK m.4(2)/c). Birden fazla amaç ayrı satıra bölünür ya da çoklu amaç olarak yazılır. |
| 10 | Hukuki sebep | KVKK m.5(2) bentleri (a-f), m.6(2)-(3) bentleri ya da **Açık Rıza** (m.5(1) / m.6(2) ilk cümle) |
| 11 | Toplama yöntemi | Otomatik / Otomatik olmayan / Karma; kanal: web formu, kağıt başvuru, mobil app, çağrı merkezi, iş ortağı, kamera vb. |
| 12 | Kayıt ortamı | Elektronik (veritabanı, dosya sunucusu, e-posta, bulut), Fiziksel (dolap, arşiv), Karma |
| 13 | Veri aktarımı yapılan iç birim | Hangi birimlerle paylaşılıyor |
| 14 | Yurt içi alıcı / alıcı grubu | Yetkili kamu kurumları, iş ortakları, tedarikçiler, hukuk büroları, denetçiler, vb. |
| 15 | Yurt dışı aktarım (E/H) | Aktarım var mı? |
| 16 | Yurt dışı alıcı | Şirket adı, ülke (örn. Microsoft Azure, İrlanda) |
| 17 | Yurt dışı aktarım hukuki temeli | KVKK m.9: Yeterlilik kararı / Standart sözleşme / Bağlayıcı şirket kuralları / Taahhütname + Kurul izni / Arızi haller / Açık rıza |
| 18 | Saklama süresi | Sayısal (örn. "İş ilişkisi sona ermesinden itibaren 10 yıl") |
| 19 | Saklama süresi gerekçesi | Mevzuat referansı (TBK, TTK, VUK, SGK Kanunu vb.) ya da iş ihtiyacı + zamanaşımı analizi |
| 20 | İmha yöntemi | Silme / Yok etme / Anonim hale getirme |
| 21 | İmha periyodu | Periyodik imha takvimi (azami 6 ay) |
| 22 | Teknik tedbirler | Şifreleme, erişim logu, MFA, ağ segmentasyonu, sızma testi, vb. |
| 23 | İdari tedbirler | Eğitim, gizlilik taahhütnamesi, erişim yetkilendirme, sözleşme hükümleri, vb. |
| 24 | Risk seviyesi | Düşük / Orta / Yüksek / Kritik (özel nitelikli + büyük hacim → yüksek/kritik) |
| 25 | İlgili aydınlatma metni | Atıf veya bağlantı |
| 26 | Açık rıza gerekli mi? | E/H + gerekçe |
| 27 | Son güncelleme tarihi + güncelleyen | Versiyon takibi |

> Not: Yön. M.9(4) gereği, mevzuatta bir saklama süresi öngörülmüş ise o süre, yoksa farklı sürelerden **en uzunu** esas alınır.

### 2.2 Hukuki Sebep Tabanı (KVKK m.5/m.6)

Envanter satırı yazılırken **her amaç için açık ve tek bir hukuki sebep** belirlenmelidir. Açık rıza son çare olarak değerlendirilir; başka bir hukuki sebep varsa açık rıza alınmaz.

**Genel kişisel veri (KVKK m.5/2):**
- a) Kanunlarda açıkça öngörülmesi
- b) Fiili imkansızlık nedeniyle rızasını açıklayamayacak kişinin korunması
- c) Sözleşmenin kurulması veya ifasıyla doğrudan ilgili olması
- ç) Hukuki yükümlülüğün yerine getirilmesi
- d) İlgili kişinin kendisi tarafından alenileştirilmiş olması
- e) Bir hakkın tesisi, kullanılması veya korunması
- f) Meşru menfaate dayalı, ilgili kişinin temel hak ve özgürlüklerine zarar vermemek kaydıyla

**Özel nitelikli kişisel veri (KVKK m.6/3):**
- Sağlık ve cinsel hayat → kamu sağlığının korunması, koruyucu hekimlik, tıbbi teşhis, tedavi ve bakım hizmetlerinin yürütülmesi, sağlık hizmetleri ile finansmanının planlanması ve yönetimi (sır saklama yükümlülüğü altındakiler)
- Diğer özel nitelikli veriler → kanunlarda öngörülen hallerde

## 3. Envanter Çıkarma Metodolojisi

### 3.1 Beş Aşamalı Yaklaşım

```
1. Süreç Keşfi  →  2. Veri Akışı Haritalama  →  3. Hukuki Analiz  →  4. Doğrulama  →  5. Versiyonlama
```

#### Aşama 1 — Süreç Keşfi

**Üç paralel kanaldan bilgi toplama:**

| Kanal | Yöntem | Çıktı |
|-------|--------|-------|
| Mülakat | Birim yöneticileri ile 60-90 dk yapılandırılmış mülakat | Süreç haritası taslağı |
| Sistem taraması | CMDB, AD, AWS/Azure inventory, SaaS console listesi | Veri tutan sistem listesi |
| Anket | Süreç sahiplerine yapılandırılmış form (Google Forms, MS Forms) | Süreç başına standart cevaplar |

**Mülakat soruları (örnek):**
1. Sürecinizde hangi kişi gruplarına ait veri işliyorsunuz?
2. Hangi sistemler kullanılıyor (in-house, SaaS, dış kaynak)?
3. Veri nasıl alınıyor (form, API, kağıt, ses kaydı, CCTV)?
4. Hangi verileri başka bir birim, kurum veya tedarikçi ile paylaşıyorsunuz?
5. Yurt dışına veri aktarımınız var mı? (SaaS sunucuları yurt dışındaysa evet)
6. Verileri ne kadar süre saklıyorsunuz? Neden?
7. Geçmişte yaşanan veri ihlali, kayıp veya yetkisiz erişim oldu mu?

#### Aşama 2 — Veri Akışı Haritalama

Süreç başına **veri akış diyagramı** çıkarın:

```
[Toplama Kaynağı] → [Aktif Sistem(ler)] → [Yedek/Arşiv] → [Aktarım Alıcıları] → [İmha]
```

Her ok için: hangi veriler hareket ediyor, kim erişiyor, hangi güvenlik tedbiriyle korunuyor.

#### Aşama 3 — Hukuki Analiz

Her süreç için Hukuk Müdürlüğü ile birlikte:
- Amaçların belirli, açık, meşru olduğunun teyidi (KVKK m.4)
- Hukuki sebebin tespiti (m.5/m.6)
- Saklama sürelerinin mevzuatla uyumlandırılması
- Aktarım rejiminin tespiti (m.8/m.9)
- Açık rıza gerekliliği değerlendirmesi

#### Aşama 4 — Doğrulama Atölyesi

Hazırlanan envanter satırlarını süreç sahibi + KVKK Sorumlusu + Bilgi Güvenliği + Hukuk birlikte gözden geçirir. Tipik atölye süresi: süreç başına 30-45 dk.

#### Aşama 5 — Versiyonlama

Envanter, sürüm kontrollü bir sistemde tutulur (Git, OneDrive sürüm geçmişi, OneTrust kayıt geçmişi). Her satır için son güncelleme tarihi ve güncelleyen kişi zorunludur.

### 3.2 Atölye Çalışması Çıktı Şablonu

```
Atölye: [Süreç Adı]
Tarih: YYYY-AA-GG
Katılımcılar: [İsim, Rol]
Karar: [Onaylandı / Revizyon gerekli]
Açık konular:
  - [Hukuki sebebin teyidi gerekiyor]
  - [Saklama süresi için Hukuk görüşü beklenecek]
Aksiyon listesi: ...
```

## 4. Şirketimiz İçin Tipik Süreç Listesi

500+ çalışanlı bir veri sorumlusu için minimum kapsam:

### 4.1 İnsan Kaynakları

| ID | Süreç |
|----|-------|
| IK-001 | Çalışan adayı işe alım ve özgeçmiş yönetimi |
| IK-002 | İşe başlatma ve özlük dosyası oluşturma |
| IK-003 | Bordro ve maaş ödemeleri |
| IK-004 | Performans değerlendirme |
| IK-005 | Eğitim ve gelişim |
| IK-006 | İzin ve devam-devamsızlık takibi |
| IK-007 | İş sağlığı ve güvenliği (sağlık raporları, kazalar) — özel nitelikli |
| IK-008 | Disiplin ve etik soruşturma |
| IK-009 | İşten çıkış ve özlük arşivi |
| IK-010 | Çalışan referans verme |

### 4.2 Müşteri ve Satış

| ID | Süreç |
|----|-------|
| MUS-001 | Müşteri kayıt ve hesap açılışı |
| MUS-002 | E-ticaret sipariş yönetimi |
| MUS-003 | Faturalama ve tahsilat |
| MUS-004 | Müşteri şikayet ve geri bildirim |
| MUS-005 | Çağrı merkezi (sesli kayıt) |
| MUS-006 | Pazarlama, kampanya ve newsletter (İYS uyumu) |
| MUS-007 | CRM ve müşteri 360° profili |
| MUS-008 | Sadakat ve puan programı |

### 4.3 Operasyon ve Lojistik

| ID | Süreç |
|----|-------|
| OPR-001 | Tedarikçi yönetimi (tedarikçi çalışanı verisi) |
| OPR-002 | Teslimat ve lojistik (kurye, alıcı verisi) |
| OPR-003 | Satınalma ve sözleşme yönetimi |

### 4.4 Bilgi Teknolojileri ve Güvenlik

| ID | Süreç |
|----|-------|
| BT-001 | Kullanıcı kimlik ve erişim yönetimi (IAM/AD) |
| BT-002 | Loglama ve SIEM |
| BT-003 | Yedekleme ve felaket kurtarma |
| BT-004 | Bulut hizmet sağlayıcıları (yurt dışı aktarım) |
| BT-005 | Çağrı merkezi yazılım entegrasyonu |
| BT-006 | Çerez ve dijital takip |

### 4.5 Fiziksel Güvenlik ve İdari

| ID | Süreç |
|----|-------|
| FIZ-001 | CCTV (kapalı devre kamera sistemi) |
| FIZ-002 | Ziyaretçi yönetimi (giriş kaydı, kart) |
| FIZ-003 | Fiziksel arşiv yönetimi |
| FIZ-004 | İç denetim ve uyum |

### 4.6 Hukuk ve Uyum

| ID | Süreç |
|----|-------|
| HUK-001 | Hukuki uyuşmazlık ve dava yönetimi |
| HUK-002 | Etik ihbar hattı (whistleblowing) |
| HUK-003 | KVKK ilgili kişi başvuru yönetimi |
| HUK-004 | Veri ihlali yönetimi |

### 4.7 Finans

| ID | Süreç |
|----|-------|
| FIN-001 | Muhasebe ve cari hesap |
| FIN-002 | Vergi beyanı |
| FIN-003 | Banka ve ödeme sistemleri |

### 4.8 Pazarlama ve İletişim

| ID | Süreç |
|----|-------|
| PAZ-001 | Web sitesi analitiği ve çerezler |
| PAZ-002 | Sosyal medya ve kampanya yönetimi |
| PAZ-003 | İYS (İleti Yönetim Sistemi) ticari elektronik ileti |

> 500+ çalışanlı bir kuruluş için tipik envanter satır sayısı **80-150 arasıdır**. 50'nin altı çıkıyorsa keşif eksik kalmıştır.

## 5. Versiyonlama, Sahiplik ve Değişiklik Yönetimi

### 5.1 Versiyon Numaralandırması

Semantik sürüm: `MAJOR.MINOR.PATCH`
- MAJOR: Mimari değişim (yeni kolon, yeni süreç ailesi)
- MINOR: Yeni süreç satırı eklenmesi, mevcut satırın anlamlı revizyonu
- PATCH: Yazım düzeltmeleri, küçük güncellemeler

### 5.2 Çift Sahiplik Modeli

Her satır için iki sahiplik:
- **Süreç sahibi (iş birimi):** içerik doğruluğundan sorumlu
- **KVKK Sorumlusu:** hukuki uyum ve VERBİS yansımasından sorumlu

### 5.3 Değişiklik Tetikleyicileri

| Tetikleyici | Aksiyon |
|-------------|---------|
| Yeni süreç başlatılması | Süreç başlamadan önce envanter satırı + VERBİS güncelleme |
| Yeni sistem/SaaS devreye alınması | Veri akışı, aktarım, yurt dışı kontrolü; envanter güncelleme |
| Yeni tedarikçi (veri işleyen) | Aktarım kolonu güncelleme + sözleşme |
| Mevzuat değişikliği | İlgili satırlarda hukuki sebep ve saklama süresinin yeniden değerlendirilmesi |
| Organizasyonel değişim (birleşme, devir, M&A) | Tüm envanterin gözden geçirilmesi |
| Veri ihlali | Etkilenen sürecin tedbirler kolonunun güncellenmesi |

> Yön. M.13: VERBİS'te kayıtlı bilgilerde değişiklik halinde **7 gün** içinde bildirim. Bu nedenle envanter güncellemeleri "ay sonu işi" değildir; süreç değiştiğinde anlık güncellenmelidir.

## 6. Araç Önerisi

### 6.1 Excel/CSV (Başlangıç düzeyi)

- **Artıları:** Düşük maliyet, hızlı başlangıç, geniş erişim.
- **Eksileri:** Sürüm kontrolü zayıf, çok kullanıcılı çalışmada çakışma, otomatik hatırlatıcı yok.
- **Öneri:** OneDrive/SharePoint üzerinde tek master kopya, salt okunur paylaşım, değişiklik için pull request mantığı.

### 6.2 KVKK/Privacy Yazılımları

| Araç | Uygunluk |
|------|---------|
| OneTrust Data Mapping | Büyük kurum, sertifikasyon ihtiyacı |
| BigID | Hassas veri keşfi + envanter |
| Yerel Türk yazılımları (Lostar, KVKK Manager vb.) | Yerel destek, KVKK uyumlu şablon |
| Confluence + JIRA | İç wiki + ticket entegrasyonu (orta ölçek) |

### 6.3 CMDB Entegrasyonu

Bilgi İşlem'in CMDB'sinde sistem listesi varsa, envanter satırlarındaki "kayıt ortamı" kolonunu sistem ID'leriyle eşlemek; sistem tarafında değişiklik olduğunda uyarı kuralı kurmak.

## 7. Yaygın Hatalar ve Kontroller

| Hata | Düzeltme |
|------|----------|
| Hukuki sebep "rıza" yazılmış ancak başka hukuki sebep mevcut | Açık rıza son çaredir; uygun bent seçilir |
| Saklama süresi "ihtiyaç oldukça" yazılmış | Belirli, sayısal süre + gerekçe zorunlu |
| Yurt dışı aktarım kolonu boş, ancak SaaS yurt dışı | SaaS sunucu lokasyonları kontrol edilir, evet/hayır netleştirilir |
| "Tüm çalışanlar erişiyor" | Erişim yetkilendirmesi rol bazlı yapılır, prensip "need to know" |
| Aydınlatma metni envanter ile uyumsuz | Çeyreklik uyum kontrolü zorunlu (bkz. envanter-bakim.md) |
| Birden fazla amaç tek satıra sıkıştırılmış | Her amaç için hukuki sebep farklı olabileceğinden ayrı satır önerilir |
| Risk seviyesi belirtilmemiş | Tüm satırlar için risk değerlendirmesi zorunlu |

## 8. Envanter Olgunluk Modeli

| Seviye | Tanım | Tipik gösterge |
|--------|-------|----------------|
| 1 - Başlangıç | Excel'de listeleme | 30+ satır, ancak kolonlar eksik |
| 2 - Yapılandırılmış | Tüm zorunlu kolonlar dolu | VERBİS bildirimi yapılmış |
| 3 - Operasyonel | Çeyreklik gözden geçirme aktif | Süreç sahibi imzalı |
| 4 - Entegre | Aydınlatma + rıza + saklama metni envanterden üretiliyor | Tek kaynak doğruluk |
| 5 - Optimize | CMDB/SaaS ile otomatik bağ, gerçek zamanlı izleme | Veri akışı haritası canlı |

Hedef olgunluk seviyesi: **4 (Entegre)** içinde 18 ay. Seviye 5 isteğe bağlıdır.

## 9. Kontrol Listesi (Yeni Süreç)

- [ ] Süreç ID atandı (şirket içi naming convention)
- [ ] Süreç sahibi belirlendi ve onayladı
- [ ] Tüm 27 kolon dolduruldu
- [ ] Hukuki sebep KVKK m.5/m.6 bentlerinden seçildi
- [ ] Saklama süresi mevzuat veya zamanaşımı analiziyle gerekçelendirildi
- [ ] Yurt içi ve yurt dışı alıcılar listelendi
- [ ] Yurt dışı varsa hukuki temel belirlendi (m.9)
- [ ] Aydınlatma metni hazırlandı veya mevcut metne bağlantı verildi
- [ ] Açık rıza gerekiyorsa metni ve toplama kanalı hazır
- [ ] Teknik ve idari tedbirler doldurmuş, Bilgi Güvenliği teyit etti
- [ ] Risk seviyesi belirlendi (özel nitelikli + büyük hacim → minimum yüksek)
- [ ] VERBİS güncelleme planlandı (7 gün)
- [ ] Saklama-imha politikası ile uyumlu
- [ ] Versiyon numarası ve güncelleyen kayda geçti

## 10. Ekler

- Şablon: [envanter-sablonu.md](./envanter-sablonu.md)
- VERBİS Kayıt: [verbis-kayit-rehberi.md](./verbis-kayit-rehberi.md)
- İstisna Değerlendirme: [verbis-istisna-degerlendirmesi.md](./verbis-istisna-degerlendirmesi.md)
- Bakım: [envanter-bakim.md](./envanter-bakim.md)
