<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Orchestrate AI Agents to Ship Full-Stack

**Project Link:** [View Project](https://learn.nextwork.org/projects/ce3cc909-905f-45a8-a61b-4ed62890cda7)

**Author:** Roy Piring Jr  
**Email:** rpiringhawaii@gmail.com

---

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/ce3cc909-905f-45a8-a61b-4ed62890cda7_5p9pdss8)

## Orchestrating AI Agent Teams to Ship at 10x Velocity

### The thesis: one Principal Engineer + AI Agent Teams = a full squad's output

The thesis: one Principal Engineer + AI Agent Teams = a full squad's output

In this project, I orchestrated three parallel AI agent teams using Claude Code Agent Teams to deliver a production-style lead generation platform within a compressed delivery window. The solution combined a streaming AI chat assistant, scheduling integration, serverless persistence, geo-targeted marketing pages, and automated deployment workflows into a single operating system.

The objective was not simply shipping a website. The goal was to practice architecture-first decomposition, parallel execution, and AI-assisted delivery patterns where a single engineer coordinates specialist agents to produce outputs normally requiring multiple engineering roles. The final system demonstrated AI orchestration, edge deployment, CI/CD automation, and customer acquisition workflows operating together as one platform.

## Setting Up the Infrastructure Foundation

### Environment and account provisioning

The foundation phase focused on establishing every dependency required for application delivery and operations. Node.js, pnpm, and Git provided the local engineering toolchain while GitHub acted as the source-control and CI anchor.

Neon Postgres was provisioned to provide serverless persistence and vector capabilities. Cloudflare Turnstile introduced anti-abuse protection and Cal.com supplied scheduling automation through Google Calendar integration.

This stage intentionally completed all infrastructure dependencies before application development began. Removing platform blockers early allowed the later AI agents to focus exclusively on feature implementation rather than environment troubleshooting.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/ce3cc909-905f-45a8-a61b-4ed62890cda7_dobkstnb)

### Credentials collected and their roles

The environment depended on four core configuration objects.

NEON_DATABASE_URL provided server-side connectivity to the Neon database supporting lead persistence and future vector retrieval capabilities.

NEXT_PUBLIC_TURNSTILE_SITE_KEY rendered browser challenges while TURNSTILE_SECRET_KEY validated tokens server-side before accepting requests.

NEXT_PUBLIC_CAL_BOOKING_URL powered embedded booking experiences for the consultation workflow.

Separating browser and server secrets preserved least-privilege boundaries while maintaining portability between development and deployment environments.

## Architecture-First Decomposition with Parallel Agents

### Decomposing the system for parallel agent execution

Claude Code Agent Teams were enabled and three parallel teammates were assigned explicit ownership boundaries to prevent overlap and merge conflicts.

Before implementation, the agents generated architecture diagrams, ADRs, database schemas, API contracts, phased plans, and reusable prompts for future sessions.

This architecture-first workflow forced design decisions before coding began. It created shared context between agents and reduced rework because implementation followed pre-approved structures rather than evolving organically during development.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/ce3cc909-905f-45a8-a61b-4ed62890cda7_771gdw7q)

### ADR 001: Cloudflare over Vercel for a solo operator

The first architectural decision selected Cloudflare Workers through OpenNext rather than Vercel.

The decision optimized for operational simplicity and cost efficiency. Cloudflare consolidated DNS, CDN, WAF, Turnstile, and compute under one vendor instead of distributing responsibilities across multiple providers.

For an individual operator this removed recurring cost growth and reduced management overhead. Turnstile validation, Workers execution, and edge controls all lived inside the same operational boundary.

The result was one dashboard, one billing model, and fewer integration points to maintain long term.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/ce3cc909-905f-45a8-a61b-4ed62890cda7_89ku6o8b)

## Scaffolding Next.js on Cloudflare Workers

### Edge-native deployment setup

The application was scaffolded directly against the Cloudflare Workers adapter instead of following a traditional Node deployment path.

The setup included dependency installation, shadcn/ui initialization using the warm-editorial design language, root layout creation, and verification of the development runtime.

Building natively for Workers established edge compatibility from day one rather than introducing migration complexity later.

Local validation confirmed compatibility between Next.js, OpenNext, Worker execution, and downstream AI integrations before feature development began.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/ce3cc909-905f-45a8-a61b-4ed62890cda7_a1ouoiwx)

### Understanding the nodejs_compat flag

The nodejs_compat setting enabled Cloudflare's compatibility layer within workerd, exposing runtime capabilities such as node:crypto, node:buffer, node:stream, async_hooks, and process handling.

This compatibility layer was mandatory for the project because OpenNext relies on Node stream patterns for SSR, the Anthropic SDK depends on streams for SSE output, and Neon uses crypto functionality in secure connections.

Without it, the Worker immediately failed during execution with missing module errors.

Enabling compatibility preserved edge deployment while supporting frameworks that still assume Node behavior internally.

## Building Core Pages and Geo-Targeted Landing

### Full-stack page architecture

The application included Home, Services, About, Booking, and localized landing pages.

The Home page operated as the conversion entry point using a hero section, services presentation, and lead capture flow. Service pages introduced advisory offerings while Booking embedded scheduling experiences through Cal.com.

An Austin-specific landing page introduced geo-targeted acquisition and local search visibility.

The architecture intentionally separated informational content from conversion mechanics so future expansion could happen independently without restructuring the platform.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/ce3cc909-905f-45a8-a61b-4ed62890cda7_civut4bg)

### Schema.org LocalBusiness structured data for organic discovery

The Austin landing page implemented Schema.org LocalBusiness metadata.

This converted the page from generic content into a discoverable business entity by declaring service type, pricing signals, geography, and canonical ownership.

areaServed mapped Austin and Texas relationships while priceRange established commercial positioning.

The canonical URL anchored local authority directly to /austin, preventing the homepage from competing for regional queries.

This improved discoverability for searches tied to local AI advisory intent and strengthened organic positioning

## Streaming AI Chat Agent with Anti-Abuse Guardrails

### Building the AI-powered pre-qualification surface

The AI layer functioned as a lead qualification engine rather than a generic chatbot.

A streaming endpoint delivered Claude responses through SSE while ChatSheet handled conversation history, token rendering, and persistent access through a floating launcher.

The experience simulated advisory engagement by answering questions and qualifying prospects before human interaction occurred.

Streaming responses reduced perceived latency and created a near real-time interaction model suitable for customer acquisition workflows.

### Cloudflare Turnstile validation on the streaming endpoint

The first message in the workflow passed through Cloudflare Turnstile validation.

The browser generated an invisible challenge token and submitted it alongside the initial request. The endpoint forwarded the token to Cloudflare verification services before any Claude invocation occurred.

Failed validation returned HTTP 403 immediately.

Architecturally, abuse prevention occurred before model execution, preventing token waste and protecting inference cost exposure.

## Lead Capture Pipeline Writing to Neon Postgres

### End-to-end lead generation infrastructure

In this phase, I implemented the persistence layer supporting the lead generation workflow. The database schema in Neon Postgres included dedicated tables for leads, chat sessions, and future RAG knowledge chunks so the platform could support both customer acquisition and AI retrieval workloads from the same backend.

The lead capture workflow was integrated into both the Home and Austin landing pages to support general and geo-targeted acquisition paths. Cloudflare Turnstile protection was added before database submission to prevent abuse while preserving user experience.

The complete flow was validated end-to-end: visitor submission → Turnstile verification → API processing → Neon persistence → query validation. This ensured the acquisition pipeline functioned as a production-ready funnel rather than isolated UI components.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/ce3cc909-905f-45a8-a61b-4ed62890cda7_2lal8hm0)

### Spam prevention without friction

Cloudflare Turnstile was selected because it minimizes user friction while maintaining anti-abuse protection. Unlike traditional CAPTCHA systems, Turnstile performs browser validation and proof-of-work checks silently in the background, allowing legitimate users to submit forms without challenge interruptions.

Validation occurred server-side before any database activity. The application posted the client token to the Turnstile verification endpoint and only continued to the Neon INSERT operation after receiving a successful response. Invalid submissions immediately returned HTTP 403, preventing bots from creating records or consuming backend resources.

The token lifecycle followed a discard model. Tokens were verified once, never stored, never logged, and never associated with persisted lead records. Since Turnstile tokens are single-use, replay attacks were automatically prevented, reducing spam exposure while preserving privacy boundaries.

## Deploying to Production and Establishing CI

### Zero-cost production deployment on Cloudflare Workers

The final deployment phase moved the application from local development into a production edge environment using Cloudflare Workers. Environment variables for Neon, Anthropic APIs, Turnstile validation, and scheduling integrations were configured directly in the deployment environment to preserve separation between code and secrets.

GitHub Actions introduced automated quality gates consisting of linting, type checking, and build validation. Every push to main triggered verification before deployment, ensuring defective changes could not bypass pipeline controls.

Production validation confirmed all application paths operated successfully. Marketing routes returned expected metadata and structured data, AI chat streamed correctly through SSE endpoints, lead submissions persisted into Neon, Turnstile blocked invalid requests, and scheduling integrations rendered live availability.

The final result was a fully operational acquisition system running on a serverless edge architecture with

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/ce3cc909-905f-45a8-a61b-4ed62890cda7_4l4bfhwk)

### Live URL and end-to-end verification

GitHub Actions introduced automated quality gates through linting, type checking, and build validation before deployment.

The production environment was deployed through OpenNext onto Cloudflare Workers and published at:

Live URL: https://apex-ai-advisory.rpiringhawaii.workers.dev

Validation confirmed all five routes returned successful responses with correct metadata and JSON-LD structures.

The AI assistant streamed responses successfully, lead submissions persisted into Neon, Turnstile blocked invalid requests, and Cal.com rendered live availability.

The complete prospect journey worked end-to-end: visit → AI interaction → lead capture → booking conversion.

## Secret Mission: RAG-Grounded Knowledge Base with pgvector

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/ce3cc909-905f-45a8-a61b-4ed62890cda7_egatecgb)

### Why RAG beats static prompts for long-term system intelligence

RAG was introduced to decouple knowledge management from deployment cycles.

Static prompts scale linearly because every request resends the entire context. Retrieval sends only the most relevant records, maintaining stable inference cost while expanding knowledge size.

Operationally this meant updates could happen through knowledge ingestion workflows instead of deployments.

Accuracy also improved because answers became grounded in retrieved content rather than generic model memory.

The retrieval layer added traceability by exposing source attribution for every response.

## Reflections on Shipping a Production System in 2 Hours

### Key tools and concepts mastered

Key tools used during the project included Node.js, pnpm, Git, Cloudflare Workers, Neon Postgres, Cal.com, Turnstile, and Anthropic APIs.

The project reinforced practical concepts including AI agent orchestration, edge-native deployment, serverless architectures, RAG systems, CI/CD workflows, and architecture-first engineering delivery.

### Time to completion and biggest challenges

This project required approximately three hours to complete.

The largest challenge involved Windows compatibility behaviors during development and dependency execution. Several runtime assumptions expected Unix-style environments and required additional validation before stabilizing the deployment workflow.

Despite those challenges, the project validated that AI agents can operate as specialized teammates when architecture, ownership, and governance are defined clearly.

I completed this project to learn how architecture-first decomposition and AI agent orchestration can accelerate delivery of full-stack systems.

The next capability I want to strengthen is production CI/CD maturity for web platforms, particularly deployment automation, governance controls, and release workflows supporting AI-enabled applications.

---

*Built with [NextWork](https://learn.nextwork.org) - [View this project](https://learn.nextwork.org/projects/ce3cc909-905f-45a8-a61b-4ed62890cda7)*
