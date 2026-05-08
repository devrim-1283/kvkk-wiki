---
title:
  en: "Retention & Erasure Policy"
  tr: "Saklama ve Silme Politikası"
section: "04-retention-erasure"
document_type: "policy_template"
regulation: "GDPR (EU 2016/679)"
articles:
  - "Art. 5(1)(e) — Storage limitation principle"
  - "Art. 5(2) — Accountability"
  - "Art. 17 — Right to erasure"
  - "Art. 25 — Data protection by design and default"
  - "Art. 30 — Records of processing activities"
  - "Recital 39 — Storage limitation"
  - "Recital 65 — Right to erasure"
related_standards:
  - "ISO/IEC 27001:2022 (A.5.33 Protection of records, A.8.10 Information deletion)"
  - "ISO/IEC 27701:2019 (PIMS)"
  - "NIST SP 800-88 Rev. 1 — Guidelines for Media Sanitization"
version: "1.0"
language: "en, tr"
last_reviewed: "2025-05-01"
review_cycle: "annual"
owner: "Data Protection Officer"
approver: "Executive Committee"
status: "approved"
classification: "internal"
---

## English

# Retention & Erasure Policy

## 1. Purpose

This Policy establishes the rules under which **[ORGANISATION NAME]** ("the Controller") retains, reviews, and securely destroys personal data, in accordance with Article 5(1)(e) of Regulation (EU) 2016/679 (GDPR) — the **storage limitation principle**.

The Controller is accountable (Article 5(2)) for demonstrating that personal data is kept "in a form which permits identification of data subjects for **no longer than is necessary**" for the purposes for which it was collected.

## 2. Scope

This Policy applies to:

- All personal data processed by the Controller in any form (electronic, paper, audio, video, biometric).
- All employees, contractors, agency staff, interns, and third parties acting on behalf of the Controller.
- All processors and sub-processors engaged by the Controller, via flow-down obligations in the Article 28 contract.
- All systems, applications, file shares, mailboxes, backups, archives, log stores, analytics warehouses, and physical filing locations under Controller control.

This Policy does **not** apply to:
- Anonymous data that meets the irreversibility threshold of Recital 26 GDPR.
- Aggregated statistics from which no individual can be re-identified.

## 3. Policy statements

### 3.1 Storage limitation

Personal data shall be retained **only for as long as necessary** to fulfil the purpose for which it was collected, plus any additional period mandated by law or required to defend legal claims.

### 3.2 Lawful basis for retention

Each retention period shall be supported by **one or more** of:

| Lawful basis for retention | Example |
|---|---|
| Performance of contract (Art. 6(1)(b)) | Order history during active customer relationship. |
| Legal obligation (Art. 6(1)(c)) | Tax/accounting records under member-state law. |
| Legal claims defence (Art. 17(3)(e)) | Records retained until expiry of statute of limitations. |
| Legitimate interest (Art. 6(1)(f)) | Limited security log retention; balanced against data subject rights. |
| Public interest archiving (Art. 89) | Cultural, historical, scientific, or statistical archive. |
| Consent (Art. 6(1)(a)) | Marketing list retained until consent is withdrawn. |

A retention period without a documented lawful basis is **non-compliant** and shall be reduced.

### 3.3 Documented retention schedule

The Retention Schedule (`retention-schedule.md`) is the authoritative list of retention periods. It shall:

- Cover every category of personal data identified in the Record of Processing Activities (Art. 30).
- Specify the lawful basis, owner, retention period, and destruction method per category.
- Reference applicable EU member-state minimum periods.
- Be reviewed annually and after any material change in law, processing activity, or system architecture.

### 3.4 Privacy by design and default

New systems and processing activities shall be designed with retention in mind from inception:

- Each personal data field shall have an associated retention period.
- Automated deletion (TTL, lifecycle rules) shall be preferred over manual deletion where feasible.
- Pseudonymisation and anonymisation shall be considered as alternatives to outright deletion where the analytical or archival purpose can still be served.

### 3.5 Erasure on request

Data subjects have the right to obtain erasure under Article 17 on the grounds set out therein. The Controller shall respond to valid erasure requests within **one month** (extendable by two further months for complex cases under Art. 12(3)). The procedure is set out in `right-to-erasure.md`.

### 3.6 Notification to recipients

Where personal data has been disclosed to recipients (other controllers, processors, sub-processors, joint controllers), the Controller shall notify each recipient of any rectification, erasure, or restriction (Art. 19) — unless this proves impossible or involves disproportionate effort.

### 3.7 Backups

Personal data in backups shall be addressed under the **backup erasure strategy** in `erasure-methods.md` §6. Where immediate physical deletion from backup is not feasible (e.g., immutable backups, ransomware-protection retention, regulatory archive requirements), the Controller shall:

- Apply technical and organisational restrictions preventing further processing of the backup-resident data.
- Crypto-shred the data on the next routine backup-cycle expiry.
- Document the residual retention and the compensating controls.

### 3.8 Processors

Article 28 contracts shall require that processors and sub-processors:

- Apply the same retention periods or shorter.
- Delete or return personal data at the end of the service (Art. 28(3)(g)).
- Provide a written **certificate of destruction** referencing categories, volumes, methods, and dates.
- Propagate erasure requests to their own sub-processors.

### 3.9 Records of destruction

Every destruction event shall be recorded using the template in `destruction-record.md`. The destruction record shall include: date, categories, volumes, method, operator, witness, location, system identifiers, and verification evidence. Destruction records shall be retained for the audit period (minimum **6 years**, extended where local law requires).

### 3.10 Exceptions

A retention period may be extended only where:

- A specific legal obligation requires it.
- Active or reasonably anticipated litigation, regulatory investigation, or audit imposes a **legal hold**.
- The data subject has given fresh, specific, informed consent.

All exceptions shall be:
- Approved by the DPO.
- Documented with reason, scope, expiry, and review date.
- Logged in the Exceptions Register.

## 4. Roles and responsibilities

### 4.1 Executive Committee
- Approves this Policy.
- Approves resourcing for compliance.

### 4.2 Data Protection Officer (DPO)
- Owns this Policy.
- Approves the Retention Schedule.
- Approves exceptions and legal holds.
- Audits compliance at least annually.
- Reports to the Executive Committee.

### 4.3 Data Owners (per business function)
- Define retention periods for data in their function.
- Maintain accuracy of the Retention Schedule for their categories.
- Trigger destruction events.
- Sign destruction records.

### 4.4 IT Operations
- Implement automated deletion controls.
- Execute deletion in production, backup, and archive systems.
- Provide technical evidence of deletion.

### 4.5 Information Security
- Verifies destruction effectiveness (sampling, key destruction confirmation).
- Owns the cryptographic key lifecycle for crypto-shredding.
- Reports anomalies to the DPO.

### 4.6 Legal
- Issues and lifts legal holds.
- Advises on member-state minimum retention periods.
- Reviews exceptions impacting litigation strategy.

### 4.7 Internal Audit
- Tests compliance with this Policy at least annually.
- Reports findings to Audit Committee and DPO.

### 4.8 All employees
- Comply with this Policy.
- Do not create informal copies (local drives, personal email, printouts) outside approved systems.
- Report suspected non-compliance to the DPO.

## 5. Periodic review

### 5.1 Policy review
- The DPO reviews this Policy at least annually.
- Material changes in law (e.g., a new EU regulation, member-state implementing act, or CJEU ruling such as Schrems II derivatives) trigger out-of-cycle review.

### 5.2 Schedule review
- The Retention Schedule is reviewed annually as a whole.
- Each Data Owner reviews their categories at least once per calendar year and signs the review.

### 5.3 Destruction review
- The DPO conducts quarterly sampling of destruction records.
- Internal Audit performs an annual audit (sampling production systems, backups, paper archives, processor confirmations).

## 6. Training and awareness

- All staff complete annual GDPR training including retention obligations.
- Data Owners receive specific training on the Retention Schedule and exception management.
- New systems integration projects include a retention-design review by the DPO.

## 7. Non-compliance

Failure to comply with this Policy may result in:

- Disciplinary action up to and including termination.
- Civil and criminal liability under GDPR and member-state law.
- Reporting to the supervisory authority where the failure constitutes a personal data breach (Art. 33).

## 8. Definitions

| Term | Meaning |
|---|---|
| Personal data | Any information relating to an identified or identifiable natural person (Art. 4(1)). |
| Processing | Any operation performed on personal data (Art. 4(2)). |
| Retention period | The maximum period for which a category of personal data may be retained. |
| Erasure | The act of rendering personal data permanently inaccessible and unrecoverable. |
| Anonymisation | Irreversible removal of identifiability such that the data is no longer personal data (Recital 26). |
| Pseudonymisation | Processing in such a way that personal data can no longer be attributed to a specific data subject without additional information (Art. 4(5)). |
| Crypto-shredding | Destruction of the cryptographic key, rendering encrypted data unrecoverable. |
| Legal hold | Suspension of routine destruction due to litigation, investigation, or audit. |

## 9. Document control

| Field | Value |
|---|---|
| Version | 1.0 |
| Effective date | [DATE] |
| Next review | [DATE + 1 YEAR] |
| Owner | DPO |
| Approver | Executive Committee |
| Distribution | All staff, processors |

---

## Türkçe

# Saklama ve Silme Politikası

## 1. Amaç

Bu Politika, **[KURULUŞ ADI]**'nın ("Kontrolör") (AB) 2016/679 Sayılı Tüzük (GDPR) Madde 5(1)(e) — **saklama sınırlaması ilkesi** uyarınca kişisel verileri sakladığı, gözden geçirdiği ve güvenli biçimde imha ettiği kuralları belirler.

Kontrolör, kişisel verilerin "toplandığı amaçlar için **gerekli olandan daha uzun süre** ilgili kişilerin tanımlanmasına olanak verecek bir biçimde" tutulmadığını kanıtlamakla yükümlüdür (Madde 5(2)).

## 2. Kapsam

Bu Politika şunları kapsar:

- Kontrolör tarafından her biçimde işlenen tüm kişisel veriler (elektronik, kâğıt, ses, video, biyometrik).
- Tüm çalışanlar, yükleniciler, ajans personeli, stajyerler ve Kontrolör adına hareket eden üçüncü taraflar.
- Madde 28 sözleşmesindeki yansıma yükümlülükleri yoluyla Kontrolör tarafından görevlendirilen tüm işleyenler ve alt-işleyenler.
- Kontrolör kontrolü altındaki tüm sistemler, uygulamalar, dosya paylaşımları, posta kutuları, yedekler, arşivler, log depoları, analitik veri ambarları ve fiziksel dosyalama konumları.

Bu Politika **şunlara uygulanmaz**:
- Resital 26 GDPR'ın geri çevrilemezlik eşiğini karşılayan anonim veriler.
- Hiçbir bireyin yeniden tanımlanamayacağı toplu istatistikler.

## 3. Politika hükümleri

### 3.1 Saklama sınırlaması

Kişisel veriler **yalnızca toplandığı amacı yerine getirmek için gerekli olduğu sürece** ve hukuken zorunlu kılınan veya hukuki taleplere karşı savunmak için gereken ek süre boyunca saklanır.

### 3.2 Saklamanın hukuki dayanağı

Her saklama süresi şunlardan **bir veya daha fazlasıyla** desteklenmelidir:

| Saklama hukuki dayanağı | Örnek |
|---|---|
| Sözleşmenin ifası (Md. 6(1)(b)) | Aktif müşteri ilişkisi sırasında sipariş geçmişi. |
| Hukuki yükümlülük (Md. 6(1)(c)) | Üye devlet hukuku kapsamında vergi/muhasebe kayıtları. |
| Hukuki talepler savunması (Md. 17(3)(e)) | Zamanaşımı süresi dolana kadar saklanan kayıtlar. |
| Meşru menfaat (Md. 6(1)(f)) | Sınırlı güvenlik log saklaması; ilgili kişi haklarıyla dengelenmiş. |
| Kamu yararı arşivlemesi (Md. 89) | Kültürel, tarihsel, bilimsel veya istatistiksel arşiv. |
| Rıza (Md. 6(1)(a)) | Rıza geri çekilene kadar saklanan pazarlama listesi. |

Belgelenmiş hukuki dayanağı olmayan bir saklama süresi **uyumsuzdur** ve azaltılır.

### 3.3 Belgelenmiş saklama çizelgesi

Saklama Çizelgesi (`retention-schedule.md`) saklama sürelerinin yetkili listesidir. Şunları yapar:

- İşleme Faaliyetleri Sicilinde (Md. 30) tanımlanan her kişisel veri kategorisini kapsar.
- Kategori başına hukuki dayanağı, sahibi, saklama süresini ve imha yöntemini belirtir.
- Geçerli AB üye devleti minimum sürelerine atıfta bulunur.
- Yıllık olarak ve hukuk, işleme faaliyeti veya sistem mimarisindeki herhangi bir maddi değişiklikten sonra gözden geçirilir.

### 3.4 Tasarımdan gizlilik ve varsayılan

Yeni sistemler ve işleme faaliyetleri başlangıçtan itibaren saklama göz önünde bulundurularak tasarlanır:

- Her kişisel veri alanının ilişkili bir saklama süresi olmalıdır.
- Otomatik silme (TTL, yaşam döngüsü kuralları) uygun olduğunda manuel silmeye tercih edilir.
- Takma adlandırma ve anonimleştirme, analitik veya arşiv amacı hâlâ sağlanabildiğinde tam silmeye alternatif olarak değerlendirilir.

### 3.5 Talep üzerine silme

İlgili kişiler, içinde belirtilen gerekçelerle Madde 17 kapsamında silme elde etme hakkına sahiptir. Kontrolör, geçerli silme taleplerine **bir ay** içinde yanıt verir (Md. 12(3) kapsamında karmaşık vakalar için iki ay daha uzatılabilir). Prosedür `right-to-erasure.md` dosyasında belirtilmiştir.

### 3.6 Alıcılara bildirim

Kişisel veriler alıcılara (diğer kontrolörlere, işleyenlere, alt-işleyenlere, ortak kontrolörlere) açıklanmışsa, Kontrolör herhangi bir düzeltme, silme veya kısıtlama hakkında her alıcıya bildirimde bulunur (Md. 19) — bunun imkânsız olduğu veya orantısız çaba içerdiği durumlar hariç.

### 3.7 Yedekler

Yedeklerdeki kişisel veriler, `erasure-methods.md` §6'daki **yedek silme stratejisi** kapsamında ele alınır. Yedekten anında fiziksel silme yapılabilir olmadığında (örn. değişmez yedekler, fidye yazılım koruma saklaması, düzenleyici arşiv gereksinimleri) Kontrolör:

- Yedekte yerleşik verilerin daha fazla işlenmesini önleyen teknik ve organizasyonel kısıtlamalar uygular.
- Bir sonraki rutin yedek-döngü süresinin sonunda veriyi kripto-parçalar.
- Artık saklamayı ve telafi edici kontrolleri belgeler.

### 3.8 İşleyenler

Madde 28 sözleşmeleri, işleyenlerin ve alt-işleyenlerin şunları yapmasını gerektirir:

- Aynı veya daha kısa saklama sürelerini uygular.
- Hizmet sona erdiğinde kişisel verileri siler veya iade eder (Md. 28(3)(g)).
- Kategorilere, hacimlere, yöntemlere ve tarihlere atıfta bulunan yazılı bir **imha sertifikası** sağlar.
- Silme taleplerini kendi alt-işleyenlerine yayar.

### 3.9 İmha kayıtları

Her imha olayı `destruction-record.md` dosyasındaki şablon kullanılarak kaydedilir. İmha kaydı şunları içerir: tarih, kategoriler, hacimler, yöntem, operatör, tanık, konum, sistem tanımlayıcıları ve doğrulama kanıtı. İmha kayıtları denetim süresi boyunca saklanır (yerel hukukun gerektirdiği yerlerde uzatılarak minimum **6 yıl**).

### 3.10 İstisnalar

Bir saklama süresi yalnızca şu durumlarda uzatılabilir:

- Belirli bir hukuki yükümlülük gerektiriyor.
- Aktif veya makul olarak öngörülen dava, düzenleyici soruşturma veya denetim **hukuki bekletme** uyguluyor.
- İlgili kişi yeni, belirli, bilgilendirilmiş rıza vermişse.

Tüm istisnalar:
- DPO tarafından onaylanır.
- Sebep, kapsam, sona erme ve inceleme tarihi ile belgelenir.
- İstisnalar Sicili'ne kaydedilir.

## 4. Roller ve sorumluluklar

### 4.1 Yönetim Komitesi
- Bu Politikayı onaylar.
- Uyumluluk için kaynak tahsisini onaylar.

### 4.2 Veri Koruma Görevlisi (DPO)
- Bu Politikanın sahibidir.
- Saklama Çizelgesini onaylar.
- İstisnaları ve hukuki bekletmeleri onaylar.
- En az yılda bir uyumluluğu denetler.
- Yönetim Komitesine raporlar.

### 4.3 Veri Sahipleri (iş işlevi başına)
- İşlevlerindeki veriler için saklama sürelerini tanımlar.
- Kategorileri için Saklama Çizelgesinin doğruluğunu korur.
- İmha olaylarını tetikler.
- İmha kayıtlarını imzalar.

### 4.4 BT Operasyonları
- Otomatik silme kontrolleri uygular.
- Üretim, yedek ve arşiv sistemlerinde silmeyi gerçekleştirir.
- Silmenin teknik kanıtını sağlar.

### 4.5 Bilgi Güvenliği
- İmha etkinliğini doğrular (örnekleme, anahtar imhasının doğrulanması).
- Kripto-parçalama için kriptografik anahtar yaşam döngüsünün sahibidir.
- Anomalileri DPO'ya raporlar.

### 4.6 Hukuk
- Hukuki bekletmeleri başlatır ve kaldırır.
- Üye devleti minimum saklama süreleri konusunda danışmanlık yapar.
- Dava stratejisini etkileyen istisnaları gözden geçirir.

### 4.7 İç Denetim
- En az yılda bir bu Politika ile uyumluluğu test eder.
- Bulguları Denetim Komitesine ve DPO'ya raporlar.

### 4.8 Tüm çalışanlar
- Bu Politikaya uyar.
- Onaylanmış sistemler dışında gayri resmi kopyalar (yerel sürücüler, kişisel e-posta, çıktılar) oluşturmaz.
- Şüpheli uyumsuzluğu DPO'ya bildirir.

## 5. Periyodik inceleme

### 5.1 Politika incelemesi
- DPO bu Politikayı en az yılda bir gözden geçirir.
- Hukuktaki maddi değişiklikler (örn. yeni bir AB tüzüğü, üye devlet uygulama yasası veya Schrems II türevleri gibi ABAD kararı) döngü dışı inceleme tetikler.

### 5.2 Çizelge incelemesi
- Saklama Çizelgesi yıllık olarak bir bütün olarak gözden geçirilir.
- Her Veri Sahibi takvim yılı başına en az bir kez kategorilerini gözden geçirir ve incelemeyi imzalar.

### 5.3 İmha incelemesi
- DPO, imha kayıtlarının üç ayda bir örneklemesini yapar.
- İç Denetim yıllık denetim gerçekleştirir (üretim sistemlerini, yedekleri, kâğıt arşivleri, işleyen onaylarını örnekler).

## 6. Eğitim ve farkındalık

- Tüm personel, saklama yükümlülükleri dahil yıllık GDPR eğitimini tamamlar.
- Veri Sahipleri, Saklama Çizelgesi ve istisna yönetimi konusunda özel eğitim alır.
- Yeni sistem entegrasyon projeleri DPO tarafından bir saklama-tasarımı incelemesi içerir.

## 7. Uyumsuzluk

Bu Politikaya uymama şunlara yol açabilir:

- İşten çıkarmaya kadar disiplin işlemi.
- GDPR ve üye devlet hukuku kapsamında medeni ve cezai sorumluluk.
- Başarısızlık bir kişisel veri ihlali oluşturuyorsa denetim makamına raporlama (Md. 33).

## 8. Tanımlar

| Terim | Anlam |
|---|---|
| Kişisel veri | Tanımlanmış veya tanımlanabilir bir gerçek kişiye ilişkin herhangi bir bilgi (Md. 4(1)). |
| İşleme | Kişisel veriler üzerinde gerçekleştirilen herhangi bir işlem (Md. 4(2)). |
| Saklama süresi | Bir kişisel veri kategorisinin saklanabileceği maksimum süre. |
| Silme | Kişisel verileri kalıcı olarak erişilemez ve kurtarılamaz hale getirme eylemi. |
| Anonimleştirme | Verinin artık kişisel veri olmadığı şekilde tanımlanabilirliğin geri dönülmez şekilde kaldırılması (Resital 26). |
| Takma adlandırma | Kişisel verilerin ek bilgi olmaksızın belirli bir ilgili kişiye atfedilemeyeceği şekilde işlenmesi (Md. 4(5)). |
| Kripto-parçalama | Kriptografik anahtarın imhası, şifrelenmiş verileri kurtarılamaz hale getirir. |
| Hukuki bekletme | Dava, soruşturma veya denetim nedeniyle rutin imhanın askıya alınması. |

## 9. Belge kontrolü

| Alan | Değer |
|---|---|
| Sürüm | 1.0 |
| Yürürlük tarihi | [TARİH] |
| Sonraki inceleme | [TARİH + 1 YIL] |
| Sahip | DPO |
| Onaylayan | Yönetim Komitesi |
| Dağıtım | Tüm personel, işleyenler |
