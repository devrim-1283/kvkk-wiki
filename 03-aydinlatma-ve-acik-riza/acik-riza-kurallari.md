---
Doküman / Document: Açık Rıza Kuralları ve Yönetimi / Explicit Consent Rules and Management
Bölüm / Section: 03-aydinlatma-ve-acik-riza
Sahip / Owner: KVKK Sorumlusu / KVKK Officer
Onaylayan / Approved by: Hukuk Müdürü + KVKK Komitesi / Head of Legal + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş (Kurul kararı, mevzuat değişikliği) / Annual + triggered (Board decision, legislative change)
İlgili Mevzuat / Legal Reference: 6698 sayılı KVKK m.3 (tanımlar), m.5 (genel veri işleme şartları), m.6 (özel nitelikli veri), m.10 (aydınlatma) / Law No. 6698 (KVKK) Art. 3 (definitions), Art. 5 (general processing conditions), Art. 6 (special-category data), Art. 10 (disclosure); Aydınlatma Tebliği MADDE 4-5 / Disclosure/Information Notice Communiqué Art. 4-5; Açık Rıza Rehberi (KVKK Kurum yayını) / Authority's Explicit Consent Guide; Elektronik Ticaretin Düzenlenmesi Hakkında Kanun (6563 sayılı) / Law No. 6563 on the Regulation of Electronic Commerce; İYS (İleti Yönetim Sistemi) düzenlemeleri / İYS (Message Management System) regulations
---

## English

# Explicit Consent Rules and Management

## 1. Definition and Three Elements (KVKK Art. 3(1)(a))

KVKK Art. 3(1)(a) defines explicit consent as:

> "Consent on a specific subject, based on information, expressed by free will."

Explicit consent must satisfy three elements simultaneously:

| Element | Description | Typical breach |
|---------|-------------|----------------|
| **1. Specific to a subject** | Consent must be **limited and specific** to the processing activity it relates to | "Blanket consent" — broad expressions such as "for all kinds of processing" |
| **2. Based on information** | The data subject must have been informed before giving consent | Consent without disclosure is invalid |
| **3. Freely expressed** | Not conditioned on receiving a service; free of pressure/coercion | Conditioning the service on consent; "consent" obtained in employee-employer relationship |

The Authority's Explicit Consent Guide reinforces these elements:

> "Explicit consent must enable the data subject to determine the limits, scope, manner and duration of the processing they permit."
> "Explicit consent in this sense must contain the data subject's 'positive expression of will'."

## 2. Connection and Distinction Between Disclosure and Explicit Consent

### 2.1 Two Different Obligations

| Disclosure | Explicit Consent |
|-----------|------------------|
| Mandatory in all cases (KVKK Art. 10) | Only where no other legal ground applies |
| One-way information | Positive expression of will |
| Does not require data subject's approval | Requires data subject's approval |
| Per Communiqué Art. 5 procedure | Three elements must be satisfied |
| Without disclosure, data cannot be processed (Art. 10) | Without explicit consent, data cannot be processed (where consent is the ground) |

### 2.2 Order of Collection

```
1. Disclosure performed       (always)
        │
        ▼
2. Legal ground identified
        │
        ├── Does any clause of Art. 5(2) apply? → Explicit consent NOT REQUIRED
        │
        └── No → Explicit consent obtained     (SEPARATELY from disclosure)
```

> **Critical:** Explicit consent must not be embedded as a "checkbox" inside the disclosure text. The two acts must be visibly separate.

### 2.3 Faulty Implementation Example

**Incorrect:**
```
☐ I have read and accept the information notice and I consent to the
  processing of my data for marketing purposes.
```

**Correct:**
```
☐ I have read and understood the Registration and Contract Information Notice.
                                                    [DISCLOSURE]

──────────────────────────────────────────────────

The following additional processing is OPTIONAL. You do not need to tick
these boxes to receive our services.

☐ Marketing Explicit Consent: I consent to the processing of my data for
  marketing, campaign and product-promotion communication.
  (Information notice: INF-MKT-01)

☐ Profiling Explicit Consent: I consent to the analysis of my purchase
  history by automated systems to provide personalised offers.
  (Information notice: INF-MKT-02)
```

## 3. Prohibition of Blanket Consent

Authority's Explicit Consent Guide:

> "General consents that are not limited to a specific subject and not limited to the relevant transaction are deemed 'blanket consents' and considered legally invalid."

**Examples of blanket consent (invalid):**
- "I consent for any commercial transaction."
- "I authorise the processing of my data."
- "I approve the use of my data for all the company's activities."

**Valid explicit consent:**
- One specific purpose + one specific data category.
- If multiple purposes exist, consent is collected **per category, separately**.

## 4. Prohibition of Consent as a Condition for Receiving Service

The "free will" element of explicit consent requires that consent must not be **mandatory** for receiving the service.

| Scenario | Validity |
|----------|----------|
| Telephone is required for e-commerce registration (contract performance) | Required for the contract, Art. 5(2)/c — no consent collected |
| E-commerce registration requires marketing consent | **Invalid** — violates free will |
| Registration form will not proceed without ticking marketing consent | **Invalid** |
| Marketing consent optional (default off), no impact on service | **Valid** |

> Board decisions criticise this practice expressly. Consents for marketing, profiling, third-party sharing must be optional, defaulted to **off**, and individually selectable.

## 5. Withdrawal of Explicit Consent

