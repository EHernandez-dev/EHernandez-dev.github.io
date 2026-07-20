# Personal website

Static website for elenahernandezmartinez.com, hosted for free on GitHub Pages.

## Design decision (2026-07-20)

Prototyped three homepage layouts (immersive full-screen hero / split screen /
minimal), then two hero fade treatments (to soft white vs to dark navy).
Final choice: immersive full-screen hero with the name centered on one line in
medium weight, tagline below, and a smooth multi-stop fade into dark navy
(#0d2130), keeping the whole site on the dark theme. The header is fixed and
turns solid navy on scroll; the About portrait is vertically centered against
its text. A soft-white lower section was tried and rejected.

Projects page (formerly Simulations, renamed): after several prototype rounds
(feature rows / cinematic banners / compact index / featured+list hybrids), the
final design is a slim full-bleed rotating THEME banner (AI for Good, AI for
Science, High-Performance Computing Simulations; 45vh, crossfade every 5s, Ken
Burns zoom, arrows + dots, pause on hover, reduced-motion respected) above a
complete numbered list of the four projects: SpeechTransformer, Simulation-
Based Inference, SLOW, Galaxy Cluster Zoom-ins. Rationale: an all-cinematic
project grid made nothing stand out; the theme banner gives identity while the
list does the navigating. Theme slides and most list thumbnails use CSS
placeholder art until real images can be downloaded (network TLS interception
blocked fetching during the session).

Contact page: prototyped info+form vs minimal-no-form vs action tiles. Winner:
the info layout WITHOUT a form (email, location, and social links under small
gold labels). The Wix contact form was deliberately dropped, so no Formspree
setup is needed.

## Structure

- `index.html`: About page (homepage)
- `projects.html`: cinematic banner overview of projects, linking to:
  - SpeechTransformer (external, TODO: confirm repo URL and description)
  - `machine-learning.html` (simulation-based inference: cluster profiles, CAMELS)
  - `local-universe.html` (SLOW)
  - `galaxy-clusters.html` (Coma cluster zoom-ins)
- `talks.html`: list of talks
- `cv.html`: embedded CV (expects `assets/cv.pdf`)
- `contact.html`: contact info and form
- `css/style.css`: shared stylesheet (supports light and dark mode)
- `assets/`: images and the CV PDF

## Remaining TODOs

1. Add your CV as `assets/cv.pdf`
2. Search for `TODO` in the HTML files and fill in:
   - Google Scholar profile URL (in the nav of every page)
   - SpeechTransformer repo URL and one-line description (`projects.html`),
     plus an image for the "AI for Good" carousel slide
3. Verify and complete the talks list in `talks.html`
4. Decide whether to port the two remaining Wix pages that were discovered
   late: "Teaching & Outreach" and "Other Projects"

## Publishing

1. Create a public GitHub repository named exactly `EHernandez-dev.github.io`
2. Push this folder's contents to its `main` branch
3. The site appears at https://ehernandez-dev.github.io within a few minutes

## Custom domain (optional)

To keep using elenahernandezmartinez.com:

1. In the repository: Settings > Pages > Custom domain > enter the domain
2. At your domain registrar, point the DNS to GitHub Pages:
   - `A` records for the apex domain: 185.199.108.153, 185.199.109.153,
     185.199.110.153, 185.199.111.153
   - `CNAME` record for `www` pointing to `ehernandez-dev.github.io`
3. Enable "Enforce HTTPS" once the certificate is issued

Note: if the domain is currently registered through Wix, it stays yours as long as
the domain registration itself is renewed. You can cancel the website plan and keep
the domain, or transfer the domain to another registrar.

## Local preview

Just open `index.html` in a browser. No build step is required.
