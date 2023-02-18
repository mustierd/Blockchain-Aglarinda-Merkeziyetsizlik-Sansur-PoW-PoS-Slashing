# Blockchain Ağlarında Merkeziyetsizlik,Sansürleme ve Slashing
<p align="center"> 
<img src="https://user-images.githubusercontent.com/82549640/219879103-fc15a311-b43c-4252-99e1-f5157ef388a3.png">
</p>


## İÇİNDEKİLER
#### 1. GİRİŞ
#### 2. Merkeziyetsizlik tam olarak nedir?
#### 3. PoW ve PoS Protokollerinde Bloklar nasıl eklenir?
<a>&nbsp;&nbsp;&nbsp;&nbsp;3.1 PoW Protokolünde Blok Ekleme</a></br>
<a>&nbsp;&nbsp;&nbsp;&nbsp;;3.2	PoS Protokolünde Blok Ekleme</a></br>
<a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3.2.1 Ethereum PoS'da Validator Olma</a></br>

#### 4. Blockchain Teknolojilerinde Sansürleme
<a>&nbsp;&nbsp;&nbsp;&nbsp;4.1 Uygulama Katmanlı Sansürleme</a></br>
<a>&nbsp;&nbsp;&nbsp;&nbsp;4.2 Protokol Katmanlı Sansürleme</a></br>
<a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4.2.1 PoW Algoritmasında Protocol Katmanlı Sansürleme</a></br>
<a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;4.2.2 PoS Algoritmasında Protocol Katmanlı Sansürleme</a></br>
#### 5. Blockchain Teknolojilerinde Slashing Kavramı
#### 6. Full Node Kurmanın Avantajları

## 1. GİRİŞ
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Merhaba ben Mustafa ERDOĞAN, Bu yazımda sizlere blok zincirlerinde sansürleme ve slashing kavramlarını ele alacağım. Bildiğimiz üzere geçtiğimiz yıl  Ethereum PoS algoritmasına geçti. Bu geçiş ile beraber bazı sorular ve endişeler ortaya çıktı. Bunlar;</p>
•	Ethereum merkeziyetsizlikten uzaklaşıyor mu?</br>
•	Ethereum PoS yapısında nasıl valitador olunur?  bloklar nasıl ekleniyor? Parayı veren düdüğü çalacak mı? Ee hani merkeziyetsizdi bu! …vb.</br></br>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Bu sorular ve endişeler, Tornada Cash blok zinciri üzerinde sansür uygulanması ile birleşerek Blockchain camiasında bir kargaşaya neden oldu. Şimdi bu endişeler ve sorunlara yol açan konuyu geniş kapsamlı, konu başlıkların altında inceleyeceğiz.</p>

## 2. Merkeziyetsizlik tam olarak nedir?
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Blockchain teknolojisinin özelliklerinin yapı taşlarından biri olan merkeziyetsizlik kavramın felsefesi, günümüzde çoğunluk tarafından yanlış bilinmektedir. Blok zincirlerin kendi kendini yönetmesi veya dışarıdan bir müdahale edilmemesi merkeziyetsizlik olarak tanımlanır. Örneğin Ethereum blok zincirinin kurucu ortaklarından olan Vitalik Buterin ve Ethereum topluluğunun var olması, getirilen güncellemelerin bu kişiler tarafından çoğunlukla gelmesi kimilerine göre bu ağın merkeziyetsizlik kavramından uzaklaştığını belirtirler. Bu ifade tam olarak doğru değildir. Bir başka neden ise Ethereum PoS algoritmasını geçtikten sonra da bu ifade tekrar gün yüzüne çıkmıştır. </p>

<p><b>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;“Bir ağın merkeziyetsiz olması, o ağda söz sahibi olmanın kolaylığı ile ilgilidir.”</b> Bu cümle tam olarak ne anlatmak istiyor?</p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Bitcoin ve Ethereum blok zincirleri üzerinden gitmek gerekir ise, her iki zincirde PoW ve PoS algoritmalarının olması farketmeksizin geçmişe dönük tüm zincir bilgileri Node ’lar tarafından tutulmaktadır. Full Node ‘lar tüm blok zincirinin bir kopyasını barındıran ve senkronize eden bir bilgisayardır. Madenciler ağda gerçekleşen işlemleri onaylamak için işlem bilgilerin doğruluğunu Node ’lara sorarak ulaşır. Bitcoin blok zincirinin boyutu ortalama 400 GB ‘dan fazladır. Ethereum blok zincirinin ise ortalama 700 GB ‘den fazladır. (Bu rakamlar değişiklik gösterebilir. Aralarındaki ortalama fark şimdilik bu boyutlardadır). Şimdi benin kuracağım Node ‘a göre bilgisayarımın özellikleri buna göre değişecektir. Bu durum ise ağa söz sahibi olmamın kolaylığını etkilemektedir. Bu örnekte Bitcoin zincirinde söz sahibi olmam, Ethereum zincirinde söz sahibi olmamdan daha kolay. Her iki ağ da merkeziyetsizdir ancak Bitcoin, Ethereum ağına göre daha merkeziyetsiz diyebiliriz. (Bitcoin topluluğunun zincir üzerindeki güncellemelere daha katı olması, daha toz kondurmaması gibi topluluk davranışları da bu durumları etkilemektedir.)</p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Kısacası bir ağda Node kurarak o ağda söz sahibi olmak ne kadar kolay ise merkeziyetsizliği o kadar güçlendirmektedir. Sadece kurulan Node ‘ların sayısı ile doğrudan orantılı değildir. Ağda söz sahibi olan bu Node ’ların dağıtık olması da, topluluk davranışları gibi durumlarda önemlidir.</p>
<p align="center"><b>“Merkeziyetsiz bir gelecek istiyorsanız “Full Node” kurun.” - @TobbyKitty</b></p>

## 3. PoW ve PoS Protokollerinde Bloklar nasıl eklenir?
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



#### &nbsp;&nbsp;&nbsp;&nbsp; 1) Solo Staking
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ethereum 'da tek başına staking, staking için altın standarttır. Tam katılım ödülleri sağlar, ağın merkeziyetsizliğini geliştirir ve hiçbir zaman fonlarınız için başka birine güvenmenizi gerektirmez. Solo staking yapmayı düşünenler en az 32 ETH 'ye ve 7 gün 24 saat internete bağlı özel bir bilgisayara sahip olmalıdır.</p>

#### &nbsp;&nbsp;&nbsp;&nbsp; 2) Bir Hizmet Olarak Stake Etme
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Donanımla uğraşmak istemiyorsanız veya kendinizi rahat hissetmiyorsanız ancak yine de 32 ETH 'nizi stake etmek istiyorsanız, hizmet olarak staking seçenekleri, yerel blok ödülleri kazanırken zor kısmı devretmenize olanak tanır.</p>

#### &nbsp;&nbsp;&nbsp;&nbsp; 3) Havuzlanmış Staking (Staking Pool)
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;32 ETH den daha az miktara sahip olan ve staking geliri elde etmek isteyen kullanıcılar için oluşturulmuş ödül havuzlarıdır. Bir havuzla staking yapmak, bir token takası kadar kolaydır.</p>

#### &nbsp;&nbsp;&nbsp;&nbsp; 4) Merkezi Borsalar
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ETH'yi kendi cüzdanınızda tutmak konusunda henüz rahat değilseniz, birçok merkezi borsa staking hizmeti sunar. Minimum gözetim veya çaba ile ETH varlıklarınızdan bir miktar getiri elde etmenize izin vermek için bir geri dönüş olabilirler.</p>

<b>Peki PoS da bir blok nasıl eklenir?</b>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ağa gönderilen doğrulanmamış işlemler PoW da da olduğu gibi Mempool (Bellek havuzu) depolanır. Validator bu havuzdaki işlemleri Node ‘lara sorarak bu işlemin doğruluğunu ispat eder. Node ‘lar bu işlemi dedikodu ağı (Gossip) ile diğer Node ‘lara iletir. Diğer Node ‘lar işlemi duyduklarında, işlemi yerel bellek havuzlarına da eklerler. Bu şekilde yine bloklarlar doldurulur fakat PoS protokolün her ağın kendisine ait algoritmasını kullanarak yeni bloğu ekleyecek validatörü	 rastgele seçer. PoS algoritması, validator ne kadar uzun süredir yeni bir bloğun onaylanmasında görev almadığını kontrol eder. Bu süre ne kadar uzunsa bir sonraki bloğun onaylayıcısı olma şansı o kadar fazladır. Yeni bloğun ekleme şansını artırmak için birden fazla validator kurarak artırabilirsiniz. Birnevi PoS algoritması tüm validatörleri sıraya koyarak blok eklemesini sağlamasını sağlamaya çalışır.</p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Validatorler PoW ‘da olduğu gibi blok ödüllerini almazlar. Doğrulayıcılar işlem ücretlerini ödül olarak alırlar. Aşağıdaki grafik, Ethereum Merge sonraki PoS a geçişinin ardından blok ödüllerinin grafiğinin değişimini göstermektedir.</p>
<p align="center"> 
<img src="https://user-images.githubusercontent.com/82549640/218871428-2c6181f7-5fd2-4cdc-ab86-c44bdee0d501.png"></br> Şekil 1 - Günlük ethereum blok ödülü
</p>

## 4. Blockchain Teknolojilerinde Sansürleme

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ethereum madenciliğinde yüzde 30’a yakın pay sahibi olan en büyük Ethereum havuzu Ethermine, Tornada Cash işlemlerini engellemeye başladı. Bunun sebebi ABD Tornada Cash zincirinde kara para aklandığını savunarak bu ağa yaptırım uygulamaya karar verdi. Bu yaptırım sonucu Ethermine havuzundaki madenciler, Tornado Cash ’e gönderilen işlemleri bloklara yazmak yerine işlemleri reddetmeye başladılar.</p>

<p align="center"> 
<img src="https://user-images.githubusercontent.com/82549640/218877789-9cb11ac5-d67a-4ce1-a425-874c6dd34c1e.png"></br> Şekil 3 - Ethermine tarafından Tornada Cash 'e  gönderilen işlemler 
</p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Bir diğer sansürleme örnek yine aynı Tornado Cash vakası üzerinden en popüler merkeziyetsiz borsalardan biri olan UniSwap borsası tarafından gerçekleşti. UniSwap geliştiricileri, UniSwap web sitesi üzerinden Tornada Cash ile işlem geçmişi olan cüzdanları engellemeye başladı. Tornada Cash üzerinde gerçekleşen bu yaptırımlar sonucu yeni bir merkeziyetsizlik tartışmasına yol açtı.</p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Peki Blockchain teknolojilerinde sansürleme mümkün mü? Mümkün ise ne derece Merkeziyetsizliği etkiliyor?</p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Blockchain ağlarında 2 türlü sansürleme çeşiti vardır. Bunlar uygulama (App) ve Protocol katmanlı sansürleme olmak üzere 2 ye ayrılır. Dolayısı ile sansürleme ihtimali her zaman vardır. PoW ve PoS teknolojilerinde sansürleme durumuna karşılık alınan önlemler farklı çalışmaktadır. Bunları ayrı ayrı inceleyelim.</p>

#### 4.1 Uygulama Katmanlı Sansürleme

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Bunun en güzel örneği yukarıda bahsettiğim UniSwap ‘ın gerçekleştirdiği sansürlemedir. UniSwap geliştiricileri Tornado Cash ile etkileşime geçen hesapları tespit ederek kırmızı listeye aldı. Bu hesapları daha sonra UniSwap web sitesi üzerinden etkileşime geçmesini engellediler. Bu durum uygulama katmanlı bir sansürlemedir ve tamamen endişe edilecek, korkulacak bir durum değildir. Bu yöntem ile tam olarak Tornado Cash blok zinciri ile iletişimini engelleyemezler. Sadece Node ‘lara gönderilen isteklerin iletişimini engellediler. Peki bu nasıl oldu?</p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;İlk olarak bir blok zincir ile nasıl iletişime geçiyoruz bundan bahsedeyim. Bildiğiniz üzere metamask, kullanıcıların private key anahtarlarını güvenli bir şekilde yöneten bir araçtır. Metamask ‘ın içerisinde varsayılan olarak infura tarafından yönetilen Node ’ları ile gelmektedir. Uygulama geliştiricileri veya kullanıcılar bir blok zinciri ile iletişime geçmek için ethers.js, web3.js gibi kütüphaneler ile birlikte metamask cüzdanını kullanarak Node ’ların anlayacağı biçimde isteklerini imzalayarak gönderir ve  blok zincir ile iletişime geçerler.</p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;UniSwap tam olarak bu blok zincir ile iletişime geçecek Node ‘lara web sitesi üzerinden kırmızı listeye alınan hesapların iletişimine geçmesini engelledi. Blok zincir ile alakası olmayan ve risk teşkil etmeyen sansürlemedir. Bu durumun üstesinden gelmek için uygulama katmanlı sansürleme uygulamayan diğer platformlar üzerinden ve en sağlıklı ve karlı yöntem olan Full Node kurarak kendi Node ’larınız üzerinden Tornado Cash ‘e işlemlerinizi gönderebilirsiniz. Full Node kurmanın avantajlarını yazımın sonunda bahsedeceğim.</p>

#### 4.2 Protokol Katmanlı Sansürleme

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Bu sansürleme en korkulan ve merkeziyetsizliği bitirebilecek yöntemdir fakat o kadar kolay değildir. Hali hazırda PoW ve PoS gerçekleşecek protocol seviyesinde sansürlemeler için geliştirmiş engelleme yöntemleri bulunmaktadır. Her iki algoritma için sansürleme nasıl gerçekleşiyor ve alınan önlemler nelerdir bunları inceleyelim.</p>

#### 4.2.1 PoW Algoritmasında Protokol Katmanlı Sansürleme

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Bir madenci veya validator en basit açıklama ile  işlemlerinin doğruluğunu Node ‘lara sorar ve yeni bir blok ekleyerek ödülünü alır. Madenciler ağda gerçekleşen işlemleri kendi isteğine göre reddedebilir. Bu tamamen madencinin isteğine bağlıdır. Tornada Cash sansürü ile devam eder isek, Ethermine madenci havuzu madencilerin %30 oranına sahiptir. Ethermine şirketi uyguladığı bu sansür ile ağda %30 ‘luk oranda Tornada Cash ‘e gönderilen işlemler reddedilecektir. Bu korkulan bir durum değildir. Çünkü işlemleriniz tahmini 4-5 blok sonrasında geri kalan ve sansür uygulamayan %70 oranına sahip madencilere düşerek işleminiz onaylanacaktır. Sansür uygulayan madenciler için bir ceza işlemi uygulanmamaktadır. PoW da slashleme gibi bir ceza durumu yoktur. Peki PoW da korkulacak durum ne zaman gerçekleşir?</p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Eğer kötü niyetli, sansür uygulayan madencilerin oranı %51 ‘i geçer ise Tornada Cash ‘e gidecek işlemler tamamen engellenecek ve Tornada Cash ‘e iletişim tamamen kesilecektir. Bu durum gerçekleştiği zaman zaten ağın hakimiyeti çoğunlukla (%51) sansür uygulayan madencilerin elinde olduğu için merkeziyetsizlik bitmiş ve ağın hakimiyeti bu sansür uygulayan madenciler tarafından sağlanacaktır. Bunun olması günümüz teknolojisinde çok zordur. Biz sadece burada en ufak ihtimalleri de olsa ele alıyoruz.</p>

#### 4.2.2 PoS Algoritmasında Protokol Katmanlı Sansürleme

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ethereum PoS algoritmasına geçtikten sonra merkeziyetsizlik hakkında endişeler ortaya çıktı. PoS, merkeziyetsizliği etkileyen bir faktör değildir. Yine merkeziyetsizlik konu başlığında değindiğimiz gibi bir ağın merkeziyetsizliğini etkileyen bilinç/faktör dağıtık bir yapıda Node kurmaktan geçer. Dolayısıyla bir sistemin sansürlenememesi için blok ekleyen madencilerin(validatörlerin) dağıtık olması gerekir. Tabi PoS ‘a geçildikten sonra merkezi borsalara stake edilerek kurulan validator bizi endişeye sokmaktadır.</p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Sitemde validatörlerin merkezi borsalara ETH ‘lerini emanet ederek doğrulayıcı olması bizi endişe etmektedir. Örneğin merkezi bir borsa olan Binance ‘ın validator havuzlarına katılanların oranı, toplam madencilere oranı %10 diyelim. Tornada Ethermine şirketinin Tornada Cash ‘ e uyguladığı sansür gibi Binance havuzunda olan validatörlerde sansür uygulamaya karar verdiğini düşünelim. Validatorler kendi isteklerine göre işlemleri doğrulamaya bildiklerini konuşmuştuk. Yine bu %10 luk dilime düşen işlemler reddedilir fakat ortalama 4-5 bilek sonra %90 ihtimalle diğer validatorler sonucu işlemler doğrulanarak bloğa eklenir. Halen korkulacak bir durum yok. Peki ne zaman korkmalıyız?</p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ethereum ağı üzerinde validatorler tarafından gerçekleşecek sansür oranı 1/3 ‘ün altında ise endişe edilecek bir durum yoktur. Ethereum topluluğunda %30’oranının altına sahip sansür uygulamaları göz ardı edilebileceğini söylemiştir. %30 oranının altında sansürleme uygulayan validatorler işlemleri “Biz görmedik” deme haklarına sahiptir. Dolayısıyla bu sansür uygulayan validatörlere bir cezai işlemi uygulanmamaktadır. Ancak bu oran %30 üzerine çıkarsa artık kötü niyetli veya sansür uygulayan bu validatorler ağ üzerindeki yavaştan işlemlerin değişikliğine yol açmaktadır ve bu durumda sansür uygulayan validatörlere slashing uygulanarak cezalandırılır. Slashing konusunu bir sonraki başlıkta açıklayacağım.</p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Bizi korkutan durumun ne olduğuna tekrar döner isek, insanların merkezi borsa veya havuzlara teslim ettiğin ETH ‘ler ile doğrulayıcı hakkına sahip olması. Daha sonra bu havuzların sansürleme uygulayabilecekleri durumunu da göz önüne getirirsek merkeziyetsizliği zedeleyecektir. Bizlerin olabildiğince merkeziyetsiz dağıtık validatorler/Node ‘lar kurarak merkeziyetsizliği güçlendirme bilincine sahip olmalıyız. Çünkü olası bir sansür durumunda ağın hakimiyeti sansür uygulayan kişiler tarafından sağlanırsa  bir Fork ‘a gidilir fakat bu Fork ile geçilen yeni zinciri benimseyecekler mi? Bu hem piyasayı kötü etkileyecektir hem de bu durum bizi korkutmaktadır. Fakat bu durum o kadar kolay değildir ve sansüre karşı alınan önlemler vardır. Bunların en önemlisi Slashing kavramıdır.</p>

<p align="center"> 
<img src="https://user-images.githubusercontent.com/82549640/218874581-76394ab2-e016-464a-9384-8b37d8f0e648.png"></br> Şekil 2 - Ethereum Pos Validator Havuzları
</p>

## 5. Blockchain Teknolojilerinde Slashing Kavramı

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Blockchain ağlarında PoW algoritmasını kullanan zincirlerde slashing kavramı yoktur. Bu kavram PoS algoritmasını kullanan zincirlerde geçerlidir. Slashing, ağda kötü niyetli olarak tabir ettiğimiz istenmeyen işlem hareketlerinde bulunan validatörleri cezalandırarak, ellerindeki ETH ’lerin gerekirse tamamını elinden alarak validatorlükten saf dışı bırakarak cezalandırma olarak açıklayabiliriz. Peki bu işlemi hangi durumlarda ve nasıl yaparız?</p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Hali hazırda PoS algoritmasında kötü blok basan, elektriği kesilen validatörlere hali hazırda ceza uygulanmaktadır. Bir validator, ağ tarafında bu istenmeyen davranışları gerçekleştirir ise 32 ETH kitleyerek sahip olduğu doğrulayıcı hakkında, ceza çeşitine göre elinden belli bir miktar ETH alınır. Ancak slashleme sonucu kötü davranışlara devam eden validatörlerin elinden tüm ETH ‘leri alınarak doğrulayıcı hakkını kaybeder.</p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Kötü niyetli validatörleri slashleye bilmemiz için 32 ETH ‘e sahip olmamız gerekmez. Slashleme Node ‘lar tarafından gerçekleşir. Bildiğimiz üzere Node ‘ olmamız için gerekli yazılımı indirerek olabiliyorduk. Node ‘lar bu yazılımın içerisine script kodlar ekleyerek bu slashleme mekanizmasını çalıştırmaktadır. Örneğin “Tornada Cash ‘e gelen işlemleri hangi validatorler engelliyor ise hepsini slashle” anlamına gelen gerekli script’i yazarak bu mekanizmayı çalıştırabiliyoruz. Bu kararı bir veya bir kişi almamaktadır. Bu kararı topluluğa ait olan yani Node ‘lar ortak kararı alarak gerçekleştirir.</p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Hangi validatorler nerelere sansür uygulanıyor bu gibi bilgiler bazı Explorer ve arşiv Node ‘lar tarafından herkes görebilir. Fakat sansürün tespiti kolay değildir. Elinizde kesin ipuçları veya bilgiler dahilinde tespit etmeniz kolaylaşacaktır.</p>

<p align="center"> 
<img src="https://user-images.githubusercontent.com/82549640/218875655-e6e15d1d-a25d-480f-a77c-106564d1e021.png"></br> Şekil 3 - https://www.beaconcha.in/validator
</p>

## 6. Full Node Kurmanın Avantajları

1) Ağa ve kendine katkınız vardır.</br>
2) Tornada Cash ‘den bloklandığın zaman veya infura çöktüğü zaman kendi nodunuz üzerinden ağa işlemlerinizi gönderebilirsiniz.</br>
3) Ağda Gas ücretlerinin fazla olduğu zamanlarda kendiniz düşük Gas ücretleri ile işlemlerinizi gerçekleştirebilirsiniz.</br>
4) Ciddi anlamda gizlilik sağlar. Full Node kurarsanız IP ‘niz büyük ölçüde gizli kalır.</br>
