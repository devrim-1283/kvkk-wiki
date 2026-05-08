---
Doküman: Envanter Bakım, Gözden Geçirme ve Değişiklik Yönetimi
Bölüm: 02-envanter-ve-sicil
Sahip: KVKK Sorumlusu
Onaylayan: Hukuk Müdürü + KVKK Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Çeyreklik (operasyonel) + Yıllık (tam revizyon) + Tetiklenmiş
İlgili Mevzuat: 6698 sayılı KVKK m.10, m.12, m.16; Veri Sorumluları Sicili Hakkında Yönetmelik MADDE 5, 9, 13; Aydınlatma Tebliği MADDE 5; Saklama ve İmha Yön. MADDE 5
---

# Envanter Bakımı, Gözden Geçirme ve Değişiklik Yönetimi

Envanter bir kez yapılıp bırakılan bir doküman değildir. Yön. M.5/d uyarınca aydınlatma yükümlülüğü, ilgili kişi başvurularının cevaplanması ve açık rızanın belirlenmesinde envantere dayalı Sicil bilgileri **esas alınır**. Bu nedenle envanter güncel kalmadığında **bir bütün uyum mimarisi yanlışlaşır**.

Bu doküman, envanterin nasıl güncel tutulacağına ilişkin operasyonel rejimi tanımlar.

## 1. Üç Katmanlı Bakım Modeli

| Katman | Sıklık | Amaç |
|--------|--------|------|
| Sürekli (event-driven) | Anlık | Süreç değişikliği olur olmaz envanter güncellenir; VERBİS bildirimi 7 gün içinde |
| Çeyreklik gözden geçirme | 3 ayda bir | Süreç sahipleri ve KVKK Sorumlusu satır bazlı doğrulama |
| Yıllık tam revizyon | Yılda bir | Tüm envanterin baştan tamamı, mevzuat ve organizasyon değişiklikleriyle uyumlandırma |

## 2. Sürekli Bakım — Olay Tabanlı

### 2.1 Değişiklik Tetikleyicileri

Aşağıdaki olayların **herhangi biri** envanteri günceller:

| # | Tetikleyici | Etkilenen alan | Aksiyon |
|---|-------------|----------------|---------|
| 1 | Yeni süreç başlatılması | Yeni satır ekleme | Süreç başlamadan envanter satırı + VERBİS güncelleme |
| 2 | Mevcut süreçte yeni amaç eklenmesi | İşleme amacı, hukuki sebep | Hukuk Müdürlüğü teyidi → güncelleme |
| 3 | Yeni veri kategorisi işlenmeye başlanması | Veri kategorisi, kişisel veri öğeleri | Aydınlatma metni de güncellenir |
| 4 | Yeni kişi grubu (örn. ilk kez ziyaretçi izleme başlatma) | Veri konusu kişi grubu | Aydınlatma metni + tabela hazırlığı |
| 5 | Yeni sistem/SaaS devreye alma | Kayıt ortamı, teknik tedbirler, yurt dışı aktarım | Bilgi Güvenliği değerlendirmesi |
| 6 | Yeni tedarikçi (veri işleyen) | Alıcı/alıcı grubu | Veri işleyen sözleşmesi imzala, sonra ekle |
| 7 | Yurt dışı aktarımın başlatılması | Yurt dışı aktarım, hukuki temel | KVKK m.9 hukuki temel hazırlığı |
| 8 | Bir aktarımın durdurulması | Alıcı/alıcı grubu | İlgili satırdan çıkar; gerekçeyi versiyon notuna yaz |
| 9 | Saklama süresi değişimi (mevzuat veya iç politika) | Saklama süresi, gerekçe | İmha politikası ile uyumlandır |
| 10 | Mevzuat değişikliği (kanun, yönetmelik, Kurul kararı) | Hukuki sebep, saklama süresi, aktarım | Hukuk Müdürlüğü gözden geçirir |
| 11 | Organizasyon değişikliği (birim oluşturma/kapatma, görev devri) | Süreç sahibi, iş birimi | Sahiplik güncellemesi |
| 12 | M&A (birleşme, devralma, bölünme) | Tüm envanter | Tam revizyon — yeni veri sorumlusu/eski kayıtlar |
| 13 | Veri ihlali tespiti | Teknik tedbirler, risk seviyesi | İhlal değerlendirme + iyileştirme |
| 14 | Yeni teknik tedbir devreye alma | Teknik tedbirler | Bilgi Güvenliği güncelleme |
| 15 | Bir tedbirin kaldırılması | Teknik/idari tedbirler | Kalkma sebebi + telafi tedbiri |
| 16 | Yeni hukuki yükümlülük (örn. yeni vergi mevzuatı, yeni sektörel düzenleme) | Hukuki sebep, saklama süresi | Hukuk Müdürlüğü |
| 17 | Açık rıza politikası değişikliği | Açık rıza gerekli mi, ilgili rıza metni | CMP güncelleme |
| 18 | Aydınlatma metni güncellemesi | Aydınlatma metni atfı | Versiyon takibi |
| 19 | İlgili kişi başvurusu ya da Kurul incelemesi sonucu çıkan eksiklik | İlgili satır(lar) | Düzeltme + iç bildirim |

### 2.2 Tetikleyici → Güncelleme Zinciri

```
Olay tespiti
    │
    ▼
Süreç Sahibi → KVKK Sorumlusu (ticket veya e-posta, max 5 iş günü)
    │
    ▼
Envanter satırı taslak güncelleme (KVKK Sorumlusu, 2 iş günü)
    │
    ▼
Hukuk Müdürlüğü teyidi (gerektiği takdirde, max 3 iş günü)
    │
    ▼
Bilgi Güvenliği teyidi (teknik tedbir varsa, max 3 iş günü)
    │
    ▼
KVKK Komitesi kabulü (kapsamlı değişiklikler, gerektiğinde)
    │
    ▼
Envanter v.X.Y yayını + değişiklik logu
    │
    ▼
VERBİS güncellemesi (Yön. M.13, 7 gün) ← KRİTİK
    │
    ▼
Aydınlatma metni / saklama-imha politikası / sözleşme uyum kontrolü
    │
    ▼
İlgili paydaşlara bildirim (süreç sahibi, eğitim listesi)
```

### 2.3 Olay Bildirim Şablonu

Süreç sahipleri aşağıdaki formatta KVKK Sorumlusu'na bildirim yapar:

```
ENVANTER GÜNCELLEME TALEBİ
=========================================

Tarih:                YYYY-AA-GG
Süreç ID:             [örn. IK-001]
Süreç Adı:            [...]
Talep Eden:           [Ad-Soyad / Görev]

Değişiklik Türü:
[ ] Yeni satır
[ ] Mevcut satır revizyonu
[ ] Satır arşivleme (süreç durduruldu)

Etkilenen Alanlar:
[ ] Veri kategorisi      [ ] Kişisel veri öğeleri
[ ] İşleme amacı         [ ] Hukuki sebep
[ ] Toplama yöntemi      [ ] Kayıt ortamı
[ ] Yurt içi alıcı       [ ] Yurt dışı aktarım
[ ] Saklama süresi       [ ] İmha yöntemi
[ ] Teknik tedbir        [ ] İdari tedbir

Değişiklik Açıklaması:
[Detaylı metin]

Yeni Durum (eski → yeni):
- Alan: [...]  →  [...]

Etki Analizi:
- Aydınlatma metni güncellenecek mi? [E/H]
- Açık rıza gerekecek mi? [E/H]
- VERBİS bildirimi etkilenecek mi? [E/H]
- Sözleşmeler etkilenecek mi? [E/H]

Önerilen Yürürlük Tarihi: YYYY-AA-GG
```

## 3. Çeyreklik Gözden Geçirme

### 3.1 Kapsam

Her çeyrekte **tüm envanter** satırları aşağıdaki kontrollerden geçer:

- [ ] Süreç sahibi hâlâ doğru mu? (organizasyon değişikliği)
- [ ] İşleme amacı operasyonel gerçeklikle örtüşüyor mu?
- [ ] Hukuki sebep güncel mi?
- [ ] Yeni alıcılar eklendi mi?
- [ ] Yurt dışı aktarım kontrol noktası: SaaS sunucu lokasyonları doğrulandı mı?
- [ ] Saklama süresi mevzuatla uyumlu mu (yıl içi mevzuat değişikliği)?
- [ ] Teknik tedbirler güncel mi (yeni güvenlik kontrolü, kaldırılan kontrol)?
- [ ] Risk seviyesi gerçekçi mi?
- [ ] Aydınlatma metnine atıf doğru ve güncel mi?

### 3.2 Çeyreklik Gözden Geçirme Toplantısı

Katılımcılar:
- KVKK Sorumlusu (toplantı sahibi)
- Tüm Süreç Sahipleri (kendi satırlarına göre)
- Hukuk Müdürlüğü temsilcisi
- Bilgi Güvenliği temsilcisi
- KVKK Komitesi gözlemci sıfatıyla

Süre: Yarım gün (kapsama göre 4-8 saat).

Çıktılar:
- Çeyreklik gözden geçirme raporu
- Eylem listesi (sahip + tarih)
- Versiyon güncellemesi

### 3.3 Çeyreklik Gözden Geçirme Şablonu

```
ÇEYREKLİK ENVANTER GÖZDEN GEÇİRME RAPORU
==========================================

Çeyrek:               [QX YYYY]
Toplantı Tarihi:      YYYY-AA-GG
Katılımcılar:         [İsimler]

1. ENVANTER METRİKLERİ
   - Toplam satır sayısı           : [n]
   - Yeni eklenen                  : [n]
   - Güncellenen                   : [n]
   - Arşivlenen (durdurulan süreç) : [n]
   - Yüksek/Kritik risk satırlar   : [n]

2. UYUM METRİKLERİ
   - VERBİS güncellenme zamanında mı? : [E/H]
   - Aydınlatma uyumu              : [%]
   - Saklama-imha uyumu            : [%]
   - Teknik tedbir uyumu           : [%]

3. AÇIK KONULAR
   [ID] [Konu] [Sahip] [Hedef Tarih]

4. KARAR LİSTESİ
   [...]

5. SONRAKİ TOPLANTI
   Tarih: YYYY-AA-GG
```

## 4. Yıllık Tam Revizyon

### 4.1 Kapsam

Yılda bir kez (ideal: takvim yılı sonu) envanter **tamamen** baştan ele alınır:

| Adım | İçerik |
|------|--------|
| 1 | Tüm envanter satırlarının süreç sahiplerine yeniden onayı |
| 2 | Mevzuat değişiklikleri taraması (Kanun, Yönetmelik, Kurul kararları) |
| 3 | Sektörel rehber güncellemelerinin değerlendirilmesi |
| 4 | Aydınlatma metinleri ile karşılıklı uyum |
| 5 | Saklama-imha politikası ile karşılıklı uyum |
| 6 | Sözleşme stoğu (veri işleyen, aktarım) ile uyum |
| 7 | Risk değerlendirmesi (özellikle özel nitelikli veri) |
| 8 | Olgunluk seviyesi ölçümü (1-5 arası) |
| 9 | Yıllık iyileştirme planı |

### 4.2 Yıllık Revizyon Çıktısı

- Versiyon **MAJOR** artırılır (örn. v1.0 → v2.0)
- Yıllık değerlendirme raporu
- KVKK Komitesi onayı
- Yönetim Kurulu özeti
- VERBİS toplu güncelleme (gerekirse)

## 5. Uyum Kontrol Listesi (Zincir)

Envanter, KVKK uyumunun **merkezi** dokümanıdır. Aşağıdaki "uyum zinciri" sürekli kontrol edilir:

```
Envanter ↔ VERBİS bildirimi ↔ Aydınlatma metni ↔ Açık rıza metni ↔ Saklama-imha politikası ↔ Sözleşmeler
```

### 5.1 Envanter ↔ VERBİS

- [ ] Envanterdeki amaçlar VERBİS'te yer alıyor mu?
- [ ] VERBİS'teki kategoriler envanterde de var mı?
- [ ] Yurt dışı aktarım her iki yerde de doğru bildirilmiş mi?
- [ ] Saklama süreleri tutarlı mı?
- [ ] Yeni süreçler 7 gün içinde VERBİS'e yansıdı mı (Yön. M.13)?

### 5.2 Envanter ↔ Aydınlatma Metinleri

- [ ] Her süreç için aydınlatma metni var mı (Aydınlatma Tebliği M.5/c)?
- [ ] Aydınlatma metnindeki amaçlar envanterdeki amaçlarla aynı mı?
- [ ] Aydınlatma metnindeki hukuki sebep envanterle aynı mı (Tebliğ M.5/h)?
- [ ] Aydınlatma metnindeki alıcı grupları envanterle aynı mı (Tebliğ M.5/ı)?
- [ ] Yurt dışı aktarım bilgisi tutarlı mı?
- [ ] Toplama yöntemi (otomatik/otomatik olmayan) tutarlı mı (Tebliğ M.5/i)?

### 5.3 Envanter ↔ Açık Rıza Metinleri

- [ ] Envanterde "açık rıza" gösterilen tüm satırlarda gerçekten rıza alınıyor mu?
- [ ] Rıza alma kanalı (form, CMP, sözlü kayıt) belgelendi mi?
- [ ] Rıza geri alma mekanizması var mı?
- [ ] Rıza alınmamış olduğu halde envanterde "açık rıza" gösterilen var mı? (yok olmalı)

### 5.4 Envanter ↔ Saklama ve İmha Politikası

- [ ] Saklama süreleri tutarlı mı?
- [ ] İmha yöntemi belirtilmiş mi?
- [ ] Periyodik imha 6 ay içinde gerçekleşiyor mu?
- [ ] İmha tutanakları arşivde mi?
- [ ] Mevzuat değişikliği sonrası saklama süresi yenilendi mi?

### 5.5 Envanter ↔ Sözleşmeler

- [ ] Veri işleyen sözleşmesi her tedarikçi için imzalandı mı?
- [ ] Aktarım sözleşmeleri (yurt dışı için standart sözleşme) var mı?
- [ ] Sözleşmedeki amaçlar envanterle örtüşüyor mu?
- [ ] Sözleşme süresi sona erdiyse yenilendi mi?

## 6. Çeyreklik Çapraz Kontrol Matrisi

| Kontrol | Çeyreklik (Q1-Q4) | Yıllık | Tetiklenmiş |
|---------|---|---|---|
| Envanter satır doğrulaması | E | E | E |
| VERBİS uyum | E | E | E |
| Aydınlatma metni güncellik | E | E | E |
| Saklama süresi mevzuat uyumu | — | E | E |
| Sözleşme stoğu güncelliği | — | E | E (yeni tedarikçide) |
| Risk değerlendirmesi | — | E | E (yeni süreç, ihlal) |
| Olgunluk seviyesi ölçümü | — | E | — |

## 7. Sahiplik Modeli ve RACI

| Aktivite | Süreç Sahibi | KVKK Sorumlusu | Hukuk | Bilgi Güvenliği | KVKK Komitesi | Yönetim Kurulu |
|----------|---|---|---|---|---|---|
| Yeni süreç envanter satırı | R | A | C | C | I | I |
| Çeyreklik gözden geçirme | C | A/R | C | C | I | I |
| Yıllık revizyon | C | R | C | C | A | I |
| VERBİS güncellemesi | I | A/R | C | I | I | I |
| Olağan dışı (Kurul incelemesi vb.) | C | R | A | C | A | I |
| M&A kapsamı | C | A | C | C | C | A |

R = Responsible | A = Accountable | C = Consulted | I = Informed

## 8. Versiyonlama Disiplini

### 8.1 Versiyon Numarası

Format: `MAJOR.MINOR.PATCH`
- **MAJOR:** Yıllık tam revizyon, mimari değişiklik (yeni kolon, kapsamlı yeniden düzenleme)
- **MINOR:** Yeni süreç eklemesi, mevcut satırın anlamlı revizyonu, yeni mevzuat uyarlaması
- **PATCH:** Yazım, format, bağlantı düzeltmesi

### 8.2 Değişiklik Kütüğü Şablonu

Envanter dosyasının yanında `degisiklik-kutugu.md` tutulur:

```
| Versiyon | Tarih | Tip | Değişiklik | Hazırlayan | Onaylayan |
|----------|-------|-----|-----------|-----------|-----------|
| 1.0.0    | 2026-05-08 | İlk yayım | İlk envanter yayını | KVKK Sor. | KVKK Komitesi |
| 1.1.0    | 2026-06-15 | MINOR | IK-011 (Stajyer Yönetimi) eklendi | KVKK Sor. | Hukuk Müd. |
| 1.1.1    | 2026-06-22 | PATCH | IK-001 saklama gerekçesi netleştirildi | KVKK Sor. | KVKK Sor. |
```

## 9. Operasyonel Risk Göstergeleri (KPI)

| KPI | Hedef | Uyarı eşiği | Kritik eşik |
|-----|-------|-------------|-------------|
| VERBİS güncelleme süresi | ≤ 5 gün | > 5 gün | > 7 gün (mevzuat ihlali) |
| Çeyreklik gözden geçirme tamamlanma | %100 | < %95 | < %85 |
| Süreç sahibi onaylanmamış satır | 0 | > 0 | > 5 |
| Aydınlatma metni eksik süreç | 0 | > 0 | > 2 |
| Yüksek/Kritik risk satırları için yıllık denetim | %100 | < %100 | < %95 |
| Saklama süresi mevzuat uyumsuzluğu | 0 | > 0 | > 1 |

## 10. Yıllık Denetim Hazırlığı

KVKK Kurul incelemesi veya iç denetim öncesi şu paket hazırlanır:

| Doküman | İlgili madde |
|---------|-------------|
| Güncel envanter (PDF + Excel) | Yön. M.4(h), 5(ç) |
| VERBİS bildirim PDF özeti | Yön. M.10 |
| Saklama ve imha politikası | Saklama ve İmha Yön. M.5 |
| Tüm aydınlatma metinleri (kanal bazında) | Aydınlatma Tebliği M.5 |
| Açık rıza metinleri ve örnek logları | KVKK m.5/1, m.6/2 |
| Veri işleyen sözleşme stoğu | KVKK m.12/2 |
| Yurt dışı aktarım sözleşmeleri / standart sözleşme | KVKK m.9 |
| Çeyreklik gözden geçirme raporları | İç doküman |
| Veri ihlali bildirim kayıtları (varsa) | KVKK m.12/5 |
| İlgili kişi başvuru ve cevap kayıtları | KVKK m.13, Başvuru Tebliği |
| Eğitim ve farkındalık kayıtları | KVKK m.12/1 idari tedbir |

## 11. Kontrol Listesi — Bakım Düzeni Kuruldu mu?

- [ ] Çeyreklik gözden geçirme takvimi kuruldu (Q1-Q4 tarihler)
- [ ] Yıllık tam revizyon ay-tarihi belirlendi
- [ ] Olay bildirim ticket sistemi (JIRA, ServiceNow vb.) kuruldu
- [ ] Süreç sahipleri eğitildi
- [ ] KVKK Komitesi gündemi tanımlandı
- [ ] VERBİS güncelleme sorumluluğu netleştirildi
- [ ] Versiyonlama disiplini belgelendi
- [ ] KPI ölçüm yöntemi tanımlı
- [ ] Yıllık denetim için doküman seti hazır
- [ ] Mevzuat takip kanalı kuruldu (KVKK Kurum bültenleri, Resmi Gazete)

## 12. Ekler

- Envanter Rehberi: [kvki-envanteri-rehberi.md](./kvki-envanteri-rehberi.md)
- Şablon: [envanter-sablonu.md](./envanter-sablonu.md)
- VERBİS Kayıt: [verbis-kayit-rehberi.md](./verbis-kayit-rehberi.md)
- İstisna Değerlendirme: [verbis-istisna-degerlendirmesi.md](./verbis-istisna-degerlendirmesi.md)
