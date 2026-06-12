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

### [control](https://davidcockson.com) — self-hosted LLM platform

[![Live](https://img.shields.io/badge/case_study-davidcockson.com-blue?style=flat-square&logo=google-chrome&logoColor=white)](https://davidcockson.com)

> A private control surface for running LLM jobs against owned hardware, exposed safely to the public internet. Built solo in 10 days, spec → live.

*   **12 Docker services** across two hosts plus cloud, **100% IaC** (Terraform + Ansible, S3-backed state), **518 pytest tests** at cutover.
*   **Crash-safe filesystem job queue** — atomic `shutil.move` transitions (`_queue → _active → _completed`), no broker, no message loss; the worker re-queues stranded jobs on restart.
*   End-to-end **SSE streaming** from FastAPI through the worker to a TypeScript React UI; **hybrid RAG** over Qdrant vectors plus a hand-rolled Neo4j knowledge graph.
*   **Multi-machine Ollama routing** with explicit cloud fallback (Groq, Gemini, Anthropic) via FastMCP; **zero open inbound ports** (Cloudflare Tunnel + Tailscale, secrets resolved at runtime from Infisical); full OpenTelemetry → Grafana Cloud telemetry.

### [EvalUI](https://evalui.davidcockson.com) — dual-backend LLM observability

[![Live](https://img.shields.io/badge/live-evalui.davidcockson.com-blue?style=flat-square&logo=vercel&logoColor=white)](https://evalui.davidcockson.com)
[![Repo](https://img.shields.io/badge/repo-evalui-181717?style=flat-square&logo=github&logoColor=white)](https://github.com/davidcockson-compliance/evalui)

> Side-by-side LLM observability across Langfuse and Arize Phoenix from one OpenTelemetry source of truth. Built solo in a single day.

*   Next.js 16 dashboard on Vercel that fans a single OTel span stream out to both backends, normalises them into a shared four-stage blueprint, and races them side-by-side.
*   Independent **Claude Haiku 4.5 judge** scoring Gemini 2.5 Flash on DeepEval Faithfulness, Contextual Precision, Answer Relevancy, and Hallucination.
*   ISR + tag-based cache invalidation to stay inside Hobby-tier limits; a `<canvas>` latency replay driven by real span timings.

### [ears-specs](https://github.com/davidcockson-compliance/EARS-SPECS) — VS Code extension

[![VS Marketplace](https://img.shields.io/badge/VS%20Marketplace-v0.2.2-007ACC?logo=visualstudiocode&logoColor=white)](https://marketplace.visualstudio.com/items?itemName=davidcockson.ears-specs)
[![Open VSX](https://img.shields.io/open-vsx/v/davidcockson/ears-specs?label=Open%20VSX&color=a60ee5)](https://open-vsx.org/extension/davidcockson/ears-specs)

> A small editor extension for writing requirements in EARS — the *Easy Approach to Requirements Syntax*, a convention that keeps each requirement to one of five plain-English templates so it stays clear and testable. EARS is a common format for spec-driven development, including writing the specs that brief LLMs and AI coding tools.

Available on the [VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=davidcockson.ears-specs) and [Open VSX](https://open-vsx.org/extension/davidcockson/ears-specs) (so it also installs in Cursor and VSCodium). It works on any `.ears.md` file and:

*   Colours the EARS keywords, `<placeholders>`, and `[DRAFT]`/`[STABLE]` markers as you write.
*   Sorts each requirement into its EARS type — Ubiquitous, State-Driven, Event-Driven, Option-Driven, Unwanted — in a sidebar list, worked out from the opening keyword.
*   Adds a command to re-organise a spec into tidy per-type sections, a scaffolder for new spec files, and Tab-completion snippets for each template.

### double-diamond — VS Code extension

[![VS Marketplace](https://img.shields.io/badge/VS%20Marketplace-v0.2.0-007ACC?logo=visualstudiocode&logoColor=white)](https://marketplace.visualstudio.com/items?itemName=davidcockson.double-diamond)

> Brings the four-phase Double Diamond design process into the editor — an idea state machine, a Kanban webview, and Obsidian library export — so discovery and definition happen where the work does. Published to the VS Code Marketplace.

### Terminalz — terminal multiplexer for the AI-agent era

> Desktop multiplexer for running multiple coding agents at once (Tauri 2 / Rust, xterm.js v6, portable-pty, TypeScript).

*   Cover-flow layout that keeps every session live, so you can fan out work across several agents and glance between them.
*   Process-type detection via `/proc` colour-codes Claude Code, Gemini CLI, and SSH panes at a glance. Built EARS-spec-first with dedicated QA passes.

### [MapIt + MappitHills](https://davidcockson.com) — geospatial rendering

[![Case study](https://img.shields.io/badge/case_study-davidcockson.com-blue?style=flat-square&logo=google-chrome&logoColor=white)](https://davidcockson.com)

> Two geospatial tools, each built in a day.

*   **MapIt** — Python CLI + web app rendering OpenStreetMap data (Overpass API) as animated SVG/HTML across four aesthetic modes, including laser/G-code output; Overpass caching/retry, SSE progress streaming, result caching, Docker, 105 tests.
*   **MappitHills** — GPX walking-route renderer over real 3D terrain (MapLibre-GL + Mapzen Terrarium tiles), gradient-coloured by ascent rate with a vertical-exaggeration slider; Flask backend, Docker.

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
