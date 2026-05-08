---
Doküman: Teknik Tedbirler — Denetim-Hazır Kontrol Listesi
Bölüm: 05-teknik-tedbirler
Sahip: İç Denetim / CISO
Onaylayan: BT Direktörü + KVKK Komitesi + Denetim Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (yeni mevzuat, yeni kontrol, denetim bulgusu)
İlgili Mevzuat: 6698 sayılı KVKK m.12; Kişisel Veri Güvenliği Rehberi — "Teknik Tedbirler Özet Tablosu"
İlgili Standart: ISO/IEC 27001:2022 Annex A; ISO/IEC 27002:2022; NIST CSF 2.0; CIS Controls v8
---

# Teknik Tedbirler Kontrol Listesi

## Kullanım

Bu liste; iç denetim örneklemesi, tedarikçi gözden geçirmesi, yıllık öz değerlendirme ve olay sonrası teknik kapsam kontrolünde **denetim-hazır** referanstır. Her satır şu şekilde değerlendirilir:

- **Durum:** Var / Yok / Kısmen / Uygulanamaz (gerekçe yazılır)
- **Kanıt:** Doküman, ekran görüntüsü, log örneği, ITSM ticket no, sözleşme maddesi
- **Sahibi:** Operasyonel sahip
- **Son Test:** Tarih + test türü
- **Sonraki Test:** Hedef tarih
- **Açıklama / Aksiyon:** Eksiklik varsa CAPA referansı

Doldurulmuş çalışma sayfası ayrı şablonda tutulur ([99-sablonlar/](../99-sablonlar/)). Bu doküman **kontrol kataloğudur**.

Eşleme: ISO 27002:2022 (A.x.y) ve NIST CSF 2.0 fonksiyon-kategori (örn. PR.AC).

---

## 1. Erişim Kontrolü ve Yetkilendirme (10 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 1.1 | Yazılı Erişim Kontrol Politikası mevcut, yıllık review tarihli | A.5.15 | GV.PO |
| 1.2 | Tüm hesaplar merkezi IdP üzerinden yönetiliyor (yerel hesap istisnaları envanterli) | A.5.16 | PR.AA-1 |
| 1.3 | RBAC rolleri tanımlı, sahibi belli, son review kaydı çeyrekliktir | A.5.18 | PR.AA-5 |
| 1.4 | "En az ayrıcalık" ilkesi uygulanmış, doğrudan kullanıcı yetkisi 0 | A.8.2 | PR.AA-5 |
| 1.5 | Joiner-Mover-Leaver SLA'ları (J -1g, M revoke ≤7g, L 0g) sağlanıyor | A.5.18 | PR.AA-1 |
| 1.6 | Çeyreklik erişim review kritik sistemlerde %100 tamamlanıyor | A.5.18 | PR.AA-5 |
| 1.7 | PAM kapsamı belgeli, oturum kaydı immutable | A.8.2 | PR.AA-2 |
| 1.8 | Break-glass hesapları MFA + audit + yıllık tatbikat | A.8.2 | PR.AA-2 |
| 1.9 | Servis hesapları sahipli, otomatik secret rotasyonu (≤90g) | A.8.5 | PR.AA-3 |
| 1.10 | DB satır seviyesi güvenlik (RLS) / view tabanlı erişim kişisel veri tablolarında | A.8.3 | PR.AA-5 |

## 2. Kimlik Doğrulama (10 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 2.1 | Kimlik Doğrulama Politikası NIST 800-63B uyumlu | A.5.17, A.8.5 | PR.AA-3 |
| 2.2 | MFA: yönetici, uzaktan erişim, kişisel veri uygulamaları %100 | A.8.5 | PR.AA-3 |
| 2.3 | Phishing-resistant MFA (FIDO2 / authenticator + number matching) yöneticide zorunlu | A.8.5 | PR.AA-3 |
| 2.4 | SMS OTP yönetici / kritik / uzaktan için kapalı | A.8.5 | PR.AA-3 |
| 2.5 | Parola hash algoritması Argon2id / bcrypt(≥12) | A.8.24 | PR.DS-1 |
| 2.6 | Parola breach kontrol (HIBP / offline corpus) entegre | A.8.5 | PR.AA-3 |
| 2.7 | Hesap kilitleme + brute-force koruma kuralları aktif | A.8.5 | PR.AA-3 |
| 2.8 | SSO kapsamı uygulama envanterinin %95+ | A.8.5 | PR.AA-1 |
| 2.9 | Cihaz uyumluluk (compliant/healthy) kişisel veri uygulamasında zorunlu | A.5.16 | PR.AA-6 |
| 2.10 | Oturum timeout 15 dk (kişisel veri) / 60 dk (genel) uygulanıyor | A.8.5 | PR.AA-3 |

## 3. Şifreleme ve Anahtar Yönetimi (10 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 3.1 | Yazılı Şifreleme Politikası, onaylı algoritma listesi yıllık güncel | A.8.24 | PR.DS-1, PR.DS-2 |
| 3.2 | Tüm dizüstü/mobil disk şifreli (FDE) MDM ile zorunlu | A.7.10 | PR.DS-1 |
| 3.3 | Sunucu disk + DB TDE + kritik alan-seviyesi şifreleme | A.8.24 | PR.DS-1 |
| 3.4 | TLS 1.2+ (1.3 tercih), zayıf cipher kapalı, HSTS aktif | A.8.24 | PR.DS-2 |
| 3.5 | mTLS dahili kişisel veri trafiğinde uygulanıyor | A.8.24 | PR.DS-2 |
| 3.6 | Anahtarlar HSM/KMS'de, kod içinde sır yok | A.8.24 | PR.DS-1 |
| 3.7 | Envelope encryption (KEK/DEK) hiyerarşisi | A.8.24 | PR.DS-1 |
| 3.8 | Anahtar rotasyon takvimi otomatik, son rotasyon kanıtlı | A.8.24 | PR.DS-1 |
| 3.9 | Görev ayrılığı: anahtar üretim/kullanım/audit ayrı kişiler | A.8.24 | PR.AA-5 |
| 3.10 | PQC yol haritası tanımlı, hibrit pilot başlatıldı | A.8.24 | GV.SC |

## 4. Ağ Güvenliği (10 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 4.1 | Ağ segmentasyonu — kişisel veri segmenti ayrılmış | A.8.22 | PR.IR-1 |
| 4.2 | Default deny + whitelist, mikrosegmentasyon (uygulama-kimlik bazlı) | A.8.22 | PR.IR-1 |
| 4.3 | NGFW HA, kurallar sahipli, yıllık temizlik | A.8.20 | PR.IR-1 |
| 4.4 | WAF "prevent" modunda, OWASP CRS uygulanıyor | A.8.21 | PR.PS-1 |
| 4.5 | DDoS koruması canlı + yıllık tatbikat | A.5.30 | PR.IR-3 |
| 4.6 | IDS/IPS inline kritik segment giriş/çıkışında | A.8.16 | DE.CM-1 |
| 4.7 | NDR / EDR tüm sunucu ve endpoint'te | A.8.16 | DE.CM-3 |
| 4.8 | Uzaktan erişim MFA + cihaz uyumlu + ZTNA / sıkı VPN | A.8.20 | PR.AA-3 |
| 4.9 | DNS filtering + DoH proxy + DNS log SIEM'e | A.8.23 | DE.CM-1 |
| 4.10 | Yıllık iç + dış sızma testi, segmentasyon doğrulanmış | A.8.29 | ID.RA-1 |

## 5. Log Yönetimi ve İzleme (10 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 5.1 | Log Yönetimi Politikası yazılı, kapsam tanımlı | A.8.15 | DE.AE-3 |
| 5.2 | Tüm kritik kaynaklar SIEM'e log gönderiyor (kapsam ≥%95) | A.8.15 | DE.AE-3 |
| 5.3 | Log içeriği kişisel veri minimize (PII redaction tarama) | A.8.15 | PR.DS-2 |
| 5.4 | Log bütünlüğü WORM + hash zinciri | A.8.15 | DE.AE-7 |
| 5.5 | NTP senkron, ≤100ms tolerans tüm sistemlerde | A.8.15 | DE.AE-3 |
| 5.6 | Log akış kesilmesi alarmı ≤5 dk | A.8.16 | DE.CM-1 |
| 5.7 | Saklama süresi mevzuat + KVKK uyumlu, otomatik imha | A.8.15 | GV.OC-3 |
| 5.8 | SOC 7/24 + eskalasyon zinciri yazılı, KVKK Sorumlusu IR ekibinde | A.5.24 | RS.MA-1 |
| 5.9 | Runbook'lar yıllık güncel, tatbikatla doğrulanmış | A.5.26 | RS.MA-2 |
| 5.10 | UEBA + threat intel SIEM ile entegre | A.5.7 | DE.AE-2 |

## 6. Yedekleme ve Kurtarma (10 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 6.1 | Yedekleme Politikası yazılı, RPO/RTO BIA ile onaylı | A.8.13 | RC.RP-1 |
| 6.2 | 3-2-1-1-0 kuralı uygulanıyor (immutable / air-gap kopya kanıtlı) | A.8.13 | PR.DS-11 |
| 6.3 | Yedek şifreli, ayrı KEK / ayrı IAM domain | A.8.13 | PR.DS-1 |
| 6.4 | Yedek anahtar M-of-N + offline kasa | A.8.24 | PR.DS-1 |
| 6.5 | Çeyreklik restore tatbikatı, kanıt arşivli | A.8.13 | RC.RP-1 |
| 6.6 | Yıllık DR site geçiş tatbikatı | A.5.30 | RC.RP-1 |
| 6.7 | Yıllık ransomware kurtarma tatbikatı | A.5.30 | RC.RP-1 |
| 6.8 | DR site farklı bölge / coğrafyada | A.5.30 | RC.RP-1 |
| 6.9 | SaaS verileri için 3rd party backup | A.5.23 | PR.DS-11 |
| 6.10 | KVKK silme talebinin yedeğe yansıma süreci yazılı | A.8.13 | GV.OC-3 |

## 7. Veri Maskeleme ve Anonimleştirme (8 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 7.1 | Test/dev ortamlarında ham üretim verisi yok (DLP discovery doğrulamalı) | A.8.11 | PR.DS-2 |
| 7.2 | Maskeleme pipeline kod / config repo'da, versiyonlu | A.8.11 | PR.DS-2 |
| 7.3 | Yeni alan eklendiğinde classification + masking rule CI gate | A.8.11 | PR.DS-2 |
| 7.4 | UI varsayılan maskeli, "doğrula" audit'li | A.8.11 | PR.DS-2 |
| 7.5 | Tokenization vault HSM korumalı | A.8.24 | PR.DS-1 |
| 7.6 | Pseudonymization mapping ayrı, korumalı, audit'li | A.8.11 | PR.DS-2 |
| 7.7 | Anonim yayın öncesi formel re-identification risk değerlendirmesi | A.8.11 | GV.RM |
| 7.8 | k-anon / DP parametreleri ve onay zinciri kayıtlı | A.8.11 | GV.RM |

## 8. DLP (8 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 8.1 | Veri sınıflandırma + sensitivity label kullanımı yaygın | A.5.12 | ID.AM-7 |
| 8.2 | Discovery taraması aylık, kapsam %95+ | A.8.12 | ID.AM-7 |
| 8.3 | Endpoint + Network + E-posta + CASB DLP entegre tek konsol | A.8.12 | DE.CM-3 |
| 8.4 | PCI / özel nitelikli için "block everywhere" politikası | A.8.12 | PR.DS-2 |
| 8.5 | Çalışan Aydınlatma Metni DLP kapsamını listeliyor, yıllık imzalı | A.5.32 | GV.OC |
| 8.6 | False positive ≤%20, aylık tunning raporu | A.8.12 | DE.AE-3 |
| 8.7 | DLP olay 4-eyes review (CISO + İK + Hukuk) | A.5.34 | RS.AN |
| 8.8 | Yıllık red team data exfil tatbikatı, tespit oranı ≥%85 | A.8.29 | DE.DP |

## 9. Uygulama Güvenliği (12 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 9.1 | S-SDLC politikası yazılı, ASVS seviyesi proje gereksiniminde | A.8.25 | PR.PS-6 |
| 9.2 | Yeni proje DPIA + tehdit modeli ile başlıyor | A.8.27 | GV.RM |
| 9.3 | CI'da SAST + SCA + secret + container + IaC scan zorunlu | A.8.29 | PR.PS-6 |
| 9.4 | DAST staging gece koşumu | A.8.29 | DE.CM-9 |
| 9.5 | Critical / High build fail; patch SLA (kritik 7g, yüksek 30g) | A.8.8 | RS.MI |
| 9.6 | SBOM her release için üretiliyor | A.8.30 | PR.PS-1 |
| 9.7 | Sırlar kasada, kodda yok; pre-commit secret scanning | A.8.24 | PR.AA-3 |
| 9.8 | API envanter güncel, shadow API tarama | A.8.26 | ID.AM-1 |
| 9.9 | BOLA / BOPLA testi yapılmış, endpoint başına authz | A.8.26 | PR.AA-5 |
| 9.10 | HTTP security headers tam set (CSP, HSTS, vd.) | A.8.26 | PR.PS-1 |
| 9.11 | Üretim/Test/Dev ayrımı net, geliştirici prod erişimi 0 | A.8.31 | PR.AA-5 |
| 9.12 | Yeni AI özelliği için LLM Top 10 + DPIA + ek aydınlatma | A.5.34 | GV.RM |

## 10. Endpoint, Cihaz ve Mobil (8 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 10.1 | MDM tüm kurumsal cihazları kayıt + politika uygulama | A.8.1 | PR.PS-1 |
| 10.2 | EDR tüm sunucu + endpoint, SOC izlemesinde | A.8.7, A.8.16 | DE.CM-3 |
| 10.3 | Disk şifreleme (FDE) zorunlu, MDM doğrulama | A.7.10 | PR.DS-1 |
| 10.4 | Patch yönetimi: kritik 7g, yüksek 30g, raporlu | A.8.8 | PR.PS-1 |
| 10.5 | USB / removable kontrol, DLP ile entegre | A.7.10, A.8.12 | PR.DS-2 |
| 10.6 | BYOD politikası — kişisel cihazda iş profili izole | A.7.9 | GV.PO |
| 10.7 | Yerel admin parolası LAPS / unique-per-host | A.5.17 | PR.AA-3 |
| 10.8 | Kayıp/çalıntı cihaz remote wipe + selektif iş profili wipe | A.7.10 | RC.RP |

## 11. Bulut ve Tedarikçi Teknolojisi (6 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 11.1 | Cloud config drift CSPM ile takip, public bucket / port 0 | A.5.23 | DE.CM-1 |
| 11.2 | KMS müşteri-yönetimli anahtar (CMK / BYOK) yüksek hassasiyet için | A.8.24 | PR.DS-1 |
| 11.3 | Private endpoint kişisel veri PaaS'larda zorunlu | A.5.23 | PR.IR-1 |
| 11.4 | Cloud audit log (CloudTrail / Activity Log / Audit Logs) SIEM'e | A.8.15 | DE.AE-3 |
| 11.5 | IAM: human ≠ service, MFA zorunlu, MAU review | A.5.18 | PR.AA-5 |
| 11.6 | Tedarikçi SaaS API tabanlı CASB ile audit edilebilir | A.5.23 | DE.CM-3 |

## 12. Olay Yönetimi (Teknik Boyut) (6 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 12.1 | IR runbook'ları (RB-01..RB-12) güncel, tatbikatlı | A.5.26 | RS.MA-2 |
| 12.2 | Forensic kanıt zinciri prosedürü hazır | A.5.28 | RS.AN-3 |
| 12.3 | KVKK Komitesi 24 saat eşik bildirimi yazılı | A.5.24 | GV.RM |
| 12.4 | Atomic Red Team / purple team yıllık, MITRE ATT&CK kapsamı | A.8.29 | DE.DP |
| 12.5 | Kritik alarm kataloğu KVKK ihlal eşiklerini içerir | A.5.25 | RS.AN-1 |
| 12.6 | İhlal sonrası lessons learned kontrole geri besliyor | A.5.27 | ID.IM |

---

## Toplam Madde Sayısı: 88

## Değerlendirme Skoru

Her madde için: Var=2, Kısmen=1, Yok=0, Uygulanamaz=hariç.

| Olgunluk | Aralık |
|----------|--------|
| **Düşük** | < 60% |
| **Gelişmekte** | 60-75% |
| **Yetkin** | 75-85% |
| **İleri** | 85-95% |
| **Optimize** | > 95% |

Hedef: **Yetkin (≥75%)** birinci yıl, **İleri (≥85%)** ikinci yıl.

## Aksiyon Planı

Her **Yok** veya **Kısmen** satırı için:

1. CAPA (Corrective and Preventive Action) açılır.
2. Sahibi, hedef tarihi, kanıt belgesi atanır.
3. KVKK Komitesi'ne çeyreklik raporda durumu raporlanır.
4. Kritik eksiklikler (örn. MFA yokluğu, log kesintisi, yedek başarısızlığı) için **30 gün** SLA.

## Yıllık Öz-Değerlendirme Akışı

1. CISO ofisi liste üzerinde kanıt toplama görev planı çıkarır (Q1).
2. Her sahip kanıt yükler (Q1 sonu).
3. İç Denetim örnekleme yapar, doğrular (Q2).
4. Bulgular CAPA'ya işlenir.
5. KVKK Komitesi'ne yıllık özet rapor (Q3).
6. Yönetim Kurulu'na yıllık güvenlik durum raporu (Q4).

## Dış Denetim ile İlişki

- ISO 27001 sertifikası varsa: bu liste, ISO Annex A'nın KVKK genişletmesi olarak iç denetim kapsamını oluşturur.
- ISO 27701 (PIMS) sertifikasına yönelinirse: A.7.x ve A.8.x ek kontrolleriyle eşlemesi yapılmıştır.
- KVKK Kurum denetimi: bu liste, talep edilen "uygulanan tedbirler" beyanının operasyonel kanıt setidir.
