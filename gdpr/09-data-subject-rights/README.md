---
title:
  en: "Data Subject Rights — Section Index"
  tr: "İlgili Kişi Hakları — Bölüm Dizini"
section: "09-data-subject-rights"
owner: "DPO Office"
classification: "Internal"
version: "1.0"
last_review: "2026-05-08"
next_review: "2027-05-08"
language: ["en", "tr"]
references:
  - "GDPR Art. 12 — Transparent information, communication and modalities for the exercise of rights"
  - "GDPR Art. 13–14 — Information to be provided"
  - "GDPR Art. 15 — Right of access"
  - "GDPR Art. 16 — Right to rectification"
  - "GDPR Art. 17 — Right to erasure (right to be forgotten)"
  - "GDPR Art. 18 — Right to restriction of processing"
  - "GDPR Art. 19 — Notification obligation regarding rectification, erasure or restriction"
  - "GDPR Art. 20 — Right to data portability"
  - "GDPR Art. 21 — Right to object"
  - "GDPR Art. 22 — Automated individual decision-making, including profiling"
  - "EDPB Guidelines 01/2022 on data subject rights — Right of access"
  - "EDPB Guidelines 5/2020 on consent (relevant to objections and withdrawal)"
---

## English

### Purpose

This section sets out how the controller receives, processes, and answers requests from data subjects exercising the rights established by Articles 12 to 22 GDPR. The objective is a single, predictable, defensible workflow that respects the rights of the requester, protects the rights of others, complies with statutory deadlines, and produces an evidence trail sufficient for supervisory authority scrutiny.

### Rights overview matrix

| Article | Right | Trigger | Default deadline | Extension allowed | Free? | Refusal grounds |
|---------|-------|--------|------------------|-------------------|-------|----------------|
| 13–14 | Information at collection | Collection of data | At collection (13) / within 1 month or earlier (14) | n/a | Yes | Existing knowledge of subject (13(4), 14(5)) |
| 15 | Access | Verified request | 1 month | +2 months for complexity or volume | Yes | Manifestly unfounded/excessive (12(5)); rights of others (15(4)); national law derogations (23) |
| 16 | Rectification | Verified request, evidence of inaccuracy | 1 month | +2 months | Yes | None substantive — dispute via Art. 21 if applicable |
| 17 | Erasure | Verified request meeting one of grounds 17(1)(a)-(f) | 1 month | +2 months | Yes | Art. 17(3) exemptions: freedom of expression, legal obligation, public interest, public health, archiving, legal claims |
| 18 | Restriction | Verified request meeting one of grounds 18(1)(a)-(d) | 1 month | +2 months | Yes | None — restriction is a temporary state |
| 19 | Notification to recipients | After 16, 17, 18 actions | Without undue delay | n/a | Yes | Disproportionate effort |
| 20 | Portability | Verified request, processing on consent or contract, automated | 1 month | +2 months | Yes | Rights of others; manifestly unfounded |
| 21 | Object | Verified request, processing on legitimate interest, public task, direct marketing | 1 month | +2 months | Yes | Compelling legitimate grounds (not for direct marketing) |
| 22 | Automated decision-making | Verified request | 1 month | +2 months | Yes | Necessary for contract; authorised by law; explicit consent |

### Key principles in this section

1. **Identity verification proportionate to risk** — never an excuse to over-collect.
2. **Default to free** — fees are an exception, narrowly justified.
3. **Default to comply** — the burden is on the controller to demonstrate the basis for any refusal.
4. **Document every decision** — the SA's first request will be the case file.
5. **Bilingual response where the requester writes in Turkish** — and English where requester writes in English.
6. **Single source of truth** — the request management system holds the case file; email exchanges are attached, not authoritative.

### How this section is organised

| File | Purpose |
|------|---------|
| `dsr-procedure.md` | The end-to-end workflow |
| `dsr-form.md` | The fillable request form for the data subject |
| `sla-workflow.md` | Operational SLA mechanics, automation, escalation |
| `response-letter-templates.md` | Bilingual response templates per right |
| `fees-and-exceptions.md` | Articles 12(5), 15(4), 17(3) and national derogations |

### Cross-references

- Section `03-transparency-consent` for the upstream Article 13/14 information that primes data subjects on their rights.
- Section `04-retention-erasure` for the retention rules that govern erasure decisions.
- Section `05-technical-measures` for the access controls and audit logging that produce the evidence used in DSR responses.
- Section `08-breach-management` for the post-breach interaction between rights requests and breach handling.
- Section `12-legal-archive` for archival of closed DSR case files.

### KPIs

| KPI | Target |
|-----|--------|
| Median time to acknowledgement | < 2 working days |
| Median time to identity verification | < 5 working days |
| Median time to substantive response | < 18 working days (well within 1-month statutory) |
| Article 12(3) extension usage rate | < 10% of requests |
| Refusal rate | < 5%; every refusal escalated to DPO |
| Complaints to SA after our response | 0 target; root-caused if > 0 |

---

## Türkçe

### Amaç

Bu bölüm, veri sorumlusunun GDPR Madde 12 ila 22 ile belirlenen hakları kullanan ilgili kişilerden gelen talepleri nasıl aldığını, işlediğini ve yanıtladığını ortaya koyar. Amaç, talep edenin haklarına saygı gösteren, başkalarının haklarını koruyan, yasal süreleri karşılayan ve denetim makamı incelemesi için yeterli kanıt izi üreten tek, öngörülebilir, savunulabilir bir iş akışıdır.

### Hak genel görünümü matrisi

| Madde | Hak | Tetikleyici | Varsayılan süre | Uzatmaya izin verilir | Ücretsiz? | Reddetme gerekçeleri |
|-------|-----|------------|-----------------|----------------------|-----------|--------------------|
| 13–14 | Toplama anında bilgilendirme | Veri toplama | Toplamada (13) / 1 ay içinde (14) | Yok | Evet | Mevcut bilgi (13(4), 14(5)) |
| 15 | Erişim | Doğrulanmış talep | 1 ay | Karmaşıklık için +2 ay | Evet | Açıkça asılsız/aşırı; başkalarının hakları |
| 16 | Düzeltme | Doğrulanmış talep, kanıt | 1 ay | +2 ay | Evet | Esaslı yok |
| 17 | Silme | Doğrulanmış talep, 17(1)(a)-(f) | 1 ay | +2 ay | Evet | Madde 17(3) muafiyetleri |
| 18 | Kısıtlama | Doğrulanmış talep, 18(1)(a)-(d) | 1 ay | +2 ay | Evet | Yok |
| 19 | Alıcılara bildirim | 16, 17, 18 sonrası | Gecikmesiz | Yok | Evet | Orantısız çaba |
| 20 | Taşınabilirlik | Rıza/sözleşme, otomatik | 1 ay | +2 ay | Evet | Başkalarının hakları |
| 21 | İtiraz | Meşru menfaat, kamu görevi, doğrudan pazarlama | 1 ay | +2 ay | Evet | Zorunlu meşru gerekçeler |
| 22 | Otomatik karar | Doğrulanmış talep | 1 ay | +2 ay | Evet | Sözleşme; hukuk; açık rıza |

### Bu bölümdeki temel ilkeler

1. **Risk ile orantılı kimlik doğrulama** — asla aşırı toplama bahanesi değil.
2. **Varsayılan: ücretsiz** — ücretler dar bir istisnadır.
3. **Varsayılan: uy** — herhangi bir reddin temelini göstermek veri sorumlusunun yüküdür.
4. **Her kararı belgeleyin** — DM'nin ilk talebi dava dosyası olacaktır.
5. **Talep eden Türkçe yazdığında iki dilli yanıt** — ve İngilizce yazdığında İngilizce.
6. **Tek doğru kaynak** — talep yönetim sistemi dava dosyasını tutar.

### Bu bölüm nasıl düzenlenmiştir

| Dosya | Amaç |
|-------|------|
| `dsr-procedure.md` | Uçtan uca iş akışı |
| `dsr-form.md` | İlgili kişinin doldurduğu talep formu |
| `sla-workflow.md` | Operasyonel SLA mekaniği, otomasyon, yükseltme |
| `response-letter-templates.md` | Hak başına iki dilli yanıt şablonları |
| `fees-and-exceptions.md` | Madde 12(5), 15(4), 17(3) ve ulusal istisnalar |

### Çapraz referanslar

- `03-transparency-consent` — yukarı akış Madde 13/14 bilgilendirme.
- `04-retention-erasure` — silme kararlarını yöneten saklama kuralları.
- `05-technical-measures` — DSR yanıtlarında kullanılan kanıtı üreten erişim kontrolleri ve denetim günlüğü.
- `08-breach-management` — ihlal sonrası hak talepleri.
- `12-legal-archive` — kapatılmış DSR dosyalarının arşivlenmesi.

### KPI'lar

| KPI | Hedef |
|-----|-------|
| Onay almaya ortalama süre | < 2 iş günü |
| Kimlik doğrulamaya ortalama süre | < 5 iş günü |
| Esaslı yanıta ortalama süre | < 18 iş günü |
| Madde 12(3) uzatma kullanım oranı | < %10 |
| Reddetme oranı | < %5 |
| Yanıt sonrası DM şikayetleri | 0 hedef |
