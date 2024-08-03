# Fuel'de Envio ile 5 Dakikadan Daha az Sürede Veri İndeksleme

Yayın Kaydı: [Kayıt](https://youtu.be/BqiCjLKorRs?si=WS2OnhfN976TlA0r)

##### Akıllı Kontrat Mühendisinin ve DApp Geliştiricinin Sorumlulukları:

- Gas (Ağ ücreti) Maliyeti
- Veriyi Elde Etme Maliyeti
- Verinin Erişilebilirliği

##### Akıllı Kontrat Tasarımı

![1st image](/assets/images/4/1.jpg "1st image")

Verileri odağımıza alarak akıllı kontrat tasarlarken off-chain hesaplama, ağ ücretleri ve veri erişilebilirliğinin en ortada en efektif olabileceği yeri düşünerek hareket ederiz.

##### Direkt Depolamadan Okusak?

Depolamayı Tanımlayalım:
![2nd image](/assets/images/4/2.png "2nd image")

SDK ile Veri Depolamasını Front-End'de Kullanalım:
![3rd image](/assets/images/4/3.png "3rd image")

[Kaynak Link](https://docs.fuel.network/guides/counter-dapp/building-a-smart-contract/)

Bu yöntemde birkaç sorun ile karşılaşıyoruz:

- Ağ ücreti kullanımı sınırlaması
- Okuma yerine depolama için optimize edilmiş olma
- Uzun cevaplama süresi
- Sadece son kontrat durumu
- Veriyi birleştirmek ya da filtrelemenin mümkün olmaması

##### İndeksleme Nedir?

Veri İndeksleme Şeması:
![4th image](/assets/images/4/4.jpg "4th image")

- Kullanıcı işlemini akıllı kontrata gönderir,
- Akıllı kontrat veriyi, veri indeksleyiciye gönderir ve receipt oluşturulur,
- Birleştirilmiş veri depolanmak için PostgreSQL veritabanına gönderilir,
- GraphQL API, Query Etkinlik Verilerini yeniden PostgreSQL veritabanına gönderir.

Sway'de Yapılışı:
![5th image](/assets/images/4/5.png "5th image")

Solidity'de Yapılışı:
![6th image](/assets/images/4/6.png "6th image")

##### Ağ Kaşifine bir Bakış

![7th image](/assets/images/4/7.jpg "7th image")

[Kaynak Link](https://app.fuel.network/tx/0x2164dfd7a16c7bec4a63e9c0b986edae41707f82e080ab5853829e6312523366/simple)

##### Sway Farm

![8th image](/assets/images/4/8.jpg "8th image")

[Oyun Link](https://swayfarm.xyz)

Akıllı Kontrat: [Kaynak Link](https://github.com/FuelLabs/sway-farm)

Terminale yazılacaklar:

- npx envio@next init
- sway-farm-indexer
- sway-farm-indexer
- dil seçin
- blockchain seçin
- Contract Import
- dosya dizininizi yazın (ör. ./sway-farm/contract/out/debug/contract-abi.json)
- seçmek istediğiniz indexi seçin
- kontrata isim girin
- kontrat adresinizi yapıştırın
- bitirdiğinizi seçin

##### Örnek: İndeksleyici Deploylama

Spark-Fi: [Link](https://sprk.fi/)
