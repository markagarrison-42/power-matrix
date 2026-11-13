# Power Matrix

Live at powermatrix.mg42apps.com. Part of the MG42 Apps suite. Owner: Mark (call him "bro").
Wave-loading strength progression tracker for Bench, Deadlift and Squat.

## Stack
- Pure static HTML + JS, no backend, no build step
- Data: Supabase project `rwtgleklptqixhigbrzy`, tables prefixed `pm_`
- Hosted on Netlify

## Workflow (GitHub-first)
- GitHub `markagarrison-42/power-matrix` is the source of truth.
- Push to main triggers GitHub Actions. A `check` job syntax-checks the JS inside `index.html` first; deploy only runs if it passes. Deploy goes to Netlify. Secrets: `NETLIFY_AUTH_TOKEN`, `NETLIFY_SITE_ID`.
- `index.html` must stay at the repo root. Netlify serves the root; moving or renaming the entry file breaks the live site.
- Every push costs a Netlify deploy. Batch changes into one commit per feature set, one descriptive sentence.
- Mark tests on his phone before calling anything done. Never say a change is live until he confirms.

## Hard rules
- The app is plain JS inside `index.html` (no Babel). `power_matrix.html` is an old copy: don't edit it.
- Validate JS before committing and grep to confirm the edit landed.
- Dates: format with the `en-CA` locale to avoid UTC shifts.
- Supabase anon key must be the long `eyJhbGci...` JWT, never `sb_publishable_`.
- Supabase RLS: four explicit policies (SELECT, INSERT, UPDATE, DELETE), not `FOR ALL`. Upserts with `onConflict` need a real UNIQUE constraint.
- SQL schema files must be idempotent.
- Fetch helpers must return distinct values for empty vs error.
- Chart.js cannot draw on a `display:none` canvas. Init charts when their tab is visible.
- Before any direct Supabase data edit, tell Mark to close the app on all devices.

## Design
Dark `#0f0f0f` background, surface `#1a1a1a`, gold `#c8a96e` accent, system font.

## Debugging
- One diagnostic step before any fix.
- If save/edit/delete "doesn't work" but the code reads fine, add a temporary `alert()` probe. Safari's remote console often shows nothing.
- iOS caches the home screen icon at install. Changing `manifest.json` alone does nothing.
