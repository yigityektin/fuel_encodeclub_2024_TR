# Durumsuz DeFi Uygulamaları Üretmek - On-chain Order Book Kodlama

Yayın Kaydı: [Kayıt](https://youtu.be/W73uiDjMvvc?si=T11bEgpC-NnSF9bU)

### Predicate'ler ile Yapılabileceklere Örnekler

##### Şartlı Ödemeler

Sadece belirli şartlar sağlandığında varlık transferi gerçekleştirilir. Aşağıdaki kodda, bu belirli tarihe ulaşıldığında gerçekleşir.

![1st image](/assets/images/6/1.png "1st image")

##### Çok Faktörlü Doğrulama

İşlemler sadece birden fazla katılımcı tarafından imzalanırsa devreye alınır.

![2nd image](/assets/images/6/2.png "2nd image")

##### Emanet Ödemeler

Varlıklar, işleme katılan iki taraftan da onay geldiği şartta transfer edilir. Lightning Network'e benzer şekilde.

![3rd image](/assets/images/6/3.png "3rd image")

##### Bağış Toplama Predicate'i

Kullanıcılar, bağış toplama adresine varlıklar göndereiblirler. Ve fonlar ancak belirli şartlar ya da hedefler sağlanırsa harcanabilir.

![4th image](/assets/images/6/4.png "4th image")

##### NFT Satışı

Alıcı NFT'ye sahip olmak için, istenen varlık çeşidinden belirli miktarı sağlamalıdır.

![5th image](/assets/images/6/5.png "5th image")

##### Kumar Oynamak

Kazanan, bir Pseudorandom sayı ile belirlenir.

![6th image](/assets/images/6/6.png "6th image")

##### Taahhütlü Varlıklar

Bu predicate, taahhüt edilmiş varlıkları belirli şartlar altında serbest hale gelmesini sağlar. Varlıklar ancak belirli bir taahhüt sürecinden sonra serbest kalabilir.

![7th image](/assets/images/6/7.png "7th image")

##### Fomo Oyunu

Her varlık aktarımı zamanlayıcıyı sıfırlar. Ve bir zaman periyodundan sonraki son varlık aktaran kişi, tüm varlıkları kazanır.

![8th image](/assets/images/6/8.png "8th image")

##### Tahmin Marketleri

Kullanıcılar bahisler yapar ve kazanan, etkinliğin sonucu belirli olduktan sonra belirli olur.

![9th image](/assets/images/6/9.png "9th image")

##### Basitleştirilmiş SPARK Orderbook Predicate'i

![10th image](/assets/images/6/10.png "10th image")

### Nasıl Predicate Yazılır?

Terminale yazılacaklar:

- forc new predicates-test
- cd predicates-test
- code .

* kodunuzu yazın

- forc build
- cargo generate --init fuellabs/sway templates/sway-test-rs --name orderbook
