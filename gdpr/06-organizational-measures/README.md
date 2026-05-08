---
title:
  en: "Organizational Measures - GDPR Article 24 / 28 / 32 / 35"
  tr: "Organizasyonel Tedbirler - GDPR Madde 24 / 28 / 32 / 35"
section: "06-organizational-measures"
document_type: "domain_index"
owner:
  primary: "Data Protection Officer (DPO)"
  secondary: "CISO, Head of Legal, HR Lead"
review_cycle: "annual"
last_review: "2026-05-08"
next_review: "2027-05-08"
classification: "Internal"
language: ["en", "tr"]
references:
  - "GDPR Art. 5(2), 24, 25, 28, 29, 32, 35, 36, 37-39, 88"
  - "ISO/IEC 27001:2022, ISO/IEC 27002:2022"
  - "ISO/IEC 27701:2019 - Privacy Information Management"
  - "ISO/IEC 27018:2019 - PII in public clouds"
  - "ISO/IEC 29134:2017 - Privacy Impact Assessment"
  - "NIST CSF 2.0 - Govern function"
  - "EDPB Guidelines on data subject rights, breach notification, DPIAs"
---

## English

# Organizational Measures - GDPR

## 1. Purpose and Scope

This domain (`06-organizational-measures`) consolidates the human, procedural
and contractual controls that complement the technical measures in
`05-technical-measures`. Article 32(1) requires "appropriate technical and
organisational measures" - the two sets are inseparable. Article 24 holds
the controller accountable for implementing them; Article 28 governs the
processor relationship; Article 35 mandates the DPIA where high risk arises;
Article 5(2) makes the controller responsible for demonstrating compliance.

## 2. Documents in this Domain

| # | File | Subject | Primary Article(s) |
|---|------|---------|--------------------|
| 1 | `README.md` | Domain overview | Art. 24, 32(1) |
| 2 | `policies-procedures.md` | Policy hierarchy and lifecycle | Art. 24(2) |
| 3 | `training.md` | Onboarding + annual + role-based + phishing simulation | Art. 39(1)(b), 32(4) |
| 4 | `confidentiality-undertaking.md` | Templates: employee, contractor, intern | Art. 28(3)(b), 29, 32(4) |
| 5 | `vendor-management.md` | DPA, sub-processors, due diligence; full DPA template | Art. 28 |
| 6 | `dpia.md` | Triggers, 11-section template, ISO 29134 | Art. 35, 36 |
| 7 | `internal-audit.md` | Three lines of defence, sample tests, CAPA | Art. 24(1), 32(1)(d) |
| 8 | `organizational-controls-checklist.md` | 60+ items cross-mapped | Art. 24, 28, 32, 35 |

## 3. Operating Model - Three Lines of Defence

| Line | Owner | Role |
|------|-------|------|
| 1 | Business / Engineering / Operations | Own and operate controls in daily processes |
| 2 | Privacy Office (DPO), Information Security (CISO), Compliance | Set policy, advise, monitor |
| 3 | Internal Audit | Provide independent assurance to the Board |

External assurance (auditors, certification bodies, supervisory authorities)
sits beyond the three lines but consumes their evidence.

## 4. Roles and Accountability

| Role | Article | Responsibility Summary |
|------|---------|------------------------|
| Controller (Board, executive) | 24 | Determines purposes and means; accountable for compliance |
| Joint controllers | 26 | Define respective responsibilities in an arrangement |
| Processor | 28 | Acts only on documented instructions |
| Sub-processor | 28(2)(4) | Bound back-to-back via written contract |
| Data Protection Officer | 37-39 | Independent advisory; monitors compliance; cooperates with DPA |
| CISO | (org) | Operates the security programme |
| Information / Data Owners | (org) | Accountable for data sets in their domain |
| Records Manager | (org) | Maintains ROPA accuracy |
| Privacy Champions | (org) | Embed privacy in business units |
| Workforce | 32(4), 29 | Process only on instructions; confidentiality bound |

The DPO has direct reporting to the highest level of management
(Article 38(3)), receives sufficient resources, and operates with
independence. Conflicts of interest documented; tasks not creating conflict
listed. Contact details published in the privacy notice
(`03-transparency-consent/`) and to the supervisory authority.

## 5. Policy Stack

A layered policy hierarchy keeps documentation sustainable:

```
Privacy Policy (external)
Information Security Policy
        |-- Access Management Policy
        |-- Encryption Policy
        |-- Backup and Recovery Policy
        |-- Vendor Management Policy
        |-- BYOD / MDM Policy
        |-- Clean Desk and Screen Policy
        |-- Cookie Policy (external)
        |-- Marketing and Direct Communications Policy
        |-- Employee Privacy Notice (internal)
        |-- CCTV / Visual Monitoring Notice
        |-- Acceptable Use Policy
        |-- Data Classification and Handling Policy
        |-- Records Retention Schedule
        |-- DPIA Procedure
        |-- Incident Response Plan
        |-- Vendor / DPA Templates
```

Each policy has owner, scope, version, review date, distribution list and
exception process. Detailed in `policies-procedures.md`.

## 6. Training and Awareness

Article 32(4) and 39(1)(b) effectively oblige training. The programme is
detailed in `training.md`:

- Onboarding privacy + security training within 30 days of joining.
- Annual refresher mandatory; completion gated against system access.
- Role-based deeper modules for high-risk roles (engineering, support,
  marketing, HR, finance, legal, DPO team).
- Quarterly phishing simulation plus event-driven micro-training.
- Effectiveness measurement at Kirkpatrick Levels 1-3.

## 7. Vendor and Processor Management

Article 28 requires that processors offer "sufficient guarantees" and act
under a written contract with mandatory clauses. The vendor lifecycle is
captured in `vendor-management.md` and includes:

- Vendor classification by risk.
- Due diligence (ISO 27001, ISO 27701, SOC 2, pen test summary, BCP).
- Mandatory DPA with sub-processor regime.
- Continuous monitoring (security ratings, SLA, incident reporting).
- Exit strategy.

A full DPA template (EU-style) is included in that document.

## 8. Data Protection Impact Assessment

Article 35 mandates a DPIA where processing is likely to result in high risk.
The procedure, mandatory triggers, 11-section template and Article 36 prior
consultation pathway are in `dpia.md`.

## 9. Internal Audit

Article 24(1) requires the controller to be able to demonstrate compliance.
The audit programme in `internal-audit.md` provides:

- Annual plan based on risk.
- Sample test procedures (ROPA accuracy, notice deployment, consent records,
  vendor contracts, retention destruction, DSR SLA, breach log, MFA
  enforcement, training completion).
- CAPA tracking through closure.

## 10. Documentation as Accountability

Article 5(2) accountability is satisfied by being able to produce, on demand:

- Records of processing activities (`02-ropa/`).
- Privacy notices and consent evidence (`03-transparency-consent/`).
- Retention schedule and destruction logs (`04-retention-erasure/`).
- TOM evidence (this domain + `05-technical-measures/`).
- DPIAs and prior consultations.
- DPA register and sub-processor list.
- Training completion records.
- Audit reports and CAPA tracking.
- Breach register and notifications (`08-breach-management/`).
- Data subject request handling logs (`09-data-subject-rights/`).

The evidence repository is structured under `11-audit-compliance/evidence/`.

## 11. Cross-References

| Theme | This Domain | Other Domain |
|-------|-------------|--------------|
| MFA enforcement | training.md | 05-technical-measures/authentication.md |
| Vendor security | vendor-management.md | 05-technical-measures/* |
| Breach drills | training.md | 08-breach-management/* |
| Consent records | internal-audit.md | 03-transparency-consent/* |
| ROPA accuracy | internal-audit.md | 02-ropa/* |
| Retention enforcement | internal-audit.md | 04-retention-erasure/* |
| DSR SLAs | internal-audit.md | 09-data-subject-rights/* |
| International transfers | vendor-management.md | 07-international-transfers/* |

---

## Türkçe

# Organizasyonel Tedbirler - GDPR

## 1. Amaç ve Kapsam

Bu alan (`06-organizational-measures`), `05-technical-measures` altındaki
teknik tedbirleri tamamlayan insan, prosedürel ve sözleşmesel kontrolleri
bir araya getirir. Madde 32(1) "uygun teknik ve organizasyonel tedbirleri"
gerektirir - iki set ayrılamaz. Madde 24 kontrolörü bunları uygulamaktan
sorumlu tutar; Madde 28 işleyici ilişkisini yönetir; Madde 35 yüksek risk
ortaya çıktığında VKD'yi zorunlu kılar; Madde 5(2) kontrolörün uyumu
göstermekten sorumlu olmasını sağlar.

## 2. Bu Alandaki Belgeler

| # | Dosya | Konu | Birincil Madde(ler) |
|---|-------|------|---------------------|
| 1 | `README.md` | Alan genel bakışı | Md. 24, 32(1) |
| 2 | `policies-procedures.md` | Politika hiyerarşisi ve yaşam döngüsü | Md. 24(2) |
| 3 | `training.md` | Onboarding + yıllık + rol bazlı + phishing simülasyonu | Md. 39(1)(b), 32(4) |
| 4 | `confidentiality-undertaking.md` | Şablonlar: çalışan, yüklenici, stajyer | Md. 28(3)(b), 29, 32(4) |
| 5 | `vendor-management.md` | DPA, alt-işleyiciler, durum tespiti; tam DPA şablonu | Md. 28 |
| 6 | `dpia.md` | Tetikleyiciler, 11-bölümlü şablon, ISO 29134 | Md. 35, 36 |
| 7 | `internal-audit.md` | Üç savunma hattı, örnek testler, CAPA | Md. 24(1), 32(1)(d) |
| 8 | `organizational-controls-checklist.md` | 60+ madde çapraz eşlenmiş | Md. 24, 28, 32, 35 |

## 3. İşletim Modeli - Üç Savunma Hattı

| Hat | Sahip | Rol |
|-----|-------|-----|
| 1 | İş / Mühendislik / Operasyonlar | Günlük süreçlerde kontrolleri sahiplenir ve işletir |
| 2 | Gizlilik Ofisi (DPO), Bilgi Güvenliği (CISO), Uyum | Politika belirler, danışmanlık verir, izler |
| 3 | İç Denetim | Yönetim Kuruluna bağımsız güvence sağlar |

Dış güvence (denetçiler, sertifikasyon kuruluşları, denetim otoriteleri)
üç hattın ötesinde durur ancak kanıtlarını tüketir.

## 4. Roller ve Hesap Verebilirlik

| Rol | Madde | Sorumluluk Özeti |
|-----|-------|------------------|
| Kontrolör (Yönetim Kurulu, üst yönetim) | 24 | Amaçları ve araçları belirler; uyumdan sorumludur |
| Müşterek kontrolörler | 26 | Bir düzenlemede ilgili sorumlulukları tanımlar |
| İşleyici | 28 | Yalnızca belgelenmiş talimatlarla hareket eder |
| Alt-işleyici | 28(2)(4) | Yazılı sözleşmeyle aynı koşullarda bağlanır |
| Veri Koruma Sorumlusu | 37-39 | Bağımsız danışmanlık; uyumu izler; DPA ile işbirliği yapar |
| CISO | (org) | Güvenlik programını işletir |
| Bilgi / Veri Sahipleri | (org) | Alanlarındaki veri kümelerinden sorumludur |
| Kayıt Yöneticisi | (org) | ROPA doğruluğunu sürdürür |
| Gizlilik Şampiyonları | (org) | Gizliliği iş birimlerine yerleştirir |
| İş Gücü | 32(4), 29 | Yalnızca talimatlarla işler; gizlilikle bağlıdır |

DPO en üst yönetim seviyesine doğrudan raporlama hakkına sahiptir
(Madde 38(3)), yeterli kaynak alır ve bağımsızlıkla çalışır. Çıkar
çatışmaları belgelenir; çatışma yaratmayan görevler listelenir. İletişim
bilgileri gizlilik bildiriminde (`03-transparency-consent/`) ve denetim
otoritesine yayımlanır.

## 5. Politika Yığını

Katmanlı bir politika hiyerarşisi belgelendirmeyi sürdürülebilir tutar:

```
Gizlilik Politikası (dış)
Bilgi Güvenliği Politikası
        |-- Erişim Yönetimi Politikası
        |-- Şifreleme Politikası
        |-- Yedekleme ve Geri Yükleme Politikası
        |-- Tedarikçi Yönetimi Politikası
        |-- BYOD / MDM Politikası
        |-- Temiz Masa ve Ekran Politikası
        |-- Çerez Politikası (dış)
        |-- Pazarlama ve Doğrudan İletişim Politikası
        |-- Çalışan Gizlilik Bildirimi (dahili)
        |-- CCTV / Görsel İzleme Bildirimi
        |-- Kabul Edilebilir Kullanım Politikası
        |-- Veri Sınıflandırma ve İşleme Politikası
        |-- Kayıt Saklama Programı
        |-- VKD Prosedürü
        |-- Olay Müdahale Planı
        |-- Tedarikçi / DPA Şablonları
```

Her politikanın sahibi, kapsamı, sürümü, inceleme tarihi, dağıtım listesi
ve istisna süreci vardır. Ayrıntıları `policies-procedures.md` içinde.

## 6. Eğitim ve Farkındalık

Madde 32(4) ve 39(1)(b) etkili olarak eğitim zorunluluğu getirir. Program
`training.md` içinde ayrıntılıdır:

- İşe başlamadan 30 gün içinde onboarding gizlilik + güvenlik eğitimi.
- Zorunlu yıllık tazeleme; tamamlama sistem erişimine karşı kapı tutulur.
- Yüksek riskli roller için rol bazlı daha derin modüller (mühendislik,
  destek, pazarlama, İK, finans, hukuk, DPO ekibi).
- Olay odaklı mikro eğitim artı üç aylık phishing simülasyonu.
- Kirkpatrick Seviye 1-3'te etkinlik ölçümü.

## 7. Tedarikçi ve İşleyici Yönetimi

Madde 28, işleyicilerin "yeterli garantiler" sunmasını ve zorunlu maddelerle
yazılı sözleşme altında hareket etmesini gerektirir. Tedarikçi yaşam
döngüsü `vendor-management.md` içinde yakalanır ve şunları içerir:

- Riske göre tedarikçi sınıflandırması.
- Durum tespiti (ISO 27001, ISO 27701, SOC 2, sızma testi özeti, BCP).
- Alt-işleyici rejimi ile zorunlu DPA.
- Sürekli izleme (güvenlik derecelendirmeleri, SLA, olay raporlama).
- Çıkış stratejisi.

Tam bir DPA şablonu (AB tarzı) o belgede yer alır.

## 8. Veri Koruma Etki Değerlendirmesi

Madde 35, işlemenin yüksek riskle sonuçlanma olasılığı olan yerde VKD'yi
zorunlu kılar. Prosedür, zorunlu tetikleyiciler, 11-bölümlü şablon ve
Madde 36 ön danışma yolu `dpia.md` içindedir.

## 9. İç Denetim

Madde 24(1), kontrolörün uyumu gösterebilmesini gerektirir.
`internal-audit.md` içindeki denetim programı şunları sağlar:

- Riske dayalı yıllık plan.
- Örnek test prosedürleri (ROPA doğruluğu, bildirim dağıtımı, onay kayıtları,
  tedarikçi sözleşmeleri, saklama imhası, DSR SLA, ihlal logu, MFA
  uygulaması, eğitim tamamlama).
- Kapanışa kadar CAPA takibi.

## 10. Hesap Verebilirlik Olarak Belgeleme

Madde 5(2) hesap verebilirliği, talep üzerine üretebilme yeteneği ile
karşılanır:

- İşleme faaliyetleri kayıtları (`02-ropa/`).
- Gizlilik bildirimleri ve onay kanıtı (`03-transparency-consent/`).
- Saklama programı ve imha logları (`04-retention-erasure/`).
- TOM kanıtı (bu alan + `05-technical-measures/`).
- VKD'ler ve ön danışmalar.
- DPA kayıt defteri ve alt-işleyici listesi.
- Eğitim tamamlama kayıtları.
- Denetim raporları ve CAPA takibi.
- İhlal kayıt defteri ve bildirimler (`08-breach-management/`).
- Veri sahibi talebi işleme logları (`09-data-subject-rights/`).

Kanıt deposu `11-audit-compliance/evidence/` altında yapılandırılmıştır.

## 11. Çapraz Referanslar

| Tema | Bu Alan | Diğer Alan |
|------|---------|-----------|
| MFA uygulaması | training.md | 05-technical-measures/authentication.md |
| Tedarikçi güvenliği | vendor-management.md | 05-technical-measures/* |
| İhlal tatbikatları | training.md | 08-breach-management/* |
| Onay kayıtları | internal-audit.md | 03-transparency-consent/* |
| ROPA doğruluğu | internal-audit.md | 02-ropa/* |
| Saklama uygulaması | internal-audit.md | 04-retention-erasure/* |
| DSR SLA'ları | internal-audit.md | 09-data-subject-rights/* |
| Uluslararası aktarımlar | vendor-management.md | 07-international-transfers/* |
