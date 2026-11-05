# Travel Album · LOS ANGELES

A single-file travel album from Los Angeles, July 2025: the Santa Monica pier and the Venice boardwalk, a day at Disney California Adventure, the Getty on its hill, Hollywood, Griffith Park and Beverly Hills, the pink walls of Melrose, and two sunsets. Thirty-six photos flow around a square ring, with a dotted LOS ANGELES in the middle. The dots are little stars, like the Walk of Fame; they spin as they scatter from the mouse and bounce back. Six chapters scroll sideways: Boardwalk, Make-Believe, Travertine, Signs, Pink and Sundown.

## Interactions

- **Photo ring.** Scroll, swipe or use the arrow keys to push the ring; it glides to a stop. Hover a photo and the dot word becomes that chapter's name, painted in that photo's colors. On touch screens, tap once to preview and again (or tap "Enter …") to go in.
- **Chapters.** Horizontal inertial scrolling, photos at their true aspect ratio. The print bench reprints the whole chapter live: `Original / Neon / Sunset / Blocks` (keys 1–4). Neon bends each photo's edges into glowing pink tubes over a dark street, like the Cozy Cone Motel sign after dark; Sunset re-lights every photo through the colors of the Santa Monica sunset; Blocks also shows each photo's five main colors.
- **Viewer.** Click any photo and particles fly out of the thumbnail, then develop from coarse to fine. The loupe always shows the original pixels, with the hex value under the pointer and the five-color palette (click to copy). ← → switch photos, 1–4 switch print style, Esc closes. `#/ch/N/M/view` links straight to a photo.
- **Sound.** Everything is synthesized live in the browser; there are no audio files. Each chapter has its own ambience: surf, gulls and a tremolo-picked surf guitar in Boardwalk, a parade march on glockenspiel and snare in Make-Believe, water and a slow vibraphone in Travertine, traffic, car horns and a muted trumpet in Signs, a 116 BPM synth-pop loop in Pink, and crickets with an electric piano in Sundown. The scale is D Mixolydian, and the ring plays an original surf-pop hook as it turns. Sound starts on your first tap or key press; the Sound button turns it off.

## Run locally

Use a local server. If you double-click `index.html`, the browser won't let the page read photo pixels. The home-page tint still works from `photos/tints.js`, but print styles and the viewer need the server.

```bash
python -m http.server 8765
```

Then open http://localhost:8765. Fonts load from Google Fonts on first visit.

## Change the photos

- `photos/sq/` holds 640×640 squares for the ring.
- `photos/full/` holds the same photos at 1600 px on the long edge, for chapters and the viewer. File names match between the two folders.
- Chapters, photos and captions live in `CHAPTERS` near the top of `index.html`. Title, home word, font, scale and motion live in `THEME` next to it.
- To regenerate both folders from originals, run `prepare_photos.py` from the photo-album skill. It also rebuilds `photos/tints.js`.
- If you replace files in `photos/sq/` by hand, rerun `bake_tints.py`.
- On Windows, run both scripts with `PYTHONUTF8=1` set, or they fail on the Chinese text they print.

## About page

`THEME.author` holds the name, email and social links. The contact block and the icons stay hidden until `email` and `links` are filled in.

## Style

Every color, font, motion, print style and sound comes from the photos. `style-dna.yaml` records where each decision came from, and `.dna/` holds the measurements and contact sheet behind it.

## Credits and copyright

- Photos © 2025 Howard. All rights reserved. Works of art that appear in the photos (Van Gogh's *Irises* at the Getty, murals, signs and park characters) belong to their owners.
- All melodies are original.
- The structure of the photo ring and dot word follows the open travel-album template, which credits the Framer template Squareo (Iconic Graphics) for the idea. The code is that template's, re-styled for this album.
