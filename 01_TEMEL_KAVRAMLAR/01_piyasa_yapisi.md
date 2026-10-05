# 1. Piyasa yapısı: swing, BOS, MSS, CHoCH, CISD, displacement

Kaynaklar: N-ana (FluxCharts BOS/CHoCH/CHoCH+/CISD, innercircletrader.net MSS), N-A3, SG, EM, WB, LQ, TS, TTrades.

## 1.1 Swing tepe / dip
- **Swing high:** 3 mum. Ortadaki mumun tepesi, solundaki ve sağındaki mumun tepesinden yüksek. Swing low bunun aynası. [N-ana MSS makalesi, N-A3]
- **Swing'in sınıfları** [N-A3, ICT "Market Structure for Precision Technicians"]:
  - **STH/STL (kısa vade):** Sıradan swing.
  - **ITH/ITL (orta vade):** Bir imbalance dengelendiğinde oluşan swing ya da her iki yanında daha düşük STH olan STH. Bearish fikirde ITH kırılırsa fikir yanlıştır.
  - **LTH/LTL (uzun vade):** Günlük grafikteki seviyeler.
- **Strong / weak** [LQ s.50-61]:
  - **Strong low/high:** Manipülasyon yapıp (likidite alıp) yapıyı kıran uç.
  - **Weak:** Yapıyı kıramamış uç. "Her strong low'un bir weak high'ı vardır."
  - Mitigate edilen strong uç weak olur.
- **Protected swing** [TTrades]: CISD ile teyit edilmiş, girişin stop'unun arkasına konduğu swing.

## 1.2 Displacement
- Tek yönde güçlü hareket: büyük gövdeler, kısa fitiller, ideal olarak arkasında FVG bırakır. [N-ana MSS, TS, SG]
- "Displacement aralığında FVG yoksa işlem yok." [N-A3]
- **LQ'daki adları:** Algo candle / vector candle ("yutan mum").

## 1.3 BOS: Break of Structure
- **Devam sinyali:** Trend yönünde bir swing ucunun kırılması. [N-ana MSS, WB, N-A3]
- N-A3'e göre BOS, *güçlü* swing'lerin kırılmasıdır ve çok günlük trendi taşır; MSS'ten daha önemlidir.
- FluxCharts'a göre "BOS bir SMC kavramıdır, ICT değil." [N-ana]

## 1.4 MSS: Market Structure Shift
- **Tanım** [N-ana MSS makalesi]: Karşı yöndeki swing'in **displacement ile ve gövde kapanışıyla** kırılması. Fitil MSS sayılmaz.
- **Geçerlilik filtresi:** Önce o uçta likidite süpürülmüş olmalı. Sıra: sweep → tutunamama → ters yönde MSS.
- N-A3'e göre MSS aralık içindeki *minör* swing'in kırılmasıdır; ancak likidite alındıktan sonra anlamlıdır.
- **EM:** "yakın 5m-1m dip/tepe hızlı hareketle kırılır."
- **SG akış şeması:** FVG mumlarından biri swing high ile **tam yatay hizada** olmalı. Displacement mumları MSS'in olduğunu gösterir.
- **LQ:** Sahte BMS/FMS. Kırılım discount/premium'a gitmeden olduysa o dip HL değildir, yalnız likiditedir.

## 1.5 CHoCH ve CHoCH+
- **CHoCH:** Karşı trend swing'inin kırılması, displacement şartı yok. "Daha yavaş, daha yumuşak dönüş uyarısı." [N-ana MSS]
- **FluxCharts tanımı:** Daha önce BOS yapan trend bir daha BOS yapamaz ve ters yönde kırılım gelir. [N-ana]
- **CHoCH+** [N-ana FluxCharts]:
  - Bullish: L → LH → **başarısız LL** (yeni dip yapamaz) → LH'yi kıran HH.
  - Bearish ayna: H → HL → başarısız HH → HL'yi kıran LL.
  - Failure swing'li dönüş olduğu için CHoCH'tan güçlüdür. MSB (Market Structure Break) ≈ CHoCH+.
- **Failure swing** [LQ s.66-69, SG "Failed Swing" varyasyonları]: Fiyatın yeni LL/HH yapamaması.

## 1.6 CISD: Change in State of Delivery
- **FluxCharts adımları (bullish)** [N-ana]:
  1. Düşüş trendi (H-L-LH-LL).
  2. Önemli seviyenin (önceki seans/gün/hafta/ay dibi) altına inip hızla geri dönüş.
  3. Düşüşü başlatan mum serisinin **açılış fiyatının üstünde kapanış** → CISD.
  - CHoCH'tan erken gelir. Tek başına sinyal değil.
- **TTrades** [N-ana]: Dibi yapan mum serisini bul, fiyat bu serinin gövdesinden geri kapanırsa dönüş teyitli sayılır ve dip "protected swing" olur. "Intra-candle CISD" tercih edilir.
- **EM (1st Presented FVG modeli):** CISD veya MSS teyit olarak kullanılır.

## 1.7 Inducement (IDM)
- Büyük trend içindeki mini karşı trend tepelerinde/diplerinde biriken likidite. [TS, SG Model 2/4, LQ]
- **LQ:** "Inducement sadece likiditedir, OB'ye yakındır." En güçlü teyit sayılır.
- **SG Model 2:** BOS sonrası iç dip (IDM) süpürülür, sonra FVG'den giriş yapılır.

## 1.8 Institutional Order Flow (IOF)
- **WB:** W/D/4H'de dipler kırılıp tepeler dokunulmuyorsa IOF bearish, tersi bullish.
- **N-A3:**
  - Bearish'ken yukarı kapanışlı mumlar direnç olmalı, aşılmamalı.
  - Bullish'te aşağı kapanışlı mumlar destek olmalı.
  - Stop bu mumlara göre trail edilebilir.
- **LQ:** "Önce likidite, sonra IOF."

## 1.9 Fiyatın 4 hali
- Konsolidasyon → genişleme (expansion) → geri çekilme (retracement) → dönüş (reversal). [WB, N-A3]
- Seanslarla eşleşmesi [WB]:
  - Asya: konsolidasyon.
  - London açılışı: Judas, yani dönüş.
  - London → NY AM: genişleme.
  - NY öğle: geri çekilme.

## Kaynaklar arası farklar (bot için karar gerekiyor)
1. **MSS'in kırdığı swing:**
   - "En yakın karşı swing" [N-ana MSS, EM].
   - "Likiditeyi alan dipten önce oluşan swing high" [SG 2022 akış şeması].
   - "En yakın kısa vadeli swing" [N-A3].
2. **Kırılım şartı:**
   - Gövde kapanışı [N-ana MSS].
   - Kapanış şartı belirtilmemiş, "hızlı hareket" [EM].
   - Yatay çizgi FVG mumlarına değsin [SG].
3. **BOS/MSS/CHoCH adlandırması** her kaynakta farklı. Kullanıcının grafiklerinde yalnız "BOS" etiketi ve kesikli çizgi var (bkz. 03).

## Bot için ölçülebilir öneri (onay bekliyor)
- **Swing:** 3 mumlu pivot (sol 1, sağ 1). İsteğe bağlı olarak 2-2 veya 3-3 ile duyarlılık testi.
- **MSS:** Sweep'ten sonraki ilk karşı swing'in **gövde kapanışıyla** aşılması. Kıran bacakta en az bir FVG şart.
- **Displacement:** Kıran bacağın gövde/aralık oranı ≥ X. En büyük mum gövdesi ≥ Y×ATR. **X ve Y kullanıcı örneklerinden ölçülecek.**
