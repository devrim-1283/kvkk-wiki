---
Doküman / Document: 72 Saat Kurul Bildirimi ve İlgili Kişi Bildirimi / 72-Hour Notification to the Authority and Data Subject Notification
Bölüm / Section: 08-ihlal-yonetimi
Sahip / Owner: KVKK Sorumlusu / KVKK Officer
Onaylayan / Approved by: Hukuk Müdürü + KVKK Komitesi / Head of Legal + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + Kurul kararı değişikliklerinde / Annual + when Authority decisions change
İlgili Mevzuat / Legal Reference: Law No. 6698 (KVKK) Art. 12(5); Authority Decision No. 2019/10 dated 24.01.2019 on "Procedures and Principles of Personal Data Breach Notification"; Authority Decision No. 2019/271 dated 18.09.2019 (foreign-resident data controller); KVKK Data Security Guide (2018); GDPR Art. 33-34 (comparative reference)
---

## English

# 72-Hour Personal Data Breach Notification Obligation

## 1. Legal Framework

### 1.1. Statutory Provision

**Law No. 6698 (KVKK), Art. 12(5):**
> "If the personal data being processed is unlawfully obtained by others, the data controller shall **notify** this situation to the data subject and to the Authority **at the earliest opportunity**."

### 1.2. Authority Decision

**Authority Decision No. 2019/10 dated 24.01.2019:** "At the earliest opportunity" is set as 72 hours.
> "In the event of a personal data breach, the data controller shall notify the Authority **without undue delay and at the latest within 72 hours from the moment of becoming aware**. If the notification cannot be made within 72 hours, the reasons for the delay shall be explained in the notification submitted to the Authority."

Notification to data subjects: **"within a reasonable time at the earliest opportunity, directly to the data subject's contact details if reachable, or, if not reachable, by appropriate means such as publishing on the data controller's own website for **at least 24 hours**."**

### 1.3. Notification Threshold

According to the Authority's decision, a **personal data breach** includes:

- Unauthorized access,
- Unlawful disclosure / transfer,
- Unauthorized alteration,
- Loss / destruction,
- Unauthorized deletion.

The notification threshold is exceeded if **any** of the above has occurred or there is a **reasonable likelihood** that it has occurred.

## 2. The 72-Hour Clock: "Awareness Moment"

### 2.1. When Does the Clock Start?

The clock starts at the moment of **"reasonable awareness"**. The progression:

| Stage | Clock status |
|-------|--------------|
| Abstract suspicion (anomalous log) | Not started |
| Automated alert (SIEM/EDR/DLP) | Not started - analysis required |
| Initial technical analysis: impact on personal data confirmed likely | **Starts** |
| Full scope and count determined | Already running |

**Practical rule:** When the Incident Commander + KVKK Officer + CISO trio jointly reach the conclusion "personal data may have been affected," that moment is recorded with minute-level precision in the incident log. **That moment = T+0**.

### 2.2. What if the Clock Starts on a Weekend / Holiday?

Holidays/weekends do **not** stop the clock. The KVKK Officer must be reachable 24/7. Notification is sent to the Authority via KEP, which works around the clock.

### 2.3. Can the Clock Be Rolled Back?

No. A post-notification finding that "we actually knew earlier" cannot reset the clock; on the contrary, it constitutes a late-notification breach. Hence the **internal suspicion -> breach assessment window must be kept under 24 hours**.

## 3. Notification Method to the Authority

### 3.1. Channel

- Primary: **"Personal Data Breach Notification Form"** on the Authority's website (ihlalbildirim.kvkk.gov.tr - sign-in via VERBİS).
- Backup: KEP - **kvkk@hs01.kep.tr**.

### 3.2. Who May Submit the Notification?

- The data controller (authorized signatory).
- The **contact person** registered with VERBİS.
- For data controllers established outside Türkiye, the **data controller representative**.

### 3.3. Form Completion

The Authority's form is on the KVKK website. The fillable version we use is in `ihlal-bildirim-formu.md`.

## 4. Notification Form Content (Authority Decision 2019/10)

| Section | Minimum Content |
|---------|-----------------|
| 1. Data controller identity | Trade name, tax ID, contact person, KEP |
| 2. Breach summary | What happened, when, where, who became aware |
| 3. Breach nature | Confidentiality / integrity / availability |
| 4. Breach category | Cyberattack, insider, loss, third party, physical |
| 5. Number of data subjects affected | Estimated + final (separate rows) |
| 6. Number of records affected | May exceed number of subjects |
| 7. Affected personal data categories | General + special category separately |
| 8. Likely consequences | Material/non-material harm, fraud risk, identity theft |
| 9. Measures taken | Technical + administrative, with hourly chronology |
| 10. Recommended measures | Advice for data subjects (passwords, card cancellation) |
| 11. Contact person | Name, title, phone, e-mail |
| 12. Annexes | Forensic summary (if any), draft communication text |

## 5. Phased / Partial Notification Right

The Authority's decision accepts **phased notification** when full information cannot be provided within 72 hours:

| Phase | Time | Content |
|-------|------|---------|
| First notification | T+72 hours | Available information + "further information will follow" note |
| Supplementary notification 1 | T+5-10 days | Scope expansion/narrowing |
| Supplementary notification 2 | T+15 days | Root cause, durable measures taken |
| Final report | T+30-60 days | RCA, CAPA, finalized scope |

**Critical:** Phased notification does **not** mean filing an empty form. The first notification must be **substantively filled** at the available information level and **updated** later.

## 6. Notification to Data Subjects

### 6.1. Scope

When is data subject notification mandatory?

- When the breach may affect the **fundamental rights and freedoms** or **material/non-material assets** of the individual.
- In practice: the Authority expects data subject notification in all reported breaches; exemption is interpreted **narrowly**.

### 6.2. Method

Per the Authority's decision:

1. **Direct notification:** to the data subject's notified contact details (e-mail, SMS, KEP, physical address).
2. **General notification (fallback):** if there is no contact address, or for very large-scale breaches, publication on the data controller's **website for at least 24 hours**.

Our preference: **dual channel** - primary contact address + website banner. SMS provides especially fast reach.

### 6.3. Data Subject Notification Content

The notification text must include the following elements in **plain language**:

- Nature of the breach (e.g., "an unauthorized third party accessed certain information in our customer database").
- Affected data categories (e.g., "name-surname, e-mail, customer number - your card information **was not affected**").
- Likely consequences (e.g., "you may receive phishing attempts").
- Measures taken (e.g., "the attack has been stopped; the system is secured").
- Measures the data subject can take (e.g., "do not open suspicious e-mails, change your password").
- KVKK Officer contact information (e-mail + telephone).
- Reference to KVKK Article 11 rights.

### 6.4. Timing

Data subject notification is made within a **"reasonable time at the earliest opportunity"**. Practical standard: **within 5 business days after the Authority notification**. Late notification is grounds for additional sanction by the Authority.

### 6.5. Templates

For ready text templates see `99-sablonlar/ihlal-iletisim/` (e-mail, 160-character SMS, web banner, press statement).

## 7. Foreign-Resident Data Controller

Authority Decision No. 2019/271 of 18.09.2019:

- A data controller resident outside Türkiye fulfills the breach notification obligation through its **Türkiye data controller representative**.
- The representative must be registered with VERBİS.
- The 72-hour clock for the representative begins at the **awareness moment in Türkiye** - time spent at headquarters abroad is not accepted as an excuse by the Authority.
- The contract must require the foreign headquarters to inform the representative **within 24 hours**.

## 8. Late Notification by the Processor

KVKK Art. 12(2): The processor cannot process beyond the controller's instructions and is **jointly responsible** for required security measures.

Scenario: A cloud provider (processor) notifies our company of a breach 5 days late.

| Question | Answer |
|----------|--------|
| When does the 72-hour clock start? | The day our company (the controller) becomes aware (day 5). |
| Is 5+3=8 total days a problem? | From our company's perspective, the notification SLA was met (3 days); however, the Authority may apply additional sanctions on the basis that the **controller's contractual and technical control over the processor is inadequate**. |
| What should the contract say? | "The processor shall notify the controller via KEP **within 24 hours** of becoming aware of the breach" + delay penalty. |
| What goes in the breach notification? | "The breach occurred at processor X; we were notified on date Y; contractual sanction Z has been initiated." The Authority wants to see this. |

## 9. Breach After Cross-Border Transfer

If data is breached in the recipient country after a cross-border transfer (recipient = foreign processor or controller):

- Our company still notifies the Authority **as data controller**.
- Notification clauses in Standard Contract or BCRs are activated.
- Foreign DPA notification (GDPR Art. 33) is made separately if required.
- The lawful basis for the transfer (adequacy decision / Standard Contract / explicit consent) is explained to the Authority.

## 10. Administrative Sanction (Failure to Notify)

KVKK Art. 18(1)(b): Violations of data security obligations -> **administrative fine**.

| Year | Lower bound (TRY) | Upper bound (TRY) |
|------|-------------------|-------------------|
| 2026 (annually updated by the Authority) | Check the Authority's page for the current schedule | - |

> **Note:** Amounts are increased annually by the revaluation rate. This document references the current figure via `12-mevzuat-arsiv/idari-para-cezalari.md`.

Late notification is also an **aggravating factor**; in repeat breaches the upper bound is applied.

## 11. Common Mistakes and How to Avoid Them

| Mistake | Correct approach |
|---------|------------------|
| "We're not sure yet, let's wait a bit longer" | If breach **likelihood** is high, notify within 72 hours - missing details can be supplemented. |
| Trying to fill all form fields and missing the deadline | First notification is filed with **available information** + "further information to follow". |
| Postponement on weekends / holidays | KVKK Officer is on 24/7 duty - the clock does not stop. |
| Skipping data subject notification | Authority exemption is narrow; omission is grounds for sanction. |
| Technical jargon in data subject text | Data subject text in B1-level Turkish - clear, brief. |
| Publishing tactical attacker hints | Do not publish technical detail without Legal + Communications approval. |
| Missing the clock while waiting for processor notification | Contractual 24-hour clause + internal trigger mechanism. |
| Single-notification = single-incident fallacy | If the same attacker caused multiple breaches, **each one is a separate notification**. |
| Treating it as a unit-level matter (only IT sees) | KVKK Officer + Legal + Board escalation is unavoidable. |
| Silence after notification | Supplementary notifications + RCA + CAPA are Authority expectations. |

## 12. Post-Notification Process with the Authority

| Stage | Time | Content |
|-------|------|---------|
| 1. Notification confirmation | 1-7 business days | Reference number from the Authority |
| 2. Request for further information | 15 days | Authority may ask follow-up questions |
| 3. On-site inspection | Variable | Authority experts may visit |
| 4. Authority decision | 3-12 months | Administrative sanction or warning |
| 5. Administrative fine | At decision date | Payment within 30 days from notification |
| 6. Administrative judicial appeal | 60 days | Administrative Court |

## 13. Internal Escalation Table (Internal Decision Authorities)

| Decision | Authority |
|----------|-----------|
| File a notification with the Authority | KVKK Officer (with Legal + CISO concurrence) |
| Approve data subject notification text | Head of Legal + Corporate Communications |
| Press statement | CEO + Director of Corporate Communications |
| Activate insurance policy | CFO + Legal |
| Decision not to pay ransom | Board (per pre-defined policy) |
| Termination of processor contract | CEO + Legal + KVKK Committee |

## 14. Records and Archive

All correspondence around and after notification:

- Recorded chronologically in the **Authority Correspondence Log**.
- KEP evidence chain copied to insured archive.
- Retention period: **10 years** (statute of limitations + archive legislation).
- Access limited to KVKK Committee and assigned Legal personnel.

## 15. Version History

| Version | Date | Change | Approval |
|---------|------|--------|----------|
| 1.0 | 2026-05-08 | First publication | KVKK Committee |

---

## Türkçe

# 72 Saat İhlal Bildirim Yükümlülüğü

## 1. Yasal Çerçeve

### 1.1. Kanun Hükmü

**6698 sayılı KVKK m.12/5:**
> "İşlenen kişisel verilerin kanuni olmayan yollarla başkaları tarafından elde edilmesi hâlinde, veri sorumlusu **bu durumu en kısa sürede** ilgilisine ve Kurula bildirir."

### 1.2. Kurul Kararı

**KVKKK 24.01.2019 tarih ve 2019/10 sayılı Kararı:** "En kısa süre" 72 saat olarak belirlenmiştir.
> "Kişisel veri ihlali halinde veri sorumlusu **bu durumu öğrendiği tarihten itibaren gecikmeksizin ve en geç 72 saat içinde** Kurula bildirir. Söz konusu bildirimin 72 saat içinde yapılamaması halinde gecikmenin sebepleri Kurula yapılacak bildirimde açıklanır."

İlgili kişiye bildirim ise: **"makul olan en kısa süre içinde, ilgili kişinin iletişim adresine ulaşılabiliyorsa doğrudan, ulaşılamıyorsa veri sorumlusunun kendi web sitesinde **en az 24 saat** süreyle yayımlanması gibi uygun yöntemlerle"** yapılır.

### 1.3. Bildirim Eşiği

Kurul kararına göre **kişisel veri ihlali**:
- Yetkisiz erişim,
- Hukuka aykırı ifşa / aktarım,
- Yetkisiz değiştirme,
- Kayıp / yok olma,
- Yetkisiz silme.

Yukarıdaki durumlardan **biri gerçekleştiyse** veya **gerçekleşme makul ihtimali varsa** bildirim eşiği aşılmıştır.

## 2. 72 Saat Sayacı: "Öğrenme Anı" Tanımı

### 2.1. Sayaç Ne Zaman Başlar?

Sayaç **"makul ölçüde haberdar olma"** anında başlar. Sıralama:

| Aşama | Sayaç durumu |
|-------|--------------|
| Soyut şüphe (anormal log) | Başlamaz |
| Otomatik alarm (SIEM/EDR/DLP) | Başlamaz — analiz gerekir |
| İlk teknik analiz: kişisel veriye etki ihtimali doğrulandı | **Başlar** |
| Tam kapsam ve sayım belirlendi | Sayaç çoktan başlamış olur |

**Pratik kural:** Olay Komutanı + KVKK Sorumlusu + CISO üçlüsünün birlikte "kişisel veri etkilenmiş olabilir" kanaatine ulaştığı an dakika hassasiyetiyle olay log'una düşer. **Bu an = T+0**.

### 2.2. Sayaç Bir Hafta Sonu / Tatil İçinde Başlarsa?

Tatil/hafta sonu **sayacı durdurmaz**. KVKK Sorumlusu 7/24 ulaşılabilir olmak zorundadır. Bildirim Kurul'a KEP ile yapıldığı için zaman bağımsız çalışır.

### 2.3. Sayaç Geriye Sarılabilir mi?

Hayır. Bildirim sonrası tespit edilen "aslında daha önce öğrenmiştik" durumu zamanaşımını geri almaz; aksine geç bildirim ihlali oluşturur. Bu nedenle **iç şüphe → ihlal değerlendirmesi süresi 24 saatten kısa** tutulmalıdır.

## 3. Kurul'a Bildirim Yöntemi

### 3.1. Kanal

- Birincil: **Kurum web sitesi üzerindeki "Veri İhlal Bildirim Formu"** (ihlalbildirim.kvkk.gov.tr — VERBİS girişi ile).
- Yedek: KEP — **kvkk@hs01.kep.tr**.

### 3.2. Kim Bildirim Yapabilir?

- Veri sorumlusu (yetkili imza yetkilisi).
- Sicile bildirilen **irtibat kişisi**.
- Yurt dışında yerleşik veri sorumlusu için **veri sorumlusu temsilcisi**.

### 3.3. Form Doldurma

Kurul formu KVKK web sitesinde mevcuttur. Şirketimizin kullanacağı doldurulabilir versiyon: bkz. `ihlal-bildirim-formu.md`.

## 4. Bildirim Formu İçeriği (Kurul 2019/10 Kararı)

| Bölüm | Asgari İçerik |
|-------|---------------|
| 1. Veri sorumlusu kimlik | Unvan, VKN, irtibat kişisi, KEP |
| 2. İhlal özeti | Ne oldu, ne zaman, nerede, kim öğrendi |
| 3. İhlal niteliği | Gizlilik / bütünlük / erişilebilirlik |
| 4. İhlal kategorisi | Siber saldırı, içeriden, kayıp, üçüncü taraf, fiziksel |
| 5. Etkilenen veri konusu kişi sayısı | Tahmini + nihai (ayrı satır) |
| 6. Etkilenen kayıt sayısı | Veri konusu kişi sayısından fazla olabilir |
| 7. Etkilenen kişisel veri kategorisi | Genel + özel nitelikli ayrı |
| 8. Olası sonuçlar | Maddi/manevi zarar, dolandırıcılık riski, kimlik hırsızlığı |
| 9. Alınan önlemler | Teknik + idari, saatlik kronoloji |
| 10. Önerilen önlemler | İlgili kişiye yönelik tavsiyeler (parola, kart iptali) |
| 11. İrtibat kişisi | Ad, ünvan, telefon, e-posta |
| 12. Ekler | Forensik özet (varsa), iletişim metni taslağı |

## 5. Aşamalı / Kısmi Bildirim Hakkı

Kurul kararı, tam bilginin 72 saatte mümkün olmaması halinde **aşamalı bildirimi** kabul eder:

| Aşama | Süre | İçerik |
|-------|------|--------|
| İlk bildirim | T+72 saat | Eldeki bilgi + "ek bilgi gönderilecek" notu |
| Tamamlayıcı bildirim 1 | T+5 - 10 gün | Kapsam genişletme/daraltma |
| Tamamlayıcı bildirim 2 | T+15 gün | Kök neden, alınan kalıcı önlemler |
| Nihai rapor | T+30-60 gün | RCA, CAPA, sonuçlanmış kapsam |

**Kritik:** Aşamalı bildirim, **eksik form gönderme** anlamına gelmez. İlk bildirim mevcut bilgi seviyesinde **dolu** olmalı; sonradan **güncellenir**.

## 6. İlgili Kişiye Bildirim

### 6.1. Kapsam

Ne zaman ilgili kişiye bildirim zorunludur?
- Kişisel veri ihlali kişinin **temel hak ve özgürlüklerini** veya **maddi/manevi varlığını** etkileyebileceği zaman.
- Pratikte: tüm bildirilmiş ihlallerde ilgili kişi bildirimi yapılması Kurul'un beklentisidir; muafiyet **çok dar** yorumlanır.

### 6.2. Yöntem

Kurul kararına göre:
1. **Doğrudan bildirim:** İlgili kişinin bildirilmiş iletişim adresine (e-posta, SMS, KEP, fiziksel adres).
2. **Genel bildirim (yedek):** İletişim adresi yoksa veya çok büyük çaplı ihlal söz konusuysa, veri sorumlusunun **web sitesinde en az 24 saat** süreyle yayımlama.

Şirketimizin tercihi: **çift kanal** — birincil iletişim adresi + web sitesi banner. SMS özellikle hızlı ulaşım sağlar.

### 6.3. İlgili Kişi Bildirim İçeriği

Bildirim metni şu unsurları **anlaşılır dilde** içermelidir:
- İhlalin niteliği (örn. "yetkisiz üçüncü taraf, müşteri veri tabanımızdaki bazı bilgilere erişim sağlamıştır").
- Etkilenmiş veri kategorisi (örn. "ad-soyad, e-posta, müşteri numarası — kart bilgileriniz **etkilenmemiştir**").
- Olası sonuçlar (örn. "phishing girişimi gelebilir").
- Alınan önlemler (örn. "saldırı durdurulmuştur, sistem güvence altına alınmıştır").
- İlgili kişinin alabileceği önlemler (örn. "şüpheli e-posta açmayın, parolanızı değiştirin").
- KVKK Sorumlusu iletişim bilgisi (e-posta + telefon).
- 11. madde haklarına atıf.

### 6.4. Süre

İlgili kişi bildirimi **"makul olan en kısa süre"** içinde yapılır. Pratik standart: **Kurul bildiriminden sonraki 5 iş günü içinde**. Geç bildirim Kurul tarafından ek yaptırım sebebidir.

### 6.5. Şablonlar

Hazır metin şablonları için bkz. `99-sablonlar/ihlal-iletisim/` (e-posta, SMS 160 karakter, web banner, basın açıklaması).

## 7. Yurt Dışında Yerleşik Veri Sorumlusu

KVKKK 18.09.2019 tarih 2019/271 sayılı Kararı:
- Yurt dışında yerleşik veri sorumlusunun **Türkiye'deki veri sorumlusu temsilcisi** ihlal bildirim yükümlülüğünü yerine getirir.
- Temsilci VERBİS'e kayıtlı olmalıdır.
- Temsilci için 72 saat sayacı **Türkiye'de** öğrenme anından başlar — yurt dışı merkezde geçen süre Kurul tarafından mazeret sayılmaz.
- Sözleşmesel olarak yurt dışı merkezin temsilciyi **24 saat içinde** haberdar etmesi şart koşulmalıdır.

## 8. Veri İşleyenin Geç Bildirimi

KVKK m.12/2: Veri işleyen, veri sorumlusunun talimatları dışında işleyemez ve **gerekli güvenlik tedbirlerinden müştereken sorumludur**.

Senaryo: Bulut sağlayıcı (veri işleyen) ihlali Şirketimize 5 gün sonra bildirir.

| Soru | Cevap |
|------|-------|
| 72 saat ne zaman başlar? | Şirketimizin (veri sorumlusunun) öğrendiği gün (5. gün). |
| Toplam 5+3 = 8 gün geçmesi sorun mu? | Şirketimiz açısından bildirim süresine uydu (3 gün); ancak Kurul, **veri sorumlusunun veri işleyen üzerindeki sözleşmesel ve teknik kontrolünü yetersiz bularak** ek yaptırım uygulayabilir. |
| Sözleşmede ne olmalı? | "Veri işleyen, ihlali öğrendiği andan itibaren **24 saat içinde** veri sorumlusuna KEP ile bildirir" + gecikme cezası. |
| İhlal bildiriminde ne yazılır? | "İhlal veri işleyen X firmasında gerçekleşmiş, tarafımıza Y tarihinde bildirilmiş, Z sözleşmesel yaptırım başlatılmıştır." Kurul bunu görmek ister. |

## 9. Yurt Dışı Aktarım Sonrası İhlal

Veri yurt dışı aktarımdan sonra etkilenen ülkede ihlale uğrarsa (alıcı = yurt dışı işleyen veya alıcı veri sorumlusu):
- Şirketimiz hâlâ **veri sorumlusu** sıfatıyla Kurul'a bildirir.
- Standart Sözleşme veya bağlayıcı şirket kuralları çerçevesindeki bildirim klozları devreye girer.
- Yurt dışı DPA bildirimi (GDPR m.33) ayrıca yapılır gerekirse.
- Aktarım hukuki sebebi (Yeterlilik kararı / Standart Sözleşme / Açık rıza) Kurul'a açıklanır.

## 10. İdari Yaptırım (Bildirim Yükümlülüğü İhlali)

KVKK m.18/1-b: Veri güvenliği ile ilgili yükümlülüklere aykırılık → **idari para cezası**.

| Yıl | Alt sınır (TL) | Üst sınır (TL) |
|-----|----------------|----------------|
| 2026 (her yıl Kurul güncellemesi) | Yıllık güncel tarife için Kurum sayfası kontrol | — |

> **Not:** Tutarlar her yıl yeniden değerleme oranıyla artırılır. Bu doküman güncel rakamı `12-mevzuat-arsiv/idari-para-cezalari.md` üzerinden referanslar.

Geç bildirim ayrıca **ağırlaştırıcı sebep**tir; mükerrer ihlalde ceza tavandan kesilir.

## 11. Tipik Hatalar ve Kaçınma

| Hata | Doğru yaklaşım |
|------|----------------|
| "Henüz emin değiliz, biraz daha bekleyelim" | İhlal **olasılığı** yüksekse 72 saat içinde bildirim — eksik bilgi tamamlanır. |
| Tüm form alanlarını doldurmaya çalışıp süreyi geçirmek | İlk bildirim **eldeki bilgi** ile yapılır; "ek bilgi gönderilecektir" notu düşülür. |
| Hafta sonu/bayramda erteleme | KVKK Sorumlusu 7/24 nöbet — sayaç durmaz. |
| İlgili kişiye bildirim atlama | Kurul muafiyeti çok dar; eksiltme ek yaptırım sebebi. |
| Bildirim metninde teknik jargon | İlgili kişi metni B1 seviye Türkçe — net, kısa. |
| Saldırgan iletişim ipuçlarını yayınlama | Hukuk + iletişim onayı olmadan teknik detay paylaşma. |
| Veri işleyenden bildirim beklerken sayacı kaçırma | Sözleşmesel 24 saat klozu + iç tetikleme mekanizması. |
| Tek bildirim → tek olay yanılgısı | Aynı saldırgan birden çok ihlal yapmışsa **her biri ayrı bildirim**. |
| Birim bildirimi (sadece IT görsün) | KVKK Sorumlusu + Hukuk + Yönetim Kurulu eskalasyonu kaçınılmaz. |
| Bildirim sonrası sessizlik | Tamamlayıcı bildirimler + RCA + CAPA Kurul beklentisi. |

## 12. Kurul Bildirim Sonrası Süreç

| Aşama | Süre | İçerik |
|-------|------|--------|
| 1. Bildirim onayı | 1-7 iş günü | Kurum'dan referans no |
| 2. Ek bilgi talebi | 15 gün | Kurul ek soru sorabilir |
| 3. Yerinde inceleme | Değişken | Kurul uzmanları gelebilir |
| 4. Kurul kararı | 3-12 ay | İdari yaptırım veya ihtar |
| 5. İdari para cezası | Karar tarihinde | Tebliğden itibaren 30 gün ödeme |
| 6. İdari yargı (itiraz) | 60 gün | İdare Mahkemesi |

## 13. İç Eskalasyon Tablosu (Şirket içi karar yetkileri)

| Karar | Yetki |
|-------|-------|
| Kurul'a bildirim yapma | KVKK Sorumlusu (Hukuk + CISO uyumla) |
| İlgili kişiye bildirim metni onayı | Hukuk Müdürü + Kurumsal İletişim |
| Basın açıklaması | CEO + Kurumsal İletişim Direktörü |
| Sigorta poliçesi aktivasyonu | CFO + Hukuk |
| Fidye ödememe kararı | Yönetim Kurulu (önceden tanımlı politika) |
| Veri işleyen ile sözleşme feshi | CEO + Hukuk + KVKK Komitesi |

## 14. Kayıt ve Arşiv

Bildirim ve sonrası tüm yazışma:
- **Kurul Yazışma Defteri**ne kronolojik işlenir.
- KEP delil zinciri sigortalı arşive kopyalanır.
- Saklama süresi **10 yıl** (zamanaşımı + arşiv mevzuatı).
- Erişim sadece KVKK Komitesi ve görevlendirilen Hukuk personeli.

## 15. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi |
