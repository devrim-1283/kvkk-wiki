# KVKK Enterprise Wiki

> Türkçe / English — *KVKK uyumlu kurumsal wiki şablonu / Enterprise-grade compliance playbook for Türkiye's Personal Data Protection Law (Law No. 6698)*

---

## 🇹🇷 Türkçe

### Bu repo nedir?

**6698 sayılı Kişisel Verilerin Korunması Kanunu (KVKK)** kapsamında veri sorumlusu konumundaki kurumlar için baştan sona uyum çerçevesi sunan, doğrudan kullanılabilir kurumsal bir wiki şablonudur. KVKK sorumlusu (irtibat kişisi/DPO), hukuk, IT, IT güvenlik, IK, satınalma, iş birimleri ve yönetim için ortak başvuru kaynağıdır.

> *"Veriyi nasıl ve ne şekilde tutmalıyız?"* sorusuna mevzuat + operasyon + teknoloji düzleminde tek elden yanıt verir.

### Kapsam

- 🏛️ **Hukuki çerçeve**: KVKK (m.1–32), VERBİS Yönetmeliği, Aydınlatma Tebliği, Başvuru Tebliği, İmha Yönetmeliği, yurt dışı aktarım rejimi (12.03.2024 / 7499 sayılı Kanun değişiklikleri dâhil), Kurul kararları.
- 🧭 **Yönetişim**: KVKK sorumlusu rolü, RACI, komite tüzüğü, yıllık uyum takvimi.
- ⚙️ **Operasyon**: Kişisel veri işleme envanteri, saklama–imha politikası, açık rıza yönetimi, ilgili kişi başvuru süreci, ihlal müdahale planı.
- 🔐 **Teknoloji**: Erişim kontrolü, şifreleme, log, yedekleme, DLP, maskeleme/anonimleştirme, bulut, AI/LLM ek kontrolleri.
- 📄 **Şablonlar**: Aydınlatma metni, açık rıza formu, envanter, taahhütname, veri işleyen sözleşmesi (DPA), ihlal bildirim formu, DPIA/LIA formları.

### Klasör yapısı

```
.
├── 00-yonetisim/                # KVKK sorumlusu, irtibat kişisi, komite, RACI, yıllık takvim
├── 01-temel-kavramlar/          # Tanımlar, ilkeler, ilgili kişi hakları, işleme şartları
├── 02-envanter-ve-sicil/        # KVKİ envanteri, VERBİS kayıt ve istisna
├── 03-aydinlatma-ve-acik-riza/  # Aydınlatma metni, açık rıza, kanal bazlı örnekler
├── 04-veri-saklama-ve-imha/     # Saklama–imha politikası, süre tablosu, periyodik imha
├── 05-teknik-tedbirler/         # Erişim, şifreleme, log, yedek, DLP, ağ, uygulama güvenliği
├── 06-idari-tedbirler/          # Politika seti, eğitim, sözleşme, risk, iç denetim
├── 07-aktarim/                  # Yurt içi/dışı aktarım, standart sözleşme, BCR, arızi haller
├── 08-ihlal-yonetimi/           # İhlal müdahale, 72 saat bildirim, kök neden analizi
├── 09-ilgili-kisi-basvurulari/  # Başvuru yönetimi, 30 gün, ücret, cevap şablonları
├── 10-ozel-konular/             # Çerez, CCTV, biyometrik, sağlık, IK, pazarlama, bulut, AI
├── 11-denetim-ve-uyum/          # Olgunluk modeli, KPI, iç denetim, Kurul denetim hazırlığı, yaptırımlar
├── 12-mevzuat-arsiv/            # 6698, VERBİS Yön., tebliğler, Kurul kararları özetleri
├── 99-sablonlar/                # Tüm şablon ve formlar
├── INDEX.md                     # Tüm doküman dizini ve sahiplik
├── LICENSE                      # CC BY 4.0
└── README.md                    # Bu dosya
```

### Kimler kullanmalı?

| Rol | Öncelikli bölümler |
|-----|---------------------|
| KVKK Sorumlusu / İrtibat Kişisi | `00`, `02`, `09`, `11` |
| Hukuk | `01`, `03`, `07`, `12` |
| IT / IT Güvenlik | `04`, `05`, `08`, `10` |
| İK | `03`, `06`, `10/ik-ve-calisan-verisi.md` |
| Satınalma / Tedarikçi Yönetimi | `06/tedarikci-yonetimi.md`, `07`, `99` |
| Pazarlama / Müşteri Operasyonu | `03`, `10/musteri-pazarlama-cms.md`, `10/cerez-yonetimi.md` |
| Yönetim / Denetim | `00`, `11` |

### Nasıl başlanır?

1. [`INDEX.md`](./INDEX.md) → tüm dokümanların aranabilir dizini ve sahiplik tablosu.
2. Yeni bir süreç başlatırken **önce** envanter (`02-envanter-ve-sicil/`) → sonra aydınlatma/rıza (`03-aydinlatma-ve-acik-riza/`).
3. Yeni SaaS/bulut alırken `06-idari-tedbirler/tedarikci-yonetimi.md` + `07-aktarim/` + `10-ozel-konular/bulut-hizmetleri.md`.
4. İhlal anında derhâl `08-ihlal-yonetimi/ihlal-mudahale-prosedur.md`.
5. Yıllık denetim için `11-denetim-ve-uyum/uyum-olgunluk-modeli.md` + `00-yonetisim/yillik-takvim.md`.

### Ön koşul

- Repo bir **şablondur**, hukuki mütalaa yerine geçmez.
- Her şirket; faaliyet alanı, ölçeği ve riski doğrultusunda dokümanları uyarlamalı, hukuk müşaviri ve KVKK sorumlusu onayından geçirmelidir.
- Mevzuatın güncel resmî metinleri için: [kvkk.gov.tr](https://www.kvkk.gov.tr) ve Resmî Gazete arşivi.

### Katkı

Pull request açıkken lütfen değişikliği etkilenen wiki dokümanı, ilgili mevzuat atfı ve gerekçe ile birlikte özetleyin. Mevzuat değişikliği veya yeni Kurul kararı sonrası güncellemeler önceliklidir.

### Lisans

Wiki içeriği [`CC BY 4.0`](./LICENSE) altında yayımlanır.

### İletişim

- **Devrim Tunçer**
- 📧 [devrim@devrimsoft.com](mailto:devrim@devrimsoft.com)
- 📱 +90 538 691 22 83
- 🌐 [devrimsoft.com](https://devrimsoft.com)

> **Uyarı**: Bu wiki bir uyum çerçevesidir. Spesifik vakalarda yetkili hukuk müşaviri görüşü alınmalıdır.

---

## 🇬🇧 English

### What is this repository?

An **enterprise-grade compliance playbook** for organizations acting as Data Controllers under **Türkiye's Personal Data Protection Law (Law No. 6698 — KVKK)**. It is a ready-to-adopt corporate wiki template covering legal, governance, operational, and technical dimensions, designed for Data Protection Officers (contact persons), legal counsel, IT, IT security, HR, procurement, business units, and management.

> Single-source answer to *"How and in what manner must we hold personal data?"* — bridging law, operations, and technology.

### Scope

- 🏛️ **Legal framework**: KVKK (Articles 1–32), VERBIS Regulation, Disclosure Communiqué, Application Communiqué, Erasure/Destruction/Anonymization Regulation, the cross-border transfer regime (including Law No. 7499 amendments effective 01.06.2024 and Authority Decision 2024/959), and Authority precedents.
- 🧭 **Governance**: DPO/contact person role, RACI matrix, committee charter, annual compliance calendar.
- ⚙️ **Operations**: Personal data processing inventory, retention & destruction policy, consent management, data subject request workflow, breach response plan.
- 🔐 **Technology**: Access control, encryption, logging, backup, DLP, masking/anonymization, cloud, AI/LLM-specific controls.
- 📄 **Templates**: Privacy notice, consent form, ROPA-style inventory, confidentiality undertaking, Data Processing Agreement (DPA), breach notification form, DPIA/LIA worksheets.

### Folder structure

```
.
├── 00-yonetisim/                # Governance — DPO, contact person, committee, RACI, calendar
├── 01-temel-kavramlar/          # Core concepts — definitions, principles, rights, lawful bases
├── 02-envanter-ve-sicil/        # ROPA inventory & VERBIS registration
├── 03-aydinlatma-ve-acik-riza/  # Privacy notices & explicit consent
├── 04-veri-saklama-ve-imha/     # Retention & destruction (erasure, destruction, anonymization)
├── 05-teknik-tedbirler/         # Technical safeguards
├── 06-idari-tedbirler/          # Organizational safeguards
├── 07-aktarim/                  # Domestic & cross-border transfers
├── 08-ihlal-yonetimi/           # Breach management — 72-hour notification
├── 09-ilgili-kisi-basvurulari/  # Data subject requests
├── 10-ozel-konular/             # Special topics — cookies, CCTV, biometrics, health, HR, marketing, cloud, AI
├── 11-denetim-ve-uyum/          # Audit & compliance — maturity model, KPIs, sanctions
├── 12-mevzuat-arsiv/            # Legal archive — annotated statutes & Authority decisions
├── 99-sablonlar/                # All templates
├── INDEX.md                     # Master index & ownership
├── LICENSE                      # CC BY 4.0
└── README.md                    # This file
```

### Who should use it?

| Role | Primary sections |
|------|------------------|
| Data Protection Officer / Contact Person | `00`, `02`, `09`, `11` |
| Legal | `01`, `03`, `07`, `12` |
| IT / IT Security | `04`, `05`, `08`, `10` |
| HR | `03`, `06`, `10/ik-ve-calisan-verisi.md` |
| Procurement / Vendor Management | `06/tedarikci-yonetimi.md`, `07`, `99` |
| Marketing / Customer Ops | `03`, `10/musteri-pazarlama-cms.md`, `10/cerez-yonetimi.md` |
| Management / Audit | `00`, `11` |

### How to start

1. [`INDEX.md`](./INDEX.md) — searchable index of all documents and ownership.
2. New process? Start with the inventory (`02-envanter-ve-sicil/`), then notice & consent (`03-aydinlatma-ve-acik-riza/`).
3. New SaaS/cloud purchase? Combine `06-idari-tedbirler/tedarikci-yonetimi.md` + `07-aktarim/` + `10-ozel-konular/bulut-hizmetleri.md`.
4. Incident? Go straight to `08-ihlal-yonetimi/ihlal-mudahale-prosedur.md`.
5. Annual audit? `11-denetim-ve-uyum/uyum-olgunluk-modeli.md` + `00-yonetisim/yillik-takvim.md`.

### Disclaimer

- This repository is a **template**, not legal advice.
- Every organization must adapt these documents to its sector, scale, and risk posture, and have them reviewed by qualified legal counsel and the DPO/contact person.
- For the current official statutory texts, see [kvkk.gov.tr](https://www.kvkk.gov.tr) and the Turkish Official Gazette archive.

### Contributing

When opening a PR, summarize the change with: affected wiki document, the relevant statute/article reference, and your rationale. Updates triggered by legislative amendments or new Authority decisions are prioritized.

### License

Wiki content is released under [`CC BY 4.0`](./LICENSE).

### Contact

- **Devrim Tunçer**
- 📧 [devrim@devrimsoft.com](mailto:devrim@devrimsoft.com)
- 📱 +90 538 691 22 83
- 🌐 [devrimsoft.com](https://devrimsoft.com)

> **Notice**: This wiki is a compliance framework. For specific cases, always seek qualified legal counsel.
