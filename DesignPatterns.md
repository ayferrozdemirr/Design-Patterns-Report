###Tasarım Desenleri (Design Patterns) Raporu


##Tasarım Deseni Nedir?

Tasarım desenleri, yazılım dünyasında tekerleği her seferinde yeniden icat etmemek için kullanılan "en iyi pratikler" (best practices) bütünüdür. Bir tasarım deseni hazır bir kod bloğu değil, kodun nasıl yapılandırılması gerektiğini gösteren bir şablondur.
Neden Pattern Kullanılır?

* Standartlaşma: Ekipteki tüm yazılımcıların aynı dili konuşmasını sağlar.
* Bakım Kolaylığı: Kodun karmaşıklığını azaltır, gelecekte yapılacak değişiklikleri kolaylaştırır.
* Yeniden Kullanılabilirlik: Test edilmiş ve onaylanmış çözümler olduğu için hata payını düşürür.
* Esneklik: Yazılımın yeni özelliklere daha dirençsiz uyum sağlamasına yardımcı olur.

##Temel Tasarım Desenleri ve İşlevleri

#Singleton (Tek Nesne)
Bir sınıftan sadece bir tane nesne (instance) oluşturulmasını garanti eder ve bu nesneye her yerden erişim sağlar. Genellikle veritabanı bağlantıları veya loglama mekanizmaları için tercih edilir.

#Factory (Fabrika)
Nesne oluşturma mantığını istemci taraftan ayırır. Hangi nesnenin oluşturulacağına merkezi bir metodun karar vermesini sağlar. Bu, sistemin nesne türlerine olan bağımlılığını azaltır.

#Strategy (Strateji)
Belirli bir işlemin farklı şekillerde yapılabileceği durumlarda kullanılır. Çalışma anında (runtime) hangi algoritmanın kullanılacağını seçmemize olanak tanır. Örneğin; ödeme sistemlerinde (Kredi kartı, Havale, PayPal) farklı stratejiler tanımlanabilir.

#Observer (Gözlemci)
Bir nesnenin durumunda değişiklik olduğunda, ona bağlı olan diğer tüm nesnelerin otomatik olarak bilgilendirilmesini sağlar. Modern yazılımlardaki "Event" sistemlerinin temelidir.

#Adapter (Adaptör)
Birbirleriyle uyumsuz olan iki arayüzün (interface) birlikte çalışmasını sağlar. Mevcut bir sınıfı, sistemin beklediği farklı bir arayüze dönüştürmek için kullanılır.

#Decorator (Dekoratör)
Nesnelere, mevcut yapılarını bozmadan dinamik olarak yeni özellikler eklemeyi sağlar. Kalıtım yerine kompozisyon kullanarak nesne işlevselliğini genişletir.

##Junior ve Senior Farkı
Görselde belirtilen en önemli kazanım, kodun kalitesi üzerindeki etkisidir:
* Junior Kodu: Genellikle sadece o anki işi bitirmeye odaklanır (spagetti kod). Karmaşık if-else blokları ve iç içe geçmiş yapılar içerir. Değişim zordur ve kod kırılgandır.
* Profesyonel Kod: Tasarım desenlerini kullanarak inşa edilir. Kod modülerdir, okunabilirdir ve "Open-Closed" prensibine uygundur (gelişime açık, değişime kapalı).