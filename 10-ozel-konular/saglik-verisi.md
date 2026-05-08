---
Doküman: Sağlık Verisi Yönetimi (m.6 Özel Nitelikli)
Bölüm: 10-ozel-konular
Sahip: KVKK Sorumlusu + İK + İSG Birimi + (varsa) İşyeri Hekimi
Onaylayan: Hukuk Müdürü + KVKK Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + sektör mevzuatı değişikliklerinde
İlgili Mevzuat: 6698 sayılı KVKK m.6; 6331 sayılı İş Sağlığı ve Güvenliği Kanunu; 4857 sayılı İş Kanunu; 5510 sayılı SGK Kanunu; 3359 sayılı Sağlık Hizmetleri Temel Kanunu; 663 sayılı KHK; Kişisel Sağlık Verileri Yönetmeliği (21.06.2019 / 30808); Kurul 2018/10 sayılı Kararı
---

# Sağlık Verisi Yönetimi

## 1. Tanım ve Kapsam

Sağlık verisi, KVKK m.6/1 kapsamında **özel nitelikli** kişisel veridir. Şirketimiz açısından sağlık verisi şu kanallardan geçer:

| Kanal | Veri Tipi |
|-------|-----------|
| İşe giriş muayenesi | Tetkik raporu, görme, işitme, kan testi |
| Periyodik sağlık muayenesi | İSG kapsamında zorunlu |
| Devamsızlık raporu | Hastalık tipi (ICD-10), istirahat süresi |
| İş kazası | Tutanak, tıbbi rapor, malüliyet derecesi |
| Meslek hastalığı | Tanı, takip raporları |
| Aşı kayıtları (örn. COVID-19) | Aşı tipi, tarih, sertifika |
| Maluliyet, engellilik | Engelli sağlık raporu |
| Hamilelik / emzirme | Süreç bilgisi |
| Sigorta tazmin talebi | Tıbbi tanı, fatura |
| Müşteri (özel sektör — sağlık dışı) | Genelde sınırlı; özel destek talebi |

> **Cinsel hayat verisi:** KVKK m.6 ile birlikte düzenlenir; Şirket bağlamında çok sınırlı (örn. cinsel taciz olayı kayıtları).

## 2. Hukuki Sebepler

### 2.1. KVKK m.6/2 - Açık Rıza

Genel kural; ancak çalışan-işveren asimetrisi nedeniyle pratikte sorunludur (özgürlük testi).

### 2.2. KVKK m.6/3 - Kanunlarda Açıkça Öngörülmesi

Sağlık ve cinsel hayat verisi açık rıza aranmaksızın ancak **kamu sağlığının korunması, koruyucu hekimlik, tıbbi teşhis, tedavi ve bakım hizmetlerinin yürütülmesi, sağlık hizmetleri ile finansmanının planlanması ve yönetimi** amaçlarıyla ve **sır saklama yükümlülüğü altında bulunan kişiler veya yetkili kurum ve kuruluşlar** tarafından işlenebilir.

> Bu, çoğu işyeri sağlık verisinin **işyeri hekimi** veya **dış İSG firması** tarafından işlenmesini kapsar — Şirketin kendisi değil.

### 2.3. Diğer Yasal Sebepler

- 6331 sayılı İSG: işe giriş + periyodik muayene zorunlu.
- 4857: çalışma ortamı sağlık koşulları.
- 5510 SGK: sağlık raporu, prim hesabı.
- 657 sayılı (kamu): farklı rejim.

## 3. Sır Saklama Yükümlülüğü

Sağlık verisi işleyen meslek mensupları:
- Hekim (Tabip Odası, sır yükümlülüğü TCK m.258).
- Hemşire, ebe.
- Eczacı, diş hekimi.
- İşyeri hekimi (6331 ek yükümlülük).
- Diğer sağlık personeli.

> **Şirket içi düzenleme:** İşyeri sağlık verisi şirket genel personeline değil, **sadece işyeri hekimi + İSG uzmanı + KVKK sorumlusu (denetim için sınırlı)** erişebilir.

## 4. Veri Akışı (Tipik İşyeri)

```
Çalışan → İşyeri Hekimi (sır saklama altında)
              ↓
       Sağlık dosyası (hekim arşivi — şifreli)
              ↓
       İK (sadece "muayene oldu/olmadı" + iş için uygunluk)
              ↓
       Üretim / Operasyon (sadece "uygun değil" sonucu)
```

İK'ya **tanı/teşhis** verisi gitmez. Sadece "iş için uygun / değil / kısıtlı" bilgisi.

## 5. Erişim Kontrolü

### 5.1. Erişim Matrisi

| Rol | Erişim |
|-----|--------|
| İşyeri Hekimi | Tam erişim — sır saklama altında |
| İSG Uzmanı | Erişim — sınırlı (risk değerlendirme) |
| İK Direktörü | "Uygun/Değil" + dolaylı bilgi (raporlu gün sayısı) |
| İK Uzmanı | Devamsızlık takibi (raporlu) |
| KVKK Sorumlusu | Denetim için sınırlı + onay |
| Hukuk | Olay halinde (kazada, davada) |
| Yönetim | Olay halinde özet |
| Diğer çalışan | YASAK |

### 5.2. Sistem Erişimi

- Sağlık dosyası **ayrı sistemde** (HER, EHR, işyeri hekimi yazılımı).
- Genel İK sisteminde sağlık verisi **sınırlı** (raporlu gün, sertifika tarihi).
- Şifreleme zorunlu.
- Audit log her erişim.

## 6. Saklama Süresi

