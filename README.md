# Kestirimci Bakım: İstatistiksel Rulman Titreşim Analizi

## Proje Amacı
Bu proje, endüstriyel sistemlerde kritik bir öneme sahip olan rulmanların (bearing) sağlık durumlarını istatistiksel yöntemlerle analiz etmeyi amaçlamaktadır. NASA Bearing Dataset kullanılarak, sağlam ve arızalı rulmanlara ait titreşim verileri incelenmiş ve zaman içindeki bozulma eğilimleri modellenmiştir.

## Veri Seti ve Ön İşleme
* **Veri Kaynağı:** NASA Bearing Dataset 
* **Özellikler:** "İşlenmiş titreşim özellikleri" kullanılmıştır. Analiz, `B1__rms` (1. Rulman RMS - Root Mean Square değeri) değişkeni üzerinden yürütülmüştür.
* **Büyük Veri (Big Data) Optimizasyonu:** Sağlam rulman veri seti yüz binlerce satırdan oluştuğu için, istatistiksel testlerin (Shapiro-Wilk) sistem sınırlarını (N=5000) aşmaması ve bellek optimizasyonu sağlamak adına veriden rastgele örneklem (random sampling) çekilerek hesaplama yapılmıştır.

## Metodoloji ve İstatistiksel Analiz
1. **Dağılım ve Normallik Analizi:** 
   * Sağlam ve bozuk rulman verilerinin dağılımlarını karşılaştırmak için **Shapiro-Wilk testi** ve **Q-Q Plot** grafikleri kullanılmıştır.
   * Sağlam rulman verisinin beklenen dağılımı sergilediği, bozuk rulman verisinin ise yapısal aşınmalar sebebiyle ideal dağılımdan saptığı görselleştirilmiştir.

2. **Doğrusal Regresyon (Linear Regression) ile Trend Modelleme:** 
   * Bozuk rulmanın zaman içerisindeki titreşim şiddeti değişimi modellenmiştir. 
   * Analiz sonucunda zaman ile RMS değeri arasında istatistiksel olarak son derece anlamlı (p < 2e-16) ve pozitif yönlü bir bozulma trendi tespit edilmiştir.

## Proje Çıktıları ve Görseller
Proje sonucunda elde edilen ve repoda yer alan grafikler:
* `saglam_rulman_qq.png`: Sağlam rulmanın normallik varsayımı.
* `bozuk_rulman_qq.png`: Bozuk rulmanın dağılım sapması.
* `regresyon_trendi.png`: Zaman serisi üzerinde bozulma eğilimini gösteren regresyon doğrusu.

## Kullanılan Teknolojiler
* **Dil:** R
* **Araçlar:** RStudio
* **Kavramlar:** Kestirimci Bakım (Predictive Maintenance), İstatistiksel Veri Analizi, Zaman Serisi, Doğrusal Regresyon, Rastgele Örneklem.
