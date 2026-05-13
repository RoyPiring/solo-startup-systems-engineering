<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a 28-Agent Advisory Firm

**Project Link:** [View Project](https://learn.nextwork.org/projects/9eb2f051-69ce-4d97-b255-0e4487a895e7)

**Author:** Roy Piring Jr  
**Email:** rpiringhawaii@gmail.com

---

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/9eb2f051-69ce-4d97-b255-0e4487a895e7_f7jt8la3)

## The Vision: Building a 28-Agent Advisory Firm

### Project goals and advisory-only scope

In this project, I built a 28-agent advisory platform designed to automate operational workflows while preserving strict advisory-only boundaries. The objective was to reduce repetitive execution work and create an AI-assisted consulting system focused on assessment, analysis, and strategic recommendations rather than implementation delivery.

The platform combines multi-agent orchestration, retrieval-augmented generation, compliance-aware retrieval, Google Workspace integration, PostgreSQL tenancy controls, and governance enforcement into a single operational environment. Instead of operating as disconnected prompts, the agents function as coordinated advisory specialists operating under a centralized constitutional framework.

## Launching the Streamlit Dashboard and Full Infrastructure

### Council scoring, dashboard, and scheduler

I built a Streamlit operations dashboard with KPI monitoring, Plotly visualizations, Mermaid architecture diagrams, and scheduled infrastructure automation through APScheduler.

The dashboard acts as the operational control plane for the advisory system. It centralizes agent health, scoring outcomes, workflow visibility, and governance status into a single interface so the organization can be monitored as a coordinated platform rather than separate automations.

The infrastructure layer also included a Makefile-driven bootstrap process so the full environment could be initialized consistently from a single command.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/9eb2f051-69ce-4d97-b255-0e4487a895e7_i8zkpcj0)

### Council veto authority in action

The Council scoring system evaluates deliverables across four weighted quality dimensions while preserving absolute veto authority over scope violations.

If implementation language such as “deploy,” “build,” or “configure” appears in a deliverable, the veto logic immediately rejects the artifact before quality scoring executes.

This matters because the platform is intentionally designed as an advisory business rather than a managed-services provider. Governance discipline takes priority over output quality if the deliverable violates the firm’s operating model.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/9eb2f051-69ce-4d97-b255-0e4487a895e7_f7jt8la3)

## Smoke Testing Across 5 Regulated Verticals

### Two-harness validation protocol

I created a synthetic validation suite spanning five regulated business verticals and executed a two-harness verification workflow using ChatGPT Codex.

The smoke tests validated orchestration consistency, scoring behavior, retrieval quality, and governance enforcement across healthcare, trades, real estate, and advisory-focused use cases.

This transformed the environment from a static architecture exercise into a continuously validated operational system.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/9eb2f051-69ce-4d97-b255-0e4487a895e7_thapnas4)

### Deliberate veto path verification

One vertical intentionally triggered a governance veto by including implementation language inside the generated artifact.

The purpose was to prove the refusal system still functions under live execution conditions rather than assuming the control path works theoretically.

This established both positive-path and negative-path testing inside the advisory platform, ensuring governance controls cannot silently degrade over time.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/9eb2f051-69ce-4d97-b255-0e4487a895e7_yiusvtbz)

## Scaffolding 28 Agents with Advisory-Only Refusal Rules

### 9 teams, 28 named agents

I designed the platform around 28 named agents distributed across nine functional teams using Pydantic-based persona models and YAML-defined behavioral contracts.

Each team operates within a defined advisory specialty while sharing centralized governance logic, retrieval rules, and refusal behavior. FastAPI endpoints exposed orchestration access while Presidio handled PII detection and protection workflows.

The architecture behaves more like a governed consulting organization than a chatbot system.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/9eb2f051-69ce-4d97-b255-0e4487a895e7_8ggljihe)

### Protecting advisory pricing power

The refusal layer prevents agents from drifting into implementation work by scanning requests for operational execution language.

If implementation intent is detected, the request is rejected and redirected toward implementation partners instead of being fulfilled directly.

This protects the business model by anchoring value around judgment, governance, and strategic analysis instead of labor-based delivery work.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/9eb2f051-69ce-4d97-b255-0e4487a895e7_vy8vs7dn)

## Enabling Google Workspace APIs and Service Account Access

### Foundation and API setup

I configured Google Workspace APIs, service-account delegation, and automated synchronization services to support advisory operations across Drive, Calendar, Docs, and Gmail.

The environment also integrated rclone to support bidirectional file synchronization between local systems and cloud storage.

This established the operational backbone for document workflows, scheduling coordination, and communication ingestion.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/9eb2f051-69ce-4d97-b255-0e4487a895e7_a9jenhox)

### Service account and domain-wide delegation scopes

The service account was configured with domain-wide delegation scopes for Drive, Calendar, Docs, and Gmail read-only access.

This allows the advisory system to securely operate across Workspace resources while preserving centralized governance controls.

The important design principle was controlled impersonation. The agents inherit only the permissions required to perform advisory workflows instead of unrestricted administrative access.

## Structuring the Obsidian Vault and PostgreSQL Data Layer

### Single source-of-truth vault design

I structured the platform around an Obsidian vault, PostgreSQL schema, and Chroma vector database acting together as the system’s persistent knowledge layer.

The Obsidian vault stores operational frameworks and reusable advisory knowledge, PostgreSQL handles structured business data, and Chroma manages semantic retrieval for agent context injection.

This creates a layered memory architecture where retrieval remains separated from transactional state management.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/9eb2f051-69ce-4d97-b255-0e4487a895e7_n98bf0e9)

### Advisory positioning contract enforcement

The advisory-positioning contract defines what the firm is allowed to do and what it must refuse.

Every agent retrieves this contract through RAG and uses it as the authoritative behavioral boundary for geography, pricing model, vertical scope, and refusal logic.

Changing the contract updates organizational behavior globally without requiring individual prompt edits across all 28 agents.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/9eb2f051-69ce-4d97-b255-0e4487a895e7_yzrkxu3g)

## Wiring RAG and Chroma for Compliance-Aware Retrieval

### Vault ingestion pipeline with vertical metadata

I built a retrieval pipeline that chunks markdown documents, detects industry verticals, and indexes content into Chroma using metadata-aware ingestion.

The retrieval layer combines semantic search with vertical filtering and keyword fallback logic to improve retrieval accuracy for compliance-sensitive advisory work.

A watchdog process continuously monitors the vault and automatically re-ingests modified templates without restarting the application.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/9eb2f051-69ce-4d97-b255-0e4487a895e7_i42kf3a6)

### Keyword fallback for compliance terminology

The keyword fallback layer exists because embeddings can miss exact compliance references such as statute codes, license identifiers, and regulatory acronyms.

If semantic similarity retrieval produces weak matches, the system performs deterministic regex scanning against raw vault files to recover exact-token references that embeddings may undervalue.

This matters because advisory credibility depends on citation precision. Approximate compliance answers are unacceptable in regulated environments.

## Connecting the Google Workspace Sync Bridge

### Drive sync, Gmail intake, and PII gating

I integrated Google Drive synchronization, Gmail triage routing, Calendar scheduling, and Docs export workflows into the advisory platform.

Incoming communications are classified through a Smart Router workflow while exports move through PII scanning before any external transmission occurs.

This creates a governed operational bridge between advisory workflows and cloud collaboration systems.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/9eb2f051-69ce-4d97-b255-0e4487a895e7_xgrtdi1p)

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/9eb2f051-69ce-4d97-b255-0e4487a895e7_75izqxdc)

### HIPAA-compliant Docs export protection

Before any document export occurs, the system runs a PII validation layer using presidio-analyzer.

If protected entities such as names, SSNs, medical identifiers, or dates exceed threshold confidence levels, the export is blocked before data leaves the local environment.

The important architectural principle is containment. Sensitive information is intercepted at the firm boundary instead of after cloud transmission has already occurred.

## Secret Mission: Multi-Tenant Enterprise Extension

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/9eb2f051-69ce-4d97-b255-0e4487a895e7_li9l0t75)

### RLS, Ollama, Hugo, and telemetry extensions

RLS, Ollama, Hugo, and telemetry extensions

I extended the platform with PostgreSQL row-level security, tenant-scoped dashboards, local Ollama routing, and telemetry-aware operational workflows.

Each tenant operates within isolated query boundaries enforced through PostgreSQL RLS policies and tenant-specific role scoping.

The Streamlit dashboard was updated to replace mock KPIs with live tenant-scoped metrics and visualizations, creating a realistic multi-tenant advisory environment.

## Reflections: Tools, Concepts, and Time Investment

### Key tools and concepts mastered

This project combined Streamlit, PostgreSQL, Chroma, FastAPI, Presidio, Google Workspace APIs, rclone, APScheduler, Ollama, and multi-agent orchestration into a governed advisory platform.

The concepts reinforced throughout the build included AI governance, RAG architecture, compliance-aware retrieval, row-level security, advisory-only business controls, tenant isolation, workflow automation, and operational orchestration.

### Time to completion

This project took approximately 90 minutes to complete. The most difficult part was balancing orchestration flexibility against governance enforcement without weakening the advisory-only operating model.

The platform introduced real-world operational considerations around retrieval quality, compliance enforcement, multi-tenant isolation, and behavioral consistency across all 28 agents.

The biggest takeaway was understanding how AI agents can operate as a governed advisory organization instead of isolated assistants.

The next area I want to improve is enterprise-scale orchestration across distributed AI teams operating over longer-running advisory engagements with persistent memory and lifecycle governance.

---

*Built with [NextWork](https://learn.nextwork.org) - [View this project](https://learn.nextwork.org/projects/9eb2f051-69ce-4d97-b255-0e4487a895e7)*
