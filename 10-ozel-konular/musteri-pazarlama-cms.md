---
Doküman: Müşteri ve Pazarlama Verisi Yönetimi (CRM, İYS, Profilleme)
Bölüm: 10-ozel-konular
Sahip: KVKK Sorumlusu + Pazarlama Direktörü + CRM Sahibi
Onaylayan: Hukuk Müdürü + KVKK Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + İYS / Kurul kararlarına göre
İlgili Mevzuat: 6698 sayılı KVKK m.5, m.11; 6563 sayılı E-Ticaret Kanunu; "Ticari İletişim ve Ticari Elektronik İletiler Hakkında Yönetmelik" (15.07.2015 / 29417); 6502 sayılı Tüketicinin Korunması Kanunu; KVKK Çerez Rehberi
---

# Müşteri ve Pazarlama Verisi Yönetimi

## 1. Amaç ve Kapsam

CRM, pazarlama otomasyonu, e-posta gönderimi, SMS, push notification, hedefli reklam, segmentasyon, A/B test, kişiselleştirme, profilleme ve otomatik karar süreçlerinin KVKK + 6563 + İYS uyumlu yönetimi.

## 2. Pazarlama için Hukuki Sebep

### 2.1. KVKK Açısından

Pazarlama amacı KVKK m.5/2 sayılan sebeplerin **hiçbirine** doğal olarak girmez:
- Sözleşmenin ifası değildir (müşteriye satış yapıyor olmamız pazarlamayı kapsamaz).
- Yasal yükümlülük yok.
- Meşru menfaat de **çok kıt** uygulanır (Kurul tutumu).

> **Sonuç:** Pazarlama için hukuki sebep **AÇIK RIZA** (m.5/1).

### 2.2. 6563 Sayılı Kanun (Ticari Elektronik İleti)

E-posta, SMS, push, sesli arama gibi **ticari elektronik iletiler** için:
- Önceden onay (m.6) zorunlu.
- Mevcut müşteri istisnası: aynı mal/hizmet için ek onay aranmaz **AMA** ret hakkı her zaman.
- Onay metni KEP / SMS / yazılı kanaldan kayıt.

### 2.3. İYS (İleti Yönetim Sistemi)

15 Ocak 2020 tarihinde Ticaret Bakanlığı tarafından devreye alınan zorunlu sistem:
- Tüm ticari elektronik ileti onayları İYS'ye işlenir.
- Onay olmayan numaralara ileti gönderimi yasak.
- Şirketler İYS'ye kayıt zorunlu.
- Aylık eşik üzerinde olan firmalar API entegrasyonu.

## 3. Pazarlama İzin Süreci

### 3.1. İzin Toplama

```
[Müşteri kayıt formu / Web sitesi / E-ticaret]
        ↓
[Açık rıza checkbox: ☐ E-posta ☐ SMS ☐ Telefon ☐ Aramalar]
        ↓
[Açıklama: Pazarlama amacı, içerik tipi, sıklık, yurt dışı aktarım]
        ↓
[Doğrulama: e-posta tıklama / SMS OTP / telefon onay]
        ↓
[Kayıt: Zaman damgası, IP, kanal, içerik, versiyon]
        ↓
[İYS bildirimi (3 iş günü içinde)]
```

### 3.2. Açık Rıza Tasarımı (Pazarlama)

Tek "Tüm pazarlamalar için" KABUL EDİLMEZ. Granüler:

| ☐ E-posta bülten (haftalık) | İçerik: yeni ürünler, kampanyalar |
| ☐ SMS bilgilendirme | İçerik: indirim alarmı, son fırsat |
| ☐ Telefon araması | İçerik: özel teklif, anket |
| ☐ Push bildirim | Mobil uygulama |
| ☐ WhatsApp Business | Sınırlı kategori şablonu |
| ☐ Pazarlama amaçlı yurt dışı aktarım | Bulut sağlayıcı, e-posta servisi |

### 3.3. Geri Alma

- Her e-postada **abonelikten çık** linki (zorunlu — Yönetmelik).
- SMS'te "RED" yanıtı.
- Web sitesi profil sayfasında tek tık.
- Çağrı merkezinden talep.
- Geri alma 3 iş günü içinde sistemden silinir + İYS güncellenir.

