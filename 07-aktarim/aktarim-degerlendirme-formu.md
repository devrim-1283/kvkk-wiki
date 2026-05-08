---
Doküman: Aktarım Etki Değerlendirmesi (TIA) ve Aktarım Onay Formu
Bölüm: 07-aktarim
Sahip: KVKK Sorumlusu
Onaylayan: Hukuk Müdürü + Bilgi Güvenliği Yöneticisi (KVKK Komitesi onayı)
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (yeni aktarım, mevzuat değişikliği, alıcı ülke hukuk değişikliği)
İlgili Mevzuat: KVKK m.5, m.6, m.8, m.9; Kurul'un 04.06.2024 tarihli ve 2024/959 sayılı kararı
---

# Aktarım Etki Değerlendirmesi (TIA) ve Onay Formu

## 1. Formun Amacı

Bu form; Şirket'in gerçekleştireceği her **kişisel veri aktarımı** (yurt içi ve yurt dışı) için **aktarım öncesinde** doldurulmak üzere tasarlanmıştır. Form aşağıdakileri sağlar:

- Aktarımın hukuki dayanağının (m.5/m.6 + m.8/m.9) net biçimde tespit edilmesi,
- Yurt dışı aktarımlarda hangi yolun (yeterlilik / uygun güvence / arızi) kullanıldığının kayıt altına alınması,
- Alıcı ülke hukuku ve uygulamasının değerlendirilmesi (yurt dışı için),
- Ek tedbirlerin tanımlanması ve uygulanmaya konulması,
- KVKK Komitesi onay zincirinin tutulması.

## 2. Form Türleri

| Form | Kullanım |
|------|----------|
| Form A | Yurt İçi Aktarım Onay Formu |
| Form B | Yurt Dışı Aktarım — Yeterlilik Kararı Yolu |
| Form C | Yurt Dışı Aktarım — Uygun Güvence Yolu (Standart Sözleşme / BCR / Taahhütname / Anlaşma) |
| Form D | Yurt Dışı Aktarım — Arızi Hâl Yolu |

Aşağıda **birleşik form** sunulmuştur; ilgili bölümler aktarım türüne göre doldurulur.

---

## 3. Aktarım Onay Formu — Birleşik

```
═══════════════════════════════════════════════════════════════
KİŞİSEL VERİ AKTARIM DEĞERLENDİRME VE ONAY FORMU
═══════════════════════════════════════════════════════════════

Form No                : ____________________________________
Form Tarihi            : ____/____/______
Form Sahibi (Birim)    : ____________________________________
Aktarım Türü           : [ ] Yurt içi  [ ] Yurt dışı

──────────────────────────────────────────────────────────────
1. AKTARIMIN GENEL TANIMI
──────────────────────────────────────────────────────────────
Aktarımın Amacı        : ______________________________________
                         ______________________________________
İş Süreci Sahibi       : ______________________________________
Veri Sorumlusu         : [ŞİRKET ADI A.Ş.]
Alıcı (Unvan)          : ______________________________________
Alıcı Adres            : ______________________________________
Alıcı Ülke             : ______________________________________
Alıcı Statüsü          : [ ] Veri Sorumlusu (VS)
                         [ ] Veri İşleyen (Vİ)
                         [ ] Joint Controller
Aktarım Sıklığı        : [ ] Tek seferlik
                         [ ] Periyodik (gün/hafta/ay/yıl)
                         [ ] Sürekli (real-time / API)
Aktarımın Süresi       : __________________________
Aktarımın Yöntemi      : [ ] API
                         [ ] Dosya transferi (SFTP/FTPS)
                         [ ] E-posta / KEP
                         [ ] Bulut barındırma (sağlayıcı: ____)
                         [ ] Uzaktan erişim (yetki ile)
                         [ ] Fiziksel medya
                         [ ] Diğer: ____________________

──────────────────────────────────────────────────────────────
2. VERİ KAPSAMI
──────────────────────────────────────────────────────────────
Veri Kategorileri      : ______________________________________
                         ______________________________________
                         (Envanter Madde No: ____________)
İlgili Kişi Grupları   : [ ] Çalışan [ ] Aday [ ] Müşteri
                         [ ] Tedarikçi yetkilisi
                         [ ] Ziyaretçi
                         [ ] Diğer: ____________________
Veri Hassasiyeti       : [ ] Genel
                         [ ] Özel nitelikli (m.6)
                         [ ] Çocuk verisi
Yaklaşık Kayıt Sayısı  : ____________________________________
Veri Hacmi             : ____________________________________

──────────────────────────────────────────────────────────────
3. HUKUKI SEBEP — m.5/m.6 İŞLEME ŞARTI
──────────────────────────────────────────────────────────────
İşleme Şartı           : KVKK m.____/____  ____________________
                         (Şart adı: açık rıza/sözleşme ifası/
                          hukuki yükümlülük/meşru menfaat/...)
Şartın Sürdürülebilir-
liği                   : Aktarım süresince geçerli mi? Evet/Hayır
Aydınlatma             : [ ] Yapıldı (sürüm: __________)
                         [ ] Güncellenecek
                         [ ] Uygulanmaz (gerekçe: __________)

──────────────────────────────────────────────────────────────
4. YURT İÇİ AKTARIM (Form A — sadece yurt içi ise)
──────────────────────────────────────────────────────────────
m.8 Aktarım Şartı      : KVKK m.____/____
Sözleşme Türü          : [ ] Veri İşleyen Sözleşmesi (DPA)
                         [ ] Aktarım Sözleşmesi (VS-VS)
                         [ ] Joint Controller Anlaşması
                         [ ] Mevzuat gereği — sözleşme yok
Sözleşme No / Tarih    : ____________________________________
DPA Asgari Unsurları   : [ ] Tam (kontrol listesi: yurtici-aktarim.md §7)
Alt-İşleyen Var mı     : [ ] Yok [ ] Var (liste eki: __________)

──────────────────────────────────────────────────────────────
5. YURT DIŞI AKTARIM YOLU (sadece yurt dışı ise)
──────────────────────────────────────────────────────────────
[ ] (Aşama 1) Yeterlilik Kararı (m.9/1)
    Liste tarihi/sürüm  : ____________________________________
    Liste linki/atfı    : ____________________________________
    Kararın hangi kapsamda olduğu (ülke/sektör/uluslararası
    kuruluş): ___________________________________________

[ ] (Aşama 2) Uygun Güvence (m.9/4)
    [ ] (a) Anlaşma + Kurul izni
        İzin tarihi/sayı: ___________________________________
    [ ] (b) Bağlayıcı Şirket Kuralları
        Onay tarihi/sayı: ___________________________________
    [ ] (c) Standart Sözleşme
        Tür             : Tip __ (VS-VS / VS-Vİ / Vİ-Vİ / Vİ-VS)
        İmza tarihi     : ____/____/______
        Kurum'a bildirim
        tarihi (5 iş g.): ____/____/______
    [ ] (ç) Yazılı taahhütname + Kurul izni
        İzin tarihi/sayı: ___________________________________

[ ] (Aşama 3) Arızi Hâl (m.9/6)
    Uygulanan bent      : (a)/(b)/(c)/(ç)/(d)/(e)/(f)
    Arızi niteliğin
    gerekçesi           : _________________________________
                          _________________________________
    Bilgilendirme yapıldı (a için): [ ] Evet [ ] Uygulanmaz

──────────────────────────────────────────────────────────────
6. ALICI ÜLKE DEĞERLENDİRMESİ (yurt dışı için)
──────────────────────────────────────────────────────────────
Alıcı Ülke             : ____________________________________

Veri Koruma Mevzuatı   : [ ] Var ve kapsamlı
                         [ ] Var ama sınırlı
                         [ ] Yok / Asgari
Bağımsız Otorite       : [ ] Var [ ] Yok
İlgili Kişi Hakları    : [ ] Etkin [ ] Sınırlı [ ] Yok
Yargısal Koruma        : [ ] Var [ ] Sınırlı [ ] Yok
Uluslararası Anlaşma   : [ ] AB GDPR uyumu var
                         [ ] Council of Europe Convention 108
                         [ ] APEC CBPR
                         [ ] Diğer: ____________________

KAMU OTORİTESİ ERİŞİM RİSKİ
İstihbarat Erişimi     : [ ] Düşük [ ] Orta [ ] Yüksek
Kolluk Erişimi         : [ ] Düşük [ ] Orta [ ] Yüksek
Disproportionate Risk  : [ ] Düşük [ ] Orta [ ] Yüksek
Açıklama               : _________________________________

──────────────────────────────────────────────────────────────
7. EK TEDBİRLER
──────────────────────────────────────────────────────────────
TEKNIK
[ ] End-to-end şifreleme
[ ] At-rest şifreleme (AES-256)
[ ] Transit şifreleme (TLS 1.2+)
[ ] Anahtar yönetimi (KMS/HSM, BYOK)
[ ] Pseudonymization
[ ] Veri minimizasyonu (sadece gerekli alanlar)
[ ] IP filtreleme / VPN
[ ] DLP
[ ] Diğer: ____________________________________________

SÖZLEŞMESEL
[ ] Standart sözleşme (Aşama 2-c)
[ ] Ek protokol (sözleşmeden sapma yok)
[ ] Notification of access requests (yerel hukuk izin verdiği ölçüde)
[ ] Audit hakkı
[ ] 24 saat ihlal bildirim hükmü
[ ] Alt-işleyen onay zorunluluğu
[ ] Diğer: ____________________________________________

ORGANİZASYONEL
[ ] Need-to-know erişim
[ ] Eğitim (alıcı tarafta)
[ ] Logging + denetim
[ ] Sözleşme sona erince imha taahhüdü
[ ] Diğer: ____________________________________________

──────────────────────────────────────────────────────────────
8. ALT-İŞLEYEN ZİNCİRİ
──────────────────────────────────────────────────────────────
Alıcı, alt-işleyen
kullanıyor mu?         : [ ] Yok [ ] Var
Alt-işleyen Listesi    : Eki (varsa)
Alt-işleyen Onay Yapısı: [ ] Yok [ ] Genel onay
                         [ ] Spesifik onay (önceden bildirim)
Alt-işleyenler
yurt dışında mı?       : [ ] Hayır [ ] Evet (ülke listesi: __)

──────────────────────────────────────────────────────────────
9. KALAN RİSK VE KARAR
──────────────────────────────────────────────────────────────
Risk Değerlendirmesi   :
  Etkilenen kişi sayısı: __________________________
  Veri hassasiyeti     : Düşük / Orta / Yüksek
  Aktarım sıklığı      : Düşük / Orta / Yüksek
  Alıcı ülke riski     : Düşük / Orta / Yüksek
  Ek tedbir etkinliği  : Düşük / Orta / Yüksek

Kalan Risk Seviyesi    : [ ] Düşük [ ] Orta [ ] Yüksek

KARAR                  : [ ] Aktarım onaylanır
                         [ ] Aktarım onaylanmaz
                         [ ] Ek tedbir gerekiyor — yeniden değerle.

──────────────────────────────────────────────────────────────
10. VERBİS GÜNCELLEMESİ
──────────────────────────────────────────────────────────────
[ ] VERBİS güncellendi
    Güncelleme tarihi  : ____/____/______
    Alıcı grubu        : ____________________________________

──────────────────────────────────────────────────────────────
11. ONAYLAR
──────────────────────────────────────────────────────────────
Hazırlayan (İş Birimi Sorumlusu)
  Ad Soyad             : ____________________________________
  Unvan / Birim        : ____________________________________
  Tarih                : ____/____/______
  İmza                 : ____________________________________

Bilgi Güvenliği Onayı
  Ad Soyad             : ____________________________________
  Tarih                : ____/____/______
  İmza                 : ____________________________________

Hukuki Onay
  Ad Soyad             : Av. ______________________________
  Tarih                : ____/____/______
  İmza                 : ____________________________________

KVKK Sorumlusu Onayı
  Ad Soyad             : ____________________________________
  Tarih                : ____/____/______
  İmza                 : ____________________________________

KVKK Komitesi Onayı (Yüksek riskli aktarım için zorunlu)
  Tarih                : ____/____/______
  Karar No             : ____________________________________

──────────────────────────────────────────────────────────────
12. EK BELGELER
──────────────────────────────────────────────────────────────
[ ] Sözleşme PDF
[ ] DPA PDF (yurt içi VS-Vİ)
[ ] Standart sözleşme + ekler (yurt dışı)
[ ] Alt-işleyen listesi
[ ] Aydınlatma metni (sürümlü)
[ ] Açık rıza ispat dökümü (varsa)
[ ] Kurum bildirim onayı (varsa)
[ ] Önceki TIA (yenileme ise)
═══════════════════════════════════════════════════════════════
```

---

## 4. Örnek 1 — AB SaaS Sağlayıcısı (Pazarlama Otomasyonu)

```
═══════════════════════════════════════════════════════════════
KİŞİSEL VERİ AKTARIM DEĞERLENDİRME VE ONAY FORMU
═══════════════════════════════════════════════════════════════

Form No                : TIA-2026-0042
Form Tarihi            : 12/04/2026
Form Sahibi (Birim)    : Dijital Pazarlama Müdürlüğü
Aktarım Türü           : [X] Yurt dışı

──────────────────────────────────────────────────────────────
1. AKTARIMIN GENEL TANIMI
──────────────────────────────────────────────────────────────
Aktarımın Amacı        : E-ticaret müşterilerine pazarlama
                         otomasyonu (e-posta, push, SMS)
                         ve segmentasyon analitiği.
İş Süreci Sahibi       : Pazarlama Müdürü
Veri Sorumlusu         : [ŞİRKET ADI A.Ş.]
Alıcı (Unvan)          : Acme Marketing Cloud Ltd.
Alıcı Adres            : Dublin, İrlanda
Alıcı Ülke             : İrlanda (AB Üyesi)
Alıcı Statüsü          : [X] Veri İşleyen (Vİ)
Aktarım Sıklığı        : [X] Sürekli (real-time API)
Aktarımın Süresi       : Sözleşme süresi (3 yıl + yenileme)
Aktarımın Yöntemi      : [X] API + bulut barındırma
                         Sağlayıcı: Acme bulut, AB region

──────────────────────────────────────────────────────────────
2. VERİ KAPSAMI
──────────────────────────────────────────────────────────────
Veri Kategorileri      : Ad-soyad, e-posta, telefon, sipariş
                         geçmişi, davranış verisi, segment
                         (Envanter Madde No: ECOM-08, MKT-03)
İlgili Kişi Grupları   : [X] Müşteri
Veri Hassasiyeti       : [X] Genel
Yaklaşık Kayıt Sayısı  : 1.2 milyon aktif müşteri
Veri Hacmi             : ~50 GB / ay artış

──────────────────────────────────────────────────────────────
3. HUKUKI SEBEP — m.5/m.6 İŞLEME ŞARTI
──────────────────────────────────────────────────────────────
İşleme Şartı           : KVKK m.5/1 — Açık Rıza
                         (Pazarlama amacı için)
Şartın Sürdürülebilir-
liği                   : Rıza geri çekilebilir; geri çekilirse
                         sağlayıcıdan da silinmesi sağlanır
Aydınlatma             : [X] Yapıldı (Sürüm: 2026-Q1 v3.2)

──────────────────────────────────────────────────────────────
5. YURT DIŞI AKTARIM YOLU
──────────────────────────────────────────────────────────────
[X] (Aşama 2) Uygun Güvence (m.9/4)
    [X] (c) Standart Sözleşme
        Tür             : Tip 2 (VS → Vİ)
        İmza tarihi     : 10/04/2026
        Kurum'a bildirim
        tarihi          : 14/04/2026 (3 iş günü)

──────────────────────────────────────────────────────────────
6. ALICI ÜLKE DEĞERLENDİRMESİ
──────────────────────────────────────────────────────────────
Alıcı Ülke             : İrlanda

Veri Koruma Mevzuatı   : [X] Var ve kapsamlı (GDPR + Data
                         Protection Act 2018)
Bağımsız Otorite       : [X] Var (DPC — Data Protection
                         Commission)
İlgili Kişi Hakları    : [X] Etkin
Yargısal Koruma        : [X] Var (CJEU dahil)
Uluslararası Anlaşma   : [X] AB GDPR
                         [X] Convention 108

KAMU OTORİTESİ ERİŞİM RİSKİ
İstihbarat Erişimi     : [X] Düşük
Kolluk Erişimi         : [X] Düşük (yargısal denetim güçlü)
Disproportionate Risk  : [X] Düşük
Açıklama               : Sağlayıcının ABD ana şirketi var.
                         Veri AB region'da; ABD ana şirketin
                         erişimi sözleşmede sınırlandırıldı.

──────────────────────────────────────────────────────────────
7. EK TEDBİRLER
──────────────────────────────────────────────────────────────
TEKNIK
[X] At-rest şifreleme (AES-256)
[X] Transit şifreleme (TLS 1.3)
[X] BYOK — anahtar Şirket'te
[X] Veri minimizasyonu (sadece gerekli alanlar)
[X] Pseudonymization (kullanıcı ID hash'lenmiş)

SÖZLEŞMESEL
[X] Standart sözleşme (Tip 2)
[X] Ek protokol — ABD ana şirket erişim sınırı
[X] Notification of access requests
[X] Audit hakkı (yıllık)
[X] 24 saat ihlal bildirim hükmü

ORGANİZASYONEL
[X] Need-to-know
[X] Sözleşme sona erince 30 günde tüm verinin imhası

──────────────────────────────────────────────────────────────
8. ALT-İŞLEYEN ZİNCİRİ
──────────────────────────────────────────────────────────────
Alt-işleyen Listesi    : 4 adet (3 AB + 1 ABD CDN)
Alt-işleyen Onay       : Spesifik onay (önceden bildirim)
                         + 14 gün itiraz hakkı
ABD CDN Risk Notu      : Sadece statik içerik; PII içermez

──────────────────────────────────────────────────────────────
9. KALAN RİSK VE KARAR
──────────────────────────────────────────────────────────────
Risk Değerlendirmesi:
  Etkilenen kişi sayısı: 1.2 milyon
  Veri hassasiyeti     : Orta
  Aktarım sıklığı      : Yüksek (sürekli)
  Alıcı ülke riski     : Düşük
  Ek tedbir etkinliği  : Yüksek

Kalan Risk Seviyesi    : [X] Düşük

KARAR                  : [X] Aktarım onaylanır

──────────────────────────────────────────────────────────────
10. VERBİS GÜNCELLEMESİ
──────────────────────────────────────────────────────────────
[X] VERBİS güncellendi 15/04/2026
    Alıcı grubu        : Yurt dışı pazarlama hizmet sağlayıcısı

──────────────────────────────────────────────────────────────
11. ONAYLAR
──────────────────────────────────────────────────────────────
Hazırlayan             : Elif YAVUZ — Pazarlama Müdürü
Bilgi Güvenliği Onayı  : Mehmet KAYA — Bilgi Güv. Yön.
Hukuki Onay            : Av. Ahmet ÖZ — Hukuk Müdürü
KVKK Sorumlusu Onayı   : Selin YILDIZ — KVKK Sorumlusu
KVKK Komitesi          : 14/04/2026, Karar No: 2026/12
═══════════════════════════════════════════════════════════════
```

---

## 5. Örnek 2 — ABD CRM Sağlayıcısı (Yüksek Risk + Ek Tedbirler)

```
═══════════════════════════════════════════════════════════════
KİŞİSEL VERİ AKTARIM DEĞERLENDİRME VE ONAY FORMU
═══════════════════════════════════════════════════════════════

Form No                : TIA-2026-0058
Form Tarihi            : 22/04/2026
Form Sahibi (Birim)    : Satış Operasyon Müdürlüğü
Aktarım Türü           : [X] Yurt dışı

──────────────────────────────────────────────────────────────
1. AKTARIMIN GENEL TANIMI
──────────────────────────────────────────────────────────────
Aktarımın Amacı        : B2B müşteri ilişki yönetimi (CRM)
                         — satış pipeline, fırsat yönetimi,
                         müşteri yetkilisi iletişim kayıtları
İş Süreci Sahibi       : Satış Operasyon Direktörü
Alıcı (Unvan)          : Globex Cloud CRM Inc.
Alıcı Adres            : San Francisco, CA, ABD
Alıcı Ülke             : ABD
Alıcı Statüsü          : [X] Veri İşleyen (Vİ)
Aktarım Sıklığı        : [X] Sürekli
Aktarımın Süresi       : 5 yıl (yenilenebilir)
Aktarımın Yöntemi      : [X] API + bulut barındırma
                         Sağlayıcı bölgesi: us-east-1

──────────────────────────────────────────────────────────────
2. VERİ KAPSAMI
──────────────────────────────────────────────────────────────
Veri Kategorileri      : Müşteri yetkilisi ad-soyad, unvan,
                         iş e-posta, iş telefonu, satış
                         görüşme notları
                         (Envanter Madde No: SLS-01)
İlgili Kişi Grupları   : [X] Müşteri (B2B yetkilisi —
                         gerçek kişi sıfatıyla)
Veri Hassasiyeti       : [X] Genel
Yaklaşık Kayıt Sayısı  : 38.000 kişi (B2B yetkilisi)
Veri Hacmi             : ~5 GB / yıl

──────────────────────────────────────────────────────────────
3. HUKUKI SEBEP — m.5/m.6 İŞLEME ŞARTI
──────────────────────────────────────────────────────────────
İşleme Şartı           : KVKK m.5/2-(f) — Meşru Menfaat
                         (B2B satış sürecinin yürütülmesi)
                         + KVKK m.5/2-(c) — Sözleşme ifası
                         (mevcut sözleşmeli müşteriler için)
Aydınlatma             : [X] Müşteri yetkilisi aydınlatma
                         metni güncellendi (Sürüm: 2026-Q2)

──────────────────────────────────────────────────────────────
5. YURT DIŞI AKTARIM YOLU
──────────────────────────────────────────────────────────────
[X] (Aşama 2) Uygun Güvence (m.9/4)
    [X] (c) Standart Sözleşme
        Tür             : Tip 2 (VS → Vİ)
        İmza tarihi     : 20/04/2026
        Kurum'a bildirim
        tarihi          : 23/04/2026 (3 iş günü)

──────────────────────────────────────────────────────────────
6. ALICI ÜLKE DEĞERLENDİRMESİ
──────────────────────────────────────────────────────────────
Alıcı Ülke             : ABD

Veri Koruma Mevzuatı   : [X] Var ama sınırlı
                         (federal düzeyde sektörel; eyalet
                         düzeyinde CCPA/CPRA, Virginia VCDPA;
                         genel federal yasası yok)
Bağımsız Otorite       : [X] Sınırlı (FTC sektörel)
İlgili Kişi Hakları    : [X] Sınırlı
Yargısal Koruma        : [X] Sınırlı (yabancılar için)
Uluslararası Anlaşma   : [ ] AB GDPR — N/A
                         [ ] Convention 108 — N/A
                         (AB-ABD Data Privacy Framework AB
                          için geçerli, KVKK kapsamında değil)

KAMU OTORİTESİ ERİŞİM RİSKİ
İstihbarat Erişimi     : [X] Yüksek (FISA 702, EO 12333)
Kolluk Erişimi         : [X] Orta (CLOUD Act etkisi)
Disproportionate Risk  : [X] Yüksek
Açıklama               : ABD istihbarat servislerinin yurt
                         dışı verilere geniş erişim yetkisi
                         var. Sözleşmesel hükümler yetersiz
                         kalabilir; ek teknik tedbirler kritik.

──────────────────────────────────────────────────────────────
7. EK TEDBİRLER
──────────────────────────────────────────────────────────────
TEKNIK
[X] At-rest şifreleme (AES-256)
[X] Transit şifreleme (TLS 1.3)
[X] BYOK — anahtar Türkiye'de Şirket KMS'inde
    (sağlayıcının kendi anahtarına erişimi yok)
[X] Field-level encryption — hassas alanlar (notlar)
[X] Veri minimizasyonu — sadece B2B iş verisi (özel
    yaşam, sosyal medya, foto göndermez)

SÖZLEŞMESEL
[X] Standart sözleşme (Tip 2)
[X] Ek protokol:
    - ABD kamu otoritesi erişim talebinde Şirket'e
      derhal bildirim (yerel hukuk izin verdiği ölçüde)
    - Erişim talebine sözleşmesel itiraz yükümlülüğü
    - Audit hakkı (yıllık 3rd party audit)
    - 24 saat ihlal bildirim
[X] Notification of access requests

ORGANİZASYONEL
[X] Need-to-know
[X] Erişim logları + Şirket SIEM entegrasyonu
[X] Sözleşme sona erince 30 günde imha

──────────────────────────────────────────────────────────────
8. ALT-İŞLEYEN ZİNCİRİ
──────────────────────────────────────────────────────────────
Alt-işleyen Listesi    : 6 adet (5 ABD + 1 İrlanda)
Alt-işleyen Onay       : Genel onay; her değişiklikte
                         30 gün önceden bildirim + itiraz hakkı
Yüksek Risk Notu       : Hint Hindistan destek ekibi vardı;
                         sözleşmede destek için hint
                         erişiminin yasaklanması talep edildi.

──────────────────────────────────────────────────────────────
9. KALAN RİSK VE KARAR
──────────────────────────────────────────────────────────────
Risk Değerlendirmesi:
  Etkilenen kişi sayısı: 38.000
  Veri hassasiyeti     : Orta-Yüksek (B2B notlar
                         hassas iş bilgisi içerebilir)
  Aktarım sıklığı      : Yüksek (sürekli)
  Alıcı ülke riski     : Yüksek
  Ek tedbir etkinliği  : Yüksek (BYOK + field encryption +
                         data minimization)

Kalan Risk Seviyesi    : [X] Orta

KARAR                  : [X] Aktarım onaylanır
                         Şart: yıllık TIA yenilemesi +
                         3rd party audit raporunun KVKK
                         Komitesi'ne sunulması.

──────────────────────────────────────────────────────────────
10. VERBİS GÜNCELLEMESİ
──────────────────────────────────────────────────────────────
[X] VERBİS güncellendi 24/04/2026
    Alıcı grubu        : Yurt dışı CRM hizmet sağlayıcısı

──────────────────────────────────────────────────────────────
11. ONAYLAR
──────────────────────────────────────────────────────────────
Hazırlayan             : Murat ARSLAN — Satış Op. Direktörü
Bilgi Güvenliği Onayı  : Mehmet KAYA — Bilgi Güv. Yön.
Hukuki Onay            : Av. Ahmet ÖZ — Hukuk Müdürü
KVKK Sorumlusu Onayı   : Selin YILDIZ — KVKK Sorumlusu
KVKK Komitesi          : 23/04/2026, Karar No: 2026/15
                         (yüksek riskli aktarım — komite onayı şart)

──────────────────────────────────────────────────────────────
12. EK BELGELER
──────────────────────────────────────────────────────────────
[X] Standart Sözleşme Tip 2 + ek protokol PDF
[X] Alt-işleyen listesi v1.4
[X] Aydınlatma metni 2026-Q2
[X] Globex SOC 2 Type II raporu
[X] Globex DPA + Subprocessor list
[X] BYOK mimari diyagramı
═══════════════════════════════════════════════════════════════
```

---

## 6. Form Yönetim Disiplini

| Konu | Kural |
|------|-------|
| Form No | TIA-[YIL]-[SIRA] formatı |
| Hazırlama tetikleyicisi | Yeni aktarım, sözleşme yenileme, mevzuat değişikliği, alıcı değişimi |
| Onay zinciri | Hazırlayan → Bilgi Güv. → Hukuk → KVKK Sorumlusu → (yüksek risk) KVKK Komitesi |
| Saklama süresi | 10 yıl |
| Yenileme | Yıllık veya tetiklenmiş |
| Saklama yeri | KVKK Sorumlusu kontrolünde elektronik imzalı PDF |
| Aramalı indeks | Form no, tarih, alıcı, ülke, durum |
| Versiyon | Yenileme önceki sürümü iptal eder, yeni sürüm yürürlüğe girer |

## 7. Yüksek Risk Tetikleyicileri

Aşağıdaki durumlarda KVKK Komitesi onayı şarttır (KVKK Sorumlusu tek imza yeterli değil):

- Özel nitelikli kişisel veri aktarımı,
- Çocuk verisi aktarımı,
- 100.000+ ilgili kişiyi etkileyen aktarım,
- Yüksek riskli ülkeye aktarım (kamu otoritesi disproportionate erişim),
- Yeni ve denenmemiş bir sağlayıcıya aktarım,
- Açık rıza yerine meşru menfaate dayanan büyük ölçekli pazarlama aktarımı,
- BCR onay süreci.
