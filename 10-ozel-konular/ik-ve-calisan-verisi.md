---
Doküman / Document: İnsan Kaynakları ve Çalışan Verisi Yönetimi / Human Resources and Employee Data Management
Bölüm / Section: 10-ozel-konular
Sahip / Owner: KVKK Sorumlusu + İK Direktörü + Bilgi Güvenliği / KVKK Officer + HR Director + Information Security
Onaylayan / Approved by: Hukuk Müdürü + KVKK Komitesi + Yönetim / Head of Legal + KVKK Committee + Management
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + AYM/Yargıtay içtihat değişikliklerinde / Annual + on Constitutional Court / Court of Cassation case-law changes
İlgili Mevzuat / Legal Reference: Law No. 6698 (KVKK); Law No. 4857 (Labor Law) Art. 5, 25, 75; Law No. 6098 (Code of Obligations) Art. 396, 419; Law No. 5510 (SGK); Law No. 6331 (OHS); Law No. 6356 (Unions); Constitutional Court E.2014/180, E.2018/31447; ECtHR Bărbulescu v. Romania (2017), López Ribalda v. Spain (2019)
---

## English

# Human Resources and Employee Data Management

## 1. Purpose and Scope

Management of candidate and employee data in line with KVKK, labor law, and human rights, throughout the lifecycle from recruitment through termination. Given our 500+ employee structure, this is one of the highest KVKK risk areas.

## 2. Lifecycle Stages

```
[Job posting] -> [Application] -> [Interview] -> [Reference] -> [Hire]
                                                                  |
   [Post-exit retention] <- [Exit process] <- [Employment]
```

### 2.1. Recruitment

**Data collected:**

- Identity (name, T.R. ID, date of birth).
- Contact.
- Education, certifications, language proficiency.
- Work experience.
- References (third-party data).
- Photo (in CV - optional).
- Expected salary.
- (Some roles) Driver's license, medical report.
- (Limited cases) Special category - disability report (quota), military service status.

**Legal grounds:**

- Art. 5(2)(c) (negotiations directly related to forming a contract).
- Art. 5(2)(f) (legitimate interest - assessing suitable candidates).

**Candidate privacy notice:**

- Data collected.
- Purpose.
- Retention (for unsuccessful applicants, **6 months - 1 year** recommended; extensible with explicit consent).
- Inclusion in blacklist / talent pool?

### 2.2. Interviews

- Are interview notes recorded? -> recording is subject to KVKK.
- Video interviews (Zoom, Teams) -> explicit consent for recording.
- AI interview screening (HireVue, etc.) -> automated decision + DPIA.

### 2.3. Reference Checks

- With candidate's consent.
- Third-party (former employer) data is also processed - care.
- "Character references" sensitive; risk of personal-data leakage.

### 2.4. Post-Hire Personal File

- Photocopy of T.R. ID.
- Diplomas, certificates.
- Criminal record (limited roles - Art. 6 conviction is **special category**).
- Military status.
- IBAN.
- Spouse, children info (minimum living allowance).
- Medical report (OHS).
- Emergency contact (spouse, parents - third-party data).

### 2.5. During Employment

- Performance reviews.
- Training records.
- Disciplinary actions.
- Payroll, payments.
- Absence, leave.
- OHS training, accident records.
- Employee surveys (engagement, culture).

### 2.6. Post-Exit

- End of employment (resignation, termination, retirement).
- Retention periods (below).
- Reference giving (with explicit consent of the former employee).

## 3. Statutory Retention Periods

| Data / Record | Period | Source |
|---------------|--------|--------|
| Payroll | **10 years** | Turkish Commercial Code Art. 82 |
| SGK enrollment notice | **10 years** | Law 5510 |
| Tax (income tax) | **5 years** | Tax Procedure Law Art. 253 |
| Personnel file | Employment + **10 years** | Labor Law + statute of limitations |
| Pre-employment medical | **15 years** | Law 6331 |
| Work accident | **15 years** | Law 5510 + Labor Law |
| Occupational disease | **30 years** | Court of Cassation case law |
| Disciplinary records | Employment + **5 years** | HR good practice |
| Performance reviews | Employment + **2-5 years** | HR good practice |
| CCTV (production) | **30 days** | KVKK + reasonable period |
| Departing-employee e-mail backup | **30-90 days** | DLP review |
| Unsuccessful candidate CV | **6 months - 1 year** | HR good practice |

> **Caution:** The longest legal period applies; unnecessarily long retention is grounds for the Authority to find a violation.

## 4. Explicit Consent Issue - Employee Asymmetry

### 4.1. Legal Framework

KVKK Art. 3: explicit consent = "consent regarding a specific subject, **based on information**, and **declared by free will**".

> **Problem:** In an employee-employer relationship, "free will" is easily contested. The employee may worry that refusal will jeopardize their employment -> **consent is invalid**.

### 4.2. Practical Approach

For employee data, **rely on other legal grounds wherever possible**:

| Data / Activity | Preferred Ground |
|-----------------|------------------|
| Payroll, tax, SGK | Art. 5(2)(a) (express provision in laws) |
| Performance reviews | Art. 5(2)(f) (legitimate interest) + employment contract |
| OHS health | Art. 6(3) (workplace physician under secrecy obligation) |
| Disciplinary | Art. 5(2)(c) (performance of contract) + Art. 5(2)(e) (establishment of right) |
| Employee cameras | Art. 5(2)(f) + proportionality (not consent) |

### 4.3. Cases Where Explicit Consent IS Needed

- Profile photos (intranet, website).
- Use of employee in marketing materials.
- Wedding/birth/training celebration posts.
- Body measurements, physical attributes (outside uniform - e.g., gifts).
- Sharing of family information for celebrations.
- BYOD app monitoring on a personal device.

### 4.4. Designing Employee Explicit Consent

- A single "I consent to all" form is **NOT acceptable**.
- Separate checkboxes.
- Refusal allowed - no negative consequence.
- Withdrawal easy.
- Records timestamped.

## 5. Employee Monitoring

### 5.1. Legal Framework

- Labor Law Art. 5: employer's right to monitor.
- Constitutional Court E.2014/180: monitoring proportionate, with prior notice, in reasonable scope.
- ECtHR Bărbulescu (2017): privacy at work is protected; **prior notice + proportionality**.
- ECtHR López Ribalda v. Spain (2019): hidden cameras exceptional, strong justification needed.

### 5.2. Monitoring Types and Standards

#### 5.2.1. E-mail Monitoring

| Type | Standard |
|------|----------|
| Volume/metadata monitoring | Prior notice + DLP |
| Content review | In incident, with KVKK + Legal approval + log |
| Automated content scanning (DLP) | Prior notice; label-based, not personal |
| Company rule: no personal use | In contract + on intranet |

#### 5.2.2. Internet Use

- Category-based blocking (productivity tools accessible).
- Detailed per-employee logging is hard to justify under proportionality.
- General reporting (aggregate + anonymized) is good practice.

#### 5.2.3. GPS / Location

- Vehicle GPS for field employees is reasonable (operational need).
- No monitoring during breaks or personal use.
- Off after working hours.

#### 5.2.4. CCTV

See `kamera-cctv.md`. In employee areas, proportionality + prior notice + union coordination.

#### 5.2.5. Keystroke / Screen Recording

- Excessively intrusive; **as a rule forbidden**.
- Limited cases: call-center quality (prior notice, limited hours), suspected crime (Legal approval).

#### 5.2.6. UEBA (User Entity Behavior Analytics)

- Anomalous behavior detection.
- Started anonymized; personalized on alarm.
- Deepens with Legal + KVKK approval.

### 5.3. Monitoring Privacy Notice

Signed by the employee at start of employment:

- Which systems are monitored.
- For what purpose.
- Retention period.
- Access authorities.
- Employee rights.

## 6. BYOD and MDM (Bring Your Own Device / Mobile Device Management)

### 6.1. BYOD Policy

- Work data on personal device -> mixed area.
- Work profile via MDM (Android Work Profile, iOS APNs).
- Personal + work in separate containers.
- The company manages only the work profile; does not see personal data.

### 6.2. KVKK Compliance

- Tell the employee: what data is visible, what is not.
- On loss/theft, **selective wipe** (work profile only).
- Geo-tracking only on loss/theft, with employee approval.

### 6.3. Bans

- Full device wipe (damaging personal data) -> exceptional, last resort.
- SMS, call log monitoring -> as a rule forbidden.
- Personal app list monitoring -> outside proportionality.

## 7. WhatsApp / Telegram / Slack at Work

### 7.1. Risks

- Customer data on personal WhatsApp -> data breach.
- WhatsApp groups hard to clean when an employee leaves.
- Backup -> cloud -> abroad.
- E2EE encryption is **opaque** to the data controller (us); auditing is hard.

### 7.2. Policy

- WhatsApp **should be banned for work** or restricted (Microsoft Teams, Slack preferred).
- WhatsApp Business + approved templates - for customer communication only.
- Slack/Teams corporate accounts - logging + retention compliant.
- On exit, employee is removed from groups + access revoked.

### 7.3. Implementation

- WhatsApp Web/Desktop blocked on corporate devices (DLP + EDR).
- Work conversations on personal WhatsApp forbidden (in contract + policy).
- Violations are disciplinary grounds.

## 8. Post-Exit Data Management

### 8.1. Account Closure (D-Day)

Last working day:

- AD/Entra account disabled.
- VPN, MFA, SSO closed.
- Access card, corporate device returned.
- E-mail auto-reply + forward (to authorized colleague).
- Cloud drives (OneDrive, Google Drive) work folders transferred to manager.

### 8.2. Data Protection

| Data | Process |
|------|---------|
| E-mail | 30-90 days archive, then deletion (except legal retention) |
| Personal folder | Work-related to manager; rest deleted |
| Certificates, keys | Revoke + rotate |
| Memberships (SaaS) | Disable + license return |

### 8.3. References

- Reference for former employee -> with **explicit consent**.
- Negative reference is a legal risk (tort).
- Standardized statements (role, employment dates).

### 8.4. Blacklist / Talent Pool

- "Do-not-rehire" list -> KVKK risky; must have a justification.
- If a legal process requires it, Legal review.
- Time-limited.

### 8.5. LinkedIn etc. - Public Information

- Public data (KVKK Art. 5(2)(d)) - limited processing.
- Sharing former employee's public profile is acceptable.
- Private messages / connection list -> not.

## 9. Sensitive Topics

### 9.1. Social Media Behavior

- Monitoring an employee's personal social-media account -> privacy violation.
- Forcing them to link the profile is forbidden.
- Rules for using company expressions are in the contract.

### 9.2. Pregnancy / Maternity Leave

- Pregnancy info is sensitive even if not deemed special category - HR + relevant manager only.
- KVKK + Labor Law Art. 74 in any role-change decisions.

### 9.3. Sexual Harassment Complaints

- Complaint records are special category (sex life).
- Legal + KVKK + HR triple - tight access.
- Long retention (statute of limitations).
- Evidence chain.

### 9.4. Union Membership

- KVKK Art. 6 special category (union).
- Processed only for lawful purposes (collective agreement, dues).
- Member-list leak is critical.

### 9.5. Ethnicity / Religion / Political Views

- Must not be processed (discrimination risk).
- May not be asked at recruitment.
- Should not appear in any record.

## 10. Automated Decisions (Performance, HR Analytics)

### 10.1. Automated Performance Scoring

- If an algorithm is used, it must be explainable.
- Art. 11(g) - right to object.
- DPIA mandatory.
- Human approval required (HR-in-the-loop).

### 10.2. AI in Recruitment

- CV screening, automated rejection.
- Bias risk -> regular audits.
- Candidate informed.
- Manual review guarantee.

## 11. HR System Security

- HRMS (Workday, SAP SuccessFactors, Logo, Mikro) access control.
- RBAC + Segregation of Duties (SoD).
- Encrypted payroll data.
- Audit log.
- Third-party payroll -> DPA.

## 12. Common Mistakes

| Mistake | Correct approach |
|---------|------------------|
| Single "explicit consent" form for all HR | Differentiate by legal ground; specific consent rare |
| Diagnosis in HR system | Physician system separate |
| Customer data in WhatsApp group | Forbidden - corporate channel |
| Former employee e-mail open for 5 years | 30-90 days, then delete |
| Indefinitely retained candidate CVs | 6 months - 1 year, then delete/anonymize |
| Social media monitoring | Forbidden - privacy |
| Keystroke logger | Excessively intrusive, not lawful |
| BYOD full wipe | Selective work-profile wipe |
| Union membership in general system | Restricted access |

## 13. KPIs

| KPI | Target |
|-----|--------|
| HR privacy notice coverage | 100% of employees |
| Exit-process SLA | Account closed on last day |
| Candidate retention compliance | 100% |
| BYOD policy compliance | 95%+ |
| WhatsApp work-use violations | < 5/year |
| Annual HR audit critical findings | Zero |

## 14. Version History

| Version | Date | Change | Approval |
|---------|------|--------|----------|
| 1.0 | 2026-05-08 | First publication | KVKK Committee |

---

## Türkçe

# İnsan Kaynakları ve Çalışan Verisi Yönetimi

## 1. Amaç ve Kapsam

Çalışan ve aday verilerinin işe alımdan iş ilişkisinin sonlandırılmasına kadar tüm süreçte KVKK, iş hukuku ve insan haklarına uygun yönetimi. Şirketimizin 500+ çalışanlı yapısı nedeniyle bu alan en yoğun KVKK risk alanlarındandır.

## 2. Yaşam Döngüsü Aşamaları

```
[İş İlanı] → [Aday Başvurusu] → [Mülakat] → [Referans] → [İşe Alım]
                                                              ↓
       [Çıkış sonrası saklama] ← [Çıkış İşlemleri] ← [Çalışan Yaşamı]
```

### 2.1. İşe Alım

**Toplanan veri:**
- Kimlik (ad-soyad, T.C., doğum tarihi).
- İletişim.
- Eğitim, sertifika, dil yetkinliği.
- İş deneyimi.
- Referans (3. kişi verisi).
- Fotoğraf (CV'de — opsiyonel).
- Beklenen ücret.
- (Bazı pozisyonlar) Sürücü belgesi, sağlık raporu.
- (Sınırlı durumlar) Özel nitelikli — engellilik raporu (kota), askerlik durumu.

**Hukuki sebepler:**
- m.5/2-c (sözleşmenin kurulmasıyla ilgili olarak işe alım görüşmeleri).
- m.5/2-f (meşru menfaat — uygun aday değerlendirme).

**Aday aydınlatma metni:**
- Toplanan veri.
- Amaç.
- Saklama süresi (alınmayanlar için **6 ay - 1 yıl** önerilir, açık rıza ile uzatılabilir).
- Kara liste / havuz dahil mi?

### 2.2. Mülakat

- Mülakat notları kayıtlı mı? → kayıt KVKK'ya tabi.
- Video mülakat (Zoom, Teams) → kayıt için açık rıza.
- AI mülakat değerlendirme (HireVue, vb.) → otomatik karar + DPIA.

### 2.3. Referans Kontrolü

- Aday rızasıyla.
- Üçüncü kişi (eski işveren) verisi de işlenmiş olur — dikkat.
- "Karakter referansı" hassas; kişisel veri sızıntısı riski.

### 2.4. İşe Alım Sonrası Özlük

- T.C. kimlik fotokopisi.
- Diploma, sertifika.
- Sabıka kaydı (sınırlı pozisyonlar — m.6 ceza mahkumiyeti **özel nitelikli**).
- Askerlik durumu.
- IBAN.
- Eş, çocuk bilgisi (AGİ — Asgari Geçim İndirimi).
- Sağlık raporu (İSG kapsamı).
- Acil durumda iletişim (eş, anne/baba — 3. kişi verisi).

### 2.5. Çalışan Yaşamı

- Performans değerlendirme.
- Eğitim kayıtları.
- Disiplin işlemleri.
- Ücret bordrosu, ödeme.
- Devamsızlık, izin.
- İSG eğitim, kaza kaydı.
- Çalışan anketi (memnuniyet, kültür).

### 2.6. Çıkış Sonrası

- İş akdi sonu (istifa, fesih, emeklilik).
- Saklama süreleri (aşağıda).
- Referans verme (eski çalışana — açık rıza ile).

## 3. Saklama Süreleri (Kanuni)

| Veri / Kayıt | Süre | Kaynak |
|-------------|------|--------|
| Bordro | **10 yıl** | TTK m.82 |
| SGK işe giriş bildirgesi | **10 yıl** | 5510 |
| Vergi (gelir vergisi) | **5 yıl** | VUK m.253 |
| Personel sicil dosyası | İş akdi + **10 yıl** | 4857 + zamanaşımı |
| İşe giriş muayenesi | **15 yıl** | 6331 |
| İş kazası kaydı | **15 yıl** | 5510 + 4857 |
| Meslek hastalığı | **30 yıl** | Yargıtay içtihatları |
| Disiplin tutanakları | İş akdi + **5 yıl** | İK iyi pratiği |
| Performans değerlendirme | İş akdi + **2-5 yıl** | İK iyi pratiği |
| CCTV (üretim) | **30 gün** | KVKK + makul süre |
| E-posta yedek (ayrılan çalışan) | **30-90 gün** | DLP gözden geçirme |
| Aday CV (alınmayan) | **6 ay - 1 yıl** | İK iyi pratiği |

> **Uyarı:** En uzun yasal süre baz alınır; gereksiz uzun saklama Kurul ihlal kararı sebebidir.

## 4. Açık Rıza Sorunu — Çalışan Asimetrisi

### 4.1. Yasal Çerçeve

KVKK m.3 açık rıza tanımı: "Belirli bir konuya ilişkin, **bilgilendirilmeye dayanan** ve **özgür iradeyle açıklanan** rıza."

> **Sorun:** Çalışan-işveren ilişkisinde "özgür irade" kolayca tartışmalı hale gelir. Çalışan rıza vermezse iş akdi tehlikeye girer endişesi → **rıza geçersiz**.

### 4.2. Pratik Yaklaşım

Çalışan veri işlemesi için **mümkün olan her durumda diğer hukuki sebeplere** dayan:

| Veri / Faaliyet | Tercih Edilen Sebep |
|-----------------|---------------------|
| Bordro, vergi, SGK | m.5/2-a (kanunlarda öngörülmesi) |
| Performans değerlendirme | m.5/2-f (meşru menfaat) + iş sözleşmesi |
| İSG sağlık | m.6/3 (sır saklama yükümlülüğü altında işyeri hekimi) |
| Disiplin | m.5/2-c (sözleşmenin ifası) + m.5/2-e (hak tesisi) |
| Çalışan kameraları | m.5/2-f + ölçülülük (rıza değil) |

### 4.3. Açık Rıza Gerekenler

- Profil fotoğrafı (intranette, web sitesinde).
- Pazarlama materyalinde çalışan kullanımı.
- Düğün/doğum/eğitim kutlama yayını.
- Beden ölçüleri, fiziksel özellikler (üniforma dışında — örn. hediye).
- Çocuk vb. aile bilgisinin kutlama amaçlı paylaşımı.
- BYOD cihaz üzerinde uygulama izleme.

### 4.4. Açık Rıza Tasarımı (Çalışan)

- Tek bir "tüm rızalarımı veriyorum" KABUL EDİLMEZ.
- Ayrı checkboxlar.
- Reddedebilir — olumsuz sonuç olmamalı.
- Geri alma kolay.
- Kayıt zaman damgalı.

## 5. Çalışan İzleme

### 5.1. Yasal Çerçeve

- 4857 m.5: işveren denetim hakkı.
- AYM E.2014/180: izleme orantılı, önceden bildirilmiş, makul kapsamda.
- ECtHR Bărbulescu (2017): kişisel mahremiyet işyerinde de korunur; **önceden bildirim + ölçülülük**.
- ECtHR López Ribalda v. Spain (2019): gizli kamera istisnaî, kuvvetli gerekçe.

### 5.2. İzleme Tipleri ve Standartları

#### 5.2.1. E-posta İzleme

| Tip | Standart |
|-----|----------|
| Hacim/metadata izleme | Önceden bildirim + DLP |
| İçerik denetimi | Olay halinde, KVKK + Hukuk onayı + log |
| Otomatik içerik tarama (DLP) | Önceden bildirim, kişisel olmayan etiket bazlı |
| Şirket kuralı: kişisel kullanım yasak | Sözleşmede + intranette |

#### 5.2.2. İnternet Kullanımı

- Kategori bazlı engelleme (üretkenlik araçları erişilebilir).
- Çalışan başına detaylı log → ölçülülük zorlu.
- Genel raporlama (toplu + anonimleştirilmiş) iyi pratik.

#### 5.2.3. GPS / Lokasyon

- Saha çalışanları için araç GPS makul (operasyonel gereklilik).
- Mola, kişisel kullanım dışında izleme.
- Mesai sonrası kapatma.

#### 5.2.4. CCTV

Bkz. `kamera-cctv.md`. Çalışan alanlarında ölçülülük + önceden bildirim + sendika koordinasyonu.

#### 5.2.5. Klavye / Ekran Kayıt

- Aşırı müdahale; **kural olarak yasak**.
- Sınırlı durumlar: çağrı merkezi kalite (önceden bildirim, sınırlı saatler), suç şüphesi (Hukuk onayı).

#### 5.2.6. UEBA (User Entity Behavior Analytics)

- Anormal davranış tespiti.
- Anonimleştirilmiş başlatılır; alarm üzerine kişiselleştirilir.
- Hukuk + KVKK onayı ile derinleşir.

### 5.3. İzleme Aydınlatma Metni

İşe başlama esnasında çalışana imzalı:
- Hangi sistemler izleniyor.
- Hangi amaçla.
- Saklama süresi.
- Erişim yetkilileri.
- Çalışan hakları.

## 6. BYOD ve MDM (Bring Your Own Device / Mobile Device Management)

### 6.1. BYOD İzin Politikası

- Kişisel cihazda iş verisi → karma alan.
- MDM (Mobile Device Management) ile iş profili (Android Work Profile, iOS APNs).
- Kişisel + iş ayrı container.
- Şirket sadece iş profilini yönetir; kişisel veri görmez.

### 6.2. KVKK Uyumu

- Çalışana açıklama: hangi veri görünür, hangi değil.
- Cihaz çalınma/kayıp halinde **selektif silme** (sadece iş profili).
- Geo-tracking sadece kayıp/çalınma halinde, çalışan onayı.

### 6.3. Yasaklar

- Tam cihaz wipe (kişisel verilere zarar) → istisnaî, son çare.
- SMS, çağrı kayıtları izleme → kural olarak yasak.
- Kişisel uygulama listesi izleme → ölçülülük dışı.

## 7. WhatsApp / Telegram / Slack İş Kullanımı

### 7.1. Riskler

- Müşteri verisi kişisel WhatsApp'ta → veri ihlali.
- Whatsapp grupları çalışan ayrılınca zor temizlenir.
- Backup → bulut → yurt dışı.
- E2EE şifreleme veri sorumlusu (Şirket) için **şeffaf değil** — denetim zor.

### 7.2. Politika

- WhatsApp **iş için yasaklanmalı** veya çok sınırlı (Microsoft Teams, Slack tercih).
- WhatsApp Business + onaylı şablonlar — müşteri iletişimi için.
- Slack/Teams kurumsal hesap — kayıt + saklama uyumlu.
- Çalışan ayrıldığında gruplardan çıkarılır + erişim iptali.

### 7.3. Uygulama

- WhatsApp Web/Desktop kurumsal cihazlarda yasaklı (DLP + EDR).
- Kişisel WhatsApp'ta iş yazışması yasak (sözleşmede + politika).
- İhlal disiplin sebebi.

## 8. Çıkış Sonrası Veri Yönetimi

### 8.1. Hesap Kapatma (D-Day)

Son çalışma günü:
- AD/Entra hesabı disable.
- VPN, MFA, SSO kapatma.
- Erişim kartı, kurumsal cihaz teslim.
- E-posta auto-reply + iletim (yetkili kişiye).
- Bulut sürücüleri (OneDrive, Google Drive) iş klasörleri yöneticiye aktarım.

### 8.2. Veri Korunması

| Veri | Süreç |
|------|-------|
| E-posta | 30-90 gün arşiv, sonra silme (yasal saklama hariç) |
| Kişisel klasör | İşle ilgili olanlar yöneticiye, kalan silinir |
| Sertifika, anahtarlar | İptal + rotasyon |
| Üyelik (SaaS) | Devre dışı + license geri |

### 8.3. Referans Paylaşımı

- Eski çalışana referans verme → **açık rıza** ile.
- Olumsuz referans hukuki risk (haksız fiil).
- Standardize edilmiş ifadeler (görev, çalışma dönemi).

### 8.4. Kara Liste / Havuz

- "Dönmemesi gereken çalışan" listesi → KVKK riskli; gerekçesi olmalı.
- Hukuki süreç gerektiriyorsa Hukuk değerlendirmesi.
- Süre sınırlı.

### 8.5. LinkedIn vb. Kamuya Açık Bilgi

- Kamuya açıklanmış veri (KVKK m.5/2-d) — sınırlı işleme.
- Eski çalışanın kamu profili paylaşımı kabul edilebilir.
- Özel mesajlar / bağlantı listesi → değil.

## 9. Hassas Konular

### 9.1. Sosyal Medya Davranışı

- Çalışanın kişisel sosyal medya hesabı izleme → mahremiyet ihlali.
- Profilini bağlamaya zorlama yasak.
- Şirket ifadelerini paylaşma kuralları sözleşmede.

### 9.2. Hamilelik / Doğum İzni

- Hamilelik bilgisi özel nitelikli sayılmasa da hassas — sadece İK + ilgili yönetici.
- Görev değişikliği vb. kararda KVKK + İş Kanunu m.74.

### 9.3. Cinsel Taciz Şikayeti

- Şikayet kaydı özel nitelikli (cinsel hayat).
- Hukuk + KVKK + İK üçlü — sıkı erişim.
- Saklama uzun (zamanaşımı).
- Kanıt zinciri.

### 9.4. Sendika Üyeliği

- KVKK m.6 özel nitelikli (sendika).
- Sadece kanuni amaçla (toplu sözleşme, prim) işlenir.
- Üye listesi sızıntısı kritik.

### 9.5. Etnik Köken / Din / Siyasi Görüş

- Kesinlikle işlenmemeli (ayrımcılık riski).
- İşe alımda sorulamaz.
- Kayıtta yer almamalı.

## 10. Otomatik Karar (Performans, İK Analitiği)

### 10.1. Otomatik Performans Skorlama

- Algoritma kullanılırsa açıklanabilir olmalı.
- m.11/g — itiraz hakkı.
- DPIA zorunlu.
- İnsan onayı gerekli (HR-in-the-loop).

### 10.2. AI ile İşe Alım Önekrı

- CV taraması, otomatik eleme.
- Önyargı (bias) riski → düzenli denetim.
- Aday bilgilendirilir.
- Manuel gözden geçirme garantisi.

## 11. İK Sistemi Güvenliği

- HRMS (Workday, SAP SuccessFactors, Logo, Mikro) erişim kontrolü.
- RBAC + SoD (Segregation of Duties).
- Bordro veri şifreli.
- Audit log.
- 3. taraf payroll → DPA.

## 12. Tipik Hatalar

| Hata | Doğru Yaklaşım |
|------|----------------|
| Tüm İK için tek "açık rıza" formu | Hukuki sebep ayrımı + spesifik rıza nadir |
| Tanı IK sisteminde | Hekim sistemi ayrı |
| WhatsApp grubunda müşteri verisi | Yasak — kurumsal kanal |
| Eski çalışan e-postası 5 yıl açık | 30-90 gün, sonra silme |
| Aday CV süresiz saklı | 6 ay - 1 yıl, sonra silme/anonim |
| Sosyal medya izleme | Yasak — mahremiyet |
| Klavye logger | Aşırı müdahale, yasal değil |
| BYOD tam cihaz wipe | Selektif iş profili silme |
| Sendika üyeliği genel sistemde | Sınırlı erişim |

## 13. KPI'lar

| KPI | Hedef |
|-----|-------|
| İK aydınlatma kapsamı | %100 çalışan |
| Çıkış süreci SLA | Son gün hesap kapatma |
| Aday saklama süresi uyum | %100 |
| BYOD politika uyum | %95+ |
| WhatsApp iş kullanım ihlali | < 5 olay/yıl |
| Yıllık İK denetim bulgu | Sıfır kritik |

## 14. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi |
