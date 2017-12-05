Bu yazımızda data structure’ın temeli olan linked list’i hatırlatmayı amaçlıyorum. Bir önceki yazımız olan Arraylerd de arraylerin
bazı negatif yönleri olduğunu söylemiştik. Bu negatif yönler

    Boyutunun sabit olması
    Dolduğunda yeni bir array tanımlama ihtiyacı
    Blok halinde depolanma(Eğer yeni bir array tanımlamanız gerekiyorsa ve Raminiz yeterli değilse)

olarak sıralayabiliriz. Bilgisayarcılar blok verileri kolaylaştırdığı için array yapısını çok seviyor. Dolayısıyla da oldukça sık
kullanılıyor. Fakat arraylerin yukarıdaki nedenlerden ötürü isterlere cevap verememesi/işlemleri meşakkatli hale  getirmesi 
linked listlerin oluşmasına neden olmuştur. Linked list’e başlamadan önce structure yapısından bahsetmem gerekir. Struct yapısı 
bize kendi ADT(Abstract Data Type)ımızı oluşturmamızda yada hazır ADT yapılarını daha esnek şekilde kullanabilmemize imkan verir. 
Struct yapısı sayesinde kendi Nodelarımızı oluşturup linked listleri kullanacağız. Node demekten kastımı birazdan anlatacağım ama 
basit olarak arraylerdeki her hücreye birer node diyebiliriz aslında. Hatta bir node tanımlayıp ne olduğuna bakalım
struct node  //node yerine istediğimiz name'i yazabiliriz
{
struct node *next;
int data;
};

Nodeları tren  vagonlarına benzetebiliriz. Her bir node kendinden sonraki node’un adresini tutarak ileri-geri hareketi 
sağlayan bir yapıya sahip.
![link to pictures](https://github.com/ahmetmuhammetkocabiyik/Data-Structures/blob/master/Images/veri.jpg)
Veri  data nın *ileri ise next pointerına denk gelmek üzere şekli yukarıdaki gibi çizilebilir.
Linked list ileri-geri hareket kapasitesine göre 4’e ayrılır

    One Way Linked List
    One Way Circular Linked List
    Douuble Way Linked List
    Double Way Circular Linked List

1)One Way Linked List

Nodelarında sadece ileri veya geri olarak tek bir yön olan linked list tipidir.
![link to pictures](https://github.com/ahmetmuhammetkocabiyik/Data-Structures/blob/master/Images/oneway_list.jpg)
Yukarıdaki gibi gösterilebilir. Programlarımızda son node’a ulaştığını anlayabilmemiz için son Node’
un pointerı her zaman NULL’a eşitlemek gerekir. Bir nodedan diğerine geçtiğimizde önceki node’a dönmek istersek,  bu linked list 
tipi sadece ileriyi gösterdiği için geri dönemeyiz. Bu yüzden programlarımızda bir head pointerı oluşturup ilk nodu’un adresine
eşitleriz böylece istediğimiz yerde olsak da tekrar ilk node’a dönebilir tekrar ileri giderek geriye gitmiş oluruz. Hafıza da 
her bir node2un içindeki kadar yer tutacağından Linked listler arraylere göre daha fazla yer tutar(Arraylerden farklı olarak 
pointerlar{pointer tipinin birim boyutu kadar} yer tutar).

<h2>2)One Way Circular Linked List</h2>

Bu linked list tipinde işin güzelliği sona gittikten sonra tekrar başa dönebilmemiz.
![link to pictures](https://github.com/ahmetmuhammetkocabiyik/Data-Structures/blob/master/Images/oneway_circular_list.jpg)
Yani son node’un next pointerı NULL’u değil ilk node’u gösteriyor böylece Listede geri gitmek için yeteri kadar ileri gitmemiz
yeterli oluyor. İlkinden tek farkı sonlanması gereken progrmalarda node sayısını bilmeden ilerleyememeiz bu node’un dezavantajıdır.
Ama node sayımızı bilirsek rahatça ileri geri hareket edebiliriz.

<h2>3)Double Way Linked List</h2>

Bu linked list tipinde hem kendinden öncekini hem de kendinden sonrakini tuttar.
![link to pictures](https://github.com/ahmetmuhammetkocabiyik/Data-Structures/blob/master/Images/doubleway_list.jpg)
Yukarıdaki şekilde de göreceğiniz gibi ilk tipimizden farkı iki yöne de gidebilmesidir. Yine son node’u NULL’a eşitlenmiş. 
Son node’un null olması bizim programlarımızda looplarda ileri geri giderken koşul olarak null’a gelmişse dur diyebilmemizi 
sağlar. Aynı döngüyü Circular listelerde yapmaya kalkarsak null olmayacağı için sonsuz loop’a düşer.

<h2>4)Double Way Circular Linked List</h2>

Bu listeyi tahmin etmişsinizdir. Tabi ki kendinden hem öncekini hem sonrasını gösteren hem de son Node’un next pointerı ilk 
node’u gösterir.
![link to pictures](https://github.com/ahmetmuhammetkocabiyik/Data-Structures/blob/master/Images/doubleway_circular_list.jpg)
Şeklinde gösterilebilir. Şimdi gelelim işin kod kısmına , aşağıda one way linked listte hem node eklemeyi hemde bastırmayı görebiliriz. Önemli olan nokta ekleme yapacağımız zaman adres ile birlikte yollamamız gerektiği ama işlemi yaparken bir aracı kullanmak uygun olacaktır.

 
Basit bir ortalama bulma programı yazarsak aşağıdaki gibi olacaktır.
