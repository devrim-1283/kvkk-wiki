---
title:
  en: "CCTV and Video Surveillance"
  tr: "CCTV ve Video Gözetim"
section: "10-special-topics"
document_id: "ST-CCTV-001"
owner: "DPO Office / Facilities Security"
classification: "Internal"
version: "1.0"
last_review: "2026-05-08"
next_review: "2027-05-08"
language: ["en", "tr"]
references:
  - "GDPR Art. 6(1)(f) — Legitimate interests"
  - "GDPR Art. 9 — Special categories of personal data (where biometric or health)"
  - "GDPR Art. 13 — Information to be provided"
  - "GDPR Art. 35 — DPIA"
  - "EDPB Guidelines 3/2019 on processing of personal data through video devices"
  - "ECtHR — Bărbulescu v. Romania (5 September 2017)"
  - "ECtHR — López Ribalda v. Spain (Grand Chamber, 17 October 2019)"
  - "CJEU — Ryneš (C-212/13) on the household exception"
  - "CNIL — Vidéosurveillance et vidéoprotection sectoral guides"
  - "ICO — Video surveillance code of practice"
---

## English

### 1. Scope

This document covers all video surveillance operated by the controller — premises CCTV, body-worn cameras, drones, vehicle dashcams, video-enabled access control, and remote workplace observation tools. It excludes purely personal household use (Ryneš, C-212/13).

The legal regime depends on the deployment context. EDPB Guidelines 3/2019 govern most aspects. Workplace deployments additionally implicate Article 88 GDPR and ECHR Article 8 jurisprudence (Bărbulescu, López Ribalda). Public-space deployments interact with national rules on public surveillance.

### 2. Lawful basis

Most CCTV is processed under Article 6(1)(f) — legitimate interests of the controller in protecting persons, property, and operations. The legitimate-interest assessment (LIA) must be documented:

| LIA component | Content |
|---------------|---------|
| Identified interest | Specific, e.g. "prevention and investigation of theft from retail stockroom" |
| Necessity | Why CCTV is necessary; why less-intrusive measures (lighting, locks, audit trails) are insufficient |
| Balancing | Weight of the controller's interest vs. data subjects' reasonable expectations and impact on them; vulnerable groups; intensity of monitoring |
| Safeguards | Signage, retention, access control, masking of private areas, audit log |

EDPB 3/2019 §17–§32 sets out how to perform the LIA. A surveillance scheme that surveys public sidewalks for general "security" is unlikely to pass.

For workplace surveillance, the case for legitimate interest is harder, and Article 88 national specifications often impose additional requirements (works council consultation, prior labour authority approval).

### 3. The household exception (Ryneš)

CJEU Ryneš held that surveillance covering even a small portion of public space falls outside the household exception. Privately-installed cameras pointing at the street, neighbour driveways, or shared apartment corridors are subject to GDPR. The controller is the householder, and they incur the same obligations as a corporate controller.

### 4. Two-tier signage

Article 13 requires information to be given. EDPB 3/2019 §114 endorses a two-tier approach:

**Tier 1 — at the camera point**:
- Pictogram of a camera (universally recognisable).
- Identity of the controller (short).
- Purpose, in 3-5 words ("Theft prevention").
- Reference to the right of access and to where Tier 2 information is available (URL, QR code, or "see reception").
- Contact for DPO or privacy office (short).

**Tier 2 — at a published location**:
- Full Article 13 information.
- Specific cameras and zones covered.
- Retention period and deletion procedure.
- Recipients (security service provider, police on lawful request).
- Rights and how to exercise them.
- Information on complaint to SA.

Tier 1 must be visible before the data subject enters the surveilled area. Indoor cameras in employee areas require Tier 1 signage even if employees have already received Tier 2 information at hire.

### 5. Prohibited zones

Surveillance must not extend to:

- Bathrooms, changing rooms, lactation rooms, prayer rooms, medical rooms.
- Smoking areas (often privacy-charged in cultural context).
- Inside individual offices or private spaces unless a specific compelling reason exists and a DPIA has been completed.
- Trade-union meeting spaces.

Where a camera's field of view inadvertently includes a prohibited zone, masking (privacy zones, blurring) must be applied at the camera level and verified.

### 6. Sound recording

Sound recording is not permitted by default and is not justified under the same legitimate interest as video. Sound recording is far more intrusive: it captures conversations, voice as biometric, semantic content. EDPB 3/2019 explicitly cautions against routine sound capture.

If sound recording is genuinely required (e.g. high-security cash handling), it requires:
- a separate, specific legitimate interest assessment;
- a DPIA;
- separate signage explicitly mentioning sound recording;
- retention shorter than video where possible;
- additional access controls.

In many Member States, recording private conversations without consent is a criminal offence regardless of GDPR. Consult Legal.

### 7. Retention

Standard retention is short. EDPB 3/2019 §123 indicates that 24 to 72 hours is often appropriate; 30 days is typical for premises CCTV. Common practice 15–30 days; longer requires specific justification (insurance, ongoing investigation, archived for litigation).

When an incident is captured and is being investigated, the relevant footage may be moved to a secured evidence vault on a litigation hold; routine deletion of the operational stream continues.

| Use case | Typical retention |
|---------|-------------------|
| General premises CCTV | 15–30 days |
| Cash handling area | 30–60 days |
| Public-facing entrance | 7–14 days |
| Body-worn cameras (security guards) | 30 days |
| Vehicle dashcams (logistics) | 7 days plus event-triggered preservation |
| Access-control video | linked to access-event retention, typically 30–90 days |
| Drone footage | event-based; not routine surveillance |

### 8. Facial recognition is special category

Article 9(1) treats biometric data used for the purpose of uniquely identifying a natural person as a special category. Facial recognition (1:N matching across a database) crosses into Article 9; verifying a known individual by face (1:1 against an enrolled template) also typically does. EDPB 3/2019 §73 and EDPB Guidelines 5/2022 on facial recognition technology in law enforcement underscore the high bar.

Facial recognition therefore requires:
- An Article 9(2) basis — typically (a) explicit consent (rare in workplace), or (g) substantial public interest with EU/MS law foundation.
- A DPIA.
- The least-intrusive alternative assessment (would access cards or PIN suffice?).
- Strong technical safeguards.
- Member State and SA consultation in many cases.

For employees in workplaces, EDPB and Member State SAs (CNIL, AEPD) have generally found facial recognition for time-and-attendance disproportionate.

### 9. Employee monitoring proportionality

ECtHR Bărbulescu (2017) and López Ribalda (Grand Chamber 2019) frame the European standard. Bărbulescu held that monitoring of an employee's instant-messaging account violated Article 8 ECHR where the employer had not given clear prior notice and where less-intrusive options existed. López Ribalda held that covert CCTV to investigate suspected theft was permissible only with serious suspicion, narrow scope, short duration, and the absence of practicable alternatives — and even then, the lack of prior notice was a heightened factor.

Operational rules:
- Prior notice in writing, before deployment, with specifics.
- Proportionate scope: cover what needs covering, not everything.
- Time-limited where it is investigation-driven.
- No covert surveillance unless extreme circumstances and DPO + Legal sign-off.
- Works council / employee representative consultation as required by Member State law.
- DPIA always.

### 10. DPIA triggers

A DPIA is mandatory under Article 35 and EDPB 4/2017 nine-criteria framework when:
- Surveillance is systematic monitoring of a publicly accessible area on a large scale.
- Special-category data is processed (facial recognition, behaviour analytics).
- Vulnerable persons are observed (children's areas, hospital corridors).
- New technology is used (AI-based behavioural analysis, drone surveillance).
- Surveillance is workplace-wide.

The DPIA documents the assessment, mitigations, and residual risk. SA prior consultation under Article 36 may be required where residual risk is high.

### 11. AI-based video analytics

Behavioural analytics (loitering detection, crowd density, age and gender estimation, emotion analysis) are within the AI Act's scope (some are prohibited). Emotion recognition in workplaces is prohibited under EU AI Act Article 5(1)(f), with limited safety/medical exceptions. Real-time remote biometric identification in publicly accessible spaces by law enforcement is prohibited subject to narrow exceptions (Article 5(1)(h)).

Even where not AI-Act-prohibited, video analytics typically requires:
- A second-stage LIA or Article 9(2) basis;
- DPIA;
- Transparency with specific information about the analytic;
- Output review by a human, not automated decisions affecting individuals (Article 22 implications).

### 12. Access control and audit

Live monitoring access is restricted to a small named operator group. Recorded review is restricted to specific roles with case-based justification. Each access is logged. Disclosure to law enforcement is on lawful request only, in writing, recorded, and the data subject is informed unless this would prejudice an investigation.

### 13. Storage and security

- Encrypted at rest;
- TLS in transit between camera and recorder, and between recorder and viewing terminal;
- Network segmentation (CCTV VLAN, no internet egress beyond strictly necessary);
- Strong authentication for operators;
- Regular firmware updates;
- Tamper-evident logging.

Cloud-based video storage is increasingly common; cloud providers are processors and the Article 28 contract applies. Verify residency and access controls; record retention does not migrate from "operational" to "archived" simply because it sits in a cloud bucket — retention rules apply equally.

### 14. Vehicle dashcams (commercial fleet)

Dashcams on commercial vehicles fall under Article 6(1)(f) for legitimate interest in driver safety, accident reconstruction, and theft prevention. EDPB 3/2019 §51 acknowledges legitimacy with proportionality.

- Inward-facing cameras (driver-facing) require additional justification and works council consultation; they implicate worker dignity and Bărbulescu/López Ribalda.
- Driver behaviour analytics (lane departure, harsh braking) require DPIA.
- Continuous recording vs. event-triggered: prefer event-triggered (loop-erased unless triggered).
- Audio: see Section 6.

### 15. Drones

Drone surveillance is governed by aviation law (EASA in the EU) and GDPR. The controller obtains aviation registration, follows no-fly rules, and conducts a DPIA for any drone with a camera. Privacy interfaces include:
- Altitude and angle reduce or amplify identifiability.
- Cameras pointing into private gardens or windows may be unlawful.
- Recordings retention.
- Coordination with emergency services where used in incident response.

### 16. Body-worn cameras (security personnel)

For security staff body-worn cameras:
- Activation is manual and event-triggered, not continuous.
- A short pre-event buffer (e.g. 30 seconds) is acceptable if disclosed.
- Audio capture is justified only where the threat profile makes it proportionate.
- Footage uploaded to secure storage; no local retention on the device after end-of-shift.
- Operators are trained; misuse is a disciplinary matter.

### 17. Subject access to CCTV footage

Data subjects have Article 15 access to CCTV footage of themselves. The controller:
- locates and reviews the relevant footage;
- redacts (blurs) other identifiable persons under Article 15(4);
- provides a still or short clip in a viewable format;
- charges no fee unless manifestly unfounded/excessive;
- follows the DSR procedure in section `09-data-subject-rights`.

### 18. Disposal of recordings

Routine deletion is automated at retention expiry. Forensic extraction copies are tracked, encrypted, and disposed of when the underlying need ends. Disposal of recording media (hard drives, SD cards) follows the secure-erasure rules in section `05-technical-measures`.

### 19. Documentation

Maintain:
- camera inventory with location, field of view, purpose, retention;
- LIA per camera or per zone;
- DPIA per system or significant change;
- access log;
- subject access request log for footage;
- incident review and disclosure log;
- SA correspondence.

---

## Türkçe

### 1. Kapsam

Bu belge, veri sorumlusu tarafından işletilen tüm video gözetimini kapsar — bina CCTV, vücuda takılı kameralar, drone'lar, araç gösterge panosu kameraları, video etkin erişim kontrolü ve uzak işyeri gözetim araçları. Yalnızca kişisel ev kullanımını hariç tutar (Ryneš, C-212/13).

Hukuki rejim, dağıtım bağlamına bağlıdır. EDPB Rehberi 3/2019 çoğu yönü yönetir.

### 2. Hukuki temel

Çoğu CCTV, kişileri, mülkü ve operasyonları korumadaki veri sorumlusunun meşru menfaatleri olarak Madde 6(1)(f) altında işlenir. Meşru menfaat değerlendirmesi (LIA) belgelenmelidir:

| LIA bileşeni | İçerik |
|--------------|--------|
| Belirlenen menfaat | Özel, örn. "perakende stok odasından hırsızlığın önlenmesi ve soruşturulması" |
| Gereklilik | CCTV neden gerekli; daha az müdahaleci önlemler neden yetersiz |
| Dengeleme | Veri sorumlusunun menfaati ile ilgili kişilerin makul beklentileri ve etkisi |
| Güvenceler | Tabela, saklama, erişim kontrolü, özel alanların maskelenmesi, denetim günlüğü |

İşyeri gözetimi için meşru menfaat durumu daha zordur ve Madde 88 ulusal şartnameler genellikle ek gereksinimler getirir.

### 3. Ev kullanımı istisnası (Ryneš)

CJEU Ryneš, kamu alanının küçük bir kısmını bile kapsayan gözetimin ev kullanımı istisnasının dışına düştüğünü kararlaştırdı.

### 4. İki kademeli tabela

EDPB 3/2019 §114 iki kademeli yaklaşımı onaylar:

**Kademe 1 — kamera noktasında**:
- Kamera piktogramı.
- Veri sorumlusunun kimliği (kısa).
- 3-5 sözcükte amaç.
- Erişim hakkı ve Kademe 2 bilginin nerede mevcut olduğuna referans.
- VKK iletişim bilgisi.

**Kademe 2 — yayımlanmış bir yerde**:
- Tam Madde 13 bilgisi.
- Kapsanan özel kameralar ve bölgeler.
- Saklama süresi ve silme prosedürü.
- Alıcılar.
- Haklar.
- DM şikayet bilgisi.

### 5. Yasak bölgeler

Gözetim şunları kapsamamalıdır:

- Banyolar, soyunma odaları, emzirme odaları, ibadet odaları, tıbbi odalar.
- Sigara alanları.
- Bireysel ofislerin veya özel alanların içi.
- Sendika toplantı alanları.

### 6. Ses kaydı

Ses kaydı varsayılan olarak izinli değildir. Gerçekten gerekiyorsa şunları gerektirir:
- ayrı, özel bir meşru menfaat değerlendirmesi;
- VKD;
- ses kaydını açıkça belirten ayrı tabela;
- mümkünse videodan daha kısa saklama;
- ek erişim kontrolleri.

Birçok Üye Devlette, özel konuşmaları rıza olmadan kaydetmek GDPR'den bağımsız olarak cezai bir suçtur.

### 7. Saklama

Standart saklama kısadır. EDPB 3/2019 §123 24 ila 72 saatin sıklıkla uygun olduğunu belirtir; bina CCTV için 30 gün tipiktir.

| Kullanım durumu | Tipik saklama |
|-----------------|--------------|
| Genel bina CCTV | 15–30 gün |
| Nakit elleçleme alanı | 30–60 gün |
| Halka açık giriş | 7–14 gün |
| Vücuda takılı kameralar (güvenlik görevlileri) | 30 gün |
| Araç gösterge panosu kameraları (lojistik) | 7 gün artı olay tetikli koruma |
| Erişim kontrol videosu | erişim olay saklama ile bağlantılı, genellikle 30–90 gün |

### 8. Yüz tanıma özel kategoridir

Madde 9(1), bir gerçek kişiyi benzersiz şekilde tanımlamak amacıyla kullanılan biyometrik veriyi özel kategori olarak değerlendirir. Yüz tanıma (bir veritabanında 1:N eşleşme) Madde 9'a girer.

Yüz tanıma şunları gerektirir:
- Madde 9(2) temeli — genellikle (a) açık rıza veya (g) AB/ÜD hukuk temeline sahip önemli kamu yararı.
- VKD.
- En az müdahaleci alternatif değerlendirmesi.
- Güçlü teknik güvenceler.

İşyerlerindeki çalışanlar için, EDPB ve Üye Devlet DM'leri (CNIL, AEPD) zaman ve devam için yüz tanımayı genel olarak orantısız bulmuştur.

### 9. Çalışan izleme orantılılığı

İHAM Bărbulescu (2017) ve López Ribalda (Büyük Daire 2019), Avrupa standardını çerçeveler.

Operasyonel kurallar:
- Dağıtımdan önce yazılı bildirim.
- Orantılı kapsam.
- Soruşturma odaklı olduğunda zaman sınırlı.
- Aşırı koşullar olmadıkça gizli gözetim yok.
- Üye Devlet hukuku tarafından gerekli olduğunda işyeri konseyi / çalışan temsilcisi danışması.
- Her zaman VKD.

### 10. VKD tetikleyicileri

VKD, Madde 35 ve EDPB 4/2017 dokuz kriterli çerçeve altında zorunludur:

- Gözetim kamuya açık alanın büyük ölçekli sistematik izlenmesidir.
- Özel kategori veri işlenir.
- Savunmasız kişiler gözlenir.
- Yeni teknoloji kullanılır.
- Gözetim işyeri çapındadır.

### 11. AI tabanlı video analitiği

Davranışsal analitik (oyalanma tespiti, kalabalık yoğunluğu, yaş ve cinsiyet tahmini, duygu analizi) AI Yasası kapsamındadır. İşyerlerinde duygu tanıma AB AI Yasası Madde 5(1)(f) altında yasaktır.

### 12. Erişim kontrolü ve denetim

Canlı izleme erişimi küçük bir adlandırılmış operatör grubuyla sınırlıdır.

### 13. Saklama ve güvenlik

- Dinlenmede şifrelenmiş;
- Aktarımda TLS;
- Ağ segmentasyonu;
- Operatörler için güçlü kimlik doğrulama;
- Düzenli üretici yazılımı güncellemeleri;
- Kurcalamayı belirgin loglama.

### 14. Araç gösterge panosu kameraları (ticari filo)

Ticari araçlardaki gösterge panosu kameraları, sürücü güvenliği, kaza yeniden yapılandırması ve hırsızlık önleme konusunda meşru menfaat için Madde 6(1)(f) altına girer.

### 15. Drone'lar

Drone gözetimi havacılık hukuku (AB'de EASA) ve GDPR tarafından yönetilir.

### 16. Vücuda takılı kameralar (güvenlik personeli)

Güvenlik personeli vücuda takılı kameraları için:
- Aktivasyon manuel ve olay tetiklidir, sürekli değildir.
- Açıklanırsa kısa bir olay öncesi tampon (örn. 30 saniye) kabul edilebilir.
- Ses yakalama yalnızca tehdit profili orantılı olduğunda haklı kılınır.
- Görüntü güvenli depolamaya yüklenir.

### 17. CCTV görüntülerine ilgili kişi erişimi

İlgili kişiler kendilerinin CCTV görüntülerine Madde 15 erişimi vardır.

### 18. Kayıtların imhası

Rutin silme saklama süresi sona erdiğinde otomatiktir.

### 19. Belgeleme

Sürdürün:
- konum, görüş alanı, amaç, saklama ile kamera envanteri;
- kamera başına veya bölge başına LIA;
- sistem veya önemli değişiklik başına VKD;
- erişim günlüğü;
- görüntü için ilgili kişi talep günlüğü;
- olay incelemesi ve ifşa günlüğü;
- DM yazışmaları.
