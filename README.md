# dynassty-assets

## Dynasty Tactics — a dot-matrix Three Kingdoms war console

A turn-based strategy prototype set in the Three Kingdoms era of China, drawn
entirely as an **LED / dot-matrix screen** — the map *and* the general portraits
are rendered as dots on a `<canvas>`. **No image files are used**; every face is
generated procedurally in code (with signature dot-portraits for Liu Bei,
Cao Cao and Sun Ce).

**Play it:** open [`game/index.html`](game/index.html) in any modern browser.
It is a single self-contained file (fonts load from Google Fonts).

### How to play
- **Select** one of your provinces (green = House Shu) on the map.
- **✚ Recruit** troops with gold, **➜ Move** troops to a neighbouring friendly
  province, or **⚔ Attack** a neighbouring enemy province.
- **Appoint a commander:** select one of your provinces and press APPOINT to open
  the officer roster (a ROTK-style row of dot-portraits) and put one of your Shu
  generals — Liu Bei, Guan Yu, Zhang Fei, Zhao Yun — in charge, or reassign them.
- Battles resolve by troop strength × the commanding general's War/Lead stats + luck.
  A conquered province's commander is captured and leaves play.
- **End Turn** collects gold/food income, feeds your armies, and lets the AI
  houses (Wei, Wu and the independent warlords) recruit and attack.
- Win by uniting all under heaven under Shu.

### Under the hood
- **Map:** a domain-warped weighted-Voronoi raster forms filled provinces with
  black borders and a dithered blue sea (DOS *Romance of the Three Kingdoms*
  look); each province has its own base tone blended toward its owner's faction
  colour, and adjacency is an explicit graph so every region is reachable.
- **Portraits:** `buildFace()` composes a 16×18 pixel grid from parametric
  features (headgear, beard, faction armour); `drawFace()` renders it as dots.
- Single committed CRT aesthetic (Press Start 2P + VT323, phosphor-green on navy).

`assets/portraits/*.png` are earlier high-res concept art, kept only as visual
reference — the game itself does not load them.
