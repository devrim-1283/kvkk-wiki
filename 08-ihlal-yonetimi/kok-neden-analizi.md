---
Doküman: Kök Neden Analizi (Root Cause Analysis) ve CAPA
Bölüm: 08-ihlal-yonetimi
Sahip: KVKK Sorumlusu + Bilgi Güvenliği Müdürü
Onaylayan: KVKK Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + her ihlal sonrası
İlgili Mevzuat: 6698 sayılı KVKK m.12, KVKK Veri Güvenliği Rehberi (2018) §5, ISO/IEC 27035-2:2023, ISO 9001:2015 §10.2, NIST SP 800-61 Rev.2 §3.4
---

# Kök Neden Analizi (RCA) ve Düzeltici/Önleyici Aksiyon (CAPA)

## 1. Amaç

Her kişisel veri ihlali sonrası **gerçek kök nedenin** bulunup giderilmesi, semptomatik çözümle yetinilmeyip aynı tipte ihlalin tekrarının önlenmesi. RCA, KVKK Veri Güvenliği Rehberi'nin "düzeltici tedbirler" yükümlülüğünün uygulamadaki karşılığıdır.

## 2. RCA Yapılması Zorunlu Durumlar

| Tetikleyici | Süre |
|-------------|------|
| Kurul'a bildirilen her ihlal | T+30 gün içinde nihai RCA |
| Eşik altı kalan ama bildirilmeyen olay | T+15 gün özet RCA |
| Tekrarlayan olay (aynı kategori 2. kez) | T+10 gün acil RCA |
| Tatbikatta kritik kaçış | T+15 gün tatbikat RCA |
| İç denetim bulgu kapsamı | Denetim raporu süresi |

## 3. RCA Metodolojileri

Şirketimiz üç farklı metodolojiyi olay tipine göre seçer:

### 3.1. 5 Whys (Hızlı, doğrusal)

Basit nedensellik zincirleri için.

**Örnek:**
> İhlal: Müşteri verileri dışa aktarıldı.
> Why 1: Çalışan toplu export yetkisine sahipti. → Çünkü her CRM kullanıcısı default'ta tam yetkili.
> Why 2: Default tam yetki neden? → Erişim politikası yıllarca güncellenmedi.
> Why 3: Neden güncellenmedi? → Politika sahibi belirsizdi.
> Why 4: Sahibi neden belirsizdi? → KVKK sonrası rol haritası yapılmadı.
> Why 5: Neden yapılmadı? → KVKK Komitesi gündemi öncelikli olarak aydınlatma metnine odaklandı, erişim sınıfı geri planda kaldı.

**Çıktı:** Kök neden = "KVKK uyum yol haritasında erişim hakları yetkilendirilmedi."

### 3.2. Fishbone (Ishikawa) — Kategoriye Göre Çoklu Neden

Kategoriler (5M+E): Man, Machine, Method, Material, Measurement, Environment.

```
                 Man           Machine
                  │              │
                  └──────┬───────┘
                         │
İhlal ←──────────────────┤
                         │
                  ┌──────┼───────┐
                  │      │       │
                Method  Measure  Environment
```

**Kullanım:** Karmaşık ihlaller (ransomware, BEC) — birden çok katmanın katkısı vardır.

**Şablon:**

| Kategori | Olası Neden 1 | Olası Neden 2 | Olası Neden 3 |
|----------|---------------|---------------|---------------|
| Man (İnsan) | Eğitim eksiği | Parola hijyeni | Sosyal mühendislik |
| Machine (Sistem) | Yama eksiği | EDR yok | Eski OS |
| Method (Süreç) | Erişim politikası | İzleme yok | Tatbikat eksik |
| Material (Yazılım/donanım) | Lisanssız | Yetersiz log | Backup hatası |
| Measurement (Ölçüm) | KPI yok | Alarm kaçış | Audit eksik |
| Environment (Ortam) | Fiziksel güvenlik | Tedarikçi | Düzenleyici baskı |

### 3.3. Apollo RCA (Cause-and-Effect Charting)

Ciddi/karmaşık ihlaller için. Her ihlal için en az iki nedensel ağaç (action cause + condition cause) çizilir.

```
                   [İhlal]
                      │
        ┌─────────────┴─────────────┐
        │                           │
   [Eylem nedeni]              [Koşul nedeni]
   (saldırgan ne yaptı)        (neye izin verildi)
        │                           │
   ┌────┴────┐                ┌─────┴─────┐
[alt eylem] [araç]         [açık]      [yetersizlik]
```

Her düğüm için **kanıt** (log, video, ifade) zorunludur. Kanıtsız hipotez budanır.

**Avantaj:** Tek kök neden yanılgısından kaçınır; **gerçek nedensel ağ** ortaya çıkar.

## 4. RCA Katmanları (Şirketimiz Standart Yaklaşımı)

Her RCA en az **dört katmanda** yürütülür:

