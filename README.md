
# Spotify ve YouTube Veri Seti Keşifsel Veri Analizi (EDA)

Bu proje, Spotify ve YouTube verilerini analiz etmeyi ve karşılaştırmayı amaçlamaktadır. Veriseti, müzik akış platformları üzerindeki popüler içeriklere ilişkin çeşitli bilgileri içermektedir.

### İçerik
Spotify'dan toplanan şarkıların her biri için 26 değişken içerir. Bu değişkenler kısaca şu şekilde açıklanmıştır:

- **Track**: Şarkının adı, Spotify platformunda görüldüğü şekliyle.
- **Artist**: Sanatçının adı.
- **Url_spotify**: Sanatçının Spotify URL'si.
- **Album**: Şarkının Spotify'da yer aldığı albüm.
- **Album_type**: Şarkının Spotify'da bir single olarak mı yoksa bir albümde mi yayınlandığını belirtir.
- **Uri**: Şarkıyı API üzerinden bulmak için kullanılan bir Spotify bağlantısı.
- **Danceability**: Tempo, ritim kararlılığı, vuruş gücü ve genel düzenlilik gibi müzikal unsurların bir kombinasyonuna dayanarak bir parçanın dans için ne kadar uygun olduğunu açıklar. 0.0 en az dans edilebilir, 1.0 en çok dans edilebilir.
- **Energy**: 0.0'dan 1.0'a kadar ölçülen ve yoğunluk ve aktivitenin algısal bir ölçüsünü temsil eden bir değerdir. Tipik olarak, enerjik parçalar hızlı, yüksek sesli ve gürültülü hissettirir. Örneğin, death metal yüksek enerjiye sahiptir, bir Bach prelüdü ise düşük puan alır. Bu niteliğe katkıda bulunan algısal özellikler arasında dinamik aralık, algılanan yüksek ses, tını, başlangıç hızı ve genel entropi bulunur.
- **Key**: Parçanın bulunduğu anahtar. Tam Sayılar, standart Pitch Class notasyonu kullanılarak perdelere eşlenir. Örneğin, 0 = C, 1 = C♯/D♭, 2 = D, vb. Anahtar algılanmadıysa, değer -1'dir.
- **Loudness**: Bir parçanın genel yüksekliği desibel (dB) cinsinden. Yükseklik değerleri, parçanın tamamı boyunca ortalanır ve parçaların göreceli yüksekliğini karşılaştırmak için kullanılır. Yükseklik, fiziksel gücün (genlik) birincil psikolojik korelasyonu olan bir ses kalitesidir. Değerler tipik olarak -60 ile 0 db arasında değişir.
- **Speechiness**: Bir parçada konuşma sözcüklerinin varlığını tespit eder. Kayıt ne kadar yalnızca konuşma gibi olursa (örneğin, talk show, sesli kitap, şiir), nitelik değeri 1.0'a o kadar yakın olur. 0.66'nın üzerindeki değerler, muhtemelen tamamen konuşma sözcüklerinden oluşan parçaları tanımlar. 0.33 ile 0.66 arasındaki değerler, rap müzik gibi, bölümler halinde veya katmanlı olarak hem müzik hem de konuşma içerebilen parçaları tanımlar. 0.33'ün altındaki değerler büyük olasılıkla müzik ve diğer konuşma olmayan parçaları temsil eder.
- **Acousticness**: Bir parçanın akustik olup olmadığının 0.0'dan 1.0'a kadar olan güvenilirlik ölçüsü. 1.0, parçanın yüksek güvenle akustik olduğunu temsil eder.
- **Instrumentalness**: Bir parçanın vokal içermediğini tahmin eder. Bu bağlamda "Ooh" ve "aah" sesleri enstrümantal olarak kabul edilir. Rap veya konuşma sözcüklerinden oluşan parçalar açıkça "vokal"dir. Instrumentalness değeri 1.0'a yaklaştıkça, parçanın vokal içermeme olasılığı o kadar artar. 0.5'in üzerindeki değerler enstrümantal parçaları temsil etmek için tasarlanmıştır, ancak güvenilirlik değer yaklaştıkça artar.
- **Liveness**: Kayıtta bir izleyicinin varlığını tespit eder. Yüksek liveness değerleri, parçanın canlı olarak icra edilme olasılığının arttığını temsil eder. 0.8'in üzerindeki bir değer, parçanın canlı olduğuna dair güçlü bir olasılık sağlar.
- **Valence**: Bir parçanın ilettiği müzikal pozitifliği 0.0'dan 1.0'a kadar ölçen bir değerdir. Yüksek valence değerlerine sahip parçalar daha pozitif (ör. mutlu, neşeli, coşkulu) seslerken, düşük valence değerlerine sahip parçalar daha negatif (ör. üzgün, depresif, öfkeli) sesler.
- **Tempo**: Bir parçanın genel tahmini temposu, dakika başına vuruş (BPM) cinsinden. Müzikal terminolojide tempo, bir parçanın hızını veya ritmini ifade eder ve doğrudan ortalama vuruş süresinden türetilir.
- **Duration_ms**: Parçanın süresi milisaniye cinsinden.
- **Stream**: Şarkının Spotify'da akış sayısı.
- **Url_youtube**: Şarkıya bağlı video klibin YouTube URL'si, varsa.
- **Title**: YouTube'daki video klibin başlığı.
- **Channel**: Videoyu yayınlayan kanalın adı.
- **Views**: Görüntülenme sayısı.
- **Likes**: Beğeni sayısı.
- **Comments**: Yorum sayısı.
- **Description**: YouTube'daki videonun açıklaması.
- **Licensed**: Videonun lisanslı içeriği temsil edip etmediğini belirtir, yani içeriğin bir YouTube içerik ortağına bağlı bir kanala yüklendiği ve daha sonra bu ortak tarafından talep edildiği anlamına gelir.
- **official_video**: Bulunan videonun şarkının resmi videosu olup olmadığını belirten boolean değer.
