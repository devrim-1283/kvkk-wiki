---
Doküman / Document: KVKK Uyum KPI ve Metrikleri / KVKK Compliance KPIs and Metrics
Bölüm / Section: 11-denetim-ve-uyum
Sahip / Owner: KVKK Sorumlusu / KVKK Officer
Onaylayan / Approved by: KVKK Komitesi + Denetim Komitesi — KVKK Committee + Audit Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık (KPI tanımları); Aylık (skor) — Annual (definitions); Monthly (scores)
İlgili Mevzuat / Legal Reference: 6698 sayılı KVKK m.12, m.15, m.16; VERBİS Yön.; Aydınlatma Tebliği; Başvuru Tebliği; İmha Yön. m.11; Veri Güvenliği Rehberi — Law No. 6698 Arts. 12, 15, 16; VERBİS Reg.; Disclosure Communiqué; Application Communiqué; Erasure Reg. Art. 11; Personal Data Security Guide
---

## English

# KVKK Compliance KPIs and Metrics

## 1. Purpose

To make operational compliance performance measurable, traceable and auditable; to detect deviations early and prioritise corrective actions; to provide evidence-based reporting to the Board of Directors and the KVKK Committee.

## 2. KPI Framework

| Category | KPI Count | Frequency |
|----------|-----------|-----------|
| Inventory and Registry | 3 | Monthly |
| Disclosure and Explicit Consent | 4 | Monthly |
| Retention and Destruction | 3 | Semi-annual + monthly tracking |
| Data Subject Requests | 4 | Monthly |
| Breach Management | 5 | Per incident + monthly summary |
| Training and Awareness | 3 | Quarterly |
| Supplier and Transfer | 4 | Quarterly |
| Technical Measures | 4 | Monthly |
| Audit Findings | 2 | Quarterly |

## 3. KPI Definitions (Detail)

### 3.1 Inventory and Registry

#### KPI-EN-01: Inventory Currency Rate

| Field | Value |
|-------|-------|
| Definition | Ratio of processes reviewed in the last 90 days to the total |
| Formula | (Processes updated within last 90 days) / (Total) × 100 |
| Target | ≥ 95% |
| Green / Yellow / Red | ≥95% / 85-95% / <85% |
| Source | GRC tool |
| Owner | Process owner (1st line) + KVKK Officer |

#### KPI-EN-02: VERBİS Notification Lag

| Field | Value |
|-------|-------|
| Definition | Average days between inventory change and VERBİS update |
| Target | ≤ 7 days (VERBİS Reg. Art. 13) |
| Green / Yellow / Red | ≤7 / 8-14 / >14 |
| Source | GRC + VERBİS notification log |
| Owner | KVKK Officer |

#### KPI-EN-03: VERBİS Record Accuracy

| Field | Value |
|-------|-------|
| Definition | Consistency between internal inventory and VERBİS notification (sample-based annual verification) |
| Target | 100% |
| Green / Yellow / Red | 100% / 95-99% / <95% |
| Owner | Internal Audit |

### 3.2 Disclosure and Explicit Consent

#### KPI-AY-01: Disclosure Notice Coverage Rate

| Field | Value |
|-------|-------|
| Definition | Of processes requiring disclosure, the proportion with the notice displayed in channel |
| Target | ≥ 98% |
| Green / Yellow / Red | ≥98% / 90-98% / <90% |

#### KPI-AY-02: Legal Sign-Off on Disclosure Notices

| Field | Value |
|-------|-------|
| Definition | Proportion of live disclosure notices with legal sign-off |
| Target | 100% |

#### KPI-AR-01: Explicit Consent Withdrawal Rate

| Field | Value |
|-------|-------|
| Definition | Percentage of active consents withdrawn during the month |
| Target | Monitoring (no threshold); sudden spikes trigger alert |
| Alert | Month-over-month > 30% rise → root cause analysis |
| Source | CMP (Consent Management Platform) |

#### KPI-AR-02: Withdrawal Response Time

| Field | Value |
|-------|-------|
| Definition | Time from consent withdrawal to processing stop |
| Target | ≤ 24 hours (automated systems), ≤ 7 days (operational) |

### 3.3 Retention and Destruction

#### KPI-IM-01: Periodic Destruction Execution Rate

| Field | Value |
|-------|-------|
| Definition | Adherence to the planned periodic destruction calendar (January and July, Erasure Reg. Art. 11/2) |
| Formula | (Destruction performed on time) / (Planned) × 100 |
| Target | 100% |
| Green / Yellow / Red | 100% / 95-99% / <95% |

#### KPI-IM-02: Destruction Lag Time

| Field | Value |
|-------|-------|
| Definition | Days of delay for data whose retention period has expired |
| Target | ≤ 180 days (Erasure Reg. Art. 11/2) |
| Green / Yellow / Red | ≤180 / 181-270 / >270 |

#### KPI-IM-03: Destruction Minutes Coverage

| Field | Value |
|-------|-------|
| Definition | Proportion of destruction operations with minutes drawn up and retained for 3 years |
| Target | 100% (Erasure Reg. Arts. 7/3, 8/3, 9/3) |

### 3.4 Data Subject Requests

#### KPI-BV-01: Request Volume (Trend)

| Field | Value |
|-------|-------|
| Definition | Monthly count of DSRs by category (information, correction, erasure, objection, portability, automated decision, damages) |
| Target | Monitoring; spikes trigger alert |

#### KPI-BV-02: Average Response Time

| Field | Value |
|-------|-------|
| Definition | Average days from request to response |
| Target | ≤ 15 days (Law Art. 13/2: 30 days max) |
| Green / Yellow / Red | ≤15 / 16-25 / >25 |

#### KPI-BV-03: SLA Met Rate

| Field | Value |
|-------|-------|
| Definition | Proportion of requests resolved within 30 days |
| Target | ≥ 98% |
| Red | <95% |

#### KPI-BV-04: Authority Escalation Rate

| Field | Value |
|-------|-------|
| Definition | Proportion of total requests escalated to the Authority after the Company's response |
| Target | ≤ 2% |
| Green / Yellow / Red | ≤2% / 2-5% / >5% |

### 3.5 Breach Management

#### KPI-IH-01: Breach Count

| Field | Value |
|-------|-------|
| Definition | Quarterly detected breaches by category (external attack, internal error, supplier, physical, loss/theft) |
| Target | Monitoring; zero target unrealistic; trend and classification critical |

#### KPI-IH-02: MTTD (Mean Time To Detect)

| Field | Value |
|-------|-------|
| Definition | Average time from breach occurrence to detection |
| Target | ≤ 24 hours |
| Green / Yellow / Red | ≤24h / 24-72h / >72h |

#### KPI-IH-03: MTTN (Mean Time To Notify Authority)

| Field | Value |
|-------|-------|
| Definition | Time from detection to Authority notification |
| Target | ≤ 72 hours (Law Art. 12/5, Authority Decision 2019/10) |
| Red | >72h — written justification required |

#### KPI-IH-04: MTTR (Mean Time To Resolve)

| Field | Value |
|-------|-------|
| Definition | Time from detection to breach closure |
| Target | ≤ 30 days (critical breach: ≤7 days) |

#### KPI-IH-05: Exercise Frequency and Success

| Field | Value |
|-------|-------|
| Definition | Annual count of incident response exercises and adherence to target times |
| Target | ≥ 2 exercises/year, ≥80% adherence |

### 3.6 Training and Awareness

#### KPI-EG-01: Training Completion Rate

| Field | Value |
|-------|-------|
| Definition | Completion rate of assigned KVKK training (role-based) |
| Target | ≥ 95% (general); 100% (critical roles: HR, IT, call centre, legal, sales) |

#### KPI-EG-02: Phishing Simulation Click Rate

| Field | Value |
|-------|-------|
| Definition | Proportion of employees clicking the malicious link in phishing simulations |
| Target | ≤ 5% |
| Green / Yellow / Red | ≤5% / 5-10% / >10% |

#### KPI-EG-03: Knowledge Test Pass Rate

| Field | Value |
|-------|-------|
| Definition | Pass rate of post-training knowledge test (≥80% to pass) |
| Target | ≥ 90% |

### 3.7 Supplier and Transfer

#### KPI-TD-01: Supplier Due Diligence Coverage

| Field | Value |
|-------|-------|
| Definition | Proportion of suppliers processing/receiving personal data with completed DPIA + security questionnaire |
| Target | 100% (high risk); ≥95% (medium) |

#### KPI-TD-02: DPA Coverage Rate

| Field | Value |
|-------|-------|
| Definition | Proportion of personal-data-receiving suppliers with signed DPA |
| Target | 100% |

#### KPI-TD-03: Cross-Border Transfer Count and TIA Rate

| Field | Value |
|-------|-------|
| Definition | Count of active cross-border transfers; proportion with completed TIA |
| Target | TIA completion: 100% |

#### KPI-TD-04: Standard Contract Authority Notification Lag

| Field | Value |
|-------|-------|
| Definition | Time from signature to Authority notification |
| Target | ≤ 5 business days (Art. 9/5, Authority Decision 2024/959) |
| Red | >5 business days |

### 3.8 Technical Measures

#### KPI-TT-01: Patch Compliance

| Field | Value |
|-------|-------|
| Definition | Time from critical patch release to deployment |
| Target | ≤ 7 days (critical); ≤ 30 days (high) |

#### KPI-TT-02: Privileged Account Coverage

| Field | Value |
|-------|-------|
| Definition | Proportion of privileged accounts under PAM; MFA mandatory |
| Target | 100% |

#### KPI-TT-03: Encryption Coverage

| Field | Value |
|-------|-------|
| Definition | Proportion of stores containing personal data with rest+transit encryption applied |
| Target | 100% (mandatory for sensitive data — Authority Decision 2018/10) |

#### KPI-TT-04: Penetration Test Finding Closure

| Field | Value |
|-------|-------|
| Definition | Proportion of critical+high penetration test findings closed within 90 days |
| Target | 100% |

### 3.9 Audit Findings

#### KPI-DN-01: Open Finding Count

| Field | Value |
|-------|-------|
| Definition | Open internal + external audit findings, by criticality |
| Target | Open critical findings = 0 |

#### KPI-DN-02: Finding Closure Time

| Field | Value |
|-------|-------|
| Definition | Days from finding to closure |
| Target | Critical ≤30 days, High ≤90 days, Medium ≤180 days |

## 4. Threshold Colour Coding

| Colour | Meaning | Escalation |
|--------|---------|------------|
| Green | On target | Informational; trend monitored |
| Yellow | Approaching threshold / partial deviation | Corrective action plan within 30 days |
| Red | Threshold breached / critical deviation | KVKK Committee within 7 days, Board within 30 days |

## 5. Monthly Dashboard Layout

```
+----------------------------------------+
|   KVKK COMPLIANCE DASHBOARD - [MM/YY]  |
+----------------------------------------+
| Overall Maturity Score: 3.7 / 5.0 [↑]  |
| Previous Month: 3.5                    |
+----------------------------------------+
| HIGHLIGHTED KPIs                       |
| - Inventory Currency:        96% [G]   |
| - VERBİS Notification Lag:    5 [G]    |
| - Periodic Destruction:     100% [G]   |
| - Request SLA Met:         98.4% [G]   |
| - MTTD:                      36 h [Y]  |
| - MTTN:                      48 h [G]  |
| - Training Completion:        93% [Y]  |
| - Phishing Click Rate:       7.2% [Y]  |
| - Open Critical Findings:      1 [R]   |
+----------------------------------------+
| RED ALERTS                             |
| - DN-01: TT-PAM coverage 92% (critical)|
| - Action: complete by end of Q3        |
| - Owner: CISO                          |
+----------------------------------------+
| MONTH'S EVENTS                         |
| - 2 breaches (1 low, 1 medium)         |
| - 1 Authority notification (medium-48h)|
| - 142 data subject requests            |
+----------------------------------------+
```

## 6. Executive Report (Quarterly)

| Section | Content |
|---------|---------|
| Executive Summary | 1 page, three highlights, three risks, three wins |
| Maturity Trend | Quarter-over-quarter change graph by dimension |
| KPI Scorecard | All KPIs, threshold status, trend arrows |
| Incident Summary | Breaches, requests, Authority correspondence |
| Regulatory Impact | Regulatory changes within the quarter and impact analysis |
| Budget and Resources | Consumption, additional requests |
| Annex: Evidence List | References supporting the report |

## 7. Data Quality and Verification

- All KPIs are auto-generated from the GRC platform; manual interventions leave an audit trail.
- Quarterly 2nd line verification (sampling).
- Annual 3rd line (Internal Audit) independent verification.
- On anomaly: root cause analysis within 14 days, correction within 30 days.

## 8. Annual KPI Review

KPI definitions are reviewed annually. Triggers:
- Regulatory change
- Significant business process change
- Industry best practice
- Authority decision / fine on a peer organisation

## 9. Related Documents

- [uyum-olgunluk-modeli.md](uyum-olgunluk-modeli.md)
- [ic-denetim-prosedur.md](ic-denetim-prosedur.md)
- [../08-ihlal-yonetimi/](../08-ihlal-yonetimi/)
- [../09-ilgili-kisi-basvurulari/](../09-ilgili-kisi-basvurulari/)

---

## Türkçe

# KVKK Uyum KPI ve Metrikleri

## 1. Amaç

Operasyonel uyum performansını ölçülebilir, izlenebilir, denetlenebilir hale getirmek; sapmaların erken tespiti ve düzeltici aksiyonların önceliklendirilmesini sağlamak; Yönetim Kurulu ve KVKK Komitesine kanıta dayalı raporlama sunmak.

## 2. KPI Çerçevesi

| Kategori | KPI Sayısı | Frekans |
|----------|------------|---------|
| Envanter ve Sicil | 3 | Aylık |
| Aydınlatma ve Açık Rıza | 4 | Aylık |
| Saklama ve İmha | 3 | 6 Aylık + Aylık takip |
| İlgili Kişi Başvurusu | 4 | Aylık |
| İhlal Yönetimi | 5 | Olay bazlı + Aylık özet |
| Eğitim ve Farkındalık | 3 | Çeyreklik |
| Tedarikçi ve Aktarım | 4 | Çeyreklik |
| Teknik Tedbirler | 4 | Aylık |
| Denetim Bulguları | 2 | Çeyreklik |

## 3. KPI Tanımları (Detay)

### 3.1 Envanter ve Sicil

#### KPI-EN-01: Envanter Güncellik Oranı

| Alan | Değer |
|------|-------|
| Tanım | Son 90 gün içinde gözden geçirilmiş süreçlerin toplam süreç sayısına oranı |
| Formül | (Son 90 gün içinde güncellenmiş süreç) / (Toplam süreç) × 100 |
| Hedef | ≥ %95 |
| Yeşil / Sarı / Kırmızı | ≥%95 / %85-95 / <%85 |
| Veri Kaynağı | GRC aracı |
| Sahip | Süreç sahibi (1. hat) + KVKK Sorumlusu |

#### KPI-EN-02: VERBİS Bildirim Gecikmesi

| Alan | Değer |
|------|-------|
| Tanım | Envanter değişiklik tarihi ile VERBİS güncelleme tarihi arasındaki ortalama gün |
| Hedef | ≤ 7 gün (VERBİS Yön. m.13) |
| Yeşil / Sarı / Kırmızı | ≤7 / 8-14 / >14 |
| Veri Kaynağı | GRC + VERBİS bildirim kayıt defteri |
| Sahip | KVKK Sorumlusu |

#### KPI-EN-03: VERBİS Kayıt Doğruluğu

| Alan | Değer |
|------|-------|
| Tanım | İç envanter ile VERBİS bildirimi arasındaki tutarlılık (örnekleme ile yıllık doğrulama) |
| Hedef | %100 |
| Yeşil / Sarı / Kırmızı | %100 / %95-99 / <%95 |
| Sahip | İç Denetim |

### 3.2 Aydınlatma ve Açık Rıza

#### KPI-AY-01: Aydınlatma Metni Kapsama Oranı

| Alan | Değer |
|------|-------|
| Tanım | Hukuki sebep gerektiren ve aydınlatma yapılması zorunlu süreçlerden, kanalda gösterilen aydınlatma metni mevcut olanların oranı |
| Hedef | ≥ %98 |
| Yeşil / Sarı / Kırmızı | ≥%98 / %90-98 / <%90 |

#### KPI-AY-02: Aydınlatma Metni Hukuk Onayı

| Alan | Değer |
|------|-------|
| Tanım | Yayında olan aydınlatma metinlerinden hukuk birimi onayı bulunanların oranı |
| Hedef | %100 |

#### KPI-AR-01: Açık Rıza Geri Alma Oranı

