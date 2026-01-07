> **FORGE-SD Project Template**
>
> This repository is cloned or forked to create new FORGE-governed projects.
> It is NOT the FORGE methodology, canon, or documentation source of truth.
>
> For FORGE methodology: [theforgemethod.org](https://theforgemethod.org)

---

> **PROJECT SHELL** — Structure only. Awaiting Frame approval and constitutional documents before Execute is authorized.

---

# [Project Name]

[One-line description from Kickoff Brief]

## Overview

[2-3 sentences from Intent Summary]

## Status

**Phase:** [Frame | Orchestrate | Refine | Govern | Execute]

## Quick Start

[Placeholder until Execute begins]

```bash
# Clone and setup
git clone [repo-url] [project-name]
cd [project-name]
pnpm install

# Development
pnpm dev
```

## Documentation

- [Constitutional Documents](docs/constitution/)
- [Build Plan](docs/build-plan.md)
- [Operational State](docs/ops/state.md)

## Project Structure

```
[project-codename]/
├── .cursor/rules/        # Cursor IDE configuration
├── .github/              # GitHub templates and workflows
├── ai_prompts/           # Task briefs and handoffs
│   ├── active/           # Current task brief only
│   ├── completed/        # Archived by PR number
│   └── templates/        # Reusable templates
├── docs/
│   ├── constitution/     # Authoritative specs (READ-ONLY during Execute)
│   ├── adr/              # Architecture Decision Records
│   └── ops/              # Operational state
├── reports/              # Status reports and audits
├── src/                  # Application source
└── tests/                # Test files
```

## Instantiation Instructions

When using this template to create a new project:

1. Clone or fork this repository
2. Replace `[Project Name]` and `[project-codename]` placeholders
3. Fill `CLAUDE.md` with project-specific values from Kickoff Brief
4. Place constitutional documents in `docs/constitution/`
5. Remove the PROJECT SHELL banner once Execute is authorized
6. Delete or update `.forge-template` marker file

---

*This project follows The FORGE Method(TM) — theforgemethod.org*
