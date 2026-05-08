---
Doküman / Document: KVKK İç Denetim Prosedürü / KVKK Internal Audit Procedure
Bölüm / Section: 11-denetim-ve-uyum
Sahip / Owner: İç Denetim Birimi / Internal Audit Function
Onaylayan / Approved by: Denetim Komitesi + Yönetim Kurulu — Audit Committee + Board of Directors
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş — Annual + triggered
İlgili Mevzuat / Legal Reference: 6698 sayılı KVKK m.12, m.15; VERBİS Yön.; Aydınlatma Tebliği; Başvuru Tebliği; İmha Yön.; IIA Standartları; COSO ERM — Law No. 6698 Arts. 12, 15; secondary KVKK legislation; IIA International Standards; COSO ERM
---

## English

# KVKK Internal Audit Procedure

## 1. Purpose and Scope

This procedure sets out the methodology and principles by which independent and objective internal auditing assures the Company's compliance with KVKK and its secondary legislation. It is aligned with the Institute of Internal Auditors (IIA) International Professional Practices Framework.

**Scope:** All personal data processing activities within the legal entity; all business units; all subsidiaries (group entities) and processor suppliers.

## 2. Three Lines of Defence Model

| Line | Unit | Responsibility | KVKK Context |
|------|------|----------------|--------------|
| 1st | Process owner (business units) | Day-to-day controls, self-assessment | HR personal data processing, call centre consent management |
| 2nd | KVKK Officer, Risk, Information Security, Legal, Compliance | Policy, monitoring, training, KPIs, advisory | Privacy notice standard, DPIA framework, breach response |
| 3rd | Internal Audit | Independent assurance, audit, reporting | Annual audit plan, finding report |

Internal Audit reports organisationally to the **Audit Committee of the Board**, not to the General Manager. This is the structural safeguard of independence.

## 3. Annual Internal Audit Plan

### 3.1 Plan Preparation

| Step | Time | Output |
|------|------|--------|
| Risk assessment | October-November | KVKK Risk Universe |
| Auditable area list | November | Audit Universe |
| Risk scoring, prioritisation | December | Risk-Based Plan Draft |
| Audit Committee approval | January | Approved Annual Plan |
| Resource allocation | January | Person-day distribution |

### 3.2 Risk Scoring

Each auditable area scored on a 1-5 scale:

| Factor | Weight |
|--------|--------|
| Volume of data processed | 15 |
| Sensitive data presence | 20 |
| Number of data subjects | 10 |
| Cross-border transfers present | 10 |
| Automated decision / profiling present | 8 |
| Past incidents / complaints | 12 |
| Time since last audit | 10 |
| Regulatory density | 8 |
| Supplier density | 7 |

Total score = Σ (factor × weight) / 100. Areas scoring ≥ 4 are audited annually; 3-4 every two years; <3 every three years.

### 3.3 Typical Annual Plan Skeleton

| Quarter | Audit Subject | Person-Days |
|---------|---------------|-------------|
| Q1 | HR personal data processing (personnel files, performance, leave, health) | 25 |
| Q1 | Incident Response design and testing | 15 |
| Q2 | Cross-border transfer (post-Art. 9 regime compliance test) | 20 |
| Q2 | End-to-end DSR process | 15 |
| Q3 | VERBİS accuracy test | 18 |
| Q3 | Supplier management and DPA compliance | 20 |
| Q4 | Retention and Destruction — periodic destruction evidence review | 18 |
| Q4 | Information Security — Personal Data Security Guide compliance | 30 |
| Year-round | Continuous monitoring — KPI verification, sampling | 25 |
| Year-round | Follow-up audits (closure of prior findings) | 14 |
| **Total** | | **200 person-days** |

## 4. Audit Phases

### 4.1 Phase 1: Planning and Opening (1-2 weeks)

| Activity | Output |
|----------|--------|
| Audit announcement (auditees informed 30 days in advance) | Formal announcement email |
| Regulatory and internal document review | Pre-engagement file |
| Risk and Control Matrix (RCM) | RCM document |
| Scope, objective, resource, timeline approval | Engagement Letter |
| Opening meeting (process owner, KVKK Officer, manager) | Meeting minutes |

### 4.2 Phase 2: Fieldwork (3-6 weeks)

#### Test Procedures

**A. Walkthrough**

- End-to-end process is followed with the process owner.
- Data collection → processing → transfer → destruction stages are verified.
- Gap between policy/procedure and actual practice is identified.
- Evidence: screenshots, system demos, employee interview notes.

**B. Document Review**

| Document | Review Focus |
|----------|--------------|
| Policies | Annual update, approval, distribution evidence |
| Procedures | Operational feasibility, owner assignment |
| Privacy notices | Disclosure Communiqué Art. 4 minimum elements, legal sign-off |
| Consent texts | Specific purpose, withdrawal channel, signature/approval evidence |
| Contracts / DPAs | Processor obligations, sub-processor approval |
| Destruction minutes | Date, method, responsible, signature |
| Training records | LMS report, completion status |
| Breach records | Detect-notify timing, root cause |

**C. Sampling**

- Statistical sampling: 95% confidence level, 5% margin of error.
- Sample size based on population:
  - <100: all
  - 100-1000: 50-90
  - 1000-10000: 90-150
  - >10000: 150-250
- Selection method: random (random.org or GRC tool), stratified or critical-item.
- Typical sampling areas: employee records, customer consent records, request responses, log records, destruction minutes.

**D. Recalculation**

- KPI values are independently recalculated for accuracy.
- Example: privacy notice coverage rate, periodic destruction execution rate.

**E. Confirmation**

- Signed original DPAs are confirmed with suppliers.
- Erasure / destruction confirmations are obtained from cross-border recipients.

**F. Technical Test (with IT audit coordination)**

- Access rights review (especially exited personnel)
- Log integrity (consistent timestamps, immutability)
- Encryption verification (sample-based)
- Backup restoration test
- DLP rules and exceptions

#### Working Papers

Standard working paper for each test:
- Objective
- Scope
- Method
- Population
- Sample
- Findings (tabular)
- Conclusion (Effective / Partially Effective / Ineffective)
- Preparer / Reviewer / Date

Working papers are retained at least 5 years (considering the Authority's audit window).

### 4.3 Phase 3: Finding Development

Each finding follows the **5C Structure**:

| Element | Description |
|---------|-------------|
| Condition | Current state observed |
| Criteria | Expected state (regulatory article, policy, best practice) |
| Cause | Why it occurred |
| Consequence | Risk, impact, possible fine/compensation |
| Corrective Action | Recommended action, owner, deadline |

### 4.4 Phase 4: Reporting

#### Finding Classification

| Class | Definition | Example | Closure Time |
|-------|------------|---------|--------------|
| Critical | Regulatory breach, fine risk, compensation, severe reputational damage | No VERBİS record, missing breach notification, request delay over 30 days | 30 days |
| High | Major control gap, near-term breach risk | Missing element in privacy notice, unsigned DPA with critical supplier | 90 days |
| Medium | Design or execution weakness, indirect risk | Missing signature on destruction minutes, training completion 92% | 180 days |
| Low | Improvement opportunity, best-practice suggestion | Policy numbering, dashboard visualisation | 365 days |

#### Finding Report Template

```
Finding No: 2026-Q2-005
Class: High
Title: 12% of critical suppliers without signed DPA

CONDITION: Of 50 critical suppliers (annual processing volume
>100K records) sampled in fieldwork, 6 were found without a
Data Processing Agreement (DPA).

CRITERIA: KVKK Art. 12/2; Personal Data Security Guide; Company
Supplier KVKK Policy v3.2 Art. 5.

CAUSE: DPA verification is not a mandatory field in the Procurement
contract review checklist. The supplier onboarding automation
lacks a KVKK control gate.

CONSEQUENCE: Risk of non-compliance with the data security
obligation (Art. 18/1-b). Possible administrative fine, joint
liability in case of breach, direct liability towards data subjects.

CORRECTIVE ACTION:
1. Sign the missing DPAs within 60 days (Owner: Procurement
   Manager, Deadline: 2026-08-15).
2. Add a DPA control gate to the supplier onboarding automation
   (Owner: IT, Deadline: 2026-09-30).
3. Verify DPA at annual renewal (Owner: KVKK Officer,
   Deadline: annual).

MANAGEMENT RESPONSE: [Process owner's response]
```

#### Report Structure

1. Executive Summary (1-2 pages)
2. Scope, objective, method
3. Overall Conclusion (Adequate / Improvement Needed / Inadequate)
4. Findings (in order of criticality)
5. Status of Prior Findings Under Follow-up
6. Annexes (working paper references)

### 4.5 Phase 5: Closing and Follow-up

| Activity | Deadline |
|----------|----------|
| Draft report to process owner | Fieldwork end + 5 business days |
| Process owner response | Draft + 10 business days |
| Closing meeting | Response + 5 business days |
| Final report to Audit Committee | Closure + 5 business days |
| Action follow-up — critical findings | 30 days |
| Follow-up audit | Each quarter |

## 5. Finding Tracking System

Centralised tracking in the GRC tool:
- Open finding count (by class)
- Aging analysis (overdue findings)
- Recurring findings (same control 2+ times)
- Action owner performance

## 6. Internal Audit Independence and Ethics

- Internal Audit does not staff personnel involved in the audited process.
- An auditor coming from another business unit cannot audit that unit within 1 year.
- Compliance with the IIA Code of Ethics: integrity, objectivity, confidentiality, competency.
- Gifts, hospitality: items above TRY 500/year are not accepted; above the threshold is reported.

## 7. Competency and Training

Minimum internal audit team composition:
- 1 certified internal auditor (CIA, CISA or equivalent)
- 1 KVKK / GDPR certified (CIPP/E, KVKK specialty)
- 1 IT / cybersecurity audit experienced (CISA, CISSP)

40 hours/year continuous professional education (CPE).

## 8. External Audit and Third-Party Use

- Independent external expertise can be commissioned for specific technical areas (e.g. penetration testing, anonymisation validation, AI/ML model fairness).
- External audit complements, does not replace, internal audit.
- Confidentiality and KVKK obligations must be explicit in the contract.

## 9. Continuous Auditing

GRC + log integration provides automated control indicators:
- Account creation → DPA presence verification
- VERBİS deviation alert (inventory ↔ VERBİS comparison)
- Destruction lag alarm (data past retention)
- DSR SLA approach warning

## 10. Reporting Line

| Frequency | Recipient | Content |
|-----------|-----------|---------|
| Weekly | Internal Audit Manager | Fieldwork status |
| Monthly | KVKK Committee | Open findings, KPIs |
| Quarterly | Audit Committee | All audit reports, follow-up |
| Annual | Board | Annual evaluation, next-year plan |
| Extraordinary | Chair of the Board | Critical finding, immediate |

## 11. Related Documents

- [uyum-olgunluk-modeli.md](uyum-olgunluk-modeli.md)
- [kpi-ve-metrikler.md](kpi-ve-metrikler.md)
- [kurul-denetim-hazirlik.md](kurul-denetim-hazirlik.md)
- [yaptirimlar-cezalar.md](yaptirimlar-cezalar.md)

---

## Türkçe

# KVKK İç Denetim Prosedürü

## 1. Amaç ve Kapsam

Bu prosedür, Şirketin KVKK ve ikincil mevzuata uyumunun bağımsız ve objektif iç denetim aracılığıyla güvence altına alınmasının yöntem ve esaslarını belirler. IIA (Institute of Internal Auditors) Uluslararası Mesleki Uygulama Standartları ile uyumludur.

**Kapsam:** Tüm tüzel kişilik bünyesindeki kişisel veri işleme faaliyetleri; tüm iş birimleri; tüm bağımlı kuruluşlar (group entities) ve veri işleyen tedarikçiler.

## 2. Üç Savunma Hattı Modeli

| Hat | Birim | Sorumluluk | KVKK Bağlamı |
|-----|-------|------------|--------------|
| 1. Hat | Süreç sahibi (iş birimleri) | Günlük kontroller, öz-değerlendirme | İK kişisel veri işleme, çağrı merkezi rıza yönetimi |
| 2. Hat | KVKK Sorumlusu, Risk Yönetimi, Bilgi Güvenliği, Hukuk, Uyum | Politika, izleme, eğitim, KPI, danışmanlık | Aydınlatma metni standardı, DPIA çerçevesi, ihlal müdahale |
| 3. Hat | İç Denetim | Bağımsız güvence, denetim, raporlama | Yıllık denetim planı, bulgu raporu |

İç Denetim, organizasyonel olarak Genel Müdüre değil, **Yönetim Kurulu Denetim Komitesine** raporlar. Bu, bağımsızlık ilkesinin yapısal güvencesidir.

## 3. Yıllık İç Denetim Planı

### 3.1 Plan Hazırlama

| Adım | Zaman | Çıktı |
|------|-------|-------|
| Risk değerlendirmesi | Ekim-Kasım | KVKK Risk Evreni |
| Denetlenebilir alan listesi | Kasım | Audit Universe |
| Risk skorlama, önceliklendirme | Aralık | Risk-Bazlı Plan Taslağı |
| Denetim Komitesi onayı | Ocak | Onaylanmış Yıllık Plan |
| Kaynak tahsisi | Ocak | Adam-gün dağılımı |

### 3.2 Risk Skorlaması

Her denetlenebilir alan için 1-5 ölçeği:

| Faktör | Ağırlık |
|--------|---------|
| İşlenen veri hacmi | 15 |
| Özel nitelikli veri varlığı | 20 |
| İlgili kişi sayısı | 10 |
| Yurt dışı aktarım var mı | 10 |
| Otomatik karar / profilleme var mı | 8 |
| Geçmiş ihlal / şikâyet | 12 |
| Son denetim üzerinden geçen süre | 10 |
| Mevzuat yoğunluğu | 8 |
| Tedarikçi yoğunluğu | 7 |

Toplam skor = Σ (faktör × ağırlık) / 100. Risk skoru ≥ 4 olan alanlar yıllık denetlenir; 3-4 arası iki yılda bir; <3 üç yılda bir.

### 3.3 Tipik Yıllık Plan İskeleti

| Çeyrek | Denetim Konusu | Adam-gün |
|--------|----------------|----------|
| Q1 | İK kişisel veri işleme süreçleri (özlük, performans, izin, sağlık) | 25 |
| Q1 | İhlal Müdahale Süreci tasarım ve test | 15 |
| Q2 | Yurt dışı aktarım (m.9 yeni rejim uyum testi) | 20 |
| Q2 | İlgili kişi başvuru süreci uçtan uca | 15 |
| Q3 | Veri Sorumluları Sicili (VERBİS) doğruluk testi | 18 |
| Q3 | Tedarikçi yönetimi ve DPA uyumu | 20 |
| Q4 | Saklama ve İmha — periyodik imha kanıt incelemesi | 18 |
| Q4 | Bilgi Güvenliği — Veri Güvenliği Rehberi uyumu | 30 |
| Yıl Boyu | Sürekli izleme — KPI doğrulama, örnekleme | 25 |
| Yıl Boyu | Takip denetimleri (önceki bulguların kapatılması) | 14 |
| **Toplam** | | **200 adam-gün** |

## 4. Denetim Aşamaları

### 4.1 Aşama 1: Planlama ve Açılış (1-2 hafta)

| Faaliyet | Çıktı |
|----------|-------|
| Denetim duyurusu (saha 30 gün öncesinden bilgilendirilir) | Resmi duyuru e-postası |
| Mevzuat ve içsel doküman gözden geçirme | Ön çalışma dosyası |
| Risk ve kontrol matrisi (RCM) hazırlama | RCM dokümanı |
| Kapsam, hedef, kaynak, takvim onayı | Engagement Letter |
| Açılış toplantısı (süreç sahibi, KVKK Sor., yönetici) | Toplantı tutanağı |

### 4.2 Aşama 2: Saha Çalışması (3-6 hafta)

#### Test Prosedürleri

**A. Walkthrough (Süreç Yürüyüşü)**

- Süreç sahibi ile birlikte uçtan uca akış izlenir.
- Veri toplama → işleme → aktarım → imha aşamaları doğrulanır.
- Politika/prosedür ile fiili uygulama arasındaki sapma tespit edilir.
- Kanıt: ekran görüntüleri, sistem demosu, çalışan görüşme notu.

**B. Belge İncelemesi**

| Doküman | İnceleme Noktası |
|---------|-------------------|
| Politikalar | Yıllık güncelleme, onay, dağıtım kanıtı |
| Prosedürler | Operasyonel uygulanabilirlik, sahip atama |
| Aydınlatma metinleri | Tebliğ m.4 asgari unsurlar, hukuk onayı |
| Açık rıza metinleri | Net amaç, geri alma kanalı, imza/onay kanıtı |
| Sözleşmeler / DPA | Veri işleyen yükümlülükleri, alt-işleyen onayı |
| İmha tutanakları | Tarih, yöntem, sorumlu, imza |
| Eğitim kayıtları | LMS raporu, başarı durumu |
| İhlal kayıtları | Tespit-bildirim süreleri, kök neden |

**C. Örnekleme (Sampling)**

- İstatistiksel örnekleme: %95 güven düzeyi, %5 hata payı.
- Popülasyon büyüklüğüne göre örnek (n) hesabı:
  - <100: tümü
  - 100-1000: 50-90
  - 1000-10000: 90-150
  - >10000: 150-250
- Örnek seçim yöntemi: rastgele (random.org veya GRC aracı), tabakalı veya kritik öğe bazlı.
- Tipik örnekleme alanları: çalışan kayıtları, müşteri rıza kayıtları, başvuru yanıtları, log kayıtları, imha tutanakları.

**D. Recalculation (Yeniden Hesaplama)**

- KPI değerlerinin doğruluğu bağımsız olarak yeniden hesaplanır.
- Örnek: aydınlatma kapsama oranı, periyodik imha gerçekleşme.

**E. Konfirmasyon**

- Tedarikçi DPA'larının imzalı orijinal nüshası tedarikçiden teyit edilir.
- Yurt dışı alıcılardan kişisel veri silme/yok etme teyitleri alınır.

**F. Teknik Test (BT denetim koordinasyonu)**

- Erişim hakları gözden geçirme (özellikle ayrılan personel)
- Log bütünlük kontrolü (tutarlı zaman damgası, değiştirilemezlik)
- Şifreleme aktif mi (örnekleme ile)
- Yedeklemeden geri alma testi
- DLP kuralları ve istisnalar

#### Çalışma Kâğıtları

Her test için standart çalışma kâğıdı:
- Hedef
- Kapsam
- Yöntem
- Popülasyon
- Örnek
- Bulgular (tablolu)
- Sonuç (Etkili / Kısmen Etkili / Etkisiz)
- Hazırlayan / Gözden Geçiren / Tarih

Çalışma kâğıtları minimum 5 yıl saklanır (Kanun denetim hakkı süresi gözetilerek).

### 4.3 Aşama 3: Bulgu Geliştirme

Her bulgu için **5C Yapısı**:

| Eleman | Açıklama |
|--------|----------|
| Condition (Durum) | Tespit edilen mevcut durum |
| Criteria (Kriter) | Beklenen durum (mevzuat maddesi, politika, en iyi uygulama) |
| Cause (Neden) | Neden ortaya çıktığı |
| Consequence (Sonuç) | Risk, etki, olası ceza/tazminat |
| Corrective Action (Düzeltici Aksiyon) | Önerilen aksiyon, sorumlu, termin |

### 4.4 Aşama 4: Raporlama

#### Bulgu Sınıflandırması

| Sınıf | Tanım | Örnek | Kapatma Süresi |
|-------|-------|-------|----------------|
| Kritik | Mevzuat ihlali, ceza riski, tazminat, ciddi itibar zararı | VERBİS kayıt yokluğu, açık ihlal bildirim eksikliği, 30 gün üzeri başvuru gecikmesi | 30 gün |
| Yüksek | Önemli kontrol eksikliği, yakın gelecekte ihlal riski | Aydınlatma metninde Tebliğ m.4 unsuru eksik, DPA imzalanmamış kritik tedarikçi | 90 gün |
| Orta | Tasarım veya uygulama zayıflığı, dolaylı risk | İmha tutanağında imza eksikliği, eğitim tamamlama %92 | 180 gün |
| Düşük | İyileştirme fırsatı, en iyi uygulama önerisi | Politika numaralandırması, dashboard görselleştirme | 365 gün |

#### Bulgu Raporu Şablonu

```
Bulgu No: 2026-Q2-005
Sınıf: Yüksek
Başlık: Kritik tedarikçilerin %12'sinde DPA imzasız

DURUM: Saha çalışmasında incelenen 50 kritik tedarikçi (yıllık
işleme hacmi >100K kayıt) örnekleminden 6'sında veri işleyen
sözleşmesi (DPA) eksik bulunmuştur.

KRİTER: KVKK m.12/2; Veri Güvenliği Rehberi; Şirket Tedarikçi
KVKK Politikası v3.2 m.5.

NEDEN: Tedarik biriminde sözleşme gözden geçirme listesinde
DPA kontrolü zorunlu alan değil. Tedarikçi onboarding
otomasyonunda KVKK kontrolü eksik.

SONUÇ: KVKK m.18/1-b kapsamında veri güvenliği yükümlülüğüne
aykırılık riski. Olası idari para cezası, ihlal halinde
zincirleme sorumluluk, ilgili kişiye karşı doğrudan
sorumluluk.

DÜZELTİCİ AKSİYON:
1. Eksik DPA'ların 60 gün içinde imzalanması (Sahip: Tedarik
   Müdürü, Termin: 2026-08-15).
2. Tedarikçi onboarding otomasyonuna DPA kontrol kapısı
   eklenmesi (Sahip: BT, Termin: 2026-09-30).
3. Yıllık yenilemede DPA kontrolü (Sahip: KVKK Sor.,
   Termin: yıllık).

YÖNETİM CEVABI: [Süreç sahibinin cevabı]
```

#### Rapor Yapısı

1. Yönetici Özeti (1-2 sayfa)
2. Kapsam, hedef, yöntem
3. Genel Sonuç (Yeterli / Geliştirilmesi Gerekli / Yetersiz)
4. Bulgular (kritiklik sırasıyla)
5. İzlemedeki Önceki Bulgular Durumu
6. Ekler (çalışma kâğıdı referansları)

### 4.5 Aşama 5: Kapanış ve Takip

| Faaliyet | Termin |
|----------|--------|
| Taslak rapor süreç sahibine | Saha bitimi + 5 iş günü |
| Süreç sahibi cevap | Taslak + 10 iş günü |
| Kapanış toplantısı | Cevap + 5 iş günü |
| Nihai rapor Denetim Komitesine | Kapanış + 5 iş günü |
| Aksiyon takip — kritik bulgular | 30 gün |
| Takip denetimi (follow-up) | Her çeyrek |

## 5. Bulgu Takip Sistemi

GRC aracında merkezi takip:
- Açık bulgu sayısı (sınıf bazında)
- Yaşlanma analizi (geciken bulgu)
- Tekrarlayan bulgu (aynı kontrolde 2+ kez)
- Aksiyon sahibi performansı

## 6. İç Denetim Bağımsızlığı ve Etik

- İç Denetim, denetlediği süreçte rol alan personel kullanmaz.
- 1 yıl içinde başka bir birimden gelen denetçi, o birimi denetleyemez.
- IIA Etik Kurallarına uyum: dürüstlük, objektiflik, gizlilik, yetkinlik.
- Hediye, ağırlama: yıllık 500 TL üzeri kabul edilmez; üzeri rapor edilir.

## 7. Yetkinlik ve Eğitim

İç denetim ekibinde minimum:
- 1 sertifikalı iç denetçi (CIA, CISA veya muadili)
- 1 KVKK / GDPR sertifikalı (CIPP/E, KVKK uzmanlık eğitimi)
- 1 BT / siber güvenlik denetim deneyimli (CISA, CISSP)

Yıllık 40 saat sürekli mesleki gelişim (CPE).

## 8. Dış Denetim ve Üçüncü Taraf Kullanımı

- Belirli teknik alanlarda (örn. sızma testi, anonimleştirme doğrulama, AI/ML model adili) bağımsız dış uzmanlık alınabilir.
- Dış denetim, iç denetimin yerini almaz; tamamlar.
- Sözleşmede gizlilik ve KVKK yükümlülükleri açık olmalı.

## 9. Sürekli Denetim (Continuous Auditing)

GRC + log entegrasyonu ile otomatik kontrol göstergeleri:
- Hesap oluşturma → DPA varlığı doğrulaması
- VERBİS sapma uyarısı (envanter ↔ VERBİS karşılaştırması)
- İmha gecikme alarmı (saklama süresi dolmuş veri)
- Başvuru SLA yaklaşma uyarısı

## 10. Raporlama Hattı

| Sıklık | Alıcı | İçerik |
|--------|-------|--------|
| Haftalık | İç Denetim Müdürü | Saha durumu |
| Aylık | KVKK Komitesi | Açık bulgular, KPI |
| Çeyreklik | Denetim Komitesi | Tüm denetim raporları, takip |
| Yıllık | Yönetim Kurulu | Yıllık değerlendirme, sonraki yıl planı |
| Olağanüstü | Yön. Kur. Bşk. | Kritik bulgu, anlık |

## 11. İlgili Dokümanlar

- [uyum-olgunluk-modeli.md](uyum-olgunluk-modeli.md)
- [kpi-ve-metrikler.md](kpi-ve-metrikler.md)
- [kurul-denetim-hazirlik.md](kurul-denetim-hazirlik.md)
- [yaptirimlar-cezalar.md](yaptirimlar-cezalar.md)
