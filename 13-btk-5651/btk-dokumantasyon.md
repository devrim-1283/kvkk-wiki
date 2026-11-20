---
Doküman / Document: BTK / Siber Güvenlik Başkanlığı Pratik Dokümantasyon Rehberi / BTK / Cybersecurity Presidency Practical Documentation Guide
Bölüm / Section: 13-btk-5651
Sahip / Owner: Hukuk + Bilgi Güvenliği Yöneticisi / Legal + Information Security Manager
Onaylayan / Approved by: KVKK Komitesi / KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-11-20
Gözden Geçirme / Review: Üç aylık (portal adresleri hızlı değişiyor) + tetiklenmiş / Quarterly (portal addresses change quickly) + triggered
İlgili Mevzuat / Legal Reference: 5651 sayılı Kanun (7590 işlenmiş) / Law No. 5651 (incl. Law 7590); 7545 sayılı Siber Güvenlik Kanunu md. 2, 7, 16, 17, Geçici md. 1-2 / Cybersecurity Law No. 7545 Arts. 2, 7, 16, 17, Provisional Arts. 1-2; 5809 sayılı Elektronik Haberleşme Kanunu md. 60/A / Electronic Communications Law No. 5809 Art. 60/A; Elektronik Haberleşme Sektöründe Şebeke ve Bilgi Güvenliği Yönetmeliği (RG 13.07.2014/29059); İnternet Toplu Kullanım Sağlayıcıları Hakkında Yönetmelik (RG 11.04.2017/30035); Faaliyet Belgesi Yönetmeliği (RG 24.10.2007/26680); 6698 sayılı KVKK md. 12/5 / KVKK Art. 12/5
---

## English

# BTK / Cybersecurity Presidency Practical Documentation Guide

> Neutral template, not legal advice. Portal addresses below were checked on 2026-11-20; several were under maintenance or unreachable that day. Re-check before every filing. Unconfirmed items are marked **DOĞRULANMADI / UNVERIFIED**.

## 1. Who does what (as of 2026-11-20)

| Body | Role relevant to companies | Basis |
|---|---|---|
| **Cybersecurity Presidency** (*Siber Güvenlik Başkanlığı*, SGB) | Authority under Law 5651 since 31.07.2026 (fines, removal/blocking decisions, hosting provider matters); authority under Law 7545; urgent measures under 5809 Art. 60/A; took over USOM functions | Law 7590 Arts. 21, 26, 27 [S1]; Law 7545 [S2] |
| **BTK** (*Bilgi Teknolojileri ve İletişim Kurumu*) | Operator authorisation and sector regulation under Law 5809; still hosts some legacy 5651 services (e-Devlet hosting notification, IP Log page) | Law 5809; pages checked 2026-11-20 [S5][S6] |
| **Local civil administrator** (governorship / district governorship) | Permit and inspection of **commercial** mass-use providers | 5651 Art. 7/1; 2017 Regulation Arts. 6, 10, 13 [S3][S4] |
| **Access Providers Association** (*Erişim Sağlayıcıları Birliği*, ESB) | Receives and forwards removal/blocking decisions; may notify content/hosting providers by e-mail | 5651 Art. 6/A [S3]; site `https://www.esb.org.tr/` reachable 2026-11-20 |
| **Prosecutor / court** | Written information requests, 10-day answer duty | CMK Art. 332 (see [toplu-kullanim-saglayici.md](toplu-kullanim-saglayici.md) §5) |
| **KVKK Authority** | Personal data breaches involving logs | KVKK Art. 12/5 (see [../08-ihlal-yonetimi/](../08-ihlal-yonetimi/)) |

Transitional rule: until the Cybersecurity Presidency issues its own secondary regulations, existing regulations apply and references to BTK are read as references to the Presidency (Law 7545 Provisional Art. 2/1, added by Law 7590) [S1].

## 2. Forms and portals

| Need | Where | Status on 2026-11-20 | Documents / inputs |
|---|---|---|---|
| Hosting provider notification (*yer sağlayıcılığı bildirimi*) | e-Devlet: `https://www.turkiye.gov.tr/btk-yer-saglayiciligi-bildirimi-4322` (BTK service, description "5651 Sayılı Kanunun ilgili maddesi gereğince Yer Sağlayıcı Bildirimlerinin değerlendirilmesi") [S6] | Service page reachable; requires e-Devlet login | Form fields behind login not reviewed (**DOĞRULANMADI / UNVERIFIED**). Legacy 2007 rule: Annex-5 petition + Annex-6 form, originals within one week (FB-Yön Art. 9/2) [S7] |
| Hosting provider interface | `https://yersaglayici.btk.gov.tr/` and `https://yersaglayici.siberguvenlik.gov.tr/` | Both showed "Sitemiz bakım aşamasındadır" (maintenance) | Secondary (2021): monthly CSV uploads of hosted and registered domains (**DOĞRULANMADI / UNVERIFIED**) [S8] |
| Hosting provider list | `https://www.btk.gov.tr/yer-saglayici-listesi` | Page reachable; linked list returned 404 | - |
| Commercial mass-use permit (*izin belgesi*) | Governorship IT branch / district governorship IT unit (2017 Reg. Art. 13/1) [S4] | Offline procedure | Petition; workplace opening and operating licence obtained first (Art. 6/1); responsible manager notified (Art. 8/1); permit issued in Annex-1 form within 15 days (Art. 6/2-3) [S4] |
| SOME registration on SİP (SOME Communication Platform) | Cybersecurity Presidency; Annex-1 "SOME İletişim Bilgileri Formu" with an official letter to the address or KEP below [S9] | Guide v1.0 dated 20.05.2026 | Only organisational SOME units, no individuals; institutional e-mail (not a person's address); at least one admin user; two-factor login (SMS by default) [S9] |
| Malicious link lists, vulnerability notices, CVE applications, cyber reports (formerly USOM) | `https://www.siberguvenlik.gov.tr/` | `usom.gov.tr` shows a notice that these services continue at siberguvenlik.gov.tr; `.txt` list downloads ended on **1 June 2026**, API recommended [S10] | API integration for blocklists |
| BTK e-Başvuru | Not located on 2026-11-20 (`ebasvuru.btk.gov.tr` did not resolve) | **DOĞRULANMADI / UNVERIFIED** | - |
| IP Log İmzalayıcı (BTK signing software) | `https://www.btk.gov.tr/ip-log-imzalayici` | Page reachable: software no longer supported since the 2017 Regulation [S5] | Do not plan around it |

## 3. Compliance file: documents to keep

Keep one controlled folder per role. Minimum contents (recommendation):

| Role | Document | Why |
|---|---|---|
| All | Role assessment memo (which 5651 roles apply, why, date, approver) | Shows the analysis behind every other decision |
| All | Published identification information (screenshot + date) | 5651 Art. 3/1; UE-Yön Art. 5 |
| All | Legal-notice mailbox, on-call roster, takedown runbook | 4-hour (8, 8/A) and 2-hour (5809 Art. 60/A) clocks |
| All | Register of authority requests and decisions (date-time received, sender, scope, action, time, responder, file hash) | Evidence of compliance; KVKK Art. 28/2-a proportionality |
| Hosting provider | Notification receipt / number; renewal or change notices | 5651 Art. 5/6 fine for not notifying |
| Hosting provider | Traffic-log specification and retention setting (1-2 years) with integrity method | 5651 Art. 5/3 |
| Mass-use provider | Network diagram (DHCP, NAT, session/RADIUS, filter), log field list, 2-year retention evidence, filter configuration | 2017 Reg. Arts. 3/1-e, 4 |
| Mass-use provider (public area) | SMS identification flow, privacy notice shown before login | Reg. Art. 4/1-c; KVKK Art. 10 |
| Commercial mass-use | Permit, workplace licence, responsible manager notice, static IP and change notices, daily integrity value records, camera retention (90 days) | Reg. Arts. 5, 6, 8, 9 |
| All using information systems | Cyber incident and vulnerability reporting procedure to the Cybersecurity Presidency | Law 7545 Art. 7/1-b |

## 4. Cybersecurity obligations beyond 5651

### 4.1 Law 7545 (Cybersecurity Law), applies broadly

- Scope, Art. 2/1: public bodies, professional organisations, **natural and legal persons** and entities without legal personality that exist, operate or provide services in cyberspace [S2].
- Art. 7/1: those providing services, collecting or processing data using information systems must (a) deliver data, information, documents, hardware, software requested by the Presidency with priority and on time; (b) take the measures in legislation and **report vulnerabilities or cyber incidents** detected in their service area to the Presidency "**gecikmeksizin**" (without delay); (c) procure cybersecurity products for public bodies and **critical infrastructure** from Presidency-authorised providers; (ç) certified cybersecurity firms obtain approval before starting; (d) implement Presidency policies, strategies and other regulatory acts [S2].
- Art. 16/10: breach of Art. 7/1 (a), (b), (c): administrative fine **1,000,000-10,000,000 TL** ((a) added by Law 7590) [S2]. Art. 16/1: not giving requested information to authorised bodies: 1-3 years imprisonment and judicial fine. Art. 17/1: defence is taken before a fine; 30 days to respond [S2].
- Provisional Art. 1/6: implementing regulations to enter into force within one year (i.e. by about 19.03.2026); until then existing rules apply where not contrary [S2]. Which implementing regulations have been published, and whether they set an hour-based reporting deadline: **DOĞRULANMADI / UNVERIFIED**.

Practical reading for an ordinary company (interpretation): Art. 7/1-b is the duty most likely to apply. Add "report to the Cybersecurity Presidency without delay" as a branch of the incident response plan, next to the KVKK breach notification ("en kısa sürede", KVKK Art. 12/5; Board decision 2019/10 sets 72 hours, see [../08-ihlal-yonetimi/](../08-ihlal-yonetimi/)).

### 4.2 Presidential Circular 2019/12 and the Information and Communication Security Guide

According to the Cybersecurity Presidency FAQ (version 1.1, 02.07.2026), the circular does **not** cover private legal persons except those operating critical infrastructure, although applying its measures is beneficial to them (finding of the 2026-11-11 study; not re-fetched on 2026-11-20) [S11].

### 4.3 Sector regulation: "Elektronik Haberleşme Sektörüne İlişkin Siber Güvenlik Yönetmeliği"

- A regulation with this **exact title** was not found in the Official Gazette, mevzuat.gov.tr or BTK searches on 2026-11-20 (**DOĞRULANMADI / UNVERIFIED** that it exists).
- The closest instrument is the **Elektronik Haberleşme Sektöründe Şebeke ve Bilgi Güvenliği Yönetmeliği** (BTK, OG 13.07.2014/29059). Its Art. 1/1 states its purpose as setting the procedures **operators** (*işletmeciler*) must follow for network and information security; Art. 3/1-ı defines an operator as a company providing electronic communications services and/or networks under an authorisation; Art. 35 requires operators to set up a SOME and work with USOM against DoS/DDoS; Art. 38 requires operators to notify the authority of breaches affecting more than 5 % of subscribers or business continuity. Personal data processing is outside its scope (Art. 1/2) [S12] (secondary consolidated copy; the Official Gazette original was not retrieved: **DOĞRULANMADI / UNVERIFIED** in primary text).
- **Who it applies to:** authorised electronic communications operators only. An ordinary company, hotspot venue, SaaS or hosting customer that is **not** authorised under Law 5809 is not an "operator" and is not directly bound. It is still bound by Law 7545 (§4.1) and, for 5651 roles, by the 5651 rules in this section.
- After Law 7590, the authority for these sector cybersecurity rules may sit with BTK or the Cybersecurity Presidency depending on the transferred power; not resolved here (**DOĞRULANMADI / UNVERIFIED**).

## 5. Contact points (verified 2026-11-20 unless noted)

| Body | Contact | Source |
|---|---|---|
| Cybersecurity Presidency | Address: T.C. Cumhurbaşkanlığı Çankaya Yerleşkesi Ziaur Rahman Cad. Çankaya / ANKARA; KEP: `siberguvenlikbaskanligi@hs01.kep.tr`; SİP support: `sip@siberguvenlik.gov.tr`; web: `https://www.siberguvenlik.gov.tr/` | SİP guide [S9] |
| BTK | Eskişehir Yolu 10.Km No:276 06530 Çankaya ANKARA; phone +90 (0312) 412 20 00; consumer line 120 | BTK site footer [S5] |
| ESB | `https://www.esb.org.tr/` | Reachable 2026-11-20 |
| USOM (legacy) | `https://www.usom.gov.tr/` now a notice page pointing to siberguvenlik.gov.tr | [S10] |

## 6. Sources

- [S1] Law No. 7590, OG 31.07.2026/33326: https://www.resmigazete.gov.tr/eskiler/2026/07/20260731-2.htm (accessed 2026-11-20)
- [S2] Law No. 7545 (Cybersecurity Law), consolidated (incl. 7590): https://www.mevzuat.gov.tr/MevzuatMetin/1.5.7545.pdf ; original OG 19.03.2025/32846: https://www.resmigazete.gov.tr/eskiler/2025/03/20250319-1.htm (accessed 2026-11-20)
- [S3] Law No. 5651, consolidated: https://www.mevzuat.gov.tr/MevzuatMetin/1.5.5651.pdf (accessed 2026-11-20)
- [S4] Regulation on Internet Mass-Use Providers, OG 11.04.2017/30035: https://www.resmigazete.gov.tr/eskiler/2017/04/20170411-3.htm (accessed 2026-11-20)
- [S5] BTK, "IP Log İmzalayıcı" (also footer contact data): https://www.btk.gov.tr/ip-log-imzalayici ; hosting list page: https://www.btk.gov.tr/yer-saglayici-listesi (accessed 2026-11-20)
- [S6] e-Devlet, BTK "Yer Sağlayıcılığı Bildirimi": https://www.turkiye.gov.tr/btk-yer-saglayiciligi-bildirimi-4322 ; BTK service list: https://www.turkiye.gov.tr/bilgi-teknolojileri-ve-iletisim-kurumu (accessed 2026-11-20)
- [S7] Activity Certificate Regulation, OG 24.10.2007/26680: https://www.resmigazete.gov.tr/eskiler/2007/10/20071024-12.htm (accessed 2026-11-20)
- [S8] Secondary: R10.net forum post, 21.05.2021: https://www.r10.net/bilisim-hukuku/2825326-btk-yer-saglayici-listesi-yer-saglayici-bildirimi.html (accessed 2026-11-20)
- [S9] Cybersecurity Presidency, "SOME İletişim Platformu (SİP) Başvuru Kılavuzu", v1.0, 20.05.2026: https://cdn.siberguvenlik.gov.tr/dokuman/26/06/260618100351_S%C4%B0P%20(SOME%20%C4%B0leti%C5%9Fim%20Platformu)%20Ba%C5%9Fvuru%20K%C4%B1lavuzu.pdf (accessed 2026-11-20)
- [S10] USOM notice page: https://www.usom.gov.tr/ (accessed 2026-11-20)
- [S11] Cybersecurity Presidency, Information and Communication Security FAQ v1.1, 02.07.2026: https://cdn.siberguvenlik.gov.tr/dokuman/26/07/260702174807_Bilgi%20ve%20%C4%B0leti%C5%9Fim%20G%C3%BCvenli%C4%9Fi%20S%C4%B1k%C3%A7a%20Sorulan%20Sorular%20Dok%C3%BCman%C4%B1.pdf (accessed 2026-11-11, prior study)
- [S12] Secondary consolidated text, Network and Information Security Regulation (Lexpera): https://www.lexpera.com.tr/mevzuat/yonetmelikler/elektronik-haberlesme-sektorunde-sebeke-ve-bilgi-guvenligi-yonetmeligi (accessed 2026-11-20)
- [S13] Law No. 5809, consolidated: https://www.mevzuat.gov.tr/MevzuatMetin/1.5.5809.pdf (accessed 2026-11-20)

---

## Türkçe

# BTK / Siber Güvenlik Başkanlığı Pratik Dokümantasyon Rehberi

> Nötr şablondur, hukuki görüş değildir. Aşağıdaki portal adresleri 2026-11-20'de kontrol edildi; bazıları o gün bakımdaydı ya da erişilemedi. Her başvurudan önce yeniden kontrol edin. Doğrulanamayanlar **DOĞRULANMADI / UNVERIFIED** olarak işaretlidir.

## 1. Kim ne yapar (2026-11-20 itibarıyla)

| Kurum | Şirketleri ilgilendiren rolü | Dayanak |
|---|---|---|
| **Siber Güvenlik Başkanlığı** (SGB) | 31.07.2026'dan beri 5651'in yetkili kurumu (cezalar, içerik çıkarma/erişim engelleme kararları, yer sağlayıcı işleri); 7545 kapsamındaki yetkili kurum; 5809 md. 60/A acil tedbirleri; USOM işlevlerini devraldı | 7590 md. 21, 26, 27 [S1]; 7545 [S2] |
| **BTK** | 5809 kapsamında işletmeci yetkilendirmesi ve sektör düzenlemesi; bazı eski 5651 hizmetlerini hâlâ barındırıyor (e-Devlet yer sağlayıcılığı bildirimi, IP Log sayfası) | 5809; sayfalar 2026-11-20'de kontrol edildi [S5][S6] |
| **Mahalli mülki amir** (valilik / kaymakamlık) | **Ticari** toplu kullanım sağlayıcının izin belgesi ve denetimi | 5651 md. 7/1; 2017 Yön. md. 6, 10, 13 [S3][S4] |
| **Erişim Sağlayıcıları Birliği** (ESB) | İçerik çıkarma/engelleme kararlarını alır ve iletir; içerik/yer sağlayıcıya e-postayla bildirim yapabilir | 5651 md. 6/A [S3]; `https://www.esb.org.tr/` 2026-11-20'de erişilebilir |
| **Savcılık / mahkeme** | Yazılı bilgi talebi, 10 günde cevap yükümlülüğü | CMK md. 332 (bkz. [toplu-kullanim-saglayici.md](toplu-kullanim-saglayici.md) §5) |
| **KVK Kurumu** | Logları etkileyen kişisel veri ihlalleri | KVKK md. 12/5 (bkz. [../08-ihlal-yonetimi/](../08-ihlal-yonetimi/)) |

Geçiş hükmü: Siber Güvenlik Başkanlığı kendi ikincil düzenlemelerini çıkarana kadar mevcut düzenlemeler uygulanır ve BTK'ya yapılan atıflar Başkanlığa yapılmış sayılır (7590 ile 7545'e eklenen Geçici md. 2/1) [S1].

