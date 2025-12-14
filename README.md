# 💡 Kombine Çevrim Enerji Santrali (CCPP) Performans Analizi ve Tahmini

Bu depo, dört temel atmosferik koşul (Sıcaklık, Vakum, Basınç, Nem) kullanarak bir Kombine Çevrim Enerji Santrali'nin **Net Elektrik Çıkışını (PE)** tahmin eden bir Doğrusal Regresyon modelinin geliştirilmesini içerir. Proje, veri bilimindeki temel adımları (Ön İşleme, Keşifçi Analiz ve Modelleme) kapsamaktadır.

## 👥 Takım ve Görev Dağılımı

Bu proje, aşağıdaki görev dağılımı ile işbirliği içinde tamamlanmıştır:

| Üye Adı | Görev Alanı | Açıklama |
| :--- | :--- | :--- |
| **Dilruba** | Pandas ve NumPy (Veri Ön İşleme) | Veri temizliği, özellik mühendisliği (kategorik değişkenler) ve ölçekleme. |
| **Buse** | Grafikler (EDA) | Dağılım, korelasyon ve değişkenler arası ilişki görselleştirmeleri. |
| **Aleyna** | Makine Öğrenmesi | Doğrusal Regresyon modelinin kurulması, eğitilmesi ve metriklerle değerlendirilmesi. |
| **İrem** | Yorumlama Satırları | Projenin tamamına açıklayıcı yorum satırları ekleyerek kod anlaşılırlığını sağlama. |

## 📁 Proje Dosyaları

* **`CCPP_Analysis.ipynb`**: Projenin tamamını içeren ana Jupyter Notebook dosyasıdır (Bu depodaki tüm kod bu dosyadadır).
* **`CCPP_data.csv`**: Kullanılan orijinal ham veri seti.
* **`README.md`**: Bu açıklama dosyası.

## 🛠️ Analiz Akışı ve Kullanılan Yöntemler

### 1. Veri Ön İşleme (Dilruba)
* **Kategorik Özellik Üretimi:** Ortam Sıcaklığı (`AT`) ve Basınç (`AP`) verilerinden yeni kategori seviyeleri (`Low`, `High`, vb.) oluşturulmuştur.
* **Normalizasyon:** Model eğitimine hazırlık için sayısal sütunlara Min-Max Normalizasyonu uygulanmıştır.

### 2. Keşifçi Veri Analizi (Buse)
* **Korelasyon:** Net Elektrik Çıkışı (`PE`) ile özellikler (`AT`, `V`) arasında güçlü **negatif** ilişkiler gözlemlenmiştir. 
* **Dağılım:** Tüm değişkenlerin dağılımı Histogram ve Kutu Grafikleriyle incelenmiştir.

### 3. Modelleme (Aleyna)
* **Model:** Regresyon görevi için **Doğrusal Regresyon (Linear Regression)** modeli seçilmiştir.
* **Performans:** Model, %80 Eğitim / %20 Test ayrımı yapılarak eğitilmiş ve aşağıdaki metriklerle başarılı bulunmuştur:
    * **R² Skoru:** Yaklaşık 0.92 (Model, verideki varyansın %92'sini açıklayabilmektedir).
    * **RMSE:** Düşük bir hata payı ile tahminlerin başarılı olduğu görülmüştür.

### 🚀 Nasıl Çalıştırılır?

1.  Bu depoyu bilgisayarınıza **clone** yapın veya **zip** olarak indirin.
2.  `CCPP_data.csv` dosyasının, `CCPP_Analysis.ipynb` dosyasıyla aynı klasörde olduğundan emin olun.
3.  Anaconda Navigator veya Visual Studio Code üzerinden **`CCPP_Analysis.ipynb`** dosyasını açın.
4.  Dosyadaki tüm hücreleri sırasıyla (Yukarıdan aşağıya) çalıştırın.
