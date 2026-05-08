---
Doküman / Document: Müşteri ve Pazarlama Verisi Yönetimi (CRM, İYS, Profilleme) / Customer and Marketing Data Management (CRM, İYS, Profiling)
Bölüm / Section: 10-ozel-konular
Sahip / Owner: KVKK Sorumlusu + Pazarlama Direktörü + CRM Sahibi / KVKK Officer + Marketing Director + CRM Owner
Onaylayan / Approved by: Hukuk Müdürü + KVKK Komitesi / Head of Legal + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + İYS / Kurul kararlarına göre / Annual + per İYS / Authority decisions
İlgili Mevzuat / Legal Reference: Law No. 6698 (KVKK) Art. 5, 11; Law No. 6563 (Electronic Commerce); "Regulation on Commercial Communications and Commercial Electronic Messages" (Official Gazette 29417 dated 15.07.2015); Law No. 6502 (Consumer Protection); KVKK Cookie Guide
---

## English

# Customer and Marketing Data Management

## 1. Purpose and Scope

KVKK + 6563 + İYS-compliant management of CRM, marketing automation, e-mail, SMS, push notifications, targeted ads, segmentation, A/B testing, personalization, profiling, and automated decision processes.

## 2. Legal Ground for Marketing

### 2.1. From the KVKK Perspective

The marketing purpose does not naturally fit any of the grounds in KVKK Art. 5(2):

- It is not performance of contract (selling to a customer does not encompass marketing).
- No legal obligation.
- Legitimate interest is **interpreted very narrowly** (Authority position).

> **Conclusion:** The legal ground for marketing is **EXPLICIT CONSENT** (Art. 5(1)).

### 2.2. Law No. 6563 (Commercial Electronic Messages)

For commercial electronic messages by e-mail, SMS, push, voice call:

- Prior approval (Art. 6) is mandatory.
- Existing-customer exception: no additional approval for the same goods/service, **but** the right to opt out remains.
- Consent record via KEP / SMS / written channel.

### 2.3. İYS (Message Management System / "İleti Yönetim Sistemi")

The mandatory system activated by the Ministry of Trade on 15 January 2020:

- All commercial electronic message approvals must be filed in İYS.
- Sending messages to numbers without approval is forbidden.
- Companies must register with İYS.
- Companies above the monthly threshold use API integration.

## 3. Marketing Permission Process

### 3.1. Permission Collection

```
[Customer registration form / Website / E-commerce]
        |
[Explicit-consent checkboxes: [ ] Email [ ] SMS [ ] Phone [ ] Calls]
        |
[Disclosure: marketing purpose, content type, frequency, cross-border transfer]
        |
[Verification: e-mail click / SMS OTP / phone confirmation]
        |
[Recording: timestamp, IP, channel, content, version]
        |
[İYS notification (within 3 business days)]
```

### 3.2. Designing Explicit Consent (Marketing)

A single "for all marketing" is NOT acceptable. Granular:

| [ ] E-mail newsletter (weekly) | Content: new products, campaigns |
| [ ] SMS notifications | Content: discount alerts, last chance |
| [ ] Telephone calls | Content: special offers, surveys |
| [ ] Push notifications | Mobile app |
| [ ] WhatsApp Business | Limited category templates |
| [ ] Cross-border transfer for marketing | Cloud provider, e-mail service |

### 3.3. Withdrawal

- Mandatory **unsubscribe** link in every e-mail (Regulation requirement).
- "STOP" reply for SMS.
- One-click on the website profile page.
- Request via call center.
- Withdrawal removed from system within 3 business days + İYS updated.

### 3.4. Existing-Customer Exception

Law 6563 Art. 6(2): For a customer who has been provided goods/services, no additional approval is needed for the **same goods/services**.

> **Practice:** The scope is interpreted narrowly. Be cautious when interpreting "same category". Judicial practice: same category is sufficient - e.g., a store customer can be e-mailed about a new store campaign.

## 4. CRM Data Management

### 4.1. Data Categories

- Identity (name, T.R. ID - only if necessary).
- Contact.
- Transaction history (order, payment).
- Engagement (e-mail open/click, web visit).
- Preferences (segment, interests).
- Net Promoter Score (NPS), CSAT.
- Complaint records.

### 4.2. CRM Access Management

- RBAC (Role-Based Access Control).
- Marketing operations -> segments + aggregates.
- Sales reps -> assigned customers.
- Customer service -> own touchpoints.
- Management -> aggregate reports.
- Audit log on every access.

### 4.3. Common CRM Systems

- Salesforce, HubSpot, Microsoft Dynamics 365, Zoho - cross-border data center concerns.
- Turkish local: Logo CRM, Mikro - domestic advantage.
- For foreign CRMs, prefer DPA + Standard Contract + Türkiye region (where available).

## 5. Profiling and Automated Decisions

### 5.1. Right to Object under KVKK Art. 11(g)

> "To object to the emergence of a result against the person from analysis of processed data exclusively by automated systems."

When objected:

- Manual review guarantee.
- Explainable decision.
- Option to be excluded from the process.

### 5.2. Profiling Scenarios

| Scenario | KVKK Compliance |
|----------|-----------------|
| Segmentation (silver/gold/platinum customer) | Disclosure + (where applicable) explicit consent |
| Lookalike modeling (similar to existing customers) | DPIA + disclosure |
| Churn prediction | DPIA - customer may be adversely affected |
| Automated credit limit (payment history) | Legal ground + manual revision |
| Targeted ads (Meta, Google) | Explicit consent - cross-border transfer |
| Recommendation engines | Disclosure + (often) explicit consent |
| A/B testing | Disclosure; if no adverse automated decision, low consent need |

### 5.3. DPIA Triggers

- Automated decisions with effect, no manual revision.
- Sensitive category (health, financial, ethnic).
- Wide scale (1M+ users).
- New technology (AI/ML).
- Continuous monitoring.

## 6. A/B Testing and Experiments

### 6.1. KVKK Perspective

- Test groups operate on personal data -> processing.
- Within "improvement" in the privacy notice.
- Reasonable if no adverse outcome arises.

### 6.2. Ethical Framework

- Opt-out option (excluded from tests) by design.
- Aggregate / anonymized result sharing.
- Sensitive content tests (e.g., emotional manipulation) forbidden - Cambridge Analytica example.

## 7. Targeted Advertising (Meta, Google, TikTok)

### 7.1. Custom Audience / Lookalike

- Upload customer list as hashed values to Meta/Google.
- Explicit consent required before hashing.
- The contractual data-controller/processor status of the ad network requires Legal review.
- KVKK transfer rules apply.

### 7.2. Pixels / Tags

- Website pixel -> user data to ad network.
- Explicit consent (via CMP) mandatory.

### 7.3. Cross-Border Transfer

- Meta, Google, TikTok are US/EU based -> abroad.
- Standard Contract additional safeguard.
- Country + purpose stated in the privacy notice.

## 8. Marketing Content Personalization

### 8.1. CRM-Triggered E-mails

- "Happy birthday" -> personal data use.
- "You forgot your basket" -> e-commerce.
- Trigger explained in the privacy notice.

### 8.2. Web Site Personalization

- Product recommendation based on prior visits.
- Cookie based.
- Explicit consent (CMP).

### 8.3. Push Notifications

- Mobile app permission has two layers:
   1. OS permission (iOS, Android).
   2. KVKK explicit consent (in-app).
- Easy withdrawal.

## 9. Customer Complaints and Feedback

### 9.1. Retention

- Complaints in scope of Law 6502 + KVKK.
- Retention: consumer dispute statute of limitations (may be 10 years).
- Personal data minimized.

### 9.2. Social-Media Complaints

- Şikayetvar, Eksisozluk, Twitter, etc. -> publicly available data.
- Recording the complaint + responding is in KVKK scope.
- User identification (username, e-mail) sensitive.

## 10. NPS / Surveys / User Research

- Survey participation with explicit consent.
- Anonymization preferred.
- Personal results restricted access.
- Retention proportionate to purpose.

## 11. Cookie Integration

See `cerez-yonetimi.md`. Marketing cookies:

- Explicit consent required.
- Through the CMP.
- If refused, marketing cookies do not load.

## 12. CMS (Customer Marketing System) Architecture

```
[Web/Mobile/Store]
       |
[Data collection (CRM, CDP)]
       |
[Segmentation (CDP)]
       |
[Marketing automation (HubSpot/Marketo/Mailchimp)]
       |
[Channel: e-mail, SMS, push, ads]
       |
[Engagement tracking]
       |
[Feedback - segment update]
```

At every stage:

- Disclosure + consent check.
- Access management.
- Encryption.
- Audit log.

## 13. Common Mistakes

| Mistake | Correct approach |
|---------|------------------|
| Single "marketing consent" | Granular per channel |
| No İYS registration | Required (3 business days) |
| SMS to a non-approved number | Use İYS query API |
| No unsubscribe link | Mandatory under the Regulation |
| Pixel without cookie consent | After consent via CMP |
| No consent for lookalike transfer | Explicit consent + disclosure |
| No Türkiye region for foreign CRM | Prefer region selection if available |
| Customer complaint in marketing data segment | Non-marketing data |
| No manual revision for automated decisions | Honor Art. 11(g) right |
| Missing DPIA (large profiling) | DPIA mandatory |

## 14. KPIs

| KPI | Target |
|-----|--------|
| İYS compliance rate | 100% |
| Valid explicit consent rate | 100% |
| Unsubscribe SLA | < 3 business days |
| Marketing message complaint rate | < 0.1% |
| CMP consent record rate | 95%+ |
| DPIA coverage (large profiling) | 100% |
| CRM access audit log | 100% |

## 15. Version History

| Version | Date | Change | Approval |
|---------|------|--------|----------|
| 1.0 | 2026-05-08 | First publication | KVKK Committee |

---

## Türkçe

# Müşteri ve Pazarlama Verisi Yönetimi

## 1. Amaç ve Kapsam

CRM, pazarlama otomasyonu, e-posta gönderimi, SMS, push notification, hedefli reklam, segmentasyon, A/B test, kişiselleştirme, profilleme ve otomatik karar süreçlerinin KVKK + 6563 + İYS uyumlu yönetimi.

## 2. Pazarlama için Hukuki Sebep

### 2.1. KVKK Açısından

Pazarlama amacı KVKK m.5/2 sayılan sebeplerin **hiçbirine** doğal olarak girmez:
- Sözleşmenin ifası değildir (müşteriye satış yapıyor olmamız pazarlamayı kapsamaz).
- Yasal yükümlülük yok.
- Meşru menfaat de **çok kıt** uygulanır (Kurul tutumu).

> **Sonuç:** Pazarlama için hukuki sebep **AÇIK RIZA** (m.5/1).

### 2.2. 6563 Sayılı Kanun (Ticari Elektronik İleti)

E-posta, SMS, push, sesli arama gibi **ticari elektronik iletiler** için:
- Önceden onay (m.6) zorunlu.
- Mevcut müşteri istisnası: aynı mal/hizmet için ek onay aranmaz **AMA** ret hakkı her zaman.
- Onay metni KEP / SMS / yazılı kanaldan kayıt.

### 2.3. İYS (İleti Yönetim Sistemi)

15 Ocak 2020 tarihinde Ticaret Bakanlığı tarafından devreye alınan zorunlu sistem:
- Tüm ticari elektronik ileti onayları İYS'ye işlenir.
- Onay olmayan numaralara ileti gönderimi yasak.
- Şirketler İYS'ye kayıt zorunlu.
- Aylık eşik üzerinde olan firmalar API entegrasyonu.

## 3. Pazarlama İzin Süreci

### 3.1. İzin Toplama

```
[Müşteri kayıt formu / Web sitesi / E-ticaret]
        ↓
[Açık rıza checkbox: ☐ E-posta ☐ SMS ☐ Telefon ☐ Aramalar]
        ↓
[Açıklama: Pazarlama amacı, içerik tipi, sıklık, yurt dışı aktarım]
        ↓
[Doğrulama: e-posta tıklama / SMS OTP / telefon onay]
        ↓
[Kayıt: Zaman damgası, IP, kanal, içerik, versiyon]
        ↓
[İYS bildirimi (3 iş günü içinde)]
```

### 3.2. Açık Rıza Tasarımı (Pazarlama)

Tek "Tüm pazarlamalar için" KABUL EDİLMEZ. Granüler:

| ☐ E-posta bülten (haftalık) | İçerik: yeni ürünler, kampanyalar |
| ☐ SMS bilgilendirme | İçerik: indirim alarmı, son fırsat |
| ☐ Telefon araması | İçerik: özel teklif, anket |
| ☐ Push bildirim | Mobil uygulama |
| ☐ WhatsApp Business | Sınırlı kategori şablonu |
| ☐ Pazarlama amaçlı yurt dışı aktarım | Bulut sağlayıcı, e-posta servisi |

### 3.3. Geri Alma

- Her e-postada **abonelikten çık** linki (zorunlu — Yönetmelik).
- SMS'te "RED" yanıtı.
- Web sitesi profil sayfasında tek tık.
- Çağrı merkezinden talep.
- Geri alma 3 iş günü içinde sistemden silinir + İYS güncellenir.

### 3.4. Mevcut Müşteri İstisnası

6563 m.6/2: Mal/hizmet sağlanan müşteriye, **aynı mal/hizmet** için ek onay gerekmez.

> **Pratik:** Kapsam dar yorumlanır. "Aynı kategori" yorumlanırken ihtiyatlı olun. Yargı pratiği: aynı kategori yeterli — örn. mağaza müşterisi e-postasına yeni mağaza kampanyası gönderilebilir.

## 4. CRM Veri Yönetimi

### 4.1. Veri Kategorileri

- Kimlik (ad-soyad, T.C. — sadece zorunluysa).
- İletişim.
- İşlem geçmişi (sipariş, ödeme).
- Etkileşim (e-posta açma, tıklama, web ziyareti).
- Tercihler (segment, ilgi alanı).
- Net Promoter Score (NPS), CSAT.
- Şikayet kayıtları.

### 4.2. CRM Erişim Yönetimi

- RBAC (Role-Based Access Control).
- Pazarlama operasyon → segment + agregat.
- Sales rep → atanan müşteriler.
- Müşteri hizmetleri → kendi temas noktası.
- Yönetim → toplu rapor.
- Audit log her erişim.

### 4.3. CRM ile İlgili Tipik Sistemler

- Salesforce, HubSpot, Microsoft Dynamics 365, Zoho — yurt dışı veri merkezi sorunu.
- Türk yerli: Logo CRM, Mikro — yurt içi avantaj.
- Yurt dışı CRM kullanımında DPA + Standart Sözleşme + Türkiye region (varsa) tercih.

## 5. Profilleme ve Otomatik Karar

### 5.1. KVKK m.11/g İtiraz Hakkı

> "İşlenen verilerin münhasıran otomatik sistemlerle analiz edilmesi suretiyle kişinin kendisi aleyhine bir sonucun ortaya çıkmasına itiraz etme."

İtiraz halinde:
- Manuel değerlendirme garantisi.
- Açıklanabilir karar.
- Süreçten muafiyet seçeneği.

### 5.2. Profilleme Senaryoları

| Senaryo | KVKK Uyum |
|---------|-----------|
| Segmentasyon (gümüş/altın/platin müşteri) | Aydınlatma + (varsa) açık rıza |
| Lookalike modeli (yeni müşteri benzeri) | DPIA + aydınlatma |
| Churn prediction | DPIA — müşteri olumsuz etkilenebilir |
| Kredi limiti otomatik (ödeme geçmişi) | Hukuki sebep + manuel revize |
| Hedefli reklam (Meta, Google) | Açık rıza — yurt dışı aktarım |
| Ürün öneri (recommendation engine) | Aydınlatma + (genelde) açık rıza |
| A/B test | Aydınlatma; otomatik aleyhine karar yoksa rıza ihtiyacı düşük |

### 5.3. DPIA Tetikleyiciler

- Otomatik karar, manuel revize olmadan etki.
- Hassas kategori (sağlık, finansal durum, etnik).
- Geniş ölçek (1M+ kullanıcı).
- Yeni teknoloji (AI/ML).
- Sürekli izleme.

## 6. A/B Test ve Deneyler

### 6.1. KVKK Açısından

- Test grupları kişisel veri üzerinde yürütülüyor → işleme.
- Aydınlatma metninde "iyileştirme" kapsamında.
- Olumsuz sonuç doğmuyorsa makul.

### 6.2. Etik Çerçeve

- Reddet seçeneği (test dışı tutulma) tasarımda.
- Sonuç paylaşımı toplu / anonim.
- Hassas içerik testi (örn. duygusal manipülasyon) yasak — Cambridge Analytica örneği.

## 7. Hedefli Reklam (Meta, Google, TikTok)

### 7.1. Custom Audience / Lookalike

- Müşteri listesini hashed olarak Meta/Google'a yükle.
- Hash öncesi açık rıza zorunlu.
- Sözleşmesel olarak reklam ağı **veri sorumlusu/işleyen** durumu Hukuk değerlendirmesi gerektirir.
- KVKK aktarım hükümleri uygulanır.

### 7.2. Pixel / Tag

- Web sitesi pixel → kullanıcı verisi reklam ağına.
- Açık rıza (CMP üzerinden) zorunlu.

### 7.3. Yurt Dışı Aktarım

- Meta, Google, TikTok ABD/AB merkezli → yurt dışı.
- Standart Sözleşme ek garantisi.
- Aydınlatmada ülke + amaç bildirimi.

## 8. Pazarlama İçeriği Kişiselleştirme

### 8.1. CRM Tetiklemeli E-posta

- "Doğum gününüz kutlu olsun" → kişisel veri kullanımı.
- "Sepetinizi unuttunuz" → e-ticaret.
- Tetikleyici aydınlatmada açıklanır.

### 8.2. Web Site Kişiselleştirme

- Önceki ziyaretler bazında ürün önerisi.
- Çerez tabanlı.
- Açık rıza (CMP).

### 8.3. Push Bildirim

- Mobil uygulama izni iki katmanlı:
   1. OS izni (iOS, Android).
   2. KVKK açık rıza (uygulama içi).
- Geri alma kolay.

## 9. Müşteri Şikayet ve Geri Bildirim

### 9.1. Saklama

- Şikayet kaydı 6502 sayılı Kanun + KVKK kapsamı.
- Saklama: tüketici uyuşmazlığı zamanaşımı (10 yıl olabilir).
- Kişisel veri minimize edilir.

### 9.2. Sosyal Medya Şikayetleri

- Şikayetvar, Eksisozluk, Twitter, vb. → kamuya açık veri.
- Şikayetin kaydı + cevap KVKK kapsamı.
- Kullanıcı tanımlama (kullanıcı adı, e-posta) hassas.

## 10. NPS / Anket / Kullanıcı Araştırması

- Anket katılımı açık rıza ile.
- Anonimleştirme öncelikli.
- Kişisel sonuçlar erişim kısıtlı.
- Saklama amaçla orantılı.

## 11. Çerez ile Entegrasyon

Bkz. `cerez-yonetimi.md`. Pazarlama çerezleri:
- Açık rıza zorunlu.
- CMP üzerinden.
- Reddedince pazarlama çerezi yüklenmez.

## 12. CMS (Customer Marketing System) Mimarisi

```
[Web/Mobil/Mağaza]
       ↓
[Veri toplama (CRM, CDP)]
       ↓
[Segmentasyon (CDP)]
       ↓
[Pazarlama otomasyonu (HubSpot/Marketo/Mailchimp)]
       ↓
[Kanal: e-posta, SMS, push, reklam]
       ↓
[Etkileşim takibi]
       ↓
[Geri besleme — segment güncelleme]
```

Her kademede:
- Aydınlatma + rıza kontrolü.
- Erişim yönetimi.
- Şifreleme.
- Audit log.

## 13. Tipik Hatalar

| Hata | Doğru Yaklaşım |
|------|----------------|
| Tek "pazarlama rızası" | Kanal bazlı granüler |
| İYS'ye kayıt yok | Zorunlu (3 iş günü) |
| Onay olmayan numaraya SMS | İYS sorgulama API |
| Abonelikten çık linki yok | Yönetmelik gereği zorunlu |
| Çerez izni almadan pixel | CMP rıza sonrası |
| Lookalike için aktarım açık rıza yok | Açık rıza + aydınlatma |
| Yurt dışı CRM Türkiye region yok | Region seçimi mümkünse |
| Müşteri şikayeti "marketing data" segmentinde | Pazarlama dışı veri |
| Otomatik karar manuel revize yok | m.11/g hakkı tanı |
| DPIA yapılmamış (büyük profilleme) | DPIA zorunlu |

## 14. KPI'lar

| KPI | Hedef |
|-----|-------|
| İYS uyum oranı | %100 |
| Açık rıza geçerli oran | %100 |
| Abonelikten çık SLA | < 3 iş günü |
| Pazarlama mesajı şikayet oranı | < %0.1 |
| CMP rıza kayıt oranı | %95+ |
| DPIA kapsam (büyük profilleme) | %100 |
| CRM erişim audit log | %100 |

## 15. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi |
