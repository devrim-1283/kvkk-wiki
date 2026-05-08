---
Doküman: Tedarikçi (Üçüncü Taraf) Yönetimi ve Veri İşleyen İlişkileri Politikası
Bölüm: 06-idari-tedbirler
Sahip: Satınalma Direktörü + KVKK Sorumlusu + Hukuk Müşaviri
Onaylayan: KVKK Komitesi + Üst Yönetim
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (önemli ihlal, yeni mevzuat, tedarikçi çıkış/giriş)
İlgili Mevzuat: 6698 sayılı KVKK m.12 (veri sorumlusunun veri işleyenle birlikte müşterek sorumluluğu), m.8 (yurt içi aktarım), m.9 (yurt dışı aktarım), m.4 (genel ilkeler); Veri Sorumlusu - Veri İşleyen ayrımı (KVKK Yayını No:106 - Haziran 2025); Türk Borçlar Kanunu (sorumluluk hükümleri); 6502 sayılı Tüketicinin Korunması Hakkında Kanun (uygulanabildiğinde)
İlgili Standart: ISO/IEC 27001:2022 A.5.19 (Information Security in Supplier Relationships), A.5.20 (Addressing Information Security within Supplier Agreements), A.5.21 (Managing Information Security in the ICT Supply Chain), A.5.22 (Monitoring, Review and Change Management of Supplier Services), A.5.23 (Information Security for Use of Cloud Services); ISO/IEC 27036 serisi; ISO/IEC 27701:2019 (PII Processor); NIST CSF 2.0 GV.SC, ID.SC; SOC 2 Type II; CSA Cloud Controls Matrix (CCM); GDPR Art. 28 (Processor)
---

# Tedarikçi (Üçüncü Taraf) Yönetimi

## 1. Amaç

Kişisel veri ve diğer kritik bilgileri **veri sorumlusu sıfatımızla** korumak için, bu veriye erişen veya bizim adımıza işleyen üçüncü tarafların KVKK ve bilgi güvenliği yükümlülüklerini sözleşme + denetim + izleme + çıkış zinciriyle tutarlı şekilde yöneten çerçeveyi tanımlar.

KVKK Yayını No:106 (Haziran 2025) ve Kişisel Veri Güvenliği Rehberi'nde "Veri Sorumlusu - Veri İşleyen" arasındaki ilişki **sözleşmeye** bağlanır. Tedarikçi sözleşmesi yoksa veya asgari unsurları taşımıyorsa, ihlal halinde veri sorumlusu **birinci derece** sorumludur.

## 2. Temel İlkeler

1. **Sınıflandırmadan Onaylamaya:** Hiçbir tedarikçi, KVKK / bilgi güvenliği değerlendirmesi tamamlanmadan kişisel veriye erişemez.
2. **Veri Sorumlusu - Veri İşleyen Ayrımı:** Her tedarikçi için **rolü** açık tanımlanır (veri sorumlusu / veri işleyen / müşterek veri sorumlusu).
3. **Sözleşmede Asgari Unsurlar:** KVKK Yönetmeliği'nde aranan unsurlar + ek koruma maddeleri.
4. **Talimat Sınırlaması:** Veri işleyen, yalnızca veri sorumlusunun **yazılı talimatı** çerçevesinde işler.
5. **Şeffaf Alt-İşleyen:** Alt yüklenicilerin önceden onaylanması ve şeffaflığı.
6. **Denetim Hakkı:** Bizim veya üçüncü taraf denetçinin tedarikçiyi denetleme hakkı.
7. **Çıkış Yönetimi:** Sözleşme bitiminde verinin iade veya imhası, dönüş kanıtı.
8. **Sürekli İzleme:** İlişki imzayla bitmez; yıllık ve risk-tetikli izleme.

## 3. Tedarikçi Tip / Sınıflandırma

### 3.1. Veri İşleme Tipi

| Tip | Tanım | Örnek |
|-----|-------|-------|
| **Veri Sorumlusu (Bağımsız)** | Tedarikçi kendi amacı için işliyor; biz veri sorumlusu, o da veri sorumlusu | Banka (ödeme), kargo şirketi, kamu kurumu (resmi raporlama) |
| **Müşterek Veri Sorumlusu** | İşleme amacını birlikte belirliyoruz | Ortak yürütülen pazar araştırması (KVKK Yayını No:106 örneği), ortak müşteri programı |
| **Veri İşleyen** | Bizim adımıza, talimatımızla işliyor | SaaS sağlayıcı (CRM, ERP, IK), bulut depolama, çağrı merkezi outsource, BT destek |

### 3.2. Risk Sınıflandırması (Kritiklik)

| Sınıf | Kriter | Örnek | Onay |
|-------|--------|-------|------|
| **A — Kritik** | Özel nitelikli veri / 100K+ kayıt / kritik altyapı | Sağlık verisi işleyen, bankacılık çekirdeği | KVKK Komitesi + Üst Yön. |
| **B — Yüksek** | Genel kişisel veri 10K+ / iş kritikliği yüksek | CRM, IK SaaS, ödeme | KVKK Komitesi |
| **C — Orta** | Sınırlı kişisel veri / standart iş | Pazarlama otomasyon, helpdesk SaaS | KVKK Sorumlusu |
| **D — Düşük** | Kişisel veri yok veya minimum | Kahve makinesi, kırtasiye | Satınalma standart |

## 4. Yaşam Döngüsü

```
1. Tedarikçi İhtiyacı Tanımlama (İş Birimi)
2. Risk ve Sınıflandırma (Satınalma + KVKK Sorumlusu)
3. Due Diligence (Pre-contract Assessment)
4. Sözleşme Müzakere ve İmza
5. Onboarding ve Erişim Aktivasyonu
6. Operasyonel Yönetim ve Sürekli İzleme
7. Yıllık (veya çeyreklik) Review
8. Olay Yönetimi ve İhlal Bildirimi
9. Sözleşme Yenileme veya Çıkış
10. Veri İade / İmha + Erişim Kapatma
```

## 5. Due Diligence (Sözleşme Öncesi Değerlendirme)

### 5.1. KVKK Uyum Anketi (Tedarikçi Doldurur)

Asgari sorular:

1. KVKK kapsamında veri sorumlusu mu, veri işleyen mi olacak?
2. VERBİS kayıt yükümlülüğü var mı; varsa kayıt no?
3. KVKK Sorumlusu / DPO atadı mı, irtibat bilgisi?
4. İşleme amacı dışında kullanım yasakları nasıl uygulanır?
5. Saklama süresi politikaları?
6. Kişisel veriyi nerede saklayacak (ülke, şehir, veri merkezi)?
7. Yurt dışı aktarım var mı? Hangi ülkeye, hangi mekanizma ile?
8. Alt yüklenici listesi + sınıflandırması?
9. Personel eğitim ve gizlilik taahhütname süreci?
10. ISO 27001, ISO 27701, SOC 2 Type II sertifikası var mı? Kapsamı?
11. Son 1-2 yıl içinde veri ihlali oldu mu?
12. İhlal halinde bizim bildirim SLA'mız nedir?
13. Sızma testi sıklığı ve son sonuç özeti?
14. Bug bounty programı var mı?
15. Yıllık iç + dış denetim raporları?
16. Sigorta (cyber liability, professional indemnity)?
17. Sözleşme bitiminde veri iade/imha süreci ve kanıtı?
18. Çıkış stratejisi (data portability, vendor lock-in)?

### 5.2. Belge ve Sertifika Talebi

| Belge | Sınıf A | Sınıf B | Sınıf C |
|-------|---------|---------|---------|
| ISO 27001 sertifikası | Zorunlu | Zorunlu | Tavsiye |
| ISO 27701 sertifikası | Zorunlu | Tavsiye | Opsiyonel |
| SOC 2 Type II raporu | Zorunlu (yıllık) | Tavsiye | Opsiyonel |
| Sızma testi özet rapor | Zorunlu (yıllık) | Zorunlu (2 yılda 1) | Tavsiye |
| Cyber sigorta poliçesi | Zorunlu | Zorunlu | Opsiyonel |
| KVKK uyum anket cevabı | Zorunlu | Zorunlu | Zorunlu |
| Mali tablo / kredibilite | Zorunlu | Zorunlu | Tavsiye |
| BCP/DR planı | Zorunlu | Zorunlu | Opsiyonel |
| Alt-işleyen listesi | Zorunlu | Zorunlu | Tavsiye |
| Veri akış diyagramı | Zorunlu | Zorunlu | – |

### 5.3. Saha / Uzaktan Değerlendirme

- Sınıf A: yıllık on-site veya video saha denetimi.
- Sınıf B: yılda en az 1 video toplantı + dokümantasyon review.
- Sınıf C: anket yeterli olabilir.

### 5.4. Skor ve Onay

- 0-100 skor (her madde ağırlık + cevap puanı).
- Eşik: A için ≥85, B için ≥75, C için ≥60.
- Eşik altı tedarikçi: ya iyileştirme planıyla şartlı onay (90 gün) ya da ret.

## 6. Veri İşleyen Sözleşmesi — Asgari Unsurlar

KVKK m.12 ve KVKK Veri Güvenliği Rehberi gerekleri + uluslararası iyi uygulama.

### 6.1. Zorunlu Maddeler

```
1. TARAFLAR ve KONU
   1.1. Veri Sorumlusu (biz) ve Veri İşleyen (tedarikçi) tanımı.
   1.2. Sözleşme'nin amacı: <hizmet kapsamı>.
   1.3. Veri İşleyen, kişisel verileri yalnızca bu Sözleşme kapsamı ve
        Veri Sorumlusu'nun yazılı talimatları dahilinde işleyebilir.

2. İŞLEME KONUSU VERİLER (Ek-1 Veri Akışı)
   2.1. İşlenen veri kategorileri.
   2.2. Veri konuları (ilgili kişi grupları).
   2.3. İşleme amaçları.
   2.4. İşleme süreleri.
   2.5. İşleme yöntemleri.
   2.6. Aktarım (eğer varsa) hedefleri.

3. TALİMAT SINIRI
   3.1. Veri İşleyen, talimat dışı işleme yapamaz.
   3.2. Talimatın hukuka aykırı olduğunu düşünüyorsa, Veri Sorumlusu'na
        derhal yazılı bildirim yapar.
   3.3. Veri İşleyen, kişisel verileri kendi amaçları için kullanamaz,
        kopyalayamaz, üçüncü taraflarla paylaşamaz.

4. GİZLİLİK
   4.1. Veri İşleyen, kişisel verilere erişebilen tüm personelinin
        gizlilik taahhüdü imzaladığını ve düzenli eğitim aldığını
        garanti eder.
   4.2. Eğitim ve taahhüt kayıtları talep halinde sunulur.

5. GÜVENLİK TEDBİRLERİ
   5.1. Veri İşleyen, KVKK m.12 ve Veri Güvenliği Rehberi kapsamında
        belirlenen teknik ve idari tedbirleri sağlar.
   5.2. Asgari teknik tedbirler EK-2'de listelenmiştir.
   5.3. Kontroller ISO 27001 / ISO 27701 / SOC 2 standartlarıyla en az
        eşdeğer olmalıdır.

6. ALT-İŞLEYEN (SUB-PROCESSOR)
   6.1. Veri İşleyen, alt yüklenici kullanımını Veri Sorumlusu'nun ön
        yazılı onayına tabi tutar.
   6.2. Mevcut alt-işleyen listesi EK-3'te yer alır.
   6.3. Alt-işleyen değişikliği, en az 30 gün önceden Veri Sorumlusu'na
        bildirilir; itiraz hakkı saklıdır.
   6.4. Veri İşleyen, alt-işleyenle bu Sözleşme'yle aynı asgari koruma
        sağlayan yazılı sözleşme yapmakla yükümlüdür.
   6.5. Veri İşleyen, alt-işleyenin eylemlerinden kendi eylemleri gibi
        sorumludur.

7. AKTARIM (YURT İÇİ / YURT DIŞI)
   7.1. Yurt içi aktarım Veri Sorumlusu'nun yazılı izni ile yapılabilir.
   7.2. Yurt dışı aktarım yalnızca KVKK m.9 hukuki mekanizmalarından
        biriyle (yeterli koruma kararı / standart sözleşme / bağlayıcı
        kurumsal kurallar / açık rıza) yapılır.
   7.3. Aktarım hedefi, yöntemi, hukuki dayanağı sözleşme ekinde
        belirtilir.

8. İLGİLİ KİŞİ HAKLARINA DESTEK
   8.1. Veri İşleyen, KVKK m.11 kapsamındaki ilgili kişi başvurusunu
        Veri Sorumlusu'na yönlendirir; kendisi cevap vermez.
   8.2. Veri Sorumlusu'nun başvuru yanıtlamasında gerekli bilgi/aksiyon
        desteğini ücretsiz ve gecikmeksizin sağlar (azami 5 iş günü).

9. VERİ İHLALİ BİLDİRİMİ
   9.1. Veri İşleyen, herhangi bir veri ihlali şüphesini en geç 24 saat
        içinde Veri Sorumlusu'na bildirir.
   9.2. Bildirim asgari içerik: zaman, etkilenen veri kategorisi, ilgili
        kişi sayısı, alınan tedbirler, devam eden risk.
   9.3. Veri Sorumlusu'nun KVKK Kurulu'na 72 saatlik bildirim sürecine
        tam destek verir; gecikme veya eksik bilgi tedarikçi temerrüdü
        sayılır.

10. YARDIM YÜKÜMLÜLÜĞÜ
    10.1. Veri İşleyen; DPIA, KVKK Kurulu denetimi, veri haritalaması
          gibi süreçlerde Veri Sorumlusu'na yardım sağlar.

11. DENETİM HAKKI
    11.1. Veri Sorumlusu veya yetkili kıldığı bağımsız denetçi, makul
          önbildirim ile Veri İşleyen'in tesislerinde, sistemlerinde ve
          dokümanlarında denetim yapma hakkına sahiptir.
    11.2. Yıllık SOC 2 Type II / ISO 27001 denetim raporları talep
          edilebilir; bu tek başına denetim hakkını ortadan kaldırmaz.
    11.3. Denetim makul ölçülere göre planlanır, ticari sırlara erişimi
          NDA çerçevesinde gerçekleşir.
    11.4. Denetim bulguları için Veri İşleyen 30/60/90 gün CAPA planı
          sunar.

12. SAKLAMA, İADE ve İMHA
    12.1. Veri İşleyen, kişisel verileri yalnızca Sözleşme süresince
          saklar.
    12.2. Sözleşme sona erdiğinde, Veri Sorumlusu'nun seçimine göre
          (a) tüm verileri iade eder, veya (b) güvenli yöntemle imha
          eder, ve imha tutanağı sunar.
    12.3. Yedekler dahil tüm kopyalar imha kapsamına dahildir; yasal
          saklama yükümlülüğü kapsamında tutulan veriler hariç.
    12.4. İade / imha en geç sözleşme bitiminden itibaren 30 gün içinde
          tamamlanır.

13. TAZMİNAT VE SİGORTA
    13.1. Veri İşleyen, KVKK ihlalinden doğacak idari para cezası,
          tazminat, dava giderlerinden kendi kusuru oranında sorumludur.
    13.2. Veri İşleyen, geçerli bir cyber liability sigortasına sahip
          olduğunu beyan eder; poliçe sınırı sözleşmeye eklenir.

14. DEVİR / İSTİSNA
    14.1. Sözleşme, Veri Sorumlusu'nun yazılı izni olmaksızın devredilemez.
    14.2. Hizmet bitimi olmadan veri başka bir vendor'a aktarılamaz.

15. SÜRE VE FESİH
    15.1. Sözleşme süresi: <yıl>
    15.2. Veri Sorumlusu, ağır ihlal halinde derhal feshedebilir.

16. UYGULANACAK HUKUK / YETKİLİ MAHKEME
    16.1. Türkiye Cumhuriyeti hukuku.
    16.2. <Şehir> Mahkemeleri ve İcra Daireleri yetkili.

EKLER
   EK-1: Veri Akış Diyagramı + Veri Kategorileri
   EK-2: Asgari Teknik ve İdari Tedbir Listesi
   EK-3: Onaylı Alt-İşleyen Listesi
   EK-4: Yurt Dışı Aktarım Mekanizması (uygunsa)
```

### 6.2. Ek-2 Asgari Teknik Tedbir Listesi

Sözleşmeye eklenen ek; tedarikçi minimum aşağıdakileri sağlar:

- Erişim kontrolü: RBAC, MFA, JML, çeyreklik review.
- Şifreleme: at-rest AES-256, in-transit TLS 1.2+ (1.3 tercih), HSM/KMS anahtar.
- Loglama: kimlik, yetki, kişisel veri erişimi, log bütünlüğü.
- Yedek: 3-2-1, immutable kopya, restore test.
- IR: 24 saat içinde bildirim, runbook, post-mortem.
- Sızma testi: yıllık.
- Personel: zorunlu eğitim + gizlilik taahhüdü.
- Veri ayrımı: çoklu kiracı (multi-tenant) ortamda mantıksal/fiziksel ayırım.

### 6.3. Standart Sözleşme Maddeleri (Yurt Dışı Aktarım)

KVKK Kurulu'nun ileride "yeterli koruma sağlayan ülke" listesi yayınladığında veya standart sözleşme şablonu çıkardığında, sözleşme eki bu standart hükümlerle uyumlanır. Bu zamana kadar:

- Açık rıza (yetersiz olabilir; süreklilik yok).
- KVKK m.9(2) "yeterli korumayı yazılı olarak taahhüt eden ve Kurul'un izninin alınması" — taahhütname + Kurul izni süreci hukuk ekibi tarafından yürütülür.

## 7. Onboarding ve Erişim Aktivasyonu

| Adım | Sahip | SLA |
|------|-------|-----|
| Sözleşme imzası ve ekleri | Hukuk + Satınalma | – |
| Tedarikçi personeli gizlilik taahhütnamesi | İK + Satınalma | İmzadan önce |
| Erişim talep formu (rol bazlı, JIT) | İş Birimi + IAM | Aktivasyon tarihinden 5 iş günü önce |
| Hesap oluşturma + MFA | IAM | Aktivasyon -1 |
| Onboarding eğitim + bilgi testi | İK + KVKK Sorumlusu | İlk hafta |
| KVKK Sorumlusu kayıt envanterine ekleme | KVKK Sorumlusu | Sözleşme imzası + 7 gün |
| VERBİS güncellemesi (gerekirse) | KVKK Sorumlusu | Aktivasyondan önce |

## 8. Operasyonel İzleme

### 8.1. Periyodik

- Aylık SLA / KPI raporu (uptime, ihlal, başarı oranı).
- Çeyreklik tedarikçi review (Sınıf A); yıllık (B/C).
- Yıllık denetim raporu (SOC 2 Type II / ISO 27001).
- Yıllık sızma testi sonuç paylaşımı.
- Yıllık BCP/DR tatbikatı sonuçları.

### 8.2. Olay Bazlı

- Tedarikçi ihlal bildirimi → 24 saat KVKK Sorumlusu inceleme → KVKK Komitesi eskalasyonu eşiği.
- Tedarikçi tarafında organizasyon değişikliği (M&A, sahiplik, yer değişikliği) → değerlendirme.
- Alt-işleyen değişikliği → onay + sözleşme güncelleme.

### 8.3. SLA / KPI Örneği

| KPI | Hedef | Raporlama |
|-----|-------|-----------|
| Sistem uptime | %99.9+ | Aylık |
| İhlal bildirim süresi | ≤24 saat | Olay başına |
| İlgili kişi başvuru destek SLA | ≤5 iş günü | Olay başına |
| Sızma testi yıllık | 1+ | Yıllık |
| Personel eğitim tamamlama | %100 | Yıllık |
| Patch SLA (kritik) | ≤7 gün | Aylık |
| Erişim review | Çeyreklik | Çeyreklik |

## 9. Çoklu Tedarikçi Haritalaması

Karmaşık ekosistemler için **Veri Akışı Diyagramı** zorunlu:

```
İlgili Kişi (Müşteri) 
     ↓ veri girişi
[Bizim Web Uygulamamız]
     ├── [CDN — Cloudflare] (transit, log) ←—— veri sorumlusu (kendi log için)
     ├── [Auth — Auth0] (kimlik) ←—— veri işleyen
     ├── [DB — RDS PostgreSQL] (kişisel veri at-rest) ←—— veri işleyen (AWS)
     ├── [CRM — Salesforce] (müşteri ilişkisi) ←—— veri işleyen
     │      └── [Alt-işleyen — AWS] (Salesforce'un infra'sı)
     ├── [İletişim — SendGrid] (e-posta) ←—— veri işleyen
     ├── [Analitik — Mixpanel] (kullanım) ←—— ?? (rol değerlendir)
     ├── [Ödeme — Iyzico] (kart) ←—— bağımsız veri sorumlusu (kart)
     └── [Çağrı Merkezi — XYZ] (destek) ←—— veri işleyen
              └── [Alt-işleyen — VoIP sağlayıcı]
```

Her bağlantı için: rol, hukuki dayanak, sözleşme tipi, aktarım mekanizması, sınıf.

VERBİS kaydında ve [02-envanter-ve-sicil/](../02-envanter-ve-sicil/) altındaki envanter dokümanında bu harita güncel tutulur.

## 10. Çıkış Yönetimi (Exit / Off-Boarding)

```
1. Çıkış Kararı (yenileme yok / iptal / değişim)
2. Çıkış Planı Hazırlama (T-90)
3. Veri Migrasyon Planı (gerekirse yeni tedarikçiye veya bize)
4. Veri İade / İmha Talebi (yazılı)
5. İade / İmha Tutanağı (tedarikçi imzalı)
6. Erişim Kapatma (T-0)
7. Sertifika / Anahtar İptal
8. KVKK Envanterinden Çıkartma
9. Lessons Learned + Belge Arşivi
```

Tedarikçi geç kalırsa veya işbirliği yapmazsa: hukuki süreç + KVKK Komitesi raporu + bir sonraki tedarikçi seçiminde uyarı.

## 11. Bulut Hizmet Sağlayıcıları (Özel Bölüm)

ISO 27001 A.5.23 ve KVKK Veri Güvenliği Rehberi'nin "Kişisel Verilerin Bulutta Depolanması" başlığı uyarınca:

### 11.1. Onaylı Bulut Sağlayıcı Listesi

- Onaylı liste KVKK Komitesi tarafından yıllık güncellenir.
- Liste dışı sağlayıcı kullanımı yasak (shadow IT — bkz. CASB, [05-teknik-tedbirler/dlp.md](../05-teknik-tedbirler/dlp.md)).

### 11.2. Bulut-Spesifik Kontroller

- Veri yerleşimi (region) sözleşmeyle bağlanır (yurt içi tercihli).
- Müşteri yönetimli anahtar (CMK / BYOK) Sınıf A için zorunlu.
- Sub-processor şeffaflığı (AWS, Azure, GCP'nin alt yüklenicileri vendor sayfasından izlenir).
- Çıkış stratejisi (data portability) sözleşmeyle.
- Yurt dışı aktarım mekanizması belirgin.

### 11.3. Shared Responsibility Model

Sözleşmeye **shared responsibility matrisi** eklenir; hangi kontrol bizde, hangisi tedarikçide net ayrışır. Bulut sağlayıcı altyapı güvenliğinden sorumlu, biz konfigürasyondan ve veri katmanından (CIS Benchmarks, CSPM) sorumluyuz.

## 12. Veri İşleyen Olduğumuz Senaryolar (Tersine)

Eğer biz **bir başka veri sorumlusu adına** veri işliyorsak (örn. müşterimize SaaS sağlıyorsak):

- Bu sefer biz "veri işleyen" sıfatıyla, müşterinin gerekli sözleşme + denetim hakkı + IR bildirim yükümlülüklerimiz olur.
- KVKK Sorumlusu, çift yönlü envanter tutar (biz işleyen vs. biz sorumlu).
- ISO 27701 (PII Processor) sertifikası bu rol için pazarlama avantajı + uyum kanıtı.

## 13. Disiplin ve Yaptırım

- Tedarikçi sözleşmeyi ihlal ederse: yazılı uyarı → düzeltme planı → uyumsuzluk → fesih.
- Ağır ihlalde (veri sızıntısı, gizlilik) derhal fesih + tazminat + KVKK Kurulu'na bildirim.
- Tedarikçi kara listesi tutulur; benzer ihlalde tekrar tedarikçi alınmaz.

## 14. Yıllık Tedarikçi Yönetim Raporu

KVKK Komitesi'ne yıllık:

- Toplam tedarikçi sayısı / sınıf bazlı dağılım.
- Yeni eklenen / çıkarılan tedarikçi.
- KVKK uyum anketi tamamlanma oranı.
- Sözleşme yenileme oranı.
- Tedarikçi tarafı olaylar / ihlaller.
- Yıllık denetim sonuçları.
- Açık CAPA aksiyonları.
- Toplam yıllık harcama (sınıflandırma bazlı).
- Yurt dışı aktarım envanteri özeti.
- Trend analizi (sektör + bizim).

## 15. Kontrol Listesi

- [ ] Tedarikçi politikası ≤24 ay güncel mi?
- [ ] Tüm tedarikçiler sınıflandırılmış (A/B/C/D), envanterli mi?
- [ ] Sınıf A/B için Veri İşleyen Sözleşmesi imzalı, asgari unsurları içeriyor mu?
- [ ] Sözleşme şablonu Hukuk + KVKK Sorumlusu onaylı, son güncellemesi 12 ay içinde mi?
- [ ] Alt-işleyen listesi şeffaf, değişiklik bildirim mekanizması işliyor mu?
- [ ] Yurt dışı aktarım mekanizması her tedarikçi için belirli mi (m.9 dayanak)?
- [ ] Veri akış diyagramı güncel, envanterle eşli mi?
- [ ] Tedarikçi onboarding sürecinde gizlilik taahhüdü ve eğitim zorunlu mu?
- [ ] Tedarikçinin KVKK Sorumlusu / DPO irtibatı kayıtlı mı?
- [ ] İhlal bildirim SLA (24 saat) sözleşmede yazılı mı?
- [ ] Yıllık SOC 2 / ISO 27001 raporları toplanıyor, gözden geçiriliyor mu?
- [ ] Sızma testi raporları yıllık alınıyor mu?
- [ ] Çeyreklik (Sınıf A) / yıllık (B/C) review yapılıyor mu, kayıt var mı?
- [ ] Bulut sağlayıcı listesi onaylı, BYOK politikası uygulanıyor mu?
- [ ] Çıkış sürecinde veri iade/imha tutanağı standart mı?
- [ ] Tedarikçi ihlali sonrası lessons learned kaydı tutuluyor mu?
- [ ] Tedarikçi kara listesi mekanizması tanımlı mı?
- [ ] Cyber liability sigortası talep ediliyor (Sınıf A/B)?
- [ ] Tedarikçi sözleşmesi devir, alt-yüklenici, fesih hükümleri net mi?
- [ ] VERBİS kaydı tedarikçi değişimleri ile güncel mi?

## 16. Yaygın Hatalar

- "Standart hizmet sözleşmesi" imzalanmış, KVKK / veri işleyen ek protokolü yok.
- Alt-işleyen listesi tutulmuyor; tedarikçi alt yüklenici değiştiriyor, biz haberdar değiliz.
- Cloud sağlayıcının "datasheet"ine güvenip kendi konfigürasyon sorumluluğumuzu fark etmemek.
- Yurt dışı aktarımın hukuki dayanağı belirsiz; m.9'a uygun mekanizma yok.
- Tedarikçi ayrıldıktan sonra erişim kapanmamış (eski kullanıcı hesabı aktif).
- Veri iade/imha tutanağı alınmamış; veri tedarikçinin tarafında yıllarca yatıyor.
- Sözleşmenin denetim hakkı maddesi soyut; pratik denetim yapılamıyor.
- Tedarikçi tarafında ihlal — bizim KVKK Kurulu'na 72 saat süresi azalıyor ama tedarikçi "araştırıyoruz" diye geciktiriyor.
