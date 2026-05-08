---
title:
  en: "Incident Response Procedure"
  tr: "Olay Müdahale Prosedürü"
section: "08-breach-management"
document_id: "BR-IR-001"
owner: "CISO / CSIRT Lead"
classification: "Internal — Restricted"
version: "1.0"
last_review: "2026-05-08"
next_review: "2027-05-08"
language: ["en", "tr"]
references:
  - "GDPR Art. 32 — Security of processing"
  - "GDPR Art. 33 — Notification of a personal data breach to the supervisory authority"
  - "GDPR Art. 4(12) — Definition of personal data breach"
  - "EDPB Guidelines 9/2022 on personal data breach notification under GDPR"
  - "NIST SP 800-61 Rev. 2 — Computer Security Incident Handling Guide (Sections 3.2, 3.3)"
  - "ISO/IEC 27035-1:2023 — Principles and process"
  - "ISO/IEC 27035-2:2023 — Guidelines to plan and prepare for incident response"
  - "ENISA — Reference Incident Classification Taxonomy"
---

## English

### 1. Lifecycle model

This procedure adopts the four-phase NIST SP 800-61 lifecycle, harmonised with ISO/IEC 27035 stages:

1. **Preparation** (ISO 27035 stage: Plan and Prepare)
2. **Detection and Analysis** (ISO 27035 stages: Detection and Reporting; Assessment and Decision)
3. **Containment, Eradication, and Recovery** (ISO 27035 stage: Responses)
4. **Post-Incident Activity** (ISO 27035 stage: Lessons Learnt)

### 2. CSIRT structure

| Role | Title | Primary duty | On-call |
|------|-------|--------------|---------|
| CSIRT Lead | CISO | Single point of decision authority during the incident | 24/7 primary |
| Deputy CSIRT Lead | Head of Security Operations | Operational command, runbook execution | 24/7 primary |
| Forensic Lead | Senior Security Engineer | Evidence preservation, chain-of-custody | 24/7 secondary |
| DPO | Data Protection Officer | Article 33/34 assessment, SA liaison | 24/7 primary |
| Legal Counsel | General Counsel or delegate | Privilege, regulatory filings, contracts | Business hours, with escalation page |
| Communications Lead | Head of Comms | External and internal messaging | Business hours, with escalation page |
| Engineering on-call | Service-specific SRE | System recovery | 24/7 per service |
| HR Liaison | HR Director | Insider, employee impact, disciplinary | Business hours, with escalation page |
| Executive Sponsor | CEO or COO | Resource authorisation, public statements | On call |

The CSIRT operates under a written charter approved annually by the executive committee. Every member has a documented backup; no single point of failure is permitted.

### 3. Detection and intake channels

The CSIRT accepts intake from any of the following:

- SIEM alert (Splunk / Elastic / Microsoft Sentinel) with severity ≥ medium.
- EDR (CrowdStrike, SentinelOne, Defender XDR) high-confidence detection.
- DLP system block or alert.
- Cloud security posture management (CSPM) finding.
- WAF blocked attack pattern, bot detection, abuse mitigation log.
- Internal report via the incident hotline, the `security@` mailbox, or the ticket system "Security Incident" form.
- External report from a customer, partner, processor, or researcher (vulnerability disclosure programme).
- Law enforcement notification.
- Supervisory authority enquiry.
- Media or social media signal.

Every intake is recorded in the incident management system with timestamp, source, and free-text description. The CSIRT lead or deputy classifies the intake within 30 minutes of receipt.

### 4. Initial classification

The intake is classified using a two-axis matrix:

**Axis A — Severity (impact on confidentiality, integrity, availability):**

| Level | Definition |
|-------|-----------|
| SEV-1 | Major disruption or confirmed exposure of regulated personal data, large scope, public visibility likely |
| SEV-2 | Significant disruption or suspected exposure of regulated personal data, contained scope |
| SEV-3 | Minor incident, no confirmed personal data impact, isolated system |
| SEV-4 | Event, low confidence, may be a false positive |

**Axis B — Personal data involvement:**

| Code | Definition |
|------|-----------|
| PD-Y | Personal data certainly involved |
| PD-S | Personal data suspected, under investigation |
| PD-N | No personal data involvement |

Combinations PD-Y or PD-S together with SEV-1 or SEV-2 trigger DPO mobilisation and start the GDPR Article 33 awareness clock at the moment classification is recorded.

