---
Doküman / Document: Türkiye'de Sızma Testi Gereklilikleri / Penetration Testing Requirements in Türkiye
Bölüm / Section: 14-siber-guvenlik
Sahip / Owner: Bilgi Güvenliği Müdürü (CISO) / Chief Information Security Officer (CISO)
Onaylayan / Approved by: Hukuk Müdürü + Satınalma Müdürü / Head of Legal + Head of Procurement
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-11-20
Gözden Geçirme / Review: Yıllık + SGB yetkilendirme düzenlemesi yayımlandığında / Annual + when the SGB authorisation scheme is published
İlgili Mevzuat / Legal Reference: Law No. 7545 Arts. 5(1)(b), 7(1)(c); draft Cyber Resilience Regulation Art. 34 (SGB, 18.11.2026, not in force); Information and Communication Security Guide v1.1 §3.1.11 (01.03.2026); BDDK BSEBY Art. 18 (RG 15.03.2020/31069); SPK Communiqué VII-128.10 Art. 8 (RG 13.03.2025/32840); TS 13638 (TSE)
---

## English

# Penetration Testing Requirements in Türkiye

> Sources accessed 2026-11-20. Not legal advice. "Draft" means the SGB draft of 18.11.2026, which is **not in force**.

## 1. Summary

| Who | Is a pentest legally required? | Frequency | Who may test | Report goes to | Retention | Source |
|-----|-------------------------------|-----------|--------------|----------------|-----------|--------|
| Any company under Law 7545 | No general statutory pentest duty in the Law | - | - | - | - | Law 7545 (SGB itself may run or commission pentests, Art. 5(1)(b)) |
| Public bodies; critical-infrastructure operators with IT unit or outsourced IT (Circular 2019/12 scope) | Yes, as a Guide measure | **At least once a year** (Guide measure 3.1.11.8, level 2) | Not specified beyond confidentiality undertaking and separation of duties for verification tests | Internal; Guide audit results to SGB via BİGDES | Not specified in §3.1.11 | [Guide v1.1](https://cdn.siberguvenlik.gov.tr/public/docs/bg_rehber.pdf) §3.1.11 |
| Banks | Yes | **At least once a year** | Independent teams not involved in design, development, implementation or operation of the services | Internal; BDDK may request (sector rules) | UNVERIFIED in Art. 18 | BSEBY Art. 18(7) |
| Capital-market institutions (SPK) | Yes | **At least once a year**; SPK may order extra tests | Natural or legal persons with no duty in the institution's IS security and holding a **national or international pentest certificate** | **SPK, within one month of completion and in any case by 31 January of the following year** | UNVERIFIED (annex EK-1 not readable) | VII-128.10 Art. 8(6)-(7) |
| Organisations obliged to run a Corporate SOME (draft) | Would be yes | **At least once a year** | **Independent organisations authorised by SGB** | **SGB and the organisation**, sent by the testing body | **At least 5 years** | Draft Art. 34 |
| Energy (EPDK) | Sector rule exists | UNVERIFIED | UNVERIFIED | UNVERIFIED | UNVERIFIED | see §6 |
| Telecom (BTK) | Sector rule exists | UNVERIFIED | UNVERIFIED | UNVERIFIED | UNVERIFIED | see §6 |
| Health | UNVERIFIED | UNVERIFIED | UNVERIFIED | UNVERIFIED | UNVERIFIED | see §6 |

## 2. TSE Certification of Pentest Firms and Personnel (TS 13638)

- **Standard:** TS 13638 "Bilgi Teknolojileri - Güvenlik Teknikleri - Sızma testi yapan personel ve firmalar için şartlar" (requirements for personnel and firms performing pentests). Source: [TSE training document 2023](https://files.tse.org.tr//2023/09/EgitimSizma.pdf); [TSE FAQ](https://www.tse.org.tr/sss/sizma-testi-yapan-firma-belgesi-almak-istiyoruz-ne-yapmaliyiz/).
- **Personnel:** four levels, each certified separately in two areas (1) Network and System Infrastructure, (2) Web Applications and Databases: Stajyer (Trainee), Kayıtlı (Registered), Sertifikalı (Certified), Kıdemli (Senior) Sızma Testi Uzmanı. TSE runs theory and practical exams several times a year (e.g., October 2026 call). Source: TSE training document; [TSE pentest page](https://www.tse.org.tr/sizma-testleri/).
- **Firms (TSE FAQ):**

| Level | Minimum certified staff | ISO/IEC 27001 |
|-------|-------------------------|---------------|
| A | 1 Senior + 1 Certified + 1 Registered + 2 Trainee | TS EN ISO/IEC 27001 certificate from a TÜRKAK-accredited body |
| B | 1 Certified + 1 Registered + 1 Trainee | same as A |
| C | 1 Registered | meet the relevant 27001 clauses listed in TS 13638 |

- **Older TSE programme (2014):** "Sızma Testi Hizmeti Veren Personel ve Firmalar İçin Yetkilendirme Programı" (first issued 01.10.2013, R7 28.05.2014) **recommends** a pentest at least once a year, more often for critical systems, and before go-live of new systems; it treats test reports as classified documents and says retention should follow the client's view. It is a TSE programme document, **not** law. Source: [USOM DSY copy](https://dsy.usom.gov.tr/usom/19/02/190211084545_1421179946-S%C4%B1zma_Testi_Kriterler.pdf).
- **"TSE-K-12":** the brief mentioned this code. **DOĞRULANMADI / UNVERIFIED**: no TSE source with that code was found; the current scheme cited by TSE is TS 13638.
- **Status vs. SGB:** TSE certification is a market and procurement reference. It is **not** the SGB authorisation required by Law 7545 Art. 7(1)(c) and draft Art. 34. No SGB authorisation scheme for pentest providers was found (UNVERIFIED that none exists).

## 3. Information and Communication Security Guide v1.1 (SGB, 01.03.2026), §3.1.11

Applies to public bodies and critical-infrastructure operators within Circular 2019/12 (SGB FAQ). Measure level 1 applies to criticality-1 asset groups; level 2 adds to criticality 2; level 3 adds to criticality 3 (Guide §2).

| No. | Level | Measure (summary) |
|-----|-------|-------------------|
| 3.1.11.1 | 1 | Regular external and internal pentests and security audits; written undertaking from the tester that no data obtained is disclosed; scope defined and documented; **social engineering tests included** |
| 3.1.11.2 | 1 | Test with different user profiles (anonymous, guest, employee, customer, support) |
| 3.1.11.3 | 1 | Where pentest is impossible or high risk on live systems: regular security audits and hardening |
| 3.1.11.4 | 1 | Test accounts controlled, monitored, logged, disabled after the test |
| 3.1.11.5 | 1 | Verification tests of closed findings under separation of duties |
| 3.1.11.6 | 1 | Findings rated with a comparable scoring method |
| 3.1.11.7 | 2 | Realistic test environments where live testing is impossible |
| 3.1.11.8 | 2 | **Pentests and security audits at least once a year** |
| 3.1.11.9 | 3 | Regular red-team exercises, documented and followed up |
| 3.1.11.10 | 3 | Vulnerability scan and security audit before adding hardware/software to the network |

## 4. Sector Rules (Primary Text Checked)

### 4.1. Banking: BDDK BSEBY (RG 15.03.2020/31069; most provisions in force 01.01.2021 per RG 20.06.2020/31161)

- Art. 18(2): Corporate SOME does or commissions **routine pentests** on IT assets.
- Art. 18(7): the bank has pentests performed **at least once a year by independent teams** with no role in design, development, implementation or operation of the services.
- Source: [consolidated text](https://www.mevzuat.gov.tr/anasayfa/MevzuatFihristDetayIframe?MevzuatNo=34360&MevzuatTertip=5&MevzuatTur=7).

### 4.2. Capital markets: SPK VII-128.10 (RG 13.03.2025/32840; in force 30.06.2025; compliance by 31.12.2025, except Art. 29(3) by 31.12.2026; different dates for crypto-asset service providers)

- Art. 8(6): at least yearly pentest by persons with no IS-security duty in the institution and holding a national or international pentest certificate; SPK may require additional tests.
- Art. 8(7): pentest procedures in **Annex EK-1**; reports sent to SPK within one month of completion and at latest by 31 January of the following year.
- Annex EK-1 is an image-only PDF; its content is **UNVERIFIED**.
- Source: [RG 13.03.2025, text](https://www.resmigazete.gov.tr/eskiler/2025/03/20250313-8.htm).

## 5. Draft Cyber Resilience Regulation (SGB, 18.11.2026, not in force)

- Art. 34(1): **at least yearly pentest by independent organisations authorised by SGB**.
- Art. 34(2): reports submitted **by the testing organisation to SGB and to the organisation**; findings prioritised and fixed within a reasonable time with verification; reports and records kept **at least 5 years**.
- Art. 34(3): regular vulnerability scanning; results provided to SGB on request.
- Art. 67 (critical infrastructure): at least yearly cyber exercise; reports kept at least 5 years.
- Applies to organisations obliged to run a Corporate SOME (Chapter 5, effective six months after publication if adopted as drafted, Art. 75).
- Source: [draft PDF](https://cdn.siberguvenlik.gov.tr/public/news/siber-dayaniklilik-yonetmeligi.pdf).

## 6. Sector Rules Not Verified in Primary Text

| Sector | Instrument found | What is UNVERIFIED |
|--------|------------------|--------------------|
| Energy (EPDK) | Enerji Sektöründe Siber Güvenlik Yetkinlik Modeli Yönetmeliği, RG 06.06.2023/32213; amendments in 2024 and RG 25.11.2025/33088 (auditor ISO 27001 or CISA, compliance by 01.03.2026). EPDK Board decision 13.07.2023/11956 on ICS security analysis and testing procedures. All per secondary sources (Lexpera, Alomaliye). | Pentest frequency, tester qualification, reporting and publication status of the ICS testing procedures |
| Telecom (BTK) | Elektronik Haberleşme Sektöründe Şebeke ve Bilgi Güvenliği Yönetmeliği, RG 13.07.2014/29059 (secondary sources) | Pentest article, current text, and which powers moved to SGB under Law 7590 |
| Health | Not identified | Whole row |
| Payment and e-money institutions (TCMB) | Not checked | Whole row |

## 7. Practical Pentest Procurement Checklist

| # | Check | Why |
|---|-------|-----|
| 1 | Identify every rule that applies (Guide, BDDK, SPK, EPDK, draft SGB) and take the strictest frequency, tester and reporting requirement | Rules overlap |
| 2 | Tester independence: no role in design, development or operation of the tested systems | BSEBY 18(7), SPK 8(6) |
| 3 | Tester qualification: TSE TS 13638 firm level (A/B/C) and named individual certificates per area (network / web-DB); for SPK, a national or international pentest certificate | SPK 8(6); TSE FAQ |
| 4 | Ask whether the firm holds SGB authorisation; record "not yet available" if no scheme exists, and add a contract clause to switch to an SGB-authorised provider when required | Law 7545 Art. 7(1)(c); draft Art. 34 |
| 5 | Signed NDA / non-disclosure undertaking covering all data obtained, before the test | Guide 3.1.11.1 |
| 6 | Written scope: IP ranges, domains, apps, APIs, cloud tenants, OT; internal + external; user profiles; social engineering in scope | Guide 3.1.11.1-2 |
| 7 | Third-party permissions: cloud provider and hosting rules, data-centre owner, ISP; written authorisation from the asset owner | Avoid unauthorised access (TCK Art. 243) |
| 8 | Rules of engagement: time windows (off-peak, DoS only out of hours), emergency stop, 7/24 contacts on both sides, incident-during-test procedure | TSE programme §5.1 |
| 9 | Test accounts created for the test only, logged, disabled afterwards | Guide 3.1.11.4 |
| 10 | Data handling: testers' copies of personal data minimised, encrypted, deleted at end with deletion certificate; KVKK data-processing agreement with the firm | KVKK Art. 12; see [05-teknik-tedbirler](../05-teknik-tedbirler/) |
| 11 | Report: comparable scoring (e.g., CVSS), executive summary, evidence, remediation advice, retest results | Guide 3.1.11.6 |
| 12 | Retest of fixed findings by someone other than the fixer | Guide 3.1.11.5 |
| 13 | Report classification and storage: confidential, not on laptops or removable media, access-controlled; keep at least 5 years (draft) unless a sector rule requires longer | TSE programme §6.2.2; draft Art. 34(2) |
| 14 | Regulator delivery: SPK within one month / by 31 January; SGB if draft adopted; BDDK on request | SPK 8(7); draft Art. 34(2) |
| 15 | If the test finds a live compromise: stop, preserve evidence, start incident procedure, assess KVKK 72h and SGB duties | [olay-bildirim-matrisi.md](olay-bildirim-matrisi.md) |
| 16 | Annual calendar entry and budget line | Guide 3.1.11.8; BSEBY 18(7); SPK 8(6) |

## 8. UNVERIFIED

- Any SGB authorisation scheme for pentest providers.
- "TSE-K-12" designation.
- SPK Annex EK-1 content; BDDK report retention period.
- EPDK, BTK, health and TCMB pentest details.

## 9. Version History

| Version | Date | Change | Approval |
|---------|------|--------|----------|
| 1.0 | 2026-11-20 | First release | KVKK Committee |

---

## Türkçe

# Türkiye'de Sızma Testi Gereklilikleri

> Kaynaklara erişim 2026-11-20. Hukuki görüş değildir. "Taslak", SGB'nin 18.11.2026 tarihli ve **yürürlükte olmayan** taslağını ifade eder.

## 1. Özet

| Kim | Sızma testi hukuken zorunlu mu? | Sıklık | Kim test edebilir | Rapor kime gider | Saklama | Kaynak |
|-----|--------------------------------|--------|-------------------|------------------|---------|--------|
| 7545 kapsamındaki her şirket | Kanunda genel bir sızma testi yükümlülüğü yok | - | - | - | - | 7545 (SGB kendisi test yapabilir veya yaptırabilir, m.5(1)(b)) |
| Kamu kurumları; bilgi işlem birimi olan veya bilgi işlemi dışarıdan alan kritik altyapı işletmeleri (2019/12 Genelge kapsamı) | Evet, Rehber tedbiri olarak | **Yılda en az bir kez** (Rehber 3.1.11.8, 2. seviye) | Gizlilik taahhüdü ve doğrulama testlerinde görevler ayrılığı dışında nitelik belirtilmemiş | Kurum içi; Rehber denetim sonuçları BİGDES ile SGB'ye | §3.1.11'de belirtilmemiş | [Rehber s.1.1](https://cdn.siberguvenlik.gov.tr/public/docs/bg_rehber.pdf) §3.1.11 |
| Bankalar | Evet | **Yılda en az bir kez** | Hizmetlerin tasarım, geliştirme, uygulama veya yürütmesinde görevi olmayan bağımsız ekipler | Kurum içi; BDDK talep edebilir | m.18'de DOĞRULANMADI | BSEBY m.18(7) |
| Sermaye piyasası kurumları (SPK) | Evet | **Yılda en az bir kez**; SPK ek test isteyebilir | Kurumun bilgi güvenliğinde görevi olmayan, sızma testinde **ulusal veya uluslararası belgeye** sahip gerçek veya tüzel kişiler | **SPK'ya, tamamlanmasından itibaren bir ay içinde ve en geç takip eden yılın 31 Ocak'ına kadar** | DOĞRULANMADI (EK-1 okunamadı) | VII-128.10 m.8(6)-(7) |
| Kurumsal SOME kurmakla yükümlü kuruluşlar (taslak) | Evet olur | **Yılda en az bir kez** | **SGB tarafından yetkilendirilmiş bağımsız kuruluşlar** | Test eden kuruluş tarafından **SGB'ye ve kuruluşa** | **En az 5 yıl** | Taslak m.34 |
| Enerji (EPDK) | Sektör düzenlemesi var | DOĞRULANMADI | DOĞRULANMADI | DOĞRULANMADI | DOĞRULANMADI | bkz. §6 |
| Elektronik haberleşme (BTK) | Sektör düzenlemesi var | DOĞRULANMADI | DOĞRULANMADI | DOĞRULANMADI | DOĞRULANMADI | bkz. §6 |
| Sağlık | DOĞRULANMADI | DOĞRULANMADI | DOĞRULANMADI | DOĞRULANMADI | DOĞRULANMADI | bkz. §6 |

## 2. Sızma Testi Firma ve Personelinin TSE Belgelendirmesi (TS 13638)

- **Standart:** TS 13638 "Bilgi Teknolojileri - Güvenlik Teknikleri - Sızma testi yapan personel ve firmalar için şartlar". Kaynak: [TSE eğitim dokümanı 2023](https://files.tse.org.tr//2023/09/EgitimSizma.pdf); [TSE SSS](https://www.tse.org.tr/sss/sizma-testi-yapan-firma-belgesi-almak-istiyoruz-ne-yapmaliyiz/).
- **Personel:** dört seviye, iki alanda ayrı ayrı sertifika (1) Ağ ve Sistem Altyapıları, (2) Web Uygulamaları ve Veritabanları: Stajyer, Kayıtlı, Sertifikalı ve Kıdemli Sızma Testi Uzmanı. TSE yılda birkaç kez teorik ve uygulamalı sınav yapar (ör. Ekim 2026 duyurusu). Kaynak: TSE eğitim dokümanı; [TSE sızma testleri sayfası](https://www.tse.org.tr/sizma-testleri/).
- **Firmalar (TSE SSS):**

| Seviye | Asgari belgeli personel | ISO/IEC 27001 |
|--------|-------------------------|---------------|
| A | 1 Kıdemli + 1 Sertifikalı + 1 Kayıtlı + 2 Stajyer | TÜRKAK akreditasyonlu kuruluştan TS EN ISO/IEC 27001 belgesi |
| B | 1 Sertifikalı + 1 Kayıtlı + 1 Stajyer | A ile aynı |
| C | 1 Kayıtlı | TS 13638'de belirtilen 27001 maddelerini sağlamak |

- **Eski TSE programı (2014):** "Sızma Testi Hizmeti Veren Personel ve Firmalar İçin Yetkilendirme Programı" (ilk yayım 01.10.2013, R7 28.05.2014) yılda en az bir kez, kritik sistemlerde daha sık ve yeni sistemlerde canlıya almadan önce test yaptırılmasını **tavsiye eder**; test raporlarını gizlilik dereceli doküman sayar, saklamanın kuruluşun görüşüne göre yapılmasını söyler. Bu bir TSE program dokümanıdır, **mevzuat değildir**. Kaynak: [USOM DSY kopyası](https://dsy.usom.gov.tr/usom/19/02/190211084545_1421179946-S%C4%B1zma_Testi_Kriterler.pdf).
- **"TSE-K-12":** görev tanımında geçen bu kod **DOĞRULANMADI / UNVERIFIED**; bu kodu taşıyan bir TSE kaynağı bulunamadı, TSE'nin güncel olarak andığı şema TS 13638'dir.
- **SGB karşısındaki durumu:** TSE belgesi piyasa ve satın alma referansıdır; 7545 m.7(1)(c) ve taslak m.34'teki SGB yetkilendirmesi **değildir**. Sızma testi sağlayıcıları için bir SGB yetkilendirme sistemi bulunamadı (olmadığı DOĞRULANMADI).

## 3. Bilgi ve İletişim Güvenliği Rehberi s.1.1 (SGB, 01.03.2026), §3.1.11

2019/12 sayılı Genelge kapsamındaki kamu kurumları ve kritik altyapı işletmelerine uygulanır (SGB SSS). 1. seviye tedbirler kritiklik derecesi 1 olan varlık gruplarına, 2. seviye kritiklik 2'ye ek olarak, 3. seviye kritiklik 3'e ek olarak uygulanır (Rehber §2).

| No. | Seviye | Tedbir (özet) |
|-----|--------|---------------|
| 3.1.11.1 | 1 | Düzenli dış ve iç sızma testi ve güvenlik denetimi; test edenden elde edilen verilerin ifşa edilmeyeceğine dair yazılı taahhüt; kapsam tanımlı ve dokümante; **sosyal mühendislik testleri kapsama dahil** |
| 3.1.11.2 | 1 | Farklı kullanıcı profilleriyle test (anonim, misafir, çalışan, hizmet alan, destek) |
| 3.1.11.3 | 1 | Canlıda test mümkün değilse veya yüksek riskliyse düzenli güvenlik denetimi ve sıkılaştırma |
| 3.1.11.4 | 1 | Test hesapları kontrol edilir, izlenir, kayda alınır, test sonunda pasif yapılır |
| 3.1.11.5 | 1 | Kapatılan açıkların doğrulama testi görevler ayrılığı ilkesiyle |
| 3.1.11.6 | 1 | Bulgular karşılaştırılabilir puanlamayla raporlanır |
| 3.1.11.7 | 2 | Canlıda test mümkün değilse gerçeğe benzer test ortamı |
| 3.1.11.8 | 2 | **Sızma testi ve güvenlik denetimi yılda en az bir kez** |
| 3.1.11.9 | 3 | Düzenli kırmızı takım tatbikatı, dokümante edilir ve takip edilir |
| 3.1.11.10 | 3 | Ağa eklenecek donanım/yazılım için önceden zafiyet taraması ve güvenlik denetimi |

## 4. Sektör Kuralları (Birincil Metin Kontrol Edildi)

### 4.1. Bankacılık: BDDK BSEBY (RG 15.03.2020/31069; hükümlerin çoğu RG 20.06.2020/31161 değişikliğiyle 01.01.2021'de yürürlükte)

- m.18(2): Kurumsal SOME, bilgi işlem varlıkları üzerinde **rutin sızma testi** yapar veya yaptırır.
- m.18(7): Banka, hizmetlerin tasarım, geliştirme, uygulama veya yürütmesinde görevi olmayan **bağımsız ekiplere yılda en az bir defa** sızma testi yaptırır.
- Kaynak: [güncel metin](https://www.mevzuat.gov.tr/anasayfa/MevzuatFihristDetayIframe?MevzuatNo=34360&MevzuatTertip=5&MevzuatTur=7).

### 4.2. Sermaye piyasası: SPK VII-128.10 (RG 13.03.2025/32840; yürürlük 30.06.2025; uyum 31.12.2025, m.29(3) için 31.12.2026; kripto varlık hizmet sağlayıcılar için farklı tarihler)

- m.8(6): kurumun bilgi güvenliğinde görevi bulunmayan ve sızma testinde ulusal veya uluslararası belgeye sahip kişilerce yılda en az bir kez; SPK ek test isteyebilir.
- m.8(7): usul ve esaslar **EK-1**'de; raporlar tamamlanmasından itibaren bir ay içinde ve en geç takip eden yılın 31 Ocak'ına kadar SPK'ya gönderilir.
- EK-1 yalnız görüntü PDF'i; içeriği **DOĞRULANMADI**.
- Kaynak: [RG 13.03.2025 metin](https://www.resmigazete.gov.tr/eskiler/2025/03/20250313-8.htm).

## 5. Siber Dayanıklılık Yönetmeliği Taslağı (SGB, 18.11.2026, yürürlükte değil)

- m.34(1): **SGB tarafından yetkilendirilmiş bağımsız kuruluşlara yılda en az bir kez** sızma testi.
- m.34(2): raporlar **test eden kuruluş tarafından SGB'ye ve kuruluşa** sunulur; bulgular önceliklendirilip makul sürede giderilir ve doğrulanır; rapor ve kayıtlar **en az 5 yıl** saklanır.
- m.34(3): düzenli zafiyet taraması; sonuçlar talep hâlinde SGB'ye.
- m.67 (kritik altyapı): yılda en az bir siber tatbikat; raporlar en az 5 yıl saklanır.
- Kurumsal SOME kurmakla yükümlü kuruluşlara uygulanır (5. bölüm; taslak olduğu gibi kabul edilirse yayımdan altı ay sonra yürürlüğe girer, m.75).
- Kaynak: [taslak PDF](https://cdn.siberguvenlik.gov.tr/public/news/siber-dayaniklilik-yonetmeligi.pdf).

## 6. Birincil Metinden Doğrulanamayan Sektör Kuralları

| Sektör | Bulunan düzenleme | DOĞRULANMAYAN |
|--------|-------------------|---------------|
| Enerji (EPDK) | Enerji Sektöründe Siber Güvenlik Yetkinlik Modeli Yönetmeliği, RG 06.06.2023/32213; 2024 değişikliği ve RG 25.11.2025/33088 değişikliği (denetçide ISO 27001 veya CISA, uyum 01.03.2026). EKS güvenlik analizi ve test usul ve esaslarına ilişkin 13.07.2023 tarihli ve 11956 sayılı EPDK Kurul Kararı. Hepsi ikincil kaynaklardan (Lexpera, Alomaliye). | Sızma testi sıklığı, test eden niteliği, raporlama ve EKS test usullerinin yayım durumu |
| Elektronik haberleşme (BTK) | Elektronik Haberleşme Sektöründe Şebeke ve Bilgi Güvenliği Yönetmeliği, RG 13.07.2014/29059 (ikincil kaynaklar) | Sızma testi maddesi, güncel metin ve 7590 ile hangi yetkilerin SGB'ye geçtiği |
| Sağlık | Tespit edilemedi | Satırın tamamı |
| Ödeme ve elektronik para kuruluşları (TCMB) | Kontrol edilmedi | Satırın tamamı |

## 7. Uygulamada Sızma Testi Satın Alma Kontrol Listesi

| # | Kontrol | Neden |
|---|---------|-------|
| 1 | Uygulanan tüm kuralları (Rehber, BDDK, SPK, EPDK, SGB taslağı) belirleyin; en katı sıklık, test eden ve raporlama şartını alın | Kurallar örtüşür |
| 2 | Test edenin bağımsızlığı: test edilen sistemlerin tasarım, geliştirme veya işletiminde rolü yok | BSEBY 18(7), SPK 8(6) |
| 3 | Test edenin niteliği: TSE TS 13638 firma seviyesi (A/B/C) ve alan bazında (ağ / web-veritabanı) isimli kişisel sertifikalar; SPK için ulusal veya uluslararası sızma testi belgesi | SPK 8(6); TSE SSS |
| 4 | Firmanın SGB yetkilendirmesi olup olmadığını sorun; sistem yoksa "henüz yok" diye kayda alın ve gerektiğinde SGB yetkili sağlayıcıya geçişi sağlayan sözleşme maddesi ekleyin | 7545 m.7(1)(c); taslak m.34 |
| 5 | Testten önce elde edilen tüm verileri kapsayan imzalı gizlilik taahhüdü | Rehber 3.1.11.1 |
| 6 | Yazılı kapsam: IP aralıkları, alan adları, uygulamalar, API'ler, bulut kiracıları, OT; iç + dış; kullanıcı profilleri; sosyal mühendislik dahil | Rehber 3.1.11.1-2 |
| 7 | Üçüncü taraf izinleri: bulut ve barındırma kuralları, veri merkezi sahibi, İSS; varlık sahibinden yazılı yetki | Yetkisiz erişimden kaçınmak (TCK m.243) |
| 8 | Çalışma kuralları: zaman pencereleri (yoğun olmayan saatler, DoS yalnız mesai dışı), acil durdurma, iki tarafta 7/24 irtibat, test sırasında olay prosedürü | TSE programı §5.1 |
| 9 | Test hesapları yalnız test için açılır, kayda alınır, sonra kapatılır | Rehber 3.1.11.4 |
| 10 | Veri işleme: test edenin elindeki kişisel veri kopyaları en aza indirilir, şifrelenir, sonunda silinir ve silme tutanağı alınır; firmayla KVKK veri işleme sözleşmesi | KVKK m.12; bkz. [05-teknik-tedbirler](../05-teknik-tedbirler/) |
| 11 | Rapor: karşılaştırılabilir puanlama (ör. CVSS), yönetici özeti, kanıt, iyileştirme önerisi, yeniden test sonucu | Rehber 3.1.11.6 |
| 12 | Kapatılan bulguların düzelten kişiden başkası tarafından yeniden testi | Rehber 3.1.11.5 |
| 13 | Rapor sınıflandırma ve saklama: gizli, dizüstü bilgisayarda veya taşınabilir ortamda tutulmaz, erişimi kısıtlı; sektör kuralı daha uzun süre istemiyorsa en az 5 yıl (taslak) | TSE programı §6.2.2; taslak m.34(2) |
| 14 | Düzenleyiciye teslim: SPK'ya bir ay içinde / 31 Ocak'a kadar; taslak kabul edilirse SGB'ye; BDDK'ya talep hâlinde | SPK 8(7); taslak m.34(2) |
| 15 | Test canlı bir ihlal bulursa: durdurun, delili koruyun, olay prosedürünü başlatın, KVKK 72 saat ve SGB yükümlülüklerini değerlendirin | [olay-bildirim-matrisi.md](olay-bildirim-matrisi.md) |
| 16 | Yıllık takvim kaydı ve bütçe kalemi | Rehber 3.1.11.8; BSEBY 18(7); SPK 8(6) |

## 8. DOĞRULANMADI / UNVERIFIED

- Sızma testi sağlayıcıları için bir SGB yetkilendirme sistemi.
- "TSE-K-12" kodu.
- SPK EK-1 içeriği; BDDK rapor saklama süresi.
- EPDK, BTK, sağlık ve TCMB sızma testi ayrıntıları.

## 9. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-11-20 | İlk yayım | KVKK Komitesi |
