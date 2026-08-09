# Table Tools

🇬🇧 [English](https://github.com/Kevinr99089/Table-Tools/blob/main/README.md) | 🇫🇷 [Français](https://github.com/Kevinr99089/Table-Tools/blob/main/README_fr.md)

**Live app:** https://kevinr99089.github.io/Table-Tools/

Single-file web app (HTML/CSS/JS, no external dependencies) for keeping score in tabletop and board games on a phone or tablet, sitting on the table during play. Interface in French or English depending on the browser's language, with a hand-drawn visual style. Published via GitHub Pages and installable as a PWA.

## Main features

- **8 score games**, each with a tailored sheet and rules available via the `?` button:
  - Belote (Us / Them)
  - Yams / Yahtzee (automatic ≥63 bonus)
  - Tarot (contract + deals)
  - Rummy (cards left in hand = penalty)
  - Uno (highest score wins, ends at 500)
  - Scrabble (turn by turn)
  - Skyjo (lowest score wins, ends at 100)
  - Mölkky (exactly 50 points, drops back to 25 if exceeded)
- **1 categories game**: "Le Bac" (random letter + built-in timer, optional exclusion of hard letters Q/U/W/X/Y/Z)
- **3 free-form sheets**: a wins tracker (round wins for checkers, chess, Connect 4...), a custom sheet (configurable number of players and rounds), and a free score sheet (generic table)
- **2 standalone tools**: a dice roller (d6) and a timer/hourglass with a flip animation; the time is set manually — tap the H/MIN/SEC value to type it directly, or use the +/− buttons on each unit
- **Every score sheet** supports adding/removing players, an optional date field, an undo button (removes the last round), and a reset button — destructive actions require a confirmation tap
- **Configurable timer alert**: choice of built-in sound (bell, whistle, drum, soft) or a custom uploaded audio file (max ~1.5 MB), adjustable volume, screen flash, and vibration (where supported)
- **Table mode**: screen wake lock (Wake Lock API, with a silent looping video fallback if the API isn't available) and fullscreen, with a reminder banner if either is lost (tab switch, etc.)
- **Automatic saving** of every sheet in progress to the browser's `localStorage` (prefix `tt15_`): nothing is lost if the page closes unexpectedly
- **Automatic bilingual UI** (FR/EN) based on the browser's language, via an internal i18n dictionary
- **Installable as a PWA**, with a home-screen icon and offline support via a service worker
- "Hand-drawn paper" design (SVG wiggle filter, handwriting-style font) built for touch use, with text selection disabled to avoid accidental highlighting

## Usage

1. Open the app at [kevinr99089.github.io/Table-Tools](https://kevinr99089.github.io/Table-Tools/) — no installation required.
2. Optionally, install it as an app from the browser menu ("Install app" / "Add to Home Screen") to get a home-screen icon and offline access.
3. Pick a game or a tool from the home screen.
4. Turn on ☀ (keep-awake) and/or ⛶ (fullscreen) if the device needs to stay on while sitting on the table.
5. Scores update automatically; the **Back** or **⌂** button returns to the home screen without losing the game in progress.

## Technical notes

- Single-file front end, no build step required.
- Hosted and served through GitHub Pages; the PWA files (`manifest.json`, `icon-192.png`, `sw.js`) are included and enable installation with a home-screen icon plus offline caching via the service worker.
- No data is sent to any server: everything stays local on the device.
