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

Sets 1–2 build muscle endurance. Set 3 builds strength. Sets 4–6 are max effort singles at the cell's peak weight. Set 7 is a backoff flush at the same weight as Set 2.

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

### Tabs

**📋 This Week**
Shows all three lifts side by side with weights pre-filled for your current cell. Each card is formatted for direct entry into Strong or any training log. Includes a Copy button per lift and a weekly notes field to log how each session felt.

**🔢 Full Matrix**
All 64 cells displayed in a 7-column grid with color-coded set types (endurance, strength, power, backoff). B / D / S badges mark each lift's current position. Click a cell to set your position; click it again to mark it complete and advance.

**🎯 Find My Start**
Enter your best recent single for each lift. The calculator finds your conservative starting cell at 80% of that number and shows a full preview of Week 1 sets. One tap sets all three lifts and drops you into This Week.

**📈 History**
Shows your full progression log per lift — cells completed, percent through program, 1-rep weight gained since starting, and a reverse-chronological list of every completed cell. Also displays all saved weekly notes in one place. Export button downloads your complete progress as a plain text file.

### How to Use

1. Open the app and go to **🎯 Find My Start**
2. Enter your best single for each lift
3. Tap **Set These As My Starting Cells**
4. You land on **This Week** — your Week 1 sets are ready
5. Log the session in Strong using the pre-filled weights
6. Add a note in the weekly notes field
7. When the week is done, tap **Next Cell** per lift or **Advance All**
8. Check **📈 History** any time to see progress and export a summary

### Finding Your Starting Cell Manually

Find your current working max for each lift and locate the cell where the 1-rep weight sits at or just below 80% of that number. If you're new to the program, start conservatively — the matrix has 64 cells and plenty of runway.

---

## Bug Fix — Missing Cell

The original printed Power Matrix document skips directly from cell **680–685** to **700–705**, omitting **690–695**. This breaks the consistent 10 lb progression increment that every other row follows.

The missing cell has been reconstructed by interpolating from the surrounding cells and inserted in its correct position. It is labeled **NEW** in the Full Matrix view.

---

## Integration with Strong App

The Power Matrix app does not connect directly to Strong. Use the **This Week** tab to see the exact sets and weights for each lift, then enter them manually into Strong before each session. The **Copy** button on each lift card copies the full set list as plain text for pasting into notes.

---

## Implementation

### Stack

- Vanilla HTML, CSS, JavaScript — single file, zero dependencies
- All state saved to browser `localStorage` (persists across sessions in the same browser)
- Deployed on Netlify via drag-and-drop

### Deployment

Hosted on Netlify. To update, drag the new `power_matrix.html` file into the existing site dashboard. The URL stays the same.

### iPhone Home Screen

1. Open the Netlify URL in Safari
2. Tap the Share button
3. Tap **Add to Home Screen**
4. Name it Power Matrix

Opens full screen as a web app with no browser chrome.

---

## PPL Split Integration

Designed for a Push / Pull / Legs training split:

| Lift | Day |
|------|-----|
| Bench Press | Push Day |
| Deadlift | Pull Day |
| Back Squat | Leg Day |

The original program recommends training each lift twice per week. On a standard PPL running each lift once per week, progress is slower but still consistent. Never program Squat and Deadlift on the same day.

---

## Files

| File | Description |
|------|-------------|
| `power_matrix.html` | The complete app — open in any browser |
| `README.md` | This file |

---

## Origin

Based on a physical Power Matrix training document. Digitized, corrected (missing 690–695 cell added), and built into a mobile-first web app. Designed for iPhone home screen use alongside the Strong app for session logging.
