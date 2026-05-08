---
Doküman: Biyometrik Veri Yönetimi (PDKS, Erişim, Ödeme, Yüz Tanıma)
Bölüm: 10-ozel-konular
Sahip: KVKK Sorumlusu + IT + İK + Bilgi Güvenliği
Onaylayan: Hukuk Müdürü + KVKK Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + Kurul kararları doğrultusunda
İlgili Mevzuat: 6698 sayılı KVKK m.6 (özel nitelikli); KVKK 31.01.2018 tarih 2018/10 sayılı "Özel Nitelikli Kişisel Verilerin İşlenmesinde Veri Sorumlularınca Alınması Gereken Yeterli Önlemler" Kararı; AYM E.2014/180; ECtHR mağdur içtihadı
---

# Biyometrik Veri Yönetimi

## 1. Tanım ve Kapsam

**Biyometrik veri:** Kişinin **fiziksel, fizyolojik veya davranışsal özelliklerinden** elde edilen ve o kişiyi **benzersiz şekilde tanımlamaya** yarayan veriler.

| Tip | Örnek |
|-----|-------|
| Fiziksel | Parmak izi, avuç içi venöz, retina, iris, yüz şablonu |
| Fizyolojik | DNA, ses tını profili, kalp ritmi |
| Davranışsal | Yürüyüş, klavye dokunma kalıbı, imza dinamiği |

KVKK m.6/1: **Biyometrik veri = özel nitelikli kişisel veri.**

## 2. Hukuki Çerçeve

### 2.1. KVKK m.6 İşleme Şartları

Özel nitelikli verilerin işlenmesi:

1. **Açık rıza** ile (m.6/2), VEYA
2. **Kanunlarda öngörülmesi** halinde (m.6/3 ile sağlık/cinsel hayat dışı; biyometrik için bu şart açık rızasız işlemeye ortam yaratabilir).

### 2.2. Kurul 2018/10 Kararı

Özel nitelikli veri işleyen veri sorumluları **yeterli önlemleri** almak zorundadır:
1. Politika ve prosedür hazırlamak (KVKK politika seti).
2. Çalışanlara düzenli eğitim, gizlilik sözleşmesi.
3. Yetki kontrol ve erişim politikası.
4. Yetki kapsam ve süresinin tanımlı olması.
5. Periyodik yetki kontrolü.
6. Görevden ayrılan çalışan yetki iptali.
7. Veriye erişen ortamın güvenliği (anti-virüs, güvenlik duvarı, vb.).
8. Verinin elektronik ortamda **kriptografik** yöntemle saklanması.
9. Anahtar yönetimi güvenli ortamda.
10. Aktarımın **şifreli** kanalla yapılması.
11. KEP veya kriptografi içeren yöntemler.
12. Fiziksel ortamda saklanan kişisel verilerin yetkisiz erişime karşı korunması.

> **Kritik:** Biyometrik veri **şifrelenmemiş** saklanırsa Kurul içtihadı doğrudan ihlal olarak değerlendirir.

## 3. Biyometrik Kullanım Senaryoları

### 3.1. Personel Devam Kontrol Sistemi (PDKS)

| Yöntem | KVKK Risk | Alternatif |
|--------|-----------|-----------|
| Manyetik kart | Düşük | — |
| Şifre / PIN | Düşük | — |
| Mobil uygulama (geofence) | Orta | GPS tartışmalı |
| Parmak izi | **Yüksek** (özel nitelikli) | Yukarıdakiler |
| Avuç içi venöz | **Yüksek** | Aynı |
| Yüz tanıma | **Yüksek** | Aynı |

**Kurul tutumu (2019, 2020 ve sonrası kararlar):** Biyometrik PDKS için **alternatif değerlendirilmesi** zorunlu. Eğer kart/şifre yeterliyse biyometrik kullanımı **orantısız** sayılır.

### 3.2. Fiziksel Erişim (Kapı, Kasa, Veri Merkezi)

- Düşük risk alanları: kart yeterli.
- Yüksek güvenlik (ARGE, kasa, veri merkezi): biyometrik gerekçe oluşturulabilir.
- Hibrit: kart + parmak izi (iki faktör).

### 3.3. Ödeme (Yüz/Parmak ile)

- Müşteri ödemesi (yüz/parmak ile) → açık rıza zorunlu.
- Apple Pay / Face ID gibi cihaz-yerleşik biyometri **cihazda** kalır → veri sorumlusu olarak Şirket'in işlemediği kabul edilir; ancak entegrasyonda dikkat.

