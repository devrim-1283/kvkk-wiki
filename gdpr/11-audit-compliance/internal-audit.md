---
title:
  en: "Internal Audit of the GDPR Program"
  tr: "GDPR Programi Ic Denetimi"
section: "11-audit-compliance"
owner: "Internal Audit / DPO"
version: "1.0"
last_review: "2026-05-08"
next_review: "2026-11-08"
classification: "Internal"
languages: ["en", "tr"]
keywords:
  en: ["internal audit", "three lines of defense", "test procedures", "CAPA"]
  tr: ["ic denetim", "uc savunma hatti", "test prosedurleri", "DOEP"]
---

## English

# Internal Audit of the GDPR Program

This procedure governs how the third line of defense — internal audit — independently assures that the GDPR program achieves accountability under Article 5(2). It complements the second-line monitoring carried out by the DPO and privacy office. The procedure aligns with the IIA Three Lines Model and with internal audit standards (IPPF).

### Audit charter alignment

Internal audit's GDPR mandate is documented in the audit charter approved by the audit committee. Key clauses:

- Independence from DPO function (DPO is a second-line role; auditor is third-line).
- Unfettered access to all processing activities, records, systems, premises, and personnel.
- Right to engage external specialists (privacy lawyers, technical auditors).
- Direct reporting line to the audit committee with administrative reporting to the CEO.

### Annual audit plan

The plan is risk-based, refreshed annually, and reviewed quarterly for residual capacity:

#### Step 1 — Risk universe

The risk universe enumerates every auditable unit. For GDPR purposes, units typically include:

- Each high-risk processing activity from the ROPA.
- Each major IT system holding personal data.
- Each major processor (Article 28).
- Each cross-border transfer cluster.
- Cross-cutting controls: DSR, breach response, training, transparency.

#### Step 2 — Risk scoring

Inherent risk score per unit considers:

- Data category sensitivity (special categories under Article 9, criminal data Article 10, child data, financial data).
- Volume of data subjects.
- Cross-border transfer footprint.
- Complexity (number of processors, sub-processors, integrations).
- Recent change (new system, new processor, M&A).
- Past findings.
- Public visibility (consumer-facing, regulator focus).

Score scale 1-5; combine via weighted formula tailored to the organization. Multiply by control effectiveness to get residual risk.

#### Step 3 — Plan composition

Aim to cover top-quartile units annually, second-quartile every two years, third-quartile every three years, fourth-quartile by exception.

#### Step 4 — Resource planning

Budget audit-days per audit. Reserve 15-20% capacity for ad-hoc incident-driven engagements.

### Sample test procedures

#### Test set A — ROPA accuracy and completeness

| Step | Procedure | Evidence |
|------|-----------|----------|
| A1 | Reconcile ROPA records to system inventory; identify gaps | Reconciliation worksheet |
| A2 | Sample 20 records; trace fields to source (legal basis, retention, transfers) | Walkthrough notes, screenshots |
| A3 | Verify retention period matches retention policy and legal requirements | Policy ref + screenshot |
| A4 | Verify transfer chain: country, instrument, TIA, supplementary measures | TIA file, SCC pack |
| A5 | Confirm process owner attestation date within 12 months | Attestation log |

#### Test set B — DSR operations

| Step | Procedure | Evidence |
|------|-----------|----------|
| B1 | Sample 30 closed DSRs across types (access, erasure, restriction, portability, objection) | Tickets |
| B2 | Verify identity verification proportionate; not excessive | Verification artefact |
| B3 | Verify response within one month or extension justified per Article 12(3) | Timestamps |
| B4 | Verify access response includes all categories of data; compare to ROPA | Export sample, ROPA |
| B5 | Verify erasure executed across primary, replica, backup (per retention) | Erasure certificate |
| B6 | Verify objection cases under Article 21 reviewed for compelling legitimate grounds | Decision memo |

#### Test set C — Consent

| Step | Procedure | Evidence |
|------|-----------|----------|
| C1 | Inspect cookie banner UX on three top devices; verify reject equally prominent | Screenshots |
| C2 | Sample marketing consents; verify granular, informed, freely given (Article 7) | Consent record |
| C3 | Verify withdrawal mechanism equally easy as giving consent | Walkthrough |
| C4 | Inspect consent log; verify immutability and content (timestamp, identifier, purpose, scope, version of notice) | DB query output |

#### Test set D — Article 32 technical measures

| Step | Procedure | Evidence |
|------|-----------|----------|
| D1 | Verify encryption in transit on customer-facing endpoints (TLS 1.2+; preferred 1.3) | Scan output |
| D2 | Verify at-rest encryption for databases and storage holding personal data | Configuration export |
| D3 | Verify MFA on all admin and remote access accounts; recertification dates | IAM export |
| D4 | Inspect access logs for sample assets; verify retention and access controls on logs themselves | Log sample |
| D5 | Confirm vulnerability scan cadence and remediation SLA adherence | Scan reports |
| D6 | Verify backup cycle, restore tests, and personal data scope within backups | Restore test report |

#### Test set E — Breach response

| Step | Procedure | Evidence |
|------|-----------|----------|
| E1 | Sample incidents from past 12 months; verify classification consistent with risk methodology | Incident records |
| E2 | For notifiable breaches, verify SA notification within 72h; if delayed, gather Article 33(1) reasoning | SA submission |
| E3 | For high-risk breaches, verify Article 34 data subject notification | Notification copy |
| E4 | Verify breach register completeness per Article 33(5) | Register export |
| E5 | Verify post-incident lessons learned action items closed | CAPA log |

#### Test set F — Vendor and processor

| Step | Procedure | Evidence |
|------|-----------|----------|
| F1 | Sample 15 processors across risk tiers; verify Article 28 DPA executed and current | DPA copies |
| F2 | Verify due diligence questionnaire completed pre-contract | Vendor file |
| F3 | Verify sub-processor list current and notification mechanism functions | Vendor portal |
| F4 | For high-risk processors, verify audit right exercised within stated cadence | Audit report or attestation |
| F5 | For non-EEA processors, verify transfer instrument and TIA on file | TIA file |

#### Test set G — Transparency

| Step | Procedure | Evidence |
|------|-----------|----------|
| G1 | Inspect privacy notices for required Article 13/14 elements | Notice text |
| G2 | Verify multilingual coverage matches data subject footprint | Notice variants |
| G3 | Test readability at grade level; layered structure | Readability tool output |
| G4 | Verify just-in-time notices at collection touchpoints | UX walkthrough |

#### Test set H — Training

| Step | Procedure | Evidence |
|------|-----------|----------|
| H1 | Verify completion rates against KPI threshold | LMS export |
| H2 | Sample training content for accuracy and currency | Course materials |
| H3 | For high-risk roles, verify role-specific modules | LMS pathway |

### Finding classification

| Severity | Definition | Closure target |
|----------|-----------|---------------|
| Critical | Imminent regulatory exposure, ongoing breach risk, or legal-basis gap on high-volume processing | 30 days |
| High | Significant control failure with material risk; legal exposure on lower-volume processing | 60 days |
| Medium | Process inefficiency, partial control gap, documentation gap | 90 days |
| Low | Minor improvement, style or housekeeping | 180 days or aligned with next review |

Each finding includes: condition, criteria (article reference, EDPB guideline, internal policy), cause, consequence, recommendation, management response, owner, target date.

### CAPA — Corrective and Preventive Action

Each finding triggers a CAPA entry. Entries track:

- Action description (corrective immediate, preventive systemic).
- Owner and accountable executive.
- Due date.
- Verification approach (re-test, evidence sample, walkthrough).
- Closure status with auditor sign-off.

CAPA dashboard shared with audit committee monthly. Aging CAPAs auto-escalate per `kpi-metrics.md` open-finding-age thresholds.

### Reporting

Each engagement produces:

1. Executive summary (1 page).
2. Detailed findings register.
3. Management response.
4. Recommendation closure plan.

Reports are issued to the audit committee and DPO. Sensitive findings (e.g. unreported breaches) follow whistleblower escalation routes if obstructed.

### Continuous auditing

Beyond cyclical audits, internal audit applies continuous auditing techniques:

- Automated reconciliation of ROPA to system inventory monthly.
- Sample-based DSR aging report weekly.
- Anomaly detection on access logs for sensitive datasets.

### Independence safeguards

- DPO does not direct internal audit work.
- Internal audit may engage external counsel directly.
- Whistleblower channel exists for staff to escalate concerns about audit independence.

---

## Türkçe

# GDPR Programı İç Denetimi

Bu prosedür, üçüncü savunma hattının — iç denetimin — GDPR programının Madde 5(2) hesap verebilirliğini sağladığını bağımsız olarak nasıl güvence altına alacağını yönetir. DPO ve gizlilik ofisinin yürüttüğü ikinci hat izlemeyi tamamlar. IIA Üç Hat Modeli ve iç denetim standartları (IPPF) ile uyumludur.

### Denetim tüzüğü hizalaması

İç denetimin GDPR yetkisi, denetim komitesi tarafından onaylanan denetim tüzüğünde belgelidir. Anahtar maddeler:

- DPO işlevinden bağımsızlık (DPO ikinci hat rolüdür; denetçi üçüncü hattır).
- Tüm işleme faaliyetlerine, kayıtlara, sistemlere, tesislere ve personele engelsiz erişim.
- Dış uzmanlarla (gizlilik avukatları, teknik denetçiler) çalışma hakkı.
- Denetim komitesine doğrudan raporlama hattı; CEO'ya idari raporlama.

### Yıllık denetim planı

Plan risk bazlıdır, yıllık yenilenir ve kalan kapasite için çeyreklik gözden geçirilir:

#### Adım 1 — Risk evreni

Risk evreni denetlenebilir her birimi sıralar. GDPR amaçları için tipik birimler:

- ROPA'dan her yüksek riskli işleme faaliyeti.
- Kişisel veri tutan her büyük BT sistemi.
- Her büyük işleyen (Madde 28).
- Her sınır ötesi aktarım kümesi.
- Çapraz kesen kontroller: DSR, ihlal yanıtı, eğitim, şeffaflık.

#### Adım 2 — Risk skorlama

Birim başına içsel risk skoru şunları dikkate alır:

- Veri kategorisi hassasiyeti (Madde 9 özel kategoriler, Madde 10 ceza verisi, çocuk verisi, finansal veri).
- Veri sahibi hacmi.
- Sınır ötesi aktarım ayak izi.
- Karmaşıklık (işleyen, alt işleyen, entegrasyon sayısı).
- Yakın değişiklik (yeni sistem, yeni işleyen, B&S).
- Geçmiş bulgular.
- Kamu görünürlüğü (tüketiciye yönelik, düzenleyici odağı).

1-5 ölçeği; organizasyona göre uyarlanmış ağırlıklı formülle birleştirin. Artık riski elde etmek için kontrol etkinliğiyle çarpın.

#### Adım 3 — Plan kompozisyonu

İlk çeyrek birimleri yıllık, ikinci çeyrek iki yılda bir, üçüncü çeyrek üç yılda bir, dördüncü çeyrek istisnai olarak kapsamayı hedefleyin.

#### Adım 4 — Kaynak planlama

Denetim başına denetim-gün bütçeleyin. Olay temelli ad-hoc çalışmalar için %15-20 kapasite ayırın.

### Örnek test prosedürleri

#### Test seti A — ROPA doğruluk ve eksiksizlik

| Adım | Prosedür | Kanıt |
|------|----------|-------|
| A1 | ROPA kayıtlarını sistem envanteri ile mutabakata getirin; boşlukları belirleyin | Mutabakat çalışma kâğıdı |
| A2 | 20 kayıt örnekleyin; alanları kaynağa kadar izleyin (hukuki dayanak, saklama, aktarımlar) | Tur notları, ekran görüntüleri |
| A3 | Saklama süresinin saklama politikası ve hukuki gereksinimlerle eşleştiğini doğrulayın | Politika ref + ekran görüntüsü |
| A4 | Aktarım zincirini doğrulayın: ülke, araç, TIA, ek tedbirler | TIA dosyası, SCC paketi |
| A5 | Süreç sahibi onay tarihinin 12 ay içinde olduğunu doğrulayın | Onay kaydı |

#### Test seti B — DSR operasyonları

| Adım | Prosedür | Kanıt |
|------|----------|-------|
| B1 | Tür bazında 30 kapatılmış DSR örnekleyin (erişim, silme, kısıtlama, taşınabilirlik, itiraz) | Talepler |
| B2 | Kimlik doğrulamanın orantılı olduğunu; aşırı olmadığını doğrulayın | Doğrulama eseri |
| B3 | Bir ay içinde yanıt veya Madde 12(3) uzatma gerekçesini doğrulayın | Zaman damgaları |
| B4 | Erişim yanıtının tüm veri kategorilerini içerdiğini ROPA ile karşılaştırarak doğrulayın | Dışa aktarma örneği, ROPA |
| B5 | Silmenin birincil, çoğaltma ve yedekte (saklamaya göre) yürütüldüğünü doğrulayın | Silme sertifikası |
| B6 | Madde 21 itiraz vakalarının zorlayıcı meşru gerekçeler için gözden geçirildiğini doğrulayın | Karar memorandumu |

#### Test seti C — Açık rıza

| Adım | Prosedür | Kanıt |
|------|----------|-------|
| C1 | Çerez bantı UX'ini üç önde gelen cihazda inceleyin; reddetmenin eşit derecede belirgin olduğunu doğrulayın | Ekran görüntüleri |
| C2 | Pazarlama rızalarını örnekleyin; ayrıntılı, bilgilendirilmiş, özgürce verilmiş olduğunu (Madde 7) doğrulayın | Rıza kaydı |
| C3 | Geri çekme mekanizmasının rıza vermek kadar kolay olduğunu doğrulayın | Tur |
| C4 | Rıza günlüğünü inceleyin; değiştirilemezlik ve içeriği (zaman damgası, tanımlayıcı, amaç, kapsam, metin sürümü) doğrulayın | DB sorgu çıktısı |

#### Test seti D — Madde 32 teknik tedbirler

| Adım | Prosedür | Kanıt |
|------|----------|-------|
| D1 | Müşteriye yönelik uç noktalarda aktarımda şifrelemeyi doğrulayın (TLS 1.2+; tercih edilen 1.3) | Tarama çıktısı |
| D2 | Kişisel veri tutan veritabanları ve depoda depolama şifrelemesini doğrulayın | Konfigürasyon dışa aktarımı |
| D3 | Tüm yönetici ve uzaktan erişim hesaplarında ÇFD'yi; yeniden onay tarihlerini doğrulayın | IAM dışa aktarımı |
| D4 | Örnek varlıklar için erişim günlüklerini inceleyin; günlüklerin kendisinde saklama ve erişim kontrollerini doğrulayın | Günlük örneği |
| D5 | Zafiyet tarama sıklığı ve düzeltme SLA uyumunu onaylayın | Tarama raporları |
| D6 | Yedek döngüsü, geri yükleme testleri ve yedeklerdeki kişisel veri kapsamını doğrulayın | Geri yükleme testi raporu |

#### Test seti E — İhlal yanıtı

| Adım | Prosedür | Kanıt |
|------|----------|-------|
| E1 | Son 12 ayın olaylarını örnekleyin; sınıflandırmanın risk metodolojisiyle tutarlı olduğunu doğrulayın | Olay kayıtları |
| E2 | Bildirilebilir ihlaller için 72 saat içinde SA bildirimini doğrulayın; gecikme varsa Madde 33(1) gerekçesini toplayın | SA bildirimi |
| E3 | Yüksek riskli ihlaller için Madde 34 ilgili kişi bildirimini doğrulayın | Bildirim kopyası |
| E4 | İhlal kayıt defterinin Madde 33(5) gereksinimine göre eksiksizliğini doğrulayın | Kayıt defteri dışa aktarımı |
| E5 | Olay sonrası çıkarılan derslerin eylem öğelerinin kapatıldığını doğrulayın | DÖEP günlüğü |

#### Test seti F — Tedarikçi ve işleyen

| Adım | Prosedür | Kanıt |
|------|----------|-------|
| F1 | Risk kademelerinde 15 işleyen örnekleyin; Madde 28 DPA'nın imzalı ve güncel olduğunu doğrulayın | DPA kopyaları |
| F2 | Sözleşme öncesi durum tespiti anketinin tamamlandığını doğrulayın | Tedarikçi dosyası |
| F3 | Alt işleyen listesinin güncel ve bildirim mekanizmasının çalıştığını doğrulayın | Tedarikçi portalı |
| F4 | Yüksek riskli işleyenler için belirtilen sıklıkta denetim hakkının kullanıldığını doğrulayın | Denetim raporu veya beyanı |
| F5 | AEA dışı işleyenler için aktarım aracını ve dosyada TIA'yı doğrulayın | TIA dosyası |

#### Test seti G — Şeffaflık

| Adım | Prosedür | Kanıt |
|------|----------|-------|
| G1 | Aydınlatma metinlerini Madde 13/14 gerekli unsurlar açısından inceleyin | Metin |
| G2 | Çok dilli kapsamın veri sahibi ayak izi ile eşleştiğini doğrulayın | Metin varyantları |
| G3 | Sınıf seviyesinde okunabilirliği test edin; katmanlı yapı | Okunabilirlik aracı çıktısı |
| G4 | Toplama temas noktalarında tam zamanında bildirimleri doğrulayın | UX turu |

#### Test seti H — Eğitim

| Adım | Prosedür | Kanıt |
|------|----------|-------|
| H1 | KPI eşiğine karşı tamamlanma oranlarını doğrulayın | LMS dışa aktarımı |
| H2 | Eğitim içeriğini doğruluk ve güncellik için örnekleyin | Kurs materyalleri |
| H3 | Yüksek riskli roller için role özgü modülleri doğrulayın | LMS yolu |

### Bulgu sınıflandırma

| Ciddiyet | Tanım | Kapanış hedefi |
|----------|-------|----------------|
| Kritik | Acil düzenleyici risk, devam eden ihlal riski veya yüksek hacimli işlemede hukuki dayanak boşluğu | 30 gün |
| Yüksek | Maddi riskli önemli kontrol arızası; düşük hacimli işlemede hukuki risk | 60 gün |
| Orta | Süreç verimsizliği, kısmi kontrol boşluğu, belge boşluğu | 90 gün |
| Düşük | Küçük iyileştirme, stil veya düzenleme | 180 gün veya bir sonraki gözden geçirmeye uygun |

Her bulgu şunları içerir: durum, kriter (madde referansı, EDPB kılavuzu, iç politika), neden, sonuç, öneri, yönetim yanıtı, sahip, hedef tarih.

### DÖEP — Düzeltici ve Önleyici Eylem

Her bulgu bir DÖEP girdisi tetikler. Girdiler şunları izler:

- Eylem açıklaması (acil düzeltici, sistemik önleyici).
- Sahip ve sorumlu yönetici.
- Vade tarihi.
- Doğrulama yaklaşımı (yeniden test, kanıt örneği, tur).
- Denetçi onayı ile kapanış durumu.

DÖEP panosu denetim komitesiyle aylık paylaşılır. Yaşlanan DÖEP'ler `kpi-metrics.md` açık-bulgu-yaşı eşiklerine göre otomatik eskale olur.

### Raporlama

Her görevlendirme şunu üretir:

1. Yönetici özeti (1 sayfa).
2. Ayrıntılı bulgu kayıt defteri.
3. Yönetim yanıtı.
4. Öneri kapanış planı.

Raporlar denetim komitesine ve DPO'ya verilir. Hassas bulgular (örn. raporlanmamış ihlaller) engellenirse muhbir eskalasyon yollarını izler.

### Sürekli denetim

Döngüsel denetimlerin ötesinde, iç denetim sürekli denetim teknikleri uygular:

- ROPA-sistem envanteri otomatik mutabakatı aylık.
- Örneklem temelli DSR yaşlandırma raporu haftalık.
- Hassas veri kümeleri için erişim günlüklerinde anomali tespiti.

### Bağımsızlık güvenceleri

- DPO iç denetim çalışmasını yönlendirmez.
- İç denetim doğrudan dış danışman tutabilir.
- Personelin denetim bağımsızlığı endişelerini eskale etmesi için muhbir kanalı vardır.
