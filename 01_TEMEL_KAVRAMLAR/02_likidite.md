# 2. Likidite

Kaynaklar: N-ana (FluxCharts BSL/SSL, Grab, Sweep, EQH/EQL; TTrades; MQL5), N-A3, N-A4, LQ, WB, SG, EM.

## 2.1 Tanım
- **BSL (buy-side liquidity):** Tepelerin üstünde biriken stop emirleri (short'ların stop'ları, kırılım alımları).
- **SSL (sell-side liquidity):** Diplerin altında biriken stop emirleri.
- "Fiyat her zaman ya likiditeye ya imbalance'a (FVG) gider." [N-A3, WB]

## 2.2 Likidite seviyeleri ve önemi
| Seviye | Kısaltma | Önem [LQ] |
|---|---|---|
| Önceki yıl / ay / hafta / gün tepe-dip | PYH/PYL, PMH/PML, PWH/PWL, PDH/PDL | MAJOR |
| HTF swing tepe/dip | — | MAJOR |
| 1H yapı tepe/dipleri | — | MEDIUM |
| Seans tepe/dipleri (Asya 20-24, London 02-05, NY 07-10 NY saati) | ASH/ASL, LOH/LOL | MEDIUM [LQ], ana likidite [N-A3] |
| Gün içi 30/15/1m tepe-dipleri, Asya ortası | — | MINOR |
| 9:30 öncesi gün içi tepe/dip (endeks) | — | [N-A3] |
| Eşit tepeler / dipler (relative equal) | EQH/EQL, REQH/REQL | Mıknatıs [N-ana, N-A3] |

- "HTF likidite > LTF likidite."
- "Büyük likidite = büyük hareket; 20 pip için minor yeter." [LQ]

## 2.3 Grab ve sweep
- **Liquidity grab:** **Tek mumda** uzun fitil + küçük gövde. Seviyenin ötesine fitille geçip geri kapanır. [N-ana FluxCharts]
- **Liquidity sweep:** **Birden çok mum** ve bazen konsolidasyonla seviyenin ötesine geçip geri döner. [N-ana]
- **TS "tek mum sweep" kuralı:**
  - HTF'de tek mum önceki yapının dibinin altını alır.
  - **Sonraki mum** sweep mumunun ne tepesini aşmalı ne dibinin altında kapanmalı. Aksi halde geçersiz.
- **N-A3:**
  - "Running a level" = seviyeyi geçip geri bakmamak.
  - "Sweeping a level" = seviyeye dokunup ötesine geçip dönmek.
- **EQH/EQL** [N-ana]: "Giriş değil, dönüş teyidi."

## 2.4 İç ve dış likidite (IRL / ERL)
- **ERL (external range liquidity):** Dealing range'in tepesi (BSL) ve dibi (SSL). [N-A4, TTrades, N-A3]
- **IRL (internal range liquidity):** Range içindeki iç tepe/dipler, FVG/imbalance, OB/breaker, range ortası (EQ).
- **TTrades:** İç = FVG, dış = swing tepe/dip.
- **Fiyat yalnız iki şekilde hareket eder** [N-A4]:
  - IRL → ERL
  - ERL → IRL
  - "External'dan internal'a, internal'dan external'a; tekrar." [N-A3]
- **TTrades:** İç → dış (trend yönü) kolaydır. Dış → iç daha fazla teyit ister.

## 2.5 Dealing range
- BSL'i alıp dönen ve SSL'i alan aralıktır. Dış likidite süpürülene kadar dealing range olarak kalır. [N-A3]
- **Bullish dealing range:** Önce SSL, sonra BSL alınır (dış tepe kırılır). Long'lar discount'taki IRL PD array'lerinden aranır.

## 2.6 Düşük ve yüksek dirençli likidite [N-A3]
- **Low resistance liquidity run (LRLR):**
  - Trendde karşı tarafın kolay alınan likiditesi. Örnek: düşüş trendindeki dipler.
  - Displacement'lı, akıcı hareket. "Basit 2R işlemleri burada." Hedef bu olmalı.
- **High resistance liquidity:**
  - Savunulan tepe/dipler, örneğin düşüş trendindeki korunan tepeler.
  - Genelde yüksek etkili haber (NFP, CPI, FOMC) olmadan kırılmaz.
  - Hedeflemekten kaçınılır.

## 2.7 Draw on Liquidity (DOL)
- Fiyatın gitmeye çalıştığı yer: likidite havuzu ya da imbalance. Bias'ı DOL belirler. [N-A3]
- **Günlük kural:** Fiyat son olarak SSL aldıysa BSL'i arar, tersi de geçerli. [N-A3]

## 2.8 Money transfer [LQ]
- Tüm SSL alındıktan sonra fiyat teslimatı BSL tarafına geçer, ya da tersi.

## Kaynaklar arası farklar
- **Grab ve sweep:**
  - FluxCharts ikisini ayırır: tek mum ve çok mum.
  - ICT kaynakları ve kullanıcının grafikleri ayırmıyor.
- **Seans likiditesinin önemi:**
  - LQ: "medium".
  - N-A3: ana likidite.
  - MQL5: yalnız PDH/PDL.

## Bot için ölçülebilir öneri
- **Seviye kümesi:** PDH/PDL, PWH/PWL, Asya H/L, London H/L, 15m/1H swing H/L, EQH/EQL.
  - EQH/EQL toleransı: iki uç arasındaki fark ≤ k × ATR. **k kullanıcıdan.**
- **Sweep:** Fitil seviyeyi geçer, mum seviyenin içinde kapanır.
  - Tek mum mu çok mum mu: **kullanıcıya soru.**
- **Seviyeler** gün başında hesaplanır, geleceğe bakmaz.
