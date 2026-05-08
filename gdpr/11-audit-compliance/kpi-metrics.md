---
title:
  en: "GDPR KPI Metrics and Operational Dashboard"
  tr: "GDPR KPI Metrikleri ve Operasyonel Pano"
section: "11-audit-compliance"
owner: "DPO / Compliance"
version: "1.0"
last_review: "2026-05-08"
next_review: "2026-11-08"
classification: "Internal"
languages: ["en", "tr"]
keywords:
  en: ["KPI", "metrics", "dashboard", "ROPA freshness", "DSR SLA", "MTTD", "MTTR"]
  tr: ["KPI", "metrik", "pano", "ROPA tazelik", "DSR SLA", "MTTD", "MTTR"]
---

## English

# GDPR Operational KPIs

The KPI catalog operationalizes the accountability principle (Article 5(2)) by translating program objectives into measurable indicators. Each KPI has a definition, formula, data source, refresh frequency, threshold, and owner. Thresholds are colour-coded **green / amber / red** to drive prioritization without overwhelming the dashboard. KPIs are reviewed monthly by the privacy office and quarterly by senior management.

### KPI catalog

#### 1. ROPA freshness rate

- **Definition:** percentage of ROPA records reviewed and signed off in the past twelve months relative to total active ROPA entries.
- **Formula:** `(records reviewed in past 12 months / total active records) × 100`.
- **Data source:** ROPA tooling export (created/updated date, attestation date).
- **Frequency:** monthly snapshot.
- **Thresholds:** green ≥ 95%, amber 85-94%, red < 85%.
- **Owner:** privacy office, with process-owner attestation per record.
- **Notes:** any record older than fifteen months auto-flags amber regardless of overall rate.

#### 2. DSR average response time

- **Definition:** mean elapsed time, in calendar days, from valid request receipt to response, including identity verification.
- **Formula:** `Σ(response_date − receipt_date) / count(closed requests)`.
- **Data source:** DSR ticketing system.
- **Frequency:** weekly rolling 90-day window.
- **Thresholds:** green ≤ 18 days (well within Article 12(3) one-month SLA), amber 19-25 days, red > 25 days.
- **Owner:** DSR operations lead.
- **Companion KPIs:** percentage answered within one month; percentage of cases extended under Article 12(3) (target ≤ 10%).

#### 3. DSR SLA breach rate

- **Definition:** percentage of requests that exceeded the statutory deadline (one month, extended up to three months only when justified).
- **Formula:** `breached requests / total closed requests × 100`.
- **Thresholds:** green = 0%, amber 0.1-1%, red > 1%.
- **Owner:** DSR operations lead.

#### 4. Consent withdrawal rate

- **Definition:** percentage of active consents withdrawn in the period — a high rate may signal poor transparency, banner UX issues, or trust erosion.
- **Formula:** `withdrawals in period / active consents at start of period × 100`.
- **Frequency:** monthly per consent type.
- **Thresholds:** baseline-relative; investigate any month-over-month change > 25%.
- **Owner:** marketing operations, advised by privacy office.

#### 5. Cookie consent acceptance vs rejection ratio

- **Definition:** ratio between accept-all, reject-all, and granular choices on cookie banner.
- **Source:** consent management platform (CMP).
- **Thresholds:** flag if accept-all > 90% — likely indicates banner imbalance or non-compliance with Planet49 (C-673/17) and EDPB Guidelines 03/2022 on deceptive design.
- **Owner:** privacy office.

#### 6. Breach mean time to detect (MTTD)

- **Definition:** average time between a breach occurring and being identified.
- **Formula:** `Σ(detection_time − occurrence_time) / count(detected breaches)`.
- **Source:** SIEM, IR ticketing.
- **Thresholds:** green ≤ 24h, amber 24-72h, red > 72h.
- **Owner:** information security.

#### 7. Breach mean time to notify SA (MTTN)

- **Definition:** time between detection and SA notification under Article 33(1).
- **Threshold:** must be ≤ 72 hours where notifiable; report any reasoned delay justification per Article 33(1) second sentence.
- **Owner:** DPO.

