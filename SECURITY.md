# Security Policy — GanttBoard for Jira

**App name:** GanttBoard for Jira
**Platform:** Atlassian Forge (Jira Cloud)
**Runtime:** Node.js 22.x (managed by Atlassian)
**Last updated:** April 23, 2026

---

## Supported Versions

The latest version deployed to the Atlassian Marketplace is the only supported version. Because the App runs on Atlassian Forge, updates are pushed to all customers automatically on the next page load.

| Version | Supported |
|---------|-----------|
| Latest (Marketplace) | Yes |
| Older versions | No — auto-upgraded by Forge |

---

## Reporting a Vulnerability

If you discover a security vulnerability in GanttBoard for Jira, please report it **privately** — do not open a public GitHub issue.

### How to report
- **Preferred:** Open a private security advisory on GitHub:
  https://github.com/mwefky/ganttboard-for-jira/security/advisories/new
- **Alternative:** Email the publisher at minawefky3@gmail.com with subject `[SECURITY] GanttBoard for Jira`

### What to include
- A description of the vulnerability
- Steps to reproduce (if possible)
- The version of the App (or date of the Marketplace listing you tested)
- Your contact info for follow-up

### What to expect
- **Acknowledgment** within 3 business days
- **Initial assessment** within 7 business days
- **Fix + redeployment** within 14 business days for critical issues
- **Credit** in the Marketplace release notes if you want it (or kept anonymous if you prefer)

---

## Security Architecture

### Platform Security (handled by Atlassian)
- Runtime sandboxing (Forge function isolation)
- HTTPS/TLS on all network traffic
- Encryption at rest for Forge KVS storage
- Authentication via Atlassian Cloud (OAuth 2.0)
- Node.js security patching (managed by Atlassian)
- DDoS protection and rate limiting (Atlassian infrastructure)

### App-Level Security
- All Jira API calls use `api.asUser()` — no privilege escalation
- No external network calls (backend restricted to `*.atlassian.net`)
- No third-party SDKs, analytics, or tracking
- No secrets stored in code or configuration (Forge handles auth)
- Input validation on all user-provided data (JQL, dates, names)
- Dependencies monitored via GitHub Dependabot

### Permission Model
The App requests the minimum scopes needed:

| Scope | Purpose |
|-------|---------|
| `read:jira-work` | Read issues, projects, fields |
| `write:jira-work` | Update dates, links, status, assignee |
| `read:jira-user` | Assignee dropdown population |
| `storage:app` | Store baselines, views, settings |

No admin-level scopes, no organization-wide scopes, no other products' scopes.

---

## Threat Model

### In-scope for security reporting
- Privilege escalation (accessing issues the user shouldn't see)
- Data leaks (sending Jira data to external parties)
- XSS in the Gantt UI
- Injection attacks (JQL, date fields, names)
- Broken authentication or authorization
- Insecure direct object references (IDOR) in Forge resolvers

### Out-of-scope
- Denial-of-service attacks (handled by Atlassian infrastructure)
- Vulnerabilities in Atlassian Forge itself (report to Atlassian)
- Vulnerabilities in Jira Cloud itself (report to Atlassian)
- Social-engineering attacks against users
- Physical attacks on Atlassian data centers

---

## Security Practices

### Development
- TypeScript strict mode for type safety
- Code review required for all changes before release
- All dependencies pinned in `package.json`
- Automated dependency scanning (Dependabot)

### Deployment
- Staged releases: dev → staging → production via Forge environments
- Only the Forge Marketplace deployment pipeline can publish updates
- No direct database access — all storage through Forge KVS

### Monitoring
- Forge platform logs accessible via `forge logs --environment production`
- Atlassian provides error alerting for resolver failures
- No telemetry sent to the publisher (zero data collection by design)

---

## Disclosure Policy

- Reporters will be kept informed throughout the triage and fix process
- We will not pursue legal action against researchers who follow responsible disclosure
- We request a reasonable disclosure window (typically 90 days or until a fix is deployed, whichever is sooner)

---

## Contact

- **Security reports:** https://github.com/mwefky/ganttboard-for-jira/security/advisories/new
- **General support:** https://github.com/mwefky/ganttboard-for-jira/issues
- **Email:** minawefky3@gmail.com
- **Atlassian Marketplace listing:** https://marketplace.atlassian.com/apps/ganttboard-for-jira
