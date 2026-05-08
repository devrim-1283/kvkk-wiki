---
title:
  en: "Retention Schedule"
  tr: "Saklama Çizelgesi"
section: "04-retention-erasure"
document_type: "schedule"
regulation: "GDPR (EU 2016/679)"
articles:
  - "Art. 5(1)(e) — Storage limitation"
  - "Art. 30 — Records of processing activities"
member_state_references:
  - "DE: Abgabenordnung (AO) § 147 — 10 years tax/accounting"
  - "DE: Handelsgesetzbuch (HGB) § 257 — 10/6 years commercial books"
  - "FR: Code de commerce L.123-22 — 10 years accounting; L.110-4 — 5 years general commercial"
  - "FR: Code du travail L.3243-4 — 5 years payslips"
  - "IT: Codice Civile art. 2220 — 10 years accounting books"
  - "ES: Código de Comercio art. 30 — 6 years commercial books"
  - "PL: Ustawa o rachunkowości — 5 years accounting"
  - "NL: Burgerlijk Wetboek art. 2:10 — 7 years"
  - "BE: Code des sociétés — 7 years"
  - "AT: Bundesabgabenordnung § 132 — 7 years tax"
language: "en, tr"
last_reviewed: "2025-05-01"
review_cycle: "annual"
owner: "Data Protection Officer"
status: "approved"
classification: "internal"
note: "Member-state minimums vary. Always verify with local counsel before operating in a specific jurisdiction. Where multiple regimes apply, the longest legally required period governs that record."
---

## English

# Retention Schedule

This Schedule sets out retention periods by data category. It is the operational expression of the Retention Policy. Where local member-state law requires a longer minimum, that minimum governs.

> **Reading the table.** "Retention period" is the maximum period from the trigger event. The trigger event is the moment from which retention begins (e.g., end of employment, contract closure, last interaction). At the end of the retention period, the data is destroyed using the listed method. "Owner" is the function accountable for triggering destruction.

### Legend

- **Trigger**: event that starts the retention clock.
- **EU min.**: shortest commonly recurring member-state minimum.
- **Method**: see `erasure-methods.md` for definitions.
- **Notes**: legal obligations, exceptions, references.

### A. HR & Employment

| # | Category | Trigger | Retention | Lawful basis | EU min. (typical) | Owner | Method | Notes |
|---|---|---|---|---|---|---|---|---|
| 1 | Job applications (unsuccessful) | Recruitment decision | 6 months (extendable to 1 year with consent) | Legitimate interest; legal claims defence | DE: 6 months (AGG § 15) | HR | DB row deletion + crypto-shred backups | Document retention reason if extended. |
| 2 | Employment contract (active) | End of employment | 10 years | Legal obligation; legal claims | DE: § 195 BGB statute (3y); HGB obligations | HR | Secure deletion | Some clauses (non-compete) may require longer. |
| 3 | Payroll records | End of fiscal year | 10 years (DE/IT); 5 years (FR/ES); 7 years (NL/BE) | Legal obligation (tax) | DE: § 147 AO 10y | Finance | Secure deletion | Tax authority access required. |
| 4 | Time & attendance records | End of fiscal year | 2–4 years | Legal obligation (working time directive); legal claims | DE: 2y (§ 16(2) ArbZG) | HR | Secure deletion | |
| 5 | Performance appraisals | End of employment | 3 years | Legitimate interest; legal claims | — | HR | Secure deletion | |
| 6 | Disciplinary records | End of employment + 3y | 3 years post-termination | Legitimate interest; legal claims | — | HR | Secure deletion | Active hold lifts on settlement. |
| 7 | Occupational health records | End of employment | 10–40 years (varies by exposure) | Legal obligation (health & safety) | Asbestos exposure: 40 years | HR / OHS | Secure archive then destroy | Country-specific health & safety rules govern. |
| 8 | Pension records | End of pension liability | Lifetime + 6 years post-final-payment | Legal obligation | — | Finance / HR | Secure deletion | |
| 9 | Background checks (post-hire) | End of employment | Maximum 6 months retention of result; underlying data: per source rules | Legitimate interest; legal obligation (regulated industries) | — | HR / Compliance | Secure deletion | Under no circumstance retain raw screening data after hire decision unless legal basis exists. |
| 10 | Training records | End of employment | 5 years | Legal obligation (regulated training); legitimate interest | — | HR | Secure deletion | |

### B. Customer & Commercial

| # | Category | Trigger | Retention | Lawful basis | EU min. (typical) | Owner | Method | Notes |
|---|---|---|---|---|---|---|---|---|
| 11 | Customer account (active) | Last login / last transaction | Active relationship + 3 years dormancy | Contract; legitimate interest | — | Sales / Customer Ops | Secure deletion | Notify customer before deletion. |
| 12 | Order/transaction records | End of fiscal year | 10 years (DE/IT); 5 years (FR); 6 years (ES); 7 years (NL/BE) | Legal obligation (tax/commercial code) | DE: § 147 AO 10y | Finance | Secure deletion | |
| 13 | Invoices | End of fiscal year | Same as #12 | Legal obligation | DE: 10y; FR: 10y; IT: 10y | Finance | Secure deletion | |
| 14 | Customer contracts | Contract end | Statutory limitation period (typ. 6–10 years) | Legal claims; legal obligation | DE: 3y (§ 195 BGB) for general; 30y for property | Legal | Secure deletion | Original signed copies may be archived longer. |
| 15 | Customer support tickets | Ticket closure | 2 years | Legitimate interest; quality assurance | — | Customer Ops | Secure deletion | |
| 16 | Customer complaints | Resolution | 5 years | Legal claims; regulatory | — | Customer Ops / Legal | Secure deletion | Financial services may require longer. |
| 17 | Marketing email opt-in (consent records) | Consent withdrawal | 3 years post-withdrawal (proof of past consent) | Legal claims; accountability (Art. 7(1)) | — | Marketing | Secure deletion | Retain proof, not the marketable contact. |
| 18 | Marketing engagement data (opens, clicks) | Last engagement | 13 months (cookie norm) or end of campaign + 1y | Legitimate interest; consent | — | Marketing | Aggregate / anonymise then delete | |
| 19 | Cookies (non-essential) | Cookie issuance | Per cookie policy (typ. ≤13 months) | Consent | EDPB guidelines: ≤13 months typical | Web / Marketing | Auto-expiry + DB cleanup | |
| 20 | Newsletter subscribers | Unsubscribe | Immediate removal from list; suppression list retained 3 years | Consent | — | Marketing | Soft delete + suppression list | |

### C. Financial & Accounting

| # | Category | Trigger | Retention | Lawful basis | EU min. (typical) | Owner | Method | Notes |
|---|---|---|---|---|---|---|---|---|
| 21 | General ledger | End of fiscal year | 10 years (DE/IT); 5–10 years elsewhere | Legal obligation (commercial/tax code) | DE: HGB § 257 — 10y | Finance | Secure deletion | |
| 22 | Tax returns and supporting docs | Filing | 10 years (DE); 6 years (UK-precedent in some cases); 5 years (FR) | Legal obligation (tax) | DE: § 147 AO 10y | Finance / Tax | Secure deletion | |
| 23 | Bank statements | End of fiscal year | 10 years | Legal obligation; legal claims | DE: 10y | Finance | Secure deletion | |
| 24 | Expense claims | End of fiscal year | 10 years (with tax) or 6 years | Legal obligation | DE: 10y | Finance | Secure deletion | |
| 25 | Audit working papers | Audit completion | 6–10 years | Regulatory; profession standards | EU Statutory Audit Directive: 5y min | Finance / Audit | Secure archive then destroy | |

### D. Logs, Security, IT

| # | Category | Trigger | Retention | Lawful basis | EU min. (typical) | Owner | Method | Notes |
|---|---|---|---|---|---|---|---|---|
| 26 | Application access logs | Log creation | 90 days operational; 1 year security forensics | Legitimate interest (security) | — | IT / SecOps | Auto-expire (log lifecycle) | Pseudonymise where possible. |
| 27 | Security incident logs | Incident closure | 5 years | Legitimate interest; legal claims | — | SecOps | Secure deletion | Aggravated breaches: longer for litigation. |
| 28 | Authentication logs (success / failure) | Event | 6–12 months | Legitimate interest (security) | — | IT / SecOps | Auto-expire | |
| 29 | DLP / IDS / SIEM logs | Event | 1 year (raw) / longer aggregated | Legitimate interest | — | SecOps | Auto-expire | |
| 30 | Backup tapes / snapshots | Creation | Per backup retention policy (typ. 30 days incremental, 1 year monthly, 7 years yearly) | Business continuity; legitimate interest | — | IT Ops | Crypto-shred / overwrite | Erasure requests propagate via crypto-shred. |
| 31 | CCTV footage | Recording | 30 days (general); up to 90 days (high-risk areas with DPIA) | Legitimate interest (security) | DE/AT/IT guidance: ~72h–30d typical | Facilities / SecOps | Auto-overwrite | Longer requires DPIA and signage. |
| 32 | Building access logs | Event | 90 days | Legitimate interest (security) | — | Facilities | Auto-expire | |
| 33 | Email mailboxes (terminated employees) | Termination | 6 months litigation hold; then delete | Legitimate interest; legal claims | — | IT Ops | Secure deletion | Auto-reply to senders during hold. |
| 34 | Endpoint device images (decommission) | Device retirement | 90 days then sanitisation | Legitimate interest | — | IT Ops | NIST 800-88 Purge | Re-issued devices follow Clear. |

### E. Special Categories & Sensitive

| # | Category | Trigger | Retention | Lawful basis | EU min. (typical) | Owner | Method | Notes |
|---|---|---|---|---|---|---|---|---|
| 35 | Health data (occupational) | End of employment | 10–40 years per exposure | Legal obligation (health & safety) | Asbestos: 40y | OHS | Secure archive then destroy | |
| 36 | Diversity & inclusion monitoring | Submission | Aggregate immediately; raw 12 months max | Legal obligation (where mandated); legitimate interest | — | HR / Compliance | Aggregate + secure deletion | |
| 37 | Whistleblower reports | Investigation closure | 5 years (or longer if legal proceedings) | Legal obligation (EU Directive 2019/1937); legal claims | EU: 5y typical | Compliance / Legal | Secure deletion | Anonymisation where possible. |
| 38 | Biometric authentication data | Account closure | Immediate post-account-closure | Consent (Art. 9(2)(a)) typically required | — | IT Sec | Crypto-shred + delete template | DPIA mandatory. |
| 39 | Children's data (where lawfully processed) | Age-out / consent withdrawal | Minimum necessary | Consent of holder of parental responsibility (Art. 8) | — | Product / Legal | Secure deletion | Heightened scrutiny. |

### F. Vendor / Processor / Contractor

| # | Category | Trigger | Retention | Lawful basis | EU min. (typical) | Owner | Method | Notes |
|---|---|---|---|---|---|---|---|---|
| 40 | Vendor contracts | Contract end | 10 years | Legal claims; legal obligation | DE: 3–10y | Procurement | Secure deletion | |
| 41 | Vendor due diligence records | Onboarding decision | Active relationship + 5 years | Legal obligation; legitimate interest | — | Procurement / Compliance | Secure deletion | |
| 42 | Article 28 DPAs | Processor relationship end | 6 years | Accountability; legal claims | — | DPO / Procurement | Secure deletion | |
| 43 | Sub-processor approvals | Sub-processor change | Active + 6 years | Accountability | — | DPO / Procurement | Secure deletion | |

### G. Marketing & Web Analytics

| # | Category | Trigger | Retention | Lawful basis | EU min. (typical) | Owner | Method | Notes |
|---|---|---|---|---|---|---|---|---|
| 44 | CRM lead records (no conversion) | Last activity | 18 months then delete | Legitimate interest | — | Sales / Marketing | Secure deletion | |
| 45 | A/B test data | Test conclusion + 90 days | 90 days post-test | Legitimate interest | — | Product Analytics | Aggregate + delete | |
| 46 | Web analytics raw events | Event | 14 months (Google Analytics norm) | Consent / legitimate interest | EDPB guidance | Analytics | Auto-expire | |

### H. DPIA, RoPA, Compliance

| # | Category | Trigger | Retention | Lawful basis | EU min. (typical) | Owner | Method | Notes |
|---|---|---|---|---|---|---|---|---|
| 47 | DPIAs | Activity end | 6 years post-activity-end | Accountability (Art. 35) | — | DPO | Secure archive | |
| 48 | RoPA (records of processing activities) | Processing end | 6 years post-end | Accountability (Art. 30) | — | DPO | Secure archive | |
| 49 | Data subject requests (DSAR, Art. 15–22) | Request closure | 3 years | Accountability; legal claims | — | DPO | Secure deletion | Request itself contains personal data. |
| 50 | Personal data breach records | Breach closure | 6 years | Accountability (Art. 33(5)) | — | DPO / SecOps | Secure deletion | |

### Worked example: cross-cutting retention conflict

A German salary record contains:
- Personal identifiers (name, address)
- Bank account
- Tax ID
- Salary amount
- Health-insurance contribution

The dominant legal driver is German tax law (§ 147 AO) — **10 years**. Even though "marketing has no need" for the record at year 4, deletion is **forbidden** until year 10. Conversely, at year 10 + 1 day, retention is **prohibited** unless another lawful basis (e.g., active litigation hold) applies.

### Verification before relying on this Schedule

This Schedule reflects common minimums as of mid-2025. **Always verify**:
- Local member-state law (regulators publish guidance and update statutes regularly).
- Sector-specific regulations (banking, insurance, telecom, healthcare).
- Recent court rulings and DPA decisions.
- Ongoing or anticipated litigation requiring legal hold.

---

## Türkçe

# Saklama Çizelgesi

Bu Çizelge, veri kategorisine göre saklama sürelerini belirler. Saklama Politikasının operasyonel ifadesidir. Yerel üye devlet hukuku daha uzun bir minimum gerektirdiğinde, bu minimum geçerlidir.

> **Tabloyu okuma.** "Saklama süresi" tetikleyici olaydan itibaren maksimum süredir. Tetikleyici olay, saklamanın başladığı andır (örn. istihdamın sonu, sözleşme kapanışı, son etkileşim). Saklama süresinin sonunda, veri listelenen yöntemle imha edilir. "Sahip", imhayı tetiklemekten sorumlu işlevdir.

### Açıklama

- **Tetikleyici**: saklama saatini başlatan olay.
- **AB min.**: en kısa yaygın olarak tekrar eden üye devlet minimumu.
- **Yöntem**: tanımlar için bkz. `erasure-methods.md`.
- **Notlar**: hukuki yükümlülükler, istisnalar, atıflar.

### A. İK ve İstihdam

| # | Kategori | Tetikleyici | Saklama | Hukuki dayanak | AB min. (tipik) | Sahip | Yöntem | Notlar |
|---|---|---|---|---|---|---|---|---|
| 1 | İş başvuruları (başarısız) | İşe alım kararı | 6 ay (rıza ile 1 yıla uzatılabilir) | Meşru menfaat; hukuki talepler | DE: 6 ay (AGG § 15) | İK | DB satır silme + yedek kripto-parçalama | Uzatılırsa saklama nedenini belgele. |
| 2 | İş sözleşmesi (aktif) | İstihdamın sonu | 10 yıl | Hukuki yükümlülük; hukuki talepler | DE: § 195 BGB (3y); HGB | İK | Güvenli silme | Bazı maddeler (rekabet etmeme) daha uzun gerektirebilir. |
| 3 | Bordro kayıtları | Mali yıl sonu | 10 yıl (DE/IT); 5 yıl (FR/ES); 7 yıl (NL/BE) | Hukuki yükümlülük (vergi) | DE: § 147 AO 10y | Finans | Güvenli silme | Vergi makamı erişimi gerekli. |
| 4 | Zaman ve devam kayıtları | Mali yıl sonu | 2–4 yıl | Hukuki yükümlülük (çalışma süresi); hukuki talepler | DE: 2y (§ 16(2) ArbZG) | İK | Güvenli silme | |
| 5 | Performans değerlendirmeleri | İstihdamın sonu | 3 yıl | Meşru menfaat; hukuki talepler | — | İK | Güvenli silme | |
| 6 | Disiplin kayıtları | İstihdamın sonu + 3y | İstihdam sonrası 3 yıl | Meşru menfaat; hukuki talepler | — | İK | Güvenli silme | Aktif bekletme uzlaşmada kalkar. |
| 7 | İş sağlığı kayıtları | İstihdamın sonu | 10–40 yıl (maruziyete göre değişir) | Hukuki yükümlülük (iş sağlığı ve güvenliği) | Asbest: 40 yıl | İK / OHS | Güvenli arşiv sonra imha | Ülkeye özel İSG kuralları geçerli. |
| 8 | Emeklilik kayıtları | Emeklilik yükümlülüğü sonu | Yaşam boyu + son ödeme sonrası 6 yıl | Hukuki yükümlülük | — | Finans / İK | Güvenli silme | |
| 9 | Geçmiş kontrolleri (işe alım sonrası) | İstihdamın sonu | Sonucun maksimum 6 ay saklanması | Meşru menfaat; hukuki yükümlülük (düzenlenen sektörler) | — | İK / Uyum | Güvenli silme | İşe alım kararı sonrası ham tarama verisi saklanmaz. |
| 10 | Eğitim kayıtları | İstihdamın sonu | 5 yıl | Hukuki yükümlülük; meşru menfaat | — | İK | Güvenli silme | |

### B. Müşteri ve Ticari

| # | Kategori | Tetikleyici | Saklama | Hukuki dayanak | AB min. (tipik) | Sahip | Yöntem | Notlar |
|---|---|---|---|---|---|---|---|---|
| 11 | Müşteri hesabı (aktif) | Son giriş / son işlem | Aktif ilişki + 3 yıl uyku | Sözleşme; meşru menfaat | — | Satış / Müşteri Ops | Güvenli silme | Silmeden önce müşteriye bildir. |
| 12 | Sipariş/işlem kayıtları | Mali yıl sonu | 10 yıl (DE/IT); 5 yıl (FR); 6 yıl (ES); 7 yıl (NL/BE) | Hukuki yükümlülük (vergi/ticaret kodu) | DE: § 147 AO 10y | Finans | Güvenli silme | |
| 13 | Faturalar | Mali yıl sonu | #12 ile aynı | Hukuki yükümlülük | DE: 10y; FR: 10y; IT: 10y | Finans | Güvenli silme | |
| 14 | Müşteri sözleşmeleri | Sözleşme sonu | Yasal zamanaşımı süresi (tip. 6–10 yıl) | Hukuki talepler; hukuki yükümlülük | DE: 3y (§ 195 BGB); 30y emlak | Hukuk | Güvenli silme | Orijinal imzalı kopyalar daha uzun arşivlenebilir. |
| 15 | Müşteri destek talepleri | Talep kapanışı | 2 yıl | Meşru menfaat; kalite güvencesi | — | Müşteri Ops | Güvenli silme | |
| 16 | Müşteri şikâyetleri | Çözüm | 5 yıl | Hukuki talepler; düzenleyici | — | Müşteri Ops / Hukuk | Güvenli silme | Finansal hizmetler daha uzun gerektirebilir. |
| 17 | Pazarlama e-posta opt-in (rıza kayıtları) | Rıza geri çekilmesi | Geri çekilme sonrası 3 yıl (geçmiş rıza kanıtı) | Hukuki talepler; hesap verebilirlik (Md. 7(1)) | — | Pazarlama | Güvenli silme | Kanıtı sakla, pazarlanabilir kişiyi değil. |
| 18 | Pazarlama etkileşim verisi (açma, tıklama) | Son etkileşim | 13 ay (çerez normu) veya kampanya sonu + 1y | Meşru menfaat; rıza | — | Pazarlama | Toplu/anonim ardından sil | |
| 19 | Çerezler (zorunlu olmayan) | Çerez verme | Çerez politikası başına (tip. ≤13 ay) | Rıza | EDPB rehberi: tip. ≤13 ay | Web / Pazarlama | Otomatik son + DB temizliği | |
| 20 | Bülten aboneleri | Abonelikten çıkma | Listeden anında kaldırma; baskı listesi 3 yıl saklanır | Rıza | — | Pazarlama | Yumuşak silme + baskı listesi | |

### C. Finansal ve Muhasebe

| # | Kategori | Tetikleyici | Saklama | Hukuki dayanak | AB min. (tipik) | Sahip | Yöntem | Notlar |
|---|---|---|---|---|---|---|---|---|
| 21 | Genel muhasebe | Mali yıl sonu | 10 yıl (DE/IT); diğerlerinde 5–10 yıl | Hukuki yükümlülük (ticaret/vergi kodu) | DE: HGB § 257 — 10y | Finans | Güvenli silme | |
| 22 | Vergi beyannameleri ve destekleyici belgeler | Beyan | 10 yıl (DE); 6 yıl (UK-bazı vakalar); 5 yıl (FR) | Hukuki yükümlülük (vergi) | DE: § 147 AO 10y | Finans / Vergi | Güvenli silme | |
| 23 | Banka ekstreleri | Mali yıl sonu | 10 yıl | Hukuki yükümlülük; hukuki talepler | DE: 10y | Finans | Güvenli silme | |
| 24 | Masraf talepleri | Mali yıl sonu | 10 yıl (vergi ile) veya 6 yıl | Hukuki yükümlülük | DE: 10y | Finans | Güvenli silme | |
| 25 | Denetim çalışma kâğıtları | Denetim tamamlanması | 6–10 yıl | Düzenleyici; meslek standartları | AB Yasal Denetim Direktifi: min 5y | Finans / Denetim | Güvenli arşiv sonra imha | |

### D. Loglar, Güvenlik, BT

| # | Kategori | Tetikleyici | Saklama | Hukuki dayanak | AB min. (tipik) | Sahip | Yöntem | Notlar |
|---|---|---|---|---|---|---|---|---|
| 26 | Uygulama erişim logları | Log oluşturma | 90 gün operasyonel; 1 yıl güvenlik adli | Meşru menfaat (güvenlik) | — | BT / SecOps | Otomatik son (log yaşam döngüsü) | Mümkünse takma ad. |
| 27 | Güvenlik olay logları | Olay kapanışı | 5 yıl | Meşru menfaat; hukuki talepler | — | SecOps | Güvenli silme | Ağırlaştırılmış ihlaller: dava için daha uzun. |
| 28 | Kimlik doğrulama logları (başarı / başarısızlık) | Olay | 6–12 ay | Meşru menfaat (güvenlik) | — | BT / SecOps | Otomatik son | |
| 29 | DLP / IDS / SIEM logları | Olay | 1 yıl (ham) / daha uzun toplu | Meşru menfaat | — | SecOps | Otomatik son | |
| 30 | Yedek bantları / snapshot'lar | Oluşturma | Yedek saklama politikası başına (tip. 30 gün artımlı, 1 yıl aylık, 7 yıl yıllık) | İş sürekliliği; meşru menfaat | — | BT Ops | Kripto-parçalama / üzerine yazma | Silme talepleri kripto-parçalama yoluyla yayılır. |
| 31 | CCTV görüntüleri | Kayıt | 30 gün (genel); 90 güne kadar (DPIA ile yüksek riskli alanlar) | Meşru menfaat (güvenlik) | DE/AT/IT rehberi: ~72s–30g tip. | Tesis / SecOps | Otomatik üzerine yazma | Daha uzun DPIA ve tabela gerektirir. |
| 32 | Bina erişim logları | Olay | 90 gün | Meşru menfaat (güvenlik) | — | Tesis | Otomatik son | |
| 33 | E-posta posta kutuları (sonlandırılmış çalışan) | Sonlandırma | 6 ay dava bekletme; sonra sil | Meşru menfaat; hukuki talepler | — | BT Ops | Güvenli silme | Bekletme sırasında gönderenlere otomatik yanıt. |
| 34 | Uç nokta cihaz görüntüleri (devre dışı bırakma) | Cihaz emekliliği | 90 gün sonra sanitasyon | Meşru menfaat | — | BT Ops | NIST 800-88 Purge | Yeniden verilen cihazlar Clear izler. |

### E. Özel Kategoriler ve Hassas

| # | Kategori | Tetikleyici | Saklama | Hukuki dayanak | AB min. (tipik) | Sahip | Yöntem | Notlar |
|---|---|---|---|---|---|---|---|---|
| 35 | Sağlık verisi (mesleki) | İstihdamın sonu | Maruziyete göre 10–40 yıl | Hukuki yükümlülük (İSG) | Asbest: 40y | OHS | Güvenli arşiv sonra imha | |
| 36 | Çeşitlilik ve katılım izleme | Gönderim | Hemen toplu; ham max 12 ay | Hukuki yükümlülük (zorunlu olduğunda); meşru menfaat | — | İK / Uyum | Toplu + güvenli silme | |
| 37 | İhbar raporları | Soruşturma kapanışı | 5 yıl (veya hukuki süreçler varsa daha uzun) | Hukuki yükümlülük (AB Direktifi 2019/1937); hukuki talepler | AB: tip. 5y | Uyum / Hukuk | Güvenli silme | Mümkünse anonim. |
| 38 | Biyometrik kimlik doğrulama verisi | Hesap kapanışı | Hesap kapanışı sonrası anında | Genellikle rıza (Md. 9(2)(a)) gerekli | — | BT Sec | Kripto-parçalama + şablon sil | DPIA zorunlu. |
| 39 | Çocuk verisi (yasal olarak işlendiğinde) | Yaş aşımı / rıza geri çekme | Minimum gerekli | Velayet sahibinin rızası (Md. 8) | — | Ürün / Hukuk | Güvenli silme | Yüksek inceleme. |

