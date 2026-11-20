---
Doküman / Document: 14 - Siber Güvenlik (Bölüm Girişi) / 14 - Cyber Security (Section Introduction)
Bölüm / Section: 14-siber-guvenlik
Sahip / Owner: Bilgi Güvenliği Müdürü (CISO) + KVKK Sorumlusu / Chief Information Security Officer (CISO) + KVKK Officer
Onaylayan / Approved by: Hukuk Müdürü + KVKK Komitesi / Head of Legal + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-11-20
Gözden Geçirme / Review: Üç aylık (ikincil mevzuat yoğun çıkıyor) + tetiklenmiş / Quarterly (secondary legislation is being issued) + triggered
İlgili Mevzuat / Legal Reference: Siber Güvenlik Kanunu No. 7545 (RG 19.03.2025/32846, as amended by Law No. 7590, RG 31.07.2026/33326); Presidential Decree (CBK) No. 177 (RG 08.01.2025/32776) as amended by CBK 183, 192 and 203; Presidential Circular 2019/12 (RG 06.07.2019/30823); SOME Communiqué (RG 11.11.2013/28818); KVKK Art. 12(5) + Board Decision 2019/10
---

## English

# 14 - Cyber Security

> **Status note (2026-11-20):** Law No. 7545 is in force, but most of its secondary legislation is **not yet in force**. On 18.11.2026 the Cyber Security Presidency opened two draft regulations for comment (deadline 03.12.2026). Texts marked "draft" in this section are **not binding law**. Re-check this section once the final texts are published in the Official Gazette.
>
> This section is a neutral compliance template. It is not legal advice.

## 1. Purpose of the Section

The KVKK wiki covers personal data. Cyber-security law in Türkiye is a **separate, parallel regime** with its own authority, its own reporting duties and its own sanctions. A single incident (for example, ransomware that also exfiltrates customer data) can trigger both regimes at the same time. This section maps the cyber-security regime and connects it to the KVKK breach workflow in [08-ihlal-yonetimi](../08-ihlal-yonetimi/).

## 2. Who Regulates What

