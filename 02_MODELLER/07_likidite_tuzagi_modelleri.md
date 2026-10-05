# Likidite tuzağı modelleri: Turtle Soup, tek mum sweep + CHoCH, PDH/PDL raid + DXY, Sick Sister

## A. Turtle Soup [SG s.31]
- **Koşullar:**
  1. Fiyat HTF PD array'e ulaşmadan zıplar ve "sahte dip" yapar.
  2. Fiyat aşağı süpürüp HTF PD array'e girer (POI).
  3. Erken alanlar stoplanır.
  4. Offset birikim/dağıtım olur; smart money emirleri burada eşleşir.
  5. Long'da sell stop'lar alınır, short'ta buy stop'lar satılır.
  6. Korele çiftte SMT beklenir.
- "Trade'i zaman çerçevesine oturtmak önemli."
- **Önceki test:** M07 (1H, 20 mumluk yeni dip + geri kapanış) **kenar vermedi.**

## B. Tek mum sweep + LTF CHoCH ("Liquidity Sweep Strategy") [TS; N-ana içindeki Türkçe özet aynı]
1. **HTF'de tek mum sweep:** Önceki yapının dibi tek mumun gövdesi veya fitiliyle alınır, ardından ani güçlü yükseliş gelir.
   - **Geçerlilik:** Sweep'ten sonraki mum, sweep mumunun ne tepesini aşmalı ne dibinin altında kapanmalı.
2. **LTF'ye inilir, CHoCH beklenir:** Son LH kırılmalı.
3. **Giriş:** OB'ye veya FVG'ye limit emir. İkisi tek bölge sayılıp ortasından da girilebilir.
4. **Stop ve hedef:**
   - Stop: OB'nin ötesi + spread tamponu.
   - Hedef: sonraki karşı swing.
- **Not:** TS "ICT yüksek kazanma oranına sahip, kullananlara göre" diyor; kanıt yok.

## C. PDH/PDL raid + DXY stratejisi [N-ana MQL5 blog]
- **Yalnız** önceki günün tepe/dibinin (dış range likiditesi) manipülasyonu işlenir.
- **Zaman:** Yalnız LOKZ 02:00-05:00 ve NYKZ 07:00-10:00 (NY).
- **Adımlar:**
  1. PDH veya PDL alınır. HTF seviyeyle çakışması artı puan.
  2. BOS + displacement + FVG. **FVG'siz BOS = giriş yok.**
  3. %50 fib'in doğru tarafındaki ilk POI'den girilir: FVG, OB veya OTE 70.5.
  4. Stop raid ucunun ötesi, hedef 3R.
  5. DXY teyidi: DXY kendi karşı seviyesini almadan EURUSD long açılmaz.
- **Kurallar:**
  - Başka bir PDH/PDL yakındaysa işlem yok.
  - EQH satılmaz, EQL alınmaz.
  - Asya trend yapıyorsa London atlanır.
  - Risk %0.25-1, en fazla 20 pip SL.
  - Günde 3R kazanılınca dur, haftada 6R.
  - Parite başına en az 200 işlem backtest.
- **Kanıtsız iddia:** "Ayda 20R tutarlı getiri, prop firm sınavlarını geçirir." Yazı, MT4 indikatörünün satış sayfası. **İddia kanıtsız.**

## D. Sick Sister [SG s.32-33]
Bkz. 01/08_smt_korelasyon.
