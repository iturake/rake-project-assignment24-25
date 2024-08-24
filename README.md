<p align="center">
  <img src="https://rake.itu.edu.tr/static/img/logo_footer.png" width="350" title="İTÜ Robotik Arama Kurtarma Ekibi">
</p>

# rake-project-assignment24-25

## ROS Turtlesim Proje Ödevi
**ödev konusu**: Bu ödev aşamasında sizden ROS temel elemanlarını kullanarak basit bir turtle-sim uygulaması yapmanız istenmektedir. turtle-sim i kullanarak periyodik olarak 2 boyutlu düzlem üzerinde istenilen noktalarda çıkan diğer turtle'ları yakalayan bir uygulama yapacaksınız.

## Ödevi Yaparken kullanacağınız ROS araçları
- ROS Service
- ROS Publisher / Subscriber
- ROS Parameter Server
- ROS launch files
- ROS launch file arguments
- ROS turtlesim package
    - turtlesim-node
    - turtlesim-services
- ROS topics
  - pose
  - cmd_vel

## Ödev Yapılırken Dikkat Edilmesi Gerekenler
- Örnek videoda da göreceğiniz üzere uygulama bir launch file a verilen, turtle'ın yakalayacağı turtle'ların spawn edileceği noktaların x ve y koordinatlarını belirten "coordinates" argumanı ile çalışıyor. Ödevinizde bulunan sadece bu dosyanın çalıştırılması ile başlamalıdır. Uygulamayı çalıştırmak için birden çok dosya kullanmayınız.
- Uygulama, verilen koordinatlar için kontroller yapmalı ve bu kontroller sonucunda gerekiyorsa bir hata mesajı verip uygulamayı çalışmadan sonlandırmalıdır. Bu kontrollere örnek olarak:
    1. Verilen koordinatlar bir dizi üzerinden x ve y koordinatlarını belirttiğinden eleman sayısı çift olmalıdır.
    2. Uygulama, turtle'ın spawnlandığı koordinat düzleminin sınırları dışında verilen koordinatları kabul etmemelidir. Bu sınırları bulmak size bırakılmıştır.
    3. Uygulama sadece float ve int tipinde verilen koordinatları kabul etmelidir. Diğer değişken tipleri için hata mesajı vermelidir.
    verilebilir.
- Ödevi yaparken python veya cpp ROS node ları kullanabilirsiniz. Ödevinizin doğru çözümü vermesi yeterlidir.
- Ödevi OOP(Object-oriented Programming) kullanarak yapmanız gerekmektedir. Robotik problemlerini OOP kullanarak çözme becerinizi ölçmek, bu ödevin amaçlarından bir tanesidir.
- ilk spawnlanan turtle; diğer turtle'lara doğrusal olarak değil, p-kontrol algoritmasını kullanarak gitmektedir. Bundan dolayı videoda da göreceğiniz üzere ilk turtle, hedef turtle'a bir eğriyi takip ederek gitmektedir.
  - Kullanılan algoritma 2 tane p-kontrol sistemi içermektedir.
      1. Hedef turtle'a olan mesafe(euclidian distance) ile ters orantılı olarak hız büyüklüğü ayarlanmaktadır.
      2. İlk turtle'ın yön vectörü ile ilk turtle'ın bulunduğu noktadan hedef noktaya giden vektörün arasındaki açıya göre açısal hız büyüklüğü ayarlanmaktadır.
