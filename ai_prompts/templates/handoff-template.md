# Handoff: PR-{N} — {Title}

**Date:** YYYY-MM-DD
**Branch:** `feat/pr-{N}-{name}`
**Task Brief:** `ai_prompts/active/pr-{N}-{name}-task-brief.md`

---

## Summary

{One sentence: what was built}

---

## Files Changed

### Created
| File | Purpose |
|------|---------|
| `{path}` | {description} |

### Modified
| File | Change |
|------|--------|
| `{path}` | {what changed} |

---

## Decisions Made

| Decision | Rationale | ADR Candidate? |
|----------|-----------|----------------|
| {Decision} | {Why} | Yes/No |

---

## Verification Results

### Sacred Four

```bash
pnpm typecheck
# [paste output]

pnpm lint
# [paste output]

pnpm test:run
# [paste output]

pnpm build
# [paste output]
```

### Results Summary

| Check | Status |
|-------|--------|
| typecheck | Pass/Fail |
| lint | Pass/Fail |
| test | Pass/Fail ({N} tests) |
| build | Pass/Fail |

---

## Outstanding Issues

- [ ] {Issue that needs CC attention}
- [ ] {Another issue}

---

## Blockers for CC

[None | List any blockers]

---

## Notes

{Anything else the reviewer should know}

---

**Ready for CC review.**
