Görüntü İşleme ve Derin Öğrenme Modeli: Hayvan Sınıflandırma
Bu proje, görüntü işleme ve derin öğrenme teknikleriyle hayvan sınıflandırması yapmak amacıyla geliştirilmiştir. Proje, aşağıdaki adımları içerir:

İçerik
Veri Seti Hazırlığı
Veri Ön İşleme ve Normalizasyon
Eğitim ve Test Verisi Bölünmesi
Derin Öğrenme Modeli (CNN) Oluşturma
Veri Artırma (Data Augmentation)
Model Eğitimi
Model Değerlendirme
Test Sonuçları ve Grafikler
Görüntü Manipülasyonu ve Beyaz Dengeleme
Kullanılan Teknolojiler
Python 3.x
OpenCV (Görüntü işleme)
TensorFlow ve Keras (Derin öğrenme)
NumPy (Sayısal hesaplamalar)
Matplotlib (Grafikler)
Scikit-learn (Veri bölme)
1. Veri Seti Hazırlığı
Proje, belirli bir dizindeki hayvan görüntülerini işlemek için aşağıdaki sınıflarda etiketlenmiş veriler kullanır:

collie
dolphin
elephant
fox
moose
rabbit
sheep
squirrel
giant+panda
polar+bear
Veri kümesinin bulunduğu dizin (dataset_path) ve çıktının kaydedileceği klasör (output_path) belirtilmiştir. Eğer çıktı klasörü mevcut değilse, yeni bir klasör oluşturulur.

2. Veri Ön İşleme ve Normalizasyon
Görüntüler, her bir sınıf için aşağıdaki işlemlerden geçirilir:

Görüntülerin boyutları 128x128 piksel olarak yeniden boyutlandırılır.
Görüntüler 0 ile 1 arasında normalize edilir.
3. Eğitim ve Test Verisi Bölünmesi
İşlenen veriler, eğitim ve test setlerine ayrılır:

Eğitim verisi: %70
Test verisi: %30
Veriler, train_test_split fonksiyonu kullanılarak rastgele ayrılır.

4. Derin Öğrenme Modeli (CNN) Oluşturma
Bir Convolutional Neural Network (CNN) modeli oluşturulmuştur:

Conv2D ve MaxPooling2D katmanları ile temel özellik çıkarımı yapılır.
Dense katmanları ile tam bağlı sınıflandırma yapılır.
Dropout katmanı ile aşırı öğrenme (overfitting) engellenir.
5. Veri Artırma (Data Augmentation)
Eğitim seti için veri artırma işlemi yapılır:

Görüntüler, rastgele dönüşümlerle (dönme, kaydırma, yatay çevirme) zenginleştirilir.
6. Model Eğitimi
Model, 20 epoch boyunca eğitim verisi ile eğitilir. Eğitim sürecinde doğruluk (accuracy) ve kayıp (loss) izlenir.

7. Model Değerlendirme
Model, test verisi ve manipüle edilmiş test verisi ile değerlendirilir:

Test doğruluğu ve kaybı hesaplanır.
Eğitim ve test doğruluğu ile kayıp grafiklerle gösterilir.
8. Test Sonuçları ve Grafikler
Eğitim sürecinin doğruluğu ve kaybı, eğitim ve test sonuçları çizgisel grafiklerle gösterilir.

9. Görüntü Manipülasyonu ve Beyaz Dengeleme
Test seti üzerindeki görüntüler, farklı ışık kaynakları (mor, sarı, yeşil) altında manipüle edilerek modelin genel performansı değerlendirilir. Ayrıca, görüntülerin beyaz dengesi ayarlanarak daha doğru sonuçlar elde edilmesi sağlanır.

Grafikler:
Eğitim ve test doğruluğu grafiklerinin yanı sıra, manipüle edilmiş test verisinin doğruluğu ve kaybı da çizilmektedir.