---
Doküman / Document: Toplu Kullanım Sağlayıcı Yükümlülükleri / Mass-Use Provider Obligations
Bölüm / Section: 13-btk-5651
Sahip / Owner: Bilgi Güvenliği Yöneticisi + Hukuk / Information Security Manager + Legal
Onaylayan / Approved by: KVKK Komitesi / KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-11-20
Gözden Geçirme / Review: Altı aylık + tetiklenmiş (Siber Güvenlik Başkanlığının yeni toplu kullanım yönetmeliği, ağ mimarisi değişikliği, Wi-Fi'ın ücretlendirilmesi) / Semi-annual + triggered (new mass-use regulation by the Cybersecurity Presidency, network architecture change, Wi-Fi becoming a paid service)
İlgili Mevzuat / Legal Reference: 5651 sayılı Kanun md. 2/1-i, 7 (7590 işlenmiş) / Law No. 5651 Arts. 2/1-i, 7 (incl. Law 7590); İnternet Toplu Kullanım Sağlayıcıları Hakkında Yönetmelik (RG 11.04.2017/30035); 5070 sayılı Elektronik İmza Kanunu md. 3/h / Electronic Signature Law No. 5070 Art. 3/h; 5326 sayılı Kabahatler Kanunu md. 17/7 / Misdemeanours Law No. 5326 Art. 17/7; 5271 sayılı CMK md. 332 / Code of Criminal Procedure Art. 332; 6698 sayılı KVKK md. 4, 5, 7, 10, 12, 28 / KVKK Arts. 4, 5, 7, 10, 12, 28
---

## English

# Mass-Use Provider (Toplu Kullanım Sağlayıcı) Obligations

> Neutral template, not legal advice. Reuses the verified findings of a 2026-11-11 study of 5651 for a Wi-Fi hotspot; every quoted provision was re-checked against the primary text on 2026-11-20 unless marked otherwise. Unconfirmed items are marked **DOĞRULANMADI / UNVERIFIED**.

## 1. Who is a mass-use provider?

- 5651 Art. 2/1-i: "*Toplu kullanım sağlayıcı: Kişilere belli bir yerde ve belli bir süre internet ortamı kullanım olanağı sağlayanı*" (whoever gives persons the possibility to use the internet at a certain place for a certain time) [S1].
- 2017 Regulation Art. 3/1-g repeats this for "natural and legal persons" [S2].
- **Commercial sub-type**, Regulation Art. 3/1-l: providers in "internet salons and similar places open to the public" offering mass-use service "**for a certain fee**", or also letting people play games on computers [S2].

| Typical setup | Classification (interpretation) |
|---|---|
| Internet café, gaming salon charging for use | Commercial mass-use provider |
| Hotel, café, restaurant, co-working, incubator, office giving guest/tenant/staff Wi-Fi without a separate fee | Non-commercial mass-use provider |
| Wi-Fi billed as a separate line item to the public | Re-assess: may become commercial |

Whether the "commercial purpose" criterion applies to hotels, co-working spaces or incubators: no court decision or official opinion found (**DOĞRULANMADI / UNVERIFIED**). Whether a network used **only** by a company's own employees makes it a mass-use provider: commonly assumed in practice, not confirmed by a primary source (**DOĞRULANMADI / UNVERIFIED**). The 2017 Regulation defines an access provider as the operator serving mass-use providers and subscribers (Art. 3/1-ç), so a building or office network is a customer of the ISP, not an access provider itself (interpretation) [S2].

## 2. Obligations of all mass-use providers (5651 Art. 7/2 + Regulation Art. 4)

5651 Art. 7/2: "*Regardless of commercial purpose, all internet mass-use providers are obliged to take the measures set by regulation on blocking access to criminal content and keeping access records relating to use*" [S1].

Regulation Art. 4/1 [S2]:

| | Obligation |
|---|---|
| (a) | Use a **content filtering system** to prevent access to criminal content |
| (b) | Record **access records** electronically in their own systems and keep them **two years** |
| (c) | Those offering internet in **public areas** set up systems that identify users by **SMS and similar methods** |

Art. 4/2: they may additionally use a "safe internet service" (optional) [S2].

### 2.1 The log set (erişim kayıtları)

Regulation Art. 3/1-e defines access records as: internal IP addresses distributed in their own network; start and end time of use; MAC address of the device using that IP; **destination IP address**; and, where one or more IPs are shared to users via ports (NAT/PAT), the **real IP and port** assigned to the user [S2].

| Record in a typical stack | Maps to | Status |
|---|---|---|
| DHCP leases + RADIUS/portal session accounting | Internal IP, MAC, start/end | Required core |
| NAT log: internal IP:port to public IP:port, time | "real IP and port assigned to the user" | Required |
| NAT/flow: destination IP | "destination IP address" | Treat as required (safest reading; sentence structure is ambiguous) |
| Destination port, protocol | Not in the definition | Beyond the text; may come with a future regulation (the law's traffic-data definition gained "source and destination port" in 2026) |
| Per-user DNS queries | Not in any provision for mass-use providers | Not required by 5651; needs its own KVKK basis |
| URLs, HTTP headers | Not in any provision for mass-use providers | Not required; avoid |
| Name, national ID (TCKN) | Not in the access-record definition | Not required as a log field |

Scope of "destination IP address" (every connection vs. NAT entry only): no official interpretation found (**DOĞRULANMADI / UNVERIFIED**).

Why ports matter: when all users exit through one public IP, a prosecutor's request gives public IP + source port + time. Chain: NAT log gives internal IP, DHCP gives MAC, session log gives the account. Without ports, users behind the same IP cannot be told apart.

### 2.2 Retention

Exactly **two years** (Art. 4/1-b) [S2]. A BTK page from 15.12.2017 still quotes the old text with "one year" [S5]; the Official Gazette text says two years and prevails. 730 days matches two years; 731 days covers leap years. Whether the 2017 Regulation was amended after 2017: no amendment found in the Official Gazette or a secondary consolidated copy [S6]; mevzuat.gov.tr consolidated copy not reached (**DOĞRULANMADI / UNVERIFIED** that no amendment exists).

### 2.3 Hash and time stamp

- The daily integrity value ("value confirming the accuracy, integrity and confidentiality", recorded daily, kept two years) is written **only for commercial** providers, Art. 5/1-e [S2]. Art. 4 has no equivalent. The words "hash" and "time stamp" do not appear in the 2017 Regulation (full-text check in the 2026-11-11 study, re-confirmed 2026-11-20).
- BTK's "IP Log İmzalayıcı" software is no longer required or supported: the phrase "with the software given by the Presidency" was removed in 2017 and BTK says it gives no support for it [S5] (page checked 2026-11-20).
- Under Law 5070 Art. 3/h a legal time stamp is one verified by an electronic certificate service provider (ESHS) with an electronic signature [S7]. A self-made SHA-256 chain is an integrity value, not a legal time stamp.

Template position: for non-commercial providers, daily hashing plus an RFC 3161 time stamp from an ESHS is **above the legal minimum** but strengthens evidential value. For commercial providers, a daily integrity value is mandatory; the method is technology-neutral since 2017.

### 2.4 Content filtering

Mandatory for all mass-use providers (Art. 4/1-a). Definition, Art. 3/1-d: software and hardware blocking access by web address, domain, IP address, keyword and similar criteria [S2]. A DNS-based filter (e.g. RPZ) fits the definition (interpretation). No official list of categories or minimum technical criterion found (**DOĞRULANMADI / UNVERIFIED**). Per-user logs of blocked attempts are not required; aggregate counters are enough and are more KVKK-friendly.

### 2.5 User identification

Only for providers giving access in **public areas**, by "SMS and similar methods" (Art. 4/1-c) [S2]. The text does **not** require name or national ID number. Phone + SMS one-time code satisfies the text. The meaning of "public area" (e.g. tenant-only network vs. guest network) and of "similar methods" has no official explanation (**DOĞRULANMADI / UNVERIFIED**). Collecting TCKN is not a 5651 duty and needs a separate KVKK proportionality analysis.

## 3. Additional obligations of commercial providers (Regulation Art. 5, 6, 8, 9)

| Provision | Obligation [S2] |
|---|---|
| Art. 5/1-a; 5651 Art. 7/1 | **Permit** (*izin belgesi*) from the local civil administrator (governor / district governor) |
| Art. 5/1-b, c | Content filtering **and** safe internet service; keep the filter active and up to date |
| Art. 5/1-ç | Get a **static IP** from the access provider; report static IP changes within 15 days |
| Art. 5/1-d, e | Keep access records 2 years; record daily the integrity value and keep it 2 years |
| Art. 5/1-f | Report closure or transfer within 15 days and return the permit |
| Art. 6 | Apply by petition to the civil administration **after** obtaining the workplace opening and operating licence; decision within 15 days; permit form in Annex-1 |
| Art. 7 | Premises opened without permit are sealed and closed |
| Art. 8 | Legal-person holders appoint a responsible manager; annual information training |
| Art. 9 | Premises rules: under-12s only with a guardian; under-15s not after 20.00 without a guardian; no tobacco, no alcohol; copyright measures; no harmful games; high-resolution (min. 3 MP) IR camera at entrances, recordings kept **90 days** and given only to competent authorities |
| Art. 13/2 | Civil administrator reports permit information to the authority within 30 days (now the Cybersecurity Presidency, 5651 Art. 7/1 as amended by 7590) [S1] |

## 4. Supervision and fines

- Supervision of **commercial** providers: inspection commission of the civil administration (Art. 10) [S2].
- 5651 Art. 7/4: for commercial providers that breach Art. 7 duties, the local civil administrator may impose a warning, an administrative fine of **1,000 to 15,000 TL**, or suspension of commercial activity for up to three days [S1].
- Regulation Art. 11/1: first breach written warning; continued breach closure up to three days; repeated breach fine 1,000-15,000 TL. Art. 11/2: breaches of Art. 9 are fined under Police Duties Law 2559 Art. 6/1-d. Art. 11/3: Law 5326 applies [S2].
- **Non-commercial** providers: neither 5651 nor the Regulation contains a specific sanction for breaching Art. 4 (Art. 7/4 and Reg. Art. 11 refer to commercial providers only) [S1][S2]. Whether a general provision (e.g. Law 5326 Art. 32) could be applied: **DOĞRULANMADI / UNVERIFIED**. The real risk is indirect: if a crime is committed from the network and the user cannot be identified, the investigation focuses on the subscriber (the provider).
- 2026 value of the 1,000-15,000 TL band after yearly revaluation under Law 5326 Art. 17/7: no official table found (**DOĞRULANMADI / UNVERIFIED**). The 2026-11-11 study's estimate (about 19,800-298,000 TL) was based on revaluation rates partly from memory and is **not** reliable.

## 5. Requests from authorities

General basis: CMK Art. 332/1: information requested **in writing** by the public prosecutor, judge or court during investigation or prosecution must be answered within **ten days**; if impossible, the reason and latest date are given within the same period (verbatim in Turkish section) [S8]. 5651 and the 2017 Regulation do not set a separate hand-over procedure for mass-use providers [S1][S2].

Recommended minimum procedure (not a legal requirement): accept only written requests via an official channel; one authorised responder; release only the records matching the requested time range and IP:port; keep a request register; hand over with a file hash and the day's integrity/time-stamp proof. Police requests without a prosecutor's instruction: limits not examined from primary text (**DOĞRULANMADI / UNVERIFIED**).

## 6. KVKK touchpoints

- Legal basis: KVKK Art. 5/2-a ("expressly provided for by laws") and 5/2-ç; no consent.
- Privacy notice before login (KVKK Art. 10), separate from any consent text.
- Retention exactly 2 years, then destruction (Arts. 4/2-d, 7).
- Extra data (DNS logs, URL logs, TCKN) are outside 5651; justify separately or do not collect.
- If a contractor runs the hotspot, it is usually the data processor; the venue that offers the service is the 5651 addressee and data controller (interpretation from the 2026-11-11 study).

## 7. Sources

- [S1] Law No. 5651, consolidated (incl. 7590): https://www.mevzuat.gov.tr/MevzuatMetin/1.5.5651.pdf (accessed 2026-11-20)
- [S2] Regulation on Internet Mass-Use Providers, OG 11.04.2017/30035: https://www.resmigazete.gov.tr/eskiler/2017/04/20170411-3.htm (accessed 2026-11-20)
- [S3] Law No. 7590, OG 31.07.2026/33326: https://www.resmigazete.gov.tr/eskiler/2026/07/20260731-2.htm (accessed 2026-11-20)
- [S4] Law No. 6698 (KVKK): https://www.mevzuat.gov.tr/MevzuatMetin/1.5.6698.pdf (accessed 2026-11-20)
- [S5] BTK, "IP Log İmzalayıcı": https://www.btk.gov.tr/ip-log-imzalayici (accessed 2026-11-20)
- [S6] Secondary consolidated copy of the 2017 Regulation (Lexpera): https://www.lexpera.com.tr/mevzuat/yonetmelikler/internet-toplu-kullanim-saglayicilari-hakkinda-yonetmelik-1 (accessed 2026-11-20)
- [S7] Law No. 5070: https://www.mevzuat.gov.tr/MevzuatMetin/1.5.5070.pdf (accessed 2026-11-11, prior study; not re-fetched)
- [S8] Law No. 5271 (CMK): https://www.mevzuat.gov.tr/MevzuatMetin/1.5.5271.pdf (accessed 2026-11-11, prior study; not re-fetched)
- [S9] Law No. 5326: https://www.mevzuat.gov.tr/MevzuatMetin/1.5.5326.pdf (accessed 2026-11-11, prior study; not re-fetched)

---

## Türkçe

# Toplu Kullanım Sağlayıcı Yükümlülükleri

> Nötr şablondur, hukuki görüş değildir. Bir Wi-Fi hotspot'u için 11.11.2026 tarihli 5651 çalışmasının doğrulanmış bulgularını kullanır; aksi belirtilmedikçe alıntılanan her hüküm 2026-11-20'de birincil metinden yeniden kontrol edildi. Doğrulanamayanlar **DOĞRULANMADI / UNVERIFIED** olarak işaretlidir.

## 1. Toplu kullanım sağlayıcı kimdir?

- 5651 md. 2/1-i: "Toplu kullanım sağlayıcı: Kişilere belli bir yerde ve belli bir süre internet ortamı kullanım olanağı sağlayanı," [S1].
- 2017 Yönetmeliği md. 3/1-g aynı tanımı "gerçek ve tüzel kişiler" için tekrarlar [S2].
- **Ticari alt tür**, Yönetmelik md. 3/1-l: "Ticari amaçla internet toplu kullanım sağlayıcı: İnternet salonu ve benzeri umuma açık yerlerde belirli bir ücret karşılığı internet toplu kullanım sağlayıcılığı hizmeti veren veya bununla beraber bilgisayarlarda bilgi ve beceri artırıcı veya zeka geliştirici nitelikteki oyunların oynatılmasına imkân sağlayan gerçek ve tüzel kişileri," [S2].

| Tipik kurulum | Sınıflandırma (yorum) |
|---|---|
| Kullanım için ücret alan internet kafe, oyun salonu | Ticari toplu kullanım sağlayıcı |
| Ayrı ücret almadan misafir/kiracı/çalışan Wi-Fi'ı veren otel, kafe, restoran, ortak ofis, kuluçka merkezi, ofis | Ticari olmayan toplu kullanım sağlayıcı |
| Wi-Fi'ın kamuya ayrı kalem olarak faturalanması | Yeniden değerlendirilir: ticari sayılabilir |

"Ticari amaç" ölçütünün otel, ortak ofis veya kuluçka merkezine uygulanmasına dair yargı kararı ya da resmî görüş bulunamadı (**DOĞRULANMADI / UNVERIFIED**). **Yalnız** şirketin kendi çalışanlarının kullandığı ağın şirketi toplu kullanım sağlayıcı yapıp yapmadığı uygulamada genellikle kabul edilir, birincil kaynakla doğrulanmadı (**DOĞRULANMADI / UNVERIFIED**). 2017 Yönetmeliği erişim sağlayıcıyı "İnternet toplu kullanım sağlayıcılarına ve abone olan kullanıcılarına internet ortamına erişim olanağı sağlayan işletmeciler ile gerçek veya tüzel kişileri," diye tanımlar (md. 3/1-ç); bina veya ofis ağı erişim sağlayıcı değil, İSS'nin müşterisidir (yorum) [S2].

## 2. Bütün toplu kullanım sağlayıcıların yükümlülükleri (5651 md. 7/2 + Yönetmelik md. 4)

5651 md. 7/2: "Ticari amaçla olup olmadığına bakılmaksızın bütün internet toplu kullanım sağlayıcılar, konusu suç oluşturan içeriklere erişimin engellenmesi ve kullanıma ilişkin erişim kayıtlarının tutulması hususlarında yönetmelikle belirlenen tedbirleri almakla yükümlüdür." [S1]

Yönetmelik md. 4/1 [S2]: "İnternet toplu kullanım sağlayıcılarının yükümlülükleri şunlardır: a) Konusu suç oluşturan içeriklere erişimi önleyici tedbirleri almak amacıyla içerik filtreleme sistemini kullanmak. b) Erişim kayıtlarını elektronik ortamda kendi sistemlerine kaydetmek ve iki yıl süre ile saklamak. c) Kamuya açık alanlarda internet erişimi sağlayan toplu kullanım sağlayıcılar, kısa mesaj servisi (sms) ve benzeri yöntemlerle kullanıcıları tanımlayacak sistemleri kurmak."

Md. 4/2: ek tedbir olarak güvenli internet hizmeti de alınabilir (ihtiyari) [S2].

### 2.1 Log seti (erişim kayıtları)

Yönetmelik md. 3/1-e: "Erişim kayıtları: Kendi iç ağlarında dağıtılan IP adres bilgilerini, kullanıma başlama ve bitiş zamanını ve bu IP adreslerini kullanan bilgisayarların tekil ağ cihaz numarasını (MAC adresi) gösteren bilgileri, hedef IP adresi, bir veya birden fazla IP adresinin portlar aracılığı ile kullanıcılara paylaştırılması yöntemi ile sunulan internet erişim hizmetinde kullanıcıya tahsis edilen gerçek IP ve port bilgilerini," [S2].

| Tipik sistemdeki kayıt | Karşılığı | Durum |
|---|---|---|
| DHCP kiraları + RADIUS/portal oturum kaydı | İç IP, MAC, başlangıç/bitiş | Zorunlu çekirdek |
| NAT kaydı: iç IP:port, dış IP:port, zaman | "kullanıcıya tahsis edilen gerçek IP ve port" | Zorunlu |
| NAT/akış: hedef IP | "hedef IP adresi" | Zorunlu sayılır (en güvenli okuma; cümle yapısı belirsiz) |
| Hedef port, protokol | Tanımda yok | Metnin ötesinde; ileride yönetmelikle gelebilir (kanundaki trafik bilgisi tanımına 2026'da "kaynak ve hedef" port eklendi) |
| Kullanıcı bazında DNS sorguları | Toplu kullanım için hiçbir hükümde yok | 5651 gereği değil; ayrı KVKK dayanağı gerekir |
| URL, HTTP başlıkları | Toplu kullanım için hiçbir hükümde yok | Gerekmez; tutulmamalı |
| Ad-soyad, T.C. kimlik no | Erişim kaydı tanımında yok | Log alanı olarak zorunlu değil |

"Hedef IP adresi"nin kapsamı (her bağlantı mı, yalnız NAT kaydı mı): resmî yorum bulunamadı (**DOĞRULANMADI / UNVERIFIED**).

Port neden önemli: tüm kullanıcılar tek genel IP'den çıkıyorsa savcılık yazısı genel IP + kaynak port + zaman verir. Zincir: NAT kaydı iç IP'yi, DHCP MAC'i, oturum kaydı hesabı bulur. Port yoksa aynı IP arkasındaki kullanıcılar ayırt edilemez.

### 2.2 Saklama süresi

Tam **iki yıl** (md. 4/1-b) [S2]. BTK'nın 15.12.2017 tarihli sayfası eski metni "bir yıl" diye alıntılamaya devam ediyor [S5]; Resmî Gazete metni iki yıl der ve esas alınır. 730 gün iki yıla denk gelir; 731 gün artık yılı da karşılar. 2017 Yönetmeliğinin sonradan değişip değişmediği: Resmî Gazete'de ve ikincil konsolide kopyada değişiklik bulunamadı [S6]; mevzuat.gov.tr konsolide metnine ulaşılamadı (değişiklik olmadığı **DOĞRULANMADI / UNVERIFIED**).

### 2.3 Hash ve zaman damgası

- Günlük bütünlük değeri yalnız **ticari** sağlayıcıya yazılmıştır, md. 5/1-e: "(d) bendi gereğince kaydedilen bilgileri ve bu bilgilerin doğruluğunu, bütünlüğünü ve gizliliğini teyit eden değeri kendi sistemlerine günlük olarak kaydetmek ve bu verileri iki yıl süre ile saklamak," [S2]. Md. 4'te karşılığı yoktur. 2017 Yönetmeliğinde "hash" ve "zaman damgası" sözcükleri geçmez (11.11.2026 çalışmasındaki tam metin taraması, 2026-11-20'de teyit edildi).
- BTK'nın "IP Log İmzalayıcı" yazılımı artık zorunlu değil ve desteklenmiyor: "Başkanlık tarafından verilen yazılım ile," ibaresi 2017'de çıkarıldı; BTK sayfası "sözkonusu yazılım (IP log imzalayıcı) ile ilgili soru ve sorunlara destek verilmemektedir" der [S5] (2026-11-20 kontrolü).
- 5070 md. 3/h: "Zaman damgası: Bir elektronik verinin, üretildiği, değiştirildiği, gönderildiği, alındığı ve / veya kaydedildiği zamanın tespit edilmesi amacıyla, elektronik sertifika hizmet sağlayıcısı tarafından elektronik imzayla doğrulanan kaydı," [S7]. Kendi ürettiğiniz SHA-256 zinciri bütünlük değeridir, hukuki zaman damgası değildir.

Şablon duruşu: ticari olmayan sağlayıcı için günlük hash + ESHS'den RFC 3161 zaman damgası **yasal asgarinin üstündedir** ama delil değerini güçlendirir. Ticari sağlayıcı için günlük bütünlük değeri zorunludur; yöntem 2017'den beri teknolojiden bağımsızdır.

### 2.4 İçerik filtresi

Bütün toplu kullanım sağlayıcılar için zorunlu (md. 4/1-a). Tanım, md. 3/1-d: "Filtreleme sistemi: İnternet ortamında web adresi, alan adı, IP adresi, kelime ve benzeri kriterlere göre erişimi engelleyen yazılımları ve donanımları," [S2]. DNS tabanlı filtre (ör. RPZ) bu tanıma uyar (yorum). Resmî kategori listesi ya da asgari teknik ölçüt bulunamadı (**DOĞRULANMADI / UNVERIFIED**). Engellenen denemelerin kullanıcı bazında kaydı istenmez; toplu sayaç yeterlidir ve KVKK bakımından daha uygundur.

### 2.5 Kullanıcı tanımlama

Yalnız **kamuya açık alanlarda** erişim verenler için, "sms ve benzeri yöntemlerle" (md. 4/1-c) [S2]. Metin ad-soyad veya T.C. kimlik no **istemez**. Telefon + SMS tek kullanımlık kod metni karşılar. "Kamuya açık alan" (ör. yalnız kiracılara açık ağ ve misafir ağı) ile "benzeri yöntemler"in resmî açıklaması yoktur (**DOĞRULANMADI / UNVERIFIED**). TCKN toplamak 5651 yükümlülüğü değildir; ayrıca KVKK ölçülülük analizi gerekir.

## 3. Ticari sağlayıcının ek yükümlülükleri (Yönetmelik md. 5, 6, 8, 9)

| Hüküm | Yükümlülük [S2] |
|---|---|
| md. 5/1-a; 5651 md. 7/1 | Mülki idare amirinden (vali / kaymakam) **izin belgesi** |
| md. 5/1-b, c | İçerik filtresi **ve** güvenli internet hizmeti; filtreyi aktif ve güncel tutmak |
| md. 5/1-ç | Erişim sağlayıcıdan **sabit IP** almak; değişikliği 15 gün içinde mülki idare amirliğine bildirmek |
| md. 5/1-d, e | Erişim kayıtlarını 2 yıl saklamak; bütünlük değerini günlük kaydedip 2 yıl saklamak |
| md. 5/1-f | Kapanma veya devri 15 gün içinde bildirmek, izin belgesini teslim etmek |
| md. 6 | İşyeri açma ve çalışma ruhsatı **alındıktan sonra** mülki idare amirliğine dilekçeyle başvuru; 15 gün içinde sonuç; izin belgesi Ek-1 |
| md. 7 | İzinsiz açılan işyeri tutanakla mühürlenip kapatılır |
| md. 8 | Tüzel kişi izin sahibi sorumlu müdür görevlendirir; yılda en az bir bilgilendirme eğitimi |
| md. 9 | İşyeri kuralları: 12 yaş altı yalnız veli/vasiyle; 15 yaş altı veli/vasisiz 20.00'den sonra alınmaz; tütün ve alkol yok; fikrî hak tedbirleri; zararlı oyun yok; girişlerde en az 3 megapiksel, gece görüşlü kamera, kayıtlar **doksan gün** saklanır ve yetkili makamlar dışında kimseye verilemez |
| md. 13/2 | Mülki idare amiri izin bilgilerini 30 gün içinde Kuruma bildirir (7590 sonrası 5651 md. 7/1'e göre Başkanlığa, yani Siber Güvenlik Başkanlığına) [S1] |

## 4. Denetim ve cezalar

- **Ticari** sağlayıcının denetimi: mülki idare amirliği denetleme komisyonu (md. 10) [S2].
- 5651 md. 7/4: "Bu maddede belirtilen yükümlülükleri ihlal eden ticari amaçla toplu kullanım sağlayıcılarına, ihlalin ağırlığına göre yönetmelikle belirlenecek usul ve esaslar çerçevesinde uyarma, bin Türk Lirasından on beş bin Türk Lirasına kadar idari para cezası verme veya üç güne kadar ticari faaliyetlerini durdurma müeyyidelerinden birine karar vermeye mahalli mülki amir yetkilidir." [S1]
- Yönetmelik md. 11/1: ilk ihlalde yazılı uyarma; devamında üç güne kadar kapatma; tekrarında 1.000-15.000 TL idari para cezası. Md. 11/2: md. 9 aykırılığında 2559 sayılı PVSK md. 6/1-d uyarınca ceza. Md. 11/3: 5326 sayılı Kanun uygulanır [S2].
- **Ticari olmayan** sağlayıcı: md. 4 ihlali için ne 5651'de ne Yönetmelikte özel yaptırım vardır (md. 7/4 ve Yön. md. 11 yalnız ticari olana atıf yapar) [S1][S2]. Genel bir hükmün (ör. 5326 md. 32) uygulanıp uygulanamayacağı **DOĞRULANMADI / UNVERIFIED**. Asıl risk dolaylıdır: ağdan işlenen bir suçta kullanıcı tespit edilemezse soruşturma abone olan sağlayıcıda yoğunlaşır.
- 1.000-15.000 TL bandının 5326 md. 17/7 uyarınca yeniden değerlenmiş 2026 tutarı: resmî tablo bulunamadı (**DOĞRULANMADI / UNVERIFIED**). 11.11.2026 çalışmasındaki tahmin (yaklaşık 19.800-298.000 TL) kısmen hafızadan alınan oranlara dayanır ve **güvenilir değildir**.

## 5. Mercilerden gelen talepler

Genel dayanak CMK md. 332/1: "Suçların soruşturma ve kovuşturması sırasında Cumhuriyet savcısı, hâkim veya mahkeme tarafından yazılı olarak istenilen bilgilere on gün içinde cevap verilmesi zorunludur. Eğer bu süre içinde istenen bilgilerin verilmesi imkânsız ise, sebebi ve en geç hangi tarihte cevap verilebileceği aynı süre içinde bildirilir." [S8]. 5651 ve 2017 Yönetmeliği toplu kullanım sağlayıcı için ayrı bir teslim usulü öngörmez [S1][S2].

Önerilen asgari usul (mevzuat şartı değil): yalnız resmî kanaldan gelen yazılı talep kabul edilir; tek yetkili cevap verir; yalnız istenen zaman aralığı ve IP:port ile eşleşen kayıt verilir; talep defteri tutulur; teslim dosyanın hash'i ve o günün bütünlük/zaman damgası kanıtıyla yapılır. Kolluğun savcılık talimatı olmadan kayıt isteme yetkisinin sınırları birincil metinden incelenmedi (**DOĞRULANMADI / UNVERIFIED**).

## 6. KVKK temas noktaları

- Hukuki sebep: KVKK md. 5/2-a ("Kanunlarda açıkça öngörülmesi") ve 5/2-ç; açık rıza istenmez.
- Girişten önce aydınlatma (KVKK md. 10), varsa rıza metninden ayrı.
- Saklama tam 2 yıl, ardından imha (md. 4/2-d, 7).
- Fazladan veri (DNS logu, URL logu, TCKN) 5651 dışındadır; ayrı gerekçelendirilir ya da toplanmaz.
- Hotspot'u bir yüklenici işletiyorsa genellikle veri işleyendir; hizmeti sunan mekân 5651 muhatabı ve veri sorumlusudur (11.11.2026 çalışmasındaki yorum).

## 7. Kaynaklar

- [S1] 5651 sayılı Kanun, konsolide (7590 işlenmiş): https://www.mevzuat.gov.tr/MevzuatMetin/1.5.5651.pdf (erişim 2026-11-20)
- [S2] İnternet Toplu Kullanım Sağlayıcıları Hakkında Yönetmelik, RG 11.04.2017/30035: https://www.resmigazete.gov.tr/eskiler/2017/04/20170411-3.htm (erişim 2026-11-20)
- [S3] 7590 sayılı Kanun, RG 31.07.2026/33326: https://www.resmigazete.gov.tr/eskiler/2026/07/20260731-2.htm (erişim 2026-11-20)
- [S4] 6698 sayılı KVKK: https://www.mevzuat.gov.tr/MevzuatMetin/1.5.6698.pdf (erişim 2026-11-20)
- [S5] BTK, "IP Log İmzalayıcı": https://www.btk.gov.tr/ip-log-imzalayici (erişim 2026-11-20)
- [S6] İkincil: 2017 Yönetmeliğinin konsolide kopyası (Lexpera): https://www.lexpera.com.tr/mevzuat/yonetmelikler/internet-toplu-kullanim-saglayicilari-hakkinda-yonetmelik-1 (erişim 2026-11-20)
- [S7] 5070 sayılı Kanun: https://www.mevzuat.gov.tr/MevzuatMetin/1.5.5070.pdf (erişim 2026-11-11, önceki çalışma; yeniden indirilmedi)
- [S8] 5271 sayılı CMK: https://www.mevzuat.gov.tr/MevzuatMetin/1.5.5271.pdf (erişim 2026-11-11, önceki çalışma; yeniden indirilmedi)
- [S9] 5326 sayılı Kanun: https://www.mevzuat.gov.tr/MevzuatMetin/1.5.5326.pdf (erişim 2026-11-11, önceki çalışma; yeniden indirilmedi)
