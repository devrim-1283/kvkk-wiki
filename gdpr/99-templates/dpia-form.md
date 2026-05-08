---
title:
  en: "Data Protection Impact Assessment — Article 35 Form"
  tr: "Veri Koruma Etki Degerlendirmesi — Madde 35 Formu"
section: "99-templates"
owner: "DPO"
version: "1.0"
last_review: "2026-05-08"
next_review: "2026-11-08"
classification: "Internal"
languages: ["en", "tr"]
keywords:
  en: ["DPIA", "Article 35", "Article 36", "high risk", "prior consultation"]
  tr: ["VKDM", "Madde 35", "Madde 36", "yuksek risk", "on danisma"]
---

## English

# DPIA — Data Protection Impact Assessment

This DPIA template implements **Article 35** GDPR and follows EDPB / WP248 rev.01 nine criteria for triggering DPIA. Where residual risk remains high, the controller consults the supervisory authority under **Article 36**.

### When to perform

A DPIA is mandatory when processing is likely to result in a high risk to rights and freedoms of natural persons, in particular:

- Article 35(3)(a) — systematic and extensive evaluation of personal aspects based on automated processing, including profiling, with legal or similarly significant effects.
- Article 35(3)(b) — processing on a large scale of special categories of data (Article 9) or criminal data (Article 10).
- Article 35(3)(c) — systematic monitoring of a publicly accessible area on a large scale.
- Plus EDPB / WP248 nine criteria — at least two indicate likely high risk.
- Plus national lists of mandatory DPIA cases issued by individual SAs.

A DPIA may also be voluntary as a good-practice measure for any processing.

### DPIA register reference

| Field | Value |
|-------|-------|
| DPIA ID | [DPIA-YYYY-NNN] |
| Date opened | [date] |
| Status | [draft / review / approved / superseded] |
| Owner | [process owner name and role] |
| DPO reviewer | [name] |
| Linked ROPA entries | [refs] |
| Approval date | [date] |
| Next review trigger | [date or event] |

---

## Section 1 — Description of processing

### 1.1 Purpose

[Plain-language description of why the processing is being undertaken.]

### 1.2 Nature

[Description of what is happening: collection, storage, transmission, profiling, automated decision-making.]

### 1.3 Scope

| Item | Detail |
|------|--------|
| Data subjects | [categories and approximate numbers] |
| Personal data categories | [list] |
| Special category data | [Y/N + categories] |
| Criminal data | [Y/N] |
| Children involved | [Y/N + age band] |
| Geographic scope | [countries] |
| Duration | [duration] |
| Frequency / volume | [continuous, batches] |

### 1.4 Context

[Relationship with data subjects (customer, employee, child, vulnerable group, public). Their reasonable expectations. Sector context. Past concerns or complaints.]

### 1.5 Stakeholders

| Role | Person |
|------|--------|
| Process owner | |
| Technical lead | |
| Legal | |
| DPO | |
| Information security | |
| External processors involved | |
| Joint controllers | |

### 1.6 Data flow diagram (ASCII)

Provide a data flow showing collection, storage, processing steps, recipients, transfers. Example:

```
[Data subject] --(form)--> [Web app] --(API)--> [App server] --(SQL)--> [Database EU]
                                                            \-(metrics)-> [Analytics SaaS US] (SCC + supplementary)
[App server] --(webhook)--> [Email provider] --(SMTP)--> [Recipient device]
[Database] --(backup)--> [Backup vault EU] --(encryption)
[Database] --(replica)--> [DR site EU]
```

Replace with the actual flow. Note pseudonymisation, encryption boundaries, and access groups.

---

## Section 2 — Necessity and proportionality

### 2.1 Lawful basis

For each purpose:

| Purpose | Article 6(1) basis | Article 9(2) basis if applicable | LIA reference if 6(1)(f) | Notes |
|---------|--------------------|----------------------------------|--------------------------|-------|
| | | | | |

### 2.2 Necessity

Is the processing necessary for the purpose? Could the purpose reasonably be achieved with less data, less identifiable data, or no personal data at all?

| Question | Answer |
|----------|--------|
| Why this volume? | |
| Why this granularity? | |
| Why this retention? | |
| Less-intrusive alternative considered? | |

### 2.3 Proportionality

