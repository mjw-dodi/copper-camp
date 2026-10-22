# Copper Camp — Survive the Butte Hill, 1906–1917

A browser survival game set in the mines and streets of Butte, Montana. Pick an immigrant origin (Irish, Cornish, Finnish, Italian, Serbian, or Chinese), take a job, and try to still be standing in Winter 1917.

**Play it:** `https://YOUR-USERNAME.github.io/copper-camp/` (after you enable GitHub Pages — see below).
The whole game is one self-contained file, `index.html`; double-click it and it runs offline.

## How it plays
- **Each season:** choose a job, work the shift, then spend three evening hours in town.
- **Every mine job is its own game:** Mucker (shovel timing), Timberman (set the swinging timber), Machine man (drill, don't jam the steel), Hot box (shovel and manage heat and ice), Trammer (push and brake the ore car).
- **Crew and boss:** a dry-room scene before each shift and a dinner-pail break halfway, with partner, greenhorn, Wobbly, boss and rumors.
- **Town:** walk Uptown or click a destination; ten interiors (the M&M, Union Hall, church, library, sauna, hospital and more).
- **Watch:** your lungs (rock dust doesn't heal), the Company's suspicion, and your standing with the men.

### Controls
| Action | Mouse / touch | Keyboard |
|---|---|---|
| Main action (dig, throw, set, drill, push) | big button | Space |
| Second action (straighten up, ice, brake) | second button | B |
| Walk | West / East buttons or "Walk to" chips | arrow keys / A, D |
| Go inside | "Go inside" | Enter |
| Pick a choice | click | number keys 1–9 |

Sound is off by default (button in the header). Progress autosaves in your browser.

## Repo layout
- `index.html` — the finished game (textures and sound embedded, about 5 MB)
- `source/copper-camp.html` — the game without embedded assets (in-code textures, synthesized sound)
- `assets/textures/` — textures baked in Blender and post-processed
- `tools/` — scripts to bake textures (Blender), generate sound (ElevenLabs), and embed both
- `tests/bot.js` — headless bot that plays full games and reports crashes, dead ends and balance (`node tests/bot.js index.html motion 10 777`)

## Rebuilding
1. `/Applications/Blender.app/Contents/MacOS/Blender -b -P tools/copper_camp_bake.py`
2. `python3 tools/copper_camp_process_textures.py textures/`
3. `python3 tools/copper_camp_apply_textures.py source/copper-camp.html textures/`
4. `ELEVENLABS_API_KEY=... python3 tools/copper_camp_gen_audio.py`, then `python3 tools/copper_camp_apply_audio.py source/copper-camp-blender.html audio/`

(`audio/` is git-ignored: check the license terms of your ElevenLabs plan before publishing the raw clips.)

## History and fiction
The events, places and dates are real: the 1907 Panic, the rustling card, the 1914 Union Hall dynamiting and martial law, the 1917 Granite Mountain fire and Frank Little's lynching. The Copper Kings (Vance, Brandt, Hobart) and their men are invented, loosely modeled on the real fight over the hill.

## License
Add a license before inviting contributions. Without one, all rights are reserved.
