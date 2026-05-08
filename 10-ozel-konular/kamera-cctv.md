---
Doküman / Document: Kamera ve CCTV Sistemleri Yönetimi / Camera and CCTV Systems Management
Bölüm / Section: 10-ozel-konular
Sahip / Owner: KVKK Sorumlusu + Güvenlik / İdari İşler + Bilgi Güvenliği / KVKK Officer + Security / Administrative Affairs + Information Security
Onaylayan / Approved by: Hukuk Müdürü + KVKK Komitesi / Head of Legal + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + Kurul kararlarına göre / Annual + per Authority decisions
İlgili Mevzuat / Legal Reference: Law No. 6698 (KVKK) Art. 5, 6; Law No. 5188 (Private Security); Law No. 4857 (Labor Law) Art. 5; Law No. 6331 (OHS); Constitutional Court rulings (E.2014/180); Authority decisions (notably 2018/52, 2019/315, etc.)
---

## English

# Camera and CCTV Systems Management

## 1. Purpose

To establish KVKK-compliant standards for the installation and operation of camera systems (CCTV, IP cam, license plate recognition, facial recognition, dashcam) used at the company's facilities, stores, warehouses, production areas, parking lots, and branches.

## 2. Legal Ground

### 2.1. General CCTV (For Security Purposes)

Evaluated under KVKK Art. 5(2):

- **Art. 5(2)(a) (express provision in laws):** Law No. 5188 on Private Security; BRSA regulations for ATM premises.
- **Art. 5(2)(f) (legitimate interest):** Workplace, asset security, theft prevention, life safety.

> **Explicit consent is NOT a suitable legal ground for CCTV.** Obtaining individual consent from everyone entering a camera area is impractical; furthermore the freedom of consent is debatable (the "they can choose not to enter" argument is weak in a workplace).

### 2.2. Employee Monitoring

Evaluated under KVKK + labor law:

- **Art. 5(2)(f) legitimate interest** + **proportionality test**.
- Constitutional Court decision E.2014/180: "The employer's right to monitor is not unlimited; employee privacy is protected."
- ECtHR Bărbulescu v. Romania (2017): Prior notice, reasonable measure, proportionality.

### 2.3. Customer Service / Advertising

Customer behavior analytics, heat maps, in-store personalized advertising -> **explicit consent** or **legitimate interest + DPIA**. If individual identification occurs, the requirement for explicit consent intensifies.

## 3. Disclosure Obligation

### 3.1. Two-Tier Disclosure

**Tier 1 - Sign / Sticker (KVKK Art. 10 + Authority expectation):**

A sign at the **entry point** and **field of view** of every recording area, containing:

```
VIDEO RECORDING IS IN PROGRESS

Data Controller: [Company Name]
Purpose: Security (asset/life/information)
Legal Ground: KVKK Art. 5(2)(f) (legitimate interest)
Retention: 30 days (extendable in case of incident)
Detailed Privacy Notice: [QR + URL]
Contact: kvkk@sirket.com.tr
```

Sign features:

- At least **A4 size** or readable from viewing distance.
- Symbol (eye/camera icon) - internationally recognized.
- Turkish + (where appropriate) English.
- Eye level or just above.

**Tier 2 - Detailed Privacy Notice (Web/QR):**

The full text reachable via QR code or URL:

- Data controller identity.
- Which areas/times are recorded.
- Whether image + audio is recorded.
- Recording purposes (memory dump).
- Retention + incident-extension rule.
- Transfer: to whom (police, courts, insurer), under what conditions.
- Data subject rights (Art. 11) + application channel.
- If facial / license-plate recognition is used, stated explicitly.

## 4. Location Restrictions (Forbidden Areas)

Under proportionality, privacy rights, and Constitutional Court interpretation **strictly forbidden**:

| Area | Reason |
|------|--------|
| Toilets, lavatories, showers | Core privacy area |
| Changing rooms | Same |
| Prayer / worship areas | Religious freedom (special category) |
| Lactation rooms, rest/sleep rooms | Privacy |
| Patient examination rooms | Health + privacy |
| Employee rest/dining areas | Continuous surveillance disproportionate (entry counters excluded) |

**Sensitive areas (only under limited conditions):**

- Cash desk, valuables area -> recording **yes**, but tight access.
- Production line employee monitoring -> proportionality test + prior notice + employment contract/protocol + union briefing.

## 5. Audio Recording

> **KVKK Authority position:** Audio recording **always requires a separate legal ground** in addition to video, and generally **explicit consent**.

