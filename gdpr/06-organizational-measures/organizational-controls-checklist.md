---
title:
  en: "Organizational Controls Checklist - 60+ Items, ISO 27002 + NIST CSF + GDPR"
  tr: "Organizasyonel Kontroller Kontrol Listesi - 60+ Madde, ISO 27002 + NIST CSF + GDPR"
section: "06-organizational-measures"
document_type: "checklist"
control_id: "ORG-CL-01"
owner:
  primary: "DPO"
  secondary: "CISO, Internal Audit"
review_cycle: "annual"
last_review: "2026-05-08"
next_review: "2027-05-08"
classification: "Internal"
language: ["en", "tr"]
references:
  - "GDPR Art. 5, 24, 25, 28, 29, 32, 33, 34, 35, 36, 37-39, 88"
  - "ISO/IEC 27002:2022"
  - "ISO/IEC 27701:2019"
  - "NIST CSF 2.0 Govern function"
---

## English

# Organizational Controls Checklist

This checklist consolidates the organizational control set across this
domain. It is the companion to
`05-technical-measures/technical-controls-checklist.md`. Use both for:

- Internal audit sampling (`internal-audit.md`).
- Vendor due diligence (`vendor-management.md`).
- DPIA control catalogue (`dpia.md`).
- Annual review and CAPA tracking.

Status legend: `[ ]` not started, `[~]` in progress, `[x]` implemented and
verified.

## A. Governance and Accountability (10 controls)

| # | Control | Source Doc | ISO 27002 | NIST CSF | GDPR | Status |
|---|---------|------------|-----------|----------|------|--------|
| A1 | Board-approved Privacy Policy and Information Security Policy | policies-procedures.md | 5.1 | GV.PO-1 | 24 | [ ] |
| A2 | Documented data protection roles (Controller, Joint, Processor, DPO, CISO, Owners) | README.md | 5.2, 5.3 | GV.RR-1..3 | 24, 26, 28, 37 | [ ] |
| A3 | DPO appointed and contact published; reports to top management | README.md | 5.31 | GV.RR-1 | 37, 38, 39 | [ ] |
| A4 | Information security objectives approved and measured | policies-procedures.md | 5.1 | GV.PO-2 | 24 | [ ] |
| A5 | Risk management approach documented (incl. ENISA methodology) | dpia.md | 5.1 | GV.RM-1 | 24, 32, 35 | [ ] |
| A6 | Risk register reviewed quarterly with executive owner | internal-audit.md | 5.1 | GV.RM-3 | 24 | [ ] |
| A7 | Annual management review (ISO 9.3 equivalent) | internal-audit.md | 5.1 | GV.OV-2 | 24 | [ ] |
| A8 | Three lines of defence operational | README.md, internal-audit.md | n/a | GV.RR | 24, 32, 39 | [ ] |
| A9 | Compliance register linking GDPR to controls | technical-controls-checklist.md, this file | n/a | GV.OC-3 | 24, 5(2) | [ ] |
| A10 | Annual statement / report to the Board on data protection posture | internal-audit.md | n/a | GV.OV-2 | 24, 39(1)(c) | [ ] |

## B. Policies and Procedures (10 controls)

| # | Control | Source Doc | ISO 27002 | NIST CSF | GDPR | Status |
|---|---------|------------|-----------|----------|------|--------|
| B1 | Policy hierarchy documented; mandatory set complete | policies-procedures.md | 5.1 | GV.PO-1 | 24(2) | [ ] |
| B2 | Each policy has owner, version, review cycle, distribution | policies-procedures.md | 5.1 | GV.PO-1 | 24(2) | [ ] |
| B3 | Annual policy review performed; evidence retained | policies-procedures.md | 5.1 | GV.PO-1 | 24(1) | [ ] |
| B4 | Workforce acknowledgement collected for Tier-1 / Tier-2 | policies-procedures.md, training.md | 5.1, 6.3 | PR.AT-1 | 24, 32(4) | [ ] |
| B5 | Privacy Policy on all relevant external touchpoints | policies-procedures.md | 5.1 | GV.PO-1 | 13, 14 | [ ] |
| B6 | Cookie Policy aligned to ePrivacy and consent capture | policies-procedures.md | n/a | GV.PO-1 | 7, ePrivacy | [ ] |
| B7 | Marketing and direct communications policy with opt-out path | policies-procedures.md | n/a | GV.PO-1 | 21, ePrivacy | [ ] |
| B8 | Employee Privacy Notice covers monitoring scope | policies-procedures.md | n/a | GV.PO-1 | 13, 88 | [ ] |
| B9 | CCTV / visual monitoring notice posted and DPIA on file | policies-procedures.md, dpia.md | n/a | GV.PO-1 | 13, 35 | [ ] |
| B10 | Exception register active with time-bound entries | policies-procedures.md | 5.1 | GV.PO-1 | 24 | [ ] |

