---
nextwork_uuid: fba05b27-d209-4ec1-91d6-7e8d162319f2
original_filename: legendary-fba05b27-d209-4ec1-91d6-7e8d162319f2.md
migrated_to: agentic-systems-engineering/multi-agent-sales-research.md
migrated_at: 2026-05-04
schema: nextwork-generator
---

<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a Multi-Agent Sales Research Tool

**Project Link:** [View Project](https://learn.nextwork.org/projects/fba05b27-d209-4ec1-91d6-7e8d162319f2)

**Author:** Roy Piring Jr  
**Email:** rpiringhawaii@gmail.com

---

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/fba05b27-d209-4ec1-91d6-7e8d162319f2_7vgvadsx)

## Building PineappleExpressAI's Prospect Research Engine

### The mission: replace 45 hours of sales research with one command

This project builds a multi-agent research system designed to generate AI-Readiness Briefs for SMB prospects in under 15 minutes.

The system replaces manual research workflows with coordinated subagents that gather, analyze, and synthesize market data into a structured output. The objective is to move from fragmented research to a repeatable pipeline that produces consistent, high-quality prospect intelligence artifacts.

### Tools and concepts mastered

The system uses Claude Code with slash commands and subagent contracts, combined with Pandoc and MiKTeX for PDF rendering, Mermaid for architecture diagrams, and Langfuse for observability.

Core concepts include multi-agent orchestration, coordinator-based execution patterns, structured output contracts, scoring-based quality gates, and the distinction between runtime observability and output correctness.

### Project timeline

This project took approximately 1 hour and 30 minutes. The main challenge was debugging headless execution, particularly handling timeouts, permission issues, and tool-level failures during automated runs.

The project demonstrates that orchestration complexity increases quickly when multiple agents and external tools are combined into a single pipeline.

## Setting Up the Automation Toolkit

### Why this step matters

The toolkit establishes the execution layer for the pipeline.

Pandoc and MiKTeX enable Markdown-to-PDF conversion, Mermaid CLI renders architecture diagrams, and Langfuse provides trace-level observability across agent execution. These tools ensure that outputs are not only generated but also traceable and production-ready.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/fba05b27-d209-4ec1-91d6-7e8d162319f2_ghfhkb4j)

### MiKTeX's role in the PDF pipeline

MiKTeX provides the LaTeX engine required for PDF generation.

Pandoc converts Markdown into LaTeX, and MiKTeX compiles it into a final PDF. Without this layer, the system would not be able to produce formatted, distributable documents.

## Scaffolding the Project with AI Assistance

### Prompting Claude Code to build the project structure

The system is scaffolded using Claude Code to establish structure and workflow.

The project includes directories for agents, commands, templates, and scratchpads, along with a CLAUDE.md memory file. Permissions are configured, and Austin market data is loaded to support research workflows.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/fba05b27-d209-4ec1-91d6-7e8d162319f2_dwvqp2mn)

### The quality gate: three scoring criteria

Quality is enforced through a scoring rubric.

Each generated brief is evaluated for specificity, accuracy, and actionability. A minimum score threshold ensures that outputs are usable before being delivered, preventing low-quality artifacts from reaching prospects.

## Designing Subagent Contracts in Claude Desktop

### Authoring three parallel research agents

Three subagents are defined with explicit responsibilities.

The Industry Researcher analyzes market context, the Competitor Scanner identifies competitive positioning, and the Pitch Drafter synthesizes findings into a sales narrative. Each agent operates under a structured contract that defines inputs, outputs, and behavior.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/fba05b27-d209-4ec1-91d6-7e8d162319f2_sencbnqj)

### Fallback logic for prospects with thin web presence

The system accounts for incomplete data scenarios.

When prospect-specific data is unavailable, the pipeline pivots to vertical-level analysis and explicitly documents gaps. These gaps are reframed as opportunities, ensuring the output remains actionable without fabricating information.

## Building the /dossier Coordinator Command

### Orchestrating three subagents with one slash command

