---
Doküman / Document: Envanter Bakım, Gözden Geçirme ve Değişiklik Yönetimi / Inventory Maintenance, Review and Change Management
Bölüm / Section: 02-envanter-ve-sicil
Sahip / Owner: KVKK Sorumlusu / KVKK Officer
Onaylayan / Approved by: Hukuk Müdürü + KVKK Komitesi / Head of Legal + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Çeyreklik (operasyonel) + Yıllık (tam revizyon) + Tetiklenmiş / Quarterly (operational) + Annual (full revision) + Triggered
İlgili Mevzuat / Legal Reference: 6698 sayılı KVKK m.10, m.12, m.16 / Law No. 6698 (KVKK) Art. 10, 12, 16; Veri Sorumluları Sicili Hakkında Yönetmelik MADDE 5, 9, 13 / Regulation on the Data Controllers' Registry Art. 5, 9, 13; Aydınlatma Tebliği MADDE 5 / Disclosure/Information Notice Communiqué Art. 5; Saklama ve İmha Yön. MADDE 5 / Erasure-Destruction Regulation Art. 5
---

## English

# Inventory Maintenance, Review and Change Management

The inventory is not a "set and forget" document. Under Reg. Art. 5/d, registry information based on the inventory is the **basis** for satisfying the disclosure obligation, responding to data subject requests, and determining the scope of explicit consent. Therefore, when the inventory is out of date, **the entire compliance architecture goes wrong**.

This document defines the operational regime for keeping the inventory current.

## 1. Three-Layer Maintenance Model

| Layer | Frequency | Purpose |
|-------|-----------|---------|
| Continuous (event-driven) | Immediate | Inventory updated as soon as a process changes; VERBİS notification within 7 days |
| Quarterly review | Every 3 months | Process owners and KVKK Officer validate row by row |
| Annual full revision | Once a year | Whole inventory is re-baselined and aligned with legislative and organisational changes |

## 2. Continuous Maintenance — Event-Driven

### 2.1 Change Triggers

**Any** of the following events triggers an inventory update:

| # | Trigger | Affected fields | Action |
|---|---------|------------------|--------|
| 1 | New process launched | New row | Inventory row before processing starts + VERBİS update |
| 2 | New purpose added to existing process | Processing purpose, legal ground | Legal Department confirmation → update |
| 3 | New data category processed | Data category, personal data items | Information notice also updated |
| 4 | New person group (e.g., visitor monitoring for the first time) | Data subject group | Update information notice + signage |
| 5 | New system/SaaS onboarded | Storage medium, technical measures, cross-border transfer | InfoSec assessment |
| 6 | New supplier (data processor) | Recipient/recipient group | Sign DPA, then add |
| 7 | Cross-border transfer started | Cross-border transfer, legal basis | Prepare KVKK Art. 9 legal basis |
| 8 | Transfer stopped | Recipient/recipient group | Remove from row; record rationale in version notes |
| 9 | Retention period change (legislative or internal policy) | Retention period, rationale | Align with destruction policy |
| 10 | Legislative change (Law, Regulation, Board decision) | Legal ground, retention period, transfer | Legal Department review |
| 11 | Organisational change (new/closed unit, role transfer) | Process owner, business unit | Update ownership |
| 12 | M&A (merger, acquisition, demerger) | All inventory | Full re-baseline — new controller / legacy records |
| 13 | Data breach detected | Technical measures, risk level | Breach assessment + remediation |
| 14 | New technical measure deployed | Technical measures | InfoSec update |
| 15 | A measure removed | Technical/administrative measures | Removal reason + compensating control |
| 16 | New legal obligation (e.g., new tax legislation, new sectoral rule) | Legal ground, retention period | Legal Department |
| 17 | Explicit-consent policy change | Explicit consent required, related consent text | CMP update |
| 18 | Information notice update | Information-notice reference | Version tracking |
| 19 | Gap discovered through a data subject request or Authority audit | Affected row(s) | Correction + internal notification |

### 2.2 Trigger → Update Chain

