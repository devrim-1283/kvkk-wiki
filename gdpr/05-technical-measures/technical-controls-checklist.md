---
title:
  en: "Technical Controls Checklist - 80+ Items, ISO 27002:2022 + NIST CSF 2.0 + GDPR Art. 32"
  tr: "Teknik Kontroller Kontrol Listesi - 80+ Madde, ISO 27002:2022 + NIST CSF 2.0 + GDPR Md. 32"
section: "05-technical-measures"
document_type: "checklist"
control_id: "TECH-CL-01"
owner:
  primary: "CISO"
  secondary: "Internal Audit"
review_cycle: "annual"
last_review: "2026-05-08"
next_review: "2027-05-08"
classification: "Internal"
language: ["en", "tr"]
references:
  - "GDPR Art. 24, 25, 32"
  - "ISO/IEC 27002:2022"
  - "NIST CSF 2.0"
  - "ENISA Handbook on Security of Personal Data Processing"
---

## English

# Technical Controls Checklist

This checklist consolidates the technical control set across this domain.
Each row identifies a control, the responsible document in this wiki, and
the cross-mappings to ISO/IEC 27002:2022, NIST CSF 2.0 and GDPR Article 32.

Use the checklist as the basis for:

- Internal audit sampling (`06-organizational-measures/internal-audit.md`).
- Vendor due diligence (`06-organizational-measures/vendor-management.md`).
- DPIA control catalogue (`06-organizational-measures/dpia.md`).
- Annual TOM review.

Status legend: `[ ]` not started, `[~]` in progress, `[x]` implemented and
verified.

## A. Identity and Access Control (12 controls)

| # | Control | Source Doc | ISO 27002 | NIST CSF | GDPR | Status |
|---|---------|------------|-----------|----------|------|--------|
| A1 | Identity directory authoritative for HR-driven JML | access-control.md | 5.16 | PR.AA-1 | 32(1)(b) | [ ] |
| A2 | Joiner provisioning SLA <=1 business day | access-control.md | 5.16 | PR.AA-1 | 32(1)(b) | [ ] |
| A3 | Mover entitlements removed within 5 business days | access-control.md | 5.18 | PR.AA-6 | 32(1)(b) | [ ] |
| A4 | Leaver access disabled <=1 hour after HR notification | access-control.md | 5.16 | PR.AA-1 | 32(1)(b) | [ ] |
| A5 | RBAC catalogue documented with toxic-combination flags | access-control.md | 5.15 | PR.AA-3 | 32(1)(b) | [ ] |
| A6 | ABAC policy in source control with tests | access-control.md | 5.15 | PR.AA-3 | 32(1)(b) | [ ] |
| A7 | PAM session brokering for all admin sessions | access-control.md | 8.2 | PR.AA-5 | 32(1)(b) | [ ] |
| A8 | Just-in-time elevation, time-bound, ticket-bound | access-control.md | 8.2 | PR.AA-5 | 32(1)(b) | [ ] |
| A9 | Quarterly recertification for privileged users | access-control.md | 5.18 | PR.AA-6 | 32(1)(b) | [ ] |
| A10 | Annual recertification for standard users | access-control.md | 5.18 | PR.AA-6 | 32(1)(b) | [ ] |
| A11 | Service accounts have registered owner and purpose | access-control.md | 5.16 | PR.AA-1 | 32(1)(b) | [ ] |
| A12 | Break-glass procedure with dual-control and 24h review | access-control.md | 8.2 | PR.AA-5 | 32(1)(b) | [ ] |

## B. Authentication (10 controls)

| # | Control | Source Doc | ISO 27002 | NIST CSF | GDPR | Status |
|---|---------|------------|-----------|----------|------|--------|
| B1 | AAL mapping recorded per system | authentication.md | 8.5 | PR.AA-2 | 32(1)(b) | [ ] |
| B2 | MFA mandatory for all workforce SSO | authentication.md | 8.5 | PR.AA-2 | 32(1)(b) | [ ] |
| B3 | Phishing-resistant MFA for AAL3 (admins, prod data) | authentication.md | 8.5 | PR.AA-2 | 32(1)(b) | [ ] |
| B4 | Password storage with Argon2id / scrypt / PBKDF2 600k+ | authentication.md | 8.24 | PR.DS-1 | 32(1)(a) | [ ] |
| B5 | Compromised-password block list refreshed monthly | authentication.md | 8.5 | PR.AA-2 | 32(1)(b) | [ ] |
| B6 | No mandatory periodic password rotation | authentication.md | 8.5 | PR.AA-2 | 32(1)(b) | [ ] |
| B7 | SSO via SAML 2.0 / OIDC; `none` JWT alg rejected | authentication.md | 8.5 | PR.AA-2 | 32(1)(b) | [ ] |
| B8 | Service account workload identity preferred over static | authentication.md | 5.17 | PR.AA-1 | 32(1)(b) | [ ] |
| B9 | Authentication logs streamed to SIEM with anomaly rules | authentication.md, logging.md | 8.15 | DE.CM-1 | 32(1)(d) | [ ] |
| B10 | Customer step-up auth before high-impact actions | authentication.md | 5.17 | PR.AA-3 | 32(1)(b) | [ ] |

## C. Cryptography and Key Management (12 controls)

| # | Control | Source Doc | ISO 27002 | NIST CSF | GDPR | Status |
|---|---------|------------|-----------|----------|------|--------|
| C1 | Personal data encrypted at rest (AES-256) | encryption.md | 8.24 | PR.DS-1 | 32(1)(a) | [ ] |
| C2 | TLS 1.3 only on new endpoints; 1.0 / 1.1 disabled | encryption.md | 8.24 | PR.DS-1 | 32(1)(a) | [ ] |
| C3 | mTLS between internal services | encryption.md, network-security.md | 8.24 | PR.DS-1 | 32(1)(a) | [ ] |
| C4 | KMS / HSM with FIPS 140-3 validated modules | encryption.md | 8.24 | PR.DS-1 | 32(1)(a) | [ ] |
| C5 | Master keys never extractable from HSM | encryption.md | 8.24 | PR.DS-1 | 32(1)(a) | [ ] |
| C6 | Cryptographic inventory maintained | encryption.md | 8.24 | PR.DS-1 | 32(1)(a) | [ ] |
| C7 | Quarterly key access recertification | encryption.md | 8.24 | PR.AA-6 | 32(1)(a) | [ ] |
| C8 | Key rotation per schedule; no overdue keys | encryption.md | 8.24 | PR.DS-1 | 32(1)(a) | [ ] |
| C9 | BYOK / HYOK strategy documented for cross-border | encryption.md | 8.24 | PR.DS-1 | 32(1)(a), 46 | [ ] |
| C10 | Crypto-shredding procedure tested for Article 17 cases | encryption.md, backup-recovery.md | 8.24 | PR.DS-3 | 17, 32(1)(a) | [ ] |
| C11 | Post-quantum readiness plan tracking NIST FIPS 203/204/205 | encryption.md | 8.24 | PR.DS-1 | 32(1)(a) | [ ] |
| C12 | Pseudonymisation register with mapping vault separation | encryption.md, masking-anonymization.md | 8.11 | PR.DS-2 | 4(5), 32(1)(a) | [ ] |

## D. Network Security (10 controls)

| # | Control | Source Doc | ISO 27002 | NIST CSF | GDPR | Status |
|---|---------|------------|-----------|----------|------|--------|
| D1 | Documented segment model with default deny | network-security.md | 8.22 | PR.IR-1 | 32(1)(b) | [ ] |
| D2 | NGFW with quarterly rule review | network-security.md | 8.20 | PR.IR-1 | 32(1)(b) | [ ] |
| D3 | WAF in front of every public web app and API gateway | network-security.md | 8.21 | DE.CM-9 | 32(1)(b) | [ ] |
| D4 | DDoS protection at edge | network-security.md | 8.20 | PR.IR-3 | 32(1)(b) | [ ] |
| D5 | IDS / IPS on north-south and east-west critical zones | network-security.md, logging.md | 8.16 | DE.CM-1 | 32(1)(d) | [ ] |
| D6 | ZTNA replacing legacy VPN | network-security.md | 8.20 | PR.AA-3 | 32(1)(b) | [ ] |
| D7 | TLS inspection bypassed for personal sensitive categories | network-security.md, dlp.md | 8.23 | PR.DS-3 | 5(1)(c), 88 | [ ] |
| D8 | Admin interfaces never exposed to public internet | network-security.md | 8.22 | PR.IR-1 | 32(1)(b) | [ ] |
| D9 | DNS firewall and DoH / DoT for endpoints | network-security.md | 8.23 | DE.CM-9 | 32(1)(b) | [ ] |
| D10 | Email gateway with SPF / DKIM / DMARC enforcement | network-security.md | 8.23 | PR.DS-1 | 32(1)(b) | [ ] |

## E. Logging and Monitoring (10 controls)

