# Blockchain Ağlarında Merkeziyetsizlik,Sansürleme ve Slashing
<p>Merhaba ben Mustafa ERDOĞAN, Bu yazımda sizlere blok zincirlerinde sansürleme ve slashing kavramlarını ele alacağım. Bildiğimiz üzere geçtiğimiz yıl  Ethereum PoS algoritmasına geçti. Bu geçiş ile beraber bazı sorular ve endişeler ortaya çıktı. Bunlar;</p>
•	Ethereum merkeziyetsizlikten uzaklaşıyor mu?</br>
•	Ethereum PoS yapısında nasıl valitador olunur?  bloklar nasıl ekleniyor? Parayı veren düdüğü çalacak mı? Ee hani merkeziyetsizdi bu! …vb.</br></br>
<p>Bu sorular ve endişeler, Tornada Cash blok zinciri üzerinde sansür uygulanması ile birleşerek Blockchain camiasında bir kargaşaya neden oldu. Şimdi bu endişeler ve sorunlara yol açan konuyu geniş kapsamlı, konu başlıkların altında inceleyeceğiz.</p>

## İÇİNDEKİLER
#### 1. GİRİŞ</br>
#### 2. Merkeziyetsizlik tam olarak nedir?</br>
#### 3. PoW ve PoS Protokollerinde Bloklar nasıl eklenir?</br>
3.1 PoW Protokolünde Blok Ekleme</br>
3.2	PoS Protokolünde Blok Ekleme </br>
3.3 Ethereum PoS'da Validator Olma</br>
3.3.1 Evde Solo Staking</br>
3.3.2 Bir Hizmet Olarak Stake Etme </br>
3.3.3 Havuzlanmış Staking (Staking Pool) </br>
3.3.4 Merkezi Borsalar </br>
#### 4. Blockchain Teknolojilerinde Sansürleme
4.1 Uygulama Katmanlı Sansürleme</br>
4.2 Protocol Katmanlı Sansürleme</br>
4.2.1 PoW Algoritmasında Protocol Katmanlı Sansürleme</br>
4.2.2 PoS Algoritmasında Protocol Katmanlı Sansürleme</br>
#### 4. Blockchain Teknolojilerinde Slashing Kavramı
#### 5. Full Node Kurmanın Avantajları

## 1. GİRİŞ
<p>Merhaba ben Mustafa ERDOĞAN, Bu yazımda sizlere blok zincirlerinde sansürleme ve slashing kavramlarını ele alacağım. Bildiğimiz üzere geçtiğimiz yıl  Ethereum PoS algoritmasına geçti. Bu geçiş ile beraber bazı sorular ve endişeler ortaya çıktı. Bunlar;</p>
•	Ethereum merkeziyetsizlikten uzaklaşıyor mu?</br>
•	Ethereum PoS yapısında nasıl valitador olunur?  bloklar nasıl ekleniyor? Parayı veren düdüğü çalacak mı? Ee hani merkeziyetsizdi bu! …vb.</br></br>
<p>Bu sorular ve endişeler, Tornada Cash blok zinciri üzerinde sansür uygulanması ile birleşerek Blockchain camiasında bir kargaşaya neden oldu. Şimdi bu endişeler ve sorunlara yol açan konuyu geniş kapsamlı, konu başlıkların altında inceleyeceğiz.</p>

### 2. TEMEL KAVRAMLAR
