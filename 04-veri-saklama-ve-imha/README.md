---
Doküman: Veri Saklama ve İmha — Bölüm Girişi
Bölüm: 04-veri-saklama-ve-imha
Sahip: KVKK Sorumlusu
Onaylayan: Hukuk Müdürü + Bilgi Güvenliği Yöneticisi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (mevzuat değişikliği, yeni veri kategorisi, sistem değişikliği, ihlal sonrası kök neden)
İlgili Mevzuat: 6698 sayılı KVKK m.4, m.5, m.6, m.7, m.12, m.16; Kişisel Verilerin Silinmesi, Yok Edilmesi veya Anonim Hale Getirilmesi Hakkında Yönetmelik (28.10.2017 / 30224, yürürlük 01.01.2018) m.5–m.12; Veri Güvenliği Rehberi (Teknik ve İdari Tedbirler); 213 sayılı VUK; 6102 sayılı TTK; 4857 sayılı İş K.; 5510 sayılı SGK Kanunu; 6098 sayılı TBK; 5651 sayılı Kanun
---

# Bölüm 04 — Veri Saklama ve İmha

## 1. Bölümün Amacı

Bu bölüm, veri sorumlusunun KVKK m.7 ve Kişisel Verilerin Silinmesi, Yok Edilmesi veya Anonim Hale Getirilmesi Hakkında Yönetmelik kapsamındaki tüm yükümlülüklerini operasyonel düzeyde uygulanabilir hale getirir. KVKK m.4(2)(d) hükmü uyarınca kişisel veriler "ilgili mevzuatta öngörülen veya işlendikleri amaç için gerekli olan süre kadar" muhafaza edilir. Bu süre dolduğunda veri sorumlusu, **resen** veya **ilgili kişinin talebi üzerine** silme, yok etme veya anonim hale getirme yükümlülüğü altındadır.

İlgili Yönetmelik, VERBİS'e kayıt yükümlülüğü olan veri sorumluları için **Kişisel Veri Saklama ve İmha Politikası** hazırlanmasını zorunlu kılar (Yön. m.5(1)). 500+ çalışanlı veri sorumlusu kurumlar — istisnai sektörel muafiyetler dışında — bu yükümlülük kapsamındadır.

## 2. Bölüm İçeriği

| # | Doküman | Amaç |
|---|---------|------|
| 1 | [README.md](README.md) | Bölüm girişi (bu doküman) |
| 2 | [saklama-imha-politikasi-sablonu.md](saklama-imha-politikasi-sablonu.md) | Yön. m.6 asgari içeriği karşılayan tam politika şablonu |
| 3 | [saklama-sureleri-tablosu.md](saklama-sureleri-tablosu.md) | 30+ veri kategorisi için süre tablosu |
| 4 | [imha-yontemleri.md](imha-yontemleri.md) | Silme, yok etme ve anonim hale getirme yöntemleri; ortam bazlı matris |
| 5 | [periyodik-imha-prosedur.md](periyodik-imha-prosedur.md) | Periyodik ve tetiklenmiş imha akışları |
| 6 | [imha-kayit-tutanagi-sablonu.md](imha-kayit-tutanagi-sablonu.md) | Yön. m.7(3) gereği 3 yıl saklanacak imha tutanağı şablonları |

## 3. Temel Kavramlar (Yön. m.4)

- **İmha:** Kişisel verilerin silinmesi, yok edilmesi veya anonim hale getirilmesini ifade eder.
- **Silme (Yön. m.8):** Kişisel verilerin **ilgili kullanıcılar** için hiçbir şekilde erişilemez ve tekrar kullanılamaz hale getirilmesi.
- **Yok etme (Yön. m.9):** Kişisel verilerin **hiç kimse** tarafından hiçbir şekilde erişilemez, geri getirilemez ve tekrar kullanılamaz hale getirilmesi.
- **Anonim hale getirme (Yön. m.10):** Kişisel verilerin başka verilerle eşleştirilse dahi hiçbir surette kimliği belirli veya belirlenebilir bir gerçek kişiyle ilişkilendirilemeyecek hale getirilmesi.
- **Periyodik imha:** İşleme şartlarının tamamı ortadan kalktığında, politikada belirtilen tekrar eden aralıklarla resen gerçekleştirilen imha (azami 6 ay).
- **İlgili kullanıcı:** Veri sorumlusu organizasyonu içerisinde veya yetki/talimat doğrultusunda kişisel verileri işleyen kişiler. Verilerin teknik olarak depolanması, korunması ve yedeklenmesinden sorumlu kişi/birim **bu tanımın dışındadır**.

## 4. Yükümlülük Üçgeni

```
                    KVKK m.4(2)(d)
                "Gerekli süre kadar saklama"
                        |
                        v
          +-------------+--------------+
          |                            |
          v                            v
    KVKK m.7                      Yön. m.5–m.12
"İşleme şartları             "Politika + süreler +
ortadan kalkınca imha"        yöntem + tutanak"
          |                            |
          +-------------+--------------+
                        |
                        v
                 KVKK m.12
            "Teknik+idari tedbir"
```

Üç yükümlülük birbirini tamamlar. Süreler doldu ama imha yapılmadıysa m.4 ihlali; imha yapılıyor ama yöntem/tutanak yoksa Yönetmelik ihlali; imha yöntemi seçilmiş ama yetersizse m.12 ihlali oluşur.

## 5. Sorumluluklar

| Rol | Sorumluluk |
|-----|------------|
| Yönetim Kurulu | Politikanın onayı, kaynak tahsisi, denetim sonuçlarının değerlendirilmesi |
| KVKK Sorumlusu | Politikanın yazımı, sürelerin envanter ile uyumu, periyodik imha koordinasyonu, ilgili kişi taleplerinin yönetimi |
| Hukuk Müdürlüğü | Saklama süreleri için mevzuat tarama, dava/itiraz nedeniyle hukuki muhafaza (legal hold) kararları |
| Bilgi Güvenliği | İmha yöntemlerinin teknik tasarımı, kanıt toplama (hash, log), güvenli imha tedarikçileri |
| BT Operasyon | İmha işlemlerinin sistemler üzerinde uygulanması, retention job'ların çalıştırılması |
| İnsan Kaynakları | Çalışan/aday verilerinin sürelerinin yönetimi |
| Tedarikçi/Satınalma | Veri işleyenlerin imha taahhütlerinin sözleşmelere yansıtılması |

## 6. Bu Bölümün Diğer Bölümlerle İlişkisi

- **02 — Envanter ve Sicil:** Saklama süreleri envanter ile birebir tutarlı olmalıdır. VERBİS'teki azami süreler bu bölümdeki tablodan beslenir.
- **03 — Aydınlatma ve Açık Rıza:** Aydınlatma metinlerinde belirtilen süreler bu politika ile aynı olmalıdır.
- **05 — Teknik Tedbirler:** İmha yöntemlerinin teknik altyapısı (kripto-silme, anahtar yönetimi, donanım imhası).
- **08 — İhlal Yönetimi:** İhlal kayıtları ve forensic verisi için saklama süreleri istisna oluşturabilir (legal hold).
- **09 — İlgili Kişi Başvuruları:** m.12 silme/yok etme talepleri 30 gün içinde sonuçlandırılır.

## 7. Denetim Frekansı

- **Aylık:** Retention job çıktıları, manuel imha tutanakları
- **Çeyreklik:** Politika ile envanter/aydınlatma uyumu kontrolü
- **Yıllık:** Politikanın bütünsel gözden geçirilmesi, mevzuat değişikliği taraması
- **Tetiklenmiş:** Mevzuat değişikliği, yeni iş süreci, sistem değişikliği, ihlal kök neden analizi
