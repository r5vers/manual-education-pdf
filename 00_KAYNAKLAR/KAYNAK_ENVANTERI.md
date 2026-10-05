# Kaynak envanteri

Bu repodaki her bilgi aşağıdaki kaynaklardan birinden gelir. Konu dosyalarında kaynak kısaltması köşeli parantezle verilir, örneğin `[SG s.18]` veya `[N-ana]`.

Toplam okunan:
- Notion ana sayfa: ~166 bin karakter, 44 görsel
- 6 Notion alt sayfası
- 5 PDF: 367 sayfa
- Sohbete yüklenen 1 PDF. EM ile aynı dosya çıktı.

## Kısaltmalar

| Kısaltma | Kaynak | Ne | Yazar / site | Dil | Boyut |
|---|---|---|---|---|---|
| **N-ana** | Notion "azeghor manual education" ana sayfa | Makale derlemesi + 44 görsellik galeri | Çok kaynaklı (aşağıda) | TR (makine çevirisi) + EN | ~166 bin karakter |
| **N-A1** | Notion alt sayfa "Fair-Value-Gaps-and-Liquidity-Void-" | Makale | ghosttraders.co.za | EN | Kısa, 7 görsel |
| **N-A2** | Notion alt sayfa "710035075-Fair-Value-Gap-Trading" | Makale | howtotrade.com | EN | Kısa, 8 görsel |
| **N-A3** | Notion alt sayfa "672495924-2022-ICT-Mentorship-Notes-Public" | ICT 2022 Mentorship topluluk notları | @bravehearttrade, @_amtrades, @arjoio derlemesi | EN | ~74 bin karakter, 26 görsel. **En zengin kaynak** |
| **N-A4** | Notion alt sayfa "884047351-Liqudity-Part-2" | "ICT Simplified – Mastering Liquidity part 2" | TritonTrades / simpletraders.io | EN | Kısa, 9 görsel |
| **N-A5** | Notion alt sayfa "884045533-Ict-2022-Model" | "ICT 2022 Model – A Complete Guide" | @murutrades | EN | Kısa, 10 görsel |
| **N-A6** | Notion alt sayfa "847513535-The-ICT-Student-s-Guide…" | **SG PDF'inin birebir kopyası** | — | EN | 51 görsel |
| **SG** | `pdf/SG_ICT_Students_Guide_Trading_Models_ImaTrader.pdf` | 20+ modelin şemaları | Ima Trader, 2023 | EN | 42 s. (s.7-35 şema) |
| **EM** | `pdf/EM_ICT_Entry_Models_Drevaxtrades.pdf` | 5 giriş modeli + grafik örnekleri | @Drevaxtrades (studocu) | EN | 26 s. |
| **WB** | `pdf/WB_ICT_Workbook_TheTradingFloor.pdf` | Kavram çalışma kitabı (alıştırmalı) | The Trading Floor | EN | 54 s. |
| **LQ** | `pdf/LQ_Market_Liquidity_and_Price_Manipulation.pdf` | "Algo" yaklaşımlı likidite kitabı | Anonim (studocu), grafikler Nisan-Mayıs 2022 | EN (bozuk) | 233 s., çoğu metinsiz grafik |
| **TS** | `pdf/TS_ICT_Trading_Strategy_NotiondanGomulu.pdf` | Site makalesinin PDF'i (Notion ana sayfaya gömülüydü) | Site adı yok | EN | 12 s. |
| **K01-K39** | `03_KULLANICININ_ISLEMLERI/gorseller/` | Kullanıcının kendi ekran görüntüleri | Kullanıcı | — | 39 görsel |

## Notion ana sayfanın (N-ana) içeriği, sırayla

Ana sayfada kullanıcının **kendi yazdığı** kural veya açıklama metni yok. Sayfa baştan sona dış kaynak kopyası/çevirisi ve açıklamasız görsellerden oluşuyor.

| Bölüm | Kaynak | Konu | Repoda nereye gitti |
|---|---|---|---|
| 1 | FluxCharts makaleleri, Türkçe makine çevirisi | IFVG, FVG, Order Block, BSL/SSL, PDH/PWH/PMH, Liquidity Grab, EQH/EQL, Premium/Discount, Breaker, BOS, CHoCH/CHoCH+, Liquidity Sweep, CISD, BPR, Breakaway Gap, Price Action Toolkit | 01_TEMEL_KAVRAMLAR (tümü), 09_indikatorler |
| 2 | Gömülü PDF "ICT Trading Strategy" (=TS) + Türkçe AI özeti | 7 kavram, tek mum sweep stratejisi | 02_MODELLER/07 (özet tekrar olduğu için tek yerde) |
| 3 | innercircletrader.net "ICT MSS" makalesi | MSS tanımı, 10 adımlı akış, 5 hata | 01/01_piyasa_yapisi, 02/01_ict_2022 |
| 4 | TTrades makaleleri (3 adet) | 9-5 çalışanlar için Fraktal Model, London seansı Fraktal Model, iç/dış likidite | 02/02_ttfm_fraktal, 01/02_likidite |
| 5 | MQL5 blog | PDH/PDL raid + DXY stratejisi, kurallar, risk | 02/07_likidite_tuzagi_modelleri |
| 6 | Reddit tarzı yazı | Sweep + SMT + BMS + 5m IFVG | 02/07_likidite_tuzagi_modelleri |
| 7 | **Galeri: 44 görsel, açıklamasız** | 5 dış görsel + 39 kullanıcı ekran görüntüsü | 03_KULLANICININ_ISLEMLERI |

Galerideki 5 dış görsel kopyalanmadı (başkasına ait). İçerikleri aşağıda.
- **G1, reddit:** NIFTY 2dk ICT 2022 scalp. 15dk tepe/dip BSL/SSL, BSL sweep → FVG → short, hedef SSL.
- **G2, reddit:** MNQ 1dk.
  - 9:30-10:00 açılış aralığında SSL sweep (Pazar açılışı / Cuma settlement seviyeleri), ardından MSS.
  - FVG + BISI/SIBI. Giriş 0.625 fib, stop 0.75 altı, hedef BSL / 0.125.
- **G3, YouTube kapağı:** ICT 2022 Sell Model özeti (BSL alındı → MSS → FVG → %50).
- **G4, infinity-trading.io "ICT 2022 Buy Model":** 5 adımlı mekanik tanım. SG s.18-20 ile aynı → 02/01_ict_2022.
- **G5, Shadtradingfx 9'lu model kolajı:** High probability, flip entry, CHoCH+inducement, LTF sell, orderflow re-alignment, simplified buy.

## Tekrarlar (birleştirildi, tek yerde tutuldu)

| Tekrar | Karar |
|---|---|
| N-A6 = SG PDF (kelime kelime aynı) | Yalnız SG PDF'i tutuldu |
| Sohbete yüklenen PDF = EM (md5 aynı) | Yalnız EM tutuldu |
| N-ana içindeki Türkçe AI özeti = TS PDF'inin özeti | TS'ye bağlandı |
| ICT 2022 modeli 7 ayrı kaynakta anlatılıyor (N-ana MSS makalesi, G4, N-A3, N-A5, SG, EM, WB/ATM) | 02/01_ict_2022.md içinde tek tabloda karşılaştırıldı; farklar korundu |
| FVG tanımı 8 kaynakta | 01/03_fvg_ailesi.md içinde tek tanım + kaynaklar arası farklar |
| Killzone saatleri 6 kaynakta, birbirini tutmuyor | 01/06_zaman.md içinde tek tablo |

## Kopyalanmayan, yalnız işaret edilen görseller

- **Alt sayfa görselleri:** N-A1, N-A2, N-A4, N-A5'in 34 görseli ve N-A3'ün 26 görseli. Hepsi dış makale/PDF kırpıntısı. Metin içerikleri konu dosyalarına aktarıldı.
- **N-A6'nın 51 görseli:** SG PDF'inde zaten var.
- **Not:** Notion görsel linkleri 5 dakikada süresi dolan imzalı linkler, kalıcı link olarak kullanılamaz.
