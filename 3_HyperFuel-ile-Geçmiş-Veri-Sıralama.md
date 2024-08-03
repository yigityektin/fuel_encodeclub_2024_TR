# HyperFuel ile Geçmiş Veri Sıralama

Yayın Kaydı: [Kayıt](https://youtu.be/XXgyc6wAbtw?si=1PkAzvMIYFyz3PU-)

##### Envio ve Fuel

Diğer protokollere kıyasla veri indekslemede büyük hızlara ulaşan Envio gün sonunda Fuel ile benzer amaçlarda hareket edebileceğini farketti.

Özellikle FuelVM'in yapısı efektiflik ve güç için Envio tarafından tercih edilme sebebi oldu.

##### Özel Sos: HyperFuel

FuelVM tercihinden sonra, tercihte karar verici olan HyperFuel veri okumak için tasarlanmış bir node yapısıdır. Konsensüs, execution gibi ayrık yapılardan ayrı olduğu için daha efektif çalışma ortamı sunar. HyperFuel, Rust tabanlı bir program olup Parquet dosyaları ile yedekleme sistemi yaratmıştır.

![1st image](/assets/images/3/1.jpg "1st image")

Blockchain'deki verileri incelerken genellikle özel alanlara odaklanılıyor. Mesela bir front-end geliştirirken sadece log verilerini önemseriz. Önceki bloğun ne olduğu, anlık ağ ücreti gibi parametrelere ihtiyacımız olmaz.

Belirli alanlara odaklanma sayesinde performans ve hız konularında artış yaşanır.

HyperFuel, HyperIndex'in yani Envio'nun backend'i gibi hareket eder.

![2nd image](/assets/images/3/2.jpg "2nd image")

HyperFuel, hızlı şekilde geçmiş verileri sıralar.

- Zincir verilerini analiz eder,
- Blok kaşifliği yapar.
- Rust, TypeScript ve Python kullanılarak etkileşime geçilebilir.

HyperIndex, akıllı kontrat tarafından desteklenen bir indeksleyicidir.

- dApp'lerin front-end'i için veri sağlar,
- Akıllı kontratlar aracılığıyla veri analizi yapar.
- JavaScript, TypeScript ve ReScript kullanılarak etkileşime geçilebilir.

**Bu yayında HyperFuel'e odaklanılacak.**

##### HyperFuel ve Özellikleri

![3rd image](/assets/images/3/3.jpg "3rd image")

- Tüm mintleme işlemleri
- x varlığının tüm işlem çıktıları
- x ve y blokları arasındaki oluşturulan tüm kontrat adresleri
- Predicate'in tüm girdileri
- x kontratını çağırma ile gelen tüm veriler

##### Örnekler

##### 1. Örnek: asset_id'yi alan tüm adresler

![4th image](/assets/images/3/4.jpg "4th image")

Fuel'de;

- Bloklar; id, height, time, prev_root, işlemler, ... gibi verilere sahiptir.
- İşlemler; Tx_id, status, script_data, receipts, inputs, outputs, ... gibi verilere sahiptir.
- Fuel, 13 farklı tipte Receipt'e sahiptir. Receiptler ise log_data, mint, burn, transfer, ... gibi verilere sahiptir.
- Girdiler; asset_id, predicate, uxto_id, ... gibi verilere sahiptir.
- Çıktılar; asset_id, to, amount, ... gibi verilere sahiptir.

Genel olarak, bir sıralayıcı yazdık, sıralayıcıya bir istek gönderdik ve çıktı veriyi yazdırdık. Ayrıca bu sürecin ne kadar vakit aldığını da çıkarttık.

![7th image](/assets/images/3/7.png "7th image")

Terminale sırasıyla yazılacaklar:

- python received-asset.py

Blok 0'dan 1.3 milyona kadarki bloklarda alınan tüm varlıkları değerlendirdik.

Tüm verileri değerlendirme sürecinin çıktıları:
![5th image](/assets/images/3/5.jpg "5th image")

##### HyperFuel Query

![6th image](/assets/images/3/6.jpg "6th image")

- Blok aralığı
- Dahil edilmek istenen receiptler, girdiler ya da çıktılar
- Veriden alınmak istenen veri alanları

##### 2. Örnek: NFT Bakiyeleri

Fuel üzerindeki tüm NFT'ler ve bakiyelerinin verilerini indeksliyoruz. Çok büyük bir yük olmasına rağmen yaklaşık 15 dakika sürüyor ve aşağıdaki çıktıları elde ediyoruz:

![8th image](/assets/images/3/8.jpg "8th image")

Örnekleri kendiniz denemek isterseniz ya da kodların tam haline ulaşmak isterseniz kaynaklardaki linklerden örneklerin GitHub linklerine erişebilirsiniz.

##### Bu Yayının Önemli Kaynakları

- [Envio Dokümantasyonu](https://docs.envio.dev/)
- [HyperFuel Dokümantasyonu](https://docs.envio.dev/docs/HyperSync/hyperfuel)
- [Discord](https://discord.gg/Q9qt8gZ2fX)
- [Envio X](https://x.com/envio_indexer/)
- [HyperIndex on Fuel Workshop](https://www.youtube.com/watch?v=BqiCjLKorRs)
- [1. Örnek](https://github.com/enviodev/hyperfuel-client-python/blob/main/examples/received-asset.py)
- [2. Örnek](https://github.com/enviodev/example-fuel-assets-script/tree/NFT)
