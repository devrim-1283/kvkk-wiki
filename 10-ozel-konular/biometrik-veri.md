---
Doküman / Document: Biyometrik Veri Yönetimi (PDKS, Erişim, Ödeme, Yüz Tanıma) / Biometric Data Management (Time/Attendance, Access, Payment, Facial Recognition)
Bölüm / Section: 10-ozel-konular
Sahip / Owner: KVKK Sorumlusu + IT + İK + Bilgi Güvenliği / KVKK Officer + IT + HR + Information Security
Onaylayan / Approved by: Hukuk Müdürü + KVKK Komitesi / Head of Legal + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + Kurul kararları doğrultusunda / Annual + per Authority decisions
İlgili Mevzuat / Legal Reference: Law No. 6698 (KVKK) Art. 6 (special category); Authority Decision No. 2018/10 dated 31.01.2018 on "Adequate Measures to be Taken by Data Controllers in Processing of Special Category Personal Data"; Constitutional Court E.2014/180; ECtHR victim case law
---

## English

# Biometric Data Management

## 1. Definition and Scope

**Biometric data:** Data derived from a person's **physical, physiological, or behavioral characteristics** that allow **unique identification** of that person.

| Type | Example |
|------|---------|
| Physical | Fingerprint, palm vein, retina, iris, facial template |
| Physiological | DNA, voice timbre profile, heart rhythm |
| Behavioral | Gait, keystroke pattern, signature dynamics |

KVKK Art. 6(1): **Biometric data = special-category personal data.**

## 2. Legal Framework

### 2.1. KVKK Art. 6 Processing Conditions

Special-category data may be processed:

1. With **explicit consent** (Art. 6(2)), OR
2. Where **expressly provided in laws** (Art. 6(3) - except health/sex life; for biometric data, this may create grounds for processing without explicit consent).

### 2.2. Authority Decision 2018/10

Data controllers processing special-category data must take **adequate measures**:

1. Prepare policies and procedures (KVKK policy set).
2. Regular training and confidentiality agreements with employees.
3. Authorization control and access policy.
4. Defined scope and duration of authorization.
5. Periodic authorization review.
6. Revocation of authorization for departing employees.
7. Security of the environment that accesses the data (anti-virus, firewall, etc.).
8. **Cryptographic** storage of data in electronic environment.
9. Key management in a secure environment.
10. Transfer over **encrypted** channels.
11. Use of KEP or methods involving cryptography.
12. Protection of physically stored personal data against unauthorized access.

> **Critical:** If biometric data is **stored unencrypted**, the Authority's case law treats it as a direct violation.

## 3. Biometric Use Scenarios

### 3.1. Personnel Time and Attendance System (PDKS)

| Method | KVKK Risk | Alternative |
|--------|-----------|-------------|
| Magnetic card | Low | - |
| Password / PIN | Low | - |
| Mobile app (geofence) | Medium | GPS controversial |
| Fingerprint | **High** (special category) | Above |
| Palm vein | **High** | Same |
| Facial recognition | **High** | Same |

**Authority position (decisions from 2019, 2020 and later):** **Alternative methods must be considered** for biometric PDKS. If a card/password is sufficient, biometric use is deemed **disproportionate**.

### 3.2. Physical Access (Doors, Safes, Data Centers)

- Low-risk areas: card is sufficient.
- High security (R&D, safes, data centers): biometric grounds may be justified.
- Hybrid: card + fingerprint (two factors).

### 3.3. Payment (Face/Fingerprint)

- Customer payment by face/finger -> explicit consent mandatory.
- On-device biometrics like Apple Pay / Face ID stay **on the device** -> not processed by us as data controller; care required in integration.

### 3.4. Authorization (BYOD, Mobile Device)

- Device unlock by biometrics is local to the device; we are not the data controller.
- Logging into our systems with a biometric token = we are data controller; consent + DPIA required.

