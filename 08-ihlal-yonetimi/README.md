---
Doküman / Document: 08 - İhlal Yönetimi (Bölüm Girişi) / 08 - Personal Data Breach Management (Section Introduction)
Bölüm / Section: 08-ihlal-yonetimi
Sahip / Owner: KVKK Sorumlusu + Bilgi Güvenliği Müdürü / KVKK Officer + Chief Information Security Officer (CISO)
Onaylayan / Approved by: Hukuk Müdürü + KVKK Komitesi / Head of Legal + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş (her ihlal sonrası) / Annual + triggered (after every breach)
İlgili Mevzuat / Legal Reference: Law No. 6698 (KVKK) Art. 12; Personal Data Protection Authority Decision No. 2019/10 dated 24.01.2019; KVKK Data Security Guide (2018); Law No. 5651; NIST SP 800-61 Rev.2; ISO/IEC 27035-1:2023
---

## English

# 08 - Personal Data Breach Management

## 1. Purpose of the Section

In its capacity as data controller, our company processes personal data that may be subject to unauthorized access, unlawful disclosure, loss, or alteration. This section operationalizes the obligations to:

- Notify the Personal Data Protection Authority of Türkiye (the "Authority") **without undue delay and at the latest within 72 hours**, pursuant to Article 12(5) of Law No. 6698 (KVKK).
- Notify **affected data subjects** through appropriate channels, pursuant to the second sentence of Art. 12(5).
- Operationally manage **containment, investigation, root cause analysis, and recurrence prevention**.

## 2. Scope

This section covers:

- All digital assets (databases, file servers, e-mail, SaaS applications, mobile devices, IoT/OT systems).
- Physical environments (archives, HR files, printed documents, CCTV recordings).
- Data processed on the company's behalf by data processors (cloud providers, outsourced call centers, HR SaaS, courier services).
- Insider threats (current/former employee, contractor, supplier).
- All geographical locations (domestic and foreign branches/offices).

## 3. File Index

| # | File | Topic |
|---|------|-------|
| 1 | `README.md` | Section introduction (this file) |
| 2 | `ihlal-mudahale-prosedur.md` | Incident lifecycle aligned with NIST 800-61 / ISO 27035; CSIRT; runbooks |
| 3 | `72-saat-bildirim.md` | 72-hour Authority notification; data subject notification; Art. 12(5) details |
| 4 | `ihlal-bildirim-formu.md` | Fillable Authority breach notification form + worked example |
| 5 | `soak-test-tatbikat.md` | Annual tabletop exercises; 5 scenarios; KPIs |
| 6 | `kok-neden-analizi.md` | 5 Whys, Fishbone, Apollo RCA; CAPA tracking |

## 4. Core Concepts

### 4.1. Incident vs. Personal Data Breach

| Concept | Definition | KVKK Notification Required? |
|---------|------------|-----------------------------|
| Security **incident** | Any attempted or actual event affecting confidentiality, integrity, or availability of an information system (e.g., failed password attempt, antivirus alert). | No - if analysis confirms no personal data was accessed. |
| Personal data **breach** | Unlawful obtaining, unauthorized access, loss, disclosure, alteration, or destruction of personal data (KVKK Art. 12(5) + Authority Decision 2019/10). | **Yes - to the Authority + data subjects.** |

**Key rule:** Not every security incident is a breach; however, **every breach starts as an incident.** The notification threshold is reached the moment "unauthorized access to or impact on personal data **occurred or is reasonably likely to have occurred**."

### 4.2. Triple Impact Model

The Authority requires breach assessment along three axes:

1. **Confidentiality breach** - unauthorized disclosure (data leak, scraping, BEC).
2. **Integrity breach** - unauthorized alteration (tampering; manipulation pre/post ransomware encryption).
3. **Availability breach** - unauthorized deletion/blocked access (ransomware, sabotage, hardware failure combined with insufficient backups).

Any one of these alone may trigger notification.

### 4.3. Definition of "Awareness Moment"

The 72-hour clock starts when **the data controller becomes reasonably aware of the breach**. Not initial suspicion - rather **the moment likelihood of impact on personal data reaches an acceptable degree of certainty**. The company records this date and time **with minute-level precision** in the incident log (see `ihlal-mudahale-prosedur.md` §6).

## 5. Governance and Roles

| Role | Responsibility |
|------|----------------|
| **KVKK Officer** | Owner of the section; coordinator of the notification process; primary point of contact with the Authority. |
| **CISO** | Technical detection, containment, forensics. |
| **Incident Commander** | Operational decision authority (CISO or delegate). |
| **Legal Counsel** | Notification text, contractual liability, regulatory risk. |
| **Corporate Communications** | Press, customer communication, social media. |
| **HR Director** | Employee breach, insider threat, discipline. |
| **Executive (CEO/CFO)** | Escalation, budget (forensics, ransom prohibition), final approval. |
| **Processor DPO** | Contractual notification obligation; informing the controller within the agreed [SLA]. |

## 6. First 24 Hours - Summary Flow

```
[T+0 Detection] -> [T+1h Initial triage]
   |
[T+2h CSIRT meeting]
   |
[T+4h Containment decision]
   |
[T+8h Scoping - record count, categories]
   |
[T+24h Authority preliminary notification - partial information allowed]
   |
[T+72h Authority final notification]
   |
[T+72h - 30 days Data subject notification]
   |
[T+30 days - 6 months Root cause + CAPA + tabletop update]
```

## 7. Linked Sections

- **05 - Technical Measures** -> SIEM, EDR, log management (detection infrastructure).
- **06 - Administrative Measures** -> Incident awareness training, confidentiality agreements.
- **07 - Transfers** -> Notification clause in processor contracts.
- **11 - Audit and Compliance** -> Breach records as input to internal audit.

## 8. Annual Performance Indicators

The effectiveness of this section is measured with the following metrics (Q1 reporting to the KVKK Committee):

| KPI | Target | Source |
|-----|--------|--------|
| Mean Time To Detect (MTTD) | < 24 hours | SIEM event log |
| Mean Time To Notify the Authority (MTTN) | < 72 hours (mandatory) | Notification archive |
| Mean Time To Respond (MTTR - containment) | < 4 hours | Incident system |
| Tabletop completion rate | 100% (4 scenarios annually) | Exercise reports |
| Recurring breach rate | 0% (CAPA effectiveness) | RCA archive |

## 9. Version History

| Version | Date | Change | Approval |
|---------|------|--------|----------|
| 1.0 | 2026-05-08 | First publication | KVKK Committee |

---

## Türkçe

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
