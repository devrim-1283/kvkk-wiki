---
Doküman / Document: Yurt İçi Kişisel Veri Aktarımı / Domestic Personal Data Transfer
Bölüm / Section: 07-aktarim
Sahip / Owner: KVKK Sorumlusu / KVKK Officer
Onaylayan / Approved by: Hukuk Müdürü + Bilgi Güvenliği Yöneticisi / Legal Director + Information Security Manager
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş / Annual + triggered (regulatory change, new business process, new vendor)
İlgili Mevzuat / Legal Reference: KVKK Art. 4, 5, 6, 8, 10, 12; Board decisions on Data Processor Contracts
---

## English

# Domestic Personal Data Transfer

## 1. Legal Framework (KVKK Art. 8)

KVKK Art. 8 governs the transfer of personal data to third parties within Turkey. The core principles:

- Data processed under the general principles (Art. 4) and processing conditions (Art. 5/Art. 6) may be transferred to third parties **provided that there is also a separate legal basis for the transfer**.
- Even within Turkey, **a basis for transfer is required separately, just like processing conditions**: lawful processing does not automatically legitimize transfer.
- Explicit consent is one of the lawful grounds for transfer; however, if other grounds exist, explicit consent is not required.

> **Critical:** Data may be lawfully processed in Turkey, but this does not directly mean it can be transferred. For transfer, one of the conditions in Art. 5/Art. 6 must be satisfied **at the moment of transfer**.

## 2. Transfer Conditions for General Personal Data (Art. 5)

Transfer can be made if any of the following exists, in addition to explicit consent:

| # | Condition | Typical Scenario |
|---|-----------|------------------|
| 1 | Explicit consent | Marketing data sharing, third-party analytics tools |
| 2 | Explicitly provided for in laws | Social Security notification, payroll sharing with CPA, providing information to judicial authorities |
| 3 | Necessary for life/bodily integrity (data subject unable to give consent) | Emergency medical situation — data transfer to hospital/ambulance |
| 4 | Directly related to formation/performance of a contract | Transfer of customer's address to a logistics firm under the contract |
| 5 | Compliance with a legal obligation of the controller | Transfer of documents to authorities during a tax audit |
| 6 | Manifestly made public by the data subject | Use of public LinkedIn profile in a competency search (limited) |
| 7 | Establishment, exercise or protection of a right | Sharing with attorney as evidence in a lawsuit |
| 8 | Legitimate interest of the data controller | HR sharing within a group of companies; transfer to marketing automation SaaS |

## 3. Transfer Conditions for Special Categories of Personal Data (Art. 6)

Transfer of special category data (health, sexual life, race, religion, biometric, etc.) is subject to stricter conditions:

- Where there is **explicit consent**,
- For special category data **other than** health and sexual life: where **explicitly provided in laws**,
- For health and sexual life data: for purposes of **public health protection, preventive medicine, medical diagnosis, treatment and care services, planning and management of health services and financing**, and **only by persons under a duty of confidentiality or authorized institutions/organizations**.

> **Practical:** Employee health reports can in principle be transferred only to persons under a duty of confidentiality such as the workplace physician; transferring to even the HR Director without explicit consent requires care.

## 4. Types of Transfer

### 4.1. Controller → Processor Transfer

A processor is a person who processes personal data **based on the controller's instructions** and **outside its own organization**. In this transfer type:

- Pursuant to KVKK Art. 12/3, **controller and processor are jointly liable**.
- A **written contract** must exist between them and contain the minimum elements.
- The processor has **no** authority to determine purpose and means; if the contract grants that authority, at that point the processor becomes a **controller** for the transferred data.

#### 4.1.1. Minimum Elements of a Processor Contract

| Element | Description |
|---------|-------------|
| Definition and scope | Data categories, data subject groups, processing purposes, duration |
| Instruction clause | The processor may process only on the controller's written instruction |
| Confidentiality | Confidentiality undertaking by processor's personnel |
| Security measures | Technical+administrative measures (KVKK Art. 12) — concretely listed |
| Sub-processor use | Sub-processor only with written authorization; same obligations passed to sub-processor |
| Assistance obligation | Help in responding to data subject requests and breach management |
| Breach notification | **Immediate notification** to controller (concrete time, e.g. 24 hours) |
| Audit | Controller's right to audit; access to audit reports |
| Termination | Destruction or return of data per controller's instructions |
| Forum and law | Republic of Turkey law and Istanbul Courts (typical) |
| KVKK Art. 12 reference | Express reference |

### 4.2. Controller → Controller Transfer

If both parties determine purpose and means in their own name, both are **controllers**. In this transfer type:

- Each party is independently responsible for KVKK compliance.
- A **transfer agreement** is signed between them; this is different from a processor contract.
- Each party must perform **its own disclosure**; the recipient party has a fresh disclosure obligation toward the data subject.

### 4.3. Joint Controllership

A structure where two or more controllers jointly decide on the same processing purpose and means. There is no explicit provision in Turkish law but it is recognized in Board decisions and doctrine. Typical examples:

- A research firm and sponsor company designing a survey together,
- An attorney and client jointly deciding on personal data shared as evidence in a case,
- Two companies jointly processing a shared customer portfolio for marketing.

In joint controllership, **both parties**:

- Disclose under Art. 10,
- Independently respond to Art. 13 applications,
- Independently take Art. 12 measures.

If a party diverges on decisions outside the agreed scope, joint controllership ends at that point.

### 4.4. Decision Tree: Is the Vendor a Controller or a Processor?

```
+-------------------------------------------------+
| Can the vendor use personal data for its own    |
| purposes outside the contract?                  |
+-------------------------------------------------+
       |                          |
    yes|                        no|
       v                          v
+--------------+        +-------------------------------+
| Controller   |        | Does the vendor have authority|
+--------------+        | to determine purpose and      |
                        | means of processing?          |
                        +-------------------------------+
                              |              |
                          yes|             no|
                              v              v
                  +------------------+  +--------------+
                  | Controller       |  | Processor    |
                  | (may be joint)   |  +--------------+
                  +------------------+
```

## 5. Testing the Legal Legitimacy of Transfer

The following questions are answered for each transfer:

1. **Which data category is being transferred?** (General / special category)
2. **Who is transferring, to whom?** (Recipient is controller or processor?)
3. **What is the purpose of transfer?** (Contract performance / legal obligation / marketing / analytics, etc.)
4. **Which Art. 5/Art. 6 condition is the basis?** (Explicit consent is last resort; legitimate interest or contract performance preferred where possible)
5. **What is the contract type?** (Processor contract / transfer agreement / joint controller arrangement)
6. **Has disclosure been made?** (Art. 10 obligation)
7. **Reflected in VERBİS?** (As recipient group)
8. **Have technical measures been taken?** (Encryption, access control)

## 6. Common Domestic Transfer Scenarios

### 6.1. Transfer of Employee Payroll to a CPA

- **Legal basis:** KVKK Art. 5/2-(a) "explicitly provided in laws" (Tax Procedure Law, Labor Law)
- **Status:** The CPA is a **controller** because of its own professional obligations.
- **Contract:** Transfer agreement and confidentiality undertaking.
- **Disclosure:** The disclosure includes "authorized CPA" as recipient group.

### 6.2. Transfer of Customer Address to Logistics Vendor

- **Legal basis:** KVKK Art. 5/2-(c) "directly related to performance of a contract"
- **Status:** **Processor** if the logistics firm uses data only for delivery; **controller** if it processes for its own carriage and insurance processes.
- **Contract:** Processor contract (with full minimum elements).
- **Disclosure:** Order disclosure lists "logistics service providers" as recipient group.

### 6.3. Transfer of Data to a CRM SaaS Provider (Hosted in Turkey)

- **Legal basis:** KVKK Art. 5/2-(f) "legitimate interest" + contract performance
- **Status:** Provider only hosts the customer's data → **processor**. If provider aggressively uses data for its own analytics/improvement → **controller** (joint controllership risk).
- **Contract:** Processor contract + DPA.
- **Disclosure:** "CRM service provider" as recipient group in customer disclosure.

### 6.4. Transfer of Marketing Data to an Ad Agency

- **Legal basis:** Explicit consent (Art. 5/1) — for marketing-related processing and transfer
- **Status:** **Controller** or **joint controller** if the agency has authority to design the campaign; **processor** if it only executes technically.
- **Contract:** Transfer agreement or processor contract.
- **Disclosure:** Transfer is explicitly stated in the explicit consent text.

