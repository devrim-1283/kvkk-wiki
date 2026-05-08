---
Doküman: Yurt İçi Kişisel Veri Aktarımı
Bölüm: 07-aktarim
Sahip: KVKK Sorumlusu
Onaylayan: Hukuk Müdürü + Bilgi Güvenliği Yöneticisi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (mevzuat değişikliği, yeni iş süreci, yeni tedarikçi)
İlgili Mevzuat: KVKK m.4, m.5, m.6, m.8, m.10, m.12; Veri İşleyenle Yapılacak Sözleşmelere İlişkin Kurul Kararları
---

# Yurt İçi Kişisel Veri Aktarımı

## 1. Hukuki Çerçeve (KVKK m.8)

KVKK m.8, kişisel verilerin Türkiye sınırları içinde üçüncü kişilere aktarılmasını düzenler. Maddenin temel ilkeleri:

- Kanunda belirtilen genel ilkeler (m.4) ve işleme şartları (m.5/m.6) çerçevesinde işlenmiş veriler, **ayrıca aktarım için bir hukuki dayanak bulunması koşuluyla** üçüncü kişilere aktarılabilir.
- Yurt içinde de aktarımın **işleme şartları gibi ayrıca aranması gerekir**: işlemenin meşru olması, otomatik olarak aktarımı meşru kılmaz.
- Açık rıza, aktarımın meşru sebeplerinden biridir; ancak başka şartlar varsa açık rıza aranmaz.

> **Kritik:** Veri yurt içinde hukuka uygun işlenmiş olabilir, ama bu doğrudan aktarılabileceği anlamına gelmez. Aktarım için m.5/m.6'da düzenlenen şartlardan birinin **aktarım anında** sağlanmış olması gerekir.

## 2. Genel Nitelikli Kişisel Veriler İçin Aktarım Şartları (m.5)

Açık rıza dışında aşağıdakilerden birinin varlığı halinde aktarım yapılabilir:

| # | Şart | Tipik Senaryo |
|---|------|---------------|
| 1 | Açık rıza | Pazarlama amaçlı paylaşım, üçüncü taraf analitik araçları |
| 2 | Kanunlarda açıkça öngörülmesi | SGK bildirimi, Mali Müşavire bordro paylaşımı, Adli mercilere bilgi verme |
| 3 | Fiili imkânsızlık (rızasını açıklayamayacak kişi) için hayat/beden bütünlüğü | Acil sağlık durumu — hastane/ambulansa veri aktarımı |
| 4 | Sözleşmenin kurulması/ifasıyla doğrudan ilgili olması | Müşteri sözleşmesi gereği lojistik firmasına teslimat adresi aktarımı |
| 5 | Veri sorumlusunun hukuki yükümlülüğü | Vergi denetiminde yetkili mercilere belge aktarımı |
| 6 | İlgili kişi tarafından alenileştirme | Aleni LinkedIn profilinin yetkinlik araştırmasında kullanılması (sınırlı) |
| 7 | Hak tesisi/kullanılması/korunması | Davada delil olarak avukatla paylaşım |
| 8 | Veri sorumlusunun meşru menfaati | Grup şirketi içinde IK paylaşımı; pazarlama otomasyon SaaS aktarımı |

## 3. Özel Nitelikli Kişisel Veriler İçin Aktarım Şartları (m.6)

Özel nitelikli veriler (sağlık, cinsel hayat, ırk, din, biyometrik vb.) için aktarım daha katı şartlara bağlıdır:

- **Açık rıza** halinde,
- Sağlık ve cinsel hayat **dışındaki** özel nitelikli veriler için: **kanunlarda açıkça öngörülmüş olması**,
- Sağlık ve cinsel hayata ilişkin veriler için: **kamu sağlığının korunması, koruyucu hekimlik, tıbbi teşhis, tedavi ve bakım hizmetlerinin yürütülmesi, sağlık hizmetleri ile finansmanının planlanması ve yönetimi** amacıyla, **sır saklama yükümlülüğü altındaki kişiler veya yetkili kurum/kuruluşlar tarafından**.

> **Pratik:** Çalışan sağlık raporları kural olarak ancak işyeri hekimi gibi sır saklama yükümlülüğü altındaki kişilere aktarılabilir; İK Direktörüne dahi açık rıza olmadan aktarılması özen gerektirir.

## 4. Aktarımın Türleri

### 4.1. Veri Sorumlusu → Veri İşleyen Aktarımı

Veri işleyen, veri sorumlusunun **talimatı doğrultusunda** ve **organizasyonu dışında** kişisel verileri işleyen kişidir. Bu aktarım türünde:

- KVKK m.12/3 uyarınca **veri sorumlusu ile veri işleyen müşterek sorumludur**.
- Aralarında **yazılı sözleşme** bulunması ve sözleşmenin asgari unsurları içermesi gerekir.
- Veri işleyenin amaç ve vasıta belirleme yetkisi **yoktur**; sözleşme ile bu yetki belirtilirse o noktada veri işleyen, aktarılan veri için **veri sorumlusu** statüsüne geçer.

#### 4.1.1. Veri İşleyen Sözleşmesinin Asgari Unsurları

| Unsur | Açıklama |
|-------|----------|
| Tanım ve kapsam | İşlenecek veri kategorileri, ilgili kişi grupları, işleme amaçları, süresi |
| Talimat hükmü | Veri işleyenin yalnızca veri sorumlusunun yazılı talimatı doğrultusunda işleyebileceği |
| Gizlilik | Veri işleyen personelinin gizlilik taahhüdü altında olması |
| Güvenlik tedbirleri | KVKK m.12 anlamında teknik+idari tedbirlerin alınması — somut listelenmiş |
| Alt-işleyen kullanımı | Alt-işleyen ancak yazılı izin ile; aynı yükümlülüklerin alt-işleyene de yansıtılması |
| Yardım yükümlülüğü | İlgili kişi taleplerinin cevaplanmasında ve ihlal yönetiminde yardım |
| İhlal bildirimi | Veri sorumlusuna **derhal bildirim** (somut süre ör. 24 saat) |
| Denetim | Veri sorumlusunun denetim hakkı; denetim raporlarına erişim |
| Sözleşmenin sona ermesi | Veri sorumlusunun talimatına göre verilerin imhası veya iadesi |
| Yargı yeri ve hukuk | Türkiye Cumhuriyeti hukuku ve İstanbul Mahkemeleri (tipik) |
| KVKK m.12 atfı | Açık atıf yapılır |

### 4.2. Veri Sorumlusu → Veri Sorumlusu Aktarımı

İki taraf da kendi adına amaç ve vasıta belirliyorsa, ikisi de **veri sorumlusudur**. Bu aktarım türünde:

- Her iki taraf bağımsız KVKK uyumundan sorumludur.
- Aralarında **aktarım sözleşmesi** akdedilir; bu, veri işleyen sözleşmesinden farklıdır.
- Her iki taraf da **kendi aydınlatma metnini** yapar; alıcı taraf, ilgili kişiye yeni bir aydınlatma yükümlülüğü altındadır.

### 4.3. Joint Controllership (Müşterek Veri Sorumluluğu)

İki veya daha çok veri sorumlusunun aynı işleme amacı ve vasıtası üzerinde ortak karar aldığı yapıdır. Türk hukukunda açık düzenleme yoktur ancak Kurul kararlarında ve doktrinde kabul görmektedir. Tipik örnekler:

- Bir araştırma şirketi ile sponsor şirket, anketi birlikte tasarlıyorsa,
- Avukat ile müvekkil, bir davada delil olarak paylaşılan kişisel veriler için ortak karar veriyorsa,
- Pazarlama amacıyla iki şirket ortak müşteri portföyünü işliyorsa.

Joint controllership halinde **iki taraf da**:

- m.10 kapsamında ilgili kişiyi aydınlatır,
- m.13 başvurularına bağımsız cevap verir,
- m.12 tedbirlerini bağımsız alır.

Anlaşmaya konu kapsam dışında bir taraf alacağı kararlarla diğerinden farklılaşırsa, joint controllership o noktada sona erer.

### 4.4. Karar Ağacı: Tedarikçi Veri Sorumlusu mu, Veri İşleyen mi?

```
+-------------------------------------------------+
| Tedarikçi kişisel veriyi sözleşme dışı kendi    |
| amaçları için kullanabilir mi?                  |
+-------------------------------------------------+
       |                          |
   evet|                       hayır|
       v                          v
+--------------+        +-------------------------------+
| Veri         |        | Tedarikçi, kişisel verinin    |
| sorumlusu    |        | işleneceği amaç ve vasıtaya   |
+--------------+        | karar verme yetkisi sahip mi? |
                        +-------------------------------+
                              |              |
                          evet|           hayır|
                              v              v
                  +------------------+  +--------------+
                  | Veri sorumlusu   |  | Veri işleyen |
                  | (joint olabilir) |  +--------------+
                  +------------------+
```

## 5. Aktarımın Hukuki Meşruluğunun Test Edilmesi

Her aktarım için aşağıdaki sorular cevaplanır:

1. **Hangi veri kategorisi aktarılıyor?** (Genel / özel nitelikli)
2. **Kim aktarıyor, kime aktarıyor?** (Alıcı veri sorumlusu mu, veri işleyen mi?)
3. **Aktarım amacı ne?** (Sözleşme ifası / hukuki yükümlülük / pazarlama / analitik / vb.)
4. **Hangi m.5/m.6 şartı dayanak?** (Açık rıza son seçenek; mümkünse meşru menfaat veya sözleşme ifası tercih edilir)
5. **Sözleşme tipi hangisi?** (Veri işleyen sözleşmesi / aktarım sözleşmesi / joint controller anlaşması)
6. **Aydınlatma yapıldı mı?** (m.10 yükümlülüğü)
7. **VERBİS'e yansıtıldı mı?** (Alıcı grubu olarak)
8. **Teknik tedbirler alındı mı?** (Şifreleme, erişim kontrolü)

## 6. Yaygın Yurt İçi Aktarım Senaryoları

### 6.1. Çalışan Bordrosunun Mali Müşavire Aktarılması

- **Hukuki sebep:** KVKK m.5/2-(a) "Kanunlarda açıkça öngörülmesi" (213 VUK, 4857 İş K.)
- **Statü:** Mali müşavir, kendi mesleki yükümlülükleri nedeniyle **veri sorumlusu** statüsündedir (kendi yasal sorumlulukları olduğu için).
- **Sözleşme:** Aktarım sözleşmesi ve gizlilik anlaşması.
- **Aydınlatma:** Çalışan aydınlatma metninde alıcı grubu olarak "yetkili mali müşavir" geçer.

### 6.2. Lojistik Tedarikçisine Müşteri Adresi Aktarılması

- **Hukuki sebep:** KVKK m.5/2-(c) "Sözleşmenin ifasıyla doğrudan ilgili olması"
- **Statü:** Lojistik firmasının yalnızca teslimat amacıyla veri kullandığı, kendi adına işlemediği durumda **veri işleyen**. Lojistik firmasının kendi taşıma ve sigorta süreci için bağımsız işlem yapması durumda **veri sorumlusu**.
- **Sözleşme:** Veri işleyen sözleşmesi (asgari unsurlar tam).
- **Aydınlatma:** Sipariş aydınlatmasında alıcı grubu olarak "lojistik hizmet sağlayıcıları".

### 6.3. CRM SaaS Sağlayıcısına Veri Aktarımı (Türkiye'de barındırma)

- **Hukuki sebep:** KVKK m.5/2-(f) "Meşru menfaat" + sözleşme ifası
- **Statü:** Sağlayıcı sadece müşterinin verisini barındırıyor → **veri işleyen**. Sağlayıcı kendi analitik/iyileştirme amacıyla agresif bir şekilde veriyi kullanıyorsa → **veri sorumlusu** (joint controllership riski).
- **Sözleşme:** Veri işleyen sözleşmesi + DPA.
- **Aydınlatma:** Müşteri aydınlatmasında alıcı grubu olarak "CRM hizmet sağlayıcısı".

### 6.4. Reklam Ajansına Pazarlama Verisi Aktarımı

- **Hukuki sebep:** Açık rıza (m.5/1) — pazarlama amaçlı işleme ve aktarım için
- **Statü:** Ajansın kampanyayı tasarlamada karar verme yetkisi varsa **veri sorumlusu** veya **joint controller**; sadece teknik uygulama yapıyorsa **veri işleyen**.
- **Sözleşme:** Aktarım sözleşmesi veya veri işleyen sözleşmesi.
- **Aydınlatma:** Açık rıza metninde aktarım açıkça belirtilir.

### 6.5. Şirketler Topluluğu İçinde IK Veri Paylaşımı

- **Hukuki sebep:** KVKK m.5/2-(f) "Meşru menfaat" + sözleşme ifası (grup içi sözleşme)
- **Statü:** Her şirket ayrı tüzel kişi → ayrı veri sorumlusu. Aktarım, ayrı bir veri sorumlusuna aktarımdır.
- **Sözleşme:** Grup içi veri paylaşım anlaşması.
- **Aydınlatma:** Çalışan aydınlatması "grup şirketleri" olarak alıcı grubunu listeler.

### 6.6. Adli Mercilere Belge Verilmesi

- **Hukuki sebep:** KVKK m.5/2-(a) "Kanunlarda açıkça öngörülmesi" (CMK, HMK)
- **Statü:** Mahkeme veya savcılığa veri verilmesi aktarımdır; ancak yasa gereği zorunlu olduğu için ayrıca rıza aranmaz.
- **Sözleşme:** Yok; resmi yazıyla iletim.
- **Aydınlatma:** Genel aydınlatma metninde "yetkili kamu kurum ve kuruluşları" olarak.

## 7. Aktarım Sözleşmesi Asgari Unsurları (VS-VS aktarımı için)

| Unsur | Açıklama |
|-------|----------|
| Taraflar | Kimliği belirli iki veri sorumlusu |
| Aktarımın amacı | Açık ve sınırlı |
| Veri kategorileri | Liste halinde |
| İlgili kişi grupları | Açık |
| Hukuki sebep | KVKK m.5/m.6 hangi şart |
| Süre | Aktarımın süresi; verilerin alıcıdaki saklama süresi |
| Aydınlatma yükümlülüğü | Alıcının ilgili kişiye karşı yükümlülüğünü kabul etmesi |
| Güvenlik tedbirleri | Tarafların alacağı teknik+idari tedbirler |
| İhlal bildirimi | Karşılıklı bildirim |
| Verinin korunma süresi | Aktarımın amacı sona erince imha veya iade |
| Sorumluluk | Karşılıklı tazminat hükümleri |
| Uyuşmazlık | TC hukuku, yetkili mahkeme |

## 8. VERBİS'e Yansıtma

Yurt içi aktarımlar VERBİS'te:

- "Kişisel verilerin aktarılabileceği alıcı/alıcı grupları" alanına alıcı grubu olarak yazılır.
- "Yurt içinde mi yurt dışına mı aktarılıyor?" alanı "yurt içi" olarak işaretlenir.
- Veri kategorisi ile alıcı grubu eşleşmesi sağlanır.

Alıcı grubu örnekleri (sicil tipik kategorileri):

- İş Ortağı
- Tedarikçi (lojistik / IT / hukuk / finans)
- Hissedarlar
- İştirakler ve Bağlı Ortaklıklar
- Yetkili Kamu Kurum ve Kuruluşları
- Hukuken Yetkili Özel Hukuk Kişileri
- Veri İşleyen Hizmet Sağlayıcısı

## 9. Tipik Hatalar

| Hata | Sonuç | Önlem |
|------|-------|-------|
| Aktarımın işleme şartı ile karıştırılması | Aktarım için ayrıca dayanak gösterilmemiş | Her aktarım için Aktarım Etki Değerlendirmesi |
| Veri işleyenin veri sorumlusu olduğunun fark edilmemesi | Yanlış sözleşme tipi; sorumluluk dağılımı hatalı | Karar ağacı uygulanır; sözleşme öncesi statü tespiti |
| Pazarlama aktarımları için meşru menfaat denenmesi | Kurul reddedebilir; açık rıza zorunluluğu | Pazarlama için açık rıza; rıza ispatı |
| DPA (veri işleyen sözleşmesi) eksik veya yetersiz | KVKK m.12 ihlali | Standart DPA şablonu; satınalma akışına entegre |
| Aydınlatmada alıcı grubu eksik | KVKK m.10 ihlali | Envanter ile aydınlatma metni karşılaştırması |
| Özel nitelikli veriyi sıradan aktarım yoluyla göndermek | KVKK m.6 ihlali | Özel nitelikli veri için ek prosedür; sır saklama yükümlüsü kontrolü |

## 10. Aktarım Öncesi Kontrol Listesi

- [ ] Aktarımın amacı tanımlandı mı?
- [ ] Hangi veri kategorileri aktarılıyor?
- [ ] Genel mi özel nitelikli mi?
- [ ] Alıcı veri sorumlusu mu, veri işleyen mi? (Karar ağacı)
- [ ] m.5/m.6 hangi işleme şartı?
- [ ] Aktarım sözleşmesi/DPA imzalandı mı?
- [ ] Sözleşme asgari unsurları içeriyor mu?
- [ ] Aydınlatma metni güncel mi?
- [ ] VERBİS'e yansıtıldı mı?
- [ ] Teknik tedbirler (şifreleme, erişim) tanımlandı mı?
- [ ] İhlal bildirim hattı kuruldu mu?
- [ ] Aktarım envanterine kayıt yapıldı mı?
