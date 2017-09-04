---
title: Yardım
---

## 1. Yeni Yazı Nasıl Yazılır?

Bütün yazılar "_post" dizini altında tutulur. Yeni yazı YYYY-AA-GG-yazi-adi.md adıyla yaratılıp bu dizine eklenir.

Örnek:

**2017-09-03-turnuva-duyurusu.md**

Eğer yazı bir turnuva ile ilgili ise dosya adında turnuva kodu da olmalıdır.

**2017-09-15-TRV9999-turnuva-duyurusu.md**


### 1.1 Yazı içeriği nasıl olmalıdır?

Bütün yazılar aşağıdaki 3 satır ile başlamalıdır. Aşağıdaki satırlardan sonra istenen yazı yazılır.

```
---
title: Yazı Başlığı
---
```

### 1.2 Yazıya nasıl resim eklenir?

/assets/images/ dizini altında yazı adı ile birebir aynı olan bir resim dosyası varsa bu dosya yazının resmi olur. Dosya uzantısının önemi yoktur. JPG, PGN, GIF olabilir.

Örnek:

2017-09-15-TRV9999-turnuva-duyurusu.jpg  
2017-09-02-sonuclar.JPG  

Eğer yazının sonuna başka resimler eklenmek isteniyorsa, yazı dosyasının adına -1, -2 eklenerek resimler eklenir.

2017-09-15-TRV9999-turnuva-duyurusu-1.jpg  
2017-09-15-TRV9999-turnuva-duyurusu-2.jpg  
2017-09-15-TRV9999-turnuva-duyurusu-3.jpg  

Eğer sürekli kullanılan bir resim eklenmek isteniyorsa, yazı başlığı kısmındaki "image" parametresi kullanılır.

### 1.3 Yazı Parametreleri

Gerekiyorsa aşağıdaki parametreler kullanılabilir.

```
---
title: Yazı Başlığı
image: resim_dosyasi_adi.jpg (assets/images dizini altındaki bir dosyanın ismi yazılırsa bu imaj gösterilir)
ukd: 1 (turnuva dosyasına tsf-turnuva-no veya tsf-hizli-turnuva-no bilgisi eklenmişse TSF sayfası linki eklenir)
elo: 1 (turnuva dosyasına elo-turnuva-no bilgisi eklenmişse FIDE sayfası linki eklenir)
odul: 0 (turnuva dosyasına ödül bilgisi eklenmişse kazananlar sütunu olmadan gösterilir)
odul: 1 (turnuva dosyasına ödül bilgisi eklenmişse kazananlar sütunu ile birlikte gösterilir)
resimler:  (eğer yazıdaki resimlere alt yazı eklenmek isteniyorsa sıraya dikkat edilerek aşağıdaki gibi eklenir.)
  - resim 1 alt yazı
  - resim 2 alt yazı
  - resim 3 alt yazı
---
```

## 2. Yeni Turnuva Nasıl Eklenir?

Turnuva eklemek için "_turnuvalar" dizini altına **YYYY-AA-GG-TRV9999-turnuva-adi** adıyla yeni bir klasör eklenir. Turnuva kodu belirlendikten sonra tüm yazı, resim, yönerge, pgn gibi dosyalarda bu kod yer almak zorundadır.

[Örnek klasör](/assets/other/ornek.zip)

Bu zip dosyasının içindeki ".yml" uzantılı dosya "/data/turnuvalar" dizini altına **YYYY-AA-GG-TRV9999-turnuva-adi** adıyla eklenir. Dosya içindeki parametreler değiştirilir. Gereksiz parametreler silinir.

```
adi: Marmaris İndigo Turnuva Adı

turnuva-durum: 0   (Turnuva başladıktan sonra 1 yapılır. 1 yapıldığında Başvuru menüsü yok olur.)
kategoriler: A; B; C; D  (Tüm ayraçlar ";")
tsf-turnuva-no: 99999 (Turnuva başında belli olmadığı için değeri silinebilir)
tsf-hizli-turnuva-no: 99999 (Turnuva başında belli olmadığı için değeri silinebilir)
fide-turnuva-no: 99999 (Turnuva başında belli olmadığı için değeri silinebilir)

konaklama: 2017-06-27-konaklama-fiyatlari (Eğer konaklama bilgisi verilecekse daha önce yazılmış bir yazını adı verilebilir. _post dizin altında bulunmalıdır.)
yonerge-kategori: true (Eğer her kategori için ayrı yönerge dosyası varsa "true", değilse silinebilir.)
oyunlar: 1 (Eğer PGN içinde hamleler varsa "1", değilse silinebilir.)

facebook-album: https://www.facebook.com/profile.php?id=100005340018875&sk=photos&collection_token=100005340018875:2305272732:69&set=a.633377346850260.1073741847.100005340018875&type=3&pnref=story
(Eğer facebook albümü varsa)

basvuru-form: <iframe src="https://docs.google.com/forms/d/e/1FAIpQLSfBz_wQUI41axFhl9fS7vmG44_3uWZ-vhYUNaGV0WZ-P97hSg/viewform?embedded=true" width="720" height="1200" frameborder="0" marginheight="0" marginwidth="0">Loading...</iframe>
(Başvuru formu Google Forms ile oluşturulur. width ve height değerleri değiştirilerek kopyalanır.)

basvuru-listesi: <iframe src="https://docs.google.com/spreadsheets/d/1CERDOGtM7Pc_lphN7DJMhusTBoKH3qd2pPlnJbty4Ao/pubhtml?widget=true&amp;headers=false" width="720" height="800"></iframe>
(Başvuru listesi Google Forms ile oluşturulur. width ve height değerleri değiştirilerek kopyalanır.)

```

### 2.1 Yönerge Dosyası Nasıl Eklenir?

_/turnuvalar/YYYY-AA-GG-TRV9999-turnuva-adi klasörü altına aşağıdaki dosya adı ile eklenir.

YYYY-AA-GG-TRV9999-turnuva-adi-yonerge.pdf

veya her kategori için farklı dosya varsa

YYYY-AA-GG-TRV9999-turnuva-adi-yonerge-A.pdf  
YYYY-AA-GG-TRV9999-turnuva-adi-yonerge-B.pdf  
YYYY-AA-GG-TRV9999-turnuva-adi-yonerge-C.pdf

**dosya uzantısı küçük harfle .pdf olmalıdır.**

### 2.2 PGN Dosyası Nasıl Eklenir?

_/turnuvalar/YYYY-AA-GG-TRV9999-turnuva-adi klasörü altına aşağıdaki dosya adı ile eklenir.

YYYY-AA-GG-TRV9999-turnuva-adi-A.pgn  
YYYY-AA-GG-TRV9999-turnuva-adi-B.pgn  
YYYY-AA-GG-TRV9999-turnuva-adi-C.pgn  

**dosya uzantısı küçük harfle .pgn olmalıdır.**

### 2.3 Sıralama Dosyası Nasıl Eklenir?

_/turnuvalar/YYYY-AA-GG-TRV9999-turnuva-adi klasörü altına aşağıdaki dosya adı ile eklenir.

YYYY-AA-GG-TRV9999-turnuva-adi-siralama-A.txt  
YYYY-AA-GG-TRV9999-turnuva-adi-siralama-B.txt  
YYYY-AA-GG-TRV9999-turnuva-adi-siralama-C.txt  

**dosya uzantısı küçük harfle .txt olmalıdır.**
