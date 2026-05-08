---
Doküman / Document: İdari Tedbirler — Bölüm Girişi / Organizational Measures — Section Introduction
Bölüm / Section: 06-idari-tedbirler
Sahip / Owner: KVKK Sorumlusu / İK Direktörü / Hukuk Müşaviri / KVKK Officer / HR Director / Legal Counsel
Onaylayan / Approved by: KVKK Komitesi + Üst Yönetim / KVKK Committee + Senior Management
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş (mevzuat değişikliği, organizasyonel değişim, ihlal, denetim bulgusu) / Annual + triggered (regulatory change, organizational change, breach, audit finding)
İlgili Mevzuat / Legal Reference: Law No. 6698 KVKK Art. 12; Regulation on the Data Controllers Registry Art. 9(1)(e); Personal Data Security Guide (Technical and Organizational Measures); Law No. 6698 KVKK Art. 4 (General Principles); Labor Law, Turkish Code of Obligations (non-compete, confidentiality), Turkish Criminal Code Art. 135-140 (offences relating to personal data)
İlgili Standart / Standard: ISO/IEC 27001:2022 Clause 5-10 + Annex A (especially A.5 Organizational Controls, A.6 People Controls); ISO/IEC 27701:2019 (Privacy Information Management System); NIST CSF 2.0 GOVERN (GV.OC, GV.RM, GV.SC, GV.PO, GV.OV); NIST Privacy Framework; ENISA Personal Data Protection by Design; OECD Privacy Principles
---

## English

# 06 — Organizational Measures

## 1. Purpose and Scope

Organizational measures cover controls at the human, organizational, process, and contractual layer that ensure the **effective implementation and sustainability** of technical controls. The **human and process arm** of the obligation of "appropriate level of security" under KVKK Art. 12. Even when technical measures are taken, if employee awareness is low, the supplier contract is weak, training is missing, or written policy does not exist, a data breach is inevitable.

The organizational measure topics listed in the KVKK Personal Data Security Guide are mapped to the following documents:

| KVKK Guide Organizational Measure | Equivalent in This Section |
|---------------------------|----------------------|
| Preparation of Personal Data Processing Inventory | [02-envanter-ve-sicil/](../02-envanter-ve-sicil/) |
| Corporate Policies (Access, Information Security, Use, Retention etc.) | [politikalar-prosedurler.md](politikalar-prosedurler.md) |
| Contracts (Between Data Controller and Data Processor) | [tedarikci-yonetimi.md](tedarikci-yonetimi.md) |
| Confidentiality Undertakings | [gizlilik-taahhutnamesi.md](gizlilik-taahhutnamesi.md) |
| Periodic and/or Random Internal Audits | [ic-denetim.md](ic-denetim.md) |
| Risk Analyses | [risk-degerlendirmesi.md](risk-degerlendirmesi.md) |
| Employment Contracts, Contracts Containing Personal Data Annex Protocol | [gizlilik-taahhutnamesi.md](gizlilik-taahhutnamesi.md), [tedarikci-yonetimi.md](tedarikci-yonetimi.md) |
| Internal Communication | [politikalar-prosedurler.md](politikalar-prosedurler.md) |
| Training and Awareness Activities | [personel-egitimi.md](personel-egitimi.md) |
| Data Controllers Registry Information System (VERBİS) Notification | [02-envanter-ve-sicil/](../02-envanter-ve-sicil/) |

## 2. Documents in This Section

| # | Document | Content | Owner |
|---|---------|--------|--------|
| 1 | [politikalar-prosedurler.md](politikalar-prosedurler.md) | Policy set map, lifecycle, approval chain | KVKK Officer + CISO |
| 2 | [personel-egitimi.md](personel-egitimi.md) | Training curriculum, measurement, phishing simulation | HR + KVKK Officer |
| 3 | [gizlilik-taahhutnamesi.md](gizlilik-taahhutnamesi.md) | Employee/consultant/intern undertaking templates | HR + Legal |
| 4 | [tedarikci-yonetimi.md](tedarikci-yonetimi.md) | Classification, due diligence, DPA, audit | Procurement + KVKK Officer |
| 5 | [risk-degerlendirmesi.md](risk-degerlendirmesi.md) | DPIA / PIA, risk score, integration | KVKK Officer + Risk |
| 6 | [ic-denetim.md](ic-denetim.md) | Annual audit plan, test procedure, reporting | Internal Audit |
| 7 | [idari-tedbir-kontrol-listesi.md](idari-tedbir-kontrol-listesi.md) | 60+ item audit checklist | Internal Audit |

## 3. Governance Structure

### 3.1. KVKK Committee

**Members (minimum):**
- Senior Management Representative (Sponsor) — General Manager / Executive Committee Member
- KVKK Officer (Committee Chair / Secretariat)
- Information Security Manager (CISO)
- IT Director
- Legal Counsel / General Secretary
- HR Director
- Communications / Marketing Director
- Risk / Internal Audit Manager (observer)

**Meeting frequency:** Monthly regular + extraordinary.

**Authority:** Policy approval, breach management, application decisions, DPIA approval, vendor approval, acceptance of training and audit results.

### 3.2. KVKK Officer

The "contact person" defined in the KVKK Regulation; in practice corresponds to the **Data Protection Officer / DPO** role in internal organization. This role's:

- Independence is preserved (reports to senior management, not the CISO).
- Sufficient resources (people + budget + access) provided.
- Authority to express independent opinion (in DPIA, vendor, breach assessments).
- Receives ongoing training, attends sectoral sharing events.

### 3.3. RACI Matrix (Organizational Measure Activities)

| Activity | R | A | C | I |
|----------|---|---|----|---|
| Policy drafting | Policy owner team | Relevant Director | KVKK Officer, Legal, CISO | Committee |
| Policy approval | Committee | Senior Management | – | All employees |
| Training design | HR + KVKK Officer | HR Director | CISO, Legal | Committee |
| Training participation | Employee | Line Manager | HR | Committee |
| Vendor due diligence | Procurement + KVKK Officer | Procurement Director | CISO, Legal | Committee |
| Contract signature | Procurement + Legal | General Secretary | KVKK Officer | Committee |
| DPIA | Process owner | KVKK Officer | CISO, Legal, IT | Committee |
| Internal audit | Internal Audit | Audit Committee | KVKK Officer, CISO | Board of Directors |

## 4. Policy Hierarchy (Top Down)

```
1. KVKK Policy (Top Level — Board of Directors Approved)
   ├── 2. Information Security Policy (CISO — Board of Directors Approved)
   ├── 2. Employee Privacy and Notice Policy (KVKK + HR)
   ├── 2. Customer Privacy Notice & Data Protection Policy (KVKK + Marketing)
   ├── 2. Retention and Destruction Policy (KVKK)
   └── 2. Vendor Policy (Procurement + KVKK)
        └── 3. Functional Standards (Access, Encryption, Backup, Incident, etc.)
              └── 4. Procedures / Working Instructions
                    └── 5. Templates / Forms / Checklists
```

No lower-level document may conflict with the upper level. The KVKK Committee decides upon detection of conflict.

## 5. KVKK Organizational Measures and Relevant Court / Decision Framework

**Common finding patterns** related to organizational measure deficiencies in KVKK Authority decisions:

- Absence or non-currency of written policy.
- Absence of a signed data processor contract with the supplier or one not containing the minimum elements required by the KVKK Regulation.
- Periodic training not provided to employees.
- Failure to notify the Authority within 72 hours in case of breach.
- Mismatch between duration / scope information in the privacy notice and actual processing activity.
- Forced explicit consent (presented as a packaged condition — violating KVKK Art. 5).
- VERBİS records not kept current.

Annual training and internal audit address these findings **preventively**.

## 6. Alignment with ISO 27001 / 27701

| ISO 27001/27701 Clause | Equivalent in This Section |
|-------------------------|------------------------|
| Clause 5 (Leadership) | KVKK Committee, Policy approval |
| Clause 6 (Planning, Risk) | risk-degerlendirmesi.md |
| Clause 7 (Support — Resources, Awareness) | personel-egitimi.md |
| Clause 8 (Operation) | All procedures |
| Clause 9 (Performance Evaluation, Internal Audit) | ic-denetim.md |
| Clause 10 (Improvement, CAPA) | ic-denetim.md, breach management |
| A.5 Organizational Controls | politikalar-prosedurler.md, tedarikci-yonetimi.md |
| A.6 People Controls | personel-egitimi.md, gizlilik-taahhutnamesi.md |
| 27701 A.7 (PII Controllers) | KVKK Policy, privacy notice, data protection |
| 27701 A.8 (PII Processors) | tedarikci-yonetimi.md, DPA template |

## 7. Measurement and KPI

- Employee training completion rate (annual refresh): target 100%.
- Phishing simulation click rate: target ≤10% (year-end).
- Vendor due diligence completion rate (new vendor, within 90 days): 100%.
- Risk-based vendor annual review completion rate: 100%.
- DPIA completion rate (in projects where required): 100%.
- Internal audit action closure rate (90 days): ≥80%.
- Policy currency (≤24 months): 100%.
- Confidentiality undertaking signature rate (new starter): 100% within orientation week.
- KVKK breach notification SLA (72 hours to Authority): 100%.
- Data subject application SLA (30 days): 100%.

