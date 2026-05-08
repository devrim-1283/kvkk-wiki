---
title:
  en: "Internal Audit - Three Lines, Sample Tests, CAPA Tracking"
  tr: "İç Denetim - Üç Hat, Örnek Testler, CAPA Takibi"
section: "06-organizational-measures"
document_type: "programme"
control_id: "ORG-AUD-01"
owner:
  primary: "Head of Internal Audit"
  secondary: "DPO, CISO, Audit Committee"
review_cycle: "annual"
last_review: "2026-05-08"
next_review: "2027-05-08"
classification: "Internal"
language: ["en", "tr"]
references:
  - "GDPR Art. 5(2), 24(1), 32(1)(d), 39(1)(b)"
  - "ISO/IEC 27001:2022 clauses 9.2 (internal audit), 9.3 (management review)"
  - "ISO/IEC 27007:2020 (Guidelines for ISMS auditing)"
  - "ISO/IEC 27701:2019"
  - "IIA Three Lines Model"
  - "NIST CSF 2.0 GV.OV"
---

## English

# Internal Audit Programme

## 1. Purpose

GDPR Article 24(1) requires the controller to be able to "demonstrate that
processing is performed in accordance with this Regulation." Article 32(1)(d)
requires "a process for regularly testing, assessing and evaluating the
effectiveness of technical and organisational measures." Article 39(1)(b)
gives the DPO the task of monitoring compliance.

The internal audit function provides independent assurance to the Board /
Audit Committee that data protection and information security controls are
designed appropriately and operating effectively. It does not replace the
first-line operational ownership or the second-line monitoring activities
of the DPO and CISO; it consumes their evidence and tests independently.

## 2. Three Lines Model

| Line | Function | Audit Programme Touchpoint |
|------|----------|-----------------------------|
| 1 | Business / Engineering / Operations | Self-assessments; control owner attestations |
| 2 | DPO, CISO, Compliance | Continuous monitoring evidence; KPIs; CAPA management |
| 3 | Internal Audit | Independent testing; sample work; reporting to Audit Committee |
| External | Statutory auditors, certification bodies, supervisory authorities | Read internal audit reports as evidence |

## 3. Annual Plan

Plan elements:

- Risk assessment input from DPO, CISO, Legal, Risk function, prior audit
  results, regulator interactions, breach trends, vendor risk register.
- Coverage rotation - every control area examined at least every two cycles
  (`05-technical-measures/technical-controls-checklist.md`,
  `organizational-controls-checklist.md`).
- Mandatory annual audits:
  - ROPA accuracy.
  - Privacy notice deployment.
  - Consent records.
  - Vendor / DPA register.
  - Retention destruction.
  - DSR SLA performance.
  - Breach log and notifications.
  - MFA enforcement.
  - Training completion.
  - Cryptographic inventory and key access.
- Risk-based sampling for the rest.
- Approval by the Audit Committee.

## 4. Audit Methodology (ISO 27007-aligned)

For each engagement:

1. Scope and objectives.
2. Pre-engagement document review.
3. Walkthroughs with control owners.
4. Sample selection (statistical or judgmental, recorded).
5. Tests - documentation, configuration, logs, interviews, observation.
6. Issue drafting (severity, root cause, recommendation).
7. Owner response (acceptance, action plan, target date).
8. Reporting (Audit Committee + DPO + CISO + Executive).
9. CAPA follow-up to closure.

## 5. Sample Test Procedures

### 5.1 ROPA Accuracy
- Select a sample of processing activities.
- Confirm in production that:
  - Lawful basis matches actual operation.
  - Data fields match those declared.
  - Retention rule is enforced.
  - Recipients listed include all real-world recipients (firewall logs, API
    integrations).
  - Cross-border transfer mechanism in place where data crosses borders.
- Cross-reference with vendor list.
- Result: pass / fail / observation.

### 5.2 Privacy Notice Deployment
- Take the published privacy notice version.
- Visit each significant data collection touchpoint (web forms, mobile
  app, in-store, customer support, employee onboarding) and confirm:
  - Notice or layered link is presented before or at collection.
  - Information matches Article 13 / 14 elements.
  - Cookie banner aligned with the notice.
- Test the data subject rights contact channel end to end.

### 5.3 Consent Records
- Sample data subjects with consent-based processing.
- Confirm consent record contains:
  - Identity of the data subject.
  - Consent text and version.
  - Date and channel of consent.
  - Clear separation from other terms (Article 7(2)).
  - Easy withdrawal mechanism.
- Confirm processing stopped on withdrawal.

### 5.4 Vendor Contracts
- Sample active vendors processing personal data.
- Confirm:
  - DPA signed and current (`vendor-management.md`).
  - Sub-processor list current.
  - SCC / TIA where applicable.
  - Audit right exercised per plan.

### 5.5 Retention Destruction
- Sample records past retention.
- Confirm destruction in production and backups
  (`05-technical-measures/backup-recovery.md`).
- Verify destruction certificates filed.

### 5.6 DSR SLA
- Sample requests over the period.
- Verify identity verification, response time, response completeness, and
  data subject feedback.
- Confirm cases handled by processors flowed correctly.

### 5.7 Breach Log
- Sample security incidents (not only those formally classified as breach).
- Confirm assessment against Article 33 / 34 was made.
- Where notification was required, confirm timing within 72 hours and
  content per Article 33(3).
- Confirm breach register entries reflect closure.

### 5.8 MFA Enforcement
- Pull IdP configuration and enforcement reports.
- Sample privileged accounts and confirm phishing-resistant MFA
  (`05-technical-measures/authentication.md`).
- Sample regular accounts and confirm MFA enrolment and enforcement.
- Investigate any exceptions and their compensating controls.

### 5.9 Training Completion
- Sample workforce and confirm:
  - Onboarding training completed within 30 days.
  - Annual refresher current.
  - Role-based modules assigned and completed for relevant roles.
- Sample phishing campaign data and confirm follow-up actions for failures.

### 5.10 Cryptographic Inventory and Key Access
- Sample systems and confirm encryption deployed
  (`05-technical-measures/encryption.md`).
- Pull HSM / KMS access logs and confirm separation of duties.
- Verify key rotations against schedule.

### 5.11 Backup Recovery
- Sample restore drill records.
- Witness or independently re-perform a restore on a sampled backup.
- Confirm RTO / RPO measurements credible and within target.

### 5.12 Logging Integrity
- Verify hash chain and signature on a sample of daily archives
  (`05-technical-measures/logging.md`).
- Verify retention enforcement and deletion controls.

## 6. CAPA (Corrective and Preventive Action)

For each finding:

- Severity (Critical, High, Medium, Low) tied to risk impact and regulatory
  exposure.
- Root cause analysis (5 Whys / fishbone) where Critical / High.
- Corrective action - addresses the immediate issue.
- Preventive action - addresses the systemic cause.
- Owner and approver.
- Target date.
- Verification method (re-test).
- Status updated continuously; visible to Audit Committee.

Aging tolerance:

| Severity | Maximum Age in CAPA |
|----------|---------------------|
| Critical | 30 days |
| High | 90 days |
| Medium | 180 days |
| Low | 365 days |

Overdue Critical or High items escalate automatically to the executive
sponsor and the Audit Committee.

## 7. Reporting

- Engagement-level report - written, with executive summary, findings,
  recommendations, owner responses.
- Quarterly summary - posture trend, top risks, CAPA aging, themes.
- Annual report - full year coverage, opinion on data protection control
  environment, plan for next year.
- Ad hoc - on critical findings or material control breakdowns.

Audit reports are personal data when they reference individuals; access is
restricted accordingly.

## 8. External Audit Coordination

- Statutory auditors and certification bodies receive read access to
  reports relevant to their scope.
- Supervisory authority requests (Article 58) handled per the regulatory
  liaison procedure.
- Joint planning with second-line teams to avoid audit fatigue at first
  line.

## 9. Independence and Competence

- Internal Audit reports administratively to the CEO and functionally to
  the Audit Committee.
- Auditors do not perform operational duties for the controls they audit.
- Auditor competence maintained through ongoing professional development
  (CIA, CISA, CIPP, ISO 27001 LA / LI as relevant).
- Conflicts of interest declared and managed.

## 10. Records and Evidence

- Engagement plan, working papers, evidence samples, draft and final
  reports, owner responses, CAPA tracking.
- Retained 6 years minimum, longer if required by law.
- Stored in the audit repository under access control with audit log on
  access.

## 11. KPIs

| Metric | Target |
|--------|--------|
| Annual plan execution | >= 95 % |
| Critical CAPA items closed within 30 days | 100 % |
| High CAPA items closed within 90 days | >= 95 % |
| Repeat findings (same root cause within 24 months) | 0 |
| Audit reports delivered on schedule | 100 % |
| Audit Committee meetings with audit input | 100 % |

## 12. Mapping

| Requirement | GDPR | ISO 27001/2:2022 | NIST CSF 2.0 |
|-------------|------|------------------|--------------|
| Internal audit | Art. 24(1), 32(1)(d) | 9.2 (27001) | GV.OV-1 |
| Management review | n/a | 9.3 (27001) | GV.OV-2 |
| Continuous improvement | Art. 32(1)(d) | 10.2 (27001) | GV.OV-3 |

## 13. Related Documents

- `policies-procedures.md` - audited policies.
- `training.md` - training completion sampled.
- `vendor-management.md` - vendor controls audited.
- `dpia.md` - DPIA register audited.
- `organizational-controls-checklist.md` - source of audited control set.
- `05-technical-measures/technical-controls-checklist.md` - source of
  audited technical controls.

---

## Türkçe

# İç Denetim Programı

## 1. Amaç

GDPR Madde 24(1), kontrolörün "işlemenin bu Tüzüğe uygun olarak
gerçekleştirildiğini gösterebilmesini" gerektirir. Madde 32(1)(d), "teknik
ve organizasyonel tedbirlerin etkinliğini düzenli olarak test etme,
değerlendirme ve denetleme süreci" gerektirir. Madde 39(1)(b) DPO'ya
uyumluluğu izleme görevi verir.

İç denetim fonksiyonu, veri koruma ve bilgi güvenliği kontrollerinin uygun
şekilde tasarlandığı ve etkin şekilde işlediğine dair Yönetim Kuruluna /
Denetim Komitesine bağımsız güvence sağlar. DPO ve CISO'nun ilk hat
operasyonel sahipliğini veya ikinci hat izleme etkinliklerini değiştirmez;
kanıtlarını tüketir ve bağımsız olarak test eder.

## 2. Üç Hat Modeli

| Hat | Fonksiyon | Denetim Programı Temas Noktası |
|-----|-----------|------------------------------|
| 1 | İş / Mühendislik / Operasyonlar | Öz değerlendirmeler; kontrol sahibi beyanları |
| 2 | DPO, CISO, Uyumluluk | Sürekli izleme kanıtı; KPI'lar; CAPA yönetimi |
| 3 | İç Denetim | Bağımsız test; örneklem çalışması; Denetim Komitesine raporlama |
| Dış | Yasal denetçiler, sertifikasyon kuruluşları, denetim otoriteleri | İç denetim raporlarını kanıt olarak okur |

## 3. Yıllık Plan

Plan unsurları:

- DPO, CISO, Hukuk, Risk fonksiyonu, önceki denetim sonuçları, düzenleyici
  etkileşimleri, ihlal trendleri, tedarikçi risk kayıt defterinden risk
  değerlendirmesi girdisi.
- Kapsam rotasyonu - her kontrol alanı en az iki döngüde bir incelenir
  (`05-technical-measures/technical-controls-checklist.md`,
  `organizational-controls-checklist.md`).
- Zorunlu yıllık denetimler:
  - ROPA doğruluğu.
  - Gizlilik bildirimi dağıtımı.
  - Onay kayıtları.
  - Tedarikçi / DPA kayıt defteri.
  - Saklama imhası.
  - DSR SLA performansı.
  - İhlal logu ve bildirimler.
  - MFA uygulaması.
  - Eğitim tamamlama.
  - Kriptografik envanter ve anahtar erişimi.
- Geri kalan için risk temelli örnekleme.
- Denetim Komitesi tarafından onay.

## 4. Denetim Metodolojisi (ISO 27007 hizalı)

Her görev için:

1. Kapsam ve hedefler.
2. Görev öncesi belge incelemesi.
3. Kontrol sahipleriyle gözden geçirmeler.
4. Örneklem seçimi (istatistiksel veya muhakeme, kayıtlı).
5. Testler - belgeleme, konfigürasyon, loglar, görüşmeler, gözlem.
6. Sorun düzenleme (ciddiyet, kök neden, öneri).
7. Sahip yanıtı (kabul, eylem planı, hedef tarih).
8. Raporlama (Denetim Komitesi + DPO + CISO + Yürütme).
9. Kapanışa kadar CAPA takibi.

## 5. Örnek Test Prosedürleri

### 5.1 ROPA Doğruluğu
- Bir işleme etkinlikleri örneklemini seçin.
- Üretimde teyit edin:
  - Yasal dayanak gerçek operasyona uyuyor.
  - Veri alanları beyan edilenlerle eşleşiyor.
  - Saklama kuralı uygulanıyor.
  - Listelenen alıcılar tüm gerçek dünya alıcılarını içeriyor (güvenlik
    duvarı logları, API entegrasyonları).
  - Veri sınırı geçtiğinde sınır ötesi aktarım mekanizması mevcut.
- Tedarikçi listesiyle çapraz referans.
- Sonuç: geçer / geçmez / gözlem.

### 5.2 Gizlilik Bildirimi Dağıtımı
- Yayımlanmış gizlilik bildirimi sürümünü alın.
- Her önemli veri toplama temas noktasını ziyaret edin (web formları,
  mobil uygulama, mağaza içi, müşteri desteği, çalışan onboarding) ve
  doğrulayın:
  - Toplama öncesinde veya toplamada bildirim veya katmanlı bağlantı sunuluyor.
  - Bilgi Madde 13 / 14 unsurlarıyla eşleşiyor.
  - Çerez bannerı bildirimle hizalı.
- Veri sahibi hakları iletişim kanalını uçtan uca test edin.

### 5.3 Onay Kayıtları
- Onay tabanlı işlemeli veri sahiplerini örnekleyin.
- Onay kaydının şunları içerdiğini doğrulayın:
  - Veri sahibinin kimliği.
  - Onay metni ve sürümü.
  - Onayın tarihi ve kanalı.
  - Diğer şartlardan açık ayrım (Madde 7(2)).
  - Kolay geri çekme mekanizması.
- Geri çekmede işlemenin durdurulduğunu doğrulayın.

### 5.4 Tedarikçi Sözleşmeleri
- Kişisel veri işleyen aktif tedarikçileri örnekleyin.
- Doğrulayın:
  - DPA imzalandı ve güncel (`vendor-management.md`).
  - Alt-işleyici listesi güncel.
  - Geçerli olduğunda SCC / TIA.
  - Plana göre kullanılan denetim hakkı.

### 5.5 Saklama İmhası
- Saklama süresi geçmiş kayıtları örnekleyin.
- Üretimde ve yedeklerde imhayı doğrulayın
  (`05-technical-measures/backup-recovery.md`).
- İmha sertifikalarının dosyalandığını doğrulayın.

### 5.6 DSR SLA
- Dönem boyunca taleplerden örnekleyin.
- Kimlik doğrulama, yanıt süresi, yanıt eksiksizliği ve veri sahibi geri
  bildirimini doğrulayın.
- İşleyiciler tarafından ele alınan vakaların doğru aktığını doğrulayın.

### 5.7 İhlal Logu
- Güvenlik olaylarını örnekleyin (yalnızca resmi olarak ihlal olarak
  sınıflandırılanları değil).
- Madde 33 / 34'e karşı değerlendirmenin yapıldığını doğrulayın.
- Bildirim gerektiğinde, 72 saat içinde zamanlama ve Madde 33(3) başına
  içeriği doğrulayın.
- İhlal kayıt defteri girişlerinin kapanışı yansıttığını doğrulayın.

### 5.8 MFA Uygulaması
- IdP konfigürasyonunu ve uygulama raporlarını çekin.
- Ayrıcalıklı hesapları örnekleyin ve phishing'e dayanıklı MFA'yı doğrulayın
  (`05-technical-measures/authentication.md`).
- Düzenli hesapları örnekleyin ve MFA kaydı ile uygulamayı doğrulayın.
- Herhangi bir istisna ve telafi edici kontrollerini araştırın.

### 5.9 Eğitim Tamamlama
- İş gücünü örnekleyin ve doğrulayın:
  - Onboarding eğitimi 30 gün içinde tamamlandı.
  - Yıllık tazeleme güncel.
  - İlgili roller için atanmış ve tamamlanmış rol bazlı modüller.
- Phishing kampanyası verisini örnekleyin ve başarısızlıklar için takip
  eylemlerini doğrulayın.

### 5.10 Kriptografik Envanter ve Anahtar Erişimi
- Sistemleri örnekleyin ve şifrelemenin dağıtıldığını doğrulayın
  (`05-technical-measures/encryption.md`).
- HSM / KMS erişim loglarını çekin ve görev ayrımını doğrulayın.
- Anahtar rotasyonlarını programa karşı doğrulayın.

### 5.11 Yedek Geri Yükleme
- Geri yükleme tatbikat kayıtlarını örnekleyin.
- Örneklenen bir yedekte geri yüklemeyi tanık olun veya bağımsız olarak
  yeniden gerçekleştirin.
- RTO / RPO ölçümlerinin güvenilir ve hedef içinde olduğunu doğrulayın.

### 5.12 Loglama Bütünlüğü
- Günlük arşivlerin örnekleminde hash zinciri ve imzayı doğrulayın
  (`05-technical-measures/logging.md`).
- Saklama uygulamasını ve silme kontrollerini doğrulayın.

## 6. CAPA (Düzeltici ve Önleyici Eylem)

Her bulgu için:

- Risk etkisi ve düzenleyici maruziyetle bağlı ciddiyet (Kritik, Yüksek,
  Orta, Düşük).
- Kritik / Yüksek olan yerde kök neden analizi (5 Neden / kılçık).
- Düzeltici eylem - acil sorunu ele alır.
- Önleyici eylem - sistemik nedeni ele alır.
- Sahip ve onaylayan.
- Hedef tarih.
- Doğrulama yöntemi (yeniden test).
- Durum sürekli güncellenir; Denetim Komitesine görünür.

Yaşlanma toleransı:

| Ciddiyet | CAPA'da Azami Yaş |
|----------|-------------------|
| Kritik | 30 gün |
| Yüksek | 90 gün |
| Orta | 180 gün |
| Düşük | 365 gün |

Geciken Kritik veya Yüksek maddeler yürütme sponsoruna ve Denetim
Komitesine otomatik yükselir.

## 7. Raporlama

- Görev seviyesi raporu - yazılı, yürütme özeti, bulgular, öneriler, sahip
  yanıtları ile.
- Üç aylık özet - duruş trendi, en yüksek riskler, CAPA yaşlanması, temalar.
- Yıllık rapor - tam yıl kapsamı, veri koruma kontrol ortamına ilişkin
  görüş, gelecek yıl için plan.
- Ad hoc - kritik bulgularda veya maddi kontrol bozulmalarında.

Denetim raporları bireylere referans verdiğinde kişisel veridir; erişim
buna göre kısıtlanır.

## 8. Dış Denetim Koordinasyonu

- Yasal denetçiler ve sertifikasyon kuruluşları kapsamlarına ilişkin
  raporlara okuma erişimi alır.
- Denetim otoritesi talepleri (Madde 58) düzenleyici irtibat prosedürü
  uyarınca ele alınır.
- İlk hatta denetim yorgunluğunu önlemek için ikinci hat ekipleriyle ortak
  planlama.

## 9. Bağımsızlık ve Yetkinlik

- İç Denetim idari olarak CEO'ya, fonksiyonel olarak Denetim Komitesine
  raporlar.
- Denetçiler, denetledikleri kontroller için operasyonel görev yapmaz.
- Denetçi yetkinliği sürekli mesleki gelişim aracılığıyla sürdürülür (CIA,
  CISA, CIPP, ilgili ölçüde ISO 27001 LA / LI).
- Çıkar çatışmaları beyan edilir ve yönetilir.

## 10. Kayıtlar ve Kanıt

- Görev planı, çalışma kağıtları, kanıt örneklemleri, taslak ve nihai
  raporlar, sahip yanıtları, CAPA takibi.
- Asgari 6 yıl, hukuk gerektiriyorsa daha uzun saklanır.
- Erişimde denetim logu ile erişim kontrolü altında denetim deposunda
  saklanır.

## 11. KPI'lar

| Metrik | Hedef |
|--------|-------|
| Yıllık plan yürütme | >= %95 |
| 30 gün içinde kapanan Kritik CAPA maddeleri | %100 |
| 90 gün içinde kapanan Yüksek CAPA maddeleri | >= %95 |
| Tekrarlayan bulgular (24 ay içinde aynı kök neden) | 0 |
| Programa göre teslim edilen denetim raporları | %100 |
| Denetim girdili Denetim Komitesi toplantıları | %100 |

## 12. Eşleme

| Gereklilik | GDPR | ISO 27001/2:2022 | NIST CSF 2.0 |
|------------|------|------------------|--------------|
| İç denetim | Md. 24(1), 32(1)(d) | 9.2 (27001) | GV.OV-1 |
| Yönetim incelemesi | yok | 9.3 (27001) | GV.OV-2 |
| Sürekli iyileştirme | Md. 32(1)(d) | 10.2 (27001) | GV.OV-3 |

## 13. İlgili Belgeler

- `policies-procedures.md` - denetlenen politikalar.
- `training.md` - örneklenen eğitim tamamlama.
- `vendor-management.md` - denetlenen tedarikçi kontrolleri.
- `dpia.md` - denetlenen VKD kayıt defteri.
- `organizational-controls-checklist.md` - denetlenen kontrol setinin
  kaynağı.
- `05-technical-measures/technical-controls-checklist.md` - denetlenen
  teknik kontrollerin kaynağı.
