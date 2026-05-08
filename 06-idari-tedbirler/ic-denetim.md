---
Doküman: KVKK ve Bilgi Güvenliği İç Denetim Standardı
Bölüm: 06-idari-tedbirler
Sahip: İç Denetim Yöneticisi / Denetim Komitesi
Onaylayan: Denetim Komitesi + Yönetim Kurulu
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık
İlgili Mevzuat: 6698 sayılı KVKK m.12 (uyum yükümlülüğü); KVKK Veri Güvenliği Rehberi — "Kurum İçi Periyodik ve/veya Rastgele Denetimler"; Sermaye Piyasası Kurulu denetim ve ihaleli denetim çerçeveleri (uygulanabildiğinde); BDDK / SPK iç denetim mevzuatı (sektörel)
İlgili Standart: ISO/IEC 27001:2022 Clause 9.2 (Internal Audit), Clause 9.3 (Management Review); ISO/IEC 27701:2019; ISO 19011:2018 (Auditing Management Systems); IIA — Institute of Internal Auditors Standards (IPPF); COBIT; NIST CSF 2.0 GV.OV (Oversight); ISACA IS Audit Standards
---

# İç Denetim — KVKK ve Bilgi Güvenliği

## 1. Amaç

KVKK ve bilgi güvenliği uyumunun **tasarlandığı gibi işlediğini** bağımsız ve sistematik biçimde doğrulamak; eksiklikleri ortaya çıkarmak; düzeltici-önleyici aksiyonları (CAPA) takip etmek; yönetime ve KVKK Komitesi'ne güvence sağlamak. KVKK Veri Güvenliği Rehberi'nin "Kurum İçi Periyodik Denetim" tedbirinin operasyonel ayağıdır.

İç denetim **bağımsız ve nesnel**dir; iç denetçi denetlediği süreçten organizasyonel olarak ayrı raporlar (Denetim Komitesi / Yönetim Kurulu).

## 2. Yönetişim

### 2.1. Yapı

```
Yönetim Kurulu
   └── Denetim Komitesi (3+ bağımsız üye)
         └── İç Denetim Yöneticisi (CAE — Chief Audit Executive)
               └── İç Denetim Ekibi (KVKK / BT / Süreç denetçileri)
```

### 2.2. İç Denetim Tüzüğü

İç denetim tüzüğü, Yönetim Kurulu onaylı, asgari aşağıdakileri içerir:

- Misyon, kapsam, yetki.
- Bağımsızlık ve nesnellik.
- Kaynak (insan, bütçe).
- Erişim hakkı (her sistem, doküman, kişiye).
- Raporlama hattı.
- Standartlara uyum (IIA / ISO 19011).
- Yıllık plan ve raporlama yükümlülüğü.

### 2.3. Yetkinlikler

İç denetim ekibi yıllık geliştirme planı:

- KVKK / GDPR sertifikası (CIPP/E veya yerel benzeri).
- ISO 27001 LA / 27701 LI sertifikası.
- CISA (Certified Information Systems Auditor) / CIA (Certified Internal Auditor).
- Sektörel uzmanlık (bankacılık, sağlık vb.).

## 3. Yıllık İç Denetim Planı

### 3.1. Risk-Bazlı Plan

Yıllık plan, risk değerlendirmesi sonucuna göre hazırlanır:

- **Yüksek riskli alanlar:** yıllık tam denetim.
- **Orta riskli alanlar:** 2 yılda bir denetim.
- **Düşük riskli alanlar:** 3 yılda bir veya örnekleme.

### 3.2. Tipik Yıllık KVKK Denetim Konuları

| Konu | Sıklık |
|------|--------|
| KVKK Politikası ve doküman seti güncellik | Yıllık |
| Veri envanteri doğruluğu (örnekleme) | Yıllık |
| VERBİS kayıtlarının güncelliği | Yıllık |
| Aydınlatma metni saha kontrolü (web, başvuru, kayıt formu) | Yıllık |
| Açık rıza kayıt örneklemesi | Yıllık |
| Saklama ve İmha — periyodik imha tutanakları | Yıllık |
| İlgili kişi başvuru SLA (30 gün) | Yıllık |
| Veri ihlali kayıt sistemi ve 72 saat bildirim | Yıllık |
| Tedarikçi sözleşmeleri ve due diligence kanıtı | Yıllık |
| Yurt dışı aktarım dayanakları | Yıllık |
| DPIA kayıtları ve onay zinciri | Yıllık |
| Personel eğitim tamamlama kanıtı | Yıllık |
| Gizlilik taahhütname imza durumu | Yıllık |
| Çerez yönetim sistemi | 2 yılda bir |
| Pazarlama izinleri (İYS) | Yıllık |
| Özel nitelikli veri erişim audit | Yıllık |
| Otomatik karar süreçleri | Yıllık |

### 3.3. Tipik Yıllık Bilgi Güvenliği Denetim Konuları

| Konu | Sıklık |
|------|--------|
| Erişim yönetimi (IAM, JML, RBAC, çeyreklik review) | Yıllık |
| Kimlik doğrulama (MFA kapsamı, parola, SSO) | Yıllık |
| Şifreleme (algoritma, anahtar yönetimi, HSM/KMS) | Yıllık |
| Ağ güvenliği (segmentasyon, FW kuralları, perimeter) | Yıllık |
| Log yönetimi ve SIEM kapsamı | Yıllık |
| Yedekleme ve restore tatbikatı | Yıllık |
| Veri maskeleme / test ortamı | Yıllık |
| DLP ve sızıntı önleme | Yıllık |
| Uygulama güvenliği (S-SDLC, SAST/DAST, sızma testi) | Yıllık |
| BCP / DR tatbikat | Yıllık |
| Olay yönetimi (IR runbook, KPI) | Yıllık |
| Bulut güvenliği (CSPM, IAM, public bucket) | Yıllık |
| Endpoint ve mobil güvenlik | Yıllık |
| Patch yönetimi SLA | Yıllık |
| Fiziksel güvenlik (veri merkezi, ofis) | 2 yılda bir |
| Tedarikçi denetim hakkı kullanımı | Yıllık |

### 3.4. Yıllık Plan Onay

- CAE plan taslağını hazırlar.
- KVKK Sorumlusu, CISO, BT Direktörü, Hukuk görüş bildirir.
- Denetim Komitesi onaylar.
- Yönetim Kurulu bilgilendirilir.

## 4. Denetim Sürecinin Adımları

### 4.1. Planlama

- Konu, kapsam, hedef, kriter, kaynak, takvim.
- Risk değerlendirme.
- Denetim soruları ve test prosedürü taslak.
- Etkilenen ekiplere ön bildirim (rastgele/spot denetim hariç).

### 4.2. Saha Çalışması (Fieldwork)

- Doküman incelemesi.
- Görüşmeler (interview).
- Sistem inceleme (uygulama, log, konfig).
- Örnekleme (random / risk-bazlı).
- Test prosedürü uygulama.
- Bulgu / kanıt toplama.

### 4.3. Raporlama

- Bulgular kategorize edilir.
- Kök neden analizi.
- Risk değerlendirmesi.
- Düzeltici ve önleyici aksiyon önerisi.
- Süreç sahibi cevabı (yönetim cevabı).
- Rapor formal yayını.

### 4.4. Takip (Follow-up)

- CAPA aksiyon planı kayıt.
- Aylık / çeyreklik takip.
- Aksiyon kapanma sonrası doğrulama.
- Açık aksiyonların Denetim Komitesi'ne raporlanması.

## 5. Test Prosedürleri (Örnekler)

### 5.1. Veri Envanteri Doğruluğu

**Hedef:** Envanterin gerçek işleme faaliyetlerini doğru yansıttığını doğrulamak.

**Test:**
1. Envanterden 20 kayıt rastgele seçilir.
2. Her kayıt için süreç sahibiyle görüşme.
3. Kayıt vs. gerçek faaliyet karşılaştırması:
   - Veri kategorileri doğru mu?
   - Saklama süresi pratikte uygulanıyor mu?
   - Aktarımlar listelenenle uyumlu mu?
   - Hukuki dayanak halen geçerli mi?
4. Üretimden 10 kayıt rastgele seçilir, hangi süreçte oluştuğu envanterle eşleştirilir; envanter dışı süreç var mı?

**Bulgu örnekleri:**
- "Pazarlama otomasyon CRM'i envanterde yok ama aktif kullanılıyor."
- "Sağlık verisi envantere `genel kişisel veri` olarak işlenmiş, özel nitelikli flag'i konmamış."
- "Saklama süresi 2 yıl yazılı, gerçekte 5 yıldır silinmiyor."

### 5.2. Aydınlatma Metni Saha Kontrolü

**Test:**
1. Web sitesi ana sayfa, kayıt formu, ödeme, çerez banner — aydınlatma erişilebilir mi?
2. Aydınlatma metni m.10 unsurlarını içeriyor mu (kimlik, amaç, hukuki sebep, aktarım, haklar)?
3. Mobil uygulama içinde aydınlatma var mı?
4. Çağrı merkezi başlangıç anonsu KVKK aydınlatma içeriyor mu?
5. Fiziksel form (mağaza, etkinlik) aydınlatma metni içeriyor mu?

### 5.3. Açık Rıza Kayıt Örneklemesi

**Test:**
1. Son 3 ayda alınan 30 açık rıza rastgele seçilir.
2. Her biri için:
   - Rıza zaman damgası, IP, kullanıcı agent kayıtlı mı?
   - Rıza özgür mü (paket/koşul yok)?
   - Rıza belirli mi (amaç-spesifik)?
   - Aydınlatma rıza öncesi gösterilmiş mi?
   - Geri çekme aynı kolaylıkta mı?
3. Geri çekme talebinin kayıttaki uygulanma süresi ölçülür.

### 5.4. Tedarikçi Sözleşmesi Review

**Test:**
1. Sınıf A/B tedarikçilerden 10 sözleşme örneklenir.
2. Her sözleşme için:
   - Veri İşleyen sözleşmesi imzalı mı?
   - Asgari unsurlar (talimat, gizlilik, alt-işleyen, ihlal bildirim, denetim, fesih) var mı?
   - Yurt dışı aktarım mekanizması belirli mi?
   - Yıllık SOC 2 / ISO 27001 raporu alınmış mı?
3. Sözleşme + uygulama tutarlılık (örn. alt-işleyen listesi sözleşme eki ile gerçek tedarikçi kayıt eşleşmesi).

### 5.5. Periyodik İmha Tutanakları

**Test:**
1. Saklama ve İmha Politikası'na göre belirlenmiş çeyreklik imha dönemi (Ocak / Nisan / Temmuz / Ekim).
2. Son 4 dönemin imha tutanakları:
   - İmza zinciri (sahip + tanık + KVKK Sorumlusu).
   - İmha edilen kayıt sayısı, kategori.
   - İmha yöntemi (silme / yok etme / anonim).
   - Yedeklerden imha akışı.
3. Crypto-shred kullanılıyorsa anahtar zeroize tutanağı.

### 5.6. İlgili Kişi Başvuru SLA

**Test:**
1. Son 12 ayda gelen başvurular kaydı (KVKK Sorumlusu CRM).
2. 20 başvuru rastgele:
   - Başvuru tarihi → cevap tarihi süresi.
   - 30 gün SLA aşıldı mı?
   - Cevap m.13 unsurlarını içeriyor mu?
   - Reddedilen başvuru gerekçesi yasal mı?
   - Başvuru kanıtı / belge zinciri tam mı?

### 5.7. Veri İhlali Kayıt Sistemi

**Test:**
1. Son 12 ayda kayıtlı ihlal/ramak kala olayları.
2. Her olay için:
   - Tespit zamanı → KVKK Komitesi bildirim → 72 saat Kurul bildirim zinciri.
   - 72 saat aşıldıysa gerekçe makul mü?
   - Etkilenen ilgili kişiye bildirim yapıldı mı (gerekiyorsa)?
   - Kök neden analizi + lessons learned dokümante mi?
3. Ramak kala olayların raporlanma kültürü değerlendirilir.

### 5.8. MFA Kapsam Doğrulama

**Test:**
1. IdP'den admin / kişisel veri uygulama erişen kullanıcı listesi.
2. Her kullanıcının MFA kayıt durumu.
3. MFA registered ≠ MFA enforced — politika gerçekten aktif mi?
4. SMS OTP kullanan ama yönetici olan kullanıcı var mı?

### 5.9. Test Ortamı Üretim Verisi Taraması

**Test:**
1. DLP discovery aracıyla test/dev veritabanları + storage taraması.
2. TC kimlik / IBAN / kart no regex eşleşmesi var mı?
3. Eşleşmeler için kök neden + remediation süresi.

### 5.10. Eğitim Kanıtı

**Test:**
1. LMS rapor: yıllık tazeleme tamamlama oranı.
2. 30 yeni başlayan rastgele:
   - Onboarding eğitim tamamlandı mı (ilk 7 gün)?
   - Gizlilik taahhütnamesi imzalı mı?
   - Bilgi testi başarı (≥%80)?

## 6. Bulgu Sınıflandırması

| Sınıf | Tanım | Aksiyon SLA |
|-------|-------|-------------|
| **Kritik** | Mevzuat ihlali, kişisel veri sızıntısı riski yüksek, ciddi finansal/itibar kaybı | 30 gün |
| **Yüksek** | Önemli kontrol eksikliği, KVKK uyum etkisi orta-yüksek | 60 gün |
| **Orta** | Kontrol etkinliğinde iyileştirme gerekli | 90 gün |
| **Düşük** | İyi uygulama önerisi, fırsat | 180 gün |

## 7. Rapor Formatı

### 7.1. Standart Rapor Bölümleri

1. **Yönetici Özeti** (1 sayfa) — kapsam, dönem, sonuç, kritik bulgular.
2. **Denetim Bilgisi** — kapsam, kriter, dönem, ekip.
3. **Metodoloji** — örnekleme, test prosedürü.
4. **Bulgular** — her bulgu için: bulgu, kök neden, risk, kanıt, öneri, yönetim cevabı.
5. **Olumlu Gözlemler** — iyi uygulamalar.
6. **Yıllık Trend** — önceki yıla göre ilerleme.
7. **Sonuç ve Genel Değerlendirme** — uyum seviyesi, olgunluk skoru.
8. **Ekler** — kanıt referansları (gizli, paydaşa özel).

### 7.2. Bulgu Şablonu

```
Bulgu No: KVKK-2026-001
Sınıf: Yüksek
Süreç: Aydınlatma Yönetimi
Bulgu: Web sitesi mobil görünümünde aydınlatma metni linki hidden menü altında, 
       ilgili kişinin erişimi pratik olarak engelleniyor.
Kök Neden: Mobil tasarım güncellemesinde KVKK Sorumlusu review akışına dahil edilmemiş.
Risk: KVKK m.10 aydınlatma yükümlülüğü, AB GDPR Art. 12 (şeffaflık).
Kanıt: Ekran görüntüleri (Ek-3), test cihazı listesi.
Öneri: 
   1. Aydınlatma metni tüm görünümlerde max 2 dokunuşla erişilebilir olmalı.
   2. Tasarım değişikliklerinde KVKK Sorumlusu review zorunlu CI gate.
Yönetim Cevabı (Pazarlama Direktörü):
   "Mobil tasarımda link footer'a taşınacak. CI gate Q3'te eklenecek.
    Aksiyon Sahibi: <isim>. Tarih: <tarih>."
Hedef Kapanış: <tarih>
Doğrulama: Re-test, ekran görüntüsü kanıtı.
```

## 8. CAPA (Corrective and Preventive Action) Takibi

- Her bulguya bir CAPA açılır.
- ITSM / GRC aracında (ServiceNow, Archer, OneTrust, vs.) tutulur.
- Aksiyon sahibi, hedef tarihi, ilerleme yüzdesi, doğrulama kanıtı.
- Aylık raporlama.
- 90 gün geçmiş açık kritik aksiyon Denetim Komitesi'ne eskalasyon.
- Tekrarlayan bulgular için **kök neden tekrarı** analizi.

## 9. Dış Denetim ile İlişki

### 9.1. Sertifikasyon Denetimi

- ISO 27001 sertifikasyonu yıllık gözetim + 3 yılda bir yeniden belgelendirme.
- ISO 27701 (PIMS) opsiyonel, KVKK uyumunu güçlendirir.
- SOC 2 Type II — uluslararası B2B müşteriler için kanıt değeri.

### 9.2. Sektörel Denetim

- BDDK denetimi (bankacılık).
- SPK denetimi (halka açık şirketler).
- Sağlık Bakanlığı denetimi (sağlık sektörü).
- KVKK Kurum denetimi (her sektör; risk-bazlı).

### 9.3. Müşteri Denetimi

- Kurumsal müşteriler "vendor security questionnaire" gönderir veya saha denetimi yapar.
- Bu denetimlere hazırlık için iç denetim raporları kanıt olarak kullanılır.

### 9.4. Bağımsız KVKK Denetimi

- Bağımsız hukuk büroları / danışmanlık şirketleri (OneTrust, BSI, Deloitte, PwC, KPMG, EY) yıllık KVKK uyum denetimi sağlayabilir.
- İç denetim sonuçlarıyla karşılaştırma → güvence güçlenir.
- Maliyet-fayda analizi yıllık değerlendirilir.

## 10. Yönetim Raporu Şablonu

KVKK Komitesi ve Yönetim Kurulu'na yıllık üst düzey raporun temel içeriği:

```
1. KAPSAM
   - Denetim Yılı: 2026
   - Denetlenen Süreçler: 14
   - Toplam Adam-Gün: 320
   - Bulgu Sayısı: 47 (Kritik 3, Yüksek 11, Orta 24, Düşük 9)

2. UYUM SEVİYESİ
   - KVKK Uyum Olgunluk Skoru: 78/100 (Yetkin)
   - Önceki Yıl: 72/100 (+6 puan)
   - Hedef: 85/100 (2027)

3. KRİTİK BULGULARIN ÖZETİ
   3.1. <bulgu>
   3.2. <bulgu>
   3.3. <bulgu>

4. AKSİYON DURUMU
   - Açık Aksiyon: 18
   - Bu Yıl Kapanan: 41
   - 90 Gün Geçmiş Açık: 2 (eskalasyon edildi)

5. SEKTÖREL VE MEVZUAT TRENDLERİ

6. RİSK PROFİLİ DEĞİŞİMİ

7. TAVSİYELER (ÜST YÖNETİM İÇİN)

8. GELECEK YIL PLAN
```

## 11. Olgunluk Modeli

| Seviye | Tanım |
|--------|-------|
| 1 — Başlangıç | Ad-hoc, doğrudan ihlale tepki |
| 2 — Tekrarlanabilir | Bazı süreçler dokümanlı, kişiye bağlı |
| 3 — Tanımlı | Politikalar yazılı, denetim yapılır |
| 4 — Yönetilen | KPI'lar ölçülür, sürekli iyileştirme |
| 5 — Optimize | Öngörücü kontrol, otomasyon yaygın |

Hedef: 2 yıl içinde Seviye 4 (Yönetilen).

## 12. Bağımsızlık ve Etik

- İç denetçi, denetlediği süreçten organizasyonel olarak ayrı.
- Çıkar çatışması beyanı yıllık.
- Hediye / faydacılık politikası.
- IIA Etik Kuralları'na bağlı.
- Whistleblower hattı denetim dışı yönetilir; ancak bulguları kayda alınabilir.

## 13. Kontrol Listesi

- [ ] İç Denetim Tüzüğü onaylı, ≤24 ay güncel mi?
- [ ] Yıllık denetim planı risk-bazlı, Denetim Komitesi onaylı mı?
- [ ] CAE bağımsız raporlama hattına sahip mi?
- [ ] Ekip yetkinliği (sertifika, deneyim) yeterli mi?
- [ ] §3.2 ve §3.3'teki konular yıllık plana dahil mi?
- [ ] Test prosedürleri yazılı, standartlaşmış mı?
- [ ] Bulgu sınıflandırması ve SLA tanımlı mı?
- [ ] Rapor şablonu standart, yönetim cevap mekanizması işliyor mu?
- [ ] CAPA aracı tüm aksiyonları takip ediyor mu?
- [ ] 90 gün geçmiş kritik aksiyon Denetim Komitesi'ne eskalasyon ediliyor mu?
- [ ] Yıllık yönetim raporu hazırlanıyor mu?
- [ ] Dış denetim (ISO, SOC, KVKK) ile koordinasyon mekanizması var mı?
- [ ] Bağımsız KVKK uyum denetimi opsiyonu yıllık değerlendiriliyor mu?
- [ ] Olgunluk skoru ölçülüyor, yıllık trend takibi var mı?
- [ ] Tekrarlayan bulgular için kök neden tekrar analizi yapılıyor mu?
- [ ] Etik / çıkar çatışması beyanı yıllık alınıyor mu?

## 14. Yaygın Hatalar

- Denetim "evet/hayır" formuna indirgenmiş, kanıt zayıf.
- Örnekleme küçük (5 kayıt), istatistiksel olarak yetersiz.
- Yönetim cevabının doldurulmaması veya geçiştirilmesi.
- Aksiyonların kapanış kanıtı olmadan "kapatıldı" işaretlenmesi.
- Tekrarlayan aynı bulgu yıldan yıla, kök neden çözülmemiş.
- KVKK ve bilgi güvenliği denetimlerinin koordinasyonsuz yapılması.
- Sektörel ek mevzuatın denetim kapsamına alınmaması.
- Bağımsızlık ihlali (denetçi denetlediği alanda eski rolde).
- Dış denetim raporlarına gereğinden çok güvenip iç testin yapılmaması.
- Denetim sonuçlarının yalnızca formal raporda kalıp eğitim/iletişime dönmemesi.
