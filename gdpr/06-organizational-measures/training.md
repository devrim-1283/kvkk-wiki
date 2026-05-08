---
title:
  en: "Training and Awareness - Onboarding, Annual Refresher, Role-based, Phishing, Kirkpatrick Effectiveness"
  tr: "Eğitim ve Farkındalık - Onboarding, Yıllık Tazeleme, Rol Bazlı, Phishing, Kirkpatrick Etkinliği"
section: "06-organizational-measures"
document_type: "programme"
control_id: "ORG-TRN-01"
owner:
  primary: "DPO"
  secondary: "CISO, HR / People Operations"
review_cycle: "annual"
last_review: "2026-05-08"
next_review: "2027-05-08"
classification: "Internal"
language: ["en", "tr"]
references:
  - "GDPR Art. 32(4), 39(1)(b), 47(2)(n)"
  - "ISO/IEC 27001:2022 clauses 7.2, 7.3; ISO/IEC 27002:2022 control 6.3"
  - "NIST CSF 2.0 PR.AT-1, PR.AT-2"
  - "ENISA Awareness Raising materials"
  - "Kirkpatrick Four Level Training Evaluation Model"
---

## English

# Training and Awareness

## 1. Purpose

Article 32(4) requires the controller to "take steps to ensure that any
natural person acting under the authority of the controller or of the
processor who has access to personal data does not process them except on
instructions from the controller, unless he or she is required to do so by
Union or Member State law." Article 39(1)(b) lists "awareness-raising and
training of staff involved in processing operations" as a DPO duty.

This document defines the training and awareness programme that operationalises
those obligations and supports ISO/IEC 27001 clauses 7.2 (competence) and 7.3
(awareness).

## 2. Audience

The programme covers:

- Permanent employees.
- Contractors and consultants with access to personal data or the
  controller's systems.
- Interns and apprentices.
- Workforce of processors (verified through the DPA - see `vendor-management.md`).
- Temporary and part-time staff.
- Board members where they access processing-related information.

## 3. Curriculum

### 3.1 Onboarding (mandatory within 30 days)

Common to all roles:
- GDPR overview - principles, lawful bases, data subject rights, breach
  obligations.
- The controller's data inventory in plain language.
- Acceptable Use Policy and Confidentiality Undertaking
  (`confidentiality-undertaking.md`).
- Information security baseline - phishing, MFA, password manager, devices,
  data classification, data sharing.
- Incident reporting - what counts, how, to whom.
- Workplace privacy - what the company monitors, what employees retain
  privacy on, contact for the DPO.
- Region-specific addenda (national law, works council expectations).

System access is gated against onboarding completion.

### 3.2 Annual Refresher (mandatory)

- Highlights changes since last cycle (regulatory, internal incidents,
  threat landscape).
- Refreshes principles and incident reporting.
- Re-acknowledgement of policies (`policies-procedures.md`).

Completion deadline tracked; non-completion triggers manager escalation,
then access suspension at 60 days.

### 3.3 Role-Based Modules

Deeper modules for high-risk roles:

| Role | Additional Modules |
|------|--------------------|
| Engineering | Privacy by Design, secure SDLC, OWASP Top 10 / API / LLM, threat modelling (STRIDE + LINDDUN), secrets management, code review |
| Customer support | Identity verification for DSR, special-category data handling, social engineering resistance, escalation patterns |
| Sales / Marketing | Lawful basis selection, ePrivacy / cookie rules, consent capture, prospect data acquisition, profiling and automated decisions |
| HR / People Operations | Employee privacy notice, monitoring proportionality, personnel record retention, recruitment data, occupational health |
| Finance / Procurement | Vendor due diligence, DPA negotiation, payment data minimisation, anti-fraud lawful basis |
| Legal | Article 6 / 9 / 49 reasoning, transfer impact assessments, breach notification drafting, court order handling |
| DPO team | EDPB guidelines deep dive, DPIA facilitation, regulator engagement, supervisory authority cooperation |
| IT / SOC | Detection content, IR runbooks, forensics, evidence handling, log integrity |
| Executives | Strategic risk, accountability, board reporting, regulatory contact decisions |

### 3.4 Just-in-Time Training

- Triggered by:
  - New tool deployment that processes personal data.
  - Phishing failure.
  - Audit finding affecting a team.
  - Regulatory change (EDPB guideline, DPA opinion, court ruling).
- Delivered as short, focused modules; completion tracked.

### 3.5 Microlearning and Awareness

- Monthly newsletter / posts highlighting threats and tips.
- Posters and digital signage rotated quarterly.
- Privacy and Security Week annually.
- Champions network in each business unit.

## 4. Phishing Simulation

- Quarterly campaigns at minimum.
- Realistic, evolving lures (credential capture, attachment, OAuth consent
  abuse, MFA bombing).
- Failure path: educational landing page within 1 second of click; short
  remedial module assigned; manager notified after second failure within 12
  months.
- Whaling and BEC drills targeted at executives and finance roles.
- Reporting button for staff to flag real phish; metrics tracked.
- All simulation logs are personal data; retained 24 months for trending,
  with raw click data pseudonymised after analysis.

## 5. Specialised Drills

- Annual breach response tabletop including DPO, CISO, Legal, Communications,
  business owners, processors as appropriate.
- Half-yearly DSR-handling drill (especially erasure and access requests
  involving complex systems).
- Annual ransomware / restore drill in collaboration with the technical
  programme (`05-technical-measures/backup-recovery.md`).

## 6. Effectiveness Measurement (Kirkpatrick)

| Level | What is Measured | How |
|-------|------------------|-----|
| 1 - Reaction | Did learners find it relevant and engaging? | Post-module survey |
| 2 - Learning | Did learners acquire the knowledge? | Quiz, scenario test |
| 3 - Behaviour | Are learners applying the knowledge? | Phishing rates, DSR-handling quality, secrets-in-code rate, audit findings, near-miss reports |
| 4 - Results | Has the programme improved the privacy posture? | Reduction in incidents, faster MTTR, stable / lowering breach severity, DPA findings |

Measurement results feed annual programme refresh.

## 7. Records and Evidence

For every individual training event:

- Identifier of learner.
- Course identifier and version.
- Completion date and score (if applicable).
- Acknowledgement evidence.
- Re-take history.

For phishing:

- Campaign metadata (date, payload type, audience).
- Per-recipient outcome (delivered, opened, clicked, reported, credentials
  attempted).
- Aggregated dashboards.

Retention: 7 years post-employment (longer where required by law). Records
support audit (`internal-audit.md`) and demonstrate compliance under
Article 5(2).

## 8. Languages and Accessibility

- Materials in operating languages (TR / EN baseline; expand by region).
- WCAG 2.1 AA compliance on digital content.
- Plain-language editing.
- Subtitles / transcripts for video.
- Accommodations process for learners with disabilities.

## 9. Vendor and Processor Workforce

- DPA requires processors to ensure their workforce is bound by
  confidentiality and trained appropriately
  (`vendor-management.md`).
- Critical processors required to share annual training summary.
- Joint exercises with major processors when feasible.

## 10. KPIs

| Metric | Target |
|--------|--------|
| Onboarding completion within 30 days | 100 % |
| Annual refresher completion within window | >= 98 % |
| Phishing reporting rate (proactive) | >= 30 % |
| Phishing failure rate (campaign) | < 5 % steady state |
| Repeat phishing failures within 12 months | < 1 % of workforce |
| DSR drill performed (per cycle) | 100 % on plan |
| Breach tabletop performed (per year) | 100 % |
| Role-based modules assigned to relevant population | 100 % |

## 11. Mapping

| Requirement | GDPR | ISO 27001/2:2022 | NIST CSF 2.0 |
|-------------|------|------------------|--------------|
| Workforce instructions | Art. 32(4) | 6.3 | PR.AT-1 |
| Awareness | Art. 39(1)(b) | 6.3 | PR.AT-1 |
| Competence | n/a | 7.2 (27001) | PR.AT-2 |
| Awareness on duties | n/a | 7.3 (27001) | PR.AT-1 |

## 12. Related Documents

- `policies-procedures.md` - documents reinforced through training.
- `confidentiality-undertaking.md` - signed at onboarding.
- `vendor-management.md` - processor obligations.
- `internal-audit.md` - sampling of training completion.

---

## Türkçe

# Eğitim ve Farkındalık

## 1. Amaç

Madde 32(4), kontrolörün "kontrolör veya işleyicinin yetkisi altında hareket
eden ve kişisel verilere erişimi olan herhangi bir gerçek kişinin Birlik
veya Üye Devlet hukukunun bunu gerektirmediği sürece kontrolörün talimatları
dışında bunları işlememesini sağlamak için adımlar atmasını" gerektirir.
Madde 39(1)(b), DPO görevi olarak "işleme operasyonlarına dahil olan
personelin farkındalığının artırılması ve eğitimini" listeler.

Bu belge, bu yükümlülükleri operasyonelleştiren ve ISO/IEC 27001 madde 7.2
(yetkinlik) ile 7.3 (farkındalık) gerekliliklerini destekleyen eğitim ve
farkındalık programını tanımlar.

## 2. Hedef Kitle

Program şunları kapsar:

- Daimi çalışanlar.
- Kişisel veriye veya kontrolörün sistemlerine erişimi olan yükleniciler ve
  danışmanlar.
- Stajyerler ve çıraklar.
- İşleyicilerin iş gücü (DPA aracılığıyla doğrulanmış - bkz.
  `vendor-management.md`).
- Geçici ve yarı zamanlı personel.
- İşleme ile ilgili bilgilere erişen yönetim kurulu üyeleri.

## 3. Müfredat

### 3.1 Onboarding (30 gün içinde zorunlu)

Tüm rollere ortak:
- GDPR genel bakışı - ilkeler, yasal dayanaklar, veri sahibi hakları, ihlal
  yükümlülükleri.
- Kontrolörün veri envanteri sade dilde.
- Kabul Edilebilir Kullanım Politikası ve Gizlilik Taahhütnamesi
  (`confidentiality-undertaking.md`).
- Bilgi güvenliği temeli - phishing, MFA, parola yöneticisi, cihazlar, veri
  sınıflandırma, veri paylaşımı.
- Olay raporlama - neyin sayıldığı, nasıl, kime.
- İşyeri gizliliği - şirketin ne izlediği, çalışanların gizliliği koruduğu
  alanlar, DPO için iletişim.
- Bölgeye özel ekler (ulusal hukuk, işyeri konseyi beklentileri).

Sistem erişimi onboarding tamamlamaya karşı kapı tutulur.

### 3.2 Yıllık Tazeleme (zorunlu)

- Son döngüden bu yana değişiklikleri (düzenleyici, dahili olaylar, tehdit
  ortamı) vurgular.
- İlkeleri ve olay raporlamayı tazeler.
- Politikaların yeniden onayı (`policies-procedures.md`).

Tamamlama son tarihi izlenir; tamamlamama yöneticiye yükseltme tetikler,
ardından 60 günde erişim askıya alınır.

### 3.3 Rol Bazlı Modüller

Yüksek riskli roller için daha derin modüller:

| Rol | Ek Modüller |
|-----|-------------|
| Mühendislik | Tasarımdan Gizlilik, güvenli SDLC, OWASP Top 10 / API / LLM, tehdit modelleme (STRIDE + LINDDUN), sır yönetimi, kod incelemesi |
| Müşteri desteği | DSR için kimlik doğrulama, özel-nitelikli veri işleme, sosyal mühendislik direnci, yükseltme örüntüleri |
| Satış / Pazarlama | Yasal dayanak seçimi, ePrivacy / çerez kuralları, onay yakalama, aday verisi edinme, profilleme ve otomatik kararlar |
| İK / İnsan Kaynakları | Çalışan gizlilik bildirimi, izleme orantılılığı, personel kaydı saklama, işe alım verisi, iş sağlığı |
| Finans / Tedarik | Tedarikçi durum tespiti, DPA müzakeresi, ödeme verisi minimizasyonu, dolandırıcılık karşıtı yasal dayanak |
| Hukuk | Madde 6 / 9 / 49 muhakemesi, aktarım etki değerlendirmeleri, ihlal bildirimi yazımı, mahkeme kararı işleme |
| DPO ekibi | EDPB rehberlerine derin dalış, VKD kolaylaştırma, düzenleyici etkileşim, denetim otoritesi işbirliği |
| BT / SOC | Algılama içeriği, IR runbook'lar, adli bilim, kanıt işleme, log bütünlüğü |
| Yöneticiler | Stratejik risk, hesap verebilirlik, yönetim kuruluna raporlama, düzenleyici iletişim kararları |

### 3.4 Tam Zamanında Eğitim

- Tetikleyiciler:
  - Kişisel veri işleyen yeni araç dağıtımı.
  - Phishing başarısızlığı.
  - Bir takımı etkileyen denetim bulgusu.
  - Düzenleyici değişiklik (EDPB rehberi, DPA görüşü, mahkeme kararı).
- Kısa, odaklı modüller olarak teslim edilir; tamamlama izlenir.

### 3.5 Mikro Öğrenme ve Farkındalık

- Tehditleri ve ipuçlarını vurgulayan aylık bülten / gönderiler.
- Üç aylık döndürülen posterler ve dijital tabela.
- Yıllık Gizlilik ve Güvenlik Haftası.
- Her iş biriminde şampiyonlar ağı.

## 4. Phishing Simülasyonu

- Asgari üç aylık kampanyalar.
- Gerçekçi, gelişen tuzaklar (kimlik bilgisi yakalama, ek, OAuth onay
  kötüye kullanımı, MFA bombalama).
- Başarısızlık yolu: tıklamadan 1 saniye içinde eğitici iniş sayfası;
  kısa düzeltme modülü atanır; 12 ay içinde ikinci başarısızlıktan sonra
  yöneticiye bildirilir.
- Yöneticiler ve finans rollerine yönelik whaling ve BEC tatbikatları.
- Personelin gerçek phish'i işaretlemesi için raporlama düğmesi; metrikler
  izlenir.
- Tüm simülasyon logları kişisel veridir; trend için 24 ay saklanır, ham
  tıklama verisi analiz sonrası pseudonimleştirilir.

## 5. Özel Tatbikatlar

- DPO, CISO, Hukuk, İletişim, iş sahipleri ve uygun olduğunda işleyiciler
  dahil yıllık ihlal müdahale masa başı tatbikatı.
- Altı aylık DSR işleme tatbikatı (özellikle karmaşık sistemler içeren
  silme ve erişim talepleri).
- Teknik program işbirliğiyle yıllık fidye yazılımı / geri yükleme tatbikatı
  (`05-technical-measures/backup-recovery.md`).

## 6. Etkinlik Ölçümü (Kirkpatrick)

| Seviye | Ne Ölçülür | Nasıl |
|--------|------------|-------|
| 1 - Tepki | Öğrenenler ilgili ve ilgi çekici buldu mu? | Modül sonrası anket |
| 2 - Öğrenme | Öğrenenler bilgiyi edindi mi? | Kısa sınav, senaryo testi |
| 3 - Davranış | Öğrenenler bilgiyi uyguluyor mu? | Phishing oranları, DSR işleme kalitesi, koddaki sırlar oranı, denetim bulguları, kıl payı raporları |
| 4 - Sonuçlar | Program gizlilik duruşunu iyileştirdi mi? | Olaylarda azalma, daha hızlı MTTR, sabit / düşen ihlal ciddiyeti, DPA bulguları |

Ölçüm sonuçları yıllık program tazelemesini besler.

## 7. Kayıtlar ve Kanıt

Her bireysel eğitim olayı için:

- Öğrenenin tanımlayıcısı.
- Kurs tanımlayıcısı ve sürümü.
- Tamamlama tarihi ve puanı (geçerliyse).
- Onay kanıtı.
- Yeniden alma geçmişi.

Phishing için:

- Kampanya meta verisi (tarih, yük türü, hedef kitle).
- Alıcı başına sonuç (teslim edildi, açıldı, tıklandı, raporlandı, kimlik
  bilgisi denendi).
- Toplulaştırılmış gösterge tabloları.

Saklama: iş ilişkisi sonrası 7 yıl (hukukun gerektirdiği yerde daha uzun).
Kayıtlar denetimi destekler (`internal-audit.md`) ve Madde 5(2) altında
uyumluluğu gösterir.

## 8. Diller ve Erişilebilirlik

- İşletim dillerinde malzemeler (TR / EN temel; bölgeye göre genişletilir).
- Dijital içerikte WCAG 2.1 AA uyumu.
- Sade dil düzenlemesi.
- Video için altyazılar / transkriptler.
- Engelli öğrenenler için uyumluluk süreci.

## 9. Tedarikçi ve İşleyici İş Gücü

- DPA, işleyicilerin iş gücünün gizlilikle bağlanmasını ve uygun şekilde
  eğitilmesini gerektirir (`vendor-management.md`).
- Kritik işleyicilerin yıllık eğitim özetini paylaşması gerekir.
- Mümkün olduğunda büyük işleyicilerle ortak tatbikatlar.

## 10. KPI'lar

| Metrik | Hedef |
|--------|-------|
| 30 gün içinde onboarding tamamlama | %100 |
| Pencere içinde yıllık tazeleme tamamlama | >= %98 |
| Phishing raporlama oranı (proaktif) | >= %30 |
| Phishing başarısızlık oranı (kampanya) | Sabit durum < %5 |
| 12 ay içinde tekrarlayan phishing başarısızlıkları | İş gücünün < %1'i |
| Yapılan DSR tatbikatı (her döngü) | %100 planda |
| Yapılan ihlal masa başı (her yıl) | %100 |
| İlgili popülasyona atanan rol bazlı modüller | %100 |

## 11. Eşleme

| Gereklilik | GDPR | ISO 27001/2:2022 | NIST CSF 2.0 |
|------------|------|------------------|--------------|
| İş gücü talimatları | Md. 32(4) | 6.3 | PR.AT-1 |
| Farkındalık | Md. 39(1)(b) | 6.3 | PR.AT-1 |
| Yetkinlik | yok | 7.2 (27001) | PR.AT-2 |
| Görevlere ilişkin farkındalık | yok | 7.3 (27001) | PR.AT-1 |

## 12. İlgili Belgeler

- `policies-procedures.md` - eğitim aracılığıyla pekiştirilen belgeler.
- `confidentiality-undertaking.md` - onboarding'te imzalanır.
- `vendor-management.md` - işleyici yükümlülükleri.
- `internal-audit.md` - eğitim tamamlama örneklemesi.