The coordinator command orchestrates the full pipeline.

It manages execution flow, triggers subagents, merges outputs, and initiates PDF generation. This central command enables the entire research process to run from a single input.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/fba05b27-d209-4ec1-91d6-7e8d162319f2_6vh95gal)

### The six-step coordinator workflow

The workflow follows a structured execution sequence.

Scratchpad data is cleared, subagents are executed in parallel, outputs are merged into a final brief, and the result is rendered into a PDF. Additional outputs, such as LinkedIn posts, are generated alongside the main artifact.

## Validating Across Two Austin Verticals

### Real estate and healthcare: proving cross-vertical capability

The system is validated across multiple industries.

Generating briefs for both real estate and healthcare demonstrates that the pipeline can adapt to different market contexts while maintaining consistent structure and quality.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/fba05b27-d209-4ec1-91d6-7e8d162319f2_rmej2iot)

### Quality gate scores after improvements

The scoring rubric was not executed end-to-end.

Only partial scoring exists from the Pitch Drafter stage, indicating that a full validation pass remains a required next step for production readiness.

### How the healthcare brief differs from real estate

Differences in output reflect data quality and market context.

Healthcare outputs include confirmed entities and richer datasets, while real estate outputs rely more on inferred patterns. This highlights how data availability impacts output precision and positioning.

## Tracing Multi-Agent Execution with Langfuse

### Capturing observability data for the pipeline

Langfuse provides trace-level visibility into how the system executes.

Each run captures timing, dependencies, and execution flow across agents. This allows inspection of where time is spent, how agents interact, and whether orchestration behaves as expected under real conditions.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/fba05b27-d209-4ec1-91d6-7e8d162319f2_e60k9gy9)

### What the trace reveals about coordinator-subagent interaction

The trace confirms the execution model.

The coordinator acts as an orchestrator without performing reasoning itself, while subagents handle all computation. Parallel execution is visible during the first phase, where research agents run concurrently, reducing total runtime. Sequential dependency appears in the second phase, where the Pitch Drafter only starts after upstream tasks complete, confirming that precondition gates are enforced.

## Mapping the Architecture with C4 Diagrams

### Visualizing the multi-agent system

Architecture is documented using C4 diagrams to represent both system boundaries and internal components.

The diagrams provide a structured way to explain how the system interacts externally and how internal components coordinate to produce outputs.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/fba05b27-d209-4ec1-91d6-7e8d162319f2_iukumdup)

### Context vs. Container: two levels of architectural detail

The context diagram represents the system as a single unit interacting with external entities such as users, public web sources, and observability systems.

The container diagram exposes internal structure, showing the coordinator, subagents, data stores, and processing tools. This distinction separates high-level understanding from implementation detail and ensures the architecture is understandable to both technical and non-technical audiences.

## Polishing the Brief into a Sales-Ready Visual

### From Markdown to branded 1-page brief in Claude Design

The final output is transformed into a polished artifact.

Claude Design converts raw Markdown into a branded visual brief suitable for external distribution. This step shifts the output from a technical document to a client-facing deliverable.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/fba05b27-d209-4ec1-91d6-7e8d162319f2_7vgvadsx)

### Why visual polish closes deals that PDFs can't

Presentation directly impacts perceived value.

A plain PDF communicates information, while a branded artifact communicates quality and intent. Visual design reinforces credibility, which influences how prospects evaluate the offering before engaging with the content itself.

## Scale Testing Across Three Austin Verticals

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/fba05b27-d209-4ec1-91d6-7e8d162319f2_i9kct6u5)

### Identifying the bottleneck and optimizing the pipeline

Performance analysis identifies the main constraint.

The Competitor Scanner is the slowest component due to multiple sequential data fetches. Parallelizing internal operations within this agent reduces execution time and improves overall pipeline efficiency.

---

*Built with [NextWork](https://learn.nextwork.org) - [View this project](https://learn.nextwork.org/projects/fba05b27-d209-4ec1-91d6-7e8d162319f2)*