| Alan | Değer |
|------|-------|
| Tanım | Aktif rızalar üzerinden ay içinde geri alınan rıza yüzdesi |
| Hedef | İzleme amaçlı (eşik yok); ani artış uyarı tetikler |
| Uyarı | Ay/ay > %30 artış → kök neden analizi |
| Veri Kaynağı | CMP (Consent Management Platform) |

#### KPI-AR-02: Geri Alma Cevap Süresi

| Alan | Değer |
|------|-------|
| Tanım | Açık rıza geri alma talebinden veri işlemenin durdurulmasına kadar geçen süre |
| Hedef | ≤ 24 saat (otomatik sistemler), ≤ 7 gün (operasyonel) |

### 3.3 Saklama ve İmha

#### KPI-IM-01: Periyodik İmha Gerçekleşme Oranı

| Alan | Değer |
|------|-------|
| Tanım | Planlanmış periyodik imha takvimine uyum (Ocak ve Temmuz, İmha Yön. m.11/2) |
| Formül | (Zamanında gerçekleşen imha) / (Planlanan imha) × 100 |
| Hedef | %100 |
| Yeşil / Sarı / Kırmızı | %100 / %95-99 / <%95 |

#### KPI-IM-02: İmha Gecikme Süresi

| Alan | Değer |
|------|-------|
| Tanım | Saklama süresi dolan veriler için imha gecikmesi (gün) |
| Hedef | ≤ 180 gün (İmha Yön. m.11/2) |
| Yeşil / Sarı / Kırmızı | ≤180 / 181-270 / >270 |

#### KPI-IM-03: İmha Tutanağı Kapsama

| Alan | Değer |
|------|-------|
| Tanım | Tüm imha işlemlerinden tutanağı düzenlenmiş ve 3 yıl saklanan oranı |
| Hedef | %100 (İmha Yön. m.7/3, m.8/3, m.9/3) |

### 3.4 İlgili Kişi Başvurusu

#### KPI-BV-01: Başvuru Sayısı (Trend)

| Alan | Değer |
|------|-------|
| Tanım | Aylık ilgili kişi başvuru sayısı (kategori bazlı: bilgi, düzeltme, silme, itiraz, taşınabilirlik, otomatik karara itiraz, zarar) |
| Hedef | İzleme; ani artış uyarı |

#### KPI-BV-02: Ortalama Yanıt Süresi

| Alan | Değer |
|------|-------|
| Tanım | Başvurudan cevaba kadar geçen ortalama gün sayısı |
| Hedef | ≤ 15 gün (Kanun m.13/2: 30 gün üst sınır) |
| Yeşil / Sarı / Kırmızı | ≤15 / 16-25 / >25 |

#### KPI-BV-03: SLA İçinde Tamamlama Oranı

| Alan | Değer |
|------|-------|
| Tanım | 30 gün içinde sonuçlanan başvuru oranı |
| Hedef | ≥ %98 |
| Kırmızı | <%95 |

#### KPI-BV-04: Kurul'a Gitme Oranı

| Alan | Değer |
|------|-------|
| Tanım | Şirket cevabından sonra Kurul'a şikâyet ile giden başvuru sayısının toplam başvuruya oranı |
| Hedef | ≤ %2 |
| Yeşil / Sarı / Kırmızı | ≤%2 / %2-5 / >%5 |

### 3.5 İhlal Yönetimi

#### KPI-IH-01: İhlal Sayısı

| Alan | Değer |
|------|-------|
| Tanım | Çeyreklik tespit edilen veri ihlali sayısı (kategori: dış saldırı, iç hata, tedarikçi, fiziksel, kayıp/çalıntı) |
| Hedef | İzleme; sıfırlama hedefi gerçekçi değil; trend ve sınıflandırma kritik |

#### KPI-IH-02: MTTD (Mean Time To Detect)

| Alan | Değer |
|------|-------|
| Tanım | İhlalin gerçekleşmesinden tespit edilmesine kadar geçen ortalama süre |
| Hedef | ≤ 24 saat |
| Yeşil / Sarı / Kırmızı | ≤24sa / 24-72sa / >72sa |

#### KPI-IH-03: MTTN (Mean Time To Notify Kurul)

| Alan | Değer |
|------|-------|
| Tanım | Tespit'ten Kurul bildirimine kadar geçen süre |
| Hedef | ≤ 72 saat (Kanun m.12/5, Kurul kararı 2019/10) |
| Kırmızı | >72 saat — gerekçeli açıklama zorunlu |

#### KPI-IH-04: MTTR (Mean Time To Resolve)

| Alan | Değer |
|------|-------|
| Tanım | Tespit'ten ihlal sonlandırmaya kadar geçen süre |
| Hedef | ≤ 30 gün (kritik ihlal: ≤7 gün) |

#### KPI-IH-05: Tatbikat Sıklığı ve Başarısı

| Alan | Değer |
|------|-------|
| Tanım | Yıllık ihlal müdahale tatbikat sayısı, hedef sürelere uyum yüzdesi |
| Hedef | ≥ 2 tatbikat/yıl, ≥%80 hedeflere uyum |

### 3.6 Eğitim ve Farkındalık

#### KPI-EG-01: Eğitim Tamamlama Oranı

| Alan | Değer |
|------|-------|
| Tanım | Atanan KVKK eğitiminin tamamlanma oranı (rol bazlı) |
| Hedef | ≥ %95 (genel); %100 (kritik roller: İK, BT, çağrı merkezi, hukuk, satış) |

#### KPI-EG-02: Phishing Simülasyon Tıklama Oranı

| Alan | Değer |
|------|-------|
| Tanım | Phishing simülasyonunda zararlı bağlantıya tıklayan çalışan oranı |
| Hedef | ≤ %5 |
| Yeşil / Sarı / Kırmızı | ≤%5 / %5-10 / >%10 |

#### KPI-EG-03: Bilgi Testi Başarı Oranı

| Alan | Değer |
|------|-------|
| Tanım | Yıllık eğitim sonrası bilgi testi başarı oranı (≥%80 başarılı) |
| Hedef | ≥ %90 |

### 3.7 Tedarikçi ve Aktarım

#### KPI-TD-01: Tedarikçi Due Diligence Kapsama

| Alan | Değer |
|------|-------|
| Tanım | Kişisel veri işleyen / aktarılan tedarikçilerden due diligence (DPIA + güvenlik anketi) tamamlanmış oranı |
| Hedef | %100 (yüksek riskli); ≥%95 (orta) |

#### KPI-TD-02: DPA Kapsama Oranı

| Alan | Değer |
|------|-------|
| Tanım | Kişisel veri aktarılan tedarikçilerden veri işleyen sözleşmesi (DPA) imzalanmış oranı |
| Hedef | %100 |

#### KPI-TD-03: Yurt Dışı Aktarım Sayısı ve TIA Oranı

| Alan | Değer |
|------|-------|
| Tanım | Aktif yurt dışı aktarım sayısı; bunlardan TIA (Transfer Impact Assessment) tamamlanmış oranı |
| Hedef | TIA tamamlama: %100 |

#### KPI-TD-04: Standart Sözleşme Kurul Bildirim Gecikmesi

| Alan | Değer |
|------|-------|
| Tanım | İmza tarihinden Kurul bildirimine kadar geçen süre |
| Hedef | ≤ 5 iş günü (m.9/5, Kurul kararı 2024/959) |
| Kırmızı | >5 iş günü |

### 3.8 Teknik Tedbirler

#### KPI-TT-01: Yama Uyumu

| Alan | Değer |
|------|-------|
| Tanım | Kritik güvenlik yamalarının yayın tarihinden uygulanmasına kadar geçen süre |
| Hedef | ≤ 7 gün (kritik); ≤ 30 gün (yüksek) |

#### KPI-TT-02: Ayrıcalıklı Hesap Kapsama

| Alan | Değer |
|------|-------|
| Tanım | Ayrıcalıklı hesapların PAM kapsamına alınma oranı; MFA zorunlu |
| Hedef | %100 |

#### KPI-TT-03: Şifreleme Kapsama

| Alan | Değer |
|------|-------|
| Tanım | Kişisel veri içeren depolardan rest+transit şifreleme uygulanmış oranı |
| Hedef | %100 (özel nitelikli veri için zorunlu — Kurul kararı 2018/10) |

#### KPI-TT-04: Sızma Testi Bulgusu Kapatma

| Alan | Değer |
|------|-------|
| Tanım | Sızma testinde tespit edilen kritik+yüksek bulguların 90 gün içinde kapatılma oranı |
| Hedef | %100 |

### 3.9 Denetim Bulguları

#### KPI-DN-01: Açık Bulgu Sayısı

| Alan | Değer |
|------|-------|
| Tanım | İç denetim + dış denetim açık bulguları, kritiklik bazında |
| Hedef | Kritik açık bulgu = 0 |

#### KPI-DN-02: Bulgu Kapatma Süresi

| Alan | Değer |
|------|-------|
| Tanım | Bulgu tarihi → kapatma tarihi |
| Hedef | Kritik ≤30 gün, Yüksek ≤90 gün, Orta ≤180 gün |

## 4. Eşik Renk Kodlaması

| Renk | Anlam | Eskalasyon |
|------|-------|------------|
| Yeşil | Hedefe uygun | Bilgi amaçlı; trend izlenir |
| Sarı | Eşiğe yaklaşıyor / kısmi sapma | Düzeltici aksiyon planı 30 gün içinde |
| Kırmızı | Eşik aşıldı / kritik sapma | KVKK Komitesi 7 gün içinde, Yönetim Kurulu 30 gün içinde bilgilendirilir |

## 5. Aylık Dashboard Yapısı

```
+----------------------------------------+
|   KVKK UYUM DASHBOARD - [Ay/Yıl]       |
+----------------------------------------+
| Genel Olgunluk Skoru: 3.7 / 5.0   [↑]  |
| Ay Önceki: 3.5                         |
+----------------------------------------+
| ÖNE ÇIKAN KPI'LAR                      |
| - Envanter Güncellik:        96% [Y]   |
| - VERBİS Bildirim Gecikme:    5 [Y]    |
| - Periyodik İmha:            100% [Y]  |
| - Başvuru SLA İçinde:        98.4% [Y] |
| - MTTD:                      36 sa [S] |
| - MTTN:                      48 sa [Y] |
| - Eğitim Tamamlama:           93% [S]  |
| - Phishing Tıklama:          7.2% [S]  |
| - Açık Kritik Bulgu:           1 [K]   |
+----------------------------------------+
| KIRMIZI ALARMLAR                       |
| - DN-01: TT-PAM kapsama %92 (kritik)   |
| - Aksiyon: Q3 sonuna kadar tamamlama   |
| - Sahip: CISO                          |
+----------------------------------------+
| AY İÇİNDE OLAYLAR                      |
| - 2 ihlal (1 düşük, 1 orta)            |
| - Kurul'a 1 bildirim (orta - 48 saat)  |
| - 142 ilgili kişi başvurusu            |
+----------------------------------------+
```

## 6. Üst Yönetim Raporu (Çeyreklik)

| Bölüm | İçerik |
|-------|--------|
| Yönetici Özeti | 1 sayfa, üç vurgu, üç risk, üç kazanım |
| Olgunluk Trendi | Boyut bazlı çeyrek/çeyrek değişim grafiği |
| KPI Skorkartı | Tüm KPI'lar, eşik durumu, trend okları |
| Olay Özeti | İhlaller, başvurular, Kurul yazışmaları |
| Mevzuat Etkisi | Çeyrek içinde değişen mevzuat ve etki analizi |
| Bütçe ve Kaynak | Tüketim, ek talep |
| Ek: Kanıt Listesi | Raporu destekleyen kanıt referansları |

## 7. Veri Kalitesi ve Doğrulama

- Tüm KPI'lar GRC platformundan otomatik üretilir; manuel müdahale denetim izi bırakır.
- Çeyreklik 2. hat doğrulaması (örnekleme).
- Yıllık 3. hat (İç Denetim) bağımsız doğrulama.
- Aykırılık tespit edilirse: kök neden analizi 14 gün, düzeltme 30 gün.

## 8. KPI Yıllık Gözden Geçirme

KPI tanımları yıllık olarak gözden geçirilir. Tetikleyiciler:
- Mevzuat değişikliği
- İş süreçlerindeki köklü değişim
- Sektör en iyi uygulamaları
- Kurul kararı / cezası alan benzer şirket örneği

## 9. İlgili Dokümanlar

- [uyum-olgunluk-modeli.md](uyum-olgunluk-modeli.md)
- [ic-denetim-prosedur.md](ic-denetim-prosedur.md)
- [../08-ihlal-yonetimi/](../08-ihlal-yonetimi/)
- [../09-ilgili-kisi-basvurulari/](../09-ilgili-kisi-basvurulari/)