### 3.5. Call-Center Voice Tone

- Identity verification by voice timbre -> biometric.
- Explicit consent + an alternative (password, OTP) must be offered.
- For those who refuse, "additional security questions" method offered.

## 4. DPIA (Data Protection Impact Assessment) Requirement

The Authority's guides recommend DPIA for high-risk processing; combined with Decision 2018/10 and international good practice, DPIA is a **de facto requirement** for biometrics.

### 4.1. DPIA Sections

1. Definition of processing (system, data, person count, flow).
2. Legal ground and necessity.
3. Proportionality test (alternative analysis).
4. Effects on data subject rights.
5. Risks (leak, fraud, identity theft, discrimination).
6. Measures (technical + administrative).
7. Residual risk + acceptance.
8. KVKK Committee approval.

### 4.2. DPIA Triggers

- New biometric system installation.
- Scope expansion (e.g., 100 -> 600 employees).
- New purpose (PDKS -> access control).
- Provider change.
- Annual review.

### 4.3. Template

For the DPIA template see `99-sablonlar/dpia-sablonu.md`.

## 5. Designing Explicit Consent

### 5.1. Employee Consent - Constraints

> Consent given by an employee to the employer is evaluated under a **freedom test**. The Authority's and the Constitutional Court's posture: due to employee-employer asymmetry, **consent is easily vitiated**.

For employee biometric use:

- An **alternative method** (card, password) must be offered.
- Refusing employees must **face no negative consequence** (promotion, performance, warning).
- Consent is collected via individually signed document; e-signature preferred.

### 5.2. Customer Explicit Consent

- Use of biometrics **cannot be mandatory** for service; alternatives must be offered.
- Consent process: privacy notice + separate consent box.
- Easy withdrawal (from app settings).

### 5.3. Minimum Content of Consent Text

```
Biometric data to be processed:
[ ] Fingerprint template (mathematical hash)
[ ] Facial template
[ ] Iris template

Processing purpose: ____________________
Processing duration: ____________________
Storage form: As template (irreversible cryptographic transformation),
              raw data not stored / deleted.

Alternative method: you may request [card / password / OTP].

I give my explicit consent: [ ] Yes  [ ] No
```

## 6. Templates vs. Raw Data

### 6.1. Template Storage

- A **mathematical representation** of the biometric (vector, hash, embedding).
- One-way transformation - ideally raw image cannot be recovered from the template.
- Modern systems store templates (fingerprint minutiae, 128/512-D facial embedding).

### 6.2. Raw Data Storage

- Fingerprint image, face photo, retina image.
- **Strongly discouraged** - cannot be undone in a breach (you can change a password, you cannot change your face).
- Raw data is processed only at first enrollment -> template is generated -> raw data is **deleted**.

### 6.3. Template Encryption

- AES-256 GCM at rest.
- Key in HSM (Hardware Security Module) or KMS (Key Management Service).
- Annual key rotation.
- Computation in encrypted environment if possible (homomorphic encryption - advanced).

## 7. Vendor Selection

### 7.1. Selection Criteria

- ISO/IEC 27001 + ISO/IEC 27701 (Privacy) certifications.
- ISO/IEC 19794 / 30107 (biometric standards) compliance.
- FIDO Alliance, BSI, NIST certifications.
- Türkiye-based data center preferred (reduces cross-border transfer issues).
- Not closed-source - transparent operation.
- Penetration test + security audit reports.

### 7.2. DPA (Data Processing Agreement)

- KVKK Art. 12 compliant contract.
- Processor obligations.
- Sub-processor approval process.
- Controller's audit rights.
- Breach notification within 24 hours.
- Data destruction + certificate at end of contract.

## 8. Technical Measures

### 8.1. Online Comparison

- Templates on encrypted server.
- Server-side comparison.
- TLS 1.3 network.
- API authentication + rate limit.

### 8.2. On-Device