| Question | Answer |
|----------|--------|
| Are the means proportionate to the legitimate aim? | |
| Are recipients limited to those who need access? | |
| Are international transfers limited and safeguarded? | |
| Are data subjects informed (Articles 13-14)? | |
| Are rights (Articles 15-22) supported in practice? | |
| Is consent (where used) freely given, specific, informed, unambiguous? | |
| Is processing aligned with data subject reasonable expectations? | |

---

## Section 3 — Risks to rights and freedoms

### 3.1 Risk identification

For each risk, document likelihood (low/medium/high) and severity (low/medium/high):

| # | Risk | Affected rights | Likelihood | Severity | Inherent risk |
|---|------|----------------|------------|----------|---------------|
| R1 | Unauthorised access to data due to weak access control | Confidentiality | M | H | High |
| R2 | Inaccurate data leading to wrong decisions | Right to rectification, right not to be subject to automated decision | L | H | Medium |
| R3 | Unwanted profiling | Right to object, right not to be subject to automated decision | M | M | Medium |
| R4 | Re-identification of pseudonymised data | Right to data protection | L | H | Medium |
| R5 | International transfer without supplementary measures | Confidentiality, lawful basis | L | H | Medium |
| R6 | Excess retention | Right to erasure, storage limitation | M | M | Medium |
| R7 | Data subject not aware of processing | Right to information | M | M | Medium |
| R8 | Children processed without parental consent | Right of the child | L | H | Medium |
| R9 | [Add specific to context] | | | | |

### 3.2 Risk scoring

Use a matrix to combine likelihood and severity:

```
              Low impact   Medium impact   High impact
High likelihood  Medium       High            Critical
Medium           Low          Medium          High
Low              Low          Low             Medium
```

---

## Section 4 — Safeguards and mitigations

For each risk, list mitigations and the resulting residual risk.

| # | Risk | Mitigation | Owner | Date | Residual risk |
|---|------|------------|-------|------|---------------|
| R1 | Unauthorised access | MFA on admin, RBAC, log monitoring, encryption at rest | Security | | Low |
| R2 | Inaccurate data | Validation on input, periodic cleansing, easy correction process | Operations | | Low |
| R3 | Unwanted profiling | Opt-out, transparency, human review on impactful decisions | Marketing | | Low |
| R4 | Re-identification | Strong key separation, pseudonymisation review (EDPB 01/2025) | Security | | Low |
| R5 | International transfer | SCCs 2021/914 + supplementary measures + TIA | Privacy office | | Low |
| R6 | Excess retention | Automated purge per retention policy | Operations | | Low |
| R7 | Lack of awareness | Layered notice, just-in-time prompt, plain-language summary | Privacy office | | Low |
| R8 | Children | Age verification, parental consent flow under Article 8 | Product | | Low |
| R9 | | | | | |

### 4.1 Privacy by design and by default (Article 25)

- [ ] Data minimisation in design.
- [ ] Pseudonymisation considered.
- [ ] Default settings privacy-friendly.
- [ ] Necessary access only.

### 4.2 Security (Article 32)

- [ ] Encryption in transit.
- [ ] Encryption at rest.
- [ ] MFA on admin.
- [ ] Logging and monitoring.
- [ ] Backup and DR with restore tests.
- [ ] Vulnerability management.
- [ ] Pen-test schedule.

---

## Section 5 — Consultation

### 5.1 Internal consultation

| Stakeholder | Date | Outcome |
|-------------|------|---------|
| DPO | | |
| Legal | | |
| Security | | |
| Engineering | | |
| Process owner | | |

### 5.2 Data subject consultation (Article 35(9))

Where appropriate, consult representatives of data subjects (Article 35(9)). Document method (survey, focus group), participants, outcome, and any changes made. If consultation not done, justify (e.g. confidentiality of business plan; consultation undermined the purpose).

| Approach | Outcome |
|----------|---------|
| | |

### 5.3 Joint controllers / processors

Where there are joint controllers (Article 26) or processors (Article 28), document their input and contribution to the DPIA.

---

## Section 6 — DPO opinion (Article 39(1)(c))

The DPO's opinion is recorded. The DPO may concur, concur with conditions, or disagree. Disagreement is escalated.

| Field | Value |
|-------|-------|
| DPO name | |
| Date | |
| Opinion | [concur / concur with conditions / disagree] |
| Conditions | [list] |
| Reasoning | [text] |

---

## Section 7 — Residual risk and Article 36 prior consultation

If residual risk is high, the controller must consult the SA before processing under Article 36.

| Field | Value |
|-------|-------|
| Overall residual risk | [low / medium / high] |
| Article 36 consultation triggered? | [Y/N] |
| If Y, SA consulted | [SA name] |
| Date submitted | |
| SA response | |
| SA reference | |

---

## Section 8 — Decision and approval

| Field | Value |
|-------|-------|
| Decision | [proceed / proceed with conditions / do not proceed] |
| Conditions | [list] |
| Sign-off — process owner | [name, date] |
| Sign-off — DPO (advisory) | [name, date] |
| Sign-off — accountable executive | [name, date] |

---

## Section 9 — Review and monitoring

| Field | Value |
|-------|-------|
| Review trigger | [date / event such as material change] |
| KPIs to monitor risk | [list] |
| Owner | |
| Next scheduled review | |

The DPIA is a living document. Review when scope, data flows, processors, transfer instruments, or risk profile change. ROPA links must be maintained.

---

## Türkçe

# VKDM — Veri Koruma Etki Değerlendirmesi

Bu VKDM şablonu **GDPR Madde 35**'i uygular ve VKDM tetiklemek için EDPB / WP248 rev.01 dokuz kriterini izler. Artık risk yüksek kalırsa, veri sorumlusu **Madde 36** altında denetim otoritesine danışır.

### Ne zaman yapılmalı

İşleme aşağıdaki gibi gerçek kişilerin hak ve özgürlüklerine yüksek risk oluşturma olasılığı taşıdığında VKDM zorunludur:

- Madde 35(3)(a) — hukuki veya benzer önemli etkili profil oluşturma dahil otomatik işleme dayalı kişisel hususların sistematik ve kapsamlı değerlendirmesi.
- Madde 35(3)(b) — özel kategori (Madde 9) veya ceza verisinin (Madde 10) büyük ölçekli işlenmesi.
- Madde 35(3)(c) — kamuya açık bir alanın büyük ölçekli sistematik izlenmesi.
- Artı EDPB / WP248 dokuz kriter — en az ikisi yüksek riski gösterir.
- Artı bireysel SA'lar tarafından yayınlanan zorunlu VKDM vakalarının ulusal listeleri.

Herhangi bir işleme için iyi uygulama tedbiri olarak gönüllü olarak da yapılabilir.

### VKDM kayıt defteri referansı

| Alan | Değer |
|------|-------|
| VKDM ID | [VKDM-YYYY-NNN] |
| Açılış tarihi | [tarih] |
| Durum | [taslak / inceleme / onaylandı / yerini aldı] |
| Sahip | [süreç sahibi adı ve rolü] |
| DPO inceleyici | [ad] |
| Bağlı ROPA girdileri | [referanslar] |
| Onay tarihi | [tarih] |
| Sonraki inceleme tetikleyicisi | [tarih veya olay] |

---

## Bölüm 1 — İşlemenin tanımı

### 1.1 Amaç

[İşlemenin neden yapıldığının sade dil açıklaması.]

### 1.2 Nitelik

[Ne olduğunun tanımı: toplama, depolama, iletim, profil oluşturma, otomatik karar verme.]

### 1.3 Kapsam

| Öğe | Ayrıntı |
|-----|---------|
| İlgili kişiler | [kategoriler ve yaklaşık sayılar] |
| Kişisel veri kategorileri | [liste] |
| Özel kategori veri | [E/H + kategoriler] |
| Ceza verisi | [E/H] |
| Çocuklar dahil | [E/H + yaş bandı] |
| Coğrafi kapsam | [ülkeler] |
| Süre | [süre] |
| Sıklık / hacim | [sürekli, gruplar] |

### 1.4 Bağlam

[İlgili kişilerle ilişki (müşteri, çalışan, çocuk, savunmasız grup, kamu). Makul beklentileri. Sektör bağlamı. Geçmiş endişeler veya şikayetler.]

### 1.5 Paydaşlar

| Rol | Kişi |
|-----|------|
| Süreç sahibi | |
| Teknik lider | |
| Hukuk | |
| DPO | |
| Bilgi güvenliği | |
| Dahil olan dış işleyenler | |
| Müşterek veri sorumluları | |

### 1.6 Veri akış diyagramı (ASCII)

Toplama, depolama, işleme adımları, alıcılar, aktarımları gösteren bir veri akışı sağlayın. Örnek:

```
[Ilgili kisi] --(form)--> [Web uyg] --(API)--> [Uyg sunucu] --(SQL)--> [Veritabani AB]
                                                         \-(metrikler)-> [Analitik SaaS ABD] (SCC + ek)
[Uyg sunucu] --(webhook)--> [E-posta saglayici] --(SMTP)--> [Alici cihazi]
[Veritabani] --(yedek)--> [Yedek kasasi AB] --(sifreleme)
[Veritabani] --(coğaltma)--> [DR sitesi AB]
```

Gerçek akışla değiştirin. Takma adlaştırma, şifreleme sınırları ve erişim grupları belirtin.

---

## Bölüm 2 — Gereklilik ve orantılılık

### 2.1 Hukuki dayanak

Her amaç için:

| Amaç | Madde 6(1) dayanağı | Uygulanırsa Madde 9(2) dayanağı | 6(1)(f) ise MMD referansı | Notlar |
|------|---------------------|----------------------------------|---------------------------|--------|
| | | | | |

### 2.2 Gereklilik

İşleme amaç için gerekli mi? Amaç makul olarak daha az veriyle, daha az tanımlanabilir veriyle veya hiç kişisel veri olmadan elde edilebilir mi?

| Soru | Yanıt |
|------|-------|
| Neden bu hacim? | |
| Neden bu ayrıntı düzeyi? | |
| Neden bu saklama? | |
| Daha az müdahaleci alternatif değerlendirildi mi? | |

### 2.3 Orantılılık

| Soru | Yanıt |
|------|-------|
| Araçlar meşru amaçla orantılı mı? | |
| Alıcılar erişime ihtiyaç duyanlarla sınırlı mı? | |
| Uluslararası aktarımlar sınırlı ve güvenli mi? | |
| İlgili kişiler bilgilendirildi mi (Madde 13-14)? | |
| Haklar (Madde 15-22) pratikte destekleniyor mu? | |
| Açık rıza (kullanıldığında) özgürce verilmiş, belirli, bilgilendirilmiş, açık mı? | |
| İşleme ilgili kişinin makul beklentileriyle hizalı mı? | |

---

## Bölüm 3 — Hak ve özgürlüklere riskler

### 3.1 Risk tanımlama

Her risk için olasılık (düşük/orta/yüksek) ve ciddiyet (düşük/orta/yüksek) belgeleyin:

| # | Risk | Etkilenen haklar | Olasılık | Ciddiyet | İçsel risk |
|---|------|-------------------|----------|----------|------------|
| R1 | Zayıf erişim kontrolü nedeniyle yetkisiz veri erişimi | Gizlilik | O | Y | Yüksek |
| R2 | Yanlış kararlara yol açan yanlış veri | Düzeltme hakkı, otomatik karara tabi olmama hakkı | D | Y | Orta |
| R3 | İstenmeyen profil oluşturma | İtiraz hakkı, otomatik karara tabi olmama hakkı | O | O | Orta |
| R4 | Takma adlaştırılmış verinin yeniden tanımlanması | Veri koruma hakkı | D | Y | Orta |
| R5 | Ek tedbirler olmadan uluslararası aktarım | Gizlilik, hukuki dayanak | D | Y | Orta |
| R6 | Aşırı saklama | Silme hakkı, depolama sınırlaması | O | O | Orta |
| R7 | İlgili kişi işlemenin farkında değil | Bilgi alma hakkı | O | O | Orta |
| R8 | Çocuklar ebeveyn rızası olmadan işleniyor | Çocuğun hakkı | D | Y | Orta |
| R9 | [Bağlama özgü ekle] | | | | |

### 3.2 Risk skorlama

Olasılık ve ciddiyeti birleştirmek için bir matris kullanın:

```
                  Düşük etki   Orta etki      Yüksek etki
Yüksek olasılık     Orta         Yüksek         Kritik
Orta                Düşük        Orta           Yüksek
Düşük               Düşük        Düşük          Orta
```

---

## Bölüm 4 — Güvenceler ve azaltmalar

Her risk için azaltmaları ve sonuçtaki artık riski listeleyin.

| # | Risk | Azaltma | Sahip | Tarih | Artık risk |
|---|------|---------|-------|-------|------------|
| R1 | Yetkisiz erişim | Yöneticide ÇFD, RBAC, günlük izleme, depolamada şifreleme | Güvenlik | | Düşük |
| R2 | Yanlış veri | Girişte doğrulama, periyodik temizleme, kolay düzeltme süreci | Operasyonlar | | Düşük |
| R3 | İstenmeyen profil oluşturma | Opt-out, şeffaflık, etkili kararlarda insan incelemesi | Pazarlama | | Düşük |
| R4 | Yeniden tanımlama | Güçlü anahtar ayrımı, takma adlaştırma incelemesi (EDPB 01/2025) | Güvenlik | | Düşük |
| R5 | Uluslararası aktarım | SCC 2021/914 + ek tedbirler + TIA | Gizlilik ofisi | | Düşük |
| R6 | Aşırı saklama | Saklama politikasına göre otomatik silme | Operasyonlar | | Düşük |
| R7 | Farkındalık eksikliği | Katmanlı metin, tam zamanında uyarı, sade dil özeti | Gizlilik ofisi | | Düşük |
| R8 | Çocuklar | Yaş doğrulama, Madde 8 altında ebeveyn rıza akışı | Ürün | | Düşük |
| R9 | | | | | |

### 4.1 Tasarımda ve varsayılan gizlilik (Madde 25)

- [ ] Tasarımda veri minimizasyonu.
- [ ] Takma adlaştırma değerlendirildi.
- [ ] Varsayılan ayarlar gizlilik dostu.
- [ ] Yalnızca gerekli erişim.

### 4.2 Güvenlik (Madde 32)

- [ ] Aktarımda şifreleme.
- [ ] Depolamada şifreleme.
- [ ] Yöneticide ÇFD.
- [ ] Günlükleme ve izleme.
- [ ] Geri yükleme testleriyle yedek ve DR.
- [ ] Zafiyet yönetimi.
- [ ] Pen-test takvimi.

---

## Bölüm 5 — Danışma

### 5.1 İç danışma

| Paydaş | Tarih | Sonuç |
|--------|-------|-------|
| DPO | | |
| Hukuk | | |
| Güvenlik | | |
| Mühendislik | | |
| Süreç sahibi | | |

### 5.2 İlgili kişi danışması (Madde 35(9))

Uygun olduğunda, ilgili kişilerin temsilcilerine danışın (Madde 35(9)). Yöntemi (anket, odak grubu), katılımcıları, sonucu ve yapılan değişiklikleri belgeleyin. Danışma yapılmadıysa, gerekçelendirin (örn. iş planının gizliliği; danışma amacı zayıflattı).

| Yaklaşım | Sonuç |
|----------|-------|
| | |

### 5.3 Müşterek veri sorumluları / işleyenler

Müşterek veri sorumluları (Madde 26) veya işleyenler (Madde 28) varsa, VKDM'ye girdilerini ve katkılarını belgeleyin.

---

## Bölüm 6 — DPO görüşü (Madde 39(1)(c))

DPO'nun görüşü kaydedilir. DPO katılabilir, koşullarla katılabilir veya katılmayabilir. Anlaşmazlık eskale edilir.

| Alan | Değer |
|------|-------|
| DPO adı | |
| Tarih | |
| Görüş | [katılır / koşullarla katılır / katılmaz] |
| Koşullar | [liste] |
| Gerekçe | [metin] |

---

## Bölüm 7 — Artık risk ve Madde 36 ön danışma

Artık risk yüksekse, veri sorumlusu Madde 36 altında işlemeden önce SA'ya danışmalıdır.

| Alan | Değer |
|------|-------|
| Genel artık risk | [düşük / orta / yüksek] |
| Madde 36 danışma tetiklendi mi? | [E/H] |
| E ise, danışılan SA | [SA adı] |
| Sunum tarihi | |
| SA yanıtı | |
| SA referansı | |

---

## Bölüm 8 — Karar ve onay

| Alan | Değer |
|------|-------|
| Karar | [devam et / koşullarla devam et / devam etme] |
| Koşullar | [liste] |
| Onay — süreç sahibi | [ad, tarih] |
| Onay — DPO (danışmanlık) | [ad, tarih] |
| Onay — sorumlu yönetici | [ad, tarih] |

---

## Bölüm 9 — Gözden geçirme ve izleme

| Alan | Değer |
|------|-------|
| Gözden geçirme tetikleyicisi | [tarih / maddi değişiklik gibi olay] |
| Riski izlemek için KPI'lar | [liste] |
| Sahip | |
| Sonraki planlı gözden geçirme | |

VKDM yaşayan bir belgedir. Kapsam, veri akışları, işleyenler, aktarım araçları veya risk profili değiştiğinde gözden geçirin. ROPA bağlantıları sürdürülmelidir.
