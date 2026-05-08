---
Doküman / Document: İhlal Müdahale Prosedürü / Personal Data Breach Incident Response Procedure
Bölüm / Section: 08-ihlal-yonetimi
Sahip / Owner: Bilgi Güvenliği Müdürü (CISO) + KVKK Sorumlusu / CISO + KVKK Officer
Onaylayan / Approved by: Hukuk Müdürü + KVKK Komitesi + Yönetim Kurulu / Head of Legal + KVKK Committee + Board of Directors
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + her ihlal sonrası / Annual + after every incident
İlgili Mevzuat / Legal Reference: Law No. 6698 (KVKK) Art. 12; Authority Decision No. 2019/10 dated 24.01.2019; KVKK Data Security Guide (2018); Law No. 5651; NIST SP 800-61 Rev.2; ISO/IEC 27035-1:2023; ISO/IEC 27001:2022 A.5.24-A.5.28
---

## English

# Personal Data Breach Incident Response Procedure

## 1. Purpose and Scope

This procedure governs the management of the incident lifecycle from the moment a personal data breach is suspected or confirmed. It is aligned with NIST SP 800-61 Rev.2 and ISO/IEC 27035-1:2023, and operationalizes the requirements of Article 12 of KVKK and the Authority's Decision No. 2019/10 of 24.01.2019.

Scope: All personal data assets within the company, company data held by data processors, employee endpoints, customer portals, websites, and mobile applications.

## 2. Incident Management Lifecycle

```
[Preparation] -> [Detection & Analysis] -> [Containment]
                                                |
[Lessons Learned] <- [Recovery] <- [Eradication]
```

Each phase is logged; phase transitions are made by Incident Commander (IC) decision.

### 2.1. Preparation

Before any process begins, the following must be in place:

- 24/7 reachable CSIRT contact list (mobile, registered electronic mail (KEP), back-up channel - Signal/WhatsApp).
- Out-of-band communication (alternative if the mail server is breached).
- Forensic toolkit (write-blocker, imager, EnCase/FTK license).
- Framework agreement with third-party forensic firms (response retainer).
- Legal counsel and crisis communication agency contacts.
- Incident classification matrix (§3).
- Runbooks (§7).
- Tabletop schedule (`soak-test-tatbikat.md`).

### 2.2. Detection & Analysis

**Detection sources:**

- SIEM correlation rules (Splunk/Sentinel/Wazuh).
- EDR/XDR alerts (CrowdStrike/SentinelOne/Defender).
- DLP events (unauthorized exfiltration).
- IDS/IPS (Suricata, Snort).
- Honeypot/canary token triggers.
- Employee reports (ethics line, IT helpdesk).
- Third-party notifications (CERT, customer, researcher, press).
- Processor notification.
- Dark web monitoring (HaveIBeenPwned, threat intel).

**Initial analysis outputs (within T+1 hour):**

- Detection time (UTC + Türkiye Time).
- First observed system/asset.
- Suspected event type (ransomware, BEC, data exfil, insider, lost device, scraping).
- Likely affected data category (general, special category, financial).
- Lateral movement risk indicators.

### 2.3. Containment

Two-tiered approach:

- **Short-term containment (T+2 - T+4 hours):** Isolate the affected system from the network (NAC/firewall), disable the user account, stop sharing. Do **not power off** - to preserve memory image.
- **Long-term containment (T+8 - T+72 hours):** Stand up temporary systems, reset passwords, harden role-based segmentation, enforce MFA broadly.

**Decision matrix:**

| Criterion | Quick power-off | Forensics first |
|-----------|-----------------|-----------------|
| Active data exfil | Yes | No |
| Lateral movement observed | Yes | No |
| Service is critical (production) | Isolate | Isolate + parallel forensics |
| Attacker still inside | Yes - urgent isolation | No |
| Attack ended | No | Yes |

### 2.4. Eradication

- Remove malware (image redeploy preferred).
- Clean backdoors and persistence (scheduled tasks, services, registry, cron).
- IOC-based scan across the entire fleet.
- Revoke threat-actor accounts.
- Rotate stolen credentials (passwords, API keys, SSH keys, OAuth tokens, certificates).

### 2.5. Recovery

- Clean restore from backup (verify the backup itself is unaffected).
- Phased return to production (canary deploy, increased monitoring).
- Gradual reopening of user access.
- 30-90 days of enhanced monitoring.

### 2.6. Lessons Learned

- Post-Incident Report (PIR) within **T+30 days**.
- Root cause analysis (`kok-neden-analizi.md`).
- CAPA (Corrective and Preventive Actions) tracking list.
- Updates to policies, procedures, training.
- Add to tabletop scenario library.

## 3. Incident Classification Matrix (Triage)

The breach decision is scored on **four axes**:

### 3.1. Number of Data Subjects Affected (E)

| Range | Score |
|-------|-------|
| 1 - 100 | 1 |
| 101 - 1,000 | 2 |
| 1,001 - 10,000 | 3 |
| 10,001 - 100,000 | 4 |
| > 100,000 | 5 |

### 3.2. Data Sensitivity (H)

| Category | Score |
|----------|-------|
| Marketing preference | 1 |
| Identity + contact | 2 |
| Financial (IBAN, masked card) | 3 |
| Card number / ID copy / location | 4 |
| Special category (health, biometric, religion, criminal) | 5 |

