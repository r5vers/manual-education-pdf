# Azeghor – Manuel Eğitim Arşivi (düzenlenmiş)

Bu repo, Notion'daki **"azeghor manual education"** sayfasının ve buraya yüklenen PDF'lerin derlenmiş halidir.
- **Kapsam:** Notion ana sayfa, 6 alt sayfa, 44 görsel, 5 PDF (367 sayfa).
- **İşlem:** Tamamı okundu, konulara göre ayrıldı, tekrarlar birleştirildi, Türkçe makine çevirisi hataları düzeltildi.
- **Amaç:** Telegram gözcü botu için kullanıcının işlem tarzını kurallara dökmek.

## Okuma sırası
1. **[05_EKSIKLER_SORULAR_CELISKILER.md](05_EKSIKLER_SORULAR_CELISKILER.md):** Önce bu. Eksikler, çelişkiler ve 12 soru burada.
2. **[03_KULLANICININ_ISLEMLERI/](03_KULLANICININ_ISLEMLERI/README.md):** 39 kendi ekran görüntün ve onlardan çıkan ortak desen.
3. **[02_MODELLER/00_model_karsilastirma.md](02_MODELLER/00_model_karsilastirma.md):** Tüm modeller tek tabloda.
4. **[04_BOT_ICIN_KURAL_TASLAKLARI/](04_BOT_ICIN_KURAL_TASLAKLARI/README.md):** Bot için taslak kural ve doğrulama planı (onaysız).
5. Kavramlara ihtiyaç oldukça 01, terimler için 06.

## Klasörler
```
00_KAYNAKLAR/
  KAYNAK_ENVANTERI.md      her kaynağın ne olduğu, kısaltması, nereye taşındığı, tekrarlar
  pdf/                     5 PDF (adlandırılmış)
01_TEMEL_KAVRAMLAR/
  01_piyasa_yapisi.md      swing, BOS, MSS, CHoCH/CHoCH+, CISD, displacement, inducement, IOF
  02_likidite.md           BSL/SSL, seviye hiyerarşisi, grab/sweep, IRL/ERL, dealing range, DOL
  03_fvg_ailesi.md         FVG, CE, giriş/stop tipleri, IFVG, BPR, VI, liquidity void, breakaway
  04_bloklar.md            OB, breaker, rejection, unicorn, algo candle, PD array matrisi
  05_premium_discount_ote.md
  06_zaman.md              tüm killzone/seans saatleri tek tabloda, Silver Bullet, açılışlar, takvim
  07_bias_anlati_po3.md    yukarıdan aşağı analiz, günlük bias, anlatı, PO3/AMD, döngüler
  08_smt_korelasyon.md
  09_indikatorler.md       grafiklerinde görülen indikatörler, TDI ayarları
02_MODELLER/
  00_model_karsilastirma.md
  01_ict_2022.md           (en çok kaynak + senin işlemlerine en yakın)
  02_ttfm_fraktal.md
  03_zaman_tabanli_modeller.md     Silver Bullet, NY Open Macro, 1st Presented FVG
  04_fvg_tabanli_girisler.md       Unicorn, IFVG, OTE
  05_ogrenci_rehberi_modelleri.md  SG Model 1-5, ATM
  06_breaker_ve_market_maker.md    Breaker Buy/Sell, MMBM/MMSM, AMD
  07_likidite_tuzagi_modelleri.md  Turtle Soup, tek mum sweep, PDH/PDL+DXY
  08_lq_kitabi_algo_yaklasimi.md
03_KULLANICININ_ISLEMLERI/
  README.md                39 görselin katalogu + ortak desen + sınırlar
  gorseller/               01_IMG_7132.png … 39_IMG_1816.png
04_BOT_ICIN_KURAL_TASLAKLARI/
  README.md
05_EKSIKLER_SORULAR_CELISKILER.md
06_SOZLUK.md               çeviri düzeltmeleri + kısaltmalar
```

## Kaynak gösterimi
Her bilginin yanında köşeli parantezde kaynağı var. Örnekler:
- `[SG s.18]`: Student's Guide PDF, 18. sayfa.
- `[N-A3]`: Notion alt sayfası "2022 Mentorship Notes".
- `[K21]`: Senin 21. ekran görüntün.

Liste: [00_KAYNAKLAR/KAYNAK_ENVANTERI.md](00_KAYNAKLAR/KAYNAK_ENVANTERI.md)

## Neler yapılmadı
- **Notion'daki orijinal metin** silinmedi veya değiştirilmedi.
- **Dış görseller kopyalanmadı:** Makale kırpıntıları ve başkalarına ait 5 galeri görseli. İçerikleri yazıya aktarıldı.
- **Bot kodu:** Hiçbir değişiklik yapılmadı.