### F. Tedarikçi / İşleyen / Yüklenici

| # | Kategori | Tetikleyici | Saklama | Hukuki dayanak | AB min. (tipik) | Sahip | Yöntem | Notlar |
|---|---|---|---|---|---|---|---|---|
| 40 | Tedarikçi sözleşmeleri | Sözleşme sonu | 10 yıl | Hukuki talepler; hukuki yükümlülük | DE: 3–10y | Tedarik | Güvenli silme | |
| 41 | Tedarikçi durum tespiti kayıtları | Onboarding kararı | Aktif ilişki + 5 yıl | Hukuki yükümlülük; meşru menfaat | — | Tedarik / Uyum | Güvenli silme | |
| 42 | Madde 28 DPA'lar | İşleyen ilişkisi sonu | 6 yıl | Hesap verebilirlik; hukuki talepler | — | DPO / Tedarik | Güvenli silme | |
| 43 | Alt-işleyen onayları | Alt-işleyen değişikliği | Aktif + 6 yıl | Hesap verebilirlik | — | DPO / Tedarik | Güvenli silme | |

### G. Pazarlama ve Web Analitiği

| # | Kategori | Tetikleyici | Saklama | Hukuki dayanak | AB min. (tipik) | Sahip | Yöntem | Notlar |
|---|---|---|---|---|---|---|---|---|
| 44 | CRM lead kayıtları (dönüşüm yok) | Son aktivite | 18 ay sonra sil | Meşru menfaat | — | Satış / Pazarlama | Güvenli silme | |
| 45 | A/B test verisi | Test sonu + 90 gün | Test sonrası 90 gün | Meşru menfaat | — | Ürün Analitiği | Toplu + sil | |
| 46 | Web analitiği ham olaylar | Olay | 14 ay (Google Analytics normu) | Rıza / meşru menfaat | EDPB rehberi | Analitik | Otomatik son | |

### H. DPIA, RoPA, Uyum

| # | Kategori | Tetikleyici | Saklama | Hukuki dayanak | AB min. (tipik) | Sahip | Yöntem | Notlar |
|---|---|---|---|---|---|---|---|---|
| 47 | DPIA'lar | Faaliyet sonu | Faaliyet sonrası 6 yıl | Hesap verebilirlik (Md. 35) | — | DPO | Güvenli arşiv | |
| 48 | RoPA (işleme kayıtları) | İşleme sonu | Sonrası 6 yıl | Hesap verebilirlik (Md. 30) | — | DPO | Güvenli arşiv | |
| 49 | İlgili kişi talepleri (DSAR, Md. 15–22) | Talep kapanışı | 3 yıl | Hesap verebilirlik; hukuki talepler | — | DPO | Güvenli silme | Talebin kendisi kişisel veri içerir. |
| 50 | Kişisel veri ihlali kayıtları | İhlal kapanışı | 6 yıl | Hesap verebilirlik (Md. 33(5)) | — | DPO / SecOps | Güvenli silme | |

### İşlenmiş örnek: kesişen saklama çatışması

Alman bir maaş kaydı şunları içerir:
- Kişisel tanımlayıcılar (ad, adres)
- Banka hesabı
- Vergi numarası
- Maaş tutarı
- Sağlık sigortası katkısı

Baskın hukuki sürücü Alman vergi hukukudur (§ 147 AO) — **10 yıl**. "Pazarlamanın 4. yılda kayda ihtiyacı yok" olsa bile, 10. yıla kadar silme **yasaktır**. Tersine, 10. yıl + 1 günde, başka bir hukuki dayanak (örn. aktif dava bekletme) uygulanmadıkça saklama **yasaktır**.

### Bu Çizelgeye güvenmeden önce doğrulama

Bu Çizelge, 2025 ortası itibarıyla yaygın minimumları yansıtır. **Her zaman doğrulayın**:
- Yerel üye devlet hukuku (düzenleyiciler rehberlik yayınlar ve tüzükleri düzenli olarak günceller).
- Sektöre özgü düzenlemeler (bankacılık, sigorta, telekom, sağlık).
- Son mahkeme kararları ve DPA kararları.
- Hukuki bekletme gerektiren devam eden veya öngörülen davalar.
