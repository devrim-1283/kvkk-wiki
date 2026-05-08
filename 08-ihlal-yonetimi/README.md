---
Doküman: 08 - İhlal Yönetimi (Bölüm Girişi)
Bölüm: 08-ihlal-yonetimi
Sahip: KVKK Sorumlusu / Bilgi Güvenliği Müdürü
Onaylayan: Hukuk Müdürü + KVKK Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (her ihlal sonrası)
İlgili Mevzuat: 6698 sayılı KVKK m.12, KVKKK 24.01.2019 tarih 2019/10 sayılı Kararı, KVKK Veri Güvenliği Rehberi (2018), 5651 sayılı Kanun, NIST SP 800-61 Rev.2, ISO/IEC 27035-1:2023
---

# 08 - Kişisel Veri İhlali Yönetimi

## 1. Bölümün Amacı

Bu bölüm, veri sorumlusu sıfatıyla şirketimizin işlediği kişisel verilerin yetkisiz erişim, hukuka aykırı ifşa, kayıp veya değiştirilmesi durumunda;
- 6698 sayılı Kanun'un 12. maddesinin 5. fıkrası uyarınca **en kısa sürede ve en geç 72 saat içinde** Kişisel Verileri Koruma Kurulu'na bildirim yükümlülüğünün,
- Kanun'un 12/5 ikinci cümlesi uyarınca **etkilenen ilgili kişilere** uygun yöntemle bildirimin,
- Olayın **sınırlandırılması, soruşturulması, kök neden analizi ve tekrarının önlenmesi** süreçlerinin

operasyonel olarak nasıl yürütüleceğini düzenler.

## 2. Kapsam

Bu bölümün kapsamına girer:
- Tüm dijital varlıklar (veri tabanları, dosya sunucuları, e-posta, SaaS uygulamalar, mobil cihazlar, IoT/OT sistemler).
- Fiziksel ortamlar (arşiv, IK dosyaları, basılı evrak, kamera kayıtları).
- Veri işleyenler tarafından şirket adına işlenen veriler (bulut sağlayıcı, dış kaynak çağrı merkezi, IK SaaS, kargo).
- İçeriden tehditler (mevcut/eski çalışan, yüklenici, tedarikçi).
- Tüm coğrafi konumlar (yurt içi ve yurt dışı şubeler/ofisler).

## 3. Bölümün Dosya Dizini

| # | Dosya | Konu |
|---|-------|------|
| 1 | [`README.md`](./README.md) | Bölüm girişi (bu dosya) |
| 2 | [`ihlal-mudahale-prosedur.md`](./ihlal-mudahale-prosedur.md) | NIST 800-61 / ISO 27035 uyumlu olay yaşam döngüsü, CSIRT, runbook'lar |
| 3 | [`72-saat-bildirim.md`](./72-saat-bildirim.md) | Kurul'a 72 saat bildirim, ilgili kişi bildirimi, m.12/5 detayları |
| 4 | [`ihlal-bildirim-formu.md`](./ihlal-bildirim-formu.md) | Doldurulabilir Kurul bildirim formu + örnek senaryo |
| 5 | [`soak-test-tatbikat.md`](./soak-test-tatbikat.md) | Yıllık tabletop tatbikatları, 5 senaryo, KPI'lar |
| 6 | [`kok-neden-analizi.md`](./kok-neden-analizi.md) | 5 Whys, Fishbone, Apollo RCA, CAPA takibi |

## 4. Temel Kavramlar

### 4.1. Olay (Incident) vs. İhlal (Breach)

| Kavram | Tanım | KVKK Bildirim Gerekir mi? |
|--------|-------|---------------------------|
| Güvenlik **olayı** | Bilgi sisteminin gizlilik, bütünlük veya erişilebilirliğini etkileyebilecek her türlü teşebbüs veya gerçekleşmiş eylem (örn. başarısız parola denemesi, antivirüs alarmı). | Hayır — analiz sonucu kişisel veriye erişim gerçekleşmediyse. |
| Kişisel veri **ihlali** | Kişisel verilerin kanuni olmayan yollarla başkaları tarafından elde edilmesi, yetkisiz erişimi, kaybı, ifşası, değiştirilmesi veya yok edilmesi (KVKK m.12/5 ile Kurul 24.01.2019/2019-10 kararı). | **Evet — Kurul'a + ilgili kişilere.** |

**Anahtar kural:** Her güvenlik olayı ihlal değildir; ancak **her ihlal mutlaka bir olaydan doğar.** Bildirim eşiği "kişisel veriye yetkisiz erişim/etkilenme **gerçekleşti veya gerçekleşme makul ihtimali var**" anıdır.

### 4.2. Üçlü Etki Modeli

Kurul kararı ihlal değerlendirmesini üç eksende ister:
1. **Gizlilik (Confidentiality) ihlali** — yetkisiz açığa çıkma (data leak, scraping, BEC).
2. **Bütünlük (Integrity) ihlali** — yetkisiz değiştirme (tampering, ransomware şifreleme öncesi/sonrası manipülasyon).
3. **Erişilebilirlik (Availability) ihlali** — yetkisiz silme/erişimin engellenmesi (ransomware, sabotaj, donanım arızası ile birleşen yetersiz yedek).

Üçü de tek başına bildirim gerektirebilir.

### 4.3. "Öğrenme Anı" Tanımı

72 saat sayacı, **veri sorumlusunun ihlalden makul ölçüde haberdar olduğu an** başlar. İlk şüphe değil; ancak **kişisel veriye etki ihtimali kabul edilebilir bir kesinliğe ulaştığı an** referans alınır. Şirket bu tarihi ve saati **dakika hassasiyetinde** olay kayıt sistemine düşer (bkz. `ihlal-mudahale-prosedur.md` §6).

## 5. Yönetişim ve Roller

| Rol | Sorumluluk |
|-----|-----------|
| **KVKK Sorumlusu** | Bölümün sahibi; bildirim sürecinin koordinatörü; Kurul ile birinci muhatap. |
| **Bilgi Güvenliği Müdürü (CISO)** | Teknik tespit, sınırlandırma, forensik. |
| **Olay Komutanı (Incident Commander)** | Operasyonel karar mercii (CISO veya delegesi). |
| **Hukuk Müşavirliği** | Bildirim metni, sözleşmesel sorumluluk, regülatif risk. |
| **Kurumsal İletişim** | Basın, müşteri iletişimi, sosyal medya. |
| **İK Direktörü** | Çalışan ihlali, içeriden tehdit, disiplin. |
| **Yönetim (CEO/CFO)** | Eskalasyon, bütçe (forensik, fidye yasak), nihai onay. |
| **DPO veri işleyen** | Sözleşmesel bildirim yükümlülüğü; veri sorumlusunu en geç [SLA] içinde haberdar etme. |

## 6. Birinci 24 Saat Özet Akış

```
[T+0 Tespit] → [T+1 saat İlk triyaj]
   ↓
[T+2 saat CSIRT toplantısı]
   ↓
[T+4 saat Sınırlandırma kararı]
   ↓
[T+8 saat Kapsam belirleme - kayıt sayısı, kategori]
   ↓
[T+24 saat Kurul taslak bildirimi - eksik veri kabul]
   ↓
[T+72 saat Kurul nihai bildirimi]
   ↓
[T+72 saat - 30 gün İlgili kişi bildirimi]
   ↓
[T+30 gün - 6 ay Kök neden + CAPA + tatbikat güncellemesi]
```

## 7. Bağlantılı Bölümler

- **05 - Teknik Tedbirler** → SIEM, EDR, log yönetimi (tespit altyapısı).
- **06 - İdari Tedbirler** → Olay farkındalığı eğitimi, gizlilik sözleşmeleri.
- **07 - Aktarım** → Veri işleyen sözleşmesindeki bildirim klozu.
- **11 - Denetim ve Uyum** → İhlal kayıtları iç denetim girdisi.

## 8. Yıllık Performans Göstergeleri

Bu bölümün etkinliği şu metriklerle ölçülür (KVKK Komitesi Q1 raporlamasında):

| KPI | Hedef | Kaynak |
|-----|-------|--------|
| Mean Time To Detect (MTTD) | < 24 saat | SIEM olay log'u |
| Mean Time To Notify (MTTN — Kurul) | < 72 saat (zorunlu) | Bildirim arşivi |
| Mean Time To Respond (MTTR — sınırlandırma) | < 4 saat | Olay sistemi |
| Tatbikat tamamlama oranı | %100 (yıllık 4 senaryo) | Tatbikat raporları |
| Tekrarlayan ihlal oranı | %0 (CAPA etkinliği) | RCA arşivi |

## 9. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi |
