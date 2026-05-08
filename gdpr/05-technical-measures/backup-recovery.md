---
title:
  en: "Backup and Recovery - 3-2-1-1-0, Immutable, Ransomware Resilience, Erasure Flow"
  tr: "Yedekleme ve Geri Yükleme - 3-2-1-1-0, Değiştirilemez, Fidye Yazılımı Dayanıklılığı, Silme Akışı"
section: "05-technical-measures"
document_type: "control_policy"
control_id: "TECH-BK-01"
owner:
  primary: "CISO"
  secondary: "IT Operations / SRE"
review_cycle: "annual"
last_review: "2026-05-08"
next_review: "2027-05-08"
classification: "Internal"
language: ["en", "tr"]
references:
  - "GDPR Art. 5(1)(d), 5(1)(e), 17, 32(1)(b), 32(1)(c)"
  - "ISO/IEC 27002:2022 controls 8.13, 8.14, 8.16"
  - "ISO 22301:2019 Business continuity"
  - "NIST CSF 2.0 PR.DS-11, RC.RP-1..6"
  - "NIST SP 800-34 Rev.1 Contingency Planning"
  - "NIST SP 800-88 Rev.1 Media Sanitization"
---

## English

# Backup and Recovery

## 1. Purpose

Article 32(1)(c) requires "the ability to restore the availability and access
to personal data in a timely manner in the event of a physical or technical
incident." This document operationalises that ability through a backup
architecture, restore-test programme, ransomware resilience controls, and an
erasure-propagation procedure aligned with Article 17.

## 2. Recovery Objectives

The controller defines RTO (Recovery Time Objective) and RPO (Recovery Point
Objective) per system tier in the BCMS register:

| Tier | Examples | RTO | RPO |
|------|----------|-----|-----|
| Critical | Authentication, payments, customer-facing | 1 hour | 5 minutes |
| High | Core back-office, employee tools | 4 hours | 1 hour |
| Medium | Analytics, reporting | 24 hours | 24 hours |
| Low | Internal portals, archives | 72 hours | 7 days |

System owners attest that their tier classification is current at least
annually.

## 3. The 3-2-1-1-0 Rule

The controller applies the modern 3-2-1-1-0 rule, an extension of the
traditional 3-2-1 rule:

- **3** copies of data (1 production + 2 backups).
- **2** different media types (e.g., online disk and object storage / tape).
- **1** copy off-site (different region or jurisdiction-aligned to transfer
  rules in `07-international-transfers/`).
- **1** copy immutable / air-gapped (object lock, WORM, or offline).
- **0** restore errors verified - regular restore tests must succeed.

## 4. Backup Architecture

### 4.1 Production Replicas
- Synchronous or near-synchronous replication for Tier-Critical systems.
- Cross-AZ within the primary region.
- Read replicas for analytics never serve as authoritative backups.

### 4.2 Snapshots
- Application-consistent snapshots (with quiescing for transactional
  systems).
- Frequency aligned to RPO.

### 4.3 Archive Backups
- Immutable storage with object lock for the legally required retention.
- Encryption with KMS-managed keys (`encryption.md`).
- Cross-region replication respecting transfer rules; data subject to
  Schrems II / Article 46 considerations replicated only to permitted
  jurisdictions.

### 4.4 Endpoint Backups
- Workforce endpoints back up business documents to managed cloud storage
  governed by DLP (`dlp.md`).
- Endpoint disk images are not retained beyond device lifecycle wipe.

## 5. Immutability and Ransomware Resilience

Ransomware is now the most common availability threat. Controls:

- **Object Lock / WORM** on the archive tier with retention enforced at
  storage level; nobody, including administrators, can delete or modify
  during the lock window.
- **Separate identity domain** for backup administration; backup admins are
  not production admins.
- **Air-gapped tier** for the most critical data sets - either offline or in
  a tenant with one-way replication and no inbound network path.
- **Anomaly detection** on backup volumes - sudden compression ratio shifts,
  encryption signatures, mass-rename patterns alert immediately.
- **MFA at backup console** (AAL3, phishing-resistant).
- **Recovery in a clean room** - restore drills include the full flow of
  spinning up a clean network and rebuilding identity to ensure recovery is
  possible without using compromised infrastructure.
- **Tabletop**: full ransomware tabletop with restore exercise at least
  annually; results captured in CAPA.

## 6. Restore Testing

Article 32(1)(d) requires regular testing. The programme:

| Test Type | Frequency | Scope |
|-----------|-----------|-------|
| Random object restore | Weekly | Sampled per critical system |
| Full system restore | Quarterly | Rotation across critical tier |
| Cross-region failover | Twice per year | Critical tier production |
| Full DR exercise | Annually | All tiers down to Medium |
| Ransomware clean-room exercise | Annually | Critical tier from immutable |

Each test produces:

- Test plan and scope.
- Pre / post checks (data integrity, application health, dependencies).
- Time measurements vs RTO / RPO targets.
- Findings logged as CAPA.
- Sign-off by system owner and CISO delegate.

Failure to meet RTO / RPO triggers a remediation plan within 30 days.

## 7. Erasure Propagation (Article 17)

Article 17 erasure must propagate to backups within a reasonable timeframe.
Outright per-record deletion in immutable tiers is not feasible; the
controller therefore applies one of the following depending on system class:

### 7.1 Operational Backups (rolling)
- Records deleted in production cycle out of operational backups within the
  rotation window (typically 30 days for daily, 12 weeks for weekly).
- The data subject is informed in the erasure response that the record will
  no longer be present in any backup after a stated date.
- Backup access controls prevent re-introduction.

### 7.2 Archive / Immutable Backups
- Crypto-shredding (`encryption.md` Section 7) used where each subject or
  scope has a unique data encryption key.
- Where crypto-shredding is impractical, the controller documents:
  - The technical reason it is impractical.
  - The measures taken to ensure the data is not used.
  - The date by which the data will exit the archive (end of legal retention
    or end of object-lock window).
  - Suppression list at restore time so any restore re-honours the erasure.
- The data subject is informed of the procedure and timeline in the response.

### 7.3 Records and Verification
- Each erasure produces an entry in the immutable audit
  (`logging.md`).
- Verification at the next restore drill confirms suppression / shred is
  effective.

## 8. Encryption and Key Management

- All backup media encrypted at rest with AES-256-GCM or AES-256-XTS.
- Backup encryption keys distinct from production keys; loss of the
  production KMS does not entail loss of backup keys, and vice versa.
- Off-site copies use region-local KMS keys.
- Key rotation on backup encryption: at least annually for new backups.
- Restore drills validate the keys are available and rotation has not broken
  decryptability.

## 9. Media Sanitisation (Decommissioning)

Article 5(1)(f) and 32(1)(b) require that decommissioned media cannot leak
personal data. The controller follows NIST SP 800-88 Rev.1:

| Media | Method | Verification |
|-------|--------|--------------|
| Magnetic disk (HDD) | Clear (overwrite) for re-use; Purge (degauss) or Destroy (shred) for end-of-life | Random sample read-back |
| SSD / NVMe | Cryptographic erase via vendor tool, plus Destroy if Tier-Restricted | Vendor attestation |
| Cloud volumes | Crypto-erase via KMS key destruction | KMS audit log |
| Tape | Degauss + physical destruction at end-of-life | Witness + certificate |
| Paper | Shred to DIN 66399 P-4 minimum, P-5 for T4-T5 | Vendor certificate |

Disposal certificates retained for 7 years.

## 10. Vendor and Cloud Backup

Where a processor performs backup on the controller's behalf:

- Coverage in the DPA (`06-organizational-measures/vendor-management.md`).
- Encryption controls and key custody documented.
- Restore tests jointly performed at least annually.
- Sub-processor approvals refreshed.
- Data location and transfer assessment per `07-international-transfers/`.
- Exit clauses ensure the controller can recover its data and require
  certified destruction of vendor copies.

## 11. KPIs

| Metric | Target |
|--------|--------|
| Critical tier RTO compliance (drills) | 100 % |
| Critical tier RPO compliance (drills) | 100 % |
| Immutable copy coverage of critical tier | 100 % |
| Restore test failures open > 30 days | 0 |
| Erasure propagation acknowledgements signed | 100 % |
| Sanitisation certificates filed | 100 % |
| Backup encryption key audit findings | 0 |

## 12. Mapping

| Requirement | GDPR | ISO 27002:2022 | NIST CSF 2.0 |
|-------------|------|----------------|--------------|
| Information backup | Art. 32(1)(c) | 8.13 | PR.DS-11 |
| Redundancy of facilities | Art. 32(1)(c) | 8.14 | PR.IR-4 |
| Erasure propagation | Art. 17 | 5.34 | PR.DS-3 |
| Disposal | Art. 5(1)(f) | 7.14, 8.10 | PR.PS-3 |

---

## Türkçe

# Yedekleme ve Geri Yükleme

## 1. Amaç

Madde 32(1)(c), "fiziksel veya teknik bir olay durumunda kişisel verilere
erişimi ve kullanılabilirliği zamanında geri yükleme yeteneği" gerektirir.
Bu belge yeteneği bir yedekleme mimarisi, geri yükleme test programı, fidye
yazılımı dayanıklılık kontrolleri ve Madde 17 ile uyumlu silme yayılma
prosedürü ile operasyonelleştirir.

## 2. Geri Yükleme Hedefleri

Kontrolör, BCMS kayıt defterinde sistem katmanı başına RTO (Geri Yükleme
Süre Hedefi) ve RPO (Geri Yükleme Nokta Hedefi) tanımlar:

| Katman | Örnekler | RTO | RPO |
|--------|----------|-----|-----|
| Kritik | Kimlik doğrulama, ödemeler, müşteri-tarafı | 1 saat | 5 dakika |
| Yüksek | Çekirdek arka ofis, çalışan araçları | 4 saat | 1 saat |
| Orta | Analitik, raporlama | 24 saat | 24 saat |
| Düşük | Dahili portallar, arşivler | 72 saat | 7 gün |

Sistem sahipleri katman sınıflandırmasının güncel olduğunu en az yılda bir
beyan eder.

## 3. 3-2-1-1-0 Kuralı

Kontrolör, geleneksel 3-2-1 kuralının modern uzantısı olan 3-2-1-1-0 kuralını
uygular:

- **3** veri kopyası (1 üretim + 2 yedek).
- **2** farklı ortam türü (örn., çevrimiçi disk ve nesne depolama / teyp).
- **1** kopya saha dışı (`07-international-transfers/` aktarım kurallarına
  hizalı farklı bölge veya yetki alanı).
- **1** kopya değiştirilemez / hava boşluklu (nesne kilidi, WORM veya
  çevrimdışı).
- **0** doğrulanmış geri yükleme hatası - düzenli geri yükleme testleri
  başarılı olmalıdır.

## 4. Yedekleme Mimarisi

### 4.1 Üretim Replikaları
- Tier-Kritik sistemler için senkron veya yarı-senkron çoğaltma.
- Birincil bölge içinde AZ'ler arası.
- Analitik için okuma replikaları yetkili yedek olarak hizmet etmez.

### 4.2 Anlık Görüntüler
- Uygulama tutarlı anlık görüntüler (işlemsel sistemler için sessizleştirme
  ile).
- RPO'ya hizalı sıklık.

### 4.3 Arşiv Yedekleri
- Yasal olarak gerekli saklama için nesne kilidi olan değiştirilemez
  depolama.
- KMS yönetimli anahtarlarla şifreleme (`encryption.md`).
- Aktarım kurallarına saygılı bölgeler arası çoğaltma; Schrems II / Madde 46
  değerlendirmelerine tabi veriler yalnızca izin verilen yetki alanlarına
  çoğaltılır.

### 4.4 Uç Nokta Yedekleri
- İş gücü uç noktaları iş belgelerini DLP yönetimli yönetilen bulut
  depolamaya yedekler (`dlp.md`).
- Uç nokta disk görüntüleri cihaz yaşam döngüsü silmenin ötesinde
  saklanmaz.

## 5. Değiştirilemezlik ve Fidye Yazılımı Dayanıklılığı

Fidye yazılımı artık en yaygın kullanılabilirlik tehdidir. Kontroller:

- Saklama depolama düzeyinde uygulanan arşiv katmanında **Nesne Kilidi /
  WORM**; yöneticiler dahil hiç kimse kilit penceresi sırasında silemez veya
  değiştiremez.
- Yedekleme yönetimi için **ayrı kimlik etki alanı**; yedek yöneticileri
  üretim yöneticileri değildir.
- En kritik veri kümeleri için **hava boşluklu katman** - ya çevrimdışı ya
  da tek yönlü çoğaltma ve gelen ağ yolu olmayan bir kiracıda.
- Yedekleme birimlerinde **anomali tespiti** - ani sıkıştırma oranı
  değişimleri, şifreleme imzaları, toplu yeniden adlandırma örüntüleri hemen
  uyarır.
- **Yedekleme konsolunda MFA** (AAL3, phishing'e dayanıklı).
- **Temiz odada geri yükleme** - geri yükleme tatbikatları, kurtarmanın
  tehlikeye girmiş altyapı kullanılmadan mümkün olduğunu sağlamak için
  temiz bir ağ kurma ve kimliği yeniden oluşturma akışını içerir.
- **Masa başı**: yıllık olarak geri yükleme tatbikatlı tam fidye yazılımı
  masa başı; sonuçlar CAPA'da yakalanır.

## 6. Geri Yükleme Testi

Madde 32(1)(d) düzenli test gerektirir. Program:

| Test Türü | Sıklık | Kapsam |
|-----------|--------|--------|
| Rastgele nesne geri yükleme | Haftalık | Kritik sistem başına örneklenmiş |
| Tam sistem geri yükleme | Üç aylık | Kritik katman boyunca rotasyon |
| Bölgeler arası yedekleme geçişi | Yılda iki kez | Kritik katman üretim |
| Tam DR tatbikatı | Yıllık | Orta'ya kadar tüm katmanlar |
| Fidye yazılımı temiz oda tatbikatı | Yıllık | Değiştirilemezden Kritik katman |

Her test üretir:

- Test planı ve kapsamı.
- Ön / son kontroller (veri bütünlüğü, uygulama sağlığı, bağımlılıklar).
- RTO / RPO hedeflerine karşı zaman ölçümleri.
- CAPA olarak kaydedilen bulgular.
- Sistem sahibi ve CISO temsilcisi tarafından imza.

RTO / RPO karşılanmadığında 30 gün içinde iyileştirme planı tetiklenir.

## 7. Silme Yayılması (Madde 17)

Madde 17 silme makul bir zaman çerçevesinde yedeklere yayılmalıdır.
Değiştirilemez katmanlarda kayıt başına doğrudan silme uygulanabilir değildir;
kontrolör bu nedenle sistem sınıfına bağlı olarak şunlardan birini uygular:

### 7.1 Operasyonel Yedekler (yuvarlanan)
- Üretim döngüsünde silinen kayıtlar rotasyon penceresinde (genellikle
  günlük için 30 gün, haftalık için 12 hafta) operasyonel yedeklerden
  düşer.
- Veri sahibine, kaydın belirtilen tarihten sonra hiçbir yedekte
  bulunmayacağı silme yanıtında bildirilir.
- Yedek erişim kontrolleri yeniden tanıtımı engeller.

### 7.2 Arşiv / Değiştirilemez Yedekler
- Her özne veya kapsamın benzersiz bir veri şifreleme anahtarına sahip
  olduğu yerde kripto-yok etme (`encryption.md` Bölüm 7) kullanılır.
- Kripto-yok etmenin uygulanabilir olmadığı yerde kontrolör belgeler:
  - Pratik olmamasının teknik nedeni.
  - Verinin kullanılmaması için alınan önlemler.
  - Verinin arşivden çıkacağı tarih (yasal saklamanın sonu veya nesne kilidi
    penceresinin sonu).
  - Geri yükleme zamanında, herhangi bir geri yüklemenin silmeyi yeniden
    onurlandırması için bastırma listesi.
- Veri sahibine prosedür ve zaman çizelgesi yanıtta bildirilir.

### 7.3 Kayıtlar ve Doğrulama
- Her silme değiştirilemez denetimde bir kayıt üretir (`logging.md`).
- Sonraki geri yükleme tatbikatında doğrulama bastırma / yok etmenin etkili
  olduğunu teyit eder.

## 8. Şifreleme ve Anahtar Yönetimi

- Tüm yedek ortam atılımda AES-256-GCM veya AES-256-XTS ile şifrelenir.
- Yedekleme şifreleme anahtarları üretim anahtarlarından farklıdır; üretim
  KMS'sinin kaybı yedek anahtarlarının kaybını gerektirmez ve tersi.
- Saha dışı kopyalar bölgeye yerel KMS anahtarları kullanır.
- Yedek şifrelemede anahtar rotasyonu: yeni yedekler için en az yıllık.
- Geri yükleme tatbikatları anahtarların kullanılabilir olduğunu ve
  rotasyonun çözülebilirliği bozmadığını doğrular.

## 9. Ortam Temizliği (Hizmet Dışı Bırakma)

Madde 5(1)(f) ve 32(1)(b), hizmet dışı bırakılmış ortamların kişisel veriyi
sızdıramamasını gerektirir. Kontrolör NIST SP 800-88 Rev.1'i izler:

| Ortam | Yöntem | Doğrulama |
|-------|--------|-----------|
| Manyetik disk (HDD) | Yeniden kullanım için Temizle (üzerine yaz); ömür sonu için Tasfiye (mıknatıssızlaştır) veya Yok Et (parçala) | Rastgele örnek geri okuma |
| SSD / NVMe | Sağlayıcı aracı ile kriptografik silme, artı Tier-Kısıtlı ise Yok Et | Sağlayıcı beyanı |
| Bulut birimleri | KMS anahtarı imhası ile kripto-silme | KMS denetim logu |
| Teyp | Mıknatıssızlaştırma + ömür sonunda fiziksel imha | Tanık + sertifika |
| Kâğıt | Asgari DIN 66399 P-4'e parçala, T4-T5 için P-5 | Sağlayıcı sertifikası |

İmha sertifikaları 7 yıl saklanır.

## 10. Tedarikçi ve Bulut Yedeği

Bir işleyici kontrolör adına yedekleme yaptığında:

- DPA'da kapsam (`06-organizational-measures/vendor-management.md`).
- Belgelenmiş şifreleme kontrolleri ve anahtar koruma.
- Yıllık olarak ortak yapılan geri yükleme testleri.
- Yenilenmiş alt-işleyici onayları.
- `07-international-transfers/` uyarınca veri konumu ve aktarım
  değerlendirmesi.
- Çıkış maddeleri kontrolörün verilerini geri almasını sağlar ve sağlayıcı
  kopyalarının sertifikalı imhasını gerektirir.

## 11. KPI'lar

| Metrik | Hedef |
|--------|-------|
| Kritik katman RTO uyumu (tatbikatlar) | %100 |
| Kritik katman RPO uyumu (tatbikatlar) | %100 |
| Kritik katmanın değiştirilemez kopya kapsamı | %100 |
| 30 gün üzeri açık geri yükleme test başarısızlıkları | 0 |
| İmzalanmış silme yayılma onayları | %100 |
| Dosyalanmış temizlik sertifikaları | %100 |
| Yedek şifreleme anahtarı denetim bulguları | 0 |

## 12. Eşleme

| Gereklilik | GDPR | ISO 27002:2022 | NIST CSF 2.0 |
|------------|------|----------------|--------------|
| Bilgi yedekleme | Md. 32(1)(c) | 8.13 | PR.DS-11 |
| Tesislerin yedekliliği | Md. 32(1)(c) | 8.14 | PR.IR-4 |
| Silme yayılması | Md. 17 | 5.34 | PR.DS-3 |
| İmha | Md. 5(1)(f) | 7.14, 8.10 | PR.PS-3 |
