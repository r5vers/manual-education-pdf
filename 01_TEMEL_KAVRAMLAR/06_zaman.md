# 6. Zaman: seanslar, killzone, Silver Bullet, makrolar, açılış fiyatları

Tüm saatler **New York saati (EST/EDT)** cinsinden. Türkiye saati yaz döneminde NY + 7, kış döneminde NY + 8. Kaynaklar: N-ana, N-A3, N-A5, SG, EM, WB, LQ.

## 6.1 Killzone ve seans saatleri: kaynakların hepsi yan yana

| Pencere | N-A3 | N-A5 | WB | MQL5 [N-ana] | SG / EM | LQ |
|---|---|---|---|---|---|---|
| Asya | 20:00-00:00 (likidite); seans 19:00-04:00 | — | **"8:00-12:00PM"** (yazım hatası, 20:00-00:00 olmalı) | — | — | Asya → Frankfurt → London |
| London killzone | 02:00-05:00 | 02:00-05:00 | 02:00-05:00 | **02:00-05:00** | — | London açılışı |
| NY killzone (forex) | 07:00-10:00, bir yerde 07:00-09:00, bir yerde 07:00-11:00 | 07:00-10:00 | 07:00-10:00 | **07:00-10:00** | — | NY açılış tuzağı |
| NY (endeks/futures) AM | 08:30-11:00, bir yerde 08:30-11:30 | 08:00-11:30 | — | — | EM: 08:30-11:00 | — |
| London close | — | 10:00-12:00 | 10:00-12:00 | — | — | "LC" |
| Öğle (işlem yok) | 12:00-13:00 (13:30'a kadar) | — | NY öğle = geri çekilme | — | SG: "Noon – lunch" | — |
| PM | 13:30-16:00, ayrıca 13:30-15:00 / 13:30-15:30 | — | — | — | EM: 13:30'dan itibaren | — |

**Tutarlı olan:** London 02-05 ve NY forex 07-10 neredeyse tüm kaynaklarda aynı. Kullanıcının seans indikatöründe "London", "NY AM", "LO close" kutuları görünüyor.

## 6.2 Silver Bullet (1 saatlik pencereler) [SG, WB, N-ana]
- **Pencereler:** London 03:00-04:00, AM 10:00-11:00, PM 14:00-15:00.
- **WB:** "Her zaman devam setup'ıdır." FVG girişi kullanılır.
- **SG:** Endekste asgari çerçeve 10 puan. Çerçeve, giriş-çıkış değil, beklenen en iyi teslimattır.
- **SG çerçeveleri:** PDH/PDL DOL, önceki seans H/L, önceki hafta H/L, NWOG'a dönüş veya uzaklaşma, OTE, 2022 modeli.

## 6.3 Açılış fiyatları
- **Gece yarısı açılışı (00:00, True Day Open / TDO):** "Algoritmanın günlük açılışı." Günlük manipülasyonu okumak için kullanılır. [N-A3, N-A5, LQ]
- **08:30:** Haber ambargosu kalkar, NY seans manipülasyonu başlar. Çoğu zaman 8:30 civarında sweep olur. [N-A5, SG, EM]
- **09:30:** Hisse senedi piyasası açılışı. Endekste 9:30-9:40 manipülasyon, 9:40-9:50 giriş, 9:50-10:10 hedef ("NY Open Macro", SG s.21).
- **Haftalık açılış ve NWOG** (New Week Opening Gap): Adı geçiyor, tanımı yok. [SG]

## 6.4 ICT zaman rehberi [EM s.8, ICT kaynaklı]
- **AM:**
  - 08:30 haber.
  - 09:30 açılış.
  - 10:00 ilk 30 dk sonrası (Judas).
  - 10:30 ilk 60 dk sonrası.
  - 11:00 Perşembe/Cuma dönüş günleri.
- **PM:**
  - 13:30 öğle bitişi.
  - 14:00 PM trendi başlar, AM stop'ları temizlenir.
  - 14:30 son iki saat.
  - 15:00 son saat.
  - 15:30 market-on-close.
- **Makrolar** [N-A3]:
  - "15:00-16:00 arasında 3 makro çalışır."
  - 9:50 makrosu (EM örneği).
  - **Makroların tam listesi kaynaklarda yok.**

## 6.5 90 dakikalık döngü [LQ]
- 00:00 NY'den başlayarak her 90 dakikada bir açılış fiyatı işaretlenir. Amaç, sahte hareketi görmek. **Kanıt sunulmamış.**

## 6.6 Gün ve takvim kuralları
- **İşlem yapılmayacak günler:**
  - FOMC, NFP, CPI günleri. [N-A3]
  - Büyük range gününden sonraki AM seansı. [N-A3]
- **Pazartesi:** ICT Pazartesi işlem yapmaz. [N-A3]
- **Ekim yarısı ve Aralık:** ICT bu dönemleri es geçer, Ocak ortasına kadar demo. [N-A3]
- **Haftalık profil iddiaları (kanıtsız, test edilmemiş):**
  - "Boğa haftasında %70 olasılıkla Salı (veya Pzt-Sal-Çar) haftanın dibi." [N-A3]
  - "Pazartesi haftanın ucunu yaparsa %90 Perşembe haftayı kapatır." [N-A3]
  - "Haftalık bias doğruysa %70 Salı dip, Perşembe tepe." [N-A3]
  - "Pazartesi manipülasyon, Cuma dağıtım" vb. [LQ]
- **Mevsimsellik:** "Nisan son haftası → Mayıs piyasa zayıf eğilimli." [N-A3]

## 6.7 Zaman ilkeleri (kaynakların ortak söylemi)
- "Önce zaman, sonra fiyat." Kilit PD array'de değilse zaman, zaman uygun değilse fiyat işe yaramaz. [N-A3]
- **TTrades, farklı görüş:** "Kesin killzone çok önemli değil. Önemli olan HTF mumunun fitilinin oluşmuş olması." Reversal Asya'da veya London başında olabilir. 4H profilde genelde 22:00 veya 02:00 mumu.

## Bot için öneri
- **Pencereler:** London 02:00-05:00 ve NY 07:00-10:00. Kaynakların ortak noktası ve kullanıcının etiketleri bunlar.
- **Diğerleri:** Silver Bullet ve LO close etiket olarak hesaplanır.
- **Haber filtresi:** FOMC/NFP/CPI günleri işaretlenir. Kapatıp kapatmama **kullanıcıdan.**
- **Saat dilimi:** Tek kaynak NY saati olur. Telegram mesajında TR saati de yazılır.
