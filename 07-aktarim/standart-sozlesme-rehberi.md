---
Doküman: Standart Sözleşme Rehberi
Bölüm: 07-aktarim
Sahip: Hukuk Müdürlüğü + KVKK Sorumlusu
Onaylayan: Hukuk Müdürü + Bilgi Güvenliği Yöneticisi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (Kurul standart metin güncellemesi, yeni alıcı, sektörel değişiklik)
İlgili Mevzuat: KVKK m.9/4-(c); Kurul'un 04.06.2024 tarihli ve 2024/959 sayılı kararı
---

# Standart Sözleşme Rehberi

## 1. Hukuki Çerçeve

KVKK m.9/4-(c) uyarınca, yeterli korumanın bulunmadığı ülkelere kişisel veri aktarımı, **Kurul tarafından ilan edilen standart sözleşmenin** taraflar arasında akdedilmesi ve Kurum'a bildirilmesi koşuluyla yapılabilir. Standart sözleşme; veri kategorileri, aktarım amaçları, alıcı ve alıcı grupları, alıcı tarafından alınacak teknik ve idari tedbirler ile özel nitelikli kişisel veriler için alınan ek önlemleri içerir.

Kurul'un **04.06.2024 tarihli ve 2024/959 sayılı kararı** ile dört türde standart sözleşme metni yayımlanmıştır.

## 2. Standart Sözleşmenin Yapısı

Standart sözleşme tipik olarak aşağıdaki bölümlerden oluşur:

| Bölüm | İçerik |
|-------|--------|
| Başlangıç | Tarafların kimliği, sözleşmenin amacı, tanımlar |
| Aktarımın kapsamı | Veri kategorileri, ilgili kişi grupları, işleme amaçları, alıcılar, alıcı ülke |
| Tarafların yükümlülükleri | Veren tarafın ve alan tarafın yükümlülükleri |
| Veri sahibi hakları | İlgili kişinin hakları, haklarını kullanma yolu, üçüncü taraf yararlandırma |
| Teknik ve idari tedbirler | Şifreleme, erişim kontrolü, ihlal yönetimi, denetim |
| Özel nitelikli veriler | Ek tedbirler |
| Alt-işleyenler | Alt-işleyen kullanımı, izin, zincir sorumluluk |
| Sözleşme süresi ve sona erme | Süre, sona erme nedenleri, sona erince imha/iade |
| Sorumluluk ve tazminat | Karşılıklı tazminat hükümleri |
| Uygulanacak hukuk | Türkiye Cumhuriyeti hukuku |
| Yargı yeri | Türk mahkemeleri |
| Ekler | Aktarım kategorileri tablosu, teknik+idari tedbirler tablosu, alt-işleyen listesi |

## 3. Sözleşme Türleri ve Seçim

### 3.1. Dört Tür

| Kod | Türkiye Tarafı | Yurt Dışı Tarafı | Tipik Senaryo |
|-----|----------------|-------------------|---------------|
| Tip 1 | Veri Sorumlusu (VS) | Veri Sorumlusu (VS) | Grup şirketleri arası aktarım (BCR yoksa); ortak müşteri portföyü |
| Tip 2 | Veri Sorumlusu (VS) | Veri İşleyen (Vİ) | SaaS sağlayıcı, bulut sağlayıcı, çağrı merkezi outsourcing |
| Tip 3 | Veri İşleyen (Vİ) | Veri İşleyen (Vİ) | Türkiye'deki bulut sağlayıcının yurt dışı alt-işleyene aktarımı |
| Tip 4 | Veri İşleyen (Vİ) | Veri Sorumlusu (VS) | Türkiye'deki veri işleyenin yurt dışı veri sorumlusuna geri aktarımı |

### 3.2. Tür Seçim Kriteri

Statü tespiti **aktarımın yönü ve tarafların KVKK statüsü**ne göre yapılır. Yanlış tür kullanımı sözleşmenin geçersizliğine yol açar.

```
Aktarımı veren taraf kim?
+----------------+----------------+
|                                 |
v                                 v
Türkiye'deki                Türkiye'deki
Veri Sorumlusu              Veri İşleyen
|                                 |
v                                 v
Alan taraf kim?            Alan taraf kim?
+--------+                  +--------+
|        |                  |        |
v        v                  v        v
VS       Vİ                 Vİ       VS
|        |                  |        |
v        v                  v        v
Tip 1   Tip 2              Tip 3   Tip 4
```

## 4. Sözleşmenin İmzalanması

### 4.1. İmza Süreci

```
1. Tedarikçi/Alıcı ile statü ve aktarım kapsamı
   netleştirilir.
                |
                v
2. Doğru sözleşme türü seçilir (Hukuk Müdürlüğü
   onayı).
                |
                v
3. Standart metin değiştirilmeden ekler doldurulur:
   - Aktarım kapsamı (veri kategorisi, amaçlar)
   - Teknik+idari tedbirler
   - Alt-işleyen listesi
                |
                v
4. Hukuk Müdürlüğü gözden geçirir; ek hükümler
   varsa standart metni değiştirmeyecek şekilde
   ayrı ek olarak eklenir.
                |
                v
5. Bilgi Güvenliği teknik tedbirlerin somut ve
   doğru olduğunu doğrular.
                |
                v
6. Tarafların yetkilileri imzalar (e-imza veya
   ıslak imza).
                |
                v
7. İmza tarihinden itibaren 5 iş günü içinde
   Kurum'a bildirim yapılır.
                |
                v
8. Sözleşme arşive alınır; aktarım envanterine
   ve VERBİS'e yansıtılır.
```

### 4.2. İmza Şekli

- **E-imza:** 5070 sayılı E-İmza Kanunu kapsamında nitelikli elektronik imza.
- **Islak imza:** Kağıt sözleşme, taraf yetkililerinin elle imzası.
- **Yetki:** İmzalayan kişinin tüzel kişilik adına imza yetkisinin bulunması gerekir; imza sirküleri kontrolü yapılır.
- **Apostil/tasdik:** Yurt dışı tarafın imzası için, ülkeye göre apostil veya konsolosluk tasdiki istenebilir; pratikte taraflar karşılıklı PDF imza ile yetiniyor.

### 4.3. Sözleşmeden Sapma Yasağı

Standart sözleşme metni **değiştirilemez**. Aşağıdaki müdahaleler sözleşmenin geçersizliğine yol açar:

- Maddenin silinmesi,
- Maddenin değiştirilmesi (kelime değişikliği dahil),
- Tarafların yükümlülüklerinin azaltılması,
- Yargı yerinin Türkiye dışına taşınması,
- Uygulanacak hukukun değiştirilmesi.

İzin verilen müdahale:
- **Ekler doldurulur** (aktarım kapsamı, teknik tedbirler, alt-işleyen).
- **Ek hükümler ayrı bir ek protokol olarak eklenebilir**, **standart metnin maddelerini değiştirmemek** kaydıyla.

### 4.4. Çoklu Aktarım

- **Aynı taraflar arası birden fazla aktarım:** Tek bir çerçeve standart sözleşme imzalanabilir; ekte tüm aktarım kapsamları listelenir.
- **Farklı taraflar:** Her taraf çifti için ayrı sözleşme.

## 5. Kurum'a Bildirim

### 5.1. Süre

İmza tarihinden itibaren **5 iş günü** içinde bildirim yapılır.

### 5.2. Bildirim Yöntemi

Kurum'un belirlediği elektronik kanal kullanılır. Bildirim genellikle:

- VERBİS / Sicil portalı üzerinden,
- veya Kurum'un duyurduğu ayrı bildirim sistemi üzerinden,
- veya KEP yolu ile (Kurum'un kabul etmesi kaydıyla).

### 5.3. Bildirim İçeriği (Tipik)

| Alan | Açıklama |
|------|----------|
| Veren tarafın bilgileri | Unvan, adres, VERBİS kayıt no |
| Alan tarafın bilgileri | Unvan, adres, ülke |
| Sözleşme türü | Tip 1/2/3/4 |
| İmza tarihi | DD/MM/YYYY |
| Aktarımın amacı | Kısa açıklama |
| Aktarım veri kategorileri | Liste |
| İlgili kişi grupları | Liste |
| Aktarım süresi | Sözleşme süresi |
| Sözleşme metninin kendisi | PDF eki |

### 5.4. Bildirimin Hukuki Niteliği

- Bildirim **izin DEĞİLDİR**. Kurum'un onayı gerekmez.
- Bildirim, uygun güvencenin **şartı**dır. Bildirim yapılmaması, sözleşmenin imzalanmış olmasına rağmen aktarımın **uygun güvence olmaksızın yapılmış sayılmasına** yol açar.
- Bildirim eksik ise Kurum ek bilgi isteyebilir.

### 5.5. Sonradan Değişiklik

- Sözleşme tarafları, kapsam, alıcı ülke gibi temel unsurlar değişirse, **yeni** sözleşme veya **ek protokol** akdedilir; 5 iş günü içinde yeniden bildirim yapılır.
- Sözleşmenin sona ermesi veya feshi de bildirilir.

## 6. Aktarım Etki Değerlendirmesi (TIA — Transfer Impact Assessment)

Standart sözleşme tek başına yeterli olmayabilir; alıcı ülkenin hukuku ve uygulaması, sözleşmesel hükümlerin fiilen uygulanmasını engelleyebilir. TIA, bu olasılığı değerlendirir ve gerekli **ek tedbirler**i belirler.

### 6.1. TIA Aşamaları

```
Aşama 1: Aktarımın Haritalanması
- Veri kategorileri, kategori sayıları, hassasiyet
- İlgili kişi grupları
- Aktarım amacı, sıklık, süre
- Aktarımı veren ve alan; alan ülke; alıcının altında
  alt-işleyen var mı?

                |
                v

Aşama 2: Alıcı Ülkenin Hukuku ve Uygulaması
- Veri koruma mevzuatı (var mı, kapsamı?)
- Bağımsız denetim otoritesi
- İlgili kişi haklarının uygulanabilirliği
- Yargısal koruma yolları
- Uluslararası anlaşmalara taraf olma

                |
                v

Aşama 3: Kamu Otoritesi Erişimi
- İstihbarat servisi erişimi
- Kolluk erişimi
- Vergi/mali otoriteler
- Erişim için gözetim mekanizması var mı?
- "Disproportionate" erişim riski
- Aktarımın gerçekleştiği sektör için spesifik yetkiler

                |
                v

Aşama 4: Sözleşmenin Yeterliliği
- Standart sözleşme + ek hükümler birlikte yeterli mi?
- Alıcı taraf, sözleşmesel taahhütlerine fiilen
  uyabilecek mi (yerel hukuk engellemiyor mu)?

                |
                v

Aşama 5: Ek Tedbirler
- Teknik: end-to-end şifreleme, anahtar yönetimi
  (kaynakta), pseudonymization, veri minimizasyonu
- Sözleşmesel: ek bildirim yükümlülükleri,
  notification of access requests, audit hakkı
- Organizasyonel: erişim sınırlaması, "need-to-know",
  log + denetim

                |
                v

Aşama 6: Kalan Risk Değerlendirmesi
- Risk azaltıldıktan sonra kalan risk kabul edilebilir mi?
- Kabul edilemiyorsa: aktarım yapılmaz / başka yol seçilir
```

### 6.2. Tipik Ek Tedbirler

| Risk | Ek Tedbir |
|------|-----------|
| Alıcı ülkenin kamu otoritesi disproportionate erişim talebi | End-to-end şifreleme + anahtarın Türkiye'de tutulması |
| Alıcı ülkede yargısal koruma zayıf | Sözleşmede üçüncü taraf yararlandırma + Türk mahkemesi yetkisi |
| Alt-işleyen zinciri uzun ve şeffaf değil | Alıcının onaylı alt-işleyen listesi + her değişikliğin önceden bildirilmesi |
| İhlal halinde bildirim gecikmesi | Sözleşmede 24 saat içinde bildirim yükümlülüğü |
| Kamu otoritesi erişim talebinde bilgi verilmemesi | "Notification of access requests" maddesi (yerel hukuk izin verdiği ölçüde) |
| Pseudonymization olmaksızın hassas veri | Kaynakta pseudonymization, anahtar Türkiye'de kalır |
| Veri minimizasyonu yetersiz | Aktarım öncesi minimizasyon, sadece gerekli alanlar |

### 6.3. TIA Şablonu Kısa Form

```
TIA — Aktarım Etki Değerlendirmesi
═════════════════════════════════════
TIA No                : ________________
Tarih                 : ____/____/______
Aktarımı Yapan        : ________________
Alıcı                 : ________________
Alıcı Ülke            : ________________
Alıcı Statü (VS/Vİ)   : ________________
Sözleşme Türü         : Tip __

1. AKTARIMIN HARİTASI
   Veri Kategorileri  : ________________
   Hassasiyet         : Genel / Özel nitelikli
   İlgili Kişi Grupları: ________________
   Aktarım Sıklığı    : Sürekli / Periyodik / Tek
   Aktarım Süresi     : ________________

2. ALICI ÜLKENİN HUKUKU
   Veri Koruma Mevzuatı: ____________________
   Denetim Otoritesi  : ____________________
   İlgili Kişi Hakları : Var / Sınırlı / Yok
   Yargı Yolu         : Var / Sınırlı / Yok

3. KAMU OTORİTESİ ERİŞİM RİSKİ
   İstihbarat         : Düşük / Orta / Yüksek
   Kolluk             : Düşük / Orta / Yüksek
   Disproportionate
   erişim riski       : Düşük / Orta / Yüksek

4. EK TEDBİRLER
   Teknik             : ____________________
   Sözleşmesel        : ____________________
   Organizasyonel     : ____________________

5. KALAN RİSK
   Risk Seviyesi      : Düşük / Orta / Yüksek
   Kabul Edilebilirlik : Evet / Hayır
   Karar              : Aktar / Aktarma / Yeni
                        tedbir gerekiyor

6. ONAY
   KVKK Sorumlusu     : ____________________
   Hukuk Müdürü       : ____________________
   Bilgi Güv. Yön.    : ____________________
```

Tam form için: [aktarim-degerlendirme-formu.md](aktarim-degerlendirme-formu.md)

## 7. Tipik Hatalar

| Hata | Sonuç | Önlem |
|------|-------|-------|
| Standart metni değiştirme (sözleşmeden sapma) | Sözleşme geçersiz; aktarım uygun güvence olmaksızın | Standart metin **değişmez**; sadece ekler doldurulur |
| Yanlış tür seçimi | Sözleşme geçersiz | Karar ağacı + Hukuk Müdürlüğü onayı |
| 5 iş günü içinde bildirim yapılmaması | Uygun güvence sağlanmamış | İmza akış sürecine zorunlu adım |
| TIA yapılmadan aktarım | Ek tedbirler eksik; risk değerlendirilmemiş | Her aktarım için TIA zorunlu |
| Alt-işleyen zincirinin ele alınmaması | Sorumluluk boşluğu | Alt-işleyen listesi + her değişiklikte güncelleme |
| İmza yetkisi kontrolsüz | Sözleşme geçersiz | İmza sirküleri kontrolü; kurumsal yetki teyidi |
| Çoklu aktarım için tek tek sözleşme | Operasyonel maliyet, gözden kaçma | Tek çerçeve sözleşme + ek liste |
| Standart sözleşme yerine kendi metnini kullanmak | Uygun güvence değildir; m.9/4-(ç) taahhütname yolu izlenmeli | Standart sözleşme şart; aksi halde Kurul izni |
| Sözleşmenin sona ermesinin bildirilmemesi | Aktarım envanteri ve VERBİS uyumsuzluk | Sona erme de bildirilir |

## 8. Operasyonel İş Akışı (Süreç Sahipleri)

| Adım | Sorumlu | Süre |
|------|---------|------|
| Tedarikçi statü tespiti | KVKK Sorumlusu + Hukuk | 2 iş günü |
| Sözleşme türü seçimi | Hukuk Müdürlüğü | 1 iş günü |
| Ekler doldurma | İlgili Birim + Bilgi Güvenliği | 3 iş günü |
| TIA hazırlama | KVKK Sorumlusu + Bilgi Güvenliği | 5 iş günü |
| Hukuki gözden geçirme | Hukuk Müdürlüğü | 3 iş günü |
| İmza | Yetkili imzacı | 1-2 iş günü |
| Kuruma bildirim | KVKK Sorumlusu | İmzadan sonra **5 iş günü içinde** |
| Envanter ve VERBİS güncelleme | KVKK Sorumlusu | 2 iş günü |
| Aydınlatma metni güncelleme | KVKK Sorumlusu + İlgili Birim | 5 iş günü |

Toplam idealde **20-25 iş günü**; karmaşık aktarımlar için 4-6 hafta.

## 9. Standart Sözleşme Yönetim Kayıtları

Her sözleşme için aşağıdaki kayıt tutulur:

| Alan | Açıklama |
|------|----------|
| Sözleşme No | Şirket içi sıra (ör. STD-2026-0042) |
| Tür | Tip 1/2/3/4 |
| Karşı taraf | Unvan, ülke, adres |
| İmza tarihi | DD/MM/YYYY |
| Yürürlük tarihi | DD/MM/YYYY |
| Sona erme tarihi | DD/MM/YYYY (varsa) |
| Kuruma bildirim tarihi | DD/MM/YYYY |
| TIA No | Bağlı TIA referansı |
| VERBİS güncellendi | Evet / Hayır |
| Aydınlatma güncellendi | Evet / Hayır |
| Ek protokoller | Liste |
| İmzacı | Şirket adına imza atan kişi |
| Sözleşme PDF | Arşiv referansı |
