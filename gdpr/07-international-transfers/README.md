---
title:
  en: "International Transfers — Section Overview"
  tr: "Uluslararası Transferler — Bölüm Genel Bakışı"
section: "07-international-transfers"
regulation: "GDPR (EU 2016/679)"
articles:
  - "Art. 44 — General principle for transfers"
  - "Art. 45 — Transfers on the basis of an adequacy decision"
  - "Art. 46 — Transfers subject to appropriate safeguards"
  - "Art. 47 — Binding corporate rules"
  - "Art. 48 — Transfers or disclosures not authorised by Union law"
  - "Art. 49 — Derogations for specific situations"
key_caselaw:
  - "Schrems I — C-362/14 (2015) — Safe Harbor invalidated"
  - "Schrems II — C-311/18 (2020) — Privacy Shield invalidated; SCC affirmed with conditions"
key_guidance:
  - "EDPB Recommendations 01/2020 — supplementary measures"
  - "EDPB Recommendations 02/2020 — European Essential Guarantees for surveillance"
  - "EU Commission Implementing Decision 2021/914 — new SCCs"
  - "EDPB Guidelines 05/2021 — interplay of Art. 3 (territorial scope) and Chapter V"
  - "EDPB Recommendations on the EU-US Data Privacy Framework (2023)"
language: "en, tr"
last_reviewed: "2025-05-01"
review_cycle: "annual"
owner: "Data Protection Officer"
co_owner: "Legal"
status: "approved"
classification: "internal"
---

## English

# International Transfers — Section Overview

Chapter V of the GDPR governs the **transfer of personal data to third countries** (countries outside the EEA) and to international organisations. The fundamental principle (Art. 44) is that the level of protection guaranteed by the Regulation must not be undermined by the transfer.

This section gives the organisation a defensible, audit-grade framework for transferring personal data internationally — Schrems II compliant, EDPB-aligned, and operationally usable.

### Why this section exists

Most modern organisations transfer personal data internationally. The CJEU's **Schrems II** judgment (16 July 2020) invalidated the EU-US Privacy Shield and confirmed that controllers using SCCs must verify, on a transfer-by-transfer basis, whether the law of the destination country provides essentially equivalent protection. Failure to comply has produced serial fines:

- **Meta Ireland** (Irish DPC, 2023) — €1.2 billion for unlawful EU-US data transfers.
- **TikTok Ireland** (Irish DPC, 2024) — €530 million for transfers and other violations.
- **Sephora** (CNIL, 2022) — sanctions on transfer documentation.
- **uber** (Dutch DPA, 2024) — €290 million for unlawful transfers to the US.

This section operationalises Chapter V so transfers are mapped, justified, documented, and continuously monitored.

### How to use this section

| If you need to... | Read |
|---|---|
| Understand the legal architecture of Chapter V | `transfer-regime.md` |
| Implement Standard Contractual Clauses (2021/914) | `scc-guide.md` |
| Build Binding Corporate Rules | `bcr-guide.md` |
| Conduct a Transfer Impact Assessment | `transfer-impact-assessment.md` |
| Apply Article 49 derogations (rare/narrow) | `derogations.md` |
| Document a specific transfer | `transfer-assessment-form.md` |

### Files in this section

1. **`transfer-regime.md`** — The Chapter V architecture: adequacy decisions (Art. 45) with current adequate-country list, appropriate safeguards (Art. 46) including SCCs and BCRs, derogations (Art. 49), and the decision tree to choose a mechanism.
2. **`scc-guide.md`** — End-to-end implementation of the Commission's 2021/914 Standard Contractual Clauses: the four modules (Controller-to-Controller, Controller-to-Processor, Processor-to-Processor, Processor-to-Controller), the docking clause, signing, supplementary measures post-Schrems II, mapping to internal contract templates.
3. **`bcr-guide.md`** — Binding Corporate Rules under Article 47: lead authority selection, EDPB approval workflow, mandatory content per WP256/JLS 12, BCR-Controller versus BCR-Processor differences, ongoing monitoring obligations.
4. **`transfer-impact-assessment.md`** — TIA methodology following EDPB Recommendations 01/2020 (six steps), country-law analysis covering US (FISA 702, EO 12333, EO 14086 / Data Privacy Framework), UK, China, Russia, and other surveillance regimes; supplementary measures (encryption, pseudonymisation, contractual, organisational); documentation requirements.
5. **`derogations.md`** — Article 49: narrow construction, occasional and non-repetitive nature, explicit consent with risk briefing, contract necessity, public interest, legal claims, vital interests, public register; documentation and DPA notification.
6. **`transfer-assessment-form.md`** — Fillable per-transfer assessment form: parties, country, lawful basis, mechanism, TIA summary, supplementary measures, DPO opinion, approval, with two worked examples (US SaaS marketing tool; India offshore support).

### Transfer mechanism overview

```
Is the transfer occurring?
├── No (recipient in EEA, or no transfer despite international dimension)
│   └── No Chapter V analysis required (subject to Art. 3 and other GDPR rules)
└── Yes (third country or international organisation)
    ├── Step 1: Is there an Article 45 adequacy decision?
    │   ├── Yes → transfer permitted; document the adequacy basis
    │   └── No → step 2
    ├── Step 2: Is there an Article 46 appropriate safeguard?
    │   ├── SCC (2021/914) → step 3 (TIA)
    │   ├── BCR → step 3 (TIA, lighter where BCR includes assessment)
    │   ├── Approved code of conduct → step 3
    │   ├── Approved certification mechanism → step 3
    │   └── Other safeguard (Art. 46(3)) with DPA authorisation → step 3
    ├── Step 3: TIA (mandatory after Schrems II)
    │   ├── Essentially equivalent protection? → transfer permitted with documented safeguards
    │   └── Not equivalent? → require supplementary measures sufficient to bring up to equivalence; if impossible, suspend transfer
    └── Step 4 (only if 1–3 fail): Article 49 derogation
        ├── Narrow, occasional, non-repetitive
        └── Document carefully; not a back-door
```

### Schrems II baseline

Every transfer relying on Article 46 must:

1. **Identify the transfer.** Parties, data, country, mechanism.
2. **Map the transfer tools.** Which Article 46 instrument is used.
3. **Assess the law and practice of the destination country.** Surveillance powers, redress, judicial independence.
4. **Identify supplementary measures.** Encryption, pseudonymisation, contractual restrictions, organisational measures.
5. **Take any procedural steps.** DPA consultation if required.
6. **Re-evaluate at appropriate intervals.** New laws, new cases, new realities.

(EDPB Recommendations 01/2020 §28–§77.)

### Data Privacy Framework (EU-US, post-2023)

The EU-US Data Privacy Framework (DPF), adopted 10 July 2023, is an Article 45 adequacy decision for transfers from the EEA to **DPF-certified** US organisations. The legal basis is EO 14086 + AG regulations limiting US signals intelligence. Considerations:

- The DPF is **not** a blanket "US is adequate" finding; it covers transfers to certified recipients.
- Verify recipient certification at `dataprivacyframework.gov`.
- Ongoing review: the EDPB has flagged remaining concerns; future challenges (Schrems III) cannot be excluded.
- Where the recipient is not DPF-certified, fall back to SCCs + TIA.

### Section integration

- **Section 02 (RoPA)**: Each processing activity records its international transfer leg, mechanism, and TIA reference.
- **Section 04 (Retention & Erasure)**: Retention limitation is a recognised supplementary measure under EDPB Recommendations 01/2020 §85.
- **Section 05 (Technical measures)**: Encryption with controller-held keys is a primary supplementary measure.
- **Section 06 (Organisational measures)**: Vendor management and processor oversight execute the contractual framework.
- **Section 08 (Breach management)**: A breach during international transfer requires special analysis (which jurisdiction notifies?).
- **Section 09 (Data subject rights)**: Erasure and information rights apply to the destination dataset.
- **Section 11 (Audit)**: TIA freshness and SCC version compliance are core audit topics.

### Common failure modes

| Failure mode | Mitigation |
|---|---|
| Old SCCs (pre-2021) still in force | Migrate to 2021/914 (deadline expired 27 Dec 2022). |
| TIA not performed | Document a TIA per `transfer-impact-assessment.md`. |
| Sub-processor transfers untracked | Article 28 contract requires sub-processor approval and disclosure. |
| US transfers not aligned with DPF status | Track recipient DPF certification; fall back to SCC + TIA. |
| Article 49 derogation used routinely | Re-classify; switch to SCC. |
| TIA never reviewed after sign | Annual TIA review + event-driven re-review. |
| "Onward transfer" from processor to its own sub-processor unauthorised | Update DPA; require flow-down. |

### Maintenance

This section is reviewed at least annually by the DPO with input from Legal. Material developments — a new CJEU ruling, an EDPB statement, a new adequacy decision, a new third-country surveillance law — trigger out-of-cycle review.

> **Verification reminder.** This section reflects the legal and supervisory landscape as of mid-2025. The DPO must verify the current status of adequacy decisions, the latest EDPB guidance, and recent CJEU case law before relying on this material for a specific transfer.

---

## Türkçe

# Uluslararası Transferler — Bölüm Genel Bakışı

GDPR'nin V. Bölümü, **kişisel verilerin üçüncü ülkelere** (AAA dışındaki ülkelere) ve uluslararası kuruluşlara transferini düzenler. Temel ilke (Md. 44), Tüzük tarafından garanti edilen koruma seviyesinin transfer ile zayıflatılmaması gerektiğidir.

Bu bölüm, kuruluşa kişisel verileri uluslararası olarak transfer etmek için savunulabilir, denetim sınıfı bir çerçeve sunar — Schrems II uyumlu, EDPB-uyumlu ve operasyonel olarak kullanılabilir.

### Bu bölüm neden var

Çoğu modern kuruluş kişisel veriyi uluslararası olarak transfer eder. ABAD'ın **Schrems II** kararı (16 Temmuz 2020), AB-ABD Privacy Shield'i geçersiz kıldı ve SCC kullanan kontrolörlerin, transfer bazında, hedef ülkenin hukukunun esasen eşdeğer koruma sağlayıp sağlamadığını doğrulamaları gerektiğini onayladı. Uyumsuzluk seri para cezalarına yol açmıştır:

- **Meta Ireland** (İrlanda DPC, 2023) — yasadışı AB-ABD veri transferleri için 1.2 milyar €.
- **TikTok Ireland** (İrlanda DPC, 2024) — transferler ve diğer ihlaller için 530 milyon €.
- **Sephora** (CNIL, 2022) — transfer belgelendirmesi yaptırımları.
- **Uber** (Hollanda DPA, 2024) — ABD'ye yasadışı transferler için 290 milyon €.

Bu bölüm V. Bölüm'ü işlevsel hale getirir, böylece transferler haritalanır, gerekçelendirilir, belgelenir ve sürekli izlenir.

### Bu bölüm nasıl kullanılır

| İhtiyacınız ise... | Okuyun |
|---|---|
| V. Bölüm'ün hukuki mimarisini anlamak | `transfer-regime.md` |
| Standart Sözleşme Şartlarını (2021/914) uygulamak | `scc-guide.md` |
| Bağlayıcı Kurum Kuralları oluşturmak | `bcr-guide.md` |
| Bir Transfer Etki Değerlendirmesi yürütmek | `transfer-impact-assessment.md` |
| Madde 49 istisnalarını uygulamak (nadir/dar) | `derogations.md` |
| Belirli bir transferi belgelemek | `transfer-assessment-form.md` |

### Bu bölümdeki dosyalar

1. **`transfer-regime.md`** — V. Bölüm mimarisi: yeterlilik kararları (Md. 45) güncel yeterli ülke listesiyle, uygun koruyucu önlemler (Md. 46) SCC ve BCR dahil, istisnalar (Md. 49) ve mekanizma seçimi için karar ağacı.
2. **`scc-guide.md`** — Komisyonun 2021/914 Standart Sözleşme Şartlarının uçtan uca uygulaması: dört modül (Kontrolör-Kontrolör, Kontrolör-İşleyen, İşleyen-İşleyen, İşleyen-Kontrolör), bağlanma maddesi, imzalama, Schrems II sonrası tamamlayıcı önlemler, dahili sözleşme şablonlarına eşleme.
3. **`bcr-guide.md`** — Madde 47 kapsamında Bağlayıcı Kurum Kuralları: lider otorite seçimi, EDPB onay iş akışı, WP256/JLS 12 başına zorunlu içerik, BCR-Kontrolör ile BCR-İşleyen farklılıkları, devam eden izleme yükümlülükleri.
4. **`transfer-impact-assessment.md`** — EDPB Tavsiyeleri 01/2020'yi izleyen TIA metodolojisi (altı adım), ABD (FISA 702, EO 12333, EO 14086 / Veri Gizlilik Çerçevesi), İngiltere, Çin, Rusya ve diğer gözetim rejimlerini kapsayan ülke-hukuk analizi; tamamlayıcı önlemler (şifreleme, takma adlandırma, sözleşmesel, organizasyonel); belgeleme gereksinimleri.
5. **`derogations.md`** — Madde 49: dar yorumlama, ara sıra ve tekrarlanmayan nitelik, risk bilgilendirmesi ile açık rıza, sözleşme zorunluluğu, kamu yararı, hukuki talepler, hayati menfaatler, kamu sicili; belgeleme ve DPA bildirimi.
6. **`transfer-assessment-form.md`** — Doldurulabilir transfer başına değerlendirme formu: taraflar, ülke, hukuki dayanak, mekanizma, TIA özeti, tamamlayıcı önlemler, DPO görüşü, onay; iki işlenmiş örnekle (ABD SaaS pazarlama aracı; Hindistan offshore destek).

### Transfer mekanizması genel bakışı

```
Transfer gerçekleşiyor mu?
├── Hayır (alıcı AAA içinde veya uluslararası boyuta rağmen transfer yok)
│   └── V. Bölüm analizi gerekli değil (Md. 3 ve diğer GDPR kurallarına tabi)
└── Evet (üçüncü ülke veya uluslararası kuruluş)
    ├── Adım 1: Madde 45 yeterlilik kararı var mı?
    │   ├── Evet → transfer izinli; yeterlilik dayanağını belgele
    │   └── Hayır → adım 2
    ├── Adım 2: Madde 46 uygun koruyucu önlem var mı?
    │   ├── SCC (2021/914) → adım 3 (TIA)
    │   ├── BCR → adım 3 (BCR değerlendirme içerdiğinde daha hafif TIA)
    │   ├── Onaylı davranış kuralları → adım 3
    │   ├── Onaylı sertifikasyon mekanizması → adım 3
    │   └── DPA yetkilendirmesiyle diğer koruma (Md. 46(3)) → adım 3
    ├── Adım 3: TIA (Schrems II sonrası zorunlu)
    │   ├── Esasen eşdeğer koruma? → belgelenmiş korumalarla transfer izinli
    │   └── Eşdeğer değil mi? → eşdeğerliğe getirmeye yeterli tamamlayıcı önlemler iste; imkânsızsa transferi askıya al
    └── Adım 4 (yalnızca 1–3 başarısızsa): Madde 49 istisnası
        ├── Dar, ara sıra, tekrarlanmayan
        └── Dikkatlice belgele; arka kapı değil
```

### Schrems II temel çizgisi

Madde 46'ya dayalı her transfer:

1. **Transferi tanımlayın.** Taraflar, veri, ülke, mekanizma.
2. **Transfer araçlarını haritalayın.** Hangi Madde 46 enstrümanı kullanılıyor.
3. **Hedef ülkenin hukukunu ve uygulamasını değerlendirin.** Gözetim yetkileri, başvuru, yargı bağımsızlığı.
4. **Tamamlayıcı önlemleri belirleyin.** Şifreleme, takma adlandırma, sözleşmesel kısıtlamalar, organizasyonel önlemler.
5. **Herhangi bir prosedür adımı atın.** Gerekirse DPA danışmanlığı.
6. **Uygun aralıklarla yeniden değerlendirin.** Yeni yasalar, yeni davalar, yeni gerçekler.

(EDPB Tavsiyeleri 01/2020 §28–§77.)

### Veri Gizlilik Çerçevesi (AB-ABD, 2023 sonrası)

10 Temmuz 2023'te kabul edilen AB-ABD Veri Gizlilik Çerçevesi (DPF), AAA'dan **DPF-sertifikalı** ABD kuruluşlarına transferler için Madde 45 yeterlilik kararıdır. Hukuki dayanak EO 14086 + ABD sinyal istihbaratını sınırlayan AG düzenlemeleridir. Hususlar:

- DPF, "ABD yeterli" şeklinde toptan bir bulgu **değildir**; sertifikalı alıcılara yapılan transferleri kapsar.
- Alıcı sertifikasyonunu `dataprivacyframework.gov`'da doğrulayın.
- Devam eden inceleme: EDPB kalan endişeleri işaretledi; gelecekteki itirazlar (Schrems III) hariç tutulamaz.
- Alıcı DPF-sertifikalı değilse, SCC + TIA'ya geri dönün.

### Bölüm entegrasyonu

- **Bölüm 02 (RoPA)**: Her işleme faaliyeti uluslararası transfer ayağını, mekanizmayı ve TIA referansını kaydeder.
- **Bölüm 04 (Saklama ve Silme)**: Saklama sınırlaması, EDPB Tavsiyeleri 01/2020 §85 kapsamında tanınmış bir tamamlayıcı önlemdir.
- **Bölüm 05 (Teknik önlemler)**: Kontrolör tarafından tutulan anahtarlarla şifreleme birincil bir tamamlayıcı önlemdir.
- **Bölüm 06 (Organizasyonel önlemler)**: Tedarikçi yönetimi ve işleyen denetimi sözleşmesel çerçeveyi yürütür.
- **Bölüm 08 (İhlal yönetimi)**: Uluslararası transfer sırasındaki bir ihlal özel analiz gerektirir (hangi yargı yetkisi bildirim yapıyor?).
- **Bölüm 09 (İlgili kişi hakları)**: Silme ve bilgi hakları hedef veri setine uygulanır.
- **Bölüm 11 (Denetim)**: TIA tazeliği ve SCC sürüm uyumluluğu temel denetim konularıdır.

### Yaygın başarısızlık modları

| Başarısızlık modu | Hafifletme |
|---|---|
| Eski SCC'ler (2021 öncesi) hâlâ yürürlükte | 2021/914'e geçin (son tarih 27 Aralık 2022 doldu). |
| TIA gerçekleştirilmedi | `transfer-impact-assessment.md` başına bir TIA belgele. |
| Alt-işleyen transferleri izlenmedi | Madde 28 sözleşmesi alt-işleyen onayı ve açıklamayı gerektirir. |
| ABD transferleri DPF durumuyla uyumlu değil | Alıcı DPF sertifikasyonunu izleyin; SCC + TIA'ya geri dönün. |
| Madde 49 istisnası rutin olarak kullanıldı | Yeniden sınıflandır; SCC'ye geç. |
| TIA imzalamadan sonra hiç gözden geçirilmedi | Yıllık TIA incelemesi + olay güdümlü yeniden inceleme. |
| İşleyenden kendi alt-işleyenine "ileri transfer" yetkisiz | DPA güncelle; aşağıya akış gerektir. |

### Bakım

Bu bölüm en az yılda bir DPO tarafından Hukuk'un katkısıyla gözden geçirilir. Maddi gelişmeler — yeni bir ABAD kararı, EDPB açıklaması, yeni yeterlilik kararı, yeni üçüncü ülke gözetim hukuku — döngü dışı inceleme tetikler.

> **Doğrulama hatırlatması.** Bu bölüm 2025 ortası itibarıyla hukuki ve denetim manzarasını yansıtır. DPO, belirli bir transfer için bu materyale güvenmeden önce yeterlilik kararlarının mevcut durumunu, en son EDPB rehberini ve son ABAD içtihatını doğrulamalıdır.
