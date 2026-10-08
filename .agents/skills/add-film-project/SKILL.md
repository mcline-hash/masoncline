---
name: add-film-project
description: >-
  Use this skill when Mason wants to add a new film, music video, commercial, or video project to the portfolio, or update an existing project's credits, video link, poster, festival laurels, or synopsis.
---

# Add Film / Video Project Skill

Follow this runbook whenever adding a new film, music video, commercial, or video project to Mason Cline's portfolio.

## 1. Information Checklist
Before adding, gather or confirm the following details from Mason:
- **Title:** e.g., `ARTIST — SONG TITLE` or `FILM TITLE`
- **Category:** One or more of `direction`, `cinematography`, `editing` (used in `data-category`)
- **Project Type / Tag:** e.g., `Music Video`, `Short Film`, `Commercial`, `Documentary`
- **Video Link:** YouTube URL (preferred for fast embedding) or Instagram video link
- **Thumbnail / Poster:**
  - If YouTube, can leave blank to automatically fetch the maximum resolution thumbnail (`https://img.youtube.com/vi/<ID>/maxresdefault.jpg`)
  - Or local / hosted image URL (`data-poster="path/to/poster.jpeg"`)
- **Credits:** Delimited by `||` in the format `Role ~ Collaborator` (e.g. `Director ~ Mason Cline||DP ~ Dario Butera||Gaffer ~ Daniel Fusco`)
- **Synopsis (Optional):** 1-2 sentence description or logline
- **Festivals / Laurels (Optional):** Comma-separated laurel image paths (`laurel1.png, laurel2.png`)

---

## 2. Card Markup Template
In `index.html`, locate `<div class="portfolio-grid">` inside `<main id="work-section">`.
Add the new project card (typically at the top of the grid or in chronological order as requested):

```html
<!-- [NUMBER]. [TITLE] -->
<div class="project-card" data-category="direction editing cinematography" 
     data-title="PROJECT TITLE"
     data-category-name="Music Video"
     data-poster="path/to/poster.jpg"
     data-video="https://youtu.be/VIDEO_ID"
     data-synopsis="Optional logline or synopsis."
     data-festivals="festival1.png,festival2.png"
     data-credits="Director ~ Mason Cline||Producer ~ Declan McKenna||DP ~ Dario Butera||1st AC ~ Jodi Gapan||Gaffer ~ Daniel Fusco">
    <div class="thumbnail-box">
        <img src="path/to/poster.jpg" alt="PROJECT TITLE">
    </div>
    <div class="project-meta">
        <div class="project-title">PROJECT TITLE</div>
        <div class="project-credits-preview">Director | Edit | Cinematography</div>
    </div>
</div>
```

---

## 3. Post-Addition Verification
1. Verify video URL parses cleanly in `parseVideoUrl()`.
2. Verify credit roles separate cleanly on the tilde (`~`) or colon (`:`).
3. Test filter behavior (`Direction`, `Cinematography`, `Editing`) to confirm the project card appears and fades in under each matching category.
4. Update `AGENTS.md` if any new collaborators or roles were introduced.
