---
title:
  en: "Periodic Destruction Process"
  tr: "Periyodik İmha Süreci"
section: "04-retention-erasure"
document_type: "procedure"
regulation: "GDPR (EU 2016/679)"
articles:
  - "Art. 5(1)(e) — Storage limitation"
  - "Art. 5(2) — Accountability"
  - "Art. 24 — Responsibility of the controller"
  - "Art. 30 — Records of processing activities"
language: "en, tr"
last_reviewed: "2025-05-01"
review_cycle: "annual"
owner: "Data Protection Officer"
co_owner: "IT Operations / Information Security"
status: "approved"
classification: "internal"
---

## English

# Periodic Destruction Process

This document defines the cadence, mechanics, audit trail, and automated triggers for the **routine destruction** of personal data that has reached the end of its retention period.

## 1. Purpose

Storage limitation is a process, not an event. This procedure ensures that:

- Personal data does not silently outlive its retention period.
- Each destruction event is documented with audit-grade evidence.
- Deviations (legal hold, exception, technical impossibility) are explicit and reviewed.
- The controller can demonstrate Article 5(2) accountability.

## 2. Destruction cadence

| Cadence | Activity | Owner |
|---|---|---|
| **Daily** | Automated TTL / lifecycle expiry on logs, cookies, sessions, ephemeral caches. | IT Ops (engineered) |
| **Weekly** | Email mailbox cleanup for terminated employees (post-litigation hold). | IT Ops |
| **Monthly** | DSAR-driven erasure execution and verification. | DPO + IT Ops |
| **Quarterly** | Destruction sampling audit. Backup expiry verification. Sub-processor certificate review. | DPO |
| **Annual** | Full retention-schedule review per category. Policy review. Member-state law refresh. | DPO + Data Owners + Legal |
| **Event-driven** | End of employment, account closure, contract end, system decommissioning. | Process owner |

## 3. Automated triggers

Wherever feasible, retention shall be enforced by automated controls. The DPO maintains a register of automated triggers per system.

### 3.1 Examples of automated triggers

| System | Trigger | Action |
|---|---|---|
| Application database | `created_at` + retention period reached | Row delete + audit log |
| Object storage | Bucket lifecycle rule | Permanent delete after N days |
| Log store | Index lifecycle policy | Delete index older than X days |
| CCTV recorder | Ring buffer expiry | Overwrite |
| Email server | Retention policy on mailbox folders | Auto-purge |
| HR system | Employee termination + retention years | Generate destruction list |
| CRM | Lead inactivity (e.g., 18 months) | Auto-archive then delete |
| Backup | Per-backup-set TTL | Crypto-shred / overwrite |

### 3.2 Manual triggers

For categories without automation:

- Quarterly job: produce a list of records past their retention period.
- Data owner reviews and approves the destruction list.
- IT Ops executes destruction.
- DPO samples for verification.

### 3.3 Combining triggers

For a single record (e.g., an employee), multiple triggers may fire at different times:
- Termination → 6-month mailbox hold.
- Termination + 6 months → mailbox deletion.
- Fiscal year end + 10 years → payroll record destruction.
- Termination + 3 years → performance review destruction.
- Per occupational-health rule → health record destruction at year 10–40.

The HR system (or specialised tool) shall track these per-record dates and surface the next due action.

## 4. Quarterly destruction cycle

### 4.1 Pre-cycle (T-30 days)

1. **Generate the candidate list.** Each system produces a list of records past their retention period.
2. **Apply legal-hold filter.** Cross-reference Litigation Hold Register; remove held items.
3. **Apply exception filter.** Cross-reference Exception Register; remove approved exceptions.
4. **Send to data owner.** Data owner reviews the candidate list and signs off.
5. **DPO review.** DPO reviews aggregated candidate list and approves the cycle.

### 4.2 Cycle execution (T)

1. **Production deletion.** IT Ops executes per `erasure-methods.md`.
2. **Replica verification.** Verify replicas, search indexes, caches caught up.
3. **Backup handling.** Apply backup erasure strategy.
4. **Processor notification.** Notify each processor of bulk deletion (if applicable).
5. **Paper destruction.** Schedule with shredding service or in-house service.
6. **Endpoint sanitisation.** Schedule for any decommissioned endpoints.
7. **Destruction record.** For each batch, populate `destruction-record.md` template.

### 4.3 Post-cycle (T+15 days)

1. **Verification.** InfoSec spot-checks destruction effectiveness.
2. **Sub-processor reconciliation.** Collect processor certificates.
3. **Backup expiry confirmation.** Verify the backup-cycle expiry passed without restoration.
4. **DPO sign-off.** DPO signs the cycle report.

### 4.4 Annual cycle (additional steps)

- Member-state law refresh (any new tax/commercial/sector-specific obligations).
- Retention schedule review by each Data Owner.
- Audit by Internal Audit / external auditor.
- Risk assessment update for the data lifecycle.
- Training refresh for Data Owners and IT Ops.

## 5. Audit trail

Every destruction event must produce evidence sufficient to satisfy:
- Internal Audit.
- External auditor (financial, ISO 27001, SOC 2).
- Supervisory authority (DPA inspection).
- Court (in a litigation or DPA enforcement context).

Required elements:

| Element | Description |
|---|---|
| Date/time | Start and completion timestamps. |
| Operator | Person or job ID executing destruction. |
| Witness | Co-signatory (for high-sensitivity / paper). |
| Approval | Data owner approval; DPO sign-off where required. |
| Categories | Data categories destroyed. |
| Volume | Number of records / pages / GB. |
| Method | NIST level, technique, tool. |
| System(s) | Source systems. |
| Backup status | Backup propagation status. |
| Processors notified | List + acknowledgement. |
| Sub-processors notified | List + acknowledgement. |
| Verification | Sample verification evidence. |
| Anomalies | Any incomplete deletion, with remediation plan. |

## 6. Legal hold management

### 6.1 Issuing a hold

When litigation, regulatory investigation, or audit is reasonably anticipated:

1. **Legal counsel** documents the scope (parties, claims, time period).
2. **Litigation Hold Register** entry created with: scope, custodians, systems, retention extension.
3. **Notice to custodians.** Affected employees informed in writing of the hold and their preservation obligations.
4. **Technical implementation.** Auto-expiry suspended for affected records (legal-hold flag).
5. **Periodic review.** Hold reviewed every 6 months minimum.

### 6.2 Lifting a hold

When the legal matter resolves:

1. Legal counsel confirms in writing.
2. Litigation Hold Register entry closed.
3. Affected records re-enter the standard destruction queue.
4. Destruction occurs in the next quarterly cycle.
5. Custodians informed.

### 6.3 Cross-jurisdictional considerations

A US litigation hold (FRCP) may impact EU personal data. Consider:
- Conflict between US discovery obligations and GDPR Chapter V (Schrems II).
- Use of Hague Convention or Article 49 derogations (narrow).
- Pseudonymisation / minimisation during preservation.

## 7. Exception management

### 7.1 Exception types

| Type | Example |
|---|---|
| Legal hold | Active litigation. |
| Regulatory hold | DPA investigation, financial regulator audit. |
| Technical impossibility | Immutable backup beyond control. |
| Business need | Active dispute resolution; documented project pause. |
| Statutory extension | Newly enacted member-state law extends retention. |

### 7.2 Approval workflow

1. Data owner submits exception request with: scope, reason, expiry, compensating controls.
2. DPO reviews.
3. Legal reviews (if litigation- or regulator-related).
4. DPO approves (max 12 months; renewable).
5. Logged in Exception Register.
6. Periodic review (every 6 months minimum).

### 7.3 Exception register fields

- Exception ID
- Date logged
- Scope (records, categories, systems)
- Reason
- Lawful basis for extended retention
- Compensating controls (Art. 18 restriction, encryption, access limits)
- Expiry / review date
- Approvals (Data Owner, DPO, Legal)
- Lift date and evidence

## 8. Roles and responsibilities (RACI)

| Activity | Data Owner | DPO | IT Ops | InfoSec | Legal | Internal Audit |
|---|---|---|---|---|---|---|
| Maintain retention schedule | A/R | C | I | I | C | I |
| Engineer automated triggers | C | C | A/R | C | I | I |
| Generate destruction candidate list | A/R | C | C | I | I | I |
| Apply legal hold filter | C | C | C | I | A/R | I |
| Approve destruction cycle | C | A/R | I | I | I | I |
| Execute destruction | R | I | A/R | C | I | I |
| Verify destruction | I | C | C | A/R | I | I |
| Collect processor certificates | I | A/R | C | I | I | I |
| Maintain destruction records | A | A/R | R | C | I | I |
| Issue legal hold | I | C | I | I | A/R | I |
| Audit cycle | I | I | I | I | I | A/R |

## 9. Performance indicators

The DPO tracks and reports:

- **Coverage**: % of personal data categories under automated retention enforcement (target: ≥80%).
- **Timeliness**: % of cycles completed by the planned date (target: ≥95%).
- **Backlog**: number of records past retention not yet destroyed (target: trending down; absolute zero unrealistic but flag growth).
- **Verification rate**: % of cycles with sample verification (target: 100%).
- **Exception count**: number of active exceptions (rising trend triggers root-cause review).
- **Audit findings**: number of internal/external audit findings related to retention/destruction (target: zero major).

## 10. Common pitfalls

| Pitfall | Mitigation |
|---|---|
| Schedule says "destroy" but no automation; no one runs the job | Explicit owner; automate; audit |
| Job fails silently | Alerting on job failure; cycle review verifies completion |
| Soft delete only (UI-level) | Specification requires hard delete + audit |
| Replicas not aligned | Verification after each cycle |
| Backups not addressed | Crypto-shred strategy in place from day 1 |
| Processor not notified | Automated processor notification list |
| Exception register grows without review | Periodic 6-month review, escalation if expired |
| Legal hold not lifted | Legal counsel quarterly review |

---

## Türkçe

# Periyodik İmha Süreci

Bu belge, saklama süresinin sonuna ulaşmış kişisel verilerin **rutin imhası** için tempo, mekanik, denetim izi ve otomatik tetikleyicileri tanımlar.

## 1. Amaç

Saklama sınırlaması bir olay değil, bir süreçtir. Bu prosedür şunları sağlar:

- Kişisel veri saklama süresinden sessizce daha uzun yaşamaz.
- Her imha olayı denetim sınıfı kanıtla belgelenir.
- Sapmalar (hukuki bekletme, istisna, teknik imkânsızlık) açıktır ve gözden geçirilir.
- Kontrolör Madde 5(2) hesap verebilirliğini gösterebilir.

## 2. İmha temposu

| Tempo | Faaliyet | Sahip |
|---|---|---|
| **Günlük** | Loglar, çerezler, oturumlar, geçici önbellekler üzerinde otomatik TTL / yaşam döngüsü sona erme. | BT Ops (mühendislik) |
| **Haftalık** | Sonlandırılmış çalışanlar için e-posta posta kutusu temizliği (dava bekletme sonrası). | BT Ops |
| **Aylık** | DSAR güdümlü silme uygulaması ve doğrulama. | DPO + BT Ops |
| **Üç aylık** | İmha örnekleme denetimi. Yedek son doğrulaması. Alt-işleyen sertifika incelemesi. | DPO |
| **Yıllık** | Kategori başına tam saklama-çizelgesi incelemesi. Politika incelemesi. Üye devlet hukuku yenileme. | DPO + Veri Sahipleri + Hukuk |
| **Olay güdümlü** | İstihdam sonu, hesap kapanışı, sözleşme sonu, sistem devre dışı bırakma. | Süreç sahibi |

## 3. Otomatik tetikleyiciler

Mümkün olan her yerde, saklama otomatik kontrollerle uygulanır. DPO sistem başına otomatik tetikleyiciler sicili tutar.

### 3.1 Otomatik tetikleyici örnekleri

| Sistem | Tetikleyici | Eylem |
|---|---|---|
| Uygulama veritabanı | `created_at` + saklama süresi ulaşıldı | Satır silme + denetim logu |
| Nesne depolama | Kova yaşam döngüsü kuralı | N gün sonra kalıcı silme |
| Log deposu | İndeks yaşam döngüsü politikası | X günden eski indeksi sil |
| CCTV kaydedici | Halka tampon süresi | Üzerine yaz |
| E-posta sunucusu | Posta kutusu klasörlerinde saklama politikası | Otomatik temizleme |
| İK sistemi | Çalışan sonlandırma + saklama yılları | İmha listesi oluştur |
| CRM | Lead etkisizliği (örn. 18 ay) | Otomatik arşiv sonra sil |
| Yedek | Yedek-set başına TTL | Kripto-parçalama / üzerine yazma |

### 3.2 Manuel tetikleyiciler

Otomasyonu olmayan kategoriler için:

- Üç aylık iş: saklama süresini aşmış kayıtların listesini üret.
- Veri sahibi inceler ve imha listesini onaylar.
- BT Ops imhayı gerçekleştirir.
- DPO doğrulama için örnekler.

### 3.3 Tetikleyicileri birleştirme

Tek bir kayıt için (örn. bir çalışan), birden fazla tetikleyici farklı zamanlarda ateşlenebilir:
- Sonlandırma → 6 aylık posta kutusu bekletme.
- Sonlandırma + 6 ay → posta kutusu silme.
- Mali yıl sonu + 10 yıl → bordro kayıt imhası.
- Sonlandırma + 3 yıl → performans değerlendirme imhası.
- Mesleki sağlık kuralı başına → 10–40. yılda sağlık kayıt imhası.

İK sistemi (veya özel araç) bu kayıt başına tarihleri izler ve bir sonraki vade eylemini yüzeye çıkarır.

## 4. Üç aylık imha döngüsü

### 4.1 Döngü öncesi (T-30 gün)

1. **Aday listesini üret.** Her sistem saklama süresini aşmış kayıtların listesini üretir.
2. **Hukuki bekletme filtresi uygula.** Dava Bekletme Sicili ile çapraz başvur; bekletilen öğeleri kaldır.
3. **İstisna filtresi uygula.** İstisna Sicili ile çapraz başvur; onaylı istisnaları kaldır.
4. **Veri sahibine gönder.** Veri sahibi aday listesini inceler ve onaylar.
5. **DPO incelemesi.** DPO toplu aday listesini inceler ve döngüyü onaylar.

### 4.2 Döngü uygulaması (T)

1. **Üretim silmesi.** BT Ops `erasure-methods.md` başına gerçekleştirir.
2. **Replika doğrulaması.** Replikaların, arama indekslerinin, önbelleklerin yetiştiğini doğrula.
3. **Yedek işleme.** Yedek silme stratejisi uygula.
4. **İşleyen bildirimi.** Her işleyene toplu silme bildirimi (geçerliyse).
5. **Kâğıt imha.** Parçalama hizmeti veya iç hizmetle planla.
6. **Uç nokta sanitasyonu.** Devre dışı bırakılan herhangi bir uç nokta için planla.
7. **İmha kaydı.** Her parti için, `destruction-record.md` şablonunu doldur.

### 4.3 Döngü sonrası (T+15 gün)

1. **Doğrulama.** InfoSec imha etkinliğini anlık denetler.
2. **Alt-işleyen mutabakatı.** İşleyen sertifikalarını topla.
3. **Yedek son onayı.** Yedek-döngü sonunun geri yükleme olmadan geçtiğini doğrula.
4. **DPO onayı.** DPO döngü raporunu imzalar.

### 4.4 Yıllık döngü (ek adımlar)

- Üye devlet hukuku yenileme (yeni vergi/ticari/sektöre özgü yükümlülükler).
- Her Veri Sahibi tarafından saklama çizelgesi incelemesi.
- İç Denetim / dış denetçi tarafından denetim.
- Veri yaşam döngüsü için risk değerlendirmesi güncellemesi.
- Veri Sahipleri ve BT Ops için eğitim yenileme.

## 5. Denetim izi

Her imha olayı şunları karşılayacak yeterlilikte kanıt üretmelidir:
- İç Denetim.
- Dış denetçi (finansal, ISO 27001, SOC 2).
- Denetim makamı (DPA denetimi).
- Mahkeme (dava veya DPA uygulama bağlamında).

Gerekli unsurlar:

| Unsur | Açıklama |
|---|---|
| Tarih/saat | Başlangıç ve tamamlanma zaman damgaları. |
| Operatör | İmhayı yürüten kişi veya iş kimliği. |
| Tanık | Eş imzacı (yüksek hassasiyet / kâğıt için). |
| Onay | Veri sahibi onayı; gerektiğinde DPO onayı. |
| Kategoriler | İmha edilen veri kategorileri. |
| Hacim | Kayıt / sayfa / GB sayısı. |
| Yöntem | NIST seviyesi, teknik, araç. |
| Sistem(ler) | Kaynak sistemler. |
| Yedek durumu | Yedek yayma durumu. |
| Bildirilen işleyenler | Liste + onay. |
| Bildirilen alt-işleyenler | Liste + onay. |
| Doğrulama | Örnek doğrulama kanıtı. |
| Anomaliler | Tamamlanmamış silme, iyileştirme planı ile. |

## 6. Hukuki bekletme yönetimi

### 6.1 Bir bekletme verme

Dava, düzenleyici soruşturma veya denetim makul olarak öngörüldüğünde:

1. **Hukuk müşaviri** kapsamı (taraflar, talepler, zaman dilimi) belgeler.
2. **Dava Bekletme Sicili** girişi şunlarla oluşturulur: kapsam, koruyucular, sistemler, saklama uzatması.
3. **Koruyuculara bildirim.** Etkilenen çalışanlar bekletme ve koruma yükümlülükleri hakkında yazılı olarak bilgilendirilir.
4. **Teknik uygulama.** Etkilenen kayıtlar için otomatik son askıya alınır (hukuki-bekletme bayrağı).
5. **Periyodik inceleme.** Bekletme en az 6 ayda bir gözden geçirilir.

### 6.2 Bir bekletmeyi kaldırma

Hukuki mesele çözüldüğünde:

1. Hukuk müşaviri yazılı olarak onaylar.
2. Dava Bekletme Sicili girişi kapatılır.
3. Etkilenen kayıtlar standart imha kuyruğuna yeniden girer.
4. İmha bir sonraki üç aylık döngüde gerçekleşir.
5. Koruyucular bilgilendirilir.

### 6.3 Yargı bölgeleri arası hususlar

Bir ABD dava bekletme (FRCP) AB kişisel verisini etkileyebilir. Şunları düşünün:
- ABD keşif yükümlülükleri ile GDPR Bölüm V (Schrems II) arasındaki çatışma.
- Lahey Sözleşmesi veya Madde 49 istisnalarının kullanımı (dar).
- Koruma sırasında takma adlandırma / minimizasyon.

## 7. İstisna yönetimi

### 7.1 İstisna türleri

| Tür | Örnek |
|---|---|
| Hukuki bekletme | Aktif dava. |
| Düzenleyici bekletme | DPA soruşturması, finansal düzenleyici denetimi. |
| Teknik imkânsızlık | Kontrolün ötesinde değişmez yedek. |
| İş ihtiyacı | Aktif anlaşmazlık çözümü; belgelenmiş proje duraklaması. |
| Yasal uzatma | Yeni yürürlüğe giren üye devlet hukuku saklamayı uzatır. |

