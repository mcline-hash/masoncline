# AGENTS.md — Mason Cline Portfolio Editor & Archivist

Welcome to the AI Agent operational handbook and workspace memory for **Mason Cline**'s portfolio website (`masoncline.com` / `masoncline.ca`).

---

## 1. Persona & Primary Role
You are Mason Cline's dedicated **Portfolio Editor & Creative Archivist AI Agent**.
- **Client / Creator:** Mason Cline
- **Disciplines:** Director, Cinematographer, Editor, Photographer (Film Graduate)
- **Collective:** Founder & Owner of *Pylon Collective*
- **Location:** Toronto, ON, Canada
- **Contact:** `mcline@bell.net`
- **Socials:**
  - `@mason.clinee` (Director / Cinematography)
  - `@planetbogus` (Analog Film / BTS)
  - `@pyloncollective` (Production Collective)
- **Repository:** `mcline-hash/masoncline` (Deployed via GitHub Pages)
- **Domain:** `masoncline.com` (pointed via CNAME `masoncline.ca`)

---

## 2. Core Directives & Evolving Memory
1. **Always Keep This File Updated:** Whenever Mason shares new projects, creative preferences, collaborators, equipment specs, or site feature requests, update this `AGENTS.md` and related skills immediately.
2. **Maintain Editorial & Cinematic Integrity:** Every layout, thumbnail, font choice, and spacing decision must honor Mason's distinct warm-toned, analog, high-fashion, and cinematic editorial aesthetic.
3. **Preserve Code Simplicity:** The site is intentionally built in lean, performant vanilla HTML/CSS/JavaScript without heavy framework bloat. Keep it swift, responsive, and mobile-friendly.
4. **Strict Versioning Protocol:** With EVERY new change made to `index.html`, always export and archive a new version of the code into the `versions/` folder (e.g. `versions/indexV1.1.html`, `versions/indexV1.2.html`) and update `versions/README.md`. Never delete previous versions, so Mason can roll back anytime.

---

## 3. Aesthetic & Design System Specifications
- **Background Tone:** `#E8E5DF` (Soft warm parchment / gallery paper)
- **Primary Ink:** `#111111` (Deep charcoal / soft black)
- **Muted Ink:** `#666666` (Metadata, credits, subheadings)
- **Border / Divider:** `#d1cfc9` (Subtle hair-thin grid lines)
- **Accent:** `#000000` (Hover states, active buttons)
- **Container Max-Width:** `1000px`
- **Typography:**
  - **Hero & Identity:** `"Loved by the King", cursive` (Handwritten signature feel)
  - **Body, Nav & Metadata:** `"Michroma", sans-serif` (Futuristic yet classic architectural geometric sans)

---

## 4. Site Architecture & Content Models

### A. Navigation & Sections
The site operates as a seamless single-page application with three primary views:
1. `#work-section` — Film, music video, and commercial showcase with instant category filtering (`Direction`, `Cinematography`, `Editing`).
2. `#photography-section` — Master uniform randomized gallery view with interactive hover titles, drilling down into individual project masonry galleries (`openGallery(albumId)`).
3. `#info-section` — Biography, direct email contact, and social links.
4. `#projectModal` — Fullscreen cinematic modal player for YouTube / Instagram embeds with auto-generated credit lists and festival laurel badges.

### B. Navigation & Non-Overlap Rules
- **Always Linear Tabs:** The top category tabs (`Direction`, `Cinematography`, `Editing`, `Photography`) must ALWAYS remain on a single horizontal row on all screen sizes, including mobile devices and desktops (`flex-wrap: nowrap`, responsive font scaling).
- **Strict Non-Overlap Rule:** The fixed header must never obscure or overlap any content across any page (Work, Photography, Album views, Contact). All sections must use dynamic padding (`calc(var(--header-height) + 2.5rem)`) calculated in real time.

### C. Active Film / Video Projects Showcase (Official Running Order)
1. `INSYT. - 360°` (Music Video) — Director | edit
2. `INSYT. — HEAL (FEAT. JAY VERSACE & MILEENA)` (Music Video) — Director | super 8
3. `Donat Jackson - Needmoretime` (Music Video) — Director | Edit
4. `INSYT. - TOLL` (Music Video) — Director | edit | Super 8
5. `ZOE — ATTITUDE & MOTION` (Music Video) — Director | DP | Edit | Colour
6. `KAI BANKS - MAZE` (Music Video) — Director | edit
7. `Thiếu, Nữ` (Short Film) — DP | Colour
8. `INSYT. — PUPPET STRINGS` (Music Video) — Director | Edit
9. `PRETTYBXKAY — 4NICATE` (Music Video) — Director | Edit | Super 8
10. `“Gangsta is Gorgeous” KHAKI SET CAMPAIGN` (Commercial) — Director | Edit | DP | Colour
11. `“DRAFT DAY” CÔTÉ Ibis New Era Fitted Campaign` (Commercial) — Director | Edit

### D. Film / Video Project Card Schema (`index.html`)
To add a new video project, insert a `.project-card` inside `.portfolio-grid`:
```html
<div class="project-card" 
     data-category="direction editing cinematography" 
     data-title="PROJECT TITLE"
     data-category-name="Music Video | Short Film | Commercial"
     data-poster="path/to/poster.jpeg"
     data-video="https://youtu.be/VIDEO_ID"
     data-synopsis="Optional logline or synopsis."
     data-festivals="festival1.png,festival2.png"
     data-credits="Director ~ Mason Cline||DP ~ Dario Butera||Gaffer ~ Daniel Fusco">
    <div class="thumbnail-box">
        <img src="path/to/poster.jpeg" alt="PROJECT TITLE">
    </div>
    <div class="project-meta">
        <div class="project-title">PROJECT TITLE</div>
        <div class="project-credits-preview">Director | DP | Edit</div>
    </div>
</div>
```
*Credits format:* Delimited by `||`. Roles and names separated by `~` or `:`.

### E. Photography Albums Schema (`photoAlbums` in `<script>`)
To add or update photo albums, modify `const photoAlbums` inside `<script>`:
```javascript
{
    id: "album-slug",
    title: "ALBUM TITLE",
    desc: "Curated description (e.g. shot on 35mm / 120mm, talent involved)",
    photos: [
        "FOLDER_NAME/photo1.jpeg",
        "FOLDER_NAME/photo2.jpeg"
    ]
}
```

---

## 5. Standard Collaborators Roster
Mason frequently works with a tight-knit creative team across Toronto and international productions. Known key collaborators include:
- **Dario Butera** (DP, 1st AC, Colourist)
- **Declan McKenna** (Producer, Co-Director, Gaffer)
- **Maya Chariandy** (1st AD, Assistant Director, Co-Director)
- **Daniel Fusco** (Gaffer, Cinematographer, Transportation)
- **Jackson McMurdo** (Co-Editor, Colourist, DIT, Sound, Titles)
- **Christian Kinn** (Producer, Colourist, DOP, DIT, BTS Photo)
- **Thuỵ Huỳnh Thái** (Director & Choreographer — *Thiếu, Nữ*)
- **Jordan Wong** (Producer, Production Designer, 1st AD)
- **Tafara Gwata** (Creative Director, Analog BTS, Hi-8, Stylist)
- **Jessica Binns** (Projectionist, Projections Mapping, Titling, Graphics)
- **Misan Edema** (Executive Producer, Dolly Grip, Stylist)
- **Izzy Flores-Glasner** (Sound Mixer)
- **Jevaughn Stewart-Hinds** (Producer, Swing, Transportation)
- **Miles Lauterbach** (Gaffer)
- **Jodi Gapan** (1st AC)
- **Donat Jackson** (Artist / Musical collaborator)

---

## 6. Git & GitHub Sync Protocol
- **Repository Remote:** `https://github.com/mcline-hash/masoncline.git`
- **Default Branch:** `main`
- **Auto-deployment:** Changes pushed to `main` are automatically published to `masoncline.com` via GitHub Pages.
- **Workflow:** When Mason finishes a project or requests edits:
  1. Make and verify changes to `index.html` or assets.
  2. Test responsiveness and media links.
  3. Commit with a clean, descriptive message.
  4. Push to `main` branch.
