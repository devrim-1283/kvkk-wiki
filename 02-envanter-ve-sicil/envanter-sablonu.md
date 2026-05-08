---
Doküman / Document: Kişisel Veri İşleme Envanteri — Doldurulabilir Şablon / Personal Data Processing Inventory — Fillable Template
Bölüm / Section: 02-envanter-ve-sicil
Sahip / Owner: KVKK Sorumlusu / KVKK Officer
Onaylayan / Approved by: Hukuk Müdürü + KVKK Komitesi / Head of Legal + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş / Annual + triggered
İlgili Mevzuat / Legal Reference: 6698 sayılı KVKK m.4-6, m.10, m.12, m.16 / Law No. 6698 (KVKK) Art. 4-6, 10, 12, 16; Veri Sorumluları Sicili Hakkında Yönetmelik MADDE 4(h), 5, 9 / Regulation on the Data Controllers' Registry Art. 4(h), 5, 9; Saklama ve İmha Yön. MADDE 5 / Erasure-Destruction Regulation Art. 5
---

## English

# Personal Data Processing Inventory — Template

This file contains a **ready-to-use** inventory template, populated with three sample rows (HR recruitment, customer order, CCTV). New rows follow the same format.

## 1. Template Table

> The table is wide; horizontal scrolling may be required in markdown viewers. The CSV header row is given in section 3 and can be loaded into Excel.

| Process ID / Süreç ID | Process Name / Süreç Adı | Business Unit / İş Birimi | Process Owner / Süreç Sahibi | Data Subject Group / Veri Konusu Kişi Grubu | Data Category / Veri Kategorisi | Personal Data Items / Kişisel Veri Öğeleri | Special Category (Y/N) / Özel Nitelikli (E/H) | Processing Purpose / İşleme Amacı | Legal Ground / Hukuki Sebep | Collection Method / Toplama Yöntemi | Storage Medium / Kayıt Ortamı | Internal Recipients / Aktarım Yapılan İç Birim | Domestic Recipient / Recipient Group / Yurt İçi Alıcı | Cross-Border Transfer (Y/N) / Yurt Dışı Aktarım | Foreign Recipient + Country / Yurt Dışı Alıcı + Ülke | Cross-Border Legal Basis / Yurt Dışı Hukuki Temel | Retention Period / Saklama Süresi | Retention Rationale / Saklama Gerekçesi | Destruction Method / İmha Yöntemi | Destruction Period / İmha Periyodu | Technical Measures / Teknik Tedbirler | Administrative Measures / İdari Tedbirler | Risk Level / Risk Seviyesi | Related Information Notice / İlgili Aydınlatma Metni | Explicit Consent Required? / Açık Rıza Gerekli mi? | Last Update / Son Güncelleme |
|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|--|
| HR-001 / IK-001 | Candidate Recruitment and CV Management / Çalışan Adayı İşe Alım ve Özgeçmiş Yönetimi | Human Resources / İnsan Kaynakları | Name Surname / HR Director / hr.director@firma.com.tr | Job Candidate / Çalışan Adayı | Identity; Contact; Professional Experience; Education; Visual/Audio | Name-surname, T.R. ID number, date of birth, telephone, e-mail, address, education, work experience, references, photograph, interview notes | N | Evaluation of candidates for open positions; interview; job offer; talent pool management | Necessary for the conclusion of a contract — application stage (Art. 5(2)/c); explicit consent for talent-pool retention | Automated (career site form, e-mail, career portal APIs); non-automated (paper application, events) | Electronic (ATS/HRIS, e-mail server, OneDrive); physical (personnel archive) | HR; hiring manager of the relevant department | Candidate-evaluation firms (ATS provider), legal partner (in case of dispute) | Y | LinkedIn Talent (USA); Greenhouse (USA/EU) | Standard contract + KVKK Board notification; explicit consent where needed | 1 year for non-hired candidates (2 years for talent pool with explicit consent); hired candidates pass to HR-002 | Statute-of-limitations analysis under Labour Law and applicable claims | Erasure (electronic) + destruction (physical) | 6-month periodic destruction calendar | TLS, AES-256 encryption, MFA, role-based access, audit log, ATS security certifications | Confidentiality undertaking, KVKK training, access authorisation matrix | Medium | INF-HR-01 (Recruitment Information Notice) | Y (for talent-pool retention) | 2026-05-08 / KVKK Officer |
| CUS-002 / MUS-002 | E-commerce Order Management and Delivery / E-ticaret Sipariş Yönetimi ve Teslimat | Operations / Customer Service | Name Surname / Operations Manager / ops.manager@firma.com.tr | Customer (natural person); delivery-address holder (may be third party) | Identity; Contact; Customer Transaction; Location; Finance | Name-surname, T.R. ID (for e-invoice), telephone, e-mail, delivery address, order history, payment information (card data tokenised), IP address, device data | N | Order intake; payment collection; delivery; returns; e-invoice issuance; customer service | Performance of contract (Art. 5(2)/c); legal obligation — Tax Procedure Law (VUK), e-invoice legislation (Art. 5(2)/ç); protection of a right (Art. 5(2)/e) | Automated (website, mobile app, call center); non-automated (in-store order form) | Electronic (e-commerce platform, payment PSP, e-invoice provider, CRM); physical (waybill, invoice copies) | Operations, Accounting, Customer Service, IT | Payment PSP, courier company, e-invoice integrator, Tax Office (statutory), legal partner | Y | AWS (Ireland — cloud infrastructure); Sendgrid (USA — transactional e-mail) | Standard contract; AWS DPA; Sendgrid SCC | Financial records 10 years (TTK Art. 82, VUK Art. 253); customer account 10 years from the end of the relationship (TBK Art. 146 limitation) | TTK, VUK, TBK | Erasure (electronic); destruction (paper invoice copies after archive period) | 6-month periodic destruction | TLS, card tokenisation (PCI-DSS), WAF, IDS/IPS, log collection (SIEM), DDoS protection, encrypted backups | KVKK training, confidentiality undertaking, supplier contracts, periodic audits | High | INF-CUS-01 (Customer E-commerce Information Notice) | N (relies on contract performance); separate consent required for marketing | 2026-05-08 / KVKK Officer |
| PHY-001 / FIZ-001 | Closed-Circuit Camera System (CCTV) / Kapalı Devre Kamera Sistemi (CCTV) | Security / Güvenlik | Name Surname / Security Manager / security.manager@firma.com.tr | Employee; visitor; supplier employee; third party (anyone in camera field of view) | Visual/Audio; Location | Image recording (face, clothing, action); timestamp; camera location | N | Building and perimeter security; crime prevention; occupational health and safety; asset protection | Legitimate interest (Art. 5(2)/f) — limited scope and duration; legal obligation for OHS (Art. 5(2)/ç) | Automated (CCTV cameras, NVR/DVR) | Electronic (recording server — corporate DC) | Security; Legal + senior management in case of incident | Authorised law enforcement (with judicial process); insurance company (in case of accident) | N | — | — | 30 days (rotating); incident records retained until incident closure | Legitimate interest balancing (PIA): short period + restricted access | Automatic overwrite; manual erasure or destruction for incident records | 30-day rotation | Access logs, MFA, network segmentation, physical lock on recording device, encrypted recording | Access authorisation (Security only), KVKK training, written process for record requests | Medium | INF-PHY-01 (CCTV Sign + Detailed Notice) | N (relies on legitimate interest) | 2026-05-08 / Security Manager |

## 2. Blank Row Template (For New Process)

Copy and fill the following table:

| Field / Alan | Value / Değer |
|--------------|---------------|
| Process ID / Süreç ID | `[unit_abbrev]-[3-digit serial]` |
| Process Name / Süreç Adı | `...` |
| Business Unit / İş Birimi | `...` |
| Process Owner / Süreç Sahibi | `Name Surname / Title / e-mail` |
| Data Subject Group / Veri Konusu Kişi Grubu | `...` |
| Data Category / Veri Kategorisi | `Identity; Contact; ...` |
| Personal Data Items / Kişisel Veri Öğeleri | `...` |
| Special Category (Y/N) / Özel Nitelikli | `N` |
| Processing Purpose / İşleme Amacı | `Specific, explicit, legitimate purpose statement` |
| Legal Ground / Hukuki Sebep | `KVKK Art. 5(2)/...` or `Explicit Consent` |
| Collection Method / Toplama Yöntemi | `Automated / non-automated / mixed + channel` |
| Storage Medium / Kayıt Ortamı | `Electronic (...) / Physical (...)` |
| Internal Recipients / Aktarım Yapılan İç Birim | `...` |
| Domestic Recipient / Yurt İçi Alıcı | `...` |
| Cross-Border Transfer (Y/N) | `N` |
| Foreign Recipient + Country | `—` (if none) |
| Cross-Border Legal Basis | `—` |
| Retention Period / Saklama Süresi | `... years/months` |
| Retention Rationale / Saklama Gerekçesi | `Statutory reference or limitation analysis` |
| Destruction Method / İmha Yöntemi | `Erasure / Destruction / Anonymisation` |
| Destruction Period / İmha Periyodu | `6 months` (default) |
| Technical Measures / Teknik Tedbirler | `Encryption, log, MFA, ...` |
| Administrative Measures / İdari Tedbirler | `Training, confidentiality, ...` |
| Risk Level / Risk Seviyesi | `Low / Medium / High / Critical` |
| Related Information Notice / Aydınlatma Metni | `INF-...` |
| Explicit Consent Required? / Açık Rıza | `Y/N + rationale` |
| Last Update / Son Güncelleme | `YYYY-MM-DD / Preparer` |

## 3. CSV Header Row (Copy-Paste, Bilingual)

```csv
process_id_surec_id,process_name_surec_adi,business_unit_is_birimi,process_owner_surec_sahibi,data_subject_group_veri_konusu_kisi_grubu,data_category_veri_kategorisi,personal_data_items_kisisel_veri_ogeleri,special_category_ozel_nitelikli,processing_purpose_isleme_amaci,legal_ground_hukuki_sebep,collection_method_toplama_yontemi,storage_medium_kayit_ortami,internal_recipients_aktarim_ic_birim,domestic_recipient_yurtici_alici,cross_border_transfer_yurtdisi_aktarim,foreign_recipient_country_yurtdisi_alici_ulke,cross_border_legal_basis_yurtdisi_hukuki_temel,retention_period_saklama_suresi,retention_rationale_saklama_gerekce,destruction_method_imha_yontemi,destruction_period_imha_periyodu,technical_measures_teknik_tedbirler,administrative_measures_idari_tedbirler,risk_level_risk_seviyesi,information_notice_aydinlatma_metni,explicit_consent_required_acik_riza_gerekli,last_update_son_guncelleme
```

### 3.1 Sample CSV Row

```csv
HR-001,Candidate Recruitment,Human Resources,HR Director,Job Candidate,Identity;Contact;Professional Experience;Education,"name-surname, T.R. ID, telephone, e-mail, education, work experience",N,"Candidate evaluation; interview; job offer","Art. 5(2)/c pre-contract measures; explicit consent for talent pool","Automated (career site); non-automated (paper)","Electronic (ATS, e-mail); physical (personnel)","HR; hiring department","Candidate-evaluation firms, legal partner",Y,"LinkedIn Talent (USA); Greenhouse (USA/EU)","Standard contract + Board notification",1 year (talent pool 2 years),"Statute-of-limitations analysis on job applications",Erasure + destruction,6 months,"TLS, AES-256, MFA, audit log","Confidentiality, KVKK training, authorisation",Medium,INF-HR-01,Y,2026-05-08
```

## 4. Field Definitions (Glossary)

### 4.1 Process ID
A unique internal identifier. Recommended format: `[Unit 2-3 letters]-[3-digit serial]` (e.g., HR-001, CUS-002, IT-014).

### 4.2 Data Subject Group (Reg. Art. 4/n)
"Category of data subjects whose personal data the data controllers process." Typical groups:
- Employee, Job Candidate, Former Employee, Employee Relative
- Customer, Prospect, Former Customer
- Supplier Employee, Supplier Authorised Representative
- Visitor, Intern, Consultant
- Shareholder, Board Member
- Third Party (reference, recipient, guarantor, etc.)
- Child (data subject under 18)

### 4.3 Data Category (Reg. Art. 4/m)
"Class of personal data of one or more groups of data subjects, grouped according to common characteristics of personal data." VERBİS standard categories:

- Identity (name-surname, T.R. ID, date of birth, gender)
- Contact (telephone, e-mail, address)
- Location (GPS, IP, location services)
- Personnel File (personnel-file data)
- Legal Proceeding (case data, power of attorney)
- Customer Transaction (orders, invoices, history)
- Physical Premises Security (CCTV, badge logs)
- Transaction Security (logs, IP, sessions)
- Risk Management (scoring, risk profile)
- Finance (IBAN, tokenised card data, income)
- Professional Experience (CV, education, certifications)
- Marketing (preferences, habits, profile)
- Visual/Audio (photo, voice recording, video)
- Health Data (special category — KVKK Art. 6)
- Sexual Life (special category)
- Criminal Record and Security Measures (special category)
- Biometric Data (special category)
- Genetic Data (special category)
- Philosophical belief, religion, sect, religious denomination (special category)
- Association/foundation/union membership (special category)
- Political opinion (special category)

### 4.4 Legal Ground
One of the clauses of KVKK Art. 5(2) (general data) or Art. 6(2)-(3) (special category). **Explicit consent is the last resort.**

### 4.5 Collection Method (Disclosure Communiqué Art. 5/i)
"Wholly or partly by automated means or non-automated means, where the data forms part of a data filing system" — explicit statement is mandatory.

### 4.6 Recipient / Recipient Group (Reg. Art. 4/a)
"Category of natural or legal persons to whom the personal data is transferred by the data controller." A category (e.g., "Courier companies", "Legal partners") may be used instead of listing each company; however, for cross-border transfers the company + country must be stated explicitly.

### 4.7 Retention Period (Reg. Art. 9/4-5)
- If a period is prescribed by legislation → that period.
- If multiple periods exist → the longest.
- When determining the period (Art. 9/4), consider sectoral practice, duration of the legal relationship, duration of legitimate interest, risk-cost, suitability for keeping up-to-date, statutory obligations, and statute of limitations.

### 4.8 Destruction Method (Erasure-Destruction Reg. Art. 8-10)
- **Erasure (silme):** Making personal data inaccessible and unusable for relevant users.
- **Destruction (yok etme):** Making personal data inaccessible, irretrievable and unusable by anyone.
- **Anonymisation:** Rendering data unrelatable to a specific or identifiable natural person, even when matched with other data.

### 4.9 Destruction Period (Erasure-Destruction Reg. Art. 11)
Periodic destruction must occur at most every **6 months**. Internal policy may set a shorter interval.

### 4.10 Risk Level
- **Low:** General data, small volume, limited sharing, low impact.
- **Medium:** General data, medium volume, external sharing exists, medium impact.
- **High:** Special-category data, large volume, automated decision-making, cross-border transfer.
- **Critical:** Children's data, biometrics, health + large volume, high automated profiling, financial transactions.

## 5. Table Display Note

Because the markdown table is wide:
- For viewing: VS Code Markdown preview, GitHub or GitLab.
- For editing: export to Excel/CSV and paste back.
- On a wiki: also viable as a Confluence or SharePoint list.

## 6. Validation Checks

After creating each row, run the following checks:

- [ ] **Are legal ground + purpose consistent?** If "performance of contract" is stated, does the row really arise from a contract?
- [ ] **Does the retention period conflict with legislation?** Watch out for differences such as VUK Art. 253 (5 years) vs. TTK Art. 82 (10 years).
- [ ] **Cross-border transfer check:** Is the SaaS provider's server location verified? "AWS Frankfurt" written as "AWS Ireland" must be corrected.
- [ ] **Was explicit consent misplaced?** The most common error is to list "explicit consent" while contract performance applies.
- [ ] **Is the information notice present and current?** Otherwise Reg. Art. 5/d is breached.
- [ ] **Is the VERBİS reflection done?** Update VERBİS within 7 days of adding a new row.

---

## Türkçe

# Kişisel Veri İşleme Envanteri — Şablon

Bu dosya, **kullanıma hazır** envanter şablonunu içerir. Üç örnek satırla doldurulmuştur (İK işe alım, müşteri sipariş, CCTV). Yeni satırlar için aynı format kullanılır.

## 1. Şablon Tablosu

> Tablo geniştir; markdown'da yatay kaydırma gerektirebilir. CSV başlık satırı bölüm 3'te verilmiştir; tercih halinde Excel'e aktarılarak çalışılabilir.

| Süreç ID | Süreç Adı | İş Birimi | Süreç Sahibi | Veri Konusu Kişi Grubu | Veri Kategorisi | Kişisel Veri Öğeleri | Özel Nitelikli (E/H) | İşleme Amacı | Hukuki Sebep | Toplama Yöntemi | Kayıt Ortamı | Aktarım Yapılan İç Birim | Yurt İçi Alıcı / Alıcı Grubu | Yurt Dışı Aktarım (E/H) | Yurt Dışı Alıcı + Ülke | Yurt Dışı Hukuki Temel | Saklama Süresi | Saklama Gerekçesi | İmha Yöntemi | İmha Periyodu | Teknik Tedbirler | İdari Tedbirler | Risk Seviyesi | İlgili Aydınlatma Metni | Açık Rıza Gerekli mi? | Son Güncelleme |
|----------|-----------|-----------|--------------|-----------------------|-----------------|---------------------|----------------------|--------------|--------------|-----------------|--------------|--------------------------|------------------------------|------------------------|------------------------|------------------------|----------------|-------------------|--------------|---------------|------------------|-----------------|---------------|-------------------------|----------------------|----------------|
| IK-001 | Çalışan Adayı İşe Alım ve Özgeçmiş Yönetimi | İnsan Kaynakları | Ad Soyad / İK Direktörü / ik.direktor@firma.com.tr | Çalışan Adayı | Kimlik; İletişim; Mesleki Deneyim; Eğitim; Görsel/İşitsel | Ad-soyad, T.C. kimlik no, doğum tarihi, telefon, e-posta, adres, eğitim bilgileri, iş tecrübesi, referans bilgileri, fotoğraf, mülakat notları | H | Açık pozisyon için aday değerlendirme; mülakat süreci; iş teklifi; aday havuzu yönetimi | Sözleşmenin kurulması için gereklilik (m.5/2/c) — başvuru aşaması; aday havuzunda saklama için Açık Rıza | Otomatik (kariyer sitesi formu, e-posta, kariyer portalı API'leri); Otomatik olmayan (kağıt başvuru, etkinlik) | Elektronik (ATS/HRIS, e-posta sunucusu, OneDrive); Fiziksel (özlük arşivi) | İK; ilgili pozisyonun bağlı olduğu departman yöneticisi | Aday değerlendirme firmaları (ATS sağlayıcısı), avukatlık ortağı (uyuşmazlık halinde) | E | LinkedIn Talent (ABD); Greenhouse (ABD/AB) | Standart sözleşme + KVKK Kurul'a bildirim; gerekiyorsa açık rıza | İşe alınmayan adaylar için 1 yıl (aday havuzu açık rıza varsa 2 yıl); işe alınanlar IK-002'ye devredilir | İşçi ve İşveren İlişkilerine Dair Kanun zamanaşımı + iş başvurusu nedeniyle hak iddiası analizi | Silme (elektronik) + Yok etme (fiziksel) | 6 aylık periyodik imha takvimi | TLS, AES-256 şifreleme, MFA, rol bazlı erişim, audit log, ATS güvenlik sertifikaları | Gizlilik taahhütnamesi, KVKK eğitimi, erişim yetkilendirme matrisi | Orta | AYD-IK-01 (İşe Alım Aydınlatma Metni) | E (aday havuzunda saklama için) | 2026-05-08 / KVKK Sorumlusu |
| MUS-002 | E-ticaret Sipariş Yönetimi ve Teslimat | Operasyon / Müşteri Hizmetleri | Ad Soyad / Operasyon Müdürü / op.mudur@firma.com.tr | Müşteri (Gerçek Kişi); Teslimat Adresi Sahibi (3. Kişi olabilir) | Kimlik; İletişim; Müşteri İşlem; Lokasyon; Finans | Ad-soyad, T.C. kimlik no (e-fatura için), telefon, e-posta, teslimat adresi, sipariş geçmişi, ödeme bilgisi (kart bilgisi tokenize), IP adresi, cihaz bilgisi | H | Sipariş alımı; ödeme tahsilatı; teslimat; iade; e-fatura kesimi; müşteri hizmetleri | Sözleşmenin ifası (m.5/2/c); hukuki yükümlülük — VUK, e-fatura mevzuatı (m.5/2/ç); ihtilaflarda hak korunması (m.5/2/e) | Otomatik (web sitesi, mobil app, çağrı merkezi); Otomatik olmayan (mağaza içi sipariş formu) | Elektronik (e-ticaret platformu, ödeme PSP'si, e-fatura sağlayıcı, CRM); Fiziksel (sevk irsaliyesi, fatura) | Operasyon, Muhasebe, Müşteri Hizmetleri, Bilgi İşlem | Ödeme PSP'si, kargo şirketi, e-fatura entegratörü, vergi dairesi (mevzuat gereği), avukatlık ortağı | E | AWS (İrlanda — bulut altyapı); Sendgrid (ABD — işlem e-postası) | Standart sözleşme; AWS Veri İşleme Sözleşmesi; Sendgrid SCC | Mali kayıtlar 10 yıl (TTK m.82, VUK m.253); müşteri hesabı için ilişki bitiminden itibaren 10 yıl (TBK m.146 zamanaşımı) | TTK, VUK, TBK | Silme (elektronik); Yok etme (kağıt fatura nüshaları için arşiv süresi sonu) | 6 aylık periyodik imha | TLS, kart tokenizasyonu (PCI-DSS), WAF, IDS/IPS, log toplama (SIEM), DDOS koruma, yedekleme şifreli | KVKK eğitimi, gizlilik taahhütnamesi, tedarikçi sözleşmeleri, periyodik denetim | Yüksek | AYD-MUS-01 (Müşteri E-ticaret Aydınlatma Metni) | H (sözleşme ifasına dayanıyor); pazarlama için ayrıca Açık Rıza | 2026-05-08 / KVKK Sorumlusu |
| FIZ-001 | Kapalı Devre Kamera Sistemi (CCTV) | Güvenlik | Ad Soyad / Güvenlik Müdürü / guvenlik.mudur@firma.com.tr | Çalışan; Ziyaretçi; Tedarikçi Çalışanı; 3. Kişi (kamera görüş alanına giren) | Görsel/İşitsel; Lokasyon | Görüntü kaydı (yüz, kıyafet, eylem); zaman damgası; kamera lokasyonu | H | Bina ve çevre güvenliği; suç önleme; iş sağlığı ve güvenliği; varlık koruma | Meşru menfaat (m.5/2/f) — sınırlı kapsam ve süre; iş sağlığı ve güvenliği için hukuki yükümlülük (m.5/2/ç) | Otomatik (CCTV kameralar, NVR/DVR) | Elektronik (kayıt sunucusu — şirket DC) | Güvenlik birimi; suç durumunda Hukuk + üst yönetim | Yetkili kolluk kuvvetleri (talep + adli süreç); sigorta firması (kaza halinde) | H | — | — | 30 gün (rotasyonel); kritik olay halinde olay kayıtları olay kapanana kadar | Meşru menfaat dengelemesi (PIA): kısa süre + sınırlı erişim | Otomatik üzerine yazma; manuel olay kaydı silme veya yok etme | 30 gün rotasyon | Erişim logu, MFA, ağ segmentasyonu, kayıt cihazı fiziksel kilit, şifreli kayıt | Erişim yetkilendirme (sadece Güvenlik birimi), KVKK eğitimi, kayıt taleplerinin yazılı süreci | Orta | AYD-FIZ-01 (CCTV Aydınlatma Tabelası + Detaylı Metin) | H (meşru menfaate dayanıyor) | 2026-05-08 / Güvenlik Müdürü |

## 2. Boş Satır Şablonu (Yeni Süreç İçin)

Aşağıdaki tabloyu kopyalayıp doldurun:

| Alan | Değer |
|------|-------|
| Süreç ID | `[birim_kısaltma]-[3 haneli sıra no]` |
| Süreç Adı | `...` |
| İş Birimi | `...` |
| Süreç Sahibi | `Ad Soyad / Unvan / e-posta` |
| Veri Konusu Kişi Grubu | `...` |
| Veri Kategorisi | `Kimlik; İletişim; ...` |
| Kişisel Veri Öğeleri | `...` |
| Özel Nitelikli (E/H) | `H` |
| İşleme Amacı | `Belirli, açık, meşru amaç ifadesi` |
| Hukuki Sebep | `KVKK m.5/2/...` veya `Açık Rıza` |
| Toplama Yöntemi | `Otomatik / Otomatik olmayan / Karma + kanal` |
| Kayıt Ortamı | `Elektronik (...) / Fiziksel (...)` |
| Aktarım Yapılan İç Birim | `...` |
| Yurt İçi Alıcı / Alıcı Grubu | `...` |
| Yurt Dışı Aktarım (E/H) | `H` |
| Yurt Dışı Alıcı + Ülke | `—` (yok ise) |
| Yurt Dışı Hukuki Temel | `—` |
| Saklama Süresi | `... yıl/ay` |
| Saklama Gerekçesi | `Mevzuat referansı veya zamanaşımı analizi` |
| İmha Yöntemi | `Silme / Yok etme / Anonim hale getirme` |
| İmha Periyodu | `6 ay` (varsayılan) |
| Teknik Tedbirler | `Şifreleme, log, MFA, ...` |
| İdari Tedbirler | `Eğitim, gizlilik, ...` |
| Risk Seviyesi | `Düşük / Orta / Yüksek / Kritik` |
| İlgili Aydınlatma Metni | `AYD-...` |
| Açık Rıza Gerekli mi? | `E/H` + gerekçe |
| Son Güncelleme | `YYYY-AA-GG / Hazırlayan` |

## 3. CSV Başlık Satırı (Kopyala-Yapıştır)

```csv
surec_id,surec_adi,is_birimi,surec_sahibi,veri_konusu_kisi_grubu,veri_kategorisi,kisisel_veri_ogeleri,ozel_nitelikli,isleme_amaci,hukuki_sebep,toplama_yontemi,kayit_ortami,aktarim_ic_birim,yurtici_alici,yurtdisi_aktarim,yurtdisi_alici_ulke,yurtdisi_hukuki_temel,saklama_suresi,saklama_gerekce,imha_yontemi,imha_periyodu,teknik_tedbirler,idari_tedbirler,risk_seviyesi,aydinlatma_metni,acik_riza_gerekli,son_guncelleme
```

### 3.1 Örnek CSV Satırı

```csv
IK-001,Çalışan Adayı İşe Alım,İnsan Kaynakları,İK Direktörü,Çalışan Adayı,Kimlik;İletişim;Mesleki Deneyim;Eğitim,"ad-soyad, TCKN, telefon, e-posta, eğitim, iş tecrübesi",H,"Aday değerlendirme; mülakat; iş teklifi","m.5/2/c sözleşme öncesi tedbirler; aday havuzu için Açık Rıza","Otomatik (kariyer sitesi); Otomatik olmayan (kağıt)","Elektronik (ATS, e-posta); Fiziksel (özlük)","İK; ilgili departman","Aday değerlendirme firmaları, avukatlık ortağı",E,"LinkedIn Talent (ABD); Greenhouse (ABD/AB)","Standart sözleşme + Kurul bildirim",1 yıl (havuz 2 yıl),"İş başvurusu zamanaşımı analizi",Silme + Yok etme,6 ay,"TLS, AES-256, MFA, audit log","Gizlilik, KVKK eğitimi, yetkilendirme",Orta,AYD-IK-01,E,2026-05-08
```

## 4. Alan Tanımları (Sözlük)

### 4.1 Süreç ID
Şirket içi tekil tanımlayıcı. Önerilen format: `[Birim 2-3 harf]-[3 haneli sıra]` (örn. IK-001, MUS-002, BT-014).

### 4.2 Veri Konusu Kişi Grubu (Yön. M.4/n)
"Veri sorumlularının kişisel verilerini işledikleri ilgili kişi kategorisi." Tipik gruplar:
- Çalışan, Çalışan Adayı, Eski Çalışan, Çalışan Yakını
- Müşteri, Potansiyel Müşteri, Eski Müşteri
- Tedarikçi Çalışanı, Tedarikçi Yetkilisi
- Ziyaretçi, Stajyer, Danışman
- Hissedar, Yönetim Kurulu Üyesi
- 3. Kişi (referans veren, alıcı, kefil vb.)
- Çocuk (18 yaş altı veri konusu)

### 4.3 Veri Kategorisi (Yön. M.4/m)
"Kişisel verilerin ortak özelliklerine göre gruplandırıldığı veri konusu kişi grubu veya gruplarına ait kişisel veri sınıfını" ifade eder. VERBİS standart kategorileri:

- Kimlik (ad-soyad, TCKN, doğum tarihi, cinsiyet)
- İletişim (telefon, e-posta, adres)
- Lokasyon (GPS, IP, lokasyon servisleri)
- Özlük (özlük dosyası verileri)
- Hukuki İşlem (dava bilgileri, vekaletname)
- Müşteri İşlem (sipariş, fatura, geçmiş)
- Fiziksel Mekan Güvenliği (CCTV, kart kayıtları)
- İşlem Güvenliği (log, IP, oturum)
- Risk Yönetimi (skoring, risk profili)
- Finans (IBAN, kart bilgisi tokenize, gelir)
- Mesleki Deneyim (CV, eğitim, sertifika)
- Pazarlama (tercih, alışkanlık, profil)
- Görsel/İşitsel (fotoğraf, ses kaydı, video)
- Sağlık Bilgileri (özel nitelikli — KVKK m.6)
- Cinsel Hayat (özel nitelikli)
- Ceza Mahkumiyeti ve Güvenlik Tedbirleri (özel nitelikli)
- Biyometrik Veri (özel nitelikli)
- Genetik Veri (özel nitelikli)
- Felsefi inanç, din, mezhep, dini yapı (özel nitelikli)
- Dernek, vakıf, sendika üyeliği (özel nitelikli)
- Siyasi düşünce (özel nitelikli)

### 4.4 Hukuki Sebep
KVKK m.5/2 (genel veri) veya m.6/2-3 (özel nitelikli) bentlerinden biri. **Açık rıza son çare** olarak değerlendirilir.

### 4.5 Toplama Yöntemi (Aydınlatma Tebliği M.5/i)
"Tamamen veya kısmen otomatik yollarla ya da veri kayıt sisteminin parçası olmak kaydıyla otomatik olmayan yollarla" — açık ifade zorunlu.

### 4.6 Alıcı / Alıcı Grubu (Yön. M.4/a)
"Veri sorumlusu tarafından kişisel verilerin aktarıldığı gerçek veya tüzel kişi kategorisi." Tek tek aktarılan firma adlarını yazmak yerine kategori (örn. "Kargo şirketleri", "Avukatlık ortakları") yazılabilir; ancak yurt dışı aktarımda firma + ülke açıkça yazılmalıdır.

### 4.7 Saklama Süresi (Yön. M.9/4-5)
- Mevzuatta süre öngörülmüşse → o süre.
- Birden fazla süre varsa → en uzunu.
- Süre belirlenirken (M.9/4) sektörel teamül, hukuki ilişkinin süresi, meşru menfaat süresi, risk-maliyet, güncel tutmaya elverişlilik, hukuki yükümlülük süresi, zamanaşımı dikkate alınır.

### 4.8 İmha Yöntemi (Saklama ve İmha Yön. M.8-10)
- **Silme:** İlgili kullanıcılar için erişilemez ve tekrar kullanılamaz hale getirme.
- **Yok etme:** Hiç kimse tarafından erişilemez, geri getirilemez, tekrar kullanılamaz hale getirme.
- **Anonim hale getirme:** Başka verilerle eşleştirilse dahi kimliği belirli/belirlenebilir bir gerçek kişiyle ilişkilendirilemez hale getirme.

### 4.9 İmha Periyodu (Saklama ve İmha Yön. M.11)
Periyodik imha azami **6 ay** olmalıdır. Şirket politikasında daha kısa belirlenebilir.

### 4.10 Risk Seviyesi
- **Düşük:** Genel veri, küçük hacim, sınırlı paylaşım, düşük etki.
- **Orta:** Genel veri, orta hacim, dış paylaşım var, orta etki.
- **Yüksek:** Özel nitelikli veri, büyük hacim, otomatik karar verme, yurt dışı aktarım.
- **Kritik:** Çocuk verisi, biyometrik, sağlık + büyük hacim, yüksek otomatik profilleme, finansal işlem.

## 5. Tablo Görünümü Notu

Markdown tablo geniş olduğu için:
- Görüntü için: VS Code Markdown önizlemesi, GitHub veya GitLab.
- Düzenleme için: Excel/CSV'ye aktarın, sonra geri yapıştırın.
- Wiki üzerinde: Confluence veya SharePoint listesi olarak da tutulabilir.

## 6. Doğrulama Kontrolleri

Her satır oluşturulduktan sonra aşağıdaki kontroller yapılır:

- [ ] **Hukuki sebep + amaç tutarlı mı?** Sözleşme ifası dendiyse satır gerçekten sözleşmeden mi doğuyor?
- [ ] **Saklama süresi mevzuatla çatışıyor mu?** VUK 5 yıl yazılmışsa kontrol et — VUK m.253 uyarınca **5 yıl** vs. TTK m.82 uyarınca **10 yıl** ayrımı.
- [ ] **Yurt dışı aktarım kontrolü:** SaaS sağlayıcının sunucu lokasyonu doğrulandı mı? "AWS Frankfurt" yerine "AWS İrlanda" yazılmışsa düzeltilmeli.
- [ ] **Açık rıza yanlış konumlandırıldı mı?** Sözleşme ifası varken "açık rıza" denmesi en yaygın hatadır.
- [ ] **Aydınlatma metni var mı, güncel mi?** Aksi halde Yön. M.5/d ihlali.
- [ ] **VERBİS yansıması yapıldı mı?** Yeni satır eklendiğinde 7 gün içinde VERBİS güncellemesi.
