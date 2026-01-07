# Constitutional Documents

**Status:** Placeholders (awaiting Refine phase)

---

## Purpose

Constitutional documents are the **authoritative specifications** for this project. They define what we're building, how it works, and the rules we follow.

**These documents are READ-ONLY during Execute.** Changes require Human Lead approval and a formal amendment process.

---

## Document Hierarchy

### Level 1: Intent (Why)
| Document | Purpose |
|----------|---------|
| `north-star.md` | Product vision, goals, success criteria |

### Level 2: Structure (What)
| Document | Purpose |
|----------|---------|
| `system-architecture.md` | Components, data flow, technical decisions |
| `engineering-playbook.md` | Coding standards, patterns, conventions |

### Level 3: Specification (How)
| Document | Purpose |
|----------|---------|
| `data-model.md` | Database schema, relationships, constraints |
| `api-contract.md` | All endpoints, request/response shapes |
| `security-policies.md` | Authentication, authorization, RLS policies |

---

## Authority Rules

1. **Constitution > CLAUDE.md** — If CLAUDE.md conflicts with any constitutional document, the constitution is authoritative.

2. **Lower levels implement higher levels** — data-model.md implements decisions from system-architecture.md, which implements north-star.md.

3. **Amendments require approval chain** — CP proposes, Leo approves, CC implements the change.

4. **No implicit changes** — All modifications must be explicit, versioned, and committed.

---

## Current Status

| Document | Status |
|----------|--------|
| north-star.md | Placeholder |
| system-architecture.md | Placeholder |
| engineering-playbook.md | Placeholder |
| data-model.md | Placeholder |
| api-contract.md | Placeholder |
| security-policies.md | Placeholder |

---

## When Documents Arrive

1. CP authors constitutional documents during Refine
2. Leo approves documents during Govern
3. CC places documents here, replacing placeholders
4. CC verifies consistency across all documents
5. Project Shell banner is removed when Execute is authorized

---

*This project follows The FORGE Method(TM) — theforgemethod.org*
