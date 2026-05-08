---
Doküman: 01-Temel Kavramlar Bölümü Girişi
Bölüm: 01-temel-kavramlar
Sahip: KVKK Sorumlusu / İrtibat Kişisi
Onaylayan: Yönetim Kurulu / Genel Müdür
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (mevzuat değişikliği, Kurul kararı)
İlgili Mevzuat: 6698 sayılı KVKK m.3, m.4, m.5, m.6, m.7, m.11, m.12, m.13
---

# 01 — Temel Kavramlar

## Bölümün Amacı

Bu bölüm, KVKK uyum programının üzerine kurulduğu **kavramsal zemin**i oluşturur. Tüm operasyonel dokümanlar (envanter, aydınlatma, açık rıza, saklama, aktarım, ihlal, başvuru) bu bölümdeki kavramların doğru anlaşılmasına dayanır.

## Dosya Listesi ve Kullanım Kılavuzu

| Doküman | Ne Zaman Kullanılır? | Birincil Sahip |
|---------|----------------------|----------------|
| **tanimlar.md** | KVKK terimi geçen her dokümanda referans; eğitim materyali; sözleşme kelimelerinin doğru kullanımı | KVKK Sorumlusu |
| **kisisel-veri-vs-ozel-nitelikli.md** | Veri kategorisi sınıflandırma kararı; envantere yeni alan ekleme; özel nitelikli veri tedbirlerinin tetiklenmesi | KVKK Sorumlusu + İş Birimi |
| **veri-sorumlusu-vs-isleyen.md** | Yeni iş ortaklığı, tedarikçi ilişkisi, M&A, grup içi paylaşım kararı | Hukuk + KVKK Sorumlusu |
| **ilgili-kisi-haklari.md** | Başvuru yönetimi; başvuru ekibi eğitimi; reddetme/kabul kararı; süre yönetimi | KVKK Sorumlusu |
| **isleme-sartlari.md** | Yeni süreç başlatma; aydınlatma metni hazırlığı; LIA dengelemesi; rıza yenileme kararı | KVKK Sorumlusu + Hukuk |

## Kullanım Sırası (Eğitim Açısından)

Yeni başlayan biri için önerilen okuma sırası:

1. **tanimlar.md** — Sözlük; ilerideki tüm dokümanların temeli
2. **kisisel-veri-vs-ozel-nitelikli.md** — En temel ayrım: hangi veri nereye düşer?
3. **veri-sorumlusu-vs-isleyen.md** — Hangi sıfattayız ve karşı tarafla ne tür sözleşme yapılır?
4. **isleme-sartlari.md** — İşlemenin hukuki dayanağı nasıl belirlenir?
5. **ilgili-kisi-haklari.md** — Veri sahibinin hakları nelerdir, nasıl yönetilir?

## Kavramsal Harita

```
KİŞİSEL VERİ
   |
   +-- Genel Kişisel Veri ---------+
   |                                |
   +-- Özel Nitelikli ------------+ |
                                  | |
                                  v v
                          İŞLEME ŞARTLARI
                                  |
       +--------------------------+----------------------------+
       |                          |                            |
   m.5/2(a)-(f)               m.6/2 (genel ÖN)            m.6/3 (sağlık/cinsel hayat)
   yasal/sözleşme/...         açık rıza/yasal               açık rıza/yetkili kurum
       |                          |                            |
       +-- Açık rıza --------+    +-- Açık rıza ------+        +-- Açık rıza
                             |                        |             VEYA
                             v                        v             Sır saklama yükümlüsü
                       AYDINLATMA YÜK.            AYDINLATMA
                       (her zaman)                (her zaman)

İLGİLİ KİŞİ → m.11 Hakları → Veri Sorumlusu → m.13 Yanıt → 30 gün
       |                                                       |
       +-------- Memnun değil → Kurul'a şikayet (60 gün) ------+

VERİ SORUMLUSU vs VERİ İŞLEYEN
   - "Neden + Nasıl" karar veren = Veri Sorumlusu
   - Talimat ile işleyen = Veri İşleyen
   - Aynı tüzel kişi her iki sıfata da girebilir
```

## Bu Bölümle İlişkili Diğer Bölümler

- **02-envanter-ve-sicil:** Veri kategorisi sınıflandırması ve hukuki sebep envantere yansır
- **03-aydinlatma-ve-acik-riza:** Aydınlatma metni ve rıza, hukuki sebep tipine göre yapılandırılır
- **04-veri-saklama-ve-imha:** Hukuki sebep süresi = saklama süresi sonu
- **07-aktarim:** Veri sorumlusu/işleyen ayrımı aktarımın doğasını belirler
- **09-ilgili-kisi-basvurulari:** m.11 hakları operasyonel akışın temeli
- **05-teknik-tedbirler & 06-idari-tedbirler:** Özel nitelikli veriye ek tedbirler buradan tetiklenir
- **10-ozel-konular:** Tedarikçi yönetimi (veri işleyen sözleşmesi)

## Bölüm Sahipliği ve Bakım

- **Doküman sahibi:** KVKK Sorumlusu
- **Onaylayan:** Yönetim Kurulu / Genel Müdür
- **Yıllık gözden geçirme:** Aralık (mevzuat ve Kurul kararları taraması ile)
- **Tetiklenmiş gözden geçirme:** Mevzuat değişikliği (24.03.2024 / 7499 sayılı Kanun benzeri köklü değişikliklerde derhal); bağlayıcı Kurul kararı
- **Eğitim materyali:** Bu bölümdeki dokümanlar yıllık zorunlu KVKK eğitiminin temel modüllerini oluşturur

## Doküman Versiyon Yönetimi

Bu bölümdeki dokümanlar **kavramsal omurga** niteliğindedir; içerik değişiklikleri:
- Mevzuat değişikliği → derhal, versiyon büyük artışı (1.0 → 2.0)
- Kurul kararı entegrasyonu → versiyon küçük artışı (1.0 → 1.1)
- Operasyonel iyileştirme → versiyon nokta artışı (1.0 → 1.0.1)

Versiyon değişikliği, KVKK Komitesi'ne bildirilir; tüm KVKK eğitim materyalleri buna göre güncellenir.