- Template stored on the device (smart card, mobile secure element).
- Server only receives "match/no match".
- Lowest network risk; **preferred** for the data controller.

### 8.3. Anti-Spoofing

- Liveness detection.
- 3D facial recognition (not based on 2D photos).
- Fingerprint: moisture/heat/capacitive sensor.
- Periodic bypass tests.

### 8.4. Backup

- Template backups **encrypted**.
- Restore audited.
- 3-2-1 strategy (3 copies, 2 media, 1 off-site).

## 9. Administrative Measures (Decision 2018/10 Articles)

- Policy document (this file).
- Annual training - all personnel with access to biometric data.
- Confidentiality agreement (NDA) - IT, HR, external support.
- Access matrix (RBAC).
- Authorization review (quarterly).
- Authorization revocation for departing employees (24 hours).
- Access log audit.

## 10. Retention Period

| Data | Period |
|------|--------|
| Active employee template | For the duration of employment |
| Active customer template | For the duration of the service |
| After employee departure | **Immediate deletion** (recommended); at most 30 days |
| End of customer relationship | Deletion within 30 days |
| Backups | Backup rotation period |

Deletion record (proof of erasure) is retained.

## 11. Data Subject Rights

- Art. 11(a)-(c): Which template for what purpose -> simple answer.
- Art. 11(e): Erasure -> equivalent to leaving the service + switching to alternative method.
- Art. 11(f): If transferred, notification.
- The template **cannot be returned to the person** (mathematical transformation); however, under Art. 11(b), "template exists, generated on X" information can be provided.

## 12. Common Mistakes

| Mistake | Correct approach |
|---------|------------------|
| PDKS only via biometric | Alternative (card) mandatory |
| Storing raw photo | Template transformation + delete raw |
| No way to withdraw consent | Process design + alternative |
| Missing/insufficient DPA | KVKK Art. 12 compliant |
| Departing-employee template lingers | Delete within 24 hours |
| Unencrypted template | AES-256 + HSM |
| No anti-spoofing | Liveness mandatory |
| Default device passwords | Change + MFA |
| No DPIA | Mandatory before first use |
| Mandatory biometric for customer | Offer alternative |

## 13. KPIs

| KPI | Target |
|-----|--------|
| DPIA completion (each system) | 100% |
| Template encryption | 100% |
| Alternative method offered | 100% |
| Valid explicit consent rate | 100% |
| Departing-employee deletion SLA | < 24 hours |
| Anti-spoofing test frequency | Twice yearly |
| Authorization review | Quarterly |

## 14. Version History

| Version | Date | Change | Approval |
|---------|------|--------|----------|
| 1.0 | 2026-05-08 | First publication | KVKK Committee |

---

## Türkçe

# Biyometrik Veri Yönetimi

## 1. Tanım ve Kapsam

**Biyometrik veri:** Kişinin **fiziksel, fizyolojik veya davranışsal özelliklerinden** elde edilen ve o kişiyi **benzersiz şekilde tanımlamaya** yarayan veriler.

| Tip | Örnek |
|-----|-------|
| Fiziksel | Parmak izi, avuç içi venöz, retina, iris, yüz şablonu |
| Fizyolojik | DNA, ses tını profili, kalp ritmi |
| Davranışsal | Yürüyüş, klavye dokunma kalıbı, imza dinamiği |

KVKK m.6/1: **Biyometrik veri = özel nitelikli kişisel veri.**

## 2. Hukuki Çerçeve

### 2.1. KVKK m.6 İşleme Şartları

Özel nitelikli verilerin işlenmesi:

1. **Açık rıza** ile (m.6/2), VEYA
2. **Kanunlarda öngörülmesi** halinde (m.6/3 ile sağlık/cinsel hayat dışı; biyometrik için bu şart açık rızasız işlemeye ortam yaratabilir).

### 2.2. Kurul 2018/10 Kararı

Özel nitelikli veri işleyen veri sorumluları **yeterli önlemleri** almak zorundadır:
1. Politika ve prosedür hazırlamak (KVKK politika seti).
2. Çalışanlara düzenli eğitim, gizlilik sözleşmesi.
3. Yetki kontrol ve erişim politikası.
4. Yetki kapsam ve süresinin tanımlı olması.
5. Periyodik yetki kontrolü.
6. Görevden ayrılan çalışan yetki iptali.
7. Veriye erişen ortamın güvenliği (anti-virüs, güvenlik duvarı, vb.).
8. Verinin elektronik ortamda **kriptografik** yöntemle saklanması.
9. Anahtar yönetimi güvenli ortamda.
10. Aktarımın **şifreli** kanalla yapılması.
11. KEP veya kriptografi içeren yöntemler.
12. Fiziksel ortamda saklanan kişisel verilerin yetkisiz erişime karşı korunması.

> **Kritik:** Biyometrik veri **şifrelenmemiş** saklanırsa Kurul içtihadı doğrudan ihlal olarak değerlendirir.

## 3. Biyometrik Kullanım Senaryoları

### 3.1. Personel Devam Kontrol Sistemi (PDKS)

| Yöntem | KVKK Risk | Alternatif |
|--------|-----------|-----------|
| Manyetik kart | Düşük | — |
| Şifre / PIN | Düşük | — |
| Mobil uygulama (geofence) | Orta | GPS tartışmalı |
| Parmak izi | **Yüksek** (özel nitelikli) | Yukarıdakiler |
| Avuç içi venöz | **Yüksek** | Aynı |
| Yüz tanıma | **Yüksek** | Aynı |

**Kurul tutumu (2019, 2020 ve sonrası kararlar):** Biyometrik PDKS için **alternatif değerlendirilmesi** zorunlu. Eğer kart/şifre yeterliyse biyometrik kullanımı **orantısız** sayılır.

### 3.2. Fiziksel Erişim (Kapı, Kasa, Veri Merkezi)

- Düşük risk alanları: kart yeterli.
- Yüksek güvenlik (ARGE, kasa, veri merkezi): biyometrik gerekçe oluşturulabilir.
- Hibrit: kart + parmak izi (iki faktör).

### 3.3. Ödeme (Yüz/Parmak ile)

- Müşteri ödemesi (yüz/parmak ile) → açık rıza zorunlu.
- Apple Pay / Face ID gibi cihaz-yerleşik biyometri **cihazda** kalır → veri sorumlusu olarak Şirket'in işlemediği kabul edilir; ancak entegrasyonda dikkat.

### 3.4. Yetkilendirme (BYOD, Mobil Cihaz)

- Cihaz açma için biyometri = cihaz yereli, Şirket veri sorumlusu değil.
- Şirket sistemine biyometrik token ile giriş = veri sorumlusu Şirket; rıza + DPIA.

### 3.5. Çağrı Merkezi Ses Tını

- Ses tını ile kimlik doğrulama → biyometrik.
- Açık rıza + alternatif (parola, OTP) sunulması.
- Reddedenlere "ek güvenlik soru" yöntemi sunulur.

## 4. DPIA (Data Protection Impact Assessment) Zorunluluğu

KVKK Kurul rehberi yüksek riskli işlemelerde DPIA önerir; Kurul 2018/10 sayılı kararı + uluslararası iyi pratik biyometrik için DPIA'yı **fiilî zorunluluk** kılar.

### 4.1. DPIA Bölümleri

1. İşleme tanımı (sistem, veri, kişi sayısı, akış).
2. Hukuki sebep ve gerekliliği.
3. Orantılılık testi (alternatif analiz).
4. İlgili kişi hakları üzerindeki etki.
5. Riskler (sızıntı, dolandırıcılık, kimlik hırsızlığı, ayrımcılık).
6. Tedbirler (teknik + idari).
7. Kalan risk + kabul.
8. KVKK Komitesi onayı.

