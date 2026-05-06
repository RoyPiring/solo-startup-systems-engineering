<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a Brand Machine with Claude

**Project Link:** [View Project](https://learn.nextwork.org/projects/f38e8012-3c4d-49db-8e56-0fcfdec31a5e)

**Author:** Roy Piring Jr  
**Email:** rpiringhawaii@gmail.com

---

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/f38e8012-3c4d-49db-8e56-0fcfdec31a5e_918eb5ph)

## The Mission: A Governed Creative Pipeline

### Project vision and goals

This project builds a Claude skill studio that generates brand-consistent artifacts through a governed, multi-agent pipeline.

The system transforms a static brand definition into a repeatable production process that outputs merch, pitch decks, and video assets. Instead of manually designing each artifact, the pipeline enforces consistency through a shared design system and automated quality gates. The goal is to move from ad hoc creative work to a controlled system where outputs are predictable, auditable, and aligned across all media.

## Designing the Pineapple AGI Brand System

### Building the single source of truth

The system is anchored by a centralized BRAND.md file that defines identity, color palette, typography, and visual construction rules.

This file acts as the only source of truth for all downstream generation. Every skill reads from it before producing output, ensuring that design decisions are not duplicated or reinterpreted across artifacts. The structure includes strict definitions for color usage, font hierarchy, and logo composition, allowing the system to enforce consistency without relying on external tools or manual review.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/f38e8012-3c4d-49db-8e56-0fcfdec31a5e_ola6cr1y)

### Why BRAND.md drives every artifact

The design system controls consistency, portability, and drift.

All generated outputs inherit their visual and textual properties directly from BRAND.md, eliminating variation across artifacts. Because the file exists within the repository, it travels with the system and removes dependency on external design tools. Updates propagate automatically, meaning a single change realigns all future outputs without requiring manual correction across prompts or files.

## Shipping the Brand Shirt Design

### Skill 1: print-ready brand merch

The shirt design skill generates a self-contained HTML artifact that translates brand rules into a visual composition.

The process reads brand definitions, generates multiple design concepts, and outputs a finalized graphic that adheres strictly to the defined palette, typography, and logo constraints. The result is a production-ready asset that can be rendered or printed without additional modification.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/f38e8012-3c4d-49db-8e56-0fcfdec31a5e_et3nw1r5)

### Brand Architect quality gate in action

The Brand Architect enforces strict compliance with the design system.

It validates color usage against the defined palette, enforces typography hierarchy, and ensures that the logo follows its construction rules. It also detects common low-quality patterns such as unnecessary gradients or inconsistent spacing. This gate ensures that outputs are not just generated, but conform to a defined standard before they are accepted.

## Building the 5-Slide Pitch Deck

### Skill 2: investor-ready storytelling

The pitch deck skill generates a structured, multi-slide presentation that aligns visual design with narrative flow.

It reads from BRAND.md and produces a five-slide artifact that integrates branding, messaging, and layout into a cohesive story. Unlike static design outputs, this artifact must balance visual consistency with clarity of communication across multiple sections.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/f38e8012-3c4d-49db-8e56-0fcfdec31a5e_5pxmu125)

### Dual-agent review pipeline

The pitch deck introduces a second evaluation layer.

The Brand Architect ensures visual correctness, while the Creative Director evaluates composition, storytelling, and clarity. This dual-layer validation reflects the higher stakes of narrative artifacts, where correctness alone is not sufficient and effectiveness must also be measured.

## Rendering the Animated Logo Reveal

### Skill 3: Remotion spring physics animation

The video generation skill introduces motion and timing into the pipeline.

It produces a short animated sequence using Remotion, requiring frame-level correctness and synchronization. This extends the system from static outputs into time-based media, where correctness depends on both visual design and execution logic.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/f38e8012-3c4d-49db-8e56-0fcfdec31a5e_woffri89)

### Full three-agent quality gate

The video pipeline adds a third validation layer.

The Production Engineer ensures that animation logic is correct, validating frame calculations, rendering configuration, and execution commands. This gate exists because errors in motion artifacts are not immediately visible and require validation before rendering to avoid costly iteration cycles.

## Establishing the Governance Layer

### CLAUDE.md and settings.json

The governance layer defines system-wide rules that all skills must follow.

These rules enforce that every artifact reads from BRAND.md, passes quality gates, and adheres to defined output constraints. They also control how files are generated and stored, ensuring consistency in structure and preventing unintended overwrites or dependency issues.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/f38e8012-3c4d-49db-8e56-0fcfdec31a5e_4jvlj4dv)

### Security and permission boundaries

The system enforces hard constraints at the execution level.

Sensitive files are inaccessible, preventing credential exposure. Destructive commands and external network calls are blocked, limiting the impact of misconfigured skills or malicious inputs. These controls operate independently of prompt logic, ensuring that governance is enforced even when instructions fail.

## Deploying Three Senior AI Quality-Gate Agents

### Brand Architect, Creative Director, Production Engineer

The system uses three specialized agents to enforce quality.

Each agent operates within a defined scope, ensuring that outputs meet visual, narrative, and technical standards. This separation allows the system to scale complexity without overloading a single validation layer.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/f38e8012-3c4d-49db-8e56-0fcfdec31a5e_m30vst2j)

### What makes the Brand Architect unique

The Brand Architect enforces strict adherence to design rules.

It validates color accuracy, ensures correct logo construction, and detects low-quality visual patterns. Unlike broader evaluators, it focuses specifically on enforcing the integrity of the design system, making it the primary gate for all visual outputs.

## Publishing a Forkable GitHub Repository

### Documenting for the community

The system is packaged as a reusable repository that documents its structure, capabilities, and usage.

The README explains how the pipeline works, what artifacts it produces, and how it can be extended. This allows others to replicate the system and adapt it to different brands or use cases.

### Smart .gitignore decisions

The repository distinguishes between source artifacts and generated outputs.

Text-based artifacts such as HTML files are versioned because they are lightweight and meaningful to track. Generated binaries, such as video files, are excluded because they can be recreated from source. This maintains repository efficiency while preserving reproducibility.

## 💎 Secret Mission: Social Card Skill with Full Agent Pipeline

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/f38e8012-3c4d-49db-8e56-0fcfdec31a5e_z60pngue)

### Dynamic $ARGUMENTS for customizable output

Runtime arguments enable flexible output without changing system structure.

Inputs are injected into the generation process while still adhering to brand rules and quality gates. If no argument is provided, the system defaults to predefined values, ensuring consistent output regardless of invocation method.

## Setting Up the Project Environment

### Tools and scaffolding

The environment establishes the project structure and toolchain.

Node.js and Git are verified, and the repository is initialized with a structured directory layout for skills, agents, and outputs. This creates a controlled workspace where all components operate predictably.

### Verified tools and folder structure

The system confirms that all required tools and directories are correctly configured.

The project structure includes separate directories for skills and agents, along with an output directory for generated artifacts. This organization ensures that responsibilities are clearly separated and that outputs are easy to locate and manage.

## Reflections and Key Takeaways

### Tools and concepts mastered

This project uses Node.js, Git, Claude Code, and Remotion to build a governed creative pipeline.

The core concepts include design systems, multi-agent validation, skill-based development, and automated artifact generation. Together, these components create a repeatable system for producing consistent, high-quality outputs.

### Time and challenges

This project took approximately 90 minutes.

The primary challenge was establishing the initial project structure and ensuring that all tools were correctly configured. Minor issues with layout and rendering required attention to detail, particularly in aligning generated outputs with design constraints.

### What's next

This project focuses on building a controlled system for generating brand artifacts.

The next step is expanding into dynamic web applications, where the same principles of governance and automation can be applied to interactive systems.

---

*Built with [NextWork](https://learn.nextwork.org) - [View this project](https://learn.nextwork.org/projects/f38e8012-3c4d-49db-8e56-0fcfdec31a5e)*
