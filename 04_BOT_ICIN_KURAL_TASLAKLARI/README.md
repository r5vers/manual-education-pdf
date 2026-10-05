# Bot için kural taslağı (ONAYSIZ, yalnız öneri)

> **Güncelleme (5 Ekim 2026):**
> - Bu taslağın yerine **[07_TEK_KURAL_SETI.md](../07_TEK_KURAL_SETI.md)** içindeki AZG-K1 v1 geçti; kullanıcının cevaplarıyla netleştirildi.
> - Aşağıdaki tablo yalnız tarihçe için duruyor.
> - Kullanıcının tarihli işlem kaydı olmadığı için doğrulama planı da 07'de güncellendi.

Bu dosya, botun (Telegram gözcüsü) kullanıcının tarzını taklit edebilmesi için gereken mekanik tanımı **taslak** olarak verir.
- Bot kodunda hiçbir değişiklik yapılmadı. Kullanıcı "başla" demeden yapılmayacak.
- Bot işlem açmaz; TP, SL veya lot vermez. Yalnız yön ve gerekçe bildirir. Aşağıdaki stop/hedef seviyeleri yalnız **iç değerlendirme** (sinyal tuttu mu?) içindir.

## Taslak model "AZG-K1": kullanıcının görsellerinden + ICT 2022 / SG Model 1'den

| Adım | Tanım (öneri) | Dayanak | Açık parametre / soru |
|---|---|---|---|
| 0. Enstrüman | EURUSD, GBPUSD, XAUUSD, NAS100 | Görsellerde görülenler (03) | Botun izleyeceği liste? |
| 1. Zaman | London 02:00-05:00 ve NY 07:00-10:00 (NY saati); etiketler London / NY AM / LO close | 01/06; görsellerdeki seans kutuları | Görsellerde 00:30-09:00 arası da işlem var. Pencereler ne kadar geniş olsun? |
| 2. Bağlam bölgesi ("gri bölge") | Üst TF'de dolmamış FVG veya OB; ya da seans tepe/dibi, PDH/PDL | 03 ortak desen; SG Model 1 "HTF POI" | Gri bölge hangi TF'den (15m / 1H / 4H)? FVG mi OB mi? Elle mi çiziliyor? |
| 3. Sweep | Fitil bölgedeki swing'in veya seans ucunun ötesine geçer, aynı veya sonraki mumlarda içeri kapanış | 01/02 | Tek mum şartı var mı? Hangi swing'ler sayılır? |
| 4. Kırılım (MSS/"BOS") | Sweep ucundan önce oluşan son karşı swing (3 mumlu pivot) **gövde kapanışıyla** aşılır; kıran bacakta FVG var | 01/01; SG akış şeması; kullanıcının kesikli çizgileri | Kırılım TF'si 1m mi 3m mi? Kapanış mı fitil mi? |
| 5. Giriş bölgesi | Kırılım bacağındaki FVG (yoksa OB); FVG, sweep→kırılım aralığının %50'sinin doğru tarafında | 01/03, 01/05 | Giriş FVG ucu mu, CE mi, OB mi? |
| 6. Geçersizlik (iç) | Sweep ucunun ötesi + spread | Görseller; N-ana MSS | — |
| 7. Hedef (iç) | En yakın karşı likidite (swing / seans ucu / karşı gri bölge); R ≥ 1.5 | Görseller; N-A3 | Asgari R? Kısmi kâr kuralı? |
| 8. Ek etiketler (filtre değil) | EMA 20/50/100/200 dizilimi, OTE, SMT, haber günü, bias | 01/07-09 | EMA'lar filtre mi? Bias nasıl belirleniyor? |

## Telegram mesajı örneği (taslak)
```
EURUSD — SHORT fikri (London, 03:12 NY / 10:12 TR)
• Bağlam: 15m bearish FVG (1.14420-1.14445) içinde
• Sweep: Asya tepesi 1.14436 alındı, 1m içeri kapandı
• Kırılım: 1m swing dibi 1.14398 gövdeyle kırıldı (displacement + FVG)
• Giriş bölgesi: 1m FVG 1.14405-1.14412 (%50'nin üstünde, premium)
• Etiketler: EMA'lar aşağı dizili | SMT (GBPUSD) yok | haber yok
```

## Doğrulama planı (sırayla, her adım onayla)
1. **Kullanıcı etiketlemesi:** Kullanıcı 20-30 işlem verir. **Tarih ve saatleri** belli olmalı; kayıplar ve "girmedim çünkü…" örnekleri de dahil. Her biri için tek satır gerekçe yazar.
2. **Dedektör (araştırma klasöründe, botta değil):**
   - AZG-K1 o tarihlerin verisinde çalıştırılır.
   - **Yakalama:** Kullanıcının işlemlerinin yüzde kaçını aynı anda buluyor?
   - **Fazla sinyal:** Kullanıcının girmediği kaç sinyal üretiyor?
   - Uyuşmayan her vaka için kural değil parametre tartışılır.
3. **Ön-kayıt:** Parametreler dondurulur, sonuç görülmeden yazılır.
4. **Test:**
   - DEV dönemi.
   - Sonra hiç bakılmamış dönem (EURUSD için mühürlü Validation/Holdout dilimleri yalnız ön-kayıttan sonra açılır).
   - Maliyet dahil, plasebo karşılaştırmalı.
5. **Bota ekleme:** Ancak 4. adım geçerse ve kullanıcı "başla" derse. İlk aşamada yalnız "gözcü" modunda.

## Gerçekçi beklenti
Bu ailenin literatürdeki varsayılan mekanik sürümleri önceki turnuvada **maliyet sonrası kenar vermedi** (bkz. 02/00). Kullanıcının elle yaptığı seçim, mekanik sürümde olmayan bir şey içeriyor olabilir: bağlam, bias, zaman. 1-2. adımlar bunun ne olduğunu ortaya çıkarmak için var. Çıkmazsa bunu açıkça söyleyeceğim.
