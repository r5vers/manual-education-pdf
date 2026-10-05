# 8. SMT ve korelasyon

Kaynaklar: WB, SG, N-A3, N-ana (MQL5, Reddit), EM.

## 8.1 SMT (Smart Money Technique) divergence
- **Tanım:** Normalde birlikte hareket eden iki enstrümandan biri eski tepe/dibini alır, diğeri alamaz. Korelasyonda "çatlak" oluşur. [WB, N-A3, SG]
- **Hangi enstrüman işlenir:**
  - WB: "Zayıf olanı, yani likiditesi alınmayan/geride kalanı işle."
  - SG: Sick Sister'da zayıfa odaklanılır.
- **Çiftler:**
  - Endeks: ES ↔ NQ ↔ YM (US500 ↔ US100 ↔ US30).
  - Forex: EURUSD ↔ GBPUSD.
  - **Ters korelasyon:** DXY ↔ EURUSD ve DXY ↔ endeksler. Dolar yukarı = endeks aşağı (risk-off). [WB]
- **Önkoşul:** "SMT yalnız HTF anlatı/bias varsa işe yarar, teyit içindir." [N-A3]
- **Stop hunt teyidi:** Biri stop'ları alamazsa gerçek bir stop hunt'ın güçlü işaretidir. [N-A3]
- **SG:** SMT'yi Model 1-4'ün varyasyonu olarak kullanır. Diplerdeki uyumsuzluk sweep'in yerine geçebilir.
- **EM:** "Varlıkta stop raid yoksa korele SMT kullanılabilir."

## 8.2 DXY teyidi (MQL5 stratejisi) [N-ana]
- "DXY kendi seviyesini almadan EURUSD long yok." EURUSD PDL raid'i ile DXY'nin PDH raid'i eşleşmeli.

## 8.3 Sick Sister [SG s.32-33]
- ES/NQ/YM üçlüsünde ikisi eski tepe/dibi alır, biri alamaz (failed SMT).
- Zayıf olan önce derin discount/premium'a gider, sonra failed SMT'nin EQH/EQL'ını hedefler.

## Kullanıcının durumu
- Kullanıcının ekran görüntülerinde SMT veya ikinci enstrüman yan yana **görünmüyor.** SMT kullanıp kullanmadığı **bilinmiyor.**

## Bot için öneri
- **Bot SMT'yi şu çiftlerde hesaplayabilir:**
  - EURUSD ↔ GBPUSD ↔ DXY.
  - NAS100 ↔ SPX500.
  - XAUUSD ↔ DXY.
- **Kullanım biçimi:** Zorunlu filtre değil, sinyal mesajında "SMT var/yok" satırı olarak.
- **Kanıt:** Önceki turnuva testinde (M08) SMT tek başına kenar vermedi.
