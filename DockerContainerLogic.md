###DOCKER CONTAINER MANTIĞI RAPORU

##Giriş
Günümüzde yazılım geliştirme süreçleri hızla değişmekte ve uygulamaların farklı ortamlarda sorunsuz şekilde çalıştırılması büyük önem taşımaktadır. Geleneksel yöntemlerde bir uygulamanın geliştirici bilgisayarında çalışmasına rağmen sunucu ortamında hata vermesi sık karşılaşılan bir problemdir. Bu durum; işletim sistemi farklılıkları, eksik kütüphaneler, sürüm uyuşmazlıkları ve bağımlılık problemlerinden kaynaklanmaktadır.
Bu sorunları çözmek amacıyla konteyner teknolojileri geliştirilmiştir. Docker, konteyner teknolojisinin en yaygın kullanılan platformlarından biridir. Docker sayesinde uygulamalar tüm bağımlılıklarıyla birlikte paketlenerek taşınabilir hale gelir. Böylece uygulama “her ortamda aynı şekilde çalışan” standart bir yapıya kavuşur.
Bu raporda Docker container mantığı detaylı şekilde incelenecek; Docker’ın çalışma prensibi, mimarisi, bileşenleri, avantajları, kullanım alanları ve uygulama süreçleri ayrıntılı biçimde açıklanacaktır.

##Docker Nedir?
Docker, uygulamaları konteyner adı verilen izole ortamlarda çalıştırmaya yarayan açık kaynaklı bir platformdur. Docker ilk olarak 2013 yılında geliştirilmiş ve kısa sürede yazılım dünyasında yaygın hale gelmiştir.

Docker’ın temel amacı:
->Yazılımın her ortamda aynı şekilde çalışmasını sağlamak
->Kurulum süreçlerini kolaylaştırmak
->Uygulama dağıtımını hızlandırmak
->Kaynak kullanımını optimize etmek
->Mikroservis mimarisini desteklemek

Docker konteynerleri, işletim sistemi çekirdeğini paylaşır ancak birbirlerinden izole şekilde çalışırlar. Bu yapı sayesinde sanal makinelere göre çok daha hafif ve hızlıdır.

##Container (Konteyner) Kavramı
Container, bir uygulamanın çalışması için gerekli olan tüm bileşenleri içeren izole yazılım paketidir.

Bir container içerisinde şunlar bulunabilir:
->Uygulama kodları
->Çalışma zamanı (runtime)
->Sistem araçları
->Kütüphaneler
->Bağımlılıklar
->Konfigürasyon dosyaları

Container mantığında uygulama işletim sisteminden bağımsız hale gelir.

##Docker’ın Çalışma Mantığı
Docker’ın çalışma mantığı temel olarak şu adımlardan oluşur:

1-Uygulama hazırlanır
2-Dockerfile oluşturulur
3-Image üretilir
4-Image üzerinden container çalıştırılır
5-Container izole ortamda uygulamayı çalıştırır

Bu yapı sayesinde uygulama her sistemde aynı davranışı gösterir.

##Docker Mimarisi

Docker mimarisi üç temel bileşenden oluşur:

1)Docker Client:
Kullanıcının Docker komutlarını yazdığı bölümdür.

2)Docker Daemon:
Docker’ın arka planda çalışan servisidir.

Görevleri:
->Image oluşturma
->Container çalıştırma
->Ağ yönetimi
->Volume yönetimi
->Kaynak kontrolü

Daemon tüm Docker işlemlerini yönetir.

3)Docker Registry:
Docker image’larının depolandığı merkezdir.

En yaygın registry:
Docker Hub

Buradan hazır image’lar indirilebilir.

Örnek:
->Ubuntu
->Nginx
->MySQL
->Redis
->Node.js

##Docker Image Nedir?
Docker Image, container oluşturmak için kullanılan şablondur.

Image:
->Salt okunurdur
->Katmanlı yapıdadır
->Tekrar kullanılabilir
->Hafif yapıdadır

Bir image çalıştırıldığında container oluşur.

##Docker Container Nedir?
Container, image’ın çalışan halidir.

Özellikleri:
->İzole ortam
->Hızlı başlatma
->Düşük kaynak tüketimi
->Taşınabilirlik
->Esnek yapı

Bir sistemde aynı anda yüzlerce container çalışabilir.

##Dockerfile Nedir?
Dockerfile, image oluşturmak için kullanılan metin dosyasıdır.

Bu dosya:
->Python ortamı oluşturur
->Dosyaları kopyalar
->Paketleri yükler
->Uygulamayı çalıştırır

##Docker’ın Katmanlı Yapısı
Docker image’ları katmanlardan oluşur.
Her komut ayrı katman üretir.

Örneğin:
->Ubuntu tabanı
->Güncelleme katmanı
->Nginx kurulumu
->Dosya kopyalama

ayrı katmanlardır.

Avantajları:
->Hızlı build
->Cache kullanımı
->Az disk kullanımı





10. Docker ve Sanal Makine Farkı
Özellik                                     	Docker	                              Sanal Makine
--------                                        --------                              ------------- 

Başlatma Süresi                              	Saniyeler	                          Dakikalar

Kaynak Kullanımı	                            Düşük	                              Yüksek

Boyut	                                        MB seviyesinde	                      GB seviyesinde

Performans	                                    Daha hızlı	                          Daha yavaş

İşletim Sistemi	                                Ortak kernel	                      Ayrı işletim sistemi


##Docker’ın Avantajları
1)Taşınabilirlik
Her ortamda aynı şekilde çalışır.

2)Hızlı Deployment
Uygulama hızlı dağıtılır.

3)Kaynak Verimliliği
Az RAM ve CPU kullanır.

4)Ölçeklenebilirlik
Birden fazla container kolayca yönetilebilir.

5)İzolasyon
Her uygulama bağımsız çalışır.

6)Mikroservis Desteği
Modern yazılım mimarileri için uygundur.

##Docker Network Yapısı
Docker container’ları ağ üzerinden haberleşebilir.

Ağ türleri:
1-Bridge Network
Varsayılan ağdır.

2-Host Network
Doğrudan host ağı kullanılır.

3-Overlay Network
Birden fazla sunucu arasında iletişim sağlar.

4-None Network
Ağ bağlantısı kapalıdır.

##Docker Volume Yapısı
Container’lar silindiğinde veriler kaybolabilir.
Bunu önlemek için volume kullanılır.

Avantajları:
->Veri kalıcılığı
->Yedekleme kolaylığı
->Paylaşımlı kullanım

##Docker Compose
Docker Compose, birden fazla container’ı tek dosya ile yönetmeye yarar.

Avantajları:
->Kolay yönetim
->Çoklu servis desteği
->Tek komutla çalıştırma

##Docker Kullanım Alanları
Docker birçok alanda kullanılmaktadır.

1)Web Uygulamaları
Node.js
PHP
Django
Spring Boot

2)Mikroservis Sistemleri
Servis bazlı mimarilerde yaygın kullanılır.

3)DevOps Süreçleri
CI/CD sistemlerinde kullanılır.

4)Test Ortamları
Standart test ortamı sağlar.

5)Bulut Sistemleri
Cloud-native mimarilerde temel teknolojidir.

##Docker Güvenliği
Container izolasyonu güvenlik sağlar ancak bazı riskler bulunmaktadır.

Dikkat edilmesi gerekenler:
->Root kullanıcı kullanmamak
->Güvenilir image kullanmak
->Gereksiz port açmamak
->Güncel image kullanmak
->Secret yönetimi yapmak

##Docker ve Kubernetes İlişkisi
Kubernetes, container orkestrasyon platformudur.
Docker container üretir.

Kubernetes ise:
->Container yönetir
->Ölçeklendirir
->Otomatik dağıtır
->Yük dengelemesi yapar

Büyük sistemlerde birlikte kullanılır.

##Gerçek Hayat Senaryosu
Bir e-ticaret sistemi düşünelim:

Sistem bileşenleri:
->Frontend
->Backend API
->MySQL
->Redis

Her servis ayrı container olarak çalıştırılır.

Avantajlar:
->Bağımsız geliştirme
->Kolay güncelleme
->Hızlı deployment
->Yüksek ölçeklenebilirlik

##Docker’ın Yazılım Geliştirmeye Etkisi
Docker yazılım geliştirme süreçlerini büyük ölçüde değiştirmiştir.

Sağladığı katkılar:
->Standart ortam
->Hızlı test
->Kolay paylaşım
->DevOps uyumu
->Sürekli entegrasyon

Modern yazılım dünyasında önemli bir yere sahiptir.

##Docker’ın Dezavantajları
Her teknolojide olduğu gibi Docker’ın da bazı dezavantajları vardır.

>Öğrenme eğrisi
>Güvenlik riskleri
>Karmaşık network yapıları
>Persistent veri yönetimi
>Büyük sistemlerde orchestration ihtiyacı