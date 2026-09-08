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
- Battles resolve by troop strength × the commanding general's War/Lead stats + luck.
- **End Turn** collects gold/food income, feeds your armies, and lets the AI
  houses (Wei, Wu and the independent warlords) recruit and attack.
- Win by uniting all under heaven under Shu.

### Under the hood
- **Map:** a weighted-Voronoi dot grid forms a China-shaped landmass; province
  adjacency is an explicit graph so every region is reachable.
- **Portraits:** `buildFace()` composes a 16×18 pixel grid from parametric
  features (headgear, beard, faction armour); `drawFace()` renders it as dots.
- Single committed CRT aesthetic (Press Start 2P + VT323, phosphor-green on navy).

`assets/portraits/*.png` are earlier high-res concept art, kept only as visual
reference — the game itself does not load them.
