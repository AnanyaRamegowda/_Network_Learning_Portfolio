# _Network_Learning_Portfolio
A single-page technical knowledge portfolio for **Ananya A R** (B.Tech — Electronics and Communication Engineering, 2026 Graduate), showcasing networking and telecom concepts, protocols, and platforms studied — from core networking fundamentals to GPON/next-generation PON fiber-access technology and vendor platforms (Tejas, Nokia).

> This is a knowledge portfolio, not a project/experience portfolio — it does not claim work experience, certifications, or hands-on projects. It presents concepts that have been studied and understood, organized for quick browsing.

---

## ✨ Features

- **9 technical categories, 125+ concept cards** — Networking Fundamentals, Switching & VLAN, IP Services, Network Protocols, Routing, Service Provider Networking, GPON Technology, Vendor Technologies & Platforms, and Next-Generation PON.
- **Animated "Network Learning" diagram** on the home page — an SVG node graph with the 9 categories orbiting a central node, connected by animated light-pulse traffic, doubling as clickable navigation.
- **Expand-to-read concept cards** — every concept shows just its name by default; clicking anywhere on the card reveals a concise 2–4 line explanation.
- **Internal hash-based routing** (`#/gpon`, `#/vendor-technologies`, etc.) — no page reloads, no external links, safe to deploy as a static site with no backend/router config needed.
- **Dark / Light theme toggle** with a full custom color system (CSS variables) — cards, borders, and headings tint with an accent-color cycle (blue / cyan / purple / teal) in both themes.
- **Vendor architecture diagrams** — Tejas OLT → Tejas NMS, and Nokia Lightspan → Altiplano/ACS vs. Nokia ISAM → Pizza Box / Chassis → AMS, shown as connected node trees.
- **PON evolution timeline** — GPON → XG-PON → XGS-PON → Combo PON.
- Fully responsive, with a compact hamburger-style navigation menu at every screen size.

---

## 🛠️ Tech Stack

This project is intentionally dependency-free:

- **HTML5 + vanilla JavaScript** — no framework, no build step, no `node_modules`.
- **CSS3** — custom properties (variables) for theming, CSS Grid/Flexbox for layout, `color-mix()` for tint blending.
- **SVG** — hand-generated network diagram with native `<animateMotion>` for the traffic-pulse animation.
- **Fonts** — [Space Grotesk](https://fonts.google.com/specimen/Space+Grotesk) (headings), [Inter](https://fonts.google.com/specimen/Inter) (body), [IBM Plex Mono](https://fonts.google.com/specimen/IBM+Plex+Mono) (concept names/labels), loaded via Google Fonts.

Everything lives in a **single HTML file** — easy to read, easy to fork, easy to deploy anywhere that serves static files.

---

## 📁 Project Structure

```
network-learning-portfolio/
├── index.html      # entire site: markup, styles, data, and routing logic
└── README.md
```

All concept data (names + explanations), routing, theming, and rendering logic live inside `index.html`, organized into clearly commented sections:

| Section in `index.html` | What it does |
|---|---|
| `<style>` | Theme variables, layout, card/nav/hero styling |
| `ROUTES` | The 9 category routes + Home |
| `DATA` | All concept names and their explanations, grouped by category/subcategory |
| `VENDOR_DETAILS` | Explanations for the vendor architecture nodes |
| `heroNetworkSVG()` | Builds the animated home-page network diagram |
| `renderCategoryPage()` / `renderVendorPage()` / `renderNextGenPage()` | Page renderers |
| `render()` | Hash-based router — maps the URL hash to a page renderer |

---

## 🚀 Running Locally

No install, no build step — just open the file:

```bash
git clone https://github.com/<your-username>/network-learning-portfolio.git
cd network-learning-portfolio
open index.html      # macOS
# or: start index.html   (Windows)
# or: xdg-open index.html   (Linux)
```

Or serve it with any static server, e.g.:

```bash
npx serve .
# or
python3 -m http.server 8000
```

---

## 🌐 Deploying on GitHub Pages

1. Push this repository to GitHub.
2. Go to **Settings → Pages**.
3. Under **Source**, select the branch (e.g. `main`) and root folder `/`.
4. Save — your site will be live at:
   `https://<your-username>.github.io/network-learning-portfolio/`

Since navigation uses hash routes (`#/gpon`, `#/routing`, …) rather than real paths, it works correctly on GitHub Pages (or any static host) with zero extra configuration — no `404.html` redirect trick needed.

---

## 🎨 Customizing

- **Add or edit a concept:** find its category inside the `DATA` object in `index.html` and add a `['Name', 'Explanation'].` pair to the relevant group's `items` array.
- **Add a new category:** add an entry to `ROUTES`, a matching key in `DATA` with a `title`, `sub`, and `groups`, and an entry in `CATEGORY_META` for the home-page card.
- **Theme colors:** edit the CSS variables under `html[data-theme="dark"]` and `html[data-theme="light"]` at the top of the `<style>` block.

---

## 👤 Author

**Ananya A R**
B.Tech — Electronics and Communication Engineering, 2026 Graduate

---

## 📄 License

This project is shared for personal/portfolio use. Feel free to fork it as a template for your own knowledge portfolio — please don't republish it with someone else's name/content as-is.
