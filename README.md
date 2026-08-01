# Maritime Porthole Clock

A handcrafted analog clock built entirely in HTML5 Canvas, styled as a brass-and-iron ship's porthole chronometer. No frameworks, no dependencies — a single self-contained HTML file that runs in any modern browser and on iPhone.

---

## Preview

The clock face is modelled after a real nautical porthole: a dark iron wall plate, a radially-graduated brass flange ringed with 24 rivets, four cardinal dog-bolt caps, and a warm ivory dial with a four-pointed compass rose at its centre. Roman numerals radiate outward from the centre, each one rotated so its base faces inward — the way numerals are traditionally engraved on instrument dials.

---

## Features

- **Dual-canvas architecture** — a static layer (frame, dial, ticks, rivets) is drawn once and cached; a dynamic layer (hands, numerals, brand text) is redrawn every frame via `requestAnimationFrame`. This keeps CPU usage low while maintaining smooth 60 fps animation.
- **Smooth sweep** — all three hands move continuously using millisecond precision, not stepping second by second.
- **Responsive sizing** — the clock scales to fill any square viewport. Every radius, font size, stroke width, and shadow offset is proportional to the window size via a single scale factor `S = width / 520`.
- **Retina / HiDPI rendering** — the canvas is drawn at `devicePixelRatio` resolution, so the clock appears sharp on Retina MacBooks and iPhone screens alike.
- **iPhone compatible** — includes `viewport-fit=cover`, `apple-mobile-web-app-capable`, `env(safe-area-inset-*)` padding for the notch and home bar, touch-scroll prevention, and orientation-change handling.
- **Google Fonts** — Roman numerals use **Abril Fatface** (horizontally compressed to 50% for a tall, elegant look); brand text uses **Caladea**. Fonts are awaited via `document.fonts.ready` before the first frame is painted.
- **Add to Home Screen** — on iPhone, the file can be saved to the home screen and runs as a full-screen web app with no browser chrome.

---

## Design Details

| Element | Detail |
|---|---|
| Outer wall | Dark iron (`#1a1c24`) with subtle radial texture rings |
| Brass flange | Radial gradient from deep brass to bright gold, 27 px wide |
| Rivets | 24 on the flange + 4 cardinal bolt caps + 4 corner mounting bolts |
| Porthole frame | Iron ring with bevelled edges and a brass inner bezel |
| Dial | Warm ivory radial gradient (`#f0e8d2` → `#d4c8a8`) |
| Concentric rings | Two subtle rings at r=190 and r=182 forming a tick channel |
| Tick marks | 60 ticks between the two rings; major ticks wider |
| Numerals | Abril Fatface, rotated radially, compressed 50% horizontally |
| Compass rose | Four-pointed star with waist 8 px, drawn in the centre |
| Hands | Tapered dark polygon with a thin gold centre ridge line |
| Second hand | Slim red line with a counterweight tail |
| Centre cap | Three nested brass circles (`#c09640` → `#e8c860` → `#f8e890`) |

---

## Usage

Open [Maritime Clock](https://tengyanhaiin-star.github.io/Maritime-Clock/) directly in a browser, no build step required.

---

## Browser Support

| Browser | Status |
|---|---|
| Safari (iOS 15+) | ✅ Full support |
| Chrome / Edge | ✅ Full support |
| Firefox | ✅ Full support |
| Safari (macOS) | ✅ Full support |

---

## License

MIT — free to use, modify, and redistribute.
