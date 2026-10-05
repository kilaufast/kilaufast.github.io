# Engineering Knowledge Portal

This repository contains the source code for the company's Engineering Knowledge Portal.

The portal is the central entry point for engineering knowledge across the organization.

It is built with:

- Astro
- Starlight
- Markdown / MDX
- GitHub Pages

## Purpose

The purpose of this repository is to make engineering knowledge easy to discover, navigate, and maintain.

It should provide access to:

- engineering conventions
- architecture documentation
- project documentation
- operational procedures
- shared technical references
- the Engineering Handbook

This repository acts as the presentation and navigation layer for engineering knowledge.

It is not intended to become the source of truth for every type of documentation.

Some documentation may live in dedicated repositories and be linked or integrated into this portal.

Examples:

- Engineering Handbook → `engineering-handbook`
- API specifications → project repositories
- application source code → project repositories
- infrastructure configuration → infrastructure repositories

## Documentation Structure

The intended information architecture is:

```text
src/content/docs/

├── index.mdx
│
├── handbook/
│   └── engineering handbook navigation or references
│
├── conventions/
│   ├── git.md
│   ├── commit.md
│   ├── branching.md
│   ├── naming.md
│   ├── api.md
│   ├── database.md
│   ├── logging.md
│   └── code-review.md
│
├── architecture/
│   ├── principles.md
│   ├── architecture-style.md
│   ├── environments.md
│   └── adr-guideline.md
│
├── projects/
│   └── <project-name>/
│       ├── overview.md
│       ├── requirements.md
│       ├── architecture.md
│       ├── development.md
│       ├── deployment.md
│       └── operations.md
│
├── operations/
│   ├── deployment.md
│   ├── monitoring.md
│   ├── backup-restore.md
│   ├── incident-response.md
│   └── disaster-recovery.md
│
└── references/
    ├── environments.md
    ├── repositories.md
    ├── services.md
    └── glossary.md
```

This structure may evolve as the engineering organization grows.

Avoid adding new top-level sections unless an existing section cannot reasonably represent the information.

## Documentation Ownership

Documentation should live as close as possible to its canonical source.

| Documentation | Preferred Location |
|---|---|
| Engineering working principles | Engineering Handbook |
| Team workflow | Engineering Handbook |
| Definition of Done | Engineering Handbook |
| Git conventions | Knowledge Portal / Conventions |
| API conventions | Knowledge Portal / Conventions |
| Architecture principles | Knowledge Portal / Architecture |
| Project architecture | Project documentation |
| API specification | Project repository / OpenAPI |
| Deployment procedure | Project or Operations documentation |
| Production runbook | Project or Operations documentation |
| ADR | Repository affected by the decision |

Avoid duplicating documentation between repositories.

Prefer links and references when another repository already owns the information.

## Local Development

Install dependencies:

```bash
npm install
```

Start the development server:

```bash
npm run dev
```

Build the site:

```bash
npm run build
```

Preview the production build:

```bash
npm run preview
```

## Deployment

The documentation site is intended to be deployed through GitHub Pages.

Deployment should eventually be automated using GitHub Actions.

Manual deployment should not be required during normal development.

## Documentation Principles

Documentation in this repository should be:

- clear
- concise
- maintainable
- discoverable
- useful during real engineering work

Prefer diagrams, examples, tables, and links where they improve understanding.

Do not document implementation details that can be understood more reliably from source code unless the information provides architectural or operational context.

## Writing Language

English is the default language for engineering documentation unless there is a clear organizational reason to use another language.

Use established technical terminology rather than translating terms when the English term is clearer.

## Status

This repository is currently being initialized.

The initial focus is:

1. establish the documentation structure
2. configure Astro and Starlight
3. define navigation
4. establish documentation conventions
5. add engineering knowledge incrementally