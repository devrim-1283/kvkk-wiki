---
Doküman: İhlal Müdahale Prosedürü (Incident Response Procedure)
Bölüm: 08-ihlal-yonetimi
Sahip: Bilgi Güvenliği Müdürü (CISO) + KVKK Sorumlusu
Onaylayan: Hukuk Müdürü + KVKK Komitesi + Yönetim Kurulu
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + her ihlal sonrası
İlgili Mevzuat: 6698 sayılı KVKK m.12, KVKKK 24.01.2019/2019-10 sayılı ihlal bildirim Kararı, KVKK Veri Güvenliği Rehberi (2018), 5651 sayılı Kanun, NIST SP 800-61 Rev.2, ISO/IEC 27035-1:2023, ISO/IEC 27001:2022 A.5.24-A.5.28
---

# İhlal Müdahale Prosedürü

## 1. Amaç ve Kapsam

Bu prosedür, kişisel veri ihlali şüphesi veya kesinleşmiş ihlal anında olay yaşam döngüsünün yönetilmesini düzenler. NIST SP 800-61 Rev.2 ve ISO/IEC 27035-1:2023 ile uyumludur ve KVKK'nın 12. maddesi ile Kurul'un 24.01.2019/2019-10 sayılı Kararı'nın gereklerini iç sürece bağlar.

Kapsam: Şirket bünyesindeki tüm kişisel veri varlıkları, veri işleyenler nezdindeki şirket verileri, çalışan kullanım cihazları, müşteri portalları, web siteleri ve mobil uygulamalar.

## 2. Olay Yönetimi Yaşam Döngüsü

```
┌──────────────┐    ┌──────────────────┐    ┌────────────────┐
│  Hazırlık    │ →  │ Tespit ve Analiz │ →  │ Sınırlandırma  │
└──────────────┘    └──────────────────┘    └────────────────┘
                                                    ↓
┌──────────────────┐    ┌──────────────┐    ┌────────────────┐
│ Ders Çıkarma     │ ←  │ Kurtarma     │ ←  │ Yok Etme       │
└──────────────────┘    └──────────────┘    └────────────────┘
```

Her aşama kayıt altına alınır; aşama geçişleri Olay Komutanı kararıyla yapılır.

### 2.1. Hazırlık (Preparation)

Süreç başlamadan önce şu unsurların hazır olması gerekir:
- 7/24 ulaşılabilir CSIRT iletişim listesi (cep, KEP, yedek kanal — Signal/WhatsApp).
- Out-of-band iletişim (mail sunucusu ihlal edilirse alternatif).
- Forensik araç seti (write-blocker, imaj alıcı, EnCase/FTK lisans).
- 3. taraf forensik firmaları ile çerçeve sözleşme (response retainer).
- Hukuki danışman ve kriz iletişim ajansı bağlantıları.
- Olay sınıflandırma matrisi (§3).
- Runbook'lar (§7).
- Tatbikat takvimi (`soak-test-tatbikat.md`).

### 2.2. Tespit ve Analiz (Detection & Analysis)

**Tespit kaynakları:**
- SIEM korelasyon kuralları (Splunk/Sentinel/Wazuh).
- EDR/XDR alarmları (CrowdStrike/SentinelOne/Defender).
- DLP olayları (yetkisiz dışa aktarım).
- IDS/IPS (Suricata, Snort).
- Honeypot/canary token tetiklemeleri.
- Çalışan ihbarları (etik hat, IT helpdesk).
- Üçüncü taraf bildirimleri (CERT, müşteri, araştırmacı, basın).
- Veri işleyen bildirimi.
- Dark web izleme (HaveIBeenPwned, threat intel).

**İlk analiz çıktıları (T+1 saat içinde):**
- Tespit zamanı (UTC + TRT).
- İlk gözlemlenen sistem/varlık.
- Şüpheli olay tipi (ransomware, BEC, data exfil, içeriden, kayıp cihaz, scraping).
- Etkilenmesi muhtemel veri kategorisi (genel, özel nitelikli, finansal).
- Yayılma riski (yatay hareket göstergeleri).

### 2.3. Sınırlandırma (Containment)

İki katmanlı yaklaşım:
- **Kısa vadeli sınırlandırma (T+2 - T+4 saat):** Etkilenen sistemi ağdan izole et (NAC/firewall), kullanıcı hesabını disable et, paylaşımı durdur. Sistemi **kapatma** — bellek imajı için.
- **Uzun vadeli sınırlandırma (T+8 - T+72 saat):** Geçici sistemler kur, parolaları sıfırla, yetki bazlı segmentasyonu sıkılaştır, MFA zorunluluğu yay.

**Karar matrisi:**
| Kriter | Hızlı kapatma | Forensik öncelikli |
|--------|---------------|---------------------|
| Aktif veri exfil | ✅ | ❌ |
| Yatay hareket gözlendi | ✅ | ❌ |
| Hizmet kritik (üretim) | İzolasyon | İzole + paralel forensik |
| Saldırgan hâlâ içeride | ✅ acil izolasyon | ❌ |
| Saldırı bitmiş | ❌ | ✅ |

### 2.4. Yok Etme (Eradication)

- Zararlı yazılımı kaldırma (image yeniden yükleme tercih edilir).
- Backdoor, persistence mekanizmalarını temizleme (scheduled tasks, services, registry, cron).
- IOC bazlı tarama tüm filo.
- Tehdit aktörü hesaplarının iptali.
- Çalınan kimlik bilgileri rotation (parola, API key, SSH key, OAuth token, sertifika).

### 2.5. Kurtarma (Recovery)

- Yedekten temiz geri yükleme (yedeğin de etkilenmediğinden emin ol).
- Aşamalı üretime alma (canary deploy, monitoring artırılmış).
- Kullanıcı erişimlerinin kademeli açılması.
- 30-90 gün artırılmış izleme.

### 2.6. Ders Çıkarma (Lessons Learned)

- Olay sonrası rapor (Post-Incident Report — PIR) en geç **T+30 gün**.
- Kök neden analizi (`kok-neden-analizi.md`).
- CAPA (Corrective and Preventive Actions) takip listesi.
- Politika, prosedür, eğitim güncellemesi.
- Tatbikat senaryosuna ekleme.

## 3. Olay Sınıflandırma Matrisi (Triyaj)

İhlal kararı şu **dört eksen** üzerinden puanlanır:

### 3.1. Etkilenen Kişi Sayısı (E)
| Aralık | Puan |
|--------|------|
| 1 - 100 | 1 |
| 101 - 1.000 | 2 |
| 1.001 - 10.000 | 3 |
| 10.001 - 100.000 | 4 |
| > 100.000 | 5 |

### 3.2. Veri Hassasiyeti (H)
| Kategori | Puan |
|----------|------|
| Pazarlama tercih | 1 |
| Kimlik + iletişim | 2 |
| Finansal (IBAN, kart maskeli) | 3 |
| Kart numarası / kimlik kopyası / lokasyon | 4 |
| Özel nitelikli (sağlık, biyometrik, din, ceza) | 5 |

### 3.3. Yayılma Riski (Y)
| Durum | Puan |
|-------|------|
| Sistem izole, dışa kapalı | 1 |
| İç ağda lateral hareket potansiyeli | 3 |
| İnternete açık, veri çoktan dışarıda | 5 |

### 3.4. Geri Döndürülebilirlik (G)
| Durum | Puan |
|-------|------|
| Veri sadece bütünlük etkilendi, yedekten geri alınabilir | 1 |
| Veri kopyalanmış olabilir ama yayımlanmamış | 3 |
| Veri zaten yayımlanmış / dark web'de | 5 |

**Toplam Risk Skoru = E + H + Y + G** (4-20 arası)

| Skor | Sınıf | Eylem |
|------|-------|-------|
| 4-7 | Düşük | Olay raporu, ihlal değerlendirmesi yap, çoğunlukla bildirim **gerekmez** |
| 8-12 | Orta | İhlal değerlendirmesi zorunlu, Kurul bildirimi büyük olasılık |
| 13-16 | Yüksek | Kurul bildirimi zorunlu + ilgili kişi bildirimi |
| 17-20 | Kritik | Kurul + ilgili kişi + basın açıklaması + üst yönetim eskalasyonu |

> **Uyarı:** Düşük skor otomatik bildirim muafiyeti değildir. Özel nitelikli veriler söz konusuysa kategoriden bağımsız bildirim eğilimi tercih edilir.

## 4. CSIRT Yapısı (Computer Security Incident Response Team)

### 4.1. Çekirdek Ekip (Core Team)

| Pozisyon | Rol | Ana Sorumluluk |
|----------|-----|----------------|
| Olay Komutanı (IC) | Karar mercii | Tüm operasyonun koordinasyonu, eskalasyon |
| Teknik Lider | Forensik & Analiz | İmaj, log, IOC, attribution |
| KVKK Sorumlusu | Düzenleyici | Kurul bildirimi, ilgili kişi iletişimi |
| Hukuk Lideri | Hukuki risk | Sözleşmesel, cezai, regülatif |
| Kurumsal İletişim | Dış iletişim | Basın, sosyal medya, müşteri |
| İK Lideri | İçeriden tehdit | Disiplin, çalışan iletişim |
| Bilgi İşlem Operasyon | Sistem yöneticisi | İzolasyon, kurtarma |

### 4.2. Genişletilmiş Ekip (Extended Team)

Ana CSIRT'in çağıracağı destek rolleri: Finans (fidye, sigorta), Satış (müşteri etkisi), Tedarik Zinciri (3. taraf), Ürün/CTO (mimari karar), Dış Forensik Firma, Dış Hukuk Firması, Sigortacı (siber poliçe), CEO/CFO eskalasyon.

### 4.3. CSIRT Aktivasyonu

Aktivasyon eşikleri:
- **Seviye 1 (Bilgilendirme):** Risk skoru 4-7. Sadece KVKK + CISO + Hukuk e-posta zinciri.
- **Seviye 2 (Sanal toplantı):** Risk skoru 8-12. Çekirdek ekip 1 saat içinde bağlanır.
- **Seviye 3 (Tam aktivasyon):** Risk skoru 13+. Çekirdek ekip 30 dakika içinde fiziksel/sanal "war room"da. Genişletilmiş ekip alarmı.
- **Seviye 4 (Krizi):** Risk skoru 17+. Yönetim Kurulu bilgilendirilir, basın koordinasyonu.

## 5. Komünikasyon Ağacı

```
Tespit eden çalışan
        ↓
IT Helpdesk (7/24 nöbet — etik hat)
        ↓
SOC L1 → SOC L2 (15 dk SLA)
        ↓
Bilgi Güvenliği Vardiya Lideri (30 dk SLA)
        ↓
CISO + KVKK Sorumlusu (60 dk SLA — dual notification)
        ↓
Olay Komutanı atanır
        ↓
CSIRT aktivasyonu (seviye bazlı)
        ↓
Yönetim eskalasyonu (Seviye 3+: CEO; Seviye 4: Yönetim Kurulu)
        ↓
Dış paydaş iletişimi (Kurul, ilgili kişi, basın, sigortacı)
```

**İletişim kanalları:**
- Birincil: Kurumsal e-posta + Telefon.
- İkincil (e-posta sistemi etkilendiyse): Kurumsal Signal grubu.
- Üçüncül: Kişisel cep + WhatsApp.
- Out-of-band: Konferans köprü (3. taraf — Webex/Teams alternatifi).

**Sessizlik kuralı (Need-to-Know):** Olay detayları sadece CSIRT içinde paylaşılır. İç duyuru CISO + Kurumsal İletişim çift onayı olmadan yapılmaz. Sosyal medya paylaşımı yasaktır (çalışan etik kurallarına bağlı).

## 6. Olay Kayıt Sistemi (Incident Log)

Her olay anında **OLAY-YYYY-NNNN** formatında numaralandırılır. Aşağıdaki bilgiler dakika hassasiyetinde kaydedilir:

| Alan | Açıklama |
|------|----------|
| Olay No | Otomatik üretilen ID |
| Tespit Tarih/Saat | UTC + TRT, dakika hassasiyetinde |
| Öğrenme Anı | "Makul şüphe" eşiğinin geçildiği an (72 saat sayacı) |
| Tespit Kaynağı | SIEM, EDR, ihbar, vb. |
| Kategori | Ransomware, BEC, exfil, kayıp cihaz, içeriden, üçüncü taraf |
| Etkilenen Sistem | Hostname, IP, uygulama, veritabanı |
| Etkilenen Veri | Kategori + tahmini kayıt sayısı |
| Risk Skoru | E+H+Y+G |
| Sınıf | Düşük/Orta/Yüksek/Kritik |
| Aktivasyon Seviyesi | 1-4 |
| Olay Komutanı | İsim |
| Aşama | Hazırlık/Tespit/Sınırlandırma/Yok Etme/Kurtarma/Kapanış |
| Ana eylemler kronolojik | Saatlik girdi |
| Kurul bildirimi | Tarih/saat/referans no |
| İlgili kişi bildirimi | Yöntem/sayı/tarih |
| Sigortacı bildirimi | Tarih |
| Adli bildirim (gerekiyorsa) | Tarih/savcılık |
| Kapanış tarihi | RCA tamamlandığında |

Kayıt sistemi **immutable** olmalıdır (write-once, tamper-evident — Splunk Enterprise SIEM, Wazuh + S3 Object Lock, vb.).

## 7. Senaryo Bazlı Runbook'lar

Aşağıdaki yedi senaryo için detaylı runbook üretilmiş ve tatbikatlarda test edilmiştir. Bu bölümde özet karar yolu verilmiştir; tam runbook'lar `99-sablonlar/runbooks/` altındadır.

### 7.1. Runbook A — Ransomware

```
T+0  Şifrelenmiş dosya/ekran tespiti
T+15 dk  Etkilenen makineyi ağdan izole, KAPATMA
T+30 dk  EDR taraması — yayılma kontrolü
T+1 saat  Yedeklerin sağlamlığı doğrula (offline backup)
T+2 saat  Saldırgan iletişim kanalını izole (T2T)
T+4 saat  Forensik imaj alımı başlar
T+8 saat  Etkilenen kişisel veri kapsamı (DLP raporu, klasör içerik analizi)
T+24 saat  Kurul taslak bildirimi
T+48 saat  Yedekten kurtarma + canary
T+72 saat  Kurul nihai bildirimi
```

**Kritik kararlar:**
- Fidye ödenmez (yönetim kurulu kararı + OFAC/yaptırım uyumu).
- Decryption tool veritabanları kontrol edilir (No More Ransom).
- Sigorta poliçesi devreye alınır (T+12 saat).

### 7.2. Runbook B — İçeriden Veri Sızıntısı (Insider Data Exfiltration)

```
T+0  DLP/UEBA alarmı — anormal indirme/USB/upload
T+15 dk  IT — kullanıcı oturumunu sessizce izle (canlı kanıt)
T+30 dk  İK ve Hukuk koordinasyonu
T+1 saat  Yetki dondurma kararı (kullanıcı haberdar olmadan)
T+2 saat  Endpoint inceleme — neyin alındığı, nereye gönderildiği
T+4 saat  Kullanıcıyla görüşme (HR + Hukuk + İK Direktörü)
T+8 saat  Cihaz forensik imajı
T+24 saat  Veri geri çağırma (üçüncü taraflarsa cease-and-desist)
T+48 saat  Adli süreç değerlendirmesi (TCK m.136 verileri hukuka aykırı verme)
T+72 saat  Kurul bildirimi
```

### 7.3. Runbook C — Kayıp/Çalıntı Cihaz (Lost Device)

```
T+0  Çalışan kayıp/çalıntı bildirir
T+15 dk  MDM ile uzaktan kilit
T+30 dk  Cihaz şifrelenmiş mi doğrula (BitLocker/FileVault status)
T+1 saat  Şifrelenmemişse YÜKSEK risk
T+2 saat  Hesap parolası sıfırla, MFA token iptali
T+4 saat  E-posta cache, OneDrive sync, son aktiviteler analizi
T+8 saat  İçerik kapsamı belirleme
T+12 saat  Karakola kayıp ihbarı (zorunlu)
T+24 saat  Cihaz silinme komutu (geri dönmedi)
T+72 saat  Kurul bildirimi (şifrelenmemiş cihazsa)
```

### 7.4. Runbook D — Üçüncü Taraf İhlali (Vendor/Processor Breach)

```
T+0  Veri işleyenden ihlal bildirimi geldi
T+15 dk  Sözleşme kontrolü — bildirim süresine uyumlu mu?
T+30 dk  Kapsam: hangi şirket verisi etkilenmiş?
T+1 saat  Geçici askıya alma kararı
T+2 saat  Bağımsız doğrulama talebi
T+4 saat  Şirket içi etki haritalama
T+24 saat  Kurul bildirimi (veri sorumlusu olarak BİZ bildiriyoruz)
T+48 saat  Sözleşmesel yaptırım, alternatif sağlayıcı planı
```

> **Önemli:** Veri işleyenin geç bildirimi mazeret değildir — Kurul nezdinde sorumluluk veri sorumlusunundur. Sözleşmeye **24 saat içinde bildirim** klozu ve gecikme cezası eklenmiş olmalıdır (`07-aktarim` bölümü).

### 7.5. Runbook E — BEC / Hesap Ele Geçirme (Business Email Compromise)

```
T+0  Anormal e-posta gönderim/yönlendirme tespit
T+15 dk  Hesap session kill, parola reset, MFA reset
T+30 dk  Inbox rule/forwarder temizliği
T+1 saat  Audit log — gönderilen mailler, açılan paylaşımlar
T+2 saat  Hassas içerik tespiti (KVKK + finans)
T+4 saat  Karşı taraf bildirimi (fraud önleme)
T+8 saat  Hesabın eriştiği SaaS API key rotation
T+24 saat  Kurul bildirimi (kişisel veri içeren mail trafiği etkilendiyse)
```

### 7.6. Runbook F — Web Sitesi / API Veri Sızıntısı (Scraping / Public Leak)

```
T+0  GitHub/Pastebin/forum'da şirket verisi keşfi
T+15 dk  Kaynak doğrulama — gerçekten bizim mi?
T+30 dk  DMCA / takedown talebi
T+1 saat  Sızıntı vektörü (hangi endpoint, hangi parametre)
T+2 saat  Endpoint kapatma / WAF kuralı
T+4 saat  Erişim log analizi — kapsam
T+24 saat  Kurul bildirimi
T+48 saat  İlgili kişi bildirimi (eposta, SMS, web)
```

### 7.7. Runbook G — Fiziksel İhlal (Arşiv/Belge Kaybı)

```
T+0  Fiziksel arşiv eksiklik/yangın/su baskını
T+30 dk  Olay yerine kontrollü erişim
T+1 saat  Eksik kategori/dosya tipi tespiti
T+2 saat  CCTV inceleme (kasıt mı, kaza mı?)
T+8 saat  Kapsam belirleme — hangi ilgili kişi?
T+24 saat  Gerekirse Kurul bildirimi
```

## 8. Saatlik Karar Matrisi

| Saat | Yapılması Gereken | Sahip | Çıktı |
|------|-------------------|-------|-------|
| T+0 | Olay açılır, ID atanır | SOC | OLAY-YYYY-NNNN |
| T+15 dk | Acil sınırlandırma kararı | Vardiya Lideri | İzolasyon ya da gözlem |
| T+30 dk | Çekirdek CSIRT haberdar | CISO | Aktivasyon seviyesi |
| T+1 saat | İlk triyaj raporu | Olay Komutanı | Risk skoru, sınıf |
| T+2 saat | War room toplantısı | IC | Aşama planı, görev dağılımı |
| T+4 saat | Sınırlandırma onayı | IC + CISO | İzolasyon doğrulandı |
| T+8 saat | Kapsam ön raporu | Teknik Lider | Veri kategorisi + sayı tahmini |
| T+12 saat | Sigortacı bildirimi | Hukuk + Finans | Poliçe aktivasyonu |
| T+24 saat | Kurul taslak bildirimi (eksik veri kabul) | KVKK Sorumlusu | Form gönderildi |
| T+48 saat | İlgili kişi bildirim taslağı | KVKK + İletişim | Onay bekleyen metin |
| T+72 saat | Kurul nihai bildirimi (kesin veri) | KVKK Sorumlusu | Form ek bilgi |
| T+5 gün | İlgili kişi bildirimi başlar | KVKK + İletişim | E-posta/SMS gönderim |
| T+15 gün | Aşamalı kurtarma tamamlandı | Operasyon | Üretim normal |
| T+30 gün | Post-Incident Report (PIR) | IC | Rapor + CAPA listesi |
| T+90 gün | CAPA tamamlanma denetimi | KVKK Sorumlusu | Kapanış raporu |
| T+1 yıl | Tatbikat senaryosuna işleme | Tatbikat Lideri | Yeni senaryo |

## 9. Forensik Kanıt Yönetimi

- Chain of custody formu her cihaz/log seti için doldurulur.
- Hash (SHA-256) doğrulamasıyla bütünlük teyit edilir.
- Kanıtlar **sigortalı kasada** (fiziksel kanıt) ve **immutable storage'da** (dijital kanıt) saklanır.
- Kanıt saklama süresi: **5 yıl** (zamanaşımı + idari yaptırım itiraz süreleri).
- Üçüncü taraf forensik firma kullanılıyorsa NDA + KVKK veri işleyen sözleşmesi imzalanır.

## 10. Veri İşleyen Bildirim Yükümlülüğü (Şirketimiz Veri Sorumlusu)

Veri işleyenler (bulut sağlayıcı, dış kaynak, IK SaaS, kargo, çağrı merkezi):
- **24 saat içinde** sözleşme gereği şirketimize bildirim yapar.
- Bildirim KEP veya sözleşmede tanımlı kanaldan gelir.
- Eksik bildirim sözleşmesel cezayı ve tek taraflı fesih hakkını doğurur.
- Veri işleyenin geç bildirimi şirketimizin Kurul karşısındaki 72 saat sayacına eklenmez — sayaç **bizim öğrenme anımız**dan başlar; ancak Kurul, geç bildirimden veri sorumlusunu da sorumlu tutabilir (sözleşmesel kontrolün yetersizliği gerekçesiyle).

## 11. Kurul ile Yazışma Standartları

- Bildirim KEP üzerinden **kvkk@hs01.kep.tr** adresine yapılır.
- Eksik bilgi sonradan tamamlanabilir; ancak ilk bildirim **mümkün olan en doluluk seviyesi** ile yapılır.
- Kurul ek bilgi talep ederse cevap süresi tebliğ edilen tarihten itibaren **15 gün** (Kurul yazısında belirtilir).
- Tüm yazışma arşivlenir ve **Kurul Yazışma Defteri**ne işlenir.

## 12. Adli Bildirim ve Diğer Düzenleyiciler

KVKK bildirimi yanında değerlendirilmesi gereken diğer yükümlülükler:
- **TCK m.136-138:** Verileri hukuka aykırı ele geçirme/verme — savcılık bildirimi (özellikle içeriden tehdit).
- **5651 sayılı Kanun:** Erişim/yer sağlayıcı kayıt yükümlülüğü.
- **BDDK / SPK / EPDK:** Sektörel ihlal bildirim rejimleri (banka, sermaye piyasası, enerji).
- **GDPR (yurt dışı vatandaş etkilendiyse):** AB temsilcisi varsa ilgili DPA'ya 72 saat bildirim.
- **EMRA / BTK:** Telekom sektörü ek bildirim yükümlülükleri.

## 13. Eğitim ve Farkındalık

- Tüm çalışan: yıllık 1 saat olay raporlama eğitimi.
- IT/SOC: çeyreklik 4 saat teknik müdahale tatbikatı.
- CSIRT çekirdek ekip: yıllık 16 saat tabletop + 8 saat fiziksel tatbikat.
- Yönetim Kurulu: yıllık 1 saat kriz yönetimi briefing.

## 14. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi + YK |

## 15. Ekler

- Ek-1: CSIRT İletişim Listesi (kontrollü erişim).
- Ek-2: Olay Sınıflandırma Karar Ağacı (tek sayfa A3).
- Ek-3: Forensik Çantası İçerik Listesi.
- Ek-4: Sigortacı Bildirim Şablonu.
- Ek-5: Kurul KEP Yazışma Şablonu.
