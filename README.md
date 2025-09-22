🚗 Araç İçi Güvenlik ve Konfor Sistemi 

Bu proje, Arduino Mega 2560 ve Proteus simülasyon ortamı kullanılarak oluşturulmuş, araç içi güvenlik ve konfor sistemlerini temel alan bir mikrodenetleyici projesidir. Proje, sensör verilerini okuyarak karar mekanizmalarıyla çeşitli güvenlik önlemlerini ve konfor sistemlerini kontrol eder.

 📚 Eğitim Seviyesi: Lisans – Bilgisayar Mühendisliği (Programlama Lab II)  
 🧠 Odak Noktası: Gömülü Sistem Tasarımı, Arduino Programlama, Simülasyon  
 🧪 Simülasyon Ortamı: Proteus  
 🧱 Kodlama Dili: Arduino C++


🧭 Projenin Kazanımları

- Mikrodenetleyici (Arduino Mega) ile sensör okuma ve karar mekanizması geliştirme
- Gerçek zamanlı LCD ekran güncelleme
- Giriş ve çıkış birimleriyle olay-tabanlı sistem kurma (event-driven system)
- Proteus ortamında sistem modelleme ve test etme
- Modüler yazılım mimarisi tasarlama (fonksiyon bazlı ayrım)

Bu proje, gerçek hayatta bir otomobilde bulunabilecek temel sistemleri anlamayı ve uygulamayı amaçlar:  
Kemer kontrolü, kapı durumu, farlar, sıcaklık-temelli klima, yakıt seviyesi gibi özellikler yazılım tabanlı şekilde kontrol edilmiştir.


🔧 Proteus - Ardunio Kütüphanesi Ekleme Talimatı

📁 1. Proteus'u Kurma
Proteus klasörünü incele 
(zip sifresi klasörde mevcuttur)

📁 2. Arduino Kütüphane Dosyaları
Ardunio Kartını Eklemen için Gerekli( Ardunio 2560 V2.0)
ArduinoMega25602TEP.LIB
ArduinoMega25602TEP.IDX

Bu iki dosya, Proteus’un kütüphane dosyalarıdır.

📂 3. Kütüphane Dosyalarını Nereye Ekleyeceğiz?
Bu dosyaları, Proteus’un kurulu olduğu dizindeki LIBRARY klasörüne kopyalaman gerekiyor.
📌 Klasör yolu genellikle şöyle olur:
C:\ProgramData\Labcenter Electronics\Proteus 8 Professional\LIBRARY
Eğer farklı bir klasöre kurduysan, Proteus klasörünün içindeki LIBRARY klasörünü bul.

📥 4. Kurulum Adımları:
Verdiğim .LIB ve .IDX dosyalarını kopyala.
Yukarıdaki LIBRARY klasörünü aç.
Dosyaları buraya yapıştır (yönetici izni gerekebilir).
Proteus'u aç → Component Mode (P tuşu) → Arduino Mega 2560'u arat.
Yeni Arduino modeli listede görünmeli.

🧪 5. Test Etme
Kütüphane başarıyla eklendiyse:
Proteus içinde “Pick Devices” ekranından Arduino Mega 2560 yaz → yeni model görünür.
Devreye ekleyip kullanabilirsin.


🔩 Ardunio 2560 V2 Kullanılan Devre Elemanları

 Giriş (Input) Bileşenleri
 Motor Butonu - Aracı başlatma 
 Emniyet Kemeri Switch - Kemer takılı mı kontrolü 
 LM35 Sıcaklık Sensörü - Sıcaklık ölçümü 
 LDR (Işık Sensörü) - Ortam ışığı kontrolü 
 Potansiyometre - Yakıt seviyesi simülasyonu 
 Kapı Anahtarı - Kapı açık/kapalı kontrolü 

Çıkış (Output) Bileşenleri
 LCD (16x2) - Bilgi ekranı 
 Kırmızı LED - Emniyet kemeri uyarısı 
 Mavi LED - Far durumu 
 Sarı LED - Yakıt uyarısı 
 RGB LED (Pembe) - Kapı açık uyarısı 
 Buzzer - Sesli uyarı 
 DC Motor - Motor & klima simülasyonu 

 🔄 Projenin Devamında

Kurulumlar tamamlandıktan sonra:
Arduino IDE üzerinden gerekli kodlar yazılır.(Ardunio klasöründeki mai.ino da kaynak kodları bulabilirisin)
Yazılan kod Proteus içinde HEX dosyası olarak kullanılır.
Devre şeması Proteus'ta hazırlanır.

Simülasyon çalıştırılarak test yapılır.
🧪 Simülasyon ve Test Senaryoları
Projenin test edilmesi için aşağıdaki senaryolar uygulanabilir:
Kapı Açık durumunda, kapı switch'i LOW konumuna geçtiğinde RGB LED yanar ve motor devre dışı bırakılır.
Kemer Takılı Değil senaryosunda, kemer switch'i HIGH konumdaysa kırmızı LED yanar, buzzer çalışır ve LCD ekranda uyarı mesajı görüntülenir.
Ortamdaki ışık seviyesi düşükse (LDR değeri 250 veya altındaysa), farları temsil eden mavi LED yanar ve LCD'de bilgilendirici bir mesaj gösterilir.
Sıcaklık 25°C'nin üzerine çıktığında, fan motoru devreye girer ve LCD ekran güncellenir.
Yakıt seviyesi %10'un altına düştüğünde, potansiyometre verisine göre sarı LED yanar ve LCD ekranda yakıt uyarısı gösterilir.
Yakıt %5’in altına düştüğünde, sarı LED yanıp sönmeye başlar.
Yakıt tamamen bittiğinde (potansiyometre değeri 0), motor durdurulur ve LCD'de "Yakıt Bitti" mesajı gösterilir.


<img width="571" height="340" alt="image" src="https://github.com/user-attachments/assets/dfcd8264-e4ef-4c02-a378-7f239c76e898" />

