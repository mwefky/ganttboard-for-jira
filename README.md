# GanttBoard for Jira

**Free Gantt charts for Jira Cloud — no 10-user cap, no time limit.**

[![Install on Atlassian Marketplace](https://img.shields.io/badge/Atlassian%20Marketplace-Install-blue)](https://marketplace.atlassian.com/apps/ganttboard-for-jira)
[![Partner Supported](https://img.shields.io/badge/Partner-Supported-green)](https://marketplace.atlassian.com/apps/ganttboard-for-jira)
[![Works with Jira Cloud](https://img.shields.io/badge/Works%20with-Jira%20Cloud-0052CC)](https://marketplace.atlassian.com/apps/ganttboard-for-jira)

GanttBoard is a native Atlassian Forge app that adds a full Gantt chart and spreadsheet view to any Jira Cloud project. Critical path, baselines, auto-scheduling, saved views, color rules, Standup mode, and MS Project XML round-trip — all in the free tier.

Free for everyone through **October 1, 2026**. Paid tiers then start at **$1.20/user/month** (11–100 users), scaling down to **$0.04/user/month** at 1,000+ users — a fraction of BigGantt, WBS Gantt, or GanttTable.

---

## Install

1. Open your Jira Cloud site
2. Go to **Apps → Explore more apps**
3. Search for **GanttBoard for Jira**
4. Click **Try it free**
5. Open any project → click the **GanttBoard** tab

Or install directly from the [Atlassian Marketplace listing](https://marketplace.atlassian.com/apps/ganttboard-for-jira).

---

## Features

- **Gantt + spreadsheet split view** — toggle between table-only, split, and Gantt-only
- **4 dependency types** — Finish-to-Start, Start-to-Start, Finish-to-Finish, Start-to-Finish, with lag/lead
- **Critical path** — auto-highlighted based on CPM
- **Baselines** — save snapshots, compare with ghost-bar overlay
- **Auto-scheduling** — cascade date changes through dependent tasks
- **Saved views** — filter + zoom + columns persisted per user
- **Color rules** — conditional formatting by status, priority, assignee, issue type
- **Standup mode** — one-click: active sprint, hide done, flat view, day zoom
- **Inline edit** — double-click dates, status, assignee (writes back to Jira)
- **Multi-select + bulk ops** — Ctrl/Shift/Ctrl+A
- **Undo/redo** — Ctrl+Z / Ctrl+Shift+Z
- **Keyboard shortcuts** — press `?` for the full list
- **Import/export** — MS Project XML round-trip, PNG snapshot, CSV
- **Dark mode** — follows your Atlassian theme

See the full demo: [youtube.com/watch?v=YZza8h4HOvk](https://www.youtube.com/watch?v=YZza8h4HOvk)

---

## Pricing

| Users | Price per user/month |
|---|---|
| 1–10 | **Free forever** |
| 11–100 | $1.20 |
| 101–250 | $0.80 |
| 251–1,000 | $0.25 |
| 1,001+ | $0.12 → $0.04 |

Free for everyone until **October 1, 2026**. See full pricing on the [Marketplace listing](https://marketplace.atlassian.com/apps/ganttboard-for-jira).

---

## Support

- **Questions or bug reports:** [Open an issue](https://github.com/mwefky/ganttboard-for-jira/issues)
- **Security vulnerabilities:** [Open a private advisory](https://github.com/mwefky/ganttboard-for-jira/security/advisories/new) — do **not** file a public issue
- **Email:** dev@getganttboard.com

Response SLA: acknowledgement within 3 business days, fix for critical issues within 14.

---

## Platform & data

- **Runs entirely on Atlassian Forge** — no data leaves Atlassian's infrastructure
- **No third-party services** — no analytics, no CDNs, no tracking
- **Encrypted** in transit (TLS) and at rest (Forge KVS)
- **GDPR-compliant** — data auto-deleted on app uninstall
- **Inherits** your Atlassian Cloud data residency settings

Full details in [PRIVACY.md](./PRIVACY.md) and [SECURITY.md](./SECURITY.md).

---

## Documentation

Full user guide and keyboard shortcut reference: **[getganttboard.com/docs](https://getganttboard.com/docs)** *(launching with the public site — same content, searchable)*.

Until the site is live, browse the guides in this repo:

- [Getting started](./README.md#install)
- [Privacy Policy](./PRIVACY.md)
- [Security Policy](./SECURITY.md)
- [End User License Agreement](./EULA.md)

---

## Changelog

### 3.15.1 — April 2026
Removed the in-panel *Open in GanttBoard* deep-link button while cross-project-type navigation testing completes. Will return in a later release.

### 3.15.0 — April 2026
Atlassian Marketplace launch. Full Gantt + spreadsheet view, 4 dependency types, critical path, baselines, auto-scheduling, saved views, color rules, Standup mode, MS Project XML round-trip, PNG/CSV export, dark mode.

---

## License

Copyright © 2026 GanttBoard. All rights reserved.
Use of the app is governed by the [EULA](./EULA.md).
