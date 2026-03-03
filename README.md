# David Cockson

**Systems thinker. Finding constraints. Designing control.**

```
regulation → system → constraint → control → automation
```

https://www.linkedin.com/in/david-cockson

![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat&logo=amazonaws&logoColor=white)
![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020?style=flat&logo=cloudflare&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=flat&logo=githubactions&logoColor=white)
![Obsidian](https://img.shields.io/badge/Obsidian-7C3AED?style=flat&logo=obsidian&logoColor=white)

---

## Background

For the last **8 years I’ve worked inside complex regulatory systems**, primarily in the gambling industry.

My work involved:

- identifying structural weaknesses in regulatory frameworks  
- investigating systemic failures across organisations and regulators  
- designing operational controls to stabilise complex systems  

In practice this meant constantly asking:

> **Where is the constraint?  
> What breaks first?  
> What control stabilises the system?**

That mindset translates naturally into **software infrastructure and automation**.

---

## Current Focus

I’m now applying the same systems thinking to **software, infrastructure, and AI workflows**.

Areas I’m actively building in:

- cloud infrastructure and containerisation  
- monitoring and observability systems  
- automation and operational tooling  
- AI governance frameworks and multi-agent workflows  

Most projects are built through a combination of **homelab experimentation and cloud deployments**.

---

## Selected Projects

**Scarlet Helix**  
Monitoring and analysis tool for the UK Gambling Commission licence register.

**AI Governance Frameworks**  
Explorations into how AI systems can generate and maintain governance documentation.

**Homelab Monitoring Stack**  
Self-hosted infrastructure used to experiment with containers, monitoring, and deployment pipelines.

---

## How I Approach Systems

```mermaid
flowchart LR

A[Observe System]:::start --> B[Identify Constraint]
B --> C[Map the Gap]
C --> D[Design Control]
D --> E[Automate Solution]
E --> F[Monitor System]
F --> A

classDef start fill:#1f2937,stroke:#38bdf8,color:#ffffff;
classDef process fill:#111827,stroke:#6ee7b7,color:#ffffff;

class B,C,D,E,F process;
```

This loop applies whether the system is:

- regulatory frameworks  
- operational processes  
- infrastructure platforms  
- AI workflows  

Understand the system.  
Remove the constraint.  
Let automation keep it stable.

---

## Current Learning

- Linux systems and tooling  
- Docker and container infrastructure  
- cloud deployment patterns  
- observability and monitoring  
- AI governance and agent workflows  

---

*Tao of Pratchett.*

**Map the gap. Architect the control.**
[Repository](https://github.com/davidcockson-compliance/pickles-gmbh-ai-governance-framework) · [Documentation site](https://davidcockson-compliance.github.io/pickles-gmbh-ai-governance-framework/)

---
 ### [sable-ai-governance-framework](https://github.com/davidcockson-compliance/sable-ai-governance-framework)

  The same multi-agent engine, different jurisdiction and risk surface.

  Sable AI Ltd is a fictional UK HR startup building Scout — an AI CV screening and shortlisting tool. The framework applies UK
  GDPR, DPA 2018, the Data (Use and Access) Act 2025, and Equality Act 2010 to a bias-critical use case where automated processing
  has direct consequences for candidate employment rights. 18 documents across five stages plus worked examples; the Phase 2
  section covers Scout end-to-end.

  **Stack:** Claude Code · Multi-agent architecture · Markdown · MkDocs · GitHub Pages
  **Licence:** CC BY 4.0

  [Repository](https://github.com/davidcockson-compliance/sable-ai-governance-framework) · [Documentation
  site](https://davidcockson-compliance.github.io/sable-ai-governance-framework/)

  ---
### [homelab-monitoring](https://github.com/davidcockson-compliance/homelab-monitoring)

Prometheus + Grafana monitoring stack for a home server. Host metrics via node_exporter, per-container visibility via Telegraf and the Docker socket API, orchestrated with Docker Compose. Air-gapped from the public internet — Tailscale only.

**Stack:** Prometheus · Grafana · Telegraf · node_exporter · Docker Compose

---

## 🗺️ How We Got Here
```mermaid
timeline
    title The Technical Evolution
        2025 : Logic & Scripts
             : Manual Compliance Audit Logic
             : Python for Data Analysis
             : Linux Mint Daily Driver
    Jan 2026 : Building & Virtualization
             : Built "ProDesk" Home Lab
             : Proxmox & Docker Deployment
    Feb 2026 : AI Governance & Agents
             : Multi-agent Claude Code system
             : EU AI Act framework — 22 documents
             : MkDocs static site deployment
    Mar 2026 : UK AI Governance
             : Sable AI — 18 documents
             : UK GDPR, Equality Act 2010
             : Bias-critical HR AI context
     Current : Cloud & Resilience
             : Scarlet Helix on Cloudflare
             : Exploring DNS Engineering
             : Deep dive into AWS & IaC
             : Observability (Prometheus, Grafana, Telegraf)
```
