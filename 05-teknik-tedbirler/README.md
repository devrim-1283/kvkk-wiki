---
Doküman / Document: Teknik Tedbirler — Bölüm Girişi / Technical Measures — Section Introduction
Bölüm / Section: 05-teknik-tedbirler
Sahip / Owner: Bilgi Güvenliği Yöneticisi (CISO) / Information Security Manager (CISO)
Onaylayan / Approved by: BT Direktörü + KVKK Komitesi / IT Director + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş (mevzuat değişikliği, ihlal, büyük mimari değişiklik, yeni teknoloji benimseme) / Annual + triggered (regulatory change, breach, major architectural change, new technology adoption)
İlgili Mevzuat / Legal Reference: Law No. 6698 KVKK Art. 12 (Obligations Regarding Data Security), Regulation on the Data Controllers Registry Art. 9(1)(e), Personal Data Security Guide (Technical and Organizational Measures), Law No. 5651 (logging obligations relevant parts), Banking Regulation and Supervision Agency (BDDK) Regulation on Information Systems and Electronic Banking Services (where applicable)
İlgili Standart / Standard: ISO/IEC 27001:2022 Annex A (especially A.5.15 Access Control, A.8 Technological Controls), ISO/IEC 27002:2022, ISO/IEC 27701:2019, NIST Cybersecurity Framework 2.0 (PROTECT, DETECT, RESPOND), NIST SP 800-53 Rev. 5, NIST SP 800-63B (Digital Identity), ENISA "Handbook on Security of Personal Data Processing" (2018, current edition), GDPR Art. 32 ("appropriate technical and organisational measures"), CIS Controls v8, OWASP ASVS 4.0
---

## English

# 05 — Technical Measures

## 1. Purpose and Scope

This section defines, in an integrated manner, the technical measures we adopt as a data controller under KVKK Art. 12 to **prevent unlawful processing and unlawful access** to personal data we process and to **ensure its preservation**. The measures cover all categories of personal data processed in on-premises, hybrid and cloud (IaaS/PaaS/SaaS) environments.

KVKK Art. 12(1) explicitly imposes on the data controller the obligation to "take all kinds of necessary technical and organizational measures to ensure an appropriate level of security." The **appropriate level of security** is not a single absolute threshold; it is determined by considering the nature, quantity of personal data processed, the data subject group, processing purpose, state of the art, and cost/benefit balance. This framework is a **risk-based** approach and aligns with the underlying logic of GDPR Art. 32, NIST CSF and ISO 27001.

## 2. Documents in This Section

| # | Document | Content | Owner |
|---|---------|--------|--------|
| 1 | [erisim-kontrolu.md](erisim-kontrolu.md) | Least privilege, RBAC/ABAC, JML, PAM, access review | IT Operations + CISO |
| 2 | [kimlik-dogrulama.md](kimlik-dogrulama.md) | MFA, SSO/IdP, password policy, service accounts | IAM Team |
| 3 | [sifreleme.md](sifreleme.md) | At-rest, in-transit, key management, HSM/KMS, PQC | Crypto Engineering + CISO |
| 4 | [ag-guvenligi.md](ag-guvenligi.md) | Segmentation, zero trust, FW/IDS/IPS/WAF, ZTNA | Network Security |
| 5 | [log-yonetimi.md](log-yonetimi.md) | Logging, SIEM, UEBA, Law No. 5651, runbook | SOC + CISO |
| 6 | [yedekleme.md](yedekleme.md) | 3-2-1, immutable, restore test, DR/BCP, RTO/RPO | IT Operations |
| 7 | [veri-maskeleme-anonimlestirme.md](veri-maskeleme-anonimlestirme.md) | Masking, tokenization, anonym/pseudonym, k-anon | Data Engineering + KVKK |
| 8 | [dlp.md](dlp.md) | Endpoint/Network/Cloud DLP, CASB, employee privacy | DLP Team + CISO |
| 9 | [uygulama-guvenligi.md](uygulama-guvenligi.md) | Secure SDLC, SAST/DAST/SCA, penetration testing, OWASP | AppSec |
| 10 | [teknik-tedbir-kontrol-listesi.md](teknik-tedbir-kontrol-listesi.md) | 80+ item audit checklist | Internal Audit |

## 3. Governance and Responsibility Model (RACI)

| Activity | Responsible (R) | Accountable (A) | Consulted (C) | Informed (I) |
|----------|-------------|-----------------|----------------|-------------------|
| Drafting technical measure policies | CISO team | CISO | KVKK Officer, Legal, IT Director | Senior Management |
| Approval of policies | CISO | IT Director | KVKK Committee | Board of Directors |
| Operational implementation | Relevant technical team | IT Operations Manager | CISO, KVKK Officer | Internal Audit |
| Measurement and reporting | SOC + CISO PMO | CISO | KVKK Committee | Senior Management |
| Internal audit | Internal Audit | Audit Committee | CISO, KVKK Officer | Board of Directors |
| Action follow-up (CAPA) | Relevant owners | CISO | Internal Audit | KVKK Committee |

## 4. Risk-Based Design Principles

The following principles are applied **without exception** in the design of technical measures:

1. **Defence in Depth:** Failure of a single control must not lead to data exposure. Independent controls at network → host → application → data layers.
2. **Least Privilege:** Every user, service account and application operates with the **minimum** privileges necessary to perform its task.
3. **Need-to-Know:** Access to personal data is limited to persons whose role actually requires viewing the data. Being authorized ≠ accessing.
4. **Default Deny:** Any access not explicitly permitted is denied.
5. **Zero Trust:** No traffic is trusted based on network location; every access request is accepted only after identity, device, session and behavior verification.
6. **Privacy by Design / Default (KVKK Art. 4 proportionality + GDPR Art. 25):** Data minimization, purpose limitation and data protection measures are embedded in the system design rather than added later.
7. **Crypto Agility:** Dependencies that prevent updating/changing the algorithms and key sizes used must not be created (especially critical before PQC migration).
8. **Fail Secure:** Failure of a component must default to a state that protects rather than exposes data.
9. **Auditability:** All security-relevant events are recorded irreversibly and are auditable.
10. **Minimization in Logs:** Log content must not contain personal data beyond the purpose of the measure itself.

## 5. Mapping with the KVKK Personal Data Security Guide

The Personal Data Security Guide published by the Authority groups technical measure topics as follows. Our document set covers this structure **one-to-one** and additionally maps to modern security standards:

| KVKK Guide Heading | Equivalent in This Section | ISO 27002:2022 Control |
|----------------------|----------------------|-------------------------|
| Ensuring Cybersecurity | ag-guvenligi.md, uygulama-guvenligi.md | A.8.20–A.8.27 |
| Personal Data Security Monitoring | log-yonetimi.md | A.8.15, A.8.16, A.5.7 |
| Security of Environments Containing Personal Data | sifreleme.md, ag-guvenligi.md | A.7.10, A.8.10, A.8.13 |
| Storage of Personal Data in the Cloud | sifreleme.md, ag-guvenligi.md, supplier (06) | A.5.23 |
| IT Systems Procurement, Development, and Maintenance | uygulama-guvenligi.md | A.8.25–A.8.34 |
| Backup of Personal Data | yedekleme.md | A.8.13 |
| User Account Management and Authority Matrix | erisim-kontrolu.md, kimlik-dogrulama.md | A.5.15–A.5.18, A.8.2, A.8.3, A.8.5 |
| Encryption | sifreleme.md | A.8.24 |
| Data Masking | veri-maskeleme-anonimlestirme.md | A.8.11 |
| Intrusion Detection and Prevention Systems | ag-guvenligi.md, log-yonetimi.md | A.8.16 |
| Penetration Testing | uygulama-guvenligi.md | A.8.29 |
| Information Security Incident Management | log-yonetimi.md + 08-ihlal-yonetimi/ | A.5.24–A.5.28 |

## 6. Measurement and KPIs

The effectiveness of technical measures cannot be assessed solely on a "have/have-not" axis; it must be **measurable**. The following indicator set is updated annually and reported quarterly:

- Critical vulnerability remediation time (MTTR-Critical) — target ≤ 7 days.
- MFA coverage percentage — target 100% (admins, remote access, all applications containing personal data).
- Privileged user ratio (privileged user / total user) — target ≤ 5%.
- Access review completion rate — target 100% per quarter.
- Backup restore test success rate — target ≥ 99%.
- Average log collection latency — target ≤ 5 minutes.
- SIEM coverage (proportion of asset inventory that is logged) — target ≥ 95%.
- Critical system TLS compliance ratio — target 100% TLS 1.2+ (1.3 preferred).
- DLP false-positive rate — target ≤ 20%.
- Unclosed JML (mover/leaver) actions — target 0 (none pending more than 24 hours).

## 7. Relationship of This Section to Other Sections

- **00-yonetisim/** — The policy approval chain and roles authorize the measures defined here.
- **04-veri-saklama-ve-imha/** — Technical destruction of data whose retention period has expired benefits from the encryption and key management processes defined here (crypto-shredding).
- **06-idari-tedbirler/** — Supplier management, training and the policy framework ensure the "effective implementation" of technical measures.
- **08-ihlal-yonetimi/** — Log management and SIEM detections feed it.
- **11-denetim-ve-uyum/** — Internal audit tests this section's checklists by sampling.

## 8. Annual Review

The CISO reviews all documents in this section **every calendar year in Q1** and when the following triggers occur:

- Regulatory change (KVKK, secondary legislation, sectoral regulation),
- Change in critical technology used by the organization (e.g., migration to a new cloud provider),
- Processing of a new category of personal data begins (especially special-category data),
- After a data breach or near-miss event,
- Independent audit finding.

Versioning: **MAJOR.MINOR**. MAJOR is a change in policy scope; MINOR is a content update. All historical versions are kept under [12-mevzuat-arsiv/](../12-mevzuat-arsiv/).

---

## Türkçe

# 05 — Teknik Tedbirler

## 1. Amaç ve Kapsam

Bu bölüm, KVKK m.12 uyarınca veri sorumlusu sıfatıyla işlediğimiz kişisel verilerin **hukuka aykırı işlenmesini ve hukuka aykırı erişilmesini önlemek** ile **muhafazasını sağlamak** amacıyla aldığımız teknik tedbirleri bütüncül biçimde tanımlar. Tedbirler; on-prem, hibrit ve bulut (IaaS/PaaS/SaaS) ortamlarda işlenen tüm kişisel veri kategorilerini kapsar.

KVKK m.12(1) hükmü, "uygun güvenlik düzeyini temin etmeye yönelik gerekli her türlü teknik ve idari tedbirleri almak" yükümlülüğünü veri sorumlusuna açıkça yüklemektedir. **Uygun güvenlik düzeyi** tek bir mutlak eşik değildir; işlenen kişisel verinin niteliği, miktarı, ilgili kişi grubu, işleme amacı, teknik gelişmişlik düzeyi (state of the art) ve maliyet/fayda dengesi göz önüne alınarak belirlenir. Bu çerçeve **risk-tabanlı (risk-based)** bir yaklaşımdır ve GDPR Art. 32, NIST CSF ile ISO 27001'in temel mantığıyla örtüşür.

## 2. Bu Bölümdeki Dokümanlar

| # | Doküman | İçerik | Sahibi |
|---|---------|--------|--------|
| 1 | [erisim-kontrolu.md](erisim-kontrolu.md) | Least privilege, RBAC/ABAC, JML, PAM, erişim review | BT Operasyon + CISO |
| 2 | [kimlik-dogrulama.md](kimlik-dogrulama.md) | MFA, SSO/IdP, parola politikası, service account | IAM Ekibi |
| 3 | [sifreleme.md](sifreleme.md) | At-rest, in-transit, anahtar yönetimi, HSM/KMS, PQC | Kripto Mühendisliği + CISO |
| 4 | [ag-guvenligi.md](ag-guvenligi.md) | Segmentasyon, zero trust, FW/IDS/IPS/WAF, ZTNA | Ağ Güvenliği |
| 5 | [log-yonetimi.md](log-yonetimi.md) | Loglama, SIEM, UEBA, 5651, runbook | SOC + CISO |
| 6 | [yedekleme.md](yedekleme.md) | 3-2-1, immutable, restore test, DR/BCP, RTO/RPO | BT Operasyon |
| 7 | [veri-maskeleme-anonimlestirme.md](veri-maskeleme-anonimlestirme.md) | Masking, tokenization, anonim/pseudonim, k-anon | Veri Mühendisliği + KVKK |
| 8 | [dlp.md](dlp.md) | Endpoint/Network/Cloud DLP, CASB, çalışan mahremiyeti | DLP Ekibi + CISO |
| 9 | [uygulama-guvenligi.md](uygulama-guvenligi.md) | Secure SDLC, SAST/DAST/SCA, sızma testi, OWASP | AppSec |
| 10 | [teknik-tedbir-kontrol-listesi.md](teknik-tedbir-kontrol-listesi.md) | 80+ maddelik denetim listesi | İç Denetim |

## 3. Yönetişim ve Sorumluluk Modeli (RACI)

| Faaliyet | Yürüten (R) | Hesap Veren (A) | Danışılan (C) | Bilgi Verilen (I) |
|----------|-------------|-----------------|----------------|-------------------|
| Teknik tedbir politikalarının yazımı | CISO ekibi | CISO | KVKK Sorumlusu, Hukuk, BT Direktörü | Üst Yönetim |
| Politikaların onayı | CISO | BT Direktörü | KVKK Komitesi | Yönetim Kurulu |
| Operasyonel uygulama | İlgili teknik ekip | BT Operasyon Müdürü | CISO, KVKK Sorumlusu | İç Denetim |
| Ölçüm ve raporlama | SOC + CISO PMO | CISO | KVKK Komitesi | Üst Yönetim |
| İç denetim | İç Denetim | Denetim Komitesi | CISO, KVKK Sorumlusu | Yönetim Kurulu |
| Aksiyon takibi (CAPA) | İlgili sahipler | CISO | İç Denetim | KVKK Komitesi |

## 4. Risk-Tabanlı Tasarım İlkeleri

Teknik tedbirlerin tasarımında aşağıdaki ilkeler **istisnasız** uygulanır:

1. **Defence in Depth (Katmanlı Güvenlik):** Tek bir kontrolün başarısız olması verinin açığa çıkmasına yol açmamalıdır. Ağ → ana makine → uygulama → veri katmanlarında bağımsız kontroller.
2. **Least Privilege:** Her kullanıcı, servis hesabı ve uygulama, görevini yapmak için gereken **minimum** yetkiyle çalışır.
3. **Need-to-Know:** Kişisel veriye erişim yalnızca o veriyi görmesi iş gereği olan kişiyle sınırlıdır. Yetkili olmak ≠ erişmek.
4. **Default Deny:** Açıkça izin verilmeyen her erişim reddedilir.
5. **Zero Trust:** Hiçbir trafiğe ağ konumuna göre güven verilmez; her erişim talebi kimliği, cihazı, oturumu, davranışı doğrulanarak kabul edilir.
6. **Privacy by Design / Default (KVKK m.4 ölçülülük + GDPR Art. 25):** Veri minimizasyonu, amaç sınırlaması ve veri koruma önlemleri sistemin tasarımına gömülür, sonradan eklenmez.
7. **Crypto Agility:** Kullanılan algoritma ve anahtar boyutlarının güncellenmesini/değiştirilmesini engelleyecek bağımlılıklar yaratılmaz (özellikle PQC geçişi öncesi kritik).
8. **Fail Secure:** Bir bileşenin arızalanması, varsayılan olarak veriyi açığa çıkaran değil koruyan bir duruma yönelmelidir.
9. **Auditability:** Tüm güvenlik açısından önemli olaylar geri dönülemez biçimde kayıt altına alınır ve denetlenebilir.
10. **Minimization in Logs:** Log içeriği, tedbirin kendisinin amacını aşan kişisel veriyi içermemelidir.

## 5. KVKK Veri Güvenliği Rehberi ile Eşleşme

Kurum'un yayımladığı Kişisel Veri Güvenliği Rehberi, teknik tedbir başlıklarını aşağıdaki gibi gruplandırır. Bizim doküman setimiz bu yapıyı **birebir** kapsar ve ek olarak modern güvenlik standartlarına eşler:

| KVKK Rehberi Başlığı | Bu Bölümde Karşılığı | ISO 27002:2022 Kontrolü |
|----------------------|----------------------|-------------------------|
| Siber Güvenliğin Sağlanması | ag-guvenligi.md, uygulama-guvenligi.md | A.8.20–A.8.27 |
| Kişisel Veri Güvenliği Takibi | log-yonetimi.md | A.8.15, A.8.16, A.5.7 |
| Kişisel Veri İçeren Ortamların Güvenliği | sifreleme.md, ag-guvenligi.md | A.7.10, A.8.10, A.8.13 |
| Kişisel Verilerin Bulutta Depolanması | sifreleme.md, ag-guvenligi.md, tedarikci (06) | A.5.23 |
| Bilgi Teknolojileri Sistemleri Tedariği, Geliştirilmesi ve Bakımı | uygulama-guvenligi.md | A.8.25–A.8.34 |
| Kişisel Verilerin Yedeklenmesi | yedekleme.md | A.8.13 |
| Kullanıcı Hesap Yönetimi ve Yetki Matrisi | erisim-kontrolu.md, kimlik-dogrulama.md | A.5.15–A.5.18, A.8.2, A.8.3, A.8.5 |
| Şifreleme | sifreleme.md | A.8.24 |
| Veri Maskeleme | veri-maskeleme-anonimlestirme.md | A.8.11 |
| Saldırı Tespit ve Önleme Sistemleri | ag-guvenligi.md, log-yonetimi.md | A.8.16 |
| Sızma Testi | uygulama-guvenligi.md | A.8.29 |
| Bilgi Güvenliği Olay Yönetimi | log-yonetimi.md + 08-ihlal-yonetimi/ | A.5.24–A.5.28 |

## 6. Ölçüm ve KPI'lar

Teknik tedbirlerin etkinliği yalnızca "var/yok" düzleminde değerlendirilemez; **ölçülebilir** olmalıdır. Aşağıdaki gösterge seti yıllık güncellenir, çeyreklik raporlanır:

- Kritik açık kapatma süresi (MTTR-Critical) — hedef ≤ 7 gün.
- MFA kapsam yüzdesi — hedef %100 (yönetici, uzaktan erişim, kişisel veri içeren tüm uygulamalar).
- Yetkili hesap oranı (privileged user / total user) — hedef ≤ %5.
- Erişim review tamamlanma oranı — hedef %100 her çeyrek.
- Yedek geri yükleme test başarı oranı — hedef ≥ %99.
- Ortalama log toplama gecikmesi — hedef ≤ 5 dakika.
- SIEM kapsam (varlık envanteri içinde loglanan oranı) — hedef ≥ %95.
- Kritik sistem TLS uyumluluk oranı — hedef %100 TLS 1.2+ (1.3 tercihli).
- DLP olay false-positive oranı — hedef ≤ %20.
- Kapatılmamış JML (mover/leaver) eylemi — hedef 0 (24 saatten fazla bekleyen).

## 7. Bu Bölümün Diğer Bölümlerle İlişkisi

- **00-yonetisim/** — Politika onay zinciri ve roller burada tanımlanan tedbirleri yetkilendirir.
- **04-veri-saklama-ve-imha/** — Saklama süresi sona eren verilerin teknik imhası burada tanımlı şifreleme ve anahtar yönetimi süreçlerinden faydalanır (crypto-shredding).
- **06-idari-tedbirler/** — Tedarikçi yönetimi, eğitim ve politika çerçevesi teknik tedbirlerin "etkin uygulanmasını" sağlar.
- **08-ihlal-yonetimi/** — Log yönetimi ve SIEM tespitleri burayı besler.
- **11-denetim-ve-uyum/** — İç denetim, bu bölümün kontrol listelerini örnekleme yöntemiyle test eder.

## 8. Yıllık Gözden Geçirme

CISO, bu bölümün tüm dokümanlarını **her takvim yılı Q1'inde** ve aşağıdaki tetikleyiciler oluştuğunda gözden geçirir:

- Mevzuat değişikliği (KVKK, ikincil mevzuat, sektörel düzenleme),
- Kurumsal kullanılan kritik teknolojinin değişimi (örn. yeni bulut sağlayıcıya geçiş),
- Yeni bir kişisel veri kategorisi işlenmeye başlandığında (özellikle özel nitelikli),
- Veri ihlali veya ramak kala olayı sonrası,
- Bağımsız denetim bulgusu.

Versiyonlama: **MAJOR.MINOR**. MAJOR; politika kapsamının değişimi. MINOR; içerik güncellemesi. Geriye dönük tüm sürümler [12-mevzuat-arsiv/](../12-mevzuat-arsiv/) altında tutulur.
