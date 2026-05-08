---
title:
  en: "Retention and Destruction Policy"
  tr: "Saklama ve Imha Politikasi"
section: "99-templates"
owner: "DPO / Legal"
version: "1.0"
last_review: "2026-05-08"
next_review: "2026-11-08"
classification: "Internal"
languages: ["en", "tr"]
keywords:
  en: ["retention", "Article 5(1)(e)", "Article 17", "destruction", "schedule"]
  tr: ["saklama", "Madde 5(1)(e)", "Madde 17", "imha", "takvim"]
---

## English

# Retention and Destruction Policy

This policy implements the **storage limitation principle (Article 5(1)(e))** and the **right to erasure (Article 17)**. It establishes the retention schedule, destruction procedure, exceptions for legal holds, and audit mechanism.

### Scope

Applies to all personal data processed by [Controller], whether stored on production systems, replicas, backups, archives, paper, or external processors. It complements the ROPA where retention is set per processing activity.

### Principles

1. Personal data is kept no longer than necessary for the purposes for which it is processed.
2. Where law mandates a longer period, that period applies.
3. Where a data subject right of erasure under Article 17 applies and no exception under Article 17(3) applies, data is erased earlier than the schedule.
4. Anonymised data falls outside scope.
5. Pseudonymised data remains personal data and is subject to retention rules.

### Retention schedule

The schedule below sets a baseline. Tailor to actual processing in the ROPA.

| Category | Period | Basis | Owner |
|----------|--------|-------|-------|
| Customer account active | While account active | Contract | Operations |
| Customer account closed | 3 years post-closure | Limitation period | Operations |
| Order/invoice | 10 years | Tax/accounting law | Finance |
| Customer support tickets | 3 years | Limitation, service quality | Support |
| Marketing consent records | Duration of consent + 12 months suppression | Accountability | Marketing |
| Marketing engagement data | 13 months | Analytics value, minimization | Marketing |
| Cookies (analytics) | 13 months | ePrivacy good practice | Marketing |
| Recruitment — applicant CVs | 6 months unsuccessful, 12 months talent pool with consent | Recruitment, accountability | HR |
| Personnel file | Duration of employment + 10 years | Tax, limitation | HR |
| Payroll | 10 years post-payment | Tax law | Finance |
| Pension | 75 years (life of plan) | Pension law | HR / Pension trustee |
| Workplace monitoring logs | 90 days | Article 32, minimization | Security |
| CCTV footage | 30 days | Security balance | Security |
| Visitor logs | 90 days | Security | Security |
| Vendor due diligence records | 7 years post-engagement | Audit | Procurement |
| Article 28 DPAs | 7 years post-termination | Audit, evidence | Procurement |
| Whistleblower reports | Per whistleblower regime, typically 5 years post-closure | Whistleblower law | Compliance |
| DPIA register entries | 5 years after processing ends | Accountability | DPO |
| ROPA records | While processing active + 5 years post-end | Accountability | DPO |
| Breach register | 5 years post-incident closure | Accountability | DPO |
| Server logs (security) | 12 months | Article 32, security | Security |
| Application logs | 90 days | Operational | Engineering |

### Trigger events

Retention timers start from defined trigger events:

| Event | Trigger |
|-------|---------|
| Account closure | Date of closure |
| Last interaction | Date of last login or transaction |
| Contract end | Date of contract termination |
| Payment | Date of payment |
| Subject leaves employment | Last working day |
| Incident closure | Date marked closed |
| Consent withdrawal | Date withdrawal received |

### Destruction procedure

#### Step 1 — Identification

Automated jobs scan the schedule and identify records due for destruction. Manual review confirms no legal hold.

#### Step 2 — Approval

Records due for destruction are approved by the data owner. Where in scope of legal hold, owner places hold instead.

#### Step 3 — Execution

Destruction is executed across all locations:

- Production database (delete or anonymise per data flow).
- Replicas (cascading delete).
- Search indexes (re-index without record).
- Caches (invalidate).
- Backups (overwrite per backup cycle; document retention of backup-only copies).
- Archives (purge or refresh archive).
- Paper records (cross-cut shredding or secure incineration).
- External processors (notify per Article 28 to delete).

#### Step 4 — Verification

Sample 5% of destruction events monthly. Verify across systems. Document destruction certificate per batch.

#### Step 5 — Logging

Each destruction event logs: identifier of record (or aggregated count), category, basis, system, executed by, date, verification.

### Backups and the retention horizon

GDPR does not require immediate deletion from backups; reasonable backup cycles are acceptable. However:

- Backup retention must itself be limited.
- Restored data must respect prior erasure events; re-erasure on restore is required.
- Document backup retention separately and link to schedule.

### Legal holds

A legal hold suspends destruction for affected records. Triggers include:

- Litigation or arbitration (filed or reasonably anticipated).
- Regulatory investigation.
- Internal investigation.
- Whistleblower report under investigation.

Holds are issued in writing by Legal, listing: scope, custodians, systems, hold start date, expected duration, release approval. Held records are flagged in retention systems and tracked in a hold register. Releases are documented.

### Exceptions to erasure (Article 17(3))

Records cannot be erased pre-schedule under Article 17 where retention is necessary for:

1. Exercising the right of freedom of expression and information.
2. Compliance with a legal obligation requiring processing.
3. Reasons of public interest in public health (Article 9(2)(h),(i)).
4. Archiving in the public interest, scientific or historical research, statistical purposes (Article 89(1)).
5. Establishment, exercise or defense of legal claims.

Each Article 17 request is assessed against these exceptions. Decisions are documented per `99-templates/dsr-response.md`.

### Exceptions to schedule (extension)

Where data must be retained beyond schedule due to:

- Court order.
- Specific contractual obligation.
- Pending DSR.
- Active dispute.

Document the extension reason, expected end, and review trigger.

### Anonymisation as alternative

Where data continues to have value after the retention period (e.g. for trends), it may be anonymised per industry standards (k-anonymity, differential privacy, generalisation) so that re-identification is not reasonably possible. Anonymised data falls outside GDPR.

Pseudonymisation does **not** equal anonymisation. Pseudonymised data remains in scope.

### Roles and responsibilities

| Role | Responsibility |
|------|---------------|
| Data owner | Confirms retention period appropriate; approves destruction |
| DPO | Reviews schedule annually; advises on Article 17 |
| Legal | Issues and releases holds |
| IT operations | Executes destruction across systems |
| Information security | Verifies destruction; secures process |
| Internal audit | Tests samples; reports to audit committee |
| Records management | Maintains physical records destruction |

### KPIs

| KPI | Target |
|-----|--------|
| Destruction execution within 30 days of due date | ≥ 95% |
| Sample verification completed monthly | 100% |
| Legal holds reviewed quarterly for release readiness | 100% |
| ROPA-retention alignment | 100% |
| Article 17 erasure requests within SLA | ≥ 99% |

### Audit

Quarterly internal audit samples destruction events and confirms with system evidence. Annual external review optional. Findings tracked in CAPA.

### Communication

This policy is communicated:

- Via the privacy training program annually.
- On change.
- New starters during onboarding.

### Maintenance

Reviewed annually. Trigger events for update: new business activity, new legal requirement, regulatory change, technology change (e.g. new CRM, new backup system).

### Schedule example with codes

Each retention rule has a code (RR-XX) used in ROPA, system tags, and backup labels:

```
RR-CUS-ACTIVE      Customer account, active           = while_active
RR-CUS-CLOSED      Customer account, closed           = +3y after closure
RR-ORD-INVOICE     Order/invoice                      = 10y from invoice date
RR-MKT-CONSENT     Marketing consent record           = duration_consent + 12m
RR-EMP-PERSONNEL   Personnel file                     = employment + 10y
RR-PAY-PAYROLL     Payroll                            = 10y after payment
RR-CCTV-VIDEO      CCTV video footage                 = 30 days
RR-LOG-SEC         Security logs                      = 12 months
RR-VEN-DPA         Article 28 DPAs                    = +7y after termination
```

Tag every dataset with the applicable code at ingestion. Automated jobs reference the code, not free text.

---

## Türkçe

# Saklama ve İmha Politikası

Bu politika, **depolama sınırlaması ilkesi (Madde 5(1)(e))** ve **silme hakkını (Madde 17)** uygular. Saklama takvimini, imha prosedürünü, hukuki tutmalar için istisnaları ve denetim mekanizmasını belirler.

### Kapsam

[Veri sorumlusu] tarafından üretim sistemlerinde, çoğaltmalarda, yedeklerde, arşivlerde, kağıtta veya dış işleyenlerde depolanan tüm kişisel verilere uygulanır. ROPA'yı tamamlar; saklama işleme faaliyeti başına ROPA'da belirlenir.

### İlkeler

1. Kişisel veri, işleme amaçları için gerekli olandan daha uzun süre saklanmaz.
2. Hukuk daha uzun süre zorunlu kıldığında, o süre uygulanır.
3. Madde 17 altında ilgili kişi silme hakkı uygulanır ve Madde 17(3) altında istisna geçerli olmadığında, veri takvimden önce silinir.
4. Anonimleştirilmiş veri kapsam dışıdır.
5. Takma adlaştırılmış veri kişisel veri olarak kalır ve saklama kurallarına tabidir.

### Saklama takvimi

Aşağıdaki takvim bir temel çizgi belirler. ROPA'daki gerçek işlemeye göre uyarlayın.

| Kategori | Süre | Dayanak | Sahip |
|----------|------|---------|-------|
| Aktif müşteri hesabı | Hesap aktif olduğu sürece | Sözleşme | Operasyonlar |
| Kapatılan müşteri hesabı | Kapanış sonrası 3 yıl | Zamanaşımı süresi | Operasyonlar |
| Sipariş/fatura | 10 yıl | Vergi/muhasebe hukuku | Finans |
| Müşteri destek talepleri | 3 yıl | Zamanaşımı, hizmet kalitesi | Destek |
| Pazarlama rıza kayıtları | Rıza süresi + 12 ay bastırma | Hesap verebilirlik | Pazarlama |
| Pazarlama etkileşim verisi | 13 ay | Analitik değer, minimizasyon | Pazarlama |
| Çerezler (analitik) | 13 ay | ePrivacy iyi uygulama | Pazarlama |
| İşe alım — başvuru CV'leri | 6 ay başarısız, rıza ile yetenek havuzu için 12 ay | İşe alım, hesap verebilirlik | İK |
| Personel dosyası | İstihdam süresi + 10 yıl | Vergi, zamanaşımı | İK |
| Bordro | Ödeme sonrası 10 yıl | Vergi hukuku | Finans |
| Emeklilik | 75 yıl (plan ömrü) | Emeklilik hukuku | İK / Emeklilik mütevellisi |
| İş yeri izleme günlükleri | 90 gün | Madde 32, minimizasyon | Güvenlik |
| CCTV kaydı | 30 gün | Güvenlik dengesi | Güvenlik |
| Ziyaretçi günlükleri | 90 gün | Güvenlik | Güvenlik |
| Tedarikçi durum tespiti kayıtları | İlişki sonrası 7 yıl | Denetim | Satın alma |
| Madde 28 DPA'ları | Fesih sonrası 7 yıl | Denetim, kanıt | Satın alma |
| Muhbir raporları | Muhbir rejimine göre, tipik olarak kapanış sonrası 5 yıl | Muhbir hukuku | Uyumluluk |
| VKDM kayıt defteri girdileri | İşleme sonu sonrası 5 yıl | Hesap verebilirlik | DPO |
| ROPA kayıtları | İşleme aktif + bitiş sonrası 5 yıl | Hesap verebilirlik | DPO |
| İhlal kayıt defteri | Olay kapanışı sonrası 5 yıl | Hesap verebilirlik | DPO |
| Sunucu günlükleri (güvenlik) | 12 ay | Madde 32, güvenlik | Güvenlik |
| Uygulama günlükleri | 90 gün | Operasyonel | Mühendislik |

### Tetikleyici olaylar

Saklama sayaçları tanımlanmış tetikleyici olaylardan başlar:

| Olay | Tetikleyici |
|------|-------------|
| Hesap kapanışı | Kapanış tarihi |
| Son etkileşim | Son giriş veya işlem tarihi |
| Sözleşme bitişi | Sözleşme fesih tarihi |
| Ödeme | Ödeme tarihi |
| Kişi istihdamdan ayrılır | Son çalışma günü |
| Olay kapanışı | Kapatıldı olarak işaretlendiği tarih |
| Rıza geri çekme | Geri çekme alındı tarihi |

### İmha prosedürü

#### Adım 1 — Tanımlama

Otomatik işler takvimi tarar ve imha için zamanı gelmiş kayıtları tanımlar. Manuel inceleme hukuki tutma olmadığını teyit eder.

#### Adım 2 — Onay

İmha için zamanı gelmiş kayıtlar veri sahibi tarafından onaylanır. Hukuki tutma kapsamındaysa, sahip imha yerine tutma yerleştirir.

#### Adım 3 — Yürütme

İmha tüm konumlarda yürütülür:

- Üretim veritabanı (veri akışına göre sil veya anonimleştir).
- Çoğaltmalar (kademeli silme).
- Arama indeksleri (kayıt olmadan yeniden indeksleme).
- Önbellekler (geçersiz kıl).
- Yedekler (yedek döngüsüne göre üzerine yaz; yalnızca yedek kopyaların saklamasını belgele).
- Arşivler (arşivi sil veya yenile).
- Kağıt kayıtlar (çapraz kesim öğütme veya güvenli yakma).
- Dış işleyenler (Madde 28'e göre silme bildirimi).

#### Adım 4 — Doğrulama

İmha olaylarının %5'ini aylık örnekleyin. Sistemler arası doğrulayın. Toplu başına imha sertifikasını belgeleyin.

#### Adım 5 — Günlükleme

Her imha olayı şunları kaydeder: kayıt tanımlayıcısı (veya toplu sayı), kategori, dayanak, sistem, yürüten, tarih, doğrulama.

### Yedekler ve saklama ufku

GDPR yedeklerden hemen silinmeyi gerektirmez; makul yedek döngüleri kabul edilebilirdir. Ancak:

- Yedek saklamanın kendisi de sınırlı olmalıdır.
- Geri yüklenen veri önceki silme olaylarına saygı göstermelidir; geri yükleme üzerine yeniden silme gereklidir.
- Yedek saklamayı ayrı belgeleyin ve takvime bağlayın.

### Hukuki tutmalar

Bir hukuki tutma, etkilenen kayıtlar için imhayı askıya alır. Tetikleyiciler şunları içerir:

- Dava veya tahkim (açılmış veya makul olarak öngörülen).
- Düzenleyici soruşturma.
- İç soruşturma.
- Soruşturma altındaki muhbir raporu.

Tutmalar Hukuk tarafından yazılı olarak verilir, şunları listeler: kapsam, sorumlular, sistemler, tutma başlangıç tarihi, beklenen süre, serbest bırakma onayı. Tutulan kayıtlar saklama sistemlerinde işaretlenir ve bir tutma kayıt defterinde izlenir. Serbest bırakmalar belgelenir.

### Silme istisnaları (Madde 17(3))

Saklama şunlar için gerekli olduğunda Madde 17 altında kayıtlar takvim öncesi silinemez:

1. İfade ve bilgi özgürlüğü hakkının kullanılması.
2. İşleme gerektiren hukuki yükümlülüğe uyum.
3. Halk sağlığında kamu yararı nedenleri (Madde 9(2)(h),(i)).
4. Kamu yararı, bilimsel veya tarihsel araştırma, istatistiksel amaçlar için arşivleme (Madde 89(1)).
5. Hukuki taleplerin kurulması, kullanılması veya savunulması.

Her Madde 17 talebi bu istisnalara karşı değerlendirilir. Kararlar `99-templates/dsr-response.md` uyarınca belgelenir.

### Takvim istisnaları (uzatma)

Veri aşağıdaki nedenlerle takvim ötesinde saklanması gerektiğinde:

- Mahkeme emri.
- Belirli sözleşmesel yükümlülük.
- Bekleyen DSR.
- Aktif anlaşmazlık.

Uzatma nedenini, beklenen sonu ve gözden geçirme tetikleyicisini belgeleyin.

### Alternatif olarak anonimleştirme

Veri saklama dönemi sonrasında değer taşımaya devam ettiğinde (örn. trendler için), endüstri standartlarına göre (k-anonimlik, diferansiyel gizlilik, genelleme) yeniden tanımlamanın makul olarak mümkün olmaması için anonimleştirilebilir. Anonimleştirilmiş veri GDPR dışındadır.

Takma adlaştırma anonimleştirmeye **eşit değildir**. Takma adlaştırılmış veri kapsamda kalır.

### Roller ve sorumluluklar

| Rol | Sorumluluk |
|-----|------------|
| Veri sahibi | Saklama süresinin uygunluğunu teyit eder; imhayı onaylar |
| DPO | Takvimi yıllık gözden geçirir; Madde 17 üzerine danışmanlık verir |
| Hukuk | Tutmaları verir ve serbest bırakır |
| BT operasyonları | Sistemler arası imhayı yürütür |
| Bilgi güvenliği | İmhayı doğrular; süreci güvence altına alır |
| İç denetim | Örnekleri test eder; denetim komitesine raporlar |
| Kayıt yönetimi | Fiziksel kayıt imhasını sürdürür |

### KPI'lar

| KPI | Hedef |
|-----|-------|
| Vade tarihinin 30 günü içinde imha yürütme | ≥ %95 |
| Aylık örnek doğrulaması tamamlanma | %100 |
| Hukuki tutmaların serbest bırakma hazırlığı için çeyreklik gözden geçirilmesi | %100 |
| ROPA-saklama hizalaması | %100 |
| SLA içinde Madde 17 silme talepleri | ≥ %99 |

### Denetim

Çeyreklik iç denetim imha olaylarını örnekler ve sistem kanıtıyla teyit eder. Yıllık dış inceleme isteğe bağlıdır. Bulgular DÖEP'te izlenir.

### İletişim

Bu politika şu şekilde iletilir:

- Yıllık gizlilik eğitim programı yoluyla.
- Değişiklikte.
- Yeni başlayanlar oryantasyon sırasında.

### Bakım

Yıllık gözden geçirilir. Güncelleme için tetikleyici olaylar: yeni iş faaliyeti, yeni hukuki gereksinim, düzenleyici değişiklik, teknoloji değişikliği (örn. yeni CRM, yeni yedek sistemi).

### Kodlu takvim örneği

Her saklama kuralı, ROPA'da, sistem etiketlerinde ve yedek etiketlerinde kullanılan bir koda (RR-XX) sahiptir:

```
RR-CUS-ACTIVE      Musteri hesabi, aktif              = while_active
RR-CUS-CLOSED      Musteri hesabi, kapatildi          = +3y after closure
RR-ORD-INVOICE     Siparis/fatura                     = 10y from invoice date
RR-MKT-CONSENT     Pazarlama riza kaydi               = duration_consent + 12m
RR-EMP-PERSONNEL   Personel dosyasi                   = employment + 10y
RR-PAY-PAYROLL     Bordro                             = 10y after payment
RR-CCTV-VIDEO      CCTV video kaydi                   = 30 days
RR-LOG-SEC         Guvenlik gunlukleri                = 12 months
RR-VEN-DPA         Madde 28 DPA'lari                  = +7y after termination
```

Her veri kümesini girişte uygulanabilir kodla etiketleyin. Otomatik işler serbest metne değil koda atıf yapar.
