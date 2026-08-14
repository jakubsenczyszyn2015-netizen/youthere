# youthere

Download site for **YouThere**, a lightweight Windows desktop app.

## Contents

| Path | What it is |
| --- | --- |
| `index.html` | The whole site — one page, styles inline, no build step and no dependencies |
| `assets/` | App icon rendered at several sizes, plus `favicon.ico` |
| `downloads/` | The Windows `.exe` and the macOS `.app` zip the download buttons point at |
| `CHANGELOG.md` | Release notes, mirrored by the `#changelog` section of the page |
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

## Current downloads

| Platform | File | Size | SHA-256 |
| --- | --- | --- | --- |
| Windows 10/11 (x64) | `downloads/YouThere.exe` | 16.9 MB | `2f5c6c412b1ab70a13ec70d4bd601b7c479b445d503eccbc52a34e130406c6fe` |
| macOS (Apple Silicon) | `downloads/YouThere-mac.zip` | 14.1 MB | `1eb62628c388627ed80f5422680abc643be871b5f7bfca6faa27605ada559ad6` |
| Linux | <https://fromsmash.com/lenex> | — | hosted off-repo, link expires |

The Linux build is too large for the 100 MB file limit, so it's distributed over a Smash
transfer link. Those expire — when it dies, replace the URL in the Linux card in
`index.html` (and in the `builds` object in the script at the bottom of the page).

## Releasing a new build

1. Drop the new file into `downloads/`.
2. Refresh the size and SHA-256 on that platform's card in `index.html`, and in the
   `builds` object in the script at the bottom of the page:
   ```bash
   sha256sum downloads/YouThere.exe
   ```
3. Add an entry to `CHANGELOG.md` and mirror it in the `#changelog` section of `index.html`.
4. Commit and push.
