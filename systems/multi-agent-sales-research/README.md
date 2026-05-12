# Build a Multi-Agent Sales Research Tool

> Inside the [Solo Startup Systems Engineering](../../README.md) portfolio · *Systems for building and scaling a startup as a solo operator.*

## Overview

This project builds a multi-agent research system designed to generate AI-Readiness Briefs for SMB prospects in under 15 minutes.

The system replaces manual research workflows with coordinated subagents that gather, analyze, and synthesize market data into a structured output. The objective is to move from fragmented research to a repeatable pipeline that produces consistent, high-quality prospect intelligence artifacts.

The architecture is built across **10 phases**, anchored by **Building PineappleExpressAI's Prospect Research Engine** on the input side and **Scale Testing Across Three Austin Verticals** at the end. Each phase is listed in the Implementation section below.

## Architecture

```mermaid
---
title: Build a Multi-Agent Sales Research Tool
---
%%{init: {"theme":"base","themeVariables": {"primaryColor":"#1B4332","primaryTextColor":"#F4D03F","primaryBorderColor":"#F4D03F","secondaryColor":"#264653","tertiaryColor":"#2F5233","lineColor":"#F4D03F","fontFamily":"ui-monospace, SFMono-Regular, Menlo, Consolas, monospace","fontSize":"13px"}}}%%
flowchart LR
    classDef datastore fill:#264653,stroke:#F4D03F,stroke-width:2px,color:#FFFFFF
    classDef service fill:#1B4332,stroke:#F4D03F,stroke-width:2px,color:#F4D03F
    classDef event fill:#7B42BC,stroke:#F4D03F,stroke-width:2px,color:#FFFFFF
    classDef io fill:#0d1117,stroke:#F4D03F,stroke-width:1.5px,color:#F4D03F,font-style:italic







    User[/Prospect Input/]
    AustinData[(Austin Market Data)]
    WebSrc[(Public Web Sources)]
    Brief[/AI-Readiness Brief PDF/]
    Linked[/LinkedIn Post/]

    subgraph Orchestration
        Slash{{"/dossier slash command"}}
        Coord(Coordinator)
        Scratch[(Scratchpad)]
    end

    subgraph Research_Agents_parallel["Research Agents - parallel fanout"]
        Industry(Industry Researcher)
        Competitor(Competitor Scanner)
    end

    subgraph Synthesis_Quality["Synthesis & Quality Gate"]
        Pitch(Pitch Drafter)
        Score{{Scoring Rubric specificity/accuracy/actionability}}
    end

    subgraph Output_Pipeline["Output Pipeline"]
        Pandoc(Pandoc)
        MikTex(MiKTeX LaTeX)
        Design(Claude Design)
    end

    Langfuse(Langfuse Tracing)

    User -->|invoke| Slash
    Slash -->|trigger| Coord
    Coord -->|clear & init| Scratch

    Coord -->|fanout phase 1| Industry
    Coord -->|fanout phase 1| Competitor
    Industry -->|market context| Scratch
    Competitor -->|competitive positioning| Scratch
    Industry -.->|fetch| WebSrc
    Competitor -.->|fetch| WebSrc
    Industry -.->|read vertical| AustinData
    Competitor -.->|read vertical| AustinData

    Scratch -->|gate: upstream complete| Pitch
    Pitch -->|draft narrative| Score
    Score -->|merge fanin| Coord

    Coord -->|render markdown| Pandoc
    Pandoc -->|LaTeX| MikTex
    MikTex -->|PDF| Brief
    Coord -->|polish| Design
    Design --> Brief
    Coord -->|side artifact| Linked

    Coord -.->|traces| Langfuse
    Industry -.->|traces| Langfuse
    Competitor -.->|traces| Langfuse
    Pitch -.->|traces| Langfuse
class AustinData,WebSrc,Scratch datastore
class Slash,Score event

    class AustinData,WebSrc,Scratch datastore
    class Coord,Industry,Competitor,Pitch,Pandoc,MikTex,Design,Langfuse service
    class Slash,Score event
    class User,Brief,Linked io
```

The diagram shows the topology and data flow of the system as built. The full architectural narrative, with screenshots and prose, lives in [`documents/multi-agent-sales-research.md`](./documents/multi-agent-sales-research.md).

## Implementation

This system is built across **10 phases**:

1. **Building PineappleExpressAI's Prospect Research Engine**
2. **Setting Up the Automation Toolkit**
3. **Scaffolding the Project with AI Assistance**
4. **Designing Subagent Contracts in Claude Desktop**
5. **Building the /dossier Coordinator Command**
6. **Validating Across Two Austin Verticals**
7. **Tracing Multi-Agent Execution with Langfuse**
8. **Mapping the Architecture with C4 Diagrams**
9. **Polishing the Brief into a Sales-Ready Visual**
10. **Scale Testing Across Three Austin Verticals**

For the full walkthrough with screenshots and step-by-step content, see [`documents/multi-agent-sales-research.md`](./documents/multi-agent-sales-research.md).

## Validation

Build outcomes verified end-to-end. Each phase below is captured with screenshots, configuration, and observable behavior in [`documents/multi-agent-sales-research.md`](./documents/multi-agent-sales-research.md):

- ✅ Building PineappleExpressAI's Prospect Research Engine
- ✅ Setting Up the Automation Toolkit
- ✅ Scaffolding the Project with AI Assistance
- ✅ Designing Subagent Contracts in Claude Desktop
- ✅ Building the /dossier Coordinator Command
- ✅ Validating Across Two Austin Verticals
- ✅ Tracing Multi-Agent Execution with Langfuse
- ✅ Mapping the Architecture with C4 Diagrams
- ✅ Polishing the Brief into a Sales-Ready Visual
- ✅ Scale Testing Across Three Austin Verticals
