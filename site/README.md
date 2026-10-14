# nathansetaro.com — static site

Plain HTML/CSS/JS. No build step, no dependencies, no server code. Open
`index.html` directly or upload the whole folder to any host — Netlify, Vercel,
GitHub Pages, Cloudflare Pages, cPanel/FTP, S3, or a Raspberry Pi running nginx.

Every path in the site is **relative**, so the folder works at a domain root
(`nathansetaro.com/`) or in a subfolder (`user.github.io/portfolio/`) with no
edits. Keep the folder's internal structure intact and keep filenames lowercase —
some hosts are case-sensitive.

```
index.html            Landing page
resume.html           Resume page
lotus-mark-dots.js    Dot data for the hero constellation
assets/               Photos, logos, resume image + PDF
logos/                Brand marks for the tool chips
```

## Filling the empty image spots

Drop a file with the matching name into `assets/` and it appears automatically —
no code change. Any of `.webp`, `.jpg`, `.jpeg`, `.png` works; a spot with no
file stays hidden (a project with no image shows its text full width).

| Name | Where it shows |
|---|---|
| `assets/about-1` … `about-3` | Three squares under the About photo — **already filled** |
| `assets/proj-ai` | Self-Hosted Personal AI Assistant |
| `assets/proj-pacifier` | Glucose Detection Pacifier — **filled** |
| `assets/proj-cloud` | Self-Hosted Cloud |
| `assets/proj-nas` | Network-Attached Storage |

Organization logos work the same way in `logos/` — add a transparent PNG named
after the slot and it replaces the monogram:
`logo-nationalgrid`, `logo-machado`, `logo-mlsc`, `logo-wpi`, `logo-wths`,
`logo-auburn`, `logo-anaeio` (**filled**), `logo-medhigh`, `logo-redcross`, `logo-comptia`.

Transparent marks sit on a themed disc: `logo-anaeio` gets teal in light mode,
`logo-auburn` gets white, and both go near-black in dark mode.

Tool chips without a brand mark accept `logos/<name>.png` too — e.g.
`canva.png`, `onshape.png`, `adobe-express.png`, `microsoft-word.png`.

## Updating the resume

Replace both `assets/resume.pdf` (download button) and `assets/resume.png`
(the on-page preview image).

## Notes

- Light/dark choice lives in `sessionStorage` under `nds-theme`: every fresh
  visit opens in light mode, and the choice carries between both pages for the
  rest of that session.
- Fonts load from Google Fonts, so the type falls back to system sans/serif offline.
