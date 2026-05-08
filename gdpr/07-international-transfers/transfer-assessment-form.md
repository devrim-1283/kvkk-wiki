---
title:
  en: "Transfer Assessment Form"
  tr: "Transfer Değerlendirme Formu"
section: "07-international-transfers"
document_type: "form_template"
regulation: "GDPR (EU 2016/679)"
articles:
  - "Art. 44–49 — Chapter V"
key_caselaw:
  - "C-311/18 Schrems II"
key_guidance:
  - "EDPB Recommendations 01/2020"
  - "EDPB Recommendations 02/2020"
language: "en, tr"
last_reviewed: "2025-05-01"
review_cycle: "annual"
owner: "Data Protection Officer"
status: "approved"
classification: "internal"
---

## English

# Transfer Assessment Form

This form is the per-transfer record of the assessment performed under Chapter V GDPR. It captures the parties, mechanism, country analysis (TIA summary), supplementary measures, DPO opinion, and the approval/decision. One form per transfer relationship; revise on material change or annually.

## 1. Form

### 1.1 Identification

| Field | Value |
|---|---|
| Transfer Assessment ID | `TA-YYYY-NNNN` |
| Initial assessment date | YYYY-MM-DD |
| Last review date | YYYY-MM-DD |
| Next review due | YYYY-MM-DD |
| Assessor | Name, role |
| RoPA reference | RoPA-NNNN |
| TIA reference (if separate document) | TIA-YYYY-NNNN |

### 1.2 Parties

#### Exporter

| Field | Value |
|---|---|
| Legal name | |
| Establishment | EU member state |
| Role | Controller / Processor |
| Contact (DPO or equivalent) | |

#### Importer

| Field | Value |
|---|---|
| Legal name | |
| Country | |
| Establishment | |
| Role | Controller / Processor / Sub-processor |
| Contact (DPO or equivalent) | |
| Group affiliation (if intra-group) | |
| Sub-processors used | List or reference |

### 1.3 Description of transfer

| Field | Value |
|---|---|
| Categories of data subjects | e.g., employees, customers, prospects |
| Categories of personal data | e.g., contact, payment, behavioural |
| Special-category data (Art. 9) | yes/no — if yes, list |
| Children's data | yes/no |
| Volume | estimate |
| Frequency | one-off / periodic / continuous |
| Purpose of transfer | |
| Storage period at importer | |
| Onward transfers (where) | |
| Hosting locations / regions | |

### 1.4 Lawful basis (intra-EU)

| Field | Value |
|---|---|
| Lawful basis (Art. 6) | (a) consent / (b) contract / (c) legal obligation / (d) vital interests / (e) public task / (f) legitimate interests |
| Special-category basis (Art. 9) | If applicable |

### 1.5 Chapter V mechanism

| Field | Value |
|---|---|
| Mechanism type | Art. 45 adequacy / Art. 46 SCC / Art. 46 BCR / Art. 46 code of conduct / Art. 46 certification / Art. 49 derogation |
| Specific instrument | e.g., SCC 2021/914 Module 2; BCR-C approved by Lead SA YYYY-MM-DD |
| Signed copy reference | Path to signed contract |
| Effective date | |
| Sub-processor handling | Specific / general authorisation; list reference |

### 1.6 TIA summary (if Art. 46 mechanism)

| Field | Value |
|---|---|
| Country surveillance laws considered | List with brief description |
| EEG-1 (clear, precise, accessible rules) | Met / partial / not met |
| EEG-2 (necessity, proportionality) | Met / partial / not met |
| EEG-3 (independent oversight) | Met / partial / not met |
| EEG-4 (effective remedies) | Met / partial / not met |
| Importer-provided inputs | Transparency report YYYY; declarations under Clause 15; etc. |
| Risk level after assessment | Low / Medium / High |
| Conclusion | Equivalence achieved without measures / with supplementary measures / not achievable |

### 1.7 Supplementary measures

#### Technical measures

| Measure | Implemented? | Effectiveness | Notes |
|---|---|---|---|
| Encryption at rest with controller-held keys | yes/no | high/medium/low | KMS reference |
| Encryption in transit | yes/no | | TLS version |
| End-to-end encryption (importer cannot decrypt) | yes/no | | Scope: which fields |
| Pseudonymisation, mapping retained EU | yes/no | | |
| Confidential computing / TEE | yes/no | | |
| Data minimisation | yes/no | | What was minimised |
| Storage limitation reduction | yes/no | | New retention period |

#### Contractual measures

| Measure | Implemented? | Notes |
|---|---|---|
| Importer commitment to challenge access requests | yes/no | |
| Notification beyond Clause 15 minimums | yes/no | |
| Audit rights | yes/no | Frequency |
| Transparency report commitment | yes/no | Frequency |
| Onward-transfer prohibitions | yes/no | |
| Termination / suspension rights | yes/no | |
| Indemnities | yes/no | |

#### Organisational measures

| Measure | Implemented? | Notes |
|---|---|---|
| Strict access control (need-to-know) | yes/no | |
| Training on government access | yes/no | |
| Formal procedure for handling requests | yes/no | |
| Vendor management oversight | yes/no | |
| Periodic audit | yes/no | Frequency |

### 1.8 Article 49 derogation (if applicable)

| Field | Value |
|---|---|
| Specific paragraph | (a) consent / (b) contract / (c) contract in interest / (d) public interest / (e) legal claims / (f) vital interests / (g) public register / residual |
| Necessity assessment | |
| Proportionality assessment | |
| Occasional & non-repetitive justification | |
| Notification to data subject | yes/no — date |
| Notification to SA (if residual) | yes/no — date |
| Documentation of consent (if (a)) | reference |

### 1.9 DPO opinion

| Field | Value |
|---|---|
| DPO name | |
| Date | |
| Opinion | Approve / Approve with conditions / Reject |
| Conditions / comments | |

### 1.10 Approval

| Role | Name | Decision | Date | Signature |
|---|---|---|---|---|
| Data Owner | | | | |
| Legal | | | | |
| Information Security | | | | |
| DPO | | | | |
| Executive (if material risk) | | | | |

### 1.11 Review schedule and triggers

| Trigger | Action |
|---|---|
| 12-month routine review | Reassess country, importer, measures |
| New surveillance law | Reassess Step 3 of TIA |
| New CJEU ruling | Reassess transfer tool and TIA |
| New EDPB statement | Reassess |
| Government access request received | Document and reassess |
| Material change in importer | Reassess |
| Material change in data flow | Reassess |
| Security incident at importer | Reassess |

### 1.12 Suspension / termination

If suspension is required:

- Date of suspension: ________
- Trigger: ________
- Action taken (return / delete data, notify data subject, notify SA): ________
- Approval (DPO): ________

---

## 2. Worked example A — US SaaS marketing automation tool

### 2.1 Identification

| Field | Value |
|---|---|
| Transfer Assessment ID | `TA-2025-017` |
| Initial assessment date | 2025-03-04 |
| Last review date | 2025-03-04 |
| Next review due | 2026-03-04 |
| Assessor | Anna Petrov, Senior Privacy Counsel |
| RoPA reference | RoPA-0091 (Marketing automation) |
| TIA reference | TIA-2025-017 (this form acts as the TIA cover) |

### 2.2 Parties

**Exporter**: ACME Europe GmbH (Munich, Germany), Controller, DPO contact dpo@acme.eu

**Importer**: SendBlast Inc. (Delaware, USA), Processor, DPO equivalent privacy@sendblast.com. SendBlast operates in US-East and US-West regions; sub-processors include AWS US (sub-processor for hosting), Twilio (SMS gateway, US), Datadog (monitoring, US).

### 2.3 Description of transfer

- Data subjects: ~ 240,000 marketing-opt-in subscribers in EU.
- Data: name, email, professional role, opt-in status, engagement events (open, click, conversion).
- Special-category: no.
- Children: no (audience B2B 18+).
- Volume: ~ 2 million events/month.
- Frequency: continuous.
- Purpose: deliver marketing email; track engagement; manage suppressions.
- Storage at importer: 24 months from last engagement.
- Onward: AWS hosting (sub-processor); Datadog logs (engineering / IR); no other onward.
- Hosting: US-East-1 primary, US-West-2 DR.

### 2.4 Lawful basis (intra-EU)

- Art. 6(1)(a) — consent (opt-in subscribers).

### 2.5 Chapter V mechanism

- SendBlast is **not** DPF-certified (verified at dataprivacyframework.gov on 2025-03-03).
- Mechanism: SCC 2021/914 Module 2 (C2P), signed 2024-11-12; addendum updated 2025-03-04 to reflect supplementary measures.
- Sub-processor handling: general authorisation; controller has 30 days to object.

### 2.6 TIA summary

- US surveillance: FISA 702 (importer is "ECSP"); EO 12333; CLOUD Act.
- EO 14086 introduces redress mechanism but EDPB has flagged residual concerns regarding bulk collection and necessity/proportionality.
- EEG-1: partially met (rules exist but bulk-collection scope debated).
- EEG-2: partially met (EO 14086 introduces necessity/proportionality references).
- EEG-3: improved with Data Protection Review Court (DPRC) but EDPB notes independence questions remain.
- EEG-4: redress now exists via DPRC for EU residents but practical effectiveness untested.
- Risk level after assessment: **medium** with measures.
- Conclusion: equivalence achievable **with supplementary measures**.

### 2.7 Supplementary measures

#### Technical

| Measure | Implemented? | Notes |
|---|---|---|
| Encryption at rest with CMEK | Yes | AWS KMS CMK held by ACME; SendBlast accesses via grant for envelope decryption only at processing time |
| TLS 1.3 in transit | Yes | |
| End-to-end encryption | Partial | Email body templates personalised at SendBlast (not e2e). Recipient address fields encrypted with public key during scheduling, decrypted at send time |
| Pseudonymisation | Partial | Subscriber primary key is opaque GUID; mapping in EU |
| Data minimisation | Yes | Removed unnecessary "company size", "country of origin" from sync |
| Storage reduction | Yes | Reduced from 36 months to 24 months from last engagement |

#### Contractual

| Measure | Implemented? | Notes |
|---|---|---|
| Challenge commitment | Yes | Section 11.4 of MSA addendum |
| Notification beyond Clause 15 | Yes | 24h to ACME, plus best-efforts to data subject |
| Audit rights | Yes | Annual, plus on-cause audits |
| Transparency report commitment | Yes | SendBlast publishes annual transparency report |
| Onward-transfer prohibitions | Yes | Limited to listed sub-processors; controller approval required |
| Indemnity | Yes | Up to contractual cap |

#### Organisational

| Measure | Implemented? | Notes |
|---|---|---|
| Need-to-know access | Yes | SendBlast confirmed |
| Government-access training | Yes | Annual |
| Formal request-handling procedure | Yes | Documented in vendor due diligence file |
| Vendor management oversight | Yes | Quarterly review by Procurement + DPO |
| Audit | Yes | Annual third-party audit |

### 2.8 DPO opinion

- DPO: Dr. Felix Klein.
- Date: 2025-03-04.
- Opinion: **Approve with conditions**.
- Conditions:
  - Annual TIA review.
  - SendBlast's DPF certification status to be re-checked semi-annually.
  - On any reported government access request, immediate DPO escalation and full review.
  - Move to DPF certification basis if SendBlast certifies.

### 2.9 Approval

| Role | Name | Decision | Date |
|---|---|---|---|
| Data Owner (CMO) | Lukas Becker | Approve | 2025-03-04 |
| Legal | Anna Petrov | Approve | 2025-03-04 |
| Information Security | Maria Klein | Approve | 2025-03-04 |
| DPO | Dr. Felix Klein | Approve with conditions | 2025-03-04 |

### 2.10 Review and triggers

- Routine review: 2026-03-04.
- Triggers: any new EDPB statement on US transfers; SendBlast's DPF certification change; any government access request; CJEU ruling on DPF.

---

## 3. Worked example B — India offshore customer support

### 3.1 Identification

| Field | Value |
|---|---|
| Transfer Assessment ID | `TA-2024-082` |
| Initial assessment date | 2024-09-12 |
| Last review date | 2025-04-15 |
| Next review due | 2026-04-15 |
| Assessor | Anna Petrov |
| RoPA reference | RoPA-0042 (Customer Support) |
| TIA reference | TIA-2024-082 |

### 3.2 Parties

**Exporter**: ACME Europe GmbH (Munich), Controller.

**Importer**: ACME Bangalore Services Pvt Ltd (Bangalore, India), Processor (intra-group). 600 customer-service agents handling tickets in English / German / French.

### 3.3 Description of transfer

- Data subjects: ~ 1.8 million EU customers (active relationship + 12-month dormant).
- Data: name, email, phone, account ID, ticket content (free text — may include sensitive disclosures), order history (ref only).
- Special-category: incidental in free text (e.g., user mentioning health condition); no systematic collection.
- Children: only where account-holder has provided child data lawfully (rare).
- Volume: ~ 32,000 ticket touches/day.
- Frequency: continuous.
- Purpose: customer support response, troubleshooting, account management.
- Storage at importer: tickets retained per SLA (resolved + 24 months); recordings (calls) 6 months.
- Onward: none beyond intra-group.
- Hosting: ACME-hosted ticketing system in EU; agents access via VDI (no local data download).

### 3.4 Lawful basis (intra-EU)

- Art. 6(1)(b) — performance of contract.
- For special-category content (incidental): Art. 9(2)(a) consent (incidental disclosure by data subject) or Art. 9(2)(f) legal claims / Art. 9(2)(h) where applicable.

### 3.5 Chapter V mechanism

- India is not adequacy-decided.
- Mechanism: SCC 2021/914 Module 2 (C2P) for processor relationship; intra-group agreement reflecting BCR-equivalent commitments (BCR application underway, expected approval 2026).
- Signed: 2024-09-12.

### 3.6 TIA summary

- Indian surveillance: Information Technology Act 2000 (Section 69 — interception authority); Telegraph Act; pending DPDPA 2023 rules; no comprehensive judicial pre-authorisation.
- DPDPA 2023 in force but cross-border export rules and government access provisions not fully clarified as of mid-2025.
- EEG-1: partial (rules exist but breadth of access powers concerning).
- EEG-2: partial.
- EEG-3: limited independent oversight historically.
- EEG-4: judicial review available but practical effectiveness mixed.
- Risk level after assessment: **medium-high** without measures; **medium** with measures.

### 3.7 Supplementary measures

#### Technical

| Measure | Implemented? | Notes |
|---|---|---|
| VDI-only access (no local download) | Yes | Citrix VDI; clipboard / printing disabled; screen-watermarking |
| Data residency in EU | Yes | Ticket DB in EU; agents access via VDI |
| Encryption in transit | Yes | TLS 1.3 |
| Field-level pseudonymisation in agent UI | Yes | Account IDs masked except last 4 chars; full ID shown only on need basis |
| MFA + JIT access | Yes | Time-bound role assignments |

#### Contractual

| Measure | Implemented? | Notes |
|---|---|---|
| Government-access challenge commitment | Yes | Intra-group policy |
| Notification | Yes | 12h to DPO |
| Audit rights | Yes | Continuous; quarterly formal audit |
| Indemnity / liability | Yes | Group umbrella |

#### Organisational

| Measure | Implemented? | Notes |
|---|---|---|
| Need-to-know access | Yes | Per-customer ticket access; cross-customer queries logged |
| Training | Yes | Quarterly + ad-hoc on regulatory developments |
| Formal request handling | Yes | Group privacy escalation matrix |
| Background checks for agents | Yes | Pre-employment + annual recheck |

### 3.8 DPO opinion

- DPO: Dr. Felix Klein.
- Initial opinion (2024-09-12): Approve with conditions.
- Updated opinion (2025-04-15 review): Approve, with continued conditions.
- Conditions:
  - Continue BCR application; review on approval / non-approval.
  - Monitor DPDPA 2023 rules issuance.
  - Continue quarterly audit.
  - Annual DPIA refresh given customer support is high-touch.
  - On any local Indian government access request: immediate DPO escalation.

### 3.9 Approval

| Role | Name | Decision | Date |
|---|---|---|---|
| Data Owner (Customer Ops VP) | Sandra Voigt | Approve | 2024-09-12 |
| Legal | Anna Petrov | Approve | 2024-09-12 |
| Information Security | Maria Klein | Approve | 2024-09-12 |
| DPO | Dr. Felix Klein | Approve w/conditions | 2024-09-12 |

### 3.10 Review history

- Initial: 2024-09-12.
- 2025-04-15 review: no material change; conditions maintained.
- 2026-04-15 next due.
- Pre-trigger: BCR approval expected 2026; if approved, mechanism updates to BCR.

---

## Türkçe

# Transfer Değerlendirme Formu

Bu form, GDPR V. Bölüm kapsamında gerçekleştirilen değerlendirmenin transfer başına kaydıdır. Tarafları, mekanizmayı, ülke analizini (TIA özeti), tamamlayıcı önlemleri, DPO görüşünü ve onay/kararı yakalar. Transfer ilişkisi başına bir form; maddi değişiklikte veya yıllık olarak revize edin.

## 1. Form

### 1.1 Tanımlama

| Alan | Değer |
|---|---|
| Transfer Değerlendirme Kimliği | `TA-YYYY-NNNN` |
| İlk değerlendirme tarihi | YYYY-MM-DD |
| Son inceleme tarihi | YYYY-MM-DD |
| Sonraki inceleme vadesi | YYYY-MM-DD |
| Değerlendirici | İsim, rol |
| RoPA referansı | RoPA-NNNN |
| TIA referansı (ayrı belge ise) | TIA-YYYY-NNNN |

### 1.2 Taraflar

#### İhracatçı

| Alan | Değer |
|---|---|
| Yasal isim | |
| Kuruluş | AB üye devleti |
| Rol | Kontrolör / İşleyen |
| İletişim (DPO veya eşdeğeri) | |

#### İthalatçı

| Alan | Değer |
|---|---|
| Yasal isim | |
| Ülke | |
| Kuruluş | |
| Rol | Kontrolör / İşleyen / Alt-işleyen |
| İletişim (DPO veya eşdeğeri) | |
| Grup bağlılığı (grup içi ise) | |
| Kullanılan alt-işleyenler | Liste veya referans |

### 1.3 Transfer açıklaması

| Alan | Değer |
|---|---|
| İlgili kişi kategorileri | örn. çalışanlar, müşteriler, potansiyeller |
| Kişisel veri kategorileri | örn. iletişim, ödeme, davranışsal |
| Özel kategori veri (Md. 9) | evet/hayır — evet ise listele |
| Çocuk verisi | evet/hayır |
| Hacim | tahmin |
| Sıklık | tek seferlik / periyodik / sürekli |
| Transfer amacı | |
| İthalatçıda saklama süresi | |
| İleri transferler (nereye) | |
| Barındırma konumları / bölgeleri | |

### 1.4 Hukuki dayanak (AB içi)

| Alan | Değer |
|---|---|
| Hukuki dayanak (Md. 6) | (a) rıza / (b) sözleşme / (c) hukuki yükümlülük / (d) hayati menfaatler / (e) kamu görevi / (f) meşru menfaatler |
| Özel kategori dayanak (Md. 9) | Geçerliyse |

### 1.5 V. Bölüm mekanizması

| Alan | Değer |
|---|---|
| Mekanizma türü | Md. 45 yeterlilik / Md. 46 SCC / Md. 46 BCR / Md. 46 davranış kuralları / Md. 46 sertifikasyon / Md. 49 istisna |
| Belirli enstrüman | örn. SCC 2021/914 Modül 2; Lider SA tarafından YYYY-MM-DD onaylı BCR-C |
| İmzalı kopya referansı | İmzalı sözleşme yolu |
| Yürürlük tarihi | |
| Alt-işleyen işleme | Belirli / genel yetkilendirme; liste referansı |

### 1.6 TIA özeti (Md. 46 mekanizma ise)

| Alan | Değer |
|---|---|
| Dikkate alınan ülke gözetim yasaları | Kısa açıklama ile liste |
| EEG-1 (açık, kesin, erişilebilir kurallar) | Karşılandı / kısmi / karşılanmadı |
| EEG-2 (gereklilik, orantılılık) | Karşılandı / kısmi / karşılanmadı |
| EEG-3 (bağımsız gözetim) | Karşılandı / kısmi / karşılanmadı |
| EEG-4 (etkili çareler) | Karşılandı / kısmi / karşılanmadı |
| İthalatçı tarafından sağlanan girdiler | YYYY şeffaflık raporu; Madde 15 kapsamında bildirimler vb. |
| Değerlendirme sonrası risk seviyesi | Düşük / Orta / Yüksek |
| Sonuç | Önlemler olmadan eşdeğerlik elde edildi / tamamlayıcı önlemlerle / elde edilemez |

### 1.7 Tamamlayıcı önlemler

#### Teknik önlemler

| Önlem | Uygulanmış? | Etkinlik | Notlar |
|---|---|---|---|
| Kontrolör tarafından tutulan anahtarlarla depoda şifreleme | evet/hayır | yüksek/orta/düşük | KMS referansı |
| Aktarımda şifreleme | evet/hayır | | TLS sürümü |
| Uçtan uca şifreleme (ithalatçı şifre çözemez) | evet/hayır | | Kapsam: hangi alanlar |
| Takma adlandırma, eşleme AB'de saklı | evet/hayır | | |
| Gizli hesaplama / TEE | evet/hayır | | |
| Veri minimizasyonu | evet/hayır | | Ne minimize edildi |
| Saklama sınırlaması azaltma | evet/hayır | | Yeni saklama süresi |

#### Sözleşmesel önlemler

| Önlem | Uygulanmış? | Notlar |
|---|---|---|
| Erişim taleplerine itiraz için ithalatçı taahhüdü | evet/hayır | |
| Madde 15 minimumlarının ötesinde bildirim | evet/hayır | |
| Denetim hakları | evet/hayır | Sıklık |
| Şeffaflık raporu taahhüdü | evet/hayır | Sıklık |
| İleri transfer yasakları | evet/hayır | |
| Sonlandırma / askıya alma hakları | evet/hayır | |
| Tazminatlar | evet/hayır | |

#### Organizasyonel önlemler

| Önlem | Uygulanmış? | Notlar |
|---|---|---|
| Sıkı erişim kontrolü (gerekli-olarak-bilinmesi) | evet/hayır | |
| Hükümet erişimi konusunda eğitim | evet/hayır | |
| Talepleri ele almak için resmi prosedür | evet/hayır | |
| Tedarikçi yönetimi gözetimi | evet/hayır | |
| Periyodik denetim | evet/hayır | Sıklık |

### 1.8 Madde 49 istisnası (geçerliyse)

| Alan | Değer |
|---|---|
| Belirli paragraf | (a) rıza / (b) sözleşme / (c) yararına sözleşme / (d) kamu yararı / (e) hukuki talepler / (f) hayati menfaatler / (g) kamu sicili / artık |
| Gereklilik değerlendirmesi | |
| Orantılılık değerlendirmesi | |
| Ara sıra ve tekrarlanmayan gerekçesi | |
| İlgili kişiye bildirim | evet/hayır — tarih |
| SA'ya bildirim (artık ise) | evet/hayır — tarih |
| Rızanın belgelenmesi (if (a)) | referans |

### 1.9 DPO görüşü

| Alan | Değer |
|---|---|
| DPO ismi | |
| Tarih | |
| Görüş | Onayla / Koşullarla onayla / Reddet |
| Koşullar / yorumlar | |

### 1.10 Onay

| Rol | İsim | Karar | Tarih | İmza |
|---|---|---|---|---|
| Veri Sahibi | | | | |
| Hukuk | | | | |
| Bilgi Güvenliği | | | | |
| DPO | | | | |
| Yönetici (maddi risk ise) | | | | |

### 1.11 İnceleme programı ve tetikleyicileri

| Tetikleyici | Eylem |
|---|---|
| 12 aylık rutin inceleme | Ülke, ithalatçı, önlemleri yeniden değerlendir |
| Yeni gözetim hukuku | TIA Adım 3'ü yeniden değerlendir |
| Yeni ABAD kararı | Transfer aracı ve TIA'yı yeniden değerlendir |
| Yeni EDPB açıklaması | Yeniden değerlendir |
| Hükümet erişim talebi alındı | Belgele ve yeniden değerlendir |
| İthalatçıda maddi değişiklik | Yeniden değerlendir |
| Veri akışında maddi değişiklik | Yeniden değerlendir |
| İthalatçıda güvenlik olayı | Yeniden değerlendir |

### 1.12 Askıya alma / sonlandırma

Askıya alma gerekiyorsa:

- Askıya alma tarihi: ________
- Tetikleyici: ________
- Atılan eylem (veriyi iade et / sil, ilgili kişiyi bilgilendir, SA'ya bildirim): ________
- Onay (DPO): ________

---

## 2. İşlenmiş örnek A — ABD SaaS pazarlama otomasyon aracı

### 2.1 Tanımlama

| Alan | Değer |
|---|---|
| Transfer Değerlendirme Kimliği | `TA-2025-017` |
| İlk değerlendirme tarihi | 2025-03-04 |
| Son inceleme tarihi | 2025-03-04 |
| Sonraki inceleme vadesi | 2026-03-04 |
| Değerlendirici | Anna Petrov, Kıdemli Gizlilik Müşaviri |
| RoPA referansı | RoPA-0091 (Pazarlama otomasyonu) |
| TIA referansı | TIA-2025-017 (bu form TIA kapağı işlevi görür) |

### 2.2 Taraflar

**İhracatçı**: ACME Europe GmbH (Münih, Almanya), Kontrolör, DPO iletişim dpo@acme.eu

**İthalatçı**: SendBlast Inc. (Delaware, ABD), İşleyen, DPO eşdeğeri privacy@sendblast.com. SendBlast US-East ve US-West bölgelerinde işletilir; alt-işleyenler arasında AWS US (barındırma için alt-işleyen), Twilio (SMS gateway, ABD), Datadog (izleme, ABD) bulunur.

### 2.3 Transfer açıklaması

- İlgili kişiler: AB'de ~ 240.000 pazarlama-opt-in abonesi.
- Veri: ad, e-posta, mesleki rol, opt-in durumu, etkileşim olayları (açma, tıklama, dönüşüm).
- Özel kategori: hayır.
- Çocuklar: hayır (B2B 18+ kitle).
- Hacim: ~ 2 milyon olay/ay.
- Sıklık: sürekli.
- Amaç: pazarlama e-postası teslimi; etkileşimi izleme; baskıları yönetme.
- İthalatçıda saklama: son etkileşimden 24 ay.
- İleri: AWS barındırma (alt-işleyen); Datadog logları (mühendislik / IR); başka ileri yok.
- Barındırma: US-East-1 birincil, US-West-2 DR.

### 2.4 Hukuki dayanak (AB içi)

- Md. 6(1)(a) — rıza (opt-in aboneler).

### 2.5 V. Bölüm mekanizması

- SendBlast DPF-sertifikalı **değil** (2025-03-03'te dataprivacyframework.gov'da doğrulandı).
- Mekanizma: SCC 2021/914 Modül 2 (C2P), 2024-11-12'de imzalandı; tamamlayıcı önlemleri yansıtmak için 2025-03-04'te ek güncellendi.
- Alt-işleyen işleme: genel yetkilendirme; kontrolörün itiraz için 30 günü vardır.

### 2.6 TIA özeti

- ABD gözetim: FISA 702 (ithalatçı "ECSP"); EO 12333; CLOUD Act.
- EO 14086 başvuru mekanizmasını tanıttı ancak EDPB toplu toplama ve gereklilik/orantılılık konusunda kalan endişeleri işaretledi.
- EEG-1: kısmen karşılandı (kurallar mevcut ancak toplu toplama kapsamı tartışmalı).
- EEG-2: kısmen karşılandı (EO 14086 gereklilik/orantılılık atıfları tanıtır).
- EEG-3: Veri Koruma İnceleme Mahkemesi (DPRC) ile geliştirildi ancak EDPB bağımsızlık sorularının kaldığını belirtir.
- EEG-4: AB sakinleri için DPRC aracılığıyla başvuru artık mevcut ancak pratik etkinliği test edilmedi.
- Değerlendirme sonrası risk seviyesi: önlemlerle **orta**.
- Sonuç: **tamamlayıcı önlemlerle** eşdeğerlik elde edilebilir.

### 2.7 Tamamlayıcı önlemler

#### Teknik

| Önlem | Uygulanmış? | Notlar |
|---|---|---|
| CMEK ile depoda şifreleme | Evet | ACME tarafından tutulan AWS KMS CMK; SendBlast yalnızca işleme zamanında zarf şifre çözme için hibe yoluyla erişir |
| TLS 1.3 aktarımda | Evet | |
| Uçtan uca şifreleme | Kısmi | E-posta gövde şablonları SendBlast'ta kişiselleştirilir (e2e değil). Alıcı adres alanları zamanlama sırasında genel anahtarla şifrelenir, gönderim zamanında şifresi çözülür |
| Takma adlandırma | Kısmi | Abone birincil anahtarı opak GUID; eşleme AB'de |
| Veri minimizasyonu | Evet | Senkronizasyondan gereksiz "şirket büyüklüğü", "menşe ülke" kaldırıldı |
| Saklama azaltma | Evet | Son etkileşimden 36 aydan 24 aya azaltıldı |

#### Sözleşmesel

| Önlem | Uygulanmış? | Notlar |
|---|---|---|
| İtiraz taahhüdü | Evet | MSA ek Bölüm 11.4 |
| Madde 15'in ötesinde bildirim | Evet | ACME'ye 24s, artı ilgili kişiye en iyi çaba |
| Denetim hakları | Evet | Yıllık, artı sebepli denetimler |
| Şeffaflık raporu taahhüdü | Evet | SendBlast yıllık şeffaflık raporu yayınlar |
| İleri transfer yasakları | Evet | Listelenen alt-işleyenlerle sınırlı; kontrolör onayı gerekli |
| Tazminat | Evet | Sözleşmesel tavana kadar |

#### Organizasyonel

| Önlem | Uygulanmış? | Notlar |
|---|---|---|
| Gerekli-olarak-bilinmesi erişimi | Evet | SendBlast onayladı |
| Hükümet erişimi eğitimi | Evet | Yıllık |
| Resmi talep işleme prosedürü | Evet | Tedarikçi durum tespiti dosyasında belgelenmiştir |
| Tedarikçi yönetimi gözetimi | Evet | Tedarik + DPO tarafından üç ayda bir inceleme |
| Denetim | Evet | Yıllık üçüncü taraf denetim |

### 2.8 DPO görüşü

- DPO: Dr. Felix Klein.
- Tarih: 2025-03-04.
- Görüş: **Koşullarla onayla**.
- Koşullar:
  - Yıllık TIA incelemesi.
  - SendBlast'ın DPF sertifika durumu altı ayda bir yeniden kontrol edilecek.
  - Bildirilen herhangi bir hükümet erişim talebinde, anında DPO eskalasyonu ve tam inceleme.
  - SendBlast sertifika alırsa DPF sertifikasyon dayanağına geç.

### 2.9 Onay

| Rol | İsim | Karar | Tarih |
|---|---|---|---|
| Veri Sahibi (CMO) | Lukas Becker | Onayla | 2025-03-04 |
| Hukuk | Anna Petrov | Onayla | 2025-03-04 |
| Bilgi Güvenliği | Maria Klein | Onayla | 2025-03-04 |
| DPO | Dr. Felix Klein | Koşullarla onayla | 2025-03-04 |

### 2.10 İnceleme ve tetikleyiciler

- Rutin inceleme: 2026-03-04.
- Tetikleyiciler: ABD transferleri konusunda yeni EDPB açıklaması; SendBlast'ın DPF sertifikasyonu değişikliği; herhangi bir hükümet erişim talebi; DPF konusunda ABAD kararı.

---

## 3. İşlenmiş örnek B — Hindistan offshore müşteri desteği

### 3.1 Tanımlama

| Alan | Değer |
|---|---|
| Transfer Değerlendirme Kimliği | `TA-2024-082` |
| İlk değerlendirme tarihi | 2024-09-12 |
| Son inceleme tarihi | 2025-04-15 |
| Sonraki inceleme vadesi | 2026-04-15 |
| Değerlendirici | Anna Petrov |
| RoPA referansı | RoPA-0042 (Müşteri Desteği) |
| TIA referansı | TIA-2024-082 |

### 3.2 Taraflar

**İhracatçı**: ACME Europe GmbH (Münih), Kontrolör.

**İthalatçı**: ACME Bangalore Services Pvt Ltd (Bangalore, Hindistan), İşleyen (grup içi). 600 müşteri hizmetleri ajanı İngilizce / Almanca / Fransızca'da talepleri ele alır.

### 3.3 Transfer açıklaması

- İlgili kişiler: ~ 1.8 milyon AB müşterisi (aktif ilişki + 12 aylık uyku).
- Veri: ad, e-posta, telefon, hesap kimliği, talep içeriği (serbest metin — hassas açıklamalar içerebilir), sipariş geçmişi (yalnızca referans).
- Özel kategori: serbest metinde rastlantısal (örn. sağlık durumu söyleyen kullanıcı); sistematik toplama yok.
- Çocuklar: yalnızca hesap sahibinin yasal olarak çocuk verisi sağladığı yerlerde (nadir).
- Hacim: ~ 32.000 talep teması/gün.
- Sıklık: sürekli.
- Amaç: müşteri desteği yanıtı, sorun giderme, hesap yönetimi.
- İthalatçıda saklama: SLA başına talepler tutulur (çözüldü + 24 ay); kayıtlar (çağrılar) 6 ay.
- İleri: grup içi ötesinde hiçbiri.
- Barındırma: AB'de ACME-barındırılan talep yönetim sistemi; ajanlar VDI yoluyla erişir (yerel veri indirme yok).

### 3.4 Hukuki dayanak (AB içi)

- Md. 6(1)(b) — sözleşmenin ifası.
- Özel kategori içerik için (rastlantısal): Md. 9(2)(a) rıza (ilgili kişi tarafından rastlantısal açıklama) veya geçerli olduğunda Md. 9(2)(f) hukuki talepler / Md. 9(2)(h).

### 3.5 V. Bölüm mekanizması

- Hindistan yeterlilik kararı verilmemiştir.
- Mekanizma: işleyen ilişkisi için SCC 2021/914 Modül 2 (C2P); BCR-eşdeğeri taahhütleri yansıtan grup içi anlaşma (BCR başvurusu devam ediyor, beklenen onay 2026).
- İmzalı: 2024-09-12.

### 3.6 TIA özeti

- Hindistan gözetimi: Bilgi Teknolojisi Yasası 2000 (Bölüm 69 — müdahale yetkisi); Telgraf Yasası; bekleyen DPDPA 2023 kuralları; kapsamlı yargısal ön yetkilendirme yok.
- DPDPA 2023 yürürlükte ancak sınır ötesi ihracat kuralları ve hükümet erişim hükümleri 2025 ortası itibarıyla tam olarak netleştirilmemiştir.
- EEG-1: kısmi (kurallar mevcut ancak erişim yetkilerinin genişliği endişe verici).
- EEG-2: kısmi.
- EEG-3: tarihsel olarak sınırlı bağımsız gözetim.
- EEG-4: yargı incelemesi mevcut ancak pratik etkinliği karışık.
- Değerlendirme sonrası risk seviyesi: önlemler olmadan **orta-yüksek**; önlemlerle **orta**.

### 3.7 Tamamlayıcı önlemler

#### Teknik

| Önlem | Uygulanmış? | Notlar |
|---|---|---|
| Yalnızca VDI erişim (yerel indirme yok) | Evet | Citrix VDI; pano / yazdırma devre dışı; ekran filigranı |
| AB'de veri ikametgâhı | Evet | AB'de talep DB; ajanlar VDI yoluyla erişir |
| Aktarımda şifreleme | Evet | TLS 1.3 |
| Ajan UI'da alan-seviyesi takma adlandırma | Evet | Hesap kimlikleri son 4 karakter dışında maskelenir; tam kimlik yalnızca gerekli temelinde gösterilir |
| MFA + JIT erişim | Evet | Zaman sınırlı rol atamaları |

#### Sözleşmesel

| Önlem | Uygulanmış? | Notlar |
|---|---|---|
| Hükümet-erişim itiraz taahhüdü | Evet | Grup içi politika |
| Bildirim | Evet | DPO'ya 12s |
| Denetim hakları | Evet | Sürekli; üç ayda bir resmi denetim |
| Tazminat / sorumluluk | Evet | Grup şemsiye |

#### Organizasyonel

| Önlem | Uygulanmış? | Notlar |
|---|---|---|
| Gerekli-olarak-bilinmesi erişimi | Evet | Müşteri başına talep erişimi; çapraz müşteri sorguları kaydedildi |
| Eğitim | Evet | Üç ayda bir + düzenleyici gelişmeler için ad hoc |
| Resmi talep işleme | Evet | Grup gizlilik eskalasyon matrisi |
| Ajanlar için geçmiş kontrolleri | Evet | İstihdam öncesi + yıllık yeniden kontrol |

### 3.8 DPO görüşü

- DPO: Dr. Felix Klein.
- İlk görüş (2024-09-12): Koşullarla onayla.
- Güncellenmiş görüş (2025-04-15 incelemesi): Devam eden koşullarla onayla.
- Koşullar:
  - BCR başvurusuna devam et; onay / reddetmede incele.
  - DPDPA 2023 kuralları yayımını izle.
  - Üç aylık denetime devam et.
  - Müşteri desteği yüksek temas olduğu için yıllık DPIA yenileme.
  - Yerel Hindistan hükümet erişim talebinde: anında DPO eskalasyonu.

### 3.9 Onay

| Rol | İsim | Karar | Tarih |
|---|---|---|---|
| Veri Sahibi (Müşteri Ops VP) | Sandra Voigt | Onayla | 2024-09-12 |
| Hukuk | Anna Petrov | Onayla | 2024-09-12 |
| Bilgi Güvenliği | Maria Klein | Onayla | 2024-09-12 |
| DPO | Dr. Felix Klein | Koşullarla onayla | 2024-09-12 |

### 3.10 İnceleme geçmişi

- İlk: 2024-09-12.
- 2025-04-15 incelemesi: maddi değişiklik yok; koşullar korundu.
- 2026-04-15 sonraki vade.
- Ön tetik: BCR onayı 2026'da bekleniyor; onaylanırsa, mekanizma BCR'ye güncellenir.
