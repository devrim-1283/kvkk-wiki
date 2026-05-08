---
title:
  en: "Legal Monitoring and Change-Impact Procedure"
  tr: "Hukuki Izleme ve Degisiklik Etki Proseduru"
section: "12-legal-archive"
owner: "Legal / DPO"
version: "1.0"
last_review: "2026-05-08"
next_review: "2026-11-08"
classification: "Internal"
languages: ["en", "tr"]
keywords:
  en: ["monitoring", "change impact", "version control", "EDPB", "OJ"]
  tr: ["izleme", "degisiklik etki", "surum kontrol", "EDPB", "OJ"]
---

## English

# Legal Monitoring and Change-Impact Procedure

This procedure ensures the GDPR program identifies, evaluates, and integrates legal change in a controlled, auditable way.

### Sources to monitor

#### Primary EU sources

| Source | What to monitor | Frequency |
|--------|----------------|-----------|
| Official Journal of the EU (OJ) — series L and C | Regulations, directives, decisions including adequacy decisions, SCC updates | Weekly |
| EDPB website (edpb.europa.eu) | Guidelines, opinions, recommendations, binding decisions | Weekly |
| European Commission DG JUST | Adequacy assessments, model contracts, evaluation reports | Monthly |
| EUR-Lex | Search across EU instruments | As needed |
| EDPS website (edps.europa.eu) | EDPS opinions on EU-institutional processing | Monthly |

#### Court sources

| Source | What to monitor | Frequency |
|--------|----------------|-----------|
| CJEU curia.europa.eu | New judgments, AG opinions, pending references | Weekly |
| ECHR hudoc.echr.coe.int | Article 8 ECHR cases relevant to data | Monthly |
| National constitutional courts | High-impact rulings | Monthly |

#### National sources (top SAs)

| SA | Site |
|----|------|
| France — CNIL | cnil.fr |
| Germany — BfDI + Länder DPAs | bfdi.bund.de + state sites |
| Italy — Garante | garanteprivacy.it |
| Spain — AEPD | aepd.es |
| Netherlands — AP | autoriteitpersoonsgegevens.nl |
| Ireland — DPC | dataprotection.ie |
| UK — ICO | ico.org.uk |
| Poland — UODO | uodo.gov.pl |

#### Adjacent regulators

| Regulator | What |
|-----------|------|
| ENISA | Technical guidance on Article 32 |
| ESMA, EBA, EIOPA | Financial services data |
| EMA | Pharmaceutical research data |
| FRA | Fundamental rights reports |
| ENISA / national CSIRTs | NIS2 incident guidance |

#### Industry and trade associations

- IAPP (Resource Centre).
- CIPL — Centre for Information Policy Leadership.
- Computer & Communications Industry Association (CCIA).
- Sectoral associations relevant to the controller.

### Monitoring cadence

| Cadence | Activity |
|---------|----------|
| Daily | Inbox alerts from monitoring services for keyword matches |
| Weekly | Review of OJ, EDPB news, CJEU judgments, top SA decisions |
| Monthly | Consolidated change log; review of EDPS, ECHR, national constitutional courts; industry reports |
| Quarterly | Comprehensive legal scan; update legal archive; refresh national derogations summary |
| Ad hoc | Major decision (e.g. CJEU), large fine, new regulation publication |

### Monitoring roles

| Role | Responsibility |
|------|---------------|
| DPO | Owns the monitoring program; ensures change impact analysis and routing |
| Privacy office team member | Performs weekly scan; logs entries |
| External counsel | Specialized monitoring (e.g. financial services, sectoral) |
| Legal | Provides interpretation of complex changes |
| Knowledge management | Maintains the archive and links |

### Change-impact analysis template

Each identified change is recorded with the following structured fields:

| Field | Content |
|-------|---------|
| ID | YYYY-NNN sequential |
| Date identified | Date |
| Source | URL or citation |
| Type | Regulation, directive, EDPB guideline, binding decision, CJEU judgment, SA decision, opinion |
| Title | Title of the instrument or decision |
| Summary | Two-paragraph plain-language summary |
| Articles affected | Map to GDPR articles or other instruments |
| Operational impact | What we must change (e.g. update notice, retrain staff, retire a control, deploy new control) |
| Wiki sections affected | List of files to update |
| Owner | Person responsible for action |
| Severity | Critical / High / Medium / Low / Informational |
| Target date | Date for action completion |
| Status | New / Assessed / In progress / Completed / Not applicable |
| Closure verification | How we confirm closure |
| Notes | Free text |

### Severity criteria

| Severity | Criteria |
|----------|----------|
| Critical | Mandatory new obligation with risk of substantial fine; requires immediate action |
| High | New interpretation tightens existing obligation; requires planned change |
| Medium | Soft-law guidance changes practice baseline |
| Low | Minor clarification or alignment opportunity |
| Informational | Background context, no operational change required |

### Distribution

Each change is communicated through a tiered approach:

| Audience | Format |
|----------|--------|
| DPO and privacy office | Full change record |
| Legal team | Full record + targeted commentary |
| Executive committee | Quarterly summary or ad hoc for Critical |
| Process owners | Direct notification when their process is affected |
| All staff | Newsletter for high-impact changes |
| Audit committee | Quarterly summary |

### Version control

This archive uses semantic versioning at the document level (1.0, 1.1, etc.). Each substantive change increments the minor version. Major rewrites increment the major version. Each change is logged in the document footer with date, author, and reason.

### Document footer pattern

```
Version | Date       | Author            | Changes
1.0     | 2026-05-08 | DPO Office        | Initial release
1.1     | YYYY-MM-DD | name              | summary
```

### Annual review

Once per year, the legal archive undergoes a comprehensive review:

1. Re-validate all article summaries against current text.
2. Re-validate all EDPB guideline statuses (some superseded).
3. Re-validate landmark judgments (some clarified or distinguished).
4. Refresh national derogation entries.
5. Assess whether new sister regulations require their own dedicated section.

### Integration with audit

Findings from monitoring feed into:

- ROPA — change records may trigger ROPA updates.
- DPIA register — new categories of high-risk processing may emerge.
- Training curriculum — new topics added.
- KPI thresholds — adjusted in light of regulatory expectation changes.
- Vendor management — new requirements rolled into DPAs.

### Worked example — CJEU judgment X published

1. Day 0 — judgment published. Privacy office team member logs entry.
2. Day 1-3 — DPO with legal counsel drafts plain-language summary and operational impact.
3. Day 7 — change impact assessed; Critical/High routed to executive committee.
4. Day 14 — owner assigns target date; CAPA opened if multi-month action required.
5. Day 30 — closure verification or progress report.

### Tools

The following tooling supports monitoring:

- RSS / email alerts from EDPB, CJEU, OJ, key SAs.
- Curated newsletters (IAPP Daily Dashboard, etc.).
- Internal change-impact tracker (spreadsheet or GRC tool).
- Knowledge base (this wiki) as the system of record.

### Quality checks

Quarterly the program manager spot-checks ten random changes to ensure:

- Source link still valid.
- Summary accurate.
- Owner identified.
- Target date set or completion logged.
- Wiki sections updated.

---

## Türkçe

# Hukuki İzleme ve Değişiklik Etki Prosedürü

Bu prosedür, GDPR programının hukuki değişikliği kontrollü, denetlenebilir bir şekilde tanımlamasını, değerlendirmesini ve entegre etmesini sağlar.

### İzlenecek kaynaklar

#### Birincil AB kaynakları

| Kaynak | İzlenecek | Sıklık |
|--------|-----------|--------|
| AB Resmi Gazetesi (OJ) — L ve C serisi | Yeterlilik kararları, SCC güncellemeleri dahil tüzükler, direktifler, kararlar | Haftalık |
| EDPB web sitesi (edpb.europa.eu) | Kılavuzlar, görüşler, tavsiyeler, bağlayıcı kararlar | Haftalık |
| Avrupa Komisyonu DG JUST | Yeterlilik değerlendirmeleri, model sözleşmeler, değerlendirme raporları | Aylık |
| EUR-Lex | AB araçlarında arama | Gerektikçe |
| EDPS web sitesi (edps.europa.eu) | AB-kurumsal işleme üzerine EDPS görüşleri | Aylık |

#### Mahkeme kaynakları

| Kaynak | İzlenecek | Sıklık |
|--------|-----------|--------|
| AAD curia.europa.eu | Yeni kararlar, HSY görüşleri, bekleyen sevkler | Haftalık |
| AİHM hudoc.echr.coe.int | Veriyle ilgili AİHS Madde 8 davaları | Aylık |
| Ulusal anayasa mahkemeleri | Yüksek etkili kararlar | Aylık |

#### Ulusal kaynaklar (en önemli SA'lar)

| SA | Site |
|----|------|
| Fransa — CNIL | cnil.fr |
| Almanya — BfDI + Länder DPA'ları | bfdi.bund.de + eyalet siteleri |
| İtalya — Garante | garanteprivacy.it |
| İspanya — AEPD | aepd.es |
| Hollanda — AP | autoriteitpersoonsgegevens.nl |
| İrlanda — DPC | dataprotection.ie |
| UK — ICO | ico.org.uk |
| Polonya — UODO | uodo.gov.pl |

#### Komşu düzenleyiciler

| Düzenleyici | Ne |
|-------------|-----|
| ENISA | Madde 32 üzerine teknik rehberlik |
| ESMA, EBA, EIOPA | Finansal hizmetler verisi |
| EMA | Farmasötik araştırma verisi |
| FRA | Temel haklar raporları |
| ENISA / ulusal CSIRT'ler | NIS2 olay rehberliği |

#### Sektör ve ticaret dernekleri

- IAPP (Kaynak Merkezi).
- CIPL — Bilgi Politikası Liderlik Merkezi.
- Bilgisayar ve İletişim Endüstrisi Derneği (CCIA).
- Veri sorumlusu için ilgili sektörel dernekler.

### İzleme sıklığı

| Sıklık | Faaliyet |
|--------|----------|
| Günlük | İzleme hizmetlerinden anahtar kelime eşleşmeleri için gelen kutusu uyarıları |
| Haftalık | OJ, EDPB haberleri, AAD kararları, en önemli SA kararlarının gözden geçirilmesi |
| Aylık | Konsolide değişiklik günlüğü; EDPS, AİHM, ulusal anayasa mahkemeleri gözden geçirme; sektör raporları |
| Çeyreklik | Kapsamlı hukuki tarama; hukuki arşivi güncelle; ulusal istisnalar özetini yenile |
| Ad hoc | Büyük karar (örn. AAD), büyük ceza, yeni tüzük yayını |

### İzleme rolleri

| Rol | Sorumluluk |
|-----|------------|
| DPO | İzleme programını sahiplenir; değişiklik etki analizi ve yönlendirmeyi sağlar |
| Gizlilik ofisi ekip üyesi | Haftalık taramayı yapar; girdileri kaydeder |
| Dış danışman | Uzmanlaşmış izleme (örn. finansal hizmetler, sektörel) |
| Hukuk | Karmaşık değişikliklerin yorumunu sağlar |
| Bilgi yönetimi | Arşivi ve bağlantıları korur |

### Değişiklik etki analizi şablonu

Her tanımlanmış değişiklik aşağıdaki yapılandırılmış alanlarla kaydedilir:

| Alan | İçerik |
|------|--------|
| ID | YYYY-NNN sıralı |
| Tanımlama tarihi | Tarih |
| Kaynak | URL veya atıf |
| Tür | Tüzük, direktif, EDPB kılavuzu, bağlayıcı karar, AAD kararı, SA kararı, görüş |
| Başlık | Aracın veya kararın başlığı |
| Özet | İki paragraflık sade dil özeti |
| Etkilenen maddeler | GDPR maddelerine veya diğer araçlara haritalama |
| Operasyonel etki | Neyi değiştirmemiz gerek (örn. metni güncelle, personeli yeniden eğit, bir kontrolü emekli et, yeni kontrol yerleştir) |
| Etkilenen wiki bölümleri | Güncellenecek dosya listesi |
| Sahip | Eylemden sorumlu kişi |
| Ciddiyet | Kritik / Yüksek / Orta / Düşük / Bilgilendirici |
| Hedef tarih | Eylem tamamlama tarihi |
| Durum | Yeni / Değerlendirildi / Devam ediyor / Tamamlandı / Geçerli değil |
| Kapanış doğrulama | Kapanışı nasıl teyit ederiz |
| Notlar | Serbest metin |

### Ciddiyet kriterleri

| Ciddiyet | Kriterler |
|----------|-----------|
| Kritik | Önemli ceza riskli zorunlu yeni yükümlülük; acil eylem gerektirir |
| Yüksek | Yeni yorum mevcut yükümlülüğü sıkılaştırır; planlı değişiklik gerektirir |
| Orta | Yumuşak hukuk rehberliği uygulama temel çizgisini değiştirir |
| Düşük | Küçük netleştirme veya hizalama fırsatı |
| Bilgilendirici | Arka plan bağlamı, operasyonel değişiklik gerekmez |

### Dağıtım

Her değişiklik kademeli yaklaşımla iletilir:

| Kitle | Format |
|-------|--------|
| DPO ve gizlilik ofisi | Tam değişiklik kaydı |
| Hukuk ekibi | Tam kayıt + hedefli yorum |
| Yürütme komitesi | Çeyreklik özet veya Kritik için ad hoc |
| Süreç sahipleri | Süreçleri etkilendiğinde doğrudan bildirim |
| Tüm personel | Yüksek etkili değişiklikler için bülten |
| Denetim komitesi | Çeyreklik özet |

### Sürüm kontrolü

Bu arşiv belge düzeyinde semantik sürümleme kullanır (1.0, 1.1 vb.). Her önemli değişiklik küçük sürümü artırır. Büyük yeniden yazımlar büyük sürümü artırır. Her değişiklik belge altbilgisinde tarih, yazar ve nedenle kaydedilir.

### Belge altbilgi deseni

```
Sürüm  | Tarih      | Yazar             | Değişiklikler
1.0    | 2026-05-08 | DPO Ofisi         | İlk yayın
1.1    | YYYY-AA-GG | ad                | özet
```

### Yıllık gözden geçirme

Yılda bir kez, hukuki arşiv kapsamlı bir gözden geçirmeden geçer:

1. Tüm madde özetlerini mevcut metne karşı yeniden doğrulayın.
2. Tüm EDPB kılavuz durumlarını yeniden doğrulayın (bazıları yerini almıştır).
3. Önemli kararları yeniden doğrulayın (bazıları netleştirilmiş veya ayrılmıştır).
4. Ulusal istisna girdilerini yenileyin.
5. Yeni kardeş tüzüklerin kendi özel bölümlerini gerektirip gerektirmediğini değerlendirin.

### Denetimle entegrasyon

İzleme bulguları şunlara beslenir:

- ROPA — değişiklik kayıtları ROPA güncellemelerini tetikleyebilir.
- VKDM kayıt defteri — yeni yüksek riskli işleme kategorileri ortaya çıkabilir.
- Eğitim müfredatı — yeni konular eklenir.
- KPI eşikleri — düzenleyici beklenti değişikliklerine göre ayarlanır.
- Tedarikçi yönetimi — DPA'lara yuvarlanan yeni gereksinimler.

### İşlenmiş örnek — AAD kararı X yayınlandı

1. Gün 0 — karar yayınlandı. Gizlilik ofisi ekip üyesi girdi kaydeder.
2. Gün 1-3 — DPO, hukuk danışmanıyla sade dil özeti ve operasyonel etki taslağı hazırlar.
3. Gün 7 — değişiklik etkisi değerlendirilir; Kritik/Yüksek yürütme komitesine yönlendirilir.
4. Gün 14 — sahip hedef tarih atar; çok aylı eylem gerekirse DÖEP açılır.
5. Gün 30 — kapanış doğrulama veya ilerleme raporu.

### Araçlar

Aşağıdaki araçlar izlemeyi destekler:

- EDPB, AAD, OJ, anahtar SA'lardan RSS / e-posta uyarıları.
- Düzenlenmiş bültenler (IAPP Daily Dashboard vb.).
- İç değişiklik etki izleyicisi (tablo veya GRC aracı).
- Kayıt sistemi olarak bilgi tabanı (bu wiki).

### Kalite kontrolleri

Çeyreklik, program yöneticisi şunları sağlamak için on rastgele değişikliği nokta kontrolü yapar:

- Kaynak bağlantısı hâlâ geçerli.
- Özet doğru.
- Sahip tanımlandı.
- Hedef tarih belirlendi veya tamamlanma kaydedildi.
- Wiki bölümleri güncellendi.