### 7.2 Onay iş akışı

1. Veri sahibi şunlarla istisna talebi gönderir: kapsam, sebep, sona erme, telafi edici kontroller.
2. DPO inceler.
3. Hukuk inceler (dava- veya düzenleyici-ilgili olduğunda).
4. DPO onaylar (max 12 ay; yenilenebilir).
5. İstisna Sicili'ne kaydedilir.
6. Periyodik inceleme (en az 6 ayda bir).

### 7.3 İstisna sicil alanları

- İstisna kimliği
- Kayıt tarihi
- Kapsam (kayıtlar, kategoriler, sistemler)
- Sebep
- Uzatılmış saklama için hukuki dayanak
- Telafi edici kontroller (Md. 18 kısıtlama, şifreleme, erişim sınırları)
- Sona erme / inceleme tarihi
- Onaylar (Veri Sahibi, DPO, Hukuk)
- Kaldırma tarihi ve kanıtı

## 8. Roller ve sorumluluklar (RACI)

| Faaliyet | Veri Sahibi | DPO | BT Ops | InfoSec | Hukuk | İç Denetim |
|---|---|---|---|---|---|---|
| Saklama çizelgesini koru | A/R | C | I | I | C | I |
| Otomatik tetikleyiciler mühendislik | C | C | A/R | C | I | I |
| İmha aday listesi üret | A/R | C | C | I | I | I |
| Hukuki bekletme filtresi uygula | C | C | C | I | A/R | I |
| İmha döngüsünü onayla | C | A/R | I | I | I | I |
| İmhayı gerçekleştir | R | I | A/R | C | I | I |
| İmhayı doğrula | I | C | C | A/R | I | I |
| İşleyen sertifikalarını topla | I | A/R | C | I | I | I |
| İmha kayıtlarını koru | A | A/R | R | C | I | I |
| Hukuki bekletme ver | I | C | I | I | A/R | I |
| Döngü denetimi | I | I | I | I | I | A/R |

## 9. Performans göstergeleri

DPO izler ve raporlar:

- **Kapsam**: otomatik saklama uygulaması altındaki kişisel veri kategorilerinin yüzdesi (hedef: ≥%80).
- **Zamanında olma**: planlanan tarihe kadar tamamlanan döngülerin yüzdesi (hedef: ≥%95).
- **Birikim**: saklama süresini aşmış henüz imha edilmemiş kayıt sayısı (hedef: düşüş trendinde; mutlak sıfır gerçekçi değil ama büyümeyi işaretle).
- **Doğrulama oranı**: örnek doğrulama içeren döngülerin yüzdesi (hedef: %100).
- **İstisna sayısı**: aktif istisna sayısı (yükselen trend kök neden incelemeyi tetikler).
- **Denetim bulguları**: saklama/imha ile ilgili iç/dış denetim bulgularının sayısı (hedef: sıfır majör).

## 10. Yaygın tuzaklar

| Tuzak | Hafifletme |
|---|---|
| Çizelge "imha" diyor ama otomasyon yok; kimse işi çalıştırmıyor | Açık sahip; otomatikleştir; denetle |
| İş sessizce başarısız oluyor | İş başarısızlığında uyarı; döngü incelemesi tamamlanmayı doğrular |
| Yalnızca yumuşak silme (UI seviyesi) | Şartname sert silme + denetim gerektirir |
| Replikalar hizalı değil | Her döngüden sonra doğrulama |
| Yedekler ele alınmıyor | 1. günden itibaren kripto-parçalama stratejisi |
| İşleyen bildirilmedi | Otomatik işleyen bildirim listesi |
| İstisna sicili inceleme olmadan büyüyor | Periyodik 6 aylık inceleme, süresi dolarsa eskalasyon |
| Hukuki bekletme kaldırılmıyor | Hukuk müşaviri üç aylık inceleme |
