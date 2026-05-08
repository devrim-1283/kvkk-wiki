---
Doküman: Yapay Zeka ve Büyük Dil Modelleri (LLM) Kullanımı
Bölüm: 10-ozel-konular
Sahip: KVKK Sorumlusu + CISO + AI/ML Lideri + Veri Bilim
Onaylayan: Hukuk Müdürü + KVKK Komitesi + CTO
Versiyon: 1.0
Yürürlük: 2026-05-08
Gözden Geçirme: Yarı yıllık (alan hızlı değişiyor)
İlgili Mevzuat: 6698 sayılı KVKK m.5, m.6, m.9, m.11/g; AB AI Act (referans, doğrudan uygulanmaz); NIST AI RMF 1.0; OWASP Top 10 for LLM (2025); ISO/IEC 42001:2023; Türkiye Ulusal AI Stratejisi
---

# Yapay Zeka ve LLM Kullanımı

## 1. Amaç

Şirket bünyesinde yapay zeka (özellikle büyük dil modelleri / LLM) kullanımının KVKK uyumlu yönetimi. Bu alan **hızla değişen** mevzuat ortamı nedeniyle ihtiyatlı yaklaşım gerektirir; AB AI Act benzeri Türkiye düzenlemesi (Yapay Zeka Kanunu) yakın gelecek beklenmektedir.

## 2. Kullanım Senaryoları

| Senaryo | Risk Seviyesi | Hukuki Sebep |
|---------|---------------|--------------|
| Çalışanın kişisel ChatGPT kullanımı (iş için) | **Yüksek** (sızıntı) | Açık rıza müşteri/diğer; politika sınırlama |
| Kurumsal ChatGPT/Claude/Gemini Enterprise | Orta | DPA + sözleşme |
| Müşteri hizmeti chatbot | Orta | Açık rıza + aydınlatma |
| Otomatik karar (kredi, insan kaynağı eleme) | **Yüksek** | DPIA + manuel revize |
| LLM ile müşteri yorumu özet | Orta | Aydınlatma; yurt dışı aktarım dikkat |
| AI ile kod yazma (Copilot, Cursor) | Düşük-Orta | Kod sızıntısı denetimi |
| LLM ile içerik üretimi (pazarlama) | Düşük | İçerik kontrol |
| RAG ile şirket dokümanlarına soru-cevap | Orta | Erişim yetkisi + DLP |
| Toplantı transcript + özet (Otter, Fireflies) | Orta-Yüksek | Açık rıza katılımcılardan |
| Kişiselleştirme (öneri sistemi) | Orta | Aydınlatma + (varsa) açık rıza |
| AI eğitiminde gerçek müşteri verisi kullanımı | **Çok Yüksek** | Açık rıza nadiren yeterli; anonimleştirme |

## 3. Çalışan ChatGPT/Claude/Gemini Kullanım Politikası

### 3.1. Risk

- Çalışan müşteri verisi prompt'a yapıştırır → veri yurt dışı.
- Şirket sırrı, kod, finansal bilgi sızar.
- Hesap çalışan kişisel → audit zor.
- Bazı modeller prompt'u eğitime kullanabilir (kapatılmazsa).

### 3.2. Politika Maddeleri

```
1. Kişisel hesap (ücretsiz/Plus) ile iş yapma YASAK.
2. Sadece onaylanmış kurumsal hesap kullanılır:
   - ChatGPT Enterprise / Team
   - Claude for Work / Enterprise
   - Gemini Enterprise
   - Microsoft Copilot for M365
3. Yapıştırma kuralları:
   - Kişisel veri (T.C., müşteri ismi, e-posta, telefon) YASAK
   - Şirket sırrı (sözleşme, kod, finansal) YASAK
   - Pseudonymize / anonimleştirilmiş veri serbest
4. Çıktı denetimi:
   - LLM çıktısı doğrulanmadan iletişimde kullanılmaz
   - Hassas karar için tek başına dayanılmaz
5. Audit:
   - Kurumsal araçlarda kullanım log'lanır
   - Anomali tespiti (DLP entegrasyonu)
6. Eğitim:
   - Yıllık 1 saat AI farkındalık eğitimi
   - Yeni iş başlangıcında onboarding modülü
7. İhlal:
   - 1. ihlal: uyarı + eğitim
   - 2. ihlal: disiplin
   - Kasıtlı veri sızıntısı: iş akdi feshi + adli süreç
```

### 3.3. Teknik Önlemler

- DLP — prompt'lara kişisel veri filtre.
- Web filtre — onaylı domainler.
- EDR — uygulama beyaz listesi.
- Endpoint kullanım analizi.

## 4. Kurumsal LLM Sözleşmeleri

### 4.1. Kontrol Listesi

| Madde | Şirketimiz Tutumu |
|-------|-------------------|
| Veri eğitime kullanılmaz | **Zorunlu** (sözleşmesel) |
| DPA / KVKK uyum klozu | Zorunlu |
| Yurt dışı aktarım Standart Sözleşme | Zorunlu (yurt dışı işleyen) |
| Audit log paylaşımı | Zorunlu |
| Saklama süresi | 30 gün max (zero retention tercih) |
| Region seçimi | AB / Türkiye |
| Şifreleme (transit + rest) | TLS 1.3 + AES-256 |
| İhlal bildirim 24 saat | Zorunlu |
| Sözleşme sonu veri silme + sertifika | Zorunlu |
| Sigorta + sorumluluk | Hukuk değerlendirmesi |

### 4.2. Önerilen Çözümler

| Çözüm | KVKK Uyum Notu |
|-------|----------------|
| OpenAI ChatGPT Enterprise / API | Zero retention opsiyonu, EU region |
| Anthropic Claude (API + Enterprise) | EU/US region; eğitim için kullanılmaz default |
| Microsoft Copilot for M365 | EU Data Boundary; tenant izolasyon |
| Google Gemini Enterprise | EU region; DLP entegrasyon |
| AWS Bedrock | Region kontrolü; veri AWS dışına çıkmaz |
| Azure OpenAI Service | EU/US; veri Azure tenant'ında |
| **On-prem (private)** | Llama 3, Mistral — veri Şirket içinde |

### 4.3. Yurt Dışı Aktarım Analizi

LLM API çağrısı = veri yurt dışına aktarım.
- Standart Sözleşme zorunlu.
- TIA (Transfer Impact Assessment).
- Kurul'a 5 iş günü içinde bildirim.

## 5. Prompt'a Kişisel Veri Sızdırma

### 5.1. Sızıntı Vektörleri

- "Şu müşterinin şikayetine cevap yaz: [müşteri ismi + e-posta + sorun]" → tüm bunlar LLM'e.
- "Bu CV'yi özetle: [tam CV]" → kişisel veri.
- "Bu sözleşmenin riskleri ne: [taraf isimleri + tutarlar]" → ticari sır.

### 5.2. Önleme

- **Pre-prompt sanitization** — DLP entegrasyon.
- **Anonimleştirme** önce, prompt sonra.
- **Pseudo ID** — kişi yerine "Müşteri A".
- **Eğitim** — çalışan farkındalık.

### 5.3. DLP Entegrasyon

- Prompt giderken kişisel veri tara.
- Bulursa engelle + kullanıcıya geri bildirim.
- Kayıt + UEBA anomali tespiti.

## 6. DPIA Zorunluluğu

KVKK Kurul rehberi yüksek riskli işleme için DPIA önerir. AI/LLM kullanımı şu durumlarda DPIA zorunludur:

- Otomatik karar (örn. işe alım, kredi, fiyatlama).
- Profilleme (segment, churn).
- Geniş ölçek (1M+ kullanıcı).
- Hassas kategori (sağlık, finans).
- Yeni teknoloji.
- Yurt dışı aktarım.

### 6.1. DPIA Bölümleri (AI Spesifik)

1. Sistem tanımı (model, sağlayıcı, veri akışı).
2. İşleme amacı + gereklilik.
3. Hukuki sebep.
4. Veri kategorisi + kaynak.
5. Algoritma açıklaması (model kart).
6. Risk: önyargı, ayrımcılık, sızıntı, halüsinasyon.
7. Tedbirler: human-in-the-loop, açıklanabilirlik, sınırlandırma.
8. İlgili kişi etki + m.11/g.
9. Kalan risk + kabul.
10. İzleme + yenileme planı.

## 7. Model Kart (Model Card)

Her AI sistemi için **model kart** yayımlanır:

```
Model Kart - [Sistem Adı] v[X.Y]

1. Genel Bilgi
   - Model: GPT-4 / Claude / Llama / vs.
   - Sağlayıcı:
   - Region:
   - Versiyon:

2. Amaç
   - Birincil:
   - Yan etki olasılıkları:

3. Eğitim Verisi (sağlayıcı bilgisi)
   - Tipi:
   - Kapsam:
   - Tarih sınırı:

4. Performans
   - Test seti sonuçları:
   - Bilinen zayıflıklar:
   - Halüsinasyon oranı (varsa ölçülmüş):

5. Önyargı (Bias) Değerlendirmesi
   - Test edilen demografi:
   - Bulgular:

6. Sınırlamalar
   - Kullanılmaması gereken senaryolar:

7. KVKK Bağlamı
   - Hukuki sebep:
   - Yurt dışı aktarım:
   - DPIA referansı:
   - İlgili kişi hakları (özellikle m.11/g):

8. İzleme
   - Performans metriği takibi:
   - Yeniden değerlendirme tarihi:
```

## 8. Açıklanabilirlik ve İlgili Kişi Hakları

### 8.1. KVKK m.11/g

> "İşlenen verilerin münhasıran otomatik sistemlerle analiz edilmesi suretiyle kişinin kendisi aleyhine bir sonucun ortaya çıkmasına itiraz etme."

**Bizim sorumluluğumuz:**
- Otomatik karar var mı, açıkla.
- Kararın temel parametreleri.
- Manuel revize seçeneği.
- Aday/müşteri talep ederse insan kararı.

### 8.2. Açıklanabilir AI (XAI) Yaklaşımları

- LIME, SHAP — model çıktısı açıklama.
- Karar yolu (decision path) — ağaç tabanlı modeller.
- Counterfactual — "ne olsaydı farklı sonuç gelirdi".
- LLM ile reasoning chain — Chain-of-Thought.

### 8.3. Şeffaflık Standartı

İlgili kişiye sunulacak açıklama:
- B1 düzey Türkçe.
- Algoritmanın temel girdileri.
- Karara etkili faktörler.
- Manuel revize yolu.
- KVKK m.11/g hakkı.

## 9. OWASP LLM Top 10 (2025)

LLM uygulama güvenliği için OWASP'ın 2025 versiyonu:

| # | Risk | KVKK Bağlamı |
|---|------|--------------|
| 1 | Prompt Injection | Yetkisiz veri sızıntısı |
| 2 | Insecure Output Handling | XSS, command injection |
| 3 | Training Data Poisoning | Bias, ayrımcılık |
| 4 | Model Denial of Service | Sistem güvenliği |
| 5 | Supply Chain Vulnerabilities | Üçüncü taraf risk |
| 6 | Sensitive Information Disclosure | KVKK ihlali doğrudan |
| 7 | Insecure Plugin Design | Eklenti istismarı |
| 8 | Excessive Agency | Otomatik karar kontrolsüz |
| 9 | Overreliance | Halüsinasyon |
| 10 | Model Theft | Fikri mülkiyet |

Her risk için iç tatbikat + mitigation.

## 10. NIST AI RMF 1.0

NIST AI Risk Management Framework — yapay zeka risk yönetimi:

### 10.1. Dört Fonksiyon

- **Govern** — Yönetişim, politika, hesap verebilirlik.
- **Map** — Bağlam, risk haritalama.
- **Measure** — Ölçüm, test.
- **Manage** — Risk yönetim, müdahale.

### 10.2. Şirket Uygulaması

- AI yönetişim komitesi (KVKK Komitesi içinde alt grup).
- AI envanteri (sistemler, kullanım amaçları).
- Risk değerlendirme matrisi (her sistem).
- Sürekli izleme + raporlama.

## 11. AB AI Act Hazırlığı

AB AI Act (2024 yürürlük, 2026-2027 zorunluluk) Türkiye'yi bağlamaz **ancak**:
- Türk firmaları AB pazarına ürün/hizmet veriyorsa kapsama girer.
- Türkiye AI Kanunu büyük olasılıkla benzer çerçeve alacak.

### 11.1. Risk Tabakaları (AI Act)

- **Yasak** (subliminal manipülasyon, sosyal puanlama).
- **Yüksek riskli** (işe alım, kredi, eğitim, hukuk) — sıkı yükümlülükler.
- **Sınırlı** (chatbot, derin sahte) — şeffaflık.
- **Düşük** — serbest.

### 11.2. Şirket Hazırlığı

- AI envanter sınıflandırması (yasak / yüksek / sınırlı / düşük).
- Yüksek riskli sistemler için ek dokümantasyon.
- CE benzeri sertifikasyona hazırlık.
- Kullanıcıya bildirim (chatbot + AI).

## 12. ISO/IEC 42001:2023

Yapay zeka yönetim sistemi (AIMS) standardı. ISO 27001 benzeri çerçeve.

- AI politika.
- Rol ve sorumluluklar.
- Risk değerlendirme.
- Kontroller (164+).
- Yıllık denetim.

> Şirket büyüklüğüne göre 12-24 ay sertifikasyon yolu.

## 13. On-Premise / Private LLM

### 13.1. Avantajları

- Veri Şirket içinde.
- Yurt dışı aktarım yok.
- Düzenleyici uyum daha kolay.
- Özel veriyle fine-tune mümkün.

### 13.2. Önerilen Modeller

- Llama 3 (Meta — açık ağırlık).
- Mistral (Mixtral — açık).
- DeepSeek, Qwen (lisans dikkat).

### 13.3. Altyapı Maliyeti

- GPU (NVIDIA H100, A100) yatırımı yüksek.
- Sürekli güncelleme + güvenlik.
- Yetenek (MLOps).
- ROI değerlendirmesi.

### 13.4. Hibrit Yaklaşım

- Hassas görevler on-prem.
- Genel görevler bulut LLM.
- Routing katmanı (LiteLLM, OpenRouter benzeri).

## 14. RAG ve Erişim Kontrolü

### 14.1. RAG (Retrieval-Augmented Generation)

- Şirket dokümanlarını embedding ile vector DB'de.
- LLM cevap verirken doküman çek.
- Cevap kaynaklı.

### 14.2. KVKK Uyumu

- Her kullanıcı için **erişim filtresi** (sadece yetkili dokümanlar).
- Audit log — kim hangi dokümana erişti.
- Hassas içerik (özlük, sağlık) ayrı index + sınırlı erişim.

### 14.3. Vector DB

- Pinecone, Weaviate, Qdrant, ChromaDB.
- Yurt dışı sağlayıcı = aktarım.
- On-prem alternatif (Qdrant kendi sunucu, pgvector).

## 15. Tipik Hatalar

| Hata | Doğru Yaklaşım |
|------|----------------|
| Çalışan kişisel ChatGPT'de iş | Kurumsal araç + politika |
| Prompt'a müşteri ismi | Pseudonymize |
| API çağrısı zero retention kapalı | Sözleşme + ayar |
| DPIA yapılmamış | Yüksek risk için zorunlu |
| Model kart yok | Her sistem için |
| m.11/g açıklanabilirlik yok | XAI + manuel revize |
| Toplantı transcript açık rıza yok | Katılımcı onayı |
| RAG erişim filtresi yok | Kullanıcı yetkisi bazlı |
| Yurt dışı LLM Standart Sözleşme yok | Kurul bildirimi zorunlu |
| Halüsinasyon kontrolü yok | İnsan onayı kritik karar |

## 16. KPI'lar

| KPI | Hedef |
|-----|-------|
| Onaylı kurumsal AI araç kullanım oranı | %100 |
| Çalışan AI farkındalık eğitim tamamlanma | %100 yıllık |
| DPIA tamamlanma (yüksek riskli AI) | %100 |
| Model kart yayım | %100 |
| Kurumsal AI sözleşme zero retention | %100 |
| DLP prompt sızıntı engelleme | %95+ |
| AI envanteri güncellik | < 30 gün |
| Yurt dışı LLM Standart Sözleşme bildirim | %100 |

## 17. Yıllık AI Yönetişim Takvimi

| Çeyrek | Aksiyon |
|--------|---------|
| Q1 | AI envanteri güncelleme + risk sınıflandırma |
| Q2 | DPIA gözden geçirme; yeni sistemler |
| Q3 | Çalışan farkındalık eğitimi yenileme |
| Q4 | Yıllık AI yönetişim raporu (KVKK Komitesi) |
| Sürekli | Mevzuat takibi (Türkiye AI Kanunu, AB AI Act) |

## 18. Bağlantılı Bölümler

- `06-idari-tedbirler/` — AI farkındalık eğitimi.
- `07-aktarim/` — Yurt dışı aktarım.
- `10-ozel-konular/musteri-pazarlama-cms.md` — Pazarlama profilleme.
- `10-ozel-konular/bulut-hizmetleri.md` — Bulut LLM altyapı.

## 19. Versiyon Tarihçesi

| Versiyon | Tarih | Değişiklik | Onay |
|----------|-------|-----------|------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Komitesi + CTO |
