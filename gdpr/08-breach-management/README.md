---
title:
  en: "Breach Management — Section Index"
  tr: "Veri İhlali Yönetimi — Bölüm Dizini"
section: "08-breach-management"
owner: "DPO Office / CISO"
classification: "Internal"
version: "1.0"
last_review: "2026-05-08"
next_review: "2027-05-08"
language: ["en", "tr"]
references:
  - "GDPR Art. 33 — Notification to supervisory authority"
  - "GDPR Art. 34 — Communication to data subject"
  - "GDPR Recitals 85–88"
  - "EDPB Guidelines 9/2022 on personal data breach notification under GDPR"
  - "EDPB Guidelines 01/2021 — Examples regarding personal data breach notification"
  - "ENISA — Recommendations for a methodology of the assessment of severity of personal data breaches"
  - "NIST SP 800-61 Rev. 2 — Computer Security Incident Handling Guide"
  - "ISO/IEC 27035-1:2023 — Information security incident management"
---

## English

### Purpose

This section is the operational core of the controller's response to a personal data breach. It binds together the legal duties of GDPR Articles 33 and 34 with the operational lifecycle defined by NIST SP 800-61 and ISO/IEC 27035, and it tells every involved role exactly what to do, in what order, and within what clock.

A personal data breach is defined in Article 4(12) GDPR as a breach of security leading to the accidental or unlawful destruction, loss, alteration, unauthorised disclosure of, or access to, personal data. EDPB Guidelines 9/2022 reaffirm the three breach types established in WP250rev.01: confidentiality breach, integrity breach, and availability breach. A single event can fall in more than one category at once.

### Scope

The procedures in this section apply to:

1. All personal data processed by the controller, regardless of medium (digital, paper, verbal recording, biometric template, backup tape).
2. All processors and sub-processors handling personal data on behalf of the controller, who are bound by Article 28(3)(f) and 33(2) to notify the controller without undue delay.
3. All employees, contractors, interns, and third parties with access to systems containing personal data.
4. All operating environments — production, staging, development, disaster recovery, archive, off-site backup.

### How this section is organised

The seven documents in this folder are arranged in the order a real incident traverses them:

| File | Primary Question Answered | Audience |
|------|---------------------------|----------|
| `incident-response.md` | How do we operate during the event? | CSIRT, IT, security |
| `72-hour-notification.md` | Do we notify the supervisory authority, and how? | DPO, Legal |
| `data-subject-notification.md` | Do we tell affected individuals, and how? | DPO, Communications |
| `notification-form.md` | What goes in the actual notification? | DPO |
| `tabletop-exercises.md` | How do we stay ready? | CSIRT, exec sponsors |
| `root-cause-analysis.md` | Why did this happen, and how do we close the gap? | Engineering, Process owners |

### Key definitions

- **Breach awareness (Recital 87, EDPB 9/2022 §31)**: a controller is "aware" when it has a reasonable degree of certainty that a security incident has occurred that has led to personal data being compromised. The 72-hour clock starts at this moment, not at the moment of the event itself, and not at the moment of full investigation.
- **High risk to rights and freedoms**: triggers the data subject notification obligation under Article 34. ENISA severity scoring and EDPB Annex examples are the reference frame.
- **Lead supervisory authority (Article 56)**: the SA of the main establishment for cross-border processing. The one-stop-shop applies; the lead SA receives the primary notification and coordinates with concerned SAs.

### Roles and responsibilities (RACI summary)

| Activity | DPO | CISO/CSIRT lead | Legal | Engineering | Communications | Executive sponsor |
|----------|-----|-----------------|-------|-------------|----------------|-------------------|
| Detection and triage | C | R/A | I | R | I | I |
| Severity scoring (ENISA) | A | R | C | C | I | I |
| 72-hour notification draft | R/A | C | C | I | I | I |
| Data subject communication | R | C | C | I | R | A |
| Containment and eradication | I | R/A | I | R | I | I |
| Lessons learned and CAPA | C | R | I | R/A | I | I |

R = Responsible, A = Accountable, C = Consulted, I = Informed.

### Cross-references

- Section `05-technical-measures` for security controls whose failure produces breaches.
- Section `06-organizational-measures` for training and access management.
- Section `09-data-subject-rights` for handling rights requests that arise after a breach.
- Section `12-legal-archive` for retention of breach files.
- Section `11-audit-compliance` for evidencing breach readiness during audits.

### Quality bar

Every breach record must be traceable, contemporaneous, and bilingual where the supervisory authority requires Turkish or where affected data subjects are Turkish residents. No breach is too small to log; the Article 33(5) internal register is mandatory regardless of notification outcome.

---

## Türkçe

### Amaç

Bu bölüm, kişisel veri ihlaline karşı veri sorumlusunun operasyonel müdahale çekirdeğidir. GDPR'nin 33 ve 34. maddelerindeki yasal yükümlülükleri NIST SP 800-61 ve ISO/IEC 27035 tarafından tanımlanan operasyonel yaşam döngüsüyle birleştirir ve her ilgili role ne yapacağını, hangi sırayla ve hangi süre içinde yapacağını tam olarak söyler.

Kişisel veri ihlali, GDPR Madde 4(12)'de kişisel verilerin kazara veya hukuka aykırı olarak yok edilmesine, kaybedilmesine, değiştirilmesine, yetkisiz olarak ifşa edilmesine veya erişilmesine yol açan bir güvenlik ihlali olarak tanımlanır. EDPB 9/2022 Rehberi, WP250rev.01'de belirlenen üç ihlal türünü yeniden teyit eder: gizlilik ihlali, bütünlük ihlali ve erişilebilirlik ihlali. Tek bir olay aynı anda birden fazla kategoriye girebilir.

### Kapsam

Bu bölümdeki prosedürler aşağıdakilere uygulanır:

1. Veri sorumlusu tarafından işlenen tüm kişisel veriler — ortamı ne olursa olsun (dijital, kâğıt, sözlü kayıt, biyometrik şablon, yedek kaset).
2. Veri sorumlusu adına kişisel veri işleyen ve Madde 28(3)(f) ile 33(2) uyarınca veri sorumlusunu gecikmeksizin bilgilendirmekle yükümlü olan tüm veri işleyenler ve alt işleyenler.
3. Kişisel veri içeren sistemlere erişimi olan tüm çalışanlar, yükleniciler, stajyerler ve üçüncü taraflar.
4. Tüm işletim ortamları — üretim, staging, geliştirme, felaket kurtarma, arşiv, ofis dışı yedekleme.

### Bu bölüm nasıl düzenlenmiştir

Bu klasördeki yedi belge, gerçek bir olayın bunları ziyaret ettiği sırayla düzenlenmiştir:

| Dosya | Cevap Verdiği Birincil Soru | Hedef Kitle |
|-------|----------------------------|-------------|
| `incident-response.md` | Olay sırasında nasıl çalışırız? | CSIRT, BT, güvenlik |
| `72-hour-notification.md` | Denetim makamına bildirir miyiz, nasıl? | VKK Sorumlusu, Hukuk |
| `data-subject-notification.md` | İlgili kişilere haber veriyor muyuz, nasıl? | VKK Sorumlusu, İletişim |
| `notification-form.md` | Asıl bildirimde ne yer alır? | VKK Sorumlusu |
| `tabletop-exercises.md` | Hazırlığı nasıl koruruz? | CSIRT, sponsor |
| `root-cause-analysis.md` | Bu neden oldu, açığı nasıl kaparız? | Mühendislik, Süreç sahipleri |

### Temel tanımlar

- **İhlalden haberdar olma (Resital 87, EDPB 9/2022 §31)**: Veri sorumlusu, kişisel verilerin tehlikeye atılmasına yol açan bir güvenlik olayının meydana geldiğine dair makul bir kesinlik derecesine sahip olduğunda "haberdar" olur. 72 saatlik süre, olayın kendi anında değil, tam soruşturmanın anında değil, bu anda başlar.
- **Hak ve özgürlüklere yüksek risk**: Madde 34 kapsamındaki ilgili kişiye bildirim yükümlülüğünü tetikler. ENISA önem puanlaması ve EDPB Ek örnekleri referans çerçevesidir.
- **Baş denetim makamı (Madde 56)**: Sınır ötesi işleme için ana yerleşim yerinin denetim makamı. Tek pencere ilkesi uygulanır; baş DM birincil bildirimi alır ve ilgili DM'lerle koordine eder.

### Rol ve sorumluluklar (RACI özeti)

| Faaliyet | VKK | CISO/CSIRT | Hukuk | Mühendislik | İletişim | Yönetici sponsor |
|----------|-----|------------|-------|-------------|----------|------------------|
| Tespit ve triyaj | C | R/A | I | R | I | I |
| Önem puanlama (ENISA) | A | R | C | C | I | I |
| 72 saat bildirim taslağı | R/A | C | C | I | I | I |
| İlgili kişi iletişimi | R | C | C | I | R | A |
| Kontrol altına alma ve giderme | I | R/A | I | R | I | I |
| Çıkarılan dersler ve CAPA | C | R | I | R/A | I | I |

R = Sorumlu, A = Hesap veren, C = Danışılan, I = Bilgilendirilen.

### Çapraz referanslar

- İhlallerin doğduğu güvenlik kontrolleri için `05-technical-measures` bölümü.
- Eğitim ve erişim yönetimi için `06-organizational-measures` bölümü.
- İhlalden sonra ortaya çıkan hak taleplerinin yönetimi için `09-data-subject-rights` bölümü.
- İhlal dosyalarının saklanması için `12-legal-archive` bölümü.
- Denetimlerde ihlal hazırlığının kanıtlanması için `11-audit-compliance` bölümü.

### Kalite çıtası

Her ihlal kaydı izlenebilir, eş zamanlı ve denetim makamının Türkçeyi gerektirdiği veya etkilenen ilgili kişilerin Türkiye'de ikamet ettiği durumlarda iki dilli olmalıdır. Hiçbir ihlal kayda alınmayacak kadar küçük değildir; Madde 33(5) iç kayıt zorunluluğu, bildirim sonucu ne olursa olsun geçerlidir.
