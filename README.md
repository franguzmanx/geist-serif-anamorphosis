# Geist Serif — Anamorphosis

Hundreds of Geist Serif letters float in 3D space. From one exact point of view, they line up and form the Evil Rabbit mark: a rabbit made of readable text. Move away and it breaks into chaos again.

**Live:** https://franguzmanx.github.io/geist-serif-anamorphosis/

![Letters forming the rabbit](preview.png)

Video: [geist-serif-anamorphosis-4k-hdr.mp4](geist-serif-anamorphosis-4k-hdr.mp4) — rendered from this code, 3840×2160, 60 fps, 12 s seamless loop, HDR (HEVC 10-bit, HLG / BT.2020). Best on an HDR screen (MacBook Pro, iPhone, recent TVs).

## Controls

| Action | Mouse / trackpad | Touch |
| --- | --- | --- |
| Turn in any direction | Drag | Drag |
| Zoom into the cloud | Scroll or pinch | Pinch |
| Back to the rabbit | Double-click, Space or Enter | Double-tap |

If you leave it alone, the camera wanders into the cloud and back to the rabbit by itself.

## HDR

On an HDR screen in Chrome, the page renders with WebGPU in extended range: the letters glow brighter than paper white, and get brighter still when the rabbit locks in. On other screens or browsers it falls back to WebGL in normal range. Add `?hdr` to the URL to force the WebGPU path.

The video is exported from the same file: `index.html?render` renders each 4K frame in float and encodes it as HLG.

## How it works

- Each letter is set on a line inside the rabbit silhouette, like a calligram.
- Each letter is then pushed to a random depth along the ray from the "solve" camera to its spot, and scaled by that depth. From that one camera the rabbit is exact, even while the letters drift.
- Off-axis, each letter also spins on itself. The spin fades to zero as you come back to the solve angle.
- One instanced mesh and one glyph atlas, rendered with [three.js](https://threejs.org).

It is one self-contained file: `index.html`. The font is embedded. three.js loads from a CDN, so you need a connection. To run it locally, open `index.html` in a browser.

## Credits

- Typeface: [Geist Serif](https://vercel.com/font) by Vercel with basement.studio, under the SIL Open Font License 1.1 (see `FONT-LICENSE.txt`).
- The rabbit mark belongs to its owner and is not covered by any open license here.
