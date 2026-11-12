# Pastedown website (GitHub Pages, custom domain)

The static marketing, support and privacy pages for Pastedown, a Mac app that turns Markdown into rich
text on the clipboard. Plain HTML and one stylesheet (shared with the other apps at victorshammas.com),
with no build step, external fonts, scripts or trackers. The app's source lives in a private repo
(`pastedown-app`).

| File | Published URL |
|---|---|
| `index.html` | https://victorshammas.com/pastedown/ |
| `support.html` | https://victorshammas.com/pastedown/support.html (the app's Help menu opens it) |
| `privacy.html` | https://victorshammas.com/pastedown/privacy.html |
| `style.css`, `icon.png`, `favicon.png`, `apple-touch-icon.png` | assets (the icons come from `Design/make-icon.swift` in the app repo) |
| `.nojekyll` | tells Pages to serve files as-is |

Keep these paths stable: the app links to `support.html` and to `#download` on the home page.

## How the URL works

The user site (`victor-shammas.github.io`) has the custom domain `victorshammas.com`, so every public
project repo with Pages turned on is served at `https://victorshammas.com/<repo-name>/`. This repo must be
named `pastedown` and needs no `CNAME` file. Pages: Settings › Pages › Deploy from a branch › `main`, `/ (root)`.

## The free download

The download button links to `https://github.com/victor-shammas/pastedown/releases/latest/download/Pastedown.dmg`:
the latest release of this repo. Releases hold only the notarized DMG, never source code. To publish a new
version, in the app repo: `Scripts/release.sh <version>`, then
`gh release create v<version> build/release/Pastedown.dmg -R victor-shammas/pastedown --title "Pastedown <version>"`,
and update the version in the hero's fine print.
