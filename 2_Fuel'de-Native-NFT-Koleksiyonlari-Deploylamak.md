# Fuel'de Native NFT Koleksiyonları Deploylamak

Yayın Kaydı: [Kayıt](https://youtu.be/JzQpITmqSj4)

##### Fuel'i Özel Kılan Farklar Neler?

- Fuel Sanal Makinesi: FuelVM
- UTXO Modeli ile birlikte Paralel İşlem Yürütme
- Blokzincir Durumlarını Minimize Etmek
- Ethereum ile birlikte Çalışılabilirlik

##### UTXO Modeli

Birden fazla durum bir ağaç şeklinde aynı anda tutulabilir.

![1st image](/assets/images/2/1.jpg "1st image")

Bu modelde, her işlem önceki işlemlerin kullanılmamış çıktılarından oluşur ve bu çıktılar girdi olarak kullanılır. Her işlem, yeni çıktılar oluşturur ve bu çıktılar daha sonra diğer işlemler için kullanılabilir hale gelir.

![2nd image](/assets/images/2/2.jpg "2nd image")

##### Temel Yapı

- Fuel: Genel Mimari
- Sepolia Testnet Ağı: Ethereum'daki Fuel L2 Testneti
- Sway: Rust benzeri Akıllı Kontrat Kodlama Dili
- Forc (Fuel Orchestrator): Hepsi bir arada olan bir geliştirici aleti. Cargo ya da npm'e benzerdir.
- Fuels: Fuel'in SDK yani geliştirici kiti. TypeScript ve Rust olarak 2 dilde vardır.
- Fuelup: Geliştirici aletinin yönetimini sağlayan parçadır. nvm ya da rustup'a benzerdir.

##### Fuel dApp'lerini Farklı Kılan Özellikler

![3rd image](/assets/images/2/3.jpg "3rd image")

- Ethereum, Solidity dilini kullanırken; Fuel, Sway dilini kullanır.
- Ethereum, EVM yani Ethereum Sanal Makinesini kullanırken; Fuel, FuelVM yani Fuel Sanal Makinesini kullanır.
- Ethereum, Indexer olarak The Graph'e sahipken; Fuel, Envio/Subsquid'e sahiptir.
- Ethereum, geliştirme ve deployment için Hardhat ve Foundry'e sahipken; Fuel, forc'a sahiptir.
- Ethereum, geliştirici kiti olarak Web3.js ve ethers.js kullanabilirken; Fuel, Fuels TS ve Fuels RS kullanabilir.

##### Solidity ve Sway Arasındaki Farklılıklar

![4th image](/assets/images/2/4.jpg "4th image")

- Solidity, Javascript'e benzeyen bir yapıya sahipken; Sway, Rust'a benzeyen bir yapıya sahiptir.
- Solidity, inheritance'a sahipken; Sway, paradigm karakter özelliklerini gösterir.
- Solidity, EVM'e özel tasarlanmıştır; Sway, FuelVM'in desteklediği her blockchaine uyumludur.
- Solidity, tekli içerik tutabilirken; Sway, birden fazla içeriği tutarak hareket edebilir.

##### Program Tipleri

- Solidity ile sadece Akıllı Kontratlar ve Kütüphaneler kodlanabilir.
- Sway ile Akıllı Kontratlar, Scriptler, Predicateler ve Kütüphaneler kodlanabilir.

##### Kod Karşılaştırması

![xth image](/assets/images/2/aftercontextsol.png "xth image")

![yth image](/assets/images/2/aftercontextsway.png "yth image")

##### Yazım Şekli ve Depolama

![5th image](/assets/images/2/5.jpg "5th image")

- Solidity, C++, Python ve Javascript'ten ilham alarak oluşturulmuştur; Sway, Rust temellidir.
- Solidity, Opt-out depolama erişimini destekler; Sway, Opt-in depolama erişimi izinlerini destekler.
- Solidity, depolama manipülasyonları kodlama dillerinin konseptlerine dayanır; Sway, depolama manipülasyonları kendi kütüphanesine ve kullanıcı tarafından tanımlanan tiplere dayanır.
- Solidity, namespacing ya da depolama alanı değişimine yapısı gereği izin vermez; Sway, depolama namespacing'ine izin verir ve depolama alanlarını nerede istediğinize göre değiştirebileceğiniz bir yapıya sahiptir.

##### Standart Kütüphaneler

![6th image](/assets/images/2/6.jpg "6th image")

- Solidity, standart kütüphaneye sahip değildir. Open-Zeppelin gibi birkaç modüle sahiptir.
- Sway, standart kütüphaneye ve çekirdek bir kütüphaneye sahiptir. Başlangıçtaki süreçleri ya da import ederken versiyon farklarını dert etmenize gerek olmaz.

##### Fungible Tokenlar

![7th image](/assets/images/2/7.jpg "7th image")

- Solidity, ETH dışında native varlığa sahip değildir. Sadece uygulama seviyesinde tokenlara sahip olabilir. ERC-20 kontratları Open-Zeppelin aracılığıyla özelleştirilir. Onaylama ve transfer yaklaşımına ihtiyaç duyar.

- Sway, FuelVM'in desteklediği her native varlığı destekleyebilir. Uygulama seviyesinde tokenlara sahip olabilir. Sway SRC-20 standartı özelleştirilebilir. Fuel'deki tüm akıllı kontratlar mint ve burn özelliğine yapısı gereği direkt sahiptir. Fuel'de çağrılar herhangi bir native varlığı transfer etmeye yarayabilir. Scriptler sayesinde onaylama ve transfer süreci tek bir işlem içerisinde yapılabilir.

##### Sway Standartları Nedir?

![8th image](/assets/images/2/8.jpg "8th image")

Sway standartları, import etmeniz ve Sway dilindeki standartları kullanmanız için bir repository'de tutulmaktadır. Repository'de çeşitli seviyelerde geliştirme standartları bulabilirsiniz.

İhtiyacınız olan standartı bulun ve standart ABI'ını kontratınıza aktarın.

##### Sway Standartları: Native Varlıklar

- SRC-20: Sway dilini kullanan Native varlıkların standart API ile implementasyonunu içerir.
- SRC-3: Fungible varlıklar için mint ve burn mekanizmasını sağlar.
- SRC-7: Native varlıkların metadatasını depolamak için kullanılan Rastgele Varlık Metadata Standartıdır.
- SRC-9: SRC-7 standartıyla birleşerek Native varlıklar için standartlaşmış metadata anahtarlarını depolamak için kullanılan Metadata Anahtar Standartıdır.
- SRC-6: Varlık depolarının implementasyonu için tanımlanan standart API'dır.
- SRC-13: Soulbound Adresi, Native varlıkların soulbound olarak kilitlenmesini sağlar.

##### Standartların Kullanımı

Alttakini, projenişn Forc.toml dosyasına ekleyin:

![zth image](/assets/images/2/swaystandards1.png "zth image")

İstediğiniz standardı Sway Akıllı Kontratınıza dahil edin:

![ath image](/assets/images/2/swaystandards2.png "ath image")

##### İhtiyacınız Olan İndirmeler

- Node.js
- Fuel Geliştirici Aleti

Detaylar: [İndirmeler](https://tinyurl.com/FuelSetup)

##### Fuel Ağı ve NFT'ler

Fuel Ağındaki tüm NFT'ler Native varlıklardır.

##### Önce Temeller

Hangi Standartlar Kullanılmalı:

- SRC-20: Native Varlıklar
- SRC-3: Mint ve Burn
- SRC-7: Metadata Standartları

Native Varlık Kütüphanesi: Standartlar dahilindeki basit fonksiyonları implemente etmek içindir.

##### NFT Koleksiyonları

Depo: [NFT Koleksiyonları](https://tinyurl.com/NFTonFuel)

##### NFT Koleksiyonu Kodlamaya Başlangıç

![15th image](/assets/images/2/15.jpg "15th image")
![16th image](/assets/images/2/16.jpg "16th image")
![17th image](/assets/images/2/17.jpg "17th image")
![18th image](/assets/images/2/18.jpg "18th image")

Terminalinize girdikten sonra sırasıyla kullanmanız gereken kodlar:

- forc
- forc new hello_world
- forc build
- 1
- y

hello_world kontratınızı ağa aktarmış oldunuz.

##### Bu Yayının Önemli Kaynakları:

![19th image](/assets/images/2/19.jpg "19th image")
