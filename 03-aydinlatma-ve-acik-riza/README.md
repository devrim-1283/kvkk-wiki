---
Doküman / Document: 03 - Aydınlatma ve Açık Rıza (Bölüm Girişi) / 03 - Disclosure (Information Notice) and Explicit Consent (Section Entry)
Bölüm / Section: 03-aydinlatma-ve-acik-riza
Sahip / Owner: KVKK Sorumlusu / KVKK Officer
Onaylayan / Approved by: Hukuk Müdürü + KVKK Komitesi / Head of Legal + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş (yeni süreç, mevzuat değişikliği, Kurul kararı) / Annual + triggered (new process, legislative change, Board decision)
İlgili Mevzuat / Legal Reference: 6698 sayılı KVKK m.3 (tanımlar), m.5, m.6 (işleme şartları), m.10 (aydınlatma yükümlülüğü) / Law No. 6698 (KVKK) Art. 3 (definitions), Art. 5, 6 (processing conditions), Art. 10 (disclosure obligation); Aydınlatma Yükümlülüğünün Yerine Getirilmesinde Uyulacak Usul ve Esaslar Hakkında Tebliğ (RG: 10.03.2018/30356), MADDE 4-5 / Communiqué on the Procedures and Principles to be Followed in Fulfilment of the Disclosure Obligation (Disclosure Communiqué), Art. 4-5; Veri Sorumluları Sicili Hakkında Yönetmelik MADDE 5(d) / Regulation on the Data Controllers' Registry Art. 5(d); Açık Rıza Rehberi (Kurum yayını) / Authority's Explicit Consent Guide
---

## English

# 03 - Disclosure (Information Notice) and Explicit Consent

## 1. Purpose of This Section

This section contains the document set for the operational implementation of the **disclosure obligation** under KVKK Art. 10 and the **explicit consent** regime under KVKK Art. 5(1) and Art. 6(2).

The disclosure obligation is the data controller's obligation to **provide information** to the data subject when personal data is collected. **Explicit consent** is the consent expressed freely, on a specific subject, based on information provided.

These two concepts are **not** alternatives to one another:

- Disclosure is mandatory **in all cases** (KVKK Art. 10) — regardless of legal ground.
- Explicit consent comes into play **only** when no other legal ground applies.
- Explicit consent must be obtained **separately** from the disclosure.

## 2. Scope of This Section

| # | Document | Purpose |
|---|----------|---------|
| 1 | [README.md](./README.md) | Section entry (this document) |
| 2 | [aydinlatma-metni-sablonu.md](./aydinlatma-metni-sablonu.md) | Mandatory content under Communiqué Art. 4-5, channel-specific templates, three full sample notices |
| 3 | [aydinlatma-metni-checklist.md](./aydinlatma-metni-checklist.md) | 30+ item information-notice checklist |
| 4 | [acik-riza-kurallari.md](./acik-riza-kurallari.md) | Definition of explicit consent, three elements, withdrawal, child data, CMP requirements |
| 5 | [ornekler.md](./ornekler.md) | Scenario-based application examples (10 scenarios) |

## 3. Legal Framework — Quick Reference

### 3.1 Disclosure Obligation (KVKK Art. 10, Disclosure Communiqué)

| Provision | Content |
|-----------|---------|
| KVKK Art. 10 | At the time of collection, the data controller informs the data subject about: identity, processing purpose, possible recipient/recipient groups of transfer, collection method and legal ground, and the rights under KVKK Art. 11. |
| Communiqué Art. 4 | Details the minimum content of the disclosure obligation (5 + further headings). |
| Communiqué Art. 5 | Procedures and principles — channel, evidence, separate text, plain language, identification of legal ground, etc. |
| Communiqué Art. 5/d | Disclosure is **not** dependent on a request from the data subject — it is a proactive obligation. |
| Communiqué Art. 5/e | The burden of proof lies with the **data controller**. |
| Communiqué Art. 5/c | A separate text is required per unit/process. |
| Communiqué Art. 5/g, j | General/vague expressions are prohibited; incomplete/misleading information is prohibited. |
| Communiqué Art. 5/ğ | Plain, clear and simple language. |
| Communiqué Art. 5/h | The legal ground — i.e., **which clause** of KVKK Art. 5 or Art. 6 — must be stated **expressly**. |
| Communiqué Art. 5/ı | The transfer purpose and recipient groups must be stated. |
| Communiqué Art. 5/i | The collection method (automated / non-automated) must be stated expressly. |

### 3.2 Explicit Consent (KVKK Art. 3, Art. 5, Art. 6)

| Provision | Content |
|-----------|---------|
| KVKK Art. 3(1)(a) | Explicit consent: consent on a specific subject, based on information, freely expressed. |
| KVKK Art. 5(1) | As a rule, general personal data may not be processed **without explicit consent**; consent is not required if any clause in Art. 5(2) applies. |
| KVKK Art. 6(2) | As a rule, special-category personal data may not be processed **without explicit consent**. |
| KVKK Art. 6(3) | Special-category data other than health and sexual life may be processed **without consent in cases provided for by law**. |

### 3.3 Three Elements — Explicit Consent

Under KVKK Art. 3(1)(a), explicit consent must satisfy three elements:

1. **Specific to a subject** — blanket consent is prohibited.
2. **Based on information** — consent without disclosure is invalid.
3. **Freely expressed** — consent that is conditional on receiving a service is invalid.

## 4. Disclosure vs. Explicit Consent — Decision Rule

```
You are looking for a legal ground to process the data.
       │
       ▼
Does any clause in KVKK Art. 5(2) apply?
   (law, contract, legal obligation, protection of rights, legitimate interest, etc.)
       │
       ├── Yes → Explicit consent NOT REQUIRED.
       │            Disclosure IS performed (always).
       │            Legal ground: that clause.
       │
       └── No  → Explicit consent IS taken.
                    Disclosure is also performed (first disclosure, then consent).
                    Explicit consent is collected SEPARATELY from the disclosure text.

Additionally, for special-category data:
   Does any clause in Art. 6(3) apply? → if yes, may be processed without consent.
   if no → explicit consent is mandatory.
```

## 5. Operational Flow (New Process)

| Step | Owner | Output |
|------|-------|--------|
| 1. Inventory row created (legal ground determined) | Process Owner + KVKK Officer | Inventory row |
| 2. Information notice prepared (channel-appropriate) | KVKK Officer + Legal | Information notice v1.0 |
| 3. If explicit consent required, consent text prepared | KVKK Officer + Legal | Explicit consent text v1.0 |
| 4. Channel integration (web, call center, paper) | Process Owner + IT | Operational implementation |
| 5. Evidence mechanism set up (log, IP, time, text version) | IT | Logging infrastructure |
| 6. Training (for operating staff) | KVKK Officer | Training record |
| 7. Compliance check (inventory ↔ disclosure ↔ consent ↔ VERBİS) | KVKK Officer | Compliance check record |

## 6. Roles and Responsibilities

| Role | Responsibility |
|------|----------------|
| KVKK Officer | Coordinates preparation of disclosure and consent texts; supervises alignment with the inventory |
| Legal Department | Approves the determination of legal ground; reviews wording for legal compliance |
| Process Owner | Ensures disclosure is performed at every touchpoint (form, screen, call, in person) |
| IT | Web/CMP/IVR integration, evidence logs, version management |
| Marketing | İYS (Message Management System) compliance — commercial-electronic-message consents |
| Training | Trains staff on how to deliver disclosure |

## 7. Links to Other Sections

| Section | Relationship |
|---------|--------------|
| 02 - Inventory and Registry | Information notices are produced from the inventory (Reg. Art. 5/d) |
| 04 - Data Retention and Destruction | Retention periods stated in the information notice |
| 07 - Transfer | Transfer recipients listed in the information notice |
| 09 - Data Subject Requests | KVKK Art. 11 rights enumerated in the information notice |
| 10 - Special Topics | Children's data, CCTV, call center, cookies, and other special headings |

