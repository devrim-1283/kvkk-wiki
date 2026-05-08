---
Doküman: Periyodik İmha Prosedürü
Bölüm: 04-veri-saklama-ve-imha
Sahip: KVKK Sorumlusu
Onaylayan: Hukuk Müdürü + Bilgi Güvenliği Yöneticisi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (mevzuat değişikliği, sistem değişikliği, ihlal sonrası)
İlgili Mevzuat: Yön. m.7, m.11, m.12; KVKK m.7, m.13
---

# Periyodik İmha Prosedürü

## 1. Amaç

Bu prosedür; Yönetmelik m.11 uyarınca veri sorumlusunun, kişisel verileri silme/yok etme/anonim hale getirme yükümlülüğünün ortaya çıktığı tarihi takip eden **ilk periyodik imha** işleminde resen imha yükümlülüğünün operasyonel olarak nasıl yerine getirileceğini düzenler. Ayrıca KVKK m.13 ve Yön. m.12 kapsamında ilgili kişi talepleri ile başlayan tetiklenmiş imha akışını tarif eder.

## 2. Yasal Süre Çerçevesi

### 2.1. Politikası Olan Veri Sorumlusu (Yön. m.11/1-2)

- İmha yükümlülüğü oluştuğu tarihi takip eden **ilk periyodik imha**da imha yapılır.
- Periyodik imha aralığı politikada belirlenir; **her halde 6 ayı geçemez**.
- En kötü senaryoda yükümlülük oluştuktan sonra azami 6 ay içinde imha tamamlanır.

### 2.2. Politikası Olmayan Veri Sorumlusu (Yön. m.11/3)

- Yükümlülüğün ortaya çıktığı tarihten itibaren **3 ay içinde** imha yapılır.

### 2.3. Kurul Tarafından Süre Kısaltma (Yön. m.11/4)

- Kurul; telafisi güç veya imkânsız zararların doğması ve açıkça hukuka aykırılık olması halinde süreleri kısaltabilir.

### 2.4. İlgili Kişi Talebi (Yön. m.12)

- İşleme şartlarının tamamı ortadan kalkmışsa: **30 gün** içinde sonuçlandırılır.
- Veri üçüncü kişiye aktarılmışsa: Üçüncü kişiye bildirim yapılır; üçüncü kişi nezdinde Yönetmelik kapsamında işlem yapılması temin edilir.
- İşleme şartları tamamen ortadan kalkmamışsa: KVKK m.13/3 uyarınca gerekçeli ret; ret cevabı 30 gün içinde yazılı/elektronik olarak iletilir.

## 3. İmha Takvimi

| Periyodik İmha No | Tetikleme Tarihi | Hazırlık Başlangıcı | Uygulama Pencerasi | Raporlama |
|-------------------|------------------|--------------------|--------------------|----------|
| Mayıs Periyodik İmhası | Her yıl 01 Mayıs | 15 Nisan | 01 Mayıs – 15 Mayıs | 31 Mayıs'a kadar Yönetim Kuruluna |
| Kasım Periyodik İmhası | Her yıl 01 Kasım | 15 Ekim | 01 Kasım – 15 Kasım | 30 Kasım'a kadar Yönetim Kuruluna |

## 4. Süreç Akışı (Periyodik İmha)

```
+--------------------------------------------------+
| ADIM 1: Tetikleme                                |
| Periyodik imha takvimi geldi                     |
| Sorumlu: KVKK Sorumlusu                          |
| Çıktı: Tetikleme bildirimi                       |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 2: Aday Listesi Oluşturma                   |
| Envanter taranır, süresi dolmuş kayıtlar çıkar.  |
| Sorumlu: BT Operasyon + İlgili Birimler          |
| Çıktı: İmha aday listesi (sistem, kategori,      |
| satır sayısı, tarih aralığı)                     |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 3: Hukuki Filtre — Legal Hold Kontrolü      |
| Hukuk Müdürlüğü, aday listeyi inceler:           |
| - Devam eden dava? Soruşturma? Inceleme?         |
| Sorumlu: Hukuk Müdürü                            |
| Çıktı: Onaylı imha listesi + Hold listesi        |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 4: Veri Sahibi Birim Onayı                  |
| Liste, ilgili birim yöneticisine gönderilir.     |
| Birim yöneticisi son ticari/operasyonel kontrol. |
| Sorumlu: Birim Yöneticisi                        |
| Çıktı: Birim onayı veya gerekçeli itiraz         |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 5: KVKK Sorumlusu Onayı                     |
| Toplam liste KVKK Sorumlusu tarafından onaylanır.|
| Yöntem (silme/yok etme/anonim) listede belirtilir|
| Sorumlu: KVKK Sorumlusu                          |
| Çıktı: Final imha listesi + yöntem matrisi       |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 6: Test Çalıştırması (Dry Run)              |
| Üretim öncesi staging'de imha jobu test edilir.  |
| Eski test: 100 kayıt; doğrulama; başarısızsa     |
| üretime geçilmez.                                |
| Sorumlu: BT Operasyon                            |
| Çıktı: Dry run raporu                            |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 7: İmha Uygulaması                          |
| Final liste sistem üzerinde uygulanır.           |
| - Aktif veritabanları                            |
| - Audit log içindeki kişisel veri                |
| - Bulut nesneleri                                |
| - Yedekler (rotasyon takvimine göre)             |
| - Replikasyon ortamları                          |
| - Yapılı/yapısız loglar                          |
| Sorumlu: BT Operasyon                            |
| Çıktı: Sistem logları, hash kanıtları            |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 8: Doğrulama                                |
| Bilgi Güvenliği bağımsız doğrulama yapar:        |
| - Örneklem ile imhanın gerçekleştiği kontrol     |
| - Yedek/replika doğrulama                        |
| Sorumlu: Bilgi Güvenliği                         |
| Çıktı: Doğrulama raporu                          |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 9: Tutanak Düzenleme                        |
| İmha kayıt tutanağı düzenlenir.                  |
| Sorumlu: KVKK Sorumlusu + İmha Yapan             |
| Çıktı: İmza atanmış tutanak                      |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 10: Onay Zinciri                            |
| Tutanaklar:                                      |
| - KVKK Sorumlusu (hazırlayan)                    |
| - Bilgi Güvenliği Yöneticisi (doğrulayan)        |
| - Hukuk Müdürü (hukuki uygunluk)                 |
| - İlgili Birim Müdürü (operasyonel uygunluk)     |
| Sorumlu: KVKK Sorumlusu                          |
| Çıktı: Onaylı tutanak                            |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 11: Arşivleme                               |
| Tutanak ve eki kanıtlar arşive alınır.           |
| Saklama süresi: en az 3 yıl (Yön. m.7(3))        |
| Sorumlu: KVKK Sorumlusu                          |
| Çıktı: Arşiv kaydı                               |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 12: Yönetim Kurulu Raporlaması              |
| Periyodik imha özet raporu üst yönetime sunulur. |
| Sorumlu: KVKK Sorumlusu                          |
| Çıktı: Yönetim Kurulu özet raporu                |
+--------------------------------------------------+
```

## 5. İlgili Kişi Talebi ile Tetiklenen İmha (Yön. m.12)

```
+--------------------------------------------------+
| ADIM 1: Başvurunun Alınması                      |
| Yazılı, KEP, e-posta veya başvuru formu kanalı   |
| ile talep alınır.                                |
| Süre Sayacı Başlar: T+0                          |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 2: Kayıt ve Atama (T+1 gün)                 |
| Talep KVKK başvuru sistemine kaydedilir.         |
| KVKK Sorumlusu sorumlu olarak atanır.            |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 3: Kimlik Doğrulama (T+3 gün)               |
| Başvuranın ilgili kişi olduğu teyit edilir.      |
| Vekilse vekaletname kontrolü.                    |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 4: Veri Tespiti (T+7 gün)                   |
| Hangi sistemlerde, hangi kategorilerde veri      |
| bulunduğu tespit edilir.                         |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 5: İşleme Şartı Değerlendirmesi (T+14 gün)  |
| KVKK m.5/m.6 şartlarının halen var olup          |
| olmadığı kontrol edilir.                         |
| - Tamamı sona erdi mi?  -> ADIM 6                |
| - Devam ediyor mu?      -> Gerekçeli ret         |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 6a: Üçüncü Kişi Tespiti (T+18 gün)          |
| Veri kimlere aktarılmış? Liste çıkarılır.        |
| Üçüncü kişiye Yön. m.12/1-b bildirimi yapılır.   |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 7: İmha Uygulaması (T+25 gün)               |
| Yöntem seçimi (m.7(5)): gerekçeli olarak         |
| seçilir, ilgili kişiye iletilir.                 |
| Aktif sistem + yedekler + log + replika.         |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 8: Tutanak ve Cevap (T+30 gün)              |
| Tutanak düzenlenir.                              |
| İlgili kişiye yazılı/elektronik cevap iletilir.  |
| Cevapta yöntem ve tarih belirtilir.              |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 9: Üçüncü Kişi Doğrulaması                  |
| Üçüncü kişiden imha teyidi alınır.               |
| Teyit ek olarak arşivlenir.                      |
+--------------------------------------------------+
```

### 5.1. 30 Gün Süresinin Hesaplanması

- Süre, başvurunun veri sorumlusuna ulaştığı **ilk gün**den itibaren işler.
- Resmi tatil / hafta sonu hesaba katılır; süre uzamaz.
- Başvuru ücreti gerektiriyorsa (Tebliğ kapsamı), ücret yatırılma tarihinden itibaren süre işler.
- Kimlik doğrulama için ek bilgi istenmişse, ek bilginin geldiği tarihten itibaren kalan süre işler (ancak süre durur, sıfırlanmaz).

## 6. Yedek ve Replikasyon İmha Stratejisi

Aktif veride yapılan silme **yedeğe ulaşmaz**. Yedek imha stratejisi politikaya bağlanır:

### 6.1. Strateji A — Yedek Rotasyonu Beklemek

- Aktif veride imha tarihinde "marker" konur.
- Yedek rotasyon takvimine göre yedek silindiğinde veri otomatik yok olur.
- Maksimum yedek tutma süresi politikada açıkça belirtilir (ör. 6 ay).
- İlgili kişi talebine cevapta "aktif sistemden silindi; yedek rotasyonu süresi sonunda tamamen yok edilecektir" beyanı verilir.

### 6.2. Strateji B — Yedek Anahtar İmhası (Crypto-Shred)

- Yedekler yazılırken her seferinde ayrı bir DEK (Data Encryption Key) ile şifrelenir.
- DEK'ler KMS'te tutulur.
- Yedek imha edilmek istendiğinde yalnızca DEK imha edilir; yedek matematik olarak okunamaz hale gelir.
- Hızlı, izlenebilir ve tutanaklı.

### 6.3. Strateji C — Tape / Soğuk Yedek Fiziksel İmha

- LTO bant veya optik soğuk yedek için degauss + parçalama.
- Tedarikçi sertifikası ile.

## 7. Log Dosyalarındaki Kişisel Verinin İmhası

- **Yapılı loglar:** İmha listesindeki kayıtların log içindeki kişisel alanları null/anonim yapılır; satırın kendisi denetim ihtiyacı için kalabilir.
- **Yapısız loglar:** Saklama süresi sonunda dosya tümüyle silinir.
- **SIEM:** İndeks bazlı yaşam döngüsü politikası; eski indeksler otomatik silinir.
- **Audit log:** Audit log'un kendisi delil değeri taşıdığı için imha edilmez; ancak içindeki kişisel veri, kayıt sona erince, denetim sürelerine sadık kalınarak temizlenir.

## 8. Kontroller ve Denetim

- **Aylık:** Retention job çıktıları, log temizleme raporları, hash sayısı.
- **Çeyreklik:** Politika ile envanter karşılaştırması; hold listesinin durumu.
- **Yıllık:** Bağımsız iç denetim; örneklem ile tutanak doğrulaması.
- **KPI'lar:**
  - Yükümlülük doğan veri sayısı / İmha edilen veri sayısı (>%95)
  - İlgili kişi talebi ortalama cevap süresi (<25 gün)
  - Açık hold dosya sayısı (<10)
  - Hatalı imha (yanlış kayıt) oranı (0)

## 9. Tutanak ve Kayıt Saklama

- Yön. m.7(3) — diğer hukuki yükümlülükler hariç **en az 3 yıl** saklanır.
- 3 yıllık asgari süre yerine kurum içi standart **5 yıl** olarak alınır (denetim ve dava süresi göz önünde bulundurularak).
- Tutanaklar elektronik imzalı olarak güvenli arşivde tutulur.

## 10. Tipik Hatalar ve Çözümler

| Hata | Çözüm |
|------|-------|
| İmha takvimi geldi ama aday listesi yok | Envanter sahipliği KVKK Sorumlusu'na verilir; aylık tarama otomatikleşir |
| Birim "verim lazım" diyerek imhayı erteler | Erteleme ancak somut hukuki sebep ile mümkündür; ticari fayda yetersiz |
| Hold gerekçesi belirsiz | Hold için yazılı gerekçe + Hukuk imzası zorunludur; hold kayıt sistemi tutulur |
| Üçüncü kişiye bildirim unutuldu | İmha akışında "üçüncü kişi tespiti" zorunlu adımdır; envanterdeki alıcı grubu bağı kullanılır |
| Yedek planlanmadı | Strateji A/B/C politikada seçilir; yedek imha takvimi periyodik imha takvimine bağlanır |
| Tutanak eksik | Tutanak şablonu kullanılır; eksik alan otomatik validasyonla bloklanır |
