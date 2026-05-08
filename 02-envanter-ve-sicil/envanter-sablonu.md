---
Doküman: Kişisel Veri İşleme Envanteri — Doldurulabilir Şablon
Bölüm: 02-envanter-ve-sicil
Sahip: KVKK Sorumlusu
Onaylayan: Hukuk Müdürü + KVKK Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş
İlgili Mevzuat: 6698 sayılı KVKK m.4-6, m.10, m.12, m.16; Veri Sorumluları Sicili Hakkında Yönetmelik MADDE 4(h), 5, 9; Saklama ve İmha Yön. MADDE 5
---

# Kişisel Veri İşleme Envanteri — Şablon

Bu dosya, **kullanıma hazır** envanter şablonunu içerir. Üç örnek satırla doldurulmuştur (İK işe alım, müşteri sipariş, CCTV). Yeni satırlar için aynı format kullanılır.

## 1. Şablon Tablosu

> Tablo geniştir; markdown'da yatay kaydırma gerektirebilir. CSV başlık satırı bölüm 3'te verilmiştir; tercih halinde Excel'e aktarılarak çalışılabilir.

| Süreç ID | Süreç Adı | İş Birimi | Süreç Sahibi | Veri Konusu Kişi Grubu | Veri Kategorisi | Kişisel Veri Öğeleri | Özel Nitelikli (E/H) | İşleme Amacı | Hukuki Sebep | Toplama Yöntemi | Kayıt Ortamı | Aktarım Yapılan İç Birim | Yurt İçi Alıcı / Alıcı Grubu | Yurt Dışı Aktarım (E/H) | Yurt Dışı Alıcı + Ülke | Yurt Dışı Hukuki Temel | Saklama Süresi | Saklama Gerekçesi | İmha Yöntemi | İmha Periyodu | Teknik Tedbirler | İdari Tedbirler | Risk Seviyesi | İlgili Aydınlatma Metni | Açık Rıza Gerekli mi? | Son Güncelleme |
|----------|-----------|-----------|--------------|-----------------------|-----------------|---------------------|----------------------|--------------|--------------|-----------------|--------------|--------------------------|------------------------------|------------------------|------------------------|------------------------|----------------|-------------------|--------------|---------------|------------------|-----------------|---------------|-------------------------|----------------------|----------------|
| IK-001 | Çalışan Adayı İşe Alım ve Özgeçmiş Yönetimi | İnsan Kaynakları | Ad Soyad / İK Direktörü / ik.direktor@firma.com.tr | Çalışan Adayı | Kimlik; İletişim; Mesleki Deneyim; Eğitim; Görsel/İşitsel | Ad-soyad, T.C. kimlik no, doğum tarihi, telefon, e-posta, adres, eğitim bilgileri, iş tecrübesi, referans bilgileri, fotoğraf, mülakat notları | H | Açık pozisyon için aday değerlendirme; mülakat süreci; iş teklifi; aday havuzu yönetimi | Sözleşmenin kurulması için gereklilik (m.5/2/c) — başvuru aşaması; aday havuzunda saklama için Açık Rıza | Otomatik (kariyer sitesi formu, e-posta, kariyer portalı API'leri); Otomatik olmayan (kağıt başvuru, etkinlik) | Elektronik (ATS/HRIS, e-posta sunucusu, OneDrive); Fiziksel (özlük arşivi) | İK; ilgili pozisyonun bağlı olduğu departman yöneticisi | Aday değerlendirme firmaları (ATS sağlayıcısı), avukatlık ortağı (uyuşmazlık halinde) | E | LinkedIn Talent (ABD); Greenhouse (ABD/AB) | Standart sözleşme + KVKK Kurul'a bildirim; gerekiyorsa açık rıza | İşe alınmayan adaylar için 1 yıl (aday havuzu açık rıza varsa 2 yıl); işe alınanlar IK-002'ye devredilir | İşçi ve İşveren İlişkilerine Dair Kanun zamanaşımı + iş başvurusu nedeniyle hak iddiası analizi | Silme (elektronik) + Yok etme (fiziksel) | 6 aylık periyodik imha takvimi | TLS, AES-256 şifreleme, MFA, rol bazlı erişim, audit log, ATS güvenlik sertifikaları | Gizlilik taahhütnamesi, KVKK eğitimi, erişim yetkilendirme matrisi | Orta | AYD-IK-01 (İşe Alım Aydınlatma Metni) | E (aday havuzunda saklama için) | 2026-05-08 / KVKK Sorumlusu |
| MUS-002 | E-ticaret Sipariş Yönetimi ve Teslimat | Operasyon / Müşteri Hizmetleri | Ad Soyad / Operasyon Müdürü / op.mudur@firma.com.tr | Müşteri (Gerçek Kişi); Teslimat Adresi Sahibi (3. Kişi olabilir) | Kimlik; İletişim; Müşteri İşlem; Lokasyon; Finans | Ad-soyad, T.C. kimlik no (e-fatura için), telefon, e-posta, teslimat adresi, sipariş geçmişi, ödeme bilgisi (kart bilgisi tokenize), IP adresi, cihaz bilgisi | H | Sipariş alımı; ödeme tahsilatı; teslimat; iade; e-fatura kesimi; müşteri hizmetleri | Sözleşmenin ifası (m.5/2/c); hukuki yükümlülük — VUK, e-fatura mevzuatı (m.5/2/ç); ihtilaflarda hak korunması (m.5/2/e) | Otomatik (web sitesi, mobil app, çağrı merkezi); Otomatik olmayan (mağaza içi sipariş formu) | Elektronik (e-ticaret platformu, ödeme PSP'si, e-fatura sağlayıcı, CRM); Fiziksel (sevk irsaliyesi, fatura) | Operasyon, Muhasebe, Müşteri Hizmetleri, Bilgi İşlem | Ödeme PSP'si, kargo şirketi, e-fatura entegratörü, vergi dairesi (mevzuat gereği), avukatlık ortağı | E | AWS (İrlanda — bulut altyapı); Sendgrid (ABD — işlem e-postası) | Standart sözleşme; AWS Veri İşleme Sözleşmesi; Sendgrid SCC | Mali kayıtlar 10 yıl (TTK m.82, VUK m.253); müşteri hesabı için ilişki bitiminden itibaren 10 yıl (TBK m.146 zamanaşımı) | TTK, VUK, TBK | Silme (elektronik); Yok etme (kağıt fatura nüshaları için arşiv süresi sonu) | 6 aylık periyodik imha | TLS, kart tokenizasyonu (PCI-DSS), WAF, IDS/IPS, log toplama (SIEM), DDOS koruma, yedekleme şifreli | KVKK eğitimi, gizlilik taahhütnamesi, tedarikçi sözleşmeleri, periyodik denetim | Yüksek | AYD-MUS-01 (Müşteri E-ticaret Aydınlatma Metni) | H (sözleşme ifasına dayanıyor); pazarlama için ayrıca Açık Rıza | 2026-05-08 / KVKK Sorumlusu |
| FIZ-001 | Kapalı Devre Kamera Sistemi (CCTV) | Güvenlik | Ad Soyad / Güvenlik Müdürü / guvenlik.mudur@firma.com.tr | Çalışan; Ziyaretçi; Tedarikçi Çalışanı; 3. Kişi (kamera görüş alanına giren) | Görsel/İşitsel; Lokasyon | Görüntü kaydı (yüz, kıyafet, eylem); zaman damgası; kamera lokasyonu | H | Bina ve çevre güvenliği; suç önleme; iş sağlığı ve güvenliği; varlık koruma | Meşru menfaat (m.5/2/f) — sınırlı kapsam ve süre; iş sağlığı ve güvenliği için hukuki yükümlülük (m.5/2/ç) | Otomatik (CCTV kameralar, NVR/DVR) | Elektronik (kayıt sunucusu — şirket DC) | Güvenlik birimi; suç durumunda Hukuk + üst yönetim | Yetkili kolluk kuvvetleri (talep + adli süreç); sigorta firması (kaza halinde) | H | — | — | 30 gün (rotasyonel); kritik olay halinde olay kayıtları olay kapanana kadar | Meşru menfaat dengelemesi (PIA): kısa süre + sınırlı erişim | Otomatik üzerine yazma; manuel olay kaydı silme veya yok etme | 30 gün rotasyon | Erişim logu, MFA, ağ segmentasyonu, kayıt cihazı fiziksel kilit, şifreli kayıt | Erişim yetkilendirme (sadece Güvenlik birimi), KVKK eğitimi, kayıt taleplerinin yazılı süreci | Orta | AYD-FIZ-01 (CCTV Aydınlatma Tabelası + Detaylı Metin) | H (meşru menfaate dayanıyor) | 2026-05-08 / Güvenlik Müdürü |

## 2. Boş Satır Şablonu (Yeni Süreç İçin)

Aşağıdaki tabloyu kopyalayıp doldurun:

| Alan | Değer |
|------|-------|
| Süreç ID | `[birim_kısaltma]-[3 haneli sıra no]` |
| Süreç Adı | `...` |
| İş Birimi | `...` |
| Süreç Sahibi | `Ad Soyad / Unvan / e-posta` |
| Veri Konusu Kişi Grubu | `...` |
| Veri Kategorisi | `Kimlik; İletişim; ...` |
| Kişisel Veri Öğeleri | `...` |
| Özel Nitelikli (E/H) | `H` |
| İşleme Amacı | `Belirli, açık, meşru amaç ifadesi` |
| Hukuki Sebep | `KVKK m.5/2/...` veya `Açık Rıza` |
| Toplama Yöntemi | `Otomatik / Otomatik olmayan / Karma + kanal` |
| Kayıt Ortamı | `Elektronik (...) / Fiziksel (...)` |
| Aktarım Yapılan İç Birim | `...` |
| Yurt İçi Alıcı / Alıcı Grubu | `...` |
| Yurt Dışı Aktarım (E/H) | `H` |
| Yurt Dışı Alıcı + Ülke | `—` (yok ise) |
| Yurt Dışı Hukuki Temel | `—` |
| Saklama Süresi | `... yıl/ay` |
| Saklama Gerekçesi | `Mevzuat referansı veya zamanaşımı analizi` |
| İmha Yöntemi | `Silme / Yok etme / Anonim hale getirme` |
| İmha Periyodu | `6 ay` (varsayılan) |
| Teknik Tedbirler | `Şifreleme, log, MFA, ...` |
| İdari Tedbirler | `Eğitim, gizlilik, ...` |
| Risk Seviyesi | `Düşük / Orta / Yüksek / Kritik` |
| İlgili Aydınlatma Metni | `AYD-...` |
| Açık Rıza Gerekli mi? | `E/H` + gerekçe |
| Son Güncelleme | `YYYY-AA-GG / Hazırlayan` |

## 3. CSV Başlık Satırı (Kopyala-Yapıştır)

```csv
surec_id,surec_adi,is_birimi,surec_sahibi,veri_konusu_kisi_grubu,veri_kategorisi,kisisel_veri_ogeleri,ozel_nitelikli,isleme_amaci,hukuki_sebep,toplama_yontemi,kayit_ortami,aktarim_ic_birim,yurtici_alici,yurtdisi_aktarim,yurtdisi_alici_ulke,yurtdisi_hukuki_temel,saklama_suresi,saklama_gerekce,imha_yontemi,imha_periyodu,teknik_tedbirler,idari_tedbirler,risk_seviyesi,aydinlatma_metni,acik_riza_gerekli,son_guncelleme
```

### 3.1 Örnek CSV Satırı

```csv
IK-001,Çalışan Adayı İşe Alım,İnsan Kaynakları,İK Direktörü,Çalışan Adayı,Kimlik;İletişim;Mesleki Deneyim;Eğitim,"ad-soyad, TCKN, telefon, e-posta, eğitim, iş tecrübesi",H,"Aday değerlendirme; mülakat; iş teklifi","m.5/2/c sözleşme öncesi tedbirler; aday havuzu için Açık Rıza","Otomatik (kariyer sitesi); Otomatik olmayan (kağıt)","Elektronik (ATS, e-posta); Fiziksel (özlük)","İK; ilgili departman","Aday değerlendirme firmaları, avukatlık ortağı",E,"LinkedIn Talent (ABD); Greenhouse (ABD/AB)","Standart sözleşme + Kurul bildirim",1 yıl (havuz 2 yıl),"İş başvurusu zamanaşımı analizi",Silme + Yok etme,6 ay,"TLS, AES-256, MFA, audit log","Gizlilik, KVKK eğitimi, yetkilendirme",Orta,AYD-IK-01,E,2026-05-08
```

## 4. Alan Tanımları (Sözlük)

### 4.1 Süreç ID
Şirket içi tekil tanımlayıcı. Önerilen format: `[Birim 2-3 harf]-[3 haneli sıra]` (örn. IK-001, MUS-002, BT-014).

### 4.2 Veri Konusu Kişi Grubu (Yön. M.4/n)
"Veri sorumlularının kişisel verilerini işledikleri ilgili kişi kategorisi." Tipik gruplar:
- Çalışan, Çalışan Adayı, Eski Çalışan, Çalışan Yakını
- Müşteri, Potansiyel Müşteri, Eski Müşteri
- Tedarikçi Çalışanı, Tedarikçi Yetkilisi
- Ziyaretçi, Stajyer, Danışman
- Hissedar, Yönetim Kurulu Üyesi
- 3. Kişi (referans veren, alıcı, kefil vb.)
- Çocuk (18 yaş altı veri konusu)

### 4.3 Veri Kategorisi (Yön. M.4/m)
"Kişisel verilerin ortak özelliklerine göre gruplandırıldığı veri konusu kişi grubu veya gruplarına ait kişisel veri sınıfını" ifade eder. VERBİS standart kategorileri:

- Kimlik (ad-soyad, TCKN, doğum tarihi, cinsiyet)
- İletişim (telefon, e-posta, adres)
- Lokasyon (GPS, IP, lokasyon servisleri)
- Özlük (özlük dosyası verileri)
- Hukuki İşlem (dava bilgileri, vekaletname)
- Müşteri İşlem (sipariş, fatura, geçmiş)
- Fiziksel Mekan Güvenliği (CCTV, kart kayıtları)
- İşlem Güvenliği (log, IP, oturum)
- Risk Yönetimi (skoring, risk profili)
- Finans (IBAN, kart bilgisi tokenize, gelir)
- Mesleki Deneyim (CV, eğitim, sertifika)
- Pazarlama (tercih, alışkanlık, profil)
- Görsel/İşitsel (fotoğraf, ses kaydı, video)
- Sağlık Bilgileri (özel nitelikli — KVKK m.6)
- Cinsel Hayat (özel nitelikli)
- Ceza Mahkumiyeti ve Güvenlik Tedbirleri (özel nitelikli)
- Biyometrik Veri (özel nitelikli)
- Genetik Veri (özel nitelikli)
- Felsefi inanç, din, mezhep, dini yapı (özel nitelikli)
- Dernek, vakıf, sendika üyeliği (özel nitelikli)
- Siyasi düşünce (özel nitelikli)

### 4.4 Hukuki Sebep
KVKK m.5/2 (genel veri) veya m.6/2-3 (özel nitelikli) bentlerinden biri. **Açık rıza son çare** olarak değerlendirilir.

### 4.5 Toplama Yöntemi (Aydınlatma Tebliği M.5/i)
"Tamamen veya kısmen otomatik yollarla ya da veri kayıt sisteminin parçası olmak kaydıyla otomatik olmayan yollarla" — açık ifade zorunlu.

### 4.6 Alıcı / Alıcı Grubu (Yön. M.4/a)
"Veri sorumlusu tarafından kişisel verilerin aktarıldığı gerçek veya tüzel kişi kategorisi." Tek tek aktarılan firma adlarını yazmak yerine kategori (örn. "Kargo şirketleri", "Avukatlık ortakları") yazılabilir; ancak yurt dışı aktarımda firma + ülke açıkça yazılmalıdır.

### 4.7 Saklama Süresi (Yön. M.9/4-5)
- Mevzuatta süre öngörülmüşse → o süre.
- Birden fazla süre varsa → en uzunu.
- Süre belirlenirken (M.9/4) sektörel teamül, hukuki ilişkinin süresi, meşru menfaat süresi, risk-maliyet, güncel tutmaya elverişlilik, hukuki yükümlülük süresi, zamanaşımı dikkate alınır.

### 4.8 İmha Yöntemi (Saklama ve İmha Yön. M.8-10)
- **Silme:** İlgili kullanıcılar için erişilemez ve tekrar kullanılamaz hale getirme.
- **Yok etme:** Hiç kimse tarafından erişilemez, geri getirilemez, tekrar kullanılamaz hale getirme.
- **Anonim hale getirme:** Başka verilerle eşleştirilse dahi kimliği belirli/belirlenebilir bir gerçek kişiyle ilişkilendirilemez hale getirme.

### 4.9 İmha Periyodu (Saklama ve İmha Yön. M.11)
Periyodik imha azami **6 ay** olmalıdır. Şirket politikasında daha kısa belirlenebilir.

### 4.10 Risk Seviyesi
- **Düşük:** Genel veri, küçük hacim, sınırlı paylaşım, düşük etki.
- **Orta:** Genel veri, orta hacim, dış paylaşım var, orta etki.
- **Yüksek:** Özel nitelikli veri, büyük hacim, otomatik karar verme, yurt dışı aktarım.
- **Kritik:** Çocuk verisi, biyometrik, sağlık + büyük hacim, yüksek otomatik profilleme, finansal işlem.

## 5. Tablo Görünümü Notu

Markdown tablo geniş olduğu için:
- Görüntü için: VS Code Markdown önizlemesi, GitHub veya GitLab.
- Düzenleme için: Excel/CSV'ye aktarın, sonra geri yapıştırın.
- Wiki üzerinde: Confluence veya SharePoint listesi olarak da tutulabilir.

## 6. Doğrulama Kontrolleri

Her satır oluşturulduktan sonra aşağıdaki kontroller yapılır:

- [ ] **Hukuki sebep + amaç tutarlı mı?** Sözleşme ifası dendiyse satır gerçekten sözleşmeden mi doğuyor?
- [ ] **Saklama süresi mevzuatla çatışıyor mu?** VUK 5 yıl yazılmışsa kontrol et — VUK m.253 uyarınca **5 yıl** vs. TTK m.82 uyarınca **10 yıl** ayrımı.
- [ ] **Yurt dışı aktarım kontrolü:** SaaS sağlayıcının sunucu lokasyonu doğrulandı mı? "AWS Frankfurt" yerine "AWS İrlanda" yazılmışsa düzeltilmeli.
- [ ] **Açık rıza yanlış konumlandırıldı mı?** Sözleşme ifası varken "açık rıza" denmesi en yaygın hatadır.
- [ ] **Aydınlatma metni var mı, güncel mi?** Aksi halde Yön. M.5/d ihlali.
- [ ] **VERBİS yansıması yapıldı mı?** Yeni satır eklendiğinde 7 gün içinde VERBİS güncellemesi.
