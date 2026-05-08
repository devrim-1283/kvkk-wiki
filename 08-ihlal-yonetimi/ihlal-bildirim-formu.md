---
Doküman / Document: Kurul'a Kişisel Veri İhlal Bildirim Formu (Doldurulabilir) / Personal Data Breach Notification Form for the Authority (Fillable)
Bölüm / Section: 08-ihlal-yonetimi
Sahip / Owner: KVKK Sorumlusu / KVKK Officer
Onaylayan / Approved by: Hukuk Müdürü + KVKK Komitesi / Head of Legal + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + Kurul form değişikliklerinde / Annual + when Authority form changes
İlgili Mevzuat / Legal Reference: Law No. 6698 (KVKK) Art. 12(5); Authority Decision No. 2019/10 dated 24.01.2019; KVKK Data Security Guide
---

## English

# Personal Data Breach Notification Form

> **Use:** This form is content-aligned with the Authority's official "Personal Data Breach Notification Form" template. The KVKK Officer fills out this form during a breach and submits it via the Authority's web portal (ihlalbildirim.kvkk.gov.tr) or via KEP. See §3 for a worked example.

## 1. Form Structure

```
+-----------------------------------------------------+
| SECTION A - Data Controller Identification          |
| SECTION B - Breach Summary and Timeline             |
| SECTION C - Affected Personal Data                  |
| SECTION D - Attack Vector and Detection             |
| SECTION E - Measures Taken                          |
| SECTION F - Data Subject Notification Plan          |
| SECTION G - Root Cause Analysis (Phased)            |
| SECTION H - Corrective/Preventive Action (CAPA)     |
| SECTION I - Lessons Learned                         |
| SECTION J - Annexes                                 |
+-----------------------------------------------------+
```

## 2. Form Template (Fillable)

---

### SECTION A - DATA CONTROLLER IDENTIFICATION

| Field | Content |
|-------|---------|
| Data controller trade name | |
| Tax / Mersis number | |
| Field of activity (NACE code) | |
| Number of employees (at time of breach) | |
| Annual financial balance (TRY) | |
| VERBİS registration number | |
| Address | |
| KEP address | |
| Telephone | |
| Contact person (KVKK Officer) | |
| Contact e-mail | |
| Contact telephone (mobile) | |
| Foreign-resident data controller? | Yes / No |
| (If yes) Data controller representative | |

---

### SECTION B - BREACH SUMMARY AND TIMELINE

| Field | Content |
|-------|---------|
| Internal incident number | OLAY-YYYY-NNNN |
| Estimated breach date | YYYY-MM-DD HH:MM (Türkiye Time) |
| Date controller became aware (T+0) | YYYY-MM-DD HH:MM |
| Notification date | YYYY-MM-DD HH:MM |
| Elapsed time (hours) | |
| Was 72 hours exceeded? | Yes / No |
| If yes, justification | |

**Timeline (chronological):**

| Time | Event |
|------|-------|
| YYYY-MM-DD HH:MM | (e.g., SIEM alert, user complaint, etc.) |
| YYYY-MM-DD HH:MM | (e.g., Core CSIRT meeting) |
| YYYY-MM-DD HH:MM | (e.g., Containment applied) |
| YYYY-MM-DD HH:MM | (e.g., Scope determined) |
| YYYY-MM-DD HH:MM | (e.g., Notification prepared) |

**Incident Summary (3-5 sentences, written for the Authority):**

> [Our company detected a [type] attack/event on [system] on [date]. The investigation determined that personal data in category [A] across [B] records belonging to data subjects was affected. The incident is currently [active/contained/closed].]

---

### SECTION C - AFFECTED PERSONAL DATA

#### C.1. Breach Nature (multi-select)
- [ ] Confidentiality breach (unauthorized disclosure)
- [ ] Integrity breach (unauthorized alteration)
- [ ] Availability breach (unauthorized deletion/blocking)

#### C.2. Number of Data Subjects Affected
| | Estimated | Final |
|---|-----------|-------|
| Customer | | |
| Employee | | |
| Supplier representative | | |
| Candidate | | |
| Website visitor | | |
| Other (specify) | | |
| **Total** | | |

#### C.3. Number of Records Affected
> Records may differ from individual count. E.g., 1 person with 10 invoices = 1 person, 10 records.

| Database / System | Record count |
|-------------------|--------------|
| | |

#### C.4. Affected Data Categories

**General Categories:**
- [ ] Identity (name, T.R. ID, date of birth)
- [ ] Contact (telephone, e-mail, address)
- [ ] Customer transactions (orders, invoices, payment - card masked)
- [ ] Financial (IBAN, credit limit)
- [ ] Marketing (preference, segmentation)
- [ ] Location (GPS, IP)
- [ ] Process security (password - hashed/clear)
- [ ] Visual/audio (photo, voice, video)
- [ ] Professional (CV, education, work history)
- [ ] Other (specify):

**Special Categories (KVKK Art. 6):**
- [ ] Health data
- [ ] Sex life
- [ ] Race / ethnicity
- [ ] Political opinion
- [ ] Philosophical belief / religion / sect / other belief
- [ ] Dress and attire
- [ ] Association / foundation / union membership
- [ ] Criminal conviction / security measures
- [ ] Biometric / genetic

#### C.5. Was Data Published?
- [ ] No (only unauthorized access; no exfiltration outside)
- [ ] Unknown / under investigation
- [ ] Yes - evidence available (URL, screenshot)
   - Publication site: ____________________
   - Takedown requested? Yes / No

#### C.6. Was the Data Encrypted / Pseudonymized?
- [ ] Fully encrypted (AES-256, key not affected)
- [ ] Pseudonymized (identity reference separate)
- [ ] Clear-text
- [ ] Mixed - explain

---

### SECTION D - ATTACK VECTOR AND DETECTION

#### D.1. Breach Category
- [ ] Cyberattack
   - [ ] Ransomware
   - [ ] BEC / phishing / account takeover
   - [ ] Web application exploit (SQLi, IDOR, RCE)
   - [ ] Data exfiltration after DDoS
   - [ ] Software vulnerability (CVE: ____________)
   - [ ] Supply chain attack
- [ ] Insider
   - [ ] Intentional (former/current employee, contractor)
   - [ ] Accidental (wrong e-mail, mishandled sharing)
- [ ] Physical
   - [ ] Stolen/lost laptop/USB/phone
   - [ ] Archive theft
   - [ ] Natural disaster / fire / flood
- [ ] Third party (processor)
- [ ] Web scraping / unauthorized data harvesting
- [ ] Misconfiguration (public S3 bucket, etc.)
- [ ] Other:

#### D.2. Attack Vector Detail (Technical)
- Initial access:
- Lateral movement:
- Privilege escalation:
- Data collection method:
- Exfiltration method:
- IOCs (IP, hash, domain):

#### D.3. Detection Method
- [ ] SIEM correlation rule (rule name: ____________)
- [ ] EDR/XDR alert
- [ ] DLP event
- [ ] IDS/IPS
- [ ] Honeypot/canary
- [ ] Employee report
- [ ] Customer/user complaint
- [ ] Third-party report (CERT, researcher, press)
- [ ] Processor notification
- [ ] Dark web monitoring
- [ ] Coincidental (audit, other incident research)
- [ ] Other:

---

### SECTION E - MEASURES TAKEN

#### E.1. Urgent Containment (T+0 - T+24 hours)
| Measure | Time (Türkiye Time) | Owner | Result |
|---------|---------------------|-------|--------|
| | | | |

#### E.2. Technical Measures
- [ ] Affected system isolated from network
- [ ] Affected user accounts disabled
- [ ] Password reset (scope: ____________)
- [ ] MFA token revocation/reset
- [ ] API key / certificate rotation
- [ ] Vulnerability patched (CVE: ____________)
- [ ] Clean restore from backup
- [ ] Fleet-wide IOC scan with EDR
- [ ] WAF / firewall rule added
- [ ] Forensic image captured
- [ ] Other:

#### E.3. Administrative Measures
- [ ] CSIRT activation (level: ____)
- [ ] Executive escalation
- [ ] Legal / Insurance notification
- [ ] Insider breach - disciplinary / employment termination process
- [ ] Contractual sanction against processor
- [ ] Internal reminder to all employees
- [ ] Other:

#### E.4. Continuing / Recommended Measures
> Short- and long-term durable measures planned.

---

### SECTION F - DATA SUBJECT NOTIFICATION PLAN

| Field | Content |
|-------|---------|
| Will notification be made? | Yes / No (if no, justification) |
| Notification method | E-mail / SMS / KEP / Postal / Web banner / Press |
| Dual-channel use | Yes / No |
| Estimated first notification date | YYYY-MM-DD |
| Estimated completion date | YYYY-MM-DD |
| Notification text ready? | Yes (attached) / In preparation |
| Data subject support line set up? | Yes / No |
| Free protection service offered? | Yes (e.g., credit monitoring) / No |

---

### SECTION G - ROOT CAUSE ANALYSIS (PHASED - MAY BE INCOMPLETE AT FIRST NOTIFICATION)

| Stage | Content |
|-------|---------|
| Direct cause | |
| Facilitating factor (human) | |
| Facilitating factor (process) | |
| Facilitating factor (technical) | |
| Systemic root cause | |

> See `kok-neden-analizi.md` for the full RCA report attached.

---

### SECTION H - CORRECTIVE / PREVENTIVE ACTION (CAPA)

| Action | Type (C/P) | Owner | Target Date | Status |
|--------|-----------|-------|-------------|--------|
| | | | | |

---

### SECTION I - LESSONS LEARNED

> 5-10 items at a clarity level fit for inclusion in the next tabletop scenario and training update.

1.
2.
3.

---

### SECTION J - ANNEXES

- [ ] Forensic summary report (PDF)
- [ ] Data subject notification draft (e-mail + SMS + web)
- [ ] Insurer notification confirmation
- [ ] Police lost-device report (if any)
- [ ] Processor contractual sanction letter
- [ ] Screenshots / IOC list
- [ ] Data category-count detail table
- [ ] Other:

**Form Completion:**

| Field | Content |
|-------|---------|
| Form completed by | (Name, title) |
| Date | YYYY-MM-DD |
| KVKK Officer approval | (Signature / KEP) |
| Head of Legal approval | (Signature / KEP) |

---

## 3. Worked Example: Ransomware with Employee HR Data Leak

### SECTION A
| Field | Content |
|-------|---------|
| Data controller trade name | ABC Sanayi ve Ticaret A.Ş. |
| Tax number | 1234567890 |
| Field of activity | Automotive supplier industry (NACE 29.32) |
| Number of employees | 612 |
| VERBİS registration | 12345-1 |
| Address | OSB 3. Cadde No:5, Bursa |
| KEP address | abcsanayi@hs01.kep.tr |
| Telephone | +90 224 XXX XX XX |
| Contact person | Ayşe Yılmaz, KVKK Officer |
| Contact e-mail | kvkk@abcsanayi.com.tr |
| Contact telephone | +90 532 XXX XX XX |
| Foreign-resident data controller | No |

### SECTION B
| Field | Content |
|-------|---------|
| Incident number | OLAY-2026-0042 |
| Estimated breach date | 2026-05-04 22:30 (Türkiye Time) |
| Awareness date (T+0) | 2026-05-05 08:15 |
| Notification date | 2026-05-07 14:00 |
| Elapsed | 53 hours 45 minutes |
| 72 hours exceeded? | No |

**Timeline:**
| Time | Event |
|------|-------|
| 2026-05-04 22:30 | First suspicious RDP login (audit log) |
| 2026-05-04 23:15 | Lateral movement - domain admin account use |
| 2026-05-05 03:00 | Bulk read on HR file server |
| 2026-05-05 06:00 | Encryption begins (LockBit variant) |
| 2026-05-05 08:00 | First employee reports inability to access files (helpdesk) |
| 2026-05-05 08:15 | SOC L2 confirms breach suspicion -> **T+0** |
| 2026-05-05 08:45 | CISO + KVKK Officer + Legal informed |
| 2026-05-05 09:00 | CSIRT Level 3 activation |
| 2026-05-05 09:30 | Affected servers isolated from network |
| 2026-05-05 12:00 | Forensic imaging completed |
| 2026-05-05 18:00 | Affected data scope preliminary report: 612 employee HR files |
| 2026-05-06 10:00 | Restore from backup begins |
| 2026-05-06 16:00 | Insurer notification (cyber policy activation) |
| 2026-05-07 09:00 | Data subject notification text ready |
| 2026-05-07 14:00 | **Authority notification submitted** |

**Incident Summary:**
> "ABC Sanayi A.Ş. detected a LockBit-variant ransomware attack on its HR file server during the night of 4-5 May 2026. The attacker compromised the RDP account of an outsourced IT contractor through password leakage and accessed the personnel files of 612 employees. Forensic evidence indicates the files were copied before encryption. Affected data: ID copies, IBAN, salary information, health reports (special category). The system was isolated on the morning of 5 May and restored from clean backup. Direct notification is being prepared for affected employees."

### SECTION C
| C.1 Breach Nature | [x] Confidentiality [x] Availability |
| C.2 Affected | 612 employees (final) + 35 former employees (total 647) |
| C.3 Records | 5,847 documents |
| C.4 Categories | General: Identity, Contact, Financial (IBAN), Professional<br>Special category: **Health reports (pre-employment medicals, absence reports)** |
| C.5 Published? | Unknown - the attacker has placed a 7-day countdown on the dark-web leak page; with no payment, publication risk is high. |
| C.6 Encrypted? | Clear-text (PDFs, no BitLocker on file system) |

### SECTION D
| D.1 Category | [x] Cyberattack -> Ransomware (LockBit) |
| D.2 Vector | Initial access: outsourced IT contractor RDP account (password leak, MFA absent).<br>Lateral movement: Mimikatz credential dump.<br>Exfiltration: rclone upload to MEGA (12 GB). |
| D.3 Detection | EDR alert (LockBit signature) + employee helpdesk complaint |

### SECTION E
| E.2 Technical | [x] Isolation [x] Account disable [x] Password reset (all admins) [x] MFA enforced (incl. RDP) [x] Clean restore from backup [x] Forensic imaging [x] Fleet-wide EDR scan [x] WAF rules |
| E.3 Administrative | [x] CSIRT Level 3 [x] Board briefing [x] Legal + insurance [x] Contractor contract suspended |

