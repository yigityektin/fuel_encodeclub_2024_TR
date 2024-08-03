# Yeni Akıllı Kontratlar, Predicateler

Yayın Kaydı: [Kayıt](https://youtu.be/5bCqGlzTk2M?si=63eMBrcpMz03GhYC)

### Problemler: Blockchainler Gittikçe Büyüyor

##### Ağınız ne kadar ağır?

![1st image](/assets/images/5/1.jpg "1st image")

##### Blockchainler Ağırlaştığında Ne Olur?

![2nd image](/assets/images/5/2.jpg "2nd image")

Ethereum ekibinden Peter'dan bir tweet: "Ethereum'un Geth'den dolayı yavaş olduğunu söylemeyi bırakın. Ağ ücreti limitini 10 katına çıkarabilirsiniz ve Geth hiçbir sorun çıkartmaz.

Ethereum yavaş çünkü durum büyümesi çok hızlı gerçekleşiyor. Geth ya da başka bir client kullanıldığında da aynı şey gerçekleşecek. Durumları başka bir yerde depolamanız gerekiyor."

![3rd image](/assets/images/5/3.jpg "3rd image")

### Blockchainler bu 3 parçalı döngü içinde boğuluyor:

- Blockchainimiz çok ucuz!,
- Zincirimiz pahalı ama bunun sebebi popüler olması,
- Zincirimiz, diğer zincirler için bir yürütme katmanı olarak var oluyor.

##### Bu döngüden nasıl çıkabiliriz?

- Çok çok hızlı büyümeyen zincirler yapmak
- Uygulamaları nasıl yaptığımızı değiştirmek

### Bitcoin

Kısaca bir geri dönüş yapalım.

##### Bitcoin'de sadece 2 tip varlık/süreç vardır:

- Coinler
- Hesaplar

![4th image](/assets/images/5/4.jpg "4th image")

##### Bitcoin Hesap Tipleri

Herkese Açık Anahtarlar: Bağlı olduğu gizli anahtar ile işlemleri imzalayarak coin harcanır.

Scriptler: Script'i sağlayarak bytecode hashlerinin adrese sağlanması ve yürütmenin başarılı bir şekilde gerçekleşmesiyle coin harcanır.

### Scriptler

##### Script Oluşturmak

![5th image](/assets/images/5/5.jpg "5th image")

Script oluşturmak 3 aşamadan oluşur:

- Script'i yazmak ve derlemek,
- Hash Script'i adrese göndermek,
- Coinleri adrese göndermek.

Farkındaysanız, hiç kod göndermedik.

##### Script'i Çalıştırmak

İşlemler şunlara sahip olmalıdır:

- Girdi olarak verilen coinler,
- Script bytecodelarını eşlemek,
- Herhangi Script girdisi (imzalar, vs).

Script, zincirin durumlarında depolanmaz.

### State'e Neler Katılır

##### Bitcoin

- UTXO'lar (miktar ve sahip)

##### Ethereum

- Hesaplar (ETH miktarı & nonce değeri)
- Kontrat bytecode'u
- Kontrat depolaması

Ana faktör ise Bitcoin'in basitçe yaratılan hafifliğini ve Ethereum'un gücünü birleştirebilip birleştiremeyeceğimiz.

![6th image](/assets/images/5/6.jpg "6th image")

### Predicate'ler

Bitcoin'in durumsuzluğunun basitliği ve Ethereum Sanal Makinesi'nin (EVM) gücünün birleşimi ise, Predicate'leri oluşturuyor.

- Predicate'ler sadece birer adreslerdir
- Oluşturulmamıştır ya da ağa önceden aktarılmamıştır
- Sadece kendi varlıkları için kullanışlıdır
- Sadece varlıkların predicate'lerden harcanmaya çalıştığı senaryoda kod ortaya çıkar

##### Hediye Verme Predicate'i

![7th image](/assets/images/5/7.png "7th image")

##### Şifre Korumalı Token Predicate'i

![8th image](/assets/images/5/8.png "8th image")

##### Native Hesap Soyutlama Predicate'i

![9th image](/assets/images/5/9.png "9th image")

Predicate temelli hesaplar yaptık, peki predicate temelli uygulamalar yapabilir miyiz?

##### Predicate temelli Limit Order

![10th image](/assets/images/5/10.png "10th image")

![11th image](/assets/images/5/11.jpg "11th image")

- Kullanıcı, teklifi açar ve Predicate ile etkileşime geçer,
- Predicate'i gerçekleştiren aracı teklifi kabul ederse teklif yerine getirilir,
- Diğer senaryoda Predicate gerçekleşmez.

##### Predicate temelli Gas Karşılama

![12th image](/assets/images/5/12.png "12th image")

### Nedir bu Predicate'ler?

Predicate'ler durumsuzdur.

- Zincir üstünde depolanan veriye erişemezler.
- Akıllı kontratlardan veri okuyamazlar,
- Anlık zamanı ya da tarihi kontrol edemezler,
- Blok hashi ya da sayısını okuyamazlar.

Eğer bir Predicate "true" değerini döndürürse, sürekli "true" değeri döner.

##### Predicate'ler Nelere Erişebilir?

İşleme dahil olan her şeye erişebilirler.

- Predicate girdi parametreleri
- Girdi coinleri
- Çıktı coinleri
- İşlem Scriptleri

##### Predicate'ler Akıllı Kontratlardan Önce Devreye Alınır

Fuel işlem süreci şu şekildedir:

- Girdilerin var olup olmadığı kontrol edilir
- Girdi ve çıktıların birbirini denkleyip denklemediği kontrol edilir
- Normal imzalar kontrol edilir
- Predicate'ler devreye alınır
- Scriptler devreye alınır (Akıllı kontrat çağrıları)

##### Predicate'ler Intent midir?

Hayır, değildir. Ancak birkaç konuda benzerlik taşırlar.

![13th image](/assets/images/5/13.jpg "13th image")

Intent kullanan hesaplar yapmak için Predicate'leri kullanabilirsiniz.

##### Predicate'ler Durum Yenileme için Vazgeçilmez bir Anahtardır

Durum Yenileme: Zincir üstündeki durum bilgilerini minimal şekilde depolamak için kullanılan bir tekniktir aynı zamanda işlemlerin içerisinde tüm durum bilgisini de içerir.

![14th image](/assets/images/5/14.jpg "14th image")

Tüm durum yenileme şeması:
![15th image](/assets/images/5/15.jpg "15th image")

##### Predicate'ler ve UTXO'larla Tüm Durum Yenilemesi

- UTXO varlık kimlikleri içerisinde durum taahhütleri
- Predicate'lerin değiştirilebilir değerleri içerisinde durum taahhütleri

##### Uniswap V2 Predicate'i

![16th image](/assets/images/5/16.png "16th image")

### Tüm bu Yapı ile Neye Eriştik?

- Merkeziyetsiz uygulamaların hızlı ve ucuz olması için bir mimari
- Blockchainlerin merkeziyetsiz kalabilmesi için bir mimari

### Bu Yayından Önemli Kaynaklar:

- [Sunum](https://hackmd.io/@dmihal/predicates-v3)
