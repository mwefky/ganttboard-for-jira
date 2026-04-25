# GanttBoard for Jira — landing site

Static HTML/CSS/JS marketing site. No framework, no build step.

## Deploy to GitHub Pages

1. Push this repo to GitHub.
2. Repository settings > Pages.
3. Build and deployment: **Deploy from a branch**.
4. Branch: `main`, Folder: `/docs/landing`.
5. Save. The site is live at `https://<username>.github.io/<repo>/` within a minute.
6. (Optional) Add custom domain `ganttboard.app` in repo settings. Add a `CNAME` record pointing to `<username>.github.io` at your DNS provider. Enable "Enforce HTTPS".

The empty `.nojekyll` file prevents GitHub Pages from running Jekyll, which would otherwise ignore files and folders starting with underscores.

## Find-and-replace before going live

Before first deploy, replace these placeholders across every file:

| Placeholder | Replace with | Files |
|---|---|---|
| `https://marketplace.atlassian.com/apps/2897452546/ganttboard-for-jira` | Actual Atlassian Marketplace listing URL, e.g. `https://marketplace.atlassian.com/apps/123456/ganttboard-for-jira` | All `.html` files |
| `ganttboard.app` | Your actual domain, if different | All `.html` files, `sitemap.xml`, `robots.txt` |

Quickest way on macOS / Linux:

```bash
cd docs/landing
grep -rl 'https://marketplace.atlassian.com/apps/2897452546/ganttboard-for-jira' . | xargs sed -i '' 's|https://marketplace.atlassian.com/apps/2897452546/ganttboard-for-jira|https://marketplace.atlassian.com/apps/XXX/ganttboard-for-jira|g'
```

## Before launch: add tracking

Each page has a commented-out slot in `<head>`:

```html
<!-- TODO: add <meta name="google-site-verification" content="..."> and GA4 tag here -->
```

Drop in your Google Search Console verification meta tag and GA4 snippet there.

## File tree

```
docs/landing/
├── .nojekyll
├── README.md
├── robots.txt
├── sitemap.xml
├── index.html                # hero landing
├── features.html             # 8 feature deep-dives
├── pricing.html              # pricing grid + FAQ
├── docs.html                 # getting-started guide
├── changelog.html            # release notes
├── blog/
│   └── jira-gantt-chart-free.html   # cornerstone SEO post
└── assets/
    ├── styles.css
    ├── logo-144.png
    └── screenshots/
        ├── 01_hero.png
        ├── 02_filters.png
        ├── 03_standup.png
        ├── 04_dep.png
        ├── 05_edit.png
        └── 06_cp_baseline.png
```

## Notes

- No JS frameworks. One small inline `<script>` per page for the mobile nav toggle; the home page adds a second tiny cycler for the screenshot showcase.
- No Google Fonts, no third-party trackers, no external CSS.
- Open Graph + Twitter Card meta set on every page. JSON-LD `SoftwareApplication` schema only on `index.html`.
- Canonical URLs, sitemap, and robots all assume `https://ganttboard.app/`. Edit if hosting elsewhere.
