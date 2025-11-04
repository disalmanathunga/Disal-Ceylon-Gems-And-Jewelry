# Disal Ceylon Gems & Jewelry

A modern, mobile‑friendly single-page website showcasing Sri Lankan gemstones and jewelry. Built with HTML, CSS, and vanilla JavaScript.

## Features

- Hero section with background video and overlay
- About and Why Choose Us sections
- Tabbed Gallery with three categories:
  - Rough Gemstones
  - Cut And Polish Gemstone
  - Jewellery
- Product names auto-derived from image filenames
- Smooth scrolling, active nav highlighting, and subtle animations
- Responsive design with mobile menu

## Getting Started

### Prerequisites

No build tools are required. Any static server or opening `index.html` directly in a browser works.

### Run Locally

Option 1: Open directly
- Double‑click `index.html` to open it in your browser.

Option 2: Serve with a local server (recommended)
- Python 3: `python -m http.server 8000`
- Then visit: `http://localhost:8000`

## Project Structure

```
Disal_Gems_And_Jewelry/
├─ index.html          # Main page
├─ style.css           # Styles (gold/black theme, responsive)
├─ main.js             # Interactions & animations
└─ Images/
   ├─ Background.mp4   # Hero background video
   ├─ logo1.png        # Site logo
   ├─ Rough Gemstones/ # Rough stones (images)
   ├─ Cut And Polish Gemstone/ # Cut & polished stones (images)
   └─ jewellery/       # Finished jewelry (images)
```

Important: The folder name is `Images` with an uppercase I. Paths in HTML/CSS are case‑sensitive on many servers.

## Managing the Gallery

The Gallery shows three categories with tabs. Items are listed in `index.html` using `<img>` tags pointing to files inside `Images/...`.

- To add a product, just drop a new image into the correct folder and add a matching gallery item in `index.html` under the proper category block.
- The text label shown on hover should match the filename (without extension). Example:

```html
<div class="gallery-item">
    <img src="Images/Rough Gemstones/Natural Teal Sapphire.jpg" alt="Natural Teal Sapphire">
    <div class="gallery-overlay">
        <p>Natural Teal Sapphire</p>
    </div>
    </div>
```

### Category Tabs

Tabs are buttons with `data-category` attributes that toggle visibility of matching containers:

```html
<button class="tab-btn" data-category="rough">Rough Gemstones</button>
...
<div class="gallery-category" data-category="rough"> ... </div>
```

The switching logic is in `main.js`. It adds/removes the `active` class on the button and the matching `.gallery-category`.

## Hero Background Video

- Video file: `Images/Background.mp4`
- The `<video>` element is placed inside the hero section and styled to cover the background.
- Layering:
  - `.hero-video` (z-index: 0)
  - `.hero-overlay` (z-index: 1) – darkens the video for readable text
  - `.hero-content` (z-index: 2)

To replace the video, swap `Images/Background.mp4` with your own file and keep the same filename (or update the `src` in `index.html`).

## Styling Notes

- Color palette uses a black & gold theme (see CSS variables).
- Active gallery tab shows a gold background effect with white text. Text is wrapped in a `<span>` and layered above the gold ripple.

## Deployment

Because this is a static site, you can host it anywhere that serves static files:

- GitHub Pages: push to `main` and configure Pages to serve from the repository root
- Netlify/Vercel: drag‑and‑drop the folder or connect the repo
- Any static host: upload the files preserving the folder structure and case

## Conventions & Tips

- Keep image filenames human‑readable; they appear as product names.
- Maintain exact folder names and case (e.g., `Images/`, not `images/`).
- Optimize images for web (JPG/PNG) to improve load time.
- If you add very large videos, consider providing a compressed MP4 and optional WebM fallback.

## License

Proprietary. All rights reserved by Disal Ceylon Gems & Jewelry unless otherwise specified.

