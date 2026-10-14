# nathansetaro.com

Plain HTML, CSS and JavaScript. No build step, no dependencies, no server code.
Open `index.html` directly, or upload the whole `site/` folder to any static host
(GitHub Pages, Netlify, Cloudflare Pages, Vercel, cPanel/FTP, nginx).

Every path is relative, so the folder works at a domain root or in a subfolder.
Keep filenames lowercase; some hosts are case-sensitive.

```
index.html          Landing page
resume.html         Resume page (image preview + PDF download)
.htaccess           Caching and MIME types for Apache hosts (ignored elsewhere)
.nojekyll           Tells GitHub Pages to serve files as-is
assets/
  fonts/            Newsreader and Instrument Sans, self-hosted (no Google Fonts call)
  lotus-dots.js     Dot data for the hero lotus
  portrait.jpg      About photo
  about-1..3.webp   Small photos under the portrait
  proj-*.webp       Project images
  resume.pdf/.png   Resume download and on-page preview
  nds-mark.png, anaeio-wordmark.png, anaeio-lotus.png   Logos
```

## Adding photos

Drop a file with a matching name into `assets/` and it appears; no code change.
`.webp`, `.jpg`, `.jpeg` and `.png` all work. A missing file shows nothing (no
placeholder box).

| File name | Where it shows |
|---|---|
| `about-1`, `about-2`, `about-3` | Under the portrait in About (shown 2:3, portrait shape) |
| `proj-ai` | Self-Hosted Personal AI Assistant (open the project row) |
| `proj-pacifier` | Glucose Detection Pacifier |
| `proj-cloud` | Self-Hosted Cloud |
| `proj-nas` | Network-Attached Storage |

Photos at least 1200px wide look sharp; WebP at quality ~80 keeps them small.

## Updating the resume

Replace both `assets/resume.pdf` (the download) and `assets/resume.png` (the
preview). If the PNG changes size, update its `width`/`height` in `resume.html`.

## Notes

- Light/dark choice is kept in `sessionStorage` under `nds-theme`: each new visit
  opens light, and the choice carries between both pages for that session.
- Motion (the lotus, tickers, reveals) stops for visitors who set
  "reduce motion" in their system settings.
