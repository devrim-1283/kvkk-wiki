---
title:
  en: "Retention & Erasure — Section Overview"
  tr: "Saklama ve Silme — Bölüm Genel Bakışı"
section: "04-retention-erasure"
regulation: "GDPR (EU 2016/679)"
articles:
  - "Art. 5(1)(e) — Storage limitation"
  - "Art. 17 — Right to erasure ('right to be forgotten')"
  - "Art. 19 — Notification obligation regarding rectification, erasure, restriction"
  - "Recital 26 — Anonymisation vs pseudonymisation"
  - "Recital 39 — Storage limitation principle"
audience:
  - "Data Protection Officers (DPO)"
  - "Records Managers"
  - "Information Security Officers"
  - "Business Process Owners"
  - "Legal & Compliance"
  - "IT Operations"
  - "HR, Finance, Marketing data owners"
language: "en, tr"
last_reviewed: "2025-05-01"
review_cycle: "annual"
owner: "DPO Office"
status: "approved"
classification: "internal"
---

## English

# Retention & Erasure — Section Overview

This section of the GDPR enterprise wiki codifies the organisation's approach to the **storage limitation principle** (Article 5(1)(e)), the **right to erasure** (Article 17), and the operational mechanics of secure deletion, anonymisation, and destruction record-keeping.

### Why this section exists

GDPR forbids keeping personal data "in a form which permits identification of data subjects for **no longer than is necessary** for the purposes for which the personal data are processed." Organisations frequently fail this test because:

- Data accumulates by default; deletion requires deliberate engineering.
- Backups, log files, and analytics warehouses outlive the operational stores they were copied from.
- Departments retain data "just in case" without any documented lawful basis.
- Erasure requests reach a controller but never propagate to processors and sub-processors.
- Cloud platforms retain soft-deleted objects, snapshots, and transaction logs beyond the user-facing retention window.

This section gives every business unit a defensible, documented, auditable retention and erasure programme.

### How to use this section

| If you need to... | Read |
|---|---|
| Understand the policy framework | `retention-policy-template.md` |
| Find the retention period for a data category | `retention-schedule.md` |
| Choose a deletion method (Clear/Purge/Destroy) | `erasure-methods.md` |
| Handle a data subject erasure request | `right-to-erasure.md` |
| Schedule and audit destruction events | `periodic-destruction.md` |
| Document a destruction event | `destruction-record.md` |

### Files in this section

1. **`retention-policy-template.md`** — Master retention and erasure policy. Establishes lawful basis for retention, ownership, governance, periodic review, exception handling, and the chain of accountability from data owner to DPO.
2. **`retention-schedule.md`** — Concrete retention periods for 30+ data categories, mapped against EU member-state minimums (German *Abgabenordnung* § 147 — 10 years for tax records; French *Code de commerce* L.123-22 — 5 years for commercial books; Italian *Codice Civile* art. 2220 — 10 years; Spanish *Código de Comercio* art. 30 — 6 years; Polish accounting law — 5 years; Dutch *Burgerlijk Wetboek* art. 2:10 — 7 years).
3. **`erasure-methods.md`** — Technical playbook for secure deletion. Implements **NIST SP 800-88 Rev. 1** (Clear / Purge / Destroy), crypto-shredding for cloud, anonymisation versus pseudonymisation under Recital 26, backup erasure strategies, and paper destruction.
4. **`right-to-erasure.md`** — Procedure for handling Article 17 requests, the six grounds for erasure, the six exemptions (freedom of expression, legal obligation, public interest, archiving, public health, legal claims), Article 19 notification to recipients, and the one-month statutory timeline.
5. **`periodic-destruction.md`** — Quarterly and annual destruction process, audit trail requirements, automated triggers, retention review cadence.
6. **`destruction-record.md`** — Fillable destruction record template plus three worked examples (paper shred, HDD degauss, database row deletion combined with backup crypto-shredding).

### Key principles applied throughout

- **Storage limitation (Art. 5(1)(e))**: Personal data shall be kept in identifiable form no longer than necessary.
- **Accountability (Art. 5(2))**: The controller shall be able to **demonstrate compliance**. Destruction records, retention schedules, and audit trails are the evidence base.
- **Data minimisation (Art. 5(1)(c))**: If a field is no longer necessary, delete the field — do not keep the record "with the field redacted in the UI".
- **Schrems II linkage**: Where personal data is exported to a third country, retention reductions and pseudonymisation are part of the *supplementary measures* under EDPB Recommendations 01/2020. See section 07.
- **Lawful basis for retention is independent from lawful basis for collection.** Retention beyond the original purpose requires its own justification (legal obligation, legal claims, public interest archiving, etc.).

### Mandatory destruction trigger events

The following events MUST trigger evaluation against the retention schedule:

- Termination of employment (HR records).
- Closure of customer account or cessation of customer relationship.
- Expiry of contractual statute of limitations.
- Expiry of tax / accounting retention obligation.
- Withdrawal of consent (where consent was the lawful basis).
- Successful Article 17 erasure request.
- End of project, study, or research where no archiving exemption applies.
- Decommissioning of a system, service, or processor.

### Roles and responsibilities (RACI summary)

| Activity | Data Owner | DPO | IT Ops | Information Security | Legal |
|---|---|---|---|---|---|
| Define retention period | A/R | C | I | I | C |
| Approve retention schedule | C | A | I | I | R |
| Execute deletion | R | I | A/R | C | I |
| Verify deletion (technical) | I | I | C | A/R | I |
| Maintain destruction records | A/R | I | C | C | I |
| Handle Article 17 requests | C | A/R | C | C | C |
| Annual policy review | C | A/R | I | C | C |

(R = Responsible, A = Accountable, C = Consulted, I = Informed)

### How this section integrates with the rest of the wiki

- **Section 02 (RoPA)**: Each processing activity in the Record of Processing Activities must reference a retention period. The retention schedule is the source of truth.
- **Section 03 (Transparency & consent)**: Privacy notices must disclose the retention period or the criteria used to determine it.
- **Section 05 (Technical measures)**: Encryption, key management, and backup design directly enable crypto-shredding.
- **Section 07 (International transfers)**: Retention reduction is a recognised supplementary measure under Schrems II.
- **Section 08 (Breach management)**: A breach involving data that should already have been deleted is an aggravating factor for fines (Art. 83(2)(d)).
- **Section 09 (Data subject rights)**: Article 17 (erasure) requests interact with rectification, restriction, and portability requests.
- **Section 11 (Audit)**: Destruction records and retention reviews are core audit evidence.

### Common failure modes (and how this section prevents them)

| Failure mode | Mitigation |
|---|---|
| "We keep everything forever, just in case." | Mandatory retention schedule per category. |
| "Marketing kept the unsubscribed list for 5 years." | Lawful basis review; consent withdrawal triggers immediate deletion. |
| "Backups still contain the customer who asked for erasure." | Backup erasure strategy + crypto-shredding. |
| "We deleted from production but the data warehouse still has it." | Erasure propagation procedure (right-to-erasure.md §4). |
| "The processor confirms deletion but we have no document." | Mandatory destruction certificate. |
| "We don't know when this employee record was supposed to be deleted." | Owner + retention period stamped in metadata at creation. |

### Regulatory penalties for failure

Storage limitation violations have produced significant fines:

- **Deutsche Wohnen SE** (Berlin DPA, 2019) — €14.5 million for retaining tenant data with no deletion concept.
- **Vodafone Italia** (Garante, 2020) — €12.25 million, partly for retention violations.
- **Swedish DPA v. employer** (2020) — fine for retaining job applicant data beyond necessity.

### Maintenance

This section is reviewed at least annually by the DPO, with input from data owners. Material change to a member-state legal retention requirement triggers an out-of-cycle update.

---

## Türkçe

# Saklama ve Silme — Bölüm Genel Bakışı

Bu bölüm, kuruluşun **saklama sınırlaması ilkesi** (Madde 5(1)(e)), **silme hakkı** (Madde 17) ve güvenli silme, anonimleştirme ve imha kayıtlarının operasyonel mekaniği konusundaki yaklaşımını kodifiye eder.

### Bu bölüm neden var

GDPR, kişisel verilerin "işlenme amaçları için **gerekli olandan daha uzun süre** ilgili kişilerin tanımlanmasına olanak verecek biçimde" tutulmasını yasaklar. Kuruluşlar bu testte sıkça başarısız olur çünkü:

- Veri varsayılan olarak birikir; silme bilinçli mühendislik gerektirir.
- Yedekler, log dosyaları ve analitik veri ambarları, kopyalandıkları operasyonel depolardan daha uzun ömürlüdür.
- Departmanlar veriyi belgelenmiş hukuki dayanak olmaksızın "ne olur ne olmaz" diye saklar.
- Silme talepleri kontrolöre ulaşır ancak işleyenlere ve alt-işleyenlere yayılmaz.
- Bulut platformları, kullanıcıya görünen saklama süresinin ötesinde yumuşak silinmiş nesneleri, snapshot'ları ve işlem loglarını saklar.

Bu bölüm, her iş birimine savunulabilir, belgelenmiş, denetlenebilir bir saklama ve silme programı sunar.

### Bu bölüm nasıl kullanılır

| İhtiyacınız ise... | Okuyun |
|---|---|
| Politika çerçevesini anlamak | `retention-policy-template.md` |
| Bir veri kategorisi için saklama süresini bulmak | `retention-schedule.md` |
| Silme yöntemi seçmek (Clear/Purge/Destroy) | `erasure-methods.md` |
| Bir ilgili kişi silme talebini ele almak | `right-to-erasure.md` |
| İmha olaylarını planlamak ve denetlemek | `periodic-destruction.md` |
| Bir imha olayını belgelemek | `destruction-record.md` |

### Bu bölümdeki dosyalar

1. **`retention-policy-template.md`** — Ana saklama ve silme politikası. Saklamanın hukuki dayanağını, sahipliği, yönetişimi, periyodik incelemeyi, istisna yönetimini ve veri sahibinden DPO'ya hesap verebilirlik zincirini kurar.
2. **`retention-schedule.md`** — 30'dan fazla veri kategorisi için somut saklama süreleri; AB üye devleti minimumlarıyla eşlenmiş (Alman *Abgabenordnung* § 147 — vergi kayıtları için 10 yıl; Fransız *Code de commerce* L.123-22 — ticari defterler için 5 yıl; İtalyan *Codice Civile* m. 2220 — 10 yıl; İspanyol *Código de Comercio* m. 30 — 6 yıl; Polonya muhasebe yasası — 5 yıl; Hollanda *Burgerlijk Wetboek* m. 2:10 — 7 yıl).
3. **`erasure-methods.md`** — Güvenli silme için teknik el kitabı. **NIST SP 800-88 Rev. 1** (Clear / Purge / Destroy), bulut için kripto-parçalama, Resital 26 kapsamında anonimleştirme - takma adlandırma, yedek silme stratejileri ve kâğıt imhası uygular.
4. **`right-to-erasure.md`** — Madde 17 taleplerinin işlenmesi için prosedür, silme için altı dayanak, altı muafiyet (ifade özgürlüğü, hukuki yükümlülük, kamu yararı, arşivleme, halk sağlığı, hukuki talepler), Madde 19 alıcılara bildirim ve bir aylık yasal süre.
5. **`periodic-destruction.md`** — Üç aylık ve yıllık imha süreci, denetim izi gereksinimleri, otomatik tetikleyiciler, saklama incelemesi sıklığı.
6. **`destruction-record.md`** — Doldurulabilir imha kaydı şablonu artı üç işlenmiş örnek (kâğıt parçalama, HDD demanyetizasyonu, veritabanı satır silme + yedek kripto-parçalama).

### Boyunca uygulanan temel ilkeler

- **Saklama sınırlaması (Md. 5(1)(e))**: Kişisel veriler tanımlanabilir biçimde gerekli olandan daha uzun tutulamaz.
- **Hesap verebilirlik (Md. 5(2))**: Kontrolör uyumu **kanıtlayabilmelidir**. İmha kayıtları, saklama çizelgeleri ve denetim izleri kanıt tabanıdır.
- **Veri minimizasyonu (Md. 5(1)(c))**: Bir alan artık gerekli değilse alanı silin — kaydı "alan UI'da gizlenmiş" şekilde tutmayın.
- **Schrems II bağlantısı**: Kişisel veriler üçüncü ülkeye aktarıldığında, saklama azaltma ve takma adlandırma, EDPB Tavsiyeleri 01/2020 kapsamındaki *tamamlayıcı önlemlerin* bir parçasıdır. Bkz. bölüm 07.
- **Saklamanın hukuki dayanağı, toplamanın hukuki dayanağından bağımsızdır.** Orijinal amacın ötesinde saklama, kendi gerekçesini gerektirir (hukuki yükümlülük, hukuki talepler, kamu yararı arşivlemesi vb.).

### Zorunlu imha tetikleyici olayları

Aşağıdaki olaylar saklama çizelgesine karşı değerlendirmeyi TETİKLEMELİDİR:

- İstihdamın sonlandırılması (İK kayıtları).
- Müşteri hesabının kapatılması veya müşteri ilişkisinin sona ermesi.
- Sözleşmesel zamanaşımının sona ermesi.
- Vergi / muhasebe saklama yükümlülüğünün sona ermesi.
- Rızanın geri çekilmesi (rızanın hukuki dayanak olduğu durumlarda).
- Başarılı bir Madde 17 silme talebi.
- Arşivleme muafiyetinin uygulanmadığı proje, çalışma veya araştırmanın sona ermesi.
- Bir sistemin, hizmetin veya işleyenin hizmet dışı bırakılması.

### Roller ve sorumluluklar (RACI özeti)

| Faaliyet | Veri Sahibi | DPO | BT Ops | Bilgi Güvenliği | Hukuk |
|---|---|---|---|---|---|
| Saklama süresini tanımla | A/R | C | I | I | C |
| Saklama çizelgesini onayla | C | A | I | I | R |
| Silmeyi gerçekleştir | R | I | A/R | C | I |
| Silmeyi doğrula (teknik) | I | I | C | A/R | I |
| İmha kayıtlarını tut | A/R | I | C | C | I |
| Madde 17 taleplerini ele al | C | A/R | C | C | C |
| Yıllık politika incelemesi | C | A/R | I | C | C |

(R = Sorumlu, A = Hesap veren, C = Danışılan, I = Bilgilendirilen)

### Bu bölümün wiki'nin geri kalanıyla entegrasyonu

- **Bölüm 02 (RoPA)**: İşleme Faaliyetleri Sicilindeki her işleme faaliyeti bir saklama süresine atıfta bulunmalıdır. Saklama çizelgesi gerçek kaynaktır.
- **Bölüm 03 (Şeffaflık ve rıza)**: Gizlilik bildirimleri saklama süresini veya bunu belirlemek için kullanılan kriterleri açıklamalıdır.
- **Bölüm 05 (Teknik önlemler)**: Şifreleme, anahtar yönetimi ve yedek tasarımı kripto-parçalamayı doğrudan mümkün kılar.
- **Bölüm 07 (Uluslararası transferler)**: Saklama azaltma, Schrems II kapsamında tanınmış bir tamamlayıcı önlemdir.
- **Bölüm 08 (İhlal yönetimi)**: Zaten silinmiş olması gereken verileri içeren bir ihlal, para cezaları için ağırlaştırıcı bir faktördür (Md. 83(2)(d)).
- **Bölüm 09 (İlgili kişi hakları)**: Madde 17 (silme) talepleri düzeltme, kısıtlama ve taşınabilirlik talepleriyle etkileşime girer.
- **Bölüm 11 (Denetim)**: İmha kayıtları ve saklama incelemeleri temel denetim kanıtıdır.

### Yaygın başarısızlık modları (ve bu bölümün bunları nasıl önlediği)

| Başarısızlık modu | Hafifletme |
|---|---|
| "Her şeyi sonsuza dek saklarız, ne olur ne olmaz." | Kategori başına zorunlu saklama çizelgesi. |
| "Pazarlama, abonelikten çıkmış listeyi 5 yıl sakladı." | Hukuki dayanak incelemesi; rıza geri çekilmesi anında silme tetikler. |
| "Yedekler hâlâ silme isteyen müşteriyi içeriyor." | Yedek silme stratejisi + kripto-parçalama. |
| "Üretimden sildik ama veri ambarında hâlâ var." | Silme yayma prosedürü (right-to-erasure.md §4). |
| "İşleyen silmeyi onaylıyor ama bizde belge yok." | Zorunlu imha sertifikası. |
| "Bu çalışan kaydının ne zaman silinmesi gerektiğini bilmiyoruz." | Sahip + saklama süresi oluşturma sırasında metadata'ya damgalanır. |

### Başarısızlık için yasal cezalar

Saklama sınırlaması ihlalleri önemli para cezalarına yol açmıştır:

- **Deutsche Wohnen SE** (Berlin DPA, 2019) — silme konsepti olmaksızın kiracı verisini saklamak için 14.5 milyon €.
- **Vodafone Italia** (Garante, 2020) — kısmen saklama ihlalleri için 12.25 milyon €.
- **İsveç DPA / işveren** (2020) — iş başvurusu verisini gerekenden uzun saklamak için ceza.

### Bakım

Bu bölüm DPO tarafından veri sahiplerinin katkısıyla en az yılda bir gözden geçirilir. Bir üye devleti yasal saklama gereksinimindeki maddi değişiklik, döngü dışı bir güncelleme tetikler.
