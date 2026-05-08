---
Doküman: 72 Saat Kurul Bildirimi ve İlgili Kişi Bildirimi
Bölüm: 08-ihlal-yonetimi
Sahip: KVKK Sorumlusu
Onaylayan: Hukuk Müdürü + KVKK Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + Kurul kararı değişikliklerinde
İlgili Mevzuat: 6698 sayılı KVKK m.12/5, KVKKK 24.01.2019 tarih 2019/10 sayılı "Kişisel Veri İhlal Bildirim Usul ve Esaslarına İlişkin" Kararı, KVKKK 18.09.2019 tarih 2019/271 sayılı Kararı (yurt dışı veri sorumlusu), KVKK Veri Güvenliği Rehberi (2018), GDPR m.33-34 (karşılaştırma)
---

# 72 Saat İhlal Bildirim Yükümlülüğü

## 1. Yasal Çerçeve

### 1.1. Kanun Hükmü

**6698 sayılı KVKK m.12/5:**
> "İşlenen kişisel verilerin kanuni olmayan yollarla başkaları tarafından elde edilmesi hâlinde, veri sorumlusu **bu durumu en kısa sürede** ilgilisine ve Kurula bildirir."

### 1.2. Kurul Kararı

**KVKKK 24.01.2019 tarih ve 2019/10 sayılı Kararı:** "En kısa süre" 72 saat olarak belirlenmiştir.
> "Kişisel veri ihlali halinde veri sorumlusu **bu durumu öğrendiği tarihten itibaren gecikmeksizin ve en geç 72 saat içinde** Kurula bildirir. Söz konusu bildirimin 72 saat içinde yapılamaması halinde gecikmenin sebepleri Kurula yapılacak bildirimde açıklanır."

İlgili kişiye bildirim ise: **"makul olan en kısa süre içinde, ilgili kişinin iletişim adresine ulaşılabiliyorsa doğrudan, ulaşılamıyorsa veri sorumlusunun kendi web sitesinde **en az 24 saat** süreyle yayımlanması gibi uygun yöntemlerle"** yapılır.

### 1.3. Bildirim Eşiği

Kurul kararına göre **kişisel veri ihlali**:
- Yetkisiz erişim,
- Hukuka aykırı ifşa / aktarım,
- Yetkisiz değiştirme,
- Kayıp / yok olma,
- Yetkisiz silme.

Yukarıdaki durumlardan **biri gerçekleştiyse** veya **gerçekleşme makul ihtimali varsa** bildirim eşiği aşılmıştır.

## 2. 72 Saat Sayacı: "Öğrenme Anı" Tanımı

### 2.1. Sayaç Ne Zaman Başlar?

Sayaç **"makul ölçüde haberdar olma"** anında başlar. Sıralama:

| Aşama | Sayaç durumu |
|-------|--------------|
| Soyut şüphe (anormal log) | Başlamaz |
| Otomatik alarm (SIEM/EDR/DLP) | Başlamaz — analiz gerekir |
| İlk teknik analiz: kişisel veriye etki ihtimali doğrulandı | **Başlar** |
| Tam kapsam ve sayım belirlendi | Sayaç çoktan başlamış olur |

**Pratik kural:** Olay Komutanı + KVKK Sorumlusu + CISO üçlüsünün birlikte "kişisel veri etkilenmiş olabilir" kanaatine ulaştığı an dakika hassasiyetiyle olay log'una düşer. **Bu an = T+0**.

### 2.2. Sayaç Bir Hafta Sonu / Tatil İçinde Başlarsa?

Tatil/hafta sonu **sayacı durdurmaz**. KVKK Sorumlusu 7/24 ulaşılabilir olmak zorundadır. Bildirim Kurul'a KEP ile yapıldığı için zaman bağımsız çalışır.

### 2.3. Sayaç Geriye Sarılabilir mi?

Hayır. Bildirim sonrası tespit edilen "aslında daha önce öğrenmiştik" durumu zamanaşımını geri almaz; aksine geç bildirim ihlali oluşturur. Bu nedenle **iç şüphe → ihlal değerlendirmesi süresi 24 saatten kısa** tutulmalıdır.

## 3. Kurul'a Bildirim Yöntemi

### 3.1. Kanal

- Birincil: **Kurum web sitesi üzerindeki "Veri İhlal Bildirim Formu"** (ihlalbildirim.kvkk.gov.tr — VERBİS girişi ile).
- Yedek: KEP — **kvkk@hs01.kep.tr**.

### 3.2. Kim Bildirim Yapabilir?

- Veri sorumlusu (yetkili imza yetkilisi).
- Sicile bildirilen **irtibat kişisi**.
- Yurt dışında yerleşik veri sorumlusu için **veri sorumlusu temsilcisi**.

### 3.3. Form Doldurma

Kurul formu KVKK web sitesinde mevcuttur. Şirketimizin kullanacağı doldurulabilir versiyon: bkz. `ihlal-bildirim-formu.md`.

## 4. Bildirim Formu İçeriği (Kurul 2019/10 Kararı)

| Bölüm | Asgari İçerik |
|-------|---------------|
| 1. Veri sorumlusu kimlik | Unvan, VKN, irtibat kişisi, KEP |
| 2. İhlal özeti | Ne oldu, ne zaman, nerede, kim öğrendi |
| 3. İhlal niteliği | Gizlilik / bütünlük / erişilebilirlik |
| 4. İhlal kategorisi | Siber saldırı, içeriden, kayıp, üçüncü taraf, fiziksel |
| 5. Etkilenen veri konusu kişi sayısı | Tahmini + nihai (ayrı satır) |
| 6. Etkilenen kayıt sayısı | Veri konusu kişi sayısından fazla olabilir |
| 7. Etkilenen kişisel veri kategorisi | Genel + özel nitelikli ayrı |
| 8. Olası sonuçlar | Maddi/manevi zarar, dolandırıcılık riski, kimlik hırsızlığı |
| 9. Alınan önlemler | Teknik + idari, saatlik kronoloji |
| 10. Önerilen önlemler | İlgili kişiye yönelik tavsiyeler (parola, kart iptali) |
| 11. İrtibat kişisi | Ad, ünvan, telefon, e-posta |
| 12. Ekler | Forensik özet (varsa), iletişim metni taslağı |

## 5. Aşamalı / Kısmi Bildirim Hakkı

Kurul kararı, tam bilginin 72 saatte mümkün olmaması halinde **aşamalı bildirimi** kabul eder:

| Aşama | Süre | İçerik |
|-------|------|--------|
| İlk bildirim | T+72 saat | Eldeki bilgi + "ek bilgi gönderilecek" notu |
| Tamamlayıcı bildirim 1 | T+5 - 10 gün | Kapsam genişletme/daraltma |
| Tamamlayıcı bildirim 2 | T+15 gün | Kök neden, alınan kalıcı önlemler |
| Nihai rapor | T+30-60 gün | RCA, CAPA, sonuçlanmış kapsam |

**Kritik:** Aşamalı bildirim, **eksik form gönderme** anlamına gelmez. İlk bildirim mevcut bilgi seviyesinde **dolu** olmalı; sonradan **güncellenir**.

## 6. İlgili Kişiye Bildirim

### 6.1. Kapsam

Ne zaman ilgili kişiye bildirim zorunludur?
- Kişisel veri ihlali kişinin **temel hak ve özgürlüklerini** veya **maddi/manevi varlığını** etkileyebileceği zaman.
- Pratikte: tüm bildirilmiş ihlallerde ilgili kişi bildirimi yapılması Kurul'un beklentisidir; muafiyet **çok dar** yorumlanır.

### 6.2. Yöntem

Kurul kararına göre:
1. **Doğrudan bildirim:** İlgili kişinin bildirilmiş iletişim adresine (e-posta, SMS, KEP, fiziksel adres).
2. **Genel bildirim (yedek):** İletişim adresi yoksa veya çok büyük çaplı ihlal söz konusuysa, veri sorumlusunun **web sitesinde en az 24 saat** süreyle yayımlama.

Şirketimizin tercihi: **çift kanal** — birincil iletişim adresi + web sitesi banner. SMS özellikle hızlı ulaşım sağlar.

### 6.3. İlgili Kişi Bildirim İçeriği

Bildirim metni şu unsurları **anlaşılır dilde** içermelidir:
- İhlalin niteliği (örn. "yetkisiz üçüncü taraf, müşteri veri tabanımızdaki bazı bilgilere erişim sağlamıştır").
- Etkilenmiş veri kategorisi (örn. "ad-soyad, e-posta, müşteri numarası — kart bilgileriniz **etkilenmemiştir**").
- Olası sonuçlar (örn. "phishing girişimi gelebilir").
- Alınan önlemler (örn. "saldırı durdurulmuştur, sistem güvence altına alınmıştır").
- İlgili kişinin alabileceği önlemler (örn. "şüpheli e-posta açmayın, parolanızı değiştirin").
- KVKK Sorumlusu iletişim bilgisi (e-posta + telefon).
- 11. madde haklarına atıf.

### 6.4. Süre

İlgili kişi bildirimi **"makul olan en kısa süre"** içinde yapılır. Pratik standart: **Kurul bildiriminden sonraki 5 iş günü içinde**. Geç bildirim Kurul tarafından ek yaptırım sebebidir.

### 6.5. Şablonlar

Hazır metin şablonları için bkz. `99-sablonlar/ihlal-iletisim/` (e-posta, SMS 160 karakter, web banner, basın açıklaması).

## 7. Yurt Dışında Yerleşik Veri Sorumlusu

KVKKK 18.09.2019 tarih 2019/271 sayılı Kararı:
- Yurt dışında yerleşik veri sorumlusunun **Türkiye'deki veri sorumlusu temsilcisi** ihlal bildirim yükümlülüğünü yerine getirir.
- Temsilci VERBİS'e kayıtlı olmalıdır.
- Temsilci için 72 saat sayacı **Türkiye'de** öğrenme anından başlar — yurt dışı merkezde geçen süre Kurul tarafından mazeret sayılmaz.
- Sözleşmesel olarak yurt dışı merkezin temsilciyi **24 saat içinde** haberdar etmesi şart koşulmalıdır.

## 8. Veri İşleyenin Geç Bildirimi

KVKK m.12/2: Veri işleyen, veri sorumlusunun talimatları dışında işleyemez ve **gerekli güvenlik tedbirlerinden müştereken sorumludur**.

Senaryo: Bulut sağlayıcı (veri işleyen) ihlali Şirketimize 5 gün sonra bildirir.

| Soru | Cevap |
|------|-------|
| 72 saat ne zaman başlar? | Şirketimizin (veri sorumlusunun) öğrendiği gün (5. gün). |
| Toplam 5+3 = 8 gün geçmesi sorun mu? | Şirketimiz açısından bildirim süresine uydu (3 gün); ancak Kurul, **veri sorumlusunun veri işleyen üzerindeki sözleşmesel ve teknik kontrolünü yetersiz bularak** ek yaptırım uygulayabilir. |
| Sözleşmede ne olmalı? | "Veri işleyen, ihlali öğrendiği andan itibaren **24 saat içinde** veri sorumlusuna KEP ile bildirir" + gecikme cezası. |
| İhlal bildiriminde ne yazılır? | "İhlal veri işleyen X firmasında gerçekleşmiş, tarafımıza Y tarihinde bildirilmiş, Z sözleşmesel yaptırım başlatılmıştır." Kurul bunu görmek ister. |

## 9. Yurt Dışı Aktarım Sonrası İhlal

Veri yurt dışı aktarımdan sonra etkilenen ülkede ihlale uğrarsa (alıcı = yurt dışı işleyen veya alıcı veri sorumlusu):
- Şirketimiz hâlâ **veri sorumlusu** sıfatıyla Kurul'a bildirir.
- Standart Sözleşme veya bağlayıcı şirket kuralları çerçevesindeki bildirim klozları devreye girer.
- Yurt dışı DPA bildirimi (GDPR m.33) ayrıca yapılır gerekirse.
- Aktarım hukuki sebebi (Yeterlilik kararı / Standart Sözleşme / Açık rıza) Kurul'a açıklanır.

## 10. İdari Yaptırım (Bildirim Yükümlülüğü İhlali)

KVKK m.18/1-b: Veri güvenliği ile ilgili yükümlülüklere aykırılık → **idari para cezası**.

| Yıl | Alt sınır (TL) | Üst sınır (TL) |
|-----|----------------|----------------|
| 2026 (her yıl Kurul güncellemesi) | Yıllık güncel tarife için Kurum sayfası kontrol | — |

> **Not:** Tutarlar her yıl yeniden değerleme oranıyla artırılır. Bu doküman güncel rakamı `12-mevzuat-arsiv/idari-para-cezalari.md` üzerinden referanslar.

Geç bildirim ayrıca **ağırlaştırıcı sebep**tir; mükerrer ihlalde ceza tavandan kesilir.

## 11. Tipik Hatalar ve Kaçınma

| Hata | Doğru yaklaşım |
|------|----------------|
| "Henüz emin değiliz, biraz daha bekleyelim" | İhlal **olasılığı** yüksekse 72 saat içinde bildirim — eksik bilgi tamamlanır. |
| Tüm form alanlarını doldurmaya çalışıp süreyi geçirmek | İlk bildirim **eldeki bilgi** ile yapılır; "ek bilgi gönderilecektir" notu düşülür. |
| Hafta sonu/bayramda erteleme | KVKK Sorumlusu 7/24 nöbet — sayaç durmaz. |
| İlgili kişiye bildirim atlama | Kurul muafiyeti çok dar; eksiltme ek yaptırım sebebi. |
| Bildirim metninde teknik jargon | İlgili kişi metni B1 seviye Türkçe — net, kısa. |
| Saldırgan iletişim ipuçlarını yayınlama | Hukuk + iletişim onayı olmadan teknik detay paylaşma. |
| Veri işleyenden bildirim beklerken sayacı kaçırma | Sözleşmesel 24 saat klozu + iç tetikleme mekanizması. |
| Tek bildirim → tek olay yanılgısı | Aynı saldırgan birden çok ihlal yapmışsa **her biri ayrı bildirim**. |
| Birim bildirimi (sadece IT görsün) | KVKK Sorumlusu + Hukuk + Yönetim Kurulu eskalasyonu kaçınılmaz. |
| Bildirim sonrası sessizlik | Tamamlayıcı bildirimler + RCA + CAPA Kurul beklentisi. |

## 12. Kurul Bildirim Sonrası Süreç

| Aşama | Süre | İçerik |
|-------|------|--------|
| 1. Bildirim onayı | 1-7 iş günü | Kurum'dan referans no |
| 2. Ek bilgi talebi | 15 gün | Kurul ek soru sorabilir |
| 3. Yerinde inceleme | Değişken | Kurul uzmanları gelebilir |
| 4. Kurul kararı | 3-12 ay | İdari yaptırım veya ihtar |
| 5. İdari para cezası | Karar tarihinde | Tebliğden itibaren 30 gün ödeme |
| 6. İdari yargı (itiraz) | 60 gün | İdare Mahkemesi |

## 13. İç Eskalasyon Tablosu (Şirket içi karar yetkileri)

| Karar | Yetki |
|-------|-------|
| Kurul'a bildirim yapma | KVKK Sorumlusu (Hukuk + CISO uyumla) |
| İlgili kişiye bildirim metni onayı | Hukuk Müdürü + Kurumsal İletişim |
| Basın açıklaması | CEO + Kurumsal İletişim Direktörü |
| Sigorta poliçesi aktivasyonu | CFO + Hukuk |
| Fidye ödememe kararı | Yönetim Kurulu (önceden tanımlı politika) |
| Veri işleyen ile sözleşme feshi | CEO + Hukuk + KVKK Komitesi |

## 14. Kayıt ve Arşiv

Bildirim ve sonrası tüm yazışma:
- **Kurul Yazışma Defteri**ne kronolojik işlenir.
- KEP delil zinciri sigortalı arşive kopyalanır.
- Saklama süresi **10 yıl** (zamanaşımı + arşiv mevzuatı).
- Erişim sadece KVKK Komitesi ve görevlendirilen Hukuk personeli.

## 15. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi |
