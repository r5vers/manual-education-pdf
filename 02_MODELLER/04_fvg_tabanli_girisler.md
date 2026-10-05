# FVG tabanlı giriş modelleri: Unicorn, IFVG, OTE

## A. Unicorn [EM s.10-12]
1. **Tanımla:**
   - Bir swing tepe veya dip kırılır.
   - Kırılım noktasında bir breaker bloğu oluşur.
   - Breaker ile **örtüşen** bir FVG vardır.
2. **Uygula:**
   - Fiyatın FVG'ye dokunması beklenir.
   - Stop, breaker ve FVG'nin ucunun ötesine konur.
   - FVG'nin tamamen dolması beklenmez.
   - Unicorn'un altında kalan boşluklar açık kalmalıdır; bu, niyeti ve hızı gösterir.
3. **Hedef:**
   - Bias yönündeki engineered likidite.
   - ICT standart sapma projeksiyonları.
- **Önkoşul:** Net HTF bias ve anlatı.
- **Örnekler:**
  - NASDAQ M1 bullish.
  - PDH stop raid → MSS → -breaker + FVG → REQL hedefi.

## B. IFVG: Inversion FVG modeli [EM s.13-18, N-ana FluxCharts, N-ana Reddit]
- **EM çerçevesi:**
  1. Likidite alınır. Anlamlı bir seviye olmalı: PDH/PDL, seans ucu ya da range ucu.
  2. Displacement oluşur.
  3. FVG **gövde kapanışıyla** ters yönde ihlal edilir ve IFVG oluşur.
  4. IFVG'ye geri çekilme beklenir.
  5. Karşı likidite hedeflenir (RR değil, likidite).
- **EM'nin hatırlattıkları:**
  - IFVG beklenti değil, zaten başlamış bir değişimin ifadesidir.
  - Önce geçerli bir FVG olmalı.
  - Killzone ve makro içinde daha iyi çalışır.
- **FluxCharts / @DodgysDD:**
  - Grab → IFVG oluşunca gir (fitil **veya** kapanış yeterli sayılıyor).
  - SL IFVG'nin ötesi, hedef 1:2.
- **Reddit 6 adım:**
  1. Likidite bölgelerini işaretle.
  2. Sweep'i izle.
  3. SMT ara.
  4. BMS: güçlü bir mum seviyenin ötesinde kapanır.
  5. Yapıyı kıran mumun 5m FVG'si.
  6. O boşluğa dönüşte gir; SL boşluğun ötesi, TP sonraki stop bölgesi.
- **Önceki test:** M09 (15m IFVG) mekanik testte **kenar vermedi.**

## C. OTE modeli [EM s.24-26, SG s.28-29, WB s.41]
1. DOL belirlenir.
2. Displacement / MSS izlenir.
3. Geri çekilmenin OTE bölgesine (0.62-0.79) gelmesi beklenir.
4. Bölgedeki FVG veya OB'den giriş yapılır.
5. Anlatıyla uyumlu olmalı.
6. Hedef sonraki likidite.
- **SG hedefleri:** -0.5 / -1 / -1.5 / -2. BE stop 0 seviyesinde.
- **EM örneği:** HTF seviyeye dokunma → displacement → MSS → premium'daki SIBI OTE ile örtüşür → dengeleme → SSL.

## Giriş ve stop tipleri (ortak) [SG s.34-35]
| Giriş | Stop |
|---|---|
| Complete Fill (FVG tamamen dolar) | Imbalance End (FVG'nin öbür ucu) |
| Consequent Encroachment (%50) | Order Block ucu |
| Entry Drill (FVG'nin ilk ucu) | Swing Point |
