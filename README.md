# Solo Startup Systems Engineering

[![License: MIT](https://img.shields.io/badge/license-MIT-1B4332?style=flat-square&labelColor=0d1117)](./LICENSE) [![Systems](https://img.shields.io/badge/systems-6-2F5233?style=flat-square&labelColor=0d1117)](./INDEX.md) [![Updated](https://img.shields.io/badge/updated-2026--05--19-264653?style=flat-square&labelColor=0d1117)](./INDEX.md)

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

- **[Build a 28-Agent Advisory Firm](./systems/agent-advisory-firm/)**: 28 agents with advisory-only refusal, Presidio PII gate, and Postgres row-level tenancy
- **[Orchestrate AI Agents to Ship Full-Stack](./systems/agent-orchestrated-advisory-platform/)**: Cloudflare Workers + Neon pgvector RAG shipped by 3 parallel Claude Code agent teams
- **[Build a Brand Machine with Claude](./systems/claude-brand-machine/)**: Governed Claude skill studio with three QA agents shipping shirt, pitch deck, and Remotion MP4
- **[Build a Multi-Agent Sales Research Tool](./systems/multi-agent-sales-research/)**: Coordinator-fanout subagents producing a 15-minute AI-Readiness Brief with Langfuse traces
- **[Build an SMB Prospect Warehouse](./systems/smb-prospect-warehouse/)**: Schema-first warehouse with Pydantic contract, 55K-row universe, Great Expectations report

_+ 1 other system in the full catalog: [`INDEX.md`](./INDEX.md)._