### 3.4. Mevcut Müşteri İstisnası

6563 m.6/2: Mal/hizmet sağlanan müşteriye, **aynı mal/hizmet** için ek onay gerekmez.

> **Pratik:** Kapsam dar yorumlanır. "Aynı kategori" yorumlanırken ihtiyatlı olun. Yargı pratiği: aynı kategori yeterli — örn. mağaza müşterisi e-postasına yeni mağaza kampanyası gönderilebilir.

## 4. CRM Veri Yönetimi

### 4.1. Veri Kategorileri

- Kimlik (ad-soyad, T.C. — sadece zorunluysa).
- İletişim.
- İşlem geçmişi (sipariş, ödeme).
- Etkileşim (e-posta açma, tıklama, web ziyareti).
- Tercihler (segment, ilgi alanı).
- Net Promoter Score (NPS), CSAT.
- Şikayet kayıtları.

### 4.2. CRM Erişim Yönetimi

- RBAC (Role-Based Access Control).
- Pazarlama operasyon → segment + agregat.
- Sales rep → atanan müşteriler.
- Müşteri hizmetleri → kendi temas noktası.
- Yönetim → toplu rapor.
- Audit log her erişim.

### 4.3. CRM ile İlgili Tipik Sistemler

- Salesforce, HubSpot, Microsoft Dynamics 365, Zoho — yurt dışı veri merkezi sorunu.
- Türk yerli: Logo CRM, Mikro — yurt içi avantaj.
- Yurt dışı CRM kullanımında DPA + Standart Sözleşme + Türkiye region (varsa) tercih.

## 5. Profilleme ve Otomatik Karar

### 5.1. KVKK m.11/g İtiraz Hakkı

> "İşlenen verilerin münhasıran otomatik sistemlerle analiz edilmesi suretiyle kişinin kendisi aleyhine bir sonucun ortaya çıkmasına itiraz etme."

İtiraz halinde:
- Manuel değerlendirme garantisi.
- Açıklanabilir karar.
- Süreçten muafiyet seçeneği.

### 5.2. Profilleme Senaryoları

| Senaryo | KVKK Uyum |
|---------|-----------|
| Segmentasyon (gümüş/altın/platin müşteri) | Aydınlatma + (varsa) açık rıza |
| Lookalike modeli (yeni müşteri benzeri) | DPIA + aydınlatma |
| Churn prediction | DPIA — müşteri olumsuz etkilenebilir |
| Kredi limiti otomatik (ödeme geçmişi) | Hukuki sebep + manuel revize |
| Hedefli reklam (Meta, Google) | Açık rıza — yurt dışı aktarım |
| Ürün öneri (recommendation engine) | Aydınlatma + (genelde) açık rıza |
| A/B test | Aydınlatma; otomatik aleyhine karar yoksa rıza ihtiyacı düşük |

### 5.3. DPIA Tetikleyiciler

- Otomatik karar, manuel revize olmadan etki.
- Hassas kategori (sağlık, finansal durum, etnik).
- Geniş ölçek (1M+ kullanıcı).
- Yeni teknoloji (AI/ML).
- Sürekli izleme.

## 6. A/B Test ve Deneyler

### 6.1. KVKK Açısından

- Test grupları kişisel veri üzerinde yürütülüyor → işleme.
- Aydınlatma metninde "iyileştirme" kapsamında.
- Olumsuz sonuç doğmuyorsa makul.

### 6.2. Etik Çerçeve

- Reddet seçeneği (test dışı tutulma) tasarımda.
- Sonuç paylaşımı toplu / anonim.
- Hassas içerik testi (örn. duygusal manipülasyon) yasak — Cambridge Analytica örneği.

## 7. Hedefli Reklam (Meta, Google, TikTok)

### 7.1. Custom Audience / Lookalike

- Müşteri listesini hashed olarak Meta/Google'a yükle.
- Hash öncesi açık rıza zorunlu.
- Sözleşmesel olarak reklam ağı **veri sorumlusu/işleyen** durumu Hukuk değerlendirmesi gerektirir.
- KVKK aktarım hükümleri uygulanır.

### 7.2. Pixel / Tag

- Web sitesi pixel → kullanıcı verisi reklam ağına.
- Açık rıza (CMP üzerinden) zorunlu.

### 7.3. Yurt Dışı Aktarım

- Meta, Google, TikTok ABD/AB merkezli → yurt dışı.
- Standart Sözleşme ek garantisi.
- Aydınlatmada ülke + amaç bildirimi.

## 8. Pazarlama İçeriği Kişiselleştirme

### 8.1. CRM Tetiklemeli E-posta

- "Doğum gününüz kutlu olsun" → kişisel veri kullanımı.
- "Sepetinizi unuttunuz" → e-ticaret.
- Tetikleyici aydınlatmada açıklanır.

### 8.2. Web Site Kişiselleştirme

- Önceki ziyaretler bazında ürün önerisi.
- Çerez tabanlı.
- Açık rıza (CMP).

### 8.3. Push Bildirim

- Mobil uygulama izni iki katmanlı:
   1. OS izni (iOS, Android).
   2. KVKK açık rıza (uygulama içi).
- Geri alma kolay.

## 9. Müşteri Şikayet ve Geri Bildirim

### 9.1. Saklama

- Şikayet kaydı 6502 sayılı Kanun + KVKK kapsamı.
- Saklama: tüketici uyuşmazlığı zamanaşımı (10 yıl olabilir).
- Kişisel veri minimize edilir.

### 9.2. Sosyal Medya Şikayetleri

- Şikayetvar, Eksisozluk, Twitter, vb. → kamuya açık veri.
- Şikayetin kaydı + cevap KVKK kapsamı.
- Kullanıcı tanımlama (kullanıcı adı, e-posta) hassas.

## 10. NPS / Anket / Kullanıcı Araştırması

- Anket katılımı açık rıza ile.
- Anonimleştirme öncelikli.
- Kişisel sonuçlar erişim kısıtlı.
- Saklama amaçla orantılı.

## 11. Çerez ile Entegrasyon

Bkz. `cerez-yonetimi.md`. Pazarlama çerezleri:
- Açık rıza zorunlu.
- CMP üzerinden.
- Reddedince pazarlama çerezi yüklenmez.

## 12. CMS (Customer Marketing System) Mimarisi

```
[Web/Mobil/Mağaza]
       ↓
[Veri toplama (CRM, CDP)]
       ↓
[Segmentasyon (CDP)]
       ↓
[Pazarlama otomasyonu (HubSpot/Marketo/Mailchimp)]
       ↓
[Kanal: e-posta, SMS, push, reklam]
       ↓
[Etkileşim takibi]
       ↓
[Geri besleme — segment güncelleme]
```

Her kademede:
- Aydınlatma + rıza kontrolü.
- Erişim yönetimi.
- Şifreleme.
- Audit log.

## 13. Tipik Hatalar

| Hata | Doğru Yaklaşım |
|------|----------------|
| Tek "pazarlama rızası" | Kanal bazlı granüler |
| İYS'ye kayıt yok | Zorunlu (3 iş günü) |
| Onay olmayan numaraya SMS | İYS sorgulama API |
| Abonelikten çık linki yok | Yönetmelik gereği zorunlu |
| Çerez izni almadan pixel | CMP rıza sonrası |
| Lookalike için aktarım açık rıza yok | Açık rıza + aydınlatma |
| Yurt dışı CRM Türkiye region yok | Region seçimi mümkünse |
| Müşteri şikayeti "marketing data" segmentinde | Pazarlama dışı veri |
| Otomatik karar manuel revize yok | m.11/g hakkı tanı |
| DPIA yapılmamış (büyük profilleme) | DPIA zorunlu |

## 14. KPI'lar

| KPI | Hedef |
|-----|-------|
| İYS uyum oranı | %100 |
| Açık rıza geçerli oran | %100 |
| Abonelikten çık SLA | < 3 iş günü |
| Pazarlama mesajı şikayet oranı | < %0.1 |
| CMP rıza kayıt oranı | %95+ |
| DPIA kapsam (büyük profilleme) | %100 |
| CRM erişim audit log | %100 |

## 15. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi |
