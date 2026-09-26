# Evrim Rugs

A luxury antique-kilim archive website with a 300-frame scroll sequence and a logo preloader.

## Preview locally

Open a terminal in this folder and run:

```powershell
& 'C:\Users\CrazyHarsh\.cache\codex-runtimes\codex-primary-runtime\dependencies\python\python.exe' -m http.server 4174 --bind 127.0.0.1
```

Then visit `http://localhost:4174`.

Alternatively, `npm start` (or `npm run dev`) launches the included `server.js` (Express) on its configured port.

## Deploy to Vercel

This is a static site—no build command or framework preset is required.

1. Push the contents of this folder to the root of a GitHub repository.
2. In Vercel, choose **Add New → Project** and import that repository.
3. Select the **Other** framework preset; leave the build command blank and set the output directory to `.`.
4. Deploy. Vercel automatically serves `index.html` and applies the cache headers in `vercel.json`.

## Project structure

```text
evrim-rugs/
├── index.html       # Website, styles, logo preloader, and GSAP animations
├── assets/          # Logo, favicons, and gallery images
├── frames/          # (optional) 300 JPG images used by the scroll animation, if present
└── README.md
```

## Features

- Museum-style antique-kilim gallery with collection, provenance, motifs, and inquiry sections.
- A scroll-driven canvas sequence that maps 300 frames to page scroll position (gracefully hides itself if `frames/` isn't present).
- A GSAP-driven logo preloader: the Evrim Rugs mark scales in, then curtains slide away to reveal the homepage.
- A live `CRAFTING THE EXPERIENCE — 0–100%` progress label.
- Two-panel textile-curtain exit that reveals the sharpened homepage hero, navigation, heading, and CTAs.
- Reduced-motion support: the preloader exits quickly without the full animation.

## Customization

- Replace the JPG files in `frames/` using the same `ezgif-frame-001.jpg` naming scheme if you want the scroll sequence active; update `const frameCount = 300` in `index.html` if the count changes.
- Swap `assets/images/evrim_rugs_logo.png` to update the logo everywhere (header, footer, and preloader).
- Change animation timing in the GSAP timelines near the end of `index.html`.

## Notes

The site loads GSAP, Tailwind CSS, Google Fonts, and a few gallery images from public CDNs. An internet connection is needed for those external resources; the scroll frames themselves are local.
