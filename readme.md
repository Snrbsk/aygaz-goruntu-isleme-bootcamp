<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Proje README</title>
    <style>
        /* Başlıkların boyutlarını ayarlıyoruz */
        h1 {
            font-size: 36px; /* Büyük başlık */
        }

        h2 {
            font-size: 30px; /* Orta büyüklükte başlık */
        }

        h3 {
            font-size: 24px; /* Küçük başlık */
        }

        /* Paragrafların boyutunu ayarlıyoruz */
        p {
            font-size: 16px; /* Normal yazı boyutu */
        }

        /* Liste elemanlarının boyutunu ayarlıyoruz */
        ul {
            font-size: 16px; /* Normal yazı boyutu */
        }

        /* Diğer metinler için boyut */
        .small-text {
            font-size: 12px; /* Küçük yazı */
        }
    </style>
</head>
<body>

<h1>Proje Başlığı</h1>
<p>Bu proje, belirli hayvan türlerini sınıflandırmak için görüntü işleme ve derin öğrenme (CNN) kullanır. Aşağıda, projenin ana adımlarına dair açıklamalar yer almaktadır.</p>

<h2>1. Veri Hazırlığı ve İşleme</h2>
<p>Görüntü verisi belirli sınıflara ayrılır ve işlenir. Resimler yeniden boyutlandırılır, normalleştirilir ve kaydedilir.</p>

<h3>Python Kod Örneği:</h3>
<pre>
<code>
import os
import cv2
import numpy as np

# Dataset yolu
dataset_path = '/path/to/dataset'

# Veri işleme fonksiyonu
def load_and_process_image(image_path):
    img = cv2.imread(image_path)
    img_resized = cv2.resize(img, (224, 224))  # Görüntüyü yeniden boyutlandır
    img_normalized = img_resized / 255.0  # Görüntüyü normalleştir
    return img_normalized
</code>
</pre>

<h2>2. Modelin Eğitilmesi</h2>
<p>Veri seti hazırlandıktan sonra, derin öğrenme modelinin eğitilmesi için çeşitli algoritmalar kullanılır. Bu süreç, modelin doğruluğunu artırmak için optimize edilir.</p>

<h3>Model Kod Örneği:</h3>
<pre>
<code>
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense, Conv2D, Flatten, MaxPooling2D

# Modeli oluşturma
model = Sequential([
    Conv2D(32, (3, 3), activation='relu', input_shape=(224, 224, 3)),
    MaxPooling2D(pool_size=(2, 2)),
    Flatten(),
    Dense(128, activation='relu'),
    Dense(3, activation='softmax')  # 3 sınıf için çıkış
])

# Modeli derleme
model.compile(optimizer='adam', loss='categorical_crossentropy', metrics=['accuracy'])
</code>
</pre>

<h2>3. Modelin Değerlendirilmesi</h2>
<p>Model eğitildikten sonra, doğruluk oranı ve kayıp değeri gibi metrikler üzerinden model değerlendirilir.</p>

<p class="small-text">Bu küçük metin, daha az dikkat çekici olabilir.</p>

</body>
</html>
