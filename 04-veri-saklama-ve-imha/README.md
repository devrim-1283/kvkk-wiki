---
Doküman / Document: Veri Saklama ve İmha — Bölüm Girişi / Data Retention and Destruction — Section Introduction
Bölüm / Section: 04-veri-saklama-ve-imha
Sahip / Owner: KVKK Sorumlusu / KVKK Officer
Onaylayan / Approved by: Hukuk Müdürü + Bilgi Güvenliği Yöneticisi / Legal Director + Information Security Manager
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş / Annual + triggered (mevzuat değişikliği, yeni veri kategorisi, sistem değişikliği, ihlal sonrası kök neden / regulatory change, new data category, system change, post-breach root cause)
İlgili Mevzuat / Legal Reference: Law No. 6698 (KVKK) Art. 4, 5, 6, 7, 12, 16; Regulation on Erasure, Destruction or Anonymization of Personal Data (28.10.2017 / OJ 30224, effective 01.01.2018) Art. 5–12; Data Security Guide (Technical and Administrative Measures); Tax Procedure Law No. 213; Turkish Commercial Code No. 6102; Labor Law No. 4857; Social Security Law No. 5510; Turkish Code of Obligations No. 6098; Law No. 5651
---

## English

# Section 04 — Data Retention and Destruction

## 1. Purpose of the Section

This section operationalizes all obligations of the data controller arising from KVKK Art. 7 and the Regulation on Erasure, Destruction or Anonymization of Personal Data. Pursuant to KVKK Art. 4(2)(d), personal data shall be retained "only for the period stipulated in the relevant legislation or required for the purpose of processing." Once that period expires, the data controller is obliged to **erase, destroy or anonymize** the data — either **ex officio** or **upon the data subject's request**.

The Regulation makes preparation of a **Personal Data Retention and Destruction Policy** mandatory for data controllers subject to the VERBİS registration obligation (Reg. Art. 5(1)). Data controllers with 500+ employees — except for sector-specific exemptions — fall within this obligation.

## 2. Section Contents

| # | Document | Purpose |
|---|----------|---------|
| 1 | [README.md](README.md) | Section introduction (this document) |
| 2 | [saklama-imha-politikasi-sablonu.md](saklama-imha-politikasi-sablonu.md) | Full policy template covering Reg. Art. 6 minimum content |
| 3 | [saklama-sureleri-tablosu.md](saklama-sureleri-tablosu.md) | Retention period table for 30+ data categories |
| 4 | [imha-yontemleri.md](imha-yontemleri.md) | Erasure, destruction and anonymization methods; medium-based matrix |
| 5 | [periyodik-imha-prosedur.md](periyodik-imha-prosedur.md) | Periodic and triggered destruction flows |
| 6 | [imha-kayit-tutanagi-sablonu.md](imha-kayit-tutanagi-sablonu.md) | Destruction record template (3-year retention per Reg. Art. 7(3)) |

## 3. Core Concepts (Reg. Art. 4)

- **Destruction (umbrella):** Refers to the erasure, destruction or anonymization of personal data.
- **Erasure (Reg. Art. 8):** Rendering personal data inaccessible and unusable in any way for **relevant users**.
- **Destruction (Reg. Art. 9):** Rendering personal data inaccessible, irretrievable and unusable in any way by **anyone**.
- **Anonymization (Reg. Art. 10):** Rendering personal data unable to be associated with an identified or identifiable natural person, even when matched with other data.
- **Periodic destruction:** Destruction performed ex officio at recurring intervals (maximum 6 months) specified in the policy, when all processing conditions cease.
- **Relevant user:** Persons who process personal data within the data controller's organization or in line with authorization/instruction. The person/unit responsible for the technical storage, protection and backup of the data is **excluded** from this definition.

## 4. The Obligation Triangle

```
                    KVKK Art. 4(2)(d)
                "Retention only as needed"
                        |
                        v
          +-------------+--------------+
          |                            |
          v                            v
     KVKK Art. 7                Reg. Art. 5–12
"Destroy when processing       "Policy + periods +
  conditions cease"             method + record"
          |                            |
          +-------------+--------------+
                        |
                        v
                   KVKK Art. 12
            "Technical+administrative measures"
```

The three obligations complement each other. If periods expire but destruction is not performed, Art. 4 is breached; if destruction is performed but method/record are missing, the Regulation is breached; if a destruction method is selected but is inadequate, Art. 12 is breached.

## 5. Responsibilities

| Role | Responsibility |
|------|----------------|
| Board of Directors | Approval of the policy, resource allocation, evaluation of audit results |
| KVKK Officer | Drafting the policy, alignment of periods with the inventory, coordination of periodic destruction, management of data subject requests |
| Legal Department | Legal scanning for retention periods, legal hold decisions due to litigation/objection |
| Information Security | Technical design of destruction methods, evidence collection (hash, log), secure destruction vendors |
| IT Operations | Implementation of destruction operations on systems, running retention jobs |
| Human Resources | Management of retention periods for employee/candidate data |
| Vendor / Procurement | Reflection of destruction commitments of data processors in contracts |

## 6. Relationship of This Section to Other Sections

- **02 — Inventory and Registry:** Retention periods must be one-to-one consistent with the inventory. The maximum periods in VERBİS are fed from the table in this section.
- **03 — Disclosure and Explicit Consent:** Periods stated in disclosure notices must match this policy.
- **05 — Technical Measures:** Technical infrastructure for destruction methods (crypto-erase, key management, hardware destruction).
- **08 — Breach Management:** Retention periods for breach records and forensic data may form an exception (legal hold).
- **09 — Data Subject Applications:** Erasure/destruction requests under Art. 12 are concluded within 30 days.

## 7. Audit Frequency

- **Monthly:** Retention job outputs, manual destruction records
- **Quarterly:** Policy-vs-inventory/disclosure consistency check
- **Annual:** Holistic review of the policy, regulatory change scan
- **Triggered:** Regulatory change, new business process, system change, root cause analysis after a breach

---

## Türkçe

# Bölüm 04 — Veri Saklama ve İmha

## 1. Bölümün Amacı

Bu bölüm, veri sorumlusunun KVKK m.7 ve Kişisel Verilerin Silinmesi, Yok Edilmesi veya Anonim Hale Getirilmesi Hakkında Yönetmelik kapsamındaki tüm yükümlülüklerini operasyonel düzeyde uygulanabilir hale getirir. KVKK m.4(2)(d) hükmü uyarınca kişisel veriler "ilgili mevzuatta öngörülen veya işlendikleri amaç için gerekli olan süre kadar" muhafaza edilir. Bu süre dolduğunda veri sorumlusu, **resen** veya **ilgili kişinin talebi üzerine** silme, yok etme veya anonim hale getirme yükümlülüğü altındadır.

İlgili Yönetmelik, VERBİS'e kayıt yükümlülüğü olan veri sorumluları için **Kişisel Veri Saklama ve İmha Politikası** hazırlanmasını zorunlu kılar (Yön. m.5(1)). 500+ çalışanlı veri sorumlusu kurumlar — istisnai sektörel muafiyetler dışında — bu yükümlülük kapsamındadır.

## 2. Bölüm İçeriği

| # | Doküman | Amaç |
|---|---------|------|
| 1 | [README.md](README.md) | Bölüm girişi (bu doküman) |
| 2 | [saklama-imha-politikasi-sablonu.md](saklama-imha-politikasi-sablonu.md) | Yön. m.6 asgari içeriği karşılayan tam politika şablonu |
| 3 | [saklama-sureleri-tablosu.md](saklama-sureleri-tablosu.md) | 30+ veri kategorisi için süre tablosu |
| 4 | [imha-yontemleri.md](imha-yontemleri.md) | Silme, yok etme ve anonim hale getirme yöntemleri; ortam bazlı matris |
| 5 | [periyodik-imha-prosedur.md](periyodik-imha-prosedur.md) | Periyodik ve tetiklenmiş imha akışları |
| 6 | [imha-kayit-tutanagi-sablonu.md](imha-kayit-tutanagi-sablonu.md) | Yön. m.7(3) gereği 3 yıl saklanacak imha tutanağı şablonları |

## 3. Temel Kavramlar (Yön. m.4)

- **İmha:** Kişisel verilerin silinmesi, yok edilmesi veya anonim hale getirilmesini ifade eder.
- **Silme (Yön. m.8):** Kişisel verilerin **ilgili kullanıcılar** için hiçbir şekilde erişilemez ve tekrar kullanılamaz hale getirilmesi.
- **Yok etme (Yön. m.9):** Kişisel verilerin **hiç kimse** tarafından hiçbir şekilde erişilemez, geri getirilemez ve tekrar kullanılamaz hale getirilmesi.
- **Anonim hale getirme (Yön. m.10):** Kişisel verilerin başka verilerle eşleştirilse dahi hiçbir surette kimliği belirli veya belirlenebilir bir gerçek kişiyle ilişkilendirilemeyecek hale getirilmesi.
- **Periyodik imha:** İşleme şartlarının tamamı ortadan kalktığında, politikada belirtilen tekrar eden aralıklarla resen gerçekleştirilen imha (azami 6 ay).
- **İlgili kullanıcı:** Veri sorumlusu organizasyonu içerisinde veya yetki/talimat doğrultusunda kişisel verileri işleyen kişiler. Verilerin teknik olarak depolanması, korunması ve yedeklenmesinden sorumlu kişi/birim **bu tanımın dışındadır**.

## 4. Yükümlülük Üçgeni

```
                    KVKK m.4(2)(d)
                "Gerekli süre kadar saklama"
                        |
                        v
          +-------------+--------------+
          |                            |
          v                            v
    KVKK m.7                      Yön. m.5–m.12
"İşleme şartları             "Politika + süreler +
ortadan kalkınca imha"        yöntem + tutanak"
          |                            |
          +-------------+--------------+
                        |
                        v
                 KVKK m.12
            "Teknik+idari tedbir"
```

Üç yükümlülük birbirini tamamlar. Süreler doldu ama imha yapılmadıysa m.4 ihlali; imha yapılıyor ama yöntem/tutanak yoksa Yönetmelik ihlali; imha yöntemi seçilmiş ama yetersizse m.12 ihlali oluşur.

## 5. Sorumluluklar

| Rol | Sorumluluk |
|-----|------------|
| Yönetim Kurulu | Politikanın onayı, kaynak tahsisi, denetim sonuçlarının değerlendirilmesi |
| KVKK Sorumlusu | Politikanın yazımı, sürelerin envanter ile uyumu, periyodik imha koordinasyonu, ilgili kişi taleplerinin yönetimi |
| Hukuk Müdürlüğü | Saklama süreleri için mevzuat tarama, dava/itiraz nedeniyle hukuki muhafaza (legal hold) kararları |
| Bilgi Güvenliği | İmha yöntemlerinin teknik tasarımı, kanıt toplama (hash, log), güvenli imha tedarikçileri |
| BT Operasyon | İmha işlemlerinin sistemler üzerinde uygulanması, retention job'ların çalıştırılması |
| İnsan Kaynakları | Çalışan/aday verilerinin sürelerinin yönetimi |
| Tedarikçi/Satınalma | Veri işleyenlerin imha taahhütlerinin sözleşmelere yansıtılması |

## 6. Bu Bölümün Diğer Bölümlerle İlişkisi

- **02 — Envanter ve Sicil:** Saklama süreleri envanter ile birebir tutarlı olmalıdır. VERBİS'teki azami süreler bu bölümdeki tablodan beslenir.
- **03 — Aydınlatma ve Açık Rıza:** Aydınlatma metinlerinde belirtilen süreler bu politika ile aynı olmalıdır.
- **05 — Teknik Tedbirler:** İmha yöntemlerinin teknik altyapısı (kripto-silme, anahtar yönetimi, donanım imhası).
- **08 — İhlal Yönetimi:** İhlal kayıtları ve forensic verisi için saklama süreleri istisna oluşturabilir (legal hold).
- **09 — İlgili Kişi Başvuruları:** m.12 silme/yok etme talepleri 30 gün içinde sonuçlandırılır.

## 7. Denetim Frekansı

- **Aylık:** Retention job çıktıları, manuel imha tutanakları
- **Çeyreklik:** Politika ile envanter/aydınlatma uyumu kontrolü
- **Yıllık:** Politikanın bütünsel gözden geçirilmesi, mevzuat değişikliği taraması
- **Tetiklenmiş:** Mevzuat değişikliği, yeni iş süreci, sistem değişikliği, ihlal kök neden analizi