- Call-center phone recordings -> statutory retention (Law 5651 traffic, 6502 consumer complaints) + disclosure + (in some cases) explicit consent.
- In-store audio recording -> as a rule, must not be done.
- Meeting recordings -> explicit consent of participants.

All audio-recorded areas need a **dedicated sign** and privacy notice.

## 6. Facial Recognition and Biometrics

Facial recognition -> **biometric data = special category (KVKK Art. 6(1))**. Detailed rules in `biometrik-veri.md`.

Summary:

- **Explicit consent** + DPIA + alternative-method assessment for facial recognition.
- "Anonymous" facial analysis (age/gender estimation without identification) is still risky; assess via DPIA against the risk of being deemed special category.
- Authority case law interprets facial recognition narrowly: "occupational safety" alone is not a sufficient ground.

## 7. License Plate Recognition (LPR)

- Plates are personal data (attributable to the owner).
- Parking entry/exit, speed violations, attendance -> may be legitimate interest; proportionality test required.
- Plate database retention: 30-90 days (by category).
- Blacklist sharing (cross-site blacklist) is a domestic transfer -> contract + disclosure.

## 8. Access Management

### 8.1. Viewing Permissions

| Role | Access |
|------|--------|
| Security shift | Live view + last 24 hours (role-based) |
| Security manager | Retroactive all recordings |
| Information Security | Access log + system administration |
| KVKK Officer | All recordings for audit (with audit approval) |
| Management | One-off access in case of incident (approved) |
| HR | In disciplinary case (Legal + KVKK approval) |
| Legal | In case of judicial process |
| Police | Court order / lawful request |
| Third party | FORBIDDEN (except for court order) |

### 8.2. Access Log

- Each viewing: who, when, which camera, which time range.
- Download/export: extra approval + log.
- Monthly access report to KVKK Committee.

### 8.3. Multi-Factor Authorization

Access to CCTV NVR/VMS systems:

- Active Directory integration.
- Mandatory MFA.
- Privileged Access Management (PAM) - JIT access.
- Privileged session recording.

## 9. Retention Period

### 9.1. Standard Period

| Category | Period |
|----------|--------|
| General security | **30 days** |
| High security (cash, R&D) | **90 days** |
| Incident/suspicious case | Until end of process + statute of limitations |
| Statutory obligation | As per legislation (BRSA, ATM, etc.) |

### 9.2. Extension in Case of Incident

- Theft, work accident, customer complaint, investigation -> the recording is held in a separate **incident dossier**.
- Marked with an "incident tag"; exempt from automatic deletion.
- "Incident-tagged" recordings reviewed in annual audit; unnecessary ones deleted.

### 9.3. Automatic Deletion

- **Cyclic recording (FIFO)** in the NVR/VMS system.
- Physical overwrite at end of retention.
- Manual deletions are logged.

## 10. Employee Monitoring - Sensitive Topic

### 10.1. Legal Framework

- KVKK Art. 5(2)(f) + proportionality.
- Labor Law Art. 5: employer's right to monitor.
- Constitutional Court E.2014/180 - measure test.
- ECtHR Bărbulescu (2017), López Ribalda v. Spain (2019).

### 10.2. Proportionality Criteria

For employer CCTV to be legitimate:

1. Has the employee been **given prior notice**?
2. Is there a **less-intrusive alternative**? (e.g., card instead of fingerprint)
3. Is monitoring **continuous or periodic**? (24/7 continuous monitoring is hard)
4. Is **data retention** limited?
5. Is **access** restricted?
6. Have **unions / employee representatives** been informed?

### 10.3. Consent vs. Employer Monitoring

- Cameras are **imposed on** the employee - explicit consent is problematic (not free).
- Legal ground should be legitimate interest + proportionality.
- Employees informed in employment contract + addendum.
- Use of CCTV for performance review is **highly sensitive**; high KVKK violation risk.

### 10.4. Forbidden Employee-Monitoring Practices

- Recording of toilets/rest areas.
- Continuous audio listening.
- Individual tracking via QR + location correlation.
- Hidden camera not communicated to the employee (illegal - Turkish Criminal Code crime + just-cause termination under labor law).
- Attendance via facial recognition (alternatives exist).

## 11. Third-Party Transfer

### 11.1. Police

- Footage is not provided absent a formal request + investigation/case information.
- Court order / prosecutor's instruction / urgent police record-based request.
- Transfer is logged.
- Data subject is not informed (confidentiality).

### 11.2. Insurer

- During damage / work-accident processes upon insurer's request.
- Contract + insurance policy + KVKK-compliant process.
- Data subject is informed where appropriate.

### 11.3. Third-Party Maintenance

- CCTV maintenance contractor -> processor agreement (KVKK Art. 12 + DPA).
- Access log + limited authorization.

## 12. CCTV Inventory

For each camera:

| Field | Content |
|-------|---------|
| Camera ID | CAM-XXX |
| Location | Building/floor/room + GPS |
| Type | IP, analog, dome, PTZ, dashcam, plate |
| Field of view | Description + photo |
| Resolution | Megapixel |
| Recording continuity | 24/7, motion, scheduled |
| Audio recording | Yes/No |
| Facial recognition | Yes/No |
| Retention | Days |
| NVR/VMS connection | System name |
| Disclosure sign | Yes/No |
| Responsible unit | Administrative / Security |
| Last audit date | YYYY-MM-DD |

> The inventory is included in the VERBİS notification.

## 13. Technical Measures

- NVR/VMS encrypted storage (AES-256 at rest).
- Network segmentation (CCTV on its own VLAN, no Internet egress).
- Default passwords changed (Hikvision, Dahua, Axis defaults are risky).
- Firmware regularly patched.
- Edge-device protection (USB ports disabled, physical lock).
- Cameras must be visible from the area they observe (no hidden cameras).

## 14. Data Subject Rights

### 14.1. Access Request (Art. 11(b))

- "I want my image from the store between Tuesday 14:00-15:00."
- The request is processed; however:
   - The person must be identified (clothing, store receipt, social-media photo, etc.).
   - Third parties are **masked** (face blur).
   - If retention has expired, the response is "deleted".
   - If in incident dossier, legal-process information is included.

### 14.2. Erasure Request (Art. 11(e))

- Already deleted in normal cycle.
- If in incident dossier, may be refused on legal grounds.

## 15. Common Mistakes

| Mistake | Correct approach |
|---------|------------------|
| No disclosure sign | One at every entry |
| Toilet camera | Forbidden - remove immediately |
| CCTV by explicit consent | Wrong legal ground - use legitimate interest |
| 6-month+ retention | 30 days standard; long retention without justification forbidden |
| Default passwords | Change + MFA |
| Recordings exposed via Internet | Network isolation |
| Hidden camera without notice | Turkish Criminal Code + labor law violations |
| Maintenance vendor unrestricted access | DPA + log + JIT |
| Facial recognition "for productivity" | DPIA + explicit consent |
| Audio recording with video by default | Separate legal ground |

## 16. KPIs

| KPI | Target |
|-----|--------|
| Disclosure-sign coverage | 100% |
| Default-password scan (every 3 months) | 0 |
| Cameras with access logs | 100% |
| Retention compliance | 100% |
| Annual DPIA (facial-recognition users) | 100% |

## 17. Version History

| Version | Date | Change | Approval |
|---------|------|--------|----------|
| 1.0 | 2026-05-08 | First publication | KVKK Committee |

---

## Türkçe

# Kamera ve CCTV Sistemleri Yönetimi

## 1. Amaç

Şirketimiz tesislerinde, mağazalarında, depolarında, üretim alanlarında, otoparklarında ve şubelerinde kullanılan kamera (CCTV, IP cam, plaka tanıma, yüz tanıma, dashcam) sistemlerinin KVKK uyumlu kurulum ve işletim standartlarını belirlemek.

## 2. Hukuki Sebep

### 2.1. Genel CCTV (Güvenlik Amaçlı)

KVKK m.5/2 kapsamında değerlendirilir:
- **m.5/2-a (kanunlarda öngörülmesi):** 5188 sayılı Özel Güvenlik Kanunu, ATM tesisinde BDDK düzenlemeleri.
- **m.5/2-f (meşru menfaat):** İşyeri, mal güvenliği, hırsızlık önleme, can güvenliği.

> **Açık rıza CCTV için uygun bir hukuki sebep DEĞİLDİR.** Kamera alanına giren herkesten ayrı ayrı rıza alınması pratik değildir; ayrıca rıza özgürlüğü tartışmalıdır (girmek istemiyorsa girmez argümanı işyeri için zayıftır).

### 2.2. Çalışan İzleme Amaçlı

KVKK + İş Hukuku birlikte değerlendirilir:
- **m.5/2-f meşru menfaat** + **ölçülülük testi**.
- AYM 2014/180 sayılı kararı: "İşveren denetim hakkı sınırsız değildir; çalışan mahremiyeti korunur."
- ECtHR Bărbulescu v. Romania (2017): Çalışan izleme önceden bildirim, makul ölçü, proportionality.

### 2.3. Müşteri Hizmetleri / Reklam

Müşteri davranışı analizi, ısı haritası, mağaza içi kişiselleştirilmiş reklam → **açık rıza** veya **meşru menfaat + DPIA**. Kişi tanımlama yapılıyorsa açık rıza zorunluluğu güçlenir.

## 3. Aydınlatma Yükümlülüğü

### 3.1. İki Katmanlı Aydınlatma

**Katman 1 — Tabela / Sticker (KVKK m.10 + Kurul beklentisi):**

Görüntü kayıt yapılan her bölgenin **giriş noktasında** ve **görüş alanına** aşağıdakileri içeren tabela:

```
KAMERA İLE GÖRÜNTÜ KAYDI YAPILMAKTADIR

Veri Sorumlusu: [Şirket Adı] A.Ş.
Amaç: Güvenlik (mal-can-bilgi)
Hukuki Sebep: KVKK m.5/2-f (meşru menfaat)
Saklama: 30 gün (olay halinde uzatılabilir)
Detaylı Aydınlatma Metni: [QR + URL]
İletişim: kvkk@sirket.com.tr
```

Tabela özellikleri:
- En az **A4 boyutu** veya görüş mesafesinden okunabilir.
- Sembol (göz/kamera ikonu) — uluslararası tanınır.
- Türkçe + (uygunsa) İngilizce.
- Yüksekliği göz hizasında veya hemen üstünde.

**Katman 2 — Detaylı Aydınlatma Metni (Web/QR):**

QR kod veya URL ile ulaşılan tam metin:
- Veri sorumlusu kimliği.
- Hangi alanlar/saatlerde kayıt.
- Görüntü + ses kaydı yapılıp yapılmadığı.
- Kayıt amaçları (bellek dökümü).
- Saklama süresi + olay durumu uzatma kuralı.
- Aktarım: kimlere (kolluk, mahkeme, sigortacı), hangi şartla.
- İlgili kişi hakları (m.11) + başvuru kanalı.
- Yüz tanıma / plaka tanıma kullanılıyorsa açıkça belirtilir.

## 4. Konum Sınırlaması (Yasak Alanlar)

KVKK ölçülülük + mahremiyet hakkı + AYM yorumu çerçevesinde **kesinlikle yasak**:

| Alan | Gerekçe |
|------|---------|
| Tuvalet, lavabo, duş | Mahremiyet hakkı çekirdek alan |
| Soyunma odaları | Aynı |
| Mescit / ibadet alanı | Din özgürlüğü (özel nitelikli veri) |
| Süt sağma odası, dinlenme/yatma odası | Mahremiyet |
| Hasta muayene odası | Sağlık + mahremiyet |
| Çalışan dinlenme/yemek alanı | Sürekli izleme orantısız (acil/giriş ölçer hariç) |

**Hassas alanlar (sadece sınırlı koşulda):**
- Kasa, değerli eşya bölgesi → kayıt **evet** ama erişim sıkı.
- Üretim hattı çalışan denetimi → orantı testi + ön bildirim + iş sözleşmesi/ek protokol + sendika bilgilendirme.

## 5. Ses Kaydı

> **KVKK Kurul tutumu:** Görüntüye ek olarak ses kaydı **kesinlikle ayrı hukuki sebep** ve genelde **açık rıza** gerektirir.

- Çağrı merkezi telefon kayıtları → yasal saklama (5651 trafik, 6502 tüketici şikayeti) + aydınlatma + (bazı durumlarda) açık rıza.
- Mağaza içi ses kaydı → kural olarak yapılmamalı.
- Toplantı kayıtları → katılımcıların açık rızası.

Tüm ses kaydı yapılan alanlarda **ek tabela** ve aydınlatma metni.

## 6. Yüz Tanıma ve Biyometrik

Yüz tanıma → **biyometrik veri = özel nitelikli (KVKK m.6/1)**. Detaylı kurallar `biometrik-veri.md` dosyasında.

Özet:
- Yüz tanıma için **açık rıza** + DPIA + alternatif değerlendirme zorunlu.
- "Anonim" yüz analizi (yaş/cinsiyet tahmini, kişi tanımlamadan) bile risklidir; özel nitelikli veri sayılma riskine karşı DPIA ile değerlendirilir.
- Kurul içtihatı yüz tanımayı dar yorumlar: "iş güvenliği" tek başına yeterli sebep değildir.

## 7. Plaka Tanıma (LPR)

- Plaka kişisel veridir (sahibe atfedilebilir).
- Otopark giriş-çıkış, hız ihlali, devamsızlık → meşru menfaat olabilir; ölçülülük testi yapılır.
- Plaka veri tabanı saklama süresi: 30-90 gün (kategoriye göre).
- Kara liste paylaşımı (siteler arası blacklist) yurt içi aktarım sayılır → sözleşme + aydınlatma.

## 8. Erişim Yönetimi

### 8.1. Görüntüleme Yetkisi

| Rol | Erişim |
|-----|--------|
| Güvenlik vardiya | Canlı izleme + son 24 saat (rol bazlı) |
| Güvenlik müdürü | Geriye dönük tüm kayıtlar |
| Bilgi Güvenliği | Erişim logu + sistem yönetimi |
| KVKK Sorumlusu | Denetim için tüm kayıtlar (denetim onayı ile) |
| Yönetim | Olay halinde tek seferlik (onaylı) |
| İK | Disiplin halinde (Hukuk + KVKK onayı) |
| Hukuk | Adli süreç halinde |
| Kolluk kuvvetleri | Mahkeme kararı / kanuni talep ile |
| Üçüncü taraf | YASAK (mahkeme kararı hariç) |

### 8.2. Erişim Logu

- Her görüntüleme: kim, ne zaman, hangi kamera, hangi saat aralığı.
- İndirme/dışa aktarma: ek onay + log.
- Aylık erişim raporu KVKK Komitesi'ne.

### 8.3. Çift Faktörlü Yetkilendirme

CCTV NVR/VMS sistemlerine erişim:
- Active Directory entegrasyonu.
- MFA zorunlu.
- Privileged Access Management (PAM) — JIT erişim.
- Oturum kaydı (privileged session recording).

## 9. Saklama Süresi

### 9.1. Standart Süre

| Kategori | Süre |
|----------|------|
| Genel güvenlik | **30 gün** |
| Yüksek güvenlik (kasa, ARGE) | **90 gün** |
| Olay/şüpheli durum | Olay süreci sonu + zamanaşımı |
| Yasal zorunluluk | Mevzuata göre (BDDK, ATM, vb.) |

### 9.2. Olay Halinde Uzatma

- Hırsızlık, iş kazası, müşteri şikayeti, soruşturma → ilgili kayıt **olay dosyasına** ayrı saklanır.
- "Olay etiketi" ile işaretlenir; otomatik silmeden istisna.
- Yıllık denetimde "olay etiketli" kayıtlar incelenir, gereksiz olanlar silinir.

### 9.3. Otomatik Silme

- NVR/VMS sistemde **döngüsel kayıt** (FIFO).
- Saklama süresi sonunda fiziksel üzerine yazma.
- Manuel silinen kayıtlar log'lanır.

## 10. Çalışan İzleme — Hassas Konu

### 10.1. Yasal Çerçeve

- KVKK m.5/2-f + ölçülülük.
- 4857 m.5 işveren denetim hakkı.
- AYM E.2014/180 ölçü testi.
- ECtHR Bărbulescu (2017), López Ribalda v. Spain (2019).

### 10.2. Ölçülülük Kriteri

İşveren CCTV'si meşru ise:
1. **Önceden bildirim** çalışana yapılmış mı?
2. **Daha az müdahaleci** alternatif var mı? (parmak izi yerine kart, vb.)
3. **Sürekli mi, dönemsel mi**? (24/7 sürekli izleme zorlu)
4. **Veri saklama** sınırlı mı?
5. **Erişim** kısıtlı mı?
6. **Sendika / çalışan temsilcileri** bilgilendirildi mi?

### 10.3. Onay vs İşveren Denetim

- Kamera çalışana **dayatılır** — açık rıza problemli (özgür değil).
- Hukuki sebep meşru menfaat + ölçülülük olmalı.
- Çalışan iş sözleşmesinde + ek protokolde aydınlatılır.
- Performans değerlendirmesi için CCTV kullanımı **çok hassas**, KVKK ihlali riski yüksek.

### 10.4. Yasak Çalışan İzleme Pratikleri

- Tuvalet/dinlenme alanı kaydı.
- Sürekli ses dinleme.
- Karekod ile bireysel takip + lokasyon korelasyonu.
- Çalışana bildirilmeden gizli kamera (illegal — TCK suç + iş hukuku haklı sebepli fesih).
- Yüz tanıma ile devamsızlık (alternatif yöntem var).

## 11. Üçüncü Taraf Aktarımı

### 11.1. Kolluk Kuvvetleri

- Resmî yazı + soruşturma/dava bilgisi olmaksızın görüntü verilmez.
- Mahkeme kararı / savcılık talimatı / acil durumda emniyet tutanaklı talep.
- Aktarım kaydı tutulur.
- Veri sahibine (gizlilik gereği) bildirim yapılmaz.

### 11.2. Sigortacı

- Hasar/iş kazası sürecinde sigortacı talebi.
- Sözleşme + sigorta poliçesi + KVKK uyumlu süreç.
- İlgili kişi gerektiğinde aydınlatılır.

### 11.3. Üçüncü Taraf Bakım

- CCTV bakım yüklenicisi → veri işleyen sözleşmesi (KVKK m.12 + DPA).
- Erişim logu + sınırlı yetki.

## 12. CCTV Envanteri

Her kamera için kayıt:

| Alan | İçerik |
|------|--------|
| Kamera ID | CAM-XXX |
| Lokasyon | Bina/kat/oda + GPS |
| Tip | IP, analog, dome, PTZ, dashcam, plaka |
| Görüş alanı | Açıklayıcı + fotoğraf |
| Çözünürlük | Megapiksel |
| Kayıt sürekliliği | 24/7, hareket, programlı |
| Ses kaydı | Var/Yok |
| Yüz tanıma | Var/Yok |
| Saklama süresi | Gün |
| NVR/VMS bağlantısı | Sistem adı |
| Aydınlatma tabelası | Var/Yok |
| Sorumlu birim | İdari İşler / Güvenlik |
| Son denetim tarihi | YYYY-AA-GG |

> Envanter VERBİS bildirimine dahil edilir.

## 13. Teknik Tedbirler

- NVR/VMS şifreli depolama (AES-256 at rest).
- Network segmentasyonu (CCTV ayrı VLAN, Internet erişimi yok).
- Default parolalar değiştirilir (Hikvision, Dahua, Axis defaultları riskli).
- Firmware düzenli yamalı.
- Edge cihaz koruması (USB port disable, fiziksel kilit).
- Kamera kameranın gördüğü alandan görünür olmalı (gizli kamera değil).

## 14. İlgili Kişi Hakları

### 14.1. Erişim Talebi (m.11/b)

- "Geçen Salı 14:00-15:00 arası mağazadaki görüntümü istiyorum."
- Talep işlenir; ancak:
   - Kişi tanımlanmalı (kıyafet, mağaza fişi, sosyal medya foto vb.).
   - Üçüncü kişiler **maskelenmiş** (yüz blur).
   - Saklama süresi geçmişse "silindi" cevap.
   - Olay dosyasında ise hukuki süreç bilgisi.

### 14.2. Silme Talebi (m.11/e)

- Standart döngüde zaten silinir.
- Olay dosyasındaysa hukuki gerekçe ile reddedilebilir.

## 15. Tipik Hatalar

| Hata | Doğru Yaklaşım |
|------|----------------|
| Aydınlatma tabelası yok | Her giriş noktasına |
| Tuvalet kamerası | Yasak — anında kaldır |
| Açık rıza ile CCTV | Hukuki sebep yanlış — meşru menfaat |
| Saklama 6 ay+ | 30 gün standart, gerekçesiz uzun yasak |
| Default parola | Değiştirme + MFA |
| Kayıtlar internet üzerinden açık | Network izolasyon |
| Çalışana bildirimsiz gizli kamera | TCK + iş hukuku ihlali |
| Bakım yüklenicisi sınırsız erişim | DPA + log + JIT |
| Yüz tanıma "verimlilik için" | DPIA + açık rıza |
| Ses kaydı görüntü ile birlikte default | Ayrı hukuki sebep |

## 16. KPI'lar

| KPI | Hedef |
|-----|-------|
| Aydınlatma tabelası kapsam | %100 |
| Default parola tarama (3 ayda bir) | 0 |
| Erişim loguna sahip kamera | %100 |
| Saklama süresine uyum | %100 |
| Yıllık DPIA (yüz tanıma kullananlar) | %100 |

## 17. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi |
