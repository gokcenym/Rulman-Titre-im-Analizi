 Rulman Titreşim Analizi ve Kestirimci Bakım Projesi

- Proje Özeti
Bu çalışmada, endüstriyel sistemlerde önemli bir rol oynayan rulmanların ivmeölçer titreşim verilerinin R ortamında incelenmesi amaçlanmıştır. Temel hedef; kararlı çalışan bir makine ile arızalı bir makinenin titreşim davranışları arasındaki olası farkları istatistiksel testler yardımıyla gözlemleyebilmek ve zaman içindeki aşınma eğilimini görsel ve matematiksel yöntemlerle modellemeye çalışmaktır.

- Projenin Amacı
* Makine Sağlığını Gözlemlemek: Rulmanların titreşim sinyalleri gibi çalışma verilerini izleyerek, olası durum değişimlerini değerlendirmeye çalışmak.
* Arıza İhtimalini Öngörebilmek: Makine tamamen işlevini yitirmeden önce veride belirebilecek değişimleri inceleyerek, kestirimci bakım yaklaşımları için temel bir analiz altyapısı oluşturmaya katkı sağlamak.
* İstatistiksel Karşılaştırmalar Sunmak: Sağlam ve arızalı olduğu bilinen rulmanların titreşim karakteristiklerini RMS, normallik incelemesi ve doğrusal regresyon gibi yaklaşımlar üzerinden istatistiksel bir çerçevede incelemek.

- Veri Seti Kaynağı
Bu projede, endüstriyel rulmanların titreşim özelliklerini incelemek amacıyla Kaggle platformunda açık kaynak olarak sunulan titreşim veri seti (NASA Bearing Dataset) kullanılmıştır. Analizler, bu veri seti içindeki işlenmiş ivmeölçer sinyalleri üzerinden gerçekleştirilmiştir.

- Kullanılan Yöntemler ve Araçlar
Proje kapsamında veri işleme ve modelleme süreçleri tamamen R Dili kullanılarak RStudio ortamında yürütülmüştür. Temel analiz adımları şu şekildedir:
* RMS (Root Mean Square) Metriği: Titreşim sinyalinin genliğini ve enerji içeriğiyle ilişkili değişimini özetleyebilmek adına ana analiz metriği olarak tercih edilmiştir.
* Normallik Testleri (Shapiro-Wilk & Q-Q Plot): Seçilen örneklemlerin normal dağılıma uygunluğunu ve dağılım özelliklerini istatistiksel bir perspektifle değerlendirmek amacıyla uygulanmıştır.
* Doğrusal Regresyon (lm): Zaman boyunca gözlenen RMS değerlerindeki genel trendi matematiksel olarak modelleyebilmek ve olası titreşim artış eğilimini değerlendirmek için kullanılmıştır.

- Veri İşleme ve Kıyaslama Yaklaşımı
Kestirimci bakım analizini gerçekleştirebilmek için zaman serisi verisi üzerinde bir durum kıyaslaması yapılmıştır. Bu doğrultuda veri seti iki ana aşamaya ayrılarak incelenmiştir:
* Sağlam Durum Analizi: Makinenin ilk çalıştığı ve mekanik olarak en sağlıklı kabul edildiği dönemi temsil etmesi amacıyla veri setinin ilk 5000 satırı (gözlemi) referans alınmıştır.
* Arızalı Durum Analizi: Rulmanların aşınmaya başladığı ve arızaya doğru giden süreci gözlemleyebilmek için, aynı veri setinin son 5000 satırı izole edilerek incelenmiştir.

- Bulgular ve Değerlendirmeler
Yapılan istatistiksel testler ve görselleştirmeler sonucunda aşağıdaki bulgular elde edilmiştir:
* Sağlam Rulman Normalliği: İlk 5000 gözlem üzerinden yapılan Q-Q Plot analizinde, verilerin referans doğrusuna yakın seyrettiği gözlemlenmiştir. Bu durum, makinenin kararlı çalıştığı evrede titreşim verisinin normal dağılıma daha uygun bir yapı sergilediğini göstermektedir (Bu gözlem Shapiro-Wilk testi ile de desteklenmiştir).
* Bozuk Rulman Dağılım Kırılması: Makinenin bozulmaya başladığı dönemi temsil eden son 5000 satırlık veride, Q-Q plot üzerindeki noktaların referans doğrusundan belirgin biçimde saptığı görülmüştür. Bu kırılma, arıza yaklaştıkça titreşim karakteristiğinin ve veri dağılım özelliklerinin farklılaştığına işaret etmektedir.
* Zamana Bağlı Aşınma Trendi: Zamana karşı çizdirilen RMS değerlerine uygulanan doğrusal regresyon (lm) modelinde, zaman katsayısının pozitif olduğu bulunmuştur. Bu pozitif eğim, zaman ilerledikçe makinedeki titreşim şiddetinde (RMS) kümülatif bir artış eğilimi olduğunu ve aşınma trendinin matematiksel olarak modellenebileceğini göstermektedir.

- Endüstriye ve İşletmelere Yararı
* Maliyeti Düşürür: Arıza belirtilerinin erken tespit edilmesi, bakımın daha planlı şekilde yapılmasına ve beklenmeyen duruş riskinin azaltılmasına katkı sağlayabilir.
* İş Güvenliği Sağlar: Kritik ekipmanlardaki olası arıza belirtilerinin erken fark edilmesi, kontrolsüz ekipman arızalarının oluşturabileceği risklerin azaltılmasına yardımcı olabilir.
* Ekipman Ömrünü Uzatır: Erken uyarı yaklaşımı, bakım kararlarının zamanında alınmasına ve ekipman üzerindeki olası hasarın önlenmesine katkı sağlayabilir.

- Kurulum ve Yapılandırma (Setup & Usage)
Bu proje tamamen temel R (Base R) fonksiyonları ile geliştirildiği için harici bir paket kurulumuna ihtiyaç duymaz. Kodu kendi ortamınızda incelemek ve çalıştırmak için aşağıdaki adımları izleyebilirsiniz:
1. Bilgisayarınızda R ve RStudio'nun kurulu olduğundan emin olun.
2. Bu depodaki kod dosyasını indirin.
3. Kaggle üzerinden ilgili titreşim veri setini (NASA Bearing Dataset) indirin. Dosya adının `features_fault_named.csv` olduğundan emin olarak R script'i ile aynı klasör içerisine yerleştirin.
4. RStudio'da projeyi açın ve çalışma dizinini dosyanın bulunduğu klasör olarak ayarlayın (`Session > Set Working Directory > To Source File Location`).
5. Kodu baştan sona çalıştırdığınızda; istatistiksel test sonuçları konsola yazdırılacak ve grafikler proje klasörüne `.png` formatında otomatik olarak kaydedilecektir.
