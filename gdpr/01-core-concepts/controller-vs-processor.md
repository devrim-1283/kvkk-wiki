---
Document / Doküman: Controller vs Processor — Roles, Joint Controllership, Article 28 Contracts / Veri Sorumlusu, Veri İşleyen — Roller, Müşterek Sorumluluk, Madde 28 Sözleşmeleri
Section / Bölüm: 01-core-concepts
Owner / Sahip: Data Protection Officer (DPO) / Veri Koruma Görevlisi
Approved by / Onaylayan: General Counsel / Genel Hukuk Müşaviri
Version / Versiyon: 1.0
Effective / Yürürlük: 2026-05-08
Review / Gözden Geçirme: Annual + triggered / Yıllık + tetiklenmiş
Legal Reference / İlgili Mevzuat: GDPR Art. 24, 26, 28, 29, 32; EDPB Guidelines 07/2020 on controller and processor; ECJ Fashion ID (C-40/17), Wirtschaftsakademie (C-210/16), Jehovan todistajat (C-25/17)
---

## English

### 1. Purpose

This document operationalizes Articles 24–28 GDPR. It explains how to determine whether the company acts as a controller, processor, or joint controller for each processing activity; what the contractual obligations are; how to manage sub-processors; and the consequences of getting it wrong. It is grounded in EDPB Guidelines 07/2020 on the concepts of controller and processor.

### 2. Why Roles Matter

The role determines who:

- Decides on lawful basis and purposes.
- Is the primary respondent to data subjects and supervisory authorities.
- Bears primary liability under Article 82 (with reverse claim rights between parties).
- Performs DPIAs.
- Concludes contracts and chooses processors.
- Maintains the ROPA under Article 30(1) (controller) or 30(2) (processor).

Mis-classification of role can lead to: unlawful processing; failure to provide appropriate notices and rights; flawed contracts; supervisory enforcement.

### 3. Controller — Article 4(7) and EDPB Guidance

A controller "determines the purposes and means" of processing. The test is functional, not formal — the label in a contract is not decisive (EDPB 07/2020).

Indicators of controllership:

- Determines **why** the processing happens (purpose).
- Determines **essential means**: which data, what duration, who has access, who receives the data.
- Has independent legal obligations triggering the processing (e.g., AML, tax, employment law).
- Has direct legal relationship with data subjects (employees, customers, candidates).
- Determines categories of data and data subjects.

Means may be split into:
- **Essential means** — always controller's prerogative.
- **Non-essential means** (technical implementation choices) — may be left to the processor.

### 4. Processor — Article 4(8)

A processor processes personal data on behalf of the controller, in accordance with controller's documented instructions (Art. 29).

Indicators of processor status:

- Acts only on the documented instructions of the controller.
- Has no independent purpose for the processing of the data.
- Provides a service whose object is processing personal data on someone else's behalf.

Examples: payroll provider, cloud hosting, email service, customer support outsourcer, marketing analytics tool configured to process only on instructions.

If the processor goes beyond instructions and determines purposes (Art. 28(10)), it becomes a controller for that processing — with full controller liability.

### 5. Joint Controllers — Article 26

Two or more controllers that **jointly determine** the purposes and means of processing are joint controllers. ECJ has interpreted joint controllership broadly:

- **Wirtschaftsakademie (C-210/16):** A Facebook fan-page operator is a joint controller with Meta because it influences the data processing through the page configuration.
- **Fashion ID (C-40/17):** A website embedding a Facebook "Like" button is a joint controller for the collection and transmission of personal data via the button.
- **Jehovan todistajat (C-25/17):** A religious community is a joint controller with its members' door-to-door note-taking.

Joint controllers must:

- Determine respective responsibilities by means of an arrangement (Art. 26(1)) — typically a written joint controller agreement.
- Make the essence of the arrangement available to data subjects (Art. 26(2)).
- Allow data subjects to exercise rights against either controller (Art. 26(3)).

### 6. Decision Tree — Role Determination

```
Does the entity determine the purposes of the processing?
        │
   Yes ─┼─► Does the entity also determine the essential means?
        │       │
        │   Yes ┼─► Is it acting independently of any other party?
        │       │       │
        │       │   Yes ─►  CONTROLLER (independent)
        │       │   No  ─►  Determine jointly with another?
        │       │              │
        │       │          Yes ─►  JOINT CONTROLLERS (Art. 26)
        │       │          No  ─►  CONTROLLER, with downstream processors
        │       │
        │   No ─►  Means delegated; determine if the delegate is a processor or another controller.
   No  ─┼─►  Is the entity processing on behalf of another, on instructions, with no own purposes?
        │       │
        │   Yes ─►  PROCESSOR (Art. 28). If exceeds instructions → CONTROLLER for that processing (Art. 28(10)).
        │   No  ─►  May be a "third party" recipient or another controller.
```

### 7. Article 28 Controller-Processor Contract — Mandatory Content

Each contract with a processor must, at minimum, include:

- Subject-matter and duration of processing.
- Nature and purpose of processing.
- Type of personal data and categories of data subjects.
- Obligations and rights of the controller.
- Processor commitments (Art. 28(3)(a)–(h)):
  - (a) Process only on documented instructions, including transfers, unless required by law to do otherwise.
  - (b) Ensure persons authorized to process are subject to confidentiality obligations.
  - (c) Take all measures required pursuant to Article 32 (security).
  - (d) Engage sub-processors only with prior specific or general authorization.
  - (e) Assist the controller in responding to data subject requests.
  - (f) Assist the controller with Art. 32–36 obligations (security, breach, DPIA).
  - (g) At controller's choice, delete or return all personal data after end of services.
  - (h) Make available all information necessary to demonstrate compliance and allow audits.

The contract must also specify:

- Sub-processor terms (back-to-back obligations under Art. 28(4)).
- Cross-border transfer mechanism (SCCs / BCRs / derogations).
- Notification obligations on breach (timing, scope).
- Indemnity and liability allocation (commercial; not strictly required by GDPR but standard practice).
- Audit rights.
- Data return / deletion certificate at termination.
- Insurance requirements (commercial standard).

### 8. Sub-processors

- General authorization: processor may engage sub-processors with general written authorization, subject to informing controller of intended changes and giving controller the opportunity to object.
- Specific authorization: processor must request approval per sub-processor.
- Whichever model, sub-processor must be bound by the same data protection obligations (Art. 28(4)) — usually via flow-down clauses.
- The processor remains fully liable to the controller for sub-processor performance.

### 9. Joint Controllership Arrangement — Mandatory Content (Art. 26)

- Identification of the joint controllers.
- Allocation of responsibilities for:
  - Information to data subjects (Art. 13/14).
  - Handling rights requests (Art. 15–22).
  - Security measures (Art. 32).
  - Breach notifications (Art. 33/34).
  - DPIAs (Art. 35).
  - Designating a contact point.
- Single point of contact for data subjects, while still allowing rights to be exercised against either controller (Art. 26(3)).
- Essence published in privacy notice and accessible to data subjects.

### 10. Common Joint Controllership Scenarios

| Scenario | Likely classification | Mitigation |
|---|---|---|
| Marketing co-promotion with partner sharing customer database | Joint controllers | Art. 26 arrangement before sharing. |
| Embedding third-party tracker on the website | Joint controllers for collection (Fashion ID) | Configure consent and document arrangement; consider alternatives. |
| Industry consortium pooling member data for benchmarking | Joint controllers | Detailed arrangement; data minimization; pseudonymization. |
| Vendor providing AI service that retrains on controller's data | Likely controller for retraining | Strict contract preventing retraining or treat as separate controller-controller flow. |
| Acquirer running due diligence using target's customer data | Two controllers (independent) for the purpose of due diligence | Confidentiality, minimization, data return on close/walk. |

### 11. Verification Workflow for New Vendors

```
1. Intake form completed by Business Unit (BU).
2. Data flow described in plain language: source, fields, frequency, retention.
3. DPO + GC + PROC classify role: processor / joint controller / independent controller.
4. If processor: Art. 28 contract drafted (use approved template).
   If joint controller: Art. 26 arrangement drafted.
   If independent controller: data sharing terms drafted; consider lawful basis.
5. Security DDQ completed by CISO; risk-rated.
6. Cross-border transfer mechanism evaluated.
7. ROPA updated with vendor entry.
8. Privacy notice updated if data subject categories change.
9. PGC approval if Class B+ per Committee Charter.
10. Contract signed; vendor onboarded; periodic review scheduled.
```

### 12. Liability Allocation (Art. 82)

- Controller is liable for damage caused by processing infringing GDPR.
- Processor is liable only where it has not complied with obligations specifically directed to processors or has acted outside or contrary to lawful instructions of the controller.
- Each is exempt if it proves it is not in any way responsible for the event giving rise to the damage.
- Joint controllers are jointly and severally liable to the data subject; recovery between them follows their arrangement.

### 13. Common Pitfalls

- Calling a vendor "data processor" in the contract while in practice the vendor uses the data for its own analytics — vendor becomes a controller.
- Skipping Art. 26 arrangement for joint controllers because there is "already a contract".
- General sub-processor authorization without an objection mechanism.
- Treating a parent or affiliate as a processor without considering whether it determines purposes for HR or marketing data.
- Forgetting that public authorities receiving data via legal instrument may not be "recipients" (Art. 4(9)).

---

## Türkçe

### 1. Amaç

Bu belge, GDPR Madde 24–28'i operasyonelleştirir. Şirketin her işleme faaliyeti için veri sorumlusu, işleyen veya müşterek veri sorumlusu olarak hareket edip etmediğinin nasıl belirleneceğini, sözleşmeden doğan yükümlülüklerin neler olduğunu, alt işleyenlerin nasıl yönetileceğini ve yanlış sınıflandırmanın sonuçlarını açıklar. Veri sorumlusu ve işleyen kavramlarına ilişkin EDPB 07/2020 Rehberine dayanır.

### 2. Rollerin Önemi

Rol, kimin şu konularda yetkili olduğunu belirler:

- Hukuki dayanak ve amaçlara karar verme.
- İlgili kişilere ve denetim makamlarına birinci derece muhatap olma.
- Madde 82 kapsamında birincil sorumluluk taşıma (taraflar arasında rücu hakları saklı).
- DPIA gerçekleştirme.
- Sözleşme akdetme ve işleyen seçme.
- Madde 30(1) (veri sorumlusu) veya 30(2) (işleyen) kapsamında ROPA tutma.

Rolün yanlış sınıflandırılması şunlara yol açabilir: hukuka aykırı işleme; uygun bildirim ve hakların sağlanmaması; kusurlu sözleşmeler; denetim makamı yaptırımı.

### 3. Veri Sorumlusu — Madde 4(7) ve EDPB Rehberi

Veri sorumlusu, işlemenin "amaçlarını ve araçlarını belirler". Test fonksiyoneldir, biçimsel değil — sözleşmedeki etiket belirleyici değildir (EDPB 07/2020).

Veri sorumluluğu göstergeleri:

- İşlemenin **neden** gerçekleştiğini (amaç) belirler.
- **Esas araçları** belirler: hangi veriler, ne kadar süre, kimin erişeceği, kimin alacağı.
- İşlemeyi tetikleyen bağımsız hukuki yükümlülükleri vardır (örn. AML, vergi, iş hukuku).
- İlgili kişilerle (çalışanlar, müşteriler, adaylar) doğrudan hukuki ilişki vardır.
- Veri ve ilgili kişi kategorilerini belirler.

Araçlar şu şekilde ayrılabilir:
- **Esas araçlar** — daima veri sorumlusunun yetkisindedir.
- **Esas olmayan araçlar** (teknik uygulama tercihleri) — işleyene bırakılabilir.

### 4. Veri İşleyen — Madde 4(8)

Veri işleyen, veri sorumlusunun belgelenmiş talimatları doğrultusunda (Md. 29), veri sorumlusu adına kişisel veri işler.

İşleyen statüsünün göstergeleri:

- Yalnızca veri sorumlusunun belgelenmiş talimatları doğrultusunda hareket eder.
- Verinin işlenmesi için bağımsız bir amacı yoktur.
- Konusu başka biri adına kişisel veri işlemek olan bir hizmet sunar.

Örnekler: bordro sağlayıcısı, bulut barındırma, e-posta hizmeti, müşteri destek dış kaynağı, yalnızca talimat üzerine işlenecek şekilde yapılandırılmış pazarlama analitiği aracı.

İşleyen, talimatların ötesine geçer ve amaçları belirlerse (Md. 28(10)), o işleme için tam sorumlu konuma geçen veri sorumlusu hâline gelir.

### 5. Müşterek Veri Sorumluları — Madde 26

İşleme amaçlarını ve araçlarını **birlikte belirleyen** iki veya daha fazla veri sorumlusu müşterek veri sorumlusudur. ABAD müşterek sorumluluğu geniş yorumladı:

- **Wirtschaftsakademie (C-210/16):** Bir Facebook hayran sayfası işletmecisi, sayfa yapılandırması yoluyla veri işlemeyi etkilediği için Meta ile müşterek veri sorumlusudur.
- **Fashion ID (C-40/17):** Bir Facebook "Beğen" düğmesini gömen web sitesi, düğme aracılığıyla kişisel verilerin toplanması ve iletilmesi konusunda müşterek veri sorumlusudur.
- **Jehovan todistajat (C-25/17):** Bir dini topluluk, üyelerinin kapı kapı not tutmasıyla müşterek veri sorumlusudur.

Müşterek veri sorumluları:

- Bir düzenleme aracılığıyla sorumluluklarını belirlemelidir (Md. 26(1)) — genellikle yazılı bir müşterek sorumluluk anlaşması.
- Düzenlemenin esasını ilgili kişilerin erişimine sunmalıdır (Md. 26(2)).
- İlgili kişilerin haklarını her iki veri sorumlusuna karşı kullanmalarına izin vermelidir (Md. 26(3)).

### 6. Karar Ağacı — Rol Belirleme

```
Şirket işleme amaçlarını belirliyor mu?
        │
  Evet ─┼─► Esas araçları da belirliyor mu?
        │       │
        │  Evet ┼─► Başka bir taraftan bağımsız mı hareket ediyor?
        │       │       │
        │       │   Evet ─►  VERİ SORUMLUSU (bağımsız)
        │       │   Hayır ─►  Başka biriyle birlikte mi belirliyor?
        │       │              │
        │       │         Evet ─►  MÜŞTEREK VERİ SORUMLULARI (Md. 26)
        │       │         Hayır ─►  VERİ SORUMLUSU, alt işleyenlerle
        │       │
        │  Hayır ─►  Araçlar devredilmiş; devralan bir işleyen mi yoksa başka bir veri sorumlusu mu?
  Hayır ┼─►  Şirket, talimatlar üzerine başka biri adına, kendi amacı olmadan mı işliyor?
        │       │
        │   Evet ─►  VERİ İŞLEYEN (Md. 28). Talimatları aşarsa → o işleme için VERİ SORUMLUSU (Md. 28(10)).
        │   Hayır ─►  "Üçüncü taraf" alıcı veya başka bir veri sorumlusu olabilir.
```

### 7. Madde 28 Veri Sorumlusu-İşleyen Sözleşmesi — Zorunlu İçerik

İşleyenle yapılan her sözleşme asgari olarak şunları içermelidir:

- İşlemenin konusu ve süresi.
- İşlemenin niteliği ve amacı.
- Kişisel veri türü ve ilgili kişi kategorileri.
- Veri sorumlusunun yükümlülükleri ve hakları.
- İşleyen taahhütleri (Md. 28(3)(a)–(h)):
  - (a) Aktarımlar dahil yalnızca belgelenmiş talimatlar üzerine işleme; hukuken aksi gerekmedikçe.
  - (b) İşleme yetkisi olan kişilerin gizlilik yükümlülüklerine tabi olmasını sağlama.
  - (c) Madde 32 uyarınca gerekli tüm güvenlik tedbirlerini alma.
  - (d) Önceden özel veya genel yetkilendirme olmadan alt işleyen kullanmama.
  - (e) İlgili kişi başvurularına yanıt verirken veri sorumlusuna yardım etme.
  - (f) Md. 32–36 yükümlülüklerinde (güvenlik, ihlal, DPIA) veri sorumlusuna yardım etme.
  - (g) Hizmetlerin sona ermesinden sonra veri sorumlusunun seçimine göre tüm kişisel verileri silme veya iade etme.
  - (h) Uyumu kanıtlamak için gerekli tüm bilgileri sağlama ve denetim olanağı tanıma.

Sözleşme ayrıca şunları belirtmelidir:

- Alt işleyen koşulları (Md. 28(4) kapsamında zincirleme yükümlülükler).
- Sınır ötesi aktarım mekanizması (SCC / BCR / istisnalar).
- İhlal durumunda bildirim yükümlülükleri (zaman, kapsam).
- Tazminat ve sorumluluk dağılımı (ticari; GDPR'da kesin zorunlu değildir ama standart uygulamadır).
- Denetim hakları.
- Sona ermede veri iade / silme sertifikası.
- Sigorta gereklilikleri (ticari standart).

### 8. Alt İşleyenler

- Genel yetkilendirme: işleyen, planlanan değişiklikleri veri sorumlusuna bildirmesi ve veri sorumlusuna itiraz fırsatı tanıması koşuluyla genel yazılı yetkiyle alt işleyen kullanabilir.
- Özel yetkilendirme: işleyen, alt işleyen başına onay talep etmelidir.
- Hangi model olursa olsun, alt işleyen aynı veri koruma yükümlülüklerine bağlı tutulmalıdır (Md. 28(4)) — genellikle aktarılan hükümlerle.
- İşleyen, alt işleyen performansı için veri sorumlusuna karşı tam sorumlu kalır.

### 9. Müşterek Sorumluluk Düzenlemesi — Zorunlu İçerik (Md. 26)

- Müşterek veri sorumlularının tanımlanması.
- Şu sorumlulukların paylaşılması:
  - İlgili kişilere bilgi verme (Md. 13/14).
  - Hak başvurularını yönetme (Md. 15–22).
  - Güvenlik tedbirleri (Md. 32).
  - İhlal bildirimleri (Md. 33/34).
  - DPIA'lar (Md. 35).
  - İrtibat noktası belirleme.
- İlgili kişiler için tek bir irtibat noktası, ancak hakların her iki veri sorumlusuna karşı kullanılabilmesi (Md. 26(3)).
- Esas, aydınlatma metninde yayımlanır ve ilgili kişilerin erişimine açıktır.

### 10. Yaygın Müşterek Sorumluluk Senaryoları

| Senaryo | Olası sınıflandırma | Önlem |
|---|---|---|
| Müşteri veritabanını paylaşan ortakla pazarlama ortak tanıtımı | Müşterek veri sorumluları | Paylaşım öncesi Md. 26 düzenlemesi. |
| Web sitesine üçüncü taraf izleyici gömme | Toplama için müşterek veri sorumluları (Fashion ID) | Rıza yapılandırılır ve düzenleme belgelenir; alternatifler değerlendirilir. |
| Üye verilerini kıyaslama için bir araya getiren sektör konsorsiyumu | Müşterek veri sorumluları | Ayrıntılı düzenleme; veri minimizasyonu; takma adlandırma. |
| Veri sorumlusunun verisiyle yeniden eğitilen AI hizmeti sağlayan tedarikçi | Yeniden eğitim için olası veri sorumlusu | Yeniden eğitimi engelleyen sıkı sözleşme veya ayrı veri sorumlusu-veri sorumlusu akışı. |
| Hedefin müşteri verisi ile durum tespiti yapan satın alıcı | İki veri sorumlusu (bağımsız) durum tespiti amacıyla | Gizlilik, minimizasyon, kapanış/vazgeçme durumunda veri iadesi. |

### 11. Yeni Tedarikçiler için Doğrulama İş Akışı

```
1. İş Birimi (İB) tarafından giriş formu doldurulur.
2. Veri akışı sade dille tanımlanır: kaynak, alanlar, sıklık, saklama.
3. VKG + GHM + SAT rolü sınıflandırır: işleyen / müşterek veri sorumlusu / bağımsız veri sorumlusu.
4. İşleyen ise: Md. 28 sözleşmesi hazırlanır (onaylı şablon).
   Müşterek veri sorumlusu ise: Md. 26 düzenlemesi hazırlanır.
   Bağımsız veri sorumlusu ise: veri paylaşım koşulları hazırlanır; hukuki dayanak değerlendirilir.
5. CISO tarafından güvenlik DDQ tamamlanır; risk derecelendirilir.
6. Sınır ötesi aktarım mekanizması değerlendirilir.
7. ROPA, tedarikçi kaydıyla güncellenir.
8. İlgili kişi kategorileri değişiyorsa aydınlatma metni güncellenir.
9. Komite Tüzüğüne göre B+ sınıfı ise GYK onayı.
10. Sözleşme imzalanır; tedarikçi onboarding edilir; periyodik inceleme planlanır.
```

### 12. Sorumluluk Dağılımı (Md. 82)

- Veri sorumlusu, GDPR'ı ihlal eden işlemenin yol açtığı zarardan sorumludur.
- İşleyen, yalnızca özellikle işleyenlere yönelik yükümlülüklere uymadığında veya veri sorumlusunun yasal talimatlarının dışında ya da aksine hareket ettiğinde sorumludur.
- Her biri, zarara yol açan olayda hiçbir şekilde sorumlu olmadığını kanıtlarsa muaftır.
- Müşterek veri sorumluları, ilgili kişiye karşı müştereken ve müteselsilen sorumludur; aralarındaki rücu düzenlemeyi takip eder.

### 13. Sık Karşılaşılan Tuzaklar

- Sözleşmede bir tedarikçiyi "veri işleyen" olarak adlandırmak ama uygulamada tedarikçinin veriyi kendi analitiği için kullanması — tedarikçi veri sorumlusu hâline gelir.
- "Zaten sözleşme var" diye müşterek veri sorumluları için Md. 26 düzenlemesini atlamak.
- İtiraz mekanizması olmaksızın genel alt işleyen yetkilendirmesi.
- Bir ana şirketi veya iştiraki, İK veya pazarlama verileri için amaçları belirleyip belirlemediğine bakmadan işleyen olarak kabul etmek.
- Yasal araç yoluyla veri alan kamu kurumlarının "alıcı" olmayabileceğini unutmak (Md. 4(9)).
