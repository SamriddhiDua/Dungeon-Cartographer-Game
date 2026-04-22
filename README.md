# Dungeon-Cartographer-Game
A procedurally generated dungeon explorer where you draw your own map as you go. BSP tree generation, fog of war, and an end-game accuracy scorecard. Built with vanilla HTML/CSS/JS.
# Dungeon Cartographer

A browser-based dungeon exploration game where **you draw the map as you go.**
Dungeons are procedurally generated using a **BSP (Binary Space Partitioning) tree** algorithm.
At the end, your hand-drawn map is scored against the real dungeon layout.

---

## Gameplay

- Explore a procedurally generated dungeon — rooms are hidden behind **fog of war**
- As you explore, **draw your own map** on the mini-grid overlay using your mouse/touch
- Avoid monsters roaming the corridors
- Collect treasure hidden in rooms
- When you exit or die, a **scorecard** reveals how accurate your map was

---

## How the Dungeon is Generated (BSP Tree)

1. The dungeon canvas is recursively split into two sub-regions (horizontal or vertical)
2. Splitting continues until regions reach a minimum size threshold
3. A room is carved inside each leaf node (with padding)
4. Sibling leaf nodes are connected by L-shaped corridors
5. This guarantees every room is reachable

---

## Scorecard Metrics

| Metric | Description |
|---|---|
| **Map Accuracy %** | Overlap between your drawn map and actual room layout |
| **Rooms Explored** | How many rooms you entered out of total |
| **Monsters Avoided** | Monsters you successfully bypassed |
| **Treasure Found** | Collectibles picked up during the run |

---

## Getting Started

```bash
git clone https://github.com/YOUR_USERNAME/dungeon-cartographer.git
cd dungeon-cartographer
# Open index.html in any modern browser — no build step required
```

Or just visit the **[Live Demo →](https://SamriddhiDua.github.io/Dungeon-Cartographer-Game)**

---

## Controls

| Key | Action |
|---|---|
| `W A S D` / Arrow Keys | Move player |
| `Left Click` (on mini-map) | Draw on your map |
| `Right Click` (on mini-map) | Erase on your map |
| `E` | Interact / collect treasure |
| `Esc` | Pause / toggle map overlay |

---

## Tech Stack

- **Vanilla HTML5 / CSS3 / JavaScript** — zero dependencies
- **Canvas API** — dungeon rendering & fog of war
- **BSP Tree Algorithm** — procedural dungeon generation

---

## Map Accuracy Algorithm

The scoring compares two binary grids:
- **Ground truth grid** — all revealed room tiles from the actual dungeon
- **Player drawn grid** — tiles marked on the mini-map overlay

```
Accuracy = (Matching "room" cells / Total actual room cells) × 100
```

Penalties apply for false positives (drawing walls as rooms).

---

## Roadmap

- [ ] Seed sharing (replay same dungeon)
- [ ] Multiple dungeon depths / floors
- [ ] Compass item that reveals partial map
- [ ] Leaderboard (localStorage high scores)
- [ ] Mobile touch controls

---

## License

MIT — free to use, modify, and distribute.
