---
name: declutter
description: Remove dead code and redundant documentation (code comments and standalone docs like design docs or READMEs), and tighten verbose prose — all without dropping a single real constraint, fact, or structural element. Trigger whenever the user wants to clean up, simplify, trim, "tidy up", or declutter code or docs, mentions unused imports/functions, stale or duplicated comments, consolidating redundant docs, or wants a doc/section rewritten to be tighter — even if they don't say "declutter".
---

# Declutter

Remove or tighten anything that doesn't earn its place — without dropping a real constraint, fact, warning, or structural element.

- **Redundant** (dead code, duplicated/stale docs) → delete
- **Verbose but valid** (same point, too many words) → rewrite tight

## Rules

- **Verify before deleting.** Search callers — tests, config, dynamic imports, serialization keys. If unused status is unclear, don't delete; say so.
- **Respect public boundaries.** Exported symbols, CLI flags, config schemas, public APIs are contracts even if unused internally. Flag; never remove silently.
- **Docs are clutter in any form** — comments and standalone docs. Keep only what adds something new.
- **Consolidate duplicates.** Keep one authoritative source; replace the rest with a pointer.
- **Keep the change minimal.** Don't refactor while tidying; mention bigger simplifications for a later pass.
- **Don't guess at side effects.** If removal risks behavior (logging, metrics, caching), call it out.

## When rewriting prose tight

Leaner version of the *same* content — not a paraphrase that drops nuance. When in doubt, keep it and flag it.

- **Lose no meaning.** Preserve every claim, constraint, warning, caveat, and example. Distinct points stay distinct — don't fuse them into one generic sentence.
- **Preserve formatting.** Keep headings, tables, code blocks, lists (including nested), callouts, and markdown semantics. Cut filler; don't collapse structure.
- **Cut filler, not substance.** Drop lead-ins, restatements, throat-clearing. When the same idea appears twice, keep the sharper instance only if they truly say the same thing.

**Example — tightened, every point and the table kept:**

Before:
> Our rate limiter is something we added last year. It limits login attempts. The limit is 5 per minute per IP address. After that the IP gets throttled. The throttle lasts 10 minutes. Note that both failed and successful attempts count. Webhooks are an exception and are not limited. There's a table below with the settings.

After:
> The login rate limiter allows 5 attempts/minute per IP, then throttles the IP for 10 minutes. This counts failed *and* successful attempts; webhooks are exempt.

| Setting | Default | Notes |
| --- | --- | --- |
| MAX_ATTEMPTS | 5 | Per minute, per IP |
| THROTTLE_MINS | 10 | Applies after limit hit |

## Workflow

1. **Scope.** No target named → ask: removal, prose tightening, or both. Still unclear → default to current changes (`git status` / `git diff`). Don't sweep the whole repo unprompted.
2. **Find candidates:** unused code, commented-out code, duplicated/stale/empty docs.
3. **Confirm safe.** Pick the authoritative doc before collapsing duplicates. Surface anything public or uncertain.
4. **Remove or consolidate** in small steps. For prose, rewrite tight while preserving points and structure.
5. **Verify** with the project's linter, type checker, and tests if present; report what you ran.
6. **Summarize:** **Removed** / **Left alone** (reason) / **Verified**.
