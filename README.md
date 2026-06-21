# Power Matrix

A strength training progression tracker for Bench Press, Deadlift, and Back Squat based on the Power Matrix program. Built as a single-file HTML app with no dependencies, hosted on Netlify, and saved to iPhone home screen as a web app.

---

## What Is the Power Matrix

The Power Matrix is a wave-loading strength program built around three compound lifts. Each "cell" in the matrix represents one week of training. Cells are organized by weight range and contain a fixed 7-set prescription that combines endurance, strength, and power work in a single session.

### Rep Structure Per Cell

| Set | Reps | Type |
|-----|------|------|
| 1 | 8 | Endurance |
| 2 | 5 | Endurance |
| 3 | 3 | Strength |
| 4 | 1 | Power |
| 5 | 1 | Power |
| 6 | 1 | Power |
| 7 | 5 | Backoff |

Sets 1–2 build muscle endurance. Sets 3 builds strength. Sets 4–6 are max effort singles at the cell's peak weight. Set 7 is a backoff flush at the same weight as Set 2.

### Progression Rules

- Complete all 7 sets exactly as prescribed before advancing to the next cell
- If you miss any set, repeat the same cell the following week
- Never skip a cell — each one bridges to the next
- Squat and Deadlift should never be trained on the same day
- Each lift (Bench, Deadlift, Squat) tracks its own independent position in the matrix

### Claimed Results

Per the original program documentation, completing the full matrix adds approximately:
- **+65 lbs** to Bench Press
- **+110 lbs** to Squat
- **+125 lbs** to Deadlift

---

## The App

### Features

- **This Week view** — shows all three lifts side by side with weights pre-filled, formatted for easy entry into Strong or any training log
- **Full Matrix view** — all 64 cells displayed in a 7-column grid with color-coded set types (endurance, strength, power, backoff)
- **Independent tracking** — Bench, Deadlift, and Squat each hold their own position
- **B / D / S badges** — visible on the matrix so you can see all three current positions at a glance
- **Copy button** — copies the week's sets as plain text for pasting into notes or a training log
- **Advance controls** — advance one lift at a time or all three at once
- **Jump to weight** — search box to scroll directly to any weight range
- **Progress tracking** — shows cells completed out of 64 per lift

### How to Use

1. Open the app and go to the **Full Matrix** tab
2. Select **Bench** and tap your starting cell
3. Switch to **Deadlift** and tap its starting cell
4. Switch to **Squat** and tap its starting cell
5. Go to the **This Week** tab to see your complete week's workout
6. After completing all sets for a lift, tap its **Next Cell** button
7. Tap **Advance All** if all three lifts are done for the week

### Finding Your Starting Cell

Find your current working max for each lift and locate the cell where the 1-rep weight is at or just below that number. Start there. If you're new to the program, start conservatively — the matrix has plenty of runway and the early cells build the foundation.

---

## Bug Fix — Missing Cell

The original printed Power Matrix document skips directly from cell **680–685** to **700–705**, omitting **690–695**. This breaks the 10 lb progression increment that every other row follows.

The missing cell has been reconstructed by interpolating from the surrounding cells and inserted in its correct position. It is labeled **NEW** in the Full Matrix view.

---

## Implementation

### Stack

- Vanilla HTML, CSS, JavaScript — single file, zero dependencies
- Progress saved to browser `localStorage` (persists across sessions in the same browser)
- Deployed on Netlify via drag-and-drop

### Deployment

Hosted on Netlify. To update, drag the new `power_matrix.html` file into the existing site on the Netlify dashboard. The URL stays the same.

### iPhone Home Screen

1. Open the Netlify URL in Safari
2. Tap the Share button
3. Tap **Add to Home Screen**
4. Name it Power Matrix

Opens full screen as a web app with no browser chrome.

---

## Integration with Strong App

The Power Matrix app does not connect directly to Strong. Use the **This Week** tab to see the exact sets and weights for each lift, then enter them manually into Strong before your session. The **Copy** button on each lift card copies the full set list as plain text.

---

## Files

| File | Description |
|------|-------------|
| `power_matrix.html` | The complete app — open in any browser |
| `README.md` | This file |

---

## Origin

Based on a physical Power Matrix training document. Digitized, corrected, and built into a mobile-friendly web app for use across a Push/Pull/Legs hypertrophy split with Bench on Push days, Deadlift on Pull days, and Squat on Leg days.
