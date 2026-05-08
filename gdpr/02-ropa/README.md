---
title: "Records of Processing Activities (ROPA) — Section Overview"
title_tr: "İşleme Faaliyetleri Kaydı (ROPA) — Bölüm Genel Bakış"
section: "02-ropa"
language: ["en", "tr"]
status: "approved"
version: "2.1.0"
last_review: "2026-04-15"
next_review: "2026-10-15"
owner: "Data Protection Officer"
owner_tr: "Veri Koruma Görevlisi"
classification: "Internal"
related_articles: ["GDPR Art. 30", "GDPR Art. 5", "GDPR Art. 24", "GDPR Art. 35"]
related_guidelines: ["EDPB Guidelines 1/2018 on transparency", "ICO Records of Processing Guidance", "CNIL ROPA Templates"]
tags: ["ropa", "article-30", "accountability", "records", "inventory"]
---

## English

### Purpose of this Section

The Records of Processing Activities (ROPA) section is the operational backbone of GDPR accountability. Article 30 of Regulation (EU) 2016/679 requires controllers and processors to maintain written (electronic) records of all processing activities under their responsibility. These records are the single most important demonstration of compliance under Article 5(2) — the accountability principle — and serve as the evidentiary foundation for every other GDPR obligation: lawful basis assessment (Art. 6), data subject information (Art. 13–14), retention scheduling (Art. 5(1)(e)), security measures (Art. 32), DPIAs (Art. 35), and supervisory authority cooperation (Art. 31).

This section provides:

1. A complete operational guide to building, maintaining, and governing the ROPA across the enterprise.
2. A ready-to-fill ROPA template covering all Article 30(1) and 30(2) mandatory fields plus best-practice extensions.
3. Worked examples for the three most common processing scenarios: HR onboarding, e-commerce order fulfilment, and CCTV surveillance.
4. A maintenance regime aligned with quarterly reviews and material-change triggers.
5. The structural separation between controller-ROPA and processor-ROPA, including information that must flow between the two.

### Files in This Section

| File | Purpose |
|------|---------|
| `ropa-guide.md` | Methodology: legal trigger, scope, discovery workshops, validation, tooling. |
| `ropa-template.md` | Ready-to-fill table with 25+ columns and three completed example rows. |
| `maintenance.md` | Quarterly and annual review cycles, change triggers, ownership, cross-checks. |
| `controller-vs-processor-ropa.md` | Separate inventories, distinct content, processor-to-controller information sharing. |

### How to Use This Section

| Role | Recommended Reading Order |
|------|---------------------------|
| Data Protection Officer | All four files in order. |
| Department head / process owner | `ropa-guide.md` (Sections 4–6), `ropa-template.md`, `maintenance.md`. |
| Procurement / vendor manager | `controller-vs-processor-ropa.md`, `maintenance.md` (M&A and vendor change triggers). |
| Internal auditor | All four files; cross-reference with `04-retention-erasure` and `05-technical-measures`. |
| Engineering / IT | `ropa-template.md` (technical-measures columns), `controller-vs-processor-ropa.md`. |

### Why ROPA Often Fails in Practice

Five recurring patterns explain why most organisations have a ROPA on paper but not in reality:

1. **The ROPA was outsourced to a consultancy.** A consulting firm produced a snapshot during a project but the organisation never internalised the methodology. Six months later the ROPA is stale.
2. **The ROPA equates systems with processing activities.** Each SaaS gets one row, ignoring that one system can host many activities (Salesforce hosts marketing leads, customer service tickets, and partner-management data — three entries, not one).
3. **No process owner exists.** Entries have a department name but no individual; nobody updates them.
4. **The ROPA is hidden in a GRC tool that operations cannot access.** Auditable, but not actionable; nobody learns from it during day-to-day decisions.
5. **No connection to procurement and change management.** New SaaS subscriptions and new vendors arrive without the ROPA being updated.

This section's methodology and templates are designed to address all five.

### Article 30 — Headline Obligations

Article 30(1) — Controller ROPA must contain, at minimum:

1. Name and contact details of the controller, joint controller(s), the controller's representative (if any), and the DPO.
2. The purposes of the processing.
3. A description of the categories of data subjects and of the categories of personal data.
4. The categories of recipients to whom personal data have been or will be disclosed, including recipients in third countries or international organisations.
5. Where applicable, transfers of personal data to a third country or an international organisation, including the identification of that third country or international organisation and, in the case of transfers referred to in the second subparagraph of Article 49(1), the documentation of suitable safeguards.
6. Where possible, the envisaged time limits for erasure of the different categories of data.
7. Where possible, a general description of the technical and organisational security measures referred to in Article 32(1).

Article 30(2) — Processor ROPA must contain, at minimum:

1. Name and contact details of the processor(s) and of each controller on behalf of which the processor is acting, and the controller's representative and the DPO where applicable.
2. The categories of processing carried out on behalf of each controller.
3. Where applicable, transfers of personal data to a third country or an international organisation, including the identification of that third country or international organisation and the documentation of suitable safeguards.
4. Where possible, a general description of the technical and organisational security measures referred to in Article 32(1).

### When ROPA is Mandatory

Article 30(5) provides a narrow derogation for organisations with fewer than 250 employees, but the derogation is largely illusory because it does not apply if any of the following conditions are met:

- The processing is likely to result in a risk to the rights and freedoms of data subjects.
- The processing is not occasional.
- The processing includes special categories of data (Art. 9) or personal data relating to criminal convictions and offences (Art. 10).

In practice, almost every commercial organisation processes employee data, customer data, and supplier data on an ongoing (non-occasional) basis. Therefore, every commercial organisation should maintain a ROPA regardless of headcount. EDPB Position Paper (April 2018) confirms this interpretation.

### Common Pitfalls Around the Article 30(5) Derogation

The "fewer than 250 employees" rule is the most misunderstood part of Article 30. The misunderstandings are:

1. **"We have under 250 staff so we are exempt."** Wrong. The exemption applies only if processing is *occasional, low-risk, and not special-category/criminal*. Almost no commercial entity meets all three on every processing activity.
2. **"Processing employee data is occasional."** Wrong. Employee data is processed continuously across payroll cycles, every working day.
3. **"We do not process special category data."** Worth re-checking. Many organisations process health data (sick leave, occupational health, allergens for catering) without realising.
4. **"The exemption removes the documentation duty entirely."** Wrong. Even within the derogation, the controller and processor must be ready to demonstrate accountability under Art. 5(2). In practice this means a ROPA-equivalent must exist.

### Quality Bar

A defensible ROPA is:

- **Complete**: covers every processing activity, not only the IT systems.
- **Current**: reflects reality within the last quarter, not the state two years ago.
- **Consistent**: uses the same taxonomy as the privacy notice, retention schedule, and DPIA register.
- **Auditable**: every entry can be traced to a process owner, a system of record, and a date of last review.
- **Bilingual where required**: where the supervisory authority operates in a non-English language (e.g., the Turkish KVKK regime under Law No. 6698), Turkish equivalents are maintained alongside English entries.

### Cross-References

- `00-governance/dpo-charter.md` — DPO ownership and escalation.
- `01-core-concepts/lawful-basis.md` — Article 6 lawful basis selection.
- `04-retention-erasure/retention-schedule.md` — Erasure timelines that must match ROPA column 18.
- `05-technical-measures/tom-register.md` — Technical and organisational measures referenced in column 22.
- `07-international-transfers/transfer-impact-assessments.md` — Transfer safeguards referenced in column 21.

### Glossary of Terms Used in This Section

| Term | Definition |
|------|------------|
| ROPA | Records of Processing Activities — the Article 30 register. |
| Controller | The natural or legal person which, alone or jointly with others, determines the purposes and means of the processing (Art. 4(7)). |
| Processor | The natural or legal person which processes personal data on behalf of the controller (Art. 4(8)). |
| Joint controllers | Two or more controllers that jointly determine the purposes and means (Art. 26). |
| Sub-processor | A processor engaged by a processor to carry out specific processing activities on behalf of the controller (Art. 28(2)). |
| Processing activity | A coherent set of operations on personal data driven by a single purpose; the unit of recording in ROPA. |
| TOM | Technical and Organisational Measures (Art. 32). |
| LIA | Legitimate Interest Assessment, required for any reliance on Art. 6(1)(f). |
| DPIA | Data Protection Impact Assessment (Art. 35). |
| TIA | Transfer Impact Assessment, required after the Schrems II decision for transfers under SCCs. |
| DPA | Data Processing Agreement (Art. 28(3)). |

### Roadmap for Implementation

The first 90 days of building a defensible ROPA programme typically follow this rough plan:

| Phase | Days | Activity |
|-------|------|----------|
| 1. Mobilise | 1–10 | Appoint DPO. Issue ROPA charter. Adopt this template. Identify business-function leads. |
| 2. Discover | 11–60 | Workshops with each business function. System discovery. Document review. |
| 3. Validate | 61–80 | DPO and Legal review of every entry. Lawful-basis verification. Vendor/DPA cross-check. Privacy-notice alignment. |
| 4. Operationalise | 81–90 | Assign ownership. Schedule first quarterly review. Wire up change-management hooks (procurement, M&A, IT change). Brief senior leadership. |

### Document Conventions Used

- All file paths are relative to the wiki root.
- Article references use the form "Art. 30(1)(a)" for clarity.
- "Member State" follows the GDPR usage and refers to EU and EEA states.
- "Supervisory authority" is the GDPR term; this includes national DPAs (CNIL in France, BfDI in Germany, AP in the Netherlands, KVKK Authority in Türkiye for the equivalent regime, etc.).

### Audit Readiness in 24 Hours

If a supervisory authority issues an Article 31 request, the DPO should be able to deliver, within 24 hours:

1. The complete current ROPA (controller register, and processor register where applicable).
2. The change log for any entry in scope of the request.
3. The named process owner for each entry.
4. The cross-references to ROPA-aligned artefacts: privacy notices, retention schedule, DPIA register, TOM register, vendor / DPA list, transfer register.
5. Evidence that the ROPA is reviewed on a regular cadence (review history with dates and reviewers).

This is achievable only when the maintenance regime in `maintenance.md` is followed continuously.

---

## Türkçe

### Bu Bölümün Amacı

İşleme Faaliyetleri Kaydı (ROPA) bölümü, GDPR hesap verebilirlik ilkesinin operasyonel omurgasıdır. (AB) 2016/679 Sayılı Tüzüğün 30. maddesi, veri sorumluları ve veri işleyenlerin sorumluluğu altında gerçekleştirilen tüm işleme faaliyetlerinin yazılı (elektronik) kayıtlarını tutmasını zorunlu kılar. Bu kayıtlar, Madde 5(2) — hesap verebilirlik ilkesi — kapsamında uyumluluğu kanıtlamanın en önemli yoludur ve diğer tüm GDPR yükümlülüklerinin (hukuki sebep değerlendirmesi Madde 6, ilgili kişi bilgilendirmesi Madde 13–14, saklama süresi planı Madde 5(1)(e), güvenlik önlemleri Madde 32, DPIA Madde 35 ve denetim otoritesi işbirliği Madde 31) kanıt temelini oluşturur.

Bu bölüm aşağıdakileri sağlar:

1. Kuruluş genelinde ROPA oluşturma, sürdürme ve yönetme konusunda eksiksiz bir operasyonel kılavuz.
2. Madde 30(1) ve 30(2) zorunlu alanlarının tamamını ve en iyi uygulama eklerini kapsayan, doldurmaya hazır bir ROPA şablonu.
3. En sık karşılaşılan üç işleme senaryosu için uygulamalı örnekler: İK işe alım, e-ticaret sipariş süreci ve CCTV gözetimi.
4. Üç aylık incelemeler ve önemli değişiklik tetikleyicileri ile uyumlu bir bakım rejimi.
5. Veri sorumlusu ROPA'sı ile veri işleyen ROPA'sı arasındaki yapısal ayrım ve aralarında akması gereken bilgi.

### Bu Bölümdeki Dosyalar

| Dosya | Amaç |
|-------|------|
| `ropa-guide.md` | Metodoloji: hukuki tetikleyici, kapsam, keşif çalıştayları, doğrulama, araçlar. |
| `ropa-template.md` | 25+ sütunlu, doldurmaya hazır tablo ve üç tamamlanmış örnek satır. |
| `maintenance.md` | Üç aylık ve yıllık inceleme döngüleri, değişiklik tetikleyicileri, sahiplik, çapraz kontroller. |
| `controller-vs-processor-ropa.md` | Ayrı envanterler, farklı içerikler, veri işleyenden veri sorumlusuna bilgi paylaşımı. |

### Bu Bölüm Nasıl Kullanılır

| Rol | Önerilen Okuma Sırası |
|-----|------------------------|
| Veri Koruma Görevlisi | Dört dosyanın tamamı sırasıyla. |
| Departman müdürü / süreç sahibi | `ropa-guide.md` (Bölüm 4–6), `ropa-template.md`, `maintenance.md`. |
| Satınalma / tedarikçi yöneticisi | `controller-vs-processor-ropa.md`, `maintenance.md` (Şirket birleşmeleri ve tedarikçi değişiklik tetikleyicileri). |
| İç denetçi | Dört dosyanın tamamı; `04-retention-erasure` ve `05-technical-measures` ile çapraz referans. |
| Mühendislik / BT | `ropa-template.md` (teknik önlemler sütunları), `controller-vs-processor-ropa.md`. |

### ROPA Pratikte Neden Sıkça Başarısız Olur

Beş tekrarlayan kalıp, çoğu kuruluşun kağıt üzerinde ROPA'sı olduğu ancak gerçekte olmadığını açıklar:

1. **ROPA bir danışmanlığa devredildi.** Bir danışmanlık firması proje sırasında anlık görüntü üretti ancak kuruluş metodolojiyi içselleştirmedi. Altı ay sonra ROPA bayatlamış.
2. **ROPA sistemleri işleme faaliyetleriyle eşitliyor.** Her SaaS'a bir satır verilir, bir sistemin birçok faaliyeti barındırabileceği göz ardı edilir (Salesforce pazarlama leadlerini, müşteri hizmetleri taleplerini ve ortak yönetim verisini barındırır — bir değil, üç giriş).
3. **Süreç sahibi yok.** Girişlerin departman adı vardır ama bireyi yoktur; kimse güncellemez.
4. **ROPA, operasyonun erişemediği bir GRC aracında gizlidir.** Denetlenebilir ama uygulanabilir değil; günlük kararlarda kimse ondan öğrenmez.
5. **Satınalma ve değişiklik yönetimine bağlantı yok.** Yeni SaaS abonelikleri ve yeni tedarikçiler ROPA güncellenmeden gelir.

Bu bölümün metodolojisi ve şablonları beş sorunu da ele almak üzere tasarlanmıştır.

### Madde 30 — Temel Yükümlülükler

Madde 30(1) — Veri Sorumlusu ROPA'sı en az aşağıdakileri içermelidir:

1. Veri sorumlusunun, ortak veri sorumlularının, veri sorumlusu temsilcisinin (varsa) ve DPO'nun adı ve iletişim bilgileri.
2. İşlemenin amaçları.
3. İlgili kişi kategorileri ile kişisel veri kategorilerinin tanımı.
4. Kişisel verilerin ifşa edildiği veya edileceği alıcı kategorileri (üçüncü ülke ve uluslararası kuruluş alıcıları dahil).
5. Uygulanabilir olduğunda, kişisel verilerin üçüncü bir ülkeye veya uluslararası bir kuruluşa aktarılması (söz konusu üçüncü ülke veya kuruluşun belirlenmesi ve Madde 49(1) ikinci alt paragraf kapsamındaki aktarımlarda uygun güvencelerin belgelenmesi dahil).
6. Mümkün olduğunda, farklı veri kategorileri için öngörülen silme süre limitleri.
7. Mümkün olduğunda, Madde 32(1)'de atıfta bulunulan teknik ve idari güvenlik önlemlerinin genel bir tanımı.

Madde 30(2) — Veri İşleyen ROPA'sı en az aşağıdakileri içermelidir:

1. Veri işleyen(ler)in ve veri işleyenin adına hareket ettiği her bir veri sorumlusunun adı ve iletişim bilgileri ile uygun olduğunda veri sorumlusu temsilcisi ve DPO bilgileri.
2. Her bir veri sorumlusu adına gerçekleştirilen işleme kategorileri.
3. Uygulanabilir olduğunda, kişisel verilerin üçüncü bir ülkeye veya uluslararası bir kuruluşa aktarılması.
4. Mümkün olduğunda, Madde 32(1)'de atıfta bulunulan teknik ve idari güvenlik önlemlerinin genel bir tanımı.

### ROPA Ne Zaman Zorunludur

Madde 30(5), 250'den az çalışanı olan kuruluşlar için dar bir muafiyet öngörür; ancak aşağıdaki koşullardan herhangi biri sağlanırsa muafiyet uygulanmaz:

- İşleme, ilgili kişilerin hak ve özgürlükleri için risk doğurma olasılığı taşıyorsa.
- İşleme, arızi (occasional) değilse.
- İşleme, özel nitelikli kişisel verileri (Madde 9) veya cezai mahkumiyet ve suçlara ilişkin kişisel verileri (Madde 10) içeriyorsa.

Pratikte, neredeyse her ticari kuruluş çalışan, müşteri ve tedarikçi verilerini sürekli (arızi olmayan) bir biçimde işler. Bu nedenle her ticari kuruluş, çalışan sayısından bağımsız olarak ROPA tutmalıdır. EDPB Tutum Belgesi (Nisan 2018) bu yorumu doğrulamaktadır.

### Madde 30(5) Muafiyetine İlişkin Yaygın Tuzaklar

"250'den az çalışan" kuralı, Madde 30'un en yanlış anlaşılan kısmıdır. Yanlış anlamalar şunlardır:

1. **"250'den az personelimiz var, bu yüzden muafız."** Yanlış. Muafiyet yalnızca işleme *arızi, düşük riskli ve özel kategori/cezai olmayan* ise geçerlidir. Hemen hiçbir ticari kuruluş her işleme faaliyetinde üçünü birden karşılamaz.
2. **"Çalışan verisi işleme arızidir."** Yanlış. Çalışan verisi her iş gününde, bordro döngüleri boyunca sürekli işlenir.
3. **"Özel kategori veri işlemiyoruz."** Yeniden kontrol etmeye değer. Birçok kuruluş farkında olmadan sağlık verisini (hastalık izni, iş sağlığı, ikram için alerjenler) işler.
4. **"Muafiyet belgeleme görevini tamamen kaldırır."** Yanlış. Muafiyet kapsamında bile veri sorumlusu ve veri işleyen, Madde 5(2) kapsamında hesap verebilirliği göstermeye hazır olmalıdır. Pratikte bu, ROPA eşdeğeri bir belgenin var olması anlamına gelir.

### Kalite Çıtası

Savunulabilir bir ROPA:

- **Eksiksiz**: yalnızca BT sistemlerini değil, her işleme faaliyetini kapsar.
- **Güncel**: iki yıl önceki durumu değil, son üç ay içindeki gerçeği yansıtır.
- **Tutarlı**: gizlilik bildirimi, saklama süresi planı ve DPIA siciliyle aynı taksonomiyi kullanır.
- **Denetlenebilir**: her giriş bir süreç sahibine, bir kayıt sistemine ve son inceleme tarihine kadar izlenebilir.
- **Gerektiğinde iki dilli**: denetim otoritesinin İngilizce dışında bir dilde faaliyet gösterdiği yerlerde (örneğin 6698 sayılı Kanun kapsamında Türk KVKK rejimi), Türkçe karşılıklar İngilizce girişlerle birlikte tutulur.

### Çapraz Referanslar

- `00-governance/dpo-charter.md` — DPO sahipliği ve eskalasyon.
- `01-core-concepts/lawful-basis.md` — Madde 6 hukuki sebep seçimi.
- `04-retention-erasure/retention-schedule.md` — ROPA sütun 18 ile eşleşmesi gereken silme süreleri.
- `05-technical-measures/tom-register.md` — Sütun 22'de atıfta bulunulan teknik ve idari önlemler.
- `07-international-transfers/transfer-impact-assessments.md` — Sütun 21'de atıfta bulunulan aktarım güvenceleri.

### Bu Bölümde Kullanılan Terimler Sözlüğü

| Terim | Tanım |
|-------|-------|
| ROPA | İşleme Faaliyetleri Kaydı — Madde 30 sicili. |
| Veri sorumlusu | Tek başına veya başkalarıyla birlikte işlemenin amaçlarını ve araçlarını belirleyen gerçek veya tüzel kişi (Madde 4(7)). |
| Veri işleyen | Kişisel verileri veri sorumlusu adına işleyen gerçek veya tüzel kişi (Madde 4(8)). |
| Ortak veri sorumluları | Amaçları ve araçları birlikte belirleyen iki veya daha fazla veri sorumlusu (Madde 26). |
| Alt işleyen | Veri sorumlusu adına belirli işleme faaliyetlerini gerçekleştirmek için bir veri işleyen tarafından çalıştırılan veri işleyen (Madde 28(2)). |
| İşleme faaliyeti | Tek bir amaç tarafından yönlendirilen kişisel veriler üzerindeki tutarlı bir operasyon kümesi; ROPA'da kayıt birimi. |
| TOM | Teknik ve İdari Önlemler (Madde 32). |
| LIA | Meşru Menfaat Değerlendirmesi, Madde 6(1)(f)'ye dayanan her durum için gereklidir. |
| DPIA | Veri Koruma Etki Değerlendirmesi (Madde 35). |
| TIA | Aktarım Etki Değerlendirmesi, SCC altındaki aktarımlar için Schrems II kararından sonra gereklidir. |
| DPA | Veri İşleme Sözleşmesi (Madde 28(3)). |

### Uygulama İçin Yol Haritası

Savunulabilir bir ROPA programı oluşturmanın ilk 90 günü genellikle bu kaba planı izler:

| Aşama | Günler | Faaliyet |
|-------|--------|----------|
| 1. Harekete geçir | 1–10 | DPO atayın. ROPA tüzüğünü yayımlayın. Bu şablonu benimseyin. İş fonksiyonu liderlerini belirleyin. |
| 2. Keşfet | 11–60 | Her iş fonksiyonu ile çalıştaylar. Sistem keşfi. Belge incelemesi. |
| 3. Doğrula | 61–80 | DPO ve Hukuk her girişi inceler. Hukuki sebep doğrulama. Tedarikçi/DPA çapraz kontrol. Gizlilik bildirimi uyumlulaştırma. |
| 4. Operasyonelleştir | 81–90 | Sahiplik atayın. İlk üç aylık incelemeyi planlayın. Değişiklik yönetim kancalarını (satınalma, M&A, BT değişikliği) bağlayın. Üst yönetimi bilgilendirin. |

### Kullanılan Belge Kuralları

- Tüm dosya yolları wiki köküne göredir.
- Madde referansları netlik için "Madde 30(1)(a)" biçiminde kullanılır.
- "Üye Devlet", GDPR kullanımına göre AB ve EEA devletlerine atıfta bulunur.
- "Denetim otoritesi" GDPR terimidir; bu, ulusal DPA'ları içerir (Fransa'da CNIL, Almanya'da BfDI, Hollanda'da AP, Türkiye'de eşdeğer rejim için KVKK Kurumu vb.).

### 24 Saatte Denetime Hazırlık

Bir denetim otoritesi Madde 31 talebi yayımlarsa, DPO 24 saat içinde şunları sunabilmelidir:

1. Eksiksiz güncel ROPA (veri sorumlusu sicili ve uygulanabilirse veri işleyen sicili).
2. Talep kapsamındaki her giriş için değişiklik kaydı.
3. Her giriş için adı geçen süreç sahibi.
4. ROPA ile uyumlu eserlere çapraz referanslar: gizlilik bildirimleri, saklama planı, DPIA sicili, TOM sicili, tedarikçi / DPA listesi, aktarım sicili.
5. ROPA'nın düzenli aralıklarla incelendiğine dair kanıt (tarih ve inceleyenlerle inceleme geçmişi).

Bu yalnızca `maintenance.md` dosyasındaki bakım rejiminin sürekli izlenmesiyle başarılabilir.
