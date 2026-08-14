# youthere

Download site for **YouThere**, a lightweight Windows desktop app.

## Contents

| Path | What it is |
| --- | --- |
| `index.html` | The whole site — one page, styles inline, no build step and no dependencies |
| `assets/` | App icon rendered at several sizes, plus `favicon.ico` |
| `downloads/YouThere.exe` | The Windows build the download buttons point at |
| `site.webmanifest` | Icons and theme colour for browsers / installed shortcuts |
| `.nojekyll` | Stops GitHub Pages from running Jekyll over the files |

## Viewing it locally

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## Publishing with GitHub Pages

Settings → Pages → *Deploy from a branch*, pick this branch and the `/ (root)` folder.
The site is static, so nothing needs to be built.

## Releasing a new build

1. Drop the new `YouThere.exe` into `downloads/`.
2. Update the size and SHA-256 in `index.html` (they appear once, just under the hero buttons):
   ```bash
   sha256sum downloads/YouThere.exe
   ```
3. Commit and push.

Current build: 22 MB, SHA-256 `30806d992898f6596c9e68c85cc3a96355ad2bcd1bf5846a88d4eeee25a49d02`.

> **Note:** the feature blurbs and FAQ describe the app in general terms (portable single
> file, no installer, no account). Edit the `#features` and `#faq` sections in `index.html`
> to say what YouThere actually does.
