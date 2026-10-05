# Model: TTrades Fractal Model (TTFM)

Kaynaklar: N-ana içindeki 3 TTrades yazısı. Galerideki K11 (IMG_0416, juneshsoni infografiği) bu modelin 4H→5m benzeridir.

## Mantık
- **Her TF'de aynı süreç:** Üst TF mumu yönü verir. Bir alt TF fitilin oluştuğunu gösterir. Daha alt TF'de CISD ile protected swing teyit edilir ve gövde işlenir.
- **Özet:** "Fitil oluşsun, gövdeyi işle."
- **Mum adları:**
  - C1: referans mum.
  - C2: C1'in ucunu alıp geri kapanan mum.
  - C3: genişleme mumu.
- **C2/C3 kapanışı:** Mum bir POI'ye (FVG vb.) uzanır, onu oluşturan mum serisinin içinden geri kapanır ve yeni bir protected swing oluşur. Bu, sonraki mumun o yönde genişleyeceği beklentisini verir.

## Eşleşmeler
| Bias | Fitil | Giriş / teyit | Kullanım |
|---|---|---|---|
| Haftalık (önceki hafta H/L'ye uzanma, haftalık C2/C3) | Günlük swing | 1H | 9-5 çalışanlar için: saat başlarında grafiğe bak |
| Günlük (C2/C3 kapanışı POI'de) | 4H (genelde 22:00 veya 02:00 4H mumu) | 15m CISD | London seansı |

## Kurallar
1. **Bias:** Günlük için C2 veya C3 kapanışı POI'de olmalı. Alternatifler: phases of price, EQ.
2. **Fitil:** Günlük fitil oluşsun. Bullish fikirde önce bir dip oluşmalı.
3. **4H swing:** Bullish'te genişleme öncesi oluşan dip. C2 kapanışı C3 genişlemesini öngörür.
4. **15m teyit:** Dibi yapan mum serisinin gövdesinden geri kapanış, yani CISD. Dip protected swing olur.
5. **Giriş tipleri:**
   - Swing point.
   - Mum kapanışı.
   - **Pozisyonel:** EQ'nun ya da CISD'nin %50'sinin tutması beklenir. Stop, karşı mum gövdesinin ötesi.
   - **Intra-candle CISD:** Tercih edilen.
6. **Devam girişleri:** Bearish'te LH, bullish'te HL.
7. **Başarısızlık:** Protected swing bozulursa kayıp geçerlidir. Zorla yeni giriş aranmaz; yeni yapı beklenir.
8. **Hedef:** Günlük setup genelde 2R verir. Haftalık yön sağlamsa haftalık hedefe tutulabilir.
9. **Zaman:**
   - "Kesin killzone çok önemli değil, HTF fitili oluşmuş olmalı."
   - London reversal: London günün tepe/dibini yapıyorsa aynı mantık geçerlidir.
   - Failure swing'lerde daha fazla teyit gerekir; SMT bu teyitlerden biri.
10. **İç/dış likidite:**
    - İç = FVG, dış = swing H/L. Seviyede tepki + C2/C3 kapanışı gerekir.
    - İç → dış (trend yönü) daha kolay.

## Önceki test sonucu
TTFM 4H→15m ve D→1H (M02) önceki turnuvada mekanik olarak test edildi. **Maliyet sonrası kenar bulunamadı** (bkz. azeghor-1-base-eurusd `arastirma/2026-10-02_model_turnuvasi`).

## Kullanıcı açısından
Kullanıcı daha önce "3-4 fraktal uyum örneği göstereceğim" demişti. **Bu örnekler henüz yok.** Kullanıcının hangi TF eşleşmesini (D→4H→15m mi, 4H→15m→1m mi) kullandığı bilinmiyor. K01-K03'teki sağdaki HTF mum katmanı bir fraktal göstergesine benziyor.
