---
Doküman / Document: Bulut Hizmetleri Yönetimi (SaaS / PaaS / IaaS) / Cloud Services Management (SaaS / PaaS / IaaS)
Bölüm / Section: 10-ozel-konular
Sahip / Owner: KVKK Sorumlusu + CISO + IT Müdürü / KVKK Officer + CISO + IT Manager
Onaylayan / Approved by: Hukuk Müdürü + KVKK Komitesi + CTO / Head of Legal + KVKK Committee + CTO
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + Kurul aktarım kararı değişikliklerinde / Annual + on Authority transfer decision changes
İlgili Mevzuat / Legal Reference: Law No. 6698 (KVKK) Art. 9, 12; KVKK Cross-Border Transfer Legislation (Art. 9 amendment); KVKK 2024 Standard Contract; US CLOUD Act / FISA 702; ISO/IEC 27017; ISO/IEC 27018; CCPA / GDPR (comparative)
---

## English

# Cloud Services Management

## 1. Purpose

KVKK-compliant selection, contracting, implementation, and audit of SaaS, PaaS, IaaS services. Cloud is one of the **broadest** and most KVKK-risky surfaces of personal data processing for the company.

## 2. Cloud Models and Shared Responsibility

### 2.1. Service Tiers

| Tier | Provider Responsibility | Customer Responsibility |
|------|-------------------------|--------------------------|
| **IaaS** (AWS EC2, Azure VM, GCP Compute) | Physical infrastructure, hypervisor | OS, application, data, users |
| **PaaS** (Azure App Service, AWS Lambda, GCP Cloud Run) | Infrastructure + runtime | Application + data |
| **SaaS** (Microsoft 365, Salesforce, HubSpot) | Full stack | Data + access management |

### 2.2. Shared Responsibility Model

- **Cloud OF the cloud** - the provider's infrastructure security.
- **Cloud IN the cloud** - the customer's data and application security.
- For KVKK: the customer (us) remains the **data controller**; the provider is generally a **data processor**.

### 2.3. Determining Controller vs. Processor

| Scenario | Provider's Capacity |
|----------|----------------------|
| Customer data on AWS S3 | Processor (we are responsible) |
| Salesforce CRM use | Processor |
| Mailchimp e-mail dispatch | Processor |
| Microsoft 365 mail server | Processor (typically) |
| LinkedIn marketing platform | Mixed - LinkedIn may also be controller in cases |
| Google Workspace | Processor |
| OpenAI ChatGPT (enterprise API) | Processor (per OpenAI contract) |

> Contractual control determines status - DPA details are critical.

## 3. Data Residency and Region Selection

### 3.1. Türkiye Region Preference Order

1. **Türkiye-resident cloud provider / region** (Türk Telekom Bulut, Turkcell Bulut, Akamai Linode Istanbul, AWS Türkiye Local Zone, Azure Türkiye region - current plans).
2. **EU region** - advantageous on adequacy decision (when published by the Authority).
3. **US / Asia** - Standard Contract + supplementary measures.

### 3.2. Data Residency Clause

In the contract:

- "Data shall be processed within **Türkiye / EU** boundaries."
- "Will not be moved to another region without customer (our) approval."
- "Backup and disaster recovery sites also within the same region."

### 3.3. Pseudo-localization Issue

Even if the provider stands up a "Türkiye region":

- The control plane is generally centralized.
- Support staff may have access from abroad.
- Logs may be aggregated centrally.

> Region selection only controls **at-rest** data. Additional safeguards needed for access, logs, support.

## 4. Cross-Border Transfer Analysis

### 4.1. KVKK Art. 9 (Current - 2024)

After the KVKK Art. 9 amendment, the cross-border transfer regime:

- Free transfer to countries with an **adequacy decision**.
- **Standard Contract** (published by the Authority).
- **Binding corporate rules** (BCR - approval process).
- **Explicit consent** (limited, last resort).
- **Temporary / limited situations** (KVKK Art. 9(6)).

### 4.2. Standard Contract

The Authority has published **Standard Contract** modules (2024). Module types:

1. Controller -> Controller (abroad).
2. Controller -> Processor (abroad).
3. Processor -> Sub-processor (abroad).
4. Processor -> Controller (abroad).

> The contract is signed and **notified to the Authority within 5 business days**. Failure to notify does not invalidate the contract but is grounds for sanction.

### 4.3. Transfer Impact Assessment (TIA)

Performed before cross-border transfer:

- Target country's data protection regime.
- Government access requests (FISA, CLOUD Act, etc.).
- Provider transparency reports.
- Additional measures (E2E encryption, customer-held key).
- Residual risk + acceptance.

### 4.4. CLOUD Act (US)

US-resident or US-affiliated providers (Amazon, Microsoft, Google, Apple, Oracle) must disclose data on US government request **regardless of where the data resides**. Conflicts with KVKK.

**Practical:**

- For critical data with US providers, additional measures.
- Customer-managed key (CMK) - the US provider cannot view encrypted data.
- Hold Your Own Key (HYOK) - key in the company's infrastructure.

### 4.5. FISA 702 (US)

US intelligence's ability to obtain data on foreign persons from US providers. The Schrems II ruling (CJEU) struck down Privacy Shield because of this. Similar concerns apply for KVKK.

## 5. DPA (Data Processing Agreement) - Cloud Provider

### 5.1. Minimum Clauses (KVKK Art. 12 + Authority Expectation)

1. Data category, purpose, duration.
2. Provider acts only on **customer instructions**.
3. Confidentiality (NDA + provider-staff secrecy).
4. Technical and administrative measures (ISO 27001, etc.).
5. Sub-processor approval process.
6. Breach notification within 24 hours (tighter than statute).
7. Support for data subject requests.
8. Audit rights + reporting.
9. Data destruction + certificate at end of contract.
10. Cross-border transfer rules.
11. Insurance + liability cap.
12. Dispute resolution (Turkish law preferred).

### 5.2. Standard Cloud Provider DPA Templates

| Provider | DPA Link |
|----------|----------|
| AWS | aws.amazon.com/compliance/data-protection/ |
| Microsoft | microsoft.com/en-us/trust-center/privacy/gdpr-overview |
| Google | cloud.google.com/terms/data-processing-addendum |
| Salesforce | salesforce.com/company/legal/agreements/ |
| HubSpot | legal.hubspot.com/dpa |

> Standard DPAs are GDPR-oriented. A KVKK addendum may be required.

## 6. Key Management

### 6.1. Provider-Managed (Default)

- AWS KMS, Azure Key Vault, GCP KMS standard.
- The provider sees and uses the key.
- KVKK risk: if the key is at the provider, "encrypted storage" is weakened (provider can access).

### 6.2. Customer-Managed Key (CMK / BYOK)

- Key generated by the customer.
- Provided to the provider but rotation and control are customer's.
- Better.

### 6.3. Hold Your Own Key (HYOK)

- Key in the company's infrastructure (HSM).
- The provider asks the company for every decryption.
- Highest protection; performance cost.
- For very sensitive data (e.g., health, finance).

### 6.4. Confidential Computing

- TEE (Trusted Execution Environment), Intel SGX, AMD SEV.
- Memory-level encryption.
- Even the hypervisor/provider cannot access the data.
- New technology - to be evaluated.

## 7. SaaS Special Topics

### 7.1. Microsoft 365

- E-mail, SharePoint, Teams, OneDrive.
- Türkiye region (near future), currently EU.
- DPA + Customer Lockbox + Double Key Encryption options.
- E5 license offers tighter control.

### 7.2. Google Workspace

- Gmail, Drive, Docs, Meet.
- Region: EU or US.
- DPA + Client-side encryption (CSE).

### 7.3. Salesforce

- CRM data.
- EU region (Hyperforce).
- Shield (audit + encryption) extra license.

### 7.4. HubSpot

- CRM + marketing automation.
- EU / Australia region selectable.
- DPA + Standard Contract.

## 8. Cloud Access Management

### 8.1. Identity (IAM)

- Federation (SAML / OIDC) integrated with corporate AD/Entra.
- Mandatory MFA.
- Privileged access - JIT (Just-In-Time).
- IAM role separation (least privilege).

### 8.2. Audit and Logging

- All provider logs (CloudTrail, Azure Activity Log, GCP Audit Logs) sent to central SIEM.
- Configuration changes monitored.
- Anomaly detection.

### 8.3. Configuration Management

- IaC (Terraform, ARM, CloudFormation).
- Public S3 bucket / open port checks.
- CSPM (Cloud Security Posture Management) - Wiz, Prisma, Defender for Cloud.

## 9. Data Portability and Exit Strategy

### 9.1. Vendor Lock-in Risk

- Proprietary formats (Salesforce, HubSpot).
- Scope and migration time.
- End-of-contract data export rights.

### 9.2. Exit Plan

- Exit clause: standard-format export, 90-day data access.
- Regular backup (in our infrastructure).
- Continuously evaluate alternative providers.

### 9.3. Data Deletion Certificate

- At end of contract, the provider must delete data + provide certificate.
- Backup deletion period (60-90 days reasonable).

## 10. CASB and Shadow IT

### 10.1. CASB (Cloud Access Security Broker)

- Microsoft Defender for Cloud Apps, Netskope, Zscaler.
- Cloud usage inventory.
- DLP integration.
- Anomaly detection.

### 10.2. Shadow IT

- SaaS used without approval by employees.
- Risk: KVKK + breach.
- Detection via CASB + policy.
- Formal approval process.

## 11. Cloud Provider Selection Criteria

| Criterion | Weight |
|-----------|--------|
| KVKK Art. 12 + contract suitability | Critical |
| ISO/IEC 27001, 27017, 27018 | High |
| Türkiye/EU region | High |
| Standard Contract ready to sign | High |
| CMK / HYOK support | Medium-High |
| Audit log + SIEM integration | High |
| 24-hour breach notification clause | High |
| Transparency report | Medium |
| Insurance coverage | Medium |
| Cost | Medium |

## 12. Cloud Migration Process

```
1. Data classification (general/special/critical)
2. Provider selection (criteria above)
3. DPIA (for critical data)
4. Contract + DPA + Standard Contract signature
5. Standard Contract notification to Authority (5 business days)
6. Test environment + security configuration
7. Phased migration (canary)
8. Production go-live
9. Continuous monitoring + annual audit
```

## 13. Common Mistakes

| Mistake | Correct approach |
|---------|------------------|
| Standard Contract signed but not notified to Authority | Mandatory within 5 business days |
| No region selection | Prefer Türkiye / EU |
| Customer-managed key not used | Activate CMK |
| MFA not active | Mandatory on all cloud accounts |
| Public S3 bucket | CSPM + audit |
| All users with default IAM rights | Least privilege |
| Audit log disabled | Active on all providers |
| No exit plan | Reduce vendor lock-in |
| No internal cloud policy | Cloud usage policy required |
| No Shadow IT inventory | CASB + approval process |
| TIA not performed | Mandatory before cross-border transfer |

## 14. KPIs

| KPI | Target |
|-----|--------|
| KVKK DPA signed with cloud providers | 100% |
| Standard Contract notification SLA | < 5 business days |
| MFA coverage (cloud) | 100% |
| CMK active (critical data) | 100% |
| Audit log collection | 100% |
| Region compliance (critical data) | Türkiye/EU 100% |
| CSPM finding closure | < 30 days |
| TIA completion | 100% on cross-border transfer |
| Annual cloud audit | 100% |

## 15. Linked Sections

- `05-teknik-tedbirler/` - Cloud security controls.
- `07-aktarim/` - Cross-border transfer law.
- `08-ihlal-yonetimi/` - Cloud-provider breach response.

## 16. Version History

| Version | Date | Change | Approval |
|---------|------|--------|----------|
| 1.0 | 2026-05-08 | First publication | KVKK Committee + CTO |

---

## Türkçe

# Bulut Hizmetleri Yönetimi

## 1. Amaç

SaaS, PaaS, IaaS hizmetlerinin KVKK uyumlu seçimi, sözleşmelendirilmesi, uygulanması ve denetlenmesi. Bulut, şirketimizin kişisel veri işleme yüzeyinin **en geniş** ve KVKK risk **en yüksek** alanlarından biridir.

## 2. Bulut Modelleri ve Sorumluluk Paylaşımı

### 2.1. Hizmet Tipleri

| Tip | Sağlayıcı Sorumluluğu | Müşteri Sorumluluğu |
|-----|----------------------|---------------------|
| **IaaS** (AWS EC2, Azure VM, GCP Compute) | Fiziksel altyapı, hipervizör | OS, uygulama, veri, kullanıcı |
| **PaaS** (Azure App Service, AWS Lambda, GCP Cloud Run) | Altyapı + runtime | Uygulama + veri |
| **SaaS** (Microsoft 365, Salesforce, HubSpot) | Tam yığın | Veri + erişim yönetimi |

### 2.2. Shared Responsibility Model

- **Cloud OF the cloud** — sağlayıcının altyapı güvenliği.
- **Cloud IN the cloud** — müşterinin veri ve uygulama güvenliği.
- KVKK açısından: Müşteri (Şirketimiz) **veri sorumlusu** kalır; sağlayıcı genelde **veri işleyen** sıfatındadır.

### 2.3. Veri Sorumlusu vs İşleyen Belirleme

| Senaryo | Sağlayıcı Sıfatı |
|---------|------------------|
| AWS S3'te müşteri verisi | İşleyen (Şirket sorumluluğu) |
| Salesforce CRM kullanım | İşleyen |
| Mailchimp e-posta gönderimi | İşleyen |
| Microsoft 365 e-posta sunucusu | İşleyen (genelde) |
| LinkedIn pazarlama platformu | Karma — bazı durumlarda LinkedIn de sorumlu |
| Google Workspace | İşleyen |
| OpenAI ChatGPT (kurumsal API) | İşleyen (OpenAI sözleşmeli) |

> Sözleşmesel kontrol pay belirler — DPA detayları kritik.

## 3. Veri Yerleşimi ve Region Seçimi

### 3.1. Türkiye Region Tercih Sıralaması

1. **Türkiye'de yerleşik bulut sağlayıcı / region** (Türk Telekom Bulut, Turkcell Bulut, Akamai Linode İstanbul, AWS Türkiye Yerel Bölgesi, Azure Türkiye region — mevcut planlar).
2. **AB region** — yeterlilik kararı (Kurul yayımladığında) avantaj.
3. **ABD / Asya** — Standart Sözleşme + ek tedbirler.

### 3.2. Veri İkamet Klozu (Data Residency)

Sözleşmede:
- "Veri **Türkiye / AB** sınırları içinde işlenecektir."
- "Müşteri (Şirket) onayı olmadan başka region'a taşınmayacaktır."
- "Yedek ve disaster recovery tesisleri de aynı region kapsamında."

### 3.3. Pseudo-localization Sorunu

Sağlayıcı "Türkiye region" kursa bile:
- Yönetim düzlemi (control plane) genelde merkezi.
- Destek personeli yurt dışında erişebilir.
- Loglar merkezi toplanabilir.

> Region seçimi sadece veri **at-rest** kontrolüdür. Erişim, log, destek için ek garantiler gerekir.

## 4. Yurt Dışı Aktarım Analizi

### 4.1. KVKK m.9 (Güncel Hali — 2024)

KVKK m.9 değişikliği ile yurt dışı aktarım rejimi:
- **Yeterlilik kararı** olan ülkeye serbest aktarım.
- **Standart Sözleşme** (Kurul tarafından yayımlanan).
- **Bağlayıcı şirket kuralları** (BCR — onay süreci).
- **Açık rıza** (sınırlı, son çare).
- **Geçici / sınırlı durumlar** (KVKK m.9/6).

### 4.2. Standart Sözleşme

KVKK Kurulu **Standart Sözleşme** modüllerini yayımlamıştır (2024). Modül tipleri:
1. Veri sorumlusu → Veri sorumlusu (yurt dışı).
2. Veri sorumlusu → Veri işleyen (yurt dışı).
3. Veri işleyen → Alt-işleyen (yurt dışı).
4. Veri işleyen → Veri sorumlusu (yurt dışı).

> Sözleşme imzalanır + **Kurul'a 5 iş günü içinde bildirilir**. Bildirim yapılmazsa sözleşme geçerli ama Kurul yaptırım sebebi.

### 4.3. Transfer Impact Assessment (TIA)

Yurt dışı aktarım öncesi yapılmalı:
- Hedef ülke veri koruma rejimi.
- Hükümet erişim talepleri (FISA, CLOUD Act, vb.).
- Sağlayıcı şeffaflık raporları.
- Ek tedbirler (E2E şifreleme, anahtar müşteride).
- Kalan risk + kabul.

### 4.4. CLOUD Act (ABD)

ABD'de yerleşik veya ABD bağlantılı sağlayıcılar (Amazon, Microsoft, Google, Apple, Oracle) ABD hükümeti talebiyle veriyi açıklamak zorunda **bulundukları ülkeye bağlı olmaksızın**. KVKK ile çatışır.

**Pratik:**
- ABD sağlayıcısı kullanılıyorsa kritik veri için ek tedbir.
- Müşteri yönetimli anahtar (CMK) — ABD sağlayıcı şifrelenmiş veriyi göremez.
- Hold Your Own Key (HYOK) — anahtar Şirket altyapısında.

### 4.5. FISA 702 (ABD)

ABD istihbaratının yabancı kişiler hakkında ABD sağlayıcılarından veri alabilmesi. Schrems II kararı (AB Adalet Divanı) bu nedenle Privacy Shield'i iptal etti. KVKK için benzer endişeler.

## 5. DPA (Data Processing Agreement) — Bulut Sağlayıcı

### 5.1. Asgari Klozlar (KVKK m.12 + Kurul beklentisi)

1. Veri kategorisi, amaç, süre.
2. Sağlayıcı sadece **müşteri talimatlarıyla** işler.
3. Gizlilik (NDA + sağlayıcı çalışan sır).
4. Teknik ve idari tedbirler (ISO 27001 vb.).
5. Alt-işleyen onay süreci.
6. İhlal bildirim 24 saat (sözleşmesel sıkı).
7. İlgili kişi taleplerinde destek.
8. Audit hakkı + raporlama.
9. Sözleşme sonu veri imha + sertifika.
10. Yurt dışı aktarım kuralları.
11. Sigorta + sorumluluk sınırı.
12. Uyuşmazlık çözüm (Türk hukuku tercih).

### 5.2. Standart Bulut Sağlayıcı DPA Şablonları

| Sağlayıcı | DPA Linki |
|-----------|-----------|
| AWS | aws.amazon.com/compliance/data-protection/ |
| Microsoft | microsoft.com/en-us/trust-center/privacy/gdpr-overview |
| Google | cloud.google.com/terms/data-processing-addendum |
| Salesforce | salesforce.com/company/legal/agreements/ |
| HubSpot | legal.hubspot.com/dpa |

> Standart DPA'lar GDPR odaklıdır. KVKK için ek anlaşma (addendum) gerekebilir.

## 6. Anahtar Yönetimi

### 6.1. Sağlayıcı Yönetimli (Default)

- AWS KMS, Azure Key Vault, GCP KMS standart.
- Sağlayıcı anahtarı görür ve kullanır.
- KVKK riski: anahtar sağlayıcıdaysa "şifreli depolama" zayıflar (sağlayıcı erişebilir).

### 6.2. Müşteri Yönetimli Anahtar (CMK / BYOK)

- Anahtar müşteri tarafından oluşturulur.
- Sağlayıcıya sağlanır ama müşteri rotation ve kontrol.
- Daha iyi.

### 6.3. Hold Your Own Key (HYOK)

- Anahtar Şirket altyapısında (HSM).
- Sağlayıcı her şifre çözme için Şirkete başvurur.
- En yüksek koruma; performans maliyeti.
- Çok hassas veri için (örn. sağlık, finans).

### 6.4. Confidential Computing

- TEE (Trusted Execution Environment), Intel SGX, AMD SEV.
- Bellek seviyesinde şifreleme.
- Hipervizör/sağlayıcı bile veriye erişemez.
- Yeni teknoloji — değerlendirilebilir.

## 7. SaaS Özel Konular

### 7.1. Microsoft 365

- E-posta, SharePoint, Teams, OneDrive.
- Türkiye region (yakın gelecek), şu an AB.
- DPA + Customer Lockbox + Double Key Encryption opsiyonları.
- E5 lisans daha sıkı kontrol.

### 7.2. Google Workspace

- Gmail, Drive, Docs, Meet.
- Region: AB ya da ABD.
- DPA + Client-side encryption (CSE).

### 7.3. Salesforce

- CRM verisi.
- AB region (Hyperforce).
- Shield (audit + encryption) ek lisans.

### 7.4. HubSpot

- CRM + pazarlama otomasyonu.
- AB / Avustralya region seçilebilir.
- DPA + standart sözleşme.

## 8. Bulut Erişim Yönetimi

### 8.1. Identity (IAM)

- Federation (SAML / OIDC) ile kurumsal AD/Entra entegrasyonu.
- MFA zorunlu.
- Privileged access — JIT (Just-In-Time).
- IAM rol ayrılması (least privilege).

### 8.2. Audit ve Loglama

- Tüm bulut sağlayıcısı log'ları (CloudTrail, Azure Activity Log, GCP Audit Logs) merkezi SIEM'e.
- Konfigürasyon değişiklikleri izlenir.
- Anomali algılama.

### 8.3. Konfigürasyon Yönetimi

- IaC (Terraform, ARM, CloudFormation) ile.
- Public S3 bucket, açık port denetimi.
- CSPM (Cloud Security Posture Management) — Wiz, Prisma, Defender for Cloud.

## 9. Veri Taşınabilirliği ve Çıkış Stratejisi

### 9.1. Vendor Lock-in Riski

- Proprietary format (Salesforce, HubSpot).
- Kapsamı, geçiş zamanı.
- Sözleşme sonu veri export hakkı.

### 9.2. Çıkış Planı

- Sözleşmede çıkış maddesi: standart format export, 90 gün veri erişim.
- Düzenli backup (kendi altyapımızda).
- Alternatif sağlayıcı sürekli değerlendirme.

### 9.3. Veri Silme Sertifikası

- Sözleşme sonu sağlayıcı veriyi silmeli + sertifika.
- Yedeklerden silme süresi (60-90 gün makul).

## 10. CASB ve Shadow IT

### 10.1. CASB (Cloud Access Security Broker)

- Microsoft Defender for Cloud Apps, Netskope, Zscaler.
- Bulut kullanım envanteri.
- DLP entegrasyonu.
- Anomali algılama.

### 10.2. Shadow IT

- Çalışanların onaysız SaaS kullanımı.
- Risk: KVKK + ihlal.
- CASB ile tespit + politika.
- Onay süreci formalize.

## 11. Bulut Sağlayıcı Seçim Kriterleri

| Kriter | Ağırlık |
|--------|---------|
| KVKK m.12 + sözleşme uygunluğu | Kritik |
| ISO/IEC 27001, 27017, 27018 | Yüksek |
| Türkiye/AB region | Yüksek |
| Standart Sözleşme imzaya hazır | Yüksek |
| CMK / HYOK desteği | Orta-Yüksek |
| Audit log + SIEM entegrasyonu | Yüksek |
| İhlal bildirim 24 saat klozu | Yüksek |
| Şeffaflık raporu | Orta |
| Sigorta kapsamı | Orta |
| Maliyet | Orta |

## 12. Bulut Migrasyon Süreci

```
1. Veri sınıflandırma (genel/özel/kritik)
2. Sağlayıcı seçimi (yukarıdaki kriterler)
3. DPIA (kritik veri için)
4. Sözleşme + DPA + Standart Sözleşme imza
5. Kurul'a Standart Sözleşme bildirim (5 iş günü)
6. Test ortamı + güvenlik konfigürasyonu
7. Aşamalı geçiş (canary)
8. Üretim canlı
9. Sürekli izleme + yıllık denetim
```

## 13. Tipik Hatalar

| Hata | Doğru Yaklaşım |
|------|----------------|
| Standart Sözleşme imzalı, Kurul'a bildirilmemiş | 5 iş günü zorunlu |
| Region seçimi yapılmamış | Türkiye / AB tercih |
| Müşteri yönetimli anahtar kullanılmıyor | CMK aktif |
| MFA aktif değil | Tüm bulut hesapları zorunlu |
| Public S3 bucket | CSPM + denetim |
| Default IAM yetkili tüm kullanıcı | Least privilege |
| Audit log devre dışı | Tüm sağlayıcılarda etkin |
| Çıkış planı yok | Vendor lock-in azaltma |
| Şirket içi politika yok | Bulut kullanım politikası şart |
| Shadow IT envanteri yok | CASB + onay süreci |
| TIA yapılmamış | Yurt dışı aktarım öncesi zorunlu |

## 14. KPI'lar

| KPI | Hedef |
|-----|-------|
| Bulut sağlayıcılarda KVKK DPA imzalı | %100 |
| Standart Sözleşme bildirim SLA | < 5 iş günü |
| MFA kapsam (bulut) | %100 |
| CMK aktif (kritik veri) | %100 |
| Audit log toplama | %100 |
| Region uyum (kritik veri) | Türkiye/AB %100 |
| CSPM bulgusu kapanma | < 30 gün |
| TIA tamamlanma | %100 yurt dışı aktarım |
| Yıllık bulut denetim | %100 |

## 15. Bağlantılı Bölümler

- `05-teknik-tedbirler/` — Bulut güvenlik kontrolleri.
- `07-aktarim/` — Yurt dışı aktarım hukuku.
- `08-ihlal-yonetimi/` — Bulut sağlayıcı ihlali müdahale.

## 16. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi + CTO |
