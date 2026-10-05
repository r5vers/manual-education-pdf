# 9. İndikatörler

Kaynaklar: Kullanıcı ekran görüntüleri (K28, K31, K33, K35-K39), N-ana (FluxCharts, MQL5), N-A2, LQ.

## 9.1 Kullanıcının grafiklerinde görülenler
| İndikatör | Nerede görüldü | Ayar (ekrandan okunan) | Kaynak kodu |
|---|---|---|---|
| Seans / killzone kutuları | Hemen hepsi | Etiketler: "London", "NY AM", "LO close"; ayar satırı "30 30 America/New_York Normal 1800-1801" | **Yok** |
| LuxAlgo **Smart Money Concepts** (Mode: Historical, Style: Monochrome) | K28, K31, K33, K39 | Kullanıcı teyit etti: gri bölgeler bu indikatörün OB/FVG/likidite çizimleri. Tanımları için bkz. 07_TEK_KURAL_SETI | Açık kaynak (CC BY-NC-SA 4.0); Python portu: github.com/makeitcount89/Trading-Smart-Money |
| EMA 50 (close) | K33 | — | Standart |
| EMA 20 / 50 / 100 / 200 | K35-K39 | Yeşil tonlarda 4 EMA | Standart |
| Pozisyon aracı (long/short kutusu) | Hepsi | TradingView standart | — |
| Gri dikdörtgen bölgeler | Çoğu | LuxAlgo SMC'nin OB/FVG kutuları (kullanıcı teyit etti) | — |
| Kesikli yatay çizgiler | Çoğu | Büyük olasılıkla LuxAlgo internal yapı (BOS/CHoCH) çizgileri; kırılım gövde kapanışıyla | — |

## 9.2 Kaynaklarda geçen indikatörler
- **FluxCharts Price Action Toolkit** [N-ana]:
  - PDH/PDL/PDO, PWH/PWL/PWO, PMH/PML/PMO, premarket H/L.
  - FluxCharts "Liquidity Grabs" göstergesi.
  - Ücretli, kodu yok.
- **LuxAlgo FVG / ICT Silver Bullet** [N-A2]: Önerilmiş.
- **MQL5 "ICT Template MT4"** [N-ana]: PDH/PDL raid'inde bildirim gönderen ücretli ürün. Yazının asıl amacı bu ürünün reklamı.
- **TDI: Traders Dynamic Index, TradingView adı "TDIGM"** [LQ s.133-156]:
  - **Ayarlar:** RSI periyodu **50**, band uzunluğu **50**, RSI üstünde hızlı MA **1**, yavaş MA **9**.
  - **Görünenler:** Üst bant, alt bant, orta bant, hızlı MA.
  - **Kullanım:**
    1. **High Volume Breakout (HVB):** Hızlı çizgi orta bandı keser.
    2. **Aşırı alım/satım:** Bantların dışı, FVG/likidite bölgesinde.
    3. **Uyumsuzluk:** Fiyat yeni dip yapar, TDI yapmaz.
  - "Stoch RSI" başlığı var, içeriği yok.
  - **ICT dışı bir yaklaşım** (LQ "Lit concepts" diyor).
- **9/21 EMA kesişimi:** OB teyidi olarak [N-ana FluxCharts]. ICT dışı.

## 9.3 Kullanıcının kullandığı EMA'lar ICT kaynaklarında yok
- Hiçbir ICT kaynağı EMA kullanmıyor; ICT "indikatör okumalarıyla işlem yapmayız" diyor [N-A3].
- Kullanıcının son dönem grafiklerinde EMA 20/50/100/200 var. Kullanıcının cevabı: **trend filtresi**, EMA'lar ters diziliyse işleme girmiyor. Girişte 5m'de, bias için 1H ve 4H'ta; "gözle" bakıyor. Ölçülebilir karşılığı 07'de.

## Eksik olan
- LuxAlgo SMC ayarları kullanıcıdan alındı (07). FVG auto threshold ve EQH/EQL varsayılanları kaynak koddan teyit edilemedi.
- Seans indikatörünün adı ve kaynak kodu?
