---
Doküman / Document: Standart Sözleşme Rehberi / Standard Contract Guide
Bölüm / Section: 07-aktarim
Sahip / Owner: Hukuk Müdürlüğü + KVKK Sorumlusu / Legal Department + KVKK Officer
Onaylayan / Approved by: Hukuk Müdürü + Bilgi Güvenliği Yöneticisi / Legal Director + Information Security Manager
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş / Annual + triggered (Board standard text update, new recipient, sectoral change)
İlgili Mevzuat / Legal Reference: KVKK Art. 9/4-(c); Personal Data Protection Board Decision No. 2024/959 dated 04.06.2024
---

## English

# Standard Contract Guide

## 1. Legal Framework

Pursuant to KVKK Art. 9/4-(c), transfer of personal data to countries without adequate protection may be made provided that the **standard contract declared by the Board** is signed between the parties and notified to the Authority. The standard contract covers data categories, transfer purposes, recipient and recipient groups, technical and administrative measures to be taken by the recipient, and supplementary measures for special category personal data.

By **Personal Data Protection Board Decision No. 2024/959 dated 04.06.2024**, four standard contract texts have been published.

Note: This is the Turkish KVKK regime's "standard contract" (a domestic instrument), distinct from EU GDPR Standard Contractual Clauses (SCCs).

## 2. Structure of the Standard Contract

The standard contract typically consists of:

| Section | Content |
|---------|---------|
| Preamble | Identity of parties, purpose, definitions |
| Scope of transfer | Data categories, data subject groups, processing purposes, recipients, recipient country |
| Obligations of the parties | Obligations of transferring and receiving party |
| Data subject rights | Rights of data subject, route to exercise, third-party-beneficiary right |
| Technical and administrative measures | Encryption, access control, breach management, audit |
| Special category data | Supplementary measures |
| Sub-processors | Sub-processor use, authorization, chain liability |
| Term and termination | Duration, reasons for termination, destruction/return upon termination |
| Liability and indemnity | Mutual indemnity provisions |
| Governing law | Republic of Turkey law |
| Jurisdiction | Turkish courts |
| Annexes | Transfer scope table, technical+administrative measures table, sub-processor list |

## 3. Contract Types and Selection

### 3.1. Four Types

| Code | Turkey Side | Foreign Side | Typical Scenario |
|------|-------------|--------------|------------------|
| Type 1 | Controller (C) | Controller (C) | Intra-group transfer (no BCR); shared customer portfolio |
| Type 2 | Controller (C) | Processor (P) | SaaS provider, cloud provider, call-center outsourcing |
| Type 3 | Processor (P) | Processor (P) | Turkish cloud provider transferring to foreign sub-processor |
| Type 4 | Processor (P) | Controller (C) | Turkish processor returning data to a foreign controller |

### 3.2. Type Selection Criteria

Status determination is made based on **the direction of transfer and the parties' KVKK status**. Using the wrong type renders the contract invalid.

```
Who is the transferring party?
+----------------+----------------+
|                                 |
v                                 v
Turkish                       Turkish
Controller                    Processor
|                                 |
v                                 v
Who is recipient?            Who is recipient?
+--------+                   +--------+
|        |                   |        |
v        v                   v        v
C        P                   P        C
|        |                   |        |
v        v                   v        v
Type 1  Type 2              Type 3  Type 4
```

## 4. Signing the Contract

### 4.1. Signing Process

```
1. Status and transfer scope clarified with the
   vendor/recipient.
                |
                v
2. Correct contract type selected (Legal
   Department approval).
                |
                v
3. Annexes filled in without modifying the
   standard text:
   - Transfer scope (data category, purposes)
   - Technical+administrative measures
   - Sub-processor list
                |
                v
4. Legal Department reviews; supplementary
   provisions, if any, added as a separate annex
   without modifying the standard text.
                |
                v
5. Information Security verifies that technical
   measures are concrete and accurate.
                |
                v
6. Authorized signatories sign (e-signature or
   wet signature).
                |
                v
7. Notification to the Authority within 5
   business days of signing.
                |
                v
8. Contract archived; transfer inventory and
   VERBİS updated.
```

### 4.2. Manner of Signature

- **E-signature:** Qualified electronic signature under E-Signature Law No. 5070.
- **Wet signature:** Paper contract, hand-signed by authorized signatories.
- **Authority:** The signer must have signing authority for the legal entity; signature circular checked.
- **Apostille/legalization:** Depending on country, apostille or consular legalization may be requested for the foreign party's signature; in practice, parties typically rely on mutual PDF signing.

### 4.3. Prohibition of Departure from the Contract

The standard contract text **cannot be modified**. The following interventions render the contract invalid:

- Deleting an article,
- Altering an article (including a wording change),
- Reducing the parties' obligations,
- Changing the jurisdiction outside Turkey,
- Changing the governing law.

Permitted interventions:
- **Annexes are filled in** (transfer scope, technical measures, sub-processors).
- **Supplementary clauses may be added as a separate annex protocol**, provided they **do not alter the articles of the standard text**.

### 4.4. Multiple Transfers

- **Multiple transfers between the same parties:** A single framework standard contract can be signed; all transfer scopes listed in the annex.
- **Different parties:** Separate contracts for each pair of parties.

## 5. Notification to the Authority

### 5.1. Deadline

Within **5 business days** of signing.

### 5.2. Notification Method

The electronic channel set by the Authority is used. Notification is generally made:

- Via the VERBİS / Registry portal,
- Or via a separate notification system announced by the Authority,
- Or via KEP (registered e-mail) where the Authority accepts.

### 5.3. Notification Content (Typical)

| Field | Description |
|-------|-------------|
| Transferring party info | Title, address, VERBİS registration no |
| Recipient party info | Title, address, country |
| Contract type | Type 1/2/3/4 |
| Signature date | DD/MM/YYYY |
| Purpose of transfer | Brief description |
| Transfer data categories | List |
| Data subject groups | List |
| Transfer duration | Contract term |
| The contract text itself | PDF attachment |

### 5.4. Legal Nature of Notification

- Notification is **NOT authorization**. The Authority's approval is not required.
- Notification is the **condition** of the appropriate safeguard. Failure to notify means the transfer is **deemed made without an appropriate safeguard**, despite the contract being signed.
- If notification is incomplete, the Authority may request additional information.

### 5.5. Subsequent Changes

- If parties, scope, recipient country or other core elements change, a **new** contract or **annex protocol** is signed; renotification within 5 business days.
- Termination/cancellation of the contract is also notified.

## 6. Transfer Impact Assessment (TIA)

The standard contract alone may not be sufficient; the recipient country's law and practice may impede the actual application of contractual provisions. The TIA assesses this and identifies necessary **supplementary measures**.

### 6.1. TIA Stages

```
Stage 1: Mapping the Transfer
- Data categories, category counts, sensitivity
- Data subject groups
- Purpose, frequency, duration of transfer
- Transferor and recipient; recipient country;
  any sub-processor under the recipient?

                |
                v

Stage 2: Recipient Country's Law and Practice
- Data protection legislation (existence, scope?)
- Independent supervisory authority
- Enforceability of data subject rights
- Judicial protection
- Party to international agreements

                |
                v

Stage 3: Public Authority Access
- Intelligence service access
- Law enforcement access
- Tax/financial authorities
- Oversight mechanism for access?
- "Disproportionate" access risk
- Sector-specific powers for the transfer's sector

                |
                v

Stage 4: Adequacy of the Contract
- Are standard contract + supplementary clauses
  together sufficient?
- Can the recipient actually comply with its
  contractual undertakings (no local law block)?

                |
                v

Stage 5: Supplementary Measures
- Technical: end-to-end encryption, key management
  (at source), pseudonymization, data minimization
- Contractual: additional notification obligations,
  notification of access requests, audit rights
- Organizational: access limitation, "need-to-know,"
  logging + audit

                |
                v

Stage 6: Residual Risk Assessment
- Is the residual risk acceptable after mitigation?
- If not: do not transfer / choose another route
```

### 6.2. Typical Supplementary Measures

| Risk | Supplementary Measure |
|------|------------------------|
| Disproportionate access by recipient country authorities | End-to-end encryption + keys held in Turkey |
| Weak judicial protection in recipient country | Third-party-beneficiary clause + Turkish court jurisdiction |
| Long, opaque sub-processor chain | Recipient's approved sub-processor list + prior notification of any change |
| Delay in breach notification | 24-hour notification clause |
| No notice of access requests | "Notification of access requests" clause (to extent local law permits) |
| Sensitive data without pseudonymization | Pseudonymization at source, key remains in Turkey |
| Insufficient data minimization | Pre-transfer minimization, only necessary fields |

### 6.3. TIA Short Form Template

```
TIA — Transfer Impact Assessment
═════════════════════════════════════
TIA No                : ________________
Date                  : ____/____/______
Transferor            : ________________
Recipient             : ________________
Recipient Country     : ________________
Recipient Status (C/P): ________________
Contract Type         : Type __

1. TRANSFER MAP
   Data Categories    : ________________
   Sensitivity        : General / Special category
   Data Subject Groups: ________________
   Frequency          : Continuous / Periodic / One-off
   Duration           : ________________

2. RECIPIENT COUNTRY LAW
   Data Protection Law : ____________________
   Supervisory Authority: ____________________
   Data Subject Rights : Yes / Limited / No
   Judicial Remedy     : Yes / Limited / No

3. PUBLIC AUTHORITY ACCESS RISK
   Intelligence       : Low / Medium / High
   Law Enforcement    : Low / Medium / High
   Disproportionate
   access risk        : Low / Medium / High

4. SUPPLEMENTARY MEASURES
   Technical          : ____________________
   Contractual        : ____________________
   Organizational     : ____________________

5. RESIDUAL RISK
   Risk Level         : Low / Medium / High
   Acceptability      : Yes / No
   Decision           : Transfer / Do not transfer /
                        New measure required

6. APPROVAL
   KVKK Officer       : ____________________
   Legal Director     : ____________________
   Inf. Sec. Manager  : ____________________
```

For the full form: [aktarim-degerlendirme-formu.md](aktarim-degerlendirme-formu.md)

## 7. Common Mistakes

| Mistake | Result | Mitigation |
|---------|--------|------------|
| Modifying the standard text (departure) | Contract invalid; transfer without appropriate safeguard | Standard text **does not change**; only annexes are filled |
| Wrong type selection | Contract invalid | Decision tree + Legal Department approval |
| Failure to notify within 5 business days | Appropriate safeguard not provided | Mandatory step in signing flow |
| Transfer without TIA | Supplementary measures missing; risk not assessed | TIA mandatory for every transfer |
| Sub-processor chain not addressed | Liability gap | Sub-processor list + update with every change |
| Signing authority unverified | Contract invalid | Signature circular check; corporate authority confirmation |
| Separate contract for each multi-transfer | Operational cost, oversight gaps | One framework contract + annex list |
| Using own text instead of standard | Not an appropriate safeguard; Art. 9/4-(ç) undertaking route should be followed | Standard contract is mandatory; otherwise Board authorization |
| Failure to notify contract termination | Mismatch with transfer inventory and VERBİS | Termination is also notified |

## 8. Operational Workflow (Owners)

| Step | Owner | Time |
|------|-------|------|
| Vendor status determination | KVKK Officer + Legal | 2 business days |
| Contract type selection | Legal Department | 1 business day |
| Filling in annexes | Relevant Unit + Information Security | 3 business days |
| Preparing TIA | KVKK Officer + Information Security | 5 business days |
| Legal review | Legal Department | 3 business days |
| Signing | Authorized signatory | 1-2 business days |
| Notification to Authority | KVKK Officer | **Within 5 business days** of signing |
| Inventory and VERBİS update | KVKK Officer | 2 business days |
| Disclosure update | KVKK Officer + Relevant Unit | 5 business days |

Total ideally **20-25 business days**; 4-6 weeks for complex transfers.

## 9. Standard Contract Management Records

For each contract the following record is maintained:

| Field | Description |
|-------|-------------|
| Contract No | Internal sequence (e.g. STD-2026-0042) |
| Type | Type 1/2/3/4 |
| Counterparty | Title, country, address |
| Signature date | DD/MM/YYYY |
| Effective date | DD/MM/YYYY |
| Termination date | DD/MM/YYYY (if any) |
| Notification date to Authority | DD/MM/YYYY |
| TIA No | Linked TIA reference |
| VERBİS updated | Yes / No |
| Disclosure updated | Yes / No |
| Annex protocols | List |
| Signatory | Person who signed for the company |
| Contract PDF | Archive reference |

---

## Türkçe

# Standart Sözleşme Rehberi

## 1. Hukuki Çerçeve

KVKK m.9/4-(c) uyarınca, yeterli korumanın bulunmadığı ülkelere kişisel veri aktarımı, **Kurul tarafından ilan edilen standart sözleşmenin** taraflar arasında akdedilmesi ve Kurum'a bildirilmesi koşuluyla yapılabilir. Standart sözleşme; veri kategorileri, aktarım amaçları, alıcı ve alıcı grupları, alıcı tarafından alınacak teknik ve idari tedbirler ile özel nitelikli kişisel veriler için alınan ek önlemleri içerir.

Kurul'un **04.06.2024 tarihli ve 2024/959 sayılı kararı** ile dört türde standart sözleşme metni yayımlanmıştır.

## 2. Standart Sözleşmenin Yapısı

Standart sözleşme tipik olarak aşağıdaki bölümlerden oluşur:

| Bölüm | İçerik |
|-------|--------|
| Başlangıç | Tarafların kimliği, sözleşmenin amacı, tanımlar |
| Aktarımın kapsamı | Veri kategorileri, ilgili kişi grupları, işleme amaçları, alıcılar, alıcı ülke |
| Tarafların yükümlülükleri | Veren tarafın ve alan tarafın yükümlülükleri |
| Veri sahibi hakları | İlgili kişinin hakları, haklarını kullanma yolu, üçüncü taraf yararlandırma |
| Teknik ve idari tedbirler | Şifreleme, erişim kontrolü, ihlal yönetimi, denetim |
| Özel nitelikli veriler | Ek tedbirler |
| Alt-işleyenler | Alt-işleyen kullanımı, izin, zincir sorumluluk |
| Sözleşme süresi ve sona erme | Süre, sona erme nedenleri, sona erince imha/iade |
| Sorumluluk ve tazminat | Karşılıklı tazminat hükümleri |
| Uygulanacak hukuk | Türkiye Cumhuriyeti hukuku |
| Yargı yeri | Türk mahkemeleri |
| Ekler | Aktarım kategorileri tablosu, teknik+idari tedbirler tablosu, alt-işleyen listesi |

## 3. Sözleşme Türleri ve Seçim

### 3.1. Dört Tür

| Kod | Türkiye Tarafı | Yurt Dışı Tarafı | Tipik Senaryo |
|-----|----------------|-------------------|---------------|
| Tip 1 | Veri Sorumlusu (VS) | Veri Sorumlusu (VS) | Grup şirketleri arası aktarım (BCR yoksa); ortak müşteri portföyü |
| Tip 2 | Veri Sorumlusu (VS) | Veri İşleyen (Vİ) | SaaS sağlayıcı, bulut sağlayıcı, çağrı merkezi outsourcing |
| Tip 3 | Veri İşleyen (Vİ) | Veri İşleyen (Vİ) | Türkiye'deki bulut sağlayıcının yurt dışı alt-işleyene aktarımı |
| Tip 4 | Veri İşleyen (Vİ) | Veri Sorumlusu (VS) | Türkiye'deki veri işleyenin yurt dışı veri sorumlusuna geri aktarımı |

### 3.2. Tür Seçim Kriteri

Statü tespiti **aktarımın yönü ve tarafların KVKK statüsü**ne göre yapılır. Yanlış tür kullanımı sözleşmenin geçersizliğine yol açar.

```
Aktarımı veren taraf kim?
+----------------+----------------+
|                                 |
v                                 v
Türkiye'deki                Türkiye'deki
Veri Sorumlusu              Veri İşleyen
|                                 |
v                                 v
Alan taraf kim?            Alan taraf kim?
+--------+                  +--------+
|        |                  |        |
v        v                  v        v
VS       Vİ                 Vİ       VS
|        |                  |        |
v        v                  v        v
Tip 1   Tip 2              Tip 3   Tip 4
```

## 4. Sözleşmenin İmzalanması

### 4.1. İmza Süreci

```
1. Tedarikçi/Alıcı ile statü ve aktarım kapsamı
   netleştirilir.
                |
                v
2. Doğru sözleşme türü seçilir (Hukuk Müdürlüğü
   onayı).
                |
                v
3. Standart metin değiştirilmeden ekler doldurulur:
   - Aktarım kapsamı (veri kategorisi, amaçlar)
   - Teknik+idari tedbirler
   - Alt-işleyen listesi
                |
                v
4. Hukuk Müdürlüğü gözden geçirir; ek hükümler
   varsa standart metni değiştirmeyecek şekilde
   ayrı ek olarak eklenir.
                |
                v
5. Bilgi Güvenliği teknik tedbirlerin somut ve
   doğru olduğunu doğrular.
                |
                v
6. Tarafların yetkilileri imzalar (e-imza veya
   ıslak imza).
                |
                v
7. İmza tarihinden itibaren 5 iş günü içinde
   Kurum'a bildirim yapılır.
                |
                v
8. Sözleşme arşive alınır; aktarım envanterine
   ve VERBİS'e yansıtılır.
```

### 4.2. İmza Şekli

- **E-imza:** 5070 sayılı E-İmza Kanunu kapsamında nitelikli elektronik imza.
- **Islak imza:** Kağıt sözleşme, taraf yetkililerinin elle imzası.
- **Yetki:** İmzalayan kişinin tüzel kişilik adına imza yetkisinin bulunması gerekir; imza sirküleri kontrolü yapılır.
- **Apostil/tasdik:** Yurt dışı tarafın imzası için, ülkeye göre apostil veya konsolosluk tasdiki istenebilir; pratikte taraflar karşılıklı PDF imza ile yetiniyor.

### 4.3. Sözleşmeden Sapma Yasağı

Standart sözleşme metni **değiştirilemez**. Aşağıdaki müdahaleler sözleşmenin geçersizliğine yol açar:

- Maddenin silinmesi,
- Maddenin değiştirilmesi (kelime değişikliği dahil),
- Tarafların yükümlülüklerinin azaltılması,
- Yargı yerinin Türkiye dışına taşınması,
- Uygulanacak hukukun değiştirilmesi.

İzin verilen müdahale:
- **Ekler doldurulur** (aktarım kapsamı, teknik tedbirler, alt-işleyen).
- **Ek hükümler ayrı bir ek protokol olarak eklenebilir**, **standart metnin maddelerini değiştirmemek** kaydıyla.

### 4.4. Çoklu Aktarım

- **Aynı taraflar arası birden fazla aktarım:** Tek bir çerçeve standart sözleşme imzalanabilir; ekte tüm aktarım kapsamları listelenir.
- **Farklı taraflar:** Her taraf çifti için ayrı sözleşme.

## 5. Kurum'a Bildirim

### 5.1. Süre

İmza tarihinden itibaren **5 iş günü** içinde bildirim yapılır.

### 5.2. Bildirim Yöntemi

Kurum'un belirlediği elektronik kanal kullanılır. Bildirim genellikle:

- VERBİS / Sicil portalı üzerinden,
- veya Kurum'un duyurduğu ayrı bildirim sistemi üzerinden,
- veya KEP yolu ile (Kurum'un kabul etmesi kaydıyla).

### 5.3. Bildirim İçeriği (Tipik)

| Alan | Açıklama |
|------|----------|
| Veren tarafın bilgileri | Unvan, adres, VERBİS kayıt no |
| Alan tarafın bilgileri | Unvan, adres, ülke |
| Sözleşme türü | Tip 1/2/3/4 |
| İmza tarihi | DD/MM/YYYY |
| Aktarımın amacı | Kısa açıklama |
| Aktarım veri kategorileri | Liste |
| İlgili kişi grupları | Liste |
| Aktarım süresi | Sözleşme süresi |
| Sözleşme metninin kendisi | PDF eki |

### 5.4. Bildirimin Hukuki Niteliği

- Bildirim **izin DEĞİLDİR**. Kurum'un onayı gerekmez.
- Bildirim, uygun güvencenin **şartı**dır. Bildirim yapılmaması, sözleşmenin imzalanmış olmasına rağmen aktarımın **uygun güvence olmaksızın yapılmış sayılmasına** yol açar.
- Bildirim eksik ise Kurum ek bilgi isteyebilir.

### 5.5. Sonradan Değişiklik

- Sözleşme tarafları, kapsam, alıcı ülke gibi temel unsurlar değişirse, **yeni** sözleşme veya **ek protokol** akdedilir; 5 iş günü içinde yeniden bildirim yapılır.
- Sözleşmenin sona ermesi veya feshi de bildirilir.

## 6. Aktarım Etki Değerlendirmesi (TIA — Transfer Impact Assessment)

Standart sözleşme tek başına yeterli olmayabilir; alıcı ülkenin hukuku ve uygulaması, sözleşmesel hükümlerin fiilen uygulanmasını engelleyebilir. TIA, bu olasılığı değerlendirir ve gerekli **ek tedbirler**i belirler.

### 6.1. TIA Aşamaları

```
Aşama 1: Aktarımın Haritalanması
- Veri kategorileri, kategori sayıları, hassasiyet
- İlgili kişi grupları
- Aktarım amacı, sıklık, süre
- Aktarımı veren ve alan; alan ülke; alıcının altında
  alt-işleyen var mı?

                |
                v

Aşama 2: Alıcı Ülkenin Hukuku ve Uygulaması
- Veri koruma mevzuatı (var mı, kapsamı?)
- Bağımsız denetim otoritesi
- İlgili kişi haklarının uygulanabilirliği
- Yargısal koruma yolları
- Uluslararası anlaşmalara taraf olma

                |
                v

Aşama 3: Kamu Otoritesi Erişimi
- İstihbarat servisi erişimi
- Kolluk erişimi
- Vergi/mali otoriteler
- Erişim için gözetim mekanizması var mı?
- "Disproportionate" erişim riski
- Aktarımın gerçekleştiği sektör için spesifik yetkiler

                |
                v

Aşama 4: Sözleşmenin Yeterliliği
- Standart sözleşme + ek hükümler birlikte yeterli mi?
- Alıcı taraf, sözleşmesel taahhütlerine fiilen
  uyabilecek mi (yerel hukuk engellemiyor mu)?

                |
                v

Aşama 5: Ek Tedbirler
- Teknik: end-to-end şifreleme, anahtar yönetimi
  (kaynakta), pseudonymization, veri minimizasyonu
- Sözleşmesel: ek bildirim yükümlülükleri,
  notification of access requests, audit hakkı
- Organizasyonel: erişim sınırlaması, "need-to-know",
  log + denetim

                |
                v

Aşama 6: Kalan Risk Değerlendirmesi
- Risk azaltıldıktan sonra kalan risk kabul edilebilir mi?
- Kabul edilemiyorsa: aktarım yapılmaz / başka yol seçilir
```

### 6.2. Tipik Ek Tedbirler

| Risk | Ek Tedbir |
|------|-----------|
| Alıcı ülkenin kamu otoritesi disproportionate erişim talebi | End-to-end şifreleme + anahtarın Türkiye'de tutulması |
| Alıcı ülkede yargısal koruma zayıf | Sözleşmede üçüncü taraf yararlandırma + Türk mahkemesi yetkisi |
| Alt-işleyen zinciri uzun ve şeffaf değil | Alıcının onaylı alt-işleyen listesi + her değişikliğin önceden bildirilmesi |
| İhlal halinde bildirim gecikmesi | Sözleşmede 24 saat içinde bildirim yükümlülüğü |
| Kamu otoritesi erişim talebinde bilgi verilmemesi | "Notification of access requests" maddesi (yerel hukuk izin verdiği ölçüde) |
| Pseudonymization olmaksızın hassas veri | Kaynakta pseudonymization, anahtar Türkiye'de kalır |
| Veri minimizasyonu yetersiz | Aktarım öncesi minimizasyon, sadece gerekli alanlar |

### 6.3. TIA Şablonu Kısa Form

```
TIA — Aktarım Etki Değerlendirmesi
═════════════════════════════════════
TIA No                : ________________
Tarih                 : ____/____/______
Aktarımı Yapan        : ________________
Alıcı                 : ________________
Alıcı Ülke            : ________________
Alıcı Statü (VS/Vİ)   : ________________
Sözleşme Türü         : Tip __

1. AKTARIMIN HARİTASI
   Veri Kategorileri  : ________________
   Hassasiyet         : Genel / Özel nitelikli
   İlgili Kişi Grupları: ________________
   Aktarım Sıklığı    : Sürekli / Periyodik / Tek
   Aktarım Süresi     : ________________

2. ALICI ÜLKENİN HUKUKU
   Veri Koruma Mevzuatı: ____________________
   Denetim Otoritesi  : ____________________
   İlgili Kişi Hakları : Var / Sınırlı / Yok
   Yargı Yolu         : Var / Sınırlı / Yok

3. KAMU OTORİTESİ ERİŞİM RİSKİ
   İstihbarat         : Düşük / Orta / Yüksek
   Kolluk             : Düşük / Orta / Yüksek
   Disproportionate
   erişim riski       : Düşük / Orta / Yüksek

4. EK TEDBİRLER
   Teknik             : ____________________
   Sözleşmesel        : ____________________
   Organizasyonel     : ____________________

5. KALAN RİSK
   Risk Seviyesi      : Düşük / Orta / Yüksek
   Kabul Edilebilirlik : Evet / Hayır
   Karar              : Aktar / Aktarma / Yeni
                        tedbir gerekiyor

6. ONAY
   KVKK Sorumlusu     : ____________________
   Hukuk Müdürü       : ____________________
   Bilgi Güv. Yön.    : ____________________
```

Tam form için: [aktarim-degerlendirme-formu.md](aktarim-degerlendirme-formu.md)

## 7. Tipik Hatalar

| Hata | Sonuç | Önlem |
|------|-------|-------|
| Standart metni değiştirme (sözleşmeden sapma) | Sözleşme geçersiz; aktarım uygun güvence olmaksızın | Standart metin **değişmez**; sadece ekler doldurulur |
| Yanlış tür seçimi | Sözleşme geçersiz | Karar ağacı + Hukuk Müdürlüğü onayı |
| 5 iş günü içinde bildirim yapılmaması | Uygun güvence sağlanmamış | İmza akış sürecine zorunlu adım |
| TIA yapılmadan aktarım | Ek tedbirler eksik; risk değerlendirilmemiş | Her aktarım için TIA zorunlu |
| Alt-işleyen zincirinin ele alınmaması | Sorumluluk boşluğu | Alt-işleyen listesi + her değişiklikte güncelleme |
| İmza yetkisi kontrolsüz | Sözleşme geçersiz | İmza sirküleri kontrolü; kurumsal yetki teyidi |
| Çoklu aktarım için tek tek sözleşme | Operasyonel maliyet, gözden kaçma | Tek çerçeve sözleşme + ek liste |
| Standart sözleşme yerine kendi metnini kullanmak | Uygun güvence değildir; m.9/4-(ç) taahhütname yolu izlenmeli | Standart sözleşme şart; aksi halde Kurul izni |
| Sözleşmenin sona ermesinin bildirilmemesi | Aktarım envanteri ve VERBİS uyumsuzluk | Sona erme de bildirilir |

## 8. Operasyonel İş Akışı (Süreç Sahipleri)

| Adım | Sorumlu | Süre |
|------|---------|------|
| Tedarikçi statü tespiti | KVKK Sorumlusu + Hukuk | 2 iş günü |
| Sözleşme türü seçimi | Hukuk Müdürlüğü | 1 iş günü |
| Ekler doldurma | İlgili Birim + Bilgi Güvenliği | 3 iş günü |
| TIA hazırlama | KVKK Sorumlusu + Bilgi Güvenliği | 5 iş günü |
| Hukuki gözden geçirme | Hukuk Müdürlüğü | 3 iş günü |
| İmza | Yetkili imzacı | 1-2 iş günü |
| Kuruma bildirim | KVKK Sorumlusu | İmzadan sonra **5 iş günü içinde** |
| Envanter ve VERBİS güncelleme | KVKK Sorumlusu | 2 iş günü |
| Aydınlatma metni güncelleme | KVKK Sorumlusu + İlgili Birim | 5 iş günü |

Toplam idealde **20-25 iş günü**; karmaşık aktarımlar için 4-6 hafta.

## 9. Standart Sözleşme Yönetim Kayıtları

Her sözleşme için aşağıdaki kayıt tutulur:

| Alan | Açıklama |
|------|----------|
| Sözleşme No | Şirket içi sıra (ör. STD-2026-0042) |
| Tür | Tip 1/2/3/4 |
| Karşı taraf | Unvan, ülke, adres |
| İmza tarihi | DD/MM/YYYY |
| Yürürlük tarihi | DD/MM/YYYY |
| Sona erme tarihi | DD/MM/YYYY (varsa) |
| Kuruma bildirim tarihi | DD/MM/YYYY |
| TIA No | Bağlı TIA referansı |
| VERBİS güncellendi | Evet / Hayır |
| Aydınlatma güncellendi | Evet / Hayır |
| Ek protokoller | Liste |
| İmzacı | Şirket adına imza atan kişi |
| Sözleşme PDF | Arşiv referansı |
