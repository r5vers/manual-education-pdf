# Breaker modelleri ve Market Maker modelleri (MMBM/MMSM, AMD)

## A. Breaker Buy Model [SG s.16]
1. Buyside likidite süpürülür ("purged").
2. Sert düşüş gelir.
3. HTF discount array'de sellside likidite süpürülür.
4. Yükseliş, sweep'ten önceki swing high'ı kırar.
5. **+Breaker** (sweep öncesi son tepe bölgesi) yeniden test edilince long açılır.
   - Stop: +BB'nin dibinin altı.
   - Hedef: -Breaker. Discount'tan premium'a, EQ üstüne.

## B. Breaker Sell Model [SG s.17]
Ayna:
1. HTF premium array'de buyside likidite alınır.
2. -BB yeniden test edilince short açılır.
   - Stop: -BB tepesinin üstü.
   - Hedef: +Breaker.

## C. Market Maker Buy Model (MMBM) [SG s.26, LQ s.86-93]
| Faz | Ne olur |
|---|---|
| Orijinal konsolidasyon | Aralık buyside likidite üretir |
| Dağıtım (distribution) | Konsolidasyondan aşağı genişleme; bir sonraki bacak discount array'e kadar düşer |
| Smart money reversal | HTF discount array'de / SSL'de uzun vadeli dip; yapı bullish'e döner. **Düşük riskli alım burası** |
| Birikim 1. ve 2. bacak | Fiyat yükselirken optimal long girişleri |
| Tamamlanma | Orijinal konsolidasyonun tepesinin üstüne çıkılır, buy stop'lar alınır |

## D. Market Maker Sell Model (MMSM) [SG s.27]
Ayna. Konsolidasyon SSL üretir → birikim (yukarı) → HTF premium'da / BSL'de reversal → yeniden dağıtım 1. ve 2. bacak → konsolidasyon dibinin altına inilir.

## E. AMD [LQ s.76-85]
- Birikim (likidite biriktirme) → manipülasyon (perakendeyi yanlış tarafa çeken sahte hareket) → dağıtım (gerçek hareket).
- "Her gün, her hafta, her ay tekrarlar. En güçlü model." Kanıt sunulmamış.
- LQ'ya göre "fiyat hareketinin %80'i range'lerde geçer". Kaynak gösterilmemiş.
- PO3 ile aynı fikir (bkz. 01/07).
