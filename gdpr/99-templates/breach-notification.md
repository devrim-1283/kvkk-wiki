---
title:
  en: "Breach Notification — Article 33 Form and Internal Triage"
  tr: "Ihlal Bildirimi — Madde 33 Formu ve Ic Triyaj"
section: "99-templates"
owner: "DPO / CISO"
version: "1.0"
last_review: "2026-05-08"
next_review: "2026-11-08"
classification: "Confidential when populated"
languages: ["en", "tr"]
keywords:
  en: ["breach notification", "Article 33", "Article 34", "72 hours"]
  tr: ["ihlal bildirimi", "Madde 33", "Madde 34", "72 saat"]
---

## English

# Breach Notification — Article 33 Form and Internal Triage

This template provides:
- An internal triage form to assess incidents and decide on Article 33/34 obligations.
- A formal Article 33 notification form for the supervisory authority.
- A communication template for affected data subjects under Article 34 where high risk.

EDPB Guidelines 9/2022 (and 01/2021 examples) followed.

---

## Part 1 — Internal Triage Form

Complete within hours of becoming aware. Drives the 72-hour clock under Article 33(1).

### Section 1.1 — Incident identification

| Field | Value |
|-------|-------|
| Incident ID | [INC-YYYY-NNN] |
| Incident type | [confidentiality / integrity / availability — pick one or more] |
| Date and time of occurrence (best estimate) | [ISO-8601] |
| Date and time of awareness | [ISO-8601] |
| Awareness via | [SIEM alert / employee report / customer report / processor / SA / other] |
| 72-hour deadline (Art. 33(1)) | [ISO-8601] |
| Incident lead | [name] |
| Initial severity | [low / medium / high / critical] |

### Section 1.2 — Scope assessment

| Field | Value |
|-------|-------|
| Affected systems | [list] |
| Affected processing activities (ROPA refs) | [list] |
| Affected categories of data subjects | [customers / employees / minors / patients / other] |
| Approximate number of data subjects | [number or range] |
| Categories of personal data | [identity / contact / financial / health / biometric / location / other] |
| Special category data involved? | [Y/N + categories] |
| Children involved? | [Y/N] |
| Cross-border processing? | [Y/N] |

### Section 1.3 — Impact assessment

| Field | Value |
|-------|-------|
| Likely consequences | [unauthorized access, alteration, destruction, loss] |
| Risk to rights and freedoms | [low / medium / high / very high] |
| Identifiability of affected individuals | [pseudonymous / direct / indirect] |
| Volume × sensitivity matrix | [score] |
| Considerations | [identity theft, financial loss, discrimination, reputational damage, distress] |

### Section 1.4 — Notification decision

Based on EDPB Guidelines 9/2022:

- **Notifiable to SA under Art. 33?** [Y/N]
  - **No** only if "unlikely to result in a risk to the rights and freedoms of natural persons." Document reasoning.
- **Notifiable to data subjects under Art. 34?** [Y/N]
  - **Yes** if "high risk" — unless 34(3) exemption applies (encryption rendering unintelligible, subsequent measures, disproportionate effort with public communication).
- **Lead SA identified?** [SA name]
- **Concerned SAs?** [list]

### Section 1.5 — Containment and remediation actions

| Action | Owner | Status | Date |
|--------|-------|--------|------|
| Disable affected accounts/credentials | Security | | |
| Patch / configuration change | Engineering | | |
| Restore from backup | Operations | | |
| Block external IPs | Network | | |
| Notify processor / sub-processor if origin | Procurement / DPO | | |
| Engage forensics (if needed) | CISO | | |
| Preserve evidence | CISO | | |

### Section 1.6 — Legal hold

Legal hold initiated: [Y/N]; scope: [systems and custodians]; date: [date]; release: [criteria].

### Section 1.7 — Communications plan

| Audience | Trigger | Channel | Owner |
|----------|---------|---------|-------|
| Executive committee | Critical/High | Verbal + written | DPO |
| Audit committee | Critical | Written | DPO |
| Affected processor | If applicable | Email + call | Procurement |
| Insurer | If notifiable claim | Notification of circumstance | Risk |
| Outside counsel | If pre-litigation | Privileged channel | Legal |
| Media | If public disclosure required | Statement | Communications |

---

## Part 2 — Article 33 SA Notification

Submit to lead SA (and concerned SAs as applicable) within 72 hours of awareness, or with reasoned delay per Article 33(1) second sentence.

### Notification contents per Article 33(3)

#### A. Nature of the breach

- Categories and approximate number of data subjects concerned: [number or range].
- Categories and approximate number of personal data records concerned: [number or range].
- Description of the breach: [factual narrative; how, when, what].

#### B. Name and contact details of DPO

- DPO name: [name]
- DPO email: [email]
- DPO telephone: [number]
- Alternative contact (if no DPO): [contact]

#### C. Likely consequences of the breach

- [List likely consequences considering categories of data, volume, identifiability, downstream uses.]

#### D. Measures taken or proposed

- Containment: [actions taken]
- Remediation: [actions]
- Mitigation for data subjects: [actions]

### Optional — additional information

- Data subject notification status (Article 34): [done / planned / not required]
- Other regulators notified: [NIS2 CSIRT, sector regulator]
- Cross-border processing — lead SA, concerned SAs: [list]

### Submission

| Field | Value |
|-------|-------|
| Submission method | [SA online portal / email / letter] |
| Submitted by | [name, role] |
| Date and time of submission | [ISO-8601] |
| Reference number assigned | [SA reference] |

### Phased reporting

Where information is not yet available, submit a preliminary notification within 72 hours and follow up in phases per Article 33(4) and EDPB Guidelines 9/2022. Document each phase.

---

## Part 3 — Article 34 Communication to Data Subjects

Where the breach is likely to result in **high risk** to rights and freedoms, communicate to affected data subjects without undue delay, in clear and plain language.

### Communication contents per Article 34(2)

#### Subject line example

"Important security notice regarding your [service / account]"

#### Body — bilingual recommended where data subject base is multilingual

Dear [Name],

We are writing to inform you of a personal data breach affecting you. We deeply regret this incident and want to be transparent about what happened, what data was involved, what we are doing, and what you can do.

**What happened:** On [date], we became aware that [factual description in plain language].

**What data was involved:** The breach affected the following categories of your data:

- [list categories — be specific]

**What we are doing:**

- [containment]
- [remediation]
- [monitoring]
- [cooperation with authorities]
- [credit monitoring offered if appropriate]

**What you can do:**

- [change password]
- [be vigilant for phishing]
- [monitor accounts]
- [contact us]

**Who to contact:**

- DPO: [name and email]
- Helpline: [number, hours, languages]
- Privacy Notice: [URL]

**Your rights:**

You have the right to lodge a complaint with [SA name and contact].

We sincerely apologise. We are committed to protecting your data and will continue to update you as appropriate.

[Signature, role]
[Date]

### Channels

| Channel | When |
|---------|------|
| Email to known address | Default if held |
| Postal letter | If no current email or email failed |
| In-product banner | Account-based services |
| Public communication / media | Per Art. 34(3)(c) where individual contact disproportionate |

### Article 34(3) exemptions

Communication to data subjects not required where:

- (a) Appropriate technical and organisational protection measures (e.g. encryption) rendered the data unintelligible to unauthorised persons.
- (b) Subsequent measures ensure the high risk is no longer likely to materialise.
- (c) Direct communication would involve disproportionate effort — public communication or similar measures used instead.

Document the chosen exemption and reasoning.

---

## Part 4 — Internal Breach Register (Article 33(5))

Maintain a register of all personal data breaches, regardless of notification.

### Register fields

| Field | Description |
|-------|-------------|
| Breach ID | [INC-YYYY-NNN] |
| Date of awareness | [ISO-8601] |
| Date of occurrence | [ISO-8601 estimate] |
| Description | [summary] |
| Categories of data | [list] |
| Categories of subjects and approx number | [list] |
| Cause | [root cause from RCA] |
| Effect | [consequences] |
| Notification to SA? | [Y/N + reference] |
| Notification to subjects? | [Y/N + reference] |
| Containment date | [ISO-8601] |
| Lessons learned action items | [CAPA refs] |
| Closure date | [ISO-8601] |

The register is reviewed quarterly. Trends inform training and control improvement.

---

## Türkçe

# İhlal Bildirimi — Madde 33 Formu ve İç Triyaj

Bu şablon şunları sağlar:
- Olayları değerlendirmek ve Madde 33/34 yükümlülüklerine karar vermek için bir iç triyaj formu.
- Denetim otoritesine resmi Madde 33 bildirim formu.
- Yüksek risk durumunda Madde 34 altında etkilenen ilgili kişiler için bir iletişim şablonu.

EDPB Kılavuzu 9/2022 (ve 01/2021 örnekleri) izlenir.

---

## Bölüm 1 — İç Triyaj Formu

Farkına varmanın saatleri içinde tamamlayın. Madde 33(1) altında 72 saatlik sayacı yönetir.

### Bölüm 1.1 — Olay tanımlama

| Alan | Değer |
|------|-------|
| Olay ID | [INC-YYYY-NNN] |
| Olay türü | [gizlilik / bütünlük / erişilebilirlik — bir veya daha fazlasını seçin] |
| Oluşum tarihi ve saati (en iyi tahmin) | [ISO-8601] |
| Farkındalık tarihi ve saati | [ISO-8601] |
| Farkındalık aracılığı | [SIEM uyarısı / çalışan raporu / müşteri raporu / işleyen / SA / diğer] |
| 72 saat son tarih (Md. 33(1)) | [ISO-8601] |
| Olay lideri | [ad] |
| Başlangıç ciddiyeti | [düşük / orta / yüksek / kritik] |

### Bölüm 1.2 — Kapsam değerlendirmesi

| Alan | Değer |
|------|-------|
| Etkilenen sistemler | [liste] |
| Etkilenen işleme faaliyetleri (ROPA referansları) | [liste] |
| Etkilenen ilgili kişi kategorileri | [müşteriler / çalışanlar / küçükler / hastalar / diğer] |
| İlgili kişi yaklaşık sayısı | [sayı veya aralık] |
| Kişisel veri kategorileri | [kimlik / iletişim / finansal / sağlık / biyometrik / konum / diğer] |
| Özel kategori veri dahil mi? | [E/H + kategoriler] |
| Çocuklar dahil mi? | [E/H] |
| Sınır ötesi işleme? | [E/H] |

### Bölüm 1.3 — Etki değerlendirmesi

| Alan | Değer |
|------|-------|
| Olası sonuçlar | [yetkisiz erişim, değişiklik, imha, kayıp] |
| Hak ve özgürlüklere risk | [düşük / orta / yüksek / çok yüksek] |
| Etkilenen bireylerin tanımlanabilirliği | [takma adlı / doğrudan / dolaylı] |
| Hacim × hassasiyet matrisi | [skor] |
| Değerlendirmeler | [kimlik hırsızlığı, finansal kayıp, ayrımcılık, itibar zararı, sıkıntı] |

### Bölüm 1.4 — Bildirim kararı

EDPB Kılavuzu 9/2022 esasına göre:

- **Md. 33 altında SA'ya bildirilebilir mi?** [E/H]
  - **Hayır** yalnızca "gerçek kişilerin hak ve özgürlüklerine risk oluşturmasının olası olmadığı" durumda. Gerekçeyi belgeleyin.
- **Md. 34 altında ilgili kişilere bildirilebilir mi?** [E/H]
  - **Evet** "yüksek risk" varsa — 34(3) istisnası uygulanmadıkça (şifreleme anlaşılmaz hale getirme, sonraki tedbirler, kamu iletişimiyle orantısız çaba).
- **Öncü SA tanımlandı mı?** [SA adı]
- **İlgili SA'lar?** [liste]

### Bölüm 1.5 — Kontrol altına alma ve düzeltme eylemleri

| Eylem | Sahip | Durum | Tarih |
|-------|-------|-------|-------|
| Etkilenen hesap/kimlik bilgilerini devre dışı bırak | Güvenlik | | |
| Yama / konfigürasyon değişikliği | Mühendislik | | |
| Yedekten geri yükleme | Operasyonlar | | |
| Dış IP'leri engelle | Ağ | | |
| Köken ise işleyene / alt işleyene bildir | Satın alma / DPO | | |
| Adli (gerekirse) dahil et | CISO | | |
| Kanıt sakla | CISO | | |

### Bölüm 1.6 — Hukuki tutma

Hukuki tutma başlatıldı: [E/H]; kapsam: [sistemler ve sorumlular]; tarih: [tarih]; serbest bırakma: [kriterler].

### Bölüm 1.7 — İletişim planı

| Kitle | Tetikleyici | Kanal | Sahip |
|-------|-------------|-------|-------|
| Yürütme komitesi | Kritik/Yüksek | Sözlü + yazılı | DPO |
| Denetim komitesi | Kritik | Yazılı | DPO |
| Etkilenen işleyen | Uygulanırsa | E-posta + arama | Satın alma |
| Sigortacı | Bildirilebilir talep ise | Durum bildirimi | Risk |
| Dış danışman | Dava öncesi ise | Ayrıcalıklı kanal | Hukuk |
| Medya | Kamu açıklaması gerekirse | Beyan | İletişim |

---

## Bölüm 2 — Madde 33 SA Bildirimi

Farkındalığın 72 saati içinde öncü SA'ya (ve uygulanabilir ilgili SA'lara) gönderin veya Madde 33(1) ikinci cümlesi uyarınca gerekçeli gecikmeyle.

### Madde 33(3) uyarınca bildirim içeriği

#### A. İhlalin niteliği

- İlgili ilgili kişi kategorileri ve yaklaşık sayısı: [sayı veya aralık].
- İlgili kişisel veri kayıt kategorileri ve yaklaşık sayısı: [sayı veya aralık].
- İhlalin tanımı: [olgusal anlatım; nasıl, ne zaman, ne].

#### B. DPO ad ve iletişim bilgileri

- DPO adı: [ad]
- DPO e-posta: [e-posta]
- DPO telefon: [numara]
- Alternatif iletişim (DPO yoksa): [iletişim]

#### C. İhlalin olası sonuçları

- [Veri kategorileri, hacim, tanımlanabilirlik, sonraki kullanımları dikkate alarak olası sonuçları listele.]

#### D. Alınan veya önerilen tedbirler

- Kontrol altına alma: [alınan eylemler]
- Düzeltme: [eylemler]
- İlgili kişiler için azaltma: [eylemler]

### İsteğe bağlı — ek bilgi

- İlgili kişi bildirim durumu (Madde 34): [yapıldı / planlandı / gerekli değil]
- Bildirilen diğer düzenleyiciler: [NIS2 CSIRT, sektör düzenleyicisi]
- Sınır ötesi işleme — öncü SA, ilgili SA'lar: [liste]

### Sunum

| Alan | Değer |
|------|-------|
| Sunum yöntemi | [SA çevrimiçi portalı / e-posta / mektup] |
| Sunan | [ad, rol] |
| Sunum tarihi ve saati | [ISO-8601] |
| Atanan referans numarası | [SA referansı] |

### Aşamalı raporlama

Bilgi henüz mevcut değilse, 72 saat içinde ön bildirim sunun ve Madde 33(4) ile EDPB Kılavuzu 9/2022 uyarınca aşamalarla takip edin. Her aşamayı belgeleyin.

---

## Bölüm 3 — İlgili Kişilere Madde 34 İletişimi

İhlalin hak ve özgürlüklere **yüksek risk** oluşturma olasılığı varsa, etkilenen ilgili kişilere gecikmeksizin, açık ve sade dilde iletin.

### Madde 34(2) uyarınca iletişim içeriği

#### Konu satırı örneği

"[Hizmet / hesap] hakkında önemli güvenlik bildirimi"

#### Gövde — ilgili kişi tabanı çok dilli olduğunda iki dilli önerilir

Sayın [Ad],

Sizi etkileyen bir kişisel veri ihlalini bildirmek için yazıyoruz. Bu olaydan derin üzüntü duyuyoruz ve neyin olduğu, hangi verinin dahil olduğu, ne yaptığımız ve ne yapabileceğiniz konusunda şeffaf olmak istiyoruz.

**Ne oldu:** [Tarihte], [olgusal sade dil açıklaması] olduğunun farkına vardık.

**Hangi veriler dahildi:** İhlal verilerinizin aşağıdaki kategorilerini etkiledi:

- [kategorileri listele — belirli ol]

**Ne yapıyoruz:**

- [kontrol altına alma]
- [düzeltme]
- [izleme]
- [otoritelerle işbirliği]
- [uygunsa kredi izleme sunulur]

**Ne yapabilirsiniz:**

- [parolayı değiştir]
- [kimlik avına karşı dikkatli ol]
- [hesapları izle]
- [bizimle iletişime geç]

**Kiminle iletişim kuracaksınız:**

- DPO: [ad ve e-posta]
- Yardım hattı: [numara, saatler, diller]
- Aydınlatma metni: [URL]

**Haklarınız:**

[SA adı ve iletişim] adresine şikayette bulunma hakkınız vardır.

İçtenlikle özür dileriz. Verilerinizi korumaya kararlıyız ve uygun şekilde sizi güncellemeye devam edeceğiz.

[İmza, rol]
[Tarih]

### Kanallar

| Kanal | Ne zaman |
|-------|----------|
| Bilinen adrese e-posta | Tutuluyorsa varsayılan |
| Posta mektubu | Mevcut e-posta yoksa veya e-posta başarısızsa |
| Ürün içi banner | Hesap tabanlı hizmetler |
| Kamu iletişimi / medya | Bireysel iletişim orantısız olduğunda Md. 34(3)(c) uyarınca |

### Madde 34(3) istisnaları

İlgili kişilere iletişim şu durumlarda gerekli değildir:

- (a) Uygun teknik ve idari koruma tedbirleri (örn. şifreleme) veriyi yetkisiz kişiler için anlaşılmaz hale getirdi.
- (b) Sonraki tedbirler yüksek riskin gerçekleşme olasılığının kalmadığını sağlar.
- (c) Doğrudan iletişim orantısız çaba içerirdi — bunun yerine kamu iletişimi veya benzeri tedbirler kullanıldı.

Seçilen istisnayı ve gerekçeyi belgeleyin.

---

## Bölüm 4 — İç İhlal Kayıt Defteri (Madde 33(5))

Bildirimden bağımsız olarak tüm kişisel veri ihlallerinin kaydını tutun.

### Kayıt defteri alanları

| Alan | Açıklama |
|------|----------|
| İhlal ID | [INC-YYYY-NNN] |
| Farkındalık tarihi | [ISO-8601] |
| Oluşum tarihi | [ISO-8601 tahmin] |
| Açıklama | [özet] |
| Veri kategorileri | [liste] |
| Sahip kategorileri ve yaklaşık sayı | [liste] |
| Sebep | [RCA'dan kök neden] |
| Etki | [sonuçlar] |
| SA'ya bildirim? | [E/H + referans] |
| Sahiplere bildirim? | [E/H + referans] |
| Kontrol altına alma tarihi | [ISO-8601] |
| Çıkarılan dersler eylem öğeleri | [DÖEP referansları] |
| Kapanış tarihi | [ISO-8601] |

Kayıt defteri çeyreklik gözden geçirilir. Trendler eğitim ve kontrol iyileştirmesini bilgilendirir.
