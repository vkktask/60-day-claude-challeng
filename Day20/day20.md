# 🧩 AI Face Puzzle Game — Day 20 Report
> **60 Days of AI · Day 20** | Built with Claude AI | Tool: Face Puzzle Game

---

## 📌 Overview

The AI Face Puzzle Game is a fully interactive, single-file HTML application that turns your own face into a sliding puzzle game. It uses the browser's webcam API to capture a photo, slices it into a grid, scrambles the pieces, and challenges you to reassemble it as fast as possible.

**Stages:**
1. **Camera** — Live webcam feed with face-guide oval, snapshot capture
2. **Difficulty** — Choose 3×3, 4×4, or 5×5 grid with photo preview
3. **Game** — Drag-and-drop puzzle with live timer, move counter, progress bar
4. **Win** — Results overlay, confetti, top-5 leaderboard saved to localStorage

---

## 🎮 Features Built

### 📸 Camera Access
- `getUserMedia()` with `facingMode: 'user'` for front-facing camera
- Mirrored live video preview with animated dashed oval face guide
- Canvas snapshot with mirroring correction (un-mirrors the flipped CSS video)
- Graceful error handling when permission is denied

### 🧩 Puzzle Generation
- **3 difficulty levels**: 3×3 (9 pieces), 4×4 (16 pieces), 5×5 (25 pieces)
- Fisher-Yates shuffle for guaranteed random scramble
- Detects already-solved state and re-shuffles to ensure the game starts scrambled
- Each piece rendered as an individual `<canvas>` element with pixel-precise cropping

### 🖱️ Drag & Touch Controls
| Control | Desktop | Mobile |
|---------|---------|--------|
| Pick up piece | `mousedown` | `touchstart` |
| Track drag | `mousemove` | `touchmove` |
| Drop & swap | `mouseup` | `touchend` |
| Highlight dragging | Indigo border + scale | Same |
| Hover target | Purple border | Same |
| Correct position | Green border glow | Same |

### ⏱️ Timer & Stats
- Real-time timer: `mm:ss.t` format (tenths of a second)
- Move counter increments on every valid swap
- "Correct pieces" counter + animated progress bar
- All stats update instantly after each move

### 🏆 Win Screen
- Auto-detects when all pieces match `currentIdx === correctIdx`
- Confetti particle system (120 particles, physics-based fall)
- Dynamic win message based on time and move count
- Top 5 leaderboard saved to `localStorage` sorted by fastest time
- Shows date, time, moves, difficulty for each entry

---

## 📊 Technical Highlights

### Single-File Architecture
- Pure HTML/CSS/JS — zero external dependencies
- All styling via CSS custom properties for consistent theming
- ~350 lines of JS, ~250 lines of CSS

### State Machine
```
Camera Screen → Difficulty Screen → Game Screen → Win Overlay
     ↑               ↑                  ↑              |
     └───────────────┴──────────────────┴──────────────┘
           (Retake / New Photo / Play Again)
```

### Key Algorithms
- **Image slicing**: `drawImage(src, sx, sy, sw, sh, 0, 0, dw, dh)` per piece
- **Scramble**: Fisher-Yates in-place shuffle tracking `currentIdx` per piece
- **Swap**: Find pieces by `currentIdx`, exchange values, re-render
- **Win check**: `pieces.every(p => p.currentIdx === p.correctIdx)`
- **Confetti**: RAF loop with velocity + gravity simulation

### Camera Mirror Fix
The `<video>` element is CSS-flipped (`transform: scaleX(-1)`) for a natural mirror view. During snapshot, the canvas draw uses `ctx.scale(-1, 1)` + `ctx.translate(width, 0)` to un-mirror and capture the correct orientation.

---

## 💡 Key Learnings

1. **getUserMedia is powerful but needs HTTPS** — works on localhost without SSL; production requires HTTPS. Handled gracefully with a visible error message.

2. **Canvas-to-canvas drawing is fast and precise** — using individual `<canvas>` elements as puzzle pieces (rather than CSS background-position tricks) gives pixel-accurate cuts and renders cleanly at all sizes.

3. **Touch events need `preventDefault()`** — without it, browser scroll interferes with drag. `{ passive: false }` is required on the listener options.

4. **Fisher-Yates + solvability** — For non-square jigsaws (where blank tile tricks apply), you need parity checks. For this face puzzle (all pieces present, no blank tile), Fisher-Yates is always solvable — just guard against the accidentally-already-solved state.

5. **localStorage leaderboards are instant wins** — no backend needed for a satisfying progression system. Sorting by `ms` (raw elapsed) gives reliable rankings even with same `mm:ss.t` display strings.

6. **AI-generated games are genuinely playable** — the whole game was specified in a single prompt and produced a working, polished product in one pass. This is what "vibe coding" looks like at its best.

---

## 🎨 Design System

| Token | Value | Use |
|-------|-------|-----|
| `--bg` | `#0a0e1a` | Page background |
| `--surface` | `#111827` | Card background |
| `--accent` | `#6366f1` | Indigo — primary actions |
| `--accent2` | `#8b5cf6` | Purple — secondary accents |
| `--green` | `#10b981` | Correct pieces, success |
| `--gold` | `#f59e0b` | Leaderboard #1, warnings |

---

## 📱 Responsive Design
- Board size auto-calculates: `min(window.innerWidth - 80, 520)px`
- Sidebar stacks below board on screens < 680px
- Difficulty grid collapses to single column on phones
- Touch events fully supported — playable on any mobile browser

---

*Built as part of the 60 Days of AI challenge on ABTalks.in | Day 20*
*Tool: Claude AI (Cowork Mode) | Language: HTML/CSS/JavaScript*