| # | Control | Source Doc | ISO 27002 | NIST CSF | GDPR | Status |
|---|---------|------------|-----------|----------|------|--------|
| E1 | Auditable event catalogue published and complete | logging.md | 8.15 | DE.CM-1 | 32(1)(d), 5(2) | [ ] |
| E2 | Log field standard - no cleartext secrets / PCI / Art. 9 | logging.md | 8.15 | DE.CM-1 | 5(1)(c), 32(1)(d) | [ ] |
| E3 | Append-only / WORM storage for production logs | logging.md | 8.15 | DE.CM-1 | 5(2) | [ ] |
| E4 | Daily hash-chain signing of log batches | logging.md | 8.15 | DE.AE-2 | 5(2) | [ ] |
| E5 | NTP / NTS clock sync with drift alerts | logging.md | 8.17 | PR.PS-2 | 32(1)(b) | [ ] |
| E6 | SIEM ingestion of in-scope systems with reliability >=99.9% | logging.md | 8.16 | DE.CM-1 | 32(1)(d) | [ ] |
| E7 | UEBA detections mapped to MITRE ATT&CK | logging.md | 8.16 | DE.AE-2 | 32(1)(d) | [ ] |
| E8 | Retention schedule per log class with auto-deletion | logging.md, 04-retention-erasure | 8.15 | DE.CM-1 | 5(1)(e) | [ ] |
| E9 | DPIA before deployment of high-risk monitoring (DLP, ZTNA recording) | logging.md, dpia | 5.34 | GV.RM-1 | 35, 88 | [ ] |
| E10 | Quarterly integrity audit on signed log archives | logging.md | 8.15 | DE.AE-2 | 5(2) | [ ] |

## F. Backup and Recovery (8 controls)

| # | Control | Source Doc | ISO 27002 | NIST CSF | GDPR | Status |
|---|---------|------------|-----------|----------|------|--------|
| F1 | RTO / RPO documented per system tier | backup-recovery.md | 8.13 | PR.DS-11 | 32(1)(c) | [ ] |
| F2 | 3-2-1-1-0 rule applied to critical-tier systems | backup-recovery.md | 8.13 | PR.DS-11 | 32(1)(c) | [ ] |
| F3 | Immutable / object-lock copy of critical tier | backup-recovery.md | 8.13 | PR.DS-11 | 32(1)(c) | [ ] |
| F4 | Backup admin identity domain separated from prod | backup-recovery.md | 8.13 | PR.AA-3 | 32(1)(c) | [ ] |
| F5 | Quarterly random restore test, annual full DR | backup-recovery.md | 8.13, 8.14 | RC.RP-1..6 | 32(1)(c), 32(1)(d) | [ ] |
| F6 | Ransomware clean-room exercise annually | backup-recovery.md | 8.13 | RC.RP-1..6 | 32(1)(c) | [ ] |
| F7 | Erasure propagation procedure (operational + archive) | backup-recovery.md | 5.34 | PR.DS-3 | 17 | [ ] |
| F8 | NIST 800-88 Rev.1 sanitisation on decommission | backup-recovery.md | 7.14, 8.10 | PR.PS-3 | 5(1)(f) | [ ] |

## G. Anonymisation and Pseudonymisation (6 controls)

| # | Control | Source Doc | ISO 27002 | NIST CSF | GDPR | Status |
|---|---------|------------|-----------|----------|------|--------|
| G1 | Each de-identified release has documented k / l / t / epsilon | masking-anonymization.md | 8.11 | PR.DS-2 | Recital 26 | [ ] |
| G2 | WP29 three-test (singling out, linkability, inference) recorded | masking-anonymization.md | 8.11 | PR.DS-2 | Recital 26 | [ ] |
| G3 | Re-identification risk assessment with DPO sign-off | masking-anonymization.md | 8.11 | PR.DS-2 | 35, Recital 26 | [ ] |
| G4 | ISO/IEC 27559 process steps observable | masking-anonymization.md | 8.11 | PR.DS-2 | n/a | [ ] |
| G5 | Differential privacy budget tracked centrally | masking-anonymization.md | 8.11 | PR.DS-2 | n/a | [ ] |
| G6 | Recipient contracts forbid re-identification | masking-anonymization.md, vendor-management | 5.20 | GV.SC-5 | 28 | [ ] |

## H. Data Loss Prevention (8 controls)

