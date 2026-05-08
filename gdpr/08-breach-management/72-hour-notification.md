---
title:
  en: "72-Hour Supervisory Authority Notification"
  tr: "Denetim Makamına 72 Saat İçinde Bildirim"
section: "08-breach-management"
document_id: "BR-NOT-001"
owner: "Data Protection Officer"
classification: "Internal — Restricted"
version: "1.0"
last_review: "2026-05-08"
next_review: "2027-05-08"
language: ["en", "tr"]
references:
  - "GDPR Art. 33(1)–(5) — Notification of personal data breach to the supervisory authority"
  - "GDPR Art. 4(12) — Definition"
  - "GDPR Art. 56 — Competence of the lead supervisory authority"
  - "GDPR Art. 60 — Cooperation between the lead and concerned authorities (one-stop-shop)"
  - "GDPR Recitals 85, 87, 88"
  - "EDPB Guidelines 9/2022 on personal data breach notification under GDPR"
  - "EDPB Guidelines 01/2021 — Examples regarding personal data breach notification"
  - "WP29 Guidelines on personal data breach notification (WP250rev.01) endorsed by the EDPB"
---

## English

### 1. Legal trigger

Article 33(1) GDPR requires the controller to notify the competent supervisory authority of a personal data breach without undue delay and, where feasible, not later than 72 hours after having become aware of it. Where notification is not made within 72 hours it must be accompanied by reasons for the delay.

The 72-hour clock starts at the moment of awareness, not at the moment of the underlying event. EDPB Guidelines 9/2022 paragraph 31 confirms that the controller is "aware" when it has a reasonable degree of certainty that a security incident has occurred that has led to personal data being compromised. A short period of investigation to confirm the existence of a breach is permissible, but it must be brief and documented.

### 2. The single exemption to notification

Article 33(1) provides only one exemption: notification is not required if the breach is "unlikely to result in a risk to the rights and freedoms of natural persons". The threshold is risk, not high risk; the high-risk threshold is for Article 34 data subject communication, not for Article 33 SA notification. Any non-trivial risk pushes the case into notification territory.

The justification for not notifying must be documented in the internal register under Article 33(5). EDPB 9/2022 stresses that the assessment must be evidence-based, not aspirational.

### 3. Awareness — when does the clock start?

Awareness arises in different ways. The DPO records the awareness moment with timestamp, evidence, and the analyst who made the determination.

| Trigger pattern | Awareness moment |
|-----------------|------------------|
| SOC analyst confirms exfiltration via DLP and egress logs | At the timestamp of the analyst's confirmation |
| Forensic firm produces interim report confirming compromise | At the timestamp of report receipt by the controller |
| Processor (Article 28) reports a breach affecting controller data | At the timestamp the processor's notification is received by the controller |
| External researcher delivers proof of vulnerability and exposure | At the timestamp of credible proof; mere allegation does not yet trigger |
| Law enforcement notifies the controller | At the timestamp of receipt |
| Public dump or media report contains controller data | At the timestamp the controller becomes aware of the link to its data |

Mere suspicion is not awareness. A short, bounded investigation period to confirm whether an event amounts to a personal data breach is permitted. That investigation period must be reasonable, documented, and kept as short as possible. It must not be used to delay the start of the 72-hour clock once awareness is in fact reached.

### 4. Risk assessment — ENISA severity framework

The risk assessment uses the ENISA methodology adapted to the EDPB criteria:

1. **Data Processing Context** — type of data, sensitivity, identifiability.
2. **Ease of Identification** — direct, indirect, very difficult.
3. **Circumstances of the Breach** — type (confidentiality, integrity, availability), volume, malicious intent.

Each factor produces a numeric score; the aggregate yields a severity level (low, medium, high, very high). Low and above triggers Article 33 notification; high and above triggers Article 34 communication to data subjects (subject to exemptions in `data-subject-notification.md`).

### 5. Content of the notification — Article 33(3)

The notification must at least:

(a) describe the nature of the personal data breach including, where possible, the categories and approximate number of data subjects concerned and the categories and approximate number of personal data records concerned;

(b) communicate the name and contact details of the data protection officer or other contact point where more information can be obtained;

(c) describe the likely consequences of the personal data breach;

(d) describe the measures taken or proposed to be taken by the controller to address the personal data breach, including, where appropriate, measures to mitigate its possible adverse effects.

Section 8 below maps each item to evidentiary expectations.

### 6. Phased notification — Article 33(4)

Where, and in so far as, it is not possible to provide the information at the same time, the information may be provided in phases without undue further delay. The controller must:

1. Send the initial notification within 72 hours, even if incomplete.
2. Identify the missing items and explain why they are not yet known.
3. Provide a target date for follow-up.
4. Submit follow-up notifications as facts become known, in writing, referencing the case number assigned by the SA.

EDPB 9/2022 §39 confirms that phased notification is the rule, not the exception, for genuinely complex incidents. It is not a licence to delay basic facts that are already in the controller's possession.

### 7. Lead authority and one-stop-shop — Articles 56 and 60

For cross-border processing, the controller submits the notification to the lead supervisory authority of its main establishment. The lead SA coordinates with concerned SAs through the IMI system. The controller does not need to file separately with each concerned SA, but should be prepared for follow-up enquiries from concerned SAs through the lead.

Where the controller has no main establishment in the EU but has an Article 27 representative, the notification is filed with the SA of the Member State where the representative is located, plus all SAs of Member States where the data subjects affected are located. There is no one-stop-shop for non-EU controllers (EDPB Guidelines 3/2018 on territorial scope).

| Scenario | Lead SA | Notify additionally |
|----------|---------|---------------------|
| Cross-border processing, main establishment in Ireland | Irish DPC | None — IMI cooperation |
| Single Member State only | SA of that Member State | None |
| Non-EU controller with Article 27 representative in Spain, breach affects DE and FR subjects | None (no one-stop-shop) | AEPD (Spain), BfDI (Germany), CNIL (France) |
| Joint controllers in BE and NL | The lead per the joint controller arrangement | The other controller's SA via IMI |

### 8. Mapping Article 33(3) to evidence

| Required element | Evidence sources | Owner |
|------------------|-----------------|-------|
| Nature of the breach | Incident timeline, forensic report, log excerpts | CSIRT lead |
| Categories of data subjects | Customer database extract, employee list, segment definition | Data owner |
| Approximate number of data subjects | Database COUNT query with timestamp; estimation method documented | Data owner |
| Categories of personal data records | Schema mapping, ROPA reference | Data owner + DPO |
| Approximate number of records | Table row counts; method documented | Data owner |
| DPO contact | DPO directory entry, email, phone | DPO |
| Likely consequences | ENISA assessment, threat intelligence, similar-incident references | DPO + CISO |
| Measures taken | Containment runbook output, ticket numbers, screenshots | CSIRT lead |
| Measures proposed | CAPA register extract | CSIRT lead + DPO |

### 9. Documentation under Article 33(5)

Article 33(5) requires the controller to document any personal data breach, comprising the facts relating to the personal data breach, its effects, and the remedial action taken. This obligation is independent of whether the SA was notified. The internal breach register must be sufficient to enable the SA to verify compliance.

The internal breach register fields:

1. Internal breach ID and case reference.
2. Date and time of awareness.
3. Date and time of underlying event (if known).
4. Source of detection.
5. Description of the event and the personal data involved.
6. Categories and approximate numbers of data subjects and records.
7. Risk assessment with ENISA score.
8. Decision: notify SA / do not notify SA, with rationale.
9. Decision: notify data subjects / do not notify, with rationale.
10. Containment, eradication, recovery actions and timestamps.
11. CAPA references.
12. Outcomes of any SA enquiries or investigations.
13. Final closure date.

### 10. Submission channels

| Authority | Primary channel | Backup channel |
|-----------|----------------|----------------|
| KVKK (Türkiye, where applicable) | VERBIS / kvkk.gov.tr e-form | Registered post (KEP) |
| Irish DPC | breaches.dataprotection.ie online form | dpobreaches@dataprotection.ie |
| CNIL (France) | notifications.cnil.fr online | Registered post |
| BfDI / Länder DPAs (Germany) | Online form per Land | Registered post |
| AEPD (Spain) | Sede electrónica AEPD | Registered post |
| ICO (UK, post-Brexit, comparator) | ICO online form / 0303 123 1113 | Registered post |

### 11. Worked timeline

For a confidentiality breach detected at H+0 with high confidence:

- H+0: SOC analyst opens ticket, classification SEV-2 PD-Y.
- H+0:30: CSIRT lead confirms, war room open.
- H+1: DPO mobilised; awareness moment recorded.
- H+6: ENISA score calculated as medium (notification required).
- H+24: Investigation produces approximate numbers; draft v1 of notification.
- H+48: Legal review complete.
- H+60: DPO submits via lead SA online portal; case number received.
- H+72: Article 33(4) phased notification flag if any element still pending.
- Day 7: Follow-up submission with exfiltration confirmation.
- Day 14: Follow-up submission with final scope.

### 12. Late notification — what to do if 72 hours has passed

If the 72-hour deadline has been missed, do not delay further. Submit immediately and include the reasons for the delay, the steps taken to assess and contain, and the controls that will be improved to prevent recurrence. EDPB 9/2022 confirms that late submission with explanation is preferable to non-submission.

### 13. After the notification

- The SA may request additional information, audit, or impose corrective measures (Article 58).
- Continue updating the internal register as the case develops.
- Coordinate with Communications on any public statements.
- Trigger the RCA process (`root-cause-analysis.md`) once the immediate response is closed.

---

## Türkçe

### 1. Yasal tetikleyici

GDPR Madde 33(1), veri sorumlusunun bir kişisel veri ihlalini, gecikmeksizin ve mümkünse haberdar olduktan sonra en geç 72 saat içinde yetkili denetim makamına bildirmesini gerektirir. Bildirim 72 saat içinde yapılmazsa gecikmenin gerekçeleri eklenmelidir.

72 saatlik süre, temel olayın anında değil, farkındalık anında başlar. EDPB 9/2022 Rehberi paragraf 31, veri sorumlusunun, kişisel verilerin tehlikeye atılmasına yol açan bir güvenlik olayının gerçekleştiğine dair makul bir kesinlik derecesine sahip olduğunda "haberdar" olduğunu teyit eder. Bir ihlalin varlığını teyit etmek için kısa bir soruşturma süresi kabul edilebilir, ancak kısa olmalı ve belgelenmelidir.

### 2. Bildirimden tek muafiyet

Madde 33(1) yalnızca bir muafiyet sağlar: ihlalin "gerçek kişilerin hak ve özgürlükleri açısından risk teşkil etme olasılığı düşükse" bildirim gerekmez. Eşik risktir, yüksek risk değildir; yüksek risk eşiği Madde 34 ilgili kişi iletişimi içindir, Madde 33 DM bildirimi için değil. Önemsiz olmayan herhangi bir risk durumu bildirim alanına iter.

Bildirmeme gerekçesi Madde 33(5) altında iç kayıtta belgelenmelidir.

### 3. Farkındalık — saat ne zaman başlar?

| Tetikleyici | Farkındalık anı |
|-------------|----------------|
| SOC analisti DLP ve çıkış günlükleriyle sızıntıyı doğrular | Analistin onay zaman damgası |
| Adli firma ihlali doğrulayan ara rapor üretir | Veri sorumlusunun raporu alma zaman damgası |
| Veri işleyen (Madde 28) veri sorumlusunun verilerini etkileyen bir ihlali bildirir | Veri işleyenin bildiriminin alındığı zaman damgası |
| Harici araştırmacı zafiyet ve ifşa kanıtı sunar | İnandırıcı kanıt zaman damgası |
| Kolluk veri sorumlusunu bilgilendirir | Alındığı zaman damgası |
| Kamuya açık sızıntı veya medya raporu veri sorumlusunun verilerini içerir | Veri sorumlusunun verilerine bağlantıdan haberdar olduğu zaman damgası |

Yalnızca şüphe farkındalık değildir. Bir olayın kişisel veri ihlali olup olmadığını teyit etmek için kısa, sınırlandırılmış bir soruşturma süresine izin verilir.

### 4. Risk değerlendirmesi — ENISA önem çerçevesi

EDPB kriterlerine uyarlanmış ENISA metodolojisi:

1. **Veri İşleme Bağlamı** — veri türü, hassasiyet, kimliklendirilebilirlik.
2. **Tanımlama Kolaylığı** — doğrudan, dolaylı, çok zor.
3. **İhlal Koşulları** — tür (gizlilik, bütünlük, erişilebilirlik), hacim, kötü niyet.

Her faktör sayısal puan üretir; toplam önem düzeyini verir (düşük, orta, yüksek, çok yüksek).

### 5. Bildirim içeriği — Madde 33(3)

Bildirim en azından:

(a) ilgili kişi kategorileri ve yaklaşık sayısı ile ilgili kişisel veri kayıtları kategorileri ve yaklaşık sayısı dahil olmak üzere kişisel veri ihlalinin niteliğini açıklamalıdır;

(b) veri koruma sorumlusunun veya daha fazla bilgi alınabilecek diğer iletişim noktasının adını ve iletişim bilgilerini iletmelidir;

(c) kişisel veri ihlalinin olası sonuçlarını açıklamalıdır;

(d) veri sorumlusu tarafından kişisel veri ihlalini ele almak için alınan veya alınması önerilen önlemleri, gerektiğinde olası olumsuz etkilerini azaltmak için önlemleri açıklamalıdır.

### 6. Aşamalı bildirim — Madde 33(4)

Bilginin aynı anda sağlanması mümkün olmadığı durumlarda, bilgi gereksiz gecikmeye uğramadan aşamalar halinde sağlanabilir. Veri sorumlusu:

1. 72 saat içinde, eksik olsa bile, ilk bildirimi gönderir.
2. Eksik öğeleri belirler ve henüz bilinmemelerinin nedenini açıklar.
3. Takip için bir hedef tarih sunar.
4. Olgular bilindikçe, DM tarafından atanan dosya numarasına atıfta bulunarak yazılı olarak takip bildirimleri gönderir.

EDPB 9/2022 §39, gerçekten karmaşık olaylar için aşamalı bildirimin kural olduğunu ve istisna olmadığını teyit eder.

### 7. Baş makam ve tek pencere — Madde 56 ve 60

Sınır ötesi işlemler için veri sorumlusu, ana yerleşim yerinin baş denetim makamına bildirimi sunar. Baş DM, IMI sistemi aracılığıyla ilgili DM'lerle koordine eder.

Veri sorumlusunun AB'de ana yerleşimi yoksa ancak Madde 27 temsilcisi varsa, bildirim temsilcinin bulunduğu Üye Devletin DM'sine ve etkilenen ilgili kişilerin bulunduğu tüm Üye Devletlerin DM'lerine sunulur. AB dışı veri sorumluları için tek pencere yoktur.

| Senaryo | Baş DM | Ek bildirim |
|---------|--------|-------------|
| Sınır ötesi işleme, ana yerleşim İrlanda | İrlanda DPC | Yok — IMI iş birliği |
| Yalnızca tek Üye Devlet | O Üye Devletin DM'si | Yok |
| AB dışı veri sorumlusu, Madde 27 temsilcisi İspanya, ihlal DE ve FR ilgili kişilerini etkiler | Yok | AEPD, BfDI, CNIL |
| BE ve NL'de ortak veri sorumluları | Ortak veri sorumlusu düzenlemesindeki baş | Diğer veri sorumlusunun DM'si IMI üzerinden |

### 8. Madde 33(3)'ü kanıta eşleme

| Gerekli unsur | Kanıt kaynakları | Sahip |
|--------------|-----------------|-------|
| İhlalin niteliği | Olay zaman çizelgesi, adli rapor | CSIRT lideri |
| İlgili kişi kategorileri | Müşteri veritabanı çıktısı, çalışan listesi | Veri sahibi |
| İlgili kişi yaklaşık sayısı | Zaman damgalı veritabanı COUNT sorgusu | Veri sahibi |
| Kişisel veri kayıtları kategorileri | Şema eşlemesi, ROPA referansı | Veri sahibi + VKK |
| Yaklaşık kayıt sayısı | Tablo satır sayıları | Veri sahibi |
| VKK iletişimi | VKK dizini | VKK |
| Olası sonuçlar | ENISA değerlendirmesi, tehdit istihbaratı | VKK + CISO |
| Alınan önlemler | Kontrol altına alma runbook çıktısı, bilet numaraları | CSIRT lideri |
| Önerilen önlemler | CAPA kayıt çıktısı | CSIRT lideri + VKK |

### 9. Madde 33(5) altında belgeleme

Madde 33(5), veri sorumlusunun her kişisel veri ihlalini, ihlale ilişkin olguları, etkilerini ve alınan düzeltici eylemi belgelemesini gerektirir. Bu yükümlülük, DM'ye bildirim yapılıp yapılmadığından bağımsızdır.

İç ihlal kayıt alanları:

1. İç ihlal kimliği ve dosya referansı.
2. Farkındalık tarihi ve saati.
3. Temel olay tarihi ve saati (biliniyorsa).
4. Tespit kaynağı.
5. Olayın ve dahil olan kişisel verilerin açıklaması.
6. İlgili kişi ve kayıtların kategorileri ve yaklaşık sayıları.
7. ENISA puanıyla risk değerlendirmesi.
8. Karar: DM'ye bildir / bildirme, gerekçeyle.
9. Karar: ilgili kişilere bildir / bildirme, gerekçeyle.
10. Kontrol altına alma, yok etme, kurtarma eylemleri ve zaman damgaları.
11. CAPA referansları.
12. DM sorgu veya soruşturmalarının sonuçları.
13. Nihai kapatma tarihi.

### 10. Gönderim kanalları

| Makam | Birincil kanal | Yedek kanal |
|-------|----------------|-------------|
| KVKK (Türkiye) | VERBIS / kvkk.gov.tr e-form | KEP |
| İrlanda DPC | breaches.dataprotection.ie | dpobreaches@dataprotection.ie |
| CNIL (Fransa) | notifications.cnil.fr | Taahhütlü posta |
| BfDI / Länder DPA (Almanya) | Eyalet başına çevrimiçi form | Taahhütlü posta |
| AEPD (İspanya) | Sede electrónica | Taahhütlü posta |
| ICO (Birleşik Krallık) | ICO çevrimiçi form | Taahhütlü posta |

### 11. Çalışılmış zaman çizelgesi

Yüksek güvenle S+0'da tespit edilen bir gizlilik ihlali için:

- S+0: SOC analisti bilet açar, sınıflandırma SEV-2 PD-Y.
- S+0:30: CSIRT lideri teyit eder, savaş odası açık.
- S+1: VKK seferber edildi; farkındalık anı kaydedildi.
- S+6: ENISA puanı orta olarak hesaplandı (bildirim gerekli).
- S+24: Soruşturma yaklaşık sayıları üretir; bildirim taslak v1.
- S+48: Hukuk incelemesi tamamlandı.
- S+60: VKK, baş DM portalı üzerinden gönderir; dosya numarası alınır.
- S+72: Herhangi bir öğe hâlâ beklemedeyse Madde 33(4) aşamalı bildirim bayrağı.
- 7. gün: Sızıntı teyitli takip gönderimi.
- 14. gün: Nihai kapsamla takip gönderimi.

### 12. Geç bildirim

72 saatlik süre kaçırıldıysa daha fazla geciktirmeyin. Hemen gönderin ve gecikmenin nedenlerini, değerlendirme ve kontrol altına alma adımlarını ve tekrarı önlemek için iyileştirilecek kontrolleri ekleyin. EDPB 9/2022, açıklamalı geç gönderimin bildirim yapmamaktan tercih edildiğini teyit eder.

### 13. Bildirimden sonra

- DM ek bilgi, denetim isteyebilir veya düzeltici önlemler uygulayabilir (Madde 58).
- Olay geliştikçe iç kayıtları güncellemeye devam edin.
- Kamuya açıklamalar konusunda İletişim ile koordine edin.
- Acil müdahale kapatıldıktan sonra RCA sürecini tetikleyin.
