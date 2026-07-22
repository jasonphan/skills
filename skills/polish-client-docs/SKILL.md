---
name: polish-client-docs
description: >-
  Rewrite client-facing docs so a non-technical reader can skim them without
  effort. Turns buried steps into lists, expands jargon, cuts AI tells and
  filler, and keeps every commitment and the author's voice. Use for proposals,
  SOWs, status updates, reports, decks, or any external prose the user wants
  clarified, tightened, simplified, or made more readable, even if they never
  say "polish". Prefer this over general cleanup when the reader is a client or
  stakeholder. Not for dead-code cleanup or internal eng docs.
---

# Polish Client Docs

Make client-facing writing easy to skim and hard to misread. A busy stakeholder should get the point on the first pass. The result should sound like a careful human wrote it, not a model.

## Non-negotiables

1. **Commitments stay locked.** Do not change scope, dates, prices, deliverables, legal terms, or promises. If something looks wrong or unclear, keep it and flag it.
2. **Meaning stays intact.** Every real claim, caveat, and ask survives. You rearrange and simplify. You do not drop substance.
3. **Voice stays the author's.** Tighten and clarify. Do not flatten into generic corporate speak.
4. **Structure serves the skim.** Steps, options, and parallel items become lists. Dense paragraph chains of process are a failure mode.
5. **The prose looks human.** Apply the `unslop` skill to the revised text before you deliver it.

## What "clear" means here

A client reader should be able to answer these without re-reading:

- What is this about?
- What do you need from me?
- What happens next, and in what order?

If those answers are buried mid-paragraph, restructure until they are obvious.

## Structure rules

These rules drive the rewrite. Language polish comes after structure.

### Steps become numbered lists

If the reader must do things in order, or you are describing a sequence, use a numbered list. Do not leave multiple steps inside one or two sentences ("First... then... after which... once...").

**Weak (steps trapped in prose):**
> To proceed, please approve the SOW, after which we'll provision the environment so your team can begin UAT, and once sign-off is received we'll move to production.

**Strong:**
> Path to launch:
> 1. You approve the statement of work.
> 2. We set up the environment.
> 3. Your team runs user acceptance testing.
> 4. After you sign off, we go to production.

### Options and parallel items become bullets

Choices, deliverables, inclusions, contacts, and other peer items belong in bullets. Do not comma-stack them in a long sentence when a list is clearer.

### One idea per sentence

If a sentence asks the reader to hold more than one action, condition, or date, split it.

### Short paragraphs

Default to 1-3 sentences. Start a new paragraph when the topic shifts. Wall-of-text sections get broken up even when the wording is already plain.

### Lead with the point

Put the ask, decision, date, or outcome first. Context follows. Do not open with throat-clearing ("As discussed previously, following our alignment...").

### Headings that earn their place

Use sentence-case headings that name the section's job ("What we need from you", "Timeline", "What's included"). Drop decorative or vague headings ("Overview", "Next steps" with no content under them).

## Language rules

- Prefer plain words. "Use" beats "leverage". "Help" beats "facilitate". "Start" beats "initiate".
- Expand jargon and acronyms on first use, or replace them when the client does not need the term. "Single sign-on (SSO)" or just "log in with your company account".
- Say it once. Cut hedging, restatement, and filler ("It is important to note that", "In order to").
- Prefer active voice when the actor matters ("We will send the report Friday" not "The report will be sent Friday").
- Keep numbers, names, and dates concrete. Do not round or soften them while polishing.

## Human voice (no AI tells)

After the clarity rewrite, run `unslop` on the result. For client docs, watch these especially hard:

- No em dashes. Use a period or a comma.
- No colon used as a mid-sentence connector. Colons are fine before a list.
- No chatbot closers ("I hope this helps!", "Let me know if you have any questions!" unless the source already used that and the author wants it).
- No inflated filler ("transformative", "synergies", "robust solution", "seamless experience").
- No bold on every noun. Bold sparingly, for true emphasis only.
- Straight quotes, not curly quotes.

The skill file and your reply follow the same voice rules.

## Input

- **Pasted text:** revise and return the revised version.
- **Files:** read the path the user points to (`.md`, `.txt`, and other readable formats). If a file is not readable as text, ask for an export. Edit in place when the user is working from a file.

## Workflow

1. **Scope the reader.** Who is the client reader, and what decision or update is this for? If nothing is named, use the latest pasted text or the obvious file.
2. **Restructure for skim.** Turn sequences into numbered lists, peer items into bullets, split dense sentences, shorten paragraphs, put the point first.
3. **Plain language.** Expand or replace jargon. Cut repetition and filler. Keep commitments exact.
4. **Human pass.** Apply `unslop`. Fix any remaining AI tells.
5. **Commitment check.** Re-read against the source for dates, prices, scope, and promises. Flag anything uncertain instead of guessing.
6. **Deliver.**
   - Revised doc (inline paste, or edit the file).
   - Short note of what changed, in this shape:
     - **Restructured.** Lists, headings, or paragraph breaks you introduced
     - **Clarified.** Jargon or wording you simplified
     - **Flagged.** Anything contradictory, stale, or left untouched on purpose

## Examples

### Jargon and commitments

**Before:**
> We'll leverage the OAuth2 handshake to facilitate SSO via IdP federation, pending sign-off on the SOW. Rollout is targeted for Q3 contingent on resource allocation.

**After:**
> You'll log in with your existing company account (single sign-on). Work starts once you approve the statement of work. We're aiming for a Q3 launch.

### Voice without corporate fog

**Before:**
> We are incredibly excited to partner with you on this transformative initiative that will unlock synergies across your organization.

**After:**
> We're glad to be working with you on this.

### Buried asks

**Before:**
> Per our conversation, and in light of the upcoming board meeting next Thursday, it would be helpful if you could review the attached deck and share feedback on slides 4-7 regarding pricing so we can finalize before the meeting.

**After:**
> Please review slides 4-7 (pricing) and send feedback before Thursday's board meeting so we can finalize the deck.