| Veri | Süre | Kaynak |
|------|------|--------|
| İşe giriş muayenesi | İş akdi sonrası **15 yıl** | 6331 sayılı Kanun + işyeri hekimi mevzuatı |
| Periyodik muayene | Aynı | Aynı |
| İş kazası kaydı | **15 yıl** (zamanaşımı) | 5510 + iş kazası mevzuatı |
| Meslek hastalığı | **30 yıl** | Yargıtay içtihatları |
| Devamsızlık raporu | İlgili yıl + **5 yıl** | İK iyi pratiği |
| Hamilelik / emzirme | Süreç sonu + **5 yıl** | İK |

## 7. Aktarım

### 7.1. SGK / E-Bildirge

- SGK'ya aktarım kanuni yükümlülük (5510).
- KVKK m.6/3 kapsamı + m.5/2-a.
- Aydınlatma + bilgilendirme.

### 7.2. MEDULA, e-Reçete

- Sağlık Bakanlığı sistemleri.
- İşyeri hekimi tarafından kullanılır.
- Veri sorumlusu Şirket; veri işleyen Bakanlık değildir, ancak özel rejim.

### 7.3. Sigorta (Özel Sağlık)

- Özel sigorta tazmin sürecinde aktarım.
- Açık rıza zorunlu (sigorta sözleşmesi imzasında).
- Gerekli minimum veri (Need-to-Know).

### 7.4. Yurt Dışı Aktarım

- Çok sınırlı (örn. uluslararası işveren ofisleri arası bilgi paylaşımı).
- KVKK m.9 + Standart Sözleşme + DPIA.
- Tercih: Türkiye sınırları içinde işleme.

## 8. Teknik Tedbirler (Kurul 2018/10)

- AES-256 şifreleme at rest.
- TLS 1.3 in transit.
- HSM/KMS anahtar yönetimi.
- DLP — sağlık verisi etiketi.
- Erişim log + UEBA anomalisi.
- Yedekleme şifreli.
- Pseudonymization (IK ile sağlık dosyası referans ayrı).
- Veritabanı kolon bazlı şifreleme (özellikle ICD-10 alanı).

## 9. İdari Tedbirler

- Sağlık verisi politikası (bu doküman + ek prosedür).
- İşyeri hekimi sözleşmesi — KVKK uyumlu.
- Sır saklama yükümlülüğü beyanı (yıllık).
- Eğitim — sağlık verisi farkındalık.
- Audit — yıllık.

## 10. HIMSS / HL7 / FHIR Uyumu

Sağlık entegrasyonu söz konusuysa:

### 10.1. HL7 v2 / v3
- Mesaj standardı.
- Hasta verisi alanları (PID, ORC, OBR, OBX).

### 10.2. FHIR (Fast Healthcare Interoperability Resources)
- REST API tabanlı.
- Resource bazlı (Patient, Observation, Condition, MedicationRequest).
- KVKK uyumu için:
   - OAuth 2.0 + SMART on FHIR.
   - Audit logger (FHIR AuditEvent).
   - Consent resource ile rıza yönetimi.

### 10.3. HIMSS EMR Olgunluk Modeli
- 0-7 seviye.
- KVKK gereği Türkiye uygulaması ek katmanlar (KVK Kurul kararları, sektör mevzuatı).

## 11. SGK Entegrasyonları

### 11.1. e-Bildirge
- Aylık prim bildirimi.
- Çalışan sağlık verisi ek bildirimleri (iş kazası, meslek hastalığı).

### 11.2. e-Reçete
- İşyeri hekimi kullanır.
- Şirket genel sistemine yansımaz.

### 11.3. MEDULA
- Sağlık hizmeti sunucularıyla SGK arası.
- Şirket çalışanları için özel sigorta varsa entegre olabilir.

## 12. Hassas Konu — Aşı / Pandemi Verisi

COVID-19 deneyiminden:
- Aşı sertifikası özel nitelikli.
- "Aşı oldu mu?" sorgusu açık rıza ile.
- Yasal zorunluluk (kamu sağlığı) sınırlı durumlarda m.6/3.
- HES kodu vb. eski uygulamalar dönemi geçti; mevcut benzer durumlarda **DPIA** yapılır.

## 13. İlgili Kişi Hakları

- m.11/b: Sağlık dosyası kopyası talep edilebilir → **işyeri hekimi** üzerinden, Şirket KVKK Sorumlusu koordinasyon.
- m.11/d: Düzeltme — tıbbi rapor düzeltme klinik gerektirir; Şirket sadece kayıt düzeltir.
- m.11/e: Silme — yasal saklama süresi içinde reddedilir; sonrasında silinir.
- Sır saklama yükümlülüğüyle çatışmada Hukuk + Hekim danışılır.

## 14. Tipik Hatalar

| Hata | Doğru Yaklaşım |
|------|----------------|
| İK genel sisteminde tanı saklamak | Sadece "uygun/değil"; tanı hekim sisteminde |
| Diğer çalışana sağlık paylaşımı | Yasak — sır ihlali + TCK suç |
| Toplu aşı listesi yöneticide görünür | Liderlik raporu sadece "X / Y" toplam |
| Sağlık + IK aynı veritabanında | Pseudonymize, ayrı şema |
| Açık rıza yerine zorunlu kılma | İSG zorunluluğu m.6/3 ile çözülür |
| 5 yıl saklama | 15 yıl + (meslek hastalığı 30 yıl) |
| Yurt dışı bulut sağlık verisi | Türkiye yerleşim tercih |
| Şifresiz e-postada rapor | KEP + şifreli ek |

## 15. KPI'lar

| KPI | Hedef |
|-----|-------|
| Sağlık verisine erişim audit log | %100 |
| Şifreleme kapsamı | %100 |
| Yıllık sır saklama beyanı | %100 |
| İK'da tanı saklama | %0 |
| Aktarım DPA + KVKK uyum | %100 |
| Sağlık DPIA güncel | Yıllık |

## 16. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi |
