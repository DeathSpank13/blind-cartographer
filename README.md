# Blind Cartographer

A browser game about maps and orientation, made as a solo project for the seminar Maps and the City (Summer 2026) by Jaber Rashki Ghaleh No.

You play a courier who has to deliver the five letters of a dead mapmaker in a city you have never seen, and you have to do it without a map. You find your way by the tall landmarks that show above the fog (the lighthouse, cathedral, clock tower and windmill), by edges like the waterfront and the river, and by the character of each district. After the fifth letter the game shows the real map of the city next to your own sketch.

## Files

| File | What it is |
|---|---|
| `index.html` | The project page |
| `blind-cartographer.html` | The game, which runs in any browser |
| `report/Post-Mortem_Blind-Cartographer.html` | The post mortem report with all figures |
| `report/Post-Mortem_Blind-Cartographer.md` | The same report as plain text |
| `report/figures/` | Screenshots and design scribbles used in the report |

## How to play

Open `blind-cartographer.html` in a browser, or play it on the project page.

| Key | Action |
|---|---|
| W A S D or arrows | walk |
| E | deliver a letter at its door or continue a dialog |
| M | open your sketchbook and draw your own map |
| T | read the directions of the current letter again |
| H | help |
| R | play again (on the ending screen) |

## Preset scenes

The game can be opened with a hash to jump straight to some scenes, which is how the report figures were made: `#pose=1` (lighthouse), `#pose=2` (plaza), `#pose=3` (sketchbook) and `#pose=4` (ending). With a pose or `#debug` active, pressing N delivers the current letter right away.