## C. Training and Awareness (8 controls)

| # | Control | Source Doc | ISO 27002 | NIST CSF | GDPR | Status |
|---|---------|------------|-----------|----------|------|--------|
| C1 | Onboarding training within 30 days; access gated | training.md | 6.3 | PR.AT-1 | 32(4), 39(1)(b) | [ ] |
| C2 | Annual refresher mandatory; >=98 % completion | training.md | 6.3 | PR.AT-1 | 32(4), 39(1)(b) | [ ] |
| C3 | Role-based modules assigned to relevant population | training.md | 6.3 | PR.AT-2 | 32(4) | [ ] |
| C4 | Quarterly phishing simulation with remedial training | training.md | 6.3 | PR.AT-1 | 32(4) | [ ] |
| C5 | DSR-handling drill at least every 6 months | training.md | 6.3 | PR.AT-2 | 12-22 | [ ] |
| C6 | Annual breach-response tabletop including DPO and Legal | training.md | 6.3 | PR.AT-2, RC.RP | 33, 34 | [ ] |
| C7 | Kirkpatrick L1-L3 effectiveness reviewed annually | training.md | 6.3 | GV.OV | 32(4) | [ ] |
| C8 | Training records retained 7 years post-employment | training.md, 04-retention-erasure | 6.3 | PR.AT-1 | 5(2) | [ ] |

## D. Confidentiality and Personnel (6 controls)

| # | Control | Source Doc | ISO 27002 | NIST CSF | GDPR | Status |
|---|---------|------------|-----------|----------|------|--------|
| D1 | Signed confidentiality undertaking on day 1 | confidentiality-undertaking.md | 6.6 | GV.RR-3 | 28(3)(b), 29, 32(4) | [ ] |
| D2 | Re-acknowledgement on material change or every 24 months | confidentiality-undertaking.md | 6.6 | GV.RR-3 | 28(3)(b) | [ ] |
| D3 | Pre-employment screening proportionate to role and law | n/a (refer HR policy) | 6.1 | GV.RR-3 | 5(1)(c), 88 | [ ] |
| D4 | Disciplinary process for breach referenced | confidentiality-undertaking.md, policies-procedures.md | 6.4 | GV.RR-3 | 32(4), 88 | [ ] |
| D5 | Off-boarding checklist covers data return / destruction | confidentiality-undertaking.md, 05-technical-measures/access-control.md | 6.5 | PR.PS-3 | 5(1)(f) | [ ] |
| D6 | Surviving obligations period documented and applied | confidentiality-undertaking.md | 6.6 | GV.RR-3 | 5(1)(f) | [ ] |

## E. Vendor and Processor Management (10 controls)

| # | Control | Source Doc | ISO 27002 | NIST CSF | GDPR | Status |
|---|---------|------------|-----------|----------|------|--------|
| E1 | Vendor classification (V1-V4) maintained | vendor-management.md | 5.19 | GV.SC-1 | 28 | [ ] |
| E2 | DPA with mandatory Article 28 clauses for every processor | vendor-management.md | 5.19, 5.20 | GV.SC-4 | 28(3) | [ ] |
| E3 | Sub-processor list current with notice mechanism | vendor-management.md | 5.21 | GV.SC-5 | 28(2), 28(4) | [ ] |
| E4 | TIA performed and stored for non-adequacy transfers | vendor-management.md, 07-international-transfers | 5.20 | GV.SC | 44-49 | [ ] |
| E5 | SCCs incorporated where required (Module 2/3) | vendor-management.md | 5.20 | GV.SC-4 | 46 | [ ] |
| E6 | Due diligence packages on file (ISO certs, SOC 2, pen test) | vendor-management.md | 5.19 | GV.SC-3 | 28(1) | [ ] |
| E7 | Continuous monitoring (security ratings) for V1-V2 | vendor-management.md | 5.22 | GV.SC-7 | 28 | [ ] |
| E8 | Vendor incident reporting SLAs in DPA tested | vendor-management.md | 5.22 | RS.CO | 33 | [ ] |
| E9 | Audit right exercised on plan for V1 vendors | vendor-management.md, internal-audit.md | 5.22 | GV.SC-7 | 28(3)(h) | [ ] |
| E10 | Exit and certified destruction process tested | vendor-management.md, 05-technical-measures/backup-recovery.md | 5.21 | GV.SC | 5(1)(f), 28 | [ ] |

## F. DPIA and Prior Consultation (6 controls)

| # | Control | Source Doc | ISO 27002 | NIST CSF | GDPR | Status |
|---|---------|------------|-----------|----------|------|--------|
| F1 | DPIA register with every high-risk processing | dpia.md | 5.34 | GV.RM-1 | 35 | [ ] |
| F2 | DPIA performed before processing starts | dpia.md | 5.34 | GV.RM-1 | 35(1) | [ ] |
| F3 | DPO opinion captured on every DPIA | dpia.md | 5.31 | GV.RR-1 | 35(2), 39(1)(c) | [ ] |
| F4 | Prior consultation submitted where high residual risk remains | dpia.md | 5.34 | GV.RM-1 | 36 | [ ] |
| F5 | DPIA refreshed every <=2 years for high-risk processing | dpia.md | 5.34 | GV.RM-1 | 35 | [ ] |
| F6 | Data subjects or representatives consulted where appropriate | dpia.md | 5.34 | GV.RM-1 | 35(9) | [ ] |

## G. Internal Audit (6 controls)

| # | Control | Source Doc | ISO 27002 | NIST CSF | GDPR | Status |
|---|---------|------------|-----------|----------|------|--------|
| G1 | Annual audit plan approved by Audit Committee | internal-audit.md | 9.2 (27001) | GV.OV-1 | 24, 32(1)(d) | [ ] |
| G2 | Mandatory annual audits of ROPA, notice, consent, vendor, retention, DSR, breach, MFA, training, crypto | internal-audit.md | 9.2 (27001) | GV.OV-1 | 24, 32(1)(d) | [ ] |
| G3 | CAPA tracking with severity-based aging tolerance | internal-audit.md | 10.1, 10.2 (27001) | GV.OV-3 | 32(1)(d) | [ ] |
| G4 | Critical findings closed within 30 days | internal-audit.md | 10.1, 10.2 (27001) | GV.OV-3 | 32(1)(d) | [ ] |
| G5 | Independence safeguards in place for Internal Audit | internal-audit.md | n/a | GV.RR | 24 | [ ] |
| G6 | Annual report to Board on data protection control environment | internal-audit.md | 9.3 (27001) | GV.OV-2 | 24, 39(1)(c) | [ ] |

## H. Records, Lawful Basis and Transparency (6 controls)

| # | Control | Source Doc | ISO 27002 | NIST CSF | GDPR | Status |
|---|---------|------------|-----------|----------|------|--------|
| H1 | ROPA accurate and current | 02-ropa | 5.34 | GV.OC | 30 | [ ] |
| H2 | Lawful basis recorded per processing activity | 02-ropa, dpia.md | 5.34 | GV.PO | 6, 9, 10 | [ ] |
| H3 | Privacy notices deployed at all collection touchpoints | 03-transparency-consent | n/a | GV.PO-1 | 13, 14 | [ ] |
| H4 | Consent records auditable and withdrawal supported | 03-transparency-consent, internal-audit.md | n/a | GV.PO-1 | 7 | [ ] |
| H5 | Cookie consent meeting EDPB / national DPA expectations | 03-transparency-consent | n/a | GV.PO-1 | 7, ePrivacy | [ ] |
| H6 | Children's data special handling documented | dpia.md, 03-transparency-consent | 5.34 | GV.PO | 8 | [ ] |

## I. Breach and Incident Management (6 controls)

| # | Control | Source Doc | ISO 27002 | NIST CSF | GDPR | Status |
|---|---------|------------|-----------|----------|------|--------|
| I1 | Incident response plan with breach decision tree | 08-breach-management | 5.24, 5.25 | RS.MA, RS.CO | 33, 34 | [ ] |
| I2 | Article 33 supervisory notification within 72 hours | 08-breach-management | 5.25 | RS.CO-2 | 33 | [ ] |
| I3 | Article 34 data subject communication path tested | 08-breach-management | 5.25 | RS.CO-3 | 34 | [ ] |
| I4 | Internal breach register up to date with closures | 08-breach-management | 5.24 | RS.MA | 33(5) | [ ] |
| I5 | Tabletop exercises tested (annual minimum) | training.md, 08-breach-management | 5.27 | RC.RP | 33, 34 | [ ] |
| I6 | Lessons learned drive CAPA into the controls baseline | internal-audit.md, 08-breach-management | 10.1 | GV.OV-3 | 32(1)(d) | [ ] |

## J. Data Subject Rights and Retention (6 controls)

| # | Control | Source Doc | ISO 27002 | NIST CSF | GDPR | Status |
|---|---------|------------|-----------|----------|------|--------|
| J1 | DSR intake channel(s) advertised and accessible | 09-data-subject-rights | n/a | GV.PO-1 | 12 | [ ] |
| J2 | Identity verification proportionate and documented | 09-data-subject-rights | n/a | PR.AA-3 | 12, 11 | [ ] |
| J3 | DSR fulfilled within statutory timeframe (1 month + extensions) | 09-data-subject-rights, internal-audit.md | n/a | GV.OV | 12(3) | [ ] |
| J4 | Retention schedule maintained with automated deletion | 04-retention-erasure | 8.10 | GV.OC | 5(1)(e) | [ ] |
| J5 | Erasure propagation to backups documented and tested | 04-retention-erasure, 05-technical-measures/backup-recovery.md | 5.34, 8.13 | PR.DS-3 | 17 | [ ] |
| J6 | Automated decision-making safeguards (Art. 22) implemented where applicable | dpia.md, 03-transparency-consent | 5.34 | GV.RM-1 | 22 | [ ] |

## Total

| Domain | Controls |
|--------|----------|
| A. Governance and Accountability | 10 |
| B. Policies and Procedures | 10 |
| C. Training and Awareness | 8 |
| D. Confidentiality and Personnel | 6 |
| E. Vendor and Processor Management | 10 |
| F. DPIA and Prior Consultation | 6 |
| G. Internal Audit | 6 |
| H. Records, Lawful Basis and Transparency | 6 |
| I. Breach and Incident Management | 6 |
| J. Data Subject Rights and Retention | 6 |
| **Total** | **74** |

## Audit Sampling

Internal audit (`internal-audit.md`) samples a risk-weighted subset of
controls each cycle. Coverage rotation ensures every control is examined at
least every two cycles.

## Evidence

Each control has a designated evidence artefact filed under
`11-audit-compliance/evidence/<control_id>/`.

---

## Türkçe

# Organizasyonel Kontroller Kontrol Listesi

Bu kontrol listesi, bu alandaki organizasyonel kontrol setini bir araya
getirir. `05-technical-measures/technical-controls-checklist.md`'in
tamamlayıcısıdır. Her ikisini de şunlar için kullanın:

- İç denetim örneklemesi (`internal-audit.md`).
- Tedarikçi durum tespiti (`vendor-management.md`).
- VKD kontrol kataloğu (`dpia.md`).
- Yıllık inceleme ve CAPA takibi.

Durum açıklaması: `[ ]` başlanmadı, `[~]` devam ediyor, `[x]` uygulandı ve
doğrulandı.

## A. Yönetişim ve Hesap Verebilirlik (10 kontrol)

| # | Kontrol | Kaynak | ISO 27002 | NIST CSF | GDPR | Durum |
|---|---------|--------|-----------|----------|------|-------|
| A1 | Yönetim Kurulu onaylı Gizlilik Politikası ve Bilgi Güvenliği Politikası | policies-procedures.md | 5.1 | GV.PO-1 | 24 | [ ] |
| A2 | Belgelenmiş veri koruma rolleri (Kontrolör, Müşterek, İşleyici, DPO, CISO, Sahipler) | README.md | 5.2, 5.3 | GV.RR-1..3 | 24, 26, 28, 37 | [ ] |
| A3 | DPO atandı ve iletişim bilgileri yayımlandı; üst yönetime raporlar | README.md | 5.31 | GV.RR-1 | 37, 38, 39 | [ ] |
| A4 | Onaylanmış ve ölçülen bilgi güvenliği hedefleri | policies-procedures.md | 5.1 | GV.PO-2 | 24 | [ ] |
| A5 | Belgelenmiş risk yönetimi yaklaşımı (ENISA metodolojisi dahil) | dpia.md | 5.1 | GV.RM-1 | 24, 32, 35 | [ ] |
| A6 | Yürütme sahibiyle üç ayda bir incelenen risk kayıt defteri | internal-audit.md | 5.1 | GV.RM-3 | 24 | [ ] |
| A7 | Yıllık yönetim incelemesi (ISO 9.3 eşdeğeri) | internal-audit.md | 5.1 | GV.OV-2 | 24 | [ ] |
| A8 | Üç savunma hattı operasyonel | README.md, internal-audit.md | yok | GV.RR | 24, 32, 39 | [ ] |
| A9 | GDPR'yi kontrollere bağlayan uyumluluk kayıt defteri | technical-controls-checklist.md, bu dosya | yok | GV.OC-3 | 24, 5(2) | [ ] |
| A10 | Veri koruma duruşu üzerine Yönetim Kuruluna yıllık beyan / rapor | internal-audit.md | yok | GV.OV-2 | 24, 39(1)(c) | [ ] |

## B. Politikalar ve Prosedürler (10 kontrol)

| # | Kontrol | Kaynak | ISO 27002 | NIST CSF | GDPR | Durum |
|---|---------|--------|-----------|----------|------|-------|
| B1 | Politika hiyerarşisi belgelenmiş; zorunlu set tamamlanmış | policies-procedures.md | 5.1 | GV.PO-1 | 24(2) | [ ] |
| B2 | Her politikanın sahibi, sürümü, inceleme döngüsü, dağıtımı | policies-procedures.md | 5.1 | GV.PO-1 | 24(2) | [ ] |
| B3 | Yıllık politika incelemesi yapılmış; kanıt saklanmış | policies-procedures.md | 5.1 | GV.PO-1 | 24(1) | [ ] |
| B4 | Katman-1 / Katman-2 için iş gücü onayı toplanmış | policies-procedures.md, training.md | 5.1, 6.3 | PR.AT-1 | 24, 32(4) | [ ] |
| B5 | Tüm ilgili dış temas noktalarında Gizlilik Politikası | policies-procedures.md | 5.1 | GV.PO-1 | 13, 14 | [ ] |
| B6 | ePrivacy ve onay yakalama ile hizalı Çerez Politikası | policies-procedures.md | yok | GV.PO-1 | 7, ePrivacy | [ ] |
| B7 | Vazgeçme yolu olan Pazarlama ve doğrudan iletişim politikası | policies-procedures.md | yok | GV.PO-1 | 21, ePrivacy | [ ] |
| B8 | İzleme kapsamını kapsayan Çalışan Gizlilik Bildirimi | policies-procedures.md | yok | GV.PO-1 | 13, 88 | [ ] |
| B9 | CCTV / görsel izleme bildirimi yayımlandı ve VKD dosyada | policies-procedures.md, dpia.md | yok | GV.PO-1 | 13, 35 | [ ] |
| B10 | Süreye bağlı girişlerle aktif istisna kayıt defteri | policies-procedures.md | 5.1 | GV.PO-1 | 24 | [ ] |

## C. Eğitim ve Farkındalık (8 kontrol)

