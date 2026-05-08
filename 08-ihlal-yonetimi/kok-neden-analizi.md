---
Doküman / Document: Kök Neden Analizi (RCA) ve CAPA / Root Cause Analysis (RCA) and CAPA
Bölüm / Section: 08-ihlal-yonetimi
Sahip / Owner: KVKK Sorumlusu + Bilgi Güvenliği Müdürü / KVKK Officer + CISO
Onaylayan / Approved by: KVKK Komitesi / KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + her ihlal sonrası / Annual + after every breach
İlgili Mevzuat / Legal Reference: Law No. 6698 (KVKK) Art. 12; KVKK Data Security Guide (2018) §5; ISO/IEC 27035-2:2023; ISO 9001:2015 §10.2; NIST SP 800-61 Rev.2 §3.4
---

## English

# Root Cause Analysis (RCA) and Corrective / Preventive Actions (CAPA)

## 1. Purpose

After every personal data breach, the goal is to identify and address the **true root cause**, avoiding symptomatic fixes and preventing recurrence of the same type of breach. RCA is the practical correlate of the "corrective measures" obligation in the KVKK Data Security Guide.

## 2. When RCA Is Mandatory

| Trigger | Timing |
|---------|--------|
| Every breach reported to the Authority | Final RCA within T+30 days |
| Below-threshold incidents not reported | Summary RCA within T+15 days |
| Recurring incidents (same category second time) | Urgent RCA within T+10 days |
| Critical miss in tabletop | Tabletop RCA within T+15 days |
| Internal audit finding | As per audit report timeline |

## 3. RCA Methodologies

The company chooses among three methodologies depending on the type of incident:

### 3.1. 5 Whys (Fast, linear)

For simple chains of causality.

**Example:**
> Breach: Customer data was exfiltrated.
> Why 1: The employee had bulk export privilege. -> Because every CRM user is fully privileged by default.
> Why 2: Why default full privilege? -> Access policy was not updated for years.
> Why 3: Why not updated? -> Policy owner was unclear.
> Why 4: Why was the owner unclear? -> Role mapping was not done after KVKK rollout.
> Why 5: Why not done? -> The KVKK Committee prioritized privacy notices and de-prioritized access classes.

**Output:** Root cause = "Access rights were not authorized in the KVKK compliance roadmap."

### 3.2. Fishbone (Ishikawa) - Multiple Causes by Category

Categories (5M+E): Man, Machine, Method, Material, Measurement, Environment.

```
                 Man           Machine
                  |              |
                  +------+-------+
                         |
Breach <-----------------+
                         |
                  +------+-------+
                  |      |       |
                Method  Measure  Environment
```

**Use:** Complex breaches (ransomware, BEC) - multiple layers contribute.

**Template:**

| Category | Possible cause 1 | Possible cause 2 | Possible cause 3 |
|----------|------------------|------------------|------------------|
| Man (Human) | Training gap | Password hygiene | Social engineering |
| Machine (System) | Patch gap | No EDR | Old OS |
| Method (Process) | Access policy | No monitoring | No tabletop |
| Material (Software/hardware) | Unlicensed | Insufficient logging | Backup failure |
| Measurement | No KPI | Alert miss | Audit gap |
| Environment | Physical security | Vendor | Regulatory pressure |

### 3.3. Apollo RCA (Cause-and-Effect Charting)

For serious / complex breaches. At least two causal trees per incident (action cause + condition cause).

```
                   [Breach]
                      |
        +-------------+-------------+
        |                           |
   [Action cause]              [Condition cause]
   (what attacker did)         (what was permitted)
        |                           |
   +----+----+                +-----+-----+
[sub-action] [tool]         [vuln]      [inadequacy]
```

Each node requires **evidence** (log, video, statement). Hypotheses without evidence are pruned.

**Advantage:** Avoids the single-root-cause fallacy and surfaces the **real causal network**.

## 4. RCA Layers (Company Standard Approach)

Every RCA is conducted across at least **four layers**:

### 4.1. Technical Layer

- Which vulnerability? (CVE, configuration, architecture)
- Which system? (Version, patch status)
- Which monitoring was bypassed? (SIEM, EDR, DLP gaps)
- Which control was missing? (Encryption, segmentation, MFA)

### 4.2. Process Layer

- Which procedure was missing / outdated?
- Did the approval chain function?
- Were SLAs realistic?
- Did the tabletop cover this scenario?

### 4.3. Human Layer

- Who decided / failed to decide what?
- Was the level of training adequate?
- Were workload or fatigue factors at play?
- Was there ethical / intentional negligence?

> **Important:** The human layer is **not individual blame**. "Just culture" principle: honest mistakes are not punished; deliberate violations are disciplined.

### 4.4. Governance Layer

- Was the policy current?
- Was the budget sufficient?
- Was management support there?
- Was the risk appetite well-defined?

## 5. RCA Process (Step by Step)

```
1. RCA triggered (incident closure)
        |
2. RCA Lead assigned (CISO or KVKK Officer)
        |
3. RCA team formed (5-7 people, cross-functional)
        |
4. Evidence collection (logs, interviews, documents)
        |
5. Timeline reconstruction
        |
6. Methodology selection (5 Whys / Fishbone / Apollo)
        |
7. Hypotheses + evidence matching
        |
8. Root cause confirmation (RCA Lead + KVKK Officer)
        |
9. CAPA design
        |
10. KVKK Committee approval
        |
11. CAPA execution
        |
12. Effectiveness verification (8 weeks later)
        |
13. Closure
```

## 6. RCA Team

| Role | Responsibility |
|------|----------------|
| RCA Lead | Process management, reporting |
| Incident Commander | Incident chronology, response decisions |
| Technical Lead | Forensic evidence interpretation |
| KVKK Officer | Regulatory perspective |
| Human Factors Specialist | HR + Training - "just culture" framing |
| Process Owner | Affected business process expertise |
| Independent Reviewer | Senior from another function (bias check) |

## 7. Evidence Collection Discipline

- **Hourly log priority:** SIEM, EDR, DLP, network flow, identity systems.
- **Interview protocol:** Structured, recorded, two interviewers, with legal oversight.
- **Documents:** Policy versions, training records, change tickets.
- **Retention:** All RCA files in insured archive for **5 years**.
- **Anonymization:** Personalized for internal distribution; anonymized for any external sharing.

## 8. CAPA (Corrective and Preventive Actions)

### 8.1. Corrective Action

- Prevents recurrence of the incident.
- Specific, measurable, with target date.
- Directly addresses the root cause.

### 8.2. Preventive Action

- Stops similar but not-yet-occurred incidents.
- Applied across other systems/processes.
- Counters "we got lucky this time" situations.

### 8.3. CAPA Design Standard

Every CAPA must be **SMART**:
- **S**pecific - clear definition.
- **M**easurable - measurable KPI.
- **A**chievable - realistic.
- **R**elevant - tied to root cause.
- **T**ime-bound - deadline.

### 8.4. CAPA Template

| Field | Content |
|-------|---------|
| CAPA No | CAPA-YYYY-NNNN |
| Linked incident | OLAY-YYYY-NNNN |
| Type | Corrective / Preventive |
| Root cause reference | RCA section |
| Description | (SMART) |
| Owner (Unit) | |
| Owner (Person) | |
| Target date | |
| KPI | |
| Approval | KVKK Committee |
| Status | Open / In progress / Done / Cancelled |
| Effectiveness verification date | T+8 weeks after |
| Verification method | Test / Audit / Tabletop |
| Verification result | Pass / Fail |

### 8.5. Typical CAPA Examples

| Root cause | Corrective | Preventive |
|------------|------------|------------|
| Lack of MFA | MFA mandatory on all remote access | MFA default on new account onboarding |
| Patch gap | Patch the affected system + fleet-wide CVE scan | Monthly automated patch cycle, defined SLA |
| Access violation | Permission removed from user | Quarterly least-privilege review |
| Training gap | Targeted refresher (affected unit) | Annual general + 6-monthly module training |
| Third party | Tightened contractual clause | Renew all vendor contracts |
| Backup failure | Set up immutable backup | Monthly restore drill |
| DLP gap | Updated DLP rule set | Quarterly DLP false-positive review |
| Outdated policy | Policy updated | Annual policy cycle |

## 9. CAPA Tracking

### 9.1. System
- Separate CAPA project on JIRA / Asana / ServiceNow.
- Each action ticketed.
- Owner, date, status, evidence link.
- Weekly automated escalation for overdue actions.

### 9.2. Governance
- Monthly CAPA review by KVKK Committee.
- Overdue actions added to Board agenda.
- Random CAPA sampling in annual audit.

### 9.3. Effectiveness Verification

Saying an action is "closed" is not enough. Its **effect** must be verified:

| Action | Verification method |
|--------|---------------------|
| MFA enforced | AD log - 0 logins without MFA |
| Patch cycle | Patch compliance report 95%+ |
| Training | Quiz pass rate 85%+ |
| Contract clause | Inspection of every new/renewed contract |
| Immutable backup | Successful restore drill |
| DLP rule | False positives < 5% + true positives 90%+ |

Actions whose effectiveness cannot be verified within 8 weeks are **reopened**.

## 10. Recurrence-Prevention Metrics

| Metric | Target | Source |
|--------|--------|--------|
| Recurring breach rate | 0% | RCA archive |
| CAPA on-time closure | >= 90% | CAPA system |
| CAPA effectiveness verification | 100% | CAPA system |
| RCA quality score (auditor) | >= 8/10 | Internal audit |
| Root cause found (first 30 days) | >= 95% | RCA archive |

## 11. RCA Report Template

```markdown
# RCA Report - OLAY-YYYY-NNNN

## 1. Summary
- Incident date:
- Incident type:
- Affected data:
- Notification status:

## 2. Detailed Incident Timeline
| Time | Event | Evidence |
|------|-------|----------|
|  |  |  |

## 3. Evidence
3.1. Technical:
3.2. Documentary:
3.3. Interviews:

## 4. Methodology
[5 Whys / Fishbone / Apollo selected - rationale]

## 5. Causal Analysis
5.1. Technical layer:
5.2. Process layer:
5.3. Human layer:
5.4. Governance layer:

## 6. Root Cause(s)
[Clear sentence, evidence-based]

## 7. CAPA List
[See table]

## 8. Risk Assessment
- Recurrence likelihood:
- Impact magnitude:
- Residual risk (post-CAPA):

## 9. Policy / Training Update Recommendations

## 10. RCA Team
- Lead:
- Members:
- Independent reviewer:

## 11. Approval
- KVKK Officer:
- CISO:
- Legal:
- KVKK Committee:
- Date:
```

## 12. RCA Maturity

| Level | Definition |
|-------|------------|
| 1 - Reactive | Only major incidents |
| 2 - Systematic | All reported breaches |
| 3 - Extended | Below-threshold incidents too |
| 4 - Predictive | Near misses too |
| 5 - Learning | Internalized in the organization; training data |

Company target level: **4** (end of 2027).

## 13. Linked Sections

- `06-idari-tedbirler/egitim.md` - Training updates from RCA outputs.
- `11-denetim-ve-uyum/aksiyon-takibi.md` - CAPA list integration.
- `08-ihlal-yonetimi/soak-test-tatbikat.md` - Inclusion in tabletop scenarios.

## 14. Version History

| Version | Date | Change | Approval |
|---------|------|--------|----------|
| 1.0 | 2026-05-08 | First publication | KVKK Committee |

---

## Türkçe

# Kök Neden Analizi (RCA) ve Düzeltici/Önleyici Aksiyon (CAPA)

## 1. Amaç

Her kişisel veri ihlali sonrası **gerçek kök nedenin** bulunup giderilmesi, semptomatik çözümle yetinilmeyip aynı tipte ihlalin tekrarının önlenmesi. RCA, KVKK Veri Güvenliği Rehberi'nin "düzeltici tedbirler" yükümlülüğünün uygulamadaki karşılığıdır.

## 2. RCA Yapılması Zorunlu Durumlar

| Tetikleyici | Süre |
|-------------|------|
| Kurul'a bildirilen her ihlal | T+30 gün içinde nihai RCA |
| Eşik altı kalan ama bildirilmeyen olay | T+15 gün özet RCA |
| Tekrarlayan olay (aynı kategori 2. kez) | T+10 gün acil RCA |
| Tatbikatta kritik kaçış | T+15 gün tatbikat RCA |
| İç denetim bulgu kapsamı | Denetim raporu süresi |

## 3. RCA Metodolojileri

Şirketimiz üç farklı metodolojiyi olay tipine göre seçer:

### 3.1. 5 Whys (Hızlı, doğrusal)

Basit nedensellik zincirleri için.

**Örnek:**
> İhlal: Müşteri verileri dışa aktarıldı.
> Why 1: Çalışan toplu export yetkisine sahipti. → Çünkü her CRM kullanıcısı default'ta tam yetkili.
> Why 2: Default tam yetki neden? → Erişim politikası yıllarca güncellenmedi.
> Why 3: Neden güncellenmedi? → Politika sahibi belirsizdi.
> Why 4: Sahibi neden belirsizdi? → KVKK sonrası rol haritası yapılmadı.
> Why 5: Neden yapılmadı? → KVKK Komitesi gündemi öncelikli olarak aydınlatma metnine odaklandı, erişim sınıfı geri planda kaldı.

**Çıktı:** Kök neden = "KVKK uyum yol haritasında erişim hakları yetkilendirilmedi."

### 3.2. Fishbone (Ishikawa) — Kategoriye Göre Çoklu Neden

Kategoriler (5M+E): Man, Machine, Method, Material, Measurement, Environment.

```
                 Man           Machine
                  │              │
                  └──────┬───────┘
                         │
İhlal ←──────────────────┤
                         │
                  ┌──────┼───────┐
                  │      │       │
                Method  Measure  Environment
```

**Kullanım:** Karmaşık ihlaller (ransomware, BEC) — birden çok katmanın katkısı vardır.

**Şablon:**

| Kategori | Olası Neden 1 | Olası Neden 2 | Olası Neden 3 |
|----------|---------------|---------------|---------------|
| Man (İnsan) | Eğitim eksiği | Parola hijyeni | Sosyal mühendislik |
| Machine (Sistem) | Yama eksiği | EDR yok | Eski OS |
| Method (Süreç) | Erişim politikası | İzleme yok | Tatbikat eksik |
| Material (Yazılım/donanım) | Lisanssız | Yetersiz log | Backup hatası |
| Measurement (Ölçüm) | KPI yok | Alarm kaçış | Audit eksik |
| Environment (Ortam) | Fiziksel güvenlik | Tedarikçi | Düzenleyici baskı |

### 3.3. Apollo RCA (Cause-and-Effect Charting)

Ciddi/karmaşık ihlaller için. Her ihlal için en az iki nedensel ağaç (action cause + condition cause) çizilir.

```
                   [İhlal]
                      │
        ┌─────────────┴─────────────┐
        │                           │
   [Eylem nedeni]              [Koşul nedeni]
   (saldırgan ne yaptı)        (neye izin verildi)
        │                           │
   ┌────┴────┐                ┌─────┴─────┐
[alt eylem] [araç]         [açık]      [yetersizlik]
```

Her düğüm için **kanıt** (log, video, ifade) zorunludur. Kanıtsız hipotez budanır.

**Avantaj:** Tek kök neden yanılgısından kaçınır; **gerçek nedensel ağ** ortaya çıkar.

## 4. RCA Katmanları (Şirketimiz Standart Yaklaşımı)

Her RCA en az **dört katmanda** yürütülür:

### 4.1. Teknik Katman
- Hangi açık? (CVE, yapılandırma, mimari)
- Hangi sistem? (Versiyon, yama durumu)
- Hangi izleme atlandı? (SIEM, EDR, DLP gap)
- Hangi tedbir eksikti? (Şifreleme, segmentasyon, MFA)

### 4.2. Süreç Katmanı
- Hangi prosedür eksik / güncel değildi?
- Onay zinciri çalıştı mı?
- SLA'lar gerçekçi miydi?
- Tatbikat bu senaryoyu kapsıyor muydu?

### 4.3. İnsan Katmanı
- Kim hangi kararı verdi / vermedi?
- Eğitim seviyesi yeterli miydi?
- İş yükü, yorgunluk faktörü var mıydı?
- Etik / kasıtlı ihmal var mıydı?

> **Önemli:** İnsan katmanı **bireysel suçlama** değildir. "Just culture" prensibi: dürüst hata cezasız, kasıtlı ihlal disiplinli.

### 4.4. Yönetişim Katmanı
- Politika güncel miydi?
- Bütçe yeterli miydi?
- Yönetim desteği var mıydı?
- Risk iştahı doğru tanımlanmış mıydı?

## 5. RCA Süreci (Adım Adım)

```
1. RCA tetiklendi (olay kapanış)
        ↓
2. RCA Lideri atandı (CISO veya KVKK Sorumlusu)
        ↓
3. RCA ekibi oluşturuldu (5-7 kişi, çapraz fonksiyon)
        ↓
4. Kanıt toplama (log, görüşme, doküman)
        ↓
5. Zaman çizgisi rekonstrüksiyon
        ↓
6. Metodoloji seçimi (5 Whys / Fishbone / Apollo)
        ↓
7. Hipotezler + kanıt eşleştirme
        ↓
8. Kök neden onayı (RCA Lideri + KVKK Sorumlusu)
        ↓
9. CAPA tasarımı
        ↓
10. KVKK Komitesi onayı
        ↓
11. CAPA uygulama
        ↓
12. Etkinlik doğrulama (8 hafta sonra)
        ↓
13. Kapanış
```

## 6. RCA Ekibi

| Rol | Sorumluluk |
|-----|-----------|
| RCA Lideri | Süreç yönetimi, raporlama |
| Olay Komutanı | Olay kronolojisi, müdahale kararları |
| Teknik Lider | Forensik delil yorumu |
| KVKK Sorumlusu | Düzenleyici uyum açısı |
| İnsan Faktörleri Uzmanı | İK + Eğitim — "just culture" çerçevesi |
| Süreç Sahibi | Etkilenen iş süreci uzmanı |
| Bağımsız Hakem | Diğer fonksiyondan kıdemli (önyargı kontrolü) |

## 7. Kanıt Toplama Disiplini

- **Saatlik log önceliği:** SIEM, EDR, DLP, ağ akışı, kimlik sistemi.
- **Görüşme protokolü:** Yapılandırılmış, kayıt altında, çift görüşmeci, hukuk gözetiminde.
- **Doküman:** Politika versiyonları, eğitim kayıtları, değişiklik biletleri.
- **Saklama:** Tüm RCA dosyaları **5 yıl** sigortalı arşiv.
- **Anonimleştirme:** Yayım iç dağıtımda kişiselleştirilmiş, dış paylaşımda anonim.

## 8. CAPA (Corrective and Preventive Actions)

### 8.1. Düzeltici Aksiyon (Corrective)

- Olayın tekrarını önler.
- Belirli, ölçülebilir, hedef tarihli.
- Doğrudan kök nedeni hedefler.

### 8.2. Önleyici Aksiyon (Preventive)

- Benzer ama henüz yaşanmamış olayları engeller.
- Diğer sistem/süreçlerde de uygulanır.
- "Bu sefer şanslıydık" durumlarına karşı.

### 8.3. CAPA Tasarımı Standardı

Her CAPA aksiyonu **SMART** olmalıdır:
- **S**pecific — net tanım.
- **M**easurable — ölçülebilir KPI.
- **A**chievable — gerçekçi.
- **R**elevant — kök nedene bağlı.
- **T**ime-bound — son tarih.

### 8.4. CAPA Şablonu

| Alan | İçerik |
|------|--------|
| CAPA No | CAPA-YYYY-NNNN |
| Bağlı olay | OLAY-YYYY-NNNN |
| Tip | Düzeltici / Önleyici |
| Kök neden referansı | RCA bölümü |
| Tanım | (SMART) |
| Sahip (Birim) | |
| Sahip (Kişi) | |
| Hedef tarih | |
| KPI | |
| Onay | KVKK Komitesi |
| Durum | Açık / Devam / Tamamlandı / İptal |
| Etkinlik doğrulama tarihi | T+8 hafta sonra |
| Doğrulama yöntemi | Test / Audit / Tatbikat |
| Doğrulama sonucu | Geçti / Kaldı |

### 8.5. Tipik CAPA Örnekleri

| Kök neden | Düzeltici | Önleyici |
|-----------|-----------|----------|
| MFA eksiği | Tüm uzaktan erişimde MFA zorunlu | Yeni hesap onboarding'inde MFA varsayılan |
| Yama eksiği | Etkilenen sistem yamasız + tüm filo CVE tarama | Aylık otomatik yama döngüsü, SLA tanımı |
| Erişim ihlali | Kullanıcı yetki kaldırıldı | Çeyreklik least-privilege review |
| Eğitim eksiği | Hedefli yenileme eğitimi (etkilenen birim) | Yıllık genel + 6 aylık modül eğitim |
| 3. taraf | Sözleşme klozu sıkılaştırıldı | Tüm tedarikçi sözleşme yenilenmesi |
| Yedek hatası | Immutable backup kuruldu | Aylık restore tatbikatı |
| DLP gap | DLP kural seti güncellendi | Çeyreklik DLP false-positive review |
| Politika güncel değil | Politika güncellendi | Yıllık politika döngüsü |

## 9. CAPA Takibi

### 9.1. Sistem
- JIRA / Asana / ServiceNow üzerinde ayrı CAPA projesi.
- Her aksiyon biletlenmiş.
- Sahibi, tarihi, durumu, kanıt linki.
- Geciken aksiyon haftalık otomatik eskalasyon.

### 9.2. Yönetişim
- KVKK Komitesi aylık CAPA gözden geçirme.
- Geciken aksiyonlar YK ekitilerine.
- Yıllık denetimde rastgele CAPA örneklemi.

### 9.3. Etkinlik Doğrulama

Aksiyon **kapatıldı** demek yetersizdir. **Etki**si doğrulanmalıdır:

| Aksiyon | Doğrulama yöntemi |
|---------|-------------------|
| MFA zorunlu | AD log — MFA olmadan giriş 0 |
| Yama döngüsü | Patch compliance raporu %95+ |
| Eğitim | Quiz başarı oranı %85+ |
| Sözleşme klozu | Tüm yeni/yenilenen sözleşme kontrolü |
| Backup immutable | Restore tatbikatı başarılı |
| DLP kuralı | False positive < %5 + true positive %90+ |

8 hafta içinde etkinlik doğrulanamayan aksiyon **yeniden açılır**.

## 10. Tekrar Etmeyi Önleme Metrikleri

| Metrik | Hedef | Kaynak |
|--------|-------|--------|
| Tekrarlayan ihlal oranı | %0 | RCA arşivi |
| CAPA zamanında kapanma | ≥ %90 | CAPA sistem |
| CAPA etkinlik doğrulama | %100 | CAPA sistem |
| RCA kalite skoru (denetçi) | ≥ 8/10 | İç denetim |
| Kök neden bulma (ilk 30 gün) | ≥ %95 | RCA arşivi |

## 11. RCA Raporu Şablonu

```markdown
# RCA Raporu - OLAY-YYYY-NNNN

## 1. Özet
- Olay tarihi:
- Olay tipi:
- Etkilenen veri:
- Bildirim durumu:

## 2. Olay Zaman Çizgisi (Detaylı)
| Zaman | Olay | Kanıt |
|-------|------|-------|
| | | |

## 3. Kanıtlar
3.1. Teknik:
3.2. Doküman:
3.3. Görüşme:

## 4. Metodoloji
[5 Whys / Fishbone / Apollo seçildi — gerekçe]

## 5. Nedensel Analiz
5.1. Teknik katman:
5.2. Süreç katmanı:
5.3. İnsan katmanı:
5.4. Yönetişim katmanı:

## 6. Kök Neden(ler)
[Net cümle, kanıta dayalı]

## 7. CAPA Listesi
[Bkz. tablo]

## 8. Risk Değerlendirmesi
- Tekrar olasılığı:
- Etki büyüklüğü:
- Kalan risk (CAPA sonrası):

## 9. Politika / Eğitim Güncellemesi Önerileri

## 10. RCA Ekibi
- Lider:
- Üyeler:
- Bağımsız hakem:

## 11. Onay
- KVKK Sorumlusu:
- CISO:
- Hukuk:
- KVKK Komitesi:
- Tarih:
```

## 12. RCA Yapma Olgunluk

| Seviye | Tanım |
|--------|-------|
| 1 — Reaktif | Sadece büyük olaylarda |
| 2 — Sistematik | Tüm bildirilen ihlallere |
| 3 — Genişletilmiş | Eşik altı olaylara da |
| 4 — Tahminsel | Yakın-kaçışlara (near miss) |
| 5 — Öğrenen | Kuruma içselleşmiş, eğitim verisi |

Şirket hedef seviye: **4** (2027 sonu).

## 13. Bağlantılı Bölümler

- `06-idari-tedbirler/egitim.md` — RCA çıktısı eğitim güncellemesi.
- `11-denetim-ve-uyum/aksiyon-takibi.md` — CAPA listesi entegrasyonu.
- `08-ihlal-yonetimi/soak-test-tatbikat.md` — Tatbikat senaryosuna işleme.

## 14. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi |
