# GanttBoard for Jira — landing site

Static HTML/CSS/JS marketing site for https://getganttboard.com. No framework,
no build step. Edit the HTML directly and push.

## Deploy

GitHub Pages, already configured:

- **Branch:** `main`
- **Folder:** `/docs` ← this directory
- **Custom domain:** `getganttboard.com`, set by the `CNAME` file here

Pushing to `main` redeploys. A rebuild takes about a minute, so a page fetched
immediately after a push can still be the previous version — check twice before
concluding a change didn't land.

The empty `.nojekyll` file stops GitHub Pages running Jekyll, which would
otherwise ignore files and folders beginning with an underscore.

## Structure

```
docs/
├── index.html              # hero landing page
├── features.html           # feature overview
├── features/               # 14 per-feature deep-dive pages
├── blog/                   # 8 posts, index.html lists them
├── pricing.html  docs.html  changelog.html
├── eula.html  privacy.html  security.html
├── assets/                 # styles.css, logo, screenshots/
├── CNAME  robots.txt  sitemap.xml  llms.txt
└── googleae6864541384f9c5.html   # Search Console verification — do not delete
```

Add a new page: create the HTML, then add it to `sitemap.xml`. New blog posts
also need a link from `blog/index.html`.

## Things that are easy to get wrong

- **The Marketplace app id `2897452546` is real.** It appears across the HTML and
  is the live listing. Do not treat it as a placeholder to be substituted.
- **Promo date: `January 1, 2027`, everywhere.** Any page carrying a different
  date is a P0 bug. Grep before shipping copy changes.
- **The demo video id is `IZAUC6g_PFU`.** Earlier ids (`vRXU3zlNmvw`,
  `YZza8h4HOvk`) are unlisted on YouTube. An unlisted video still plays when
  embedded, so a stale embed looks fine and is easy to miss.
- **No personal identifiers on any public surface** — no personal GitHub links,
  no personal email. Public contact is `dev@getganttboard.com`.
- **Competitor claims must be sourced and dated**, or omitted.

## Notes

- No JS frameworks. One small inline `<script>` per page for the mobile nav
  toggle; the home page adds a second for the screenshot cycler.
- No Google Fonts, no analytics, no third-party trackers, no external CSS.
- Open Graph and Twitter Card meta on every page. JSON-LD `SoftwareApplication`
  schema on `index.html` only.
- Canonical URLs, `sitemap.xml` and `robots.txt` all assume
  `https://getganttboard.com/`.
