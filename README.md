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
| Windows 10/11 (x64) | `downloads/YouThere.exe` | 16.9 MB | `419ccdab55323edeec07a2450b261c6cf7e772aa9cbfa81e14c44b307c19d483` |
| macOS (Apple Silicon) | `downloads/YouThere-mac.zip` | 14.1 MB | `49b02812c818580753ba8671f302251b4c6cbd921391838741ff12283af761a3` |
| Linux | <https://fromsmash.com/lenex2> | — | hosted off-repo, link expires |

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
