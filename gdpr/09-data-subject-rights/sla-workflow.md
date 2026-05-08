---
title:
  en: "DSR SLA Workflow, Automation, and Identity Verification"
  tr: "DSR SLA İş Akışı, Otomasyon ve Kimlik Doğrulama"
section: "09-data-subject-rights"
document_id: "DSR-SLA-001"
owner: "DPO Office"
classification: "Internal"
version: "1.0"
last_review: "2026-05-08"
next_review: "2027-05-08"
language: ["en", "tr"]
references:
  - "GDPR Art. 12(2)–(6)"
  - "GDPR Recital 64"
  - "EDPB Guidelines 01/2022 — Right of access"
---

## English

### 1. Daily SLA roadmap

The one-month statutory deadline (Article 12(3)) is broken into operational milestones so that no case drifts. The roadmap below is for a typical Article 15 access request received on day 0; for other rights the substantive-response deadline shifts but the verification, scoping, and review pattern is the same.

| Day | Event | SLA milestone | System action |
|-----|-------|---------------|---------------|
| Day 0 | Request received | Logged | Auto-create case, assign DSR-YYYY-NNNN, send acknowledgement template |
| Day 1 | Triage | Right(s) classified, tier set | Routing rule fires; primary handler assigned; SLA timer starts |
| Day 2 | Acknowledgement dispatched | Acknowledgement evidence captured | Email log saved; Day-2 KPI met |
| Day 3–5 | Identity verification | Verified or escalated | Automation completes Tier 1/2 in same day; Tier 3/4 may need handler intervention |
| Day 6–10 | Scope expansion | Systems queried, processor requests sent | Automated queries to ROPA-mapped systems; DPA-driven processor tickets |
| Day 11–14 | Data assembly | Draft response under review | Handler reviews retrieved data; redaction tooling applied |
| Day 15–17 | Legal / DPO review | Decision approved | DPO sign-off recorded |
| Day 18–22 | Response prepared | Bilingual response, evidence packaged | Templated letter generated, attachments staged |
| Day 23–25 | Response dispatch | Confirmation captured | Delivery logged |
| Day 26–30 | Buffer for rework or extension notice | Decision to extend recorded if needed | Extension letter under Article 12(3) sent within Day 30 |
| Day 30 | Statutory hard stop | All cases must have substantive response or extension issued | SLA breach alert if not met |
| Day 60–90 | Extension period (if invoked) | Substantive response completed | Closure |

If a case is dispatched before Day 25 the buffer is freed; if a case slips past Day 22 a senior handler is paged.

### 2. Automation requirements

Manual workflows do not scale. The DSR programme runs on a small set of integrated systems:

| System | Purpose |
|--------|---------|
| Ticket / case management (ServiceNow, Jira Service Management, Zendesk DSR module, OneTrust DSR) | Case file, SLA timer, audit log |
| Identity verification microservice | Tier 1/2/3 routing, OTP issuance, evidence capture |
| Customer 360 / CRM integration | Single-customer view across products |
| ROPA mapping service | Translate "what data do we have on this person" into a list of systems to query |
| Data discovery agents (per system) | Pull data on identity, return structured packet |
| Redaction tooling | Apply Article 15(4) redactions for third-party data |
| Communications generator | Bilingual templated letters |
| Audit log | Immutable, time-stamped, exportable for SA |

Automation targets:

| Target | Goal |
|--------|------|
| Time from receipt to acknowledgement | < 4 working hours |
| Tier 1 verification | < 1 hour |
| Tier 2 verification | < 24 hours |
| ROPA system query coverage | 100% of catalogued systems |
| Manual handler workload per case | 60–90 minutes for standard Article 15 |

### 3. Risk-tiered identity verification

The four-tier model:

#### Tier 1 — Authenticated session

The requester is making the request from an authenticated session inside the controller's product. Identity is established by the active session and the request is bound to the authenticated user. No additional verification is required.

Use cases:
- in-app "request a copy of my data" flow;
- in-app "delete my account and data" flow;
- HR self-service kiosk on corporate network for employee requests.

Risks: someone using a colleague's logged-in computer. Mitigation: any erasure or portability action invokes a step-up authentication (re-enter password and MFA).

#### Tier 2 — On-file channel match

The requester writes from an email address or postal address on file with the controller. One factor of corroboration is requested:
- last four digits of customer ID;
- last invoice month;
- a one-time code sent to the on-file phone number;
- a confirmation link sent to the on-file email (if the request came by post).

Use cases:
- email request from the customer's known email;
- letter from the address on file.

Risks: account takeover where the attacker has changed the on-file email. Mitigation: cross-check recent identifier changes; if the email was changed within the last 90 days, escalate to Tier 3.

#### Tier 3 — Two-factor verification

The requester is unknown to us, the channel does not match a record on file, or the request involves sensitive identifiers. Two factors are required, drawn from a defined list:
- something you know (account credentials, PIN, account-specific question);
- something you have (a code on a registered device, an existing token);
- something you are (occasionally, a live photo for low-risk accounts; never as a default);
- a documentary fact known only to the requester (transaction amount, ticket number).

ID document copy is not required by default at Tier 3. The agent calibrates to the data sensitivity.

#### Tier 4 — High-risk verification

Reserved for:
- Article 9 special category data requests;
- erasure of an entire long-term account;
- data of a deceased person;
- requests involving children;
- requests by lawyers, executors, court-appointed administrators;
- requests where there is reasonable suspicion of fraud or coercion.

Tier 4 includes:
- a redacted ID document (everything except name and photo) provided through a secure upload channel;
- a written authorisation if acting through a representative;
- where appropriate, a video call with the DPO office;
- legal review of any document submitted.

Tier 4 evidence is retained only as long as needed for verification (typically deleted within 30 days of case closure unless required for litigation hold) and stored encrypted with restricted access.

### 4. What must not happen during identity verification

EDPB 01/2022 §72 and good practice prohibit:
- demanding ID documents at Tier 1 or Tier 2;
- using the verification process to test the requester's commitment to their request;
- requiring the requester to complete more steps than a fraudulent request would survive;
- collecting more data than the request itself would have produced.

If the controller cannot identify the requester from the data held (Article 11), it informs the requester and asks for further information. If the requester does not provide it, Articles 15–20 do not apply, but the controller must still document this position and respond in writing.

### 5. Escalation thresholds

| Trigger | Escalation |
|---------|-----------|
| Tier 4 case | DPO-supervised |
| Day 22 still not dispatched | Senior handler + DPO daily check-in |
| Day 28 still not dispatched | Executive sponsor notified |
| Article 12(3) extension considered | DPO approval required; reasons documented |
| Refusal under Article 12(5) | DPO approval required |
| Lawyer-on-other-side request | Legal joins case file |
| Request from a public figure or a vulnerable person | DPO supervision; communications review |
| Request appears to relate to active litigation | Legal joins; potential litigation hold |
| Request that is part of a coordinated campaign (>10 similar requests) | Aggregate response strategy with DPO and Legal |

### 6. Coordinated campaigns and bulk requests

Where a third party orchestrates many similar requests on behalf of named data subjects, the controller responds to each individually but may use a templated letter and an aggregated case ID prefix. Each requester remains entitled to a personalised, timely response. The DPO ensures that templating does not erode quality.

### 7. Cross-product and cross-jurisdiction handling

If the requester has accounts across multiple products, the case handler treats this as a single request unless the products operate under separate legal entities with separate controllerships. In that case the requester is told that their request has been forwarded to each controller, and each operates its own SLA.

For requesters whose data sits across EU and Türkiye:
- GDPR rights apply to EU-side data;
- KVKK Article 11 rights apply to TR-side data;
- a unified response is preferred where the requester writes once;
- bilingual delivery is the default.

### 8. SLA tracking and reporting

The DSR system produces:

- Daily exception report: cases at Day 22+ without dispatch.
- Weekly KPI report: median, p90, breach count.
- Monthly DPO dashboard: refusal rate, extension rate, complaints.
- Quarterly executive report: trend lines and resourcing implications.
- Annual audit pack: all metrics with evidence for SA review.

Breach of SLA is treated as an internal incident. Repeated breaches in a single team trigger root-cause analysis under section `08-breach-management` discipline.

### 9. Handler workload management

A handler manages a maximum of 25 active cases at any time. Overflow is escalated to the lead handler. Hiring is calibrated so that the team can absorb predictable spikes (post-launch, post-incident, end-of-year) without breaching SLA.

Cross-training across products and across rights is mandatory; no single point of failure on any individual handler.

### 10. Tooling principles

- Audit log: immutable, time-stamped, exportable.
- Version control: every letter and every decision recorded with version.
- Localisation: bilingual templates by default; additional languages as needed.
- Accessibility: WCAG-compliant for any web component; large-print and screen-reader formats available on request.
- Security: encryption at rest, TLS in transit, restricted access by role, no email of sensitive data in plain attachments.

### 11. Quarterly review of the workflow

Every quarter the DPO reviews:
- KPI trends;
- new categories of request seen;
- changes in EDPB or SA guidance affecting workflow;
- new products or processors that change the scope landscape;
- regulator decisions in the same sector;
- complaints or DSR-related litigation.

Updates to this document are version-controlled and trained out to the team.

---

## Türkçe

### 1. Günlük SLA yol haritası

Bir aylık yasal süre (Madde 12(3)), hiçbir vakanın savrulmaması için operasyonel kilometre taşlarına bölünür. Aşağıdaki yol haritası, 0. günde alınan tipik bir Madde 15 erişim talebi içindir.

| Gün | Olay | SLA kilometre taşı | Sistem eylemi |
|-----|------|-------------------|--------------|
| 0. gün | Talep alındı | Kayıtlı | Otomatik dosya oluştur, DSR-YYYY-NNNN ata, onay şablonunu gönder |
| 1. gün | Triyaj | Hak(lar) sınıflandırıldı, aşama belirlendi | Yönlendirme kuralı çalışır; birincil işleyici atanır; SLA zamanlayıcısı başlar |
| 2. gün | Onay gönderildi | Onay kanıtı yakalandı | E-posta günlüğü kaydedildi |
| 3.–5. gün | Kimlik doğrulama | Doğrulandı veya yükseltildi | Otomasyon Aşama 1/2'yi aynı gün tamamlar; Aşama 3/4 işleyici müdahalesi gerektirebilir |
| 6.–10. gün | Kapsam genişletme | Sistemler sorgulandı, veri işleyen talepleri gönderildi | ROPA eşlemeli sistemlere otomatik sorgular; VİS odaklı veri işleyen biletleri |
| 11.–14. gün | Veri toplama | Taslak yanıt incelemede | İşleyici alınan veriyi inceler; redaksiyon araçları uygulanır |
| 15.–17. gün | Hukuk / VKK incelemesi | Karar onaylandı | VKK onayı kaydedildi |
| 18.–22. gün | Yanıt hazırlandı | İki dilli yanıt, kanıt paketlendi | Şablonlu mektup oluşturuldu, ekler hazırlandı |
| 23.–25. gün | Yanıt gönderildi | Onay yakalandı | Teslimat kaydedildi |
| 26.–30. gün | Yeniden çalışma veya uzatma bildirimi için tampon | Gerekirse uzatma kararı kaydedildi | Madde 12(3) uzatma mektubu 30. gün içinde gönderildi |
| 30. gün | Yasal kesin son tarih | Tüm vakaların esaslı yanıtı veya uzatması yayımlanmış olmalı | Karşılanmadıysa SLA ihlal uyarısı |
| 60.–90. gün | Uzatma süresi (çağrılmışsa) | Esaslı yanıt tamamlandı | Kapatma |

### 2. Otomasyon gereksinimleri

Manuel iş akışları ölçeklenmez. DSR programı küçük bir entegre sistem kümesi üzerinde çalışır:

| Sistem | Amaç |
|--------|------|
| Bilet / vaka yönetimi | Dosya, SLA zamanlayıcısı, denetim günlüğü |
| Kimlik doğrulama mikro hizmeti | Aşama 1/2/3 yönlendirme, OTP yayını, kanıt yakalama |
| Müşteri 360 / CRM entegrasyonu | Ürünler arası tek müşteri görünümü |
| ROPA eşleme hizmeti | "Bu kişi hakkında hangi veriye sahibiz" sorusunu sorgulanacak sistem listesine çevirir |
| Veri keşif ajanları (sistem başına) | Kimlik üzerine veri çeker, yapılandırılmış paket döndürür |
| Redaksiyon aracı | Üçüncü taraf verileri için Madde 15(4) redaksiyonlarını uygular |
| İletişim oluşturucu | İki dilli şablonlu mektuplar |
| Denetim günlüğü | Değiştirilemez, zaman damgalı, DM için dışa aktarılabilir |

Otomasyon hedefleri:

| Hedef | Amaç |
|-------|------|
| Alıştan onaya kadar süre | < 4 iş saati |
| Aşama 1 doğrulaması | < 1 saat |
| Aşama 2 doğrulaması | < 24 saat |
| ROPA sistem sorgu kapsamı | Kataloglu sistemlerin %100'ü |
| Vaka başına manuel işleyici iş yükü | Standart Madde 15 için 60–90 dakika |

### 3. Risk seviyeli kimlik doğrulama

Dört aşama:

#### Aşama 1 — Kimlik doğrulamalı oturum

Talep eden, veri sorumlusunun ürünü içinde kimlik doğrulamalı bir oturumdan talepte bulunmaktadır. Kimlik aktif oturumla belirlenir ve talep, kimlik doğrulamalı kullanıcıya bağlanır.

Kullanım durumları:
- uygulama içi "verimin kopyasını talep et" akışı;
- uygulama içi "hesabımı ve verimi sil" akışı;
- çalışan talepleri için kurumsal ağdaki İK self-servis kiosku.

Riskler: bir meslektaşın oturum açmış bilgisayarını kullanan biri. Azaltma: herhangi bir silme veya taşınabilirlik eylemi yükseltilmiş kimlik doğrulama gerektirir.

#### Aşama 2 — Dosya kanalı eşleşmesi

Talep eden, veri sorumlusunda kayıtlı bir e-posta adresinden veya posta adresinden yazıyor. Bir doğrulama faktörü istenir:
- müşteri kimliğinin son dört hanesi;
- son fatura ayı;
- dosyada bulunan telefon numarasına gönderilen tek seferlik kod;
- dosyada bulunan e-postaya gönderilen onay bağlantısı.

#### Aşama 3 — İki faktörlü doğrulama

Talep eden bize bilinmiyor, kanal dosyada bir kayıtla eşleşmiyor veya talep hassas tanımlayıcılar içeriyor.

Kimlik belgesi kopyası Aşama 3'te varsayılan olarak gerekmez. Aracı, veri hassasiyetine göre kalibre eder.

#### Aşama 4 — Yüksek riskli doğrulama

Şunlar için ayrılmıştır:
- Madde 9 özel kategori veri talepleri;
- tüm uzun vadeli hesabın silinmesi;
- vefat etmiş bir kişinin verisi;
- çocukları içeren talepler;
- avukatlar, vasiyet uygulayıcıları tarafından talepler;
- dolandırıcılık veya zorlama makul şüphesi olan talepler.

Aşama 4 dahildir:
- güvenli yükleme kanalı üzerinden sağlanan redakteli bir kimlik belgesi (ad ve fotoğraf dışındaki her şey);
- temsilci aracılığıyla hareket ediliyorsa yazılı yetkilendirme;
- uygun olduğunda, VKK ofisi ile görüntülü görüşme;
- gönderilen belgelerin hukuki incelemesi.

Aşama 4 kanıtı yalnızca doğrulama için gereken süre boyunca saklanır.

### 4. Kimlik doğrulama sırasında olmaması gerekenler

EDPB 01/2022 §72 ve iyi uygulama yasaktır:
- Aşama 1 veya Aşama 2'de kimlik belgesi talep etmek;
- doğrulama sürecini talep edenin taahhüdünü test etmek için kullanmak;
- talep edenin sahte bir talebin atlatabileceğinden daha fazla adım tamamlamasını gerektirmek;
- talebin kendisinin üreteceğinden daha fazla veri toplamak.

### 5. Yükseltme eşikleri

| Tetikleyici | Yükseltme |
|-------------|-----------|
| Aşama 4 vakası | VKK denetiminde |
| 22. gün hâlâ gönderilmedi | Kıdemli işleyici + VKK günlük kontrolü |
| 28. gün hâlâ gönderilmedi | Yönetici sponsor bilgilendirildi |
| Madde 12(3) uzatması düşünüldü | VKK onayı gerekli |
| Madde 12(5) altında reddetme | VKK onayı gerekli |
| Karşı taraf avukatından talep | Hukuk dosyaya katılır |
| Kamuoyunda bilinen veya savunmasız kişiden talep | VKK denetimi |
| Aktif davayla ilgili görünen talep | Hukuk katılır; potansiyel dava tutma |
| Koordineli kampanyanın parçası olan talep (10+ benzer talep) | VKK ve Hukuk ile toplu yanıt stratejisi |

### 6. Koordineli kampanyalar ve toplu talepler

Bir üçüncü taraf, adlandırılmış ilgili kişiler adına birçok benzer talebi koordine ettiğinde, veri sorumlusu her birine ayrı yanıt verir ancak şablonlu bir mektup ve bir araya getirilmiş bir vaka kimliği öneki kullanabilir.

### 7. Çapraz ürün ve çapraz yargı yetkisi yönetimi

Talep edenin birden fazla ürün üzerinde hesabı varsa, vaka işleyicisi bunu tek bir talep olarak değerlendirir.

AB ve Türkiye'deki verileri olan talep edenler için:
- AB tarafı veri için GDPR hakları geçerlidir;
- TR tarafı veri için KVKK Madde 11 hakları geçerlidir;
- talep eden bir kez yazdığında birleşik yanıt tercih edilir;
- iki dilli teslimat varsayılandır.

### 8. SLA izleme ve raporlama

DSR sistemi şunları üretir:
- Günlük istisna raporu: gönderim olmadan 22+ günde olan vakalar.
- Haftalık KPI raporu: medyan, p90, ihlal sayısı.
- Aylık VKK panosu: reddetme oranı, uzatma oranı, şikayetler.
- Üç aylık yönetici raporu: trend çizgileri ve kaynaklama etkileri.
- Yıllık denetim paketi: DM incelemesi için kanıtla tüm metrikler.

### 9. İşleyici iş yükü yönetimi

Bir işleyici aynı anda en fazla 25 aktif vaka yönetir.

### 10. Araç ilkeleri

- Denetim günlüğü: değiştirilemez, zaman damgalı, dışa aktarılabilir.
- Sürüm kontrolü.
- Yerelleştirme: varsayılan olarak iki dilli şablonlar.
- Erişilebilirlik: web bileşeni için WCAG uyumlu.
- Güvenlik: dinlenmede şifreleme, aktarımda TLS, role göre kısıtlı erişim.

### 11. İş akışının üç aylık incelemesi

Her çeyrekte VKK şunları inceler:
- KPI trendleri;
- görülen yeni talep kategorileri;
- iş akışını etkileyen EDPB veya DM rehberlik değişiklikleri;
- kapsam manzarasını değiştiren yeni ürünler veya veri işleyenler;
- aynı sektördeki düzenleyici kararları;
- şikayetler veya DSR ile ilgili davalar.
