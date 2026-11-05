# Howard's Travel Albums

Interactive single-file photo albums, one per trip. Each album is a self-contained static site: a ring of photos around a dotted title word, sideways-scrolling chapters, live print styles, a particle-developing photo viewer with a loupe, and sound synthesized in the browser. The colors, type, motion and sound of every album are derived from its own photos.

## Albums

| Album | Trip | Photos | Chapters |
| --- | --- | --- | --- |
| [`paris-2026/`](paris-2026/README.md) | Paris, May 2026 | 34 | Stone, Lattice, Gallery, Terrace, Sweet, Blue hour |
| [`tokyo-2026/`](tokyo-2026/README.md) | Echigo-Yuzawa & Tokyo, February 2026 | 35 | Snow 雪, Shrine 社, First bloom 桜, Glass 鏡, Bowls 麺, Lights 灯 |
| [`lake-geneva-2025/`](lake-geneva-2025/README.md) | Milwaukee, Holy Hill & Lake Geneva, Wisconsin, October 2025 | 36 | Big Sky, Spires, Steamboats, Glitter, Sweet, Dusk |

Each album's README covers its interactions, sound design and how to swap photos.

## Run locally

There is no build step and no dependencies. Serve an album folder over HTTP; opening `index.html` directly from disk blocks pixel reads, so print styles and the viewer stop working.

```bash
cd paris-2026        # or tokyo-2026
python -m http.server 8765
```

Then open http://localhost:8765. Fonts load from Google Fonts on first visit.

## Album layout

```
<album>/
├── index.html        # the whole site: HTML, CSS, JS; CHAPTERS and THEME near the top
├── photos/
│   ├── sq/           # 640×640 squares for the ring
│   ├── full/         # 1600 px long edge, for chapters and the viewer
│   └── tints.js      # baked 32×32 color samples, used when pixels can't be read
├── style-dna.yaml    # where each color, font, motion and sound decision came from
├── .dna/             # measurements and contact sheet behind style-dna.yaml
└── README.md
```

## Adding an album

Albums are generated with the `photo-album` Claude Code skill: point it at a folder of trip photos and it produces a new `<city>-<year>/` folder in this layout. Its `prepare_photos.py` builds `photos/sq/`, `photos/full/` and `photos/tints.js`; on Windows run it with `PYTHONUTF8=1`.

## Credits and copyright

- Photos © 2026 Howard. All rights reserved.
- The photo ring and dot-word structure follow the open travel-album template, which credits the Framer template Squareo (Iconic Graphics) for the idea.
