---
title:
  en: "Breach Tabletop Exercises and Readiness KPIs"
  tr: "İhlal Masa Başı Tatbikatları ve Hazırlık KPI'ları"
section: "08-breach-management"
document_id: "BR-EX-001"
owner: "CISO / DPO"
classification: "Internal"
version: "1.0"
last_review: "2026-05-08"
next_review: "2027-05-08"
language: ["en", "tr"]
references:
  - "GDPR Art. 32(1)(d) — Process for regularly testing, assessing and evaluating effectiveness of measures"
  - "ISO/IEC 27035-3:2020 — Guidelines for ICT incident response operations"
  - "NIST SP 800-84 — Guide to Test, Training, and Exercise Programs for IT Plans and Capabilities"
  - "ENISA — Good Practice Guide on National Exercises"
  - "EDPB Guidelines 9/2022"
---

## English

### 1. Why tabletop exercises

Article 32(1)(d) GDPR makes the regular testing, assessment, and evaluation of the effectiveness of technical and organisational measures a core obligation. Tabletop exercises are the most cost-effective form of evidence that the controller's breach response is real, not theoretical. They surface gaps in runbooks, role coverage, communication paths, and decision authority before a real incident exposes them.

A tabletop is not a drill of technical recovery (that is a recovery test, run separately). A tabletop is a paper-based, time-compressed walkthrough of decision-making under realistic uncertainty. It tests whether the people in the room — DPO, CISO, Legal, Comms, Engineering, Executive — make defensible decisions on the same facts a real breach would present.

### 2. Annual schedule

| Quarter | Exercise | Lead | Participants |
|---------|---------|------|--------------|
| Q1 | Ransomware affecting customer-facing service | CSIRT lead | Full CSIRT + executive sponsor |
| Q2 | Insider exfiltration of HR data | DPO | DPO, HR, Legal, CISO, CSIRT |
| Q3 | Third-party processor breach (cloud SaaS) | DPO | DPO, vendor management, Legal, Engineering |
| Q4 | Cross-border BEC with material data exposure | CISO | Full CSIRT + Comms + executive sponsor |
| Annual | Full board-level briefing using Q1–Q4 outputs | Executive sponsor | Board, audit committee |

In addition, an unannounced micro-exercise (60 minutes, 3 participants) is run quarterly to test the on-call escalation tree.

### 3. Exercise design principles

Each exercise is designed by the exercise lead one month in advance and approved by the DPO and CISO jointly. The design includes:

1. **Scenario brief**: a one-page narrative describing the initial facts. Realistic, drawn from threat intelligence, anonymised from real industry incidents.
2. **Injects**: 5–8 timed updates that change facts during the exercise (e.g. "30 minutes in, the legal team receives a media enquiry"; "60 minutes in, a customer posts on X claiming their data is for sale").
3. **Discussion questions**: aligned to decision points (Article 33 trigger? Article 34 trigger? law enforcement engagement? customer notification?).
4. **Observers**: silent note-takers who capture decisions, gaps, and time stamps.
5. **Hot wash**: 30-minute structured debrief immediately after the exercise.
6. **Cold wash**: written report within 5 working days; CAPA actions assigned with owners and due dates.

### 4. Five mandatory scenarios

#### 4.1 Ransomware with exfiltration

A LockBit-derivative encrypts production database servers. A ransom note threatens publication of customer data within 96 hours. Initial access traced to a phished contractor VPN credential. EDR blocks lateral movement on a secondary subnet. Backups exist but the most recent (12 hours old) is on a SAN that the attacker briefly accessed. Key decision points: pay or not, when to disclose, how to scope the exfiltrated dataset, what to tell employees who are also affected.

#### 4.2 Insider data theft

An HR analyst is preparing to leave. DLP flags a download of 4,200 employee records to a personal cloud account. The analyst's current notice period ends in 3 days. Manager wants to "talk to them first". DPO must determine the breach scope. Legal must navigate employment law and evidence preservation. Executive must decide whether to pursue criminal complaint. Key decision points: when to suspend, how to interview, how to scope, what to say to other employees.

#### 4.3 Third-party processor breach

A SaaS vendor used for customer support emails the controller stating that "an unauthorised access incident may have affected our customers". The vendor offers no specifics for 18 hours. Customers begin asking why their support tickets contain data that has been seen on a known leak forum. Key decision points: when does the controller's awareness clock start, how to extract specifics from the processor under Article 28(3)(f), how to communicate to data subjects when facts are still partial.

#### 4.4 Cross-border BEC

A finance manager's mailbox is compromised. The attacker uses inbox rules to filter and deletes evidence. The compromise is detected when a vendor calls about an unpaid invoice that was redirected. The mailbox contains contracts with personal data of EU and Turkish counterparties. Key decision points: lead SA designation under Article 56, communication strategy across multiple jurisdictions and languages, MFA reset cascade, evidence preservation for criminal report.

#### 4.5 Lost executive laptop

A board member loses a laptop on a train. The laptop has full-disk encryption (BitLocker), but the login session was active when lost (lid was closed but device was sleeping). The laptop contains board-pack PDFs with personal data of senior employees, a snapshot of the M&A target's data room (third-party personal data), and a copy of the upcoming workforce reduction plan. Key decision points: are we covered by the encryption exemption, what is the residual risk in sleep state, is law enforcement engaged, what is told to the board.

### 5. Roles during a tabletop

| Role | Responsibility during exercise |
|------|-------------------------------|
| Exercise lead | Drives scenario, injects updates, controls clock, keeps debate on track |
| Scribe | Records decisions, time stamps, points of disagreement |
| Observers | Capture KPI data, identify gaps, do not participate in discussion |
| Players | Operate as in real incident; cannot consult external resources unless realistic |
| Subject-matter advisor | Available to answer factual questions about systems, vendors, data; not a decision-maker |

The exercise lead may not double as a player. If the CSIRT lead is also the exercise lead, a deputy plays the CSIRT lead role.

### 6. Hot wash structure

Immediately after the exercise, 30 minutes:

1. Each player gives a 60-second self-assessment of their performance.
2. Scribe presents the decision timeline.
3. Observers present the gap list.
4. Group discusses the three biggest issues.
5. Lead drafts the immediate CAPA candidates on a board.
6. Photo of the board is the closing artefact.

### 7. Cold wash report template

Within 5 working days the exercise lead delivers a written report:

1. **Scenario summary** (1 page).
2. **Timeline of decisions** (with timestamps and decision-makers).
3. **KPI scores** (Section 8).
4. **Gap inventory** (categorised: process, technology, people, governance).
5. **CAPA actions** (SMART, with owner, target date, success criteria, link to internal ticket).
6. **Lessons learned** (narrative).
7. **Recommendations for next exercise**.

The report is reviewed by DPO, CISO, and the executive sponsor. The annual board-level briefing aggregates the four quarterly reports.

### 8. KPIs

The five core KPIs measured in every exercise (and tracked across real incidents):

| KPI | Definition | Target |
|-----|-----------|--------|
| MTTD — Mean Time to Detect | Time from underlying event to incident ticket open | < 4 hours for SEV-1, < 12 hours for SEV-2 |
| MTTI — Mean Time to Investigate | Time from ticket open to confirmed scope | < 6 hours for confirming awareness |
| MTTC — Mean Time to Contain | Time from confirmed awareness to first containment action that stops further data loss | < 2 hours |
| MTTN — Mean Time to Notify | Time from confirmed awareness to Article 33 submission | < 72 hours, target < 48 hours |
| MTTR — Mean Time to Recover | Time from containment to full service restoration | per service-level objective |

Supplementary KPIs:

- **Decision quality score**: post-hoc rating by independent reviewer of each major decision (1–5 scale, anchor descriptions).
- **Communication latency**: time between decision and communication to affected stakeholders.
- **Stakeholder notification completeness**: percentage of required stakeholders contacted within target window.
- **Phased notification rate**: percentage of incidents requiring Article 33(4) phased notification (high rate may indicate scoping weakness).

### 9. Maturity model

The CSIRT maturity is evaluated annually on the following 5-stage scale:

| Level | Description |
|-------|------------|
| 1 — Ad hoc | Response is improvised; runbooks not consulted; KPIs not measured |
| 2 — Repeatable | Runbooks exist and are followed; KPIs measured but not analysed |
| 3 — Defined | Runbooks tested annually; KPIs analysed; CAPA tracked |
| 4 — Managed | KPIs trend-analysed; gaps systematically closed; tabletop scenarios derived from threat intelligence |
| 5 — Optimising | Continuous improvement loop; cross-team rotations; external benchmarking; threat-led exercises |

The CISO presents the maturity self-assessment to the audit committee annually with evidence.

### 10. External validation

Every two years, an external advisor (law firm with breach practice, or specialist consultancy) facilitates one tabletop. The external advisor produces a candid report independent of internal politics. The report is treated as privileged where applicable.

### 11. Integrating real-incident lessons

When a real incident is closed, its RCA outputs are incorporated into the next tabletop scenario. The objective is to ensure that lessons are not buried in the closed-incident archive but actively rehearsed.

### 12. Confidentiality of exercise materials

Tabletop scenarios, especially those drawn from real-world threat intelligence, are sensitive:

- treated as Internal — Restricted at minimum;
- not shared with vendors or external parties without NDA;
- archived in the secure exercise repository with access by exercise lead and DPO;
- destroyed or anonymised before any external publication or training reuse.

### 13. Engagement of the board and audit committee

Tabletop participation by the executive sponsor (and at least one board observer) is mandatory annually. The board audit committee receives the annual aggregate report and the maturity-model evidence. The risk register and the breach KPIs are linked.

---

## Türkçe

### 1. Masa başı tatbikatları neden

GDPR Madde 32(1)(d), teknik ve organizasyonel önlemlerin etkinliğinin düzenli olarak test edilmesini, değerlendirilmesini ve izlenmesini temel bir yükümlülük olarak belirler. Masa başı tatbikatları, veri sorumlusunun ihlal müdahalesinin gerçek olduğunun, teorik olmadığının en uygun maliyetli kanıt biçimidir. Gerçek bir olay onları açığa çıkarmadan önce runbook'lardaki, rol kapsamındaki, iletişim yollarındaki ve karar yetkisindeki boşlukları gün yüzüne çıkarırlar.

Masa başı bir teknik kurtarma tatbikatı değildir (bu ayrı yapılan bir kurtarma testidir). Masa başı, gerçekçi belirsizlik altında karar vermenin kâğıt tabanlı, zaman sıkıştırmalı bir gözden geçirmesidir.

### 2. Yıllık takvim

| Çeyrek | Tatbikat | Lider | Katılımcılar |
|--------|----------|-------|--------------|
| Ç1 | Müşteriye dönük hizmeti etkileyen fidye yazılımı | CSIRT lideri | Tam CSIRT + sponsor |
| Ç2 | İK verisinin içeriden sızdırılması | VKK | VKK, İK, Hukuk, CISO, CSIRT |
| Ç3 | Üçüncü taraf veri işleyen ihlali | VKK | VKK, tedarikçi yönetimi, Hukuk, Mühendislik |
| Ç4 | Önemli veri ifşası içeren sınır ötesi BEC | CISO | Tam CSIRT + İletişim + sponsor |
| Yıllık | Ç1-Ç4 çıktılarını kullanan kurul düzeyinde brifing | Sponsor | Yönetim kurulu, denetim komitesi |

Buna ek olarak, üç ayda bir nöbet yükseltme ağacını test etmek için duyurusuz mikro tatbikat (60 dakika, 3 katılımcı) yapılır.

### 3. Tatbikat tasarım ilkeleri

Her tatbikat, tatbikat lideri tarafından bir ay önceden tasarlanır ve VKK ile CISO tarafından ortaklaşa onaylanır.

1. **Senaryo özeti**: ilk olguları anlatan tek sayfalık bir anlatı.
2. **İncekler**: tatbikat sırasında olguları değiştiren 5–8 zamanlı güncelleme.
3. **Tartışma soruları**: karar noktalarına hizalanır.
4. **Gözlemciler**: kararları, boşlukları ve zaman damgalarını yakalayan sessiz not alıcılar.
5. **Sıcak yıkama**: tatbikatın hemen ardından 30 dakikalık yapılandırılmış değerlendirme.
6. **Soğuk yıkama**: 5 iş günü içinde yazılı rapor.

### 4. Beş zorunlu senaryo

#### 4.1 Sızıntılı fidye yazılımı

LockBit türevi üretim veritabanlarını şifreler. Fidye notu 96 saat içinde müşteri verilerinin yayınlanmasını tehdit eder. İlk erişim, oltalanmış bir yüklenici VPN kimlik bilgisine kadar izlenir.

#### 4.2 İçeriden veri hırsızlığı

Bir İK analisti ayrılmaya hazırlanır. DLP, kişisel bir bulut hesabına 4.200 çalışan kaydının indirilmesini işaretler. Analistin mevcut ihbar süresi 3 gün içinde sona erer.

#### 4.3 Üçüncü taraf veri işleyen ihlali

Müşteri desteği için kullanılan bir SaaS satıcısı, "yetkisiz bir erişim olayı müşterilerimizi etkilemiş olabilir" diye veri sorumlusuna e-posta gönderir.

#### 4.4 Sınır ötesi BEC

Bir finans yöneticisinin posta kutusu tehlikeye girer. Saldırgan, kanıtları filtrelemek ve silmek için gelen kutusu kuralları kullanır.

#### 4.5 Kayıp yönetici dizüstü bilgisayarı

Bir yönetim kurulu üyesi trende bir dizüstü bilgisayarı kaybeder. Dizüstü tam disk şifrelemesine (BitLocker) sahiptir, ancak kaybolduğunda oturum aktifti.

### 5. Tatbikat sırasında roller

| Rol | Tatbikat sırasında sorumluluk |
|-----|-----------------------------|
| Tatbikat lideri | Senaryoyu yürütür, güncellemeler enjekte eder, saati kontrol eder |
| Kâtip | Kararları, zaman damgalarını, anlaşmazlık noktalarını kaydeder |
| Gözlemciler | KPI verilerini yakalar, boşlukları belirler |
| Oyuncular | Gerçek olayda olduğu gibi çalışır |
| Konu uzmanı danışmanı | Sistemler, satıcılar, veriler hakkında olgusal soruları yanıtlar |

### 6. Sıcak yıkama yapısı

Tatbikatın hemen ardından, 30 dakika:

1. Her oyuncu performansının 60 saniyelik bir öz değerlendirmesini yapar.
2. Kâtip karar zaman çizelgesini sunar.
3. Gözlemciler boşluk listesini sunar.
4. Grup en büyük üç sorunu tartışır.
5. Lider acil CAPA adaylarını panoya çizer.
6. Panonun fotoğrafı kapanış yapıtıdır.

### 7. Soğuk yıkama rapor şablonu

5 iş günü içinde yazılı rapor:

1. **Senaryo özeti** (1 sayfa).
2. **Karar zaman çizelgesi**.
3. **KPI puanları** (Bölüm 8).
4. **Boşluk envanteri** (kategorize: süreç, teknoloji, insan, yönetişim).
5. **CAPA eylemleri** (SMART, sahip, hedef tarih, başarı kriteri, iç bilet bağlantısı).
6. **Çıkarılan dersler**.
7. **Sonraki tatbikat için öneriler**.

### 8. KPI'lar

Her tatbikatta ölçülen beş temel KPI:

| KPI | Tanım | Hedef |
|-----|-------|-------|
| MTTD — Tespite Kadar Geçen Ortalama Süre | Temel olaydan olay biletinin açılmasına kadar | SEV-1 için < 4 saat, SEV-2 için < 12 saat |
| MTTI — Soruşturmaya Kadar Geçen Ortalama Süre | Bilet açılmasından kapsamın doğrulanmasına | < 6 saat |
| MTTC — Kontrol Altına Almaya Kadar Geçen Ortalama Süre | Doğrulanmış farkındalıktan ilk kontrol altına alma eylemine | < 2 saat |
| MTTN — Bildirime Kadar Geçen Ortalama Süre | Doğrulanmış farkındalıktan Madde 33 gönderimine | < 72 saat, hedef < 48 |
| MTTR — Kurtarmaya Kadar Geçen Ortalama Süre | Kontrol altına almadan tam hizmet restorasyonuna | hizmet seviyesi hedefine göre |

### 9. Olgunluk modeli

CSIRT olgunluğu yıllık olarak değerlendirilir:

| Düzey | Açıklama |
|-------|----------|
| 1 — Ad hoc | Müdahale doğaçlamadır; runbook'lar danışılmaz |
| 2 — Tekrarlanabilir | Runbook'lar var ve takip edilir; KPI'lar ölçülür ama analiz edilmez |
| 3 — Tanımlı | Runbook'lar yıllık test edilir; KPI'lar analiz edilir; CAPA izlenir |
| 4 — Yönetilen | KPI'lar trend analizi; boşluklar sistematik kapatılır |
| 5 — İyileştiren | Sürekli iyileştirme döngüsü; çapraz takım rotasyonları; dış kıyaslama |

### 10. Dış doğrulama

İki yılda bir, harici bir danışman bir masa başını yönetir. Harici danışman iç siyasetten bağımsız samimi bir rapor üretir.

### 11. Gerçek olay derslerini entegre etme

Bir gerçek olay kapatıldığında, RCA çıktıları bir sonraki masa başı senaryosuna dahil edilir.

### 12. Tatbikat materyallerinin gizliliği

Masa başı senaryoları en azından İç — Kısıtlı olarak işlem görür.

### 13. Yönetim kurulu ve denetim komitesinin katılımı

Yönetici sponsorun (ve en az bir kurul gözlemcisinin) yıllık masa başı katılımı zorunludur.
