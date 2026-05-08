---
Doküman / Document: Periyodik İmha Prosedürü / Periodic Destruction Procedure
Bölüm / Section: 04-veri-saklama-ve-imha
Sahip / Owner: KVKK Sorumlusu / KVKK Officer
Onaylayan / Approved by: Hukuk Müdürü + Bilgi Güvenliği Yöneticisi / Legal Director + Information Security Manager
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş / Annual + triggered (regulatory change, system change, post-breach)
İlgili Mevzuat / Legal Reference: Reg. Art. 7, 11, 12; KVKK Art. 7, 13
---

## English

# Periodic Destruction Procedure

## 1. Purpose

This procedure regulates how the data controller will operationally fulfill its ex officio destruction obligation in the **first periodic destruction** following the date the obligation to erase/destroy/anonymize personal data arose, pursuant to Reg. Art. 11. It also describes the triggered destruction flow that begins with data subject requests under KVKK Art. 13 and Reg. Art. 12.

## 2. Statutory Time Frame

### 2.1. Data Controller With a Policy (Reg. Art. 11/1-2)

- Destruction is performed in the **first periodic destruction** following the date the destruction obligation arose.
- The periodic destruction interval is determined in the policy; in any case, it cannot exceed **6 months**.
- In the worst case, destruction is completed within a maximum of 6 months after the obligation arose.

### 2.2. Data Controller Without a Policy (Reg. Art. 11/3)

- Destruction is performed within **3 months** of the date the obligation arose.

### 2.3. Period Shortening by the Board (Reg. Art. 11/4)

- The Board may shorten periods if irreparable or impossible-to-remedy damages would arise and there is clear unlawfulness.

### 2.4. Data Subject Request (Reg. Art. 12)

- If all processing conditions have ceased: Concluded within **30 days**.
- If data was transferred to a third party: The third party is notified; actions per the Regulation are ensured at the third party.
- If processing conditions have not entirely ceased: Reasoned rejection under KVKK Art. 13/3; rejection communicated in writing/electronically within 30 days.

## 3. Destruction Calendar

| Periodic Destruction No | Trigger Date | Preparation Start | Execution Window | Reporting |
|-------------------------|--------------|-------------------|------------------|-----------|
| May Periodic Destruction | May 1 each year | April 15 | May 1 – May 15 | To Board by May 31 |
| November Periodic Destruction | Nov 1 each year | Oct 15 | Nov 1 – Nov 15 | To Board by Nov 30 |

## 4. Process Flow (Periodic Destruction)

```
+--------------------------------------------------+
| STEP 1: Trigger                                  |
| Periodic destruction calendar reached            |
| Owner: KVKK Officer                              |
| Output: Trigger notification                     |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| STEP 2: Generate Candidate List                  |
| Inventory scanned, expired records identified.   |
| Owner: IT Operations + Relevant Units            |
| Output: Destruction candidate list (system,      |
| category, row count, date range)                 |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| STEP 3: Legal Filter — Legal Hold Check          |
| Legal Department reviews the candidate list:     |
| - Ongoing litigation? Investigation? Inquiry?    |
| Owner: Legal Director                            |
| Output: Approved destruction list + Hold list    |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| STEP 4: Data Owner Unit Approval                 |
| List sent to relevant unit manager.              |
| Manager performs final commercial/operational    |
| check.                                           |
| Owner: Unit Manager                              |
| Output: Unit approval or reasoned objection      |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| STEP 5: KVKK Officer Approval                    |
| Total list approved by KVKK Officer.             |
| Method (erasure/destruction/anonymization)       |
| specified per item.                              |
| Owner: KVKK Officer                              |
| Output: Final destruction list + method matrix   |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| STEP 6: Test Run (Dry Run)                       |
| Destruction job tested in staging before prod.   |
| Test sample: 100 records; if validation fails,   |
| do not promote to production.                    |
| Owner: IT Operations                             |
| Output: Dry run report                           |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| STEP 7: Destruction Execution                    |
| Final list executed on systems.                  |
| - Active databases                                |
| - Personal data in audit logs                    |
| - Cloud objects                                  |
| - Backups (per rotation calendar)                |
| - Replication environments                       |
| - Structured/unstructured logs                   |
| Owner: IT Operations                             |
| Output: System logs, hash evidence               |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| STEP 8: Verification                             |
| Information Security performs independent        |
| verification:                                    |
| - Sample-based verification of destruction       |
| - Backup/replica verification                    |
| Owner: Information Security                      |
| Output: Verification report                      |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| STEP 9: Record Preparation                       |
| Destruction record is prepared.                  |
| Owner: KVKK Officer + Executor                   |
| Output: Signed record                            |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| STEP 10: Approval Chain                          |
| Records signed by:                               |
| - KVKK Officer (preparer)                        |
| - Information Security Manager (verifier)        |
| - Legal Director (legal compliance)              |
| - Relevant Unit Manager (operational compliance) |
| Owner: KVKK Officer                              |
| Output: Approved record                          |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| STEP 11: Archiving                               |
| Record and supporting evidence archived.         |
| Retention: at least 3 years (Reg. Art. 7(3))     |
| Owner: KVKK Officer                              |
| Output: Archive entry                            |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| STEP 12: Board Reporting                         |
| Periodic destruction summary submitted to top    |
| management.                                      |
| Owner: KVKK Officer                              |
| Output: Board summary report                     |
+--------------------------------------------------+
```

## 5. Destruction Triggered by Data Subject Request (Reg. Art. 12)

```
+--------------------------------------------------+
| STEP 1: Application Receipt                      |
| Application received via written, KEP, email or  |
| application form.                                |
| Counter starts: T+0                              |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| STEP 2: Registration and Assignment (T+1)        |
| Application logged in KVKK application system.   |
| KVKK Officer assigned as owner.                  |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| STEP 3: Identity Verification (T+3)              |
| Verify the applicant is the data subject.        |
| Power of attorney check if a representative.     |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| STEP 4: Data Identification (T+7)                |
| Identify in which systems and which categories   |
| the data resides.                                |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| STEP 5: Processing Condition Assessment (T+14)   |
| Check if KVKK Art. 5/Art. 6 conditions still     |
| exist.                                           |
| - All ended? -> STEP 6                           |
| - Continuing? -> Reasoned rejection              |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| STEP 6a: Third-Party Identification (T+18)       |
| To whom was data transferred? List drawn up.     |
| Notify third party per Reg. Art. 12/1-b.         |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| STEP 7: Destruction Execution (T+25)             |
| Method selection (Art. 7(5)) made with reasons   |
| and communicated to data subject.                |
| Active system + backups + log + replica.         |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| STEP 8: Record and Response (T+30)               |
| Record prepared.                                 |
| Written/electronic response sent to data         |
| subject. Response states method and date.        |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| STEP 9: Third-Party Confirmation                 |
| Confirmation received from third party.          |
| Confirmation archived as supporting document.    |
+--------------------------------------------------+
```

### 5.1. Calculation of the 30-Day Period

- The period runs from the **first day** the application reaches the data controller.
- Public holidays / weekends are counted; the period is not extended.
- If the application requires a fee (per the Communiqué), the period runs from the date the fee is paid.
- If additional information is requested for identity verification, the remaining period runs from when the additional information arrives (the period pauses, not resets).

## 6. Backup and Replication Destruction Strategy

Erasure on active data **does not reach backups**. The backup destruction strategy is set in the policy:

### 6.1. Strategy A — Wait for Backup Rotation

- A "marker" is placed on the active data on the destruction date.
- When backups are deleted per the rotation calendar, the data is automatically gone.
- The maximum backup retention period is explicitly stated in the policy (e.g. 6 months).
- The response to the data subject states "deleted from active system; will be fully destroyed at the end of backup rotation period."

### 6.2. Strategy B — Backup Key Destruction (Crypto-Shred)

- Backups are encrypted with a separate DEK (Data Encryption Key) each time.
- DEKs are kept in KMS.
- When a backup is to be destroyed, only the DEK is destroyed; the backup becomes mathematically unreadable.
- Fast, traceable and recordable.

### 6.3. Strategy C — Tape / Cold Backup Physical Destruction

- Degauss + shredding for LTO tape or optical cold backups.
- With vendor certificate.

## 7. Destruction of Personal Data in Log Files

- **Structured logs:** Personal fields of records on the destruction list are nulled/anonymized; the row itself may remain for audit needs.
- **Unstructured logs:** The file is fully deleted at end of retention.
- **SIEM:** Index-based lifecycle policy; old indexes deleted automatically.
- **Audit log:** The audit log itself is not destroyed because it carries evidentiary value; however, personal data within it is cleansed when records expire, observing audit retention periods.

## 8. Controls and Audit

- **Monthly:** Retention job outputs, log cleansing reports, hash counts.
- **Quarterly:** Policy-vs-inventory comparison; status of hold list.
- **Annual:** Independent internal audit; sample-based record verification.
- **KPIs:**
  - Records eligible / records destroyed (>95%)
  - Average response time for data subject requests (<25 days)
  - Open hold files (<10)
  - Erroneous destruction (wrong record) rate (0)

## 9. Records and Retention

- Reg. Art. 7(3) — at least **3 years**, excluding other legal obligations.
- The internal standard is **5 years** (considering audit and litigation periods).
- Records are kept as electronically signed PDFs in a secure archive.

## 10. Common Mistakes and Solutions

| Mistake | Solution |
|---------|----------|
| Calendar arrived but no candidate list | Inventory ownership assigned to KVKK Officer; monthly scanning automated |
| Unit defers destruction citing "we still need data" | Deferral only with concrete legal reason; commercial benefit insufficient |
| Hold rationale unclear | Hold requires written rationale + Legal signature; hold log maintained |
| Third-party notification forgotten | "Third-party identification" is a mandatory step; recipient group link in inventory used |
| Backup not planned | Strategy A/B/C chosen in policy; backup destruction calendar tied to periodic calendar |
| Record incomplete | Use the record template; missing fields automatically blocked |

---

## Türkçe

# Periyodik İmha Prosedürü

## 1. Amaç

Bu prosedür; Yönetmelik m.11 uyarınca veri sorumlusunun, kişisel verileri silme/yok etme/anonim hale getirme yükümlülüğünün ortaya çıktığı tarihi takip eden **ilk periyodik imha** işleminde resen imha yükümlülüğünün operasyonel olarak nasıl yerine getirileceğini düzenler. Ayrıca KVKK m.13 ve Yön. m.12 kapsamında ilgili kişi talepleri ile başlayan tetiklenmiş imha akışını tarif eder.

## 2. Yasal Süre Çerçevesi

### 2.1. Politikası Olan Veri Sorumlusu (Yön. m.11/1-2)

- İmha yükümlülüğü oluştuğu tarihi takip eden **ilk periyodik imha**da imha yapılır.
- Periyodik imha aralığı politikada belirlenir; **her halde 6 ayı geçemez**.
- En kötü senaryoda yükümlülük oluştuktan sonra azami 6 ay içinde imha tamamlanır.

### 2.2. Politikası Olmayan Veri Sorumlusu (Yön. m.11/3)

- Yükümlülüğün ortaya çıktığı tarihten itibaren **3 ay içinde** imha yapılır.

### 2.3. Kurul Tarafından Süre Kısaltma (Yön. m.11/4)

- Kurul; telafisi güç veya imkânsız zararların doğması ve açıkça hukuka aykırılık olması halinde süreleri kısaltabilir.

### 2.4. İlgili Kişi Talebi (Yön. m.12)

- İşleme şartlarının tamamı ortadan kalkmışsa: **30 gün** içinde sonuçlandırılır.
- Veri üçüncü kişiye aktarılmışsa: Üçüncü kişiye bildirim yapılır; üçüncü kişi nezdinde Yönetmelik kapsamında işlem yapılması temin edilir.
- İşleme şartları tamamen ortadan kalkmamışsa: KVKK m.13/3 uyarınca gerekçeli ret; ret cevabı 30 gün içinde yazılı/elektronik olarak iletilir.

## 3. İmha Takvimi

| Periyodik İmha No | Tetikleme Tarihi | Hazırlık Başlangıcı | Uygulama Pencerasi | Raporlama |
|-------------------|------------------|--------------------|--------------------|----------|
| Mayıs Periyodik İmhası | Her yıl 01 Mayıs | 15 Nisan | 01 Mayıs – 15 Mayıs | 31 Mayıs'a kadar Yönetim Kuruluna |
| Kasım Periyodik İmhası | Her yıl 01 Kasım | 15 Ekim | 01 Kasım – 15 Kasım | 30 Kasım'a kadar Yönetim Kuruluna |

## 4. Süreç Akışı (Periyodik İmha)

```
+--------------------------------------------------+
| ADIM 1: Tetikleme                                |
| Periyodik imha takvimi geldi                     |
| Sorumlu: KVKK Sorumlusu                          |
| Çıktı: Tetikleme bildirimi                       |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 2: Aday Listesi Oluşturma                   |
| Envanter taranır, süresi dolmuş kayıtlar çıkar.  |
| Sorumlu: BT Operasyon + İlgili Birimler          |
| Çıktı: İmha aday listesi (sistem, kategori,      |
| satır sayısı, tarih aralığı)                     |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 3: Hukuki Filtre — Legal Hold Kontrolü      |
| Hukuk Müdürlüğü, aday listeyi inceler:           |
| - Devam eden dava? Soruşturma? Inceleme?         |
| Sorumlu: Hukuk Müdürü                            |
| Çıktı: Onaylı imha listesi + Hold listesi        |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 4: Veri Sahibi Birim Onayı                  |
| Liste, ilgili birim yöneticisine gönderilir.     |
| Birim yöneticisi son ticari/operasyonel kontrol. |
| Sorumlu: Birim Yöneticisi                        |
| Çıktı: Birim onayı veya gerekçeli itiraz         |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 5: KVKK Sorumlusu Onayı                     |
| Toplam liste KVKK Sorumlusu tarafından onaylanır.|
| Yöntem (silme/yok etme/anonim) listede belirtilir|
| Sorumlu: KVKK Sorumlusu                          |
| Çıktı: Final imha listesi + yöntem matrisi       |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 6: Test Çalıştırması (Dry Run)              |
| Üretim öncesi staging'de imha jobu test edilir.  |
| Eski test: 100 kayıt; doğrulama; başarısızsa     |
| üretime geçilmez.                                |
| Sorumlu: BT Operasyon                            |
| Çıktı: Dry run raporu                            |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 7: İmha Uygulaması                          |
| Final liste sistem üzerinde uygulanır.           |
| - Aktif veritabanları                            |
| - Audit log içindeki kişisel veri                |
| - Bulut nesneleri                                |
| - Yedekler (rotasyon takvimine göre)             |
| - Replikasyon ortamları                          |
| - Yapılı/yapısız loglar                          |
| Sorumlu: BT Operasyon                            |
| Çıktı: Sistem logları, hash kanıtları            |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 8: Doğrulama                                |
| Bilgi Güvenliği bağımsız doğrulama yapar:        |
| - Örneklem ile imhanın gerçekleştiği kontrol     |
| - Yedek/replika doğrulama                        |
| Sorumlu: Bilgi Güvenliği                         |
| Çıktı: Doğrulama raporu                          |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 9: Tutanak Düzenleme                        |
| İmha kayıt tutanağı düzenlenir.                  |
| Sorumlu: KVKK Sorumlusu + İmha Yapan             |
| Çıktı: İmza atanmış tutanak                      |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 10: Onay Zinciri                            |
| Tutanaklar:                                      |
| - KVKK Sorumlusu (hazırlayan)                    |
| - Bilgi Güvenliği Yöneticisi (doğrulayan)        |
| - Hukuk Müdürü (hukuki uygunluk)                 |
| - İlgili Birim Müdürü (operasyonel uygunluk)     |
| Sorumlu: KVKK Sorumlusu                          |
| Çıktı: Onaylı tutanak                            |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 11: Arşivleme                               |
| Tutanak ve eki kanıtlar arşive alınır.           |
| Saklama süresi: en az 3 yıl (Yön. m.7(3))        |
| Sorumlu: KVKK Sorumlusu                          |
| Çıktı: Arşiv kaydı                               |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 12: Yönetim Kurulu Raporlaması              |
| Periyodik imha özet raporu üst yönetime sunulur. |
| Sorumlu: KVKK Sorumlusu                          |
| Çıktı: Yönetim Kurulu özet raporu                |
+--------------------------------------------------+
```

## 5. İlgili Kişi Talebi ile Tetiklenen İmha (Yön. m.12)

```
+--------------------------------------------------+
| ADIM 1: Başvurunun Alınması                      |
| Yazılı, KEP, e-posta veya başvuru formu kanalı   |
| ile talep alınır.                                |
| Süre Sayacı Başlar: T+0                          |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 2: Kayıt ve Atama (T+1 gün)                 |
| Talep KVKK başvuru sistemine kaydedilir.         |
| KVKK Sorumlusu sorumlu olarak atanır.            |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 3: Kimlik Doğrulama (T+3 gün)               |
| Başvuranın ilgili kişi olduğu teyit edilir.      |
| Vekilse vekaletname kontrolü.                    |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 4: Veri Tespiti (T+7 gün)                   |
| Hangi sistemlerde, hangi kategorilerde veri      |
| bulunduğu tespit edilir.                         |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 5: İşleme Şartı Değerlendirmesi (T+14 gün)  |
| KVKK m.5/m.6 şartlarının halen var olup          |
| olmadığı kontrol edilir.                         |
| - Tamamı sona erdi mi?  -> ADIM 6                |
| - Devam ediyor mu?      -> Gerekçeli ret         |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 6a: Üçüncü Kişi Tespiti (T+18 gün)          |
| Veri kimlere aktarılmış? Liste çıkarılır.        |
| Üçüncü kişiye Yön. m.12/1-b bildirimi yapılır.   |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 7: İmha Uygulaması (T+25 gün)               |
| Yöntem seçimi (m.7(5)): gerekçeli olarak         |
| seçilir, ilgili kişiye iletilir.                 |
| Aktif sistem + yedekler + log + replika.         |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 8: Tutanak ve Cevap (T+30 gün)              |
| Tutanak düzenlenir.                              |
| İlgili kişiye yazılı/elektronik cevap iletilir.  |
| Cevapta yöntem ve tarih belirtilir.              |
+--------------------------------------------------+
                       |
                       v
+--------------------------------------------------+
| ADIM 9: Üçüncü Kişi Doğrulaması                  |
| Üçüncü kişiden imha teyidi alınır.               |
| Teyit ek olarak arşivlenir.                      |
+--------------------------------------------------+
```

### 5.1. 30 Gün Süresinin Hesaplanması

- Süre, başvurunun veri sorumlusuna ulaştığı **ilk gün**den itibaren işler.
- Resmi tatil / hafta sonu hesaba katılır; süre uzamaz.
- Başvuru ücreti gerektiriyorsa (Tebliğ kapsamı), ücret yatırılma tarihinden itibaren süre işler.
- Kimlik doğrulama için ek bilgi istenmişse, ek bilginin geldiği tarihten itibaren kalan süre işler (ancak süre durur, sıfırlanmaz).

## 6. Yedek ve Replikasyon İmha Stratejisi

Aktif veride yapılan silme **yedeğe ulaşmaz**. Yedek imha stratejisi politikaya bağlanır:

### 6.1. Strateji A — Yedek Rotasyonu Beklemek

- Aktif veride imha tarihinde "marker" konur.
- Yedek rotasyon takvimine göre yedek silindiğinde veri otomatik yok olur.
- Maksimum yedek tutma süresi politikada açıkça belirtilir (ör. 6 ay).
- İlgili kişi talebine cevapta "aktif sistemden silindi; yedek rotasyonu süresi sonunda tamamen yok edilecektir" beyanı verilir.

### 6.2. Strateji B — Yedek Anahtar İmhası (Crypto-Shred)

- Yedekler yazılırken her seferinde ayrı bir DEK (Data Encryption Key) ile şifrelenir.
- DEK'ler KMS'te tutulur.
- Yedek imha edilmek istendiğinde yalnızca DEK imha edilir; yedek matematik olarak okunamaz hale gelir.
- Hızlı, izlenebilir ve tutanaklı.

### 6.3. Strateji C — Tape / Soğuk Yedek Fiziksel İmha

- LTO bant veya optik soğuk yedek için degauss + parçalama.
- Tedarikçi sertifikası ile.

## 7. Log Dosyalarındaki Kişisel Verinin İmhası

- **Yapılı loglar:** İmha listesindeki kayıtların log içindeki kişisel alanları null/anonim yapılır; satırın kendisi denetim ihtiyacı için kalabilir.
- **Yapısız loglar:** Saklama süresi sonunda dosya tümüyle silinir.
- **SIEM:** İndeks bazlı yaşam döngüsü politikası; eski indeksler otomatik silinir.
- **Audit log:** Audit log'un kendisi delil değeri taşıdığı için imha edilmez; ancak içindeki kişisel veri, kayıt sona erince, denetim sürelerine sadık kalınarak temizlenir.

## 8. Kontroller ve Denetim

- **Aylık:** Retention job çıktıları, log temizleme raporları, hash sayısı.
- **Çeyreklik:** Politika ile envanter karşılaştırması; hold listesinin durumu.
- **Yıllık:** Bağımsız iç denetim; örneklem ile tutanak doğrulaması.
- **KPI'lar:**
  - Yükümlülük doğan veri sayısı / İmha edilen veri sayısı (>%95)
  - İlgili kişi talebi ortalama cevap süresi (<25 gün)
  - Açık hold dosya sayısı (<10)
  - Hatalı imha (yanlış kayıt) oranı (0)

## 9. Tutanak ve Kayıt Saklama

- Yön. m.7(3) — diğer hukuki yükümlülükler hariç **en az 3 yıl** saklanır.
- 3 yıllık asgari süre yerine kurum içi standart **5 yıl** olarak alınır (denetim ve dava süresi göz önünde bulundurularak).
- Tutanaklar elektronik imzalı olarak güvenli arşivde tutulur.

## 10. Tipik Hatalar ve Çözümler

| Hata | Çözüm |
|------|-------|
| İmha takvimi geldi ama aday listesi yok | Envanter sahipliği KVKK Sorumlusu'na verilir; aylık tarama otomatikleşir |
| Birim "verim lazım" diyerek imhayı erteler | Erteleme ancak somut hukuki sebep ile mümkündür; ticari fayda yetersiz |
| Hold gerekçesi belirsiz | Hold için yazılı gerekçe + Hukuk imzası zorunludur; hold kayıt sistemi tutulur |
| Üçüncü kişiye bildirim unutuldu | İmha akışında "üçüncü kişi tespiti" zorunlu adımdır; envanterdeki alıcı grubu bağı kullanılır |
| Yedek planlanmadı | Strateji A/B/C politikada seçilir; yedek imha takvimi periyodik imha takvimine bağlanır |
| Tutanak eksik | Tutanak şablonu kullanılır; eksik alan otomatik validasyonla bloklanır |
