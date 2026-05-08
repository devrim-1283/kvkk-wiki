---
Doküman / Document: İdari Tedbirler — Denetim-Hazır Kontrol Listesi / Organizational Measures — Audit-Ready Checklist
Bölüm / Section: 06-idari-tedbirler
Sahip / Owner: İç Denetim / KVKK Sorumlusu / Internal Audit / KVKK Officer
Onaylayan / Approved by: KVKK Komitesi + Denetim Komitesi / KVKK Committee + Audit Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş / Annual + triggered
İlgili Mevzuat / Legal Reference: Law No. 6698 KVKK Art. 12; KVKK Personal Data Security Guide — "Organizational Measures Summary Table"
İlgili Standart / Standard: ISO/IEC 27001:2022 Annex A (especially A.5, A.6); ISO/IEC 27701:2019; NIST CSF 2.0 GOVERN; CIS Controls v8; OECD Privacy Principles
---

## English

# Organizational Measures Checklist

## Use

This list serves as an **audit-ready** reference for internal audit sampling, annual self-assessment, KVKK Committee quarterly review, and external audit preparation. Each row is evaluated as follows:

- **Status:** Yes / No / Partial / Not Applicable (justification written)
- **Evidence:** Document, screenshot, log, ticket no, contract, signature
- **Owner:** Operational owner
- **Last Test:** Date + test type
- **Next Test:** Target date
- **Description / Action:** CAPA reference if missing

ISO 27002:2022 A.x.y references are mapped to each row.

---

## 1. Governance and Policy Framework (10 items)

| # | Control | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 1.1 | Top-level KVKK Policy present, Board of Directors approved, ≤24 months current | A.5.1 | GV.PO |
| 1.2 | Information Security Policy Board of Directors approved, ≤24 months current | A.5.1 | GV.PO |
| 1.3 | KVKK Committee established, members defined, monthly meeting held | A.5.2 | GV.OV |
| 1.4 | KVKK Officer / DPO appointed, independence preserved | A.5.2, A.5.4 | GV.RR |
| 1.5 | Policy hierarchy (top-bottom level) consistent, no conflicts | A.5.1 | GV.PO |
| 1.6 | Document Management System (DMS) versioned, audit trail active | A.5.33 | GV.OC-3 |
| 1.7 | Policy approval chain documented (e-signature / wet) | A.5.1 | GV.PO |
| 1.8 | Old version archive kept for 5 years | A.5.33 | GV.OC-3 |
| 1.9 | Exception register kept, time-bound + with compensating controls | A.5.1 | GV.PO |
| 1.10 | Annual policy review schedule published, 100% completion | A.5.1 | GV.PO |

## 2. Personnel Training and Awareness (8 items)

| # | Control | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 2.1 | Annual training program documented, KVKK Committee approved | A.6.3 | PR.AT |
| 2.2 | General + role-based modules current (≤12 months) | A.6.3 | PR.AT |
| 2.3 | LMS completion rate ≥95% annual | A.6.3 | PR.AT |
| 2.4 | New starter onboarding training is access activation condition | A.6.3 | PR.AT |
| 2.5 | Knowledge test pass threshold ≥80%, measured | A.6.3 | PR.AT |
| 2.6 | Phishing simulation quarterly, KPI reported | A.6.3 | PR.AT |
| 2.7 | Vishing / AI-clone social engineering simulation annual | A.6.3 | PR.AT |
| 2.8 | Vendor/consultant/intern training mandatory, recorded | A.6.3 | PR.AT |

## 3. Confidentiality Undertakings (6 items)

| # | Control | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 3.1 | Employee KVKK and Confidentiality Undertaking template Legal + KVKK Officer approved | A.6.6 | PR.AA |
| 3.2 | All new starters sign within orientation week | A.6.2 | PR.AA |
| 3.3 | Manager / special-category access additional undertakings signed | A.6.6 | PR.AA |
| 3.4 | Intern + consultant + vendor personnel separate variants signed | A.6.6 | PR.AA |
| 3.5 | Signature records personnel file + archive (employment + 10 years) | A.6.5 | GV.OC-3 |
| 3.6 | Re-signing process within 90 days on version change | A.6.6 | PR.AA |

## 4. Vendor (Third Party) Management (12 items)

| # | Control | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 4.1 | Vendor Policy ≤24 months current | A.5.19 | GV.SC |
| 4.2 | All vendors classified (A/B/C/D), inventoried | A.5.19 | ID.SC |
| 4.3 | For Class A/B, Data Processor Contract signed, KVKK Art. 12 minimum elements | A.5.20 | GV.SC |
| 4.4 | Contract template Legal + KVKK Officer approved, ≤12 months current | A.5.20 | GV.SC |
| 4.5 | Sub-processor transparency + change notification flow | A.5.20, A.5.21 | GV.SC |
| 4.6 | Cross-border transfer mechanism specific for each vendor (Art. 9 basis) | A.5.20 | GV.SC |
| 4.7 | Data flow diagram current, consistent with inventory | A.5.21 | ID.AM-7 |
| 4.8 | Annual SOC 2 / ISO 27001 reports collected, reviewed | A.5.22 | GV.SC |
| 4.9 | Penetration test report received annually (Class A) | A.5.22 | GV.SC |
| 4.10 | Quarterly (A) / annual (B/C) review performed, recorded | A.5.22 | GV.SC |
| 4.11 | Approved cloud provider list, BYOK/CMK policy | A.5.23 | GV.SC |
| 4.12 | Standard data return/destruction record used in exit process | A.5.22 | GV.SC |

## 5. Risk Management and DPIA (8 items)

| # | Control | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 5.1 | DPIA Standard documented, ≤24 months current | A.5.34 | GV.RM |
| 5.2 | Risk screening (threshold) integrated into new project process | A.5.34 | GV.RM |
| 5.3 | DPIA trigger list current, compliant with KVKK guides | A.5.34 | GV.RM |
| 5.4 | Risk score matrix calibrated, risk appetite management approved | A.5.34 | GV.RM |
| 5.5 | KVKK Officer writing independent DPIA opinion | A.5.34 | GV.RR |
| 5.6 | KVKK Committee DPIA approval records archived | A.5.34 | GV.OV |
| 5.7 | DPIA-required project / DPIA completion ratio 100% | A.5.34 | GV.RM |
| 5.8 | Annual DPIA review schedule present, 100% completion | A.5.34 | GV.RM |

## 6. Data Subject Rights and Privacy Notice (6 items)

| # | Control | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 6.1 | Privacy Notice Standard documented, contains Art. 10 elements | A.5.34 | GV.OC |
| 6.2 | Web site + mobile + form + call center privacy notice accessible | A.5.34 | GV.OC |
| 6.3 | Explicit consent records timestamped, withdrawal as easy | A.5.34 | GV.OC |
| 6.4 | Data subject application channel (email + form + KEP) published | A.5.34 | GV.OC |
| 6.5 | Application SLA (30 days) achieved 100% | A.5.34 | RS.MA |
| 6.6 | Rejected application reason legal, Art. 13 elements in response | A.5.34 | GV.OC |

## 7. Data Breach Management (5 items)

| # | Control | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 7.1 | Data Breach Management Procedure ≤24 months current | A.5.24 | RS.MA |
| 7.2 | Detection → Committee → 72-hour Authority notification chain documented | A.5.24 | GV.RM |
| 7.3 | Breach record system (chronological, comprehensive) maintained | A.5.27 | RS.AN |
| 7.4 | Annual breach drill performed (tabletop) | A.5.26 | RS.MA |
| 7.5 | Post-breach lessons learned feed back to policy | A.5.27 | ID.IM |

## 8. Retention, Destruction and Data Lifecycle (5 items)

| # | Control | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 8.1 | Retention and Destruction Policy ≤24 months current | A.5.33 | GV.OC-3 |
| 8.2 | Periodic destruction (quarterly) recorded, multi-signature | A.8.10 | GV.OC-3 |
| 8.3 | Destruction flow from backups documented, auditable | A.8.13 | PR.DS-3 |
| 8.4 | Retention period defined for each data category, automatic trigger in system | A.5.33 | GV.OC-3 |
| 8.5 | Key zeroize record in crypto-shred use | A.8.24 | PR.DS-3 |

## 9. VERBİS and Inventory (4 items)

| # | Control | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 9.1 | VERBİS record current, last update ≤6 months | A.5.34 | GV.OC |
| 9.2 | Data inventory live document, quarterly review | A.5.9 | ID.AM-7 |
| 9.3 | Inventory ↔ VERBİS ↔ DPIA consistency audited annually | A.5.9 | ID.AM-7 |
| 9.4 | Inventory update mandatory when new process added (CI gate) | A.5.9 | ID.AM-7 |

## 10. Internal Audit and Continuous Improvement (6 items)

| # | Control | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 10.1 | Internal Audit Charter ≤24 months current, Board of Directors approved | – (Clause 9.2) | GV.OV |
| 10.2 | Annual audit plan risk-based, Audit Committee approved | – (Clause 9.2) | GV.OV |
| 10.3 | KVKK audit topics (§3.2 list) included in annual plan | – (Clause 9.2) | GV.OV |
| 10.4 | Findings in CAPA tool, 90-day past due critical open 0 | – (Clause 10.1) | ID.IM |
| 10.5 | Annual management report submitted to KVKK Committee + Board of Directors | – (Clause 9.3) | GV.OV |
| 10.6 | External audit (ISO, SOC, KVKK) integration and follow-up mechanism | A.5.36 | GV.SC |

## 11. Employee Monitoring, Privacy, Acceptable Use (5 items)

| # | Control | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 11.1 | Employee Privacy Notice current, monitored channels listed, signed annually | A.5.32 | GV.OC |
| 11.2 | DLP / monitoring scope passes KVKK Art. 4 proportionality test | A.5.32, A.8.12 | GV.OC |
| 11.3 | BYOD policy provides work profile / personal data separation | A.7.9 | GV.PO |
| 11.4 | Acceptable Use Policy (AUP) signed | A.5.10 | GV.PO |
| 11.5 | Monitoring data 4-eyes review (CISO + HR + Legal) | A.5.32 | GV.OV |

## 12. Discipline and Sanctions (3 items)

| # | Control | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 12.1 | Discipline Regulation includes information security violation classification | A.6.4 | GV.PO |
| 12.2 | Right of defense + appeal documented in disciplinary process | A.6.4 | GV.PO |
| 12.3 | Breach evidence chain (chain of custody) procedure ready | A.5.28 | RS.AN |

## 13. Communication and Third-Party Notification (4 items)

| # | Control | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 13.1 | Crisis communication plan, spokesperson appointed, media response templates ready | A.5.5, A.5.24 | RS.CO |
| 13.2 | Data subject breach notification template Turkish + English ready | A.5.34 | RS.CO |
| 13.3 | Vendor breach notification flow working in contract and operations | A.5.20 | RS.CO |
| 13.4 | Sectoral regulator (BDDK / CMB / Ministry of Health) notification calendar present | A.5.5 | RS.CO |

## 14. Sectoral and Special Cases (3 items)

| # | Control | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 14.1 | If children's data, additional protections (parental consent process) | A.5.34 | GV.OC |
| 14.2 | Marketing consents IYS compliant, opt-out processes automated | A.5.34 | GV.OC |
| 14.3 | CCTV / camera recording purpose + duration + sharing policy applied | A.7.4 | GV.PO |

---

## Total Items: 85

## Evaluation Score

For each item: Yes=2, Partial=1, No=0, Not Applicable=excluded.

| Maturity | Range | Comment |
|----------|--------|-------|
| **Low** | < 60% | Severe non-compliance risk in KVKK audit |
| **Developing** | 60-75% | Basic compliance present, systematic gaps |
| **Competent** | 75-85% | Acceptable compliance, active improvement |
| **Advanced** | 85-95% | Mature program, above sector average |
| **Optimized** | > 95% | Excellent compliance, leader level |

Target: **Competent (≥75%)** in the first year, **Advanced (≥85%)** in the second year.

## Annual Self-Assessment Flow

```
Q1
   - KVKK Officer prepares evidence collection task plan for the list
   - Owners upload evidence

Q2
   - Internal Audit verifies with sampling
   - Findings processed into CAPA

Q3
   - Results in summary report to KVKK Committee
   - Annual management report prepared

Q4
   - Annual security+privacy posture report to Board of Directors
   - Next year's plan (new target KPI, new control)
```

## CAPA Prioritization

For each **No** or **Partial** row:

| Control Impact | SLA |
|-----------------|-----|
| May be a finding in KVKK Authority audit | 30 days |
| Creates legislative violation risk | 30 days |
| Mandatory under KVKK Art. 12 organizational measure heading | 60 days |
| Missing at the level of good practice | 90 days |
| Opportunity for maturity increase | 180 days |

## Relationship with External Audit

- **If ISO 27001 certification exists:** This list forms the internal audit scope as the KVKK extension of ISO Annex A. Completing self-assessment before ISO LA audit is strong preparation.
- **If pursuing ISO 27701 (PIMS) certification:** Mapping with A.7.x and A.8.x additional controls + this list provides preparation foundation.
- **KVKK Authority audit:** This list is the evidence set of the requested "applied organizational measures" declaration.

## Combined (Technical + Organizational) Score

Evaluated together with [teknik-tedbir-kontrol-listesi.md](../05-teknik-tedbirler/teknik-tedbir-kontrol-listesi.md):

```
Total Items: 88 (Technical) + 85 (Organizational) = 173
```

In the annual report, the KVKK Committee determines overall organizational maturity using the **weighted score of both lists together**. A single list is an inadequate picture — KVKK Art. 12 requires both technical and organizational measures.

## Common Mistakes (Frequent in this List)

- "Policy exists" but "≤24 months not current" — no annual review schedule.
- "Contract signed" but "minimum elements missing" — template not current.
- "Training given" but "completion report missing / exam pass missing" — weak evidence.
- "DPIA performed" but "KVKK Officer opinion missing" — independence questioned.
- "VERBİS current" but "conflicts with inventory" — quick finding in audit.
- "Breach record system exists" but "near-miss events not recorded" — culture issue.
- "Privacy notice exists" but "hidden in mobile view" — Art. 10 violation.
- "Vendor approval done" but "sub-processor change not monitored" — weak transparency.

---

## Türkçe

# İdari Tedbirler Kontrol Listesi

## Kullanım

Bu liste; iç denetim örneklemesi, yıllık öz değerlendirme, KVKK Komitesi çeyreklik gözden geçirme ve dış denetime hazırlık için **denetim-hazır** referanstır. Her satır şu şekilde değerlendirilir:

- **Durum:** Var / Yok / Kısmen / Uygulanamaz (gerekçe yazılır)
- **Kanıt:** Doküman, ekran görüntüsü, log, ticket no, sözleşme, imza
- **Sahibi:** Operasyonel sahip
- **Son Test:** Tarih + test türü
- **Sonraki Test:** Hedef tarih
- **Açıklama / Aksiyon:** Eksiklik varsa CAPA referansı

ISO 27002:2022 A.x.y referansları her satıra eşlenmiştir.

---

## 1. Yönetişim ve Politika Çerçevesi (10 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 1.1 | Üst düzey KVKK Politikası mevcut, Yönetim Kurulu onaylı, ≤24 ay güncel | A.5.1 | GV.PO |
| 1.2 | Bilgi Güvenliği Politikası Yönetim Kurulu onaylı, ≤24 ay güncel | A.5.1 | GV.PO |
| 1.3 | KVKK Komitesi kurulmuş, üyeleri tanımlı, aylık toplantı yapılıyor | A.5.2 | GV.OV |
| 1.4 | KVKK Sorumlusu / DPO atanmış, bağımsızlığı korunuyor | A.5.2, A.5.4 | GV.RR |
| 1.5 | Politika hiyerarşisi (üst-alt seviye) tutarlı, çelişki yok | A.5.1 | GV.PO |
| 1.6 | Doküman Yönetim Sistemi (DMS) versiyonlu, audit trail aktif | A.5.33 | GV.OC-3 |
| 1.7 | Politika onay zinciri belgeli (e-imza / ıslak) | A.5.1 | GV.PO |
| 1.8 | Eski versiyon arşivi 5 yıl saklanıyor | A.5.33 | GV.OC-3 |
| 1.9 | İstisna defteri tutuluyor, süreli + telafi edici kontrollü | A.5.1 | GV.PO |
| 1.10 | Yıllık politika review takvimi yayınlandı, %100 tamamlanma | A.5.1 | GV.PO |

## 2. Personel Eğitim ve Farkındalık (8 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 2.1 | Yıllık eğitim programı yazılı, KVKK Komitesi onaylı | A.6.3 | PR.AT |
| 2.2 | Genel + rol bazlı modüller güncel (≤12 ay) | A.6.3 | PR.AT |
| 2.3 | LMS tamamlanma oranı yıllık ≥%95 | A.6.3 | PR.AT |
| 2.4 | Yeni başlayan onboarding eğitim erişim aktivasyon koşulu | A.6.3 | PR.AT |
| 2.5 | Bilgi testi başarı eşiği ≥%80, ölçülüyor | A.6.3 | PR.AT |
| 2.6 | Phishing simülasyon çeyreklik, KPI raporlu | A.6.3 | PR.AT |
| 2.7 | Vishing / AI-clone sosyal mühendislik simülasyonu yıllık | A.6.3 | PR.AT |
| 2.8 | Tedarikçi/danışman/stajyer eğitim zorunlu, kayıtlı | A.6.3 | PR.AT |

## 3. Gizlilik Taahhütnameleri (6 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 3.1 | Çalışan KVKK ve Gizlilik Taahhütnamesi şablonu Hukuk + KVKK Sorumlusu onaylı | A.6.6 | PR.AA |
| 3.2 | Tüm yeni başlayan oryantasyon haftası içinde imzalıyor | A.6.2 | PR.AA |
| 3.3 | Yönetici / özel nitelikli erişim ek taahhütleri imzalı | A.6.6 | PR.AA |
| 3.4 | Stajyer + danışman + tedarikçi personeli ayrı varyantları imzalı | A.6.6 | PR.AA |
| 3.5 | İmza kayıtları özlük dosyası + arşiv (istihdam + 10 yıl) | A.6.5 | GV.OC-3 |
| 3.6 | Versiyon değişiminde yeniden imza süreci 90 gün içinde | A.6.6 | PR.AA |

## 4. Tedarikçi (Üçüncü Taraf) Yönetimi (12 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 4.1 | Tedarikçi Politikası ≤24 ay güncel | A.5.19 | GV.SC |
| 4.2 | Tüm tedarikçiler sınıflandırılmış (A/B/C/D), envanterli | A.5.19 | ID.SC |
| 4.3 | Sınıf A/B için Veri İşleyen Sözleşmesi imzalı, KVKK m.12 asgari unsurları | A.5.20 | GV.SC |
| 4.4 | Sözleşme şablonu Hukuk + KVKK Sorumlusu onaylı, ≤12 ay güncel | A.5.20 | GV.SC |
| 4.5 | Alt-işleyen şeffaflığı + değişiklik bildirim akışı | A.5.20, A.5.21 | GV.SC |
| 4.6 | Yurt dışı aktarım mekanizması her tedarikçi için belirli (m.9 dayanak) | A.5.20 | GV.SC |
| 4.7 | Veri akış diyagramı güncel, envanterle tutarlı | A.5.21 | ID.AM-7 |
| 4.8 | Yıllık SOC 2 / ISO 27001 raporları toplandı, gözden geçirildi | A.5.22 | GV.SC |
| 4.9 | Sızma testi raporu yıllık alındı (Sınıf A) | A.5.22 | GV.SC |
| 4.10 | Çeyreklik (A) / yıllık (B/C) review yapıldı, kayıtlı | A.5.22 | GV.SC |
| 4.11 | Onaylı bulut sağlayıcı listesi, BYOK/CMK politikası | A.5.23 | GV.SC |
| 4.12 | Çıkış sürecinde veri iade/imha tutanağı standart kullanılıyor | A.5.22 | GV.SC |

## 5. Risk Yönetimi ve DPIA (8 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 5.1 | DPIA Standardı yazılı, ≤24 ay güncel | A.5.34 | GV.RM |
| 5.2 | Risk taraması (threshold) yeni proje sürecine entegre | A.5.34 | GV.RM |
| 5.3 | DPIA tetik listesi güncel, KVKK rehberlerine uyumlu | A.5.34 | GV.RM |
| 5.4 | Risk skor matrisi kalibre, risk iştahı yönetim onaylı | A.5.34 | GV.RM |
| 5.5 | KVKK Sorumlusu DPIA bağımsız görüşü yazıyor | A.5.34 | GV.RR |
| 5.6 | KVKK Komitesi DPIA onay tutanakları arşivli | A.5.34 | GV.OV |
| 5.7 | DPIA gereken proje / DPIA tamamlanan oranı %100 | A.5.34 | GV.RM |
| 5.8 | Yıllık DPIA review takvimi var, %100 tamamlanma | A.5.34 | GV.RM |

## 6. İlgili Kişi Hakları ve Aydınlatma (6 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 6.1 | Aydınlatma Metni Standardı yazılı, m.10 unsurlarını içeriyor | A.5.34 | GV.OC |
| 6.2 | Web sitesi + mobil + form + çağrı merkezi aydınlatma erişilebilir | A.5.34 | GV.OC |
| 6.3 | Açık rıza kayıtları zaman damgalı, geri çekme aynı kolaylıkta | A.5.34 | GV.OC |
| 6.4 | İlgili kişi başvuru kanalı (e-posta + form + KEP) yayınlandı | A.5.34 | GV.OC |
| 6.5 | Başvuru SLA (30 gün) %100 tutturuluyor | A.5.34 | RS.MA |
| 6.6 | Reddedilen başvuru gerekçesi yasal, m.13 unsurları cevapta | A.5.34 | GV.OC |

## 7. Veri İhlali Yönetimi (5 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 7.1 | Veri İhlali Yönetimi Prosedürü ≤24 ay güncel | A.5.24 | RS.MA |
| 7.2 | Tespit → Komite → 72 saat Kurul bildirim zinciri yazılı | A.5.24 | GV.RM |
| 7.3 | İhlal kayıt sistemi (kronolojik, kapsamlı) tutuluyor | A.5.27 | RS.AN |
| 7.4 | İhlal tatbikatı yıllık yapıldı (tabletop) | A.5.26 | RS.MA |
| 7.5 | İhlal sonrası lessons learned politikaya geri besliyor | A.5.27 | ID.IM |

## 8. Saklama, İmha ve Veri Yaşam Döngüsü (5 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 8.1 | Saklama ve İmha Politikası ≤24 ay güncel | A.5.33 | GV.OC-3 |
| 8.2 | Periyodik imha (çeyreklik) tutanaklı, çoklu imza | A.8.10 | GV.OC-3 |
| 8.3 | Yedeklerden imha akışı yazılı, denetlenebilir | A.8.13 | PR.DS-3 |
| 8.4 | Saklama süresi her veri kategorisi için tanımlı, sistemde otomatik tetikli | A.5.33 | GV.OC-3 |
| 8.5 | Crypto-shred kullanımında anahtar zeroize tutanağı | A.8.24 | PR.DS-3 |

## 9. VERBİS ve Envanter (4 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 9.1 | VERBİS kaydı güncel, son güncelleme ≤6 ay | A.5.34 | GV.OC |
| 9.2 | Veri envanteri canlı doküman, çeyreklik review | A.5.9 | ID.AM-7 |
| 9.3 | Envanter ↔ VERBİS ↔ DPIA tutarlılığı yıllık denetlenmiş | A.5.9 | ID.AM-7 |
| 9.4 | Yeni süreç eklendiğinde envanter güncelleme zorunlu (CI gate) | A.5.9 | ID.AM-7 |

## 10. İç Denetim ve Sürekli İyileştirme (6 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 10.1 | İç Denetim Tüzüğü ≤24 ay güncel, Yönetim Kurulu onaylı | – (Clause 9.2) | GV.OV |
| 10.2 | Yıllık denetim planı risk-bazlı, Denetim Komitesi onaylı | – (Clause 9.2) | GV.OV |
| 10.3 | KVKK denetim konuları (§3.2 listesi) yıllık planda yer alıyor | – (Clause 9.2) | GV.OV |
| 10.4 | Bulgular CAPA aracında, 90 gün geçmiş kritik açık 0 | – (Clause 10.1) | ID.IM |
| 10.5 | Yıllık yönetim raporu KVKK Komitesi + Yönetim Kurulu'na sunuldu | – (Clause 9.3) | GV.OV |
| 10.6 | Dış denetim (ISO, SOC, KVKK) entegrasyonu ve takip mekanizması | A.5.36 | GV.SC |

## 11. Çalışan İzleme, Mahremiyet, Kabul Edilebilir Kullanım (5 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 11.1 | Çalışan Aydınlatma Metni güncel, denetlenen kanallar listeli, yıllık imzalı | A.5.32 | GV.OC |
| 11.2 | DLP / izleme kapsamı KVKK m.4 ölçülülük testinden geçti | A.5.32, A.8.12 | GV.OC |
| 11.3 | BYOD politikası iş profili / kişisel veri ayrımını sağlıyor | A.7.9 | GV.PO |
| 11.4 | Kabul Edilebilir Kullanım Politikası (AUP) imzalı | A.5.10 | GV.PO |
| 11.5 | İzleme verisi 4-eyes review (CISO + İK + Hukuk) | A.5.32 | GV.OV |

## 12. Disiplin ve Yaptırım (3 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 12.1 | Disiplin Yönetmeliği bilgi güvenliği ihlal sınıflandırması içeriyor | A.6.4 | GV.PO |
| 12.2 | Disiplin sürecinde savunma + itiraz hakkı yazılı | A.6.4 | GV.PO |
| 12.3 | İhlal kanıt zinciri (chain of custody) prosedürü hazır | A.5.28 | RS.AN |

## 13. İletişim ve Üçüncü Taraf Bilgilendirme (4 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 13.1 | Kriz iletişim planı, sözcü atanmış, medya yanıt şablonları hazır | A.5.5, A.5.24 | RS.CO |
| 13.2 | İlgili kişi ihlal bildirim şablonu Türkçe + İngilizce hazır | A.5.34 | RS.CO |
| 13.3 | Tedarikçi ihlal bildirim akışı sözleşmede ve operasyonda işliyor | A.5.20 | RS.CO |
| 13.4 | Sektörel düzenleyici (BDDK / SPK / Sağlık Bakanlığı) bildirim takvimi var | A.5.5 | RS.CO |

## 14. Sektörel ve Özel Durumlar (3 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 14.1 | Çocuk verisi varsa ek korumalar (ebeveyn rıza süreci) | A.5.34 | GV.OC |
| 14.2 | Pazarlama izinleri İYS uyumlu, opt-out süreçleri otomatik | A.5.34 | GV.OC |
| 14.3 | CCTV / kamera kayıtları amaç + süre + paylaşım politikası uygulanıyor | A.7.4 | GV.PO |

---

## Toplam Madde Sayısı: 85

## Değerlendirme Skoru

Her madde için: Var=2, Kısmen=1, Yok=0, Uygulanamaz=hariç.

| Olgunluk | Aralık | Yorum |
|----------|--------|-------|
| **Düşük** | < 60% | KVKK denetiminde ciddi uyumsuzluk riski |
| **Gelişmekte** | 60-75% | Temel uyum var, sistematik gap'ler |
| **Yetkin** | 75-85% | Kabul edilebilir uyum, aktif iyileştirme |
| **İleri** | 85-95% | Olgun program, sektör ortalaması üstü |
| **Optimize** | > 95% | Mükemmel uyum, lider seviyesi |

Hedef: **Yetkin (≥75%)** birinci yıl, **İleri (≥85%)** ikinci yıl.

## Yıllık Öz-Değerlendirme Akışı

```
Q1
   - KVKK Sorumlusu liste için kanıt toplama görev planı çıkarır
   - Sahipler kanıt yükler

Q2
   - İç Denetim örnekleme ile doğrular
   - Bulgular CAPA'ya işlenir

Q3
   - Sonuçlar KVKK Komitesi'ne özet rapor
   - Yıllık yönetim raporu hazırlanır

Q4
   - Yönetim Kurulu'na yıllık güvenlik+mahremiyet durum raporu
   - Sonraki yıl planı (yeni hedef KPI, yeni kontrol)
```

## CAPA Önceliklendirme

Her **Yok** veya **Kısmen** satırı için:

| Kontrol Etkisi | SLA |
|-----------------|-----|
| KVKK Kurulu denetiminde bulgu olabilir | 30 gün |
| Mevzuat ihlali riski yaratıyor | 30 gün |
| KVKK m.12 idari tedbir başlığında zorunlu | 60 gün |
| İyi uygulama düzeyinde eksik | 90 gün |
| Olgunluk artışı için fırsat | 180 gün |

## Dış Denetim ile İlişki

- **ISO 27001 sertifikası varsa:** bu liste, ISO Annex A'nın KVKK genişletmesi olarak iç denetim kapsamını oluşturur. ISO LA denetiminden önce öz-değerlendirmenin tamamlanması güçlü hazırlıktır.
- **ISO 27701 (PIMS) sertifikasına yönelinirse:** A.7.x ve A.8.x ek kontrolleriyle eşleme + bu liste, hazırlık temelini sağlar.
- **KVKK Kurum denetimi:** bu liste, talep edilen "uygulanan idari tedbirler" beyanının kanıt setidir.

## Birleşik (Teknik + İdari) Skor

[teknik-tedbir-kontrol-listesi.md](../05-teknik-tedbirler/teknik-tedbir-kontrol-listesi.md) ile birlikte değerlendirildiğinde:

```
Toplam Madde: 88 (Teknik) + 85 (İdari) = 173
```

KVKK Komitesi yıllık raporda **iki listenin birlikte ağırlıklı skoru** kullanılarak kurum genel olgunluğu belirlenir. Tek liste yetersiz tablodur — KVKK m.12 hem teknik hem idari tedbir gerektirir.

## Yaygın Hatalar (Bu Listede Sık Çıkan)

- "Politika var" ama "≤24 ay güncel değil" — yıllık review takvimi yok.
- "Sözleşme imzalı" ama "asgari unsurlar eksik" — şablon güncel değil.
- "Eğitim verildi" ama "tamamlanma raporu yok / sınav başarı yok" — kanıt zayıf.
- "DPIA yapıldı" ama "KVKK Sorumlusu görüşü yok" — bağımsızlık sorgulanır.
- "VERBİS güncel" ama "envanter ile çelişiyor" — denetimde hızlı bulgu.
- "İhlal kayıt sistemi var" ama "ramak kala olayları kayda alınmıyor" — kültür sorunu.
- "Aydınlatma metni mevcut" ama "mobil görünümde gizli" — m.10 ihlali.
- "Tedarikçi onayı yapıldı" ama "alt-işleyen değişimi izlenmiyor" — şeffaflık zayıf.