| # | Kontrol | Kaynak | ISO 27002 | NIST CSF | GDPR | Durum |
|---|---------|--------|-----------|----------|------|-------|
| C1 | 30 gün içinde onboarding eğitimi; erişim kapı tutulmuş | training.md | 6.3 | PR.AT-1 | 32(4), 39(1)(b) | [ ] |
| C2 | Zorunlu yıllık tazeleme; >=%98 tamamlama | training.md | 6.3 | PR.AT-1 | 32(4), 39(1)(b) | [ ] |
| C3 | İlgili popülasyona atanan rol bazlı modüller | training.md | 6.3 | PR.AT-2 | 32(4) | [ ] |
| C4 | Düzeltme eğitimi ile üç aylık phishing simülasyonu | training.md | 6.3 | PR.AT-1 | 32(4) | [ ] |
| C5 | En az 6 ayda bir DSR-işleme tatbikatı | training.md | 6.3 | PR.AT-2 | 12-22 | [ ] |
| C6 | DPO ve Hukuk dahil yıllık ihlal müdahale masa başı | training.md | 6.3 | PR.AT-2, RC.RP | 33, 34 | [ ] |
| C7 | Yıllık incelenen Kirkpatrick L1-L3 etkinliği | training.md | 6.3 | GV.OV | 32(4) | [ ] |
| C8 | İş ilişkisi sonrası 7 yıl saklanan eğitim kayıtları | training.md, 04-retention-erasure | 6.3 | PR.AT-1 | 5(2) | [ ] |

## D. Gizlilik ve Personel (6 kontrol)

| # | Kontrol | Kaynak | ISO 27002 | NIST CSF | GDPR | Durum |
|---|---------|--------|-----------|----------|------|-------|
| D1 | 1. günde imzalanmış gizlilik taahhütnamesi | confidentiality-undertaking.md | 6.6 | GV.RR-3 | 28(3)(b), 29, 32(4) | [ ] |
| D2 | Maddi değişimde veya 24 ayda yeniden onay | confidentiality-undertaking.md | 6.6 | GV.RR-3 | 28(3)(b) | [ ] |
| D3 | İşe alma öncesi taraması role ve hukuka orantılı | yok (İK politikasına bakın) | 6.1 | GV.RR-3 | 5(1)(c), 88 | [ ] |
| D4 | İhlal için disiplin sürecine referans | confidentiality-undertaking.md, policies-procedures.md | 6.4 | GV.RR-3 | 32(4), 88 | [ ] |
| D5 | Ayrılış kontrol listesi veri iadesi / imhasını kapsar | confidentiality-undertaking.md, 05-technical-measures/access-control.md | 6.5 | PR.PS-3 | 5(1)(f) | [ ] |
| D6 | Devam eden yükümlülükler süresi belgelenmiş ve uygulanmış | confidentiality-undertaking.md | 6.6 | GV.RR-3 | 5(1)(f) | [ ] |

## E. Tedarikçi ve İşleyici Yönetimi (10 kontrol)

| # | Kontrol | Kaynak | ISO 27002 | NIST CSF | GDPR | Durum |
|---|---------|--------|-----------|----------|------|-------|
| E1 | Sürdürülen tedarikçi sınıflandırması (V1-V4) | vendor-management.md | 5.19 | GV.SC-1 | 28 | [ ] |
| E2 | Her işleyici için zorunlu Madde 28 maddeli DPA | vendor-management.md | 5.19, 5.20 | GV.SC-4 | 28(3) | [ ] |
| E3 | Bildirim mekanizmasıyla güncel alt-işleyici listesi | vendor-management.md | 5.21 | GV.SC-5 | 28(2), 28(4) | [ ] |
| E4 | Yeterlilik dışı aktarımlar için yapılan ve saklanan TIA | vendor-management.md, 07-international-transfers | 5.20 | GV.SC | 44-49 | [ ] |
| E5 | Gerektiğinde dahil edilen SCC'ler (Modül 2/3) | vendor-management.md | 5.20 | GV.SC-4 | 46 | [ ] |
| E6 | Dosyada durum tespiti paketleri (ISO sertifikaları, SOC 2, sızma testi) | vendor-management.md | 5.19 | GV.SC-3 | 28(1) | [ ] |
| E7 | V1-V2 için sürekli izleme (güvenlik derecelendirmeleri) | vendor-management.md | 5.22 | GV.SC-7 | 28 | [ ] |
| E8 | DPA'da test edilmiş tedarikçi olay raporlama SLA'ları | vendor-management.md | 5.22 | RS.CO | 33 | [ ] |
| E9 | V1 tedarikçileri için planda kullanılan denetim hakkı | vendor-management.md, internal-audit.md | 5.22 | GV.SC-7 | 28(3)(h) | [ ] |
| E10 | Çıkış ve sertifikalı imha süreci test edilmiş | vendor-management.md, 05-technical-measures/backup-recovery.md | 5.21 | GV.SC | 5(1)(f), 28 | [ ] |

## F. VKD ve Ön Danışma (6 kontrol)

| # | Kontrol | Kaynak | ISO 27002 | NIST CSF | GDPR | Durum |
|---|---------|--------|-----------|----------|------|-------|
| F1 | Her yüksek riskli işleme ile VKD kayıt defteri | dpia.md | 5.34 | GV.RM-1 | 35 | [ ] |
| F2 | İşleme başlamadan önce yapılan VKD | dpia.md | 5.34 | GV.RM-1 | 35(1) | [ ] |
| F3 | Her VKD'de DPO görüşü yakalanmış | dpia.md | 5.31 | GV.RR-1 | 35(2), 39(1)(c) | [ ] |
| F4 | Yüksek kalan risk kaldığında sunulan ön danışma | dpia.md | 5.34 | GV.RM-1 | 36 | [ ] |
| F5 | Yüksek riskli işleme için <=2 yılda yenilenen VKD | dpia.md | 5.34 | GV.RM-1 | 35 | [ ] |
| F6 | Uygun olduğunda istişare edilen veri sahipleri veya temsilciler | dpia.md | 5.34 | GV.RM-1 | 35(9) | [ ] |

## G. İç Denetim (6 kontrol)

| # | Kontrol | Kaynak | ISO 27002 | NIST CSF | GDPR | Durum |
|---|---------|--------|-----------|----------|------|-------|
| G1 | Denetim Komitesi tarafından onaylanan yıllık denetim planı | internal-audit.md | 9.2 (27001) | GV.OV-1 | 24, 32(1)(d) | [ ] |
| G2 | ROPA, bildirim, onay, tedarikçi, saklama, DSR, ihlal, MFA, eğitim, kripto zorunlu yıllık denetimleri | internal-audit.md | 9.2 (27001) | GV.OV-1 | 24, 32(1)(d) | [ ] |
| G3 | Ciddiyet temelli yaşlanma toleransı ile CAPA takibi | internal-audit.md | 10.1, 10.2 (27001) | GV.OV-3 | 32(1)(d) | [ ] |
| G4 | 30 gün içinde kapanan kritik bulgular | internal-audit.md | 10.1, 10.2 (27001) | GV.OV-3 | 32(1)(d) | [ ] |
| G5 | İç Denetim için yürürlükte bağımsızlık güvenceleri | internal-audit.md | yok | GV.RR | 24 | [ ] |
| G6 | Veri koruma kontrol ortamı üzerine Yönetim Kuruluna yıllık rapor | internal-audit.md | 9.3 (27001) | GV.OV-2 | 24, 39(1)(c) | [ ] |

## H. Kayıtlar, Yasal Dayanak ve Şeffaflık (6 kontrol)

| # | Kontrol | Kaynak | ISO 27002 | NIST CSF | GDPR | Durum |
|---|---------|--------|-----------|----------|------|-------|
| H1 | Doğru ve güncel ROPA | 02-ropa | 5.34 | GV.OC | 30 | [ ] |
| H2 | İşleme etkinliği başına kayıtlı yasal dayanak | 02-ropa, dpia.md | 5.34 | GV.PO | 6, 9, 10 | [ ] |
| H3 | Tüm toplama temas noktalarında dağıtılan gizlilik bildirimleri | 03-transparency-consent | yok | GV.PO-1 | 13, 14 | [ ] |
| H4 | Denetlenebilir onay kayıtları ve geri çekme desteklenir | 03-transparency-consent, internal-audit.md | yok | GV.PO-1 | 7 | [ ] |
| H5 | EDPB / ulusal DPA beklentilerini karşılayan çerez onayı | 03-transparency-consent | yok | GV.PO-1 | 7, ePrivacy | [ ] |
| H6 | Çocuk verisi özel işleme belgelenmiş | dpia.md, 03-transparency-consent | 5.34 | GV.PO | 8 | [ ] |

## I. İhlal ve Olay Yönetimi (6 kontrol)

| # | Kontrol | Kaynak | ISO 27002 | NIST CSF | GDPR | Durum |
|---|---------|--------|-----------|----------|------|-------|
| I1 | İhlal karar ağacıyla olay müdahale planı | 08-breach-management | 5.24, 5.25 | RS.MA, RS.CO | 33, 34 | [ ] |
| I2 | 72 saat içinde Madde 33 denetim bildirimi | 08-breach-management | 5.25 | RS.CO-2 | 33 | [ ] |
| I3 | Test edilmiş Madde 34 veri sahibi iletişim yolu | 08-breach-management | 5.25 | RS.CO-3 | 34 | [ ] |
| I4 | Kapanışlarla güncel dahili ihlal kayıt defteri | 08-breach-management | 5.24 | RS.MA | 33(5) | [ ] |
| I5 | Test edilen masa başı tatbikatları (asgari yıllık) | training.md, 08-breach-management | 5.27 | RC.RP | 33, 34 | [ ] |
| I6 | Öğrenilenler kontroller temeline CAPA olarak iter | internal-audit.md, 08-breach-management | 10.1 | GV.OV-3 | 32(1)(d) | [ ] |

## J. Veri Sahibi Hakları ve Saklama (6 kontrol)

| # | Kontrol | Kaynak | ISO 27002 | NIST CSF | GDPR | Durum |
|---|---------|--------|-----------|----------|------|-------|
| J1 | Reklamı yapılan ve erişilebilir DSR alım kanalları | 09-data-subject-rights | yok | GV.PO-1 | 12 | [ ] |
| J2 | Orantılı ve belgelenmiş kimlik doğrulama | 09-data-subject-rights | yok | PR.AA-3 | 12, 11 | [ ] |
| J3 | Yasal süre içinde yerine getirilen DSR (1 ay + uzatmalar) | 09-data-subject-rights, internal-audit.md | yok | GV.OV | 12(3) | [ ] |
| J4 | Otomatik silme ile sürdürülen saklama programı | 04-retention-erasure | 8.10 | GV.OC | 5(1)(e) | [ ] |
| J5 | Yedeklere silme yayılması belgelenmiş ve test edilmiş | 04-retention-erasure, 05-technical-measures/backup-recovery.md | 5.34, 8.13 | PR.DS-3 | 17 | [ ] |
| J6 | Geçerli olduğunda otomatik karar (Md. 22) güvenceleri uygulanmış | dpia.md, 03-transparency-consent | 5.34 | GV.RM-1 | 22 | [ ] |

## Toplam

| Alan | Kontroller |
|------|-----------|
| A. Yönetişim ve Hesap Verebilirlik | 10 |
| B. Politikalar ve Prosedürler | 10 |
| C. Eğitim ve Farkındalık | 8 |
| D. Gizlilik ve Personel | 6 |
| E. Tedarikçi ve İşleyici Yönetimi | 10 |
| F. VKD ve Ön Danışma | 6 |
| G. İç Denetim | 6 |
| H. Kayıtlar, Yasal Dayanak ve Şeffaflık | 6 |
| I. İhlal ve Olay Yönetimi | 6 |
| J. Veri Sahibi Hakları ve Saklama | 6 |
| **Toplam** | **74** |

## Denetim Örneklemesi

İç denetim (`internal-audit.md`), her döngüde risk ağırlıklı bir kontrol
alt kümesini örnekler. Kapsama rotasyonu her kontrolün en az iki döngüde
bir incelenmesini sağlar.

## Kanıt

Her kontrolün `11-audit-compliance/evidence/<control_id>/` altında
dosyalanmış belirlenmiş bir kanıt yapısı vardır.
