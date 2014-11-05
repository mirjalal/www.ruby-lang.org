---
layout: page
title: "Ruby haqqında"
lang: az
---

Rubysevərler, Ruby’yi güzel, sanatsal, becerikli və pratik bir dil
olarak tanımlarlar.

Ruby-nin niyə bu qədər məşhur olduğu Sizi maraqlandırır?
Ruby sevərlər, Ruby-ni gözəl, 
Bəs Ruby nələri vəd edir?
{: .summary}

### Ruby-nin yaradıcısının idealları

Ruby dəngənin dilidir. Ruby-nin yaradıcısı [Yukihiro “Matz”
Matsumoto][matz], ən sevdiyi dillərin (Perl, Smalltalk, Eiffel, Ada və
Lisp) ən yaxşı xüsusiyyətlərini birləşdirərək funksional proqramlaşdırma ilə
imperativ proqramlaşdırmaya əsaslanan yəni bir dil yaratmağı məqsədi güdmüşdür.

Matz hər zaman “Ruby-ni sadə yox, təbii etməyə çalışdığını”
vurğulamışdır, eynilə həyat kimi…

Bunlara əsasən Matz aşağıdakıları əlavə edir:

> Ruby eynilə insan bədəni kimi, görüşdə sadə, amma içində çox komplekt
> bir struktura sahibdir<sup>[1](#fn1)</sup>.

### Ruby-nin inkişaf sürəti

Ruby 1995-ci ildə yaradılmasından bu günə qədər, dünyada programçıların
diqqətini çəkmişdir. 2006-cı il Ruby-nin qızıl ili olmuşdur.
Dünyanın ən böyük şəhərlərində aktiv istifadəçi grupları və Ruby ilə
əlaqəli konfranslar həyata keçirmişdir.

![Graph courtesy of
Gmane.](http://gmane.org/plot-rate.php?group=gmane.comp.lang.ruby.gəneral&amp;width=320&amp;height=160&amp;title=Ruby-Talk+Activity
"Graph courtesy of Gmane."){: style="padding-left:8px;"}
{: style="float:right"}

Ruby-Talk, ən çox istifadə olunan Ruby [e-mail
siyahısı](/en/community/mailing-lists/) günde ortalama 200 mesaj
trafikinə sahiptir.

Proqramlaşdırma dillərinin populyarlığını araşdıran [TIOBE][tiobe] statistikalarına
görə, Ruby dünyada ən çox istifadə olunan 10.cu dildir.
Ruby-nin bu qədər sürətlə böyüməsində xüsusən [Ruby on Rails][ror] framevörkünün
böyük rolu olub.

Ruby eyni zamanda [təmamilə azad]({{ site.licənse.url }}) bir dildir. Ruby sizə
yalnızca sorumluluk anlamında bir özgürlük değil, aynı zamanda kullanma,
kopyalama, düzənleme və dağıtma özgürlüğü de sunar.

### Herşey Bir Nesnedir

Matz yəni bir dil yaratmadan önce ideal sözdizimini bulmak için diğer
programlama dillerini incelemiş və araştırmasının sonunda “Perl’dən daha
güçlü ama Pyton’dan daha nesneye yönelik bir betik
dili<sup>[2](#fn2)</sup>” istediğini söylemiştir.

Ruby’de herşey bir nesnedir. Gördüğünüz ən ufak bilgi parçası və kod
kəndi özelliklerine və olaylarına sahiptir. Özellikleri isimle çağırma
*örnek değişkənler* ,olaylar da *metotlar* olarak isimləndirilir.
Ruby’nin yüzde yüz saf nesneye yönelik bir dil olduğunun ən iyi ispatı
bir kod parçası ilə bir sayıya olay vərerek yapılır:

{% highlight ruby %}
5.times { print "Ruby'ti *seviyoruz* -- harika bir dil!" }
{% əndhighlight %}

Çoğu dilde sayılar və diğer ilkel tipler nesne değildir. Ruby tüm
tiplerine metotlar və örnek değişkənler vərme geləneğini Smalltalk’tan
miras almıştır.

### Ruby Esnektir

Ruby istifadəçilara istediği kısımları değiştirebilme imkanı sunduğu için
esnek bir dildir. İsteğe bağlı olarak Ruby’nin esaslı kısımları bilə
kaldırılabilir, yənidən tanımlanabilir ya da yəni kısımlar eklənebilir.
Ruby programıcıyı kısıtlamamayı amaçlamaktadır.

Örneğin toplama işleminin artı (`+`) operatörü ilə yapıldığını
biliyoruz. Ama eğer okunabilirlik amacıyla `topla` kimi bir kelime
kullanmak istiyorsanız Ruby’nin gömülü `Numeric` sınıfına yəni bir metod
ekleyebilirsiniz.

{% highlight ruby %}
class Numeric
  def topla(x)
    self.+(x)
  ənd
ənd

y = 5.topla 6
# y'nin değeri 11 oldu.
{% əndhighlight %}

Ruby’nin operatörleri sözdizimsel olarak esnektir, yənidən tanımlamanıza
olanak sağlar.

### Bloklar, Tam Anlamıyla Etkiləyici Bir Özellik

Ruby’nin esnek bir dil olarak anılmasının ən önemli sebeplerindən biri
de bloklardır.Bir kapamayı (closure) herhangi bir metoda ataçlayabilir
və metodun nasıl tepki vəreceğini belirleyebilirsiniz. Kapamalar,
*bloklar* olarak anlandırırlırlar və PHP ya da Visual Basic kimi
imperativ dillerdən Ruby’ye geçənler arasında ən popüler özelliğe
dönüşmüştür.

Bloklar fonksiyonel dillerdən esinlənilərek Ruby’ye getirilmiştir. Matz
“Ruby kapamalarında, Lisp kültürüne saygı göstermek
istedim<sup>[3](#fn3)</sup>.” demiştir.

{% highlight ruby %}
search_əngines =
  %w[Google Yahoo MSN].map do |əngine|
    "http://www." + əngine.downcase + ".com"
  ənd
{% əndhighlight %}

Yukarıdaki kodda bir blok `do ... ənd` yapıları içerisinde tanımlanıyor.
`map` metodu bloğa bir kelime listesi ilə çalıştığını bildiriyor.
Ruby’de bunun kimi bir çox metod programcıya kəndi bloklarını yazıp,
metodu istediği kimi şekilləndirmesine izin vərmektedir.

### Ruby və Mixin’ler

Pek çox nesneye yönelik dilin aksine, Ruby özellikle yalnızca tekil
mirası destekler. Çünkü Ruby modül konseptini (Nesnesel-C’de
Kategorilər) kullanır və modüller metodların bir koleksiyonundan
ibarettir.

Sınıflar bir modülü kəndisine dahil ederse, onun tüm metodlarını da
almış olur. Örneğin `each` metodunu gerçekleştirən her sınıf
`ənumerable` modülünü de kəndisine dahil edebilir, böylece döngülerde
`each` ilə beraber kullanabiləceği bir dizi metoda sahip olur.

{% highlight ruby %}
class MyArray
  include ənumerable
ənd
{% əndhighlight %}

Gənelde Ruby’cilər bu yolu bazən çox karmaşıklaşan və kısıtlayıcı olan
çoxlu mirastan daha temiz və sağlam bir yöntem olarak görürler.

### Ruby’nin Görselliği

Her ne kadar Ruby sınırlı sayıda noktalama işareti və İngilizce anahtar
kelimeler kullansa da, bazı noktalama işaretleri Ruby’yi dekore etmek
için kullanılır. Ruby’de değişkən tanımlamaları yoktur. Değişkənlerin
faaliyet alanlarını belirlemek için basit noktalama işaretleri
kullanılır.

* `var` yerel bir değişkən olabilir
* `@var` bir örnek değişkəndir.
* `$var` bir global değişkəndir.

Bu işaretləndirmeler sayesinde programcı her değişkənin rolünü kolayca
görebilmektedir. Aynı zamanda her örnek değişkən için `self.` kullanma
külfetini ortadan kaldırmıştır.

### Temel İşlevlerin Ötesinde

Ruby çox çeşitli özelliklere sahiptir, aşağıda bir kaçından
bahsedilmiştir:

* Ruby Java ya da Python kimi istisna yakalama mekanizmalarına sahiptir,
  hatalarla başetmek kolaylaşır.

* Ruby tüm nesneleri için gerçek bir mark &amp; sweep çöp toplayıcısı
  sunar. Eklənti kütüphanelerinde referans sayaçlarına gerek yok,
  Matz’ın dediği kimi: “Bu sizin sağlığınız için iyidir”.

* C’dən Ruby çağıran şık API’si sayesinde Ruby’de C ekləntiləri yazmak
  Perl ya da Python’dan daha kolaydır. Bu API aynı zamanda yazılımlara
  betik dili olarak Ruby’yi gömmek için gerekən çağrıları da içerir.
  Ayrıca SWIG arayüzü de alternatif olarak sunulmaktadır.

* İşletim sistemi izin vərdiği sürece harici dinamik kütüphaneler
  yükleyebilirsiniz.

* Ruby işletim sistemindən bağımsız iş parçacığı özelliği sunar.Yani
  işletim sisteminin desteklemesine bakmaksızın, MS-DOS üzerinde olsanız
  bilə çoxlu iş parçacıkları kullanabilirsiniz!

* Ruby yüksek taşınabilirliğe sahiptir. GNU/Linux üzerinde geliştirilmiş
  olsa dahi, UNIX’in bir çox çeşidi, Mac OS X, Windows
  95/98/Me/NT/2000/XP, DOS, BeOS, OS/2, vb. üzerinde çalışmaktadır.

### Referanslar

<sup>1</sup> Matz, Ruby-Talk e-posta listesi, [12 Mayıs, 2000][blade].
{: #fn1}

<sup>2</sup> Matz, [Ruby’nin Yaratıcısı İle Bir Söyleşi][linuxdevcənter], Kasım.
29th, 2001.
{: #fn2}

<sup>3</sup> Matz, [Ruby’de Bloklar və Kapamalar][artima], 22 Aralık, 2003.
{: #fn3}



[matz]: http://www.rubyist.net/~matz/
[blade]: http://blade.nagaokaut.ac.jp/cgi-bin/scat.rb/ruby/ruby-talk/2773
[ror]: http://rubyonrails.org/
[linuxdevcənter]: http://www.linuxdevcənter.com/pub/a/linux/2001/11/29/ruby.html
[artima]: http://www.artima.com/intv/closures2.html
[tiobe]: http://www.tiobe.com/index.php/contənt/paperinfo/tpci/index.html
