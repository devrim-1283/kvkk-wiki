---
title:
  en: "Personal Data Breach Notification Form"
  tr: "Kişisel Veri İhlali Bildirim Formu"
section: "08-breach-management"
document_id: "BR-FORM-001"
owner: "Data Protection Officer"
classification: "Internal — Restricted"
version: "1.0"
last_review: "2026-05-08"
next_review: "2027-05-08"
language: ["en", "tr"]
references:
  - "GDPR Art. 33(3) — Content of notification"
  - "GDPR Art. 33(4) — Phased notification"
  - "GDPR Art. 33(5) — Internal documentation"
  - "EDPB Guidelines 9/2022"
---

## English

### Purpose of this form

This form is the controller's primary working artefact for the Article 33 notification. It mirrors the field structure used by major supervisory authority online portals (Irish DPC, CNIL, BfDI, AEPD, ICO) and the Turkish KVKK breach notification structure, so that data captured here can be transcribed into any portal without re-discovery work.

The form is fillable inside the incident management system. The DPO is the form owner. The CSIRT lead and Engineering on-call provide source data. Legal reviews before submission. The executive sponsor is informed of submission.

### Section A — Identification

| Field | Value |
|-------|-------|
| Internal breach ID | `BR-YYYY-NNNN` |
| Notification reference (assigned by SA) | (filled after submission) |
| Date and time of awareness (UTC) | YYYY-MM-DDTHH:MMZ |
| Date and time of underlying event (if known, UTC) | YYYY-MM-DDTHH:MMZ |
| Notification type | Initial / Phased follow-up / Final |
| Notifying entity legal name | |
| Notifying entity registration number | |
| Notifying entity registered address | |
| Lead supervisory authority | |
| Concerned supervisory authorities (one-stop-shop) | |
| Article 27 representative (if non-EU controller) | |
| DPO name | |
| DPO email | |
| DPO phone | |
| Alternative contact name | |
| Alternative contact email | |

### Section B — Nature of the breach

| Field | Value |
|-------|-------|
| Type of breach (multi-select) | Confidentiality / Integrity / Availability |
| Cause (multi-select) | Malicious external / Malicious insider / Negligent insider / System failure / Third-party processor / Loss / Theft / Unknown |
| Vector / mechanism (free text, factual) | |
| Was the data subject to encryption? | Yes / No / Partial |
| Was the encryption key compromised? | Yes / No / Unknown |
| Was the data subject to pseudonymisation? | Yes / No / Partial |
| Was multi-factor authentication in place on affected access paths? | Yes / No / Partial |
| Backup state | Available, untouched / Partially affected / Fully affected |
| Sustained duration of the compromise (estimated) | |

### Section C — Categories and approximate numbers

| Field | Value |
|-------|-------|
| Categories of data subjects (multi-select) | Customers / Employees / Job applicants / Children / Patients / Vulnerable persons / Public officials / Other (specify) |
| Approximate number of data subjects | |
| Estimation method | Database query / Log-based estimate / Vendor report / Other (specify) |
| Categories of personal data (multi-select) | Identification (name, DOB, ID number) / Contact (email, phone, address) / Financial (IBAN, card number) / Health / Genetic / Biometric / Sexual orientation / Religious / Political opinion / Trade union / Criminal / Children's data / Location / Online identifiers (IP, cookies) / Authentication credentials / Behavioural / Other (specify) |
| Approximate number of records | |
| Geographic distribution of data subjects | |
| Were any Article 9 special categories involved? | Yes / No, with detail |
| Were any Article 10 criminal data involved? | Yes / No |

### Section D — Likely consequences

Describe the likely consequences for affected data subjects, in plain language. Address:

- Identity theft potential.
- Financial loss potential.
- Reputational harm.
- Discrimination risk.
- Physical danger risk.
- Loss of access to essential services.
- Loss of confidentiality of professional secrecy.
- Other harms specific to the affected categories.

| Field | Value |
|-------|-------|
| ENISA severity score (numeric) | |
| ENISA severity level (Low / Medium / High / Very High) | |
| Likely consequences narrative | (free text) |
| Will the breach trigger Article 34 communication to data subjects? | Yes / No / Under assessment |
| If no Article 34 communication, which exemption applies? | Encryption / Subsequent measures / Disproportionate effort / Not high risk / N/A |

### Section E — Measures taken or proposed

| Field | Value |
|-------|-------|
| Immediate containment actions taken | (free text + ticket references) |
| Eradication actions completed or planned | |
| Recovery actions completed or planned | |
| Mitigations specifically for data subjects | (e.g. forced password reset, credit monitoring offer, identity protection service) |
| Notifications to processors and sub-processors | |
| Notifications to law enforcement | |
| Notifications to cyber insurer | |
| Coordinated public communication plan | |

### Section F — Cross-border processing

| Field | Value |
|-------|-------|
| Is the processing cross-border under Art. 4(23)? | Yes / No |
| Member States of affected data subjects | |
| Lead SA designation reasoning | |
| Concerned SAs identified | |
| Joint controller? | Yes / No, identify other controller(s) |
| Processor(s) involved | List names and roles |

### Section G — Phased notification

If phased notification under Article 33(4) is invoked:

| Field | Value |
|-------|-------|
| Items not yet known | |
| Reason for delay | |
| Target date for follow-up | |
| Investigation milestones | |

### Section H — Documentation cross-reference

| Field | Value |
|-------|-------|
| Forensic report ID | |
| Incident timeline document | |
| ENISA scoring worksheet | |
| Internal breach register entry | |
| CAPA tickets | |
| Communications artefacts | |
| Legal privilege markings | |

### Section I — Approvals

| Approver | Name | Role | Date and time |
|----------|------|------|---------------|
| DPO | | | |
| Legal | | | |
| CISO | | | |
| Executive sponsor | | | |

---

## Worked example — Ransomware affecting 612 employee HR records

### Section A — Identification (worked example)

| Field | Value |
|-------|-------|
| Internal breach ID | `BR-2026-0142` |
| Notification reference | (to be filled by SA) |
| Date and time of awareness (UTC) | 2026-04-22T07:14Z |
| Date and time of underlying event (UTC) | 2026-04-21T22:30Z (initial intrusion estimated) |
| Notification type | Initial |
| Notifying entity legal name | Aegis Logistics A.Ş. (example) |
| Notifying entity registration number | İstanbul Trade Registry No. 123456-5 |
| Notifying entity registered address | Maslak Mah., İstanbul, Türkiye |
| Lead supervisory authority | Irish DPC (main establishment in Dublin) |
| Concerned supervisory authorities | KVKK (TR), CNIL (FR), AEPD (ES), Garante (IT) |
| Article 27 representative | n/a |
| DPO name | Eda Korkmaz |
| DPO email | dpo@aegis-logistics.example |
| DPO phone | +90 212 555 0142 |
| Alternative contact name | Faruk Demir, Deputy DPO |
| Alternative contact email | dpo-deputy@aegis-logistics.example |

### Section B — Nature of the breach (worked example)

| Field | Value |
|-------|-------|
| Type of breach | Confidentiality + Availability |
| Cause | Malicious external (LockBit-derivative ransomware via initial access broker) |
| Vector | Compromised VPN credentials (phished from a contractor) used to deploy ransomware on the internal HR file server `hrfs01.corp.aegis.local`. Exfiltration occurred 2026-04-21T23:18Z to 2026-04-22T01:42Z via outbound HTTPS to two attacker-controlled IPs identified in egress logs. Encryption deployed 2026-04-22T02:10Z. |
| Was the data subject to encryption? | At rest: yes (BitLocker volume encryption). In active session at time of compromise: no (decrypted by mounted user session). |
| Was the encryption key compromised? | No (BitLocker key not extracted; ransomware operated on decrypted active volume). |
| Was the data subject to pseudonymisation? | No |
| MFA on affected access paths? | Partial — VPN required MFA but the contractor's MFA token was active at time of phishing (real-time relay attack). |
| Backup state | Untouched — daily immutable backups in segregated storage, restored within 14 hours. |
| Sustained duration | ~3 hours 40 minutes from initial intrusion to encryption. Ransom note discovered at 2026-04-22T07:14Z when first employee logged in. |

### Section C — Categories and approximate numbers (worked example)

| Field | Value |
|-------|-------|
| Categories of data subjects | Employees (current and former, last 7 years) |
| Approximate number of data subjects | 612 |
| Estimation method | HRIS database COUNT(*) of employee_records WHERE active OR termination_date >= 2019-04-22, cross-checked against the file server's `hr_records` directory listing recovered from immutable backup. Confidence: high. |
| Categories of personal data | Identification (name, DOB, national ID); Contact (home address, phone, personal email); Financial (IBAN, salary, tax ID); Health (occupational health questionnaires for 84 employees in roles requiring fitness certification); Other (performance reviews, disciplinary letters, references) |
| Approximate number of records | 612 employee folders, comprising approximately 14,800 individual documents |
| Geographic distribution | TR 412, FR 78, ES 64, IT 41, IE 17 |
| Article 9 special categories? | Yes — occupational health data of 84 employees |
| Article 10 criminal data? | No |

### Section D — Likely consequences (worked example)

ENISA severity score: 3.7 / Level: High.

Plain-language consequences:
- Identity theft is plausible: national IDs combined with DOB and home addresses appear on dark-web extortion site preview.
- Financial fraud possible via IBAN-based mandate fraud.
- Special-category occupational health data exposure may cause distress and discrimination risk.
- Salary disclosure may cause workplace tension.
- Pre-employment references include third-party personal data of referees.

Article 34 communication: Yes, required.

### Section E — Measures taken or proposed (worked example)

- Containment: Network isolation of `hrfs01` and adjacent file servers at 2026-04-22T07:32Z. VPN access for the contractor account revoked 07:35Z. All active VPN sessions for contractors terminated 07:48Z.
- Eradication: Reimaged `hrfs01`. Reset all domain administrator credentials. Forced reset of all 612 affected employees' enterprise credentials. Rotated VPN PSK and replaced phishing-resistant MFA (FIDO2) for all contractor accounts.
- Recovery: Restored `hrfs01` from immutable backup taken 2026-04-21T03:00Z; integrity validated via hash comparison.
- Mitigations for data subjects: Forced credential reset; 24-month identity protection and credit monitoring service offered free of charge; dedicated DPO hotline; advice on bank mandate vigilance; offer of reissue of national ID via state assistance.
- Processor notifications: Payroll processor and benefits administrator notified at 09:00Z.
- Law enforcement: Report filed with Turkish Cybercrime Department and Europol EC3 at 12:00Z.
- Cyber insurer: AIG notified at 13:30Z; counsel engaged.
- Public communication: Coordinated with Communications; press release planned for 2026-04-25 after individual notifications begin.

### Section F — Cross-border processing (worked example)

- Cross-border under Article 4(23): Yes.
- Member States of affected data subjects: TR, FR, ES, IT, IE.
- Lead SA: Irish DPC (main establishment Dublin since 2022 reorganisation).
- Concerned SAs: KVKK (TR), CNIL (FR), AEPD (ES), Garante (IT).
- Joint controller: No.
- Processors: Aegis Cloud HRIS (Article 28) — not the source of compromise; payroll processor — informed; benefits administrator — informed.

### Section G — Phased notification (worked example)

Initial notification submitted at H+62 (2026-04-24T21:00Z). Items still under investigation at submission:
- Forensic confirmation of exfiltration completeness (currently estimated at 80% of folder contents).
- Final list of all dark-web posting timestamps.
- Identification of initial access broker.

Target date for follow-up: 2026-05-01.

### Section H — Documentation cross-reference (worked example)

| Field | Value |
|-------|-------|
| Forensic report ID | FOR-2026-0142 (Mandiant interim) |
| Incident timeline document | TL-2026-0142 |
| ENISA scoring worksheet | ENISA-2026-0142 |
| Internal breach register entry | BR-REG-2026-0142 |
| CAPA tickets | CAPA-2026-0331, CAPA-2026-0332, CAPA-2026-0333 |
| Communications artefacts | COMMS-2026-0142 (employee letter EN/TR/FR/ES/IT) |
| Legal privilege markings | Privileged & Confidential — under instruction of General Counsel |

### Section I — Approvals (worked example)

| Approver | Name | Role | Date and time |
|----------|------|------|---------------|
| DPO | Eda Korkmaz | DPO | 2026-04-24T20:50Z |
| Legal | Selim Aydın | General Counsel | 2026-04-24T20:55Z |
| CISO | Marco Rossi | CISO | 2026-04-24T20:58Z |
| Executive sponsor | Ayşe Yılmaz | COO | 2026-04-24T21:00Z |

---

## Türkçe

### Bu formun amacı

Bu form, Madde 33 bildirimi için veri sorumlusunun birincil çalışma yapıtıdır. Büyük denetim makamı çevrimiçi portallarının (İrlanda DPC, CNIL, BfDI, AEPD, ICO) ve Türk KVKK ihlal bildirim yapısının kullandığı alan yapısını yansıtır, böylece burada yakalanan veriler herhangi bir portala yeniden keşif çalışması olmadan aktarılabilir.

Form, olay yönetim sisteminde doldurulabilir. VKK Sorumlusu form sahibidir. CSIRT lideri ve Mühendislik nöbetçisi kaynak verileri sağlar. Hukuk gönderimden önce inceler. Yönetici sponsor gönderim hakkında bilgilendirilir.

### Bölüm A — Tanımlama

| Alan | Değer |
|------|-------|
| İç ihlal kimliği | `BR-YYYY-NNNN` |
| Bildirim referansı (DM tarafından atanır) | (gönderim sonrası doldurulur) |
| Farkındalık tarih ve saati (UTC) | YYYY-MM-DDTHH:MMZ |
| Temel olay tarih ve saati (biliniyorsa, UTC) | YYYY-MM-DDTHH:MMZ |
| Bildirim türü | İlk / Aşamalı takip / Nihai |
| Bildiren kuruluş tüzel adı | |
| Bildiren kuruluş tescil numarası | |
| Bildiren kuruluş tescilli adresi | |
| Baş denetim makamı | |
| İlgili denetim makamları (tek pencere) | |
| Madde 27 temsilcisi (AB dışı veri sorumlusu ise) | |
| VKK adı | |
| VKK e-posta | |
| VKK telefon | |
| Alternatif iletişim adı | |
| Alternatif iletişim e-posta | |

### Bölüm B — İhlalin niteliği

| Alan | Değer |
|------|-------|
| İhlal türü (çoklu seçim) | Gizlilik / Bütünlük / Erişilebilirlik |
| Neden (çoklu seçim) | Kötü niyetli dış / Kötü niyetli iç / İhmalkâr iç / Sistem arızası / Üçüncü taraf veri işleyen / Kayıp / Hırsızlık / Bilinmeyen |
| Vektör / mekanizma (serbest metin, olgusal) | |
| Veri şifrelendi mi? | Evet / Hayır / Kısmen |
| Şifreleme anahtarı tehlikeye girdi mi? | Evet / Hayır / Bilinmiyor |
| Veri takma adlandırmaya tabi miydi? | Evet / Hayır / Kısmen |
| Etkilenen erişim yollarında çok faktörlü kimlik doğrulama? | Evet / Hayır / Kısmen |
| Yedekleme durumu | Mevcut, dokunulmamış / Kısmen etkilenmiş / Tamamen etkilenmiş |
| Tehlikenin sürdüğü süre (tahmini) | |

### Bölüm C — Kategoriler ve yaklaşık sayılar

| Alan | Değer |
|------|-------|
| İlgili kişi kategorileri | Müşteri / Çalışan / İş başvuru sahibi / Çocuk / Hasta / Savunmasız / Kamu görevlisi / Diğer |
| Yaklaşık ilgili kişi sayısı | |
| Tahmin yöntemi | Veritabanı sorgusu / Günlük tabanlı tahmin / Tedarikçi raporu / Diğer |
| Kişisel veri kategorileri | Tanımlama / İletişim / Finansal / Sağlık / Genetik / Biyometrik / Cinsel yönelim / Dinî / Siyasi görüş / Sendika / Cezai / Çocuk verisi / Konum / Çevrimiçi tanımlayıcılar / Kimlik bilgisi / Davranışsal / Diğer |
| Yaklaşık kayıt sayısı | |
| İlgili kişilerin coğrafi dağılımı | |
| Madde 9 özel kategoriler dahil mi? | Evet / Hayır, ayrıntıyla |
| Madde 10 cezai veriler dahil mi? | Evet / Hayır |

### Bölüm D — Olası sonuçlar

Etkilenen ilgili kişiler için olası sonuçları sade dille açıklayın. Şunları ele alın:

- Kimlik hırsızlığı potansiyeli.
- Finansal kayıp potansiyeli.
- İtibar zararı.
- Ayrımcılık riski.
- Fiziksel tehlike riski.
- Temel hizmetlere erişim kaybı.
- Mesleki gizliliğin gizliliğinin kaybı.
- Etkilenen kategorilere özgü diğer zararlar.

| Alan | Değer |
|------|-------|
| ENISA önem puanı (sayısal) | |
| ENISA önem düzeyi | |
| Olası sonuçlar açıklaması | (serbest metin) |
| İhlal Madde 34 iletişimini tetikleyecek mi? | Evet / Hayır / Değerlendirme altında |
| Madde 34 iletişimi yoksa hangi muafiyet uygulanır? | Şifreleme / Sonraki önlemler / Orantısız çaba / Yüksek risk değil / Yok |

### Bölüm E — Alınan veya önerilen önlemler

| Alan | Değer |
|------|-------|
| Acil kontrol altına alma eylemleri | (serbest metin + bilet referansları) |
| Tamamlanan veya planlanan yok etme eylemleri | |
| Tamamlanan veya planlanan kurtarma eylemleri | |
| İlgili kişilere yönelik özel azaltmalar | |
| Veri işleyen ve alt işleyen bildirimleri | |
| Kolluk bildirimleri | |
| Siber sigorta bildirimi | |
| Koordineli kamu iletişim planı | |

### Bölüm F — Sınır ötesi işleme

| Alan | Değer |
|------|-------|
| Madde 4(23) altında sınır ötesi mi? | Evet / Hayır |
| Etkilenen ilgili kişilerin Üye Devletleri | |
| Baş DM atama gerekçesi | |
| Tanımlanan ilgili DM'ler | |
| Ortak veri sorumlusu? | Evet / Hayır |
| Dahil veri işleyen(ler) | |

### Bölüm G — Aşamalı bildirim

| Alan | Değer |
|------|-------|
| Henüz bilinmeyen öğeler | |
| Gecikme nedeni | |
| Takip için hedef tarih | |
| Soruşturma kilometre taşları | |

### Bölüm H — Belge çapraz referansı

| Alan | Değer |
|------|-------|
| Adli rapor kimliği | |
| Olay zaman çizelgesi belgesi | |
| ENISA puanlama çalışma sayfası | |
| İç ihlal kayıt girdisi | |
| CAPA biletleri | |
| İletişim yapıtları | |
| Hukuki ayrıcalık işaretleri | |

### Bölüm I — Onaylar

| Onaylayan | Ad | Rol | Tarih ve saat |
|-----------|----|-----|--------------|
| VKK | | | |
| Hukuk | | | |
| CISO | | | |
| Yönetici sponsor | | | |

### Çalışılmış örnek — 612 çalışan İK kaydını etkileyen fidye yazılımı

(Yukarıdaki çalışılmış örnek bölümleri bilgileri içerir; Türkçe çeviri için yukarıdaki İngilizce çalışılmış örneğe başvurulur ve ihtiyaç duyulduğunda Türkçe DPO ofisi tarafından çevrilir. Olay zaman damgaları, etkilenen ilgili kişi sayıları ve risk değerlendirmesi aynıdır: Aegis Logistics A.Ş., 612 çalışan İK kaydı, ENISA Yüksek seviye, Madde 34 iletişimi gerekli.)
