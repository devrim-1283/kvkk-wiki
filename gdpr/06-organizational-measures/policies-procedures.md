---
title:
  en: "Policies and Procedures - Hierarchy, Lifecycle, Annual Review"
  tr: "Politikalar ve Prosedürler - Hiyerarşi, Yaşam Döngüsü, Yıllık İnceleme"
section: "06-organizational-measures"
document_type: "policy_framework"
control_id: "ORG-POL-01"
owner:
  primary: "DPO"
  secondary: "CISO, General Counsel"
review_cycle: "annual"
last_review: "2026-05-08"
next_review: "2027-05-08"
classification: "Internal"
language: ["en", "tr"]
references:
  - "GDPR Art. 5(2), 24, 25, 32, 88"
  - "ISO/IEC 27001:2022 clause 5.2; ISO/IEC 27002:2022 controls 5.1, 5.2, 5.4"
  - "ISO/IEC 27701:2019"
  - "NIST CSF 2.0 GV.PO"
---

## English

# Policies and Procedures

## 1. Purpose

GDPR Article 24(2) requires that, "where proportionate", the controller
implement appropriate data protection policies. ISO/IEC 27001 clause 5.2
requires a top management approved information security policy. This
document establishes the policy hierarchy, lifecycle and ownership model.

## 2. Policy Hierarchy

The hierarchy isolates intent (top), procedure (middle) and operating
detail (bottom):

```
Tier 1 - Apex Statements (Board approved)
    Privacy Policy (external)
    Information Security Policy

Tier 2 - Functional Policies (Executive approved)
    Access Management Policy
    Encryption and Cryptographic Key Management Policy
    Backup and Recovery Policy
    Vendor Management Policy
    BYOD / MDM Policy
    Clean Desk and Clean Screen Policy
    Cookie Policy (external)
    Marketing and Direct Communications Policy
    Employee Privacy Notice (internal-facing)
    CCTV / Visual Monitoring Notice
    Acceptable Use Policy
    Data Classification and Handling Policy
    Records Retention Schedule
    DPIA Procedure
    Incident Response Plan

Tier 3 - Standards and Guidelines (Owner approved)
    Cryptographic Standard
    Logging Standard
    Network Standard
    Secure Coding Standard
    Patch Management Standard

Tier 4 - Procedures and Work Instructions
    Operational runbooks
    Step-by-step guides
    Templates (DPA, DPIA, breach notification, DSR response)
```

## 3. Mandatory Document Set

The minimum policy set for the controller:

| Document | Audience | Owner | Lawful Basis Anchor |
|----------|----------|-------|----------------------|
| Privacy Policy | External | DPO | Art. 13, 14 |
| Information Security Policy | Internal | CISO | Art. 32 |
| Access Management Policy | Internal | CISO | Art. 32 |
| Encryption Policy | Internal | CISO | Art. 32(1)(a) |
| Backup and Recovery Policy | Internal | CISO | Art. 32(1)(c) |
| Vendor Management Policy | Internal | DPO + CISO + Procurement | Art. 28 |
| BYOD / MDM Policy | Internal | CISO + HR | Art. 5(1)(f), 88 |
| Clean Desk / Screen Policy | Internal | CISO | Art. 5(1)(f) |
| Cookie Policy | External | DPO + Marketing | ePrivacy + GDPR |
| Marketing and Direct Communications Policy | Internal | DPO + Marketing | Art. 6(1), 21 |
| Employee Privacy Notice | Internal | DPO + HR | Art. 13, 88 |
| CCTV / Visual Monitoring Notice | External (signage) + Internal | DPO + Facilities | Art. 13, 35 |
| Acceptable Use Policy | Internal | CISO + HR | Art. 32, 88 |
| Data Classification and Handling Policy | Internal | DPO + CISO | Art. 5, 32 |
| Records Retention Schedule | Internal + DPA-disclosed | DPO + Records | Art. 5(1)(e) |
| DPIA Procedure | Internal | DPO | Art. 35 |
| Incident Response Plan | Internal | CISO + DPO | Art. 33, 34 |

External documents (privacy notice, cookie policy, CCTV notice) appear in
`03-transparency-consent/`.

## 4. Document Anatomy

Every policy uses a common header:

- Title.
- Owner (named role, not individual).
- Approver (named role).
- Effective date.
- Version.
- Last review.
- Next review.
- Distribution list / classification.
- Scope.
- Definitions.
- Roles and responsibilities.
- Policy statements.
- Procedures (or links to Tier-3 / Tier-4).
- Exceptions process.
- Enforcement and consequences.
- Related documents.
- Cross-mapping (GDPR, ISO, NIST).

## 5. Lifecycle

### 5.1 Initiation
- Triggered by: regulatory change, audit finding, incident lessons learned,
  new processing activity, technology change, periodic review.
- Drafted by the policy owner with input from impacted stakeholders.

### 5.2 Consultation
- Privacy Office reviews data protection implications.
- Legal reviews regulatory and contractual implications.
- Impacted business unit leaders sign off.
- Works council / employee representatives consulted where Article 88 or
  national law requires.

### 5.3 Approval
- Tier 1: Board.
- Tier 2: Executive committee or relevant C-level.
- Tier 3-4: Domain owner.

### 5.4 Publication
- Internal portal with searchable index.
- Acknowledgement workflow for Tier-1 / Tier-2 by all employees.
- Targeted notice for changes affecting specific roles.
- Translation into operating languages (TR / EN baseline).

### 5.5 Review
- Annual minimum, or sooner on:
  - Material change to processing.
  - Audit / DPA finding.
  - Major incident.
  - New regulation, EDPB / DPA guidance, court decision (Schrems-style).
- Review log retained as evidence.

### 5.6 Retirement
- Superseded versions archived for at least 6 years.
- Cross-references updated.

## 6. Exceptions

- Time-bound (max 12 months without re-review).
- Documented with: requester, business need, alternative controls, residual
  risk, approver.
- Reviewed by the policy owner and (for high-risk) DPO and CISO.
- Tracked in the exceptions register; expired exceptions removed.

## 7. Acknowledgement and Awareness

- All employees acknowledge:
  - Acceptable Use Policy.
  - Information Security Policy.
  - Confidentiality Undertaking (`confidentiality-undertaking.md`).
  - Employee Privacy Notice.
- Acknowledgement renewed on material change and at least every 24 months.
- Records retained for 7 years post-employment.

Awareness through `training.md` reinforces policy content.

## 8. Compliance and Enforcement

- Internal audit (`internal-audit.md`) samples policy compliance annually.
- Disciplinary process referenced for material breach.
- Workforce processing logs (`05-technical-measures/logging.md`) feed
  monitoring within Article 88 boundaries.
- Whistleblowing channel for suspected violations protected against
  retaliation per applicable law.

## 9. Records

For each policy version, the following are retained:

- Approved final document.
- Change log (what changed, why, by whom).
- Consultation record.
- Approval evidence (e-signature, board minute reference).
- Distribution / acknowledgement evidence.

Retention: 6 years after retirement of the version, longer if any law
requires.

## 10. Mapping

| Requirement | GDPR | ISO 27001/2:2022 | NIST CSF 2.0 |
|-------------|------|------------------|--------------|
| Apex policy | Art. 24(2) | 5.2 (27001), 5.1 (27002) | GV.PO-1 |
| Topic-specific policies | Art. 24(2) | 5.1 | GV.PO-1 |
| Roles | Art. 24, 37 | 5.2, 5.3 | GV.RR |
| Review cycle | Art. 24(1) | 5.1 | GV.PO-1 |

## 11. Related Documents

- `training.md` - awareness programme.
- `vendor-management.md` - vendor and processor controls.
- `dpia.md` - DPIA procedure.
- `internal-audit.md` - assurance over policies.
- `confidentiality-undertaking.md` - workforce binding.

---

## Türkçe

# Politikalar ve Prosedürler

## 1. Amaç

GDPR Madde 24(2), "orantılı olduğu yerde" kontrolörün uygun veri koruma
politikalarını uygulamasını gerektirir. ISO/IEC 27001 madde 5.2, üst yönetim
onaylı bir bilgi güvenliği politikası gerektirir. Bu belge politika
hiyerarşisini, yaşam döngüsünü ve sahiplik modelini belirler.

## 2. Politika Hiyerarşisi

Hiyerarşi niyeti (üst), prosedürü (orta) ve işletim ayrıntısını (alt)
ayırır:

```
Katman 1 - Apex Beyanları (Yönetim Kurulu onaylı)
    Gizlilik Politikası (dış)
    Bilgi Güvenliği Politikası

Katman 2 - İşlevsel Politikalar (Yönetim onaylı)
    Erişim Yönetimi Politikası
    Şifreleme ve Kriptografik Anahtar Yönetimi Politikası
    Yedekleme ve Geri Yükleme Politikası
    Tedarikçi Yönetimi Politikası
    BYOD / MDM Politikası
    Temiz Masa ve Temiz Ekran Politikası
    Çerez Politikası (dış)
    Pazarlama ve Doğrudan İletişim Politikası
    Çalışan Gizlilik Bildirimi (iç paydaşa yönelik)
    CCTV / Görsel İzleme Bildirimi
    Kabul Edilebilir Kullanım Politikası
    Veri Sınıflandırma ve İşleme Politikası
    Kayıt Saklama Programı
    VKD Prosedürü
    Olay Müdahale Planı

Katman 3 - Standartlar ve Kılavuzlar (Sahip onaylı)
    Kriptografik Standart
    Loglama Standardı
    Ağ Standardı
    Güvenli Kodlama Standardı
    Yama Yönetimi Standardı

Katman 4 - Prosedürler ve İş Talimatları
    Operasyonel runbook'lar
    Adım adım rehberler
    Şablonlar (DPA, VKD, ihlal bildirimi, DSR yanıtı)
```

## 3. Zorunlu Belge Seti

Kontrolör için asgari politika seti:

| Belge | Hedef Kitle | Sahip | Yasal Dayanak |
|-------|-------------|-------|----------------|
| Gizlilik Politikası | Dış | DPO | Md. 13, 14 |
| Bilgi Güvenliği Politikası | İç | CISO | Md. 32 |
| Erişim Yönetimi Politikası | İç | CISO | Md. 32 |
| Şifreleme Politikası | İç | CISO | Md. 32(1)(a) |
| Yedekleme ve Geri Yükleme Politikası | İç | CISO | Md. 32(1)(c) |
| Tedarikçi Yönetimi Politikası | İç | DPO + CISO + Tedarik | Md. 28 |
| BYOD / MDM Politikası | İç | CISO + İK | Md. 5(1)(f), 88 |
| Temiz Masa / Ekran Politikası | İç | CISO | Md. 5(1)(f) |
| Çerez Politikası | Dış | DPO + Pazarlama | ePrivacy + GDPR |
| Pazarlama ve Doğrudan İletişim Politikası | İç | DPO + Pazarlama | Md. 6(1), 21 |
| Çalışan Gizlilik Bildirimi | İç | DPO + İK | Md. 13, 88 |
| CCTV / Görsel İzleme Bildirimi | Dış (tabela) + İç | DPO + Tesisler | Md. 13, 35 |
| Kabul Edilebilir Kullanım Politikası | İç | CISO + İK | Md. 32, 88 |
| Veri Sınıflandırma ve İşleme Politikası | İç | DPO + CISO | Md. 5, 32 |
| Kayıt Saklama Programı | İç + DPA-açıklamalı | DPO + Kayıtlar | Md. 5(1)(e) |
| VKD Prosedürü | İç | DPO | Md. 35 |
| Olay Müdahale Planı | İç | CISO + DPO | Md. 33, 34 |

Dış belgeler (gizlilik bildirimi, çerez politikası, CCTV bildirimi)
`03-transparency-consent/` içinde görünür.

## 4. Belge Anatomisi

Her politika ortak bir başlık kullanır:

- Başlık.
- Sahip (bireyin değil, adlandırılmış rol).
- Onaylayan (adlandırılmış rol).
- Yürürlük tarihi.
- Sürüm.
- Son inceleme.
- Sonraki inceleme.
- Dağıtım listesi / sınıflandırma.
- Kapsam.
- Tanımlar.
- Roller ve sorumluluklar.
- Politika beyanları.
- Prosedürler (veya Katman-3 / Katman-4'e bağlantılar).
- İstisnalar süreci.
- Uygulama ve sonuçlar.
- İlgili belgeler.
- Çapraz eşleme (GDPR, ISO, NIST).

## 5. Yaşam Döngüsü

### 5.1 Başlatma
- Tetikleyici: düzenleyici değişiklik, denetim bulgusu, olay öğrenilenleri,
  yeni işleme etkinliği, teknoloji değişikliği, periyodik inceleme.
- Etkilenen paydaşlardan girdi ile politika sahibi tarafından taslaklandı.

### 5.2 Danışma
- Gizlilik Ofisi veri koruma etkilerini inceler.
- Hukuk düzenleyici ve sözleşmesel etkileri inceler.
- Etkilenen iş birimi liderleri onaylar.
- Madde 88 veya ulusal hukukun gerektirdiği yerde işyeri konseyi / çalışan
  temsilcileri ile istişare edilir.

### 5.3 Onay
- Katman 1: Yönetim Kurulu.
- Katman 2: Yürütme komitesi veya ilgili C seviyesi.
- Katman 3-4: Alan sahibi.

### 5.4 Yayım
- Aranabilir indeks ile dahili portal.
- Tüm çalışanlar için Katman-1 / Katman-2 onay iş akışı.
- Belirli rolleri etkileyen değişiklikler için hedeflenmiş bildirim.
- İşletim dillerine çeviri (TR / EN temel).

### 5.5 İnceleme
- Asgari yıllık veya daha erken:
  - İşlemede maddi değişiklik.
  - Denetim / DPA bulgusu.
  - Büyük olay.
  - Yeni düzenleme, EDPB / DPA rehberi, mahkeme kararı (Schrems tarzı).
- İnceleme logu kanıt olarak saklanır.

### 5.6 Emeklilik
- Üzerine geçilen sürümler en az 6 yıl arşivlenir.
- Çapraz referanslar güncellenir.

## 6. İstisnalar

- Süreye bağlı (yeniden inceleme olmadan azami 12 ay).
- Şunlarla belgelenir: talep eden, iş gereksinimi, alternatif kontroller,
  kalan risk, onaylayan.
- Politika sahibi ve (yüksek risk için) DPO ve CISO tarafından incelenir.
- İstisnalar kayıt defterinde izlenir; süresi dolmuş istisnalar kaldırılır.

## 7. Onay ve Farkındalık

- Tüm çalışanlar şunları onaylar:
  - Kabul Edilebilir Kullanım Politikası.
  - Bilgi Güvenliği Politikası.
  - Gizlilik Taahhütnamesi (`confidentiality-undertaking.md`).
  - Çalışan Gizlilik Bildirimi.
- Onay maddi değişiklikte ve en az 24 ayda bir yenilenir.
- Kayıtlar iş ilişkisi sonrası 7 yıl saklanır.

`training.md` üzerinden farkındalık politika içeriğini pekiştirir.

## 8. Uyumluluk ve Uygulama

- İç denetim (`internal-audit.md`) politika uyumluluğunu yıllık örnekler.
- Maddi ihlal için disiplin süreci referans alınır.
- İş gücü işleme logları (`05-technical-measures/logging.md`) Madde 88
  sınırları içinde izlemeyi besler.
- Şüpheli ihlaller için ihbar kanalı, geçerli hukuk uyarınca misillemeye
  karşı korunur.

## 9. Kayıtlar

Her politika sürümü için şunlar saklanır:

- Onaylanmış nihai belge.
- Değişiklik logu (ne değişti, neden, kim tarafından).
- Danışma kaydı.
- Onay kanıtı (e-imza, yönetim kurulu tutanak referansı).
- Dağıtım / onay kanıtı.

Saklama: sürüm emekliye ayrıldıktan sonra 6 yıl, herhangi bir hukuk daha
uzun gerektiriyorsa daha uzun.

## 10. Eşleme

| Gereklilik | GDPR | ISO 27001/2:2022 | NIST CSF 2.0 |
|------------|------|------------------|--------------|
| Apex politika | Md. 24(2) | 5.2 (27001), 5.1 (27002) | GV.PO-1 |
| Konuya özel politikalar | Md. 24(2) | 5.1 | GV.PO-1 |
| Roller | Md. 24, 37 | 5.2, 5.3 | GV.RR |
| İnceleme döngüsü | Md. 24(1) | 5.1 | GV.PO-1 |

## 11. İlgili Belgeler

- `training.md` - farkındalık programı.
- `vendor-management.md` - tedarikçi ve işleyici kontrolleri.
- `dpia.md` - VKD prosedürü.
- `internal-audit.md` - politikalar üzerinde güvence.
- `confidentiality-undertaking.md` - iş gücü bağlama.
