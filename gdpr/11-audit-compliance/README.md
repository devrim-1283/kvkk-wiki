---
title:
  en: "Audit and Compliance"
  tr: "Denetim ve Uyumluluk"
section: "11-audit-compliance"
owner: "DPO / Compliance"
version: "1.0"
last_review: "2026-05-08"
next_review: "2026-11-08"
classification: "Internal"
languages: ["en", "tr"]
related:
  - "00-governance/README.md"
  - "12-legal-archive/README.md"
  - "99-templates/README.md"
keywords:
  en: ["audit", "compliance", "maturity", "kpi", "supervisory authority", "fines"]
  tr: ["denetim", "uyumluluk", "olgunluk", "kpi", "denetim otoritesi", "para cezalari"]
---

## English

# Section 11 — Audit and Compliance

This section governs how the controller demonstrates ongoing GDPR compliance under the **accountability principle (Article 5(2))**, monitors the effectiveness of technical and organizational measures, prepares for supervisory authority engagement, and manages risk of administrative fines under **Article 83**.

### Scope

The audit and compliance program covers all twelve operational dimensions defined in the maturity model: governance, ROPA, transparency, consent, retention, transfers, technical, organizational, breach, DSR, training, and vendor management. It applies to:

- All processing activities included in the Article 30 ROPA.
- All establishments of the controller within and outside the EEA, where Article 3 (territorial scope) extends GDPR jurisdiction.
- All processors and sub-processors engaged on the basis of Article 28 processing agreements.

### Target audience

| Audience | Use |
|----------|-----|
| Data Protection Officer (Article 37-39) | Owner of audit program and supervisory liaison |
| Internal Audit | Independent assurance, three lines of defense second/third line |
| Senior management and governing body | Receive quarterly assurance reports, approve risk acceptance |
| Process owners and business leads | First line of defense, execute control activities |
| Procurement and vendor management | Implement Article 28 due diligence and ongoing monitoring |
| Information security | Operate technical controls under Article 32 |
| Privacy champions network | Local first-line oversight in business units |
| External auditors and certification bodies | Article 42 certification, ISO 27701, SOC 2, statutory audit |

### How to use this section

1. Read **maturity-model.md** to assess current state across twelve dimensions on a five-level scale.
2. Use **kpi-metrics.md** to operationalize ongoing measurement and dashboarding.
3. Apply **internal-audit.md** to plan, execute, and report annual audit cycles.
4. Use **sa-investigation-prep.md** to prepare for supervisory authority dawn raids, formal inquiries, and information requests.
5. Reference **sanctions-fines.md** for the Article 83 framework, recent enforcement actions, and lessons learned.

### Legal anchors

- **Article 5(2) GDPR** — accountability obliges the controller to demonstrate compliance.
- **Article 24 GDPR** — controller must implement appropriate technical and organizational measures, reviewed and updated where necessary.
- **Article 25 GDPR** — data protection by design and by default, subject to ongoing review.
- **Article 35 GDPR** — DPIAs and prior consultation under Article 36 where residual risk is high.
- **Article 39(1)(b) GDPR** — DPO duty to monitor compliance.
- **Article 58 GDPR** — supervisory authority investigative powers, including audits and on-site inspections.
- **Article 83 GDPR** — administrative fines, two-tier structure (€10M or 2% / €20M or 4% of global annual turnover, whichever is higher).
- **Article 84 GDPR** — additional national penalties.
- **EDPB Guidelines 04/2022** on calculation of administrative fines.

### Three lines of defense

Aligned with the **IIA Three Lines Model**:

| Line | Role | Responsibility |
|------|------|----------------|
| First | Process owners, business leads, system owners | Execute and own controls; identify and mitigate risks day-to-day |
| Second | DPO, privacy office, compliance, information security risk | Set framework, monitor, advise, escalate, challenge first line |
| Third | Internal audit | Independent assurance to the audit committee |

### Audit cycle

The annual cycle has the following phases, with a target of completing one full cycle every twelve months and a higher cadence for high-risk processing activities:

1. **Risk assessment** — refresh inherent risk scoring across the ROPA.
2. **Audit plan** — risk-based selection of in-scope activities for the year.
3. **Fieldwork** — walkthroughs, control testing, sample testing, evidence collection.
4. **Reporting** — findings rated CRITICAL / HIGH / MEDIUM / LOW with corrective actions.
5. **CAPA tracking** — corrective and preventive actions tracked to closure with verification.
6. **Continuous monitoring** — between audit cycles, KPI dashboards and exception alerts feed risk re-assessment.

### Output artefacts

The following artefacts are produced and retained in evidence repositories:

- Annual GDPR audit report.
- Quarterly compliance scorecard.
- Monthly KPI dashboard.
- Maturity self-assessment (annual minimum, semi-annual recommended).
- CAPA register.
- Supervisory authority interaction log.
- Incident and breach register, cross-linked to Article 33 register.

### Cross-references

- For governance structure, see `00-governance/governance-model.md`.
- For ROPA template, see `99-templates/ropa.csv`.
- For breach reporting, see `08-breach-management/`.
- For DSR metrics inputs, see `09-data-subject-rights/`.

---

## Türkçe

# Bölüm 11 — Denetim ve Uyumluluk

Bu bölüm, veri sorumlusunun **hesap verebilirlik ilkesi (Madde 5(2))** uyarınca GDPR uyumunu nasıl sürekli olarak kanıtlayacağını, teknik ve idari tedbirlerin etkinliğini nasıl izleyeceğini, denetim otoritesi etkileşimine nasıl hazırlanacağını ve **Madde 83** kapsamındaki idari para cezası riskini nasıl yöneteceğini düzenler.

### Kapsam

Denetim ve uyumluluk programı, olgunluk modelinde tanımlanan on iki operasyonel boyutu kapsar: yönetişim, VERBİS/ROPA, şeffaflık, açık rıza, saklama, transferler, teknik, idari, ihlal, ilgili kişi talepleri, eğitim ve tedarikçi yönetimi. Aşağıdakilere uygulanır:

- Madde 30 ROPA'ya dahil tüm işleme faaliyetleri.
- AEA içindeki ve dışındaki tüm veri sorumlusu yerleşim yerleri (Madde 3 ülkesel kapsamı).
- Madde 28 işleme sözleşmeleri esasında devreye alınan tüm işleyenler ve alt işleyenler.

### Hedef kitle

| Kitle | Kullanım |
|-------|----------|
| Veri Koruma Görevlisi (Madde 37-39) | Denetim programı sahibi ve denetim otoritesi muhatabı |
| İç Denetim | Üç savunma hattı modeli ikinci/üçüncü hat bağımsız güvence |
| Üst yönetim ve yönetim kurulu | Çeyreklik güvence raporları alır, risk kabulünü onaylar |
| Süreç sahipleri ve iş birimi liderleri | Birinci savunma hattı, kontrol faaliyetlerini yürütür |
| Satın alma ve tedarikçi yönetimi | Madde 28 durum tespiti ve sürekli izleme |
| Bilgi güvenliği | Madde 32 teknik kontrolleri işletir |
| Gizlilik elçileri ağı | İş birimlerinde yerel birinci hat gözetimi |
| Dış denetçiler ve sertifikasyon kuruluşları | Madde 42 sertifikasyon, ISO 27701, SOC 2, yasal denetim |

### Bu bölüm nasıl kullanılır

1. **maturity-model.md** dosyasını okuyarak on iki boyutta beş seviyeli mevcut durumu değerlendirin.
2. Sürekli ölçüm ve gösterge tabloları için **kpi-metrics.md** kullanın.
3. Yıllık denetim döngülerini planlamak, yürütmek ve raporlamak için **internal-audit.md** uygulayın.
4. Denetim otoritesi sabah baskınları, resmi soruşturmalar ve bilgi taleplerine hazırlık için **sa-investigation-prep.md** kullanın.
5. Madde 83 çerçevesi, son yaptırım kararları ve çıkarılan dersler için **sanctions-fines.md** referans alın.

### Hukuki dayanaklar

- **GDPR Madde 5(2)** — hesap verebilirlik, veri sorumlusunu uyumu kanıtlamakla yükümlü kılar.
- **GDPR Madde 24** — veri sorumlusu uygun teknik ve idari tedbirleri uygulamalı, gerektiğinde gözden geçirmeli ve güncellemelidir.
- **GDPR Madde 25** — tasarımda ve varsayılan olarak veri koruması, sürekli gözden geçirmeye tabi.
- **GDPR Madde 35** — yüksek artık riskte VKDM ve Madde 36 ön danışma.
- **GDPR Madde 39(1)(b)** — DPO'nun uyumu izleme görevi.
- **GDPR Madde 58** — yerinde denetim dahil denetim otoritesi soruşturma yetkileri.
- **GDPR Madde 83** — idari para cezaları, iki kademeli yapı (10M EUR veya küresel cironun %2'si / 20M EUR veya küresel cironun %4'ü, hangisi yüksekse).
- **GDPR Madde 84** — ek ulusal cezalar.
- **EDPB Kılavuzu 04/2022** — idari para cezalarının hesaplanması.

### Üç savunma hattı

**IIA Üç Hat Modeli** ile uyumlu:

| Hat | Rol | Sorumluluk |
|-----|-----|------------|
| Birinci | Süreç sahipleri, iş birimi liderleri, sistem sahipleri | Kontrolleri yürütür ve sahiplenir; günlük riskleri tanımlar ve azaltır |
| İkinci | DPO, gizlilik ofisi, uyumluluk, bilgi güvenliği riski | Çerçeveyi belirler, izler, danışmanlık verir, eskalasyon yapar, birinci hattı sorgular |
| Üçüncü | İç denetim | Denetim komitesine bağımsız güvence |

### Denetim döngüsü

Yıllık döngü aşağıdaki aşamalardan oluşur; tam bir döngünün her on iki ayda bir tamamlanması ve yüksek riskli işleme faaliyetleri için daha sık yapılması hedeflenir:

1. **Risk değerlendirmesi** — ROPA genelinde içsel risk skorlamasının yenilenmesi.
2. **Denetim planı** — yıl için kapsama dahil faaliyetlerin risk bazlı seçimi.
3. **Saha çalışması** — süreç turları, kontrol testi, örnekleme testi, kanıt toplama.
4. **Raporlama** — KRİTİK / YÜKSEK / ORTA / DÜŞÜK olarak derecelendirilen bulgular ve düzeltici eylemler.
5. **DÖEP takibi** — düzeltici ve önleyici eylemler kapanışa kadar doğrulanarak izlenir.
6. **Sürekli izleme** — denetim döngüleri arasında KPI panoları ve istisna uyarıları risk yeniden değerlendirmesini besler.

### Üretilen çıktılar

Aşağıdaki çıktılar üretilir ve kanıt depolarında saklanır:

- Yıllık GDPR denetim raporu.
- Çeyreklik uyumluluk skor kartı.
- Aylık KPI panosu.
- Olgunluk öz değerlendirmesi (asgari yıllık, yarı yıllık önerilir).
- DÖEP kayıt defteri.
- Denetim otoritesi etkileşim günlüğü.
- Olay ve ihlal kayıt defteri, Madde 33 kayıt defteri ile çapraz bağlantılı.

### Çapraz referanslar

- Yönetişim yapısı için `00-governance/governance-model.md`.
- ROPA şablonu için `99-templates/ropa.csv`.
- İhlal raporlaması için `08-breach-management/`.
- DSR metrik girdileri için `09-data-subject-rights/`.
