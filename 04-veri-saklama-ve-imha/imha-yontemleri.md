---
Doküman: İmha Yöntemleri ve Ortam Bazlı Uygulama Matrisi
Bölüm: 04-veri-saklama-ve-imha
Sahip: Bilgi Güvenliği Yöneticisi
Onaylayan: KVKK Sorumlusu + Hukuk Müdürü
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (yeni teknoloji, yeni veri kategorisi, ihlal sonrası)
İlgili Mevzuat: Yön. m.7, m.8, m.9, m.10; Veri Güvenliği Rehberi (Teknik Tedbirler); NIST SP 800-88 Rev.1 (referans); ISO/IEC 27040 (referans)
---

# İmha Yöntemleri ve Ortam Bazlı Uygulama Matrisi

## 1. Giriş

Yönetmeliğin imha tanımı üç ayrı yöntemi kapsar (Yön. m.4(1)/c). Her yöntemin **hukuki sonucu**, **uygulama eşiği** ve **kanıt yükümlülüğü** farklıdır. Yöntem seçimi keyfi değildir; ortamın yapısı, verinin niteliği, veri sorumlusu ile veri işleyenin teknik kapasitesi ve geri döndürülebilirlik riski birlikte değerlendirilir (Yön. m.7(5)).

```
                        İMHA
                          |
        +-----------------+-----------------+
        |                 |                 |
      SİLME           YOK ETME       ANONİM HALE GETİRME
      (Yön. m.8)      (Yön. m.9)        (Yön. m.10)
        |                 |                 |
İlgili kullanıcılar   Hiç kimse        Verinin kişisel
için erişilemez       için erişilemez   nitelikten
ve tekrar             ve geri           kalıcı olarak
kullanılamaz          getirilemez       çıkarılması
```

## 2. Yöntem 1 — Silme (Yön. m.8)

### 2.1. Tanım

Kişisel verilerin **ilgili kullanıcılar** için hiçbir şekilde erişilemez ve tekrar kullanılamaz hale getirilmesi işlemidir. Burada ölçü "ilgili kullanıcı"dır; teknik olarak depolanmadan veya yedeklenmesinden sorumlu kişi (sistem yöneticisi, yedek operatörü) bu tanımın dışındadır.

### 2.2. Uygulama Şekilleri

- **Veritabanında satır silme (DELETE):** Aktif veride satır silinir. Yedek ve loglarda kalan kopyalar için ayrı plan gerekir.
- **Soft-delete + hard-delete birleşimi:** Önce satır "deleted" işaretlenir (entegre uygulamalarda referans bütünlüğü için), sonra retention job ile fiziken silinir. Soft-delete tek başına Yön. m.8 anlamında silme **DEĞİLDİR**.
- **Dosya silme + boş alan üzerine yazma:** Sürdürülemez; iz ve geri kazanım riski vardır. Kurumsal ortamda **secure delete** araçları kullanılmalıdır.
- **Bulutta nesne silme + sürüm temizliği:** Versionlu objelerde sürüm geçmişi de silinmelidir.
- **Yetki kaldırma (erişim odaklı silme):** Sadece veri sorumlusu özel sorumlulukta tutulan veriler için kabul edilir; veri sahibinin erişimi kalkmış olur.
- **Kayıt karartma/maskeleme:** Sadece görsel/yazılı belgelerde tüm satırın değil belirli alanların kaldırılması gerektiğinde uygulanır. Bu yöntem kayıt türüne göre **kısmi silme** olarak değerlendirilir.

### 2.3. Tipik Hatalar

- Aktif tabloyu sildi, yedeği unuttu — yedekte hâlâ erişilebilir.
- "Recycle bin" / "trash" içine taşıdı — kullanıcı geri çekebilir, silme tamamlanmamış.
- Pasif veri olarak başka tabloya taşındı — tekrar erişilebilir, silme değil.
- Sadece UI'da gizledi — backend'de tutuluyor, ilgili kullanıcı yine erişebilir.
- Soft-delete kalıcı kabul edildi — hard-delete planı yok.

## 3. Yöntem 2 — Yok Etme (Yön. m.9)

### 3.1. Tanım

Kişisel verilerin **hiç kimse** tarafından hiçbir şekilde erişilemez, geri getirilemez ve tekrar kullanılamaz hale getirilmesi işlemidir. Eşik daha yüksektir: yedekleri, log içindeki parçaları, fiziksel medyayı kapsar.

### 3.2. Uygulama Şekilleri

- **Fiziksel ortam imhası:** HDD/SSD/USB/CD/manyetik bant fiziksel olarak parçalanır, eritilir, yakılır.
- **Manyetik ortam degauss:** Manyetik diskler için güçlü manyetik alan ile veri silme. SSD için **uygun değildir** (NAND yapısına etki etmez).
- **Kriptografik silme (crypto-shredding):** Veri AES-256 ile şifreli yazılmışsa, sadece şifreleme anahtarının imhası ile veri pratik olarak yok edilir. Bulut, dağıtık ortam ve büyük yedekler için en pratik yöntemdir.
- **Tüm yedeklerin imhası:** Yedek rotasyon takvimine göre bekletilen yedekler, yok etme talebi sonrası rotasyon tamamlandığında imha edilir; rotasyon sonu beklenmediğinde yedek anahtarı imha edilir.
- **Tape (manyetik bant) imhası:** Degauss + fiziksel kesme.
- **Kağıt belge yok etme:** Onaylı imha makinesi (Cross-cut DIN P-4 veya P-5 minimum, gizlilik dereceli belgeler için P-7); özel evrak için yakma.

### 3.3. NIST 800-88 Sınıflandırması (Referans)

| Sınıf | Tanım | Kullanım |
|-------|-------|----------|
| Clear | Standart yazılım ile veri üzerine yazma | Düşük gizlilik, ortam yeniden kullanılacak |
| Purge | Donanım veya kriptografik teknik ile geri getirilemez kılma | Orta-yüksek gizlilik, ortam yeniden kullanılabilir |
| Destroy | Fiziksel parçalama, yakma, eritme | Yüksek gizlilik veya ortam kullanılmayacak |

Türk hukukunda **Yok Etme** kavramı NIST'in **Purge** ve **Destroy** seviyelerine karşılık gelir. Sadece "Clear" yok etme için yetersizdir.

## 4. Yöntem 3 — Anonim Hale Getirme (Yön. m.10)

### 4.1. Tanım

Kişisel verilerin başka verilerle eşleştirilse dahi hiçbir surette kimliği belirli veya belirlenebilir bir gerçek kişiyle ilişkilendirilemeyecek hale getirilmesidir. Veri kişisel veri olmaktan çıkar; KVKK kapsamından çıkar.

**Kritik:** Anonim hale getirme, geri döndürme ve eşleştirme açısından **gerçek anonimlik** üretmelidir. Sadece doğrudan tanıtıcının (ad, T.C. kimlik no) kaldırılması yeterli değildir; quasi-identifier (yaş, posta kodu, meslek, cinsiyet) kombinasyonu ile yeniden tanımlanma riski vardır.

### 4.2. Pseudonymization Anonimleştirme DEĞİLDİR

Pseudonymization (takma adlandırma); doğrudan tanıtıcılar yerine başka anahtar konulması, ancak bağlantı verisinin **veri sorumlusunda saklanmaya devam etmesi**dir. Bu kişisel veridir, anonim değildir. Yön. m.10 anlamında imha amacıyla kullanılamaz; sadece **işleme tedbiri** olarak değer taşır.

### 4.3. Anonimleştirme Teknikleri

| Teknik | Açıklama | Güç | Veri Faydası |
|--------|----------|-----|--------------|
| **Generalization** | Spesifik değerin daha genel kategoriye yükseltilmesi (ör. "27 yaş" → "20-29 yaş aralığı") | Orta | Yüksek |
| **Suppression** | Belirli alanın tamamen silinmesi | Yüksek | Orta |
| **Noise addition** | Sayısal değerlere kontrollü gürültü eklenmesi | Orta-Yüksek | Yüksek (istatistik için) |
| **Permutation** | Kayıtlar arası alan değerlerinin yer değiştirilmesi | Orta | Orta |
| **Tokenization (geri dönüşümlü değil)** | Doğrudan tanıtıcının takma değer ile değiştirilmesi; **eşleme tablosu imha edilirse** anonimleştirme | Yüksek | Yüksek |
| **k-anonimite** | Her satırın en az k-1 başka satıra benzemesi (quasi-identifier kombinasyonu) | Orta | Yüksek |
| **l-çeşitlilik** | k-anonim grubunda hassas özniteliğin en az l farklı değer alması | Yüksek | Orta |
| **t-yakınlık** | k-anonim grubunda hassas özniteliğin dağılımının orijinal dağılıma "t" mesafede olması | Yüksek | Orta-Düşük |
| **Diferansiyel gizlilik** | Sorgu çıktılarına matematik tabanlı gürültü; bireyin varlığı/yokluğu ayırt edilemez | Çok Yüksek | Düşük-Orta |

### 4.4. Yeniden Tanımlanma Riski Değerlendirmesi

Anonimleştirme her zaman risk değerlendirmesi ile yapılmalıdır:

```
+----------------------------------------+
| 1. Veri seti içeriğinin haritalanması  |
| - Doğrudan tanıtıcılar                 |
| - Quasi-identifier'lar                 |
| - Hassas öznitelikler                  |
+----------------------------------------+
                 |
                 v
+----------------------------------------+
| 2. Tehdit modeli                       |
| - Kim erişebilir? (iç/dış)             |
| - Hangi yan veri ile eşleştirebilir?   |
| - Motivasyon ve maliyet                |
+----------------------------------------+
                 |
                 v
+----------------------------------------+
| 3. Üç riskin değerlendirilmesi         |
| - Singling out (bireyi ayırma)         |
| - Linkability (eşleştirme)             |
| - Inference (çıkarım)                  |
+----------------------------------------+
                 |
                 v
+----------------------------------------+
| 4. Teknik seçimi ve uygulanması        |
+----------------------------------------+
                 |
                 v
+----------------------------------------+
| 5. Sonuç doğrulama                     |
| - Re-identification testi              |
| - Saldırı senaryosu simülasyonu        |
+----------------------------------------+
                 |
                 v
+----------------------------------------+
| 6. Risk kalıntısı kabul edilebilir mi? |
+----------------------------------------+
            |               |
        evet|            hayır|
            v               v
        Yayımla        Tekniği güçlendir
```

Risk kalıntısı kabul edilebilir değilse veri **anonim sayılmaz** ve KVKK kapsamında işlem görmeye devam eder.

## 5. Ortam Bazlı Uygulama Matrisi

### 5.1. Kağıt Ortam

| Veri Türü | Yöntem | Standart | Kanıt |
|-----------|--------|----------|-------|
| Genel ofis evrakı | Cross-cut shredder | DIN 66399 P-4 | İmha tutanağı + günlük log |
| Özlük dosyası, sözleşme | Cross-cut shredder | DIN 66399 P-5 | İmha tutanağı + 2 kişi imza |
| Sağlık raporu, finansal | Mikro-shredder + yakma | DIN 66399 P-7 | İmha tutanağı + 3 kişi imza + foto kanıt |
| Yüksek hassasiyet (TC No içeren toplu liste) | Yakma | — | Tutanak + yakma alanı görüntüsü |
| Tedarikçi imha hizmeti | Şirket dışı sertifikalı imha (NAID AAA önerilir) | — | Tedarikçi imha sertifikası + tutanak |

### 5.2. Manyetik Disk (HDD)

| Senaryo | Yöntem | Standart |
|---------|--------|----------|
| Yeniden kullanım | DoD 5220.22-M (3 geçiş) veya NIST 800-88 Clear | İmha logu, hash kanıtı |
| Yeniden kullanım — yüksek hassasiyet | NIST 800-88 Purge — degausser | Degausser kalibrasyon kaydı + tutanak |
| Kullanım dışı | Fiziksel parçalama (shredder, ezici makine) | Foto kanıt + tutanak |
| Kullanım dışı — şifreli yazılmış disk | Anahtar imhası + sökme | Anahtar imha kaydı + tutanak |

### 5.3. SSD (NAND/Flash)

> **Kritik:** SSD'de degausser etkisizdir; wear-leveling nedeniyle yazılım üzerine yazma da garanti vermez. Tek güvenli yol fiziksel imha veya cihazın kendi **secure erase / sanitize** komutudur (TCG Opal, NVMe sanitize).

| Senaryo | Yöntem | Standart |
|---------|--------|----------|
| Yeniden kullanım | Cihazın sanitize komutu (NVMe Format with crypto-erase, ATA Sanitize) | NIST 800-88 Purge |
| Kullanım dışı | Fiziksel imha (chip-level shredder) | Foto kanıt + tutanak |

### 5.4. USB Bellek, SD Kart, Optik Medya

| Ortam | Yöntem |
|-------|--------|
| USB / SD kart (NAND) | Sanitize + fiziksel imha |
| CD / DVD / Blu-ray | Optik shredder (gizlilik dereceli için P-7 eşdeğeri) |
| Manyetik bant (LTO) | Degausser + fiziksel kesme |

### 5.5. Bulut Ortamı

| Senaryo | Yöntem |
|---------|--------|
| IaaS / VM disk | Cloud sağlayıcı disk silme + sağlayıcının "secure deletion" politikasının kanıtı (DPA + sertifika) |
| Nesne depolama (S3, blob, GCS) | Object delete + version history delete + lifecycle rule + (Object Lock kullanılıyorsa) retention sona erdirme |
| Yönetilen veritabanı | Kayıt silme + transaction log temizliği + yedek imha takvimi |
| Yedek (managed backup) | Sağlayıcı yedek imha taahhütü + retention policy + crypto-shredding (anahtar BYOK ise) |
| SaaS uygulama | Sağlayıcıdan imha taahhüdü (DPA içinde "termination data deletion" maddesi) + sağlayıcının imha sertifikası |

> **Crypto-shredding** bulut için en pratik yöntemdir: anahtarlar HSM/KMS'te tutulur; veri silinmek istendiğinde anahtar imha edilir; veri matematik olarak erişilemez hale gelir. Anahtar yönetiminin bağımsız tutulması gerekir.

### 5.6. Veritabanı

| Senaryo | Yöntem |
|---------|--------|
| Aktif satır | DELETE / UPDATE (kişisel alan NULL/anonim) |
| Audit log içindeki kişisel veri | Log row anonimleştirme + retention job |
| Transaction log | Veritabanı bakım planı, log truncation, eski WAL/redo log temizliği |
| Yedek dosyaları | Yedek rotasyonu içinde imha; gerekirse yedek anahtarı imhası |
| Replikasyon | Read replica üzerinde de retention job çalıştırılır; replikasyon gecikmesi süre hesabına eklenir |
| Materialize view, index, full-text search | Silme operasyonları sonrası tüm türetilmiş yapıların yeniden inşası |

#### 5.6.1. SQL Örneği (PostgreSQL — Hard Delete + Audit)

```sql
BEGIN;

INSERT INTO kvkk_imha_audit (
    islem_id, tablo_adi, satir_id, islem_tarihi, gerekce, sorumlu, hash
) VALUES (
    gen_random_uuid(), 'musteri', :musteri_id, now(),
    'Periyodik imha — saklama süresi doldu', :sorumlu_id,
    digest(:musteri_id::text || now()::text, 'sha256')
);

DELETE FROM musteri WHERE id = :musteri_id;

COMMIT;
```

Audit kaydı, "ne, ne zaman, kim, neden" sorularını cevaplar. Hash, kayıtların sonradan değiştirilemediğini ispatlar.

### 5.7. Log Dosyaları

Loglar genellikle kişisel veri (IP, kullanıcı adı, T.C. No, telefon, e-posta) barındırır. Log retention politikasına ek olarak:

- **Yapılı loglar (JSON, structured):** Kişisel alanların maskelenerek / silinerek saklanması.
- **Yapısız loglar (text):** Saklama süresi sonunda log dosyası tümüyle silinir.
- **SIEM:** Index retention politikasına bağlanır; eski indekslerin silinmesi otomatik.
- **Yedeklerdeki loglar:** Yedek rotasyon ile birlikte imha edilir.

## 6. Yöntem Seçim Karar Ağacı

```
+---------------------------------+
| Veri imha yükümlülüğü oluştu    |
+---------------------------------+
              |
              v
+---------------------------------+
| Veri analitik/raporlama için    |
| anonim halde değerli mi?        |
+---------------------------------+
        |                |
    evet|            hayır|
        v                v
+--------------+   +-----------------+
| Yön. m.10    |   | Veri ortamı/    |
| Anonim hale  |   | medya yeniden   |
| getirme      |   | kullanılacak mı?|
+--------------+   +-----------------+
                        |          |
                    evet|       hayır|
                        v          v
              +--------------+  +--------------+
              | Yön. m.8     |  | Yön. m.9     |
              | Silme        |  | Yok etme     |
              | (ilgili      |  | (fiziksel/   |
              |  kullanıcı   |  |  kripto      |
              |  erişimi     |  |  imhası)     |
              |  kalkar)     |  +--------------+
              +--------------+
```

## 7. Kanıt Yönetimi

Her imha işlemi için:

- **Tutanak:** [imha-kayit-tutanagi-sablonu.md](imha-kayit-tutanagi-sablonu.md) şablonuna uygun.
- **Hash kanıtı:** Silinen kaydın özet kimliği SHA-256 ile alınır; verinin kendisi tutulmaz, sadece hash.
- **Foto/video:** Fiziksel imha için.
- **Sistem logu:** Operasyonun başlangıç-bitiş zaman damgası, çalışan kullanıcı, işlemin job ID'si.
- **Tedarikçi sertifikası:** Şirket dışı imha tedarikçisi varsa.
- **Chain of custody:** Ortamın imha noktasına ulaşana kadar geçtiği elleri gösteren zincir.

## 8. Risk Senaryoları ve Önlemler

| Risk | Önlem |
|------|-------|
| Yedek tape'lerde imha edilen veri yıllarca kaldı | Yedek rotasyon süresi politikaya yansıtılır; yedek anahtar imhası ile pratikleştirilir |
| Bulut sağlayıcı "soft-delete" yaptı, veri rezerv edildi | DPA'da "hard-delete" taahhüdü; sağlayıcı imha sertifikası |
| Test ortamında üretim verisi kaldı | DLP + ortam segmentasyonu + maskeleme zorunluluğu |
| SSD üzerinde DoD wipe yapıldı, veri kaldı | SSD için sadece sanitize/destroy; DoD wipe yasaklanır |
| Anonimleştirme zayıf, re-identification mümkün | Yıllık re-identification testi; quasi-identifier listesi |
| Pseudonymization, anonim sayıldı | Pseudonymization KVKK kapsamından çıkarmaz; tablo bunu net belirtir |
| İmha tutanağı yok, kanıt eksik | Otomatik tutanak üretimi (job çıktısından template'lenir) |
| Birden fazla kopyada veri var (replikasyon, cache) | İmha öncesi tam veri haritası; tüm kopyaların eşzamanlı imhası |
