# NASA Rulman Verisinde İstatistiksel RMS Trend Analizi

## Proje Amacı

Bu proje, NASA Bearing Dataset içindeki sağlam ve arızalı rulmanlara ait titreşim verilerini istatistiksel yöntemlerle incelemeyi amaçlamaktadır. Analizde `B1__rms` (1. rulmanın RMS değeri) değişkeni kullanılarak dağılımlar görselleştirilmiş ve arızalı rulman verisindeki RMS değerinin zaman içindeki eğilimi doğrusal regresyonla incelenmiştir.

Bu çalışma, rulman verisi üzerinde yapılan bir istatistiksel analiz örneğidir. Mevcut analiz tek başına gelecekteki arızaları veya bakım zamanını tahmin etmez.

## Veri Seti ve Ön İşleme

- **Veri kaynağı:** NASA Bearing Dataset.
- **Kullanılan değişken:** `B1__rms` (1. rulmanın RMS değeri).
- **Girdi dosyaları:** Kodun çalışması için `features_good_named.csv` ve `features_fault_named.csv` dosyaları R betiğiyle aynı dizinde bulunmalıdır. Veri dosyaları depoda yer almıyorsa, bu dosyaların hangi kaynaktan ve hangi adımlarla elde edildiği ayrıca açıklanmalıdır.
- **Örnekleme:** Sağlam rulman verisinin normallik testi için 5.000 gözlem rastgele seçilmiştir. Rastgele örneklemin tekrarlanabilir olması için analiz öncesinde sabit bir tohum değeri belirlenmesi önerilir.

## Metodoloji ve İstatistiksel Analiz

### 1. Dağılımın incelenmesi

Sağlam ve arızalı rulmanların `B1__rms` değerleri Q-Q grafikleriyle görselleştirilmiş; sağlam rulman verisinden seçilen 5.000 gözlem üzerinde Shapiro-Wilk testi uygulanmıştır.

Shapiro-Wilk testi, verinin normal dağılımla uyumunu değerlendirmek için kullanılmıştır. Büyük örneklemlerde küçük sapmaların da istatistiksel olarak anlamlı çıkabileceği göz önünde bulundurulmalı; sonuçlar Q-Q grafikleriyle birlikte yorumlanmalıdır. Mevcut analizde Q-Q grafikleri tüm veri üzerinden çizilirken normallik testi sağlam veriden alınan rastgele örneklem üzerinde yapılmıştır.

### 2. Arızalı rulman verisinde RMS eğilimi

Arızalı rulman verisindeki `B1__rms` değerinin satır sırasına göre değişimi doğrusal regresyonla incelenmiştir. Modelde satır sırası zaman göstergesi olarak kullanılmıştır.

Analiz çıktısında zaman göstergesi ile RMS değeri arasında pozitif yönlü ve istatistiksel olarak anlamlı bir ilişki raporlanmıştır (`p < 2e-16`). Bu sonuç, incelenen veri içindeki doğrusal eğilimi gösterir; tek başına gelecekteki arıza zamanını veya bakım ihtiyacını tahmin ettiği anlamına gelmez. Ölçümlerin zaman sırasına bağlı olabileceği için regresyon sonuçları bu sınırlama dikkate alınarak yorumlanmalıdır.

## Proje Çıktıları

Depoda bulunan grafikler:

- `saglam_rulman_qq.png`: Sağlam rulman RMS değerlerinin Q-Q grafiği.
- `bozuk_rulman_qq.png`: Arızalı rulman RMS değerlerinin Q-Q grafiği.
- `regresyon_trendi.png`: Arızalı rulman RMS değerlerinin satır sırasına göre değişimi ve doğrusal regresyon çizgisi.

 ## Analiz Sınırları ve Gelecek Çalışmalar (Limitations & Future Work)
* **Değişken Sınırlandırması:** Bu mini araştırma ve keşifsel çalışmada (EDA) temel trendi görmek adına yalnızca RMS (Root Mean Square) değeri baz alınmıştır. Gelecek aşamalarda verisetindeki Kurtosis, Skewness ve Peak-to-Peak gibi diğer titreşim metriklerinin de sürece dahil edilmesi planlanmaktadır.
Zaman Serisi Dinamikleri: Arızalı rulmana ait RMS değerlerinin satır sırasına göre eğilimini incelemek için doğrusal regresyon kullanılmıştır. Sensör ölçümlerinde zaman bağımlılığı ve otokorelasyon bulunabileceğinden, regresyon sonuçları bu sınırlama dikkate alınarak yorumlanmalıdır. Gelecek çalışmalarda, zaman bilgisi ve veri yapısı uygun olduğunda zaman serisi veya kestirim modellerinin denenmesi planlanmaktadır.

## Kullanılan Teknolojiler

- **Programlama dili:** R
- **Geliştirme ortamı:** RStudio
- **Yöntemler:** Betimsel analiz, Q-Q grafikleri, Shapiro-Wilk testi ve doğrusal regresyon
