---
Doküman: Personel Eğitim ve Farkındalık Programı
Bölüm: 06-idari-tedbirler
Sahip: İK Direktörü + KVKK Sorumlusu
Onaylayan: KVKK Komitesi + Üst Yönetim
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (önemli ihlal, mevzuat değişikliği, yeni teknoloji)
İlgili Mevzuat: 6698 sayılı KVKK m.12; KVKK Veri Güvenliği Rehberi — "Eğitim ve Farkındalık Faaliyetleri"
İlgili Standart: ISO/IEC 27001:2022 A.6.3 (Information Security Awareness, Education and Training); ISO/IEC 27701:2019; NIST CSF 2.0 PR.AT (Awareness and Training); NIST SP 800-50; NIST SP 800-181 (NICE Workforce Framework); ENISA "Awareness Raising Quality Standard"
---

# Personel Eğitim ve Farkındalık Programı

## 1. Amaç

Tüm çalışan, yönetici, danışman, stajyer, geçici personel ve üçüncü taraf personelinin **rolüne uygun düzeyde** kişisel veri koruma ve bilgi güvenliği bilgisine sahip olmasını ve bu bilgiyi günlük iş davranışına yansıtmasını sağlamak. KVKK Veri Güvenliği Rehberi'nde "Eğitim ve Farkındalık Faaliyetleri" başlığının doğrudan operasyonel uygulamasıdır.

## 2. İlkeler

1. **Zorunluluk:** Eğitim **opsiyonel değildir** — işe başlama haftası içinde ve yıllık olarak tazeleme zorunludur.
2. **Rol Bazlı:** Genel müfredat + role özel modüller. Çağrı merkezi temsilcisinin ihtiyaçları, yazılım geliştiricininkinden farklıdır.
3. **Kanıt Gerekli:** Tamamlanma kayıtları (LMS) denetim için saklanır.
4. **Etkinlik Ölçümü:** Sadece tamamlanma değil, **bilgi sınaması ve davranış değişimi** ölçülür.
5. **Tetkikleyici:** Olay sonrası, mevzuat değişimi, yeni teknoloji benimseme tetiklenmiş eğitim getirir.
6. **Sürekli (Just-in-Time):** Yıllık tek seferlik eğitim yetmez; mikro öğrenme + simülasyon + iletişim kampanyaları.
7. **Mahremiyet:** Eğitim katılım ve performans verileri çalışanın özlük dosyasında, sınırlı erişimle.

## 3. Hedef Kitle ve Modüller

### 3.1. Genel Modüller (Tüm Çalışanlar)

| Modül | Süre | Sıklık |
|-------|------|--------|
| KVKK Temelleri | 60 dk | İşe başlangıç + yıllık |
| Bilgi Güvenliği Temelleri | 60 dk | İşe başlangıç + yıllık |
| Phishing & Sosyal Mühendislik | 30 dk | Yıllık |
| Şifre & MFA | 20 dk | İşe başlangıç + yıllık |
| Temiz Masa & Temiz Ekran | 15 dk | Yıllık |
| Mobil & BYOD Güvenliği | 20 dk | Yıllık |
| Veri İhlali Tanıma & Bildirim | 20 dk | Yıllık |
| İlgili Kişi Hakları (m.11) | 30 dk | Yıllık |

### 3.2. Rol Bazlı Modüller

| Rol | Ek Modüller |
|-----|-------------|
| **İK** | Çalışan veri kategorileri, özlük dosyası, gizlilik taahhütnamesi, ayrılış süreci, özel nitelikli veri (sağlık, sendika), DPIA hassasiyetleri |
| **BT / DevOps / SRE** | Erişim yönetimi, log mahremiyeti, üretim verisi yasakları, secrets, IR runbook |
| **Yazılım Geliştirici** | Secure SDLC, OWASP Top 10/API/LLM, tehdit modelleme, secrets, kişisel veri minimizasyonu, kod incelemesi |
| **Veri / Analitik / BI** | Maskeleme/anonim, re-identification riski, DPIA, BI-de aydınlatma |
| **AI / ML Mühendisleri** | LLM Top 10, eğitim verisi mahremiyeti, model memorization, açıklanabilirlik, otomatik karar |
| **Çağrı Merkezi / Müşteri Hizmetleri** | İlgili kişi başvurusu, kimlik doğrulama, sosyal mühendislik (vishing), ekran maskelemesi, çağrı kaydı kuralları |
| **Satış / Pazarlama** | Pazarlama izinleri (İYS), açık rıza, çerez, dış araç entegrasyonu, profil bazlı pazarlama |
| **Finans / Muhasebe** | PCI farkındalığı, finansal dolandırıcılık (BEC), kart verisi yasakları |
| **Hukuk** | KVKK güncel kararlar, sözleşme şablonları, ihlal bildirimi, AB GDPR (uluslararası iş için) |
| **Yöneticiler** | Mover/leaver kontrol, takım eğitim sorumluluğu, ihlal raporlama, açık liderlik |
| **Üst Yönetim** | Kurul karar / yaptırım örnekleri, raporlama, risk iştahı, kriz iletişimi |
| **Tedarikçi/Danışman** | Erişim sınırları, gizlilik taahhütnamesi, IR bildirim |

## 4. Müfredat İçerikleri (Detay Anahatları)

### 4.1. KVKK Temelleri

- KVKK kapsamı, tanımlar (kişisel veri, özel nitelikli, veri sorumlusu, veri işleyen).
- Genel ilkeler (m.4) — hukuka uygunluk, doğruluk, belirli ve meşru amaç, ölçülülük, saklama süresi.
- İşleme şartları (m.5, m.6) — açık rıza ve diğer hukuki sebepler.
- Aydınlatma yükümlülüğü (m.10).
- İlgili kişi hakları (m.11) ve başvuru.
- Veri Sorumlusu - Veri İşleyen ayrımı.
- Yurt içi ve yurt dışı aktarım (m.8, m.9).
- VERBİS.
- KVKK Kurumu kararları, yaptırım örnekleri (idari para cezası, TCK m.135-140).
- Şirket içi süreçlere bağlama: aydınlatma metinleri, başvuru e-posta adresi, ihlal hattı.

### 4.2. Phishing & Sosyal Mühendislik

- Yaygın senaryolar: fatura sahtekarlığı, BEC (Business Email Compromise), kargo, banka, IK / İK uzantısı, AI-clone ses, deepfake video.
- "Acillik + otorite + merak" üçlüsü.
- Hover, alan kontrolü, eklerle ilgili davranış.
- Şüpheli mesajı bildirme (one-click report button).
- Vishing (sesli), smishing (SMS), QR phishing.
- "İçeriden istek" denetimi (CFO'dan acil EFT talebi → süreç dışı).
- Phishing simülasyon programı + sonuç odaklı eğitim.

### 4.3. Şifre & MFA

- NIST 800-63B uyumlu parola davranışı (uzunluk, passphrase, parola yöneticisi).
- MFA neden? FIDO2 vs. SMS.
- Push fatigue saldırısı + savunma.
- Hesap ele geçirme tespiti (giriş bildirimleri, anormal aktivite).
- Parola yöneticisi kullanımı (Bitwarden, 1Password kurumsal).
- Hesap kurtarma süreci.

### 4.4. Veri İhlali Tanıma ve Bildirim

- "İhlal" nedir? (kişisel veriye yetkisiz erişim, kayıp, ifşa, değişiklik, hizmet kesintisi).
- Tipik göstergeler: kayıp dizüstü/USB, yanlış e-posta gönderimi, açık link paylaşımı, şüpheli giriş bildirimi.
- Bildirim hattı: nereye, nasıl, ne zaman.
- "Cezalandırılma korkusu yok" — açık bildirim teşviki (kasıtlı olmayan hatalar için).
- 72 saat Kurul'a bildirim arka planı.
- Bildirim örnek formu.

### 4.5. Geliştirici Güvenliği (Detay)

- Tehdit modelleme alıştırması.
- OWASP Top 10 kod örnekleriyle.
- Secrets management, dependency hygiene, SBOM.
- Hassas veri logging yasakları (regex tarama).
- Kişisel veri minimizasyonu — alan eklemeden önce gerekçe.
- Test ortamı veri yasakları.
- Güvenli kod inceleme.

### 4.6. AI / ML Modülü (Yeni)

- LLM Top 10.
- Eğitim verisi mahremiyeti — "modeli ne kadar bilir?"
- Prompt injection ve jailbreak.
- Otomatik karar alma + KVKK m.4 ölçülülük + ilgili kişi hakları.
- Tedarikçi LLM API'lerine kişisel veri gönderme — aktarım rejimi, sözleşme.
- Audit log + insan denetimi.

## 5. Sunum Formatları

- **e-Learning (LMS):** Modül, video, quiz. Ana çatı.
- **Sınıf eğitimi:** Yöneticiler, hassas roller (KVKK Sorumlusu, IR ekibi).
- **Webinar:** Aylık güncel konu (yeni Kurul kararı, sektör vakası).
- **Mikro öğrenme:** 2-5 dk video / infografik / Slack ipucu.
- **Pano / poster:** Ofis fiziksel iletişim.
- **Newsletter:** Aylık güvenlik bülteni.
- **Capture the Flag (CTF):** Yıllık yarışmalı oyunlaştırma.
- **Tabletop:** Üst yönetim için kriz senaryosu.

## 6. Phishing Simülasyon Programı

### 6.1. Çerçeve

- En az **çeyreklik** kampanya (4 / yıl).
- Senaryo zorluk dağılımı (kolay → orta → zor).
- Tıklayan kullanıcı: anında "öğrenme sayfası" (utandırma değil — eğitim).
- Tekrarlı tıklayan kullanıcı: zorunlu ek eğitim, yöneticiyle görüşme.
- "Şüpheli olarak bildirenler" tanınır (gamification, leaderboard).
- KPI: tıklama oranı, raporlama oranı, tekrar oranı.

### 6.2. Senaryo Türleri

- Sahte İK e-postası (zam mektubu, performans değerlendirme).
- Sahte BT e-postası (parola sıfırla, MFA reset).
- Kurumsal araç bildirimi (Microsoft 365, Slack, GitHub).
- Üst yönetim tarafından gönderilmiş gibi (BEC).
- QR code phishing (poster üzerinden).
- Vishing simülasyonu (yıllık 1-2 kez, ekip seçimli).
- AI-clone ses (yıllık 1 kez).

### 6.3. Mahremiyet ve Hukuki Çerçeve

- Simülasyon **çalışan aydınlatma metnine** açıkça yazılmıştır.
- Bireysel başarı / başarısızlık verisi yöneticiye değil, sadece İK + CISO ofisine açıktır.
- Tekrarlı kullanıcı için disiplin **derhal** uygulanmaz; eğitim önerilir.
- Sonuçlar agregate raporlanır (departman ortalama, trend), bireysel "shame" yok.

## 7. Yeni Başlayan Onboarding

| Gün | Aktivite |
|-----|----------|
| -1 | İK pakete erişim aktivasyonu, oryantasyon takvimi |
| 1 | Oryantasyon (KVKK + bilgi güvenliği temelleri sunum) |
| 1 | Gizlilik taahhütnamesi imzası |
| 1-3 | LMS modül 1-2 (KVKK + Bilgi Güvenliği) |
| 4-5 | LMS modül 3-5 (Phishing, MFA, BYOD) |
| 5 | Rol bazlı ek modüller (departmana göre) |
| 7 | Bilgi testi (≥%80 başarı şartı) |
| 14 | İlk phishing simülasyonu |
| 30 | Bağlı yöneticiyle KVKK pratik konuşma |

Tamamlanma kayıtları LMS'de 5 yıl saklanır. Tamamlamayan çalışan üretime erişemez (BT erişim aktivasyonu eğitim tamamlanmasına bağlı).

## 8. Yıllık Tazeleme

- Tüm çalışanlar yılda en az **bir kez** zorunlu tazeleme.
- 30 dk yoğunlaştırılmış (yenilikler, yeni Kurul kararları, sektörel vakalar, yeni teknoloji).
- Bilgi testi (≥%80).
- Yıl içinde **olmayan** çalışan (uzun izin) dönüşte 30 gün ek süre.
- Tamamlamayan çalışan için yöneticiye uyarı + İK takip + ileri uyumsuzlukta disiplin.

## 9. Tetikleyici (Olay-Sonrası) Eğitim

- Şirket içi ihlal/ramak kala olayı sonrası, etkilenen ekip için mikro modül (anonimleştirilmiş vaka).
- KVKK Kurulu kararı yayımlanması — ilgili rolün eğitim modülü güncellenir.
- Yeni teknolojinin benimsenmesi (örn. yeni AI aracı) → kullanım öncesi modül zorunlu.
- Mevzuat değişikliği — 90 gün içinde tüm çalışanlara duyuru + 6 ay içinde tazeleme.

## 10. Etkinlik Ölçümü

### 10.1. Düzeyler (Kirkpatrick'in 4 Seviyesi)

1. **Tepki:** Memnuniyet anketi.
2. **Öğrenme:** Pre-test / post-test bilgi farkı.
3. **Davranış:** Phishing simülasyon raporlama oranı, gerçek olayda raporlama hızı.
4. **Sonuç:** İhlal sayısı / şiddeti, KPI'lar.

### 10.2. KPI'lar

- Tamamlanma oranı (yıllık tazeleme): hedef %100.
- Sınav başarı oranı (≥%80): hedef %95+.
- Phishing tıklama oranı: hedef ≤%10 (yıl sonu); start baseline ölç.
- Phishing rapor oranı (zararsız simülasyon): hedef ≥%50.
- Tekrarlı tıklayan kullanıcı sayısı: hedef azalan trend.
- Olaylarda "ilk tespit kaynağı = kullanıcı raporu" oranı: hedef artan.
- Çalışan memnuniyet (post-eğitim NPS): trend takibi.

## 11. Bütçe ve Kaynaklar

- LMS lisansı (kullanıcı başına yıllık).
- İçerik geliştirme (iç + dış).
- Phishing simülasyon platformu (KnowBe4, Proofpoint, Hoxhunt, Cofense).
- Sertifika eğitim bütçesi (KVKK Sorumlusu, CISO, IR ekibi için yıllık).
- İletişim kampanyası (poster, video, etkinlik).
- Yıllık güvenlik haftası / KVKK gününü kutlama (Türkiye'de "Bilgi Güvenliği Farkındalık Ayı" — Ekim).

## 12. Tedarikçi / Danışman / Stajyer Eğitimi

- Onboarding: kısa (15 dk) bilgi güvenliği + KVKK temelleri.
- Gizlilik taahhütnamesi imzası (bkz. [gizlilik-taahhutnamesi.md](gizlilik-taahhutnamesi.md)).
- Erişim verilen sisteme rol bazlı eğitim.
- Sözleşme süresi 1 yılı aşıyorsa yıllık tazeleme.
- Tedarikçi şirket kendi eğitim politikasıyla yetinemez — kurumumuzun standart modülleri zorunlu.

## 13. Uyumsuzluk Yönetimi

| Durum | Aksiyon |
|-------|---------|
| Yeni başlayan eğitim tamamlamadı | BT erişim aktivasyonu durdurulur, İK + yönetici uyarısı |
| Yıllık tazeleme süresi geçti | Yönetici uyarısı + 14 gün ek süre + sonraki ihlalde disiplin |
| Phishing tıklama tekrarlı | Mikro modül zorunlu + yönetici görüşmesi + 3 ihlalde disiplin |
| Bilgi testi başarısız (3 deneme) | Yüz yüze eğitim + yeniden test |

## 14. KVKK Sorumlusu / IR Ekibi Sertifikalı Eğitim

- Yıllık bütçeli sertifika programı:
  - **CISSP, CISM, CIPP/E (veya yerel benzerleri)**.
  - **ISO 27001 LA / LI**.
  - **ISO 27701 LI**.
  - KVKK Kurum eğitim/sempozyum.
  - Sektör konferansları (CyberWeek TR, ISACA, OWASP TR).
- Bilgi paylaşım ortamı: kurum içi "communities of practice".

## 15. Loglama ve Kanıt

- LMS: tamamlanma, sınav skoru, deneme sayısı.
- Phishing platformu: kampanya, sonuç, tıklayan/raporlayan listesi.
- Eğitim katılım imza listesi (sınıf eğitimleri için).
- Bilgi güvenliği günü etkinlik kaydı.

Saklama: aktif istihdam süresince + 5 yıl ayrılış sonrası.

## 16. Kontrol Listesi

- [ ] Yıllık eğitim takvimi yayınlandı, KVKK Komitesi onaylı mı?
- [ ] Genel + rol bazlı modüller güncel, ≤12 ay revizyon tarihli mi?
- [ ] LMS tüm çalışanlara açık, tamamlanma raporu çeyreklik mi?
- [ ] Tamamlanma oranı %100 hedefe yakın mı?
- [ ] Bilgi testi başarı eşiği ≥%80 mi?
- [ ] Yeni başlayan eğitim erişim aktivasyon koşulu mu?
- [ ] Phishing simülasyon çeyreklik, KPI ölçülüyor mu?
- [ ] Sosyal mühendislik (vishing/AI-clone) simülasyonu yıllık var mı?
- [ ] Tetikleyici olay-sonrası eğitim mekanizması işliyor mu?
- [ ] Yöneticilere özel modül var mı (mover/leaver, raporlama)?
- [ ] Tedarikçi/danışman/stajyer eğitim zorunlu mu?
- [ ] KVKK Sorumlusu / IR ekibi sertifikalı eğitim bütçesi yıllık mı?
- [ ] Bireysel veriler agregate raporlanıyor, çalışan mahremiyeti gözetiliyor mu?
- [ ] Aydınlatma metni eğitim/simülasyonu listeliyor mu?
- [ ] Disiplin sınıflandırması ve eskalasyonu yazılı mı?
- [ ] Yıllık etkinlik (KVKK günü, güvenlik haftası) kutlanıyor mu?

## 17. Yıllık Yönetim Raporu Şablonu

KVKK Komitesi'ne yıllık şu tablo:

- Toplam çalışan / eğitime tabi olan / tamamlayan.
- Sınav başarı oranı.
- Phishing simülasyon trendleri (4 çeyreklik).
- Olaylarda kullanıcı katkısı (ilk tespit kaynağı).
- Tetikleyici eğitim sayısı.
- Disiplin işlemi sayısı.
- Bütçe kullanımı.
- Sonraki yıl planı (yeni modül, yeni hedef KPI).