## 8. Common Misconceptions

| Misconception | Correct |
|---------------|---------|
| "If I take explicit consent, I don't need disclosure." | Disclosure is mandatory in all cases. |
| "I made a disclosure, so the legal ground is automatically explicit consent." | Determining the legal ground is a separate analysis. |
| "Explicit consent in a single form, mandatory to obtain service." | Making it mandatory violates the "freely expressed" element. |
| "I'll take one general consent for everything." | Blanket consent is prohibited. |
| "The contract is signed, no need for disclosure." | A contract is no substitute for disclosure. |
| "One disclosure on the website is enough." | A separate text per unit/process is required (Communiqué Art. 5/c). |
| "Saying 'we are recording the call' on a voice line is enough." | All mandatory items in Communiqué Art. 4 are required. |

## 9. How to Use This Section

1. When designing a new process, open **aydinlatma-metni-sablonu.md** and select the channel-appropriate template.
2. Run the resulting text through **aydinlatma-metni-checklist.md**.
3. If the process requires explicit consent, apply **acik-riza-kurallari.md**.
4. In case of implementation ambiguity, find a similar scenario in **ornekler.md**.

## 10. Change History

| Version | Date | Change | Prepared by |
|---------|------|--------|-------------|
| 1.0 | 2026-05-08 | Initial publication | KVKK Officer |

---

## Türkçe

# 03 - Aydınlatma ve Açık Rıza

## 1. Bölümün Amacı

Bu bölüm, KVKK m.10 kapsamında **aydınlatma yükümlülüğünün** ve KVKK m.5(1) ile m.6(2) kapsamında **açık rıza** rejiminin operasyonel olarak uygulanmasına ilişkin doküman setini içerir.

Aydınlatma yükümlülüğü; veri sorumlusunun, kişisel verilerin elde edilmesi sırasında ilgili kişiye **bilgi sağlama** yükümlülüğüdür. **Açık rıza** ise, belirli bir konuya ilişkin bilgilendirilmeye dayalı ve özgür iradeyle açıklanan onaydır.

Bu iki kavram birbirinin alternatifi **değildir**:

- Aydınlatma **her halde** zorunludur (KVKK m.10) — hangi hukuki sebep olursa olsun.
- Açık rıza **sadece** başka bir hukuki sebep yoksa devreye girer.
- Açık rıza ile aydınlatma **ayrı** alınmalıdır.

## 2. Bölüm Kapsamı

| # | Doküman | Amaç |
|---|---------|------|
| 1 | [README.md](./README.md) | Bölüm girişi (bu doküman) |
| 2 | [aydinlatma-metni-sablonu.md](./aydinlatma-metni-sablonu.md) | Tebliğ M.4-5 zorunlu içerikler, kanal bazlı şablonlar, üç tam metin örneği |
| 3 | [aydinlatma-metni-checklist.md](./aydinlatma-metni-checklist.md) | 30+ maddelik aydınlatma metni kontrol listesi |
| 4 | [acik-riza-kurallari.md](./acik-riza-kurallari.md) | Açık rıza tanımı, 3 unsuru, geri alma, çocuk verisi, CMP gereksinimleri |
| 5 | [ornekler.md](./ornekler.md) | Senaryo bazlı uygulama örnekleri (10 senaryo) |

## 3. Hukuki Çerçeve — Hızlı Referans

### 3.1 Aydınlatma Yükümlülüğü (KVKK m.10, Aydınlatma Tebliği)

| Hüküm | İçerik |
|-------|--------|
| KVKK m.10 | Veri sorumlusu, kişisel verilerin elde edilmesi sırasında: kimliği, işleme amacı, aktarılabilecek alıcı/alıcı grupları, toplama yöntemi ve hukuki sebep, KVKK m.11 hakları konusunda ilgili kişiyi bilgilendirir. |
| Tebliğ M.4 | Aydınlatma yükümlülüğünün asgari içeriğini detaylandırır (5 + ek başlık). |
| Tebliğ M.5 | Usul ve esaslar — kanal, ispat, ayrı metin, açık dil, hukuki sebep belirtimi vb. |
| Tebliğ M.5/d | Aydınlatma, ilgili kişinin talebine bağlı **değildir** — aktif yükümlülüktür. |
| Tebliğ M.5/e | İspat yükümlülüğü **veri sorumlusundadır**. |
| Tebliğ M.5/c | Her birim/süreç için ayrı metin gerekir. |
| Tebliğ M.5/g, j | Genel/muğlak ifade yasak; eksik/yanıltıcı bilgi yasak. |
| Tebliğ M.5/ğ | Anlaşılır, açık ve sade dil. |
| Tebliğ M.5/h | Hukuki sebep — KVKK m.5 ya da m.6 bentlerinden hangisine dayanıldığı **açıkça** belirtilir. |
| Tebliğ M.5/ı | Aktarım amacı ve alıcı grupları belirtilir. |
| Tebliğ M.5/i | Otomatik / otomatik olmayan elde etme yöntemi açıkça belirtilir. |

### 3.2 Açık Rıza (KVKK m.3, m.5, m.6)

| Hüküm | İçerik |
|-------|--------|
| KVKK m.3/1/a | Açık rıza: belirli bir konuya ilişkin, bilgilendirilmeye dayanan ve özgür iradeyle açıklanan rızadır. |
| KVKK m.5(1) | Genel kişisel veriler kural olarak ilgili kişinin **açık rızası olmaksızın** işlenemez; ancak m.5(2)'deki bentlerden biri varsa rıza aranmaz. |
| KVKK m.6(2) | Özel nitelikli kişisel veriler kural olarak ilgili kişinin **açık rızası olmaksızın** işlenemez. |
| KVKK m.6(3) | Sağlık ve cinsel hayat dışındaki özel nitelikli verilerin **kanunlarda öngörülen hallerde** rızasız işlenmesi mümkündür. |

### 3.3 Üç Unsur — Açık Rıza

KVKK m.3/1/a tanımına göre açık rıza üç unsuru sağlamalıdır:

1. **Belirli bir konuya ilişkin** olması — battaniye rıza yasak.
2. **Bilgilendirmeye dayalı** olması — aydınlatma yapılmadan rıza geçersiz.
3. **Özgür irade** ile açıklanması — hizmet alma şartına bağlı rıza geçersiz.

## 4. Aydınlatma vs. Açık Rıza — Karar Kuralı

```
Veriyi işlemeniz için bir hukuki sebep arıyorsunuz.
       │
       ▼
KVKK m.5(2) bentlerinden biri var mı?
   (kanun, sözleşme, hukuki yükümlülük, hak korunması, meşru menfaat vb.)
       │
       ├── Evet → Açık rıza ARANMAZ.
       │            Aydınlatma YAPILIR (her halde).
       │            Hukuki sebep: o bent.
       │
       └── Hayır → Açık rıza ALINIR.
                    Aydınlatma da YAPILIR (önce aydınlatma, sonra rıza).
                    Açık rıza, aydınlatma metninden AYRI alınır.

Özel nitelikli veri için ek olarak:
   m.6(3) bentlerinden biri var mı? → varsa rızasız işlenebilir.
   yoksa → açık rıza zorunlu.
```

## 5. Operasyonel Akış (Yeni Süreç)

| Adım | Sorumlu | Çıktı |
|------|---------|-------|
| 1. Envanter satırı oluşturulur (hukuki sebep tespit) | Süreç Sahibi + KVKK Sorumlusu | Envanter satırı |
| 2. Aydınlatma metni hazırlanır (kanala uygun) | KVKK Sorumlusu + Hukuk | Aydınlatma metni v1.0 |
| 3. Açık rıza gerekli ise rıza metni hazırlanır | KVKK Sorumlusu + Hukuk | Açık rıza metni v1.0 |
| 4. Kanal entegrasyonu yapılır (web, çağrı merkezi, kağıt) | Süreç Sahibi + Bilgi İşlem | Operasyonel uygulama |
| 5. İspat mekanizması kurulur (log, IP, zaman, metin versiyonu) | Bilgi İşlem | Log altyapısı |
| 6. Eğitim verilir (uygulayıcı çalışanlara) | KVKK Sorumlusu | Eğitim kaydı |
| 7. Uyum kontrolü (envanter ↔ aydınlatma ↔ rıza ↔ VERBİS) | KVKK Sorumlusu | Uyum kontrol kaydı |

## 6. Roller ve Sorumluluklar

| Rol | Sorumluluk |
|-----|-----------|
| KVKK Sorumlusu | Aydınlatma ve rıza metinlerinin hazırlanmasını koordine etmek; envanterle uyumu denetlemek |
| Hukuk Müdürlüğü | Hukuki sebep tespitini onaylamak; metin dilini hukuki uyum açısından kontrol etmek |
| Süreç Sahibi | Sürecin tüm temas noktalarında (form, ekran, çağrı, sözlü) aydınlatmanın yapılmasını sağlamak |
| Bilgi İşlem | Web/CMP/IVR entegrasyonu, ispat logları, sürüm yönetimi |
| Pazarlama | İYS (İleti Yönetim Sistemi) uyumu — ticari elektronik ileti onayları |
| Eğitim | Çalışanlara aydınlatma yapma yöntemlerinin öğretilmesi |

## 7. Diğer Bölümlerle Bağlantı

| Bölüm | İlişki |
|-------|--------|
| 02 - Envanter ve Sicil | Aydınlatma metinleri envanterden üretilir (Yön. M.5/d) |
| 04 - Veri Saklama ve İmha | Aydınlatma metninde saklama süresi belirtilir |
| 07 - Aktarım | Aktarım alıcıları aydınlatma metninde gösterilir |
| 09 - İlgili Kişi Başvuruları | KVKK m.11 hakları aydınlatma metninde sayılır |
| 10 - Özel Konular | Çocuk verisi, CCTV, çağrı merkezi, çerez gibi özel başlıklar |

## 8. Yaygın Yanılgılar

| Yanılgı | Doğrusu |
|---------|---------|
| "Açık rıza alırsam aydınlatmaya gerek yok" | Aydınlatma her halde zorunludur. |
| "Aydınlatma yaptım, hukuki sebep otomatik açık rıza olur" | Hukuki sebep tespiti ayrı bir analizdir. |
| "Açık rıza tek formda, hizmet alma için zorunlu" | Hizmet için zorunlu kılma "özgür irade"yi ihlal eder. |
| "Tek bir genel rıza alırım, her şey için geçerli" | Battaniye rıza yasaktır. |
| "Sözleşme zaten imzalandı, aydınlatmaya ihtiyaç yok" | Sözleşme aydınlatma yerine geçmez. |
| "Web sitesinde tek aydınlatma metni yeterli" | Her birim/süreç için ayrı metin (Tebliğ M.5/c). |
| "Ses kaydında 'aramayı kaydediyoruz' demek aydınlatma için yeterli" | Tebliğ M.4'teki tüm zorunlu unsurlar gerekli. |

## 9. Bu Bölümün Kullanımı

1. Yeni süreç tasarımında, **aydinlatma-metni-sablonu.md** açılır ve kanal türüne uygun şablon seçilir.
2. Hazırlanan metin, **aydinlatma-metni-checklist.md** ile kontrol edilir.
3. Süreç açık rıza gerektiriyorsa, **acik-riza-kurallari.md** uygulanır.
4. Uygulama belirsizliği halinde, **ornekler.md** dokümanından benzer senaryo bulunur.

## 10. Değişiklik Geçmişi

| Versiyon | Tarih | Değişiklik | Hazırlayan |
|----------|-------|-----------|-----------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Sorumlusu |
