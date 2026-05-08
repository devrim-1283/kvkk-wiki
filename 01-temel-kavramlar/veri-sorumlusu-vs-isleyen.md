---
Doküman / Document: Veri Sorumlusu ve Veri İşleyen Ayrımı / Distinction Between Data Controller and Data Processor
Bölüm / Section: 01-temel-kavramlar
Sahip / Owner: KVKK Sorumlusu / KVKK Officer
Onaylayan / Approved by: Yönetim Kurulu / Genel Müdür / Board of Directors / CEO
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş (yeni iş ortaklığı, M&A) / Annual + triggered (new partnership, M&A)
İlgili Mevzuat / Legal Reference: 6698 sayılı KVKK m.3/1(ı) ve (ğ); m.12 (veri güvenliği); Kurum Yayını "Veri Sorumlusu ve Veri İşleyen" Haziran 2025 / KVKK Art. 3/1(ı) and (ğ); Art. 12 (data security); Authority publication "Data Controller and Data Processor" June 2025
---

## English

# Distinction Between Data Controller and Data Processor

## 1. Purpose

This document sets out the operational framework for clearly distinguishing the roles of **data controller** and **data processor** under KVKK, identifying the correct role in concrete partnership scenarios and ensuring full satisfaction of contractual obligations.

## 2. Legal Definitions

### 2.1 Data Controller (KVKK Art. 3/1(ı))
"The natural or legal person who determines the purposes and means of processing personal data, and who is responsible for the establishment and management of the data filing system."

### 2.2 Data Processor (KVKK Art. 3/1(ğ))
"The natural or legal person who processes personal data on behalf of the data controller based on the authority granted by the data controller."

### 2.3 Authority Opinion (June 2025 Publication)
- The data controller is the party that answers the questions **"why"** and **"how"** in the processing of personal data.
- The data processor is the independent party processing personal data **on the instructions of the data controller** and **outside its organization**.

## 3. Distinction Criteria (Decision Test)

To determine the role of the parties in a processing activity, the question **"who decided?"** is asked for the following:

| Decision | Indicates Data Controller |
|----------|---------------------------|
| **Method of collecting personal data** | Decided by the controller |
| **Categories of data to be collected** | Decided by the controller |
| **Purpose of use** | Decided by the controller |
| **Whose data will be collected** | Decided by the controller |
| **Whether and with whom data will be shared** | Decided by the controller |
| **Retention periods** | Decided by the controller |

| Decision | Can Be Left to Processor |
|----------|--------------------------|
| Which IT systems will be used | Generally chosen by the processor |
| Technical details of storage method | Processor |
| Technical details of security measures | Processor (controller sets the minimum) |
| Technical method of transfer | Processor |
| Method of implementing retention period in the system | Processor |
| Erasure method (delete/destroy/anonymize) — technical | Processor |

**Critical:** The **strategic** dimension of "how" (which process, for which purpose) belongs to the controller; the **operational/technical** dimension is for the processor.

## 4. Dual Role Within the Same Legal Entity

A natural or legal person may simultaneously act as **both data controller and data processor**. This is a "context-dependent" classification:

### Example 1: Cloud Service Provider
- **For its own employee data** → data controller (recruitment, payroll, performance)
- **For data stored on behalf of customer companies** → data processor (under customer's instructions)

### Example 2: Call Center
- **Data of its own employees** → data controller
- **Customer calls made on behalf of the customer company** → data processor

### Example 3: Tax Advisor
- **Own office employees** → data controller
- **Processing the client's payroll** → generally data controller (as it has independent professional legal obligations)

### Example 4: Marketing Agency
- **Its own employees** → data controller
- **Processing campaign data for a customer company** → data processor (limited by instruction)
- **Conducting market research** → data controller (often, decisions are made by it)

## 5. Roles in a Group of Companies

Under KVKK, **each legal entity is a separate data controller**.

### 5.1 Important Principles
- ABC A.Ş. and XYZ Ltd. Şti. within a holding → two separate data controllers
- Sharing between group companies is not an "internal flow" but a **transfer** — KVKK Art. 8 (domestic) or Art. 9 (cross-border affiliated company) applies
- Shared services (HR, IT, finance shared services): the providing group company is either a controller or processor for the other; this must be clarified contractually
- "One privacy notice across the holding" → since each legal entity requires separate notification and VERBİS registration, sections distinguishing each company's identity must be present under the umbrella text

### 5.2 Decision Flow for Intra-Group Transfer
```
Intra-group sharing planned
    |
    +-- Does the recipient group company have its own decision-making authority?
    |   |
    |   +-- Yes → Transfer. Operation between two separate controllers.
    |   |          (Explicit consent OR Art. 8 processing condition; transfer purpose stated in privacy notice)
    |   |
    |   +-- No, processes only on instruction → Acts as a processor
    |               (Data processor contract required)
    |
    +-- Transfer to a foreign group company?
        |
        +-- Yes → KVKK Art. 9 (adequacy decision / appropriate safeguard / incidental)
```

## 6. Data Processor Contract — Minimum Provisions

Under KVKK Art. 12 and the data security obligation, a **written contract** between the data controller and the data processor is mandatory. At a minimum, the contract must contain the following provisions:

### 6.1 Subject and Term
- Subject and duration of the processing activity
- Categories of personal data and groups of data subjects
- Undertaking not to deviate from the determined purpose and scope

### 6.2 Adherence to Instructions
- The processor processes **only on the data controller's written instructions**
- Processing outside such instructions is prohibited

### 6.3 Confidentiality (KVKK Art. 12/4)
- Confidentiality obligation of the processor and persons working on its behalf
- This obligation continues indefinitely after the contract ends
- The processor obtains confidentiality undertakings from its personnel

### 6.4 Security Measures (KVKK Art. 12)
- Minimum technical and administrative safeguards to be applied by the processor
- Access management, log records, encryption, leakage prevention
- The processor's measures must be equivalent to those of the controller

### 6.5 Sub-Processors
- Sub-processors may not be used **without the controller's prior written consent**
- The list of approved sub-processors must form an appendix to the contract
- A written contract on the same conditions is required with the sub-processor
- The principal processor remains fully liable for any breach by the sub-processor

### 6.6 Cross-Border Transfer
- If transfers will be made abroad, to which countries
- Under which appropriate safeguard (BCR, standard contract, undertaking)
- Prior consent of the controller is required

### 6.7 Audit Rights
- The controller's right to audit whether the safeguards are implemented
- Coverage by independent third-party audits (ISO 27001, ISO 27701, SOC 2 Type II)
- Annual minimum sharing of audit reports

### 6.8 Breach Notification
- The processor notifies the controller within **24 hours** of becoming aware of a breach
- Notification content: incident summary, affected data categories, number of individuals, measures taken
- The processor provides full support for the controller's preparation of the 72-hour notification to the Authority

### 6.9 Data Subject Requests
- The processor's reasonable assistance obligation for applications made to the controller
- Forwarding of requests received directly to the processor to the controller
- Scope of the assistance obligation (provision, deletion, correction of data, etc.)

### 6.10 Return and Destruction
- Upon termination of the contract, the processor either:
  - **Returns** all data in its possession to the controller, or
  - **Destroys** them on the controller's instruction
- Maintains a destruction record
- Completes destruction within 30 days

### 6.11 Legal Obligations
- Undertaking of full compliance with KVKK and secondary legislation
- Obligation to adapt to regulatory changes
- Recourse provisions in the event of administrative fines

### 6.12 Insurance
- For high-risk processing, the processor maintains cyber insurance or professional liability insurance

## 7. "Contractual Role" vs "Actual Role"

An important misconception: the parties labeling themselves as "data processor" in the contract does not automatically grant them this status under KVKK. **The actual role arises from actual decision-making authority.**

For example: Even if a market research company is named "data processor" in the contract, if it determines questionnaire content, sample selection and data use decisions, it is a **data controller**.

## 8. Practical Scenarios (Türkiye Context)

### Scenario 1: SaaS CRM Provider
- **Customer company** (e-commerce platform) → Data controller
- **CRM SaaS provider** → Data processor
- **Required contract:** Data processing agreement (DPA), with KVKK Art. 12 requirements
- **Cross-border dimension:** If the SaaS provider is foreign → Art. 9 regime

### Scenario 2: Call Center Outsourcing
- **Bank** → Controller
- **Call center company** → Processor
- **Important:** Where the bank determines call center scripts and customer response policies — the outsourcer cannot deviate; has no interpretation authority

### Scenario 3: Payroll Service
- **Employer company** → Controller
- **Payroll service provider** → Processor (only if processing strictly on instructions)
- **Otherwise:** If the tax advisor acts under independent professional legal duties (anti-money-laundering reporting, etc.) → may also be an independent controller

### Scenario 4: Cloud Database (AWS RDS, Azure SQL, GCP Cloud SQL)
- **Customer company** → Controller
- **Cloud provider** → Processor
- **Standard DPA:** Hyperscalers' standard DPAs may have limited sub-processor lists and audit rights; negotiation may be required for improvement
- **Cross-border:** Where the data is located (is there a Türkiye region?) may trigger the Art. 9 regime

### Scenario 5: Courier / Logistics
- **E-commerce company** → Controller
- **Courier company** → Processor or controller?
- **Test:** If the courier processes the recipient's personal data for additional purposes (its own marketing, its own insurance process) during delivery → its own controller status arises
- **In practice:** Most courier companies are both processor (on behalf of the sender) and controller (under their own legal obligations)

### Scenario 6: Law Firm
- **Client company** → Controller (for its own data)
- **Lawyer / law firm** → Generally an independent controller (due to legal duties of the legal profession)
- **Performing the case under instruction does not eliminate controller status** — the lawyer is subject to professional obligations independent of client instructions

### Scenario 7: Insurance Brokerage
- **Insurance company** → Controller
- **Broker** → Generally an independent controller (has its own professional duties)
- **As the party transmitting the insurance request**, the broker has independent contracting/duty obligations

### Scenario 8: Marketing / Advertising Agency
- **Brand company** → Controller
- **If the agency only performs creative production with limited personal data processing** → may be a processor
- **If the agency runs a data-driven campaign, performs segmentation, builds Lookalike audiences** → independent controller status

### Scenario 9: HR Recruitment / Headhunter
- **Hiring company** → Controller
- **Headhunter** → Generally an independent controller (has its own candidate pool, its own processes)
- **Outsourced HR** (only sourcing for the company's position) → may be a processor, if it does not use candidate data for any other purpose

### Scenario 10: Joint Marketing / Co-marketing
- If two companies engage in joint marketing → may be **joint data controllers**
- **Joint controllers:** Where both parties have authority over purposes/means of processing (both answer "why")
- **Contractually:** Allocation of obligations between the parties must be set out in writing

## 9. Practical Decision Flow

```
A data partnership / service relationship is starting
              |
              v
   What will the counterparty do, in which process? Define in detail.
              |
              v
   Ask "Why will it process?"
              |
              +-- For its own purpose (own legal obligation, own product) → INDEPENDENT CONTROLLER
              |
              +-- Solely on our instruction → May be a PROCESSOR
              |
   Ask "How will it process?"
              |
              +-- It makes strategic/processing-purpose decisions → JOINT CONTROLLER or INDEPENDENT CONTROLLER
              |
              +-- It only chooses the technical method (storage method, encryption type) → PROCESSOR
              |
              v
   Decision: Controller / Joint controller / Processor / Independent controller
              |
              v
   Prepare the appropriate type of contract:
   - Between two controllers: joint processing agreement + transfer disclosure in privacy notices
   - Controller-Processor: KVKK Art. 12-compliant Data Processing Agreement (DPA)
   - Joint controllers: responsibility allocation agreement
              |
              v
   Initiate supplier DD (due diligence)
              |
              v
   Update VERBİS notification: recipient groups updated, registry record amended if required
              |
              v
   Privacy notice updated
              |
              v
   Added to annual audit calendar
```

## 10. Common Mistakes

| Mistake | Correct Position |
|---------|------------------|
| "Cloud provider is a data processor, no contract needed" | KVKK Art. 12 mandates a written contract |
| "DPA is signed, that's it" | Annual audit, breach notification follow-up, sub-processor approval are continuous |
| "Group of companies, same owner" → single controller | Each legal entity is a separate controller |
| "The lawyer works on our instructions, is a processor" | Lawyer is generally an independent controller (professional legal duty) |
| "One VERBİS notification is enough" | A separate VERBİS record is required for each legal entity |
| "We are not liable for the processor's breach" | Under KVKK, the controller is also liable for the processor's actions (Art. 12) |
| "There is a joint controller arrangement but no contract" | Joint controller scenarios require written allocation of responsibilities |
| "The standard contract is sufficient, no negotiation needed" | Hyperscalers' standard DPAs may not always fully satisfy KVKK Art. 12 requirements; supplementary clauses are needed |

## 11. Related Documents

- `01-temel-kavramlar/tanimlar.md`
- `01-temel-kavramlar/isleme-sartlari.md`
- `07-aktarim/yurt-ici-aktarim.md`
- `07-aktarim/yurt-disi-aktarim.md`
- `10-ozel-konular/tedarikci-yonetimi.md`
- `99-sablonlar/veri-isleyen-sozlesmesi.md`
- `99-sablonlar/musterek-vs-sorumluluk-paylasim-sozlesmesi.md`

---

## Türkçe

# Veri Sorumlusu ve Veri İşleyen Ayrımı

## 1. Amaç

Bu doküman, KVKK kapsamındaki **veri sorumlusu** ve **veri işleyen** sıfatlarının net ayrıştırılması, somut ortaklık senaryolarında doğru sıfat tespiti, sözleşmesel yükümlülüklerin tam karşılanması için operasyonel çerçeveyi belirler.

## 2. Yasal Tanımlar

### 2.1 Veri Sorumlusu (KVKK m.3/1(ı))
"Kişisel verilerin işleme amaçlarını ve vasıtalarını belirleyen, veri kayıt sisteminin kurulmasından ve yönetilmesinden sorumlu olan gerçek veya tüzel kişi."

### 2.2 Veri İşleyen (KVKK m.3/1(ğ))
"Veri sorumlusunun verdiği yetkiye dayanarak onun adına kişisel verileri işleyen gerçek veya tüzel kişi."

### 2.3 Kurum Görüşü (Haziran 2025 Yayını)
- Veri sorumlusu kişisel verilerin işlenmesinde **"neden"** ve **"nasıl"** sorularına cevap verecek olan taraftır.
- Veri işleyen, **veri sorumlusunun talimatları çerçevesinde** ve **organizasyonu dışında** kişisel veri işleyen bağımsız taraftır.

## 3. Ayrım Kriterleri (Karar Testi)

Bir işleme faaliyetinde tarafların sıfatını belirlemek için aşağıdaki kararları **kim verdi?** sorusu sorulur:

| Karar | Veri Sorumlusu Olduğunu Gösterir |
|-------|----------------------------------|
| **Kişisel verilerin toplanma yöntemi** | Karar veren VS |
| **Toplanacak veri kategorileri** | Karar veren VS |
| **Hangi amaçla kullanılacak** | Karar veren VS |
| **Hangi bireylerin verileri toplanacak** | Karar veren VS |
| **Verilerin paylaşılıp paylaşılmayacağı, kiminle** | Karar veren VS |
| **Saklama süreleri** | Karar veren VS |

| Karar | Veri İşleyene Bırakılabilir |
|-------|------------------------------|
| Hangi BT sistemlerinin kullanılacağı | Genellikle işleyen seçer |
| Saklama yönteminin teknik detayları | İşleyen |
| Güvenlik tedbirlerinin teknik detayları | İşleyen (asgari seviye VS belirler) |
| Aktarımın teknik yöntemi | İşleyen |
| Saklama süresinin sistemde uygulanma metodu | İşleyen |
| İmha yöntemi (silme/yok etme/anonim) — teknik | İşleyen |

**Kritik:** "Nasıl"ın **stratejik** karar boyutu (hangi süreçte, hangi amaçla) VS'ye, **operasyonel-teknik** boyutu işleyene düşer.

## 4. Aynı Tüzel Kişilik İçinde İkili Sıfat

Bir gerçek veya tüzel kişi aynı anda **hem veri sorumlusu hem veri işleyen** sıfatlarını taşıyabilir. Bu, "duruma göre değişen" bir sınıflandırmadır:

### Örnek 1: Bulut Hizmet Sağlayıcısı
- **Kendi çalışan verileri için** → veri sorumlusu (işe alım, bordro, performans)
- **Müşteri şirketler için sakladığı veriler için** → veri işleyen (müşterinin talimatlarıyla)

### Örnek 2: Çağrı Merkezi
- **Kendi personelinin verileri** → veri sorumlusu
- **Müşteri şirket adına yapılan müşteri aramaları** → veri işleyen

### Örnek 3: Mali Müşavir
- **Kendi büro çalışanları** → veri sorumlusu
- **Müşterinin bordrosunu işlemesi** → genellikle veri sorumlusu (mesleki yasal yükümlülükleri olduğundan)

### Örnek 4: Pazarlama Ajansı
- **Kendi çalışanları** → veri sorumlusu
- **Müşteri şirket için kampanya verisi işleme** → veri işleyen (talimat ile sınırlı)
- **Pazar araştırması yapma** → veri sorumlusu (çoğu zaman, kararları kendisi alır)

## 5. Şirketler Topluluğunda Sıfat

KVKK kapsamında **her tüzel kişilik ayrı veri sorumlusudur**.

### 5.1 Önemli İlkeler
- Holding bünyesindeki ABC A.Ş. ve XYZ Ltd. Şti. → iki ayrı VS
- Veri grup şirketleri arasında "iç akış" değil **aktarımdır** — KVKK m.8 (yurt içi) veya m.9 (yurt dışı bağlı şirket) hükümleri uygulanır
- Müşterek hizmet (HR, BT, finans paylaşımlı servisler): hizmet veren grup şirketi diğeri için ya VS ya işleyendir; sözleşmesel olarak netleştirilmelidir
- "Holding genelinde tek aydınlatma metni" → her tüzel kişi için ayrı bildirim ve VERBİS kaydı gerektirdiğinden, çatı metin altında her şirketin kimliğinin ayrıştırıldığı bölümler şarttır

### 5.2 Grup İçi Aktarım Karar Akışı
```
Grup içi paylaşım planlanıyor
    |
    +-- Veriyi alan grup şirketinin kendi karar yetkisi var mı?
    |   |
    |   +-- Evet → Aktarım. İki ayrı VS arası işlem.
    |   |          (Açık rıza VEYA m.8 işleme şartı; aktarım amacı aydınlatmada belirtilmeli)
    |   |
    |   +-- Hayır, sadece talimat ile işliyor → İşleyen pozisyonunda
    |               (Veri işleyen sözleşmesi gerekli)
    |
    +-- Yurt dışındaki grup şirketine aktarım mı?
        |
        +-- Evet → KVKK m.9 (yeterlilik kararı / uygun güvence / arızi)
```

## 6. Veri İşleyen Sözleşmesi — Asgari Hükümler

KVKK m.12 ve veri güvenliği yükümlülüğü kapsamında, veri sorumlusu ile veri işleyen arasında **yazılı sözleşme** zorunludur. Sözleşmede asgari aşağıdaki hükümler bulunmalıdır:

### 6.1 Konu ve Süre
- İşleme faaliyetinin konusu, süresi
- Kişisel veri kategorileri ve ilgili kişi grupları
- Belirlenen amaç ve kapsam dışına çıkılmaması taahhüdü

### 6.2 Talimat Bağlılığı
- İşleyenin **yalnızca veri sorumlusunun yazılı talimatları** doğrultusunda işleme yapması
- Talimatlar dışındaki işlemenin yasak olduğu

### 6.3 Sır Saklama (KVKK m.12/4)
- İşleyenin ve onun adına çalışan kişilerin sır saklama yükümlülüğü
- Bu yükümlülüğün sözleşme bitiminden sonra da süresiz devam edeceği
- İşleyenin personeline gizlilik taahhüdü imzalattığı

### 6.4 Güvenlik Tedbirleri (KVKK m.12)
- İşleyenin uygulayacağı asgari teknik ve idari tedbirler
- Erişim yönetimi, log kayıtları, şifreleme, sızıntı önleme
- İşleyenin tedbirlerinin VS'ninkilere eşdeğer olması

### 6.5 Alt İşleyen
- VS'nin **önceden yazılı izni olmadan** alt işleyen kullanılamayacağı
- Onaylanmış alt işleyen listesinin sözleşmenin ekini oluşturması
- Alt işleyenle aynı koşulları içeren yazılı sözleşme zorunluluğu
- Alt işleyenin ihlali durumunda asıl işleyenin tam sorumlu olması

### 6.6 Yurt Dışı Aktarım
- Yurt dışına aktarım yapılacaksa hangi ülkelere
- Hangi uygun güvence (BCR, standart sözleşme, taahhütname) ile
- VS'nin önceden onayı gerektiği

### 6.7 Denetim Hakkı
- VS'nin tedbirlerin yerine getirilip getirilmediğini denetleme hakkı
- Bağımsız üçüncü taraf denetimi (ISO 27001, ISO 27701, SOC 2 Type II) ile karşılanabilirliği
- Yıllık asgari denetim raporu paylaşımı

### 6.8 İhlal Bildirimi
- İşleyenin ihlali öğrendikten sonra **24 saat içinde** VS'ye bildirim
- Bildirim içeriği: olay özeti, etkilenen veri kategorileri, kişi sayısı, alınan tedbirler
- VS'nin Kurum'a 72 saat içinde bildirim hazırlığı için işleyenin tam destek sağlaması

### 6.9 İlgili Kişi Talepleri
- VS'ye yönelmiş başvurularda işleyenin makul yardım yükümlülüğü
- Doğrudan işleyene yönelmiş taleplerin VS'ye yönlendirilmesi
- Yardım yükümlülüğünün kapsamı (verilerin temini, silinmesi, düzeltilmesi vb.)

### 6.10 İade ve İmha
- Sözleşme sona erdiğinde işleyenin elindeki tüm verileri:
  - **VS'ye iade etmesi** veya
  - **VS'nin talimatına göre imha etmesi**
- İmha tutanağı düzenlemesi
- İmhanın 30 gün içinde tamamlanması

### 6.11 Hukuki Yükümlülükler
- KVKK ve ikincil mevzuata tam uyum taahhüdü
- Mevzuat değişikliklerine adapte olma yükümlülüğü
- İdari para cezası halinde rücu hükümleri

### 6.12 Sigorta
- Yüksek riskli işlemelerde işleyenin siber sigorta veya mesleki sorumluluk sigortası tutması

## 7. "Sözleşmedeki sıfat" vs "Gerçek sıfat"

Önemli bir yanılgı: tarafların sözleşmede kendilerini "veri işleyen" olarak nitelemesi, KVKK kapsamında otomatik olarak bu sıfatı vermez. **Gerçek sıfat, fiili karar verme yetkisinden doğar.**

Örneğin: Pazar araştırması şirketi sözleşmede "veri işleyen" yazsa bile, kendisi anket sorularına, örneklem seçimine, veri kullanım kararlarına etki ediyorsa **veri sorumlusudur**.

## 8. Pratik Senaryolar (Türkiye Bağlamı)

### Senaryo 1: SaaS CRM Sağlayıcısı
- **Müşteri şirket** (e-ticaret platformu) → Veri sorumlusu
- **CRM SaaS sağlayıcı** → Veri işleyen
- **Gerekli sözleşme:** Veri işleme sözleşmesi (DPA), KVKK m.12 gereksinimleri ile
- **Yurt dışı boyutu:** SaaS sağlayıcı yurt dışı ise → m.9 rejimi

### Senaryo 2: Çağrı Merkezi Outsourcing
- **Banka** → VS
- **Çağrı merkezi şirketi** → İşleyen
- **Önemli:** Çağrı merkezi script'lerini ve müşteri yanıt politikalarını bankanın belirlediği durumda — talimat dışına çıkamaz; yorum yetkisi yok

### Senaryo 3: Bordro Hizmeti
- **İşveren şirket** → VS
- **Bordro hizmet sağlayıcı** → İşleyen (sadece talimatla işliyorsa)
- **Aksi:** Mali müşavir mesleki yasal yükümlülüklerle hareket ediyorsa (yolsuzluk bildirim zorunluluğu vs.) → bağımsız VS pozisyonu da olabilir

### Senaryo 4: Bulut Veri Tabanı (AWS RDS, Azure SQL, GCP Cloud SQL)
- **Müşteri şirket** → VS
- **Bulut sağlayıcı** → İşleyen
- **Standart DPA:** Hyperscaler'ların standart DPA'larında alt işleyen listeleri ve denetim hakları sınırlı; iyileştirme için müzakere gerekli olabilir
- **Yurt dışı:** Veri lokasyonunun nerede olduğu (Türkiye region var mı?) m.9 rejimi tetikleyebilir

### Senaryo 5: Kargo / Lojistik
- **E-ticaret şirketi** → VS
- **Kargo şirketi** → İşleyen mi, VS mi?
- **Test:** Kargo şirketi teslimat sürecinde alıcının kişisel verilerini başka amaçla (kendi pazarlaması, kendi sigorta süreci) işliyorsa → kendi adına VS sıfatı doğar
- **Pratikte:** Çoğu kargo şirketi hem işleyen (gönderen şirket adına) hem VS (kendi yasal yükümlülükleri kapsamında)

### Senaryo 6: Hukuk Firması
- **Müvekkil şirket** → VS (kendi verisi için)
- **Avukat / hukuk firması** → Genellikle bağımsız VS (avukatlık mesleğinin yasal sorumlulukları gereği)
- **Talimatla davanın yürütülmesi VS sıfatını ortadan kaldırmaz** — avukat, müvekkilin talimatından bağımsız mesleki yükümlülüklere tabidir

### Senaryo 7: Sigorta Brokerlığı
- **Sigorta şirketi** → VS
- **Broker** → Genellikle bağımsız VS (kendi mesleki yükümlülükleri var)
- **Sigorta talebini ileten kişi olarak** broker bağımsız sözleşme/yükümlülük taşır

### Senaryo 8: Pazarlama / Reklam Ajansı
- **Marka şirket** → VS
- **Ajans, sadece kreatif üretim yapıyorsa kişisel veri işlemesi sınırlı** → işleyen olabilir
- **Ajans data-driven kampanya yürütüyor, segmentasyon yapıyor, Lookalike audience oluşturuyor** → bağımsız VS pozisyonu

### Senaryo 9: İK İşe Alım / Headhunter
- **İşe alım yapan şirket** → VS
- **Headhunter** → Genellikle bağımsız VS (kendi aday havuzu var, kendi süreçleri var)
- **Outsource İK** (sadece şirketin pozisyonu için aday bulma) → işleyen olabilir, eğer aday verisini başka amaçla kullanmıyorsa

### Senaryo 10: Ortak Pazarlama / Co-marketing
- İki şirket ortak pazarlama yapıyorsa → **müşterek veri sorumluları** olabilir
- **Müşterek VS:** İki tarafın da işleme amacı/vasıtası belirleme yetkisi varsa (her ikisi de "neden" sorusuna cevap veriyor)
- **Sözleşmesel olarak:** Hangi tarafın hangi yükümlülüğü üstleneceği yazılı netleştirilmeli

## 9. Pratik Karar Akışı

```
Bir veri ortaklığı / hizmet ilişkisi başlıyor
              |
              v
    Karşı taraf hangi süreçte ne yapacak? Detaylı belirle.
              |
              v
   "Neden işleyecek?" sorusunu sor
              |
              +-- Kendi amacı için (kendi yasal yükümlülüğü, kendi ürünü) → BAĞIMSIZ VS
              |
              +-- Sadece bizim talimatımız ile → İŞLEYEN olabilir
              |
   "Nasıl işleyecek?" sorusunu sor
              |
              +-- Stratejik/işleme amacı kararları kendisi alıyor → MÜŞTEREK VS veya BAĞIMSIZ VS
              |
              +-- Sadece teknik metodu kendisi seçiyor (saklama yöntemi, şifreleme türü) → İŞLEYEN
              |
              v
   Karar: VS / Müşterek VS / İşleyen / Bağımsız VS
              |
              v
   Buna göre uygun sözleşme türünü hazırla:
   - VS-VS arası: Ortak işleme sözleşmesi + aydınlatma metinlerinde aktarım belirtilmesi
   - VS-İşleyen: KVKK m.12 uyumlu Veri İşleme Sözleşmesi (DPA)
   - Müşterek VS: Sorumluluk paylaşım sözleşmesi
              |
              v
   Tedarikçi DD (due diligence) süreci başlat
              |
              v
   VERBİS bildiriminde: alıcı grupları güncellenir, gerekirse kayıt değiştirilir
              |
              v
   Aydınlatma metni güncellenir
              |
              v
   Yıllık denetim takvimine eklenir
```

## 10. Yaygın Hatalar

| Hata | Doğrusu |
|------|---------|
| "Bulut sağlayıcı veri işleyendir, sözleşmeye gerek yok" | KVKK m.12 yazılı sözleşme zorunlu kılar |
| "DPA imzalandı, bitti" | Yıllık denetim, ihlal bildirim takibi, alt işleyen onayı sürekli |
| "Şirketler topluluğu, aynı sahip" → tek VS | Her tüzel kişi ayrı VS |
| "Avukat bizim talimatımızla çalışıyor, işleyendir" | Avukat genellikle bağımsız VS (mesleki yasal yükümlülük) |
| "VERBİS'e tek bildirim yeterli" | Her tüzel kişi için ayrı VERBİS kaydı |
| "İşleyenin ihlalinden biz sorumlu değiliz" | KVKK kapsamında VS, işleyenin eylemlerinden de sorumlu (m.12) |
| "Müşterek VS konusu var ama sözleşme yok" | Müşterek VS senaryoları yazılı sorumluluk paylaşımı gerektirir |
| "Standart sözleşmeden yeterli, müzakere gerekmez" | Hyperscaler standart DPA'ları her zaman KVKK m.12 gereksinimlerini tam karşılamayabilir; ek hükümler eklenmeli |

## 11. İlgili Dokümanlar

- `01-temel-kavramlar/tanimlar.md`
- `01-temel-kavramlar/isleme-sartlari.md`
- `07-aktarim/yurt-ici-aktarim.md`
- `07-aktarim/yurt-disi-aktarim.md`
- `10-ozel-konular/tedarikci-yonetimi.md`
- `99-sablonlar/veri-isleyen-sozlesmesi.md`
- `99-sablonlar/musterek-vs-sorumluluk-paylasim-sozlesmesi.md`
