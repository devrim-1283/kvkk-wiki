---
Document / Doküman: Personal Data vs Special Categories (Articles 9 & 10) / Kişisel Veri ve Özel Nitelikli Kategoriler (Madde 9 ve 10)
Section / Bölüm: 01-core-concepts
Owner / Sahip: Data Protection Officer (DPO) / Veri Koruma Görevlisi
Approved by / Onaylayan: Privacy / Data Governance Committee / Gizlilik / Veri Yönetişim Komitesi
Version / Versiyon: 1.0
Effective / Yürürlük: 2026-05-08
Review / Gözden Geçirme: Annual + triggered / Yıllık + tetiklenmiş
Legal Reference / İlgili Mevzuat: GDPR Art. 9, 10; EDPB Guidelines 03/2020 on health data; ECJ Meta Platforms (C-252/21), OT (C-184/20)
---

## English

### 1. Purpose

This document distinguishes ordinary personal data from special categories of personal data (Article 9) and personal data relating to criminal convictions and offences (Article 10), specifies the conditions under which each category may be processed, and provides a decision tree for classification.

### 2. Why the Distinction Matters

Special categories are subject to a default prohibition of processing (Article 9(1)). Processing is permitted only when one of the exceptions in Article 9(2) applies. Misclassification leads to:

- Unlawful processing (Article 5(1)(a) breach).
- Higher Article 83(5) fine bracket (up to €20m / 4%).
- DPIA omission risk under Article 35(3)(b).
- Data subject claims under Article 82.

ECJ in OT v. Vyriausioji tarnybinės etikos komisija (C-184/20) confirmed that data which by deduction reveal a special category (e.g., a partner's name disclosing sexual orientation) may itself be treated as special category. ECJ Meta Platforms (C-252/21) reinforced strict interpretation of Article 9(2)(e) "manifestly made public" exception.

### 3. Article 9(1) Special Categories — Closed List

| Category | Examples | Operational note |
|---|---|---|
| Racial or ethnic origin | Skin color, ethnicity, ancestry markers | Photographs alone do not become special category but may indirectly reveal race. |
| Political opinions | Party membership, voting intent, advocacy | Includes inferred opinions from behavior. |
| Religious or philosophical beliefs | Faith, observance, atheism | Includes dietary restrictions if linked to religion. |
| Trade union membership | Union ID, dues, participation | Including past membership. |
| Genetic data | DNA, RNA, chromosomal, hereditary markers | Article 4(13). |
| Biometric data for unique identification | Fingerprints, face templates, iris scans, voice prints used to identify | Per Article 4(14). Photo of a face is not, by itself, biometric data unless processed for unique ID. |
| Health data | Medical records, prescriptions, diagnoses, occupational health, mental health | Includes any data revealing health status (EDPB Guidelines 03/2020). |
| Sex life | Sexual practices, history | |
| Sexual orientation | Stated or inferred orientation | ECJ OT C-184/20 — inferred via partner identification is captured. |

### 4. Article 9(2) Exceptions — Conditions to Process

Processing is allowed when at least one of the following applies (and other GDPR principles still apply):

- (a) **Explicit consent** — granular, informed, specific, demonstrable. Member State law may prohibit consent-based processing in some cases.
- (b) **Employment, social security and social protection law** — necessary for obligations and exercising specific rights of controller or data subject; subject to Member State law providing safeguards.
- (c) **Vital interests** — where data subject is physically or legally incapable of giving consent.
- (d) **Foundation, association, non-profit body** — processing of members' or former members' data within legitimate activities, with appropriate safeguards.
- (e) **Manifestly made public** by the data subject — strict interpretation; mere visibility online does not equal "manifestly made public" (Meta Platforms C-252/21).
- (f) **Establishment, exercise or defense of legal claims** or courts acting in their judicial capacity.
- (g) **Substantial public interest** — on the basis of Union or Member State law, proportionate, and providing safeguards.
- (h) **Preventive or occupational medicine, medical diagnosis, healthcare or treatment** — by or under responsibility of a professional subject to professional secrecy.
- (i) **Public health** — protecting against serious cross-border threats; under Union/Member State law providing safeguards.
- (j) **Archiving in the public interest, scientific or historical research, statistical purposes** — under Article 89(1) safeguards.

For each Article 9(2) exception relied on, the controller must:

- Document the legal basis for relying on it.
- Document the safeguards (especially for (b), (g), (i), (j) which require additional Member State law).
- Reflect this in the ROPA and privacy notice.
- Reflect this in the DPIA where required.

### 5. Article 10 — Criminal Convictions and Offences

Processing of personal data relating to criminal convictions and offences or related security measures may be carried out only:

- Under the control of official authority; or
- When authorized by Union or Member State law providing for appropriate safeguards.

A comprehensive register of criminal convictions may be kept only under the control of official authority.

**Operational impact:**
- Criminal background checks for employment must rely on a Member State law authorization (e.g., German BDSG §26, French Loi Informatique et Libertés Art. 46) and proportionality.
- HR may not store conviction details longer than the legitimate need; results-only summaries are preferred.

### 6. Decision Tree: Is It Special Category?

```
Is it data relating to a natural person? ── No ──► Not personal data; not special category.
        │
        Yes
        │
Does it directly fall in the closed list (Art. 9(1))? ── Yes ──► Special category.
        │                                                                  │
        No                                                                  │
        │                                                                  │
Could it indirectly reveal an Art. 9(1) attribute through                  │
inference, combination, or association?                                     │
(e.g., dietary preference → religion;                                       │
partner name → sexual orientation, OT C-184/20)                             │
        │                                                                  │
        Yes ────────────────────────────────────────────────────────────────►
        │
        No
        │
Does processing aim to uniquely identify a person                          
through biometric features?                                                
        │                                                                  │
        Yes ────────────────────────────────────────────────────────────────►
        │
        No
        │
Is it data on criminal convictions / offences (Art. 10)? ── Yes ──► Treat under Art. 10 regime.
        │
        No
        │
        ▼
   Ordinary personal data
```

### 7. Examples and Edge Cases

| Scenario | Classification | Note |
|---|---|---|
| Employee blood-type for emergency contact card | Health data → Art. 9 | Even if used only on incident; exception (h)/(i) or explicit consent required. |
| Photo on employee badge | Personal data, not special by default | Becomes special if processed for unique ID via biometric template. |
| CV mentioning religious affiliation | Special category | Relying on consent in employment is fragile — see EDPB Guidelines 05/2020. |
| Wearable step-count for wellness program | May reveal health data | DPIA likely required; strict purpose limitation and consent. |
| Vaccination status for COVID-19 access | Health data | Member State law dependent; many Member States imposed specific frameworks. |
| Gym usage frequency | Generally not special | Unless combined to reveal health condition. |
| Union dues deduction in payroll | Trade union membership | Special category; legal authorization required. |
| Photographs at a Pride march | Sexual orientation context | Even if "public", reuse for new purposes may be unlawful. |

### 8. Operational Controls

When processing special categories or criminal data, the following minimum controls apply:

- **DPIA** (Art. 35(3)(b)) where processing is on a large scale.
- **Lawful basis (Art. 6) plus Art. 9(2) exception** documented, both required.
- **Strict access control:** least privilege, MFA, granular role-based access, audit logging.
- **Encryption at rest and in transit.**
- **Pseudonymization where technically feasible.**
- **Retention limits** stricter than ordinary data; documented in retention schedule.
- **Special privacy notice clauses** identifying the category and exception.
- **Training** for staff handling special categories — annual mandatory.
- **Vendor contracts** explicitly listing special category processing and additional safeguards.
- **Cross-border transfer:** evaluated with heightened TIA scrutiny.

### 9. Member State Variations

- **Germany (BDSG §22, §26):** detailed conditions for employment-related special category processing.
- **France (Loi Informatique et Libertés Art. 6, Art. 9, Art. 46):** authorization regime for some health-related and criminal data.
- **Italy (Garante decisions):** strict on biometric data in employment.
- **Spain (LOPDGDD):** specific safeguards for political opinion, religion, union, sexual orientation in employment.

### 10. Common Pitfalls

- Treating "voluntary" wellness data as ordinary personal data.
- Storing CV religion fields without an Article 9(2) exception.
- Using facial recognition for time-attendance without explicit consent and proportionality test.
- Mixing criminal background data with HR data without segregation.
- Inferring religious dietary needs and storing them without recognizing the special category status.
- Relying on Article 9(2)(e) "manifestly made public" because data is visible online.

---

## Türkçe

### 1. Amaç

Bu belge, sıradan kişisel veriyi özel nitelikli kişisel veri kategorilerinden (Madde 9) ve cezai mahkûmiyet ve suçlara ilişkin kişisel verilerden (Madde 10) ayırır, her kategorinin işlenebileceği koşulları belirler ve sınıflandırma için bir karar ağacı sunar.

### 2. Bu Ayrımın Önemi

Özel nitelikli kategoriler varsayılan olarak işleme yasağına tabidir (Madde 9(1)). İşleme yalnızca Madde 9(2) istisnalarından biri uygulandığında izinlidir. Yanlış sınıflandırma şunlara yol açar:

- Hukuka aykırı işleme (Madde 5(1)(a) ihlali).
- Daha yüksek Madde 83(5) ceza dilimi (20 milyon Euro'ya / %4'e kadar).
- Madde 35(3)(b) uyarınca DPIA atlama riski.
- Madde 82 uyarınca ilgili kişi talepleri.

ABAD'ın OT v. Vyriausioji tarnybinės etikos komisija (C-184/20) kararı, çıkarım yoluyla bir özel kategoriyi açığa vuran verilerin (örn. bir partnerin adının cinsel yönelimi açığa vurması) kendisinin özel kategori olarak ele alınabileceğini teyit etti. ABAD Meta Platforms (C-252/21) kararı, Madde 9(2)(e) "açıkça kamuya açık hâle getirilmiş" istisnasının dar yorumunu pekiştirdi.

### 3. Madde 9(1) Özel Nitelikli Kategoriler — Kapalı Liste

| Kategori | Örnekler | Operasyonel not |
|---|---|---|
| Irk veya etnik köken | Ten rengi, etnik köken, soy belirteçleri | Yalnızca fotoğraflar özel kategori sayılmaz ancak ırkı dolaylı açığa vurabilir. |
| Siyasi görüş | Parti üyeliği, oy niyeti, savunuculuk | Davranıştan çıkarsanan görüşler dahildir. |
| Dini veya felsefi inanç | İnanç, ibadet, ateizm | Dine bağlıysa beslenme kısıtlamalarını da kapsar. |
| Sendika üyeliği | Sendika kimliği, aidatlar, katılım | Geçmiş üyelik dahil. |
| Genetik veri | DNA, RNA, kromozom, kalıtsal belirteçler | Madde 4(13). |
| Benzersiz tanımlama amaçlı biyometrik veri | Tanımlama için kullanılan parmak izi, yüz şablonu, iris taraması, ses örüntüsü | Madde 4(14). Yüz fotoğrafı, benzersiz tanımlama için işlenmedikçe tek başına biyometrik veri değildir. |
| Sağlık verisi | Tıbbi kayıtlar, reçeteler, teşhisler, iş yeri sağlığı, ruh sağlığı | Sağlık durumunu açığa vuran herhangi bir veriyi kapsar (EDPB 03/2020 Rehberi). |
| Cinsel yaşam | Cinsel pratikler, geçmiş | |
| Cinsel yönelim | Beyan edilen veya çıkarsanan yönelim | ABAD OT C-184/20 — partner kimliği üzerinden çıkarsama dahildir. |

### 4. Madde 9(2) İstisnaları — İşleme Koşulları

Aşağıdakilerden en az biri uygulandığında işleme izinlidir (diğer GDPR ilkeleri yine geçerlidir):

- (a) **Açık rıza** — ayrıntılı, bilgilendirilmiş, belirli, kanıtlanabilir. Üye Devlet hukuku bazı durumlarda rızaya dayalı işlemeyi yasaklayabilir.
- (b) **İstihdam, sosyal güvenlik ve sosyal koruma hukuku** — veri sorumlusu veya ilgili kişinin yükümlülükleri ve özel haklarının kullanılması için gerekli; güvenceler sağlayan Üye Devlet hukukuna tabi.
- (c) **Hayati menfaatler** — ilgili kişinin fiziksel veya yasal olarak rıza veremediği durumlarda.
- (d) **Vakıf, dernek, kâr amacı gütmeyen kuruluş** — meşru faaliyetler içinde uygun güvencelerle üyelerinin veya eski üyelerinin verilerinin işlenmesi.
- (e) İlgili kişi tarafından **açıkça kamuya açık hâle getirilmiş** — dar yorum; bir verinin çevrimiçi görünür olması "açıkça kamuya açık" anlamına gelmez (Meta Platforms C-252/21).
- (f) **Yasal taleplerin tesisi, kullanılması veya savunulması** veya yargı yetkisini kullanan mahkemeler.
- (g) **Önemli kamu yararı** — Birlik veya Üye Devlet hukukuna dayalı, orantılı ve güvenceler sağlayan.
- (h) **Önleyici veya iş yeri tıbbı, tıbbi teşhis, sağlık hizmeti veya tedavi** — mesleki sırra tabi bir uzman tarafından veya onun sorumluluğunda.
- (i) **Halk sağlığı** — ciddi sınır ötesi tehditlere karşı koruma; güvenceler sağlayan Birlik/Üye Devlet hukuku altında.
- (j) **Kamu yararına arşivleme, bilimsel veya tarihsel araştırma, istatistiksel amaçlar** — Madde 89(1) güvenceleri altında.

Dayanılan her Madde 9(2) istisnası için veri sorumlusu:

- Dayanma için yasal temeli belgeler.
- Güvenceleri belgeler (özellikle (b), (g), (i), (j) ek Üye Devlet hukuku gerektirir).
- ROPA ve aydınlatma metnine yansıtır.
- Gerektiğinde DPIA'ya yansıtır.

### 5. Madde 10 — Cezai Mahkûmiyet ve Suçlar

Cezai mahkûmiyet ve suçlara veya ilgili güvenlik tedbirlerine ilişkin kişisel verilerin işlenmesi yalnızca:

- Resmi makamın denetiminde; veya
- Uygun güvenceler sağlayan Birlik veya Üye Devlet hukuku tarafından yetkilendirildiğinde gerçekleştirilebilir.

Cezai mahkûmiyetlerin kapsamlı bir sicili yalnızca resmi makamın denetiminde tutulabilir.

**Operasyonel etki:**
- İstihdam için adli sicil kontrolleri Üye Devlet hukuku yetkilendirmesine (örn. Alman BDSG §26, Fransız Loi Informatique et Libertés Md. 46) ve orantılılığa dayanmalıdır.
- İK, mahkûmiyet ayrıntılarını meşru ihtiyaç süresinden uzun saklayamaz; yalnızca sonuç özetleri tercih edilir.

### 6. Karar Ağacı: Özel Kategori mi?

```
Bir gerçek kişiyle ilişkili veri mi? ── Hayır ──► Kişisel veri değil; özel kategori değil.
        │
        Evet
        │
Kapalı listeye doğrudan giriyor mu (Md. 9(1))? ── Evet ──► Özel kategori.
        │                                                                  │
        Hayır                                                                │
        │                                                                  │
Çıkarım, birleştirme veya çağrışım yoluyla bir Md. 9(1)                    │
özelliğini dolaylı olarak açığa vuruyor mu?                                 │
(örn. beslenme tercihi → din;                                                │
partner adı → cinsel yönelim, OT C-184/20)                                   │
        │                                                                  │
        Evet ────────────────────────────────────────────────────────────────►
        │
        Hayır
        │
İşleme, biyometrik özelliklerle bir kişiyi benzersiz                       
biçimde tanımlamayı amaçlıyor mu?                                           
        │                                                                  │
        Evet ────────────────────────────────────────────────────────────────►
        │
        Hayır
        │
Cezai mahkûmiyet / suçlara ilişkin veri mi (Md. 10)? ── Evet ──► Md. 10 rejimi altında ele alın.
        │
        Hayır
        │
        ▼
   Sıradan kişisel veri
```

### 7. Örnekler ve Sınır Durumlar

| Senaryo | Sınıflandırma | Not |
|---|---|---|
| Çalışanın acil iletişim kartı için kan grubu | Sağlık verisi → Md. 9 | Yalnızca olayda kullanılsa bile; istisna (h)/(i) veya açık rıza gerekir. |
| Çalışan kimliğindeki fotoğraf | Kişisel veri, varsayılan olarak özel değil | Biyometrik şablonla benzersiz tanımlama için işlenirse özel hâle gelir. |
| Dini ilişkiyi belirten CV | Özel kategori | İstihdamda rızaya dayanmak kırılgandır — bkz. EDPB 05/2020 Rehberi. |
| Sağlıklı yaşam programı için adım sayısı bilekliği | Sağlık verisini açığa vurabilir | DPIA muhtemelen gerekir; sıkı amaç sınırlaması ve rıza. |
| COVID-19 erişimi için aşı durumu | Sağlık verisi | Üye Devlet hukukuna bağlıdır; pek çok Üye Devlet özel çerçeveler getirdi. |
| Spor salonu kullanım sıklığı | Genelde özel değil | Sağlık durumunu açığa vurmak üzere birleştirilmedikçe. |
| Bordroda sendika aidatı kesintisi | Sendika üyeliği | Özel kategori; yasal yetkilendirme gerekir. |
| Onur Yürüyüşü'ndeki fotoğraflar | Cinsel yönelim bağlamı | "Kamuya açık" olsa bile yeni amaçlarla yeniden kullanım hukuka aykırı olabilir. |

### 8. Operasyonel Kontroller

Özel kategorileri veya cezai verileri işlerken aşağıdaki asgari kontroller uygulanır:

- Geniş ölçekli işleme olduğunda **DPIA** (Md. 35(3)(b)).
- **Md. 6 hukuki dayanağı artı Md. 9(2) istisnası** her ikisi de belgelenmiş olmalı.
- **Sıkı erişim kontrolü:** en az ayrıcalık, MFA, ayrıntılı rol bazlı erişim, denetim günlüğü.
- **Bekleyen ve aktarımdaki şifreleme.**
- Teknik olarak mümkün olduğunda **takma adlandırma.**
- Sıradan veriden daha sıkı **saklama sınırları**; saklama planında belgelenir.
- Kategoriyi ve istisnayı tanımlayan **özel aydınlatma metni hükümleri.**
- Özel kategorileri işleyen personel için **eğitim** — yıllık zorunlu.
- Özel kategori işlemeyi ve ek güvenceleri açıkça listeleyen **tedarikçi sözleşmeleri.**
- **Sınır ötesi aktarım:** artırılmış TIA incelemesiyle değerlendirilir.

### 9. Üye Devlet Farklılıkları

- **Almanya (BDSG §22, §26):** istihdamla ilgili özel kategori işleme için ayrıntılı koşullar.
- **Fransa (Loi Informatique et Libertés Md. 6, Md. 9, Md. 46):** bazı sağlıkla ilgili ve cezai veriler için yetkilendirme rejimi.
- **İtalya (Garante kararları):** istihdamda biyometrik veri konusunda katı.
- **İspanya (LOPDGDD):** istihdamda siyasi görüş, din, sendika, cinsel yönelim için özel güvenceler.

### 10. Sık Karşılaşılan Tuzaklar

- "Gönüllü" sağlıklı yaşam verisini sıradan kişisel veri olarak ele almak.
- CV'deki din alanlarını Madde 9(2) istisnası olmadan saklamak.
- Mesai takibi için yüz tanımayı açık rıza ve orantılılık testi olmaksızın kullanmak.
- Adli sicil verisini İK verisiyle ayırmadan karıştırmak.
- Dini beslenme ihtiyaçlarını çıkarsayıp özel kategori statüsünü tanımadan saklamak.
- Veri çevrimiçi görünür olduğu için Madde 9(2)(e) "açıkça kamuya açık" istisnasına dayanmak.
