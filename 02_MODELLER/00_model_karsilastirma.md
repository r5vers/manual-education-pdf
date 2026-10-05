# Modellerin karşılaştırması (tek sayfa özet)

Bütün modeller aynı iskeletin varyasyonlarıdır: **bağlam → likidite alımı → yapı değişimi → giriş bölgesi → karşı likidite hedefi.**

| Model | Bağlam | Tetik (likidite) | Teyit | Giriş | Stop | Hedef | Zaman | Dosya | Önceki mekanik test |
|---|---|---|---|---|---|---|---|---|---|
| ICT 2022 | Günlük DOL / HTF bias | Bariz HTF BSL/SSL | MSS + displacement + FVG (%50'nin doğru tarafında) | FVG limit | Sweep ucu / FVG mumları | Karşı likidite, ≥2R | AM 8:30-11, PM 13:30+, killzone | 01 | M01/M01b: kenar yok |
| TTFM | Üst TF C2/C3 kapanışı | Üst TF fitili | Alt TF CISD → protected swing | Swing / kapanış / %50 CISD | Protected swing | 2R+, üst TF hedefi | HTF fitili oluşmuşsa | 02 | M02: kenar yok |
| Silver Bullet | Mevcut yön | — | Pencere içi FVG | FVG | FVG ucu | DOL (≥10 puan) | 03-04, 10-11, 14-15 | 03 | M04: kenar yok |
| NY Open Macro | 08:30 açılışına göre konum | 09:30-09:40 sweep | MSS | FVG + BB / VI | — | ~10 puan, ≥1:2 | 09:30-10:10 | 03 | Test edilmedi |
| 1st Presented FVG | Bias + DOL | Stop raid (Judas) | CISD / MSS | İlk FVG (veya inverse'i) | — | DOL | 09:30-10:00 | 03 | Test edilmedi |
| Unicorn | HTF bias | Swing kırılımı | Breaker + örtüşen FVG | FVG'ye dokunuş | Breaker + FVG ucu | Engineered likidite | — | 04 | Test edilmedi |
| IFVG | HTF anlatı | Anlamlı stop hunt | FVG'nin gövde kapanışıyla ters kırılması | IFVG geri testi | IFVG ötesi | Likidite (veya 1:2) | Killzone | 04 | M09: kenar yok |
| OTE | DOL | Likidite | Displacement / MSS | 0.62-0.79'daki FVG/OB | Swing ucu | -0.5/-1/-1.5/-2 | 08:30-11:00 | 04 | Test edilmedi |
| SG Model 1-4 | HTF POI | LTF likidite alımı (veya failed swing / SMT) | BOS + displacement + FVG (+ IDM, + OTE) | FVG | — | İyi R:R | — | 05 | (≈ICT 2022) |
| Box (Model 5) | HTF POI | Konsolidasyon dışına agresif çıkış | Agresif geri dönüş | Konsolidasyon ucunun yeniden testi | — | — | — | 05 | Test edilmedi |
| ATM | — | BSL | Swing low kırılımı | FVG/BB/OB | — | 15m/1H dip | Her TF | 05 | (≈ICT 2022) |
| Breaker Buy/Sell | HTF discount/premium array | Önce karşı taraf, sonra bu taraf purge | Swing kırılımı | Breaker yeniden testi | Breaker'ın öbür ucu | Karşı breaker | — | 06 | Test edilmedi |
| MMBM/MMSM | HTF array | Konsolidasyon likiditesi | Smart money reversal | 1. ve 2. bacak | — | Orijinal konsolidasyon ucu | — | 06 | Test edilmedi |
| Turtle Soup | HTF PD array | Sahte dip altı sweep | (SMT) | — | — | — | Zamanla | 07 | M07: kenar yok |
| Tek mum sweep (TS) | HTF | Tek mum sweep + sonraki mum şartı | LTF CHoCH | OB/FVG | OB ötesi + tampon | Karşı swing | — | 07 | Test edilmedi |
| PDH/PDL raid + DXY | PDH/PDL | PDH/PDL raid | BOS + FVG + DXY teyidi | %50'nin doğru tarafındaki ilk POI | Raid ucu | 3R | LOKZ / NYKZ | 07 | Benzeri test edildi: kenar yok |
| Sweep + SMT + BMS + IFVG | — | Sweep | SMT + BMS | Kıran mumun 5m FVG'si | Boşluk ötesi | Sonraki stop bölgesi | — | 04 | Test edilmedi |

"Önceki mekanik test" sütunu, azeghor-1-base-eurusd reposundaki `arastirma/2026-10-02_model_turnuvasi` sonuçlarıdır.
- **Test koşulları:** 2013-2023 verisi, maliyet dahil, ön-kayıtlı.
- **"Kenar yok" ne demek:** Literatürdeki varsayılan tanımın maliyet sonrası istatistiksel olarak sıfırdan ayrışmadığı.
- **Ne demek değil:** Kullanıcının elle uyguladığı sürümün de kenarsız olduğu.