### SECTION F
- Notification method: KEP (registered employee e-mail) + SMS + HR meeting
- First notification: 2026-05-09
- Completion: 2026-05-12
- Support line: Call center 0850-XXX (KVKK specialist)
- Free service: 12 months credit monitoring for affected employees

### SECTION G (Phased - at first notification)
- Direct cause: Lack of MFA on contractor account + shared password.
- Human: Contractor password hygiene gaps; employee awareness.
- Process: Third-party access policy left MFA optional.
- Technical: RDP external access not behind VPN; weak network segmentation.
- Systemic: Vendor security audits should be quarterly, not annual.

### SECTION H (CAPA - summary)
| Action | Type | Owner | Target |
|--------|------|-------|--------|
| MFA mandatory on all remote access | Corrective | CISO | 2026-05-15 |
| RDP only behind VPN | Corrective | Network | 2026-05-20 |
| Vendor security questionnaire annual -> quarterly | Preventive | Procurement | 2026-06-01 |
| EDR on all servers (100% coverage) | Corrective | CISO | 2026-05-30 |
| Employee + contractor awareness training | Preventive | HR + KVKK | 2026-06-15 |
| Backups become immutable (S3 Object Lock) | Preventive | Infrastructure | 2026-07-01 |
| Leak monitoring service (dark web) | Preventive | CISO | 2026-05-30 |

### SECTION I (Lessons - summary)
1. Third-party access is our highest-risk vector; zero-trust model is mandatory.
2. MFA cannot be optional - all external access without exception.
3. Without immutable backups, ransomware finds room for ransom negotiation.
4. Detection could have been 9 hours earlier with tighter EDR rules.
5. HR files should be encrypted at rest (file-level encryption), not stored in clear text.
6. Crisis communication text was ready in 24 hours - the pre-approved template worked.

### SECTION J Annexes
- [x] Forensic summary report (Mandiant, 12 pages)
- [x] Data subject e-mail + SMS text
- [x] Insurer notification confirmation
- [x] IOC list (IP, hash, domain)
- [x] Data category-count table

---

## 4. Form Retention

- The completed form is recorded in the **Authority Correspondence Log**.
- The original KEP evidence chain is retained in the insured archive for **10 years**.
- Internal versions (drafts, redactions) **are not deleted** - retained for the audit trail.

## 5. Version History

| Version | Date | Change | Approval |
|---------|------|--------|----------|
| 1.0 | 2026-05-08 | First publication | KVKK Committee |

---

## Türkçe

# Kişisel Veri İhlal Bildirim Formu

> **Kullanım:** Bu form Kurul'un resmî "Kişisel Veri İhlal Bildirim Formu" şablonu ile içerik olarak paraleldir. KVKK Sorumlusu, ihlal anında bu formu doldurarak Kurul'un web portalına (ihlalbildirim.kvkk.gov.tr) ya da KEP üzerinden yükler. Doldurulmuş örnek için §3'e bakınız.

## 1. Form Yapısı

```
┌─────────────────────────────────────────────────────┐
│ BÖLÜM A — Veri Sorumlusu Kimlik Bilgileri           │
│ BÖLÜM B — İhlal Özeti ve Zaman Çizgisi              │
│ BÖLÜM C — Etkilenen Kişisel Veri                    │
│ BÖLÜM D — Saldırı Vektörü ve Tespit                 │
│ BÖLÜM E — Alınan Tedbirler                          │
│ BÖLÜM F — İlgili Kişi Bildirim Planı                │
│ BÖLÜM G — Kök Neden Analizi (Aşamalı)               │
│ BÖLÜM H — Düzeltici/Önleyici Aksiyon (CAPA)         │
│ BÖLÜM İ — Öğrenilen Dersler                         │
│ BÖLÜM J — Ekler                                     │
└─────────────────────────────────────────────────────┘
```

## 2. Form Şablonu (Doldurulabilir)

---

### BÖLÜM A — VERİ SORUMLUSU KİMLİK BİLGİLERİ

| Alan | İçerik |
|------|--------|
| Veri sorumlusu unvanı | |
| Vergi numarası / Mersis No | |
| Faaliyet alanı (NACE kodu) | |
| Çalışan sayısı (ihlal anı) | |
| Yıllık mali bilanço (TL) | |
| VERBİS sicil numarası | |
| Adres | |
| KEP adresi | |
| Telefon | |
| İrtibat kişisi (KVKK Sorumlusu) | |
| İrtibat e-posta | |
| İrtibat telefon (cep) | |
| Yurt dışı veri sorumlusu mu? | Evet / Hayır |
| (Evet ise) Veri sorumlusu temsilcisi | |

---

### BÖLÜM B — İHLAL ÖZETİ VE ZAMAN ÇİZGİSİ

| Alan | İçerik |
|------|--------|
| Olay numarası (iç) | OLAY-YYYY-NNNN |
| İhlalin gerçekleştiği tahmini tarih | YYYY-AA-GG SS:DD (TRT) |
| Veri sorumlusunun ihlali öğrendiği tarih (T+0) | YYYY-AA-GG SS:DD (TRT) |
| Bildirim tarihi | YYYY-AA-GG SS:DD (TRT) |
| Geçen süre (saat) | |
| 72 saati aştı mı? | Evet / Hayır |
| Aştıysa gerekçe | |

**Zaman Çizgisi (Kronolojik):**

| Zaman | Olay |
|-------|------|
| YYYY-AA-GG SS:DD | (örn. SIEM alarmı, kullanıcı şikayeti, vb.) |
| YYYY-AA-GG SS:DD | (örn. Çekirdek CSIRT toplantısı) |
| YYYY-AA-GG SS:DD | (örn. Sınırlandırma uygulandı) |
| YYYY-AA-GG SS:DD | (örn. Kapsam belirlendi) |
| YYYY-AA-GG SS:DD | (örn. Bildirim hazırlandı) |

**Olay Özeti (3-5 cümle, Kurul okuyacak şekilde):**

> [Şirketimiz X tarihinde Y sistemi üzerinde Z türü bir saldırı/olay tespit etmiştir. Yapılan incelemede A kategorisindeki kişisel verilerin B sayıda ilgili kişiye ait kayıt bağlamında etkilendiği belirlenmiştir. Olay halen [aktif/sınırlandırılmış/sonlandırılmış] durumdadır.]

---

### BÖLÜM C — ETKİLENEN KİŞİSEL VERİ

#### C.1. İhlal Niteliği (Birden çok seçilebilir)
- [ ] Gizlilik ihlali (yetkisiz açığa çıkma)
- [ ] Bütünlük ihlali (yetkisiz değiştirme)
- [ ] Erişilebilirlik ihlali (yetkisiz silme/engelleme)

#### C.2. Etkilenen İlgili Kişi Sayısı
| | Tahmini | Nihai |
|---|---------|-------|
| Müşteri | | |
| Çalışan | | |
| Tedarikçi temsilcisi | | |
| Aday | | |
| Web sitesi ziyaretçisi | | |
| Diğer (belirtiniz) | | |
| **Toplam** | | |

#### C.3. Etkilenen Kayıt Sayısı
> Kayıt sayısı kişi sayısından farklı olabilir. Örn. 1 kişiye ait 10 fatura → 1 kişi, 10 kayıt.

| Veri tabanı / sistem | Kayıt sayısı |
|----------------------|--------------|
| | |

#### C.4. Etkilenen Veri Kategorileri

**Genel Nitelikli:**
- [ ] Kimlik (ad-soyad, T.C. no, doğum tarihi)
- [ ] İletişim (telefon, e-posta, adres)
- [ ] Müşteri işlem (sipariş, fatura, ödeme — kart maskeli)
- [ ] Finansal (IBAN, kredi limiti)
- [ ] Pazarlama (tercih, segmentasyon)
- [ ] Lokasyon (GPS, IP)
- [ ] İşlem güvenliği (parola — hash/clear)
- [ ] Görsel/işitsel (fotoğraf, ses, video)
- [ ] Mesleki (özgeçmiş, eğitim, çalışma geçmişi)
- [ ] Diğer (belirtiniz):

**Özel Nitelikli (KVKK m.6):**
- [ ] Sağlık verileri
- [ ] Cinsel hayat
- [ ] Irk / etnik köken
- [ ] Siyasi düşünce
- [ ] Felsefi inanç / din / mezhep / diğer inanç
- [ ] Kılık-kıyafet
- [ ] Dernek / vakıf / sendika üyeliği
- [ ] Ceza mahkûmiyeti / güvenlik tedbirleri
- [ ] Biyometrik / genetik

#### C.5. Veri Yayımlandı mı?
- [ ] Hayır (sadece yetkisiz erişim, sızıntı dışarıda yok)
- [ ] Bilinmiyor / araştırılıyor
- [ ] Evet — kanıt var (URL, ekran görüntüsü)
   - Yayım yeri: ____________________
   - Erişim engeli talep edildi mi? Evet / Hayır

#### C.6. Şifrelenmiş / Pseudonymized mıydı?
- [ ] Tam şifreli (AES-256, anahtar etkilenmedi)
- [ ] Pseudonymized (kimlik referansı ayrı)
- [ ] Açık (clear-text)
- [ ] Karma — açıklayınız

---

### BÖLÜM D — SALDIRI VEKTÖRÜ VE TESPİT

#### D.1. İhlal Kategorisi
- [ ] Siber saldırı
   - [ ] Ransomware
   - [ ] BEC / kimlik avı / hesap ele geçirme
   - [ ] Web uygulaması istismarı (SQLi, IDOR, RCE)
   - [ ] DDoS sonrası veri sızdırma
   - [ ] Yazılım açığı (CVE: ____________)
   - [ ] Tedarik zinciri saldırısı
- [ ] İçeriden (insider)
   - [ ] Kasıtlı (eski/aktif çalışan, yüklenici)
   - [ ] Kasıtsız (yanlış e-posta, hatalı paylaşım)
- [ ] Fiziksel
   - [ ] Çalıntı/kayıp dizüstü/USB/telefon
   - [ ] Arşiv hırsızlığı
   - [ ] Doğal afet / yangın / su baskını
- [ ] Üçüncü taraf (veri işleyen)
- [ ] Web scraping / yetkisiz veri toplama
- [ ] Yapılandırma hatası (S3 bucket public, vb.)
- [ ] Diğer:

#### D.2. Saldırı Vektörü Detayı (Teknik)
- Giriş yöntemi:
- Yatay hareket:
- Yükselme (privilege escalation):
- Veri toplama yöntemi:
- Veri çıkarma yöntemi (exfil):
- IOC'ler (IP, hash, domain):

#### D.3. Tespit Yöntemi
- [ ] SIEM korelasyon kuralı (kural adı: ____________)
- [ ] EDR/XDR alarmı
- [ ] DLP olayı
- [ ] IDS/IPS
- [ ] Honeypot/canary
- [ ] Çalışan ihbarı
- [ ] Müşteri/kullanıcı şikayeti
- [ ] Üçüncü taraf bildirimi (CERT, araştırmacı, basın)
- [ ] Veri işleyen bildirimi
- [ ] Dark web izleme
- [ ] Tesadüfi (denetim, başka olay araştırması)
- [ ] Diğer:

---

### BÖLÜM E — ALINAN TEDBİRLER

#### E.1. Acil Sınırlandırma (T+0 - T+24 saat)
| Tedbir | Saat (TRT) | Sahip | Sonuç |
|--------|-----------|-------|-------|
| | | | |

#### E.2. Teknik Tedbirler
- [ ] Etkilenen sistem ağdan izole edildi
- [ ] Etkilenen kullanıcı hesapları disable
- [ ] Parola sıfırlama (kapsam: ____________)
- [ ] MFA token iptali / sıfırlama
- [ ] API anahtar / sertifika rotasyonu
- [ ] Açık kapatıldı / yama uygulandı (CVE: ____________)
- [ ] Yedekten temiz geri yükleme
- [ ] EDR ile tüm filo IOC taraması
- [ ] WAF / firewall kuralı eklendi
- [ ] Forensik imaj alındı
- [ ] Diğer:

#### E.3. İdari Tedbirler
- [ ] CSIRT aktivasyonu (seviye: ____)
- [ ] Yönetim eskalasyonu
- [ ] Hukuk / Sigorta bildirimi
- [ ] İçeriden ihlal — disiplin / iş akdi feshi süreci
- [ ] Veri işleyen ile sözleşmesel yaptırım
- [ ] Tüm çalışanlara hatırlatma duyurusu
- [ ] Diğer:

#### E.4. Sürdürülen / Önerilen Tedbirler
> Kısa ve uzun vadede planlanan kalıcı önlemler.

---

### BÖLÜM F — İLGİLİ KİŞİ BİLDİRİM PLANI

| Alan | İçerik |
|------|--------|
| Bildirim yapılacak mı? | Evet / Hayır (Hayır ise gerekçe) |
| Bildirim yöntemi | E-posta / SMS / KEP / Posta / Web banner / Basın |
| Çift kanal kullanımı | Evet / Hayır |
| Tahmini ilk bildirim tarihi | YYYY-AA-GG |
| Tahmini tamamlanma tarihi | YYYY-AA-GG |
| Bildirim metni hazır mı? | Evet (ek olarak verildi) / Hazırlanıyor |
| İlgili kişi destek hattı kuruldu mu? | Evet / Hayır |
| Ücretsiz koruma hizmeti sunuluyor mu? | Evet (örn. kredi izleme) / Hayır |

---

### BÖLÜM G — KÖK NEDEN ANALİZİ (AŞAMALI — İLK BİLDİRİMDE EKSİK OLABİLİR)

| Aşama | İçerik |
|-------|--------|
| Doğrudan neden | |
| Kolaylaştırıcı faktör (insan) | |
| Kolaylaştırıcı faktör (süreç) | |
| Kolaylaştırıcı faktör (teknik) | |
| Sistemik kök neden | |

> RCA detayları için bkz. `kok-neden-analizi.md` ekteki tam rapor.

---

### BÖLÜM H — DÜZELTİCİ / ÖNLEYİCİ AKSİYON (CAPA)

| Aksiyon | Tip (D/Ö) | Sahip | Hedef Tarih | Durum |
|---------|-----------|-------|-------------|-------|
| | | | | |

---

### BÖLÜM İ — ÖĞRENİLEN DERSLER

> 5-10 madde, gelecek tatbikat senaryosuna ve eğitim güncellemesine girecek netlikte.

1.
2.
3.

---

### BÖLÜM J — EKLER

- [ ] Forensik özet raporu (PDF)
- [ ] İlgili kişi bildirim metni taslağı (e-posta + SMS + web)
- [ ] Sigortacı bildirim onayı
- [ ] Karakola ihbar tutanağı (gerekiyorsa)
- [ ] Veri işleyen sözleşme yaptırım yazısı
- [ ] Ekran görüntüleri / IOC listesi
- [ ] Veri kategori-sayı detay tablosu
- [ ] Diğer:

**Form Doldurma:**

| Alan | İçerik |
|------|--------|
| Formu dolduran | (Ad-Soyad, ünvan) |
| Tarih | YYYY-AA-GG |
| KVKK Sorumlusu onayı | (İmza / KEP) |
| Hukuk Müdürü onayı | (İmza / KEP) |

---

## 3. Doldurulmuş Örnek: Ransomware ile Çalışan IK Verisi Sızıntısı

### BÖLÜM A
| Alan | İçerik |
|------|--------|
| Veri sorumlusu unvanı | ABC Sanayi ve Ticaret A.Ş. |
| Vergi numarası | 1234567890 |
| Faaliyet alanı | Otomotiv yan sanayi (NACE 29.32) |
| Çalışan sayısı | 612 |
| VERBİS sicil numarası | 12345-1 |
| Adres | OSB 3. Cadde No:5, Bursa |
| KEP adresi | abcsanayi@hs01.kep.tr |
| Telefon | +90 224 XXX XX XX |
| İrtibat kişisi | Ayşe Yılmaz, KVKK Sorumlusu |
| İrtibat e-posta | kvkk@abcsanayi.com.tr |
| İrtibat telefon | +90 532 XXX XX XX |
| Yurt dışı veri sorumlusu | Hayır |

### BÖLÜM B
| Alan | İçerik |
|------|--------|
| Olay numarası | OLAY-2026-0042 |
| İhlal tahmini tarihi | 2026-05-04 22:30 (TRT) |
| Öğrenme tarihi (T+0) | 2026-05-05 08:15 (TRT) |
| Bildirim tarihi | 2026-05-07 14:00 (TRT) |
| Geçen süre | 53 saat 45 dakika |
| 72 saati aştı mı? | Hayır |

**Zaman Çizgisi:**
| Zaman | Olay |
|-------|------|
| 2026-05-04 22:30 | İlk şüpheli RDP girişi (audit log) |
| 2026-05-04 23:15 | Yatay hareket — domain admin hesap kullanımı |
| 2026-05-05 03:00 | İK dosya sunucusunda toplu okuma |
| 2026-05-05 06:00 | Şifreleme başlıyor (LockBit varyantı) |
| 2026-05-05 08:00 | İlk çalışan dosyaya erişemediğini bildiriyor (helpdesk) |
| 2026-05-05 08:15 | SOC L2 ihlal şüphesini doğruluyor → **T+0** |
| 2026-05-05 08:45 | CISO + KVKK Sorumlusu + Hukuk haberdar |
| 2026-05-05 09:00 | CSIRT Seviye 3 aktivasyon |
| 2026-05-05 09:30 | Etkilenen sunucular ağdan izole |
| 2026-05-05 12:00 | Forensik imaj alımı tamamlandı |
| 2026-05-05 18:00 | Etkilenen veri kapsamı ön rapor: 612 çalışan IK dosyası |
| 2026-05-06 10:00 | Yedekten geri yükleme başladı |
| 2026-05-06 16:00 | Sigortacı bildirimi (siber poliçe aktivasyonu) |
| 2026-05-07 09:00 | İlgili kişi bildirim metni hazır |
| 2026-05-07 14:00 | **Kurul'a bildirim** |

**Olay Özeti:**
> "ABC Sanayi A.Ş.'nin İK dosya sunucusunda 4-5 Mayıs 2026 gecesi LockBit varyantı bir fidye yazılımı saldırısı tespit edilmiştir. Saldırgan, dış kaynak IT yüklenicisinin RDP hesabını parola sızıntısı yoluyla ele geçirmiş ve 612 çalışana ait özlük dosyalarına erişim sağlamıştır. Dosyalar şifrelenmeden önce kopyalandığına dair forensik delil bulunmaktadır. Etkilenen veriler: kimlik fotokopisi, IBAN, ücret bilgisi, sağlık raporları (özel nitelikli). Sistem 5 Mayıs sabahı izole edilmiş, temiz yedekten kurtarılmıştır. Etkilenen çalışanlara doğrudan bildirim hazırlanmaktadır."

### BÖLÜM C
| C.1 İhlal Niteliği | ☑ Gizlilik ☑ Erişilebilirlik |
| C.2 Etkilenen kişi | 612 çalışan (kesin) + 35 eski çalışan (toplam 647) |
| C.3 Kayıt sayısı | 5.847 doküman |
| C.4 Veri kategorileri | Genel: Kimlik, İletişim, Finansal (IBAN), Mesleki<br>Özel nitelik: **Sağlık raporları (işe giriş muayenesi, devamsızlık raporu)** |
| C.5 Yayımlandı mı? | Bilinmiyor — saldırgan dark web sızıntı sayfasına 7 gün geri sayım koymuştur, ödenmediği için yayım riski yüksektir. |
| C.6 Şifreli mi? | Açık (clear-text PDF, dosya sistemi BitLocker yoktu) |

### BÖLÜM D
| D.1 Kategori | ☑ Siber saldırı → Ransomware (LockBit) |
| D.2 Vektör | İlk giriş: dış kaynak IT yüklenici RDP hesabı (parola sızıntısı, MFA yoktu).<br>Yatay hareket: Mimikatz ile credential dump.<br>Veri çıkarma: rclone ile MEGA bulutuna 12 GB upload. |
| D.3 Tespit | EDR alarmı (LockBit imza) + çalışan helpdesk şikayeti |

### BÖLÜM E
| E.2 Teknik tedbirler | ☑ İzolasyon ☑ Hesap disable ☑ Parola reset (tüm yöneticiler) ☑ MFA zorunlu kılındı (RDP dahil) ☑ Yedekten temiz geri yükleme ☑ Forensik imaj ☑ Tüm filo EDR taraması ☑ WAF kuralları |
| E.3 İdari | ☑ CSIRT Seviye 3 ☑ YK bilgilendirme ☑ Hukuk + sigorta ☑ Yüklenici sözleşme askıya alındı |

### BÖLÜM F
- Bildirim yöntemi: KEP (kayıtlı çalışan e-posta) + SMS + İK görüşme
- İlk bildirim: 2026-05-09
- Tamamlanma: 2026-05-12
- Destek hattı: Çağrı merkezi 0850-XXX (KVKK uzman)
- Ücretsiz hizmet: Etkilenen çalışanlara 12 ay kredi izleme servisi

### BÖLÜM G (Aşamalı — ilk bildirimde)
- Doğrudan neden: Yüklenici hesabında MFA yokluğu + paylaşılan parola.
- İnsan: Yüklenici parola hijyeni eksik, çalışan farkındalık.
- Süreç: Üçüncü taraf erişim politikası MFA'yı opsiyonel bırakıyordu.
- Teknik: RDP dış erişim VPN arkasında değildi, network segmentasyonu zayıftı.
- Sistemik: Yüklenici güvenlik denetimi yıllık değil çeyreklik olmalı.

### BÖLÜM H (CAPA — özet)
| Aksiyon | Tip | Sahip | Hedef |
|---------|-----|-------|-------|
| Tüm uzaktan erişimde MFA zorunlu | Düzeltici | CISO | 2026-05-15 |
| RDP yalnız VPN arkasında | Düzeltici | Network | 2026-05-20 |
| Yüklenici güvenlik anketi yıllık → çeyreklik | Önleyici | Tedarik | 2026-06-01 |
| EDR tüm sunucular (kapsam %100) | Düzeltici | CISO | 2026-05-30 |
| Çalışan + yüklenici farkındalık eğitimi | Önleyici | İK + KVKK | 2026-06-15 |
| Yedek immutable olacak (S3 Object Lock) | Önleyici | Altyapı | 2026-07-01 |
| Sızıntı izleme servisi (dark web) | Önleyici | CISO | 2026-05-30 |

### BÖLÜM İ (Dersler — özet)
1. Üçüncü taraf erişimi en yüksek risk vektörümüz; sıfır güven (zero trust) modeli zorunlu.
2. MFA opsiyonel olamaz — istisnasız tüm dış erişim.
3. Yedeklerin immutable olmadığı durumda ransomware fidyeli pazarlık zemini bulur.
4. Olay tespiti EDR ile 9 saat erken yapılabilirdi — kural setlerini sıkılaştır.
5. İK dosyaları açık metin değil şifreli depolanmalı (file-level encryption).
6. Kriz iletişim metni 24 saatte hazırlanabildi — pre-approved şablon işe yaradı.

### BÖLÜM J Ekler
- ☑ Forensik özet rapor (Mandiant, 12 sayfa)
- ☑ İlgili kişi e-posta + SMS metni
- ☑ Sigortacı bildirim onayı
- ☑ IOC listesi (IP, hash, domain)
- ☑ Veri kategori-sayı tablosu

---

## 4. Form Saklama

- Doldurulmuş form **Kurul Yazışma Defteri**ne işlenir.
- Orijinal KEP delil zinciri sigortalı arşivde **10 yıl** saklanır.
- İç versiyonlar (taslak, redaksiyon) **silinmez** — denetim zinciri için saklanır.

## 5. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi |
