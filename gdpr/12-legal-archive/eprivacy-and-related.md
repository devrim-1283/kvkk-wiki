---
title:
  en: "ePrivacy and Related EU Instruments — Interplay with GDPR"
  tr: "ePrivacy ve Ilgili AB Araclari — GDPR ile Etkilesim"
section: "12-legal-archive"
owner: "Legal / DPO"
version: "1.0"
last_review: "2026-05-08"
next_review: "2026-11-08"
classification: "Internal"
languages: ["en", "tr"]
keywords:
  en: ["ePrivacy", "NIS2", "DSA", "DMA", "Data Act", "DGA", "AI Act"]
  tr: ["ePrivacy", "NIS2", "DSA", "DMA", "Data Act", "DGA", "AI Act"]
---

## English

# ePrivacy and Related EU Instruments — Interplay with GDPR

GDPR sits at the centre of an increasingly dense EU digital regulatory ecosystem. This reference summarises the core sister instruments and how they interact with GDPR.

### Hierarchy and lex specialis

GDPR is the lex generalis for personal data. Other instruments may operate as lex specialis where they regulate the same matter. Article 95 GDPR explicitly preserves ePrivacy obligations as lex specialis for matters within ePrivacy scope (e.g. confidentiality of communications, cookies). Recital 173 confirms.

### ePrivacy Directive 2002/58/EC (as amended by 2009/136/EC)

#### Scope

- Confidentiality of electronic communications.
- Processing of traffic and location data.
- Unsolicited communications (Article 13).
- Cookies and similar technologies (Article 5(3)) — consent required for storage of and access to information on terminal equipment, with limited exceptions ("strictly necessary" for the service requested by the user).

#### GDPR interplay

- For Article 5(3) cookie processing, ePrivacy mandates consent. The standard of consent is the GDPR consent standard (Article 4(11), 7) per Planet49 (C-673/17) and EDPB Guidelines 05/2020.
- Where processing involves personal data, GDPR overlays — providing legal basis, transparency, rights.
- Direct marketing under Article 13 ePrivacy: opt-in for natural persons by default; soft opt-in for existing customers under conditions; legal persons may have different treatment by member state.

#### National transposition

Each member state has transposed ePrivacy. Examples:

| MS | Law |
|----|-----|
| Germany | TTDSG 2021 |
| France | Code des postes et des communications électroniques + LIL Art. 82 |
| Italy | Codice delle comunicazioni elettroniche |
| Spain | LSSI-CE |
| UK (post-Brexit) | PECR 2003 |

### ePrivacy Regulation — proposal status

The ePrivacy Regulation (proposed 2017) has been negotiated for years. As of mid-2025 the file remains under inter-institutional negotiation. If adopted, it will:

- Replace the Directive with directly applicable rules.
- Extend scope to over-the-top (OTT) communication services (e.g. messengers).
- Strengthen rules on metadata and tracking technologies.
- Update consent and machine-readable signal mechanisms.

Until adoption, the 2002/58/EC framework remains in force.

### NIS2 Directive (EU) 2022/2555

#### Scope

NIS2 imposes cybersecurity obligations on operators of essential and important services across many sectors (energy, transport, finance, healthcare, digital infrastructure, manufacturing, public administration, postal, food, chemicals, research, providers of digital services, etc.). Member states transposed by October 2024.

#### GDPR interplay

- Article 32 GDPR (security of processing) and NIS2 cybersecurity obligations are complementary; many controls overlap.
- NIS2 has separate incident reporting timeline (24h early warning, 72h notification, 1-month final report) running in parallel to GDPR Article 33's 72h personal data breach clock when the incident affects personal data.
- Same incident may trigger reporting to both the SA (GDPR) and the competent NIS2 authority/CSIRT.
- Coordinate to avoid contradictory submissions; align on risk classification.

### Digital Services Act — Regulation (EU) 2022/2065

#### Scope

DSA regulates intermediary services (mere conduit, caching, hosting) and online platforms with tiered obligations escalating to Very Large Online Platforms (VLOPs) and search engines (VLOSEs).

#### GDPR interplay

- DSA Articles 26-28 prohibit dark patterns, advertising profiling targeting minors, and special category-based ads. These align with EDPB Guidelines 03/2022.
- DSA transparency database for content moderation does not relax GDPR obligations.
- DSA risk assessments for VLOPs include systemic risks to fundamental rights including data protection.
- Article 27 transparency on recommender systems.
- DSA enforcement primarily by Commission for VLOPs/VLOSEs; Digital Services Coordinators in member states for others.

### Digital Markets Act — Regulation (EU) 2022/1925

#### Scope

DMA regulates designated "gatekeepers" of core platform services (CPS) — operating systems, search, social networking, messaging, video sharing, intermediation, advertising.

#### GDPR interplay

- Article 5(2) DMA prohibits cross-service personal data combination by gatekeepers without specific consent (separate from GDPR Article 6 basis).
- Article 6(9) and (10) DMA on data portability and access rights complement GDPR Article 20.
- Interoperability obligations for messaging may have privacy design implications.
- DMA enforcement primarily by Commission.

### Data Act — Regulation (EU) 2023/2854

#### Scope

Data Act regulates access to and use of data generated by IoT and connected products and related services. Effective from September 2025.

#### GDPR interplay

- Where data is personal, GDPR fully applies.
- Data Act distinguishes user (data holder) and third party requests; access mechanisms must respect GDPR.
- Article 4(12) Data Act requires data holder to make personal data available where applicable rights of data subjects align.
- B2B / B2G data sharing under Data Act must respect GDPR principles.

### Data Governance Act — Regulation (EU) 2022/868

#### Scope

DGA promotes voluntary data sharing through three mechanisms: re-use of public sector protected data, data intermediation services, data altruism.

#### GDPR interplay

- Public sector data re-use under DGA (Articles 5-9) — must reconcile with GDPR for personal data; technical and organizational measures often required (anonymisation, pseudonymisation, secure processing environment).
- Data altruism organisations under DGA Article 17 must comply with GDPR for personal data they handle.
- Data intermediation services under DGA Articles 10-13 are typically Article 28 processors when processing personal data on behalf of users.

### AI Act — Regulation (EU) 2024/1689

#### Scope

The AI Act establishes a risk-based regulatory framework: prohibited AI, high-risk AI, limited-risk AI, minimal-risk AI; specific rules for general-purpose AI models. Phased application 2025-2027.

#### GDPR interplay

- AI Act and GDPR coexist; both apply to AI systems processing personal data.
- High-risk AI obligations include data governance (Article 10) — quality of training, validation, and testing data sets, free of biases, with respect to GDPR.
- Article 26 AI Act for deployers includes maintaining logs, fundamental rights impact assessment for some categories — interacts with GDPR Article 35 DPIA.
- Article 22 GDPR on automated individual decision-making applies to AI systems making decisions with legal/similar effects.
- Prohibited AI under Article 5 AI Act includes social scoring by public authorities, certain real-time biometric identification — overlaps with GDPR Article 9 special category data.
- General-purpose AI (e.g. foundation models) faces obligations on training data documentation, copyright compliance, and transparency.

### Open Data Directive (EU) 2019/1024

- Public sector documents made available for re-use.
- Personal data carve-outs respect GDPR.

### Whistleblower Directive (EU) 2019/1937

- Internal reporting channels for breaches of EU law.
- Personal data of whistleblowers and subjects requires GDPR-compliant processing.
- Identity confidentiality is critical.

### Coordination and consistency

#### Multi-instrument incident scenario

A cybersecurity incident affecting personal data of customers of a regulated bank (NIS2 essential entity, GDPR controller, DORA financial entity) may trigger:

- GDPR Article 33 — 72h SA notification.
- NIS2 — 24h early warning and 72h notification to competent authority/CSIRT.
- DORA Regulation (EU) 2022/2554 — financial entity ICT incident reporting.
- Possibly DSA — if entity is online platform.
- National sectoral regulators in addition.

A single internal trigger should fan out to a coordinated set of notifications, not parallel uncoordinated ones.

#### Multi-instrument processing scenario

A VLOP using profiling for advertising must address:

- GDPR Article 5, 6, 9, 13, 22.
- ePrivacy Article 5(3) for cookies.
- DSA Articles 26-28 for advertising and dark patterns.
- DMA Article 5(2) if gatekeeper, on cross-service data combination.
- AI Act if recommender involves regulated AI risk class.

### Maintenance

This reference is reviewed quarterly. Updates triggered by entry into force, delegated/implementing acts, or Commission/EDPB joint guidance.

---

## Türkçe

# ePrivacy ve İlgili AB Araçları — GDPR ile Etkileşim

GDPR, giderek yoğunlaşan bir AB dijital düzenleyici ekosisteminin merkezindedir. Bu referans, çekirdek kardeş araçları ve GDPR ile nasıl etkileştiklerini özetler.

### Hiyerarşi ve lex specialis

GDPR, kişisel veri için lex generalis'tir. Diğer araçlar, aynı konuyu düzenlediklerinde lex specialis olarak çalışabilir. GDPR Madde 95, ePrivacy yükümlülüklerini ePrivacy kapsamı içindeki konular için (örn. iletişimlerin gizliliği, çerezler) lex specialis olarak açıkça korur. Gerekçe 173 teyit eder.

### ePrivacy Direktifi 2002/58/EC (2009/136/EC ile değiştirilmiş)

#### Kapsam

- Elektronik iletişimlerin gizliliği.
- Trafik ve konum verisi işleme.
- İstenmeyen iletişimler (Madde 13).
- Çerezler ve benzer teknolojiler (Madde 5(3)) — sınırlı istisnalarla terminal ekipmanındaki bilgilerin depolanması ve erişimi için rıza gerekir (kullanıcı tarafından talep edilen hizmet için "kesinlikle gerekli").

#### GDPR etkileşimi

- Madde 5(3) çerez işleme için ePrivacy rızayı zorunlu kılar. Rıza standardı, Planet49 (C-673/17) ve EDPB Kılavuzu 05/2020 uyarınca GDPR rıza standardıdır (Madde 4(11), 7).
- İşleme kişisel veri içerdiğinde, GDPR örtüşür — hukuki dayanak, şeffaflık, haklar sağlar.
- ePrivacy Madde 13 doğrudan pazarlama: gerçek kişiler için varsayılan olarak opt-in; mevcut müşteriler için koşullarla yumuşak opt-in; tüzel kişiler üye devlete göre farklı muamele görebilir.

#### Ulusal aktarım

Her üye devlet ePrivacy'yi aktarmıştır. Örnekler:

| ÜD | Yasa |
|----|------|
| Almanya | TTDSG 2021 |
| Fransa | Code des postes et des communications électroniques + LIL Md. 82 |
| İtalya | Codice delle comunicazioni elettroniche |
| İspanya | LSSI-CE |
| UK (Brexit sonrası) | PECR 2003 |

### ePrivacy Tüzüğü — teklif durumu

ePrivacy Tüzüğü (2017'de teklif edildi) yıllardır müzakere edilmiştir. 2025 ortası itibarıyla dosya kurumlar arası müzakere altında kalır. Kabul edilirse:

- Direktifi doğrudan uygulanabilir kurallarla değiştirecek.
- Kapsamı over-the-top (OTT) iletişim hizmetlerine (örn. mesajlaşma uygulamaları) genişletecek.
- Meta veri ve izleme teknolojileri kurallarını güçlendirecek.
- Rıza ve makine okunabilir sinyal mekanizmalarını güncelleyecek.

Kabule kadar 2002/58/EC çerçevesi yürürlükte kalır.

### NIS2 Direktifi (AB) 2022/2555

#### Kapsam

NIS2, birçok sektörde (enerji, ulaşım, finans, sağlık, dijital altyapı, üretim, kamu yönetimi, posta, gıda, kimyasallar, araştırma, dijital hizmet sağlayıcıları vb.) temel ve önemli hizmet operatörlerine siber güvenlik yükümlülükleri getirir. Üye devletler Ekim 2024'e kadar aktardı.

#### GDPR etkileşimi

- GDPR Madde 32 (işleme güvenliği) ve NIS2 siber güvenlik yükümlülükleri tamamlayıcıdır; birçok kontrol örtüşür.
- NIS2'nin GDPR Madde 33'ün 72 saatlik kişisel veri ihlali sayacına paralel çalışan ayrı olay raporlama zaman çizelgesi (24s erken uyarı, 72s bildirim, 1 ay nihai rapor) vardır; olay kişisel veriyi etkilediğinde.
- Aynı olay hem SA'ya (GDPR) hem de yetkili NIS2 otoritesine/CSIRT'e raporlamayı tetikleyebilir.
- Çelişkili sunumları önlemek için koordine olun; risk sınıflandırmasında hizalanın.

### Dijital Hizmetler Yasası — Tüzük (AB) 2022/2065

#### Kapsam

DSA, aracı hizmetleri (sadece iletim, önbellekleme, barındırma) ve çok büyük çevrimiçi platformlara (VLOP'lar) ve arama motorlarına (VLOSE'ler) tırmanan kademeli yükümlülüklerle çevrimiçi platformları düzenler.

#### GDPR etkileşimi

- DSA Madde 26-28, karanlık desenleri, küçükleri hedefleyen reklam profilini ve özel kategori temelli reklamları yasaklar. Bunlar EDPB Kılavuzu 03/2022 ile uyumludur.
- İçerik moderasyonu için DSA şeffaflık veritabanı GDPR yükümlülüklerini gevşetmez.
- VLOP'lar için DSA risk değerlendirmeleri, veri koruma dahil temel haklara sistemik riskleri içerir.
- Madde 27 öneri sistemleri üzerine şeffaflık.
- DSA yaptırım esas olarak VLOP/VLOSE'lar için Komisyon tarafından; üye devletlerdeki Dijital Hizmet Koordinatörleri diğerleri için.

### Dijital Pazarlar Yasası — Tüzük (AB) 2022/1925

#### Kapsam

DMA, çekirdek platform hizmetlerinin (CPS) atanmış "kapı bekçileri"ni düzenler — işletim sistemleri, arama, sosyal ağ, mesajlaşma, video paylaşımı, aracılık, reklam.

#### GDPR etkileşimi

- DMA Madde 5(2), kapı bekçileri tarafından belirli rıza olmadan hizmetler arası kişisel veri kombinasyonunu yasaklar (GDPR Madde 6 dayanağından ayrı).
- DMA Madde 6(9) ve (10), veri taşınabilirliği ve erişim hakları üzerine GDPR Madde 20'yi tamamlar.
- Mesajlaşma için birlikte çalışabilirlik yükümlülüklerinin gizlilik tasarım etkileri olabilir.
- DMA yaptırımı esas olarak Komisyon tarafından.

### Veri Yasası — Tüzük (AB) 2023/2854

#### Kapsam

Veri Yasası, IoT ve bağlı ürünler ve ilgili hizmetler tarafından üretilen verilere erişim ve kullanımı düzenler. Eylül 2025'ten itibaren etkili.

#### GDPR etkileşimi

- Veri kişisel olduğunda, GDPR tam olarak uygulanır.
- Veri Yasası kullanıcı (veri sahibi) ve üçüncü taraf taleplerini ayırır; erişim mekanizmaları GDPR'a saygı göstermelidir.
- Madde 4(12) Veri Yasası, ilgili kişi haklarının uygulandığı yerlerde veri sahibinin kişisel veriyi kullanılabilir hale getirmesini gerektirir.
- Veri Yasası altındaki B2B / B2G veri paylaşımı GDPR ilkelerine saygı göstermelidir.

### Veri Yönetişimi Yasası — Tüzük (AB) 2022/868

#### Kapsam

DGA, üç mekanizma yoluyla gönüllü veri paylaşımını teşvik eder: kamu sektörü korumalı verisinin yeniden kullanımı, veri aracılık hizmetleri, veri özgecilik.

#### GDPR etkileşimi

- DGA altında kamu sektörü veri yeniden kullanımı (Madde 5-9) — kişisel veri için GDPR ile uzlaştırılmalıdır; teknik ve idari tedbirler genellikle gereklidir (anonimleştirme, takma adlaştırma, güvenli işleme ortamı).
- DGA Madde 17 altında veri özgecilik kuruluşları, ele aldıkları kişisel veri için GDPR'a uymalıdır.
- DGA Madde 10-13 altında veri aracılık hizmetleri, kullanıcılar adına kişisel veri işlerken tipik olarak Madde 28 işleyenleridir.

### AI Yasası — Tüzük (AB) 2024/1689

#### Kapsam

AI Yasası risk bazlı bir düzenleyici çerçeve oluşturur: yasaklanmış AI, yüksek riskli AI, sınırlı riskli AI, minimal riskli AI; genel amaçlı AI modelleri için belirli kurallar. 2025-2027 aşamalı uygulama.

#### GDPR etkileşimi

- AI Yasası ve GDPR birlikte var olur; her ikisi de kişisel veri işleyen AI sistemlerine uygulanır.
- Yüksek riskli AI yükümlülükleri veri yönetişimini içerir (Madde 10) — eğitim, doğrulama ve test veri kümelerinin kalitesi, GDPR'a saygı ile yanlılıklardan arındırılmış.
- Dağıtıcılar için Madde 26 AI Yasası, bazı kategoriler için günlük tutma, temel haklar etki değerlendirmesini içerir — GDPR Madde 35 VKDM ile etkileşir.
- Otomatik bireysel karar verme üzerine GDPR Madde 22, hukuki/benzer etkili kararlar veren AI sistemlerine uygulanır.
- AI Yasası Madde 5 altında yasaklanan AI, kamu otoriteleri tarafından sosyal puanlama, belirli gerçek zamanlı biyometrik tanımlamayı içerir — GDPR Madde 9 özel kategori veriyle örtüşür.
- Genel amaçlı AI (örn. temel modeller), eğitim verisi belgelemesi, telif uyumu ve şeffaflık üzerine yükümlülüklerle karşılaşır.

### Açık Veri Direktifi (AB) 2019/1024

- Yeniden kullanım için kullanılabilir kamu sektörü belgeleri.
- Kişisel veri istisnaları GDPR'a saygı gösterir.

### Muhbir Direktifi (AB) 2019/1937

- AB hukuku ihlalleri için iç raporlama kanalları.
- Muhbirlerin ve konuların kişisel verisi GDPR uyumlu işleme gerektirir.
- Kimlik gizliliği kritiktir.

### Koordinasyon ve tutarlılık

#### Çoklu araç olay senaryosu

Düzenlenmiş bir bankanın (NIS2 temel kuruluş, GDPR veri sorumlusu, DORA finansal kuruluş) müşterilerinin kişisel verilerini etkileyen bir siber güvenlik olayı şunları tetikleyebilir:

- GDPR Madde 33 — 72s SA bildirimi.
- NIS2 — 24s erken uyarı ve yetkili otorite/CSIRT'e 72s bildirim.
- DORA Tüzüğü (AB) 2022/2554 — finansal kuruluş BİT olay raporlaması.
- Muhtemelen DSA — kuruluş çevrimiçi platformsa.
- Ayrıca ulusal sektörel düzenleyiciler.

Tek bir iç tetikleyici, paralel koordine edilmemiş bildirimler değil, koordineli bir bildirim setine yayılmalıdır.

#### Çoklu araç işleme senaryosu

Reklamcılık için profil oluşturma kullanan bir VLOP şunları ele almalıdır:

- GDPR Madde 5, 6, 9, 13, 22.
- Çerezler için ePrivacy Madde 5(3).
- Reklam ve karanlık desenler için DSA Madde 26-28.
- Hizmetler arası veri kombinasyonu üzerine, kapı bekçisiyse DMA Madde 5(2).
- Öneri düzenlenmiş AI risk sınıfı içeriyorsa AI Yasası.

### Bakım

Bu referans çeyreklik gözden geçirilir. Yürürlüğe girme, yetki devri/uygulama yasaları veya Komisyon/EDPB ortak rehberliği ile tetiklenen güncellemeler.
