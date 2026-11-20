---
Doküman / Document: 5651 Log Kontrol Listesi (KVKK Eşlemeli) / Law 5651 Log Checklist (Mapped to KVKK)
Bölüm / Section: 13-btk-5651
Sahip / Owner: Bilgi Güvenliği Yöneticisi + KVKK Sorumlusu / Information Security Manager + KVKK Officer
Onaylayan / Approved by: KVKK Komitesi / KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-11-20
Gözden Geçirme / Review: Yıllık + tetiklenmiş (yeni log kaynağı, ağ değişikliği, yeni 5651 yönetmeliği) / Annual + triggered (new log source, network change, new 5651 regulation)
İlgili Mevzuat / Legal Reference: 5651 sayılı Kanun md. 2/1-j, 5/3, 6/1-b, 7/2 / Law No. 5651 Arts. 2/1-j, 5/3, 6/1-b, 7/2; İnternet Toplu Kullanım Sağlayıcıları Hakkında Yönetmelik md. 3/1-e, 4, 5 (RG 11.04.2017/30035); Faaliyet Belgesi Yönetmeliği md. 3/1-t, 16 (RG 24.10.2007/26680); 6698 sayılı KVKK md. 4, 5, 7, 10, 12, 28 / KVKK Arts. 4, 5, 7, 10, 12, 28; 5271 sayılı CMK md. 332
---

## English

# Law 5651 Log Checklist (Mapped to KVKK)

> Neutral template, not legal advice. Use one copy per role (hosting / mass-use / access). Legal basis and sources for each row are in the role documents: [yer-saglayici.md](yer-saglayici.md), [toplu-kullanim-saglayici.md](toplu-kullanim-saglayici.md), [erisim-saglayici.md](erisim-saglayici.md). Items marked **DOĞRULANMADI / UNVERIFIED** there remain unverified here.

KVKK principle keys (KVKK Art. 4/2 [S2]): **(a)** lawfulness and fairness; **(b)** accuracy; **(c)** specific, explicit, legitimate purpose; **(ç)** connected, limited, proportionate; **(d)** retention only for the legal or necessary period. Other KVKK keys: **Art. 5/2-a/ç** legal basis; **Art. 7** destruction; **Art. 10** notice; **Art. 12** security; **Art. 28/2-a** crime-investigation exemption.

## 1. Scope and purpose

| # | Check | 5651 requirement | KVKK link | Evidence | Status |
|---|---|---|---|---|---|
| 1.1 | Roles identified and documented (hosting / mass-use / access / social network) | 5651 Art. 2 definitions | 4/2-a, 4/2-c | Role memo | ☐ |
| 1.2 | Purpose of each log written as "5651 legal obligation" and nothing broader | 5651 Art. 5/3, 6/1-b, 7/2 | 4/2-c; 5/2-a/ç | Processing inventory entry | ☐ |
| 1.3 | No explicit consent requested for 5651 logs | Statutory duty | 5/2-a ("expressly provided for by laws") | Login / sign-up screens | ☐ |
| 1.4 | Privacy notice names the 5651 purpose, legal basis, retention, recipients (courts, prosecutors, Cybersecurity Presidency) | - | Art. 10 | Notice text, screenshot of pre-login display | ☐ |
| 1.5 | Logs used for 5651 not reused for marketing, analytics or staff monitoring without a separate basis | - | 4/2-c, 4/2-ç | Access policy, data-flow diagram | ☐ |

## 2. Field set (data minimisation)

| # | Check | 5651 requirement | KVKK link | Evidence | Status |
|---|---|---|---|---|---|
| 2.1 | **Mass-use:** internal IP, MAC, start/end time logged | Reg. 2017 Art. 3/1-e | 4/2-ç | DHCP + session log sample | ☐ |
| 2.2 | **Mass-use:** NAT mapping with public IP **and port** logged | Reg. 2017 Art. 3/1-e | 4/2-ç | NAT log sample | ☐ |
| 2.3 | **Mass-use:** destination IP logged (safest reading; scope UNVERIFIED) | Reg. 2017 Art. 3/1-e | 4/2-ç (document the reasoning) | Flow log sample | ☐ |
| 2.4 | **Hosting:** source IP and port, destination IP and port, time, requested address, method, result | Law Art. 2/1-j; FB-Yön 2007 Art. 3/1-t | 4/2-ç | Access log sample | ☐ |
| 2.5 | **Access provider:** traffic data per regulation (subscriber data, connection times, IP and ports) | Law Art. 6/1-b; FB-Yön Art. 3/1-f | 4/2-ç | Operator log spec | ☐ |
| 2.6 | Fields **beyond** 5651 (per-user DNS queries, URLs for mass-use, HTTP headers, TCKN) either absent or covered by a separate, written legal basis and proportionality note | Not required by 5651 | 4/2-ç; 5/2 | Field list with basis per field | ☐ |
| 2.7 | No passwords, OTP codes, tokens, request bodies or full query strings with personal data in logs | - | 4/2-ç; Art. 12 | Regex scan result | ☐ |
| 2.8 | Blocked-content attempts kept as aggregate counters, not per user (mass-use filter) | Filter mandatory (Reg. Art. 4/1-a); per-user log not required | 4/2-ç | Filter reporting config | ☐ |

## 3. Accuracy and integrity

| # | Check | 5651 requirement | KVKK link | Evidence | Status |
|---|---|---|---|---|---|
| 3.1 | All log sources NTP-synchronised; time zone recorded | Correct start/end times (Reg. Art. 3/1-e) | 4/2-b | NTP config, drift alarm | ☐ |
| 3.2 | **Hosting / access:** accuracy, integrity, confidentiality ensured | Law Art. 5/3, 6/1-b | 4/2-b; Art. 12 | Integrity design | ☐ |
| 3.3 | **Commercial mass-use:** daily integrity value recorded and kept 2 years | Reg. Art. 5/1-e | Art. 12 | Daily hash files | ☐ |
| 3.4 | **Non-commercial mass-use:** integrity value optional; if used, daily hash chain + ESHS time stamp documented as "above minimum" | Not in Reg. Art. 4 | Art. 12 | Seal/verify job logs | ☐ |
| 3.5 | Integrity verification is cryptographic (recompute and compare), not just "file exists" | Evidential value | 4/2-b | Verification report | ☐ |
| 3.6 | Log write path is append-only / WORM; deletion outside the retention job raises an alarm | Integrity (Art. 5/3, 6/1-b) | Art. 12 | Storage policy, alarm test | ☐ |

## 4. Retention and destruction

| # | Check | 5651 requirement | KVKK link | Evidence | Status |
|---|---|---|---|---|---|
| 4.1 | **Mass-use:** retention exactly 2 years (730/731 days) | Reg. Art. 4/1-b, 5/1-d | 4/2-d | Retention setting | ☐ |
| 4.2 | **Hosting:** fixed period between 1 and 2 years chosen, with written reasoning (old 6-month text superseded by law floor) | Law Art. 5/3 | 4/2-d | Retention schedule row | ☐ |
| 4.3 | **Access provider:** period within 6 months-2 years per regulation | Law Art. 6/1-b | 4/2-d | Retention schedule row | ☐ |
| 4.4 | Automatic destruction at period end, in the next periodic destruction cycle | - | Art. 7; destruction regulation | Destruction job logs, minutes | ☐ |
| 4.5 | Backups and archives follow the same end date (no copy outlives the period except legal hold) | - | 4/2-d; Art. 7 | Backup retention config | ☐ |
| 4.6 | Legal hold procedure: only for a specific written request, scoped, recorded, released when closed | CMK Art. 332 requests | 4/2-d; 28/2-a | Legal hold register | ☐ |
| 4.7 | Retention schedule in [../04-veri-saklama-ve-imha/](../04-veri-saklama-ve-imha/) matches this checklist (no "10 years" or "6 months" for 5651 logs) | Law Art. 5/3, 6/1-b; Reg. Art. 4 | 4/2-d | Cross-check note | ☐ |

## 5. Access control and disclosure

| # | Check | 5651 requirement | KVKK link | Evidence | Status |
|---|---|---|---|---|---|
| 5.1 | Read access limited to named roles (e.g. legal responder, security lead); no general IT access | Confidentiality (Art. 5/3, 6/1-b; Reg. Art. 5/1-e) | Art. 12/1 | Access matrix | ☐ |
| 5.2 | Every read of 5651 logs is itself logged (who, when, query, reason) | - | Art. 12/1, 12/3 | Audit log sample | ☐ |
| 5.3 | Contractor running the system has a written data processing agreement and acts on instructions | - | Art. 12/2 | Signed DPA | ☐ |
| 5.4 | Disclosure only on written request from prosecutor, judge or court (or competent authority); scope limited to requested time range and IP:port | CMK Art. 332/1 (10 days) | 28/2-a (proportionate) | Request register | ☐ |
| 5.5 | Delivered files hashed and listed in a hand-over record | - | Art. 12 | Hand-over records | ☐ |
| 5.6 | Requests from employers or tenants for staff traffic logs handled under a written rule (default: refuse without legal basis) | - | 4/2-c; 5/2 | Rule text | ☐ |
| 5.7 | Logs stored in Türkiye or, if abroad / via a foreign CDN, transfer assessed under KVKK Art. 9 | - | Art. 9 | Transfer assessment ([../07-aktarim/](../07-aktarim/)) | ☐ |

## 6. Incidents

| # | Check | Requirement | Evidence | Status |
|---|---|---|---|---|
| 6.1 | Breach of 5651 logs (leak, tampering) triggers KVKK breach procedure | KVKK Art. 12/5 | IR plan branch | ☐ |
| 6.2 | Cyber incidents and vulnerabilities reported to the Cybersecurity Presidency without delay | Law 7545 Art. 7/1-b | IR plan branch | ☐ |
| 6.3 | Log pipeline outage (no logs for > X minutes) alarmed and recorded as a compliance gap | 5651 retention duties | Alarm test | ☐ |

## 7. Sources

- [S1] Role documents in this section (each with its own primary sources and access dates).
- [S2] Law No. 6698 (KVKK): https://www.mevzuat.gov.tr/MevzuatMetin/1.5.6698.pdf (accessed 2026-11-20)
- [S3] Law No. 5651, consolidated: https://www.mevzuat.gov.tr/MevzuatMetin/1.5.5651.pdf (accessed 2026-11-20)
- [S4] Regulation on Internet Mass-Use Providers, OG 11.04.2017/30035: https://www.resmigazete.gov.tr/eskiler/2017/04/20170411-3.htm (accessed 2026-11-20)
- [S5] Activity Certificate Regulation, OG 24.10.2007/26680: https://www.resmigazete.gov.tr/eskiler/2007/10/20071024-12.htm (accessed 2026-11-20)
- [S6] Law No. 7545: https://www.mevzuat.gov.tr/MevzuatMetin/1.5.7545.pdf (accessed 2026-11-20)

---

## Türkçe

# 5651 Log Kontrol Listesi (KVKK Eşlemeli)

> Nötr şablondur, hukuki görüş değildir. Her rol (yer / toplu kullanım / erişim) için ayrı kopya kullanılır. Her satırın hukuki dayanağı ve kaynakları rol dokümanlarındadır: [yer-saglayici.md](yer-saglayici.md), [toplu-kullanim-saglayici.md](toplu-kullanim-saglayici.md), [erisim-saglayici.md](erisim-saglayici.md). Orada **DOĞRULANMADI / UNVERIFIED** işaretli noktalar burada da doğrulanmamış sayılır.

KVKK ilke anahtarları (KVKK md. 4/2 [S2]): **(a)** hukuka ve dürüstlük kurallarına uygunluk; **(b)** doğru ve gerektiğinde güncel olma; **(c)** belirli, açık ve meşru amaç; **(ç)** amaçla bağlantılı, sınırlı ve ölçülü olma; **(d)** ilgili mevzuatta öngörülen veya gerekli süre kadar muhafaza. Diğer anahtarlar: **md. 5/2-a/ç** hukuki sebep; **md. 7** imha; **md. 10** aydınlatma; **md. 12** güvenlik; **md. 28/2-a** suç soruşturması istisnası.

## 1. Kapsam ve amaç

| # | Kontrol | 5651 şartı | KVKK bağı | Kanıt | Durum |
|---|---|---|---|---|---|
| 1.1 | Roller belirlenip yazılı hâle getirildi (yer / toplu kullanım / erişim / sosyal ağ) | 5651 md. 2 tanımları | 4/2-a, 4/2-c | Rol notu | ☐ |
| 1.2 | Her logun amacı "5651 kanuni yükümlülüğü" olarak yazıldı, daha geniş değil | 5651 md. 5/3, 6/1-b, 7/2 | 4/2-c; 5/2-a/ç | Envanter kaydı | ☐ |
| 1.3 | 5651 logları için açık rıza istenmiyor | Kanuni yükümlülük | 5/2-a ("Kanunlarda açıkça öngörülmesi") | Giriş / kayıt ekranları | ☐ |
| 1.4 | Aydınlatma metni 5651 amacını, hukuki sebebi, süreyi ve alıcıları (mahkeme, savcılık, Siber Güvenlik Başkanlığı) sayıyor | - | md. 10 | Metin, girişten önceki gösterimin ekran görüntüsü | ☐ |
| 1.5 | 5651 logları ayrı dayanak olmadan pazarlama, analitik veya çalışan izleme için kullanılmıyor | - | 4/2-c, 4/2-ç | Erişim politikası, veri akış şeması | ☐ |

## 2. Alan seti (veri minimizasyonu)

| # | Kontrol | 5651 şartı | KVKK bağı | Kanıt | Durum |
|---|---|---|---|---|---|
| 2.1 | **Toplu kullanım:** iç IP, MAC, başlangıç/bitiş zamanı tutuluyor | 2017 Yön. md. 3/1-e | 4/2-ç | DHCP + oturum logu örneği | ☐ |
| 2.2 | **Toplu kullanım:** genel IP **ve port** ile NAT eşlemesi tutuluyor | 2017 Yön. md. 3/1-e | 4/2-ç | NAT logu örneği | ☐ |
| 2.3 | **Toplu kullanım:** hedef IP tutuluyor (en güvenli okuma; kapsamı DOĞRULANMADI) | 2017 Yön. md. 3/1-e | 4/2-ç (gerekçe yazılı) | Akış logu örneği | ☐ |
| 2.4 | **Yer sağlayıcı:** kaynak IP ve port, hedef IP ve port, zaman, istenen adres, metot, sonuç | Kanun md. 2/1-j; FB-Yön 2007 md. 3/1-t | 4/2-ç | Erişim logu örneği | ☐ |
| 2.5 | **Erişim sağlayıcı:** yönetmeliğe göre trafik bilgisi (abone verisi, bağlantı zamanları, IP ve port) | Kanun md. 6/1-b; FB-Yön md. 3/1-f | 4/2-ç | İşletmeci log tanımı | ☐ |
| 2.6 | 5651'in **ötesindeki** alanlar (kullanıcı bazında DNS sorgusu, toplu kullanımda URL, HTTP başlıkları, TCKN) ya yok ya da ayrı, yazılı hukuki sebep ve ölçülülük notuyla tutuluyor | 5651 istemez | 4/2-ç; 5/2 | Alan başına dayanaklı alan listesi | ☐ |
| 2.7 | Loglarda parola, OTP kodu, token, istek gövdesi veya kişisel veri taşıyan tam sorgu dizesi yok | - | 4/2-ç; md. 12 | Regex tarama sonucu | ☐ |
| 2.8 | Engellenen içerik denemeleri kullanıcı bazında değil toplu sayaç olarak tutuluyor (toplu kullanım filtresi) | Filtre zorunlu (Yön. md. 4/1-a); kullanıcı bazında log istenmez | 4/2-ç | Filtre raporlama ayarı | ☐ |

## 3. Doğruluk ve bütünlük

| # | Kontrol | 5651 şartı | KVKK bağı | Kanıt | Durum |
|---|---|---|---|---|---|
| 3.1 | Tüm log kaynakları NTP ile eşzamanlı, saat dilimi kayıtlı | Doğru başlangıç/bitiş zamanı (Yön. md. 3/1-e) | 4/2-b | NTP ayarı, sapma alarmı | ☐ |
| 3.2 | **Yer / erişim:** doğruluk, bütünlük, gizlilik sağlanıyor | Kanun md. 5/3, 6/1-b | 4/2-b; md. 12 | Bütünlük tasarımı | ☐ |
| 3.3 | **Ticari toplu kullanım:** günlük bütünlük değeri kaydediliyor ve 2 yıl saklanıyor | Yön. md. 5/1-e | md. 12 | Günlük hash dosyaları | ☐ |
| 3.4 | **Ticari olmayan toplu kullanım:** bütünlük değeri ihtiyari; kullanılıyorsa günlük hash zinciri + ESHS zaman damgası "asgarinin üstü" olarak belgelenmiş | Yön. md. 4'te yok | md. 12 | Mühür/doğrulama iş logları | ☐ |
| 3.5 | Bütünlük doğrulaması kriptografik (yeniden hesapla ve karşılaştır), yalnız "dosya var mı" değil | Delil değeri | 4/2-b | Doğrulama raporu | ☐ |
| 3.6 | Log yazım yolu yalnız ekleme / WORM; saklama işi dışındaki silme alarm üretir | Bütünlük (md. 5/3, 6/1-b) | md. 12 | Depolama politikası, alarm testi | ☐ |

## 4. Saklama ve imha

| # | Kontrol | 5651 şartı | KVKK bağı | Kanıt | Durum |
|---|---|---|---|---|---|
| 4.1 | **Toplu kullanım:** saklama tam 2 yıl (730/731 gün) | Yön. md. 4/1-b, 5/1-d | 4/2-d | Saklama ayarı | ☐ |
| 4.2 | **Yer sağlayıcı:** 1 ile 2 yıl arasında sabit süre, yazılı gerekçeyle seçildi (eski altı aylık metin kanuni alt sınırla aşıldı) | Kanun md. 5/3 | 4/2-d | Saklama tablosu satırı | ☐ |
| 4.3 | **Erişim sağlayıcı:** yönetmeliğe göre 6 ay-2 yıl aralığında süre | Kanun md. 6/1-b | 4/2-d | Saklama tablosu satırı | ☐ |
| 4.4 | Süre sonunda otomatik imha, ilk periyodik imha döneminde | - | md. 7; İmha Yönetmeliği | İmha iş logları, tutanak | ☐ |
| 4.5 | Yedek ve arşivler aynı bitiş tarihine uyuyor (hukuki muhafaza dışında hiçbir kopya süreyi aşmıyor) | - | 4/2-d; md. 7 | Yedek saklama ayarı | ☐ |
| 4.6 | Hukuki muhafaza (legal hold) usulü: yalnız belirli yazılı talep için, kapsamlı, kayıtlı, dosya kapanınca kaldırılır | CMK md. 332 talepleri | 4/2-d; 28/2-a | Muhafaza defteri | ☐ |
| 4.7 | [../04-veri-saklama-ve-imha/](../04-veri-saklama-ve-imha/) saklama tablosu bu listeyle uyumlu (5651 logları için "10 yıl" veya "6 ay" yok) | Kanun md. 5/3, 6/1-b; Yön. md. 4 | 4/2-d | Çapraz kontrol notu | ☐ |

## 5. Erişim kontrolü ve paylaşım

| # | Kontrol | 5651 şartı | KVKK bağı | Kanıt | Durum |
|---|---|---|---|---|---|
| 5.1 | Okuma yetkisi adı belirli rollerle sınırlı (ör. hukuki cevap sorumlusu, güvenlik lideri); genel BT erişimi yok | Gizlilik (md. 5/3, 6/1-b; Yön. md. 5/1-e) | md. 12/1 | Erişim matrisi | ☐ |
| 5.2 | 5651 loglarının her okunması ayrıca loglanıyor (kim, ne zaman, sorgu, gerekçe) | - | md. 12/1, 12/3 | Denetim logu örneği | ☐ |
| 5.3 | Sistemi işleten yüklenicinin yazılı veri işleme sözleşmesi var ve talimatla çalışıyor | - | md. 12/2 | İmzalı sözleşme | ☐ |
| 5.4 | Paylaşım yalnız savcı, hâkim veya mahkemenin (ya da yetkili merciin) yazılı talebiyle; kapsam istenen zaman aralığı ve IP:port ile sınırlı | CMK md. 332/1 (10 gün) | 28/2-a (orantılı) | Talep defteri | ☐ |
| 5.5 | Teslim edilen dosyaların hash'i alınıp teslim tutanağına yazılıyor | - | md. 12 | Teslim tutanakları | ☐ |
| 5.6 | İşverenin veya kiracının çalışan trafik logu talebi yazılı kurala göre ele alınıyor (varsayılan: hukuki dayanak yoksa ret) | - | 4/2-c; 5/2 | Kural metni | ☐ |
| 5.7 | Loglar Türkiye'de tutuluyor; yurt dışında / yabancı CDN üzerinden ise KVKK md. 9 aktarım değerlendirmesi yapıldı | - | md. 9 | Aktarım değerlendirmesi ([../07-aktarim/](../07-aktarim/)) | ☐ |

## 6. Olaylar

| # | Kontrol | Şart | Kanıt | Durum |
|---|---|---|---|---|
| 6.1 | 5651 loglarının ihlali (sızıntı, değiştirme) KVKK ihlal prosedürünü tetikliyor | KVKK md. 12/5 | Olay müdahale planı dalı | ☐ |
| 6.2 | Siber olay ve zafiyetler Siber Güvenlik Başkanlığına gecikmeksizin bildiriliyor | 7545 md. 7/1-b | Olay müdahale planı dalı | ☐ |
| 6.3 | Log hattı kesintisi (X dakikadan uzun log yok) alarm üretiyor ve uyum açığı olarak kaydediliyor | 5651 saklama yükümlülükleri | Alarm testi | ☐ |

## 7. Kaynaklar

- [S1] Bu bölümdeki rol dokümanları (her biri kendi birincil kaynakları ve erişim tarihleriyle).
- [S2] 6698 sayılı KVKK: https://www.mevzuat.gov.tr/MevzuatMetin/1.5.6698.pdf (erişim 2026-11-20)
- [S3] 5651 sayılı Kanun, konsolide: https://www.mevzuat.gov.tr/MevzuatMetin/1.5.5651.pdf (erişim 2026-11-20)
- [S4] İnternet Toplu Kullanım Sağlayıcıları Hakkında Yönetmelik, RG 11.04.2017/30035: https://www.resmigazete.gov.tr/eskiler/2017/04/20170411-3.htm (erişim 2026-11-20)
- [S5] Faaliyet Belgesi Yönetmeliği, RG 24.10.2007/26680: https://www.resmigazete.gov.tr/eskiler/2007/10/20071024-12.htm (erişim 2026-11-20)
- [S6] 7545 sayılı Kanun: https://www.mevzuat.gov.tr/MevzuatMetin/1.5.7545.pdf (erişim 2026-11-20)
