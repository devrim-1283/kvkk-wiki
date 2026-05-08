---
Doküman / Document: 30 Gün İşleyişi (SLA, Otomasyon, Eskalasyon) / 30-Day Operation (SLA, Automation, Escalation)
Bölüm / Section: 09-ilgili-kisi-basvurulari
Sahip / Owner: KVKK Sorumlusu / KVKK Officer
Onaylayan / Approved by: Hukuk Müdürü / Head of Legal
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık / Annual
İlgili Mevzuat / Legal Reference: Law No. 6698 (KVKK) Art. 13(2); Application Communiqué Articles 6(5) and 7
---

## English

# 30-Day Operation - SLA, Automation, Escalation

## 1. Legal Framework

KVKK Art. 13(2) + Communiqué Art. 6(5): The data controller concludes the application **at the earliest opportunity according to the nature of the request, and at the latest within 30 days**, free of charge. If the operation entails additional cost, the fee in Communiqué Art. 7 may be charged.

> **Critical:** The "additional 60-day extension" of GDPR Art. 12 does **not** exist in KVKK. 30 days is a **strict** period; every day of overrun is grounds for sanction.

## 2. Calculation of T+0 (Application Date)

| Channel | T+0 |
|---------|-----|
| Written (post / hand-delivered) | Date of service of the document (Communiqué Art. 5(4)) |
| KEP | Date received in the company KEP account (Art. 5(5)) |
| Secure/mobile e-signature e-mail | Date received in the company e-mail system |
| Pre-registered e-mail | Date received in the company e-mail system |
| Online application software | Date the system records the application |

> Weekend/public holiday: 30 days are counted as **calendar days**. There is no "extension" for holidays - the system runs 24/7.

## 3. Daily SLA Roadmap

### 3.1. Day 0 - Application Received

| Hour | Action | Owner |
|------|--------|-------|
| 0-1 hour | Automatic acknowledgment + reference number | System |
| 1-4 hours | Manual pre-check | KVKK specialist |
| 4-24 hours | Triage (right/category/unit) | KVKK Officer |
| 24 hours | Assignment made | KVKK Officer |

### 3.2. Days 1-3 - Identity Verification

- If identity proof is missing, send a follow-up e-mail.
- For high-risk requests, secondary verification (OTP, video, hint).
- If identity is verified, mark as "verified".

### 3.3. Days 3-7 - Data Search

- Query the relevant sources from the data map.
- Parallel searches across IT, CRM, HR, Marketing, Call Center.
- For data with third parties, request from processors (contractual SLA).
- Backup data status - backup rotation plan output.

### 3.4. Days 7-15 - Decision Work

- The relevant unit submits a draft response to the KVKK Officer.
- Legal evaluation (accept/refuse/partial).
- For automated decision objections, Data Science is involved.
- Prepare the list for third-party notification if needed.

### 3.5. Days 15-25 - Response Preparation

- The response letter is templated (Communiqué Art. 6 mandatory items).
- Final Legal sign-off.
- Final read-through by the KVKK Officer.
- Fee calculation (page count, storage media).

### 3.6. Days 25-30 - Delivering the Response

- Dispatch on the chosen channel (KEP / e-mail / postal).
- Notification to third parties (if needed).
- The substance of the request is actually fulfilled (deletion, rectification).
- Closure record.

> **Target:** Average response time **under 15 days**. The 30-day cap is a limit, not a rule.

## 4. Automated Tracking System Requirements

### 4.1. Ticket System Features

- Unique BSV-YYYY-NNNN ID per application.
- KVKK custom fields (channel, right, required unit, deadline).
- Automatic user notifications (acknowledgment, status updates, response).
- Audit log (immutable - Splunk integration).
- KEP integration (incoming KEP -> automatic ticket).
- E-mail integration (kvkk@sirket.com.tr -> ticket).
- Web form integration (https://...kvkk/basvuru -> ticket).

### 4.2. SLA Alerts

| Stage | Alert |
|-------|-------|
| Day 0 | Ticket opened - KVKK specialist Slack/Teams notification |
| Day 3 | Triage complete? - reminder to KVKK Officer |
| Day 7 | Data search progress? - reminder to unit owner |
| Day 14 | Halfway - summary report by KVKK Officer |
| Day 21 | Final week - reminder to Legal |
| Day 25 | Critical - alert KVKK Committee |
| Day 28 | Red alert - notify CISO + CEO |
| Day 30 | SLA exceeded - automatic incident opened (`olay-yonetimi`) |

### 4.3. Data Search Automation

- Centralized search (Elasticsearch/Splunk) - one interface across all sources.
- Federated search by T.R. ID number.
- Source map: CRM (Salesforce/Hubspot), ERP (SAP/Oracle), HR (Workday/SAP SuccessFactors), marketing (HubSpot/Marketo/Mailchimp), call center (Genesys/Avaya), e-mail archive (Mimecast), web logs (CloudFlare/Akamai), CCTV (video management system).
- Results auto-generated as PDF report.

### 4.4. Template Engine

- Response letters use **Word/PDF templates** + variable fields.
- Mandatory Art. 6 fields are auto-populated.
- After Legal sign-off, digital signature + KEP dispatch.

## 5. Identity Verification Methods

### 5.1. Risk-Level Mapping

| Risk level | Request type | Verification method |
|-----------|--------------|---------------------|
| Low | "Is my data being processed?" (Art. 11(a)) | T.R. ID + registered e-mail |
| Medium | Information (Art. 11(b)), rectification (Art. 11(d)) | T.R. ID + two-clue match (e.g., customer no + last order date) |
| High | Data copy, erasure (Art. 11(e)), transfer list (Art. 11(ç)) | OTP + two clues + (if needed) video call |
| Critical | Application by proxy, former employee/customer, special category | Notarized PoA + ID copy + extra verification |

### 5.2. Errors in Verification

- 3 failed OTPs -> lock + human review.
- Wrong clue answer -> additional question.
- Suspicious activity -> notify Incident Management (`08-ihlal-yonetimi/`).

### 5.3. Unverifiable Applications

- 2nd completion request within 14 days.
- 3rd and final completion request within 21 days.
- Day 28 - prepare refusal text on grounds "identity not verified".
- Day 30 - reasoned refusal response.

## 6. Complex Requests

### 6.1. KVKK Has No Extension - "Complex" Is Not an Excuse

Some organizations cite the GDPR analogy and ask for 30+30+30 days. **KVKK does not allow this.** The 30-day cap applies even to complex requests. Process design must accommodate this:

- Automated data search (avoids manual hours).
- Standardized response templates (shortens drafting).
- Legal on-call (same-day evaluations).
- Third-party SLAs kept tight at **7-15 days**.

### 6.2. Multi-Right Requests

If 5 rights are claimed in one application, **30 days applies to all of them**. Single response letter, separate sections per right.

### 6.3. Historical Wide-Scope Requests

E.g., "all data over the last 10 years". For records already deleted because retention has lapsed, the response:

- Summarizes the retention policy.
- States the deletion date.
- Provides a copy of available data.

## 7. Fee Calculation Examples

### 7.1. Written Response (Communiqué Art. 7(1))

| Pages | Fee |
|-------|-----|
| 1-10 pages | **Free** |
| Page 11 | 1 TRY |
| 50-page response | (50-10) x 1 TRY = **40 TRY** |
| 200-page response | (200-10) x 1 TRY = **190 TRY** |

### 7.2. Storage Media (Communiqué Art. 7(2))

| Medium | Cost (approx.) |
|--------|----------------|
| CD (700 MB) | 5-10 TRY |
| DVD (4.7 GB) | 8-15 TRY |
| USB stick (8 GB) | 50-150 TRY |
| USB stick (32 GB) | 150-300 TRY |

> The fee may not exceed the **unit cost** of the storage medium. No markup.

### 7.3. Resulting from Our Error

If the application results from the data controller's (our) error, the **fee is refunded within 7 days** (bank transfer). The invoice is canceled.

### 7.4. VAT

The Communiqué's fee schedule does not explicitly mention VAT. **General practice:** the fee is interpreted as VAT-inclusive; no extra VAT is charged to the applicant. The company invoices VAT-inclusive.

## 8. Escalation Thresholds

### 8.1. SLA Breach Escalation

| Delay | Escalation |
|-------|-----------|
| 0-7 days | Relevant unit manager |
| 7-14 days | Unit director + KVKK Officer |
| 14-21 days | KVKK Committee |
| 21-30 days | CEO + Board notification |
| 30+ days | Incident opened, RCA, prep for explanation to Authority |

### 8.2. Legal Risk Escalation

- Request involves special category data -> Legal + KVKK Committee.
- Request conflicts with a court ruling -> Legal + criminal process.
- Suspected attacker / malicious application -> 08-Incident Management.
- Suspicious power of attorney -> notarial verification.

### 8.3. Communication Risk

- Request reflected in media -> Corporate Communications activates.
- Complaint on social media -> joint Legal + Communications response.
- Authority letter received -> action plan within 5 business days.

## 9. Process Monitoring Dashboards

### 9.1. Operational Dashboard (Daily)

- Number of open applications.
- Today's incoming applications.
- Applications approaching the 7-day mark.
- Applications past 25+ days (red).
- Unassigned applications.
- Awaiting identity verification.
- Awaiting Legal sign-off.

### 9.2. Management Dashboard (Weekly)

- Weekly inflow trends.
- Average response time.
- 30-day compliance rate.
- Distribution by right.
- Distribution by channel.
- Refused vs accepted ratios.
- Authority correspondence open?

### 9.3. Annual Report (KVKK Committee)

- Total applications.
- Annual trend.
- Authority overturn rate of refusals.
- Process improvement recommendations.
- Budget and resource needs.

## 10. Common Mistakes

| Mistake | Correct approach |
|---------|------------------|
| Asking for "extension" on complex requests | Shorten with automation and templates; no extension. |
| Assuming the clock stops on holidays | Clock does not stop; expand on-call coverage. |
| Continuously delaying identity verification | Should be settled in the first 3 days; not at day 28. |
| Squeezing the response into the last day | Should be ready on day 25; 5-day buffer. |
| Sending the response before fee is paid | Up to practice: fee first then response (with Legal sign-off). |
| Omitting the right to complain in the response | Always included - per the spirit of Art. 6. |
| Stopping the clock while waiting for third parties | Clock does not stop; tight third-party SLAs. |

## 11. Process Improvement

### 11.1. Monthly Retrospective

KVKK team monthly review:
- Which step takes the most time?
- Which right is hardest?
- Is automation sufficient?
- Is Legal sign-off time reasonable?

### 11.2. Annual Improvement Cycle

- Benchmarking (sector peers).
- Revisions in light of new Authority decisions.
- Training updates.
- Automation investments.

## 12. Version History

| Version | Date | Change | Approval |
|---------|------|--------|----------|
| 1.0 | 2026-05-08 | First publication | KVKK Committee |

---

## Türkçe

# 30 Gün İşleyişi — SLA, Otomasyon, Eskalasyon

## 1. Yasal Çerçeve

KVKK m.13/2 + Tebliğ MADDE 6/5: Veri sorumlusu başvuruyu **talebin niteliğine göre en kısa sürede ve en geç 30 gün içinde** ücretsiz olarak sonuçlandırır. İşlem maliyet gerektiriyorsa Tebliğ M.7'deki ücret alınabilir.

> **Kritik:** GDPR m.12'de yer alan "ek 60 gün uzatma" KVKK'da **bulunmaz**. 30 gün **kati** süredir; aşıldığı her gün Kurul yaptırım sebebidir.

## 2. Başvuru Tarihi (T+0) Hesabı

| Kanal | T+0 |
|-------|-----|
| Yazılı (posta/elden) | Evrakın tebliğ edildiği tarih (Tebliğ M.5/4) |
| KEP | Şirket KEP hesabına ulaşma tarihi (M.5/5) |
| Güvenli/mobil e-imzalı e-posta | Şirket e-posta sistemine ulaşma tarihi |
| Sistemde kayıtlı e-posta | Şirket e-posta sistemine ulaşma tarihi |
| Çevrimiçi başvuru yazılımı | Sistemin başvuruyu kaydettiği tarih |

> Hafta sonu/resmi tatil: 30 gün **takvim günü** olarak sayılır. Tatilde "uzatma" yoktur — sistem 7/24 işler.

## 3. Günlük SLA Yol Haritası

### 3.1. Gün 0 — Başvuru Geldi

| Saat | Eylem | Sahip |
|------|-------|-------|
| 0-1 saat | Otomatik kabul + referans no | Sistem |
| 1-4 saat | Manuel ön kontrol | KVKK uzmanı |
| 4-24 saat | Triyaj (hak/kategori/birim) | KVKK Sorumlusu |
| 24 saat | Atama yapılır | KVKK Sorumlusu |

### 3.2. Gün 1-3 — Kimlik Doğrulama

- Kimlik kanıtı eksikse ek talep e-postası.
- Yüksek riskli talep ise ikincil doğrulama (OTP, video, ipucu).
- Kimlik doğrulanırsa "doğrulandı" stamp.

### 3.3. Gün 3-7 — Veri Arama

- Veri haritasından ilgili kaynaklara sorgu.
- IT, CRM, IK, Pazarlama, Çağrı Merkezi paralel arama.
- Üçüncü taraflarda veri varsa veri işleyenlere (sözleşmesel SLA) talep.
- Yedeklerde veri durumu — yedek rotasyon planı çıkışı.

### 3.4. Gün 7-15 — Karar Çalışması

- İlgili birim cevap taslağı KVKK Sorumlusuna iletir.
- Hukuk değerlendirme (kabul/ret/kısmi).
- Otomatik karar itirazı varsa Veri Bilim ekibi devreye.
- Üçüncü kişiye bildirim gerekiyorsa liste hazırlığı.

### 3.5. Gün 15-25 — Cevap Hazırlığı

- Cevap mektubu şablona dökülür (Tebliğ M.6 zorunlu unsurlar).
- Hukuk son onay.
- KVKK Sorumlusu son okuma.
- Ücret hesabı (sayfa sayısı, kayıt ortamı).

### 3.6. Gün 25-30 — Cevabın İletilmesi

- Cevap kanalına göre gönderim (KEP / e-posta / posta).
- Üçüncü kişilere bildirim (gerekiyorsa).
- Talebin gereği fiilen yerine getirilir (silme, düzeltme).
- Kapanış kaydı.

> **Hedef:** Ortalama cevap süresi **15 gün altı**. 30 gün son sınır, kural değil.

## 4. Otomatik Takip Sistemi Gereksinimleri

### 4.1. Ticket Sistemi Özellikleri

- Her başvuruya benzersiz BSV-YYYY-NNNN ID.
- KVKK custom alanlar (kanal, hak, gerekli birim, son tarih).
- Otomatik kullanıcı bildirimi (kabul, durum güncellemesi, cevap).
- Audit log (immutable — Splunk integration).
- KEP entegrasyonu (gelen KEP otomatik ticket).
- E-posta entegrasyonu (kvkk@sirket.com.tr → ticket).
- Web form entegrasyonu (https://...kvkk/basvuru → ticket).

### 4.2. SLA Uyarıları

| Aşama | Uyarı |
|-------|-------|
| Gün 0 | Ticket açıldı — KVKK uzmanı slack/teams notification |
| Gün 3 | Triyaj tamam mı? — KVKK Sorumlusu hatırlatma |
| Gün 7 | Veri arama ilerleme? — birim sahibine hatırlatma |
| Gün 14 | Yarı yol — KVKK Sorumlusu özet rapor |
| Gün 21 | Son hafta — Hukuk hatırlatma |
| Gün 25 | Kritik — KVKK Komitesi alert |
| Gün 28 | Kırmızı alarm — CISO + CEO bilgilendirme |
| Gün 30 | SLA aşıldı — otomatik olay açma (`olay-yonetimi`) |

### 4.3. Veri Arama Otomasyonu

- Centralized search (Elasticsearch/Splunk) — tüm kaynaklar tek arayüz.
- T.C. kimlik no üzerinden federated search.
- Kaynak haritası: CRM (Salesforce/Hubspot), ERP (SAP/Oracle), IK (Workday/SAP SuccessFactors), pazarlama (HubSpot/Marketo/Mailchimp), çağrı merkezi (Genesys/Avaya), e-posta arşivi (Mimecast), web log (CloudFlare/Akamai), CCTV (görüntü yönetim sistemi).
- Sonuçlar PDF rapor olarak otomatik üretilir.

### 4.4. Şablon Motoru

- Cevap mektupları **Word/PDF şablonları** + değişken alanlar.
- Tebliğ M.6 zorunlu alanlar otomatik doldurulur.
- Hukuk onay sonrası dijital imza + KEP gönderim.

## 5. Kimlik Doğrulama Yöntemleri

### 5.1. Risk Seviyesine Göre Eşleme

| Risk seviyesi | Talep tipi | Doğrulama yöntemi |
|---------------|-----------|-------------------|
| Düşük | "Verim işleniyor mu" (m.11/a) | T.C. + sistemde kayıtlı e-posta |
| Orta | Bilgi (m.11/b), düzeltme (m.11/d) | T.C. + iki ipucu eşleşmesi (örn. müşteri no + son sipariş tarihi) |
| Yüksek | Veri kopyası, silme (m.11/e), aktarım listesi (m.11/ç) | OTP + iki ipucu + (gerekirse) video görüşme |
| Kritik | Vekil ile başvuru, eski çalışan/müşteri, özel nitelikli veri | Noter onaylı vekaletname + kimlik fotokopisi + ek doğrulama |

### 5.2. Doğrulama Sırasında Hata

- 3 başarısız OTP → kilitlenme + insan onayı.
- Yanlış ipucu cevabı → ek soru.
- Şüpheli aktivite → İhlal Yönetimi'ne bildirim (bkz. `08-ihlal-yonetimi/`).

### 5.3. Doğrulanamayan Başvurular

- 14 gün içinde 2. tamamlama talebi.
- 21 gün içinde 3. ve son tamamlama talebi.
- 28 gün — "kimlik doğrulanamadı" gerekçesiyle reddetme metni hazırlığı.
- 30 gün — gerekçeli ret cevap.

## 6. Karmaşık Talepler

### 6.1. KVKK'da Uzatma Yok — "Karmaşık" Mazeret Olmaz

Bazı kuruluşlar GDPR analojisiyle 30+30+30 gün talep eder. **KVKK bunu kabul etmez.** Karmaşık taleplerde bile 30 gün sınırına uyulması zorunludur. Süreç tasarımı buna göre yapılmalıdır:

- Otomatik veri arama (manuel saatler harcanmasını önler).
- Standardize cevap şablonları (yazma süresini kısaltır).
- Hukuk on-call (gün içinde değerlendirme).
- Üçüncü taraf SLA'ları **7-15 gün** sıkı tutulur.

### 6.2. Çoklu Hak Talebi

Bir başvuruda 5 hak istenmiş olsa bile **30 gün hepsine** uygulanır. Tek cevap mektubu ama her hak için ayrı bölüm.

### 6.3. Geçmişe Dönük Geniş Veri Talebi

Örn. "Son 10 yıldaki tüm verim". Süre dolduğu için silinmiş kayıtlar varsa cevapta:
- Saklama politikamız özetlenir.
- Silinme tarihi belirtilir.
- Mevcut veri kopyası verilir.

## 7. Ücret Hesaplama Örneği

### 7.1. Yazılı Cevap (Tebliğ M.7/1)

| Sayfa Sayısı | Ücret |
|--------------|-------|
| 1-10 sayfa | **Ücretsiz** |
| 11. sayfa | 1 TL |
| 50 sayfa cevap | (50-10) × 1 TL = **40 TL** |
| 200 sayfa cevap | (200-10) × 1 TL = **190 TL** |

### 7.2. Kayıt Ortamı (Tebliğ M.7/2)

| Ortam | Maliyet (yaklaşık) |
|-------|-------------------|
| CD (700 MB) | 5-10 TL |
| DVD (4.7 GB) | 8-15 TL |
| USB bellek (8 GB) | 50-150 TL |
| USB bellek (32 GB) | 150-300 TL |

> Ücret kayıt ortamı **birim maliyetini geçemez**. Kâr eklenemez.

### 7.3. Hatadan Kaynaklı

Başvuru veri sorumlusunun (Şirket) hatasından kaynaklanıyorsa **alınan ücret 7 gün içinde iade** edilir (banka havalesi). Fatura iptal edilir.

### 7.4. KDV

Tebliğ ücret tarifesinde KDV açıkça belirtilmemiştir. **Genel uygulama:** ücret KDV dahil bedel olarak yorumlanır; başvuru sahibinden ek KDV talep edilmez. Şirket faturayı KDV dahil keser.

## 8. Eskalasyon Eşikleri

### 8.1. SLA İhlali Eskalasyonu

| Gecikme | Eskalasyon |
|---------|-----------|
| 0-7 gün | İlgili birim yöneticisi |
| 7-14 gün | Birim direktörü + KVKK Sorumlusu |
| 14-21 gün | KVKK Komitesi |
| 21-30 gün | CEO + Yönetim Kurulu bildirimi |
| 30+ gün | Olay açılır, RCA, Kurul'a açıklama hazırlığı |

### 8.2. Hukuki Risk Eskalasyonu

- Talep özel nitelikli veri içeriyor → Hukuk + KVKK Komitesi.
- Talep mahkeme kararı ile çelişiyor → Hukuk + Adli süreç.
- Saldırgan / kötü niyetli başvuru şüphesi → 08-İhlal Yönetimi.
- Vekaletname şüpheli → Noter doğrulama.

### 8.3. İletişim Riski

- Talep medyaya yansıdı → Kurumsal İletişim devreye.
- Şikâyet sosyal medyada → Hukuk + İletişim ortak yanıt.
- Kurul yazısı geldi → 5 iş günü içinde aksiyon planı.

## 9. Süreç İzleme Kontrol Paneli

### 9.1. Operasyonel Pano (Günlük)

- Açık başvuru sayısı.
- Bugünkü gelen başvurular.
- 7 gün altı yaklaşan başvurular.
- 25+ gün geçmiş başvurular (kırmızı).
- Atanmamış başvurular.
- Kimlik doğrulama bekleyenler.
- Hukuk onay bekleyenler.

### 9.2. Yönetim Panosu (Haftalık)

- Haftalık geliş trendleri.
- Ortalama cevap süresi.
- 30 gün uyum oranı.
- Hak bazında dağılım.
- Kanal bazında dağılım.
- Reddedilenler / kabul edilenler oranı.
- Kurul yazışması var mı?

### 9.3. Yıllık Rapor (KVKK Komitesi)

- Toplam başvuru.
- Yıllık trend.
- Reddedilenlerin Kurul tarafından gözden geçirilme oranı.
- Süreç iyileştirme önerileri.
- Bütçe ve kaynak ihtiyacı.

## 10. Tipik Hatalar

| Hata | Doğru Yaklaşım |
|------|----------------|
| "Karmaşık talep" diye uzatma istemek | Otomasyon ve şablon ile süreyi kısalt; uzatma yok. |
| Tatilde sayacın durduğunu varsaymak | Sayaç durmaz; on-call kapsamı genişlet. |
| Kimlik doğrulamayı sürekli geciktirmek | İlk 3 gün net olmalı; 28. günde başlanmaz. |
| Cevap mektubunu son güne sıkıştırmak | 25. gün hazır olmalı; 5 gün buffer. |
| Ücret tahsil edilmeden cevap göndermek | Uygulama bağlı: önce ücret, sonra cevap (Hukuk onayı ile). |
| Şikayet hakkını cevap mektubunda atlamak | Mutlaka eklenir — Tebliğ M.6 ruhuna uygun. |
| Üçüncü taraf cevabı beklerken sayacı durdurmak | Sayaç durmaz; üçüncü taraf SLA'sı sıkı tutulur. |

## 11. Süreç İyileştirme

### 11.1. Aylık Retrospektif

KVKK ekibi her ay:
- En çok zaman alan adım hangisi?
- Hangi hak en zor?
- Otomasyon yeterli mi?
- Hukuk onay süresi makul mu?

### 11.2. Yıllık İyileştirme Çevrimi

- Kıyaslama (sektör peer'leriyle).
- Yeni Kurul kararları doğrultusunda revizyon.
- Eğitim güncellemesi.
- Otomasyon yatırımı.

## 12. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi |
