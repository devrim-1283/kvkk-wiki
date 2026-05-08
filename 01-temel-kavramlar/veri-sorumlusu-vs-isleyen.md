---
Doküman: Veri Sorumlusu ve Veri İşleyen Ayrımı
Bölüm: 01-temel-kavramlar
Sahip: KVKK Sorumlusu / İrtibat Kişisi
Onaylayan: Yönetim Kurulu / Genel Müdür
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (yeni iş ortaklığı, M&A)
İlgili Mevzuat: 6698 sayılı KVKK m.3/1(ı) ve (ğ); m.12 (veri güvenliği); Kurum Yayını "Veri Sorumlusu ve Veri İşleyen" Haziran 2025
---

# Veri Sorumlusu ve Veri İşleyen Ayrımı

## 1. Amaç

Bu doküman, KVKK kapsamındaki **veri sorumlusu** ve **veri işleyen** sıfatlarının net ayrıştırılması, somut ortaklık senaryolarında doğru sıfat tespiti, sözleşmesel yükümlülüklerin tam karşılanması için operasyonel çerçeveyi belirler.

## 2. Yasal Tanımlar

### 2.1 Veri Sorumlusu (KVKK m.3/1(ı))
"Kişisel verilerin işleme amaçlarını ve vasıtalarını belirleyen, veri kayıt sisteminin kurulmasından ve yönetilmesinden sorumlu olan gerçek veya tüzel kişi."

### 2.2 Veri İşleyen (KVKK m.3/1(ğ))
"Veri sorumlusunun verdiği yetkiye dayanarak onun adına kişisel verileri işleyen gerçek veya tüzel kişi."

### 2.3 Kurum Görüşü (Haziran 2025 Yayını)
- Veri sorumlusu kişisel verilerin işlenmesinde **"neden"** ve **"nasıl"** sorularına cevap verecek olan taraftır.
- Veri işleyen, **veri sorumlusunun talimatları çerçevesinde** ve **organizasyonu dışında** kişisel veri işleyen bağımsız taraftır.

## 3. Ayrım Kriterleri (Karar Testi)

Bir işleme faaliyetinde tarafların sıfatını belirlemek için aşağıdaki kararları **kim verdi?** sorusu sorulur:

| Karar | Veri Sorumlusu Olduğunu Gösterir |
|-------|----------------------------------|
| **Kişisel verilerin toplanma yöntemi** | Karar veren VS |
| **Toplanacak veri kategorileri** | Karar veren VS |
| **Hangi amaçla kullanılacak** | Karar veren VS |
| **Hangi bireylerin verileri toplanacak** | Karar veren VS |
| **Verilerin paylaşılıp paylaşılmayacağı, kiminle** | Karar veren VS |
| **Saklama süreleri** | Karar veren VS |

| Karar | Veri İşleyene Bırakılabilir |
|-------|------------------------------|
| Hangi BT sistemlerinin kullanılacağı | Genellikle işleyen seçer |
| Saklama yönteminin teknik detayları | İşleyen |
| Güvenlik tedbirlerinin teknik detayları | İşleyen (asgari seviye VS belirler) |
| Aktarımın teknik yöntemi | İşleyen |
| Saklama süresinin sistemde uygulanma metodu | İşleyen |
| İmha yöntemi (silme/yok etme/anonim) — teknik | İşleyen |

**Kritik:** "Nasıl"ın **stratejik** karar boyutu (hangi süreçte, hangi amaçla) VS'ye, **operasyonel-teknik** boyutu işleyene düşer.

## 4. Aynı Tüzel Kişilik İçinde İkili Sıfat

Bir gerçek veya tüzel kişi aynı anda **hem veri sorumlusu hem veri işleyen** sıfatlarını taşıyabilir. Bu, "duruma göre değişen" bir sınıflandırmadır:

### Örnek 1: Bulut Hizmet Sağlayıcısı
- **Kendi çalışan verileri için** → veri sorumlusu (işe alım, bordro, performans)
- **Müşteri şirketler için sakladığı veriler için** → veri işleyen (müşterinin talimatlarıyla)

### Örnek 2: Çağrı Merkezi
- **Kendi personelinin verileri** → veri sorumlusu
- **Müşteri şirket adına yapılan müşteri aramaları** → veri işleyen

### Örnek 3: Mali Müşavir
- **Kendi büro çalışanları** → veri sorumlusu
- **Müşterinin bordrosunu işlemesi** → genellikle veri sorumlusu (mesleki yasal yükümlülükleri olduğundan)

### Örnek 4: Pazarlama Ajansı
- **Kendi çalışanları** → veri sorumlusu
- **Müşteri şirket için kampanya verisi işleme** → veri işleyen (talimat ile sınırlı)
- **Pazar araştırması yapma** → veri sorumlusu (çoğu zaman, kararları kendisi alır)

## 5. Şirketler Topluluğunda Sıfat

KVKK kapsamında **her tüzel kişilik ayrı veri sorumlusudur**.

### 5.1 Önemli İlkeler
- Holding bünyesindeki ABC A.Ş. ve XYZ Ltd. Şti. → iki ayrı VS
- Veri grup şirketleri arasında "iç akış" değil **aktarımdır** — KVKK m.8 (yurt içi) veya m.9 (yurt dışı bağlı şirket) hükümleri uygulanır
- Müşterek hizmet (HR, BT, finans paylaşımlı servisler): hizmet veren grup şirketi diğeri için ya VS ya işleyendir; sözleşmesel olarak netleştirilmelidir
- "Holding genelinde tek aydınlatma metni" → her tüzel kişi için ayrı bildirim ve VERBİS kaydı gerektirdiğinden, çatı metin altında her şirketin kimliğinin ayrıştırıldığı bölümler şarttır

### 5.2 Grup İçi Aktarım Karar Akışı
```
Grup içi paylaşım planlanıyor
    |
    +-- Veriyi alan grup şirketinin kendi karar yetkisi var mı?
    |   |
    |   +-- Evet → Aktarım. İki ayrı VS arası işlem.
    |   |          (Açık rıza VEYA m.8 işleme şartı; aktarım amacı aydınlatmada belirtilmeli)
    |   |
    |   +-- Hayır, sadece talimat ile işliyor → İşleyen pozisyonunda
    |               (Veri işleyen sözleşmesi gerekli)
    |
    +-- Yurt dışındaki grup şirketine aktarım mı?
        |
        +-- Evet → KVKK m.9 (yeterlilik kararı / uygun güvence / arızi)
```

## 6. Veri İşleyen Sözleşmesi — Asgari Hükümler

KVKK m.12 ve veri güvenliği yükümlülüğü kapsamında, veri sorumlusu ile veri işleyen arasında **yazılı sözleşme** zorunludur. Sözleşmede asgari aşağıdaki hükümler bulunmalıdır:

### 6.1 Konu ve Süre
- İşleme faaliyetinin konusu, süresi
- Kişisel veri kategorileri ve ilgili kişi grupları
- Belirlenen amaç ve kapsam dışına çıkılmaması taahhüdü

### 6.2 Talimat Bağlılığı
- İşleyenin **yalnızca veri sorumlusunun yazılı talimatları** doğrultusunda işleme yapması
- Talimatlar dışındaki işlemenin yasak olduğu

### 6.3 Sır Saklama (KVKK m.12/4)
- İşleyenin ve onun adına çalışan kişilerin sır saklama yükümlülüğü
- Bu yükümlülüğün sözleşme bitiminden sonra da süresiz devam edeceği
- İşleyenin personeline gizlilik taahhüdü imzalattığı

### 6.4 Güvenlik Tedbirleri (KVKK m.12)
- İşleyenin uygulayacağı asgari teknik ve idari tedbirler
- Erişim yönetimi, log kayıtları, şifreleme, sızıntı önleme
- İşleyenin tedbirlerinin VS'ninkilere eşdeğer olması

### 6.5 Alt İşleyen
- VS'nin **önceden yazılı izni olmadan** alt işleyen kullanılamayacağı
- Onaylanmış alt işleyen listesinin sözleşmenin ekini oluşturması
- Alt işleyenle aynı koşulları içeren yazılı sözleşme zorunluluğu
- Alt işleyenin ihlali durumunda asıl işleyenin tam sorumlu olması

### 6.6 Yurt Dışı Aktarım
- Yurt dışına aktarım yapılacaksa hangi ülkelere
- Hangi uygun güvence (BCR, standart sözleşme, taahhütname) ile
- VS'nin önceden onayı gerektiği

### 6.7 Denetim Hakkı
- VS'nin tedbirlerin yerine getirilip getirilmediğini denetleme hakkı
- Bağımsız üçüncü taraf denetimi (ISO 27001, ISO 27701, SOC 2 Type II) ile karşılanabilirliği
- Yıllık asgari denetim raporu paylaşımı

### 6.8 İhlal Bildirimi
- İşleyenin ihlali öğrendikten sonra **24 saat içinde** VS'ye bildirim
- Bildirim içeriği: olay özeti, etkilenen veri kategorileri, kişi sayısı, alınan tedbirler
- VS'nin Kurum'a 72 saat içinde bildirim hazırlığı için işleyenin tam destek sağlaması

### 6.9 İlgili Kişi Talepleri
- VS'ye yönelmiş başvurularda işleyenin makul yardım yükümlülüğü
- Doğrudan işleyene yönelmiş taleplerin VS'ye yönlendirilmesi
- Yardım yükümlülüğünün kapsamı (verilerin temini, silinmesi, düzeltilmesi vb.)

### 6.10 İade ve İmha
- Sözleşme sona erdiğinde işleyenin elindeki tüm verileri:
  - **VS'ye iade etmesi** veya
  - **VS'nin talimatına göre imha etmesi**
- İmha tutanağı düzenlemesi
- İmhanın 30 gün içinde tamamlanması

### 6.11 Hukuki Yükümlülükler
- KVKK ve ikincil mevzuata tam uyum taahhüdü
- Mevzuat değişikliklerine adapte olma yükümlülüğü
- İdari para cezası halinde rücu hükümleri

### 6.12 Sigorta
- Yüksek riskli işlemelerde işleyenin siber sigorta veya mesleki sorumluluk sigortası tutması

## 7. "Sözleşmedeki sıfat" vs "Gerçek sıfat"

Önemli bir yanılgı: tarafların sözleşmede kendilerini "veri işleyen" olarak nitelemesi, KVKK kapsamında otomatik olarak bu sıfatı vermez. **Gerçek sıfat, fiili karar verme yetkisinden doğar.**

Örneğin: Pazar araştırması şirketi sözleşmede "veri işleyen" yazsa bile, kendisi anket sorularına, örneklem seçimine, veri kullanım kararlarına etki ediyorsa **veri sorumlusudur**.

## 8. Pratik Senaryolar (Türkiye Bağlamı)

### Senaryo 1: SaaS CRM Sağlayıcısı
- **Müşteri şirket** (e-ticaret platformu) → Veri sorumlusu
- **CRM SaaS sağlayıcı** → Veri işleyen
- **Gerekli sözleşme:** Veri işleme sözleşmesi (DPA), KVKK m.12 gereksinimleri ile
- **Yurt dışı boyutu:** SaaS sağlayıcı yurt dışı ise → m.9 rejimi

### Senaryo 2: Çağrı Merkezi Outsourcing
- **Banka** → VS
- **Çağrı merkezi şirketi** → İşleyen
- **Önemli:** Çağrı merkezi script'lerini ve müşteri yanıt politikalarını bankanın belirlediği durumda — talimat dışına çıkamaz; yorum yetkisi yok

### Senaryo 3: Bordro Hizmeti
- **İşveren şirket** → VS
- **Bordro hizmet sağlayıcı** → İşleyen (sadece talimatla işliyorsa)
- **Aksi:** Mali müşavir mesleki yasal yükümlülüklerle hareket ediyorsa (yolsuzluk bildirim zorunluluğu vs.) → bağımsız VS pozisyonu da olabilir

### Senaryo 4: Bulut Veri Tabanı (AWS RDS, Azure SQL, GCP Cloud SQL)
- **Müşteri şirket** → VS
- **Bulut sağlayıcı** → İşleyen
- **Standart DPA:** Hyperscaler'ların standart DPA'larında alt işleyen listeleri ve denetim hakları sınırlı; iyileştirme için müzakere gerekli olabilir
- **Yurt dışı:** Veri lokasyonunun nerede olduğu (Türkiye region var mı?) m.9 rejimi tetikleyebilir

### Senaryo 5: Kargo / Lojistik
- **E-ticaret şirketi** → VS
- **Kargo şirketi** → İşleyen mi, VS mi?
- **Test:** Kargo şirketi teslimat sürecinde alıcının kişisel verilerini başka amaçla (kendi pazarlaması, kendi sigorta süreci) işliyorsa → kendi adına VS sıfatı doğar
- **Pratikte:** Çoğu kargo şirketi hem işleyen (gönderen şirket adına) hem VS (kendi yasal yükümlülükleri kapsamında)

### Senaryo 6: Hukuk Firması
- **Müvekkil şirket** → VS (kendi verisi için)
- **Avukat / hukuk firması** → Genellikle bağımsız VS (avukatlık mesleğinin yasal sorumlulukları gereği)
- **Talimatla davanın yürütülmesi VS sıfatını ortadan kaldırmaz** — avukat, müvekkilin talimatından bağımsız mesleki yükümlülüklere tabidir

### Senaryo 7: Sigorta Brokerlığı
- **Sigorta şirketi** → VS
- **Broker** → Genellikle bağımsız VS (kendi mesleki yükümlülükleri var)
- **Sigorta talebini ileten kişi olarak** broker bağımsız sözleşme/yükümlülük taşır

### Senaryo 8: Pazarlama / Reklam Ajansı
- **Marka şirket** → VS
- **Ajans, sadece kreatif üretim yapıyorsa kişisel veri işlemesi sınırlı** → işleyen olabilir
- **Ajans data-driven kampanya yürütüyor, segmentasyon yapıyor, Lookalike audience oluşturuyor** → bağımsız VS pozisyonu

### Senaryo 9: İK İşe Alım / Headhunter
- **İşe alım yapan şirket** → VS
- **Headhunter** → Genellikle bağımsız VS (kendi aday havuzu var, kendi süreçleri var)
- **Outsource İK** (sadece şirketin pozisyonu için aday bulma) → işleyen olabilir, eğer aday verisini başka amaçla kullanmıyorsa

### Senaryo 10: Ortak Pazarlama / Co-marketing
- İki şirket ortak pazarlama yapıyorsa → **müşterek veri sorumluları** olabilir
- **Müşterek VS:** İki tarafın da işleme amacı/vasıtası belirleme yetkisi varsa (her ikisi de "neden" sorusuna cevap veriyor)
- **Sözleşmesel olarak:** Hangi tarafın hangi yükümlülüğü üstleneceği yazılı netleştirilmeli

## 9. Pratik Karar Akışı

```
Bir veri ortaklığı / hizmet ilişkisi başlıyor
              |
              v
    Karşı taraf hangi süreçte ne yapacak? Detaylı belirle.
              |
              v
   "Neden işleyecek?" sorusunu sor
              |
              +-- Kendi amacı için (kendi yasal yükümlülüğü, kendi ürünü) → BAĞIMSIZ VS
              |
              +-- Sadece bizim talimatımız ile → İŞLEYEN olabilir
              |
   "Nasıl işleyecek?" sorusunu sor
              |
              +-- Stratejik/işleme amacı kararları kendisi alıyor → MÜŞTEREK VS veya BAĞIMSIZ VS
              |
              +-- Sadece teknik metodu kendisi seçiyor (saklama yöntemi, şifreleme türü) → İŞLEYEN
              |
              v
   Karar: VS / Müşterek VS / İşleyen / Bağımsız VS
              |
              v
   Buna göre uygun sözleşme türünü hazırla:
   - VS-VS arası: Ortak işleme sözleşmesi + aydınlatma metinlerinde aktarım belirtilmesi
   - VS-İşleyen: KVKK m.12 uyumlu Veri İşleme Sözleşmesi (DPA)
   - Müşterek VS: Sorumluluk paylaşım sözleşmesi
              |
              v
   Tedarikçi DD (due diligence) süreci başlat
              |
              v
   VERBİS bildiriminde: alıcı grupları güncellenir, gerekirse kayıt değiştirilir
              |
              v
   Aydınlatma metni güncellenir
              |
              v
   Yıllık denetim takvimine eklenir
```

## 10. Yaygın Hatalar

| Hata | Doğrusu |
|------|---------|
| "Bulut sağlayıcı veri işleyendir, sözleşmeye gerek yok" | KVKK m.12 yazılı sözleşme zorunlu kılar |
| "DPA imzalandı, bitti" | Yıllık denetim, ihlal bildirim takibi, alt işleyen onayı sürekli |
| "Şirketler topluluğu, aynı sahip" → tek VS | Her tüzel kişi ayrı VS |
| "Avukat bizim talimatımızla çalışıyor, işleyendir" | Avukat genellikle bağımsız VS (mesleki yasal yükümlülük) |
| "VERBİS'e tek bildirim yeterli" | Her tüzel kişi için ayrı VERBİS kaydı |
| "İşleyenin ihlalinden biz sorumlu değiliz" | KVKK kapsamında VS, işleyenin eylemlerinden de sorumlu (m.12) |
| "Müşterek VS konusu var ama sözleşme yok" | Müşterek VS senaryoları yazılı sorumluluk paylaşımı gerektirir |
| "Standart sözleşmeden yeterli, müzakere gerekmez" | Hyperscaler standart DPA'ları her zaman KVKK m.12 gereksinimlerini tam karşılamayabilir; ek hükümler eklenmeli |

## 11. İlgili Dokümanlar

- `01-temel-kavramlar/tanimlar.md`
- `01-temel-kavramlar/isleme-sartlari.md`
- `07-aktarim/yurt-ici-aktarim.md`
- `07-aktarim/yurt-disi-aktarim.md`
- `10-ozel-konular/tedarikci-yonetimi.md`
- `99-sablonlar/veri-isleyen-sozlesmesi.md`
- `99-sablonlar/musterek-vs-sorumluluk-paylasim-sozlesmesi.md`