| # | Control | Source Doc | ISO 27002 | NIST CSF | GDPR | Status |
|---|---------|------------|-----------|----------|------|--------|
| H1 | Discovery sweep across SaaS, file shares, code, BI | dlp.md | 8.12 | PR.DS-3 | 5(1)(f) | [ ] |
| H2 | EU PII identifier library covers operating jurisdictions | dlp.md | 8.12 | PR.DS-3 | 5(1)(f) | [ ] |
| H3 | Endpoint DLP agent healthy on all managed devices | dlp.md | 8.12 | PR.DS-3 | 5(1)(f) | [ ] |
| H4 | Network and email DLP active with response workflow | dlp.md | 8.12 | PR.DS-3 | 5(1)(f) | [ ] |
| H5 | CASB inventory of sanctioned and shadow IT SaaS | dlp.md | 8.12 | PR.DS-3 | 5(1)(f) | [ ] |
| H6 | Article 88 / Article 6(1)(f) balancing test on file | dlp.md, 03-transparency-consent | 5.34 | GV.RM-1 | 6(1)(f), 88 | [ ] |
| H7 | DPIA before policy expansion or new monitoring scope | dlp.md, dpia | 5.34 | GV.RM-1 | 35 | [ ] |
| H8 | DLP event retention <=24 months unless legal exception | dlp.md, 04-retention-erasure | 8.15 | PR.DS-3 | 5(1)(e) | [ ] |

## I. Application Security (12 controls)

| # | Control | Source Doc | ISO 27002 | NIST CSF | GDPR | Status |
|---|---------|------------|-----------|----------|------|--------|
| I1 | Privacy by design recorded at requirements stage | application-security.md | 8.25 | GV.PO-1 | 25 | [ ] |
| I2 | LINDDUN run for new personal-data systems | application-security.md, dpia | 8.27 | GV.RM-1 | 25, 35 | [ ] |
| I3 | STRIDE threat model on T3-T5 components | application-security.md | 8.27 | ID.RA | 32 | [ ] |
| I4 | OWASP ASVS L2 minimum for in-scope applications | application-security.md | 8.26 | PR.PS-1 | 32 | [ ] |
| I5 | SAST blocking on critical, gating on high | application-security.md | 8.29 | PR.PS-1 | 32 | [ ] |
| I6 | SCA in CI with SLA-tracked remediation | application-security.md | 8.29 | PR.PS-1 | 32 | [ ] |
| I7 | DAST nightly against staging | application-security.md | 8.29 | PR.PS-1 | 32 | [ ] |
| I8 | Container and IaC scanning at build and admission | application-security.md | 8.27 | PR.PS-1 | 32 | [ ] |
| I9 | SBOM signed and stored per release | application-security.md | 8.30 | GV.SC | 32 | [ ] |
| I10 | Secrets manager; pre-commit blocks committed secrets | application-security.md | 8.24 | PR.DS-1 | 32(1)(a) | [ ] |
| I11 | Annual pen test + on every major change | application-security.md | 8.29 | PR.PS-1 | 32(1)(d) | [ ] |
| I12 | OWASP LLM Top 10 covered for AI features | application-security.md | 8.27 | PR.PS-1 | 22, 25, 32 | [ ] |

## Total

| Domain | Controls |
|--------|----------|
| A. Identity and Access | 12 |
| B. Authentication | 10 |
| C. Cryptography and Key Management | 12 |
| D. Network Security | 10 |
| E. Logging and Monitoring | 10 |
| F. Backup and Recovery | 8 |
| G. Anonymisation and Pseudonymisation | 6 |
| H. Data Loss Prevention | 8 |
| I. Application Security | 12 |
| **Total** | **88** |

## Audit Sampling

Internal audit (`06-organizational-measures/internal-audit.md`) samples a
risk-weighted subset of controls each cycle. Coverage rotation ensures every
control is examined at least every two cycles.

## Evidence

Each control has a designated evidence artefact filed under
`11-audit-compliance/evidence/<control_id>/`. CAPA tickets feed back into
the next review.

---

## Türkçe

# Teknik Kontroller Kontrol Listesi

Bu kontrol listesi, bu alandaki teknik kontrol setini bir araya getirir. Her
satır bir kontrolü, bu wikideki sorumlu belgeyi ve ISO/IEC 27002:2022, NIST
CSF 2.0 ve GDPR Madde 32'ye çapraz eşlemeleri tanımlar.

Kontrol listesini şunlar için temel olarak kullanın:

- İç denetim örneklemesi (`06-organizational-measures/internal-audit.md`).
- Tedarikçi durum tespiti (`06-organizational-measures/vendor-management.md`).
- VKD kontrol kataloğu (`06-organizational-measures/dpia.md`).
- Yıllık TOM incelemesi.

Durum açıklaması: `[ ]` başlanmadı, `[~]` devam ediyor, `[x]` uygulandı ve
doğrulandı.

## A. Kimlik ve Erişim Kontrolü (12 kontrol)

