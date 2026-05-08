---
Doküman / Document: Yedekleme, Kurtarma ve İş Sürekliliği Standardı / Backup, Recovery and Business Continuity Standard
Bölüm / Section: 05-teknik-tedbirler
Sahip / Owner: BT Operasyon Müdürü / CISO (yedek bütünlüğü) / IT Operations Manager / CISO (backup integrity)
Onaylayan / Approved by: BT Direktörü + KVKK Komitesi / IT Director + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş (büyük mimari değişiklik, ihlal, başarısız restore tatbikatı) / Annual + triggered (major architectural change, breach, failed restore drill)
İlgili Mevzuat / Legal Reference: Law No. 6698 KVKK Art. 12; Personal Data Security Guide — "Backup of Personal Data"
İlgili Standart / Standard: ISO/IEC 27001:2022 A.8.13 (Information Backup), A.5.30 (ICT Readiness for Business Continuity), A.8.14 (Redundancy of Information Processing Facilities); ISO 22301 (Business Continuity); NIST CSF 2.0 PR.DS-11, RC.RP; NIST SP 800-34 (Contingency Planning); CIS Controls v8 #11; ENISA Backup & Restore Guidelines
---

## English

# Backup, Recovery and Business Continuity

## 1. Purpose

To ensure that personal data and other critical information can be restored timely and completely against **loss, corruption, ransomware, natural disaster, human error**. The existence of a backup alone is not enough; **integrity, confidentiality, and recoverability** are guaranteed together.

## 2. Design Principles

1. **Personal Data Backup = Personal Data:** Backup is also within the KVKK scope. Subject to the same encryption, access, retention, and destruction rules.
2. **3-2-1-1-0 Rule:**
   - **3** copies (1 production + 2 backup),
   - **2** different media/technology,
   - **1** offsite,
   - **1** offline / immutable / air-gapped,
   - **0** unverified restore (every drill must be completed with verification).
3. **Encryption Mandatory:** Backup uses **separate key chain** from the production system.
4. **An Untested Backup is Not a Backup:** Quarterly restore test mandatory.
5. **Ransomware Resistant:** At least one copy is unaffected by compromise of the production system (immutable / air-gapped / offline).
6. **Aligned with Retention Policy:** Backup retention period = production data retention period + reasonable recovery window.
7. **Compatible with Crypto-Shred:** Data subject deletion request is processed from backups too (may be delayed by policy; duration documented).

## 3. Backup Strategy

### 3.1. Data Classification + RTO/RPO Table

| Class / System | RPO (loss tolerance) | RTO (recovery time) | Backup Frequency | Retention |
|----------------|------------------------|------------------------|----------------|---------|
| Tier 0 — Card, health, critical customer DB | 15 minutes | 1 hour | Continuous (CDC) + hourly | 35 days hot, 1 year warm, 7 years cold |
| Tier 1 — Customer application DB | 1 hour | 4 hours | Hourly | 35 days, 1 year, 5 years |
| Tier 2 — HR, finance, ERP | 4 hours | 8 hours | Every 4 hours | 30 days, 1 year, 7 years |
| Tier 3 — Content, file sharing | 24 hours | 24 hours | Daily | 30 days, 90 days |
| Tier 4 — Internal wiki, intranet | 7 days | 72 hours | Weekly | 90 days |

> RPO/RTO targets are determined by **business impact analysis (BIA)**. Senior management approval required.

### 3.2. Backup Types

- **Full:** Weekly.
- **Incremental:** Daily.
- **Differential:** Daily in some scenarios (instead of incremental).
- **Snapshot:** Hourly (application-consistent; VSS / fsfreeze / DB-quiesce).
- **CDC / Log-shipping:** Continuous (DB transaction log).
- **Replication:** Synchronous / asynchronous (to DR site).

> Replication **is not a backup** — deleted/corrupted data goes to the second copy synchronously. Replication + backup used together.

### 3.3. Placement

```
Production Site (Primary)
   ├── Local snapshot (hourly) ── fastest recovery in ransomware
   ├── Local backup repo (strict IAM, MFA, immutability)
   ├── Replication → DR Site (asynchronous)
   └── Offsite cloud backup (immutable bucket, separate tenant)
                                         ↓
                                   Air-gap / Tape vault (offline)
```

### 3.4. Air-Gap & Immutability

- **S3 Object Lock (Compliance Mode)** / Azure Immutable Blob / GCP Bucket Lock: no one (including root) can delete during the specified retention period.
- **Tape/LTO** (LTO-9 + WORM cartridge) — annual vault.
- **Backup vendor "hardened repository"** (Veeam Hardened Linux Repo, Rubrik Air Gap, Cohesity SecureView).
- **Separate IAM tenant / account** — production environment credentials cannot access backup infrastructure.
- **2FA + 4-eyes** delete approval (required even for operationally mandatory deletion).

## 4. Encryption and Key Management

- Backup encrypted **during ingest**; TLS in transit.
- Key on **KMS/HSM**, under **different KEK** from production DEK.
- Backup key accessed with credentials separate from the production system; storage and audit separate.
- Lost key = lost data; therefore, backup of the **key** is also kept separate (HSM cluster + offline paper M-of-N share vault).

## 5. Integrity Verification

- Checksum (SHA-256) + manifest at every backup generation.
- Periodic (weekly) checksum verification.
- Scrub for bit-rot detection (object storage, ZFS scrub, tape verify).
- Backup metadata also stored on a separate system.

## 6. Restore Test Program

### 6.1. Test Frequencies

| Test | Frequency | Who |
|------|--------|-----|
| Single file restore (random) | Monthly | IT Operations |
| DB point-in-time restore | Quarterly | DBA |
| Full server / VM restore | Quarterly | IT Operations |
| Application-integrated restore | Quarterly | Application Team + DBA |
| DR site cutover drill (planned) | Annual | BCP Committee |
| DR site cutover + business continuity | Annual | Business Units + IT |
| Ransomware recovery drill | Annual | CISO + SOC + IT |
| Air-gap / tape restore | Annual | IT Operations |

### 6.2. Test Evidence

- Pre-test: scope, target RTO/RPO, team, success criteria.
- During test: timestamped log, screenshots, measurements.
- Post-test: report (success/failure, measurement vs target, finding, action).
- Failures **open CAPA**; closed within 30 days or justified.

### 6.3. Validation Criteria

- Data completeness (row count, hash, sample comparison).
- Data consistency (foreign keys, application-level reference).
- Authentication / authorization works.
- RTO measurement — against target.
- Post-restore application smoke test.

## 7. DR (Disaster Recovery) Architecture

### 7.1. DR Strategy Types

| Strategy | Cost | Recovery Time |
|----------|---------|------------------|
| Backup & Restore | Low | Hours-days |
| Pilot Light (DR site minimum) | Medium | Hours |
| Warm Standby (reduced capacity ready) | High | Minutes-hours |
| Active-Active (concurrently running) | Very high | Near zero |

For Tier 0/1 systems, at least **Warm Standby**; Pilot Light may suffice for Tier 2-3.

### 7.2. DR Site Location

- **Cannot** be in the same natural disaster zone as the primary site (earthquake fault line, flood basin, same power grid).
- Domestic preference (KVKK transfer regime evaluated for offshore DR — see [07-aktarim](../07-aktarim/)).
- Cloud DR: separate region and ideally separate cloud provider (multi-cloud) may be preferred.

### 7.3. RTO/RPO Validation

- Annual DR drill with planned cutover measures.
- Expected RTO/RPO deviations analyzed.
- Annual BCP report submitted to Board of Directors.

## 8. Ransomware Resilience

### 8.1. Design Measures

- **Immutable + air-gap copy** (mandatory).
- **Backup infrastructure on separate IAM domain** — backup access not impacted if production AD is compromised.
- **Backup operator account MFA + PAM**.
- **Backup stop alarm** — backup job failure alarm within 24 hours.
- **Suspicious delete/encrypt flow detection** — anomalous file rename volume detected by EDR.
- **Backup inventory read-only copy** — attacker may try to delete the inventory.

### 8.2. Annual Drill Scenarios

- Entire production environment assumed encrypted → restore from DR site + air-gap copy.
- Production AD compromised → backup infrastructure verified unaffected.
- Attacker assumed to have deleted backups → does the immutable copy meet the target?

## 9. Backup Access Control

- Backup operator = small team (3-5 persons).
- 4-eyes restore: production restore requires approval of two persons.
- Logged via PAM session.
- Backup inventory, restore log to SIEM.
- Periodic review (quarterly).

## 10. Interaction with KVKK Destruction Requests

### 10.1. Issue

When a data subject requests deletion under KVKK Art. 7 / Art. 11, even if deleted from production system, **may remain in backups**. KVKK Committee position: if deleting backups is **operationally disproportionate**, the following approach is accepted under **documented policy**:

### 10.2. Backup-Transitional Destruction Policy

1. The record is **immediately** deleted/anonymized in production.
2. The old record reflected in backup is automatically destroyed at **end of backup retention period**.
3. Restore from this backup record is an **exception**. If a restore from backup is performed, the restore procedure **automatically triggers** re-deletion of deleted records (a deletion list is kept).
4. Data subject information notice / privacy notice explains this aspect.
5. When the crypto-shred method applies (backup key per class), key destruction may shorten this period.

### 10.3. Documentation

- Deletion request → deletion record → record in anonymized list in backup queue → backup destruction record.
- Chain demonstrable in audit investigation.

## 11. End of Backup Retention Period

- End of retention period automatically triggers destruction policy.
- Tape: degausser or physical shredding, record.
- Disk: secure erase (NIST SP 800-88) + crypto-shred.
- Cloud immutable: retention period self-cancels; deletion after period.

## 12. Vendor Backup

- The SaaS provider's backup policy **must meet ours**.
- Clauses added to the contract: RPO/RTO, backup encryption, recoverability, exit strategy (delivery of data).
- SaaS data is regularly backed up to **our side** (e.g., 3rd party backup for Microsoft 365, Salesforce, Workday).
- See [06-idari-tedbirler/tedarikci-yonetimi.md](../06-idari-tedbirler/tedarikci-yonetimi.md).

## 13. Logging

- Backup success/failure (job, target, duration, size).
- Restore initiation (who, why, scope).
- Backup deletion (manual/automatic).
- Key access.
- Policy change.

All backup events to SIEM (see [log-yonetimi.md](log-yonetimi.md)).

## 14. Checklist

- [ ] Is there CDC or hourly snapshot for all Tier 0/1 systems?
- [ ] Is the 3-2-1-1-0 rule applied? (Air-gap/immutable copy validated)
- [ ] Is backup encryption + separate KEK applied?
- [ ] Is the backup key protected with M-of-N + offline vault?
- [ ] Is backup infrastructure managed via separate IAM domain + MFA/PAM?
- [ ] Is quarterly restore drill performed, evidence archived?
- [ ] Was annual DR site cutover drill performed?
- [ ] Was annual ransomware recovery drill performed?
- [ ] Tape/LTO with immutable cartridge, vault control?
- [ ] Are RTO/RPO determined per BIA and approved by management?
- [ ] Is DR site in a different region / geography?
- [ ] Is there 3rd party backup for SaaS data?
- [ ] Is the process for KVKK deletion request reflection on backup documented?
- [ ] Is backup integrity verified by periodic scrub?
- [ ] Does the backup failure alarm trigger ≤ 24 hours?
- [ ] Is backup operator access 4-eyes and PAM logged?
- [ ] Is backup deletion authority limited, end-of-retention automatic?

## 15. KPI

- Backup success rate: ≥ 99%.
- Restore drill success rate: ≥ 99%.
- Average restore time vs. RTO: 95%+ target hit.
- Air-gap copy freshness: ≤ 24 hours.
- Backup operator action PAM record rate: 100%.

## 16. Breach / Recovery Response Flow

```
Trigger (data loss / corruption / ransomware) →
   1) Isolate (affected system)
   2) Check backup inventory — from which date to revert?
   3) Historical impact: how much data loss (RPO)
   4) Choose restore target (immutable copy preferred)
   5) Restore to test environment first, validate
   6) Restore to production
   7) Smoke test + business unit approval
   8) Lessons learned + post-incident report
```

KVKK Committee informed; if personal data was affected, the 08-ihlal-yonetimi procedure is triggered.

---

## Türkçe

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
