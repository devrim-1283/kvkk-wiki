---
Doküman: Veri Koruma Etki Değerlendirmesi (DPIA / PIA) Formu
Bölüm: 99-sablonlar
Sahip: KVKK Sorumlusu + Süreç Sahibi
Onaylayan: KVKK Komitesi (yüksek risk durumunda)
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (süreç değişikliği, mevzuat, ihlal sonrası)
İlgili Mevzuat: 6698 sayılı KVKK m.4 (ölçülülük, gereklilik), m.6 (özel nitelikli veri), m.12 (güvenlik); Kurul kararı 2018/10
---

# Veri Koruma Etki Değerlendirmesi (DPIA / PIA)

> **NE ZAMAN ZORUNLU:** Aşağıdaki durumlarda DPIA yapılması zorunlu kabul edilir:
> - Özel nitelikli kişisel veri içeren süreçler (sağlık, biyometrik, ceza mahkumiyeti, dini-siyasi inanç vb.)
> - Büyük hacimli kişisel veri işleme (>10.000 kişi)
> - Profilleme veya otomatik karar alma süreçleri (m.11/g)
> - Yurt dışına aktarım içeren süreçler
> - Yeni teknolojilerin (AI/ML, IoT, biyometrik tanıma, davranışsal izleme) kullanımı
> - CCTV/sürekli izleme sistemleri
> - Çocuklara ait veri işleyen süreçler
> - Kamuya açık alanlarda yaygın izleme
> - Veri sahibinin temel hak ve özgürlüklerine yüksek risk teşkil eden işleme

---

## DPIA FORMU

```
======================================================================
KİŞİSEL VERİ İŞLEME ETKİ DEĞERLENDİRME FORMU (DPIA)
======================================================================

DPIA Referans No  : DPIA-[YIL]-[SIRA]
Düzenleme Tarihi  : ___________________________
Düzenleyen        : ___________________________
Süreç Sahibi Birim: ___________________________
Süreç Sahibi Kişi : ___________________________

----------------------------------------------------------------------
1. SÜREÇ TANIMI
----------------------------------------------------------------------

1.1 Süreç adı:
    ___________________________________________________________________

1.2 Süreç envanteri kayıt no'su:
    ___________________________________________________________________

1.3 Süreç tanımı (1-2 paragraf):
    ___________________________________________________________________
    ___________________________________________________________________
    ___________________________________________________________________

1.4 İşleme amacı / amaçları:
    - Amaç 1: ____________________________________________________
    - Amaç 2: ____________________________________________________

1.5 Hizmet / sistem kullanımı:
    - Sistem 1: ____________________________________________________
    - Sistem 2: ____________________________________________________

1.6 Süreç başlangıç tarihi (planlanan / gerçekleşen):
    ___________________________________________________________________

1.7 İşleme süresi (devamlı / proje):
    ___________________________________________________________________

----------------------------------------------------------------------
2. İŞLENEN KİŞİSEL VERİLER
----------------------------------------------------------------------

2.1 Veri konusu kişi grupları:
    [ ] Çalışanlar
    [ ] Adaylar
    [ ] Müşteriler
    [ ] Potansiyel müşteriler
    [ ] Tedarikçi temsilcileri
    [ ] Çocuklar (özel hassasiyet)
    [ ] Diğer: ___________________________

2.2 Veri kategorileri:
    [ ] Kimlik (ad-soyad, T.C. kimlik no, doğum)
    [ ] İletişim (e-posta, telefon, adres)
    [ ] Lokasyon (GPS, IP)
    [ ] Çevrim içi tanımlayıcı (cookie, cihaz ID)
    [ ] Müşteri işlem (sipariş, fatura)
    [ ] Finans (banka hesap)
    [ ] Görsel/işitsel (CCTV, ses kaydı, fotoğraf)
    [ ] Mesleki/eğitim (CV, sertifika)
    [ ] Pazarlama tercihi
    [ ] Davranış (web, uygulama, ürün kullanımı)
    [ ] ÖZEL NİTELİKLİ:
        [ ] Sağlık
        [ ] Biyometrik
        [ ] Genetik
        [ ] Cinsel hayat
        [ ] Ceza mahkumiyeti / güvenlik tedbiri
        [ ] Dini, felsefi, siyasi inanç
        [ ] Irk, etnik köken
        [ ] Sendika, dernek, vakıf üyeliği
        [ ] Kılık-kıyafet

2.3 Tahmini işlenen kişi sayısı:
    ___________________________________________________________________

2.4 Veri toplama yöntemi:
    [ ] Doğrudan ilgili kişiden
    [ ] Üçüncü taraftan
    [ ] Otomatik (sensör, CCTV, log)
    [ ] Kamuya açık kaynak

----------------------------------------------------------------------
3. VERİ AKIŞ DİYAGRAMI
----------------------------------------------------------------------

```ascii
[Veri Kaynağı]                        [Saklama]
   │                                       ▲
   │                                       │
   ▼                                       │
[Toplama Kanalı] ──► [İşleme Sistem] ──┐  │
   (web/app/                            │  │
    çağrı/manuel)                       │  │
                                        ▼  │
                                  [Aktarım]│
                                   ├─yurt içi
                                   └─yurt dışı
                                        │
                                        ▼
                                  [Üçüncü Taraf]
```
(Kendi süreciniz için diyagramı çiziniz.)

3.1 Veri akış adımları:
    1) Kaynak: ____________________________
    2) Toplama: ____________________________
    3) İşleme: ____________________________
    4) Saklama: ____________________________
    5) Aktarım: ____________________________
    6) İmha: ____________________________

----------------------------------------------------------------------
4. HUKUKİ SEBEP VE ÖLÇÜLÜLÜK
----------------------------------------------------------------------

4.1 İşleme şartları (KVKK m.5/2 ve m.6/2-3):
    [ ] m.5/2-a Kanunda açıkça öngörülme
    [ ] m.5/2-b Hayati zorunluluk
    [ ] m.5/2-c Sözleşme kurulması/ifası
    [ ] m.5/2-ç Hukuki yükümlülük
    [ ] m.5/2-d Alenileştirme
    [ ] m.5/2-e Hakkın tesisi/kullanılması/korunması
    [ ] m.5/2-f Meşru menfaat (LIA gerekli)
    [ ] m.5/1 / m.6/2 Açık rıza
    [ ] m.6/3 Sağlık (sır saklama yükümlü kişi)
    [ ] m.6 (7499 sonrası) Diğer özel nitelikli sebep:
        ___________________________

4.2 GEREKLİLİK TESTİ
    Bu işleme amaca ulaşmak için gerekli midir?
    Daha az müdahaleci alternatifler değerlendirildi mi?
    
    Alternatif 1: ____________________________________ → [Reddedildi/Kabul]
    Alternatif 2: ____________________________________ → [Reddedildi/Kabul]
    
    Sonuç: Bu işleme amaca ulaşmak için
    [ ] gereklidir [ ] alternatif yol seçilebilir

4.3 ÖLÇÜLÜLÜK TESTİ
    İşlenen veri amaçla orantılı mıdır?
    Veri minimizasyonu yapılabilir mi?
    
    İşlenen alanların gerekçesi (her alan için 1 cümle):
    - [Alan 1]: ____________________________
    - [Alan 2]: ____________________________
    - [Alan 3]: ____________________________
    
    Çıkarılabilecek alanlar: ___________________________
    Sonuç: İşleme [ ] ölçülüdür [ ] minimize edilebilir

4.4 SÜRE
    Saklama süresi ve dayanağı:
    ___________________________________________________________________

----------------------------------------------------------------------
5. AKTARIM
----------------------------------------------------------------------

5.1 Yurt içi aktarım:
    | Alıcı | Amaç | İlişki | DPA İmzalı |
    |-------|------|--------|------------|
    |       |      |        |            |

5.2 Yurt dışı aktarım:
    | Alıcı | Ülke | Hukuki Dayanak (m.9) | TIA Yapıldı |
    |-------|------|-----------------------|-------------|
    |       |      |                       |             |

----------------------------------------------------------------------
6. İLGİLİ KİŞİ HAKLARI
----------------------------------------------------------------------

6.1 Aydınlatma metni
    [ ] Süreç için aydınlatma metni mevcut
    Link/Konum: ________________________________
    Hukuk onay tarihi: __________________________

6.2 Açık rıza gerekiyor mu?
    [ ] Evet — rıza metni mevcut: __________________
    [ ] Hayır

6.3 m.11 hakları nasıl yönetilecek?
    - Bilgi: ___________________________
    - Düzeltme: ___________________________
    - Silme: ___________________________
    - Otomatik karara itiraz: ___________________________

6.4 Çocuk verisi varsa özel önlemler:
    ___________________________________________________________________

----------------------------------------------------------------------
7. RİSK HARİTASI
----------------------------------------------------------------------

Her tehdit için: olasılık (1-5) × etki (1-5) = risk skoru

| # | Tehdit | Olasılık | Etki | Skor | Hassasiyet |
|---|--------|----------|------|------|-------------|
| 1 | Yetkisiz erişim (içeriden) |  |  |  |  |
| 2 | Yetkisiz erişim (dışarıdan — siber saldırı) |  |  |  |  |
| 3 | Veri sızıntısı (e-posta, USB, yanlış muhatap) |  |  |  |  |
| 4 | Veri kaybı (donanım arızası, yedekleme hatası) |  |  |  |  |
| 5 | Yanlış veri (eksik, hatalı, güncel olmayan) |  |  |  |  |
| 6 | Aşırı saklama (süre dolmuş veri saklanması) |  |  |  |  |
| 7 | Tedarikçi ihlali |  |  |  |  |
| 8 | Yurt dışı aktarımda koruma eksikliği |  |  |  |  |
| 9 | İlgili kişi hakları kullanılamaması |  |  |  |  |
| 10 | Otomatik karar — adil olmama, ayrımcılık |  |  |  |  |
| 11 | Profilleme — beklenmeyen kullanım |  |  |  |  |
| 12 | Yeniden tanımlanma (anonimleştirme zafiyeti) |  |  |  |  |

Risk düzeyi:
- Düşük (1-6): Standart kontrollerle yönetilir
- Orta (7-12): Ek kontrol önerilir
- Yüksek (13-20): Kontrol zorunlu, KVKK Komitesi onayı
- Kritik (>20): Süreç tasarımının yeniden değerlendirilmesi

----------------------------------------------------------------------
8. ALINAN VE ALINACAK TEDBİRLER
----------------------------------------------------------------------

8.1 Teknik Tedbirler
    [ ] Şifreleme rest (algoritma: ______)
    [ ] Şifreleme transit (TLS sürümü: ______)
    [ ] Erişim yetki kontrolü — RBAC
    [ ] Çok faktörlü kimlik doğrulama (MFA)
    [ ] Ayrıcalıklı erişim yönetimi (PAM)
    [ ] Loglama (saklama: ___ ay)
    [ ] SIEM / anomali tespit
    [ ] Veri kaybı önleme (DLP)
    [ ] Veri maskeleme / pseudonymization
    [ ] Anonimleştirme (test/analitik ortam)
    [ ] Yedekleme (frekans: ___, saklama: ___)
    [ ] Yama yönetimi
    [ ] Sızma testi yıllık
    [ ] Diğer: ___________________________

8.2 İdari Tedbirler
    [ ] Politika ve prosedür
    [ ] Yetki listesi (kim erişebilir, sayı: ___)
    [ ] Eğitim (modül: ______)
    [ ] Gizlilik taahhütnamesi
    [ ] Periyodik denetim
    [ ] Tedarikçi DPA
    [ ] İhlal müdahale planı

8.3 Özel Nitelikli Veri için (Kurul 2018/10) — varsa
    [ ] Tüm gereklilikler değerlendirildi (matriks ekte)

----------------------------------------------------------------------
9. ARTIK RİSK
----------------------------------------------------------------------

Tedbirler sonrası:
| Tehdit (yukarıdan #) | Tedbir Sonrası Skor | Kabul Edilebilir mi |
|----------------------|---------------------|----------------------|
| 1 |  |  |
| 2 |  |  |
| 3 |  |  |
| ... |  |  |

Genel artık risk değerlendirmesi:
[ ] Düşük — kabul edilebilir
[ ] Orta — kabul edilebilir, ek izleme
[ ] Yüksek — ek tedbir gerekli, KVKK Komitesi onayı
[ ] Kritik — süreç başlatılmamalı / askıya alınmalı

----------------------------------------------------------------------
10. KVKK SORUMLUSU GÖRÜŞÜ
----------------------------------------------------------------------

Görüş özeti:
___________________________________________________________________
___________________________________________________________________

[ ] Onaylıyorum
[ ] Şartlı onaylıyorum (şartlar): _______________________________
[ ] Onaylamıyorum (gerekçe): ___________________________________

Ad-Soyad: ___________________________
Tarih   : ___________________________
İmza    : ___________________________

----------------------------------------------------------------------
11. ONAYLAR
----------------------------------------------------------------------

Süreç Sahibi:
Ad-Soyad: ____________________ Tarih: __________ İmza: __________

Hukuk Müşaviri:
Ad-Soyad: ____________________ Tarih: __________ İmza: __________

KVKK Sorumlusu:
Ad-Soyad: ____________________ Tarih: __________ İmza: __________

KVKK Komitesi (yüksek risk için):
Toplantı No / Tarih: ___________________________
Karar: [ ] Onay [ ] Şartlı [ ] Ret

----------------------------------------------------------------------
12. GÖZDEN GEÇİRME TAKVİMİ
----------------------------------------------------------------------

- İlk gözden geçirme tarihi: 6 ay sonra
- Sonraki periyodik gözden geçirme: yıllık
- Tetiklenmiş gözden geçirme:
  - Süreç değişikliği
  - Mevzuat değişikliği
  - İhlal sonrası
  - Tedarikçi değişikliği
  - Yeni veri kategorisi eklenmesi

======================================================================
```

