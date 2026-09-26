# NISHAN_OS // CREATOR PROTOCOL — SETUP GUIDE

## 1. HOW TO INSTALL

1. Go to your profile repository: `github.com/nishan9-99/nishan9-99`
   (a repo named exactly like your username is your special profile repo).
2. Upload the files keeping this structure:

```
nishan9-99/
├── README.md
├── SETUP.md          (this file — optional to keep)
└── assets/
    ├── hero.svg
    ├── boot.svg
    ├── player-hud.svg
    ├── radar.svg
    ├── skill-tree.svg
    ├── loadout.svg
    ├── aura.svg
    ├── achievements.svg
    ├── inventory.svg
    ├── terminal.svg
    ├── creator-mode.svg
    ├── 3d-module.svg
    ├── game-dev.svg
    ├── roadmap.svg
    ├── system-log.svg
    ├── comms.svg
    └── footer.svg
```

3. Commit. Open `github.com/nishan9-99` — the profile boots itself.

Easiest path on the web UI: open the repo → `Add file → Upload files` →
drag the whole folder structure in (GitHub keeps folders when you drag a folder).

## 2. HOW TO CUSTOMIZE

Everything is plain text in plain files. No build step.

| What | Where |
|---|---|
| Name / handle / class | `assets/hero.svg`, `assets/player-hud.svg`, `assets/footer.svg` |
| College, education, location | `assets/player-hud.svg`, `assets/terminal.svg` |
| Skill bars | `README.md` → `03 // CHARACTER ATTRIBUTES` (edit the `█`/`░` blocks) |
| 3D module percentages | `assets/3d-module.svg` (bar `width` + `%` text) |
| Mission objectives | `README.md` → `06 // CURRENT MISSION` |
| Level / XP | `README.md` → `15 // PLAYER PROGRESSION` |
| Socials / email | `README.md` → `22 // COMMS TERMINAL` + `assets/comms.svg` |
| Colors | Search-replace hex codes in `assets/*.svg` (`#00E5FF` cyan, `#B388FF` purple, `#FF9E64` orange, `#05070A` background) |

SVG text is inside `<text ...> ... </text>` tags. Change the words, keep the tags.

## 3. HOW TO ADD PROJECTS LATER

1. Open `README.md`, find `21 // QUEST DATABASE`.
2. Inside the HTML comment there is a ready project slot
   (name, description, tech stack, status, GitHub, live demo, screenshot,
   difficulty, mission reward).
3. Copy it out of the comment, fill it in, delete the "LOCKED" box when
   the first project is real.

## 4. HOW TO UPDATE ACHIEVEMENTS

1. Open `assets/achievements.svg`.
2. Find the card you earned, e.g. `FIRST GAME`.
3. Change `[ LOCKED ]` → `[ UNLOCKED ]`, its fill `#FF5470` → `#00E5FF`,
   and the card border `stroke="#3A4454"` → `stroke="#00E5FF"`.
4. Update the header count `0 OF 7 UNLOCKED`.

## 5. HOW TO UPDATE SKILLS

- Quick bars: edit the `█`/`░` ratio in `README.md` section 03.
- Skill tree node status: in `assets/skill-tree.svg` find the node, change
  its status text (e.g. `LEARNING` → `ACTIVE`) and its stroke color
  (orange `#FF9E64` = learning, cyan `#00E5FF` = active).
- 3D module: adjust bar widths and `%` labels in `assets/3d-module.svg`.

## 6. TROUBLESHOOTING

- **Images show as broken:** the `assets/` folder name or path changed.
  The README references `assets/hero.svg` etc. — keep the folder at the
  repo root, case-sensitive.
- **An animation looks static:** GitHub serves SVGs through an image proxy
  (camo). SMIL animation plays in all modern browsers, but some proxy
  caches can freeze frame one. Everything is designed to look complete
  as a static image too — hard-refresh to re-trigger.
- **Streak widget shows an error card:** streak-stats.demolab.com had a
  bad moment. It recovers on its own; the rest of the profile is
  independent of it. Fallback line: `DATA STREAM: AWAITING LIVE SIGNAL`.
- **Want more GitHub stat cards:** there is a commented-out block in
  section 16 of the README for github-readme-stats. It was erroring at
  build time, so it's off by default. Test the URL in your browser first.

## 7. GITHUB COMPATIBILITY NOTES

- No JavaScript, no CSS files, no iframes — GitHub strips all of those.
- All motion is SMIL (`<animate>` / `<animateTransform>`) inside SVGs,
  which GitHub does render.
- Markdown + HTML + SVG + details/summary only. All section accordions
  (Classified Files) are native GitHub features.
- Every external image is served by an established README service and was
  verified live at build time (2026-09-27): streak-stats.demolab.com,
  komarev.com (profile views), img.shields.io (badges).
- Static fallbacks: every SVG reads perfectly with animation frozen.
  Alt text on every image describes the content for screen readers.
- Mobile: all images are 900px wide SVGs that scale down cleanly; no wide
  fixed tables except the boss database (5 short columns).

