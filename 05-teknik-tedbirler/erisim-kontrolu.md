---
Doküman / Document: Erişim Kontrolü Politikası ve Prosedürü / Access Control Policy and Procedure
Bölüm / Section: 05-teknik-tedbirler
Sahip / Owner: Bilgi Güvenliği Yöneticisi (CISO) / Information Security Manager (CISO)
Onaylayan / Approved by: BT Direktörü + KVKK Komitesi / IT Director + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş / Annual + triggered
İlgili Mevzuat / Legal Reference: Law No. 6698 KVKK Art. 12; Personal Data Security Guide — "User Account Management and Authority Matrix"
İlgili Standart / Standard: ISO/IEC 27001:2022 A.5.15 (Access Control), A.5.16 (Identity Management), A.5.17 (Authentication Information), A.5.18 (Access Rights), A.8.2 (Privileged Access Rights), A.8.3 (Information Access Restriction), A.8.5 (Secure Authentication); NIST CSF 2.0 PR.AA-1..PR.AA-6; NIST SP 800-53 AC-2, AC-3, AC-5, AC-6; CIS Controls v8 #5, #6
---

## English

# Access Control

## 1. Purpose

To ensure that access to personal data is limited to authorized persons, only within the scope they are authorized for, and only for the time they are authorized. This document is the operational arm of the obligation under KVKK Art. 12(1) to "prevent unlawful access."

## 2. Core Principles

### 2.1. Least Privilege

Every user, service account and application is run with the **minimum privileges** required to perform its task. Privileges are determined by answering "should it?" rather than "could it?". Elevated privileges are granted on request, with justification, for a fixed time.

### 2.2. Need-to-Know

Access rights are limited to personal data **actually needed** to perform tasks within the user's job description. "Being authorized" is different from "accessing"; rather than bulk authorization, restrictions at the dataset/record level are preferred.

### 2.3. Segregation of Duties (SoD)

For sensitive operations, controls are established such that no single person can complete the end-to-end process. Examples:

- An application developer cannot write directly to the production database.
- The person who prepares payroll cannot approve it.
- The person opening an access request cannot approve their own request.
- The DB administrator cannot have authority to delete audit logs (logs are kept on a different system, with a different authority).

### 2.4. Default Deny

The result of all access requests not explicitly permitted is set to **deny** (firewall, ACL, IAM policy, RLS).

### 2.5. Periodic Re-Validation

Each granted permission is **not considered permanent**. It is re-validated through quarterly (critical) and annual (general) reviews.

## 3. Access Control Models

### 3.1. RBAC (Role-Based Access Control)

This is the standard model. Permissions are assigned to **roles**, users are assigned to roles. Granting authority directly to users is prohibited (except in break-glass emergencies).

**Role matrix example (personal data perspective):**

| Role | Customer Data | Employee Personnel | Health Data | Financial Data | Log/Audit |
|-----|---------------|---------------|---------------|-----------|-----------|
| Call Center Representative | Read (own assigned customer) | – | – | – | – |
| Call Center Manager | Read (team), masked | – | – | – | Read (team) |
| HR Specialist | – | Read/Write (own personnel group) | – | – | – |
| HR Director | – | Read/Write (all) | – | – | Read |
| Occupational Physician | – | Read (limited) | Read/Write | – | – |
| Accounting Specialist | – | – | – | Read/Write | – |
| System Administrator | – | – | – | – | Read/Write |
| Auditor (internal) | Read (sampling) | Read | Read (justified) | Read | Read |
| Developer (Prod) | FORBIDDEN | FORBIDDEN | FORBIDDEN | FORBIDDEN | – |
| Developer (Test/Mask) | Masked | Masked | Synthetic | Masked | – |

### 3.2. ABAC (Attribute-Based Access Control)

Complements RBAC under complex conditions. The decision is the combination of user attributes (department, location, seniority), resource attributes (classification, owning team), environment (device posture, network location, time, MFA status) and action type as a **policy expression**.

**Example ABAC rule:**

```
PERMIT
  WHEN
    user.department == "Finance"
    AND resource.classification IN ("Financial")
    AND resource.region == user.region
    AND device.posture == "compliant"
    AND mfa.recent < 8h
    AND time.local BETWEEN 08:00 AND 20:00
```

ABAC is particularly powerful for cross-border transfer restrictions and multi-jurisdictional (e.g., EU data subject vs. Turkish data subject) distinctions.

### 3.3. PBAC and ReBAC

ReBAC is preferred where relational authorization is required (e.g., "I can only see my customer's data within my assigned case"). For complex business rules, PBAC (policy engine — OPA, Cedar) is positioned as a central decision point.

## 4. User Lifecycle (JML — Joiner / Mover / Leaver)

### 4.1. Joiner (Onboarding)

Trigger: Employment contract signed in HR, start date confirmed.

| Step | Owner | SLA |
|------|-------|-----|
| Role template selection by position | HR + Manager | -3 business days before start |
| Account creation (IdP, email, directory) | IAM | -1 business day before start |
| Device assignment and device policy | IT Operations | -1 business day before start |
| Standard role assignments (RBAC package) | IAM | -1 business day before start |
| MFA enrollment requirement | User | First day, first session |
| Confidentiality undertaking (see 06-idari-tedbirler) | HR | Orientation day |
| KVKK + information security training | HR + LMS | First 5 business days |
| Non-standard access requests | Manager → IAM | When needed |

### 4.2. Mover (Department/Position Change)

**Critical rule:** Adding rights for the new role is **not enough**. The privileges of the old role **must be revoked**. Failure of the mover process creates "privilege creep" over time and is itself a finding under KVKK audit.

| Step | Owner | SLA |
|------|-------|-----|
| Inventory of all old role rights | IAM | Change approval + 1 business day |
| New role template applied | IAM | Change date |
| Revocation of old privileges | IAM | Change date + 7 days (retention during transition is forbidden unless rationale documented) |
| Manager validation of new role | New Manager | Change date + 14 days |

### 4.3. Leaver (Departure)

| Step | Owner | SLA |
|------|-------|-----|
| Access closure (planned departure) | IAM | Last working day at 18:00 |
| Access closure (termination/bad leaver) | IAM | **Within minutes of decision** — by HR call |
| Device handover, disk handover/encryption verification | IT Operations | Last working day |
| Email forwarding (if appropriate) and auto-reply | IT Operations | Last working day |
| Log/data retention period before account is deleted | IAM + Legal | As per policy (typically 90–365 days) |
| Final account destruction | IAM | End of retention period |
| Vendor/consultant departure notification chain | Contract Owner | -7 days from contract end |

## 5. Quarterly Access Recertification

Each quarter, owners by **personal data category** complete the following review for their systems:

1. The IAM platform (Entra/Okta/Keycloak etc.) generates a review list: role → user, list of direct privileges, last login date, last MFA date.
2. **Owner manager** decides for each row: keep / remove / modify.
3. The decision is delivered to IAM within 14 business days. Otherwise, **rights are automatically suspended** (auto-revoke on no-response).
4. Review record is digitally signed and kept for 5 years (audit evidence).
5. Annotated findings are reported to the CISO; 100% completion is a KPI.

**Critical systems (personnel + health + financial + customer DB):** review **quarterly**.
**General systems:** review **annually**.

## 6. Privileged Access Management (PAM)

### 6.1. Scope

The following accounts are considered "privileged" and are taken under PAM:

- Domain Admin, Cloud Tenant Admin (Global Admin), root, sa, postgres, oracle DBA.
- Hypervisor / cluster administrator (vCenter, Kubernetes cluster-admin).
- Vault/secret manager administrator.
- SIEM/SOC analyst privilege (especially capabilities to delete/modify logs).
- Backup administrator.
- Network equipment (firewall, switch, load balancer) administrator.
- Any account with direct SQL access to a production DB holding personal data.

### 6.2. Design Rules

- **Vault-based exit:** Privileged credentials are pulled from a vault (CyberArk, HashiCorp Vault, Delinea, Azure PIM, AWS IAM Identity Center + Session Manager); not statically distributed.
- **JIT (Just-in-Time) elevation:** Roles are not permanently assigned; opened with request + approval + time window (e.g., 1–4 hours). Automatically revoked at the end of the period.
- **JEA (Just-Enough-Admin):** Even when elevated, only the cmdlet/command/scope needed for that specific job is opened.
- **Session recording:** PAM session (RDP, SSH, web console) is recorded as **full screen video + command stream**. The recording is kept immutable in a separate storage that the actual operator cannot access.
- **MFA mandatory:** PAM login requires MFA + device compliance check every time.
- **Request + approval chain:** Two-sided approval (4-eyes). Break-glass in emergencies.
- **Time window:** Privileged sessions outside normal business hours automatically tag the SOC with **enhanced monitoring**.

### 6.3. Break-Glass Accounts

- For each critical platform, **two** break-glass accounts exist.
- Their passwords are kept enveloped (split knowledge) in the vault, use generates an alarm, and a justified report is mandatory within 24 hours.
- MFA exception is **not allowed**; FIDO2 physical key is mandatory (including a backup key).
- Annual drill is mandatory; evidence of successful use is added to the audit record.

## 7. Access Request and Approval Flow

```
User (request) → Manager (1st approval) → Resource Owner (2nd approval)
                                       → KVKK Officer (justification assessment if personal data)
                                       → IAM (implementation)
                                       → Time-bound assignment (default 90 days, critical 30 days)
                                       → Automatic removal at end of period + re-request requirement
```

**Mandatory fields on the request form:**
- User, requested role/resource, justification (job description), duration, personal data category, data minimization note.
- If the KVKK Officer cannot perform the "need-to-know" test, a **rejection with justification** returns to the IAM record.

## 8. Layer-Based Implementation

### 8.1. Operating System (Linux)

```
# /etc/sudoers.d/finance-readers — limited sudo
%finance-readers ALL=(postgres) NOPASSWD: /usr/bin/psql -U readonly -d finance_db
Defaults:%finance-readers logfile=/var/log/sudo_finance.log, log_input, log_output

# File ACL example — personnel
setfacl -m g:hr-uzman:r-x /var/data/hr/sicil
setfacl -m g:hr-yonetici:rwx /var/data/hr/sicil
chmod o-rwx /var/data/hr/sicil
```

### 8.2. Operating System (Windows / AD)

- AD Tier Model (Tier 0 / 1 / 2): Tier 0 accounts only log on to Tier 0 machines; PAW (Privileged Access Workstation) is mandatory.
- Local admin passwords are different on each machine and rotate automatically with LAPS (Local Administrator Password Solution).
- "Domain Admin" membership count is single-digit; individual admin account + separate user account.

### 8.3. Database

```sql
-- PostgreSQL — Row Level Security
ALTER TABLE customer_pii ENABLE ROW LEVEL SECURITY;
CREATE POLICY pii_region_policy ON customer_pii
  USING (region = current_setting('app.current_region'));

-- Masked view (for developer)
CREATE VIEW customer_dev AS
  SELECT id, hash(email) AS email_hash, mask_phone(phone) AS phone, ...
  FROM customer_pii;
REVOKE ALL ON customer_pii FROM dev_role;
GRANT SELECT ON customer_dev TO dev_role;
```

### 8.4. Application / API

- An **authorization decision** is mandatory for every endpoint (URL filtering is not enough).
- "Insecure Direct Object Reference (IDOR)" testing runs on every CI (OWASP ASVS V4.1).
- API keys from the vault, short-lived tokens (OAuth2 / OIDC), scope-limited.
- Rate limiting based on user + IP + endpoint.

### 8.5. File Sharing / SaaS

- Cloud storage: "Anyone with the link" disabled by default; external sharing requires approval (DLP integrated).
- SharePoint/Drive: sensitivity label → automatic encryption + access restriction.
- Email external sharing: TLS enforcement + external recipient warning + DLP policy.

### 8.6. Storage (S3 / Blob / GCS)

- Public access **default block**.
- Bucket policy + IAM policy conflicts are scanned (CSPM).
- "Block public ACL" enforced at the tenant level.
- Mandatory encryption with KMS (BYOK optional).

## 9. Service Accounts and Machine Identity

- Human and service accounts are **separated**. Service accounts are not assigned in a person's name; team ownership is mandatory.
- Where possible, **managed identity** (Azure MI, AWS IAM Role for Service, GCP Workload Identity).
- If static secrets are required, in the vault, with automatic rotation.
- Service accounts are included in annual review; mandatory transfer if owner leaves.

## 10. Monitoring and Detection

The following events are high priority in SIEM:

- Outside-business-hours session on a critical system.
- Access to a personal data table after privilege elevation (sudo, runas, AssumeRole).
- Multiple failed MFA + then successful (sign of push fatigue).
- Creation of a new service account, new role, new IAM policy attach.
- Use of break-glass account.
- Concurrent sessions of the same user from two distant geographic locations.
- Following a "DENY", an attempt by the same user to access via a different path within a short time.

## 11. Exception Management

Exceptions can only be in writing, justified, and time-limited. Form: who, why, which policy clause, compensating controls, duration (≤180 days, extension requires re-approval), risk owner, KVKK Officer opinion. The exception register is audited annually.

## 12. Checklist (Quick Audit)

- [ ] Are all accounts managed via SSO/IdP?
- [ ] Are RBAC roles documented, with a clear owner and last review record?
- [ ] Are there permissions assigned directly to users? (Target: 0)
- [ ] Are Joiner-Mover-Leaver SLAs met? (Mover revoke 7 days, Leaver 0 days.)
- [ ] Is quarterly access review 100% for critical systems?
- [ ] Is PAM scope clear, session recording immutable?
- [ ] Have break-glass accounts been validated by drill?
- [ ] Are service accounts owned, with automatic password rotation?
- [ ] Are tables containing personal data restricted by RLS / view-based limitation?
- [ ] Is developer prod access zero?
- [ ] Is cloud storage public access block active across the tenant?
- [ ] Does the access request form include the KVKK Officer's opinion?
- [ ] Is the exception record time-bound and with compensating controls?
- [ ] Has an annual access simulation (Red Team privilege escalation drill) been performed?
- [ ] Do all privileged actions go to SIEM? (Sub-5-minute lag)
- [ ] Is the access review completion rate reported?

## 13. Evidence and Retention

- IAM logs: at least 2 years, 5 years for systems containing personal data.
- Access review signature/decision records: 5 years.
- PAM session recordings: 1 year (up to 5 years with justification).
- Break-glass usage report: 5 years.
- Exception decisions: 5 years following the end of the term.

## 14. Breach Scenarios and Response

- **Privileged account compromised:** Account immediately disabled, sessions terminated, all secrets rotated from the vault, audit + IoC scanning on affected systems, KVKK Committee informed within 4 hours.
- **Old privileges not removed at Mover and access occurred with old privileges:** Incident classification "high", post-mortem mandatory, if the data subject is affected, the 08-ihlal-yonetimi procedure is triggered.
- **Access review left blank:** Automatic suspension applied; if continues without justification for 7 days, account is closed.

---

## Türkçe

# Erişim Kontrolü

## 1. Amaç

Kişisel verilere erişimin yalnızca yetkili kişilere, yetkili oldukları kapsamda ve yetkili oldukları süreyle sınırlı olmasını sağlamak. KVKK m.12(1) "hukuka aykırı erişimi önleme" yükümlülüğünün operasyonel ayağı bu dokümandır.

## 2. Temel İlkeler

### 2.1. En Az Ayrıcalık (Least Privilege)

Her kullanıcı, servis hesabı ve uygulama, görevini yerine getirmek için **gerekli olan minimum yetkiyle** çalıştırılır. Yetki "olabilir mi?" değil, "olmalı mı?" sorusuna verilen cevapla belirlenir. Genişletilmiş yetkiler talep üzerine, gerekçeyle, süreli verilir.

### 2.2. Bilmesi Gereken (Need-to-Know)

Erişim hakkı, kullanıcının iş tanımı içerisindeki görevin yürütülmesi için **fiilen ihtiyaç duyulan** kişisel veriyle sınırlandırılır. "Yetkili olmak" ile "erişmek" farklıdır; toplu yetkilendirme yerine veri kümesi/ kayıt seviyesinde sınırlama tercih edilir.

### 2.3. Görev Ayrılığı (Segregation of Duties — SoD)

Hassas işlemlerde tek kişinin uçtan uca süreci tamamlayamayacağı kontroller kurulur. Örnekler:

- Uygulama geliştirici, üretim veritabanına doğrudan yazamaz.
- Bordro hazırlayan kişi onaylayamaz.
- Erişim talebini açan, kendi talebini onaylayamaz.
- DB yöneticisi, denetim loglarını silme yetkisine sahip olamaz (logları farklı sistemde, ayrı yetkili tutar).

### 2.4. Default Deny

Açıkça izin verilmemiş tüm erişim isteklerinin sonucu **redde** ayarlanır (firewall, ACL, IAM policy, RLS).

### 2.5. Periyodik Yeniden Doğrulama

Verilen her yetki **kalıcı kabul edilmez**. Çeyreklik (kritik) ve yıllık (genel) review'larla yeniden doğrulanır.

## 3. Erişim Kontrol Modelleri

### 3.1. RBAC (Role-Based Access Control)

Standart kullanım modelidir. Yetkiler **rollere** atanır, kullanıcılar rollere atanır. Doğrudan kullanıcıya yetki vermek yasaktır (acil durumda break-glass dışında).

**Rol matrisi örneği (kişisel veri perspektifi):**

| Rol | Müşteri Verisi | Çalışan Özlük | Sağlık Verisi | Mali Veri | Log/Audit |
|-----|---------------|---------------|---------------|-----------|-----------|
| Çağrı Merkezi Temsilcisi | Oku (kendi atanmış müşteri) | – | – | – | – |
| Çağrı Merkezi Yöneticisi | Oku (ekip), maskeli | – | – | – | Oku (ekip) |
| İK Uzmanı | – | Oku/Yaz (kendi sicil grubu) | – | – | – |
| İK Direktörü | – | Oku/Yaz (tümü) | – | – | Oku |
| İşyeri Hekimi | – | Oku (sınırlı) | Oku/Yaz | – | – |
| Muhasebe Uzmanı | – | – | – | Oku/Yaz | – |
| Sistem Yöneticisi | – | – | – | – | Oku/Yaz |
| Denetçi (iç) | Oku (örnekleme) | Oku | Oku (gerekçeli) | Oku | Oku |
| Geliştirici (Prod) | YASAK | YASAK | YASAK | YASAK | – |
| Geliştirici (Test/Mask) | Maskeli | Maskeli | Sentetik | Maskeli | – |

### 3.2. ABAC (Attribute-Based Access Control)

Karmaşık koşullarda RBAC'i tamamlar. Karar; kullanıcı niteliği (departman, lokasyon, kıdem), kaynak niteliği (sınıflandırma, sahip ekip), ortam (cihaz uyumluluğu, ağ konumu, saat, MFA durumu) ve eylem türünün **politika ifadesi** ile birleştirilmesidir.

**Örnek ABAC kuralı:**

```
PERMIT
  WHEN
    user.department == "Finans"
    AND resource.classification IN ("Mali")
    AND resource.region == user.region
    AND device.posture == "compliant"
    AND mfa.recent < 8h
    AND time.local BETWEEN 08:00 AND 20:00
```

ABAC; yurt dışı aktarım kısıtları, çoklu yargı bölgesi (örn. AB veri konusu vs. Türkiye veri konusu) ayrımları için özellikle güçlüdür.

### 3.3. PBAC ve ReBAC

İlişkisel yetkilendirme gereken durumlarda (örn. "müşterimin verisini yalnızca atanmış vakam içinde görebilirim") ReBAC tercih edilir. Karmaşık iş kurallarında PBAC (policy engine — OPA, Cedar) merkezi karar noktası olarak konumlandırılır.

## 4. Kullanıcı Yaşam Döngüsü (JML — Joiner / Mover / Leaver)

### 4.1. Joiner (İşe Başlama)

Tetik: İK'da iş akdi imzalanır, başlama tarihi onaylanır.

| Adım | Sahip | SLA |
|------|-------|-----|
| Pozisyona göre rol şablonu seçimi | İK + Yönetici | İşe başlamadan -3 iş günü |
| Hesap oluşturma (IdP, e-posta, dizin) | IAM | İşe başlamadan -1 iş günü |
| Cihaz tahsisi ve cihaz politikası | BT Operasyon | İşe başlamadan -1 iş günü |
| Standart rol atamaları (RBAC paketi) | IAM | İşe başlamadan -1 iş günü |
| MFA kayıt zorunluluğu | Kullanıcı | İlk gün, ilk oturum |
| Gizlilik taahhütnamesi (bkz. 06-idari-tedbirler) | İK | Oryantasyon günü |
| KVKK + bilgi güvenliği eğitimi | İK + LMS | İlk 5 iş günü |
| Standart dışı erişim talepleri | Yönetici → IAM | İhtiyaç anında |

### 4.2. Mover (Departman/Pozisyon Değişimi)

**Kritik kural:** Yeni rol için yetki ekleme **yetmez**. Eski rolün yetkileri **çekilmek zorundadır**. Mover sürecinin başarısızlığı zamanla "ayrıcalık birikmesi" (privilege creep) yaratır ve KVKK denetiminde başlı başına bulgu konusudur.

| Adım | Sahip | SLA |
|------|-------|-----|
| Eski rolün tüm yetkilerinin envanteri | IAM | Değişiklik onayı + 1 iş günü |
| Yeni rol şablonu uygulama | IAM | Değişiklik tarihi |
| Eski yetkilerin çekilmesi (revoke) | IAM | Değişiklik tarihi + 7 gün (gerekçesi belgelenmedikçe geçişte muhafaza yasak) |
| Yöneticinin yeni rol doğrulaması | Yeni Yönetici | Değişiklik tarihi + 14 gün |

### 4.3. Leaver (Ayrılış)

| Adım | Sahip | SLA |
|------|-------|-----|
| Erişim kapatma (planlı ayrılış) | IAM | Son çalışma günü saat 18:00 |
| Erişim kapatma (sözleşme feshi/kötü ayrılış) | IAM | **Karar dakika içinde** — İK çağrısıyla |
| Cihaz teslim, disk teslim/şifreleme doğrulama | BT Operasyon | Son çalışma günü |
| E-posta yönlendirmesi (uygunsa) ve auto-reply | BT Operasyon | Son çalışma günü |
| Hesap silinmeden önce log/data koruma süresi | IAM + Hukuk | Politika gereği (genelde 90–365 gün) |
| Hesap nihai imha | IAM | Saklama süresi sonu |
| Tedarikçi/danışman ayrılışı bildirim zinciri | Sözleşme Sahibi | Sözleşme bitişinden -7 gün |

## 5. Çeyreklik Erişim Review (Access Recertification)

Her çeyrek **kişisel veri kategorisi** bazlı sahipler, kendi sistemleri için aşağıdaki review'u tamamlar:

1. IAM platformu (Entra/Okta/Keycloak vb.) review listesi üretir: rol → kullanıcı, doğrudan yetki listesi, son giriş tarihi, son MFA tarihi.
2. **Sahip yönetici** her satır için karar verir: koru / kaldır / değiştir.
3. Karar 14 iş günü içinde IAM'e iletilir. Aksi halde **otomatik olarak yetki askıya alınır** (auto-revoke on no-response).
4. Review kaydı dijital imzalanır ve 5 yıl saklanır (denetim kanıtı).
5. Açıklamalı bulgular CISO'ya raporlanır; %100 tamamlanma KPI'dır.

**Kritik sistemler (özlük + sağlık + finansal + müşteri DB):** review **çeyreklik**.
**Genel sistemler:** review **yıllık**.

## 6. Ayrıcalıklı Erişim Yönetimi (PAM)

### 6.1. Kapsam

Aşağıdaki hesaplar "ayrıcalıklı" sayılır ve PAM kapsamına alınır:

- Domain Admin, Cloud Tenant Admin (Global Admin), root, sa, postgres, oracle DBA.
- Hypervisor / cluster yöneticisi (vCenter, Kubernetes cluster-admin).
- Kasa/secret manager yöneticisi.
- SIEM/SOC analist yetkisi (özellikle log silme/değiştirme yetenekleri).
- Yedekleme yöneticisi.
- Ağ ekipmanı (firewall, switch, load balancer) yöneticisi.
- Kişisel veri tutan üretim DB'sine doğrudan SQL erişimi olan herhangi bir hesap.

### 6.2. Tasarım Kuralları

- **Vault tabanlı çıkış:** Ayrıcalıklı kimlik bilgileri vault'tan (CyberArk, HashiCorp Vault, Delinea, Azure PIM, AWS IAM Identity Center + Session Manager) çekilir; statik dağıtılmaz.
- **JIT (Just-in-Time) yükseltme:** Rol kalıcı atanmaz; talep + onay + zaman penceresiyle açılır (ör. 1–4 saat). Süre sonunda otomatik geri alınır.
- **JEA (Just-Enough-Admin):** Yükseltme alındığında bile yalnızca o iş için gereken cmdlet/komut/kapsam açılır.
- **Oturum kaydı:** PAM oturumu (RDP, SSH, web konsol) **tam ekran video + komut akışı** olarak kayda alınır. Kayıt, asıl operatörün erişemeyeceği ayrı bir depolamada immutable tutulur.
- **MFA zorunlu:** PAM girişi her seferinde MFA + cihaz uyumluluğu kontrolü ister.
- **Talep + onay zinciri:** İki taraflı onay (4-eyes). Acil durumda break-glass.
- **Saatli pencere:** Olağan iş saati dışındaki ayrıcalıklı oturum, otomatik **artırılmış izleme** etiketiyle SOC'a düşer.

### 6.3. Break-Glass Hesapları

- Her kritik platform için **iki adet** break-glass hesabı vardır.
- Parolaları kasada zarflanmış (split knowledge) tutulur, kullanım alarm üretir, 24 saat içinde gerekçeli rapor zorunludur.
- MFA istisnası **yoktur**; FIDO2 fiziksel anahtar zorunludur (yedek anahtar dahil).
- Yıllık tatbikat zorunlu; başarılı kullanım kanıtı denetim kaydına eklenir.

## 7. Erişim Talep ve Onay Akışı

```
Kullanıcı (talep) → Yöneticisi (1. onay) → Kaynak Sahibi (2. onay)
                                       → KVKK Sorumlusu (kişisel veri ise gerekçe değerlendirmesi)
                                       → IAM (uygulama)
                                       → Süreli atama (default 90 gün, kritik 30 gün)
                                       → Süre sonu otomatik kaldırma + yeniden talep zorunluluğu
```

**Talep formunda zorunlu alanlar:**
- Kullanıcı, talep edilen rol/kaynak, gerekçe (iş açıklaması), süre, kişisel veri kategorisi, veri minimizasyon notu.
- KVKK Sorumlusu, "bilmesi gereken" testini yapamadıysa **reddi gerekçeli** bir IAM kaydına döner.

## 8. Katman Bazlı Uygulama

### 8.1. İşletim Sistemi (Linux)

```
# /etc/sudoers.d/finance-readers — sınırlı sudo
%finance-readers ALL=(postgres) NOPASSWD: /usr/bin/psql -U readonly -d finance_db
Defaults:%finance-readers logfile=/var/log/sudo_finance.log, log_input, log_output

# Dosya ACL örneği — özlük
setfacl -m g:hr-uzman:r-x /var/data/hr/sicil
setfacl -m g:hr-yonetici:rwx /var/data/hr/sicil
chmod o-rwx /var/data/hr/sicil
```

### 8.2. İşletim Sistemi (Windows / AD)

- AD Tier Modeli (Tier 0 / 1 / 2): Tier 0 hesaplar yalnızca Tier 0 makinalara giriş yapar; PAW (Privileged Access Workstation) zorunludur.
- LAPS (Local Administrator Password Solution) ile yerel admin parolaları her makinede farklı, otomatik döner.
- "Domain Admin" üyesi sayısı tek hane; bireysel admin hesabı + ayrı kullanıcı hesabı.

### 8.3. Veritabanı

```sql
-- PostgreSQL — Row Level Security
ALTER TABLE customer_pii ENABLE ROW LEVEL SECURITY;
CREATE POLICY pii_region_policy ON customer_pii
  USING (region = current_setting('app.current_region'));

-- Maskeli görünüm (geliştiriciye)
CREATE VIEW customer_dev AS
  SELECT id, hash(email) AS email_hash, mask_phone(phone) AS phone, ...
  FROM customer_pii;
REVOKE ALL ON customer_pii FROM dev_role;
GRANT SELECT ON customer_dev TO dev_role;
```

### 8.4. Uygulama / API

- Her endpoint için **authorization decision** zorunlu (URL filtreleme yetmez).
- "Insecure Direct Object Reference (IDOR)" testi her CI'da çalışır (OWASP ASVS V4.1).
- API key'ler kasadan, kısa ömürlü token (OAuth2 / OIDC), scope sınırlı.
- Rate limiting kullanıcı + IP + endpoint bazlı.

### 8.5. Dosya Paylaşım / SaaS

- Bulut depolama: "Anyone with the link" varsayılan kapalı; harici paylaşım onayı zorunlu (DLP entegre).
- SharePoint/Drive: hassasiyet etiketi (sensitivity label) → otomatik şifreleme + erişim kısıtı.
- E-posta dış paylaşım: TLS zorlama + dış alıcı uyarısı + DLP politikası.

### 8.6. Depo (S3 / Blob / GCS)

- Public access **default block**.
- Bucket policy + IAM policy çakışması taranır (CSPM).
- "Block public ACL" tenant bazında zorlanır.
- KMS ile zorunlu şifreleme (BYOK opsiyonel).

## 9. Servis Hesapları ve Makina Kimliği

- İnsan ile servis hesabı **ayrılır**. Servis hesabı insan adına atanmaz; ekip sahipliği zorunlu.
- Mümkünse **managed identity** (Azure MI, AWS IAM Role for Service, GCP Workload Identity).
- Statik secret zorunluysa kasada, otomatik döndürmeli.
- Servis hesabı yıllık review'a dahil; sahibi ayrılırsa devir zorunlu.

## 10. İzleme ve Tespit

Aşağıdaki olaylar SIEM'de yüksek öncelik:

- Kritik sistemde iş saati dışı oturum.
- Yetki yükseltme (sudo, runas, AssumeRole) sonrası kişisel veri tablosuna erişim.
- Birden fazla başarısız MFA + ardından başarılı (push fatigue belirtisi).
- Yeni servis hesabı oluşturma, yeni rol oluşturma, yeni IAM policy attach.
- Break-glass hesabı kullanımı.
- Aynı kullanıcının iki uzak coğrafi konumdan eş zamanlı oturumu.
- "DENY" sonrası kısa süre içinde aynı kullanıcı tarafından farklı yoldan erişim denemesi.

## 11. İstisna Yönetimi

İstisna ancak yazılı, gerekçeli, süreli olabilir. Form: kim, neden, hangi politika maddesi, telafi edici kontroller, süre (≤180 gün, uzatma yeniden onayla), risk sahibi, KVKK Sorumlusu görüşü. İstisna defteri yıllık review'da denetlenir.

## 12. Kontrol Listesi (Hızlı Denetim)

- [ ] Tüm hesaplar SSO/IdP üzerinden mi yönetiliyor?
- [ ] RBAC rolleri yazılı, sahibi belirli, son review'u kayıtlı mı?
- [ ] Doğrudan kullanıcıya verilmiş yetki var mı? (Hedef: 0)
- [ ] Joiner-Mover-Leaver SLA'ları sağlanıyor mu? (Mover'da revoke 7 gün, Leaver 0 gün.)
- [ ] Çeyreklik erişim review'u kritik sistemler için %100 mü?
- [ ] PAM kapsamı net, oturum kaydı immutable mı?
- [ ] Break-glass hesapları tatbikatla doğrulandı mı?
- [ ] Servis hesapları sahipli, parolaları otomatik döndürmeli mi?
- [ ] Kişisel veri içeren tablolarda RLS / view tabanlı kısıtlama uygulandı mı?
- [ ] Geliştirici prod erişimi sıfır mı?
- [ ] Bulut depolama public access block tenant geneli aktif mi?
- [ ] Erişim talep formu KVKK Sorumlusu görüşü içeriyor mu?
- [ ] İstisna kaydı süreli ve telafi edici kontrollü mü?
- [ ] Yıllık erişim simülasyonu (Red Team yetki yükseltme tatbikatı) yapıldı mı?
- [ ] Tüm ayrıcalıklı eylemler SIEM'e gidiyor mu? (5 dk gecikme altı)
- [ ] Erişim review tamamlanma oranı raporlanıyor mu?

## 13. Kanıt ve Saklama

- IAM logları: en az 2 yıl, kişisel veri içeren sistemler için 5 yıl.
- Erişim review imza/karar kayıtları: 5 yıl.
- PAM oturum kayıtları: 1 yıl (gerekçeyle 5 yıla kadar).
- Break-glass kullanım rapor: 5 yıl.
- İstisna kararları: süresinin sonunu takip eden 5 yıl.

## 14. İhlal Senaryoları ve Yanıt

- **Ayrıcalıklı hesap ele geçirildi:** Hesap derhal devre dışı, oturumlar kopar, kasadan tüm sırlar döner, etkili sistemlerde audit + IoC tarama, KVKK Komitesi 4 saat içinde bilgilendirilir.
- **Mover'da eski yetki kaldırılmadı ve eski yetkiyle erişim oldu:** Olay sınıflandırması "yüksek", post-mortem zorunlu, ilgili kişi etkilendiyse 08-ihlal-yonetimi prosedürü tetiklenir.
- **Erişim review boş bırakıldı:** Otomatik askıya alma uygulanır, 7 gün içinde gerekçesiz devam ederse hesap kapanır.
