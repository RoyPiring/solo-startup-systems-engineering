# Orchestrate AI Agents to Ship Full-Stack

> Inside the [Solo Startup Systems Engineering](../../README.md) portfolio · *Systems for building and scaling a startup as a solo operator.*

## Overview

The thesis: one Principal Engineer + AI Agent Teams = a full squad's output

In this project, I orchestrated three parallel AI agent teams using Claude Code Agent Teams to deliver a production-style lead generation platform within a compressed delivery window. The solution combined a streaming AI chat assistant, scheduling integration, serverless persistence, geo-targeted marketing pages, and automated deployment workflows into a single operating system.

The objective was not simply shipping a website. The goal was to practice architecture-first decomposition, parallel execution, and AI-assisted delivery patterns where a single engineer coordinates specialist agents to produce outputs normally requiring multiple engineering roles. The final system demonstrated AI orchestration, edge deployment, CI/CD automation, and customer acquisition workflows operating together as one platform.

The architecture is built across **9 phases**, anchored by **Orchestrating AI Agent Teams to Ship at 10x Velocity** on the input side and **RAG-Grounded Knowledge Base with pgvector** at the end. Each phase is listed in the Implementation section below.

## Architecture

```mermaid
---
title: Orchestrate AI Agents to Ship Full-Stack
---
%%{init: {"theme":"base","themeVariables": {"primaryColor":"#1B4332","primaryTextColor":"#F4D03F","primaryBorderColor":"#F4D03F","secondaryColor":"#264653","tertiaryColor":"#2F5233","lineColor":"#F4D03F","fontFamily":"ui-monospace, SFMono-Regular, Menlo, Consolas, monospace","fontSize":"13px"}}}%%
flowchart LR
    classDef datastore fill:#264653,stroke:#F4D03F,stroke-width:2px,color:#FFFFFF
    classDef service fill:#1B4332,stroke:#F4D03F,stroke-width:2px,color:#F4D03F
    classDef event fill:#7B42BC,stroke:#F4D03F,stroke-width:2px,color:#FFFFFF
    classDef io fill:#0d1117,stroke:#F4D03F,stroke-width:1.5px,color:#F4D03F,font-style:italic

    Principal[/"Principal Engineer (operator)"/]

    subgraph Toolchain["Local Toolchain"]
        Node("Node.js + pnpm")
        Git("Git + GitHub")
        ShadcnUI("shadcn/ui warm-editorial")
    end

    subgraph AgentTeams["Claude Code Agent Teams (3 parallel)"]
        AgentA("Team A: Pages + SEO")
        AgentB("Team B: AI Chat + Lead Capture")
        AgentC("Team C: Infra + CI/CD")
    end

    subgraph PreArtifacts["Architecture-First Artifacts"]
        ADR001[(ADR 001: Cloudflare over Vercel)]
        ArchDiagrams[(Architecture Diagrams)]
        DBSchema[(Neon Schema: leads, sessions, rag_chunks)]
        APIContracts[(API Contracts)]
        PhasedPlans[(Phased Plans + Reusable Prompts)]
    end

    subgraph EdgeRuntime["Cloudflare Workers Edge"]
        OpenNext("OpenNext adapter")
        NodeCompat{{"nodejs_compat flag"}}
        WorkerExec("Worker execution")
    end

    subgraph NextApp["Next.js Application"]
        HomePage("Home: hero + lead capture")
        Services("Services pages")
        About("About page")
        Booking("Booking page")
        AustinPage("Austin geo-targeted landing")
    end

    subgraph SEO["Local SEO Layer"]
        SchemaOrg[(Schema.org LocalBusiness JSON-LD)]
        AreaServed("areaServed: Austin + Texas")
        Canonical("Canonical URL /austin")
    end

    subgraph ChatLayer["Streaming AI Chat"]
        ChatSheet("ChatSheet UI + floating launcher")
        SSEEndpoint("SSE streaming endpoint")
        AnthropicAPI("Anthropic Claude API")
    end

    subgraph AntiAbuse["Anti-Abuse Cost Gate"]
        TurnstileBrowser("Turnstile browser challenge")
        TurnstileVerify{{"Turnstile server verify"}}
        Reject403{{"HTTP 403 reject"}}
    end

    subgraph LeadPipeline["Lead Capture Pipeline"]
        LeadForm("Lead form (Home + Austin)")
        LeadAPI("API: validate + persist")
        Neon[(Neon Postgres)]
        LeadsTable[(leads table)]
        SessionsTable[(chat_sessions table)]
    end

    subgraph Scheduling["Scheduling Integration"]
        CalCom("Cal.com booking widget")
        GoogleCal("Google Calendar sync")
    end

    subgraph CICD["GitHub Actions CI/CD"]
        Lint("Lint")
        TypeCheck("Type check")
        BuildGate("Build validation")
        PushMain{{"Push to main"}}
        Deploy("Deploy to Workers")
    end

    subgraph Production["Production Edge"]
        LiveURL[/"apex-ai-advisory.rpiringhawaii.workers.dev"/]
    end

    subgraph SecretMission["Secret Mission: pgvector RAG"]
        RAGChunks[(rag_chunks table + pgvector)]
        Embed("Embedding pipeline")
        Retrieve("Vector retrieval")
        Grounded("Grounded responses with source attribution")
    end

    Principal --> AgentTeams
    Principal --> Toolchain
    AgentTeams --> ADR001
    AgentTeams --> ArchDiagrams
    AgentTeams --> DBSchema
    AgentTeams --> APIContracts
    AgentTeams --> PhasedPlans

    AgentA --> NextApp
    AgentA --> SEO
    AgentB --> ChatLayer
    AgentB --> LeadPipeline
    AgentC --> EdgeRuntime
    AgentC --> CICD

    OpenNext --> WorkerExec
    NodeCompat -.enables.-> WorkerExec
    NextApp --> OpenNext
    AustinPage --> SchemaOrg
    SchemaOrg --> AreaServed
    SchemaOrg --> Canonical

    ChatSheet --> SSEEndpoint
    SSEEndpoint -.first message.-> TurnstileBrowser
    TurnstileBrowser --> TurnstileVerify
    TurnstileVerify -.fail.-> Reject403
    TurnstileVerify -.pass.-> AnthropicAPI

    LeadForm --> TurnstileBrowser
    TurnstileVerify -.pass.-> LeadAPI
    LeadAPI --> Neon
    Neon --> LeadsTable
    Neon --> SessionsTable

    Booking --> CalCom
    CalCom --> GoogleCal

    PushMain --> Lint
    Lint --> TypeCheck
    TypeCheck --> BuildGate
    BuildGate --> Deploy
    Deploy --> LiveURL
    WorkerExec --> LiveURL

    Neon --> RAGChunks
    RAGChunks --> Embed
    Embed --> Retrieve
    Retrieve --> AnthropicAPI
    Retrieve --> Grounded

    class Node,Git,ShadcnUI,OpenNext,WorkerExec,HomePage,Services,About,Booking,AustinPage service
    class ChatSheet,SSEEndpoint,AnthropicAPI,LeadForm,LeadAPI,CalCom,GoogleCal,Lint,TypeCheck,BuildGate,Deploy service
    class AgentA,AgentB,AgentC,AreaServed,Canonical,TurnstileBrowser,Embed,Retrieve,Grounded service
    class ADR001,ArchDiagrams,DBSchema,APIContracts,PhasedPlans,SchemaOrg,Neon,LeadsTable,SessionsTable,RAGChunks datastore
    class NodeCompat,TurnstileVerify,Reject403,PushMain event
    class Principal,LiveURL io
```

The diagram shows the topology and data flow of the system as built. The full architectural narrative, with screenshots and prose, lives in [`documents/agent-orchestrated-advisory-platform.md`](./documents/agent-orchestrated-advisory-platform.md).

## Implementation

This system is built across **9 phases**:

1. **Orchestrating AI Agent Teams to Ship at 10x Velocity**
2. **Setting Up the Infrastructure Foundation**
3. **Architecture-First Decomposition with Parallel Agents**
4. **Scaffolding Next.js on Cloudflare Workers**
5. **Building Core Pages and Geo-Targeted Landing**
6. **Streaming AI Chat Agent with Anti-Abuse Guardrails**
7. **Lead Capture Pipeline Writing to Neon Postgres**
8. **Deploying to Production and Establishing CI**
9. **RAG-Grounded Knowledge Base with pgvector**

For the full walkthrough with screenshots and step-by-step content, see [`documents/agent-orchestrated-advisory-platform.md`](./documents/agent-orchestrated-advisory-platform.md).

## Validation

Build outcomes verified end-to-end. Each phase below is captured with screenshots, configuration, and observable behavior in [`documents/agent-orchestrated-advisory-platform.md`](./documents/agent-orchestrated-advisory-platform.md):

- ✅ Orchestrating AI Agent Teams to Ship at 10x Velocity
- ✅ Setting Up the Infrastructure Foundation
- ✅ Architecture-First Decomposition with Parallel Agents
- ✅ Scaffolding Next.js on Cloudflare Workers
- ✅ Building Core Pages and Geo-Targeted Landing
- ✅ Streaming AI Chat Agent with Anti-Abuse Guardrails
- ✅ Lead Capture Pipeline Writing to Neon Postgres
- ✅ Deploying to Production and Establishing CI
- ✅ RAG-Grounded Knowledge Base with pgvector
