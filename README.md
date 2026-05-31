<div align="center">
  <h1>Hi, I'm David Cockson 👋</h1>
  <h3>Infrastructure · Observability · AI Workflows</h3>
  <p><em>regulation → system → constraint → control → automation</em></p>
  
  <p>
    I build self-hosted infrastructure, monitoring stacks, and AI tooling from my homelab.<br/> 
    Most of what I ship is open source.
  </p>

  <p>📍 Macclesfield, UK</p>

  <!-- Social / Link Badges -->
  <a href="https://davidcockson.com"><img src="https://img.shields.io/badge/Portfolio-davidcockson.com-blue?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Website"/></a>
  <a href="https://blog.davidcockson.com"><img src="https://img.shields.io/badge/Blog-Read_My_Writing-FF5722?style=for-the-badge&logo=hashnode&logoColor=white" alt="Blog"/></a>
  <a href="https://linkedin.com/in/davidcockson"><img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
  <a href="mailto:hello@davidcockson.com"><img src="https://img.shields.io/badge/Email-hello@davidcockson.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/></a>
</div>

<br/>

<div align="center">
  <!-- Tech Stack Badges -->
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
  <img src="https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white" alt="Terraform" />
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker" />
  <img src="https://img.shields.io/badge/Proxmox-E57000?style=flat-square&logo=proxmox&logoColor=white" alt="Proxmox" />
  <img src="https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white" alt="Prometheus" />
  <img src="https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white" alt="Grafana" />
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI" />
</div>

---

## 🔭 Current Focus

*   **Distributed AI Systems** — Multi-provider LLM routing, Model Context Protocol (MCP), and multi-agent graph pipelines.
*   **Self-Hosted Infrastructure** — High-availability virtualization on Proxmox (Ubuntu VMs), container orchestration via Docker, and secure networking.
*   **Full-Stack Observability** — Telemetry pipelines spanning infrastructure, runtimes, and LLMs using Prometheus, Grafana, Loki, Tempo, OpenTelemetry, and Langfuse.
*   **Infrastructure as Code (IaC)** — Declarative systems provisioning and configuration management via Terraform, Ansible, and automated CI/CD engine loops.

---

## 🛠️ Selected Projects

### [ears-specs](https://github.com/davidcockson-compliance/EARS-SPECS) — VS Code extension

[![VS Marketplace](https://img.shields.io/visual-studio-marketplace/v/davidcockson.ears-specs?label=VS%20Marketplace&logo=visualstudiocode&color=007ACC)](https://marketplace.visualstudio.com/items?itemName=davidcockson.ears-specs)
[![Open VSX](https://img.shields.io/open-vsx/v/davidcockson/ears-specs?label=Open%20VSX&color=a60ee5)](https://open-vsx.org/extension/davidcockson/ears-specs)

> A small editor extension for writing requirements in EARS — the *Easy Approach to Requirements Syntax*, a convention that keeps each requirement to one of five plain-English templates so it stays clear and testable. EARS is a common format for spec-driven development, including writing the specs that brief LLMs and AI coding tools.

Available on the [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=davidcockson.ears-specs) and [Open VSX](https://open-vsx.org/extension/davidcockson/ears-specs) (so it also installs in Cursor and VSCodium). It works on any `.ears.md` file and:

*   Colours the EARS keywords, `<placeholders>`, and `[DRAFT]`/`[STABLE]` markers as you write.
*   Sorts each requirement into its EARS type — Ubiquitous, State-Driven, Event-Driven, Option-Driven, Unwanted — in a sidebar list, worked out from the opening keyword.
*   Adds a command to re-organise a spec into tidy per-type sections, a scaffolder for new spec files, and Tab-completion snippets for each template.

### [vault-runner](https://github.com/davidcockson-compliance/vault-runner)
> Self-hosted LLM job runner that turns an Obsidian vault into a distributed, deterministic AI workbench.

*   **File-Driven Pipeline:** Decentralized task queue (`_queue` → `_active` → `_completed`) managed entirely through markdown files.
*   **Unified Engine Matrix:** Multi-provider routing layer orchestrating local Ollama nodes alongside Groq, Gemini, Anthropic, and HuggingFace endpoints via a single configuration table.
*   **Knowledge Synthesis:** Complex research execution powered by LangGraph — features parallel web scraping, entity extraction into a KuzuDB graph database, and automated report compilation.
*   **Self-Healing Workflows:** Closed-loop GitLab CI code-generation engine that catches execution context, streams tracebacks back to the LLM, fixes failures, and automatically re-tests.
*   **State & Memory:** Contextual execution memory using a MemPalace MCP server to surface past run data with a single declarative YAML flag.
*   **Dual-Layer Telemetry:** System metrics and runtime traces routed to OpenTelemetry/Tempo/Grafana, paired with deep LLM call, token, and cost analysis via Langfuse. Automated alert routing via Discord.
*   **Reactive UI:** Lightweight administrative interface built with FastAPI, HTMX, and Server-Sent Events (SSE) for live-streaming job states.
*   **Quality Gates:** 87 automated unit/integration tests managed via parallelized GitLab CI and GitHub Actions pipelines with automated deployment on green merge.

### [sable-ai-governance-framework](https://github.com/davidcockson-compliance/sable-ai-governance-framework)
> Operational risk and structural compliance architecture mapping AI system constraints to automated software guardrails.

*   Translates high-level organizational policy directives, regulatory compliance rules, and algorithmic data requirements into auditable code controls.
*   Codifies risk-mitigation vectors directly into target deployment configurations and LLM orchestration schemas.

### [homelab-monitoring](https://github.com/davidcockson-compliance/homelab-monitoring)
> Declarative Prometheus and Grafana stack engineered for multi-node bare metal and virtualized infrastructure visibility.

*   Aggregates system metrics, OS logs, and runtime traces across the homelab infrastructure cluster.
*   Implements deep per-container resource tracking, performance profiling, and error anomaly detection using standard Docker metrics exporters.

### [infra-practice](https://github.com/davidcockson-compliance/infra-practice)
> A modular blueprint repo showcasing cloud infrastructure patterns, secure network topography, and automated software delivery.

*   Implements immutable infrastructure practices utilizing highly reusable, modular Terraform modules.
*   Provisions structured cloud environments alongside automated, repeatable Python deployment pipelines and security baselines.

### [pickles-gmbh-ai-governance-framework](https://github.com/davidcockson-compliance/pickles-gmbh-ai-governance-framework)
> Enterprise-scoped AI governance framework designed to enforce security constraints, policy alignment, and compliance tracking in automated system workflows.

---

## ✍️ Recent Writing

*   [My First Alert Fired and It Was Not a Test](https://blog.davidcockson.com) — *18 Apr 2026*
*   [Git - Green, Blue and Purple?](https://blog.davidcockson.com) — *18 Apr 2026*
*   [Linguistic Fluidity: Why reading Cyberpunk Makes Me Better at AI](https://blog.davidcockson.com) — *2 Apr 2026*

*More articles at [blog.davidcockson.com](https://blog.davidcockson.com) →*

---

## ⚙️ How I Approach Systems

```mermaid
flowchart LR
    A[Observe system] --> B[Find constraint]
    B --> C[Map the gap]
    C --> D[Design control]
    D --> E[Automate solution]
    E --> F[Monitor outcome]
    F --> A
