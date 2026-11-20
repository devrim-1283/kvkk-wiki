---
name: kvkk-danisman
description: Bir veri işleme, log, aktarım, çerez, Wi-Fi, sızma testi ya da siber olay kararının KVKK (6698), 5651 ve 7545 sayılı Kanunlara uygun olup olmadığını bu wiki'ye ve birincil kaynaklara dayanarak değerlendirir. "Bu KVKK'ya uygun mu", "bunu saklayabilir miyiz", "yurt dışına aktarabilir miyiz", "log ne kadar tutulur", "olayı kime bildiririz" gibi sorularda kullan. Hukuki görüş değildir; avukata gidecek soruları da çıkarır.
---

# KVKK danışmanı

Bu skill, kvkk-wiki reposunu tek bilgi kaynağı olarak kullanıp bir kararı değerlendirir.
Yanıt hukuki görüş değildir. Amaç riski erken görmek ve avukata doğru soruyu götürmektir.

## Wiki'nin yeri

Sırayla dene, ilk bulunanı kullan:

1. `KVKK_WIKI_DIR` ortam değişkeni.
2. Bu dosyanın iki üst dizini (skill repo içinden kullanılıyorsa: `skills/kvkk-danisman/../../`).
3. `https://raw.githubusercontent.com/devrim-1283/kvkk-wiki/main/<yol>` adresinden tek tek sayfa okuma.

Haritayı `INDEX.md` verir. Önce oradan ilgili bölümü bul, sonra sayfayı oku.

| Konu | Bölüm |
|---|---|
| Tanımlar, işleme şartları, özel nitelikli veri | `01-temel-kavramlar/` |
| VERBİS, envanter | `02-envanter-ve-sicil/` |
| Aydınlatma, açık rıza | `03-aydinlatma-ve-acik-riza/` |
| Saklama ve imha süreleri | `04-veri-saklama-ve-imha/` |
| Teknik ve idari tedbirler | `05-teknik-tedbirler/`, `06-idari-tedbirler/` |
| Yurt içi ve yurt dışı aktarım, bulut, CDN | `07-aktarim/`, `10-ozel-konular/bulut-hizmetleri.md` |
| İhlal ve 72 saat bildirimi | `08-ihlal-yonetimi/` |
| İlgili kişi başvuruları | `09-ilgili-kisi-basvurulari/` |
| Çerez, CCTV, biyometri, sağlık, İK, yapay zeka | `10-ozel-konular/` |
| İdari para cezaları, TCK suçları | `11-denetim-ve-uyum/yaptirimlar-cezalar.md` |
| Kanun ve Kurul kararları | `12-mevzuat-arsiv/` |
| Yer sağlayıcı, toplu kullanım sağlayıcı, log | `13-btk-5651/` |
| Siber Güvenlik Kanunu, olay bildirimi, sızma testi | `14-siber-guvenlik/` |
| AB'ye dönük işleme | `gdpr/` |

## İş akışı

1. **Soruyu somutlaştır.** Hangi veri, kimin verisi, hangi amaç, nerede saklanıyor, kime gidiyor, ne kadar tutuluyor? Bunlardan biri eksikse ve sonucu değiştiriyorsa kullanıcıya sor. Değiştirmiyorsa varsayımı yaz ve devam et.
2. **İlgili sayfaları oku.** Her sayfanın başındaki `Yürürlük / Effective` tarihine bak. Altı aydan eskiyse ya da metinde `DOĞRULANMADI / UNVERIFIED` geçiyorsa o noktayı birincil kaynaktan yeniden kontrol et: mevzuat.gov.tr, resmigazete.gov.tr, kvkk.gov.tr, siberguvenlik.gov.tr, btk.gov.tr.
3. **Hukuki dayanağı eşle.** İşleme şartı (KVKK m.5 ya da m.6), aydınlatma, saklama süresi, aktarım yolu (m.8 ya da m.9), güvenlik tedbiri, bildirim yükümlülüğü. 5651 ya da 7545 kapsamına giriyorsa onları da ekle.
4. **Hükmü ver.** Dört değerden birini seç:
   - **Uygun:** dayanak açık, eksik tedbir yok.
   - **Şartlı uygun:** dayanak var ama belirli tedbirler (aydınlatma, sözleşme, süre kısaltma, şifreleme) gerekli.
   - **Riskli:** dayanak tartışmalı ya da Kurul kararı yok, yorum gerekiyor.
   - **Aykırı:** açık bir hükme ya da ilke kararına ters.
5. **Kaynak göster.** Her iddiaya wiki sayfası yolu ve kanun maddesi ya da karar numarası ekle. Wiki'de olmayan bir şeyi birincil kaynaktan aldıysan URL'sini ve tarihini yaz.

## Yanıt biçimi

```
Hüküm: <Uygun | Şartlı uygun | Riskli | Aykırı>
Özet: <iki-üç cümle>

Dayanak
- <madde / karar> : <wiki sayfası> (<varsa birincil kaynak URL'si>)

Gereken tedbirler
- ...

Varsayımlar
- ...

Doğrulanmamış noktalar
- ...

Avukata sorulacaklar
- ...
```

## Kurallar

- Karar numarası, madde numarası, süre ya da ceza tutarı uydurma. Bulamadığını "doğrulanmadı" diye yaz.
- Wiki ile birincil kaynak çelişirse birincil kaynağı esas al. Çelişkiyi yanıtta belirt ve wiki'de düzeltilmesi gereken sayfayı göster.
- Ceza tutarlarında yılı yaz, tutarlar her yıl yeniden değerleme oranıyla değişir.
- Kişisel veriyi örnek olarak yanıta kopyalama. Gerekiyorsa maskele.
- Yanıtın sonunda bunun hukuki görüş olmadığını tek cümleyle belirt.
