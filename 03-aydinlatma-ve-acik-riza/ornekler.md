---
Doküman: Senaryo Bazlı Aydınlatma ve Açık Rıza Örnekleri
Bölüm: 03-aydinlatma-ve-acik-riza
Sahip: KVKK Sorumlusu
Onaylayan: Hukuk Müdürü + KVKK Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş
İlgili Mevzuat: 6698 sayılı KVKK m.5, m.6, m.9, m.10, m.11; Aydınlatma Tebliği MADDE 4-5; 6563 sayılı Elektronik Ticaretin Düzenlenmesi Hakkında Kanun ve İYS Yönetmeliği; ilgili sektör mevzuatı
---

# Senaryo Bazlı Aydınlatma ve Açık Rıza Örnekleri

Bu doküman, sık karşılaşılan iş senaryoları için aydınlatma ve açık rıza uygulamasının pratik karşılığını gösterir. Her senaryoda:
1. **Bağlam** — operasyonel durum
2. **Hukuki analiz** — hangi sebep, açık rıza gerekli mi
3. **Aydınlatma metni** — uygun kanal için kısaltılmış örnek
4. **Açık rıza ekranı / akışı** — varsa
5. **İspat ve kayıt** — neyi nasıl logluyoruz
6. **Sık hatalar**

---

## Senaryo 1 — Müşteri E-ticaret Kayıt + Pazarlama Ek Rıza

### Bağlam
B2C e-ticaret sitesinde kullanıcı kayıt formu. Sipariş verme + pazarlama iletişimi ayrı amaçlar.

### Hukuki Analiz
- **Hesap oluşturma + sözleşme:** KVKK m.5/2/c (sözleşmenin ifası için zorunluluk)
- **Sipariş takibi, faturalandırma:** m.5/2/c, m.5/2/ç (VUK gereği)
- **Pazarlama (e-posta, SMS, push):** Açık rıza + İYS onayı zorunlu
- **Profilleme (alışveriş analizine dayalı öneri):** Açık rıza
- **3. kişi pazarlama paylaşımı:** Açık rıza

### Form Tasarımı

```
[Sayfa 1 — Üyelik Bilgileri]
Ad Soyad:  [____________]
E-posta:   [____________]
Telefon:   [____________]
Şifre:     [____________]

→ "İleri" butonu

[Sayfa 2 — Bilgilendirme ve Onay]

ZORUNLU
☐ "Üyelik Aydınlatma Metni"ni (AYD-MUS-01) okudum ve anladım.
☐ Mesafeli Satış Ön Bilgilendirme Formu'nu okudum, kabul ediyorum.
☐ Üyelik Sözleşmesi'ni okudum, kabul ediyorum.

OPSİYONEL — AÇIK RIZA
Aşağıdaki seçimler tamamen size aittir. Vermemeniz halinde
hizmetimizden faydalanmanıza engel oluşturmaz.

☐ Pazarlama Açık Rızası
   Şirket'in açık ve kapalı kampanyaları, indirimleri ve yeni ürün
   tanıtımları hakkında e-posta, SMS ve push bildirim almayı kabul
   ediyorum. (Aydınlatma: AYD-PAZ-01) (İYS: e-posta + SMS)

☐ Kişiselleştirme / Profilleme Açık Rızası
   Site üzerindeki davranışlarımın ve sipariş geçmişimin analiz
   edilerek bana özel öneriler sunulmasını kabul ediyorum.
   (Aydınlatma: AYD-PAZ-02)

☐ İş Ortaklarıyla Pazarlama Amaçlı Paylaşım
   Pazarlama amaçlı verilerin Şirket'in iş ortaklarıyla paylaşılmasını
   kabul ediyorum. (Aydınlatma: AYD-PAZ-03)

[Üye Ol]
```

### İspat ve Kayıt

CMP kaydı:
```
{
  "user_id": "U-394827",
  "consent": [
    { "category": "marketing_email_sms",   "status": "granted",   "version": "AYD-PAZ-01:1.2" },
    { "category": "profiling",             "status": "withdrawn", "version": "AYD-PAZ-02:1.0" },
    { "category": "third_party_sharing",   "status": "granted",   "version": "AYD-PAZ-03:1.1" }
  ],
  "channel": "web",
  "ip": "85.x.x.x",
  "user_agent": "Mozilla/5.0 ...",
  "recorded_at": "2026-05-08T13:24:10Z",
  "iys_record_id": "IYS-0000-0000"
}
```

### Sık Hatalar
- Hesap açma için pazarlama rızası şartına bağlama
- Aydınlatma + tüm rızaları tek checkbox'a sıkıştırma
- "Tümünü işaretle" varsayılanı
- Geri alma kanalının olmaması

---

## Senaryo 2 — Çalışan İşe Alım → İşe Alım Sonrası Geçiş

### Bağlam
İşe alım süreci → işe başladıktan sonra özlük dosyası süreci. **İki farklı süreç → iki farklı aydınlatma metni.**

### Hukuki Analiz
- **Aday değerlendirme:** m.5/2/c (sözleşme öncesi tedbirler), m.5/2/f (meşru menfaat)
- **Aday havuzunda saklama (işe alınmadıysa):** Açık rıza
- **İşe alındıktan sonra özlük:** m.5/2/c (sözleşme ifası), m.5/2/ç (İş Kanunu, SGK), m.6/3 (sağlık verisi için sır saklayanlarca)

### Aydınlatma Akışı

1. Başvuru anında: **AYD-IK-01 (İşe Alım)** gösterilir.
2. İşe alındığında: **AYD-IK-02 (Özlük Dosyası)** ayrıca verilir, imzalı kopya alınır.
3. Sağlık raporu için: **AYD-IK-07 (İSG)** + ek aydınlatma.
4. Aday havuzunda saklama isteniyorsa açık rıza ayrı alınır.

### Aday Havuzu Açık Rıza Metni (Form üstünde)

```
☐ İş başvurum değerlendirmesi sonucunda işe alınmamam halinde,
  ileride uygun pozisyonlar açıldığında değerlendirilmek üzere
  başvuru bilgilerimin Şirket tarafından maksimum 2 yıl süreyle
  saklanmasına açık rıza veriyorum. (AYD-IK-01)

  Bu rızayı dilediğim zaman ik-kvkk@sirketadi.com.tr adresine
  başvurarak geri alabilirim.
```

### Sık Hatalar
- Tek aydınlatma metni ile aday + çalışan ayrımının yapılmaması
- İSG sağlık verisi için ayrı aydınlatma yapılmaması
- Aday havuzu için rıza alınmadan saklama
- Çalışana "açık rıza vermek zorundasınız" hissi verme

---

## Senaryo 3 — CCTV: Ziyaretçi Tabela + Detaylı Aydınlatma

### Bağlam
Şirket binasında CCTV bulunmakta. Tüm girişler izlenmekte, soyunma odası, WC vb. kapsam dışı.

### Hukuki Analiz
- **Hukuki sebep:** m.5/2/f (meşru menfaat — bina güvenliği) + m.5/2/ç (İSG mevzuatı)
- **Açık rıza gerekmiyor**

### Tabela Metni (Bina Girişi — Görünür Yer)

```
┌──────────────────────────────────────────────────┐
│ [Şirket logosu]                                   │
│                                                   │
│ DİKKAT — KAPALI DEVRE KAMERA SİSTEMİ              │
│                                                   │
│ Bu alan güvenlik amacıyla kamera ile             │
│ izlenmektedir.                                    │
│                                                   │
│ Veri Sorumlusu: [Şirket Tam Ünvanı]              │
│ İşleme Amacı: Bina ve çevre güvenliği,           │
│ İSG kapsamında giriş-çıkış kaydı                 │
│ Hukuki Sebep: KVKK m.5/2/f ve m.5/2/ç           │
│                                                   │
│ Detaylı aydınlatma metni:                        │
│ www.sirketadi.com.tr/kvkk/cctv                   │
│ [QR KOD]                                          │
│                                                   │
│ Saklama: 30 gün                                  │
│ Başvuru: kvkk@sirketadi.com.tr                  │
└──────────────────────────────────────────────────┘
```

### Detay Metnine Eklenecek Önemli Bilgi

```
Kameralar bina ortak alanları, giriş-çıkışlar, koridorlar,
otopark ve ana güvenlik noktalarında konumlanmıştır. Tuvalet,
soyunma odası, dini ibadet alanları ve özel mahremiyet alanları
kapsam dışında bırakılmıştır. Toplam [n] kamera bulunmaktadır.
Kayıtlara yalnızca yetkilendirilmiş Güvenlik personeli erişebilir.
Kayıtlar, olay yokluğunda 30 günde rotasyonel olarak silinir.
```

### Sık Hatalar
- Tek tabela ile yetinme; web sayfasında detay vermeme
- Mahremiyet alanlarına kamera yerleştirme
- 30 günden uzun saklama gerekçesizce
- Kayıtlara çok geniş erişim yetkisi

---

## Senaryo 4 — Çağrı Merkezi Ses Kaydı Anonsu (Tam Metin)

### Bağlam
Inbound (gelen arama) ve outbound (giden arama) çağrı merkezi. Tüm görüşmeler kayıt altında.

### Hukuki Analiz
- **Inbound (müşteri sözleşmesi gereği):** m.5/2/c
- **Inbound (genel destek, hizmet kalitesi):** m.5/2/f
- **Outbound (pazarlama):** Açık rıza + İYS onayı
- **Eğitim amaçlı kullanım:** ek meşru menfaat değerlendirmesi gerekir

### Inbound — IVR Anonsu (Görüşme Başında)

```
"[Şirket adı]'na hoş geldiniz.

Şirketimiz tarafından hizmet kalitesinin denetlenmesi, taleplerinizin
kayıt altına alınması ve sözleşmemizin ifası amacıyla, KVKK
madde 5/2/c ve madde 5/2/f bentlerine dayanarak, görüşmeniz ses
kayıt altına alınmaktadır.

Detaylı aydınlatma metnimize www.sirketadi.com.tr/kvkk/cm
adresinden ulaşabilirsiniz.

Görüşmeye devam etmek istemiyorsanız hattan ayrılabilirsiniz.

Talebiniz için 1, hesabınız için 2..."
```

### Outbound — Pazarlama Çağrısı

```
[Operatör]:
"İyi günler [Müşteri adı]. [Şirket adı]'ndan [Operatör adı] arıyor.
Görüşmeniz kayıt altındadır.

Sizinle [ürün/kampanya] hakkında bilgi paylaşmak isterim. KVKK ve
İYS kayıtlarımız uyarınca daha önce pazarlama iletişimi açık
rızanız bulunmaktadır. Görüşmeyi sürdürmek ister misiniz?"

[Müşteri red ederse]
"Anladım. Pazarlama iletişimi rızanızı geri çekmenizi sağlayacağım.
Bilgilendirme e-postası gelecektir. İyi günler dilerim."

[Sistem üzerinde rıza durumu güncellenir, e-posta tetiklenir]
```

### İspat
- IVR anons sistem logu (gösterim)
- Ses kaydı (tam görüşme)
- CRM üzerinde rıza durumu
- İYS onay kaydı (outbound için)

### Sık Hatalar
- Anons "görüşme kayıt altına alınıyor" ile yetiniliyor; veri sorumlusu, amaç, hukuki sebep, başvuru bilgisi eksik
- Outbound pazarlama aramasında İYS onayı kontrol edilmeden arama yapma
- Ses kaydını sınırsız süre saklama

---

## Senaryo 5 — Mobil Uygulama İzinleri (Lokasyon, Kamera, Mikrofon, Kişiler)

### Bağlam
Mobil uygulama, hizmet için lokasyon, kamera (ürün fotoğrafı), mikrofon (sesli arama özelliği) ve kişiler (paylaşma) erişimi ister.

### Hukuki Analiz
İşletim sistemi izni ≠ KVKK rızası. **Her ikisi de gereklidir.**

| İzin | Amaç | Hukuki Sebep |
|------|------|--------------|
| Lokasyon (kaba) | Yakın mağaza önerisi | m.5/2/f (meşru menfaat — bilgilendirici amaç) |
| Lokasyon (hassas, sürekli) | Lokasyon bazlı kampanya | Açık rıza |
| Kamera | Ürün fotoğrafı yükleme | m.5/2/c (sözleşme ifası — kullanıcı içerik üretimi) |
| Mikrofon | Sesli müşteri hizmeti | m.5/2/c (sözleşme ifası) |
| Kişiler | Davet et özelliği | Açık rıza + 3. kişi rızası beklenir |

### Akış

```
[Uygulama ilk açılış]
1. Onboarding ekranı: AYD-MOB-01 (Mobil Uygulama Aydınlatma)
2. Hesap oluşturma → e-posta/telefon doğrulama
3. İzin istekleri (gerektiğinde — anlık):
   - Lokasyon istendiğinde modal:
     "Mağazaları yakınınızdan görmek için lokasyon erişimi gerekli.
      Bu, KVKK m.5/2/f bendi kapsamında işlenir.
      İşletim sistemi izni vermeniz halinde lokasyonunuz cihazınızda
      tutulur ve sadece yakın mağaza listesi için kullanılır."
     [İzin Ver]  [Reddet]

4. Pazarlama açık rıza ekranı (ayrı):
   ☐ Lokasyon bazlı pazarlama açık rızası
   ☐ Push bildirimle pazarlama açık rızası
```

### Sık Hatalar
- İşletim sistemi iznini KVKK rızası ile karıştırma
- Kullanıcı izin vermeyince uygulamayı işlevsiz bırakma
- Sürekli arka plan lokasyonu sessizce alma
- Kişiler erişiminden 3. kişilerin rızası alınmadan veri kullanma

---

## Senaryo 6 — Çerez Bandı (CMP) + IAB TCF Türkiye Uyarlaması

### Bağlam
Web sitesi analitik ve pazarlama çerezleri kullanıyor. IAB TCF (Transparency & Consent Framework) v2 yapısı kullanılıyor; ancak Türkiye için yerel uyumluluk gereksinimleri var.

### Hukuki Analiz
- **Zorunlu çerezler:** m.5/2/f (meşru menfaat — site fonksiyonu)
- **Performans/analitik:** Açık rıza önerilir (Kurum çerez rehberi paralelinde)
- **Pazarlama/reklam:** Açık rıza zorunlu

### Çerez Bandı Tasarımı

```
[Sayfa altında — sticky bar]

┌────────────────────────────────────────────────────────┐
│ Çerez Tercihleri                                        │
│                                                          │
│ Web sitemiz çerezler kullanır. Zorunlu çerezler          │
│ siteyi çalıştırır. Diğer çerezler tercihlerinize         │
│ bırakılmıştır.                                           │
│                                                          │
│ [Tümünü Reddet]   [Tümünü Kabul Et]   [Tercihleri Yönet]│
└────────────────────────────────────────────────────────┘
```

> "Tümünü Reddet" butonu "Tümünü Kabul Et" ile **eşit kolaylıkta** ve **eşit görsel ağırlıkta** olmalıdır.

### Tercihleri Yönet (Detaylı Modal)

```
☑ Zorunlu çerezler  (kapatılamaz)
   Oturum yönetimi, güvenlik ve temel fonksiyonlar.
   [Detay listesi]

☐ Performans / Analitik
   Sayfa performansı ve kullanım analizi (Google Analytics, vb.)
   Süre: 13 ay | Üçüncü taraflar: Google İrlanda

☐ Pazarlama / Reklam
   Hedeflenmiş reklam ve kampanya iletişimi (Meta, Google Ads)
   Süre: 13 ay | Üçüncü taraflar: Meta (ABD), Google Ads (İrlanda)

☐ Sosyal Medya
   Sosyal medya paylaşım eklentileri (Facebook, X)
   Süre: oturum + 1 yıl

[Tercihleri Kaydet]   [Vazgeç]

Detaylı çerez politikası: [link]
KVKK Aydınlatma Metni: AYD-WEB-01
```

### IAB TCF Notu
- IAB TCF v2 string'i tek başına KVKK uyumu sağlamaz.
- Türkçe metin + KVKK m.5/m.6 atfı + Kurum'un çerez rehberi + İYS uyumu ek gerekliliklerdir.
- TCF Vendor List'i, üçüncü taraf alıcılar olarak aydınlatma metninde belirtilmelidir.

### Sık Hatalar
- "Sadece kabul et" butonu (red dengelenmemiş)
- Tercih kaydeden butonun varsayılan kabul olması
- 3. taraf çerezlerin hiç bildirilmemesi
- Cookie wall (kabul etmeden sayfaya girilemiyor) — Kurul rehberlerinde eleştirilmiştir

---

## Senaryo 7 — Newsletter / SMS Pazarlama (İYS Uyumu Dahil)

### Bağlam
Mevcut müşteri olmayan ziyaretçiden newsletter aboneliği alınıyor.

### Hukuki Analiz
- **KVKK rızası:** m.5/1 ilk cümle — açık rıza
- **İYS onayı:** 6563 sayılı Kanun + İYS Yönetmeliği — onay zorunlu, İYS'ye kayıt
- **Mevcut müşteri istisnası:** sınırlı (ilgili sektör mevzuatına bakılır)

### Newsletter Kayıt Formu

```
Newsletter'a Abone Ol

E-posta: [_______________]

☐ E-posta ile kampanya, indirim ve yeni ürün bilgileri almayı
  kabul ediyorum.
  KVKK Aydınlatması: AYD-PAZ-01
  İYS Onayı: e-posta kanalı

  Onayımı dilediğim zaman aboneliği iptal et bağlantısı veya
  iys.org.tr üzerinden geri alabilirim.

[Abone Ol]
```

### İlk Onay E-postası (Çift-onaylı / Double Opt-in)

```
Konu: E-posta aboneliğinizi onaylayın

[Kullanıcı adı] merhaba,

[Şirket adı] e-posta listesine abone olmak istediğinizi belirttiniz.

Aboneliğinizi onaylamak için tıklayın:
[ONAYLA] (link 7 gün geçerli)

Eğer bu isteği siz yapmadıysanız, bu e-postayı görmezden gelebilirsiniz.

KVKK Aydınlatma Metni: [link]
İYS bilgileri ve abonelik yönetimi: iys.org.tr
```

> Çift-onaylı (double opt-in) yapı yasal zorunluluk değildir; ancak Kurul incelemelerinde "rıza ispatı" kalitesini artırır ve hatalı kayıtları önler.

### Her Pazarlama E-postası Altında

```
─────────────────────────────────────────
Bu e-posta, KVKK m.5/1 ilk cümle uyarınca aldığımız açık rızaya
dayalı olarak gönderilmiştir.

Aboneliği iptal etmek için: [İptal Linki]
İYS üzerinden yönetmek için: iys.org.tr
KVKK Aydınlatma Metni: [Link]

[Şirket Tam Ünvanı] - [MERSİS] - [Adres]
```

### Sık Hatalar
- İYS'ye onay kaydedilmiyor
- Abonelikten çıkma butonu gizli/zor
- Tek opt-in ile sahte kayıt riski
- Onay altında yer alan ifadelerin mevzuat dışı çıkması (örn. "kampanya, anket, üçüncü taraf, başka faaliyet" gibi geniş)

---

## Senaryo 8 — Sağlık Kurumu Hasta Kayıt (KVKK m.6 Sağlık Verisi)

### Bağlam
Özel hastane / poliklinik. Hasta kaydı, muayene, tedavi süreçleri.

### Hukuki Analiz
- **Sağlık verisi:** KVKK m.6 — özel nitelikli
- **m.6/3 istisnası:** Sır saklama yükümlülüğü altındaki kişilerce (hekim, hemşire, eczacı vb.) kamu sağlığının korunması, koruyucu hekimlik, tıbbi teşhis, tedavi ve bakım, sağlık hizmetlerinin planlanması ve yönetimi amaçlarıyla rızasız işlenebilir.
- **Mali işlem (faturalama, sigorta):** ek olarak m.5/2/c ve m.5/2/ç
- **Sağlık verisi dışındaki amaçlar (örn. pazarlama, araştırma):** açık rıza

### Hasta Kayıt Aydınlatma Metni (Özet)

```
HASTA AYDINLATMA METNİ
[Hastane Tam Ünvanı]

İşlenen Veriler:
- Kimlik, iletişim
- Sağlık verileri (özel nitelikli): tanı, tedavi, ilaç, tıbbi görüntüleme,
  laboratuvar sonuçları, anamnez
- Mali bilgiler (faturalama amacıyla)

Amaçlar:
- Tıbbi teşhis, tedavi ve bakım hizmetleri
- Sağlık hizmetinin planlanması ve yönetimi
- Mevzuat gereği sağlık otoritelerine bildirim
- Sigorta tahakkuk ve faturalama
- Bilimsel araştırma (anonim hale getirilerek; aksi halde açık rıza ile)

Hukuki Sebep:
- KVKK m.6/3 — sağlık ve cinsel hayata ilişkin verilerin sır saklama
  yükümlülüğü altındaki kişilerce işlenmesi
- KVKK m.5/2/ç — Sağlık Bakanlığı bildirimleri (Sağlık Hizmetleri
  Temel Kanunu vb.)
- KVKK m.5/2/c — sağlık hizmeti sözleşmesinin ifası
- KVKK m.5/2/e — bir hakkın tesisi (sigorta, dava)

Aktarım:
- Sağlık Bakanlığı, ilgili bakanlık birimleri (mevzuat gereği)
- SGK ve özel sağlık sigorta şirketleri
- Sevk yapılan diğer sağlık kuruluşları
- Avukatlık ortağı (ihtilaf halinde)
- Yurt dışı: medikal görüş için yurt dışı uzman gerekiyorsa açık rıza
  ile aktarım yapılabilir

Saklama:
- Hasta dosyası: ilgili sağlık mevzuatı ve TBK zamanaşımı süreleri
  birlikte değerlendirilir; **20 yıl** referans alınır.
```

### Açık Rıza Gereken Senaryolar (Hastanede)

| İşleme | Rıza |
|--------|------|
| Tedavi amaçlı sağlık verisi işleme | Aranmaz (m.6/3) |
| Sigorta için sağlık raporu paylaşımı | Genelde aranmaz; sözleşme + mevzuat |
| Klinik araştırmaya katılım | Açık rıza zorunlu |
| Pazarlama (yeni hizmet duyurusu) | Açık rıza zorunlu |
| Hasta deneyimi anketi | m.5/2/f veya açık rıza |
| Sosyal medya paylaşımı için fotoğraf | Açık rıza zorunlu |

### Sık Hatalar
- Sağlık verilerine genel personel erişimi (sır saklama yükümlülüğü ile sınırlı)
- Hasta dosyalarının yetersiz saklama süresi belirlenmesi
- Klinik araştırma için açık rıza alınmaması
- Pazarlama amaçlı kullanım için sağlık verisinin rızasız kullanılması

---

## Senaryo 9 — İK Referans Alma Süreci

### Bağlam
İşe alım finalinde adayın belirttiği eski işveren / yöneticilerinden referans alınıyor. Referans veren kişi de bir veri sahibi olabilir.

### Hukuki Analiz

İki ayrı veri konusu kişi grubu:
1. **Aday** — kendi verisi
2. **Referans Veren** — kişisel verisi (en azından adı, kurumu, iletişimi)

| Veri konusu | Hukuki sebep |
|-------------|--------------|
| Aday — referans bilgisinin işlenmesi | m.5/2/c (sözleşme öncesi tedbirler) |
| Aday — referansın görüşünün alınması | m.5/2/f (meşru menfaat — yetkinlik değerlendirme) |
| Referans veren — iletişim verisi | m.5/2/f (meşru menfaat); aydınlatma yapılır |
| Referans verenden alınan görüş (nitelikli yorum) | Veri kategorisine göre m.5/2/f |

### Operasyonel Akış

1. Aday, başvuru formunda referans iletişimini paylaşır.
2. Aydınlatma metninde "ilettiğiniz referans bilgilerinin sahibi olan kişiden de aydınlatma ve gerekli halde rızayı almanız beklenir" notu yer alır.
3. İK, referansı arar; arama başında **referans verene aydınlatma** yapar:

```
"Merhaba [İsim]. [Şirket adı]'ndan [İK uzmanı adı] arıyor. [Aday adı]
sizi referans olarak göstermiştir. Sizinle adayın geçmiş iş deneyimi
hakkında bilgi paylaşmak istiyorum.

Görüşmemiz, KVKK m.5/2/f bendi uyarınca meşru menfaate dayalı olarak
yapılmaktadır. Verdiğiniz bilgiler [aday adı]'nın işe alım kararında
kullanılacak ve 1 yıl süreyle saklanacaktır. Detaylı aydınlatma metnimiz
talep ettiğinizde tarafınıza iletilebilir.

Devam etmek ister misiniz?"
```

### Sık Hatalar
- Referans verene aydınlatma yapılmaması (çağrı başında)
- Aday tarafından paylaşılan referans verisinin rızasız kullanılması (örn. kara liste)
- Referans yanıtlarının uzun süre saklanması
- Telefon kayıt anonsunun referans aramaları için yapılmaması

---

## Senaryo 10 — Tedarikçi Çalışan Verisi Paylaşımı

### Bağlam
Şirket A (veri sorumlusu) tedarikçi B'nin çalışanlarına bina/sistem erişimi sağlamak için ad-soyad, T.C. kimlik no, telefon, görev unvanı bilgilerini alıyor.

### Hukuki Analiz
- **Şirket A açısından (veri sorumlusu):** m.5/2/c (Şirket A ile B arasındaki sözleşmenin ifası); m.5/2/f (binayı koruma meşru menfaati)
- **Tedarikçi B çalışanı (veri konusu):** Çalışanın kendi rızası değil; B'nin ifa yükümlülüğü
- **Aydınlatma:** Şirket A, tedarikçi çalışanını **doğrudan** aydınlatabilir veya tedarikçi B aracılığıyla aydınlatma yapılır.

### Sözleşme Hükmü Önerisi (B → A)

```
"Tedarikçi (B), Şirket'e (A) ileteceği çalışan kişisel verilerinin
elde edilmesi ve A'ya aktarımı süreçlerinde KVKK m.10 kapsamındaki
aydınlatma yükümlülüğünü kendi çalışanlarına karşı yerine getirmiş
olduğunu beyan ve taahhüt eder. A'nın binasında çalışacak çalışanlara
A'nın AYD-OPR-01 (Tedarikçi Çalışan Bina ve Sistem Erişimi) aydınlatma
metni ayrıca tebliğ edilecek ve A'nın talebi halinde imzalı kopyaları
A'ya iletilecektir."
```

### Tedarikçi Çalışanına Aydınlatma Metni (Bina Girişinde)

