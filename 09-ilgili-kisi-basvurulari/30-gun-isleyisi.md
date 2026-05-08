---
Doküman: 30 Gün İşleyişi (SLA, Otomasyon, Eskalasyon)
Bölüm: 09-ilgili-kisi-basvurulari
Sahip: KVKK Sorumlusu
Onaylayan: Hukuk Müdürü
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık
İlgili Mevzuat: 6698 sayılı KVKK m.13/2; Veri Sorumlusuna Başvuru Tebliği MADDE 6/5, MADDE 7
---

# 30 Gün İşleyişi — SLA, Otomasyon, Eskalasyon

## 1. Yasal Çerçeve

KVKK m.13/2 + Tebliğ MADDE 6/5: Veri sorumlusu başvuruyu **talebin niteliğine göre en kısa sürede ve en geç 30 gün içinde** ücretsiz olarak sonuçlandırır. İşlem maliyet gerektiriyorsa Tebliğ M.7'deki ücret alınabilir.

> **Kritik:** GDPR m.12'de yer alan "ek 60 gün uzatma" KVKK'da **bulunmaz**. 30 gün **kati** süredir; aşıldığı her gün Kurul yaptırım sebebidir.

## 2. Başvuru Tarihi (T+0) Hesabı

| Kanal | T+0 |
|-------|-----|
| Yazılı (posta/elden) | Evrakın tebliğ edildiği tarih (Tebliğ M.5/4) |
| KEP | Şirket KEP hesabına ulaşma tarihi (M.5/5) |
| Güvenli/mobil e-imzalı e-posta | Şirket e-posta sistemine ulaşma tarihi |
| Sistemde kayıtlı e-posta | Şirket e-posta sistemine ulaşma tarihi |
| Çevrimiçi başvuru yazılımı | Sistemin başvuruyu kaydettiği tarih |

> Hafta sonu/resmi tatil: 30 gün **takvim günü** olarak sayılır. Tatilde "uzatma" yoktur — sistem 7/24 işler.

## 3. Günlük SLA Yol Haritası

### 3.1. Gün 0 — Başvuru Geldi

| Saat | Eylem | Sahip |
|------|-------|-------|
| 0-1 saat | Otomatik kabul + referans no | Sistem |
| 1-4 saat | Manuel ön kontrol | KVKK uzmanı |
| 4-24 saat | Triyaj (hak/kategori/birim) | KVKK Sorumlusu |
| 24 saat | Atama yapılır | KVKK Sorumlusu |

### 3.2. Gün 1-3 — Kimlik Doğrulama

- Kimlik kanıtı eksikse ek talep e-postası.
- Yüksek riskli talep ise ikincil doğrulama (OTP, video, ipucu).
- Kimlik doğrulanırsa "doğrulandı" stamp.

### 3.3. Gün 3-7 — Veri Arama

- Veri haritasından ilgili kaynaklara sorgu.
- IT, CRM, IK, Pazarlama, Çağrı Merkezi paralel arama.
- Üçüncü taraflarda veri varsa veri işleyenlere (sözleşmesel SLA) talep.
- Yedeklerde veri durumu — yedek rotasyon planı çıkışı.

### 3.4. Gün 7-15 — Karar Çalışması

- İlgili birim cevap taslağı KVKK Sorumlusuna iletir.
- Hukuk değerlendirme (kabul/ret/kısmi).
- Otomatik karar itirazı varsa Veri Bilim ekibi devreye.
- Üçüncü kişiye bildirim gerekiyorsa liste hazırlığı.

### 3.5. Gün 15-25 — Cevap Hazırlığı

- Cevap mektubu şablona dökülür (Tebliğ M.6 zorunlu unsurlar).
- Hukuk son onay.
- KVKK Sorumlusu son okuma.
- Ücret hesabı (sayfa sayısı, kayıt ortamı).

### 3.6. Gün 25-30 — Cevabın İletilmesi

- Cevap kanalına göre gönderim (KEP / e-posta / posta).
- Üçüncü kişilere bildirim (gerekiyorsa).
- Talebin gereği fiilen yerine getirilir (silme, düzeltme).
- Kapanış kaydı.

> **Hedef:** Ortalama cevap süresi **15 gün altı**. 30 gün son sınır, kural değil.

## 4. Otomatik Takip Sistemi Gereksinimleri

### 4.1. Ticket Sistemi Özellikleri

- Her başvuruya benzersiz BSV-YYYY-NNNN ID.
- KVKK custom alanlar (kanal, hak, gerekli birim, son tarih).
- Otomatik kullanıcı bildirimi (kabul, durum güncellemesi, cevap).
- Audit log (immutable — Splunk integration).
- KEP entegrasyonu (gelen KEP otomatik ticket).
- E-posta entegrasyonu (kvkk@sirket.com.tr → ticket).
- Web form entegrasyonu (https://...kvkk/basvuru → ticket).

### 4.2. SLA Uyarıları

| Aşama | Uyarı |
|-------|-------|
| Gün 0 | Ticket açıldı — KVKK uzmanı slack/teams notification |
| Gün 3 | Triyaj tamam mı? — KVKK Sorumlusu hatırlatma |
| Gün 7 | Veri arama ilerleme? — birim sahibine hatırlatma |
| Gün 14 | Yarı yol — KVKK Sorumlusu özet rapor |
| Gün 21 | Son hafta — Hukuk hatırlatma |
| Gün 25 | Kritik — KVKK Komitesi alert |
| Gün 28 | Kırmızı alarm — CISO + CEO bilgilendirme |
| Gün 30 | SLA aşıldı — otomatik olay açma (`olay-yonetimi`) |

### 4.3. Veri Arama Otomasyonu

- Centralized search (Elasticsearch/Splunk) — tüm kaynaklar tek arayüz.
- T.C. kimlik no üzerinden federated search.
- Kaynak haritası: CRM (Salesforce/Hubspot), ERP (SAP/Oracle), IK (Workday/SAP SuccessFactors), pazarlama (HubSpot/Marketo/Mailchimp), çağrı merkezi (Genesys/Avaya), e-posta arşivi (Mimecast), web log (CloudFlare/Akamai), CCTV (görüntü yönetim sistemi).
- Sonuçlar PDF rapor olarak otomatik üretilir.

### 4.4. Şablon Motoru

- Cevap mektupları **Word/PDF şablonları** + değişken alanlar.
- Tebliğ M.6 zorunlu alanlar otomatik doldurulur.
- Hukuk onay sonrası dijital imza + KEP gönderim.

## 5. Kimlik Doğrulama Yöntemleri

### 5.1. Risk Seviyesine Göre Eşleme

| Risk seviyesi | Talep tipi | Doğrulama yöntemi |
|---------------|-----------|-------------------|
| Düşük | "Verim işleniyor mu" (m.11/a) | T.C. + sistemde kayıtlı e-posta |
| Orta | Bilgi (m.11/b), düzeltme (m.11/d) | T.C. + iki ipucu eşleşmesi (örn. müşteri no + son sipariş tarihi) |
| Yüksek | Veri kopyası, silme (m.11/e), aktarım listesi (m.11/ç) | OTP + iki ipucu + (gerekirse) video görüşme |
| Kritik | Vekil ile başvuru, eski çalışan/müşteri, özel nitelikli veri | Noter onaylı vekaletname + kimlik fotokopisi + ek doğrulama |

### 5.2. Doğrulama Sırasında Hata

- 3 başarısız OTP → kilitlenme + insan onayı.
- Yanlış ipucu cevabı → ek soru.
- Şüpheli aktivite → İhlal Yönetimi'ne bildirim (bkz. `08-ihlal-yonetimi/`).

### 5.3. Doğrulanamayan Başvurular

- 14 gün içinde 2. tamamlama talebi.
- 21 gün içinde 3. ve son tamamlama talebi.
- 28 gün — "kimlik doğrulanamadı" gerekçesiyle reddetme metni hazırlığı.
- 30 gün — gerekçeli ret cevap.

## 6. Karmaşık Talepler

### 6.1. KVKK'da Uzatma Yok — "Karmaşık" Mazeret Olmaz

Bazı kuruluşlar GDPR analojisiyle 30+30+30 gün talep eder. **KVKK bunu kabul etmez.** Karmaşık taleplerde bile 30 gün sınırına uyulması zorunludur. Süreç tasarımı buna göre yapılmalıdır:

- Otomatik veri arama (manuel saatler harcanmasını önler).
- Standardize cevap şablonları (yazma süresini kısaltır).
- Hukuk on-call (gün içinde değerlendirme).
- Üçüncü taraf SLA'ları **7-15 gün** sıkı tutulur.

### 6.2. Çoklu Hak Talebi

Bir başvuruda 5 hak istenmiş olsa bile **30 gün hepsine** uygulanır. Tek cevap mektubu ama her hak için ayrı bölüm.

### 6.3. Geçmişe Dönük Geniş Veri Talebi

Örn. "Son 10 yıldaki tüm verim". Süre dolduğu için silinmiş kayıtlar varsa cevapta:
- Saklama politikamız özetlenir.
- Silinme tarihi belirtilir.
- Mevcut veri kopyası verilir.

## 7. Ücret Hesaplama Örneği

### 7.1. Yazılı Cevap (Tebliğ M.7/1)

| Sayfa Sayısı | Ücret |
|--------------|-------|
| 1-10 sayfa | **Ücretsiz** |
| 11. sayfa | 1 TL |
| 50 sayfa cevap | (50-10) × 1 TL = **40 TL** |
| 200 sayfa cevap | (200-10) × 1 TL = **190 TL** |

### 7.2. Kayıt Ortamı (Tebliğ M.7/2)

| Ortam | Maliyet (yaklaşık) |
|-------|-------------------|
| CD (700 MB) | 5-10 TL |
| DVD (4.7 GB) | 8-15 TL |
| USB bellek (8 GB) | 50-150 TL |
| USB bellek (32 GB) | 150-300 TL |

> Ücret kayıt ortamı **birim maliyetini geçemez**. Kâr eklenemez.

### 7.3. Hatadan Kaynaklı

Başvuru veri sorumlusunun (Şirket) hatasından kaynaklanıyorsa **alınan ücret 7 gün içinde iade** edilir (banka havalesi). Fatura iptal edilir.

### 7.4. KDV

Tebliğ ücret tarifesinde KDV açıkça belirtilmemiştir. **Genel uygulama:** ücret KDV dahil bedel olarak yorumlanır; başvuru sahibinden ek KDV talep edilmez. Şirket faturayı KDV dahil keser.

## 8. Eskalasyon Eşikleri

### 8.1. SLA İhlali Eskalasyonu

| Gecikme | Eskalasyon |
|---------|-----------|
| 0-7 gün | İlgili birim yöneticisi |
| 7-14 gün | Birim direktörü + KVKK Sorumlusu |
| 14-21 gün | KVKK Komitesi |
| 21-30 gün | CEO + Yönetim Kurulu bildirimi |
| 30+ gün | Olay açılır, RCA, Kurul'a açıklama hazırlığı |

### 8.2. Hukuki Risk Eskalasyonu

- Talep özel nitelikli veri içeriyor → Hukuk + KVKK Komitesi.
- Talep mahkeme kararı ile çelişiyor → Hukuk + Adli süreç.
- Saldırgan / kötü niyetli başvuru şüphesi → 08-İhlal Yönetimi.
- Vekaletname şüpheli → Noter doğrulama.

### 8.3. İletişim Riski

- Talep medyaya yansıdı → Kurumsal İletişim devreye.
- Şikâyet sosyal medyada → Hukuk + İletişim ortak yanıt.
- Kurul yazısı geldi → 5 iş günü içinde aksiyon planı.

## 9. Süreç İzleme Kontrol Paneli

### 9.1. Operasyonel Pano (Günlük)

- Açık başvuru sayısı.
- Bugünkü gelen başvurular.
- 7 gün altı yaklaşan başvurular.
- 25+ gün geçmiş başvurular (kırmızı).
- Atanmamış başvurular.
- Kimlik doğrulama bekleyenler.
- Hukuk onay bekleyenler.

### 9.2. Yönetim Panosu (Haftalık)

- Haftalık geliş trendleri.
- Ortalama cevap süresi.
- 30 gün uyum oranı.
- Hak bazında dağılım.
- Kanal bazında dağılım.
- Reddedilenler / kabul edilenler oranı.
- Kurul yazışması var mı?

### 9.3. Yıllık Rapor (KVKK Komitesi)

- Toplam başvuru.
- Yıllık trend.
- Reddedilenlerin Kurul tarafından gözden geçirilme oranı.
- Süreç iyileştirme önerileri.
- Bütçe ve kaynak ihtiyacı.

## 10. Tipik Hatalar

| Hata | Doğru Yaklaşım |
|------|----------------|
| "Karmaşık talep" diye uzatma istemek | Otomasyon ve şablon ile süreyi kısalt; uzatma yok. |
| Tatilde sayacın durduğunu varsaymak | Sayaç durmaz; on-call kapsamı genişlet. |
| Kimlik doğrulamayı sürekli geciktirmek | İlk 3 gün net olmalı; 28. günde başlanmaz. |
| Cevap mektubunu son güne sıkıştırmak | 25. gün hazır olmalı; 5 gün buffer. |
| Ücret tahsil edilmeden cevap göndermek | Uygulama bağlı: önce ücret, sonra cevap (Hukuk onayı ile). |
| Şikayet hakkını cevap mektubunda atlamak | Mutlaka eklenir — Tebliğ M.6 ruhuna uygun. |
| Üçüncü taraf cevabı beklerken sayacı durdurmak | Sayaç durmaz; üçüncü taraf SLA'sı sıkı tutulur. |

## 11. Süreç İyileştirme

### 11.1. Aylık Retrospektif

KVKK ekibi her ay:
- En çok zaman alan adım hangisi?
- Hangi hak en zor?
- Otomasyon yeterli mi?
- Hukuk onay süresi makul mu?

### 11.2. Yıllık İyileştirme Çevrimi

- Kıyaslama (sektör peer'leriyle).
- Yeni Kurul kararları doğrultusunda revizyon.
- Eğitim güncellemesi.
- Otomasyon yatırımı.

## 12. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi |
