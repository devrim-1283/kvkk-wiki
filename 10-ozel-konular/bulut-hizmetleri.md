---
Doküman: Bulut Hizmetleri Yönetimi (SaaS / PaaS / IaaS)
Bölüm: 10-ozel-konular
Sahip: KVKK Sorumlusu + CISO + IT Müdürü
Onaylayan: Hukuk Müdürü + KVKK Komitesi + CTO
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + Kurul aktarım kararı değişikliklerinde
İlgili Mevzuat: 6698 sayılı KVKK m.9, m.12; KVKK Yurt Dışı Aktarım Mevzuatı (m.9 değişiklik); KVKK 2024 Standart Sözleşme; ABD CLOUD Act / FISA 702; ISO/IEC 27017; ISO/IEC 27018; CCPA / GDPR (karşılaştırma)
---

# Bulut Hizmetleri Yönetimi

## 1. Amaç

SaaS, PaaS, IaaS hizmetlerinin KVKK uyumlu seçimi, sözleşmelendirilmesi, uygulanması ve denetlenmesi. Bulut, şirketimizin kişisel veri işleme yüzeyinin **en geniş** ve KVKK risk **en yüksek** alanlarından biridir.

## 2. Bulut Modelleri ve Sorumluluk Paylaşımı

### 2.1. Hizmet Tipleri

| Tip | Sağlayıcı Sorumluluğu | Müşteri Sorumluluğu |
|-----|----------------------|---------------------|
| **IaaS** (AWS EC2, Azure VM, GCP Compute) | Fiziksel altyapı, hipervizör | OS, uygulama, veri, kullanıcı |
| **PaaS** (Azure App Service, AWS Lambda, GCP Cloud Run) | Altyapı + runtime | Uygulama + veri |
| **SaaS** (Microsoft 365, Salesforce, HubSpot) | Tam yığın | Veri + erişim yönetimi |

### 2.2. Shared Responsibility Model

- **Cloud OF the cloud** — sağlayıcının altyapı güvenliği.
- **Cloud IN the cloud** — müşterinin veri ve uygulama güvenliği.
- KVKK açısından: Müşteri (Şirketimiz) **veri sorumlusu** kalır; sağlayıcı genelde **veri işleyen** sıfatındadır.

### 2.3. Veri Sorumlusu vs İşleyen Belirleme

| Senaryo | Sağlayıcı Sıfatı |
|---------|------------------|
| AWS S3'te müşteri verisi | İşleyen (Şirket sorumluluğu) |
| Salesforce CRM kullanım | İşleyen |
| Mailchimp e-posta gönderimi | İşleyen |
| Microsoft 365 e-posta sunucusu | İşleyen (genelde) |
| LinkedIn pazarlama platformu | Karma — bazı durumlarda LinkedIn de sorumlu |
| Google Workspace | İşleyen |
| OpenAI ChatGPT (kurumsal API) | İşleyen (OpenAI sözleşmeli) |

> Sözleşmesel kontrol pay belirler — DPA detayları kritik.

## 3. Veri Yerleşimi ve Region Seçimi

### 3.1. Türkiye Region Tercih Sıralaması

1. **Türkiye'de yerleşik bulut sağlayıcı / region** (Türk Telekom Bulut, Turkcell Bulut, Akamai Linode İstanbul, AWS Türkiye Yerel Bölgesi, Azure Türkiye region — mevcut planlar).
2. **AB region** — yeterlilik kararı (Kurul yayımladığında) avantaj.
3. **ABD / Asya** — Standart Sözleşme + ek tedbirler.

### 3.2. Veri İkamet Klozu (Data Residency)

Sözleşmede:
- "Veri **Türkiye / AB** sınırları içinde işlenecektir."
- "Müşteri (Şirket) onayı olmadan başka region'a taşınmayacaktır."
- "Yedek ve disaster recovery tesisleri de aynı region kapsamında."

### 3.3. Pseudo-localization Sorunu

Sağlayıcı "Türkiye region" kursa bile:
- Yönetim düzlemi (control plane) genelde merkezi.
- Destek personeli yurt dışında erişebilir.
- Loglar merkezi toplanabilir.

> Region seçimi sadece veri **at-rest** kontrolüdür. Erişim, log, destek için ek garantiler gerekir.

## 4. Yurt Dışı Aktarım Analizi

### 4.1. KVKK m.9 (Güncel Hali — 2024)

KVKK m.9 değişikliği ile yurt dışı aktarım rejimi:
- **Yeterlilik kararı** olan ülkeye serbest aktarım.
- **Standart Sözleşme** (Kurul tarafından yayımlanan).
- **Bağlayıcı şirket kuralları** (BCR — onay süreci).
- **Açık rıza** (sınırlı, son çare).
- **Geçici / sınırlı durumlar** (KVKK m.9/6).

### 4.2. Standart Sözleşme

KVKK Kurulu **Standart Sözleşme** modüllerini yayımlamıştır (2024). Modül tipleri:
1. Veri sorumlusu → Veri sorumlusu (yurt dışı).
2. Veri sorumlusu → Veri işleyen (yurt dışı).
3. Veri işleyen → Alt-işleyen (yurt dışı).
4. Veri işleyen → Veri sorumlusu (yurt dışı).

> Sözleşme imzalanır + **Kurul'a 5 iş günü içinde bildirilir**. Bildirim yapılmazsa sözleşme geçerli ama Kurul yaptırım sebebi.

### 4.3. Transfer Impact Assessment (TIA)

Yurt dışı aktarım öncesi yapılmalı:
- Hedef ülke veri koruma rejimi.
- Hükümet erişim talepleri (FISA, CLOUD Act, vb.).
- Sağlayıcı şeffaflık raporları.
- Ek tedbirler (E2E şifreleme, anahtar müşteride).
- Kalan risk + kabul.

### 4.4. CLOUD Act (ABD)

ABD'de yerleşik veya ABD bağlantılı sağlayıcılar (Amazon, Microsoft, Google, Apple, Oracle) ABD hükümeti talebiyle veriyi açıklamak zorunda **bulundukları ülkeye bağlı olmaksızın**. KVKK ile çatışır.

**Pratik:**
- ABD sağlayıcısı kullanılıyorsa kritik veri için ek tedbir.
- Müşteri yönetimli anahtar (CMK) — ABD sağlayıcı şifrelenmiş veriyi göremez.
- Hold Your Own Key (HYOK) — anahtar Şirket altyapısında.

### 4.5. FISA 702 (ABD)

ABD istihbaratının yabancı kişiler hakkında ABD sağlayıcılarından veri alabilmesi. Schrems II kararı (AB Adalet Divanı) bu nedenle Privacy Shield'i iptal etti. KVKK için benzer endişeler.

## 5. DPA (Data Processing Agreement) — Bulut Sağlayıcı

### 5.1. Asgari Klozlar (KVKK m.12 + Kurul beklentisi)

1. Veri kategorisi, amaç, süre.
2. Sağlayıcı sadece **müşteri talimatlarıyla** işler.
3. Gizlilik (NDA + sağlayıcı çalışan sır).
4. Teknik ve idari tedbirler (ISO 27001 vb.).
5. Alt-işleyen onay süreci.
6. İhlal bildirim 24 saat (sözleşmesel sıkı).
7. İlgili kişi taleplerinde destek.
8. Audit hakkı + raporlama.
9. Sözleşme sonu veri imha + sertifika.
10. Yurt dışı aktarım kuralları.
11. Sigorta + sorumluluk sınırı.
12. Uyuşmazlık çözüm (Türk hukuku tercih).

### 5.2. Standart Bulut Sağlayıcı DPA Şablonları

| Sağlayıcı | DPA Linki |
|-----------|-----------|
| AWS | aws.amazon.com/compliance/data-protection/ |
| Microsoft | microsoft.com/en-us/trust-center/privacy/gdpr-overview |
| Google | cloud.google.com/terms/data-processing-addendum |
| Salesforce | salesforce.com/company/legal/agreements/ |
| HubSpot | legal.hubspot.com/dpa |

> Standart DPA'lar GDPR odaklıdır. KVKK için ek anlaşma (addendum) gerekebilir.

## 6. Anahtar Yönetimi

### 6.1. Sağlayıcı Yönetimli (Default)

- AWS KMS, Azure Key Vault, GCP KMS standart.
- Sağlayıcı anahtarı görür ve kullanır.
- KVKK riski: anahtar sağlayıcıdaysa "şifreli depolama" zayıflar (sağlayıcı erişebilir).

### 6.2. Müşteri Yönetimli Anahtar (CMK / BYOK)

- Anahtar müşteri tarafından oluşturulur.
- Sağlayıcıya sağlanır ama müşteri rotation ve kontrol.
- Daha iyi.

### 6.3. Hold Your Own Key (HYOK)

- Anahtar Şirket altyapısında (HSM).
- Sağlayıcı her şifre çözme için Şirkete başvurur.
- En yüksek koruma; performans maliyeti.
- Çok hassas veri için (örn. sağlık, finans).

### 6.4. Confidential Computing

- TEE (Trusted Execution Environment), Intel SGX, AMD SEV.
- Bellek seviyesinde şifreleme.
- Hipervizör/sağlayıcı bile veriye erişemez.
- Yeni teknoloji — değerlendirilebilir.

## 7. SaaS Özel Konular

### 7.1. Microsoft 365

- E-posta, SharePoint, Teams, OneDrive.
- Türkiye region (yakın gelecek), şu an AB.
- DPA + Customer Lockbox + Double Key Encryption opsiyonları.
- E5 lisans daha sıkı kontrol.

### 7.2. Google Workspace

- Gmail, Drive, Docs, Meet.
- Region: AB ya da ABD.
- DPA + Client-side encryption (CSE).

### 7.3. Salesforce

- CRM verisi.
- AB region (Hyperforce).
- Shield (audit + encryption) ek lisans.

### 7.4. HubSpot

- CRM + pazarlama otomasyonu.
- AB / Avustralya region seçilebilir.
- DPA + standart sözleşme.

## 8. Bulut Erişim Yönetimi

### 8.1. Identity (IAM)

- Federation (SAML / OIDC) ile kurumsal AD/Entra entegrasyonu.
- MFA zorunlu.
- Privileged access — JIT (Just-In-Time).
- IAM rol ayrılması (least privilege).

### 8.2. Audit ve Loglama

- Tüm bulut sağlayıcısı log'ları (CloudTrail, Azure Activity Log, GCP Audit Logs) merkezi SIEM'e.
- Konfigürasyon değişiklikleri izlenir.
- Anomali algılama.

### 8.3. Konfigürasyon Yönetimi

- IaC (Terraform, ARM, CloudFormation) ile.
- Public S3 bucket, açık port denetimi.
- CSPM (Cloud Security Posture Management) — Wiz, Prisma, Defender for Cloud.

## 9. Veri Taşınabilirliği ve Çıkış Stratejisi

### 9.1. Vendor Lock-in Riski

- Proprietary format (Salesforce, HubSpot).
- Kapsamı, geçiş zamanı.
- Sözleşme sonu veri export hakkı.

### 9.2. Çıkış Planı

- Sözleşmede çıkış maddesi: standart format export, 90 gün veri erişim.
- Düzenli backup (kendi altyapımızda).
- Alternatif sağlayıcı sürekli değerlendirme.

### 9.3. Veri Silme Sertifikası

- Sözleşme sonu sağlayıcı veriyi silmeli + sertifika.
- Yedeklerden silme süresi (60-90 gün makul).

## 10. CASB ve Shadow IT

### 10.1. CASB (Cloud Access Security Broker)

- Microsoft Defender for Cloud Apps, Netskope, Zscaler.
- Bulut kullanım envanteri.
- DLP entegrasyonu.
- Anomali algılama.

### 10.2. Shadow IT

- Çalışanların onaysız SaaS kullanımı.
- Risk: KVKK + ihlal.
- CASB ile tespit + politika.
- Onay süreci formalize.

## 11. Bulut Sağlayıcı Seçim Kriterleri

| Kriter | Ağırlık |
|--------|---------|
| KVKK m.12 + sözleşme uygunluğu | Kritik |
| ISO/IEC 27001, 27017, 27018 | Yüksek |
| Türkiye/AB region | Yüksek |
| Standart Sözleşme imzaya hazır | Yüksek |
| CMK / HYOK desteği | Orta-Yüksek |
| Audit log + SIEM entegrasyonu | Yüksek |
| İhlal bildirim 24 saat klozu | Yüksek |
| Şeffaflık raporu | Orta |
| Sigorta kapsamı | Orta |
| Maliyet | Orta |

## 12. Bulut Migrasyon Süreci

```
1. Veri sınıflandırma (genel/özel/kritik)
2. Sağlayıcı seçimi (yukarıdaki kriterler)
3. DPIA (kritik veri için)
4. Sözleşme + DPA + Standart Sözleşme imza
5. Kurul'a Standart Sözleşme bildirim (5 iş günü)
6. Test ortamı + güvenlik konfigürasyonu
7. Aşamalı geçiş (canary)
8. Üretim canlı
9. Sürekli izleme + yıllık denetim
```

## 13. Tipik Hatalar

| Hata | Doğru Yaklaşım |
|------|----------------|
| Standart Sözleşme imzalı, Kurul'a bildirilmemiş | 5 iş günü zorunlu |
| Region seçimi yapılmamış | Türkiye / AB tercih |
| Müşteri yönetimli anahtar kullanılmıyor | CMK aktif |
| MFA aktif değil | Tüm bulut hesapları zorunlu |
| Public S3 bucket | CSPM + denetim |
| Default IAM yetkili tüm kullanıcı | Least privilege |
| Audit log devre dışı | Tüm sağlayıcılarda etkin |
| Çıkış planı yok | Vendor lock-in azaltma |
| Şirket içi politika yok | Bulut kullanım politikası şart |
| Shadow IT envanteri yok | CASB + onay süreci |
| TIA yapılmamış | Yurt dışı aktarım öncesi zorunlu |

## 14. KPI'lar

| KPI | Hedef |
|-----|-------|
| Bulut sağlayıcılarda KVKK DPA imzalı | %100 |
| Standart Sözleşme bildirim SLA | < 5 iş günü |
| MFA kapsam (bulut) | %100 |
| CMK aktif (kritik veri) | %100 |
| Audit log toplama | %100 |
| Region uyum (kritik veri) | Türkiye/AB %100 |
| CSPM bulgusu kapanma | < 30 gün |
| TIA tamamlanma | %100 yurt dışı aktarım |
| Yıllık bulut denetim | %100 |

## 15. Bağlantılı Bölümler

- `05-teknik-tedbirler/` — Bulut güvenlik kontrolleri.
- `07-aktarim/` — Yurt dışı aktarım hukuku.
- `08-ihlal-yonetimi/` — Bulut sağlayıcı ihlali müdahale.

## 16. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi + CTO |