| # | Kontrol | Kaynak | ISO 27002 | NIST CSF | GDPR | Durum |
|---|---------|--------|-----------|----------|------|-------|
| A1 | İK odaklı JML için yetkili kimlik dizini | access-control.md | 5.16 | PR.AA-1 | 32(1)(b) | [ ] |
| A2 | Joiner sağlama SLA <=1 iş günü | access-control.md | 5.16 | PR.AA-1 | 32(1)(b) | [ ] |
| A3 | Mover yetkileri 5 iş günü içinde kaldırıldı | access-control.md | 5.18 | PR.AA-6 | 32(1)(b) | [ ] |
| A4 | Leaver erişimi İK bildiriminden sonra <=1 saat içinde devre dışı | access-control.md | 5.16 | PR.AA-1 | 32(1)(b) | [ ] |
| A5 | Toksik kombinasyon işaretleri ile belgelenmiş RBAC kataloğu | access-control.md | 5.15 | PR.AA-3 | 32(1)(b) | [ ] |
| A6 | Test'lerle kaynak kontrolünde ABAC politikası | access-control.md | 5.15 | PR.AA-3 | 32(1)(b) | [ ] |
| A7 | Tüm yönetici oturumları için PAM oturum aracılığı | access-control.md | 8.2 | PR.AA-5 | 32(1)(b) | [ ] |
| A8 | Just-in-time yükseltme, süreye bağlı, bilete bağlı | access-control.md | 8.2 | PR.AA-5 | 32(1)(b) | [ ] |
| A9 | Ayrıcalıklı kullanıcılar için üç aylık resertifikasyon | access-control.md | 5.18 | PR.AA-6 | 32(1)(b) | [ ] |
| A10 | Standart kullanıcılar için yıllık resertifikasyon | access-control.md | 5.18 | PR.AA-6 | 32(1)(b) | [ ] |
| A11 | Servis hesaplarının kayıtlı sahip ve amacı vardır | access-control.md | 5.16 | PR.AA-1 | 32(1)(b) | [ ] |
| A12 | Çift kontrol ve 24s incelemeli acil durum prosedürü | access-control.md | 8.2 | PR.AA-5 | 32(1)(b) | [ ] |

## B. Kimlik Doğrulama (10 kontrol)

| # | Kontrol | Kaynak | ISO 27002 | NIST CSF | GDPR | Durum |
|---|---------|--------|-----------|----------|------|-------|
| B1 | Sistem başına AAL eşlemesi kayıtlı | authentication.md | 8.5 | PR.AA-2 | 32(1)(b) | [ ] |
| B2 | Tüm iş gücü SSO'sunda zorunlu MFA | authentication.md | 8.5 | PR.AA-2 | 32(1)(b) | [ ] |
| B3 | AAL3 için phishing'e dayanıklı MFA (yöneticiler, üretim verisi) | authentication.md | 8.5 | PR.AA-2 | 32(1)(b) | [ ] |
| B4 | Argon2id / scrypt / PBKDF2 600k+ ile parola depolama | authentication.md | 8.24 | PR.DS-1 | 32(1)(a) | [ ] |
| B5 | Tehlikeye girmiş parola engelleme listesi aylık yenilenir | authentication.md | 8.5 | PR.AA-2 | 32(1)(b) | [ ] |
| B6 | Zorunlu periyodik parola rotasyonu yok | authentication.md | 8.5 | PR.AA-2 | 32(1)(b) | [ ] |
| B7 | SAML 2.0 / OIDC üzerinden SSO; `none` JWT alg reddedilir | authentication.md | 8.5 | PR.AA-2 | 32(1)(b) | [ ] |
| B8 | Statik üzerine iş yükü kimliği tercih edilen servis hesabı | authentication.md | 5.17 | PR.AA-1 | 32(1)(b) | [ ] |
| B9 | Anomali kurallarıyla SIEM'e akan kimlik doğrulama logları | authentication.md, logging.md | 8.15 | DE.CM-1 | 32(1)(d) | [ ] |
| B10 | Yüksek etkili eylemlerden önce müşteri adım yükseltme kimlik doğrulaması | authentication.md | 5.17 | PR.AA-3 | 32(1)(b) | [ ] |

## C. Kriptografi ve Anahtar Yönetimi (12 kontrol)

| # | Kontrol | Kaynak | ISO 27002 | NIST CSF | GDPR | Durum |
|---|---------|--------|-----------|----------|------|-------|
| C1 | Atılımda şifrelenmiş kişisel veri (AES-256) | encryption.md | 8.24 | PR.DS-1 | 32(1)(a) | [ ] |
| C2 | Yeni uç noktalarda yalnızca TLS 1.3; 1.0 / 1.1 devre dışı | encryption.md | 8.24 | PR.DS-1 | 32(1)(a) | [ ] |
| C3 | Dahili servisler arasında mTLS | encryption.md, network-security.md | 8.24 | PR.DS-1 | 32(1)(a) | [ ] |
| C4 | FIPS 140-3 onaylı modüllerle KMS / HSM | encryption.md | 8.24 | PR.DS-1 | 32(1)(a) | [ ] |
| C5 | Master anahtarlar HSM'den asla çıkarılamaz | encryption.md | 8.24 | PR.DS-1 | 32(1)(a) | [ ] |
| C6 | Kriptografik envanter tutulur | encryption.md | 8.24 | PR.DS-1 | 32(1)(a) | [ ] |
| C7 | Anahtar erişimi üç aylık resertifikasyon | encryption.md | 8.24 | PR.AA-6 | 32(1)(a) | [ ] |
| C8 | Programa göre anahtar rotasyonu; gecikmiş anahtar yok | encryption.md | 8.24 | PR.DS-1 | 32(1)(a) | [ ] |
| C9 | Sınır ötesi için BYOK / HYOK stratejisi belgelenmiş | encryption.md | 8.24 | PR.DS-1 | 32(1)(a), 46 | [ ] |
| C10 | Madde 17 vakaları için test edilmiş kripto-yok etme prosedürü | encryption.md, backup-recovery.md | 8.24 | PR.DS-3 | 17, 32(1)(a) | [ ] |
| C11 | NIST FIPS 203/204/205'i izleyen kuantum sonrası hazırlık planı | encryption.md | 8.24 | PR.DS-1 | 32(1)(a) | [ ] |
| C12 | Eşleme kasası ayrımı ile pseudonimizasyon kayıt defteri | encryption.md, masking-anonymization.md | 8.11 | PR.DS-2 | 4(5), 32(1)(a) | [ ] |

## D. Ağ Güvenliği (10 kontrol)

| # | Kontrol | Kaynak | ISO 27002 | NIST CSF | GDPR | Durum |
|---|---------|--------|-----------|----------|------|-------|
| D1 | Varsayılan reddetli belgelenmiş segment modeli | network-security.md | 8.22 | PR.IR-1 | 32(1)(b) | [ ] |
| D2 | Üç aylık kural incelemeli NGFW | network-security.md | 8.20 | PR.IR-1 | 32(1)(b) | [ ] |
| D3 | Her genel web uygulaması ve API ağ geçidinin önünde WAF | network-security.md | 8.21 | DE.CM-9 | 32(1)(b) | [ ] |
| D4 | Kenarda DDoS koruması | network-security.md | 8.20 | PR.IR-3 | 32(1)(b) | [ ] |
| D5 | Kuzey-güney ve doğu-batı kritik bölgelerde IDS / IPS | network-security.md, logging.md | 8.16 | DE.CM-1 | 32(1)(d) | [ ] |
| D6 | Eski VPN'in yerini ZTNA aldı | network-security.md | 8.20 | PR.AA-3 | 32(1)(b) | [ ] |
| D7 | Kişisel hassas kategoriler için TLS incelemesi atlandı | network-security.md, dlp.md | 8.23 | PR.DS-3 | 5(1)(c), 88 | [ ] |
| D8 | Yönetim arayüzleri asla genel internete açılmaz | network-security.md | 8.22 | PR.IR-1 | 32(1)(b) | [ ] |
| D9 | DNS güvenlik duvarı ve uç noktalar için DoH / DoT | network-security.md | 8.23 | DE.CM-9 | 32(1)(b) | [ ] |
| D10 | SPF / DKIM / DMARC uygulamasıyla e-posta ağ geçidi | network-security.md | 8.23 | PR.DS-1 | 32(1)(b) | [ ] |

## E. Loglama ve İzleme (10 kontrol)

| # | Kontrol | Kaynak | ISO 27002 | NIST CSF | GDPR | Durum |
|---|---------|--------|-----------|----------|------|-------|
| E1 | Yayımlanmış ve eksiksiz denetlenebilir olay kataloğu | logging.md | 8.15 | DE.CM-1 | 32(1)(d), 5(2) | [ ] |
| E2 | Log alanı standardı - açık metin sırlar / PCI / Md. 9 yok | logging.md | 8.15 | DE.CM-1 | 5(1)(c), 32(1)(d) | [ ] |
| E3 | Üretim logları için yalnızca ekle / WORM depolama | logging.md | 8.15 | DE.CM-1 | 5(2) | [ ] |
| E4 | Log gruplarının günlük hash zinciri imzalama | logging.md | 8.15 | DE.AE-2 | 5(2) | [ ] |
| E5 | Kayma uyarılarıyla NTP / NTS saat senkronizasyonu | logging.md | 8.17 | PR.PS-2 | 32(1)(b) | [ ] |
| E6 | %99,9'dan fazla güvenilirlikle kapsam dahili sistemlerin SIEM alımı | logging.md | 8.16 | DE.CM-1 | 32(1)(d) | [ ] |
| E7 | MITRE ATT&CK'a eşlenmiş UEBA algılamaları | logging.md | 8.16 | DE.AE-2 | 32(1)(d) | [ ] |
| E8 | Otomatik silmeyle log sınıfı başına saklama programı | logging.md, 04-retention-erasure | 8.15 | DE.CM-1 | 5(1)(e) | [ ] |
| E9 | Yüksek riskli izleme dağıtımından önce VKD (DLP, ZTNA kaydı) | logging.md, dpia | 5.34 | GV.RM-1 | 35, 88 | [ ] |
| E10 | İmzalı log arşivlerinde üç aylık bütünlük denetimi | logging.md | 8.15 | DE.AE-2 | 5(2) | [ ] |

## F. Yedekleme ve Geri Yükleme (8 kontrol)

| # | Kontrol | Kaynak | ISO 27002 | NIST CSF | GDPR | Durum |
|---|---------|--------|-----------|----------|------|-------|
| F1 | Sistem katmanı başına RTO / RPO belgelenmiş | backup-recovery.md | 8.13 | PR.DS-11 | 32(1)(c) | [ ] |
| F2 | Kritik katman sistemlere uygulanan 3-2-1-1-0 kuralı | backup-recovery.md | 8.13 | PR.DS-11 | 32(1)(c) | [ ] |
| F3 | Kritik katmanın değiştirilemez / nesne kilitli kopyası | backup-recovery.md | 8.13 | PR.DS-11 | 32(1)(c) | [ ] |
| F4 | Yedekleme yönetici kimlik etki alanı üretimden ayrı | backup-recovery.md | 8.13 | PR.AA-3 | 32(1)(c) | [ ] |
| F5 | Üç aylık rastgele geri yükleme testi, yıllık tam DR | backup-recovery.md | 8.13, 8.14 | RC.RP-1..6 | 32(1)(c), 32(1)(d) | [ ] |
| F6 | Yıllık fidye yazılımı temiz oda tatbikatı | backup-recovery.md | 8.13 | RC.RP-1..6 | 32(1)(c) | [ ] |
| F7 | Silme yayılma prosedürü (operasyonel + arşiv) | backup-recovery.md | 5.34 | PR.DS-3 | 17 | [ ] |
| F8 | Hizmet dışı bırakmada NIST 800-88 Rev.1 temizliği | backup-recovery.md | 7.14, 8.10 | PR.PS-3 | 5(1)(f) | [ ] |

## G. Anonimleştirme ve Pseudonimizasyon (6 kontrol)

| # | Kontrol | Kaynak | ISO 27002 | NIST CSF | GDPR | Durum |
|---|---------|--------|-----------|----------|------|-------|
| G1 | Her tanımsızlaştırılmış yayımın belgelenmiş k / l / t / epsilon değeri | masking-anonymization.md | 8.11 | PR.DS-2 | Resital 26 | [ ] |
| G2 | WP29 üç testi (tekilleştirme, bağlanabilirlik, çıkarım) kayıtlı | masking-anonymization.md | 8.11 | PR.DS-2 | Resital 26 | [ ] |
| G3 | DPO onaylı yeniden tanımlama risk değerlendirmesi | masking-anonymization.md | 8.11 | PR.DS-2 | 35, Resital 26 | [ ] |
| G4 | ISO/IEC 27559 süreç adımları gözlemlenebilir | masking-anonymization.md | 8.11 | PR.DS-2 | yok | [ ] |
| G5 | Diferansiyel gizlilik bütçesi merkezi izleniyor | masking-anonymization.md | 8.11 | PR.DS-2 | yok | [ ] |
| G6 | Alıcı sözleşmeleri yeniden tanımlamayı yasaklıyor | masking-anonymization.md, vendor-management | 5.20 | GV.SC-5 | 28 | [ ] |

## H. Veri Sızıntısı Önleme (8 kontrol)

| # | Kontrol | Kaynak | ISO 27002 | NIST CSF | GDPR | Durum |
|---|---------|--------|-----------|----------|------|-------|
| H1 | SaaS, dosya paylaşımları, kod, BI üzerinde keşif taraması | dlp.md | 8.12 | PR.DS-3 | 5(1)(f) | [ ] |
| H2 | AB PII tanımlayıcı kütüphanesi işletim yetki alanlarını kapsar | dlp.md | 8.12 | PR.DS-3 | 5(1)(f) | [ ] |
| H3 | Tüm yönetilen cihazlarda sağlıklı uç nokta DLP ajanı | dlp.md | 8.12 | PR.DS-3 | 5(1)(f) | [ ] |
| H4 | Müdahale iş akışı ile ağ ve e-posta DLP aktif | dlp.md | 8.12 | PR.DS-3 | 5(1)(f) | [ ] |
| H5 | Yetkili ve gölge BT SaaS CASB envanteri | dlp.md | 8.12 | PR.DS-3 | 5(1)(f) | [ ] |
| H6 | Madde 88 / Madde 6(1)(f) dengeleme testi dosyada | dlp.md, 03-transparency-consent | 5.34 | GV.RM-1 | 6(1)(f), 88 | [ ] |
| H7 | Politika genişlemesi veya yeni izleme kapsamından önce VKD | dlp.md, dpia | 5.34 | GV.RM-1 | 35 | [ ] |
| H8 | Yasal istisna olmadıkça DLP olay saklaması <=24 ay | dlp.md, 04-retention-erasure | 8.15 | PR.DS-3 | 5(1)(e) | [ ] |

## I. Uygulama Güvenliği (12 kontrol)

| # | Kontrol | Kaynak | ISO 27002 | NIST CSF | GDPR | Durum |
|---|---------|--------|-----------|----------|------|-------|
| I1 | Gereksinim aşamasında kayıtlı tasarımdan gizlilik | application-security.md | 8.25 | GV.PO-1 | 25 | [ ] |
| I2 | Yeni kişisel-veri sistemleri için yürütülen LINDDUN | application-security.md, dpia | 8.27 | GV.RM-1 | 25, 35 | [ ] |
| I3 | T3-T5 bileşenlerde STRIDE tehdit modeli | application-security.md | 8.27 | ID.RA | 32 | [ ] |
| I4 | Kapsam dahili uygulamalar için OWASP ASVS L2 asgari | application-security.md | 8.26 | PR.PS-1 | 32 | [ ] |
| I5 | Kritikte engelleyici, yüksekte kapı SAST | application-security.md | 8.29 | PR.PS-1 | 32 | [ ] |
| I6 | SLA izlemeli düzeltme ile CI'da SCA | application-security.md | 8.29 | PR.PS-1 | 32 | [ ] |
| I7 | Staging'e karşı gece DAST | application-security.md | 8.29 | PR.PS-1 | 32 | [ ] |
| I8 | Yapım ve kabulde konteyner ve IaC taraması | application-security.md | 8.27 | PR.PS-1 | 32 | [ ] |
| I9 | Yayım başına imzalı ve saklanan SBOM | application-security.md | 8.30 | GV.SC | 32 | [ ] |
| I10 | Sır yöneticisi; pre-commit gönderilen sırları engeller | application-security.md | 8.24 | PR.DS-1 | 32(1)(a) | [ ] |
| I11 | Yıllık sızma testi + her büyük değişiklikte | application-security.md | 8.29 | PR.PS-1 | 32(1)(d) | [ ] |
| I12 | AI özellikleri için OWASP LLM Top 10 kapsanır | application-security.md | 8.27 | PR.PS-1 | 22, 25, 32 | [ ] |

## Toplam

| Alan | Kontroller |
|------|-----------|
| A. Kimlik ve Erişim | 12 |
| B. Kimlik Doğrulama | 10 |
| C. Kriptografi ve Anahtar Yönetimi | 12 |
| D. Ağ Güvenliği | 10 |
| E. Loglama ve İzleme | 10 |
| F. Yedekleme ve Geri Yükleme | 8 |
| G. Anonimleştirme ve Pseudonimizasyon | 6 |
| H. Veri Sızıntısı Önleme | 8 |
| I. Uygulama Güvenliği | 12 |
| **Toplam** | **88** |

## Denetim Örneklemesi

İç denetim (`06-organizational-measures/internal-audit.md`), her döngüde
risk ağırlıklı bir kontrol alt kümesini örnekler. Kapsama rotasyonu her
kontrolün en az iki döngüde bir incelenmesini sağlar.

## Kanıt

Her kontrolün `11-audit-compliance/evidence/<control_id>/` altında
dosyalanmış belirlenmiş bir kanıt yapısı vardır. CAPA biletleri sonraki
incelemeye geri besleme yapar.
