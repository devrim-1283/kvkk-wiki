---
Doküman / Document: BTK / 5651 Yükümlülükleri: Bölüm Girişi / BTK / Law 5651 Obligations: Section Introduction
Bölüm / Section: 13-btk-5651
Sahip / Owner: Hukuk + KVKK Sorumlusu / Legal + KVKK Officer
Onaylayan / Approved by: KVKK Komitesi + Bilgi Güvenliği Yöneticisi / KVKK Committee + Information Security Manager
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-11-20
Gözden Geçirme / Review: Altı aylık + tetiklenmiş (Siber Güvenlik Başkanlığının yeni ikincil düzenlemesi, 5651 değişikliği, Anayasa Mahkemesi kararı) / Semi-annual + triggered (new secondary regulation by the Cybersecurity Presidency, amendment to Law 5651, Constitutional Court decision)
İlgili Mevzuat / Legal Reference: 5651 sayılı Kanun (7590 sayılı Kanun işlenmiş konsolide metin) / Law No. 5651 (consolidated, incl. Law No. 7590); 7590 sayılı Kanun (RG 31.07.2026/33326); 7545 sayılı Siber Güvenlik Kanunu (RG 19.03.2025/32846); İnternet Toplu Kullanım Sağlayıcıları Hakkında Yönetmelik (RG 11.04.2017/30035); Erişim Sağlayıcılara ve Yer Sağlayıcılara Faaliyet Belgesi Verilmesine İlişkin Usul ve Esaslar Hakkında Yönetmelik (RG 24.10.2007/26680); İnternet Ortamında Yapılan Yayınların Düzenlenmesine Dair Usul ve Esaslar Hakkında Yönetmelik (RG 30.11.2007/26716); 6698 sayılı KVKK md. 4, 5, 7, 12, 28 / KVKK Arts. 4, 5, 7, 12, 28
---

## English

# BTK / Law 5651 Obligations: Section Introduction

> Neutral template. Not legal advice. Every legal statement below carries a source URL and access date; anything that could not be confirmed from a primary source is marked **DOĞRULANMADI / UNVERIFIED**.

## 1. Why this section exists

Law No. 5651 (the "Internet Law") assigns obligations by **role**, not by sector. A single company can hold several roles at once:

| Role (5651 Art. 2) | Typical company situation | Document |
|---|---|---|
| Content provider (*içerik sağlayıcı*, Art. 2/1-f) | Company website, blog, app content | Covered briefly in [yer-saglayici.md](yer-saglayici.md) §3 (identification info) |
| Hosting provider (*yer sağlayıcı*, Art. 2/1-m) | Hosts third-party content or services: SaaS where customers publish content, forums, customer sub-sites, hosting/reseller business | [yer-saglayici.md](yer-saglayici.md) |
| Mass-use provider (*toplu kullanım sağlayıcı*, Art. 2/1-i) | Office, guest or tenant Wi-Fi, café, hotel, co-working, incubator | [toplu-kullanim-saglayici.md](toplu-kullanim-saglayici.md) |
| Access provider (*erişim sağlayıcı*, Art. 2/1-e) | ISPs and operators; rarely an ordinary company | [erisim-saglayici.md](erisim-saglayici.md) |
| Social network provider (*sosyal ağ sağlayıcı*, Art. 2/1-s) | Platforms where users create and share content for social interaction | [erisim-saglayici.md](erisim-saglayici.md) §4 |

Supporting documents: [btk-dokumantasyon.md](btk-dokumantasyon.md) (portals, forms, contact points, cybersecurity bodies) and [log-kontrol-listesi.md](log-kontrol-listesi.md) (5651 log requirement ↔ KVKK principle checklist).

## 2. Important change: "BTK" is no longer the 5651 authority (since 31.07.2026)

Law No. 7590 (accepted 24.07.2026, Official Gazette 31.07.2026, No. 33326) transferred the Information and Communication Technologies Authority's (BTK, "Kurum") powers under Law 5651 to the **Cybersecurity Presidency** (*Siber Güvenlik Başkanlığı*, "Başkanlık"). Art. 27/2-a of Law 7590 adds to 5651 Art. 2/1 the definition "v) Başkanlık: Siber Güvenlik Başkanlığını" and changes the definition of "Başkan" to the President of the Cybersecurity Presidency [S1][S2].

Transitional rule (Law 7545 Provisional Art. 2/1, added by Law 7590 Art. 26): until the Cybersecurity Presidency issues its own secondary regulations, **existing regulations continue to apply**, and references in them to BTK are deemed made to the Cybersecurity Presidency [S1].

Practical consequences:

- The 2007 and 2017 regulations cited in this section are still the operative texts; read "Kurum"/"BTK" in them as "Siber Güvenlik Başkanlığı".
- In privacy notices, contracts and internal documents, refer to "Siber Güvenlik Başkanlığı" (optionally "formerly BTK").
- Whether the Cybersecurity Presidency has published a new 5651 regulation or draft after 31.07.2026: none found in searches on 2026-11-20: **DOĞRULANMADI / UNVERIFIED** that none exists.
- The section folder keeps the name `13-btk-5651` for findability; BTK still runs operator authorisation under Law 5809 and some legacy portals (see [btk-dokumantasyon.md](btk-dokumantasyon.md)).

## 3. How 5651 relates to KVKK

5651 logs contain personal data (IP, MAC address, port, timestamps, and sometimes subscriber identity). The two regimes interact as follows:

| Question | 5651 says | KVKK says | Resulting rule |
|---|---|---|---|
| Legal basis for keeping the log | Retention is a statutory duty (e.g. 5651 Art. 5/3, 6/1-b, 7/2) [S2] | Processing without consent is allowed where "expressly provided for by laws" (Art. 5/2-a) or necessary for a legal obligation (Art. 5/2-ç) [S3] | Do **not** ask for explicit consent for 5651 logs; cite the law. |
| Which fields | The regulation lists the fields (e.g. 2017 Regulation Art. 3/1-e for mass-use providers) [S4] | Data must be "connected, limited and proportionate" to the purpose (Art. 4/2-ç) [S3] | Collect the listed fields. Extra fields (DNS queries, URLs, national ID) need a separate basis and proportionality analysis. |
| How long | Fixed periods or ranges: mass-use 2 years; hosting 1-2 years; access 6 months-2 years [S2][S4] | Keep only "for the period laid down in the relevant legislation or necessary for the purpose" (Art. 4/2-d), then erase/destroy/anonymise (Art. 7) [S3] | Retention period = the 5651 period. On expiry, destroy in the next periodic destruction cycle (see [../04-veri-saklama-ve-imha/](../04-veri-saklama-ve-imha/)). |
| Security | Accuracy, integrity, confidentiality for hosting/access traffic data (Art. 5/3, 6/1-b) [S2] | Appropriate technical and organisational measures (Art. 12/1); joint responsibility with processors (Art. 12/2) [S3] | Same controls satisfy both: access control, integrity values, access logging. |
| Disclosure to authorities | Court/prosecutor requests; Cybersecurity Presidency requests | Arts. 10, 11 and 16 do not apply where processing is necessary for crime prevention or investigation, provided it is proportionate (Art. 28/2-a) [S3] | Hand over only what the written request covers; keep a register. |

**The core tension: log retention vs data minimisation.** 5651 forces retention; KVKK forbids anything beyond what is needed. The defensible position is: keep **exactly** the 5651 field set, for **exactly** the 5651 period, with access restricted to named roles, and destroy on schedule. Logging "everything, forever, just in case" is a KVKK violation that 5651 does not excuse.

## 4. Consistency notes for other sections of this wiki

- [../05-teknik-tedbirler/log-yonetimi.md](../05-teknik-tedbirler/log-yonetimi.md) §7 shows "Law No. 5651 (if hosting provider): 2 years to 10 years". The 5651 ranges reviewed here have a **maximum of two years** for hosting, access and mass-use logs [S2][S4]. The 10-year figure has no basis in 5651.
- [../04-veri-saklama-ve-imha/saklama-sureleri-tablosu.md](../04-veri-saklama-ve-imha/saklama-sureleri-tablosu.md) row 28 shows "6 months - 2 years" for web server logs under 5651 Art. 5. Since the 2014 amendment the statutory floor for hosting providers is **one year** (5651 Art. 5/3); the six-month figure comes from the 2007 regulations, which were not updated [S2][S5].

These are recommendations for follow-up edits in those documents; this section does not change them.

## 5. Section contents

| Document | Scope |
|---|---|
| [yer-saglayici.md](yer-saglayici.md) | Hosting provider: definition, notification, traffic data, takedown deadlines, fines |
| [toplu-kullanim-saglayici.md](toplu-kullanim-saglayici.md) | Mass-use provider: commercial vs non-commercial, permit, log set, integrity, filtering, fines |
| [erisim-saglayici.md](erisim-saglayici.md) | Access provider basics; social network provider rules (7253/7418/7578) as far as relevant to companies |
| [btk-dokumantasyon.md](btk-dokumantasyon.md) | Portals, forms, documents, contact points; Cybersecurity Presidency, USOM, Law 7545; sector cybersecurity regulation |
| [log-kontrol-listesi.md](log-kontrol-listesi.md) | Checklist mapping 5651 log requirements to KVKK principles |

## 6. Sources

- [S1] Law No. 7590, Official Gazette 31.07.2026/33326: https://www.resmigazete.gov.tr/eskiler/2026/07/20260731-2.htm (accessed 2026-11-20)
- [S2] Law No. 5651, consolidated text (incl. 7590): https://www.mevzuat.gov.tr/MevzuatMetin/1.5.5651.pdf (accessed 2026-11-20)
- [S3] Law No. 6698 (KVKK), consolidated: https://www.mevzuat.gov.tr/MevzuatMetin/1.5.6698.pdf (accessed 2026-11-20)
- [S4] Regulation on Internet Mass-Use Providers, OG 11.04.2017/30035: https://www.resmigazete.gov.tr/eskiler/2017/04/20170411-3.htm (accessed 2026-11-20)
- [S5] Regulation on Activity Certificates for Access and Hosting Providers, OG 24.10.2007/26680: https://www.resmigazete.gov.tr/eskiler/2007/10/20071024-12.htm ; consolidated index https://www.mevzuat.gov.tr/anasayfa/MevzuatFihristDetayIframe?MevzuatTur=7&MevzuatNo=11679&MevzuatTertip=5 (accessed 2026-11-20)

---

## Türkçe

# BTK / 5651 Yükümlülükleri: Bölüm Girişi

> Nötr şablondur, hukuki görüş değildir. Aşağıdaki her hukuki tespitin yanında kaynak URL'si ve erişim tarihi vardır. Birincil kaynaktan doğrulanamayan her nokta **DOĞRULANMADI / UNVERIFIED** olarak işaretlidir.

## 1. Bu bölüm neden var?

5651 sayılı Kanun yükümlülükleri sektöre göre değil **role** göre dağıtır. Bir şirket aynı anda birden fazla rol taşıyabilir:

| Rol (5651 md. 2) | Tipik şirket durumu | Doküman |
|---|---|---|
| İçerik sağlayıcı (md. 2/1-f) | Şirket web sitesi, blog, uygulama içeriği | [yer-saglayici.md](yer-saglayici.md) §3'te kısaca (tanıtıcı bilgiler) |
| Yer sağlayıcı (md. 2/1-m) | Üçüncü kişi içeriğini veya hizmetini barındırma: müşterinin içerik yayımladığı SaaS, forum, müşteri alt siteleri, hosting/bayilik | [yer-saglayici.md](yer-saglayici.md) |
| Toplu kullanım sağlayıcı (md. 2/1-i) | Ofis, misafir ya da kiracı Wi-Fi'ı, kafe, otel, ortak ofis, kuluçka merkezi | [toplu-kullanim-saglayici.md](toplu-kullanim-saglayici.md) |
| Erişim sağlayıcı (md. 2/1-e) | İSS ve işletmeciler; sıradan bir şirket nadiren | [erisim-saglayici.md](erisim-saglayici.md) |
| Sosyal ağ sağlayıcı (md. 2/1-s) | Kullanıcıların sosyal etkileşim amacıyla içerik oluşturup paylaştığı platformlar | [erisim-saglayici.md](erisim-saglayici.md) §4 |

Destek dokümanları: [btk-dokumantasyon.md](btk-dokumantasyon.md) (portallar, formlar, iletişim noktaları, siber güvenlik kurumları) ve [log-kontrol-listesi.md](log-kontrol-listesi.md) (5651 log şartı ↔ KVKK ilkesi kontrol listesi).

## 2. Önemli değişiklik: 5651'in yetkili kurumu artık BTK değil (31.07.2026'dan beri)

7590 sayılı Kanun (kabul 24.07.2026, RG 31.07.2026, sayı 33326) Bilgi Teknolojileri ve İletişim Kurumunun ("Kurum") 5651 kapsamındaki yetkilerini **Siber Güvenlik Başkanlığına** ("Başkanlık") devretti. 7590 md. 27/2-a, 5651 md. 2/1'e "v) Başkanlık: Siber Güvenlik Başkanlığını," tanımını ekledi ve "Başkan" tanımını Siber Güvenlik Başkanı olarak değiştirdi [S1][S2].

Geçiş hükmü (7590 md. 26 ile 7545 sayılı Kanuna eklenen Geçici Madde 2/1): Siber Güvenlik Başkanlığı ikincil düzenlemelerini çıkarana kadar **mevcut düzenlemelerin uygulanmasına devam olunur**; bu düzenlemelerdeki BTK'ya yapılan atıflar Siber Güvenlik Başkanlığına yapılmış sayılır [S1].

Pratik sonuçlar:

- Bu bölümde anılan 2007 ve 2017 yönetmelikleri hâlâ uygulanan metinlerdir. İçlerindeki "Kurum"/"BTK" ibaresi "Siber Güvenlik Başkanlığı" olarak okunur.
- Aydınlatma metinlerinde, sözleşmelerde ve iç belgelerde "Siber Güvenlik Başkanlığı" (isteğe bağlı olarak "eski adıyla BTK yetkisi") yazılmalıdır.
- Siber Güvenlik Başkanlığının 31.07.2026 sonrasında yeni bir 5651 yönetmeliği ya da taslağı yayımlayıp yayımlamadığı: 2026-11-20 aramalarında bulunamadı. Hiç olmadığı **DOĞRULANMADI / UNVERIFIED**.
- Klasör adı bulunabilirlik için `13-btk-5651` olarak kaldı. BTK, 5809 sayılı Kanun kapsamındaki işletmeci yetkilendirmesini ve bazı eski portalları yürütmeye devam ediyor (bkz. [btk-dokumantasyon.md](btk-dokumantasyon.md)).

## 3. 5651'in KVKK ile ilişkisi

5651 logları kişisel veri içerir (IP, MAC adresi, port, zaman bilgisi, bazen abone kimliği). İki rejim şöyle kesişir:

| Soru | 5651 | KVKK | Sonuç kuralı |
|---|---|---|---|
| Logu tutmanın hukuki sebebi | Saklama kanuni yükümlülüktür (ör. 5651 md. 5/3, 6/1-b, 7/2) [S2] | "Kanunlarda açıkça öngörülmesi" (md. 5/2-a) veya hukuki yükümlülük (md. 5/2-ç) hâlinde rıza aranmaz [S3] | 5651 logları için açık rıza **istenmez**; kanun dayanak gösterilir. |
| Hangi alanlar | Yönetmelik alanları sayar (ör. toplu kullanım için 2017 Yönetmeliği md. 3/1-e) [S4] | Veri, amaçla "bağlantılı, sınırlı ve ölçülü" olmalı (md. 4/2-ç) [S3] | Sayılan alanlar tutulur. Fazlası (DNS sorgusu, URL, T.C. kimlik no) ayrı hukuki sebep ve ölçülülük analizi ister. |
| Ne kadar süre | Sabit süre ya da aralık: toplu kullanım 2 yıl; yer sağlayıcı 1-2 yıl; erişim sağlayıcı 6 ay-2 yıl [S2][S4] | "İlgili mevzuatta öngörülen veya işlendikleri amaç için gerekli olan süre kadar" saklama (md. 4/2-d), ardından silme/yok etme/anonimleştirme (md. 7) [S3] | Saklama süresi = 5651 süresi. Süre dolunca ilk periyodik imhada imha edilir (bkz. [../04-veri-saklama-ve-imha/](../04-veri-saklama-ve-imha/)). |
| Güvenlik | Yer ve erişim sağlayıcı trafik bilgisinde doğruluk, bütünlük, gizlilik (md. 5/3, 6/1-b) [S2] | Uygun güvenlik düzeyi için teknik ve idari tedbirler (md. 12/1); veri işleyenle müşterek sorumluluk (md. 12/2) [S3] | Aynı kontroller iki rejimi de karşılar: erişim kontrolü, bütünlük değeri, erişim kaydı. |
| Mercilere verme | Mahkeme/savcılık talepleri; Siber Güvenlik Başkanlığı talepleri | Suçun önlenmesi veya soruşturulması için gerekli ve orantılı işlemede md. 10, 11 ve 16 uygulanmaz (md. 28/2-a) [S3] | Yalnız yazılı talebin kapsadığı kayıt verilir; talep defteri tutulur. |

**Asıl gerilim: log saklama ve veri minimizasyonu.** 5651 saklamayı zorunlu kılar, KVKK gerekenden fazlasını yasaklar. Savunulabilir duruş şudur: 5651 alan setinin **tam kendisi**, 5651 süresinin **tam kendisi** kadar, adı belirli rollerle sınırlı erişimle tutulur ve takvime göre imha edilir. "Her şeyi, sonsuza kadar, ne olur ne olmaz" diye loglamak KVKK ihlalidir ve 5651 bunu haklı kılmaz.

## 4. Wiki'nin diğer bölümleriyle tutarlılık notları

- [../05-teknik-tedbirler/log-yonetimi.md](../05-teknik-tedbirler/log-yonetimi.md) §7 tablosu "5651 (yer sağlayıcıysak): 2 yıl ila 10 yıl" diyor. Burada incelenen 5651 aralıklarında yer, erişim ve toplu kullanım logları için **üst sınır iki yıldır** [S2][S4]. 10 yıl rakamının 5651'de dayanağı yoktur.
- [../04-veri-saklama-ve-imha/saklama-sureleri-tablosu.md](../04-veri-saklama-ve-imha/saklama-sureleri-tablosu.md) 28. satır 5651 md. 5 için web sunucu logunda "6 ay - 2 yıl" diyor. 2014 değişikliğinden beri yer sağlayıcı için kanuni alt sınır **bir yıldır** (5651 md. 5/3). Altı ay rakamı güncellenmemiş 2007 yönetmeliklerinden gelir [S2][S5].

Bunlar o dokümanlarda yapılacak düzeltmeler için öneridir; bu bölüm onları değiştirmez.

## 5. Bölüm içeriği

| Doküman | Kapsam |
|---|---|
| [yer-saglayici.md](yer-saglayici.md) | Yer sağlayıcı: tanım, bildirim, trafik bilgisi, içerik çıkarma süreleri, cezalar |
| [toplu-kullanim-saglayici.md](toplu-kullanim-saglayici.md) | Toplu kullanım sağlayıcı: ticari/ticari olmayan, izin belgesi, log seti, bütünlük, filtre, cezalar |
| [erisim-saglayici.md](erisim-saglayici.md) | Erişim sağlayıcı temelleri; sosyal ağ sağlayıcı kuralları (7253/7418/7578) şirketleri ilgilendirdiği ölçüde |
| [btk-dokumantasyon.md](btk-dokumantasyon.md) | Portallar, formlar, belgeler, iletişim noktaları; Siber Güvenlik Başkanlığı, USOM, 7545; sektörel siber güvenlik yönetmeliği |
| [log-kontrol-listesi.md](log-kontrol-listesi.md) | 5651 log şartlarını KVKK ilkelerine eşleyen kontrol listesi |

## 6. Kaynaklar

- [S1] 7590 sayılı Kanun, RG 31.07.2026/33326: https://www.resmigazete.gov.tr/eskiler/2026/07/20260731-2.htm (erişim 2026-11-20)
- [S2] 5651 sayılı Kanun, konsolide metin (7590 işlenmiş): https://www.mevzuat.gov.tr/MevzuatMetin/1.5.5651.pdf (erişim 2026-11-20)
- [S3] 6698 sayılı KVKK, konsolide: https://www.mevzuat.gov.tr/MevzuatMetin/1.5.6698.pdf (erişim 2026-11-20)
- [S4] İnternet Toplu Kullanım Sağlayıcıları Hakkında Yönetmelik, RG 11.04.2017/30035: https://www.resmigazete.gov.tr/eskiler/2017/04/20170411-3.htm (erişim 2026-11-20)
- [S5] Erişim Sağlayıcılara ve Yer Sağlayıcılara Faaliyet Belgesi Verilmesine İlişkin Usul ve Esaslar Hakkında Yönetmelik, RG 24.10.2007/26680: https://www.resmigazete.gov.tr/eskiler/2007/10/20071024-12.htm ; konsolide fihrist https://www.mevzuat.gov.tr/anasayfa/MevzuatFihristDetayIframe?MevzuatTur=7&MevzuatNo=11679&MevzuatTertip=5 (erişim 2026-11-20)
