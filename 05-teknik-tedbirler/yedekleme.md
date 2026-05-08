---
Doküman: Yedekleme, Kurtarma ve İş Sürekliliği Standardı
Bölüm: 05-teknik-tedbirler
Sahip: BT Operasyon Müdürü / CISO (yedek bütünlüğü)
Onaylayan: BT Direktörü + KVKK Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (büyük mimari değişiklik, ihlal, başarısız restore tatbikatı)
İlgili Mevzuat: 6698 sayılı KVKK m.12; Kişisel Veri Güvenliği Rehberi — "Kişisel Verilerin Yedeklenmesi"
İlgili Standart: ISO/IEC 27001:2022 A.8.13 (Information Backup), A.5.30 (ICT Readiness for Business Continuity), A.8.14 (Redundancy of Information Processing Facilities); ISO 22301 (Business Continuity); NIST CSF 2.0 PR.DS-11, RC.RP; NIST SP 800-34 (Contingency Planning); CIS Controls v8 #11; ENISA Backup & Restore Guidelines
---

# Yedekleme, Kurtarma ve İş Sürekliliği

## 1. Amaç

Kişisel veri ve diğer kritik bilginin **kayıp, bozulma, fidye yazılımı, doğal afet, insan hatası** karşısında zamanında ve eksiksiz biçimde geri yüklenebilmesini sağlamak. Yedek varlığı tek başına yeterli değildir; **bütünlüğü, gizliliği, geri yüklenebilirliği** beraber garantiye alınır.

## 2. Tasarım İlkeleri

1. **Kişisel Veri Yedeği = Kişisel Veri:** Yedek de KVKK kapsamındadır. Şifreleme, erişim, saklama, imha kurallarına aynen tabidir.
2. **3-2-1-1-0 Kuralı:**
   - **3** kopya (1 üretim + 2 yedek),
   - **2** farklı medya/teknoloji,
   - **1** offsite,
   - **1** offline / immutable / air-gapped,
   - **0** doğrulanmamış restore (her tatbikatın doğrulamayla tamamlanması).
3. **Şifreleme Zorunlu:** Yedek üretim sistemiyle **ayrı anahtar zinciri** kullanır.
4. **Test Edilmemiş Yedek Yedek Değildir:** Çeyreklik restore testi zorunlu.
5. **Ransomware Karşıtı:** En az bir kopya, üretim sisteminin ele geçmesinden etkilenmez (immutable / air-gapped / offline).
6. **Saklama Politikası ile Hizalı:** Yedek saklama süresi, üretim verisinin saklama süresi + makul kurtarma penceresi.
7. **Crypto-Shred ile Uyumlu:** İlgili kişinin silme talebi yedeklerden de işlenir (politika gereği gecikmeli olabilir; süre belgelenir).

## 3. Yedekleme Stratejisi

### 3.1. Veri Sınıflandırma + RTO/RPO Tablosu

| Sınıf / Sistem | RPO (kayıp toleransı) | RTO (kurtarma süresi) | Yedek Sıklığı | Saklama |
|----------------|------------------------|------------------------|----------------|---------|
| Tier 0 — Kart, sağlık, kritik müşteri DB | 15 dakika | 1 saat | Continuous (CDC) + saatlik | 35 gün hot, 1 yıl warm, 7 yıl cold |
| Tier 1 — Müşteri uygulama DB | 1 saat | 4 saat | Saatlik | 35 gün, 1 yıl, 5 yıl |
| Tier 2 — İK, mali, ERP | 4 saat | 8 saat | 4 saatte bir | 30 gün, 1 yıl, 7 yıl |
| Tier 3 — İçerik, dosya paylaşım | 24 saat | 24 saat | Günlük | 30 gün, 90 gün |
| Tier 4 — Dahili wiki, intranet | 7 gün | 72 saat | Haftalık | 90 gün |

> RPO/RTO hedefleri **iş etkisi analizi (BIA)** ile belirlenir. Üst yönetim onayı gerekir.

### 3.2. Yedek Türleri

- **Full:** Haftalık.
- **Incremental:** Günlük.
- **Differential:** Bazı senaryolarda günlük (incremental yerine).
- **Snapshot:** Saatlik (uygulama-tutarlı; VSS / fsfreeze / DB-quiesce).
- **CDC / Log-shipping:** Sürekli (DB transaction log).
- **Replikasyon:** Eş zamanlı / asenkron (DR sitesine).

> Replikasyon **yedek değildir** — silinen / bozulan veri eş zamanlı olarak ikinci kopyaya da gider. Replikasyon + yedek beraber kullanılır.

### 3.3. Yerleşim

```
Üretim Site (Birincil)
   ├── Local snapshot (saatlik) ── ransomware'da en hızlı kurtarma
   ├── Local backup repo (sıkı IAM, MFA, immutability) 
   ├── Replikasyon → DR Site (asenkron)
   └── Offsite cloud backup (immutable bucket, ayrı tenant) 
                                         ↓
                                   Air-gap / Tape kasası (offline)
```

### 3.4. Air-Gap & Immutability

- **S3 Object Lock (Compliance Mode)** / Azure Immutable Blob / GCP Bucket Lock: belirlenen retention süresince hiç kimse (root dahil) silemez.
- **Tape/LTO** (LTO-9 + WORM kartuş) — yıllık kasa.
- **Backup vendor "hardened repository"** (Veeam Hardened Linux Repo, Rubrik Air Gap, Cohesity SecureView).
- **Ayrı IAM tenant / hesap** — üretim ortam credential'ı yedek altyapısına erişemez.
- **2FA + 4-eyes** silme onayı (operatörel zorunlu silme bile bunu gerektirir).

## 4. Şifreleme ve Anahtar Yönetimi

- Yedek **ingest sırasında** şifrelenir; transitte de TLS.
- Anahtar **KMS/HSM** üzerinde, üretim DEK ile **farklı KEK altında**.
- Yedek anahtarı, üretim sisteminden ayrı bir credential ile erişilir; saklama yeri ve audit ayrı.
- Anahtar kayıp = veri kayıp; bu nedenle anahtar **yedeği** ayrı süreçle (HSM cluster + offline kâğıt M-of-N share kasası) korunur.

## 5. Bütünlük Doğrulama

- Her yedek üretiminde checksum (SHA-256) + manifest.
- Periyodik (haftalık) checksum doğrulama.
- Bit-rot tespiti için scrub (object storage, ZFS scrub, tape verify).
- Yedek meta verileri ayrı sistemde de saklanır.

## 6. Geri Yükleme (Restore) Test Programı

### 6.1. Test Sıklıkları

| Test | Sıklık | Kim |
|------|--------|-----|
| Tek dosya restore (random) | Aylık | BT Operasyon |
| DB point-in-time restore | Çeyreklik | DBA |
| Tam sunucu / VM restore | Çeyreklik | BT Operasyon |
| Uygulama bütünleşik restore | Çeyreklik | Uygulama Ekibi + DBA |
| DR site geçiş tatbikatı (planlı) | Yıllık | BCP Komitesi |
| DR site geçiş + iş süreklilik | Yıllık | İş Birimleri + BT |
| Ransomware kurtarma tatbikatı | Yıllık | CISO + SOC + BT |
| Air-gap / tape restore | Yıllık | BT Operasyon |

### 6.2. Test Kanıtı

- Test öncesi: kapsam, hedef RTO/RPO, ekip, başarı kriteri.
- Test sırası: zaman damgalı log, ekran görüntüleri, ölçümler.
- Test sonrası: rapor (başarı/başarısız, ölçüm vs hedef, bulgu, aksiyon).
- Başarısızlıklar **CAPA** açar; 30 gün içinde kapanır veya gerekçe yazılır.

### 6.3. Doğrulama Kriterleri

- Veri tamlığı (satır sayısı, hash, örnek karşılaştırma).
- Veri tutarlılığı (yabancı anahtar, uygulama-seviyesi referans).
- Kimlik doğrulama / yetki çalışıyor mu.
- RTO ölçümü — hedefe karşı.
- Restore sonrası uygulama smoke test.

## 7. DR (Felaket Kurtarma) Mimarisi

### 7.1. DR Strateji Türleri

| Strateji | Maliyet | Kurtarma Süresi |
|----------|---------|------------------|
| Backup & Restore | Düşük | Saatler-günler |
| Pilot Light (DR site minimum) | Orta | Saatler |
| Warm Standby (azaltılmış kapasite hazır) | Yüksek | Dakikalar-saatler |
| Active-Active (eş zamanlı çalışan) | Çok yüksek | Yakın sıfır |

Tier 0/1 sistemler için en az **Warm Standby**; Tier 2-3 için Pilot Light yeterli olabilir.

### 7.2. DR Site Konumu

- Birincil siteyle aynı doğal afet kuşağında **olamaz** (deprem fay hattı, sel havzası, aynı elektrik şebekesi).
- Yurt içinde tercih (yurt dışı DR için KVKK aktarım rejimi değerlendirilir — bkz. [07-aktarim](../07-aktarim/)).
- Bulut DR: ayrı bölge (region) ve mümkünse ayrı cloud sağlayıcı (multi-cloud) tercih edilebilir.

### 7.3. RTO/RPO Doğrulama

- Yıllık DR tatbikatı planlı geçişle ölçer.
- Beklenen RTO/RPO sapmaları analiz edilir.
- Yönetim Kurulu'na yıllık BCP raporu sunulur.

## 8. Ransomware Dirençlilik

### 8.1. Tasarım Önlemleri

- **Immutable + air-gap kopya** (zorunlu).
- **Yedek altyapısı ayrı IAM domain** — üretim AD'sinde compromise olursa yedek erişimi etkilenmez.
- **Yedek operatör hesabı MFA + PAM**.
- **Yedek durdurma alarmı** — yedek job başarısızlığı 24 saat içinde alarm.
- **Şüpheli silme/encrypt akışı tespiti** — anormal hacimde dosya yeniden adlandırma EDR ile tespit.
- **Yedek envanteri salt-okunur kopya** — saldırgan envanter silmek isteyebilir.

### 8.2. Yıllık Tatbikat Senaryoları

- Tüm üretim ortamı şifrelenmiş varsayılır → DR site + air-gap kopyadan geri yükleme.
- Üretim AD compromise → yedek altyapısının etkilenmediği doğrulanır.
- Saldırgan yedek silmiş varsayılır → immutable kopya hedefi karşılar mı?

## 9. Yedek Erişim Kontrolü

- Yedek operatörü = küçük ekip (3-5 kişi).
- 4-eyes restore: production restore iki kişinin onayı.
- PAM ile oturum kayıtlı.
- Yedek envanter, restore log'u SIEM'e.
- Periyodik review (çeyreklik).

## 10. KVKK İmha Talepleri ile Etkileşim

### 10.1. Sorun

İlgili kişi KVKK m.7 / m.11 kapsamında silme talep ettiğinde, üretim sisteminden silinse de **yedeklerde kalabilir**. KVKK Komitesi'nin pozisyonu: yedek silmek **operasyonel olarak orantısız** ise, **belgeli politika** ile şu yaklaşım kabul edilir:

### 10.2. Yedek-Geçişli İmha Politikası

1. Üretimde kayıt **derhal** silinir/anonimleştirilir.
2. Yedeğe yansıyan eski kayıt, yedek **saklama süresi sonunda** otomatik imha edilir.
3. Bu yedek kayıttan **geri yükleme istisna** durumudur. Eğer yedekten geri yükleme yapılırsa, geri yükleme prosedürü silinmiş kayıtların yeniden silinmesini **otomatik tetikler** (silme listesi tutulur).
4. İlgili kişi bilgilendirme metninde / aydınlatma metninde bu husus açıklanır.
5. Crypto-shred yöntemi geçerli olduğunda (yedek anahtarı sınıf bazlı), anahtar imhası bu süreyi kısaltabilir.

### 10.3. Belgeleme

- Silme talebi → silme tutanağı → yedek kuyruğunda anonim listede kayıt → yedek imhası tutanağı.
- Denetim soruşturmasında zincir gösterilebilir.

## 11. Yedek Saklama Süresi Sonu

- Saklama süresi sonu otomatik olarak imha politikasını tetikler.
- Tape: degausser veya fiziksel parçalama, tutanak.
- Disk: secure erase (NIST SP 800-88) + crypto-shred.
- Bulut immutable: retention süresi kendiliğinden iptale döner; süreden sonra silme.

## 12. Tedarikçi Yedeği

- SaaS sağlayıcının yedek politikası **bizim politikamızı karşılamak zorundadır**.
- Sözleşmeye eklenen maddeler: RPO/RTO, yedek şifreleme, geri yüklenebilirlik, exit strategy (verinin teslim edilmesi).
- Düzenli olarak SaaS verilerinin **kendi tarafımıza** yedeği alınır (örn. Microsoft 365, Salesforce, Workday için 3rd party backup).
- Bkz. [06-idari-tedbirler/tedarikci-yonetimi.md](../06-idari-tedbirler/tedarikci-yonetimi.md).

## 13. Loglama

- Yedek başarı/başarısız (job, hedef, süre, boyut).
- Restore başlatma (kim, neden, kapsam).
- Yedek silme (manuel/otomatik).
- Anahtar erişim.
- Politika değişikliği.

Tüm yedek olayları SIEM'e (bkz. [log-yonetimi.md](log-yonetimi.md)).

## 14. Kontrol Listesi

- [ ] Tüm Tier 0/1 sistemler için CDC veya saatlik snapshot var mı?
- [ ] 3-2-1-1-0 kuralı uygulanıyor mu? (Air-gap/immutable kopya doğrulanmış)
- [ ] Yedek şifreleme + ayrı KEK uygulanıyor mu?
- [ ] Yedek anahtarı M-of-N + offline kasa ile korunuyor mu?
- [ ] Yedek altyapısı ayrı IAM domain + MFA/PAM ile mi yönetiliyor?
- [ ] Çeyreklik restore tatbikatı yapılıyor mu, kanıt arşivleniyor mu?
- [ ] Yıllık DR site geçiş tatbikatı yapıldı mı?
- [ ] Yıllık ransomware kurtarma tatbikatı yapıldı mı?
- [ ] Tape/LTO immutable kartuş ile, kasa kontrolü?
- [ ] RTO/RPO BIA'a göre belirlenip yönetimce onaylandı mı?
- [ ] DR site farklı bölge / coğrafyada mı?
- [ ] SaaS verileri için 3rd party backup var mı?
- [ ] KVKK silme talebinin yedeğe yansıma süreci yazılı mı?
- [ ] Yedek bütünlüğü periyodik scrub ile doğrulanıyor mu?
- [ ] Yedek başarısızlık alarmı ≤ 24 saat tetikliyor mu?
- [ ] Yedek operatörü erişimi 4-eyes ve PAM kayıtlı mı?
- [ ] Yedek silme yetkisi sınırlı, retention sonu otomatik mi?

## 15. KPI

- Yedek başarı oranı: ≥ %99.
- Restore tatbikat başarı oranı: ≥ %99.
- Ortalama restore süresi vs. RTO: hedef tutturma %95+.
- Air-gap kopya tazeliği: ≤ 24 saat.
- Yedek operatör eylemi PAM kayıt oranı: %100.

## 16. İhlal / Kurtarma Yanıt Akışı

```
Tetik (veri kayıp / bozulma / ransomware) →
   1) İzole et (etkilenen sistem)
   2) Yedek envanteri kontrol — hangi tarihten geri dön?
   3) Tarihsel etki: ne kadar veri kaybı olacak (RPO)
   4) Restore hedefi seç (immutable kopya tercihli)
   5) Test ortamına önce restore, doğrula
   6) Üretime geri yükle
   7) Smoke test + iş birimi onayı
   8) Lessons learned + post-incident report
```

KVKK Komitesi bilgilendirilir; eğer kişisel veri etkilendiyse 08-ihlal-yonetimi prosedürü tetiklenir.
