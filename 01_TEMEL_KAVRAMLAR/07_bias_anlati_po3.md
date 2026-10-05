# 7. Bias, anlatı (narrative), PO3/AMD, döngüler

Kaynaklar: N-A3 (en ayrıntılı), N-A5, N-ana (TTrades, MQL5), SG, WB, LQ, EM.

## 7.1 Yukarıdan aşağı analiz sırası
**N-A3 (ICT 2022):**
1. **Haftalık:** Haftalık mum yukarı mı aşağı mı genişler? Yukarıda imbalance mı, aşağıda likidite havuzu mu var? Etkenler: mevsimsellik, faiz, bilanço dönemi, haftalık/günlük PA.
2. **Günlük:** DOL belirlenir.
   - Analizin %70'i günlük grafiktedir. 5 günden ileri tahmin yapılmaz.
   - "Günlük grafiğe karşı işlem başarısızlık ister."
3. **4H/1H:** Çerçeve, en yakın PD array'ler, 1H order flow.
4. **15M:** "Bellwether" grafiği. Gün içi yapı ve trade yönetimi buradan yapılır.
   - "Çıkışı 1-5m yapıya göre yapma."
5. **5M/3M/1M:** FVG girişi. "Endekste 1-3m en iyisi."

**TTrades (9-5 çalışanlar için):**
- Haftalık bias: önceki haftanın tepesine mi dibine mi uzanıyor? Haftalık C2/C3 kapanışı.
- → Haftalık yönle uyumlu günlük swing.
- → Günlük + 1H Fractal Model.

**WB:**
- **Analiz zaman dilimleri:**
  - Scalp: 1H/15M/5M/1M.
  - Gün içi: D/4H/1H/15M/5M.
- **Grafik genişliği:** D 9-12 ay, 4H 3 ay, 1H 3 hafta, 15M 3-4 gün.

## 7.2 Günlük bias kontrol listesi [N-A3]
- Son olarak hangi likidite alındı? SSL alındıysa BSL aranır, tersi de geçerli.
- Swing / kısa vadeli / relative equal tepe-dipler, yani dinlenen likidite.
- Likidite alındıktan sonraki MSS.
- İmbalance'lar (FVG/OB).
- Günlük aralığın discount/premium konumu (gövdelerle).
- HH/HL/LH/LL.
- **Bullish bias:** Fiyat PDH'yi arar, PDL'yi kıramaz.
- **Dış gün:** Hem PDH hem PDL aynı günde kırılırsa genelde günlük dönüş işaretidir.
- Bias'ı geçersiz kılan fiyat seviyesi önceden yazılır.
- "Bias net değilse **bekle, işlem yapma**." "İki tarafı da savunabiliyorsan düşük olasılıktır."
- DXY ile teyit.

## 7.3 Anlatı (narrative)
- **Bias:** Fiyatın hangi yöne gideceği.
- **Narrative:** Oraya nasıl gideceği. [N-A3]
- "DOL ve anlatı net değilse işlem yok." "Yüksek olasılık = kendini o kadar tek taraflı hissettirir ki karşı tarafı savunamazsın." [N-A3]
- EM: "Önce anlatı, sonra model. Her zaman bu sırayla."

## 7.4 Power of 3 (PO3) / AMD
- **Tanım:** Accumulation (birikim) → Manipulation (manipülasyon) → Distribution (dağıtım). Fraktaldır: günlük, haftalık, seanslık, 30 dk mum. [N-A3, SG, WB, LQ]
- **Boğa günü:**
  - Açılış günün dibine yakındır.
  - Önce aşağı (Judas / manipülasyon) gidilir, önemli dip yapılır.
  - Sonra yükselişle günün tepesine yakın kapanış.
- **Seans karşılığı** [WB, SG, LQ]:
  - Asya: birikim.
  - London: manipülasyon. Asya tepe/dibi alınır.
  - NY: dağıtım ya da London'ın devamı. NY öğlende dönüş yaygın.
- **Judas swing:**
  - Karşı likiditeye sahte hareket, sonra HTF yönünde devam. [WB, N-A3]
  - Gece yarısı açılışının üstüne sahte çıkış, sonra düşüş. Bu, short bias'lı günün örneği. [N-A3]
- **LQ'nun günlük döngüsü:** Asya birikim → Frankfurt sahte hareket → London açılışında agresif sweep (Asya dibi + PDL) → NY açılış tuzağı (sahte BOS) → gün sonu dönüş.

## 7.5 Fiyat döngüleri ve konsolidasyon beklentisi [N-A3]
- Konsolidasyon → genişleme → geri çekilme → dönüş.
- **Konsolidasyon beklenen durumlar:**
  - HTF aralığın EQ'su.
  - Haftanın sonunda kırmızı haber varken başında yokken.
  - FOMC/CPI/NFP öncesi.
  - Asya çok genişse London'da.
  - London çok genişse NY'de.

## 7.6 HTF döngüsü ve IPDA [LQ, N-A3]
- "IPDA son 20/40/60 güne bakar." Büyük likidite alımı + PDH kırılımından sonra son 20/40/60/90 günün en yüksek tepesi hedef olur.
- "Ortalama 20 gün sonra dönüş." [LQ] **Kanıt yok.**
- "3-5 günde yön değişir." [LQ] **Kanıt yok.**

## 7.7 Fraktal uyum (TTFM)
- Detay 02_MODELLER/02.
- **Özet:** Üst TF mumunun C2 kapanışı yönü verir → alt TF'de fitil oluşur → daha alt TF'de CISD ile protected swing → gövdeyi işle.

## Kaynaklar arası farklar
- **Bias'ın kaynağı:**
  - Günlük DOL [N-A3].
  - Haftalık C2/C3 [TTrades].
  - 1H/4H trend [N-A5].
  - Günlük açılışa göre konum [LQ].
- **Bias yokken işlem:**
  - "Bias yoksa işlem yok" [N-A5, N-A3].
  - "1H'ı günlük bias gibi kullan, küçük lotla karşı trend" [N-A3].

## Bot için öneri
- **Mekanik bias adayları:**
  - (a) Önceki gün son alınan likidite tarafı.
  - (b) Günlük kapanışın önceki gün aralığına göre konumu.
  - (c) Fiyatın günlük açılışa göre konumu.
- Kullanıcının bias çizimleri gelince hangisine en çok uyduğu ölçülecek.
- **Kullanıcının bias çizimleri henüz yok** (bkz. 05_EKSIKLER).
