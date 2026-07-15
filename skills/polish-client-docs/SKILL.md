---
name: polish-client-docs
description: Make client-facing documentation clear, easy to understand, and free of duplicated content. Works on pasted text or on locally converted files (.txt, .md, .docx, .pdf exports) from sources like Google Docs, Word, or PDFs. Trigger whenever the user wants to clean up, tighten, clarify, or simplify a client-facing doc, proposal, report, deck, or any prose meant for a non-technical audience — even if they don't say "polish".
---

# Polish Client Docs

Make documentation written for clients clear and easy to understand: plain language, no redundancy, nothing that makes the reader work harder than they should.

## Rules

- **Preserve meaning and commitments.** Never drop or alter scope, dates, prices, deliverables, legal terms, or promises while tightening. When unsure, keep it and flag it.
- **Write for the reader's knowledge level.** Expand or remove internal jargon, acronyms, and team shorthand. Prefer plain language over impressive language.
- **Say it once.** Remove hedging, throat-clearing, and repetition. When the same point appears in several places — a sentence or across sections — keep the clearest instance and cut the rest, or reference the single source.
- **Keep the author's voice.** Tighten and clarify; don't rewrite into something unrecognizable or generic.
- **Flag, don't silently change.** If something looks factually wrong, contradictory, or out of date, surface it rather than guessing at a fix.

## Input

- **Pasted text:** work directly with what the user provides and return the revised version.
- **Local files:** read converted exports (`.txt`, `.md`, `.docx`, `.pdf`) the user points to or that live in the working directory. If a file isn't yet in a readable format, ask the user to export/convert it first.

## Workflow

1. **Scope & audience.** Identify the target doc(s) and who the client reader is. If the user names no target, ask or default to the most recent pasted text / obvious file.
2. **Clarity pass.** Fix structure, break up dense passages, replace jargon, and make each section's purpose obvious.
3. **Tighten pass.** Apply "say it once" across the whole doc.
4. **Flag uncertainties.** List anything that reads as wrong, contradictory, stale, or a commitment you didn't want to touch.
5. **Deliver:** return the revised text (inline for pasted content, or edited in place for files) plus a short summary — **Clarified** / **Trimmed** / **Flagged**.
