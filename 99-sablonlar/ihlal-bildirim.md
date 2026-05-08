---
Doküman / Document: Veri İhlali Bildirim Şablonları (Kurul ve İç Triyaj) / Data Breach Notification Templates (Authority + Internal Triage)
Bölüm / Section: 99-sablonlar
Sahip / Owner: KVKK Sorumlusu + Hukuk Müşavirliği — KVKK Officer + Legal Counsel
Onaylayan / Approved by: KVKK Komitesi — KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş — Annual + triggered
İlgili Mevzuat / Legal Reference: 6698 sayılı KVKK m.12/5; KVKK Kurulu 24.01.2019 tarihli ve 2019/10 sayılı Karar — KVKK Art. 12/5; Authority Decision No. 2019/10 dated 24.01.2019
---

## English

# Data Breach Notification Templates

## 1. Time Discipline

| Step | Time |
|------|------|
| Suspected breach detected | T0 |
| Internal triage complete | T0 + 6 hours |
| KVKK Committee (crisis) informed | T0 + 12 hours |
| Authority notification draft ready | T0 + 36 hours |
| Final sign-off by Legal + KVKK Officer | T0 + 60 hours |
| Authority notification sent | T0 + 72 hours (latest) |
| Notification to data subjects (as soon as possible) | T0 + 7 days (target) |

> Notification to the Authority later than 72 hours requires **written reasons for delay** (Authority Decision 2019/10).

The Turkish text below is the binding form. The English versions are parallel deployment material.

---

## 2. TEMPLATE A — INTERNAL TRIAGE FORM (English equivalent)

```
==========================================================
DATA BREACH INTERNAL TRIAGE FORM
==========================================================

Breach Reference No: IH-[YEAR]-[SEQ]
Drafting Date/Time: [DATE TIME]
Drafted by: [NAME - ROLE]

A. SOURCE OF SUSPECTED BREACH
[ ] SOC / SIEM alert
[ ] Employee report
[ ] Supplier report
[ ] Data subject complaint
[ ] Media / third party
[ ] Internal audit
[ ] Other: ___________________

B. INITIAL DETECTION
- Detection date/time (T0):
- Estimated breach occurrence date:
- Lag between occurrence and detection (MTTD):
- Detected by:

C. NATURE OF THE BREACH (KVKK Art. 12/5 and Authority 2019/10)
[ ] Confidentiality breach (unauthorised disclosure, leak)
[ ] Integrity breach (unauthorised alteration, corruption)
[ ] Availability breach (loss, deletion, ransom, service outage)
[ ] Multiple

D. AFFECTED SYSTEM/PROCESS
- System: ___________________
- Process (from inventory): ___________________
- Process owner unit: ___________________

E. BREACH TYPE
[ ] External (cyber) attack
[ ] Internal error / mistake
[ ] Internal misuse
[ ] Supplier / third-party
[ ] Physical (loss, theft, paper)
[ ] Device loss / theft (laptop, USB, phone)
[ ] Wrong recipient (email, courier)
[ ] Social engineering / phishing
[ ] Other: ___________________

F. AFFECTED DATA
- Data categories: ___________________
- Sensitive data involved: [Yes/No] — Detail: ___________________
- Children's data: [Yes/No]
- Estimated number of affected persons: ___________________
- Data subject group: [Employee/Customer/Applicant/Supplier/Other]

G. INITIAL SCALE ASSESSMENT
[ ] LOW — limited records, low sensitivity, fast containment
[ ] MEDIUM — medium volume, limited sensitivity
[ ] HIGH — large volume OR sensitive data OR cross-border impact
[ ] CRITICAL — high volume + sensitive + media/reputation OR
   large-scale consumer harm

H. INITIAL RESPONSE (within T0 + 4 hours)
- Containment: [Yes/No] — Detail:
- Unauthorised access blocked:
- Affected systems isolated:
- Forensic preservation:

I. PRELIMINARY ROOT CAUSE
[ ] Authorisation error
[ ] Patch missing / vulnerability
[ ] Configuration error
[ ] Social engineering
[ ] Training gap
[ ] Supplier process failure
[ ] Policy violation
[ ] Unknown (not yet established)

J. CONCURRENT NOTIFICATIONS
[ ] CISO / IT Manager
[ ] KVKK Officer
[ ] Legal Counsel
[ ] General Manager
[ ] Communications Director
[ ] Internal Audit
[ ] Audit Committee of the Board (in critical cases)

K. AUTHORITY NOTIFICATION ASSESSMENT
- 72-hour Authority notification: [Yes/No/Under review]
- If no, justification: ___________________
- Notification to data subjects: [Yes/No] — Method: ___________________

L. TEAM ASSIGNMENT
- Incident Response Lead: ___________________
- Legal counterpart: ___________________
- Technical response lead: ___________________
- Communications lead: ___________________
- KVKK Officer (Authority counterpart): ___________________

M. NEXT STEPS
- T0 + 12 h: KVKK Committee extraordinary meeting
- T0 + 24 h: Detailed root cause analysis begins
- T0 + 36 h: Authority notification draft complete
- T0 + 72 h: Authority notification sent
- T0 + 7 days: Data subject notifications complete
- T0 + 30 days: Closure report

==========================================================
Approval
- Drafter: ___________________ (signature, date)
- KVKK Officer: ___________________
- Legal Counsel: ___________________
==========================================================
```

---

## 3. TEMPLATE B — DATA BREACH NOTIFICATION TO THE KVKK AUTHORITY (English equivalent)

> Generated from the Authority's published standard form (Decision 2019/10 dated 24.01.2019). Filed via the Authority's VERBİS portal or kvkk.gov.tr/Notification.

```
==========================================================
PERSONAL DATA BREACH NOTIFICATION FORM
KVKK Article 12/5 and Authority Decision 2019/10
==========================================================

A. CONTROLLER INFORMATION
- Controller Full Legal Name: [COMPANY]
- Mersis No: [MERSIS]
- VERBİS Registration No (if any): [VERBIS]
- Address: [ADDRESS]
- KEP Address: [KEP]
- Phone: [PHONE]
- Website: [WEB]

B. CONTACT PERSON / CONTROLLER REPRESENTATIVE
- Name-Surname: [NAME]
- Role: [ROLE — e.g. KVKK Officer]
- Phone: [PHONE]
- Email: [EMAIL]

C. BREACH SCOPE
1. Date the breach occurred (or estimated range):
   [DATE OR RANGE]

2. Date the breach was detected:
   [DATE AND TIME]

3. Detection method:
   [E.g. automatic anomaly detection by SOC; employee report;
   supplier report; data subject complaint]

4. Date this form is sent to the Authority:
   [DATE AND TIME]

5. If notification exceeds 72 hours, reasons for delay:
   [Leave blank if within window; otherwise, detailed explanation]

D. NATURE OF THE BREACH
[ ] Confidentiality breach (unauthorised disclosure)
[ ] Integrity breach (unauthorised alteration)
[ ] Availability breach (loss, deletion, service outage)

Description: [BREACH SCENARIO 100-300 WORDS]

E. AFFECTED PERSONAL DATA
1. Data categories:
   [E.g. identity (name, ID number), contact (email, phone),
   customer transaction (order, invoice), marketing preferences]

2. Sensitive data involved:
   [Yes/No] — If yes: [Health, biometric, etc.]

3. Data subject groups:
   [E.g. customers, employees, applicants, supplier representatives]

4. Estimated number of affected persons:
   [NUMBER OR RANGE]; basis of estimate:

5. Number of records affected:
   [NUMBER OR RANGE]

6. Affected systems:
   [System name, description]

F. LIKELY CONSEQUENCES
1. Likely risks for affected data subjects:
   [E.g. fraud, identity theft, moral harm, commercial loss]

2. Impact level: [Low / Medium / High / Very High]

3. Impact rationale:
   [DATA VOLUME × SENSITIVITY × REUSE RISK]

G. MEASURES TAKEN OR PLANNED
1. Immediate measures (within T0 + 72 hours):
   [E.g. isolation of affected systems, password reset, blocking
   unauthorised access, log preservation]

2. Mid-term measures (within T0 + 30 days):
   [E.g. closing the vulnerability, additional MFA, access review,
   training module update]

3. Long-term structural measures:
   [E.g. process change, architectural improvement, control gate]

H. NOTIFICATION TO DATA SUBJECTS
1. Will data subjects be notified:
   [Yes/No] — If no, reasons:

2. Notification method:
   [Email / SMS / website announcement / letter / combined]

3. Notification draft:
   [TEXT — clear language for the data subject covering breach
   nature, affected data, measures taken, what the data subject
   can do, contact information]

4. Target notification date:
   [DATE]

I. ROOT CAUSE ANALYSIS
1. Cause of the incident:
   [E.g. vulnerability, human error, social engineering, supplier
   error]

2. Structural changes to prevent recurrence:
   [Defined]

J. ANNEXES
[ ] Data subject notification text
[ ] Incident timeline
[ ] Affected data list (anonymised)
[ ] Forensic analysis report (if any)
[ ] Prior relevant Authority decisions (if any precedent)

K. APPROVALS
- Drafted by: [KVKK Officer] — [DATE]
- Legal: [Legal Counsel] — [DATE]
- Authorised signatory: [General Manager / KVKK Committee Chair] — [DATE]

==========================================================
```

---

## 4. TEMPLATE C — DATA SUBJECT NOTIFICATION (Email/SMS/Web) (English equivalent)

```
Dear [NAME],

[COMPANY] would like to inform you under Law No. 6698 on the
Protection of Personal Data of a data security event identified
on [DATE].

WHAT HAPPENED?
[2-3 sentences in clear language. No blame; professional regret.
E.g. "Following an unauthorised access to a supplier's systems,
the name-surname and email address of a limited number of our
customers may have been accessed by unauthorised third parties."]

WHICH INFORMATION WAS AFFECTED?
[Clear list — e.g. name-surname, email. State explicitly what was
not affected: "Your passwords, payment details and ID numbers
were not affected."]

WHAT DID WE DO?
[Measures taken — e.g. unauthorised access stopped immediately,
affected system isolated, passwords forcibly reset, KVKK Authority
notified, security audit launched.]

WHAT YOU CAN DO?
[Practical recommendations — e.g. change your password, do not
open suspicious emails, monitor your account activity, enable 2FA.]

CONTACT
For questions: [EMAIL] / [PHONE]
For KVKK Art. 11 rights: [APPLICATION LINK]

The KVKK Authority has also been informed; you can apply to the
Authority via [KVKK APPLICATION ROUTE].

Regards,
[COMPANY NAME]
```

---

## 5. Notification Decision Matrix

| Impact | Authority Notification | Data Subject Notification |
|--------|-------------------------|----------------------------|
| Low (limited records, low sensitivity, fast containment) | Generally required (Art. 12/5) | Risk-dependent |
| Medium | Required | Recommended |
| High | Required | Required |
| Critical | Required + extraordinary speed | Required + media communication |

> Per Authority Decision 2019/10, **where there is a risk to data subjects' rights**, notification to data subjects is made. Where no risk and impact is limited, notification to the Authority alone may suffice; this assessment is documented.

## 6. Related Documents

- [../12-mevzuat-arsiv/kurul-kararlari-ozeti.md](../12-mevzuat-arsiv/kurul-kararlari-ozeti.md)
- [../08-ihlal-yonetimi/](../08-ihlal-yonetimi/)
- [../11-denetim-ve-uyum/kpi-ve-metrikler.md](../11-denetim-ve-uyum/kpi-ve-metrikler.md)

---

## Türkçe

# Veri İhlali Bildirim Şablonları

## 1. Süre Disiplini

| Adım | Süre |
|------|------|
| İhlal şüphesi tespit | T0 |
| İç triyaj tamamlanır | T0 + 6 saat |
| KVKK Komitesi (kriz) bilgilendirilir | T0 + 12 saat |
| Kurul'a bildirim taslağı hazır | T0 + 36 saat |
| Hukuk + KVKK Sor. nihai onay | T0 + 60 saat |
| Kurul'a bildirim gönderilir | T0 + 72 saat (en geç) |
| İlgili kişiye bildirim (en kısa sürede) | T0 + 7 gün (genel hedef) |

> Kurul'a 72 saatten geç bildirim halinde **gecikme nedeni yazılı olarak açıklanmalıdır** (Kurul kararı 2019/10).

---

## 2. ŞABLON A — İÇ TRİYAJ FORMU

```
==========================================================
VERİ İHLALİ İÇ TRİYAJ FORMU
==========================================================

İhlal Referans No: IH-[YIL]-[SIRA]
Düzenlenme Tarihi/Saati: [TARİH SAAT]
Düzenleyen: [AD-SOYAD - ROL]

A. İHLAL ŞÜPHESİ KAYNAĞI
[ ] SOC / SIEM uyarısı
[ ] Çalışan bildirimi
[ ] Tedarikçi bildirimi
[ ] İlgili kişi şikâyeti
[ ] Medya / üçüncü kişi
[ ] İç denetim
[ ] Diğer: ___________________

B. İLK TESPİT BİLGİLERİ
- Tespit tarihi/saati (T0):
- İhlalin gerçekleştiği tahmini tarih:
- Tespit ile ihlal arası gecikme (MTTD):
- Tespit eden kişi:

C. İHLALİN NİTELİĞİ (KVKK m.12/5 ve Kurul 2019/10)
[ ] Gizliliğin ihlali (yetkisiz açıklama, sızıntı)
[ ] Bütünlüğün ihlali (yetkisiz değişiklik, bozulma)
[ ] Erişilebilirliğin ihlali (kayıp, silme, fidye, hizmet kesintisi)
[ ] Birden fazla niteliğin ihlali

D. ETKİLENEN SİSTEM/SÜREÇ
- Sistem: ___________________
- Süreç (envanterden): ___________________
- Süreç sahibi birim: ___________________

E. İHLAL TÜRÜ
[ ] Dış saldırı (siber)
[ ] İç hata / yanlışlık
[ ] İç kötüye kullanım
[ ] Tedarikçi / üçüncü taraf kaynaklı
[ ] Fiziksel (kayıp, hırsızlık, basılı evrak)
[ ] Cihaz kaybı / çalıntı (laptop, USB, telefon)
[ ] Yanlış muhatap (e-posta, kargo)
[ ] Sosyal mühendislik / phishing
[ ] Diğer: ___________________

F. ETKİLENEN VERİLER
- Veri kategorileri: ___________________
- Özel nitelikli veri var mı: [Evet/Hayır] — Detay: ___________________
- Çocuk verisi var mı: [Evet/Hayır]
- Tahmini etkilenen kişi sayısı: ___________________
- Veri konusu kişi grubu: [Çalışan/Müşteri/Aday/Tedarikçi/Diğer]

G. İHLAL ÖLÇEĞİ İLK DEĞERLENDİRMESİ
[ ] DÜŞÜK — sınırlı kayıt, hassas olmayan veri, hızlı kapatma
[ ] ORTA — orta hacim, sınırlı hassasiyet
[ ] YÜKSEK — yüksek hacim VEYA özel nitelikli veri VEYA yurt dışı etki
[ ] KRİTİK — büyük hacim + özel nitelikli + medya/itibar etkisi VEYA
   tüketici hakları toplu zarara uğramış

H. İLK MÜDAHALE (T0 + 4 saat içinde)
- Kapsama alma (containment) yapıldı mı: [Evet/Hayır] — Detay:
- Yetkisiz erişim engellendi mi:
- Etkilenen sistem izole edildi mi:
- Adli koruma (forensic preservation) yapıldı mı:

I. KÖK NEDEN ÖN ANALİZİ
[ ] Yetki yönetim hatası
[ ] Yama eksikliği / güvenlik açığı
[ ] Yapılandırma hatası
[ ] Sosyal mühendislik
[ ] Eğitim eksikliği
[ ] Tedarikçi süreç hatası
[ ] Politika ihlali
[ ] Bilinmiyor (henüz tespit edilmedi)

J. EŞZAMANLI BİLDİRİMLER
[ ] CISO / BT Müdürü
[ ] KVKK Sorumlusu
[ ] Hukuk Müşavirliği
[ ] Genel Müdür
[ ] İletişim Direktörü
[ ] İç Denetim
[ ] Yön. Kur. Denetim Komitesi (kritik durumda)

K. KURUL BİLDİRİM ZORUNLULUĞU DEĞERLENDİRMESİ
- Bu ihlal 72 saat içinde Kurul'a bildirilecek mi: [Evet/Hayır/Değerlendirmede]
- Hayır ise gerekçe: ___________________
- İlgili kişiye bildirim yapılacak mı: [Evet/Hayır] — Yöntem: ___________________

L. EKİP ATAMA
- İhlal Müdahale Sorumlusu: ___________________
- Hukuki muhatap: ___________________
- Teknik müdahale lideri: ___________________
- İletişim sorumlusu: ___________________
- KVKK Sor. (Kurul muhatap): ___________________

M. SONRAKİ ADIMLAR
- T0 + 12 saat: KVKK Komitesi olağanüstü toplantı
- T0 + 24 saat: Detaylı kök neden analizi başlatılır
- T0 + 36 saat: Kurul bildirim taslağı tamamlanır
- T0 + 72 saat: Kurul bildirimi gönderilir
- T0 + 7 gün: İlgili kişi bildirimi tamamlanır
- T0 + 30 gün: Kapanış raporu

==========================================================
Onay
- Düzenleyen: ___________________ (imza, tarih)
- KVKK Sorumlusu: ___________________
- Hukuk Müşaviri: ___________________
==========================================================
```

---

## 3. ŞABLON B — KVKK KURULU'NA VERİ İHLALİ BİLDİRİMİ

> Kurul'un yayımladığı standart formdan üretilmiştir (24.01.2019 tarihli ve 2019/10 sayılı Karar). Form, Kurum'un VERBİS portalı veya kvkk.gov.tr/Bildirim sayfası üzerinden gönderilir.

```
==========================================================
KİŞİSEL VERİ İHLALİ BİLDİRİM FORMU
KVKK Madde 12/5 ve Kurul Kararı 2019/10
==========================================================

A. VERİ SORUMLUSU BİLGİLERİ
- Veri Sorumlusu Tam Ticari Unvanı: [ŞİRKET]
- Mersis No: [MERSİS]
- VERBİS Kayıt No (varsa): [VERBİS]
- Adres: [ADRES]
- KEP Adresi: [KEP]
- Telefon: [TEL]
- Web sitesi: [WEB]

B. İRTİBAT KİŞİSİ / VERİ SORUMLUSU TEMSİLCİSİ
- Ad-Soyad: [AD-SOYAD]
- Görevi: [GÖREV - örn. KVKK Sorumlusu]
- Telefon: [TEL]
- E-posta: [E-POSTA]

C. İHLALİN KAPSAMI
1. İhlalin gerçekleştiği tarih (veya tahmini tarih aralığı):
   [TARİH VEYA ARALIK]

2. İhlalin tespit edildiği tarih:
   [TARİH VE SAAT]

3. İhlalin tespit edilme yöntemi:
   [Örn. SOC sistemi tarafından otomatik anomali tespiti; çalışan bildirimi;
   tedarikçi bildirimi; ilgili kişi şikâyeti]

4. Bu form Kurul'a hangi tarihte iletilmektedir:
   [TARİH VE SAAT]

5. 72 saatten geç bildirimde, gecikme nedeni:
   [Boş bırakılırsa süre içindedir; aksi halde detaylı açıklama]

D. İHLALİN NİTELİĞİ
[ ] Gizliliğin ihlali (yetkisiz açıklanma)
[ ] Bütünlüğün ihlali (yetkisiz değiştirilme)
[ ] Erişilebilirliğin ihlali (kayıp, silme, hizmet kesintisi)

Açıklama: [İHLAL SENARYOSU 100-300 KELİME]

E. İHLALDEN ETKİLENEN KİŞİSEL VERİLER
1. Veri kategorileri:
   [Örn. kimlik (ad-soyad, T.C. kimlik no), iletişim (e-posta, telefon),
   müşteri işlem (sipariş, fatura), pazarlama tercihleri]

2. Özel nitelikli veri içeriyor mu:
   [Evet/Hayır] — Evet ise: [Sağlık, biyometrik, vb.]

3. Veri konusu kişi grupları:
   [Örn. müşteriler, çalışanlar, adaylar, tedarikçi temsilcileri]

4. Tahmini etkilenen kişi sayısı:
   [SAYI VEYA ARALIK]; tahmin gerekçesi:

5. Etkilenen kayıt sayısı:
   [SAYI VEYA ARALIK]

6. Etkilenen sistem(ler):
   [Sistem adı, açıklaması]

F. İHLALİN OLASI SONUÇLARI
1. Etkilenen ilgili kişiler için olası riskler:
   [Örn. dolandırıcılık, kimlik hırsızlığı, manevi zarar, ticari kayıp]

2. Etki düzeyi: [Düşük / Orta / Yüksek / Çok Yüksek]

3. Etki gerekçesi:
   [VERİ HACMİ × HASSASİYET × YENİDEN KULLANIM RİSKİ]

G. ALINMIŞ VEYA ALINMASI PLANLANAN ÖNLEMLER
1. Acil önlemler (T0 + 72 saat içinde alınanlar):
   [Örn. etkilenen sistemlerin izolasyonu, parolaların sıfırlanması,
   yetkisiz erişimin durdurulması, log koruma]

2. Orta vadeli önlemler (T0 + 30 gün içinde):
   [Örn. ilgili güvenlik açığının kapatılması, ek MFA, yetki gözden
   geçirme, eğitim modülü güncelleme]

3. Uzun vadeli yapısal önlemler:
   [Örn. süreç değişikliği, mimari iyileştirme, kontrol noktası ekleme]

H. İLGİLİ KİŞİLERE BİLDİRİM
1. İlgili kişilere bildirim yapılacak mı:
   [Evet/Hayır] — Hayır ise gerekçe:

2. Bildirim yöntemi:
   [E-posta / SMS / web sitesi duyurusu / mektup / kombine]

3. Bildirim taslağı:
   [METİN — İlgili kişiye anlaşılır biçimde, ihlal niteliği, etkilenen
   veriler, alınan önlemler, ilgili kişinin kendi alabileceği önlemler,
   iletişim bilgileri]

4. Bildirim tarihi (hedef):
   [TARİH]

I. KÖK NEDEN ANALİZİ
1. Olayın oluşum sebebi:
   [Örn. zafiyet, insan hatası, sosyal mühendislik, tedarikçi hatası]

2. Aynı türden ihlali önlemek için yapısal değişiklikler:
   [Tanımlı]

J. EKLER
[ ] İlgili kişi bildirim metni
[ ] Olay zaman çizelgesi
[ ] Etkilenen veri listesi (anonimize)
[ ] Adli analiz raporu (varsa)
[ ] Önceki ilgili Kurul kararları (kendiliğinden örnek varsa)

K. ONAYLAR
- Hazırlayan: [KVKK Sorumlusu] — [TARİH]
- Hukuk: [Hukuk Müşaviri] — [TARİH]
- Yetkili İmza: [Genel Müdür / KVKK Komitesi Başkanı] — [TARİH]

==========================================================
```

---

## 4. ŞABLON C — İLGİLİ KİŞİYE BİLDİRİM ŞABLONU (E-posta/SMS/Web)

```
Sayın [AD-SOYAD],

[ŞİRKET] olarak, [TARİH] tarihinde fark edilen bir veri güvenliği olayı
nedeniyle 6698 sayılı Kişisel Verilerin Korunması Kanunu kapsamında sizi
bilgilendirmek isteriz.

NE OLDU?
[Olay özeti — 2-3 cümle, anlaşılır dil. Suçlama yok, üzgün ifadesi
profesyonel ölçüde. Örn. "Tedarikçi sistemlerinde gerçekleşen yetkisiz
bir erişim sonucu, sınırlı sayıdaki müşterimizin ad-soyad ve e-posta
adresi yetkisiz üçüncü kişiler tarafından erişilmiş olabilir."]

HANGİ BİLGİLER ETKİLENDİ?
[Net liste — örn. ad-soyad, e-posta. Etkilenmeyenler özellikle belirtilir:
"Şifreleriniz, ödeme bilgileriniz ve kimlik numaralarınız etkilenmemiştir."]

NE YAPTIK?
[Alınan önlemler — örn. yetkisiz erişim derhal kesildi, etkilenen sistem
izole edildi, parolalar zorla sıfırlandı, KVKK Kurumuna bildirim yapıldı,
güvenlik denetimi başlatıldı.]

SİZ NE YAPABİLİRSİNİZ?
[Pratik öneriler — örn. parolanızı değiştirin, şüpheli e-postaları
açmayın, hesap hareketlerinizi kontrol edin, 2FA aktifleştirin.]

İLETİŞİM
Sorularınız için: [E-POSTA] / [TELEFON]
KVKK m.11 hakları için: [BAŞVURU LİNKİ]

KVKK Kurumu da olaydan haberdar edilmiştir; gerekirse Kurum'a
[KVKK BAŞVURU YOLU] üzerinden başvurabilirsiniz.

Saygılarımızla,
[ŞİRKET ADI]
```

---

## 5. İhlal Bildirim Karar Matrisi

| Etki | Kurul'a Bildirim | İlgili Kişiye Bildirim |
|------|-------------------|-------------------------|
| Düşük (sınırlı kayıt, düşük hassasiyet, hızlı kapatma) | Genelde gerekli (m.12/5) | Risk değerlendirmesine bağlı |
| Orta | Gerekli | Önerilir |
| Yüksek | Gerekli | Zorunlu |
| Kritik | Gerekli + olağanüstü hızda | Zorunlu + medya iletişimi |

> Kurul kararı 2019/10 ışığında, **kişi haklarına yönelik risk varsa** ilgili kişiye bildirim yapılır. Risk yoksa ve verilerin etkisi sınırlıysa Kurul'a bildirim ile yetinilebilir; bu değerlendirme yazılı yapılır.

## 6. İlgili Dokümanlar

- [../12-mevzuat-arsiv/kurul-kararlari-ozeti.md](../12-mevzuat-arsiv/kurul-kararlari-ozeti.md)
- [../08-ihlal-yonetimi/](../08-ihlal-yonetimi/)
- [../11-denetim-ve-uyum/kpi-ve-metrikler.md](../11-denetim-ve-uyum/kpi-ve-metrikler.md)
