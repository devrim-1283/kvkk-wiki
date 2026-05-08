---
title: "ROPA Maintenance — Review Cycles, Change Triggers, Cross-Checks"
title_tr: "ROPA Bakımı — İnceleme Döngüleri, Değişiklik Tetikleyicileri, Çapraz Kontroller"
section: "02-ropa"
language: ["en", "tr"]
status: "approved"
version: "2.2.0"
last_review: "2026-04-15"
next_review: "2026-10-15"
owner: "Data Protection Officer"
classification: "Internal"
related_articles: ["GDPR Art. 5(2)", "GDPR Art. 24", "GDPR Art. 30", "GDPR Art. 32", "GDPR Art. 33", "GDPR Art. 35"]
related_guidelines: ["EDPB Position Paper April 2018", "ICO Records of Processing Activities Guidance"]
tags: ["ropa", "maintenance", "lifecycle", "change-management"]
---

## English

### 1. Why Maintenance Matters

A ROPA created once and ignored is worse than no ROPA at all: it creates the illusion of compliance while documenting an outdated reality. Article 30 imposes an ongoing obligation to keep records up to date. The reasonable test is whether, on the day a supervisory authority arrives, the ROPA reflects the **current** state of processing. This document defines the maintenance regime that achieves that.

### 2. Review Cadence

#### 2.1 Quarterly Review (Standard)

Each ROPA entry is reviewed by its named process owner every quarter. The DPO rotates through entries to ensure each is independently spot-checked at least annually.

Quarterly review steps:

1. Process owner re-reads the entry and ticks each field as still accurate, changed, or unknown.
2. Process owner confirms vendor list (Column 18) is unchanged or supplies the change.
3. Process owner confirms retention period (Column 22) still aligns with the retention schedule.
4. Process owner confirms IT systems (Column 28) are unchanged or supplies the change.
5. Process owner updates Last Reviewed (Column 32) and the change-log notes (Column 34).
6. DPO reviews the diff and either accepts or queries.

#### 2.2 Annual Comprehensive Review

Once a year, every entry is reviewed top-to-bottom by the DPO with the process owner present. The annual review:

- Re-tests the lawful basis selection.
- Re-runs the legitimate-interest balancing test (where Art. 6(1)(f) is cited).
- Re-validates the Article 9 condition.
- Reviews the proportionality and necessity of the processing.
- Confirms cross-references against privacy notice, retention schedule, DPIA register, and TOM register.
- Captures lessons learned from any incidents (breaches, DSAR escalations, complaints).

#### 2.3 Cross-Check Calendar

| Check | Frequency | Owner |
|-------|-----------|-------|
| ROPA vs. privacy notice | Quarterly | DPO |
| ROPA vs. retention schedule | Quarterly | DPO + Records Manager |
| ROPA vs. TOM register | Semi-annual | DPO + CISO |
| ROPA vs. DPIA register | Semi-annual | DPO |
| ROPA vs. vendor / DPA list | Quarterly | DPO + Procurement |
| ROPA vs. third-country transfer mapping | Quarterly | DPO |
| ROPA vs. cookie / consent banner | Semi-annual | DPO + Marketing Ops |

### 3. Change Triggers

A ROPA entry must be updated **immediately** (not at the next quarterly review) when any of the following occurs:

#### 3.1 New System Onboarding

Trigger: any new SaaS subscription, on-premises system, or significant feature release that processes personal data.

Action: prior to go-live, a new ROPA entry (or a delta to an existing entry) is created and approved by the DPO. Procurement and IT change-management workflows must include a "ROPA created or updated?" checkbox before approval.

#### 3.2 New or Replaced Vendor

Trigger: any new processor or sub-processor; replacement of an existing vendor; material change to a vendor's processing scope.

Action: update Columns 18, 19, 20, 21, 31. Re-execute or re-validate the DPA. If the new vendor is in a third country, update transfer mapping and run a Transfer Impact Assessment (TIA).

#### 3.3 Merger, Acquisition, Divestiture, or Joint Venture

Trigger: any corporate transaction that changes legal-entity boundaries.

Action: within 30 days of closing, the ROPA is reviewed for:

- New entries inherited from the acquired entity.
- Joint-controllership analysis under Art. 26.
- Vendor consolidation (often the highest-risk area for compliance drift).
- Transfer mapping changes (new global affiliates).
- Privacy notice harmonisation.

For divestitures, identify entries that **leave** the ROPA (transferred to the divested entity) and update accordingly.

#### 3.4 New Purpose for Existing Data

Trigger: an existing dataset is repurposed (e.g., customer support logs being used for product analytics).

Action: this is a "further processing" scenario under Article 6(4). Run the compatibility test and either rely on a fresh lawful basis (often consent), or stop the new use. Update the ROPA with a new entry or expand the existing entry's purposes.

#### 3.5 New Data Category

Trigger: collection begins of a category not previously processed (e.g., a new biometric authentication method).

Action: update Columns 11, 12, 14, 16, and—almost always—run a DPIA before deployment.

#### 3.6 New Recipient or Transfer

Trigger: data is shared with a recipient not previously listed.

Action: update Columns 18 and, if cross-border, 20–21. Verify lawful basis and DPA. For new third-country transfers, run TIA.

#### 3.7 Retention Change

Trigger: legal change (e.g., new tax retention period); business change (e.g., shorter customer-record retention chosen).

Action: update Column 22; ensure the retention schedule is updated in the same PR/commit.

#### 3.8 Change in Lawful Basis

Trigger: rare, but happens (e.g., relying on consent and switching to legitimate interest after a service redesign).

Action: highest-care change. Update Column 10. Update the privacy notice and notify data subjects where the change is material under Article 13(3).

#### 3.9 Breach

Trigger: a confirmed personal data breach affecting any system or process listed in the ROPA.

Action: ROPA is the first lookup during breach assessment. After the breach is closed, review the entry for control failures and update Columns 24, 25, 26 (TOMs and DPIA).

#### 3.10 Regulatory Change

Trigger: change in GDPR enforcement guidance, EDPB guideline update, or Member State law change that materially affects an entry.

Action: DPO assesses impact, updates affected entries, and logs the regulatory driver in Column 34.

### 4. Ownership and Escalation

#### 4.1 Owners

| Role | Responsibility |
|------|----------------|
| Process owner | First line of defence. Owns content of the entry. |
| Department head | Approves first-line content; signs off on change. |
| DPO | Second line of defence. Approves lawful basis, transfers, special-category treatment. |
| Legal | Approves contractual implications (DPAs, joint-controller arrangements, transfer instruments). |
| CISO / CTO | Approves TOM-related entries (Columns 24–25, 28). |
| Internal Audit | Independent third line. Tests the regime annually. |
| Records Manager | Maintains retention-schedule alignment. |

#### 4.2 Escalation Triggers

| Issue | Escalate To | Within |
|-------|-------------|--------|
| Process owner cannot identify lawful basis | DPO | 5 working days |
| Vendor refuses to sign updated DPA | Procurement + Legal | 5 working days |
| Discovered shadow-IT processing | DPO | Same day |
| Discovered third-country transfer without safeguard | DPO | Same day; suspend transfer pending review |
| Breach suspected during review | Breach Manager | Immediately under Art. 33 timer |
| DPIA threshold reached during review | DPO | 5 working days; pause new feature if pre-launch |

### 5. Quality Metrics

Reportable to the Privacy Steering Committee monthly:

- Number of ROPA entries.
- Percentage of entries reviewed in the last quarter.
- Percentage of entries with a process owner with active employment status.
- Number of ROPA changes triggered by change category (new system, vendor, M&A, etc.).
- Average age of "Last Reviewed" date.
- Outstanding actions from the last DPO walk-through, by age.
- Number of supervisory authority responses served from the ROPA in the period.

### 6. Tooling and Audit Trail

Whatever the storage tool, every change must produce an audit trail showing:

- Who changed what, when.
- Who approved.
- The before/after value of changed fields.
- The triggering event (link to ticket, DPIA, vendor change, M&A close).

For wiki-style storage, this is enforced by version control (git history). For GRC tooling, the equivalent change-history feature must be enabled and immutable.

### 7. Decommissioning Entries

When a processing activity ceases:

1. The entry is **not deleted**. It is marked status = "Decommissioned" with an end date.
2. The entry remains accessible until the longest applicable retention period has elapsed plus a safety margin.
3. The entry is referenced in the ROPA's index as historical to maintain accountability for past processing.

### 8. Sample Quarterly Review Email Template

> Subject: ROPA Quarterly Review — Q\_, Entry \[Entry ID\]
>
> Dear \[Process Owner\],
>
> Please review the attached ROPA entry by \[deadline\].
>
> 1. Re-read each field. Tick "OK," "Updated," or "Unknown."
> 2. Confirm the IT systems list reflects what is in production.
> 3. Confirm the vendor and sub-processor list is current.
> 4. Confirm the retention period is still applied in practice.
> 5. Note any changes in field 34 with date and your initials.
>
> Reply to this email with the updated entry (or a "no change" confirmation) by \[deadline\]. Late submissions will be escalated to your department head.
>
> Best,
> Office of the DPO

---

## Türkçe

### 1. Bakım Neden Önemlidir

Bir kez oluşturulup göz ardı edilen bir ROPA, hiç ROPA olmamasından daha kötüdür: güncel olmayan bir gerçeği belgelerken uyumluluk yanılsaması yaratır. Madde 30, kayıtların güncel tutulmasına ilişkin sürekli bir yükümlülük getirir. Makul test, bir denetim otoritesinin geldiği gün ROPA'nın işlemenin **mevcut** durumunu yansıtıp yansıtmadığıdır. Bu belge, bunu sağlayan bakım rejimini tanımlar.

### 2. İnceleme Sıklığı

#### 2.1 Üç Aylık İnceleme (Standart)

Her ROPA girişi, adı geçen süreç sahibi tarafından her üç ayda bir incelenir. DPO, her girişin yılda en az bir kez bağımsız olarak nokta kontrolden geçmesini sağlamak için girişler arasında dönüşümlü inceleme yapar.

Üç aylık inceleme adımları:

1. Süreç sahibi girişi yeniden okur ve her alanı hâlâ doğru, değişmiş veya bilinmiyor olarak işaretler.
2. Süreç sahibi tedarikçi listesinin (Sütun 18) değişmediğini onaylar veya değişikliği sağlar.
3. Süreç sahibi saklama süresinin (Sütun 22) hâlâ saklama planıyla uyumlu olduğunu onaylar.
4. Süreç sahibi BT sistemlerinin (Sütun 28) değişmediğini onaylar veya değişikliği sağlar.
5. Süreç sahibi Son İnceleme (Sütun 32) ve değişiklik kaydını (Sütun 34) günceller.
6. DPO farkı inceler ve kabul eder veya sorgular.

#### 2.2 Yıllık Kapsamlı İnceleme

Yılda bir kez, süreç sahibinin katılımıyla DPO her girişi baştan sona inceler. Yıllık inceleme:

- Hukuki sebep seçimini yeniden test eder.
- Madde 6(1)(f) gerekçesi varsa meşru menfaat dengeleme testini yeniden çalıştırır.
- Madde 9 koşulunu yeniden doğrular.
- İşlemenin orantılılığını ve gerekliliğini gözden geçirir.
- Gizlilik bildirimi, saklama planı, DPIA sicili ve TOM siciliyle çapraz referansları onaylar.
- Olaylardan (ihlaller, DSAR eskalasyonları, şikayetler) çıkarılan dersleri yakalar.

#### 2.3 Çapraz Kontrol Takvimi

| Kontrol | Sıklık | Sahip |
|---------|--------|-------|
| ROPA vs. gizlilik bildirimi | Üç aylık | DPO |
| ROPA vs. saklama planı | Üç aylık | DPO + Kayıt Yöneticisi |
| ROPA vs. TOM sicili | Altı aylık | DPO + CISO |
| ROPA vs. DPIA sicili | Altı aylık | DPO |
| ROPA vs. tedarikçi / DPA listesi | Üç aylık | DPO + Satınalma |
| ROPA vs. üçüncü ülke aktarım haritası | Üç aylık | DPO |
| ROPA vs. çerez / onay banner'ı | Altı aylık | DPO + Pazarlama Ops |

### 3. Değişiklik Tetikleyicileri

Bir ROPA girişi aşağıdaki durumlardan herhangi biri gerçekleştiğinde **derhal** (sonraki üç aylık incelemede değil) güncellenmelidir:

#### 3.1 Yeni Sistem Entegrasyonu

Tetikleyici: kişisel veri işleyen herhangi bir yeni SaaS aboneliği, yerinde sistem veya önemli özellik sürümü.

Eylem: canlıya almadan önce yeni bir ROPA girişi (veya mevcut girişe delta) oluşturulur ve DPO tarafından onaylanır. Satınalma ve BT değişiklik yönetim iş akışlarında onay öncesi "ROPA oluşturuldu mu veya güncellendi mi?" kutusu bulunmalıdır.

#### 3.2 Yeni veya Değişen Tedarikçi

Tetikleyici: herhangi bir yeni veri işleyen veya alt işleyen; mevcut tedarikçinin değiştirilmesi; bir tedarikçinin işleme kapsamında önemli değişiklik.

Eylem: Sütun 18, 19, 20, 21, 31'i güncelleyin. DPA'yı yeniden imzalayın veya doğrulayın. Yeni tedarikçi üçüncü bir ülkedeyse, aktarım haritasını güncelleyin ve Aktarım Etki Değerlendirmesi (TIA) yapın.

#### 3.3 Birleşme, Devralma, Ayrılma veya Ortak Girişim

Tetikleyici: tüzel kişi sınırlarını değiştiren herhangi bir kurumsal işlem.

Eylem: kapanıştan sonraki 30 gün içinde ROPA şunlar için incelenir:

- Devralınan tüzel kişiden devralınan yeni girişler.
- Madde 26 kapsamında ortak veri sorumluluğu analizi.
- Tedarikçi konsolidasyonu (uyumluluk kayması için en yüksek riskli alan).
- Aktarım haritalama değişiklikleri (yeni global iştirakler).
- Gizlilik bildirimi uyumlulaştırması.

Ayrılmalar için ROPA'dan **çıkan** girişleri (ayrılan tüzel kişiye aktarılan) belirleyin ve buna göre güncelleyin.

#### 3.4 Mevcut Veri İçin Yeni Amaç

Tetikleyici: mevcut bir veri kümesi yeni bir amaç için kullanılır (örneğin müşteri destek loglarının ürün analitiği için kullanılması).

Eylem: bu, Madde 6(4) kapsamında "ileri işleme" senaryosudur. Uyumluluk testini yapın ve ya yeni bir hukuki sebebe dayanın (genellikle onay) ya da yeni kullanımı durdurun. ROPA'yı yeni bir giriş veya mevcut girişin amaçlarını genişleterek güncelleyin.

#### 3.5 Yeni Veri Kategorisi

Tetikleyici: daha önce işlenmemiş bir kategorinin toplanmasının başlaması (örneğin yeni bir biyometrik kimlik doğrulama yöntemi).

Eylem: Sütun 11, 12, 14, 16'yı güncelleyin ve—neredeyse her zaman—dağıtımdan önce DPIA yapın.

#### 3.6 Yeni Alıcı veya Aktarım

Tetikleyici: daha önce listelenmemiş bir alıcıyla veri paylaşımı.

Eylem: Sütun 18'i ve sınır ötesiyse 20–21'i güncelleyin. Hukuki sebebi ve DPA'yı doğrulayın. Yeni üçüncü ülke aktarımları için TIA çalıştırın.

#### 3.7 Saklama Süresi Değişikliği

Tetikleyici: yasal değişiklik (örneğin yeni vergi saklama süresi); iş değişikliği (örneğin daha kısa müşteri kayıt saklama).

Eylem: Sütun 22'yi güncelleyin; saklama planının aynı PR/commit'te güncellendiğinden emin olun.

#### 3.8 Hukuki Sebepte Değişiklik

Tetikleyici: nadir, ancak olur (örneğin onaya dayanırken hizmet yeniden tasarımı sonrası meşru menfaate geçmek).

Eylem: en yüksek özen gerektiren değişiklik. Sütun 10'u güncelleyin. Gizlilik bildirimini güncelleyin ve değişiklik Madde 13(3) kapsamında önemliyse ilgili kişileri bilgilendirin.

#### 3.9 İhlal

Tetikleyici: ROPA'da listelenen herhangi bir sistemi veya süreci etkileyen onaylanmış bir kişisel veri ihlali.

Eylem: ROPA, ihlal değerlendirmesi sırasında ilk başvurudur. İhlal kapatıldıktan sonra, kontrol başarısızlıkları için girişi inceleyin ve Sütun 24, 25, 26'yı (TOM'lar ve DPIA) güncelleyin.

#### 3.10 Düzenleyici Değişiklik

Tetikleyici: GDPR uygulama rehberinde değişiklik, EDPB kılavuz güncellemesi veya bir girişi önemli ölçüde etkileyen Üye Devlet hukuku değişikliği.

Eylem: DPO etkiyi değerlendirir, etkilenen girişleri günceller ve düzenleyici sürücüyü Sütun 34'e kaydeder.

### 4. Sahiplik ve Eskalasyon

#### 4.1 Sahipler

| Rol | Sorumluluk |
|-----|------------|
| Süreç sahibi | Birinci savunma hattı. Girişin içeriğini sahiplenir. |
| Departman müdürü | Birinci hat içeriğini onaylar; değişikliği imzalar. |
| DPO | İkinci savunma hattı. Hukuki sebebi, aktarımları, özel kategori muamelesini onaylar. |
| Hukuk | Sözleşmesel sonuçları onaylar (DPA'lar, ortak veri sorumluluğu sözleşmeleri, aktarım araçları). |
| CISO / CTO | TOM ile ilgili girişleri onaylar (Sütun 24–25, 28). |
| İç Denetim | Bağımsız üçüncü hat. Rejimi yıllık olarak test eder. |
| Kayıt Yöneticisi | Saklama planı uyumunu sürdürür. |

#### 4.2 Eskalasyon Tetikleyicileri

| Sorun | Yükseltilecek Kişi | İçinde |
|-------|---------------------|--------|
| Süreç sahibi hukuki sebebi belirleyemiyor | DPO | 5 iş günü |
| Tedarikçi güncel DPA'yı imzalamayı reddediyor | Satınalma + Hukuk | 5 iş günü |
| Gölge BT işleme keşfedildi | DPO | Aynı gün |
| Güvencesiz üçüncü ülke aktarımı keşfedildi | DPO | Aynı gün; inceleme bekleyene kadar aktarımı askıya alın |
| İnceleme sırasında ihlal şüphesi | İhlal Yöneticisi | Madde 33 zamanlayıcısı altında derhal |
| İnceleme sırasında DPIA eşiğine ulaşıldı | DPO | 5 iş günü; lansman öncesi yeni özelliği duraklatın |

### 5. Kalite Metrikleri

Aylık olarak Gizlilik Yönlendirme Komitesine raporlanır:

- ROPA giriş sayısı.
- Son üç ayda incelenen giriş yüzdesi.
- Aktif istihdam durumundaki süreç sahibi olan giriş yüzdesi.
- Değişiklik kategorisine göre tetiklenen ROPA değişiklik sayısı (yeni sistem, tedarikçi, M&A vb.).
- "Son İnceleme" tarihinin ortalama yaşı.
- Yaş bazında son DPO incelemesinden kalan eylemler.
- Dönemde ROPA'dan sunulan denetim otoritesi yanıtı sayısı.

### 6. Araçlar ve Denetim İzi

Hangi depolama aracı olursa olsun, her değişiklik şu denetim izini üretmelidir:

- Kim neyi ne zaman değiştirdi.
- Kim onayladı.
- Değişen alanların önceki/sonraki değeri.
- Tetikleyici olay (bilete, DPIA'ya, tedarikçi değişikliğine, M&A kapanışına bağlantı).

Wiki tarzı depolama için bu, sürüm kontrolü (git geçmişi) ile zorlanır. GRC araçları için eşdeğer değişiklik geçmişi özelliği etkin ve değiştirilemez olmalıdır.

### 7. Girişlerin Hizmetten Çıkarılması

Bir işleme faaliyeti durdurulduğunda:

1. Giriş **silinmez**. Bitiş tarihiyle "Hizmetten Çıkarılmış" olarak işaretlenir.
2. Giriş, geçerli en uzun saklama süresi artı bir güvenlik marjı geçene kadar erişilebilir kalır.
3. Geçmiş işleme için hesap verebilirliği korumak amacıyla giriş ROPA'nın dizininde tarihsel olarak referans verilir.

### 8. Örnek Üç Aylık İnceleme E-posta Şablonu

> Konu: ROPA Üç Aylık İnceleme — Ç\_, Giriş \[Giriş Kimliği\]
>
> Sayın \[Süreç Sahibi\],
>
> Lütfen ekteki ROPA girişini \[son tarih\] tarihine kadar inceleyiniz.
>
> 1. Her alanı yeniden okuyun. "Tamam," "Güncellendi" veya "Bilinmiyor" olarak işaretleyin.
> 2. BT sistemleri listesinin üretimde olanı yansıttığını onaylayın.
> 3. Tedarikçi ve alt işleyen listesinin güncel olduğunu onaylayın.
> 4. Saklama süresinin pratikte hâlâ uygulandığını onaylayın.
> 5. Herhangi bir değişikliği 34. alana tarih ve baş harflerinizle not edin.
>
> Güncellenmiş girişle (veya "değişiklik yok" onayıyla) \[son tarih\] tarihine kadar bu e-postayı yanıtlayın. Geç gönderimler departman müdürünüze yükseltilecektir.
>
> Saygılarımla,
> DPO Ofisi
