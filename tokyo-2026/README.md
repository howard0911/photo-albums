# Travel Album · TOKYO

A single-file travel album from February 2026: the snow of Echigo-Yuzawa, then Tokyo's first cherry blossoms and its lit-up winter nights. Thirty-five photos flow around a square ring. In the middle, TOKYO is built from tiny pink petals that scatter from the mouse and drift back. Six chapters scroll sideways: Snow 雪, Shrine 社, First bloom 桜, Glass 鏡, Bowls 麺, Lights 灯.

## Interactions

- **Photo ring.** Scroll, swipe or use the arrow keys to push the ring; it glides to a stop. Hover a photo and the petals regroup into that chapter's name, colored from that photo. On touch screens, tap once to preview and again (or tap "Enter …") to go in.
- **Chapters.** Horizontal inertial scrolling, photos at their true aspect ratio. The print bench reprints the whole chapter live: `Original 原 / Riso 刷 / Sumi 墨 / Blocks 色` (keys 1–4).
  - Riso prints in the sakura pink and the Yuzawa sky blue.
  - Sumi turns each photo into an ink line drawing.
  - Blocks also shows each photo's five main colors.
- **Viewer.** Click any photo and particles fly out of the thumbnail, then develop from coarse to fine. The loupe always shows the original pixels, with the hex value under the pointer and the five-color palette (click to copy). ← → switch photos, 1–4 switch print style, Esc closes. `#/ch/N/M/view` links straight to a photo.
- **Sound.** Everything is synthesized live in the browser in the Japanese yo scale; there are no audio files. Each chapter has its own sound:
  - Snow: mountain wind and a breathy flute
  - Shrine: a temple bell, shrine suzu bells and koto
  - First bloom: koto and a bush warbler
  - Glass: the crowd, soft synth and the Shibuya crossing chirp
  - Bowls: sizzle and wood blocks
  - Lights: a music box

  Sound starts on your first tap or key press; the Sound button turns it off.

## Run locally

Use a local server. If you double-click `index.html`, the browser won't let the page read photo pixels, so the print styles and the viewer stop working.

```bash
python -m http.server 8766
```

Then open http://localhost:8766. Fonts load from Google Fonts on first visit.

## Change the photos

- `photos/sq/` holds 640×640 squares for the ring.
- `photos/full/` holds the same photos at 1600 px on the long edge, for chapters and the viewer. File names match between the two folders.
- Chapters, photos and captions live in `CHAPTERS` near the top of `index.html`. Title, home word, font, scale and motion live in `THEME` next to it.
- To regenerate both folders from originals, run `prepare_photos.py` from the photo-album skill. It also rebuilds `photos/tints.js`.
- If you replace files in `photos/sq/` by hand, rerun `bake_tints.py`.
- On Windows, run both scripts with `PYTHONUTF8=1` set.

## About page

`THEME.author` holds the name, email and social links. The contact block and the icons stay hidden until `email` and `links` are filled in.

## Style

Every color, font, motion, print style and sound comes from the photos. `style-dna.yaml` records where each decision came from, and `.dna/` holds the measurements and contact sheet behind it.

## Credits and copyright

- Photos © 2026 Howard. All rights reserved.
- The structure of the photo ring and dot word follows the open travel-album template, which credits the Framer template Squareo (Iconic Graphics) for the idea. The code is that template's, re-styled for this album.
