# AGENTS.md

## Repository Purpose

This repository is the company's Engineering Knowledge Portal.

It is a documentation website built with Astro and Starlight and intended to be deployed through GitHub Pages.

The primary objective is to make engineering knowledge easy to discover, navigate, maintain, and understand.

Treat this repository primarily as a documentation system, not as a general-purpose web application.

## Core Responsibility

This repository owns the organization and presentation of shared engineering knowledge, including:

- engineering conventions
- architecture documentation
- project documentation
- operational documentation
- technical references
- navigation to the Engineering Handbook

The dedicated `engineering-handbook` repository owns documentation about how the engineering team works.

Do not copy Handbook content into this repository unless there is a strong technical reason.

Prefer linking to or integrating the canonical source instead.

## Technology

Use:

- Astro
- Starlight
- TypeScript where code is required
- Markdown / MDX for documentation content

Prefer Starlight-native functionality before introducing custom components or additional dependencies.

Do not add another frontend framework unless there is a concrete requirement that Astro and Starlight cannot reasonably satisfy.

## Design Philosophy

Prefer:

1. simple documentation architecture
2. clear navigation
3. readable content
4. minimal customization
5. maintainable implementation

Avoid:

- unnecessary abstractions
- custom design systems without a requirement
- complex client-side state
- unnecessary JavaScript
- visual customization that makes future Starlight upgrades difficult
- over-engineering

Content quality and information architecture are more important than visual novelty.

## Information Architecture

Use the following conceptual structure:

```text
Handbook
Conventions
Architecture
Projects
Operations
References
```

Interpret them as:

```text
Handbook
→ How we work

Conventions
→ How we write and build software

Architecture
→ How we design systems

Projects
→ How individual systems work

Operations
→ How systems are operated and recovered

References
→ Frequently needed engineering information
```

Do not introduce a new top-level documentation category before checking whether the content belongs to one of these categories.

## Source of Truth Rules

Avoid documentation duplication.

Before creating documentation, determine its canonical owner.

Examples:

- team workflow → `engineering-handbook`
- engineering principles → `engineering-handbook`
- Git naming convention → this repository
- project-specific API → project repository
- project architecture → project documentation
- architectural decision → relevant repository ADR
- OpenAPI contract → project repository
- production troubleshooting → project runbook or Operations section

When another repository owns the information, reference it instead of copying it.

## Documentation Style

Documentation should answer practical questions.

Prefer content that helps an engineer:

- understand a system
- make a decision
- perform a task
- troubleshoot a problem
- understand why a decision was made

Use:

- headings
- short paragraphs
- tables
- lists
- diagrams
- Mermaid
- code examples

Avoid unnecessarily long prose.

Prefer:

```text
general explanation
→ structure
→ details
→ examples
```

Use clear technical English.

Avoid marketing language.

## Project Documentation

For new projects, prefer this minimum structure:

```text
projects/<project-name>/

├── overview.md
├── scope.md
├── requirements.md
├── architecture.md
├── development.md
├── deployment.md
└── operations.md
```

Additional documentation may be introduced when justified.

Examples:

```text
security.md
monitoring.md
backup-recovery.md
performance.md
technical-debt.md
```

Do not create empty documentation files merely to satisfy a template.

## Architecture Documentation

Prefer diagrams when relationships are important.

Mermaid is preferred for diagrams that can reasonably be represented as code.

Architecture documentation should explain intent and boundaries rather than reproduce every implementation detail.

## Astro and Starlight Rules

Prefer standard Starlight patterns.

Use Starlight configuration for:

- navigation
- sidebar
- metadata
- search
- documentation layout

Introduce custom Astro components only when standard Markdown, MDX, or Starlight components are insufficient.

Keep custom styling small and isolated.

Avoid modifying generated files.

## File Naming

Use lowercase kebab-case.

Examples:

```text
engineering-principles.md
backup-restore.md
incident-response.md
project-lifecycle.md
```

Avoid:

```text
EngineeringPrinciples.md
engineering_principles.md
Engineering Principles.md
```

## Secrets and Sensitive Information

Never commit:

- passwords
- API keys
- access tokens
- private keys
- production credentials
- confidential personal information

Documentation may explain which environment variables or credentials are required, but never include secret values.

## Changes

When modifying documentation:

1. preserve the canonical source of truth
2. keep navigation consistent
3. avoid duplicate documentation
4. update related links
5. ensure the site builds successfully

Before considering a structural change complete, run:

```bash
npm run build
```

## Definition of Done

A documentation change is complete when:

- the content is technically accurate
- the canonical source is correct
- navigation is understandable
- internal links work
- formatting renders correctly
- the Starlight build succeeds
- no sensitive information is exposed

## When Unsure

Prefer the smallest maintainable solution.

Do not invent policies, architecture decisions, project facts, infrastructure details, or organizational rules.

If information is unknown, leave it explicitly undefined or mark it as needing clarification rather than fabricating details.