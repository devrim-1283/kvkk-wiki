---
title:
  en: "GDPR Section — Landing"
  tr: "GDPR Bolumu — Giris"
section: "gdpr"
owner: "DPO"
version: "1.0"
last_review: "2026-05-08"
next_review: "2026-11-08"
classification: "Internal"
languages: ["en", "tr"]
keywords:
  en: ["GDPR", "landing", "scope", "audience", "navigation"]
  tr: ["GDPR", "giris", "kapsam", "kitle", "navigasyon"]
---

## English

# GDPR Section — Landing

Welcome to the GDPR (Regulation (EU) 2016/679) section of the enterprise privacy wiki. This section is the controller's authoritative knowledge base for designing, operating, evidencing, and improving GDPR compliance.

### Scope

This section covers:

- The regulation itself — Articles 1-99 with operational impact mapping.
- The interpretive corpus — EDPB / WP29 guidelines and CJEU jurisprudence.
- Member state derogations affecting cross-border programs.
- Sister EU instruments interacting with GDPR — ePrivacy, NIS2, DSA, DMA, Data Act, DGA, AI Act.
- Operational guidance — governance, ROPA, transparency, consent, retention, transfers, technical and organizational measures, breach response, data subject rights, and special topics.
- Audit and compliance — maturity, KPIs, internal audit, supervisory authority engagement, sanctions.
- Templates — privacy notices, consent, ROPA, retention, breach, DSR responses, DPA, confidentiality, training, DPIA, LIA.

### Target audience

| Audience | What you need |
|----------|---------------|
| Data Protection Officer | Full structure; daily operating reference |
| Privacy office team | Operational guidance and templates |
| Senior management | Maturity and KPI dashboards (`11-audit-compliance/`) |
| Legal counsel | Legal archive (`12-legal-archive/`) and templates |
| Process owners | Section relevant to their processing + ROPA, retention, DSR |
| Engineering | Article 25 by-design, Article 32 technical measures, DPIA inputs |
| Information security | Article 32, breach response, vendor management |
| HR | Employee notice, employee data section, training, confidentiality |
| Marketing | Consent, transparency, direct marketing |
| Procurement | DPA, vendor due diligence, processor and sub-processor management |
| Internal audit | `11-audit-compliance/internal-audit.md` test procedures |
| External auditors and certification bodies | Documentation and evidence repositories |

### How to use this section

1. Start with `INDEX.md` for navigation.
2. New to GDPR? Read `01-core-concepts/` first, then `00-governance/`.
3. Operating a process? Open the corresponding section + `99-templates/` for ready-to-adapt artefacts.
4. Auditing? Use `11-audit-compliance/` and the legal archive.
5. Researching law? Use `12-legal-archive/`.
6. Always cite your source — Article, EDPB guideline, or CJEU case — when justifying a control or decision.

### Top-level repository

This section sits within the broader privacy and data protection program at the top-level repository (e.g. KVKK + GDPR + sectoral). See the top-level `README.md` (`..\README.md`) for cross-section navigation. Where Turkish and Spanish (or other) data protection laws have their own sections, look there for Turkish KVKK or jurisdiction-specific guidance.

### Bilingual format

Every document in this section is bilingual:

- English block first.
- Turkish block second, separated by `---`.
- YAML metadata header includes both language codes.
- Tables use bilingual headers where width allows.

### Versioning and ownership

Each document has an explicit owner (front-matter), version, last review date, and next review date. Document footer logs material changes.

### Confidentiality

All documents in this section are classified Internal unless marked otherwise. Templates may become Public when published (e.g. customer privacy notice). Investigation files and breach records are typically Confidential.

### Contributing

To propose a change:

1. Identify the document and section.
2. Open a change request describing the rationale and citing the source.
3. Privacy office reviews; legal review where material; DPO sign-off.
4. Approved changes update the document and version.

### Useful entry points

- `INDEX.md` — searchable bilingual master index.
- `12-legal-archive/gdpr-articles.md` — Article 1-99 with cross-links.
- `11-audit-compliance/maturity-model.md` — assess current state.
- `99-templates/` — start operationalizing today.

### Disclaimer

This wiki is an internal compliance reference. Templates and guidance are starting points. Engage qualified legal counsel for binding interpretations, and tailor to your actual processing, jurisdiction, and risk.

---

## Türkçe

# GDPR Bölümü — Giriş

Kurumsal gizlilik wiki'sinin GDPR (AB Tüzüğü 2016/679) bölümüne hoş geldiniz. Bu bölüm, GDPR uyumunu tasarlamak, işletmek, kanıtlamak ve iyileştirmek için veri sorumlusunun yetkili bilgi tabanıdır.

### Kapsam

Bu bölüm şunları kapsar:

- Tüzüğün kendisi — operasyonel etki eşleştirmeli Madde 1-99.
- Yorumlama külliyatı — EDPB / WP29 kılavuzları ve AAD içtihadı.
- Sınır ötesi programları etkileyen üye devlet istisnaları.
- GDPR ile etkileşen kardeş AB araçları — ePrivacy, NIS2, DSA, DMA, Data Act, DGA, AI Act.
- Operasyonel rehberlik — yönetişim, ROPA, şeffaflık, açık rıza, saklama, aktarımlar, teknik ve idari tedbirler, ihlal yanıtı, ilgili kişi hakları ve özel konular.
- Denetim ve uyumluluk — olgunluk, KPI'lar, iç denetim, denetim otoritesi etkileşimi, yaptırımlar.
- Şablonlar — aydınlatma metinleri, açık rıza, ROPA, saklama, ihlal, DSR yanıtları, DPA, gizlilik, eğitim, VKDM, MMD.

### Hedef kitle

| Kitle | İhtiyacınız |
|-------|-------------|
| Veri Koruma Görevlisi | Tam yapı; günlük operasyon referansı |
| Gizlilik ofisi ekibi | Operasyonel rehberlik ve şablonlar |
| Üst yönetim | Olgunluk ve KPI panoları (`11-audit-compliance/`) |
| Hukuk danışmanı | Hukuki arşiv (`12-legal-archive/`) ve şablonlar |
| Süreç sahipleri | Kendi işlemelerine ilişkin bölüm + ROPA, saklama, DSR |
| Mühendislik | Madde 25 tasarımda, Madde 32 teknik tedbirler, VKDM girdileri |
| Bilgi güvenliği | Madde 32, ihlal yanıtı, tedarikçi yönetimi |
| İK | Çalışan metni, çalışan veri bölümü, eğitim, gizlilik |
| Pazarlama | Açık rıza, şeffaflık, doğrudan pazarlama |
| Satın alma | DPA, tedarikçi durum tespiti, işleyen ve alt işleyen yönetimi |
| İç denetim | `11-audit-compliance/internal-audit.md` test prosedürleri |
| Dış denetçiler ve sertifikasyon kuruluşları | Belgeleme ve kanıt depoları |

### Bu bölüm nasıl kullanılır

1. Navigasyon için `INDEX.md` ile başlayın.
2. GDPR'a yeni misiniz? Önce `01-core-concepts/`, sonra `00-governance/` okuyun.
3. Bir süreç mi işletiyorsunuz? Hazır uyarlanabilir eserler için ilgili bölümü + `99-templates/` açın.
4. Denetim mi yapıyorsunuz? `11-audit-compliance/` ve hukuki arşivi kullanın.
5. Hukuk araştırıyor musunuz? `12-legal-archive/` kullanın.
6. Bir kontrolü veya kararı gerekçelendirirken her zaman kaynağınızı — Madde, EDPB kılavuzu veya AAD davası — atıf yapın.

### Üst seviye depo

Bu bölüm, üst seviye depodaki daha geniş gizlilik ve veri koruma programının (örn. KVKK + GDPR + sektörel) içinde yer alır. Bölümler arası navigasyon için üst seviye `README.md` (`..\README.md`) bakın. Türk ve İspanyol (veya başka) veri koruma yasalarının kendi bölümleri olduğunda, Türk KVKK veya yargı bölgesine özgü rehberlik için oraya bakın.

### İki dilli format

Bu bölümdeki her belge iki dillidir:

- Önce İngilizce blok.
- Ardından `---` ile ayrılmış Türkçe blok.
- YAML meta veri başlığı her iki dil kodunu içerir.
- Tablolar genişlik elverdiğinde iki dilli başlıklar kullanır.

### Sürümleme ve sahiplik

Her belgenin açık bir sahibi (front-matter), sürümü, son inceleme tarihi ve sonraki inceleme tarihi vardır. Belge altbilgisi maddi değişiklikleri kaydeder.

### Gizlilik

Bu bölümdeki tüm belgeler aksi belirtilmedikçe İç olarak sınıflandırılmıştır. Şablonlar yayınlandığında Kamuya Açık olabilir (örn. müşteri aydınlatma metni). Soruşturma dosyaları ve ihlal kayıtları tipik olarak Gizlidir.

### Katkıda bulunma

Bir değişiklik önermek için:

1. Belgeyi ve bölümü tanımlayın.
2. Gerekçeyi açıklayan ve kaynağı atıf yapan bir değişiklik talebi açın.
3. Gizlilik ofisi inceler; maddi olduğunda hukuk incelemesi; DPO onayı.
4. Onaylanan değişiklikler belgeyi ve sürümü günceller.

### Faydalı giriş noktaları

- `INDEX.md` — aranabilir iki dilli ana indeks.
- `12-legal-archive/gdpr-articles.md` — çapraz bağlantılarla Madde 1-99.
- `11-audit-compliance/maturity-model.md` — mevcut durumu değerlendirin.
- `99-templates/` — bugün operasyonel hale getirmeye başlayın.

### Sorumluluk reddi

Bu wiki bir iç uyum referansıdır. Şablonlar ve rehberlik başlangıç noktalarıdır. Bağlayıcı yorumlar için nitelikli hukuk danışmanını dahil edin ve gerçek işlemenize, yargı bölgenize ve riskinize göre uyarlayın.