### 4.2. DPIA Tetikleyicileri

- Yeni biyometrik sistem kurulumu.
- Kapsam genişlemesi (örn. 100 → 600 çalışan).
- Yeni amaç eklenmesi (PDKS → erişim kontrolü).
- Sağlayıcı değişikliği.
- Yıllık gözden geçirme.

### 4.3. Şablon

DPIA şablonu için bkz. `99-sablonlar/dpia-sablonu.md`.

## 5. Açık Rıza Tasarımı

### 5.1. Çalışan Açık Rızası — Sınırlamalar

> Çalışanın işverene karşı verdiği rıza **özgürlük testi** ile değerlendirilir. KVKK Kurulu ve AYM tutumu: çalışan-işveren asimetrisi nedeniyle **rıza kolayca sakatlanır**.

Bu nedenle çalışan biyometrik kullanımında:
- **Alternatif yöntem** (kart, şifre) sunulmalı.
- Reddeden çalışanlar **olumsuz sonuç görmemelidir** (terfi, performans, uyarı).
- Rıza bireysel imzalı belge ile alınır, e-imza tercih.

### 5.2. Müşteri Açık Rızası

- Hizmet kullanımı için biyometrik **zorunlu** kılınamaz; alternatif sunulur.
- Rıza süreci aydınlatma + ayrı onay kutusu.
- Geri alma kolay (uygulama ayarlarından).

### 5.3. Rıza Metni Asgari Unsurlar

```
Bu kapsamda işlenecek biyometrik veriniz:
☐ Parmak izi şablonu (matematiksel hash)
☐ Yüz şablonu
☐ İris şablonu

İşleme amacı: ____________________
İşleme süresi: ____________________
Saklama biçimi: Şablon olarak (geri dönüştürülemez kriptografik dönüşüm),
                ham veri saklanmaz/silinir.

Alternatif yöntem: [kart / şifre / OTP] talep edebilirsiniz.

Açık rızamı vermek istiyorum: ☐ Evet ☐ Hayır
```

## 6. Şablon vs Ham Veri

### 6.1. Şablon (Template) Saklama

- Biyometrik özelliğin **matematiksel temsili** (vektör, hash, embedding).
- Tek yönlü dönüşüm — şablondan ham görüntü elde edilemez ideali.
- Modern sistemler şablon saklar (parmak izi minutiae, yüz embedding 128/512 boyutlu).

### 6.2. Ham Veri Saklama

- Parmak izi görüntüsü, yüz fotoğrafı, retina görüntüsü.
- **Kesinlikle önerilmez** — ihlal halinde geri alınamaz (parolanı değiştirebilirsin, yüzünü değiştiremezsin).
- Ham veri sadece ilk kayıt anında işlenir → şablon üretilir → ham veri **silinir**.

### 6.3. Şablonun Şifrelenmesi

- AES-256 GCM ile at-rest.
- Anahtar HSM (Hardware Security Module) veya KMS (Key Management Service).
- Anahtar rotation 12 ayda bir.
- Hesaplamalar şifreli ortamda mümkünse (homomorphic encryption — gelişmiş senaryo).

## 7. Sağlayıcı Seçimi

### 7.1. Tercih Kriterleri

- ISO/IEC 27001 + ISO/IEC 27701 (Privacy) sertifikası.
- ISO/IEC 19794 / 30107 (biyometrik standartlar) uyumu.
- FIDO Alliance, BSI, NIST sertifikaları.
- Türkiye'de yerleşik veri merkezi tercih (yurt dışı aktarım sorunu azalır).
- Kapalı kaynak değil — şeffaf işleyiş.
- Pen test + güvenlik denetim raporları.

### 7.2. DPA (Data Processing Agreement)

- KVKK m.12 uyumlu sözleşme.
- Veri işleyen yükümlülükleri.
- Alt-işleyen onay süreci.
- Veri sorumlusunun denetim hakkı.
- İhlal bildirim 24 saat içinde.
- Sözleşme sonu veri imha + sertifika.

## 8. Teknik Tedbirler

### 8.1. Çevrimiçi (Online) Karşılaştırma

- Şablonlar şifreli sunucuda.
- Karşılaştırma sunucu tarafında.
- Ağ TLS 1.3.
- API authentication + rate limit.

### 8.2. Cihaz Üstü (On-device)

- Şablon cihazda saklanır (smart card, mobile secure element).
- Sunucu sadece "match/no match" cevabını alır.
- Ağ riski en düşük; veri sorumlusu için **tercih edilir**.

### 8.3. Anti-spoofing

- Liveness detection (canlılık tespiti).
- 3D yüz tanıma (2D fotoğrafa dayanmaz).
- Parmak izi: nem/ısı/kapasitif sensör.
- Periyodik bypass testleri.

### 8.4. Yedekleme

- Şablon yedekleri **şifreli**.
- Yedekten geri yükleme audit'li.
- 3-2-1 strateji (3 kopya, 2 medya, 1 off-site).

## 9. İdari Tedbirler (Kurul 2018/10 Karar Maddeleri)

- Politika dokümanı (bu dosya).
- Yıllık eğitim — biyometrik veriye erişen tüm personel.
- Gizlilik sözleşmesi (NDA) — IT, İK, dış destek.
- Erişim matris (RBAC).
- Yetki gözden geçirme (çeyreklik).
- Ayrılan çalışan yetki iptali (24 saat).
- Erişim log denetimi.

## 10. Saklama Süresi

| Veri | Süre |
|------|------|
| Aktif çalışan şablonu | İş akdi süresince |
| Aktif müşteri şablonu | Hizmet süresince |
| Çalışan ayrıldıktan sonra | **Anında silme** (öner.); en geç 30 gün |
| Müşteri ilişki sonu | 30 gün içinde silme |
| Yedekler | Yedek rotasyon süresi |

İmha kanıtı (silme tutanağı) saklanır.

## 11. İlgili Kişi Hakları

- m.11/a-c: Hangi şablon hangi amaç → cevap basit.
- m.11/e: Silme talebi → hizmetten çıkış + alternatif yönteme geçiş ile aynı.
- m.11/f: Aktarım yapılmışsa bildirim.
- Şablon **kişiye geri verilemez** (matematiksel dönüşüm); ancak m.11/b kapsamında "şablon mevcut, X tarihinde oluşturuldu" bilgisi verilebilir.

## 12. Tipik Hatalar

| Hata | Doğru Yaklaşım |
|------|----------------|
| PDKS biyometrik tek seçenek | Alternatif (kart) zorunlu |
| Ham fotoğraf saklama | Şablon dönüşüm + ham silme |
| Açık rıza geri alma yok | Süreç tasarımı + alternatif |
| DPA yok / yetersiz | KVKK m.12 uyumlu sözleşme |
| Ayrılan çalışan şablonu kalıyor | 24 saat içinde silme |
| Şifrelenmemiş şablon | AES-256 + HSM |
| Anti-spoofing yok | Liveness zorunlu |
| Cihaz default parola | Değiştirme + MFA |
| DPIA yapılmamış | İlk kullanımdan önce zorunlu |
| Müşteri zorunlu biyometri | Alternatif sunulur |

## 13. KPI'lar

| KPI | Hedef |
|-----|-------|
| DPIA tamamlanma (her sistem) | %100 |
| Şablon şifreleme | %100 |
| Alternatif yöntem sunum oranı | %100 |
| Açık rıza geçerli oran | %100 |
| Ayrılan çalışan silme SLA | < 24 saat |
| Anti-spoofing test sıklığı | Yıllık 2 kez |
| Yetki gözden geçirme | Çeyreklik |

## 14. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi |
