# Solo Startup Systems Engineering

[![License: MIT](https://img.shields.io/badge/license-MIT-1B4332?style=flat-square&labelColor=0d1117)](./LICENSE) [![Systems](https://img.shields.io/badge/systems-5-2F5233?style=flat-square&labelColor=0d1117)](./INDEX.md) [![Updated](https://img.shields.io/badge/updated-2026--05--18-264653?style=flat-square&labelColor=0d1117)](./INDEX.md)

> *What does a solo operator build to launch and scale a startup?*

Systems for building and scaling a startup as a solo operator. Each system in this domain ships with a Mermaid architecture diagram, a numbered implementation map, and a checkmark list of build outcomes verified end-to-end. The original source document is kept per system.

## Who this is for

| Reader | What to look at | Time |
|--------|----------------|------|
| Recruiter | This README, badges | 10 sec |
| Hiring Manager | Systems list below, per-system Validation | 2 min |
| Engineer | Per-system Architecture + Implementation | 15 min |
| Learner | Per-system end-to-end source content | 30 min |

## What this domain covers

Reference architectures for building and scaling a startup as a solo operator. Each system documents what's needed now, what's deferred, and why, sized for one builder running zero-to-one and beyond.

**What it isn't.** A claim of having shipped a successful startup. A blueprint for VC-stage scaling.

## Featured Systems

- **[Build a 28-Agent Advisory Firm](./systems/agent-advisory-firm/)**: 28-agent advisory platform with governance veto, PII gate, and multi-tenant RLS isolation.
- **[Build a Brand Machine with Claude](./systems/claude-brand-machine/)**: BRAND.md source-of-truth feeds three Claude skills behind three named quality-gate agents.
- **[Build a Multi-Agent Sales Research Tool](./systems/multi-agent-sales-research/)**: Coordinator with parallel subagent fanout, scoring rubric, and Langfuse traces for prospect briefs.
- **[Build an SMB Prospect Warehouse](./systems/smb-prospect-warehouse/)**: Schema-first Pydantic contract drives a 55K-row DuckDB warehouse with Great Expectations gates.
- **[Ship a Startup Website with AI Agents](./systems/startup-site-ai-agents/)**: Parallel agents ship a Next.js site behind axe-core zero-violations and Playwright E2E gates to a live URL.



