---
name: polish-client-docs
description: Polish client-facing docs into plain language — expand jargon, cut redundancy, keep commitments and the author's voice. Use when the audience is a client or non-technical reader (proposals, reports, SOWs, status updates, decks), or when the user wants to clean up, clarify, tighten, or simplify that kind of prose — even if they don't say "polish". Prefer this over general doc tidying when the reader is external. Not for dead-code cleanup or internal eng docs.
---

# Polish Client Docs

Turn technical or internal writing into something a client reads without effort. Commitments stay locked; language and structure open up.

## Rules

- **Preserve meaning and commitments.** Never drop or alter scope, dates, prices, deliverables, legal terms, or promises while tightening. When unsure, keep it and flag it.
- **Write for the reader.** Expand or remove jargon, acronyms, and team shorthand. Prefer plain language over impressive language.
- **Say it once.** Cut hedging, throat-clearing, and repetition. Same point in several places → keep the clearest instance (or reference it).
- **Keep the author's voice.** Tighten and clarify; don't rewrite into something unrecognizable or generic.
- **Flag, don't silently change.** Surface anything that looks wrong, contradictory, or out of date.

## Examples

**Technical → client-plain (jargon expanded, commitments kept):**

Before:
> We'll leverage the OAuth2 handshake to facilitate SSO via IdP federation, pending sign-off on the SOW. Rollout is targeted for Q3 contingent on resource allocation.

After:
> You'll be able to log in with your existing company account (single sign-on). This starts once you approve the statement of work, and we're aiming for a Q3 launch.

**Keep the author's voice (tighten, don't flatten into generic corporate-speak):**

Before:
> We are incredibly excited to partner with you on this transformative initiative that will unlock synergies across your organization.

After:
> We're glad to be working with you on this.

## Input

- **Pasted text:** revise what the user provides; return the revised version.
- **Local files:** read `.txt`, `.md`, `.docx`, `.pdf` the user points to (or that live in the working directory). If not yet readable, ask them to export/convert first.

## Workflow

1. **Scope & audience.** Identify the doc(s) and who the client reader is. No target → ask, or default to latest pasted text / obvious file.
2. **Clarity pass.** Fix structure, break up dense passages, replace jargon, make each section's purpose obvious.
3. **Tighten pass.** Apply "say it once" across the whole doc.
4. **Flag uncertainties.** List anything wrong, contradictory, stale, or a commitment you left untouched.
5. **Deliver:** revised text (inline for paste, edit-in-place for files) plus **Clarified** / **Trimmed** / **Flagged**.
