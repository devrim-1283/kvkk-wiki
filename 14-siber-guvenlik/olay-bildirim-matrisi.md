---
Doküman / Document: Siber Olay Bildirim Matrisi / Cyber Incident Notification Matrix
Bölüm / Section: 14-siber-guvenlik
Sahip / Owner: Bilgi Güvenliği Müdürü (CISO) + KVKK Sorumlusu / CISO + KVKK Officer
Onaylayan / Approved by: Hukuk Müdürü + KVKK Komitesi / Head of Legal + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-11-20
Gözden Geçirme / Review: Üç aylık + her yeni yönetmelikte / Quarterly + on every new regulation
İlgili Mevzuat / Legal Reference: KVKK Art. 12(5); KVKK Board Decision 2019/10; Law No. 7545 Arts. 7(1)(b), 16; Law No. 5809 Art. 60/A; SOME Communiqué (RG 11.11.2013/28818) Arts. 5, 7; BDDK BSEBY Art. 18; SPK VII-128.10 Art. 24; Information and Communication Security Guide v1.1 §3.1.10; draft Cyber Resilience Regulation Arts. 14, 27, 33 (not in force)
---

## English

# Cyber Incident Notification Matrix

> Sources accessed 2026-11-20. Not legal advice. Rows marked **DRAFT** come from the SGB draft Cyber Resilience Regulation (18.11.2026) and are **not in force**. Several duties can apply to one incident at the same time: work down the whole table.

## 1. Matrix

| # | Incident type | Notify whom | Deadline | Legal basis | Status |
|---|---------------|-------------|----------|-------------|--------|
| 1 | Personal data breach (unauthorised access, disclosure, loss, alteration) in any sector | **KVKK Board** (ihlalbildirim.kvkk.gov.tr / KEP) | **Without undue delay, at the latest 72 hours** from awareness | KVKK Art. 12(5); Board Decision 2019/10 (24.01.2019) | In force. See [72-saat-bildirim.md](../08-ihlal-yonetimi/72-saat-bildirim.md) |
| 2 | Same breach: affected data subjects | **Data subjects** directly, or by appropriate means if unreachable | Within a reasonable time, as soon as possible | KVKK Art. 12(5); Decision 2019/10 | In force |
| 3 | Any vulnerability or cyber incident detected in the area where the party provides services (any party under Law 7545) | **SGB** (siberguvenlik.gov.tr/ihbar; KEP siberguvenlikbaskanligi@hs01.kep.tr) | **Without delay** ("gecikmeksizin"); no hour figure in the Law | Law 7545 Art. 7(1)(b); fine TRY 1M-10M (Art. 16(10)) | In force |
| 4 | Cyber incident at an organisation with a Corporate SOME | **USOM (now SGB)** + **sectoral SOME** | Without delay | SOME Communiqué Art. 5(6) (applied via Law 7545 Prov. Art. 1(6)) | In force |
| 5 | Cyber incident in a sectoral SOME's sector (sectoral SOME's own duty) | **USOM (now SGB)** | Without delay | SOME Communiqué Art. 7(2) | In force |
| 6 | Suspected crime found during incident response | **Public prosecutor / law enforcement** (incl. Police Cybercrime Department) + **USOM (SGB)** | Without delay | SOME Communiqué Art. 5(5); draft Art. 24(1)(e) | In force (Communiqué) |
| 7 | Public body or critical-infrastructure operator under Circular 2019/12: incident response report | **Top management, SGB, and sectoral SOME** if any | Per criteria set by SGB (Guide does not state hours) | Guide v1.1 measure 3.1.10.5 | Applied |
| 8 | Bank: incident escalates into a crisis, data leak or disclosure, BCP or secondary site activated | **Sectoral SOME (BDDK)**; customers after bank's assessment if sensitive or personal data leaked | **Immediately** ("derhal") | BSEBY Art. 18(5); also Art. 18(1) reporting to BDDK and Art. 18(6) root-cause report to sectoral SOME | In force |
| 9 | SPK-regulated institution: incident with potential to disrupt critical operations or cause a data leak | **SPK**, customers and other relevant bodies | **Immediately** | VII-128.10 Art. 24(4) | In force |
| 10 | SPK-regulated: incident affecting critical systems or sensitive data, after response | **SPK**: incident response report | **Immediately** after preparation | VII-128.10 Art. 24(5) | In force |
| 11 | Energy-sector incident | EPDK / sectoral SOME | **DOĞRULANMADI / UNVERIFIED** | Enerji Sektöründe Siber Güvenlik Yetkinlik Modeli Yönetmeliği (RG 06.06.2023/32213, per secondary sources) | UNVERIFIED |
| 12 | Electronic-communications operator incident | BTK and/or SGB (powers partly moved by Law 7590) | **UNVERIFIED** | Şebeke ve Bilgi Güvenliği Yönetmeliği (RG 13.07.2014/29059, per secondary sources); Law 7590 Prov. Art. 2 | UNVERIFIED |
| 13 | Health-sector incident | Ministry of Health / sectoral SOME | **UNVERIFIED** | not identified | UNVERIFIED |
| 14 | SGB emergency measure notified to operators, access providers, data centres, content or hosting providers | (Comply, not notify) | **Within 2 hours** of notification | Law 5809 Art. 60/A(2) (Law 7590, in force 31.07.2026); fine TRY 20k-100k per violation | In force |
| 15 | SGB official letter about a vulnerability or required measures | **SGB**, official letter via KEP or post (e-mail not accepted) | Act "as soon as possible"; deadline stated in the letter; extension by written request | SGB FAQ; Law 7545 Art. 7(1)(a)-(b) | In force (practice) |
| 16 | **DRAFT** - any party: cyber incidents, possible breaches, suspicious situations | **SGB** in SGB format | Without delay | Draft Art. 27 | Not in force |
| 17 | **DRAFT** - Corporate-SOME-obliged organisation: Level 1-2 incident (low / medium) | **Sectoral SOME** (SGB if no sectoral SOME) | **12 hours** from detection; update **72 hours**; detailed report **1 month** | Draft Arts. 14, 33(1), (2), (5) | Not in force |
| 18 | **DRAFT** - Corporate-SOME-obliged organisation: Level 3-5 incident (high / very high / national cyber crisis) | **Sectoral SOME + SGB** | **12 hours** from detection; update **72 hours**; detailed report **1 month** | Draft Arts. 14, 33(1), (2), (5) | Not in force |
| 19 | **DRAFT** - incidents with no mandatory duty, threats, vulnerabilities | **SGB** (voluntary) | - | Draft Art. 73 | Not in force |

## 2. Draft Incident Levels (draft Art. 14)

| Level | Name | Short description |
|-------|------|-------------------|
| 1 | Low impact | Limited systems or users, no data leak, core services not interrupted, handled with normal capability |
| 2 | Medium impact | Temporary disruption of some services, limited data loss or breach, controllable with own response capacity |
| 3 | High impact | Significant effect on critical systems or core services, serious CIA consequences, affects public services |
| 4 | Very high impact | Several organisations significantly affected, cross-sector spread or potential, serious economic or social effect |
| 5 | National cyber crisis | Serious disruption (or risk) of critical infrastructure or critical public services, requires national crisis mechanisms |

The reporting party classifies; SGB may reclassify (draft Art. 14(2)).

## 3. Non-Incident Notifications Under Law 7545 (for completeness)

| Event | Notify / approval | Basis |
|-------|-------------------|-------|
| Merger, demerger, share transfer or sale of a company producing cyber-security products/services | Notify SGB; **approval** for control-conferring transactions; unapproved = invalid | Art. 18(2)-(3) |
| Export of permit-subject cyber-security products | SGB approval | Art. 18(1) |
| Start of activity by a cyber-security company subject to certification | SGB approval before starting | Art. 7(1)(ç) |
| DRAFT - change of sectoral SOME contact details | SİP update within 3 working days | Draft Art. 21(5) |

## 4. How to Use the Matrix

1. At T0 (awareness of a possible incident), open one incident file. Record detection time to the minute; draft deadlines run from **detection**, KVKK from **awareness** of a personal data breach.
2. Ask in parallel: personal data affected? (rows 1-2) Sector regulator? (rows 8-13) Corporate SOME? (rows 4, 17-18) Crime? (row 6).
3. Send the SGB notification under row 3 even when no personal data is involved.
4. Keep facts consistent across KVKK, SGB and sector notices; update all when scope changes.
5. Do not publish unverified leak claims (Law 7545 Art. 16(5)).

## 5. UNVERIFIED

- Rows 11-13 (energy, telecom, health).
- Whether SGB has issued criteria for Guide measure 3.1.10.5 deadlines.
- Final deadlines in the Cyber Resilience Regulation.

## 6. Version History

| Version | Date | Change | Approval |
|---------|------|--------|----------|
| 1.0 | 2026-11-20 | First release | KVKK Committee |

---

## Türkçe

# Siber Olay Bildirim Matrisi

> Kaynaklara erişim 2026-11-20. Hukuki görüş değildir. **TASLAK** işaretli satırlar SGB'nin 18.11.2026 tarihli Siber Dayanıklılık Yönetmeliği Taslağı'ndandır ve **yürürlükte değildir**. Tek bir olaya birden fazla yükümlülük aynı anda uygulanabilir: tablonun tamamını tarayın.

## 1. Matris

| # | Olay türü | Kime bildirilir | Süre | Hukuki dayanak | Durum |
|---|-----------|-----------------|------|----------------|-------|
| 1 | Her sektörde kişisel veri ihlali (yetkisiz erişim, ifşa, kayıp, değişiklik) | **KVKK Kurulu** (ihlalbildirim.kvkk.gov.tr / KEP) | Öğrenmeden itibaren **gecikmeksizin, en geç 72 saat** | KVKK m.12(5); 24.01.2019 tarihli 2019/10 sayılı Kurul Kararı | Yürürlükte. Bkz. [72-saat-bildirim.md](../08-ihlal-yonetimi/72-saat-bildirim.md) |
| 2 | Aynı ihlal: etkilenen ilgili kişiler | **İlgili kişiler** doğrudan, ulaşılamıyorsa uygun yöntemle | Makul sürede, en kısa zamanda | KVKK m.12(5); 2019/10 sayılı Karar | Yürürlükte |
| 3 | Hizmet sunulan alanda tespit edilen her zafiyet veya siber olay (7545 kapsamındaki her taraf) | **SGB** (siberguvenlik.gov.tr/ihbar; KEP siberguvenlikbaskanligi@hs01.kep.tr) | **Gecikmeksizin**; Kanunda saat yok | 7545 m.7(1)(b); 1-10 milyon TL ceza (m.16(10)) | Yürürlükte |
| 4 | Kurumsal SOME'si olan kuruluşta siber olay | **USOM (artık SGB)** + **sektörel SOME** | Gecikmeksizin | SOME Tebliği m.5(6) (7545 geçici m.1(6) yoluyla uygulanır) | Yürürlükte |
| 5 | Sektörel SOME'nin sektöründe siber olay (sektörel SOME'nin kendi yükümlülüğü) | **USOM (artık SGB)** | Gecikmeksizin | SOME Tebliği m.7(2) | Yürürlükte |
| 6 | Olay müdahalesinde suç şüphesi | **Cumhuriyet savcılığı / kolluk** (Emniyet Siber Suçlarla Mücadele dahil) + **USOM (SGB)** | Gecikmeksizin | SOME Tebliği m.5(5); taslak m.24(1)(e) | Yürürlükte (Tebliğ) |
| 7 | 2019/12 Genelge kapsamındaki kamu kurumu veya kritik altyapı işletmesi: olay müdahale raporu | **Üst yönetim, SGB ve varsa sektörel SOME** | SGB'nin belirleyeceği kriterlere göre (Rehber saat vermez) | Rehber s.1.1 tedbir 3.1.10.5 | Uygulanıyor |
| 8 | Banka: olayın krize dönüşmesi, veri sızıntısı veya ifşası, süreklilik planının ya da ikincil merkezin devreye alınması | **Sektörel SOME (BDDK)**; hassas veya kişisel veri sızdıysa bankanın değerlendirmesinden sonra müşteriler | **Derhal** | BSEBY m.18(5); ayrıca m.18(1) BDDK'ya raporlama ve m.18(6) kök neden çalışmasının sektörel SOME'ye bildirimi | Yürürlükte |
| 9 | SPK kurumu: kritik operasyonları kesintiye uğratacak veya veri sızıntısıyla sonuçlanacak potansiyelde olay | **SPK**, müşteriler ve ilgili diğer kurumlar | **Derhal** | VII-128.10 m.24(4) | Yürürlükte |
| 10 | SPK kurumu: kritik sistemleri veya hassas verileri etkileyen olay, müdahale sonrası | **SPK**: siber olay müdahale raporu | Hazırlandıktan sonra **derhal** | VII-128.10 m.24(5) | Yürürlükte |
| 11 | Enerji sektöründe olay | EPDK / sektörel SOME | **DOĞRULANMADI / UNVERIFIED** | Enerji Sektöründe Siber Güvenlik Yetkinlik Modeli Yönetmeliği (ikincil kaynaklara göre RG 06.06.2023/32213) | DOĞRULANMADI |
| 12 | Elektronik haberleşme işletmecisinde olay | BTK ve/veya SGB (yetkilerin bir kısmı 7590 ile geçti) | **DOĞRULANMADI** | Şebeke ve Bilgi Güvenliği Yönetmeliği (ikincil kaynaklara göre RG 13.07.2014/29059); 7590 geçici m.2 | DOĞRULANMADI |
| 13 | Sağlık sektöründe olay | Sağlık Bakanlığı / sektörel SOME | **DOĞRULANMADI** | tespit edilemedi | DOĞRULANMADI |
| 14 | İşletmecilere, erişim sağlayıcılara, veri merkezlerine, içerik veya yer sağlayıcılara bildirilen SGB acil tedbir kararı | (Bildirim değil, uygulama) | Bildirimden itibaren **en geç 2 saat** | 5809 m.60/A(2) (7590, yürürlük 31.07.2026); eylem başına 20-100 bin TL ceza | Yürürlükte |
| 15 | Zafiyet veya alınacak önlemler hakkında SGB resmî yazısı | **SGB**, KEP veya posta ile resmî yazı (e-posta kabul edilmez) | "En kısa zamanda"; süre yazıda belirtilir; ek süre yazıyla istenir | SGB SSS; 7545 m.7(1)(a)-(b) | Yürürlükte (uygulama) |
| 16 | **TASLAK** - her taraf: siber olaylar, olası ihlaller, şüpheli durumlar | **SGB**, SGB formatında | Gecikmeksizin | Taslak m.27 | Yürürlükte değil |
| 17 | **TASLAK** - kurumsal SOME yükümlüsü: 1-2. seviye olay (düşük / orta) | **Sektörel SOME** (yoksa SGB) | Tespitten itibaren **12 saat**; güncelleme **72 saat**; ayrıntılı rapor **1 ay** | Taslak m.14, 33(1), (2), (5) | Yürürlükte değil |
| 18 | **TASLAK** - kurumsal SOME yükümlüsü: 3-5. seviye olay (yüksek / çok yüksek / ulusal siber kriz) | **Sektörel SOME + SGB** | Tespitten itibaren **12 saat**; güncelleme **72 saat**; ayrıntılı rapor **1 ay** | Taslak m.14, 33(1), (2), (5) | Yürürlükte değil |
| 19 | **TASLAK** - zorunlu bildirim kapsamında olmayan olay, tehdit, zafiyet | **SGB** (gönüllü) | - | Taslak m.73 | Yürürlükte değil |

## 2. Taslaktaki Olay Seviyeleri (taslak m.14)

| Seviye | Ad | Kısa açıklama |
|--------|----|---------------|
| 1 | Düşük etkili | Sınırlı sistem veya kullanıcı, veri sızıntısı yok, temel hizmet kesilmiyor, olağan imkânla giderilir |
| 2 | Orta etkili | Bazı hizmetlerde geçici aksama, sınırlı veri kaybı veya ihlali, kurumun müdahale kapasitesiyle kontrol edilir |
| 3 | Yüksek etkili | Kritik sistemleri veya temel hizmetleri önemli ölçüde etkiler, gizlilik/bütünlük/erişilebilirlikte ciddi sonuç, kamu hizmetini etkiler |
| 4 | Çok yüksek etkili | Birden fazla kuruluşu önemli ölçüde etkiler, sektörler arası yayılım veya potansiyeli, ciddi ekonomik veya toplumsal etki |
| 5 | Ulusal siber kriz | Kritik altyapı veya kritik kamu hizmetinde ciddi kesinti (veya riski), ulusal kriz mekanizmalarını gerektirir |

Sınıflandırmayı bildiren taraf yapar; SGB yeniden değerlendirip değiştirebilir (taslak m.14(2)).

## 3. 7545 Kapsamında Olay Dışı Bildirimler (bütünlük için)

| Olay | Bildirim / onay | Dayanak |
|------|-----------------|---------|
| Siber güvenlik ürün/hizmeti üreten şirkette birleşme, bölünme, pay devri veya satış | SGB'ye bildirim; kontrol sağlayan işlemde **onay**; onaysız işlem geçersiz | m.18(2)-(3) |
| İzne tabi siber güvenlik ürünlerinin ihracatı | SGB onayı | m.18(1) |
| Sertifikasyona tabi siber güvenlik şirketinin faaliyete başlaması | Başlamadan önce SGB onayı | m.7(1)(ç) |
| TASLAK - sektörel SOME iletişim bilgisi değişikliği | 3 iş günü içinde SİP güncellemesi | Taslak m.21(5) |

## 4. Matris Nasıl Kullanılır

1. T0'da (olası olayın öğrenilmesi) tek bir olay dosyası açın. Tespit zamanını dakika hassasiyetinde kaydedin; taslaktaki süreler **tespitten**, KVKK süresi kişisel veri ihlalinin **öğrenilmesinden** işler.
2. Paralel olarak sorun: kişisel veri etkilendi mi? (1-2. satırlar) Sektör düzenleyicisi var mı? (8-13) Kurumsal SOME var mı? (4, 17-18) Suç var mı? (6)
3. Kişisel veri olmasa bile 3. satırdaki SGB bildirimini yapın.
4. KVKK, SGB ve sektör bildirimlerinde olguları tutarlı tutun; kapsam değişince hepsini güncelleyin.
5. Doğrulanmamış sızıntı iddiası yayımlamayın (7545 m.16(5)).

## 5. DOĞRULANMADI / UNVERIFIED

- 11-13. satırlar (enerji, elektronik haberleşme, sağlık).
- SGB'nin Rehber tedbiri 3.1.10.5 için süre kriteri yayımlayıp yayımlamadığı.
- Siber Dayanıklılık Yönetmeliği'nin nihai süreleri.

## 6. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-11-20 | İlk yayım | KVKK Komitesi |
