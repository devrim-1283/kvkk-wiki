---
Document / Doküman: Core Concepts — Section Introduction & File Index / Temel Kavramlar — Bölüm Girişi ve Dosya Dizini
Section / Bölüm: 01-core-concepts
Owner / Sahip: Data Protection Officer (DPO) / Veri Koruma Görevlisi
Approved by / Onaylayan: Privacy / Data Governance Committee / Gizlilik / Veri Yönetişim Komitesi
Version / Versiyon: 1.0
Effective / Yürürlük: 2026-05-08
Review / Gözden Geçirme: Annual + triggered / Yıllık + tetiklenmiş
Legal Reference / İlgili Mevzuat: GDPR Art. 4, 5, 6, 9, 10, 12–22, 24–28
---

## English

### 1. Purpose

This section establishes the GDPR vocabulary and conceptual baseline that every other section depends on. Without shared and precise definitions of "personal data," "controller," "processor," "consent," "lawful basis," "data subject rights," and "special categories," the rest of the program is built on sand.

The core-concepts documents are written for two audiences:

- Operational teams (HR, IT, Marketing, Procurement, Engineering, Customer Support) who need to translate legal text into day-to-day decisions.
- Legal, DPO, and Audit teams who require defensible interpretation backed by Articles, Recitals, EDPB Guidelines, and ECJ case-law.

### 2. Why Definitions Matter

Mis-classification cascades. Treating personal data as anonymous data, treating special categories as ordinary personal data, mis-identifying a processor as a controller, or relying on the wrong lawful basis are the most common root causes of:

- Article 83 fines (up to €20 million or 4% of global annual turnover, whichever is higher).
- Data subject claims for material and non-material damage under Article 82.
- Adverse rulings from the Court of Justice of the European Union (ECJ).
- Regulator-mandated cessation of processing.

Investing in precise definitions and applying them consistently across the enterprise is the cheapest control available.

### 3. File Index

| # | File | Purpose | Primary GDPR Articles |
|---|---|---|---|
| 1 | `README.md` | Section introduction and file index. | Art. 4, 5, 6 |
| 2 | `definitions.md` | 30+ key terms from Article 4, plus operational definitions. | Art. 4 |
| 3 | `personal-vs-special-categories.md` | Article 9 special categories and Article 10 criminal data. | Art. 9, 10 |
| 4 | `controller-vs-processor.md` | Articles 24–28, joint controllers (Art. 26), processor contracts (Art. 28). | Art. 24, 26, 28 |
| 5 | `data-subject-rights.md` | Articles 12–22 — transparency, access, rectification, erasure, restriction, portability, object, ADM. | Art. 12–22 |
| 6 | `lawful-bases.md` | Article 5 principles + Article 6 lawful bases, LIA template, balancing test. | Art. 5, 6, 7 |

### 4. How to Use This Section

1. Read `definitions.md` first; it is the dictionary used by every other document.
2. Use `personal-vs-special-categories.md` to classify data sets in ROPA and DPIAs.
3. Use `controller-vs-processor.md` whenever a new third-party arrangement is contemplated.
4. Use `lawful-bases.md` as the entry gate for any new processing — no processing exists in this organization without a documented lawful basis.
5. Use `data-subject-rights.md` to operate the rights-handling workflows.

### 5. Authoritative Sources

| Source | Use |
|---|---|
| Regulation (EU) 2016/679 (GDPR) — full text | Primary source. |
| EDPB Guidelines (latest versions) | Authoritative interpretation. |
| EDPS opinions | Public-sector and EU institution context. |
| ECJ judgments (Costeja C-131/12; Bara C-201/14; Schrems II C-311/18; Planet49 C-673/17; Fashion ID C-40/17; Meta Platforms C-252/21) | Binding interpretation of GDPR concepts. |
| Member State law (e.g., German BDSG, French Loi Informatique et Libertés) | Implementation detail and stricter rules where applicable. |
| ISO 27701, ISO 29134 | Privacy controls and DPIA methodology. |

### 6. Maintenance

- Owner: DPO.
- Review cycle: annual and on any of the following triggers:
  - New EDPB guideline materially affecting interpretation.
  - ECJ judgment affecting GDPR concepts in scope.
  - Member State law amendment.
  - Internal incident or audit finding indicating misinterpretation.

### 7. Glossary Discipline

To keep definitions consistent:

- A central glossary file (`definitions.md`) is the single source of truth.
- Other documents must use the same terms verbatim where possible and link back to the glossary on first use.
- Translations must be reviewed by a qualified data protection translator; "controller" → "veri sorumlusu", "processor" → "veri işleyen", "data subject" → "ilgili kişi", "personal data" → "kişisel veri", "special categories" → "özel nitelikli kişisel veri kategorileri", "consent" → "açık rıza" (where required to be unambiguous and explicit) or "rıza".

### 8. Pitfalls This Section Helps Avoid

- Confusing "anonymous" data with "pseudonymized" data and assuming GDPR no longer applies.
- Calling a vendor a "data processor" without scrutinizing whether they actually determine purposes (and therefore become a joint or independent controller).
- Assuming "consent" is the default lawful basis when "contract" or "legitimate interests" is the correct one — and creating user-experience friction or legal fragility.
- Missing that biometric data used for unique identification falls into Article 9, even though biometric data not used for unique identification may not.
- Treating "right to erasure" as absolute when it is conditional and subject to exceptions (Art. 17(3)).

### 9. Related Sections

- `00-governance/` — DPO, Privacy Committee, RACI.
- `02-records-and-registry/` — operationalizing definitions in ROPA.
- `03-transparency-and-consent/` — applying lawful bases in user-facing surfaces.
- `06-administrative-measures/` — embedding definitions in policy.
- `11-audit-and-compliance/` — testing whether classifications hold up in practice.

---

## Türkçe

### 1. Amaç

Bu bölüm, diğer her bölümün dayandığı GDPR kelime hazinesini ve kavramsal temeli oluşturur. "Kişisel veri", "veri sorumlusu", "veri işleyen", "rıza", "hukuki dayanak", "ilgili kişi hakları" ve "özel nitelikli kategoriler" için ortak ve kesin tanımlar olmadan programın geri kalanı kum üzerine inşa edilir.

Temel kavramlar belgeleri iki kitle için yazılmıştır:

- Yasal metni günlük kararlara çevirmesi gereken operasyonel ekipler (İK, BT, Pazarlama, Satın Alma, Mühendislik, Müşteri Destek).
- Maddeler, Gerekçeler, EDPB Rehberleri ve ABAD içtihadıyla desteklenen savunulabilir yorum gerektiren Hukuk, VKG ve Denetim ekipleri.

### 2. Tanımlar Neden Önemlidir

Yanlış sınıflandırma kademe kademe büyür. Kişisel veriyi anonim veri olarak ele almak, özel nitelikli verileri olağan kişisel veri gibi değerlendirmek, bir veri işleyeni veri sorumlusu olarak yanlış tanımlamak veya yanlış hukuki dayanağa güvenmek aşağıdaki en yaygın kök nedenlerdir:

- Madde 83 cezaları (20 milyon Euro'ya veya küresel yıllık cironun %4'üne kadar; hangisi daha yüksekse).
- Madde 82 kapsamında maddi ve manevi zarar için ilgili kişi talepleri.
- Avrupa Birliği Adalet Divanı (ABAD) aleyhe kararları.
- Düzenleyicinin işleme faaliyetini durdurma kararı.

Kesin tanımlara yatırım yapmak ve bunları kuruluş genelinde tutarlı uygulamak, mevcut en ucuz kontroldür.

### 3. Dosya Dizini

| # | Dosya | Amaç | Birincil GDPR Maddeleri |
|---|---|---|---|
| 1 | `README.md` | Bölüm girişi ve dosya dizini. | Md. 4, 5, 6 |
| 2 | `definitions.md` | Madde 4'ten 30+ anahtar terim ve operasyonel tanımlar. | Md. 4 |
| 3 | `personal-vs-special-categories.md` | Madde 9 özel nitelikli veriler ve Madde 10 cezai veriler. | Md. 9, 10 |
| 4 | `controller-vs-processor.md` | Madde 24–28, müşterek veri sorumluları (Md. 26), işleyen sözleşmeleri (Md. 28). | Md. 24, 26, 28 |
| 5 | `data-subject-rights.md` | Madde 12–22 — şeffaflık, erişim, düzeltme, silme, kısıtlama, taşınabilirlik, itiraz, OKV. | Md. 12–22 |
| 6 | `lawful-bases.md` | Madde 5 ilkeleri + Madde 6 hukuki dayanaklar, LIA şablonu, denge testi. | Md. 5, 6, 7 |

### 4. Bu Bölüm Nasıl Kullanılır?

1. Önce `definitions.md` okunur; diğer her belgenin kullandığı sözlüktür.
2. ROPA ve DPIA'larda veri kümelerini sınıflandırmak için `personal-vs-special-categories.md` kullanılır.
3. Yeni bir üçüncü taraf düzenlemesi düşünüldüğünde `controller-vs-processor.md` kullanılır.
4. Yeni her işleme için giriş kapısı olarak `lawful-bases.md` kullanılır — bu kuruluşta belgelenmiş hukuki dayanağı olmadan hiçbir işleme yoktur.
5. Hak işleme iş akışlarını yürütmek için `data-subject-rights.md` kullanılır.

### 5. Yetkili Kaynaklar

| Kaynak | Kullanım |
|---|---|
| (AB) 2016/679 sayılı Tüzük (GDPR) — tam metin | Birincil kaynak. |
| EDPB Rehberleri (en son sürümler) | Yetkili yorum. |
| EDPS görüşleri | Kamu sektörü ve AB kurumu bağlamı. |
| ABAD kararları (Costeja C-131/12; Bara C-201/14; Schrems II C-311/18; Planet49 C-673/17; Fashion ID C-40/17; Meta Platforms C-252/21) | GDPR kavramlarının bağlayıcı yorumu. |
| Üye Devlet hukuku (örn. Alman BDSG, Fransız Loi Informatique et Libertés) | Uygulama detayı ve uygulanabilir olduğunda daha katı kurallar. |
| ISO 27701, ISO 29134 | Gizlilik kontrolleri ve DPIA metodolojisi. |

### 6. Bakım

- Sahibi: VKG.
- Gözden geçirme döngüsü: yıllık ve aşağıdaki tetikleyicilerden herhangi birinde:
  - Yorumu maddi olarak etkileyen yeni bir EDPB rehberi.
  - Kapsamdaki GDPR kavramlarını etkileyen ABAD kararı.
  - Üye Devlet hukukunda değişiklik.
  - Yanlış yorumu işaret eden iç olay veya denetim bulgusu.

### 7. Sözlük Disiplini

Tanımları tutarlı tutmak için:

- Merkezi bir sözlük dosyası (`definitions.md`) tek doğru kaynaktır.
- Diğer belgeler aynı terimleri mümkün olduğunca aynen kullanmalı ve ilk kullanımda sözlüğe bağlantı vermelidir.
- Çeviriler, nitelikli bir veri koruma çevirmeni tarafından gözden geçirilmelidir; "controller" → "veri sorumlusu", "processor" → "veri işleyen", "data subject" → "ilgili kişi", "personal data" → "kişisel veri", "special categories" → "özel nitelikli kişisel veri kategorileri", "consent" → "açık rıza" (açık ve net olması gerektiğinde) veya "rıza".

### 8. Bu Bölümün Önlemeye Yardımcı Olduğu Tuzaklar

- "Anonim" verileri "takma adlı" verilerle karıştırmak ve GDPR'ın artık uygulanmadığını varsaymak.
- Bir tedarikçiyi gerçekten amaçları belirleyip belirlemediğini incelemeden "veri işleyen" olarak adlandırmak (ve bu nedenle müşterek veya bağımsız veri sorumlusu hâline gelmek).
- Doğru dayanak "sözleşme" veya "meşru menfaat" iken "rıza"yı varsayılan hukuki dayanak kabul etmek — ve böylece kullanıcı deneyimi sürtüşmesi veya hukuki kırılganlık oluşturmak.
- Benzersiz tanımlama için kullanılan biyometrik verilerin Madde 9'a girdiğini gözden kaçırmak — benzersiz tanımlama için kullanılmayan biyometrik veriler bu kapsama girmeyebilir.
- "Silme hakkını" mutlak kabul etmek — oysa şartlıdır ve istisnalara tabidir (Md. 17(3)).

### 9. İlgili Bölümler

- `00-governance/` — VKG, Gizlilik Komitesi, RACI.
- `02-records-and-registry/` — ROPA'da tanımları operasyonelleştirme.
- `03-transparency-and-consent/` — kullanıcıya yönelik yüzeylerde hukuki dayanakları uygulama.
- `06-administrative-measures/` — politikalara tanım gömme.
- `11-audit-and-compliance/` — sınıflandırmaların pratikte tutup tutmadığını test etme.
