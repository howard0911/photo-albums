# Travel Album · SoCal

A single-file travel album from Southern California, Christmas 2025: Christmas Day in Los Angeles, a rainy Malibu and Point Dume, Santa Barbara's courthouse and mission, a golden evening at Laguna Beach, then La Jolla and Balboa Park under a hard blue San Diego sky. Thirty-six photos flow around a square ring, with a dotted SoCal in the middle. The dots are little diamonds, like the courthouse tile and the star on the Balboa tree; they tilt as they scatter from the mouse, spring back, and now and then one flares like a bulb. Six chapters scroll sideways: Tinsel, Rain, Red Roofs, Golden, Cobalt and Feast.

## Interactions

- **Photo ring.** Scroll, swipe or use the arrow keys to push the ring; it glides to a stop. Hover a photo and the dot word becomes that chapter's name, painted in that photo's colors. On touch screens, tap once to preview and again (or tap "Enter …") to go in.
- **Chapters.** Horizontal inertial scrolling, photos at their true aspect ratio. The print bench reprints the whole chapter live: `Original / Tile / Screen print / Blocks` (keys 1–4). Tile lays each photo in glazed squares of its own eight colors with white grout; Screen print pulls four flat inks, ink black, two inks mixed from the photo's mid-tones, and bare paper, slightly off-register; Blocks also shows each photo's five main colors.
- **Viewer.** Click any photo and particles fly out of the thumbnail, then develop from coarse to fine. The loupe always shows the original pixels, with the hex value under the pointer and the five-color palette (click to copy). ← → switch photos, 1–4 switch print style, Esc closes. `#/ch/N/M/view` links straight to a photo.
- **Sound.** Everything is synthesized live in the browser; there are no audio files. Each chapter has its own ambience: a fire crackling with sleigh bells and carols on handbells in Tinsel, heavy surf and rain in Rain, a courtyard fountain and nylon guitar in Red Roofs, waves, ukulele and slide steel guitar in Golden, a fountain, marimba, gulls and sea lions in Cobalt, and a dining room with a walking bass, electric piano and mahjong tiles in Feast. The scale is C major, and the ring plays Joy to the World as it turns. Sound starts on your first tap or key press; the Sound button turns it off.

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

- Photos © 2025 Howard. All rights reserved.
- The ring melody is "Antioch" (Joy to the World); the Tinsel chapter plays phrases of Deck the Halls, Silent Night, O Come All Ye Faithful and Jingle Bells. All are traditional carols in the public domain.
- The structure of the photo ring and dot word follows the open travel-album template, which credits the Framer template Squareo (Iconic Graphics) for the idea. The code is that template's, re-styled for this album.
