# Travel Album · Chicago

A single-file travel album from one October day in Chicago, 2025: brunch under the glass roof at RH in the Gold Coast, the lagoon, the farmers market and the zoo in Lincoln Park, then an afternoon on the University of Chicago campus in Hyde Park. Thirty-six photos flow around a square ring, with a dotted Chicago in the middle, set in a Gothic letter like the campus. The dots are little pointed arches, like the windows of Rockefeller Chapel. They lean away from the mouse and settle back slowly. Six chapters scroll sideways: Atrium, Brunch, Lagoon, Zoo, Ivy and Spires.

## Interactions

- **Photo ring.** Scroll, swipe or use the arrow keys to push the ring; it glides to a stop. Hover a photo and the dot word becomes that chapter's name, painted in that photo's colors. On touch screens, tap once to preview and again (or tap "Enter …") to go in.
- **Chapters.** Horizontal inertial scrolling, photos at their true aspect ratio. The print bench reprints the whole chapter live: `Original / Stained glass / Cutout / Blocks` (keys 1–4).
  - Stained glass cuts each photo into leaded panes, each pane one of six colors from the photo itself, lit as if the sun were behind it.
  - Cutout turns the photo into a backlit silhouette against a cobalt sky, the way the afternoon sun did to the towers.
  - Blocks also shows each photo's five main colors.
- **Viewer.** Click any photo and particles fly out of the thumbnail, then develop from coarse to fine. The loupe always shows the original pixels, with the hex value under the pointer and the five-color palette (click to copy). ← → switch photos, 1–4 switch print style, Esc closes. `#/ch/N/M/view` links straight to a photo.
- **Sound.** Everything is synthesized live in the browser; there are no audio files. Each chapter has its own ambience:
  - Atrium: the courtyard fountain, chandelier crystals and slow piano chords.
  - Brunch: a jazz trio with walking upright bass, brushes and piano over a café murmur.
  - Lagoon: wind over the water, ducks and a clarinet.
  - Zoo: the crowd, birds, honking flamingos and a skipping marimba.
  - Ivy: leaves, a solo bass line, vibraphone and the odd crow.
  - Spires: carillon bells over a low organ hum.

  The scale is D Dorian, and the ring plays an original tune on the carillon as it turns. Sound starts on your first tap or key press; the Sound button turns it off.

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

- Photos © 2025 Howard. All rights reserved. Buildings, signs and works that appear in the photos belong to their owners.
- All melodies are original.
- The structure of the photo ring and dot word follows the open travel-album template, which credits the Framer template Squareo (Iconic Graphics) for the idea. The code is that template's, re-styled for this album.
