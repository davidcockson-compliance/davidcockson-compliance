# David Cockson

**Infrastructure · Observability · AI Workflows**

`regulation → system → constraint → control → automation`

I build self-hosted infrastructure, monitoring stacks, and AI tooling
from my homelab. Most of what I ship is open source.

📍 Macclesfield, UK  
🔗 [davidcockson.com](https://davidcockson.com) · [blog](https://blog.davidcockson.com) · [linkedin](https://www.linkedin.com/in/david-cockson) · hello@davidcockson.com

![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)
![Proxmox](https://img.shields.io/badge/Proxmox-E57000?style=flat&logo=proxmox&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Terraform](https://img.shields.io/badge/Terraform-7B42BC?style=flat&logo=terraform&logoColor=white)
![Ansible](https://img.shields.io/badge/Ansible-EE0000?style=flat&logo=ansible&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=flat&logo=prometheus&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat&logo=grafana&logoColor=white)
![Loki](https://img.shields.io/badge/Loki-F5A800?style=flat&logo=grafana&logoColor=white)
![OpenTelemetry](https://img.shields.io/badge/OpenTelemetry-425CC7?style=flat&logo=opentelemetry&logoColor=white)
![Langfuse](https://img.shields.io/badge/Langfuse-0A0A0A?style=flat)
![Cloudflare](https://img.shields.io/badge/Cloudflare-F38020?style=flat&logo=cloudflare&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat&logo=amazonaws&logoColor=white)

---

## Current Focus

- distributed AI systems — multi-provider LLM routing, MCP, agent + research pipelines
- self-hosted infrastructure on Proxmox (Ubuntu VMs) + Docker
- observability (Prometheus, Grafana, Loki, Tempo, OpenTelemetry, Langfuse)
- infrastructure-as-code (Terraform, Ansible, CI/CD pipelines)
- *next-gen observability + agent platform — private homelab build* <!-- reword in your voice -->

---

## Selected Projects

### vault-runner

Self-hosted LLM job runner that turns an Obsidian vault into a distributed AI workbench.

- file-based job queue (`_queue → _active → _completed`) driven from markdown
- multi-provider routing — local Ollama + Groq / Gemini / Anthropic / HuggingFace from one config table
- LangGraph research pipeline — parallel web search → KuzuDB knowledge graph → synthesised report
- GitLab CI code-gen loop — generate → push → CI → LLM fix on failure → retry
- semantic memory via MemPalace MCP — past outputs retrieved with one YAML flag
- dual observability — OpenTelemetry → Tempo/Grafana + Langfuse LLM traces; Discord alerts on failure
- FastAPI + HTMX dashboard with live SSE output streaming
- 87 tests · GitLab CI + GitHub Actions · auto-deploy on merge

→ [davidcockson-compliance/vault-runner](https://github.com/davidcockson-compliance/vault-runner)

---

### scarlet-helix

Monitoring tool for the UK Gambling Commission licence register — domain
discovery, corporate group identification, compliance views.

→ [repo](https://github.com/davidcockson-compliance/scarlet-helix) · [live](https://scarlet-helix.davidcockson.com)

---

### lccp-regulation-filter

Converts the UK Gambling Commission's LCCP regulations into a structured
dataset with filtering and gap-analysis tooling.

→ [repo](https://github.com/davidcockson-compliance/lccp-regulation-filter) · [live](https://lccp-filter.davidcockson.com)

---

### homelab-monitoring

Prometheus + Grafana stack for a home server. Host metrics and
per-container visibility via Docker exporters.

→ [repo](https://github.com/davidcockson-compliance/homelab-monitoring)

---

### infra-practice

Terraform and Python automation practice — IaC patterns, CI/CD pipelines,
repeatable cloud deployments.

→ [repo](https://github.com/davidcockson-compliance/infra-practice)

---

### AI Governance Frameworks

Structured governance models for AI systems, generated and maintained with
AI-assisted workflows.

- [Sable AI Governance Framework](https://davidcockson-compliance.github.io/sable-ai-governance-framework/)
- [Pickles GmbH AI Governance Framework](https://davidcockson-compliance.github.io/pickles-gmbh-ai-governance-framework/)

---

## Recent writing

- [My First Alert Fired and It Was Not a Test](https://blog.davidcockson.com/posts/brute-force-attack/) — 18 Apr 2026
- [Git - Green, Blue and Purple?](https://blog.davidcockson.com/posts/git-green-blue-purple/) — 18 Apr 2026
- [Linguistic Fluidity: Why reading Cyberpunk Makes Me Better at AI](https://blog.davidcockson.com/posts/why-am-i-excellent-using-ai-/) — 2 Apr 2026

[More at blog.davidcockson.com →](https://blog.davidcockson.com)

---

## How I Approach Systems

```mermaid
flowchart LR
A[Observe system] --> B[Find constraint]
B --> C[Map the gap]
C --> D[Design control]
D --> E[Automate solution]
E --> F[Monitor outcome]
F --> A