### 3.4. Yetkilendirme (BYOD, Mobil Cihaz)

- Cihaz açma için biyometri = cihaz yereli, Şirket veri sorumlusu değil.
- Şirket sistemine biyometrik token ile giriş = veri sorumlusu Şirket; rıza + DPIA.

### 3.5. Çağrı Merkezi Ses Tını

- Ses tını ile kimlik doğrulama → biyometrik.
- Açık rıza + alternatif (parola, OTP) sunulması.
- Reddedenlere "ek güvenlik soru" yöntemi sunulur.

## 4. DPIA (Data Protection Impact Assessment) Zorunluluğu

KVKK Kurul rehberi yüksek riskli işlemelerde DPIA önerir; Kurul 2018/10 sayılı kararı + uluslararası iyi pratik biyometrik için DPIA'yı **fiilî zorunluluk** kılar.

### 4.1. DPIA Bölümleri

1. İşleme tanımı (sistem, veri, kişi sayısı, akış).
2. Hukuki sebep ve gerekliliği.
3. Orantılılık testi (alternatif analiz).
4. İlgili kişi hakları üzerindeki etki.
5. Riskler (sızıntı, dolandırıcılık, kimlik hırsızlığı, ayrımcılık).
6. Tedbirler (teknik + idari).
7. Kalan risk + kabul.
8. KVKK Komitesi onayı.

### 4.2. DPIA Tetikleyicileri

- Yeni biyometrik sistem kurulumu.
- Kapsam genişlemesi (örn. 100 → 600 çalışan).
- Yeni amaç eklenmesi (PDKS → erişim kontrolü).
- Sağlayıcı değişikliği.
- Yıllık gözden geçirme.

### 4.3. Şablon

DPIA şablonu için bkz. `99-sablonlar/dpia-sablonu.md`.

## 5. Açık Rıza Tasarımı

### 5.1. Çalışan Açık Rızası — Sınırlamalar

> Çalışanın işverene karşı verdiği rıza **özgürlük testi** ile değerlendirilir. KVKK Kurulu ve AYM tutumu: çalışan-işveren asimetrisi nedeniyle **rıza kolayca sakatlanır**.

Bu nedenle çalışan biyometrik kullanımında:
- **Alternatif yöntem** (kart, şifre) sunulmalı.
- Reddeden çalışanlar **olumsuz sonuç görmemelidir** (terfi, performans, uyarı).
- Rıza bireysel imzalı belge ile alınır, e-imza tercih.

### 5.2. Müşteri Açık Rızası

- Hizmet kullanımı için biyometrik **zorunlu** kılınamaz; alternatif sunulur.
- Rıza süreci aydınlatma + ayrı onay kutusu.
- Geri alma kolay (uygulama ayarlarından).

### 5.3. Rıza Metni Asgari Unsurlar

```
Bu kapsamda işlenecek biyometrik veriniz:
☐ Parmak izi şablonu (matematiksel hash)
☐ Yüz şablonu
☐ İris şablonu

İşleme amacı: ____________________
İşleme süresi: ____________________
Saklama biçimi: Şablon olarak (geri dönüştürülemez kriptografik dönüşüm),
                ham veri saklanmaz/silinir.

Alternatif yöntem: [kart / şifre / OTP] talep edebilirsiniz.

Açık rızamı vermek istiyorum: ☐ Evet ☐ Hayır
```

## 6. Şablon vs Ham Veri

### 6.1. Şablon (Template) Saklama

- Biyometrik özelliğin **matematiksel temsili** (vektör, hash, embedding).
- Tek yönlü dönüşüm — şablondan ham görüntü elde edilemez ideali.
- Modern sistemler şablon saklar (parmak izi minutiae, yüz embedding 128/512 boyutlu).

### 6.2. Ham Veri Saklama

- Parmak izi görüntüsü, yüz fotoğrafı, retina görüntüsü.
- **Kesinlikle önerilmez** — ihlal halinde geri alınamaz (parolanı değiştirebilirsin, yüzünü değiştiremezsin).
- Ham veri sadece ilk kayıt anında işlenir → şablon üretilir → ham veri **silinir**.

### 6.3. Şablonun Şifrelenmesi

- AES-256 GCM ile at-rest.
- Anahtar HSM (Hardware Security Module) veya KMS (Key Management Service).
- Anahtar rotation 12 ayda bir.
- Hesaplamalar şifreli ortamda mümkünse (homomorphic encryption — gelişmiş senaryo).

## 7. Sağlayıcı Seçimi

### 7.1. Tercih Kriterleri

- ISO/IEC 27001 + ISO/IEC 27701 (Privacy) sertifikası.
- ISO/IEC 19794 / 30107 (biyometrik standartlar) uyumu.
- FIDO Alliance, BSI, NIST sertifikaları.
- Türkiye'de yerleşik veri merkezi tercih (yurt dışı aktarım sorunu azalır).
- Kapalı kaynak değil — şeffaf işleyiş.
- Pen test + güvenlik denetim raporları.

### 7.2. DPA (Data Processing Agreement)

- KVKK m.12 uyumlu sözleşme.
- Veri işleyen yükümlülükleri.
- Alt-işleyen onay süreci.
- Veri sorumlusunun denetim hakkı.
- İhlal bildirim 24 saat içinde.
- Sözleşme sonu veri imha + sertifika.

## 8. Teknik Tedbirler

### 8.1. Çevrimiçi (Online) Karşılaştırma

- Şablonlar şifreli sunucuda.
- Karşılaştırma sunucu tarafında.
- Ağ TLS 1.3.
- API authentication + rate limit.

### 8.2. Cihaz Üstü (On-device)

- Şablon cihazda saklanır (smart card, mobile secure element).
- Sunucu sadece "match/no match" cevabını alır.
- Ağ riski en düşük; veri sorumlusu için **tercih edilir**.

### 8.3. Anti-spoofing

- Liveness detection (canlılık tespiti).
- 3D yüz tanıma (2D fotoğrafa dayanmaz).
- Parmak izi: nem/ısı/kapasitif sensör.
- Periyodik bypass testleri.

### 8.4. Yedekleme

- Şablon yedekleri **şifreli**.
- Yedekten geri yükleme audit'li.
- 3-2-1 strateji (3 kopya, 2 medya, 1 off-site).

## 9. İdari Tedbirler (Kurul 2018/10 Karar Maddeleri)

- Politika dokümanı (bu dosya).
- Yıllık eğitim — biyometrik veriye erişen tüm personel.
- Gizlilik sözleşmesi (NDA) — IT, İK, dış destek.
- Erişim matris (RBAC).
- Yetki gözden geçirme (çeyreklik).
- Ayrılan çalışan yetki iptali (24 saat).
- Erişim log denetimi.

## 10. Saklama Süresi

| Veri | Süre |
|------|------|
| Aktif çalışan şablonu | İş akdi süresince |
| Aktif müşteri şablonu | Hizmet süresince |
| Çalışan ayrıldıktan sonra | **Anında silme** (öner.); en geç 30 gün |
| Müşteri ilişki sonu | 30 gün içinde silme |
| Yedekler | Yedek rotasyon süresi |

İmha kanıtı (silme tutanağı) saklanır.

## 11. İlgili Kişi Hakları

- m.11/a-c: Hangi şablon hangi amaç → cevap basit.
- m.11/e: Silme talebi → hizmetten çıkış + alternatif yönteme geçiş ile aynı.
- m.11/f: Aktarım yapılmışsa bildirim.
- Şablon **kişiye geri verilemez** (matematiksel dönüşüm); ancak m.11/b kapsamında "şablon mevcut, X tarihinde oluşturuldu" bilgisi verilebilir.

## 12. Tipik Hatalar

| Hata | Doğru Yaklaşım |
|------|----------------|
| PDKS biyometrik tek seçenek | Alternatif (kart) zorunlu |
| Ham fotoğraf saklama | Şablon dönüşüm + ham silme |
| Açık rıza geri alma yok | Süreç tasarımı + alternatif |
| DPA yok / yetersiz | KVKK m.12 uyumlu sözleşme |
| Ayrılan çalışan şablonu kalıyor | 24 saat içinde silme |
| Şifrelenmemiş şablon | AES-256 + HSM |
| Anti-spoofing yok | Liveness zorunlu |
| Cihaz default parola | Değiştirme + MFA |
| DPIA yapılmamış | İlk kullanımdan önce zorunlu |
| Müşteri zorunlu biyometri | Alternatif sunulur |

## 13. KPI'lar

| KPI | Hedef |
|-----|-------|
| DPIA tamamlanma (her sistem) | %100 |
| Şablon şifreleme | %100 |
| Alternatif yöntem sunum oranı | %100 |
| Açık rıza geçerli oran | %100 |
| Ayrılan çalışan silme SLA | < 24 saat |
| Anti-spoofing test sıklığı | Yıllık 2 kez |
| Yetki gözden geçirme | Çeyreklik |

## 14. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi |
