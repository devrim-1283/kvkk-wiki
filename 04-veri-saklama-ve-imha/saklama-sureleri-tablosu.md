---
Doküman / Document: Kişisel Veri Saklama Süreleri Tablosu / Personal Data Retention Periods Table
Bölüm / Section: 04-veri-saklama-ve-imha
Sahip / Owner: KVKK Sorumlusu / KVKK Officer
Onaylayan / Approved by: Hukuk Müdürü + Bilgi Güvenliği Yöneticisi / Legal Director + Information Security Manager
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş / Annual + triggered (regulatory change, new business process, litigation period trigger)
İlgili Mevzuat / Legal Reference: KVKK Art. 4(2)(d), Art. 7; Reg. Art. 6/1-g; Labor Law No. 4857 Art. 75; Tax Procedure Law No. 213 Art. 253; Turkish Commercial Code No. 6102 Art. 82; Turkish Code of Obligations No. 6098 Art. 146-147; Social Security Law No. 5510; Law No. 5651; Consumer Protection Law No. 6502; Payment Services Law No. 6493; AML Law No. 5549 (MASAK)
---

## English

# Personal Data Retention Periods Table

## 1. Use of the Table

- **Minimum period:** The period during which retention is mandatory under explicit legislation or due to right/litigation statute of limitations.
- **Maximum period:** At the end of this period, data falls within the scope of periodic destruction; further retention is possible only on a concrete legal ground.
- The period runs from **the date the processing purpose for which the data category was derived ends**. E.g., the personnel file period starts when employment ends.
- Period extension is possible only with a concrete **legal hold** (ongoing litigation, audit, investigation) and a joint decision of the KVKK Officer + Legal Director.
- If multiple overlapping laws apply, **the longest period** applies.

## 2. Period Decision Algorithm

```
+------------------------------------------+
| Data category determined                 |
+------------------------------------------+
              |
              v
+------------------------------------------+
| Is there an explicit period in law?      |
+------------------------------------------+
       |                       |
    yes|                     no|
       v                       v
+--------------+    +--------------------------+
| Apply        |    | Is right/litigation      |
| statutory    |    | statute of limitation    |
| period       |    | applicable?              |
+--------------+    +--------------------------+
       |                 |              |
       |              yes|            no|
       |                 v              v
       |    +--------------+   +-------------------+
       |    | Apply        |   | Period required   |
       |    | limitation   |   | by processing     |
       |    | period       |   | purpose           |
       |    +--------------+   +-------------------+
       |                 |              |
       v                 v              v
+------------------------------------------+
| Is there a legal hold?                   |
+------------------------------------------+
              |
       yes (extend during legal hold)
              |
              v
+------------------------------------------+
| Destruction calendar at end of period    |
+------------------------------------------+
```

## 3. Period Table (By Data Category)

> Periods are common practice in Turkey for organizations with 500+ employees. Subject to sectoral legislation (BDDK, SPK, EPDK, Ministry of Health, etc.), each organization should adapt to its own situation.

### 3.1. Human Resources

| # | Data Category | Legal Reason | Legal Basis | Min. Period | Max. Period | Destruction Method | Owner |
|---|---------------|--------------|-------------|-------------|-------------|--------------------|-------|
| 1 | Employee personnel file (ID, residence, diploma, contract) | Performance of contract + legal obligation | Labor Law No. 4857 Art. 75 (10 yrs), Code of Obligations No. 6098 Art. 146 (10 yrs) | 10 years from end of employment | 10 years | Paper: shredder + record; Electronic: hard-delete + log cleansing | HR |
| 2 | Payroll, wage calculation, deduction documents | Legal obligation | Tax Procedure Law Art. 253 (5 yrs), Labor Law Art. 75; Social Security 10 yrs | 10 years from relevant period | 10 years | Paper: shredder; Electronic: hard-delete | HR + Finance |
| 3 | Social Security entry/exit notifications, service records | Legal obligation | Social Security Law No. 5510 Art. 86 | 10 years from end of employment | 10 years | Paper: shredder; Electronic: hard-delete | HR |
| 4 | Occupational accident and disease records | Legal obligation + likelihood of litigation | OSH Law No. 6331 Art. 14, Code of Obligations Art. 146 | 15 years from notification (long limitation) | 15 years | Paper: shredder; Electronic: hard-delete | HR + OSH |
| 5 | Performance, training, disciplinary records | Performance of contract + legitimate interest | Labor Law No. 4857 general | 10 years from end of employment | 10 years | Electronic: hard-delete | HR |
| 6 | Rejected candidate applications (CV, interview notes) | Explicit consent + legitimate interest (future role assessment) | KVKK Art. 5/2 | 6 months after position closure; with explicit consent up to **2 years** | 2 years | Electronic: hard-delete; Paper: shredder | HR |
| 7 | Reference info accompanying job applications | Pre-contractual measures + legitimate interest | KVKK Art. 5/2 | 6 months prior to start when hired; with rejection at the same time | 2 years | Electronic: hard-delete | HR |
| 8 | Employee health reports (special category) | OSH obligation | OSH Law, Health Personnel Law | 15 years from end of employment | 15 years | Sealed envelope archive → record-based destruction | Workplace Physician + HR |
| 9 | Employee biometric records (fingerprint, face) | Explicit consent (special category) | KVKK Art. 6/2 | **Immediate** destruction at end of employment; long retention prohibited | End of employment | Electronic: crypto-erase + log | HR + Information Security |

### 3.2. Customer and Contract

| # | Data Category | Legal Reason | Legal Basis | Min. Period | Max. Period | Destruction Method | Owner |
|---|---------------|--------------|-------------|-------------|-------------|--------------------|-------|
| 10 | Customer contracts and annexes (natural person/officer) | Performance of contract + legal obligation + limitation | Code of Obligations Art. 146 (10 yrs), Commercial Code Art. 82 (10 yrs commercial retention) | 10 years from contract end | 10 years | Paper: shredder; Electronic: hard-delete + backup destruction | Legal + Relevant Unit |
| 11 | Current account, invoice, dispatch note | Legal obligation | Tax Procedure Law Art. 253 (5 yrs), Commercial Code Art. 82 (10 yrs) | 10 years from relevant period | 10 years | Paper: shredder; Electronic: hard-delete | Finance |
| 12 | Customer contact info (CRM records) | Performance of contract + legitimate interest | KVKK Art. 5/2-c, f | 10 years from contract end; commercial e-message consent managed separately | 10 years | Electronic: hard-delete | Marketing + Sales |
| 13 | Consumer complaints and replies | Legal obligation | Consumer Protection Law Art. 68 (limitation) | 5 years from complaint closure | 5 years | Electronic: hard-delete; Paper: shredder | Customer Service |

### 3.3. Financial and Tax

| # | Data Category | Legal Reason | Legal Basis | Min. Period | Max. Period | Destruction Method | Owner |
|---|---------------|--------------|-------------|-------------|-------------|--------------------|-------|
| 14 | Invoices, books, declarations | Legal obligation | Tax Procedure Law Art. 253 (5 yrs); Commercial Code Art. 82 (10 yrs) | 10 years from relevant period | 10 years | Paper: shredder + incineration; Electronic: hard-delete | Finance |
| 15 | E-invoice, e-ledger, e-archive records | Legal obligation | Tax Procedure Law Communiqués | 10 years from relevant period | 10 years | Electronic: hard-delete + backup destruction | Finance + IT |
| 16 | Bank account movements, receipts | Legal obligation + commercial retention | Commercial Code Art. 82 | 10 years from transaction date | 10 years | Paper: shredder; Electronic: hard-delete | Finance |
| 17 | Card payment info (PAN, expiry) | Performance of contract | BKM Rules, PCI-DSS | **Immediate** deletion after authorization; PAN retention prohibited; if retained masking + tokenization | End of transaction | Tokenization + crypto-erase | Payments/IT |
| 18 | Refund, chargeback records | Legal obligation + limitation | Consumer Protection Law | 5 years from transaction date | 5 years | Electronic: hard-delete | Finance |
| 19 | AML/CFT identity verification (for obliged institutions) | Legal obligation | AML Law No. 5549 Art. 6 | 8 years from end of relationship | 8 years | Electronic: hard-delete; Paper: shredder | Compliance |

### 3.4. E-Commerce and Marketing

| # | Data Category | Legal Reason | Legal Basis | Min. Period | Max. Period | Destruction Method | Owner |
|---|---------------|--------------|-------------|-------------|-------------|--------------------|-------|
| 20 | E-commerce order record (buyer, product, price, address) | Performance of contract + legal obligation | Consumer Protection Law, E-Commerce Law No. 6563 | 10 years from order completion (Commercial Code retention) | 10 years | Electronic: hard-delete | E-commerce + Finance |
| 21 | Membership/account info (name, email, phone, password hash) | Explicit consent / performance of contract | KVKK Art. 5/2 | 10 years from account deletion/termination (limitation) | 10 years | Electronic: hard-delete | E-commerce |
| 22 | Marketing consent (E-Commerce Law IYS record) | Explicit consent | E-Commerce Law Art. 6 | Until withdrawal; **3 years** for proof after withdrawal | 3 years (post-rejection) | Electronic: hard-delete | Marketing |
| 23 | Cookie data — strictly necessary | Legitimate interest | KVKK Art. 5/2-f | During session | End of session | Browser-side + server-side delete | Web/Marketing |
| 24 | Cookie data — analytics | Explicit consent | KVKK Art. 5/1 | Period stated in cookie policy (typically 13 months) | 13 months | Automatic expiry | Web/Marketing |
| 25 | Cookie data — marketing/3rd party | Explicit consent | KVKK Art. 5/1 | Per cookie policy; immediate at consent withdrawal | 13 months | Automatic expiry + end of consent | Web/Marketing |

### 3.5. Security and Monitoring

| # | Data Category | Legal Reason | Legal Basis | Min. Period | Max. Period | Destruction Method | Owner |
|---|---------------|--------------|-------------|-------------|-------------|--------------------|-------|
| 26 | CCTV footage (entrance, common areas) | Legitimate interest | KVKK Art. 5/2-f, Art. 10 disclosure requirement | 15-30 days if no incident; until end of incident if incident | 30 days (routine) | Auto-overwrite; controlled deletion after incident | Information Security + Physical Security |
| 27 | Call center voice recordings | Performance of contract + legitimate interest (quality, dispute) | KVKK Art. 5/2-c, f | 1-3 years from call (evidence); longer if sectoral mandate | 3 years (subject to sectoral exception) | Electronic: hard-delete + backup destruction | Call Center + IT |
| 28 | Web server access logs (IP, URL, timestamp) | Legal obligation | Law No. 5651 Art. 5, Hosting Provider Regulation | 6 months – 2 years from transaction (per content/host/access provider) | 2 years | Electronic: hard-delete + log rotation | IT |
| 29 | System access logs, privileged operation logs | Legitimate interest (security, audit) | KVKK Art. 12, ISO 27001 | At least 1 year; 2-5 years for critical systems | 5 years | Electronic: hard-delete + SIEM rotation | Information Security |
| 30 | Firewall, IPS, EDR event logs | Legitimate interest | KVKK Art. 12 | At least 1 year | 2 years | Electronic: hard-delete | Information Security |
| 31 | DLP event logs | Legitimate interest + breach management | KVKK Art. 12 | 1 year if no breach suspicion; until end of forensic period if breach | 5 years | Electronic: hard-delete | Information Security |
| 32 | Visitor log (paper or electronic) | Legitimate interest | KVKK Art. 5/2-f | 2 years from visit date | 2 years | Paper: shredder; Electronic: hard-delete | Physical Security |

### 3.6. Governance and Compliance

| # | Data Category | Legal Reason | Legal Basis | Min. Period | Max. Period | Destruction Method | Owner |
|---|---------------|--------------|-------------|-------------|-------------|--------------------|-------|
| 33 | KVKK data subject application and response records | Legal obligation | KVKK Art. 13, Application Communiqué | 10 years from response date (limitation) | 10 years | Electronic: hard-delete | KVKK Officer |
| 34 | Breach record system (KVKK Art. 12 breach records) | Legal obligation | KVKK Art. 12, Board decisions | At least 5 years from breach closure | 10 years | Electronic: hard-delete | KVKK Officer + Information Security |
| 35 | Destruction records (Reg. Art. 7(3)) | Legal obligation | Reg. Art. 7(3) | **At least 3 years** after operation | 5 years (recommended) | Paper: archive → shredder; Electronic: hard-delete | KVKK Officer |
| 36 | Explicit consent proof records | Legal obligation (burden of proof) | KVKK Art. 3, Art. 5/1 | Relationship period + 10 years (limitation) | 10 years | Electronic: hard-delete | KVKK Officer + Relevant Unit |
| 37 | Disclosure notice version archive | Legal obligation (proof) | KVKK Art. 10, Disclosure Communiqué | 10 years from end of applicability of relevant version | 10 years | Versioned archive | KVKK Officer |
| 38 | DPIA / VBİA reports | Legitimate interest + audit | KVKK Art. 12, Data Security Guide | 5 years from end of assessed process | 5 years | Electronic: hard-delete | KVKK Officer |

### 3.7. Suppliers and Contracted Third Parties

| # | Data Category | Legal Reason | Legal Basis | Min. Period | Max. Period | Destruction Method | Owner |
|---|---------------|--------------|-------------|-------------|-------------|--------------------|-------|
| 39 | Supplier contract and annexes (officer info) | Performance of contract + legal obligation | Code of Obligations Art. 146, Commercial Code Art. 82 | 10 years from contract end | 10 years | Paper: shredder; Electronic: hard-delete | Procurement + Legal |
| 40 | Supplier authorized contact info | Performance of contract | KVKK Art. 5/2-c | 10 years from contract end | 10 years | Electronic: hard-delete | Procurement |
| 41 | Data processor audit reports | Legitimate interest + audit | KVKK Art. 12 | 5 years from contract end | 5 years | Electronic: hard-delete | KVKK Officer + Procurement |

### 3.8. Legal and Corporate

| # | Data Category | Legal Reason | Legal Basis | Min. Period | Max. Period | Destruction Method | Owner |
|---|---------------|--------------|-------------|-------------|-------------|--------------------|-------|
| 42 | Power of attorney (natural person) | Legal obligation | Code of Obligations, related law | 10 years from end of attorneyship | 10 years | Paper: shredder | Legal |
| 43 | Personal data of company shareholders/officers | Legal obligation | Commercial Code | Shareholding/term + 10 years | 10 years | Electronic: hard-delete | Legal + HR |
| 44 | Litigation files (containing personal data) | Legal obligation | Code of Obligations Art. 146 | 10 years from finalization | 10 years | Paper: shredder; Electronic: hard-delete | Legal |
| 45 | General Assembly, Board minutes (natural person info) | Legal obligation | Commercial Code | 10 years | 10 years | Corporate archive | Legal + Board Secretariat |

## 4. Period Exceptions

### 4.1. Legal Hold

In the following cases, the retention period is paused and destruction is deferred:

- Ongoing or likely litigation (party or evidence),
- A retention order issued by a competent authority (court, prosecutor, BDDK, SPK, Competition Authority, Tax Inspectorate, etc.),
- An investigation initiated by the KVKK Board,
- Breach forensic investigation.

For data under legal hold:
- The Legal Director and KVKK Officer issue a joint written decision,
- The relevant data is flagged "hold," retention jobs are disabled,
- Within 30 days after the hold reason ends, it goes back to the standard destruction calendar,
- The hold duration and reason are recorded.

### 4.2. Withdrawal of Explicit Consent

Withdrawal of explicit consent is prospective; processing stops as soon as the withdrawal reaches the data controller. If no other legal basis exists, the data is destroyed.

## 5. Table Maintenance Discipline

- Annual scan: Regulatory change scan with the Legal Department.
- New process trigger: A row is added to the table before a new process starts; inventory and VERBİS are updated.
- Period shortening: If the Board decides otherwise (Reg. Art. 11/4 — irreparable harm or clear unlawfulness), the period is shortened.
- Period extension: Only with a concrete legal reason + Legal Department approval.

---

## Türkçe

# Kişisel Veri Saklama Süreleri Tablosu

## 1. Tablonun Kullanımı

- **Asgari süre:** Mevzuatın açıkça öngördüğü veya hak/dava zamanaşımı nedeniyle saklanması zorunlu olan süre.
- **Azami süre:** Bu sürenin sonunda veriler periyodik imha kapsamına girer; tutulması ancak somut bir hukuki sebebe dayanırsa mümkündür.
- Süre, **veri kategorisinin türetildiği işleme amacının sona erdiği tarih**ten itibaren işler. Ör. iş ilişkisi sona erdiğinde özlük dosyası süresi başlar.
- Sürenin uzaması ancak somut **legal hold** (devam eden dava, denetim, soruşturma) ile ve KVKK Sorumlusu + Hukuk Müdürü ortak kararıyla mümkündür.
- Çakışan birden fazla mevzuat varsa **en uzun süre** uygulanır.

## 2. Süre Kararı Algoritması

```
+------------------------------------------+
| Veri kategorisi belirlendi               |
+------------------------------------------+
              |
              v
+------------------------------------------+
| Mevzuatta açık süre var mı?              |
+------------------------------------------+
       |                       |
   evet|                    hayır|
       v                       v
+--------------+    +--------------------------+
| Mevzuat      |    | Hak veya dava zamanaşımı |
| süresini     |    | uygulanabilir mi?        |
| uygula       |    +--------------------------+
+--------------+         |              |
       |             evet|           hayır|
       |                 v               v
       |    +--------------+   +-------------------+
       |    | Zamanaşımını |   | İşleme amacının   |
       |    | uygula       |   | gerektirdiği süre |
       |    +--------------+   +-------------------+
       |                 |              |
       v                 v              v
+------------------------------------------+
| Legal hold var mı?                       |
+------------------------------------------+
              |
       evet (legal hold süresince uzat)
              |
              v
+------------------------------------------+
| Süre sonunda imha takvimi                |
+------------------------------------------+
```

## 3. Süre Tablosu (Veri Kategorisi Bazlı)

