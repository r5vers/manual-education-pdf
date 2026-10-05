# LQ kitabı: "Algo" yaklaşımı (strong/weak, algo candle, TDI, Ping Pong)

Kaynak: LQ (233 sayfa, anonim; grafikler Nisan-Mayıs 2022, EURUSD/GBPUSD/DXY/XAU/US100). Metnin çoğu bozuk İngilizce; 150'den fazla sayfa metinsiz grafik. Kavramların bir kısmı ICT dışı ("Lit concepts").

## Kitabın ana fikirleri
1. **"Piyasayı arz-talep değil, likidite için yapılan manipülasyon hareket ettirir."**
   - "Algoritma" perakende emirlerin nerede olduğunu bilir.
   - Amaç: perakendeyi pozisyona çekmek, panik yaratmak, stop'ları almak.
   - **Bu bir inanç; test edilemez.**
2. **Likidite hiyerarşisi:** Major / medium / minor (bkz. 01/02).
3. **Günlük döngü:** Asya birikim → Frankfurt sahte hareket → London agresif sweep → NY tuzağı → gün sonu dönüş.
   - "%90 London/NY günün tepe/dibini yapar." Kanıtsız.
4. **Haftalık ve HTF döngüleri:** Pazartesi manipülasyon/birikim, 20/40/60 gün, "ortalama 20 günde dönüş". Kanıtsız.
5. **Strong/weak yapı:**
   - Manipülasyon yapıp yapıyı kıran uç güçlüdür.
   - Discount/premium'a gitmeden olan kırılım sahte BMS'dir (FBMS/FMS).
6. **Algo candle (AC):** Likiditeyi alıp hemen FVG oluşturan mum. Very strong AC: likidite + strong kırılım + inducement + FVG.
7. **FVG:** "Tamamen dolunca dönüş olasılığı yüksek." Vector candle ve HVI (high volume imbalance) de var; HVI tanımlanmamış.
8. **Bloklar:** Breaker (agresif kaymada güçlü), rejection block (inducement + seans ucu).
9. **TDI indikatörü:** RSI 50, band 50, hızlı 1, yavaş 9. HVB, aşırı alım/satım, uyumsuzluk (bkz. 01/09).
10. **Giriş türleri:**
    - **Risk entry:** MMSM + günlük döngü + very strong AC + aşırı premium.
    - **Confirmation entry:** HTF mitigation + AHS + HVB. "AHS" tanımlanmamış; muhtemelen Asia High Sweep.
    - **Price action teyidi:** Rejection block + displacement. Giriş, sonraki mumun açılışında veya önceki mumun dibi kırılınca.
11. **Yönetim:** Yapı kırılınca stop başa baş (BE).
12. **Ping Pong (1m):**
    - Anlatıya hakim olmak gerekir.
    - Yüksek etkili haberde veya LO/NYO'da kullanılır.
    - "Her hareketi yakalamaya çalışma."
    - **Kesin kural verilmemiş;** yalnız örnek grafikler var.

## Değerlendirme
- Kitap kavramları çoğunlukla tanımsız bırakıyor (HVI, AHS, Ping Pong) ve sayısal iddiaları kaynaksız. Bot için doğrudan kural çıkarılabilecek kısım az.
- Mekanikleşmeye en uygun kısımlar:
  - Strong/weak swing.
  - Algo candle (likidite alan mum + hemen FVG).
  - TDI ayarları.
- Kullanıcının bu kitaptan **hangi kısmı kullandığı** bilinmiyor. Grafiklerinde TDI yok.
