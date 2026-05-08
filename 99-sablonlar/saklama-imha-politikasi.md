---
Doküman / Document: Kişisel Veri Saklama ve İmha Politikası — Şablon / Personal Data Retention and Destruction Policy — Template
Bölüm / Section: 99-sablonlar
Sahip / Owner: KVKK Sorumlusu / KVKK Officer
Onaylayan / Approved by: KVKK Komitesi + Yönetim Kurulu — KVKK Committee + Board of Directors
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş — Annual + triggered
İlgili Mevzuat / Legal Reference: 6698 sayılı KVKK m.7; İmha Yönetmeliği m.5 ve m.6 — KVKK Art. 7; Erasure Regulation Arts. 5 and 6
---

## English

# [COMPANY FULL LEGAL NAME] — PERSONAL DATA RETENTION AND DESTRUCTION POLICY (English equivalent)

The Turkish version below is the legally binding text. The English equivalent is provided for international groups; for legal force in Türkiye, the Turkish text governs.

## 1. PURPOSE

This Policy sets out the procedures and principles for erasure, destruction or anonymisation of personal data processed by [COMPANY FULL LEGAL NAME] (the "Company") as data controller, in compliance with Law No. 6698 on the Protection of Personal Data ("KVKK"), the Regulation on the Erasure, Destruction or Anonymisation of Personal Data ("Erasure Regulation") and related legislation.

## 2. SCOPE

This Policy applies to all personal data processed in all units of the Company, in all physical and electronic media, and to all employees, contractors, interns, suppliers and other business partners processing such data.

## 3. LEGAL BASIS

| Legislation | Article |
|-------------|---------|
| KVKK | Art. 4/d (retention period principle); Art. 7 (erasure/destruction/anonymisation); Art. 16 (Registry and policy obligation) |
| Erasure Regulation | Arts. 5, 6 (minimum elements); Arts. 7-10 (methods); Art. 11 (periodic destruction); Art. 12 (on-request destruction) |
| Disclosure Communiqué | Art. 4 (statement of retention period in privacy notice) |
| VERBİS Regulation | Art. 9/f (retention period in VERBİS notification) |

## 4. DEFINITIONS

| Term | Definition |
|------|------------|
| Personal Data | Any information relating to an identified or identifiable natural person |
| Sensitive Personal Data | Data listed in KVKK Art. 6/1 |
| Retention Period | Period for which personal data must be retained for the processing purpose |
| Destruction | Erasure, destruction or anonymisation |
| Erasure | Rendering inaccessible and unusable in any way for relevant users |
| Destruction | Rendering inaccessible, irretrievable and unusable by anyone, in any way |
| Anonymisation | Rendering data such that they cannot be associated with an identified or identifiable natural person even when matched with other data |
| Periodic Destruction | Recurring, ex officio destruction of data when statutory conditions for processing have ceased |
| Relevant User | Department/personnel responsible for storage, processing or technical maintenance |

## 5. RECORDING MEDIA (Erasure Reg. Art. 6/b)

### 5.1 Electronic Media

| Medium | Description |
|--------|-------------|
| Servers (DNS, web, email, file, application servers, etc.) | Company central data centre and DR centre |
| Software (SAP/ERP, CRM, HR, finance, payroll, call centre, e-commerce platforms) | Enterprise software for business processes |
| Information security devices (firewall, IDS, antivirus, log server) | Security and monitoring |
| Personal computers (desktop, laptop, tablet) | User endpoints |
| Mobile devices (phone) | Corporate devices (under MDM) |
| Optical (CD, DVD), magnetic (HDD, external HDD), USB | Backup and transfer media |
| Printer, scanner, photocopier | Disk-bearing peripherals |
| Cloud systems (authorised vendors) | Under DPA |

### 5.2 Physical Media

| Medium | Description |
|--------|-------------|
| Paper | Employment contract, personnel file, invoice, petition |
| Manual filing systems | Survey forms, application forms |
| Written, printed, visual media | Training materials, internal publications |