| Body | Legal basis | Role relevant to a company | Source (accessed 2026-11-20) |
|------|-------------|----------------------------|------------------------------|
| **Siber Güvenlik Başkanlığı (SGB, Cyber Security Presidency)** | CBK 177 (RG 08.01.2025/32776); Law 7545 Arts. 5-8, 18 | Central cyber-security authority attached to the Presidency. Critical infrastructure, SOME structure, incident notifications, audits, certification and authorisation of cyber-security products, services and companies, sanctions. Since CBK 192 also digital government and public-sector AI. | [CBK 177 consolidated](https://www.mevzuat.gov.tr/mevzuat?MevzuatNo=177&MevzuatTur=19&MevzuatTertip=5); [Law 7545 consolidated](https://www.mevzuat.gov.tr/mevzuat?MevzuatNo=7545&MevzuatTur=1&MevzuatTertip=5) |
| **Siber Güvenlik Kurulu (Cyber Security Board)** | Law 7545 Art. 9 | Chaired by the President. Sets policy and strategy, determines critical infrastructure sectors. On 05.05.2026 it designated 15 critical infrastructure sectors (see §4). | [SGB news 05.05.2026](https://siberguvenlik.gov.tr/haberler/detay/siber_guvenlik_kurulu_toplandi) |
| **USOM (National Cyber Incident Response Centre)** | SOME Communiqué (RG 11.11.2013/28818); Law 7545 Prov. Art. 1 | Formerly run by BTK. Now operates under SGB. usom.gov.tr states that CVE requests, tip-offs, malicious-link lists and security notices continue on siberguvenlik.gov.tr; .txt list sharing ended on 01.06.2026. | [usom.gov.tr notice](https://www.usom.gov.tr) |
| **Sectoral SOME and Corporate SOME (incident response teams)** | SOME Communiqué Arts. 5, 7; SGB FAQ | Sectoral SOMEs sit in sector regulators; organisations in a sector run a Corporate SOME under the sectoral SOME. Joining the SOME Communication Platform (SİP, sip.siberguvenlik.gov.tr) is mandatory for all public bodies and all organisations operating in critical sectors (SGB FAQ). | [SGB FAQ](https://siberguvenlik.gov.tr/sss) |
| **BTK (Information and Communication Technologies Authority)** | Law 5809; Law 7545 Prov. Art. 1; Law 7590 Art. 27 | Remains the electronic-communications regulator. Assets used exclusively for national cyber-security activities were transferred from BTK to SGB (within six months of 19.03.2025). By Law 7590 (in force 31.07.2026) the 5651 internet-law functions, the domain-name policy power (new 5809 Art. 60/A) and the lawful-interception technical function (2559 Add. Art. 7) were moved from BTK to SGB. | [Law 7590, RG 31.07.2026](https://www.resmigazete.gov.tr/eskiler/2026/07/20260731-2.htm) |
| **BTK Siber Güvenlik Dairesi Başkanlığı** | - | **DOĞRULANMADI / UNVERIFIED** whether this department still exists or under what name after the 2025-2026 transfers. Do not use it as a reporting channel without checking. | - |
| **CBDDO (Presidency Digital Transformation Office)** | CBK 1 Arts. 527-527/B | **Abolished** by CBK 183 (RG 28.03.2025/32855). Its cyber-security duties, the Information and Communication Security Guide and BİGDES moved to SGB (SGB FAQ). cbddo.gov.tr did not respond on 2026-11-20. | [CBK 1 consolidated](https://www.mevzuat.gov.tr/mevzuat?MevzuatNo=1&MevzuatTur=19&MevzuatTertip=5); [SGB FAQ](https://siberguvenlik.gov.tr/sss) |
| **Emniyet Genel Müdürlüğü Siber Suçlarla Mücadele Daire Başkanlığı (Police cybercrime department)** | Criminal procedure; SOME Communiqué Art. 5(5) | Criminal investigation of cyber crime. Where a SOME finds signs of a crime it must notify the competent authorities without delay (SOME Communiqué Art. 5(5)). The department's own reporting channel was **not confirmed** from an official source (UNVERIFIED); file through the public prosecutor or police. | [SOME Communiqué, RG 11.11.2013/28818](https://www.turmob.org.tr/arsiv/mbs/resmigazete/28818-28818-2.docx) |
| **BDDK (banking)** | BSEBY, RG 15.03.2020/31069 | Sectoral SOME for banks; annual pentest; immediate notification of serious incidents. | [BSEBY consolidated](https://www.mevzuat.gov.tr/anasayfa/MevzuatFihristDetayIframe?MevzuatNo=34360&MevzuatTertip=5&MevzuatTur=7) |
| **SPK (capital markets)** | Communiqué VII-128.10, RG 13.03.2025/32840 | Annual pentest with report to SPK; immediate incident notification. | [RG 13.03.2025](https://www.resmigazete.gov.tr/eskiler/2025/03/20250313-8.htm) |
| **EPDK (energy)** | Enerji Sektöründe Siber Güvenlik Yetkinlik Modeli Yönetmeliği (RG 06.06.2023/32213, per secondary sources) | Energy-sector cyber maturity model. Details **UNVERIFIED** in primary text. | see [sizma-testleri.md](sizma-testleri.md) |
| **KVKK Kurulu (Personal Data Protection Board)** | KVKK Art. 12(5); Decision 2019/10 | Personal data breach notification within 72 hours. | [08-ihlal-yonetimi/72-saat-bildirim.md](../08-ihlal-yonetimi/72-saat-bildirim.md) |

## 3. How Cyber Law Touches KVKK Breach Notification

1. **Two separate duties, two recipients.** A personal data breach goes to the KVKK Board within 72 hours (KVKK Art. 12(5), Decision 2019/10). A cyber incident or vulnerability detected in the area where a party provides services goes to SGB "without delay" (Law 7545 Art. 7(1)(b)). Reporting to one does **not** discharge the other.
2. **Different thresholds.** KVKK is triggered by personal data. Law 7545 is triggered by a "cyber incident", defined as a breach of confidentiality, integrity or availability of IT systems or data (Art. 3(1)(g)), so it also covers incidents with no personal data (DDoS, OT outage).
3. **Different clocks.** The law itself sets no hour figure for SGB ("gecikmeksizin", without delay). The 18.11.2026 **draft** Cyber Resilience Regulation proposes 12 hours (initial), 72 hours (update) and one month (detailed report) for organisations obliged to have a Corporate SOME (draft Art. 33). See [olay-bildirim-matrisi.md](olay-bildirim-matrisi.md).
4. **Personal data inside SGB processes.** Law 7545 Art. 6(2) requires SGB to process personal data lawfully and to delete, destroy or anonymise it once no longer needed. Data obtained under Art. 6(1)(ç) may be worked on for at most two years and then destroyed.
5. **Criminal exposure linked to leaks.** Law 7545 Art. 16(4) criminalises making previously leaked personal data available, sharing or selling it (3-5 years' imprisonment). Art. 16(5) criminalises knowingly creating or spreading false claims of a data leak to cause public panic or to target institutions or people (2-5 years). Breach communications must therefore be accurate.
6. **One incident record.** Keep one incident file feeding both notifications so that facts, timestamps and scope stay consistent between the KVKK form and the SGB/sectoral SOME notification.

## 4. Critical Infrastructure Sectors (Cyber Security Board, 05.05.2026)

Digital Infrastructures, Digital Services, Electronic Communications, Energy, Finance, Food and Agriculture, Manufacturing Industry, Public Services, Media and Crisis Communication, Post and Cargo, Health, Defence Industry, Water Management, Transport, Space. Source: [SGB news, 05.05.2026](https://siberguvenlik.gov.tr/haberler/detay/siber_guvenlik_kurulu_toplandi). Being in a listed sector does not by itself make an organisation a "critical infrastructure"; under the draft regulation SGB and sectoral SOMEs designate individual organisations (draft Arts. 6, 22).

## 5. File Index

| # | File | Topic |
|---|------|-------|
| 1 | `README.md` | This file: authorities, KVKK interplay |
| 2 | [siber-guvenlik-kanunu-7545.md](siber-guvenlik-kanunu-7545.md) | Law 7545: scope, duties, reporting, localisation, sanctions, secondary legislation |
| 3 | [siber-guvenlik-baskanligi.md](siber-guvenlik-baskanligi.md) | SGB: mandate, structure, published rules and guides, certification |
| 4 | [sizma-testleri.md](sizma-testleri.md) | Penetration testing rules + procurement checklist |
| 5 | [siber-sirket-yonetmelikleri.md](siber-sirket-yonetmelikleri.md) | Duties of cyber-security vendors and of ordinary companies |
| 6 | [olay-bildirim-matrisi.md](olay-bildirim-matrisi.md) | Incident → recipient → deadline → legal basis |

## 6. Open Items (UNVERIFIED)

- Current status and name of BTK's former Siber Güvenlik Dairesi Başkanlığı.
- An official reporting channel of the Police Cybercrime Department.
- Final text and publication date of the Cyber Resilience Regulation and the Audit Regulation (drafts only as of 2026-11-20).
- Any SGB certification or authorisation regulation for cyber-security companies (none found, not even a draft).

## 7. Version History

| Version | Date | Change | Approval |
|---------|------|--------|----------|
| 1.0 | 2026-11-20 | First release | KVKK Committee |

---

## Türkçe

# 14 - Siber Güvenlik

> **Durum notu (2026-11-20):** 7545 sayılı Kanun yürürlüktedir; ancak ikincil mevzuatının büyük kısmı **henüz yürürlükte değildir**. Siber Güvenlik Başkanlığı 18.11.2026'da iki yönetmelik taslağını görüşe açmıştır (son gün 03.12.2026). Bu bölümde "taslak" olarak işaretlenen metinler **bağlayıcı hukuk değildir**. Nihai metinler Resmî Gazete'de yayımlanınca bölüm yeniden gözden geçirilmelidir.
>
> Bu bölüm tarafsız bir uyum şablonudur, hukuki görüş değildir.

## 1. Bölümün Amacı

KVKK wiki'si kişisel verileri ele alır. Türkiye'de siber güvenlik hukuku ise kendi otoritesi, kendi bildirim yükümlülükleri ve kendi yaptırımları olan **ayrı ve paralel bir rejimdir**. Tek bir olay (örneğin müşteri verisini de dışarı çıkaran bir fidye yazılımı) iki rejimi aynı anda tetikleyebilir. Bu bölüm siber güvenlik rejimini haritalar ve [08-ihlal-yonetimi](../08-ihlal-yonetimi/) altındaki KVKK ihlal akışına bağlar.

## 2. Kim Neyi Düzenliyor

| Kurum | Hukuki dayanak | Şirket açısından rolü | Kaynak (erişim 2026-11-20) |
|-------|----------------|------------------------|----------------------------|
| **Siber Güvenlik Başkanlığı (SGB)** | 177 sayılı CBK (RG 08.01.2025/32776); 7545 sayılı Kanun m.5-8, 18 | Cumhurbaşkanlığına bağlı merkezi siber güvenlik otoritesi. Kritik altyapılar, SOME yapısı, olay bildirimleri, denetim, siber güvenlik ürün, hizmet ve şirketlerinin sertifikasyon ve yetkilendirmesi, yaptırımlar. 192 sayılı CBK'den beri dijital devlet ve kamuda yapay zekâ da görev alanında. | [177 sayılı CBK güncel metin](https://www.mevzuat.gov.tr/mevzuat?MevzuatNo=177&MevzuatTur=19&MevzuatTertip=5); [7545 güncel metin](https://www.mevzuat.gov.tr/mevzuat?MevzuatNo=7545&MevzuatTur=1&MevzuatTertip=5) |
| **Siber Güvenlik Kurulu** | 7545 m.9 | Cumhurbaşkanı başkanlığında. Politika ve strateji belirler, kritik altyapı sektörlerini belirler. 05.05.2026'da 15 kritik altyapı sektörü belirledi (bkz. §4). | [SGB haberi 05.05.2026](https://siberguvenlik.gov.tr/haberler/detay/siber_guvenlik_kurulu_toplandi) |
| **USOM (Ulusal Siber Olaylara Müdahale Merkezi)** | SOME Tebliği (RG 11.11.2013/28818); 7545 geçici m.1 | Önceden BTK bünyesindeydi, artık SGB altında. usom.gov.tr'deki duyuruya göre CVE başvuruları, ihbarlar, zararlı bağlantı listeleri ve güvenlik bildirimleri siberguvenlik.gov.tr üzerinden sürüyor; .txt liste paylaşımı 01.06.2026'da sona erdi. | [usom.gov.tr duyurusu](https://www.usom.gov.tr) |
| **Sektörel SOME ve Kurumsal SOME** | SOME Tebliği m.5, 7; SGB SSS | Sektörel SOME'ler sektör düzenleyicilerinde bulunur; sektördeki kuruluşlar sektörel SOME himayesinde kurumsal SOME işletir. SOME İletişim Platformu'na (SİP, sip.siberguvenlik.gov.tr) üyelik tüm kamu kuruluşları ile kritik sektörlerde faaliyet gösteren tüm kuruluşlar için zorunludur (SGB SSS). | [SGB SSS](https://siberguvenlik.gov.tr/sss) |
| **BTK** | 5809 sayılı Kanun; 7545 geçici m.1; 7590 m.27 | Elektronik haberleşme düzenleyicisi olarak devam ediyor. Münhasıran ulusal siber güvenlik faaliyetinde kullanılan varlıklar 19.03.2025'ten itibaren altı ay içinde SGB'ye devredildi. 7590 sayılı Kanunla (yürürlük 31.07.2026) 5651 sayılı Kanundaki görevler, alan adı politikası yetkisi (5809 yeni m.60/A) ve yasal dinlemenin teknik icrası (2559 ek m.7) BTK'dan SGB'ye geçti. | [7590 sayılı Kanun, RG 31.07.2026](https://www.resmigazete.gov.tr/eskiler/2026/07/20260731-2.htm) |
| **BTK Siber Güvenlik Dairesi Başkanlığı** | - | 2025-2026 devirlerinden sonra bu dairenin hâlâ var olup olmadığı ya da adı **DOĞRULANMADI / UNVERIFIED**. Kontrol edilmeden bildirim kanalı olarak kullanılmamalı. | - |
| **CBDDO (Cumhurbaşkanlığı Dijital Dönüşüm Ofisi)** | 1 sayılı CBK m.527-527/B | 183 sayılı CBK ile (RG 28.03.2025/32855) **kaldırıldı**. Siber güvenlik görevleri, Bilgi ve İletişim Güvenliği Rehberi ve BİGDES SGB'ye geçti (SGB SSS). cbddo.gov.tr 2026-11-20'de yanıt vermedi. | [1 sayılı CBK güncel metin](https://www.mevzuat.gov.tr/mevzuat?MevzuatNo=1&MevzuatTur=19&MevzuatTertip=5); [SGB SSS](https://siberguvenlik.gov.tr/sss) |
| **Emniyet Genel Müdürlüğü Siber Suçlarla Mücadele Daire Başkanlığı** | Ceza muhakemesi; SOME Tebliği m.5(5) | Siber suçların adli soruşturması. SOME, müdahale sırasında suç izlenimi veren bir durumla karşılaşırsa yetkili makamlara gecikmeksizin bildirir (SOME Tebliği m.5(5)). Dairenin kendi bildirim kanalı resmî kaynaktan **doğrulanamadı** (UNVERIFIED); başvuru Cumhuriyet başsavcılığı veya kolluk üzerinden yapılmalı. | [SOME Tebliği, RG 11.11.2013/28818](https://www.turmob.org.tr/arsiv/mbs/resmigazete/28818-28818-2.docx) |
| **BDDK (bankacılık)** | BSEBY, RG 15.03.2020/31069 | Bankalar için sektörel SOME; yıllık sızma testi; ciddi olaylarda derhal bildirim. | [BSEBY güncel metin](https://www.mevzuat.gov.tr/anasayfa/MevzuatFihristDetayIframe?MevzuatNo=34360&MevzuatTertip=5&MevzuatTur=7) |
| **SPK (sermaye piyasası)** | VII-128.10 sayılı Tebliğ, RG 13.03.2025/32840 | Yıllık sızma testi ve raporun SPK'ya gönderilmesi; olayda derhal bildirim. | [RG 13.03.2025](https://www.resmigazete.gov.tr/eskiler/2025/03/20250313-8.htm) |
| **EPDK (enerji)** | Enerji Sektöründe Siber Güvenlik Yetkinlik Modeli Yönetmeliği (ikincil kaynaklara göre RG 06.06.2023/32213) | Enerji sektörü siber olgunluk modeli. Ayrıntılar birincil metinden **DOĞRULANMADI**. | bkz. [sizma-testleri.md](sizma-testleri.md) |
| **KVKK Kurulu** | KVKK m.12(5); 2019/10 sayılı Karar | Kişisel veri ihlalinde 72 saat içinde bildirim. | [08-ihlal-yonetimi/72-saat-bildirim.md](../08-ihlal-yonetimi/72-saat-bildirim.md) |

## 3. Siber Güvenlik Hukuku KVKK İhlal Bildirimine Nerede Değiyor

1. **İki ayrı yükümlülük, iki ayrı muhatap.** Kişisel veri ihlali 72 saat içinde KVKK Kurulu'na bildirilir (KVKK m.12(5), 2019/10 sayılı Karar). Hizmet sunulan alanda tespit edilen siber olay veya zafiyet SGB'ye "gecikmeksizin" bildirilir (7545 m.7(1)(b)). Birine bildirim yapmak diğerini **karşılamaz**.
2. **Farklı eşikler.** KVKK kişisel veriyle tetiklenir. 7545 ise bilişim sistemlerinin veya verinin gizlilik, bütünlük veya erişilebilirliğinin ihlali olarak tanımlanan "siber olay" ile tetiklenir (m.3(1)(g)); kişisel veri içermeyen olayları (DDoS, OT kesintisi) da kapsar.
3. **Farklı süreler.** Kanun SGB bildirimi için saat öngörmez ("gecikmeksizin"). 18.11.2026 tarihli **taslak** Siber Dayanıklılık Yönetmeliği, kurumsal SOME kurmakla yükümlü kuruluşlar için 12 saat (ilk bildirim), 72 saat (güncelleme) ve bir ay (ayrıntılı rapor) önermektedir (taslak m.33). Bkz. [olay-bildirim-matrisi.md](olay-bildirim-matrisi.md).
4. **SGB süreçlerinde kişisel veri.** 7545 m.6(2), SGB'nin kişisel verileri hukuka uygun işlemesini ve gerek kalmadığında silmesini, yok etmesini veya anonimleştirmesini öngörür. m.6(1)(ç) kapsamında alınan bilgiler en fazla iki yıl çalışmaya konu edilir, sonra imha edilir.
5. **Sızıntıyla bağlantılı cezai risk.** 7545 m.16(4), daha önce sızan kişisel verileri erişime açmayı, paylaşmayı veya satışa çıkarmayı suç sayar (3-5 yıl hapis). m.16(5), halkta panik yaratmak veya kurum ya da kişileri hedef göstermek amacıyla bilerek gerçeğe aykırı veri sızıntısı içeriği oluşturmayı veya yaymayı suç sayar (2-5 yıl). İhlal iletişimi bu nedenle doğru olmalıdır.
6. **Tek olay dosyası.** KVKK formu ile SGB/sektörel SOME bildirimi arasında olgu, zaman damgası ve kapsam tutarlı kalsın diye iki bildirimi de besleyen tek bir olay dosyası tutulmalıdır.

## 4. Kritik Altyapı Sektörleri (Siber Güvenlik Kurulu, 05.05.2026)

Dijital Altyapılar, Dijital Hizmetler, Elektronik Haberleşme, Enerji, Finans, Gıda ve Tarım, İmalat Sanayii, Kamu Hizmetleri, Medya ve Kriz İletişimi, Posta ve Kargo, Sağlık, Savunma Sanayii, Su Yönetimi, Ulaştırma, Uzay. Kaynak: [SGB haberi, 05.05.2026](https://siberguvenlik.gov.tr/haberler/detay/siber_guvenlik_kurulu_toplandi). Listedeki bir sektörde bulunmak kuruluşu tek başına "kritik altyapı" yapmaz; taslak yönetmeliğe göre kuruluşları tek tek SGB ve sektörel SOME'ler belirler (taslak m.6, 22).

## 5. Dosya Dizini

| # | Dosya | Konu |
|---|-------|------|
| 1 | `README.md` | Bu dosya: kurumlar, KVKK ile ilişki |
| 2 | [siber-guvenlik-kanunu-7545.md](siber-guvenlik-kanunu-7545.md) | 7545 sayılı Kanun: kapsam, yükümlülükler, bildirim, yerelleştirme, yaptırımlar, ikincil mevzuat |
| 3 | [siber-guvenlik-baskanligi.md](siber-guvenlik-baskanligi.md) | SGB: görev, teşkilat, yayımlanan düzenleme ve rehberler, sertifikasyon |
| 4 | [sizma-testleri.md](sizma-testleri.md) | Sızma testi kuralları + satın alma kontrol listesi |
| 5 | [siber-sirket-yonetmelikleri.md](siber-sirket-yonetmelikleri.md) | Siber güvenlik şirketlerinin ve sıradan şirketlerin yükümlülükleri |
| 6 | [olay-bildirim-matrisi.md](olay-bildirim-matrisi.md) | Olay → muhatap → süre → hukuki dayanak |

## 6. Açık Kalemler (DOĞRULANMADI / UNVERIFIED)

- BTK'nın eski Siber Güvenlik Dairesi Başkanlığı'nın bugünkü durumu ve adı.
- Emniyet Siber Suçlarla Mücadele Daire Başkanlığı'nın resmî bildirim kanalı.
- Siber Dayanıklılık Yönetmeliği ile Denetim Yönetmeliği'nin nihai metni ve yayım tarihi (2026-11-20 itibarıyla yalnız taslak).
- Siber güvenlik şirketlerine yönelik bir SGB sertifikasyon veya yetkilendirme düzenlemesi (taslağı dahi bulunamadı).

## 7. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-11-20 | İlk yayım | KVKK Komitesi |
