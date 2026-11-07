<div align="center">

# Danny · Portfolio

**A fast, single-file portfolio with a CV-style layout, scroll-driven timeline and a mouse-reactive hero.**

![HTML5](https://img.shields.io/badge/HTML5-14171A?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-14171A?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-14171A?style=flat-square&logo=javascript&logoColor=white)
![No build step](https://img.shields.io/badge/build-none-C23B22?style=flat-square)
![Dependencies](https://img.shields.io/badge/dependencies-0-C23B22?style=flat-square)

<img src="docs/preview.png" alt="Preview of the portfolio hero section" width="880">

</div>

---

## About

This is the personal portfolio of **Danny**, apprentice IT specialist for system integration (Fachinformatiker für Systemintegration) at [Wobcom](https://wobcom.de) in Wolfsburg, and developer. It presents selected projects, a repository browser for [github.com/devdanny21](https://github.com/devdanny21), a career timeline, skills and contact details.

The whole site is one `index.html` file. There is no framework, no bundler and no package manager.

## Features

**Design**
- CV-style layout: a narrow label column, a wide content column and hairlines instead of cards
- One accent colour, used only for links, hover states and the primary button
- Light and dark theme: follows the system setting and can be switched with a toggle that remembers the choice
- Typography: Archivo for headings, Public Sans for text
- Fully responsive, from phone width up to wide desktops

**Motion**
- Hero name rises letter by letter, followed by staggered fade-ins
- Dot grid on a `<canvas>` that reacts to the mouse and pauses when off screen
- Magnetic primary button
- Scroll progress bar and sticky header with scroll-spy navigation
- Sections and rows reveal on scroll with staggered delays
- Animated career timeline: the line fills while you scroll and each node pulses when reached
- Count-up numbers for repositories and player peak

**Interaction**
- Spotlight hover on every row that follows the cursor
- Underlines that draw on hover, arrows that slide in, titles that shift
- Repository filter (All, Own, Forks) with a sliding indicator and animated list changes
- Copy-to-clipboard button for the Discord name with a text fallback

**Care for users**
- `prefers-reduced-motion` turns off all animation and shows content immediately
- Semantic landmarks, labelled controls and visible keyboard focus
- `localStorage` access is wrapped in `try/catch`, so the page works with blocked storage
- All content stays visible when JavaScript is unavailable; scripts only add motion and interaction

## Tech stack

| Part | Choice |
| --- | --- |
| Markup | Semantic HTML5 |
| Styling | Plain CSS with custom properties as design tokens |
| Behaviour | Vanilla JavaScript (`IntersectionObserver`, `ResizeObserver`, `requestAnimationFrame`, Canvas 2D) |
| Fonts | [Archivo](https://fonts.google.com/specimen/Archivo) and [Public Sans](https://fonts.google.com/specimen/Public+Sans) via Google Fonts |

## Project structure

```text
.
├── index.html        the entire site: markup, styles and scripts
├── docs/
│   └── preview.png   screenshot used in this README
└── README.md
```

## Getting started

Open `index.html` in a browser, or serve the folder locally:

```bash
python3 -m http.server 8080
```

Then visit <http://localhost:8080>.

## Customise

Everything lives in `index.html`.

| What | Where |
| --- | --- |
| Colours, easing and fonts | the `:root` block at the top of the `<style>`, plus the two dark-theme blocks below it |
| Name, role and intro | the `.hero` section |
| Featured projects | the first two `article.row.item` elements in `#projekte` |
| GitHub repositories | the `a.repo` elements; set `data-kind="own"` or `data-kind="fork"` |
| Career timeline | the `article.tl-item` elements in `#werdegang` |
| Skills | the rows inside `dl.skills`; every word is a `<span>` |
| Contact details | the `#kontakt` section |

When you add or remove a repository, update the numbers in the three `data-count` attributes of the filter tabs and in the GitHub fact in the hero.

To change the hero background, edit the `step` variable in the canvas script (grid spacing) or the radius value `170` (size of the mouse glow).

## Deploy

**GitHub Pages**

1. Push the repository to GitHub.
2. Open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and the `/ (root)` folder, and save.
4. The site is available at `https://<username>.github.io/<repository>/` after a minute.

**Netlify, Vercel, Cloudflare Pages**

Create a project from the repository, leave the build command empty and set the publish directory to the repository root.

## Browser support

Current versions of Chrome, Edge, Firefox and Safari. The page needs CSS custom properties, `mask-image`, `:focus-visible`, `IntersectionObserver` and Canvas 2D.

## Credits

- Fonts: Archivo and Public Sans, both licensed under the [SIL Open Font License](https://openfontlicense.org)
- Design and code: Danny

## Contact

- GitHub: [@devdanny21](https://github.com/devdanny21)
- Discord: `devdanny21`
