---
name: polish-client-docs
description: Polish client-facing docs into plain language — expand jargon, cut redundancy, keep commitments and the author's voice. Use when the audience is a client or non-technical reader (proposals, reports, SOWs, status updates, decks), or when the user wants to clean up, clarify, tighten, or simplify that kind of prose — even if they don't say "polish". Prefer this over general doc tidying when the reader is external. Not for dead-code cleanup or internal eng docs.
---

# Polish Client Docs

Turn internal or technical writing into something a client reads without effort. Commitments stay locked; language and structure open up.

## Rules

- **Preserve meaning and commitments.** Never drop or alter scope, dates, prices, deliverables, legal terms, or promises while tightening. When unsure, keep it and flag it.
- **Write for the reader's knowledge level.** Expand or remove internal jargon, acronyms, and team shorthand. Prefer plain language over impressive language.
- **Say it once.** Remove hedging, throat-clearing, and repetition. When the same point appears in several places, keep the clearest instance and cut the rest, or reference the single source.
- **Keep the author's voice.** Tighten and clarify; don't rewrite into something unrecognizable or generic.
- **Flag, don't silently change.** If something looks factually wrong, contradictory, or out of date, surface it rather than guessing at a fix.

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

- **Pasted text:** work directly with what the user provides and return the revised version.
- **Local files:** read converted exports (`.txt`, `.md`, `.docx`, `.pdf`) the user points to or that live in the working directory. If a file isn't yet in a readable format, ask the user to export/convert it first.

## Workflow

1. **Scope & audience.** Identify the target doc(s) and who the client reader is. If the user names no target, ask or default to the most recent pasted text / obvious file.
2. **Clarity pass.** Fix structure, break up dense passages, replace jargon, and make each section's purpose obvious.
3. **Tighten pass.** Apply "say it once" across the whole doc.
4. **Flag uncertainties.** List anything that reads as wrong, contradictory, stale, or a commitment you didn't want to touch.
5. **Deliver:** return the revised text (inline for pasted content, or edited in place for files) plus a short summary — **Clarified** / **Trimmed** / **Flagged**.
