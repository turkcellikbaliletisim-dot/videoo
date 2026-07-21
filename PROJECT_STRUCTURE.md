# BayiGo Video Project Structure

## Amaç

Bu belge, Codex'in Remotion tabanlı BayiGo tanıtım filmi projesini hangi klasör ve dosya yapısıyla oluşturacağını tanımlar.

## Kök yapı

```text
videoo/
├── README.md
├── MASTER_PROMPT.md
├── PROJECT_STRUCTURE.md
├── STYLE_GUIDE.md
├── TECH_STACK.md
├── TODO.md
├── package.json
├── tsconfig.json
├── remotion.config.ts
├── .gitignore
├── .env.example
├── docs/
├── public/
├── src/
├── scripts/
├── render/
└── output/
```

## `docs/`

Proje içeriği ve üretim kararları burada tutulur.

```text
docs/
├── STORYBOARD.md
├── VOICEOVER.md
├── VOICEOVER_PHONETIC.md
├── DIRECTOR_NOTES.md
├── ASSET_LIST.md
├── MUSIC_GUIDE.md
├── SFX_GUIDE.md
└── QA_CHECKLIST.md
```

## `public/`

Remotion tarafından doğrudan erişilecek tüm medya dosyaları burada bulunur.

```text
public/
├── assets/
│   ├── logos/
│   ├── images/
│   ├── screenshots/
│   ├── icons/
│   ├── fonts/
│   ├── lottie/
│   └── textures/
├── audio/
│   ├── music/
│   ├── sfx/
│   └── voice/
└── data/
```

### Kurallar

- Dosya adları küçük harf ve tire ile yazılmalı.
- Boşluk ve Türkçe karakter kullanılmamalı.
- Görseller mümkünse WebP veya optimize PNG olmalı.
- Logolar mümkünse SVG olmalı.
- Her harici varlığın kaynağı `docs/ASSET_LIST.md` içinde belirtilmeli.

## `src/`

```text
src/
├── index.ts
├── Root.tsx
├── compositions/
├── scenes/
├── components/
├── animations/
├── transitions/
├── layouts/
├── hooks/
├── utils/
├── config/
├── data/
├── types/
└── styles/
```

## `src/compositions/`

Tüm Remotion kompozisyonları burada tanımlanır.

```text
compositions/
├── BayiGoMaster.tsx
├── BayiGoPreview.tsx
├── BayiGoVertical.tsx
└── ScenePreviews.tsx
```

- `BayiGoMaster.tsx`: 1920x1080 final film
- `BayiGoPreview.tsx`: düşük kalite hızlı ön izleme
- `BayiGoVertical.tsx`: 1080x1920 dikey sürüm
- `ScenePreviews.tsx`: sahneleri ayrı ayrı render etmek için

## `src/scenes/`

Her ana sahne ayrı klasörde geliştirilir.

```text
scenes/
├── Scene01Problem/
│   ├── Scene01Problem.tsx
│   ├── timeline.ts
│   └── content.ts
├── Scene02Reveal/
├── Scene03Market/
├── Scene04Media/
├── Scene05Value/
└── Scene06Final/
```

Her sahne:

- Kendi zaman çizelgesine sahip olmalı.
- Merkezi renk ve tipografi sistemini kullanmalı.
- Doğrudan asset yolu yazmamalı.
- Tek başına render edilebilir olmalı.

## `src/components/`

Tekrar kullanılabilir görsel parçalar.

```text
components/
├── BrandLogo.tsx
├── BrowserFrame.tsx
├── PhoneFrame.tsx
├── DashboardCard.tsx
├── AnimatedCounter.tsx
├── KineticText.tsx
├── Cursor.tsx
├── NotificationStack.tsx
├── ProgressTracker.tsx
├── GlowOrb.tsx
└── SafeArea.tsx
```

## `src/animations/`

Animasyon yardımcıları ve ortak hareket tarifleri.

```text
animations/
├── easing.ts
├── springs.ts
├── reveals.ts
├── parallax.ts
├── counters.ts
├── camera.ts
├── motionBlur.ts
└── stagger.ts
```

## `src/transitions/`

```text
transitions/
├── BlurTransition.tsx
├── MaskTransition.tsx
├── LightSweepTransition.tsx
├── CameraPushTransition.tsx
└── FadeTransition.tsx
```

Geçişler kısa, akıcı ve mesajı destekleyici olmalı.

## `src/config/`

```text
config/
├── brand.ts
├── video.ts
├── audio.ts
├── typography.ts
├── timing.ts
└── assets.ts
```

Tüm ortak değerler buradan yönetilmeli:

- FPS
- çözünürlük
- toplam süre
- renkler
- fontlar
- ses seviyeleri
- asset yolları
- sahne başlangıç ve bitiş kareleri

## `src/data/`

Videoda gösterilen metinler ve örnek veriler burada tutulur.

```text
data/
├── market.ts
├── media.ts
├── benefits.ts
└── voiceover.ts
```

Metinleri bileşen içine gömmek yerine buradan çağır.

## `scripts/`

```text
scripts/
├── generate-tts.ts
├── validate-assets.ts
├── render-scenes.ts
├── render-preview.ts
├── render-final.ts
├── render-vertical.ts
└── concat-scenes.sh
```

## `render/`

Geçici ve sahne bazlı render çıktıları.

```text
render/
├── scene-01.mp4
├── scene-02.mp4
├── scene-03.mp4
├── scene-04.mp4
├── scene-05.mp4
└── scene-06.mp4
```

Bu klasör Git tarafından izlenmemelidir.

## `output/`

Teslim edilecek son dosyalar.

```text
output/
├── bayigo-preview.mp4
├── bayigo-final-1080p.mp4
├── bayigo-final-vertical.mp4
└── manifest.json
```

## Mimari kurallar

1. Sahne bileşenleri 300 satırı aşmamalı.
2. Tekrarlanan animasyon kodları ortak yardımcıya taşınmalı.
3. Tüm süre hesapları frame tabanlı olmalı.
4. Rastgele değer gerekiyorsa deterministik seed kullanılmalı.
5. Render sırasında internet bağlantısına ihtiyaç duyulmamalı.
6. Tüm assetler render öncesinde yerelde bulunmalı.
7. Yatay ve dikey sürüm aynı veri ve sahne sistemini paylaşmalı.
8. Her sahne hata durumunda diğerlerinden bağımsız render edilebilmeli.