### 4.1. Teknik Katman
- Hangi açık? (CVE, yapılandırma, mimari)
- Hangi sistem? (Versiyon, yama durumu)
- Hangi izleme atlandı? (SIEM, EDR, DLP gap)
- Hangi tedbir eksikti? (Şifreleme, segmentasyon, MFA)

### 4.2. Süreç Katmanı
- Hangi prosedür eksik / güncel değildi?
- Onay zinciri çalıştı mı?
- SLA'lar gerçekçi miydi?
- Tatbikat bu senaryoyu kapsıyor muydu?

### 4.3. İnsan Katmanı
- Kim hangi kararı verdi / vermedi?
- Eğitim seviyesi yeterli miydi?
- İş yükü, yorgunluk faktörü var mıydı?
- Etik / kasıtlı ihmal var mıydı?

> **Önemli:** İnsan katmanı **bireysel suçlama** değildir. "Just culture" prensibi: dürüst hata cezasız, kasıtlı ihlal disiplinli.

### 4.4. Yönetişim Katmanı
- Politika güncel miydi?
- Bütçe yeterli miydi?
- Yönetim desteği var mıydı?
- Risk iştahı doğru tanımlanmış mıydı?

## 5. RCA Süreci (Adım Adım)

```
1. RCA tetiklendi (olay kapanış)
        ↓
2. RCA Lideri atandı (CISO veya KVKK Sorumlusu)
        ↓
3. RCA ekibi oluşturuldu (5-7 kişi, çapraz fonksiyon)
        ↓
4. Kanıt toplama (log, görüşme, doküman)
        ↓
5. Zaman çizgisi rekonstrüksiyon
        ↓
6. Metodoloji seçimi (5 Whys / Fishbone / Apollo)
        ↓
7. Hipotezler + kanıt eşleştirme
        ↓
8. Kök neden onayı (RCA Lideri + KVKK Sorumlusu)
        ↓
9. CAPA tasarımı
        ↓
10. KVKK Komitesi onayı
        ↓
11. CAPA uygulama
        ↓
12. Etkinlik doğrulama (8 hafta sonra)
        ↓
13. Kapanış
```

## 6. RCA Ekibi

| Rol | Sorumluluk |
|-----|-----------|
| RCA Lideri | Süreç yönetimi, raporlama |
| Olay Komutanı | Olay kronolojisi, müdahale kararları |
| Teknik Lider | Forensik delil yorumu |
| KVKK Sorumlusu | Düzenleyici uyum açısı |
| İnsan Faktörleri Uzmanı | İK + Eğitim — "just culture" çerçevesi |
| Süreç Sahibi | Etkilenen iş süreci uzmanı |
| Bağımsız Hakem | Diğer fonksiyondan kıdemli (önyargı kontrolü) |

## 7. Kanıt Toplama Disiplini

- **Saatlik log önceliği:** SIEM, EDR, DLP, ağ akışı, kimlik sistemi.
- **Görüşme protokolü:** Yapılandırılmış, kayıt altında, çift görüşmeci, hukuk gözetiminde.
- **Doküman:** Politika versiyonları, eğitim kayıtları, değişiklik biletleri.
- **Saklama:** Tüm RCA dosyaları **5 yıl** sigortalı arşiv.
- **Anonimleştirme:** Yayım iç dağıtımda kişiselleştirilmiş, dış paylaşımda anonim.

## 8. CAPA (Corrective and Preventive Actions)

### 8.1. Düzeltici Aksiyon (Corrective)

- Olayın tekrarını önler.
- Belirli, ölçülebilir, hedef tarihli.
- Doğrudan kök nedeni hedefler.

### 8.2. Önleyici Aksiyon (Preventive)

- Benzer ama henüz yaşanmamış olayları engeller.
- Diğer sistem/süreçlerde de uygulanır.
- "Bu sefer şanslıydık" durumlarına karşı.

### 8.3. CAPA Tasarımı Standardı

Her CAPA aksiyonu **SMART** olmalıdır:
- **S**pecific — net tanım.
- **M**easurable — ölçülebilir KPI.
- **A**chievable — gerçekçi.
- **R**elevant — kök nedene bağlı.
- **T**ime-bound — son tarih.

### 8.4. CAPA Şablonu

| Alan | İçerik |
|------|--------|
| CAPA No | CAPA-YYYY-NNNN |
| Bağlı olay | OLAY-YYYY-NNNN |
| Tip | Düzeltici / Önleyici |
| Kök neden referansı | RCA bölümü |
| Tanım | (SMART) |
| Sahip (Birim) | |
| Sahip (Kişi) | |
| Hedef tarih | |
| KPI | |
| Onay | KVKK Komitesi |
| Durum | Açık / Devam / Tamamlandı / İptal |
| Etkinlik doğrulama tarihi | T+8 hafta sonra |
| Doğrulama yöntemi | Test / Audit / Tatbikat |
| Doğrulama sonucu | Geçti / Kaldı |

### 8.5. Tipik CAPA Örnekleri

| Kök neden | Düzeltici | Önleyici |
|-----------|-----------|----------|
| MFA eksiği | Tüm uzaktan erişimde MFA zorunlu | Yeni hesap onboarding'inde MFA varsayılan |
| Yama eksiği | Etkilenen sistem yamasız + tüm filo CVE tarama | Aylık otomatik yama döngüsü, SLA tanımı |
| Erişim ihlali | Kullanıcı yetki kaldırıldı | Çeyreklik least-privilege review |
| Eğitim eksiği | Hedefli yenileme eğitimi (etkilenen birim) | Yıllık genel + 6 aylık modül eğitim |
| 3. taraf | Sözleşme klozu sıkılaştırıldı | Tüm tedarikçi sözleşme yenilenmesi |
| Yedek hatası | Immutable backup kuruldu | Aylık restore tatbikatı |
| DLP gap | DLP kural seti güncellendi | Çeyreklik DLP false-positive review |
| Politika güncel değil | Politika güncellendi | Yıllık politika döngüsü |

## 9. CAPA Takibi

### 9.1. Sistem
- JIRA / Asana / ServiceNow üzerinde ayrı CAPA projesi.
- Her aksiyon biletlenmiş.
- Sahibi, tarihi, durumu, kanıt linki.
- Geciken aksiyon haftalık otomatik eskalasyon.

### 9.2. Yönetişim
- KVKK Komitesi aylık CAPA gözden geçirme.
- Geciken aksiyonlar YK ekitilerine.
- Yıllık denetimde rastgele CAPA örneklemi.

### 9.3. Etkinlik Doğrulama

Aksiyon **kapatıldı** demek yetersizdir. **Etki**si doğrulanmalıdır:

| Aksiyon | Doğrulama yöntemi |
|---------|-------------------|
| MFA zorunlu | AD log — MFA olmadan giriş 0 |
| Yama döngüsü | Patch compliance raporu %95+ |
| Eğitim | Quiz başarı oranı %85+ |
| Sözleşme klozu | Tüm yeni/yenilenen sözleşme kontrolü |
| Backup immutable | Restore tatbikatı başarılı |
| DLP kuralı | False positive < %5 + true positive %90+ |

8 hafta içinde etkinlik doğrulanamayan aksiyon **yeniden açılır**.

## 10. Tekrar Etmeyi Önleme Metrikleri

| Metrik | Hedef | Kaynak |
|--------|-------|--------|
| Tekrarlayan ihlal oranı | %0 | RCA arşivi |
| CAPA zamanında kapanma | ≥ %90 | CAPA sistem |
| CAPA etkinlik doğrulama | %100 | CAPA sistem |
| RCA kalite skoru (denetçi) | ≥ 8/10 | İç denetim |
| Kök neden bulma (ilk 30 gün) | ≥ %95 | RCA arşivi |

## 11. RCA Raporu Şablonu

```markdown
# RCA Raporu - OLAY-YYYY-NNNN

## 1. Özet
- Olay tarihi:
- Olay tipi:
- Etkilenen veri:
- Bildirim durumu:

## 2. Olay Zaman Çizgisi (Detaylı)
| Zaman | Olay | Kanıt |
|-------|------|-------|
| | | |

## 3. Kanıtlar
3.1. Teknik:
3.2. Doküman:
3.3. Görüşme:

## 4. Metodoloji
[5 Whys / Fishbone / Apollo seçildi — gerekçe]

## 5. Nedensel Analiz
5.1. Teknik katman:
5.2. Süreç katmanı:
5.3. İnsan katmanı:
5.4. Yönetişim katmanı:

## 6. Kök Neden(ler)
[Net cümle, kanıta dayalı]

## 7. CAPA Listesi
[Bkz. tablo]

## 8. Risk Değerlendirmesi
- Tekrar olasılığı:
- Etki büyüklüğü:
- Kalan risk (CAPA sonrası):

## 9. Politika / Eğitim Güncellemesi Önerileri

## 10. RCA Ekibi
- Lider:
- Üyeler:
- Bağımsız hakem:

## 11. Onay
- KVKK Sorumlusu:
- CISO:
- Hukuk:
- KVKK Komitesi:
- Tarih:
```

## 12. RCA Yapma Olgunluk

| Seviye | Tanım |
|--------|-------|
| 1 — Reaktif | Sadece büyük olaylarda |
| 2 — Sistematik | Tüm bildirilen ihlallere |
| 3 — Genişletilmiş | Eşik altı olaylara da |
| 4 — Tahminsel | Yakın-kaçışlara (near miss) |
| 5 — Öğrenen | Kuruma içselleşmiş, eğitim verisi |

Şirket hedef seviye: **4** (2027 sonu).

## 13. Bağlantılı Bölümler

- `06-idari-tedbirler/egitim.md` — RCA çıktısı eğitim güncellemesi.
- `11-denetim-ve-uyum/aksiyon-takibi.md` — CAPA listesi entegrasyonu.
- `08-ihlal-yonetimi/soak-test-tatbikat.md` — Tatbikat senaryosuna işleme.

## 14. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi |
