---
title:
  en: "Transfer Regime — Chapter V Overview"
  tr: "Transfer Rejimi — V. Bölüm Genel Bakışı"
section: "07-international-transfers"
document_type: "reference"
regulation: "GDPR (EU 2016/679)"
articles:
  - "Art. 44 — General principle for transfers"
  - "Art. 45 — Adequacy decisions"
  - "Art. 46 — Appropriate safeguards"
  - "Art. 47 — Binding corporate rules"
  - "Art. 48 — Transfers or disclosures not authorised by Union law"
  - "Art. 49 — Derogations"
  - "Art. 50 — International cooperation"
key_caselaw:
  - "C-362/14 Schrems I (2015)"
  - "C-311/18 Schrems II (2020)"
  - "C-507/17 Google v CNIL (2019) — territorial scope of dereferencing"
key_guidance:
  - "EDPB Recommendations 01/2020 (supplementary measures)"
  - "EDPB Recommendations 02/2020 (European Essential Guarantees)"
  - "EDPB Guidelines 05/2021 (interplay Art. 3 / Chapter V)"
language: "en, tr"
last_reviewed: "2025-05-01"
review_cycle: "annual"
owner: "Data Protection Officer"
status: "approved"
classification: "internal"
note: "Adequate-country list verified mid-2025; verify against the European Commission's official register before relying."
---

## English

# Transfer Regime — Chapter V Overview

## 1. Article 44 — General principle

Any transfer of personal data which are undergoing processing or are intended for processing **after transfer to a third country or to an international organisation** shall take place only if, subject to the other GDPR provisions, the conditions in Chapter V are complied with by the controller and processor, **including for onward transfers** of personal data from the third country or an international organisation to another third country or to another international organisation.

This is the lock principle: protection travels with the data. Every onward transfer must be assessed.

## 2. What counts as a transfer?

EDPB Guidelines 05/2021 §7 set three cumulative criteria:

1. The controller / processor (the "exporter") is **subject to GDPR** for the relevant processing.
2. The exporter **discloses by transmission or otherwise makes the data available** to another controller / processor / joint controller / individual (the "importer").
3. The importer is in a **third country**, or is an international organisation (irrespective of whether the importer is itself subject to GDPR by virtue of Art. 3).

Examples that **are** transfers:
- An EU controller sends customer records to a US SaaS processor for storage.
- An EU subsidiary uploads payroll data to a parent-company HR system in India.
- An EU processor returns processed records to its non-EU client controller.

Examples that are **not** transfers:
- A non-EU controller subject to GDPR (Art. 3(2)) processing data **within the EU** (no transmission to a non-EU recipient).
- A data subject in a third country directly accessing their own account at an EU controller (the data subject is not a "recipient" in this sense).

## 3. Article 45 — Adequacy decisions

The Commission may decide, after assessment, that a third country, a territory, or one or more specified sectors within a third country, or an international organisation, ensures an **adequate level of protection**. Where adequacy applies, no further authorisation is required (Art. 45(1)) — the transfer is treated as if it were intra-EU for Chapter V purposes.

### 3.1 Adequate countries (verified mid-2025; always verify with the Commission's current list)

| Country / territory | Decision year | Notes |
|---|---|---|
| Andorra | 2010 | |
| Argentina | 2003 | |
| Canada (commercial organisations under PIPEDA) | 2001 | Commercial sector only |
| Faroe Islands | 2010 | |
| Guernsey | 2003 | |
| Isle of Man | 2004 | |
| Israel | 2011 | Under monitoring |
| Japan | 2019 | Mutual adequacy with EU; supplementary protections |
| Jersey | 2008 | |
| New Zealand | 2012 | |
| Republic of Korea (South Korea) | 2021 | |
| Switzerland | 2000 | |
| United Kingdom | 2021 | Two decisions: GDPR + Law Enforcement Directive; sunset 2025 unless renewed |
| Uruguay | 2012 | |
| United States | 2023 | **Limited**: applies only to organisations certified under the EU-US Data Privacy Framework (DPF) |

> **Verification requirement.** The DPO must check `https://commission.europa.eu/law/law-topic/data-protection/international-dimension-data-protection/adequacy-decisions_en` (or the equivalent successor page) before relying on this list. New decisions, withdrawals, or renewals can change the picture between annual reviews.

### 3.2 What an adequacy decision means operationally

- The transfer is permitted **without** SCCs, BCRs, or derogations.
- A TIA is **not** generally required (the Commission already assessed adequacy).
- Document the basis: data subject's data, recipient, decision reference, scope.
- Monitor for revocation, sunset, or modification.

