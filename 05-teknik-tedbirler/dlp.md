---
Doküman: Veri Sızıntısı Önleme (DLP) Politikası ve Standardı
Bölüm: 05-teknik-tedbirler
Sahip: DLP Ekip Lideri / CISO
Onaylayan: BT Direktörü + KVKK Komitesi + Hukuk + İK
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (yeni veri kümesi, false positive trendi, yeni vector)
İlgili Mevzuat: 6698 sayılı KVKK m.4 (Genel İlkeler — ölçülülük), m.12 (Veri Güvenliği), m.20 (Çalışan İzleme — Anayasa m.20 mahremiyet); İş Kanunu m.27 vd.; KVKK Çalışan Aydınlatma rehberi
İlgili Standart: ISO/IEC 27001:2022 A.8.12 (Data Leakage Prevention); NIST CSF 2.0 PR.DS-5; CIS Controls v8 #3.13; Cloud Security Alliance (CSA) DLP guidance; ENISA "Data Loss Prevention"
---

# Data Loss Prevention (DLP)

## 1. Amaç

Kişisel veri ve diğer hassas bilginin **yetkisiz biçimde dışarı çıkmasını** (dış paylaşım, sızdırılma, kasıtlı/kasıtsız ifşa) tespit ve önlemek için tasarlanmış kontrolleri tanımlar. KVKK m.12 "hukuka aykırı erişimi önleme" ve m.4 "amaç dışı işleme yasağı" ilkelerinin operasyonel ayağıdır.

## 2. Kapsam

DLP, üç temel veri durumu için tasarlanır:

1. **Data in Use** — son kullanıcı cihazında, uygulama içinde.
2. **Data in Motion** — ağda (e-posta, web, bulut SaaS, mesajlaşma).
3. **Data at Rest** — depolama alanlarında (sunucu, paylaşım, bulut depolama, endpoint disk).

## 3. Tasarım İlkeleri

1. **Veri Sınıflandırma Önce, DLP Sonra:** DLP, sınıflandırma çerçevesi olmadan etkisizdir. Politikalar sınıfa göre yazılır.
2. **Discovery Önce, Politika Sonra:** Hangi veri nerede yatıyor görülmeden kontrol koyulamaz.
3. **Önleyici + Tespit Edici Birlikte:** Block edilemeyen senaryoda alarm + post-hoc inceleme.
4. **Mahremiyet ile Dengeli:** Çalışan izleme orantılı, açıklanmış, log saklama makul.
5. **Çalışan Eğitimi DLP'nin Yarısıdır:** Teknolojik kontrol, davranış değişikliğiyle birlikte etkili olur.
6. **Sürekli Tunning:** False positive %20'nin altına inmediği sürece kullanıcı güveni erir.
7. **Insider Threat'a Hazır:** En tehlikeli sızıntı yetkili kullanıcıdandır; UEBA + DLP entegre.

## 4. Veri Discovery (Keşif)

### 4.1. Hedef

Hangi veri kümesi nerede yatıyor görmek; gizli/yanlış konumdaki kişisel veriyi ortaya çıkarmak.

### 4.2. Kapsam

- Endpoint (Windows/macOS/Linux laptop, sunucu).
- Dosya paylaşımı (SMB, NFS, SharePoint, Google Drive, Dropbox).
- E-posta arşivi.
- Veritabanları.
- Object storage (S3/Blob/GCS).
- Kod depoları.
- SaaS uygulamaları (Salesforce, Workday, ServiceNow, vs.).

### 4.3. Tanıma Yöntemleri

| Yöntem | Açıklama | Tipik Kullanım |
|--------|-----------|----------------|
| Regex / Pattern | TC kimlik no, IBAN, kart no (Luhn), telefon | Yapı belli alanlar |
| Keyword / Dictionary | "Maaş", "rapor sonucu", "tıbbi" | Sektörel terim |
| Document fingerprint | Bilinen hassas dokümanın tam/parçalı eşleşmesi | Ticari sır, sözleşme |
| Database fingerprint | Belirli DB satırlarının dış bulunması | Müşteri listesi |
| Machine learning classifier | Tıbbi rapor, finansal tablo | Yarı yapısal |
| Optical Character Recognition | Resim içinde metin (TC fotokopisi vb.) | Form doldurma |
| Microsoft Sensitivity Label | Otomatik / manuel etiket | Kurumsal entegrasyon |

### 4.4. Discovery Çalışması

- İlk taraflı tarama (full scan): tek seferlik, baseline.
- Aylık fark taraması.
- Yeni alan açıldıkça tetiklenmiş tarama.
- Bulgu raporu: hassas veri yanlış lokasyonda → CAPA, sahibinin migrasyonu.

## 5. Politika Tasarımı

### 5.1. Türk Bağlamı için Tipik Tanımlayıcı Listesi

| Veri Tipi | Tanıma Sınyali | Politika Aksiyonu |
|-----------|-----------------|--------------------|
| TC Kimlik No | 11 hane + algoritma kontrolü | Block (dış e-posta), Alarm (iç) |
| IBAN (TR..) | TR + 24 karakter + checksum | Block (dış), Alarm (iç) |
| Vergi Kimlik No | 10 hane + algoritma | Alarm |
| Kredi Kartı (PAN) | 13–19 hane + Luhn + BIN whitelist | Block heryerde |
| Sağlık Verisi | ICD-10 kodu, "tahlil sonucu" anahtar kelimeleri | Block (dış paylaşım) |
| Adli Sicil | Mevzuat anahtar kelimeleri | Block |
| Biyometrik (parmak, yüz şablonu) | Dosya formatı + boyut + "biyometrik" etiketi | Block |
| Maaş | Regex + bordro şablonu | Block (dış), Alarm (iç) |
| Çalışan özlük dosyası | Sensitivity label | Block (dış) |
| Müşteri listesi | DB fingerprint | Block / 2-step approval |
| Kaynak kod (sıkıyo) | Şirket repo path eşleşme | Alarm (kişisel cihaz) |

### 5.2. Aksiyon Türleri

- **Block & Notify:** Eylem engellenir, kullanıcıya açıklayıcı mesaj.
- **Block & Justify:** Kullanıcı gerekçe yazarak override edebilir; yönetici/SOC alarmlanır.
- **Encrypt:** Dış paylaşım otomatik şifreli (Microsoft Purview, Sensitivity label).
- **Quarantine:** Dosya/postaya el konulur, yönetici review eder.
- **Alert Only:** Yalnızca alarm; üretim aşamalı geçişte kullanılır, kalıcı **olmamalı**.
- **Tombstone / Remove:** Yanlış konumdaki veri yerinden alınır, "burada olmamalı" bilgisi bırakılır.

### 5.3. Politika Önceliklendirme

- En sıkı kontroller: PCI (kart), özel nitelikli (sağlık, biyometrik).
- Orta: TC kimlik, IBAN, ad-soyad, e-posta.
- Düşük: Genel iletişim bilgisi (kurumsal e-posta gönderilebilir).
- Şirket sırrı, kaynak kod ayrı politika ailesi.

## 6. DLP Bileşenleri

### 6.1. Endpoint DLP

- Ajan tabanlı (CrowdStrike, Microsoft Purview, Trellix, Forcepoint, Symantec).
- USB / removable media kontrolü.
- Yazıcı kontrolü.
- Pano (clipboard) sınırlandırma (hassas kopyalama bilgi verir/bloklar).
- Yerel uygulamada upload denetimi (tarayıcı).

### 6.2. Network DLP

- Çıkış noktasında inline (forward proxy, ICAP).
- HTTP/S, FTP, SMB analizi.
- Şifreli trafik için TLS inspection (mahremiyet listesi hariç — bkz. [ag-guvenligi.md](ag-guvenligi.md)).

### 6.3. Email DLP

- Mail gateway entegrasyonu (Mimecast, Proofpoint, Microsoft Defender).
- Outbound e-posta inceleme: konu + gövde + ek + nested ek.
- Otomatik şifreleme (sensitivity label triggered).
- Dış alıcı uyarısı.

### 6.4. Cloud / SaaS DLP (CASB)

- API tabanlı CASB (Microsoft Defender for Cloud Apps, Netskope, Palo Alto Prisma).
- SaaS içinde dosya tarama, paylaşım kontrolü.
- "Public link" tespiti, otomatik kapama veya alarm.
- IDP / cihaz uyumluluğu ile koşullu erişim.

### 6.5. Web/Mobile Channel DLP

- Webmail (Gmail, Yandex), file-share (WeTransfer, Dropbox personal), kod paylaşımı (pastebin, GitHub gist).
- Tipik politika: kişisel cihazlardan kişisel webmail'e iş cihazından upload **block**.

### 6.6. Print DLP

- Yazıcı kuyrukları DLP ajan ile.
- Hassas dokümanın şirket dışı yazıcıya gönderimi engelli.
- Gizli sınıfı dokümanlar yazıcıdan **PIN ile** alınır.

## 7. Çalışan Mahremiyeti ve Hukuki Çerçeve

### 7.1. Yasal Sınırlar

- **KVKK m.4 (Ölçülülük):** İşleme amacı için gerekli, sınırlı, ölçülü olmalı.
- **Anayasa m.20:** Özel hayatın gizliliği.
- **İş Kanunu:** İşverenin denetim hakkı, ancak çalışanın mahremiyetiyle dengelenmiş.
- **AYM ve Yargıtay içtihadı:** Çalışanın denetlendiğine **önceden açık biçimde bilgilendirilmesi** zorunlu.

### 7.2. Operasyonel Yansımalar

- DLP politikası, **Çalışan Aydınlatma Metni** + **Bilgi İşlem Kullanım Politikası** ile **açıkça** duyurulur (yıllık imza).
- İncelenen kanallar listelenir (kurumsal e-posta, dosya paylaşım, web proxy, endpoint).
- Kişisel webmail/sosyal medya/kişisel mesajlaşma içeriği **incelenmez**.
- Loglama amaca **uygun** ve **minimum** içerikle yapılır.
- DLP olay incelemesi 4-eyes (CISO + İK + Hukuk).
- Saklama süresi tanımlı (genel kural 1 yıl; soruşturma açıldığında uzatılabilir).
- Olay sonucunda disiplin işlemi sadece **resmi süreç** üzerinden, çalışana savunma hakkı tanınarak.

### 7.3. BYOD Bağlamı

- Kişisel cihaza DLP ajan kurulmaz; **iş profili** (Android Work Profile, iOS supervised) içinde kontrol uygulanır.
- Kişisel verilere kurum erişmez.
- Selektif silme — sadece iş profili wipe.

## 8. False Positive ve Tunning

### 8.1. FP'nin Maliyeti

- Kullanıcı verimsizliği.
- "Hep yanlış pozitif" algısı SOC alarmlarına duyarsızlık yaratır.
- Override haklarının yaygın kullanımı politikayı aşındırır.

### 8.2. Tunning Süreci

- Hedef: false positive ≤ %20.
- Aylık FP raporu, en sık eşleşen kural / kullanıcı.
- Beyaz liste yönetimi (örn. iç yazılım hata mesajları kart numarasına benziyorsa).
- Bağlam ekleme (alıcı domain, gönderici departman, dosya formatı).
- Eğitim malzemesi olarak gerçek olay anonimleştirilmiş paylaşımı.

## 9. Olay Yanıtı (DLP Spesifik)

### 9.1. Olay Sınıfları

| Sınıf | Tanım | Yanıt |
|-------|-------|-------|
| Düşük | Kullanıcı politikayı bilmeden dış e-posta'ya iliştirdi, block çalıştı | Eğitim hatırlatması |
| Orta | Tekrarlayan kural ihlali | Yönetici görüşmesi, ek eğitim |
| Yüksek | Toplu / kasti dış aktarım, hassas veri | Soruşturma, hesap dondurma, İK + Hukuk |
| Kritik | Aktif veri sızıntısı kanıtı | IR aktivasyonu, ihlal yönetimi (08), KVKK Komitesi |

### 9.2. İnceleme Akışı

1. SOC olayı triage eder.
2. Yetersiz bağlam varsa kullanıcıdan açıklama (gerekçe).
3. 4-eyes review: CISO temsilcisi + İK + Hukuk (yüksek/kritik).
4. Karar: kapatma / eğitim / disiplin / IR.
5. Kanıt zinciri korunur.
6. Lessons learned politikaya geri besler.

## 10. Insider Threat Programı

DLP, insider threat programının teknik ayağıdır. Tamamlayıcılar:

- UEBA — kullanıcı baseline + anomali.
- HR sinyalleri (ayrılık duyurusu, performans sorunu) ile koşullu artırılmış izleme (gerekçeli, süreli, KVKK Sorumlusu onayıyla, Hukuk denetimli).
- Periyodik insider threat inceleme komitesi (CISO + İK + Hukuk + KVKK).
- Çalışan ayrılık dönemi 30 gün artırılmış izleme (default, çıkış müşterekliği — exit interview ile uyumlu).

## 11. Loglama ve Kanıt

- DLP olayı ham kayıt: zaman, kullanıcı, kanal, kural, eylem, eşleşen örnek (kişisel veri minimize, hash + ilk 2 + son 2 karakter).
- Saklama: 1 yıl genel, 5 yıl kritik / soruşturmalı.
- Kanıt zinciri (chain of custody) — bkz. [log-yonetimi.md](log-yonetimi.md).
- Olaylar SIEM'e + CASB konsoluna.

## 12. KPI

- Discovery kapsamı: %95+ veri varlık envanterinin kapsanması.
- DLP Block oranı / toplam: trend.
- False positive: ≤ %20.
- Override kullanımı: izlenen, sahibi belli, az.
- Politika ihlali olayları: aylık trend, departman bazlı eğitim ihtiyacı.
- Aydınlatma metni güncellik: yıllık.
- Yıllık tatbikat (red team data exfil) tespit oranı: ≥ %85.

## 13. Kontrol Listesi

- [ ] Veri sınıflandırma + sensitivity label uygulanıyor mu?
- [ ] Discovery taraması tüm depolama tipleri için aylık çalışıyor mu?
- [ ] Endpoint, Network, E-posta, CASB DLP entegre tek konsoldan yönetiliyor mu?
- [ ] PCI veri için "block everywhere" politikası var mı?
- [ ] Özel nitelikli veri için sıkı politika + audit var mı?
- [ ] Çalışan Aydınlatma Metni DLP kapsamını listeliyor, yıllık imzalı mı?
- [ ] Kişisel webmail/sosyal medya içeriği inceleme dışı mı?
- [ ] BYOD'da iş profili / kişisel veri ayrımı uygulanıyor mu?
- [ ] False positive aylık raporlanıyor, hedef ≤ %20 mi?
- [ ] DLP olay 4-eyes review (CISO + İK + Hukuk) ile inceleniyor mu?
- [ ] Insider threat programı UEBA ile entegre mi, ayrılık döneminde artırılmış izleme yazılı mı?
- [ ] DLP olayları SIEM'e gidiyor, KVKK ihlal eşiğinde 08 sürecini tetikliyor mu?
- [ ] Yıllık red team data exfil tatbikatı yapılıyor mu?
- [ ] Override kullanımı sahibi/sıklığı izleniyor mu?
- [ ] Yazıcı, USB, pano kontrolü politika uyumlu mu?
- [ ] Discovery sonucu yanlış lokasyondaki veri için CAPA açılıyor mu?
- [ ] Tedarikçi/danışman cihaz/erişiminde DLP kapsamı belirli mi?

## 14. Yaygın Hatalar

- "Detect only" modunda kalıp asla "prevent"e geçmemek.
- Çalışana DLP varlığını duyurmamak — hukuki risk yaratır.
- TLS inspection olmadan ağ DLP'sinin etkisiz olduğunun fark edilmemesi.
- Aşırı geniş regex (ör. tüm 11 haneli sayılar TC) yüzünden FP fırtınası.
- BYOD'da kişisel cihaza tam ajan kurulması — KVKK ölçülülük ihlali.
- Override kullanımının takipsiz kalması.
- DLP'nin yalnızca dış sızıntı odaklı kurulması, dahili lateral data movement görmezden gelinmesi.

## 15. Tedarikçi Yönetimi ile İlişki

- Veri işleyen tedarikçilerin DLP zorunluluğu sözleşme maddesi olarak belirlenir.
- Tedarikçi olayında bildirim SLA (24-72 saat).
- Tedarikçi penetrasyon test sonuçları periyodik gözden geçirilir.
- Bkz. [06-idari-tedbirler/tedarikci-yonetimi.md](../06-idari-tedbirler/tedarikci-yonetimi.md).
