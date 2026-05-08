---
Doküman: Veri İhlali Bildirim Şablonları (Kurul ve İç Triyaj)
Bölüm: 99-sablonlar
Sahip: KVKK Sorumlusu + Hukuk Müşavirliği
Onaylayan: KVKK Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş
İlgili Mevzuat: 6698 sayılı KVKK m.12/5; KVKK Kurulu 24.01.2019 tarihli ve 2019/10 sayılı Karar
---

# Veri İhlali Bildirim Şablonları

## 1. Süre Disiplini

| Adım | Süre |
|------|------|
| İhlal şüphesi tespit | T0 |
| İç triyaj tamamlanır | T0 + 6 saat |
| KVKK Komitesi (kriz) bilgilendirilir | T0 + 12 saat |
| Kurul'a bildirim taslağı hazır | T0 + 36 saat |
| Hukuk + KVKK Sor. nihai onay | T0 + 60 saat |
| Kurul'a bildirim gönderilir | T0 + 72 saat (en geç) |
| İlgili kişiye bildirim (en kısa sürede) | T0 + 7 gün (genel hedef) |

> Kurul'a 72 saatten geç bildirim halinde **gecikme nedeni yazılı olarak açıklanmalıdır** (Kurul kararı 2019/10).

---

## 2. ŞABLON A — İÇ TRİYAJ FORMU

```
==========================================================
VERİ İHLALİ İÇ TRİYAJ FORMU
==========================================================

İhlal Referans No: IH-[YIL]-[SIRA]
Düzenlenme Tarihi/Saati: [TARİH SAAT]
Düzenleyen: [AD-SOYAD - ROL]

A. İHLAL ŞÜPHESİ KAYNAĞI
[ ] SOC / SIEM uyarısı
[ ] Çalışan bildirimi
[ ] Tedarikçi bildirimi
[ ] İlgili kişi şikâyeti
[ ] Medya / üçüncü kişi
[ ] İç denetim
[ ] Diğer: ___________________

B. İLK TESPİT BİLGİLERİ
- Tespit tarihi/saati (T0):
- İhlalin gerçekleştiği tahmini tarih:
- Tespit ile ihlal arası gecikme (MTTD):
- Tespit eden kişi:

C. İHLALİN NİTELİĞİ (KVKK m.12/5 ve Kurul 2019/10)
[ ] Gizliliğin ihlali (yetkisiz açıklama, sızıntı)
[ ] Bütünlüğün ihlali (yetkisiz değişiklik, bozulma)
[ ] Erişilebilirliğin ihlali (kayıp, silme, fidye, hizmet kesintisi)
[ ] Birden fazla niteliğin ihlali

D. ETKİLENEN SİSTEM/SÜREÇ
- Sistem: ___________________
- Süreç (envanterden): ___________________
- Süreç sahibi birim: ___________________

E. İHLAL TÜRÜ
[ ] Dış saldırı (siber)
[ ] İç hata / yanlışlık
[ ] İç kötüye kullanım
[ ] Tedarikçi / üçüncü taraf kaynaklı
[ ] Fiziksel (kayıp, hırsızlık, basılı evrak)
[ ] Cihaz kaybı / çalıntı (laptop, USB, telefon)
[ ] Yanlış muhatap (e-posta, kargo)
[ ] Sosyal mühendislik / phishing
[ ] Diğer: ___________________

F. ETKİLENEN VERİLER
- Veri kategorileri: ___________________
- Özel nitelikli veri var mı: [Evet/Hayır] — Detay: ___________________
- Çocuk verisi var mı: [Evet/Hayır]
- Tahmini etkilenen kişi sayısı: ___________________
- Veri konusu kişi grubu: [Çalışan/Müşteri/Aday/Tedarikçi/Diğer]

G. İHLAL ÖLÇEĞİ İLK DEĞERLENDİRMESİ
[ ] DÜŞÜK — sınırlı kayıt, hassas olmayan veri, hızlı kapatma
[ ] ORTA — orta hacim, sınırlı hassasiyet
[ ] YÜKSEK — yüksek hacim VEYA özel nitelikli veri VEYA yurt dışı etki
[ ] KRİTİK — büyük hacim + özel nitelikli + medya/itibar etkisi VEYA
   tüketici hakları toplu zarara uğramış

H. İLK MÜDAHALE (T0 + 4 saat içinde)
- Kapsama alma (containment) yapıldı mı: [Evet/Hayır] — Detay:
- Yetkisiz erişim engellendi mi:
- Etkilenen sistem izole edildi mi:
- Adli koruma (forensic preservation) yapıldı mı:

I. KÖK NEDEN ÖN ANALİZİ
[ ] Yetki yönetim hatası
[ ] Yama eksikliği / güvenlik açığı
[ ] Yapılandırma hatası
[ ] Sosyal mühendislik
[ ] Eğitim eksikliği
[ ] Tedarikçi süreç hatası
[ ] Politika ihlali
[ ] Bilinmiyor (henüz tespit edilmedi)

J. EŞZAMANLI BİLDİRİMLER
[ ] CISO / BT Müdürü
[ ] KVKK Sorumlusu
[ ] Hukuk Müşavirliği
[ ] Genel Müdür
[ ] İletişim Direktörü
[ ] İç Denetim
[ ] Yön. Kur. Denetim Komitesi (kritik durumda)

K. KURUL BİLDİRİM ZORUNLULUĞU DEĞERLENDİRMESİ
- Bu ihlal 72 saat içinde Kurul'a bildirilecek mi: [Evet/Hayır/Değerlendirmede]
- Hayır ise gerekçe: ___________________
- İlgili kişiye bildirim yapılacak mı: [Evet/Hayır] — Yöntem: ___________________

L. EKİP ATAMA
- İhlal Müdahale Sorumlusu: ___________________
- Hukuki muhatap: ___________________
- Teknik müdahale lideri: ___________________
- İletişim sorumlusu: ___________________
- KVKK Sor. (Kurul muhatap): ___________________

M. SONRAKİ ADIMLAR
- T0 + 12 saat: KVKK Komitesi olağanüstü toplantı
- T0 + 24 saat: Detaylı kök neden analizi başlatılır
- T0 + 36 saat: Kurul bildirim taslağı tamamlanır
- T0 + 72 saat: Kurul bildirimi gönderilir
- T0 + 7 gün: İlgili kişi bildirimi tamamlanır
- T0 + 30 gün: Kapanış raporu

==========================================================
Onay
- Düzenleyen: ___________________ (imza, tarih)
- KVKK Sorumlusu: ___________________
- Hukuk Müşaviri: ___________________
==========================================================
```

---

## 3. ŞABLON B — KVKK KURULU'NA VERİ İHLALİ BİLDİRİMİ

> Kurul'un yayımladığı standart formdan üretilmiştir (24.01.2019 tarihli ve 2019/10 sayılı Karar). Form, Kurum'un VERBİS portalı veya kvkk.gov.tr/Bildirim sayfası üzerinden gönderilir.

```
==========================================================
KİŞİSEL VERİ İHLALİ BİLDİRİM FORMU
KVKK Madde 12/5 ve Kurul Kararı 2019/10
==========================================================

A. VERİ SORUMLUSU BİLGİLERİ
- Veri Sorumlusu Tam Ticari Unvanı: [ŞİRKET]
- Mersis No: [MERSİS]
- VERBİS Kayıt No (varsa): [VERBİS]
- Adres: [ADRES]
- KEP Adresi: [KEP]
- Telefon: [TEL]
- Web sitesi: [WEB]

B. İRTİBAT KİŞİSİ / VERİ SORUMLUSU TEMSİLCİSİ
- Ad-Soyad: [AD-SOYAD]
- Görevi: [GÖREV - örn. KVKK Sorumlusu]
- Telefon: [TEL]
- E-posta: [E-POSTA]

C. İHLALİN KAPSAMI
1. İhlalin gerçekleştiği tarih (veya tahmini tarih aralığı):
   [TARİH VEYA ARALIK]

2. İhlalin tespit edildiği tarih:
   [TARİH VE SAAT]

3. İhlalin tespit edilme yöntemi:
   [Örn. SOC sistemi tarafından otomatik anomali tespiti; çalışan bildirimi;
   tedarikçi bildirimi; ilgili kişi şikâyeti]

4. Bu form Kurul'a hangi tarihte iletilmektedir:
   [TARİH VE SAAT]

5. 72 saatten geç bildirimde, gecikme nedeni:
   [Boş bırakılırsa süre içindedir; aksi halde detaylı açıklama]

D. İHLALİN NİTELİĞİ
[ ] Gizliliğin ihlali (yetkisiz açıklanma)
[ ] Bütünlüğün ihlali (yetkisiz değiştirilme)
[ ] Erişilebilirliğin ihlali (kayıp, silme, hizmet kesintisi)

Açıklama: [İHLAL SENARYOSU 100-300 KELİME]

E. İHLALDEN ETKİLENEN KİŞİSEL VERİLER
1. Veri kategorileri:
   [Örn. kimlik (ad-soyad, T.C. kimlik no), iletişim (e-posta, telefon),
   müşteri işlem (sipariş, fatura), pazarlama tercihleri]

2. Özel nitelikli veri içeriyor mu:
   [Evet/Hayır] — Evet ise: [Sağlık, biyometrik, vb.]

3. Veri konusu kişi grupları:
   [Örn. müşteriler, çalışanlar, adaylar, tedarikçi temsilcileri]

4. Tahmini etkilenen kişi sayısı:
   [SAYI VEYA ARALIK]; tahmin gerekçesi:

5. Etkilenen kayıt sayısı:
   [SAYI VEYA ARALIK]

6. Etkilenen sistem(ler):
   [Sistem adı, açıklaması]

F. İHLALİN OLASI SONUÇLARI
1. Etkilenen ilgili kişiler için olası riskler:
   [Örn. dolandırıcılık, kimlik hırsızlığı, manevi zarar, ticari kayıp]

2. Etki düzeyi: [Düşük / Orta / Yüksek / Çok Yüksek]

3. Etki gerekçesi:
   [VERİ HACMİ × HASSASİYET × YENİDEN KULLANIM RİSKİ]

G. ALINMIŞ VEYA ALINMASI PLANLANAN ÖNLEMLER
1. Acil önlemler (T0 + 72 saat içinde alınanlar):
   [Örn. etkilenen sistemlerin izolasyonu, parolaların sıfırlanması,
   yetkisiz erişimin durdurulması, log koruma]

2. Orta vadeli önlemler (T0 + 30 gün içinde):
   [Örn. ilgili güvenlik açığının kapatılması, ek MFA, yetki gözden
   geçirme, eğitim modülü güncelleme]

3. Uzun vadeli yapısal önlemler:
   [Örn. süreç değişikliği, mimari iyileştirme, kontrol noktası ekleme]

H. İLGİLİ KİŞİLERE BİLDİRİM
1. İlgili kişilere bildirim yapılacak mı:
   [Evet/Hayır] — Hayır ise gerekçe:

2. Bildirim yöntemi:
   [E-posta / SMS / web sitesi duyurusu / mektup / kombine]

3. Bildirim taslağı:
   [METİN — İlgili kişiye anlaşılır biçimde, ihlal niteliği, etkilenen
   veriler, alınan önlemler, ilgili kişinin kendi alabileceği önlemler,
   iletişim bilgileri]

4. Bildirim tarihi (hedef):
   [TARİH]

I. KÖK NEDEN ANALİZİ
1. Olayın oluşum sebebi:
   [Örn. zafiyet, insan hatası, sosyal mühendislik, tedarikçi hatası]

2. Aynı türden ihlali önlemek için yapısal değişiklikler:
   [Tanımlı]

J. EKLER
[ ] İlgili kişi bildirim metni
[ ] Olay zaman çizelgesi
[ ] Etkilenen veri listesi (anonimize)
[ ] Adli analiz raporu (varsa)
[ ] Önceki ilgili Kurul kararları (kendiliğinden örnek varsa)

K. ONAYLAR
- Hazırlayan: [KVKK Sorumlusu] — [TARİH]
- Hukuk: [Hukuk Müşaviri] — [TARİH]
- Yetkili İmza: [Genel Müdür / KVKK Komitesi Başkanı] — [TARİH]

==========================================================
```

---

## 4. ŞABLON C — İLGİLİ KİŞİYE BİLDİRİM ŞABLONU (E-posta/SMS/Web)

```
Sayın [AD-SOYAD],

[ŞİRKET] olarak, [TARİH] tarihinde fark edilen bir veri güvenliği olayı
nedeniyle 6698 sayılı Kişisel Verilerin Korunması Kanunu kapsamında sizi
bilgilendirmek isteriz.

NE OLDU?
[Olay özeti — 2-3 cümle, anlaşılır dil. Suçlama yok, üzgün ifadesi
profesyonel ölçüde. Örn. "Tedarikçi sistemlerinde gerçekleşen yetkisiz
bir erişim sonucu, sınırlı sayıdaki müşterimizin ad-soyad ve e-posta
adresi yetkisiz üçüncü kişiler tarafından erişilmiş olabilir."]

HANGİ BİLGİLER ETKİLENDİ?
[Net liste — örn. ad-soyad, e-posta. Etkilenmeyenler özellikle belirtilir:
"Şifreleriniz, ödeme bilgileriniz ve kimlik numaralarınız etkilenmemiştir."]

NE YAPTIK?
[Alınan önlemler — örn. yetkisiz erişim derhal kesildi, etkilenen sistem
izole edildi, parolalar zorla sıfırlandı, KVKK Kurumuna bildirim yapıldı,
güvenlik denetimi başlatıldı.]

SİZ NE YAPABİLİRSİNİZ?
[Pratik öneriler — örn. parolanızı değiştirin, şüpheli e-postaları
açmayın, hesap hareketlerinizi kontrol edin, 2FA aktifleştirin.]

İLETİŞİM
Sorularınız için: [E-POSTA] / [TELEFON]
KVKK m.11 hakları için: [BAŞVURU LİNKİ]

KVKK Kurumu da olaydan haberdar edilmiştir; gerekirse Kurum'a
[KVKK BAŞVURU YOLU] üzerinden başvurabilirsiniz.

Saygılarımızla,
[ŞİRKET ADI]
```

---

## 5. İhlal Bildirim Karar Matrisi

| Etki | Kurul'a Bildirim | İlgili Kişiye Bildirim |
|------|-------------------|-------------------------|
| Düşük (sınırlı kayıt, düşük hassasiyet, hızlı kapatma) | Genelde gerekli (m.12/5) | Risk değerlendirmesine bağlı |
| Orta | Gerekli | Önerilir |
| Yüksek | Gerekli | Zorunlu |
| Kritik | Gerekli + olağanüstü hızda | Zorunlu + medya iletişimi |

> Kurul kararı 2019/10 ışığında, **kişi haklarına yönelik risk varsa** ilgili kişiye bildirim yapılır. Risk yoksa ve verilerin etkisi sınırlıysa Kurul'a bildirim ile yetinilebilir; bu değerlendirme yazılı yapılır.

## 6. İlgili Dokümanlar

- [../12-mevzuat-arsiv/kurul-kararlari-ozeti.md](../12-mevzuat-arsiv/kurul-kararlari-ozeti.md)
- [../08-ihlal-yonetimi/](../08-ihlal-yonetimi/)
- [../11-denetim-ve-uyum/kpi-ve-metrikler.md](../11-denetim-ve-uyum/kpi-ve-metrikler.md)
