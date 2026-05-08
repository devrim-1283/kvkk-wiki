---
Doküman: İhlal Müdahale Tatbikatı (Tabletop / Soak Test) Programı
Bölüm: 08-ihlal-yonetimi
Sahip: Bilgi Güvenliği Müdürü (CISO) + KVKK Sorumlusu
Onaylayan: KVKK Komitesi + Yönetim
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yıllık
İlgili Mevzuat: 6698 sayılı KVKK m.12, KVKK Veri Güvenliği Rehberi (2018) §5.4, NIST SP 800-84, ISO/IEC 27035-3:2020
---

# İhlal Müdahale Tatbikatı (Tabletop & Soak Test)

## 1. Amaç

KVKK Veri Güvenliği Rehberi'nin gereği ve uluslararası iyi uygulamaların (NIST 800-84, ISO 27035-3) ışığında, ihlal müdahale prosedürünün **kâğıt üzerinde değil pratikte** çalıştığını yıllık olarak doğrulamak. Tatbikatlar üç düzlemde yürütülür:

1. **Tabletop egzersizi (masa başı):** Senaryoyu okur, kararlar tartışılır. Hız ve süreç değerlendirmesi.
2. **Functional drill (fonksiyonel tatbikat):** Gerçek araçlar (SIEM, EDR, KEP) kullanılır; sistem dokunulmaz.
3. **Red team / Purple team (canlı):** Etik saldırgan ekibi gerçek saldırı simüle eder, mavi takım yanıt verir.

## 2. Yıllık Tatbikat Takvimi

| Çeyrek | Tip | Hedef Senaryo | Katılımcılar |
|--------|-----|---------------|--------------|
| Q1 | Tabletop | Ransomware (Senaryo A) | CSIRT çekirdek + YK gözlemci |
| Q2 | Functional | İçeriden veri sızıntısı (Senaryo B) | CSIRT + İK + DLP ekibi |
| Q3 | Tabletop | Üçüncü taraf ihlali (Senaryo C) | CSIRT + Tedarik + Hukuk |
| Q4 | Red/Purple | Web uygulaması istismarı (Senaryo D) | SOC + AppSec + Red Team |
| Yıllık özel | Tabletop | Kayıp cihaz + içeriden kombine (Senaryo E) | Tüm CSIRT + Yönetim |

## 3. Tatbikat Yönetişimi

### 3.1. Roller

| Rol | Sorumluluk |
|-----|-----------|
| Tatbikat Lideri (Exercise Director) | Senaryo akışı, "injects" zamanlaması, kayıt |
| Beyaz Takım (Adjudicator) | Kararları değerlendirir, puanlama |
| Mavi Takım (Defenders) | CSIRT'in tatbikattaki hali |
| Kırmızı Takım (Attackers) | Sadece red/purple tatbikatta |
| Mor Takım (Purple) | Saldırı + savunma birlikte çalışır |
| Gözlemciler | YK üyesi, Hukuk, KVKK Komitesi |

### 3.2. Tatbikat Bütçesi

- Tabletop: 4 saat × katılımcı + 16 saat hazırlık.
- Functional: 8 saat × katılımcı + 24 saat hazırlık.
- Red/Purple: 5 iş günü dış firma + dahili 80 saat.

### 3.3. Gizlilik

- Senaryo katılımcılara önceden açıklanmaz (sürpriz öğesi).
- Sonuçlar sadece KVKK Komitesi + üst yönetim ile paylaşılır.
- Dış paylaşım yapılmaz (saldırgan istihbaratı).

## 4. KPI'lar (Performans Göstergeleri)

Her tatbikat sonunda ölçülür:

| KPI | Açıklama | Hedef |
|-----|----------|-------|
| MTTD (Mean Time To Detect) | İlk olay → tespit | < 30 dakika |
| MTTI (Mean Time To Identify) | Tespit → ihlal kararı | < 4 saat |
| MTTC (Mean Time To Contain) | Tespit → sınırlandırma | < 2 saat |
| MTTN (Mean Time To Notify) | T+0 → Kurul taslak | < 24 saat |
| MTTR (Mean Time To Recover) | Tespit → üretim normal | < 72 saat |
| Bildirim metin kalite skoru | 1-10 (Hukuk değerlendirme) | ≥ 8 |
| Karar zinciri eksiksizliği | Her kritik karar belgelendi mi | %100 |
| İletişim ağacı uyumu | Doğru kişi doğru zamanda haberdar | %95 |

## 5. SENARYO A — Ransomware (Tabletop)

### 5.1. Brief
> "06:30 — Bursa fabrika SCADA sunucusuna giren bir SOC analiti, dosyaların `.lockbit` uzantısı aldığını fark eder. Ekran üzerinde fidye notu görünür: '5 BTC içinde 7 gün, ödemezseniz IK ve ARGE verilerini sızdıracağız.' Olay açma helpdesk'a 06:45'te düşer."

### 5.2. Inject'ler (Beyaz Takım sırayla atar)

| T+ | Inject | Beklenen yanıt |
|----|--------|----------------|
| T+0 dk | Helpdesk e-postası | SOC L2'ye eskalasyon, izolasyon kararı |
| T+30 dk | İkinci sunucu da etkilendi (yatay hareket) | Aktivasyon Seviye 3, network segmentasyonu |
| T+1 saat | "Fidye ödenmeli mi" YK sorusu | Politika hatırlatma — ödenmez, sigorta |
| T+2 saat | Saldırgan İK verisi örneği yayımladı | İlgili kişi bildirim hazırlığı başlasın |
| T+4 saat | Basın ajansı arıyor | Kurumsal İletişim devreye, "yorum yok" değil önceden hazır metin |
| T+6 saat | EDR tüm filo taraması — 12 sunucu daha IOC | Genişletilmiş izolasyon |
| T+12 saat | Yedeklerin de etkilendiği rapor | Kriz! Önceden offline backup var mıydı? |
| T+24 saat | Kurul'a taslak bildirim deadline | Form hazır mı, KEP gönderildi mi |
| T+48 saat | Saldırgan ikinci ödeme uyarısı | Politika tekrar |
| T+72 saat | Kurul nihai bildirim deadline | Form tamamlandı mı |

### 5.3. Karar Noktaları (Adjudicator değerlendirir)

- Etkilenen sistem **kapatıldı mı, izole mi edildi**? (Doğru: izolasyon — bellek delili korunur)
- Sigortacı **T+12 saatte** mi haberdar oldu?
- İlgili kişi bildirim metninde **hangi veri kategorileri** açıkça yazıldı?
- Yedeklerin de etkilendiği gerçeği medyaya **kontrollü mü** açıklandı?
- Fidye konusu YK'ya **politika gereği** mi taşındı?

### 5.4. Sıkça Yapılan Hatalar

- Etkilenen sunucuyu kapatma (RAM kanıtı kaybolur).
- Sigortacıyı bildirmemeyi seçme (poliçe SLA'yı kaçırırsa hak düşer).
- "Veri kategorisi belirsiz" diyerek bildirimi geciktirme.
- Sosyal medyada erken duyuru (saldırgan tatmin olur, fidye baskısı artar).

## 6. SENARYO B — İçeriden Veri Sızıntısı (Functional Drill)

### 6.1. Brief
> "Pazartesi 10:30 — DLP sistemi 'Ahmet K.' isimli pazarlama uzmanının son 3 günde 8.500 müşteri kaydını şirket dışı bir Gmail adresine yüklediğini raporlar. Çalışan 2 hafta sonra rakip firmada işe başlayacak."

### 6.2. Inject'ler

| T+ | Inject | Beklenen yanıt |
|----|--------|----------------|
| T+0 | DLP alarmı | SOC + İK + Hukuk üçlü koordinasyon |
| T+30 dk | Çalışanın aktif oturumu var | Sessiz izleme — kanıt toplama (canlı) |
| T+1 saat | Ek dış adresler tespit | Tam kapsam haritalama |
| T+2 saat | Çalışan yetkilerinin uzaktan dondurulması | İK onay ile sessizce |
| T+4 saat | Çalışan ile yüz yüze görüşme planı | Hukuk + İK + tanık |
| T+6 saat | Cihaz forensik imajı | Chain of custody |
| T+12 saat | Adli savcılık değerlendirme | TCK m.136 |
| T+24 saat | Veri geri çağırma — alıcı firmaya cease & desist | Hukuk |
| T+48 saat | Etkilenen müşteri bildirim hazırlığı | KVKK + İletişim |
| T+72 saat | Kurul bildirim | KVKK Sorumlusu |

### 6.3. Functional Drill Aksiyonları

- **DLP konsolu açılır**, gerçek log incelenir (test verisiyle).
- **HR sistemi**nde çalışan dondurma uygulanır (test sandbox).
- **AD/Entra**'da hesap disable edilir.
- **KEP gönderim** simülasyonu (test KEP).
- **Kurul portalı** (test ortamı varsa) — form taslak doldurulur.

### 6.4. Karar Noktaları

- Çalışan haberdar olmadan kanıt toplama süresi yeterli miydi?
- Hukuk + İK senkronu kuruldu mu?
- Adli süreç **aynı anda** başlatılabilir mi (idari + cezai)?
- Rakip firmaya cease & desist hangi delillerle gönderildi?

## 7. SENARYO C — Üçüncü Taraf İhlali (Tabletop)

### 7.1. Brief
> "Salı 14:00 — Bordro hizmeti aldığımız 'PayrollX SaaS' firmasından KEP gelir: 'Müşterilerimizin %18'ini etkileyen bir veri ihlali tespit edilmiştir. Şirketinize ait 612 çalışanın bordro ve IBAN bilgileri etkilenmiş olabilir. İlk tespitimiz 5 gün önceydi, şu an iletişime geçiyoruz.'"

### 7.2. Inject'ler

| T+ | Inject | Beklenen yanıt |
|----|--------|----------------|
| T+0 | KEP geldi | Sözleşme bildirim klozu kontrolü — 24 saat klozu ihlali tespit |
| T+30 dk | Alıcı firma bilgi paylaşmıyor | Sözleşmesel yaptırım, geçici askıya alma |
| T+1 saat | Tedarikçi yedek planı | İK + Finans alternatif sağlayıcı |
| T+4 saat | Bağımsız forensik talebi | Hukuk + CISO |
| T+12 saat | Sigortacı bildirim | CFO + Hukuk |
| T+24 saat | Kurul taslak bildirim | KVKK Sorumlusu |
| T+48 saat | Çalışan iletişim | İK + KVKK |
| T+72 saat | Kurul nihai | KVKK Sorumlusu |

### 7.3. Karar Noktaları

- 5 günlük gecikme **bizim 72 saatimize sayıldı mı**? (Cevap: hayır, bizim T+0'ımız bugün; ancak Kurul'a açıklamalıyız.)
- Sözleşme **tek taraflı fesih** hakkı içeriyor mu?
- Sözleşmesel **ceza-i şart** ne kadar?
- Yeni sağlayıcıya geçiş süresi (vendor lock-in?) tatbikatta hesaplandı mı?

### 7.4. Tatbikat Çıktısı

- Tedarikçi sözleşme klozları haritası (kim 24 saat, kim 72 saat, kim eksik).
- Yedek tedarikçi listesi güncellemesi.
- Veri taşınabilirliği tatbikatı (export-import zaman ölçümü).

## 8. SENARYO D — Web Uygulaması İstismarı (Red/Purple)

### 8.1. Brief
> "Dış red team firması, müşteri portali için OWASP Top 10 testi kapsamında SQL Injection açığı tespit eder ve 1.2 M müşteri kaydını exfiltrate eder (test ortamı veya prod canary)."

### 8.2. Saldırı Aşamaları (Red)

1. Reconnaissance — Wayback, Shodan, Censys.
2. Vulnerability scanning — Burp Suite, sqlmap.
3. Initial access — SQLi.
4. Privilege escalation — DB kullanıcısından sistem.
5. Lateral movement — diğer sunuculara.
6. Data collection — müşteri tablosu.
7. Exfiltration — DNS tunneling.

### 8.3. Savunma Aşamaları (Blue)

1. WAF anomaly score yükselişi.
2. SIEM korelasyon — DB query patlaması.
3. EDR — anormal süreç.
4. DLP — DNS dışa veri çıkışı.
5. SOC L1 alarm → L2 doğrulama.
6. CSIRT aktivasyon.
7. Sınırlandırma + bildirim.

### 8.4. Purple Sinerji Noktaları

- Red her aşamayı **bildirimsiz** yapar; Blue ne kadarını yakaladı?
- Yakalanmayan aşamalar için **detection engineering** çıktıları.
- WAF kural setlerinin gerçek saldırıda nasıl performans gösterdiği.

### 8.5. Çıktı

- Detection coverage matrix (MITRE ATT&CK).
- Yeni SIEM kuralı önerileri (en az 5).
- Yama önerileri (CVSS önceliği).
- Bildirim akışı süre ölçümü.

## 9. SENARYO E — Kombine: Kayıp Dizüstü + İçeriden Tehdit

### 9.1. Brief
> "Pazar gecesi — bir bölge müdürü 'dizüstüm bagajdan çalındı' diye bildirir. Ertesi gün, IT log'larında dizüstüğün 6 ay boyunca anormal dosya indirme aktivitesi yaptığı tespit edilir. Bölge müdürü 1 ay içinde işten ayrılmayı planlamış."

### 9.2. Çoklu Vektör

| Boyut | Eylem |
|-------|-------|
| Kayıp cihaz | MDM uzaktan kilit, BitLocker doğrulama |
| İçeriden | Disiplin + Hukuk + adli inceleme |
| Veri kapsamı | Son 6 aylık aktivite analizi |
| KVKK | Bildirim yapılır mı? Şifrelenmişse rezerv durum |
| Kriz | Bölge satışları, müşteri itibarı |

### 9.3. Bu Senaryonun Amacı

Kategoriler arası karar verme: kayıp **mi**, içeriden **mi**, ikisi birden **mi**? Bildirim metni hangisini öne çıkarır? Adli süreç hangi yönde ilerler? Tatbikat ekibinin **bilgi belirsizliği** altındaki performansını ölçer.

## 10. Tatbikat Sonrası Rapor Şablonu

Her tatbikat sonrası 7 iş günü içinde aşağıdaki rapor hazırlanır:

```markdown
# Tatbikat Sonrası Rapor

## 1. Tatbikat Bilgileri
- Tatbikat adı:
- Tarih:
- Senaryo:
- Süre:
- Katılımcılar:
- Tatbikat Lideri:

## 2. Senaryo Özeti

## 3. KPI Ölçümleri
| KPI | Hedef | Gerçekleşen | Durum |
|-----|-------|-------------|-------|
| MTTD | < 30 dk | | ☐ Geçti ☐ Kaldı |
| MTTI | < 4 saat | | |
| MTTC | < 2 saat | | |
| MTTN | < 24 saat | | |
| MTTR | < 72 saat | | |
| Bildirim kalitesi | ≥ 8/10 | | |

## 4. Doğru Yapılanlar
1.
2.

## 5. Eksiklikler / Kaçırılan Noktalar
1.
2.

## 6. Senaryo-Spesifik Bulgular

## 7. Aksiyon Listesi (CAPA)
| # | Aksiyon | Sahip | Tarih | Durum |
|---|---------|-------|-------|-------|
| 1 | | | | |

## 8. Prosedür / Eğitim Güncellemesi Önerileri

## 9. Sonraki Tatbikat Önerileri

## 10. Yönetim İmza
- Tatbikat Lideri:
- CISO:
- KVKK Sorumlusu:
- KVKK Komitesi:
```

## 11. Aksiyon Takibi

Tatbikat aksiyonları **`11-denetim-ve-uyum/aksiyon-takibi.md`** ile entegredir. Aşamalar:

1. Aksiyon JIRA/asana/yazılı listede açılır.
2. Sahip ve tarih atanır.
3. Çeyreklik KVKK Komitesi gözden geçirir.
4. Kapanmamış aksiyonlar **sonraki tatbikat senaryosuna** girer.
5. Yıllık denetimde tatbikat aksiyonları kontrol edilir.

## 12. Tatbikat Olgunluk Modeli

Şirketin tatbikat olgunluk seviyesi:

| Seviye | Tanım |
|--------|-------|
| 1 — Ad-hoc | Yıllık 1 tatbikat, dokümante edilmemiş |
| 2 — Sürekli | Çeyreklik tatbikat, raporlama var |
| 3 — Ölçülen | KPI'lar takip ediliyor, eğilim raporu |
| 4 — Yönetilen | Kırmızı takım dahil, eskalasyon test |
| 5 — Optimize | Otomasyon, threat-informed defense, sürekli iyileştirme |

Şirketimiz hedef seviye: **4 — Yönetilen** (2026 sonu).

## 13. Tatbikat Etiği

- Çalışan tatbikat sırasında **gerçekten zararlı** araç çalıştıramaz.
- Üretim sistemleri etkilenmemelidir (sandbox/test).
- Sosyal mühendislik tatbikatlarında çalışan **gizlice rezalet edilmez** — eğitim odaklı.
- Tatbikat sonuçları bireysel ceza için kullanılmaz; süreç iyileştirme.
- Saldırı simülasyonu **yasal kapsamda** (yetki belgesi imzalı).

## 14. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi |
