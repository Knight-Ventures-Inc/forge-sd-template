# FORGE Project Template

**A FORGE-governed software development project.**

---

## FORGE Canon Reference

This project operates under **The FORGE Method(TM)**.

**Canonical Authority:**
- FORGE Core: [FORGE-Method/core/forge-core.md](https://github.com/Knight-Ventures-Inc/FORGE-Method)
- Operations: [FORGE-Method/core/forge-operations.md](https://github.com/Knight-Ventures-Inc/FORGE-Method)
- SD Profile: [FORGE-Method/profiles/forge-sd-profile.md](https://github.com/Knight-Ventures-Inc/FORGE-Method)

> **Rule:** This repo does not redefine FORGE. It *consumes* FORGE by reference.
> If methodology questions arise, consult the canon.

---

## Template Usage Notice

> **This file is part of `forge-project-template/` — the operational scaffold for new FORGE projects.**

### If You Are Reading This IN the Template Repo

**This is an ARTIFACT, not a workspace.**

| Do | Don't |
|----|-------|
| Copy this repo to create new projects | Work directly in this repo |
| Reference patterns here | Add project-specific code here |
| Customize after copying | Store recon, research, or proposals here |

**Template changes only arrive via promotion from `../_workspace/` after explicit approval.**

### If You Copied This to Create a New Project

You're in the right place. Customize the `[CUSTOMIZE]` sections below and proceed.

---

## Project Identity

### What This Is
[CUSTOMIZE: 2-3 sentences describing the project's purpose]

### What This Is NOT
- [CUSTOMIZE: Explicit non-goal 1]
- [CUSTOMIZE: Explicit non-goal 2]
- [CUSTOMIZE: Explicit non-goal 3]

### Who This Is For
- **Primary users:** [CUSTOMIZE: Who uses this directly]
- **Stakeholders:** [CUSTOMIZE: Who cares about outcomes]

---

## Constitution Check (CC: Read This First)

**Before any work, check constitutional status:**

```
docs/constitution/
├── PRODUCT.md        # Product intent (North Star)
├── TECH.md           # Technical architecture
└── GOVERNANCE.md     # Security, permissions, policies
```

### If Constitution Is Empty or Missing

**STOP.** Do not scaffold. Do not implement.

Request from Human Lead:
1. Product brief / North Star document
2. Technical decisions / architecture constraints
3. Governance rules (auth, RLS, security requirements)

The constitution must exist before Execute phase begins.

### If Constitution Exists

Proceed with scaffolding and execution per the constitution.

---

## Agent Lanes

| Role | Agent | Authority | Boundary |
|------|-------|-----------|----------|
| **Human Lead** | [CUSTOMIZE] | Final decisions, greenlight, merge | Reviews, approves, resolves |
| **Strategist** | Product Strategist | Frame phase, product intent | Does NOT implement or plan architecture |
| **Architect** | Project Architect v2 | Architecture packets, planning | Does NOT implement code |
| **Quality Gate** | CC (Claude Code) | Verification, PRs, build-plan | Does NOT make arch decisions |
| **Implementation** | Cursor | Code per task briefs | Does NOT create PRs |
| **Recon Agent** | Codex Cloud (optional) | Remote recon, handoff packets | Does NOT modify code |

### Lane Rules

- **Strategist and Architect** communicate bidirectionally (through Human Lead)
- **Specs flow one-way** to Quality Gate (no modifications)
- **Quality Gate and Implementation** cycle tightly
- **Implementation Engine never communicates** with Strategist or Architect
- **Codex Cloud** produces recon reports and handoff packets only (never modifies code)

---

## Inbox-Driven Workflow (Frame Phase)

The Product Strategist uses an inbox-driven workflow for Frame phase work.

### Structure

```
inbox/
├── 00_drop/              ← Discovery input (human writes here)
│   └── <feature-slug>/   ← One folder per feature
└── 10_product-intent/    ← Product Intent Packets (agent writes here)
    └── <feature-slug>/   ← Output packet
```

### Workflow

1. **Human drops discovery materials** in `inbox/00_drop/<slug>/`
   - README.md (required) — describe the idea
   - threads/ — transcripts, notes, brain dumps
   - assets/ — sketches, screenshots
   - links.md — external references

2. **Product Strategist processes** the discovery materials
   - Asks clarifying questions (up to 3 rounds)
   - Synthesizes into coherent product intent
   - Produces Product Intent Packet

3. **Output appears** in `inbox/10_product-intent/<slug>/`
   - 8 required artifacts (intent, actors, use-cases, etc.)
   - Professional PM-level quality

4. **Human Lead routes** to Project Architect v2

5. **Project Architect v2 processes** the Product Intent Packet
   - Asks clarifying questions (up to 2 rounds)
   - Decomposes into architecture components
   - Produces Architecture & Execution Packet

6. **Architecture Packet appears** in `inbox/20_architecture-plan/<slug>/`
   - 7 artifacts (architecture, execution plan, PR plan, etc.)
   - Complete planning ready for execution

7. **Human Lead routes** to Ops Conductor / Execute agents

### Relationship to Constitution

- **Product Intent Packets** are Frame-phase discovery artifacts
- **Architecture Packets** are Orchestrate-phase planning artifacts
- **PRODUCT.md** (in `docs/constitution/`) is the refined constitutional doc
- Packets **precede and inform** constitutional docs but don't replace them
- Both packet types are preserved as historical records

See `inbox/README.md` for detailed submission guidelines.

---

## Platform vs Tenant Planes

This project operates on two planes:

### Platform Plane
- **Scope:** System-wide (the SaaS platform itself)
- **Actors:** Stakeholders
- **Surfaces:** Stakeholder Portal, Stakeholder AI
- **Access:** Invite-only platform memberships

### Tenant Plane
- **Scope:** Per-organization (firms, customers, ventures)
- **Actors:** Owners, Admins, Members
- **Surfaces:** Tenant application
- **Access:** Organization memberships

### Session Invariant
**A session is scoped to exactly one plane.** No cross-visibility between planes.

- Stakeholder session → Stakeholder Portal only
- Tenant session → Tenant app for that org only

### Dual-Plane Humans
If a human operates in both planes, they use **separate identities**:
- Stakeholder identity (separate email)
- Tenant identity (separate email)

Switching planes requires logout/login.

---

## Current State

### Phase
[CUSTOMIZE: Frame | Orchestrate | Refine | Govern | Execute]

### If In Execute
- **Current PR:** [PR-XX or "None"]
- **Build Plan:** `docs/build-plan.md`
- **Active Brief:** `ai_prompts/active/`
- **Ops State:** `docs/ops/state.md`

---

## Commands

### Verification Sequence (Sacred Four)
```bash
pnpm typecheck && pnpm lint && pnpm test:run && pnpm build
```
**All four must pass before any PR. No exceptions.**

### Development
```bash
pnpm dev          # Start development server
pnpm build        # Production build
```

### Database (if using Supabase)
```bash
pnpm db:generate  # Generate migrations
pnpm db:migrate   # Apply migrations
```

---

## DATE SAFETY RULE

All dates used in:
- `CHANGELOG.md`
- `plans/`
- `reports/`
- `docs/decisions/`

**MUST** be based on the current local system date at runtime.

If the agent cannot verify the current date, it must halt and request confirmation before writing dated artifacts.

**Heuristic or assumed dates are prohibited.**

---

## Non-Negotiables

1. **Constitution before Execute** — No constitutional docs = no scaffolding
2. **Verification runs before every PR** — Sacred Four, all must pass
3. **Constitutional docs are read-only** — Suggest changes, don't modify
4. **5-line rule** — < 5 lines: CC fixes; >= 5 lines: back to Cursor
5. **File-based handoffs** — Everything through `ai_prompts/`
6. **Archive before starting** — Each PR archives the previous brief

---

## Getting Oriented (CC Session Start)

```
1. Read this file (you're doing it)
2. Check docs/constitution/ — if empty, STOP and request inputs
3. Check docs/build-plan.md for current PR
4. Run: git log --oneline -5
5. Check ai_prompts/active/ for current brief
6. Ready to proceed (~90 seconds)
```

---

## Key Locations

| What | Where |
|------|-------|
| Constitution | `docs/constitution/` |
| Build Plan | `docs/build-plan.md` |
| Ops State | `docs/ops/state.md` |
| Inbox (Frame & Orchestrate) | `inbox/` |
| Discovery Input | `inbox/00_drop/` |
| Product Intent Packets | `inbox/10_product-intent/` |
| Architecture Packets | `inbox/20_architecture-plan/` |
| Current Brief | `ai_prompts/active/` |
| Completed Briefs | `ai_prompts/completed/` |
| Templates | `ai_prompts/templates/` |
| ADRs | `docs/adr/` |
| Parking Lot | `docs/parking-lot/` |
| Discovery (legacy) | `docs/discovery/` |
| Auth Utilities | `src/lib/auth/` |
| Stakeholder Portal (Platform Plane) | `src/app/portal/` |
| Stakeholder AI | `supabase/functions/stakeholder-ai/` |
| Auth Migrations | `supabase/migrations/` |

---

## Parking Lot Protocol

The parking lot (`docs/parking-lot/`) captures issues and ideas discovered during development that shouldn't derail current PR scope.

### Files

| File | What Goes Here |
|------|----------------|
| `known-issues.md` | Bugs, broken things, security risks, technical debt |
| `future-work.md` | Feature ideas, enhancements, optimizations, nice-to-haves |

### When to Log

Log to parking lot **immediately** when you discover:
- A bug unrelated to your current PR
- A missing feature that would be nice but isn't in scope
- Technical debt worth addressing later
- A security concern that needs follow-up
- An optimization opportunity
- Ideas from debugging that could improve the system

### Entry Format

```markdown
## [YYYY-MM-DD] Short Title

**Source:** PR-XX or context | **Severity:** Low/Medium/High | **Effort:** X hrs

One-paragraph description of the issue or idea.

**Workaround:** (if applicable for known-issues)

**Fix:** Proposed solution or next steps.
```

### Workflow

1. **Discover** an issue or idea during PR work
2. **Log immediately** to the appropriate parking-lot file
3. **Continue** with current PR scope
4. **Review** parking lot when planning future PRs
5. **Graduate** items to GitHub Issues when prioritized for a specific PR

**Golden Rule:** Don't let discoveries get lost in conversation history. If it's not in scope, park it.

---

## Technical Stack

| Layer | Technology |
|-------|------------|
| Framework | [CUSTOMIZE: e.g., Next.js 15] |
| Language | [CUSTOMIZE: e.g., TypeScript 5.x] |
| Database | [CUSTOMIZE: e.g., Supabase/Postgres] |
| Auth | [CUSTOMIZE: e.g., Supabase Auth] |
| Hosting | [CUSTOMIZE: e.g., Vercel] |
| Styling | [CUSTOMIZE: e.g., Tailwind + shadcn/ui] |

---

## FORGE Extensions

This project includes scaffolding for required FORGE extensions.

### Discovery Pack (Required for All Projects)

Location: `docs/discovery/`

Every FORGE project begins with discovery. The Discovery Pack provides structured intake-to-spec workflow.

| Stage | Folder | Purpose |
|-------|--------|---------|
| Intake | `docs/discovery/intake/` | Raw inputs (transcripts, notes, screenshots) |
| Structure | `docs/discovery/themes/` | Organized themes |
| Handoff | `docs/discovery/handoff/` | Final spec pack |

**See:** `docs/discovery/README.md`

### Auth/RBAC (Required for Software Projects)

Location: `supabase/migrations/`, `src/lib/auth/`

FORGE uses an org-centric identity model for tenant-level roles and a separate platform-level membership system.

#### Tenant Roles (within organizations)

| Role | Description |
|------|-------------|
| Owner | Ultimate authority over the organization |
| Admin | User management, settings |
| Member | Standard team access |

#### Platform Memberships (supra-tenant)

| Role | Description |
|------|-------------|
| Stakeholder | Stakeholder Portal access, feedback, visibility into product execution |

**Note:** Stakeholder is a platform-level actor, not a tenant role. Stakeholders operate in the platform plane (Stakeholder Portal) and have no implicit access to tenant data. See [Auth/RBAC extension](https://github.com/Knight-Ventures-Inc/FORGE-Method/blob/main/docs/extensions/auth-rbac.md).

**Key files:**
- `supabase/migrations/00001_auth_foundation.sql` — Schema and RLS
- `src/lib/auth/types.ts` — TypeScript types
- `src/lib/auth/client.ts` — Client utilities

### Stakeholder Interface (Required for Software Projects)

Location: `src/app/portal/`, `supabase/functions/stakeholder-ai/`

Supra-tenant visibility and feedback system for stakeholders. The Stakeholder Portal operates in the platform plane and provides visibility into product execution (roadmap, milestones, status) without access to tenant data.

**Portal:** `src/app/portal/`
- Feedback submission and voting
- Project visibility (platform-level, not tenant data)

**Stakeholder AI:** `supabase/functions/stakeholder-ai/`
- Explains project status and roadmap
- Answers questions about the product (from platform context only)
- Captures feedback
- Does NOT access tenant data
- Does NOT execute tasks (execution is FAI, maturity-gated)

**Key files:**
- `supabase/migrations/00002_stakeholder_portal.sql` — Portal schema
- `supabase/functions/stakeholder-ai/index.ts` — AI edge function

---

## FORGE AI Interface (FAI) — Optional

> **Skip this section** if your project does not use FORGE AI Interface.

FAI is an optional FORGE extension that provides a first-class AI interface layer. **FAI is an interface layer, not an autonomous agent.**

### FAI Capabilities

If enabled, FAI provides:
- **Knowledge-Based Q&A** — Answer questions about how the app works
- **Action Execution** — Perform user actions via API with RBAC mirroring
- **Feedback Capture** — Convert conversations to structured parking-lot entries
- **Multimodal Intake** — Accept screenshots for visual context

### FAI Boundaries (Non-Negotiable)

| FAI Does NOT | Why |
|--------------|-----|
| Modify code | Code authority remains with CC/Cursor |
| Create PRs | PRs remain in Quality Gate lane |
| Auto-merge | Human Lead approval required |
| Exceed user permissions | RBAC mirroring enforced |

### FAI Configuration

If adopting FAI:
1. Complete `docs/constitution/FAI.md`
2. Create GitHub App with minimal permissions
3. Configure feedback routing to parking-lot
4. Review `ai_prompts/templates/fai-feedback-brief.template.md`

### FAI Status: [DISABLED / ENABLED]

Set to ENABLED in `docs/constitution/FAI.md` when adopting.

---

*This project follows The FORGE Method(TM) — theforgemethod.org*