## 6. REASONS REQUIRING RETENTION AND DESTRUCTION (Erasure Reg. Art. 6/c)

### 6.1 Reasons for Retention

- KVKK and related legislation
- Other applicable laws (Labour Law, SSI, OHSS, Tax Procedure Law, Code of Obligations, Commercial Code, Consumer Law, Banking Law, Financial Leasing Law, etc.)
- Contractual obligations
- Establishment, exercise or protection of rights
- Necessity for legitimate interests (likely dispute, fraud prevention, service quality)
- Express obligations stipulated in laws

### 6.2 Reasons for Destruction

- Cessation of all conditions in KVKK Arts. 5 and 6
- Expiry of retention period
- Determination, on a data subject's application, that processing conditions are absent
- Withdrawal of explicit consent (only for data based solely on explicit consent)

## 7. TECHNICAL AND ADMINISTRATIVE MEASURES (Erasure Reg. Art. 6/ç)

### 7.1 Technical Measures

- Network and application security
- Encryption (rest + transit)
- Penetration tests (annual)
- Information security incident management (SIEM)
- Authorisation matrix and limited access
- Authorisation control (PAM, MFA)
- Logging
- Data masking (where required)
- Anti-virus, anti-malware, DLP
- Backup and disaster recovery
- Patch management
- Firewall

### 7.2 Administrative Measures

- Personal data inventory
- Policies and procedures
- Employee training (annual + role-based)
- Confidentiality undertakings
- KVKK compliance committee
- KVKK clauses in supplier contracts (DPA)
- Incident Response Plan
- Regular audit
- Internal periodic checks

## 8. DESTRUCTION METHODS (Erasure Reg. Art. 6/d)

### 8.1 Erasure

| Medium | Method |
|--------|--------|
| Servers / software | Record-deletion command, software's erase function, removal of relevant user's access |
| Cloud solutions | Compliance with provider's erase request |
| Paper | Blacking-out, cutting, making unreadable (only if erasure-only) |
| Portable media | Software erase command (consider backups/originals) |

### 8.2 Destruction

| Medium | Method |
|--------|--------|
| Magnetic disk (HDD etc.) | Demagnetisation (degausser); physical shredding |
| SSD / flash memory | Hardware secure-erase (TRIM/secure erase); physical shredding |
| Optical media (CD, DVD) | Physical shredding |
| Paper | Certified paper shredder (cross-cut, P-4 or higher); incineration |
| Cloud systems | Crypto-shredding (key destruction); destruction certificate from provider |
| Backups | End of backup rotation + crypto-shredding |

### 8.3 Anonymisation

Where the purpose of retention persists but identification is no longer required:

| Method | Description |
|--------|-------------|
| Masking | Identifier fields masked (e.g. name → "Customer-1234") |
| Aggregation | Individual data converted into summary statistics |
| Data derivation | Identifier replaced with derived general data (age range instead of age) |
| K-anonymity | Each record matches at least k-1 others |
| L-diversity | K-anonymity + l different values in sensitive field |
| T-closeness | Sensitive field distribution close to general population |
| Noise addition | Small random deviations added to numeric fields |

> A "re-identifiability test" is performed after anonymisation; if risk persists, anonymisation is incomplete. Risk re-evaluated annually.

## 9. RETENTION AND DESTRUCTION PERIODS TABLE (Erasure Reg. Art. 6/e)

| # | Process / Data Category | Retention Period | Legal Basis | Destruction Method |
|---|--------------------------|------------------|-------------|---------------------|
| 1 | Employee personnel file | 10 years after end of employment | Labour Law Art. 75; SSI Art. 86; CO Art. 146 | Erasure + physical destruction |
| 2 | OHSS records (health, accidents) | 15 years | OHSS Law Art. 27 | Erasure + physical destruction |
| 3 | Payroll / wage slips | 10 years | CO Art. 146; SSI | Erasure |
| 4 | Unsuccessful applicant CVs | 6 months (general) / 1 year (talent pool — with explicit consent) | KVKK Art. 4/d; Authority case law | Erasure |
| 5 | Customer contract and invoice | Contract end + 10 years | CO Art. 146; Tax Procedure Law Art. 253 | Erasure |
| 6 | Customer contact data (non-contract) | Until legal basis ceases + 2 years | KVKK Art. 4/d; legitimate interest | Erasure |
| 7 | Customer marketing (with explicit consent) | Until withdrawal / 2 years passive | Explicit consent | Erasure |
| 8 | Call centre voice recordings | 2 years (general); 10 years for financial transactions | Consumer Law; Banking legislation | Destruction |
| 9 | CCTV footage | 30-60 days (area- and risk-based) | Legitimate interest; Authority case law | Automatic overwrite |
| 10 | PDKS (entry-exit) | 5 years | Labour Law; legitimate interest | Erasure |
| 11 | Cookie data | Per cookie lifetime (session / 2 years cap) | Explicit consent / legitimate interest | Automatic erasure |
| 12 | Breach records | At least 5 years | KVKK Art. 12; Erasure Reg. Art. 7/3 (3 years) | Erasure |
| 13 | DSR records | 5 years | KVKK Art. 13; dispute limitation | Erasure |
| 14 | Supplier contracts and contacts | Contract end + 10 years | CO Art. 146 | Erasure + physical destruction |
| 15 | Social media / campaign participation | 1 year post-campaign | Explicit consent / legitimate interest | Erasure |
| 16 | Web server logs | 6 months - 2 years | Internet Law (5651) | Erasure |

> The table is kept in sync with the process inventory. New processes or regulatory changes trigger an update within 7 days.

## 10. PERIODIC DESTRUCTION PERIOD (Erasure Reg. Art. 6/f, Art. 11)

Periodic destruction is performed **at intervals not exceeding 6 months**. Company calendar:

| Period | Date | Owner | Output |
|--------|------|-------|--------|
| Q1 | 15-31 January each year | Process owners + KVKK Officer | Destruction minutes |
| Q3 | 15-31 July each year | Process owners + KVKK Officer | Destruction minutes |

### 10.1 Periodic Destruction Process

1. The process owner identifies data with expired retention.
2. Reviewed jointly with the KVKK Officer; exception cases (ongoing dispute, statutory retention) are reported.
3. Destruction performed (with appropriate method).
4. Minutes drafted: date, medium, category, volume, method, responsible, signatures.
5. Minutes retained at least 3 years (5 years recommended for audit readiness).
6. Reflected in the KVKK Officer's quarterly report.

### 10.2 On-Request Destruction (Art. 12)

When the data subject applies:
- Resolved within **30 days** at the latest.
- Refused with reasons if KVKK Arts. 5-6 conditions persist.
- Where destruction occurs, third parties to whom the data were transferred are notified.
- The result is communicated to the data subject in writing or electronically.

## 11. POLICY UPDATES (Erasure Reg. Art. 6/g)

| Trigger | Time |
|---------|------|
| Regulatory change | 30 days |
| Company organisational change | 60 days |
| New process / new data category | 30 days |
| Annual full revision | November each year |

Update process:
1. KVKK Officer drafts the update.
2. Legal Counsel reviews.
3. KVKK Committee approves.
4. The Audit Committee of the Board is informed.
5. Stakeholders notified.
6. Version increments; old version archived.

## 12. RESPONSIBILITIES

| Role | Responsibility |
|------|----------------|
| KVKK Officer | Policy management, periodic destruction coordination, reporting |
| Process Owners | Apply retention periods in their processes, perform periodic destruction |
| Legal Counsel | Verify legal basis of retention periods |
| IT | Apply technical destruction methods, log preservation |
| Internal Audit | Independent audit of policy compliance |

## 13. ANNEXES

- Annex 1: Detailed Retention Periods Table (mapped to inventory)
- Annex 2: Destruction Minutes Template
- Annex 3: Destruction Methods Technical Instruction

## 14. ENTRY INTO FORCE

This Policy entered into force by Board of Directors decision dated [DATE] No. [NO].

| Approval | Name | Date | Signature |
|----------|------|------|-----------|
| Drafter | KVKK Officer | | |
| Legal sign-off | Legal Counsel | | |
| Approver | KVKK Committee | | |
| Approver | Board of Directors | | |

Version: [VERSION] | Effective: [DATE]

---

## ANNEX-2: DESTRUCTION MINUTES TEMPLATE

```
DESTRUCTION MINUTES

Minute No: [YEAR]-[QUARTER]-[SEQ]
Date: [DATE]
Time: [TIME]
Location: [LOCATION]

Type: [Periodic / On-Request / Other]
Scope:
- Process: [PROCESS]
- Data category: [CATEGORY]
- Data subject group: [GROUP]
- Volume (records / files): [VOLUME]
- Medium destroyed: [MEDIUM]

Method: [Erasure / Destruction / Anonymisation]
Method detail: [TECHNICAL — e.g. crypto-shredding, physical shredding]
Third-party service: [IF ANY — certificate attached]

Legal Basis (retention expired):
[POLICY TABLE ROW REFERENCE]

Responsible Personnel:
- Process Owner: [NAME] ____________________ (signature)
- KVKK Officer: [NAME] _________________ (signature)
- IT Responsible (if any): [NAME] ______________ (signature)

Approval:
- Manager: [NAME] ___________________ (signature)

Retention: 5 years (audit readiness)
```

## Related Documents

- [../12-mevzuat-arsiv/imha-yonetmeligi.md](../12-mevzuat-arsiv/imha-yonetmeligi.md)
- [../04-veri-saklama-ve-imha/](../04-veri-saklama-ve-imha/)
- [kvki-envanter.csv](kvki-envanter.csv)

---

## Türkçe

# [ŞİRKET TAM TİCARİ UNVANI] — KİŞİSEL VERİ SAKLAMA VE İMHA POLİTİKASI

## 1. AMAÇ

İşbu Politika, [ŞİRKET TAM TİCARİ UNVANI] ("Şirket") tarafından veri sorumlusu sıfatıyla işlenen kişisel verilerin 6698 sayılı Kişisel Verilerin Korunması Kanunu ("KVKK"), Kişisel Verilerin Silinmesi, Yok Edilmesi veya Anonim Hale Getirilmesi Hakkında Yönetmelik ("İmha Yönetmeliği") ve ilgili mevzuat çerçevesinde silinmesi, yok edilmesi veya anonim hale getirilmesine ilişkin usul ve esasları düzenler.

## 2. KAPSAM

Bu Politika, Şirket'in tüm birimlerinde, tüm fiziksel ve elektronik ortamlarda işlenen tüm kişisel veriler ve bu verileri işleyen tüm çalışanlar, danışmanlar, stajyerler, tedarikçiler ve diğer iş ortakları hakkında uygulanır.

## 3. DAYANAK

| Mevzuat | Madde |
|---------|-------|
| KVKK | m.4/d (saklama süresi ilkesi); m.7 (silme/yok etme/anonim hale getirme); m.16 (Sicil ve politika hazırlama yükümlülüğü) |
| İmha Yönetmeliği | m.5, m.6 (politika asgari unsurları); m.7-10 (imha yöntemleri); m.11 (periyodik imha); m.12 (talep üzerine imha) |
| Aydınlatma Tebliği | m.4 (saklama süresinin aydınlatma metninde belirtilmesi) |
| VERBİS Yönetmeliği | m.9/f (saklama süresinin VERBİS bildiriminde yer alması) |

## 4. TANIMLAR

| Terim | Tanım |
|-------|-------|
| Kişisel Veri | Kimliği belirli veya belirlenebilir gerçek kişiye ilişkin her türlü bilgi |
| Özel Nitelikli Kişisel Veri | KVKK m.6/1'de sayılan veriler |
| Saklama Süresi | Kişisel verinin işleme amacı doğrultusunda muhafaza edilmesi gereken süre |
| İmha | Silme, yok etme veya anonim hale getirme |
| Silme | İlgili kullanıcılar için hiçbir şekilde erişilemez ve tekrar kullanılamaz hale getirme |
| Yok Etme | Hiç kimse tarafından, hiçbir şekilde erişilemez, geri getirilemez ve tekrar kullanılamaz hale getirme |
| Anonim Hale Getirme | Verinin başka verilerle eşleştirilse dahi kimliği belirli/belirlenebilir gerçek kişiyle ilişkilendirilemeyecek hale getirme |
| Periyodik İmha | Kanun'da öngörülen şartların ortadan kalkması durumunda kişisel verilerin tekrarlayan ve resen yapılan imhası |
| İlgili Kullanıcı | Verinin saklanmasından, işlenmesinden veya teknik bakımından sorumlu departman/personel |

## 5. KAYIT ORTAMLARI (İmha Yön. m.6/b)

Şirket'te kişisel veri aşağıdaki kayıt ortamlarında işlenmektedir:

### 5.1 Elektronik Ortamlar

| Ortam | Açıklama |
|-------|----------|
| Sunucular (alan adı sunucusu, web sunucusu, e-posta sunucusu, dosya sunucusu, uygulama sunucusu vb.) | Şirket merkezi veri merkezi ve felaket kurtarma merkezi |
| Yazılımlar (SAP/ERP, CRM, İK, finans, bordro, çağrı merkezi, e-ticaret platformu) | İş süreçleri için kullanılan kurumsal yazılımlar |
| Bilgi güvenliği cihazları (güvenlik duvarı, izinsiz giriş tespit sistemi, antivirüs, log sunucusu) | Güvenlik ve izleme |
| Kişisel bilgisayarlar (masaüstü, dizüstü, tablet) | Kullanıcı uçları |
| Mobil cihazlar (telefon) | İş cihazları (MDM kapsamında) |
| Optik diskler (CD, DVD), manyetik diskler (sabit disk, harici disk), USB | Yedekleme ve transfer ortamları |
| Yazıcı, tarayıcı, fotokopi makinesi | Disk içeren çevre birimleri |
| Bulut sistemler (yetkilendirilmiş tedarikçiler) | DPA çerçevesinde |

### 5.2 Fiziksel Ortamlar

| Ortam | Açıklama |
|-------|----------|
| Kağıt | İş sözleşmesi, özlük dosyası, fatura, dilekçe |
| Manuel veri kayıt sistemleri | Anket formları, başvuru formları |
| Yazılı, basılı, görsel ortamlar | Eğitim materyalleri, şirket içi yayınlar |

## 6. SAKLAMA VE İMHAYI GEREKTİREN HUKUKİ, TEKNİK VE DİĞER NEDENLER (İmha Yön. m.6/c)

### 6.1 Saklamayı Gerektiren Nedenler

- KVKK ve ilgili mevzuat
- İlgili sair kanunlar (İş Kanunu, SGK, ISG, VUK, TBK, TTK, Tüketici Kanunu, Bankacılık Kanunu, Finansal Kiralama Kanunu, vb.)
- Sözleşme yükümlülükleri
- Hakların tesisi, kullanılması veya korunması
- Meşru menfaatler için gerekli olma (uyuşmazlık ihtimali, dolandırıcılık önleme, hizmet kalitesi)
- Kanunlarda açıkça öngörülen yükümlülükler

### 6.2 İmhayı Gerektiren Nedenler

- KVKK m.5 ve m.6'daki işleme şartlarının tamamen ortadan kalkması
- Saklama süresinin dolması
- İlgili kişinin başvurusu üzerine işleme şartlarının olmadığının tespiti
- Açık rızanın geri alınması (yalnızca açık rıza dayanağıyla işlenen verilerde)

## 7. ALINAN TEKNİK VE İDARİ TEDBİRLER (İmha Yön. m.6/ç)

### 7.1 Teknik Tedbirler

- Ağ güvenliği ve uygulama güvenliği
- Şifreleme (rest + transit)
- Sızma testleri (yıllık)
- Bilgi güvenliği olay yönetimi (SIEM)
- Yetki matrisi ve sınırlı erişim
- Yetki kontrol (PAM, MFA)
- Log kayıtları
- Veri maskeleme (gerekli ortamlarda)
- Anti-virüs, anti-malware, DLP
- Yedekleme ve felaket kurtarma
- Yama yönetimi
- Güvenlik duvarı

### 7.2 İdari Tedbirler

- Kişisel veri envanteri
- Politika ve prosedürler
- Çalışan eğitimleri (yıllık + rol bazlı)
- Gizlilik taahhütnameleri
- KVKK uyum komitesi
- Tedarikçi sözleşmelerinde KVKK hükümleri (DPA)
- İhlal Müdahale Planı
- Düzenli denetim
- Kurum içi periyodik kontroller

## 8. İMHA YÖNTEMLERİ (İmha Yön. m.6/d)

### 8.1 Silme

| Kayıt Ortamı | Yöntem |
|--------------|--------|
| Sunucular / yazılımlar | Sicil silme komutu, yazılımın silme fonksiyonu, ilgili kullanıcının erişiminin kaldırılması |
| Bulut çözümleri | Bulut sağlayıcısının silme talebine uyma |
| Kağıt ortamı | Kara kalemle karartma, kesme, üzerine yazılamaz hale getirme (yalnızca silme amaçlıysa) |
| Taşınabilir medya | Yazılım silme komutu (yedek/orijinal kopyalar dikkate alınır) |

### 8.2 Yok Etme

| Kayıt Ortamı | Yöntem |
|--------------|--------|
| Manyetik disk (sabit disk vb.) | Demağnetizasyon (degausser); fiziksel parçalama |
| SSD / flash bellek | Donanımsal silme komutu (TRIM/secure erase); fiziksel parçalama |
| Optik medya (CD, DVD) | Fiziksel parçalama |
| Kağıt | Sertifikalı kağıt imha cihazı (cross-cut, P-4 ve üzeri); yakma |
| Bulut sistemler | Crypto-shredding (anahtar imhası); sağlayıcı tarafından yok etme sertifikası |
| Yedekler | Yedek rotasyonu sona erdirme + crypto-shredding |

### 8.3 Anonim Hale Getirme

Veri analitiği veya saklama amacının devam etmesinin gerektiği ancak kişiyle bağlantı kurulmasının gerekli olmadığı durumlarda:

| Yöntem | Açıklama |
|--------|----------|
| Maskeleme | Tanımlayıcı alanların maskelenmesi (örn. ad-soyad → "Müşteri-1234") |
| Toplama (aggregation) | Bireysel verilerin toplanmış istatistiklere dönüştürülmesi |
| Veri türetme | Tanımlayıcı veri yerine türetilmiş genel veri (yaş yerine yaş aralığı) |
| K-anonimlik | Her kayıt en az k-1 başka kayıtla eşleşir |
| L-çeşitlilik | K-anonimlik + duyarlı alanda l farklı değer |
| T-yakınlık | Duyarlı alan dağılımının genel popülasyona yakın olması |
| Gürültü ekleme | Sayısal alanlara rastgele küçük sapma ekleme |

> Anonim hale getirme sonrası **yeniden tanımlanma riski testi** yapılır; risk varsa anonimleştirme tamamlanmamış sayılır. Risk yıllık yeniden değerlendirilir.

## 9. SAKLAMA VE İMHA SÜRELERİ TABLOSU (İmha Yön. m.6/e)

| No | Süreç / Veri Kategorisi | Saklama Süresi | Hukuki Dayanak | İmha Yöntemi |
|----|-------------------------|----------------|-----------------|---------------|
| 1 | Çalışan özlük dosyası | İş ilişkisi sona erdikten sonra 10 yıl | İş Kanunu m.75; SGK Kanunu m.86; TBK m.146 | Silme + fiziksel imha |
| 2 | İSG kayıtları (sağlık, kazalar) | 15 yıl | İSG Kanunu m.27 | Silme + fiziksel imha |
| 3 | Bordro / ücret bordroları | 10 yıl | TBK m.146; SGK | Silme |
| 4 | İşe alınmayan aday CV'leri | 6 ay (genel) / 1 yıl (yetkinlik havuzu — açık rıza ile) | KVKK m.4/d; Kurul içtihadı | Silme |
| 5 | Müşteri sözleşmesi ve fatura | Sözleşme bitiş + 10 yıl | TBK m.146; VUK m.253 | Silme |
| 6 | Müşteri iletişim verisi (sözleşme dışı) | Hukuki sebep sona erene + 2 yıl | KVKK m.4/d; meşru menfaat | Silme |
| 7 | Müşteri pazarlama (açık rıza ile) | Geri alınana kadar / 2 yıl pasif olarak | Açık rıza | Silme |
| 8 | Çağrı merkezi ses kayıtları | 2 yıl (genel); finansal işlem 10 yıl | TKHK; Bankacılık mevzuatı | Yok etme |
| 9 | CCTV görüntüleri | 30-60 gün (alan ve risk bazlı) | Meşru menfaat; Kurul içtihadı | Otomatik üzerine yazma |
| 10 | PDKS (giriş-çıkış) | 5 yıl | İş Kanunu; meşru menfaat | Silme |
| 11 | Çerez verileri | Çerez ömrüne göre (oturum / 2 yıl üst sınır) | Açık rıza / meşru menfaat | Otomatik silme |
| 12 | İhlal kayıtları | Asgari 5 yıl | KVKK m.12; İmha Yön. m.7/3 (3 yıl) | Silme |
| 13 | Başvuru kayıtları | 5 yıl | KVKK m.13; uyuşmazlık zamanaşımı | Silme |
| 14 | Tedarikçi sözleşmeleri ve iletişim | Sözleşme bitiş + 10 yıl | TBK m.146 | Silme + fiziksel imha |
| 15 | Sosyal medya / kampanya katılım | Kampanya sonrası 1 yıl | Açık rıza / meşru menfaat | Silme |
| 16 | Web sitesi sunucu logları | 6 ay - 2 yıl | İnternet Mevzuatı / 5651 K. | Silme |

> Tablo, süreç envanteri ile senkron tutulur. Yeni süreç eklendiğinde veya mevzuat değişikliği halinde tablo 7 gün içinde güncellenir.

## 10. PERİYODİK İMHA SÜRESİ (İmha Yön. m.6/f, m.11)

Periyodik imha **6 ayı geçmeyecek aralıklarla** gerçekleştirilir. Şirket'te periyodik imha takvimi:

| Dönem | Tarih | Sahip | Çıktı |
|-------|-------|-------|-------|
| Q1 | Her yıl Ocak ayının 15-31'i | Süreç sahipleri + KVKK Sor. | İmha tutanağı |
| Q3 | Her yıl Temmuz ayının 15-31'i | Süreç sahipleri + KVKK Sor. | İmha tutanağı |

### 10.1 Periyodik İmha Süreci

1. Süreç sahibi, saklama süresi dolan verileri tespit eder.
2. KVKK Sorumlusu ile birlikte gözden geçirir; istisna durumlar (devam eden uyuşmazlık, yasal saklama) raporlanır.
3. İmha gerçekleştirilir (uygun yöntemle).
4. İmha tutanağı düzenlenir: tarih, kayıt ortamı, veri kategorisi, hacim, yöntem, sorumlu, imza.
5. Tutanak en az 3 yıl saklanır (denetim hazırlığı için 5 yıl önerilir).
6. KVKK Sorumlusu çeyreklik raporunda yer alır.

### 10.2 Talep Üzerine İmha (m.12)

İlgili kişi başvurduğunda:
- Talep en geç **30 gün** içinde sonuçlandırılır.
- KVKK m.5-6 işleme şartları devam ediyorsa gerekçeli reddedilir.
- İmha gerçekleşirse aktarılan üçüncü kişilere bildirilir.
- Sonuç ilgili kişiye yazılı veya elektronik olarak bildirilir.