### 3.3 Country-specific notes

- **United Kingdom.** The 2021 adequacy decision sunsets in mid-2025 unless renewed. The DPO must monitor the Commission renewal process. A non-renewal would force migration to SCCs.
- **United States.** The DPF (2023) replaces Privacy Shield. Adequacy applies **only to certified entities**. The DPO must verify recipient certification at `dataprivacyframework.gov` and monitor for legal challenges (Schrems III).
- **Israel.** Subject to ongoing monitoring; review of compatibility with GDPR principles is anticipated.

## 4. Article 46 — Appropriate safeguards

Where there is no adequacy decision, transfers may proceed if the controller / processor has provided **appropriate safeguards**, and on condition that **enforceable data subject rights** and **effective legal remedies** for data subjects are available.

### 4.1 Safeguards under Article 46(2) — no specific authorisation required

| Safeguard | Description |
|---|---|
| (a) Legally binding instrument between public authorities | E.g., international agreement between government bodies. |
| (b) Binding Corporate Rules (BCR) | Approved per Art. 47. See `bcr-guide.md`. |
| (c) Standard Contractual Clauses (SCC) — Commission | The 2021/914 set. See `scc-guide.md`. |
| (d) SCCs adopted by a supervisory authority and approved by Commission | Less common; applies where a DPA has its own SCC set approved. |
| (e) Approved code of conduct under Art. 40 | Must include binding and enforceable commitments to apply safeguards. |
| (f) Approved certification mechanism under Art. 42 | Same. |

### 4.2 Safeguards under Article 46(3) — supervisory authority authorisation required

| Safeguard | Description |
|---|---|
| (a) Contractual clauses between controller/processor and recipient | Bespoke clauses, requires DPA authorisation. |
| (b) Provisions inserted into administrative arrangements between public authorities | Requires DPA authorisation. |

### 4.3 Schrems II implications

Crucially, the CJEU held that signing a Chapter V instrument is **not enough**. The exporter must verify that the destination country's law and practice provide **essentially equivalent** protection. Where it does not, supplementary measures are required.

This is operationalised in the Transfer Impact Assessment (`transfer-impact-assessment.md`).

## 5. Article 47 — Binding Corporate Rules

BCRs are personal-data-protection policies adhered to by a group of undertakings or enterprises engaged in joint economic activity. They must:

- Be legally binding on members of the group.
- Apply to every member of the group.
- Confer enforceable rights on data subjects.
- Be approved by the competent supervisory authority via the consistency mechanism (Art. 63–67).

Used by multinationals to transfer **within** the corporate group across borders. See `bcr-guide.md`.

## 6. Article 48 — Foreign access to data

Article 48 has become extremely important under Schrems II. It provides:

> Any judgment of a court or tribunal and any decision of an administrative authority of a third country requiring a controller or processor to transfer or disclose personal data may only be recognised or enforceable in any manner if based on an international agreement, such as a mutual legal assistance treaty.

The implication: third-country government access requests not based on an MLA / equivalent are **not by themselves a lawful basis** to transfer or disclose. The recipient must invoke an Article 49 derogation or refuse, document the conflict, and notify the data subject where possible.

This bears especially on:
- US FISA 702 directives.
- Cloud Act subpoenas.
- Chinese national-security demands under PRC Cybersecurity Law / Data Security Law / PIPL.

## 7. Article 49 — Derogations

For specific situations, transfers may proceed in the absence of adequacy or safeguards. Derogations are **narrowly construed**, **occasional**, **non-repetitive**, and apply per-transfer. See `derogations.md`.

## 8. Article 50 — International cooperation

The Commission and supervisory authorities take steps to develop international cooperation mechanisms; this article is structural rather than operational for the controller.

## 9. Decision tree (consolidated)

```
1. Is there a transfer (per EDPB Guidelines 05/2021)?
   - No → Chapter V does not apply; verify other GDPR rules.
   - Yes → continue.

2. Is there an Article 45 adequacy decision covering this recipient?
   - Yes → transfer permitted; document basis; monitor adequacy.
   - No → continue.

3. Is there an appropriate safeguard under Article 46?
   - SCC (2021/914), BCR, code of conduct, certification, public-authority arrangement.
   - Document the instrument.
   - Continue to TIA.

4. Conduct TIA (EDPB Recommendations 01/2020).
   - Equivalent protection? → transfer with documented safeguards.
   - Not equivalent? → identify supplementary measures sufficient to bring up to equivalence.
   - Sufficient? → transfer with documented supplementary measures.
   - Insufficient? → suspend transfer.

5. (Last resort) Article 49 derogation.
   - Narrow, specific, occasional.
   - Document carefully.
```

## 10. Onward transfers

Onward transfers (recipient-to-another-third-country) inherit the protection requirement (Art. 44 last sentence). Practically:

- The Article 28 contract / SCCs flow onward-transfer constraints.
- The recipient must apply equivalent safeguards before onward transfer.
- The exporter remains accountable.

For SCCs, Clause 8.7 (in modules where applicable) requires onward-transfer commitments.

## 11. Transfers within multinationals

Common scenarios:

| Scenario | Mechanism |
|---|---|
| EU subsidiary → non-EU parent (HR data) | BCR-Controller, or SCC C2C / C2P |
| EU subsidiary → non-EU shared service centre (back-office) | BCR-Processor, or SCC C2P |
| EU controller → US-DPF-certified SaaS processor | DPF (Art. 45) for the certified parts; SCC + TIA otherwise |
| EU controller → non-DPF US SaaS processor | SCC C2P + TIA + supplementary measures |
| EU processor → non-EU sub-processor | Article 28 + SCC P2P + TIA |
| Internal transfer (EU subsidiary → EU subsidiary) | Not a Chapter V transfer (intra-EEA) |

## 12. Special data types

| Data type | Notes |
|---|---|
| Special-category data (Art. 9) | Higher scrutiny in TIA; supplementary measures more demanding. |
| Children's data | Heightened protections; explicit DPIA where transfer involves children. |
| Criminal-conviction data (Art. 10) | Member-state law constraints; many member states restrict processing. |
| Public-sector data | Article 48 issue more salient; assess foreign-court access. |

## 13. Documentation

For every transfer relying on Chapter V, maintain:

- **Per-transfer assessment** (`transfer-assessment-form.md`).
- **Mechanism document** (signed SCC set; BCR approval certificate; adequacy reference).
- **TIA** (if Art. 46).
- **Supplementary measures plan** (if applicable).
- **Sub-processor consents** (Art. 28).
- **Annual review** entries.

These are part of the Article 5(2) accountability evidence base and of the Article 30 RoPA.

## 14. Termination of a transfer

If, at any time, the protection in the third country no longer meets equivalence (e.g., new surveillance law, supervisory authority direction, data breach), the controller must:

1. Suspend the transfer.
2. Notify the data subject where appropriate.
3. Notify the supervisory authority (Art. 33 if a breach; Art. 36 if prior consultation triggered).
4. Repatriate or delete data.
5. Document and review.

The 2021/914 SCCs include a suspension obligation (Clause 14 / 16) that must be enforced.

---

## Türkçe

# Transfer Rejimi — V. Bölüm Genel Bakışı

## 1. Madde 44 — Genel ilke

İşlenmekte olan veya **üçüncü ülkeye veya uluslararası kuruluşa transferden sonra işlenmek üzere** olan kişisel verilerin herhangi bir transferi, yalnızca, diğer GDPR hükümlerine tabi olmak koşuluyla, V. Bölümdeki koşullara kontrolör ve işleyen tarafından **üçüncü ülkeden veya uluslararası kuruluştan başka bir üçüncü ülkeye veya başka bir uluslararası kuruluşa kişisel verilerin ileri transferleri için de** uyulması durumunda gerçekleşir.

Bu kilit ilkesidir: koruma veriyle birlikte hareket eder. Her ileri transfer değerlendirilmelidir.

## 2. Transfer olarak ne sayılır?

EDPB Rehberleri 05/2021 §7 üç birikimli kriter belirler:

1. Kontrolör / işleyen ("ihracatçı") ilgili işleme için **GDPR'a tabi**dir.
2. İhracatçı veriyi başka bir kontrolör / işleyen / ortak kontrolör / kişiye ("ithalatçı") **iletim yoluyla açıklar veya başka şekilde erişilebilir kılar**.
3. İthalatçı **üçüncü bir ülkede**dir veya bir uluslararası kuruluştur (ithalatçının kendisinin Md. 3 nedeniyle GDPR'a tabi olup olmadığına bakılmaksızın).

Transfer **olan** örnekler:
- Bir AB kontrolörü, depolama için müşteri kayıtlarını ABD SaaS işleyenine gönderir.
- Bir AB iştiraki bordro verisini Hindistan'daki ana şirket İK sistemine yükler.
- Bir AB işleyeni, işlenmiş kayıtları AB dışındaki müşteri kontrolörüne döndürür.

Transfer **olmayan** örnekler:
- GDPR'a tabi (Md. 3(2)) bir AB dışı kontrolör veriyi **AB içinde** işliyor (AB dışı alıcıya iletim yok).
- Üçüncü ülkedeki bir ilgili kişi AB kontrolöründeki kendi hesabına doğrudan erişiyor (ilgili kişi bu anlamda "alıcı" değildir).

## 3. Madde 45 — Yeterlilik kararları

Komisyon, değerlendirme sonrasında, bir üçüncü ülkenin, bir bölgenin veya bir üçüncü ülke içindeki belirli sektörlerin veya bir uluslararası kuruluşun **yeterli koruma seviyesi** sağladığına karar verebilir. Yeterlilik uygulandığında, başka bir yetkilendirme gerekli değildir (Md. 45(1)) — transfer, V. Bölüm amaçları için AB içiymiş gibi muamele görür.

### 3.1 Yeterli ülkeler (2025 ortası doğrulandı; her zaman Komisyonun güncel listesiyle doğrulayın)

| Ülke / bölge | Karar yılı | Notlar |
|---|---|---|
| Andorra | 2010 | |
| Arjantin | 2003 | |
| Kanada (PIPEDA kapsamındaki ticari kuruluşlar) | 2001 | Yalnızca ticari sektör |
| Faroe Adaları | 2010 | |
| Guernsey | 2003 | |
| Man Adası | 2004 | |
| İsrail | 2011 | İzleme altında |
| Japonya | 2019 | AB ile karşılıklı yeterlilik; tamamlayıcı korumalar |
| Jersey | 2008 | |
| Yeni Zelanda | 2012 | |
| Kore Cumhuriyeti (Güney Kore) | 2021 | |
| İsviçre | 2000 | |
| Birleşik Krallık | 2021 | İki karar: GDPR + Kolluk Kuvvetleri Direktifi; yenilenmezse 2025 sunset |
| Uruguay | 2012 | |
| Amerika Birleşik Devletleri | 2023 | **Sınırlı**: yalnızca AB-ABD Veri Gizlilik Çerçevesi (DPF) altında sertifikalı kuruluşlar için geçerlidir |

> **Doğrulama gereksinimi.** DPO bu listeye güvenmeden önce `https://commission.europa.eu/law/law-topic/data-protection/international-dimension-data-protection/adequacy-decisions_en` (veya eşdeğeri ardıl sayfayı) kontrol etmelidir. Yeni kararlar, geri çekmeler veya yenilemeler yıllık incelemeler arasında resmi değiştirebilir.

### 3.2 Bir yeterlilik kararının operasyonel olarak ne anlama geldiği

- Transfer SCC, BCR veya istisnalar **olmadan** izinlidir.
- Genel olarak TIA **gerekmez** (Komisyon zaten yeterliliği değerlendirdi).
- Dayanağı belgele: ilgili kişinin verisi, alıcı, karar referansı, kapsam.
- Geri çekme, sunset veya değişiklik için izleyin.

### 3.3 Ülkeye özgü notlar

- **Birleşik Krallık.** 2021 yeterlilik kararı, yenilenmezse 2025 ortasında sunset olur. DPO Komisyon yenileme sürecini izlemelidir. Yenilenmeme SCC'lere geçişi zorlar.
- **Amerika Birleşik Devletleri.** DPF (2023) Privacy Shield'in yerini alır. Yeterlilik **yalnızca sertifikalı varlıklara** uygulanır. DPO alıcı sertifikasyonunu `dataprivacyframework.gov`'da doğrulamalı ve hukuki itirazları (Schrems III) izlemelidir.
- **İsrail.** Devam eden izleme altında; GDPR ilkeleriyle uyumluluğun gözden geçirilmesi öngörülmektedir.

## 4. Madde 46 — Uygun koruyucu önlemler

Yeterlilik kararı yoksa, kontrolör / işleyen **uygun koruyucu önlemleri** sağladıysa ve **uygulanabilir ilgili kişi haklarının** ve **etkili yasal çarelerin** ilgili kişiler için mevcut olması koşuluyla transferler devam edebilir.

### 4.1 Madde 46(2) kapsamındaki korumalar — özel yetkilendirme gerekmez

| Koruma | Açıklama |
|---|---|
| (a) Kamu otoriteleri arasında yasal olarak bağlayıcı enstrüman | Örn. devlet organları arasındaki uluslararası anlaşma. |
| (b) Bağlayıcı Kurum Kuralları (BCR) | Md. 47'ye göre onaylı. Bkz. `bcr-guide.md`. |
| (c) Standart Sözleşme Şartları (SCC) — Komisyon | 2021/914 seti. Bkz. `scc-guide.md`. |
| (d) Bir denetim makamı tarafından kabul edilen ve Komisyon tarafından onaylanan SCC'ler | Daha az yaygın; bir DPA'nın kendi SCC seti onaylandığında uygulanır. |
| (e) Md. 40 kapsamında onaylı davranış kuralları | Korumaları uygulamak için bağlayıcı ve uygulanabilir taahhütler içermelidir. |
| (f) Md. 42 kapsamında onaylı sertifikasyon mekanizması | Aynı. |

### 4.2 Madde 46(3) kapsamındaki korumalar — denetim makamı yetkilendirmesi gerekli

| Koruma | Açıklama |
|---|---|
| (a) Kontrolör/işleyen ile alıcı arasındaki sözleşmesel maddeler | Özel maddeler, DPA yetkilendirmesi gerektirir. |
| (b) Kamu otoriteleri arasındaki idari düzenlemelere eklenen hükümler | DPA yetkilendirmesi gerektirir. |

### 4.3 Schrems II etkileri

Önemli olarak, ABAD bir V. Bölüm enstrümanını imzalamanın **yeterli olmadığına** karar verdi. İhracatçı, hedef ülkenin hukukunun ve uygulamasının **esasen eşdeğer** koruma sağladığını doğrulamalıdır. Sağlamadığı yerlerde, tamamlayıcı önlemler gereklidir.

Bu Transfer Etki Değerlendirmesinde işlevsel hale getirilir (`transfer-impact-assessment.md`).

## 5. Madde 47 — Bağlayıcı Kurum Kuralları

BCR'ler, ortak ekonomik faaliyette bulunan bir grup teşebbüs veya işletme tarafından uyulan kişisel veri koruma politikalarıdır. Şunlar olmalıdır:

- Grubun üyeleri için yasal olarak bağlayıcı.
- Grubun her üyesine uygulanır.
- İlgili kişilere uygulanabilir haklar tanır.
- Tutarlılık mekanizması yoluyla yetkili denetim makamı tarafından onaylı (Md. 63–67).

Çok uluslu şirketler tarafından kurumsal grup **içinde** sınır ötesi transfer için kullanılır. Bkz. `bcr-guide.md`.

## 6. Madde 48 — Veriye yabancı erişim

Madde 48, Schrems II altında son derece önemli hale geldi. Şunu sağlar:

> Bir kontrolör veya işleyenden kişisel verileri transfer veya açıklama yapmasını gerektiren üçüncü ülkenin bir mahkeme veya tribünalinin herhangi bir kararı ve idari makamının herhangi bir kararı, yalnızca karşılıklı yasal yardım anlaşması gibi uluslararası bir anlaşmaya dayanıyorsa herhangi bir şekilde tanınabilir veya uygulanabilir.

Anlam: MLA / eşdeğerine dayanmayan üçüncü ülke hükümet erişim talepleri **kendi başlarına transfer veya açıklama için yasal bir dayanak değildir**. Alıcı bir Madde 49 istisnasını başvurmalı veya reddetmeli, çatışmayı belgelemeli ve mümkünse ilgili kişiyi bilgilendirmelidir.

Bu özellikle şunları etkiler:
- ABD FISA 702 direktifleri.
- Cloud Act mahkeme celpleri.
- ÇHC Siber Güvenlik Yasası / Veri Güvenliği Yasası / PIPL kapsamındaki Çin ulusal güvenlik talepleri.

## 7. Madde 49 — İstisnalar

Belirli durumlar için, yeterlilik veya korumaların yokluğunda transferler devam edebilir. İstisnalar **dar yorumlanır**, **ara sıra**, **tekrarlanmaz** ve transfer başına uygulanır. Bkz. `derogations.md`.

## 8. Madde 50 — Uluslararası işbirliği

Komisyon ve denetim makamları uluslararası işbirliği mekanizmalarını geliştirmek için adımlar atar; bu madde kontrolör için operasyonel olmaktan çok yapısaldır.

## 9. Karar ağacı (konsolide)

```
1. Bir transfer var mı (EDPB Rehberleri 05/2021 başına)?
   - Hayır → V. Bölüm uygulanmaz; diğer GDPR kurallarını doğrula.
   - Evet → devam et.

2. Bu alıcıyı kapsayan bir Madde 45 yeterlilik kararı var mı?
   - Evet → transfer izinli; dayanağı belgele; yeterliliği izle.
   - Hayır → devam et.

3. Madde 46 kapsamında uygun bir koruma var mı?
   - SCC (2021/914), BCR, davranış kuralları, sertifikasyon, kamu otoritesi düzenlemesi.
   - Enstrümanı belgele.
   - TIA'ya devam et.

4. TIA gerçekleştir (EDPB Tavsiyeleri 01/2020).
   - Eşdeğer koruma? → belgelenmiş korumalarla transfer.
   - Eşdeğer değil? → eşdeğerliğe getirmeye yeterli tamamlayıcı önlemleri belirle.
   - Yeterli? → belgelenmiş tamamlayıcı önlemlerle transfer.
   - Yetersiz? → transferi askıya al.

5. (Son çare) Madde 49 istisnası.
   - Dar, belirli, ara sıra.
   - Dikkatlice belgele.
```

## 10. İleri transferler

İleri transferler (alıcıdan başka bir üçüncü ülkeye) koruma gereksinimini devralır (Md. 44 son cümle). Pratik olarak:

- Madde 28 sözleşmesi / SCC'ler ileri transfer kısıtlamalarını akıtır.
- Alıcı ileri transferden önce eşdeğer korumaları uygulamalıdır.
- İhracatçı hesap verebilir kalır.

SCC'ler için, geçerli olduğu modüllerde Madde 8.7 ileri transfer taahhütlerini gerektirir.

## 11. Çok uluslulardaki transferler

Yaygın senaryolar:

| Senaryo | Mekanizma |
|---|---|
| AB iştiraki → AB dışı ana şirket (İK verisi) | BCR-Kontrolör veya SCC C2C / C2P |
| AB iştiraki → AB dışı ortak hizmet merkezi (geri ofis) | BCR-İşleyen veya SCC C2P |
| AB kontrolörü → ABD-DPF-sertifikalı SaaS işleyeni | Sertifikalı kısımlar için DPF (Md. 45); aksi halde SCC + TIA |
| AB kontrolörü → DPF olmayan ABD SaaS işleyeni | SCC C2P + TIA + tamamlayıcı önlemler |
| AB işleyeni → AB dışı alt-işleyen | Madde 28 + SCC P2P + TIA |
| Dahili transfer (AB iştiraki → AB iştiraki) | V. Bölüm transferi değil (AAA içi) |

## 12. Özel veri türleri

| Veri türü | Notlar |
|---|---|
| Özel kategori veri (Md. 9) | TIA'da daha yüksek inceleme; tamamlayıcı önlemler daha talepkar. |
| Çocuk verisi | Yüksek korumalar; transfer çocukları içerdiğinde açık DPIA. |
| Suç mahkumiyeti verisi (Md. 10) | Üye devlet hukuku kısıtlamaları; birçok üye devlet işlemeyi kısıtlar. |
| Kamu sektörü verisi | Madde 48 sorunu daha belirgin; yabancı mahkeme erişimini değerlendir. |

## 13. Belgeleme

V. Bölüme dayalı her transfer için şunları sürdürün:

- **Transfer başına değerlendirme** (`transfer-assessment-form.md`).
- **Mekanizma belgesi** (imzalı SCC seti; BCR onay sertifikası; yeterlilik referansı).
- **TIA** (Md. 46 ise).
- **Tamamlayıcı önlemler planı** (geçerliyse).
- **Alt-işleyen onayları** (Md. 28).
- **Yıllık inceleme** girişleri.

Bunlar Madde 5(2) hesap verebilirlik kanıt tabanının ve Madde 30 RoPA'nın bir parçasıdır.

## 14. Bir transferi sonlandırma

Herhangi bir zamanda, üçüncü ülkedeki koruma artık eşdeğerliği karşılamıyorsa (örn. yeni gözetim hukuku, denetim makamı yönlendirmesi, veri ihlali), kontrolör:

1. Transferi askıya alır.
2. Uygun olduğunda ilgili kişiyi bilgilendirir.
3. Denetim makamını bilgilendirir (ihlal ise Md. 33; ön danışma tetiklendiyse Md. 36).
4. Veriyi ülkeye iade eder veya siler.
5. Belgeler ve gözden geçirir.

2021/914 SCC'leri uygulanması gereken bir askıya alma yükümlülüğü içerir (Madde 14 / 16).
