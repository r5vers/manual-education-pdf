# 3. Fiyat boşluğu ailesi: FVG, IFVG, BPR, VI, liquidity void

Kaynaklar: N-ana (FluxCharts IFVG/FVG/BPR/Breakaway), N-A1, N-A2, N-A3, SG, EM, WB, LQ, TS.

## 3.1 FVG: Fair Value Gap
- **Tanım:** 3 mumlu formasyon. 1. mumun fitili ile 3. mumun fitili arasında örtüşmeyen boşluk kalır. Orta mum büyük ve displacement'lıdır. [Tüm kaynaklar]
  - **Bullish FVG (BISI):** 1. mumun tepesi < 3. mumun dibi. Boşluk = [mum1.high, mum3.low].
  - **Bearish FVG (SIBI):** 1. mumun dibi > 3. mumun tepesi. Boşluk = [mum3.high, mum1.low].
  - Açılımlar: BISI = buyside imbalance sellside inefficiency. SIBI = sellside imbalance buyside inefficiency. [N-A3, WB]
- **Ek şartlar:**
  - "Büyük mumun gövde/fitil oranı ~%70." [N-A2]
  - "Önce likidite koşusu olmalı ve FVG bir MSS'in displacement aralığında olmalı." [N-A3]
  - "Gün içi zaman dilimlerinde en iyi." [N-ana]
- **Konum filtresi:**
  - Long FVG, displacement fib'inin %50'sinde veya altında olmalı (discount). Short FVG ise %50'de veya üstünde olmalı (premium). [SG, EM, N-A3, WB]
  - SG akış şeması: dipten swing high'a %50. "Gap %50'de veya altında."

## 3.2 FVG içindeki seviyeler ve giriş tipleri
- **Consequent Encroachment (CE):** FVG'nin %50'si. [N-A1, N-A3]
- **Mean Threshold:** OB gövdesinin %50'si. [N-A3]
- **Giriş tipleri** [SG s.34]:
  - Complete Fill: FVG'nin tamamı dolar.
  - CE: FVG'nin ortası.
  - Entry Drill: FVG'nin ilk ucu.
  - EM: long'da FVG'nin **tepesine** buy limit. Bu Entry Drill ile aynı.
- **Stop tipleri** [SG s.35]:
  - Imbalance End: FVG'nin öbür ucu.
  - Order Block: OB'nin ucu.
  - Swing Point: swing ucu.
- **IOFED:** FVG'nin %50'sinden azı doldurulur, yani fiyat CE'ye kadar gelmez. [N-A1]
- **N-A3:** "Mumlar FVG'ye fitil atmalı, tam gövdeyle kapanmamalı. Gövde kapanışı FVG'yi geçersiz kılar, fitil kılmaz."

## 3.3 FVG türleri
- **Breakaway gap:**
  - Fiyatın geri dönmediği FVG. Güçlü yönlü ivme gösterir. [N-ana, N-A1]
  - **Giriş için kullanılmaz.** [N-ana]
  - Açık kalması devam için teyittir. [WB örnek 3]
- **Measuring gap:** Hareketin ortasında açık kalan FVG. Kurumsal akışı gösterir. [N-A1]
- **Liquidity void:** Tek yönlü, uzun mumlarla dolu ve üzerinde fitil/gövde olmayan boşluk. Fiyat genelde geri gelir. [N-A1, N-A3, WB, LQ]
- **Volume imbalance (VI):** **2 mum** arasındaki gövde boşluğu, yani kapanıştan sonraki açılışa kadar. Üstüne gövde kapanınca dengelenmiş sayılır. [WB]
- **Immediate rebalance:** Displacement anında karşı boşluğa hemen geri dönülür, FVG hiç oluşmaz. Genişleme isteğini gösterir. [N-A3]
- **"FVG tamamen dolunca dönüş olasılığı yüksek":** HTF FVG için LTF FVG'den daha geçerli. [LQ]

## 3.4 IFVG: Inversion FVG
- **Tanım:** Geçerli bir FVG ters yönde kırılır, sonra ters yönlü PD array olarak kullanılır.
  - Kırılan bullish FVG direnç olur, kırılan bearish FVG destek olur. [EM, N-ana]
- **Kırılım şartı (çelişki var):**
  - EM: **yalnız gövde kapanışı.** "Fitil sonda/likidite etkileşimidir, kapanış kabuldür."
  - FluxCharts [N-ana]: "fitil **veya** kapanış."
- **Kullanım:**
  - Tek başına setup değil, teyit aracıdır. [EM]
  - Önce anlamlı stop hunt olmalı: PDH/PDL, seans uçları. "Rastgele tepe/dip önemsiz." [EM]
  - Displacement, killzone ve HTF anlatı gerekir.
- **FluxCharts / @DodgysDD stratejisi:** Liquidity grab → IFVG oluşunca gir → SL IFVG'nin ötesi → 1:2. [N-ana]
- **Reddit stratejisi:** Yapıyı kıran mumun 5m FVG'si → geri dönüşte gir. [N-ana]

## 3.5 BPR: Balanced Price Range
- Kısa sürede zıt yönlü iki displacement oluşur ve iki FVG örtüşür. Örtüşen bölge güçlü PD array'dir. [TS, N-ana]
- FluxCharts: "her BPR bir IFVG'dir." Fiyat aralıkta iki ucu da test eder; aralık kırılınca asıl trendin devamı beklenir.

## 3.6 Adlandırma karışıklığı (düzeltildi)
- **N-A2'nin adlandırması ters:**
  - "Undervalued FVG = bearish FVG" ve "Overrated FVG = bullish FVG" diye anlatıyor.
  - Bu yaygın ICT dili değil ve kafa karıştırıcı. Repoda yalnız **bullish/bearish FVG (BISI/SIBI)** kullanılır.
- **N-ana makine çevirisinin hatalı adları:**
  - "Değer Kaybı Açığı (IFVG)", "Ters Değer Boşluğu" → doğrusu **Inversion FVG**.
  - "Adil Değer Farkı/Açığı/Boşluğu" → hepsi **FVG**.
- **İki ayrı strateji:**
  - "FVG'nin dolmasını bekleyip ilk hareket yönünde gir." [N-A2, ICT kaynakları]
  - "FVG'ye karşı, dolmasını bekleyerek gir."
  - N-A2 ikincisini daha güvenilir bulmuyor, birincisini öneriyor.

## Bot için ölçülebilir öneri
- **FVG:** Kesin 3 mum tanımı.
  - Asgari boşluk ≥ m × ATR. **m kullanıcı örneklerinden.**
- **Geçersizlik:** Ters yönde **gövde kapanışı**. N-A3 ve EM aynı yönde. Kullanıcı onaylarsa bu kullanılır.
- **Giriş seviyesi:** FVG ilk ucu, CE veya tam dolum.
  - **Kullanıcının grafiklerinden ölçülecek.** Görsellerde giriş genelde FVG/OB'nin içinde.
