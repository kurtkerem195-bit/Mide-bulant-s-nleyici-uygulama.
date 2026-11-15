# Hareket İşaretleri

Araçta telefona bakarken yaşanan mide bulantısını azaltmaya yardımcı olan, Android için ücretsiz bir uygulama. Ekranın kenarlarında aracın hızlanma, frenleme ve dönüşlerine göre kayan noktalar gösterir.

> iPhone'daki "Araç Hareketi İşaretleri" (Vehicle Motion Cues) özelliğinden esinlenilmiştir. Apple ile hiçbir bağlantısı yoktur.

<!-- Ekran görüntülerini buraya ekle:
<p align="center">
  <img src="docs/ekran1.png" width="240" />
  <img src="docs/ekran2.png" width="240" />
</p>
-->

## Neden işe yarayabilir?

Araçta telefona bakarken gözlerin sabit bir ekran görür, ama iç kulağın aracın hareketini hisseder. Bu uyumsuzluk bulantıya yol açabilir. Uygulama telefonun hareket sensörünü okuyup ekranın kenarlarında aracın hareketiyle uyumlu noktalar gösterir. Böylece gözün gördüğü ile vücudunun hissettiği birbirine yaklaşır.

- Araç **hızlanınca** noktalar aşağı, **frenleyince** yukarı kayar.
- **Dönüşlerde** noktalar dönüşün tersi yönüne kayar.
- Noktalar manzara gibi akar, hareket bitince yavaşça durur.

## Özellikler

- Diğer uygulamaların üstünde çalışır, dokunmaları engellemez
- Arkadaki renge göre **beyaz ya da siyah** olan noktalar (isteğe bağlı), ya da sabit beyaz / siyah
- Nokta rengi, sıklığı, boyutu ve görünürlüğü ayarlanabilir
- Hassasiyet ve akış hızı ayarı
- Sol/sağ ve üst/alt kenarı ayrı ayrı açıp kapatma
- Hareketsizken otomatik gizleme
- Hızlı ayarlar paneline karo ekleme (tek dokunuşla aç/kapat)
- iPhone Ayarlar'a benzeyen, açık/koyu temalı arayüz
- İnternet erişimi yok, hiçbir veri toplanmaz

## Kurulum

Gereksinim: **Android 8.0 (API 26)** ve üzeri.

1. [Releases](../../releases) sayfasından en son `.apk` dosyasını indir.
2. Dosyayı aç. Telefon istediğinde, tarayıcın ya da dosya yöneticin için **"Bilinmeyen kaynaklardan yüklemeye izin ver"** seçeneğini aç.
3. Yükle ve uygulamayı aç.

## Kullanım

1. **"Üstte gösterme"** iznini ver (uygulama seni ilgili ayar sayfasına götürür).
2. Ana anahtarı aç. İstersen sağ üstteki hızlı ayarlar karosunu da ekleyebilirsin.
3. Nokta rengi **Otomatik** ise ekran paylaşma izni penceresi çıkar, **"Tüm ekran"** seçeneğini seç. Beyaz ya da Siyah seçersen bu izin gerekmez.
4. Telefonu araçta mümkünse sabit bir tutucuya koy.

### Ayarlar

| Ayar | Ne yapar |
|---|---|
| Nokta rengi | Otomatik (arka plana göre), Beyaz, Siyah |
| Nokta sıklığı | Seyrek, Normal, Sık |
| Nokta boyutu | 0,6× – 2× |
| Görünürlük | %20 – %100 |
| Hassasiyet | Noktaların ne kadar kaydığı |
| Akış hızı | Hızlanırken ve virajda noktaların akış hızı |
| Kenarlar | Sol/sağ ve üst/alt kenarı aç/kapat |
| Otomatik gizleme | Hareketsizken noktaları gizler (5–60 sn) |

## İzinler ve gizlilik

| İzin | Neden gerekli |
|---|---|
| Diğer uygulamaların üzerinde gösterme (`SYSTEM_ALERT_WINDOW`) | Noktaları ekranın üstüne çizmek için |
| Ön plan servisi (`FOREGROUND_SERVICE`, `..._SPECIAL_USE`) | Arka planda hareket sensörünü okumak için |
| Ekran paylaşma (`..._MEDIA_PROJECTION`) | Sadece **Otomatik renk** modunda, noktaların arkasındaki rengin parlaklığını ölçmek için |
| Bildirimler (`POST_NOTIFICATIONS`) | Bildirimdeki "Durdur" düğmesi için |

- Uygulamada **internet izni yoktur**, hiçbir veri cihazdan dışarı çıkmaz.
- Ekran görüntüsü çok düşük çözünürlükte, yalnızca parlaklık ölçmek için işlenir. Kaydedilmez ve saklanmaz.

## Bilinen sınırlar

- Telefonun hareket sensörü **sabit hızı** ölçemez, sadece hız değişimini ölçer. Düz yolda sabit hızla giderken noktalar sakinleşir.
- Telefonu elde tutarken el hareketlerine de tepki verir. Sabit bir tutucu en iyi sonucu verir.
- "Otomatik gizleme" gerçek araç algılaması değildir, sadece telefonun hareket sensörüne dayanır.
- Ekran görüntüsüne kapalı uygulamalarda (bazı bankacılık uygulamaları gibi) Otomatik renk çalışmaz, noktalar beyaz kalır.
- Bazı telefonlarda pil tasarrufu servisi durdurabilir. Uygulama için pil kısıtlamasını kapat.

## Kaynak koddan derleme

1. [Android Studio](https://developer.android.com/studio)'yu kur.
2. Depoyu klonla:
   ```bash
   git clone https://github.com/<kullanici-adi>/<repo-adi>.git
   ```
3. Android Studio'da klasörü aç, Gradle senkronizasyonu bitince telefonu bağlayıp **Run**'a bas.

Kotlin ve Jetpack Compose ile yazılmıştır.

## Katkı

Hata bildirimleri ve öneriler için [Issues](../../issues) bölümünü kullanabilirsin. Hata bildirirken telefon modelini, Android sürümünü ve ne olduğunu yazarsan çok yardımcı olur.

## Önemli not

Bu uygulama tıbbi bir cihaz, tedavi ya da tavsiye değildir. Bulantıyı azaltmaya yardımcı olabilir, ama herkeste aynı etkiyi göstermeyebilir. Şikâyetlerin sürerse bir sağlık uzmanına danış.

## Lisans

<!-- Bir lisans seç ve LICENSE dosyasını ekle. Örneğin MIT: https://choosealicense.com/licenses/mit/ -->
Lisans: `<buraya lisans adı>`

---

## English summary

**Hareket İşaretleri** (Motion Cues) is a free Android app that helps reduce motion sickness in vehicles. It draws small dots along the screen edges that move with the vehicle's acceleration, braking and turns, inspired by the iPhone's Vehicle Motion Cues feature (not affiliated with Apple).

- Works on top of other apps without blocking touches
- Dot color adapts to the background (optional), or fixed white/black
- Adjustable size, density, opacity, sensitivity and flow speed
- Quick Settings tile, auto-hide when still, light/dark UI
- No internet permission, no data collected

Requires Android 8.0+. Download the APK from [Releases](../../releases). This app is not a medical device or medical advice.
