# Install notes

Push to the special repo `nishan9-99/nishan9-99` (replacing the old README and assets):

- `README.md` (repo root)
- `assets/hero-hud.svg`, `assets/toolchain-hud.svg`, `assets/card-*.svg` (4 files)

Asset hosting: every local asset is referenced by a repo-relative path (`assets/...`), so they work as soon as they sit in the same repo. The animations are SMIL inside the SVGs (no JavaScript), which GitHub renders.
Live panels load from public services and update on their own: github-readme-stats.vercel.app (stats + languages), streak-stats.demolab.com (streak), github-profile-summary-cards.vercel.app (summary), komarev.com (views counter), img.shields.io (badges). They cache for a few hours, so numbers can lag.
