---
Doküman: İmha Kayıt Tutanağı Şablonları
Bölüm: 04-veri-saklama-ve-imha
Sahip: KVKK Sorumlusu
Onaylayan: Hukuk Müdürü + Bilgi Güvenliği Yöneticisi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş
İlgili Mevzuat: Yön. m.7(3), m.7(4); KVKK m.12
---

# İmha Kayıt Tutanağı Şablonları

## 1. Tutanak Yükümlülüğü

Yön. m.7(3): "Kişisel verilerin silinmesi, yok edilmesi ve anonim hale getirilmesiyle ilgili yapılan bütün işlemler kayıt altına alınır ve söz konusu kayıtlar, diğer hukuki yükümlülükler hariç olmak üzere **en az üç yıl süreyle** saklanır."

Tutanak; imha yöntemini, kapsamını, sorumlularını ve kanıtlarını gösteren resmi belgedir. Tutanak olmaksızın yapılan imha, ispat yükümlülüğü açısından **yapılmamış sayılır**.

Yön. m.7(4): "Veri sorumlusu, kişisel verilerin silinmesi, yok edilmesi, anonim hale getirilmesi işlemiyle ilgili uyguladığı yöntemleri ilgili politika ve prosedürlerinde açıklamakla yükümlüdür."

## 2. Asgari İçerik

Her tutanakta aşağıdaki alanlar bulunmalıdır:

| Alan | Açıklama |
|------|----------|
| Tutanak No | Şirket içi tekil kimlik (yıl/sıra ör. 2026/IMHA-0142) |
| Tutanak Türü | Periyodik / İlgili Kişi Talebi / Tetiklenmiş / Tedarikçi |
| İşlem Tarihi | İmhanın yapıldığı tarih ve saat |
| İşlem Yeri | Fiziksel veya sistem adı |
| Veri Kategorisi | Hangi kişisel veri kategorisi (envanter referansı) |
| Hukuki Sebep | KVKK m.5/6 hangi şartı altında işleniyordu, hangi şartın sona ermesi imhayı tetikledi |
| Kapsam (Sayı/Ortam) | Etkilenen kayıt sayısı, ortam (DB/dosya/sunucu/medya) |
| Yöntem | Silme / Yok Etme / Anonim Hale Getirme — alt yöntem (DELETE, fiziksel parçalama, k-anonim, vb.) |
| Standart Atfı | Uygulanan teknik standart (NIST 800-88, DIN 66399 vb.) varsa |
| Kanıt Türü | Hash, log, foto, sertifika |
| Üçüncü Kişi Aktarımı | Veri aktarılmış mı? Bildirim yapıldı mı? |
| Tedarikçi | Şirket dışı imha hizmeti varsa tedarikçi adı + sertifika no |
| Sorumlu (Hazırlayan) | İmhayı uygulayan kişi (ad, unvan, imza) |
| Doğrulayan | Bilgi Güvenliği bağımsız doğrulama (ad, unvan, imza) |
| Onaylayan | KVKK Sorumlusu (ad, unvan, imza) |
| Hukuki Onay | Hukuk Müdürü (ad, unvan, imza) |
| Saklanma Süresi | Tutanağın asgari saklama süresi (en az 3 yıl) |
| Eki Belgeler | Sistem log, foto, sertifika, hash listesi |

## 3. Tutanak Numaralandırma Şeması

```
[YIL]/[YÖNTEM]/[SIRA]
örnek: 2026/IMHA-0142
       2026/PER-0007 (Periyodik İmha)
       2026/TLP-0023 (İlgili Kişi Talebi)
```

## 4. Tutanak Saklama

- Saklama süresi: Yön. m.7(3) — en az 3 yıl. Kurum içi standart: 5 yıl.
- Saklama formatı: Elektronik imzalı PDF + sistem audit log.
- Saklama yeri: KVKK Sorumlusu kontrolünde güvenli arşiv (erişim sınırlı, log kayıtlı).
- Saklama metaverisi: Tutanak no, tarih, kategori, sorumlu — aranabilir indekste.

---

## 5. Genel Tutanak Şablonu

```
══════════════════════════════════════════════════════
KİŞİSEL VERİ İMHA TUTANAĞI
══════════════════════════════════════════════════════

Tutanak No:        : ____________________________
Tutanak Türü       : [ ] Periyodik     [ ] İlgili Kişi Talebi
                     [ ] Tetiklenmiş   [ ] Tedarikçi İmhası
                     [ ] Diğer: __________________________

İşlem Tarihi/Saati : ____/____/______ — ___:___
İşlem Yeri         : ______________________________
                     (Fiziksel adres veya sistem adı)

──────────────────────────────────────────────────────
1. KAPSAMA İLİŞKİN BİLGİLER
──────────────────────────────────────────────────────
Veri Kategorisi    : __________________________________
                     (Envanter Madde No: __________)
Veri Sahibi Grup   : __________________________________
                     (Çalışan / Müşteri / Aday / Tedarikçi
                      / Ziyaretçi / Diğer)
Hukuki Sebep —
İşleme Şartı       : KVKK m.____ / m.____
                     Şartın Sona Erme Sebebi:
                     _________________________________
Kayıt Sayısı       : _________ kayıt
Tarih Aralığı      : ____/____/____ — ____/____/____
Ortam              : [ ] Aktif veritabanı
                     [ ] Yedek (rotasyon / soğuk)
                     [ ] Kağıt belge
                     [ ] Manyetik medya (HDD/Tape)
                     [ ] SSD/Flash medya
                     [ ] Optik medya
                     [ ] Bulut nesne depolama
                     [ ] Log/SIEM
                     [ ] Diğer: __________________

──────────────────────────────────────────────────────
2. UYGULANAN İMHA YÖNTEMİ
──────────────────────────────────────────────────────
Ana Yöntem         : [ ] Silme (Yön. m.8)
                     [ ] Yok Etme (Yön. m.9)
                     [ ] Anonim Hale Getirme (Yön. m.10)

Alt Yöntem         : ____________________________________
                     (DELETE/UPDATE, degauss, parçalama,
                      yakma, sanitize, crypto-shred,
                      k-anonim, generalization, vb.)

Uygulanan Standart : ____________________________________
                     (NIST 800-88 Purge/Destroy,
                      DIN 66399 P-4/P-5/P-7,
                      DoD 5220.22-M, ISO 27040, vb.)

Yöntem Seçim
Gerekçesi          : ____________________________________

──────────────────────────────────────────────────────
3. KANIT VE DOĞRULAMA
──────────────────────────────────────────────────────
Hash Kanıtları     : Eki-1 (ayrı dosya)
                     SHA-256 hash adedi: __________
Sistem Logu        : Eki-2 (ayrı dosya)
                     Log Sistemi: ____________________
                     Job ID: _________________________
                     Başlangıç: __:__:__  Bitiş: __:__:__
Görsel Kanıt       : [ ] Var (Eki-3) — foto/video
                     [ ] Yok
Tedarikçi Sertif.  : [ ] Yok
                     [ ] Var: ____________________ no
                     Tedarikçi: ____________________

──────────────────────────────────────────────────────
4. ÜÇÜNCÜ KİŞİ AKTARIMI
──────────────────────────────────────────────────────
Aktarılan Üçüncü
Kişiler            : [ ] Yok
                     [ ] Var: __________________________

Üçüncü Kişiye
Bildirim           : [ ] Yapıldı (Tarih: __/__/____)
                     [ ] Bekliyor
                     [ ] Uygulanabilir değil
Üçüncü Kişi
Onayı/Teyidi       : [ ] Alındı (Tarih: __/__/____)
                     [ ] Bekliyor

──────────────────────────────────────────────────────
5. SORUMLULAR VE İMZALAR
──────────────────────────────────────────────────────
Hazırlayan (İmhayı Uygulayan)
  Ad Soyad         : ____________________________
  Unvan / Birim    : ____________________________
  Tarih            : ____/____/______
  İmza             : ____________________________

Doğrulayan (Bilgi Güvenliği — bağımsız)
  Ad Soyad         : ____________________________
  Unvan / Birim    : ____________________________
  Tarih            : ____/____/______
  İmza             : ____________________________

KVKK Sorumlusu Onayı
  Ad Soyad         : ____________________________
  Unvan            : KVKK Sorumlusu
  Tarih            : ____/____/______
  İmza             : ____________________________

Hukuki Onay (Hukuk Müdürü)
  Ad Soyad         : ____________________________
  Unvan            : Hukuk Müdürü
  Tarih            : ____/____/______
  İmza             : ____________________________

──────────────────────────────────────────────────────
6. SAKLAMA VE ARŞİVLEME
──────────────────────────────────────────────────────
Tutanak Saklama
Süresi             : En az 3 yıl (Yön. m.7(3))
                     Kurum standardı: 5 yıl
Arşiv Yeri         : __________________________________
Arşiv Numarası     : __________________________________

══════════════════════════════════════════════════════
EKİ BELGELER
══════════════════════════════════════════════════════
[ ] Eki-1: Hash listesi (SHA-256)
[ ] Eki-2: Sistem logu çıktısı
[ ] Eki-3: Foto/video kanıtı
[ ] Eki-4: Tedarikçi imha sertifikası
[ ] Eki-5: Üçüncü kişi bildirim/teyit yazısı
[ ] Eki-6: İlgili kişi başvuru ve cevap (varsa)
[ ] Eki-7: Yöntem teknik talimatı/runbook çıktısı
══════════════════════════════════════════════════════
```

---

## 6. Örnek Tutanak 1 — Kağıt Belge Shredder ile Yok Etme

```
══════════════════════════════════════════════════════
KİŞİSEL VERİ İMHA TUTANAĞI
══════════════════════════════════════════════════════

Tutanak No         : 2026/PER-0007
Tutanak Türü       : [X] Periyodik
İşlem Tarihi/Saati : 12/05/2026 — 10:30
İşlem Yeri         : Genel Müdürlük — IK Arşivi (B-Blok B1)

──────────────────────────────────────────────────────
1. KAPSAMA İLİŞKİN BİLGİLER
──────────────────────────────────────────────────────
Veri Kategorisi    : İşe alım sürecinde reddedilen aday CV'leri
                     (Envanter Madde No: IK-04)
Veri Sahibi Grup   : Çalışan adayı
Hukuki Sebep —
İşleme Şartı       : KVKK m.5/2-(f) Meşru menfaat
                     Şartın Sona Erme Sebebi:
                     2 yıllık azami saklama süresi doldu
Kayıt Sayısı       : 1.142 dosya
Tarih Aralığı      : 01/01/2024 — 30/04/2024
Ortam              : [X] Kağıt belge

──────────────────────────────────────────────────────
2. UYGULANAN İMHA YÖNTEMİ
──────────────────────────────────────────────────────
Ana Yöntem         : [X] Yok Etme (Yön. m.9)
Alt Yöntem         : Cross-cut shredder (mikro kesim)
Uygulanan Standart : DIN 66399 P-5
Yöntem Seçim
Gerekçesi          : Kağıt ortamda kişisel veri içeren
                     başvuru dosyaları; geri döndürme
                     riski olmaksızın yok etme zorunlu.

──────────────────────────────────────────────────────
3. KANIT VE DOĞRULAMA
──────────────────────────────────────────────────────
Hash Kanıtları     : N/A (kağıt ortam)
Sistem Logu        : N/A
Görsel Kanıt       : [X] Var — Eki-3 (3 adet foto:
                     öncesi-sırasında-sonrası)
Tedarikçi Sertif.  : [X] Yok (kurum içi shredder)

──────────────────────────────────────────────────────
4. ÜÇÜNCÜ KİŞİ AKTARIMI
──────────────────────────────────────────────────────
Aktarılan Üçüncü
Kişiler            : [X] Yok

──────────────────────────────────────────────────────
5. SORUMLULAR VE İMZALAR
──────────────────────────────────────────────────────
Hazırlayan         : Ayşe DEMİR — IK Uzmanı
Doğrulayan         : Mehmet KAYA — Bilgi Güvenliği Uzmanı
KVKK Sorumlusu     : Selin YILDIZ — KVKK Sorumlusu
Hukuki Onay        : Av. Ahmet ÖZ — Hukuk Müdürü

──────────────────────────────────────────────────────
6. SAKLAMA VE ARŞİVLEME
──────────────────────────────────────────────────────
Saklama Süresi     : 5 yıl
Arşiv Yeri         : KVKK Arşivi — Dolap 03 / Klasör 14
Arşiv Numarası     : KVKK-ARS-2026-0007

══════════════════════════════════════════════════════
EKİ BELGELER
══════════════════════════════════════════════════════
[X] Eki-3: 3 adet foto (öncesi/sırasında/sonrası)
[X] Eki-7: IK-PROC-005 Aday Dosyası İmha Talimatı v2.1
══════════════════════════════════════════════════════
```

