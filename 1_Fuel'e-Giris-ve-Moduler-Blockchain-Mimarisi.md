# Fuel'e Giriş ve Modüler Blockchain Mimarisi

##### Fuel İsmi Nereden Geliyor?

Öncelikle Fuel isminin nereden geldiğinden bahsedildi Fuel Network'ün asıl amacının gas faktörünü minimize etmek hatta tamamen ortadan kaldırmak olması ve fuel == gas kelimelerinin anlamdaşlığı bu süreçte yön verici oldu.

##### Fuel V1

Fuel V1 ile Ethereum'da deploylanmış ilk Optimistic Rollup olmanın yanı sıra şu an üst düzey olarak sayılan Rollupların dahi eksik olduğu bazı güvenlik faktörlerinin Fuel V1'da aktif olduğu belirtildi. Sistemin basitliği, sadece ödeme, transfer ve değiş tokuş için kullanılabilirliği yeni bir yol açtı.

##### Fuel Nedir?

Fuel, Rollupların işletim sistemi olarak da adlandırılan, yüksek performanslı ve sürdürülebilir Rolluplar inşa etmek için bir takım araçlardan oluşan bir mimaridir.

![4th image](/assets/images/4.png "4th image")

##### Fuel'in Doğuşu

Halihazırdaki VM'lerin birbirlerinin biraz değiştirilmiş kopyaları olmaları ve Fuel tarafından aşılmak istenen sorunlara tam olarak cevap verememeleri sebebiyle Fuel ortaya çıktı.

##### Fuel Neler Vaat Ediyor?

1. Bloklar arasında paralel işlem yürütme
2. Durumların (State) minimizasyonu
3. Birlikte çalışılabilirlik
4. Yapıdan gelen Hesap Soyutlama
5. Düşük Seviyede Sanal Makine
6. Rahat Geliştirici Ortamı

![6th image](/assets/images/6.jpg "6th image")

##### UTXO Modeli ve Predicate'ler

Fuel, UTXO temelli, daha rahat geliştirilebilir ve kullanışlı bir işlem modeline sahiptir. Aynı zamanda Predicate adını verdiğimiz on-chain fonksyionlar ile birlikte Akıllı Kontratların getirdiği depolama yükünden bir nebze kurtulabildiğimiz bir model öne sürülüyor.

![7th image](/assets/images/7.jpg "7th image")

##### Script'ler

Scriptler, işlemlerin geçici depolamalarının işlemlerde tutulması ve durumlara aktarılmaması ile birlikte düğümlerdeki depolamayı hafifletmeyi hedefleyen bir geliştirme aracıdır.

##### Native Varlıklar

Ağa özel (Native) varlıklar, tek bir durum üzerinden hareket eder ve değeri olamayan durumları (NFT ile sahipliği temsil etmek gibi) temsil etmekte kullanılabilirler.

##### Predicate'ler ve Kullanım Alanları

Predicateler ise transfer ve işlemleri yapabilmek için durumsuz kodlardır. Predicateler ile birlikte Hesap Soyutlama ve Durumsuz DeFi ürünleri yaratılabilir.

##### FuelVM ve Farklılıkları

FuelVM'i de diğer VM'lerden ayıran birkaç yapısal farklılık var. İşte FuelVM'in yapısı ve farklılıklarından bazıları:

![11th image](/assets/images/11.jpg "11th image")

##### Sway

Fuel ağının kendi kodlama dili olan Sway'den bahsederken de bir akıllı kontrat dili demek yerine bir blockchain dili demek tercih ediliyor. Çünkü akıllı kontratların yanı sıra Predicateler ve Scriptler de Sway ile kodlanabilir durumdalar.

##### Fuel'in Mimarisi

Fuel ağının genel yapısından da aşağıdaki görseldeki şekilde bahsedildi:

![13th image](/assets/images/13.jpg "13th image")

Ayrıca Fuel ağının çıkış tarihi olarak 2024, Q3'ün sonu tahmin ediliyor.

##### Puan Programı

Sunumun sonunda ise Fuel tarafından yakın zamanda başlatılan puan programından bahsedildi. Detaylı bilgi için önceki tweetimize göz atabilirsiniz:

[Tweet Link](https://x.com/fuelnetworkTR/status/1810596755123155281)

##### Yayında Belirtilen Kaynaklar

- [Fuel Nedir?](https://docs.fuel.network/docs/intro/what-is-fuel/)
- [Sway Book](https://fuellabs.github.io/sway/v0.62.0/book/)
- [Sway Playground](https://www.sway-playground.org/)
- [Forum](https://forum.fuel.network/)
- [Sway Örnekleri](https://github.com/FuelLabs/sway-by-example)
