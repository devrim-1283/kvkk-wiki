---
Doküman / Document: Veri Sızıntısı Önleme (DLP) Politikası ve Standardı / Data Loss Prevention (DLP) Policy and Standard
Bölüm / Section: 05-teknik-tedbirler
Sahip / Owner: DLP Ekip Lideri / CISO / DLP Team Lead / CISO
Onaylayan / Approved by: BT Direktörü + KVKK Komitesi + Hukuk + İK / IT Director + KVKK Committee + Legal + HR
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş (yeni veri kümesi, false positive trendi, yeni vector) / Annual + triggered (new dataset, false positive trend, new vector)
İlgili Mevzuat / Legal Reference: Law No. 6698 KVKK Art. 4 (General Principles — proportionality), Art. 12 (Data Security), Art. 20 (Employee Monitoring — Constitution Art. 20 privacy); Labor Law Art. 27 et seq.; KVKK Employee Privacy Notice guide
İlgili Standart / Standard: ISO/IEC 27001:2022 A.8.12 (Data Leakage Prevention); NIST CSF 2.0 PR.DS-5; CIS Controls v8 #3.13; Cloud Security Alliance (CSA) DLP guidance; ENISA "Data Loss Prevention"
---

## English

# Data Loss Prevention (DLP)

## 1. Purpose

Defines controls designed to detect and prevent **unauthorized exit** (external sharing, leakage, intentional/unintentional disclosure) of personal data and other sensitive information. The operational arm of the principles "preventing unlawful access" under KVKK Art. 12 and "prohibition of out-of-purpose processing" under Art. 4.

## 2. Scope

DLP is designed for three core data states:

1. **Data in Use** — on the end user's device, within the application.
2. **Data in Motion** — on the network (email, web, cloud SaaS, messaging).
3. **Data at Rest** — in storage (server, share, cloud storage, endpoint disk).

## 3. Design Principles

1. **Data Classification First, DLP Second:** DLP is ineffective without a classification framework. Policies are written by class.
2. **Discovery First, Policy Second:** Cannot place control without seeing where data lies.
3. **Preventive + Detective Together:** Alarm + post-hoc review in unblockable scenarios.
4. **Balanced with Privacy:** Employee monitoring is proportional, disclosed, with reasonable log retention.
5. **Employee Training is Half of DLP:** Technological control is effective alongside behavior change.
6. **Continuous Tuning:** Until false positive drops below 20%, user trust erodes.
7. **Insider Threat Ready:** The most dangerous leak is from authorized users; UEBA + DLP integrated.

## 4. Data Discovery

### 4.1. Goal

To see which dataset lies where; to surface hidden/misplaced personal data.

### 4.2. Scope

- Endpoint (Windows/macOS/Linux laptop, server).
- File shares (SMB, NFS, SharePoint, Google Drive, Dropbox).
- Email archive.
- Databases.
- Object storage (S3/Blob/GCS).
- Code repositories.
- SaaS applications (Salesforce, Workday, ServiceNow, etc.).

### 4.3. Identification Methods

| Method | Description | Typical Use |
|--------|-----------|----------------|
| Regex / Pattern | Turkish ID number, IBAN, card number (Luhn), telephone | Structured fields |
| Keyword / Dictionary | "Salary", "test result", "medical" | Sectoral terms |
| Document fingerprint | Exact/partial match of a known sensitive document | Trade secret, contract |
| Database fingerprint | Detection of certain DB rows externally | Customer list |
| Machine learning classifier | Medical report, financial statement | Semi-structured |
| Optical Character Recognition | Text in images (Turkish ID photocopy, etc.) | Form filling |
| Microsoft Sensitivity Label | Auto / manual label | Corporate integration |

### 4.4. Discovery Effort

- First-party scan (full scan): one-time, baseline.
- Monthly delta scan.
- Triggered scan as new fields are opened.
- Finding report: sensitive data in wrong location → CAPA, owner migration.

## 5. Policy Design

### 5.1. Typical Identifier List for Turkish Context

