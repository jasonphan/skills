---
name: polish-client-docs
description: >-
  Use this skill when polishing client-facing or stakeholder prose so a
  non-technical reader can skim it without effort. Trigger for proposals, SOWs,
  status updates, reports, decks, or any external writing the user wants
  clarified, tightened, simplified, or made more readable, even if they never
  say "polish". Prefer this over general cleanup when the audience is a client
  or stakeholder. Use declutter for dead/redundant docs or tight rewrites that
  are not client-facing.
---

# Polish Client Docs

Make client-facing writing easy to skim and hard to misread. A busy stakeholder should get the point on the first pass. Cut what repeats. Order what remains so the logic is obvious. The result should sound like a careful human wrote it, not a model.

This skill is for stakeholder skim and locked commercial meaning. For dead docs, unused code comments, or tightening internal prose without client-doc structure, use declutter instead.

## Non-negotiables

1. **Commitments stay locked.** Do not change scope, dates, prices, deliverables, legal terms, or promises. If something looks wrong or unclear, keep it and flag it.
2. **Meaning stays intact.** Every distinct claim, caveat, and ask survives. Duplicate restatements of the same point do not. You rearrange, dedupe, and simplify. You do not drop substance.
3. **Voice stays the author's.** Tighten and clarify. Do not flatten into generic corporate speak.
4. **Structure serves the skim.** Steps, options, and parallel items become lists. Dense paragraph chains of process are a failure mode.
5. **Flow makes sense.** Sections and paragraphs follow a logic the reader can track without jumping around.
6. **The prose looks human.** Follow **Human voice** below. Keep voice cleanup inside this skill so the rewrite stays consistent.

## What "clear" means here

A client reader should be able to answer these without re-reading:

- What is this about?
- What do you need from me?
- What happens next, and in what order?

If those answers are buried mid-paragraph, repeated in three places, or arrive out of order, restructure until they are obvious.

## Structure rules

Cut redundancy and fix order before you polish wording. Structure does more for skim than word choice.

### Steps become numbered lists

If the reader must do things in order, or you are describing a sequence, use a numbered list. Do not leave multiple steps inside one or two sentences ("First... then... after which... once...").

**Weak (steps trapped in prose):**
> To proceed, please approve the SOW, after which we'll provision the environment so your team can begin UAT, and once sign-off is received we'll move to production.

**Strong:**
> Path to launch:
>
> 1. You approve the statement of work.
> 2. We set up the environment.
> 3. Your team runs user acceptance testing.
> 4. After you sign off, we go to production.

### Options and parallel items become bullets

Choices, deliverables, inclusions, contacts, and other peer items belong in bullets. Do not comma-stack them in a long sentence when a list is clearer.

### One idea per sentence

If a sentence asks the reader to hold more than one action, condition, or date, split it.

### Short paragraphs

Default to 1-3 sentences. Start a new paragraph when the topic shifts.

### Lead with the point

Put the ask, decision, date, or outcome first. Context follows. Do not open with throat-clearing ("As discussed previously, following our alignment...").

### Headings that earn their place

Use sentence-case headings that name the section's job ("What we need from you", "Timeline", "What's included"). Drop decorative or vague headings ("Overview", "Next steps" with no content under them).

### Cut repeats, keep distinct points

Same fact, ask, or caveat twice → keep the strongest instance. Opening or closing that only restates what follows or came before → cut it. Do not fuse two different commitments into one vague sentence.

### Order for logical flow

Put the ask where the reader will see it before the detail. A common shape is: why this exists → ask → details → timeline → risks → how to reply. Adjust when the doc type demands it (timeline-first status update, contiguous legal block).

Within a section, put cause before effect, prerequisite before step, and decision before justification. Merge sections that cover the same thread. Flag chronological or causal contradictions instead of inventing an order that papers over them.

## Language rules

- Expand jargon and acronyms on first use, or replace them when the client does not need the term. "Single sign-on (SSO)" or just "log in with your company account".
- Cut hedging and filler ("It is important to note that", "In order to") so the ask is not buried.
- Prefer active voice when the actor matters. Keep numbers, names, and dates concrete; do not round or soften them while polishing.

## Human voice (no AI tells)

After the clarity rewrite, make the prose sound like a careful human wrote it:

- No em dashes (period or comma). Colons only before lists, not as mid-sentence connectors.
- No chatbot closers unless the source already used them and the author wants them kept.
- No inflated filler ("transformative", "synergies", "robust solution", "seamless experience", "leverage", "utilize").
- No "It's not just X, it's Y". State the point directly.
- Bold sparingly. Straight quotes. Vary sentence length a little so the rhythm does not read as generated.

The skill file and your reply follow the same voice rules.

## Input

- **Pasted text:** revise and return the revised version.
- **Files:** read the path the user points to (`.md`, `.txt`, and other readable formats). If a file is not readable as text, ask for an export. Edit in place when the user is working from a file.

## Workflow

1. **Scope the reader.** Who is the client reader, and what decision or update is this for? If nothing is named, use the latest pasted text or the obvious file.
2. **Cut redundancy.** Keep the strongest instance of each repeated fact, ask, or caveat. Drop pure restatement.
3. **Fix flow.** Reorder so the logic is easy to follow. Merge split threads. Keep prerequisites before dependent steps.
4. **Restructure for skim.** Numbered lists for sequences, bullets for peers, split dense sentences, short paragraphs, point first.
5. **Clarify wording.** Expand or replace jargon. Cut filler. Keep commitments exact.
6. **Human pass.** Apply **Human voice**.
7. **Commitment check.** Re-read against the source for dates, prices, scope, and promises. Confirm you did not drop a distinct point while deduping. Flag anything uncertain instead of guessing.
8. **Deliver.**
   - Revised doc (inline paste, or edit the file).
   - Short note of what changed, in this shape:
     - **Removed.** Redundant restatements you cut
     - **Reordered.** Flow fixes (what moved where, and why in one short phrase)
     - **Restructured.** Lists, headings, or paragraph breaks you introduced
     - **Clarified.** Jargon or wording you simplified
     - **Flagged.** Anything contradictory, stale, or left untouched on purpose

## Examples

### Jargon and commitments

**Before:**
> We'll leverage the OAuth2 handshake to facilitate SSO via IdP federation, pending sign-off on the SOW. Rollout is targeted for Q3 contingent on resource allocation.

**After:**
> You'll log in with your existing company account (single sign-on). Work starts once you approve the statement of work. We're aiming for a Q3 launch.

### Buried asks

**Before:**
> Per our conversation, and in light of the upcoming board meeting next Thursday, it would be helpful if you could review the attached deck and share feedback on slides 4-7 regarding pricing so we can finalize before the meeting.

**After:**
> Please review slides 4-7 (pricing) and send feedback before Thursday's board meeting so we can finalize the deck.

### Redundancy and flow

**Before:**
> As a next step we need your feedback on pricing. Also attached is background on the project history for context. Please send pricing feedback on slides 4-7. Timeline-wise, the board meets Thursday, so feedback before then helps. Project background: we started discovery in January and aligned on scope in March.

**After:**
> Please send feedback on slides 4-7 (pricing) before Thursday's board meeting.
>
> Background: discovery started in January. We aligned on scope in March.
