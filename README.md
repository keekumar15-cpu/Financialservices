# MSAII LLC — Financial Services AI Landing Page

A single-page, CRO-optimized landing page for MSAII LLC's AI infrastructure offer targeting accounting firms, RIAs, and insurance agencies. Built as a static site — no build step, no dependencies, no framework.

**Live structure:** Hero → Quantified Results → Three-Tier Offer Stack → Security & Trust → FAQ → Final CTA, with a single conversion path (a booking modal) triggered from every CTA on the page.

## Tech

- Plain HTML, CSS, and vanilla JS in one file — no bundler, no `node_modules`
- Fonts loaded from Google Fonts CDN (Space Grotesk, Inter, IBM Plex Mono)
- No backend, no forms, no analytics wired in yet (see [Customization](#customization))

## File Structure

```
.
└── index.html   # the entire site — markup, styles, and script
```

Everything lives in one file by design, so the whole site can be dragged onto a host with zero configuration.

## Deploy

### Netlify (drag-and-drop)
1. Go to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag `index.html` (or this whole repo folder) onto the page
3. Done — Netlify serves `index.html` automatically at your site's root

> **Important:** the file must be named `index.html`. Netlify only auto-serves a file with that exact name at the root URL — anything else 404s until you hit its specific path.

### Netlify (Git-based)
1. Push this repo to GitHub
2. In Netlify: **Add new site → Import an existing project** → connect the repo
3. Build command: leave blank (no build step)
4. Publish directory: `.` (repo root, since `index.html` lives there)

### GitHub Pages
1. Push this repo to GitHub
2. **Settings → Pages → Source** → select the branch and `/ (root)` folder
3. Site will be live at `https://<username>.github.io/<repo-name>/`

### Any other static host (Vercel, Cloudflare Pages, S3, etc.)
No build step required — just point the host at this directory and serve `index.html`.

## Customization

| What | Where |
|---|---|
| Booking link | Search `cal.com/keerthana-saravana-kumar-y6aess` — appears once, inside the modal markup |
| Colors / theme | CSS custom properties at the top of the `<style>` block (`:root { --blue, --cyan, --bg, ... }`) |
| Copy (headlines, stats, FAQ, tier details) | Inline in the HTML body, grouped by `<section>` |
| Fonts | `<link>` tags in `<head>`, plus the `--font-display` / `--font-body` / `--font-mono` variables |

### Things to wire up before sending real traffic
- [ ] Swap the placeholder analytics — none are installed yet (GA4, Plausible, etc.)
- [ ] Add a custom domain in your host's dashboard once DNS is ready
- [ ] Add an Open Graph image / meta tags if this will be shared as a link (currently has none)
- [ ] Confirm the Cal.com booking link is the correct, current one before going live

## Browser Support

Uses CSS Grid, `IntersectionObserver`, and `backdrop-filter`. All content is visible by default — scroll animations and the booking modal are progressive enhancements, so the page degrades gracefully if JavaScript fails to load.

## License

Internal MSAII LLC marketing asset — not licensed for redistribution.