### 6.5. HR Data Sharing Within Group Companies

- **Legal basis:** KVKK Art. 5/2-(f) "legitimate interest" + contract performance (intra-group agreement)
- **Status:** Each company is a separate legal entity → separate controllers. Transfer is to a separate controller.
- **Contract:** Intra-group data sharing agreement.
- **Disclosure:** Employee disclosure lists "group companies" as recipient group.

### 6.6. Providing Documents to Judicial Authorities

- **Legal basis:** KVKK Art. 5/2-(a) "explicitly provided in laws" (Code of Criminal Procedure, Code of Civil Procedure)
- **Status:** Providing data to a court or prosecutor is a transfer; however, since legally mandatory, no separate consent is required.
- **Contract:** None; transmittal via official letter.
- **Disclosure:** "Authorized public institutions and organizations" in the general disclosure.

## 7. Minimum Elements of Transfer Agreement (for C-C Transfers)

| Element | Description |
|---------|-------------|
| Parties | Two identified data controllers |
| Purpose | Clear and limited |
| Data categories | Listed |
| Data subject groups | Stated |
| Legal basis | Which Art. 5/Art. 6 condition |
| Duration | Transfer duration; recipient retention period |
| Disclosure obligation | Acceptance of recipient's obligation toward data subject |
| Security measures | Technical+administrative measures by parties |
| Breach notification | Mutual notification |
| Data protection period | Destruction or return when transfer purpose ends |
| Liability | Mutual indemnification clauses |
| Disputes | Turkish law, competent court |

## 8. Reflection in VERBİS

Domestic transfers in VERBİS:

- Listed under "Recipient/recipient groups to whom personal data may be transferred."
- "Domestic or cross-border transfer?" field marked "domestic."
- Mapping between data category and recipient group ensured.

Typical recipient group examples (standard registry categories):

- Business Partner
- Supplier (logistics / IT / legal / finance)
- Shareholders
- Affiliates and Subsidiaries
- Authorized Public Institutions and Organizations
- Legally Authorized Private Law Persons
- Data Processor Service Provider

## 9. Common Mistakes

| Mistake | Result | Mitigation |
|---------|--------|------------|
| Confusing transfer with processing condition | Separate basis for transfer not shown | Transfer Impact Assessment for each transfer |
| Failing to recognize a processor as a controller | Wrong contract type; misallocation of liability | Apply decision tree; status determination before contracting |
| Trying to use legitimate interest for marketing transfers | Board may reject; explicit consent required | Explicit consent for marketing; consent proof |
| Missing or insufficient DPA (processor contract) | KVKK Art. 12 violation | Standard DPA template; integrated into procurement flow |
| Missing recipient group in disclosure | KVKK Art. 10 violation | Reconcile disclosure with inventory |
| Sending special category data via ordinary transfer | KVKK Art. 6 violation | Special procedure for special category data; check duty of confidentiality |

## 10. Pre-Transfer Checklist

- [ ] Has the purpose of transfer been defined?
- [ ] Which data categories are being transferred?
- [ ] General or special category?
- [ ] Is the recipient a controller or processor? (Decision tree)
- [ ] Which Art. 5/Art. 6 processing condition?
- [ ] Has the transfer agreement/DPA been signed?
- [ ] Does the contract contain minimum elements?
- [ ] Is the disclosure notice up to date?
- [ ] Has it been reflected in VERBİS?
- [ ] Have technical measures (encryption, access) been defined?
- [ ] Has the breach notification line been established?
- [ ] Has the entry been made in the transfer inventory?

---

## Türkçe

# Yurt İçi Kişisel Veri Aktarımı

## 1. Hukuki Çerçeve (KVKK m.8)

KVKK m.8, kişisel verilerin Türkiye sınırları içinde üçüncü kişilere aktarılmasını düzenler. Maddenin temel ilkeleri:

- Kanunda belirtilen genel ilkeler (m.4) ve işleme şartları (m.5/m.6) çerçevesinde işlenmiş veriler, **ayrıca aktarım için bir hukuki dayanak bulunması koşuluyla** üçüncü kişilere aktarılabilir.
- Yurt içinde de aktarımın **işleme şartları gibi ayrıca aranması gerekir**: işlemenin meşru olması, otomatik olarak aktarımı meşru kılmaz.
- Açık rıza, aktarımın meşru sebeplerinden biridir; ancak başka şartlar varsa açık rıza aranmaz.

> **Kritik:** Veri yurt içinde hukuka uygun işlenmiş olabilir, ama bu doğrudan aktarılabileceği anlamına gelmez. Aktarım için m.5/m.6'da düzenlenen şartlardan birinin **aktarım anında** sağlanmış olması gerekir.

## 2. Genel Nitelikli Kişisel Veriler İçin Aktarım Şartları (m.5)

Açık rıza dışında aşağıdakilerden birinin varlığı halinde aktarım yapılabilir:

| # | Şart | Tipik Senaryo |
|---|------|---------------|
| 1 | Açık rıza | Pazarlama amaçlı paylaşım, üçüncü taraf analitik araçları |
| 2 | Kanunlarda açıkça öngörülmesi | SGK bildirimi, Mali Müşavire bordro paylaşımı, Adli mercilere bilgi verme |
| 3 | Fiili imkânsızlık (rızasını açıklayamayacak kişi) için hayat/beden bütünlüğü | Acil sağlık durumu — hastane/ambulansa veri aktarımı |
| 4 | Sözleşmenin kurulması/ifasıyla doğrudan ilgili olması | Müşteri sözleşmesi gereği lojistik firmasına teslimat adresi aktarımı |
| 5 | Veri sorumlusunun hukuki yükümlülüğü | Vergi denetiminde yetkili mercilere belge aktarımı |
| 6 | İlgili kişi tarafından alenileştirme | Aleni LinkedIn profilinin yetkinlik araştırmasında kullanılması (sınırlı) |
| 7 | Hak tesisi/kullanılması/korunması | Davada delil olarak avukatla paylaşım |
| 8 | Veri sorumlusunun meşru menfaati | Grup şirketi içinde IK paylaşımı; pazarlama otomasyon SaaS aktarımı |

## 3. Özel Nitelikli Kişisel Veriler İçin Aktarım Şartları (m.6)

Özel nitelikli veriler (sağlık, cinsel hayat, ırk, din, biyometrik vb.) için aktarım daha katı şartlara bağlıdır:

- **Açık rıza** halinde,
- Sağlık ve cinsel hayat **dışındaki** özel nitelikli veriler için: **kanunlarda açıkça öngörülmüş olması**,
- Sağlık ve cinsel hayata ilişkin veriler için: **kamu sağlığının korunması, koruyucu hekimlik, tıbbi teşhis, tedavi ve bakım hizmetlerinin yürütülmesi, sağlık hizmetleri ile finansmanının planlanması ve yönetimi** amacıyla, **sır saklama yükümlülüğü altındaki kişiler veya yetkili kurum/kuruluşlar tarafından**.

> **Pratik:** Çalışan sağlık raporları kural olarak ancak işyeri hekimi gibi sır saklama yükümlülüğü altındaki kişilere aktarılabilir; İK Direktörüne dahi açık rıza olmadan aktarılması özen gerektirir.

## 4. Aktarımın Türleri

### 4.1. Veri Sorumlusu → Veri İşleyen Aktarımı

Veri işleyen, veri sorumlusunun **talimatı doğrultusunda** ve **organizasyonu dışında** kişisel verileri işleyen kişidir. Bu aktarım türünde:

- KVKK m.12/3 uyarınca **veri sorumlusu ile veri işleyen müşterek sorumludur**.
- Aralarında **yazılı sözleşme** bulunması ve sözleşmenin asgari unsurları içermesi gerekir.
- Veri işleyenin amaç ve vasıta belirleme yetkisi **yoktur**; sözleşme ile bu yetki belirtilirse o noktada veri işleyen, aktarılan veri için **veri sorumlusu** statüsüne geçer.

#### 4.1.1. Veri İşleyen Sözleşmesinin Asgari Unsurları

| Unsur | Açıklama |
|-------|----------|
| Tanım ve kapsam | İşlenecek veri kategorileri, ilgili kişi grupları, işleme amaçları, süresi |
| Talimat hükmü | Veri işleyenin yalnızca veri sorumlusunun yazılı talimatı doğrultusunda işleyebileceği |
| Gizlilik | Veri işleyen personelinin gizlilik taahhüdü altında olması |
| Güvenlik tedbirleri | KVKK m.12 anlamında teknik+idari tedbirlerin alınması — somut listelenmiş |
| Alt-işleyen kullanımı | Alt-işleyen ancak yazılı izin ile; aynı yükümlülüklerin alt-işleyene de yansıtılması |
| Yardım yükümlülüğü | İlgili kişi taleplerinin cevaplanmasında ve ihlal yönetiminde yardım |
| İhlal bildirimi | Veri sorumlusuna **derhal bildirim** (somut süre ör. 24 saat) |
| Denetim | Veri sorumlusunun denetim hakkı; denetim raporlarına erişim |
| Sözleşmenin sona ermesi | Veri sorumlusunun talimatına göre verilerin imhası veya iadesi |
| Yargı yeri ve hukuk | Türkiye Cumhuriyeti hukuku ve İstanbul Mahkemeleri (tipik) |
| KVKK m.12 atfı | Açık atıf yapılır |

### 4.2. Veri Sorumlusu → Veri Sorumlusu Aktarımı

İki taraf da kendi adına amaç ve vasıta belirliyorsa, ikisi de **veri sorumlusudur**. Bu aktarım türünde:

- Her iki taraf bağımsız KVKK uyumundan sorumludur.
- Aralarında **aktarım sözleşmesi** akdedilir; bu, veri işleyen sözleşmesinden farklıdır.
- Her iki taraf da **kendi aydınlatma metnini** yapar; alıcı taraf, ilgili kişiye yeni bir aydınlatma yükümlülüğü altındadır.

### 4.3. Joint Controllership (Müşterek Veri Sorumluluğu)

İki veya daha çok veri sorumlusunun aynı işleme amacı ve vasıtası üzerinde ortak karar aldığı yapıdır. Türk hukukunda açık düzenleme yoktur ancak Kurul kararlarında ve doktrinde kabul görmektedir. Tipik örnekler:

- Bir araştırma şirketi ile sponsor şirket, anketi birlikte tasarlıyorsa,
- Avukat ile müvekkil, bir davada delil olarak paylaşılan kişisel veriler için ortak karar veriyorsa,
- Pazarlama amacıyla iki şirket ortak müşteri portföyünü işliyorsa.

Joint controllership halinde **iki taraf da**:

- m.10 kapsamında ilgili kişiyi aydınlatır,
- m.13 başvurularına bağımsız cevap verir,
- m.12 tedbirlerini bağımsız alır.

Anlaşmaya konu kapsam dışında bir taraf alacağı kararlarla diğerinden farklılaşırsa, joint controllership o noktada sona erer.

### 4.4. Karar Ağacı: Tedarikçi Veri Sorumlusu mu, Veri İşleyen mi?

```
+-------------------------------------------------+
| Tedarikçi kişisel veriyi sözleşme dışı kendi    |
| amaçları için kullanabilir mi?                  |
+-------------------------------------------------+
       |                          |
   evet|                       hayır|
       v                          v
+--------------+        +-------------------------------+
| Veri         |        | Tedarikçi, kişisel verinin    |
| sorumlusu    |        | işleneceği amaç ve vasıtaya   |
+--------------+        | karar verme yetkisi sahip mi? |
                        +-------------------------------+
                              |              |
                          evet|           hayır|
                              v              v
                  +------------------+  +--------------+
                  | Veri sorumlusu   |  | Veri işleyen |
                  | (joint olabilir) |  +--------------+
                  +------------------+
```

## 5. Aktarımın Hukuki Meşruluğunun Test Edilmesi

Her aktarım için aşağıdaki sorular cevaplanır:

1. **Hangi veri kategorisi aktarılıyor?** (Genel / özel nitelikli)
2. **Kim aktarıyor, kime aktarıyor?** (Alıcı veri sorumlusu mu, veri işleyen mi?)
3. **Aktarım amacı ne?** (Sözleşme ifası / hukuki yükümlülük / pazarlama / analitik / vb.)
4. **Hangi m.5/m.6 şartı dayanak?** (Açık rıza son seçenek; mümkünse meşru menfaat veya sözleşme ifası tercih edilir)
5. **Sözleşme tipi hangisi?** (Veri işleyen sözleşmesi / aktarım sözleşmesi / joint controller anlaşması)
6. **Aydınlatma yapıldı mı?** (m.10 yükümlülüğü)
7. **VERBİS'e yansıtıldı mı?** (Alıcı grubu olarak)
8. **Teknik tedbirler alındı mı?** (Şifreleme, erişim kontrolü)

## 6. Yaygın Yurt İçi Aktarım Senaryoları

### 6.1. Çalışan Bordrosunun Mali Müşavire Aktarılması

- **Hukuki sebep:** KVKK m.5/2-(a) "Kanunlarda açıkça öngörülmesi" (213 VUK, 4857 İş K.)
- **Statü:** Mali müşavir, kendi mesleki yükümlülükleri nedeniyle **veri sorumlusu** statüsündedir (kendi yasal sorumlulukları olduğu için).
- **Sözleşme:** Aktarım sözleşmesi ve gizlilik anlaşması.
- **Aydınlatma:** Çalışan aydınlatma metninde alıcı grubu olarak "yetkili mali müşavir" geçer.

### 6.2. Lojistik Tedarikçisine Müşteri Adresi Aktarılması

- **Hukuki sebep:** KVKK m.5/2-(c) "Sözleşmenin ifasıyla doğrudan ilgili olması"
- **Statü:** Lojistik firmasının yalnızca teslimat amacıyla veri kullandığı, kendi adına işlemediği durumda **veri işleyen**. Lojistik firmasının kendi taşıma ve sigorta süreci için bağımsız işlem yapması durumda **veri sorumlusu**.
- **Sözleşme:** Veri işleyen sözleşmesi (asgari unsurlar tam).
- **Aydınlatma:** Sipariş aydınlatmasında alıcı grubu olarak "lojistik hizmet sağlayıcıları".

### 6.3. CRM SaaS Sağlayıcısına Veri Aktarımı (Türkiye'de barındırma)

- **Hukuki sebep:** KVKK m.5/2-(f) "Meşru menfaat" + sözleşme ifası
- **Statü:** Sağlayıcı sadece müşterinin verisini barındırıyor → **veri işleyen**. Sağlayıcı kendi analitik/iyileştirme amacıyla agresif bir şekilde veriyi kullanıyorsa → **veri sorumlusu** (joint controllership riski).
- **Sözleşme:** Veri işleyen sözleşmesi + DPA.
- **Aydınlatma:** Müşteri aydınlatmasında alıcı grubu olarak "CRM hizmet sağlayıcısı".

### 6.4. Reklam Ajansına Pazarlama Verisi Aktarımı

- **Hukuki sebep:** Açık rıza (m.5/1) — pazarlama amaçlı işleme ve aktarım için
- **Statü:** Ajansın kampanyayı tasarlamada karar verme yetkisi varsa **veri sorumlusu** veya **joint controller**; sadece teknik uygulama yapıyorsa **veri işleyen**.
- **Sözleşme:** Aktarım sözleşmesi veya veri işleyen sözleşmesi.
- **Aydınlatma:** Açık rıza metninde aktarım açıkça belirtilir.

### 6.5. Şirketler Topluluğu İçinde IK Veri Paylaşımı

- **Hukuki sebep:** KVKK m.5/2-(f) "Meşru menfaat" + sözleşme ifası (grup içi sözleşme)
- **Statü:** Her şirket ayrı tüzel kişi → ayrı veri sorumlusu. Aktarım, ayrı bir veri sorumlusuna aktarımdır.
- **Sözleşme:** Grup içi veri paylaşım anlaşması.
- **Aydınlatma:** Çalışan aydınlatması "grup şirketleri" olarak alıcı grubunu listeler.

### 6.6. Adli Mercilere Belge Verilmesi

- **Hukuki sebep:** KVKK m.5/2-(a) "Kanunlarda açıkça öngörülmesi" (CMK, HMK)
- **Statü:** Mahkeme veya savcılığa veri verilmesi aktarımdır; ancak yasa gereği zorunlu olduğu için ayrıca rıza aranmaz.
- **Sözleşme:** Yok; resmi yazıyla iletim.
- **Aydınlatma:** Genel aydınlatma metninde "yetkili kamu kurum ve kuruluşları" olarak.

## 7. Aktarım Sözleşmesi Asgari Unsurları (VS-VS aktarımı için)

| Unsur | Açıklama |
|-------|----------|
| Taraflar | Kimliği belirli iki veri sorumlusu |
| Aktarımın amacı | Açık ve sınırlı |
| Veri kategorileri | Liste halinde |
| İlgili kişi grupları | Açık |
| Hukuki sebep | KVKK m.5/m.6 hangi şart |
| Süre | Aktarımın süresi; verilerin alıcıdaki saklama süresi |
| Aydınlatma yükümlülüğü | Alıcının ilgili kişiye karşı yükümlülüğünü kabul etmesi |
| Güvenlik tedbirleri | Tarafların alacağı teknik+idari tedbirler |
| İhlal bildirimi | Karşılıklı bildirim |
| Verinin korunma süresi | Aktarımın amacı sona erince imha veya iade |
| Sorumluluk | Karşılıklı tazminat hükümleri |
| Uyuşmazlık | TC hukuku, yetkili mahkeme |

## 8. VERBİS'e Yansıtma

Yurt içi aktarımlar VERBİS'te:

- "Kişisel verilerin aktarılabileceği alıcı/alıcı grupları" alanına alıcı grubu olarak yazılır.
- "Yurt içinde mi yurt dışına mı aktarılıyor?" alanı "yurt içi" olarak işaretlenir.
- Veri kategorisi ile alıcı grubu eşleşmesi sağlanır.

Alıcı grubu örnekleri (sicil tipik kategorileri):

- İş Ortağı
- Tedarikçi (lojistik / IT / hukuk / finans)
- Hissedarlar
- İştirakler ve Bağlı Ortaklıklar
- Yetkili Kamu Kurum ve Kuruluşları
- Hukuken Yetkili Özel Hukuk Kişileri
- Veri İşleyen Hizmet Sağlayıcısı

## 9. Tipik Hatalar

| Hata | Sonuç | Önlem |
|------|-------|-------|
| Aktarımın işleme şartı ile karıştırılması | Aktarım için ayrıca dayanak gösterilmemiş | Her aktarım için Aktarım Etki Değerlendirmesi |
| Veri işleyenin veri sorumlusu olduğunun fark edilmemesi | Yanlış sözleşme tipi; sorumluluk dağılımı hatalı | Karar ağacı uygulanır; sözleşme öncesi statü tespiti |
| Pazarlama aktarımları için meşru menfaat denenmesi | Kurul reddedebilir; açık rıza zorunluluğu | Pazarlama için açık rıza; rıza ispatı |
| DPA (veri işleyen sözleşmesi) eksik veya yetersiz | KVKK m.12 ihlali | Standart DPA şablonu; satınalma akışına entegre |
| Aydınlatmada alıcı grubu eksik | KVKK m.10 ihlali | Envanter ile aydınlatma metni karşılaştırması |
| Özel nitelikli veriyi sıradan aktarım yoluyla göndermek | KVKK m.6 ihlali | Özel nitelikli veri için ek prosedür; sır saklama yükümlüsü kontrolü |

## 10. Aktarım Öncesi Kontrol Listesi

- [ ] Aktarımın amacı tanımlandı mı?
- [ ] Hangi veri kategorileri aktarılıyor?
- [ ] Genel mi özel nitelikli mi?
- [ ] Alıcı veri sorumlusu mu, veri işleyen mi? (Karar ağacı)
- [ ] m.5/m.6 hangi işleme şartı?
- [ ] Aktarım sözleşmesi/DPA imzalandı mı?
- [ ] Sözleşme asgari unsurları içeriyor mu?
- [ ] Aydınlatma metni güncel mi?
- [ ] VERBİS'e yansıtıldı mı?
- [ ] Teknik tedbirler (şifreleme, erişim) tanımlandı mı?
- [ ] İhlal bildirim hattı kuruldu mu?
- [ ] Aktarım envanterine kayıt yapıldı mı?
