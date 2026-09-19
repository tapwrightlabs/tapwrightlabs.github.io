# tapwrightlabs.github.io

The website of **Tapwright Labs**, a small independent studio that makes games that are easy to pick up and hard to put down.

Live at <https://tapwrightlabs.github.io/> (GitHub Pages, served from the root of the default branch).

## What's here

| Path | What it is |
|---|---|
| `index.html` | The studio: what we make and our games |
| `smashadillo.html` | Smashadillo: the pitch, a gameplay video, how it plays, screenshots. Coming soon |
| `privacy.html` | Privacy policy for this site and our web games |
| `404.html` | Shown by GitHub Pages for any missing page |
| `style.css` | The only stylesheet. One dark theme taken from the studio logo (`color-scheme: dark`), so the site looks the same whatever the system setting |
| `favicon.svg`, `favicon-32.png`, `apple-touch-icon.png` | Icons. The favicon is a simple flask drawn in the brand colours (the full badge is unreadable at 32 px). The 180 px touch icon is the full logo badge on navy |
| `img/` | The studio logo (`logo-256/512/768.webp` for the pages, `logo-256/512.png` for press use), screenshots (WebP, 480 and 960 px wide) and the link-preview images (`og-*.png/jpg`, 1200x630) |
| `media/` | The gameplay video (`smashadillo-trailer.mp4`) and its poster frame |

## Rules for this site

- Plain static HTML and CSS. No build step, no JavaScript.
- No analytics, no cookies, no ads, no third-party scripts, no web fonts, no CDNs. Every file is served from this repo.
- No personal data. The only contact is tapwrightlabs@gmail.com.
- No playable builds of our games here. Videos and screenshots only.
- The video uses `preload="none"` with a poster, so it only downloads when someone presses play.
- Animations play once and stop (the logo fading in, three bubbles, the toppling 4 on the 404 page). `prefers-reduced-motion` turns them off.
- Links use root paths (`/style.css`) so `404.html` works at any depth.
- If anything that collects data is ever added, `privacy.html` is updated first.

## Preview locally

```sh
python3 -m http.server 8000 --bind 127.0.0.1
```

Then open <http://127.0.0.1:8000/>.

## Look

The theme comes from the studio logo: a navy badge with an electric-blue to cyan glowing rim, a lab flask with a game controller in it, and "LABS" in cyan capitals.

| Token | Colour | Used for |
|---|---|---|
| `--bg` / `--bg-deep` | `#060b18` / `#03060e` | Page and footer background |
| `--panel` / `--panel-2` | `#0c1630` / `#111f40` | Cards and panels (vertical gradient), `--edge` `#1d2d56` for their borders |
| `--text` / `--text-soft` | `#eef4ff` / `#a9b8d3` | Body text and secondary text |
| `--blue` / `--cyan` | `#1f8fff` / `#22d3ee` | Accent gradient, links, glows, the section-title dash, the footer line |
| `--on-accent` | `#04101f` | Text on the gradient button |

Every text colour passes WCAG AA on every background it sits on (lowest: button text on the blue end of the gradient, 5.9:1). No web fonts: headings use Avenir Next where available, then Montserrat, Segoe UI or the system font.

## Page weight (first load, uncompressed transfer)

| Page | Phone (390 px, 3x screen) | Desktop (1280 px, 1x) | Desktop (1280 px, 2x) |
|---|---|---|---|
| Home | about 83 KB | about 65 KB | about 83 KB |
| Smashadillo | about 93 KB | about 92 KB | about 143 KB |
| Privacy | about 18 KB | about 18 KB | about 18 KB |
| 404 | about 15 KB | about 15 KB | about 15 KB |

Measured in headless Chrome with the cache off. The logo is the biggest part of the home page (29 KB at 512 px, 47 KB at 768 px, picked by screen density). GitHub Pages compresses the HTML and CSS, so the real transfer is a little smaller.

The gameplay video (about 8.9 MB, 22.7 s, 1280x720 H.264 + AAC with the game's sound) is not included: it loads only on play. Its index (`moov`) sits at the front of the file so playback starts before the whole file arrives.

## Rights

Copyright 2026 Tapwright Labs. All rights reserved. The code and images in this repo are not licensed for reuse.