## 11. POLİTİKANIN GÜNCELLENMESİ (İmha Yön. m.6/g)

| Tetikleyici | Süre |
|-------------|------|
| Mevzuat değişikliği | 30 gün |
| Şirket organizasyon değişikliği | 60 gün |
| Yeni süreç / yeni veri kategorisi | 30 gün |
| Yıllık tam revizyon | Her yıl Kasım |

Güncelleme süreci:
1. KVKK Sorumlusu güncelleme taslağı hazırlar.
2. Hukuk Müşavirliği inceler.
3. KVKK Komitesi onaylar.
4. Yönetim Kurulu Denetim Komitesi bilgilendirilir.
5. İlgili paydaşlara duyurulur.
6. Versiyon numarası artırılır; eski sürüm arşive.

## 12. SORUMLULAR

| Rol | Sorumluluk |
|-----|------------|
| KVKK Sorumlusu | Politikanın yönetilmesi, periyodik imha koordinasyonu, raporlama |
| Süreç Sahipleri | Kendi süreçlerinde saklama sürelerinin uygulanması, periyodik imha gerçekleştirme |
| Hukuk Müşavirliği | Saklama sürelerinin hukuki dayanağının doğrulanması |
| Bilgi Teknolojileri | Teknik imha yöntemlerinin uygulanması, log koruma |
| İç Denetim | Politika uyumunun bağımsız denetimi |

## 13. EKLER

- Ek-1: Saklama Süreleri Detay Tablosu (envanterle eşleşik)
- Ek-2: İmha Tutanağı Şablonu
- Ek-3: İmha Yöntemleri Teknik Talimatı

## 14. YÜRÜRLÜK

İşbu Politika, Yönetim Kurulu'nun [TARİH] tarihli [SAYI] sayılı kararı ile yürürlüğe girmiştir.

| Onay | Ad-Soyad | Tarih | İmza |
|------|----------|-------|------|
| Hazırlayan | KVKK Sorumlusu | | |
| Hukuk Onayı | Hukuk Müşaviri | | |
| Onaylayan | KVKK Komitesi | | |
| Onaylayan | Yönetim Kurulu | | |

Versiyon: [SÜRÜM] | Yürürlük: [TARİH]

---

## EK-2: İMHA TUTANAĞI ŞABLONU

```
İMHA TUTANAĞI

Tutanak No: [YIL]-[ÇEYREK]-[SIRA]
Tarih: [TARİH]
Saat: [SAAT]
Yer: [LOKASYON]

İmha Türü: [Periyodik / Talep Üzerine / Diğer]
İmha Kapsamı:
- Süreç: [SÜREÇ ADI]
- Veri kategorisi: [KATEGORİ]
- Veri konusu kişi grubu: [GRUP]
- Hacim (kayıt sayısı / dosya sayısı): [HACİM]
- İmha edilen kayıt ortamı: [ORTAM]

İmha Yöntemi: [Silme / Yok Etme / Anonim Hale Getirme]
Yöntem Detayı: [TEKNİK YÖNTEM — örn. crypto-shredding, fiziksel parçalama]
Üçüncü Taraf Hizmeti: [VARSA — sertifika ekte]

Hukuki Dayanak (saklama süresi dolmuştur):
[POLİTİKA TABLOSU SATIR REFERANSI]

Sorumlu Personel:
- Süreç Sahibi: [AD-SOYAD] ____________________ (imza)
- KVKK Sorumlusu: [AD-SOYAD] _________________ (imza)
- BT Sorumlu (varsa): [AD-SOYAD] ______________ (imza)

Onay:
- Yönetici: [AD-SOYAD] ___________________ (imza)

Saklama: 5 yıl (denetim hazırlığı)
```

## İlgili Dokümanlar

- [../12-mevzuat-arsiv/imha-yonetmeligi.md](../12-mevzuat-arsiv/imha-yonetmeligi.md)
- [../04-veri-saklama-ve-imha/](../04-veri-saklama-ve-imha/)
- [kvki-envanter.csv](kvki-envanter.csv)
