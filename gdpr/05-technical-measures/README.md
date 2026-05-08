---
title:
  en: "Technical Measures - Article 32 GDPR"
  tr: "Teknik Tedbirler - GDPR Madde 32"
section: "05-technical-measures"
document_type: "domain_index"
owner:
  primary: "Chief Information Security Officer (CISO)"
  secondary: "Data Protection Officer (DPO)"
review_cycle: "annual"
last_review: "2026-05-08"
next_review: "2027-05-08"
classification: "Internal"
language: ["en", "tr"]
references:
  - "GDPR Art. 5(1)(f), 24, 25, 32, 35"
  - "ENISA Handbook on Security of Personal Data Processing (2017, updated 2022)"
  - "ISO/IEC 27001:2022, ISO/IEC 27002:2022"
  - "ISO/IEC 27701:2019"
  - "ISO/IEC 27018:2019"
  - "NIST Cybersecurity Framework 2.0 (2024)"
  - "NIST SP 800-63B"
  - "NIST SP 800-88 Rev.1"
  - "EDPB Guidelines 9/2022 on personal data breach notification"
  - "OWASP Top 10 2021, OWASP API Top 10 2023, OWASP LLM Top 10 2025"
---

## English

# Technical Measures - GDPR Article 32

## 1. Purpose and Scope

This domain (`05-technical-measures`) consolidates the technical control set the
controller and its processors implement to satisfy Article 32(1) of the General
Data Protection Regulation (Regulation (EU) 2016/679). Article 32 requires the
controller and processor, "taking into account the state of the art, the costs
of implementation and the nature, scope, context and purposes of processing as
well as the risk of varying likelihood and severity for the rights and freedoms
of natural persons," to implement appropriate technical and organisational
measures (TOMs) to ensure a level of security appropriate to the risk.

The technical measures described here are inseparable from the organisational
measures recorded under `06-organizational-measures`. Article 32 names four
illustrative non-exhaustive control families:

- (a) the pseudonymisation and encryption of personal data;
- (b) the ability to ensure the ongoing confidentiality, integrity, availability
  and resilience of processing systems and services;
- (c) the ability to restore the availability and access to personal data in a
  timely manner in the event of a physical or technical incident;
- (d) a process for regularly testing, assessing and evaluating the
  effectiveness of technical and organisational measures for ensuring the
  security of the processing.

This domain operationalises those four illustrative families and binds them to
ENISA's risk-based handbook, ISO/IEC 27002:2022 controls, NIST CSF 2.0
functions (Govern, Identify, Protect, Detect, Respond, Recover) and the OWASP
secure-application standards.

## 2. Documents in this Domain

| # | File | Subject | Primary Article(s) |
|---|------|---------|--------------------|
| 1 | `README.md` | Domain overview, mapping table | Art. 32 |
| 2 | `access-control.md` | RBAC, ABAC, JML, PAM, SoD | Art. 5(1)(f), 32(1)(b), 32(4) |
| 3 | `authentication.md` | MFA, password policy, SSO | Art. 32(1)(b) |
| 4 | `encryption.md` | At-rest, in-transit, KMS, PQC, pseudonymisation | Art. 32(1)(a), 4(5) |
| 5 | `network-security.md` | Segmentation, NGFW, WAF, ZTNA, SASE | Art. 32(1)(b) |
| 6 | `logging.md` | Audit events, SIEM, retention | Art. 5(2), 30, 32(1)(d) |
| 7 | `backup-recovery.md` | 3-2-1-1-0, immutable, restore tests | Art. 32(1)(c), 32(1)(b) |
| 8 | `masking-anonymization.md` | k-anon, l-div, t-close, DP, ISO 20889 | Art. 4(5), Recital 26 |
| 9 | `dlp.md` | Endpoint, network, CASB, EU PII | Art. 5(1)(f), 88 |
| 10 | `application-security.md` | PbD, OWASP, SAST/DAST/SCA, SBOM, pen test | Art. 25, 32 |
| 11 | `technical-controls-checklist.md` | 80+ controls cross-mapped | Art. 32 |

## 3. Risk-Based Approach (ENISA Methodology)

ENISA's "Handbook on Security of Personal Data Processing" prescribes four
sequential steps that the controller is required to evidence in the Records of
Processing (Article 30) and DPIAs (Article 35):

1. **Definition of processing operations and context** - what data, what
   purposes, what categories of data subjects, what systems.
2. **Understanding and evaluation of impact** - severity for data subjects on a
   four-level scale (Low / Medium / High / Very High) considering Article 9
   special categories, Article 10 criminal data, profiling and large-scale
   monitoring.
3. **Definition of threats and evaluation of their likelihood** - likelihood on
   the same four-level scale based on attack surface, threat actors and
   exposure.
4. **Selection of appropriate security measures** - controls calibrated to the
   resulting risk level, drawn from ENISA's reference set and supplemented with
   ISO 27002:2022 Annex A and NIST CSF 2.0.

Risk owners must record the residual risk after controls. Where residual risk
remains High, prior consultation under Article 36 is required before processing
starts.

## 4. Standards Mapping (Authoritative)

| Layer | GDPR | ISO/IEC 27002:2022 | NIST CSF 2.0 |
|-------|------|--------------------|--------------|
| Identity & Access | Art. 32(1)(b), 32(4) | 5.15-5.18, 8.2, 8.3, 8.5 | PR.AA-1..6, PR.AT |
| Cryptography | Art. 32(1)(a) | 8.24 | PR.DS-1, PR.DS-2 |
| Network | Art. 32(1)(b) | 8.20-8.23 | PR.IR-1..4, DE.CM |
| Logging & Monitoring | Art. 32(1)(d), 5(2) | 8.15-8.17 | DE.CM, DE.AE |
| Resilience & Backup | Art. 32(1)(c) | 8.13, 8.14 | RC.RP, PR.DS-11 |
| Anonymisation | Art. 4(5), Recital 26 | 8.11 | PR.DS-1, PR.DS-2 |
| App Security | Art. 25, 32 | 8.25-8.30 | PR.PS, ID.RA, PR.DS |

## 5. State of the Art

"State of the art" is a moving target. The reference baseline used for this
wiki cycle (May 2026 - May 2027) is:

- **TLS** - 1.3 only on new endpoints; TLS 1.2 with deprecated ciphers
  removed; TLS 1.0 / 1.1 disabled at all layers.
- **Symmetric encryption** - AES-256-GCM at rest as default; ChaCha20-Poly1305
  acceptable.
- **Asymmetric** - RSA-3072 minimum, ECDSA P-256 / P-384, Ed25519.
- **Hashing** - SHA-256 minimum; SHA-1 only for legacy interoperability and
  never for security.
- **Password storage** - Argon2id (RFC 9106), scrypt, or PBKDF2 with at least
  600,000 SHA-256 iterations (NIST SP 800-63B 2024 update).
- **Post-quantum readiness** - Track NIST FIPS 203 (ML-KEM), FIPS 204 (ML-DSA),
  FIPS 205 (SLH-DSA); deploy hybrid KEM in TLS where feasible; complete crypto
  inventory by Q4 2026.
- **MFA** - Phishing-resistant (FIDO2 / WebAuthn / passkeys) for administrators
  and remote access; TOTP minimum for all employees; SMS OTP only as fallback.

## 6. Roles and Responsibilities

| Role | Responsibility |
|------|----------------|
| Board / Executive | Approve risk appetite and security budget |
| CISO | Own technical security strategy and TOM design |
| DPO | Advise, monitor compliance with Art. 24, 25, 32, 35 |
| Engineering Leads | Implement controls in product and infrastructure |
| Internal Audit | Provide independent assurance |
| Vendor Risk | Verify processor controls per Art. 28 |

## 7. Verification and Continuous Improvement

Article 32(1)(d) requires a process for **regularly testing, assessing and
evaluating** the effectiveness of measures. The minimum cadence:

- Vulnerability scanning - weekly external, monthly internal.
- Penetration testing - annually and on every major change.
- Configuration baseline review - quarterly.
- Access recertification - quarterly for privileged, annually for standard.
- DR / restore drill - at least twice per year, one full failover.
- Tabletop exercise (incident response) - twice per year minimum.
- Internal audit of TOMs - annually (`06-organizational-measures/internal-audit.md`).

## 8. Evidence Repository

All control evidence is filed under `11-audit-compliance/evidence/` and indexed
by control ID. The audit programme (`06-organizational-measures/internal-audit.md`)
defines the sampling methodology and CAPA tracking.

---

## Türkçe

# Teknik Tedbirler - GDPR Madde 32

## 1. Amaç ve Kapsam

Bu alan (`05-technical-measures`), kontrolör ve veri işleyicilerinin Genel Veri
Koruma Tüzüğü (Tüzük (AB) 2016/679) Madde 32(1) gerekliliklerini karşılamak
üzere uyguladığı teknik kontrol setini bir araya getirir. Madde 32, "teknolojinin
mevcut durumu, uygulama maliyetleri ve işlemenin nitelik, kapsam, bağlam ve
amaçları ile gerçek kişilerin hak ve özgürlüklerine yönelik değişen olasılık ve
ciddiyetteki riski göz önünde bulundurarak" kontrolör ve işleyicinin riske uygun
düzeyde güvenlik sağlayacak teknik ve organizasyonel tedbirleri (TOM) uygulamasını
zorunlu kılar.

Burada açıklanan teknik tedbirler, `06-organizational-measures` altında
düzenlenen organizasyonel tedbirlerden ayrı düşünülemez. Madde 32 dört örnek
kontrol ailesini sıralar:

- (a) kişisel verilerin pseudonimizasyonu (örtükleştirme) ve şifrelenmesi;
- (b) işleme sistem ve hizmetlerinin sürekli gizliliğini, bütünlüğünü,
  kullanılabilirliğini ve dayanıklılığını sağlama yeteneği;
- (c) fiziksel veya teknik bir olay durumunda kişisel verilere erişimi ve
  kullanılabilirliği zamanında geri yükleme yeteneği;
- (d) işleme güvenliğini sağlamak için teknik ve organizasyonel tedbirlerin
  etkinliğini düzenli olarak test etme, değerlendirme ve denetleme süreci.

Bu alan, dört aileyi ENISA risk temelli el kitabı, ISO/IEC 27002:2022
kontrolleri, NIST CSF 2.0 fonksiyonları (Govern, Identify, Protect, Detect,
Respond, Recover) ve OWASP güvenli uygulama standartlarına bağlar.

## 2. Bu Alandaki Belgeler

| # | Dosya | Konu | Birincil Madde(ler) |
|---|-------|------|---------------------|
| 1 | `README.md` | Alan genel bakışı, eşleme tablosu | Md. 32 |
| 2 | `access-control.md` | RBAC, ABAC, JML, PAM, SoD | Md. 5(1)(f), 32(1)(b), 32(4) |
| 3 | `authentication.md` | MFA, parola politikası, SSO | Md. 32(1)(b) |
| 4 | `encryption.md` | Atılım, taşıma, KMS, PQC, pseudonimizasyon | Md. 32(1)(a), 4(5) |
| 5 | `network-security.md` | Segmentasyon, NGFW, WAF, ZTNA, SASE | Md. 32(1)(b) |
| 6 | `logging.md` | Denetim olayları, SIEM, saklama | Md. 5(2), 30, 32(1)(d) |
| 7 | `backup-recovery.md` | 3-2-1-1-0, değiştirilemez, geri yükleme testleri | Md. 32(1)(c) |
| 8 | `masking-anonymization.md` | k-anon, l-div, t-close, DP, ISO 20889 | Md. 4(5), Resital 26 |
| 9 | `dlp.md` | Endpoint, ağ, CASB, AB PII | Md. 5(1)(f), 88 |
| 10 | `application-security.md` | PbD, OWASP, SAST/DAST/SCA, SBOM, pentest | Md. 25, 32 |
| 11 | `technical-controls-checklist.md` | 80+ kontrol çapraz eşleme | Md. 32 |

## 3. Risk Temelli Yaklaşım (ENISA Metodolojisi)

ENISA'nın "Kişisel Veri İşleme Güvenliği El Kitabı" dört adımlı bir akış öngörür
ve kontrolörün bu akışı İşleme Faaliyetleri Kayıtları (Madde 30) ve VKD'lerde
(Madde 35) belgelemesi beklenir:

1. **İşleme operasyonlarının ve bağlamının tanımlanması** - hangi veriler,
   hangi amaçlar, hangi veri sahibi kategorileri, hangi sistemler.
2. **Etkinin anlaşılması ve değerlendirilmesi** - veri sahipleri için ciddiyetin
   dört seviyeli ölçekte (Düşük / Orta / Yüksek / Çok Yüksek) belirlenmesi;
   Madde 9 özel nitelikli kategoriler, Madde 10 cezai veri, profilleme ve büyük
   ölçekli izleme dikkate alınır.
3. **Tehditlerin tanımlanması ve olasılıklarının değerlendirilmesi** - aynı dört
   seviyeli ölçekte saldırı yüzeyi, tehdit aktörleri ve maruziyet temelinde.
4. **Uygun güvenlik tedbirlerinin seçilmesi** - ortaya çıkan risk seviyesine
   kalibre edilmiş kontroller; ENISA referans setinden seçilir, ISO 27002:2022
   Ek A ve NIST CSF 2.0 ile tamamlanır.

Risk sahipleri, kontrol sonrası kalan riski kayıt altına alır. Kalan risk
Yüksek olarak kalırsa, işleme başlamadan önce Madde 36 uyarınca ön danışma
zorunludur.

## 4. Standart Eşleme (Otoriter)

| Katman | GDPR | ISO/IEC 27002:2022 | NIST CSF 2.0 |
|--------|------|--------------------|--------------|
| Kimlik ve Erişim | Md. 32(1)(b), 32(4) | 5.15-5.18, 8.2, 8.3, 8.5 | PR.AA-1..6, PR.AT |
| Kriptografi | Md. 32(1)(a) | 8.24 | PR.DS-1, PR.DS-2 |
| Ağ | Md. 32(1)(b) | 8.20-8.23 | PR.IR-1..4, DE.CM |
| Loglama ve İzleme | Md. 32(1)(d), 5(2) | 8.15-8.17 | DE.CM, DE.AE |
| Dayanıklılık ve Yedek | Md. 32(1)(c) | 8.13, 8.14 | RC.RP, PR.DS-11 |
| Anonimleştirme | Md. 4(5), Resital 26 | 8.11 | PR.DS-1, PR.DS-2 |
| Uygulama Güvenliği | Md. 25, 32 | 8.25-8.30 | PR.PS, ID.RA, PR.DS |

## 5. Teknolojinin Mevcut Durumu

"Teknolojinin mevcut durumu" hareketli bir hedeftir. Bu wiki döngüsü için
(Mayıs 2026 - Mayıs 2027) referans temel:

- **TLS** - Yeni uç noktalarda yalnızca 1.3; eski şifre paketleriyle TLS 1.2
  kaldırılmıştır; TLS 1.0 / 1.1 tüm katmanlarda devre dışıdır.
- **Simetrik şifreleme** - Varsayılan olarak atılımda AES-256-GCM;
  ChaCha20-Poly1305 kabul edilebilir.
- **Asimetrik** - RSA-3072 asgari, ECDSA P-256 / P-384, Ed25519.
- **Özetleme** - Asgari SHA-256; SHA-1 yalnızca eski uyumluluk için ve asla
  güvenlik amacıyla değil.
- **Parola depolama** - Argon2id (RFC 9106), scrypt veya en az 600.000 SHA-256
  iterasyonlu PBKDF2 (NIST SP 800-63B 2024 güncellemesi).
- **Kuantum sonrası hazırlık** - NIST FIPS 203 (ML-KEM), FIPS 204 (ML-DSA),
  FIPS 205 (SLH-DSA) izlenir; mümkün yerlerde TLS'de hibrit KEM dağıtılır;
  kripto envanteri 2026 Q4 itibarıyla tamamlanır.
- **MFA** - Yöneticiler ve uzaktan erişim için phishing'e dayanıklı (FIDO2 /
  WebAuthn / passkey'ler); tüm çalışanlar için asgari TOTP; SMS OTP yalnızca
  yedek olarak.

## 6. Roller ve Sorumluluklar

| Rol | Sorumluluk |
|-----|------------|
| Yönetim Kurulu / Üst Yönetim | Risk iştahını ve güvenlik bütçesini onaylar |
| CISO | Teknik güvenlik stratejisi ve TOM tasarımına sahiptir |
| VKS / DPO | Md. 24, 25, 32, 35 uyumunu danışmanlık eder ve izler |
| Mühendislik Liderleri | Kontrolleri ürün ve altyapıda uygular |
| İç Denetim | Bağımsız güvence sağlar |
| Tedarikçi Riski | Md. 28 uyarınca işleyici kontrollerini doğrular |

## 7. Doğrulama ve Sürekli İyileştirme

Madde 32(1)(d), tedbirlerin etkinliğinin **düzenli olarak test edilmesi,
değerlendirilmesi ve denetlenmesi** sürecini gerektirir. Asgari kadans:

- Zafiyet taraması - haftalık dış, aylık iç.
- Sızma testi - yıllık ve her büyük değişiklikte.
- Konfigürasyon temel değerlendirmesi - üç aylık.
- Erişim resertifikasyonu - ayrıcalıklılar için üç aylık, standart için yıllık.
- DR / geri yükleme tatbikatı - yılda en az iki kez, biri tam yedekleme
  geçişi.
- Masa başı tatbikatı (olay müdahalesi) - yılda asgari iki kez.
- TOM iç denetimi - yıllık (`06-organizational-measures/internal-audit.md`).

## 8. Kanıt Deposu

Tüm kontrol kanıtları `11-audit-compliance/evidence/` altında dosyalanır ve
kontrol kimliği ile indekslenir. Denetim programı
(`06-organizational-measures/internal-audit.md`) örnekleme metodolojisini ve
CAPA takibini tanımlar.
