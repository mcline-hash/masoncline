# Portfolio Code Versions & Changelog Archive

This folder stores timestamped and versioned snapshots of `index.html` so that any prior version can be restored instantly if needed.

---

## Version History

### `indexV1.1.html` (Current Production)
* **Date:** 2026-10-08
* **Key Changes:**
  1. **Strictly Linear Navigation Tabs:** Configured `.directory-nav` on mobile and desktop with `flex-wrap: nowrap`, responsive font scaling, and smooth horizontal fitting so `Direction`, `Cinematography`, `Editing`, and `Photography` never wrap across multiple rows.
  2. **Added New Project:** Added *Donat Jackson — Needmoretime* (`https://www.youtube.com/watch?v=m3GzM8sJ_V8`) with `Director | Edit` credit preview, tagged for Direction and Editing.
  3. **Reordered Homepage Projects (11 Projects):**
     1. `INSYT. - 360°`
     2. `INSYT. — HEAL (FEAT. JAY VERSACE & MILEENA)`
     3. `Donat Jackson - Needmoretime`
     4. `INSYT. - TOLL`
     5. `ZOE — ATTITUDE & MOTION`
     6. `KAI BANKS - MAZE`
     7. `Thiếu, Nữ`
     8. `INSYT. — PUPPET STRINGS`
     9. `PRETTYBXKAY — 4NICATE`
     10. `“Gangsta is Gorgeous” KHAKI SET CAMPAIGN`
     11. `“DRAFT DAY” CÔTÉ Ibis New Era Fitted Campaign`
  4. **Dynamic Header Non-Overlap Engine:** Added real-time height calculation (`updateHeaderHeight()`) in JavaScript and dynamic CSS padding (`calc(var(--header-height) + 2.5rem)` / `+ 2rem` on mobile) across all sections (`#work-section`, `#photography-section`, `#info-section`, `#gallery-view`) to eliminate header overlap.

---

### `indexV1.0.html` (Original Baseline)
* **Date:** Prior baseline
* **Description:** Initial single-page portfolio code as originally deployed on GitHub Pages.