## 8. Annual Cycle

```
Q1: Policy review + update + Senior Management approval
Q2: Annual training campaign + phishing simulation + vendor review
Q3: Internal audit + DPIA portfolio review
Q4: Annual report (Committee + Board of Directors) + next year's plan
```

## 9. Relationship of This Section to Other Sections

- **00-yonetisim/** — Top-level governance and policy framework.
- **02-envanter-ve-sicil/** — VERBİS, personal data inventory (basic input of organizational measure).
- **03-aydinlatma-ve-acik-riza/** — Privacy notices, explicit consent management.
- **04-veri-saklama-ve-imha/** — Retention and destruction policy.
- **05-teknik-tedbirler/** — Policy expressions are operationalized here.
- **08-ihlal-yonetimi/** — Committee decision and process start here.
- **09-ilgili-kisi-basvurulari/** — Application process training and tracking.
- **11-denetim-ve-uyum/** — Internal audit, external audit, certification.

## 10. Document Versioning and Access

- All organizational measure documents are **versioned**, with last approval date and approver written.
- Access to documents: read access for all employees via intranet; editing only in owner team.
- New starters sign the document set in orientation (read-and-understood record).
- Old versions are kept under [12-mevzuat-arsiv/](../12-mevzuat-arsiv/) (5-year retention for events of which they are evidence).

---

## Türkçe

# 06 — İdari Tedbirler

## 1. Amaç ve Kapsam

İdari tedbirler, teknik kontrollerin **etkin uygulanmasını ve sürdürülebilirliğini** sağlayan; insan, organizasyon, süreç ve sözleşme katmanındaki kontrolleri kapsar. KVKK m.12'nin "uygun güvenlik düzeyi" yükümlülüğünün **insan ve süreç ayağıdır**. Teknik tedbir alındığında bile çalışan farkındalığı düşükse, tedarikçi sözleşmesi zayıfsa, eğitim eksikse, yazılı politika yoksa veri ihlali kaçınılmazdır.

KVKK Veri Güvenliği Rehberi'nde sıralanan idari tedbir başlıkları aşağıdaki dokümanlara haritalanmıştır:

| KVKK Rehberi İdari Tedbir | Bu Bölümde Karşılığı |
|---------------------------|----------------------|
| Kişisel Veri İşleme Envanteri Hazırlama | [02-envanter-ve-sicil/](../02-envanter-ve-sicil/) |
| Kurumsal Politikalar (Erişim, Bilgi Güvenliği, Kullanım, Saklama vb.) | [politikalar-prosedurler.md](politikalar-prosedurler.md) |
| Sözleşmeler (Veri Sorumlusu - Veri İşleyen Arasındaki) | [tedarikci-yonetimi.md](tedarikci-yonetimi.md) |
| Gizlilik Taahhütnameleri | [gizlilik-taahhutnamesi.md](gizlilik-taahhutnamesi.md) |
| Kurum İçi Periyodik ve/veya Rastgele Denetimler | [ic-denetim.md](ic-denetim.md) |
| Risk Analizleri | [risk-degerlendirmesi.md](risk-degerlendirmesi.md) |
| İş Sözleşmeleri, Kişisel Veri Ek Protokol İçeren Sözleşmeler | [gizlilik-taahhutnamesi.md](gizlilik-taahhutnamesi.md), [tedarikci-yonetimi.md](tedarikci-yonetimi.md) |
| Kurumsal İletişim | [politikalar-prosedurler.md](politikalar-prosedurler.md) |
| Eğitim ve Farkındalık Faaliyetleri | [personel-egitimi.md](personel-egitimi.md) |
| Veri Sorumluları Sicil Bilgi Sistemi (VERBİS) Bilgilendirmesi | [02-envanter-ve-sicil/](../02-envanter-ve-sicil/) |

## 2. Bu Bölümdeki Dokümanlar

| # | Doküman | İçerik | Sahibi |
|---|---------|--------|--------|
| 1 | [politikalar-prosedurler.md](politikalar-prosedurler.md) | Politika seti haritası, yaşam döngüsü, onay zinciri | KVKK Sorumlusu + CISO |
| 2 | [personel-egitimi.md](personel-egitimi.md) | Eğitim müfredatı, ölçüm, phishing simülasyonu | İK + KVKK Sorumlusu |
| 3 | [gizlilik-taahhutnamesi.md](gizlilik-taahhutnamesi.md) | Çalışan/danışman/stajyer taahhütname şablonları | İK + Hukuk |
| 4 | [tedarikci-yonetimi.md](tedarikci-yonetimi.md) | Sınıflandırma, due diligence, VİS, denetim | Satınalma + KVKK Sorumlusu |
| 5 | [risk-degerlendirmesi.md](risk-degerlendirmesi.md) | DPIA / PIA, risk skoru, entegrasyon | KVKK Sorumlusu + Risk |
| 6 | [ic-denetim.md](ic-denetim.md) | Yıllık denetim planı, test prosedürü, raporlama | İç Denetim |
| 7 | [idari-tedbir-kontrol-listesi.md](idari-tedbir-kontrol-listesi.md) | 60+ maddelik denetim listesi | İç Denetim |

## 3. Yönetişim Yapısı

### 3.1. KVKK Komitesi

**Üyeler (asgari):**
- Üst Yönetim Temsilcisi (Sponsor) — Genel Müdür / İcra Kurulu Üyesi
- KVKK Sorumlusu (Komite Başkanı / Sekretaryası)
- Bilgi Güvenliği Yöneticisi (CISO)
- BT Direktörü
- Hukuk Müşaviri / Genel Sekreter
- İK Direktörü
- İletişim / Pazarlama Direktörü
- Risk / İç Denetim Yöneticisi (gözlemci)

**Toplantı sıklığı:** Aylık olağan + olağanüstü.

**Yetki:** Politika onayı, ihlal yönetimi, başvuru kararları, DPIA onayı, tedarikçi onayı, eğitim ve denetim sonuçlarının kabulü.

### 3.2. KVKK Sorumlusu

KVKK Yönetmeliği'nde "irtibat kişisi" tanımlı; pratikte iç organizasyonda **Veri Koruma Sorumlusu / DPO** rolüyle eş düşer. Bu rolün:

- Bağımsızlığı korunur (CISO'ya değil, üst yönetime raporlar).
- Yeterli kaynak (insan + bütçe + erişim) sağlanır.
- Bağımsız görüş bildirme yetkisi vardır (DPIA, tedarikçi, ihlal değerlendirmelerinde).
- Sürekli eğitim alır, sektörel paylaşımlara katılır.

### 3.3. RACI Matrisi (İdari Tedbir Faaliyetleri)

| Faaliyet | R | A | C | I |
|----------|---|---|----|---|
| Politika yazımı | Politika sahibi ekip | İlgili Direktör | KVKK Sorumlusu, Hukuk, CISO | Komite |
| Politika onayı | Komite | Üst Yönetim | – | Tüm çalışan |
| Eğitim tasarımı | İK + KVKK Sorumlusu | İK Direktörü | CISO, Hukuk | Komite |
| Eğitim katılımı | Çalışan | Hat Yönetici | İK | Komite |
| Tedarikçi due diligence | Satınalma + KVKK Sorumlusu | Satınalma Direktörü | CISO, Hukuk | Komite |
| Sözleşme imzası | Satınalma + Hukuk | Genel Sekreter | KVKK Sorumlusu | Komite |
| DPIA | Süreç sahibi | KVKK Sorumlusu | CISO, Hukuk, BT | Komite |
| İç denetim | İç Denetim | Denetim Komitesi | KVKK Sorumlusu, CISO | Yönetim Kurulu |

## 4. Politika Hiyerarşisi (Üstten Alta)

```
1. KVKK Politikası (Üst Düzey — Yönetim Kurulu Onaylı)
   ├── 2. Bilgi Güvenliği Politikası (CISO — Yönetim Kurulu Onaylı)
   ├── 2. Çalışan Mahremiyet ve Aydınlatma Politikası (KVKK + İK)
   ├── 2. Müşteri Aydınlatma & Veri Koruma Politikası (KVKK + Pazarlama)
   ├── 2. Saklama ve İmha Politikası (KVKK)
   └── 2. Tedarikçi Politikası (Satınalma + KVKK)
        └── 3. İşlevsel Standartlar (Erişim, Şifreleme, Yedekleme, Olay, vb.)
              └── 4. Prosedürler / Çalışma Talimatları
                    └── 5. Şablonlar / Formlar / Kontrol Listeleri
```

Her seviye, üst seviyeyle çelişemez. Çelişki tespitinde KVKK Komitesi karar verir.

## 5. KVKK İdari Tedbirleri ve İlgili Yargı / Karar Çerçevesi

KVKK Kurulu kararlarında idari tedbir eksikliğine ilişkin **yaygın bulgu örüntüleri**:

- Yazılı politikanın bulunmaması veya güncel olmaması.
- Tedarikçi ile imzalı veri işleyen sözleşmesi olmaması veya KVKK Yönetmeliği'nde aranan asgari unsurları taşımaması.
- Çalışanlara periyodik eğitim verilmemesi.
- İhlal halinde 72 saat içinde Kurul'a bildirim yapılmaması.
- Aydınlatma metnindeki süre / kapsam bilgisinin gerçek işleme faaliyetiyle örtüşmemesi.
- Açık rıza zorlanması (paket koşul olarak sunulması — KVKK m.5'in ihlali).
- VERBİS kayıtlarının güncel tutulmaması.

Yıllık eğitim ve iç denetim, bu bulguları **önleyici** olarak adresler.

## 6. ISO 27001 / 27701 ile Hizalama

| ISO 27001/27701 Maddesi | Bu Bölümde Karşılığı |
|-------------------------|------------------------|
| Clause 5 (Leadership) | KVKK Komitesi, Politika onayı |
| Clause 6 (Planning, Risk) | risk-degerlendirmesi.md |
| Clause 7 (Support — Resources, Awareness) | personel-egitimi.md |
| Clause 8 (Operation) | Tüm prosedürler |
| Clause 9 (Performance Evaluation, Internal Audit) | ic-denetim.md |
| Clause 10 (Improvement, CAPA) | ic-denetim.md, ihlal yönetimi |
| A.5 Organizational Controls | politikalar-prosedurler.md, tedarikci-yonetimi.md |
| A.6 People Controls | personel-egitimi.md, gizlilik-taahhutnamesi.md |
| 27701 A.7 (PII Controllers) | KVKK Politikası, aydınlatma, veri koruma |
| 27701 A.8 (PII Processors) | tedarikci-yonetimi.md, VİS sözleşme şablonu |

## 7. Ölçüm ve KPI

- Çalışan eğitim tamamlama oranı (yıllık tazeleme): hedef %100.
- Phishing simülasyon tıklama oranı: hedef ≤%10 (yıl sonu).
- Tedarikçi due diligence tamamlanma oranı (yeni tedarikçi, 90 gün içinde): %100.
- Risk-bazlı tedarikçi yıllık review tamamlanma oranı: %100.
- DPIA tamamlanma oranı (gerekli olduğu projelerde): %100.
- İç denetim aksiyon kapanma oranı (90 gün): ≥%80.
- Politika güncellik (≤24 ay): %100.
- Gizlilik taahhütname imza oranı (yeni başlayan): %100 oryantasyon haftası içinde.
- KVKK ihlal bildirim SLA (Kurul'a 72 saat): %100.
- İlgili kişi başvuru SLA (30 gün): %100.

## 8. Yıllık Çevrim

```
Q1: Politika review + güncelleme + Üst Yönetim onayı
Q2: Yıllık eğitim kampanyası + phishing simülasyonu + tedarikçi review
Q3: İç denetim + DPIA portföy review
Q4: Yıllık rapor (Komite + Yönetim Kurulu) + sonraki yıl planı
```

## 9. Bu Bölümün Diğer Bölümlerle İlişkisi

- **00-yonetisim/** — Üst seviye yönetişim ve politika çerçevesi.
- **02-envanter-ve-sicil/** — VERBİS, kişisel veri envanteri (idari tedbirin temel girdisi).
- **03-aydinlatma-ve-acik-riza/** — Aydınlatma metinleri, açık rıza yönetimi.
- **04-veri-saklama-ve-imha/** — Saklama ve imha politikası.
- **05-teknik-tedbirler/** — Politika ifadeleri burada operasyonelleşir.
- **08-ihlal-yonetimi/** — Komite kararı ve süreç burada başlar.
- **09-ilgili-kisi-basvurulari/** — Başvuru süreci eğitimi ve takibi.
- **11-denetim-ve-uyum/** — İç denetim, dış denetim, sertifikasyon.

## 10. Doküman Versiyonlama ve Erişim

- Tüm idari tedbir dokümanları **versiyonlu**, son onay tarihi ve onaylayan kişi yazılı.
- Dokümanlara erişim: tüm çalışanlara intranet üzerinden okuma; düzenleme yalnızca sahip ekipte.
- Yeni başlayanlar oryantasyonda doküman setini imzalar (okudum-anladım kaydı).
- Eski sürümler [12-mevzuat-arsiv/](../12-mevzuat-arsiv/) altında muhafaza edilir (delili olduğu olaylar için 5 yıl saklama).
