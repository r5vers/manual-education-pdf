# 5. Premium / Discount, Equilibrium, OTE

Kaynaklar: N-ana (FluxCharts Premium/Discount), N-A3, SG, EM, WB, LQ, TS.

## 5.1 Equilibrium (EQ), premium, discount
- **Fib aracı:** Bir hareketin dibi ile tepesi arasına çekilir. **%50 = EQ.** [WB, N-ana, N-A3]
  - EQ'nun üstü premium (pahalı): short aranır.
  - EQ'nun altı discount (ucuz): long aranır.
- **Kural:** "Yalnız discount'ta long, yalnız premium'da short." [N-A3, N-A5, WB]
- **Ölçülen aralık kaynağa göre değişiyor:**
  - Displacement aralığı (2022 modeli) [SG, EM, N-A3].
  - Günlük swing aralığı (günlük bias) [N-A3].
  - HTF dealing range [N-A5].
- **N-A3 iki ayrı öneri veriyor:**
  - "Fib'i mum gövdeleriyle çek, daha doğru."
  - "Günlük aralık için gövde kullan, fitil değil."
- **Günlük açılış (D.O / 00:00 NY) ile tanım** [LQ, N-A5]:
  - Açılışın altı gün içi discount, üstü premium.
  - Boğa günde 00:00'ın altında long aranır.
- **LQ:**
  - "BSL'in üstü premium, SSL'in altı discount."
  - "Eski tepenin üstü kısa vadeli premium, eski dibin altı kısa vadeli discount." [N-A3]

## 5.2 OTE: Optimal Trade Entry
- **Bölge:** Geri çekilmenin %62-79'u.
- **Kaynaklara göre seviyeler:**
  - SG: %70.5 ortası.
  - TS: 61.8-78.6.
  - WB: "ICT OTE 70.5-79 arası."
- **Akış:** Likidite alınır → displacement/MSS → geri çekilme OTE'ye gelir → orada FVG/OB/breaker varsa giriş. [EM, SG, WB]
  - "Fib sebep değil, ölçüm aracı." [EM, SG]
- **SG fib ayarları:** 0, 1, 0.5, 0.62, 0.705, 0.79.
- **SG hedef ayarları:** -0.5 (kısmi 1), -1 (kısmi 2), -1.5 (tam TP), -2. BE stop 0'da.
- **Zaman:** Genelde 08:30-11:00 NY. [SG]

## 5.3 Standart sapma projeksiyonları
- EM'de "ICT standard deviations ile hedef" geçiyor. SG'nin -0.5/-1/-1.5/-2 seviyeleri bunun karşılığı.
- **Hangi aralığın projekte edileceği tanımlanmamış.**

## Kaynaklar arası farklar
- **Fib'in neye çekileceği:**
  - Displacement bacağı.
  - Sweep dibinden swing high'a [SG akış şeması].
  - Günlük aralık.
- **OTE aralığı:** 62-79, 70.5-79 veya 61.8-78.6.
- **Fitil/gövde:** Bazı kaynaklar gövde diyor, çoğu belirtmiyor.

## Bot için öneri
- **Ana tanım:** Fib, sweep ucundan MSS bacağının ucuna çekilir. Bu, SG/G4 2022 akış şemasının tanımı.
  - Long'da FVG'nin üst kenarı ≤ %50 seviyesi olmalı.
- **OTE:** Ek etiket olarak hesaplanır (0.62-0.79). Zorunlu filtre değil, kullanıcı karar verecek.
