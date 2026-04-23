# Privacy Policy — GanttBoard for Jira

**Last updated:** April 23, 2026
**App name:** GanttBoard for Jira
**Platform:** Atlassian Forge (Jira Cloud)
**Publisher:** Mina Wefky

---

## 1. Overview

GanttBoard for Jira ("the App") is a Gantt chart visualization tool built entirely on the **Atlassian Forge** platform. Because the App runs on Forge, **all data remains within Atlassian's infrastructure** — nothing is sent to external servers, third parties, or the publisher.

This Privacy Policy explains what data the App accesses, how it is stored, and the rights you have over that data.

---

## 2. What Data the App Accesses

The App reads and writes the following data from your Jira Cloud instance, on behalf of the currently authenticated user:

### Jira Issue Data
- Issue key, summary, status, priority, issue type
- Start date, due date, progress
- Assignee (display name, avatar, account ID)
- Parent/child hierarchy (epics, stories, tasks, sub-tasks)
- Issue links (dependencies: Blocks, Relates to, etc.)
- Sprint ID, sprint name, sprint state
- Version release markers

### App-Specific Data (stored in Forge KVS)
- **Baselines** — snapshots of task dates you explicitly save
- **Saved views** — filter + zoom + layout configurations you name and save
- **Color rules** — conditional formatting rules you create
- **Calendar settings** — working days, holidays you configure
- **Project settings** — zoom level, display toggles

### Data the App Does NOT Access
- Issue comments, attachments, worklogs
- User email addresses, phone numbers, or passwords
- Billing or account information
- Data from projects or issues you don't have permission to view in Jira

---

## 3. How the App Uses Data

The App uses your Jira data solely to:

1. Render the Gantt chart visualization
2. Calculate the critical path and auto-schedule tasks
3. Update issue dates, status, and assignee when you drag/edit in the App
4. Create and delete issue links (dependencies) when you draw them in the App
5. Re-rank issues when you drag to reorder them
6. Save baselines and views that you explicitly create

**The App does not:**
- Send any data outside Atlassian Cloud
- Share data with third parties
- Use data for analytics, advertising, or marketing
- Train machine-learning models on your data
- Access data after you uninstall the App

---

## 4. Where Data is Stored

All data stays within **Atlassian's infrastructure**:

| Data type | Storage location |
|-----------|------------------|
| Jira issues | Your Jira Cloud instance (unchanged) |
| Baselines, saved views, settings, color rules | Atlassian Forge KVS (Key-Value Store) |

The App uses **no external databases, no third-party cloud storage, no file systems, and no publisher-operated servers.**

Data residency follows your Atlassian Cloud data residency settings automatically (managed by Atlassian).

---

## 5. Data Encryption

- **In transit:** All communication uses HTTPS/TLS, enforced by the Atlassian Forge platform.
- **At rest:** Forge KVS storage is encrypted at rest by Atlassian.

---

## 6. Access Control

The App makes all Jira API calls using the currently authenticated user's identity (`api.asUser()`). This means:

- The App **cannot** access issues, projects, or fields the user doesn't already have permission to see in Jira
- The App **cannot** elevate privileges or act as an admin
- The App respects all Jira project permissions, issue security levels, and field-level permissions

### Permissions the App requests
- `read:jira-work` — Read issues and projects
- `write:jira-work` — Update issue dates, create/delete links, transition status
- `read:jira-user` — Look up user info for assignee dropdowns
- `storage:app` — Store baselines, views, and settings in Forge KVS

---

## 7. Third-Party Services

**None.** The App does not use:
- Third-party analytics (Google Analytics, Segment, Mixpanel, etc.)
- Advertising networks
- External CDNs (all assets served from Forge)
- Error tracking services (Sentry, Rollbar, etc.)
- Chat/support widgets
- Any other third-party SDKs

---

## 8. Data Retention & Deletion

- **Active use:** App-specific data (baselines, views, settings) persists in Forge KVS until the user or admin explicitly deletes it.
- **Uninstall:** When the App is uninstalled, Atlassian automatically deletes all Forge KVS data associated with the App per Forge platform policy.
- **Jira data:** The App does not store copies of Jira issues — it reads them live from Jira on every load. Deleting an issue in Jira immediately removes it from the Gantt view.

### Right to request data deletion
Customers can delete all App-specific data by uninstalling the App from their Atlassian site. No manual data deletion request is needed.

---

## 9. GDPR Compliance

The App is GDPR-compliant because:

- **No PII is collected** beyond what Jira already stores (assignee display names/avatars)
- **No data is transferred** outside Atlassian's infrastructure
- **Data residency** inherits from the customer's Atlassian Cloud settings
- **Right to deletion** is satisfied by App uninstall
- **Right to access** is satisfied by Jira's existing data export features (the App stores no additional PII)
- **No data processing agreements with third parties** (there are no third parties)

### Data Processing Role
Atlassian is the **Data Processor** for all Jira data, including data rendered by this App. The App publisher is a **sub-processor only** to the extent of the Forge platform infrastructure — and because the App runs entirely on Forge, no data is ever transmitted to the publisher.

---

## 10. Children's Privacy

The App is a business productivity tool and is not directed at children under 13. The App does not knowingly collect data from children.

---

## 11. Security Incidents

If a security vulnerability is discovered in the App, it will be patched and a new version deployed via the Atlassian Marketplace. Customers are notified via the Marketplace update channel.

Security issues should be reported privately via GitHub Security Advisories:
**https://github.com/mwefky/ganttboard-for-jira/security/advisories/new**

See [SECURITY.md](./SECURITY.md) for the full security policy.

---

## 12. Changes to This Policy

If this Privacy Policy changes materially, the "Last updated" date will be revised and the change will be announced in the Marketplace release notes.

---

## 13. Contact

- **Support:** https://github.com/mwefky/ganttboard-for-jira/issues
- **Security:** https://github.com/mwefky/ganttboard-for-jira/security/advisories/new
- **Email:** minawefky3@gmail.com
- **Marketplace listing:** https://marketplace.atlassian.com/apps/ganttboard-for-jira

---

## Summary

- Runs entirely on Atlassian Forge — no external servers
- No data leaves Atlassian Cloud
- No third-party services, analytics, or tracking
- Respects all Jira permissions (user-level access)
- Encrypted in transit and at rest
- Data auto-deleted on App uninstall
- GDPR-compliant, inherits customer data residency