## 2. Formlar ve portallar

| İhtiyaç | Nerede | 2026-11-20 durumu | Belgeler / girdiler |
|---|---|---|---|
| Yer sağlayıcılığı bildirimi | e-Devlet: `https://www.turkiye.gov.tr/btk-yer-saglayiciligi-bildirimi-4322` (BTK hizmeti; açıklama: "5651 Sayılı Kanunun ilgili maddesi gereğince Yer Sağlayıcı Bildirimlerinin değerlendirilmesi.") [S6] | Hizmet sayfası erişilebilir; e-Devlet girişi gerekir | Giriş arkasındaki form alanları incelenmedi (**DOĞRULANMADI / UNVERIFIED**). Eski 2007 kuralı: Ek-5 dilekçe + Ek-6 form, asıllar bir hafta içinde (FB-Yön md. 9/2) [S7] |
| Yer sağlayıcı arayüzü | `https://yersaglayici.btk.gov.tr/` ve `https://yersaglayici.siberguvenlik.gov.tr/` | İkisi de "Sitemiz bakım aşamasındadır" gösterdi | İkincil (2021): barındırılan ve tescil edilen alan adlarının her ay CSV ile yüklenmesi (**DOĞRULANMADI / UNVERIFIED**) [S8] |
| Yer sağlayıcı listesi | `https://www.btk.gov.tr/yer-saglayici-listesi` | Sayfa erişilebilir; bağlantılı liste 404 verdi | - |
| Ticari toplu kullanım izin belgesi | Valilik bilgi işlem şube müdürlüğü / kaymakamlık bilgi işlem şefliği (2017 Yön. md. 13/1) [S4] | Fiziki usul | Dilekçe; önce işyeri açma ve çalışma ruhsatı (md. 6/1); sorumlu müdür bildirimi (md. 8/1); izin belgesi Ek-1 formunda, 15 gün içinde (md. 6/2-3) [S4] |
| SİP'e (SOME İletişim Platformu) SOME kaydı | Siber Güvenlik Başkanlığı; Ek-1 "SOME İletişim Bilgileri Formu" resmî yazıyla aşağıdaki adrese veya KEP'e [S9] | Kılavuz v1.0, 20.05.2026 | Yalnız kuruluşların SOME birimleri, bireysel başvuru yok; kurumsal e-posta (kişiye ait olmayan); en az bir yönetici kullanıcı; iki faktörlü giriş (varsayılan SMS) [S9] |
| Zararlı bağlantı listeleri, güvenlik bildirimleri, CVE başvuruları, siber ihbar (eski USOM) | `https://www.siberguvenlik.gov.tr/` | `usom.gov.tr` bu hizmetlerin siberguvenlik.gov.tr üzerinden süreceğini duyuruyor; `.txt` liste paylaşımı **1 Haziran 2026**'da sona erdi, API öneriliyor [S10] | Engelleme listeleri için API entegrasyonu |
| BTK e-Başvuru | 2026-11-20'de bulunamadı (`ebasvuru.btk.gov.tr` çözülmedi) | **DOĞRULANMADI / UNVERIFIED** | - |
| IP Log İmzalayıcı (BTK imzalama yazılımı) | `https://www.btk.gov.tr/ip-log-imzalayici` | Sayfa erişilebilir: 2017 Yönetmeliğinden beri destek verilmiyor [S5] | Planlamada kullanılmaz |

## 3. Uyum dosyası: saklanacak belgeler

Her rol için kontrollü bir klasör tutulur. Asgari içerik (öneri):

| Rol | Belge | Neden |
|---|---|---|
| Tümü | Rol değerlendirme notu (hangi 5651 rolleri, neden, tarih, onaylayan) | Diğer tüm kararların arkasındaki analizi gösterir |
| Tümü | Yayımlanmış tanıtıcı bilgiler (ekran görüntüsü + tarih) | 5651 md. 3/1; UE-Yön md. 5 |
| Tümü | Hukuki bildirim e-posta kutusu, nöbet listesi, içerik kaldırma runbook'u | 4 saat (md. 8, 8/A) ve 2 saat (5809 md. 60/A) süreleri |
| Tümü | Merci talepleri ve kararları defteri (alınış tarih-saati, gönderen, kapsam, işlem, saat, cevap veren, dosya hash'i) | Uyum kanıtı; KVKK md. 28/2-a orantılılık |
| Yer sağlayıcı | Bildirim alındısı / numarası; yenileme veya değişiklik bildirimleri | 5651 md. 5/6 bildirim yapmama cezası |
| Yer sağlayıcı | Trafik logu tanımı ve saklama ayarı (1-2 yıl), bütünlük yöntemi | 5651 md. 5/3 |
| Toplu kullanım | Ağ şeması (DHCP, NAT, oturum/RADIUS, filtre), log alan listesi, 2 yıllık saklama kanıtı, filtre yapılandırması | 2017 Yön. md. 3/1-e, 4 |
| Toplu kullanım (kamuya açık alan) | SMS tanımlama akışı, girişten önce gösterilen aydınlatma metni | Yön. md. 4/1-c; KVKK md. 10 |
| Ticari toplu kullanım | İzin belgesi, işyeri ruhsatı, sorumlu müdür bildirimi, sabit IP ve değişiklik bildirimleri, günlük bütünlük değeri kayıtları, kamera saklama (90 gün) | Yön. md. 5, 6, 8, 9 |
| Bilişim sistemi kullanan herkes | Siber Güvenlik Başkanlığına siber olay ve zafiyet bildirim prosedürü | 7545 md. 7/1-b |

## 4. 5651 dışındaki siber güvenlik yükümlülükleri

### 4.1 7545 sayılı Siber Güvenlik Kanunu: geniş kapsamlı

- Kapsam, md. 2/1: "Bu Kanun, siber uzayda varlık gösteren, faaliyet yürüten, hizmet sunan kamu kurum ve kuruluşları, kamu kurumu niteliğinde meslek kuruluşları, gerçek ve tüzel kişiler ile tüzel kişiliği bulunmayan kuruluşları kapsar." [S2]
- Md. 7/1: bilişim sistemleri kullanarak hizmet sunan, veri toplayan, işleyen ve benzeri faaliyet yürütenler (a) Başkanlığın talep ettiği veri, bilgi, belge, donanım, yazılımı öncelikle ve zamanında iletir; (b) "Siber güvenliğe yönelik olarak milli güvenlik, kamu düzeni veya kamu hizmetinin gereği gibi yürütülmesi amacıyla mevzuatın öngördüğü tedbirleri almak, hizmet sundukları alanda tespit ettikleri zafiyet veya siber olayları gecikmeksizin Başkanlığa bildirmek."; (c) kamu kurumları ve **kritik altyapılarda** kullanılacak siber güvenlik ürünlerini Başkanlıkça yetkilendirilmiş kişilerden tedarik eder; (ç) belgelendirmeye tabi siber güvenlik şirketleri faaliyete başlamadan Başkanlık onayı alır; (d) Başkanlığın politika, strateji ve düzenleyici işlemlerini uygular [S2].
- Md. 16/10: md. 7/1 (a), (b), (c) ihlalinde **1.000.000-10.000.000 TL** idari para cezası ((a) bendi 7590 ile eklendi) [S2]. Md. 16/1: yetkili mercilerin istediği bilgi ve belgeyi vermemek: 1-3 yıl hapis ve adli para cezası. Md. 17/1: cezadan önce savunma alınır, 30 gün süre [S2].
- Geçici md. 1/6: uygulama düzenlemeleri bir yıl içinde (yaklaşık 19.03.2026'ya kadar) yürürlüğe konulur; o zamana kadar mevcut düzenlemelerin Kanuna aykırı olmayan hükümleri uygulanır [S2]. Hangi uygulama düzenlemelerinin yayımlandığı ve saatle tanımlı bir bildirim süresi getirip getirmediği **DOĞRULANMADI / UNVERIFIED**.

Sıradan bir şirket için pratik okuma (yorum): en olası uygulanacak hüküm md. 7/1-b'dir. Olay müdahale planına KVKK ihlal bildiriminin ("en kısa sürede", KVKK md. 12/5; Kurulun 2019/10 kararı 72 saat öngörür, bkz. [../08-ihlal-yonetimi/](../08-ihlal-yonetimi/)) yanına "Siber Güvenlik Başkanlığına gecikmeksizin bildirim" dalı eklenmelidir.

### 4.2 2019/12 sayılı Cumhurbaşkanlığı Genelgesi ve Bilgi ve İletişim Güvenliği Rehberi

Siber Güvenlik Başkanlığı SSS'sine (sürüm 1.1, 02.07.2026) göre Genelge "Kritik altyapı işleten özel hukuk tüzel kişiler hariç olmak üzere, diğer özel hukuk tüzel kişileri kapsamamakla beraber genelgede yer alan tedbirlerin uygulanması bu kurumların yararına olacaktır" (11.11.2026 çalışmasının bulgusu; 2026-11-20'de yeniden indirilmedi) [S11].

### 4.3 Sektör yönetmeliği: "Elektronik Haberleşme Sektörüne İlişkin Siber Güvenlik Yönetmeliği"

- **Tam olarak bu adı taşıyan** bir yönetmelik 2026-11-20'de Resmî Gazete, mevzuat.gov.tr ve BTK aramalarında bulunamadı (var olduğu **DOĞRULANMADI / UNVERIFIED**).
- En yakın düzenleme BTK'nın **Elektronik Haberleşme Sektöründe Şebeke ve Bilgi Güvenliği Yönetmeliği**dir (RG 13.07.2014/29059). Md. 1/1: "Bu Yönetmeliğin amacı, şebeke ve bilgi güvenliğinin sağlanmasına yönelik olarak işletmecilerin uyacakları usul ve esasları düzenlemektir." Md. 3/1-ı işletmeciyi yetkilendirme çerçevesinde elektronik haberleşme hizmeti sunan ve/veya şebekesi sağlayan ve altyapısını işleten şirket olarak tanımlar; md. 35 işletmecilerin SOME kurmasını ve DoS/DDoS'a karşı USOM koordinasyonunda tedbir almasını, md. 38 abonelerin %5'inden fazlasını veya iş sürekliliğini etkileyen ihlallerin Kuruma bildirilmesini ister. Kişisel verilerin işlenmesi kapsam dışıdır (md. 1/2) [S12] (ikincil konsolide kopya; Resmî Gazete aslı indirilemedi: birincil metinden **DOĞRULANMADI / UNVERIFIED**).
- **Kime uygulanır:** yalnız 5809 kapsamında yetkilendirilmiş elektronik haberleşme işletmecilerine. 5809 kapsamında yetkilendirilmemiş sıradan şirket, hotspot sunan mekân, SaaS ya da hosting müşterisi "işletmeci" değildir ve doğrudan bağlı değildir. Yine de 7545'e (§4.1) ve 5651 rolleri için bu bölümdeki kurallara tabidir.
- 7590 sonrasında bu sektörel siber güvenlik kurallarındaki yetkinin, devredilen yetkiye göre BTK'da mı Siber Güvenlik Başkanlığında mı kaldığı burada çözülmedi (**DOĞRULANMADI / UNVERIFIED**).

## 5. İletişim noktaları (aksi belirtilmedikçe 2026-11-20'de doğrulandı)

| Kurum | İletişim | Kaynak |
|---|---|---|
| Siber Güvenlik Başkanlığı | Adres: T.C. Cumhurbaşkanlığı Çankaya Yerleşkesi Ziaur Rahman Cad. Çankaya / ANKARA; KEP: `siberguvenlikbaskanligi@hs01.kep.tr`; SİP desteği: `sip@siberguvenlik.gov.tr`; web: `https://www.siberguvenlik.gov.tr/` | SİP kılavuzu [S9] |
| BTK | Eskişehir Yolu 10.Km No:276 06530 Çankaya ANKARA; telefon +90 (0312) 412 20 00; tüketici hattı 120 | BTK sitesi alt bilgisi [S5] |
| ESB | `https://www.esb.org.tr/` | 2026-11-20'de erişilebilir |
| USOM (eski) | `https://www.usom.gov.tr/` artık siberguvenlik.gov.tr'ye yönlendiren duyuru sayfası | [S10] |

## 6. Kaynaklar

- [S1] 7590 sayılı Kanun, RG 31.07.2026/33326: https://www.resmigazete.gov.tr/eskiler/2026/07/20260731-2.htm (erişim 2026-11-20)
- [S2] 7545 sayılı Siber Güvenlik Kanunu, konsolide (7590 işlenmiş): https://www.mevzuat.gov.tr/MevzuatMetin/1.5.7545.pdf ; asıl RG 19.03.2025/32846: https://www.resmigazete.gov.tr/eskiler/2025/03/20250319-1.htm (erişim 2026-11-20)
- [S3] 5651 sayılı Kanun, konsolide: https://www.mevzuat.gov.tr/MevzuatMetin/1.5.5651.pdf (erişim 2026-11-20)
- [S4] İnternet Toplu Kullanım Sağlayıcıları Hakkında Yönetmelik, RG 11.04.2017/30035: https://www.resmigazete.gov.tr/eskiler/2017/04/20170411-3.htm (erişim 2026-11-20)
- [S5] BTK, "IP Log İmzalayıcı" (alt bilgideki iletişim verisi dahil): https://www.btk.gov.tr/ip-log-imzalayici ; yer sağlayıcı listesi sayfası: https://www.btk.gov.tr/yer-saglayici-listesi (erişim 2026-11-20)
- [S6] e-Devlet, BTK "Yer Sağlayıcılığı Bildirimi": https://www.turkiye.gov.tr/btk-yer-saglayiciligi-bildirimi-4322 ; BTK hizmet listesi: https://www.turkiye.gov.tr/bilgi-teknolojileri-ve-iletisim-kurumu (erişim 2026-11-20)
- [S7] Faaliyet Belgesi Yönetmeliği, RG 24.10.2007/26680: https://www.resmigazete.gov.tr/eskiler/2007/10/20071024-12.htm (erişim 2026-11-20)
- [S8] İkincil: R10.net forum iletisi, 21.05.2021: https://www.r10.net/bilisim-hukuku/2825326-btk-yer-saglayici-listesi-yer-saglayici-bildirimi.html (erişim 2026-11-20)
- [S9] Siber Güvenlik Başkanlığı, "SOME İletişim Platformu (SİP) Başvuru Kılavuzu", sürüm 1.0, 20.05.2026: https://cdn.siberguvenlik.gov.tr/dokuman/26/06/260618100351_S%C4%B0P%20(SOME%20%C4%B0leti%C5%9Fim%20Platformu)%20Ba%C5%9Fvuru%20K%C4%B1lavuzu.pdf (erişim 2026-11-20)
- [S10] USOM duyuru sayfası: https://www.usom.gov.tr/ (erişim 2026-11-20)
- [S11] Siber Güvenlik Başkanlığı, Bilgi ve İletişim Güvenliği SSS sürüm 1.1, 02.07.2026: https://cdn.siberguvenlik.gov.tr/dokuman/26/07/260702174807_Bilgi%20ve%20%C4%B0leti%C5%9Fim%20G%C3%BCvenli%C4%9Fi%20S%C4%B1k%C3%A7a%20Sorulan%20Sorular%20Dok%C3%BCman%C4%B1.pdf (erişim 2026-11-11, önceki çalışma)
- [S12] İkincil: Şebeke ve Bilgi Güvenliği Yönetmeliği konsolide metni (Lexpera): https://www.lexpera.com.tr/mevzuat/yonetmelikler/elektronik-haberlesme-sektorunde-sebeke-ve-bilgi-guvenligi-yonetmeligi (erişim 2026-11-20)
- [S13] 5809 sayılı Kanun, konsolide: https://www.mevzuat.gov.tr/MevzuatMetin/1.5.5809.pdf (erişim 2026-11-20)
