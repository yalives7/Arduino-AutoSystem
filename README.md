# 🚗 Araç İçi Güvenlik ve Konfor Sistemi

Bu proje, **Arduino Mega 2560** ve **Proteus** simülasyon ortamı kullanılarak oluşturulmuş, araç içi güvenlik ve konfor sistemlerini temel alan bir mikrodenetleyici projesidir.  
Sensör verilerini okuyarak karar mekanizmalarıyla çeşitli güvenlik önlemleri ve konfor sistemlerini kontrol eder.

---

## 📚 Proje Bilgileri

- **Eğitim Seviyesi:** Lisans – Bilgisayar Mühendisliği Öğrencisi 2.sınıf
- **Odak Noktası:** Gömülü Sistem Tasarımı, Arduino Programlama, Simülasyon  
- **Simülasyon Ortamı:** Proteus  
- **Kodlama Dili:** Arduino C++  
- **Teslim Tarihi:** 27.04.2025

---

## 🧭 Projenin Kazanımları

- Mikrodenetleyici (Arduino Mega) ile sensör okuma ve karar mekanizması geliştirme  
- Gerçek zamanlı LCD ekran güncelleme  
- Giriş ve çıkış birimleriyle olay-tabanlı sistem kurma  
- Proteus ortamında sistem modelleme ve test etme  
- Modüler yazılım mimarisi tasarlama  

Bu proje, gerçek hayatta bir otomobilde bulunabilecek temel sistemleri anlamayı ve uygulamayı amaçlar:  
**Kemer kontrolü, kapı durumu, farlar, sıcaklık-temelli klima, yakıt seviyesi** gibi özellikler yazılım tabanlı şekilde kontrol edilmektedir.

---

## 🔧 Proteus - Arduino Kütüphanesi Ekleme Talimatı

### 1. Proteus'u Kurma  
Proteus yazılımının resmi web sitesine gidin:  
[https://www.labcenter.com/](https://www.labcenter.com/)  
Ücretsiz deneme sürümünü veya satın alma seçeneklerini inceleyin.

### 2. Arduino Kütüphane Dosyaları  
Arduino Mega 2560 kartını eklemek için gereken dosyalar:  
- `ArduinoMega25602TEP.LIB`  
- `ArduinoMega25602TEP.IDX`

### 3. Kütüphane Dosyalarını Nereye Ekleyeceğiz?  
Bu dosyaları, Proteus’un kurulu olduğu dizindeki `LIBRARY` klasörüne kopyalayın.  
**Örnek klasör yolu:**  
C:\ProgramData\Labcenter Electronics\Proteus 8 Professional\LIBRARY

*Eğer farklı bir klasöre kuruluysa, Proteus klasöründeki `LIBRARY` klasörünü bulun.*

### 4. Kurulum Adımları  
- `.LIB` ve `.IDX` dosyalarını kopyalayın.  
- `LIBRARY` klasörünü açın ve dosyaları yapıştırın (Yönetici izni gerekebilir).  
- Proteus'u açın → `Component Mode` (P tuşu) → `Arduino Mega 2560` arayın.  
- Yeni Arduino modeli listede görünmelidir.

### 5. Test Etme  
Kütüphane başarıyla eklendiyse:  
Proteus içinde “Pick Devices” ekranından `Arduino Mega 2560` arayın → model görünür.  
Devreye ekleyip kullanabilirsiniz.

---

## 🔩 Arduino 2560 V2 Kullanılan Devre Elemanları

### Giriş (Input) Bileşenleri
- Motor Butonu – Aracı başlatma  
- Emniyet Kemeri Switch – Kemer takılı mı kontrolü  
- LM35 Sıcaklık Sensörü – Sıcaklık ölçümü  
- LDR (Işık Sensörü) – Ortam ışığı kontrolü  
- Potansiyometre – Yakıt seviyesi simülasyonu  
- Kapı Anahtarı – Kapı açık/kapalı kontrolü  

### Çıkış (Output) Bileşenleri
- LCD (16x2) – Bilgi ekranı  
- Kırmızı LED – Emniyet kemeri uyarısı  
- Mavi LED – Far durumu  
- Sarı LED – Yakıt uyarısı  
- RGB LED (Pembe) – Kapı açık uyarısı  
- Buzzer – Sesli uyarı  
- DC Motor – Motor & klima simülasyonu  

---

## 🔄 Projenin Devamında

- Kurulumlar tamamlandıktan sonra Arduino IDE üzerinden gerekli kodlar yazılır.  
  (Arduino klasöründeki `main.ino` dosyasında kaynak kodları bulabilirsiniz)  
- Yazılan kod Proteus içinde HEX dosyası olarak kullanılır.  
- Devre şeması Proteus'ta hazırlanır.  
- Simülasyon çalıştırılarak test yapılır.

---

## 🧪 Simülasyon ve Test Senaryoları

- **Kapı Açık:** Kapı switch LOW konumuna geçtiğinde RGB LED yanar, motor devre dışı bırakılır.  
- **Kemer Takılı Değil:** Kemer switch HIGH konumdaysa kırmızı LED yanar, buzzer çalışır ve LCD uyarı mesajı gösterir.  
- **Düşük Işık:** LDR değeri 250 veya altındaysa mavi LED yanar ve LCD'de bilgi mesajı gösterilir.  
- **Yüksek Sıcaklık:** 25°C üzerindeyse fan motoru devreye girer ve LCD güncellenir.  
- **Düşük Yakıt:** %10'un altına düştüğünde sarı LED yanar, LCD yakıt uyarısı gösterir.  
- **Çok Düşük Yakıt:** %5’in altına düştüğünde sarı LED yanıp sönmeye başlar.  
- **Yakıt Bitti:** Potansiyometre değeri 0 ise motor durdurulur, LCD'de "Yakıt Bitti" mesajı gösterilir.

---

## 📄 Akademik Bağlam ve Detaylı Rapor

Bu proje, Bilgisayar Mühendisliği – Prolab II dersi kapsamında geliştirilmiştir.
📁 docs/prolab2.proje pdfe bak
Proje; sistem tasarımı, sensör entegrasyonu, karar mekanizmaları, simülasyon testleri ve modüler yazılım geliştirme gibi becerileri geliştirmek amacıyla hazırlanmıştır.

📘 Detaylı teknik bilgiler, algoritmalar, karar tabloları, test senaryoları ve gelişim süreci gibi tüm içerikler aşağıdaki dökümanda yer almaktadır:
📁 docs/report.pdf — Geliştirme sürecine ve teknik detaylara kapsamlı bir bakış

Bu rapor, projenin nasıl planlandığını, hangi ihtiyaçlara cevap verdiğini ve nasıl geliştirildiğini görmek isteyenler için rehber niteliğindedir.

---

## 📂 Dosyalar ve İletişim

Hey, sen! Eğer projemi test etmek istiyorsan, `.pdsprj` ve `.ino` dosyalarımı bulabilirsin :)

---

![Proje Görseli](https://github.com/user-attachments/assets/dfcd8264-e4ef-4c02-a378-7f239c76e898)

---

**Teşekkürler!**


