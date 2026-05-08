---
Doküman / Document: Kişisel Verilerin Aktarımı — Bölüm Girişi / Personal Data Transfers — Section Introduction
Bölüm / Section: 07-aktarim
Sahip / Owner: KVKK Sorumlusu / KVKK Officer
Onaylayan / Approved by: Hukuk Müdürü + Bilgi Güvenliği Yöneticisi / Legal Director + Information Security Manager
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş / Annual + triggered (regulatory change, Board decision, new vendor/transfer route)
İlgili Mevzuat / Legal Reference: Law No. 6698 (KVKK) Art. 5, 6, 8, 9; Law No. 7499 dated 12.03.2024 (effective 01.06.2024); Personal Data Protection Board Decision No. 2024/959 dated 04.06.2024 (Standard Contracts and BCRs); Authority's adequacy decision country list
---

## English

# Section 07 — Personal Data Transfers

## 1. Purpose of the Section

This section regulates the entire operational and legal framework for the data controller's transfer of personal data domestically (KVKK Art. 8) and abroad (KVKK Art. 9). With **Law No. 7499 on the Amendment of the Code of Criminal Procedure and Other Laws**, published in Official Gazette No. 32487 dated 12.03.2024, KVKK Art. 9 was substantially revised; the new regime entered into force on **01.06.2024**.

The new regime envisages a **tiered architecture** for cross-border transfers:

1. An **adequacy decision** for the destination country / sector / international organization;
2. **Appropriate safeguards** (4 sub-methods);
3. **Occasional/incidental cases** (a closed list of 6 exceptional cases).

By Personal Data Protection Board Decision No. 2024/959 dated 04.06.2024, the **standard contractual clauses (SCC) / standard contract texts** and **Binding Corporate Rules (BCR) application forms** along with helper guidelines have been published.

Note on terminology: Turkey's "standard contract" is a domestic regime under KVKK Art. 9/4-(c) and is distinct from EU GDPR Standard Contractual Clauses (SCCs); they are not interchangeable.

## 2. Section Contents

| # | Document | Purpose |
|---|----------|---------|
| 1 | [README.md](README.md) | Section introduction (this document) |
| 2 | [yurtici-aktarim.md](yurtici-aktarim.md) | KVKK Art. 8 — domestic transfer regime |
| 3 | [yurtdisi-aktarim-rejimi.md](yurtdisi-aktarim-rejimi.md) | KVKK Art. 9 — tiered regime, decision tree |
| 4 | [standart-sozlesme-rehberi.md](standart-sozlesme-rehberi.md) | Standard contract application; notification flow |
| 5 | [baglayici-sirket-kurallari.md](baglayici-sirket-kurallari.md) | BCR scope, prior Board approval |
| 6 | [arizi-aktarim.md](arizi-aktarim.md) | Occasional/incidental cases (Art. 9/6) — 6 exceptions |
| 7 | [aktarim-degerlendirme-formu.md](aktarim-degerlendirme-formu.md) | Fillable form + samples |

## 3. Transfer Regime Top View

```
+------------------------------------------------------------+
|                    PERSONAL DATA TRANSFER                  |
+------------------------------------------------------------+
                              |
              +---------------+----------------+
              |                                |
              v                                v
+--------------------------+    +--------------------------+
| DOMESTIC (Art. 8)        |    | CROSS-BORDER (Art. 9)    |
|                          |    |                          |
| - Art. 5/Art. 6 condition|    | + TIERED REGIME:         |
| - Separately required    |    |                          |
|   for transfer too       |    |   1. Adequacy decision   |
| - Explicit consent or    |    |   2. Appropriate         |
|   exceptions             |    |      safeguards          |
| - Contract obligation    |    |   3. Occasional cases    |
|                          |    |                          |
|                          |    | + Art. 5/6 condition is  |
|                          |    |   separately required    |
|                          |    |   on every path          |
+--------------------------+    +--------------------------+
```

## 4. Key Definitions and Distinctions

### 4.1. Transfer

KVKK does not explicitly define "transfer"; however, transfer is interpreted as **granting access** or **physically/digitally transmitting** personal data to another natural/legal person. Transfer covers all of the following:

- Transfer by contract (supplier, service provider),
- De facto sharing (email, file transfer),
- Granting access via API,
- Cloud hosting (counts as transfer if on the provider's infrastructure),
- Remote access (a foreign office connecting to a system in Turkey).

### 4.2. Controller — Processor Transfer

Transfer can be **controller → processor** or **controller → controller**. They give rise to different obligations:

| Dimension | C → P | C → C |
|-----------|-------|-------|
| Contract type | Data Processing Agreement (within meaning of KVKK Art. 12) | Transfer agreement + each party's independent KVKK compliance |
| Control | C determines purpose and means; P acts on instructions | Both parties determine their own purpose and means |
| Disclosure | C performs | Each party performs for its own role |
| Liability | C primarily liable for P's breach | A breach by one does not automatically create liability for the other |
| Joint controllership | Not present | Possible — reasoned analysis required |

### 4.3. Domestic vs Cross-Border

A transfer is "cross-border" when data is **physically written to a server outside Turkey** or **a natural/legal person abroad can access it**. Even if a cloud provider has a Turkey region, cross-border transfer may be triggered depending on the provider's foreign support/admin/access rights. A **Transfer Impact Assessment (TIA)** is required to clarify this.

## 5. Common Obligation: Art. 5 and Art. 6 Processing Condition

In both domestic and cross-border transfers, **before** transfer, the processing of the data must be grounded in a condition under KVKK Art. 5 (general) or Art. 6 (special category). The transfer itself is grounded separately:

- Domestic: Art. 8 provisions,
- Cross-border: Art. 9 provisions (adequacy / appropriate safeguard / occasional).

Both grounds must be satisfied independently. An existing processing condition does not by itself legitimize transfer.

## 6. Responsibilities

| Role | Responsibility |
|------|----------------|
| Board of Directors | Approval of cross-border transfer strategy; acceptance of standard contract templates |
| KVKK Officer | Management of transfer inventory; Transfer Impact Assessment (TIA) for each transfer; standard contract notifications; notification to the Authority within 5 business days |
| Legal Department | Legal review of contract texts; analysis of recipient country law; Board permission applications |
| Information Security | Implementation of technical measures (encryption, key management, supplementary measures); security of transfer infrastructure |
| Procurement | Reflecting standard contract/DPA requirement at the tender stage |
| IT | Technical implementation of transfer; cloud provider selection backed by compliance analysis |
| Business Units | Notify the KVKK Officer of new transfer requests; business rationale |

## 7. Relationship of This Section to Other Sections

- **02 — Inventory and Registry:** The transfer inventory (recipient, country, category, basis) is the data source of this section; reflected in VERBİS notification.
- **03 — Disclosure and Explicit Consent:** Where the legal basis for transfer is explicit consent, the consent text is written consistently with this section.
- **05 — Technical Measures:** Supplementary technical measures in transfer (encryption, IP filtering, key management).
- **08 — Breach Management:** Breach records in cross-border transfers require additional care.
- **10 — Special Topics:** Cloud, call center, e-commerce transfer routes.

## 8. Audit and KPIs

- Transfer count consistency with the inventory
- Share of transfers with signed standard contract (>95% target)
- Notification rate within 5 business days (100% target)
- Transfers without completed TIA (=0 target)
- Share of cross-border transfers based on explicit consent (kept as low as possible; consent is revocable)

## 9. Legal References

- Law No. 6698 (KVKK) — Art. 5, 6, 8, 9 (as amended by Law No. 7499 dated 12.03.2024)
- Official Gazette No. 32487 dated 12.03.2024 — Law No. 7499 (effective 01.06.2024)
- Personal Data Protection Board Decision No. 2024/959 dated 04.06.2024 — Standard Contracts and BCR
- "Adequacy List of Countries" maintained on the Authority's website
- "Guide on Cross-Border Transfer" issued by the Authority

---

## Türkçe

# Bölüm 07 — Kişisel Verilerin Aktarımı

## 1. Bölümün Amacı

Bu bölüm, veri sorumlusunun kişisel verileri yurt içinde (KVKK m.8) ve yurt dışına (KVKK m.9) aktarımına ilişkin tüm operasyonel ve hukuki çerçeveyi düzenler. 12.03.2024 tarihli ve 32487 sayılı Resmî Gazete'de yayımlanan **7499 sayılı Ceza Muhakemesi Kanunu ile Bazı Kanunlarda Değişiklik Yapılmasına Dair Kanun** ile KVKK m.9 köklü bir biçimde değiştirilmiş ve yeni rejim **01.06.2024** tarihinde yürürlüğe girmiştir.

Yeni rejim, kişisel verilerin yurt dışına aktarımında **aşamalı bir yapı** öngörür:

1. **Yeterlilik kararı** bulunan ülke / sektör / uluslararası kuruluş;
2. **Uygun güvenceler** (4 alt yöntem);
3. **Arızi haller** (sınırlı sayıda 6 istisnai hal).

Kurul'un 04.06.2024 tarihli ve 2024/959 sayılı kararı ile **standart sözleşme metinleri** ve **bağlayıcı şirket kuralları (BCR)** başvuru formları ile yardımcı kılavuzlar yayımlanmıştır.

## 2. Bölüm İçeriği

| # | Doküman | Amaç |
|---|---------|------|
| 1 | [README.md](README.md) | Bölüm girişi (bu doküman) |
| 2 | [yurtici-aktarim.md](yurtici-aktarim.md) | KVKK m.8 — yurt içi aktarım rejimi |
| 3 | [yurtdisi-aktarim-rejimi.md](yurtdisi-aktarim-rejimi.md) | KVKK m.9 — aşamalı rejim, karar ağacı |
| 4 | [standart-sozlesme-rehberi.md](standart-sozlesme-rehberi.md) | Standart sözleşme uygulaması; bildirim akışı |
| 5 | [baglayici-sirket-kurallari.md](baglayici-sirket-kurallari.md) | BCR kapsamı, Kurul ön onayı |
| 6 | [arizi-aktarim.md](arizi-aktarim.md) | Arızi haller (m.9/6) — 6 istisnai hal |
| 7 | [aktarim-degerlendirme-formu.md](aktarim-degerlendirme-formu.md) | Doldurulabilir form + örnekler |

## 3. Aktarım Rejimi Üst Görünümü

```
+------------------------------------------------------------+
|                     KİŞİSEL VERİ AKTARIMI                  |
+------------------------------------------------------------+
                              |
              +---------------+----------------+
              |                                |
              v                                v
+--------------------------+    +--------------------------+
| YURT İÇİ (m.8)           |    | YURT DIŞI (m.9)          |
|                          |    |                          |
| - m.5/m.6 işleme şartı   |    | + AŞAMALI REJİM:         |
| - Aktarım için ayrıca    |    |                          |
|   ayrıca aranır          |    |   1. Yeterlilik kararı   |
| - Açık rıza veya         |    |   2. Uygun güvenceler    |
|   istisnalar             |    |   3. Arızi haller        |
| - Sözleşme zorunluluğu   |    |                          |
|                          |    | + Tüm yollarda m.5/m.6   |
|                          |    |   şartı ayrıca aranır    |
+--------------------------+    +--------------------------+
```

## 4. Temel Tanımlar ve Ayrımlar

### 4.1. Aktarım

KVKK'da aktarım açıkça tanımlanmamıştır; ancak aktarım, kişisel verinin başka bir gerçek/tüzel kişiye **erişiminin sağlanması** veya **fiziksel/dijital olarak iletilmesi** olarak yorumlanır. Aktarım, aşağıdakilerin tümünü kapsar:

- Sözleşmeyle aktarım (tedarikçi, hizmet sağlayıcı),
- Fiilî paylaşım (e-posta, dosya transferi),
- API ile erişim verme,
- Bulut barındırma (veri sağlayıcının altyapısında ise aktarım sayılır),
- Uzaktan erişim (yabancı ofisin Türkiye'deki sisteme bağlanması).

### 4.2. Veri Sorumlusu - Veri İşleyen Aktarımı

Aktarım, **veri sorumlusu → veri işleyen** veya **veri sorumlusu → veri sorumlusu** olabilir. İkisi farklı yükümlülükler doğurur:

| Boyut | VS → Vİ | VS → VS |
|-------|---------|---------|
| Sözleşme türü | Veri İşleme Sözleşmesi (KVKK m.12 anlamında) | Aktarım sözleşmesi + her iki tarafın bağımsız KVKK uyumu |
| Kontrol | VS amaç ve vasıtaları belirler; Vİ talimat ile hareket eder | İki taraf da kendi amaç ve vasıtalarını belirler |
| Aydınlatma | VS yapar | Her iki taraf kendi rolü için yapar |
| Sorumluluk | Vİ'nin ihlali halinde VS'nin sorumluluğu öncelikli | Birinin ihlali diğerinin sorumluluğunu doğurmaz |
| Joint controllership | Yok | Mümkün — gerekçeli analiz yapılmalı |

### 4.3. Yurt İçi vs Yurt Dışı

Aktarımın "yurt dışı" sayılması; verinin **fiziksel olarak Türkiye dışında bir sunucuya yazılması** veya **yurt dışındaki bir gerçek/tüzel kişinin erişebilmesi** ile ortaya çıkar. Bulut sağlayıcının Türkiye'de region'u olsa bile, sağlayıcının yurt dışındaki destek/idare/erişim haklarına bağlı olarak yurt dışı aktarım söz konusu olabilir. **Aktarım Etki Değerlendirmesi (TIA)** bunu netleştirmek için gereklidir.

## 5. Ortak Yükümlülük: m.5 ve m.6 İşleme Şartı

Hem yurt içi hem yurt dışı aktarımda, **aktarımdan ÖNCE** verinin işlenmesinin KVKK m.5 (genel) veya m.6 (özel nitelikli) kapsamında bir şartla dayanaklandırılması gerekir. Aktarımın kendisi ayrıca dayanaklandırılır:

- Yurt içi: m.8 hükümleri,
- Yurt dışı: m.9 hükümleri (yeterlilik / uygun güvence / arızi).

İki dayanak da bağımsız olarak sağlanmalıdır. Mevcut işleme şartı tek başına aktarımı meşrulaştırmaz.

## 6. Sorumluluklar

| Rol | Sorumluluk |
|-----|------------|
| Yönetim Kurulu | Yurt dışı aktarım stratejisinin onayı; standart sözleşme şablonlarının kabulü |
| KVKK Sorumlusu | Aktarım envanterinin yönetimi; her aktarım için Aktarım Etki Değerlendirmesi (TIA); standart sözleşme bildirimleri; Kurul'a 5 iş günü içinde bildirim |
| Hukuk Müdürlüğü | Sözleşme metinlerinin hukuki gözden geçirmesi; alıcı ülke hukuku analizi; Kurul izin başvuruları |
| Bilgi Güvenliği | Teknik tedbirlerin uygulanması (şifreleme, anahtar yönetimi, ek tedbirler); aktarım altyapısının güvenliği |
| Satınalma | Sözleşmeye standart sözleşme/DPA zorunluluğunun ihale aşamasında yansıtılması |
| BT | Teknik aktarım uygulamasının yapılması; bulut sağlayıcı tercihinin uygunluk analizi ile yapılması |
| İş Birimleri | Yeni aktarım talebinin KVKK Sorumlusu'na bildirilmesi; iş gerekçesi |

## 7. Bu Bölümün Diğer Bölümlerle İlişkisi

- **02 — Envanter ve Sicil:** Aktarım envanteri (alıcı, ülke, kategori, dayanak) bu bölümün veri kaynağıdır; VERBİS bildirimine yansır.
- **03 — Aydınlatma ve Açık Rıza:** Aktarımın hukuki sebebi açık rıza ise rıza metni bu bölümle uyumlu yazılır.
- **05 — Teknik Tedbirler:** Aktarımda ek teknik tedbirler (şifreleme, IP filtreleme, anahtar yönetimi).
- **08 — İhlal Yönetimi:** Yurt dışı aktarımdaki ihlal kayıtları ek özen gerektirir.
- **10 — Özel Konular:** Bulut, çağrı merkezi, e-ticaret aktarım rotaları.

## 8. Denetim ve KPI

- Aktarım sayısının envanter ile uyumu
- Standart sözleşme imzalı aktarım oranı (>%95 hedef)
- 5 iş günü içinde bildirim oranı (%100 hedef)
- TIA tamamlanmamış aktarım sayısı (=0 hedef)
- Açık rızaya bağlı yurt dışı aktarım oranı (mümkün olduğunca düşük; rıza geri çekilebilir)

## 9. Mevzuat Atfı

- 6698 sayılı KVKK — m.5, m.6, m.8, m.9 (12.03.2024 / 7499 sayılı Kanun ile değişik)
- 12.03.2024 tarihli ve 32487 sayılı Resmî Gazete — 7499 sayılı Kanun (yürürlük 01.06.2024)
- KVKK Kurulu'nun 04.06.2024 tarihli ve 2024/959 sayılı kararı — Standart Sözleşmeler ve BCR
- "Yeterli Korumanın Bulunduğu Ülkeler" Kurul Listesi (Kurum web sitesinde güncel)
- Kurum tarafından yayımlanan "Yurt Dışına Aktarıma İlişkin Rehber"
