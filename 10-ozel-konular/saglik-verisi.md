---
Doküman / Document: Sağlık Verisi Yönetimi (m.6 Özel Nitelikli) / Health Data Management (Art. 6 Special Category)
Bölüm / Section: 10-ozel-konular
Sahip / Owner: KVKK Sorumlusu + İK + İSG Birimi + (varsa) İşyeri Hekimi / KVKK Officer + HR + OHS Unit + (if applicable) Workplace Physician
Onaylayan / Approved by: Hukuk Müdürü + KVKK Komitesi / Head of Legal + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + sektör mevzuatı değişikliklerinde / Annual + on sectoral legislation changes
İlgili Mevzuat / Legal Reference: Law No. 6698 (KVKK) Art. 6; Law No. 6331 (Occupational Health and Safety); Law No. 4857 (Labor Law); Law No. 5510 (SGK); Law No. 3359 (Basic Health Services); Statutory Decree No. 663; Personal Health Data Regulation (Official Gazette 30808 dated 21.06.2019); Authority Decision 2018/10
---

## English

# Health Data Management

## 1. Definition and Scope

Health data is **special category** personal data under KVKK Art. 6(1). For our company, health data flows through the following channels:

| Channel | Data Type |
|---------|-----------|
| Pre-employment medical | Lab report, vision, hearing, blood test |
| Periodic medical exam | Mandatory under OHS |
| Sick leave certificate | Disease type (ICD-10), days off |
| Work accident | Statement, medical report, disability degree |
| Occupational disease | Diagnosis, follow-up reports |
| Vaccination records (e.g., COVID-19) | Vaccine type, date, certificate |
| Disability | Disability medical report |
| Pregnancy / breastfeeding | Process information |
| Insurance claim | Medical diagnosis, invoice |
| Customer (private sector - non-health) | Generally limited; special-needs requests |

> **Sex-life data:** Regulated together with KVKK Art. 6; very limited in our context (e.g., records of sexual harassment incidents).

## 2. Legal Grounds

### 2.1. KVKK Art. 6(2) - Explicit Consent

The general rule; however, due to employee-employer asymmetry, problematic in practice (freedom test).

### 2.2. KVKK Art. 6(3) - Express Provision in Laws

Health and sex-life data may be processed without explicit consent only for the purposes of **public health protection, preventive medicine, medical diagnosis, treatment and care services, planning and management of health services and their financing**, and **only by persons under a secrecy obligation or authorized institutions/organizations**.

> This covers most workplace health data being processed by the **workplace physician** or an **outsourced OHS firm** - not the company itself.

### 2.3. Other Legal Grounds

- Law No. 6331 (OHS): pre-employment + periodic exams mandatory.
- Law No. 4857: workplace health conditions.
- Law No. 5510 (SGK): medical reports, premium calculation.
- Law No. 657 (public sector): different regime.

## 3. Secrecy Obligation

Healthcare professionals processing health data:

- Physicians (Medical Chamber, secrecy under Turkish Criminal Code Art. 258).
- Nurses, midwives.
- Pharmacists, dentists.
- Workplace physicians (additional under Law 6331).
- Other healthcare staff.

> **Internal arrangement:** Workplace health data is not accessible to general staff but **only to the workplace physician + OHS specialist + KVKK Officer (limited, for audit)**.

## 4. Data Flow (Typical Workplace)

```
Employee -> Workplace physician (under secrecy)
                |
         Health file (physician archive - encrypted)
                |
         HR (only "examined / not" + fitness for work)
                |
         Production / Operations (only "not fit" outcome)
```

HR does **not** receive diagnosis/illness data. Only "fit / unfit / restricted" status.

## 5. Access Control

### 5.1. Access Matrix

| Role | Access |
|------|--------|
| Workplace physician | Full access - under secrecy |
| OHS specialist | Limited (risk assessment) |
| HR Director | "Fit/Unfit" + indirect (sick-day count) |
| HR specialist | Sick-leave tracking (with reports) |
| KVKK Officer | Audit only with approval |
| Legal | In incidents (accident, lawsuit) |
| Management | Summary in incident |
| Other employees | FORBIDDEN |

### 5.2. System Access

- The medical file is in a **separate system** (HER, EHR, workplace physician software).
- General HR system has **limited** health data (sick days, certificate dates).
- Encryption mandatory.
- Audit log on every access.

## 6. Retention Period

| Data | Period | Source |
|------|--------|--------|
| Pre-employment medical | **15 years** post-employment | Law 6331 + workplace physician legislation |
| Periodic medical exam | Same | Same |
| Work accident record | **15 years** (statute of limitations) | Law 5510 + work accident legislation |
| Occupational disease | **30 years** | Court of Cassation case law |
| Sick-leave certificate | Year + **5 years** | HR good practice |
| Pregnancy / breastfeeding | End of process + **5 years** | HR |

## 7. Transfers

### 7.1. SGK / e-Bildirge

- Transfer to SGK is a statutory obligation (Law 5510).
- KVKK Art. 6(3) + Art. 5(2)(a).
- Disclosure + information.

### 7.2. MEDULA, e-Reçete

- Ministry of Health systems.
- Used by the workplace physician.
- The data controller is the company; the Ministry is not a processor, but a special regime applies.

### 7.3. Insurance (Private Health)

- Transfers during private insurance claim processes.
- Explicit consent required (when signing the insurance contract).
- Need-to-know minimum data.

### 7.4. Cross-Border Transfer

- Very limited (e.g., information sharing across international employer offices).
- KVKK Art. 9 + Standard Contract + DPIA.
- Preferred: process within Türkiye.

## 8. Technical Measures (Decision 2018/10)

- AES-256 encryption at rest.
- TLS 1.3 in transit.
- HSM/KMS key management.
- DLP - health-data label.
- Access log + UEBA anomalies.
- Encrypted backups.
- Pseudonymization (separate reference between HR and the medical file).
- Column-level database encryption (especially the ICD-10 field).

## 9. Administrative Measures

- Health data policy (this document + supplementary procedure).
- Workplace physician contract - KVKK compliant.
- Annual secrecy declaration.
- Training - health data awareness.
- Annual audit.

## 10. HIMSS / HL7 / FHIR Compliance

If health integration is involved:

### 10.1. HL7 v2 / v3
- Messaging standard.
- Patient data fields (PID, ORC, OBR, OBX).

### 10.2. FHIR (Fast Healthcare Interoperability Resources)
- REST API based.
- Resource oriented (Patient, Observation, Condition, MedicationRequest).
- For KVKK compliance:
   - OAuth 2.0 + SMART on FHIR.
   - Audit logger (FHIR AuditEvent).
   - Consent resource for consent management.

### 10.3. HIMSS EMR Maturity Model
- Levels 0-7.
- Türkiye-specific layers under KVKK (Authority decisions, sectoral legislation).

## 11. SGK Integrations

### 11.1. e-Bildirge
- Monthly premium notifications.
- Additional employee health-data reports (work accidents, occupational diseases).

### 11.2. e-Reçete
- Used by the workplace physician.
- Does not flow into the general company system.

### 11.3. MEDULA
- Between healthcare service providers and SGK.
- May integrate if there is private insurance for company employees.

## 12. Sensitive Topic - Vaccine / Pandemic Data

From COVID-19 experience:

- Vaccination certificate is special category.
- "Are you vaccinated?" query with explicit consent.
- Statutory obligation (public health) limited cases under Art. 6(3).
- Past applications like the HES code era are gone; current similar cases require a **DPIA**.

## 13. Data Subject Rights

- Art. 11(b): Health-file copy may be requested -> via the **workplace physician**, with KVKK Officer coordination.
- Art. 11(d): Rectification - medical-report rectification requires clinical action; the company only fixes records.
- Art. 11(e): Erasure - refused within statutory retention; deleted thereafter.
- Where there is conflict with the secrecy obligation, Legal + Physician are consulted.