### 5. Hourly decision matrix

The first 24 hours are time-boxed. The deputy CSIRT lead drives the runbook on the clock below. All times are wall clock from the moment the incident is opened.

| Hour | Required action | Owner | Output |
|------|----------------|-------|--------|
| H+0 | Intake recorded, classification assigned, war room opened | CSIRT lead | Incident ticket, war room link |
| H+0:30 | Bridge call active, runbook selected, scribe assigned | Deputy lead | Bridge log start |
| H+1 | DPO formally notified if PD-Y or PD-S | CSIRT lead | DPO acknowledgement |
| H+2 | Containment plan drafted, executive sponsor notified | Deputy lead, CISO | Containment plan v0 |
| H+4 | Initial scope estimate (records, categories, users) | Forensic lead | Scope memo |
| H+6 | Severity decision under ENISA scoring framework | DPO + CISO | Severity score recorded |
| H+8 | Article 33 trigger decision: notify, monitor, do not notify | DPO | Decision memo |
| H+12 | If notify: draft notification under preparation; legal review opens | DPO + Legal | Draft v0 |
| H+18 | If high risk to data subjects: Article 34 communication plan started | DPO + Comms | Comms plan v0 |
| H+24 | Status update to executive committee, customers if material | Exec sponsor | Status report 1 |
| H+48 | Continued investigation, evidence preservation, draft refined | Forensic + DPO | Status report 2 |
| H+72 | Article 33 notification submitted (or phased notification with explanation) | DPO | SA submission record |

### 6. Runbooks

The following runbooks are mandatory and are stored as separate operational playbooks under the security team's repository, but their decision logic is captured here.

#### 6.1 Ransomware

1. Isolate affected hosts at network layer (EDR network containment, switch port disable).
2. Preserve memory and disk images of at least three representative hosts before any reimaging.
3. Identify the strain (ransom note hash, file extension, behavioural signature).
4. Determine if data was exfiltrated before encryption (egress logs, dark-web monitor, ransom note language). Exfiltration converts an availability breach into a confidentiality breach.
5. Engage law enforcement liaison; engage cyber insurer; do not pay before legal and law enforcement consultation.
6. Restore from immutable backup; validate integrity; rotate all credentials with possible exposure.
7. Personal data assessment: which datasets sat on encrypted hosts, what categories, how many subjects.
8. DPO closes Article 33 trigger decision within 72 hours from awareness.

#### 6.2 Insider — malicious or negligent

1. Suspend the user account and revoke session tokens at H+0 of confirmed suspicion.
2. Preserve mailbox, endpoint, badge, and access logs under HR Liaison oversight.
3. Engage Legal early — employment law and privilege concerns interact.
4. Search for data exfiltration via DLP, cloud sharing logs, USB write events, personal cloud connections.
5. If confirmed exfiltration of personal data: confidentiality breach, follow Section 5 hourly matrix.
6. HR-led disciplinary process runs in parallel and does not block notification timeline.

#### 6.3 Lost or stolen device

1. Confirm device identity and last known state from MDM (Intune, Jamf, Workspace ONE).
2. Issue a remote wipe command; record outcome (acknowledged, pending, failed).
3. Determine encryption status at the moment of loss; verify with attestation log not user assertion.
4. Determine what personal data was on the device — local mailbox cache, downloaded reports, offline documents.
5. If full-disk encryption was active and key was not compromised: document this as a likely Article 34 exemption (encryption rendering data unintelligible). Notify SA per Article 33 if risk is more than low.
6. If encryption status is unknown or compromised: proceed as confidentiality breach.

#### 6.4 Business Email Compromise (BEC)

1. Force password reset and revoke all sessions and refresh tokens for the compromised account.
2. Pull mailbox audit log: forwarding rules, inbox rules, mail flow rules.
3. Review sent items in the period of compromise; classify any personal data sent externally.
4. Identify any wire-transfer fraud or invoice manipulation.
5. Notify counterparties whose data may have been disclosed (clients, vendors); coordinate with Legal.
6. Article 33 assessment within 72 hours.

#### 6.5 Web application data leak

1. Block the attack vector at WAF or application layer.
2. Pull application logs, database audit logs, and access logs for the entire window of vulnerability.
3. Estimate data exposure using log evidence — do not over-estimate or under-estimate; document method.
4. If exposure is confirmed and contains personal data: confidentiality breach.
5. Review for any data integrity damage (modified records).
6. Patch, validate, redeploy; rotate credentials and API keys that may have been exposed.

#### 6.6 Third-party processor breach

1. Demand the processor's written breach report under Article 28(3)(f).
2. Confirm the awareness moment of the controller — typically at receipt of the processor's notification, but may be earlier if the controller had earlier independent signal.
3. Do not relay the processor's notification verbatim; the controller is responsible for the Article 33 content.
4. Coordinate any joint communications.
5. Open a CAPA against the processor and the contract.

#### 6.7 Physical breach

1. Secure the premises; preserve CCTV; engage facilities security.
2. Identify what personal data was physically accessible — paper files, unattended terminals, server room access.
3. Inventory of removable assets; cross-check against pre-incident inventory.
4. Police report where applicable.
5. Article 33 assessment within 72 hours.

### 7. Containment, eradication, recovery

Containment must be fast but proportionate. Premature eradication destroys forensic value.

- Short-term containment: stop the bleed (block IP, disable account, isolate host).
- Forensic preservation: capture before destroying.
- Long-term containment: rebuild parallel infrastructure if needed; do not let attackers see eradication actions until ready.
- Eradication: remove malware, close vulnerability, rotate compromised secrets.
- Recovery: restore service; monitor at heightened alert; gradually return to normal.

### 8. Communications during the incident

- Internal: status reports at H+8, H+24, then daily until closed.
- Executive: real-time bridge presence by exec sponsor for SEV-1.
- External: nothing leaves the company without DPO and Legal sign-off. Communications Lead drafts; Legal approves; CSIRT lead authorises release.
- Media: only the designated spokesperson speaks to media. All employees referred to that spokesperson.

### 9. Evidence and chain of custody

All forensic evidence is logged with:

- Source system, timestamp, collector identity.
- Hash (SHA-256) at collection.
- Storage location, with access list.
- Transfer log for any movement.

Evidence is retained for the longer of: 7 years; the limitation period of any underlying claim; or as instructed by Legal under litigation hold.

### 10. Closure

An incident is closed when:

1. Containment, eradication, and recovery are complete and validated.
2. Article 33 obligations have been discharged or affirmatively documented as not triggered.
3. Article 34 obligations have been discharged or affirmatively documented as not triggered.
4. RCA is complete (see `root-cause-analysis.md`).
5. CAPA actions are entered with owners and due dates.
6. Lessons-learned review has been held with all stakeholders.

### 11. Metrics

The CSIRT publishes monthly metrics including MTTD (mean time to detect), MTTI (mean time to investigate), MTTC (mean time to contain), MTTN (mean time to notify), and MTTR (mean time to recover). See `tabletop-exercises.md` for definitions.

---

## Türkçe

### 1. Yaşam döngüsü modeli

Bu prosedür, NIST SP 800-61 dört aşamalı yaşam döngüsünü ISO/IEC 27035 aşamalarıyla uyumlu olarak benimser:

1. **Hazırlık** (ISO 27035: Planlama ve Hazırlık)
2. **Tespit ve Analiz** (ISO 27035: Tespit ve Raporlama; Değerlendirme ve Karar)
3. **Kontrol Altına Alma, Yok Etme ve Kurtarma** (ISO 27035: Yanıtlar)
4. **Olay Sonrası Faaliyet** (ISO 27035: Çıkarılan Dersler)

### 2. CSIRT yapısı

| Rol | Unvan | Birincil görev | Nöbet |
|------|-------|---------------|-------|
| CSIRT Lideri | CISO | Olay sırasında tek karar mercii | 7/24 birincil |
| CSIRT Lider Yardımcısı | Güvenlik Operasyonları Müdürü | Operasyonel komuta, runbook yürütme | 7/24 birincil |
| Adli Bilişim Lideri | Kıdemli Güvenlik Mühendisi | Delil koruma, gözetim zinciri | 7/24 ikincil |
| VKK Sorumlusu | Veri Koruma Sorumlusu | Madde 33/34 değerlendirmesi, DM ile irtibat | 7/24 birincil |
| Hukuk Müşaviri | Genel Hukuk Müşaviri | Avukat-müvekkil ayrıcalığı, düzenleyici dosyalama | Mesai saatleri, çağrı yükseltme |
| İletişim Lideri | İletişim Müdürü | Dış ve iç mesajlaşma | Mesai saatleri, çağrı yükseltme |
| Mühendislik Nöbetçisi | Hizmete özgü SRE | Sistem kurtarma | Hizmete göre 7/24 |
| İK Bağlantısı | İK Direktörü | İçeriden tehdit, çalışan etkisi | Mesai saatleri, çağrı yükseltme |
| Yönetici Sponsor | CEO veya COO | Kaynak yetkilendirme, kamu açıklamaları | Çağrı |

CSIRT, her yıl yönetim kurulu tarafından onaylanan yazılı bir tüzük altında çalışır. Her üyenin belgelenmiş yedeği vardır; tek arıza noktasına izin verilmez.

### 3. Tespit ve giriş kanalları

CSIRT aşağıdakilerden gelen girişleri kabul eder:

- Önem ≥ orta olan SIEM uyarısı.
- EDR yüksek güven tespiti (CrowdStrike, SentinelOne, Defender XDR).
- DLP engelleme veya uyarı.
- Bulut güvenlik durumu yönetimi (CSPM) bulgusu.
- WAF engellenen saldırı paterni, bot tespiti, kötüye kullanım azaltma günlüğü.
- Olay yardım hattı, `security@` posta kutusu veya bilet sisteminin "Güvenlik Olayı" formu üzerinden iç bildirim.
- Müşteri, ortak, veri işleyen veya araştırmacıdan dış bildirim (zafiyet açıklama programı).
- Kolluk kuvveti bildirimi.
- Denetim makamı sorgusu.
- Medya veya sosyal medya sinyali.

Her giriş, zaman damgası, kaynak ve serbest metin açıklamasıyla olay yönetim sistemine kaydedilir. CSIRT lideri veya yardımcısı, alındıktan sonra 30 dakika içinde girişi sınıflandırır.

### 4. İlk sınıflandırma

Giriş, iki eksenli bir matris kullanılarak sınıflandırılır:

**Eksen A — Önem (gizlilik, bütünlük, erişilebilirliğe etki):**

| Düzey | Tanım |
|-------|-------|
| SEV-1 | Büyük kesinti veya düzenlenmiş kişisel verinin teyitli ifşası, geniş kapsam, kamuya yansıma olasılığı |
| SEV-2 | Önemli kesinti veya düzenlenmiş kişisel veri ifşa şüphesi, kontrollü kapsam |
| SEV-3 | Küçük olay, kişisel veri etkisi teyitsiz, izole sistem |
| SEV-4 | Olay, düşük güven, hatalı pozitif olabilir |

**Eksen B — Kişisel veri kapsamı:**

| Kod | Tanım |
|-----|-------|
| PD-Y | Kişisel veri kesinlikle kapsamda |
| PD-S | Kişisel veri şüphesi, soruşturma altında |
| PD-N | Kişisel veri kapsamı yok |

PD-Y veya PD-S ile birlikte SEV-1 veya SEV-2 olan kombinasyonlar, VKK Sorumlusu seferberliğini tetikler ve sınıflandırma kaydedildiği anda GDPR Madde 33 farkındalık saatini başlatır.

### 5. Saatlik karar matrisi

İlk 24 saat zamanla sınırlandırılmıştır. Lider yardımcısı, aşağıdaki saatte runbook'u yürütür.

| Saat | Gerekli işlem | Sahip | Çıktı |
|------|--------------|-------|-------|
| S+0 | Giriş kayıtlı, sınıflandırma atandı, savaş odası açıldı | CSIRT lideri | Olay bileti, savaş odası bağlantısı |
| S+0:30 | Köprü çağrısı aktif, runbook seçildi, kâtip atandı | Lider yardımcısı | Köprü günlüğü başlangıcı |
| S+1 | PD-Y veya PD-S ise VKK Sorumlusu resmi bildirimi | CSIRT lideri | VKK onayı |
| S+2 | Kontrol altına alma planı taslağı, yönetici sponsor bildirimi | Lider yardımcısı, CISO | Plan v0 |
| S+4 | İlk kapsam tahmini (kayıtlar, kategoriler, kullanıcılar) | Adli lider | Kapsam notu |
| S+6 | ENISA puanlama altında önem kararı | VKK + CISO | Önem puanı |
| S+8 | Madde 33 tetikleme kararı: bildir, izle, bildirme | VKK | Karar notu |
| S+12 | Bildirilecekse: bildirim taslağı, hukuk incelemesi açılır | VKK + Hukuk | Taslak v0 |
| S+18 | İlgili kişiye yüksek risk varsa: Madde 34 iletişim planı başlar | VKK + İletişim | İletişim planı v0 |
| S+24 | Yönetim komitesine, gerekirse müşterilere durum güncellemesi | Sponsor | Durum raporu 1 |
| S+48 | Soruşturma sürer, delil korunur, taslak iyileştirilir | Adli + VKK | Durum raporu 2 |
| S+72 | Madde 33 bildirimi gönderildi (veya açıklamayla birlikte aşamalı) | VKK | DM gönderim kaydı |

### 6. Runbook'lar

Aşağıdaki runbook'lar zorunludur; tam operasyonel oyun kitapları güvenlik ekibi deposunda saklanır, ancak karar mantıkları burada özetlenir.

#### 6.1 Fidye yazılımı

1. Etkilenen ana bilgisayarları ağ katmanında izole edin.
2. Görüntü yeniden yüklemeden önce en az üç temsili ana bilgisayarın bellek ve disk imajlarını saklayın.
3. Türü belirleyin (fidye notu hash, dosya uzantısı, davranışsal imza).
4. Şifrelemeden önce verilerin sızdırılıp sızdırılmadığını belirleyin. Sızıntı, erişilebilirlik ihlalini gizlilik ihlaline dönüştürür.
5. Kolluk irtibatına başvurun; siber sigortacıyı dahil edin; hukuk ve kolluk istişaresi olmadan ödeme yapmayın.
6. Değiştirilemez yedekten geri yükleyin; bütünlüğü doğrulayın; ifşa olası tüm kimlik bilgilerini değiştirin.
7. Kişisel veri değerlendirmesi: hangi veri kümeleri şifrelenmiş ana bilgisayardaydı, kategoriler, kişi sayısı.
8. VKK, farkındalıktan itibaren 72 saat içinde Madde 33 tetikleme kararını kapatır.

#### 6.2 İçeriden — kötü niyetli veya ihmalkâr

1. Kullanıcı hesabını askıya alın ve oturum tokenlerini iptal edin (S+0 onaylı şüphede).
2. Posta kutusunu, uç noktayı, kart ve erişim günlüklerini İK Bağlantısı denetiminde koruyun.
3. Hukuku erken devreye sokun.
4. DLP, bulut paylaşım günlükleri, USB yazma olayları, kişisel bulut bağlantıları üzerinden veri sızıntısı arayın.
5. Onaylı sızıntı varsa: gizlilik ihlali, Bölüm 5 saatlik matrisi izleyin.
6. İK liderliğindeki disiplin süreci paralel yürür ve bildirim takvimini engellemez.

#### 6.3 Kayıp veya çalıntı cihaz

1. MDM'den (Intune, Jamf, Workspace ONE) cihaz kimliğini ve son bilinen durumu doğrulayın.
2. Uzaktan silme komutu verin; sonucu kaydedin.
3. Kayıp anındaki şifreleme durumunu belirleyin; kullanıcı beyanıyla değil tasdik günlüğüyle doğrulayın.
4. Cihazda hangi kişisel verilerin bulunduğunu belirleyin.
5. Tam disk şifrelemesi aktifse ve anahtar tehlikeye girmediyse: bunu olası bir Madde 34 muafiyeti (verileri okunamaz hâle getirme) olarak belgeleyin. Risk düşükten fazlaysa Madde 33'e göre DM'ye bildirin.
6. Şifreleme durumu bilinmiyor veya tehlikeye girdiyse: gizlilik ihlali olarak ilerleyin.

#### 6.4 İş E-postası Tehlikesi (BEC)

1. Tehlikeye giren hesap için parola sıfırlamayı zorlayın ve tüm oturumları ile yenileme tokenlerini iptal edin.
2. Posta kutusu denetim günlüğünü çekin: yönlendirme kuralları, gelen kutusu kuralları, posta akışı kuralları.
3. Tehlike döneminde gönderilen öğeleri inceleyin; harici gönderilen kişisel verileri sınıflandırın.
4. Havale dolandırıcılığı veya fatura manipülasyonunu belirleyin.
5. Verisi ifşa olabilecek karşı tarafları bilgilendirin; Hukukla koordine edin.
6. 72 saat içinde Madde 33 değerlendirmesi.

#### 6.5 Web uygulaması veri sızıntısı

1. Saldırı vektörünü WAF veya uygulama katmanında engelleyin.
2. Tüm zafiyet penceresi için uygulama, veritabanı denetim ve erişim günlüklerini çekin.
3. Günlük kanıtını kullanarak veri ifşasını tahmin edin — yöntemi belgeleyin.
4. Onaylı ifşa kişisel veri içeriyorsa: gizlilik ihlali.
5. Veri bütünlüğü hasarını (değiştirilmiş kayıtlar) inceleyin.
6. Yamalayın, doğrulayın, yeniden dağıtın; ifşa olabilecek kimlik bilgileri ve API anahtarlarını döndürün.

#### 6.6 Üçüncü taraf veri işleyen ihlali

1. Veri işleyenin Madde 28(3)(f) altındaki yazılı ihlal raporunu talep edin.
2. Veri sorumlusunun farkındalık anını teyit edin — tipik olarak veri işleyenin bildirimini aldığında, ancak veri sorumlusunun daha erken bağımsız bir sinyali varsa daha erken olabilir.
3. Veri işleyenin bildirimini olduğu gibi iletmeyin; Madde 33 içeriğinden veri sorumlusu sorumludur.
4. Ortak iletişimleri koordine edin.
5. Veri işleyene ve sözleşmeye karşı bir CAPA açın.

#### 6.7 Fiziksel ihlal

1. Tesisleri güvenli hale getirin; CCTV'yi koruyun; tesis güvenliğini devreye sokun.
2. Hangi kişisel verilerin fiziksel olarak erişilebilir olduğunu belirleyin.
3. Çıkarılabilir varlıkların envanteri; olay öncesi envanterle çapraz kontrol.
4. Geçerli olduğunda polis raporu.
5. 72 saat içinde Madde 33 değerlendirmesi.

### 7. Kontrol altına alma, yok etme, kurtarma

Kontrol altına alma hızlı ama orantılı olmalı. Erken yok etme adli değeri tahrip eder.

- Kısa vadeli kontrol: kanamayı durdurun (IP engelle, hesap devre dışı bırak, ana bilgisayarı izole et).
- Adli koruma: yok etmeden önce yakalayın.
- Uzun vadeli kontrol: gerekirse paralel altyapı yeniden inşa edin; saldırganın yok etme eylemlerini hazır olmadan görmesine izin vermeyin.
- Yok etme: kötü amaçlı yazılımı kaldırın, zafiyeti kapatın, ifşa olan sırları döndürün.
- Kurtarma: hizmeti geri yükleyin; yüksek alarmda izleyin; yavaş yavaş normale dönün.

### 8. Olay sırasında iletişim

- İç: S+8'de, S+24'te, sonra kapanana kadar günlük durum raporları.
- Yönetici: SEV-1 için sponsor tarafından gerçek zamanlı köprü varlığı.
- Dış: VKK ve Hukuk onayı olmadan hiçbir şey şirketten çıkmaz. İletişim Lideri taslağı hazırlar; Hukuk onaylar; CSIRT lideri yayını yetkilendirir.
- Medya: Yalnızca atanmış sözcü medyaya konuşur.

### 9. Delil ve gözetim zinciri

Tüm adli deliller şu bilgilerle kaydedilir:

- Kaynak sistem, zaman damgası, toplayan kimliği.
- Toplama anında hash (SHA-256).
- Saklama yeri ve erişim listesi.
- Herhangi bir taşıma için aktarım günlüğü.

Deliller aşağıdakilerin daha uzun olanı kadar saklanır: 7 yıl; herhangi bir esas talebin zamanaşımı süresi; veya Hukuk talimatıyla dava tutma süresi.

### 10. Kapatma

Bir olay aşağıdaki durumlarda kapatılır:

1. Kontrol altına alma, yok etme ve kurtarma tamamlandı ve doğrulandı.
2. Madde 33 yükümlülükleri yerine getirildi veya tetiklenmediği belgelendi.
3. Madde 34 yükümlülükleri yerine getirildi veya tetiklenmediği belgelendi.
4. Kök neden analizi tamamlandı (bkz. `root-cause-analysis.md`).
5. CAPA eylemleri sahip ve son tarihlerle girildi.
6. Tüm paydaşlarla çıkarılan dersler incelemesi yapıldı.

### 11. Metrikler

CSIRT, MTTD, MTTI, MTTC, MTTN ve MTTR dahil olmak üzere aylık metrikler yayınlar. Tanımlar için `tabletop-exercises.md`'ye bakın.
