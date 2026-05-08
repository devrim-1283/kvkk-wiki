---
title:
  en: "Templates Index"
  tr: "Sablonlar Indeksi"
section: "99-templates"
owner: "DPO / Legal"
version: "1.0"
last_review: "2026-05-08"
next_review: "2026-11-08"
classification: "Internal"
languages: ["en", "tr"]
keywords:
  en: ["templates", "privacy notice", "consent", "ROPA", "DPA", "DPIA", "LIA"]
  tr: ["sablonlar", "aydinlatma", "riza", "VERBIS", "DPA", "VKDM", "MMD"]
---

## English

# Templates Index

This section contains legal-grade, ready-to-adapt templates that operationalize GDPR obligations. Each template is a starting point — controllers must tailor wording to their actual processing, jurisdiction, sector, and risk profile, and have local counsel review where material.

### How to use these templates

1. Identify the obligation. Cross-reference the wiki section that explains the substantive law.
2. Open the template. Read the entire template before editing — placeholder fields are throughout.
3. Tailor. Replace `[bracketed placeholders]` with controller-specific text. Remove inapplicable clauses.
4. Review. Have legal counsel review before publication or signature.
5. Translate. Templates are bilingual (EN/TR) by default. If your data subject base requires additional languages, translate consistently and version-control each language pack.
6. Version. Track who, what, when changed in document footer.
7. Approve. Route through privacy office sign-off and any business-line approvals.
8. Publish or execute. Apply the template in production with audit trail.

### Index

| File | Purpose | Article basis |
|------|---------|---------------|
| `privacy-notice.md` | Three privacy notices: customer/web, employee, CCTV | Art. 12-14 |
| `consent-form.md` | Three consent forms: marketing, third-country transfer, profiling | Art. 4(11), 7, 9, 22, 49 |
| `ropa.csv` | ROPA template with bilingual headers and example rows | Art. 30 |
| `retention-policy.md` | Full retention and destruction policy | Art. 5(1)(e), 17 |
| `breach-notification.md` | Article 33 notification form + internal triage | Art. 33-34 |
| `dsr-response.md` | Bilingual response letters per Article 15-22 | Art. 12-22 |
| `dpa.md` | Article 28 DPA full template | Art. 28 |
| `confidentiality-undertaking.md` | Employee/contractor/intern confidentiality | Art. 28(3)(b), 29, 32(4) |
| `training-tracker.md` | Training attendance and curriculum tracking | Art. 39(1)(b) |
| `dpia-form.md` | Article 35 DPIA full form | Art. 35-36 |
| `lia-form.md` | Legitimate Interest Assessment | Art. 6(1)(f) |

### Naming conventions

- Use the exact field labels in your templates so that data flows between templates remain consistent (e.g. processing activity name appears identically in ROPA, DPIA, retention schedule).
- Keep version numbers visible at the top of each template instance.
- Where bilingual, place English first and Turkish below the divider, or use parallel columns.

### Common pitfalls

- Filling in only the fields you find easy and leaving the rest blank — every field must be answered or marked "not applicable" with reason.
- Copying a template from another project without re-validating jurisdiction.
- Treating templates as "set and forget" — they require periodic refresh, especially after major regulatory change.

### Quality criteria

A completed template is acceptable only when it:

1. Cites the specific article(s) it implements.
2. Is dated and version-controlled.
3. Has an identified owner.
4. Is accessible to relevant stakeholders.
5. Has been reviewed by legal/DPO at least once.
6. Reflects current ROPA reality (no orphaned templates).

### Cross-reference matrix

| Operation | Templates needed |
|-----------|------------------|
| New website launch | privacy-notice (customer), consent-form (cookies/marketing), ropa, lia-form (if legitimate interest) |
| New employee onboarding | privacy-notice (employee), confidentiality-undertaking, training-tracker |
| New SaaS vendor (processor) | dpa, ropa update, possibly dpia |
| New high-risk processing | dpia, lia (if applicable), ropa, privacy-notice |
| Personal data breach | breach-notification + triage, possibly dsr-response if affected requests |
| Data subject request | dsr-response, internal log |
| New third-country transfer | dpa, consent-form (third-country), TIA, ropa |

### Maintenance

Templates are reviewed annually or upon material legal change. Versions are recorded. Older versions are archived for evidence (e.g. version of privacy notice in force at the time of a complaint).

---

## Türkçe

# Şablonlar İndeksi

Bu bölüm, GDPR yükümlülüklerini operasyonel hale getiren hukuk düzeyinde, hazır-uyarlanabilir şablonlar içerir. Her şablon bir başlangıç noktasıdır — veri sorumluları metni gerçek işlemelerine, yargı bölgesine, sektörüne ve risk profiline göre uyarlamalı ve maddi olduğunda yerel danışmanın incelemesini sağlamalıdır.

### Bu şablonlar nasıl kullanılır

1. Yükümlülüğü tanımlayın. Maddi hukuku açıklayan wiki bölümüne çapraz referans verin.
2. Şablonu açın. Düzenlemeden önce tüm şablonu okuyun — yer tutucu alanlar boyunca vardır.
3. Uyarlayın. `[parantezli yer tutucuları]` veri sorumlusuna özgü metinle değiştirin. Geçerli olmayan maddeleri kaldırın.
4. İnceleyin. Yayınlamadan veya imzalamadan önce hukuk danışmanı incelemesini sağlayın.
5. Çevirin. Şablonlar varsayılan olarak iki dillidir (EN/TR). İlgili kişi tabanınız ek diller gerektirirse, tutarlı şekilde çevirin ve her dil paketini sürüm kontrolü altına alın.
6. Sürümlendirin. Belge altbilgisinde kim, ne, ne zaman değiştirdiğini izleyin.
7. Onaylayın. Gizlilik ofisi onayından ve gerekli iş birimi onaylarından geçirin.
8. Yayınlayın veya yürütün. Şablonu denetim izi ile üretimde uygulayın.

### İndeks

| Dosya | Amaç | Madde dayanağı |
|-------|------|-----------------|
| `privacy-notice.md` | Üç aydınlatma metni: müşteri/web, çalışan, CCTV | Md. 12-14 |
| `consent-form.md` | Üç açık rıza formu: pazarlama, üçüncü ülke aktarımı, profil oluşturma | Md. 4(11), 7, 9, 22, 49 |
| `ropa.csv` | İki dilli başlıklar ve örnek satırlarla ROPA şablonu | Md. 30 |
| `retention-policy.md` | Tam saklama ve imha politikası | Md. 5(1)(e), 17 |
| `breach-notification.md` | Madde 33 bildirim formu + iç triyaj | Md. 33-34 |
| `dsr-response.md` | Madde 15-22 başına iki dilli yanıt mektupları | Md. 12-22 |
| `dpa.md` | Madde 28 DPA tam şablonu | Md. 28 |
| `confidentiality-undertaking.md` | Çalışan/yüklenici/stajyer gizlilik taahhüdü | Md. 28(3)(b), 29, 32(4) |
| `training-tracker.md` | Eğitim katılımı ve müfredat izleme | Md. 39(1)(b) |
| `dpia-form.md` | Madde 35 VKDM tam formu | Md. 35-36 |
| `lia-form.md` | Meşru Menfaat Değerlendirmesi | Md. 6(1)(f) |

### Adlandırma kuralları

- Şablonlar arasında veri akışlarının tutarlı kalması için şablonlarınızda tam alan etiketlerini kullanın (örn. işleme faaliyeti adı ROPA, VKDM, saklama takviminde aynı şekilde görünür).
- Sürüm numaralarını her şablon örneğinin üstünde görünür tutun.
- İki dilli olduğunda, İngilizceyi önce ve Türkçeyi ayraç altında yerleştirin veya paralel sütunlar kullanın.

### Yaygın tuzaklar

- Yalnızca kolay bulduğunuz alanları doldurmak ve geri kalanı boş bırakmak — her alan yanıtlanmalı veya gerekçe ile "geçerli değil" olarak işaretlenmelidir.
- Yargı bölgesini yeniden doğrulamadan başka bir projeden şablon kopyalamak.
- Şablonları "kur ve unut" gibi ele almak — özellikle büyük düzenleyici değişiklik sonrası periyodik tazeleme gerektirirler.

### Kalite kriterleri

Tamamlanmış bir şablon yalnızca şu durumlarda kabul edilebilir:

1. Uyguladığı belirli madde(leri) atıf yapar.
2. Tarihli ve sürüm kontrollüdür.
3. Tanımlanmış bir sahibi vardır.
4. İlgili paydaşlara erişilebilir.
5. En az bir kez hukuk/DPO tarafından incelenmiştir.
6. Mevcut ROPA gerçeğini yansıtır (yetim şablon yok).

### Çapraz referans matrisi

| Operasyon | Gerekli şablonlar |
|-----------|-------------------|
| Yeni web sitesi başlatma | privacy-notice (müşteri), consent-form (çerez/pazarlama), ropa, lia-form (meşru menfaat ise) |
| Yeni çalışan oryantasyonu | privacy-notice (çalışan), confidentiality-undertaking, training-tracker |
| Yeni SaaS tedarikçisi (işleyen) | dpa, ropa güncellemesi, muhtemelen dpia |
| Yeni yüksek riskli işleme | dpia, lia (uygulanırsa), ropa, privacy-notice |
| Kişisel veri ihlali | breach-notification + triyaj, etkilenen talepler varsa muhtemelen dsr-response |
| İlgili kişi talebi | dsr-response, iç günlük |
| Yeni üçüncü ülke aktarımı | dpa, consent-form (üçüncü ülke), TIA, ropa |

### Bakım

Şablonlar yıllık veya maddi hukuki değişiklikte gözden geçirilir. Sürümler kaydedilir. Eski sürümler kanıt için arşivlenir (örn. şikayet anında yürürlükte olan aydınlatma metni sürümü).