```
Event detected
    │
    ▼
Process Owner → KVKK Officer (ticket or e-mail, max 5 business days)
    │
    ▼
Inventory row draft update (KVKK Officer, 2 business days)
    │
    ▼
Legal Department confirmation (where required, max 3 business days)
    │
    ▼
Information Security confirmation (if technical measures involved, max 3 business days)
    │
    ▼
KVKK Committee acceptance (broad changes, where required)
    │
    ▼
Inventory v.X.Y release + change log
    │
    ▼
VERBİS update (Reg. Art. 13, 7 days) ← CRITICAL
    │
    ▼
Information notice / retention-destruction policy / contract alignment check
    │
    ▼
Notification to relevant stakeholders (process owner, training list)
```

### 2.3 Event Notification Template

Process owners notify the KVKK Officer using the following format:

```
INVENTORY UPDATE REQUEST
=========================================

Date:                YYYY-MM-DD
Process ID:          [e.g., HR-001]
Process Name:        [...]
Requested by:        [Name-Surname / Title]

Type of change:
[ ] New row
[ ] Existing row revision
[ ] Row archival (process discontinued)

Affected fields:
[ ] Data category       [ ] Personal data items
[ ] Processing purpose  [ ] Legal ground
[ ] Collection method   [ ] Storage medium
[ ] Domestic recipient  [ ] Cross-border transfer
[ ] Retention period    [ ] Destruction method
[ ] Technical measure   [ ] Administrative measure

Change description:
[Detailed text]

New state (old → new):
- Field: [...]  →  [...]

Impact analysis:
- Information notice update needed? [Y/N]
- Explicit consent needed? [Y/N]
- VERBİS notification affected? [Y/N]
- Contracts affected? [Y/N]

Proposed effective date: YYYY-MM-DD
```

## 3. Quarterly Review

### 3.1 Scope

Each quarter, **all inventory rows** pass through the following checks:

- [ ] Is the process owner still correct? (organisational change)
- [ ] Does the processing purpose match operational reality?
- [ ] Is the legal ground current?
- [ ] Have any new recipients been added?
- [ ] Cross-border transfer checkpoint: are SaaS server locations verified?
- [ ] Is the retention period aligned with legislation (any changes during the year)?
- [ ] Are technical measures current (new control added, control removed)?
- [ ] Is the risk level realistic?
- [ ] Is the information-notice reference correct and up to date?

### 3.2 Quarterly Review Meeting

Participants:
- KVKK Officer (chair)
- All Process Owners (per their rows)
- Legal Department representative
- Information Security representative
- KVKK Committee as observer

Duration: half a day (4-8 hours depending on scope).

Outputs:
- Quarterly review report
- Action list (owner + date)
- Version update

### 3.3 Quarterly Review Template

```
QUARTERLY INVENTORY REVIEW REPORT
==========================================

Quarter:           [QX YYYY]
Meeting Date:      YYYY-MM-DD
Participants:      [Names]

1. INVENTORY METRICS
   - Total rows                : [n]
   - New                       : [n]
   - Updated                   : [n]
   - Archived (discontinued)   : [n]
   - High/Critical-risk rows   : [n]

2. COMPLIANCE METRICS
   - VERBİS updated on time?   : [Y/N]
   - Information-notice align. : [%]
   - Retention-destruction     : [%]
   - Technical-measure align.  : [%]

3. OPEN ITEMS
   [ID] [Topic] [Owner] [Target Date]

4. DECISIONS
   [...]

5. NEXT MEETING
   Date: YYYY-MM-DD
```

## 4. Annual Full Revision

### 4.1 Scope

Once a year (ideally end of calendar year), the inventory is re-baselined **completely**:

| Step | Content |
|------|---------|
| 1 | All inventory rows re-validated by process owners |
| 2 | Sweep of legislative changes (Law, Regulation, Board decisions) |
| 3 | Review of sectoral guideline updates |
| 4 | Cross-alignment with information notices |
| 5 | Cross-alignment with retention-destruction policy |
| 6 | Alignment with contract stock (data processors, transfers) |
| 7 | Risk reassessment (especially special-category data) |
| 8 | Maturity-level measurement (1-5) |
| 9 | Annual improvement plan |

### 4.2 Annual Revision Output

- Version **MAJOR** incremented (e.g., v1.0 → v2.0)
- Annual evaluation report
- KVKK Committee approval
- Board of Directors summary
- Bulk VERBİS update (where needed)

## 5. Compliance Checklist (The Chain)

The inventory is the **central** document of KVKK compliance. The "compliance chain" below is continuously checked:

```
Inventory ↔ VERBİS notification ↔ Information notice ↔ Explicit consent text ↔ Retention-destruction policy ↔ Contracts
```

