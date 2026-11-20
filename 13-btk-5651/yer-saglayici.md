---
Doküman / Document: Yer Sağlayıcı Yükümlülükleri / Hosting Provider Obligations
Bölüm / Section: 13-btk-5651
Sahip / Owner: Hukuk + Bilgi Güvenliği Yöneticisi / Legal + Information Security Manager
Onaylayan / Approved by: KVKK Komitesi / KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-11-20
Gözden Geçirme / Review: Altı aylık + tetiklenmiş (Siber Güvenlik Başkanlığının yer sağlayıcı yönetmeliği, 5651 md. 5 veya 8 değişikliği, AYM kararı) / Semi-annual + triggered (Cybersecurity Presidency hosting regulation, amendment to 5651 Art. 5 or 8, Constitutional Court decision)
İlgili Mevzuat / Legal Reference: 5651 sayılı Kanun md. 2, 3, 5, 8, 8/A, 9/A (7590 işlenmiş) / Law No. 5651 Arts. 2, 3, 5, 8, 8/A, 9/A (incl. Law 7590); 5809 sayılı Kanun md. 60/A (7590 ile eklendi) / Law No. 5809 Art. 60/A (added by Law 7590); Erişim Sağlayıcılara ve Yer Sağlayıcılara Faaliyet Belgesi Verilmesine İlişkin Usul ve Esaslar Hakkında Yönetmelik (RG 24.10.2007/26680); İnternet Ortamında Yapılan Yayınların Düzenlenmesine Dair Usul ve Esaslar Hakkında Yönetmelik (RG 30.11.2007/26716); 6698 sayılı KVKK md. 4, 7, 12 / KVKK Arts. 4, 7, 12
---

## English

# Hosting Provider (Yer Sağlayıcı) Obligations

> Neutral template, not legal advice. Items that could not be confirmed from a primary source are marked **DOĞRULANMADI / UNVERIFIED**. Authority references: since 31.07.2026 the 5651 authority is the Cybersecurity Presidency (*Siber Güvenlik Başkanlığı*), see [README.md](README.md) §2.

## 1. Definition: when is a company a hosting provider?

5651 Art. 2/1-m: "*Yer sağlayıcı: Hizmet ve içerikleri barındıran sistemleri sağlayan veya işleten gerçek veya tüzel kişileri*" (natural or legal persons who provide or operate systems that host services and content) [S1].

Related definitions [S1]:

- Content provider (Art. 2/1-f): whoever produces, changes and provides information or data offered on the internet.
- Removal of content (Art. 2/1-ö): removal of content by content or hosting providers from servers or hosted content.
- Notice method (Art. 2/1-r): a person claiming a rights violation first notifies the content provider and, if no result within a reasonable time, the hosting provider, via their contact addresses.

Practical classification (interpretation, not a statute):

| Situation | Role |
|---|---|
| Company publishes only its own website content | Content provider; the hosting company or cloud provider is the hosting provider |
| Company runs a platform where customers or users publish content (SaaS with customer pages, forum, marketplace listings, customer sub-domains) | Content provider for its own content **and** hosting provider for third-party content |
| Company resells hosting or runs servers for third parties | Hosting provider |
| Company runs a social interaction platform | Also a social network provider (see [erisim-saglayici.md](erisim-saglayici.md) §4); Ek Art. 4/17 says social network duties do not remove hosting duties [S1] |

Art. 5/4 allows a regulation to classify hosting providers "by the nature of their work" and differentiate their duties [S1]. No such classification regulation was found as of 2026-11-20 (**DOĞRULANMADI / UNVERIFIED** that none exists).

## 2. Statutory obligations (5651 Art. 5)

Quoted from the consolidated law [S1]:

| Para. | Obligation | Text (summary; quotes in Turkish section) |
|---|---|---|
| 5/1 | No general monitoring duty | Not obliged to check hosted content or investigate unlawful activity |
| 5/2 | Takedown on notice | Must remove unlawful hosted content when informed under Arts. 8 and 9 |
| 5/3 | Traffic data retention | Keep traffic data for a period set by regulation, **not less than one year and not more than two years**, and ensure its accuracy, integrity and confidentiality |
| 5/4 | Classification | Regulation may classify and differentiate hosting providers |
| 5/5 | (Annulled) | Annulled by Constitutional Court decision E.2014/87, K.2015/112 (8.12.2015) |
| 5/6 | Fine | Hosting provider that **does not make the hosting provider notification** (*yer sağlayıcılık bildirimi*) or does not fulfil its duties under this Law: administrative fine **100,000-1,000,000 TL** by the President (now President of the Cybersecurity Presidency) |

Also relevant:

- **Art. 3/1 identification information:** content, hosting and access providers must keep their identification information up to date and accessible on their own site; fine 2,000-50,000 TL (Art. 3/2) [S1]. The 2007 regulation (UE-Yön Art. 5) limits this to providers acting for "commercial or economic purposes" and lists: name/title, responsible persons, tax ID or trade registry number, address, e-mail and phone, and supervising authority if applicable [S3].
- **Art. 3/3:** notifications may be sent by e-mail or other means to addresses obtained from the website, domain, IP and similar sources [S1]. Keep a monitored legal-notice e-mail on the site.
- **Art. 6/A-11:** the Access Providers Association (*Erişim Sağlayıcıları Birliği*) may send removal/blocking decisions to e-mail addresses found on the content or hosting provider's site [S1].

## 3. Traffic data (trafik bilgisi): what and how long

**Law definition (5651 Art. 2/1-j, as amended by 7253 and 7590):** "IP addresses of the parties, **source and destination port** information, start and end time of the service, type of service used, amount of data transferred and, if any, subscriber identity information" [S1][S2].

**Regulation definition (2007, still in the consolidated text):** hosting traffic data = "source IP address, destination IP address, connection date-time, requested page address, operation information (GET, POST command details) and result information" [S4]. In practice this is a web server / reverse proxy access log.

**Retention period:**

| Source | Period | Status |
|---|---|---|
| 5651 Art. 5/3 (since 6518, 2014) | Set by regulation, **min. 1 year, max. 2 years** | In force [S1] |
| FB-Yön 2007 Art. 16/1-c; UE-Yön 2007 Art. 7/1-c | **6 months**, with hash values and time stamp | Text never updated after 2014; conflicts with the law floor [S4][S3] |

Template position: the statutory floor of 1 year prevails over the outdated 6-month text. Choose a fixed period between 1 and 2 years, write it in the retention schedule with this reasoning, and destroy at the end of it (KVKK Arts. 4/2-d, 7). Which exact period the new Cybersecurity Presidency regulation will set: **DOĞRULANMADI / UNVERIFIED**.

**Integrity:** the law requires accuracy, integrity and confidentiality (Art. 5/3). The 2007 regulations require file integrity values (hash) kept "together with a time stamp" [S4]. Under Law 5070 Art. 3/h a legal time stamp is one verified by an electronic certificate service provider (findings of the 2026-11-11 study; Kamu SM status as ESHS not re-checked: **DOĞRULANMADI / UNVERIFIED**).

**Field set recommended for a template:** timestamp (with time zone, NTP-synced), source IP, **source port** (needed behind CGNAT; the law definition now names source and destination port), destination IP and port, requested URL/host, method, status code, bytes, user/customer ID if authenticated. Do **not** log request bodies, passwords, tokens or full query strings carrying personal data (see [../05-teknik-tedbirler/log-yonetimi.md](../05-teknik-tedbirler/log-yonetimi.md) §4).

## 4. Hosting provider notification (bildirim) and activity certificate

- The **2007 regulation** (FB-Yön) still requires every natural or legal person who wants to act as a hosting provider in Türkiye to obtain an **activity certificate** (*faaliyet belgesi*) before starting (Art. 4/1); applications are made electronically with Annex 5 petition and Annex 6 form, originals sent within one week (Art. 9/2); the certificate is valid 5 years (Art. 5/2); changes are reported within one month (Art. 17) [S4]. The consolidated index shows only one amendment (RG 1.3.2008/26803) [S4].
- The **law** since 2014 speaks of a "*yer sağlayıcılık bildirimi*" (hosting provider notification) and fines its absence (Art. 5/6) [S1].
- Secondary sources state that the certificate was replaced by an online notification made through the BTK hosting provider interface `https://yersaglayici.btk.gov.tr/` with e-Devlet login, after which the site appears on the BTK hosting provider list with a number; a 2021 forum post describes monthly CSV uploads of hosted/registered domains [S6][S7]. The e-Devlet entry point is confirmed below; the regulatory text replacing the certificate and the list of required documents were not found (**DOĞRULANMADI / UNVERIFIED**).
- e-Devlet lists a BTK service "Yer Sağlayıcılığı Bildirimi" at `https://www.turkiye.gov.tr/btk-yer-saglayiciligi-bildirimi-4322`, described as "5651 Sayılı Kanunun ilgili maddesi gereğince Yer Sağlayıcı Bildirimlerinin değerlendirilmesi"; login with e-Devlet password, mobile signature, e-signature, ID card or internet banking [S10] (checked 2026-11-20; the form content behind the login was not reviewed).
- On **2026-11-20** both `https://yersaglayici.btk.gov.tr/` and `https://yersaglayici.siberguvenlik.gov.tr/` returned a "Sitemiz bakım aşamasındadır" (under maintenance) page; `https://www.btk.gov.tr/yer-saglayici-listesi` links to a list URL that returned 404 (checked 2026-11-20).

Action for the template: before launching a hosting service, check the current portal (Cybersecurity Presidency or BTK), file the notification, keep the filing receipt and number in the compliance file, and re-check after each authority announcement. Whether a company that hosts only its **own** content must notify: commonly answered "no" in practice (secondary source [S7]); **DOĞRULANMADI / UNVERIFIED**.

## 5. Content removal (içeriğin yayından çıkarılması): deadlines

| Basis | Who decides | Deadline for providers | Sanction for non-compliance |
|---|---|---|---|
| 5651 Art. 8 (catalogue crimes: e.g. child sexual abuse, obscenity, gambling, incitement to suicide) | Judge/court; prosecutor in urgent cases (judge approval within 24 h + 24 h); the President ex officio for certain content | Art. 8/5: **immediately and at the latest within 4 hours** of notification [S1] | Art. 8/10: those responsible at content, hosting or access providers: judicial fine 500-3,000 days for not executing a protective measure; Art. 8/11 administrative fine 10,000-100,000 (old) TL for administrative measures (part of the addressee wording annulled by AYM E.2020/76 K.2023/172) [S1] |
| 5651 Art. 8/A (urgent: right to life, national security, public order, crime prevention, public health) | The President, on request of the Presidency of the Republic or ministries; judge approval within 24 h, decision within 48 h | **Immediately and within 4 hours** (8/A-1) [S1] | Art. 8/A-5: **50,000-500,000 TL** administrative fine on access, content and hosting providers; Art. 8/A-4: failing to give information needed to identify perpetrators on judicial decision: judicial fine 3,000-10,000 days [S1] |
| 5651 Art. 9 (personal rights) | **Annulled** by AYM E.2020/76, K.2023/172, effective **10.10.2024** [S1] | n/a | Which procedure replaces Art. 9 for personal-rights takedowns: **DOĞRULANMADI / UNVERIFIED** (no new Art. 9 in the consolidated text as of 2026-11-20) |
| 5651 Art. 9/A (privacy) | Applicant to the Presidency; judge within 24 h + 48 h | Access providers block within 4 hours (URL-based) [S1] | Mainly access provider; hosting provider should still remove on a court order |
| 5809 Art. 60/A (added by 7590; Constitution Art. 22 grounds, urgent) | Cybersecurity Presidency; judge approval within 24 h + 48 h | **Immediately and at the latest within 2 hours**; addressed also to "data centres and relevant content and hosting providers" [S8] | Art. 60/A-3: 20,000-100,000 TL per violating act [S8] |

Older procedural rule: UE-Yön 2007 Art. 10 (2-day response to removal and reply requests) is shown as annulled by Danıştay 13th Chamber E.2013/239, K.2019/4266, affirmed by İDDK 2022 (secondary consolidated source [S9]; **DOĞRULANMADI / UNVERIFIED** from primary text).

Operational minimum for a 4-hour (and 2-hour) clock:

1. One published legal-notice e-mail and a 24/7 on-call role able to remove content.
2. Runbook: verify sender (KEP, official domain, Association system), identify URL, remove or disable, preserve a copy for evidence, confirm in writing, record times.
3. Register of decisions received (date-time of notification, URL, action, time of action, person).

## 6. Fines summary (nominal amounts in the law text)

| Provision | Amount | Authority |
|---|---|---|
| Art. 3/2 identification info | 2,000-50,000 TL | President (Cybersecurity Presidency) |
| Art. 5/6 no notification / duties | 100,000-1,000,000 TL | President |
| Art. 8/A-5 urgent decision not executed | 50,000-500,000 TL | President |
| 5809 Art. 60/A-3 | 20,000-100,000 TL per act | Cybersecurity Presidency |

Whether and how these amounts are revalued yearly under Law 5326 Art. 17/7, and the 2026 figures: **DOĞRULANMADI / UNVERIFIED** (no official 2026 table found).

## 7. KVKK touchpoints

- Hosting traffic logs: legal basis KVKK Art. 5/2-a/ç; period per §3; then Art. 7 destruction.
- Customer content you host is processed **on the customer's behalf**: you are usually a data processor; a data processing agreement is needed (KVKK Art. 12/2).
- Takedown requests often contain personal data of the complainant; keep them under the same access controls.

## 8. Sources

- [S1] Law No. 5651, consolidated (incl. 7590): https://www.mevzuat.gov.tr/MevzuatMetin/1.5.5651.pdf (accessed 2026-11-20)
- [S2] Law No. 7590, OG 31.07.2026/33326: https://www.resmigazete.gov.tr/eskiler/2026/07/20260731-2.htm (accessed 2026-11-20)
- [S3] Regulation on the Procedures and Principles for Internet Publications (UE-Yön), OG 30.11.2007/26716: https://www.resmigazete.gov.tr/eskiler/2007/11/20071130-6.htm (accessed 2026-11-20)
- [S4] Activity Certificate Regulation (FB-Yön), OG 24.10.2007/26680: https://www.resmigazete.gov.tr/eskiler/2007/10/20071024-12.htm ; consolidated index: https://www.mevzuat.gov.tr/anasayfa/MevzuatFihristDetayIframe?MevzuatTur=7&MevzuatNo=11679&MevzuatTertip=5 (accessed 2026-11-20)
- [S5] BTK page "Yer Sağlayıcı Listesi": https://www.btk.gov.tr/yer-saglayici-listesi (accessed 2026-11-20)
- [S6] Secondary: Levent Samgar, "5651 Yer Sağlayıcı" (undated): https://leventsamgar.com/5651-yer-saglayici/ (accessed 2026-11-20)
- [S7] Secondary: R10.net forum post, 21.05.2021: https://www.r10.net/bilisim-hukuku/2825326-btk-yer-saglayici-listesi-yer-saglayici-bildirimi.html (accessed 2026-11-20)
- [S8] Law No. 5809, consolidated (Art. 60/A, definition "Başkanlık"): https://www.mevzuat.gov.tr/MevzuatMetin/1.5.5809.pdf (accessed 2026-11-20)
- [S9] Secondary consolidated text of UE-Yön (Lexpera): https://www.lexpera.com.tr/mevzuat/yonetmelikler/internet-ortaminda-yapilan-yayinlarin-duzenlenmesine-dair-usul-ve-esaslar-hakkinda-yonetmelik (accessed 2026-11-20)
- [S10] e-Devlet, BTK "Yer Sağlayıcılığı Bildirimi": https://www.turkiye.gov.tr/btk-yer-saglayiciligi-bildirimi-4322 (accessed 2026-11-20)

---

## Türkçe

# Yer Sağlayıcı Yükümlülükleri

> Nötr şablondur, hukuki görüş değildir. Birincil kaynaktan doğrulanamayan noktalar **DOĞRULANMADI / UNVERIFIED** olarak işaretlidir. Yetkili kurum: 31.07.2026'dan beri 5651'in yetkili kurumu Siber Güvenlik Başkanlığıdır, bkz. [README.md](README.md) §2.

## 1. Tanım: şirket ne zaman yer sağlayıcıdır?

5651 md. 2/1-m: "Yer sağlayıcı: Hizmet ve içerikleri barındıran sistemleri sağlayan veya işleten gerçek veya tüzel kişileri," [S1].

İlgili tanımlar [S1]:

- İçerik sağlayıcı (md. 2/1-f): "İnternet ortamı üzerinden kullanıcılara sunulan her türlü bilgi veya veriyi üreten, değiştiren ve sağlayan gerçek veya tüzel kişileri,"
- İçeriğin yayından çıkarılması (md. 2/1-ö): "İçerik veya yer sağlayıcılar tarafından içeriğin sunuculardan veya barındırılan içerikten çıkarılmasını,"
- Uyarı yöntemi (md. 2/1-r): hakkı ihlal edildiğini iddia eden kişinin önce içerik sağlayıcısına, makul sürede sonuç alınamazsa yer sağlayıcısına iletişim adresleri üzerinden bildirimi.

Pratik sınıflandırma (kanun hükmü değil, yorumdur):

| Durum | Rol |
|---|---|
| Şirket yalnız kendi web sitesi içeriğini yayımlıyor | İçerik sağlayıcı; hosting/bulut firması yer sağlayıcıdır |
| Müşterilerin veya kullanıcıların içerik yayımladığı platform (müşteri sayfalı SaaS, forum, ilan, müşteri alt alan adları) | Kendi içeriği için içerik sağlayıcı **ve** üçüncü kişi içeriği için yer sağlayıcı |
| Hosting bayiliği ya da üçüncü kişiler için sunucu işletme | Yer sağlayıcı |
| Sosyal etkileşim platformu | Ayrıca sosyal ağ sağlayıcı (bkz. [erisim-saglayici.md](erisim-saglayici.md) §4); Ek md. 4/17'ye göre sosyal ağ yükümlülükleri yer sağlayıcılıktan doğan yükümlülükleri kaldırmaz [S1] |

Md. 5/4, yer sağlayıcıların "yaptıkları işin niteliğine göre" sınıflandırılmasını yönetmeliğe bırakır [S1]. 2026-11-20 itibarıyla böyle bir sınıflandırma yönetmeliği bulunamadı (hiç olmadığı **DOĞRULANMADI / UNVERIFIED**).

## 2. Kanuni yükümlülükler (5651 md. 5)

Konsolide metinden [S1]:

- **md. 5/1:** "Yer sağlayıcı, yer sağladığı içeriği kontrol etmek veya hukuka aykırı bir faaliyetin söz konusu olup olmadığını araştırmakla yükümlü değildir."
- **md. 5/2:** "Yer sağlayıcı, yer sağladığı hukuka aykırı içeriği bu Kanunun 8 inci ve 9 uncu maddelerine göre haberdar edilmesi hâlinde yayından çıkarmakla yükümlüdür."
- **md. 5/3:** "Yer sağlayıcı, yer sağladığı hizmetlere ilişkin trafik bilgilerini bir yıldan az ve iki yıldan fazla olmamak üzere yönetmelikte belirlenecek süre kadar saklamakla ve bu bilgilerin doğruluğunu, bütünlüğünü ve gizliliğini sağlamakla yükümlüdür."
- **md. 5/4:** yönetmelikle sınıflandırma ve farklılaştırma imkânı.
- **md. 5/5:** AYM'nin 8.12.2015 tarihli E.2014/87, K.2015/112 sayılı kararıyla iptal.
- **md. 5/6:** "Yer sağlayıcılık bildiriminde bulunmayan veya bu Kanundaki yükümlülüklerini yerine getirmeyen yer sağlayıcı hakkında Başkan tarafından yüz bin Türk lirasından bir milyon Türk lirasına kadar idari para cezası verilir." (Başkan: 7590 sonrası Siber Güvenlik Başkanı)

İlgili diğer hükümler:

- **md. 3/1 tanıtıcı bilgiler:** içerik, yer ve erişim sağlayıcıları tanıtıcı bilgilerini kendi internet ortamında güncel bulundurur; aykırılıkta 2.000-50.000 TL idari para cezası (md. 3/2) [S1]. 2007 tarihli UE-Yön md. 5 bunu "ticari veya ekonomik amaçlı" sağlayıcılarla sınırlar ve şunları sayar: ad-soyad/unvan ve sorumlu kişiler, vergi kimlik veya ticaret sicil numarası, yerleşim yeri/merkez, e-posta ve telefon, varsa denetim mercii [S3].
- **md. 3/3:** bildirim internet sayfasındaki iletişim araçları, alan adı, IP adresi ve benzeri kaynaklardan elde edilen adreslere e-posta veya diğer iletişim araçlarıyla yapılabilir [S1]. Sitede izlenen bir hukuki bildirim e-postası bulundurun.
- **md. 6/A-11:** Erişim Sağlayıcıları Birliği içeriğin çıkarılması ve/veya erişimin engellenmesi kararlarını içerik veya yer sağlayıcının sitesinden tespit edilebilen e-posta adreslerine bildirebilir [S1].

## 3. Trafik bilgisi: ne ve ne kadar süre

**Kanun tanımı (5651 md. 2/1-j, 7253 ve 7590 değişiklikleriyle):** "Trafik bilgisi: Taraflara ilişkin IP adresi, kaynak ve hedef port bilgisi, verilen hizmetin başlama ve bitiş zamanı, yararlanılan hizmetin türü, aktarılan veri miktarı ve varsa abone kimlik bilgilerini," [S1][S2].

**Yönetmelik tanımı (2007, konsolide metinde hâlâ duruyor):** "Yer sağlayıcı trafik bilgisi: İnternet ortamındaki her türlü yer sağlamaya ilişkin olarak; kaynak IP adresi, hedef IP adresi, bağlantı tarih-saat bilgisi, istenen sayfa adresi, işlem bilgisi (GET, POST komut detayları) ve sonuç bilgisi gibi bilgileri," [S4]. Pratikte web sunucusu / ters vekil sunucu erişim logudur.

**Saklama süresi:**

| Kaynak | Süre | Durum |
|---|---|---|
| 5651 md. 5/3 (6518 ile, 2014) | Yönetmelikle belirlenir, **en az 1, en çok 2 yıl** | Yürürlükte [S1] |
| FB-Yön 2007 md. 16/1-c; UE-Yön 2007 md. 7/1-c | **Altı ay**, hash ve zaman damgasıyla | 2014 sonrası güncellenmedi; kanuni alt sınırla çelişiyor [S4][S3] |

Şablon duruşu: kanundaki bir yıllık alt sınır, güncellenmemiş altı aylık yönetmelik metnine üstündür. 1 ile 2 yıl arasında sabit bir süre seçilir, gerekçesiyle saklama tablosuna yazılır ve süre sonunda imha edilir (KVKK md. 4/2-d, 7). Siber Güvenlik Başkanlığının yeni yönetmeliğinin hangi süreyi belirleyeceği **DOĞRULANMADI / UNVERIFIED**.

**Bütünlük:** kanun doğruluk, bütünlük ve gizlilik ister (md. 5/3). 2007 yönetmelikleri dosya bütünlük değerlerinin (hash) "zaman damgası ile birlikte" saklanmasını ister [S4]. 5070 md. 3/h'ye göre hukuki anlamda zaman damgası, elektronik sertifika hizmet sağlayıcısının elektronik imzayla doğruladığı kayıttır (2026-11-11 çalışmasının bulgusu; Kamu SM'nin ESHS statüsü yeniden kontrol edilmedi: **DOĞRULANMADI / UNVERIFIED**).

**Şablon için önerilen alan seti:** zaman (saat dilimiyle, NTP eşzamanlı), kaynak IP, **kaynak port** (CGNAT arkasında gerekir; kanun tanımı artık kaynak ve hedef portu sayıyor), hedef IP ve port, istenen URL/host, metot, durum kodu, bayt, kimlik doğrulanmışsa kullanıcı/müşteri kimliği. İstek gövdesi, parola, token ve kişisel veri taşıyan tam sorgu dizesi **loglanmaz** (bkz. [../05-teknik-tedbirler/log-yonetimi.md](../05-teknik-tedbirler/log-yonetimi.md) §4).

## 4. Yer sağlayıcılık bildirimi ve faaliyet belgesi

- **2007 yönetmeliği** (FB-Yön) md. 4/1 hâlâ şöyle der: "Türkiye Cumhuriyeti sınırları içerisinde erişim sağlayıcı olmak isteyen sermaye şirketleri ile yer sağlayıcı olarak faaliyet göstermek isteyen gerçek veya tüzel kişiler, hizmet vermeye başlamadan önce Kurum tarafından düzenlenecek faaliyet belgesini almakla yükümlüdür." Başvuru Ek-5 dilekçe ve Ek-6 formla elektronik ortamda yapılır, asıllar bir hafta içinde gönderilir (md. 9/2); belge beş yıl geçerlidir (md. 5/2); bilgi değişikliği bir ay içinde bildirilir (md. 17) [S4]. Konsolide fihrist yalnız bir değişiklik gösterir (RG 1.3.2008/26803) [S4].
- **Kanun** 2014'ten beri "yer sağlayıcılık bildirimi"nden söz eder ve yapılmamasını cezalandırır (md. 5/6) [S1].
- İkincil kaynaklara göre faaliyet belgesinin yerini, BTK Yer Sağlayıcılığı Bildirim Arayüzü (`https://yersaglayici.btk.gov.tr/`) üzerinden e-Devlet girişiyle yapılan çevrim içi bildirim almıştır; kabul edilen site BTK Yer Sağlayıcı Listesi'nde numarasıyla yayımlanır; 2021 tarihli bir forum iletisi barındırılan/tescil edilen alan adlarının her ay CSV ile yüklendiğini anlatır [S6][S7]. e-Devlet giriş noktası aşağıda doğrulandı; faaliyet belgesinin yerini alan düzenleyici metin ve istenen belge listesi bulunamadı (**DOĞRULANMADI / UNVERIFIED**).
- e-Devlet'te BTK'ya ait "Yer Sağlayıcılığı Bildirimi" hizmeti `https://www.turkiye.gov.tr/btk-yer-saglayiciligi-bildirimi-4322` adresinde listelenir; açıklaması "5651 Sayılı Kanunun ilgili maddesi gereğince Yer Sağlayıcı Bildirimlerinin değerlendirilmesi." Giriş e-Devlet şifresi, mobil imza, elektronik imza, kimlik kartı veya internet bankacılığıyla yapılır [S10] (2026-11-20 kontrolü; giriş arkasındaki form incelenmedi).
- **2026-11-20** tarihinde hem `https://yersaglayici.btk.gov.tr/` hem `https://yersaglayici.siberguvenlik.gov.tr/` "Sitemiz bakım aşamasındadır" sayfası döndürdü; `https://www.btk.gov.tr/yer-saglayici-listesi` sayfasındaki liste bağlantısı 404 verdi (2026-11-20 kontrolü).

Şablon için eylem: barındırma hizmetine başlamadan önce güncel portalı (Siber Güvenlik Başkanlığı veya BTK) kontrol edin, bildirimi yapın, başvuru alındısını ve numarasını uyum dosyasında saklayın, her kurum duyurusundan sonra yeniden kontrol edin. Yalnız **kendi** içeriğini barındıran şirketin bildirim yapıp yapmayacağı uygulamada genellikle "hayır" diye cevaplanır (ikincil kaynak [S7]); **DOĞRULANMADI / UNVERIFIED**.

## 5. İçeriğin yayından çıkarılması: süreler

| Dayanak | Karar mercii | Sağlayıcı için süre | Uymamanın yaptırımı |
|---|---|---|---|
| 5651 md. 8 (katalog suçlar: çocukların cinsel istismarı, müstehcenlik, kumar, intihara yönlendirme vb.) | Hâkim/mahkeme; gecikmede sakınca varsa savcı (24 saatte hâkim onayı, hâkim 24 saatte karar); bazı içerikte Başkan re'sen | md. 8/5: "derhal ve en geç kararın bildirilmesi anından itibaren dört saat içinde" [S1] | md. 8/10: koruma tedbirini uygulamayan içerik, yer veya erişim sağlayıcı sorumlularına 500-3.000 gün adli para cezası; md. 8/11: idari tedbir kararına uymamada 10.000-100.000 (eski) TL idari para cezası (muhatap ibaresinin bir kısmı AYM E.2020/76 K.2023/172 ile iptal) [S1] |
| 5651 md. 8/A (yaşam hakkı, millî güvenlik, kamu düzeni, suçun önlenmesi, genel sağlık; gecikmede sakınca) | Cumhurbaşkanlığı veya bakanlık talebiyle Başkan; 24 saatte hâkim onayı, hâkim 48 saatte karar | "derhâl ve en geç kararın bildirilmesi anından itibaren dört saat içinde" (md. 8/A-1) [S1] | md. 8/A-5: erişim, içerik ve yer sağlayıcılara **50.000-500.000 TL** idari para cezası; md. 8/A-4: faillere ulaşmak için gereken bilgiyi hâkim kararına rağmen vermeyen sorumlulara 3.000-10.000 gün adli para cezası [S1] |
| 5651 md. 9 (kişilik hakları) | AYM E.2020/76, K.2023/172 ile **iptal**, yürürlük **10.10.2024** [S1] | - | md. 9'un yerine hangi usulün uygulanacağı **DOĞRULANMADI / UNVERIFIED** (2026-11-20 itibarıyla konsolide metinde yeni md. 9 yok) |
| 5651 md. 9/A (özel hayatın gizliliği) | Başkanlığa başvuru; 24 saatte hâkime sunulur, hâkim 48 saatte karar verir | Erişim sağlayıcılar URL bazında 4 saatte uygular [S1] | Esas muhatap erişim sağlayıcıdır; yer sağlayıcı mahkeme kararı gelirse yine çıkarır |
| 5809 md. 60/A (7590 ile eklendi; Anayasa md. 22 sebepleri, gecikmede sakınca) | Siber Güvenlik Başkanlığı; 24 saatte hâkim onayı, hâkim 48 saatte karar | "derhal ve kararın bildirilmesi anından itibaren en geç iki saat içinde"; muhataplar arasında "veri merkezlerine ve ilgili içerik ve yer sağlayıcılara" da var [S8] | md. 60/A-3: ihlal teşkil eden eylem başına 20.000-100.000 TL [S8] |

Eski usul hükmü: UE-Yön 2007 md. 10 (çıkarma ve cevap talebine iki gün içinde yanıt) Danıştay 13. Dairesinin E.2013/239, K.2019/4266 kararıyla iptal edilmiş, İDDK 2022'de onanmış görünüyor (ikincil konsolide kaynak [S9]; birincil metinden **DOĞRULANMADI / UNVERIFIED**).

4 saatlik (ve 2 saatlik) süre için asgari işleyiş:

1. Sitede yayımlanmış tek bir hukuki bildirim e-postası ve içeriği kaldırabilecek 7/24 nöbetçi rol.
2. Runbook: göndereni doğrula (KEP, resmî alan adı, Birlik sistemi), URL'yi belirle, kaldır veya erişimi kapat, delil için kopya sakla, yazılı teyit ver, saatleri kaydet.
3. Gelen kararlar defteri (bildirim tarih-saati, URL, işlem, işlem saati, işlemi yapan kişi).

## 6. Ceza özeti (kanun metnindeki nominal tutarlar)

| Hüküm | Tutar | Yetkili |
|---|---|---|
| md. 3/2 tanıtıcı bilgi | 2.000-50.000 TL | Başkan (Siber Güvenlik Başkanı) |
| md. 5/6 bildirim yok / yükümlülük ihlali | 100.000-1.000.000 TL | Başkan |
| md. 8/A-5 acil karara uymama | 50.000-500.000 TL | Başkan |
| 5809 md. 60/A-3 | Eylem başına 20.000-100.000 TL | Siber Güvenlik Başkanlığı |

Bu tutarların 5326 sayılı Kanun md. 17/7 uyarınca yıllık yeniden değerlemeye tabi olup olmadığı ve 2026 tutarları **DOĞRULANMADI / UNVERIFIED** (resmî 2026 tablosu bulunamadı).

## 7. KVKK temas noktaları

- Yer sağlayıcı trafik logu: hukuki sebep KVKK md. 5/2-a/ç; süre §3'e göre; ardından md. 7 imha.
- Barındırdığınız müşteri içeriği **müşteri adına** işlenir: genellikle veri işleyensiniz; veri işleme sözleşmesi gerekir (KVKK md. 12/2).
- İçerik kaldırma talepleri çoğu zaman şikâyetçinin kişisel verisini içerir; aynı erişim kontrolleri altında tutulur.

## 8. Kaynaklar

- [S1] 5651 sayılı Kanun, konsolide (7590 işlenmiş): https://www.mevzuat.gov.tr/MevzuatMetin/1.5.5651.pdf (erişim 2026-11-20)
- [S2] 7590 sayılı Kanun, RG 31.07.2026/33326: https://www.resmigazete.gov.tr/eskiler/2026/07/20260731-2.htm (erişim 2026-11-20)
- [S3] İnternet Ortamında Yapılan Yayınların Düzenlenmesine Dair Usul ve Esaslar Hakkında Yönetmelik (UE-Yön), RG 30.11.2007/26716: https://www.resmigazete.gov.tr/eskiler/2007/11/20071130-6.htm (erişim 2026-11-20)
- [S4] Faaliyet Belgesi Yönetmeliği (FB-Yön), RG 24.10.2007/26680: https://www.resmigazete.gov.tr/eskiler/2007/10/20071024-12.htm ; konsolide fihrist: https://www.mevzuat.gov.tr/anasayfa/MevzuatFihristDetayIframe?MevzuatTur=7&MevzuatNo=11679&MevzuatTertip=5 (erişim 2026-11-20)
- [S5] BTK "Yer Sağlayıcı Listesi" sayfası: https://www.btk.gov.tr/yer-saglayici-listesi (erişim 2026-11-20)
- [S6] İkincil: Levent Samgar, "5651 Yer Sağlayıcı" (tarihsiz): https://leventsamgar.com/5651-yer-saglayici/ (erişim 2026-11-20)
- [S7] İkincil: R10.net forum iletisi, 21.05.2021: https://www.r10.net/bilisim-hukuku/2825326-btk-yer-saglayici-listesi-yer-saglayici-bildirimi.html (erişim 2026-11-20)
- [S8] 5809 sayılı Kanun, konsolide (md. 60/A, "Başkanlık" tanımı): https://www.mevzuat.gov.tr/MevzuatMetin/1.5.5809.pdf (erişim 2026-11-20)
- [S9] İkincil: UE-Yön konsolide metni (Lexpera): https://www.lexpera.com.tr/mevzuat/yonetmelikler/internet-ortaminda-yapilan-yayinlarin-duzenlenmesine-dair-usul-ve-esaslar-hakkinda-yonetmelik (erişim 2026-11-20)
- [S10] e-Devlet, BTK "Yer Sağlayıcılığı Bildirimi": https://www.turkiye.gov.tr/btk-yer-saglayiciligi-bildirimi-4322 (erişim 2026-11-20)
