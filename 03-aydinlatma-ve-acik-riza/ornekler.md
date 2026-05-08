---
Doküman / Document: Senaryo Bazlı Aydınlatma ve Açık Rıza Örnekleri / Scenario-Based Disclosure and Explicit Consent Examples
Bölüm / Section: 03-aydinlatma-ve-acik-riza
Sahip / Owner: KVKK Sorumlusu / KVKK Officer
Onaylayan / Approved by: Hukuk Müdürü + KVKK Komitesi / Head of Legal + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş / Annual + triggered
İlgili Mevzuat / Legal Reference: 6698 sayılı KVKK m.5, m.6, m.9, m.10, m.11 / Law No. 6698 (KVKK) Art. 5, 6, 9, 10, 11; Aydınlatma Tebliği MADDE 4-5 / Disclosure/Information Notice Communiqué Art. 4-5; 6563 sayılı Elektronik Ticaretin Düzenlenmesi Hakkında Kanun ve İYS Yönetmeliği / Law No. 6563 on the Regulation of Electronic Commerce and the İYS Regulation; ilgili sektör mevzuatı / relevant sectoral legislation
---

## English

# Scenario-Based Disclosure and Explicit Consent Examples

This document shows the practical translation of disclosure and explicit-consent practice for commonly encountered scenarios. For each scenario:
1. **Context** — operational situation
2. **Legal analysis** — which ground, is consent required
3. **Information notice** — abbreviated example for the appropriate channel
4. **Consent screen / flow** — if any
5. **Evidence and records** — what is logged and how
6. **Common errors**

---

## Scenario 1 — Customer E-commerce Registration + Optional Marketing Consent

### Context
B2C e-commerce site, user registration form. Order placement and marketing communication are separate purposes.

### Legal Analysis
- **Account creation + contract:** KVKK Art. 5(2)/c (necessity for contract performance)
- **Order tracking, invoicing:** Art. 5(2)/c, Art. 5(2)/ç (under Tax Procedure Law (VUK))
- **Marketing (e-mail, SMS, push):** Explicit consent + İYS approval mandatory
- **Profiling (recommendations based on purchase analysis):** Explicit consent
- **Sharing for marketing with third parties:** Explicit consent

### Form Design

```
[Page 1 — Membership Information]
Full name: [____________]
E-mail:    [____________]
Phone:     [____________]
Password:  [____________]

→ "Next" button

[Page 2 — Information and Approval]

MANDATORY
☐ I have read and understood the "Membership Information Notice" (INF-CUS-01).
☐ I have read and accept the Distance Sales Pre-Information Form.
☐ I have read and accept the Membership Agreement.

OPTIONAL — EXPLICIT CONSENT
The choices below are entirely up to you. Not giving them does not prevent
you from receiving our service.

☐ Marketing Explicit Consent
   I accept receiving e-mail, SMS and push notifications about the Company's
   open and closed campaigns, discounts and new product introductions.
   (Information notice: INF-MKT-01) (İYS: e-mail + SMS)

☐ Personalisation / Profiling Explicit Consent
   I accept the analysis of my behaviour on the site and my purchase history
   to receive personalised recommendations.
   (Information notice: INF-MKT-02)

☐ Sharing With Business Partners for Marketing
   I accept sharing of marketing-related data with our business partners.
   (Information notice: INF-MKT-03)

[Sign Up]
```

### Evidence and Records

CMP record:
```
{
  "user_id": "U-394827",
  "consent": [
    { "category": "marketing_email_sms",   "status": "granted",   "version": "INF-MKT-01:1.2" },
    { "category": "profiling",             "status": "withdrawn", "version": "INF-MKT-02:1.0" },
    { "category": "third_party_sharing",   "status": "granted",   "version": "INF-MKT-03:1.1" }
  ],
  "channel": "web",
  "ip": "85.x.x.x",
  "user_agent": "Mozilla/5.0 ...",
  "recorded_at": "2026-05-08T13:24:10Z",
  "iys_record_id": "IYS-0000-0000"
}
```

### Common Errors
- Conditioning account creation on marketing consent
- Combining disclosure and all consents into a single checkbox
- "Tick all" defaulted on
- No withdrawal channel

---

## Scenario 2 — Job Candidate Onboarding → Transition After Hire

### Context
Recruitment process → personnel-file process after start of employment. **Two different processes → two different information notices.**

### Legal Analysis
- **Candidate evaluation:** Art. 5(2)/c (pre-contract measures), Art. 5(2)/f (legitimate interest)
- **Talent-pool retention (if not hired):** Explicit consent
- **Personnel file after hire:** Art. 5(2)/c (contract performance), Art. 5(2)/ç (Labour Law, SGK), Art. 6(3) (health data by persons under a duty of confidentiality)

### Disclosure Flow

1. At application: **INF-HR-01 (Recruitment)** is shown.
2. On hire: **INF-HR-02 (Personnel File)** is delivered separately and a signed copy taken.
3. For medical reports: **INF-HR-07 (OHS)** + supplementary disclosure.
4. If talent-pool retention is requested, separate explicit consent.

### Talent-Pool Explicit Consent (Above the Form)

```
☐ In the event that I am not hired as a result of evaluation of my
  application, I consent to the retention of my application data by the
  Company for up to 2 years to be evaluated for suitable future positions.
  (INF-HR-01)

  I may withdraw this consent at any time by contacting
  hr-kvkk@companyname.com.tr.
```

### Common Errors
- A single notice failing to distinguish candidate vs. employee
- No separate disclosure for OHS health data
- Talent-pool retention without consent
- Creating the impression that the employee "must" consent

---

## Scenario 3 — CCTV: Visitor Sign + Detailed Information Notice

### Context
The company building has CCTV. All entrances are monitored; toilets, changing rooms etc. are out of scope.

### Legal Analysis
- **Legal ground:** Art. 5(2)/f (legitimate interest — building security) + Art. 5(2)/ç (OHS legislation)
- **Explicit consent not required**

### Sign Text (Building Entrance — Visible Place)

```
┌──────────────────────────────────────────────────┐
│ [Company logo]                                    │
│                                                   │
│ NOTICE — CLOSED-CIRCUIT CAMERA SYSTEM             │
│                                                   │
│ This area is monitored by CCTV for security       │
│ purposes.                                         │
│                                                   │
│ Data Controller: [Full Company Title]             │
│ Purpose: Building and perimeter security,         │
│   entry/exit records under OHS                    │
│ Legal Ground: KVKK Art. 5(2)/f and 5(2)/ç         │
│                                                   │
│ Detailed information notice:                      │
│ www.companyname.com.tr/kvkk/cctv                  │
│ [QR CODE]                                         │
│                                                   │
│ Retention: 30 days                                │
│ Application: kvkk@companyname.com.tr              │
└──────────────────────────────────────────────────┘
```

### Detail to Add to the Long-form Notice

```
The cameras are positioned in common areas, entrances/exits, corridors,
the parking lot, and main security points. They do not cover toilets,
changing rooms, prayer rooms, or other private areas. There are [n] cameras
in total. Only authorised Security personnel access the recordings.
Recordings are rotated every 30 days unless an incident is recorded.
```

### Common Errors
- Relying on the sign alone; no detail on the website
- Cameras placed in private areas
- Unjustified retention longer than 30 days
- Excessive access rights to recordings

---

## Scenario 4 — Call Center Voice Recording Announcement (Full Text)

### Context
Inbound and outbound call center. All conversations are recorded.

### Legal Analysis
- **Inbound (under customer contract):** Art. 5(2)/c
- **Inbound (general support, service quality):** Art. 5(2)/f
- **Outbound (marketing):** Explicit consent + İYS approval
- **Use for training purposes:** Additional legitimate-interest assessment required

### Inbound — IVR Announcement (Start of Call)

```
"Welcome to [Company name].

Your call is being recorded for the purposes of monitoring service quality,
recording your requests, and performing our contract, on the basis of KVKK
Art. 5(2)/c and Art. 5(2)/f.

Our detailed information notice is available at
www.companyname.com.tr/kvkk/cm.

If you do not wish to continue, you may end the call.

For requests press 1, for your account press 2..."
```

### Outbound — Marketing Call

```
[Operator]:
"Good day [Customer name]. This is [Operator name] calling from [Company].
This call is being recorded.

I would like to share information about [product/campaign]. According to our
KVKK and İYS records, you have previously given explicit consent to marketing
communication. Would you like to proceed?"

[If the customer refuses]
"Understood. I will arrange the withdrawal of your marketing-communication
consent. A confirmation e-mail will follow. Have a good day."

[Consent state updated in the system, e-mail triggered]
```

### Evidence
- IVR announcement system log (display)
- Voice recording (full call)
- Consent state in CRM
- İYS approval record (for outbound)

### Common Errors
- Announcement limited to "this call is being recorded"; missing data controller, purpose, legal ground, application info
- Outbound marketing call placed without checking İYS approval
- Voice recordings retained for unlimited duration

---

## Scenario 5 — Mobile App Permissions (Location, Camera, Microphone, Contacts)

### Context
A mobile application requests location, camera (product photo), microphone (voice support feature) and contacts (sharing) access.

### Legal Analysis
OS permission ≠ KVKK consent. **Both are required.**

| Permission | Purpose | Legal Ground |
|------------|---------|--------------|
| Location (coarse) | Nearest-store suggestion | Art. 5(2)/f (legitimate interest — informational) |
| Location (precise, continuous) | Location-based campaign | Explicit consent |
| Camera | Product-photo upload | Art. 5(2)/c (contract performance — user-generated content) |
| Microphone | Voice customer service | Art. 5(2)/c (contract performance) |
| Contacts | Invite-friends feature | Explicit consent + third party's consent expected |

### Flow

```
[App first launch]
1. Onboarding screen: INF-MOB-01 (Mobile App Information Notice)
2. Account creation → e-mail/phone verification
3. Permission requests (just-in-time):
   - Location modal:
     "Location access is needed to show stores nearby.
      This is processed under KVKK Art. 5(2)/f.
      If you grant the OS permission, your location stays on your device
      and is used only to list nearby stores."
     [Allow]  [Reject]

4. Marketing explicit-consent screen (separate):
   ☐ Location-based marketing explicit consent
   ☐ Push-notification marketing explicit consent
```

### Common Errors
- Confusing OS permission with KVKK consent
- Disabling the app when permission is not granted
- Silently capturing background location
- Using contacts data without consent of the third parties

---

## Scenario 6 — Cookie Banner (CMP) + IAB TCF Localised for Turkey

### Context
The website uses analytics and marketing cookies. The IAB TCF (Transparency & Consent Framework) v2 structure is used; local compliance for Turkey is also required.

### Legal Analysis
- **Strictly necessary cookies:** Art. 5(2)/f (legitimate interest — site functionality)
- **Performance/analytics:** Explicit consent recommended (per Authority's cookie guide)
- **Marketing/advertising:** Explicit consent mandatory

### Cookie Banner Design

```
[Bottom of page — sticky bar]

┌────────────────────────────────────────────────────────┐
│ Cookie Preferences                                      │
│                                                          │
│ Our website uses cookies. Strictly necessary cookies     │
│ run the site. Other cookies depend on your preferences.  │
│                                                          │
│ [Reject All]   [Accept All]   [Manage Preferences]       │
└────────────────────────────────────────────────────────┘
```

> "Reject All" must be **as easy** and **visually weighted equally** as "Accept All".

### Manage Preferences (Detailed Modal)

```
☑ Strictly necessary  (cannot be turned off)
   Session, security and core functionality.
   [Detail list]

☐ Performance / Analytics
   Page performance and usage analysis (Google Analytics, etc.)
   Duration: 13 months | Third parties: Google Ireland

☐ Marketing / Advertising
   Targeted advertising and campaign communication (Meta, Google Ads)
   Duration: 13 months | Third parties: Meta (USA), Google Ads (Ireland)

☐ Social Media
   Social-media share plugins (Facebook, X)
   Duration: session + 1 year

[Save Preferences]   [Cancel]

Detailed cookie policy: [link]
KVKK Information Notice: INF-WEB-01
```

### IAB TCF Note
- An IAB TCF v2 string alone does not provide KVKK compliance.
- A Turkish text + reference to KVKK Art. 5/Art. 6 + the Authority's cookie guide + İYS compliance are additional requirements.
- TCF Vendor List entries must be listed as third-party recipients in the information notice.

### Common Errors
- Only an "Accept" button (refusal not balanced)
- Saved preference defaults to accept
- Third-party cookies not declared
- Cookie wall (cannot enter without accepting) — criticised in Board guidance

---

## Scenario 7 — Newsletter / SMS Marketing (Including İYS Compliance)

### Context
A newsletter subscription is being collected from a visitor who is not yet a customer.

### Legal Analysis
- **KVKK consent:** Art. 5(1) first sentence — explicit consent
- **İYS approval:** Law No. 6563 + İYS Regulation — approval mandatory, registered with İYS
- **Existing-customer exemption:** limited (relevant sectoral rules apply)

### Newsletter Sign-up Form

```
Subscribe to Newsletter

E-mail: [_______________]

☐ I agree to receive campaign, discount and new-product information by e-mail.
  KVKK Disclosure: INF-MKT-01
  İYS Approval: e-mail channel

  I may withdraw at any time via the unsubscribe link or via iys.org.tr.

[Subscribe]
```

### First Confirmation E-mail (Double Opt-in)

```
Subject: Confirm your e-mail subscription

Hello [User name],

You requested to subscribe to the [Company name] e-mail list.

Click to confirm your subscription:
[CONFIRM] (link valid for 7 days)

If you did not request this, you may ignore this e-mail.

KVKK Information Notice: [link]
İYS information and subscription management: iys.org.tr
```

> Double opt-in is not legally mandatory; however, it improves the quality of "consent evidence" in Authority audits and prevents erroneous registrations.

### Below Each Marketing E-mail

```
─────────────────────────────────────────
This e-mail was sent based on the explicit consent we obtained under
KVKK Art. 5(1) first sentence.

To unsubscribe: [Unsubscribe link]
To manage via İYS: iys.org.tr
KVKK Information Notice: [Link]

[Full Company Title] - [MERSIS] - [Address]
```

### Common Errors
- Approval not registered with İYS
- Hidden / hard-to-find unsubscribe button
- Single opt-in risk of fake registration
- Wording extending beyond legislative scope (e.g., "campaigns, surveys, third parties, other activities")

---

## Scenario 8 — Healthcare Patient Registration (KVKK Art. 6 Health Data)

### Context
Private hospital / polyclinic. Patient registration, examination, treatment processes.

### Legal Analysis
- **Health data:** KVKK Art. 6 — special category
- **Art. 6(3) exception:** May be processed without consent by persons under a duty of confidentiality (physician, nurse, pharmacist, etc.) for the protection of public health, preventive medicine, medical diagnosis, treatment and care, planning and management of health services and financing.
- **Financial transactions (billing, insurance):** additionally Art. 5(2)/c and Art. 5(2)/ç
- **Purposes other than health (e.g., marketing, research):** explicit consent

### Patient Registration Information Notice (Summary)

```
PATIENT INFORMATION NOTICE
[Full Hospital Name]

Data Processed:
- Identity, contact
- Health data (special category): diagnosis, treatment, medication, medical
  imaging, lab results, anamnesis
- Financial information (for billing)

Purposes:
- Medical diagnosis, treatment and care
- Planning and management of health services
- Reporting to health authorities under legislation
- Insurance accrual and billing
- Scientific research (anonymised; otherwise, with explicit consent)

Legal Ground:
- KVKK Art. 6(3) — processing of health and sexual-life data by persons
  under a duty of confidentiality
- KVKK Art. 5(2)/ç — Ministry of Health notifications (Basic Law on Health
  Services, etc.)
- KVKK Art. 5(2)/c — performance of the healthcare contract
- KVKK Art. 5(2)/e — establishment of a right (insurance, litigation)

Transfer:
- Ministry of Health, relevant ministry units (statutory)
- SGK and private health insurers
- Other healthcare institutions for referrals
- Legal partner (in case of dispute)
- Cross-border: where a foreign expert opinion is required, transferred
  with explicit consent

Retention:
- Patient file: relevant healthcare legislation and TBK limitation periods
  evaluated together; **20 years** as reference.
```

### Scenarios Requiring Explicit Consent (Inside the Hospital)

| Processing | Consent |
|-----------|---------|
| Health data processing for treatment | Not required (Art. 6(3)) |
| Sharing health report for insurance | Generally not required; contract + statute |
| Participation in clinical research | Explicit consent mandatory |
| Marketing (announcement of new services) | Explicit consent mandatory |
| Patient-experience survey | Art. 5(2)/f or explicit consent |
| Photo for social-media share | Explicit consent mandatory |

### Common Errors
- Generic staff access to health data (limited to those under a duty of confidentiality)
- Insufficient retention period for patient files
- No explicit consent for clinical research
- Use of health data for marketing without consent

---

## Scenario 9 — HR Reference-Check Process

### Context
At the final stage of recruitment, references provided by the candidate (former employer / managers) are contacted. The reference provider is also a data subject.

### Legal Analysis

Two different data subject groups:
1. **Candidate** — own data
2. **Reference provider** — personal data (at least name, organisation, contact)

| Data subject | Legal ground |
|--------------|--------------|
| Candidate — processing of reference information | Art. 5(2)/c (pre-contract measures) |
| Candidate — obtaining the reference's opinion | Art. 5(2)/f (legitimate interest — competency assessment) |
| Reference provider — contact data | Art. 5(2)/f (legitimate interest); disclosure performed |
| Opinion taken from the reference (qualified comment) | Art. 5(2)/f, depending on category |

### Operational Flow

1. The candidate shares reference contact details on the application form.
2. The information notice contains "you are expected to obtain disclosure and, where required, consent from the reference whose contact details you share."
3. HR calls the reference and starts with a **disclosure to the reference**:

```
"Hello [Name]. This is [HR specialist name] from [Company]. [Candidate name]
listed you as a reference. I would like to discuss the candidate's past
work experience with you.

Our call is being conducted on the basis of legitimate interest under KVKK
Art. 5(2)/f. The information you provide will be used in [candidate name]'s
recruitment decision and retained for 1 year. Our detailed information
notice can be sent to you on request.

May I proceed?"
```

### Common Errors
- Failing to make disclosure to the reference (at the start of the call)
- Using reference data shared by the candidate without consent (e.g., blacklist)
- Long retention of reference responses
- Missing call-recording announcement when reference is called

---

## Scenario 10 — Sharing Supplier-Employee Data

### Context
Company A (data controller) receives name-surname, T.R. ID number, telephone and job title of supplier B's employees in order to provide them with building/system access.

### Legal Analysis
- **From Company A's perspective (data controller):** Art. 5(2)/c (performance of the contract between A and B); Art. 5(2)/f (legitimate interest in protecting the building)
- **Supplier B's employee (data subject):** Not the employee's own consent; B's performance obligation
- **Disclosure:** Company A may disclose to the supplier's employee **directly** or via supplier B.

### Suggested Contract Clause (B → A)

```
"The Supplier (B) represents and undertakes that, in the course of obtaining
the personal data of its employees and transferring them to the Company (A),
it has fulfilled the disclosure obligation under KVKK Art. 10 vis-à-vis its
own employees. Employees who will work in A's building will additionally be
served A's INF-OPR-01 (Supplier Employee Building and System Access)
information notice, and signed copies will be provided to A on its request."
```

### Information Notice for the Supplier Employee (At Building Entry)

```
DEAR VISITOR / SUPPLIER EMPLOYEE

[Full Title of Company A] processes the following personal data of yours
to enable your access to our building and/or systems:

Data: name-surname, T.R. ID number, telephone, photograph (for the badge),
       title, name of the supplier company you work for

Purpose: Building and system security, performance of the supplier contract,
OHS records

Legal Ground:
- KVKK Art. 5(2)/c — Performance of the contract between our company and
  your supplier
- KVKK Art. 5(2)/f — Legitimate interest in building security
- KVKK Art. 5(2)/ç — OHS legislation

Retention: 1 year from completion of the work

Transfer: Authorised law enforcement (with written request and judicial
process), insurance company (in case of accident)

Cross-border transfer: NONE

KVKK Art. 11 rights and applications: [info]
Detailed information notice: INF-OPR-01 (available on request at the badge
issue point)
```

### Common Errors
- Treating the supplier employee as not requiring disclosure because they "are an employee of the supplier"
- Absence of KVKK clauses in the supplier contract
- Treating supplier-employee data like customer data at Company A
- Continuing retention beyond 1 year

---

## 11. General Cross-Scenario Reference Table

| Scenario type | Disclosure | Explicit Consent | Suggested Legal Ground |
|---------------|-----------|------------------|------------------------|
| Customer contract (registration, order) | Yes | N | Art. 5(2)/c, Art. 5(2)/ç |
| Marketing (e-mail/SMS/push) | Yes | Y | Art. 5(1) + İYS |
| Profiling | Yes | Y | Art. 5(1) |
| Inbound call center voice recording | Yes (announcement) | N | Art. 5(2)/c, Art. 5(2)/f |
| Outbound call center marketing | Yes | Y | Art. 5(1) + İYS |
| Employee personnel file | Yes | N | Art. 5(2)/c, Art. 5(2)/ç |
| Job candidate | Yes | N (Y for talent pool) | Art. 5(2)/c |
| CCTV building security | Yes | N | Art. 5(2)/f, Art. 5(2)/ç |
| Visitor management | Yes | N | Art. 5(2)/f, Art. 5(2)/ç |
| Mobile app — core function | Yes | N | Art. 5(2)/c, Art. 5(2)/f |
| Mobile app — location/contacts/microphone (non-essential) | Yes | Y | Art. 5(1) |
| Cookies analytics | Yes | Y (recommended) | Art. 5(1) |
| Cookies marketing | Yes | Y (mandatory) | Art. 5(1) |
| Newsletter | Yes | Y | Art. 5(1) + İYS |
| Health data treatment | Yes | N | Art. 6(3) |
| Health data marketing/research | Yes | Y | Art. 6(2) |
| Employee reference | Yes | N | Art. 5(2)/f |
| Supplier employee building access | Yes | N | Art. 5(2)/c, Art. 5(2)/f, Art. 5(2)/ç |

## 12. Annexes

- Template: [aydinlatma-metni-sablonu.md](./aydinlatma-metni-sablonu.md)
- Checklist: [aydinlatma-metni-checklist.md](./aydinlatma-metni-checklist.md)
- Explicit Consent Rules: [acik-riza-kurallari.md](./acik-riza-kurallari.md)

---

## Türkçe

# Senaryo Bazlı Aydınlatma ve Açık Rıza Örnekleri

Bu doküman, sık karşılaşılan iş senaryoları için aydınlatma ve açık rıza uygulamasının pratik karşılığını gösterir. Her senaryoda:
1. **Bağlam** — operasyonel durum
2. **Hukuki analiz** — hangi sebep, açık rıza gerekli mi
3. **Aydınlatma metni** — uygun kanal için kısaltılmış örnek
4. **Açık rıza ekranı / akışı** — varsa
5. **İspat ve kayıt** — neyi nasıl logluyoruz
6. **Sık hatalar**

---

## Senaryo 1 — Müşteri E-ticaret Kayıt + Pazarlama Ek Rıza

### Bağlam
B2C e-ticaret sitesinde kullanıcı kayıt formu. Sipariş verme + pazarlama iletişimi ayrı amaçlar.

### Hukuki Analiz
- **Hesap oluşturma + sözleşme:** KVKK m.5/2/c (sözleşmenin ifası için zorunluluk)
- **Sipariş takibi, faturalandırma:** m.5/2/c, m.5/2/ç (VUK gereği)
- **Pazarlama (e-posta, SMS, push):** Açık rıza + İYS onayı zorunlu
- **Profilleme (alışveriş analizine dayalı öneri):** Açık rıza
- **3. kişi pazarlama paylaşımı:** Açık rıza

### Form Tasarımı

```
[Sayfa 1 — Üyelik Bilgileri]
Ad Soyad:  [____________]
E-posta:   [____________]
Telefon:   [____________]
Şifre:     [____________]

→ "İleri" butonu

[Sayfa 2 — Bilgilendirme ve Onay]

ZORUNLU
☐ "Üyelik Aydınlatma Metni"ni (AYD-MUS-01) okudum ve anladım.
☐ Mesafeli Satış Ön Bilgilendirme Formu'nu okudum, kabul ediyorum.
☐ Üyelik Sözleşmesi'ni okudum, kabul ediyorum.

OPSİYONEL — AÇIK RIZA
Aşağıdaki seçimler tamamen size aittir. Vermemeniz halinde
hizmetimizden faydalanmanıza engel oluşturmaz.

☐ Pazarlama Açık Rızası
   Şirket'in açık ve kapalı kampanyaları, indirimleri ve yeni ürün
   tanıtımları hakkında e-posta, SMS ve push bildirim almayı kabul
   ediyorum. (Aydınlatma: AYD-PAZ-01) (İYS: e-posta + SMS)

☐ Kişiselleştirme / Profilleme Açık Rızası
   Site üzerindeki davranışlarımın ve sipariş geçmişimin analiz
   edilerek bana özel öneriler sunulmasını kabul ediyorum.
   (Aydınlatma: AYD-PAZ-02)

☐ İş Ortaklarıyla Pazarlama Amaçlı Paylaşım
   Pazarlama amaçlı verilerin Şirket'in iş ortaklarıyla paylaşılmasını
   kabul ediyorum. (Aydınlatma: AYD-PAZ-03)

[Üye Ol]
```

### İspat ve Kayıt

CMP kaydı:
```
{
  "user_id": "U-394827",
  "consent": [
    { "category": "marketing_email_sms",   "status": "granted",   "version": "AYD-PAZ-01:1.2" },
    { "category": "profiling",             "status": "withdrawn", "version": "AYD-PAZ-02:1.0" },
    { "category": "third_party_sharing",   "status": "granted",   "version": "AYD-PAZ-03:1.1" }
  ],
  "channel": "web",
  "ip": "85.x.x.x",
  "user_agent": "Mozilla/5.0 ...",
  "recorded_at": "2026-05-08T13:24:10Z",
  "iys_record_id": "IYS-0000-0000"
}
```

### Sık Hatalar
- Hesap açma için pazarlama rızası şartına bağlama
- Aydınlatma + tüm rızaları tek checkbox'a sıkıştırma
- "Tümünü işaretle" varsayılanı
- Geri alma kanalının olmaması

---

## Senaryo 2 — Çalışan İşe Alım → İşe Alım Sonrası Geçiş

### Bağlam
İşe alım süreci → işe başladıktan sonra özlük dosyası süreci. **İki farklı süreç → iki farklı aydınlatma metni.**

### Hukuki Analiz
- **Aday değerlendirme:** m.5/2/c (sözleşme öncesi tedbirler), m.5/2/f (meşru menfaat)
- **Aday havuzunda saklama (işe alınmadıysa):** Açık rıza
- **İşe alındıktan sonra özlük:** m.5/2/c (sözleşme ifası), m.5/2/ç (İş Kanunu, SGK), m.6/3 (sağlık verisi için sır saklayanlarca)

### Aydınlatma Akışı

1. Başvuru anında: **AYD-IK-01 (İşe Alım)** gösterilir.
2. İşe alındığında: **AYD-IK-02 (Özlük Dosyası)** ayrıca verilir, imzalı kopya alınır.
3. Sağlık raporu için: **AYD-IK-07 (İSG)** + ek aydınlatma.
4. Aday havuzunda saklama isteniyorsa açık rıza ayrı alınır.

### Aday Havuzu Açık Rıza Metni (Form üstünde)

```
☐ İş başvurum değerlendirmesi sonucunda işe alınmamam halinde,
  ileride uygun pozisyonlar açıldığında değerlendirilmek üzere
  başvuru bilgilerimin Şirket tarafından maksimum 2 yıl süreyle
  saklanmasına açık rıza veriyorum. (AYD-IK-01)

  Bu rızayı dilediğim zaman ik-kvkk@sirketadi.com.tr adresine
  başvurarak geri alabilirim.
```

### Sık Hatalar
- Tek aydınlatma metni ile aday + çalışan ayrımının yapılmaması
- İSG sağlık verisi için ayrı aydınlatma yapılmaması
- Aday havuzu için rıza alınmadan saklama
- Çalışana "açık rıza vermek zorundasınız" hissi verme

---

## Senaryo 3 — CCTV: Ziyaretçi Tabela + Detaylı Aydınlatma

### Bağlam
Şirket binasında CCTV bulunmakta. Tüm girişler izlenmekte, soyunma odası, WC vb. kapsam dışı.

### Hukuki Analiz
- **Hukuki sebep:** m.5/2/f (meşru menfaat — bina güvenliği) + m.5/2/ç (İSG mevzuatı)
- **Açık rıza gerekmiyor**

### Tabela Metni (Bina Girişi — Görünür Yer)

```
┌──────────────────────────────────────────────────┐
│ [Şirket logosu]                                   │
│                                                   │
│ DİKKAT — KAPALI DEVRE KAMERA SİSTEMİ              │
│                                                   │
│ Bu alan güvenlik amacıyla kamera ile             │
│ izlenmektedir.                                    │
│                                                   │
│ Veri Sorumlusu: [Şirket Tam Ünvanı]              │
│ İşleme Amacı: Bina ve çevre güvenliği,           │
│ İSG kapsamında giriş-çıkış kaydı                 │
│ Hukuki Sebep: KVKK m.5/2/f ve m.5/2/ç           │
│                                                   │
│ Detaylı aydınlatma metni:                        │
│ www.sirketadi.com.tr/kvkk/cctv                   │
│ [QR KOD]                                          │
│                                                   │
│ Saklama: 30 gün                                  │
│ Başvuru: kvkk@sirketadi.com.tr                  │
└──────────────────────────────────────────────────┘
```

### Detay Metnine Eklenecek Önemli Bilgi

```
Kameralar bina ortak alanları, giriş-çıkışlar, koridorlar,
otopark ve ana güvenlik noktalarında konumlanmıştır. Tuvalet,
soyunma odası, dini ibadet alanları ve özel mahremiyet alanları
kapsam dışında bırakılmıştır. Toplam [n] kamera bulunmaktadır.
Kayıtlara yalnızca yetkilendirilmiş Güvenlik personeli erişebilir.
Kayıtlar, olay yokluğunda 30 günde rotasyonel olarak silinir.
```

### Sık Hatalar
- Tek tabela ile yetinme; web sayfasında detay vermeme
- Mahremiyet alanlarına kamera yerleştirme
- 30 günden uzun saklama gerekçesizce
- Kayıtlara çok geniş erişim yetkisi

---

## Senaryo 4 — Çağrı Merkezi Ses Kaydı Anonsu (Tam Metin)

### Bağlam
Inbound (gelen arama) ve outbound (giden arama) çağrı merkezi. Tüm görüşmeler kayıt altında.

### Hukuki Analiz
- **Inbound (müşteri sözleşmesi gereği):** m.5/2/c
- **Inbound (genel destek, hizmet kalitesi):** m.5/2/f
- **Outbound (pazarlama):** Açık rıza + İYS onayı
- **Eğitim amaçlı kullanım:** ek meşru menfaat değerlendirmesi gerekir

### Inbound — IVR Anonsu (Görüşme Başında)

```
"[Şirket adı]'na hoş geldiniz.

Şirketimiz tarafından hizmet kalitesinin denetlenmesi, taleplerinizin
kayıt altına alınması ve sözleşmemizin ifası amacıyla, KVKK
madde 5/2/c ve madde 5/2/f bentlerine dayanarak, görüşmeniz ses
kayıt altına alınmaktadır.

Detaylı aydınlatma metnimize www.sirketadi.com.tr/kvkk/cm
adresinden ulaşabilirsiniz.

Görüşmeye devam etmek istemiyorsanız hattan ayrılabilirsiniz.

Talebiniz için 1, hesabınız için 2..."
```

### Outbound — Pazarlama Çağrısı

```
[Operatör]:
"İyi günler [Müşteri adı]. [Şirket adı]'ndan [Operatör adı] arıyor.
Görüşmeniz kayıt altındadır.

Sizinle [ürün/kampanya] hakkında bilgi paylaşmak isterim. KVKK ve
İYS kayıtlarımız uyarınca daha önce pazarlama iletişimi açık
rızanız bulunmaktadır. Görüşmeyi sürdürmek ister misiniz?"

[Müşteri red ederse]
"Anladım. Pazarlama iletişimi rızanızı geri çekmenizi sağlayacağım.
Bilgilendirme e-postası gelecektir. İyi günler dilerim."

[Sistem üzerinde rıza durumu güncellenir, e-posta tetiklenir]
```

### İspat
- IVR anons sistem logu (gösterim)
- Ses kaydı (tam görüşme)
- CRM üzerinde rıza durumu
- İYS onay kaydı (outbound için)

### Sık Hatalar
- Anons "görüşme kayıt altına alınıyor" ile yetiniliyor; veri sorumlusu, amaç, hukuki sebep, başvuru bilgisi eksik
- Outbound pazarlama aramasında İYS onayı kontrol edilmeden arama yapma
- Ses kaydını sınırsız süre saklama

---

## Senaryo 5 — Mobil Uygulama İzinleri (Lokasyon, Kamera, Mikrofon, Kişiler)

### Bağlam
Mobil uygulama, hizmet için lokasyon, kamera (ürün fotoğrafı), mikrofon (sesli arama özelliği) ve kişiler (paylaşma) erişimi ister.

### Hukuki Analiz
İşletim sistemi izni ≠ KVKK rızası. **Her ikisi de gereklidir.**

| İzin | Amaç | Hukuki Sebep |
|------|------|--------------|
| Lokasyon (kaba) | Yakın mağaza önerisi | m.5/2/f (meşru menfaat — bilgilendirici amaç) |
| Lokasyon (hassas, sürekli) | Lokasyon bazlı kampanya | Açık rıza |
| Kamera | Ürün fotoğrafı yükleme | m.5/2/c (sözleşme ifası — kullanıcı içerik üretimi) |
| Mikrofon | Sesli müşteri hizmeti | m.5/2/c (sözleşme ifası) |
| Kişiler | Davet et özelliği | Açık rıza + 3. kişi rızası beklenir |

### Akış

```
[Uygulama ilk açılış]
1. Onboarding ekranı: AYD-MOB-01 (Mobil Uygulama Aydınlatma)
2. Hesap oluşturma → e-posta/telefon doğrulama
3. İzin istekleri (gerektiğinde — anlık):
   - Lokasyon istendiğinde modal:
     "Mağazaları yakınınızdan görmek için lokasyon erişimi gerekli.
      Bu, KVKK m.5/2/f bendi kapsamında işlenir.
      İşletim sistemi izni vermeniz halinde lokasyonunuz cihazınızda
      tutulur ve sadece yakın mağaza listesi için kullanılır."
     [İzin Ver]  [Reddet]

4. Pazarlama açık rıza ekranı (ayrı):
   ☐ Lokasyon bazlı pazarlama açık rızası
   ☐ Push bildirimle pazarlama açık rızası
```

### Sık Hatalar
- İşletim sistemi iznini KVKK rızası ile karıştırma
- Kullanıcı izin vermeyince uygulamayı işlevsiz bırakma
- Sürekli arka plan lokasyonu sessizce alma
- Kişiler erişiminden 3. kişilerin rızası alınmadan veri kullanma

---

## Senaryo 6 — Çerez Bandı (CMP) + IAB TCF Türkiye Uyarlaması

### Bağlam
Web sitesi analitik ve pazarlama çerezleri kullanıyor. IAB TCF (Transparency & Consent Framework) v2 yapısı kullanılıyor; ancak Türkiye için yerel uyumluluk gereksinimleri var.

### Hukuki Analiz
- **Zorunlu çerezler:** m.5/2/f (meşru menfaat — site fonksiyonu)
- **Performans/analitik:** Açık rıza önerilir (Kurum çerez rehberi paralelinde)
- **Pazarlama/reklam:** Açık rıza zorunlu

### Çerez Bandı Tasarımı

```
[Sayfa altında — sticky bar]

┌────────────────────────────────────────────────────────┐
│ Çerez Tercihleri                                        │
│                                                          │
│ Web sitemiz çerezler kullanır. Zorunlu çerezler          │
│ siteyi çalıştırır. Diğer çerezler tercihlerinize         │
│ bırakılmıştır.                                           │
│                                                          │
│ [Tümünü Reddet]   [Tümünü Kabul Et]   [Tercihleri Yönet]│
└────────────────────────────────────────────────────────┘
```

> "Tümünü Reddet" butonu "Tümünü Kabul Et" ile **eşit kolaylıkta** ve **eşit görsel ağırlıkta** olmalıdır.

### Tercihleri Yönet (Detaylı Modal)

```
☑ Zorunlu çerezler  (kapatılamaz)
   Oturum yönetimi, güvenlik ve temel fonksiyonlar.
   [Detay listesi]

☐ Performans / Analitik
   Sayfa performansı ve kullanım analizi (Google Analytics, vb.)
   Süre: 13 ay | Üçüncü taraflar: Google İrlanda

☐ Pazarlama / Reklam
   Hedeflenmiş reklam ve kampanya iletişimi (Meta, Google Ads)
   Süre: 13 ay | Üçüncü taraflar: Meta (ABD), Google Ads (İrlanda)

☐ Sosyal Medya
   Sosyal medya paylaşım eklentileri (Facebook, X)
   Süre: oturum + 1 yıl

[Tercihleri Kaydet]   [Vazgeç]

Detaylı çerez politikası: [link]
KVKK Aydınlatma Metni: AYD-WEB-01
```

### IAB TCF Notu
- IAB TCF v2 string'i tek başına KVKK uyumu sağlamaz.
- Türkçe metin + KVKK m.5/m.6 atfı + Kurum'un çerez rehberi + İYS uyumu ek gerekliliklerdir.
- TCF Vendor List'i, üçüncü taraf alıcılar olarak aydınlatma metninde belirtilmelidir.

### Sık Hatalar
- "Sadece kabul et" butonu (red dengelenmemiş)
- Tercih kaydeden butonun varsayılan kabul olması
- 3. taraf çerezlerin hiç bildirilmemesi
- Cookie wall (kabul etmeden sayfaya girilemiyor) — Kurul rehberlerinde eleştirilmiştir

---

## Senaryo 7 — Newsletter / SMS Pazarlama (İYS Uyumu Dahil)

### Bağlam
Mevcut müşteri olmayan ziyaretçiden newsletter aboneliği alınıyor.

### Hukuki Analiz
- **KVKK rızası:** m.5/1 ilk cümle — açık rıza
- **İYS onayı:** 6563 sayılı Kanun + İYS Yönetmeliği — onay zorunlu, İYS'ye kayıt
- **Mevcut müşteri istisnası:** sınırlı (ilgili sektör mevzuatına bakılır)

### Newsletter Kayıt Formu

```
Newsletter'a Abone Ol

E-posta: [_______________]

☐ E-posta ile kampanya, indirim ve yeni ürün bilgileri almayı
  kabul ediyorum.
  KVKK Aydınlatması: AYD-PAZ-01
  İYS Onayı: e-posta kanalı

  Onayımı dilediğim zaman aboneliği iptal et bağlantısı veya
  iys.org.tr üzerinden geri alabilirim.

[Abone Ol]
```

### İlk Onay E-postası (Çift-onaylı / Double Opt-in)

```
Konu: E-posta aboneliğinizi onaylayın

[Kullanıcı adı] merhaba,

[Şirket adı] e-posta listesine abone olmak istediğinizi belirttiniz.

Aboneliğinizi onaylamak için tıklayın:
[ONAYLA] (link 7 gün geçerli)

Eğer bu isteği siz yapmadıysanız, bu e-postayı görmezden gelebilirsiniz.

KVKK Aydınlatma Metni: [link]
İYS bilgileri ve abonelik yönetimi: iys.org.tr
```

> Çift-onaylı (double opt-in) yapı yasal zorunluluk değildir; ancak Kurul incelemelerinde "rıza ispatı" kalitesini artırır ve hatalı kayıtları önler.

### Her Pazarlama E-postası Altında

```
─────────────────────────────────────────
Bu e-posta, KVKK m.5/1 ilk cümle uyarınca aldığımız açık rızaya
dayalı olarak gönderilmiştir.

Aboneliği iptal etmek için: [İptal Linki]
İYS üzerinden yönetmek için: iys.org.tr
KVKK Aydınlatma Metni: [Link]

[Şirket Tam Ünvanı] - [MERSİS] - [Adres]
```

### Sık Hatalar
- İYS'ye onay kaydedilmiyor
- Abonelikten çıkma butonu gizli/zor
- Tek opt-in ile sahte kayıt riski
- Onay altında yer alan ifadelerin mevzuat dışı çıkması (örn. "kampanya, anket, üçüncü taraf, başka faaliyet" gibi geniş)

---

## Senaryo 8 — Sağlık Kurumu Hasta Kayıt (KVKK m.6 Sağlık Verisi)

### Bağlam
Özel hastane / poliklinik. Hasta kaydı, muayene, tedavi süreçleri.

### Hukuki Analiz
- **Sağlık verisi:** KVKK m.6 — özel nitelikli
- **m.6/3 istisnası:** Sır saklama yükümlülüğü altındaki kişilerce (hekim, hemşire, eczacı vb.) kamu sağlığının korunması, koruyucu hekimlik, tıbbi teşhis, tedavi ve bakım, sağlık hizmetlerinin planlanması ve yönetimi amaçlarıyla rızasız işlenebilir.
- **Mali işlem (faturalama, sigorta):** ek olarak m.5/2/c ve m.5/2/ç
- **Sağlık verisi dışındaki amaçlar (örn. pazarlama, araştırma):** açık rıza

### Hasta Kayıt Aydınlatma Metni (Özet)

```
HASTA AYDINLATMA METNİ
[Hastane Tam Ünvanı]

İşlenen Veriler:
- Kimlik, iletişim
- Sağlık verileri (özel nitelikli): tanı, tedavi, ilaç, tıbbi görüntüleme,
  laboratuvar sonuçları, anamnez
- Mali bilgiler (faturalama amacıyla)

Amaçlar:
- Tıbbi teşhis, tedavi ve bakım hizmetleri
- Sağlık hizmetinin planlanması ve yönetimi
- Mevzuat gereği sağlık otoritelerine bildirim
- Sigorta tahakkuk ve faturalama
- Bilimsel araştırma (anonim hale getirilerek; aksi halde açık rıza ile)

Hukuki Sebep:
- KVKK m.6/3 — sağlık ve cinsel hayata ilişkin verilerin sır saklama
  yükümlülüğü altındaki kişilerce işlenmesi
- KVKK m.5/2/ç — Sağlık Bakanlığı bildirimleri (Sağlık Hizmetleri
  Temel Kanunu vb.)
- KVKK m.5/2/c — sağlık hizmeti sözleşmesinin ifası
- KVKK m.5/2/e — bir hakkın tesisi (sigorta, dava)

Aktarım:
- Sağlık Bakanlığı, ilgili bakanlık birimleri (mevzuat gereği)
- SGK ve özel sağlık sigorta şirketleri
- Sevk yapılan diğer sağlık kuruluşları
- Avukatlık ortağı (ihtilaf halinde)
- Yurt dışı: medikal görüş için yurt dışı uzman gerekiyorsa açık rıza
  ile aktarım yapılabilir

Saklama:
- Hasta dosyası: ilgili sağlık mevzuatı ve TBK zamanaşımı süreleri
  birlikte değerlendirilir; **20 yıl** referans alınır.
```

### Açık Rıza Gereken Senaryolar (Hastanede)

| İşleme | Rıza |
|--------|------|
| Tedavi amaçlı sağlık verisi işleme | Aranmaz (m.6/3) |
| Sigorta için sağlık raporu paylaşımı | Genelde aranmaz; sözleşme + mevzuat |
| Klinik araştırmaya katılım | Açık rıza zorunlu |
| Pazarlama (yeni hizmet duyurusu) | Açık rıza zorunlu |
| Hasta deneyimi anketi | m.5/2/f veya açık rıza |
| Sosyal medya paylaşımı için fotoğraf | Açık rıza zorunlu |

### Sık Hatalar
- Sağlık verilerine genel personel erişimi (sır saklama yükümlülüğü ile sınırlı)
- Hasta dosyalarının yetersiz saklama süresi belirlenmesi
- Klinik araştırma için açık rıza alınmaması
- Pazarlama amaçlı kullanım için sağlık verisinin rızasız kullanılması

---

## Senaryo 9 — İK Referans Alma Süreci

### Bağlam
İşe alım finalinde adayın belirttiği eski işveren / yöneticilerinden referans alınıyor. Referans veren kişi de bir veri sahibi olabilir.

### Hukuki Analiz

İki ayrı veri konusu kişi grubu:
1. **Aday** — kendi verisi
2. **Referans Veren** — kişisel verisi (en azından adı, kurumu, iletişimi)

| Veri konusu | Hukuki sebep |
|-------------|--------------|
| Aday — referans bilgisinin işlenmesi | m.5/2/c (sözleşme öncesi tedbirler) |
| Aday — referansın görüşünün alınması | m.5/2/f (meşru menfaat — yetkinlik değerlendirme) |
| Referans veren — iletişim verisi | m.5/2/f (meşru menfaat); aydınlatma yapılır |
| Referans verenden alınan görüş (nitelikli yorum) | Veri kategorisine göre m.5/2/f |

### Operasyonel Akış

1. Aday, başvuru formunda referans iletişimini paylaşır.
2. Aydınlatma metninde "ilettiğiniz referans bilgilerinin sahibi olan kişiden de aydınlatma ve gerekli halde rızayı almanız beklenir" notu yer alır.
3. İK, referansı arar; arama başında **referans verene aydınlatma** yapar:

```
"Merhaba [İsim]. [Şirket adı]'ndan [İK uzmanı adı] arıyor. [Aday adı]
sizi referans olarak göstermiştir. Sizinle adayın geçmiş iş deneyimi
hakkında bilgi paylaşmak istiyorum.

Görüşmemiz, KVKK m.5/2/f bendi uyarınca meşru menfaate dayalı olarak
yapılmaktadır. Verdiğiniz bilgiler [aday adı]'nın işe alım kararında
kullanılacak ve 1 yıl süreyle saklanacaktır. Detaylı aydınlatma metnimiz
talep ettiğinizde tarafınıza iletilebilir.

Devam etmek ister misiniz?"
```

### Sık Hatalar
- Referans verene aydınlatma yapılmaması (çağrı başında)
- Aday tarafından paylaşılan referans verisinin rızasız kullanılması (örn. kara liste)
- Referans yanıtlarının uzun süre saklanması
- Telefon kayıt anonsunun referans aramaları için yapılmaması

---

## Senaryo 10 — Tedarikçi Çalışan Verisi Paylaşımı

### Bağlam
Şirket A (veri sorumlusu) tedarikçi B'nin çalışanlarına bina/sistem erişimi sağlamak için ad-soyad, T.C. kimlik no, telefon, görev unvanı bilgilerini alıyor.

### Hukuki Analiz
- **Şirket A açısından (veri sorumlusu):** m.5/2/c (Şirket A ile B arasındaki sözleşmenin ifası); m.5/2/f (binayı koruma meşru menfaati)
- **Tedarikçi B çalışanı (veri konusu):** Çalışanın kendi rızası değil; B'nin ifa yükümlülüğü
- **Aydınlatma:** Şirket A, tedarikçi çalışanını **doğrudan** aydınlatabilir veya tedarikçi B aracılığıyla aydınlatma yapılır.

### Sözleşme Hükmü Önerisi (B → A)

```
"Tedarikçi (B), Şirket'e (A) ileteceği çalışan kişisel verilerinin
elde edilmesi ve A'ya aktarımı süreçlerinde KVKK m.10 kapsamındaki
aydınlatma yükümlülüğünü kendi çalışanlarına karşı yerine getirmiş
olduğunu beyan ve taahhüt eder. A'nın binasında çalışacak çalışanlara
A'nın AYD-OPR-01 (Tedarikçi Çalışan Bina ve Sistem Erişimi) aydınlatma
metni ayrıca tebliğ edilecek ve A'nın talebi halinde imzalı kopyaları
A'ya iletilecektir."
```

### Tedarikçi Çalışanına Aydınlatma Metni (Bina Girişinde)

```
SAYIN ZİYARETÇİ / TEDARİKÇİ ÇALIŞANI

[Şirket A Tam Ünvanı] olarak, sizin bina ve/veya sistemlerimize
erişiminizi sağlayabilmek amacıyla aşağıdaki kişisel verilerinizi
işlemekteyiz:

Veriler: ad-soyad, T.C. kimlik no, telefon, fotoğraf (kart için),
        görev unvanı, çalıştığınız tedarikçi firma adı

Amaç: Bina ve sistem güvenliği, tedarikçi sözleşmesi ifası, İSG kayıtları

Hukuki Sebep:
- KVKK m.5/2/c — Şirketimiz ile tedarikçi firmanız arasındaki
  sözleşmenin ifası
- KVKK m.5/2/f — Bina güvenliği meşru menfaati
- KVKK m.5/2/ç — İSG mevzuatı

Saklama: İşin tamamlanmasından itibaren 1 yıl

Aktarım: Yetkili kolluk kuvvetleri (talep + adli süreç halinde),
sigorta firması (kaza halinde)

Yurt dışı aktarım: YOK

KVKK m.11 hakları ve başvuru: [bilgi]
Detaylı aydınlatma metni: AYD-OPR-01 (kart teslim noktasından
talep edebilirsiniz)
```

### Sık Hatalar
- Tedarikçi çalışanının "tedarikçi firma çalışanı" olduğu için aydınlatmanın gereksiz sayılması
- Tedarikçi sözleşmesinde KVKK hükümlerinin yer almaması
- Tedarikçi çalışanı verilerinin Şirket A'da müşteri verisi gibi işlenmesi
- 1 yıllık sürenin aşılmasına rağmen verilerin tutulması

---

## 11. Genel Kontrol Tablosu (Senaryo Bağımsız)

| Senaryo Türü | Aydınlatma | Açık Rıza | Hukuki Sebep Önerisi |
|--------------|-----------|-----------|---------------------|
| Müşteri sözleşmesi (kayıt, sipariş) | Evet | H | m.5/2/c, m.5/2/ç |
| Pazarlama (e-posta/SMS/push) | Evet | E | m.5/1 + İYS |
| Profilleme | Evet | E | m.5/1 |
| Çağrı merkezi ses kaydı (inbound) | Evet (anons) | H | m.5/2/c, m.5/2/f |
| Çağrı merkezi outbound pazarlama | Evet | E | m.5/1 + İYS |
| Çalışan özlük dosyası | Evet | H | m.5/2/c, m.5/2/ç |
| Çalışan adayı | Evet | H (havuz için E) | m.5/2/c |
| CCTV bina güvenlik | Evet | H | m.5/2/f, m.5/2/ç |
| Ziyaretçi yönetimi | Evet | H | m.5/2/f, m.5/2/ç |
| Mobil app — temel fonksiyon | Evet | H | m.5/2/c, m.5/2/f |
| Mobil app — lokasyon/kişiler/mikrofon (gereksiz) | Evet | E | m.5/1 |
| Çerez analitik | Evet | E (önerilir) | m.5/1 |
| Çerez pazarlama | Evet | E (zorunlu) | m.5/1 |
| Newsletter | Evet | E | m.5/1 + İYS |
| Sağlık verisi tedavi | Evet | H | m.6/3 |
| Sağlık verisi pazarlama/araştırma | Evet | E | m.6/2 |
| Çalışan referansı | Evet | H | m.5/2/f |
| Tedarikçi çalışanı bina erişimi | Evet | H | m.5/2/c, m.5/2/f, m.5/2/ç |

## 12. Ekler

- Şablon: [aydinlatma-metni-sablonu.md](./aydinlatma-metni-sablonu.md)
- Kontrol Listesi: [aydinlatma-metni-checklist.md](./aydinlatma-metni-checklist.md)
- Açık Rıza Kuralları: [acik-riza-kurallari.md](./acik-riza-kurallari.md)
