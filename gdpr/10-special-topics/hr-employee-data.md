---
title:
  en: "HR and Employee Data Processing"
  tr: "İK ve Çalışan Veri İşleme"
section: "10-special-topics"
document_id: "ST-HR-001"
owner: "DPO Office / HR Director"
classification: "Internal"
version: "1.0"
last_review: "2026-05-08"
next_review: "2027-05-08"
language: ["en", "tr"]
references:
  - "GDPR Art. 6 — Lawful basis"
  - "GDPR Art. 9 — Special categories (where applicable to HR)"
  - "GDPR Art. 88 — Processing in the context of employment"
  - "GDPR Recitals 39, 47, 71, 155"
  - "EDPB Opinion 2/2017 on data processing at work (legacy WP249, endorsed by EDPB)"
  - "ECtHR — Bărbulescu v. Romania (5 September 2017)"
  - "ECtHR — López Ribalda v. Spain (Grand Chamber, 17 October 2019)"
  - "ECtHR — Antović and Mirković v. Montenegro (2017)"
  - "CNIL — Guide pour les employeurs et les salariés"
  - "ICO — Employment practices code"
  - "BfDI — Data protection in employment"
---

## English

### 1. Scope

This document covers personal data processing across the employee lifecycle: recruitment, hire, onboarding, performance, learning, compensation, benefits, leave and absence, discipline, occupational medicine, change of role, leaver, post-employment references, and litigation/regulatory contexts. It also covers contractors, interns, and agency staff where the controller exercises direction.

### 2. Article 88 — Member State law layer

Article 88 GDPR allows Member States, by law or collective agreement, to provide more specific rules on the processing of employees' personal data. Many Member States have done so:

- **Germany** — Bundesdatenschutzgesetz §26 sets out a detailed regime; works councils have substantial co-determination rights.
- **France** — Code du travail, Loi Informatique et Libertés Article 88; CNIL guidance is detailed.
- **Italy** — Statuto dei Lavoratori Article 4 (employee monitoring), Codice Privacy.
- **Spain** — Estatuto de los Trabajadores; LOPDGDD Article 89 (digital rights).
- **Netherlands** — Wet bescherming persoonsgegevens (legacy) and now UAVG.
- **Türkiye** — KVKK plus İş Kanunu provisions.

The controller layers GDPR with applicable Member State employment-data law. Multinational employers maintain country-specific addenda to the global HR privacy notice.

### 3. Lawful bases

Choice of basis matters. EDPB Opinion 2/2017 emphasises that consent in the employment relationship is rarely freely given because of the imbalance of power. Reliance on consent is reserved for genuinely optional matters (e.g. participation in optional team photo for the company magazine; optional health screening).

Typical pairings:

| Activity | Article 6 | Article 9 if special-category |
|----------|-----------|-------------------------------|
| Payroll | (b) contract / (c) legal obligation | n/a unless health deductions |
| Tax and social security | (c) legal obligation | n/a |
| Performance management | (b) contract | n/a |
| Training | (b) contract / (f) legitimate interest | n/a |
| Health-and-safety records | (c) legal obligation | (b)/(h)/(i) |
| Disciplinary | (b) contract / (f) legitimate interest | (b)/(g) for sensitive aspects |
| Sickness absence | (c) legal obligation | (b)/(h) |
| Background checks | (b) contract / (c) legal obligation / (f) legitimate interest | (b) for criminal data + Member State law |
| Diversity monitoring | (a) consent (and Member State law) | (a) explicit consent (Article 9(2)(a)) |
| Whistleblowing | (c) legal obligation under whistleblowing law | (b) and (g) for sensitive content |
| Internal directory / org chart | (f) legitimate interest | n/a |
| Employee monitoring | (f) legitimate interest with strict balancing | (b)/(g) where applicable |

### 4. Recruitment

Lawful basis: (b) for steps prior to entering a contract, supplemented by (f) for retaining unsuccessful candidates' data for limited periods. Special-category data (e.g. health, religion, trade union) is generally not relevant and should not be solicited.

Practical rules:
- ATS records: retain only what is necessary.
- Unsuccessful candidates: short retention (commonly 6 months in EU practice unless candidate consents to a talent pool).
- AI-assisted screening tools: subject to Article 22 analysis, EU AI Act high-risk obligations (Annex III), and bias testing.
- Reference checks: with candidate's awareness; Article 13/14 information to referees.
- Right-to-work checks: process with care for nationality data; do not over-retain.

### 5. Hire and onboarding

Collect only what is necessary:
- identity and right-to-work documents;
- bank details for payroll;
- emergency contact (consent or legitimate interest with employee awareness);
- relevant qualifications;
- benefits enrolment selections.

Provide a comprehensive Article 13 employee privacy notice at hire. Update it materially when systems or vendors change.

### 6. Performance, discipline, grievance

- Performance reviews are personal data; subject access applies; rectification of factual errors required; rectification of opinion is not required but the employee may add their view.
- Disciplinary records are sensitive but not Article 9 unless they touch protected categories.
- Grievance and whistleblowing files: separate access regime; tightly restricted.
- Training records: useful for both HR and compliance; integrate with role-based access controls.

### 7. Employee monitoring

The most legally fraught area. ECtHR has set the European baseline:

- **Bărbulescu (2017)**: monitoring of employee instant-messaging without clear prior notice and without proportionality assessment violates Article 8 ECHR.
- **López Ribalda (2019, Grand Chamber)**: covert CCTV in a workplace can be lawful but only with serious suspicion, narrow scope, short duration, and absence of practicable alternatives. The lack of prior notice was a heightened factor for review.
- **Antović and Mirković (2017)**: video monitoring of university auditoriums was disproportionate.

Operational rules:
- Necessity test before any monitoring.
- Proportionality: scope, intrusiveness, duration.
- Transparency: prior written notice, with specifics, signed acknowledgement where possible.
- Less-intrusive alternatives considered first.
- Works council / employee representative consultation per Member State law.
- DPIA for any systematic monitoring.
- No covert monitoring except in extreme cases with DPO and Legal sign-off.
- Audit log of monitoring access.

Common monitoring tools and assessments:

| Tool | Typical assessment |
|------|-------------------|
| Email content scanning for DLP | Proportionate if scoped to security; must avoid private content monitoring |
| Web traffic / network logs | Proportionate at infrastructure level; not for productivity surveillance |
| Productivity software (keystroke timers, screenshots, app-time tracking) | Highly disproportionate in most cases; CNIL and AEPD have rejected |
| Call recording (sales, support) | With prior notice to employees and customers; necessity tested |
| Vehicle telematics | Proportionate for fleet safety; off-duty and after-hours masking |
| Building access logs | Proportionate; retention limited |
| CCTV in workplace | See `cctv-surveillance.md` |
| Mood / wellbeing analytics | Proportionate only with explicit consent and individual control |

### 8. BYOD and MDM

Bring-your-own-device introduces complexity: the employer needs to protect corporate data, the employee owns the device.

Patterns:
- **Containerisation**: corporate data in a container (Microsoft Intune, Workspace ONE, Google Endpoint Management) with employer policy applied only to the container.
- **MAM (mobile application management) without MDM**: employer manages corporate apps without controlling the device.
- **Strict device management**: employer-issued device with MDM; not BYOD.

Rules:
- BYOD policy disclosed before enrolment.
- Wipe scope limited to corporate container.
- Employee retains control over personal data on the device.
- Off-boarding: specific corporate-data wipe; no impact on personal photos, messages, contacts.
- DPIA where MDM has visibility into personal apps or location.

### 9. Sickness, absence, and health-related processing

- Reason for absence: minimum necessary disclosure; line manager need not learn diagnosis, only fitness-for-work and adjustments needed.
- Occupational physician: separate role under professional secrecy; channel for medical detail.
- Return-to-work assessments: documented; access restricted.
- Long-term illness: reasonable adjustments process; data minimisation.
- Mental health support / EAP: separate processor; no manager visibility.

### 10. Equality monitoring and diversity data

Where the controller monitors workforce diversity (gender, ethnicity, disability, sexual orientation, religion), the data is special category and requires Article 9(2)(a) explicit consent or Member State law authorisation under (b)/(g)/(j). Practical rules:
- Voluntary, anonymised aggregate reporting where possible.
- Strict access control.
- Separate from individual personnel files.
- Cannot be used in individual decisions; technical separation enforced.

### 11. Background checks and CRC (criminal records)

Article 10 GDPR governs criminal data: processing only under official authority or where authorised by EU/MS law providing appropriate safeguards. Member State variations:

- Some states (UK, Germany, Italy) permit CRC for specific roles.
- Disclosure must be proportionate to the role.
- Records retention limited to what is necessary for the role-eligibility decision.
- Self-disclosure without verification is generally not "criminal records processing" but still personal data.

### 12. Whistleblowing

Directive (EU) 2019/1937 on whistleblowing requires confidential reporting channels. Privacy considerations:
- The whistleblower's identity is protected.
- The accused person retains GDPR rights (subject to investigation integrity).
- Subject access by the accused: balance against rights of others (Article 15(4)).
- Retention: limited; closure of investigation triggers review.
- Transfer to third parties: tightly controlled.

### 13. Internal investigations

Whether for misconduct, fraud, or compliance failure:
- Documented purpose and scope at the outset.
- Lawful basis: (f) legitimate interest with strict balancing, or (c) legal obligation.
- Article 9 if special category emerges (medical absence in fraud probe, for example).
- Subject's right to be informed at an appropriate time (Article 13/14 may be deferred under Article 14(5)(b) if it would prejudice the investigation).
- Privilege considerations.
- Audit log of investigators' access.

### 14. End of employment and post-exit

Off-boarding actions:
- Disable access to corporate systems on the last day; revoke MFA tokens; collect or wipe devices.
- Forwarding rules on email: only with employee written consent and time-limited; otherwise auto-reply with the new contact.
- Personal files, photographs from team events: subject to ongoing rights.
- Reference policy: typically factual confirmation only, in writing.
- Retention of personnel records: per Member State labour law (often 5–10 years for tax-relevant; longer for pension).
- Re-employment list / talent pool: with consent and an opt-out.
- LinkedIn-style endorsements posted by the employer: stop processing on request.

### 15. References

Practical rules:
- Provide factual confirmations only (dates, role, last salary if law permits) unless the employee consents to fuller content.
- Refused or limited references must be defensible.
- The reference is also personal data of the new employer's prospect — Article 15 applies to the requester.
- Do not include unsubstantiated subjective judgments that could expose the controller to liability.

### 16. Workforce analytics and AI

Employer-side analytics on workforce data (attrition prediction, performance modelling, candidate ranking) typically:
- requires DPIA;
- triggers Article 22 if decisions are based solely on automated processing with significant effect;
- is high-risk under EU AI Act Annex III for employment-related uses;
- requires bias testing and explainability;
- requires worker consultation in many Member States;
- benefits from layered review with human decision-makers.

### 17. Subject access rights specifics

| Right | Employment specifics |
|-------|--------------------|
| Article 15 | Employees may request access to their personnel file. Provide; redact third parties; the employee's own input remains. |
| Article 16 | Factual rectification. Opinion is not rectified but the employee may add a counter-statement. |
| Article 17 | Limited by retention obligations under labour, tax, pension law. |
| Article 18 | Useful during disputes; does not stop legal-claim processing. |
| Article 20 | Limited; payroll data on contract may be portable. |
| Article 21 | Limited where processing is contract-based. |
| Article 22 | Triggered by automated screening and ranking tools. |

### 18. Cross-border employee data flows

Multinational HR systems (Workday, SAP SuccessFactors, Oracle HCM, BambooHR, Personio):
- Cloud processor under Article 28.
- Cross-border transfer assessment per `07-international-transfers`.
- Data residency configuration.
- Sub-processor management.
- Joint-controller analysis where the global HQ exercises HR policy decisions for Member State subsidiaries.

### 19. KVKK comparator

Türkiye'deki istihdam, KVKK ile İş Kanunu hükümlerinin etkileşimine tabidir. KVK Kurulu, işveren izleme ve özlük dosyası saklama hakkında kararlar yayımlamıştır. Çoğu özlük dosyası belgesi 10 yıllık saklamaya tabidir.

### 20. Documentation pack

For HR programmes:
- Employee privacy notice (Article 13) per country.
- ROPA entries for each HR processing activity.
- DPIA for monitoring, AI, large-scale changes.
- Article 28 contracts with all HR vendors.
- Member State Article 88 rule mapping.
- Works council consultation records.
- Background-check policy and Article 10 basis.
- Whistleblowing policy.
- BYOD/MDM policy.
- Off-boarding runbook.

---

## Türkçe

### 1. Kapsam

Bu belge, çalışan yaşam döngüsü boyunca kişisel veri işlemeyi kapsar: işe alım, işe başlama, oryantasyon, performans, öğrenme, ücretlendirme, yan haklar, izin ve devamsızlık, disiplin, mesleki tıp, rol değişikliği, ayrılan, istihdam sonrası referanslar ve dava/düzenleyici bağlamlar.

### 2. Madde 88 — Üye Devlet hukuku katmanı

Madde 88 GDPR, Üye Devletlerin yasa veya toplu sözleşme yoluyla çalışanların kişisel verilerinin işlenmesi konusunda daha spesifik kurallar sağlamasına izin verir.

- **Almanya** — Bundesdatenschutzgesetz §26.
- **Fransa** — Code du travail, Loi Informatique et Libertés Madde 88.
- **İtalya** — Statuto dei Lavoratori Madde 4.
- **İspanya** — Estatuto de los Trabajadores; LOPDGDD Madde 89.
- **Hollanda** — UAVG.
- **Türkiye** — KVKK ve İş Kanunu hükümleri.

### 3. Hukuki temeller

EDPB Opinion 2/2017, istihdam ilişkisinde rızanın güç dengesizliği nedeniyle nadiren özgürce verildiğini vurgular.

| Faaliyet | Madde 6 | Madde 9 özel kategori ise |
|----------|---------|---------------------------|
| Bordro | (b) sözleşme / (c) yasal yükümlülük | yok, sağlık kesintileri hariç |
| Vergi ve sosyal güvenlik | (c) yasal yükümlülük | yok |
| Performans yönetimi | (b) sözleşme | yok |
| Eğitim | (b) sözleşme / (f) meşru menfaat | yok |
| İş sağlığı ve güvenliği kayıtları | (c) yasal yükümlülük | (b)/(h)/(i) |
| Disiplin | (b) sözleşme / (f) meşru menfaat | (b)/(g) |
| Hastalık devamsızlığı | (c) yasal yükümlülük | (b)/(h) |
| Geçmiş kontrolleri | (b) sözleşme / (c) yasal / (f) meşru | (b) cezai veri için + ÜD hukuku |
| Çeşitlilik izleme | (a) rıza | (a) açık rıza |
| İhbar (whistleblowing) | (c) yasal yükümlülük | (b) ve (g) |
| İç dizin / org şeması | (f) meşru menfaat | yok |
| Çalışan izleme | (f) meşru menfaat sıkı dengelemeyle | (b)/(g) |

### 4. İşe alım

- ATS kayıtları: yalnızca gerekli olanı saklayın.
- Başarısız adaylar: kısa saklama (genellikle 6 ay).
- AI destekli tarama araçları: Madde 22 analizi, AB AI Yasası yüksek risk yükümlülükleri, önyargı testi.

### 5. İşe başlama ve oryantasyon

Yalnızca gerekli olanı toplayın:
- kimlik ve çalışma hakkı belgeleri;
- bordro için banka bilgileri;
- acil durum iletişimi;
- ilgili nitelikler;
- yan hak kayıt seçimleri.

İşe başlamada kapsamlı bir Madde 13 çalışan gizlilik bildirimi sağlayın.

### 6. Performans, disiplin, şikayet

- Performans değerlendirmeleri kişisel veridir; konu erişimi uygulanır.
- Disiplin kayıtları hassastır.
- Şikayet ve ihbar dosyaları: ayrı erişim rejimi.

### 7. Çalışan izleme

İHAM Avrupa temel çizgisini belirledi:

- **Bărbulescu (2017)**: önceden net bildirim olmadan çalışanın anlık mesajlaşmasının izlenmesi Madde 8 İHAS'ı ihlal eder.
- **López Ribalda (2019, Büyük Daire)**: bir işyerinde gizli CCTV yalnızca ciddi şüphe, dar kapsam, kısa süre ve uygulanabilir alternatiflerin yokluğuyla yasal olabilir.
- **Antović ve Mirković (2017)**: üniversite amfilerinin video izlemesi orantısızdı.

| Araç | Tipik değerlendirme |
|------|---------------------|
| DLP için e-posta içeriği taraması | Güvenliğe kapsamlandığında orantılı |
| Web trafiği / ağ günlükleri | Altyapı düzeyinde orantılı |
| Verimlilik yazılımı (tuş vuruşu zamanlayıcıları, ekran görüntüleri, uygulama-zaman izleme) | Çoğu durumda son derece orantısız |
| Çağrı kaydı (satış, destek) | Çalışanlara ve müşterilere önceden bildirimle |
| Araç telematiği | Filo güvenliği için orantılı |
| Bina erişim günlükleri | Orantılı; saklama sınırlı |
| İşyerinde CCTV | Bkz. `cctv-surveillance.md` |
| Ruh hali / refah analitiği | Yalnızca açık rıza ile orantılı |

### 8. BYOD ve MDM

- **Konteynerleştirme**: kurumsal veri bir konteynerde, yalnızca konteynere uygulanan işveren politikası.
- **MDM olmadan MAM**: işveren cihazı kontrol etmeden kurumsal uygulamaları yönetir.
- **Sıkı cihaz yönetimi**: işveren tarafından verilen MDM'li cihaz; BYOD değil.

### 9. Hastalık, devamsızlık ve sağlıkla ilgili işleme

- Devamsızlık nedeni: minimum gerekli açıklama.
- Mesleki hekim: mesleki gizlilik altında ayrı rol.
- İşe dönüş değerlendirmeleri.

### 10. Eşitlik izleme ve çeşitlilik verisi

İşgücü çeşitliliği izlendiğinde, veri özel kategori olur ve Madde 9(2)(a) açık rıza veya (b)/(g)/(j) altında Üye Devlet hukuku yetkilendirmesi gerektirir.

### 11. Geçmiş kontrolleri ve cezai sicil (CRC)

Madde 10 GDPR cezai veriyi yönetir.

### 12. İhbar (whistleblowing)

Direktif (AB) 2019/1937 gizli raporlama kanalları gerektirir.

### 13. İç soruşturmalar

- Başlangıçta belgelenmiş amaç ve kapsam.
- Hukuki temel: (f) sıkı dengelemeyle meşru menfaat veya (c) yasal yükümlülük.
- Madde 9 özel kategori ortaya çıkarsa.
- Konunun uygun bir zamanda bilgilendirilme hakkı.

### 14. İstihdamın sonu ve çıkış sonrası

- Son gün kurumsal sistemlere erişimi devre dışı bırakın.
- E-postada yönlendirme kuralları: yalnızca çalışan yazılı rızasıyla ve süreli.
- Personel kayıtlarının saklanması: Üye Devlet iş hukukuna göre.

### 15. Referanslar

- Yalnızca olgusal teyitler sağlayın.
- Reddedilen veya sınırlı referanslar savunulabilir olmalıdır.

### 16. İşgücü analitiği ve AI

İşveren tarafı işgücü verisi analitiği genellikle:
- VKD gerektirir;
- Madde 22'yi tetikler;
- Annex III altında AB AI Yasası yüksek risktir;
- önyargı testi ve açıklanabilirlik gerektirir;
- birçok Üye Devlette işçi danışması gerektirir.

### 17. Konu erişim hakları özellikleri

| Hak | İstihdam özellikleri |
|-----|--------------------|
| Madde 15 | Çalışanlar özlük dosyalarına erişim talep edebilir. |
| Madde 16 | Olgusal düzeltme. |
| Madde 17 | İş, vergi, emeklilik hukuku altındaki saklama yükümlülükleriyle sınırlı. |
| Madde 18 | Anlaşmazlıklar sırasında yararlı. |
| Madde 20 | Sınırlı; sözleşme bordro verisi taşınabilir olabilir. |
| Madde 21 | Sözleşme tabanlı işleme yapıldığında sınırlı. |
| Madde 22 | Otomatik tarama ve sıralama araçları tarafından tetiklenir. |

### 18. Sınır ötesi çalışan veri akışları

Çok uluslu İK sistemleri (Workday, SAP SuccessFactors, Oracle HCM, BambooHR, Personio):
- Madde 28 altında bulut veri işleyen.
- `07-international-transfers` başına sınır ötesi aktarım değerlendirmesi.

### 19. KVKK karşılaştırması

Türkiye'deki istihdam, KVKK ile İş Kanunu hükümlerinin etkileşimine tabidir. KVK Kurulu, işveren izleme ve özlük dosyası saklama hakkında kararlar yayımlamıştır. Çoğu özlük dosyası belgesi 10 yıllık saklamaya tabidir.

### 20. Belgeleme paketi

İK programları için:
- Ülke başına çalışan gizlilik bildirimi (Madde 13).
- Her İK işleme faaliyeti için ROPA girişleri.
- İzleme, AI, büyük ölçekli değişiklikler için VKD.
- Tüm İK satıcılarıyla Madde 28 sözleşmeleri.
- Üye Devlet Madde 88 kural eşleştirmesi.
- İşyeri konseyi danışma kayıtları.
- Geçmiş kontrol politikası ve Madde 10 temeli.
- İhbar politikası.
- BYOD/MDM politikası.
- Çıkış runbook'u.
