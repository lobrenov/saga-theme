# Saga theme

An Obsidian theme (name "Saga", light and dark) in the Saga app's modern parchment style. It sets Obsidian's CSS variables from Saga's tokens and adds selector rules only where variables cannot reach.

## Files
- `src/theme.css` hand-written source
- `build.mjs` (`npm run build`) writes `theme.css`: `@font-face` rules with the woff2 files as base64 data URIs, then the source. The built `theme.css` is committed.
- `fonts/` vendored woff2 files and their SIL OFL notices (`LICENSE-*.txt`)
- `manifest.json`
- `versions.json` each theme version's minimum Obsidian version
- `.github/workflows/release.yml` on a pushed tag, creates a draft GitHub release with `manifest.json` and `theme.css` attached

## Release
Bump `version` in `manifest.json` and `package.json`, add it to `versions.json`, build, commit, then push a tag named the version (`git tag 0.1.2 && git push origin 0.1.2`). Publish the draft release the workflow creates.

## Install
With BRAT: Add beta theme, `lobrenov/saga-theme`. Or copy `manifest.json` and `theme.css` into `<vault>/.obsidian/themes/Saga/`.

## Palettes
`theme.css` declares Saga's token names (`--saga-ground`, `--saga-sheet`, `--saga-chrome`, `--saga-ink`, `--saga-rubric`, `--saga-gilt`, ...) under `.theme-light` and `.theme-dark`; every Obsidian variable references them.

| Role | Light | Dark |
| --- | --- | --- |
| sheet (note, `--background-primary`) | `#fbf8f2` | `#231d17` |
| ground (tab bar, status bar, `--background-secondary`) | `#f4efe5` | `#1b1612` |
| chrome (sidebars) | `#ece5d7` | `#15110e` |
| ink / ink-2 / ink-3 | `#2a241d` / `#5f5547` / `#6b5f51` | `#ece3d2` / `#bfb39e` / `#a99d88` |
| rubric (links, accent text) | `#9a3324` | `#e0846f` |
| accent fill (buttons, checked boxes, white text; `--accent-h/s/l`) | `#9a3324` | `#b5503d` |
| gilt (blockquote rule, highlight) | `#b08d4c` | `#c9a55e` |
| rule | `#ddd3c2` | `#3a3126` |

`--color-red` to `--color-pink` and their `-rgb` triplets map to Saga-family hues (rubric red, ochre, Saga green, location teal, faction blue, rumour purple). `--color-base-*` map onto the same surfaces and inks.

The plugin's renderer colours (`--saga-character`, `--saga-location`, `--saga-faction`, `--saga-item`, `--saga-map`, `--saga-document` and `-tint`) are set for both modes with `body.theme-*.theme-*` selectors, which outrank the plugin's own `body.theme-dark` defaults regardless of load order.

## Type
- Headings and the inline title: Fraunces (600), sizes 1.9, 1.5, 1.25, 1.05em; inline title 46px, tracking -0.015em; h6 in small caps
- Reading text: Source Serif 4, line height 1.65
- Interface: IBM Plex Sans; code: IBM Plex Mono
- Property keys and the Properties heading: 11px, 600, uppercase, 0.1em tracking

## Selector rules
Sidebar background (chrome), selected file outline, property labels and divider, tag, modal and prompt shadows, link underline colour, focus outline colour.

## Lists
- Bullets by level: bullet, hollow bullet, square, diamond, repeating (levels 1 to 8)
- Alternative checkboxes: the [Alternative Checkboxes Reference Set](https://github.com/damiankorcz/Alternative-Checkboxes-Reference-Set)'s 20 characters with its Lucide icons, in Saga hues; `[-]` lines are struck through. A snippet setting `--theme-alternative-checkboxes: disable` on `body` turns them off.

## Callouts
Saga's `secret` (red), `statblock` (ochre) and `read-aloud` (blue) callout types, with the Saga app's icons.

## Contrast
Body ink, muted and faint text, rubric links and the accent fill's white text meet WCAG AA (4.5:1) on the sheet, ground, chrome and chip surfaces in both modes. Gilt is decorative only.
