---
title:
  en: "Transfer Impact Assessment (TIA) Methodology"
  tr: "Transfer Etki Değerlendirmesi (TIA) Metodolojisi"
section: "07-international-transfers"
document_type: "methodology"
regulation: "GDPR (EU 2016/679)"
articles:
  - "Art. 44 — General principle"
  - "Art. 46 — Appropriate safeguards"
  - "Art. 48 — Foreign access"
key_caselaw:
  - "C-311/18 Schrems II (2020)"
key_guidance:
  - "EDPB Recommendations 01/2020 — supplementary measures"
  - "EDPB Recommendations 02/2020 — European Essential Guarantees for surveillance"
language: "en, tr"
last_reviewed: "2025-05-01"
review_cycle: "annual"
owner: "Data Protection Officer"
co_owner: "Legal"
status: "approved"
classification: "internal"
---

## English

# Transfer Impact Assessment (TIA) Methodology

## 1. Purpose

The TIA is the documented analysis required by **Schrems II** (CJEU C-311/18, 16 July 2020) and codified in **Clause 14 of the 2021/914 SCCs** and in the post-Schrems II BCR criteria. It assesses, on a transfer-by-transfer basis, whether the law and practice of the destination country allow the importer to comply with the transfer instrument and whether **essentially equivalent protection** is provided.

This methodology follows **EDPB Recommendations 01/2020 v2.0** (10 June 2021), which set out a six-step process and reference **EDPB Recommendations 02/2020** (the European Essential Guarantees for surveillance).

## 2. The six steps (EDPB Recommendations 01/2020)

### Step 1 — Know your transfers

Map every transfer:

- Parties: exporter, importer, role (controller / processor / sub-processor).
- Categories of data subjects.
- Categories of data and special-category status.
- Volume and frequency.
- Purpose.
- Storage period.
- Sub-processors.
- Onward transfers.
- Hosting locations (regions).
- Data subject access (whether the data subject is in the EEA or elsewhere).

The RoPA is the starting point. Identify gaps.

### Step 2 — Identify the transfer tool

Confirm the Article 46 instrument:
- SCC (which module).
- BCR (BCR-C / BCR-P).
- Code of conduct.
- Certification.

If relying on Art. 45 adequacy, no TIA is required for that flow (but document the basis).
If relying on Art. 49 derogation, document the derogation conditions; TIA-equivalent assessment of necessity and proportionality required.

### Step 3 — Assess the law and practice of the third country

Assess whether anything in the destination country's law or practice impinges on the transfer tool's effectiveness.

#### 3.1 Sources

- National laws and regulations (constitution, data protection act, surveillance laws, sectoral laws).
- Implementing regulations and case law.
- Public reports (transparency reports, civil-society analyses).
- Government statements.
- EDPB statements on third countries.
- Sector-specific peer benchmarks.
- Importer-provided information (transparency reports, government request statistics).

#### 3.2 The European Essential Guarantees (EDPB Recommendations 02/2020)

For any country whose surveillance regime is in scope, assess against:

| EEG | Description |
|---|---|
| **EEG 1** | Processing should be based on clear, precise, and accessible rules. |
| **EEG 2** | Necessity and proportionality with regard to the legitimate objectives pursued must be demonstrated. |
| **EEG 3** | An independent oversight mechanism should exist. |
| **EEG 4** | Effective remedies need to be available to the individual. |

Where the destination law fails one or more EEGs in a manner that affects the transfer, supplementary measures (Step 4) are required, or the transfer must not proceed.

#### 3.3 Country-specific summary (for context — verify current state)

##### United States

- **FISA Section 702** (50 USC § 1881a): allows targeting of non-US persons reasonably believed to be outside the US for foreign-intelligence information; covers electronic communication service providers; bulk capability concerns; *Schrems II* held that 702 fails to meet EEG.
- **Executive Order 12333**: signals intelligence collection outside the US, no statutory basis or independent judicial review historically.
- **Executive Order 14086 (October 2022)** and AG regulations introduced limitations and a redress mechanism (Data Protection Review Court). The Commission relied on these in granting the 2023 DPF adequacy decision.
- **CLOUD Act (2018)**: extraterritorial production orders; data subject to providers under US jurisdiction even when stored abroad.
- **Sectoral**: HIPAA, GLBA, COPPA, etc.

For non-DPF transfers, supplementary measures are typically required.

##### United Kingdom

- **Data Protection Act 2018 + UK GDPR**: equivalent framework.
- **Investigatory Powers Act 2016 (IPA 2016)**: surveillance powers; oversight via IPCO and Investigatory Powers Tribunal.
- Currently subject to a 2021 EU adequacy decision (sunset 2025 unless renewed).
- TIA may rely on the adequacy decision; monitor for renewal.

##### China (PRC)

- **Cybersecurity Law (2017)**: data localisation for "critical information infrastructure operators".
- **Data Security Law (2021)**: classifies data by sensitivity; cross-border restrictions; cooperation with national security demands.
- **Personal Information Protection Law (PIPL, 2021)**: domestic GDPR-style law but with strong national-security carve-outs.
- **Article 41 of PIPL**: cross-border data export rules — security assessment, certification, or standard contract.
- Government access regime: limited statutory limits and remedies; concerns under EEG.
- TIA: typically high risk; supplementary measures (encryption with controller-held keys, minimisation) essential or transfers should be reconsidered.

##### Russia

- **Federal Law 152-FZ "On Personal Data" (2006, amended)**: data localisation requirements (Russian citizens' data first stored in Russia).
- **Yarovaya Law (2016)**: communications retention and decryption; broad government access.
- Sanctions regime since 2022 has further complicated transfers.
- TIA: very high risk; transfers limited.

##### India

- **Digital Personal Data Protection Act 2023 (DPDPA)**: domestic data-protection law in force; rules under development as of mid-2025.
- Government access powers under various statutes (Information Technology Act 2000, telecom rules); concerns about lack of judicial oversight.
- TIA: country-specific assessment; supplementary measures often advisable.

##### Brazil, Switzerland, Japan, South Korea, Argentina, etc.

Adequate decision (or close-to-adequate framework) — TIA may rely heavily on the adequacy basis or be lighter.

##### Other (no adequacy)

Country-specific TIA needed. Look at the actual surveillance framework and effective oversight.

#### 3.4 The "subjective + objective" assessment

EDPB requires assessing both **the relevant legislation** and **the practice** (e.g., whether providers in the destination country have been served with surveillance orders, the nature of those orders, the redress available). The importer's input (transparency reports, internal records, declarations under Clause 15) feeds the analysis.

### Step 4 — Identify and adopt supplementary measures

Where Step 3 reveals risk that surveillance or other access could affect the transfer's compliance, supplementary measures are required to bring protection up to "essentially equivalent".

#### 4.1 Technical measures

Most effective when properly implemented:

| Measure | Description |
|---|---|
| **End-to-end encryption** with controller-held keys | Importer cannot decrypt; data remains protected even if disclosed. Strong against bulk-access regimes. |
| **Pseudonymisation with controller-held mapping** | Importer sees pseudonyms only; identifying mapping never leaves EU. |
| **Split processing / multi-party computation** | No single jurisdiction holds full data. |
| **Confidential computing / TEE** | Data remains encrypted during processing. |
| **Secure multi-party computation, homomorphic encryption** | Specialised; high cost. |
| **Data minimisation (transfer only what is necessary)** | Reduce attack surface. |
| **Storage limitation** | Reduce retention to operational minimum. |

EDPB Annex 2 of Recommendations 01/2020 provides scenario-specific examples.

#### 4.2 Contractual measures

- Importer commitment to challenge access requests.
- Notification obligations beyond Clause 15 minimums.
- Audit rights.
- Transparency report commitments.
- Onward-transfer prohibitions.
- Termination / suspension rights with data return.
- Indemnities.

#### 4.3 Organisational measures

- Strict access control (need-to-know, separation of duties).
- Training and awareness on surveillance handling.
- Formal procedure for handling government requests.
- Privacy-by-design enhancements.
- Vendor management oversight.
- Periodic audit.

#### 4.4 Effectiveness

A measure is effective only if it actually neutralises the residual risk. For example, encryption with importer-held keys is **not effective** against a regime that can compel the importer to surrender keys.

### Step 5 — Take procedural steps

Depending on the safeguard adopted:
- **SCCs**: confirm Annex II (TOMs) reflects supplementary measures; sign with the warranties of Clause 14.
- **BCR**: ensure the BCR programme captures supplementary measures.
- **Authorisation under Art. 46(3)**: SA authorisation required.
- **Where the assessment cannot conclude positively even with supplementary measures**: do not transfer.

### Step 6 — Re-evaluate at appropriate intervals

Continuous duty:

- Annual TIA review at minimum.
- Event-driven review on:
  - New surveillance laws or amendments.
  - New CJEU rulings.
  - New EDPB statements.
  - Government access requests received under Clause 15.
  - Material change in importer operations or location.
  - Material change in data flows.
  - Security incidents.

## 3. TIA documentation

### 3.1 Mandatory documentation

| Section | Content |
|---|---|
| 1. Identification | Transfer ID, date, parties, RoPA reference. |
| 2. Description of transfer | Categories, volume, purpose, frequency, sub-processors. |
| 3. Transfer tool | SCC module / BCR / other; signed copies referenced. |
| 4. Country assessment | Laws and practice; EEG analysis; importer-provided data. |
| 5. Risk analysis | What could go wrong; likelihood; severity. |
| 6. Supplementary measures | Technical, contractual, organisational. Effectiveness justification. |
| 7. Conclusion | Equivalence achieved / not achieved; transfer permitted / not. |
| 8. Approvals | Data owner, DPO, Legal sign-off. |
| 9. Review schedule | Next review date; trigger events. |

### 3.2 Record retention

The TIA is part of accountability evidence (Art. 5(2)). Retain for 6 years after the transfer ceases (or longer where required).

## 4. Assessment template

```yaml
tia_id: TIA-YYYY-NNNN
date_initial: YYYY-MM-DD
date_review: YYYY-MM-DD
ropa_ref: RoPA-NNNN
exporter:
  name: ...
  role: controller / processor
  establishment: EU member state
importer:
  name: ...
  role: controller / processor / sub-processor
  country: ...
  establishment: ...
transfer:
  data_subjects: [employees, customers, ...]
  data_categories: [contact, payment, ...]
  special_categories: [yes/no, which]
  children: [yes/no]
  volume: estimate
  frequency: ongoing / periodic / one-off
  purpose: ...
  storage_period: ...
  sub_processors: [...]
  onward_transfers: [...]
mechanism:
  type: SCC-2021/914 / BCR / Art-49 / Art-45
  details: module 2 (C2P); signed YYYY-MM-DD
country_assessment:
  surveillance_laws: [...]
  EEG_1_assessment: ...
  EEG_2_assessment: ...
  EEG_3_assessment: ...
  EEG_4_assessment: ...
  importer_inputs: [transparency report, declaration, ...]
  risk_level: low / medium / high
supplementary_measures:
  technical: [...]
  contractual: [...]
  organisational: [...]
  effectiveness_justification: ...
conclusion:
  equivalence_achieved: yes / yes-with-measures / no
  decision: proceed / suspend / do-not-transfer
approvals:
  data_owner: ...
  DPO: ...
  legal: ...
review:
  next_due: YYYY-MM-DD
  triggers: [new law, new caselaw, new measures, incident]
```

## 5. Practical examples

### 5.1 EU controller → US SaaS (non-DPF)

- Mechanism: SCC Module 2 (C2P).
- Country assessment: FISA 702, EO 12333, EO 14086 partial mitigation; importer is "electronic communication service provider".
- Risk: high if in clear; medium with mitigations.
- Supplementary measures:
  - Encryption at rest and in transit with controller-managed keys (CMEK / BYOK).
  - End-to-end encryption for sensitive fields where feasible.
  - Pseudonymisation in primary store; mapping retained EU-side.
  - Importer commitment to challenge access requests + transparency report.
  - Sub-processor restrictions to non-US-jurisdiction where feasible.
- Conclusion: proceed with documented measures; review at 12 months.

### 5.2 EU controller → US SaaS (DPF-certified)

- Mechanism: Art. 45 (DPF).
- Country assessment: covered by Commission decision; minimal further analysis.
- Risk: as assessed by Commission; monitor for changes (Schrems III risk).
- Supplementary measures: optional / customer-driven.
- Conclusion: proceed; verify recipient certification is current; monitor DPF status.

### 5.3 EU controller → India offshore support processor

- Mechanism: SCC Module 2 (C2P).
- Country assessment: DPDPA (2023) + IT Act + telecom; oversight gaps; high access risk.
- Supplementary measures:
  - Pseudonymisation; mapping retained EU-side.
  - Restricted personnel access via VPN/VDI; data not stored locally.
  - Strong contractual restrictions; mandatory training.
  - Audit rights.
  - Notification commitments.
- Conclusion: proceed with measures; review at 12 months or upon DPDPA rules finalisation.

### 5.4 EU controller → Chinese hosting

- Mechanism: SCC Module 2 + supplementary.
- Country assessment: Cybersecurity Law, Data Security Law, PIPL, government access regime; high risk.
- Supplementary measures: limited utility against compelled disclosure.
- Conclusion: in many cases, **do not transfer** unless (a) data is encrypted such that the importer cannot decrypt and (b) processing is local-only with no decrypted access in China; even then, careful case-by-case.

## 6. Limitations of supplementary measures

EDPB acknowledges that not every surveillance scenario can be neutralised by supplementary measures. For example, where the data must be in clear at the importer to perform the service, encryption alone is insufficient against compelled-disclosure regimes. In such cases, the transfer must be suspended or restructured (e.g., move processing to an adequate country).

## 7. Common pitfalls

| Pitfall | Mitigation |
|---|---|
| TIA generic, not country-specific | Country-by-country EEG analysis with current sources |
| Ignoring practice (only law) | Include importer transparency reports, civil-society analyses |
| No assessment of supplementary measure effectiveness | Document why each measure addresses the residual risk |
| TIA done once, never reviewed | Annual + event-driven |
| TIA not signed off by DPO and Legal | Full sign-off chain |
| TIA not linked to RoPA | Cross-reference both ways |
| Treating sub-processor flow as identical to processor flow | Separate analysis for each leg |
| Overlooking onward transfers | Walk the full data path |

---

## Türkçe

# Transfer Etki Değerlendirmesi (TIA) Metodolojisi

## 1. Amaç

TIA, **Schrems II** (ABAD C-311/18, 16 Temmuz 2020) tarafından gerekli kılınan ve **2021/914 SCC'lerinin Madde 14'ünde** ve Schrems II sonrası BCR kriterlerinde kodifiye edilmiş belgelenmiş analizdir. Transfer bazında, hedef ülkenin hukukunun ve uygulamasının ithalatçının transfer enstrümanına uymasına izin verip vermediğini ve **esasen eşdeğer korumanın** sağlanıp sağlanmadığını değerlendirir.

Bu metodoloji, altı adımlı bir süreç belirleyen ve **EDPB Tavsiyeleri 02/2020**'ye (gözetim için Avrupa Temel Garantileri) atıfta bulunan **EDPB Tavsiyeleri 01/2020 v2.0**'ı (10 Haziran 2021) izler.

## 2. Altı adım (EDPB Tavsiyeleri 01/2020)

### Adım 1 — Transferlerinizi tanıyın

Her transferi haritalayın:

- Taraflar: ihracatçı, ithalatçı, rol (kontrolör / işleyen / alt-işleyen).
- İlgili kişi kategorileri.
- Veri kategorileri ve özel kategori durumu.
- Hacim ve sıklık.
- Amaç.
- Saklama süresi.
- Alt-işleyenler.
- İleri transferler.
- Barındırma konumları (bölgeler).
- İlgili kişi erişimi (ilgili kişi AAA'da mı yoksa başka yerde mi).

RoPA başlangıç noktasıdır. Boşlukları belirleyin.

### Adım 2 — Transfer aracını tanımla

Madde 46 enstrümanını onayla:
- SCC (hangi modül).
- BCR (BCR-C / BCR-P).
- Davranış kuralları.
- Sertifikasyon.

Md. 45 yeterliliğine dayanılıyorsa, bu akış için TIA gerekli değildir (ancak dayanağı belgele).
Md. 49 istisnasına dayanılıyorsa, istisna koşullarını belgele; gerekliliğin ve orantılılığın TIA-eşdeğeri değerlendirmesi gerekli.

### Adım 3 — Üçüncü ülkenin hukukunu ve uygulamasını değerlendir

Hedef ülkenin hukukunda veya uygulamasında transfer aracının etkinliğini etkileyen herhangi bir şey olup olmadığını değerlendirin.

#### 3.1 Kaynaklar

- Ulusal yasalar ve düzenlemeler (anayasa, veri koruma yasası, gözetim yasaları, sektörel yasalar).
- Uygulama düzenlemeleri ve içtihat.
- Kamu raporları (şeffaflık raporları, sivil toplum analizleri).
- Hükümet açıklamaları.
- Üçüncü ülkelerde EDPB açıklamaları.
- Sektöre özgü emsal kıyaslamaları.
- İthalatçı tarafından sağlanan bilgiler (şeffaflık raporları, hükümet talep istatistikleri).

#### 3.2 Avrupa Temel Garantileri (EDPB Tavsiyeleri 02/2020)

Gözetim rejimi kapsamda olan herhangi bir ülke için, şunlara karşı değerlendirin:

| EEG | Açıklama |
|---|---|
| **EEG 1** | İşleme, açık, kesin ve erişilebilir kurallara dayanmalıdır. |
| **EEG 2** | Takip edilen meşru hedeflere göre gereklilik ve orantılılık gösterilmelidir. |
| **EEG 3** | Bağımsız bir gözetim mekanizması var olmalıdır. |
| **EEG 4** | Bireye etkili çareler mevcut olmalıdır. |

Hedef hukuk transferi etkileyecek şekilde bir veya daha fazla EEG'yi karşılayamadığında, tamamlayıcı önlemler (Adım 4) gereklidir veya transfer ilerleyemez.

#### 3.3 Ülkeye özel özet (bağlam için — mevcut durumu doğrulayın)

##### Amerika Birleşik Devletleri

- **FISA Bölüm 702** (50 USC § 1881a): ABD dışında olduğuna makul olarak inanılan ABD vatandaşı olmayanları yabancı istihbarat bilgisi için hedeflemeye izin verir; elektronik iletişim hizmet sağlayıcılarını kapsar; toplu kapasite endişeleri; *Schrems II* 702'nin EEG'yi karşılamadığına karar verdi.
- **Yürütme Kararı 12333**: ABD dışında sinyal istihbaratı toplama, tarihsel olarak yasal dayanak veya bağımsız yargı incelemesi yoktur.
- **Yürütme Kararı 14086 (Ekim 2022)** ve AG düzenlemeleri sınırlamalar ve bir başvuru mekanizması (Veri Koruma İnceleme Mahkemesi) tanıttı. Komisyon 2023 DPF yeterlilik kararını verirken bunlara dayandı.
- **CLOUD Act (2018)**: ülke dışı üretim emirleri; ABD yargısına tabi sağlayıcılara tabi veri yurt dışında saklanırken bile.
- **Sektörel**: HIPAA, GLBA, COPPA vb.

DPF olmayan transferler için, tamamlayıcı önlemler tipik olarak gereklidir.

##### Birleşik Krallık

- **Veri Koruma Yasası 2018 + UK GDPR**: eşdeğer çerçeve.
- **Soruşturma Yetkileri Yasası 2016 (IPA 2016)**: gözetim yetkileri; IPCO ve Soruşturma Yetkileri Tribünali aracılığıyla gözetim.
- Şu anda 2021 AB yeterlilik kararına tabi (yenilenmezse 2025 sunset).
- TIA yeterlilik kararına dayanabilir; yenileme için izleyin.

##### Çin (ÇHC)

- **Siber Güvenlik Yasası (2017)**: "kritik bilgi altyapısı operatörleri" için veri yerelleştirmesi.
- **Veri Güvenliği Yasası (2021)**: veriyi hassasiyete göre sınıflandırır; sınır ötesi kısıtlamalar; ulusal güvenlik talepleriyle işbirliği.
- **Kişisel Bilgi Koruma Yasası (PIPL, 2021)**: yerel GDPR tarzı yasa ancak güçlü ulusal güvenlik istisnalarıyla.
- **PIPL'in 41. Maddesi**: sınır ötesi veri ihracat kuralları — güvenlik değerlendirmesi, sertifikasyon veya standart sözleşme.
- Hükümet erişim rejimi: sınırlı yasal sınırlar ve çareler; EEG altında endişeler.
- TIA: tipik olarak yüksek risk; tamamlayıcı önlemler (kontrolör tarafından tutulan anahtarlarla şifreleme, minimizasyon) esastır veya transferler yeniden değerlendirilmelidir.

##### Rusya

- **Federal Yasa 152-FZ "Kişisel Veriler Üzerine" (2006, değişiklik)**: veri yerelleştirme gereksinimleri (Rus vatandaşlarının verisi önce Rusya'da saklanır).
- **Yarovaya Yasası (2016)**: iletişim saklama ve şifre çözme; geniş hükümet erişimi.
- 2022'den beri yaptırım rejimi transferleri daha da karmaşıklaştırdı.
- TIA: çok yüksek risk; transferler sınırlı.

##### Hindistan

- **Dijital Kişisel Veri Koruma Yasası 2023 (DPDPA)**: yerel veri koruma yasası yürürlükte; 2025 ortası itibarıyla kurallar geliştirme aşamasında.
- Çeşitli tüzükler altında hükümet erişim yetkileri (Bilgi Teknolojisi Yasası 2000, telekom kuralları); yargısal gözetim eksikliği konusunda endişeler.
- TIA: ülkeye özel değerlendirme; tamamlayıcı önlemler genellikle tavsiye edilir.

##### Brezilya, İsviçre, Japonya, Güney Kore, Arjantin vb.

Yeterli karar (veya yeterliliğe yakın çerçeve) — TIA yeterlilik dayanağına büyük ölçüde dayanabilir veya daha hafif olabilir.

##### Diğer (yeterlilik yok)

Ülkeye özel TIA gerekli. Gerçek gözetim çerçevesine ve etkili gözetime bakın.

#### 3.4 "Öznel + nesnel" değerlendirme

EDPB hem **ilgili mevzuatın** hem de **uygulamanın** değerlendirilmesini gerektirir (örn. hedef ülkedeki sağlayıcılara gözetim emirleri verilip verilmediği, bu emirlerin doğası, mevcut başvuru). İthalatçının girdisi (şeffaflık raporları, dahili kayıtlar, Madde 15 kapsamındaki bildirimler) analizi besler.

### Adım 4 — Tamamlayıcı önlemleri belirle ve kabul et

Adım 3 gözetimin veya diğer erişimin transferin uyumunu etkileyebileceği riskini ortaya çıkardığında, korumayı "esasen eşdeğer" seviyesine getirmek için tamamlayıcı önlemler gereklidir.

#### 4.1 Teknik önlemler

Doğru uygulandığında en etkili:

| Önlem | Açıklama |
|---|---|
| **Kontrolör tarafından tutulan anahtarlarla uçtan uca şifreleme** | İthalatçı şifre çözemez; veri açıklansa bile korunmaya devam eder. Toplu erişim rejimlerine karşı güçlü. |
| **Kontrolör tarafından tutulan eşleme ile takma adlandırma** | İthalatçı yalnızca takma adları görür; tanımlama eşlemesi AB'den ayrılmaz. |
| **Bölünmüş işleme / çok taraflı hesaplama** | Tek bir yargı yetkisi tam veriyi tutmaz. |
| **Gizli hesaplama / TEE** | Veri işleme sırasında şifrelenmiş kalır. |
| **Güvenli çok taraflı hesaplama, homomorfik şifreleme** | Uzmanlık; yüksek maliyet. |
| **Veri minimizasyonu (yalnızca gerekli olanı transfer et)** | Saldırı yüzeyini azalt. |
| **Saklama sınırlaması** | Saklamayı operasyonel minimuma azalt. |

EDPB Tavsiyeleri 01/2020 Ek 2 senaryoya özel örnekler sağlar.

#### 4.2 Sözleşmesel önlemler

- İthalatçının erişim taleplerine itiraz etme taahhüdü.
- Madde 15 minimumunun ötesinde bildirim yükümlülükleri.
- Denetim hakları.
- Şeffaflık raporu taahhütleri.
- İleri transfer yasakları.
- Veri iadesiyle sonlandırma / askıya alma hakları.
- Tazminatlar.

#### 4.3 Organizasyonel önlemler

- Sıkı erişim kontrolü (gerekli-olarak-bilinmesi, görevlerin ayrılması).
- Gözetim işleme konusunda eğitim ve farkındalık.
- Hükümet taleplerini ele almak için resmi prosedür.
- Tasarımdan gizlilik geliştirmeleri.
- Tedarikçi yönetimi gözetimi.
- Periyodik denetim.

#### 4.4 Etkinlik

Bir önlem yalnızca artık riski gerçekten nötralize ederse etkilidir. Örneğin, ithalatçı tarafından tutulan anahtarlarla şifreleme, ithalatçıyı anahtarları teslim etmeye zorlayabilen bir rejime karşı **etkili değildir**.

### Adım 5 — Prosedür adımlarını at

Kabul edilen korumaya bağlı olarak:
- **SCC'ler**: Ek II'nin (TOM'lar) tamamlayıcı önlemleri yansıttığını onayla; Madde 14 garantileriyle imzala.
- **BCR**: BCR programının tamamlayıcı önlemleri yakaladığından emin ol.
- **Md. 46(3) kapsamında yetkilendirme**: SA yetkilendirmesi gerekli.
- **Tamamlayıcı önlemlerle bile değerlendirme olumlu sonuçlanamadığında**: transfer yapmayın.

### Adım 6 — Uygun aralıklarla yeniden değerlendir

Sürekli görev:

- Minimum yıllık TIA incelemesi.
- Şunlarda olay güdümlü inceleme:
  - Yeni gözetim yasaları veya değişiklikler.
  - Yeni ABAD kararları.
  - Yeni EDPB açıklamaları.
  - Madde 15 kapsamında alınan hükümet erişim talepleri.
  - İthalatçı operasyonlarında veya konumda maddi değişiklik.
  - Veri akışlarında maddi değişiklik.
  - Güvenlik olayları.

## 3. TIA belgelemesi

### 3.1 Zorunlu belgeleme

| Bölüm | İçerik |
|---|---|
| 1. Tanımlama | Transfer kimliği, tarih, taraflar, RoPA referansı. |
| 2. Transfer açıklaması | Kategoriler, hacim, amaç, sıklık, alt-işleyenler. |
| 3. Transfer aracı | SCC modülü / BCR / diğer; imzalı kopyalar referans verilmiş. |
| 4. Ülke değerlendirmesi | Yasalar ve uygulama; EEG analizi; ithalatçı tarafından sağlanan veri. |
| 5. Risk analizi | Neyin yanlış gidebileceği; olasılık; ciddiyet. |
| 6. Tamamlayıcı önlemler | Teknik, sözleşmesel, organizasyonel. Etkinlik gerekçesi. |
| 7. Sonuç | Eşdeğerlik elde edildi / edilmedi; transfer izinli / değil. |
| 8. Onaylar | Veri sahibi, DPO, Hukuk onayı. |
| 9. İnceleme programı | Sonraki inceleme tarihi; tetikleyici olaylar. |

### 3.2 Kayıt saklama

TIA hesap verebilirlik kanıtının (Md. 5(2)) bir parçasıdır. Transfer sona erdikten sonra 6 yıl sakla (veya gerekirse daha uzun).

## 4. Değerlendirme şablonu

```yaml
tia_id: TIA-YYYY-NNNN
date_initial: YYYY-MM-DD
date_review: YYYY-MM-DD
ropa_ref: RoPA-NNNN
exporter:
  name: ...
  role: kontrolör / işleyen
  establishment: AB üye devleti
importer:
  name: ...
  role: kontrolör / işleyen / alt-işleyen
  country: ...
  establishment: ...
transfer:
  data_subjects: [çalışanlar, müşteriler, ...]
  data_categories: [iletişim, ödeme, ...]
  special_categories: [evet/hayır, hangi]
  children: [evet/hayır]
  volume: tahmin
  frequency: devam eden / periyodik / tek seferlik
  purpose: ...
  storage_period: ...
  sub_processors: [...]
  onward_transfers: [...]
mechanism:
  type: SCC-2021/914 / BCR / Md-49 / Md-45
  details: modül 2 (C2P); imzalı YYYY-MM-DD
country_assessment:
  surveillance_laws: [...]
  EEG_1_assessment: ...
  EEG_2_assessment: ...
  EEG_3_assessment: ...
  EEG_4_assessment: ...
  importer_inputs: [şeffaflık raporu, beyan, ...]
  risk_level: düşük / orta / yüksek
supplementary_measures:
  technical: [...]
  contractual: [...]
  organisational: [...]
  effectiveness_justification: ...
conclusion:
  equivalence_achieved: evet / önlemlerle-evet / hayır
  decision: ilerle / askıya al / transfer-yapma
approvals:
  data_owner: ...
  DPO: ...
  legal: ...
review:
  next_due: YYYY-MM-DD
  triggers: [yeni yasa, yeni içtihat, yeni önlemler, olay]
```

## 5. Pratik örnekler

### 5.1 AB kontrolörü → ABD SaaS (DPF olmayan)

- Mekanizma: SCC Modül 2 (C2P).
- Ülke değerlendirmesi: FISA 702, EO 12333, EO 14086 kısmi hafifletme; ithalatçı "elektronik iletişim hizmet sağlayıcısı".
- Risk: açıkta yüksek; hafifletmelerle orta.
- Tamamlayıcı önlemler:
  - Kontrolör tarafından yönetilen anahtarlarla (CMEK / BYOK) depoda ve aktarımda şifreleme.
  - Mümkün olduğunda hassas alanlar için uçtan uca şifreleme.
  - Birincil depoda takma adlandırma; eşleme AB tarafında saklı.
  - Erişim taleplerine itiraz + şeffaflık raporu için ithalatçı taahhüdü.
  - Mümkün olduğunda ABD-yargı yetkisi olmayanlara alt-işleyen kısıtlamaları.
- Sonuç: belgelenmiş önlemlerle ilerle; 12 ayda incele.

### 5.2 AB kontrolörü → ABD SaaS (DPF-sertifikalı)

- Mekanizma: Md. 45 (DPF).
- Ülke değerlendirmesi: Komisyon kararıyla kapsanmıştır; minimum daha fazla analiz.
- Risk: Komisyon tarafından değerlendirildiği gibi; değişiklikler için izle (Schrems III riski).
- Tamamlayıcı önlemler: isteğe bağlı / müşteri güdümlü.
- Sonuç: ilerle; alıcı sertifikasyonunun güncel olduğunu doğrula; DPF durumunu izle.

### 5.3 AB kontrolörü → Hindistan offshore destek işleyeni

- Mekanizma: SCC Modül 2 (C2P).
- Ülke değerlendirmesi: DPDPA (2023) + IT Yasası + telekom; gözetim boşlukları; yüksek erişim riski.
- Tamamlayıcı önlemler:
  - Takma adlandırma; eşleme AB tarafında saklı.
  - VPN/VDI yoluyla kısıtlı personel erişimi; veri yerel olarak saklanmaz.
  - Güçlü sözleşmesel kısıtlamalar; zorunlu eğitim.
  - Denetim hakları.
  - Bildirim taahhütleri.
- Sonuç: önlemlerle ilerle; 12 ayda veya DPDPA kuralları kesinleştiğinde incele.

### 5.4 AB kontrolörü → Çin barındırma

- Mekanizma: SCC Modül 2 + tamamlayıcı.
- Ülke değerlendirmesi: Siber Güvenlik Yasası, Veri Güvenliği Yasası, PIPL, hükümet erişim rejimi; yüksek risk.
- Tamamlayıcı önlemler: zorla açıklamaya karşı sınırlı fayda.
- Sonuç: birçok durumda, **transfer yapmayın**, eğer (a) veri ithalatçının şifre çözemeyeceği şekilde şifrelenmediyse ve (b) işleme yalnızca yereldeyse Çin'de şifresi çözülmüş erişim olmaksızın; o zaman bile, dikkatli vaka bazında.

## 6. Tamamlayıcı önlemlerin sınırlamaları

EDPB her gözetim senaryosunun tamamlayıcı önlemlerle nötralize edilemeyeceğini kabul eder. Örneğin, hizmeti gerçekleştirmek için verinin ithalatçıda açık olması gerekiyorsa, yalnızca şifreleme zorla açıklama rejimlerine karşı yetersizdir. Bu gibi durumlarda, transfer askıya alınmalı veya yeniden yapılandırılmalıdır (örn. işlemeyi yeterli bir ülkeye taşıma).

## 7. Yaygın tuzaklar

| Tuzak | Hafifletme |
|---|---|
| TIA genel, ülkeye özel değil | Güncel kaynaklarla ülke bazında EEG analizi |
| Uygulamayı yok sayma (yalnızca yasa) | İthalatçı şeffaflık raporlarını, sivil toplum analizlerini dahil et |
| Tamamlayıcı önlem etkinliği değerlendirmesi yok | Her önlemin artık riski neden ele aldığını belgele |
| TIA bir kez yapıldı, hiç gözden geçirilmedi | Yıllık + olay güdümlü |
| TIA DPO ve Hukuk tarafından imzalanmadı | Tam onay zinciri |
| TIA RoPA'ya bağlı değil | İki yönlü çapraz başvuru |
| Alt-işleyen akışını işleyen akışı ile aynı sayma | Her ayak için ayrı analiz |
| İleri transferleri gözden kaçırma | Tam veri yolunu yürü |
