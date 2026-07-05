# Power Matrix

A mobile-first strength training progression app for Bench Press, Deadlift, and Back Squat. Built as a single-file HTML app with no dependencies, hosted on Netlify, and saved to iPhone home screen as a web app.

**Live app:** [powermatrix.mg42apps.com](https://powermatrix.mg42apps.com)

---

## What Is the Power Matrix

The Power Matrix is a wave-loading strength program built around three compound lifts. Each "cell" represents one week of training with a fixed 7-set prescription combining endurance, strength, and power work.

### Rep Structure Per Cell

| Set | Reps | Purpose |
|-----|------|---------|
| 1 | 8 | Endurance |
| 2 | 5 | Endurance |
| 3 | 3 | Strength |
| 4 | 1 | Power |
| 5 | 1 | Power |
| 6 | 1 | Power |
| 7 | 5 | Backoff |

### Progression Rules

- Complete all 7 sets before advancing
- If you miss any set, repeat the same cell
- Each lift tracks its own independent position
- Squat and Deadlift should never be on the same day

### Claimed Results

- **+65 lbs** Bench Press
- **+110 lbs** Squat
- **+125 lbs** Deadlift

---

## App Flow

### First Launch
Enter your best recent single rep for each lift. The app finds your conservative starting cell at **80% of your max**. The matrix stays hidden — you only see your workout.

### Every Session
Three lift tabs: Bench · Deadlift · Squat. Each shows 7 set cards with reps and total weight. Tap a set to check it off. Tap the per-side weight to see the plate breakdown.

### After All 7 Sets
A **"How did that feel?"** prompt appears with three options:
- ✅ **Good** — advance to next cell
- 🔁 **Repeat** — same cell next week
- 👇 **Too heavy** — drop back one cell

### Every 4 Weeks
A reassessment banner prompts you to update your 1-rep maxes and recalibrate.

---

## Features

- **Set checkboxes** — tap to check off each set as you complete it
- **Plate breakdown popup** — tap any per-side weight to see exactly what to load, with a visual bar diagram
- **Per-lift 1RM reset** — reset and recalibrate any single lift without touching the others
- **Jump to cell** — move to any cell in the matrix without clearing history
- **Repeat cell** — stay on the same cell for another week with one tap
- **LBS / KG toggle** — all weights convert instantly including cell identifiers
- **Reassess prompt** — surfaces every 4 weeks to update maxes
- **History tab** — completed cells, progress percentage, and 1-rep progression per lift
- **Export** — downloads full progress as a plain text file
- **Progress saved** in browser localStorage

---

## Plate Math

All weights are snapped to the nearest 5 lb increment (10 lb total — a pair of 5s) so every weight is loadable on a standard bar. Available plates: 45, 35, 25, 10, 5 lbs (or 20, 15, 10, 5, 2.5 kg). 2.5 lb plates are never required.

---

## Bug Fix — Missing Cell

The original printed Power Matrix skips from **680–685** directly to **700–705**, omitting **690–695**. This cell has been reconstructed and inserted in its correct position.

---

## PPL Split Integration

| Lift | Day |
|------|-----|
| Bench Press | Push Day |
| Deadlift | Pull Day |
| Back Squat | Leg Day |

Each lift tracks independently so they can progress at different rates.

---

## Deployment

Hosted on Netlify. To update, drag `power_matrix.html` into the existing site in the Netlify dashboard. The URL stays the same.

### iPhone Home Screen
1. Open the app URL in Safari
2. Tap Share → **Add to Home Screen**
3. Name it Power Matrix

---

## Files

| File | Description |
|------|-------------|
| `power_matrix.html` | Complete app — open in any browser |
| `README.md` | This file |

---

## Stack

Vanilla HTML, CSS, JavaScript. Single file. Zero dependencies. No build step.
