# Eksikler, kafa karıştıran noktalar, çelişkiler ve sorular

> **Güncelleme (5 Ekim 2026):**
> - D bölümündeki 12 soru cevaplandı.
> - B bölümündeki 12 çelişkinin her biri için tek tanım seçildi.
> - Cevaplar ve kararlar için bkz. **[07_TEK_KURAL_SETI.md](07_TEK_KURAL_SETI.md)**. Bu dosyadaki çelişkiler artık geçmiş kayıt olarak duruyor.

## A. Eksikler (dosyalarda olmayan ama bot için gereken)
1. **Kullanıcının kendi kuralları yok.** Notion ana sayfada kullanıcının yazdığı tek bir kural veya açıklama cümlesi yok; her şey dış kaynak kopyası.
2. **Ekran görüntülerinin açıklaması yok.** 39 görselde neden girildiği, gri bölgenin hangi TF'den geldiği, bias'ın ne olduğu yazmıyor.
3. **Tarih/saat yok.** Yalnız 3 MT5 görseli tarihli (28 Nisan). Diğerleri piyasa verisiyle eşleştirilip yeniden üretilemiyor.
4. **Kayıp ve "girmedim" örnekleri yok.** 1 kayıp dışında hepsi kazanç.
5. **Daha önce söz verilenler gelmedi:**
   - 3-4 fraktal uyum örneği.
   - 1-2 bias çizimi.
   - İndikatörlerin açık kaynak kodları: LuxAlgo hangi sürüm ve ayar, seans indikatörü, gri bölge çizici var mı.
6. **Kaynak eksikleri:**
   - "Liquidity **Part 2**" var, Part 1 yok.
   - SG'nin bahsettiği "PD Arrays" ve "Daily & Weekly Bias" kitapları yok.
   - N-A3'ün verdiği Google Drive linkleri açılmadı.
7. **Kaynaklarda adı geçip tanımı olmayan kavramlar:**
   - Mitigation, propulsion ve vacuum block.
   - NWOG.
   - Makroların tam listesi.
   - "JB".
   - HVI ve AHS (LQ).
   - Ping Pong kuralları (LQ).

## B. Çelişkiler (kaynaklar farklı söylüyor; bot için birinin seçilmesi gerek)
| # | Konu | Farklı görüşler |
|---|---|---|
| 1 | Killzone saatleri | NY: 07-10, 07-09, 07-11, 08:30-11, 08-11:30. Asya: 20-24 vs WB'deki "8-12PM" yazım hatası (01/06) |
| 2 | 2022 modelinde stop | En düşük dip [G4] / FVG'nin 3 mumunun en düşüğü [SG] / swing veya FVG 1. mumu [EM] / FVG'yi yaratan mum [N-A3] / sweep fitili + tampon [N-ana] |
| 3 | 2022 modelinde giriş | FVG içinde limit [SG] / FVG'nin ucunda [EM] / CE / complete fill [SG giriş tipleri] |
| 4 | MSS'in kırdığı swing | En yakın karşı swing / sweep'ten ÖNCE oluşan swing [SG buy] / sweep'ten SONRA oluşan swing [SG sell] |
| 5 | Fitil mi kapanış mı | MSS: gövde kapanışı [N-ana]. FVG geçersizliği: gövde kapanışı [N-A3]. IFVG: gövde [EM] vs fitil veya kapanış [FluxCharts]. Breaker: "tartışmalı" [FluxCharts] |
| 6 | BOS / MSS / CHoCH adları | Her kaynak farklı (01/01). N-A3: BOS > MSS. FluxCharts: BOS SMC kavramı. LQ: BMS/FMS |
| 7 | OB tanımı | Son karşı mum [WB] / en büyük aralıklı karşı mum [N-A3] / "son yukarı mum" [N-A5, hatalı] / fitil-gövde seçimi FVG örtüşmesine bağlı [N-A3] |
| 8 | OTE aralığı | 62-79 / 70.5-79 / 61.8-78.6 |
| 9 | Hedef | Sabit 2R [N-A3, N-A5] / 3R [MQL5] / "RR değil likidite" [EM] / 1:2 [FluxCharts] |
| 10 | Bias şartı | Zorunlu [çoğu] / 2022 akış şemasında yok [SG] / "killzone değil HTF fitili önemli" [TTrades] |
| 11 | FVG dolunca | "Dönüş olasılığı yüksek" [LQ] vs "FVG tutmalı, gövdeyle geçilmemeli" [N-A3] |
| 12 | FVG adlandırması | "Undervalued = bearish" [N-A2]; standart dışı ve kafa karıştırıcı |

## C. Beğenmediğim / güvenilmez bulduğum kısımlar
1. **Kanıtsız sayısal iddialar:**
   - "Ayda 20R" [MQL5]. Ürün satış sayfası.
   - "Boğa haftasında %70 Salı dip", "%90 Perşembe kapatır" [N-A3].
   - "%90 London/NY günün tepe/dibini yapar", "ortalama 20 günde dönüş", "fiyatın %80'i range" [LQ].
   - "ICT yüksek kazanma oranına sahip" [TS].
   - Hiçbirinde veri veya test yok. Önceki turnuvada test edilen benzer kurallar maliyet sonrası kenar vermedi.
2. **Test edilemez inançlar:**
   - "Algoritma fiyatı verir, alım-satım baskısı yoktur."
   - "Merkez bankası verisi."
   - "Kaybettiğimde sorumlu değilim."
   - Bunlar bot kuralı olamaz.
3. **Makine çevirisi:** Notion'daki Türkçe metin ciddi hatalı. "BİT" = ICT, "Boost of Support" = BOS gibi. Bu repoda düzeltildi (06_SOZLUK). Orijinal Türkçe metne güvenmemek gerekir.
4. **Fazla model, tek iskelet:** 20'den fazla isimli model aslında aynı 5 adımın varyasyonu. Bot için tek, iyi tanımlanmış bir iskelet + etiketler daha sağlıklı.
5. **Seçim yanlılığı:** Ekran görüntülerinin neredeyse tamamı kazanç. Bunlar "model tutuyor" kanıtı olarak kullanılamaz.

## D. Kullanıcıya sorular (cevaplar 04'teki taslağı netleştirir)
1. Gri bölgeler hangi zaman diliminden: 15m mi, 1H mi, 4H mi? FVG mi, OB mi, ikisi de mi? Elle mi çiziyorsun, indikatör mü?
2. Kesikli çizgi neyi gösteriyor: kırılmasını beklediğin swing mi? Kırılım için mum **kapanışı** mı şart, fitil yeter mi?
3. Kırılımı hangi TF'de bekliyorsun: 1m mi, 3m mi, 5m mi? Enstrümana göre değişiyor mu?
4. Girişi tam olarak nereden yapıyorsun: FVG'nin başı, ortası, OB?
5. Bias'ı nasıl belirliyorsun? Bias'a karşı işlem alıyor musun?
6. EMA 20/50/100/200'ü ne için ekledin: trend filtresi mi? Ters dizilimde işlem almıyor musun?
7. Hangi saatlerde işlem yapıyorsun? Pencere dışında gelen kurulumu alıyor musun?
8. Haber günlerinde işlem yapıyor musun?
9. Stop'u sweep ucunun ne kadar ötesine koyuyorsun? Hedefi nasıl seçiyorsun, kısmi alıyor musun?
10. Botun izleyeceği enstrümanlar hangileri: EURUSD, GBPUSD, XAUUSD, NAS100?
11. Bu kaynaklardan hangisini **gerçekten** uyguluyorsun? Örneğin TTFM mi, 2022 mi, LQ kitabı mı?
12. Elinde **tarihli** işlem kaydı var mı (MT5 geçmişi, TradingView işaretleri, günlük)? Varsa en değerli veri bu olur.
