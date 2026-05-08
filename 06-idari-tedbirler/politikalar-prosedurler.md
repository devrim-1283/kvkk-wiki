---
Doküman: Politikalar ve Prosedürler — Doküman Yönetimi Standardı
Bölüm: 06-idari-tedbirler
Sahip: KVKK Sorumlusu / CISO (Bilgi Güvenliği Politikaları için)
Onaylayan: KVKK Komitesi + İlgili Direktör + Üst Yönetim (üst seviye için Yönetim Kurulu)
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş (mevzuat değişikliği, organizasyonel değişim, ihlal)
İlgili Mevzuat: 6698 sayılı KVKK m.12; KVKK Veri Güvenliği Rehberi — "Kurumsal Politikalar"
İlgili Standart: ISO/IEC 27001:2022 Clause 5.2 (Policy), 7.5 (Documented Information), Annex A.5.1, A.5.2; ISO/IEC 27701:2019; NIST CSF 2.0 GV.PO; NIST SP 800-53 PM-1
---

# Politikalar ve Prosedürler

## 1. Amaç

Kurumun KVKK uyumu ve bilgi güvenliği için sahip olması gereken **politika setini**, **doküman yaşam döngüsünü**, **onay zincirini** ve **yayınlama/erişim** kurallarını tanımlar. KVKK Veri Güvenliği Rehberi'nde "Kurumsal Politikalar" başlığı altında talep edilen tedbirin operasyonel uygulamasıdır.

## 2. Doküman Tipleri ve Hiyerarşi

| Seviye | Tip | Örnek | Onaylayan | Süre |
|--------|-----|-------|-----------|------|
| 1 | Üst Düzey Politika (Charter / Manifesto) | KVKK Politikası, Bilgi Güvenliği Politikası | Yönetim Kurulu | 2 yıl |
| 2 | Politika | Erişim Yönetimi, Saklama, Tedarikçi | Üst Yönetim + KVKK Komitesi | 2 yıl |
| 3 | Standart | Şifreleme Standardı, Loglama Standardı | Direktör + CISO | 1-2 yıl |
| 4 | Prosedür / Çalışma Talimatı | Joiner-Leaver İşlemi Prosedürü | Süreç Sahibi + KVKK Sorumlusu | 1 yıl |
| 5 | Şablon / Form / Kontrol Listesi | Veri İşleyen Sözleşme Şablonu | Hukuk + KVKK Sorumlusu | 1 yıl |

**Kural:** Alt seviye doküman, üst seviyeyle çelişemez. Çelişki bulunduğunda alt seviye revize edilir.

## 3. Asgari Politika Seti (Veri Sorumlusu — 500+ Çalışan)

### 3.1. Üst Düzey

1. **KVKK Politikası** — Şirketin kişisel veri işleme yaklaşımını, ilkelerini, sorumluluklarını ve ilgili kişi haklarını ortaya koyan üst düzey doküman.
2. **Bilgi Güvenliği Politikası** — CIA üçlüsü çerçevesinde kurumun yaklaşımı, sorumluluk, kabul edilebilir kullanım, uyum.

### 3.2. KVKK / Mahremiyet Odaklı

3. **Aydınlatma Metni Standardı** — m.10 yükümlülüğü için içerik, dil, yayın kanalı.
4. **Açık Rıza Yönetimi Politikası** — Rıza alma, kayıt, geri çekme süreçleri.
5. **Saklama ve İmha Politikası** — KVKK m.7 ve İmha Yönetmeliği uyumlu.
6. **İlgili Kişi Başvuru Yönetimi Prosedürü** — m.11/13 başvuru kanalı, kimlik doğrulama, SLA.
7. **Veri İhlali Yönetimi Prosedürü** — Tespit, sınırlama, bildirim, kayıt.
8. **Veri Aktarım Politikası** — Yurt içi ve yurt dışı aktarım kuralları, m.9.
9. **VERBİS Yönetimi Prosedürü** — Sicil güncel tutma sorumluluğu.
10. **Çerez Politikası** — Web sitesi çerezleri, kategorileri, opt-in/out.
11. **Pazarlama İletişimi Politikası** — KVKK + Elektronik Ticaret Kanunu (İYS) uyumlu.
12. **Çalışan Mahremiyet Politikası** — Çalışan verisinin işlenme şekli, izleme uygulamaları.
13. **CCTV / Kamera Politikası** — Görüntü kaydı amaç, süre, paylaşım.
14. **Kişisel Veri Etki Değerlendirmesi (DPIA) Standardı** — Ne zaman, nasıl yapılır.

### 3.3. Bilgi Güvenliği — Operasyonel

15. **Erişim Yönetimi Standardı** — RBAC, JML, PAM (bkz. [05-teknik-tedbirler/erisim-kontrolu.md](../05-teknik-tedbirler/erisim-kontrolu.md)).
16. **Kimlik Doğrulama Standardı** — MFA, parola, SSO.
17. **Şifreleme Standardı** — Algoritma, anahtar yönetimi.
18. **Ağ Güvenliği Standardı** — Segmentasyon, perimeter, ZTNA.
19. **Yedekleme ve İş Sürekliliği Standardı** — RPO/RTO, restore test.
20. **Log ve İzleme Standardı** — Logging, SIEM, saklama.
21. **DLP / Veri Sızıntısı Önleme Standardı**.
22. **Uygulama Güvenliği / S-SDLC Standardı**.
23. **Mobil ve Uzaktan Çalışma Politikası** — BYOD, MDM.
24. **Temiz Masa — Temiz Ekran Politikası** — Fiziksel mahremiyet.
25. **Sosyal Mühendislik ve Phishing Politikası** — Eğitim, simülasyon, raporlama.
26. **Olay Yönetimi (IR) Prosedürü** — RB-01..RB-12 runbook seti.
27. **Değişiklik Yönetimi Politikası** — CAB, acil değişiklik.
28. **Kabul Edilebilir Kullanım Politikası (AUP)** — Çalışan davranışı, internet, sosyal medya.

### 3.4. Tedarikçi ve Üçüncü Taraf

29. **Tedarikçi Yönetimi Politikası** — Sınıflandırma, due diligence, monitoring.
30. **Veri İşleyen Sözleşmesi Standart Maddeleri** — Asgari unsurlar, denetim hakkı.
31. **Bulut Hizmeti Kullanımı Politikası** — Onaylı sağlayıcı listesi, veri yerleşimi.

### 3.5. İK ve Eğitim

32. **İşe Alım ve Ayrılık Politikası (KVKK Bağlantısı)** — Özlük dosyası, gizlilik taahhütnamesi, ayrılışta erişim kapama.
33. **Personel Eğitim ve Farkındalık Programı** — Yıllık müfredat.
34. **Disiplin Politikası — Bilgi Güvenliği İhlalleri** — İhlal sınıfları ve yaptırım.

### 3.6. Yönetişim

35. **KVKK Komitesi Çalışma Esasları** — Üyeler, toplantı, karar.
36. **Risk Yönetimi Politikası** — Risk iştahı, skorlama.
37. **İç Denetim Tüzüğü ve Yıllık Plan** — Bağımsızlık, kapsam.
38. **Politika ve Doküman Yönetimi Politikası** — Bu doküman.

## 4. Politika Yaşam Döngüsü

```
Tetik (yeni risk / mevzuat / gap)
   → 1. Taslak (Sahip ekip)
   → 2. Paydaş Review (Hukuk, BT, İK, KVKK Sorumlusu, ilgili iş birimi)
   → 3. Üst Yönetim / Komite Onayı
   → 4. Yayınlama (intranet, e-posta duyuru, eğitim)
   → 5. Uygulama (operasyonel adımlar)
   → 6. İzleme & Ölçüm (KPI, denetim)
   → 7. Periyodik Review (≤2 yıl)
   → 8. Revizyon / Geri Çekme
```

## 5. Standart Politika Şablonu (Bölümler)

Her politika dokümanında aşağıdaki bölümler bulunur:

1. **Başlık + Meta Bilgi** (versiyon, sahip, onaylayan, yürürlük, gözden geçirme tarihi).
2. **Amaç** — Politikanın çözdüğü sorun.
3. **Kapsam** — Hangi kişiler, sistemler, lokasyonlar dahil.
4. **Tanımlar** — Tartışmalı / teknik terimler.
5. **Roller ve Sorumluluklar** — RACI.
6. **Politika Hükümleri** — Yapılması ve yapılmaması gerekenler.
7. **İstisnalar** — İstisna talep süreci.
8. **Ölçüm / KPI** — Etkinlik göstergeleri.
9. **Uyumsuzluk ve Yaptırım** — Disiplin sürecine atıf.
10. **İlgili Dokümanlar** — Üst/alt politikalar, mevzuat.
11. **Revizyon Geçmişi** — Tarih, değişiklik özeti, onaylayan.

## 6. Onay Zinciri

| Doküman Türü | Hazırlayan | Review (zorunlu) | Onaylayan | Yayın |
|--------------|------------|-------------------|------------|-------|
| Üst Düzey Politika | KVKK Sorumlusu / CISO | Hukuk + Tüm Komite + Üst Yön. | Yönetim Kurulu | İntranet + Genel duyuru |
| Politika (Seviye 2) | Sahip ekip | Hukuk + KVKK Sorumlusu + CISO + İlgili Direktör | KVKK Komitesi + Üst Yönetim | İntranet + e-posta |
| Standart | Teknik ekip + CISO ofisi | KVKK Sorumlusu + İlgili Direktör | CISO + İlgili Direktör | İntranet |
| Prosedür | Süreç Sahibi | Süreç paydaşları + KVKK Sorumlusu | İlgili Müdür | İntranet |
| Şablon / Form | Süreç Sahibi | Hukuk + KVKK Sorumlusu | KVKK Sorumlusu | İntranet |

Onay e-imza veya ıslak imza ile belgelenir; kanıt PDF + meta-data arşivde.

## 7. Yayınlama ve İletişim

- **Yayın Kanalı:** İntranet politika kütüphanesi (Confluence / SharePoint vb.) — tek yetkili kaynak.
- **Sürüm Bilgisi:** Her dokümanın başında ve dosya adında (örn. `KVKK-Politikasi-v2.0-2026.pdf`).
- **Yeni Yayın:** Şirket geneli e-posta + departman bazlı bildirim. Kritik politika için 30 dakikalık brifing.
- **Çevirisi:** Türkçe asli + İngilizce mevcut (uluslararası iştirakler için).
- **Erişilebilirlik:** Engelli erişim standartları (WCAG 2.1 AA) için yayın formatı düzenlenir.

## 8. Versiyonlama Kuralı

- **MAJOR.MINOR** (örn. 2.1).
- **MAJOR** — Politikanın amacı, kapsamı veya önemli hükmü değişti.
- **MINOR** — Açıklama, örnek, küçük revizyon.
- Yıllık review minor versiyon üretebilir.
- Her sürüm ayrı kayıt; geri dönülebilir.

## 9. Eski Sürüm Yönetimi

- Eski sürüm "ARŞİV" klasörüne taşınır, yeni sürüm yayınlanır.
- Çalışanların eski versiyona dayanarak hareket etmesi önlenir (eski sürüm açıkça "geçersiz" damgalı).
- Adli soruşturma / denetim olası hallerinde eski sürüm 5 yıl saklanır.
- Versiyon değişimini takip eden 30 gün içinde tüm çalışanların yeni versiyonu okudum onayı (kritik politika için).

## 10. Periyodik Review

### 10.1. Yıllık Tetikleyiciler

- Yasal değişiklik (KVKK, ikincil mevzuat, sektörel düzenleme).
- Kurumsal değişiklik (organizasyon, M&A, yeni iş kolu).
- Teknolojik değişiklik (yeni bulut, yeni IdP, yeni AI sistem).
- İhlal veya ramak kala olayı.
- Bağımsız denetim bulgusu.
- KVKK Kurulu kararı / sektörel rehber yenilenmesi.

### 10.2. Review Akışı

1. KVKK Sorumlusu yıllık takvim açıklar (Q1).
2. Her doküman sahibi kendi dokümanını review için açar.
3. Değişiklik gerekiyorsa taslak güncellenir, paydaş review.
4. Onay zinciri tetiklenir.
5. Yayın + iletişim.
6. Komite'ye review tamamlanma raporu.

## 11. İstisna Yönetimi

- İstisna **yazılı, gerekçeli, süreli, telafi edici kontrollü, onaylı** olabilir.
- İstisna formu: kim, neden, hangi madde, telafi edici kontrol, süre (≤180 gün), risk sahibi, KVKK Sorumlusu görüşü.
- İstisna defteri tutulur; yıllık review.
- İstisna birikimi politika revizyon ihtiyacına işaret eder.

## 12. Uyumsuzluk ve Yaptırım

- Uyumsuzluk Disiplin Politikası'na göre değerlendirilir.
- Sınıflandırma:
  - **A — Kasıtlı / Ağır:** Veri ifşası, kasıtlı erişim ihlali → fesih ve hukuki süreç dahil.
  - **B — İhmal / Tekrarlı:** Yazılı uyarı + zorunlu eğitim.
  - **C — Hata / İlk:** Eğitim hatırlatması.
- Tedarikçi uyumsuzluğunda sözleşme maddesi tetiklenir.
- KVKK Sorumlusu, ihlal halinde Komite'yi bilgilendirir.

## 13. Politika Şablonu (Markdown — kısa örnek başlangıç)

```markdown
---
Doküman: <başlık>
Sahip: <ekip / kişi>
Onaylayan: <komite>
Versiyon: 1.0
Yürürlük: YYYY-MM-DD
Gözden Geçirme: <tarih>
İlgili Mevzuat: ...
İlgili Standart: ...
---

# 1. Amaç
# 2. Kapsam
# 3. Tanımlar
# 4. Roller ve Sorumluluklar
# 5. Politika Hükümleri
# 6. İstisnalar
# 7. Ölçüm
# 8. Uyumsuzluk ve Yaptırım
# 9. İlgili Dokümanlar
# 10. Revizyon Geçmişi
```

## 14. Doküman Yönetim Sistemi (DMS) Beklentileri

- Versiyon kontrolü, audit trail, erişim kontrolü.
- Onay akışı (workflow) yerleşik.
- Otomatik review hatırlatıcıları (90, 30, 7 gün öncesinden).
- "Okudum" tutanağı (kritik politikalar için).
- Arama (full-text), etiket / kategori.
- Eski sürüm arşivi (read-only).
- Tipik adaylar: Confluence + Comala Workflow, SharePoint + Power Automate, GitOps yaklaşımı (Markdown + git PR review + CI yayın).

## 15. KPI

- Politika güncellik (≤24 ay): hedef %100.
- Yıllık review tamamlanma: %100.
- "Okudum" oranı (yeni başlayan, oryantasyon haftası içinde): %100.
- Kritik politika revizyonu sonrası 30 gün içinde okudum oranı: ≥%95.
- Açık istisna sayısı: trend takibi (yıl başına azalış hedefi).
- Uyumsuzluk olay sayısı: aylık trend.

## 16. Kontrol Listesi

- [ ] KVKK Politikası ve Bilgi Güvenliği Politikası mevcut, ≤2 yıl güncel mi?
- [ ] §3'te listelenen 38 doküman mevcut mu (kapsamı uygun değilse gerekçeli)?
- [ ] Tüm dokümanlar standart şablona uyuyor mu (versiyon, onaylayan, yürürlük)?
- [ ] Onay zinciri belgeli mi?
- [ ] DMS audit trail aktif mi?
- [ ] Yıllık review takvimi yayınlandı mı?
- [ ] Eski sürümler arşivde 5 yıl korunuyor mu?
- [ ] İstisna defteri güncel, süreli, telafi edici kontrollü mü?
- [ ] "Okudum" kayıtları yeni başlayanlar için 100% mi?
- [ ] Kritik politika revizyonu çalışanlara duyuruluyor mu?
- [ ] Türkçe asli + İngilizce sürüm tutarlı mı?
- [ ] Politika hiyerarşisi çelişki kontrolü yıllık yapılıyor mu?
- [ ] KPI'lar yıllık raporlanıyor, KVKK Komitesi'ne sunuluyor mu?
- [ ] Disiplin Politikası bilgi güvenliği ihlali sınıflandırması içeriyor mu?
- [ ] Tedarikçi sözleşmelerinde "tedarikçinin politikalarımıza uyumu" maddesi var mı?

## 17. Yaygın Hatalar

- Politika dokümanları yıllarca güncellenmemiş, mevzuatla çelişen ifadeler.
- "Yazıldı ama uygulanmıyor" — KPI ölçümü yok.
- Çalışan hangi politikanın geçerli olduğunu bilmiyor (intranet karmaşası).
- Standart şablon yok — her politika farklı dilde ve yapıda.
- "Okudum" sadece formal, anlama testi yok.
- İstisna kullanımı politika dışı normalleşmiş.
- Eski sürüm yanlışlıkla geçerli sanılarak uygulanmış.
- Tedarikçi sözleşmesinde politikalara atıf yok, asgari unsurlar eksik.
