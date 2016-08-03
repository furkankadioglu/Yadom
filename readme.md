
YADOM - Yazılım Dökümantasyon Modeli
------------------------------
Müşteri, Yazılım Geliştirmeni arasındaki iletişimi en az hatayla kurmayı ve bunu sürdürmeyi amaçlayan, dökümantasyon yapısı.

Yapı
====
 - Tip
 - Öncelik Durumu
 - Fikir
 - İstek
 - Modeller
 - Fonksiyonlar
 - Bağlı Sayfalar
 - Dolaylı Sayfalar
 - Beklentiler
 - Dosya Ekleri
 - Diğer Notlar


Yapıda bulunan her maddeyi tek tek açıklamaya çalışacağım şimdi. Örnekli yoldan gidelim.

Burada örneğimiz bir blog olsun; yani bir blog sistemi kodlanacak ve bunu YADOM formatına göre anlatmayı göstereceğiz. Önce tek tek yapı elementlerini örneklendirecek, sonra da tam bir örnek vereceğim.

## Tip ##

Üçe ayrılmalıdır. Bunlar nelerdir?

 1. Major
 2. Minor
 3. Patch

**Neden Böyle?**

Çünkü [Semantic](http://semver.org/) versiyonlamayı kullanıyoruz. Hal böyle olunca da fikrin ve dökümantasyonun kendisine göre versiyon vermemiz gerekir, bu yapı sayesinde fikir ve dökümanla birlikte versiyonlama planı da oluşmuş oluyor.

Major, Minor ve Patch arasındaki farklar temel olarak şu şekildedir;

 - **Major**: Ana fikri ve büyük bir yapı değişikliği/eklenti/oluşumu kapsar.
 - **Minor**: Küçük değişiklikleri kapsar, major sınıfına girmeyecek herşey buraya dahildir.
 - **Patch**: Daha önce major ve minor sınıflarında yazılan kodlardan herhangi birinde hata/bug çıktıysa, bu durumu düzeltmek için yapılan güncellemelere/fixlere denir.

Daha fazla bilgi almak için [semver.org](http://semver.org)'u kaynak alabilirsiniz.

**Örnek Kullanım**

Blog sistemimize bir de sabit sayfa yapısı ekleyeceğiz.

**Tip:** Major

Blog sistemimizdeki mevcut olan sayfa yapımıza, dinamik olarak anasayfayı da düzenlemeyi ekleyeceğiz.

**Tip:** Minor

İletişim sayfasından mail göndermeye çalışınca hata çıkıyor.

**Tip:** Patch


## Öncelik Durumu ##

Öncelik durumu yazılımcının iş listesini düzene sokar, müşteri ise önce görmek istediklerini ve yaptırmak istediklerinin öncelik listesini çıkarmış, daha nesnel bir plan listesi oluşturur. Burada dikkat edilmesi gereken nokta; bu öncelik durumları deadline tarihleri değillerdir.

Öncelik durumları listesi şu şekildedir, sırasıyla öncelikliden önceliksize gitmektedir.

 - Önemli ve Acil
 - Önemli
 - Önemsiz
 - Bekleyebilir

**Örnek Kullanım**

İletişim sayfasından mail göndermeye çalışınca hata çıkıyor.

**Öncelik Durumu:** Önemli ve Acil

Blog sistemimizdeki mevcut olan sayfa yapımıza, dinamik olarak anasayfayı da düzenlemeyi ekleyeceğiz.

**Öncelik Durumu:** Önemli

İnternet sitesine girdiğimizde, galeri bölümünde bir yavaşlık var gibi.

**Öncelik Durumu:** Önemsiz

Kontrol panelinde sayfa ekleme butonu "ekle" yerine "submit" olarak kalmış.

**Öncelik Durumu:** Bekleyebilir

## Fikir ##

Kısaca yapılacak işin tek cümlelik özetine denir, tek cümlelik(!). 

**Örnek Kullanım**

Yapılacak İş:  Kontrol panelindeki sayfalar bölümüne giriş yapıldığında tarihler şu an 03:12:00 01.01.1993 şeklinde çıkıyor, bunların "2 saat önce", "6 ay önce" gibi zaman tiplerine çevirilmesi gerekli, eski ve detaylı tarihlerin de profil bölümüne taşınması mantıklı olacaktır.

**Fikir:**  Sayfalardaki tarihlerin kolay okunabilirliğini sağlamak

## İstek ##

Kısaca fikirin detaylandırılmış versiyonu, burada fikrinizin tam detayını bahsetmenizi, olmasını istediğiniz herşeyi detaylıca anlatmanız bekleniyor.

**Örnek Kullanım**

Fikir:  Sayfalardaki tarihlerin kolay okunabilirliğini sağlamak

**İstek:**  Kontrol panelindeki sayfalar bölümüne giriş yapıldığında tarihler şu an 03:12:00 01.01.1993 şeklinde çıkıyor, bunların "2 saat önce", "6 ay önce" gibi zaman tiplerine çevirilmesi gerekli, eski ve detaylı tarihlerin de profil bölümüne taşınması mantıklı olacaktır.

## Modeller *(Opsiyonel)* ##

Opsiyonel yazdığına bakmayın, bazı durumlarda kullanılması mümkün olmadığından bu şekilde, gerektiğinde gayet zorunlu bir parametremizden bahsedeceğim. 

Model, bir fikrin zorunlu veya opsiyonel değişkenlerinin belirtildiği yerdir. Cümlelerle anlatması zor, örneğe geçelim.

**Örnek Kullanım**

Özet İstek: Basit bir sayfalar bölümü olacak, yeni sayfa eklenebilecek. *(Bu durumda modelimiz Sayfa oluyor)*
Bu durumda sayfa adı altında tutulacak veriler, model bölümünde belirtilir, hemen yapalım. 

Bir model başlığı olur ve detayları olur.

**Model:** 
SAYFA
 - Sayfa Başlığı
 - Sayfa Açıklaması
 - Sayfa Keywordleri
 - Oluşturulma Tarihi
 - Okunma Sayısı

## Fonksiyonlar *(Opsiyonel)* ##

Bu da modeldeki gibi, duruma bağlı olarak zorunludur. Eğer bir model varsa ancak bu bölümde olabilir.

Fonksiyonlar, burada fikir olarak bir modelin işleyişlerini belirtmeniz bekleniyor. Örnekle daha iyi anlaşılacaktır. İki parametresi vardır biri fonksiyonun bağlı olacağı modelin adıdır diğeri ise açıklamasıdır. Burada sizden beklenen bir yazılımcı gibi fonksiyonlar yazmanız değildir, sadece fikir modelinizin işleyişlerini anlatırsanız, yazılımcılar bunu daha kolay algılayıp koda hatasız dökeceklerdir.

Standart fonksiyonları **yazmamanız** sizin için daha iyi olur bu arada, mesela; Oluşturma, Silme, Düzenleme, Kaydetme

**Örnek Kullanım**

Modelde belirttiğimiz örnekten gidelim.

Özet İstek: Basit bir sayfalar bölümü olacak *(temel modelimiz Sayfa oluyor)*

**Fonksiyon:** Okuyucu Ekle

Kullanıcı sayfaya girdiğinde, kullanıcının bu sayfayı okuduğunu bildiren bir veri kaydet.

**Fonksiyon:** Okuyucuları Getir

Oluşturduğumuz sayfayı kimler okumuşsa databaseden bunları getir ve listele.

**Fonksiyon:** Facebookta Paylaş

Kullanıcı, sayfaya girdikten ve okuduktan sonra bir buton ile yazıyı sosyal medyada paylaşabilmelidir.

## Bağlı Sayfalar *(Opsiyonel)* ##

Bu fikri kapsayan sayfalara denir, fikir koda çevirildiğinde bu fikrin görüntülenmesi, yönetilebilmesi gibi bölümlerin hangi sayfalarda olacağını gösterir. Örneğe geçelim!

**Örnek Kullanım**

Modelde belirttiğimiz örnekten gidelim.
Özet İstek: Basit bir sayfalar bölümü olacak *(temel modelimiz Sayfa oluyor)*

**Bağlı Sayfa:** Sayfa görüntüleme sayfası

**Bağlı Sayfa:** Tüm sayfaların görüntülendiği bir sayfa (timeline)

**Bağlı Sayfa:** Kontrol paneli sayfa görüntüleme düzenleme

**Bağlı Sayfa:** Kontrol paneli sayfa görüntüleme ekleme

**Bağlı Sayfa:** Kontrol paneli sayfa görüntüleme silme


## Dolaylı Sayfalar *(Opsiyonel)* ##

Böyle bir parametre gerekli olmayabilir veya aklınıza da gelmemiş olabilir, biraz detaya kaçmış bir parametre olduğunun farkındayım fakat eğer doldurulabilirse en çok çıkan bir aksaklığın/unutulmuşluğun önüne geçebilecektir.

Dolaylı Sayfa, bir fikrin sisteme entegrasyonuyla birlikte önceden yapılmış bölümlerde yapılacak değişikliği belirtir.

**Örnek Kullanım**

Modelde belirttiğimiz örnekten gidelim.

Özet İstek: Basit bir sayfalar bölümü olacak *(temel modelimiz Sayfa oluyor)*

**Dolaylı Sayfa:** İnternet sitemizdeki tüm sayfaların üst navigasyon menüsüne SAYFALAR bölümünü ekleyelim.

**Dolaylı Sayfa:** Sayfalar bölümünü eklememizle birlikte, Anasayfa'ya Son Açılmış Sayfalar diye bir ek yapalım. 

## Beklentiler *(Opsiyonel)* ##

Burada fikrinizi gerçekleştirecek olan yazılımcıdan yapmasını umduğunuz şeyleri yazmalısınız (eğer varsa), bu konu da en iyi örnekle anlaşılacaktır. 

**Örnek Kullanım**

Modelde belirttiğimiz örnekten gidelim.

Özet İstek: Basit bir sayfalar bölümü olacak.

**Beklenti:** Sayfa arama bölümünde aranılacak sayfayı yazdığımızda sayfa yenilenmeden veriler gelmeli.

**Beklenti:** Admin panelinde sayfa silmeye tıkladığımızda emin misiniz diye sormalı.

## Dosya Ekleri *(Opsiyonel)* ##

Dosya eki, fikrinizi daha iyi anlatmayı amaçlayan materyalleri koyabileceğiniz bölüm.

**Örnek Kullanım**

Varsayalım ki Google'ın ana arama sayfasını düzenlettiriyorsunuz, fikriniz bunun üzerine..

**Dosya Eki:** http://galeri2.uludagsozluk.com/301/insanin-olum-ani-videosunda-bile-reklam-almak_377263.jpg

## Diğer Notlar *(Opsiyonel)* ##

Diğer Not, dediğimiz kısım ise bu şablona sığdıramadığımız fakat yazma gereksinimi bulunduğunuz geriye kalan herşeydir. İletmek istediğiniz bir bilgi de olabilir.

**Örnek Kullanım**

**Diğer Not:** Saat 13.00'dan sonra ofiste olacağım, sorun varsa görüşebiliriz.

**Diğer Not:** Site kontrol paneli şifresi 123456.

Diğer
====

Yazılı iletişimi en fonksiyonel halde işimiz de nasıl kullanabiliriz diye düşünerek bu dökümantasyonu yazdım, Dökümantasyon formatı olarak gerçekten çok uzun veya çok sade başka formatlarda olmasına rağmen bu yapının daha amaca ve iletişime yönelik olduğunu düşünüyorum.

Önerilere ve geliştirmeye tamamen açıktır.

Son Örnek
====

 **Tip**
 Minor

----------


 **Öncelik Durumu**
 Önemli

----------


 **Fikir**
 Haberler diye bir bölüm eklenmesi

----------

 **İstek**
Haberler bölümü kontrol panelinden yönetilebilir. Haberler bölümünün kategorileri olmalı ve bu kategoriler de yine kontrol panelinden yönetilebilir olmalı. Buradan girdiğimiz haberleri kullanıcılar Haberler bölümünden görüntüleyebilmeli ve istedikleri haberi tıklayıp okuyabilmeleri gerekiyor, beğendikleri haberi de facebookta paylaşabilmeleri lazım.


----------


 **Modeller**

HABER
 - Haber Başlığı
 - Haber Açıklaması
 - Haber Keywordleri
 - Haber Kategorisi (Oluşturulacak olan kategori modeliyle bağlantılı)
 - Yazar (Daha önceki kullanıcı modelinden bağlantılı)
 - Oluşturulma Tarihi
 - Okunma Sayısı

KATEGORI
 - Kategori Adı
 - Kategori Açıklaması

HABER KATEGORI BAGLANTISI
*(Burası için biraz yazılım bilgisi gerekebilir, bunu eklemeseniz de olur, bu tablo bir köprü görevi görerek haberler ile kategorileri eşleştirir)*
 - Kategori Adı
 - Haber Adı

----------

 **Fonksiyonlar**

Fonksiyon: Okuyucu Ekle
Kullanıcı sayfaya girdiğinde, kullanıcının bu sayfayı okuduğunu bildiren bir veri kaydet.

Fonksiyon: Okuyucuları Getir
Oluşturduğumuz sayfayı kimler okumuşsa databaseden bunları getir ve listele.

Fonksiyon: Facebookta Paylaş
Kullanıcı, sayfaya girdikten ve okuduktan sonra bir buton ile yazıyı sosyal medyada paylaşabilmelidir.

----------


 **Bağlı Sayfalar**

Bağlı Sayfa: Haber Ekleme Sayfası

Bağlı Sayfa: Haber Silme Sayfası

Bağlı Sayfa: Haber Düzenleme Sayfası

Bağlı Sayfa: Kullanıcı Haber Görüntüleme Sayfası

Bağlı Sayfa: Kategoriler Sayfası

Bağlı Sayfa: Kategorideki Haberler Sayfası


----------


 **Dolaylı Sayfalar**

Dolaylı Sayfa: Anasayfa sayfasının sağ kısmına son eklenen haberler bölümü ekleyelim ve burada son 5 haber çıksın.

----------


 **Beklentiler**
 
 Beklenti: Kullanıcı tarafında haber arama bölümünde dinamik arama olsun, sayfa yenilenmeden arama yapsın ve sonuçlar gelsin.

----------


 
 **Dosya Ekleri**

Şu siteye benzeyebilir haberler bölümü

Dosya Eki: http://www.nytimes.com/

----------


 **Diğer Notlar**

Diğer Not: Kontrol paneline giriş yapabilmen için sana hesap oluşturdum kullanıcı adı dev şifresi 1234

Diğer Not: Yarın saat 2'den sonra sorularını yanıtlayabilirim.
