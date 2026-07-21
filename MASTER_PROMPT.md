# BayiGo Tanıtım Filmi — Codex Master Prompt

## Görev

Bu depodaki dokümanları ve sağlanan BayiGo TDM sunumunu analiz ederek yaklaşık **60 saniyelik**, Türkçe seslendirmeli, premium ürün tanıtım filmi geliştir.

Bu çalışma bir slayt videosu değildir. Sunumdaki içerikleri yeniden kurgula; anlatımı, ekran hareketlerini ve görsel ritmi profesyonel bir ürün filmi mantığıyla oluştur.

## Hedef

İzleyen TDM yöneticisi videonun sonunda şu üç mesajı net biçimde anlamalıdır:

1. BayiGo Market, bayi sipariş ve operasyon süreçlerini tek merkezde toplar.
2. BayiGo Medya, bayiye özel görsel ve video üretimini hızlandırır.
3. BayiGo, TDM ve bayi tarafında hız, standartlaşma ve gelir artışı sağlar.

## Hedef kitle

- Turkcell TDM yöneticileri
- Bölge ve kanal yöneticileri
- Dağıtım şirketleri
- Büyük bayi organizasyonları

## Süre ve format

- Ana film: 55–65 saniye
- Yatay çıktı: 1920x1080, 25 veya 30 fps
- Dikey çıktı: 1080x1920
- Ön izleme: düşük bitrate MP4
- Final: yüksek kalite H.264 MP4
- Her sahne ayrı render edilebilir olmalı

## Kullanılacak teknoloji

- Remotion
- React
- TypeScript
- GSAP
- SVG animasyonları
- FFmpeg
- Gemini TTS

Framer Motion yalnızca basit arayüz geçişlerinde kullanılabilir. Ana zamanlama Remotion frame sistemi üzerinden yürütülmelidir.

## Kullanılmayacak yöntemler

- PowerPoint slaytlarını doğrudan videoya çevirmek
- Statik ekran görüntülerini uzun süre göstermek
- Adobe After Effects proje dosyası üretmek
- Premiere, CapCut veya Filmora bağımlılığı kurmak
- Telifsiz olduğu doğrulanmamış müzik ya da ses kullanmak
- Uzun AI video kliplerine güvenmek

## Görsel yön

Referans hissi:

- Apple ürün filmleri
- OpenAI ürün duyuruları
- Stripe ve Linear motion design dili

Tasarım karakteri:

- Minimal
- Kurumsal
- Teknolojik
- Güven veren
- Yüksek kontrastlı
- Kontrollü hareketli

Renkler:

- Turkcell sarısı
- Derin lacivert
- Beyaz
- Siyah
- Yumuşak mavi-mor geçişler yalnızca destekleyici olarak

## Motion design kuralları

Önemli anlarda After Effects kalitesinde hissedilen ancak tamamen kodla üretilen animasyonlar kullan:

- 2.5D kamera hareketleri
- Parallax
- Motion blur benzetimi
- Depth of field hissi
- Mask reveal
- Shape morph
- Kinetic typography
- UI focus zoom
- Light sweep
- Glow
- Particle accents
- Animated counters
- Card stacking
- Timeline ve progress animasyonları

Efektler mesajı güçlendirmeli; gösteriş için kullanılmamalıdır.

## Anlatı yapısı

### 1. Problem — 0:00–0:10

Telefon, WhatsApp, Excel, dağınık siparişler, kaçırılan kampanyalar ve yüksek medya üretim maliyetini hızlı ve kontrollü bir kaos diliyle göster.

### 2. Dönüşüm — 0:10–0:16

Her şey kısa süreliğine durur. Karanlık ekranda şu soru belirir:

> Peki ya bütün bunlar tek platformdan yönetilebilseydi?

Ardından BayiGo logosu sinematik şekilde oluşur.

### 3. BayiGo Market — 0:16–0:35

Dashboard, ürün kataloğu, kampanyalar, cari limit, sipariş, kargo ve raporlama akışını canlı bir ürün demosu gibi göster.

### 4. BayiGo Medya — 0:35–0:50

Şablon seçimi, bayi logosu, telefon, adres, otomatik kişiselleştirme, video üretimi ve sosyal medya paylaşımını tek akışta göster.

### 5. Değer ve final — 0:50–1:00

Hız, standartlaşma, gelir artışı ve profesyonel görünüm mesajlarını güçlü tipografiyle özetle.

Final metni:

> Geleceğin bayi ekosistemi bugün başlıyor.

Ardından:

> bayigo.net

## Seslendirme

Gemini TTS kullanılacak. Her sahne için iki metin tutulacak:

- Normal Türkçe metin
- Gemini TTS için fonetik metin

Örnek telaffuzlar:

- BayiGo → Bayi Go
- TDM → Te De Me
- WhatsApp → Vatsap
- B2B → Bi Tu Bi
- API → A Pi Ay
- AI → Ey Ay

Türkçe karakterleri körü körüne dönüştürme. Önce doğal okuma denemesi yap; yalnızca sorunlu kelimeleri fonetikleştir.

## Ses tasarımı

- Başlangıçta kontrollü bildirim ve arayüz yoğunluğu
- Dönüşüm anında kısa sessizlik
- Logo girişinde düşük frekanslı vurgu
- UI hareketlerinde yumuşak click, hover ve whoosh
- Finalde güven veren yükseliş

Müzik ve efekt seviyeleri seslendirmeyi bastırmamalıdır.

## Proje yapısı

Her sahne ayrı bileşen olmalı. Ortak animasyonlar, easing değerleri, renkler, tipografi ve süreler merkezi yapılandırmadan gelmelidir.

## Çalışma sırası

1. Tüm Markdown dosyalarını oku.
2. Eksik asset listesini çıkar.
3. Storyboard ve zaman çizelgesini oluştur.
4. Remotion iskeletini kur.
5. Önce düşük kalite animatic üret.
6. Seslendirmeyi ekle ve zamanlamayı kilitle.
7. Sahne animasyonlarını geliştir.
8. Ses tasarımını ekle.
9. Yatay ve dikey render al.
10. Kalite kontrol listesini tamamla.

## Kabul kriterleri

- Video 55–65 saniye aralığında olmalı.
- İlk 10 saniyede problem açıkça anlaşılmalı.
- Market ve Medya bölümleri birbirinden ayırt edilebilmeli.
- Hiçbir sahne sıradan slayt gösterisi gibi görünmemeli.
- Türkçe seslendirme doğal ve anlaşılır olmalı.
- Düşük kalite ön izleme kolayca indirilebilir olmalı.
- Final render tek komutla alınabilmeli.
- Kullanılan tüm varlıkların lisansı veya kaynağı belgelenmeli.
