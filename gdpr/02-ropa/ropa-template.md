---
title: "ROPA Template — Ready-to-Fill Article 30 Register"
title_tr: "ROPA Şablonu — Doldurmaya Hazır Madde 30 Sicili"
section: "02-ropa"
language: ["en", "tr"]
status: "approved"
version: "2.4.0"
last_review: "2026-04-15"
next_review: "2026-07-15"
owner: "Data Protection Officer"
classification: "Internal"
related_articles: ["GDPR Art. 6", "GDPR Art. 9", "GDPR Art. 10", "GDPR Art. 22", "GDPR Art. 30", "GDPR Art. 32", "GDPR Art. 35", "GDPR Art. 44–49"]
related_guidelines: ["CNIL ROPA Templates", "ICO Records of Processing Activities Template", "EDPB Position Paper April 2018"]
tags: ["ropa", "template", "register", "examples"]
---

## English

### How to Use This Template

The table below lists every column an Article 30(1)-compliant Controller ROPA must contain, plus best-practice extensions recommended by CNIL, ICO, and the EDPB. Each entry in the live ROPA is one row. Where this wiki is used as the system of record, copy the table into a per-entry markdown file under `02-ropa/entries/<entry-id>.md`.

Three fully-completed example rows follow the column reference: HR onboarding, e-commerce order fulfilment, and CCTV surveillance.

### Column Reference

| # | Column | Mandatory? | Source / Notes |
|---|--------|------------|----------------|
| 1 | Entry ID | Recommended | Globally unique, e.g., `ROPA-HR-001`. |
| 2 | Processing activity name | Recommended | Short, plain-language label. |
| 3 | Controller legal entity | Mandatory (Art. 30(1)(a)) | Legal name and registered address. |
| 4 | Joint controllers | Mandatory (Art. 30(1)(a)) | Where Article 26 applies; reference the joint-controller agreement. |
| 5 | Controller representative (Art. 27) | Mandatory (Art. 30(1)(a)) | Where the controller is established outside the EU. |
| 6 | DPO contact | Mandatory (Art. 30(1)(a)) | Name, email, phone. |
| 7 | Process owner | Recommended | Internal owner: name, role, email. |
| 8 | Business unit / function | Recommended | HR, Sales, Operations, etc. |
| 9 | Purpose of processing | Mandatory (Art. 30(1)(b)) | Plain-language statement; one row per distinct purpose. |
| 10 | Lawful basis (Art. 6) | Recommended | Specific Article 6(1) sub-clause. |
| 11 | Article 9 condition (if special category) | Recommended | If processing special category data, cite Art. 9(2) sub-clause. |
| 12 | Article 10 indicator (criminal data) | Recommended | Yes/No. |
| 13 | Article 22 indicator (automated decision-making) | Recommended | Yes/No; if Yes, link to Art. 22 documentation. |
| 14 | Categories of data subjects | Mandatory (Art. 30(1)(c)) | Employees, candidates, customers, visitors, etc. |
| 15 | Estimated number of data subjects | Recommended | Order of magnitude (10s, 100s, 1,000s, 10,000s, 100,000s, 1M+). |
| 16 | Categories of personal data | Mandatory (Art. 30(1)(c)) | Use a controlled vocabulary (identity, contact, financial, health, biometric, etc.). |
| 17 | Source of data | Recommended | Data subject; third party; public source. |
| 18 | Categories of recipients | Mandatory (Art. 30(1)(d)) | Internal departments, processors, third-party controllers. |
| 19 | Sub-processors | Recommended | Named sub-processors with country of establishment. |
| 20 | Third-country transfers | Mandatory (Art. 30(1)(e)) | Yes/No; if Yes, list destination country. |
| 21 | Transfer mechanism / safeguards | Mandatory (Art. 30(1)(e)) | Adequacy decision (Art. 45), SCCs (Art. 46), BCRs (Art. 47), derogation (Art. 49). |
| 22 | Retention period | Mandatory (Art. 30(1)(f)) | Concrete period; cross-reference retention schedule. |
| 23 | Erasure / archival mechanism | Recommended | How and where erasure happens. |
| 24 | Technical measures (TOM) | Mandatory (Art. 30(1)(g)) | Reference TOM register entry. |
| 25 | Organisational measures (TOM) | Mandatory (Art. 30(1)(g)) | Training, access governance, vendor governance. |
| 26 | DPIA reference | Recommended | If Art. 35 DPIA conducted. |
| 27 | Risk score (residual) | Recommended | Low / Medium / High. |
| 28 | IT systems / applications | Recommended | List the systems where data resides. |
| 29 | Country of storage | Recommended | Country where data primarily resides. |
| 30 | Privacy notice reference | Recommended | URL or document ID. |
| 31 | Data Processing Agreement (DPA) reference | Recommended | If processor relationship; contract reference. |
| 32 | Last reviewed | Recommended | Date and reviewer name. |
| 33 | Next review due | Recommended | Date. |
| 34 | Notes / change log | Recommended | Material changes since last review. |

### Example Row 1 — HR Onboarding

| Field | Value |
|-------|-------|
| 1. Entry ID | ROPA-HR-001 |
| 2. Activity name | Employee onboarding and personnel record creation |
| 3. Controller | Acme Holdings Europe B.V., Herengracht 100, 1015 Amsterdam, NL |
| 4. Joint controllers | None |
| 5. Representative | N/A (controller in EU) |
| 6. DPO | Dr. Lina Hartmann, dpo@acme.eu, +31 20 555 0100 |
| 7. Process owner | Sandra Wells, Head of People Operations, sandra.wells@acme.eu |
| 8. Business unit | Human Resources |
| 9. Purpose | Establish and maintain the personnel file required to perform the employment contract and meet statutory employer obligations (payroll, social security, tax, occupational health). |
| 10. Lawful basis (Art. 6) | Art. 6(1)(b) contract for performance of the employment contract; Art. 6(1)(c) legal obligation for tax, social security, and occupational health filings. |
| 11. Art. 9 condition | Art. 9(2)(b) employment law for occupational health data; Art. 9(2)(h) for company medical examinations; Art. 9(2)(g) for diversity reporting where required by law. |
| 12. Art. 10 indicator | Yes — for roles requiring background checks (regulated industry roles only). |
| 13. Art. 22 indicator | No |
| 14. Categories of data subjects | Employees, contractors with employment-equivalent treatment. |
| 15. Number of data subjects | ~3,200 across the EU. |
| 16. Categories of personal data | Identity (name, DOB, national ID, passport copy where required), contact (home address, personal email, emergency contact), employment (start date, role, department, salary, bank details), health (sick-leave records, occupational health certificate, disability accommodation if disclosed), tax & social security IDs, photograph for security badge. |
| 17. Source of data | Data subject (primary); background-check provider for regulated roles. |
| 18. Categories of recipients | Internal: HR, Payroll, Line Management, IT (for account provisioning), Finance (for expense). External: Payroll bureau (ADP Netherlands B.V.), Pension administrator (Aegon), Occupational Health Service (Arbo Unie), Tax Authority, Social Security Authority. |
| 19. Sub-processors | ADP sub-processors as listed in DPA Annex A; Aegon sub-processors as listed in DPA Annex C. |
| 20. Third-country transfers | Yes — limited transfer to Acme Holdings Inc. (US) for global HRIS (Workday) hosting. |
| 21. Transfer mechanism | EU–US Data Privacy Framework certification (Workday LLC); SCCs Module 3 (controller-to-processor) as fallback; Transfer Impact Assessment dated 2025-09-01 on file. |
| 22. Retention period | Active employment + 7 years post-termination for tax-relevant records (statutory); 2 years post-termination for non-tax records; immediately upon failed background check (where role-conditional). |
| 23. Erasure mechanism | Workday auto-archive after 7 years; physical files shredded by certified vendor with destruction certificate. |
| 24. Technical measures | Encryption at rest (AES-256) and in transit (TLS 1.3); MFA required for HRIS; role-based access controls; audit logging. Reference: TOM-REG-005. |
| 25. Organisational measures | Annual privacy training (mandatory); HR access policy reviewed annually; segregation of duties between HR Operations and Compensation; DPA with all processors. |
| 26. DPIA reference | DPIA-HR-2024-01 (Workday HRIS deployment). |
| 27. Risk score | Medium (residual). |
| 28. IT systems | Workday (HRIS), ADP Vantage (payroll), Active Directory, ServiceNow (onboarding tickets), DocuSign (contracts). |
| 29. Country of storage | Netherlands (primary); Ireland (DR); United States (Workday tenant). |
| 30. Privacy notice reference | Internal employee privacy notice v4.2 (intranet/privacy/employee). |
| 31. DPA reference | DPA-2023-014 (ADP); DPA-2024-022 (Workday); DPA-2022-009 (Aegon); DPA-2023-031 (Arbo Unie). |
| 32. Last reviewed | 2026-03-22 by Dr. Lina Hartmann (DPO). |
| 33. Next review due | 2026-09-22. |
| 34. Notes | Q1 2026: replaced legacy SAP HCM with Workday. DPIA refreshed. SCCs Module 3 re-executed with updated annexes. |

### Example Row 2 — E-commerce Order Fulfilment

| Field | Value |
|-------|-------|
| 1. Entry ID | ROPA-COM-014 |
| 2. Activity name | Customer order placement, payment, fulfilment, and post-sale support |
| 3. Controller | Acme Retail Europe B.V., Herengracht 100, 1015 Amsterdam, NL |
| 4. Joint controllers | None |
| 5. Representative | N/A |
| 6. DPO | Dr. Lina Hartmann, dpo@acme.eu |
| 7. Process owner | Mark Devries, Head of E-commerce, mark.devries@acme.eu |
| 8. Business unit | Customer Operations |
| 9. Purpose | Take, process, ship, and support customer orders placed through the acme.eu storefront; handle returns and warranty claims. |
| 10. Lawful basis (Art. 6) | Art. 6(1)(b) contract for order processing and shipping; Art. 6(1)(c) legal obligation for tax invoicing and consumer-protection records; Art. 6(1)(f) legitimate interest for fraud prevention (LIA-2025-004). |
| 11. Art. 9 condition | N/A |
| 12. Art. 10 indicator | No |
| 13. Art. 22 indicator | Yes — automated fraud screening at checkout; meaningful human review available on request. |
| 14. Categories of data subjects | Customers (B2C); B2B customer contacts. |
| 15. Number of data subjects | ~850,000 active customers; ~3.2M historic. |
| 16. Categories of personal data | Identity (name), contact (email, phone, shipping/billing address), order history, payment tokens (no full PAN — tokenised by PSP), device identifiers, IP address, customer service interactions. |
| 17. Source of data | Data subject; payment service provider (tokenised payment data). |
| 18. Categories of recipients | Internal: E-commerce Operations, Customer Service, Finance (for revenue), Fraud team. External: Payment Service Provider (Stripe Payments Europe Ltd), Logistics (DHL, PostNL), Email Service Provider (Mailgun EU), Fraud screening (Sift), Customer review platform (Trustpilot — only with customer opt-in). |
| 19. Sub-processors | Stripe sub-processors per DPA Annex; Mailgun sub-processors per DPA Annex; Sift sub-processors per DPA Annex. |
| 20. Third-country transfers | Yes — Sift (US) processes IP, device fingerprint, order metadata for fraud screening. |
| 21. Transfer mechanism | EU–US Data Privacy Framework certification (Sift Inc.); SCCs Module 2 as fallback; TIA-2025-014 on file. |
| 22. Retention period | Order data: 10 years (tax law); payment tokens: per PSP retention; customer service tickets: 3 years; fraud signals: 24 months; abandoned cart data: 90 days. |
| 23. Erasure mechanism | Automated retention job runs monthly; customer-initiated erasure supported via account portal subject to legal-hold rules. |
| 24. Technical measures | TLS 1.3, AES-256 at rest, tokenisation of payment data, WAF, DDoS protection, MFA on admin tools, audit logging, network segmentation. Reference: TOM-REG-009. |
| 25. Organisational measures | Annual customer-service training; access reviews quarterly; vendor due diligence; PCI DSS Level 1 (PSP); breach response runbook. |
| 26. DPIA reference | DPIA-COM-2024-04 (fraud-screening automated decision-making). |
| 27. Risk score | Medium. |
| 28. IT systems | Shopify Plus (storefront), NetSuite (ERP), Zendesk (support), Stripe (payments), Sift (fraud). |
| 29. Country of storage | Ireland (primary), Germany (DR). |
| 30. Privacy notice reference | acme.eu/privacy v6.1 (customer-facing layered notice). |
| 31. DPA reference | DPA-2024-001 (Stripe), DPA-2023-019 (Mailgun), DPA-2024-027 (Sift), DPA-2022-014 (DHL), DPA-2022-015 (PostNL). |
| 32. Last reviewed | 2026-04-02 by Dr. Lina Hartmann. |
| 33. Next review due | 2026-07-02. |
| 34. Notes | Q1 2026: Sift transferred to EU–US DPF. Trustpilot integration added under separate consent. |

### Example Row 3 — CCTV Surveillance at Corporate HQ

| Field | Value |
|-------|-------|
| 1. Entry ID | ROPA-FAC-002 |
| 2. Activity name | CCTV surveillance of perimeter, entrances, and shared communal areas |
| 3. Controller | Acme Holdings Europe B.V., Herengracht 100, 1015 Amsterdam, NL |
| 4. Joint controllers | Building management company (only at shared common-area entrances; joint-controller arrangement signed 2024-06-15). |
| 5. Representative | N/A |
| 6. DPO | Dr. Lina Hartmann, dpo@acme.eu |
| 7. Process owner | Tom Veerkamp, Head of Facilities Security, tom.veerkamp@acme.eu |
| 8. Business unit | Facilities and Physical Security |
| 9. Purpose | Protect persons (employees, visitors, contractors) and property (premises, equipment, sensitive areas) from theft, vandalism, unauthorised access, and to support criminal investigations where required. |
| 10. Lawful basis (Art. 6) | Art. 6(1)(f) legitimate interest. Documented LIA dated 2025-11-08 demonstrates necessity and balancing test (LIA-2025-008). |
| 11. Art. 9 condition | N/A — CCTV configured to avoid systematic capture of special-category data; no audio recording. |
| 12. Art. 10 indicator | No (incidental capture during incident review may surface criminal-related material; handled per separate incident-handling SOP). |
| 13. Art. 22 indicator | No — no automated decision-making. |
| 14. Categories of data subjects | Employees, contractors, visitors, delivery personnel, members of the public (within camera field of view in publicly accessible areas only). |
| 15. Number of data subjects | Indeterminate; visitors ~50/day; employees ~600 onsite. |
| 16. Categories of personal data | Image (video footage); time stamp; entry/exit metadata correlated with badge logs (linked dataset, not within CCTV). |
| 17. Source of data | Data subject (passive capture). |
| 18. Categories of recipients | Internal: Facilities Security, HR (in case of incident), Legal. External: Law enforcement only on lawful request; CCTV system provider (operational support, no routine access). |
| 19. Sub-processors | None routine. |
| 20. Third-country transfers | No — footage hosted on EU on-premises NVR. |
| 21. Transfer mechanism | N/A |
| 22. Retention period | 30 days standard rolling retention. Incident footage: retained as part of the specific incident file, separately governed. |
| 23. Erasure mechanism | NVR auto-overwrite at 30 days; incident footage exported to evidence archive with chain of custody. |
| 24. Technical measures | Encrypted storage, access via dedicated security workstation, MFA, audit log of every replay event, segmented network, no internet access from NVR. Reference: TOM-REG-014. |
| 25. Organisational measures | Camera placement reviewed annually for proportionality; signage at every public entrance referencing the layered CCTV notice; only Facilities Security can replay; incident-review SOP. |
| 26. DPIA reference | DPIA-FAC-2024-02 (CCTV deployment refresh). |
| 27. Risk score | Low. |
| 28. IT systems | Milestone XProtect (NVR); on-prem only. |
| 29. Country of storage | Netherlands. |
| 30. Privacy notice reference | CCTV signage at all entrances + layered CCTV notice (intranet/privacy/cctv). |
| 31. DPA reference | DPA-2024-009 (Milestone Systems support). |
| 32. Last reviewed | 2026-02-18 by Dr. Lina Hartmann. |
| 33. Next review due | 2026-08-18. |
| 34. Notes | 2026-Q1: two camera angles repositioned to reduce capture of public sidewalk after periodic proportionality review. |

### Empty Template Row (for Copying)

```
| Field | Value |
|-------|-------|
| 1. Entry ID |  |
| 2. Activity name |  |
| 3. Controller |  |
| 4. Joint controllers |  |
| 5. Representative |  |
| 6. DPO |  |
| 7. Process owner |  |
| 8. Business unit |  |
| 9. Purpose |  |
| 10. Lawful basis (Art. 6) |  |
| 11. Art. 9 condition |  |
| 12. Art. 10 indicator |  |
| 13. Art. 22 indicator |  |
| 14. Categories of data subjects |  |
| 15. Number of data subjects |  |
| 16. Categories of personal data |  |
| 17. Source of data |  |
| 18. Categories of recipients |  |
| 19. Sub-processors |  |
| 20. Third-country transfers |  |
| 21. Transfer mechanism |  |
| 22. Retention period |  |
| 23. Erasure mechanism |  |
| 24. Technical measures |  |
| 25. Organisational measures |  |
| 26. DPIA reference |  |
| 27. Risk score |  |
| 28. IT systems |  |
| 29. Country of storage |  |
| 30. Privacy notice reference |  |
| 31. DPA reference |  |
| 32. Last reviewed |  |
| 33. Next review due |  |
| 34. Notes |  |
```

---

## Türkçe

### Bu Şablonu Nasıl Kullanırsınız

Aşağıdaki tablo, Madde 30(1) uyumlu bir Veri Sorumlusu ROPA'sının içermesi gereken her sütunu ve CNIL, ICO ve EDPB tarafından önerilen en iyi uygulama eklerini listeler. Canlı ROPA'daki her giriş bir satırdır. Bu wiki kayıt sistemi olarak kullanıldığında, tabloyu `02-ropa/entries/<giriş-id>.md` altında giriş başına bir markdown dosyasına kopyalayın.

Sütun referansının ardından üç tam doldurulmuş örnek satır gelir: İK işe alım, e-ticaret sipariş süreci ve CCTV gözetimi.

### Sütun Referansı

| # | Sütun | Zorunlu mu? | Kaynak / Notlar |
|---|-------|-------------|-----------------|
| 1 | Giriş Kimliği | Önerilen | Küresel olarak benzersiz, örn. `ROPA-HR-001`. |
| 2 | İşleme faaliyeti adı | Önerilen | Kısa, sade dilli etiket. |
| 3 | Veri sorumlusu tüzel kişi | Zorunlu (Madde 30(1)(a)) | Yasal isim ve tescilli adres. |
| 4 | Ortak veri sorumluları | Zorunlu (Madde 30(1)(a)) | Madde 26 uygulanırsa; ortak veri sorumluluğu sözleşmesini referans verin. |
| 5 | Veri sorumlusu temsilcisi (Madde 27) | Zorunlu (Madde 30(1)(a)) | Veri sorumlusu AB dışında ise. |
| 6 | DPO iletişim | Zorunlu (Madde 30(1)(a)) | İsim, e-posta, telefon. |
| 7 | Süreç sahibi | Önerilen | Dahili sahip: isim, rol, e-posta. |
| 8 | İş birimi / fonksiyon | Önerilen | İK, Satış, Operasyonlar vb. |
| 9 | İşleme amacı | Zorunlu (Madde 30(1)(b)) | Sade dil ifadesi; her ayrı amaç için bir satır. |
| 10 | Hukuki sebep (Madde 6) | Önerilen | Madde 6(1) alt bendi. |
| 11 | Madde 9 koşulu (özel kategori ise) | Önerilen | Özel kategori veri işleniyorsa Madde 9(2) alt bendini belirtin. |
| 12 | Madde 10 göstergesi (cezai veri) | Önerilen | Evet/Hayır. |
| 13 | Madde 22 göstergesi (otomatik karar) | Önerilen | Evet/Hayır; Evet ise Madde 22 belgesine bağlantı. |
| 14 | İlgili kişi kategorileri | Zorunlu (Madde 30(1)(c)) | Çalışanlar, adaylar, müşteriler, ziyaretçiler vb. |
| 15 | Tahmini ilgili kişi sayısı | Önerilen | Büyüklük sırası (10'lar, 100'ler, 1.000'ler, 10.000'ler, 100.000'ler, 1M+). |
| 16 | Kişisel veri kategorileri | Zorunlu (Madde 30(1)(c)) | Kontrollü kelime hazinesi kullanın (kimlik, iletişim, finansal, sağlık, biyometrik vb.). |
| 17 | Veri kaynağı | Önerilen | İlgili kişi; üçüncü taraf; kamuya açık kaynak. |
| 18 | Alıcı kategorileri | Zorunlu (Madde 30(1)(d)) | Dahili departmanlar, veri işleyenler, üçüncü taraf veri sorumluları. |
| 19 | Alt işleyenler | Önerilen | Adlandırılmış alt işleyenler ve kuruluş ülkesi. |
| 20 | Üçüncü ülke aktarımları | Zorunlu (Madde 30(1)(e)) | Evet/Hayır; Evet ise hedef ülkeyi listeleyin. |
| 21 | Aktarım mekanizması / güvenceler | Zorunlu (Madde 30(1)(e)) | Yeterlilik kararı (Madde 45), SCC (Madde 46), BCR (Madde 47), muafiyet (Madde 49). |
| 22 | Saklama süresi | Zorunlu (Madde 30(1)(f)) | Somut süre; saklama planına çapraz referans. |
| 23 | Silme / arşivleme mekanizması | Önerilen | Silmenin nasıl ve nerede gerçekleştiği. |
| 24 | Teknik önlemler (TOM) | Zorunlu (Madde 30(1)(g)) | TOM sicil girişine referans. |
| 25 | İdari önlemler (TOM) | Zorunlu (Madde 30(1)(g)) | Eğitim, erişim yönetimi, tedarikçi yönetimi. |
| 26 | DPIA referansı | Önerilen | Madde 35 DPIA yapıldıysa. |
| 27 | Risk skoru (artık) | Önerilen | Düşük / Orta / Yüksek. |
| 28 | BT sistemleri / uygulamaları | Önerilen | Verinin bulunduğu sistemleri listeleyin. |
| 29 | Depolama ülkesi | Önerilen | Verinin asıl bulunduğu ülke. |
| 30 | Gizlilik bildirimi referansı | Önerilen | URL veya belge kimliği. |
| 31 | DPA referansı | Önerilen | Veri işleyen ilişkisi varsa; sözleşme referansı. |
| 32 | Son inceleme | Önerilen | Tarih ve inceleyen adı. |
| 33 | Sonraki inceleme | Önerilen | Tarih. |
| 34 | Notlar / değişiklik kaydı | Önerilen | Son incelemeden bu yana önemli değişiklikler. |

### Örnek Satır 1 — İK İşe Alım

| Alan | Değer |
|------|-------|
| 1. Giriş Kimliği | ROPA-HR-001 |
| 2. Faaliyet adı | Çalışan işe alım ve özlük dosyası oluşturma |
| 3. Veri sorumlusu | Acme Holdings Europe B.V., Herengracht 100, 1015 Amsterdam, NL |
| 4. Ortak veri sorumluları | Yok |
| 5. Temsilci | Yok (veri sorumlusu AB içinde) |
| 6. DPO | Dr. Lina Hartmann, dpo@acme.eu, +31 20 555 0100 |
| 7. Süreç sahibi | Sandra Wells, İnsan Operasyonları Müdürü, sandra.wells@acme.eu |
| 8. İş birimi | İnsan Kaynakları |
| 9. Amaç | İş sözleşmesinin ifası ve yasal işveren yükümlülüklerinin (bordro, sosyal güvenlik, vergi, iş sağlığı) yerine getirilmesi için gereken özlük dosyasını oluşturmak ve sürdürmek. |
| 10. Hukuki sebep (Madde 6) | İş sözleşmesinin ifası için Madde 6(1)(b); vergi, sosyal güvenlik ve iş sağlığı bildirimleri için yasal yükümlülük Madde 6(1)(c). |
| 11. Madde 9 koşulu | İş sağlığı verisi için Madde 9(2)(b) iş hukuku; şirket sağlık muayeneleri için Madde 9(2)(h); yasaların gerektirdiği yerlerde çeşitlilik raporlaması için Madde 9(2)(g). |
| 12. Madde 10 göstergesi | Evet — yalnızca arka plan kontrolü gerektiren roller (regüle sektör rolleri). |
| 13. Madde 22 göstergesi | Hayır |
| 14. İlgili kişi kategorileri | Çalışanlar, çalışanlara eşdeğer muamele edilen yükleniciler. |
| 15. İlgili kişi sayısı | AB genelinde ~3.200. |
| 16. Kişisel veri kategorileri | Kimlik (isim, doğum tarihi, ulusal kimlik, gerektiğinde pasaport kopyası), iletişim (ev adresi, kişisel e-posta, acil durum kişisi), istihdam (başlangıç tarihi, rol, departman, maaş, banka bilgileri), sağlık (hastalık izni, iş sağlığı sertifikası, beyan edilmişse engellilik düzenlemesi), vergi ve sosyal güvenlik kimlikleri, güvenlik kartı için fotoğraf. |
| 17. Veri kaynağı | İlgili kişi (birincil); regüle roller için arka plan kontrol sağlayıcı. |
| 18. Alıcı kategorileri | Dahili: İK, Bordro, Hat Yöneticileri, BT (hesap açma için), Finans (gider için). Harici: Bordro bürosu (ADP Netherlands B.V.), Emeklilik yöneticisi (Aegon), İş Sağlığı Hizmeti (Arbo Unie), Vergi Dairesi, Sosyal Güvenlik Otoritesi. |
| 19. Alt işleyenler | DPA Ek A'da listelenen ADP alt işleyenleri; DPA Ek C'de listelenen Aegon alt işleyenleri. |
| 20. Üçüncü ülke aktarımları | Evet — küresel HRIS (Workday) barındırması için Acme Holdings Inc. (ABD)'ye sınırlı aktarım. |
| 21. Aktarım mekanizması | AB-ABD Veri Gizliliği Çerçevesi sertifikası (Workday LLC); yedek olarak SCC Modül 3 (veri sorumlusundan veri işleyene); 2025-09-01 tarihli Aktarım Etki Değerlendirmesi dosyada. |
| 22. Saklama süresi | Aktif istihdam + vergi ile ilgili kayıtlar için işten ayrılma sonrası 7 yıl (yasal); vergi dışı kayıtlar için işten ayrılma sonrası 2 yıl; başarısız arka plan kontrolü durumunda derhal (rol koşullu olduğunda). |
| 23. Silme mekanizması | 7 yıl sonra Workday otomatik arşivleme; fiziksel dosyalar imha sertifikalı satıcı tarafından parçalanır. |
| 24. Teknik önlemler | Statik (AES-256) ve aktarımdaki (TLS 1.3) şifreleme; HRIS için MFA zorunlu; rol tabanlı erişim kontrolü; denetim loglaması. Referans: TOM-REG-005. |
| 25. İdari önlemler | Yıllık gizlilik eğitimi (zorunlu); İK erişim politikası yıllık inceleniyor; İK Operasyonları ve Ücretlendirme arasında görev ayrılığı; tüm veri işleyenlerle DPA. |
| 26. DPIA referansı | DPIA-HR-2024-01 (Workday HRIS dağıtımı). |
| 27. Risk skoru | Orta (artık). |
| 28. BT sistemleri | Workday (HRIS), ADP Vantage (bordro), Active Directory, ServiceNow (oryantasyon biletleri), DocuSign (sözleşmeler). |
| 29. Depolama ülkesi | Hollanda (birincil); İrlanda (felaket kurtarma); ABD (Workday tenant). |
| 30. Gizlilik bildirimi referansı | Dahili çalışan gizlilik bildirimi v4.2 (intranet/privacy/employee). |
| 31. DPA referansı | DPA-2023-014 (ADP); DPA-2024-022 (Workday); DPA-2022-009 (Aegon); DPA-2023-031 (Arbo Unie). |
| 32. Son inceleme | 2026-03-22, Dr. Lina Hartmann (DPO). |
| 33. Sonraki inceleme | 2026-09-22. |
| 34. Notlar | 2026-Ç1: eski SAP HCM, Workday ile değiştirildi. DPIA yenilendi. SCC Modül 3 güncel eklerle yeniden imzalandı. |

### Örnek Satır 2 — E-ticaret Sipariş İşleme

| Alan | Değer |
|------|-------|
| 1. Giriş Kimliği | ROPA-COM-014 |
| 2. Faaliyet adı | Müşteri sipariş alma, ödeme, teslim ve satış sonrası destek |
| 3. Veri sorumlusu | Acme Retail Europe B.V. |
| 4. Ortak veri sorumluları | Yok |
| 5. Temsilci | Yok |
| 6. DPO | Dr. Lina Hartmann |
| 7. Süreç sahibi | Mark Devries, E-ticaret Müdürü |
| 8. İş birimi | Müşteri Operasyonları |
| 9. Amaç | acme.eu mağazası üzerinden verilen müşteri siparişlerini almak, işlemek, sevk etmek ve desteklemek; iadeler ve garanti taleplerini ele almak. |
| 10. Hukuki sebep (Madde 6) | Sipariş işleme ve sevkiyat için Madde 6(1)(b); vergi faturalandırma ve tüketici koruma kayıtları için Madde 6(1)(c); dolandırıcılık önleme için Madde 6(1)(f) (LIA-2025-004). |
| 11. Madde 9 koşulu | Yok |
| 12. Madde 10 göstergesi | Hayır |
| 13. Madde 22 göstergesi | Evet — ödeme sırasında otomatik dolandırıcılık taraması; talep üzerine anlamlı insan incelemesi mevcuttur. |
| 14. İlgili kişi kategorileri | B2C müşteriler; B2B müşteri kişileri. |
| 15. İlgili kişi sayısı | ~850.000 aktif müşteri; ~3.2M tarihsel. |
| 16. Kişisel veri kategorileri | Kimlik (isim), iletişim (e-posta, telefon, sevkiyat/fatura adresi), sipariş geçmişi, ödeme tokenleri (tam PAN yok — PSP tarafından tokenize), cihaz tanımlayıcıları, IP adresi, müşteri hizmetleri etkileşimleri. |
| 17. Veri kaynağı | İlgili kişi; ödeme hizmet sağlayıcı (tokenize ödeme verisi). |
| 18. Alıcı kategorileri | Dahili: E-ticaret Operasyonları, Müşteri Hizmetleri, Finans, Dolandırıcılık ekibi. Harici: PSP (Stripe Payments Europe Ltd), Lojistik (DHL, PostNL), E-posta hizmeti (Mailgun EU), Dolandırıcılık tarama (Sift), Müşteri yorum platformu (Trustpilot — yalnızca müşteri onayı ile). |
| 19. Alt işleyenler | Stripe alt işleyenleri DPA Ek'e göre; Mailgun alt işleyenleri DPA Ek'e göre; Sift alt işleyenleri DPA Ek'e göre. |
| 20. Üçüncü ülke aktarımları | Evet — Sift (ABD) IP, cihaz parmak izi, sipariş meta verisini dolandırıcılık taraması için işler. |
| 21. Aktarım mekanizması | AB-ABD DPF (Sift Inc.); yedek olarak SCC Modül 2; TIA-2025-014 dosyada. |
| 22. Saklama süresi | Sipariş verisi: 10 yıl (vergi hukuku); ödeme tokenleri: PSP saklama politikasına göre; müşteri hizmetleri talepleri: 3 yıl; dolandırıcılık sinyalleri: 24 ay; terk edilmiş sepet verisi: 90 gün. |
| 23. Silme mekanizması | Aylık otomatik saklama görevi; müşteri tarafından başlatılan silme, yasal saklama kurallarına tabi olarak hesap portalından desteklenir. |
| 24. Teknik önlemler | TLS 1.3, statik AES-256, ödeme verisinin tokenizasyonu, WAF, DDoS koruma, yönetim araçlarında MFA, denetim loglaması, ağ segmentasyonu. Referans: TOM-REG-009. |
| 25. İdari önlemler | Yıllık müşteri hizmetleri eğitimi; üç aylık erişim incelemeleri; tedarikçi durum tespiti; PCI DSS Seviye 1 (PSP); ihlal yanıt çalışma kitabı. |
| 26. DPIA referansı | DPIA-COM-2024-04 (dolandırıcılık tarama otomatik karar verme). |
| 27. Risk skoru | Orta. |
| 28. BT sistemleri | Shopify Plus, NetSuite, Zendesk, Stripe, Sift. |
| 29. Depolama ülkesi | İrlanda (birincil), Almanya (DR). |
| 30. Gizlilik bildirimi referansı | acme.eu/privacy v6.1. |
| 31. DPA referansı | DPA-2024-001 (Stripe), DPA-2023-019 (Mailgun), DPA-2024-027 (Sift), DPA-2022-014 (DHL), DPA-2022-015 (PostNL). |
| 32. Son inceleme | 2026-04-02, Dr. Lina Hartmann. |
| 33. Sonraki inceleme | 2026-07-02. |
| 34. Notlar | 2026-Ç1: Sift, AB-ABD DPF'ye geçti. Ayrı onay altında Trustpilot entegrasyonu eklendi. |

### Örnek Satır 3 — Genel Merkezde CCTV Gözetimi

| Alan | Değer |
|------|-------|
| 1. Giriş Kimliği | ROPA-FAC-002 |
| 2. Faaliyet adı | Çevre, girişler ve ortak alanların CCTV gözetimi |
| 3. Veri sorumlusu | Acme Holdings Europe B.V. |
| 4. Ortak veri sorumluları | Bina yönetim şirketi (yalnızca ortak alan girişlerinde; 2024-06-15 tarihli ortak veri sorumluluğu sözleşmesi). |
| 5. Temsilci | Yok |
| 6. DPO | Dr. Lina Hartmann |
| 7. Süreç sahibi | Tom Veerkamp, Tesis Güvenliği Müdürü |
| 8. İş birimi | Tesisler ve Fiziksel Güvenlik |
| 9. Amaç | Kişileri (çalışanlar, ziyaretçiler, yükleniciler) ve mülkü (tesisler, ekipman, hassas alanlar) hırsızlık, vandalizm, izinsiz erişimden korumak ve gerektiğinde cezai soruşturmaları desteklemek. |
| 10. Hukuki sebep (Madde 6) | Madde 6(1)(f) meşru menfaat. 2025-11-08 tarihli LIA, gereklilik ve dengeleme testini gösterir (LIA-2025-008). |
| 11. Madde 9 koşulu | Yok — CCTV özel kategori veriyi sistematik olarak yakalamayacak şekilde yapılandırılmıştır; ses kaydı yapılmaz. |
| 12. Madde 10 göstergesi | Hayır (olay incelemesi sırasında dolaylı yakalama olabilir; ayrı olay-yönetim SOP'u ile ele alınır). |
| 13. Madde 22 göstergesi | Hayır. |
| 14. İlgili kişi kategorileri | Çalışanlar, yükleniciler, ziyaretçiler, teslimat personeli, kamuya açık alanlardaki kamera görüş alanı içindeki halk. |
| 15. İlgili kişi sayısı | Belirsiz; ziyaretçiler ~50/gün; yerinde çalışan ~600. |
| 16. Kişisel veri kategorileri | Görüntü (video kaydı); zaman damgası; rozet logları ile ilişkilendirilen giriş/çıkış meta verisi (CCTV içinde değil). |
| 17. Veri kaynağı | İlgili kişi (pasif yakalama). |
| 18. Alıcı kategorileri | Dahili: Tesis Güvenliği, İK (olay durumunda), Hukuk. Harici: Yalnızca yasal talep üzerine kolluk; CCTV sistem sağlayıcısı (operasyonel destek, rutin erişim yok). |
| 19. Alt işleyenler | Rutin yok. |
| 20. Üçüncü ülke aktarımları | Hayır — kayıtlar AB içi yerinde NVR'da. |
| 21. Aktarım mekanizması | Yok. |
| 22. Saklama süresi | 30 gün standart döngüsel saklama. Olay kayıtları: belirli olay dosyasının parçası olarak ayrı yönetilir. |
| 23. Silme mekanizması | NVR 30 günde otomatik üzerine yazma; olay kayıtları kanıt arşivine zincirleme korunma ile dışa aktarılır. |
| 24. Teknik önlemler | Şifreli depolama, özel güvenlik iş istasyonu üzerinden erişim, MFA, her tekrar oynatma için denetim logu, segmente ağ, NVR'da internet erişimi yok. Referans: TOM-REG-014. |
| 25. İdari önlemler | Kamera yerleşimi yıllık olarak orantılılık açısından inceleniyor; her kamuya açık girişte katmanlı CCTV bildirimine atıfta bulunan tabela; yalnızca Tesis Güvenliği tekrar oynatabilir; olay-inceleme SOP'u. |
| 26. DPIA referansı | DPIA-FAC-2024-02. |
| 27. Risk skoru | Düşük. |
| 28. BT sistemleri | Milestone XProtect (NVR); yalnızca yerinde. |
| 29. Depolama ülkesi | Hollanda. |
| 30. Gizlilik bildirimi referansı | Tüm girişlerdeki CCTV tabelası + katmanlı CCTV bildirimi. |
| 31. DPA referansı | DPA-2024-009 (Milestone Systems desteği). |
| 32. Son inceleme | 2026-02-18, Dr. Lina Hartmann. |
| 33. Sonraki inceleme | 2026-08-18. |
| 34. Notlar | 2026-Ç1: orantılılık incelemesinden sonra kaldırım yakalamasını azaltmak için iki kamera açısı yeniden konumlandırıldı. |

### Boş Şablon Satırı (Kopyalama İçin)

```
| Alan | Değer |
|------|-------|
| 1. Giriş Kimliği |  |
| 2. Faaliyet adı |  |
| 3. Veri sorumlusu |  |
| 4. Ortak veri sorumluları |  |
| 5. Temsilci |  |
| 6. DPO |  |
| 7. Süreç sahibi |  |
| 8. İş birimi |  |
| 9. Amaç |  |
| 10. Hukuki sebep (Madde 6) |  |
| 11. Madde 9 koşulu |  |
| 12. Madde 10 göstergesi |  |
| 13. Madde 22 göstergesi |  |
| 14. İlgili kişi kategorileri |  |
| 15. İlgili kişi sayısı |  |
| 16. Kişisel veri kategorileri |  |
| 17. Veri kaynağı |  |
| 18. Alıcı kategorileri |  |
| 19. Alt işleyenler |  |
| 20. Üçüncü ülke aktarımları |  |
| 21. Aktarım mekanizması |  |
| 22. Saklama süresi |  |
| 23. Silme mekanizması |  |
| 24. Teknik önlemler |  |
| 25. İdari önlemler |  |
| 26. DPIA referansı |  |
| 27. Risk skoru |  |
| 28. BT sistemleri |  |
| 29. Depolama ülkesi |  |
| 30. Gizlilik bildirimi referansı |  |
| 31. DPA referansı |  |
| 32. Son inceleme |  |
| 33. Sonraki inceleme |  |
| 34. Notlar |  |
```