## 14. Common Mistakes

| Mistake | Correct approach |
|---------|------------------|
| Storing diagnosis in general HR system | Only "fit/unfit"; diagnosis in physician system |
| Sharing health info with other employees | Forbidden - secrecy violation + criminal under TCC |
| Vaccine list visible to managers | Leadership report only "X / Y" totals |
| Health + HR in the same database | Pseudonymize, separate schema |
| Mandating instead of explicit consent | OHS obligation handled via Art. 6(3) |
| 5-year retention | 15 years + (occupational disease 30 years) |
| Foreign cloud for health data | Türkiye location preferred |
| Unencrypted e-mail with the report | KEP + encrypted attachment |

## 15. KPIs

| KPI | Target |
|-----|--------|
| Audit log on health-data access | 100% |
| Encryption coverage | 100% |
| Annual secrecy declaration | 100% |
| Diagnosis stored in HR | 0% |
| Transfer DPA + KVKK compliance | 100% |
| Health DPIA current | Annual |

## 16. Version History

| Version | Date | Change | Approval |
|---------|------|--------|----------|
| 1.0 | 2026-05-08 | First publication | KVKK Committee |

---

## Türkçe

# Sağlık Verisi Yönetimi

## 1. Tanım ve Kapsam

Sağlık verisi, KVKK m.6/1 kapsamında **özel nitelikli** kişisel veridir. Şirketimiz açısından sağlık verisi şu kanallardan geçer:

| Kanal | Veri Tipi |
|-------|-----------|
| İşe giriş muayenesi | Tetkik raporu, görme, işitme, kan testi |
| Periyodik sağlık muayenesi | İSG kapsamında zorunlu |
| Devamsızlık raporu | Hastalık tipi (ICD-10), istirahat süresi |
| İş kazası | Tutanak, tıbbi rapor, malüliyet derecesi |
| Meslek hastalığı | Tanı, takip raporları |
| Aşı kayıtları (örn. COVID-19) | Aşı tipi, tarih, sertifika |
| Maluliyet, engellilik | Engelli sağlık raporu |
| Hamilelik / emzirme | Süreç bilgisi |
| Sigorta tazmin talebi | Tıbbi tanı, fatura |
| Müşteri (özel sektör — sağlık dışı) | Genelde sınırlı; özel destek talebi |

> **Cinsel hayat verisi:** KVKK m.6 ile birlikte düzenlenir; Şirket bağlamında çok sınırlı (örn. cinsel taciz olayı kayıtları).

## 2. Hukuki Sebepler

### 2.1. KVKK m.6/2 - Açık Rıza

Genel kural; ancak çalışan-işveren asimetrisi nedeniyle pratikte sorunludur (özgürlük testi).

### 2.2. KVKK m.6/3 - Kanunlarda Açıkça Öngörülmesi

Sağlık ve cinsel hayat verisi açık rıza aranmaksızın ancak **kamu sağlığının korunması, koruyucu hekimlik, tıbbi teşhis, tedavi ve bakım hizmetlerinin yürütülmesi, sağlık hizmetleri ile finansmanının planlanması ve yönetimi** amaçlarıyla ve **sır saklama yükümlülüğü altında bulunan kişiler veya yetkili kurum ve kuruluşlar** tarafından işlenebilir.

> Bu, çoğu işyeri sağlık verisinin **işyeri hekimi** veya **dış İSG firması** tarafından işlenmesini kapsar — Şirketin kendisi değil.

### 2.3. Diğer Yasal Sebepler

- 6331 sayılı İSG: işe giriş + periyodik muayene zorunlu.
- 4857: çalışma ortamı sağlık koşulları.
- 5510 SGK: sağlık raporu, prim hesabı.
- 657 sayılı (kamu): farklı rejim.

## 3. Sır Saklama Yükümlülüğü

Sağlık verisi işleyen meslek mensupları:
- Hekim (Tabip Odası, sır yükümlülüğü TCK m.258).
- Hemşire, ebe.
- Eczacı, diş hekimi.
- İşyeri hekimi (6331 ek yükümlülük).
- Diğer sağlık personeli.

> **Şirket içi düzenleme:** İşyeri sağlık verisi şirket genel personeline değil, **sadece işyeri hekimi + İSG uzmanı + KVKK sorumlusu (denetim için sınırlı)** erişebilir.

## 4. Veri Akışı (Tipik İşyeri)

```
Çalışan → İşyeri Hekimi (sır saklama altında)
              ↓
       Sağlık dosyası (hekim arşivi — şifreli)
              ↓
       İK (sadece "muayene oldu/olmadı" + iş için uygunluk)
              ↓
       Üretim / Operasyon (sadece "uygun değil" sonucu)
```

İK'ya **tanı/teşhis** verisi gitmez. Sadece "iş için uygun / değil / kısıtlı" bilgisi.

## 5. Erişim Kontrolü

### 5.1. Erişim Matrisi

| Rol | Erişim |
|-----|--------|
| İşyeri Hekimi | Tam erişim — sır saklama altında |
| İSG Uzmanı | Erişim — sınırlı (risk değerlendirme) |
| İK Direktörü | "Uygun/Değil" + dolaylı bilgi (raporlu gün sayısı) |
| İK Uzmanı | Devamsızlık takibi (raporlu) |
| KVKK Sorumlusu | Denetim için sınırlı + onay |
| Hukuk | Olay halinde (kazada, davada) |
| Yönetim | Olay halinde özet |
| Diğer çalışan | YASAK |

### 5.2. Sistem Erişimi

- Sağlık dosyası **ayrı sistemde** (HER, EHR, işyeri hekimi yazılımı).
- Genel İK sisteminde sağlık verisi **sınırlı** (raporlu gün, sertifika tarihi).
- Şifreleme zorunlu.
- Audit log her erişim.

## 6. Saklama Süresi

| Veri | Süre | Kaynak |
|------|------|--------|
| İşe giriş muayenesi | İş akdi sonrası **15 yıl** | 6331 sayılı Kanun + işyeri hekimi mevzuatı |
| Periyodik muayene | Aynı | Aynı |
| İş kazası kaydı | **15 yıl** (zamanaşımı) | 5510 + iş kazası mevzuatı |
| Meslek hastalığı | **30 yıl** | Yargıtay içtihatları |
| Devamsızlık raporu | İlgili yıl + **5 yıl** | İK iyi pratiği |
| Hamilelik / emzirme | Süreç sonu + **5 yıl** | İK |

## 7. Aktarım

### 7.1. SGK / E-Bildirge

- SGK'ya aktarım kanuni yükümlülük (5510).
- KVKK m.6/3 kapsamı + m.5/2-a.
- Aydınlatma + bilgilendirme.

### 7.2. MEDULA, e-Reçete

- Sağlık Bakanlığı sistemleri.
- İşyeri hekimi tarafından kullanılır.
- Veri sorumlusu Şirket; veri işleyen Bakanlık değildir, ancak özel rejim.

### 7.3. Sigorta (Özel Sağlık)

- Özel sigorta tazmin sürecinde aktarım.
- Açık rıza zorunlu (sigorta sözleşmesi imzasında).
- Gerekli minimum veri (Need-to-Know).

### 7.4. Yurt Dışı Aktarım

- Çok sınırlı (örn. uluslararası işveren ofisleri arası bilgi paylaşımı).
- KVKK m.9 + Standart Sözleşme + DPIA.
- Tercih: Türkiye sınırları içinde işleme.

## 8. Teknik Tedbirler (Kurul 2018/10)

- AES-256 şifreleme at rest.
- TLS 1.3 in transit.
- HSM/KMS anahtar yönetimi.
- DLP — sağlık verisi etiketi.
- Erişim log + UEBA anomalisi.
- Yedekleme şifreli.
- Pseudonymization (IK ile sağlık dosyası referans ayrı).
- Veritabanı kolon bazlı şifreleme (özellikle ICD-10 alanı).

## 9. İdari Tedbirler

- Sağlık verisi politikası (bu doküman + ek prosedür).
- İşyeri hekimi sözleşmesi — KVKK uyumlu.
- Sır saklama yükümlülüğü beyanı (yıllık).
- Eğitim — sağlık verisi farkındalık.
- Audit — yıllık.

## 10. HIMSS / HL7 / FHIR Uyumu

Sağlık entegrasyonu söz konusuysa:

### 10.1. HL7 v2 / v3
- Mesaj standardı.
- Hasta verisi alanları (PID, ORC, OBR, OBX).

### 10.2. FHIR (Fast Healthcare Interoperability Resources)
- REST API tabanlı.
- Resource bazlı (Patient, Observation, Condition, MedicationRequest).
- KVKK uyumu için:
   - OAuth 2.0 + SMART on FHIR.
   - Audit logger (FHIR AuditEvent).
   - Consent resource ile rıza yönetimi.

### 10.3. HIMSS EMR Olgunluk Modeli
- 0-7 seviye.
- KVKK gereği Türkiye uygulaması ek katmanlar (KVK Kurul kararları, sektör mevzuatı).

## 11. SGK Entegrasyonları

### 11.1. e-Bildirge
- Aylık prim bildirimi.
- Çalışan sağlık verisi ek bildirimleri (iş kazası, meslek hastalığı).

### 11.2. e-Reçete
- İşyeri hekimi kullanır.
- Şirket genel sistemine yansımaz.

### 11.3. MEDULA
- Sağlık hizmeti sunucularıyla SGK arası.
- Şirket çalışanları için özel sigorta varsa entegre olabilir.

## 12. Hassas Konu — Aşı / Pandemi Verisi

COVID-19 deneyiminden:
- Aşı sertifikası özel nitelikli.
- "Aşı oldu mu?" sorgusu açık rıza ile.
- Yasal zorunluluk (kamu sağlığı) sınırlı durumlarda m.6/3.
- HES kodu vb. eski uygulamalar dönemi geçti; mevcut benzer durumlarda **DPIA** yapılır.

## 13. İlgili Kişi Hakları

- m.11/b: Sağlık dosyası kopyası talep edilebilir → **işyeri hekimi** üzerinden, Şirket KVKK Sorumlusu koordinasyon.
- m.11/d: Düzeltme — tıbbi rapor düzeltme klinik gerektirir; Şirket sadece kayıt düzeltir.
- m.11/e: Silme — yasal saklama süresi içinde reddedilir; sonrasında silinir.
- Sır saklama yükümlülüğüyle çatışmada Hukuk + Hekim danışılır.

## 14. Tipik Hatalar

| Hata | Doğru Yaklaşım |
|------|----------------|
| İK genel sisteminde tanı saklamak | Sadece "uygun/değil"; tanı hekim sisteminde |
| Diğer çalışana sağlık paylaşımı | Yasak — sır ihlali + TCK suç |
| Toplu aşı listesi yöneticide görünür | Liderlik raporu sadece "X / Y" toplam |
| Sağlık + IK aynı veritabanında | Pseudonymize, ayrı şema |
| Açık rıza yerine zorunlu kılma | İSG zorunluluğu m.6/3 ile çözülür |
| 5 yıl saklama | 15 yıl + (meslek hastalığı 30 yıl) |
| Yurt dışı bulut sağlık verisi | Türkiye yerleşim tercih |
| Şifresiz e-postada rapor | KEP + şifreli ek |

## 15. KPI'lar

| KPI | Hedef |
|-----|-------|
| Sağlık verisine erişim audit log | %100 |
| Şifreleme kapsamı | %100 |
| Yıllık sır saklama beyanı | %100 |
| İK'da tanı saklama | %0 |
| Aktarım DPA + KVKK uyum | %100 |
| Sağlık DPIA güncel | Yıllık |

## 16. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi |
