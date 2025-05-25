# 🎮 Video Game Sales Prediction

Bu repo, video oyunları satış verilerinin analiz edilerek satış eğilimlerinin ve oyun performanslarının incelendiği bir veri analizi projesini içermektedir. Analiz kapsamında kullanılan veri seti, dünya çapındaki çeşitli platformlar üzerinde yayınlanan oyunların satış rakamlarını içermektedir.

---

## 📥 Giriş

Bu proje kapsamında kullanılan veri seti; oyun adı, platform, yıl, tür, yayıncı, 
bölgesel satışlar ve küresel satışlar gibi bilgileri içeren toplam 11 sütundan oluşmaktadır. 
Analizde; veri temizleme, ön işleme, betimleyici istatistikler ve görselleştirme yöntemleri kullanılarak oyun satış verileri üzerine içgörüler elde edilmiştir.

Notebook dosyasının içerisinde tüm analizler ayrıntılı olarak markdown hücreleriyle açıklanmıştır.

Projede kullanılan veri seti [Kaggle - Video Game Sales](https://www.kaggle.com/datasets/gregorut/videogame-sales-with-ratings) üzerinden alınmıştır.

- Veri 16.000+ oyun kaydı içermektedir.
- Hedef: `Global_Sales` üzerinden regresyon, ayrıca `High_Sales` etiketiyle sınıflandırma yapılmıştır.
- Kullanılan algoritmalar:
  - **Linear Regression**
  - **Random Forest Classifier**
- Kategorik değişkenler `OneHotEncoder` ile dönüştürülmüştür.
- Başarılı oyun etiketi `Log(Global_Sales)` değerinin medyanına göre oluşturulmuştur.

---

## 📊 Metrikler

### 🔵 Regresyon (Global Sales Tahmini):
(NA + EU satışları ile tahmin)

| Metrik       | Değer  |
| ------------ | ------ |
| **R² Skoru** | 0.9608 |
| **MAE**      | 0.1161 |
| **MSE**      | 0.0842 |
| **RMSE**     | 0.2901 |

------------------------------------------------------
### 🔵 Random Forest Classifier

Model, oyunları yüksek satışlı mı (başarılı) yoksa değil mi (başarısız) olarak sınıflandırmak için Random Forest Classifier kullanmıştır. Burada başarı tanımı, oyunun logaritmik satış değeri (Log(Global_Sales)) medyanın üstündeyse "başarılı" kabul edilmesiyle belirlenmiştir.

Accuracy (Doğruluk): 0.71
Model, tüm oyunlar arasında %71 oranında doğru tahmin yapmıştır.

Precision (Kesinlik): 0.70
Modelin “bu oyun başarılı” dediği oyunların %70’i gerçekten başarılı çıktı.

Recall (Duyarlılık): 0.75
Gerçekten başarılı olan oyunların %75’i model tarafından doğru şekilde tespit edildi.

F1-score: 0.72
Precision ve Recall'un dengeli bir ortalaması. Modelin genel sınıflandırma yeteneği açısından güçlü bir skordur.

Bu sonuçlara göre model, özellikle başarılı oyunları tanıma konusunda güçlü bir performans sergilemiştir. Başarı tahmininde en etkili faktörler; oyun türü (Genre), yayıncı (Publisher) ve platform (Platform) olmuştur.

### Ek 
Ek olarak bu çalışma dışında, oyun türleri ve platformlar bazında daha detaylı segmentasyon yapılarak hedef kitle analizleri gerçekleştirilebilir.

### Kaggle

[Projenin Kaggle Linki](https://www.kaggle.com/code/alpkavas/videogame-reg-classification)

--------------------------------------

[Kaggle DataSet Link(videogamesales)](https://www.kaggle.com/datasets/gregorut/videogamesales)

