---
title:
  en: "Root Cause Analysis and CAPA"
  tr: "Kök Neden Analizi ve CAPA"
section: "08-breach-management"
document_id: "BR-RCA-001"
owner: "CISO / DPO"
classification: "Internal"
version: "1.0"
last_review: "2026-05-08"
next_review: "2027-05-08"
language: ["en", "tr"]
references:
  - "GDPR Art. 32 — Security of processing"
  - "GDPR Art. 33(3)(d) — Measures taken or proposed"
  - "ISO/IEC 27035-1:2023 — Lessons learnt phase"
  - "ISO 9001:2015 §10.2 — Nonconformity and corrective action"
  - "ISO 13485:2016 — CAPA in regulated quality systems (reference for CAPA discipline)"
  - "Apollo Root Cause Analysis methodology (Dean Gano)"
  - "Ishikawa Fishbone Diagram (Kaoru Ishikawa)"
---

## English

### 1. Purpose and scope

Root cause analysis (RCA) is the structured investigation that follows every personal data breach (and every near-miss serious enough to be classified as SEV-2 or higher). Its purpose is to identify causal factors deep enough that the corrective and preventive actions (CAPA) derived from them will reduce the probability or severity of recurrence in a measurable way.

This document defines the RCA discipline applied to breaches and to material near-misses. It is mandatory: a breach is not closed until the RCA is delivered, the CAPA is registered, and the executive sponsor has signed off the action plan.

### 2. Triggers for RCA

| Trigger | RCA depth |
|---------|----------|
| Personal data breach with Article 33 notification | Full four-layer RCA |
| Personal data breach without notification (Article 33(5) register entry only) | Full four-layer RCA |
| Near-miss SEV-2 or higher (e.g. DLP would have allowed exfiltration if not for last-mile control) | Full four-layer RCA |
| Near-miss SEV-3 | Lightweight 5 Whys + targeted CAPA |
| Repeat incident in same control area within 12 months | Full four-layer RCA + governance review |

### 3. Methodology stack

Three complementary techniques are used in combination, not in isolation. Selection depends on the complexity of the case.

#### 3.1 5 Whys

The 5 Whys is used as the entry technique for every RCA. It is fast, lightweight, and exposes the obvious chain of causation. It is not sufficient alone — it tends to fixate on a single causal chain and miss systemic factors — but it is a useful warm-up.

Each "why" must be evidence-backed. Asserted causes without evidence are flagged and parked for verification.

#### 3.2 Fishbone (Ishikawa)

The fishbone diagram is used for any RCA where multiple contributing factors are likely. The categories adapted for breach RCA:

- **People** (training, awareness, fatigue, intent, manning levels)
- **Process** (runbooks, change management, joiner/mover/leaver, vendor management)
- **Technology** (controls, configurations, asset inventory, patching)
- **Environment** (physical security, network segmentation, third-party connectivity)
- **Measurement** (logging, monitoring, alerting, metrics)
- **Management** (governance, prioritisation, resourcing, accountability)

Each branch is populated with contributing factors evidenced by incident artefacts. Factors are ranked by probability and impact.

#### 3.3 Apollo RCA (causal chains)

Apollo RCA (Dean Gano) is used for serious breaches. It builds a directed graph of causes, distinguishing actions and conditions, and continues until each root reaches a control-actionable level. It explicitly accepts multiple roots and rejects the convenient single "root" simplification.

The Apollo chart for a breach is preserved as a permanent artefact, version-controlled, and revisited if the same conditions reappear.

### 4. Four-layer model

For full-depth RCA, every breach is examined through four layers. A complete RCA must propose CAPAs across at least three of the four layers; a single-layer fix is treated as evidence of inadequate analysis.

#### Layer 1 — Technical

Did a technical control fail to operate as designed, or was no control present where one was needed? Examples:

- Missing or misconfigured WAF rule.
- DLP signature not deployed to the relevant data class.
- MFA not enforced for the affected access path.
- Patching SLA missed for the exploited vulnerability.
- Encryption not applied to the affected data store.
- Excess privilege on the affected account.
- Inadequate logging that prevented timely detection.

#### Layer 2 — Human

Did a person make a decision or take an action that contributed to the breach? This layer is examined without blame and with full attention to context:

- Was the person trained?
- Was the workload reasonable?
- Was the procedure clear?
- Was the right tool available?
- Was the warning signal salient and unambiguous?

This layer never concludes "the user clicked a phishing link, end of story". The question is what made the system tolerant of that click.

#### Layer 3 — Process

Did a process or procedure fail to operate as designed, or was no process present where one was needed?

- Joiner/mover/leaver not executed cleanly.
- Vendor management did not catch a sub-processor change.
- Change management approved a change without security review.
- Incident classification was wrong, leading to delayed escalation.
- Runbook had a gap for the specific scenario encountered.

#### Layer 4 — Governance

Was there an issue in how the organisation prioritised, resourced, or held itself accountable?

- Risk register did not reflect the threat.
- Investment in the affected control was deprioritised the previous year.
- Reporting line for the affected risk was unclear.
- Board did not receive the relevant signal.
- Audit findings on related issues were not closed.

### 5. RCA workflow

| Day | Activity | Owner |
|-----|---------|-------|
| Day 0 (incident closure) | RCA scoping meeting; team assembled | DPO + CISO |
| Day 1–3 | Evidence collection (timeline, logs, interviews); 5 Whys draft | RCA lead |
| Day 4–7 | Fishbone workshop; Apollo chart for serious cases | RCA lead |
| Day 8–10 | Four-layer review; CAPA draft | RCA lead + control owners |
| Day 11–14 | Stakeholder review (DPO, CISO, Legal, Engineering, exec sponsor) | RCA lead |
| Day 15 | Final RCA report and CAPA register entry | RCA lead |
| Day 30 | Executive sponsor sign-off; CAPA tracker active | Exec sponsor |
| Day 90, 180, 365 | CAPA progress reviews | DPO + CISO |

### 6. CAPA discipline

CAPA actions are SMART:

- **Specific**: a single, named change with a verifiable outcome.
- **Measurable**: success criteria stated in numeric or boolean terms.
- **Assigned**: a single named owner (not a team).
- **Realistic**: feasible within the authority and resources of the owner.
- **Time-bound**: explicit due date and review checkpoints.

Every CAPA is recorded with:

| Field | Description |
|-------|------------|
| CAPA ID | `CAPA-YYYY-NNNN` |
| Source | RCA document ID |
| Layer | Technical / Human / Process / Governance |
| Description | The action |
| Success criteria | Verifiable test |
| Owner | Single named individual |
| Sponsor | Executive accountable |
| Due date | ISO date |
| Review dates | 30 / 90 / 180 / 365 days |
| Status | Open / In progress / Validated / Closed |
| Evidence of closure | Link to artefact (PR, runbook update, training completion record, control test) |
| Effectiveness review | Performed at Day 365: did this CAPA actually reduce risk? Evidence. |

CAPAs are not closed when the action is taken. They are closed when the effectiveness review at Day 365 (or earlier if criteria allow) confirms the intended risk reduction. CAPAs that fail effectiveness review are reopened with new actions.

### 7. Common CAPA categories

Across recurring breach types, common CAPA categories include:

- **Identity and access**: privilege right-sizing, just-in-time access, FIDO2 keys for high-risk roles, lifecycle automation.
- **Detection**: new alert rules, baseline updates, additional log sources, threat hunting cadence.
- **Containment readiness**: pre-staged isolation actions, network segmentation, kill-switch playbooks.
- **Vendor management**: revised DPAs, sub-processor approval gates, audit clauses, exit testing.
- **Training**: targeted training for affected roles, phishing simulation calibration, executive training.
- **Process**: runbook updates, decision-tree improvements, communication templates.
- **Governance**: risk register update, board reporting refinement, budget realignment, KPI changes.

### 8. Anti-patterns

The RCA discipline rejects the following anti-patterns. The DPO has standing authority to send back any RCA that exhibits them.

- **Single-cause closure** — a serious breach attributed to "user error" with no other layer addressed.
- **Vague action verbs** — "improve awareness", "review processes", "consider" — without specific deliverables.
- **Owner-by-committee** — actions assigned to a team or department; no individual accountability.
- **Cosmetic technical fix** — patching the immediate hole without addressing the systemic class.
- **Token training** — adding a slide to a deck that nobody reads.
- **Procurement instead of fix** — buying a new tool that overlaps existing capability without solving the underlying gap.
- **Missing effectiveness review** — closing a CAPA on the day the action is taken, with no follow-up.

### 9. Confidentiality and privilege

RCA documents may be subject to legal privilege where prepared in contemplation of litigation or under instruction of counsel. The DPO and Legal coordinate at RCA scoping to determine the privilege posture. RCA documents are stored in the secure document repository with access limited to need-to-know.

When the SA requests RCA materials under Article 58 enforcement powers, the controller responds in coordination with Legal, recognising that RCA documents are typically discoverable and that good-faith RCA is itself a mitigating factor.

### 10. Aggregate analysis

Quarterly, the DPO and CISO produce an aggregate analysis of all RCAs in the quarter:

- recurring causal patterns;
- CAPA closure rates;
- effectiveness review outcomes;
- correlation with risk register entries.

The aggregate is presented to the executive committee. Patterns that recur across multiple quarters trigger a deeper systemic review (architecture, organisation design, governance).

### 11. Use of RCA outputs in tabletop exercises

Anonymised RCA narratives feed into tabletop scenarios (see `tabletop-exercises.md`). The objective is institutional learning that travels beyond the original case.

### 12. Worked example — RCA layers for the ransomware case

The worked example in `notification-form.md` (Aegis Logistics 612-record ransomware) yields:

- **Technical**: phishing-resistant MFA was deployed for employees but not consistently for contractors; VPN allowed credential-only fallback under exception process. CAPA: enforce FIDO2 for all VPN access; remove fallback; deploy DNS filtering on contractor devices.
- **Human**: contractor was not enrolled in the same phishing awareness programme as employees. CAPA: extend programme; require completion before VPN access provisioned; refresh every 6 months.
- **Process**: contractor onboarding ran outside the joiner workflow; security review of contractor access was discretionary. CAPA: integrate contractor lifecycle into the joiner/mover/leaver pipeline; mandatory security review at provisioning.
- **Governance**: contractor population was not in the asset inventory or in the risk register's "remote access" risk. CAPA: extend inventory and risk register; quarterly review at executive committee.

Each CAPA carries owner, due date, success criteria, and Day-365 effectiveness review hooks.

---

## Türkçe

### 1. Amaç ve kapsam

Kök neden analizi (RCA), her kişisel veri ihlalini (ve SEV-2 veya daha yüksek olarak sınıflandırılabilecek kadar ciddi her ramak kala olayını) takip eden yapılandırılmış soruşturmadır. Amacı, bunlardan türetilen düzeltici ve önleyici eylemlerin (CAPA), tekrarın olasılığını veya şiddetini ölçülebilir bir şekilde azaltacak kadar derin nedensel faktörleri belirlemektir.

Bir ihlal RCA teslim edilene, CAPA kayıtlı olana ve yönetici sponsor eylem planını onaylayana kadar kapatılmaz.

### 2. RCA tetikleyicileri

| Tetikleyici | RCA derinliği |
|-------------|--------------|
| Madde 33 bildirimi olan kişisel veri ihlali | Tam dört katmanlı RCA |
| Bildirimi olmayan kişisel veri ihlali | Tam dört katmanlı RCA |
| SEV-2 veya daha yüksek ramak kala | Tam dört katmanlı RCA |
| SEV-3 ramak kala | Hafif 5 Neden + hedefli CAPA |
| 12 ay içinde aynı kontrol alanında tekrarlanan olay | Tam dört katmanlı RCA + yönetişim incelemesi |

### 3. Metodoloji yığını

Üç tamamlayıcı teknik birlikte kullanılır.

#### 3.1 5 Neden

5 Neden, her RCA için giriş tekniği olarak kullanılır. Hızlıdır, hafiftir ve bariz nedensellik zincirini açığa çıkarır. Tek başına yeterli değildir — tek bir nedensel zincire takılma eğilimindedir — ancak yararlı bir ısınmadır.

Her "neden" kanıt destekli olmalıdır. Kanıtsız iddia edilen nedenler işaretlenir ve doğrulama için park edilir.

#### 3.2 Fishbone (Ishikawa)

Fishbone diyagramı, birden fazla katkıda bulunan faktörün muhtemel olduğu herhangi bir RCA için kullanılır. İhlal RCA'sı için uyarlanmış kategoriler:

- **İnsan** (eğitim, farkındalık, yorgunluk, niyet, kadro seviyeleri)
- **Süreç** (runbook'lar, değişiklik yönetimi, joiner/mover/leaver, tedarikçi yönetimi)
- **Teknoloji** (kontroller, yapılandırmalar, varlık envanteri, yamalar)
- **Çevre** (fiziksel güvenlik, ağ segmentasyonu, üçüncü taraf bağlantısı)
- **Ölçüm** (günlükleme, izleme, uyarı, metrikler)
- **Yönetim** (yönetişim, önceliklendirme, kaynaklama, hesap verebilirlik)

#### 3.3 Apollo RCA (nedensel zincirler)

Ciddi ihlaller için Apollo RCA (Dean Gano) kullanılır. Nedenlerin yönlendirilmiş bir grafiğini oluşturur, eylemleri ve koşulları ayırt eder ve her kök kontrol-eylenebilir bir seviyeye ulaşana kadar devam eder.

### 4. Dört katmanlı model

Tam derinlikli RCA için her ihlal dört katman üzerinden incelenir.

#### Katman 1 — Teknik

Bir teknik kontrol tasarlandığı gibi çalışmadı mı veya bir kontrolün bulunması gereken yerde hiç kontrol yok muydu?

- Eksik veya yanlış yapılandırılmış WAF kuralı.
- İlgili veri sınıfına dağıtılmamış DLP imzası.
- Etkilenen erişim yolu için MFA zorunlu kılınmamış.
- Sömürülen zafiyet için yama SLA'sı kaçırıldı.
- Etkilenen veri deposuna şifreleme uygulanmadı.
- Etkilenen hesapta aşırı ayrıcalık.
- Zamanında tespiti engelleyen yetersiz günlükleme.

#### Katman 2 — İnsan

Bir kişi ihlale katkıda bulunan bir karar verdi mi veya eylem aldı mı? Bu katman suçlama olmadan ve bağlama tam dikkat verilerek incelenir.

#### Katman 3 — Süreç

Bir süreç veya prosedür tasarlandığı gibi çalışmadı mı?

#### Katman 4 — Yönetişim

Kuruluşun nasıl önceliklendirdiği, kaynak ayırdığı veya kendini hesap verebilir tuttuğunda bir sorun var mıydı?

### 5. RCA iş akışı

| Gün | Faaliyet | Sahip |
|-----|---------|-------|
| 0 (olay kapatma) | RCA kapsamlandırma toplantısı; ekip bir araya getirildi | VKK + CISO |
| 1–3 | Kanıt toplama (zaman çizelgesi, günlükler, görüşmeler); 5 Neden taslağı | RCA lideri |
| 4–7 | Fishbone çalıştayı; ciddi vakalar için Apollo grafiği | RCA lideri |
| 8–10 | Dört katmanlı inceleme; CAPA taslağı | RCA lideri + kontrol sahipleri |
| 11–14 | Paydaş incelemesi | RCA lideri |
| 15 | Nihai RCA raporu ve CAPA kayıt girişi | RCA lideri |
| 30 | Yönetici sponsor onayı; CAPA izleyici aktif | Sponsor |
| 90, 180, 365 | CAPA ilerleme incelemeleri | VKK + CISO |

### 6. CAPA disiplini

CAPA eylemleri SMART'tır:

- **Spesifik**: doğrulanabilir bir sonuca sahip tek, adlandırılmış bir değişiklik.
- **Ölçülebilir**: başarı kriterleri sayısal veya boolean olarak belirtilir.
- **Atanmış**: tek adlandırılmış sahip (ekip değil).
- **Gerçekçi**: sahibinin yetkisi ve kaynakları içinde uygulanabilir.
- **Zaman sınırlı**: açık son tarih ve inceleme kontrol noktaları.

| Alan | Açıklama |
|------|----------|
| CAPA kimliği | `CAPA-YYYY-NNNN` |
| Kaynak | RCA belge kimliği |
| Katman | Teknik / İnsan / Süreç / Yönetişim |
| Açıklama | Eylem |
| Başarı kriterleri | Doğrulanabilir test |
| Sahip | Tek adlandırılmış birey |
| Sponsor | Hesap veren yönetici |
| Son tarih | ISO tarihi |
| İnceleme tarihleri | 30 / 90 / 180 / 365 gün |
| Durum | Açık / Devam ediyor / Doğrulandı / Kapalı |
| Kapatma kanıtı | Yapıt bağlantısı (PR, runbook güncellemesi, eğitim tamamlama kaydı, kontrol testi) |
| Etkinlik incelemesi | 365. günde yapılır: bu CAPA gerçekten riski azalttı mı? Kanıt. |

CAPA'lar eylem alındığında kapatılmaz. 365. günde (veya kriterler izin veriyorsa daha erken) etkinlik incelemesi amaçlanan risk azalmasını teyit ettiğinde kapatılırlar.

### 7. Yaygın CAPA kategorileri

- **Kimlik ve erişim**: ayrıcalık doğru boyutlandırma, tam zamanında erişim, yüksek riskli roller için FIDO2 anahtarları.
- **Tespit**: yeni uyarı kuralları, taban çizgisi güncellemeleri, ek günlük kaynakları.
- **Kontrol altına alma hazırlığı**: önceden hazırlanmış izolasyon eylemleri, ağ segmentasyonu.
- **Tedarikçi yönetimi**: revize edilmiş VİS'ler, alt veri işleyen onay kapıları.
- **Eğitim**: etkilenen roller için hedefli eğitim.
- **Süreç**: runbook güncellemeleri, karar ağacı iyileştirmeleri.
- **Yönetişim**: risk kaydı güncellemesi, kurul raporlama iyileştirmesi.

### 8. Anti-patterler

RCA disiplini aşağıdaki anti-patternleri reddeder:

- **Tek nedenli kapatma** — başka katman ele alınmadan "kullanıcı hatası"na atfedilen ciddi ihlal.
- **Belirsiz eylem fiilleri** — "farkındalığı artır", "süreçleri gözden geçir", "değerlendir".
- **Komite-tarafından-sahip** — bir takıma veya departmana atanan eylemler.
- **Kozmetik teknik düzeltme** — sistemik sınıfı ele almadan acil deliği yamalama.
- **Sembolik eğitim** — kimsenin okumadığı bir slayt eklemek.
- **Düzeltme yerine satın alma** — temel boşluğu çözmeden mevcut yetenekle örtüşen yeni bir araç satın alma.
- **Eksik etkinlik incelemesi**.

### 9. Gizlilik ve ayrıcalık

RCA belgeleri, dava beklentisiyle veya avukat talimatıyla hazırlandığında hukuki ayrıcalığa tabi olabilir. VKK ve Hukuk RCA kapsamlandırmasında koordine eder.

### 10. Toplam analiz

Üç ayda bir, VKK ve CISO çeyrekteki tüm RCA'ların toplam bir analizini üretir.

### 11. Tatbikat tatbikatlarında RCA çıktılarının kullanımı

Anonimleştirilmiş RCA anlatıları masa başı senaryolarına beslenir.

### 12. Çalışılmış örnek — fidye yazılımı vakası için RCA katmanları

`notification-form.md`'deki çalışılmış örnek (Aegis Logistics 612 kayıtlı fidye yazılımı):

- **Teknik**: oltalanmaya dayanıklı MFA çalışanlar için dağıtıldı ancak yükleniciler için tutarlı şekilde uygulanmadı; VPN istisna süreci altında yalnızca kimlik bilgileri yedeğine izin verdi. CAPA: tüm VPN erişimi için FIDO2 zorunlu; yedeği kaldır; yüklenici cihazlarına DNS filtreleme uygula.
- **İnsan**: yüklenici çalışanlarla aynı oltalama farkındalık programına kayıtlı değildi. CAPA: programı uzat; VPN erişimi sağlanmadan önce tamamlamayı şart koş; her 6 ayda bir yenile.
- **Süreç**: yüklenici onboarding'i joiner iş akışının dışında çalıştı; yüklenici erişiminin güvenlik incelemesi takdire bağlıydı. CAPA: yüklenici yaşam döngüsünü joiner/mover/leaver hattına entegre et; provisioning'de zorunlu güvenlik incelemesi.
- **Yönetişim**: yüklenici nüfusu varlık envanterinde veya risk kaydının "uzaktan erişim" riskinde değildi. CAPA: envanter ve risk kaydını genişlet; yönetim komitesinde üç ayda bir inceleme.

Her CAPA sahip, son tarih, başarı kriterleri ve 365. gün etkinlik inceleme kancalarını taşır.
