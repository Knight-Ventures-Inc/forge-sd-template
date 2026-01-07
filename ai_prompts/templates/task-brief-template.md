# Task Brief: PR-{N} — {Title}

**Date:** YYYY-MM-DD
**Branch:** `feat/pr-{N}-{name}`
**Depends On:** PR-{N-1} (must be merged first) | None

---

## Objective

{One sentence: what this PR accomplishes and why it matters}

---

## Scope

**Implement:**
- {Specific thing to build}
- {Another specific thing}
- {Tests for the above}

**Do NOT:**
- {Explicitly out of scope item}
- {Another thing to avoid}

---

## Files to Create/Modify

| File | Action | Purpose |
|------|--------|---------|
| `src/app/api/v1/{resource}/route.ts` | Create | {endpoint purpose} |
| `src/lib/{module}.ts` | Create | {utility purpose} |
| `src/lib/validation/{schema}.ts` | Create | Zod schema |
| `tests/{test-file}.test.ts` | Create | Unit tests |

---

## Specs to Reference

- `docs/constitution/api-contract.md` Section {X}
- `docs/constitution/data-model.md` Section {Y}
- `docs/constitution/engineering-playbook.md` Section {Z}

---

## Acceptance Criteria

- [ ] {Specific, testable criterion}
- [ ] {Another criterion}
- [ ] All tests pass: `pnpm test:run`
- [ ] No TypeScript errors: `pnpm typecheck`
- [ ] Lint passes: `pnpm lint`
- [ ] Build succeeds: `pnpm build`

---

## Implementation Notes

{Any additional context, warnings, or guidance}

---

## Handoff Expectations

When complete, create `ai_prompts/active/pr-{N}-{name}-handoff.md` with:
- Files changed (created vs modified)
- Decisions made (flag any ADR candidates)
- Test output (paste actual results)
- Any blockers for CC
