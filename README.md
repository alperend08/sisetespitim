# 🧴 Şişe Tespiti (Bottle Detection) - OpenCV + PyQt5

Bu proje, **şişe tespiti ve sayımı** yapmak için geliştirilmiş bir **OpenCV + PyQt5** tabanlı görsel arayüz (GUI) uygulamasıdır.  
Kullanıcı, `.png` veya `.jpg` formatındaki görüntüleri seçerek sistemin **şişe ağızlarını otomatik tespit etmesini ve saymasını** sağlar.  
Uygulama, görüntü işleme teknikleriyle çalışır — yapay zeka modeli gerektirmez.

---

## 🎯 Amaç

Endüstriyel üretim hatlarında, depo görüntülerinde veya laboratuvar deneylerinde şişe gibi silindirik nesnelerin sayısını **otomatik ve doğru şekilde belirlemek**.  
Elle sayım hatalarını ortadan kaldırır, hız ve doğruluk sağlar.

---

## 🧠 Temel Özellikler

- 📂 Klasörden görüntü seçme (tek tek veya toplu)
- 🧮 Şişe sayısını otomatik tespit etme  
- 🔲 Her şişeyi yeşil kutularla işaretleme  
- 📋 Sonuçları arayüzde anlık görüntüleme  
- 🪟 PyQt5 arayüzü ile kolay kullanım  

---

## ⚙️ Kullanılan Teknolojiler

| Teknoloji | Açıklama |
|------------|-----------|
| **Python 3.12+** | Temel dil |
| **OpenCV (cv2)** | Görüntü işleme, Hough Dairesel Algılama |
| **NumPy** | Sayısal hesaplama |
| **PyQt5** | Arayüz tasarımı |
| **JSON** | Kalibrasyon dosyası kaydı |

---

## 📁 Proje Yapısı

sisetespitim/
│
├── images/ → Girdi görüntüleri
├── calib_preview/ → Kalibrasyon sonuçlarının kaydedildiği klasör
├── bottle_hough_config.json → Hough parametrelerinin kaydedildiği ayar dosyası
├── sise_tespit.py → Ana GUI uygulaması (PyQt5 + OpenCV)
├── train_calibrate.py → Görüntü kalibrasyon (Hough parametre ayarı)
└── README.md
3️⃣ Kullanım

“📂 Görsel Seç” butonuna tıklayarak bir .png veya .jpg görüntü seç.

“Şişeleri Say” butonuna bastığında sistem otomatik olarak görüntüdeki şişe ağızlarını algılar.

“Şişeleri İşaretle” butonuna bastığında tespit edilen şişeler yeşil kutularla işaretlenir.

Sağ tarafta toplam şişe sayısı görüntülenir.

🧩 Teknik Açıklama

Algoritma, Hough Circle Transform (Dairesel Dönüşüm) yöntemiyle çalışır:

Görüntü gri tonlamaya çevrilir.

Gürültü azaltmak için Gaussian Blur uygulanır.

Kenar tespiti (Canny) yapılır.

cv2.HoughCircles() fonksiyonu ile dairesel şekiller (şişe ağızları) bulunur.

Her daire koordinatları kaydedilir ve yeşil çemberle çizilir.

Tespit edilen daire sayısı şişe adedi olarak ekranda gösterilir.

📊 Kalibrasyon

Tespit hassasiyetini artırmak için train_calibrate.py script’i kullanılır.
Bu script, images.zip içindeki örnek görselleri tarayarak bottle_hough_config.json dosyasını oluşturur.
Parametreler (ör. dp, minDist, param1, param2, minRadius, maxRadius) otomatik optimize edilir.

🧪 Örnek Çıktı
Görsel: bottles_03.png
Toplam Tespit: 21 şişe

[✔️ Her şişe ağız kısmı yeşil çember ile işaretlenmiş şekilde görüntülenir]

🔮 Gelecek Geliştirmeler

🎥 Gerçek zamanlı kamera akışında şişe tespiti

💾 JSON yerine SQLite tabanlı veri kaydı

🧠 Derin öğrenme tabanlı tespit (YOLO veya DETR entegrasyonu)

📈 Tespit başarı oranı istatistik ekranı

👨‍💻 Geliştirici

Alperen D
💡 Görüntü İşleme • Yapay Zeka • Otomasyon Sistemleri