> Süreler, ülkemizde 500+ çalışanlı kurumsal yapılarda yaygın uygulamadır. Sektörel mevzuat (BDDK, SPK, EPDK, Sağlık Bakanlığı vb.) saklı kalmak üzere, kurum kendi durumuna uyarlamalıdır.

### 3.1. İnsan Kaynakları

| # | Veri Kategorisi | Hukuki Sebep | Mevzuat Dayanağı | Asgari Süre | Azami Süre | İmha Yöntemi | Sahibi |
|---|-----------------|--------------|------------------|-------------|------------|--------------|--------|
| 1 | Çalışan özlük dosyası (kimlik, ikamet, diploma, sözleşme) | Sözleşmenin ifası + hukuki yükümlülük | 4857 İş K. m.75 (10 yıl), 6098 TBK m.146 (10 yıl) | İş ilişkisinin bitiminden itibaren 10 yıl | 10 yıl | Kağıt: shredder + tutanak; Elektronik: hard-delete + log temizliği | İK |
| 2 | Bordro, ücret hesabı, kesinti belgeleri | Hukuki yükümlülük | 213 VUK m.253 (5 yıl), 4857 İş K. m.75; SGK 10 yıl | İlgili dönemden itibaren 10 yıl | 10 yıl | Kağıt: shredder; Elektronik: hard-delete | İK + Mali İşler |
| 3 | SGK işe giriş/çıkış bildirgeleri, hizmet dökümleri | Hukuki yükümlülük | 5510 SGK m.86 | İş ilişkisinin bitiminden itibaren 10 yıl | 10 yıl | Kağıt: shredder; Elektronik: hard-delete | İK |
| 4 | İş kazası ve meslek hastalığı kayıtları | Hukuki yükümlülük + dava ihtimali | 6331 İSG K. m.14, 6098 TBK m.146 | Olayın bildiriminden itibaren 15 yıl (uzun zamanaşımı) | 15 yıl | Kağıt: shredder; Elektronik: hard-delete | İK + İSG |
| 5 | Performans değerlendirme, eğitim, disiplin kayıtları | Sözleşmenin ifası + meşru menfaat | 4857 İş K. genel | İş ilişkisinin bitiminden itibaren 10 yıl | 10 yıl | Elektronik: hard-delete | İK |
| 6 | İşe alım sürecinde reddedilen aday başvuruları (CV, mülakat notu) | Açık rıza + meşru menfaat (gelecek pozisyon değerlendirmesi) | KVKK m.5/2 | Pozisyonun kapanması + 6 ay; açık rıza varsa azami **2 yıl** | 2 yıl | Elektronik: hard-delete; Kağıt: shredder | İK |
| 7 | İş başvurusu ile gelen referans bilgileri | Sözleşme öncesi tedbir + meşru menfaat | KVKK m.5/2 | İşe alımda işe başlamadan 6 ay; reddedilende başvuru ile birlikte | 2 yıl | Elektronik: hard-delete | İK |
| 8 | Çalışan sağlık raporları (özel nitelikli) | İSG yükümlülüğü | 6331 İSG K., Sağlık Personeli Kanunu | İş ilişkisinin bitiminden itibaren 15 yıl | 15 yıl | Kapalı zarflı arşiv → tutanaklı imha | İşyeri Hekimi + İK |
| 9 | Çalışan biyometrik kayıt (parmak izi, yüz tanıma) | Açık rıza (özel nitelikli) | KVKK m.6/2 | İş ilişkisinin bitiminden itibaren **derhal** imha; uzun saklama yasaktır | İlişki sonu | Elektronik: kripto-silme + log | İK + Bilgi Güvenliği |

### 3.2. Müşteri ve Sözleşme

| # | Veri Kategorisi | Hukuki Sebep | Mevzuat Dayanağı | Asgari Süre | Azami Süre | İmha Yöntemi | Sahibi |
|---|-----------------|--------------|------------------|-------------|------------|--------------|--------|
| 10 | Müşteri sözleşmesi ve ekleri (gerçek kişi/yetkili) | Sözleşmenin ifası + hukuki yükümlülük + zamanaşımı | 6098 TBK m.146 (10 yıl), 6102 TTK m.82 (10 yıl, ticari saklama) | Sözleşmenin sona ermesinden itibaren 10 yıl | 10 yıl | Kağıt: shredder; Elektronik: hard-delete + yedek imhası | Hukuk + İlgili Birim |
| 11 | Cari hesap, fatura, irsaliye | Hukuki yükümlülük | 213 VUK m.253 (5 yıl), 6102 TTK m.82 (10 yıl) | İlgili dönemden itibaren 10 yıl | 10 yıl | Kağıt: shredder; Elektronik: hard-delete | Mali İşler |
| 12 | Müşteri iletişim bilgileri (CRM kayıtları) | Sözleşmenin ifası + meşru menfaat | KVKK m.5/2-c, f | Sözleşme bitişinden 10 yıl; ticari elektronik ileti rızası ayrıca yönetilir | 10 yıl | Elektronik: hard-delete | Pazarlama + Satış |
| 13 | Tüketici şikayetleri ve cevapları | Hukuki yükümlülük | 6502 Tüketici K. m.68 (zamanaşımı) | Şikayet kapanmasından itibaren 5 yıl | 5 yıl | Elektronik: hard-delete; Kağıt: shredder | Müşteri Hizmetleri |

### 3.3. Mali ve Vergisel

| # | Veri Kategorisi | Hukuki Sebep | Mevzuat Dayanağı | Asgari Süre | Azami Süre | İmha Yöntemi | Sahibi |
|---|-----------------|--------------|------------------|-------------|------------|--------------|--------|
| 14 | Faturalar, defterler, beyannameler | Hukuki yükümlülük | 213 VUK m.253 (5 yıl); 6102 TTK m.82 (10 yıl) | İlgili dönemden itibaren 10 yıl | 10 yıl | Kağıt: shredder + yakma; Elektronik: hard-delete | Mali İşler |
| 15 | E-fatura, e-defter, e-arşiv kayıtları | Hukuki yükümlülük | 213 VUK Tebliğleri | İlgili dönemden itibaren 10 yıl | 10 yıl | Elektronik: hard-delete + yedek imhası | Mali İşler + BT |
| 16 | Banka hesap hareketleri, dekont | Hukuki yükümlülük + ticari saklama | 6102 TTK m.82 | İşlem tarihinden itibaren 10 yıl | 10 yıl | Kağıt: shredder; Elektronik: hard-delete | Mali İşler |
| 17 | Kart ödeme bilgisi (kart no, son kullanma) | Sözleşmenin ifası | BKM Kuralları, PCI-DSS | Yetkilendirmeden sonra **derhal** silme; PAN tutmak yasak; saklanırsa maskeleme + tokenizasyon | İşlem sonu | Tokenizasyon + kripto-silme | Ödeme/IT |
| 18 | İade, chargeback kayıtları | Hukuki yükümlülük + zamanaşımı | 6502 Tüketici K. | İşlem tarihinden 5 yıl | 5 yıl | Elektronik: hard-delete | Mali İşler |
| 19 | MASAK kapsamı kimlik tespiti (yükümlü kuruluşlarda) | Hukuki yükümlülük | 5549 MASAK K. m.6 | İlişki bitiminden 8 yıl | 8 yıl | Elektronik: hard-delete; Kağıt: shredder | Uyum |

### 3.4. E-Ticaret ve Pazarlama

| # | Veri Kategorisi | Hukuki Sebep | Mevzuat Dayanağı | Asgari Süre | Azami Süre | İmha Yöntemi | Sahibi |
|---|-----------------|--------------|------------------|-------------|------------|--------------|--------|
| 20 | E-ticaret sipariş kaydı (alıcı, ürün, fiyat, adres) | Sözleşmenin ifası + hukuki yükümlülük | 6502 Tüketici K., 6563 ETK | Sipariş tamamlanmasından 10 yıl (TTK ticari saklama) | 10 yıl | Elektronik: hard-delete | E-ticaret + Mali İşler |
| 21 | Üyelik / hesap bilgileri (ad, e-posta, telefon, parola hash'i) | Açık rıza / sözleşmenin ifası | KVKK m.5/2 | Hesabın silinmesi/feshinden 10 yıl (zamanaşımı) | 10 yıl | Elektronik: hard-delete | E-ticaret |
| 22 | Pazarlama izni (ETK İYS kaydı) | Açık rıza | 6563 ETK m.6 | İznin geri alınmasına kadar; geri alındıktan sonra ispat amaçlı **3 yıl** | 3 yıl (ret sonrası) | Elektronik: hard-delete | Pazarlama |
| 23 | Çerez verisi — zorunlu | Meşru menfaat | KVKK m.5/2-f | Oturum süresince | Oturum sonu | Tarayıcı tarafı + sunucu tarafı silme | Web/Pazarlama |
| 24 | Çerez verisi — analitik | Açık rıza | KVKK m.5/1 | Çerez politikasında belirtilen süre (genelde 13 ay) | 13 ay | Otomatik expiry | Web/Pazarlama |
| 25 | Çerez verisi — pazarlama / 3. taraf | Açık rıza | KVKK m.5/1 | Çerez politikasında belirtilen süre; rıza geri çekilince derhal | 13 ay | Otomatik expiry + rıza sonu | Web/Pazarlama |

### 3.5. Güvenlik ve İzleme

| # | Veri Kategorisi | Hukuki Sebep | Mevzuat Dayanağı | Asgari Süre | Azami Süre | İmha Yöntemi | Sahibi |
|---|-----------------|--------------|------------------|-------------|------------|--------------|--------|
| 26 | CCTV görüntü kayıtları (giriş-çıkış, ortak alan) | Meşru menfaat | KVKK m.5/2-f, m.10 aydınlatma şartı | Olay olmazsa 15-30 gün; olay halinde olay süresi sonuna kadar | 30 gün (rutin) | Otomatik üzerine yazma; olay sonrası kontrollü silme | Bilgi Güvenliği + Fiziksel Güvenlik |
| 27 | Çağrı merkezi ses kaydı | Sözleşmenin ifası + meşru menfaat (kalite, ihtilaf) | KVKK m.5/2-c, f | Çağrı tarihinden 1-3 yıl (delil); sektörel zorunluluk varsa daha uzun | 3 yıl (sektörel istisna saklı) | Elektronik: hard-delete + yedek imha | Çağrı Merkezi + BT |
| 28 | Web sunucu erişim logları (IP, URL, timestamp) | Hukuki yükümlülük | 5651 Kanun m.5, Yer Sağlayıcı Yönetmeliği | İşlem tarihinden 6 ay – 2 yıl (içerik/yer/erişim sağlayıcı niteliğine göre) | 2 yıl | Elektronik: hard-delete + log rotasyonu | BT |
| 29 | Sistem erişim logları, ayrıcalıklı işlem logları | Meşru menfaat (güvenlik, denetim) | KVKK m.12, ISO 27001 | En az 1 yıl; kritik sistemlerde 2-5 yıl | 5 yıl | Elektronik: hard-delete + SIEM rotasyonu | Bilgi Güvenliği |
| 30 | Firewall, IPS, EDR olay logları | Meşru menfaat | KVKK m.12 | En az 1 yıl | 2 yıl | Elektronik: hard-delete | Bilgi Güvenliği |
| 31 | DLP olay kayıtları | Meşru menfaat + ihlal yönetimi | KVKK m.12 | İhlal şüphesi yoksa 1 yıl; ihlalde forensic süresi sonuna kadar | 5 yıl | Elektronik: hard-delete | Bilgi Güvenliği |
| 32 | Ziyaretçi defteri (kağıt veya elektronik) | Meşru menfaat | KVKK m.5/2-f | Ziyaret tarihinden 2 yıl | 2 yıl | Kağıt: shredder; Elektronik: hard-delete | Fiziksel Güvenlik |

### 3.6. Yönetişim ve Uyum

| # | Veri Kategorisi | Hukuki Sebep | Mevzuat Dayanağı | Asgari Süre | Azami Süre | İmha Yöntemi | Sahibi |
|---|-----------------|--------------|------------------|-------------|------------|--------------|--------|
| 33 | KVKK ilgili kişi başvuru ve cevap kayıtları | Hukuki yükümlülük | KVKK m.13, Başvuru Tebliği | Başvurunun cevaplandığı tarihten 10 yıl (zamanaşımı) | 10 yıl | Elektronik: hard-delete | KVKK Sorumlusu |
| 34 | İhlal kayıt sistemi (KVKK m.12 ihlal kayıtları) | Hukuki yükümlülük | KVKK m.12, Kurul kararları | İhlalin kapanmasından sonra en az 5 yıl | 10 yıl | Elektronik: hard-delete | KVKK Sorumlusu + Bilgi Güvenliği |
| 35 | İmha tutanakları (Yön. m.7(3)) | Hukuki yükümlülük | Yön. m.7(3) | İşlemden sonra **en az 3 yıl** | 5 yıl (önerilir) | Kağıt: arşiv → shredder; Elektronik: hard-delete | KVKK Sorumlusu |
| 36 | Açık rıza ispat kayıtları | Hukuki yükümlülük (ispat yükü) | KVKK m.3, m.5/1 | İlişki süresi + 10 yıl (zamanaşımı) | 10 yıl | Elektronik: hard-delete | KVKK Sorumlusu + İlgili Birim |
| 37 | Aydınlatma metinleri sürüm arşivi | Hukuki yükümlülük (ispat) | KVKK m.10, Aydınlatma Tebliği | İlgili sürümün uygulanmadığı tarihten 10 yıl | 10 yıl | Sürümlü arşiv | KVKK Sorumlusu |
| 38 | VBİA / DPIA raporları | Meşru menfaat + denetim | KVKK m.12, Veri Güvenliği Rehberi | Risk değerlendirilen sürecin sona ermesinden 5 yıl | 5 yıl | Elektronik: hard-delete | KVKK Sorumlusu |

### 3.7. Tedarikçi ve Sözleşmeli Üçüncü Kişiler

| # | Veri Kategorisi | Hukuki Sebep | Mevzuat Dayanağı | Asgari Süre | Azami Süre | İmha Yöntemi | Sahibi |
|---|-----------------|--------------|------------------|-------------|------------|--------------|--------|
| 39 | Tedarikçi sözleşmesi ve ekleri (yetkili kişi bilgisi) | Sözleşmenin ifası + hukuki yükümlülük | 6098 TBK m.146, 6102 TTK m.82 | Sözleşmenin sona ermesinden 10 yıl | 10 yıl | Kağıt: shredder; Elektronik: hard-delete | Satınalma + Hukuk |
| 40 | Tedarikçi yetkili iletişim bilgileri | Sözleşmenin ifası | KVKK m.5/2-c | Sözleşmenin sona ermesinden 10 yıl | 10 yıl | Elektronik: hard-delete | Satınalma |
| 41 | Veri işleyen denetim raporları | Meşru menfaat + denetim | KVKK m.12 | Sözleşmenin sona ermesinden 5 yıl | 5 yıl | Elektronik: hard-delete | KVKK Sorumlusu + Satınalma |

### 3.8. Hukuki ve Kurumsal

| # | Veri Kategorisi | Hukuki Sebep | Mevzuat Dayanağı | Asgari Süre | Azami Süre | İmha Yöntemi | Sahibi |
|---|-----------------|--------------|------------------|-------------|------------|--------------|--------|
| 42 | Vekaletname (gerçek kişi) | Hukuki yükümlülük | TBK, ilgili mevzuat | Vekaletin sona ermesinden 10 yıl | 10 yıl | Kağıt: shredder | Hukuk |
| 43 | Şirket ortakları/yöneticileri kişisel verileri | Hukuki yükümlülük | 6102 TTK | Ortaklık/görev süresi + 10 yıl | 10 yıl | Elektronik: hard-delete | Hukuk + İK |
| 44 | Dava dosyaları (kişisel veri içerenler) | Hukuki yükümlülük | 6098 TBK m.146 | Karar kesinleşmesinden 10 yıl | 10 yıl | Kağıt: shredder; Elektronik: hard-delete | Hukuk |
| 45 | Genel Kurul, Yönetim Kurulu kayıtları (gerçek kişi bilgisi) | Hukuki yükümlülük | 6102 TTK | 10 yıl | 10 yıl | Kurumsal arşiv | Hukuk + Yönetim Kurulu Sekreteryası |

## 4. Süre İstisnaları

### 4.1. Legal Hold

Aşağıdaki durumlarda saklama süresi durdurulur ve verinin imhası ertelenir:

- Devam eden veya muhtemel dava (taraf veya delil),
- Yetkili merci (mahkeme, savcılık, BDDK, SPK, Rekabet Kurumu, Vergi Müfettişliği vb.) tarafından verilmiş tutma kararı,
- KVKK Kurulu tarafından başlatılmış inceleme,
- İhlal forensik incelemesi.

Legal hold uygulanan veri için:
- Hukuk Müdürü ve KVKK Sorumlusu ortak yazılı kararı düzenler,
- İlgili veri "hold" olarak işaretlenir, retention job'ları devre dışı bırakılır,
- Hold sebebi sona erdiğinde 30 gün içinde standart imha takvimine alınır,
- Hold süresi ve gerekçesi tutanağa işlenir.

### 4.2. Açık Rızanın Geri Alınması

Açık rızanın geri alınması ileriye yöneliktir; geri alma beyanının veri sorumlusuna ulaştığı andan itibaren işleme durdurulur. Başka bir hukuki dayanak yoksa veri imha edilir.

## 5. Tablo Bakım Disiplini

- Yıllık tarama: Hukuk Müdürlüğü ile mevzuat değişikliği taraması.
- Yeni süreç tetiklemesi: Yeni iş süreci başlatılmadan tabloya satır eklenir; envanter ve VERBİS güncellenir.
- Süre kısaltma: Kurul aksine karar verirse (Yön. m.11/4 — telafisi güç zarar veya açık hukuka aykırılık) süre kısaltılır.
- Süre uzatma: Sadece somut bir hukuki sebep + Hukuk Müdürlüğü onayı ile.
