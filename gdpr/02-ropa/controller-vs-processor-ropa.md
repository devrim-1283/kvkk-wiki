---
title: "Controller vs Processor ROPA — Two Registers, Distinct Content, Required Information Flow"
title_tr: "Veri Sorumlusu ve Veri İşleyen ROPA'sı — İki Sicil, Farklı İçerik, Zorunlu Bilgi Akışı"
section: "02-ropa"
language: ["en", "tr"]
status: "approved"
version: "2.0.0"
last_review: "2026-04-15"
next_review: "2026-10-15"
owner: "Data Protection Officer"
classification: "Internal"
related_articles: ["GDPR Art. 4(7)", "GDPR Art. 4(8)", "GDPR Art. 26", "GDPR Art. 28", "GDPR Art. 30(1)", "GDPR Art. 30(2)", "GDPR Art. 32"]
related_guidelines: ["EDPB Guidelines 07/2020 on the concepts of controller and processor", "EDPB Position Paper April 2018"]
tags: ["ropa", "controller", "processor", "joint-controller", "subprocessor"]
---

## English

### 1. Why Two Registers Are Required

Article 30 imposes distinct documentation duties on **controllers** (Art. 30(1)) and **processors** (Art. 30(2)). The two registers answer different questions:

- The **controller ROPA** answers: *Why are we processing this data, and what choices have we made?*
- The **processor ROPA** answers: *What are we doing with someone else's data on their instructions, and what controls did we apply?*

A single legal entity may be a controller for some data flows and a processor for others. Each role requires its own register. Confusion between the two is one of the most common Article 30 audit findings.

### 2. Conceptual Distinction

#### 2.1 Definitions (Art. 4)

- **Controller** (Art. 4(7)): the natural or legal person which, alone or jointly with others, determines the **purposes** and **means** of the processing.
- **Processor** (Art. 4(8)): the natural or legal person which processes personal data **on behalf of** the controller.

The controller decides the *why* and the high-level *how*. The processor executes within those parameters.

#### 2.2 Joint Controllers (Art. 26)

When two or more parties jointly determine the purposes and means, they are joint controllers. Joint controllers must agree, in a transparent manner, their respective responsibilities under the GDPR (Art. 26(1)). The essence of this arrangement must be made available to data subjects (Art. 26(2)).

In ROPA terms:

- Each joint controller maintains its own controller ROPA, but Column 4 lists the joint controllers and references the joint-controllership agreement.
- Where the same processing is jointly carried out, the entries should be aligned across joint controllers' registers.

#### 2.3 Sub-processors

A processor may engage sub-processors only with the controller's prior specific or general written authorisation (Art. 28(2)). Where the authorisation is general, the processor must inform the controller of any intended changes and give the controller the chance to object (Art. 28(2) second sentence).

Each processor's ROPA must list its sub-processors (with country of establishment), and the controller's ROPA should mirror that information through the vendor list (Column 19 of the template).

### 3. Content Differences

| Field | Controller ROPA | Processor ROPA |
|-------|-----------------|----------------|
| Controller / processor identification | Self (controller) + joint controllers, representative, DPO | Self (processor) + each controller served + their representative + their DPO |
| Purposes | Mandatory | Not in processor's record (purposes are the controller's) |
| Lawful basis | Mandatory (best practice) | Not applicable (controller's responsibility) |
| Categories of data subjects | Mandatory | Best practice (often inherited from each controller) |
| Categories of personal data | Mandatory | Best practice (often inherited from each controller) |
| **Categories of processing** | Useful but not Art. 30(1) field | **Mandatory (Art. 30(2)(b))** |
| Categories of recipients | Mandatory | Generally not applicable (processor cannot disclose without controller instructions) |
| Sub-processors | Best practice (mirror) | Best practice; required by DPA |
| Third-country transfers and safeguards | Mandatory | Mandatory |
| Retention period | Mandatory | Often mirror of controller's; processor's own retention only for what processor genuinely controls |
| TOMs | Mandatory | Mandatory |
| DPIA reference | Best practice | Not applicable (DPIA is the controller's duty) |
| DPA reference | Best practice | Mandatory in practice (the DPA defines the relationship) |

### 4. Processor ROPA — Detailed Field Notes

#### 4.1 Identification

The processor ROPA must list, for each controller served:

1. The controller's legal name and address.
2. The controller's representative (Art. 27) where applicable.
3. The controller's DPO contact, where applicable.

For organisations serving many controllers (e.g., SaaS platforms with thousands of customers), this is typically maintained as a structured list (CSV or database) with one row per controller. The aggregate view counts as the ROPA.

#### 4.2 Categories of Processing

Examples:

- "Hosting and storage of customer relationship management data."
- "Email delivery and bounce processing for marketing communications."
- "Payroll calculation and statutory filing."
- "Cloud-based file storage and synchronisation."
- "Endpoint device management and patching."

Each "category of processing" is broader than a single technical operation; it describes the *service* provided.

#### 4.3 Transfers

Processor must document:

- The destination country.
- The transfer mechanism (adequacy decision, SCCs, BCRs, derogation).
- The safeguards applied.
- Any sub-processor in a third country.

#### 4.4 TOMs

The processor's TOM description must demonstrate compliance with Article 32. This typically includes:

- Encryption (in transit, at rest).
- Pseudonymisation where applicable.
- Confidentiality, integrity, availability, and resilience measures.
- Restoration capability.
- Regular testing of effectiveness.
- Access governance.
- Personnel training.
- Vendor governance for sub-processors.

### 5. Information Flow Between Controller and Processor

The two registers are not isolated. Article 28 and Article 30 together require a managed information flow:

#### 5.1 At Onboarding

The DPA must commit the processor to:

- Process only on documented instructions (Art. 28(3)(a)).
- Ensure persons authorised to process are bound by confidentiality (Art. 28(3)(b)).
- Take Article 32 measures (Art. 28(3)(c)).
- Engage sub-processors only with authorisation (Art. 28(3)(d)).
- Assist the controller with rights requests (Art. 28(3)(e)).
- Assist the controller with security, breach, DPIA obligations (Art. 28(3)(f)).
- Delete or return data at end of services (Art. 28(3)(g)).
- Make available all information necessary to demonstrate compliance and allow audits (Art. 28(3)(h)).

The processor must give the controller the information required to complete the controller's ROPA, including:

- Country of storage.
- Sub-processor list.
- TOM summary.
- Transfer mechanisms.
- Retention defaults.
- Breach response procedures.

#### 5.2 During the Relationship

- Processor notifies controller of any new sub-processor in time for the controller to object.
- Processor notifies controller of any change in storage location, transfer route, or material change to TOMs.
- Processor notifies controller of any breach affecting the controller's data without undue delay (Art. 33(2)).
- Controller updates its ROPA when notified.

#### 5.3 At Termination

- Processor returns or deletes the data per controller instructions (Art. 28(3)(g)).
- Processor updates its ROPA to mark the entry as decommissioned.
- Controller updates its ROPA to mark the relationship ended and to point to alternative processing arrangements.

### 6. Common Confusion: Cloud Provider Roles

Cloud providers often play layered roles:

- **Infrastructure-as-a-Service (IaaS)**: typically processor for content stored by customers; controller for account, billing, and operational telemetry of the customer.
- **Software-as-a-Service (SaaS)**: typically processor for customer business data; controller for product analytics, account management.
- **Platform-as-a-Service (PaaS)**: typically processor for application data; controller for platform telemetry.

The exact split depends on the contract and the actual decisions made. Read the DPA carefully.

### 7. Sample Processor ROPA Entry

| Field | Value |
|-------|-------|
| Entry ID | PROC-ROPA-007 |
| Activity name | SaaS hosting of CRM application for European customers |
| Processor | Acme Cloud Services Ireland Ltd, Dublin, IE |
| Processor representative | N/A |
| Processor DPO | dpo@acmecloud.eu |
| Controllers served | Approx. 1,200 EU customers; aggregated list maintained in customer-master.csv |
| Categories of processing on behalf of each controller | Hosting; database operations; backup; restore; routine support; security monitoring |
| Categories of data subjects (typical) | Customers, prospects, end users of customer's CRM (variable per controller) |
| Categories of personal data (typical) | Identity, contact, business interactions; potentially special-category if controller chooses to store it (controlled by controller's contract type) |
| Sub-processors | Hyperscaler (AWS Ireland) for compute and storage; Datadog Ireland for monitoring; Twilio Ireland for SMS notifications when enabled |
| Third-country transfers | Yes — emergency support engineers in US under SCCs Module 3 with TIA on file; Datadog metadata replicated to US under SCCs Module 2; Twilio US fallback for SMS reachability under SCCs Module 2 |
| Retention period | Per controller instruction; default 30 days post-termination for full deletion; backups overwritten within 90 days |
| TOMs | ISO 27001:2022 certified; SOC 2 Type II; encryption at rest (AES-256) and in transit (TLS 1.3); MFA mandatory; tenant isolation; logging; quarterly access reviews; annual penetration testing |
| DPIA reference | Internal DPIA-CLOUD-2024-03 (operational, not customer-facing) |
| Storage country | Ireland (primary), Frankfurt (DR) |
| DPA reference | Standard DPA v3.2 (executed with each customer) |
| Last reviewed | 2026-04-10 |
| Next review due | 2026-10-10 |
| Notes | Q1 2026: Datadog moved metadata processing region to EU-only by default; US transfer is now opt-in only. |

### 8. Audit Readiness Checklist

A dual-register organisation passes audit when:

- [ ] Controller ROPA and processor ROPA are clearly labelled and separated.
- [ ] No entry is on both registers for the same data flow.
- [ ] Joint controllers are documented in both controllers' registers with the agreement attached.
- [ ] Every processor relationship has a corresponding entry in both the controller's and the processor's register.
- [ ] Sub-processor lists in the processor register match the vendor list in the controller register.
- [ ] Transfer mechanisms are consistent across the two registers for the same data flow.
- [ ] DPAs are referenced from both sides.

---

## Türkçe

### 1. İki Sicil Neden Gereklidir

Madde 30, **veri sorumlularına** (Madde 30(1)) ve **veri işleyenlere** (Madde 30(2)) farklı belgeleme görevleri yükler. İki sicil farklı sorulara yanıt verir:

- **Veri sorumlusu ROPA'sı**: *Bu veriyi neden işliyoruz ve hangi seçimleri yaptık?*
- **Veri işleyen ROPA'sı**: *Başkasının verisiyle, onun talimatları doğrultusunda ne yapıyoruz ve hangi kontrolleri uyguladık?*

Tek bir tüzel kişi bazı veri akışları için veri sorumlusu, diğerleri için veri işleyen olabilir. Her rol kendi sicilini gerektirir. İkisi arasındaki karışıklık en yaygın Madde 30 denetim bulgularındandır.

### 2. Kavramsal Ayrım

#### 2.1 Tanımlar (Madde 4)

- **Veri sorumlusu** (Madde 4(7)): tek başına veya başkalarıyla birlikte işlemenin **amaçlarını** ve **araçlarını** belirleyen gerçek veya tüzel kişi.
- **Veri işleyen** (Madde 4(8)): kişisel verileri veri sorumlusu **adına** işleyen gerçek veya tüzel kişi.

Veri sorumlusu *neden*'i ve üst düzey *nasıl*'ı belirler. Veri işleyen bu parametreler içinde uygulamayı yapar.

#### 2.2 Ortak Veri Sorumluları (Madde 26)

İki veya daha fazla taraf amaçları ve araçları birlikte belirlediğinde, bunlar ortak veri sorumlularıdır. Ortak veri sorumluları, GDPR kapsamındaki sorumluluklarını şeffaf bir şekilde belirleyen bir anlaşma yapmalıdır (Madde 26(1)). Bu düzenlemenin özü ilgili kişilere sunulmalıdır (Madde 26(2)).

ROPA açısından:

- Her ortak veri sorumlusu kendi veri sorumlusu ROPA'sını tutar, ancak Sütun 4 ortak veri sorumlularını listeler ve ortak veri sorumluluğu sözleşmesine atıfta bulunur.
- Aynı işleme birlikte yürütüldüğünde, girişler ortak veri sorumlularının sicilleri arasında uyumlulaştırılmalıdır.

#### 2.3 Alt İşleyenler

Bir veri işleyen, alt işleyenleri yalnızca veri sorumlusunun önceden belirli veya genel yazılı izniyle çalıştırabilir (Madde 28(2)). İzin genel ise, veri işleyen herhangi bir değişiklik niyetini veri sorumlusuna bildirmeli ve veri sorumlusuna itiraz fırsatı vermelidir (Madde 28(2) ikinci cümle).

Her veri işleyenin ROPA'sı alt işleyenlerini (kuruluş ülkesiyle birlikte) listelemelidir ve veri sorumlusunun ROPA'sı bu bilgiyi tedarikçi listesi (şablonun Sütun 19'u) üzerinden yansıtmalıdır.

### 3. İçerik Farkları

| Alan | Veri Sorumlusu ROPA'sı | Veri İşleyen ROPA'sı |
|------|--------------------------|------------------------|
| Veri sorumlusu / işleyen kimliği | Kendi (sorumlu) + ortak sorumlular, temsilci, DPO | Kendi (işleyen) + hizmet verilen her veri sorumlusu + temsilcisi + DPO'su |
| Amaçlar | Zorunlu | İşleyenin kaydında değil (amaçlar veri sorumlusunun) |
| Hukuki sebep | Zorunlu (en iyi uygulama) | Uygulanmaz (veri sorumlusunun sorumluluğu) |
| İlgili kişi kategorileri | Zorunlu | En iyi uygulama (genellikle her veri sorumlusundan devralınır) |
| Kişisel veri kategorileri | Zorunlu | En iyi uygulama (genellikle her veri sorumlusundan devralınır) |
| **İşleme kategorileri** | Yararlı ama Madde 30(1) alanı değil | **Zorunlu (Madde 30(2)(b))** |
| Alıcı kategorileri | Zorunlu | Genellikle uygulanmaz (işleyen, veri sorumlusunun talimatı olmadan ifşa edemez) |
| Alt işleyenler | En iyi uygulama (yansıtma) | En iyi uygulama; DPA tarafından gerekli |
| Üçüncü ülke aktarımları ve güvenceler | Zorunlu | Zorunlu |
| Saklama süresi | Zorunlu | Genellikle veri sorumlusunun aynası; işleyenin kendi saklaması yalnızca gerçekten kontrol ettiği için |
| TOM'lar | Zorunlu | Zorunlu |
| DPIA referansı | En iyi uygulama | Uygulanmaz (DPIA veri sorumlusunun görevidir) |
| DPA referansı | En iyi uygulama | Pratikte zorunlu (DPA ilişkiyi tanımlar) |

### 4. Veri İşleyen ROPA'sı — Ayrıntılı Alan Notları

#### 4.1 Tanımlama

Veri işleyen ROPA'sı, hizmet verilen her veri sorumlusu için şunları listelemelidir:

1. Veri sorumlusunun yasal adı ve adresi.
2. Uygulanabilirse veri sorumlusunun temsilcisi (Madde 27).
3. Uygulanabilirse veri sorumlusunun DPO iletişimi.

Birçok veri sorumlusuna hizmet veren kuruluşlar için (örneğin binlerce müşterisi olan SaaS platformları), bu genellikle veri sorumlusu başına bir satırlık yapılı bir liste (CSV veya veritabanı) olarak tutulur. Toplam görünüm ROPA olarak sayılır.

#### 4.2 İşleme Kategorileri

Örnekler:

- "Müşteri ilişkileri yönetimi verilerinin barındırma ve depolaması."
- "Pazarlama iletişimleri için e-posta gönderimi ve geri dönüş işleme."
- "Bordro hesaplama ve yasal bildirim."
- "Bulut tabanlı dosya depolama ve senkronizasyon."
- "Uç nokta cihaz yönetimi ve yamalama."

Her "işleme kategorisi" tek bir teknik operasyondan daha geniştir; sağlanan *hizmeti* tanımlar.

#### 4.3 Aktarımlar

Veri işleyen şunları belgelemelidir:

- Hedef ülke.
- Aktarım mekanizması (yeterlilik kararı, SCC, BCR, muafiyet).
- Uygulanan güvenceler.
- Üçüncü bir ülkedeki herhangi bir alt işleyen.

#### 4.4 TOM'lar

Veri işleyenin TOM açıklaması, Madde 32 ile uyumluluğu göstermelidir. Bu genellikle şunları içerir:

- Şifreleme (aktarımda, statikte).
- Uygulanabilir yerlerde takma ad verme.
- Gizlilik, bütünlük, kullanılabilirlik ve dayanıklılık önlemleri.
- Geri yükleme yeteneği.
- Etkinliğin düzenli testi.
- Erişim yönetimi.
- Personel eğitimi.
- Alt işleyenler için tedarikçi yönetimi.

### 5. Veri Sorumlusu ve İşleyen Arasında Bilgi Akışı

İki sicil izole değildir. Madde 28 ve Madde 30 birlikte yönetilen bir bilgi akışı gerektirir:

#### 5.1 İlişki Kurarken

DPA, veri işleyeni şunlara taahhüt ettirmelidir:

- Yalnızca belgelenmiş talimatlar üzerine işleme (Madde 28(3)(a)).
- İşleme yetkili kişilerin gizlilikle bağlı olmasını sağlama (Madde 28(3)(b)).
- Madde 32 önlemlerini alma (Madde 28(3)(c)).
- Alt işleyenleri yalnızca izinle çalıştırma (Madde 28(3)(d)).
- Veri sorumlusuna haklar talepleri konusunda yardımcı olma (Madde 28(3)(e)).
- Veri sorumlusuna güvenlik, ihlal, DPIA yükümlülükleri konusunda yardımcı olma (Madde 28(3)(f)).
- Hizmet sonunda veriyi silme veya iade etme (Madde 28(3)(g)).
- Uyumluluğu göstermek ve denetimlere izin vermek için gerekli tüm bilgileri sağlama (Madde 28(3)(h)).

Veri işleyen, veri sorumlusunun ROPA'sını tamamlamak için gereken bilgileri vermelidir; bu bilgiler şunları içerir:

- Depolama ülkesi.
- Alt işleyen listesi.
- TOM özeti.
- Aktarım mekanizmaları.
- Saklama varsayılanları.
- İhlal yanıt prosedürleri.

#### 5.2 İlişki Süresince

- İşleyen, veri sorumlusunun itiraz edebilmesi için herhangi bir yeni alt işleyeni zamanında bildirir.
- İşleyen, depolama konumu, aktarım rotası veya TOM'larda önemli değişiklikleri bildirir.
- İşleyen, veri sorumlusunun verisini etkileyen ihlali gecikmeksizin bildirir (Madde 33(2)).
- Veri sorumlusu, bilgilendirildiğinde ROPA'sını günceller.

#### 5.3 İlişki Sonlandığında

- İşleyen, veri sorumlusu talimatları doğrultusunda veriyi iade eder veya siler (Madde 28(3)(g)).
- İşleyen, ROPA'sını girişi hizmet dışı olarak işaretlemek üzere günceller.
- Veri sorumlusu, ilişkinin sona erdiğini ve alternatif işleme düzenlemelerine işaret etmek üzere ROPA'sını günceller.

### 6. Yaygın Karışıklık: Bulut Sağlayıcı Rolleri

Bulut sağlayıcılar genellikle katmanlı roller oynar:

- **Infrastructure-as-a-Service (IaaS)**: müşteriler tarafından depolanan içerik için genellikle veri işleyen; müşterinin hesap, faturalama ve operasyonel telemetri verisi için veri sorumlusu.
- **Software-as-a-Service (SaaS)**: müşteri iş verisi için genellikle veri işleyen; ürün analitiği, hesap yönetimi için veri sorumlusu.
- **Platform-as-a-Service (PaaS)**: uygulama verisi için genellikle veri işleyen; platform telemetri için veri sorumlusu.

Tam dağılım sözleşmeye ve fiilen alınan kararlara bağlıdır. DPA'yı dikkatlice okuyun.

### 7. Örnek Veri İşleyen ROPA Girişi

| Alan | Değer |
|------|-------|
| Giriş Kimliği | PROC-ROPA-007 |
| Faaliyet adı | Avrupa müşterileri için CRM uygulamasının SaaS barındırması |
| Veri işleyen | Acme Cloud Services Ireland Ltd, Dublin, IE |
| Temsilci | Yok |
| DPO | dpo@acmecloud.eu |
| Hizmet verilen veri sorumluları | Yaklaşık 1.200 AB müşterisi; toplu liste customer-master.csv'de |
| Her veri sorumlusu adına işleme kategorileri | Barındırma; veritabanı işlemleri; yedekleme; geri yükleme; rutin destek; güvenlik izleme |
| Tipik ilgili kişi kategorileri | Müşteriler, potansiyel müşteriler, müşterinin CRM'inin son kullanıcıları (her veri sorumlusu için değişken) |
| Tipik kişisel veri kategorileri | Kimlik, iletişim, iş etkileşimleri; veri sorumlusunun depolamayı seçmesi durumunda potansiyel olarak özel kategori |
| Alt işleyenler | Hyperscaler (AWS Ireland) işlem ve depolama için; Datadog Ireland izleme için; etkin olduğunda SMS bildirimleri için Twilio Ireland |
| Üçüncü ülke aktarımları | Evet — ABD'deki acil destek mühendisleri SCC Modül 3 altında dosyada TIA ile; Datadog meta verisi SCC Modül 2 altında ABD'ye replike edildi; SMS erişilebilirliği için Twilio ABD yedeği SCC Modül 2 altında |
| Saklama süresi | Veri sorumlusu talimatına göre; varsayılan, sonlandırma sonrası 30 gün tam silme; yedekler 90 gün içinde üzerine yazılır |
| TOM'lar | ISO 27001:2022 sertifikalı; SOC 2 Tip II; statik (AES-256) ve aktarımdaki (TLS 1.3) şifreleme; zorunlu MFA; tenant izolasyonu; loglama; üç aylık erişim incelemeleri; yıllık sızma testi |
| DPIA referansı | Dahili DPIA-CLOUD-2024-03 |
| Depolama ülkesi | İrlanda (birincil), Frankfurt (DR) |
| DPA referansı | Standart DPA v3.2 (her müşteri ile imzalanmış) |
| Son inceleme | 2026-04-10 |
| Sonraki inceleme | 2026-10-10 |
| Notlar | 2026-Ç1: Datadog meta veri işleme bölgesini varsayılan olarak yalnızca AB'ye taşıdı; ABD aktarımı artık yalnızca isteğe bağlı. |

### 8. Denetime Hazırlık Kontrol Listesi

İkili sicilli bir kuruluş şu durumlarda denetimi geçer:

- [ ] Veri sorumlusu ROPA'sı ve veri işleyen ROPA'sı açıkça etiketlenmiş ve ayrılmıştır.
- [ ] Aynı veri akışı için her iki sicilde de giriş yoktur.
- [ ] Ortak veri sorumluları her iki sorumlunun da sicilinde, anlaşma ekli olarak belgelenmiştir.
- [ ] Her veri işleyen ilişkisinin hem veri sorumlusunun hem de veri işleyenin sicilinde karşılık gelen bir girişi vardır.
- [ ] Veri işleyen sicilindeki alt işleyen listeleri, veri sorumlusu sicilindeki tedarikçi listesiyle eşleşir.
- [ ] Aynı veri akışı için aktarım mekanizmaları iki sicil arasında tutarlıdır.
- [ ] DPA'lar her iki taraftan da referans verilmiştir.