---

## 7. Örnek Tutanak 2 — HDD Degausser + Fiziksel Parçalama

```
══════════════════════════════════════════════════════
KİŞİSEL VERİ İMHA TUTANAĞI
══════════════════════════════════════════════════════

Tutanak No         : 2026/IMHA-0142
Tutanak Türü       : [X] Tetiklenmiş (Donanım hurdaya çıkma)
İşlem Tarihi/Saati : 18/05/2026 — 14:00
İşlem Yeri         : Veri Merkezi — Disk İmha Odası

──────────────────────────────────────────────────────
1. KAPSAMA İLİŞKİN BİLGİLER
──────────────────────────────────────────────────────
Veri Kategorisi    : Eski ERP sunucusu disk diziminden
                     çıkartılan HDD'ler (çalışan, müşteri,
                     finansal veriler dahil karma)
                     (Envanter Madde No: BT-12, BT-13)
Veri Sahibi Grup   : Çalışan + Müşteri + Tedarikçi
Hukuki Sebep —
İşleme Şartı       : Çoklu — KVKK m.5/2-(c) sözleşme
                     ifası + (e) hak tesisi + (f) meşru
                     menfaat
                     Şartın Sona Erme Sebebi: Sistem
                     migrasyonu sonrası eski donanımın
                     kullanım dışı çıkarılması
Kayıt Sayısı       : Disk başına ~~ TB; toplam veri
                     hacmi tahmini 2.3 TB
Ortam              : [X] Manyetik medya (HDD)

  Disk Listesi:
  Seri No                Üretici    Kapasite
  WD-WMC4M0H17832        WD         2 TB
  WD-WMC4M0H17855        WD         2 TB
  ST3000DM001-Z3T2HK1    Seagate    3 TB
  ST3000DM001-Z3T2HM2    Seagate    3 TB
  ... (toplam 8 disk)

──────────────────────────────────────────────────────
2. UYGULANAN İMHA YÖNTEMİ
──────────────────────────────────────────────────────
Ana Yöntem         : [X] Yok Etme (Yön. m.9)
Alt Yöntem         : 1) Degausser ile manyetik silme
                     2) Mekanik parçalama (drive shredder)
Uygulanan Standart : NIST 800-88 Rev.1 Purge → Destroy
Yöntem Seçim
Gerekçesi          : Donanım yeniden kullanılmayacak;
                     hassas veri içerir; çoklu yöntem ile
                     telafisi imkansız geri getirme.

──────────────────────────────────────────────────────
3. KANIT VE DOĞRULAMA
──────────────────────────────────────────────────────
Hash Kanıtları     : Disk öncesi disk imajından alınan
                     hash'ler — Eki-1 (kontrol amaçlı)
Sistem Logu        : Degausser cihaz logu — Eki-2
                     Cihaz: Garner HD-3WXL
                     Kalibrasyon: 2026-04-01 (geçerli)
Görsel Kanıt       : [X] Var — Eki-3:
                     - Disk öncesi (seri no görünür)
                     - Degausser işlem sırası
                     - Parçalama sonrası (parça hali)
Tedarikçi Sertif.  : [X] Yok (kurum içi cihaz)

──────────────────────────────────────────────────────
4. ÜÇÜNCÜ KİŞİ AKTARIMI
──────────────────────────────────────────────────────
Aktarılan Üçüncü
Kişiler            : [X] Var: ABC Lojistik A.Ş. (eski
                     teslimat kayıtları paylaşıldı)
Üçüncü Kişiye
Bildirim           : [X] Yapıldı (20/05/2026 / KEP yolu)
Üçüncü Kişi
Onayı/Teyidi       : [ ] Bekliyor (taahhüt 30 gün içinde)

──────────────────────────────────────────────────────
5. SORUMLULAR VE İMZALAR
──────────────────────────────────────────────────────
Hazırlayan         : Burak ÇELİK — Sistem Yöneticisi
Doğrulayan         : Mehmet KAYA — Bilgi Güvenliği Uzmanı
KVKK Sorumlusu     : Selin YILDIZ — KVKK Sorumlusu
Hukuki Onay        : Av. Ahmet ÖZ — Hukuk Müdürü

──────────────────────────────────────────────────────
6. SAKLAMA VE ARŞİVLEME
──────────────────────────────────────────────────────
Saklama Süresi     : 5 yıl
Arşiv Yeri         : KVKK Dijital Arşiv (e-imzalı PDF)
Arşiv Numarası     : KVKK-ARS-2026-0142

══════════════════════════════════════════════════════
EKİ BELGELER
══════════════════════════════════════════════════════
[X] Eki-1: Disk hash listesi (SHA-256)
[X] Eki-2: Degausser cihaz logu (CSV çıktı)
[X] Eki-3: Foto-video kanıtı (3 adet, zaman damgalı)
[X] Eki-5: Üçüncü kişi (ABC Lojistik) bildirim KEP'i
[X] Eki-7: BT-PROC-018 Disk İmha Runbook v3.0
══════════════════════════════════════════════════════
```

---

## 8. Örnek Tutanak 3 — Bulut Veritabanı Silme + Crypto-Shredding

```
══════════════════════════════════════════════════════
KİŞİSEL VERİ İMHA TUTANAĞI
══════════════════════════════════════════════════════

Tutanak No         : 2026/TLP-0023
Tutanak Türü       : [X] İlgili Kişi Talebi
İşlem Tarihi/Saati : 03/06/2026 — 16:45
İşlem Yeri         : AWS eu-central-1 — Production
                     veritabanı + S3 yedek

──────────────────────────────────────────────────────
1. KAPSAMA İLİŞKİN BİLGİLER
──────────────────────────────────────────────────────
Veri Kategorisi    : E-ticaret üye hesap kayıtları
                     (Envanter Madde No: ECOM-01)
Veri Sahibi Grup   : Tek bir müşteri (Talep No:
                     KVKK-BSV-2026-0214)
Hukuki Sebep —
İşleme Şartı       : Açık rıza geri çekildi (KVKK m.5/1);
                     Sözleşmesel ilişki sona ermiş;
                     Vergi/ticari saklama süresi geçilmiş.
                     Şartın Sona Erme Sebebi: Tüm işleme
                     şartları ortadan kalktı (Yön. m.12/1-a)
Kayıt Sayısı       : 1 müşteri profili + 47 sipariş
                     kaydı + 312 oturum/erişim logu
Ortam              : [X] Bulut nesne depolama (S3)
                     [X] Aktif veritabanı (RDS PostgreSQL)
                     [X] Log/SIEM (CloudWatch + ES)
                     [X] Yedek (RDS otomatik snapshot)

──────────────────────────────────────────────────────
2. UYGULANAN İMHA YÖNTEMİ
──────────────────────────────────────────────────────
Ana Yöntem         : [X] Silme (Yön. m.8) — aktif sistem
                     [X] Yok Etme (Yön. m.9) — yedek
Alt Yöntem         : 1) DB: hard-delete (DELETE)
                        + audit kaydı
                     2) S3: object delete + version delete
                        + lifecycle expiry
                     3) Log: PII alanları null + indeks
                        bazlı retention
                     4) Yedek: BYOK DEK (Data Encryption
                        Key) imhası — crypto-shredding
Uygulanan Standart : Bulut sağlayıcı DPA (AWS) imha
                     taahhüdü; NIST 800-88 Purge (kripto)
Yöntem Seçim
Gerekçesi          : Bulutta donanım imhası mümkün değil;
                     anahtar imhası ile pratik yok etme
                     gerçekleştirildi. İlgili kişiye
                     yöntem ve gerekçe ile bilgi verildi.

──────────────────────────────────────────────────────
3. KANIT VE DOĞRULAMA
──────────────────────────────────────────────────────
Hash Kanıtları     : Müşteri ID hash'i (SHA-256) —
                     Eki-1 (verinin kendisi tutulmadı)
Sistem Logu        : - RDS general log (Eki-2)
                     - CloudTrail KMS API logu (Eki-2)
                     - S3 access log (Eki-2)
                     Job ID: KVKK-PURGE-2026-0023
                     Başlangıç: 16:30:12 — Bitiş: 16:43:28
Görsel Kanıt       : [X] Var — Eki-3 (KMS konsol ekran
                     görüntüsü "Pending deletion" → "Deleted")
Tedarikçi Sertif.  : N/A (AWS DPA kapsamında)

──────────────────────────────────────────────────────
4. ÜÇÜNCÜ KİŞİ AKTARIMI
──────────────────────────────────────────────────────
Aktarılan Üçüncü
Kişiler            : [X] Var:
                     - Lojistik tedarikçisi (sipariş adresi)
                     - Ödeme servisi (ödeme tokenları)
                     - Pazarlama otomasyon SaaS sağlayıcısı
Üçüncü Kişiye
Bildirim           : [X] Yapıldı (03/06/2026 / KEP yolu)
Üçüncü Kişi
Onayı/Teyidi       : [X] Lojistik — alındı 05/06/2026
                     [X] Ödeme — alındı 04/06/2026
                     [ ] Pazarlama — bekliyor (15 gün)

──────────────────────────────────────────────────────
5. SORUMLULAR VE İMZALAR
──────────────────────────────────────────────────────
Hazırlayan         : Burak ÇELİK — Sistem Yöneticisi
Doğrulayan         : Mehmet KAYA — Bilgi Güvenliği Uzmanı
KVKK Sorumlusu     : Selin YILDIZ — KVKK Sorumlusu
Hukuki Onay        : Av. Ahmet ÖZ — Hukuk Müdürü

──────────────────────────────────────────────────────
6. SAKLAMA VE ARŞİVLEME
──────────────────────────────────────────────────────
Saklama Süresi     : 5 yıl
Arşiv Yeri         : KVKK Dijital Arşiv (e-imzalı PDF)
Arşiv Numarası     : KVKK-ARS-2026-0023

══════════════════════════════════════════════════════
EKİ BELGELER
══════════════════════════════════════════════════════
[X] Eki-1: Müşteri ID hash listesi (SHA-256)
[X] Eki-2: AWS sistem logları (RDS, CloudTrail, S3)
[X] Eki-3: KMS Pending Deletion → Deleted ekran görüntüsü
[X] Eki-5: 3 üçüncü kişiye gönderilen KEP + alınan teyit
[X] Eki-6: İlgili kişi başvuru (No: KVKK-BSV-2026-0214)
            ve veri sorumlusunun cevap yazısı
[X] Eki-7: BT-PROC-024 Bulut PII Purge Runbook v2.0
══════════════════════════════════════════════════════
```

## 9. Tutanak Doğrulama Kontrol Listesi

İmha tutanağı imzaya çıkmadan önce KVKK Sorumlusu aşağıdaki kontrolleri yapar:

- [ ] Tutanak no şirket içi sıra ile tutarlı
- [ ] İşleme şartı ve şartın sona erme sebebi açıkça yazılmış
- [ ] Veri kategorisi envanter ile birebir uyumlu
- [ ] Kayıt sayısı ve hash adedi tutarlı
- [ ] Yöntem, ortam türüne uygun seçilmiş
- [ ] Uygulanan standart referans verilmiş
- [ ] Kanıt türü (hash/log/foto/sertifika) belirtilmiş
- [ ] Üçüncü kişi aktarımı kontrol edilmiş; bildirim yapılmış
- [ ] 4 imza tamam (Hazırlayan, Doğrulayan, KVKK Sorumlusu, Hukuk Müdürü)
- [ ] Eki belgeler eksiksiz
- [ ] Saklama süresi ve arşiv numarası verilmiş
- [ ] Elektronik imza atılmış
