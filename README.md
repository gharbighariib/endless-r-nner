# Endless rünner

**Stable Build** — a small HTML5 canvas endless-runner with a shop, skins, save system, and rewarded-ad friendly hooks.

---

## Project Overview

This is a single-file HTML5 game (`HTML + CSS + JS`). Players dodge enemies, collect coins, pick up power-ups, and unlock cosmetic skins via an in-game shop. Save data is persisted to `localStorage` so coins, unlocked skins, and high score survive across sessions.

Key quality-of-life and safety features:

* Touch input corrected to use `canvas.getBoundingClientRect()` (ensures touch works on non-full-width canvases).
* Auto-pause when the tab/window loses focus (`visibilitychange` / `blur`) with a visible "PAUSED" overlay.
* High score is saved to and displayed from `localStorage` (start screen + game over screen). Shows a "NEW HIGH SCORE!" badge when beaten.

---

## Files

* `index.html` — single-file game containing HTML, CSS, and JS. Can be renamed or embedded into your repo as `index.html`.

---

## How to Run (Local)

1. Clone or download the repo.
2. Open `index.html` in a modern browser (Chrome, Edge, Firefox recommended).

> For local testing of service workers (if adding a PWA later), use a static server like `npx http-server`. Otherwise, opening directly works fine.

---

## Controls

* **Keyboard:** `ArrowLeft` / `ArrowRight` or `A` / `D`
* **Touch:** Tap or drag on the left/right half of the canvas to move.

---

## Game Features

* Difficulty modes: **Easy / Normal / Hard** (affects enemy speed and spawn rate)
* Enemies, coins, and power-ups (slow, coin x2)
* Floating text and HUD badges for visual feedback
* Cosmetic shop with unlockable skins (prices defined in `COLORS` array)
* Save data: `coins`, `highScore`, `unlockedColors`, `selectedColor`
* Auto-pause overlay on tab blur/visibility change

---

## Save Data Format (`localStorage` key: `endlessRunnerSave`)

```json
{
  "coins": 0,
  "highScore": 0,
  "unlockedColors": ["cyan"],
  "selectedColor": "cyan"
}
