# Saga theme

The Saga Obsidian theme, light and dark, in the Saga app's modern parchment style. Companion to the Saga for Obsidian plugin (`../saga-obsidian`), whose renderer colours it sets. Design, files and palettes are in `README.md`.

## Scripts
- `npm run build` writes `theme.css` (fonts embedded) from `src/theme.css`; commit the result

## Conventions
- Edit `src/theme.css`, never `theme.css`.
- Bump `version` in `manifest.json` and `package.json` together and add it to `versions.json`; releases are tags named the version (`README.md`, Release).
