---
Doküman / Document: Kişisel Veri ve Özel Nitelikli Kişisel Veri Ayrımı / Distinction Between Personal Data and Sensitive (Special Category) Personal Data
Bölüm / Section: 01-temel-kavramlar
Sahip / Owner: KVKK Sorumlusu / KVKK Officer
Onaylayan / Approved by: Yönetim Kurulu / Genel Müdür / Board of Directors / CEO
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş (mevzuat değişikliği, Kurul kararı) / Annual + triggered (regulatory change, Kurul decision)
İlgili Mevzuat / Legal Reference: 6698 sayılı KVKK m.3, m.5, m.6; Kurul Kararı 31/01/2018, 2018/10 (özel nitelikli ek tedbirler) / KVKK Art. 3, 5, 6; Kurul Decision 31/01/2018, 2018/10 (additional safeguards for sensitive data)
---

## English

# Distinction Between Personal Data and Sensitive (Special Category) Personal Data

## 1. Purpose

This document is prepared to clearly distinguish the concepts of **personal data** and **sensitive (special category) personal data** under KVKK, set out the operational criteria to be used in classification decisions, and prevent commonly made mistakes.

## 2. Definition of Personal Data

### 2.1 Legal Definition
KVKK Art. 3/1(d): "Any information relating to an identified or identifiable natural person."

### 2.2 Two Elements

**(a) Identified OR identifiable:**
- **Identified:** Data that directly identifies (National ID, name and surname + date of birth, biometric, etc.)
- **Identifiable:** May not identify on its own; with another piece of data or with reasonable effort, the identity can be revealed.

**(b) Natural person:** Legal entities (companies) are not data subjects. However, data of natural persons who are owners/officers of a company is in scope.

### 2.3 The "Identifiability" Test

Questions to be asked when determining whether data is personal data:
1. Can I identify a natural person using this data alone?
2. If not: Does the data controller or another reasonable party hold any other data?
3. Can these data be combined with reasonable effort to identify the person?
4. If yes → it is personal data.

### 2.4 Examples of Personal Data (Wide Spectrum)

| Type | Example |
|------|---------|
| Direct identity | Name and surname, National ID, passport number, tax number |
| Direct contact | Phone, e-mail, address |
| Online identifier | IP address, device ID, cookie ID, MAC address |
| Location | GPS coordinates, IP-based location, base station |
| Behavioral | Click trails, session logs, purchase history |
| Visual/audio | Photo, video recording, voice recording, CCTV |
| Financial | Bank account number, card number (partial or full), salary, credit score |
| Professional | Position, employment history, performance data |
| Education | Graduation information, transcript |
| Social | Family ties, marital status |
| Device/Technical | UA information, screen resolution (when matched with the person) |

## 3. Sensitive (Special Category) Personal Data

### 3.1 Exhaustive List (KVKK Art. 6/1)
Sensitive (special category) personal data are listed **exhaustively (numerus clausus)**. **The list cannot be expanded by analogy.** The list is as follows:

1. **Race**
2. **Ethnic origin**
3. **Political opinion**
4. **Philosophical belief**
5. **Religion**
6. **Denomination or other beliefs**
7. **Dress and appearance**
8. **Membership of an association, foundation, or trade union**
9. **Health**
10. **Sexual life**
11. **Data relating to criminal conviction and security measures**
12. **Biometric data**
13. **Genetic data**

### 3.2 Important Notes

- The list is **exhaustive**; for example, "economic situation" or "professional performance" are not sensitive (they are general personal data).
- A separate regime applies to **health and sexual life** data (Art. 6/3).
- **Biometric and genetic** data were not included in the original 2016 text; they were added as sensitive data with the 2017 amendment.

## 4. Health and Sexual Life Data — Special Regime

### 4.1 Conditions of Processing (KVKK Art. 6/3)
Personal data relating to health and sexual life may **only** be processed:
- **With explicit consent**, OR
- For the following purposes **without seeking the data subject's explicit consent**: protection of public health, preventive medicine, medical diagnosis, treatment and care services, planning and management of healthcare services.
- Additional condition for these exception grounds: processing must be **carried out by persons under a confidentiality obligation or by authorized institutions/organizations**.

### 4.2 Other Sensitive Data (Excluding Health/Sexual Life)
- With explicit consent, OR
- May be processed where **provided in laws** (Art. 6/2).

## 5. Kurul Decision 31/01/2018, 2018/10 — Additional Adequate Measures

In addition to the general safeguards under KVKK Art. 12, the Kurul stipulates the following additional technical/administrative safeguards for processing of sensitive personal data:

### 5.1 For All Sensitive Data
- A separate **sensitive data policy** and procedure
- Limitation of personnel authorized to process and **confidentiality undertaking**
- Maintaining a separate authorization control matrix
- **Periodic training** for processing staff
- Stricter access, authorization and audit logs

### 5.2 In Electronic Environments
- Use of **cryptographic methods** (during storage and transfer)
- **Key management performed in a secure environment**
- The logs of the systems containing the data must be kept tamper-proof
- **Security updates** must be applied without interruption
- Required **security tests** must be applied to the systems

### 5.3 In Physical Environments
- **Physical security** measures against unauthorized access
- Protection against **environmental threats** (flood, fire, etc.)
- **Control and supervision** of the environment

### 5.4 During Transfer
- **By e-mail**: corporate e-mail + secure transmission (KEP, TLS)
- **Via portable memory/CD/DVD**: encryption, transmission of cryptographic key by a separate channel
- **Between different physical environments**: cryptographic methods

## 6. Decision Tree: "Is This Data Sensitive?"

```
Is the data personal data?
   |
   +-- No → Out of scope (anonymous/legal entity/out of scope)
   |
   +-- Yes ↓
        |
   Does it fall into one of the 13 categories in Art. 6/1?
        |
        +-- Yes → IT IS SENSITIVE
        |          |
        |          +-- Health or sexual life?
        |          |    |
        |          |    +-- Yes → Art. 6/3 regime (explicit consent OR
        |          |              processing by persons under a duty of
        |          |              secrecy / authorized bodies for public
        |          |              health/diagnosis/treatment etc.)
        |          |    |
        |          |    +-- No  → Art. 6/2 regime (explicit consent OR
        |          |               provided in laws)
        |          |
        |          +-- Apply additional technical/administrative safeguards under Kurul Decision 2018/10
        |
        +-- No → General personal data (Art. 5 processing conditions)
```

## 7. Practical Category Classification (Operational)

### 7.1 Definitively Sensitive (Typical Business Scenarios)

| Data | Typical Context |
|------|-----------------|
| Health report, diagnosis, medication information | HR (medical report), insurance, hospital |
| HIV, pregnancy, chronic disease | HR, insurance |
| Blood type (in emergency) | HR emergency, hospital |
| Disability status / report | HR (tax/incentive) |
| Trade union membership | HR (dues deduction) |
| Criminal record | HR (recruitment), sectoral requirement (banking, insurance) |
| Court decision / case information | Legal counsel |
| Fingerprint, retina, facial recognition | Access control, mobile banking |
| DNA test | Healthcare |
| Religion/denomination | Holiday planning, military service status (religion field) |
| Ethnic origin | Marketing segmentation (generally should not be processed) |

### 7.2 NOT Sensitive (Frequently Confused)

| Data | Why Not Sensitive? |
|------|--------------------|
| Salary, income | Financial information — general personal data under Art. 5 |
| Bank account, IBAN | Financial information — general personal data |
| Card number | General personal data (PCI-DSS sectoral regime is separate) |
| Performance evaluation | Professional information — general personal data |
| Education status | General personal data |
| Location / GPS | General personal data (location) |
| IP address | General personal data |
| Social media likes | General personal data (unless inferring religion/political opinion) |
| Cookie | General personal data |
| Phone call metadata | General personal data |

### 7.3 Borderline Cases (Context-Dependent)

| Data | Description |
|------|-------------|
| **Food preference (vegetarian, halal)** | Not sensitive on its own; but it may be linked to "religion." If processed for the purpose of inference, it may trigger the sensitive data regime. |
| **Profile photo** | General personal data. But processing for face recognition → biometric (sensitive). |
| **Voice recording** | General personal data. But extracting "voice pattern" for biometric authentication → sensitive. |
| **CCTV footage** | General. If facial recognition analysis is performed → sensitive (biometric). |
| **Gender** | General personal data (not sexual life). |
| **Identity card photocopy** | General personal data. If it shows the religion field → triggers additional sensitive regime. |
| **Membership information** | Sports club → general; trade union → sensitive; political party → sensitive. |

## 8. "Visible Identity Document" — Critical Practical Scenario

In Türkiye, the practice of obtaining identity card photocopies is widespread, so caution is required:
- Old-type ID cards displayed a **religion field** → keeping the photocopy triggered SENSITIVE data processing.
- New TC ID cards do **not** include a religion field; however, they include a "Blood Type" field (health data).
- **Practical rule:** When taking a photocopy/scan of the identity, the religion and blood type fields must be masked (the established opinion of the Kurul).
- Best practice: Capture only the necessary fields (National ID + name and surname + photo); avoid taking a full photocopy.

## 9. Common Mistakes and Preventive Steps

| Mistake | Preventive Approach |
|---------|---------------------|
| Expansive interpretation instead of "the sensitive list is exhaustive" | Training emphasizes that the Art. 6/1 list is exhaustive |
| Health report visible to all in HR | Restricted access; only health unit/HR officer |
| Religion/blood type fields left visible on identity photocopy | Automatic masking; reference image guidance at intake |
| Bulk listing during trade union dues deduction | Restricted list access; confidentiality undertaking; encrypted transmission |
| Implementing biometric entry without explicit consent on grounds of "convenience" | Explicit consent is mandatory (where not health/sexual life); alternative method must be offered |
| Failure to record privacy notice for camera-based recognition systems | DPIA + supplementary privacy notice + Kurul Decision 2018/10 measures |
| Failure to distinguish general vs sensitive in CCTV recordings | CCTV is generally general; if facial recognition analysis is performed it is biometric |
| Keeping criminal records during recruitment | Should not be requested unless there is a sectoral mandate; if requested, lawful basis and necessity must be demonstrated |
| Believing one can freely process "publicly available sensitive data" | Public availability does not grant a right to free processing; the Art. 6 regime still applies |

## 10. Classification Operation (Connection to the Inventory)

Each entry in the data inventory contains the following classification field:

| Data Category | Sensitivity Class | Lawful Basis | Access Level |
|---------------|-------------------|--------------|--------------|
| Health report | Sensitive (Health) | Art. 6/3 | "Confidential" |
| Payslip | General Personal Data | Art. 5/2(a) - expressly provided in laws | "Internal" |
| Performance score | General Personal Data | Art. 5/2(f) - legitimate interest | "Internal" |
| Fingerprint | Sensitive (Biometric) | Art. 6/2 - explicit consent | "Highly Confidential" |

## 11. Reflection Across Compliance Documents

The classification of data as sensitive must be reflected in the following documents:
- **Data inventory**: sensitivity field
- **VERBİS notification**: sensitive data category field
- **Retention and Erasure Policy**: separate retention table for sensitive
- **Access matrix**: stricter authorization
- **Privacy notice**: explicit listing of processed sensitive data
- **Explicit consent text**: specific consent for the sensitive category
- **Training**: additional module in role-based training
- **Supplier contract**: additional clauses for suppliers processing sensitive data

## 12. Related Documents

- `01-temel-kavramlar/tanimlar.md`
- `01-temel-kavramlar/isleme-sartlari.md`
- `02-envanter-ve-sicil/envanter-rehberi.md`
- `05-teknik-tedbirler/ozel-nitelikli-veri-tedbirleri.md`
- `06-idari-tedbirler/erisim-yetki-yonetimi.md`
- `12-mevzuat-arsiv/kurul-karari-2018-10.md`

---

## Türkçe

# Kişisel Veri ve Özel Nitelikli Kişisel Veri Ayrımı

## 1. Amaç

Bu doküman, KVKK kapsamındaki **kişisel veri** ve **özel nitelikli kişisel veri** kavramlarını net olarak ayrıştırmak, sınıflandırma kararlarında kullanılacak operasyonel kriterleri ortaya koymak ve sıkça yapılan hataları engellemek için hazırlanmıştır.

## 2. Kişisel Veri Tanımı

### 2.1 Yasal Tanım
KVKK m.3/1(d): "Kimliği belirli veya belirlenebilir gerçek kişiye ilişkin her türlü bilgi."

### 2.2 İki Unsur

**(a) Kimliği belirli VEYA belirlenebilir:**
- **Belirli:** Doğrudan kimlik tespiti yapan veriler (TCKN, ad-soyad + doğum tarihi, biyometrik vs.)
- **Belirlenebilir:** Tek başına kimlik tespiti yapmayabilir, başka veriyle eşleştiğinde ya da makul çabayla kimliği ortaya çıkarabilir.

**(b) Gerçek kişi:** Tüzel kişiler (şirketler) ilgili kişi değildir. Ancak şirket sahibinin/yetkilisinin (gerçek kişi) verisi kapsamdadır.

### 2.3 "Belirlenebilir" Testi

Bir verinin kişisel veri olup olmadığını belirlerken sorulacak sorular:
1. Bu veriyi tek başına kullanarak bir gerçek kişiyi tanıyabilir miyim?
2. Hayır ise: Veri sorumlusunun veya başka makul taraf üyesinin elinde başka veri var mı?
3. Bu verilerin makul çabayla birleştirilmesi kişiyi belirleyebilir mi?
4. Cevap evet ise → kişisel veridir.

### 2.4 Kişisel Veri Örnekleri (Geniş Yelpaze)

| Tür | Örnek |
|-----|-------|
| Doğrudan kimlik | Ad-soyad, TCKN, pasaport no, vergi no |
| Doğrudan iletişim | Telefon, e-posta, adres |
| Çevrimiçi tanımlayıcı | IP adresi, cihaz ID, çerez ID, MAC adresi |
| Konum | GPS koordinatı, IP-bazlı lokasyon, baz istasyonu |
| Davranışsal | Tıklama izleri, oturum kayıtları, satın alma geçmişi |
| Görsel/işitsel | Fotoğraf, video kaydı, ses kaydı, CCTV |
| Mali | Banka hesap no, kart no (kısmi veya tam), maaş, kredi skoru |
| Mesleki | Pozisyon, iş geçmişi, performans verisi |
| Eğitim | Mezuniyet bilgisi, transkript |
| Sosyal | Aile yakınlığı, medeni hal |
| Cihaz/Teknik | UA bilgisi, ekran çözünürlüğü (kişiyle eşleşince) |

## 3. Özel Nitelikli Kişisel Veri

### 3.1 Tahdidi Liste (KVKK m.6/1)
Özel nitelikli kişisel veriler **tahdidi (sınırlı sayıda)** sayılmıştır. **Kıyas yoluyla genişletilemez.** Liste şu şekildedir:

1. **Irk**
2. **Etnik köken**
3. **Siyasi düşünce**
4. **Felsefi inanç**
5. **Din**
6. **Mezhep veya diğer inançlar**
7. **Kılık ve kıyafet**
8. **Dernek, vakıf ya da sendika üyeliği**
9. **Sağlık**
10. **Cinsel hayat**
11. **Ceza mahkûmiyeti ve güvenlik tedbirleriyle ilgili veriler**
12. **Biyometrik veri**
13. **Genetik veri**

### 3.2 Önemli Notlar

- Liste **tahdidi**dir; örneğin "ekonomik durum" veya "mesleki performans" özel nitelikli sayılmaz (genel kişisel veridir).
- **Sağlık ve cinsel hayat** verileri için ayrı bir rejim vardır (m.6/3).
- **Biyometrik ve genetik** veriler 2016'daki ilk metinde yoktu; 2017 değişikliği ile özel nitelikli oldu.

## 4. Sağlık ve Cinsel Hayat Verisi — Özel Rejim

### 4.1 İşlenebilirlik Şartları (KVKK m.6/3)
Sağlık ve cinsel hayata ilişkin kişisel veriler **ancak**:
- **Açık rıza ile**, VEYA
- Aşağıdaki amaçlar için **ilgili kişinin açık rızası aranmaksızın**: kamu sağlığının korunması, koruyucu hekimlik, tıbbi teşhis, tedavi ve bakım hizmetlerinin yürütülmesi, sağlık hizmetlerinin planlanması ve yönetimi.
- Bu istisna sebepleri için ek koşul: **sır saklama yükümlülüğü altında bulunan kişiler veya yetkili kurum/kuruluşlar tarafından** işlenmesi gerekir.

### 4.2 Diğer Özel Nitelikli Veriler (Sağlık/Cinsel Hayat Dışı)
- Açık rıza ile, VEYA
- **Kanunlarda öngörülmesi** halinde işlenebilir (m.6/2).

## 5. Kurul Kararı 31/01/2018, 2018/10 — Ek Yeterli Önlemler

Özel nitelikli kişisel verilerin işlenmesinde, KVKK m.12'deki genel tedbirlere ek olarak Kurul tarafından öngörülen ilave teknik/idari tedbirler şunlardır:

### 5.1 Tüm Özel Nitelikli Veriler İçin
- Ayrı bir **özel nitelikli veri politikası** ve prosedürü
- İşleme yetkisi olan personelin sınırlandırılması ve **gizlilik taahhüdü**
- Yetki kontrol matrisinin ayrı tutulması
- İşleme yapacak personele yönelik **periyodik eğitim**
- Erişim, yetkilendirme ve denetim kayıtlarının daha sıkı tutulması

### 5.2 Elektronik Ortamlarda
- **Kriptografik yöntemler** kullanılması (saklama ve aktarım sırasında)
- **Anahtar yönetiminin güvenli ortamda** yapılması
- Verilerin bulunduğu **sistemlerin loglarının** kullanıcı müdahalesine kapalı tutulması
- **Güvenlik güncellemelerinin** kesintisiz uygulanması
- Sistemlere **gerekli güvenlik testlerinin** uygulanması

### 5.3 Fiziki Ortamlarda
- Yetkisiz girişlere karşı **fiziksel güvenlik** tedbirleri
- **Çevresel tehditlere** karşı (sel, yangın vb.) korunma
- Ortamın **kontrolü ve gözetimi**

### 5.4 Aktarım Sırasında
- **E-posta ile**: kurumsal e-posta + güvenli iletim (KEP, TLS)
- **Taşınabilir bellek/CD/DVD ile**: şifreleme, kriptografik anahtarın ayrı yolla iletimi
- **Farklı fiziksel ortamlar arası**: kriptografik yöntemler

## 6. Karar Ağacı: "Bu Veri Özel Nitelikli mi?"

```
Veri kişisel veri mi?
   |
   +-- Hayır → Kapsam dışı (anonim/tüzel kişi/kapsam dışı)
   |
   +-- Evet ↓
        |
   m.6/1 listesindeki 13 kategoriden birine giriyor mu?
        |
        +-- Evet → ÖZEL NİTELİKLİDİR
        |          |
        |          +-- Sağlık veya cinsel hayat mı?
        |          |    |
        |          |    +-- Evet → m.6/3 rejimi (açık rıza VEYA
        |          |              sır saklama yükümlülüğündeki kişi/kurumun
        |          |              kamu sağlığı/teşhis/tedavi vb. amacıyla)
        |          |    |
        |          |    +-- Hayır → m.6/2 rejimi (açık rıza VEYA
        |          |               kanunlarda öngörülme)
        |          |
        |          +-- Kurul Kararı 2018/10 ek teknik/idari tedbirler uygulanmalı
        |
        +-- Hayır → Genel kişisel veri (m.5 işleme şartları)
```

## 7. Pratik Kategori Sınıflandırması (Operasyonel)

### 7.1 Kesin Özel Nitelikli (Tipik İşletme Senaryoları)

| Veri | Tipik Bağlam |
|------|--------------|
| Sağlık raporu, teşhis, ilaç bilgisi | İK (sağlık raporu), sigorta, hastane |
| HIV, gebelik, kronik hastalık | İK, sigorta |
| Kan grubu (acil durumda) | İK acil durum, hastane |
| Engellilik durumu / raporu | İK (vergi/teşvik) |
| Sendika üyeliği | İK (aidat kesintisi) |
| Adli sicil kaydı | İK (işe alım), sektörel zorunluluk (banka, sigorta) |
| Mahkeme kararı / dava bilgileri | Hukuk müşavirliği |
| Parmak izi, retina, yüz tanıma | Erişim kontrol, mobil bankacılık |
| DNA testi | Sağlık |
| Din/mezhep | Bayram tatili planlama, askerlik durumu (din hanesi) |
| Etnik köken | Pazarlama segmentasyonu (genelde işlenmemeli) |

### 7.2 Özel Nitelikli OLMAYAN (Sıkça Karıştırılan)

| Veri | Niye Özel Nitelikli Değil? |
|------|----------------------------|
| Maaş, gelir | Mali bilgi — m.5 kapsamında genel kişisel veri |
| Banka hesap, IBAN | Mali bilgi — genel kişisel veri |
| Kart numarası | Genel kişisel veri (PCI-DSS sektörel rejim ayrı) |
| Performans değerlendirmesi | Mesleki bilgi — genel kişisel veri |
| Eğitim durumu | Genel kişisel veri |
| Konum / GPS | Genel kişisel veri (lokasyon) |
| IP adresi | Genel kişisel veri |
| Sosyal medya beğenileri | Genel kişisel veri (din/siyasi düşünce çıkarımı yapmadıkça) |
| Çerez | Genel kişisel veri |
| Telefon araması metaverisi | Genel kişisel veri |

### 7.3 Sınır Vakaları (Bağlama Göre)

| Veri | Açıklama |
|------|----------|
| **Yemek tercihi (vejetaryen, helal)** | Tek başına özel nitelikli değildir; ama "din" ile ilişki kuruluyor olabilir. Çıkarsama yapan amaçla işleniyorsa özel nitelikli rejimi tetikleyebilir. |
| **Profil fotoğrafı** | Genel kişisel veri. Ama yüz tanıma için işlenmesi → biyometrik (özel nitelikli). |
| **Ses kaydı** | Genel kişisel veri. Ama biyometrik kimlik doğrulama amacıyla "ses örüntüsü" çıkarımı → özel nitelikli. |
| **CCTV görüntüsü** | Genel. Yüz tanıma analizi yapılıyorsa → özel nitelikli (biyometrik). |
| **Cinsiyet** | Genel kişisel veri (cinsel hayat değil). |
| **Kimlik fotokopisi** | Genel kişisel veri. Üzerinde din hanesi varsa → özel nitelikli ek rejim. |
| **Üyelik bilgisi** | Spor kulübü → genel; sendika → özel; siyasi parti → özel. |

## 8. "Görünür Kimlik Belgesi" — Kritik Pratik Senaryo

Türkiye'de kimlik fotokopisi alımı yaygın olduğundan dikkat:
- Eski tip nüfus cüzdanlarında **din hanesi** yer alıyordu → kimlik fotokopisi tutulması ÖZEL NİTELİKLİ veri işleme tetiklerdi.
- Yeni TC kimlik kartlarında din hanesi **yoktur**; ancak "Kan Grubu" hanesi vardır (sağlık verisi).
- **Pratik kural:** Kimlik fotokopisi/taraması alınırken din ve kan grubu alanı maskelenmeli (Kurul'un yerleşik görüşü).
- En iyi uygulama: Yalnızca gereken alanları (TCKN + ad-soyad + foto) almak; tam fotokopi alınmasından kaçınmak.

## 9. Yaygın Hatalar ve Önleyici Adımlar

| Hata | Önleyici Yaklaşım |
|------|-------------------|
| "Özel nitelikli liste daraltıcıdır" yerine genişletici yorum | Eğitimde m.6/1 listesi tahdidi olduğu vurgulanır |
| Sağlık raporunu HR'da herkesin görmesi | Erişim kısıtlaması; sadece sağlık birimi/insan kaynakları yetkilisi |
| Kimlik fotokopisinde din/kan grubu alanlarının açık tutulması | Otomatik maskeleme; alımda örnek görüntü ile yönlendirme |
| Sendika aidatı kesintisinde toplu listeleme | Liste erişimi kısıtlı; gizlilik taahhüdü; şifreli iletim |
| Biyometrik girişin "kolaylık" gerekçesiyle açık rızasız uygulanması | Açık rıza zorunludur (sağlık/cinsel hayat değilse); alternatif yöntem sunulmalı |
| Kameralı tanıma sistemleri için aydınlatma metnine atlanmış kayıt | DPIA + ek aydınlatma + Kurul kararı 2018/10 tedbirleri |
| CCTV kayıtlarında genel + özel nitelikli ayrımı yapılmaması | CCTV genelde genel; ancak yüz tanıma analizi yapılıyorsa biyometrik |
| Adli sicil kaydının işe alımda tutulması | Sektörel zorunluluk yoksa istenmemeli; yoksa hukuki sebep ve zorunluluk gösterilmelidir |
| "Halka açık özel nitelikli veriler" işleyebileceğimi düşünmek | Halka açık olması serbestçe işleme hakkı vermez; yine m.6 rejimi geçerli |

## 10. Sınıflandırma Operasyonu (Veri Envanteri Bağı)

Her veri envanteri kaydında aşağıdaki sınıflandırma alanı bulunur:

| Veri Kategorisi | Hassasiyet Sınıfı | Hukuki Sebep | Erişim Düzeyi |
|------------------|--------------------|--------------|---------------|
| Sağlık raporu | Özel Nitelikli (Sağlık) | m.6/3 | "Gizli" |
| Maaş bordrosu | Genel Kişisel Veri | m.5/2(a) - kanunlarda açıkça öngörülme | "Kurum İçi" |
| Performans skoru | Genel Kişisel Veri | m.5/2(f) - meşru menfaat | "Kurum İçi" |
| Parmak izi | Özel Nitelikli (Biyometrik) | m.6/2 - açık rıza | "Çok Gizli" |

## 11. Uyum Dokümanlarına Yansımalar

Bir verinin özel nitelikli sınıflandırılması aşağıdaki dokümanlara yansımalıdır:
- **Veri envanteri**: hassasiyet alanı
- **VERBİS bildirimi**: özel nitelikli veri kategorisi alanı
- **Saklama ve İmha Politikası**: özel nitelikli için ayrı saklama tablosu
- **Erişim matrisi**: daha sıkı yetkilendirme
- **Aydınlatma metni**: işlenen özel nitelikli veriler açıkça belirtilir
- **Açık rıza metni**: özel nitelikli kategorinin spesifik onayı
- **Eğitim**: ilgili pozisyon eğitiminde ek modül
- **Tedarikçi sözleşmesi**: özel nitelikli işleyen tedarikçilere ek hükümler

## 12. İlgili Dokümanlar

- `01-temel-kavramlar/tanimlar.md`
- `01-temel-kavramlar/isleme-sartlari.md`
- `02-envanter-ve-sicil/envanter-rehberi.md`
- `05-teknik-tedbirler/ozel-nitelikli-veri-tedbirleri.md`
- `06-idari-tedbirler/erisim-yetki-yonetimi.md`
- `12-mevzuat-arsiv/kurul-karari-2018-10.md`
