---
name: declutter
description: Remove dead code and redundant documentation (code comments and standalone docs like design docs or READMEs), and tighten verbose prose — all without dropping a single real constraint, fact, or structural element. Trigger whenever the user wants to clean up, simplify, trim, "tidy up", or declutter code or docs, mentions unused imports/functions, stale or duplicated comments, consolidating redundant docs, or wants a doc/section rewritten to be tighter — even if they don't say "declutter".
---

# Declutter

> **Remove or tighten anything that doesn't earn its place — without dropping a single real constraint, fact, warning, or structural element.**

- **Redundant content** (dead code, duplicated or stale docs) → *delete* it.
- **Verbose but valid prose** (same point, more words than it needs) → *rewrite it tight*.

## Rules

- **Verify before deleting.** Search every caller — including tests, config, and string-based references like dynamic imports or serialization keys. If you can't confirm something is unused, don't delete it; say so.
- **Respect public boundaries.** Exported symbols, CLI flags, config schemas, and public APIs may be unused internally but are still contracts. Flag these; never remove them silently.
- **Redundant docs are clutter in any form** — code comments and standalone docs (design docs, READMEs, runbooks). Keep only what adds something new.
- **Consolidate duplicated docs.** When several docs repeat the same content, keep one authoritative source and replace the rest with a pointer to it.
- **Keep the change minimal.** Don't refactor working code while tidying; mention bigger simplifications but leave them for another pass.
- **Don't guess at side effects.** If removal risks behavior changes (logging, metrics, caching), call it out rather than deleting.

## When rewriting prose tight

Leaner version of the *same* content — not a paraphrase that drops nuance. When in doubt, keep it and flag it.

- **Lose no meaning.** Preserve every factual claim, constraint, warning, caveat, and example. If two sentences make distinct points, keep them distinct — never fuse them into one generic sentence just to save words.
- **Preserve formatting structure.** Keep heading hierarchy, tables, code blocks, lists (including nested lists), and callouts. Decluttering means cutting filler and reordering for flow — not converting a table into a paragraph or collapsing a nested list into prose. Keep markdown semantics (links, emphasis, inline code) intact.
- **Cut filler, not substance.** Remove redundant lead-ins, restated points, and throat-clearing. When the same idea appears twice, keep the sharper instance — but only when they genuinely say the same thing.

**Example — tightened, every point and the table kept:**

Before:
> Our rate limiter is something we added last year. It limits login attempts. The limit is 5 per minute per IP address. After that the IP gets throttled. The throttle lasts 10 minutes. Note that both failed and successful attempts count. Webhooks are an exception and are not limited. There's a table below with the settings.

After:
> The login rate limiter allows 5 attempts/minute per IP, then throttles the IP for 10 minutes. This counts failed *and* successful attempts; webhooks are exempt.

| Setting | Default | Notes |
| --- | --- | --- |
| MAX_ATTEMPTS | 5 | Per minute, per IP |
| THROTTLE_MINS | 10 | Applies after limit hit |

Throat-clearing gone; every constraint, the exemption, and the table remain.

## Workflow

1. **Scope.** If the user names no target, ask whether they want removal, prose tightening, or both. If still unspecified, default to current changes — uncommitted working-tree modifications (e.g. `git status`, `git diff`). Don't sweep the whole repo unprompted.
2. **Find candidates:** unused code, commented-out code, and docs (code or prose) that are duplicated, stale, or say nothing new.
3. **Confirm safe.** For docs, pick the authoritative copy before collapsing duplicates. Surface anything public or uncertain.
4. **Remove or consolidate** in small steps — replace redundant docs with a reference to the single source. For prose, rewrite tight while preserving points and structure.
5. **Verify** with the project's linter, type checker, and tests if present; report what you ran.
6. **Summarize:** **Removed** / **Left alone** (reason) / **Verified**.
