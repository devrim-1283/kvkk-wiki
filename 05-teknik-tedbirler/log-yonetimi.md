---
Doküman: Log Yönetimi, SIEM ve Olay İzleme Politikası
Bölüm: 05-teknik-tedbirler
Sahip: SOC Lideri / CISO
Onaylayan: BT Direktörü + KVKK Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (yeni log kaynağı, mevzuat, tespit gap)
İlgili Mevzuat: 6698 sayılı KVKK m.12; Kişisel Veri Güvenliği Rehberi — "Kişisel Veri Güvenliği Takibi", "Bilgi Güvenliği Olay Yönetimi"; 5651 sayılı İnternet Ortamında Yapılan Yayınların Düzenlenmesi ve Bu Yayınlar Yoluyla İşlenen Suçlarla Mücadele Edilmesi Hakkında Kanun ve ilgili Yönetmelik (yer/iç sağlayıcı log saklama yükümlülüğü)
İlgili Standart: ISO/IEC 27001:2022 A.8.15 (Logging), A.8.16 (Monitoring Activities), A.5.7 (Threat Intelligence); NIST CSF 2.0 DETECT (DE.AE, DE.CM, DE.DP); NIST SP 800-92 (Guide to Computer Security Log Management); MITRE ATT&CK; SANS SOC playbook framework; ENISA SIEM guidelines
---

# Log Yönetimi, SIEM ve İzleme

## 1. Amaç

Kişisel veri işleme ortamlarında **gerçekleşen, gerçekleşmeye çalışılan ve şüpheli** her güvenlik açısından önemli olayın toplanması, korunması, analizi, tespit edilmesi ve müdahale edilmesi için bütünleşik bir log + SIEM + tespit + müdahale çerçevesi tanımlar. KVKK m.12'nin "muhafaza" ve "ihlal halinde tespit" yükümlülüklerinin teknik temelidir.

## 2. Tanımlar

| Terim | Tanım |
|-------|-------|
| Log | Bir sistem veya uygulamanın olay kaydı. |
| Telemetri | Geniş anlamda olay + metrik + iz (trace) verisi. |
| SIEM | Security Information and Event Management — toplama, normalizasyon, korelasyon, alarm. |
| SOAR | Security Orchestration, Automation, Response — playbook otomasyonu. |
| UEBA | User and Entity Behavior Analytics — davranışsal anomali tespiti. |
| WORM | Write Once Read Many — değiştirilemez depolama. |
| Threat Intel | Tehdit istihbaratı, IOC, TTP. |

## 3. Loglanacak Olaylar

### 3.1. Kimlik / Kimlik Doğrulama

- Başarılı/başarısız oturum açma (kullanıcı, IP, kullanıcı agent, lokasyon, MFA durumu).
- Parola değişimi, sıfırlama, kurtarma akışı.
- MFA challenge, başarısız MFA, push fatigue.
- Federation assertion (SAML/OIDC).
- Token üretim, refresh, iptal.

### 3.2. Yetkilendirme

- Yetki yükseltme (sudo, runas, AssumeRole, PIM eligible → active).
- Rol/grup üyeliğinde değişiklik.
- IAM policy ekleme/silme.
- Erişim reddi (DENY).
- Politika dışı erişim girişimi.

### 3.3. Kişisel Veri Erişim Olayları

- Kişisel veri içeren tablolardan SELECT (kullanıcı, sorgu özeti, satır sayısı; sorgu metni — değerler maskelenmiş).
- Kişisel veri export / indirme (kullanıcı, hedef, dosya, satır sayısı).
- Kişisel veri yazdırma.
- Kişisel veri içeren e-posta gönderimi (büyük ek, yığın gönderim).
- Kişisel veri tablosu üzerinde DDL (CREATE/ALTER/DROP/TRUNCATE).
- Toplu silme/güncelleme.
- API üzerinden bulk read.

### 3.4. Sistem Yöneticisi Etkinlikleri

- Servis başlatma/durdurma.
- Konfigürasyon değişikliği.
- Yeni hesap oluşturma.
- Log temizleme/durdurma — **kritik alarm**.
- Saat değişikliği — **kritik alarm**.
- Yedek/restore işlemi.
- Anahtar kullanımı (KMS/HSM).

### 3.5. Ağ ve Çevre

- Firewall: izinli/izinsiz trafik.
- WAF: kural tetiklenmesi.
- IDS/IPS: tüm uyarı.
- VPN/ZTNA: bağlantı.
- DNS sorgu yanıt.
- Proxy URL erişim.

### 3.6. Uygulama Olayları

- Hata mesajları (kişisel veri içermeyecek şekilde sanitized).
- Ödeme, kayıt, hesap oluşturma, hesap silme, ilgili kişi başvurusu.
- Açık rıza kayıt değişimleri.
- Yapılandırma değişiklikleri.

### 3.7. Diğer

- Antivirüs / EDR olay.
- Yedek başarı/başarısız.
- Sertifika sona erme yaklaşımı.
- DLP olay.

## 4. Log İçeriği — Kişisel Veri Minimizasyonu

Loglama "her şeyi al" değildir. Loglar başlı başına **kişisel veri ortamıdır**.

### 4.1. Yasak / Sınırlı İçerik

- Parola, OTP, secret, API key, sertifika özel anahtarı — **asla**.
- Kart numarası tam (PAN) — **asla**; en fazla BIN + son 4.
- CVV/CVC — **asla**.
- TC kimlik no, sağlık verisi düz metin — **maskeli** veya hash.
- E-posta gövdesi, mesaj içeriği — **gerekmedikçe yok**.
- Çağrı kayıtları — sadece amaca uygun + KVKK aydınlatma + saklama süresi.

### 4.2. Önerilen İçerik

- Olay zamanı (UTC + saat dilimi).
- Olay türü (taxonomy).
- Aktör (kullanıcı/servis/sistem) — kullanıcı adı + kullanıcı ID.
- Hedef (kaynak/sistem/kayıt referansı).
- Sonuç (success/failure + reason code).
- Bağlam (IP, kullanıcı agent, oturum ID, korelasyon ID).
- Hassas veri varsa **referans** (kayıt ID), değer değil.

### 4.3. Sanitization

- Uygulama logları, SDK seviyesinde otomatik PII redaction.
- Düzenli ifade tabanlı tarayıcı (TC kimlik, IBAN, kart) ingestion'da sterilizasyon.
- "Tutamadık" durumlarda log alarmı + remediasyon.

## 5. Log Bütünlüğü

Loglar saldırganın değiştirip izini kapatabileceği bir varlıktır. Bütünlük zorunludur.

### 5.1. Kontroller

- **Merkezi toplama** — log üreten ana makine ile saklanan yer farklıdır.
- **WORM depolama** — yazılan log, retention süresi boyunca değiştirilemez/silinemez (S3 Object Lock — Compliance Mode, Azure Immutable Blob, Glacier Vault Lock).
- **Hashing & Signing** — ingest sırasında her partikül hash'lenir, periyodik olarak imzalanır (Merkle tree önerilir).
- **Ayrı yetki** — log yöneticisi ile sistem yöneticisi farklı kişilerdir (görev ayrılığı).
- **Saat senkronizasyonu** — tüm sistemler NTP ile senkron, en az 100ms tolerans.
- **Tam taşıma** — ana makinede sadece transit buffer; gönderim başarısız olduğunda alarm.

### 5.2. İhlal Tespiti

- Log akış kesilmesi → 5 dakika içinde alarm.
- Hash zincirinde kopukluk → kritik alarm + IR.
- Yetkili olmayan kişi tarafından log silme girişimi → kritik alarm.

## 6. SIEM Mimarisi

### 6.1. Bileşenler

```
Kaynaklar → Toplayıcı (Beats/Fluentd/Vector/syslog) → Pipeline (parse/enrich/sanitize) →
   → Hot tier (arama, dashboard, alarm — 90 gün) →
   → Warm tier (uzun arama, daha ucuz — 1 yıl) →
   → Cold/Archive (WORM, retention sonu — 2-7 yıl)
```

### 6.2. Normalizasyon

- ECS (Elastic Common Schema) veya OCSF (Open Cybersecurity Schema Framework) kullan.
- Tüm kaynaklar aynı alanlara çevrilir.

### 6.3. Enrichment

- Kullanıcı bağlamı (departman, lokasyon, hassasiyet seviyesi).
- IP → coğrafi konum, ASN, threat intel.
- Cihaz → uyumluluk durumu.
- Asset → CMDB (kişisel veri var mı, hangi sistem).

### 6.4. Korelasyon

- Kural tabanlı (Sigma, vendor formatı).
- Davranışsal (UEBA — user/entity baseline).
- Threat-intel eşleştirme.
- Multi-stage attack tespiti (örn. başarısız brute force → başarılı giriş → yetki yükseltme → veri okuma).

### 6.5. Tespit İçeriği — Kanonik Use Case'ler (KVKK odaklı)

| Use Case | Tetik | Aciliyet |
|----------|-------|----------|
| Yetkili olmayan kişisel veri erişimi | Kullanıcı RBAC dışı tablo SELECT | Kritik |
| Toplu kişisel veri exfiltration | Outbound > 100 MB / kısa süre / az bilinen domain | Kritik |
| Log silme/durdurma | Audit servis durdurma, log dosyası rm | Kritik |
| Ayrıcalıklı oturum saat dışı | Admin → kişisel veri DB iş saati dışı | Yüksek |
| Push fatigue | 10+ MFA push 5 dk içinde | Yüksek |
| Atypical travel | Aynı kullanıcı 1 saatte iki ülke | Yüksek |
| Kart verisi log'da | Regex tetik PAN düz metin log | Kritik |
| Yedek başarısızlık | Yedek job fail + 24 saat retry yok | Yüksek |
| Sertifika sona erme | < 7 gün | Yüksek |
| Yeni IAM rol kişisel veri yetkili | Provisioning olay | Orta |
| Anormal API çağrı hacmi | Endpoint baseline +5σ | Orta |
| Kötü amaçlı IP'den giriş başarılı | Threat intel hit | Kritik |
| Şifresiz HTTP → kişisel veri uygulaması | Prod TLS bypass | Yüksek |
| Yeni servis hesabı + kritik yetki | Provisioning + yetki | Yüksek |
| Veri kümesinde toplu DELETE/UPDATE | DML threshold | Yüksek |

### 6.6. UEBA

- Kullanıcı baseline: tipik giriş saati, lokasyon, cihaz, eriştiği veri kümeleri.
- Sapma → "anomalous score" → SOC tetik.
- Insider threat tespitinin temel yapı taşı.

## 7. Saklama Süresi

| Log Türü | Hot | Warm | Cold/Archive | Toplam |
|----------|-----|------|--------------|--------|
| Kimlik / yetki | 90 gün | 1 yıl | 4 yıl | **5 yıl** |
| Kişisel veri erişim | 90 gün | 1 yıl | 4 yıl | **5 yıl** |
| Sistem yöneticisi | 90 gün | 1 yıl | 1 yıl | **2 yıl** (kritik için 5 yıl) |
| Ağ / firewall | 90 gün | 9 ay | – | **1 yıl** |
| WAF | 90 gün | 9 ay | – | **1 yıl** |
| Uygulama | 90 gün | 9 ay | – | **1 yıl** |
| Yedek | 90 gün | 1 yıl | 4 yıl | **5 yıl** |
| 5651 (yer sağlayıcıysak) | – | – | – | Kanun gereği **2 yıl** ila 10 yıl arası ilgili düzenlemeye göre |
| PCI scope (uygulanırsa) | 90 gün online | – | 1 yıl arşiv | 1 yıl (PCI minimum) |

> Saklama süresi sonu **otomatik imha** — manuel uzatma yalnızca aktif soruşturma / hukuki tutma (legal hold) için ve gerekçeli.

## 8. 5651 Sayılı Kanun Çerçevesi

Eğer faaliyet kapsamımız "yer sağlayıcı" veya "iç içerik sağlayıcı" niteliğindeyse:

- Erişim ve trafik bilgileri kanunda tanımlı süre kadar saklanır.
- Saklama süresi içinde bütünlük korunur, yetkili merciin talebine elektronik ortamda iletilebilir.
- Saklanan bilgilerin **doğruluğunu, bütünlüğünü ve gizliliğini** sağlamak yer sağlayıcının yükümlülüğüdür.
- Bu kapsamdaki loglar, KVKK kapsamındaki kişisel veri logundan **ayrı erişim** ile yönetilir; sahibi Hukuk + CISO.

## 9. SOC Operasyonları

### 9.1. Vardiya Yapısı

- 7/24 izleme (kurum büyüklüğü gerektiriyor).
- 3 vardiya (08-16, 16-00, 00-08), Tier-1 / Tier-2 / Tier-3 + Threat Hunting.
- Vardiya devir formu, açık biletler, devam eden olaylar, eskalasyon zinciri.

### 9.2. Eskalasyon Zinciri

```
Tier-1 (triage, yanlış pozitif elemesi) → Tier-2 (analiz, IOC, sınırlama) →
   → Tier-3 (derin forensic, lateral movement, kapsamlı IR)
   → CISO + KVKK Sorumlusu (kişisel veri ihlali ihtimali) → KVKK Komitesi → Yönetim
```

### 9.3. Bilet Yaşam Döngüsü

- New → Triage → Confirmed True / False → Containment → Eradication → Recovery → Closed → Lessons Learned.
- Her bilet için MTTD, MTTR ölçülür.

## 10. Runbook'lar (Örnek Başlıklar)

Her runbook standart format: tetikleyici, hızlı tanı, konteyner, eradicate, recover, kanıt toplama, KVKK Komitesine bildirim eşiği.

- **RB-01 Yetkili Olmayan Kişisel Veri Erişim Şüphesi**
- **RB-02 Veri Exfiltration**
- **RB-03 Ransomware**
- **RB-04 Phishing — Kullanıcı Kimlik Bilgisi Verdi**
- **RB-05 Web Defacement**
- **RB-06 Yetki Yükseltme + Lateral Movement**
- **RB-07 Yedek Başarısız + Restore Test Başarısız**
- **RB-08 PAM Break-Glass Kullanımı**
- **RB-09 SaaS Hesap Ele Geçirme (BEC)**
- **RB-10 DDoS**
- **RB-11 Şüpheli SaaS DLP Olayı**
- **RB-12 Kayıp/Çalıntı Cihaz**

## 11. Kanıt ve Forensic

- Bir olay tespit edildiğinde "evidence preservation" devreye girer:
  - Etkilenen sistemin RAM dump'ı (mümkünse).
  - Disk imajı (dd, F-Response, EnCase).
  - Log snapshot — değiştirilemez kopya.
  - Network capture (PCAP) — ilgili pencere.
- Chain of custody belgesi imzalanır, kanıt saklama yeri kilitli/şifreli.
- Hukuki süreçte kullanılabilirlik için NIST IR 8444 / ISO 27037 referansı.

## 12. KVKK Komitesi Bildirim Eşiği

İhlal yönetimi (08) ile koordineli:

- **Kişisel veri ihlali şüphesi** tespit edildiği andan itibaren 24 saat içinde KVKK Komitesi bilgilendirilir.
- **Doğrulanmış ihlal** sonrası 72 saat içinde Kurul'a bildirim hazırlığı (KVKK m.12(5)).
- Müdahale ekibi içinde KVKK Sorumlusu, Hukuk, CISO sabit üye.

## 13. Threat Intelligence

- IOC feed (commercial + open — AlienVault OTX, MISP, abuse.ch, vendor).
- Sektörel paylaşım — CERT, sektör ISAC.
- Kurum içi IOC üretimi — kapatılan olaylardan IOC çıkar, aramaya enjekte et.
- TIP (Threat Intelligence Platform) ile SIEM/EDR/FW entegrasyonu.

## 14. SOAR Otomasyonu

- Yaygın senaryolarda playbook otomasyonu:
  - Phishing URL bildirimi → sandbox → IOC çıkar → block FW/Proxy/Email.
  - Şüpheli giriş → kullanıcı oturum kapat + parola force change + MFA reset talebi.
  - EDR detection → host isolate + ticket + analyst atama.
- Otomatik aksiyonlar onay zinciri ile (otomatik isolate olur, otomatik veri silme olmaz).

## 15. Test ve Doğrulama

- **Atomic Red Team / Caldera** ile MITRE ATT&CK tekniklerinin tespit edilebilirliği yıllık ölçülür (purple team).
- **Tabletop** egzersizleri çeyreklik (CISO + İK + Hukuk + KVKK + İletişim katılır).
- **Tetik testi** — her yeni alarm kuralı için pozitif test senaryosu.

## 16. KPI

- MTTD (Mean Time To Detect) — hedef ≤ 1 saat (kritik).
- MTTR (Mean Time To Respond) — hedef ≤ 4 saat (kritik).
- False positive oranı — ≤ %20.
- Kapsam: kritik varlıkların loglanma yüzdesi — %100.
- Log gecikmesi — ortalama ≤ 5 dk.
- Çözümlenmiş yüksek olay sayısı / toplam — aylık trend.
- Tatbikat tespit oranı — %85+.

## 17. Kontrol Listesi

- [ ] Tüm kritik kaynaklar SIEM'e log gönderiyor mu? (Kapsam ≥ %95)
- [ ] Log içeriği kişisel veri minimizasyonu uyguluyor mu (PII redaction)?
- [ ] Log bütünlüğü WORM + hash zinciri ile korunuyor mu?
- [ ] Saat senkronizasyonu (NTP) tüm sistemlerde mi?
- [ ] Log akışı kesilmesi alarmı 5 dk içinde tetikliyor mu?
- [ ] Saklama politikası KVKK + 5651 + sektörel mevzuata uyumlu mu?
- [ ] Saklama sonu otomatik imha çalışıyor mu?
- [ ] SOC 7/24 + eskalasyon zinciri belirli mi?
- [ ] Runbook'lar yıllık güncel + tatbikatla doğrulanmış mı?
- [ ] KVKK Sorumlusu IR ekibinde mi, 24 saat eşik yazılı mı?
- [ ] UEBA + threat intel SIEM'le entegre mi?
- [ ] Atomic Red Team / purple team yıllık yapıldı mı?
- [ ] Forensic kanıt zinciri (chain of custody) prosedürü hazır mı?
- [ ] PCI/sağlık/finans varsa sektörel saklama kuralı ek olarak uygulanıyor mu?
- [ ] Ayrıcalıklı log yöneticisi + sistem yöneticisi farklı kişiler mi?
- [ ] Kart numarası, OTP gibi yasaklı veri log'larda yok mu (regex tarama doğrulaması)?
