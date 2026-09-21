# dynassty-assets

## Dynasty Tactics — a dot-matrix Three Kingdoms war console

A turn-based strategy prototype set in the Three Kingdoms era of China, drawn
entirely as an **LED / dot-matrix screen** — the map *and* the general portraits
are rendered as dots on a `<canvas>`. **No image files are used**; every face is
generated procedurally in code (with signature dot-portraits for Liu Bei,
Cao Cao and Sun Ce).

**Play it:** open [`game/index.html`](game/index.html) in any modern browser.
It is a single self-contained file (fonts load from Google Fonts).

Works on desktop and **phone** (portrait) — everything is tap-driven, no double-click.

### How to play
- **Select** one of your provinces (green = House Shu) on the map.
- **✚ Recruit** troops with gold, **➜ Move** troops to a neighbouring friendly
  province, or **⚔ Attack** a neighbouring enemy province.
- **Armies of up to 4 officers:** press OFFICERS on one of your provinces to open
  the roster (ROTK-style dot-portraits) and tap to add/remove your Shu generals —
  Liu Bei, Guan Yu, Zhang Fei, Zhao Yun. The **commander is the highest-level
  officer**, and their **level sets how many officers the army may hold** (Lv N →
  N slots, up to 4).
- **Levels & growth:** each general has a level (shown as `Lv N`). Winning battles
  grants XP; on level-up their War/Int/Cha/Lead rise and the army can hold one more
  officer. Generals start at set ranks (e.g. Cao Cao and Lü Bu at Lv 4).
- **Battles** resolve by troop strength × the commander's War/Lead + **35 % of each
  other officer's War** + luck. Winning an assault marches the whole army into the
  conquered province; the defenders' officers are captured and leave play.
- **End Turn** collects gold/food income, feeds your armies, and lets the AI
  houses (Wei, Wu and the independent warlords) recruit and attack.
- Win by uniting all under heaven under Shu.

### Under the hood
- **Map:** a domain-warped weighted-Voronoi raster forms filled provinces with
  black borders and a dithered blue sea (DOS *Romance of the Three Kingdoms*
  look); each province has its own base tone blended toward its owner's faction
  colour, and adjacency is an explicit graph so every region is reachable.
- **Portraits:** `buildFace()` composes a shaded 32×40 pixel bust from parametric
  features (light/shadow modelling, brows/eyes/nose/mouth, headgear, beard, faction
  armour, ink outline); `drawFace()` renders it as dots — no image files.
- Single committed CRT aesthetic (Press Start 2P + VT323, phosphor-green on navy).

`assets/portraits/*.png` are earlier high-res concept art, kept only as visual
reference — the game itself does not load them.
