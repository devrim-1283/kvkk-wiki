---
Doküman: İdari Tedbirler — Denetim-Hazır Kontrol Listesi
Bölüm: 06-idari-tedbirler
Sahip: İç Denetim / KVKK Sorumlusu
Onaylayan: KVKK Komitesi + Denetim Komitesi
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık + tetiklenmiş
İlgili Mevzuat: 6698 sayılı KVKK m.12; KVKK Veri Güvenliği Rehberi — "İdari Tedbirler Özet Tablosu"
İlgili Standart: ISO/IEC 27001:2022 Annex A (özellikle A.5, A.6); ISO/IEC 27701:2019; NIST CSF 2.0 GOVERN; CIS Controls v8; OECD Privacy Principles
---

# İdari Tedbirler Kontrol Listesi

## Kullanım

Bu liste; iç denetim örneklemesi, yıllık öz değerlendirme, KVKK Komitesi çeyreklik gözden geçirme ve dış denetime hazırlık için **denetim-hazır** referanstır. Her satır şu şekilde değerlendirilir:

- **Durum:** Var / Yok / Kısmen / Uygulanamaz (gerekçe yazılır)
- **Kanıt:** Doküman, ekran görüntüsü, log, ticket no, sözleşme, imza
- **Sahibi:** Operasyonel sahip
- **Son Test:** Tarih + test türü
- **Sonraki Test:** Hedef tarih
- **Açıklama / Aksiyon:** Eksiklik varsa CAPA referansı

ISO 27002:2022 A.x.y referansları her satıra eşlenmiştir.

---

## 1. Yönetişim ve Politika Çerçevesi (10 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 1.1 | Üst düzey KVKK Politikası mevcut, Yönetim Kurulu onaylı, ≤24 ay güncel | A.5.1 | GV.PO |
| 1.2 | Bilgi Güvenliği Politikası Yönetim Kurulu onaylı, ≤24 ay güncel | A.5.1 | GV.PO |
| 1.3 | KVKK Komitesi kurulmuş, üyeleri tanımlı, aylık toplantı yapılıyor | A.5.2 | GV.OV |
| 1.4 | KVKK Sorumlusu / DPO atanmış, bağımsızlığı korunuyor | A.5.2, A.5.4 | GV.RR |
| 1.5 | Politika hiyerarşisi (üst-alt seviye) tutarlı, çelişki yok | A.5.1 | GV.PO |
| 1.6 | Doküman Yönetim Sistemi (DMS) versiyonlu, audit trail aktif | A.5.33 | GV.OC-3 |
| 1.7 | Politika onay zinciri belgeli (e-imza / ıslak) | A.5.1 | GV.PO |
| 1.8 | Eski versiyon arşivi 5 yıl saklanıyor | A.5.33 | GV.OC-3 |
| 1.9 | İstisna defteri tutuluyor, süreli + telafi edici kontrollü | A.5.1 | GV.PO |
| 1.10 | Yıllık politika review takvimi yayınlandı, %100 tamamlanma | A.5.1 | GV.PO |

## 2. Personel Eğitim ve Farkındalık (8 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 2.1 | Yıllık eğitim programı yazılı, KVKK Komitesi onaylı | A.6.3 | PR.AT |
| 2.2 | Genel + rol bazlı modüller güncel (≤12 ay) | A.6.3 | PR.AT |
| 2.3 | LMS tamamlanma oranı yıllık ≥%95 | A.6.3 | PR.AT |
| 2.4 | Yeni başlayan onboarding eğitim erişim aktivasyon koşulu | A.6.3 | PR.AT |
| 2.5 | Bilgi testi başarı eşiği ≥%80, ölçülüyor | A.6.3 | PR.AT |
| 2.6 | Phishing simülasyon çeyreklik, KPI raporlu | A.6.3 | PR.AT |
| 2.7 | Vishing / AI-clone sosyal mühendislik simülasyonu yıllık | A.6.3 | PR.AT |
| 2.8 | Tedarikçi/danışman/stajyer eğitim zorunlu, kayıtlı | A.6.3 | PR.AT |

## 3. Gizlilik Taahhütnameleri (6 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 3.1 | Çalışan KVKK ve Gizlilik Taahhütnamesi şablonu Hukuk + KVKK Sorumlusu onaylı | A.6.6 | PR.AA |
| 3.2 | Tüm yeni başlayan oryantasyon haftası içinde imzalıyor | A.6.2 | PR.AA |
| 3.3 | Yönetici / özel nitelikli erişim ek taahhütleri imzalı | A.6.6 | PR.AA |
| 3.4 | Stajyer + danışman + tedarikçi personeli ayrı varyantları imzalı | A.6.6 | PR.AA |
| 3.5 | İmza kayıtları özlük dosyası + arşiv (istihdam + 10 yıl) | A.6.5 | GV.OC-3 |
| 3.6 | Versiyon değişiminde yeniden imza süreci 90 gün içinde | A.6.6 | PR.AA |

## 4. Tedarikçi (Üçüncü Taraf) Yönetimi (12 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 4.1 | Tedarikçi Politikası ≤24 ay güncel | A.5.19 | GV.SC |
| 4.2 | Tüm tedarikçiler sınıflandırılmış (A/B/C/D), envanterli | A.5.19 | ID.SC |
| 4.3 | Sınıf A/B için Veri İşleyen Sözleşmesi imzalı, KVKK m.12 asgari unsurları | A.5.20 | GV.SC |
| 4.4 | Sözleşme şablonu Hukuk + KVKK Sorumlusu onaylı, ≤12 ay güncel | A.5.20 | GV.SC |
| 4.5 | Alt-işleyen şeffaflığı + değişiklik bildirim akışı | A.5.20, A.5.21 | GV.SC |
| 4.6 | Yurt dışı aktarım mekanizması her tedarikçi için belirli (m.9 dayanak) | A.5.20 | GV.SC |
| 4.7 | Veri akış diyagramı güncel, envanterle tutarlı | A.5.21 | ID.AM-7 |
| 4.8 | Yıllık SOC 2 / ISO 27001 raporları toplandı, gözden geçirildi | A.5.22 | GV.SC |
| 4.9 | Sızma testi raporu yıllık alındı (Sınıf A) | A.5.22 | GV.SC |
| 4.10 | Çeyreklik (A) / yıllık (B/C) review yapıldı, kayıtlı | A.5.22 | GV.SC |
| 4.11 | Onaylı bulut sağlayıcı listesi, BYOK/CMK politikası | A.5.23 | GV.SC |
| 4.12 | Çıkış sürecinde veri iade/imha tutanağı standart kullanılıyor | A.5.22 | GV.SC |

## 5. Risk Yönetimi ve DPIA (8 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 5.1 | DPIA Standardı yazılı, ≤24 ay güncel | A.5.34 | GV.RM |
| 5.2 | Risk taraması (threshold) yeni proje sürecine entegre | A.5.34 | GV.RM |
| 5.3 | DPIA tetik listesi güncel, KVKK rehberlerine uyumlu | A.5.34 | GV.RM |
| 5.4 | Risk skor matrisi kalibre, risk iştahı yönetim onaylı | A.5.34 | GV.RM |
| 5.5 | KVKK Sorumlusu DPIA bağımsız görüşü yazıyor | A.5.34 | GV.RR |
| 5.6 | KVKK Komitesi DPIA onay tutanakları arşivli | A.5.34 | GV.OV |
| 5.7 | DPIA gereken proje / DPIA tamamlanan oranı %100 | A.5.34 | GV.RM |
| 5.8 | Yıllık DPIA review takvimi var, %100 tamamlanma | A.5.34 | GV.RM |

## 6. İlgili Kişi Hakları ve Aydınlatma (6 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 6.1 | Aydınlatma Metni Standardı yazılı, m.10 unsurlarını içeriyor | A.5.34 | GV.OC |
| 6.2 | Web sitesi + mobil + form + çağrı merkezi aydınlatma erişilebilir | A.5.34 | GV.OC |
| 6.3 | Açık rıza kayıtları zaman damgalı, geri çekme aynı kolaylıkta | A.5.34 | GV.OC |
| 6.4 | İlgili kişi başvuru kanalı (e-posta + form + KEP) yayınlandı | A.5.34 | GV.OC |
| 6.5 | Başvuru SLA (30 gün) %100 tutturuluyor | A.5.34 | RS.MA |
| 6.6 | Reddedilen başvuru gerekçesi yasal, m.13 unsurları cevapta | A.5.34 | GV.OC |

## 7. Veri İhlali Yönetimi (5 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 7.1 | Veri İhlali Yönetimi Prosedürü ≤24 ay güncel | A.5.24 | RS.MA |
| 7.2 | Tespit → Komite → 72 saat Kurul bildirim zinciri yazılı | A.5.24 | GV.RM |
| 7.3 | İhlal kayıt sistemi (kronolojik, kapsamlı) tutuluyor | A.5.27 | RS.AN |
| 7.4 | İhlal tatbikatı yıllık yapıldı (tabletop) | A.5.26 | RS.MA |
| 7.5 | İhlal sonrası lessons learned politikaya geri besliyor | A.5.27 | ID.IM |

## 8. Saklama, İmha ve Veri Yaşam Döngüsü (5 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 8.1 | Saklama ve İmha Politikası ≤24 ay güncel | A.5.33 | GV.OC-3 |
| 8.2 | Periyodik imha (çeyreklik) tutanaklı, çoklu imza | A.8.10 | GV.OC-3 |
| 8.3 | Yedeklerden imha akışı yazılı, denetlenebilir | A.8.13 | PR.DS-3 |
| 8.4 | Saklama süresi her veri kategorisi için tanımlı, sistemde otomatik tetikli | A.5.33 | GV.OC-3 |
| 8.5 | Crypto-shred kullanımında anahtar zeroize tutanağı | A.8.24 | PR.DS-3 |

## 9. VERBİS ve Envanter (4 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 9.1 | VERBİS kaydı güncel, son güncelleme ≤6 ay | A.5.34 | GV.OC |
| 9.2 | Veri envanteri canlı doküman, çeyreklik review | A.5.9 | ID.AM-7 |
| 9.3 | Envanter ↔ VERBİS ↔ DPIA tutarlılığı yıllık denetlenmiş | A.5.9 | ID.AM-7 |
| 9.4 | Yeni süreç eklendiğinde envanter güncelleme zorunlu (CI gate) | A.5.9 | ID.AM-7 |

## 10. İç Denetim ve Sürekli İyileştirme (6 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 10.1 | İç Denetim Tüzüğü ≤24 ay güncel, Yönetim Kurulu onaylı | – (Clause 9.2) | GV.OV |
| 10.2 | Yıllık denetim planı risk-bazlı, Denetim Komitesi onaylı | – (Clause 9.2) | GV.OV |
| 10.3 | KVKK denetim konuları (§3.2 listesi) yıllık planda yer alıyor | – (Clause 9.2) | GV.OV |
| 10.4 | Bulgular CAPA aracında, 90 gün geçmiş kritik açık 0 | – (Clause 10.1) | ID.IM |
| 10.5 | Yıllık yönetim raporu KVKK Komitesi + Yönetim Kurulu'na sunuldu | – (Clause 9.3) | GV.OV |
| 10.6 | Dış denetim (ISO, SOC, KVKK) entegrasyonu ve takip mekanizması | A.5.36 | GV.SC |

## 11. Çalışan İzleme, Mahremiyet, Kabul Edilebilir Kullanım (5 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 11.1 | Çalışan Aydınlatma Metni güncel, denetlenen kanallar listeli, yıllık imzalı | A.5.32 | GV.OC |
| 11.2 | DLP / izleme kapsamı KVKK m.4 ölçülülük testinden geçti | A.5.32, A.8.12 | GV.OC |
| 11.3 | BYOD politikası iş profili / kişisel veri ayrımını sağlıyor | A.7.9 | GV.PO |
| 11.4 | Kabul Edilebilir Kullanım Politikası (AUP) imzalı | A.5.10 | GV.PO |
| 11.5 | İzleme verisi 4-eyes review (CISO + İK + Hukuk) | A.5.32 | GV.OV |

## 12. Disiplin ve Yaptırım (3 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 12.1 | Disiplin Yönetmeliği bilgi güvenliği ihlal sınıflandırması içeriyor | A.6.4 | GV.PO |
| 12.2 | Disiplin sürecinde savunma + itiraz hakkı yazılı | A.6.4 | GV.PO |
| 12.3 | İhlal kanıt zinciri (chain of custody) prosedürü hazır | A.5.28 | RS.AN |

## 13. İletişim ve Üçüncü Taraf Bilgilendirme (4 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 13.1 | Kriz iletişim planı, sözcü atanmış, medya yanıt şablonları hazır | A.5.5, A.5.24 | RS.CO |
| 13.2 | İlgili kişi ihlal bildirim şablonu Türkçe + İngilizce hazır | A.5.34 | RS.CO |
| 13.3 | Tedarikçi ihlal bildirim akışı sözleşmede ve operasyonda işliyor | A.5.20 | RS.CO |
| 13.4 | Sektörel düzenleyici (BDDK / SPK / Sağlık Bakanlığı) bildirim takvimi var | A.5.5 | RS.CO |

## 14. Sektörel ve Özel Durumlar (3 madde)

| # | Kontrol | ISO 27002 | NIST CSF |
|---|---------|-----------|----------|
| 14.1 | Çocuk verisi varsa ek korumalar (ebeveyn rıza süreci) | A.5.34 | GV.OC |
| 14.2 | Pazarlama izinleri İYS uyumlu, opt-out süreçleri otomatik | A.5.34 | GV.OC |
| 14.3 | CCTV / kamera kayıtları amaç + süre + paylaşım politikası uygulanıyor | A.7.4 | GV.PO |

---

## Toplam Madde Sayısı: 85

## Değerlendirme Skoru

Her madde için: Var=2, Kısmen=1, Yok=0, Uygulanamaz=hariç.

| Olgunluk | Aralık | Yorum |
|----------|--------|-------|
| **Düşük** | < 60% | KVKK denetiminde ciddi uyumsuzluk riski |
| **Gelişmekte** | 60-75% | Temel uyum var, sistematik gap'ler |
| **Yetkin** | 75-85% | Kabul edilebilir uyum, aktif iyileştirme |
| **İleri** | 85-95% | Olgun program, sektör ortalaması üstü |
| **Optimize** | > 95% | Mükemmel uyum, lider seviyesi |

Hedef: **Yetkin (≥75%)** birinci yıl, **İleri (≥85%)** ikinci yıl.

## Yıllık Öz-Değerlendirme Akışı

```
Q1
   - KVKK Sorumlusu liste için kanıt toplama görev planı çıkarır
   - Sahipler kanıt yükler

Q2
   - İç Denetim örnekleme ile doğrular
   - Bulgular CAPA'ya işlenir

Q3
   - Sonuçlar KVKK Komitesi'ne özet rapor
   - Yıllık yönetim raporu hazırlanır

Q4
   - Yönetim Kurulu'na yıllık güvenlik+mahremiyet durum raporu
   - Sonraki yıl planı (yeni hedef KPI, yeni kontrol)
```

## CAPA Önceliklendirme

Her **Yok** veya **Kısmen** satırı için:

| Kontrol Etkisi | SLA |
|-----------------|-----|
| KVKK Kurulu denetiminde bulgu olabilir | 30 gün |
| Mevzuat ihlali riski yaratıyor | 30 gün |
| KVKK m.12 idari tedbir başlığında zorunlu | 60 gün |
| İyi uygulama düzeyinde eksik | 90 gün |
| Olgunluk artışı için fırsat | 180 gün |

## Dış Denetim ile İlişki

- **ISO 27001 sertifikası varsa:** bu liste, ISO Annex A'nın KVKK genişletmesi olarak iç denetim kapsamını oluşturur. ISO LA denetiminden önce öz-değerlendirmenin tamamlanması güçlü hazırlıktır.
- **ISO 27701 (PIMS) sertifikasına yönelinirse:** A.7.x ve A.8.x ek kontrolleriyle eşleme + bu liste, hazırlık temelini sağlar.
- **KVKK Kurum denetimi:** bu liste, talep edilen "uygulanan idari tedbirler" beyanının kanıt setidir.

## Birleşik (Teknik + İdari) Skor

[teknik-tedbir-kontrol-listesi.md](../05-teknik-tedbirler/teknik-tedbir-kontrol-listesi.md) ile birlikte değerlendirildiğinde:

```
Toplam Madde: 88 (Teknik) + 85 (İdari) = 173
```

KVKK Komitesi yıllık raporda **iki listenin birlikte ağırlıklı skoru** kullanılarak kurum genel olgunluğu belirlenir. Tek liste yetersiz tablodur — KVKK m.12 hem teknik hem idari tedbir gerektirir.

## Yaygın Hatalar (Bu Listede Sık Çıkan)

- "Politika var" ama "≤24 ay güncel değil" — yıllık review takvimi yok.
- "Sözleşme imzalı" ama "asgari unsurlar eksik" — şablon güncel değil.
- "Eğitim verildi" ama "tamamlanma raporu yok / sınav başarı yok" — kanıt zayıf.
- "DPIA yapıldı" ama "KVKK Sorumlusu görüşü yok" — bağımsızlık sorgulanır.
- "VERBİS güncel" ama "envanter ile çelişiyor" — denetimde hızlı bulgu.
- "İhlal kayıt sistemi var" ama "ramak kala olayları kayda alınmıyor" — kültür sorunu.
- "Aydınlatma metni mevcut" ama "mobil görünümde gizli" — m.10 ihlali.
- "Tedarikçi onayı yapıldı" ama "alt-işleyen değişimi izlenmiyor" — şeffaflık zayıf.
