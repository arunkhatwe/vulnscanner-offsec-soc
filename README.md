# 🌐 VulnScanner — Modular Vulnerability Scanner for Red Teamers
_A professional-grade recon, enumeration, and CVE detection engine._

<p align="center">
  <img src="https://img.shields.io/badge/Status-Active-success?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Language-TypeScript-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Framework-Next.js-black?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Database-Prisma-purple?style=for-the-badge" />
</p>

---

## 🚀 About VulnScanner
**VulnScanner** helps security professionals identify vulnerabilities, perform modular scanning, leverage passive recon and credentialed checks, track risk scores, and take action with actionable reports and seamless integrations — all through a powerful, intuitive dashboard.

---

## ✨ Key Features

### 🔎 Active & Passive Recon
- Custom TCP port scanner
- Nmap support (optional)
- Subdomain brute-forcing
- HTTP header & security header analyzer
- CMS detection (WordPress, Joomla, Drupal)

### 🧠 CVE & Threat Intelligence
- Real-time CVE lookup via NVD API
- Risk scoring (CVSS + CWE mapping)
- Suggested remediation steps

### 🔐 Credentialed Scanning
- SSH checks
- Form-based HTTP login
- Secure credential storage (Vault-backed)

### 📡 Passive Recon Integrations
- Shodan
- Censys
- crt.sh
- Wayback Machine  

### 📊 Dashboard & Reporting
- Clean, modern Next.js dashboard
- Scan history timeline
- Trend graphs
- JSON, Markdown, and PDF report export
- Webhooks, Slack, Jira integration
- Scheduled scans

---

## 🧱 Tech Stack
| Layer | Tech |
|-------|------|
| Frontend | Next.js 14 (App Router), TailwindCSS, ShadCN UI |
| Backend  | Node.js, API routes, Prisma ORM |
| Database | PostgreSQL |
| Queue System | BullMQ + Redis |
| Auth | NextAuth |
| Reporting | Markdown → PDF generator |
| Integrations | NVD API, Shodan, Censys |

---

## yet to update
