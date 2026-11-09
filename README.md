# Awesome-System-Status-Uptime-Monitoring

# Awesome System Status & Uptime Monitoring

> A curated list of top System Status and Uptime Monitoring platforms — both SaaS/Hosted commercial solutions and open-source alternatives for tracking service availability and communicating incidents to users.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
- [Open-Source Software](#-open-source-software)
  - [Uptime Kuma](#uptime-kuma)
  - [Gatus](#gatus)
  - [OneUptime](#oneuptime)
  - [Kener](#kener)
  - [Cachet](#cachet)
  - [cState](#cstate)
  - [StatPing.ng](#statpingng)
  - [Openstatus](#openstatus)
  - [Kuvasz Uptime](#kuvasz-uptime)
- [Comparison at a Glance](#-comparison-at-a-glance)
- [Contributing](#-contributing)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted System Status and Uptime Monitoring platforms, sorted in descending order by company size (valuation / annual revenue).

| Platform | Company Size (Valuation / Revenue) | Starting Paid Price | Free Tier / Trial Limit | Key Focus & Strengths | Primary Trade-offs |
|---|---|---|---|---|---|
| **Atlassian Statuspage** | ~$40B–$55B market cap / ~$4.4B–$5.2B ARR | $29/mo (Hobby plan) | **Free forever plan**: Up to 100 subscribers, 2 team members, 2 metrics, 25 components, email & Slack/Teams notifications | Industry-standard incumbent with deep integrations (Datadog, New Relic, PagerDuty, Jira, Slack). Built-in incident workflows and subscriber management. | High pricing at scale; subscriber notifications paywalled on low tiers; SAML SSO enterprise-only. |
| **Freshstatus** (Freshworks) | ~$3.5B–$4.5B market cap / ~$720M–$840M ARR | $19/agent/mo (Freshservice Starter; legacy was $0) | **Free forever plan**: Up to 250 subscribers, unlimited services/components, custom domain support, email & Slack alerts | Deep native integration into the Freshworks ecosystem (Freshdesk/Freshservice); generous free tier allowances. | Standalone product transitioned into Freshservice suite; limited standalone monitoring depth. |
| **Better Stack** | ~$93M valuation / ~$3.8M ARR | $29/mo (Team plan) | **Free forever plan**: 1 status page (custom domain & dark mode), 10 uptime monitors (3-min checks), 10 heartbeats, email & Slack alerts | Bundles uptime monitoring, on-call scheduling, log management, and status pages into one cohesive vendor. Sub-30s checks on paid plans. | High-volume log storage (>100GB/mo) gets pricey; enterprise procurement sometimes requires Atlassian specifically. |
| **StatusCast** | ~$1.1M estimated ARR (Acquired by 4me / Xurrent) | $39/mo (Starter plan) | **14-day free trial**: Full access to status page features, multi-channel alerts, and ITSM integrations (no credit card required) | Specializes in employee-facing internal IT status pages, enterprise ITSM integrations, and audience segmentation. | Geared primarily toward internal corporate IT rather than public developer-facing status pages. |
| **Statuspal** | ~$550K estimated ARR | $46/mo (Hobby plan) | **14-day free trial**: Up to 10 monitored services, 5 team members, 500 subscribers, full public status page features | Advanced subscriber management, multi-language pages, granular audience segmentation, and cost-effective SMB pricing. | Smaller third-party monitoring integration catalog; lean team with narrower feature scope than enterprise suites. |
| **Instatus** | ~$297K estimated ARR | $20/mo (Pro plan) | **Free forever plan**: Up to 200 email subscribers, 15 monitors (2-min checks), 5 team members, 2 on-call members (`instatus.com` domain) | Extremely fast page load speeds (sub-100ms first paint), clean modern UI, affordable custom domain upgrade at $20/mo. | Smaller integration ecosystem; lacks deep enterprise governance and complex incident workflows. |
| **Hund** | Bootstrapped / Profitable (<$1M ARR) | $29/mo (20 components base) | **30-day free trial**: Full access to component dependency modeling, watchdog monitoring, and status page features (no credit card required) | Deep component hierarchy (groups, regions, sub-components, nested dependencies) and granular state machines for 50+ services. | Lower brand recognition; minimal growth marketing; overkill for simple services (<10 components). |

---

## 🟩 Open-Source Software

Self-hosted, community-driven System Status and Uptime Monitoring tools. The open-source ecosystem spans **monitoring-first tools with status pages**, **status-page-first tools**, and **full incident lifecycle platforms**.

### Uptime Kuma
**Stack:** Node.js / SQLite | **License:** MIT  
Uptime Kuma is the most popular self-hosted uptime monitor, often described as an open-source UptimeRobot alternative [citation:8]. It supports HTTP(s), TCP, ping, DNS, and keyword monitoring with **78+ notification providers** (the largest alerting ecosystem in the category) [citation:14]. It includes a built-in status page and a polished web UI. **Trade-off:** Primarily a monitoring tool; its status page is functional but less feature-rich than dedicated status page platforms, and it lacks incident management workflows [citation:14].  
**Best for:** Teams wanting a proven, easy-to-deploy uptime monitor with a built-in status page and the broadest notification coverage.

### Gatus
**Stack:** Go / PostgreSQL or SQLite | **License:** Apache-2.0  
Gatus is a developer-oriented health dashboard with **10k+ GitHub stars**, configured entirely via YAML [citation:11][citation:5]. It monitors HTTP, ICMP, TCP, DNS, GraphQL, and TLS certificate expiry, exports Prometheus metrics, and alerts to Slack, Discord, Teams, PagerDuty, and 20+ providers [citation:11]. The YAML config is version-controlled and GitOps-friendly, with every monitor reviewable as a pull request [citation:11]. **Trade-off:** No admin UI (all configuration via YAML), no incident management or maintenance scheduling, and no subscriber notifications [citation:14].  
**Best for:** DevOps teams wanting GitOps-native monitoring with Prometheus integration and minimal resource usage (~10 MB RAM at idle).

### OneUptime
**Stack:** Docker / Kubernetes | **License:** Open Source  
OneUptime is the "everything platform": monitoring, status pages, on-call, incident management, and logs in one project [citation:2]. It can replace several paid tools at once, but expects you to be comfortable with Docker or Kubernetes and a real chunk of resources [citation:2]. **Trade-off:** On a small VPS it is the wrong tool; it is heavier than single-binary alternatives and intended for platform teams already running Kubernetes [citation:2].  
**Best for:** Platform teams wanting one open-source system to own the entire incident lifecycle (monitoring, on-call, status page, logs).

### Kener
**Stack:** SvelteKit / Node.js / SQLite or PostgreSQL | **License:** MIT  
Kener is a status page with **full incident management lifecycle**, 11 active monitoring types, maintenance windows (with RRULE), and subscriber email notifications [citation:14]. It has an admin dashboard with RBAC (3 roles), 17+ REST API endpoints, i18n support, and embeddable widgets (badges, bars, charts) [citation:14]. **Trade-off:** Smaller community than Uptime Kuma or Gatus, and its monitoring depth is less than dedicated monitoring tools [citation:14].  
**Best for:** Teams wanting a balanced open-source status page with incident management, monitoring, and subscriber notifications in one tool.

### Cachet
**Stack:** PHP / Laravel / MySQL/PostgreSQL/SQLite | **License:** BSD-3 (2.x) / Custom source-available (3.x)  
Cachet is the long-running PHP-based status page system [citation:3]. **Important caveat:** The 3.x rebuild is still in development with no stable release; the newest tagged stable release remains v2.4.1 from 2023, and the v3 branch ships under a custom source-available license rather than the BSD one 2.x carried [citation:2]. It is a **page-first** tool: v3 added a basic HTTP check, but you schedule it yourself and a failure colours a component rather than opening an incident, so in practice you still feed it from elsewhere [citation:2].  
**Best for:** PHP teams wanting a traditional status page with a dashboard, accepting slow development and the lack of built-in active monitoring.

### cState
**Stack:** Hugo (static) | **License:** MIT  
cState is a static status page for Hugo: clean design, minimal JS, super light HTML/CSS, high customization, optional admin panel, and a read-only API [citation:8]. It is **purely a communication page** — there is no active monitoring; incidents are created via Markdown files or a CMS [citation:14]. Best used with Netlify or Docker.  
**Best for:** Teams that already have monitoring elsewhere and need a fast, serverless incident communication page with no runtime dependencies.

### StatPing.ng
**Stack:** Go / Docker | **License:** GPL-3.0  
StatPing.ng is a community-kept fork of the older Statping, a single Go binary that does both monitoring and a status page [citation:2][citation:8]. It automatically fetches the application and renders a status page. **Trade-off:** Smaller community behind it than Uptime Kuma or Gatus [citation:2].  
**Best for:** Teams wanting a single-binary tool that combines basic monitoring with a status page, accepting a smaller community.

### Openstatus
**Stack:** AGPL-3.0 / Docker | **License:** AGPL-3.0  
Openstatus is fully open source and can be self-hosted (the checker runs as an 8.5MB Docker image) or used as managed SaaS [citation:6]. It is used by open-source projects like Cal.com, Documenso, Hanko, and OpenPanel for transparent uptime data, with subscriber notifications via email, RSS/Atom, and JSON [citation:6]. The free plan includes one monitor, one status page, and 6 regions [citation:6].  
**Best for:** Open-source projects and small teams wanting an open-source status page with a free managed tier and community subscriptions.

### Kuvasz Uptime
**Stack:** Kotlin / Docker | **License:** Open Source  
Kuvasz is a performant uptime and SSL monitoring service with brandable status pages, Infrastructure-as-Code support, Prometheus integration, and a complete REST API [citation:8]. It supports per-monitor notification channels (Slack, Discord, Telegram, PagerDuty, MS Teams, Google Chat), Prometheus and OpenTelemetry exporters, maintenance windows, and an MCP server for AI assistant integration.  
**Best for:** Teams wanting a modern, API-driven uptime monitor with brandable status pages and strong notification/integration support.

---

## 📊 Comparison at a Glance

| Software | License | Type | Monitoring | Status Page | Incident Mgmt | Self-Hosted | Best For |
|----------|---------|------|------------|-------------|---------------|-------------|----------|
| **Atlassian Statuspage** | Proprietary | Status page | (Integrations) | ✅ | ✅ | ❌ | Enterprise procurement |
| **Better Stack** | Proprietary | Bundled suite | ✅ | ✅ | ✅ On-call | ❌ | Indie/mid-market consolidation |
| **Instatus** | Proprietary | Status page | (Integrations) | ✅ | ✅ | ❌ | Affordable Statuspage alt |
| **Statuspal** | Proprietary | Status page | (Integrations) | ✅ | ✅ | ❌ | Subscriber management |
| **Hund** | Proprietary | Status page | (Integrations) | ✅ | ✅ | ❌ | Component-heavy services |
| **Uptime Kuma** | MIT | Monitoring + page | ✅ | ✅ Basic | ❌ | ✅ | Broad alerting + simple page |
| **Gatus** | Apache-2.0 | Monitoring + page | ✅ | ✅ Basic | ❌ | ✅ | GitOps-native monitoring |
| **OneUptime** | Open Source | Full lifecycle | ✅ | ✅ | ✅ On-call | ✅ | K8s platform teams |
| **Kener** | MIT | Status page + monitor | ✅ | ✅ | ✅ | ✅ | Balanced OSS status page |
| **Cachet** | BSD/SSPL | Status page | (Basic check) | ✅ | ✅ | ✅ | PHP traditional page |
| **cState** | MIT | Static page | ❌ | ✅ | (Markdown) | ✅ (Static) | Serverless communication |
| **Openstatus** | AGPL-3.0 | Status page + monitor | ✅ | ✅ | ✅ | ✅ | Open-source projects |
| **Kuvasz** | Open Source | Uptime + SSL | ✅ | ✅ | (Maintenance) | ✅ | API-driven monitoring |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source System Status or Uptime Monitoring tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source. Note that the open-source ecosystem **splits** between monitoring-first tools with basic status pages (Uptime Kuma, Gatus), status-page-first tools (Cachet, cState, Kener), and full incident lifecycle platforms (OneUptime). Uptime Kuma is the most popular entry point for uptime monitoring with a built-in page, while Kener offers the most balanced open-source status page with incident management and monitoring in one tool. Gatus is the strongest choice for DevOps teams wanting YAML/GitOps-native configuration.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
