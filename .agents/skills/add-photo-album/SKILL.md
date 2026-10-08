---
name: add-photo-album
description: >-
  Use this skill when Mason wants to add a new photography album, add photos to an existing album, or update analog photo galleries (35mm, 120mm, BTS).
---

# Add Photo Album Skill

Follow this runbook whenever adding a new photography album or adding photographs to an existing series in Mason Cline's portfolio.

## 1. Information Checklist
Before adding, gather:
- **Album Slug / ID:** e.g., `reach`, `pathfinder`, `thieu-nu` (kebab-case)
- **Album Title:** e.g., `REACH campaign`, `PATHFINDER`
- **Album Description:** e.g., `Editorial Fashion Campaign for REACH COLLECTIVE, featuring Tandie Tyrell & Seunn, shot on 35mm`
- **Image Files:**
  - Placed in a named directory at the project root (e.g., `13 NEW ALBUM/`)
  - Stored as optimized `.jpeg` or `.png`
  - High resolution for editorial viewing while respecting loading performance

---

## 2. Code Implementation (`index.html`)
In `index.html`, locate `const photoAlbums = [` in the `<script>` section.

### Adding a New Album
Append or insert a new album object:
```javascript
{
    id: "new-album-slug",
    title: "NEW ALBUM TITLE",
    desc: "Description of the shoot, featured talent, camera formats (e.g. shot on 35mm / 120mm).",
    photos: [
        "13 NEW ALBUM/photo1.jpeg",
        "13 NEW ALBUM/photo2.jpeg",
        "13 NEW ALBUM/photo3.jpeg"
    ]
}
```

### Adding Photos to an Existing Album
Locate the existing entry matching the `id` (e.g. `thieu-nu` or `zoe`) and append new photo paths to the `photos` array.

---

## 3. How the Dynamic Photography System Works
- **Master Randomized Grid (`renderMasterGallery()`):**
  Collects all photos from all albums, shuffles them with Fisher-Yates shuffle, and renders them in a uniform grid with hover labels revealing the album title. Clicking any image opens that specific album.
- **Dedicated Masonry Grid (`openGallery(albumId)`):**
  Hides the master view and displays the chosen album's photos in a vertical masonry flow with a back button and curated description.

---

## 4. Post-Addition Verification
1. Ensure image relative paths match folder names exactly (including spaces).
2. Check that images load smoothly with `loading="lazy"`.
3. Verify that the master gallery shuffle includes images from the new album.
4. Verify that clicking an image opens the album with correct title and logline.
