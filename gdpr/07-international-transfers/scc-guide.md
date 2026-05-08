---
title:
  en: "Standard Contractual Clauses (SCC) Guide"
  tr: "Standart Sözleşme Şartları (SCC) Rehberi"
section: "07-international-transfers"
document_type: "implementation_guide"
regulation: "GDPR (EU 2016/679)"
articles:
  - "Art. 46(2)(c) — SCCs"
  - "Art. 28 — Processor obligations"
key_instruments:
  - "EU Commission Implementing Decision 2021/914 (4 June 2021) — new SCCs"
  - "EU Commission Implementing Decision 2021/915 (4 June 2021) — Art. 28 SCCs (intra-EEA)"
key_caselaw:
  - "C-311/18 Schrems II — SCCs valid; supplementary measures required"
key_guidance:
  - "EDPB Recommendations 01/2020 (supplementary measures)"
  - "EDPB Q&A on the new SCCs (May 2022)"
language: "en, tr"
last_reviewed: "2025-05-01"
review_cycle: "annual"
owner: "Data Protection Officer"
co_owner: "Legal"
status: "approved"
classification: "internal"
---

## English

# Standard Contractual Clauses (SCC) Guide

This Guide implements the Commission Implementing Decision (EU) 2021/914 of 4 June 2021 — the new Standard Contractual Clauses for the transfer of personal data to third countries. The pre-2021 SCCs (Decisions 2001/497/EC and 2010/87/EU) have been **invalid since 27 December 2022**; legacy contracts have been migrated.

## 1. Structure of the 2021/914 SCCs

The Decision contains a single set of clauses with a **modular** structure. Parties select the module appropriate to their relationship.

### 1.1 The four modules

| Module | Roles | Typical scenario |
|---|---|---|
| **Module 1 (C2C)** | Controller (exporter) → Controller (importer) | Two independent controllers exchanging data; e.g., joint marketing campaign with a non-EU partner. |
| **Module 2 (C2P)** | Controller (exporter) → Processor (importer) | EU controller engaging a non-EU processor; e.g., SaaS, cloud hosting. |
| **Module 3 (P2P)** | Processor (exporter) → Processor (importer) | EU processor engaging a non-EU sub-processor on behalf of the controller. |
| **Module 4 (P2C)** | Processor (exporter) → Controller (importer) | Non-EU client controller receives data from its EU processor (rare, e.g., reverse-flow). |

### 1.2 Common clauses (apply across modules)

- **Clause 1 — Purpose and scope.** Defines the SCC mechanism.
- **Clause 2 — Effect and invariability.** Modifications other than approved options invalidate Article 46 reliance.
- **Clause 3 — Third-party beneficiary rights.** Data subjects may directly invoke many provisions.
- **Clause 4 — Interpretation.** GDPR governs.
- **Clause 5 — Hierarchy.** SCCs prevail over conflicting terms.
- **Clause 6 — Description of transfer (Annex I.B).**
- **Clause 7 — Docking clause (optional).** Allows new parties to join.

### 1.3 Module-specific obligations (key clauses)

- **Clause 8 — Data protection safeguards.** Includes purpose limitation, transparency, accuracy, storage limitation, security, special-category data restrictions, onward transfers, processing under instructions, etc.
- **Clause 9 — Use of sub-processors (Modules 2, 3).** General authorisation or specific authorisation; transparency to controller; cascade of equivalent obligations.
- **Clause 10 — Data subject rights.** Importer assists in fulfilment.
- **Clause 11 — Redress.** Independent dispute resolution / DPA / court.
- **Clause 12 — Liability.** Joint and several to data subjects.
- **Clause 13 — Supervision.** Identifying competent supervisory authority.
- **Clause 14 — Local laws and practices affecting compliance with the Clauses.** *Schrems II clause.* Requires the parties to **warrant**, after assessment, that the importer's local laws do not prevent compliance, and to document the assessment (TIA).
- **Clause 15 — Obligations of the data importer in case of access by public authorities.** Notification to exporter (where legally permitted), legal challenge, transparency reports.
- **Clause 16 — Non-compliance and termination.** Importer notifies; exporter may suspend; right of termination if breach not cured.
- **Clause 17 — Governing law.** EU member-state law that allows third-party beneficiary rights.
- **Clause 18 — Forum and jurisdiction.** Courts of the chosen member state; data subjects may bring claims in their member state of habitual residence.

### 1.4 Annexes

- **Annex I.A — List of parties.**
- **Annex I.B — Description of transfer (categories of data subjects, categories of personal data, sensitive data, frequency, nature, purpose, storage period, transfers to sub-processors).**
- **Annex I.C — Competent supervisory authority.**
- **Annex II — Technical and organisational measures (TOMs).**
- **Annex III — List of sub-processors (where applicable).**

## 2. The docking clause (Clause 7)

The docking clause allows additional parties to accede to the SCCs after signature. Operationally:

- Useful for multinational groups where new entities may onboard later.
- Each new party signs an accession agreement referencing the SCCs.
- The docking clause does not weaken the per-transfer assessment.

## 3. Choosing the right module

### 3.1 Decision matrix

```
Are you the:
├── Controller exporting to:
│   ├── Independent controller (no instructions) → Module 1 (C2C)
│   └── Processor (acts on instructions) → Module 2 (C2P)
└── Processor exporting to:
    ├── Sub-processor → Module 3 (P2P)
    └── Client controller (returning data) → Module 4 (P2C)
```

### 3.2 Multi-role transfers

A single relationship may involve multiple data flows requiring different modules. The contract may use multiple modules with corresponding annexes.

### 3.3 Joint controllers

If parties are joint controllers (Art. 26), the SCCs do not displace the joint-controller arrangement; both must coexist.

## 4. Implementation workflow

### 4.1 Assessment

1. **Identify the transfer.** Parties, country, data, frequency, purpose.
2. **Confirm Chapter V mechanism choice.** SCC selected over BCR / DPF / derogation.
3. **Choose the module.** Per the matrix.
4. **Run the TIA.** See `transfer-impact-assessment.md`.
5. **Identify supplementary measures.** Encryption, pseudonymisation, contractual, organisational.

### 4.2 Drafting

1. **Use the official text.** Do not rewrite Clauses 1–18; deletions or modifications kill Art. 46 reliance.
2. **Complete the annexes.**
   - Annex I.A — full legal names, contact, role, signing person.
   - Annex I.B — categories of data subjects, data, special-category, frequency, nature, purpose, storage, sub-processors.
   - Annex I.C — competent SA (the SA of the EU exporter's establishment).
   - Annex II — TOMs (encryption, access control, network segmentation, monitoring, IR, BC/DR, sub-processor controls).
   - Annex III — list of sub-processors with contacts.
3. **Choose options where offered.**
   - Specific or general authorisation for sub-processors (Clause 9 — Module 2/3).
   - Governing law (Clause 17 — choose an EU member-state law).
   - Forum (Clause 18).
   - Independent redress mechanism (Clause 11) optional addition.
4. **Document supplementary measures.** Either in Annex II (TOMs) or in a side document referenced from the TIA.

### 4.3 Signing

1. **Authorised signatories** for both parties.
2. **Original or qualified electronic signature.**
3. **Date** of signing on each party.
4. **Storage** in contract repository with metadata (parties, module, effective date, transfer purpose).

### 4.4 Operationalisation

1. **Update Article 28 DPA** to reference the SCC where appropriate.
2. **Onboard the recipient** in the vendor management system with TIA reference.
3. **Update RoPA** with mechanism and TIA reference.
4. **Set monitoring** for material change in destination law / practice.

### 4.5 Annual review

- Re-confirm TIA validity.
- Verify sub-processor list still accurate.
- Verify TOMs in Annex II still implemented.
- Review any government access requests received under Clause 15.
- Sign-off by DPO.

## 5. Sub-processors (Clause 9)

### 5.1 Specific authorisation

The processor lists each sub-processor in Annex III; controller authorises individually. Changes require fresh authorisation.

Pros: maximum control. Cons: operational burden for fast-moving SaaS environments.

### 5.2 General authorisation

The processor maintains a public list of sub-processors and notifies the controller of changes with sufficient advance notice (at least the period stipulated, typically 14–30 days). Controller may object; if no resolution, transfer suspends.

Pros: operational flexibility. Cons: requires robust monitoring by controller.

### 5.3 Cascade obligations

The sub-processor must be subject to **the same data protection obligations** as the processor (Clause 9, mirror of Art. 28(4) GDPR). Practically:

- Processor signs SCC P2P with the sub-processor (where the sub-processor is in a third country).
- Or BCR / adequacy where applicable.
- Plus a sub-processor agreement under Article 28.

## 6. Schrems II compliance: Clause 14 in practice

### 6.1 The warranty

Clause 14(a): the parties **warrant** that they have no reason to believe that the laws and practices in the third country applicable to the importer prevent the importer from fulfilling its obligations under the SCCs. They take into account, *inter alia*, the relevant aspects of the legal system.

### 6.2 The TIA

The TIA documents this assessment. EDPB Recommendations 01/2020 set six steps. The TIA is referenced from Clause 14(b) ("documentation").

### 6.3 Supplementary measures

Where Clause 14 cannot be honoured without supplementary measures:
- **Technical**: end-to-end encryption with controller-held keys; pseudonymisation; split processing; encrypted-in-use techniques; trusted hardware.
- **Contractual**: warranties on access by public authorities; legal-challenge commitment; transparency reports; immediate notification.
- **Organisational**: minimisation; access policies; review of legal regime; training.

These are documented in Annex II or a referenced supplementary-measures document.

### 6.4 Ongoing duty

If the parties become aware of changes that undermine compliance, they must reassess. Triggers include:
- New surveillance laws.
- New CJEU rulings.
- New EDPB statements.
- Government access requests received.
- Material change in importer's operations.

## 7. Government access (Clause 15)

The importer must:

1. **Promptly notify** the exporter and (where possible) the data subject of any legally binding request from a public authority. If notification is prohibited, **use best efforts** to obtain a waiver.
2. **Challenge** the request if there are reasonable grounds (e.g., conflict with international law, with EU charter rights). Document the challenge.
3. **Provide minimum amount** of data permissible.
4. **Publish transparency reports** where lawful (annual aggregated statistics).

These obligations are not always achievable under local law (e.g., FISA gag orders). The TIA must address.

## 8. Liability and redress

### 8.1 Liability among parties (Clause 12)

Parties are liable for damage caused by breach of the SCCs. Modules vary in detail.

### 8.2 Liability to data subjects (Clause 12(b))

Joint and several to data subjects for material and non-material damage. Importer's domicile is irrelevant — data subjects may sue under EU mechanisms.

### 8.3 Independent redress (optional)

Parties may add an independent dispute resolution body. Increasingly used to demonstrate Art. 46 effectiveness.

## 9. Termination (Clause 16)

Triggers:
- Importer breach not cured within reasonable time.
- Exporter unable to comply (e.g., importer's law changes).
- Final unappealable decision of supervisory authority or court.

On termination:
- Importer returns or deletes personal data (controller's choice).
- Confirms in writing.
- Onward processors take same action.

## 10. Common errors

| Error | Why it fails | Correction |
|---|---|---|
| Modifying Clauses 1–18 | Voids Art. 46 reliance | Use options; supplement via Annex II / side document |
| Missing TOMs in Annex II | Insufficient evidence | Detail technical and organisational measures |
| No TIA or TIA too generic | Schrems II non-compliance | Country-specific TIA per `transfer-impact-assessment.md` |
| Sub-processor list outdated | Clause 9 breach | Establish notification & approval workflow |
| Signing only one module when multi-flow exists | Coverage gap | Use multi-module signing or multiple SCCs |
| Choosing non-EU governing law | Cannot work | Choose EU member-state law that supports third-party beneficiary rights |
| Treating SCCs as set-and-forget | Clause 14 ongoing duty | Annual review + event-driven re-review |
| Old SCCs still in effect | Invalid since 27 Dec 2022 | Migrate to 2021/914 |

## 11. SCC vs DPF (US) practical mapping

| Recipient profile | Recommended mechanism |
|---|---|
| US recipient, DPF-certified, processing in US | DPF (Art. 45 adequacy) |
| US recipient, NOT DPF-certified | SCC (Module 2/3) + TIA + supplementary measures |
| US recipient, DPF-certified BUT processes via non-DPF affiliate | SCC + TIA for the affiliate flow |
| Non-US third-country recipient | SCC (relevant module) + TIA |

## 12. Internal contract integration

The organisation's standard Article 28 DPA template should:

- Reference the SCCs by Decision number.
- Include the SCCs as a Schedule (or cross-reference an executed copy).
- Specify the module(s) selected.
- Reference Annex II (TOMs) consistent with internal security baseline.
- Reference Annex III (sub-processors).
- Coexist with sector-specific addenda (e.g., HIPAA-style BAA where US healthcare data is involved).

## 13. Migration checklist (legacy → 2021/914)

For any contract still on pre-2021 SCCs (which should not exist post-Dec 2022; included for completeness):

- [ ] Identify all impacted contracts.
- [ ] Determine module(s) needed.
- [ ] Run / refresh TIA.
- [ ] Draft new SCCs with annexes.
- [ ] Re-sign.
- [ ] Update RoPA.
- [ ] Archive old version.

---

## Türkçe

# Standart Sözleşme Şartları (SCC) Rehberi

Bu Rehber, 4 Haziran 2021 tarihli Komisyon Uygulama Kararı (AB) 2021/914'ü — kişisel verilerin üçüncü ülkelere transferi için yeni Standart Sözleşme Şartlarını uygular. 2021 öncesi SCC'ler (2001/497/EC ve 2010/87/EU Kararları) **27 Aralık 2022'den beri geçersizdir**; eski sözleşmeler taşındı.

## 1. 2021/914 SCC'lerinin yapısı

Karar, **modüler** bir yapıya sahip tek bir madde seti içerir. Taraflar ilişkilerine uygun modülü seçer.

### 1.1 Dört modül

| Modül | Roller | Tipik senaryo |
|---|---|---|
| **Modül 1 (C2C)** | Kontrolör (ihracatçı) → Kontrolör (ithalatçı) | İki bağımsız kontrolör veri değişimi; örn. AB dışı bir ortakla ortak pazarlama kampanyası. |
| **Modül 2 (C2P)** | Kontrolör (ihracatçı) → İşleyen (ithalatçı) | AB kontrolörü bir AB dışı işleyeni görevlendirir; örn. SaaS, bulut barındırma. |
| **Modül 3 (P2P)** | İşleyen (ihracatçı) → İşleyen (ithalatçı) | AB işleyeni kontrolör adına AB dışı bir alt-işleyen görevlendirir. |
| **Modül 4 (P2C)** | İşleyen (ihracatçı) → Kontrolör (ithalatçı) | AB dışı müşteri kontrolörü AB işleyeninden veri alır (nadir, örn. ters akış). |

### 1.2 Ortak maddeler (modüller arasında uygulanır)

- **Madde 1 — Amaç ve kapsam.** SCC mekanizmasını tanımlar.
- **Madde 2 — Etki ve değiştirilemezlik.** Onaylı seçenekler dışındaki değişiklikler Madde 46 dayanağını geçersiz kılar.
- **Madde 3 — Üçüncü taraf yararlanıcı hakları.** İlgili kişiler birçok hükmü doğrudan başvurabilir.
- **Madde 4 — Yorumlama.** GDPR yönetir.
- **Madde 5 — Hiyerarşi.** SCC'ler çatışan terimlerden üstündür.
- **Madde 6 — Transfer açıklaması (Ek I.B).**
- **Madde 7 — Bağlanma maddesi (isteğe bağlı).** Yeni tarafların katılmasına izin verir.

### 1.3 Modüle özel yükümlülükler (anahtar maddeler)

- **Madde 8 — Veri koruma korumaları.** Amaç sınırlaması, şeffaflık, doğruluk, saklama sınırlaması, güvenlik, özel kategori veri kısıtlamaları, ileri transferler, talimatlar altında işleme vb. dahildir.
- **Madde 9 — Alt-işleyenlerin kullanımı (Modül 2, 3).** Genel yetkilendirme veya özel yetkilendirme; kontrolöre şeffaflık; eşdeğer yükümlülüklerin kademeli aşağı akışı.
- **Madde 10 — İlgili kişi hakları.** İthalatçı yerine getirmede yardım eder.
- **Madde 11 — Başvuru.** Bağımsız anlaşmazlık çözümü / DPA / mahkeme.
- **Madde 12 — Sorumluluk.** İlgili kişilere müteselsil ve müşterek.
- **Madde 13 — Denetim.** Yetkili denetim makamını tanımlama.
- **Madde 14 — Maddelere uyumu etkileyen yerel yasalar ve uygulamalar.** *Schrems II maddesi.* Tarafların değerlendirme sonrasında, ithalatçının yerel yasalarının uyumu engellemediğini **garanti etmesini** ve değerlendirmeyi (TIA) belgelemesini gerektirir.
- **Madde 15 — Kamu otoritelerince erişim durumunda veri ithalatçısının yükümlülükleri.** İhracatçıya bildirim (yasal olarak izinli olduğunda), yasal itiraz, şeffaflık raporları.
- **Madde 16 — Uyumsuzluk ve sonlandırma.** İthalatçı bildirir; ihracatçı askıya alabilir; ihlal düzelmezse sonlandırma hakkı.
- **Madde 17 — Yönetim hukuku.** Üçüncü taraf yararlanıcı haklarına izin veren AB üye devlet hukuku.
- **Madde 18 — Forum ve yargı yetkisi.** Seçilen üye devletin mahkemeleri; ilgili kişiler mutad ikametgâhının üye devletinde dava açabilir.

### 1.4 Ekler

- **Ek I.A — Tarafların listesi.**
- **Ek I.B — Transfer açıklaması (ilgili kişi kategorileri, kişisel veri kategorileri, hassas veri, sıklık, doğa, amaç, saklama süresi, alt-işleyenlere transferler).**
- **Ek I.C — Yetkili denetim makamı.**
- **Ek II — Teknik ve organizasyonel önlemler (TOM'lar).**
- **Ek III — Alt-işleyenlerin listesi (geçerli olduğunda).**

## 2. Bağlanma maddesi (Madde 7)

Bağlanma maddesi imza sonrası ek tarafların SCC'lere katılmasına izin verir. Operasyonel olarak:

- Daha sonra yeni varlıklar onboarding olabilen çok uluslu gruplar için yararlıdır.
- Her yeni taraf SCC'lere atıfta bulunan bir katılım anlaşması imzalar.
- Bağlanma maddesi transfer başına değerlendirmeyi zayıflatmaz.

## 3. Doğru modülü seçme

### 3.1 Karar matrisi

```
Sen:
├── Şuna ihraç eden kontrolör:
│   ├── Bağımsız kontrolör (talimat yok) → Modül 1 (C2C)
│   └── İşleyen (talimatlara göre hareket eder) → Modül 2 (C2P)
└── Şuna ihraç eden işleyen:
    ├── Alt-işleyen → Modül 3 (P2P)
    └── Müşteri kontrolörü (veriyi geri döndürür) → Modül 4 (P2C)
```

### 3.2 Çok rollü transferler

Tek bir ilişki, farklı modüller gerektiren birden fazla veri akışını içerebilir. Sözleşme, karşılık gelen eklerle birden fazla modül kullanabilir.

### 3.3 Ortak kontrolörler

Taraflar ortak kontrolörse (Md. 26), SCC'ler ortak kontrolör düzenlemesinin yerini almaz; her ikisi de bir arada bulunmalıdır.

## 4. Uygulama iş akışı

### 4.1 Değerlendirme

1. **Transferi tanımla.** Taraflar, ülke, veri, sıklık, amaç.
2. **V. Bölüm mekanizma seçimini onayla.** BCR / DPF / istisna yerine SCC seçildi.
3. **Modülü seç.** Matris başına.
4. **TIA çalıştır.** Bkz. `transfer-impact-assessment.md`.
5. **Tamamlayıcı önlemleri belirle.** Şifreleme, takma adlandırma, sözleşmesel, organizasyonel.

### 4.2 Hazırlama

1. **Resmi metni kullanın.** 1–18 maddelerini yeniden yazmayın; silmeler veya değişiklikler Md. 46 dayanağını öldürür.
2. **Ekleri tamamlayın.**
   - Ek I.A — tam yasal isimler, iletişim, rol, imzalayan kişi.
   - Ek I.B — ilgili kişi kategorileri, veri, özel kategori, sıklık, doğa, amaç, saklama, alt-işleyenler.
   - Ek I.C — yetkili SA (AB ihracatçısının kuruluşunun SA'sı).
   - Ek II — TOM'lar (şifreleme, erişim kontrolü, ağ segmentasyonu, izleme, IR, BC/DR, alt-işleyen kontrolleri).
   - Ek III — iletişim bilgileriyle alt-işleyenlerin listesi.
3. **Sunulan seçenekleri seçin.**
   - Alt-işleyenler için belirli veya genel yetkilendirme (Madde 9 — Modül 2/3).
   - Yönetim hukuku (Madde 17 — bir AB üye devlet hukuku seçin).
   - Forum (Madde 18).
   - Bağımsız başvuru mekanizması (Madde 11) isteğe bağlı ekleme.
4. **Tamamlayıcı önlemleri belgele.** Ek II'de (TOM'lar) veya TIA'dan referans verilen yan belgede.

### 4.3 İmzalama

1. Her iki taraf için **yetkili imzacılar**.
2. **Orijinal veya nitelikli elektronik imza.**
3. Her tarafta imzalama **tarihi**.
4. Metaverile birlikte sözleşme deposunda **depolama** (taraflar, modül, yürürlük tarihi, transfer amacı).

### 4.4 Operasyonel hale getirme

1. Uygun olduğunda SCC'ye atıfta bulunmak için **Madde 28 DPA'yı güncelle**.
2. TIA referansıyla tedarikçi yönetim sisteminde **alıcıyı onboarding yap**.
3. Mekanizma ve TIA referansıyla **RoPA'yı güncelle**.
4. Hedef hukuk / uygulamadaki maddi değişiklik için **izleme ayarla**.

### 4.5 Yıllık inceleme

- TIA geçerliliğini yeniden onayla.
- Alt-işleyen listesinin hâlâ doğru olduğunu doğrula.
- Ek II'deki TOM'ların hâlâ uygulandığını doğrula.
- Madde 15 kapsamında alınan herhangi bir hükümet erişim talebini incele.
- DPO onayı.

## 5. Alt-işleyenler (Madde 9)

### 5.1 Belirli yetkilendirme

İşleyen her alt-işleyeni Ek III'te listeler; kontrolör ayrı ayrı yetkilendirir. Değişiklikler yeni yetkilendirme gerektirir.

Artıları: maksimum kontrol. Eksileri: hızlı hareket eden SaaS ortamları için operasyonel yük.

### 5.2 Genel yetkilendirme

İşleyen alt-işleyenlerin kamuya açık listesini tutar ve değişiklikleri yeterli ön bildirimle (en az şart koşulan süre, tipik 14–30 gün) kontrolöre bildirir. Kontrolör itiraz edebilir; çözüm yoksa transfer askıya alınır.

Artıları: operasyonel esneklik. Eksileri: kontrolör tarafından sağlam izleme gerektirir.

### 5.3 Kademeli yükümlülükler

Alt-işleyen, işleyenle **aynı veri koruma yükümlülüklerine** tabi olmalıdır (Madde 9, GDPR Md. 28(4) aynası). Pratik olarak:

- İşleyen alt-işleyenle SCC P2P imzalar (alt-işleyen üçüncü ülkedeyse).
- Veya geçerli olduğunda BCR / yeterlilik.
- Artı Madde 28 kapsamında bir alt-işleyen anlaşması.

## 6. Schrems II uyumu: Madde 14 pratikte

### 6.1 Garanti

Madde 14(a): taraflar, ithalatçıya uygulanan üçüncü ülkedeki yasaların ve uygulamaların ithalatçının SCC'ler kapsamındaki yükümlülüklerini yerine getirmesini engellediğine inanmak için sebepleri olmadığını **garanti eder**. *Inter alia*, hukuk sisteminin ilgili yönlerini dikkate alırlar.

### 6.2 TIA

TIA bu değerlendirmeyi belgeler. EDPB Tavsiyeleri 01/2020 altı adım belirler. TIA Madde 14(b)'den ("belgeleme") referans verilir.

### 6.3 Tamamlayıcı önlemler

Madde 14, tamamlayıcı önlemler olmadan onurlandırılamadığında:
- **Teknik**: kontrolör tarafından tutulan anahtarlarla uçtan uca şifreleme; takma adlandırma; bölünmüş işleme; kullanımda şifreli teknikler; güvenilir donanım.
- **Sözleşmesel**: kamu otoritelerince erişim üzerine garantiler; yasal itiraz taahhüdü; şeffaflık raporları; anında bildirim.
- **Organizasyonel**: minimizasyon; erişim politikaları; hukuki rejim incelemesi; eğitim.

Bunlar Ek II'de veya referans verilen tamamlayıcı önlemler belgesinde belgelenir.

### 6.4 Devam eden görev

Taraflar uyumu zayıflatan değişikliklerin farkına varırsa, yeniden değerlendirmelidir. Tetikleyiciler şunları içerir:
- Yeni gözetim yasaları.
- Yeni ABAD kararları.
- Yeni EDPB açıklamaları.
- Alınan hükümet erişim talepleri.
- İthalatçının operasyonlarındaki maddi değişiklik.

## 7. Hükümet erişimi (Madde 15)

İthalatçı:

1. **Hızla bildirim** verir, ihracatçıyı ve (mümkün olduğunda) ilgili kişiyi bir kamu otoritesinden gelen yasal olarak bağlayıcı herhangi bir talep hakkında. Bildirim yasaksa, feragatname elde etmek için **en iyi çabayı** kullanır.
2. Makul gerekçeler varsa talebe **itiraz eder** (örn. uluslararası hukukla, AB şartı haklarıyla çatışma). İtirazı belgele.
3. **İzin verilen minimum miktarda** veri sağlar.
4. Yasal olduğunda **şeffaflık raporları yayınlar** (yıllık toplu istatistikler).

Bu yükümlülükler yerel hukuk altında her zaman ulaşılabilir değildir (örn. FISA gag emirleri). TIA bunu ele almalıdır.

## 8. Sorumluluk ve başvuru

### 8.1 Taraflar arası sorumluluk (Madde 12)

Taraflar SCC ihlali nedeniyle oluşan zarardan sorumludur. Modüller detayda farklılık gösterir.

### 8.2 İlgili kişilere sorumluluk (Madde 12(b))

Maddi ve maddi olmayan zarar için ilgili kişilere müteselsil ve müşterek. İthalatçının ikametgâhı önemsizdir — ilgili kişiler AB mekanizmaları altında dava açabilir.

### 8.3 Bağımsız başvuru (isteğe bağlı)

Taraflar bağımsız bir anlaşmazlık çözüm organı ekleyebilir. Md. 46 etkinliğini göstermek için giderek daha fazla kullanılıyor.

## 9. Sonlandırma (Madde 16)

Tetikleyiciler:
- Makul süre içinde düzeltilmeyen ithalatçı ihlali.
- İhracatçının uyum sağlayamaması (örn. ithalatçının hukuku değişir).
- Denetim makamının veya mahkemenin nihai itiraz edilemez kararı.

Sonlandırmada:
- İthalatçı kişisel veriyi iade eder veya siler (kontrolörün seçimi).
- Yazılı olarak onaylar.
- İleri işleyenler aynı eylemi yapar.

## 10. Yaygın hatalar

| Hata | Neden başarısız | Düzeltme |
|---|---|---|
| 1–18 maddelerini değiştirme | Md. 46 dayanağını geçersiz kılar | Seçenekleri kullan; Ek II / yan belge ile destekle |
| Ek II'de eksik TOM'lar | Yetersiz kanıt | Teknik ve organizasyonel önlemleri detaylandır |
| TIA yok veya çok genel TIA | Schrems II uyumsuzluğu | `transfer-impact-assessment.md` başına ülkeye özel TIA |
| Alt-işleyen listesi güncel değil | Madde 9 ihlali | Bildirim ve onay iş akışı oluştur |
| Çoklu akış varken yalnızca bir modülü imzalama | Kapsam boşluğu | Çoklu modül imzalama veya birden fazla SCC kullan |
| AB dışı yönetim hukuku seçme | Çalışmaz | Üçüncü taraf yararlanıcı haklarını destekleyen AB üye devlet hukuku seç |
| SCC'leri ayarla-ve-unut olarak ele alma | Madde 14 devam eden görev | Yıllık inceleme + olay güdümlü yeniden inceleme |
| Eski SCC'ler hâlâ yürürlükte | 27 Aralık 2022'den beri geçersiz | 2021/914'e geç |

## 11. SCC karşı DPF (ABD) pratik eşleme

| Alıcı profili | Önerilen mekanizma |
|---|---|
| ABD alıcısı, DPF-sertifikalı, ABD'de işleme | DPF (Md. 45 yeterlilik) |
| ABD alıcısı, DPF-sertifikalı DEĞİL | SCC (Modül 2/3) + TIA + tamamlayıcı önlemler |
| ABD alıcısı, DPF-sertifikalı ANCAK DPF olmayan iştirak yoluyla işliyor | İştirak akışı için SCC + TIA |
| ABD dışı üçüncü ülke alıcısı | SCC (ilgili modül) + TIA |

## 12. Dahili sözleşme entegrasyonu

Kuruluşun standart Madde 28 DPA şablonu:

- SCC'lere Karar numarasıyla atıfta bulunmalı.
- SCC'leri Çizelge olarak içermeli (veya yürütülmüş bir kopyaya çapraz başvuru).
- Seçilen modül(leri) belirtmeli.
- Dahili güvenlik temel çizgisiyle tutarlı Ek II'ye (TOM'lar) atıfta bulunmalı.
- Ek III'e (alt-işleyenler) atıfta bulunmalı.
- Sektöre özel eklerle bir arada bulunmalı (örn. ABD sağlık verisi söz konusu olduğunda HIPAA tarzı BAA).

## 13. Geçiş kontrol listesi (eski → 2021/914)

Hâlâ 2021 öncesi SCC'lerde olan herhangi bir sözleşme için (Aralık 2022 sonrası mevcut olmamalı; bütünlük için dahil):

- [ ] Etkilenen tüm sözleşmeleri tanımla.
- [ ] İhtiyaç duyulan modül(leri) belirle.
- [ ] TIA çalıştır / yenile.
- [ ] Eklerle yeni SCC'leri hazırla.
- [ ] Yeniden imzala.
- [ ] RoPA'yı güncelle.
- [ ] Eski sürümü arşivle.
