---
title:
  en: "Access Control - Least Privilege, RBAC/ABAC, JML, PAM, SoD"
  tr: "Erişim Kontrolü - Asgari Yetki, RBAC/ABAC, JML, PAM, GoA"
section: "05-technical-measures"
document_type: "control_policy"
control_id: "TECH-AC-01"
owner:
  primary: "CISO"
  secondary: "IT Operations / Identity Team"
review_cycle: "annual"
last_review: "2026-05-08"
next_review: "2027-05-08"
classification: "Internal"
language: ["en", "tr"]
references:
  - "GDPR Art. 5(1)(f), 5(2), 24, 25, 32(1)(b), 32(4)"
  - "ISO/IEC 27002:2022 controls 5.15, 5.16, 5.17, 5.18, 8.2, 8.3, 8.5"
  - "ISO/IEC 27001:2022 Annex A"
  - "NIST CSF 2.0 PR.AA-1..6"
  - "NIST SP 800-53 Rev.5 AC family"
  - "ENISA Handbook on Security of Personal Data Processing - Access Control"
---

## English

# Access Control

## 1. Purpose

Access control implements Article 5(1)(f) (integrity and confidentiality),
Article 32(1)(b) (ongoing confidentiality) and Article 32(4) (processing only
on documented instructions). This document establishes the lifecycle, models
and controls for granting, modifying, reviewing and revoking access to systems
and data within the controller's environment.

## 2. Guiding Principles

1. **Least privilege** - every identity holds only the access strictly needed
   for its current function.
2. **Need-to-know** - data access is scoped to data sets necessary for the
   role's purpose. ROPA-declared purposes determine permissible access.
3. **Default deny** - the absence of an explicit grant means no access.
4. **Separation of duties** - no single identity can both initiate and approve
   high-impact transactions or both administer and audit a system.
5. **Joiner-Mover-Leaver (JML) lifecycle** - HR is the system of record;
   identity provisioning is event-driven and timestamped.
6. **Auditability** - every grant, change and revocation produces an immutable
   log entry under `logging.md`.

## 3. Identity Lifecycle (JML)

### 3.1 Joiner

- Trigger: HR record creation (signed contract).
- SLA: identity provisioned within 1 business day before the start date.
- Default role: zero-privilege baseline (corporate email, SSO, MFA enrolment).
- Functional roles: assigned on day one through automated role catalogue.
- Confidentiality undertaking signed on day one
  (`06-organizational-measures/confidentiality-undertaking.md`).
- Mandatory training assigned in LMS
  (`06-organizational-measures/training.md`).

### 3.2 Mover

- Trigger: HR transfer event or manager request.
- SLA: prior role removed within 5 business days; new role granted same day.
- Recertification: line manager confirms removal of legacy entitlements via
  ticket; identity team verifies no orphan entitlements remain.

### 3.3 Leaver

- Trigger: HR termination event.
- SLA:
  - Voluntary leaver - all logical access disabled at end of last working day.
  - Involuntary leaver - access disabled within 1 hour of HR notification.
- Email and document scope frozen for legal hold review (90 days minimum).
- Hardware returned and wiped per `backup-recovery.md` and NIST SP 800-88
  Rev.1.
- Post-exit obligations confirmed in writing (NDA, IP assignment).

## 4. Authorisation Models

### 4.1 RBAC (Role-Based Access Control)

- Primary model for stable, function-based access.
- Roles are catalogued in the IAM directory with:
  - Role ID, owner, business purpose.
  - Entitlement bundle (system + permission set).
  - Toxic-combination flag (SoD conflicts).
  - Recertification frequency.
- Maximum 8 roles per identity except for general-purpose collaboration tools.
- Role engineering reviewed annually; orphan and unused roles purged.

### 4.2 ABAC (Attribute-Based Access Control)

- Used where access depends on context (data tag, location, device posture,
  time, project).
- Policy expressed in standard policy language (XACML, OPA Rego or equivalent)
  with versioning in source control.
- Required attributes:
  - Subject - role, clearance, employment status.
  - Resource - classification, data subject category, jurisdiction.
  - Action - read, write, delete, export.
  - Environment - device managed/unmanaged, network zone, time window.
- Policy evaluated by central PDP; PEP enforces in application or proxy.

### 4.3 Privileged Access Management (PAM)

Privileged accounts (administrators, service accounts with elevated rights,
break-glass identities) are managed under a dedicated PAM solution:

- **Vaulted credentials** - no static admin passwords on endpoints; secrets
  injected at session start.
- **Session brokering** - all admin sessions proxied with full keystroke and
  screen recording for audit.
- **Just-in-time elevation** - default role is non-privileged; elevation is
  ticket-bound, time-bound (max 4 hours), and approver-bound (M-1).
- **Credential rotation** - automatic on session end and at minimum every 24
  hours for shared credentials.
- **Break-glass accounts** - sealed, hardware-stored, dual-control, monitored
  for any use, post-use review within 24 hours.

## 5. Segregation of Duties (SoD)

Toxic combinations are catalogued and prevented at provisioning. Indicative
matrix:

| Conflicting Roles | Mitigation |
|-------------------|------------|
| Developer + Production deploy | CI/CD with mandatory peer review |
| Database admin + Audit log admin | Audit logs streamed to separate tenant |
| Vendor onboarding + Vendor approval | Two distinct owners |
| Payroll edit + Payroll approval | Maker-checker workflow |
| User provisioning + User access review | Reviewer cannot self-approve |

The PAM and IAM platforms enforce these rules; manual exceptions require a
documented compensating control approved by the CISO with quarterly re-review.

## 6. Access Review (Recertification)

| Population | Frequency | Reviewer | Evidence |
|-----------|-----------|----------|----------|
| Privileged human users | Quarterly | System owner + CISO delegate | Signed report in audit repository |
| Service accounts | Quarterly | Application owner | Recert ticket |
| Standard human users | Annually | Line manager | Manager attestation |
| Third-party / processor users | Quarterly | Vendor manager + system owner | Recert ticket + DPA reference |
| Shared mailboxes / inboxes | Semi-annually | Information owner | Inventory + sign-off |

Outcomes:

- Approve - no change.
- Modify - reduce / change entitlements.
- Revoke - remove entirely.

A tracked CAPA is opened for any reviewer non-response within 5 business days
of the recertification window closing. Non-response after 10 business days
triggers automatic revocation.

## 7. Service and Machine Identities

- Service accounts are owned by an application, not an individual.
- Each service account has a registered owner and a published purpose.
- Where supported, workload identities (federated tokens, mTLS, SPIFFE) are
  used in preference to long-lived static credentials.
- Static secrets are stored in the secrets manager
  (`application-security.md` Section on secrets management) and referenced by
  identity, never embedded in source.
- Rotation - automatic, maximum 90 days for application secrets, 24 hours for
  shared admin credentials.

## 8. Remote Access

- All remote administrative access via the PAM session broker over the ZTNA
  channel (`network-security.md`).
- MFA mandatory and phishing-resistant for administrators
  (`authentication.md`).
- Device posture verified - managed device, disk encryption on, EDR healthy,
  OS patched.
- Split tunnelling prohibited for sessions accessing production data.

## 9. Physical Access

Physical access to facilities and data centres applies the same principles:

- Badge-based access with role-bound zones.
- Multi-factor for restricted zones (badge + PIN or badge + biometric).
- Visitor logbook retained for 1 year.
- CCTV per `dlp.md` retention rules.
- Data centre racks under dual-control where feasible.

## 10. KPIs and Metrics

| Metric | Target |
|--------|--------|
| Mean time to disable leaver access | <= 1 hour after HR notification |
| Privileged accounts with PAM brokering | 100 % |
| Recertification completion rate | >= 98 % within window |
| Toxic-combination violations open | 0 |
| Service accounts without owner | 0 |
| Static admin passwords on endpoints | 0 |

## 11. Mapping

| Requirement | ISO 27002:2022 | NIST CSF 2.0 |
|-------------|----------------|--------------|
| Identity management | 5.16 | PR.AA-1 |
| Authentication | 8.5 | PR.AA-2 |
| Authorisation | 5.15 | PR.AA-3 |
| Privileged access | 8.2 | PR.AA-5 |
| Access rights review | 5.18 | PR.AA-6 |
| Information access | 8.3 | PR.DS-1 |

## 12. Related Documents

- `authentication.md` - credential and MFA requirements.
- `logging.md` - audit event capture for grants, sessions, recertification.
- `06-organizational-measures/confidentiality-undertaking.md`.
- `06-organizational-measures/training.md`.

---

## Türkçe

# Erişim Kontrolü

## 1. Amaç

Erişim kontrolü; Madde 5(1)(f) (bütünlük ve gizlilik), Madde 32(1)(b)
(sürekli gizlilik) ve Madde 32(4) (yalnızca belgelenmiş talimatlarla işleme)
gerekliliklerini uygular. Bu belge, sistemlere ve verilere erişim
verilmesi, değiştirilmesi, gözden geçirilmesi ve geri alınmasına ilişkin yaşam
döngüsünü, modelleri ve kontrolleri belirler.

## 2. Yol Gösterici İlkeler

1. **Asgari yetki** - her kimlik yalnızca mevcut işlevi için gerçekten gerekli
   erişimi taşır.
2. **Bilmesi gereken** - veri erişimi rolün amacı için gereken veri kümeleriyle
   sınırlandırılır. ROPA'da beyan edilen amaçlar izin verilen erişimi belirler.
3. **Varsayılan reddet** - açık bir yetki yoksa erişim yoktur.
4. **Görev ayrımı** - tek bir kimlik yüksek etkili işlemleri hem başlatamaz hem
   de onaylayamaz; bir sistemi hem yönetip hem denetleyemez.
5. **Joiner-Mover-Leaver (JML) yaşam döngüsü** - İK kayıt sahibidir; kimlik
   sağlama olay tetiklemeli ve zaman damgalıdır.
6. **Denetlenebilirlik** - her yetkilendirme, değişiklik ve iptal `logging.md`
   altında değiştirilemez bir log kaydı üretir.

## 3. Kimlik Yaşam Döngüsü (JML)

### 3.1 Joiner (İşe Başlayan)

- Tetikleyici: İK kaydı oluşturma (imzalı sözleşme).
- SLA: kimlik, başlangıç tarihinden önce 1 iş günü içinde sağlanır.
- Varsayılan rol: sıfır ayrıcalık temel düzey (kurumsal e-posta, SSO, MFA
  kaydı).
- İşlevsel roller: ilk gün otomatik rol kataloğu üzerinden atanır.
- Gizlilik taahhütnamesi ilk gün imzalanır
  (`06-organizational-measures/confidentiality-undertaking.md`).
- Zorunlu eğitim LMS'te atanır
  (`06-organizational-measures/training.md`).

### 3.2 Mover (Görev Değişikliği)

- Tetikleyici: İK transfer olayı veya yönetici talebi.
- SLA: önceki rol 5 iş günü içinde kaldırılır; yeni rol aynı gün verilir.
- Resertifikasyon: hat yöneticisi eski yetkilerin kaldırıldığını talep
  üzerinden teyit eder; kimlik ekibi yetim yetki kalmadığını doğrular.

### 3.3 Leaver (Ayrılan)

- Tetikleyici: İK iş çıkış olayı.
- SLA:
  - Gönüllü ayrılma - tüm mantıksal erişim son iş gününün sonunda devre dışı.
  - İstem dışı ayrılma - İK bildiriminden itibaren 1 saat içinde erişim kapalı.
- E-posta ve doküman alanı yasal hold incelemesi için dondurulur (asgari 90
  gün).
- Donanım iade alınır ve `backup-recovery.md` ve NIST SP 800-88 Rev.1 uyarınca
  silinir.
- Çıkış sonrası yükümlülükler yazılı olarak teyit edilir (NDA, FSM devri).

## 4. Yetkilendirme Modelleri

### 4.1 RBAC (Rol Tabanlı)

- Stabil, işleve dayalı erişim için birincil model.
- Roller IAM dizininde kataloglanır:
  - Rol kimliği, sahip, iş amacı.
  - Yetki paketi (sistem + izin seti).
  - Toksik kombinasyon işareti (GoA çakışmaları).
  - Resertifikasyon sıklığı.
- Genel amaçlı işbirliği araçları hariç kimlik başına azami 8 rol.
- Rol mühendisliği yıllık gözden geçirilir; yetim ve kullanılmayan roller
  kaldırılır.

### 4.2 ABAC (Öznitelik Tabanlı)

- Erişimin bağlama (veri etiketi, konum, cihaz duruşu, zaman, proje) bağlı
  olduğu durumlarda kullanılır.
- Politika standart politika dilinde (XACML, OPA Rego veya eşdeğeri) ifade
  edilir; sürüm kontrolünde tutulur.
- Gerekli öznitelikler:
  - Özne - rol, yetki seviyesi, çalışma durumu.
  - Kaynak - sınıflandırma, veri sahibi kategorisi, yetki alanı.
  - Eylem - okuma, yazma, silme, dışa aktarma.
  - Çevre - cihaz yönetilen/yönetilmeyen, ağ bölgesi, zaman penceresi.
- Politika merkezi PDP tarafından değerlendirilir; PEP uygulamada veya proxy'de
  uygulamayı zorlar.

### 4.3 Ayrıcalıklı Erişim Yönetimi (PAM)

Ayrıcalıklı hesaplar (yöneticiler, yükseltilmiş haklara sahip servis hesapları,
acil durum kimlikleri) özel bir PAM çözümü altında yönetilir:

- **Kasalanmış kimlik bilgileri** - uç noktalarda statik yönetici parolası
  yoktur; sırlar oturum başlangıcında enjekte edilir.
- **Oturum aracılığı** - tüm yönetici oturumları, denetim için tam tuş ve ekran
  kaydı ile aracılı geçer.
- **Just-in-time yükseltme** - varsayılan rol ayrıcalıksızdır; yükseltme bilete
  bağlı, süreye bağlı (azami 4 saat) ve onayçıya bağlı (M-1).
- **Kimlik bilgisi rotasyonu** - oturum sonunda ve paylaşılan kimlik bilgileri
  için en az 24 saatte bir otomatik.
- **Acil durum hesapları** - mühürlü, donanımda saklanır, çift kontrol,
  herhangi bir kullanım izlenir, kullanım sonrası inceleme 24 saat içinde.

## 5. Görev Ayrımı (GoA)

Toksik kombinasyonlar kataloglanır ve sağlama anında engellenir. Gösterge
matrisi:

| Çakışan Roller | Hafifletme |
|----------------|------------|
| Geliştirici + Üretim dağıtımı | Zorunlu peer review'lı CI/CD |
| Veritabanı yöneticisi + Denetim log yöneticisi | Denetim logları ayrı kiracıya akar |
| Tedarikçi onboarding + Tedarikçi onayı | İki farklı sahip |
| Bordro düzenleme + Bordro onayı | Maker-checker iş akışı |
| Kullanıcı sağlama + Kullanıcı erişim incelemesi | İnceleyen kendini onaylayamaz |

PAM ve IAM platformları bu kuralları uygular; manuel istisnalar CISO onayıyla
belgelenmiş telafi edici kontrol gerektirir ve üç ayda bir yeniden incelenir.

## 6. Erişim İncelemesi (Resertifikasyon)

| Popülasyon | Sıklık | İnceleyen | Kanıt |
|------------|--------|-----------|-------|
| Ayrıcalıklı insan kullanıcıları | Üç aylık | Sistem sahibi + CISO temsilcisi | Denetim deposunda imzalı rapor |
| Servis hesapları | Üç aylık | Uygulama sahibi | Resert bileti |
| Standart insan kullanıcıları | Yıllık | Hat yöneticisi | Yönetici beyanı |
| Üçüncü taraf / işleyici kullanıcılar | Üç aylık | Tedarikçi yöneticisi + sistem sahibi | Resert bileti + DPA referansı |
| Paylaşılan posta kutuları / gelen kutuları | Altı aylık | Bilgi sahibi | Envanter + onay |

Sonuçlar:

- Onayla - değişiklik yok.
- Değiştir - yetkileri azalt / değiştir.
- İptal et - tamamen kaldır.

Resertifikasyon penceresi kapandıktan sonra 5 iş günü içinde yanıt vermeyen
inceleyici için izlenen bir CAPA açılır. 10 iş günü sonrası yanıtsızlık
otomatik iptali tetikler.

## 7. Servis ve Makine Kimlikleri

- Servis hesapları bireye değil, uygulamaya aittir.
- Her servis hesabının kayıtlı bir sahibi ve yayımlanmış bir amacı vardır.
- Desteklendiği yerlerde, uzun ömürlü statik kimlik bilgileri yerine iş yükü
  kimlikleri (federe token, mTLS, SPIFFE) tercih edilir.
- Statik sırlar sır yöneticisinde saklanır
  (`application-security.md` sır yönetimi bölümü) ve kimlikle başvurulur,
  asla kaynağa gömülmez.
- Rotasyon - otomatik, uygulama sırları için azami 90 gün, paylaşılan yönetici
  kimlik bilgileri için 24 saat.

## 8. Uzaktan Erişim

- Tüm uzaktan yönetimsel erişim ZTNA kanalı üzerinden PAM oturum aracısı ile
  (`network-security.md`).
- Yöneticiler için phishing'e dayanıklı ve zorunlu MFA
  (`authentication.md`).
- Cihaz duruşu doğrulanır - yönetilen cihaz, disk şifreleme açık, EDR sağlıklı,
  OS yamalı.
- Üretim verisine erişen oturumlarda split tünelleme yasaktır.

## 9. Fiziksel Erişim

Tesislere ve veri merkezlerine fiziksel erişim aynı ilkeleri uygular:

- Role bağlı bölgelerle kart tabanlı erişim.
- Kısıtlı bölgeler için çok faktörlü (kart + PIN veya kart + biyometri).
- Ziyaretçi defteri 1 yıl saklanır.
- CCTV `dlp.md` saklama kurallarına göre.
- Veri merkezi rafları mümkünse çift kontrolde.

## 10. KPI ve Metrikler

| Metrik | Hedef |
|--------|-------|
| Ayrılan erişimini devre dışı bırakma süresi | İK bildiriminden sonra <= 1 saat |
| PAM aracılı ayrıcalıklı hesaplar | %100 |
| Resertifikasyon tamamlanma oranı | Pencere içinde >= %98 |
| Açık toksik kombinasyon ihlalleri | 0 |
| Sahibi olmayan servis hesapları | 0 |
| Uç noktada statik yönetici parolası | 0 |

## 11. Eşleme

| Gereklilik | ISO 27002:2022 | NIST CSF 2.0 |
|------------|----------------|--------------|
| Kimlik yönetimi | 5.16 | PR.AA-1 |
| Kimlik doğrulama | 8.5 | PR.AA-2 |
| Yetkilendirme | 5.15 | PR.AA-3 |
| Ayrıcalıklı erişim | 8.2 | PR.AA-5 |
| Erişim hakkı incelemesi | 5.18 | PR.AA-6 |
| Bilgiye erişim | 8.3 | PR.DS-1 |

## 12. İlgili Belgeler

- `authentication.md` - kimlik bilgisi ve MFA gereksinimleri.
- `logging.md` - yetkilendirme, oturum, resertifikasyon için denetim olayı
  yakalama.
- `06-organizational-measures/confidentiality-undertaking.md`.
- `06-organizational-measures/training.md`.
