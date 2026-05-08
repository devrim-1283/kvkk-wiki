---
title:
  en: "Cloud Services and Hyperscaler Risk"
  tr: "Bulut Hizmetleri ve Hyperscaler Riski"
section: "10-special-topics"
document_id: "ST-CLOUD-001"
owner: "DPO Office / Cloud Architecture / Procurement"
classification: "Internal"
version: "1.0"
last_review: "2026-05-08"
next_review: "2027-05-08"
language: ["en", "tr"]
references:
  - "GDPR Art. 28 — Processor"
  - "GDPR Art. 32 — Security"
  - "GDPR Art. 44–49 — International transfers"
  - "Schrems II (CJEU C-311/18)"
  - "EDPB Recommendations 01/2020 on supplementary measures (Schrems II)"
  - "EDPB Recommendations 02/2020 on the European Essential Guarantees"
  - "Standard Contractual Clauses Decision (EU) 2021/914"
  - "EU-US Data Privacy Framework (Adequacy Decision 2023/1795)"
  - "US CLOUD Act (2018)"
  - "FISA Section 702; Executive Order 12333"
  - "ISO/IEC 27017, 27018"
  - "ENISA Cloud Security Strategy and Procurement Guidance"
---

## English

### 1. Shared responsibility model

Cloud computing splits responsibility between the cloud provider (processor) and the customer (controller). The split varies by service model:

| Layer | IaaS | PaaS | SaaS |
|-------|------|------|------|
| Physical security | Provider | Provider | Provider |
| Hardware | Provider | Provider | Provider |
| Hypervisor | Provider | Provider | Provider |
| Network / firewall | Shared | Provider mostly | Provider |
| OS patching | Customer | Provider | Provider |
| Middleware | Customer | Provider | Provider |
| Application | Customer | Customer | Provider |
| Identity & access | Customer | Customer | Customer |
| Data classification | Customer | Customer | Customer |
| Data encryption (at rest, in transit) | Shared | Shared | Shared |
| Backup configuration | Customer | Shared | Shared |
| Configuration of the service | Customer | Customer | Customer |

The controller cannot delegate compliance. Even on SaaS, the controller remains responsible for choosing the service, configuring it, and overseeing it.

### 2. Article 28 DPA

Every cloud relationship requires a written Article 28 DPA (Data Processing Agreement) covering the eight elements of 28(3):

(a) processing only on documented instructions;
(b) confidentiality of authorised personnel;
(c) Article 32 security measures;
(d) sub-processor authorisation and conditions;
(e) assistance with data subject rights;
(f) assistance with Articles 32–36 (security, breach, DPIA);
(g) deletion or return of data at end of services;
(h) audit and information rights.

Hyperscaler standard DPAs (AWS, Microsoft, Google, Oracle) are generally GDPR-aligned, but always read the specific terms and country-of-customer addenda. KVKK-specific addenda exist for Turkish customers.

### 3. Sub-processors

Article 28(2) and (4) require:
- prior specific or general written authorisation by the controller for sub-processors;
- the controller must be informed of intended changes with opportunity to object;
- the same data protection obligations as in the main DPA pass through to sub-processors;
- the processor remains liable to the controller for the sub-processor's acts.

Hyperscalers maintain public sub-processor lists with notification mechanisms. The controller subscribes to change notifications and reviews against the contract terms before taking effect.

### 4. Customer-managed keys (CMK / BYOK / HYOK)

Encryption-with-keys-controlled-by-the-customer reduces processor power over the data:

| Pattern | Description | Practical effect |
|---------|-------------|------------------|
| Provider-managed keys | Provider holds the keys | Lowest control; provider can decrypt |
| Bring Your Own Key (BYOK) | Customer generates and uploads key into provider HSM | Better; provider operates within its HSM but holds the key in memory at use |
| Hold Your Own Key (HYOK) | Customer's HSM holds the key; provider asks for unwrap | Strongest; customer can revoke |
| Confidential computing | Encryption persists during processing in trusted execution environments | Cutting edge; reduces provider visibility further |

For Schrems II purposes, customer-controlled keys are an important supplementary measure. They are not on their own a complete answer but combined with strict access controls, contractual challenge rights, and transparency they materially reduce risk.

### 5. Data residency

Most hyperscalers offer regional residency. Choices include:

- Single region (EU): all data at rest stays in named EU regions; some metadata and logs may transit globally.
- Multi-region within EU: redundancy across EU regions.
- Sovereign cloud: provider-operated infrastructure under EU operator control with limits on US access (e.g. Microsoft Cloud for Sovereignty, Oracle EU Sovereign Cloud, AWS European Sovereign Cloud, Google Sovereign Cloud).
- Local national cloud: in-country only; for highly regulated sectors.

Residency does not eliminate transfer risk on its own. US-domiciled providers may be subject to extraterritorial demands (CLOUD Act, FISA 702) regardless of where the data physically sits.

### 6. Schrems II and US transfers

CJEU Schrems II (C-311/18) invalidated the EU-US Privacy Shield, finding that US surveillance laws (FISA 702, EO 12333) and limited remedies for non-US persons did not provide essentially equivalent protection.

The EU-US Data Privacy Framework (DPF) entered force July 2023. The DPF addresses some of the deficiencies (Data Protection Review Court, EO 14086 reforms). However:

- The DPF is a Commission adequacy decision; it permits transfers to DPF-certified US recipients without additional measures.
- For non-DPF-certified recipients, SCCs plus a Transfer Impact Assessment (TIA) remain required.
- The DPF is challenged (NOYO Schrems III pending); contingency planning is prudent.

Operational steps for any US transfer:
- Check DPF certification at dataprivacyframework.gov;
- Where DPF applies, document reliance and verify scope (HR-data variant, etc.);
- Where DPF does not apply, sign 2021 SCCs (EU 2021/914), and conduct TIA;
- TIA addresses laws of recipient country and the practice of authorities;
- TIA evaluates supplementary measures: encryption, pseudonymisation, contractual rights, organisational measures;
- TIA records the residual risk and the controller's accept/reject decision.

### 7. EDPB Recommendations 01/2020 — supplementary measures

EDPB Recommendations 01/2020 (post-Schrems II) detail a six-step process:
1. Know your transfers.
2. Verify the transfer tool relied upon.
3. Assess law and practice of the third country.
4. Identify and adopt supplementary measures.
5. Implement procedural steps.
6. Re-evaluate at appropriate intervals.

The recommendations include technical (e.g. encryption with key under exclusive control of the data exporter), contractual (e.g. transparency commitments, data subject's rights), and organisational measures (e.g. internal policies, audits).

### 8. CLOUD Act, FISA 702, EO 12333

- **CLOUD Act (2018)**: extends US law-enforcement authority to data held by US service providers regardless of where data is stored. The provider may receive a US warrant requiring production of data held in the EU.
- **FISA 702**: authorises broad surveillance of non-US persons abroad by US intelligence; the controller of personal data made available to a covered US provider may be in scope.
- **EO 12333**: authorises US intelligence collection abroad.

These laws are part of the practice of US authorities considered in the TIA. EO 14086 (2022) introduced new safeguards relied upon by the DPF. The controller documents reliance and continues to monitor enforcement reality.

### 9. Comparable third-country regimes

- **UK**: post-Brexit adequacy decision; UK-specific DPA terms.
- **Switzerland**: adequacy; align with FADP.
- **China**: PIPL governs; data export requires specific mechanisms (security assessment, SCCs, certification); transfers from EU to China require strong supplementary measures.
- **India**: DPDP 2023 enacted; in-bound EU transfers require TIA.
- **Brazil**: LGPD aligned; controller-to-controller transfers may rely on adequacy or mechanism.
- **Türkiye**: KVKK; outbound transfers from Türkiye separately governed (KVKK Article 9), with new 2024 framework using SCCs comparable to EU SCCs.

### 10. Audit rights

Article 28(3)(h) requires the processor to allow for and contribute to audits, including inspections. In the cloud context, individual customer on-site audit is rarely feasible at hyperscalers. Acceptable patterns:
- third-party audit reports (ISO 27001, SOC 2 Type II, ISO 27017, ISO 27018, C5 in Germany, ENS in Spain) made available to the customer;
- pooled customer audits;
- regulator-led audits;
- targeted audits for specific causes (post-incident, on regulator request).

Insistence on traditional on-site audit is not necessary if the processor provides robust assurance through third-party reports.

### 11. Exit strategy

Article 28(3)(g) requires deletion or return of data at end of services. Exit planning addresses:
- format and method of return;
- timeline and milestones;
- secure deletion verification;
- residual logs and backups (typically retained on a documented schedule);
- transition of operational responsibilities.

Exit testing is part of business continuity planning. Periodic dry runs validate the exit can be executed.

### 12. Cloud-specific breach considerations

A cloud breach may be:
- **Customer-side**: customer's misconfiguration (open S3 bucket, exposed API). The customer is the controller and the responsible party.
- **Provider-side**: provider's vulnerability or operational failure. The provider notifies the customer per the DPA; the customer assesses Article 33/34.
- **Joint**: shared misconfiguration; root cause may span both parties.

Notification obligations between provider and customer are time-bound by the DPA (commonly 24–48 hours). The customer's 72-hour clock under Article 33 starts when the customer becomes aware (which may be at receipt of the provider notification).

See also section `08-breach-management`.

### 13. SaaS specifics

For SaaS, the customer typically has limited control over the application stack. Mitigations:
- detailed initial security review and DPIA;
- contractual representations and warranties on encryption, residency, sub-processors;
- continuous monitoring (vendor risk management);
- incident notification SLA in the DPA;
- read-only audit access where available;
- data export and deletion mechanisms validated.

### 14. PaaS specifics

PaaS gives more configuration control. Customer responsibilities increase: identity management, secret management, network configuration, logging configuration, deployment safety. The controller's DevSecOps practices materially affect outcomes.

### 15. IaaS specifics

IaaS gives most control. Customer is responsible for OS patching, application security, all configuration, encryption, monitoring. Controller DevOps maturity directly affects compliance.

### 16. Contract minimums

In addition to Article 28 elements:
- residency commitments;
- sub-processor list and change notification process;
- transparency reporting (number of government access requests received) where lawful;
- challenge clauses (provider commits to push back on unlawful demands);
- liability and indemnity for processor breaches;
- breach notification timeline;
- assistance with data subject rights, with SLA;
- audit and assurance provisions;
- exit and return-of-data provisions;
- governing law and jurisdiction;
- transfer mechanism (DPF, SCCs, BCR) explicitly identified.

### 17. Vendor risk management cadence

| Cadence | Activity |
|---------|---------|
| Pre-contract | Detailed DPIA + security review + TIA |
| Annual | Re-assess assurance reports; update TIA if law/practice changed |
| Quarterly | Review sub-processor changes and transparency report |
| Monthly | Operational metrics (uptime, incidents) |
| On change | Re-evaluate when significant changes occur (new region, new service feature, new sub-processor) |
| Post-incident | Lessons learnt; possible CAPA against vendor |

### 18. Multi-cloud and lock-in

Multi-cloud reduces single-vendor risk and improves negotiation leverage. It also multiplies the compliance surface. The controller maintains a consistent compliance baseline across clouds rather than allowing per-cloud drift.

### 19. KVKK considerations

KVKK 2024 Yurt Dışına Aktarım Tebliği introduced SCC-style standard contracts. Hyperscalers operating in Türkiye offer KVKK-specific addenda. Outbound transfers from Türkiye to non-adequate countries follow the new framework: standard contracts, BCRs, undertakings, or explicit-consent for limited cases.

### 20. Documentation pack

For each cloud relationship:
- DPIA;
- Article 28 DPA (signed, dated, version);
- TIA for any non-EEA transfer;
- Sub-processor list with notification mechanism;
- Audit reports archive (SOC 2, ISO);
- Residency and configuration evidence;
- Exit plan and last test result;
- Incident notification log;
- DSR-handling SLA evidence;
- KVKK / Member State specific addenda.

---

## Türkçe

### 1. Paylaşılan sorumluluk modeli

Bulut bilişim, bulut sağlayıcısı (veri işleyen) ile müşteri (veri sorumlusu) arasında sorumluluğu böler.

| Katman | IaaS | PaaS | SaaS |
|--------|------|------|------|
| Fiziksel güvenlik | Sağlayıcı | Sağlayıcı | Sağlayıcı |
| Donanım | Sağlayıcı | Sağlayıcı | Sağlayıcı |
| Hipervizör | Sağlayıcı | Sağlayıcı | Sağlayıcı |
| Ağ / güvenlik duvarı | Paylaşılan | Çoğunlukla sağlayıcı | Sağlayıcı |
| OS yamalama | Müşteri | Sağlayıcı | Sağlayıcı |
| Ara katman yazılımı | Müşteri | Sağlayıcı | Sağlayıcı |
| Uygulama | Müşteri | Müşteri | Sağlayıcı |
| Kimlik ve erişim | Müşteri | Müşteri | Müşteri |
| Veri sınıflandırma | Müşteri | Müşteri | Müşteri |
| Veri şifreleme | Paylaşılan | Paylaşılan | Paylaşılan |
| Yedekleme yapılandırması | Müşteri | Paylaşılan | Paylaşılan |
| Hizmetin yapılandırması | Müşteri | Müşteri | Müşteri |

Veri sorumlusu uyumluluğu devredemez.

### 2. Madde 28 VİS

Her bulut ilişkisi 28(3)'ün sekiz unsurunu kapsayan yazılı bir Madde 28 VİS gerektirir:

(a) yalnızca belgelenmiş talimatlar üzerine işleme;
(b) yetkili personelin gizliliği;
(c) Madde 32 güvenlik önlemleri;
(d) alt veri işleyen yetkilendirmesi ve koşullar;
(e) ilgili kişi haklarına yardım;
(f) Madde 32-36'ya yardım;
(g) hizmet sonunda silme veya iade;
(h) denetim ve bilgi hakları.

### 3. Alt veri işleyenler

Madde 28(2) ve (4) gerektirir:
- alt veri işleyenler için veri sorumlusunun ön yazılı yetkilendirmesi;
- itiraz fırsatıyla niyet edilen değişiklikler hakkında bilgilendirilme;
- aynı veri koruma yükümlülüklerinin alt veri işleyenlere geçmesi;
- veri işleyenin alt veri işleyenin eylemleri için sorumlu kalması.

### 4. Müşteri yönetimli anahtarlar (CMK / BYOK / HYOK)

| Örüntü | Açıklama | Pratik etki |
|--------|----------|-------------|
| Sağlayıcı yönetimli anahtarlar | Sağlayıcı anahtarları tutar | En düşük kontrol |
| Bring Your Own Key (BYOK) | Müşteri sağlayıcı HSM'sine anahtar yükler | Daha iyi |
| Hold Your Own Key (HYOK) | Müşterinin HSM'si anahtarı tutar | En güçlü; müşteri iptal edebilir |
| Gizli bilişim | İşleme sırasında güvenilir yürütme ortamlarında şifreleme devam eder | İleri seviye |

### 5. Veri yerleşimi

Çoğu hyperscaler bölgesel yerleşim sunar.

ABD merkezli sağlayıcılar verinin fiziksel olarak nerede oturduğuna bakılmaksızın yargı dışı taleplere tabi olabilir (CLOUD Act, FISA 702).

### 6. Schrems II ve ABD aktarımları

CJEU Schrems II (C-311/18), AB-ABD Privacy Shield'i geçersiz kıldı.

AB-ABD Veri Mahremiyeti Çerçevesi (DPF) Temmuz 2023'te yürürlüğe girdi.

Herhangi bir ABD aktarımı için operasyonel adımlar:
- dataprivacyframework.gov'da DPF sertifikasını kontrol edin;
- DPF uygulanırsa güvenmeyi belgeleyin ve kapsamı doğrulayın;
- DPF uygulanmıyorsa 2021 SCC'leri imzalayın ve TIA yapın;
- TIA, alıcı ülkenin yasalarını ve yetkililerin uygulamasını ele alır;
- TIA ek önlemleri değerlendirir.

### 7. EDPB Tavsiyeleri 01/2020 — ek önlemler

EDPB Tavsiyeleri 01/2020 altı adımlı bir süreç ayrıntılandırır:
1. Aktarımlarınızı bilin.
2. Güvenilen aktarım aracını doğrulayın.
3. Üçüncü ülkenin hukuk ve uygulamasını değerlendirin.
4. Ek önlemleri belirleyin ve benimseyin.
5. Prosedürel adımları uygulayın.
6. Uygun aralıklarla yeniden değerlendirin.

### 8. CLOUD Act, FISA 702, EO 12333

- **CLOUD Act (2018)**: ABD kolluk yetkisini, verinin nerede saklandığına bakılmaksızın ABD hizmet sağlayıcılarının tuttuğu veriye genişletir.
- **FISA 702**: yurt dışındaki ABD dışı kişilerin geniş gözetlemesine yetki verir.
- **EO 12333**: yurt dışındaki ABD istihbarat toplamasına yetki verir.

EO 14086 (2022) DPF tarafından güvenilen yeni güvenceler getirdi.

### 9. Karşılaştırılabilir üçüncü ülke rejimleri

- **Birleşik Krallık**: Brexit sonrası yeterlilik kararı.
- **İsviçre**: yeterlilik.
- **Çin**: PIPL yönetir; veri ihracatı spesifik mekanizmalar gerektirir.
- **Hindistan**: DPDP 2023.
- **Brezilya**: LGPD.
- **Türkiye**: KVKK; Türkiye'den çıkan aktarımlar ayrı yönetilir.

### 10. Denetim hakları

Madde 28(3)(h) veri işleyenin denetimlere izin vermesini ve katkıda bulunmasını gerektirir.

Kabul edilebilir örüntüler:
- üçüncü taraf denetim raporları (ISO 27001, SOC 2 Tip II, ISO 27017, ISO 27018);
- havuzlu müşteri denetimleri;
- düzenleyici liderliğindeki denetimler;
- belirli nedenler için hedefli denetimler.

### 11. Çıkış stratejisi

Madde 28(3)(g) hizmet sonunda verilerin silinmesini veya iade edilmesini gerektirir.

### 12. Buluta özgü ihlal hususları

Bir bulut ihlali şu şekilde olabilir:
- **Müşteri tarafı**: müşterinin yanlış yapılandırması.
- **Sağlayıcı tarafı**: sağlayıcının zafiyeti.
- **Ortak**: paylaşılan yanlış yapılandırma.

### 13. SaaS özellikleri

SaaS için müşteri genellikle uygulama yığını üzerinde sınırlı kontrole sahiptir.

### 14. PaaS özellikleri

PaaS daha fazla yapılandırma kontrolü verir.

### 15. IaaS özellikleri

IaaS en fazla kontrolü verir.

### 16. Sözleşme minimumları

Madde 28 unsurlarına ek olarak:
- yerleşim taahhütleri;
- alt veri işleyen listesi ve değişiklik bildirimi süreci;
- şeffaflık raporlaması;
- itiraz hükümleri;
- veri işleyen ihlalleri için sorumluluk ve tazminat;
- ihlal bildirim süresi;
- ilgili kişi haklarına yardım, SLA ile;
- denetim ve güvence hükümleri;
- çıkış ve veri iadesi hükümleri;
- yönetilen hukuk ve yargı;
- aktarım mekanizması açıkça tanımlanmış.

### 17. Tedarikçi risk yönetimi ritmi

| Ritim | Faaliyet |
|-------|----------|
| Sözleşme öncesi | Ayrıntılı VKD + güvenlik incelemesi + TIA |
| Yıllık | Güvence raporlarını yeniden değerlendirin |
| Üç aylık | Alt veri işleyen değişikliklerini ve şeffaflık raporunu inceleyin |
| Aylık | Operasyonel metrikler |
| Değişiklikte | Önemli değişiklikler olduğunda yeniden değerlendirin |
| Olay sonrası | Çıkarılan dersler |

### 18. Çoklu bulut ve kilitlenme

Çoklu bulut tek tedarikçi riskini azaltır.

### 19. KVKK hususları

KVKK 2024 Yurt Dışına Aktarım Tebliği SCC tarzı standart sözleşmeler getirdi. Türkiye'de faaliyet gösteren hyperscaler'lar KVKK'ya özgü ekler sunar. Türkiye'den yeterli olmayan ülkelere giden aktarımlar yeni çerçeveyi takip eder: standart sözleşmeler, BCR'ler, taahhütler veya sınırlı durumlar için açık rıza.

### 20. Belgeleme paketi

Her bulut ilişkisi için:
- VKD;
- Madde 28 VİS (imzalı, tarihli, sürüm);
- Herhangi bir AEA dışı aktarım için TIA;
- Bildirim mekanizması ile alt veri işleyen listesi;
- Denetim raporları arşivi (SOC 2, ISO);
- Yerleşim ve yapılandırma kanıtı;
- Çıkış planı ve son test sonucu;
- Olay bildirim günlüğü;
- DSR yönetimi SLA kanıtı;
- KVKK / Üye Devlet özel ekleri.