## DPIA Yöntemi — Pratik İpuçları

### Ne Zaman DPIA Yapılır?

- Süreç tasarımı **başlamadan önce** (Privacy by Design)
- Önemli süreç değişikliği (yeni alıcı, yeni amaç, yeni veri kategorisi)
- İhlal sonrası kök neden analizi parçası
- Yıllık tazeleme (yüksek riskli süreçler)

### Kim Yapar?

- **Liderlik:** KVKK Sorumlusu
- **Süreç bilgisi:** Süreç Sahibi
- **Hukuki dayanak:** Hukuk Müşaviri
- **Teknik bilgi:** BT / Bilgi Güvenliği
- **İlgili kişi perspektifi:** mümkünse anket veya odak grubu

### Belgelendirme

- DPIA dosyası GRC platformunda
- 5 yıl saklama (denetim hazırlığı için 7 yıl)
- KVKK Sorumlusu indeksli liste
- Yıllık iç denetim örneklemi

## İlgili Dokümanlar

- [meşru-menfaat-degerlendirmesi.md](meşru-menfaat-degerlendirmesi.md)
- [../12-mevzuat-arsiv/kurul-kararlari-ozeti.md](../12-mevzuat-arsiv/kurul-kararlari-ozeti.md)
- [../10-ozel-konular/](../10-ozel-konular/)
- [../05-teknik-tedbirler/](../05-teknik-tedbirler/)
