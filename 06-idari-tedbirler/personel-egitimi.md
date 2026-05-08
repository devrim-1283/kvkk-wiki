---
Doküman / Document: Personel Eğitim ve Farkındalık Programı / Personnel Training and Awareness Program
Bölüm / Section: 06-idari-tedbirler
Sahip / Owner: İK Direktörü + KVKK Sorumlusu / HR Director + KVKK Officer
Onaylayan / Approved by: KVKK Komitesi + Üst Yönetim / KVKK Committee + Senior Management
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş (önemli ihlal, mevzuat değişikliği, yeni teknoloji) / Annual + triggered (significant breach, regulatory change, new technology)
İlgili Mevzuat / Legal Reference: Law No. 6698 KVKK Art. 12; KVKK Personal Data Security Guide — "Training and Awareness Activities"
İlgili Standart / Standard: ISO/IEC 27001:2022 A.6.3 (Information Security Awareness, Education and Training); ISO/IEC 27701:2019; NIST CSF 2.0 PR.AT (Awareness and Training); NIST SP 800-50; NIST SP 800-181 (NICE Workforce Framework); ENISA "Awareness Raising Quality Standard"
---

## English

# Personnel Training and Awareness Program

## 1. Purpose

To ensure that all employees, managers, consultants, interns, temporary staff, and third-party personnel possess **personal data protection and information security knowledge appropriate to their role** and reflect this knowledge in their daily work behavior. The direct operational implementation of "Training and Awareness Activities" in the KVKK Personal Data Security Guide.

## 2. Principles

1. **Mandatory:** Training is **not optional** — within the first week of starting and annual refresh is mandatory.
2. **Role-Based:** General curriculum + role-specific modules. The needs of a call center representative differ from those of a software developer.
3. **Evidence Required:** Completion records (LMS) kept for audit.
4. **Effectiveness Measurement:** Not just completion, but **knowledge testing and behavior change** are measured.
5. **Triggering:** Post-incident, regulatory change, new technology adoption trigger training.
6. **Continuous (Just-in-Time):** Annual one-off training is not enough; micro-learning + simulation + communication campaigns.
7. **Privacy:** Training participation and performance data in the employee's personnel file with restricted access.

## 3. Target Audiences and Modules

### 3.1. General Modules (All Employees)

| Module | Duration | Frequency |
|-------|------|--------|
| KVKK Fundamentals | 60 min | Onboarding + annual |
| Information Security Fundamentals | 60 min | Onboarding + annual |
| Phishing & Social Engineering | 30 min | Annual |
| Password & MFA | 20 min | Onboarding + annual |
| Clean Desk & Clean Screen | 15 min | Annual |
| Mobile & BYOD Security | 20 min | Annual |
| Data Breach Recognition & Reporting | 20 min | Annual |
| Data Subject Rights (Art. 11) | 30 min | Annual |

### 3.2. Role-Based Modules

| Role | Additional Modules |
|-----|-------------|
| **HR** | Employee data categories, personnel file, confidentiality undertaking, departure process, special-category data (health, union), DPIA sensitivities |
| **IT / DevOps / SRE** | Access management, log privacy, production data prohibitions, secrets, IR runbook |
| **Software Developer** | Secure SDLC, OWASP Top 10/API/LLM, threat modeling, secrets, personal data minimization, code review |
| **Data / Analytics / BI** | Masking/anonymization, re-identification risk, DPIA, privacy notice in BI |
| **AI / ML Engineers** | LLM Top 10, training data privacy, model memorization, explainability, automated decisions |
| **Call Center / Customer Service** | Data subject application, identity verification, social engineering (vishing), screen masking, call recording rules |
| **Sales / Marketing** | Marketing consents (IYS), explicit consent, cookies, external tool integrations, profile-based marketing |
| **Finance / Accounting** | PCI awareness, financial fraud (BEC), card data prohibitions |
| **Legal** | KVKK current decisions, contract templates, breach notification, EU GDPR (for international business) |
| **Managers** | Mover/leaver controls, team training responsibility, breach reporting, open leadership |
| **Senior Management** | Authority decision / sanction examples, reporting, risk appetite, crisis communication |
| **Vendor/Consultant** | Access boundaries, confidentiality undertaking, IR notification |

## 4. Curriculum Contents (Detailed Outlines)

### 4.1. KVKK Fundamentals

- KVKK scope, definitions (personal data, special category, data controller, data processor).
- General principles (Art. 4) — lawfulness, accuracy, specific and legitimate purpose, proportionality, retention period.
- Conditions of processing (Art. 5, Art. 6) — explicit consent and other legal grounds.
- Privacy notice obligation (Art. 10).
- Data subject rights (Art. 11) and application.
- Data Controller - Data Processor distinction.
- Domestic and cross-border transfer (Art. 8, Art. 9).
- VERBİS.
- KVKK Authority decisions, sanction examples (administrative fine, Turkish Criminal Code Art. 135-140).
- Linking to internal processes: privacy notices, application email address, breach hotline.

### 4.2. Phishing & Social Engineering

- Common scenarios: invoice fraud, BEC (Business Email Compromise), shipping, banking, IK / IK extension, AI-clone voice, deepfake video.
- "Urgency + authority + curiosity" trio.
- Hover, domain check, behavior with attachments.
- Reporting suspicious messages (one-click report button).
- Vishing (voice), smishing (SMS), QR phishing.
- "Internal request" check (urgent EFT request from CFO → out of process).
- Phishing simulation program + result-oriented training.

### 4.3. Password & MFA

- NIST 800-63B compliant password behavior (length, passphrase, password manager).
- Why MFA? FIDO2 vs. SMS.
- Push fatigue attack + defense.
- Account takeover detection (login notifications, unusual activity).
- Password manager use (Bitwarden, 1Password Enterprise).
- Account recovery process.

### 4.4. Data Breach Recognition and Reporting

- What is a "breach"? (unauthorized access, loss, disclosure, alteration, service interruption of personal data).
- Typical indicators: lost laptop/USB, wrong email send, open link sharing, suspicious login notification.
- Reporting hotline: where, how, when.
- "No fear of punishment" — encourage open reporting (for unintentional mistakes).
- 72-hour Authority notification background.
- Sample notification form.

### 4.5. Developer Security (Detail)

- Threat modeling exercise.
- OWASP Top 10 with code examples.
- Secrets management, dependency hygiene, SBOM.
- Sensitive data logging prohibitions (regex scan).
- Personal data minimization — justification before adding fields.
- Test environment data prohibitions.
- Secure code review.

### 4.6. AI / ML Module (New)

- LLM Top 10.
- Training data privacy — "how much does the model know?"
- Prompt injection and jailbreak.
- Automated decision-making + KVKK Art. 4 proportionality + data subject rights.
- Sending personal data to vendor LLM APIs — transfer regime, contract.
- Audit log + human oversight.

## 5. Delivery Formats

- **e-Learning (LMS):** Module, video, quiz. The main framework.
- **Classroom training:** Managers, sensitive roles (KVKK Officer, IR team).
- **Webinar:** Monthly current topic (new Authority decision, sector case).
- **Micro-learning:** 2-5 min video / infographic / Slack tip.
- **Posters:** Office physical communications.
- **Newsletter:** Monthly security bulletin.
- **Capture the Flag (CTF):** Annual competitive gamification.
- **Tabletop:** Crisis scenario for senior management.

## 6. Phishing Simulation Program

### 6.1. Framework

- At least **quarterly** campaign (4 / year).
- Scenario difficulty distribution (easy → medium → hard).
- Clicking user: instant "learning page" (not shaming — education).
- Repeated clicker: mandatory additional training, conversation with manager.
- "Those who report as suspicious" recognized (gamification, leaderboard).
- KPI: click rate, reporting rate, repeat rate.

### 6.2. Scenario Types

- Fake HR email (raise letter, performance review).
- Fake IT email (reset password, MFA reset).
- Corporate tool notification (Microsoft 365, Slack, GitHub).
- Sent as if by senior management (BEC).
- QR code phishing (via poster).
- Vishing simulation (annually 1-2 times, team-selected).
- AI-clone voice (annually 1 time).

### 6.3. Privacy and Legal Framework

- Simulation is explicitly written in the **employee privacy notice**.
- Individual success / failure data is open only to HR + CISO office, not the manager.
- Discipline is **not immediately** applied for repeated user; training is recommended.
- Results reported in aggregate (departmental average, trend), no individual "shame".

## 7. New Starter Onboarding

| Day | Activity |
|-----|----------|
| -1 | HR package access activation, orientation calendar |
| 1 | Orientation (KVKK + information security fundamentals presentation) |
| 1 | Confidentiality undertaking signature |
| 1-3 | LMS module 1-2 (KVKK + Information Security) |
| 4-5 | LMS module 3-5 (Phishing, MFA, BYOD) |
| 5 | Role-based additional modules (by department) |
| 7 | Knowledge test (≥80% pass requirement) |
| 14 | First phishing simulation |
| 30 | KVKK practical conversation with line manager |

Completion records kept in LMS for 5 years. Employees not completing cannot access production (IT access activation tied to training completion).

## 8. Annual Refresh

- All employees mandatory refresh **at least once** per year.
- 30-min concentrated (innovations, new Authority decisions, sector cases, new technology).
- Knowledge test (≥80%).
- Employee absent (long leave) during the year, 30 day extension upon return.
- For employees not completing, manager warning + HR follow-up + further non-compliance discipline.

## 9. Triggered (Post-Incident) Training

- Post in-house breach/near-miss event, micro module for affected team (anonymized case).
- KVKK Authority decision publication — relevant role's training module updated.
- Adoption of new technology (e.g., new AI tool) → mandatory module before use.
- Regulatory change — announcement to all employees within 90 days + refresh within 6 months.

## 10. Effectiveness Measurement

### 10.1. Levels (Kirkpatrick's 4 Levels)

1. **Reaction:** Satisfaction survey.
2. **Learning:** Pre-test / post-test knowledge difference.
3. **Behavior:** Phishing simulation reporting rate, real-event reporting speed.
4. **Result:** Number/severity of incidents, KPIs.

### 10.2. KPIs

- Completion rate (annual refresh): target 100%.
- Exam pass rate (≥80%): target 95%+.
- Phishing click rate: target ≤10% (year-end); start baseline measure.
- Phishing report rate (innocuous simulation): target ≥50%.
- Number of repeat clickers: target decreasing trend.
- "Initial detection source = user report" rate in incidents: target increasing.
- Employee satisfaction (post-training NPS): trend tracking.

## 11. Budget and Resources

- LMS license (per user per year).
- Content development (in-house + external).
- Phishing simulation platform (KnowBe4, Proofpoint, Hoxhunt, Cofense).
- Certification training budget (annual for KVKK Officer, CISO, IR team).
- Communication campaign (poster, video, event).
- Annual security week / KVKK Day celebration (in Turkey, "Information Security Awareness Month" — October).

## 12. Vendor / Consultant / Intern Training

- Onboarding: short (15 min) information security + KVKK fundamentals.
- Confidentiality undertaking signature (see [gizlilik-taahhutnamesi.md](gizlilik-taahhutnamesi.md)).
- Role-based training for accessed system.
- Annual refresh if contract duration exceeds 1 year.
- Vendor company cannot rely on its own training policy — our standard modules are mandatory.

## 13. Non-Compliance Management

| Situation | Action |
|-------|---------|
| New starter not completed training | IT access activation halted, HR + manager warning |
| Annual refresh deadline passed | Manager warning + 14-day extension + discipline on next breach |
| Repeated phishing click | Mandatory micro module + manager conversation + discipline on 3rd violation |
| Knowledge test failed (3 attempts) | In-person training + retest |

## 14. Certified Training for KVKK Officer / IR Team

- Annual budgeted certification program:
  - **CISSP, CISM, CIPP/E (or local equivalents)**.
  - **ISO 27001 LA / LI**.
  - **ISO 27701 LI**.
  - KVKK Authority training/symposium.
  - Sector conferences (CyberWeek TR, ISACA, OWASP TR).
- Knowledge sharing environment: in-house "communities of practice".

## 15. Logging and Evidence

- LMS: completion, exam score, attempt count.
- Phishing platform: campaign, result, list of clickers/reporters.
- Training attendance signature list (for classroom training).
- Information Security Day event records.

Retention: throughout active employment + 5 years post-departure.

## 16. Checklist

- [ ] Has the annual training calendar been published, KVKK Committee approved?
- [ ] Are general + role-based modules current, ≤12 months revision date?
- [ ] Is the LMS open to all employees, completion report quarterly?
- [ ] Is the completion rate close to 100% target?
- [ ] Is the knowledge test pass threshold ≥80%?
- [ ] Is new starter training the access activation condition?
- [ ] Phishing simulation quarterly, KPI measured?
- [ ] Annual social engineering (vishing/AI-clone) simulation present?
- [ ] Triggered post-incident training mechanism working?
- [ ] Is there a manager-specific module (mover/leaver, reporting)?
- [ ] Is vendor/consultant/intern training mandatory?
- [ ] Is the certified training budget annual for KVKK Officer / IR team?
- [ ] Are individual data reported in aggregate, employee privacy respected?
- [ ] Does the privacy notice list training/simulation?
- [ ] Are discipline classification and escalation documented?
- [ ] Is the annual event (KVKK day, security week) celebrated?

## 17. Annual Management Report Template

Annual table to KVKK Committee:

- Total employees / training-eligible / completed.
- Exam pass rate.
- Phishing simulation trends (4 quarterly).
- User contribution in incidents (initial detection source).
- Number of triggered trainings.
- Number of disciplinary actions.
- Budget usage.
- Next year's plan (new module, new target KPI).

---

## Türkçe

# Personel Eğitim ve Farkındalık Programı

## 1. Amaç

Tüm çalışan, yönetici, danışman, stajyer, geçici personel ve üçüncü taraf personelinin **rolüne uygun düzeyde** kişisel veri koruma ve bilgi güvenliği bilgisine sahip olmasını ve bu bilgiyi günlük iş davranışına yansıtmasını sağlamak. KVKK Veri Güvenliği Rehberi'nde "Eğitim ve Farkındalık Faaliyetleri" başlığının doğrudan operasyonel uygulamasıdır.

## 2. İlkeler

1. **Zorunluluk:** Eğitim **opsiyonel değildir** — işe başlama haftası içinde ve yıllık olarak tazeleme zorunludur.
2. **Rol Bazlı:** Genel müfredat + role özel modüller. Çağrı merkezi temsilcisinin ihtiyaçları, yazılım geliştiricininkinden farklıdır.
3. **Kanıt Gerekli:** Tamamlanma kayıtları (LMS) denetim için saklanır.
4. **Etkinlik Ölçümü:** Sadece tamamlanma değil, **bilgi sınaması ve davranış değişimi** ölçülür.
5. **Tetkikleyici:** Olay sonrası, mevzuat değişimi, yeni teknoloji benimseme tetiklenmiş eğitim getirir.
6. **Sürekli (Just-in-Time):** Yıllık tek seferlik eğitim yetmez; mikro öğrenme + simülasyon + iletişim kampanyaları.
7. **Mahremiyet:** Eğitim katılım ve performans verileri çalışanın özlük dosyasında, sınırlı erişimle.

## 3. Hedef Kitle ve Modüller

### 3.1. Genel Modüller (Tüm Çalışanlar)

| Modül | Süre | Sıklık |
|-------|------|--------|
| KVKK Temelleri | 60 dk | İşe başlangıç + yıllık |
| Bilgi Güvenliği Temelleri | 60 dk | İşe başlangıç + yıllık |
| Phishing & Sosyal Mühendislik | 30 dk | Yıllık |
| Şifre & MFA | 20 dk | İşe başlangıç + yıllık |
| Temiz Masa & Temiz Ekran | 15 dk | Yıllık |
| Mobil & BYOD Güvenliği | 20 dk | Yıllık |
| Veri İhlali Tanıma & Bildirim | 20 dk | Yıllık |
| İlgili Kişi Hakları (m.11) | 30 dk | Yıllık |

### 3.2. Rol Bazlı Modüller

| Rol | Ek Modüller |
|-----|-------------|
| **İK** | Çalışan veri kategorileri, özlük dosyası, gizlilik taahhütnamesi, ayrılış süreci, özel nitelikli veri (sağlık, sendika), DPIA hassasiyetleri |
| **BT / DevOps / SRE** | Erişim yönetimi, log mahremiyeti, üretim verisi yasakları, secrets, IR runbook |
| **Yazılım Geliştirici** | Secure SDLC, OWASP Top 10/API/LLM, tehdit modelleme, secrets, kişisel veri minimizasyonu, kod incelemesi |
| **Veri / Analitik / BI** | Maskeleme/anonim, re-identification riski, DPIA, BI-de aydınlatma |
| **AI / ML Mühendisleri** | LLM Top 10, eğitim verisi mahremiyeti, model memorization, açıklanabilirlik, otomatik karar |
| **Çağrı Merkezi / Müşteri Hizmetleri** | İlgili kişi başvurusu, kimlik doğrulama, sosyal mühendislik (vishing), ekran maskelemesi, çağrı kaydı kuralları |
| **Satış / Pazarlama** | Pazarlama izinleri (İYS), açık rıza, çerez, dış araç entegrasyonu, profil bazlı pazarlama |
| **Finans / Muhasebe** | PCI farkındalığı, finansal dolandırıcılık (BEC), kart verisi yasakları |
| **Hukuk** | KVKK güncel kararlar, sözleşme şablonları, ihlal bildirimi, AB GDPR (uluslararası iş için) |
| **Yöneticiler** | Mover/leaver kontrol, takım eğitim sorumluluğu, ihlal raporlama, açık liderlik |
| **Üst Yönetim** | Kurul karar / yaptırım örnekleri, raporlama, risk iştahı, kriz iletişimi |
| **Tedarikçi/Danışman** | Erişim sınırları, gizlilik taahhütnamesi, IR bildirim |

## 4. Müfredat İçerikleri (Detay Anahatları)

### 4.1. KVKK Temelleri

- KVKK kapsamı, tanımlar (kişisel veri, özel nitelikli, veri sorumlusu, veri işleyen).
- Genel ilkeler (m.4) — hukuka uygunluk, doğruluk, belirli ve meşru amaç, ölçülülük, saklama süresi.
- İşleme şartları (m.5, m.6) — açık rıza ve diğer hukuki sebepler.
- Aydınlatma yükümlülüğü (m.10).
- İlgili kişi hakları (m.11) ve başvuru.
- Veri Sorumlusu - Veri İşleyen ayrımı.
- Yurt içi ve yurt dışı aktarım (m.8, m.9).
- VERBİS.
- KVKK Kurumu kararları, yaptırım örnekleri (idari para cezası, TCK m.135-140).
- Şirket içi süreçlere bağlama: aydınlatma metinleri, başvuru e-posta adresi, ihlal hattı.

### 4.2. Phishing & Sosyal Mühendislik

- Yaygın senaryolar: fatura sahtekarlığı, BEC (Business Email Compromise), kargo, banka, IK / İK uzantısı, AI-clone ses, deepfake video.
- "Acillik + otorite + merak" üçlüsü.
- Hover, alan kontrolü, eklerle ilgili davranış.
- Şüpheli mesajı bildirme (one-click report button).
- Vishing (sesli), smishing (SMS), QR phishing.
- "İçeriden istek" denetimi (CFO'dan acil EFT talebi → süreç dışı).
- Phishing simülasyon programı + sonuç odaklı eğitim.

### 4.3. Şifre & MFA

- NIST 800-63B uyumlu parola davranışı (uzunluk, passphrase, parola yöneticisi).
- MFA neden? FIDO2 vs. SMS.
- Push fatigue saldırısı + savunma.
- Hesap ele geçirme tespiti (giriş bildirimleri, anormal aktivite).
- Parola yöneticisi kullanımı (Bitwarden, 1Password kurumsal).
- Hesap kurtarma süreci.

### 4.4. Veri İhlali Tanıma ve Bildirim

- "İhlal" nedir? (kişisel veriye yetkisiz erişim, kayıp, ifşa, değişiklik, hizmet kesintisi).
- Tipik göstergeler: kayıp dizüstü/USB, yanlış e-posta gönderimi, açık link paylaşımı, şüpheli giriş bildirimi.
- Bildirim hattı: nereye, nasıl, ne zaman.
- "Cezalandırılma korkusu yok" — açık bildirim teşviki (kasıtlı olmayan hatalar için).
- 72 saat Kurul'a bildirim arka planı.
- Bildirim örnek formu.

### 4.5. Geliştirici Güvenliği (Detay)

- Tehdit modelleme alıştırması.
- OWASP Top 10 kod örnekleriyle.
- Secrets management, dependency hygiene, SBOM.
- Hassas veri logging yasakları (regex tarama).
- Kişisel veri minimizasyonu — alan eklemeden önce gerekçe.
- Test ortamı veri yasakları.
- Güvenli kod inceleme.

### 4.6. AI / ML Modülü (Yeni)

- LLM Top 10.
- Eğitim verisi mahremiyeti — "modeli ne kadar bilir?"
- Prompt injection ve jailbreak.
- Otomatik karar alma + KVKK m.4 ölçülülük + ilgili kişi hakları.
- Tedarikçi LLM API'lerine kişisel veri gönderme — aktarım rejimi, sözleşme.
- Audit log + insan denetimi.

## 5. Sunum Formatları

- **e-Learning (LMS):** Modül, video, quiz. Ana çatı.
- **Sınıf eğitimi:** Yöneticiler, hassas roller (KVKK Sorumlusu, IR ekibi).
- **Webinar:** Aylık güncel konu (yeni Kurul kararı, sektör vakası).
- **Mikro öğrenme:** 2-5 dk video / infografik / Slack ipucu.
- **Pano / poster:** Ofis fiziksel iletişim.
- **Newsletter:** Aylık güvenlik bülteni.
- **Capture the Flag (CTF):** Yıllık yarışmalı oyunlaştırma.
- **Tabletop:** Üst yönetim için kriz senaryosu.

## 6. Phishing Simülasyon Programı

### 6.1. Çerçeve

- En az **çeyreklik** kampanya (4 / yıl).
- Senaryo zorluk dağılımı (kolay → orta → zor).
- Tıklayan kullanıcı: anında "öğrenme sayfası" (utandırma değil — eğitim).
- Tekrarlı tıklayan kullanıcı: zorunlu ek eğitim, yöneticiyle görüşme.
- "Şüpheli olarak bildirenler" tanınır (gamification, leaderboard).
- KPI: tıklama oranı, raporlama oranı, tekrar oranı.

### 6.2. Senaryo Türleri

- Sahte İK e-postası (zam mektubu, performans değerlendirme).
- Sahte BT e-postası (parola sıfırla, MFA reset).
- Kurumsal araç bildirimi (Microsoft 365, Slack, GitHub).
- Üst yönetim tarafından gönderilmiş gibi (BEC).
- QR code phishing (poster üzerinden).
- Vishing simülasyonu (yıllık 1-2 kez, ekip seçimli).
- AI-clone ses (yıllık 1 kez).

### 6.3. Mahremiyet ve Hukuki Çerçeve

- Simülasyon **çalışan aydınlatma metnine** açıkça yazılmıştır.
- Bireysel başarı / başarısızlık verisi yöneticiye değil, sadece İK + CISO ofisine açıktır.
- Tekrarlı kullanıcı için disiplin **derhal** uygulanmaz; eğitim önerilir.
- Sonuçlar agregate raporlanır (departman ortalama, trend), bireysel "shame" yok.

## 7. Yeni Başlayan Onboarding

| Gün | Aktivite |
|-----|----------|
| -1 | İK pakete erişim aktivasyonu, oryantasyon takvimi |
| 1 | Oryantasyon (KVKK + bilgi güvenliği temelleri sunum) |
| 1 | Gizlilik taahhütnamesi imzası |
| 1-3 | LMS modül 1-2 (KVKK + Bilgi Güvenliği) |
| 4-5 | LMS modül 3-5 (Phishing, MFA, BYOD) |
| 5 | Rol bazlı ek modüller (departmana göre) |
| 7 | Bilgi testi (≥%80 başarı şartı) |
| 14 | İlk phishing simülasyonu |
| 30 | Bağlı yöneticiyle KVKK pratik konuşma |

Tamamlanma kayıtları LMS'de 5 yıl saklanır. Tamamlamayan çalışan üretime erişemez (BT erişim aktivasyonu eğitim tamamlanmasına bağlı).

## 8. Yıllık Tazeleme

- Tüm çalışanlar yılda en az **bir kez** zorunlu tazeleme.
- 30 dk yoğunlaştırılmış (yenilikler, yeni Kurul kararları, sektörel vakalar, yeni teknoloji).
- Bilgi testi (≥%80).
- Yıl içinde **olmayan** çalışan (uzun izin) dönüşte 30 gün ek süre.
- Tamamlamayan çalışan için yöneticiye uyarı + İK takip + ileri uyumsuzlukta disiplin.

## 9. Tetikleyici (Olay-Sonrası) Eğitim

- Şirket içi ihlal/ramak kala olayı sonrası, etkilenen ekip için mikro modül (anonimleştirilmiş vaka).
- KVKK Kurulu kararı yayımlanması — ilgili rolün eğitim modülü güncellenir.
- Yeni teknolojinin benimsenmesi (örn. yeni AI aracı) → kullanım öncesi modül zorunlu.
- Mevzuat değişikliği — 90 gün içinde tüm çalışanlara duyuru + 6 ay içinde tazeleme.

## 10. Etkinlik Ölçümü

### 10.1. Düzeyler (Kirkpatrick'in 4 Seviyesi)

1. **Tepki:** Memnuniyet anketi.
2. **Öğrenme:** Pre-test / post-test bilgi farkı.
3. **Davranış:** Phishing simülasyon raporlama oranı, gerçek olayda raporlama hızı.
4. **Sonuç:** İhlal sayısı / şiddeti, KPI'lar.

### 10.2. KPI'lar

- Tamamlanma oranı (yıllık tazeleme): hedef %100.
- Sınav başarı oranı (≥%80): hedef %95+.
- Phishing tıklama oranı: hedef ≤%10 (yıl sonu); start baseline ölç.
- Phishing rapor oranı (zararsız simülasyon): hedef ≥%50.
- Tekrarlı tıklayan kullanıcı sayısı: hedef azalan trend.
- Olaylarda "ilk tespit kaynağı = kullanıcı raporu" oranı: hedef artan.
- Çalışan memnuniyet (post-eğitim NPS): trend takibi.

## 11. Bütçe ve Kaynaklar

- LMS lisansı (kullanıcı başına yıllık).
- İçerik geliştirme (iç + dış).
- Phishing simülasyon platformu (KnowBe4, Proofpoint, Hoxhunt, Cofense).
- Sertifika eğitim bütçesi (KVKK Sorumlusu, CISO, IR ekibi için yıllık).
- İletişim kampanyası (poster, video, etkinlik).
- Yıllık güvenlik haftası / KVKK gününü kutlama (Türkiye'de "Bilgi Güvenliği Farkındalık Ayı" — Ekim).

## 12. Tedarikçi / Danışman / Stajyer Eğitimi

- Onboarding: kısa (15 dk) bilgi güvenliği + KVKK temelleri.
- Gizlilik taahhütnamesi imzası (bkz. [gizlilik-taahhutnamesi.md](gizlilik-taahhutnamesi.md)).
- Erişim verilen sisteme rol bazlı eğitim.
- Sözleşme süresi 1 yılı aşıyorsa yıllık tazeleme.
- Tedarikçi şirket kendi eğitim politikasıyla yetinemez — kurumumuzun standart modülleri zorunlu.

## 13. Uyumsuzluk Yönetimi

| Durum | Aksiyon |
|-------|---------|
| Yeni başlayan eğitim tamamlamadı | BT erişim aktivasyonu durdurulur, İK + yönetici uyarısı |
| Yıllık tazeleme süresi geçti | Yönetici uyarısı + 14 gün ek süre + sonraki ihlalde disiplin |
| Phishing tıklama tekrarlı | Mikro modül zorunlu + yönetici görüşmesi + 3 ihlalde disiplin |
| Bilgi testi başarısız (3 deneme) | Yüz yüze eğitim + yeniden test |

## 14. KVKK Sorumlusu / IR Ekibi Sertifikalı Eğitim

- Yıllık bütçeli sertifika programı:
  - **CISSP, CISM, CIPP/E (veya yerel benzerleri)**.
  - **ISO 27001 LA / LI**.
  - **ISO 27701 LI**.
  - KVKK Kurum eğitim/sempozyum.
  - Sektör konferansları (CyberWeek TR, ISACA, OWASP TR).
- Bilgi paylaşım ortamı: kurum içi "communities of practice".

## 15. Loglama ve Kanıt

- LMS: tamamlanma, sınav skoru, deneme sayısı.
- Phishing platformu: kampanya, sonuç, tıklayan/raporlayan listesi.
- Eğitim katılım imza listesi (sınıf eğitimleri için).
- Bilgi güvenliği günü etkinlik kaydı.

Saklama: aktif istihdam süresince + 5 yıl ayrılış sonrası.

## 16. Kontrol Listesi

- [ ] Yıllık eğitim takvimi yayınlandı, KVKK Komitesi onaylı mı?
- [ ] Genel + rol bazlı modüller güncel, ≤12 ay revizyon tarihli mi?
- [ ] LMS tüm çalışanlara açık, tamamlanma raporu çeyreklik mi?
- [ ] Tamamlanma oranı %100 hedefe yakın mı?
- [ ] Bilgi testi başarı eşiği ≥%80 mi?
- [ ] Yeni başlayan eğitim erişim aktivasyon koşulu mu?
- [ ] Phishing simülasyon çeyreklik, KPI ölçülüyor mu?
- [ ] Sosyal mühendislik (vishing/AI-clone) simülasyonu yıllık var mı?
- [ ] Tetikleyici olay-sonrası eğitim mekanizması işliyor mu?
- [ ] Yöneticilere özel modül var mı (mover/leaver, raporlama)?
- [ ] Tedarikçi/danışman/stajyer eğitim zorunlu mu?
- [ ] KVKK Sorumlusu / IR ekibi sertifikalı eğitim bütçesi yıllık mı?
- [ ] Bireysel veriler agregate raporlanıyor, çalışan mahremiyeti gözetiliyor mu?
- [ ] Aydınlatma metni eğitim/simülasyonu listeliyor mu?
- [ ] Disiplin sınıflandırması ve eskalasyonu yazılı mı?
- [ ] Yıllık etkinlik (KVKK günü, güvenlik haftası) kutlanıyor mu?

## 17. Yıllık Yönetim Raporu Şablonu

KVKK Komitesi'ne yıllık şu tablo:

- Toplam çalışan / eğitime tabi olan / tamamlayan.
- Sınav başarı oranı.
- Phishing simülasyon trendleri (4 çeyreklik).
- Olaylarda kullanıcı katkısı (ilk tespit kaynağı).
- Tetikleyici eğitim sayısı.
- Disiplin işlemi sayısı.
- Bütçe kullanımı.
- Sonraki yıl planı (yeni modül, yeni hedef KPI).
