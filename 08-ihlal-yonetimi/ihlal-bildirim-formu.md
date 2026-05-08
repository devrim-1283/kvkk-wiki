---
Doküman: Kurul'a Kişisel Veri İhlal Bildirim Formu (Doldurulabilir)
Bölüm: 08-ihlal-yonetimi
Sahip: KVKK Sorumlusu
Onaylayan: Hukuk Müdürü + KVKK Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + Kurul form değişikliklerinde
İlgili Mevzuat: 6698 sayılı KVKK m.12/5, KVKKK 24.01.2019/2019-10 sayılı Kararı, KVKK Veri Güvenliği Rehberi
---

# Kişisel Veri İhlal Bildirim Formu

> **Kullanım:** Bu form Kurul'un resmî "Kişisel Veri İhlal Bildirim Formu" şablonu ile içerik olarak paraleldir. KVKK Sorumlusu, ihlal anında bu formu doldurarak Kurul'un web portalına (ihlalbildirim.kvkk.gov.tr) ya da KEP üzerinden yükler. Doldurulmuş örnek için §3'e bakınız.

## 1. Form Yapısı

```
┌─────────────────────────────────────────────────────┐
│ BÖLÜM A — Veri Sorumlusu Kimlik Bilgileri           │
│ BÖLÜM B — İhlal Özeti ve Zaman Çizgisi              │
│ BÖLÜM C — Etkilenen Kişisel Veri                    │
│ BÖLÜM D — Saldırı Vektörü ve Tespit                 │
│ BÖLÜM E — Alınan Tedbirler                          │
│ BÖLÜM F — İlgili Kişi Bildirim Planı                │
│ BÖLÜM G — Kök Neden Analizi (Aşamalı)               │
│ BÖLÜM H — Düzeltici/Önleyici Aksiyon (CAPA)         │
│ BÖLÜM İ — Öğrenilen Dersler                         │
│ BÖLÜM J — Ekler                                     │
└─────────────────────────────────────────────────────┘
```

## 2. Form Şablonu (Doldurulabilir)

---

### BÖLÜM A — VERİ SORUMLUSU KİMLİK BİLGİLERİ

| Alan | İçerik |
|------|--------|
| Veri sorumlusu unvanı | |
| Vergi numarası / Mersis No | |
| Faaliyet alanı (NACE kodu) | |
| Çalışan sayısı (ihlal anı) | |
| Yıllık mali bilanço (TL) | |
| VERBİS sicil numarası | |
| Adres | |
| KEP adresi | |
| Telefon | |
| İrtibat kişisi (KVKK Sorumlusu) | |
| İrtibat e-posta | |
| İrtibat telefon (cep) | |
| Yurt dışı veri sorumlusu mu? | Evet / Hayır |
| (Evet ise) Veri sorumlusu temsilcisi | |

---

### BÖLÜM B — İHLAL ÖZETİ VE ZAMAN ÇİZGİSİ

| Alan | İçerik |
|------|--------|
| Olay numarası (iç) | OLAY-YYYY-NNNN |
| İhlalin gerçekleştiği tahmini tarih | YYYY-AA-GG SS:DD (TRT) |
| Veri sorumlusunun ihlali öğrendiği tarih (T+0) | YYYY-AA-GG SS:DD (TRT) |
| Bildirim tarihi | YYYY-AA-GG SS:DD (TRT) |
| Geçen süre (saat) | |
| 72 saati aştı mı? | Evet / Hayır |
| Aştıysa gerekçe | |

**Zaman Çizgisi (Kronolojik):**

| Zaman | Olay |
|-------|------|
| YYYY-AA-GG SS:DD | (örn. SIEM alarmı, kullanıcı şikayeti, vb.) |
| YYYY-AA-GG SS:DD | (örn. Çekirdek CSIRT toplantısı) |
| YYYY-AA-GG SS:DD | (örn. Sınırlandırma uygulandı) |
| YYYY-AA-GG SS:DD | (örn. Kapsam belirlendi) |
| YYYY-AA-GG SS:DD | (örn. Bildirim hazırlandı) |

**Olay Özeti (3-5 cümle, Kurul okuyacak şekilde):**

> [Şirketimiz X tarihinde Y sistemi üzerinde Z türü bir saldırı/olay tespit etmiştir. Yapılan incelemede A kategorisindeki kişisel verilerin B sayıda ilgili kişiye ait kayıt bağlamında etkilendiği belirlenmiştir. Olay halen [aktif/sınırlandırılmış/sonlandırılmış] durumdadır.]

---

### BÖLÜM C — ETKİLENEN KİŞİSEL VERİ

#### C.1. İhlal Niteliği (Birden çok seçilebilir)
- [ ] Gizlilik ihlali (yetkisiz açığa çıkma)
- [ ] Bütünlük ihlali (yetkisiz değiştirme)
- [ ] Erişilebilirlik ihlali (yetkisiz silme/engelleme)

#### C.2. Etkilenen İlgili Kişi Sayısı
| | Tahmini | Nihai |
|---|---------|-------|
| Müşteri | | |
| Çalışan | | |
| Tedarikçi temsilcisi | | |
| Aday | | |
| Web sitesi ziyaretçisi | | |
| Diğer (belirtiniz) | | |
| **Toplam** | | |

#### C.3. Etkilenen Kayıt Sayısı
> Kayıt sayısı kişi sayısından farklı olabilir. Örn. 1 kişiye ait 10 fatura → 1 kişi, 10 kayıt.

| Veri tabanı / sistem | Kayıt sayısı |
|----------------------|--------------|
| | |

#### C.4. Etkilenen Veri Kategorileri

**Genel Nitelikli:**
- [ ] Kimlik (ad-soyad, T.C. no, doğum tarihi)
- [ ] İletişim (telefon, e-posta, adres)
- [ ] Müşteri işlem (sipariş, fatura, ödeme — kart maskeli)
- [ ] Finansal (IBAN, kredi limiti)
- [ ] Pazarlama (tercih, segmentasyon)
- [ ] Lokasyon (GPS, IP)
- [ ] İşlem güvenliği (parola — hash/clear)
- [ ] Görsel/işitsel (fotoğraf, ses, video)
- [ ] Mesleki (özgeçmiş, eğitim, çalışma geçmişi)
- [ ] Diğer (belirtiniz):

**Özel Nitelikli (KVKK m.6):**
- [ ] Sağlık verileri
- [ ] Cinsel hayat
- [ ] Irk / etnik köken
- [ ] Siyasi düşünce
- [ ] Felsefi inanç / din / mezhep / diğer inanç
- [ ] Kılık-kıyafet
- [ ] Dernek / vakıf / sendika üyeliği
- [ ] Ceza mahkûmiyeti / güvenlik tedbirleri
- [ ] Biyometrik / genetik

#### C.5. Veri Yayımlandı mı?
- [ ] Hayır (sadece yetkisiz erişim, sızıntı dışarıda yok)
- [ ] Bilinmiyor / araştırılıyor
- [ ] Evet — kanıt var (URL, ekran görüntüsü)
   - Yayım yeri: ____________________
   - Erişim engeli talep edildi mi? Evet / Hayır

#### C.6. Şifrelenmiş / Pseudonymized mıydı?
- [ ] Tam şifreli (AES-256, anahtar etkilenmedi)
- [ ] Pseudonymized (kimlik referansı ayrı)
- [ ] Açık (clear-text)
- [ ] Karma — açıklayınız

---

### BÖLÜM D — SALDIRI VEKTÖRÜ VE TESPİT

#### D.1. İhlal Kategorisi
- [ ] Siber saldırı
   - [ ] Ransomware
   - [ ] BEC / kimlik avı / hesap ele geçirme
   - [ ] Web uygulaması istismarı (SQLi, IDOR, RCE)
   - [ ] DDoS sonrası veri sızdırma
   - [ ] Yazılım açığı (CVE: ____________)
   - [ ] Tedarik zinciri saldırısı
- [ ] İçeriden (insider)
   - [ ] Kasıtlı (eski/aktif çalışan, yüklenici)
   - [ ] Kasıtsız (yanlış e-posta, hatalı paylaşım)
- [ ] Fiziksel
   - [ ] Çalıntı/kayıp dizüstü/USB/telefon
   - [ ] Arşiv hırsızlığı
   - [ ] Doğal afet / yangın / su baskını
- [ ] Üçüncü taraf (veri işleyen)
- [ ] Web scraping / yetkisiz veri toplama
- [ ] Yapılandırma hatası (S3 bucket public, vb.)
- [ ] Diğer:

#### D.2. Saldırı Vektörü Detayı (Teknik)
- Giriş yöntemi:
- Yatay hareket:
- Yükselme (privilege escalation):
- Veri toplama yöntemi:
- Veri çıkarma yöntemi (exfil):
- IOC'ler (IP, hash, domain):

#### D.3. Tespit Yöntemi
- [ ] SIEM korelasyon kuralı (kural adı: ____________)
- [ ] EDR/XDR alarmı
- [ ] DLP olayı
- [ ] IDS/IPS
- [ ] Honeypot/canary
- [ ] Çalışan ihbarı
- [ ] Müşteri/kullanıcı şikayeti
- [ ] Üçüncü taraf bildirimi (CERT, araştırmacı, basın)
- [ ] Veri işleyen bildirimi
- [ ] Dark web izleme
- [ ] Tesadüfi (denetim, başka olay araştırması)
- [ ] Diğer:

---

### BÖLÜM E — ALINAN TEDBİRLER

#### E.1. Acil Sınırlandırma (T+0 - T+24 saat)
| Tedbir | Saat (TRT) | Sahip | Sonuç |
|--------|-----------|-------|-------|
| | | | |

#### E.2. Teknik Tedbirler
- [ ] Etkilenen sistem ağdan izole edildi
- [ ] Etkilenen kullanıcı hesapları disable
- [ ] Parola sıfırlama (kapsam: ____________)
- [ ] MFA token iptali / sıfırlama
- [ ] API anahtar / sertifika rotasyonu
- [ ] Açık kapatıldı / yama uygulandı (CVE: ____________)
- [ ] Yedekten temiz geri yükleme
- [ ] EDR ile tüm filo IOC taraması
- [ ] WAF / firewall kuralı eklendi
- [ ] Forensik imaj alındı
- [ ] Diğer:

#### E.3. İdari Tedbirler
- [ ] CSIRT aktivasyonu (seviye: ____)
- [ ] Yönetim eskalasyonu
- [ ] Hukuk / Sigorta bildirimi
- [ ] İçeriden ihlal — disiplin / iş akdi feshi süreci
- [ ] Veri işleyen ile sözleşmesel yaptırım
- [ ] Tüm çalışanlara hatırlatma duyurusu
- [ ] Diğer:

#### E.4. Sürdürülen / Önerilen Tedbirler
> Kısa ve uzun vadede planlanan kalıcı önlemler.

---

### BÖLÜM F — İLGİLİ KİŞİ BİLDİRİM PLANI

| Alan | İçerik |
|------|--------|
| Bildirim yapılacak mı? | Evet / Hayır (Hayır ise gerekçe) |
| Bildirim yöntemi | E-posta / SMS / KEP / Posta / Web banner / Basın |
| Çift kanal kullanımı | Evet / Hayır |
| Tahmini ilk bildirim tarihi | YYYY-AA-GG |
| Tahmini tamamlanma tarihi | YYYY-AA-GG |
| Bildirim metni hazır mı? | Evet (ek olarak verildi) / Hazırlanıyor |
| İlgili kişi destek hattı kuruldu mu? | Evet / Hayır |
| Ücretsiz koruma hizmeti sunuluyor mu? | Evet (örn. kredi izleme) / Hayır |

---

### BÖLÜM G — KÖK NEDEN ANALİZİ (AŞAMALI — İLK BİLDİRİMDE EKSİK OLABİLİR)

| Aşama | İçerik |
|-------|--------|
| Doğrudan neden | |
| Kolaylaştırıcı faktör (insan) | |
| Kolaylaştırıcı faktör (süreç) | |
| Kolaylaştırıcı faktör (teknik) | |
| Sistemik kök neden | |

> RCA detayları için bkz. `kok-neden-analizi.md` ekteki tam rapor.

---

### BÖLÜM H — DÜZELTİCİ / ÖNLEYİCİ AKSİYON (CAPA)

| Aksiyon | Tip (D/Ö) | Sahip | Hedef Tarih | Durum |
|---------|-----------|-------|-------------|-------|
| | | | | |

---

### BÖLÜM İ — ÖĞRENİLEN DERSLER

> 5-10 madde, gelecek tatbikat senaryosuna ve eğitim güncellemesine girecek netlikte.

1.
2.
3.

---

### BÖLÜM J — EKLER

- [ ] Forensik özet raporu (PDF)
- [ ] İlgili kişi bildirim metni taslağı (e-posta + SMS + web)
- [ ] Sigortacı bildirim onayı
- [ ] Karakola ihbar tutanağı (gerekiyorsa)
- [ ] Veri işleyen sözleşme yaptırım yazısı
- [ ] Ekran görüntüleri / IOC listesi
- [ ] Veri kategori-sayı detay tablosu
- [ ] Diğer:

**Form Doldurma:**

| Alan | İçerik |
|------|--------|
| Formu dolduran | (Ad-Soyad, ünvan) |
| Tarih | YYYY-AA-GG |
| KVKK Sorumlusu onayı | (İmza / KEP) |
| Hukuk Müdürü onayı | (İmza / KEP) |

---

## 3. Doldurulmuş Örnek: Ransomware ile Çalışan IK Verisi Sızıntısı

### BÖLÜM A
| Alan | İçerik |
|------|--------|
| Veri sorumlusu unvanı | ABC Sanayi ve Ticaret A.Ş. |
| Vergi numarası | 1234567890 |
| Faaliyet alanı | Otomotiv yan sanayi (NACE 29.32) |
| Çalışan sayısı | 612 |
| VERBİS sicil numarası | 12345-1 |
| Adres | OSB 3. Cadde No:5, Bursa |
| KEP adresi | abcsanayi@hs01.kep.tr |
| Telefon | +90 224 XXX XX XX |
| İrtibat kişisi | Ayşe Yılmaz, KVKK Sorumlusu |
| İrtibat e-posta | kvkk@abcsanayi.com.tr |
| İrtibat telefon | +90 532 XXX XX XX |
| Yurt dışı veri sorumlusu | Hayır |

### BÖLÜM B
| Alan | İçerik |
|------|--------|
| Olay numarası | OLAY-2026-0042 |
| İhlal tahmini tarihi | 2026-05-04 22:30 (TRT) |
| Öğrenme tarihi (T+0) | 2026-05-05 08:15 (TRT) |
| Bildirim tarihi | 2026-05-07 14:00 (TRT) |
| Geçen süre | 53 saat 45 dakika |
| 72 saati aştı mı? | Hayır |

**Zaman Çizgisi:**
| Zaman | Olay |
|-------|------|
| 2026-05-04 22:30 | İlk şüpheli RDP girişi (audit log) |
| 2026-05-04 23:15 | Yatay hareket — domain admin hesap kullanımı |
| 2026-05-05 03:00 | İK dosya sunucusunda toplu okuma |
| 2026-05-05 06:00 | Şifreleme başlıyor (LockBit varyantı) |
| 2026-05-05 08:00 | İlk çalışan dosyaya erişemediğini bildiriyor (helpdesk) |
| 2026-05-05 08:15 | SOC L2 ihlal şüphesini doğruluyor → **T+0** |
| 2026-05-05 08:45 | CISO + KVKK Sorumlusu + Hukuk haberdar |
| 2026-05-05 09:00 | CSIRT Seviye 3 aktivasyon |
| 2026-05-05 09:30 | Etkilenen sunucular ağdan izole |
| 2026-05-05 12:00 | Forensik imaj alımı tamamlandı |
| 2026-05-05 18:00 | Etkilenen veri kapsamı ön rapor: 612 çalışan IK dosyası |
| 2026-05-06 10:00 | Yedekten geri yükleme başladı |
| 2026-05-06 16:00 | Sigortacı bildirimi (siber poliçe aktivasyonu) |
| 2026-05-07 09:00 | İlgili kişi bildirim metni hazır |
| 2026-05-07 14:00 | **Kurul'a bildirim** |

**Olay Özeti:**
> "ABC Sanayi A.Ş.'nin İK dosya sunucusunda 4-5 Mayıs 2026 gecesi LockBit varyantı bir fidye yazılımı saldırısı tespit edilmiştir. Saldırgan, dış kaynak IT yüklenicisinin RDP hesabını parola sızıntısı yoluyla ele geçirmiş ve 612 çalışana ait özlük dosyalarına erişim sağlamıştır. Dosyalar şifrelenmeden önce kopyalandığına dair forensik delil bulunmaktadır. Etkilenen veriler: kimlik fotokopisi, IBAN, ücret bilgisi, sağlık raporları (özel nitelikli). Sistem 5 Mayıs sabahı izole edilmiş, temiz yedekten kurtarılmıştır. Etkilenen çalışanlara doğrudan bildirim hazırlanmaktadır."

### BÖLÜM C
| C.1 İhlal Niteliği | ☑ Gizlilik ☑ Erişilebilirlik |
| C.2 Etkilenen kişi | 612 çalışan (kesin) + 35 eski çalışan (toplam 647) |
| C.3 Kayıt sayısı | 5.847 doküman |
| C.4 Veri kategorileri | Genel: Kimlik, İletişim, Finansal (IBAN), Mesleki<br>Özel nitelik: **Sağlık raporları (işe giriş muayenesi, devamsızlık raporu)** |
| C.5 Yayımlandı mı? | Bilinmiyor — saldırgan dark web sızıntı sayfasına 7 gün geri sayım koymuştur, ödenmediği için yayım riski yüksektir. |
| C.6 Şifreli mi? | Açık (clear-text PDF, dosya sistemi BitLocker yoktu) |

### BÖLÜM D
| D.1 Kategori | ☑ Siber saldırı → Ransomware (LockBit) |
| D.2 Vektör | İlk giriş: dış kaynak IT yüklenici RDP hesabı (parola sızıntısı, MFA yoktu).<br>Yatay hareket: Mimikatz ile credential dump.<br>Veri çıkarma: rclone ile MEGA bulutuna 12 GB upload. |
| D.3 Tespit | EDR alarmı (LockBit imza) + çalışan helpdesk şikayeti |

### BÖLÜM E
| E.2 Teknik tedbirler | ☑ İzolasyon ☑ Hesap disable ☑ Parola reset (tüm yöneticiler) ☑ MFA zorunlu kılındı (RDP dahil) ☑ Yedekten temiz geri yükleme ☑ Forensik imaj ☑ Tüm filo EDR taraması ☑ WAF kuralları |
| E.3 İdari | ☑ CSIRT Seviye 3 ☑ YK bilgilendirme ☑ Hukuk + sigorta ☑ Yüklenici sözleşme askıya alındı |

### BÖLÜM F
- Bildirim yöntemi: KEP (kayıtlı çalışan e-posta) + SMS + İK görüşme
- İlk bildirim: 2026-05-09
- Tamamlanma: 2026-05-12
- Destek hattı: Çağrı merkezi 0850-XXX (KVKK uzman)
- Ücretsiz hizmet: Etkilenen çalışanlara 12 ay kredi izleme servisi

### BÖLÜM G (Aşamalı — ilk bildirimde)
- Doğrudan neden: Yüklenici hesabında MFA yokluğu + paylaşılan parola.
- İnsan: Yüklenici parola hijyeni eksik, çalışan farkındalık.
- Süreç: Üçüncü taraf erişim politikası MFA'yı opsiyonel bırakıyordu.
- Teknik: RDP dış erişim VPN arkasında değildi, network segmentasyonu zayıftı.
- Sistemik: Yüklenici güvenlik denetimi yıllık değil çeyreklik olmalı.

### BÖLÜM H (CAPA — özet)
| Aksiyon | Tip | Sahip | Hedef |
|---------|-----|-------|-------|
| Tüm uzaktan erişimde MFA zorunlu | Düzeltici | CISO | 2026-05-15 |
| RDP yalnız VPN arkasında | Düzeltici | Network | 2026-05-20 |
| Yüklenici güvenlik anketi yıllık → çeyreklik | Önleyici | Tedarik | 2026-06-01 |
| EDR tüm sunucular (kapsam %100) | Düzeltici | CISO | 2026-05-30 |
| Çalışan + yüklenici farkındalık eğitimi | Önleyici | İK + KVKK | 2026-06-15 |
| Yedek immutable olacak (S3 Object Lock) | Önleyici | Altyapı | 2026-07-01 |
| Sızıntı izleme servisi (dark web) | Önleyici | CISO | 2026-05-30 |

### BÖLÜM İ (Dersler — özet)
1. Üçüncü taraf erişimi en yüksek risk vektörümüz; sıfır güven (zero trust) modeli zorunlu.
2. MFA opsiyonel olamaz — istisnasız tüm dış erişim.
3. Yedeklerin immutable olmadığı durumda ransomware fidyeli pazarlık zemini bulur.
4. Olay tespiti EDR ile 9 saat erken yapılabilirdi — kural setlerini sıkılaştır.
5. İK dosyaları açık metin değil şifreli depolanmalı (file-level encryption).
6. Kriz iletişim metni 24 saatte hazırlanabildi — pre-approved şablon işe yaradı.

### BÖLÜM J Ekler
- ☑ Forensik özet rapor (Mandiant, 12 sayfa)
- ☑ İlgili kişi e-posta + SMS metni
- ☑ Sigortacı bildirim onayı
- ☑ IOC listesi (IP, hash, domain)
- ☑ Veri kategori-sayı tablosu

---

## 4. Form Saklama

- Doldurulmuş form **Kurul Yazışma Defteri**ne işlenir.
- Orijinal KEP delil zinciri sigortalı arşivde **10 yıl** saklanır.
- İç versiyonlar (taslak, redaksiyon) **silinmez** — denetim zinciri için saklanır.

## 5. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi |
