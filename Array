
ARRAY
-----
Merhabalar. ilk serimiz olan data structure'ın ilk bölümü olan arraylerden başlayarak linked list,stack,
queue,tree ve son olarak da graphlarla serimizi tamamlamayı düşünüyorum.Çok vakit kaybetmeden hadi başlayalım;4
Arrayler blok halinde veri tutmamız gerektiğinde kullanmamız için tasarlanmış ADT(Abstract Data Type) üzerinde tanımlı bir yapıdır.
Örneğin 20 çallışanı olan bir firma için bir dizi sayı tutma ihtiyacınız oldu. Şimdilik 20 tane sayı tutmamız gerektiğini 
varsayalım. Her bir rakamı ayrı ayrı
int birinci_sayi=21;
int ikinci_sayi=213123;
şeklinde tutmak cidden yorucu bir iş olurdu ayrıca birden fazla liste olduðunu düþündüğümüzde isim bulmakta bile zorlanmaya başlardık.
Bu gibi durumlarda bizler arrayeri kullanıyoruz. Arraylerimizi 'ADT tipi'-'arrayimizin ismi'-['arryimizin boyutu']; şeklinde tanım-
lıyoruz. Bu bizim şu an ki ihtiyacımız için
int array[20];
şeklinde olacaktır. Tip niye önemli derseniz hafızada yer ayırıken önemli, isim de kolay kullanım için önemli(adreslerle uğraşmak 
istemeyiz), boyut ise bizim sınırlandırıcı etkenimiz olarak yine arrayin tanımlanması sırasında lazım olduğu için isteniyor. 
Sınırlandırıcı etkenden kastım eğer programı çalıştırıken 20 değil de 30 sayı girmeniz gerekirse o zaman yeni bir array tanımlayıp
ilk tanımladığınız arraydeki verileri yeni tanımladığınız array'e teker teker atayıp ardından yeni verilerinizi 
ekleyebilirsiniz(C progrmalama dilinde boyut sıkıntısını aşmanın bir yolu var aslında). Peki arrayleri tanımlarken veya 
silinirken(bir şekilde birinin silmesi lazım, silinmez ise bizim için en değerli şeylerden olan ram kullanımı artar ve biz 
bunu istemeyiz) arka planda neler oluyor;
Öncelikle arrayimizi tanımlarken (arrayimizin boyutu)*(arrayimizin tipinin default boyutu{örneğin int için 4 byte, 
double için 8 byte}) kadar arasında boşluk olmayan yani blok halinde Ram'de bir yer ayrılıyor. 
Bizim örneğimiz için (20)*(4byte)=80byte'lık bir hafıza sadece bizim 20 tane sayımızı tutumak için ayrılıyor. Peki silinirken
nasıl siliniyor siz programlama yaparken silindi mi silinmedi mi kontrol etmiyorsunuz.OOP dillerden herhangi birinde programlama
yapıyorsanız default constructor sizin yerinize bu işi hallediyor. Eğer c gibi bir procedural programlama dillerinde programlama 
yapıyorsanız programınız çalışmayı bitirinceye kadar arrayiniz silinmeyecektir. En son program kapandıktan sonra işletim
sisteminiz sizin yerinize hafızayı tekrar boşaltacaktır. Peki arrayi tanımladık içini nasıl dolduracağız;
array[0]=123123;
array[2]=397461;
şeklinde doldurabiliriz. Arraylerde ileri veya geri gitmek içinse sadece köşeli parantezler içine girdiğimiz değerleri azaltıp
artırmamız yeterli. Peki program arkada nasıl çalışıyor derseniz, arraylerin blok halinde tutulduğunu söylemiştim. 
Ram'de adresler üzerinden çalışan bir yapıya sahip. Dolayısıyla sizin köşeli parantezler arasına girsdiğiniz değerler hafızada 
arrayin tutulduğu adresten array tipinizin default boyutu kadar ileride oluyor. Unutmadan arrayler C,C++,JAVA gibi dillerde 0'dan
başlarken COBOL,FORTRAN,ALGOL68 gibi dillerde 1'den başlıyor. Resimde hexadecimal olarak gösterildiğini bilerek adreslerin 
farklarını alırsanız size array tipinizin deafult boyutunu verecektir. Son olarak arraylerin pozitif ve negatif yöleri şunlardır:

POZİTİF YÖNLERİ

    Rahat hareket kabiliyeti(ileri-geri{özellikle loooplarla kullanım})
    Kolay anlaşılabilir

NEGATİF YÖNLERİ

    Boyutunun sabit olması
    Dolduğunda yeni bir array tanımlama ihtiyacı
Blok halinde depolanma(Eğer yeni bir array tanımlamanız gerekiyorsa ve Raminiz yeterli değilse)
