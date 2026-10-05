# Tek kural seti (çelişkiler çözüldü) — sürüm 1.1

Bu dosya, 05'teki 12 çelişkinin her biri için **tek** bir tanım seçer. Seçim sırası:
1. **Kullanıcının kendi cevabı** (5 Ekim 2026'da sorulan 12 soru, aşağıda).
2. **Kullanıcının ekranındaki indikatör: LuxAlgo "Smart Money Concepts".** Ekran görüntülerindeki "Historical Monochrome" ibaresi bu indikatörün *Mode = Historical*, *Style = Monochrome* ayarıdır. Gri kutuları ve kesikli çizgileri bu indikatör çiziyor; bot da aynı tanımı kullanmalı.
3. **ICT'nin kendi öğretisi**, yani 2022 Mentorship. Kaynaklar arasında en çok tekrar edilen ve iç tutarlılığı olan sürümü seçildi.
4. **Kalan durumlarda** ölçülebilir ve geleceğe bakmayan en basit sürüm.

## Kullanıcının cevapları (5 Ekim 2026)
| # | Soru | Cevap |
|---|---|---|
| 1 | Gri bölgeler | LuxAlgo indikatörü çiziyor: OB, FVG ve likidite seviyeleri |
| 2 | Kırılım şartı | **Gövde kapanışı şart** |
| 3 | Kırılım zaman dilimi | Genelde **5m**, bazen **3m** |
| 4 | Giriş | **FVG'nin yarısına (%50, CE) gelmesini bekliyorum; dönüşe başlarsa giriyorum** |
| 5 | Bias | **1H / 4H trend** |
| 6 | EMA 20/50/100/200 | **Trend filtresi**: ters diziliyse girmiyor |
| 7 | Saatler | **London ve NY** |
| 8 | Haber günleri (NFP, CPI, FOMC) | **İşlem yapmıyor** |
| 9 | Stop / hedef | **Stop sweep ucunun ötesi, hedef karşı likidite** |
| 10 | Enstrümanlar | **EURUSD, XAUUSD, NAS100** (GBPUSD yok) |
| 11 | Uygulanan model | **ICT 2022 modeli + TTFM (fraktal)** |
| 12 | Tarihli işlem kaydı | **Yok** |
| 13 | EMA'lara hangi TF'de bakıyor | **Girişte 5m; bias için 1H ve 4H** |
| 14 | EMA şartı | **Gözle bakıyor**, kesin kural yok |
| 15 | Asgari R | **1.5 uygun** |
| 16 | LuxAlgo ayarları | Hepsi açık (aşağıdaki tablo); FVG timeframe = grafiğin kendi TF'si; diğer ayarlar varsayılan; OB mitigation = High/Low |

## LuxAlgo SMC'nin tanımları (bot bunları birebir kopyalamalı)
Kaynak: LuxAlgo SMC Pine v5 kodunun açık kaynak Python portu (`github.com/makeitcount89/Trading-Smart-Money`, `scripts/engine.py`). LuxAlgo'nun kendi sitesi ve TradingView bu ortamdan erişilemedi.

| Öğe | LuxAlgo'daki tanım |
|---|---|
| **Swing / pivot** | `leg(size)`: `size` bar önceki tepe, ondan sonraki `size` barın en yükseğinden yüksekse pivot tepe olur. Yalnız sağ taraf kontrol edilir. **Internal yapı: size = 5 (sabit). Swing yapı: size = 50.** |
| **Kırılım (BOS/CHoCH)** | `close[i-1] <= pivot` ve `close[i] > pivot` → yükseliş kırılımı. **Kapanışla** olur, fitil saymaz. Trend tersine dönüyorsa CHoCH, aynı yöndeyse BOS. Internal yapı çizgileri **kesikli**, swing yapı çizgileri düz. |
| **Order Block** | Kırılım olunca, kırılan pivotun barından kırılım barına kadar (kırılım barı hariç) **en düşük dibi olan bar** bullish OB'dir; bearish için en yüksek tepeli bar. Bölge = o barın **tüm high-low aralığı**. Aralığı ≥ 2 × ATR(200) olan barlarda high/low yer değiştirir, böylece aşırı fitil OB ucu olmaz. Internal ve swing OB'den en son 5'er tane gösterilir. |
| **OB'nin geçersizleşmesi** | Varsayılan "High/Low": bullish OB'nin dibinin altına inilince silinir, bearish OB'nin tepesinin üstüne çıkılınca silinir. |
| **FVG** | 3 mum boşluğu + orta mumun gövde değişimi otomatik eşiğin üstünde olmalı (*auto threshold*). **Bu ayrıntı kaynak koddan teyit edilemedi;** kullanıcının ekranındaki FVG ayarları sorulacak (bkz. sonuç bölümü). |
| **EQH/EQL** | Eşit tepe/dip: fark < eşik × ATR. Varsayılan eşik ve onay barı sayısı **teyit edilemedi.** |

**Önemli sonuç:** LuxAlgo'nun bullish OB'si çoğu zaman **sweep yapan mumun kendisidir**, çünkü kırılan tepe ile kırılım arasındaki en düşük dipli bar odur. Kullanıcının "stop sweep ucunun ötesi" kuralı bu yüzden "stop OB'nin ötesi" ile neredeyse aynı yere düşüyor. İki kaynak birbirini tutuyor.

## Kullanıcının LuxAlgo SMC ayarları (5 Ekim 2026, kullanıcının beyanı)
| Bölüm | Durum | Değer |
|---|---|---|
| Mode / Style | — | Historical / Monochrome |
| Internal Structure (kesikli BOS/CHoCH) | Açık | Varsayılan |
| Swing Structure (düz BOS/CHoCH, HH/HL etiketleri) | Açık | Varsayılan |
| Internal Order Blocks | Açık | Varsayılan |
| Swing Order Blocks | Açık | Varsayılan |
| OB Mitigation | — | **High/Low** |
| Equal Highs/Lows | Açık | Varsayılan |
| Fair Value Gaps | Açık | **Timeframe = grafiğin TF'si**; diğerleri varsayılan |
| Premium/Discount Zones | Açık | Varsayılan |
| Daily/Weekly/Monthly High-Low | Açık | Varsayılan |

"Varsayılan" değerler port kodundan teyitli olanlar:
- Internal pivot uzunluğu 5, swing pivot uzunluğu 50.
- ATR(200) ile yüksek volatilite filtresi.
- 5'er OB gösterimi.
- High/Low mitigation.

FVG auto threshold ve EQH/EQL eşiği/onay barı varsayılan değerleri **kaynak koddan teyit edilemedi**. Bot bunları LuxAlgo'nun bilinen v5 varsayılanlarıyla (FVG auto threshold açık; EQH/EQL onay 3 bar, eşik 0.1 × ATR) kodlayacak. İlk kalibrasyonda kullanıcının grafiğindeki kutularla karşılaştırılacak.

**Pratik sonuç:** FVG ve OB'ler grafiğin TF'sine göre çiziliyor.
- 5m grafikte 5m kutular görünüyor; bias için 1H/4H'a bakıldığında 1H/4H kutular görünüyor.
- Bot iki katmanı da hesaplar:
  - **Bağlam:** 1H/4H LuxAlgo OB/FVG, premium/discount bölgesi, PDH/PDL, EQH/EQL.
  - **Tetik:** 5m LuxAlgo internal CHoCH + 5m FVG.

## 12 çelişkinin çözümü
| # | Konu | Seçilen tek tanım | Neden |
|---|---|---|---|
| 1 | Killzone saatleri (NY saati) | **London 02:00-05:00.** NY: **EURUSD ve XAUUSD 07:00-10:00, NAS100 08:30-11:00.** TR saati yazın +7, kışın +8 (London 09:00-12:00 TR, NY 14:00-17:00 TR). | ICT'nin kendi pencereleri. Forex için 07-10, endeks için 08:30-11:00 tüm ICT kaynaklarında aynı; diğer varyantlar bunların genişletilmiş hali. Kullanıcı London + NY dedi. |
| 2 | Stop | **Sweep ucu + spread payı.** Bu, LuxAlgo OB'sinin ucuyla genelde aynı yer. | Kullanıcı cevabı, MSS makalesi ve infinity-trading akış şeması aynı; LuxAlgo OB tanımı destekliyor. "FVG mumunun dibi" daha dar ve daha çabuk stoplanan bir varyant. |
| 3 | Giriş | **FVG'nin %50'si (CE).** Fiyat CE'ye değdikten sonra giriş TF'sinde (5m/3m) **dönüş yönünde kapanan ilk mum** = giriş anı. | Kullanıcı cevabı ("yarısına gelip bekliyorum, dönerse giriyorum"). ICT'de CE resmi bir seviye. |
| 4 | MSS'in kırdığı swing | **Sweep ucundan ÖNCE oluşan son karşı internal pivot** (LuxAlgo size = 5). Long için: dipten önceki son internal tepe. Short için ayna: tepeden önceki son internal dip. | Akış şemasının buy versiyonu ile infinity-trading aynı söylüyor. SG'nin sell versiyonundaki "SONRA" ifadesi aynalık mantığına ters; baskı hatası sayıldı. LuxAlgo'nun internal CHoCH'u da tam bu pivotu kullanıyor. |
| 5 | Fitil mi kapanış mı | **Her yerde gövde kapanışı:** MSS/BOS kırılımı, FVG'nin geçersizleşmesi, IFVG oluşumu. | Kullanıcı cevabı + LuxAlgo (close ile kırılım) + ICT notları + EM + MSS makalesi aynı. Yalnız FluxCharts "fitil de olur" diyor; azınlık. |
| 6 | Adlandırma | **MSS** = sweep sonrası, önceki internal trendin tersine ilk kapanışlı kırılım (LuxAlgo'da internal CHoCH). **BOS** = trend yönünde kapanışlı kırılım. CHoCH+, BMS, MSB, FMS adları kullanılmaz. | Tek sözlük; LuxAlgo'nun etiketleriyle birebir eşleşiyor, böylece kullanıcı botun mesajını grafikte görebilir. |
| 7 | Order Block | **LuxAlgo tanımı** (yukarıdaki tablo). ICT'nin "son karşı renkli mum" tanımı yalnız not olarak kalır. | Kullanıcının gördüğü gri kutular bunlar. Bot farklı tanım kullanırsa kullanıcının grafiğiyle uyuşmaz. |
| 8 | OTE | **0.62-0.79 (0.705 orta).** Yalnız etiket olarak; filtre değil. | Kullanıcı OTE değil CE kullanıyor. Aralık ICT'nin kendi Fib ayarı. |
| 9 | Hedef | **En yakın karşı likidite:** karşı internal/swing pivot, EQH/EQL, seans ucu, PDH/PDL; hangisi önce geliyorsa. **Asgari R ≥ 1.5.** | Kullanıcı cevabı; 1.5R kullanıcı tarafından onaylandı. |
| 10 | Bias ve EMA | **Bias:** 1H ve 4H'ta LuxAlgo yapı yönü aynı **ve** her iki TF'de EMA filtresi geçer. **Giriş filtresi:** 5m'de EMA filtresi geçer. **EMA filtresi (long):** fiyat > EMA200 ve EMA50 > EMA200. Short için tersi. Dört EMA'nın tam sıralı olup olmadığı (20>50>100>200) yalnız **etiket** olarak yazılır. | Kullanıcı EMA'ya 5m'de girişte, 1H/4H'ta bias için bakıyor ama "gözle" bakıyor. Gözü taklit eden en basit ölçülebilir kural bu. Tam sıralama şartı sinyalleri çok azaltır; etiket olarak tutulup gölge dönemde kullanıcının "girerdim/girmezdim" cevaplarıyla hangisinin gözüne uyduğu ölçülecek. |
| 11 | FVG dolunca ne olur | **FVG gövdeyle kapanarak geçilirse geçersizdir.** İçine fitil atıp dönmesi "tutuyor" demektir. | ICT notları + #5 ile tutarlı. LQ'nun "tamamen dolunca dönüş" iddiası kanıtsız ve diğerleriyle çelişiyor. |
| 12 | FVG adları | **Bullish FVG / bearish FVG.** "Undervalued/overrated" kullanılmaz. | Standart ICT dili. |

Ek tek tanımlar:
- **Premium/discount:** Fib sweep ucundan MSS bacağının ucuna çekilir. Long'da CE bu aralığın %50'sinin **altında** olmalı, short'ta üstünde. Kaynak: 2022 akış şeması.
- **Sweep:** Fiyat bir likidite seviyesinin (internal/swing pivot, EQH/EQL, Asya/London ucu, PDH/PDL) ötesine **fitille** geçer, mum seviyenin içinde kapanır. Tek mum veya birkaç mum fark etmez.
- **Displacement:** MSS'i yapan bacakta en az bir FVG olmalı. Ayrıca bir sayısal eşik konmadı; FVG şartı ICT'nin kendi filtresi.
- **TTFM'nin rolü:** Zorunlu değil, **ek etiket.** "4H'ta son kapanan mum C2 (önceki 4H mumunun ucunu alıp içeri kapandı) ve yönü sinyalle aynı" ise mesajda "TTFM uyumlu" yazar. Kullanıcı hem 2022 hem TTFM dedi; ikisini birden zorunlu yapmak sinyali çok azaltır, önce etiket olarak ölçülecek.
- **Haber:** NFP, CPI, FOMC günlerinde **gün boyu sinyal yok.**

## Tek akış: AZG-K1 v1 (EURUSD, XAUUSD, NAS100)
1. **Gün filtresi:** NFP/CPI/FOMC günü değilse devam.
2. **Pencere:** London 02:00-05:00 NY; NY 07:00-10:00 (NAS100: 08:30-11:00).
3. **Bias:** 1H ve 4H'ta LuxAlgo yapı yönü aynı, iki TF'de de EMA filtresi geçiyor (fiyat ve EMA50, EMA200'ün doğru tarafında). Değilse sinyal yok.
4. **Bağlam:** Fiyat bias yönündeki dolmamış bir 1H/4H LuxAlgo OB veya FVG'nin içinde, ya da bias yönünün discount/premium bölgesinde bir likidite seviyesinde (seans ucu, PDH/PDL, EQH/EQL).
5. **Sweep:** Bias'ın tersi yöndeki likidite fitille alınır, mum içeri kapanır.
6. **MSS:** 5m'de sweep'ten önceki son karşı internal pivot (LuxAlgo internal CHoCH) gövde kapanışıyla kırılır; kıran bacakta 5m FVG var. 5m'de EMA filtresi geçiyor. 3m yalnız ikinci aşamada denenecek.
7. **Konum:** FVG'nin CE'si sweep→MSS aralığının doğru yarısında (long için discount).
8. **Tetik:** Fiyat CE'ye değer; ardından 5m/3m'de bias yönünde kapanan ilk mum. **Telegram mesajı bu anda gider.**
9. **İç değerlendirme (mesajda TP/SL/lot yok):** Geçersizlik = sweep ucu + spread. Hedef = en yakın karşı likidite. R < 1.5 ise sinyal gönderilmez.
10. **Etiketler:** TTFM uyumu, OTE içinde mi, SMT (EURUSD↔DXY, NAS100↔SPX, XAU↔DXY), Silver Bullet penceresi mi.

## Açık soru kalmadı
- Kural seti kullanıcının cevaplarıyla kapandı.
- Kalan belirsizlikler (FVG eşiği, EMA'nın "göz" karşılığı, bağlamın 1H mi 4H mi olduğu) **soruyla değil ölçümle** netleşecek: aşağıdaki gölge dönemde.

## Kayıt olmadığı için doğrulama planı değişti
Kullanıcının tarihli işlem kaydı yok. Bu yüzden:
1. **AZG-K1 v1 bir araştırma klasöründe çalıştırılır**, bota eklenmez. Son 6-12 ayın verisinde ürettiği sinyaller grafik görselleriyle kullanıcıya gösterilir.
2. **Kullanıcı her birine "girerdim / girmezdim / şu yüzden"** der. Bu, eksik olan etiketli veri setini oluşturur.
3. Uyuşmazlıklar parametreye çevrilir. Ardından ön-kayıt yapılır ve hiç bakılmamış dönemde maliyetli test yapılır.
4. **Bundan sonra her işlem için kayıt tutulmalı:** tarih, saat, enstrüman, yön, giriş, stop, hedef, sonuç ve tek cümle gerekçe. Bunun için hazır bir şablon yapılabilir.

Bot koduna dokunulmadı; kullanıcı "başla" demeden dokunulmayacak.

## Sürüm 1.2 ve ilk test (5 Ekim 2026)
- **Kalibrasyon:** Kullanıcı 28 adayı kör etiketledi. Gerekçelerinden iki şart eklendi:
  - **FVG ≥ 0.2 × ATR14 (5m).** Daha küçük boşluklar FVG sayılmaz.
  - **FVG'den tetiğe en fazla 12 mum (1 saat).** Fiyat oyalanıp akümüle olduysa sinyal yok.
- **Ön-kayıtlı tek atış testi:** Hiç bakılmamış dönem; EURUSD 2025-06 → 2026-05, XAUUSD 2025-06 → 2026-05, NAS100 2025-11 → 2026-05.
  - 54 sinyal, ortalama −0.09R, t = −0.52, kazanma %33.
  - Ters yön plasebosu +0.33R.
  - **Sonuç: KALMADI.** Kuralın mekanik hali bu dönemde para kazandırmadı.
- **Ayrıntı:** `r5vers/azeghor-1-base-eurusd` → `arastirma/2026-10-05_azg_k1_golge/README.md`.

## Sürüm 1.3: kullanıcının "geometri" tarifi (5 Ekim 2026)
- **Tanım:**
  - OTE %62-79 şart (Fib 5m'de sweep ucundan kırılım ucuna).
  - Net swing (bacağın başladığı uç, iki yanda ≥3 mum).
  - Displacement'lı ve orantılı FVG (orta mum gövdesi ≥ %50 ve ≥ 0.8 ATR; FVG ≥ 0.2 ATR ve ≥ bacağın %15'i).
  - Fiyat girişten önce FVG'nin öbür ucunu geçerse iptal.
- **Yeni veri (Dukascopy):** 2,5 yılda 3 enstrümanda 12 sinyal, ortalama −0.13R, kazanma 4/12. **Belirsiz:** az işlem.
- **Aynı veride v1.2:** 135 sinyal, −0.17R. **Kalmadı.**
- **Kalibrasyon notu:** Kullanıcının etiketlerinde OTE, girdiği ve girmediği işlemleri ayırmadı.
