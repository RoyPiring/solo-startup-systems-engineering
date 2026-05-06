<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Ship a Startup Website with AI Agents

**Project Link:** [View Project](https://learn.nextwork.org/projects/d31a4ff3-5276-4064-a4ab-cfb03fb2f1a0)

**Author:** Roy Piring Jr  
**Email:** rpiringhawaii@gmail.com

---

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/d31a4ff3-5276-4064-a4ab-cfb03fb2f1a0_yhgqyiwr)

## Shipping a Real Startup Website with AI-Assisted Development

### Project overview

This project builds a multi-page Next.js website for a fictional AI advisory startup, PineappleAI, using parallel AI agents inside Antigravity IDE.

The objective is to deliver a production-ready site with a landing page, services page, about page, and contact form within a constrained time window. The focus is not just speed, but proving that coordinated AI agents can generate, validate, and deploy a complete web system while maintaining consistency across architecture, design, and accessibility.

### Key tools and concepts

The system is built using Node.js, Git, Antigravity IDE, Next.js, TypeScript, Tailwind CSS, Playwright, and Vercel.

Core concepts include AI-assisted development, multi-agent orchestration, E2E testing, WCAG 2.2 AA accessibility standards, Git-based workflows, and server-side rendering with cookie-based state management. The project also reinforces how model selection impacts output quality depending on task complexity.

### Time and reflections

This project took approximately 2 hours. The main challenge was resolving the flash of unstyled content during theme switching, which required correct handling of server-side cookies in Next.js.


The project demonstrates how AI agents can accelerate development, but still requires controlled architecture decisions to maintain consistency and avoid UI or state issues.

## Setting Up the Development Environment

### Step goals

The environment establishes the execution layer for the application.

Node.js and Git are installed to support local development and version control. Antigravity IDE provides access to AI agents and model orchestration. The project is scaffolded using a Next.js command that initializes TypeScript, Tailwind CSS, ESLint, and App Router configuration, creating a production-ready baseline.

### Node.js and Git versions verified

The environment is validated by confirming Node.js version 20.10.0 and Git version 2.42.0.

This ensures compatibility with Next.js and avoids runtime inconsistencies during development and deployment.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/d31a4ff3-5276-4064-a4ab-cfb03fb2f1a0_uomu1h66)

### Understanding the scaffolding command

The initialization command uses the --yes flag to bypass prompts and apply default configurations.

This enables fast, repeatable project setup without manual input, which is necessary when integrating with automated workflows or AI-driven execution.

## Planning the Architecture with Gemini Pro

### Step goals

Architecture is defined before implementation to prevent rework.

An AGENTS.md file establishes coding standards, accessibility rules, and model selection guidelines. Gemini Pro is used to generate system structure, component hierarchy, and design tokens, while Git feature branches isolate each phase of development.

### AGENTS.md and model selection rationale

AGENTS.md acts as the control layer for all AI agents.

It defines when to use high-reasoning models versus fast-response models. Gemini Pro is reserved for architectural decisions, while Gemini Flash is used for deterministic tasks like UI scaffolding. This separation ensures efficiency without sacrificing design integrity.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/d31a4ff3-5276-4064-a4ab-cfb03fb2f1a0_bk90ugcg)

## Building the Landing Page

### Step goals

The landing page establishes the visual and structural baseline.

It follows the design system defined in AGENTS.md and implements accessibility standards from the start. This ensures consistency across all future pages.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/d31a4ff3-5276-4064-a4ab-cfb03fb2f1a0_nkb4vtam)

### Semantic HTML and accessibility

Semantic HTML elements define structure and accessibility.

Using elements like main and proper document structure enables screen readers to navigate content effectively. This ensures compliance with accessibility standards and improves usability for assistive technologies.

## Running Parallel Agents to Build Services and About Pages

### Step goals

Parallel agents are used to accelerate development across independent components.

Each agent operates within its own feature branch, generating code for a specific page. Outputs are reviewed, approved, and merged into the main branch to maintain quality and consistency.

### How parallel agents accelerate development

Task specialization improves speed and accuracy.

High-reasoning agents handle complex logic, while faster models generate repetitive UI components. Isolating work across branches prevents context conflicts and reduces errors in generated code.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/d31a4ff3-5276-4064-a4ab-cfb03fb2f1a0_s7dxgrsd)

### Choosing the right model for the task

Model selection is based on task complexity.

Gemini Flash is used for UI scaffolding due to its speed and predictable output, while Gemini Pro is reserved for decisions that require deeper reasoning, such as architecture and state management.

## Building an Accessible Contact Form

### Step goals

The contact form introduces user interaction and validation.

It is built with basic structure first, then refined through accessibility checks to ensure compliance with WCAG standards.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/d31a4ff3-5276-4064-a4ab-cfb03fb2f1a0_kep4iao2)

### Accessible error handling with aria-describedby

Error messaging is linked directly to input fields.

This ensures screen readers announce validation feedback correctly, providing the same context to all users regardless of how they interact with the interface.

## Achieving Zero Accessibility Violations with axe-core

### Step goals

Automated and manual testing validate accessibility compliance.

Axe-core scans identify violations, which are then resolved to meet WCAG 2.2 AA standards. Manual verification ensures keyboard navigation and screen reader behavior function as expected.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/d31a4ff3-5276-4064-a4ab-cfb03fb2f1a0_knwnzuyr)

### Initial violation count

Initial testing identified a single contrast issue, which was resolved.

Final results show zero accessibility violations across all pages, confirming compliance.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/d31a4ff3-5276-4064-a4ab-cfb03fb2f1a0_gz0xbldi)

### Manual keyboard and screen reader verification

Manual testing confirms usability beyond automated scans.

All interactive elements are accessible via keyboard, and visual focus indicators are clearly visible. Screen readers correctly announce form errors and input relationships.

## Writing E2E Tests with Playwright

### Step goals

E2E tests validate real user interactions.

Tests cover navigation, form submission, validation behavior, and accessibility checks across all pages.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/d31a4ff3-5276-4064-a4ab-cfb03fb2f1a0_ltd0gnpv)

### Why semantic locators matter

Semantic locators align tests with real user behavior.

Using roles and labels ensures tests remain stable even if styling changes, while also reinforcing accessibility standards across the application.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/d31a4ff3-5276-4064-a4ab-cfb03fb2f1a0_8arlhn9h)

## Merging Branches and Deploying to Vercel

### Step goals

All feature branches are merged into the main branch for deployment.

The application is deployed to Vercel, and the full test suite is executed against the live environment to confirm functionality.

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/d31a4ff3-5276-4064-a4ab-cfb03fb2f1a0_9mfkmc76)

### Git branch history

The project includes five feature branches representing each phase of development.

These branches are merged into a unified history, demonstrating structured and incremental progress from initial setup to final testing.

### Live deployment URL

The application is successfully deployed and validated.

https://pineapple-ai-eight.vercel.app

## Secret Mission: Case Studies Page with Animations and Dark/Light Mode

![Image](https://learn.nextwork.org/refreshed_maroon_timid_jujube/uploads/d31a4ff3-5276-4064-a4ab-cfb03fb2f1a0_1td9hy9g)

### Model selection for theme architecture

Gemini Pro is used for this phase due to its reasoning capabilities.

Managing SSR-safe theme toggling and cookie persistence requires understanding interactions between server rendering, client state, and styling systems. This prevents UI inconsistencies such as flashing during theme changes.

---

*Built with [NextWork](https://learn.nextwork.org) - [View this project](https://learn.nextwork.org/projects/d31a4ff3-5276-4064-a4ab-cfb03fb2f1a0)*
