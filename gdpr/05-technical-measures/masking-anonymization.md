---
title:
  en: "Masking and Anonymisation - k-Anonymity, l-Diversity, t-Closeness, Differential Privacy, Synthetic Data"
  tr: "Maskeleme ve Anonimleştirme - k-Anonim, l-Çeşitlilik, t-Yakınlık, Diferansiyel Gizlilik, Sentetik Veri"
section: "05-technical-measures"
document_type: "control_policy"
control_id: "TECH-ANON-01"
owner:
  primary: "DPO"
  secondary: "CISO, Data Engineering Lead"
review_cycle: "annual"
last_review: "2026-05-08"
next_review: "2027-05-08"
classification: "Internal"
language: ["en", "tr"]
references:
  - "GDPR Art. 4(1), 4(5), 11, 25, 32, Recital 26"
  - "Article 29 WP Opinion 05/2014 on Anonymisation Techniques (still cited under EDPB)"
  - "ISO/IEC 20889:2018 Privacy enhancing data de-identification techniques"
  - "ISO/IEC 27559:2022 Privacy-enhancing data de-identification framework"
  - "Sweeney 2002 (k-anonymity); Machanavajjhala et al. 2007 (l-diversity); Li et al. 2007 (t-closeness)"
  - "Dwork & Roth - Algorithmic Foundations of Differential Privacy"
  - "ENISA Pseudonymisation Techniques and Best Practices (2019, updated 2021)"
---

## English

# Masking and Anonymisation

## 1. Why This Matters Under GDPR

GDPR Recital 26 sets the boundary: "The principles of data protection should
therefore not apply to anonymous information, namely information which does
not relate to an identified or identifiable natural person, or to personal
data rendered anonymous in such a manner that the data subject is not or no
longer identifiable. This Regulation does not therefore concern the
processing of such anonymous information, including for statistical or
research purposes."

Anonymisation is a high bar. Pseudonymisation is not anonymisation. To assess
whether data has been rendered anonymous, the controller must consider "all
the means reasonably likely to be used" - by the controller or any other
person - to identify the natural person, including singling out, linkability
and inference (the WP29 three tests). If any of those is realistic, the data
remains personal data and the GDPR continues to apply.

This document defines:

- The difference between masking, pseudonymisation and anonymisation.
- The technique families and when each is appropriate.
- The risk-based assessment that must accompany every release.
- The governance, including ISO/IEC 20889 and 27559 alignment.

## 2. Definitions

| Term | Definition |
|------|------------|
| **Masking** | Replacing or hiding values in a UI or log so unauthorised viewers cannot read them. The underlying record is unchanged. Not a privacy guarantee on its own. |
| **Pseudonymisation** (Art. 4(5)) | Reversible technique - replacing identifiers with tokens, with the mapping kept separately. Data remains personal. |
| **Anonymisation** (Recital 26) | Irreversible technique that removes the link between data and any identified or identifiable person, taking into account all means reasonably likely to be used. Data is no longer personal. |
| **De-identification** | Umbrella term covering both pseudonymisation and anonymisation (used by ISO 20889). |

## 3. The Three WP29 Tests

Before declaring a release "anonymised", the controller evaluates:

1. **Singling out** - is it possible to isolate a record that uniquely
   describes one individual?
2. **Linkability** - is it possible to link two records that belong to the
   same individual, in the same data set or across data sets?
3. **Inference** - is it possible to deduce, with significant probability, a
   value of an attribute from values of other attributes?

If the answer to all three is "no" with reasonable likelihood, the data may
be treated as anonymous.

## 4. Technique Families (ISO/IEC 20889)

### 4.1 Removal and generalisation
- Direct removal of identifiers (names, IDs, contact).
- Generalisation - reducing precision (date of birth -> birth year, postcode
  -> region).
- Top / bottom coding - capping outliers (age >= 90 collapsed).

### 4.2 Suppression
- Cell suppression where a value is too rare.
- Record suppression where the whole record is unique.

### 4.3 Perturbation
- Noise addition.
- Rounding.
- Micro-aggregation.

### 4.4 Pseudonymisation
- Tokenisation, FPE, HMAC with secret salt (`encryption.md`).

### 4.5 Differential Privacy
- Carefully calibrated noise that bounds the contribution of any single
  individual to a query result, parameterised by a privacy budget (epsilon).

### 4.6 Synthetic Data
- Generative models trained on real data producing artificial records that
  preserve statistical properties.

## 5. k-Anonymity

A data set is **k-anonymous** if every record's quasi-identifier combination
is shared by at least k-1 other records. Practical guidance:

- Choose k based on context, not as a magic number. k = 5 is a frequent
  baseline for low-risk releases; k = 11 for healthcare; k = 20 for highly
  sensitive small populations.
- Quasi-identifiers must be enumerated (age, gender, postcode, profession,
  date of admission ...). Failing to enumerate them is the most common cause
  of re-identification.
- k-anonymity does not protect against attribute disclosure when the
  sensitive attribute is uniform within the equivalence class.

## 6. l-Diversity

A data set has **l-diversity** if every equivalence class (set of records
sharing quasi-identifiers) contains at least l "well-represented" values for
the sensitive attribute. Variants:

- Distinct l-diversity - at least l distinct sensitive values.
- Entropy l-diversity - entropy of sensitive values >= log(l).
- Recursive (c, l)-diversity - bounds skew.

l-diversity addresses homogeneity attacks but does not handle skewness or
similarity (e.g., diseases that are different codes but semantically close).

## 7. t-Closeness

A data set has **t-closeness** if the distribution of the sensitive attribute
within any equivalence class is within distance t of the distribution in the
overall table. t-closeness mitigates similarity and skewness attacks at the
cost of utility loss.

Choosing t is application-specific; t in the range 0.1 to 0.3 is common for
healthcare aggregates.

## 8. Differential Privacy

DP provides a mathematical guarantee:

For any two data sets differing by a single record, and for any subset S of
possible outputs, Pr[M(D1) in S] <= e^epsilon * Pr[M(D2) in S]

Practical considerations:

- **Local DP** - noise added at the device before submission to the
  controller. Stronger user guarantee, weaker analytic utility.
- **Central DP** - noise added by the controller before publishing
  aggregates. Better utility, requires trusting the controller's
  implementation.
- **Privacy budget** - epsilon is finite. Repeated queries on the same data
  set deplete the budget; controls must enforce a global budget cap and
  refuse queries beyond it.
- **Composition** - sequential composition adds budgets; advanced composition
  techniques apply for repeated queries.
- **Implementation** - libraries such as IBM diffprivlib, Google DP, OpenDP
  and Tumult Analytics carry the most mature primitives. Implementation
  errors are common; production deployments require external review.

DP is appropriate for statistical releases, dashboards and ML training where
exact-record fidelity is not required.

## 9. Synthetic Data

Synthetic data is generated from a model trained on real data:

- Tabular - GANs, VAEs, copulas, Bayesian networks.
- Text / time series - sequence models.
- Hybrid - simulations driven by real distributions.

Privacy is not automatic. Membership inference, attribute inference and
reconstruction attacks are documented in literature. Required controls:

- Train under DP (DP-SGD or PATE) to bound leakage.
- Privacy red-team the synthetic release before publication.
- Document utility-privacy trade-off in the release dossier.
- Treat synthetic data with re-identification potential as personal data
  until proven otherwise.

## 10. Re-identification Risk Assessment

Every release of de-identified data goes through a documented assessment:

1. **Define the release context** - audience (public vs trusted recipient),
   purpose, contractual constraints.
2. **Enumerate quasi-identifiers** including outside knowledge (publicly
   available data sets) and adversary capability.
3. **Compute risk metrics** appropriate to the technique (k, l, t, epsilon,
   prosecutor / journalist / marketer risk per ISO 25237 in healthcare).
4. **Compare to threshold** set by the DPO and recorded in the de-identification
   register.
5. **Apply additional controls** if risk exceeds threshold (more
   generalisation, suppression, lower epsilon, contractual restrictions on
   the recipient).
6. **Sign off** - DPO and data steward sign before release; release dossier
   archived.

The dossier records the data set, technique parameters, risk metrics,
controls and sign-off.

## 11. ISO/IEC 27559 Framework

The controller aligns process with ISO/IEC 27559:2022:

1. Establish the de-identification context.
2. Identify direct and indirect identifiers.
3. Determine acceptable risk level.
4. Select techniques and parameters.
5. Apply controls including data and motivation controls.
6. Validate by measuring residual risk.
7. Monitor and re-assess as the threat landscape (and adversary auxiliary
   information) evolves.

## 12. Operational Controls

- A central de-identification register lists every recurrent release.
- Releases destined for the public domain receive an additional second-pair-
  of-eyes review.
- Recipient contracts forbid re-identification attempts and require notification
  of any incident.
- Annual review of releases against new auxiliary information that may have
  become available since release.
- Where re-identification risk increases (new linkable data set published),
  the release is reassessed and may be withdrawn or refreshed with stronger
  controls.

## 13. Common Anti-Patterns

- "Anonymisation" by hashing direct identifiers only - linkable.
- Removing names but keeping date of birth + postcode - widely shown to be
  re-identifying.
- Aggregations on small populations without suppression.
- Sharing "anonymised" location traces - well documented as re-identifiable.
- Treating pseudonymisation as anonymisation in DPIAs (`06-organizational-measures/dpia.md`).
- Differential privacy with epsilon set "as small as possible" without a
  documented budget allocation.

## 14. KPIs

| Metric | Target |
|--------|--------|
| De-identified releases with re-id assessment | 100 % |
| Releases with documented k, l, t, or epsilon | 100 % |
| Recipient contracts in force | 100 % |
| Re-identification incidents | 0 |
| Annual reviews completed on time | 100 % |

## 15. Mapping

| Requirement | GDPR | ISO 27002:2022 | NIST CSF 2.0 |
|-------------|------|----------------|--------------|
| Anonymisation | Recital 26 | 8.11 | PR.DS-2 |
| Pseudonymisation | Art. 4(5), 32(1)(a) | 8.11 | PR.DS-2 |
| ISO frameworks | n/a | 8.11 (cross-ref ISO 20889 / 27559) | n/a |

---

## Türkçe

# Maskeleme ve Anonimleştirme

## 1. GDPR Kapsamında Neden Önemli

GDPR Resital 26 sınırı belirler: "Veri koruma ilkeleri bu nedenle anonim
bilgilere, yani tanımlanmış veya tanımlanabilir bir gerçek kişiye ait olmayan
bilgilere veya veri sahibinin artık tanımlanamayacağı şekilde anonim hale
getirilmiş kişisel verilere uygulanmamalıdır. Bu Tüzük dolayısıyla istatistik
veya araştırma amaçları dahil olmak üzere bu tür anonim bilgilerin işlenmesini
ilgilendirmez."

Anonimleştirme yüksek bir eşiktir. Pseudonimizasyon anonimleştirme değildir.
Verinin anonim hale getirilip getirilmediğini değerlendirmek için kontrolör,
kontrolör veya başka herhangi bir kişi tarafından gerçek kişiyi tanımlamak
amacıyla "makul olarak kullanılması olası tüm araçları" göz önünde
bulundurmalıdır - tekilleştirme, bağlanabilirlik ve çıkarım dahil (WP29 üç
testi). Bunlardan herhangi biri gerçekçiyse veri kişisel veri olarak kalır
ve GDPR uygulanmaya devam eder.

Bu belge şunları tanımlar:

- Maskeleme, pseudonimizasyon ve anonimleştirme arasındaki fark.
- Teknik aileleri ve her birinin uygun olduğu durumlar.
- Her yayım ile birlikte yapılması gereken risk temelli değerlendirme.
- ISO/IEC 20889 ve 27559 hizalaması dahil yönetişim.

## 2. Tanımlar

| Terim | Tanım |
|-------|-------|
| **Maskeleme** | Yetkisiz görüntüleyenlerin değerleri okuyamaması için bir UI veya logda değerleri değiştirme veya gizleme. Altta yatan kayıt değişmez. Tek başına bir gizlilik garantisi değildir. |
| **Pseudonimizasyon** (Md. 4(5)) | Tersine çevrilebilir teknik - tanımlayıcıları tokenlarla değiştirme, eşleme ayrı tutulur. Veri kişisel kalır. |
| **Anonimleştirme** (Resital 26) | Makul olarak kullanılması olası tüm araçları göz önünde bulundurarak veri ile herhangi bir tanımlanmış veya tanımlanabilir kişi arasındaki bağı kaldıran tersine çevrilemez teknik. Veri artık kişisel değildir. |
| **De-identification** | Hem pseudonimizasyon hem anonimleştirmeyi kapsayan şemsiye terim (ISO 20889 tarafından kullanılır). |

## 3. WP29 Üç Testi

Bir yayımı "anonimleştirilmiş" olarak ilan etmeden önce kontrolör değerlendirir:

1. **Tekilleştirme** - bir bireyi benzersiz şekilde tanımlayan bir kaydı
   izole etmek mümkün mü?
2. **Bağlanabilirlik** - aynı veri kümesinde veya veri kümeleri arasında aynı
   bireye ait iki kaydı bağlamak mümkün mü?
3. **Çıkarım** - diğer öznitelik değerlerinden bir özniteliğin değerini
   önemli olasılıkla çıkarmak mümkün mü?

Üçünün de cevabı makul olasılıkla "hayır" ise veri anonim olarak ele
alınabilir.

## 4. Teknik Aileler (ISO/IEC 20889)

### 4.1 Kaldırma ve genelleme
- Tanımlayıcıların doğrudan kaldırılması (adlar, kimlikler, iletişim).
- Genelleme - hassasiyetin azaltılması (doğum tarihi -> doğum yılı, posta
  kodu -> bölge).
- Üst / alt kodlama - aykırı değerleri sınırlama (yaş >= 90 toplulaştırılır).

### 4.2 Bastırma
- Bir değer çok nadir olduğunda hücre bastırma.
- Tüm kayıt benzersiz olduğunda kayıt bastırma.

### 4.3 Karıştırma
- Gürültü ekleme.
- Yuvarlama.
- Mikro toplulaştırma.

### 4.4 Pseudonimizasyon
- Tokenizasyon, FPE, gizli tuzlu HMAC (`encryption.md`).

### 4.5 Diferansiyel Gizlilik
- Bir gizlilik bütçesi (epsilon) ile parametrize edilen, herhangi bir tek
  bireyin sorgu sonucuna katkısını sınırlayan dikkatlice kalibre edilmiş
  gürültü.

### 4.6 Sentetik Veri
- Gerçek veri üzerinde eğitilmiş, istatistiksel özellikleri koruyan yapay
  kayıtlar üreten üretken modeller.

## 5. k-Anonim

Bir veri kümesi her kaydın yarı tanımlayıcı kombinasyonunun en az k-1 başka
kayıt tarafından paylaşıldığında **k-anonim**'dir. Pratik rehberlik:

- k'yı bağlama göre seç, sihirli sayı olarak değil. k = 5 düşük riskli
  yayımlar için sık bir temel; sağlık için k = 11; yüksek hassasiyetli küçük
  popülasyonlar için k = 20.
- Yarı tanımlayıcılar sayılmalıdır (yaş, cinsiyet, posta kodu, meslek, kabul
  tarihi ...). Bunları sayamamak yeniden tanımlamanın en yaygın nedenidir.
- k-anonim, hassas öznitelik denklik sınıfı içinde tek tip olduğunda
  öznitelik açıklamaya karşı koruma sağlamaz.

## 6. l-Çeşitlilik

Bir veri kümesi, her denklik sınıfı (yarı tanımlayıcıları paylaşan kayıt
kümesi) hassas öznitelik için en az l "iyi temsil edilen" değer içerdiğinde
**l-çeşitliliğe** sahiptir. Çeşitler:

- Distinct l-çeşitlilik - en az l farklı hassas değer.
- Entropy l-çeşitlilik - hassas değerlerin entropisi >= log(l).
- Recursive (c, l)-çeşitlilik - eğikliği sınırlar.

l-çeşitlilik homojenlik saldırılarını ele alır ancak eğiklik veya benzerliği
ele almaz (örn., farklı kodlar olan ancak anlamsal olarak yakın hastalıklar).

## 7. t-Yakınlık

Bir veri kümesi, herhangi bir denklik sınıfı içindeki hassas özniteliğin
dağılımı genel tablodaki dağılıma t mesafesi içindeyse **t-yakınlığa**
sahiptir. t-yakınlık, fayda kaybı pahasına benzerlik ve eğiklik saldırılarını
azaltır.

t seçimi uygulamaya özgüdür; sağlık toplamları için 0,1 ila 0,3 aralığında t
yaygındır.

## 8. Diferansiyel Gizlilik

DP matematiksel bir garanti sağlar:

Tek bir kayıtla farklı iki veri kümesi için ve olası çıktıların herhangi bir
S alt kümesi için, Pr[M(D1) S içinde] <= e^epsilon * Pr[M(D2) S içinde]

Pratik hususlar:

- **Yerel DP** - kontrolöre gönderilmeden önce cihazda eklenen gürültü. Daha
  güçlü kullanıcı garantisi, daha zayıf analitik fayda.
- **Merkezi DP** - kontrolör tarafından toplamları yayımlamadan önce eklenen
  gürültü. Daha iyi fayda, kontrolörün uygulamasına güven gerektirir.
- **Gizlilik bütçesi** - epsilon sonludur. Aynı veri kümesinde tekrarlanan
  sorgular bütçeyi tüketir; kontroller global bir bütçe sınırı uygulamalı ve
  bunun ötesindeki sorguları reddetmelidir.
- **Kompozisyon** - sıralı kompozisyon bütçeleri ekler; tekrarlanan sorgular
  için gelişmiş kompozisyon teknikleri uygulanır.
- **Uygulama** - IBM diffprivlib, Google DP, OpenDP ve Tumult Analytics gibi
  kütüphaneler en olgun primitifleri taşır. Uygulama hataları yaygındır;
  üretim dağıtımları dış inceleme gerektirir.

DP, kayıt başına kesin sadakatin gerekli olmadığı istatistiksel yayımlar,
gösterge tabloları ve ML eğitimi için uygundur.

## 9. Sentetik Veri

Sentetik veri, gerçek veri üzerinde eğitilmiş bir modelden üretilir:

- Tablo - GAN'lar, VAE'ler, kopulalar, Bayes ağları.
- Metin / zaman serisi - sıra modelleri.
- Hibrit - gerçek dağılımlarla yönlendirilen simülasyonlar.

Gizlilik otomatik değildir. Üyelik çıkarımı, öznitelik çıkarımı ve yeniden
yapılandırma saldırıları literatürde belgelenmiştir. Gerekli kontroller:

- Sızıntıyı sınırlamak için DP altında eğit (DP-SGD veya PATE).
- Yayım öncesi sentetik yayımı gizlilik kırmızı takımıyla test et.
- Yayım dosyasında fayda-gizlilik takasını belgele.
- Yeniden tanımlama potansiyeli olan sentetik veriyi aksini kanıtlayana
  kadar kişisel veri olarak ele al.

## 10. Yeniden Tanımlama Risk Değerlendirmesi

Her tanımsızlaştırılmış veri yayımı belgelenmiş bir değerlendirmeden geçer:

1. **Yayım bağlamını tanımla** - hedef kitle (kamuya açık vs güvenilir
   alıcı), amaç, sözleşmesel kısıtlar.
2. Dış bilgi (kamuya açık veri kümeleri) ve düşman yeteneği dahil **yarı
   tanımlayıcıları say**.
3. Tekniğe uygun **risk metriklerini hesapla** (k, l, t, epsilon, sağlıkta
   ISO 25237 başına savcı / gazeteci / pazarlamacı riski).
4. DPO tarafından belirlenen ve tanımsızlaştırma kayıt defterinde kaydedilen
   **eşiğe karşılaştır**.
5. Risk eşiği aşarsa **ek kontrol uygula** (daha fazla genelleme, bastırma,
   daha düşük epsilon, alıcı üzerinde sözleşmesel kısıtlar).
6. **Onayla** - DPO ve veri yöneticisi yayımdan önce imzalar; yayım dosyası
   arşivlenir.

Dosya veri kümesini, teknik parametrelerini, risk metriklerini, kontrolleri
ve onayı kaydeder.

## 11. ISO/IEC 27559 Çerçevesi

Kontrolör süreci ISO/IEC 27559:2022 ile hizalar:

1. Tanımsızlaştırma bağlamını oluştur.
2. Doğrudan ve dolaylı tanımlayıcıları belirle.
3. Kabul edilebilir risk seviyesini belirle.
4. Teknik ve parametreleri seç.
5. Veri ve motivasyon kontrolleri dahil kontrolleri uygula.
6. Kalan riski ölçerek doğrula.
7. Tehdit ortamı (ve düşman yardımcı bilgisi) geliştikçe izle ve yeniden
   değerlendir.

## 12. Operasyonel Kontroller

- Merkezi bir tanımsızlaştırma kayıt defteri her tekrarlayan yayımı
  listeler.
- Kamuya açık alana yönelik yayımlar ek bir ikinci-göz incelemesi alır.
- Alıcı sözleşmeleri yeniden tanımlama girişimlerini yasaklar ve herhangi bir
  olayın bildirilmesini gerektirir.
- Yayımdan bu yana mevcut hale gelmiş olabilecek yeni yardımcı bilgilere
  karşı yayımların yıllık incelemesi.
- Yeniden tanımlama riski arttığında (yeni bağlanabilir veri kümesi
  yayımlandığında), yayım yeniden değerlendirilir ve geri çekilebilir veya
  daha güçlü kontrollerle yenilenebilir.

## 13. Yaygın Anti-Desenler

- Yalnızca doğrudan tanımlayıcıları hashleyerek "anonimleştirme" - bağlanabilir.
- Adları kaldırma ancak doğum tarihi + posta kodu tutma - yaygın olarak
  yeniden tanımlayıcı olduğu gösterilmiştir.
- Bastırma olmadan küçük popülasyonlarda toplamlar.
- "Anonimleştirilmiş" konum izlerini paylaşma - yeniden tanımlanabilir
  olarak iyi belgelenmiştir.
- VKD'lerde pseudonimizasyonu anonimleştirme olarak ele alma
  (`06-organizational-measures/dpia.md`).
- Belgelenmiş bütçe tahsisi olmadan epsilon "mümkün olduğunca küçük"
  ayarlanan diferansiyel gizlilik.

## 14. KPI'lar

| Metrik | Hedef |
|--------|-------|
| Yeniden tanımlama değerlendirmesi olan tanımsızlaştırılmış yayımlar | %100 |
| Belgelenmiş k, l, t veya epsilon ile yayımlar | %100 |
| Yürürlükte olan alıcı sözleşmeleri | %100 |
| Yeniden tanımlama olayları | 0 |
| Zamanında tamamlanan yıllık incelemeler | %100 |

## 15. Eşleme

| Gereklilik | GDPR | ISO 27002:2022 | NIST CSF 2.0 |
|------------|------|----------------|--------------|
| Anonimleştirme | Resital 26 | 8.11 | PR.DS-2 |
| Pseudonimizasyon | Md. 4(5), 32(1)(a) | 8.11 | PR.DS-2 |
| ISO çerçeveleri | yok | 8.11 (ISO 20889 / 27559 çapraz referans) | yok |
