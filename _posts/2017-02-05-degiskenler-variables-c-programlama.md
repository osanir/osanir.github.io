
---

title: C Programlama Diline Giriş

published: true

---

İlk bölümde öğrendiğimiz bilgiler ile basit bir C programı yazabiliriz ve buna yorumlar ekleyebiliriz. Bu harika, ama kullanıcılar ile etkileşime geçmek daha güzel olmaz mı? Şanslıyız, C kullanıcıdan girdi (input) almamızı kabul ediyor. Bu bölümde C programlama ve değişkenler üzerinde duracağız.

  

## Değişkenler

  

Öncelikle girdi almadan önce bu girdileri saklayacak bir yerimiz olması gerekiyor. Programlamada, girdi ve veriler değişkenler halinde saklanır. Çeşitli değişken tipleri vardır. Derleyiciye bir değişken bildirdiğinizde, değişkenin adıyla birlikte veri tipini de eklemeniz gerekir. En temel değişken tipleri **int**, **char** ve **float** diyebiliriz. Bu tiplerin her biri farklı veri tiplerini depolar.

  

**Char** tipindeki bir değişken tek bir karakteri depolar, **int** tipindeki bir değişken tam sayıları tutabilir (yani ondalık kısımları tutmaz), **float** tipindeki bir değişken ise ondalık kısmları olan sayıları tutar. Bu değişken türlerinden her biri, bir değişken bildirirken kullandığınız bir anahtar kelimedir. Bazı değişkenler değerlerini tutabilmek için bilgisayarın belleğinde daha fazla yer kaplar.

  

Değişken tiplerinin diğerlerine de baktığımızda birbirine benzeyen birçok değişkeni göreceğiz. İlk olarak bu kadar benzer değişkenlerin olması saçma gelebilir, çünkü birçoğu birbirlerinin yerine kullanılabilecek değişkenler olacak. Peki neden benzer değişkenler var sorusunun cevabını ise şöyle verebiliriz: "Bu değişkenlerin herbiri bilgisayarın belleğinde farklı miktarlarda yer kaplar. Programımızı daha verimli hale getirmek için daha az yer kaplayan değişken tiplerini kullanmamız gerekecek." Bu değişkenlerin tamamının kullanıldığını unutmayın!

  

Bir değişkeni kullanmadan önce derleyiciye, kullanacağımız değişkenin tipinin ne olduğunu bildirmemiz gerekir. Bir değişkeni bildirmek için <değişken  tipi>  <değişken  adı>; söz dizimini kullanacağız. Hemen akıllara daha iyi oturması için bir örnek verelim:

  

`int benimDegiskenim;`

  

Satır sonundaki noktalı virgüle dikkat edin. Bir fonksiyon çağırmamamıza rağmen ifadenin sonunda yine de noktalı virgül kullandık. Bu kod, _benimDegiskenim_ adlı bir değişkeni oluşturdu. Artık _benimDegiskenim_ adlı değişkenimizi programımızda kullanmakta özgürüz.

  

Bir satırda **aynı tipte** birden fazla değişkeni de tanımlayabiliriz. Bunun için tanımlamak istediğimiz değişkenler arasına virgül koymamız gerekiyor. Tanımlanmamış bir değişken kullanılmaya çalışılırsa program hata verecek ve çalışmayacaktır.

  

Değişken tanımlamaya birkaç örnek verelim:

-  `int x;` /* x adında bir tam sayı değişken tanımladık. */

-  `int a, b, c, d;` /* a, b, c ve d adında dört adet tam sayı değişken tanımladık. */

-  `char harf;` /* harf adında bir char değişken tanımladık.*/

-  `float piSayisi;` /* piSayisi adında bir float değişken tanımladık. */

  

Aynı tipte birden fazla değişkene sahip olabilirsiniz ama aynı ada sahip birden fazla değişkeniniz olamaz. Tipleri farklı bile olsa aynı isimde iki değişken kullanmayın.

  

##### Son olarak; {.example}

  

Değişkenler ile ilgili son olarak şunu söyleyelim: Değişken tanımlamanızı değişkeni kullanmadan önce yapmalısınız. Programların yukarıdan aşağıya okunduğunu unutmayın. Yani tanımlamanız kod bloğunuzun üzerinde bulunmalı.

  

Bunu da biri doğru biri yanlış olan iki örnek ile gösterelim:

  

**Hatalı**

```c

#include <stdio.h>

int main()

{

/* yanlış! değişken tanımlaması kullanmadan önce tanımlanmalı. */

printf( "x, sonraki satırda tanımlanmış" );

int x;

  

return 0;

}

```

**Doğru**

```c

int main()

{

int x;

printf( "x, önceki satırda tanımlanmış" );

  

return 0;

}

```

## Girdi (Input) Okuma

  

C programlama dilinde giriş-çıkışlar için değişkenleri kullanmak başta can sıkıcı olabilir ama onunla hareket etmek mantıklı olacaktır. Kullanıcıdan bir girdi almak için scanf fonksiyonunu kullanacağız, bir çıktı istediğimizde de printf fonksiyonunu kullanacağız. Şimdi aşağıdaki kodu inceleyelim. Bu kodu kendi derleyicinizde de derleyip çalıştırabilirsiniz. Kodu canlı görmek iyi olacaktır.

  

```c

int main()

{

int bu_bir_sayi;

  

printf( "Bir sayi girin: " );

scanf( "%d", &bu_bir_sayi );

printf( "Girdiginiz sayi: %d", bu_bir_sayi );

getchar();

return 0;

}

```

  

## Tüm bunların anlamı ne?

  

**#include** ve **main fonksiyonu**nu daha önce incelemiştik. "main", fonksiyonu çalıştıracağımız bütün programlarda bulunmak zorunda, "#include" ise printf ve scanf fonksiyonlarına erişimi sağlar.

  

**<stdio.h>** içerisindeki "io" tahmin edebileceğiniz üzere input/output kelimelerinin baş harflerinden oluşuyor ve std ise sadece standart anlamına geliyor, "h" harfinin header kelimesinin ilk harfi olduğunu söylemiştik).

  

**int** kelimesi, **bu\_bir\_sayi** değişkeninin bir tam sayı olduğunu bildiriyor.

  

Şimdi işlerin ilginçleştiği yere gelelim, **scanf** fonksiyonumuz tırnak alarak çalışır ve aldığımız değerleri değişkenlere "&" işareti ile yerleştiririz. Tırnak işaretleri arasındakiler, scanf fonksiyonuna, programın alacağı girdinin tipini bildirir. Şuna dikkat edin, tırnak işaretleri arasında sadece "%d" işareti bulunuyor ve bu işaret, scanf fonksiyonuna, bir integer yani tam sayı okunacağını söylüyor. İkinci argümanımız ise değişkenimiz. Daha sonra neler olduğu hakkında daha fazla şey öğreneceğiz, ama şimdilik olayın özü, scanf'in değişkenin değerini değiştirmek için nerede depolandığını bilmesinin gerekli olmasıdır. Değişkenin başında "&" işaretini kullanarak değişkenin **konumunu/adresini** scanf'e bildirmiş oluyoruz. Scanf fonksiyonu ise bu konuma, kullanıcıdan alınan **girdinin işlenmesini** sağlar.

  

Özet olarak scanf fonksiyonu için şunu söyleyebiliriz: _Scanf fonksiyonu çağrıldığında, her bir scanf fonksiyonu tırnak işaretlerinin arasına bakarak, alınacak olan girdinin tipini öğrenir ve alınan değeri ("&" ile), hedeflenen değişkenin içine yerleştirir._ (Yazının bundan sonraki kısımlarda tırnak işaretlerinin arası yerine string kelimesini tercih edersem kafanız karışmasın. Birçok ingilizce kaynakta tırnak işaretlerinin arasını belirtmek için string kullanılıyor.)

  

Gelelim printf fonksiyonumuza. İkinci printf'e bakın. Scanf'te olduğu gibi "%d" içeriyor. İkiside tırnak işaretlerinin arasındayken değişkenlerin değerini gösterebilmek için aynı biçimde çalışıyorlar. Bu durumu incelediğimzde "%d", tırnakların kapanışından sonraki ilk bağımsız değişkeni gösterecektir. Normal şartlarda tırnak içindeki "Girdiginiz sayi: " kelimeleri doğrudan yazılacak ve ardından ("%d" gelen yere) **bu\_bir\_sayi** değişkeninin **değeri** gelecek.

  

## Adım adım ne yaptık?

  

1. #include ile header'ı programa dahil ettik ve main fonksiyonumuzu oluşturduk.

2. bu\_bir\_sayi adında, tam sayı (integer) tipinde bir değişken tanımladık.

3. scanf ile kullanıcından tam sayı tipinde bir integer aldık, bu değeri bu\_bir\_sayi adlı değişkenimizin içine ("&" işareti ile) yazdırdık.

4. Ekrana kullanıcının girdiği sayıyı yazdırmak istedik. Tırnak işaretleri arasına önce ekranda belirmesini istediğimiz yazıyı yazdık sonra değişkenimizin gelmesini istediğimiz yere "%d" yi yerleştirdik. Tırnağı kapattıktan sonra bir virgül çektik ve "%d" nin yerine gelmesini istediğimiz değişkenin adını yazdık.

5. getchar() kullanarak programın, kullanıcı enter'a basmadan önce kapanmasını engelledik.

6. return 0 ile programın başarılı bir şekilde sona erdiği bilgisini işletim sistemine bildirdik.

  

## Operatörler

  

Tabi ki değişkenler hangi türde olursa olsun, onları değiştiremediğimiz sürece o kadar da ilgi çekici değiller. Değişkenler üzerinde matematiksel işlemler yaparken veya değişkenleri birbirlerine atarken kullandığımız işaretlerin genel adına **operatörler** diyebiliriz sanırım. Bunlar bazı operatörler: " *, -, +, /, =, ==, >, < ".

  

Değerleri birbirleriyle çarpmak için **\***,

bölmek için **/**,

toplamak için **+**,

çıkarmak için **-** operatörünü kullanacağız. Bunun dışında iki değerin birbirlerine göre durumlarını (büyüklük-küçüklük gibi) sınamak için kullandığımız operatörler de var. "<" operatörü ile soldaki değerin sağdaki değerden **küçük** olması durumunu, benzer şekilde ">" operatörü ile soldaki değerin sağdaki değerden **büyük** olması durumunu kontrol edebiliyoruz. İki değerin birbirlerine eşit olmaları durumunu ise "==" operatörü ile sağlayacağız. C programlama dilinde "=" operatörü kullanıldığında, operatörün sağındaki değişkenin değeri, solundaki değerin değişkenine atanır. Bu durumların karıştırılması başınıza ufak sorunlar açabilir.

Birkaç örnek verelim:
(Yorum kullanımını ve noktalı virgüllere dikkat edin.)
```c
a = 4 * 6; /* a değişkenine 24 atandı. */
a = a + 5; /* a değişkenine, a değişkeninin orjinal değerine 5 eklenmiş hali atandı. */
a == 5     /* a değişkenine 5 ATANMADI! a değişkeninin değeri ile 5 in eşitliği kontrol ediliyor.*/
```
Eşitliğin gösterimi olan "\=\=", atamanın bir diğer yolu değildir. C programlama dilinin birçok alanında çok kullanışlıdır. Koşullu ifadeler (if-else) ve döngüler (for-while) gibi yapılarda sık sık kullanacağız. Eşitlik var ise program "1" değeri, yani olumlu değeri döndürdüğü için if-else ifadelerinde kontrol yapısı olarak kullanılabilir. Bir printf fonksiyonunda, değişkeni yazmak yerine 4==2*2 gibi doğru bir ifade yazarsanız, printf fonksiyonu ekrana 1 yazdıracaktır.

## Deneyerek test etmeyi unutmayın!

Şöyle bir ifade yazarak test edebilirsiniz.
```c
printf("%d",4==2*2); /* Ekrana 1 yazdıracaktır. */
printf("%d",4==3*3); /* Ekrana 0 yazdıracaktır. */
```
Tahmin edebileceğiniz üzere "<" ve ">" operatörlerimiz de büyüklük küçüklük kontrolü yapıyor. Buna da birkaç örnek verelim.
```c
a < 5 /* a 'nın 5 'ten küçük olma durumunu kontrol eder. */
a > 5 /* a 'nın 5 'ten büyük olma durumunu kontrol eder.*/
a == 5 /* a 'nın 5 'e eşit olma durumunu kontrol eder.*/
```
Bir ifadenin doğruluğu sonucu 1 değerini döndürdüğünü söylemiştik. Verdiğimiz eşitlik örneğine ek olarak büyüklük küçüklük durumları içinde ifade doğru ise 1 değeri dönecektir. Şöyle örnek verelim buna da:
```c
printf("%d",4 > 3); /* Ekrana 1 yazdıracaktır. */
printf("%d",4 < 3); /* Ekrana 0 yazdıracaktır. */
printf("%d",3 > 4); /* Ekrana 0 yazdıracaktır. */
printf("%d",3 < 4); /* Ekrana 1 yazdıracaktır. */
printf("%d",3 > 2*2); /* Ekrana 0 yazdıracaktır. */
printf("%d",3 < 2*2); /* Ekrana 1 yazdıracaktır. */
```
Bu bölümde değişkenlerden, nasıl kullanabileceğimizden, input output yani giriş çıkışlardan, scanf ve printf fonksiyonunu çalışma şeklinden bahsettik.
Sonraki bölümde koşullu ifadeler olan If-Else ifadelerine göz atacağız.
