---
Doküman / Document: VERBİS Kayıt Rehberi / VERBİS (Data Controllers' Registry Information System) Registration Guide
Bölüm / Section: 02-envanter-ve-sicil
Sahip / Owner: KVKK Sorumlusu / KVKK Officer
Onaylayan / Approved by: Hukuk Müdürü + KVKK Komitesi / Head of Legal + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş (mevzuat değişikliği, organizasyonel değişim) / Annual + triggered (legislative change, organisational change)
İlgili Mevzuat / Legal Reference: 6698 sayılı KVKK m.16 / Law No. 6698 (KVKK) Art. 16; Veri Sorumluları Sicili Hakkında Yönetmelik MADDE 4, 5, 7, 8, 9, 10, 11, 12, 13, 14, 17 / Regulation on the Data Controllers' Registry Art. 4, 5, 7, 8, 9, 10, 11, 12, 13, 14, 17
---

## English

# VERBİS Registration Guide

VERBİS (Veri Sorumluları Sicil Bilgi Sistemi — Data Controllers' Registry Information System) is the internet-based system created and operated by the Personal Data Protection Authority for use in registry applications and other registry transactions (Reg. Art. 4/o).

VERBİS address: **https://verbis.kvkk.gov.tr**

## 1. When the Registration Obligation Begins (Reg. Art. 8)

| Situation | Period |
|-----------|--------|
| Rule — Reg. Art. 8(1) | Data controllers must complete their registration obligations **before they start processing personal data**. |
| Becoming subject afterwards — Reg. Art. 8(2) | Data controllers not previously subject to the registration obligation must register within **thirty days** of becoming subject. |
| Request for additional time — Reg. Art. 8(3) | In cases of factual, technical or legal impossibility, written application to the Authority within **7 business days** of the impossibility arising. The Authority may grant additional time, on a one-off basis and not exceeding **thirty days**. |
| Change notification — Reg. Art. 13 | Any change in registered information must be notified via VERBİS within **7 days**. |
| Removal of registration — Reg. Art. 14 | If the activity that triggers registration ceases, the registration is removed. **Obligations relating to the registered period continue.** |

## 2. Coverage Check (Are We Subject to VERBİS?)

For an organisation with 500+ employees, coverage is virtually certain. For detailed threshold analysis, see [verbis-istisna-degerlendirmesi.md](./verbis-istisna-degerlendirmesi.md).

**Quick check:**
- Annual employee count above 50? **Yes → Subject.**
- Annual financial balance sheet above the threshold? **Yes → Subject.**
- Main activity is the processing of special-category personal data (e.g., a healthcare institution)? **Yes → Subject (regardless of threshold).**
- Established outside Turkey? **Yes → Subject through a data controller representative (Reg. Art. 5/b).**

## 3. Content of the Notification (Reg. Art. 9)

A registration application contains the following information (Reg. Art. 9/1):

| # | Item | Explanation |
|---|------|-------------|
| a | Identity and address information of the data controller, any data controller representative, and the contact person | Application form (as set by the Board) |
| b | Purposes for which personal data will be processed | From the inventory — using VERBİS headings |
| c | Data subject groups and categories of their data | From the inventory — using VERBİS headings |
| ç | Recipients or recipient groups to whom personal data may be transferred | From the inventory — using VERBİS headings |
| d | Personal data envisaged to be transferred to foreign countries | From the inventory — using VERBİS headings |
| e | Measures taken according to the criteria determined by the Board under KVKK Art. 12 | From the inventory — VERBİS headings + "Other" |
| f | The **maximum retention period** prescribed by legislation or required for the processing purpose | Mapped to data categories |

**Important (Reg. Art. 9/4):** If a period is prescribed by law it is taken; otherwise the **longest** of the various periods is used. When determining the period, sectoral practice, duration of the legal relationship, duration of legitimate interest, risk-cost, suitability for keeping up-to-date, statutory obligations, and statute of limitations are considered.

**The "Other" heading (Reg. Art. 9/6):** If VERBİS standard headings do not fully cover the data controller's activities, the "Other" field is used to complete the notification.

## 4. VERBİS Registration — Step-by-Step Operational Flow

### 4.1 Preparation Phase (Before Starting Registration)

| Step | Owner | Time |
|------|-------|------|
| 1. Prepare a VERBİS-mapped summary of the KVKİ inventory | KVKK Officer | 1-2 weeks |
| 2. Identify the contact person and obtain authorisation decision (Reg. Art. 11) | Board of Directors | 1 day |
| 3. Have a KEP (Registered Electronic Mail) address ready (obtain if missing) — Reg. Art. 4/g, Art. 12 | IT | 1-2 weeks |
| 4. Provide corporate e-Government access (authorised natural person) | IT | 1 day |
| 5. Have an approved Retention and Destruction Policy (Erasure-Destruction Reg. Art. 5) | Legal + KVKK Committee | beforehand |

### 4.2 System Steps

> **Warning:** The screen names below are updated from time to time by the Authority. While following the steps, consult the VERBİS help documentation and FAQ pages.

#### Step 1 — User Registration

1. Go to https://verbis.kvkk.gov.tr.
2. Click "Sicile Kayıt" → "Veri Sorumlusu Yönetici Girişi" (Registry Sign-up → Data Controller Manager Login).
3. The authorised person logs in via e-Government (T.R. ID + e-Government password / mobile signature / e-signature).
4. On first login the system creates a **Data Controller Manager** profile using identity information from e-Government.

#### Step 2 — Data Controller Information

For a legal entity:
- Tax identification number, MERSİS (Central Registry System) number
- Full title (as registered in the Trade Registry)
- Registered (head office) address
- KEP address
- Contact phone number, corporate e-mail

#### Step 3 — Designating the Contact Person (Reg. Art. 11/4)

The contact person:
- Is a natural person resident in Turkey.
- Their T.R. ID number, name-surname, corporate e-mail, corporate phone, and title are entered.
- **Important:** The contact person is **not** authorised to represent the data controller. Their role is solely to facilitate communication with the Authority and in connection with data subject requests.

#### Step 4 — Sector / Business Field Information

- The company's field of activity is selected (NACE-code based).
- An incorrect sector selection can cause errors in correspondence with the Authority.

#### Step 5 — Notification of Processing Activities

This step is fed by the inventory. VERBİS provides **standard headings**; the inventory is mapped to them.

**Sections to complete:**

| Section | Content |
|---------|---------|
| Processing Purposes | Standard list + "Other" |
| Data Subject Groups | Standard list (Employee, Customer, Supplier, Visitor, etc.) + "Other" |
| Data Categories | Standard list (Identity, Contact, Finance, etc.) — special category flagged separately |
| Recipients / Recipient Groups | Standard list (Authorised public bodies, business partners, suppliers, etc.) + "Other" |
| Cross-Border Transfers | Yes/No; if yes, data category + country |
| Data Security Measures | KVKK Art. 12 standard list + "Other" |
| Retention Periods | Numerical period per data category |

> In each section, the "Other" option is used to explain information that does not fit the standard headings (Reg. Art. 9/6).

#### Step 6 — Notification Approval and Publication

- After all fields are completed, a "Notification Preview" screen appears.
- Approval of the KVKK Officer and Legal Department is obtained.
- Click "Submit Notification".
- The system generates a reference number and a PDF summary. Archive this PDF.

#### Step 7 — Information Disclosed Publicly (Reg. Art. 7)

The following information is publicly disclosed from the Registry:

- Name, address and KEP of the data controller, any representative and the contact person
- Processing purposes
- Person groups + data categories
- Recipients + recipient groups
- Cross-border transfers
- Date of registration and date of removal
- Data security measures
- Maximum retention period

> This information is visible on the company's website and on the publicly accessible Registry search of the Authority. Misleading or incomplete information is subject to administrative fines (Reg. Art. 17, KVKK Art. 18).

## 5. Change Notification (Reg. Art. 13)

Any change in registered information must be notified to the Authority via VERBİS within **7 days**.

### 5.1 Events that Trigger a Change

| Event | Affected Section |
|-------|------------------|
| Change of company title | Data controller information |
| Address change | Data controller information |
| KEP address update | Contact information |
| Change of contact person | Contact person information |
| New process launched (new purpose, new person group) | Processing activities |
| New recipient group (new supplier type) | Recipients/recipient groups |
| Cross-border transfer commenced | Cross-border transfers |
| Update of retention period | Retention periods |
| New technical measure added / removed | Data security measures |
| Discontinuation of a process | Processing activities |

### 5.2 Change Notification Process

```
1. Process owner files change request → KVKK Officer
2. Inventory update (same day)
3. Verification by Legal + KVKK Officer
4. Update relevant fields in VERBİS
5. Re-archive PDF summary
6. Notify process owner
```

> The 7-day period runs as **calendar days**. Missing the deadline triggers risk of administrative fines under Reg. Art. 17 / KVKK Art. 18(1)(ç).

## 6. Removal from the Registry (Reg. Art. 14)

If the activity that triggers the registration obligation ceases or no longer exists, the data controller files for removal via VERBİS (Reg. Art. 14/1).

**Key points:**
- Removal is not automatic; the Authority reviews the application.
- Removed records remain accessible but **cannot be modified** (Reg. Art. 14/2).
- Removal does not extinguish obligations relating to the registered period (Reg. Art. 14/3). Inventory, retention-destruction policy, breach handling, etc. continue for the registered period.

## 7. Communication Channels (Reg. Art. 12)

All communications by the Authority with the data controller are made through the contact information provided to the Registry:

| Data controller type | Communication channel |
|----------------------|------------------------|
| Legal person resident in Turkey | Identity, address and KEP of the legal person registered with the Registry (Reg. Art. 12/a) |
| Natural person resident in Turkey | Identity, address and KEP of the natural person registered with the Registry (Reg. Art. 12/b) |
| Data controller not resident in Turkey | Through the data controller representative registered with the Registry (Reg. Art. 12/c) |

> A **KEP (Registered Electronic Mail) address** under Reg. Art. 4/g is the qualified form of e-mail providing legal evidence of the dispatch and delivery of electronic messages. A significant portion of the Authority's notifications occurs via KEP; the KEP address must be monitored continuously.

## 8. Contact Person vs. Data Controller Representative vs. KVKK Officer

These three concepts are commonly conflated:

| Role | Legal definition | Authority |
|------|------------------|-----------|
| **Data Controller** | The legal person itself (Reg. Art. 11/1) | The legal person bears the obligation |
| **Data Controller Representative** | The Turkey-resident representative of a data controller not resident in Turkey (Reg. Art. 4/p, Art. 11/2) | Authorities listed in Reg. Art. 11/3 (receiving notices, forwarding requests, registry transactions) |
| **Contact Person** | The Turkey-resident natural person designated for legal entities resident in Turkey and for foreign representatives, for communication with the Authority (Reg. Art. 4/ç, Art. 11/4) | Communication only; **no** representation authority |
| **KVKK Officer** | Internal corporate role — not a registered position; operational responsibility | Defined by internal policy |

> Designating the same individual as both contact person and KVKK Officer is operationally advantageous, although not legally required.

## 9. Common Errors and Corrections

| Error | Consequence | Correction |
|-------|-------------|-----------|
| Doing VERBİS registration without an inventory | Breach of Reg. Art. 5/ç; misleading registry information possible | Inventory first, then VERBİS |
| Marking cross-border transfer as "No" while SaaS is abroad | Misleading registry information; potential breach of Art. 9 | Verify SaaS locations, file correct notification |
| Writing "as needed" as the retention period | Indeterminate period — breach of Reg. Art. 9/4 | Specific numerical period + rationale |
| Missing the 7-day change notification | Breach of Reg. Art. 13; administrative fine | Quarterly audit calendar |
| KEP address not monitored | Authority notice missed | At least two persons monitor the KEP |
| Presenting the contact person as a representative | Legal confusion, slower request handling | Define the role correctly in internal policy |
| Not using "Other" for purposes outside standard headings | Incomplete notification | Reg. Art. 9/6 — fill the "Other" field |
| Mismatch between publicly available information and the website information notice | Breach of Reg. Art. 5/d, picked up in Authority audits | Quarterly alignment check |

## 10. Operational Routine After Registration

### 10.1 Quarterly Controls

| Control | Frequency |
|---------|-----------|
| KEP address monitoring protocol | Daily |
| VERBİS record summary — alignment with inventory | Quarterly |
| Alignment between publicly disclosed information and the website | Quarterly |
| Currency of contact person information | Quarterly |
| Retention periods and legislative changes | Annual |
| Cross-border transfer — contracts and legal basis confirmation | Annual |

### 10.2 Internal Document Layout

```
/02-envanter-ve-sicil/
   /verbis-bildirim-pdfs/
      /2026/
         2026-Q2-bildirim-v1.0.pdf
         2026-Q3-degisiklik-v1.1.pdf
   /irtibat-kisisi-yetki/
      yetkilendirme-kararı-2026.pdf
   /kayit-iletisim-loglari/
      KEP-takip-listesi.xlsx
```

## 11. Administrative Sanctions (Reg. Art. 17, KVKK Art. 18)

Breach of registration and notification obligations attracts administrative fines under KVKK Art. 18(1)(ç). Fine amounts are revalued annually; the current figure must be checked against the Authority's annual announcement.

> **Practical advice:** The fine is set within statutory minimum-maximum range at the Board's discretion. Incomplete/misleading notifications attract amounts close to the maximum, while simple delays may attract amounts closer to the minimum. Inventory accuracy and discipline in change notifications therefore directly drive financial impact.

## 12. Quick Reference Card

```
[ ] Inventory ready and approved
[ ] Contact person assigned, authorisation decision issued
[ ] KEP address active and monitored
[ ] Authorised person identified for e-Government login
[ ] VERBİS notification submitted, PDF archived
[ ] "Registry Information" section added to the website
[ ] Information notices aligned with the Registry
[ ] Quarterly audit calendar in place
[ ] Change triggers defined
[ ] 7-day change notification discipline trained
```

## 13. Annexes

- Inventory Guide: [kvki-envanteri-rehberi.md](./kvki-envanteri-rehberi.md)
- Template: [envanter-sablonu.md](./envanter-sablonu.md)
- Exception Assessment: [verbis-istisna-degerlendirmesi.md](./verbis-istisna-degerlendirmesi.md)
- Maintenance: [envanter-bakim.md](./envanter-bakim.md)

---

## Türkçe

# VERBİS Kayıt Rehberi

VERBİS (Veri Sorumluları Sicil Bilgi Sistemi), Kişisel Verileri Koruma Kurumu Başkanlığı tarafından oluşturulan ve yönetilen, Sicile başvuruda ve Sicile ilişkin diğer işlemlerde kullanılan internet üzerinden erişilebilen bilişim sistemidir (Yön. M.4/o).

VERBİS adresi: **https://verbis.kvkk.gov.tr**

## 1. Kayıt Yükümlülüğünün Başlangıcı (Yön. M.8)

| Durum | Süre |
|-------|------|
| Kural — Yön. M.8(1) | Veri sorumluları, **kişisel veri işlemeye başlamadan önce** Sicile kayıt yükümlülüklerini yerine getirmek zorundadır. |
| Sonradan yükümlü olanlar — Yön. M.8(2) | Kayıt yükümlülüğü altında bulunmayan, sonradan yükümlü hale gelen veri sorumluları, yükümlülük altına girmelerini müteakip **otuz gün** içerisinde Sicile kaydolur. |
| Ek süre talebi — Yön. M.8(3) | Fiili, teknik veya hukuki imkansızlık halinde, imkansızlığın ortaya çıktığı tarihten itibaren en geç **7 iş günü** içerisinde Kuruma yazılı başvuru ve gerekçe ile ek süre talep edilebilir. Kurum, bir defaya mahsus olmak ve her halde **otuz günü geçmemek** üzere ek süre verebilir. |
| Değişiklik bildirimi — Yön. M.13 | Sicilde kayıtlı bilgilerde değişiklik halinde **7 gün** içinde VERBİS üzerinden Kuruma bildirim. |
| Kayıt silinmesi — Yön. M.14 | Kayıt yükümlülüğünü gerektiren faaliyet sona ererse, sicil kaydı silinir. **Kayıtlı dönemdeki yükümlülükler ortadan kalkmaz.** |

## 2. Yükümlülük Kontrolü (Bizim Şirketimiz Yükümlü mü?)

500+ çalışanlı bir kuruluş için yükümlülük neredeyse kesindir. Detaylı eşik analizi için bkz. [verbis-istisna-degerlendirmesi.md](./verbis-istisna-degerlendirmesi.md).

**Hızlı kontrol:**
- Yıllık çalışan sayısı 50'den fazla mı? **Evet → Yükümlü.**
- Yıllık mali bilanço toplamı eşik üstünde mi? **Evet → Yükümlü.**
- Ana faaliyet özel nitelikli kişisel veri işlemek mi? (örn. sağlık kuruluşu) **Evet → Yükümlü (eşik bağımsız).**
- Yurt dışında yerleşik mi? **Evet → Veri sorumlusu temsilcisi marifetiyle yükümlü (Yön. M.5/b).**

## 3. Kayıt Bildiriminin İçeriği (Yön. M.9)

Sicile yapılan kayıt başvurusu aşağıdaki bilgileri içerir (Yön. M.9/1):

| # | Madde | Açıklama |
|---|-------|----------|
| a | Veri sorumlusu, varsa veri sorumlusu temsilcisi ve irtibat kişisine ait kimlik ve adres bilgileri | Başvuru formu (Kurul tarafından belirlenir) |
| b | Kişisel verilerin hangi amaçla işleneceği | Envanterden — VERBİS başlıkları kullanılarak |
| c | Veri konusu kişi grubu ve grupları ile bu kişilere ait veri kategorileri | Envanterden — VERBİS başlıkları kullanılarak |
| ç | Kişisel verilerin aktarılabileceği alıcı veya alıcı grupları | Envanterden — VERBİS başlıkları kullanılarak |
| d | Yabancı ülkelere aktarımı öngörülen kişisel veriler | Envanterden — VERBİS başlıkları kullanılarak |
| e | KVKK m.12 öngörülen ve Kurul tarafından belirlenen kriterlere göre alınan tedbirler | Envanterden — VERBİS başlıkları + "Diğer" başlığı |
| f | Kişisel verilerin mevzuatta öngörülen veya işlendikleri amaç için gerekli olan **azami muhafaza edilme süresi** | Veri kategorileri ile eşleştirilerek |

**Önemli (Yön. M.9/4):** Mevzuatta süre öngörülmüşse o süre, yoksa farklı süreler arasından **en uzunu** esas alınır. Süre belirlenirken sektörel teamül, hukuki ilişki süresi, meşru menfaat süresi, risk-maliyet, güncel tutma elverişliliği, hukuki yükümlülük süresi ve zamanaşımı dikkate alınır.

**"Diğer" başlığı (Yön. M.9/6):** VERBİS'teki standart başlıklar veri sorumlusunun faaliyetlerini tam karşılamıyorsa, "Diğer" alanı kullanılarak bildirim tamamlanır.

## 4. VERBİS Kayıt — Adım Adım Operasyonel Akış

### 4.1 Hazırlık Aşaması (Kayda Başlamadan Önce)

| Adım | Sorumlu | Süre |
|------|---------|------|
| 1. KVKİ envanterinin VERBİS'e çevrilmiş özetini hazırla | KVKK Sorumlusu | 1-2 hafta |
| 2. İrtibat kişisini belirle ve yetkilendirme kararı al (Yön. M.11) | Yönetim Kurulu | 1 gün |
| 3. KEP adresini hazır et (yoksa al) — Yön. M.4/g, M.12 | Bilgi İşlem | 1-2 hafta |
| 4. Kurumsal e-Devlet erişimi sağla (yetkili gerçek kişi) | Bilgi İşlem | 1 gün |
| 5. Saklama ve İmha Politikası onaylanmış olsun (Saklama ve İmha Yön. M.5) | Hukuk + KVKK Komitesi | önceden |

### 4.2 Sistem Üzerinde Adımlar

> **Uyarı:** Aşağıdaki ekran adları KVKK Kurumu tarafından zaman zaman güncellenmektedir. Adımları takip ederken VERBİS yardım dokümanı ve "Sıkça Sorulan Sorular" sayfası kontrol edilmelidir.

#### Adım 1 — Kullanıcı Kaydı

1. https://verbis.kvkk.gov.tr adresine gidin.
2. "Sicile Kayıt" → "Veri Sorumlusu Yönetici Girişi" linkine tıklayın.
3. Yetkili kişi e-Devlet üzerinden giriş yapar (T.C. kimlik + e-Devlet şifresi / mobil imza / e-imza).
4. İlk girişte sistem, e-Devlet'ten gelen kimlik bilgilerini kullanarak **Veri Sorumlusu Yöneticisi** profili oluşturur.

#### Adım 2 — Veri Sorumlusu Bilgileri

Tüzel kişi için:
- Vergi kimlik numarası, MERSİS numarası
- Tam ünvan (ticaret sicilinden tam alınmış)
- Adres bilgileri (merkez)
- KEP adresi
- İletişim numarası, kurumsal e-posta

#### Adım 3 — İrtibat Kişisi Atama (Yön. M.11/4)

İrtibat kişisi:
- Türkiye'de yerleşik bir gerçek kişidir.
- T.C. kimlik numarası, ad-soyad, kurumsal e-posta, kurumsal telefon, görev unvanı bilgileri girilir.
- **Önemli:** İrtibat kişisi, veri sorumlusunu temsile yetkili **değildir**. Görevi yalnızca Kurum ile iletişim ve ilgili kişi taleplerine ilişkin iletişim sağlamaktır.

#### Adım 4 — Lev (Faaliyet Alanı / Sektör) Bilgileri

- Şirketin faaliyet alanı seçilir (NACE kodu temelli).
- Sektör seçimi yanlış yapılırsa Kurum yazışmalarında hata oluşabilir.

#### Adım 5 — İşleme Faaliyetlerinin Bildirimi

Bu adım envanterden beslenir. VERBİS, **standart başlıklar** sunar; envanter bu başlıklarla eşlenir.

**Doldurulacak bölümler:**

| Bölüm | İçerik |
|-------|--------|
| İşleme Amaçları | Standart liste + "Diğer" |
| Veri Konusu Kişi Grupları | Standart liste (Çalışan, Müşteri, Tedarikçi, Ziyaretçi, vb.) + "Diğer" |
| Veri Kategorileri | Standart liste (Kimlik, İletişim, Finans, vb.) — özel nitelikli ayrı işaretlenir |
| Alıcı / Alıcı Grupları | Standart liste (Yetkili kamu kurumları, iş ortakları, tedarikçiler, vb.) + "Diğer" |
| Yabancı Ülkelere Aktarım | Aktarım var/yok; varsa veri kategorisi + ülke |
| Veri Güvenliği Tedbirleri | KVKK m.12 standart liste + "Diğer" |
| Saklama Süreleri | Veri kategorisi bazında — sayısal süre |

> Her bölümde "Diğer" seçeneği zorunlu olmayan bilgiyi açıklamak için kullanılır (Yön. M.9/6).

#### Adım 6 — Bildirim Onayı ve Yayım

- Tüm alanlar doldurulduktan sonra "Bildirim Önizleme" ekranı görüntülenir.
- KVKK Sorumlusu ve Hukuk Müdürlüğü onayı alınır.
- "Bildirimi Tamamla" tıklanır.
- Sistem, bir referans numarası ve PDF özeti üretir. Bu PDF arşivlenir.

#### Adım 7 — Kamuya Açılan Bilgiler (Yön. M.7)

Sicilden aşağıdaki bilgiler kamuya açıklanır:

- Veri sorumlusu, varsa temsilcisi ve irtibat kişisinin adı, adresi, KEP
- İşleme amaçları
- Kişi grupları + veri kategorileri
- Alıcı + alıcı grupları
- Yabancı ülkelere aktarım
- Sicile kayıt tarihi ve sona erdiği tarih
- Veri güvenliği tedbirleri
- Azami saklama süresi

> Bu bilgiler şirketin web sitesinde ve KVKK Kurumu kamuya açık sicil arama servisinde görünür. Yanıltıcı veya eksik bilgi vermenin idari para cezası yaptırımı vardır (Yön. M.17, KVKK m.18).

## 5. Değişiklik Bildirimi (Yön. M.13)

Sicilde kayıtlı bilgilerde **herhangi bir değişiklik** olursa, VERBİS üzerinden **7 gün** içinde Kurum'a bildirim yapılır.

### 5.1 Değişikliği Tetikleyen Olaylar

| Olay | Etkilenen Bölüm |
|------|-----------------|
| Şirket ünvan değişimi | Veri sorumlusu bilgileri |
| Adres değişikliği | Veri sorumlusu bilgileri |
| KEP adresi güncellenmesi | İletişim bilgileri |
| İrtibat kişisi değişimi | İrtibat kişisi bilgileri |
| Yeni süreç başlatılması (yeni amaç, yeni kişi grubu) | İşleme faaliyetleri |
| Yeni alıcı grubu eklenmesi (yeni tedarikçi tipi) | Alıcı/alıcı grupları |
| Yurt dışı aktarım başlatılması | Yabancı ülkelere aktarım |
| Saklama süresi güncellenmesi | Saklama süreleri |
| Yeni teknik tedbir devreye alma / kaldırma | Veri güvenliği tedbirleri |
| Bir sürecin durdurulması | İşleme faaliyetleri |

### 5.2 Değişiklik Bildirim Süreci

```
1. Süreç sahibinden değişiklik talebi → KVKK Sorumlusu
2. Envanter güncellemesi (aynı gün)
3. Hukuk + KVKK Sorumlusu doğrulaması
4. VERBİS'te ilgili alanlar güncellenir
5. PDF özeti tekrar arşivlenir
6. Süreç sahibine bildirim
```

> 7 günlük süre **takvim günü** olarak işler. Geçirildiğinde Yön. M.17 uyarınca KVKK m.18(1)(ç) idari para cezası riski doğar.

## 6. Sicil Kaydının Silinmesi (Yön. M.14)

Kayıt yükümlüğünü gerektiren faaliyet sona erer veya ortadan kalkarsa, veri sorumlusu VERBİS üzerinden silme başvurusu yapar (Yön. M.14/1).

**Önemli noktalar:**
- Silme başvurusu otomatik kabul değildir; Kurum inceler.
- Silinmiş kayıtlar erişilebilir kalır ancak **değiştirilemez** (Yön. M.14/2).
- Sicil kaydının silinmesi, kayıtlı dönemdeki yükümlülükleri ortadan kaldırmaz (Yön. M.14/3). Yani envanter, saklama-imha politikası, ihlal yönetimi gibi yükümlülükler kayıtlı dönem için sürer.

## 7. İletişim Kanalları (Yön. M.12)

Kurum tarafından veri sorumlusuyla kurulacak her türlü iletişim, Sicile bildirilen iletişim bilgileri üzerinden gerçekleştirilir:

| Veri sorumlusu tipi | İletişim kanalı |
|--------------------|------------------|
| Türkiye'de yerleşik tüzel kişi | Sicile bildirilen kimlik, adres, KEP üzerinden tüzel kişi (Yön. M.12/a) |
| Türkiye'de yerleşik gerçek kişi | Sicile bildirilen kimlik, adres, KEP üzerinden gerçek kişi (Yön. M.12/b) |
| Türkiye'de yerleşik olmayan veri sorumlusu | Sicile bildirilen veri sorumlusu temsilcisi (Yön. M.12/c) |

> **KEP adresi** Yön. M.4/g uyarınca elektronik iletilerin gönderim ve teslimine ilişkin hukuki delil sağlayan, elektronik postanın nitelikli şeklidir. Kurum tebligatlarının önemli bir kısmı KEP üzerinden yapılır; KEP adresinin sürekli izlenmesi zorunludur.

## 8. İrtibat Kişisi vs. Veri Sorumlusu Temsilcisi vs. KVKK Sorumlusu

Üç kavram sıkça karıştırılır:

| Rol | Hukuki tanım | Yetki |
|-----|-------------|-------|
| **Veri Sorumlusu** | Tüzel kişiliğin kendisi (Yön. M.11/1) | Yükümlülük tüzel kişide |
| **Veri Sorumlusu Temsilcisi** | Türkiye'de yerleşik olmayan veri sorumlusunun Türkiye'deki temsilcisi (Yön. M.4/p, M.11/2) | Yön. M.11/3 listesindeki yetkiler (tebligat alma, başvuru iletme, Sicil işlemleri) |
| **İrtibat Kişisi** | Türkiye'de yerleşik tüzel kişiler ve yabancı temsilciler için Kurum ile iletişim için belirlenen gerçek kişi (Yön. M.4/ç, M.11/4) | Sadece **iletişim**; temsil yetkisi **YOK** |
| **KVKK Sorumlusu** | Şirket içi rol — kayıt değil, operasyonel sorumluluk | İç yönergeyle belirlenir |

> İrtibat kişisi seçilirken bu rolün KVKK Sorumlusu ile aynı kişide olması operasyonel olarak avantajlıdır; ancak hukuken zorunlu değildir.

## 9. Yaygın Hatalar ve Düzeltme

| Hata | Sonuç | Düzeltme |
|------|-------|----------|
| Envanter yokken VERBİS kaydı yapma | Yön. M.5/ç ihlali; Sicil bilgileri yanıltıcı olabilir | Önce envanter, sonra VERBİS |
| Yurt dışı aktarımı "Hayır" işaretleme (oysa SaaS yurt dışı) | Sicil bilgileri yanıltıcı; m.9 ihlali olası | SaaS lokasyonları teyit, doğru bildirim |
| Saklama süresi olarak "ihtiyaç olduğu sürece" yazma | Belirsiz süre — Yön. M.9/4 ihlali | Belirli sayısal süre + gerekçe |
| 7 günlük değişiklik bildirimini kaçırma | Yön. M.13 ihlali; idari para cezası | Çeyreklik denetim takvimi |
| KEP adresi izlenmiyor | Kurum tebligatı kaçırılıyor | KEP'i en az iki kişinin izlemesi |
| İrtibat kişisini yetkili gibi sunma | Hukuki kafa karışıklığı, başvuru cevap süreci aksaması | Rolün doğru tanımlanması, iç yönerge |
| Standart başlıklarda yer almayan amaç için "Diğer" alanını kullanmama | Eksik bildirim | Yön. M.9/6 — "Diğer" alanı doldurulur |
| Kamuya açık bilgilerle web sitesindeki Aydınlatma Metni'nin uyumsuzluğu | Yön. M.5/d ihlali, Kurul incelemelerinde tespit | Çeyreklik uyum kontrolü |

## 10. Kayıt Sonrası Operasyonel Düzen

### 10.1 Çeyreklik Kontroller

| Kontrol | Sıklık |
|---------|--------|
| KEP adresi izleme protokolü | Günlük |
| VERBİS kayıt özeti — envanter ile uyum | Çeyreklik |
| Kamuya açık bilgilerin web sitesi ile uyumu | Çeyreklik |
| İrtibat kişisi bilgileri güncelliği | Çeyreklik |
| Saklama süreleri ve mevzuat değişikliği | Yıllık |
| Yurt dışı aktarım — sözleşme ve hukuki temel teyidi | Yıllık |

### 10.2 İç Belge Setinin Düzeni

```
/02-envanter-ve-sicil/
   /verbis-bildirim-pdfs/
      /2026/
         2026-Q2-bildirim-v1.0.pdf
         2026-Q3-degisiklik-v1.1.pdf
   /irtibat-kisisi-yetki/
      yetkilendirme-kararı-2026.pdf
   /kayit-iletisim-loglari/
      KEP-takip-listesi.xlsx
```

## 11. İdari Yaptırım (Yön. M.17, KVKK m.18)

Sicile kayıt ve bildirim yükümlülüğüne aykırılık halinde KVKK m.18(1)(ç) bendinde yer alan idari para cezası uygulanır. Para cezası tutarları her yıl yeniden değerleme oranında güncellenir; güncel tutar için Kurum'un yıllık duyurusu kontrol edilmelidir.

> **Pratik tavsiye:** Para cezası, Kurul'un takdir yetkisi içinde alt-üst sınır arasında belirlenir. Eksik/yanıltıcı bildirim üst sınıra, basit gecikme alt sınıra yakın değerlendirilir. Bu nedenle envanter doğruluğu ve değişiklik bildirim disiplini doğrudan finansal etkiyi belirler.

## 12. Hızlı Referans Kartı

```
[ ] Envanter hazır ve onaylı
[ ] İrtibat kişisi atandı, yetkilendirme kararı alındı
[ ] KEP adresi aktif, izleniyor
[ ] e-Devlet üzerinden giriş yapan yetkili belirlendi
[ ] VERBİS bildirimi tamamlandı, PDF arşivlendi
[ ] Web sitesinde "Sicil Bilgileri" bölümü eklendi
[ ] Aydınlatma metinleri Sicil ile uyumlu
[ ] Çeyreklik denetim takvimi kuruldu
[ ] Değişiklik tetikleyicileri tanımlandı
[ ] 7 günlük değişiklik bildirim disiplini eğitildi
```

## 13. Ekler

- Envanter Rehberi: [kvki-envanteri-rehberi.md](./kvki-envanteri-rehberi.md)
- Şablon: [envanter-sablonu.md](./envanter-sablonu.md)
- İstisna Değerlendirme: [verbis-istisna-degerlendirmesi.md](./verbis-istisna-degerlendirmesi.md)
- Bakım: [envanter-bakim.md](./envanter-bakim.md)
