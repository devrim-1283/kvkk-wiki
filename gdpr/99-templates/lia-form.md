---
title:
  en: "Legitimate Interest Assessment — Article 6(1)(f) Form"
  tr: "Mesru Menfaat Degerlendirmesi — Madde 6(1)(f) Formu"
section: "99-templates"
owner: "DPO / Legal"
version: "1.0"
last_review: "2026-05-08"
next_review: "2026-11-08"
classification: "Internal"
languages: ["en", "tr"]
keywords:
  en: ["LIA", "Article 6(1)(f)", "balancing test", "legitimate interest"]
  tr: ["MMD", "Madde 6(1)(f)", "dengeleme testi", "mesru menfaat"]
---

## English

# Legitimate Interest Assessment (LIA)

The LIA documents the controller's reliance on Article 6(1)(f) GDPR — legitimate interests pursued by the controller or by a third party, except where overridden by the interests or fundamental rights and freedoms of the data subject which require protection of personal data, in particular where the data subject is a child.

This template follows the **three-step test** elaborated in WP217 and consistently endorsed by the EDPB and SAs:

1. **Purpose test** — is there a legitimate interest?
2. **Necessity test** — is the processing necessary for that interest?
3. **Balancing test** — do the controller/third-party interests override the data subject's interests, rights, and freedoms?

LIA is mandatory whenever Article 6(1)(f) is the lawful basis. Public authorities cannot rely on Article 6(1)(f) for processing in the performance of their tasks (Article 6(1) last sentence).

### LIA register reference

| Field | Value |
|-------|-------|
| LIA ID | [LIA-YYYY-NNN] |
| Date | [YYYY-MM-DD] |
| Status | [draft / approved / reviewed] |
| Owner | [process owner] |
| DPO reviewer | [name] |
| Linked ROPA entry | [ROPA-XXX] |
| Approval date | |
| Next review trigger | [event/date] |

---

## Step 1 — Purpose test

### 1.1 What is the legitimate interest?

[Plain-language description of the interest pursued by the controller or by a third party. Be specific.]

Examples of recognized legitimate interests (subject to balancing):

- Network and information security (Recital 49).
- Prevention of fraud (Recital 47).
- Direct marketing (subject to Article 21 right to object) (Recital 47).
- Reporting possible criminal acts to authorities (Recital 50).
- Internal administrative purposes within a group of undertakings (Recital 48).

Specific to this processing: [details].

### 1.2 Is the interest lawful, clearly articulated, and present (not speculative)?

| Question | Answer |
|----------|--------|
| Is the interest lawful (not contrary to law)? | |
| Is it specifically articulated? | |
| Is it real and present (not hypothetical)? | |

### 1.3 Whose interest?

| Field | Value |
|-------|-------|
| Controller's own interest | [describe] |
| Third party interest | [describe — who is the third party, what is their interest] |
| Public interest dimension | [if any] |

### 1.4 Benefits

| Beneficiary | Benefit | Magnitude |
|-------------|---------|-----------|
| Controller | | |
| Data subject | | |
| Third parties | | |
| Society | | |

### 1.5 Conclusion of purpose test

[Yes — proceed to necessity test / No — Article 6(1)(f) not available; choose another lawful basis or stop.]

---

## Step 2 — Necessity test

### 2.1 Is the processing necessary?

| Question | Answer |
|----------|--------|
| Does the processing actually achieve the legitimate interest? | |
| Could the interest be achieved without processing personal data? | |
| Could the interest be achieved with less personal data? | |
| Could the interest be achieved with less intrusive means? | |
| Could the interest be achieved with anonymous or aggregated data? | |
| Could the interest be achieved with pseudonymised data? | |

### 2.2 Alternatives considered

| Alternative | Why rejected |
|-------------|--------------|
| | |

### 2.3 Conclusion of necessity test

[Yes — proceed to balancing test / No — narrow scope or change basis.]

---

## Step 3 — Balancing test

### 3.1 Nature of data subject's interests, rights, and freedoms

| Aspect | Description |
|--------|-------------|
| Reasonable expectations | What would the data subject reasonably expect? |
| Relationship | Customer / employee / minor / vulnerable / non-customer? |
| Power asymmetry | Significant if employment, public services, or essential service |
| Past communications | What have we told the data subject? |

### 3.2 Nature of personal data

| Question | Yes/No, details |
|----------|-----------------|
| Is special category data involved (Article 9)? | |
| Is criminal data involved (Article 10)? | |
| Are children involved? | |
| Sensitive context (financial, health, location)? | |
| Identifiable directly or indirectly? | |
| Volume? | |

### 3.3 Way the data is processed

| Aspect | Description |
|--------|-------------|
| Public to private | |
| Aggregated to individualised | |
| Volume of recipients | |
| International transfers | |
| Combined with other data | |
| Retention period | |
| Profiling or automated decision-making | |

### 3.4 Possible impact on data subject

| Type of impact | Description |
|----------------|-------------|
| Loss of control over personal data | |
| Discrimination or exclusion | |
| Identity theft or fraud | |
| Financial loss | |
| Reputational damage | |
| Loss of confidentiality (special category, communications) | |
| Distress or anxiety | |
| Physical or psychological harm | |

### 3.5 Mitigating measures (these influence the balance)

| Measure | Description |
|---------|-------------|
| Transparency | [layered notice, just-in-time, plain language] |
| Granular control / opt-out | [mechanism] |
| Right to object enabled (Article 21) | [mechanism — must be at least as easy as the relevant action] |
| Data minimisation | [scope and details] |
| Pseudonymisation | [where feasible] |
| Encryption | [in transit, at rest] |
| Access control | [RBAC, MFA] |
| Retention limited | [specific period and rationale] |
| Aggregation / anonymisation downstream | [for analytics] |
| Sensitive context handling | [special procedures] |

### 3.6 Balancing conclusion

| Field | Value |
|-------|-------|
| Without mitigations, is balance in favor of legitimate interest? | [Y/N] |
| With mitigations, is balance in favor of legitimate interest? | [Y/N — required to proceed] |
| Reasoning | [text] |

If the balancing tilts against the controller's interest even after mitigations, Article 6(1)(f) is **not** available. Choose another basis or stop.

---

## Step 4 — Documentation and operationalisation

### 4.1 Article 13/14 transparency

The legitimate interest and its description must be communicated in the privacy notice (Article 13(1)(d), 14(2)(b)). The notice should reference the LIA and offer the right to object (Article 21).

### 4.2 Direct marketing carve-out (Article 21(2))

For direct marketing, the right to object is absolute — no balancing applies once the data subject objects. The LIA still supports the *initial* processing but cannot resist objections.

### 4.3 Linkage with DPIA

If the processing is high-risk (Article 35), the LIA is integrated into or attached to the DPIA. The two documents reference each other.

### 4.4 Children

Special care for children (Recital 38). Where processing relates to children, expectations are stronger and balance often tips against the controller without strong protective mitigations.

### 4.5 Review cadence

LIA reviewed:

- On material change to processing.
- On regulatory change (e.g. EDPB 02/2024 on direct marketing).
- On change of mitigations.
- Otherwise at least annually.

---

## Section 5 — Approval

| Field | Value |
|-------|-------|
| Process owner | [name, date, signature] |
| DPO opinion (advisory) | [concur / concur with conditions / disagree] |
| Accountable executive | [name, date, signature] |

---

## Common LIA examples

The following examples illustrate typical LIA outcomes; do not copy without performing your own analysis.

| Processing | Outcome |
|-----------|---------|
| IT security logging of admin access | Often legitimate; high necessity; low impact with proper safeguards |
| Fraud detection on payment data | Often legitimate; necessary; mitigated by minimisation, retention limits |
| Direct marketing to existing customers | Possible under 6(1)(f) plus right to object (Article 21); ePrivacy may require consent |
| Analytics with pseudonymisation | Often legitimate if mitigations strong; aggregate where possible |
| Sharing data with group company for HR | Possible (Recital 48), with internal safeguards and transparency |
| Behavioral advertising | Not generally accepted under 6(1)(f) post Meta DPC binding decisions; consent typically required |
| Tracking via cookies | ePrivacy requires consent; LIA cannot substitute |
| Combining datasets without consent | Higher risk; case-by-case |
| Processing children's data for profiling | Strongly disfavored without consent and protective measures |

### Anti-patterns

- Conclusory LIA stating "we have legitimate interest in X, balance in our favor" without analysis.
- Skipping necessity test.
- Treating data subject expectations as identical to terms-of-service language.
- Ignoring children's heightened protection.
- Using LIA to override mandatory consent (e.g. cookies, ePrivacy).
- Not refreshing LIA after material change.

---

## Türkçe

# Meşru Menfaat Değerlendirmesi (MMD)

MMD, veri sorumlusunun GDPR Madde 6(1)(f)'ye dayanmasını belgeler — kişisel verilerin korunmasını gerektiren ilgili kişinin menfaatleri veya temel hakları ve özgürlükleri tarafından geçersiz kılınmadığı sürece, özellikle ilgili kişi bir çocuk olduğunda, veri sorumlusu veya bir üçüncü taraf tarafından izlenen meşru menfaatler.

Bu şablon, WP217'de geliştirilen ve EDPB ile SA'lar tarafından tutarlı olarak onaylanan **üç adımlı testi** izler:

1. **Amaç testi** — meşru bir menfaat var mı?
2. **Gereklilik testi** — işleme bu menfaat için gerekli mi?
3. **Dengeleme testi** — veri sorumlusu/üçüncü taraf menfaatleri ilgili kişinin menfaatlerini, haklarını ve özgürlüklerini geçersiz kılıyor mu?

MMD, Madde 6(1)(f) hukuki dayanak olduğunda her zaman zorunludur. Kamu otoriteleri görevlerinin yerine getirilmesinde işleme için Madde 6(1)(f)'ye dayanamaz (Madde 6(1) son cümle).

### MMD kayıt defteri referansı

| Alan | Değer |
|------|-------|
| MMD ID | [MMD-YYYY-NNN] |
| Tarih | [YYYY-AA-GG] |
| Durum | [taslak / onaylandı / gözden geçirildi] |
| Sahip | [süreç sahibi] |
| DPO inceleyici | [ad] |
| Bağlı ROPA girdisi | [ROPA-XXX] |
| Onay tarihi | |
| Sonraki gözden geçirme tetikleyicisi | [olay/tarih] |

---

## Adım 1 — Amaç testi

### 1.1 Meşru menfaat nedir?

[Veri sorumlusu veya bir üçüncü taraf tarafından izlenen menfaatin sade dil açıklaması. Belirli olun.]

Tanınmış meşru menfaat örnekleri (dengelemeye tabi):

- Ağ ve bilgi güvenliği (Gerekçe 49).
- Dolandırıcılığın önlenmesi (Gerekçe 47).
- Doğrudan pazarlama (Madde 21 itiraz hakkına tabi) (Gerekçe 47).
- Otoritelere olası suç eylemlerinin raporlanması (Gerekçe 50).
- Bir teşebbüs grubu içinde iç idari amaçlar (Gerekçe 48).

Bu işlemeye özgü: [ayrıntılar].

### 1.2 Menfaat hukuka uygun, açıkça ifade edilmiş ve mevcut (spekülatif değil) mi?

| Soru | Yanıt |
|------|-------|
| Menfaat hukuka uygun mu (hukuka aykırı değil)? | |
| Açıkça ifade edilmiş mi? | |
| Gerçek ve mevcut mü (varsayımsal değil)? | |

### 1.3 Kimin menfaati?

| Alan | Değer |
|------|-------|
| Veri sorumlusunun kendi menfaati | [tanımla] |
| Üçüncü taraf menfaati | [tanımla — üçüncü taraf kim, menfaatleri ne] |
| Kamu yararı boyutu | [varsa] |

### 1.4 Faydalar

| Yararlanıcı | Fayda | Büyüklük |
|-------------|-------|----------|
| Veri sorumlusu | | |
| İlgili kişi | | |
| Üçüncü taraflar | | |
| Toplum | | |

### 1.5 Amaç testi sonucu

[Evet — gereklilik testine geç / Hayır — Madde 6(1)(f) mevcut değil; başka hukuki dayanak seç veya dur.]

---

## Adım 2 — Gereklilik testi

### 2.1 İşleme gerekli mi?

| Soru | Yanıt |
|------|-------|
| İşleme gerçekten meşru menfaati gerçekleştiriyor mu? | |
| Menfaat kişisel veri işlemeden gerçekleştirilebilir mi? | |
| Menfaat daha az kişisel veriyle gerçekleştirilebilir mi? | |
| Menfaat daha az müdahaleci araçlarla gerçekleştirilebilir mi? | |
| Menfaat anonim veya toplu veriyle gerçekleştirilebilir mi? | |
| Menfaat takma adlaştırılmış veriyle gerçekleştirilebilir mi? | |

### 2.2 Değerlendirilen alternatifler

| Alternatif | Neden reddedildi |
|------------|-------------------|
| | |

### 2.3 Gereklilik testi sonucu

[Evet — dengeleme testine geç / Hayır — kapsamı daralt veya dayanağı değiştir.]

---

## Adım 3 — Dengeleme testi

### 3.1 İlgili kişinin menfaatleri, hakları ve özgürlüklerinin niteliği

| Husus | Açıklama |
|-------|----------|
| Makul beklentiler | İlgili kişi makul olarak ne bekler? |
| İlişki | Müşteri / çalışan / küçük / savunmasız / müşteri olmayan? |
| Güç asimetrisi | İstihdam, kamu hizmetleri veya temel hizmet ise önemli |
| Geçmiş iletişimler | İlgili kişiye ne söyledik? |

### 3.2 Kişisel verinin niteliği

| Soru | Evet/Hayır, ayrıntı |
|------|---------------------|
| Özel kategori veri dahil mi (Madde 9)? | |
| Ceza verisi dahil mi (Madde 10)? | |
| Çocuklar dahil mi? | |
| Hassas bağlam (finansal, sağlık, konum)? | |
| Doğrudan veya dolaylı olarak tanımlanabilir? | |
| Hacim? | |

### 3.3 Verinin işlenme şekli

| Husus | Açıklama |
|-------|----------|
| Kamudan özele | |
| Toplu olarak bireyselleştirilmiş | |
| Alıcı hacmi | |
| Uluslararası aktarımlar | |
| Diğer verilerle birleştirilmiş | |
| Saklama süresi | |
| Profil oluşturma veya otomatik karar verme | |

### 3.4 İlgili kişiye olası etki

| Etki türü | Açıklama |
|-----------|----------|
| Kişisel veri üzerinde kontrol kaybı | |
| Ayrımcılık veya dışlama | |
| Kimlik hırsızlığı veya dolandırıcılık | |
| Finansal kayıp | |
| İtibar zararı | |
| Gizlilik kaybı (özel kategori, iletişimler) | |
| Sıkıntı veya kaygı | |
| Fiziksel veya psikolojik zarar | |

### 3.5 Azaltıcı tedbirler (bunlar dengeyi etkiler)

| Tedbir | Açıklama |
|--------|----------|
| Şeffaflık | [katmanlı metin, tam zamanında, sade dil] |
| Ayrıntılı kontrol / opt-out | [mekanizma] |
| İtiraz hakkı etkin (Madde 21) | [mekanizma — ilgili eylem kadar kolay olmalı] |
| Veri minimizasyonu | [kapsam ve ayrıntılar] |
| Takma adlaştırma | [mümkün olduğunda] |
| Şifreleme | [aktarımda, depolamada] |
| Erişim kontrolü | [RBAC, ÇFD] |
| Sınırlı saklama | [belirli süre ve gerekçe] |
| Aşağı akışta toplama / anonimleştirme | [analitik için] |
| Hassas bağlam ele alma | [özel prosedürler] |

### 3.6 Dengeleme sonucu

| Alan | Değer |
|------|-------|
| Azaltmalar olmadan, denge meşru menfaat lehine mi? | [E/H] |
| Azaltmalarla, denge meşru menfaat lehine mi? | [E/H — devam etmek için gerekli] |
| Gerekçe | [metin] |

Azaltmalardan sonra bile denge veri sorumlusunun menfaati aleyhine eğilirse, Madde 6(1)(f) mevcut **değildir**. Başka bir dayanak seçin veya durun.

---

## Adım 4 — Belgeleme ve operasyonelleştirme

### 4.1 Madde 13/14 şeffaflık

Meşru menfaat ve açıklaması aydınlatma metninde iletilmelidir (Madde 13(1)(d), 14(2)(b)). Metin MMD'ye atıfta bulunmalı ve itiraz hakkını sunmalıdır (Madde 21).

### 4.2 Doğrudan pazarlama istisnası (Madde 21(2))

Doğrudan pazarlama için itiraz hakkı mutlaktır — ilgili kişi itiraz ettiğinde dengeleme uygulanmaz. MMD hâlâ *ilk* işlemeyi destekler ancak itirazlara direnmez.

### 4.3 VKDM ile bağlantı

İşleme yüksek riskli ise (Madde 35), MMD VKDM'ye entegre edilir veya eklenir. İki belge birbirine atıfta bulunur.

### 4.4 Çocuklar

Çocuklar için özel özen (Gerekçe 38). İşleme çocuklarla ilgili olduğunda, beklentiler daha güçlüdür ve denge güçlü koruyucu azaltmalar olmadan genellikle veri sorumlusu aleyhine eğilir.

### 4.5 Gözden geçirme sıklığı

MMD şu durumlarda gözden geçirilir:

- İşlemeye maddi değişiklikte.
- Düzenleyici değişiklikte (örn. doğrudan pazarlama üzerine EDPB 02/2024).
- Azaltmaların değişmesinde.
- Aksi takdirde en az yıllık.

---

## Bölüm 5 — Onay

| Alan | Değer |
|------|-------|
| Süreç sahibi | [ad, tarih, imza] |
| DPO görüşü (danışmanlık) | [katılır / koşullarla katılır / katılmaz] |
| Sorumlu yönetici | [ad, tarih, imza] |

---

## Yaygın MMD örnekleri

Aşağıdaki örnekler tipik MMD sonuçlarını gösterir; kendi analizinizi yapmadan kopyalamayın.

| İşleme | Sonuç |
|--------|-------|
| Yönetici erişiminin BT güvenlik günlüğü | Sıklıkla meşru; yüksek gereklilik; uygun güvencelerle düşük etki |
| Ödeme verisinde dolandırıcılık tespiti | Sıklıkla meşru; gerekli; minimizasyon, saklama sınırlarıyla azaltılmış |
| Mevcut müşterilere doğrudan pazarlama | İtiraz hakkı (Madde 21) artı 6(1)(f) altında mümkün; ePrivacy rıza gerektirebilir |
| Takma adlaştırma ile analitik | Azaltmalar güçlüyse sıklıkla meşru; mümkün olduğunda toplu |
| İK için grup şirketiyle veri paylaşımı | İç güvenceler ve şeffaflıkla mümkün (Gerekçe 48) |
| Davranışsal reklamcılık | Meta DPC bağlayıcı kararları sonrası 6(1)(f) altında genellikle kabul edilmez; tipik olarak rıza gerekir |
| Çerezler yoluyla izleme | ePrivacy rıza gerektirir; MMD yerini alamaz |
| Rıza olmadan veri kümelerini birleştirme | Daha yüksek risk; vaka bazında |
| Profil oluşturma için çocuk verisi işleme | Rıza ve koruyucu tedbirler olmadan güçlü şekilde önerilmez |

### Anti-desenler

- Analiz olmadan "X üzerinde meşru menfaatimiz var, denge lehimize" diyen sonuç çıkaran MMD.
- Gereklilik testini atlama.
- İlgili kişi beklentilerini hizmet şartları diliyle özdeş kabul etme.
- Çocukların yüksek korumasını göz ardı etme.
- Zorunlu rızayı geçersiz kılmak için MMD kullanma (örn. çerezler, ePrivacy).
- Maddi değişiklikten sonra MMD'yi tazelememe.
