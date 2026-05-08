---
Doküman: Kişisel Verilerin Aktarımı — Bölüm Girişi
Bölüm: 07-aktarim
Sahip: KVKK Sorumlusu
Onaylayan: Hukuk Müdürü + Bilgi Güvenliği Yöneticisi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (mevzuat değişikliği, Kurul kararı, yeni tedarikçi/aktarım rotası)
İlgili Mevzuat: 6698 sayılı KVKK m.5, m.6, m.8, m.9; 12.03.2024 tarihli ve 7499 sayılı Kanun (yürürlük 01.06.2024); KVKK Kurul'un 04.06.2024 tarihli ve 2024/959 sayılı kararı (Standart Sözleşmeler ve BCR); Kurul'un yeterli korumalı ülkeler listesi
---

# Bölüm 07 — Kişisel Verilerin Aktarımı

## 1. Bölümün Amacı

Bu bölüm, veri sorumlusunun kişisel verileri yurt içinde (KVKK m.8) ve yurt dışına (KVKK m.9) aktarımına ilişkin tüm operasyonel ve hukuki çerçeveyi düzenler. 12.03.2024 tarihli ve 32487 sayılı Resmî Gazete'de yayımlanan **7499 sayılı Ceza Muhakemesi Kanunu ile Bazı Kanunlarda Değişiklik Yapılmasına Dair Kanun** ile KVKK m.9 köklü bir biçimde değiştirilmiş ve yeni rejim **01.06.2024** tarihinde yürürlüğe girmiştir.

Yeni rejim, kişisel verilerin yurt dışına aktarımında **aşamalı bir yapı** öngörür:

1. **Yeterlilik kararı** bulunan ülke / sektör / uluslararası kuruluş;
2. **Uygun güvenceler** (4 alt yöntem);
3. **Arızi haller** (sınırlı sayıda 6 istisnai hal).

Kurul'un 04.06.2024 tarihli ve 2024/959 sayılı kararı ile **standart sözleşme metinleri** ve **bağlayıcı şirket kuralları (BCR)** başvuru formları ile yardımcı kılavuzlar yayımlanmıştır.

## 2. Bölüm İçeriği

| # | Doküman | Amaç |
|---|---------|------|
| 1 | [README.md](README.md) | Bölüm girişi (bu doküman) |
| 2 | [yurtici-aktarim.md](yurtici-aktarim.md) | KVKK m.8 — yurt içi aktarım rejimi |
| 3 | [yurtdisi-aktarim-rejimi.md](yurtdisi-aktarim-rejimi.md) | KVKK m.9 — aşamalı rejim, karar ağacı |
| 4 | [standart-sozlesme-rehberi.md](standart-sozlesme-rehberi.md) | Standart sözleşme uygulaması; bildirim akışı |
| 5 | [baglayici-sirket-kurallari.md](baglayici-sirket-kurallari.md) | BCR kapsamı, Kurul ön onayı |
| 6 | [arizi-aktarim.md](arizi-aktarim.md) | Arızi haller (m.9/6) — 6 istisnai hal |
| 7 | [aktarim-degerlendirme-formu.md](aktarim-degerlendirme-formu.md) | Doldurulabilir form + örnekler |

## 3. Aktarım Rejimi Üst Görünümü

```
+------------------------------------------------------------+
|                     KİŞİSEL VERİ AKTARIMI                  |
+------------------------------------------------------------+
                              |
              +---------------+----------------+
              |                                |
              v                                v
+--------------------------+    +--------------------------+
| YURT İÇİ (m.8)           |    | YURT DIŞI (m.9)          |
|                          |    |                          |
| - m.5/m.6 işleme şartı   |    | + AŞAMALI REJİM:         |
| - Aktarım için ayrıca    |    |                          |
|   ayrıca aranır          |    |   1. Yeterlilik kararı   |
| - Açık rıza veya         |    |   2. Uygun güvenceler    |
|   istisnalar             |    |   3. Arızi haller        |
| - Sözleşme zorunluluğu   |    |                          |
|                          |    | + Tüm yollarda m.5/m.6   |
|                          |    |   şartı ayrıca aranır    |
+--------------------------+    +--------------------------+
```

## 4. Temel Tanımlar ve Ayrımlar

### 4.1. Aktarım

KVKK'da aktarım açıkça tanımlanmamıştır; ancak aktarım, kişisel verinin başka bir gerçek/tüzel kişiye **erişiminin sağlanması** veya **fiziksel/dijital olarak iletilmesi** olarak yorumlanır. Aktarım, aşağıdakilerin tümünü kapsar:

- Sözleşmeyle aktarım (tedarikçi, hizmet sağlayıcı),
- Fiilî paylaşım (e-posta, dosya transferi),
- API ile erişim verme,
- Bulut barındırma (veri sağlayıcının altyapısında ise aktarım sayılır),
- Uzaktan erişim (yabancı ofisin Türkiye'deki sisteme bağlanması).

### 4.2. Veri Sorumlusu - Veri İşleyen Aktarımı

Aktarım, **veri sorumlusu → veri işleyen** veya **veri sorumlusu → veri sorumlusu** olabilir. İkisi farklı yükümlülükler doğurur:

| Boyut | VS → Vİ | VS → VS |
|-------|---------|---------|
| Sözleşme türü | Veri İşleme Sözleşmesi (KVKK m.12 anlamında) | Aktarım sözleşmesi + her iki tarafın bağımsız KVKK uyumu |
| Kontrol | VS amaç ve vasıtaları belirler; Vİ talimat ile hareket eder | İki taraf da kendi amaç ve vasıtalarını belirler |
| Aydınlatma | VS yapar | Her iki taraf kendi rolü için yapar |
| Sorumluluk | Vİ'nin ihlali halinde VS'nin sorumluluğu öncelikli | Birinin ihlali diğerinin sorumluluğunu doğurmaz |
| Joint controllership | Yok | Mümkün — gerekçeli analiz yapılmalı |

### 4.3. Yurt İçi vs Yurt Dışı

Aktarımın "yurt dışı" sayılması; verinin **fiziksel olarak Türkiye dışında bir sunucuya yazılması** veya **yurt dışındaki bir gerçek/tüzel kişinin erişebilmesi** ile ortaya çıkar. Bulut sağlayıcının Türkiye'de region'u olsa bile, sağlayıcının yurt dışındaki destek/idare/erişim haklarına bağlı olarak yurt dışı aktarım söz konusu olabilir. **Aktarım Etki Değerlendirmesi (TIA)** bunu netleştirmek için gereklidir.

## 5. Ortak Yükümlülük: m.5 ve m.6 İşleme Şartı

Hem yurt içi hem yurt dışı aktarımda, **aktarımdan ÖNCE** verinin işlenmesinin KVKK m.5 (genel) veya m.6 (özel nitelikli) kapsamında bir şartla dayanaklandırılması gerekir. Aktarımın kendisi ayrıca dayanaklandırılır:

- Yurt içi: m.8 hükümleri,
- Yurt dışı: m.9 hükümleri (yeterlilik / uygun güvence / arızi).

İki dayanak da bağımsız olarak sağlanmalıdır. Mevcut işleme şartı tek başına aktarımı meşrulaştırmaz.

## 6. Sorumluluklar

| Rol | Sorumluluk |
|-----|------------|
| Yönetim Kurulu | Yurt dışı aktarım stratejisinin onayı; standart sözleşme şablonlarının kabulü |
| KVKK Sorumlusu | Aktarım envanterinin yönetimi; her aktarım için Aktarım Etki Değerlendirmesi (TIA); standart sözleşme bildirimleri; Kurul'a 5 iş günü içinde bildirim |
| Hukuk Müdürlüğü | Sözleşme metinlerinin hukuki gözden geçirmesi; alıcı ülke hukuku analizi; Kurul izin başvuruları |
| Bilgi Güvenliği | Teknik tedbirlerin uygulanması (şifreleme, anahtar yönetimi, ek tedbirler); aktarım altyapısının güvenliği |
| Satınalma | Sözleşmeye standart sözleşme/DPA zorunluluğunun ihale aşamasında yansıtılması |
| BT | Teknik aktarım uygulamasının yapılması; bulut sağlayıcı tercihinin uygunluk analizi ile yapılması |
| İş Birimleri | Yeni aktarım talebinin KVKK Sorumlusu'na bildirilmesi; iş gerekçesi |

## 7. Bu Bölümün Diğer Bölümlerle İlişkisi

- **02 — Envanter ve Sicil:** Aktarım envanteri (alıcı, ülke, kategori, dayanak) bu bölümün veri kaynağıdır; VERBİS bildirimine yansır.
- **03 — Aydınlatma ve Açık Rıza:** Aktarımın hukuki sebebi açık rıza ise rıza metni bu bölümle uyumlu yazılır.
- **05 — Teknik Tedbirler:** Aktarımda ek teknik tedbirler (şifreleme, IP filtreleme, anahtar yönetimi).
- **08 — İhlal Yönetimi:** Yurt dışı aktarımdaki ihlal kayıtları ek özen gerektirir.
- **10 — Özel Konular:** Bulut, çağrı merkezi, e-ticaret aktarım rotaları.

## 8. Denetim ve KPI

- Aktarım sayısının envanter ile uyumu
- Standart sözleşme imzalı aktarım oranı (>%95 hedef)
- 5 iş günü içinde bildirim oranı (%100 hedef)
- TIA tamamlanmamış aktarım sayısı (=0 hedef)
- Açık rızaya bağlı yurt dışı aktarım oranı (mümkün olduğunca düşük; rıza geri çekilebilir)

## 9. Mevzuat Atfı

- 6698 sayılı KVKK — m.5, m.6, m.8, m.9 (12.03.2024 / 7499 sayılı Kanun ile değişik)
- 12.03.2024 tarihli ve 32487 sayılı Resmî Gazete — 7499 sayılı Kanun (yürürlük 01.06.2024)
- KVKK Kurulu'nun 04.06.2024 tarihli ve 2024/959 sayılı kararı — Standart Sözleşmeler ve BCR
- "Yeterli Korumanın Bulunduğu Ülkeler" Kurul Listesi (Kurum web sitesinde güncel)
- Kurum tarafından yayımlanan "Yurt Dışına Aktarıma İlişkin Rehber"
