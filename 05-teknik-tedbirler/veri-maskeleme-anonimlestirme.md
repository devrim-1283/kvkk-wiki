---
Doküman: Veri Maskeleme, Tokenization, Anonimleştirme ve Pseudonymization Standardı
Bölüm: 05-teknik-tedbirler
Sahip: Veri Mühendisliği Lideri / KVKK Sorumlusu (anonimlik değerlendirme)
Onaylayan: BT Direktörü + KVKK Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (yeni veri kümesi, yeni teknik, re-identification kanıtı)
İlgili Mevzuat: 6698 sayılı KVKK m.7 (Silme/Yok Etme/Anonim Hale Getirme), m.28 (Anonim hale getirilen veri); Kişisel Verilerin Silinmesi, Yok Edilmesi veya Anonim Hale Getirilmesi Hakkında Yönetmelik; Kişisel Veri Güvenliği Rehberi — "Veri Maskeleme"
İlgili Standart: ISO/IEC 27001:2022 A.8.11 (Data Masking); ISO/IEC 20889 (Privacy Enhancing Data De-identification Terminology and Classification of Techniques); ISO/IEC 27559 (Privacy-enhancing data de-identification framework); NIST SP 800-188 (De-Identifying Government Datasets); NIST IR 8053; ENISA "Pseudonymisation Techniques and Best Practices"; GDPR Recital 26 (anonimlik test çerçevesi)
---

# Veri Maskeleme, Tokenization, Anonimleştirme ve Pseudonymization

## 1. Amaç

Kişisel verinin **gerçek değerinin** ifşa edilmediği bağlamlarda (test, geliştirme, eğitim, analitik, log, BI, demo) operasyonel ihtiyaca cevap veren ama **gizlilik garantisi** sunan teknik yöntemleri standardize eder. KVKK m.7 anonimleştirme zorunluluğunun teknik temelini ve test/dev ortamı için maskeleme zorunluluğunun çerçevesini oluşturur.

## 2. Kavramsal Ayrım — Kritik

| Kavram | KVKK Statüsü | Geri Döndürülebilir mi? | Kim için |
|--------|--------------|--------------------------|----------|
| **Maskeleme (Masking)** | Hâlâ kişisel veri (görüntüleme katmanı) | Evet (orijinal saklı) | Sınırlı görüş için |
| **Tokenization** | Hâlâ kişisel veri (token + map = re-identifiable) | Vault üzerinde evet | Ödeme/kart, dahili sistemler |
| **Pseudonymization (Müstear)** | Hâlâ kişisel veri (KVKK kapsamı **devam eder**) | Anahtarla evet | Analitik, yan kullanım |
| **Anonymization (Anonim)** | KVKK **kapsam dışı** (m.28) | **Hayır** — geri çevrilemez | Kamuya açık paylaşım, istatistik |

**Kritik uyarı:** GDPR Recital 26 ve KVKK Yönetmeliği'ne göre veri "anonim" sayılabilmesi için **makul bütün araçlarla bile** ilgili kişiye geri bağlanamaz olmalıdır. Sadece doğrudan tanımlayıcıyı kaldırmak (de-identification) **anonimleştirme değildir** — re-identification riski hâlâ vardır. Bu nedenle gerçek anonimleştirme yüksek bir bardır ve formel risk değerlendirmesi ister.

## 3. Veri Maskeleme

### 3.1. Türler

| Tür | Tanım | Kullanım |
|-----|-------|----------|
| **Static Data Masking (SDM)** | Kalıcı, üretim klonu sırasında bir kez maskelenir, sonraki erişimlerde gerçek değer dönmez | Test/dev/eğitim ortamı |
| **Dynamic Data Masking (DDM)** | Üretim DB'sinde veri değişmez; sorgu cevabı kullanıcının yetkisine göre maskeli/açık döner | İç destek/QA, yetkisiz görüş |
| **On-the-Fly Masking** | Üretimden test ortamına aktarım sırasında stream halinde maskeleme | DataOps boru hattı |

### 3.2. Maskeleme Teknikleri

| Teknik | Örnek | Notlar |
|--------|-------|--------|
| Karakter ikamesi | `0532-***-**67` | Görsel format korunur; UI'da yeterli |
| Hash | `SHA-256(email + tuz)` | Geri çevrilemez ama bağlanabilir |
| Tokenization | `42342342` → `tok_x9k2…` | Vault tarafında geri çevrilebilir |
| Shuffle | Kolon değerleri kayıtlar arasında karıştırılır | İstatistik korunur, satır eşlemesi bozulur |
| Substitution | Gerçek isim → sahte isim listesi | Format korunur |
| Nulling / Redaction | "REDACTED" | Bilgi kaybı yüksek; bazı testler için yetersiz |
| Date variance | ±N gün rastgele | Sıralama korunur |
| Numeric variance | ±%X | Toplama-ortalama yaklaşık korunur |
| Encryption (AES) | Şifreli sütun | DB içinde maskeli görüntüleme için |
| FPE (Format-Preserving Encryption — FF1) | Kart no şifresi yine 16 hane | Tip-uyumlu uygulamalar |

### 3.3. Test/Dev Ortamı için Zorunlu Kurallar

- **Üretim verisi test/dev'e ham yazılamaz.** İhlal durumunda doğrudan KVKK bulgusudur.
- Klonlama anında, **maskeleme boru hattının çıktısı** test ortamına yazılır.
- Maskeleme kuralları **alan listesi + alan başına teknik** olarak versiyonludur (kod / config repo'da).
- Yeni alan eklendiğinde, klasifikasyon → maskeleme kuralı **CI gate** ile zorunlu kılınır.
- "Test data" olarak gözüken her veri alanı periyodik olarak **gerçek üretim değeri var mı?** taraması ile kontrol edilir (DLP discovery).

### 3.4. Referansiyel Bütünlük

- TC kimlik gibi alan birden fazla tabloda kullanılıyorsa, maskeleme **deterministic** olmalıdır (aynı girdi her seferinde aynı maskeli çıktıyı üretir) — JOIN'lerin çalışması için.
- Format-preserving deterministic encryption (FF1) tercih edilir.

### 3.5. Görsel Maskeleme (UI)

- Çağrı merkezi temsilcisi ekranında kart numarası `**** **** **** 1234`, telefon `0532 *** ** 67`.
- Yetkili kullanıcı "doğrula" butonuyla tek seferde, gerekçeli, audit'li olarak görür.

## 4. Tokenization

### 4.1. Çalışma Prensibi

```
Üretim sistem ────► Tokenization Service ────► Token (ör. tok_AbC123)
       ▲                    │
       │                    ▼
   Sadece token       Token Vault (PAN ↔ Token map, HSM-protected)
       │                    ▲
       └─── Vault çağrı ────┘ (yetkili sistem, audit)
```

- Üretim sistemleri **token** ile çalışır; gerçek değer yalnızca tokenization vault'unda.
- Vault HSM'de korunur, erişim çok dar yetkili (PCI scope'u küçültür).
- Token tipi:
  - **Format-preserving:** orijinal formata sahip (kart numarası uzunluğu).
  - **Format-non-preserving:** tamamen rastgele.
- Vault'a erişimi olmayan tüm sistemler PCI scope dışında kalabilir (DSS scope reduction).

### 4.2. FPE vs Tokenization

| Kriter | FPE | Tokenization |
|--------|-----|--------------|
| Reversal | Anahtarla | Vault map ile |
| Format | Korunur | Korunabilir / korunmayabilir |
| Anahtar dağılımı | Daha geniş | Yok (vault tek nokta) |
| Bağımlılık | Anahtar | Vault HA |
| Tipik kullanım | DB içi şifreleme + format gereği | Ödeme, scope reduction |

## 5. Pseudonymization (Müstear)

### 5.1. Tanım

Doğrudan tanımlayıcı (isim, TC, e-posta) bir **müstear** (örn. rastgele ID veya hash) ile değiştirilir; mapping ayrı, korumalı bir yerde tutulur. **Veri hâlâ KVKK kapsamındadır**, çünkü mapping ile yeniden tanımlanabilir.

### 5.2. Yöntemler

- **Counter-based:** veritabanı sıralı ID. Risk: sıralama bilgi sızdırır (kayıt sayısı, sıra).
- **Random ID:** UUID v4 / v7. Tercihli.
- **Cryptographic hash:** SHA-256(value + tuz). Tuzun sızması = pseudonymization sızması.
- **Keyed hash (HMAC-SHA256):** anahtarla; daha güvenli.
- **Encryption:** AES-GCM ile. Anahtar erişimi olmayan, yeniden tanımlayamaz.

### 5.3. Kullanım Alanları

- Analitik veri ambarı / lakehouse: mapping erişimi sıkı sınırlandırılmış, KVKK Sorumlusu onayıyla.
- Araştırma, raporlama.
- Çapraz veri kümesi birleştirme (aynı pseudonym ile).
- Özellikle özel nitelikli veriyle çalışılan analitikte tercih edilir.

### 5.4. Kuvvetlendirme

- Mapping HSM/vault'ta.
- Log'da pseudonymized değer, gerçek değer asla.
- Pseudonym yıllık veya kayıt-bazlı dönüştürme (rotating pseudonym) mümkün.
- Quasi-identifier (yaş, posta kodu, cinsiyet) ek olarak generalize / suppress edilmediyse, pseudonymization tek başına yetersiz olabilir (re-identification risk).

## 6. Anonymization (Anonim Hale Getirme)

### 6.1. Anonim Sayılma Eşiği

KVKK Yönetmeliği "Anonim hale getirme; kişisel verinin başka verilerle eşleştirilse dahi hiçbir surette belirli veya belirlenebilir bir gerçek kişiyle ilişkilendirilemeyecek hâle getirilmesi" der. **Pratik test:** "Saldırgan, makul kaynaklarla, makul zaman ve maliyetle yeniden tanımlama yapamasın."

### 6.2. Klasik Teknikler

#### 6.2.1. Suppression (Bastırma)
Belirli alanları/kayıtları kaldırma. Düşük frekanslı kayıtlar silinir.

#### 6.2.2. Generalization (Genelleme)
Belirli değeri kaba kategoriye çevirme:
- Yaş 34 → "30-39"
- Posta kodu 06800 → "068**"
- Tarih 12.05.2026 → "2026-Q2"

#### 6.2.3. Aggregation
Bireysel kayıt yerine grup özetleri.

#### 6.2.4. Perturbation / Noise Injection
Sayısal değerlere küçük rastgele gürültü ekleme.

#### 6.2.5. Microaggregation
Benzer k kayıt grubunun her birini grup ortalamasıyla değiştirme.

### 6.3. k-Anonymity

Her kayıt en az **k-1** başka kayıtla quasi-identifier setinde aynı görünmeli. k=5 yaygın eşik; hassas verilerde k=10–20 önerilir.

**Sınırlama:** Eğer grup içindeki **hassas öznitelik** çeşitlilik göstermiyorsa (örn. herkes aynı hastalığa sahip), k-anonim yetmez.

### 6.4. l-Diversity

Her quasi-identifier sınıfında, hassas öznitelik en az **l** farklı değer almalı. Anlamlı çeşitlilik gerektirir.

### 6.5. t-Closeness

Hassas özniteliğin sınıf-içi dağılımı, genel popülasyon dağılımına yakın (≤ t Earth Mover's Distance) olmalı.

### 6.6. Differential Privacy

Modern altın standart. Bir kişinin kayıtta bulunup bulunmamasının çıktıya etkisi matematiksel olarak sınırlandırılır (ε — privacy budget). Apple, Google, ABD Census kullanır.

- **Globalde gürültü** veya **lokalde gürültü** (LDP).
- Aggregation queries ve ML eğitiminde kullanılabilir.
- ε ne kadar küçük → gizlilik o kadar yüksek, fayda o kadar düşük.
- ε bütçesi takip edilir; tek veri kümesinde sorgular birikim yapar.

### 6.7. Synthetic Data

Gerçek veri kümesinin **istatistiksel özelliklerini** öğrenen üretim modelinden (GAN, VAE, kopula) yeni, sentetik kayıtlar üretmek. Doğru yapılırsa anonim, ama:

- Model kapasitesi yüksekse memorization (orijinal kayıtların ezberlenmesi) riski.
- Synthetic data anonim **kabul edilebilmesi için** privacy guarantee (örn. DP-trained generator) zorunlu.

## 7. Re-identification Risk Değerlendirmesi

Anonimleştirilmiş veri yayınlanmadan / paylaşılmadan **önce** zorunlu rapor:

### 7.1. Risk Modelleri (ISO/IEC 20889 / ISO/IEC 27559)

- **Prosecutor:** saldırganın bildiği belirli bir bireyi arayışı.
- **Journalist:** rastgele bir bireyi tanımlamayı amaçlar.
- **Marketer:** geniş ölçekli, yüzde olarak ne kadar yeniden tanımlanır?

### 7.2. Sorulacak Sorular

- Hangi quasi-identifier'lar var?
- Saldırganın elinde dışsal hangi veriler olabilir? (Seçmen listesi, sosyal medya, sızdırılmış DB, ticari pazarlama listesi.)
- En küçük equivalence class size nedir? (k)
- Hassas öznitelikler nasıl dağılıyor? (l, t)
- ML/aggregation çıkışı membership inference saldırısına dayanıyor mu?
- Yayın ölçeği? (kapalı analitik, ortak çalışan, kamuya açık?)

### 7.3. Tablo: Kabul Edilebilir Risk Eşiği

| Yayın Modu | Hedef k | DP ε (varsa) | Onay |
|------------|---------|----------------|------|
| Dahili analitik (sıkı erişim) | 5 | – | Veri Sahibi |
| Kontrollü ortak | 10 | ≤ 4 | KVKK Sorumlusu |
| Kamuya açık | 20+ | ≤ 1 | KVKK Komitesi + dış uzman görüşü |

### 7.4. Belgeleme

- Anonimleştirme öncesi orijinal veri kümesi adı, sahibi, alanlar.
- Uygulanan teknikler ve parametreler.
- Risk değerlendirme sonucu, onay zinciri.
- Yayın sonrası izleme planı (re-identification şüphesi geri besleme).
- Saklama: anonim kabul edilen sürüm KVKK m.28 dışı; mapping/orijinal kayıt İmha Yönetmeliği uyumlu.

## 8. Pratik Senaryolar

### 8.1. Senaryo: Geliştirici Test Veri Kümesi

- Production DB → DataOps maskeleme pipeline → Test DB.
- Maskeleme kuralları: TC kimlik FPE (deterministic), e-posta substitution, tarih ±30 gün, ad/soyad fake-name listesinden, hassas veri (sağlık) tamamen sentetik.
- CI gate: "her yeni alan classification + masking rule yoksa fail".

### 8.2. Senaryo: BI Analitik

- Pseudonymized müşteri ID + generalized yaş, posta kodu (5'lik dilim), agregate metrikler.
- Mapping (pseudonym → gerçek müşteri) ayrı vault'ta, sadece KVKK Sorumlusu onayıyla erişim.
- BI dashboard'larda asla doğrudan tanımlayıcı yer almaz.

### 8.3. Senaryo: ML Eğitim Verisi

- Eğer model ezberlerse re-identification kanıtı oluşturabilir.
- Differential Privacy ile eğitim (DP-SGD), federated learning, secure aggregation.
- Eğitim verisi minimum gerekli alanlarla.
- Modelin "memorization audit"i (membership inference test) yıllık.

### 8.4. Senaryo: Akademik / Açık Veri Yayını

- En sıkı kontroller. Dış uzman görüşü, k≥20, DP, suppression yüksek.
- Yayım sonrası re-identification olayı izleme.

## 9. Loglama ve Audit

- Maskeleme job'ları (girdi kaynağı, kural seti versiyonu, çıktı, kayıt sayısı).
- Vault erişim (tokenization, pseudonymization mapping).
- Anonimleştirme süreci (öncesi/sonrası özet, parametreler, risk raporu).
- Test ortamına yazılan veri taramaları (gerçek PII bulunursa kritik alarm).

## 10. Kontrol Listesi

- [ ] Test/dev/eğitim ortamlarında ham üretim verisi yok mu (tarama doğrulamalı)?
- [ ] Maskeleme pipeline kod/config repo'da, versiyonlu mu?
- [ ] Yeni alan eklendiğinde classification + masking rule CI gate ile zorunlu mu?
- [ ] Deterministic masking referansiyel bütünlüğü koruyor mu?
- [ ] UI üzerinde varsayılan görüntü maskeli, "doğrula"ya tıklama audit'li mi?
- [ ] Tokenization vault HSM korumalı, erişim sıkı mı?
- [ ] Pseudonymization mapping ayrı, korumalı, audit'li mi?
- [ ] Pseudonymized verinin de KVKK kapsamında olduğu belgeli mi?
- [ ] Anonim yayın öncesi formel re-identification risk değerlendirmesi yapılıyor mu?
- [ ] k-anon, l-diversity, t-closeness veya DP parametreleri kayıtlı mı?
- [ ] DP ε bütçesi takip ediliyor mu?
- [ ] Synthetic data privacy garantisiyle üretiliyor mu (memorization auditli)?
- [ ] Anonimleştirme onay zinciri (KVKK Sorumlusu / Komite) belgeli mi?
- [ ] DLP ile test ortamında PII tarama yapılıyor mu?
- [ ] Anonim sürüm + orijinal sürüm + mapping yaşam döngüleri ayrı yönetiliyor mu?

## 11. Yaygın Hatalar

- "MD5 hash" ile pseudonymization → sözlük + brute force ile geri çözülür (özellikle TC kimlik gibi sınırlı alan).
- "İsmi sildim, anonim oldu" → quasi-identifier'larla tekrar tanımlanır.
- Test ortamında "production'dan birkaç kayıt çekelim, hızlı debug" → KVKK ihlali.
- Maskelemenin yalnızca UI'da yapılması (DB / loglarda gerçek değer var) → log scraping ile sızar.
- Tokenization vault'unda standart erişim → scope reduction kazancı yok.
- Anonim sürüm yayınlandıktan sonra ek bir bilgi kaynağıyla re-identification olabileceğini değerlendirmemek.

## 12. Sürekli İyileştirme

- Yıllık bir kez **iç red team / dış uzman** ile re-identification denemesi (anonim yayınlanmış veri kümeleri üzerinde).
- Yeni teknik literatür (özellikle privacy-preserving ML) takibi.
- Re-identification olay/şüphesi olduğunda derhal soruşturma + yayının geri çekilmesi.
