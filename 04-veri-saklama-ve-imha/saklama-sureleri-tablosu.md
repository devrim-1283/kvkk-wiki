---
Doküman: Kişisel Veri Saklama Süreleri Tablosu
Bölüm: 04-veri-saklama-ve-imha
Sahip: KVKK Sorumlusu
Onaylayan: Hukuk Müdürü + Bilgi Güvenliği Yöneticisi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (mevzuat değişikliği, yeni iş süreci, dava süresi tetiklemesi)
İlgili Mevzuat: KVKK m.4(2)(d), m.7; Yön. m.6/1-g; 4857 İş K. m.75; 213 VUK m.253; 6102 TTK m.82; 6098 TBK m.146-147; 5510 SGK Kanunu; 5651 Kanun; 6502 Tüketici K.; 6493 Ödeme Hizmetleri K.; 5549 MASAK K.
---

# Kişisel Veri Saklama Süreleri Tablosu

## 1. Tablonun Kullanımı

- **Asgari süre:** Mevzuatın açıkça öngördüğü veya hak/dava zamanaşımı nedeniyle saklanması zorunlu olan süre.
- **Azami süre:** Bu sürenin sonunda veriler periyodik imha kapsamına girer; tutulması ancak somut bir hukuki sebebe dayanırsa mümkündür.
- Süre, **veri kategorisinin türetildiği işleme amacının sona erdiği tarih**ten itibaren işler. Ör. iş ilişkisi sona erdiğinde özlük dosyası süresi başlar.
- Sürenin uzaması ancak somut **legal hold** (devam eden dava, denetim, soruşturma) ile ve KVKK Sorumlusu + Hukuk Müdürü ortak kararıyla mümkündür.
- Çakışan birden fazla mevzuat varsa **en uzun süre** uygulanır.

## 2. Süre Kararı Algoritması

```
+------------------------------------------+
| Veri kategorisi belirlendi               |
+------------------------------------------+
              |
              v
+------------------------------------------+
| Mevzuatta açık süre var mı?              |
+------------------------------------------+
       |                       |
   evet|                    hayır|
       v                       v
+--------------+    +--------------------------+
| Mevzuat      |    | Hak veya dava zamanaşımı |
| süresini     |    | uygulanabilir mi?        |
| uygula       |    +--------------------------+
+--------------+         |              |
       |             evet|           hayır|
       |                 v               v
       |    +--------------+   +-------------------+
       |    | Zamanaşımını |   | İşleme amacının   |
       |    | uygula       |   | gerektirdiği süre |
       |    +--------------+   +-------------------+
       |                 |              |
       v                 v              v
+------------------------------------------+
| Legal hold var mı?                       |
+------------------------------------------+
              |
       evet (legal hold süresince uzat)
              |
              v
+------------------------------------------+
| Süre sonunda imha takvimi                |
+------------------------------------------+
```

## 3. Süre Tablosu (Veri Kategorisi Bazlı)

> Süreler, ülkemizde 500+ çalışanlı kurumsal yapılarda yaygın uygulamadır. Sektörel mevzuat (BDDK, SPK, EPDK, Sağlık Bakanlığı vb.) saklı kalmak üzere, kurum kendi durumuna uyarlamalıdır.

### 3.1. İnsan Kaynakları

| # | Veri Kategorisi | Hukuki Sebep | Mevzuat Dayanağı | Asgari Süre | Azami Süre | İmha Yöntemi | Sahibi |
|---|-----------------|--------------|------------------|-------------|------------|--------------|--------|
| 1 | Çalışan özlük dosyası (kimlik, ikamet, diploma, sözleşme) | Sözleşmenin ifası + hukuki yükümlülük | 4857 İş K. m.75 (10 yıl), 6098 TBK m.146 (10 yıl) | İş ilişkisinin bitiminden itibaren 10 yıl | 10 yıl | Kağıt: shredder + tutanak; Elektronik: hard-delete + log temizliği | İK |
| 2 | Bordro, ücret hesabı, kesinti belgeleri | Hukuki yükümlülük | 213 VUK m.253 (5 yıl), 4857 İş K. m.75; SGK 10 yıl | İlgili dönemden itibaren 10 yıl | 10 yıl | Kağıt: shredder; Elektronik: hard-delete | İK + Mali İşler |
| 3 | SGK işe giriş/çıkış bildirgeleri, hizmet dökümleri | Hukuki yükümlülük | 5510 SGK m.86 | İş ilişkisinin bitiminden itibaren 10 yıl | 10 yıl | Kağıt: shredder; Elektronik: hard-delete | İK |
| 4 | İş kazası ve meslek hastalığı kayıtları | Hukuki yükümlülük + dava ihtimali | 6331 İSG K. m.14, 6098 TBK m.146 | Olayın bildiriminden itibaren 15 yıl (uzun zamanaşımı) | 15 yıl | Kağıt: shredder; Elektronik: hard-delete | İK + İSG |
| 5 | Performans değerlendirme, eğitim, disiplin kayıtları | Sözleşmenin ifası + meşru menfaat | 4857 İş K. genel | İş ilişkisinin bitiminden itibaren 10 yıl | 10 yıl | Elektronik: hard-delete | İK |
| 6 | İşe alım sürecinde reddedilen aday başvuruları (CV, mülakat notu) | Açık rıza + meşru menfaat (gelecek pozisyon değerlendirmesi) | KVKK m.5/2 | Pozisyonun kapanması + 6 ay; açık rıza varsa azami **2 yıl** | 2 yıl | Elektronik: hard-delete; Kağıt: shredder | İK |
| 7 | İş başvurusu ile gelen referans bilgileri | Sözleşme öncesi tedbir + meşru menfaat | KVKK m.5/2 | İşe alımda işe başlamadan 6 ay; reddedilende başvuru ile birlikte | 2 yıl | Elektronik: hard-delete | İK |
| 8 | Çalışan sağlık raporları (özel nitelikli) | İSG yükümlülüğü | 6331 İSG K., Sağlık Personeli Kanunu | İş ilişkisinin bitiminden itibaren 15 yıl | 15 yıl | Kapalı zarflı arşiv → tutanaklı imha | İşyeri Hekimi + İK |
| 9 | Çalışan biyometrik kayıt (parmak izi, yüz tanıma) | Açık rıza (özel nitelikli) | KVKK m.6/2 | İş ilişkisinin bitiminden itibaren **derhal** imha; uzun saklama yasaktır | İlişki sonu | Elektronik: kripto-silme + log | İK + Bilgi Güvenliği |

### 3.2. Müşteri ve Sözleşme

| # | Veri Kategorisi | Hukuki Sebep | Mevzuat Dayanağı | Asgari Süre | Azami Süre | İmha Yöntemi | Sahibi |
|---|-----------------|--------------|------------------|-------------|------------|--------------|--------|
| 10 | Müşteri sözleşmesi ve ekleri (gerçek kişi/yetkili) | Sözleşmenin ifası + hukuki yükümlülük + zamanaşımı | 6098 TBK m.146 (10 yıl), 6102 TTK m.82 (10 yıl, ticari saklama) | Sözleşmenin sona ermesinden itibaren 10 yıl | 10 yıl | Kağıt: shredder; Elektronik: hard-delete + yedek imhası | Hukuk + İlgili Birim |
| 11 | Cari hesap, fatura, irsaliye | Hukuki yükümlülük | 213 VUK m.253 (5 yıl), 6102 TTK m.82 (10 yıl) | İlgili dönemden itibaren 10 yıl | 10 yıl | Kağıt: shredder; Elektronik: hard-delete | Mali İşler |
| 12 | Müşteri iletişim bilgileri (CRM kayıtları) | Sözleşmenin ifası + meşru menfaat | KVKK m.5/2-c, f | Sözleşme bitişinden 10 yıl; ticari elektronik ileti rızası ayrıca yönetilir | 10 yıl | Elektronik: hard-delete | Pazarlama + Satış |
| 13 | Tüketici şikayetleri ve cevapları | Hukuki yükümlülük | 6502 Tüketici K. m.68 (zamanaşımı) | Şikayet kapanmasından itibaren 5 yıl | 5 yıl | Elektronik: hard-delete; Kağıt: shredder | Müşteri Hizmetleri |

### 3.3. Mali ve Vergisel

| # | Veri Kategorisi | Hukuki Sebep | Mevzuat Dayanağı | Asgari Süre | Azami Süre | İmha Yöntemi | Sahibi |
|---|-----------------|--------------|------------------|-------------|------------|--------------|--------|
| 14 | Faturalar, defterler, beyannameler | Hukuki yükümlülük | 213 VUK m.253 (5 yıl); 6102 TTK m.82 (10 yıl) | İlgili dönemden itibaren 10 yıl | 10 yıl | Kağıt: shredder + yakma; Elektronik: hard-delete | Mali İşler |
| 15 | E-fatura, e-defter, e-arşiv kayıtları | Hukuki yükümlülük | 213 VUK Tebliğleri | İlgili dönemden itibaren 10 yıl | 10 yıl | Elektronik: hard-delete + yedek imhası | Mali İşler + BT |
| 16 | Banka hesap hareketleri, dekont | Hukuki yükümlülük + ticari saklama | 6102 TTK m.82 | İşlem tarihinden itibaren 10 yıl | 10 yıl | Kağıt: shredder; Elektronik: hard-delete | Mali İşler |
| 17 | Kart ödeme bilgisi (kart no, son kullanma) | Sözleşmenin ifası | BKM Kuralları, PCI-DSS | Yetkilendirmeden sonra **derhal** silme; PAN tutmak yasak; saklanırsa maskeleme + tokenizasyon | İşlem sonu | Tokenizasyon + kripto-silme | Ödeme/IT |
| 18 | İade, chargeback kayıtları | Hukuki yükümlülük + zamanaşımı | 6502 Tüketici K. | İşlem tarihinden 5 yıl | 5 yıl | Elektronik: hard-delete | Mali İşler |
| 19 | MASAK kapsamı kimlik tespiti (yükümlü kuruluşlarda) | Hukuki yükümlülük | 5549 MASAK K. m.6 | İlişki bitiminden 8 yıl | 8 yıl | Elektronik: hard-delete; Kağıt: shredder | Uyum |

### 3.4. E-Ticaret ve Pazarlama

| # | Veri Kategorisi | Hukuki Sebep | Mevzuat Dayanağı | Asgari Süre | Azami Süre | İmha Yöntemi | Sahibi |
|---|-----------------|--------------|------------------|-------------|------------|--------------|--------|
| 20 | E-ticaret sipariş kaydı (alıcı, ürün, fiyat, adres) | Sözleşmenin ifası + hukuki yükümlülük | 6502 Tüketici K., 6563 ETK | Sipariş tamamlanmasından 10 yıl (TTK ticari saklama) | 10 yıl | Elektronik: hard-delete | E-ticaret + Mali İşler |
| 21 | Üyelik / hesap bilgileri (ad, e-posta, telefon, parola hash'i) | Açık rıza / sözleşmenin ifası | KVKK m.5/2 | Hesabın silinmesi/feshinden 10 yıl (zamanaşımı) | 10 yıl | Elektronik: hard-delete | E-ticaret |
| 22 | Pazarlama izni (ETK İYS kaydı) | Açık rıza | 6563 ETK m.6 | İznin geri alınmasına kadar; geri alındıktan sonra ispat amaçlı **3 yıl** | 3 yıl (ret sonrası) | Elektronik: hard-delete | Pazarlama |
| 23 | Çerez verisi — zorunlu | Meşru menfaat | KVKK m.5/2-f | Oturum süresince | Oturum sonu | Tarayıcı tarafı + sunucu tarafı silme | Web/Pazarlama |
| 24 | Çerez verisi — analitik | Açık rıza | KVKK m.5/1 | Çerez politikasında belirtilen süre (genelde 13 ay) | 13 ay | Otomatik expiry | Web/Pazarlama |
| 25 | Çerez verisi — pazarlama / 3. taraf | Açık rıza | KVKK m.5/1 | Çerez politikasında belirtilen süre; rıza geri çekilince derhal | 13 ay | Otomatik expiry + rıza sonu | Web/Pazarlama |

### 3.5. Güvenlik ve İzleme

| # | Veri Kategorisi | Hukuki Sebep | Mevzuat Dayanağı | Asgari Süre | Azami Süre | İmha Yöntemi | Sahibi |
|---|-----------------|--------------|------------------|-------------|------------|--------------|--------|
| 26 | CCTV görüntü kayıtları (giriş-çıkış, ortak alan) | Meşru menfaat | KVKK m.5/2-f, m.10 aydınlatma şartı | Olay olmazsa 15-30 gün; olay halinde olay süresi sonuna kadar | 30 gün (rutin) | Otomatik üzerine yazma; olay sonrası kontrollü silme | Bilgi Güvenliği + Fiziksel Güvenlik |
| 27 | Çağrı merkezi ses kaydı | Sözleşmenin ifası + meşru menfaat (kalite, ihtilaf) | KVKK m.5/2-c, f | Çağrı tarihinden 1-3 yıl (delil); sektörel zorunluluk varsa daha uzun | 3 yıl (sektörel istisna saklı) | Elektronik: hard-delete + yedek imha | Çağrı Merkezi + BT |
| 28 | Web sunucu erişim logları (IP, URL, timestamp) | Hukuki yükümlülük | 5651 Kanun m.5, Yer Sağlayıcı Yönetmeliği | İşlem tarihinden 6 ay – 2 yıl (içerik/yer/erişim sağlayıcı niteliğine göre) | 2 yıl | Elektronik: hard-delete + log rotasyonu | BT |
| 29 | Sistem erişim logları, ayrıcalıklı işlem logları | Meşru menfaat (güvenlik, denetim) | KVKK m.12, ISO 27001 | En az 1 yıl; kritik sistemlerde 2-5 yıl | 5 yıl | Elektronik: hard-delete + SIEM rotasyonu | Bilgi Güvenliği |
| 30 | Firewall, IPS, EDR olay logları | Meşru menfaat | KVKK m.12 | En az 1 yıl | 2 yıl | Elektronik: hard-delete | Bilgi Güvenliği |
| 31 | DLP olay kayıtları | Meşru menfaat + ihlal yönetimi | KVKK m.12 | İhlal şüphesi yoksa 1 yıl; ihlalde forensic süresi sonuna kadar | 5 yıl | Elektronik: hard-delete | Bilgi Güvenliği |
| 32 | Ziyaretçi defteri (kağıt veya elektronik) | Meşru menfaat | KVKK m.5/2-f | Ziyaret tarihinden 2 yıl | 2 yıl | Kağıt: shredder; Elektronik: hard-delete | Fiziksel Güvenlik |

### 3.6. Yönetişim ve Uyum

| # | Veri Kategorisi | Hukuki Sebep | Mevzuat Dayanağı | Asgari Süre | Azami Süre | İmha Yöntemi | Sahibi |
|---|-----------------|--------------|------------------|-------------|------------|--------------|--------|
| 33 | KVKK ilgili kişi başvuru ve cevap kayıtları | Hukuki yükümlülük | KVKK m.13, Başvuru Tebliği | Başvurunun cevaplandığı tarihten 10 yıl (zamanaşımı) | 10 yıl | Elektronik: hard-delete | KVKK Sorumlusu |
| 34 | İhlal kayıt sistemi (KVKK m.12 ihlal kayıtları) | Hukuki yükümlülük | KVKK m.12, Kurul kararları | İhlalin kapanmasından sonra en az 5 yıl | 10 yıl | Elektronik: hard-delete | KVKK Sorumlusu + Bilgi Güvenliği |
| 35 | İmha tutanakları (Yön. m.7(3)) | Hukuki yükümlülük | Yön. m.7(3) | İşlemden sonra **en az 3 yıl** | 5 yıl (önerilir) | Kağıt: arşiv → shredder; Elektronik: hard-delete | KVKK Sorumlusu |
| 36 | Açık rıza ispat kayıtları | Hukuki yükümlülük (ispat yükü) | KVKK m.3, m.5/1 | İlişki süresi + 10 yıl (zamanaşımı) | 10 yıl | Elektronik: hard-delete | KVKK Sorumlusu + İlgili Birim |
| 37 | Aydınlatma metinleri sürüm arşivi | Hukuki yükümlülük (ispat) | KVKK m.10, Aydınlatma Tebliği | İlgili sürümün uygulanmadığı tarihten 10 yıl | 10 yıl | Sürümlü arşiv | KVKK Sorumlusu |
| 38 | VBİA / DPIA raporları | Meşru menfaat + denetim | KVKK m.12, Veri Güvenliği Rehberi | Risk değerlendirilen sürecin sona ermesinden 5 yıl | 5 yıl | Elektronik: hard-delete | KVKK Sorumlusu |

### 3.7. Tedarikçi ve Sözleşmeli Üçüncü Kişiler

| # | Veri Kategorisi | Hukuki Sebep | Mevzuat Dayanağı | Asgari Süre | Azami Süre | İmha Yöntemi | Sahibi |
|---|-----------------|--------------|------------------|-------------|------------|--------------|--------|
| 39 | Tedarikçi sözleşmesi ve ekleri (yetkili kişi bilgisi) | Sözleşmenin ifası + hukuki yükümlülük | 6098 TBK m.146, 6102 TTK m.82 | Sözleşmenin sona ermesinden 10 yıl | 10 yıl | Kağıt: shredder; Elektronik: hard-delete | Satınalma + Hukuk |
| 40 | Tedarikçi yetkili iletişim bilgileri | Sözleşmenin ifası | KVKK m.5/2-c | Sözleşmenin sona ermesinden 10 yıl | 10 yıl | Elektronik: hard-delete | Satınalma |
| 41 | Veri işleyen denetim raporları | Meşru menfaat + denetim | KVKK m.12 | Sözleşmenin sona ermesinden 5 yıl | 5 yıl | Elektronik: hard-delete | KVKK Sorumlusu + Satınalma |

### 3.8. Hukuki ve Kurumsal

| # | Veri Kategorisi | Hukuki Sebep | Mevzuat Dayanağı | Asgari Süre | Azami Süre | İmha Yöntemi | Sahibi |
|---|-----------------|--------------|------------------|-------------|------------|--------------|--------|
| 42 | Vekaletname (gerçek kişi) | Hukuki yükümlülük | TBK, ilgili mevzuat | Vekaletin sona ermesinden 10 yıl | 10 yıl | Kağıt: shredder | Hukuk |
| 43 | Şirket ortakları/yöneticileri kişisel verileri | Hukuki yükümlülük | 6102 TTK | Ortaklık/görev süresi + 10 yıl | 10 yıl | Elektronik: hard-delete | Hukuk + İK |
| 44 | Dava dosyaları (kişisel veri içerenler) | Hukuki yükümlülük | 6098 TBK m.146 | Karar kesinleşmesinden 10 yıl | 10 yıl | Kağıt: shredder; Elektronik: hard-delete | Hukuk |
| 45 | Genel Kurul, Yönetim Kurulu kayıtları (gerçek kişi bilgisi) | Hukuki yükümlülük | 6102 TTK | 10 yıl | 10 yıl | Kurumsal arşiv | Hukuk + Yönetim Kurulu Sekreteryası |

## 4. Süre İstisnaları

### 4.1. Legal Hold

Aşağıdaki durumlarda saklama süresi durdurulur ve verinin imhası ertelenir:

- Devam eden veya muhtemel dava (taraf veya delil),
- Yetkili merci (mahkeme, savcılık, BDDK, SPK, Rekabet Kurumu, Vergi Müfettişliği vb.) tarafından verilmiş tutma kararı,
- KVKK Kurulu tarafından başlatılmış inceleme,
- İhlal forensik incelemesi.

Legal hold uygulanan veri için:
- Hukuk Müdürü ve KVKK Sorumlusu ortak yazılı kararı düzenler,
- İlgili veri "hold" olarak işaretlenir, retention job'ları devre dışı bırakılır,
- Hold sebebi sona erdiğinde 30 gün içinde standart imha takvimine alınır,
- Hold süresi ve gerekçesi tutanağa işlenir.

### 4.2. Açık Rızanın Geri Alınması

Açık rızanın geri alınması ileriye yöneliktir; geri alma beyanının veri sorumlusuna ulaştığı andan itibaren işleme durdurulur. Başka bir hukuki dayanak yoksa veri imha edilir.

## 5. Tablo Bakım Disiplini

- Yıllık tarama: Hukuk Müdürlüğü ile mevzuat değişikliği taraması.
- Yeni süreç tetiklemesi: Yeni iş süreci başlatılmadan tabloya satır eklenir; envanter ve VERBİS güncellenir.
- Süre kısaltma: Kurul aksine karar verirse (Yön. m.11/4 — telafisi güç zarar veya açık hukuka aykırılık) süre kısaltılır.
- Süre uzatma: Sadece somut bir hukuki sebep + Hukuk Müdürlüğü onayı ile.
