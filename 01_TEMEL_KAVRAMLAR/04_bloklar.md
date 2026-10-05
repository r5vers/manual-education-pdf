# 4. Bloklar: Order Block, Breaker, Rejection, Mitigation, Unicorn, Algo Candle

Kaynaklar: N-ana (FluxCharts OB/Breaker), N-A3, N-A5, SG, EM, WB, LQ, TS.

## 4.1 Order Block (OB)
- **Tanım (çoğunluk):**
  - Bullish OB: enerjik yükselişten önceki **son aşağı kapanışlı mum(lar)**.
  - Bearish OB: enerjik düşüşten önceki **son yukarı kapanışlı mum(lar)**. [WB, N-ana]
- **N-A3'ün daha dar tanımı:**
  - Bullish OB = destek seviyesi yakınında, açılış-kapanış aralığı en büyük olan aşağı kapanışlı mum.
  - Yüksek olasılıklı OB'nin şartları:
    - Likidite alımı.
    - BOS.
    - FVG + displacement. Displacement OB'nin 2-3 katı olmalı.
    - Seans içinde oluşmuş olmalı.
- **Çizim** [N-A3]:
  - Fitil bir FVG ile örtüşüyorsa fitil kullanılır, örtüşmüyorsa gövde.
  - Ayrı bir notta "gövdeyle çiz" diyor.
  - Önemli olan %50, yani mean threshold.
- **Geçersizlik:** Tepki olmadan içinden geçilirse ya da mean threshold aşılırsa. [N-A3]
- **FluxCharts'ın ek teyidi:** 9/21 EMA kesişimi, 1:1.5. Bu ICT dışı bir ekleme. [N-ana]
- **N-A5 hatası:** "OB = displacement öncesi son yukarı mum" diyor. Bu yalnız **bearish** OB için doğru.

## 4.2 Breaker block
- **Tanım:** Likidite alınır, ardından MSS gelir. Kırılan swing'in bölgesi yeniden test edilir. [N-A3, WB, SG]
  - **Bullish breaker:** Eski dip süpürülür. Ondan önceki son swing high'ın son yukarı mumu (bölgesi) kırılınca, geri testte long.
  - **Bearish breaker:** Ayna. Swing low'un son aşağı mumu kullanılır.
- **Modeller:** Breaker Buy/Sell Model [SG s.16-17]: purged side → HTF array → breaker yeniden testi → stop breaker'ın öbür ucu.
- **LQ:** "Momentum kayması agresifse breaker güçlüdür."
- **FluxCharts:** "Geçersiz OB." Fitil mi kapanış mı tartışmalı.

## 4.3 Unicorn
- Breaker bloğu ile **örtüşen** FVG. [EM]
- Detay: 02_MODELLER/04.

## 4.4 Rejection block
- Uzun fitilli tepe/dipte gövdenin ötesindeki fitil bölgesi. Fiyat fitille likiditeyi alıp döner. [N-A3, LQ]
- **LQ:**
  - Güçlü rejection block = inducement + seans tepe/dibinde oluşum.
  - "HTF rejection block = LTF algo candle."

## 4.5 Mitigation, propulsion, vacuum blokları
- Yalnız adları geçiyor (SG reklam sayfası, N-A3 PD array matrisi). **Tanımları kaynaklarda yok.**

## 4.6 Algo candle (LQ'ya özgü)
- Likiditeyi alan ve hemen ardından FVG oluşturan mum. Tepeyi/dibi "strong" yapan şey budur.
- "Very strong AC" = likidite alır + strong high/low kırar + inducement + FVG.
- Bu ICT'nin "OB + displacement" fikrine yakın, ama terim ICT dışı.

## 4.7 PD Array Matrisi (öncelik sırası) [N-A3]
- **Premium (yukarıdan aşağı):** Old high/low, rejection block, bearish JB, FVG, liquidity void, bearish breaker, mitigation block.
- **Discount:** Aynı sıranın aynası.
- **"JB" kaynakta açıklanmamış.** Muhtemelen bir blok türü kastediliyor.
- **Bearish breaker notu:** "Fiyatın OB'ye ulaşmasını engeller, en baskın PD array'dir." Liste sırasıyla çelişkili bir not.

## Bot için ölçülebilir öneri
- **OB:** MSS bacağını başlatan son karşı renkli mum. Bölge = gövde.
  - Fitil/gövde tercihi **kullanıcıdan**.
- **Breaker:** Sweep → MSS sonrası, sweep'ten önceki son karşı swing'in son karşı mumu.
- **Kullanıcının grafiklerindeki "gri bölge":** FVG mi OB mi bilinmiyor. **Kullanıcıya soru.**