### 5.1 Inventory ↔ VERBİS

- [ ] Are inventory purposes present in VERBİS?
- [ ] Are VERBİS categories present in the inventory?
- [ ] Is cross-border transfer correctly notified in both?
- [ ] Are retention periods consistent?
- [ ] Did new processes reflect in VERBİS within 7 days (Reg. Art. 13)?

### 5.2 Inventory ↔ Information Notices

- [ ] Is there an information notice for each process (Disclosure Communiqué Art. 5/c)?
- [ ] Do purposes in the notice match the inventory?
- [ ] Does the legal ground in the notice match the inventory (Communiqué Art. 5/h)?
- [ ] Do recipient groups match the inventory (Communiqué Art. 5/ı)?
- [ ] Is cross-border information consistent?
- [ ] Is the collection method (automated/non-automated) consistent (Communiqué Art. 5/i)?

### 5.3 Inventory ↔ Explicit Consent Texts

- [ ] For all rows showing "explicit consent" in the inventory, is consent actually being collected?
- [ ] Is the consent collection channel (form, CMP, voice record) documented?
- [ ] Is there a consent withdrawal mechanism?
- [ ] Are there any rows showing "explicit consent" in the inventory where consent is not being taken? (There should be none.)

### 5.4 Inventory ↔ Retention and Destruction Policy

- [ ] Are retention periods consistent?
- [ ] Is the destruction method specified?
- [ ] Does periodic destruction occur within 6 months?
- [ ] Are destruction records archived?
- [ ] Have retention periods been refreshed after legislative changes?

### 5.5 Inventory ↔ Contracts

- [ ] Has a data-processor agreement been signed with each supplier?
- [ ] Are there transfer agreements (standard contract for cross-border)?
- [ ] Do contract purposes match the inventory?
- [ ] Have expired contracts been renewed?

## 6. Quarterly Cross-Check Matrix

| Control | Quarterly (Q1-Q4) | Annual | Triggered |
|---------|---|---|---|
| Inventory row validation | Y | Y | Y |
| VERBİS alignment | Y | Y | Y |
| Information-notice currency | Y | Y | Y |
| Retention-period legislative alignment | — | Y | Y |
| Contract stock currency | — | Y | Y (new supplier) |
| Risk assessment | — | Y | Y (new process, breach) |
| Maturity-level measurement | — | Y | — |

## 7. Ownership Model and RACI

| Activity | Process Owner | KVKK Officer | Legal | InfoSec | KVKK Committee | Board |
|----------|---|---|---|---|---|---|
| New process inventory row | R | A | C | C | I | I |
| Quarterly review | C | A/R | C | C | I | I |
| Annual revision | C | R | C | C | A | I |
| VERBİS update | I | A/R | C | I | I | I |
| Extraordinary (Authority audit, etc.) | C | R | A | C | A | I |
| M&A scope | C | A | C | C | C | A |

R = Responsible | A = Accountable | C = Consulted | I = Informed

## 8. Versioning Discipline

### 8.1 Version Number

Format: `MAJOR.MINOR.PATCH`
- **MAJOR:** Annual full revision, architectural change (new column, broad re-organisation)
- **MINOR:** Addition of a new process, meaningful row revision, alignment to new legislation
- **PATCH:** Spelling, formatting, link fixes

### 8.2 Change Log Template

A `degisiklik-kutugu.md` (change log) is kept alongside the inventory file:

```
| Version | Date | Type | Change | Prepared by | Approved by |
|---------|------|------|--------|-------------|-------------|
| 1.0.0   | 2026-05-08 | Initial release | Initial inventory publication | KVKK Officer | KVKK Committee |
| 1.1.0   | 2026-06-15 | MINOR | HR-011 (Internship Management) added | KVKK Officer | Head of Legal |
| 1.1.1   | 2026-06-22 | PATCH | HR-001 retention rationale clarified | KVKK Officer | KVKK Officer |
```

## 9. Operational Risk Indicators (KPI)

| KPI | Target | Warning threshold | Critical threshold |
|-----|--------|-------------------|--------------------|
| VERBİS update time | ≤ 5 days | > 5 days | > 7 days (regulatory breach) |
| Quarterly review completion | 100% | < 95% | < 85% |
| Process-owner-unsigned rows | 0 | > 0 | > 5 |
| Processes without information notice | 0 | > 0 | > 2 |
| Annual audit of high/critical-risk rows | 100% | < 100% | < 95% |
| Retention period non-compliance | 0 | > 0 | > 1 |

## 10. Annual Audit Preparation

The following package is prepared ahead of a KVKK Authority audit or internal audit:

| Document | Relevant article |
|----------|------------------|
| Current inventory (PDF + Excel) | Reg. Art. 4(h), 5(ç) |
| VERBİS notification PDF summary | Reg. Art. 10 |
| Retention and destruction policy | Erasure-Destruction Reg. Art. 5 |
| All information notices (per channel) | Disclosure Communiqué Art. 5 |
| Explicit consent texts and sample logs | KVKK Art. 5(1), Art. 6(2) |
| Data-processor contract stock | KVKK Art. 12(2) |
| Cross-border transfer agreements / standard contracts | KVKK Art. 9 |
| Quarterly review reports | Internal document |
| Data-breach notification records (if any) | KVKK Art. 12(5) |
| Data subject application and response logs | KVKK Art. 13, Application Communiqué |
| Training and awareness records | KVKK Art. 12(1) administrative measure |

## 11. Checklist — Has the Maintenance Routine Been Established?

- [ ] Quarterly review calendar set (Q1-Q4 dates)
- [ ] Annual full revision date set
- [ ] Event-notification ticketing (JIRA, ServiceNow, etc.) set up
- [ ] Process owners trained
- [ ] KVKK Committee agenda defined
- [ ] VERBİS update responsibility clarified
- [ ] Versioning discipline documented
- [ ] KPI measurement method defined
- [ ] Document set ready for annual audit
- [ ] Legislative-tracking channel set up (KVKK bulletins, Official Gazette)

## 12. Annexes

- Inventory Guide: [kvki-envanteri-rehberi.md](./kvki-envanteri-rehberi.md)
- Template: [envanter-sablonu.md](./envanter-sablonu.md)
- VERBİS Registration: [verbis-kayit-rehberi.md](./verbis-kayit-rehberi.md)
- Exception Assessment: [verbis-istisna-degerlendirmesi.md](./verbis-istisna-degerlendirmesi.md)

---

## Türkçe

# Envanter Bakımı, Gözden Geçirme ve Değişiklik Yönetimi

Envanter bir kez yapılıp bırakılan bir doküman değildir. Yön. M.5/d uyarınca aydınlatma yükümlülüğü, ilgili kişi başvurularının cevaplanması ve açık rızanın belirlenmesinde envantere dayalı Sicil bilgileri **esas alınır**. Bu nedenle envanter güncel kalmadığında **bir bütün uyum mimarisi yanlışlaşır**.

Bu doküman, envanterin nasıl güncel tutulacağına ilişkin operasyonel rejimi tanımlar.

## 1. Üç Katmanlı Bakım Modeli

| Katman | Sıklık | Amaç |
|--------|--------|------|
| Sürekli (event-driven) | Anlık | Süreç değişikliği olur olmaz envanter güncellenir; VERBİS bildirimi 7 gün içinde |
| Çeyreklik gözden geçirme | 3 ayda bir | Süreç sahipleri ve KVKK Sorumlusu satır bazlı doğrulama |
| Yıllık tam revizyon | Yılda bir | Tüm envanterin baştan tamamı, mevzuat ve organizasyon değişiklikleriyle uyumlandırma |

## 2. Sürekli Bakım — Olay Tabanlı

### 2.1 Değişiklik Tetikleyicileri

Aşağıdaki olayların **herhangi biri** envanteri günceller:

| # | Tetikleyici | Etkilenen alan | Aksiyon |
|---|-------------|----------------|---------|
| 1 | Yeni süreç başlatılması | Yeni satır ekleme | Süreç başlamadan envanter satırı + VERBİS güncelleme |
| 2 | Mevcut süreçte yeni amaç eklenmesi | İşleme amacı, hukuki sebep | Hukuk Müdürlüğü teyidi → güncelleme |
| 3 | Yeni veri kategorisi işlenmeye başlanması | Veri kategorisi, kişisel veri öğeleri | Aydınlatma metni de güncellenir |
| 4 | Yeni kişi grubu (örn. ilk kez ziyaretçi izleme başlatma) | Veri konusu kişi grubu | Aydınlatma metni + tabela hazırlığı |
| 5 | Yeni sistem/SaaS devreye alma | Kayıt ortamı, teknik tedbirler, yurt dışı aktarım | Bilgi Güvenliği değerlendirmesi |
| 6 | Yeni tedarikçi (veri işleyen) | Alıcı/alıcı grubu | Veri işleyen sözleşmesi imzala, sonra ekle |
| 7 | Yurt dışı aktarımın başlatılması | Yurt dışı aktarım, hukuki temel | KVKK m.9 hukuki temel hazırlığı |
| 8 | Bir aktarımın durdurulması | Alıcı/alıcı grubu | İlgili satırdan çıkar; gerekçeyi versiyon notuna yaz |
| 9 | Saklama süresi değişimi (mevzuat veya iç politika) | Saklama süresi, gerekçe | İmha politikası ile uyumlandır |
| 10 | Mevzuat değişikliği (kanun, yönetmelik, Kurul kararı) | Hukuki sebep, saklama süresi, aktarım | Hukuk Müdürlüğü gözden geçirir |
| 11 | Organizasyon değişikliği (birim oluşturma/kapatma, görev devri) | Süreç sahibi, iş birimi | Sahiplik güncellemesi |
| 12 | M&A (birleşme, devralma, bölünme) | Tüm envanter | Tam revizyon — yeni veri sorumlusu/eski kayıtlar |
| 13 | Veri ihlali tespiti | Teknik tedbirler, risk seviyesi | İhlal değerlendirme + iyileştirme |
| 14 | Yeni teknik tedbir devreye alma | Teknik tedbirler | Bilgi Güvenliği güncelleme |
| 15 | Bir tedbirin kaldırılması | Teknik/idari tedbirler | Kalkma sebebi + telafi tedbiri |
| 16 | Yeni hukuki yükümlülük (örn. yeni vergi mevzuatı, yeni sektörel düzenleme) | Hukuki sebep, saklama süresi | Hukuk Müdürlüğü |
| 17 | Açık rıza politikası değişikliği | Açık rıza gerekli mi, ilgili rıza metni | CMP güncelleme |
| 18 | Aydınlatma metni güncellemesi | Aydınlatma metni atfı | Versiyon takibi |
| 19 | İlgili kişi başvurusu ya da Kurul incelemesi sonucu çıkan eksiklik | İlgili satır(lar) | Düzeltme + iç bildirim |

### 2.2 Tetikleyici → Güncelleme Zinciri

```
Olay tespiti
    │
    ▼
Süreç Sahibi → KVKK Sorumlusu (ticket veya e-posta, max 5 iş günü)
    │
    ▼
Envanter satırı taslak güncelleme (KVKK Sorumlusu, 2 iş günü)
    │
    ▼
Hukuk Müdürlüğü teyidi (gerektiği takdirde, max 3 iş günü)
    │
    ▼
Bilgi Güvenliği teyidi (teknik tedbir varsa, max 3 iş günü)
    │
    ▼
KVKK Komitesi kabulü (kapsamlı değişiklikler, gerektiğinde)
    │
    ▼
Envanter v.X.Y yayını + değişiklik logu
    │
    ▼
VERBİS güncellemesi (Yön. M.13, 7 gün) ← KRİTİK
    │
    ▼
Aydınlatma metni / saklama-imha politikası / sözleşme uyum kontrolü
    │
    ▼
İlgili paydaşlara bildirim (süreç sahibi, eğitim listesi)
```

### 2.3 Olay Bildirim Şablonu

Süreç sahipleri aşağıdaki formatta KVKK Sorumlusu'na bildirim yapar:

```
ENVANTER GÜNCELLEME TALEBİ
=========================================

Tarih:                YYYY-AA-GG
Süreç ID:             [örn. IK-001]
Süreç Adı:            [...]
Talep Eden:           [Ad-Soyad / Görev]

Değişiklik Türü:
[ ] Yeni satır
[ ] Mevcut satır revizyonu
[ ] Satır arşivleme (süreç durduruldu)

Etkilenen Alanlar:
[ ] Veri kategorisi      [ ] Kişisel veri öğeleri
[ ] İşleme amacı         [ ] Hukuki sebep
[ ] Toplama yöntemi      [ ] Kayıt ortamı
[ ] Yurt içi alıcı       [ ] Yurt dışı aktarım
[ ] Saklama süresi       [ ] İmha yöntemi
[ ] Teknik tedbir        [ ] İdari tedbir

Değişiklik Açıklaması:
[Detaylı metin]

Yeni Durum (eski → yeni):
- Alan: [...]  →  [...]

Etki Analizi:
- Aydınlatma metni güncellenecek mi? [E/H]
- Açık rıza gerekecek mi? [E/H]
- VERBİS bildirimi etkilenecek mi? [E/H]
- Sözleşmeler etkilenecek mi? [E/H]

Önerilen Yürürlük Tarihi: YYYY-AA-GG
```

## 3. Çeyreklik Gözden Geçirme

### 3.1 Kapsam

Her çeyrekte **tüm envanter** satırları aşağıdaki kontrollerden geçer:

- [ ] Süreç sahibi hâlâ doğru mu? (organizasyon değişikliği)
- [ ] İşleme amacı operasyonel gerçeklikle örtüşüyor mu?
- [ ] Hukuki sebep güncel mi?
- [ ] Yeni alıcılar eklendi mi?
- [ ] Yurt dışı aktarım kontrol noktası: SaaS sunucu lokasyonları doğrulandı mı?
- [ ] Saklama süresi mevzuatla uyumlu mu (yıl içi mevzuat değişikliği)?
- [ ] Teknik tedbirler güncel mi (yeni güvenlik kontrolü, kaldırılan kontrol)?
- [ ] Risk seviyesi gerçekçi mi?
- [ ] Aydınlatma metnine atıf doğru ve güncel mi?

### 3.2 Çeyreklik Gözden Geçirme Toplantısı

Katılımcılar:
- KVKK Sorumlusu (toplantı sahibi)
- Tüm Süreç Sahipleri (kendi satırlarına göre)
- Hukuk Müdürlüğü temsilcisi
- Bilgi Güvenliği temsilcisi
- KVKK Komitesi gözlemci sıfatıyla

Süre: Yarım gün (kapsama göre 4-8 saat).

Çıktılar:
- Çeyreklik gözden geçirme raporu
- Eylem listesi (sahip + tarih)
- Versiyon güncellemesi

### 3.3 Çeyreklik Gözden Geçirme Şablonu

```
ÇEYREKLİK ENVANTER GÖZDEN GEÇİRME RAPORU
==========================================

Çeyrek:               [QX YYYY]
Toplantı Tarihi:      YYYY-AA-GG
Katılımcılar:         [İsimler]

1. ENVANTER METRİKLERİ
   - Toplam satır sayısı           : [n]
   - Yeni eklenen                  : [n]
   - Güncellenen                   : [n]
   - Arşivlenen (durdurulan süreç) : [n]
   - Yüksek/Kritik risk satırlar   : [n]

2. UYUM METRİKLERİ
   - VERBİS güncellenme zamanında mı? : [E/H]
   - Aydınlatma uyumu              : [%]
   - Saklama-imha uyumu            : [%]
   - Teknik tedbir uyumu           : [%]

3. AÇIK KONULAR
   [ID] [Konu] [Sahip] [Hedef Tarih]

4. KARAR LİSTESİ
   [...]

5. SONRAKİ TOPLANTI
   Tarih: YYYY-AA-GG
```

## 4. Yıllık Tam Revizyon

### 4.1 Kapsam

Yılda bir kez (ideal: takvim yılı sonu) envanter **tamamen** baştan ele alınır:

| Adım | İçerik |
|------|--------|
| 1 | Tüm envanter satırlarının süreç sahiplerine yeniden onayı |
| 2 | Mevzuat değişiklikleri taraması (Kanun, Yönetmelik, Kurul kararları) |
| 3 | Sektörel rehber güncellemelerinin değerlendirilmesi |
| 4 | Aydınlatma metinleri ile karşılıklı uyum |
| 5 | Saklama-imha politikası ile karşılıklı uyum |
| 6 | Sözleşme stoğu (veri işleyen, aktarım) ile uyum |
| 7 | Risk değerlendirmesi (özellikle özel nitelikli veri) |
| 8 | Olgunluk seviyesi ölçümü (1-5 arası) |
| 9 | Yıllık iyileştirme planı |

### 4.2 Yıllık Revizyon Çıktısı

- Versiyon **MAJOR** artırılır (örn. v1.0 → v2.0)
- Yıllık değerlendirme raporu
- KVKK Komitesi onayı
- Yönetim Kurulu özeti
- VERBİS toplu güncelleme (gerekirse)

## 5. Uyum Kontrol Listesi (Zincir)

Envanter, KVKK uyumunun **merkezi** dokümanıdır. Aşağıdaki "uyum zinciri" sürekli kontrol edilir:

```
Envanter ↔ VERBİS bildirimi ↔ Aydınlatma metni ↔ Açık rıza metni ↔ Saklama-imha politikası ↔ Sözleşmeler
```

### 5.1 Envanter ↔ VERBİS

- [ ] Envanterdeki amaçlar VERBİS'te yer alıyor mu?
- [ ] VERBİS'teki kategoriler envanterde de var mı?
- [ ] Yurt dışı aktarım her iki yerde de doğru bildirilmiş mi?
- [ ] Saklama süreleri tutarlı mı?
- [ ] Yeni süreçler 7 gün içinde VERBİS'e yansıdı mı (Yön. M.13)?

### 5.2 Envanter ↔ Aydınlatma Metinleri

- [ ] Her süreç için aydınlatma metni var mı (Aydınlatma Tebliği M.5/c)?
- [ ] Aydınlatma metnindeki amaçlar envanterdeki amaçlarla aynı mı?
- [ ] Aydınlatma metnindeki hukuki sebep envanterle aynı mı (Tebliğ M.5/h)?
- [ ] Aydınlatma metnindeki alıcı grupları envanterle aynı mı (Tebliğ M.5/ı)?
- [ ] Yurt dışı aktarım bilgisi tutarlı mı?
- [ ] Toplama yöntemi (otomatik/otomatik olmayan) tutarlı mı (Tebliğ M.5/i)?

### 5.3 Envanter ↔ Açık Rıza Metinleri

- [ ] Envanterde "açık rıza" gösterilen tüm satırlarda gerçekten rıza alınıyor mu?
- [ ] Rıza alma kanalı (form, CMP, sözlü kayıt) belgelendi mi?
- [ ] Rıza geri alma mekanizması var mı?
- [ ] Rıza alınmamış olduğu halde envanterde "açık rıza" gösterilen var mı? (yok olmalı)

### 5.4 Envanter ↔ Saklama ve İmha Politikası

- [ ] Saklama süreleri tutarlı mı?
- [ ] İmha yöntemi belirtilmiş mi?
- [ ] Periyodik imha 6 ay içinde gerçekleşiyor mu?
- [ ] İmha tutanakları arşivde mi?
- [ ] Mevzuat değişikliği sonrası saklama süresi yenilendi mi?

### 5.5 Envanter ↔ Sözleşmeler

- [ ] Veri işleyen sözleşmesi her tedarikçi için imzalandı mı?
- [ ] Aktarım sözleşmeleri (yurt dışı için standart sözleşme) var mı?
- [ ] Sözleşmedeki amaçlar envanterle örtüşüyor mu?
- [ ] Sözleşme süresi sona erdiyse yenilendi mi?

## 6. Çeyreklik Çapraz Kontrol Matrisi

| Kontrol | Çeyreklik (Q1-Q4) | Yıllık | Tetiklenmiş |
|---------|---|---|---|
| Envanter satır doğrulaması | E | E | E |
| VERBİS uyum | E | E | E |
| Aydınlatma metni güncellik | E | E | E |
| Saklama süresi mevzuat uyumu | — | E | E |
| Sözleşme stoğu güncelliği | — | E | E (yeni tedarikçide) |
| Risk değerlendirmesi | — | E | E (yeni süreç, ihlal) |
| Olgunluk seviyesi ölçümü | — | E | — |

## 7. Sahiplik Modeli ve RACI

| Aktivite | Süreç Sahibi | KVKK Sorumlusu | Hukuk | Bilgi Güvenliği | KVKK Komitesi | Yönetim Kurulu |
|----------|---|---|---|---|---|---|
| Yeni süreç envanter satırı | R | A | C | C | I | I |
| Çeyreklik gözden geçirme | C | A/R | C | C | I | I |
| Yıllık revizyon | C | R | C | C | A | I |
| VERBİS güncellemesi | I | A/R | C | I | I | I |
| Olağan dışı (Kurul incelemesi vb.) | C | R | A | C | A | I |
| M&A kapsamı | C | A | C | C | C | A |

R = Responsible | A = Accountable | C = Consulted | I = Informed

## 8. Versiyonlama Disiplini

### 8.1 Versiyon Numarası

Format: `MAJOR.MINOR.PATCH`
- **MAJOR:** Yıllık tam revizyon, mimari değişiklik (yeni kolon, kapsamlı yeniden düzenleme)
- **MINOR:** Yeni süreç eklemesi, mevcut satırın anlamlı revizyonu, yeni mevzuat uyarlaması
- **PATCH:** Yazım, format, bağlantı düzeltmesi

### 8.2 Değişiklik Kütüğü Şablonu

Envanter dosyasının yanında `degisiklik-kutugu.md` tutulur:

```
| Versiyon | Tarih | Tip | Değişiklik | Hazırlayan | Onaylayan |
|----------|-------|-----|-----------|-----------|-----------|
| 1.0.0    | 2026-05-08 | İlk yayım | İlk envanter yayını | KVKK Sor. | KVKK Komitesi |
| 1.1.0    | 2026-06-15 | MINOR | IK-011 (Stajyer Yönetimi) eklendi | KVKK Sor. | Hukuk Müd. |
| 1.1.1    | 2026-06-22 | PATCH | IK-001 saklama gerekçesi netleştirildi | KVKK Sor. | KVKK Sor. |
```

## 9. Operasyonel Risk Göstergeleri (KPI)

| KPI | Hedef | Uyarı eşiği | Kritik eşik |
|-----|-------|-------------|-------------|
| VERBİS güncelleme süresi | ≤ 5 gün | > 5 gün | > 7 gün (mevzuat ihlali) |
| Çeyreklik gözden geçirme tamamlanma | %100 | < %95 | < %85 |
| Süreç sahibi onaylanmamış satır | 0 | > 0 | > 5 |
| Aydınlatma metni eksik süreç | 0 | > 0 | > 2 |
| Yüksek/Kritik risk satırları için yıllık denetim | %100 | < %100 | < %95 |
| Saklama süresi mevzuat uyumsuzluğu | 0 | > 0 | > 1 |

## 10. Yıllık Denetim Hazırlığı

KVKK Kurul incelemesi veya iç denetim öncesi şu paket hazırlanır:

| Doküman | İlgili madde |
|---------|-------------|
| Güncel envanter (PDF + Excel) | Yön. M.4(h), 5(ç) |
| VERBİS bildirim PDF özeti | Yön. M.10 |
| Saklama ve imha politikası | Saklama ve İmha Yön. M.5 |
| Tüm aydınlatma metinleri (kanal bazında) | Aydınlatma Tebliği M.5 |
| Açık rıza metinleri ve örnek logları | KVKK m.5/1, m.6/2 |
| Veri işleyen sözleşme stoğu | KVKK m.12/2 |
| Yurt dışı aktarım sözleşmeleri / standart sözleşme | KVKK m.9 |
| Çeyreklik gözden geçirme raporları | İç doküman |
| Veri ihlali bildirim kayıtları (varsa) | KVKK m.12/5 |
| İlgili kişi başvuru ve cevap kayıtları | KVKK m.13, Başvuru Tebliği |
| Eğitim ve farkındalık kayıtları | KVKK m.12/1 idari tedbir |

## 11. Kontrol Listesi — Bakım Düzeni Kuruldu mu?

- [ ] Çeyreklik gözden geçirme takvimi kuruldu (Q1-Q4 tarihler)
- [ ] Yıllık tam revizyon ay-tarihi belirlendi
- [ ] Olay bildirim ticket sistemi (JIRA, ServiceNow vb.) kuruldu
- [ ] Süreç sahipleri eğitildi
- [ ] KVKK Komitesi gündemi tanımlandı
- [ ] VERBİS güncelleme sorumluluğu netleştirildi
- [ ] Versiyonlama disiplini belgelendi
- [ ] KPI ölçüm yöntemi tanımlı
- [ ] Yıllık denetim için doküman seti hazır
- [ ] Mevzuat takip kanalı kuruldu (KVKK Kurum bültenleri, Resmi Gazete)

## 12. Ekler

- Envanter Rehberi: [kvki-envanteri-rehberi.md](./kvki-envanteri-rehberi.md)
- Şablon: [envanter-sablonu.md](./envanter-sablonu.md)
- VERBİS Kayıt: [verbis-kayit-rehberi.md](./verbis-kayit-rehberi.md)
- İstisna Değerlendirme: [verbis-istisna-degerlendirmesi.md](./verbis-istisna-degerlendirmesi.md)
