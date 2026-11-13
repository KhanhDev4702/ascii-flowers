# ASCII Flowers — Sunflowers & Lilies

Open `index.html` directly in a browser. No dependencies or build step.

The default bouquet has six sunflowers: stems grow, broad leaves unfurl, green
buds swell, and two rings of golden petals open around brown spiral seed disks.
Ruscus and baby’s breath surround the flowers. The bloom takes about 15 seconds,
then the bouquet keeps swaying. This is an artistic time-lapse, not a botanical simulation.
The original lily scene is also available.

## Controls
- Click the bouquet, Space or R: replay.
- P / C or Colors: cycle golden yellow, sunset orange, and cream (sunflowers),
  or the original pink / white / mixed palettes (lilies).
- F or the Sunflowers / Lilies button: switch flower type.
- All controls also work with the on-screen buttons on mobile.

## URL options
- `?flower=sunflower` (default) or `?flower=lily`
- `?p=0`, `?p=1`, `?p=2`: palette
- `?t=15`: start with the flowers fully open
- Example: `index.html?flower=sunflower&p=0&t=15`

## Local server (optional)
Run `python3 -m http.server 8000` in this folder, then open
http://localhost:8000. To share publicly, upload these three files to a static host.

## Implementation
`bouquet.js` retains the original lily renderer and adds a separate sunflower
scene and geometry. Both use the same low-resolution Canvas → colored ASCII
pipeline. Layout scales to the viewport; no external fonts or network requests.

## Tulips
Use the flower button or F to cycle Sunflowers → Lilies → Tulips.
Open `index.html?flower=tulip` to start directly with tulips.
Seven tulips grow long leaves and open overlapping petals into upright cups.
P / Colors cycles pink, coral red, and lavender. Opening finishes around 15 seconds.
Use `?flower=tulip&p=2&t=16` to see the lavender bouquet fully open.

## Falling stars
Small ASCII stars twinkle and drift gently down behind all three flower types.
Enabled by default. Press S or Stars: on/off to toggle without restarting the bloom.
Use `?flower=tulip&stars=0` to start without stars; `stars=1` enables them.
The background clock is independent of the bloom replay. Star count adapts to
screen size, with masking to keep the bouquet clear.
