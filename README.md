# TableTools

🇬🇧 [English](https://github.com/Kevinr99089/Table-Tools/blob/main/README.md) | 🇫🇷 [Français](https://github.com/Kevinr99089/Table-Tools/blob/main/README_fr.md)

Single-file web app (HTML/CSS/JS, no external dependencies) for keeping score in tabletop and board games on a phone or tablet, sitting on the table during play. Interface in French or English depending on the browser's language, with a hand-drawn visual style.

## Main features

- **13 ready-to-use scoring games**, each with a tailored sheet and rules available via the `?` button:
  - Belote (Us / Them)
  - Yams / Yahtzee (automatic ≥63 bonus)
  - Tarot (contract + deals)
  - Rummy (cards left in hand = penalty)
  - Uno (highest score wins, ends at 500)
  - Scrabble (turn by turn)
  - Categories / "Le Bac" (random letter + built-in timer, optional exclusion of hard letters Q/W/X/Y/Z)
  - 421 (3 dice + scoresheet)
  - Mölkky (exactly 50 points, drops back to 25 if exceeded)
  - Skyjo (lowest score wins, ends at 100)
  - Pétanque (Us / Them, up to 13)
  - Wins tracker (round wins for checkers, chess, Connect 4...)
  - Custom sheet (configurable number of players and rounds)
  - Free score (generic sheet)
- **2 standalone tools**: a dice roller (d6) and a timer/hourglass with a flip animation and presets (30s to 5min), plus manual h/min/s adjustment.
- **Table mode**: screen wake lock (Wake Lock API, with a silent looping video fallback if the API isn't available) and fullscreen, with a reminder banner if either is lost (tab switch, etc.).
- **Automatic saving** of every sheet in progress to the browser's `localStorage` (prefix `tt15_`): nothing is lost if the page closes unexpectedly.
- **Automatic bilingual UI** (FR/EN) based on the browser's language, via an internal i18n dictionary.
- "Hand-drawn paper" design (SVG wiggle filter, handwriting-style font) built for touch use, with text selection disabled to avoid accidental highlighting.

## Usage

1. Open `ScoreTable.html` in a browser (double-click or serve it as a static file).
2. Pick a game or a tool from the home screen.
3. Turn on ☀ (keep-awake) and/or ⛶ (fullscreen) if the device needs to stay on while sitting on the table.
4. Scores update automatically; the **Back** or **⌂** button returns to the home screen without losing the game in progress.

## Technical notes

- Single file, no installation or build step required.
- The HTML references `manifest.json`, `icon-192.png`, and `sw.js` (for use as an installable PWA with an icon and offline service worker), but these files are **not included** in `ScoreTable.html`: the app works perfectly fine without them (loading errors are silently ignored), but you'll need to add them separately if you want to install it as a proper home-screen app.
- No data is sent to any server: everything stays local on the device.