```
SAYIN ZİYARETÇİ / TEDARİKÇİ ÇALIŞANI

[Şirket A Tam Ünvanı] olarak, sizin bina ve/veya sistemlerimize
erişiminizi sağlayabilmek amacıyla aşağıdaki kişisel verilerinizi
işlemekteyiz:

Veriler: ad-soyad, T.C. kimlik no, telefon, fotoğraf (kart için),
        görev unvanı, çalıştığınız tedarikçi firma adı

Amaç: Bina ve sistem güvenliği, tedarikçi sözleşmesi ifası, İSG kayıtları

Hukuki Sebep:
- KVKK m.5/2/c — Şirketimiz ile tedarikçi firmanız arasındaki
  sözleşmenin ifası
- KVKK m.5/2/f — Bina güvenliği meşru menfaati
- KVKK m.5/2/ç — İSG mevzuatı

Saklama: İşin tamamlanmasından itibaren 1 yıl

Aktarım: Yetkili kolluk kuvvetleri (talep + adli süreç halinde),
sigorta firması (kaza halinde)

Yurt dışı aktarım: YOK

KVKK m.11 hakları ve başvuru: [bilgi]
Detaylı aydınlatma metni: AYD-OPR-01 (kart teslim noktasından
talep edebilirsiniz)
```

### Sık Hatalar
- Tedarikçi çalışanının "tedarikçi firma çalışanı" olduğu için aydınlatmanın gereksiz sayılması
- Tedarikçi sözleşmesinde KVKK hükümlerinin yer almaması
- Tedarikçi çalışanı verilerinin Şirket A'da müşteri verisi gibi işlenmesi
- 1 yıllık sürenin aşılmasına rağmen verilerin tutulması

---

## 11. Genel Kontrol Tablosu (Senaryo Bağımsız)

| Senaryo Türü | Aydınlatma | Açık Rıza | Hukuki Sebep Önerisi |
|--------------|-----------|-----------|---------------------|
| Müşteri sözleşmesi (kayıt, sipariş) | Evet | H | m.5/2/c, m.5/2/ç |
| Pazarlama (e-posta/SMS/push) | Evet | E | m.5/1 + İYS |
| Profilleme | Evet | E | m.5/1 |
| Çağrı merkezi ses kaydı (inbound) | Evet (anons) | H | m.5/2/c, m.5/2/f |
| Çağrı merkezi outbound pazarlama | Evet | E | m.5/1 + İYS |
| Çalışan özlük dosyası | Evet | H | m.5/2/c, m.5/2/ç |
| Çalışan adayı | Evet | H (havuz için E) | m.5/2/c |
| CCTV bina güvenlik | Evet | H | m.5/2/f, m.5/2/ç |
| Ziyaretçi yönetimi | Evet | H | m.5/2/f, m.5/2/ç |
| Mobil app — temel fonksiyon | Evet | H | m.5/2/c, m.5/2/f |
| Mobil app — lokasyon/kişiler/mikrofon (gereksiz) | Evet | E | m.5/1 |
| Çerez analitik | Evet | E (önerilir) | m.5/1 |
| Çerez pazarlama | Evet | E (zorunlu) | m.5/1 |
| Newsletter | Evet | E | m.5/1 + İYS |
| Sağlık verisi tedavi | Evet | H | m.6/3 |
| Sağlık verisi pazarlama/araştırma | Evet | E | m.6/2 |
| Çalışan referansı | Evet | H | m.5/2/f |
| Tedarikçi çalışanı bina erişimi | Evet | H | m.5/2/c, m.5/2/f, m.5/2/ç |

## 12. Ekler

- Şablon: [aydinlatma-metni-sablonu.md](./aydinlatma-metni-sablonu.md)
- Kontrol Listesi: [aydinlatma-metni-checklist.md](./aydinlatma-metni-checklist.md)
- Açık Rıza Kuralları: [acik-riza-kurallari.md](./acik-riza-kurallari.md)
