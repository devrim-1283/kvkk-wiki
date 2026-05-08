---
title: "ROPA Operational Guide — Building and Governing the Article 30 Register"
title_tr: "ROPA Operasyonel Kılavuzu — Madde 30 Sicilinin Oluşturulması ve Yönetimi"
section: "02-ropa"
language: ["en", "tr"]
status: "approved"
version: "3.0.0"
last_review: "2026-04-15"
next_review: "2026-10-15"
owner: "Data Protection Officer"
classification: "Internal"
related_articles: ["GDPR Art. 5(2)", "GDPR Art. 24", "GDPR Art. 30", "GDPR Art. 32", "GDPR Art. 35", "GDPR Art. 49"]
related_guidelines: ["EDPB Position Paper on the derogations of Article 30(5) (April 2018)", "ICO Records of Processing Activities Guidance", "CNIL ROPA Templates (registre des activités de traitement)"]
tags: ["ropa", "article-30", "methodology", "discovery", "workshops"]
---

## English

### 1. Legal Foundation

Article 30 GDPR transforms the abstract accountability obligation in Article 5(2) into a concrete documentary deliverable. Without a ROPA, no organisation can credibly demonstrate compliance, respond to a supervisory authority request under Article 31, or build a defensible breach response under Article 33. The European Data Protection Board (EDPB), in its Position Paper of April 2018, made clear that the Article 30(5) "fewer than 250 employees" derogation is "very limited" and should be read narrowly.

The ROPA is also the **input** to almost every other GDPR deliverable:

- The privacy notice (Articles 13–14) is generated *from* the ROPA.
- The retention schedule lives *inside* or *alongside* the ROPA.
- The DPIA register (Article 35) is triggered *by* high-risk entries flagged in the ROPA.
- The international transfer mapping (Articles 44–49) is extracted *from* the ROPA.
- The data subject rights workflow (Articles 15–22) uses the ROPA to locate where data lives.

### 2. Mandatory vs Recommended Content

#### 2.1 Mandatory under Article 30(1) — Controller

| # | Field | GDPR Reference |
|---|-------|----------------|
| 1 | Controller, joint controller(s), representative, DPO contact details | Art. 30(1)(a) |
| 2 | Purposes of processing | Art. 30(1)(b) |
| 3 | Categories of data subjects | Art. 30(1)(c) |
| 4 | Categories of personal data | Art. 30(1)(c) |
| 5 | Categories of recipients | Art. 30(1)(d) |
| 6 | Third-country transfers and safeguards | Art. 30(1)(e) |
| 7 | Envisaged retention periods | Art. 30(1)(f) |
| 8 | General description of TOMs | Art. 30(1)(g) |

#### 2.2 Mandatory under Article 30(2) — Processor

| # | Field | GDPR Reference |
|---|-------|----------------|
| 1 | Processor and each controller, representative, DPO | Art. 30(2)(a) |
| 2 | Categories of processing per controller | Art. 30(2)(b) |
| 3 | Third-country transfers and safeguards | Art. 30(2)(c) |
| 4 | General description of TOMs | Art. 30(2)(d) |

#### 2.3 Recommended Best-Practice Extensions

Authoritative templates from CNIL, ICO and EDPB practical guides recommend extending the minimum legal content with:

- Lawful basis (Art. 6) and, where applicable, Article 9 condition.
- Special category indicator (Art. 9) and criminal data indicator (Art. 10).
- Source of the data (collected from data subject vs. third-party source).
- IT systems / applications where data resides.
- Owner / process owner / business unit.
- DPIA reference (where conducted) and risk score.
- Date of last review and reviewer.
- Cross-border data flow diagram reference.
- Vendor contracts / DPA reference.
- Automated decision-making indicator (Art. 22).
- Data subject volume estimate.
- Country of origin and country of storage.

### 3. Controller vs Processor ROPA — Conceptual Difference

A controller's ROPA describes **why** the organisation processes data. A processor's ROPA describes **what** the organisation does **on behalf of** other controllers. The same legal entity may play both roles for different data flows and therefore must maintain both registers.

See `controller-vs-processor-ropa.md` for detailed treatment.

### 4. Methodology — How to Build the ROPA

A defensible ROPA is built through a four-phase methodology: **Scope → Discovery → Validation → Operationalisation**.

#### 4.1 Phase 1 — Scope

Define the legal entity boundary. For groups, decide whether each subsidiary maintains its own ROPA or whether a single corporate ROPA covers all entities (the latter requires explicit joint controllership analysis under Article 26).

Identify the in-scope business functions:

1. Human Resources (recruitment, onboarding, payroll, performance, offboarding).
2. Sales and Marketing (CRM, lead generation, advertising, events).
3. Customer Operations (orders, support, returns, account management).
4. Finance and Procurement (vendor management, accounts payable, expense management).
5. IT and Security (logging, monitoring, identity management, access control).
6. Facilities (CCTV, access badges, visitor logs).
7. Legal and Compliance (litigation hold, regulatory reporting, whistleblowing).
8. Product and Engineering (analytics, customer-facing features).
9. Mergers, Acquisitions, and Investor Relations (deal data rooms).

#### 4.2 Phase 2 — Discovery

Discovery happens in three parallel streams:

##### 4.2.1 Workshops

Run a 90-minute workshop per business function. Workshop input:

- Process owner and a senior practitioner.
- Pre-read: blank ROPA template and a sample completed row.
- Pre-fill: any data the DPO can glean from the corporate intranet, vendor list, and IT asset register.

Workshop agenda:

| Time | Activity |
|------|----------|
| 0–10 min | Reset on Article 30 obligation, accountability, and consequences of incomplete ROPA. |
| 10–40 min | Walk the function's process map; identify each step that touches personal data. |
| 40–70 min | For each identified processing activity, fill the ROPA template live. |
| 70–85 min | Identify gaps (lawful basis disputes, retention unknowns, vendor uncertainty). |
| 85–90 min | Assign actions, set follow-up date. |

##### 4.2.2 System Discovery

Cross-check workshop output against:

- IT asset register / CMDB.
- SaaS subscription list (procurement records, expense reports, single sign-on logs).
- Vendor contracts (looking for "personal data," "GDPR," "data processing").
- Network egress logs (where DLP exists).
- Data Loss Prevention (DLP) classification reports.
- Data warehouse / lakehouse table catalog.

This step typically uncovers 15–30% additional processing activities not surfaced in workshops, often involving shadow IT.

##### 4.2.3 Document Review

Review:

- Existing privacy notices (any processing described to data subjects must appear in the ROPA).
- Existing DPIAs (any high-risk processing logged here must appear in the ROPA).
- Cookie banner declarations.
- Marketing consent platform configuration.
- Vendor list with data processing agreements (DPAs).

#### 4.3 Phase 3 — Validation

Validation reduces error and inconsistency:

1. **Lawful basis review** — DPO confirms each Article 6 basis selection. Pay particular attention to "legitimate interest": a documented Legitimate Interest Assessment (LIA) must exist for every entry citing Art. 6(1)(f).
2. **Retention sanity check** — every retention period must align with `04-retention-erasure/retention-schedule.md`. Mismatches must be reconciled in one direction.
3. **Recipient reconciliation** — every named recipient must appear on the vendor list with a DPA in place (Art. 28).
4. **Transfer reconciliation** — every third-country transfer must have a documented Article 46 safeguard or Article 49 derogation.
5. **Cross-reference against privacy notice** — purposes, categories, recipients, retention, and transfers must match what is told to data subjects.
6. **Legal review** — Legal sign-off on lawful bases, especially for sensitive processing (Art. 9, Art. 10).

#### 4.4 Phase 4 — Operationalisation

Make the ROPA a living document:

- Assign each entry to a process owner with a named individual and email address.
- Add a "last reviewed" date and a "next review due" date.
- Trigger a quarterly review cycle (see `maintenance.md`).
- Connect change-management processes (procurement, system onboarding, M&A, vendor swap) to ROPA update obligations.
- Connect breach response (Art. 33–34) to ROPA — the ROPA is the first lookup during a breach.

### 5. Tooling

ROPA can be maintained in:

| Tool | Pros | Cons |
|------|------|------|
| Spreadsheet (Excel / Sheets) | Cheap, flexible, universally readable. | Hard to enforce schema, version control, multi-user editing. Suitable for <30 entries. |
| Wiki + structured templates (Confluence, Notion, this repo) | Auditable, linkable, supports cross-references. | Manual reporting; weaker as the register grows. |
| Dedicated GRC / privacy management software (OneTrust, TrustArc, Collibra, Wire, Privacy Tools) | Workflow, automation, reporting, integrations. | Cost; vendor lock-in; risk of "tool-driven theatre." |
| Custom internal database | Full control, deep integration. | Engineering cost; ongoing maintenance. |

For organisations with 50–500 processing activities, a structured wiki or a mid-tier GRC tool is usually optimal. Above 500 activities, dedicated tooling pays back.

Whatever the tool, **the ROPA must be exportable to a single document or table** so a supervisory authority request under Article 31 can be served within hours, not weeks.

### 6. Common Failure Modes

1. **Treating ROPA as a one-off project.** It must be a living register with quarterly reviews.
2. **Confusing system inventory with processing activity inventory.** A single system may host many processing activities; one processing activity may span many systems.
3. **Listing only IT systems and ignoring paper / manual processing.** Paper records, on-paper signature pads, photocopied identification documents, and meeting notes all count.
4. **Stopping at the workshop and skipping validation.** Workshop output is hypothesis; validation proves it.
5. **Letting the ROPA drift out of sync with the privacy notice.** Both must be updated together.
6. **Failing to document the Legitimate Interest Assessment.** "Legitimate interest" without an LIA is not a defensible basis.
7. **Missing the M&A trigger.** Acquisitions, divestitures, and joint ventures must trigger immediate ROPA delta analysis.
8. **Failing to integrate processor information.** Processors' Article 30(2) records must inform the controller's understanding of subprocessing chains.

### 7. Roles and Responsibilities (RACI)

| Activity | DPO | Process Owner | IT/Security | Legal | Procurement |
|----------|-----|---------------|-------------|-------|-------------|
| Define methodology | A/R | C | C | C | I |
| Run workshops | R | A/R | C | I | I |
| Maintain ROPA register | A | R | C | I | C |
| Validate lawful basis | R | C | I | A/R | I |
| Validate vendors / DPAs | C | C | I | A | R |
| Approve final entries | A | R | I | C | I |
| Quarterly review | A/R | R | C | C | C |
| Trigger update on change | C | R | R | C | R |

(R = Responsible, A = Accountable, C = Consulted, I = Informed.)

### 8. Output Quality Checklist

A ROPA entry is "complete" only when **all** of the following are true:

- [ ] Process owner named with email contact.
- [ ] Purpose stated in plain language understandable to a non-lawyer.
- [ ] Lawful basis identified with reference to specific Article 6 sub-clause.
- [ ] If Art. 9 data: Article 9(2) condition cited.
- [ ] Categories of data subjects enumerated (employees, candidates, customers, etc.).
- [ ] Categories of personal data enumerated using a controlled vocabulary.
- [ ] Each recipient named with relationship type (controller, joint controller, processor, sub-processor, third-party recipient under separate basis).
- [ ] For each third-country transfer, the destination country, the transfer mechanism (adequacy decision, SCCs, BCRs, derogation), and the safeguards reference.
- [ ] Retention period stated in concrete terms (not "as long as necessary").
- [ ] TOMs summarised with reference to a TOM register entry.
- [ ] Source of data (data subject vs. other source).
- [ ] Date of last review with reviewer name.
- [ ] DPIA reference if conducted.

---

## Türkçe

### 1. Hukuki Temel

GDPR Madde 30, Madde 5(2)'deki soyut hesap verebilirlik yükümlülüğünü somut bir belgesel çıktıya dönüştürür. ROPA olmadan hiçbir kuruluş, uyumluluğunu inanılır biçimde gösteremez, Madde 31 kapsamında bir denetim otoritesi talebine yanıt veremez veya Madde 33 kapsamında savunulabilir bir ihlal yanıtı oluşturamaz. Avrupa Veri Koruma Kurulu (EDPB), Nisan 2018 tarihli Tutum Belgesinde, Madde 30(5)'teki "250'den az çalışan" muafiyetinin "çok sınırlı" olduğunu ve dar yorumlanması gerektiğini açıkça belirtmiştir.

ROPA aynı zamanda neredeyse tüm diğer GDPR çıktılarının **girdisidir**:

- Gizlilik bildirimi (Madde 13–14) ROPA'dan üretilir.
- Saklama süresi planı ROPA'nın içinde veya yanında yer alır.
- DPIA sicili (Madde 35), ROPA'da işaretlenen yüksek riskli girişler tarafından tetiklenir.
- Uluslararası aktarım haritalaması (Madde 44–49) ROPA'dan çıkarılır.
- Veri sahibi hakları iş akışı (Madde 15–22), verinin nerede yaşadığını bulmak için ROPA'yı kullanır.

### 2. Zorunlu ve Önerilen İçerik

#### 2.1 Madde 30(1) Kapsamında Zorunlu — Veri Sorumlusu

| # | Alan | GDPR Referansı |
|---|------|----------------|
| 1 | Veri sorumlusu, ortak veri sorumluları, temsilci, DPO iletişim | Madde 30(1)(a) |
| 2 | İşleme amaçları | Madde 30(1)(b) |
| 3 | İlgili kişi kategorileri | Madde 30(1)(c) |
| 4 | Kişisel veri kategorileri | Madde 30(1)(c) |
| 5 | Alıcı kategorileri | Madde 30(1)(d) |
| 6 | Üçüncü ülke aktarımları ve güvenceler | Madde 30(1)(e) |
| 7 | Öngörülen saklama süreleri | Madde 30(1)(f) |
| 8 | Teknik ve İdari Önlemlerin (TOM) genel açıklaması | Madde 30(1)(g) |

#### 2.2 Madde 30(2) Kapsamında Zorunlu — Veri İşleyen

| # | Alan | GDPR Referansı |
|---|------|----------------|
| 1 | Veri işleyen, her veri sorumlusu, temsilci, DPO | Madde 30(2)(a) |
| 2 | Her veri sorumlusu için işleme kategorileri | Madde 30(2)(b) |
| 3 | Üçüncü ülke aktarımları ve güvenceler | Madde 30(2)(c) |
| 4 | TOM'ların genel açıklaması | Madde 30(2)(d) |

#### 2.3 Önerilen En İyi Uygulama Eklemeleri

CNIL, ICO ve EDPB pratik kılavuzlarındaki yetkili şablonlar, asgari yasal içeriği şu eklemelerle genişletmeyi önerir:

- Hukuki sebep (Madde 6) ve uygulanabilirse Madde 9 koşulu.
- Özel nitelikli veri göstergesi (Madde 9) ve cezai veri göstergesi (Madde 10).
- Verinin kaynağı (ilgili kişiden mi yoksa üçüncü taraf kaynaktan mı toplandı).
- Verinin bulunduğu BT sistemleri / uygulamaları.
- Sahip / süreç sahibi / iş birimi.
- DPIA referansı (yapıldıysa) ve risk skoru.
- Son inceleme tarihi ve inceleyen.
- Sınır ötesi veri akışı diyagramı referansı.
- Tedarikçi sözleşmeleri / DPA referansı.
- Otomatik karar verme göstergesi (Madde 22).
- İlgili kişi sayısı tahmini.
- Köken ülke ve depolama ülkesi.

### 3. Veri Sorumlusu ve Veri İşleyen ROPA'sı — Kavramsal Fark

Veri sorumlusunun ROPA'sı, kuruluşun veriyi **neden** işlediğini açıklar. Veri işleyenin ROPA'sı, kuruluşun başka veri sorumluları **adına ne yaptığını** açıklar. Aynı tüzel kişi farklı veri akışları için her iki rolü de üstlenebilir ve bu nedenle her iki sicili de tutmalıdır.

Ayrıntılı ele alım için `controller-vs-processor-ropa.md` dosyasına bakınız.

### 4. Metodoloji — ROPA Nasıl Oluşturulur

Savunulabilir bir ROPA, dört aşamalı bir metodolojiyle oluşturulur: **Kapsam → Keşif → Doğrulama → Operasyonelleştirme**.

#### 4.1 Aşama 1 — Kapsam

Tüzel kişi sınırını tanımlayın. Gruplar için, her bir bağlı şirketin kendi ROPA'sını mı tutacağını yoksa tek bir kurumsal ROPA'nın tüm tüzel kişileri mi kapsayacağını belirleyin (sonuncusu Madde 26 kapsamında açık bir ortak veri sorumluluğu analizi gerektirir).

Kapsam dahilindeki iş fonksiyonlarını belirleyin:

1. İnsan Kaynakları (işe alım, oryantasyon, bordro, performans, ayrılış).
2. Satış ve Pazarlama (CRM, talep yaratma, reklamcılık, etkinlikler).
3. Müşteri Operasyonları (siparişler, destek, iadeler, hesap yönetimi).
4. Finans ve Satınalma (tedarikçi yönetimi, ödenecek hesaplar, gider yönetimi).
5. BT ve Güvenlik (loglama, izleme, kimlik yönetimi, erişim kontrolü).
6. Tesis Yönetimi (CCTV, geçiş kartları, ziyaretçi kayıtları).
7. Hukuk ve Uyumluluk (dava saklamaları, düzenleyici raporlama, ihbar).
8. Ürün ve Mühendislik (analitik, müşteriye yönelik özellikler).
9. Birleşme, Devralma ve Yatırımcı İlişkileri (anlaşma veri odaları).

#### 4.2 Aşama 2 — Keşif

Keşif üç paralel akışta gerçekleşir:

##### 4.2.1 Çalıştaylar

Her iş fonksiyonu için 90 dakikalık bir çalıştay düzenleyin. Çalıştay girdisi:

- Süreç sahibi ve kıdemli bir uygulayıcı.
- Ön okuma: boş ROPA şablonu ve örnek tamamlanmış bir satır.
- Ön doldurma: DPO'nun kurumsal intranet, tedarikçi listesi ve BT varlık kaydından çıkarabileceği veriler.

Çalıştay gündemi:

| Süre | Faaliyet |
|------|----------|
| 0–10 dk | Madde 30 yükümlülüğü, hesap verebilirlik ve eksik ROPA'nın sonuçlarına ilişkin hatırlatma. |
| 10–40 dk | Fonksiyonun süreç haritasını gözden geçirin; kişisel veriye dokunan her adımı belirleyin. |
| 40–70 dk | Belirlenen her işleme faaliyeti için ROPA şablonunu canlı olarak doldurun. |
| 70–85 dk | Boşlukları belirleyin (hukuki sebep tartışmaları, bilinmeyen saklama süreleri, tedarikçi belirsizliği). |
| 85–90 dk | Eylemleri atayın, takip tarihi belirleyin. |

##### 4.2.2 Sistem Keşfi

Çalıştay çıktısını şunlarla çapraz kontrol edin:

- BT varlık kaydı / CMDB.
- SaaS abonelik listesi (satınalma kayıtları, gider raporları, tek oturum açma logları).
- Tedarikçi sözleşmeleri ("kişisel veri", "GDPR", "veri işleme" terimlerini arayın).
- Ağ çıkış logları (DLP varsa).
- Veri Kaybı Önleme (DLP) sınıflandırma raporları.
- Veri ambarı / lakehouse tablo kataloğu.

Bu adım, çalıştaylarda gün yüzüne çıkmayan, çoğu zaman gölge BT içeren %15–30 ek işleme faaliyetini ortaya çıkarır.

##### 4.2.3 Belge İncelemesi

Şunları inceleyin:

- Mevcut gizlilik bildirimleri (ilgili kişilere açıklanan her işleme ROPA'da görünmelidir).
- Mevcut DPIA'lar (burada kayıtlı her yüksek riskli işleme ROPA'da görünmelidir).
- Çerez banner bildirimleri.
- Pazarlama onay platformu yapılandırması.
- Veri işleme sözleşmeleri (DPA) ile tedarikçi listesi.

#### 4.3 Aşama 3 — Doğrulama

Doğrulama, hata ve tutarsızlığı azaltır:

1. **Hukuki sebep incelemesi** — DPO her bir Madde 6 sebep seçimini onaylar. "Meşru menfaat" için özellikle dikkatli olun: Madde 6(1)(f) gerekçesi gösteren her giriş için belgelenmiş bir Meşru Menfaat Değerlendirmesi (LIA) bulunmalıdır.
2. **Saklama süresi mantık kontrolü** — her saklama süresi `04-retention-erasure/retention-schedule.md` ile uyumlu olmalıdır. Uyumsuzluklar tek yönde uzlaştırılmalıdır.
3. **Alıcı uzlaşması** — adı geçen her alıcı, tedarikçi listesinde DPA ile birlikte yer almalıdır (Madde 28).
4. **Aktarım uzlaşması** — her üçüncü ülke aktarımının belgelenmiş bir Madde 46 güvencesi veya Madde 49 muafiyeti olmalıdır.
5. **Gizlilik bildirimine karşı çapraz referans** — amaçlar, kategoriler, alıcılar, saklama ve aktarımlar ilgili kişilere anlatılanla eşleşmelidir.
6. **Hukuki inceleme** — özellikle hassas işlemeler (Madde 9, Madde 10) için hukuki sebeplerin Hukuk onayı.

#### 4.4 Aşama 4 — Operasyonelleştirme

ROPA'yı yaşayan bir belgeye dönüştürün:

- Her girişi adı ve e-posta adresi olan bir süreç sahibine atayın.
- "Son inceleme" tarihi ve "Sonraki inceleme" tarihi ekleyin.
- Üç aylık bir inceleme döngüsü tetikleyin (`maintenance.md` dosyasına bakın).
- Değişiklik yönetimi süreçlerini (satınalma, sistem entegrasyonu, M&A, tedarikçi değişimi) ROPA güncelleme yükümlülüklerine bağlayın.
- İhlal yanıtını (Madde 33–34) ROPA'ya bağlayın — bir ihlal sırasında ilk başvuru ROPA'dır.

### 5. Araçlar

ROPA şu araçlarla tutulabilir:

| Araç | Avantaj | Dezavantaj |
|------|---------|------------|
| Tablo (Excel / Sheets) | Ucuz, esnek, evrensel olarak okunabilir. | Şema, sürüm kontrolü, çok kullanıcılı düzenleme zor. <30 girişe uygun. |
| Wiki + yapısal şablonlar (Confluence, Notion, bu repo) | Denetlenebilir, bağlanabilir, çapraz referans destekli. | Manuel raporlama; sicil büyüdükçe zayıflar. |
| Adanmış GRC / gizlilik yönetim yazılımı (OneTrust, TrustArc, Collibra, Wire, Privacy Tools) | İş akışı, otomasyon, raporlama, entegrasyonlar. | Maliyet; tedarikçi bağımlılığı; "araç odaklı tiyatro" riski. |
| Özel iç veritabanı | Tam kontrol, derin entegrasyon. | Mühendislik maliyeti; sürekli bakım. |

50–500 işleme faaliyeti olan kuruluşlar için yapılı bir wiki veya orta seviye bir GRC aracı genellikle optimaldir. 500 faaliyetin üzerinde adanmış araç kendini amorti eder.

Hangi araç olursa olsun, **ROPA tek bir belgeye veya tabloya aktarılabilir olmalıdır** ki Madde 31 kapsamındaki bir denetim otoritesi talebi haftalar değil saatler içinde yanıtlanabilsin.

### 6. Yaygın Başarısızlık Modları

1. **ROPA'yı tek seferlik bir proje olarak görmek.** Üç aylık incelemelerle yaşayan bir sicil olmalıdır.
2. **Sistem envanteri ile işleme faaliyeti envanterini karıştırmak.** Tek bir sistem birçok işleme faaliyetini barındırabilir; bir işleme faaliyeti birçok sistemi kapsayabilir.
3. **Sadece BT sistemlerini listeleyip kağıt / manuel işlemeyi göz ardı etmek.** Kağıt kayıtlar, kağıt imza tabletleri, fotokopiyle kimlik belgeleri ve toplantı notları sayılır.
4. **Çalıştayda durmak ve doğrulamayı atlamak.** Çalıştay çıktısı bir hipotezdir; doğrulama bunu kanıtlar.
5. **ROPA'nın gizlilik bildiriminden kopmasına izin vermek.** İkisi birlikte güncellenmelidir.
6. **Meşru Menfaat Değerlendirmesini belgelememek.** LIA'sız "meşru menfaat" savunulabilir bir sebep değildir.
7. **M&A tetikleyicisini kaçırmak.** Devralmalar, ayrılmalar ve ortak girişimler hemen ROPA delta analizi tetiklemelidir.
8. **Veri işleyen bilgisini entegre etmemek.** Veri işleyenlerin Madde 30(2) kayıtları, veri sorumlusunun alt işleme zincirlerini anlamasına katkı sağlamalıdır.

### 7. Roller ve Sorumluluklar (RACI)

| Faaliyet | DPO | Süreç Sahibi | BT/Güvenlik | Hukuk | Satınalma |
|----------|-----|---------------|-------------|-------|-----------|
| Metodolojiyi tanımla | A/R | C | C | C | I |
| Çalıştayları yürüt | R | A/R | C | I | I |
| ROPA sicilini sürdür | A | R | C | I | C |
| Hukuki sebebi doğrula | R | C | I | A/R | I |
| Tedarikçileri / DPA'ları doğrula | C | C | I | A | R |
| Nihai girişleri onayla | A | R | I | C | I |
| Üç aylık inceleme | A/R | R | C | C | C |
| Değişiklikte güncelleme tetikle | C | R | R | C | R |

(R = Sorumlu, A = Hesap Veren, C = Danışılan, I = Bilgilendirilen.)

### 8. Çıktı Kalitesi Kontrol Listesi

Bir ROPA girişi yalnızca aşağıdakilerin **tümü** doğru olduğunda "tamamlanmış" sayılır:

- [ ] Süreç sahibi e-posta iletişim bilgisiyle adlandırıldı.
- [ ] Amaç, hukukçu olmayanlar tarafından anlaşılabilir sade bir dille belirtildi.
- [ ] Hukuki sebep, Madde 6 alt bendine atıfla belirlendi.
- [ ] Madde 9 verisi varsa: Madde 9(2) koşulu belirtildi.
- [ ] İlgili kişi kategorileri sayıldı (çalışanlar, adaylar, müşteriler vb.).
- [ ] Kişisel veri kategorileri kontrollü bir kelime hazinesiyle sayıldı.
- [ ] Her alıcı, ilişki tipiyle (veri sorumlusu, ortak veri sorumlusu, veri işleyen, alt işleyen, ayrı sebebe dayalı üçüncü taraf alıcı) adlandırıldı.
- [ ] Her üçüncü ülke aktarımı için hedef ülke, aktarım mekanizması (yeterlilik kararı, SCC, BCR, muafiyet) ve güvence referansı verildi.
- [ ] Saklama süresi somut terimlerle belirtildi ("gerektiği kadar" değil).
- [ ] TOM'lar bir TOM sicil girişine atıfla özetlendi.
- [ ] Verinin kaynağı (ilgili kişi vs. başka kaynak).
- [ ] İnceleyen adıyla son inceleme tarihi.
- [ ] Yapıldıysa DPIA referansı.
