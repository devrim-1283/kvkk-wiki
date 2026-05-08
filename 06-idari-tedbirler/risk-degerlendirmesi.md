---
Doküman: Kişisel Veri Etki Değerlendirmesi (DPIA / PIA) ve Risk Yönetimi Standardı
Bölüm: 06-idari-tedbirler
Sahip: KVKK Sorumlusu + Risk Yönetimi
Onaylayan: KVKK Komitesi + Üst Yönetim
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (yeni proje, yeni teknoloji, mevzuat değişikliği)
İlgili Mevzuat: 6698 sayılı KVKK m.4 (genel ilkeler — ölçülülük), m.6 (özel nitelikli), m.12 (veri güvenliği); KVKK Kurum Rehberleri; GDPR Art. 35 (DPIA — kıyaslamalı çerçeve)
İlgili Standart: ISO/IEC 29134:2017 (Privacy Impact Assessment); ISO/IEC 27005:2022 (Information Security Risk Management); ISO 31000:2018 (Risk Management); NIST Privacy Framework; NIST CSF 2.0 GV.RM, ID.RA; ENISA "Recommendations on Shaping Technology Risks"; CNIL PIA Methodology
---

# Kişisel Veri Etki Değerlendirmesi (DPIA / PIA) ve Risk Değerlendirmesi

## 1. Amaç

Yüksek riskli kişisel veri işleme faaliyetlerinin **başlamadan önce** sistematik biçimde değerlendirilmesini, ölçülülük testinden geçirilmesini, risklerin tanımlanıp tedbirlerle azaltılmasını ve KVKK Komitesi'nin onayına sunulmasını sağlar. KVKK m.4 ölçülülük ilkesinin operasyonel ayağıdır; KVKK Kurulu'nun **risk-bazlı uyum** yaklaşımının doğal sonucudur.

> KVKK metni DPIA'yı GDPR Art. 35 gibi açıkça düzenlememekle birlikte, KVKK m.4 genel ilkeleri ve m.12 yükümlülüğü, **risk değerlendirmesinin yapılmadığı yüksek riskli işlemeleri** Kurul nezdinde defacto uyumsuzluk haline getirir. Bu yüzden DPIA, **iyi yönetişim ve uyum kanıtının** ayrılmaz parçasıdır.

## 2. Tanımlar

| Terim | Tanım |
|-------|-------|
| **DPIA / KVED** | Data Protection Impact Assessment — Kişisel Veri Etki Değerlendirmesi. |
| **PIA** | Privacy Impact Assessment (geniş gizlilik değerlendirmesi). |
| **Risk** | Belirli bir tehdidin meydana gelme olasılığı ile ortaya çıkacak etkinin birleşimi. |
| **Artık Risk** | Tedbir alındıktan sonra kalan risk. |
| **Risk İştahı** | Yönetimin kabul etmeye hazır olduğu risk düzeyi. |
| **Tehdit** | Zarara yol açabilecek olay. |
| **Zafiyet** | Tehdidin istismar edebileceği zayıflık. |
| **Tedbir** | Riski azaltmaya yönelik kontrol. |

## 3. DPIA Ne Zaman Zorunlu?

DPIA, aşağıdaki **tetikleyicilerden** biri varsa zorunludur:

### 3.1. Yüksek Risk Senaryoları (KVKK Kurum Rehberleri ve GDPR WP29 önerileri)

1. **Sistemli ve büyük ölçekli profilleme / değerlendirme** — kredi puanlama, sigorta risk skoru, çalışan performans algoritması.
2. **Otomatik karar alma** — KVKK m.5/2(f) "ilgili kişinin temel hak ve özgürlüklerine zarar vermemek kaydıyla" — fakat hak ve özgürlüklere etkisi olabiliyorsa DPIA.
3. **Özel nitelikli veri işleme (KVKK m.6)** — sağlık, biyometrik, genetik, ceza mahkumiyeti, sendika, din vb.
4. **Çocuk verisi** — 18 yaş altı.
5. **Çalışan izleme (sürekli, geniş kapsamlı)** — DLP geniş, kamera, GPS, klavye/ekran yakalama.
6. **Geniş ölçekli kamuya açık alanın izlenmesi** — CCTV ağı, kamuya yüz tanıma.
7. **Yeni teknoloji benimseme** — AI/ML, biyometri, IoT, blockchain, AR/VR.
8. **Birden fazla veri kümesinin birleştirilmesi** (data combination) — sektör pazarı, profil zenginleştirme.
9. **Bir kişiye karşı sözleşme yapma / hizmet sağlama kararının otomatik verilmesi.**
10. **Yurt dışı aktarım** — özellikle yeterli koruma kararı bulunmayan ülkelere.
11. **Sağlık, finans, eğitim alanı** — yüksek hassasiyetli sektörel.
12. **Müşterilerin / çalışanların izleme amacıyla işlenmesi.**

### 3.2. Tetikleyici Tablosu

| Tetik | DPIA |
|-------|------|
| Yeni proje, kişisel veri içeriyor | Risk taraması; yüksek riskli ise DPIA |
| Mevcut süreç yeni teknoloji | DPIA |
| Yeni tedarikçi (Sınıf A) | DPIA bileşenli due diligence |
| Yurt dışı aktarım yeni ülke | DPIA |
| Çalışan izleme aracı yeni | DPIA |
| AI/ML model üretime alma | DPIA |
| Mevzuat değişikliği etki | Mevcut DPIA review |
| Önemli ihlal sonrası | Etkilenen sürecin DPIA review |

## 4. DPIA Süreci

```
1. Tetik (Yeni proje / değişiklik)
2. Risk Taraması (Threshold Assessment) — DPIA gerekli mi?
3. Ekip Oluşturma (süreç sahibi + KVKK Sorumlusu + CISO + Hukuk + BT)
4. Veri Akış Haritalama
5. Gereklilik ve Ölçülülük Testi
6. Tehdit & Risk Tanımlama
7. Tedbir Tasarımı
8. Artık Risk Değerlendirme
9. KVKK Sorumlusu Görüşü
10. KVKK Komitesi Karar (Onay / İyileştirme / Ret)
11. Uygulama ve İzleme
12. Periyodik Review
```

## 5. DPIA Şablonu (Bölümler)

### 5.1. Yönetici Özeti

- Proje / süreç adı.
- Süreç sahibi.
- Hazırlayanlar.
- Hazırlama tarihi.
- Sonuç (onay durumu, koşullar, artık risk seviyesi).

### 5.2. Süreç Tanımı

- Süreç amacı (iş hedefi).
- Faydalanıcılar (ilgili kişi grupları).
- Hizmetin / sürecin akışı (üst düzey).
- İlgili sistemler ve teknolojiler.
- Veri sorumlusu / veri işleyen rolleri.

### 5.3. Veri Akışı

- Veri kategorileri (genel + özel nitelikli).
- Veri kaynağı (ilgili kişiden mi, üçüncü taraftan mı?).
- İşleme adımları (toplama → kullanım → saklama → aktarım → imha).
- Veri akış diyagramı (görsel).
- Aktarım hedefleri (yurt içi / yurt dışı).
- Saklama süreleri.
- İmha yöntemleri.

### 5.4. Hukuki Dayanak

- KVKK m.5 (genel) / m.6 (özel nitelikli) hangi şart?
- Açık rıza alıyorsa: rızanın özgür / aydınlatılmış / belirli olduğunun gösterilmesi.
- Sözleşmenin kurulması, yasal yükümlülük, kamu yararı vb. dayanaklar yazılı.
- Yurt dışı aktarım hukuki mekanizması (m.9).

### 5.5. Gereklilik ve Ölçülülük Testi

KVKK m.4 ölçülülük testi:

- **Amaca uygun mu?** Veri toplanan amaç için gerekli mi?
- **Sınırlı mı?** Daha az veriyle aynı amaca ulaşılabilir mi?
- **Ölçülü mü?** Veri toplama yöntemi, kapsamı orantılı mı?
- **Belirli mi?** Amaç açık ve anlaşılır mı?
- **Saklama süresi makul mu?**
- **Alternatifleri değerlendirildi mi?** (Anonim, sentetik, daha az hassas).

### 5.6. İlgili Kişi Hakları

- Aydınlatma metni hazırlandı mı?
- Açık rıza süreci nasıl?
- Erişim, düzeltme, silme, itiraz, taşınabilirlik, otomatik karara itiraz hakları nasıl uygulanır?
- Başvuru kanalı kayıtlı mı?

### 5.7. Tehdit ve Risk Tanımlama

LINDDUN (gizlilik) + STRIDE (güvenlik) çerçevelerinde:

| # | Tehdit | Etki | Olasılık | Risk Skoru | Tedbir | Artık Risk |
|---|--------|------|----------|------------|--------|------------|
| R1 | Yetkisiz erişim DB'ye | Çok Yüksek | Orta | **Yüksek** | MFA + RLS + audit | Düşük |
| R2 | Veri sorumlusu talimat dışı kullanım (insider) | Yüksek | Düşük | Orta | DLP + UEBA + eğitim | Düşük |
| R3 | Yurt dışı aktarımda yetkisiz erişim | Çok Yüksek | Düşük | Orta | Standart sözleşme + şifreleme + denetim | Düşük |
| R4 | Algoritma yanlış sınıflandırma | Yüksek | Orta | **Yüksek** | İnsan denetimi + DPIA review + itiraz hakkı | Orta |
| ... | ... | ... | ... | ... | ... | ... |

### 5.8. İlgili Kişi Üzerindeki Olası Etki

- Maddi zarar (kayıp, dolandırıcılık).
- Manevi zarar (utanç, ayrımcılık, itibar kaybı).
- Hizmet erişiminin engellenmesi (otomatik karar).
- Mahremiyet ihlali.
- Profil oluşturma sonucu kategori / damga.
- Çocuk için ek hassasiyet.
- Özel nitelikli veri için ek hassasiyet.

### 5.9. Tedbirler

| Kategori | Tedbir |
|----------|--------|
| Teknik | Şifreleme, MFA, RLS, audit log, DLP, anahtar yönetimi |
| İdari | Eğitim, taahhütname, politika, denetim, sözleşme |
| Hukuki | Aydınlatma, rıza, sözleşme şartları, mevzuat takibi |
| Süreçsel | Kontrol noktaları, 4-eyes, periyodik review |
| Veri Mimarisi | Minimizasyon, anonim/pseudonym, veri kalitesi, saklama otomatik |

### 5.10. Artık Risk ve Onay

- Tedbirler sonrası kalan risk skoru.
- Risk iştahıyla karşılaştırma — kabul edilebilir mi?
- Kabul edilemez ise: ek tedbir / proje yeniden tasarım / iptal.
- KVKK Sorumlusu görüş yazısı (ekte).
- KVKK Komitesi karar tutanağı (ekte).

### 5.11. İzleme ve Review

- Hangi sıklıkla review (yıllık, çeyreklik).
- Hangi olaylar review'u tetikler.
- KPI'lar.

## 6. Risk Skor Matrisi

### 6.1. Etki (Impact)

| Seviye | Tanım | Örnek |
|--------|-------|-------|
| 5 — Çok Yüksek | İlgili kişiye geri dönüşü olmayan zarar; geniş ölçekli ifşa | Sağlık verisi kamuya sızdı |
| 4 — Yüksek | Önemli zarar; düzeltme zor | TC kimlik + kart 100K kayıt sızdı |
| 3 — Orta | Düzeltilebilir zarar; geçici hizmet kesintisi | Sınırlı kişisel veri (ad-soyad) sızdı |
| 2 — Düşük | Asgari zarar; hızlı düzeltme | Loglama eksiği fark edildi |
| 1 — Çok Düşük | İhmal edilebilir | Politika güncelleme gecikti |

### 6.2. Olasılık (Likelihood)

| Seviye | Tanım |
|--------|-------|
| 5 — Çok Yüksek | Aktif olarak gerçekleşen veya çok yakın |
| 4 — Yüksek | Yıl içinde gerçekleşmesi olası |
| 3 — Orta | 1-3 yıl içinde olası |
| 2 — Düşük | 3-5 yıl içinde olası |
| 1 — Çok Düşük | Pratik olarak olası değil |

### 6.3. Risk Skoru

```
Risk = Etki × Olasılık
```

| Skor | Sınıf | Aksiyon |
|------|-------|---------|
| 20-25 | Kritik | DERHAL — proje durdurulur, üst yönetim kararı |
| 12-19 | Yüksek | Tedbir mecburi — 30 gün içinde |
| 6-11 | Orta | Tedbir önerilir — 90 gün içinde |
| 1-5 | Düşük | İzlenir — yıllık review |

### 6.4. Risk İştahı

Kurum genel risk iştahı: KVKK ihlal yaratan riski **Düşük seviyede** tolere eder. Yüksek-Kritik risk açıkça gerekçeli + üst yönetim onayı + telafi edici kontroller olmadan kabul edilemez.

## 7. Yönetimsel Roller

| Rol | Sorumluluk |
|-----|-------------|
| Süreç Sahibi (İş Birimi) | DPIA hazırlık talebi, içerik bilgisi sağlama, tedbir uygulama |
| KVKK Sorumlusu | DPIA metodoloji, görüş yazısı, takip |
| CISO ofisi | Teknik tedbir tasarım, tehdit modelleme |
| Hukuk | Hukuki dayanak, sözleşme |
| BT / Mimari | Veri akışı, sistem entegrasyon |
| Risk Yönetimi | Skor, tutarlılık, kurumsal risk entegrasyonu |
| KVKK Komitesi | Onay / ret / koşullu onay kararı |
| İç Denetim | DPIA tatbiki örnekleme denetimi |

## 8. Risk Yönetimi Bağlantıları

DPIA, kurumun **bütüncül risk yönetimi** çerçevesine entegredir:

```
Stratejik Risk (Üst Yönetim)
   ↓
Operasyonel Risk (Risk Yönetimi)
   ├── Bilgi Güvenliği Risk Kayıt (CISO)
   ├── Mahremiyet/KVKK Risk Kayıt (KVKK Sorumlusu) ← DPIA çıktıları buraya
   ├── BT Risk Kayıt
   ├── Tedarikçi Risk Kayıt
   └── İş Sürekliliği Risk
```

Risk kayıtları çeyreklik gözden geçirilir. KVKK riskleri, kurumsal risk kayıtlarına eklenir.

## 9. Hızlı Tarama (Screening / Threshold) Şablonu

DPIA başlatma kararı için kısa form (10 soru, 5 dk):

```
1. Süreç kişisel veri içeriyor mu? (E/H)
2. Özel nitelikli veri (m.6) var mı? (E/H)
3. Çocuk verisi var mı? (E/H)
4. İlgili kişi sayısı 10K+ mi? (E/H)
5. Yeni teknoloji (AI, biyometri, IoT) kullanılıyor mu? (E/H)
6. Otomatik karar / profilleme var mı? (E/H)
7. Çalışan / kullanıcı izleme yapılıyor mu? (E/H)
8. Yurt dışı aktarım var mı? (E/H)
9. Birden fazla veri kümesi birleştiriliyor mu? (E/H)
10. Halka açık alan / kamuoyu izleme var mı? (E/H)

EVET sayısı:
   0-1: DPIA gerekmez (basit risk taraması yeterli)
   2-3: Hafif DPIA (kısa form)
   4+: Tam DPIA
```

## 10. Tipik DPIA Senaryoları (Şablon Başlıkları)

1. **Yeni e-ticaret platformu** — müşteri kaydı, ödeme, profil oluşturma.
2. **Çalışan performans yönetim sistemi** — KPI takibi, otomatik öneri.
3. **AI tabanlı müşteri destek chatbot'u** — sohbet kayıtları, kişisel veri ifşası.
4. **CCTV ağı yenileme** — yeni kamera lokasyonları, yüz tanıma feature'ı.
5. **İK SaaS göçü** — eski sisteme/yeni sisteme geçiş, yurt dışı aktarım.
6. **Yeni biyometrik giriş sistemi** — parmak izi, iris.
7. **Pazarlama otomasyon platformu** — segmentasyon, davranış izleme.
8. **Sağlık check-up programı** — özel nitelikli veri.
9. **Klavye/ekran izleme aracı** — yüksek izleme yoğunluğu.
10. **Çocuğa yönelik eğitim platformu** — ebeveyn rıza süreci.

