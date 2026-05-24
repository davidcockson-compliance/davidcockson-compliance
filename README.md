# David Cockson
**Infrastructure · Observability · AI Workflows**
regulation → system → constraint → control → automation
I build self-hosted infrastructure, monitoring stacks, and AI tooling from my homelab. Most of what I ship is open source.
📍 Macclesfield, UK
🔗 davidcockson.com · blog · linkedin · hello@davidcockson.com
## Current Focus
 * distributed AI systems — multi-provider LLM routing, Model Context Protocol (MCP), and multi-agent graph pipelines
 * self-hosted infrastructure — high-availability virtualization on Proxmox (Ubuntu VMs), container orchestration via Docker, and secure networking
 * full-stack observability — telemetry pipelines spanning infrastructure, runtimes, and LLMs using Prometheus, Grafana, Loki, Tempo, OpenTelemetry, and Langfuse
 * infrastructure as code (IaC) — declarative systems provisioning and configuration management via Terraform, Ansible, and automated CI/CD engine loops
## Selected Projects
### vault-runner
Self-hosted LLM job runner that turns an Obsidian vault into a distributed, deterministic AI workbench.
 * **File-Driven Pipeline:** Decentralized task queue (_queue → _active → _completed) managed entirely through markdown files.
 * **Unified Engine Matrix:** Multi-provider routing layer orchestrating local Ollama nodes alongside Groq, Gemini, Anthropic, and HuggingFace endpoints via a single configuration table.
 * **Knowledge Synthesis:** Complex research execution powered by LangGraph — features parallel web scraping, entity extraction into a KuzuDB graph database, and automated report compilation.
 * **Self-Healing Workflows:** Closed-loop GitLab CI code-generation engine that catches execution context, streams tracebacks back to the LLM, fixes failures, and automatically re-tests.
 * **State & Memory:** Contextual execution memory using a MemPalace MCP server to surface past run data with a single declarative YAML flag.
 * **Dual-Layer Telemetry:** System metrics and runtime traces routed to OpenTelemetry/Tempo/Grafana, paired with deep LLM call, token, and cost analysis via Langfuse. Automated alert routing via Discord.
 * **Reactive UI:** Lightweight administrative interface built with FastAPI, HTMX, and Server-Sent Events (SSE) for live-streaming job states.
 * **Quality Gates:** 87 automated unit/integration tests managed via parallelized GitLab CI and GitHub Actions pipelines with automated deployment on green merge.
→ davidcockson-compliance/vault-runner
### sable-ai-governance-framework
Operational risk and structural compliance architecture mapping AI system constraints to automated software guardrails.
 * Translates high-level organizational policy directives, regulatory compliance rules, and algorithmic data requirements into auditable code controls.
 * Codifies risk-mitigation vectors directly into target deployment configurations and LLM orchestration schemas.
→ davidcockson-compliance/sable-ai-governance-framework
### homelab-monitoring
Declarative Prometheus and Grafana stack engineered for multi-node bare metal and virtualized infrastructure visibility.
 * Aggregates system metrics, OS logs, and runtime traces across the homelab infrastructure cluster.
 * Implements deep per-container resource tracking, performance profiling, and error anomaly detection using standard Docker metrics exporters.
→ davidcockson-compliance/homelab-monitoring
### infra-practice
A modular blueprint repo showcasing cloud infrastructure patterns, secure network topography, and automated software delivery.
 * Implements immutable infrastructure practices utilizing highly reusable, modular Terraform modules.
 * Provisions structured cloud environments alongside automated, repeatable Python deployment pipelines and security baselines.
→ davidcockson-compliance/infra-practice
### pickles-gmbh-ai-governance-framework
Enterprise-scoped AI governance framework designed to enforce security constraints, policy alignment, and compliance tracking in automated system workflows.
→ davidcockson-compliance/pickles-gmbh-ai-governance-framework
## Recent Writing
 * My First Alert Fired and It Was Not a Test — 18 Apr 2026
 * Git - Green, Blue and Purple? — 18 Apr 2026
 * Linguistic Fluidity: Why reading Cyberpunk Makes Me Better at AI — 2 Apr 2026
More articles at blog.davidcockson.com →
## How I Approach Systems
```mermaid
flowchart LR
A[Observe system] --> B[Find constraint]
B --> C[Map the gap]
C --> D[Design control]
D --> E[Automate solution]
E --> F[Monitor outcome]
F --> A
