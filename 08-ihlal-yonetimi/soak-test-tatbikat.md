---
Doküman / Document: İhlal Müdahale Tatbikatı (Tabletop / Soak Test) Programı / Personal Data Breach Response Tabletop / Soak Test Programme
Bölüm / Section: 08-ihlal-yonetimi
Sahip / Owner: Bilgi Güvenliği Müdürü (CISO) + KVKK Sorumlusu / CISO + KVKK Officer
Onaylayan / Approved by: KVKK Komitesi + Yönetim / KVKK Committee + Management
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık / Annual
İlgili Mevzuat / Legal Reference: Law No. 6698 (KVKK) Art. 12; KVKK Data Security Guide (2018) §5.4; NIST SP 800-84; ISO/IEC 27035-3:2020
---

## English

# Personal Data Breach Response Tabletop & Soak Test

## 1. Purpose

In line with the KVKK Data Security Guide and international good practice (NIST 800-84, ISO 27035-3), the goal is to verify annually that the breach response procedure works **in practice and not just on paper**. Exercises are run on three planes:

1. **Tabletop:** Read the scenario; discuss the decisions. Speed and process assessment.
2. **Functional drill:** Real tools (SIEM, EDR, KEP) are used; production systems are not touched.
3. **Red team / Purple team (live):** An ethical attacker team simulates a real attack; the blue team responds.

## 2. Annual Exercise Calendar

| Quarter | Type | Target Scenario | Participants |
|---------|------|-----------------|--------------|
| Q1 | Tabletop | Ransomware (Scenario A) | Core CSIRT + Board observer |
| Q2 | Functional | Insider data exfiltration (Scenario B) | CSIRT + HR + DLP team |
| Q3 | Tabletop | Third-party breach (Scenario C) | CSIRT + Procurement + Legal |
| Q4 | Red/Purple | Web application exploit (Scenario D) | SOC + AppSec + Red Team |
| Annual special | Tabletop | Lost device + insider combined (Scenario E) | Whole CSIRT + Management |

## 3. Exercise Governance

### 3.1. Roles

| Role | Responsibility |
|------|----------------|
| Exercise Director | Scenario flow, timing of "injects", recording |
| White Team (Adjudicator) | Evaluates decisions; scoring |
| Blue Team (Defenders) | The CSIRT in tabletop mode |
| Red Team (Attackers) | Only in red/purple exercises |
| Purple Team | Attack and defense work together |
| Observers | Board member, Legal, KVKK Committee |

### 3.2. Exercise Budget

- Tabletop: 4 hours x participants + 16 hours preparation.
- Functional: 8 hours x participants + 24 hours preparation.
- Red/Purple: 5 business days external firm + 80 internal hours.

### 3.3. Confidentiality

- The scenario is not disclosed to participants in advance (surprise element).
- Outputs are shared only with KVKK Committee + senior management.
- No external sharing (attacker intelligence).

## 4. KPIs

Measured at the end of each exercise:

| KPI | Description | Target |
|-----|-------------|--------|
| MTTD (Mean Time To Detect) | First event -> detection | < 30 minutes |
| MTTI (Mean Time To Identify) | Detection -> breach decision | < 4 hours |
| MTTC (Mean Time To Contain) | Detection -> containment | < 2 hours |
| MTTN (Mean Time To Notify) | T+0 -> Authority preliminary notification | < 24 hours |
| MTTR (Mean Time To Recover) | Detection -> normal production | < 72 hours |
| Notification text quality score | 1-10 (Legal evaluation) | >= 8 |
| Decision-chain completeness | Was every critical decision documented? | 100% |
| Communication-tree compliance | Right person informed at the right time | 95% |

## 5. SCENARIO A - Ransomware (Tabletop)

### 5.1. Brief
> "06:30 - A SOC analyst working on the SCADA server at the Bursa factory notices files have taken the `.lockbit` extension. A ransom note appears on the screen: '5 BTC within 7 days, otherwise we will leak HR and R&D data.' The helpdesk receives a ticket at 06:45."

### 5.2. Injects (sequenced by White Team)

| T+ | Inject | Expected response |
|----|--------|-------------------|
| T+0 min | Helpdesk e-mail | Escalate to SOC L2; isolation decision |
| T+30 min | Second server is also affected (lateral movement) | Activate Level 3; network segmentation |
| T+1 hour | Board asks "should we pay the ransom" | Reiterate policy - no payment, insurance |
| T+2 hours | Attacker publishes a sample of HR data | Begin data subject notification preparation |
| T+4 hours | Press agency calls | Corporate Communications steps in - not "no comment" but pre-approved text |
| T+6 hours | Fleet-wide EDR scan - 12 more servers show IOCs | Extended isolation |
| T+12 hours | Backups are also reported affected | Crisis! Was there a separate offline backup? |
| T+24 hours | Authority preliminary notification deadline | Form ready, KEP sent? |
| T+48 hours | Attacker second payment warning | Reiterate policy |
| T+72 hours | Authority final notification deadline | Form complete? |

### 5.3. Decision Points (assessed by Adjudicator)

- Was the affected system **powered off or isolated**? (Correct: isolation - to preserve memory evidence.)
- Was the insurer notified at **T+12 hours**?
- Were the **data categories** clearly stated in the data subject notification text?
- Was the fact that backups were also affected explained to the media in a **controlled** way?
- Was the ransom decision escalated to the Board **per policy**?

### 5.4. Common Mistakes

- Powering off the affected server (RAM evidence is lost).
- Choosing not to notify the insurer (if SLA is missed, coverage may be void).
- Delaying notification because "data category is unclear".
- Premature social media announcement (attacker is gratified; ransom pressure increases).

## 6. SCENARIO B - Insider Data Exfiltration (Functional Drill)

### 6.1. Brief
> "Monday 10:30 - The DLP system reports that marketing specialist 'Ahmet K.' uploaded 8,500 customer records to a Gmail address outside the company over the last 3 days. The employee will start at a competitor in 2 weeks."

### 6.2. Injects

| T+ | Inject | Expected response |
|----|--------|-------------------|
| T+0 | DLP alert | Triple coordination: SOC + HR + Legal |
| T+30 min | Employee has an active session | Silent monitoring - live evidence |
| T+1 hour | Additional external addresses identified | Full scope mapping |
| T+2 hours | Permission freeze (silently, with HR approval) | HR sign-off |
| T+4 hours | In-person meeting plan | Legal + HR + witness |
| T+6 hours | Forensic imaging of device | Chain of custody |
| T+12 hours | Prosecutorial assessment | Turkish Criminal Code Art. 136 |
| T+24 hours | Data recall - cease & desist to recipient firm | Legal |
| T+48 hours | Affected customer notification preparation | KVKK + Communications |
| T+72 hours | Authority notification | KVKK Officer |

### 6.3. Functional Drill Actions

- The **DLP console** is opened; real logs are reviewed (with test data).
- **Account freeze** is applied in HRMS (test sandbox).
- Account is disabled in **AD/Entra**.
- **KEP send** simulation (test KEP).
- **Authority portal** (test environment if available) - draft form completion.

### 6.4. Decision Points

- Was the duration of evidence collection without alerting the employee sufficient?
- Was Legal-HR synchronization established?
- Can criminal proceedings be started **simultaneously** with administrative process?
- On what evidence was cease-and-desist sent to the competitor?

## 7. SCENARIO C - Third-Party Breach (Tabletop)

### 7.1. Brief
> "Tuesday 14:00 - KEP from 'PayrollX SaaS', our payroll service provider: 'A data breach affecting 18% of our customers has been detected. Up to 612 of your employees may have payroll and IBAN information affected. Our first detection was 5 days ago; we are now reaching out.'"

### 7.2. Injects

| T+ | Inject | Expected response |
|----|--------|-------------------|
| T+0 | KEP arrives | Check contractual notification clause - 24-hour clause violated |
| T+30 min | Vendor not sharing information | Contractual sanction; temporary suspension |
| T+1 hour | Vendor backup plan | HR + Finance evaluate alternative provider |
| T+4 hours | Independent forensic request | Legal + CISO |
| T+12 hours | Insurer notification | CFO + Legal |
| T+24 hours | Authority preliminary notification | KVKK Officer |
| T+48 hours | Employee communication | HR + KVKK |
| T+72 hours | Authority final | KVKK Officer |

### 7.3. Decision Points

- Did the 5-day delay **count against our 72 hours**? (Answer: no, our T+0 is today; but we must explain it to the Authority.)
- Does the contract include **unilateral termination** rights?
- What is the contractual **penalty clause**?
- Was the transition time to a new provider (vendor lock-in?) calculated in the exercise?

### 7.4. Exercise Output

- Map of vendor contractual clauses (who is 24 hours, who 72, who lacks).
- Updated alternative-vendor list.
- Data portability drill (export-import time measurement).

## 8. SCENARIO D - Web Application Exploit (Red/Purple)

### 8.1. Brief
> "An external red team firm tests the customer portal under OWASP Top 10, finds an SQL Injection vulnerability, and exfiltrates 1.2M customer records (test environment or production canary)."

### 8.2. Attack Phases (Red)

1. Reconnaissance - Wayback, Shodan, Censys.
2. Vulnerability scanning - Burp Suite, sqlmap.
3. Initial access - SQLi.
4. Privilege escalation - DB user to system.
5. Lateral movement - to other servers.
6. Data collection - customer table.
7. Exfiltration - DNS tunneling.

### 8.3. Defense Phases (Blue)

1. WAF anomaly score increases.
2. SIEM correlation - DB query spike.
3. EDR - abnormal process.
4. DLP - DNS data egress.
5. SOC L1 alarm -> L2 verification.
6. CSIRT activation.
7. Containment + notification.

### 8.4. Purple Synergy Points

- Red performs every phase **silently**; how much does Blue catch?
- For phases not caught, generate **detection engineering** outputs.
- How did WAF rule sets actually perform under real attack?

### 8.5. Output

- Detection coverage matrix (MITRE ATT&CK).
- New SIEM rule recommendations (at least 5).
- Patch recommendations (CVSS prioritized).
- Notification flow timing.

## 9. SCENARIO E - Combined: Lost Laptop + Insider Threat

### 9.1. Brief
> "Sunday night - a regional manager reports 'my laptop was stolen from the trunk'. The next day, IT logs show abnormal file-download activity on the laptop over the past 6 months. The regional manager planned to leave the company within 1 month."

### 9.2. Multiple Vectors

| Dimension | Action |
|-----------|--------|
| Lost device | MDM remote lock; BitLocker verification |
| Insider | Discipline + Legal + criminal review |
| Data scope | Last 6 months activity analysis |
| KVKK | Notification required? Encryption may exempt |
| Crisis | Regional sales, customer reputation |

### 9.3. Purpose of This Scenario

Cross-category decision-making: is it **loss**, **insider**, or **both**? Which one does the notification text emphasize? In which direction does the criminal process go? Tests the team's performance under **information uncertainty**.

## 10. Post-Exercise Report Template

Within 7 business days of each exercise, the following report is prepared:

```markdown
# Post-Exercise Report

## 1. Exercise Information
- Exercise name:
- Date:
- Scenario:
- Duration:
- Participants:
- Exercise Director:

## 2. Scenario Summary

## 3. KPI Measurements
| KPI | Target | Achieved | Status |
|-----|--------|----------|--------|
| MTTD | < 30 min |  | [ ] Pass [ ] Fail |
| MTTI | < 4 hours |  |  |
| MTTC | < 2 hours |  |  |
| MTTN | < 24 hours |  |  |
| MTTR | < 72 hours |  |  |
| Notification quality | >= 8/10 |  |  |

## 4. What Went Right
1.
2.

## 5. Gaps / Missed Points
1.
2.

## 6. Scenario-Specific Findings

## 7. Action List (CAPA)
| # | Action | Owner | Date | Status |
|---|--------|-------|------|--------|
| 1 |  |  |  |  |

## 8. Procedure / Training Update Recommendations

## 9. Next Exercise Recommendations

## 10. Management Sign-off
- Exercise Director:
- CISO:
- KVKK Officer:
- KVKK Committee:
```

## 11. Action Tracking

Exercise actions are integrated with **`11-denetim-ve-uyum/aksiyon-takibi.md`**. Stages:

1. Action opened in JIRA/asana/written list.
2. Owner and date assigned.
3. Quarterly review by KVKK Committee.
4. Open actions enter the **next exercise scenario**.
5. Annual audit reviews exercise actions.

## 12. Exercise Maturity Model

The company's exercise maturity:

| Level | Definition |
|-------|------------|
| 1 - Ad-hoc | One annual exercise, undocumented |
| 2 - Continuous | Quarterly exercises, reporting in place |
| 3 - Measured | KPIs tracked; trend reporting |
| 4 - Managed | Red team included; escalation tested |
| 5 - Optimized | Automation; threat-informed defense; continuous improvement |

Company target level: **4 - Managed** (end of 2026).

## 13. Exercise Ethics

- Employees may not run **actually harmful** tools during the exercise.
- Production systems must not be impacted (sandbox/test).
- Social engineering exercises must not be used to **publicly shame** employees - training-oriented.
- Exercise outcomes are not used for individual punishment; process improvement.
- Attack simulations operate **within legal scope** (signed authorization).

## 14. Version History

| Version | Date | Change | Approval |
|---------|------|--------|----------|
| 1.0 | 2026-05-08 | First publication | KVKK Committee |

---

## Türkçe

# İhlal Müdahale Tatbikatı (Tabletop & Soak Test)

## 1. Amaç

KVKK Veri Güvenliği Rehberi'nin gereği ve uluslararası iyi uygulamaların (NIST 800-84, ISO 27035-3) ışığında, ihlal müdahale prosedürünün **kâğıt üzerinde değil pratikte** çalıştığını yıllık olarak doğrulamak. Tatbikatlar üç düzlemde yürütülür:

1. **Tabletop egzersizi (masa başı):** Senaryoyu okur, kararlar tartışılır. Hız ve süreç değerlendirmesi.
2. **Functional drill (fonksiyonel tatbikat):** Gerçek araçlar (SIEM, EDR, KEP) kullanılır; sistem dokunulmaz.
3. **Red team / Purple team (canlı):** Etik saldırgan ekibi gerçek saldırı simüle eder, mavi takım yanıt verir.

## 2. Yıllık Tatbikat Takvimi

| Çeyrek | Tip | Hedef Senaryo | Katılımcılar |
|--------|-----|---------------|--------------|
| Q1 | Tabletop | Ransomware (Senaryo A) | CSIRT çekirdek + YK gözlemci |
| Q2 | Functional | İçeriden veri sızıntısı (Senaryo B) | CSIRT + İK + DLP ekibi |
| Q3 | Tabletop | Üçüncü taraf ihlali (Senaryo C) | CSIRT + Tedarik + Hukuk |
| Q4 | Red/Purple | Web uygulaması istismarı (Senaryo D) | SOC + AppSec + Red Team |
| Yıllık özel | Tabletop | Kayıp cihaz + içeriden kombine (Senaryo E) | Tüm CSIRT + Yönetim |

## 3. Tatbikat Yönetişimi

### 3.1. Roller

| Rol | Sorumluluk |
|-----|-----------|
| Tatbikat Lideri (Exercise Director) | Senaryo akışı, "injects" zamanlaması, kayıt |
| Beyaz Takım (Adjudicator) | Kararları değerlendirir, puanlama |
| Mavi Takım (Defenders) | CSIRT'in tatbikattaki hali |
| Kırmızı Takım (Attackers) | Sadece red/purple tatbikatta |
| Mor Takım (Purple) | Saldırı + savunma birlikte çalışır |
| Gözlemciler | YK üyesi, Hukuk, KVKK Komitesi |

### 3.2. Tatbikat Bütçesi

- Tabletop: 4 saat × katılımcı + 16 saat hazırlık.
- Functional: 8 saat × katılımcı + 24 saat hazırlık.
- Red/Purple: 5 iş günü dış firma + dahili 80 saat.

### 3.3. Gizlilik

- Senaryo katılımcılara önceden açıklanmaz (sürpriz öğesi).
- Sonuçlar sadece KVKK Komitesi + üst yönetim ile paylaşılır.
- Dış paylaşım yapılmaz (saldırgan istihbaratı).

## 4. KPI'lar (Performans Göstergeleri)

Her tatbikat sonunda ölçülür:

| KPI | Açıklama | Hedef |
|-----|----------|-------|
| MTTD (Mean Time To Detect) | İlk olay → tespit | < 30 dakika |
| MTTI (Mean Time To Identify) | Tespit → ihlal kararı | < 4 saat |
| MTTC (Mean Time To Contain) | Tespit → sınırlandırma | < 2 saat |
| MTTN (Mean Time To Notify) | T+0 → Kurul taslak | < 24 saat |
| MTTR (Mean Time To Recover) | Tespit → üretim normal | < 72 saat |
| Bildirim metin kalite skoru | 1-10 (Hukuk değerlendirme) | ≥ 8 |
| Karar zinciri eksiksizliği | Her kritik karar belgelendi mi | %100 |
| İletişim ağacı uyumu | Doğru kişi doğru zamanda haberdar | %95 |

## 5. SENARYO A — Ransomware (Tabletop)

### 5.1. Brief
> "06:30 — Bursa fabrika SCADA sunucusuna giren bir SOC analiti, dosyaların `.lockbit` uzantısı aldığını fark eder. Ekran üzerinde fidye notu görünür: '5 BTC içinde 7 gün, ödemezseniz IK ve ARGE verilerini sızdıracağız.' Olay açma helpdesk'a 06:45'te düşer."

### 5.2. Inject'ler (Beyaz Takım sırayla atar)

| T+ | Inject | Beklenen yanıt |
|----|--------|----------------|
| T+0 dk | Helpdesk e-postası | SOC L2'ye eskalasyon, izolasyon kararı |
| T+30 dk | İkinci sunucu da etkilendi (yatay hareket) | Aktivasyon Seviye 3, network segmentasyonu |
| T+1 saat | "Fidye ödenmeli mi" YK sorusu | Politika hatırlatma — ödenmez, sigorta |
| T+2 saat | Saldırgan İK verisi örneği yayımladı | İlgili kişi bildirim hazırlığı başlasın |
| T+4 saat | Basın ajansı arıyor | Kurumsal İletişim devreye, "yorum yok" değil önceden hazır metin |
| T+6 saat | EDR tüm filo taraması — 12 sunucu daha IOC | Genişletilmiş izolasyon |
| T+12 saat | Yedeklerin de etkilendiği rapor | Kriz! Önceden offline backup var mıydı? |
| T+24 saat | Kurul'a taslak bildirim deadline | Form hazır mı, KEP gönderildi mi |
| T+48 saat | Saldırgan ikinci ödeme uyarısı | Politika tekrar |
| T+72 saat | Kurul nihai bildirim deadline | Form tamamlandı mı |

### 5.3. Karar Noktaları (Adjudicator değerlendirir)

- Etkilenen sistem **kapatıldı mı, izole mi edildi**? (Doğru: izolasyon — bellek delili korunur)
- Sigortacı **T+12 saatte** mi haberdar oldu?
- İlgili kişi bildirim metninde **hangi veri kategorileri** açıkça yazıldı?
- Yedeklerin de etkilendiği gerçeği medyaya **kontrollü mü** açıklandı?
- Fidye konusu YK'ya **politika gereği** mi taşındı?

### 5.4. Sıkça Yapılan Hatalar

- Etkilenen sunucuyu kapatma (RAM kanıtı kaybolur).
- Sigortacıyı bildirmemeyi seçme (poliçe SLA'yı kaçırırsa hak düşer).
- "Veri kategorisi belirsiz" diyerek bildirimi geciktirme.
- Sosyal medyada erken duyuru (saldırgan tatmin olur, fidye baskısı artar).

## 6. SENARYO B — İçeriden Veri Sızıntısı (Functional Drill)

### 6.1. Brief
> "Pazartesi 10:30 — DLP sistemi 'Ahmet K.' isimli pazarlama uzmanının son 3 günde 8.500 müşteri kaydını şirket dışı bir Gmail adresine yüklediğini raporlar. Çalışan 2 hafta sonra rakip firmada işe başlayacak."

### 6.2. Inject'ler

| T+ | Inject | Beklenen yanıt |
|----|--------|----------------|
| T+0 | DLP alarmı | SOC + İK + Hukuk üçlü koordinasyon |
| T+30 dk | Çalışanın aktif oturumu var | Sessiz izleme — kanıt toplama (canlı) |
| T+1 saat | Ek dış adresler tespit | Tam kapsam haritalama |
| T+2 saat | Çalışan yetkilerinin uzaktan dondurulması | İK onay ile sessizce |
| T+4 saat | Çalışan ile yüz yüze görüşme planı | Hukuk + İK + tanık |
| T+6 saat | Cihaz forensik imajı | Chain of custody |
| T+12 saat | Adli savcılık değerlendirme | TCK m.136 |
| T+24 saat | Veri geri çağırma — alıcı firmaya cease & desist | Hukuk |
| T+48 saat | Etkilenen müşteri bildirim hazırlığı | KVKK + İletişim |
| T+72 saat | Kurul bildirim | KVKK Sorumlusu |

### 6.3. Functional Drill Aksiyonları

- **DLP konsolu açılır**, gerçek log incelenir (test verisiyle).
- **HR sistemi**nde çalışan dondurma uygulanır (test sandbox).
- **AD/Entra**'da hesap disable edilir.
- **KEP gönderim** simülasyonu (test KEP).
- **Kurul portalı** (test ortamı varsa) — form taslak doldurulur.

### 6.4. Karar Noktaları

- Çalışan haberdar olmadan kanıt toplama süresi yeterli miydi?
- Hukuk + İK senkronu kuruldu mu?
- Adli süreç **aynı anda** başlatılabilir mi (idari + cezai)?
- Rakip firmaya cease & desist hangi delillerle gönderildi?

## 7. SENARYO C — Üçüncü Taraf İhlali (Tabletop)

### 7.1. Brief
> "Salı 14:00 — Bordro hizmeti aldığımız 'PayrollX SaaS' firmasından KEP gelir: 'Müşterilerimizin %18'ini etkileyen bir veri ihlali tespit edilmiştir. Şirketinize ait 612 çalışanın bordro ve IBAN bilgileri etkilenmiş olabilir. İlk tespitimiz 5 gün önceydi, şu an iletişime geçiyoruz.'"

### 7.2. Inject'ler

| T+ | Inject | Beklenen yanıt |
|----|--------|----------------|
| T+0 | KEP geldi | Sözleşme bildirim klozu kontrolü — 24 saat klozu ihlali tespit |
| T+30 dk | Alıcı firma bilgi paylaşmıyor | Sözleşmesel yaptırım, geçici askıya alma |
| T+1 saat | Tedarikçi yedek planı | İK + Finans alternatif sağlayıcı |
| T+4 saat | Bağımsız forensik talebi | Hukuk + CISO |
| T+12 saat | Sigortacı bildirim | CFO + Hukuk |
| T+24 saat | Kurul taslak bildirim | KVKK Sorumlusu |
| T+48 saat | Çalışan iletişim | İK + KVKK |
| T+72 saat | Kurul nihai | KVKK Sorumlusu |

### 7.3. Karar Noktaları

- 5 günlük gecikme **bizim 72 saatimize sayıldı mı**? (Cevap: hayır, bizim T+0'ımız bugün; ancak Kurul'a açıklamalıyız.)
- Sözleşme **tek taraflı fesih** hakkı içeriyor mu?
- Sözleşmesel **ceza-i şart** ne kadar?
- Yeni sağlayıcıya geçiş süresi (vendor lock-in?) tatbikatta hesaplandı mı?

### 7.4. Tatbikat Çıktısı

- Tedarikçi sözleşme klozları haritası (kim 24 saat, kim 72 saat, kim eksik).
- Yedek tedarikçi listesi güncellemesi.
- Veri taşınabilirliği tatbikatı (export-import zaman ölçümü).

## 8. SENARYO D — Web Uygulaması İstismarı (Red/Purple)

### 8.1. Brief
> "Dış red team firması, müşteri portali için OWASP Top 10 testi kapsamında SQL Injection açığı tespit eder ve 1.2 M müşteri kaydını exfiltrate eder (test ortamı veya prod canary)."

### 8.2. Saldırı Aşamaları (Red)

1. Reconnaissance — Wayback, Shodan, Censys.
2. Vulnerability scanning — Burp Suite, sqlmap.
3. Initial access — SQLi.
4. Privilege escalation — DB kullanıcısından sistem.
5. Lateral movement — diğer sunuculara.
6. Data collection — müşteri tablosu.
7. Exfiltration — DNS tunneling.

### 8.3. Savunma Aşamaları (Blue)

1. WAF anomaly score yükselişi.
2. SIEM korelasyon — DB query patlaması.
3. EDR — anormal süreç.
4. DLP — DNS dışa veri çıkışı.
5. SOC L1 alarm → L2 doğrulama.
6. CSIRT aktivasyon.
7. Sınırlandırma + bildirim.

### 8.4. Purple Sinerji Noktaları

- Red her aşamayı **bildirimsiz** yapar; Blue ne kadarını yakaladı?
- Yakalanmayan aşamalar için **detection engineering** çıktıları.
- WAF kural setlerinin gerçek saldırıda nasıl performans gösterdiği.

### 8.5. Çıktı

- Detection coverage matrix (MITRE ATT&CK).
- Yeni SIEM kuralı önerileri (en az 5).
- Yama önerileri (CVSS önceliği).
- Bildirim akışı süre ölçümü.

## 9. SENARYO E — Kombine: Kayıp Dizüstü + İçeriden Tehdit

### 9.1. Brief
> "Pazar gecesi — bir bölge müdürü 'dizüstüm bagajdan çalındı' diye bildirir. Ertesi gün, IT log'larında dizüstüğün 6 ay boyunca anormal dosya indirme aktivitesi yaptığı tespit edilir. Bölge müdürü 1 ay içinde işten ayrılmayı planlamış."

### 9.2. Çoklu Vektör

| Boyut | Eylem |
|-------|-------|
| Kayıp cihaz | MDM uzaktan kilit, BitLocker doğrulama |
| İçeriden | Disiplin + Hukuk + adli inceleme |
| Veri kapsamı | Son 6 aylık aktivite analizi |
| KVKK | Bildirim yapılır mı? Şifrelenmişse rezerv durum |
| Kriz | Bölge satışları, müşteri itibarı |

### 9.3. Bu Senaryonun Amacı

Kategoriler arası karar verme: kayıp **mi**, içeriden **mi**, ikisi birden **mi**? Bildirim metni hangisini öne çıkarır? Adli süreç hangi yönde ilerler? Tatbikat ekibinin **bilgi belirsizliği** altındaki performansını ölçer.

## 10. Tatbikat Sonrası Rapor Şablonu

Her tatbikat sonrası 7 iş günü içinde aşağıdaki rapor hazırlanır:

```markdown
# Tatbikat Sonrası Rapor

## 1. Tatbikat Bilgileri
- Tatbikat adı:
- Tarih:
- Senaryo:
- Süre:
- Katılımcılar:
- Tatbikat Lideri:

## 2. Senaryo Özeti

## 3. KPI Ölçümleri
| KPI | Hedef | Gerçekleşen | Durum |
|-----|-------|-------------|-------|
| MTTD | < 30 dk | | ☐ Geçti ☐ Kaldı |
| MTTI | < 4 saat | | |
| MTTC | < 2 saat | | |
| MTTN | < 24 saat | | |
| MTTR | < 72 saat | | |
| Bildirim kalitesi | ≥ 8/10 | | |

## 4. Doğru Yapılanlar
1.
2.

## 5. Eksiklikler / Kaçırılan Noktalar
1.
2.

## 6. Senaryo-Spesifik Bulgular

## 7. Aksiyon Listesi (CAPA)
| # | Aksiyon | Sahip | Tarih | Durum |
|---|---------|-------|-------|-------|
| 1 | | | | |

## 8. Prosedür / Eğitim Güncellemesi Önerileri

## 9. Sonraki Tatbikat Önerileri

## 10. Yönetim İmza
- Tatbikat Lideri:
- CISO:
- KVKK Sorumlusu:
- KVKK Komitesi:
```

## 11. Aksiyon Takibi

Tatbikat aksiyonları **`11-denetim-ve-uyum/aksiyon-takibi.md`** ile entegredir. Aşamalar:

1. Aksiyon JIRA/asana/yazılı listede açılır.
2. Sahip ve tarih atanır.
3. Çeyreklik KVKK Komitesi gözden geçirir.
4. Kapanmamış aksiyonlar **sonraki tatbikat senaryosuna** girer.
5. Yıllık denetimde tatbikat aksiyonları kontrol edilir.

## 12. Tatbikat Olgunluk Modeli

Şirketin tatbikat olgunluk seviyesi:

| Seviye | Tanım |
|--------|-------|
| 1 — Ad-hoc | Yıllık 1 tatbikat, dokümante edilmemiş |
| 2 — Sürekli | Çeyreklik tatbikat, raporlama var |
| 3 — Ölçülen | KPI'lar takip ediliyor, eğilim raporu |
| 4 — Yönetilen | Kırmızı takım dahil, eskalasyon test |
| 5 — Optimize | Otomasyon, threat-informed defense, sürekli iyileştirme |

Şirketimiz hedef seviye: **4 — Yönetilen** (2026 sonu).

## 13. Tatbikat Etiği

- Çalışan tatbikat sırasında **gerçekten zararlı** araç çalıştıramaz.
- Üretim sistemleri etkilenmemelidir (sandbox/test).
- Sosyal mühendislik tatbikatlarında çalışan **gizlice rezalet edilmez** — eğitim odaklı.
- Tatbikat sonuçları bireysel ceza için kullanılmaz; süreç iyileştirme.
- Saldırı simülasyonu **yasal kapsamda** (yetki belgesi imzalı).

## 14. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi |
