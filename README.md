# 🌐 VulnScanner — Vulnerability Scanner for Red Teamers
_A professional-grade recon, enumeration, and CVE detection engine._

<p align="center">
  <img src="https://img.shields.io/badge/Status-Active-success?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Language-TypeScript-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Framework-Next.js-black?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Database-Prisma-purple?style=for-the-badge" />
</p>

# 🚀 VulnScanner

### **AI-Powered Offensive & Defensive Vulnerability Scanning Platform**

⚠️ *Core source code is private. This public README documents the architecture, capabilities & design of the system for professional review.*

---

## ⭐ Overview

**VulnScanner** is a high-performance, AI-augmented vulnerability scanning suite engineered for **red teams, SOC teams, penetration testers, DevSecOps, and MSSPs**.
It combines ultra-fast active scanning, passive enumeration, credentialed probing, automated reporting, and AI-driven exploitation path generation — all wrapped in a real-time, modern dashboard.

This README showcases the system’s full capability, architecture, design philosophy, and engineering approach.

---

# 📚 Table of Contents

* [Features](#-feature-suite)
* [AI Augmentation](#-ai-powered-enhancements)
* [Architecture](#-architecture-overview)
* [Core Algorithms](#-core-algorithms)
* [Dashboard Features](#-dashboard--management)
* [Plugin Ecosystem](#-plugin-ecosystem)
* [Security](#-security--sandboxing)
* [Development Roadmap](#-development-roadmap)
* [Tech Stack](#-tech-stack)
* [Project Structure](#-project-structure)
* [Disclaimer](#-disclaimer)

---

# 🔥 Feature Suite

## 1. ⚡ **High-Performance Scanning Engine**

### **TCP & UDP Scanner**

* Rust microservice for ultra-high throughput
* Async architecture (Tokio runtime)
* Stealth scan mode for low-noise reconnaissance
* Optional extended Nmap compatibility

### **Subdomain Discovery**

* Wordlist brute-force
* DNS permutations & transformations
* ASN/CIDR mapping
* Wildcard DNS detection
* False-positive reduction layer

### **HTTP & Security Analyzer**

* CSP, HSTS, XSS, XFO detection
* Outdated server stack fingerprinting
* Misconfig detection
* Framework identification

### **CMS & Stack Fingerprinting**

* WordPress, Joomla, Drupal enumeration
* Plugin/theme detection & version extraction
* Known-vulnerable asset matching
* Framework detection: Laravel, Django, Angular, React, Express, Spring Boot

### **Real-Time CVE Intelligence**

* Live NVD sync
* CVSS v3.1 + CWE mapping
* Exploitability scoring
* Severity-based prioritization

---

# 🧠 AI-Powered Enhancements

## 🤖 1. **AI Attack Path Generator**

Automatically maps discovered vulnerabilities into exploitation chains:

```
Weak SSH Key → User Shell → Sudo Misconfig → Container Escape → Host Compromise
```

## 🛠 2. **AI Fix Advisor**

For each issue VulnScanner generates:

* Human-readable explanation
* Step-by-step remediation
* Terraform or Ansible patch
* Business impact summary

## 📄 3. **AI Log Summaries**

Transforms raw logs & packets into descriptive narratives for easier reporting.

---

# 🏗 Architecture Overview

```
                                   ┌──────────────────────────┐
                                   │    Web Dashboard (Next)   │
                                   └──────────────┬───────────┘
                                                  │
                                  Real-Time SSE / WebSockets
                                                  │
                         ┌─────────────────────────▼────────────────────────┐
                         │                 API Gateway (Node/TS)            │
                         └───────┬──────────────────────────────────────────┘
                                 │
                        Auth / RBAC / Vault Secrets
                                 │
                 ┌──────────────▼───────────────────────────┐
                 │      Job Queue (BullMQ + Redis)           │
                 └───────┬───────────────────────────────────┘
                         │
              ┌──────────▼────────────────────────────────────────┐
              │   Scanning Engine Cluster                          │
              │  - Rust Port Scanner                               │
              │  - Python CMS Analyzer                             │
              │  - HTTP Security Scanner                           │
              │  - Passive Recon Modules                           │
              │  - Credentialed Agents (SSH/SMB/HTTP)              │
              └──────────┬────────────────────────────────────────┘
                         │
                 ┌───────▼───────────────────┐
                 │   Sandbox Layer            │
                 │ (Docker / Firecracker VMs) │
                 └───────┬────────────────────┘
                         │
             ┌───────────▼──────────────┐
             │ Database Layer            │
             │ PostgreSQL / Redis Cache  │
             └───────────────────────────┘
```
# 🔬 Core Algorithms

## ⚡ 1. **Async TCP Scan Algorithm**

```
- Pre-generate SYN packets
- Dispatch in async batches (512–2048)
- Track RTT
- Infer open/closed/filtered
- Adaptive timeout for noisy networks
```

## 🔍 2. DNS Permutation Algorithm

```
- Apply permutations: hyphens, TLD swaps, prefixes
- Resolve in parallel
- Apply wildcard detector
- Drop noise using ASN/CIDR mapping
- Rank by validity score
```

## 📊 3. Risk Scoring Model

```
Risk = CVSS × Exploitability × Exposure × Asset Value
```

## 🧠 4. AI Attack Path Builder

```
- Build a graph: Services → Issues → Priv Esc → Lateral Moves
- Weight nodes based on likelihood
- Output highest-probability exploitation chain
```

---

# 📊 Dashboard & Management

### **1. Real-Time Scan Viewer**

* Progress bars
* Live logs
* Module-level status

### **2. Risk Heatmaps**

* Host-based
* Severity-weighted
* Department / Business-unit view

### **3. Scheduled Scans**

* Daily/Weekly/Monthly
* Compare results over time
* Attack surface analysis

### **4. Scan Diffs**

* "New vulnerabilities since last scan"
* "Resolved vulnerabilities"

---

# 🧩 Plugin Ecosystem

### **Supported Plugin Types**

* TypeScript
* Python
* Docker-isolated

### **Plugin Features**

* Hot-reload
* Safe sandboxing
* Custom findings, scanners, or rules
* Ideal for enterprise MSSPs

---

# 🛡 Security & Sandboxing

* Firecracker micro-VM isolation (optional)
* Container-level isolation for plugin execution
* Vault-secured SSH/SMB/HTTP credentials
* Strict audit logs for every action
* Multi-tenant workspace isolation

---

# 🛠 Development Roadmap

### **Phase 1 — Base Platform**

* Auth, RBAC, Dashboard, Project Structure
* Real-time logging system
* Job queue + worker system

### **Phase 2 — Active Scanners**

* TCP/UDP
* HTTP
* CMS
* Subdomain discovery

### **Phase 3 — AI Layer**

* Attack Path Engine
* AI Fix Advisor
* Narrative Generator

### **Phase 4 — Enterprise Features**

* Multi-tenancy
* RBAC
* Credentialed scanning
* Plugin ecosystem

### **Phase 5 — Integrations**

* Slack
* Teams
* Jira
* GitHub Security Alerts

---

# 🧰 Tech Stack

| Layer             | Technologies         |
| ----------------- | -------------------- |
| Frontend          | Next.js, Tailwind    |
| Backend API       | Node.js, TypeScript  |
| Workers           | BullMQ, Node         |
| High-Speed Engine | Rust                 |
| CMS/HTTP Modules  | Python               |
| Sandbox           | Docker / Firecracker |
| Database          | PostgreSQL           |
| Cache             | Redis                |
| Security          | Vault, JWT           |
| AI                | OpenAI / Local LLM   |

---

# 📁 Project Structure

```
vulnscanner/
│
├── api/                 # API Gateway
├── workers/             # Job workers
├── engines/             # Scanning engines
│   ├── rust/            # High-speed port scanner
│   ├── python/          # CMS/HTTP modules
│   └── dns/             # Subdomain engine
│
├── plugins/             # Plugin system
│
├── sandbox/             # Firecracker/Docker isolation layer
│
├── web/                 # Next.js frontend
│
└── docs/                # Documentation
```

---

# ⚠️ Disclaimer

This repository provides **documentation only**.
The **core scanning engine, AI models, exploitation systems, and backend source code are private** for security and intellectual property protection.

For demonstration, collaboration, or interviews:
📩 *Access can be granted privately upon request.*