## 11. Çıktı Saklama

- Tamamlanmış DPIA dokümanı **versiyonlu** ve KVKK Sorumlusu portföyünde.
- Saklama: süreç aktif olduğu sürece + 5 yıl sonrası.
- Erişim: KVKK Sorumlusu, CISO, ilgili Direktör, Hukuk, İç Denetim.
- KVKK Kurulu denetiminde sunulabilir formda hazır.

## 12. KPI

- DPIA gereken proje / DPIA tamamlanan: hedef %100.
- Ortalama DPIA tamamlama süresi: hedef ≤30 gün.
- DPIA review tamamlanma oranı (yıllık): %100.
- Açık DPIA aksiyonları (90 gün geçmiş): 0.
- DPIA sonucu reddedilen proje sayısı: trend takibi.
- DPIA-sonrası ihlal oranı: trend takibi (kalite göstergesi).

## 13. Kontrol Listesi

- [ ] DPIA Standardı yazılı, ≤24 ay güncel mi?
- [ ] Risk taraması (threshold) yeni proje sürecine entegre mi?
- [ ] Tetik listesi güncel, KVKK Kurum rehberleriyle uyumlu mu?
- [ ] DPIA şablonu standart, eksiksiz mi?
- [ ] Risk skor matrisi yazılı, kalibre mi?
- [ ] Risk iştahı yönetim onaylı mı?
- [ ] Her DPIA için ekip rolü atanmış mı?
- [ ] KVKK Sorumlusu bağımsız görüş yazıyor mu?
- [ ] KVKK Komitesi onay tutanakları arşivli mi?
- [ ] Tedbirlerin uygulanması takip ediliyor mu?
- [ ] Yıllık DPIA review takvimi var mı?
- [ ] DPIA çıktıları kurumsal risk kaydına işleniyor mu?
- [ ] DPIA gereken ama yapılmamış proje var mı (gap analizi)?
- [ ] Yıllık iç denetim DPIA örneklemesi yapıyor mu?
- [ ] DPIA ekibinde iş birimi temsilcisi var mı (görmezden gelinmesin)?
- [ ] Otomatik karar süreçleri için ek itiraz hakkı tasarlanmış mı?
- [ ] AI/ML projelerinde LLM Top 10 ek değerlendirmesi yapılıyor mu?

## 14. ISO 29134 Hizalama

ISO 29134 PIA başlıkları bizim şablonla şu şekilde eşleşir:

| ISO 29134 | Bizim DPIA Şablonu |
|-----------|----------------------|
| Necessity Justification | Gereklilik ve Ölçülülük (§5.5) |
| Proportionality Assessment | Gereklilik ve Ölçülülük + Tedbir tasarımı |
| Risk Assessment | Tehdit & Risk Tanımlama (§5.7) |
| Mitigation Plan | Tedbirler (§5.9) |
| Stakeholder Consultation | KVKK Komitesi + paydaş review |

## 15. Yaygın Hatalar

- DPIA yapılmadan yüksek riskli proje canlıya alınması.
- DPIA "form doldurma" gibi ele alınması, gerçek tehdit modelleme yapılmaması.
- Risk skorunun gerekçesiz kalması — denetimde savunulamaz.
- Tedbir tasarımının teknik tarafının kontrolsüz, idari/hukuki tarafının zayıf kalması.
- Artık riskin yönetim kabul tutanağıyla belgelenmemesi.
- Yıllık review'ın atlanması, sürecin değişmesine rağmen DPIA'nın güncellenmemesi.
- KVKK Sorumlusu görüşünün cosmetik olması (gerçek bağımsızlık olmaması).
- AI/ML için DPIA'nın klasik şablonla yetinmesi (LLM-spesifik tehditler kaçırılır).
- Tedarikçi DPIA dahil edilmiyor — sözleşme öncesi değerlendirme eksik.
