---
Doküman: Teknik Tedbirler — Bölüm Girişi
Bölüm: 05-teknik-tedbirler
Sahip: Bilgi Güvenliği Yöneticisi (CISO)
Onaylayan: BT Direktörü + KVKK Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (mevzuat değişikliği, ihlal, büyük mimari değişiklik, yeni teknoloji benimseme)
İlgili Mevzuat: 6698 sayılı KVKK m.12 (Veri Güvenliğine İlişkin Yükümlülükler), Veri Sorumluları Sicili Hakkında Yönetmelik m.9(1)(e), Kişisel Veri Güvenliği Rehberi (Teknik ve İdari Tedbirler), 5651 sayılı Kanun (loglama yükümlülüğü ile ilgili kısımlar), Bankacılık Düzenleme ve Denetleme Kurumu (BDDK) Bilgi Sistemleri ve Elektronik Bankacılık Hizmetleri Hakkında Yönetmelik (uygulanabildiği yerlerde)
İlgili Standart: ISO/IEC 27001:2022 Annex A (özellikle A.5.15 Erişim Kontrolü, A.8 Teknolojik Kontroller), ISO/IEC 27002:2022, ISO/IEC 27701:2019, NIST Cybersecurity Framework 2.0 (PROTECT, DETECT, RESPOND), NIST SP 800-53 Rev. 5, NIST SP 800-63B (Dijital Kimlik), ENISA "Handbook on Security of Personal Data Processing" (2018, güncel sürüm), GDPR Art. 32 ("appropriate technical and organisational measures"), CIS Controls v8, OWASP ASVS 4.0
---

# 05 — Teknik Tedbirler

## 1. Amaç ve Kapsam

Bu bölüm, KVKK m.12 uyarınca veri sorumlusu sıfatıyla işlediğimiz kişisel verilerin **hukuka aykırı işlenmesini ve hukuka aykırı erişilmesini önlemek** ile **muhafazasını sağlamak** amacıyla aldığımız teknik tedbirleri bütüncül biçimde tanımlar. Tedbirler; on-prem, hibrit ve bulut (IaaS/PaaS/SaaS) ortamlarda işlenen tüm kişisel veri kategorilerini kapsar.

KVKK m.12(1) hükmü, "uygun güvenlik düzeyini temin etmeye yönelik gerekli her türlü teknik ve idari tedbirleri almak" yükümlülüğünü veri sorumlusuna açıkça yüklemektedir. **Uygun güvenlik düzeyi** tek bir mutlak eşik değildir; işlenen kişisel verinin niteliği, miktarı, ilgili kişi grubu, işleme amacı, teknik gelişmişlik düzeyi (state of the art) ve maliyet/fayda dengesi göz önüne alınarak belirlenir. Bu çerçeve **risk-tabanlı (risk-based)** bir yaklaşımdır ve GDPR Art. 32, NIST CSF ile ISO 27001'in temel mantığıyla örtüşür.

## 2. Bu Bölümdeki Dokümanlar

| # | Doküman | İçerik | Sahibi |
|---|---------|--------|--------|
| 1 | [erisim-kontrolu.md](erisim-kontrolu.md) | Least privilege, RBAC/ABAC, JML, PAM, erişim review | BT Operasyon + CISO |
| 2 | [kimlik-dogrulama.md](kimlik-dogrulama.md) | MFA, SSO/IdP, parola politikası, service account | IAM Ekibi |
| 3 | [sifreleme.md](sifreleme.md) | At-rest, in-transit, anahtar yönetimi, HSM/KMS, PQC | Kripto Mühendisliği + CISO |
| 4 | [ag-guvenligi.md](ag-guvenligi.md) | Segmentasyon, zero trust, FW/IDS/IPS/WAF, ZTNA | Ağ Güvenliği |
| 5 | [log-yonetimi.md](log-yonetimi.md) | Loglama, SIEM, UEBA, 5651, runbook | SOC + CISO |
| 6 | [yedekleme.md](yedekleme.md) | 3-2-1, immutable, restore test, DR/BCP, RTO/RPO | BT Operasyon |
| 7 | [veri-maskeleme-anonimlestirme.md](veri-maskeleme-anonimlestirme.md) | Masking, tokenization, anonim/pseudonim, k-anon | Veri Mühendisliği + KVKK |
| 8 | [dlp.md](dlp.md) | Endpoint/Network/Cloud DLP, CASB, çalışan mahremiyeti | DLP Ekibi + CISO |
| 9 | [uygulama-guvenligi.md](uygulama-guvenligi.md) | Secure SDLC, SAST/DAST/SCA, sızma testi, OWASP | AppSec |
| 10 | [teknik-tedbir-kontrol-listesi.md](teknik-tedbir-kontrol-listesi.md) | 80+ maddelik denetim listesi | İç Denetim |

## 3. Yönetişim ve Sorumluluk Modeli (RACI)

| Faaliyet | Yürüten (R) | Hesap Veren (A) | Danışılan (C) | Bilgi Verilen (I) |
|----------|-------------|-----------------|----------------|-------------------|
| Teknik tedbir politikalarının yazımı | CISO ekibi | CISO | KVKK Sorumlusu, Hukuk, BT Direktörü | Üst Yönetim |
| Politikaların onayı | CISO | BT Direktörü | KVKK Komitesi | Yönetim Kurulu |
| Operasyonel uygulama | İlgili teknik ekip | BT Operasyon Müdürü | CISO, KVKK Sorumlusu | İç Denetim |
| Ölçüm ve raporlama | SOC + CISO PMO | CISO | KVKK Komitesi | Üst Yönetim |
| İç denetim | İç Denetim | Denetim Komitesi | CISO, KVKK Sorumlusu | Yönetim Kurulu |
| Aksiyon takibi (CAPA) | İlgili sahipler | CISO | İç Denetim | KVKK Komitesi |

## 4. Risk-Tabanlı Tasarım İlkeleri

Teknik tedbirlerin tasarımında aşağıdaki ilkeler **istisnasız** uygulanır:

1. **Defence in Depth (Katmanlı Güvenlik):** Tek bir kontrolün başarısız olması verinin açığa çıkmasına yol açmamalıdır. Ağ → ana makine → uygulama → veri katmanlarında bağımsız kontroller.
2. **Least Privilege:** Her kullanıcı, servis hesabı ve uygulama, görevini yapmak için gereken **minimum** yetkiyle çalışır.
3. **Need-to-Know:** Kişisel veriye erişim yalnızca o veriyi görmesi iş gereği olan kişiyle sınırlıdır. Yetkili olmak ≠ erişmek.
4. **Default Deny:** Açıkça izin verilmeyen her erişim reddedilir.
5. **Zero Trust:** Hiçbir trafiğe ağ konumuna göre güven verilmez; her erişim talebi kimliği, cihazı, oturumu, davranışı doğrulanarak kabul edilir.
6. **Privacy by Design / Default (KVKK m.4 ölçülülük + GDPR Art. 25):** Veri minimizasyonu, amaç sınırlaması ve veri koruma önlemleri sistemin tasarımına gömülür, sonradan eklenmez.
7. **Crypto Agility:** Kullanılan algoritma ve anahtar boyutlarının güncellenmesini/değiştirilmesini engelleyecek bağımlılıklar yaratılmaz (özellikle PQC geçişi öncesi kritik).
8. **Fail Secure:** Bir bileşenin arızalanması, varsayılan olarak veriyi açığa çıkaran değil koruyan bir duruma yönelmelidir.
9. **Auditability:** Tüm güvenlik açısından önemli olaylar geri dönülemez biçimde kayıt altına alınır ve denetlenebilir.
10. **Minimization in Logs:** Log içeriği, tedbirin kendisinin amacını aşan kişisel veriyi içermemelidir.

## 5. KVKK Veri Güvenliği Rehberi ile Eşleşme

Kurum'un yayımladığı Kişisel Veri Güvenliği Rehberi, teknik tedbir başlıklarını aşağıdaki gibi gruplandırır. Bizim doküman setimiz bu yapıyı **birebir** kapsar ve ek olarak modern güvenlik standartlarına eşler:

| KVKK Rehberi Başlığı | Bu Bölümde Karşılığı | ISO 27002:2022 Kontrolü |
|----------------------|----------------------|-------------------------|
| Siber Güvenliğin Sağlanması | ag-guvenligi.md, uygulama-guvenligi.md | A.8.20–A.8.27 |
| Kişisel Veri Güvenliği Takibi | log-yonetimi.md | A.8.15, A.8.16, A.5.7 |
| Kişisel Veri İçeren Ortamların Güvenliği | sifreleme.md, ag-guvenligi.md | A.7.10, A.8.10, A.8.13 |
| Kişisel Verilerin Bulutta Depolanması | sifreleme.md, ag-guvenligi.md, tedarikci (06) | A.5.23 |
| Bilgi Teknolojileri Sistemleri Tedariği, Geliştirilmesi ve Bakımı | uygulama-guvenligi.md | A.8.25–A.8.34 |
| Kişisel Verilerin Yedeklenmesi | yedekleme.md | A.8.13 |
| Kullanıcı Hesap Yönetimi ve Yetki Matrisi | erisim-kontrolu.md, kimlik-dogrulama.md | A.5.15–A.5.18, A.8.2, A.8.3, A.8.5 |
| Şifreleme | sifreleme.md | A.8.24 |
| Veri Maskeleme | veri-maskeleme-anonimlestirme.md | A.8.11 |
| Saldırı Tespit ve Önleme Sistemleri | ag-guvenligi.md, log-yonetimi.md | A.8.16 |
| Sızma Testi | uygulama-guvenligi.md | A.8.29 |
| Bilgi Güvenliği Olay Yönetimi | log-yonetimi.md + 08-ihlal-yonetimi/ | A.5.24–A.5.28 |

## 6. Ölçüm ve KPI'lar

Teknik tedbirlerin etkinliği yalnızca "var/yok" düzleminde değerlendirilemez; **ölçülebilir** olmalıdır. Aşağıdaki gösterge seti yıllık güncellenir, çeyreklik raporlanır:

- Kritik açık kapatma süresi (MTTR-Critical) — hedef ≤ 7 gün.
- MFA kapsam yüzdesi — hedef %100 (yönetici, uzaktan erişim, kişisel veri içeren tüm uygulamalar).
- Yetkili hesap oranı (privileged user / total user) — hedef ≤ %5.
- Erişim review tamamlanma oranı — hedef %100 her çeyrek.
- Yedek geri yükleme test başarı oranı — hedef ≥ %99.
- Ortalama log toplama gecikmesi — hedef ≤ 5 dakika.
- SIEM kapsam (varlık envanteri içinde loglanan oranı) — hedef ≥ %95.
- Kritik sistem TLS uyumluluk oranı — hedef %100 TLS 1.2+ (1.3 tercihli).
- DLP olay false-positive oranı — hedef ≤ %20.
- Kapatılmamış JML (mover/leaver) eylemi — hedef 0 (24 saatten fazla bekleyen).

## 7. Bu Bölümün Diğer Bölümlerle İlişkisi

- **00-yonetisim/** — Politika onay zinciri ve roller burada tanımlanan tedbirleri yetkilendirir.
- **04-veri-saklama-ve-imha/** — Saklama süresi sona eren verilerin teknik imhası burada tanımlı şifreleme ve anahtar yönetimi süreçlerinden faydalanır (crypto-shredding).
- **06-idari-tedbirler/** — Tedarikçi yönetimi, eğitim ve politika çerçevesi teknik tedbirlerin "etkin uygulanmasını" sağlar.
- **08-ihlal-yonetimi/** — Log yönetimi ve SIEM tespitleri burayı besler.
- **11-denetim-ve-uyum/** — İç denetim, bu bölümün kontrol listelerini örnekleme yöntemiyle test eder.

## 8. Yıllık Gözden Geçirme

CISO, bu bölümün tüm dokümanlarını **her takvim yılı Q1'inde** ve aşağıdaki tetikleyiciler oluştuğunda gözden geçirir:

- Mevzuat değişikliği (KVKK, ikincil mevzuat, sektörel düzenleme),
- Kurumsal kullanılan kritik teknolojinin değişimi (örn. yeni bulut sağlayıcıya geçiş),
- Yeni bir kişisel veri kategorisi işlenmeye başlandığında (özellikle özel nitelikli),
- Veri ihlali veya ramak kala olayı sonrası,
- Bağımsız denetim bulgusu.

Versiyonlama: **MAJOR.MINOR**. MAJOR; politika kapsamının değişimi. MINOR; içerik güncellemesi. Geriye dönük tüm sürümler [12-mevzuat-arsiv/](../12-mevzuat-arsiv/) altında tutulur.
