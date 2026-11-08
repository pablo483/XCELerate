# XCELerate

A dark-mode SaaS landing page for **XCELerate (Bundle 2.0)** — a curated collection of 1,000+ Excel and Google Sheets templates — built as a zero-build single-file web application with interactive HTML5 Canvas physics, GSAP motion, Tailwind CSS, and eSewa checkout integration.

## Key Features

- **Interactive Spreadsheet Grid Canvas (`#grid-canvas`):** Full-viewport HTML5 2D `<canvas>` rendering a `50px` cell grid where cursor movement lights up a `3×3` Excel-green cell brush that fades over time (`requestAnimationFrame`) and surfaces floating formula tokens (`=SUM()`, `=VLOOKUP`, `=IF()`, `INDEX`, `MATCH`, `98.2%`, `$12K`).
- **3D Perspective Hero & Magnetic Pill:** Mouse-tracked CSS `perspective(1000px)` tilt (`rotateX`/`rotateY` clamped to `±8°`) on `#hero-mockup` paired with a GSAP magnetic spring pill (`#dashboard-title-pill`) using `elastic.out(1, 0.3)` snap-back and floating metric cards.
- **24-Hour Flash-Sale Countdown Banner:** Fixed top FOMO banner updating `#countdown-timer` (`HH:MM:SS`) every second.
- **Template Category Marquee & Brand Strip:** Seamless CSS-animated category ticker (`Financial Models`, `SaaS Metrics`, `Gantt Charts`, `Budget Trackers`, `Inventory Management`, `SEO Dashboards`, `HR Trackers`) and social-proof brand row.
- **Scroll-Triggered Feature Cards:** Hero stagger entrances powered by GSAP and card reveals driven by native `IntersectionObserver`.
- **eSewa ePay Form Integration:** Pre-wired checkout form targeting eSewa's UAT sandbox (`https://uat.esewa.com.np/epay/main`) with `EPAYTEST` merchant parameters (`pid="XCEL-BUNDLE-01"`).

## Tech Stack

| Layer | Technology |
| :--- | :--- |
| **Markup & Styling** | HTML5, Tailwind CSS (Play CDN with custom OLED dark theme `#000000` & `#21A366` tokens) |
| **Animation & Physics** | GSAP `3.12.2`, HTML5 Canvas 2D API, CSS Keyframes, `IntersectionObserver` |
| **Typography** | Google Fonts (`Inter`, `JetBrains Mono`) |
| **Payments** | eSewa ePay Form (`uat.esewa.com.np` sandbox) |

## Project Structure

```text
XCELerate/
├── index.html   # Complete landing page markup, styles, canvas grid & GSAP logic
└── README.md    # Project documentation
```

## Run Locally

No build step or package installation is required.

```bash
git clone https://github.com/pablo483/XCELerate.git
cd XCELerate
```

Open `index.html` directly in your browser, or serve it with any static HTTP server:

```bash
# Python 3
python -m http.server 8000
```

Then visit `http://localhost:8000`.

## Configuration Notes Before Production

- **Payment Gateway (`index.html`):** Update the eSewa `<form>` action from `https://uat.esewa.com.np/epay/main` to your live eSewa production endpoint (or current HMAC-signed eSewa v2 API flow), replace `scd="EPAYTEST"` with your merchant code, and replace `su`/`fu` placeholder URLs (`https://google.com?q=...`) with your live callback pages.
- **Currency Consistency:** The pricing card copy lists USD pricing while the eSewa submit button submits `amt="49"` in NPR (`Pay Rs. 49 with eSewa`) — align the displayed currency and payment amount before launch.
- **Navigation Anchor:** Add `id="templates"` to the marquee `<section>` if you want the navbar `Templates` link (`href="#templates"`) to scroll directly to that band, and replace placeholder footer links (`#`).

## Author

**Sudarshan GC** — [@pablo483](https://github.com/pablo483)
