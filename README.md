# Blockchain Ağlarında Merkeziyetsizlik,Sansürleme ve Slashing


## İÇİNDEKİLER
#### 1. GİRİŞ</br>
#### 2. Merkeziyetsizlik tam olarak nedir?
#### 3. PoW ve PoS Protokollerinde Bloklar nasıl eklenir?
<a>&nbsp;&nbsp;&nbsp;&nbsp;3.1 PoW Protokolünde Blok Ekleme</a></br>
<a>&nbsp;&nbsp;&nbsp;&nbsp;;3.2	PoS Protokolünde Blok Ekleme</a></br>
<a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3.2.1 Ethereum PoS'da Validator Olma</a></br>

#### 4. Blockchain Teknolojilerinde Sansürleme
<a>&nbsp;&nbsp;&nbsp;&nbsp;4.1 Uygulama Katmanlı Sansürleme</a></br>
<a>&nbsp;&nbsp;&nbsp;&nbsp;4.2 Protocol Katmanlı Sansürleme</a></br>
<a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4.2.1 PoW Algoritmasında Protocol Katmanlı Sansürleme</a></br>
<a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4.2.2 PoS Algoritmasında Protocol Katmanlı Sansürleme</a></br>
#### 5. Blockchain Teknolojilerinde Slashing Kavramı
#### 6. Full Node Kurmanın Avantajları

## 1. GİRİŞ
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Merhaba ben Mustafa ERDOĞAN, Bu yazımda sizlere blok zincirlerinde sansürleme ve slashing kavramlarını ele alacağım. Bildiğimiz üzere geçtiğimiz yıl  Ethereum PoS algoritmasına geçti. Bu geçiş ile beraber bazı sorular ve endişeler ortaya çıktı. Bunlar;</p>
•	Ethereum merkeziyetsizlikten uzaklaşıyor mu?</br>
•	Ethereum PoS yapısında nasıl valitador olunur?  bloklar nasıl ekleniyor? Parayı veren düdüğü çalacak mı? Ee hani merkeziyetsizdi bu! …vb.</br></br>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Bu sorular ve endişeler, Tornada Cash blok zinciri üzerinde sansür uygulanması ile birleşerek Blockchain camiasında bir kargaşaya neden oldu. Şimdi bu endişeler ve sorunlara yol açan konuyu geniş kapsamlı, konu başlıkların altında inceleyeceğiz.</p>

### 2. Merkeziyetsizlik tam olarak nedir?
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Blockchain teknolojisinin özelliklerinin yapı taşlarından biri olan merkeziyetsizlik kavramın felsefesi, günümüzde çoğunluk tarafından yanlış bilinmektedir. Blok zincirlerin kendi kendini yönetmesi veya dışarıdan bir müdahale edilmemesi merkeziyetsizlik olarak tanımlanır. Örneğin Ethereum blok zincirinin kurucu ortaklarından olan Vitalik Buterin ve Ethereum topluluğunun var olması, getirilen güncellemelerin bu kişiler tarafından çoğunlukla gelmesi kimilerine göre bu ağın merkeziyetsizlik kavramından uzaklaştığını belirtirler. Bu ifade tam olarak doğru değildir. Bir başka neden ise Ethereum PoS algoritmasını geçtikten sonra da bu ifade tekrar gün yüzüne çıkmıştır. </p>

<p><b>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;“Bir ağın merkeziyetsiz olması, o ağda söz sahibi olmanın kolaylığı ile ilgilidir.”</b> Bu cümle tam olarak ne anlatmak istiyor?</p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Bitcoin ve Ethereum blok zincirleri üzerinden gitmek gerekir ise, her iki zincirde PoW ve PoS algoritmalarının olması farketmeksizin geçmişe dönük tüm zincir bilgileri Node ’lar tarafından tutulmaktadır. Full Node ‘lar tüm blok zincirinin bir kopyasını barındıran ve senkronize eden bir bilgisayardır. Madenciler ağda gerçekleşen işlemleri onaylamak için işlem bilgilerin doğruluğunu Node ’lara sorarak ulaşır. Bitcoin blok zincirinin boyutu ortalama 400 GB ‘dan fazladır. Ethereum blok zincirinin ise ortalama 700 GB ‘den fazladır. (Bu rakamlar değişiklik gösterebilir. Aralarındaki ortalama fark şimdilik bu boyutlardadır). Şimdi benin kuracağım Node ‘a göre bilgisayarımın özellikleri buna göre değişecektir. Bu durum ise ağa söz sahibi olmamın kolaylığını etkilemektedir. Bu örnekte Bitcoin zincirinde söz sahibi olmam, Ethereum zincirinde söz sahibi olmamdan daha kolay. Her iki ağ da merkeziyetsizdir ancak Bitcoin, Ethereum ağına göre daha merkeziyetsiz diyebiliriz. (Bitcoin topluluğunun zincir üzerindeki güncellemelere daha katı olması, daha toz kondurmaması gibi topluluk davranışları da bu durumları etkilemektedir.)</p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Kısacası bir ağda Node kurarak o ağda söz sahibi olmak ne kadar kolay ise merkeziyetsizliği o kadar güçlendirmektedir. Sadece kurulan Node ‘ların sayısı ile doğrudan orantılı değildir. Ağda söz sahibi olan bu Node ’ların dağıtık olması da, topluluk davranışları gibi durumlarda önemlidir.</p>
<p align="center"><b>“Merkeziyetsiz bir gelecek istiyorsanız “Full Node” kurun.” - @TobbyKitty</b></p>

### 3. PoW ve PoS Protokollerinde Bloklar nasıl eklenir?
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;PoW ‘da blok ekleyenlere madenci (miner), PoS ‘da ise doğrulayıcı (validator) denmektedir.</p>

### 3.1 PoW Protokolünde Blok Ekleme
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Bir madenci olmak için yeterli özelliklerde bilgisayar donanımlarına sahip olup gerekli madenci yazılımını indirdiğinizde, bilgisayarınızı açık bıraktığınız sürece ağda işlemleri doğrulayıp Blok ekleme özelliklerine sahip olabiliyorsunuz. Çevrimdışı olduğunuzda ya da elektriğiniz kesildiğinizde herhangi bir ceza işlemi uygulanmamaktadır. </p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Kendiniz solo madenci olarak katıldığınızda blok ödülünün tamamını siz alırsınız. Blok ekleme olasılığını düşünerek boşa elektrik yakma riskini azaltmak için madenci havuzlarına katılarak yaptığınız iş kadar ödülünüzü alabilirsiniz. Bu madenci havuzları aslında bir madenci gibi ağda hareket eder. “Mining Pool” yazılımları ile işlemleri ve blok ödülünü havuza katılan madenciler ile paylaşır. </p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Madenci ağda gerçekleşen işlemleri (transactions) Node ‘lara sorarak doğruluğunu onaylar ve kendi oluşturduğu sanal bloğa yerleştirir. Bu işlemleri tamamladıktan sonra madenci, oluşturulacak yeni bloğun nonce değerini Brute Force yöntemi ile çözmeye çalışır. Madencinin işlem gücü (HashRate) ne kadar yüksek ise nonce değerini bulup bloğu ekleme şansı daha fazladır. Bu nonce değeri, madencinin blok ödülünü alması için rastgele üretilen, başında o anki zorluk seviyesine göre belirli basamak sayıda 0 ile başlayan bir sayı dizisidir. Madenci diğer madenciler ile rekabete girerek doğru sayıyı bulmaya çalışır ve bulduğu zaman oluşturduğu sanal bloğu artık gerçek zincirin en sonuna ekler. Eklediği bu bloktaki ilk transfer ile ödülü kendine gönderir. Bloktaki bu ilk transfere de Coinbase denir. Bu transferi madenci kendisi gerçekleştirmemektedir. Bu Coinbase transfer bloğu eklediğinde, blok içerisinde sistem tarafından tanımlanmış olarak bulunmaktadır.</p>

<p><b>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Not:</b> Zorluk seviyesi (difficulty), örneğin Bitcoin ağında her blok 10 dk ‘da bir eklenecek şeklinde tanımlanmıştır. Bitcoin eklenecek bu zincir süresini 10 dk süresinde tutmak için nonce değerini bu zorluk seviyesine göre değiştirmektedir.</p>

### 3.2 PoS Protokolünde Blok Ekleme
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Bir validator olmak için PoW da ki gibi yüksek donanımlı bilgisayarınızın olmasına gerek yoktur. Hatta bazı durumlarda bilgisayarınızın olmasına bile gerek yoktur. Sadece 32 ETH ‘nizin olması ve bu ETH ’leri kilitlemeniz validator olmak için yeterlidir. (Staking)</p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Validator olmak için ne eksik ne fazla tam 32 ETH ‘nizin olması gerekmektedir. Bu nedenle tüm validatorler eşittir. Ancak PoW da olduğu gibi PoS ‘da da staking havuzları mevcuttur. 32 ETH den az miktara sahip olan kişiler bu havuzlara girerek, katılan kişilerden 32 ETH olacak şekilde gruplar oluşturularak validator kurarlar. Gelen ödülleri katılım sağlayan kişilerin miktarına göre paylaştırırlar.</p>

### 3.2.1 Ethereum PoS'da Validator Olma
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ethereum PoS ‘da validator olmak 4 yol vardır;</p>



#### 1) Solo Staking
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ethereum 'da tek başına staking, staking için altın standarttır. Tam katılım ödülleri sağlar, ağın merkeziyetsizliğini geliştirir ve hiçbir zaman fonlarınız için başka birine güvenmenizi gerektirmez. Solo staking yapmayı düşünenler en az 32 ETH 'ye ve 7 gün 24 saat internete bağlı özel bir bilgisayara sahip olmalıdır.</p>

#### 2) Bir Hizmet Olarak Stake Etme
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Donanımla uğraşmak istemiyorsanız veya kendinizi rahat hissetmiyorsanız ancak yine de 32 ETH 'nizi stake etmek istiyorsanız, hizmet olarak staking seçenekleri, yerel blok ödülleri kazanırken zor kısmı devretmenize olanak tanır.</p>

#### 3) Havuzlanmış Staking (Staking Pool)
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;32 ETH den daha az miktara sahip olan ve staking geliri elde etmek isteyen kullanıcılar için oluşturulmuş ödül havuzlarıdır. Bir havuzla staking yapmak, bir token takası kadar kolaydır.</p>

#### 4) Merkezi Borsalar
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ETH'yi kendi cüzdanınızda tutmak konusunda henüz rahat değilseniz, birçok merkezi borsa staking hizmeti sunar. Minimum gözetim veya çaba ile ETH varlıklarınızdan bir miktar getiri elde etmenize izin vermek için bir geri dönüş olabilirler.</p>

<b>Peki PoS da bir blok nasıl eklenir?</b>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ağa gönderilen doğrulanmamış işlemler PoW da da olduğu gibi Mempool (Bellek havuzu) depolanır. Validator bu havuzdaki işlemleri Node ‘lara sorarak bu işlemin doğruluğunu ispat eder. Node ‘lar bu işlemi dedikodu ağı (Gossip) ile diğer Node ‘lara iletir. Diğer Node ‘lar işlemi duyduklarında, işlemi yerel bellek havuzlarına da eklerler. Bu şekilde yine bloklarlar doldurulur fakat PoS protokolün her ağın kendisine ait algoritmasını kullanarak yeni bloğu ekleyecek validatörü	 rastgele seçer. PoS algoritması, validator ne kadar uzun süredir yeni bir bloğun onaylanmasında görev almadığını kontrol eder. Bu süre ne kadar uzunsa bir sonraki bloğun onaylayıcısı olma şansı o kadar fazladır. Yeni bloğun ekleme şansını artırmak için birden fazla validator kurarak artırabilirsiniz. Birnevi PoS algoritması tüm validatörleri sıraya koyarak blok eklemesini sağlamasını sağlamaya çalışır.</p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Validatorler PoW ‘da olduğu gibi blok ödüllerini almazlar. Doğrulayıcılar işlem ücretlerini ödül olarak alırlar. Aşağıdaki grafik, Ethereum Merge sonraki PoS a geçişinin ardından blok ödüllerinin grafiğinin değişimini göstermektedir.</p>
<p align="center"> 
<img src="https://user-images.githubusercontent.com/82549640/218871428-2c6181f7-5fd2-4cdc-ab86-c44bdee0d501.png"></br> Şekil 5 - Blok Zinciri
</p>

