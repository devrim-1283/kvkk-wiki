---
Doküman / Document: 02 - Envanter ve Sicil (Bölüm Girişi) / 02 - Inventory and Registry (Section Entry)
Bölüm / Section: 02-envanter-ve-sicil
Sahip / Owner: KVKK Sorumlusu / KVKK Officer
Onaylayan / Approved by: Hukuk Müdürü + KVKK Komitesi / Head of Legal + KVKK Committee
Versiyon / Version: 1.0
Yürürlük / Effective: 2026-05-08
Gözden Geçirme / Review: Yıllık + tetiklenmiş / Annual + triggered
İlgili Mevzuat / Legal Reference: 6698 sayılı KVKK m.16 / Law No. 6698 on the Protection of Personal Data Art. 16; Veri Sorumluları Sicili Hakkında Yönetmelik (RG: 30.12.2017/30286) / Regulation on the Data Controllers' Registry (Official Gazette 30.12.2017/30286), MADDE 4(h), 5(ç), 8-15 / Art. 4(h), 5(ç), 8-15; Aydınlatma Tebliği (RG: 10.03.2018/30356) / Disclosure/Information Notice Communiqué (Official Gazette 10.03.2018/30356); Kurul'un VERBİS kayıt yükümlülüğü kapsam ve istisnalarına ilişkin kararları / Board decisions on the scope of and exceptions to the VERBİS (Data Controllers' Registry Information System) registration obligation
---

## English

# 02 - Inventory and Registry

## 1. Purpose of This Section

This section contains the document set required to operationally manage, in our capacity as data controller, the preparation of the **Personal Data Processing Inventory (KVKİ — Kişisel Veri İşleme Envanteri)** and registration with the **Data Controllers' Registry (VERBİS — Veri Sorumluları Sicili Bilgi Sistemi)**. The KVKİ inventory and VERBİS obligations follow directly from KVKK Art. 16 and from the Regulation on the Data Controllers' Registry (the "Regulation"), in particular Art. 4(h), 5(ç) and Art. 8-14.

Article 5(ç) of the Regulation provides that "the information disclosed to the Registry in registry applications is prepared **on the basis of the Personal Data Processing Inventory**", which makes the **inventory a mandatory precondition of VERBİS registration**. Under Art. 5(d), the inventory is the **primary reference document** for satisfying the disclosure (information notice) obligation, responding to data subject requests, and determining the scope of explicit consent.

For these reasons the inventory is not merely a compliance artifact — it is the operational core of the KVKK compliance architecture.

## 2. Scope of This Section

| # | Document | Purpose |
|---|----------|---------|
| 1 | [README.md](./README.md) | Section entry (this document) |
| 2 | [kvki-envanteri-rehberi.md](./kvki-envanteri-rehberi.md) | KVKİ preparation methodology, content, ownership |
| 3 | [envanter-sablonu.md](./envanter-sablonu.md) | 27-column fillable inventory template, sample rows, CSV headers |
| 4 | [verbis-kayit-rehberi.md](./verbis-kayit-rehberi.md) | VERBİS registration obligation, screen-by-screen steps, change notifications |
| 5 | [verbis-istisna-degerlendirmesi.md](./verbis-istisna-degerlendirmesi.md) | Exceptions under Art. 15-16 of the Regulation, threshold decisions, decision tree |
| 6 | [envanter-bakim.md](./envanter-bakim.md) | Periodic review, change triggers, compliance checklist |

## 3. Roles and Responsibilities

| Role | Responsibility |
|------|----------------|
| KVKK Officer | Keeps the inventory continuously up to date; single point of contact for VERBİS notifications; prepares exception assessments |
| Contact Person (Reg. Art. 4/ç, Art. 11/4) | Maintains communication with the Authority; communication-facilitator role for data subject requests; **is not a representative** |
| Process Owner (each business unit) | Prepares and validates inventory rows for its own processes; reports changes to the KVKK Officer within 5 business days |
| Legal Department | Approves the determination of legal grounds; aligns retention periods with legislation; legally reviews exception assessments |
| Information Security | Completes the technical measures section; verifies data storage media and transfer channels |
| KVKK Committee | Reviews the inventory and VERBİS records on a quarterly basis; approves exception and risk-level decisions |

## 4. Key Obligations (Quick Reference)

- **Inventory obligation:** Reg. Art. 5(ç), Art. 4(h) — every data controller subject to VERBİS must maintain an inventory.
- **Start of registration:** Reg. Art. 8(1) — registration with the Registry **before** processing begins.
- **Becoming subject afterwards:** Reg. Art. 8(2) — registration within **30 days** of becoming subject to the obligation.
- **Request for additional time:** Reg. Art. 8(3) — in cases of factual, technical or legal impossibility, written application to the Authority within **7 business days** from the date the impossibility arose; up to **30 additional days** may be granted on a one-off basis.
- **Change notification:** Reg. Art. 13 — any change in the information registered in the Registry must be notified via VERBİS within **7 days**.
- **Removal from the Registry:** Reg. Art. 14 — application for removal when the activity ceases; obligations relating to the registered period continue.
- **Administrative sanction:** Reg. Art. 17, KVKK Art. 18(1)(ç) — administrative fines apply in case of breach of registration and notification obligations.

## 5. Links to Other Sections

| Linked Section | Relationship |
|----------------|--------------|
| 03 - Disclosure and Explicit Consent | Information notices are produced from inventory rows (Reg. Art. 5/d) |
| 04 - Data Retention and Destruction | Retention periods are defined in the inventory; the destruction policy is built upon the inventory (Reg. Art. 9/5) |
| 05 - Technical Measures | Reflected in the "measures taken" column of the inventory |
| 06 - Administrative Measures | The inventory itself is an administrative measure |
| 07 - Transfer | The "recipient/recipient group" and "cross-border transfer" columns of the inventory form the basis of the transfer regime |
| 09 - Data Subject Requests | Responses to KVKK Art. 11 rights are prepared from the inventory |

## 6. Document Hierarchy

```
KVKK Policy (top-level document)
   └── KVKİ Inventory (operational core)
         ├── VERBİS Notification (publicly disclosed summary)
         ├── Information Notices (per process)
         ├── Explicit Consent Texts (where required)
         ├── Retention and Destruction Policy
         └── Transfer Agreements / Undertakings
```

## 7. Recommended Use

1. Before designing a new process, read **kvki-envanteri-rehberi.md**.
2. Copy **envanter-sablonu.md** and fill it in for the relevant process.
3. The KVKK Officer validates the row; obtain Legal Department opinion where required.
4. Register / update via VERBİS using **verbis-kayit-rehberi.md**.
5. Run quarterly review against the **envanter-bakim.md** checklist.

## 8. Change History

| Version | Date | Change | Prepared by |
|---------|------|--------|-------------|
| 1.0 | 2026-05-08 | Initial publication | KVKK Officer |

---

## Türkçe

# 02 - Envanter ve Sicil

## 1. Bölümün Amacı

Bu bölüm, veri sorumlusu sıfatıyla şirketimizin **Kişisel Veri İşleme Envanteri (KVKİ)** hazırlama ve **Veri Sorumluları Sicili (VERBİS)** kaydı süreçlerini operasyonel düzeyde yönetmek için gereken doküman setini içerir. KVKİ ve VERBİS yükümlülükleri; KVKK m.16 ile Veri Sorumluları Sicili Hakkında Yönetmelik (Yön.) MADDE 4(h), 5(ç) ve MADDE 8-14 hükümlerinin doğrudan sonucudur.

Yönetmelik MADDE 5(ç) "Sicil başvurularında Sicile açıklanacak bilgiler **Kişisel Veri İşleme Envanterine dayalı olarak** hazırlanır" hükmü gereği, **envanter VERBİS kaydının zorunlu önkoşuludur**. Aynı maddenin (d) bendi gereği envanter; aydınlatma yükümlülüğü, ilgili kişi başvurularının yanıtlanması ve açık rızanın kapsamının belirlenmesinde **temel referans dokümandır**.

Bu nedenle envanter; sadece bir uyum belgesi değil, KVKK uyum mimarisinin merkezidir.

## 2. Bölüm Kapsamı

| # | Doküman | Amaç |
|---|---------|------|
| 1 | [README.md](./README.md) | Bölüm girişi (bu doküman) |
| 2 | [kvki-envanteri-rehberi.md](./kvki-envanteri-rehberi.md) | KVKİ hazırlama metodolojisi, içerik, sahiplik |
| 3 | [envanter-sablonu.md](./envanter-sablonu.md) | 27 sütunlu doldurulabilir envanter şablonu, örnek satırlar, CSV başlıkları |
| 4 | [verbis-kayit-rehberi.md](./verbis-kayit-rehberi.md) | VERBİS kayıt yükümlülüğü, ekran-ekran adımlar, değişiklik bildirimi |
| 5 | [verbis-istisna-degerlendirmesi.md](./verbis-istisna-degerlendirmesi.md) | Yön. M.15-16 istisnaları, eşik kararları, karar ağacı |
| 6 | [envanter-bakim.md](./envanter-bakim.md) | Periyodik gözden geçirme, değişiklik tetikleyicileri, uyum kontrol listesi |

## 3. Roller ve Sorumluluklar

| Rol | Sorumluluk |
|-----|-----------|
| KVKK Sorumlusu | Envanterin sürekli güncel kalmasını sağlamak; VERBİS bildirimlerinin tek temas noktası; istisna değerlendirmesini hazırlamak |
| İrtibat Kişisi (Yön. M.4/ç, M.11/4) | Kurum ile iletişimi sağlamak; ilgili kişi başvurularının cevaplanmasında iletişim kurucu rolü; **temsilci değildir** |
| Süreç Sahibi (her iş birimi) | Kendi süreçlerine ait envanter satırlarını hazırlamak ve doğrulamak; değişiklikleri 5 iş günü içinde KVKK Sorumlusu'na bildirmek |
| Hukuk Müdürlüğü | Hukuki sebep tespitini onaylamak; saklama sürelerini mevzuatla uyumlandırmak; istisna değerlendirmesini hukuken kontrol etmek |
| Bilgi Güvenliği | Teknik tedbirler bölümünü doldurmak; veri kayıt ortamı ve aktarım kanallarını teyit etmek |
| KVKK Komitesi | Envanter ve VERBİS kayıtlarını çeyrek dönemlik gözden geçirmek; istisna ve risk seviyesi kararlarını onaylamak |

## 4. Anahtar Yükümlülükler (Hızlı Referans)

- **Envanter zorunluluğu:** Yön. M.5(ç), M.4(h) — VERBİS yükümlüsü olan her veri sorumlusu envanter tutmak zorundadır.
- **Kayıt başlangıcı:** Yön. M.8(1) — Veri işlemeye **başlamadan önce** Sicile kayıt yapılır.
- **Sonradan yükümlü olanlar:** Yön. M.8(2) — Yükümlü hale gelmeyi takiben **30 gün** içinde kayıt.
- **Ek süre talebi:** Yön. M.8(3) — Fiili/teknik/hukuki imkansızlık halinde imkansızlığın doğduğu tarihten itibaren **7 iş günü** içinde Kurum'a yazılı başvuru; en fazla **30 gün** ek süre.
- **Değişiklik bildirimi:** Yön. M.13 — Sicilde kayıtlı bilgilerde değişiklik halinde **7 gün** içinde VERBİS üzerinden bildirim.
- **Sicil silinmesi:** Yön. M.14 — Faaliyet sona erdiğinde silme başvurusu; ancak kayıtlı dönemdeki yükümlülükler devam eder.
- **İdari yaptırım:** Yön. M.17, KVKK m.18(1)(ç) — Sicile kayıt ve bildirim yükümlülüğüne aykırılık halinde idari para cezası.

## 5. Diğer Bölümlerle Bağlantı

| Bağlantılı Bölüm | İlişki |
|------------------|--------|
| 03 - Aydınlatma ve Açık Rıza | Aydınlatma metinleri envanter satırlarından üretilir (Yön. M.5/d) |
| 04 - Veri Saklama ve İmha | Saklama süreleri envanterde tanımlanır; imha politikası envantere dayanır (Yön. M.9/5) |
| 05 - Teknik Tedbirler | Envanterin "alınan tedbirler" kolonuna yansıtılır |
| 06 - İdari Tedbirler | Envanter bizzat bir idari tedbirdir |
| 07 - Aktarım | Envanterdeki "alıcı/alıcı grubu" ve "yurt dışı aktarım" kolonları aktarım rejiminin tabanıdır |
| 09 - İlgili Kişi Başvuruları | 11. madde haklarına cevap envanter üzerinden hazırlanır |

## 6. Doküman Hiyerarşisi

```
KVKK Politikası (üst doküman)
   └── KVKİ Envanteri (operasyonel kalp)
         ├── VERBİS Bildirimi (kamuya açık özet)
         ├── Aydınlatma Metinleri (her süreç için)
         ├── Açık Rıza Metinleri (gerekli süreçlerde)
         ├── Saklama ve İmha Politikası
         └── Aktarım Sözleşmeleri / Taahhütnameler
```

## 7. Kullanım Önerisi

1. Yeni bir süreç tasarımına başlamadan önce **kvki-envanteri-rehberi.md** dokümanı okunur.
2. **envanter-sablonu.md** kopyalanır, ilgili süreç için doldurulur.
3. KVKK Sorumlusu doğrular; gerekiyorsa Hukuk Müdürlüğü görüşü alınır.
4. **verbis-kayit-rehberi.md** üzerinden VERBİS kaydı yapılır/güncellenir.
5. **envanter-bakim.md** kontrol listesine göre çeyreklik gözden geçirme yapılır.

## 8. Değişiklik Geçmişi

| Versiyon | Tarih | Değişiklik | Hazırlayan |
|----------|-------|-----------|-----------|
| 1.0 | 2026-05-08 | İlk yayım | KVKK Sorumlusu |
