# Power Matrix

A mobile-first strength training progression app for Bench Press, Deadlift, and Back Squat. Built as a single-file HTML app with no dependencies, hosted on Netlify with Supabase for cloud storage and authentication.

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
Sign up with email and password. Enter your best recent single rep for each lift. The app finds your conservative starting cell at **80% of your max**.

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

- **Cloud storage** — progress saves to Supabase and syncs across any device
- **Email auth** — sign up once, works across all mg42apps (Power Matrix, FitLog, and more)
- **Set checkboxes** — tap to check off each set as you complete it
- **Plate breakdown popup** — tap any weight to see exactly what to load with a visual bar diagram
- **Per-lift 1RM reset** — reset and recalibrate any single lift without touching the others
- **Jump to cell** — move to any cell without clearing history
- **Feedback prompt** — Good / Repeat / Too Heavy after completing all sets
- **LBS / KG toggle** — all weights and cell labels convert instantly
- **Reassess prompt** — surfaces every 4 weeks to update maxes
- **Full Matrix view** — all 64 cells with B/D/S badges marking current positions
- **History tab** — completed cells, progress percentage, and 1-rep progression per lift
- **Export** — downloads full progress as plain text

---

## Plate Math

All weights snap to the nearest 5 lb increment so every weight is loadable on a standard bar. Available plates: 45, 35, 25, 10, 5 lbs (or 20, 15, 10, 5, 2.5 kg). 2.5 lb plates are never required.

---

## Bug Fix — Missing Cell

The original printed Power Matrix skips from **680–685** directly to **700–705**, omitting **690–695**. This cell has been reconstructed and inserted in its correct position.

---

## Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Vanilla HTML, CSS, JavaScript — single file, zero dependencies |
| Auth | Supabase Auth (email/password) |
| Database | Supabase Postgres (`pm_progress` table) |
| Hosting | Netlify |
| DNS | Cloudflare (`powermatrix.mg42apps.com`) |
| CI/CD | GitHub Actions — push to main auto-deploys to Netlify |

---

## Database

Supabase project: `rwtgleklptqixhigbrzy` (shared with FitLog)

Table: `pm_progress` — one row per user, upserted on every save. Row Level Security enabled — users can only access their own data.

---

## PPL Split Integration

| Lift | Day |
|------|-----|
| Bench Press | Push Day |
| Deadlift | Pull Day |
| Back Squat | Leg Day |

Each lift tracks independently so they can progress at different rates.

---

## iPhone Home Screen

1. Open **powermatrix.mg42apps.com** in Safari
2. Tap Share → **Add to Home Screen**
3. Name it Power Matrix

---

## CI/CD

Every push to `main` triggers a GitHub Actions workflow that deploys to Netlify automatically. No manual file uploads needed.

---

## Files

| File | Description |
|------|-------------|
| `index.html` | App served by Netlify |
| `power_matrix.html` | Source copy |
| `README.md` | This file |
| `.github/workflows/deploy.yml` | Auto-deploy workflow |
