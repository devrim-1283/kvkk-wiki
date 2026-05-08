# KVKK + GDPR Enterprise Wiki

> Türkçe / English — *Türkiye KVKK (Kanun No. 6698) ve EU GDPR (Tüzük 2016/679) için kurumsal uyum wiki şablonu — her doküman EN+TR paralel.*
> *Enterprise-grade compliance playbook for Türkiye's KVKK (Law No. 6698) and EU GDPR (Regulation 2016/679) — every document in parallel English + Turkish.*

---

## 🇹🇷 Türkçe

### Bu repo nedir?

İki yargı alanını tek çatı altında toplayan, doğrudan kullanılabilir kurumsal uyum wiki şablonudur:

- **KVKK** — kök seviyede `00-…` `99-sablonlar` klasörleri
- **GDPR** — `gdpr/` alt klasörü (00-governance … 99-templates)

Her doküman **bilingual**'dır: önce `## English`, sonra `## Türkçe` bölümü; üstte ortak metadata. KVKK Sorumlusu / DPO, hukuk, IT, IT güvenlik, İK, satınalma, iş birimleri ve yönetim için ortak başvuru kaynağıdır.

> *"Veriyi nasıl ve ne şekilde tutmalıyız?"* sorusuna mevzuat + operasyon + teknoloji düzleminde tek elden, iki yargı alanında yanıt.

### Kapsam

#### KVKK (Türkiye)
- 🏛️ KVKK m.1–32, VERBİS Yönetmeliği, Aydınlatma Tebliği, Başvuru Tebliği, İmha Yönetmeliği, yurt dışı aktarım rejimi (12.03.2024 / 7499 sayılı Kanun, 04.06.2024 / 2024-959 Kurul kararı), Kurul kararları (2018/10, 2019/10, 2024/959).
- 🧭 KVKK sorumlusu, irtibat kişisi, komite, RACI, yıllık takvim.
- ⚙️ KVKİ envanteri, VERBİS, saklama-imha, açık rıza, başvuru, ihlal müdahale.
- 🔐 Erişim, şifreleme, log, yedek, DLP, maskeleme, bulut, AI.

#### GDPR (EU/EEA)
- 🏛️ GDPR Art. 1–99, EDPB Guidelines, ECJ jurisprudence (Schrems I/II, Costeja, Bara, Planet49, Fashion ID, Wirtschaftsakademie, SCHUFA, Meta), national derogations (DE/FR/IT/ES/NL/IE/PL).
- 🧭 DPO (Art. 37–39), EU representative (Art. 27), committee, RACI.
- ⚙️ ROPA (Art. 30), transparency (Art. 12-14), consent (Art. 7), retention & erasure (Art. 5(1)(e), 17), DSR (Art. 15-22), breach (Art. 33-34).
- 🌍 Cross-border transfers — adequacy decisions, SCCs (2021/914, four modules), BCRs, TIA (post-Schrems II), Art. 49 derogations.
- 🔐 Art. 32 technical & organizational measures, ISO 27701, NIST CSF, EU AI Act (Reg. 2024/1689), OWASP LLM Top 10.

### Klasör yapısı

```
.
├── 00-yonetisim/                # KVKK — Yönetişim
├── 01-temel-kavramlar/          # KVKK — Temel kavramlar
├── 02-envanter-ve-sicil/        # KVKK — Envanter + VERBİS
├── 03-aydinlatma-ve-acik-riza/  # KVKK — Aydınlatma + açık rıza
├── 04-veri-saklama-ve-imha/     # KVKK — Saklama + imha
├── 05-teknik-tedbirler/         # KVKK — Teknik tedbirler
├── 06-idari-tedbirler/          # KVKK — İdari tedbirler
├── 07-aktarim/                  # KVKK — Aktarım
├── 08-ihlal-yonetimi/           # KVKK — İhlal yönetimi
├── 09-ilgili-kisi-basvurulari/  # KVKK — İlgili kişi başvuruları
├── 10-ozel-konular/             # KVKK — Çerez, CCTV, biyometrik, sağlık, İK, AI
├── 11-denetim-ve-uyum/          # KVKK — Denetim + uyum
├── 12-mevzuat-arsiv/            # KVKK — Mevzuat arşivi
├── 99-sablonlar/                # KVKK — Tüm şablonlar
├── INDEX.md                     # KVKK — Master index
│
├── gdpr/
│   ├── 00-governance/           # GDPR — DPO, EU representative, committee
│   ├── 01-core-concepts/        # GDPR — Definitions, rights, lawful bases
│   ├── 02-ropa/                 # GDPR — Records of Processing (Art. 30)
│   ├── 03-transparency-consent/ # GDPR — Privacy notice + consent
│   ├── 04-retention-erasure/    # GDPR — Storage limitation + Art. 17
│   ├── 05-technical-measures/   # GDPR — Art. 32 technical
│   ├── 06-organizational-measures/ # GDPR — Organizational
│   ├── 07-international-transfers/ # GDPR — Chapter V, SCCs, BCRs, TIA
│   ├── 08-breach-management/    # GDPR — Art. 33-34
│   ├── 09-data-subject-rights/  # GDPR — Art. 15-22
│   ├── 10-special-topics/       # GDPR — Cookies, CCTV, biometrics, health, AI
│   ├── 11-audit-compliance/     # GDPR — Audit, fines, sanctions
│   ├── 12-legal-archive/        # GDPR — Articles, EDPB, ECJ, national
│   ├── 99-templates/            # GDPR — Templates
│   ├── INDEX.md                 # GDPR — Master index
│   └── README.md                # GDPR — Section landing
│
├── LICENSE                      # CC BY 4.0
└── README.md                    # Bu dosya
```

### Kimler kullanmalı?

| Rol | KVKK öncelik | GDPR öncelik |
|-----|--------------|--------------|
| KVKK Sorumlusu / DPO | `00`, `02`, `09`, `11` | `gdpr/00`, `gdpr/02`, `gdpr/09`, `gdpr/11` |
| Hukuk / Legal | `01`, `03`, `07`, `12` | `gdpr/01`, `gdpr/03`, `gdpr/07`, `gdpr/12` |
| IT / Bilgi Güvenliği | `04`, `05`, `08`, `10` | `gdpr/04`, `gdpr/05`, `gdpr/08`, `gdpr/10` |
| İK | `03`, `06`, `10` | `gdpr/03`, `gdpr/06`, `gdpr/10` |
| Satınalma | `06`, `07`, `99` | `gdpr/06`, `gdpr/07`, `gdpr/99` |
| Pazarlama | `03`, `10` | `gdpr/03`, `gdpr/10` |
| Yönetim / Denetim | `00`, `11` | `gdpr/00`, `gdpr/11` |

### Nasıl başlanır?

1. [`INDEX.md`](./INDEX.md) → KVKK doküman dizini.
2. [`gdpr/INDEX.md`](./gdpr/INDEX.md) → GDPR doküman dizini.
3. Yeni süreç: önce envanter (`02-…` veya `gdpr/02-ropa`), sonra aydınlatma/rıza (`03-…` veya `gdpr/03-transparency-consent`).
4. SaaS/bulut alımı: `06-idari-tedbirler/tedarikci-yonetimi.md` + `07-aktarim` + `10-ozel-konular/bulut-hizmetleri.md` (KVKK), `gdpr/06-organizational-measures/vendor-management.md` + `gdpr/07-international-transfers/scc-guide.md` + `gdpr/10-special-topics/cloud-services.md` (GDPR).
5. İhlal anında: `08-ihlal-yonetimi/ihlal-mudahale-prosedur.md` ve/veya `gdpr/08-breach-management/incident-response.md`.

### Ön koşul

- Repo bir **şablondur**, hukuki mütalaa yerine geçmez.
- Her şirket; faaliyet alanı, ölçeği ve riski doğrultusunda dokümanları uyarlamalı, hukuk müşaviri ve KVKK Sorumlusu / DPO onayından geçirmelidir.
- KVKK güncel resmî metinleri: [kvkk.gov.tr](https://www.kvkk.gov.tr).
- GDPR güncel: [eur-lex.europa.eu](https://eur-lex.europa.eu) ve [edpb.europa.eu](https://edpb.europa.eu).

### Lisans

[`CC BY 4.0`](./LICENSE).

### İletişim

- **Devrim Tunçer**
- 📧 [devrim@devrimsoft.com](mailto:devrim@devrimsoft.com)
- 📱 +90 538 691 22 83
- 🌐 [devrimsoft.com](https://devrimsoft.com)

> **Uyarı**: Bu wiki bir uyum çerçevesidir. Spesifik vakalarda yetkili hukuk müşaviri görüşü alınmalıdır.

---

## 🇬🇧 English

### What is this repository?

A unified, ready-to-adopt corporate wiki template covering **two jurisdictions** under one roof:

- **KVKK** — Türkiye's Personal Data Protection Law (Law No. 6698). Folders `00-…` to `99-sablonlar` at repo root.
- **GDPR** — EU General Data Protection Regulation (Regulation 2016/679). Under `gdpr/` (00-governance to 99-templates).

Every document is **bilingual** — `## English` first, then `## Türkçe`, with shared metadata header. Designed for DPO/KVKK Officer, legal, IT, IT security, HR, procurement, business units, and management.

> Single-source answer to *"How and in what manner must we hold personal data?"* — across both regimes, bridging law, operations, and technology.

### Scope

#### KVKK (Türkiye)
- 🏛️ KVKK Art. 1–32, VERBIS Regulation, Disclosure Communiqué, Application Communiqué, Erasure Regulation, cross-border transfer regime (Law No. 7499 of 12.03.2024, Authority Decision 2024/959), Authority decisions (2018/10, 2019/10, 2024/959).
- 🧭 KVKK Officer, contact person, committee, RACI, annual calendar.
- ⚙️ ROPA-equivalent, VERBIS registration, retention–destruction, explicit consent, data subject requests, breach response.

#### GDPR (EU/EEA)
- 🏛️ GDPR Articles 1–99, EDPB Guidelines, ECJ jurisprudence (Schrems I/II, Costeja, Bara, Planet49, Fashion ID, Wirtschaftsakademie, SCHUFA, Meta), national derogations (DE/FR/IT/ES/NL/IE/PL).
- 🧭 DPO (Art. 37–39), EU representative (Art. 27), committee, RACI.
- ⚙️ ROPA (Art. 30), transparency (Art. 12-14), consent (Art. 7), retention & erasure (Art. 5(1)(e), 17), DSR (Art. 15-22), breach (Art. 33-34).
- 🌍 Cross-border transfers — adequacy, SCCs (Implementing Decision 2021/914, four modules), BCRs (Art. 47), Transfer Impact Assessment post-Schrems II, Art. 49 derogations.
- 🔐 Art. 32 technical & organizational measures, ISO 27701, NIST CSF 2.0, EU AI Act (Reg. 2024/1689), OWASP LLM Top 10 2025.

### Folder structure

See the Turkish section above — same tree.

### Who should use it?

| Role | KVKK priority | GDPR priority |
|------|---------------|---------------|
| DPO / KVKK Officer | `00`, `02`, `09`, `11` | `gdpr/00`, `gdpr/02`, `gdpr/09`, `gdpr/11` |
| Legal | `01`, `03`, `07`, `12` | `gdpr/01`, `gdpr/03`, `gdpr/07`, `gdpr/12` |
| IT / IT Security | `04`, `05`, `08`, `10` | `gdpr/04`, `gdpr/05`, `gdpr/08`, `gdpr/10` |
| HR | `03`, `06`, `10` | `gdpr/03`, `gdpr/06`, `gdpr/10` |
| Procurement | `06`, `07`, `99` | `gdpr/06`, `gdpr/07`, `gdpr/99` |
| Marketing | `03`, `10` | `gdpr/03`, `gdpr/10` |
| Management / Audit | `00`, `11` | `gdpr/00`, `gdpr/11` |

### How to start

1. [`INDEX.md`](./INDEX.md) — KVKK searchable index.
2. [`gdpr/INDEX.md`](./gdpr/INDEX.md) — GDPR searchable index.
3. New process: start with the inventory (`02-…` or `gdpr/02-ropa`), then notice & consent (`03-…` or `gdpr/03-transparency-consent`).
4. SaaS/cloud purchase: combine vendor management + transfer + cloud services in the relevant jurisdiction.
5. Incident: go straight to `08-ihlal-yonetimi/ihlal-mudahale-prosedur.md` and/or `gdpr/08-breach-management/incident-response.md`.

### Disclaimer

- This repository is a **template**, not legal advice.
- Every organization must adapt the documents to its sector, scale, and risk posture, and have them reviewed by qualified legal counsel and the DPO/KVKK Officer.
- For current official statutory texts: KVKK at [kvkk.gov.tr](https://www.kvkk.gov.tr); GDPR at [eur-lex.europa.eu](https://eur-lex.europa.eu) and [edpb.europa.eu](https://edpb.europa.eu).

### Contributing

PRs welcome. Summarize: affected document, statute/guideline reference, rationale. Updates triggered by legislative change or new authority decision are prioritized.

### License

[`CC BY 4.0`](./LICENSE).

### Contact

- **Devrim Tunçer**
- 📧 [devrim@devrimsoft.com](mailto:devrim@devrimsoft.com)
- 📱 +90 538 691 22 83
- 🌐 [devrimsoft.com](https://devrimsoft.com)

> **Notice**: This wiki is a compliance framework. For specific cases, always seek qualified legal counsel.

---

### Repo Stats

- **209 dosya / 209 files** — Markdown + CSV
- **~98.700+ satır / lines** of bilingual operational content
- **2 jurisdictions** — KVKK + GDPR
- **14 sections × 2** — fully parallel structure