### 3.3. Spread Risk (Y)

| Status | Score |
|--------|-------|
| System isolated, externally closed | 1 |
| Lateral movement potential within internal network | 3 |
| Internet-facing, data already external | 5 |

### 3.4. Reversibility (G)

| Status | Score |
|--------|-------|
| Only integrity affected, restorable from backup | 1 |
| Data may have been copied but not published | 3 |
| Data already published / on dark web | 5 |

**Total Risk Score = E + H + Y + G** (range 4-20)

| Score | Class | Action |
|-------|-------|--------|
| 4-7 | Low | Incident report, breach assessment performed; notification mostly **not required** |
| 8-12 | Medium | Breach assessment mandatory; Authority notification very likely |
| 13-16 | High | Authority notification mandatory + data subject notification |
| 17-20 | Critical | Authority + data subjects + press statement + executive escalation |

> **Caution:** A low score does not mean automatic exemption. When special category data is involved, notification is preferred regardless of score.

## 4. CSIRT Structure (Computer Security Incident Response Team)

### 4.1. Core Team

| Position | Role | Primary Responsibility |
|----------|------|------------------------|
| Incident Commander (IC) | Decision authority | Overall coordination, escalation |
| Technical Lead | Forensics & analysis | Imaging, logs, IOCs, attribution |
| KVKK Officer | Regulatory | Authority notification, data subject communication |
| Legal Lead | Legal risk | Contractual, criminal, regulatory |
| Corporate Communications | External communications | Press, social media, customers |
| HR Lead | Insider threat | Discipline, employee communications |
| IT Operations | System administration | Isolation, recovery |

### 4.2. Extended Team

Support roles called in by Core CSIRT: Finance (ransom, insurance), Sales (customer impact), Supply Chain (third party), Product/CTO (architectural decisions), External Forensics Firm, External Counsel, Insurer (cyber policy), CEO/CFO escalation.

### 4.3. CSIRT Activation

Activation thresholds:

- **Level 1 (Information):** Risk score 4-7. Email thread for KVKK + CISO + Legal only.
- **Level 2 (Virtual meeting):** Risk score 8-12. Core team joins within 1 hour.
- **Level 3 (Full activation):** Risk score 13+. Core team in physical/virtual war room within 30 minutes. Extended team alerted.
- **Level 4 (Crisis):** Risk score 17+. Board informed; press coordination.

## 5. Communication Tree

```
Detecting employee
        |
IT Helpdesk (24/7 on-call - ethics line)
        |
SOC L1 -> SOC L2 (15-minute SLA)
        |
Information Security Shift Lead (30-minute SLA)
        |
CISO + KVKK Officer (60-minute SLA - dual notification)
        |
Incident Commander assigned
        |
CSIRT activation (level-based)
        |
Executive escalation (Level 3+: CEO; Level 4: Board)
        |
External stakeholder communication (Authority, data subjects, press, insurer)
```

**Communication channels:**

- Primary: Corporate e-mail + telephone.
- Secondary (if e-mail system affected): Corporate Signal group.
- Tertiary: Personal mobile + WhatsApp.
- Out-of-band: Conference bridge (third-party - Webex/Teams alternative).

**Silence rule (Need-to-Know):** Incident details are shared only within CSIRT. Internal announcements require dual approval from CISO + Corporate Communications. Social media posting is forbidden (binding under employee code of conduct).

## 6. Incident Log

Every incident is numbered **OLAY-YYYY-NNNN** (Turkish "olay" = incident). The following fields are recorded with minute-level precision:

| Field | Description |
|-------|-------------|
| Incident ID | Auto-generated |
| Detection date/time | UTC + Türkiye Time, minute-level |
| Awareness moment | When the "reasonable suspicion" threshold was crossed (72-hour clock) |
| Detection source | SIEM, EDR, tip-off, etc. |
| Category | Ransomware, BEC, exfil, lost device, insider, third party |
| Affected system | Hostname, IP, application, database |
| Affected data | Category + estimated record count |
| Risk score | E+H+Y+G |
| Class | Low/Medium/High/Critical |
| Activation level | 1-4 |
| Incident Commander | Name |
| Phase | Preparation/Detection/Containment/Eradication/Recovery/Closure |
| Main actions chronological | Hourly entry |
| Authority notification | Date/time/reference no. |
| Data subject notification | Method/count/date |
| Insurer notification | Date |
| Criminal notification (if any) | Date/prosecutor |
| Closure date | When RCA is complete |

The log must be **immutable** (write-once, tamper-evident - Splunk Enterprise SIEM, Wazuh + S3 Object Lock, etc.).

## 7. Scenario-Based Runbooks

Detailed runbooks have been produced and tested in tabletops for the seven scenarios below. Summary decision paths are given here; full runbooks live under `99-sablonlar/runbooks/`.

### 7.1. Runbook A - Ransomware

```
T+0       Encrypted files/screen detected
T+15 min  Isolate affected machine from network; do NOT power off
T+30 min  EDR scan - lateral movement check
T+1 hour  Verify backup integrity (offline backup)
T+2 hour  Isolate attacker communication channel
T+4 hour  Forensic imaging starts
T+8 hour  Affected personal data scope (DLP report, folder content analysis)
T+24 hour Authority preliminary notification
T+48 hour Restore from backup + canary
T+72 hour Authority final notification
```

**Critical decisions:**

- Ransom is not paid (Board decision + OFAC/sanctions compliance).
- Decryption tool databases are checked (No More Ransom).
- Insurance policy is activated (T+12 hours).

### 7.2. Runbook B - Insider Data Exfiltration

```
T+0       DLP/UEBA alert - abnormal download/USB/upload
T+15 min  IT - silently observe user session (live evidence)
T+30 min  HR and Legal coordination
T+1 hour  Permission freeze decision (without alerting user)
T+2 hour  Endpoint review - what was taken, where it went
T+4 hour  Conversation with user (HR + Legal + HR Director)
T+8 hour  Forensic imaging of device
T+24 hour Data recall (cease and desist if third parties involved)
T+48 hour Criminal process assessment (Turkish Criminal Code Art. 136)
T+72 hour Authority notification
```

### 7.3. Runbook C - Lost / Stolen Device

```
T+0       Employee reports lost/stolen device
T+15 min  Remote lock via MDM
T+30 min  Verify device is encrypted (BitLocker/FileVault status)
T+1 hour  If unencrypted, treat as HIGH risk
T+2 hour  Reset account passwords, revoke MFA tokens
T+4 hour  Analyze e-mail cache, OneDrive sync, recent activity
T+8 hour  Determine content scope
T+12 hour Police lost-device report (mandatory)
T+24 hour Remote wipe command (if not returned)
T+72 hour Authority notification (if device was unencrypted)
```

### 7.4. Runbook D - Third-Party Breach (Vendor/Processor)

```
T+0       Processor notifies a breach
T+15 min  Contract check - within notification SLA?
T+30 min  Scope: which company data is affected?
T+1 hour  Temporary suspension decision
T+2 hour  Independent verification request
T+4 hour  Internal impact mapping
T+24 hour Authority notification (WE notify, as data controller)
T+48 hour Contractual sanction; alternative provider plan
```

> **Important:** Late notification by the processor is no excuse - vis-a-vis the Authority, the controller is responsible. The contract must include a **24-hour notification clause** plus a delay penalty (`07-aktarim` section).

### 7.5. Runbook E - BEC / Account Takeover (Business Email Compromise)

```
T+0       Abnormal e-mail send/forward detected
T+15 min  Kill account session, password reset, MFA reset
T+30 min  Inbox rule/forwarder cleanup
T+1 hour  Audit log - sent emails, opened shares
T+2 hour  Sensitive content detection (KVKK + finance)
T+4 hour  Counter-party notification (fraud prevention)
T+8 hour  Rotate API keys for SaaS the account accessed
T+24 hour Authority notification (if mail traffic with personal data was affected)
```

### 7.6. Runbook F - Website / API Data Leak (Scraping / Public Leak)

```
T+0       Company data discovered on GitHub/Pastebin/forum
T+15 min  Source verification - is it really ours?
T+30 min  DMCA / takedown request
T+1 hour  Leak vector (which endpoint, which parameter)
T+2 hour  Endpoint shutdown / WAF rule
T+4 hour  Access log analysis - scope
T+24 hour Authority notification
T+48 hour Data subject notification (e-mail, SMS, web)
```

### 7.7. Runbook G - Physical Breach (Archive/Document Loss)

```
T+0       Physical archive loss/fire/flood
T+30 min  Controlled access to scene
T+1 hour  Identify missing categories/file types
T+2 hour  CCTV review (intentional or accidental?)
T+8 hour  Determine scope - which data subjects?
T+24 hour Authority notification if required
```

## 8. Hourly Decision Matrix

| Hour | Action | Owner | Output |
|------|--------|-------|--------|
| T+0 | Open incident, assign ID | SOC | OLAY-YYYY-NNNN |
| T+15 min | Urgent containment decision | Shift Lead | Isolation or observation |
| T+30 min | Core CSIRT informed | CISO | Activation level |
| T+1 hour | Initial triage report | IC | Risk score, class |
| T+2 hour | War room meeting | IC | Phase plan, assignments |
| T+4 hour | Containment approval | IC + CISO | Isolation confirmed |
| T+8 hour | Preliminary scope report | Technical Lead | Data category + estimated count |
| T+12 hour | Insurer notification | Legal + Finance | Policy activation |
| T+24 hour | Authority preliminary notification (incomplete OK) | KVKK Officer | Form submitted |
| T+48 hour | Data subject notification draft | KVKK + Communications | Pending approval text |
| T+72 hour | Authority final notification (definitive data) | KVKK Officer | Form supplemented |
| T+5 days | Data subject notification begins | KVKK + Communications | E-mail/SMS dispatch |
| T+15 days | Phased recovery complete | Operations | Production normalized |
| T+30 days | Post-Incident Report (PIR) | IC | Report + CAPA list |
| T+90 days | CAPA completion audit | KVKK Officer | Closure report |
| T+1 year | Add to tabletop scenarios | Exercise Lead | New scenario |

## 9. Forensic Evidence Management

- Chain-of-custody form for every device/log set.
- Hash (SHA-256) verification for integrity.
- Evidence stored in **insured safe** (physical) and **immutable storage** (digital).
- Evidence retention: **5 years** (statute of limitations + administrative sanction objection windows).
- Third-party forensic firms sign NDA + KVKK data processor agreement.

## 10. Processor Notification Obligation (We Are the Data Controller)

Data processors (cloud provider, outsourcer, HR SaaS, courier, call center):

- Must notify us **within 24 hours** by contract.
- Notification arrives via KEP or contractually defined channel.
- Insufficient notification triggers contractual penalty and unilateral termination right.
- A processor's late notification is **not added** to our 72-hour clock - the clock starts at **our awareness moment**; however, the Authority may also hold the controller responsible (citing inadequate contractual control).

## 11. Correspondence Standards with the Authority

- Notifications are sent via KEP to **kvkk@hs01.kep.tr**.
- Missing information may be supplemented later, but the first notification is filed at the **highest fillable completeness**.
- If the Authority requests further information, the response window is **15 days** from notification (specified in the Authority's letter).
- All correspondence is archived and recorded in the **Authority Correspondence Log**.

## 12. Criminal Notification and Other Regulators

Other obligations to consider alongside KVKK notification:

- **Turkish Criminal Code Art. 136-138:** Unlawfully obtaining/disclosing data - prosecutorial referral (especially for insider threats).
- **Law No. 5651:** Access/host provider record obligations.
- **BRSA / CMB / EMRA:** Sectoral breach notification regimes (banking, capital markets, energy).
- **GDPR (if foreign data subjects are affected):** 72-hour notification to the relevant DPA via the EU representative if any.
- **EMRA / ICTA:** Additional notification obligations in the telecom sector.

## 13. Training and Awareness

- All employees: 1 hour annual incident reporting training.
- IT/SOC: 4 hours quarterly technical response drill.
- CSIRT core team: 16 hours annual tabletop + 8 hours physical drill.
- Board: 1 hour annual crisis management briefing.

## 14. Version History

| Version | Date | Change | Approval |
|---------|------|--------|----------|
| 1.0 | 2026-05-08 | First publication | KVKK Committee + Board |

## 15. Annexes

- Annex 1: CSIRT Contact List (controlled access).
- Annex 2: Incident Classification Decision Tree (single-page A3).
- Annex 3: Forensic Bag Contents List.
- Annex 4: Insurer Notification Template.
- Annex 5: Authority KEP Correspondence Template.

---

## Türkçe

# İhlal Müdahale Prosedürü

## 1. Amaç ve Kapsam

Bu prosedür, kişisel veri ihlali şüphesi veya kesinleşmiş ihlal anında olay yaşam döngüsünün yönetilmesini düzenler. NIST SP 800-61 Rev.2 ve ISO/IEC 27035-1:2023 ile uyumludur ve KVKK'nın 12. maddesi ile Kurul'un 24.01.2019/2019-10 sayılı Kararı'nın gereklerini iç sürece bağlar.

Kapsam: Şirket bünyesindeki tüm kişisel veri varlıkları, veri işleyenler nezdindeki şirket verileri, çalışan kullanım cihazları, müşteri portalları, web siteleri ve mobil uygulamalar.

## 2. Olay Yönetimi Yaşam Döngüsü

```
┌──────────────┐    ┌──────────────────┐    ┌────────────────┐
│  Hazırlık    │ →  │ Tespit ve Analiz │ →  │ Sınırlandırma  │
└──────────────┘    └──────────────────┘    └────────────────┘
                                                    ↓
┌──────────────────┐    ┌──────────────┐    ┌────────────────┐
│ Ders Çıkarma     │ ←  │ Kurtarma     │ ←  │ Yok Etme       │
└──────────────────┘    └──────────────┘    └────────────────┘
```

Her aşama kayıt altına alınır; aşama geçişleri Olay Komutanı kararıyla yapılır.

### 2.1. Hazırlık (Preparation)

Süreç başlamadan önce şu unsurların hazır olması gerekir:
- 7/24 ulaşılabilir CSIRT iletişim listesi (cep, KEP, yedek kanal — Signal/WhatsApp).
- Out-of-band iletişim (mail sunucusu ihlal edilirse alternatif).
- Forensik araç seti (write-blocker, imaj alıcı, EnCase/FTK lisans).
- 3. taraf forensik firmaları ile çerçeve sözleşme (response retainer).
- Hukuki danışman ve kriz iletişim ajansı bağlantıları.
- Olay sınıflandırma matrisi (§3).
- Runbook'lar (§7).
- Tatbikat takvimi (`soak-test-tatbikat.md`).

### 2.2. Tespit ve Analiz (Detection & Analysis)

**Tespit kaynakları:**
- SIEM korelasyon kuralları (Splunk/Sentinel/Wazuh).
- EDR/XDR alarmları (CrowdStrike/SentinelOne/Defender).
- DLP olayları (yetkisiz dışa aktarım).
- IDS/IPS (Suricata, Snort).
- Honeypot/canary token tetiklemeleri.
- Çalışan ihbarları (etik hat, IT helpdesk).
- Üçüncü taraf bildirimleri (CERT, müşteri, araştırmacı, basın).
- Veri işleyen bildirimi.
- Dark web izleme (HaveIBeenPwned, threat intel).

**İlk analiz çıktıları (T+1 saat içinde):**
- Tespit zamanı (UTC + TRT).
- İlk gözlemlenen sistem/varlık.
- Şüpheli olay tipi (ransomware, BEC, data exfil, içeriden, kayıp cihaz, scraping).
- Etkilenmesi muhtemel veri kategorisi (genel, özel nitelikli, finansal).
- Yayılma riski (yatay hareket göstergeleri).

### 2.3. Sınırlandırma (Containment)

İki katmanlı yaklaşım:
- **Kısa vadeli sınırlandırma (T+2 - T+4 saat):** Etkilenen sistemi ağdan izole et (NAC/firewall), kullanıcı hesabını disable et, paylaşımı durdur. Sistemi **kapatma** — bellek imajı için.
- **Uzun vadeli sınırlandırma (T+8 - T+72 saat):** Geçici sistemler kur, parolaları sıfırla, yetki bazlı segmentasyonu sıkılaştır, MFA zorunluluğu yay.

**Karar matrisi:**
| Kriter | Hızlı kapatma | Forensik öncelikli |
|--------|---------------|---------------------|
| Aktif veri exfil | ✅ | ❌ |
| Yatay hareket gözlendi | ✅ | ❌ |
| Hizmet kritik (üretim) | İzolasyon | İzole + paralel forensik |
| Saldırgan hâlâ içeride | ✅ acil izolasyon | ❌ |
| Saldırı bitmiş | ❌ | ✅ |

### 2.4. Yok Etme (Eradication)

- Zararlı yazılımı kaldırma (image yeniden yükleme tercih edilir).
- Backdoor, persistence mekanizmalarını temizleme (scheduled tasks, services, registry, cron).
- IOC bazlı tarama tüm filo.
- Tehdit aktörü hesaplarının iptali.
- Çalınan kimlik bilgileri rotation (parola, API key, SSH key, OAuth token, sertifika).

### 2.5. Kurtarma (Recovery)

- Yedekten temiz geri yükleme (yedeğin de etkilenmediğinden emin ol).
- Aşamalı üretime alma (canary deploy, monitoring artırılmış).
- Kullanıcı erişimlerinin kademeli açılması.
- 30-90 gün artırılmış izleme.

### 2.6. Ders Çıkarma (Lessons Learned)

- Olay sonrası rapor (Post-Incident Report — PIR) en geç **T+30 gün**.
- Kök neden analizi (`kok-neden-analizi.md`).
- CAPA (Corrective and Preventive Actions) takip listesi.
- Politika, prosedür, eğitim güncellemesi.
- Tatbikat senaryosuna ekleme.

## 3. Olay Sınıflandırma Matrisi (Triyaj)

İhlal kararı şu **dört eksen** üzerinden puanlanır:

### 3.1. Etkilenen Kişi Sayısı (E)
| Aralık | Puan |
|--------|------|
| 1 - 100 | 1 |
| 101 - 1.000 | 2 |
| 1.001 - 10.000 | 3 |
| 10.001 - 100.000 | 4 |
| > 100.000 | 5 |

### 3.2. Veri Hassasiyeti (H)
| Kategori | Puan |
|----------|------|
| Pazarlama tercih | 1 |
| Kimlik + iletişim | 2 |
| Finansal (IBAN, kart maskeli) | 3 |
| Kart numarası / kimlik kopyası / lokasyon | 4 |
| Özel nitelikli (sağlık, biyometrik, din, ceza) | 5 |

### 3.3. Yayılma Riski (Y)
| Durum | Puan |
|-------|------|
| Sistem izole, dışa kapalı | 1 |
| İç ağda lateral hareket potansiyeli | 3 |
| İnternete açık, veri çoktan dışarıda | 5 |

### 3.4. Geri Döndürülebilirlik (G)
| Durum | Puan |
|-------|------|
| Veri sadece bütünlük etkilendi, yedekten geri alınabilir | 1 |
| Veri kopyalanmış olabilir ama yayımlanmamış | 3 |
| Veri zaten yayımlanmış / dark web'de | 5 |

**Toplam Risk Skoru = E + H + Y + G** (4-20 arası)

| Skor | Sınıf | Eylem |
|------|-------|-------|
| 4-7 | Düşük | Olay raporu, ihlal değerlendirmesi yap, çoğunlukla bildirim **gerekmez** |
| 8-12 | Orta | İhlal değerlendirmesi zorunlu, Kurul bildirimi büyük olasılık |
| 13-16 | Yüksek | Kurul bildirimi zorunlu + ilgili kişi bildirimi |
| 17-20 | Kritik | Kurul + ilgili kişi + basın açıklaması + üst yönetim eskalasyonu |

> **Uyarı:** Düşük skor otomatik bildirim muafiyeti değildir. Özel nitelikli veriler söz konusuysa kategoriden bağımsız bildirim eğilimi tercih edilir.

## 4. CSIRT Yapısı (Computer Security Incident Response Team)

### 4.1. Çekirdek Ekip (Core Team)

| Pozisyon | Rol | Ana Sorumluluk |
|----------|-----|----------------|
| Olay Komutanı (IC) | Karar mercii | Tüm operasyonun koordinasyonu, eskalasyon |
| Teknik Lider | Forensik & Analiz | İmaj, log, IOC, attribution |
| KVKK Sorumlusu | Düzenleyici | Kurul bildirimi, ilgili kişi iletişimi |
| Hukuk Lideri | Hukuki risk | Sözleşmesel, cezai, regülatif |
| Kurumsal İletişim | Dış iletişim | Basın, sosyal medya, müşteri |
| İK Lideri | İçeriden tehdit | Disiplin, çalışan iletişim |
| Bilgi İşlem Operasyon | Sistem yöneticisi | İzolasyon, kurtarma |

### 4.2. Genişletilmiş Ekip (Extended Team)

Ana CSIRT'in çağıracağı destek rolleri: Finans (fidye, sigorta), Satış (müşteri etkisi), Tedarik Zinciri (3. taraf), Ürün/CTO (mimari karar), Dış Forensik Firma, Dış Hukuk Firması, Sigortacı (siber poliçe), CEO/CFO eskalasyon.

### 4.3. CSIRT Aktivasyonu

Aktivasyon eşikleri:
- **Seviye 1 (Bilgilendirme):** Risk skoru 4-7. Sadece KVKK + CISO + Hukuk e-posta zinciri.
- **Seviye 2 (Sanal toplantı):** Risk skoru 8-12. Çekirdek ekip 1 saat içinde bağlanır.
- **Seviye 3 (Tam aktivasyon):** Risk skoru 13+. Çekirdek ekip 30 dakika içinde fiziksel/sanal "war room"da. Genişletilmiş ekip alarmı.
- **Seviye 4 (Krizi):** Risk skoru 17+. Yönetim Kurulu bilgilendirilir, basın koordinasyonu.

## 5. Komünikasyon Ağacı

```
Tespit eden çalışan
        ↓
IT Helpdesk (7/24 nöbet — etik hat)
        ↓
SOC L1 → SOC L2 (15 dk SLA)
        ↓
Bilgi Güvenliği Vardiya Lideri (30 dk SLA)
        ↓
CISO + KVKK Sorumlusu (60 dk SLA — dual notification)
        ↓
Olay Komutanı atanır
        ↓
CSIRT aktivasyonu (seviye bazlı)
        ↓
Yönetim eskalasyonu (Seviye 3+: CEO; Seviye 4: Yönetim Kurulu)
        ↓
Dış paydaş iletişimi (Kurul, ilgili kişi, basın, sigortacı)
```

**İletişim kanalları:**
- Birincil: Kurumsal e-posta + Telefon.
- İkincil (e-posta sistemi etkilendiyse): Kurumsal Signal grubu.
- Üçüncül: Kişisel cep + WhatsApp.
- Out-of-band: Konferans köprü (3. taraf — Webex/Teams alternatifi).

**Sessizlik kuralı (Need-to-Know):** Olay detayları sadece CSIRT içinde paylaşılır. İç duyuru CISO + Kurumsal İletişim çift onayı olmadan yapılmaz. Sosyal medya paylaşımı yasaktır (çalışan etik kurallarına bağlı).

## 6. Olay Kayıt Sistemi (Incident Log)

Her olay anında **OLAY-YYYY-NNNN** formatında numaralandırılır. Aşağıdaki bilgiler dakika hassasiyetinde kaydedilir:

| Alan | Açıklama |
|------|----------|
| Olay No | Otomatik üretilen ID |
| Tespit Tarih/Saat | UTC + TRT, dakika hassasiyetinde |
| Öğrenme Anı | "Makul şüphe" eşiğinin geçildiği an (72 saat sayacı) |
| Tespit Kaynağı | SIEM, EDR, ihbar, vb. |
| Kategori | Ransomware, BEC, exfil, kayıp cihaz, içeriden, üçüncü taraf |
| Etkilenen Sistem | Hostname, IP, uygulama, veritabanı |
| Etkilenen Veri | Kategori + tahmini kayıt sayısı |
| Risk Skoru | E+H+Y+G |
| Sınıf | Düşük/Orta/Yüksek/Kritik |
| Aktivasyon Seviyesi | 1-4 |
| Olay Komutanı | İsim |
| Aşama | Hazırlık/Tespit/Sınırlandırma/Yok Etme/Kurtarma/Kapanış |
| Ana eylemler kronolojik | Saatlik girdi |
| Kurul bildirimi | Tarih/saat/referans no |
| İlgili kişi bildirimi | Yöntem/sayı/tarih |
| Sigortacı bildirimi | Tarih |
| Adli bildirim (gerekiyorsa) | Tarih/savcılık |
| Kapanış tarihi | RCA tamamlandığında |

Kayıt sistemi **immutable** olmalıdır (write-once, tamper-evident — Splunk Enterprise SIEM, Wazuh + S3 Object Lock, vb.).

## 7. Senaryo Bazlı Runbook'lar

Aşağıdaki yedi senaryo için detaylı runbook üretilmiş ve tatbikatlarda test edilmiştir. Bu bölümde özet karar yolu verilmiştir; tam runbook'lar `99-sablonlar/runbooks/` altındadır.

### 7.1. Runbook A — Ransomware

```
T+0  Şifrelenmiş dosya/ekran tespiti
T+15 dk  Etkilenen makineyi ağdan izole, KAPATMA
T+30 dk  EDR taraması — yayılma kontrolü
T+1 saat  Yedeklerin sağlamlığı doğrula (offline backup)
T+2 saat  Saldırgan iletişim kanalını izole (T2T)
T+4 saat  Forensik imaj alımı başlar
T+8 saat  Etkilenen kişisel veri kapsamı (DLP raporu, klasör içerik analizi)
T+24 saat  Kurul taslak bildirimi
T+48 saat  Yedekten kurtarma + canary
T+72 saat  Kurul nihai bildirimi
```

**Kritik kararlar:**
- Fidye ödenmez (yönetim kurulu kararı + OFAC/yaptırım uyumu).
- Decryption tool veritabanları kontrol edilir (No More Ransom).
- Sigorta poliçesi devreye alınır (T+12 saat).

### 7.2. Runbook B — İçeriden Veri Sızıntısı (Insider Data Exfiltration)

```
T+0  DLP/UEBA alarmı — anormal indirme/USB/upload
T+15 dk  IT — kullanıcı oturumunu sessizce izle (canlı kanıt)
T+30 dk  İK ve Hukuk koordinasyonu
T+1 saat  Yetki dondurma kararı (kullanıcı haberdar olmadan)
T+2 saat  Endpoint inceleme — neyin alındığı, nereye gönderildiği
T+4 saat  Kullanıcıyla görüşme (HR + Hukuk + İK Direktörü)
T+8 saat  Cihaz forensik imajı
T+24 saat  Veri geri çağırma (üçüncü taraflarsa cease-and-desist)
T+48 saat  Adli süreç değerlendirmesi (TCK m.136 verileri hukuka aykırı verme)
T+72 saat  Kurul bildirimi
```

### 7.3. Runbook C — Kayıp/Çalıntı Cihaz (Lost Device)

```
T+0  Çalışan kayıp/çalıntı bildirir
T+15 dk  MDM ile uzaktan kilit
T+30 dk  Cihaz şifrelenmiş mi doğrula (BitLocker/FileVault status)
T+1 saat  Şifrelenmemişse YÜKSEK risk
T+2 saat  Hesap parolası sıfırla, MFA token iptali
T+4 saat  E-posta cache, OneDrive sync, son aktiviteler analizi
T+8 saat  İçerik kapsamı belirleme
T+12 saat  Karakola kayıp ihbarı (zorunlu)
T+24 saat  Cihaz silinme komutu (geri dönmedi)
T+72 saat  Kurul bildirimi (şifrelenmemiş cihazsa)
```

### 7.4. Runbook D — Üçüncü Taraf İhlali (Vendor/Processor Breach)

```
T+0  Veri işleyenden ihlal bildirimi geldi
T+15 dk  Sözleşme kontrolü — bildirim süresine uyumlu mu?
T+30 dk  Kapsam: hangi şirket verisi etkilenmiş?
T+1 saat  Geçici askıya alma kararı
T+2 saat  Bağımsız doğrulama talebi
T+4 saat  Şirket içi etki haritalama
T+24 saat  Kurul bildirimi (veri sorumlusu olarak BİZ bildiriyoruz)
T+48 saat  Sözleşmesel yaptırım, alternatif sağlayıcı planı
```

> **Önemli:** Veri işleyenin geç bildirimi mazeret değildir — Kurul nezdinde sorumluluk veri sorumlusunundur. Sözleşmeye **24 saat içinde bildirim** klozu ve gecikme cezası eklenmiş olmalıdır (`07-aktarim` bölümü).

### 7.5. Runbook E — BEC / Hesap Ele Geçirme (Business Email Compromise)

```
T+0  Anormal e-posta gönderim/yönlendirme tespit
T+15 dk  Hesap session kill, parola reset, MFA reset
T+30 dk  Inbox rule/forwarder temizliği
T+1 saat  Audit log — gönderilen mailler, açılan paylaşımlar
T+2 saat  Hassas içerik tespiti (KVKK + finans)
T+4 saat  Karşı taraf bildirimi (fraud önleme)
T+8 saat  Hesabın eriştiği SaaS API key rotation
T+24 saat  Kurul bildirimi (kişisel veri içeren mail trafiği etkilendiyse)
```

### 7.6. Runbook F — Web Sitesi / API Veri Sızıntısı (Scraping / Public Leak)

```
T+0  GitHub/Pastebin/forum'da şirket verisi keşfi
T+15 dk  Kaynak doğrulama — gerçekten bizim mi?
T+30 dk  DMCA / takedown talebi
T+1 saat  Sızıntı vektörü (hangi endpoint, hangi parametre)
T+2 saat  Endpoint kapatma / WAF kuralı
T+4 saat  Erişim log analizi — kapsam
T+24 saat  Kurul bildirimi
T+48 saat  İlgili kişi bildirimi (eposta, SMS, web)
```

### 7.7. Runbook G — Fiziksel İhlal (Arşiv/Belge Kaybı)

```
T+0  Fiziksel arşiv eksiklik/yangın/su baskını
T+30 dk  Olay yerine kontrollü erişim
T+1 saat  Eksik kategori/dosya tipi tespiti
T+2 saat  CCTV inceleme (kasıt mı, kaza mı?)
T+8 saat  Kapsam belirleme — hangi ilgili kişi?
T+24 saat  Gerekirse Kurul bildirimi
```

## 8. Saatlik Karar Matrisi

| Saat | Yapılması Gereken | Sahip | Çıktı |
|------|-------------------|-------|-------|
| T+0 | Olay açılır, ID atanır | SOC | OLAY-YYYY-NNNN |
| T+15 dk | Acil sınırlandırma kararı | Vardiya Lideri | İzolasyon ya da gözlem |
| T+30 dk | Çekirdek CSIRT haberdar | CISO | Aktivasyon seviyesi |
| T+1 saat | İlk triyaj raporu | Olay Komutanı | Risk skoru, sınıf |
| T+2 saat | War room toplantısı | IC | Aşama planı, görev dağılımı |
| T+4 saat | Sınırlandırma onayı | IC + CISO | İzolasyon doğrulandı |
| T+8 saat | Kapsam ön raporu | Teknik Lider | Veri kategorisi + sayı tahmini |
| T+12 saat | Sigortacı bildirimi | Hukuk + Finans | Poliçe aktivasyonu |
| T+24 saat | Kurul taslak bildirimi (eksik veri kabul) | KVKK Sorumlusu | Form gönderildi |
| T+48 saat | İlgili kişi bildirim taslağı | KVKK + İletişim | Onay bekleyen metin |
| T+72 saat | Kurul nihai bildirimi (kesin veri) | KVKK Sorumlusu | Form ek bilgi |
| T+5 gün | İlgili kişi bildirimi başlar | KVKK + İletişim | E-posta/SMS gönderim |
| T+15 gün | Aşamalı kurtarma tamamlandı | Operasyon | Üretim normal |
| T+30 gün | Post-Incident Report (PIR) | IC | Rapor + CAPA listesi |
| T+90 gün | CAPA tamamlanma denetimi | KVKK Sorumlusu | Kapanış raporu |
| T+1 yıl | Tatbikat senaryosuna işleme | Tatbikat Lideri | Yeni senaryo |

## 9. Forensik Kanıt Yönetimi

- Chain of custody formu her cihaz/log seti için doldurulur.
- Hash (SHA-256) doğrulamasıyla bütünlük teyit edilir.
- Kanıtlar **sigortalı kasada** (fiziksel kanıt) ve **immutable storage'da** (dijital kanıt) saklanır.
- Kanıt saklama süresi: **5 yıl** (zamanaşımı + idari yaptırım itiraz süreleri).
- Üçüncü taraf forensik firma kullanılıyorsa NDA + KVKK veri işleyen sözleşmesi imzalanır.

## 10. Veri İşleyen Bildirim Yükümlülüğü (Şirketimiz Veri Sorumlusu)

Veri işleyenler (bulut sağlayıcı, dış kaynak, IK SaaS, kargo, çağrı merkezi):
- **24 saat içinde** sözleşme gereği şirketimize bildirim yapar.
- Bildirim KEP veya sözleşmede tanımlı kanaldan gelir.
- Eksik bildirim sözleşmesel cezayı ve tek taraflı fesih hakkını doğurur.
- Veri işleyenin geç bildirimi şirketimizin Kurul karşısındaki 72 saat sayacına eklenmez — sayaç **bizim öğrenme anımız**dan başlar; ancak Kurul, geç bildirimden veri sorumlusunu da sorumlu tutabilir (sözleşmesel kontrolün yetersizliği gerekçesiyle).

## 11. Kurul ile Yazışma Standartları

- Bildirim KEP üzerinden **kvkk@hs01.kep.tr** adresine yapılır.
- Eksik bilgi sonradan tamamlanabilir; ancak ilk bildirim **mümkün olan en doluluk seviyesi** ile yapılır.
- Kurul ek bilgi talep ederse cevap süresi tebliğ edilen tarihten itibaren **15 gün** (Kurul yazısında belirtilir).
- Tüm yazışma arşivlenir ve **Kurul Yazışma Defteri**ne işlenir.

## 12. Adli Bildirim ve Diğer Düzenleyiciler

KVKK bildirimi yanında değerlendirilmesi gereken diğer yükümlülükler:
- **TCK m.136-138:** Verileri hukuka aykırı ele geçirme/verme — savcılık bildirimi (özellikle içeriden tehdit).
- **5651 sayılı Kanun:** Erişim/yer sağlayıcı kayıt yükümlülüğü.
- **BDDK / SPK / EPDK:** Sektörel ihlal bildirim rejimleri (banka, sermaye piyasası, enerji).
- **GDPR (yurt dışı vatandaş etkilendiyse):** AB temsilcisi varsa ilgili DPA'ya 72 saat bildirim.
- **EMRA / BTK:** Telekom sektörü ek bildirim yükümlülükleri.

## 13. Eğitim ve Farkındalık

- Tüm çalışan: yıllık 1 saat olay raporlama eğitimi.
- IT/SOC: çeyreklik 4 saat teknik müdahale tatbikatı.
- CSIRT çekirdek ekip: yıllık 16 saat tabletop + 8 saat fiziksel tatbikat.
- Yönetim Kurulu: yıllık 1 saat kriz yönetimi briefing.

## 14. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi + YK |

## 15. Ekler

- Ek-1: CSIRT İletişim Listesi (kontrollü erişim).
- Ek-2: Olay Sınıflandırma Karar Ağacı (tek sayfa A3).
- Ek-3: Forensik Çantası İçerik Listesi.
- Ek-4: Sigortacı Bildirim Şablonu.
- Ek-5: Kurul KEP Yazışma Şablonu.
