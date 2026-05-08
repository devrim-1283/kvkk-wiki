---
title:
  en: "Special Topics — Section Index"
  tr: "Özel Konular — Bölüm Dizini"
section: "10-special-topics"
owner: "DPO Office"
classification: "Internal"
version: "1.0"
last_review: "2026-05-08"
next_review: "2027-05-08"
language: ["en", "tr"]
references:
  - "GDPR (full text)"
  - "ePrivacy Directive 2002/58/EC as amended"
  - "EU AI Act (Regulation 2024/1689)"
  - "EDPB Guidelines (cross-cutting)"
  - "ISO/IEC 42001:2023"
  - "NIST AI Risk Management Framework"
---

## English

### Purpose

The previous nine sections describe the controller's general data protection programme. This section covers topics that are specialised, sector-cross-cutting, or rapidly evolving. Each topic interacts with the general programme but adds its own legal sources, control patterns, and operational obligations.

### Index

| File | Topic |
|------|-------|
| `cookies-and-tracking.md` | ePrivacy Directive Art. 5(3), CMP, dark patterns, cookie wall, third-country pixels |
| `cctv-surveillance.md` | Video surveillance, signage, employee monitoring, facial recognition |
| `biometric-data.md` | Article 9 special category, Article 9(2) bases, EDPB 5/2022, alternative-least-intrusive |
| `health-data.md` | Article 9(2)(h)/(i), professional secrecy, EHR, HL7/FHIR |
| `hr-employee-data.md` | Article 88, recruitment to exit, monitoring proportionality, BYOD |
| `marketing-and-cms.md` | ePrivacy + GDPR consent, soft opt-in, profiling, adtech transfers |
| `cloud-services.md` | Shared responsibility, Article 28 DPA, sub-processor consent, third-country access laws |
| `ai-and-llm.md` | EU AI Act, Article 22, training data, employee LLM use, OWASP LLM Top 10, ISO 42001 |

### Reading order

For a privacy-by-design rollout, suggested reading order:

1. `ai-and-llm.md` and `cloud-services.md` for the platform layer.
2. `cookies-and-tracking.md` and `marketing-and-cms.md` for the customer-facing surface.
3. `biometric-data.md`, `health-data.md`, `cctv-surveillance.md` for the special-category categories.
4. `hr-employee-data.md` for the workforce-data programme.

Each file is self-contained and cross-references the others where decisions interact (e.g. employee monitoring CCTV references both `cctv-surveillance.md` and `hr-employee-data.md`).

### Risk overview

| Topic | Typical risk profile | DPIA usually required? |
|-------|---------------------|------------------------|
| Cookies and tracking | Medium — high if third-country adtech | If profiling at scale |
| CCTV surveillance | Medium — high if biometric or workplace | Yes if systematic monitoring |
| Biometric data | High — Article 9 | Yes |
| Health data | High — Article 9 | Yes |
| HR employee data | Medium — high | Often yes |
| Marketing | Medium | If profiling at scale |
| Cloud services | Medium — depends on scope, transfers | Yes if Schrems II concerns |
| AI / LLM | High — depends on use | Yes for high-risk under AI Act |

### Cross-references

- Section `00-governance` for the DPIA process and risk methodology.
- Section `02-ropa` for processing inventory.
- Section `03-transparency-consent` for consent mechanics.
- Section `04-retention-erasure` for retention rules.
- Section `05-technical-measures` for security baselines.
- Section `07-international-transfers` for transfer mechanisms.

---

## Türkçe

### Amaç

Önceki dokuz bölüm, veri sorumlusunun genel veri koruma programını anlatır. Bu bölüm, uzmanlaşmış, sektör çapında veya hızla gelişen konuları kapsar. Her konu genel programla etkileşir ancak kendi hukuki kaynaklarını, kontrol örüntülerini ve operasyonel yükümlülüklerini ekler.

### Dizin

| Dosya | Konu |
|-------|------|
| `cookies-and-tracking.md` | ePrivacy Direktifi Madde 5(3), CMP, karanlık örüntüler, çerez duvarı, üçüncü ülke pikselleri |
| `cctv-surveillance.md` | Video izleme, tabela, çalışan izleme, yüz tanıma |
| `biometric-data.md` | Madde 9 özel kategori, Madde 9(2) temelleri, EDPB 5/2022, en az müdahaleci alternatif |
| `health-data.md` | Madde 9(2)(h)/(i), mesleki gizlilik, EHR, HL7/FHIR |
| `hr-employee-data.md` | Madde 88, işe alımdan ayrılışa, izleme orantılılığı, BYOD |
| `marketing-and-cms.md` | ePrivacy + GDPR rıza, yumuşak opt-in, profilleme, reklam teknolojisi aktarımları |
| `cloud-services.md` | Paylaşılan sorumluluk, Madde 28 VİS, alt işleyen rızası, üçüncü ülke erişim hukuku |
| `ai-and-llm.md` | AB AI Yasası, Madde 22, eğitim verisi, çalışan LLM kullanımı, OWASP LLM Top 10, ISO 42001 |

### Okuma sırası

Tasarımda mahremiyet uygulaması için önerilen okuma sırası:

1. Platform katmanı için `ai-and-llm.md` ve `cloud-services.md`.
2. Müşteriye dönük yüzey için `cookies-and-tracking.md` ve `marketing-and-cms.md`.
3. Özel kategori kategorileri için `biometric-data.md`, `health-data.md`, `cctv-surveillance.md`.
4. İşgücü veri programı için `hr-employee-data.md`.

### Risk genel görünümü

| Konu | Tipik risk profili | VKD gerekli mi? |
|------|-------------------|-----------------|
| Çerezler ve izleme | Orta — üçüncü ülke reklam teknolojisi varsa yüksek | Ölçekli profilleme varsa |
| CCTV izleme | Orta — biyometrik veya işyeri ise yüksek | Sistematik izleme varsa evet |
| Biyometrik veri | Yüksek — Madde 9 | Evet |
| Sağlık verisi | Yüksek — Madde 9 | Evet |
| İK çalışan verisi | Orta — yüksek | Genellikle evet |
| Pazarlama | Orta | Ölçekli profilleme varsa |
| Bulut hizmetleri | Orta — kapsama, aktarımlara bağlı | Schrems II endişeleri varsa evet |
| AI / LLM | Yüksek — kullanıma bağlı | AI Yasası altında yüksek risk için evet |

### Çapraz referanslar

- VKD süreci ve risk metodolojisi için `00-governance` bölümü.
- İşleme envanteri için `02-ropa` bölümü.
- Rıza mekaniği için `03-transparency-consent` bölümü.
- Saklama kuralları için `04-retention-erasure` bölümü.
- Güvenlik temel çizgileri için `05-technical-measures` bölümü.
- Aktarım mekanizmaları için `07-international-transfers` bölümü.
