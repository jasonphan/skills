---
name: declutter
description: Remove dead code and redundant documentation (code comments and standalone docs like design docs or READMEs) to keep a codebase lean. Trigger whenever the user wants to clean up, simplify, trim, or "tidy up" code or docs, mentions unused imports/functions, stale or duplicated comments, or consolidating redundant docs — even if they don't say "declutter".
---

# Declutter

Strip away what isn't needed so the code and docs that remain are easier to read: no dead code, no redundant documentation, the simplest thing that still works.

## Rules

- **Verify before deleting.** Search every caller — including tests, config, and string-based references like dynamic imports or serialization keys. If you can't confirm something is unused, don't delete it; say so.
- **Respect public boundaries.** Exported symbols, CLI flags, config schemas, and public APIs may be unused internally but are still contracts. Flag these; never remove them silently.
- **Redundant docs are clutter in any form** — code comments and standalone docs (design docs, READMEs, runbooks). Keep only what adds something new.
- **Consolidate duplicated docs.** When several docs repeat the same content, keep one authoritative source and replace the rest with a pointer to it.
- **Keep the change minimal.** Don't refactor working code while tidying; mention bigger simplifications but leave them for another pass.
- **Don't guess at side effects.** If removal risks behavior changes (logging, metrics, caching), call it out rather than deleting.

## Workflow

1. **Scope.** If the user names no target, default to current changes — uncommitted working-tree modifications (e.g. `git status`, `git diff`). Don't sweep the whole repo unprompted.
2. **Find candidates:** unused code, commented-out code, and docs (code or prose) that are duplicated, stale, or say nothing new.
3. **Confirm safe.** For docs, pick the authoritative copy before collapsing duplicates. Surface anything public or uncertain.
4. **Remove or consolidate** in small steps — replace redundant docs with a reference to the single source.
5. **Verify** with the project's linter, type checker, and tests if present; report what you ran.
6. **Summarize:** **Removed** / **Left alone** (reason) / **Verified**.
