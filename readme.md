<div>
    <h1>Görüntü İşleme ve Sınıflandırma Projesi</h1>
        <p>Bu proje, görüntü işleme teknikleri ve derin öğrenme kullanarak çeşitli hayvan sınıflarını sınıflandırmak için geliştirilmiştir. Proje, bir dizi hayvan görüntüsünü işleyip sınıflandırma modelini eğitmek amacıyla çeşitli adımları içerir. Ayrıca, modelin test ve doğruluk analizleri de yapılmaktadır.</p>
    <h3>Proje Adımları</h3>
        <ol>
            <li>
                <h4>Veri İşleme</h4>
                <p><strong>Veri Yolu (Dataset Path):</strong> Proje, hayvan sınıflarını içeren bir veri seti ile çalışmaktadır. Bu veri seti, her bir hayvan türü için farklı görüntüler içermektedir.</p>
                <p><strong>Veri Sınıfları:</strong> Proje, aşağıdaki hayvan türlerini içeren sınıflara sahiptir:</p>
                <ul>
                    <li>Collie</li>
                    <li>Dolphin</li>
                    <li>Elephant</li>
                    <li>Fox</li>
                    <li>Moose</li>
                    <li>Rabbit</li>
                    <li>Sheep</li>
                    <li>Squirrel</li>
                    <li>Giant Panda</li>
                    <li>Polar Bear</li>
                </ul>
                <p><strong>Veri Ön İşleme:</strong> Görüntüler, boyutları 128x128 piksele küçültülerek normalleştirilir. Ayrıca, her bir sınıf için 650 görüntü seçilir ve işlenmiş görüntüler <code>processed_animals</code> klasörüne kaydedilir.</p>
            </li>
            <li>
                <h4>Eğitim ve Test Verisinin Bölünmesi</h4>
                <p>Veri seti, eğitim ve test verilerine ayrılır:</p>
                <ul>
                    <li>Eğitim Verisi: %70</li>
                    <li>Test Verisi: %30</li>
                </ul>
                <p>Bu veri, modelin eğitiminde ve doğruluk analizinde kullanılır.</p>
            </li>
            <li>
                <h4>Derin Öğrenme Modeli</h4>
                <p><strong>Model Yapısı:</strong> Konvolüsyonel Sinir Ağı (CNN) kullanılarak bir sınıflandırma modeli oluşturulmuştur. Modelin katmanları şunlardır:</p>
                <ul>
                    <li>Konvolüsyonel katman (Conv2D)</li>
                    <li>Havuzlama katmanı (MaxPooling2D)</li>
                    <li>Tam bağlı katman (Dense)</li>
                    <li>Dropout katmanı</li>
                </ul>
                <p><strong>Model Derleme:</strong> Model, 'adam' optimizasyon algoritması ile derlenmiş ve <code>sparse_categorical_crossentropy</code> kayıp fonksiyonu ile eğitilmiştir.</p>
            </li>
            <li>
                <h4>Veri Artırma</h4>
                <p>Modelin daha iyi genelleme yapabilmesi için veri artırma (data augmentation) teknikleri uygulanmıştır:</p>
                <ul>
                    <li>Görüntüde döndürme, kaydırma ve yatay çevirme gibi işlemler yapılmıştır.</li>
                </ul>
            </li>
            <li>
                <h4>Modelin Eğitimi</h4>
                <p>Model, 20 epoch boyunca eğitilmiş ve her bir epoch için eğitim ve doğrulama doğrulukları (accuracy) ile kayıp (loss) değerleri izlenmiştir.</p>
            </li>
            <li>
                <h4>Test ve Değerlendirme</h4>
                <p>Model, test verisi üzerinde değerlendirilmiş ve doğruluk (accuracy) değeri hesaplanmıştır. Ayrıca, eğitim sürecinde elde edilen doğruluk ve kayıp grafiklerinin yanı sıra, test verisi sonuçları da görselleştirilmiştir.</p>
            </li>
            <li>
                <h4>Işık Manipülasyonu ve Beyaz Dengesi</h4>
                <p>Modelin genel doğruluğunu artırmak için, test verileri üzerinde ışık kaynakları manipülasyonu ve beyaz dengesi ayarlamaları yapılmıştır:</p>
                <ul>
                    <li><strong>Işık Manipülasyonu:</strong> Farklı ışık kaynakları (morumsu, sarımsı, yeşilimsi) ile görüntüler manipüle edilmiştir.</li>
                    <li><strong>Beyaz Dengesi:</strong> Görüntülerde beyaz dengesi ayarları yapılmıştır.</li>
                </ul>
                <p>Manipüle edilmiş görüntülerle model tekrar test edilmiştir ve bu test sonuçları da görselleştirilmiştir.</p>
            </li>
        </ol>
        <h3>Gereksinimler</h3>
        <p>Projenin çalışabilmesi için aşağıdaki Python kütüphanelerine ihtiyacınız vardır:</p>
        <ul>
            <li><strong>tensorflow</strong> - Derin öğrenme modelinin eğitilmesi ve değerlendirilmesi için.</li>
            <li><strong>opencv-python</strong> - Görüntü işleme işlemleri için.</li>
            <li><strong>numpy</strong> - Sayısal hesaplamalar için.</li>
            <li><strong>matplotlib</strong> - Grafikler için.</li>
            <li><strong>sklearn</strong> - Eğitim ve test verilerinin bölünmesi için.</li>
        </ul>
    </div>