| Data Type | Identification Signal | Policy Action |
|-----------|-----------------|--------------------|
| Turkish ID Number | 11 digits + algorithm check | Block (external email), Alarm (internal) |
| IBAN (TR..) | TR + 24 chars + checksum | Block (external), Alarm (internal) |
| Tax Number | 10 digits + algorithm | Alarm |
| Credit Card (PAN) | 13–19 digits + Luhn + BIN whitelist | Block everywhere |
| Health Data | ICD-10 code, "lab result" keywords | Block (external sharing) |
| Criminal Record | Legislation keywords | Block |
| Biometric (fingerprint, face template) | File format + size + "biometric" label | Block |
| Salary | Regex + payroll template | Block (external), Alarm (internal) |
| Employee personnel file | Sensitivity label | Block (external) |
| Customer list | DB fingerprint | Block / 2-step approval |
| Source code (strict) | Company repo path match | Alarm (personal device) |

### 5.2. Action Types

- **Block & Notify:** Action blocked, descriptive message to user.
- **Block & Justify:** User can override with justification; manager/SOC alerted.
- **Encrypt:** External sharing automatically encrypted (Microsoft Purview, Sensitivity label).
- **Quarantine:** File/email impounded, manager reviews.
- **Alert Only:** Alarm only; used in a phased production transition, **should not be permanent**.
- **Tombstone / Remove:** Data in wrong location is moved out, "should not be here" message left.

### 5.3. Policy Prioritization

- Strictest controls: PCI (card), special-category (health, biometric).
- Medium: Turkish ID, IBAN, name-surname, email.
- Low: General contact info (corporate emails sendable).
- Trade secrets, source code separate policy family.

## 6. DLP Components

### 6.1. Endpoint DLP

- Agent-based (CrowdStrike, Microsoft Purview, Trellix, Forcepoint, Symantec).
- USB / removable media control.
- Printer control.
- Clipboard restriction (sensitive copy notifies/blocks).
- Upload control in local applications (browser).

### 6.2. Network DLP

- Inline at the egress point (forward proxy, ICAP).
- HTTP/S, FTP, SMB analysis.
- TLS inspection for encrypted traffic (excluding privacy list — see [ag-guvenligi.md](ag-guvenligi.md)).

### 6.3. Email DLP

- Mail gateway integration (Mimecast, Proofpoint, Microsoft Defender).
- Outbound email examination: subject + body + attachment + nested attachment.
- Automatic encryption (sensitivity label triggered).
- External recipient warning.

### 6.4. Cloud / SaaS DLP (CASB)

- API-based CASB (Microsoft Defender for Cloud Apps, Netskope, Palo Alto Prisma).
- File scanning, sharing control within SaaS.
- "Public link" detection, automatic closure or alarm.
- Conditional access with IDP / device compliance.

### 6.5. Web/Mobile Channel DLP

- Webmail (Gmail, Yandex), file-share (WeTransfer, Dropbox personal), code sharing (pastebin, GitHub gist).
- Typical policy: upload from work device to personal webmail from personal device **block**.

### 6.6. Print DLP

- Print queues with DLP agent.
- Sending sensitive documents to non-company printer blocked.
- Documents classified as Confidential picked up from printer **with PIN**.

## 7. Employee Privacy and Legal Framework

### 7.1. Legal Boundaries

- **KVKK Art. 4 (Proportionality):** Must be necessary, limited, and proportional for the processing purpose.
- **Constitution Art. 20:** Privacy of private life.
- **Labor Law:** Employer's right of inspection, but balanced with employee privacy.
- **Constitutional Court and Court of Cassation case law:** Employee must be **explicitly notified in advance** that they are being monitored.

### 7.2. Operational Reflections

- DLP policy is **clearly** announced (annual signature) with the **Employee Privacy Notice** + **IT Use Policy**.
- Channels examined are listed (corporate email, file sharing, web proxy, endpoint).
- Personal webmail/social media/personal messaging content is **not examined**.
- Logging is performed with content **proportional** and **minimized** to purpose.
- DLP incident review 4-eyes (CISO + HR + Legal).
- Defined retention period (general rule 1 year; can be extended when investigation is opened).
- Disciplinary action arising from incident only via **formal process**, with the right of defense afforded to the employee.

### 7.3. BYOD Context

- DLP agent not installed on personal device; control applied within **work profile** (Android Work Profile, iOS supervised).
- Organization does not access personal data.
- Selective wipe — only work profile wipe.

## 8. False Positive and Tuning

### 8.1. Cost of FP

- User productivity loss.
- "Always false positive" perception creates desensitization to SOC alarms.
- Widespread use of override rights erodes the policy.

### 8.2. Tuning Process

- Target: false positive ≤ 20%.
- Monthly FP report, most frequently matching rule / user.
- Whitelist management (e.g., if internal software error messages resemble card numbers).
- Adding context (recipient domain, sender department, file format).
- Sharing real incident anonymized as training material.

## 9. Incident Response (DLP-Specific)

### 9.1. Incident Classes

| Class | Definition | Response |
|-------|-------|-------|
| Low | User unknowingly attached to external email, block worked | Training reminder |
| Medium | Repeated rule violation | Manager conversation, additional training |
| High | Bulk / intentional external transfer, sensitive data | Investigation, account freeze, HR + Legal |
| Critical | Active data leakage evidence | IR activation, breach management (08), KVKK Committee |

### 9.2. Investigation Flow

1. SOC triages the event.
2. If insufficient context, request explanation (justification) from user.
3. 4-eyes review: CISO representative + HR + Legal (high/critical).
4. Decision: closure / training / discipline / IR.
5. Chain of custody maintained.
6. Lessons learned feed back to policy.

## 10. Insider Threat Program

DLP is the technical arm of the insider threat program. Complementary:

- UEBA — user baseline + anomaly.
- HR signals (departure announcement, performance issue) with conditionally enhanced monitoring (justified, time-limited, with KVKK Officer approval, Legal supervised).
- Periodic insider threat review committee (CISO + HR + Legal + KVKK).
- 30 days of enhanced monitoring during employee leave period (default, exit synchronicity — aligned with exit interview).

## 11. Logging and Evidence

- Raw record of DLP event: time, user, channel, rule, action, matched sample (personal data minimized, hash + first 2 + last 2 chars).
- Retention: 1 year general, 5 years critical / under investigation.
- Chain of custody — see [log-yonetimi.md](log-yonetimi.md).
- Events to SIEM + CASB console.

## 12. KPI

- Discovery coverage: 95%+ data asset inventory coverage.
- DLP Block ratio / total: trend.
- False positive: ≤ 20%.
- Override usage: tracked, owned, low.
- Policy violation incidents: monthly trend, departmental training need.
- Privacy notice currency: annual.
- Annual drill (red team data exfil) detection rate: ≥ 85%.

## 13. Checklist

- [ ] Are data classification + sensitivity labels applied?
- [ ] Is discovery scanning running monthly for all storage types?
- [ ] Are Endpoint, Network, Email, CASB DLPs integrated and managed from a single console?
- [ ] Is there a "block everywhere" policy for PCI data?
- [ ] Is there a strict policy + audit for special-category data?
- [ ] Does the Employee Privacy Notice list DLP scope, signed annually?
- [ ] Is personal webmail/social media content out of scope of inspection?
- [ ] Is the work profile / personal data separation applied in BYOD?
- [ ] Are false positives reported monthly, with target ≤ 20%?
- [ ] Are DLP events reviewed 4-eyes (CISO + HR + Legal)?
- [ ] Is the insider threat program integrated with UEBA, with enhanced monitoring during departure period documented?
- [ ] Do DLP events go to SIEM, triggering process 08 at the KVKK breach threshold?
- [ ] Is the annual red team data exfil drill conducted?
- [ ] Is override usage owner/frequency monitored?
- [ ] Are printer, USB, clipboard controls policy compliant?
- [ ] Is CAPA opened for data found in wrong location by discovery?
- [ ] Is DLP scope on vendor/consultant device/access defined?

## 14. Common Mistakes

- Staying in "Detect only" mode and never moving to "prevent."
- Failing to inform employees about the existence of DLP — creates legal risk.
- Not realizing that network DLP is ineffective without TLS inspection.
- Excessively broad regex (e.g., all 11-digit numbers as Turkish ID) causing FP storms.
- Installing a full agent on a personal device in BYOD — violates KVKK proportionality.
- Override usage going unmonitored.
- DLP set up only with focus on external leakage, ignoring internal lateral data movement.

## 15. Relationship with Vendor Management

- DLP requirement for vendors processing data established as a contract clause.
- Notification SLA for vendor incident (24-72 hours).
- Vendor penetration test results periodically reviewed.
- See [06-idari-tedbirler/tedarikci-yonetimi.md](../06-idari-tedbirler/tedarikci-yonetimi.md).

---

## Türkçe

# Data Loss Prevention (DLP)

## 1. Amaç

Kişisel veri ve diğer hassas bilginin **yetkisiz biçimde dışarı çıkmasını** (dış paylaşım, sızdırılma, kasıtlı/kasıtsız ifşa) tespit ve önlemek için tasarlanmış kontrolleri tanımlar. KVKK m.12 "hukuka aykırı erişimi önleme" ve m.4 "amaç dışı işleme yasağı" ilkelerinin operasyonel ayağıdır.

## 2. Kapsam

DLP, üç temel veri durumu için tasarlanır:

1. **Data in Use** — son kullanıcı cihazında, uygulama içinde.
2. **Data in Motion** — ağda (e-posta, web, bulut SaaS, mesajlaşma).
3. **Data at Rest** — depolama alanlarında (sunucu, paylaşım, bulut depolama, endpoint disk).

## 3. Tasarım İlkeleri

1. **Veri Sınıflandırma Önce, DLP Sonra:** DLP, sınıflandırma çerçevesi olmadan etkisizdir. Politikalar sınıfa göre yazılır.
2. **Discovery Önce, Politika Sonra:** Hangi veri nerede yatıyor görülmeden kontrol koyulamaz.
3. **Önleyici + Tespit Edici Birlikte:** Block edilemeyen senaryoda alarm + post-hoc inceleme.
4. **Mahremiyet ile Dengeli:** Çalışan izleme orantılı, açıklanmış, log saklama makul.
5. **Çalışan Eğitimi DLP'nin Yarısıdır:** Teknolojik kontrol, davranış değişikliğiyle birlikte etkili olur.
6. **Sürekli Tunning:** False positive %20'nin altına inmediği sürece kullanıcı güveni erir.
7. **Insider Threat'a Hazır:** En tehlikeli sızıntı yetkili kullanıcıdandır; UEBA + DLP entegre.

## 4. Veri Discovery (Keşif)

### 4.1. Hedef

Hangi veri kümesi nerede yatıyor görmek; gizli/yanlış konumdaki kişisel veriyi ortaya çıkarmak.

### 4.2. Kapsam

- Endpoint (Windows/macOS/Linux laptop, sunucu).
- Dosya paylaşımı (SMB, NFS, SharePoint, Google Drive, Dropbox).
- E-posta arşivi.
- Veritabanları.
- Object storage (S3/Blob/GCS).
- Kod depoları.
- SaaS uygulamaları (Salesforce, Workday, ServiceNow, vs.).

### 4.3. Tanıma Yöntemleri

| Yöntem | Açıklama | Tipik Kullanım |
|--------|-----------|----------------|
| Regex / Pattern | TC kimlik no, IBAN, kart no (Luhn), telefon | Yapı belli alanlar |
| Keyword / Dictionary | "Maaş", "rapor sonucu", "tıbbi" | Sektörel terim |
| Document fingerprint | Bilinen hassas dokümanın tam/parçalı eşleşmesi | Ticari sır, sözleşme |
| Database fingerprint | Belirli DB satırlarının dış bulunması | Müşteri listesi |
| Machine learning classifier | Tıbbi rapor, finansal tablo | Yarı yapısal |
| Optical Character Recognition | Resim içinde metin (TC fotokopisi vb.) | Form doldurma |
| Microsoft Sensitivity Label | Otomatik / manuel etiket | Kurumsal entegrasyon |

### 4.4. Discovery Çalışması

- İlk taraflı tarama (full scan): tek seferlik, baseline.
- Aylık fark taraması.
- Yeni alan açıldıkça tetiklenmiş tarama.
- Bulgu raporu: hassas veri yanlış lokasyonda → CAPA, sahibinin migrasyonu.

## 5. Politika Tasarımı

### 5.1. Türk Bağlamı için Tipik Tanımlayıcı Listesi

| Veri Tipi | Tanıma Sınyali | Politika Aksiyonu |
|-----------|-----------------|--------------------|
| TC Kimlik No | 11 hane + algoritma kontrolü | Block (dış e-posta), Alarm (iç) |
| IBAN (TR..) | TR + 24 karakter + checksum | Block (dış), Alarm (iç) |
| Vergi Kimlik No | 10 hane + algoritma | Alarm |
| Kredi Kartı (PAN) | 13–19 hane + Luhn + BIN whitelist | Block heryerde |
| Sağlık Verisi | ICD-10 kodu, "tahlil sonucu" anahtar kelimeleri | Block (dış paylaşım) |
| Adli Sicil | Mevzuat anahtar kelimeleri | Block |
| Biyometrik (parmak, yüz şablonu) | Dosya formatı + boyut + "biyometrik" etiketi | Block |
| Maaş | Regex + bordro şablonu | Block (dış), Alarm (iç) |
| Çalışan özlük dosyası | Sensitivity label | Block (dış) |
| Müşteri listesi | DB fingerprint | Block / 2-step approval |
| Kaynak kod (sıkıyo) | Şirket repo path eşleşme | Alarm (kişisel cihaz) |

### 5.2. Aksiyon Türleri

- **Block & Notify:** Eylem engellenir, kullanıcıya açıklayıcı mesaj.
- **Block & Justify:** Kullanıcı gerekçe yazarak override edebilir; yönetici/SOC alarmlanır.
- **Encrypt:** Dış paylaşım otomatik şifreli (Microsoft Purview, Sensitivity label).
- **Quarantine:** Dosya/postaya el konulur, yönetici review eder.
- **Alert Only:** Yalnızca alarm; üretim aşamalı geçişte kullanılır, kalıcı **olmamalı**.
- **Tombstone / Remove:** Yanlış konumdaki veri yerinden alınır, "burada olmamalı" bilgisi bırakılır.

### 5.3. Politika Önceliklendirme

- En sıkı kontroller: PCI (kart), özel nitelikli (sağlık, biyometrik).
- Orta: TC kimlik, IBAN, ad-soyad, e-posta.
- Düşük: Genel iletişim bilgisi (kurumsal e-posta gönderilebilir).
- Şirket sırrı, kaynak kod ayrı politika ailesi.

## 6. DLP Bileşenleri

### 6.1. Endpoint DLP

- Ajan tabanlı (CrowdStrike, Microsoft Purview, Trellix, Forcepoint, Symantec).
- USB / removable media kontrolü.
- Yazıcı kontrolü.
- Pano (clipboard) sınırlandırma (hassas kopyalama bilgi verir/bloklar).
- Yerel uygulamada upload denetimi (tarayıcı).

### 6.2. Network DLP

- Çıkış noktasında inline (forward proxy, ICAP).
- HTTP/S, FTP, SMB analizi.
- Şifreli trafik için TLS inspection (mahremiyet listesi hariç — bkz. [ag-guvenligi.md](ag-guvenligi.md)).

### 6.3. Email DLP

- Mail gateway entegrasyonu (Mimecast, Proofpoint, Microsoft Defender).
- Outbound e-posta inceleme: konu + gövde + ek + nested ek.
- Otomatik şifreleme (sensitivity label triggered).
- Dış alıcı uyarısı.

### 6.4. Cloud / SaaS DLP (CASB)

- API tabanlı CASB (Microsoft Defender for Cloud Apps, Netskope, Palo Alto Prisma).
- SaaS içinde dosya tarama, paylaşım kontrolü.
- "Public link" tespiti, otomatik kapama veya alarm.
- IDP / cihaz uyumluluğu ile koşullu erişim.

### 6.5. Web/Mobile Channel DLP

- Webmail (Gmail, Yandex), file-share (WeTransfer, Dropbox personal), kod paylaşımı (pastebin, GitHub gist).
- Tipik politika: kişisel cihazlardan kişisel webmail'e iş cihazından upload **block**.

### 6.6. Print DLP

- Yazıcı kuyrukları DLP ajan ile.
- Hassas dokümanın şirket dışı yazıcıya gönderimi engelli.
- Gizli sınıfı dokümanlar yazıcıdan **PIN ile** alınır.

## 7. Çalışan Mahremiyeti ve Hukuki Çerçeve

### 7.1. Yasal Sınırlar

- **KVKK m.4 (Ölçülülük):** İşleme amacı için gerekli, sınırlı, ölçülü olmalı.
- **Anayasa m.20:** Özel hayatın gizliliği.
- **İş Kanunu:** İşverenin denetim hakkı, ancak çalışanın mahremiyetiyle dengelenmiş.
- **AYM ve Yargıtay içtihadı:** Çalışanın denetlendiğine **önceden açık biçimde bilgilendirilmesi** zorunlu.

### 7.2. Operasyonel Yansımalar

- DLP politikası, **Çalışan Aydınlatma Metni** + **Bilgi İşlem Kullanım Politikası** ile **açıkça** duyurulur (yıllık imza).
- İncelenen kanallar listelenir (kurumsal e-posta, dosya paylaşım, web proxy, endpoint).
- Kişisel webmail/sosyal medya/kişisel mesajlaşma içeriği **incelenmez**.
- Loglama amaca **uygun** ve **minimum** içerikle yapılır.
- DLP olay incelemesi 4-eyes (CISO + İK + Hukuk).
- Saklama süresi tanımlı (genel kural 1 yıl; soruşturma açıldığında uzatılabilir).
- Olay sonucunda disiplin işlemi sadece **resmi süreç** üzerinden, çalışana savunma hakkı tanınarak.

### 7.3. BYOD Bağlamı

- Kişisel cihaza DLP ajan kurulmaz; **iş profili** (Android Work Profile, iOS supervised) içinde kontrol uygulanır.
- Kişisel verilere kurum erişmez.
- Selektif silme — sadece iş profili wipe.

## 8. False Positive ve Tunning

### 8.1. FP'nin Maliyeti

- Kullanıcı verimsizliği.
- "Hep yanlış pozitif" algısı SOC alarmlarına duyarsızlık yaratır.
- Override haklarının yaygın kullanımı politikayı aşındırır.

### 8.2. Tunning Süreci

- Hedef: false positive ≤ %20.
- Aylık FP raporu, en sık eşleşen kural / kullanıcı.
- Beyaz liste yönetimi (örn. iç yazılım hata mesajları kart numarasına benziyorsa).
- Bağlam ekleme (alıcı domain, gönderici departman, dosya formatı).
- Eğitim malzemesi olarak gerçek olay anonimleştirilmiş paylaşımı.

## 9. Olay Yanıtı (DLP Spesifik)

### 9.1. Olay Sınıfları

| Sınıf | Tanım | Yanıt |
|-------|-------|-------|
| Düşük | Kullanıcı politikayı bilmeden dış e-posta'ya iliştirdi, block çalıştı | Eğitim hatırlatması |
| Orta | Tekrarlayan kural ihlali | Yönetici görüşmesi, ek eğitim |
| Yüksek | Toplu / kasti dış aktarım, hassas veri | Soruşturma, hesap dondurma, İK + Hukuk |
| Kritik | Aktif veri sızıntısı kanıtı | IR aktivasyonu, ihlal yönetimi (08), KVKK Komitesi |

### 9.2. İnceleme Akışı

1. SOC olayı triage eder.
2. Yetersiz bağlam varsa kullanıcıdan açıklama (gerekçe).
3. 4-eyes review: CISO temsilcisi + İK + Hukuk (yüksek/kritik).
4. Karar: kapatma / eğitim / disiplin / IR.
5. Kanıt zinciri korunur.
6. Lessons learned politikaya geri besler.

## 10. Insider Threat Programı

DLP, insider threat programının teknik ayağıdır. Tamamlayıcılar:

- UEBA — kullanıcı baseline + anomali.
- HR sinyalleri (ayrılık duyurusu, performans sorunu) ile koşullu artırılmış izleme (gerekçeli, süreli, KVKK Sorumlusu onayıyla, Hukuk denetimli).
- Periyodik insider threat inceleme komitesi (CISO + İK + Hukuk + KVKK).
- Çalışan ayrılık dönemi 30 gün artırılmış izleme (default, çıkış müşterekliği — exit interview ile uyumlu).

## 11. Loglama ve Kanıt

- DLP olayı ham kayıt: zaman, kullanıcı, kanal, kural, eylem, eşleşen örnek (kişisel veri minimize, hash + ilk 2 + son 2 karakter).
- Saklama: 1 yıl genel, 5 yıl kritik / soruşturmalı.
- Kanıt zinciri (chain of custody) — bkz. [log-yonetimi.md](log-yonetimi.md).
- Olaylar SIEM'e + CASB konsoluna.

## 12. KPI

- Discovery kapsamı: %95+ veri varlık envanterinin kapsanması.
- DLP Block oranı / toplam: trend.
- False positive: ≤ %20.
- Override kullanımı: izlenen, sahibi belli, az.
- Politika ihlali olayları: aylık trend, departman bazlı eğitim ihtiyacı.
- Aydınlatma metni güncellik: yıllık.
- Yıllık tatbikat (red team data exfil) tespit oranı: ≥ %85.

## 13. Kontrol Listesi

- [ ] Veri sınıflandırma + sensitivity label uygulanıyor mu?
- [ ] Discovery taraması tüm depolama tipleri için aylık çalışıyor mu?
- [ ] Endpoint, Network, E-posta, CASB DLP entegre tek konsoldan yönetiliyor mu?
- [ ] PCI veri için "block everywhere" politikası var mı?
- [ ] Özel nitelikli veri için sıkı politika + audit var mı?
- [ ] Çalışan Aydınlatma Metni DLP kapsamını listeliyor, yıllık imzalı mı?
- [ ] Kişisel webmail/sosyal medya içeriği inceleme dışı mı?
- [ ] BYOD'da iş profili / kişisel veri ayrımı uygulanıyor mu?
- [ ] False positive aylık raporlanıyor, hedef ≤ %20 mi?
- [ ] DLP olay 4-eyes review (CISO + İK + Hukuk) ile inceleniyor mu?
- [ ] Insider threat programı UEBA ile entegre mi, ayrılık döneminde artırılmış izleme yazılı mı?
- [ ] DLP olayları SIEM'e gidiyor, KVKK ihlal eşiğinde 08 sürecini tetikliyor mu?
- [ ] Yıllık red team data exfil tatbikatı yapılıyor mu?
- [ ] Override kullanımı sahibi/sıklığı izleniyor mu?
- [ ] Yazıcı, USB, pano kontrolü politika uyumlu mu?
- [ ] Discovery sonucu yanlış lokasyondaki veri için CAPA açılıyor mu?
- [ ] Tedarikçi/danışman cihaz/erişiminde DLP kapsamı belirli mi?

## 14. Yaygın Hatalar

- "Detect only" modunda kalıp asla "prevent"e geçmemek.
- Çalışana DLP varlığını duyurmamak — hukuki risk yaratır.
- TLS inspection olmadan ağ DLP'sinin etkisiz olduğunun fark edilmemesi.
- Aşırı geniş regex (ör. tüm 11 haneli sayılar TC) yüzünden FP fırtınası.
- BYOD'da kişisel cihaza tam ajan kurulması — KVKK ölçülülük ihlali.
- Override kullanımının takipsiz kalması.
- DLP'nin yalnızca dış sızıntı odaklı kurulması, dahili lateral data movement görmezden gelinmesi.

## 15. Tedarikçi Yönetimi ile İlişki

- Veri işleyen tedarikçilerin DLP zorunluluğu sözleşme maddesi olarak belirlenir.
- Tedarikçi olayında bildirim SLA (24-72 saat).
- Tedarikçi penetrasyon test sonuçları periyodik gözden geçirilir.
- Bkz. [06-idari-tedbirler/tedarikci-yonetimi.md](../06-idari-tedbirler/tedarikci-yonetimi.md).
