# Git ve GitHub Hakkında
GitHub, Git adlı bir sürüm kontrol sistemini barındıran bulut tabanlı bir hizmettir. Geliştiricilerin, ilerlemelerini ayrıntılı olarak takip ederken ortak projelerde işbirliği yapmasına ve değişiklikler yapmasına olanak tanır.
Kaynak denetimi olarak da bilinen sürüm denetimi, yazılım kodundaki değişiklikleri izleme ve yönetme uygulamasıdır. Sürüm kontrol sistemleri, yazılım ekiplerinin zaman içinde kaynak kodunda yapılan değişiklikleri yönetmesine yardımcı olan yazılım araçlarıdır. Geliştirme ortamları hızlandıkça, sürüm kontrol sistemleri yazılım ekiplerinin daha hızlı ve daha akıllı çalışmasına yardımcı olur. Geliştirme süresini kısaltmalarına ve başarılı dağıtımları artırmalarına yardımcı olduklarından özellikle DevOps ekipleri için yararlıdırlar .

Peki sürüm kontrolü, yüksek performanslı geliştirme ve DevOps ekiplerinin gelişmesine nasıl yardımcı olur?
Sürüm kontrol yazılımı, kodda yapılan her değişikliği özel bir veritabanı türünde tutar. Bir hata yapılırsa, geliştiriciler saati geri alabilir ve tüm ekip üyelerinin kesintiyi en aza indirirken hatayı düzeltmeye yardımcı olmak için kodun önceki sürümlerini karşılaştırabilir.
Özetle, sürüm kontrolü, geliştiricilerin aynı anda projeler üzerinde çalışmasına olanak tanır. Meslektaşlarının çalışmalarını ihlal etmeden veya geciktirmeden ihtiyaç duydukları kadar değişiklik yapmalarını sağlar. Kaynak kodunda söz konusu değişiklikler, dağıtıldıklarında projeyi mahvederse, GitHub bunları birkaç tıklamayla tersine çevirmeyi kolaylaştırır ve projenin önceki sürümü geri getirilir.
Yazımın başında belirttiğim gibi GitHub Git sürüm kontrol sistemini kullanır.

GIT NEDİR?
Git, 2005 yılında başlatılan ve piyasadaki en popüler VCS'lerden biri haline gelen açık kaynaklı bir projedir. Geliştiricilerin %87'sinden fazlası projeleri için Git'i kullanır.
Dağıtılmış bir sürüm kontrol sistemidir. Yani, erişim izni verilen ekipteki herhangi bir geliştirici, Git komut satırı araçlarını (Git command line tools) kullanarak kaynak kodunu ve değişiklik geçmişini yönetebilir.
Dağıtık sürüm kontrol sistemlerinden bazıları: Aegis, Bazaar, Git, SVK 
Git, merkezi sürüm kontrol sistemlerinden farklı olarak özellik dalları (feature branches) sunar. Bu, ekipteki her yazılım mühendisinin kodda değişiklik yapmak için yalıtılmış bir yerel depo sağlayan bir özellik dalını ayırabileceği anlamına gelir.
Merkezi sürüm kontrol sistemlerinden bazıları: CVS, Subversion, Vesta
Bilgisayarınıza Git'i Kurun
Bunun için Windows'ta PowerShell, macOS ve Linux'ta Terminal'i açın. (Linux işletim sistemlerinde Git halihazırda kurulu olarak gelebilir.)
Komutlar;
Windows: choco install git
macOS: brew install git
Linux: sudo apt-get install git

TEMEL GIT KOMUTLARI

1- git init 
git init komutu, genellikle bir Git deposu olmayan (veya repo olarak adlandırılır) herhangi bir yeni projede çalıştıracağınız ilk komuttur.
Bir klasörü Git deposuna dönüştürmek için veya boş bir repo başlatmak için kullanabilirsiniz.
Git Init Komutunu Kullanın
cd ile başlamak istediğiniz dizine gidin. 
Ardından, bu komutu çalıştırın.

$ git init

Bu, geçerli dizini bir Git deposuna dönüştürür; yeni bir .gitalt dizin eklenecektir. Bu, projenizin birden çok sürümünü kaydetmeye başlamanıza olanak tanır.
2- git clone
Bu komut, kaynak kodu uzak bir depodan (GitHub gibi) indirmek için kullanılır.
Git Clone Komutunu Kullanın
$ git clone <repourl>

Bir depoyu klonladığınızda, kod otomatik olarak yerel makinenize indirilir.
Kolaylık sağlamak için indirilen sürüm, kaynak (indirdiğiniz yerdeki depo) ile bağlantılıdır. Bunun bir kolaylık olduğunu söylüyorum çünkü aynı proje üzerinde işbirliği yaparken, değişikliklerinizi tek bir depoda toplamak istersiniz.
Ancak bazen insanlar bu bağlantıya sahip olmak istemezler. Bunun için bu komutu çalıştırın. 
$ git remote rm origin
Bu, indirilen mevcut depoyu kaynaktan ayıracaktır.
3- Git Branch
Branch, Git'in en önemli işlevlerinden biridir. Bu, ekiplerin aynı kod tabanında paralel olarak çalışmasına olanak tanır.
Diyelim ki mevcut projenin a özelliği üzerinde çalışıyorsunuz . Ve takım arkadaşınız b özelliği üzerinde çalışıyor. Her bir özellik için ayrı bir dal oluşturarak, ikiniz de çakışma endişesi duymadan aynı kod tabanında paralel olarak çalışabilirsiniz.
Yeni bir branch oluşturmak için Git Branch kullanın.
$ git branch <branch-isim>

Bu komut, yalnızca yerel sisteminizde yeni bir branch oluşturacaktır. Bunun depodaki tüm üyeler tarafından görünmesini istiyorsanız,
git push -u <remote> <branch-isim>
Tüm branch'leri görüntüleme komutu;
$ git branch 
veya
$ git branch - list

Bir branch silmek için Git komutu;
$ git branch -d <branch-name>
4- Git Checkout 
Bir branch oluşturduktan sonra başka bir komutla şubeye geçmeniz gerekecek. Git Checkout komutunun devreye girdiği yer burasıdır.
Git Checkout Komutunu Kullanın.
$ git checkout <branch-name>

Bu sizi otomatik olarak komutta belirttiğiniz şube adına yönlendirir.
Ancak, bir şubeden diğerine geçerken iki şeyi göz önünde bulundurmanız gerekir:
Önceki dalda bazı değişiklikler yaptıysanız, önce bunları taahhüt etmeniz ve (bu komutu aşağıda ele alacağım) uzak deponuza göndermeniz gerekir.
Değiştirmek istediğiniz şube yerel sisteminizde mevcut olmalıdır. Değilse, onları çekebilirsiniz.
Benim kadar tembelseniz, eminim hem yeni bir dal oluşturacak hem de otomatik olarak geçiş yapacak tek bir komut isteyeceksiniz.
Aşağıdaki komut tam olarak bunu yapar.
$ git checkout -b <branch-name>

5- Git Add
Her yeni dosya oluşturduğunuzda, sildiğinizde veya değişiklik yaptığınızda Git'e onu izlemesini ve hazırlama alanına eklemesini söylemeniz gerekir. Aksi takdirde, değişikliklerinizi zorlamaya çalıştığınızda değişiklik yaptığınız dosyalar eklenmeyecektir.
Git Add Komutunu Kullanın.
$ git add <file-name>

Bu komut, bir sonraki işleminize yalnızca tek bir dosya ekleyecektir. Değişiklik yapılan tüm dosyaları eklemek isterseniz,
$ git add -A

Git add kullanmanın uzak depoda herhangi bir değişiklik yapmayacağını unutmamak önemlidir. Değişiklikleriniz yalnızca siz bunları commit ettiğinizde kaydedilecektir.
6- Git Commit 
Git Commit komutunu geliştirme sürecinizde bir kontrol noktası gibi düşünün.
Genellikle değişikliklerinizi kaydetmek için kullanılır. Agile Tool'da size atanan belirli bir iş öğesini tamamladıktan sonra olabilir .
Kod değişikliklerinizi her gerçekleştirdiğinizde, yaptığınız değişiklikleri kısaca açıklayan bir mesaj da ekleyebilirsiniz. Bu, diğer ekip üyelerinin nelerin eklendiğini, değiştirildiğini veya kaldırıldığını hızla anlamasına yardımcı olur.
Git Commit Komutunu Kullanın.
$ git commit -a

Bu, çalıştığınız dizindeki tüm değişiklikleri commit edecektir. Bu komut çalıştırıldığında, bir commit mesajı girmeniz istenir. Alternatif olarak, komutun kendisine commit mesajını girebilir ve commit  mesajını girmenizin isteneceği ek adımı atlayabilirsiniz.
Bunu yapmak için aşağıdaki git komutunu çalıştırın:
$ git commit -am "<commit-message>"

7- Git Push
Tüm commit değişikliklerinizi takım arkadaşlarınıza sunmak için, onları uzak kaynağa göndermeniz gerekir.
Git Push Komutunu Kullanın.
$ git push <remote> <branch-ismi>

git push komutunun yalnızca yaptığınız değişiklikleri yükleyeceğini unutmayın.
8- Git Pull
Tabii ki, takım arkadaşlarınızdan da en son güncellemeleri almak istersiniz.
git pull komutu, takım arkadaşlarınızın push ettiği tüm değişiklikleri getirmenize ve bunları otomatik olarak reponuzla birleştirmenize olanak tanır.
Git Pull Komutunu Kullanın.
$ git pull <remote>

Çoğu durumda, başka bir takım arkadaşının eklediği bir dosyadaki satırı değiştirdiğiniz için çakışmayla karşılaşacaksınız. Bu gibi durumlarda, çakışmaları manuel olarak çözmeniz gerekir.
9- Git Stash 

Git Stash çalışmanızı geçici olarak rafa kaldırır, böylece başka bir yere geçebilir, başka bir şey üzerinde çalışabilir ve daha sonra buna geri dönebilirsiniz.
Başka bir şey üzerinde çalışmanız gerekiyorsa ve bir kod değişikliğinin ortasındaysanız, ancak kodu uygulamaya hazır değilseniz, bu mükemmeldir.
Git Stash Save Komutunu Kullanın.
$ git stash save "<stash-message>"

Bu, girdiğiniz mesajla değişikliklerinizi saklayacaktır. Bu, özellikle birkaç zulanız olduğunda, geri dönüp zulanızı geri yüklemek istediğinizde yardımcı olabilir.
Ancak bu, yalnızca git add kullanarak eklediğiniz izlenen dosyalarınızı saklar. İzlenmeyen dosyaları da dahil etmek istiyorsanız, çalıştırın
$ git stash save -u

Git Stash List Komutunu Kullanın.
Saklanan tüm kodları görüntülemek istediğinizde, bu komutu kullanarak bunları görüntüleyebilirsiniz. Kodunuzu sakladığınızda, git bir saklama kimliği atar, böylece daha sonra belirli bir saklanan kodu geri yükleyebilirsiniz.
Örneğin:
$ git stash list
Bu, aşağıdakileri gösterebilir
stash@{0}: On master: Stashed with message1
stash@{1}: On master: Stashed with message2
Git Stash Apply Komutunu Kullanma
Bu, yığındaki en üstteki zulayı otomatik olarak geri yükleyecek ve uygulayacaktır.
$ git stash apply

Uygulamak istediğiniz belirli bir zulayı geri yüklemek istiyorsanız, yukarıdaki örneği kullanarak basitçe çalıştırabilirsiniz.
Git Stash Pop Komutunu Kullanın.
Stash'ı yığından da otomatik olarak silmek için git stash pop komutu kullanılır.
Yığındaki belirli bir zula için yapmak istiyorsanız, çalıştırın git stash pop stash@{0}.
10- Git Status

Deponuzda olanlarla biraz kaybolmuş hissettiğinizde Git Status komutu, bilmeniz gereken tüm bilgileri size söyleyebilir.
Git Status Komutunu Kullanın.
$ git status

11- Git Log

Git durumu size ihtiyaç duyacağınız neredeyse tüm bilgileri verirken, commit geçmişi hakkında size bilgi vermez. İşte git log burada kullanılır.
Git Log Komutunu Kullanma
$ git log

Bu, tüm commit geçmişini görüntüler. Commit geçmişiniz büyükse, bunun yalnızca bir bölümünü gösterir ve kaydırmak için [boşluk] tuşuna basabilir veya çıkmak için q yazabilirsiniz.
