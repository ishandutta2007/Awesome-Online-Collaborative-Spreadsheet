# Awesome-Online-Collaborative-Spreadsheet

# Awesome Online Collaborative Spreadsheet

> A curated list of top Online Collaborative Spreadsheet platforms — both SaaS/Hosted commercial solutions and open-source alternatives for real-time co-editing, data collection, and spreadsheet-based workflows.
> 🌟 Star this repo if you find it useful! 🌟

---

## 📋 Table of Contents

- [SaaS / Hosted Platforms](#-saas--hosted-platforms)
  - [Google Sheets](#google-sheets)
  - [Microsoft Excel Online](#microsoft-excel-online)
  - [Airtable](#airtable)
  - [Smartsheet](#smartsheet)
  - [Coda](#coda)
- [Open-Source Software](#-open-source-software)
  - [Nextcloud Spreadsheet](#nextcloud-spreadsheet)
  - [Casual Sheets](#casual-sheets)
  - [Diwan Sheets](#diwan-sheets)
  - [AlephGrid](#alephgrid)
  - [Baserow](#baserow)
  - [NocoDB](#nocodb)
  - [Rowflare](#rowflare)
  - [SoloSheet](#solosheet)

---

## 🟦 SaaS / Hosted Platforms

Commercial, cloud-hosted Online Collaborative Spreadsheet platforms. These are not open-source but are included as reference points for feature comparison.

### Google Sheets
**Type:** Real-time collaborative spreadsheets within Google Workspace
Google Sheets provides real-time co-editing with live cursors, comments, and version history. It is the most widely adopted cloud spreadsheet, integrated with Google Drive and the broader Workspace ecosystem. Its strength is accessibility and zero setup; the trade-off is that data resides on Google's infrastructure.

### Microsoft Excel Online
**Type:** Browser-based Excel with co-authoring
Excel Online provides the familiar Excel experience in the browser, with real-time co-authoring, comments, and track changes. It is the natural choice for organizations standardized on Microsoft 365, with seamless transition to desktop Excel for advanced features.

### Airtable
**Type:** Relational database with spreadsheet interface
Airtable combines a spreadsheet-like grid with relational database capabilities, views (Kanban, calendar, gallery), and automations. It is positioned for teams wanting structured data collection beyond simple spreadsheets, with a free tier for small teams and paid plans scaling by records and features.

### Smartsheet
**Type:** Spreadsheet-based work management with automation
Smartsheet provides a spreadsheet-like interface with automated workflows, Gantt views, and reporting. It is positioned for operations teams already comfortable with grids who want to layer automation on top.

### Coda
**Type:** Doc-based workspace with tables and automation
Coda combines documents, spreadsheets, and automation into a single canvas. Teams can build custom workflows and trackers within a doc-like interface, positioned for teams wanting more structured data capabilities than Notion provides.

---

## 🟩 Open-Source Software

Self-hosted, community-driven Online Collaborative Spreadsheet tools. The open-source ecosystem spans **full office suite integrations**, **Excel-flavored collaborative editors**, **data-scale spreadsheets**, and **Airtable-style database hybrids**.

### Nextcloud Spreadsheet
**Stack:** PHP / Nextcloud Office (Collabora/Euro-Office) | **License:** AGPL-3.0
Nextcloud Spreadsheet is a collaborative spreadsheet editor that runs on infrastructure you choose, positioned as a sovereign open-source alternative to Excel and Google Sheets [citation:4][citation:6]. Key features include:
- **Real-time co-editing** with named cursors showing who is working where
- **Full XLSX, XLS, and ODS compatibility**, so files round-trip cleanly with Excel and LibreOffice users
- **Thousands of functions and formulas**, sorting, filtering, macros, and charts
- **Granular access controls** (view, comment, edit) with public links and password-protected shares
- **Federated collaboration** allowing teams on separate Nextcloud instances to co-edit the same sheet
- **Desktop clients** for Linux, macOS, and Windows, plus mobile editing

As part of Nextcloud Office, it integrates with Nextcloud Files, Talk, and Groupware in a single self-hosted workspace [citation:4].
**Best for:** Organizations wanting a full, sovereign spreadsheet solution with strong Excel compatibility and integration into a broader self-hosted collaboration suite, accepting the Nextcloud deployment overhead.

### Casual Sheets
**Stack:** TypeScript / Univer OSS / Hocuspocus / Fastify / Redis | **License:** Apache-2.0
Casual Sheets is an **Excel-flavored web spreadsheet with real-time collaborative editing**, built entirely on Univer OSS (never the closed Pro package) [citation:1][citation:8]. Key features include:
- **Full xlsx / ods / csv / tsv round-trip** with parsing in Web Workers so the main thread never blocks
- **Office-style ribbon** with Home, Insert, Formulas, Data, View, and Review tabs
- **Charts** (8 types with trendlines), **pivot tables**, **sparklines**, conditional formatting, and data validation
- **Real-time co-editing** with live cursors, live-typing ghost, presence avatars, and password-protected rooms
- **View-only enforcement** at the Univer engine layer (server-side), not just the UI
- **Single Docker image** with web, Hocuspocus, and Fastify in one container; Redis for persistence

Anonymous sessions require no accounts, with rooms addressed at `/r/<roomId>` [citation:8]. The project has 357+ Playwright e2e tests and is fully auditable under Apache-2.0 [citation:1].
**Best for:** Teams wanting a lightweight, self-hosted Excel-like collaborative editor with strong format compatibility and minimal infrastructure, accepting that it is a focused spreadsheet tool rather than a full office suite.

### Diwan Sheets
**Stack:** Go / TypeScript / CRDT (Yjs) | **License:** MIT OR Apache-2.0
Diwan is a **single-binary office suite** with Documents, Sheets, Slides, Whiteboards, and PDF signing, where sheets include formulas, formats, charts, and pivots . Key characteristics:
- **No account, no cloud, no external service required** — runs as a single Go binary with the frontend embedded
- **CRDT-based peer-to-peer collaboration** — sheets use LWW/tree CRDTs, with end-to-end-encrypted rooms where the key never reaches any server
- The server role is **content-blind peer discovery** only; it learns that peers share a room ID, never any content
- **One binary on one box is all two people need** for collaboration, with no relay or configuration

Sheets are one surface of a broader office suite, not a standalone product .
**Best for:** Privacy-focused teams wanting a self-contained office suite with peer-to-peer encrypted collaboration, accepting that sheets are one component of a broader binary rather than a dedicated spreadsheet platform.

### AlephGrid
**Stack:** Rust / DuckDB / React | **License:** Open Source
AlephGrid is an open-source spreadsheet designed for **data that doesn't fit in a spreadsheet** — it handles datasets far beyond typical row limits by leveraging DuckDB under the hood [citation:2]. Key features include:
- **Scales to millions of rows** with DuckDB as the compute engine
- **SQL support** (can be disabled via `--disable-sql` for security)
- **Team features** with authentication (`--auth accounts`), spaces, roles, and OpenID Connect SSO
- **Memory budget management** with disk spilling when limits are reached
- **Docker deployment** with a setup code for creating the admin account
- **MCP client support** for AI agent integration

It is positioned for teams whose data exceeds the practical limits of browser-based spreadsheets, not as a general-purpose Excel replacement [citation:2].
**Best for:** Data teams needing spreadsheet-like interaction over large datasets (millions of rows) without exporting to a database, accepting a Rust/DuckDB stack and a narrower feature set than full Excel.

### Baserow
**Stack:** Python / Django / Vue.js / PostgreSQL | **License:** MIT (open-core)
Baserow is an open-source **spreadsheet-database hybrid** positioned as an Airtable alternative, trusted by over 150,000 users [citation:9]. Key features include:
- **Spreadsheet-like interface** with grid, Kanban, calendar, and gallery views
- **Application and portal building** with publishing to your own domain
- **Automations** for repetitive workflows and **dashboards** for visualization
- **AI Assistant (Kuma)** for building databases and workflows with natural language
- **GDPR, HIPAA, and SOC 2 Type II compliant**
- **Self-hosted with no storage restrictions**; Docker deployment with a single command

The open-core model keeps non-premium features under MIT, allowing commercial and private use [citation:9].
**Best for:** Teams wanting an Airtable-style database-spreadsheet hybrid with strong compliance certifications and a mature self-hosted deployment, accepting that it is database-first rather than a pure spreadsheet.

### NocoDB
**Stack:** Node.js / Vue.js / SQL databases | **License:** Open Source
NocoDB turns **any existing SQL database** (MySQL, PostgreSQL, SQL Server, SQLite) into a smart spreadsheet interface, positioned as the leading open-source Airtable alternative [citation:7][citation:11]. Key characteristics:
- **Connects to your own database** — data stays in your infrastructure, with no vendor lock-in
- **Auto-generates REST and GraphQL APIs** with Swagger documentation
- **Views**: grid, Kanban, calendar, gallery, and form
- **Virtual columns** (Lookup, Rollup, Formula) that exist only in the NocoDB layer without polluting the raw schema
- **Webhooks and automation** for event-driven workflows
- **Scales to millions of rows** because it relies on the underlying database's power

It is safe for non-technical users by limiting the operations they can perform on the database [citation:7].
**Best for:** Teams with existing SQL databases wanting a safe, user-friendly spreadsheet interface over their data without migrating it, accepting that it is a database UI rather than a standalone spreadsheet.

### Rowflare
**Stack:** (Check repository) | **License:** Open Source
Rowflare is an open-source **Airtable alternative** listed on the TrueNAS Apps Market, providing grid, timeline, and gallery views with automations [citation:3]. It is positioned for teams wanting a self-hosted Airtable-style interface, with documented self-hosting instructions. **Note:** Search results are limited; verify current feature coverage and maintenance status before adoption.
**Best for:** Teams wanting a self-hosted Airtable alternative with multiple view types and automations, with careful evaluation of maturity.

### SoloSheet
**Stack:** Python / Qt (PySide6) | **License:** GPL-3.0-or-later
SoloSheet is a **local, private, offline-only spreadsheet** built on the open `.sheet` JSON format, explicitly positioned as "as Markdown is to Word, SoloSheet is to Excel" [citation:14]. Key characteristics:
- **100% offline with zero telemetry** — there is no code in it that opens a socket
- **Wiki-linked sheets** — every `.sheet` file is a single spreadsheet, linkable to others inside formulas (e.g., `=[[sales]]!B4`)
- **Open JSON format** readable in any text editor, with no XML or lock-in
- **Lean by design** — fewer features than Excel, but simple, fast, and portable
- **CSV import and export** for data movement

It is a desktop application rather than a web-based collaborative platform [citation:14].
**Best for:** Individuals wanting a private, offline spreadsheet that stays out of the cloud entirely, accepting that it is not a collaborative tool.

---

## 📊 Comparison at a Glance

| Software | License | Stack | Real-Time Co-Edit | XLSX Support | Self-Hosted | Best For |
|----------|---------|-------|-------------------|--------------|-------------|----------|
| **Google Sheets** | Proprietary | Cloud | ✅ | ✅ | ❌ | Universal cloud spreadsheets |
| **Excel Online** | Proprietary | Cloud | ✅ | ✅ Native | ❌ | Microsoft 365 estates |
| **Airtable** | Proprietary | Cloud | (Check) | (Import) | ❌ | Database-spreadsheet hybrid |
| **Nextcloud Spreadsheet** | AGPL-3.0 | PHP/Nextcloud | ✅ | ✅ | ✅ | Sovereign full spreadsheet |
| **Casual Sheets** | Apache-2.0 | TypeScript/Univer | ✅ | ✅ | ✅ | Lightweight Excel-like editor |
| **Diwan Sheets** | MIT/Apache | Go/CRDT | ✅ P2P | (Check) | ✅ | Private office suite |
| **AlephGrid** | Open Source | Rust/DuckDB | (Check) | ❌ | ✅ | Millions of rows |
| **Baserow** | MIT (core) | Django/Postgres | (Check) | (Import) | ✅ | Airtable + compliance |
| **NocoDB** | Open Source | Node.js/SQL | (Check) | ❌ | ✅ | SQL database UI |
| **SoloSheet** | GPL-3.0 | Python/Qt | ❌ | ❌ | ✅ (Local) | Offline private sheets |

---

## 🤝 Contributing

Contributions are welcome! If you know of an open-source Online Collaborative Spreadsheet tool that should be listed here, please open a pull request with:

- Project name and URL
- Brief description (1–2 sentences)
- Stack and license
- Why it stands out

Please ensure the project is actively maintained (releases within the last 12 months) and genuinely open-source.

**Note on the open-source ecosystem:** The collaborative spreadsheet space splits between **full Excel-compatible editors** (Nextcloud Spreadsheet for sovereign office suites, Casual Sheets for lightweight Excel-flavored co-editing), **data-scale spreadsheets** (AlephGrid for millions of rows via DuckDB), **Airtable-style database hybrids** (Baserow, NocoDB, Rowflare), and **offline-only tools** (SoloSheet). **Nextcloud Spreadsheet** is the strongest choice for organizations wanting a complete, sovereign replacement for Google Sheets with full XLSX/ODS compatibility and integration into a broader collaboration suite [citation:4]. **Casual Sheets** offers a remarkably feature-dense Excel-like experience (charts, pivots, sparklines, view-only enforcement) in a single Apache-2.0 Docker image [citation:8]. For data that exceeds spreadsheet limits, **AlephGrid** with DuckDB is the purpose-built option [citation:2]. No open-source project fully replicates Google Sheets' zero-friction collaboration at global scale, but Nextcloud and Casual Sheets cover the core collaborative spreadsheet workflow for self-hosted deployments.

---

## 📄 License

This list is released under CC0 1.0 Universal (Public Domain). The software projects listed retain their respective licenses.

---

⭐ **If this list helped you discover a useful tool, please star the repo!** ⭐