#### 8. Breach mean time to remediate (MTTR)

- **Definition:** time between detection and full containment plus eradication.
- **Threshold:** risk-tier dependent — for high risk, target ≤ 7 days.
- **Owner:** information security.

#### 9. Mandatory training completion rate

- **Definition:** percentage of in-scope staff who completed required training within deadline.
- **Formula:** `completed / required × 100`.
- **Frequency:** monthly.
- **Thresholds:** green ≥ 95%, amber 85-94%, red < 85%.
- **Owner:** HR with privacy office curriculum oversight.
- **Companion:** assessment pass rate ≥ 90%; phishing simulation fail rate ≤ 10%.

#### 10. Vendor DPA coverage

- **Definition:** percentage of in-scope processors with executed Article 28 DPA, sub-processor approvals current, and TIA where transfer applies.
- **Thresholds:** green ≥ 99%, amber 95-98%, red < 95%.
- **Owner:** procurement, validated by privacy office.

#### 11. Transfer Impact Assessment (TIA) completion

- **Definition:** percentage of cross-border transfers with documented TIA aligned to EDPB Recommendations 01/2020 (post-Schrems II).
- **Thresholds:** green = 100% for new transfers, amber 95-99%, red < 95%.
- **Owner:** privacy office.

#### 12. Open finding age

- **Definition:** age in days of unresolved audit, regulatory, or DSR findings, by severity.
- **Thresholds (Critical):** green ≤ 30 days, amber 31-60, red > 60.
- **Thresholds (High):** green ≤ 60, amber 61-90, red > 90.
- **Owner:** CAPA owner, escalated to executive sponsor at red.

#### 13. DPIA coverage

- **Definition:** percentage of processing activities triggering Article 35 thresholds with completed DPIA on file.
- **Triggers:** EDPB WP248 nine criteria — at least two trigger DPIA. Article 35(3) compulsory cases also covered.
- **Thresholds:** green ≥ 98%, amber 90-97%, red < 90%.
- **Owner:** privacy office.

#### 14. Right of access turnaround quality

- **Definition:** percentage of access requests answered with structured machine-readable extract.
- **Thresholds:** green ≥ 90%, amber 80-89%, red < 80%.
- **Owner:** DSR operations.

#### 15. Privacy notice readability

- **Definition:** Flesch-Kincaid grade level of customer-facing notices.
- **Threshold:** target ≤ grade 9; layered notices with summary boxes recommended (EDPB Guidelines 03/2020 transparency).
- **Owner:** privacy office, content team.

#### 16. Sub-processor change notification SLA

- **Definition:** elapsed time between processor notification and our acknowledgment/objection window.
- **Threshold:** ≤ 14 days from receipt to internal review decision.
- **Owner:** procurement.

### Monthly dashboard

A condensed monthly view aggregates the catalog into a single page. Recommended layout:

```
+----------------------------------------------------------------+
| GDPR DASHBOARD — Period: YYYY-MM                                |
+----------------------+-----------------+----------+-------------+
| KPI                  | Current         | Trend    | Status      |
+----------------------+-----------------+----------+-------------+
| ROPA freshness       | 96%             | up 2 pts | green       |
| DSR avg response     | 14 days         | flat     | green       |
| DSR SLA breaches     | 0.4%            | up       | amber       |
| Consent withdrawals  | 3.1%            | flat     | green       |
| Cookie accept-all    | 78%             | down     | green       |
| Breach MTTD          | 18h             | down     | green       |
| Breach MTTN          | 0 / 0 in window | n/a      | green       |
| Training completion  | 91%             | up       | amber       |
| Vendor DPA coverage  | 97%             | up       | amber       |
| TIA completion       | 100%            | flat     | green       |
| Open findings (Crit) | 1 @ 22 days     | n/a      | green       |
| Open findings (High) | 4 @ 51 days     | n/a      | green       |
| DPIA coverage        | 98%             | flat     | green       |
+----------------------+-----------------+----------+-------------+
| Top risks: Vendor X re-assessment overdue; Cookie banner test  |
+----------------------------------------------------------------+
```

### Data quality and integrity

KPI integrity depends on disciplined ticketing hygiene, accurate process metadata, and a single source of truth for ROPA. Sample audit trails should accompany monthly reporting so that values can be reproduced.

### Reporting cadence

| Stakeholder | Cadence | Format |
|-------------|---------|--------|
| DPO and privacy office | weekly | rolling dashboard |
| Executive committee | monthly | one-page scorecard with trends |
| Audit committee / board | quarterly | scorecard plus narrative and risk |
| Supervisory authority | on request or as part of accountability evidence | extracts as needed |

### Anti-pattern warnings

- Avoid vanity metrics with no operational lever (e.g. raw count of records). Pair raw counts with denominators.
- Avoid averaging maturity scores — track per-dimension lows.
- Avoid trailing-only metrics for breach response — leading indicators (drill cadence) matter equally.

---

## Türkçe

# GDPR Operasyonel KPI'ları

KPI kataloğu, program hedeflerini ölçülebilir göstergelere çevirerek hesap verebilirlik ilkesini (Madde 5(2)) işlevsel hale getirir. Her KPI'nın bir tanımı, formülü, veri kaynağı, yenileme sıklığı, eşiği ve sahibi vardır. Eşikler **yeşil / sarı / kırmızı** renk kodludur ve panoyu boğmadan önceliklendirme sağlar. KPI'lar gizlilik ofisi tarafından aylık, üst yönetim tarafından çeyreklik gözden geçirilir.

### KPI kataloğu

#### 1. ROPA tazelik oranı

- **Tanım:** son on iki ayda gözden geçirilip onaylanan ROPA kayıtlarının toplam aktif kayıtlara oranı.
- **Formül:** `(son 12 ayda gözden geçirilen kayıtlar / toplam aktif kayıtlar) × 100`.
- **Veri kaynağı:** ROPA aracı dışa aktarımı (oluşturma/güncelleme tarihi, onay tarihi).
- **Sıklık:** aylık fotoğraf.
- **Eşikler:** yeşil ≥ %95, sarı %85-94, kırmızı < %85.
- **Sahip:** gizlilik ofisi, kayıt başına süreç sahibi onayı ile.
- **Not:** on beş aydan eski herhangi bir kayıt, genel orana bakılmaksızın otomatik sarı işaretlenir.

#### 2. DSR ortalama yanıt süresi

- **Tanım:** geçerli talep alındısından yanıta kadar kimlik doğrulama dahil geçen ortalama süre (takvim günü).
- **Formül:** `Σ(yanıt_tarihi − alındı_tarihi) / kapatılan_talep_sayısı`.
- **Veri kaynağı:** DSR talep sistemi.
- **Sıklık:** haftalık 90 günlük dönen pencere.
- **Eşikler:** yeşil ≤ 18 gün (Madde 12(3) bir aylık SLA içinde rahatlıkla), sarı 19-25 gün, kırmızı > 25 gün.
- **Sahip:** DSR operasyon lideri.
- **Tamamlayıcı KPI'lar:** bir ay içinde yanıtlanan yüzde; Madde 12(3) altında uzatılan vaka yüzdesi (hedef ≤ %10).

#### 3. DSR SLA aşım oranı

- **Tanım:** yasal süreyi (bir ay, ancak gerekçeli olarak üç aya kadar uzatılabilir) aşan taleplerin yüzdesi.
- **Formül:** `aşılan talep / kapatılan toplam talep × 100`.
- **Eşikler:** yeşil = %0, sarı %0.1-1, kırmızı > %1.
- **Sahip:** DSR operasyon lideri.

#### 4. Açık rıza geri çekme oranı

- **Tanım:** dönemde geri çekilen aktif rızaların yüzdesi — yüksek oran zayıf şeffaflık, bant UX sorunları veya güven erozyonu işareti olabilir.
- **Formül:** `dönemdeki geri çekmeler / dönem başındaki aktif rızalar × 100`.
- **Sıklık:** rıza türü başına aylık.
- **Eşikler:** taban çizgiye göre; aydan aya %25'ten fazla değişimi araştırın.
- **Sahip:** pazarlama operasyonları, gizlilik ofisi danışmanlığı.

#### 5. Çerez rıza kabul/red oranı

- **Tanım:** çerez bantında tümünü kabul, tümünü reddet ve ayrıntılı seçimler arasındaki oran.
- **Kaynak:** rıza yönetim platformu (CMP).
- **Eşikler:** tümünü kabul > %90 ise işaretleyin — bant dengesizliği veya Planet49 (C-673/17) ile EDPB Kılavuzu 03/2022 (aldatıcı tasarım) uyumsuzluğu işareti olabilir.
- **Sahip:** gizlilik ofisi.

#### 6. İhlal ortalama tespit süresi (MTTD)

- **Tanım:** ihlalin gerçekleşmesi ile tespit edilmesi arasındaki ortalama süre.
- **Formül:** `Σ(tespit_zamanı − oluşum_zamanı) / tespit_edilen_ihlal_sayısı`.
- **Kaynak:** SIEM, OM talep sistemi.
- **Eşikler:** yeşil ≤ 24s, sarı 24-72s, kırmızı > 72s.
- **Sahip:** bilgi güvenliği.

#### 7. İhlal ortalama SA bildirim süresi (MTTN)

- **Tanım:** tespit ile Madde 33(1) altında SA bildirimi arasındaki süre.
- **Eşik:** bildirilebilir olduğunda ≤ 72 saat olmalıdır; gerekçeli her gecikme için Madde 33(1) ikinci cümleye göre gerekçe raporlayın.
- **Sahip:** DPO.

#### 8. İhlal ortalama düzeltme süresi (MTTR)

- **Tanım:** tespit ile tam kontrol altına alma artı yok etme arasındaki süre.
- **Eşik:** risk kademesine bağlı — yüksek risk için hedef ≤ 7 gün.
- **Sahip:** bilgi güvenliği.

#### 9. Zorunlu eğitim tamamlanma oranı

- **Tanım:** kapsam içi personelin son tarihinde gerekli eğitimi tamamlama yüzdesi.
- **Formül:** `tamamlanan / gerekli × 100`.
- **Sıklık:** aylık.
- **Eşikler:** yeşil ≥ %95, sarı %85-94, kırmızı < %85.
- **Sahip:** İK, gizlilik ofisi müfredat denetiminde.
- **Tamamlayıcı:** değerlendirme geçme oranı ≥ %90; olta saldırısı simülasyonu başarısız oranı ≤ %10.

#### 10. Tedarikçi DPA kapsama

- **Tanım:** Madde 28 DPA'sı imzalanmış, alt işleyen onayları güncel ve uygulanan transferlerde TIA olan kapsam içi işleyenlerin yüzdesi.
- **Eşikler:** yeşil ≥ %99, sarı %95-98, kırmızı < %95.
- **Sahip:** satın alma, gizlilik ofisi tarafından doğrulanır.

#### 11. Aktarım Etki Değerlendirmesi (TIA) tamamlanma

- **Tanım:** EDPB Tavsiyeleri 01/2020 (Schrems II sonrası) ile uyumlu belgelenmiş TIA'ya sahip sınır ötesi aktarımların yüzdesi.
- **Eşikler:** yeşil = yeni aktarımlar için %100, sarı %95-99, kırmızı < %95.
- **Sahip:** gizlilik ofisi.

#### 12. Açık bulgu yaşı

- **Tanım:** ciddiyete göre çözülmemiş denetim, düzenleyici veya DSR bulgularının gün cinsinden yaşı.
- **Eşikler (Kritik):** yeşil ≤ 30 gün, sarı 31-60, kırmızı > 60.
- **Eşikler (Yüksek):** yeşil ≤ 60, sarı 61-90, kırmızı > 90.
- **Sahip:** DÖEP sahibi, kırmızıda yürütme sponsoruna eskalasyon.

#### 13. VKDM (DPIA) kapsamı

- **Tanım:** Madde 35 eşiklerini tetikleyen ve dosyada tamamlanmış VKDM bulunan işleme faaliyetlerinin yüzdesi.
- **Tetikleyiciler:** EDPB WP248 dokuz kriter — en az iki tanesi VKDM'yi tetikler. Madde 35(3) zorunlu vakalar da kapsanır.
- **Eşikler:** yeşil ≥ %98, sarı %90-97, kırmızı < %90.
- **Sahip:** gizlilik ofisi.

#### 14. Erişim hakkı yanıt kalitesi

- **Tanım:** yapılandırılmış makine okunabilir özetle yanıtlanan erişim taleplerinin yüzdesi.
- **Eşikler:** yeşil ≥ %90, sarı %80-89, kırmızı < %80.
- **Sahip:** DSR operasyonları.

#### 15. Aydınlatma metni okunabilirliği

- **Tanım:** müşteriye yönelik metinlerin Flesch-Kincaid sınıf seviyesi.
- **Eşik:** hedef ≤ sınıf 9; özet kutuları olan katmanlı metinler önerilir (EDPB Kılavuzu 03/2020 şeffaflık).
- **Sahip:** gizlilik ofisi, içerik ekibi.

#### 16. Alt işleyen değişiklik bildirim SLA'sı

- **Tanım:** işleyen bildirimi ile bizim onay/itiraz penceremiz arasındaki süre.
- **Eşik:** alındıdan iç inceleme kararına ≤ 14 gün.
- **Sahip:** satın alma.

### Aylık pano

Yoğunlaştırılmış aylık görünüm, kataloğu tek sayfaya toplar. Önerilen düzen:

```
+----------------------------------------------------------------+
| GDPR PANOSU — Dönem: YYYY-AA                                    |
+----------------------+-----------------+----------+-------------+
| KPI                  | Mevcut          | Trend    | Durum       |
+----------------------+-----------------+----------+-------------+
| ROPA tazeligi        | %96             | +2 pts   | yesil       |
| DSR ort. yanit       | 14 gun          | sabit    | yesil       |
| DSR SLA asimi        | %0.4            | yukari   | sari        |
| Riza geri cekme      | %3.1            | sabit    | yesil       |
| Cerez tum kabul      | %78             | asagi    | yesil       |
| Ihlal MTTD           | 18s             | asagi    | yesil       |
| Ihlal MTTN           | 0 / 0 pencere   | y/d      | yesil       |
| Egitim tamamlama     | %91             | yukari   | sari        |
| Tedarikci DPA        | %97             | yukari   | sari        |
| TIA tamamlama        | %100            | sabit    | yesil       |
| Acik bulgu (Krit)    | 1 @ 22 gun      | y/d      | yesil       |
| Acik bulgu (Yuksek)  | 4 @ 51 gun      | y/d      | yesil       |
| VKDM kapsami         | %98             | sabit    | yesil       |
+----------------------+-----------------+----------+-------------+
| En riskli: Tedarikci X yeniden degerlendirme gecikmis           |
+----------------------------------------------------------------+
```

### Veri kalitesi ve bütünlüğü

KPI bütünlüğü, disiplinli talep hijyeni, doğru süreç meta verisi ve ROPA için tek doğruluk kaynağına bağlıdır. Aylık raporlama, değerlerin yeniden üretilebilmesi için örnek denetim izleriyle birlikte gelmelidir.

### Raporlama sıklığı

| Paydaş | Sıklık | Format |
|--------|--------|--------|
| DPO ve gizlilik ofisi | haftalık | dönen pano |
| Yürütme komitesi | aylık | trendli tek sayfa skor kartı |
| Denetim komitesi / kurul | çeyreklik | skor kartı artı anlatı ve risk |
| Denetim otoritesi | talep üzerine veya hesap verebilirlik kanıtının parçası | gerektiğinde özetler |

### Anti-desen uyarıları

- Operasyonel kaldıracı olmayan gösteriş metriklerinden kaçının (örn. ham kayıt sayısı). Ham sayıları paydalarla eşleştirin.
- Olgunluk skorlarını ortalama almaktan kaçının — boyut başına en düşükleri izleyin.
- İhlal yanıtı için yalnızca gecikmeli metriklerden kaçının — öncü göstergeler (tatbikat sıklığı) eşit derecede önemlidir.
