---
Doküman: Erişim Kontrolü Politikası ve Prosedürü
Bölüm: 05-teknik-tedbirler
Sahip: Bilgi Güvenliği Yöneticisi (CISO)
Onaylayan: BT Direktörü + KVKK Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş
İlgili Mevzuat: 6698 sayılı KVKK m.12; Kişisel Veri Güvenliği Rehberi — "Kullanıcı Hesap Yönetimi ve Yetki Matrisi"
İlgili Standart: ISO/IEC 27001:2022 A.5.15 (Access Control), A.5.16 (Identity Management), A.5.17 (Authentication Information), A.5.18 (Access Rights), A.8.2 (Privileged Access Rights), A.8.3 (Information Access Restriction), A.8.5 (Secure Authentication); NIST CSF 2.0 PR.AA-1..PR.AA-6; NIST SP 800-53 AC-2, AC-3, AC-5, AC-6; CIS Controls v8 #5, #6
---

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