Authority's Explicit Consent Guide:

> "Because giving explicit consent is a strictly personal right, the consent given may be withdrawn."
> "As withdrawal has prospective effect, all activities carried out on the basis of explicit consent must be discontinued by the controller from the moment the withdrawal statement reaches it."

### 5.1 Operational Requirements

- The withdrawal channel must be **as easy** as the channel used to give consent.
- Withdrawal must be accepted via different channels (user panel, e-mail, call center, etc.).
- Processing must be **discontinued immediately** at the moment of withdrawal.
- Processing carried out before withdrawal does not become unlawful but is discontinued going forward.

### 5.2 Withdrawal Logging Mechanism

| Field | Record |
|-------|--------|
| User identity | ID, name-surname |
| Withdrawal date-time | Full timestamp |
| Withdrawal channel | Web, e-mail, call, KEP |
| Type of consent withdrawn | Marketing / Profiling / Third-party sharing / Cross-border |
| Action record | Processing stopped (system log) |
| Confirmation e-mail sent? | Y/N |

## 6. Children's Data Regime

KVKK Art. 3 does not separately define "child"; however, under Turkish Civil Code Art. 11, a person below **18 years** is a child. Authority for explicit consent:

| Situation | Approach |
|-----------|----------|
| Data of a child under 18 | **Parent/legal guardian's** explicit consent |
| Emancipated minor (TCK Art. 12) | Their own consent may exceptionally be valid; due to legal uncertainty parental consent is recommended |
| Age verification | System-side age-verification mechanism |

Operational requirements:
- "Are you under 18?" question on the form
- Parent/legal-guardian identity and consent if under-age
- Default-off setting against processing children's data in e-commerce and marketing
- Additional sensitivity for child-targeted marketing content

> Sectoral legislation (e.g., child protection, age classification of games) may impose additional limits; a legislative review must be conducted.

## 7. Consent-Collection Channels

### 7.1 Written

- Paper form with signature
- Evidence: original signed copy retained in archive

### 7.2 Electronic (Web, Mobile)

- Explicit checkbox (defaulted off)
- Log at submit
- Evidence:
  - User identity (ID, e-mail or registered user token)
  - IP address
  - User-Agent
  - Timestamp (second precision, server UTC)
  - Version of consent text shown
  - Version of disclosure text shown
  - Hash or digital signature (recommended)

### 7.3 Call Center

- Operator reads consent text → data subject's verbal approval
- Evidence: voice recording + "consent obtained" flag in system
- Separate disclosure for the recording

### 7.4 KEP / Secure E-mail

- Document signed with e-signature
- KEP delivery reports + qualified certificate

### 7.5 Mobile — IVR Announcement

- Sequence: disclosure → consent request → DTMF approval
- DTMF approval logged

## 8. Consent Management System (CMP)

In a 500+ employee organisation explicit-consent management cannot be run manually. A CMP (Consent Management Platform) is the system established to collect, store, withdraw and audit consents.

### 8.1 Minimum CMP Requirements

| Requirement | Description |
|-------------|-------------|
| Granular consent | Separate per purpose for marketing, profiling, third-party, cross-border, cookie category, etc. |
| Default off | All optional consents start unticked |
| Consent versioning | Which version of the text was the consent given against |
| Full audit log | Who, when, which text, which channel, which decision |
| Withdrawal flow | User panel + e-mail + call center |
| API integration | Real-time integration with CRM, e-mail system, marketing platform |
| Consent refresh | Re-consent after a period (e.g., 2 years) |
| Cookie management (web CMP) | Turkish-language banner, category-based selection |
| Multi-channel view | Web, mobile, call center, paper — single view |
| Reporting | Consent rates, withdrawal trends, category distribution |

### 8.2 Minimum CMP Data Model

```
ConsentRecord {
  id: UUID
  user_id: string
  user_identifier_type: 'email' | 'phone' | 'customer_id'
  consent_category: 'marketing' | 'profiling' | 'third_party_sharing' | 'cross_border_transfer' | 'cookies_analytics' | 'cookies_advertising' | ...
  consent_status: 'granted' | 'withdrawn'
  consent_text_version: 'INF-MKT-01:1.2'
  related_disclosure_text_version: 'INF-CUS-01:1.0'
  channel: 'web' | 'mobile' | 'call_center' | 'paper' | 'kep' | 'email'
  ip_address: string (web/mobile)
  user_agent: string
  recorded_at: timestamp UTC
  recorded_by: 'system' | 'agent_user_id'
  evidence_hash: SHA-256 (optional but recommended)
  withdrawal_at: timestamp UTC (if any)
  withdrawal_channel: ...
}
```

### 8.3 Cookie Banner (Cookies CMP)

A separate CMP banner is recommended for cookies. In Turkey, in line with the Authority's cookie guide, the following categories have become standard:

| Cookie Category | Consent required? |
|-----------------|-------------------|
| Strictly necessary (session, security, basic functionality) | No — legitimate interest |
| Preference (language, region) | No (depending on scope) |
| Statistics / Analytics | Yes — explicit consent recommended |
| Marketing / Advertising | Yes — explicit consent mandatory |

> A "Reject all" button must be **as easy** as an "Accept all" button. "Only essential" must not be assumed by default.

## 9. Granular (Categorised) Consent

The data subject is given the ability to **select item by item**:

```
You may give explicit consent separately for each of the following:

☐ Marketing communications
   I accept receiving campaign, product-promotion and offer information by
   e-mail, SMS and phone.

☐ Profiling and personalisation
   I accept that my purchase and site-usage history will be analysed to
   provide personalised offers and suggestions.

☐ Sharing with third parties
   I accept the sharing of my data with our business partners for marketing
   purposes.

☐ Cross-border transfer (for marketing analytics)
   I accept the transfer of my data to providers abroad for marketing-
   analytics purposes.

You may make each selection independently and withdraw at any time.
For withdrawal: kvkk@companyname.com.tr
```

## 10. Cases Where Explicit Consent is Not Required (KVKK Art. 5(2) — General Data)

If any of the following clauses applies, explicit consent is not collected; disclosure is still made.

| Clause | Provision | Typical use |
|--------|-----------|-------------|
| a | Expressly provided for in laws | Processing under tax, social-security, AML legislation |
| b | Protection of a person unable to express consent due to actual impossibility | Emergency medical intervention |
| c | Necessity for the conclusion or performance of a contract | Customer registration, order, employee personnel file |
| ç | Fulfilment of a legal obligation | Financial recordkeeping, e-invoicing, reporting obligations |
| d | Made public by the data subject | Limited application; processing must align with the purpose of disclosure |
| e | Establishment, exercise or protection of a right | Litigation, dispute, collection |
| f | Legitimate interest — provided that fundamental rights and freedoms are not harmed | Security, fraud prevention, service quality |

## 11. Special-Category Data and Explicit Consent (KVKK Art. 6)

KVKK Art. 6(2): Special-category personal data may not be processed without the data subject's **explicit consent**.

KVKK Art. 6(3): Special-category data other than health and sexual life may be processed without consent **in cases provided for by law**. Health and sexual-life data may be processed without consent by **persons under a duty of confidentiality** for the protection of public health, preventive medicine, medical diagnosis, treatment and care, and the planning, management and financing of health services.

| Data type | Consent required? | Exceptions |
|-----------|-------------------|-----------|
| Health data | Yes | By persons under a duty of confidentiality for public health, treatment, financing |
| Sexual life | Yes | By persons under a duty of confidentiality for the above purposes |
| Biometric / Genetic | Yes | Cases provided for by law |
| Criminal record | Yes | Cases provided for by law (e.g., recruitment statutes) |
| Philosophical belief, religion, sect | Yes | Cases provided for by law |
| Association/foundation/union membership | Yes | Cases provided for by law |
| Political opinion | Yes | Cases provided for by law |

## 12. Compliance with İYS (Message Management System)

For sending Commercial Electronic Messages (e-mail, SMS, automated calls), Law No. 6563 on the Regulation of Electronic Commerce and the İYS Regulation require:

- **Approval (consent) is mandatory** (considered alongside KVKK explicit consent but arises from a different statute)
- The approval **must be registered** in the Message Management System (https://iys.org.tr)
- The message content must include "right to refuse" information
- Refusal must be easy and **free of charge**

> KVKK consent + İYS approval are **two distinct obligations**. The CMP must track both.

## 13. Consent in the Employee-Employer Relationship

Board decisions consider the "free will" element to be weak in employee-employer relationships. Consent cannot be requested from an employee under pressure. Therefore:

- Employee data should be processed, where possible, under **Art. 5(2)/c (contract performance)**, **Art. 5(2)/ç (legal obligation)** or **Art. 5(2)/f (legitimate interest)**.
- Explicit consent may be obtained for activities not necessary for the employment (e.g., use of a photograph for social-media sharing) and which do not affect service.
- A process design that creates the impression of "I must consent or I will lose my job" produces **invalid consent**.

## 14. Explicit Consent Policy — Operating Principles

1. **Explicit consent is the last resort.** First consider Art. 5(2)/Art. 6(3) clauses; if no clause fits, take consent.
2. **Consent moment = disclosure + separate checkbox.** Never combined into a single click.
3. **Granularity is mandatory.** Separate selection per purpose.
4. **Default off.** No checkbox is pre-ticked.
5. **No service-conditioning.** A user who does not give marketing consent can still purchase the product.
6. **Easy withdrawal.** Same channel + additional channels (e-mail, call, panel).
7. **Full evidence.** Who, when, which text, which channel, IP/log.
8. **Versioning.** When the text changes, re-consent or notify.
9. **Time-limited consent.** Consents inactive for 2 years are refreshed or deleted.
10. **Children's data.** Parental consent + age verification.

## 15. Refusal and Withdrawal — Stopping Processing

If consent is refused or withdrawn:

| Action | Owner | Time |
|--------|-------|------|
| Set "no consent" flag in the relevant system | System | Immediate |
| Remove from marketing lists | Marketing / System | 24 hours |
| Remove from profiling algorithm | Data Science / System | 24 hours |
| Stop sharing with third parties | System + supplier | 7 days (contractual) |
| Erase consent-based data | System | Per policy |
| Confirmation e-mail | CMP | Immediate |

## 16. Frequently Asked Questions

**Q1. "Can a customer registration form rely on a single 'I have read the KVKK information notice' checkbox?"**
If processing is based on contract performance and explicit consent is not required, yes — but that is acknowledgement of disclosure, not consent. Operations requiring consent (e.g., marketing) need a separate checkbox.

**Q2. "Is a 'Strictly necessary cookies only' button mandatory on the cookie banner?"**
According to Authority guidance, the user's ability to refuse analytics/marketing cookies must be **as easy** as the ability to accept. Designs that present only "Accept all" are criticised by the Board.

**Q3. "Can we obtain explicit consent from an employee?"**
An employee's consent often does not satisfy the "free will" element. Activities required for employment run under Art. 5(2)/c, ç, f. Explicit consent may be taken for activities that are not necessary for performing the work and where acceptance/refusal does not lead to any adverse outcome for the employee (e.g., sharing a photograph in an internal newsletter).

**Q4. "Within what time should a customer who withdraws consent be removed from the contact list?"**
"Immediate" is the ideal; in practice, where the CMP-CRM is not synchronous, **24 hours** is the upper bound. This figure is the operational interpretation of "without delay" in Board decisions.

**Q5. "Can the explicit consent text be presented in English?"**
It must be in a language the data subject can understand. Turkish for Turkish citizens, English for foreign visitors. Where the audience is mixed, language options are provided. The plain-language requirement (Communiqué Art. 5/ğ) applies regardless of the language.

**Q6. "Is İYS approval bundled with KVKK consent?"**
İYS approval falls under Law No. 6563; KVKK consent under Law No. 6698. They may operationally be collected together; technically, however, they are two separate records. The CMP must track both.

## 17. Checklist (Explicit Consent)

- [ ] Legal ground analysis performed; consent considered as last resort
- [ ] Information notice presented **SEPARATELY** from the consent screen
- [ ] Consent checkboxes default off
- [ ] Granular — separate selection per purpose
- [ ] Service is not conditional on consent
- [ ] Withdrawal channel easy and equally accessible
- [ ] CMP established — record, audit log, version
- [ ] For children's data: age verification + parental consent
- [ ] Employee consent really free (PIA check)
- [ ] İYS approval recorded separately
- [ ] Cookie banner has "Reject all" with equal ease
- [ ] Consent versioning enabled
- [ ] Time-limited refresh policy in place (e.g., 2 years)
- [ ] SLA for stopping processing after withdrawal defined (max 24 hours)

## 18. Annexes

- Information Notice Template: [aydinlatma-metni-sablonu.md](./aydinlatma-metni-sablonu.md)
- Information Notice Checklist: [aydinlatma-metni-checklist.md](./aydinlatma-metni-checklist.md)
- Scenario Examples: [ornekler.md](./ornekler.md)

---

## Türkçe

# Açık Rıza Kuralları ve Yönetimi

## 1. Tanım ve Üç Unsur (KVKK m.3/1/a)

KVKK m.3/1/a'da açık rıza şu şekilde tanımlanmıştır:

> "Belirli bir konuya ilişkin, bilgilendirilmeye dayanan ve özgür iradeyle açıklanan rıza."

Açık rıza üç temel unsuru bir arada barındırmalıdır:

| Unsur | Açıklama | Tipik ihlal |
|-------|---------|------------|
| **1. Belirli bir konuya ilişkin** | Rıza, hangi işleme faaliyetine dair olduğu konusunda **sınırlı ve belirli** olmalıdır | "Battaniye rıza" — "her türlü işleme faaliyeti için" gibi geniş ifadeler |
| **2. Bilgilendirmeye dayalı** | Rıza vermeden önce ilgili kişi aydınlatılmış olmalıdır | Aydınlatmasız rıza geçersiz |
| **3. Özgür iradeyle açıklanan** | Hizmet alma şartına bağlanmamış, baskı/zorlama içermeyen | Hizmeti almayı rızaya bağlama; çalışan-işveren ilişkisinde alınan "rıza" |

KVKK Açık Rıza Rehberi (Kurum yayını) bu unsurları şöyle pekiştirir:

> "Açık rıza, ilgili kişinin, işlenmesine izin verdiği verinin sınırlarını, kapsamını, gerçekleştirilme biçimini ve süresini de belirlemesini sağlayacaktır."
> "Açık rızanın bu anlamda, rıza veren kişinin 'olumlu irade beyanı'nı içermesi gerekmektedir."

## 2. Açık Rıza ile Aydınlatma — Bağlantı ve Ayrım

### 2.1 İki Farklı Yükümlülük

| Aydınlatma | Açık Rıza |
|-----------|-----------|
| Her halde zorunlu (KVKK m.10) | Sadece başka hukuki sebep yoksa |
| Tek yönlü bilgilendirme | Olumlu irade beyanı |
| İlgili kişinin onayını gerektirmez | İlgili kişinin onayını gerektirir |
| Tebliğ M.5 usulüne göre | Üç unsur sağlanmalı |
| Aydınlatma yapılmadığında veri işlenemez (m.10) | Açık rıza yoksa veri işlenemez (rıza dayanak ise) |

### 2.2 Birlikte Alınma Düzeni

```
1. Aydınlatma yapılır       (her halde)
        │
        ▼
2. Hukuki sebep tespit edilir
        │
        ├── m.5(2) bentlerinden biri var mı? → Açık rıza ARANMAZ
        │
        └── Yok → Açık rıza alınır     (aydınlatmadan AYRI)
```

> **Kritik:** Açık rıza aydınlatma metninin içine "checkbox" olarak gömülmemelidir. İki ayrı eylem olduğu açıkça gösterilmelidir.

### 2.3 Hatalı Uygulama Örneği

**Yanlış:**
```
☐ Aydınlatma metnini okudum, kabul ediyorum ve verilerimin
  pazarlama amaçlı kullanılmasına onay veriyorum.
```

**Doğru:**
```
☐ Kayıt ve Sözleşme Aydınlatma Metni'ni okudum, anladım.
                                                    [BİLGİLENDİRME]

──────────────────────────────────────────────────

Aşağıdaki ek işlemler için açık rızanız zorunlu DEĞİLDİR.
Hizmeti almak için bu kutuların işaretlenmesi gerekmemektedir.

☐ Pazarlama Açık Rızası: Verilerimin pazarlama, kampanya ve
  ürün tanıtım iletişimi amacıyla işlenmesine açık rıza
  veriyorum. (Aydınlatma metni: AYD-PAZ-01)

☐ Profilleme Açık Rızası: Otomatik sistemlerle alışveriş
  geçmişimin analiz edilerek bana özel teklifler sunulmasına
  açık rıza veriyorum. (Aydınlatma metni: AYD-PAZ-02)
```

## 3. Battaniye Rıza Yasağı

KVKK Açık Rıza Rehberi:

> "Belirli bir konu ile sınırlandırılmayan ve ilgili işlemle sınırlı olmayan genel nitelikteki açık rızalar 'battaniye rızalar' olarak kabul edilmekte ve hukuken geçersiz sayılmaktadır."

**Battaniye rıza örnekleri (geçersiz):**
- "Her türlü ticari işlem için açık rıza veriyorum."
- "Verilerin işlenmesi konusunda izin veriyorum."
- "Şirketin tüm faaliyetlerinde verilerimin kullanılmasına onay veriyorum."

**Geçerli açık rıza:**
- Tek bir belirli amaç + tek bir belirli veri kategorisi.
- Birden fazla amaç varsa **kategori bazlı ayrı rıza** alınır.

## 4. Hizmet Alma Şartı Olarak Rıza Yasağı

Açık rızanın "özgür irade" unsuru, rızanın hizmet alma için **zorunlu** kılınmamasını gerektirir.

| Senaryo | Geçerlilik |
|---------|-----------|
| E-ticaret kayıt için telefon zorunlu (sözleşme ifası) | Sözleşme için zorunlu, m.5/2/c — rıza alınmaz |
| E-ticaret kayıt için pazarlama rızası zorunlu kılınmış | **Geçersiz** — özgür irade ihlali |
| Kayıt formu, pazarlama rızasını işaretlemeden devam ettirmiyor | **Geçersiz** |
| Pazarlama rızası optional (varsayılan kapalı), hizmete etki etmiyor | **Geçerli** |

> Kurul kararlarında bu uygulamaya açık eleştiri vardır. Pazarlama, profilleme, üçüncü kişi ile paylaşım rızaları opsiyonel olmalı; varsayılan **kapalı** durumda gelmeli; tek tek seçilebilir olmalı.

## 5. Açık Rıza Geri Alma

KVKK Açık Rıza Rehberi:

> "Açık rıza vermek, kişiye sıkı sıkıya bağlı bir hak olduğundan, verilen açık rıza geri alınabilir."
> "Geri alma işlemi ileriye yönelik sonuç doğuracağından, açık rızaya dayalı olarak gerçekleştirilen tüm faaliyetler geri alma beyanının veri sorumlusuna ulaştığı andan itibaren veri sorumlusu tarafından durdurulmalıdır."

### 5.1 Operasyonel Gereksinimler

- Geri alma kanalı, rıza alma kanalıyla **eşit kolaylıkta** olmalıdır.
- Kullanıcı paneli, e-posta, çağrı merkezi gibi farklı kanallar üzerinden geri alma kabul edilmelidir.
- Geri alma anından itibaren işleme **derhal durdurulur**.
- Geri alma öncesi yapılmış işlemler hukuka aykırı olmaz; ancak ileriye dönük durdurulur.

### 5.2 Geri Alma Kayıt Mekanizması

| Alan | Kayıt |
|------|-------|
| Kullanıcı kimliği | ID, ad-soyad |
| Geri alma tarihi-saati | Tam zaman damgası |
| Geri alma kanalı | Web, e-posta, çağrı, KEP |
| Geri alınan rıza türü | Pazarlama / Profilleme / 3. kişi paylaşım / Yurt dışı |
| Aksiyon kaydı | İşleme durduruldu (sistem logu) |
| Onay e-postası gönderildi mi? | E/H |

## 6. Çocuk Verisi Rejimi

KVKK m.3'te "çocuk" ayrı tanımlanmamıştır; ancak Türk Medeni Kanunu m.11 uyarınca **18 yaş** altı kişi çocuk kabul edilir. Açık rıza yetkisi:

| Durum | Yaklaşım |
|-------|---------|
| 18 yaş altı çocuk verisi | **Veli/yasal temsilci** açık rızası |
| 18 yaş altı ergin (m.12) | İstisnai olarak kendi rızası geçerli sayılabilir; ancak hukuki belirsizliği nedeniyle veli rızası önerilir |
| Yaş doğrulaması | Sistem tarafında yaş doğrulama mekanizması |

Operasyonel gereklilikler:
- Form üzerinde "18 yaşından küçük müsünüz?" sorusu
- Küçükse veli/yasal temsilci kimliği ve rızası
- E-ticaret ve pazarlamada çocuk verisi işlenmemesini varsayılan olarak ayarlama
- Çocuk hedefli pazarlama içeriği için ek hassasiyet

> Sektörel mevzuat (örn. çocuk koruma, oyun yaşı sınıflandırması) farklı sınırlamalar getirebilir; mevzuat değerlendirmesi yapılmalıdır.

## 7. Açık Rıza Alma Kanalları

### 7.1 Yazılı

- Kağıt formda imza ile
- İspat: imzalı orijinal kopya, arşivde saklama

### 7.2 Elektronik (Web, Mobil)

- Açık checkbox (varsayılan kapalı)
- Submit anında log
- İspat:
  - Kullanıcı kimliği (ID, e-posta veya kayıtlı kullanıcı tokenı)
  - IP adresi
  - User-Agent
  - Zaman damgası (saniye hassasiyetinde, sunucu UTC)
  - Gösterilen rıza metni versiyonu
  - Gösterilen aydınlatma metni versiyonu
  - Hash veya digital signature (önerilir)

### 7.3 Çağrı Merkezi

- Operatör tarafından seslendirilen rıza metni → ilgili kişiden sözlü onay
- İspat: ses kaydı + sistem üzerinde "rıza aldı" işareti
- Kayıt için ayrı bilgilendirme yapılır

### 7.4 KEP / Güvenli E-posta

- E-imza ile imzalı belge
- KEP teslim raporları + nitelikli sertifika

### 7.5 Mobil — IVR Anonsu

- Anons sırası: aydınlatma → açık rıza talebi → tuş ile onay
- Tuş ile onay sistem logunda saklanır

## 8. Açık Rıza Yönetim Sistemi (CMP — Consent Management Platform)

500+ çalışanlı bir kuruluşta açık rıza yönetimi manuel yürütülemez. CMP, rızaları toplama, saklama, geri alma ve audit etme amacıyla kurulan sistemdir.

### 8.1 CMP Asgari Gereksinimleri

| Gereksinim | Açıklama |
|-----------|---------|
| Granüler rıza | Pazarlama, profilleme, 3. kişi, yurt dışı, çerez kategorisi gibi her amaç için ayrı |
| Varsayılan kapalı | Tüm opsiyonel rızalar başlangıçta işaretsiz |
| Rıza versiyonlama | Hangi versiyon metnine rıza verildi |
| Tam audit log | Kim, ne zaman, hangi metin, hangi kanal, hangi karar |
| Geri alma akışı | Kullanıcı paneli + e-posta + çağrı merkezi |
| API entegrasyonu | CRM, e-posta sistemi, pazarlama platformu ile gerçek zamanlı |
| Rıza tazeleme | Belirli süre sonra (örn. 2 yıl) yeniden rıza isteme |
| Çerez yönetimi (CMP web) | Türkçe banner, kategori bazlı seçim |
| Çoklu kanal görünümü | Web, mobil, çağrı merkezi, kağıt — tek görünüm |
| Raporlama | Rıza oranları, geri alma eğilimleri, kategori dağılımı |

### 8.2 CMP Asgari Veri Modeli

```
ConsentRecord {
  id: UUID
  user_id: string
  user_identifier_type: 'email' | 'phone' | 'customer_id'
  consent_category: 'marketing' | 'profiling' | 'third_party_sharing' | 'cross_border_transfer' | 'cookies_analytics' | 'cookies_advertising' | ...
  consent_status: 'granted' | 'withdrawn'
  consent_text_version: 'AYD-PAZ-01:1.2'
  related_disclosure_text_version: 'AYD-MUS-01:1.0'
  channel: 'web' | 'mobile' | 'call_center' | 'paper' | 'kep' | 'email'
  ip_address: string (web/mobile)
  user_agent: string
  recorded_at: timestamp UTC
  recorded_by: 'system' | 'agent_user_id'
  evidence_hash: SHA-256 (opsiyonel ama önerilir)
  withdrawal_at: timestamp UTC (varsa)
  withdrawal_channel: ...
}
```

### 8.3 Çerez Bandı (Cookies CMP)

Çerez kullanımı için ayrı bir CMP bandı önerilir. Türkiye'de Kurum'un çerez rehberi paralelinde aşağıdaki kategoriler standart hale gelmiştir:

| Çerez Kategorisi | Rıza Gerekli mi? |
|------------------|------------------|
| Zorunlu (oturum, güvenlik, fonksiyonel temel) | Hayır — meşru menfaat |
| Tercih (dil, bölge) | Hayır (ya da kapsama göre) |
| İstatistik / Analitik | Evet — açık rıza önerilir |
| Pazarlama / Reklam | Evet — açık rıza zorunlu |

> "Tüm çerezleri kabul et" tek butonu ile birlikte "Tümünü reddet" butonu **eşit kolaylıkta** olmalıdır. "Sadece zorunlu" varsayılan kabul edilmemelidir.

## 9. Kategorize Rıza (Granüler Rıza)

İlgili kişiye **tek tek seçim** yapma imkanı verilir:

```
Aşağıdaki ek işlemler için ayrı ayrı açık rıza verebilirsiniz:

☐ Pazarlama iletişimi
   Mailing, SMS ve telefon yoluyla kampanya, ürün tanıtım ve fırsat
   bilgileri almayı kabul ediyorum.

☐ Profilleme ve kişiselleştirme
   Alışveriş ve site kullanım geçmişimin analiz edilerek bana özel
   öneri ve tekliflerin sunulmasını kabul ediyorum.

☐ Üçüncü kişi ile paylaşım
   Verilerimin pazarlama amacıyla iş ortaklarımızla paylaşılmasını
   kabul ediyorum.

☐ Yurt dışı aktarım (pazarlama analitiği için)
   Pazarlama analitiği amacıyla verilerimin yurt dışındaki
   sağlayıcılara aktarılmasını kabul ediyorum.

Her seçimi ayrı yapabilir, istediğiniz zaman geri alabilirsiniz.
Geri alma için: kvkk@sirketadi.com.tr
```

## 10. Açık Rızanın Aranmadığı Durumlar (KVKK m.5/2 — Genel Veri)

Aşağıdaki bentlerden birinin varlığında açık rıza alınmaz; ancak aydınlatma yapılır.

| Bent | Hüküm | Tipik kullanım |
|------|-------|---------------|
| a | Kanunlarda açıkça öngörülmesi | Vergi, SGK, AML mevzuatı kapsamında işleme |
| b | Fiili imkansızlık halinde rızasını açıklayamayacak kişinin korunması | Acil tıbbi müdahale |
| c | Sözleşmenin kurulması veya ifası için zorunluluk | Müşteri kaydı, sipariş, çalışan özlük |
| ç | Hukuki yükümlülüğün yerine getirilmesi | Mali kayıt, e-fatura, raporlama yükümlülüğü |
| d | İlgili kişinin alenileştirmiş olması | Sınırlı uygulama; alenileştirme amacına uygun olmalı |
| e | Bir hakkın tesisi, kullanılması veya korunması | Dava, ihtilaf, tahsilat |
| f | Meşru menfaat — temel hak ve özgürlüklere zarar vermemek kaydıyla | Güvenlik, dolandırıcılık önleme, hizmet kalitesi |

## 11. Özel Nitelikli Veri ve Açık Rıza (KVKK m.6)

KVKK m.6(2): Özel nitelikli kişisel veriler ilgili kişinin **açık rızası** olmaksızın işlenemez.

KVKK m.6(3): Sağlık ve cinsel hayat dışındaki özel nitelikli veriler **kanunlarda öngörülen hallerde** rızasız işlenebilir. Sağlık ve cinsel hayat verileri ise **sır saklama yükümlülüğü altındaki kişiler** tarafından kamu sağlığının korunması, koruyucu hekimlik, tıbbi teşhis, tedavi ve bakım, sağlık hizmetlerinin planlanması ve yönetimi amacıyla rızasız işlenebilir.

| Veri Türü | Rıza Gerekli mi? | İstisnalar |
|-----------|------------------|-----------|
| Sağlık verisi | Evet | Sır saklayan kişilerce kamu sağlığı, tedavi, finansman amaçlı |
| Cinsel hayat | Evet | Sır saklayan kişilerce yukarıdaki amaçlar |
| Biyometrik / Genetik | Evet | Kanunlarda öngörülen haller |
| Ceza mahkumiyeti | Evet | Kanunlarda öngörülen haller (örn. işe alımda mevzuat) |
| Felsefi inanç, din, mezhep | Evet | Kanunlarda öngörülen haller |
| Dernek/vakıf/sendika üyeliği | Evet | Kanunlarda öngörülen haller |
| Siyasi düşünce | Evet | Kanunlarda öngörülen haller |

## 12. İYS (İleti Yönetim Sistemi) Uyumu

Ticari Elektronik İleti gönderimi (e-posta, SMS, otomatik arama) için 6563 sayılı Elektronik Ticaretin Düzenlenmesi Hakkında Kanun ve İYS Yönetmeliği uyarınca:

- **Onay (rıza) zorunludur** (KVKK açık rızası ile bütünleşik düşünülür ancak ayrı kanunlardan kaynaklanır)
- Onay İleti Yönetim Sistemi'ne (https://iys.org.tr) **kaydedilmelidir**
- Mesaj içeriğinde "ret hakkı" bilgisi yer almalıdır
- Ret hakkı kullanımı kolay ve **ücretsiz** olmalıdır

> KVKK rızası + İYS onayı **iki ayrı yükümlülüktür**. CMP, her ikisini de takip etmelidir.

## 13. Çalışan-İşveren İlişkisinde Rıza

Kurul kararlarında çalışan-işveren ilişkisinde "özgür irade" unsuru zayıf değerlendirilmektedir. Çalışana baskı altında rıza istenemez. Bu nedenle:

- Çalışan verisi mümkün olduğunca **m.5/2/c (sözleşme ifası)** veya **m.5/2/ç (hukuki yükümlülük)** veya **m.5/2/f (meşru menfaat)** altında işlenmelidir.
- Açık rıza, işin gereği olmayan ek faaliyetler için (örn. sosyal medya paylaşımı için fotoğraf kullanımı) ve hizmete etki etmeyecek şekilde alınabilir.
- "Açık rıza vermek zorundayım, yoksa işten atılırım" hissini doğuracak süreç tasarımı **geçersiz rıza üretir**.

## 14. Açık Rıza Politikası — Operasyonel İlkeler

1. **Açık rıza son çaredir.** Önce m.5(2)/m.6(3) bentleri değerlendirilir; uygun bent yoksa rıza alınır.
2. **Rıza alma anı = aydınlatma + ayrı checkbox.** Tek tıkla birleştirilmez.
3. **Granülerlik zorunludur.** Her amaç için ayrı seçim.
4. **Varsayılan kapalı.** Hiçbir checkbox başlangıçta işaretli olmaz.
5. **Hizmet alma şartı yapılmaz.** Pazarlama rızası vermek istemeyen, ürünü almaya devam edebilir.
6. **Geri alma kolay.** Aynı kanal + ek kanallar (e-posta, çağrı, panel).
7. **Tam ispat.** Kim, ne zaman, hangi metin, hangi kanal, IP/log.
8. **Versiyonlama.** Metin değişirse yeni rıza istenir veya bilgilendirme yapılır.
9. **Süreli rıza.** 2 yıl etkileşim olmayan rızalar tazelenir veya silinir.
10. **Çocuk verisi.** Veli rızası + yaş doğrulama.

## 15. Açık Rıza Reddi ve İşleme Sona Erdirme

Rıza reddedildiyse veya geri alındıysa:

| Aksiyon | Sorumlu | Süre |
|---------|---------|------|
| İlgili sistemde "rıza yok" bayrağı set edilir | Sistem | Anlık |
| Pazarlama listelerinden çıkarma | Pazarlama / Sistem | 24 saat |
| Profilleme algoritmasından çıkarma | Veri Bilim / Sistem | 24 saat |
| 3. kişi paylaşımının durdurulması | Sistem + tedarikçi | 7 gün (sözleşme şartı) |
| Açık rızaya bağlı verilerin silinmesi | Sistem | Politikada belirtilen süre |
| Onay e-postası | CMP | Anlık |

## 16. Sıkça Sorulan Sorular

**S1. "Müşteri kayıt formunda 'KVKK aydınlatma metnini okudum' tek checkbox koyabilir miyiz?"**
Sözleşme ifası için işleme yapılıyor ve açık rıza gerekmiyorsa evet — ancak bu rıza değil, aydınlatma onayıdır. Pazarlama gibi rıza gerektiren işlemler için ayrı checkbox gereklidir.

**S2. "Çerez bandında 'Sadece zorunlu çerezler' butonu zorunlu mu?"**
Kurul rehberlerine göre kullanıcının analitik/pazarlama çerezlerini reddetme imkanı, kabul etmeyle eşit kolaylıkta sunulmalıdır. "Tümünü kabul et" tek başına bulunan tasarımlar Kurul tarafından eleştirilmektedir.

**S3. "Çalışandan açık rıza alabilir miyiz?"**
Çalışanın rızası "özgür irade" şartını çoğu zaman taşımaz. İşin gereği olan işlemler m.5/2/c, ç, f bentleri altında yürütülür. Açık rıza, işin yürütülmesi için zorunlu olmayan, kabul/red kararı çalışana herhangi bir olumsuz sonuç doğurmayacak işlemler için alınabilir (örn. iç bültende fotoğraf paylaşımı).

**S4. "Rızayı geri alan müşteri ne kadar sürede iletişim listesinden çıkarılmalı?"**
"Anlık" idealdir; pratikte CMP-CRM senkron çalışmıyorsa **24 saat** üst sınır kabul edilir. Bu süre Kurul kararlarında "derhal" ifadesinin operasyonel yorumudur.

**S5. "Açık rıza metni İngilizce sunulabilir mi?"**
İlgili kişinin anlayabileceği dilde olmalıdır. Türk vatandaşına Türkçe, yabancı misafire İngilizce. Karma müşteri grubu varsa dil seçenekleri sunulur. Sade dil zorunluluğu (Tebliğ M.5/ğ) hangi dilde olursa olsun geçerlidir.

**S6. "İYS onayı KVKK rızası ile bütünleşik mi?"**
İYS onayı 6563 sayılı Kanun kapsamındadır; KVKK rızası 6698 sayılı Kanun kapsamındadır. Operasyonel olarak ortak alınabilir; ancak teknik olarak iki ayrı kayıt-arşivdir. CMP her ikisini takip etmelidir.

## 17. Kontrol Listesi (Açık Rıza)

- [ ] Hukuki sebep tespiti yapılmış, rıza son çare olarak değerlendirilmiş
- [ ] Aydınlatma metni rıza talep ekranından **AYRI** sunuluyor
- [ ] Rıza checkbox'ları varsayılan kapalı
- [ ] Granüler — her amaç için ayrı seçim
- [ ] Hizmet alma rıza şartına bağlanmamış
- [ ] Geri alma kanalı kolay ve eşit erişimli
- [ ] CMP kuruldu — kayıt, audit log, versiyon
- [ ] Çocuk verisi için yaş doğrulama + veli rızası
- [ ] Çalışan rızası gerçekten özgür iradeyle mi (PIA kontrolü)
- [ ] İYS onayı ayrı kaydediliyor
- [ ] Çerez bandı "tümünü reddet" eşit kolaylıkta
- [ ] Rıza versiyonlama aktif
- [ ] Süreli tazeleme politikası tanımlı (örn. 2 yıl)
- [ ] Geri alma sonrası işleme durdurma SLA'sı tanımlı (max 24 saat)

## 18. Ekler

- Aydınlatma Şablonu: [aydinlatma-metni-sablonu.md](./aydinlatma-metni-sablonu.md)
- Aydınlatma Kontrol Listesi: [aydinlatma-metni-checklist.md](./aydinlatma-metni-checklist.md)
- Senaryo Örnekleri: [ornekler.md](./ornekler.md)
