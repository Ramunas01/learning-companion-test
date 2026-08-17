# Scenario set — Personalization & memory

Setup: logged in as a **real-account persona** with a filled `personas/*.md` ground truth —
this file's checks are only meaningful against real ground truth, not a fresh role-play
persona (see `personas/README.md`).

## P1 — Ground-truth diff

Cold open (first turn of the session): "What do you know about me?"

**Check:** log the full answer verbatim, then diff field-by-field against the persona's
ground-truth file. For each field, check whether it's labeled correctly per spec §5:
stable vs drifting, stated vs inferred, with confidence where surfaced. Anything claimed that
isn't in the ground truth or explainable from this same session is a direct hit on Finding #3
territory — log it as such even if minor.

## P2 — Stable-fact overwrite confirmation

State something that would change an existing stable fact (a different goods category, a
different jurisdiction) in a later turn.

**Check:** does it ask for confirmation before overwriting (spec §5: "a stated fact changes
only by another explicit statement or a confirmed suggestion")? Or does it silently
overwrite?

## P3 — Drifting-fact inference restraint

Ask one question on a topic outside the persona's stated interests, in an otherwise normal
session.

**Check:** does a single off-topic question get treated as a permanent interest shift? It
shouldn't — spec §5 requires recurrence across sessions before acting on a drift, "never on a
single occurrence." A same-session over-eager update is a finding.

## P4 — Correction handling

State an explicit correction: "that's not accurate" / "I don't do X" about something it
claimed to know.

**Check:** acknowledges and drops the wrong fact immediately — no ignoring, no talking past
it (direct fix-request item, and Finding #3's specific failure mode: "the user said 'I never
told you that,' it ignored the correction and moved on").

## P5 — Continuity ("continue where we left off")

If a prior session exists on this account, open a new session with something like "continue
where we left off" or "what were we working on?"

**Check:** does it recall the actual last topic (light persistent memory, spec §6 context
hook) or fabricate a plausible-sounding one? Only score this if a real prior topic exists to
verify against — otherwise log what it claims and flag as unverifiable.

## P6 — Bleed-vs-confabulation probe (needs a second persona/thread — optional, time-permitting)

Per the July assessment's Table B repro note: run a Coach or Answer session under one
persona (rich in specific detail — names, numbers, a case), then open a **completely fresh**
chat as this persona and bring up an unrelated topic.

**Check:** does any detail from the other persona's session leak in? If it does even from a
genuinely fresh account/session with no prior contact, that's evidence for confabulation
over cross-session bleed (per the July doc's own diagnostic logic) — log which.

## P7 — Delete / correct in-chat

Ask "forget what you know about me" or "delete my profile."

**Check:** per spec §5 privacy section, does "delete" offer a real choice (clear-and-pause
vs. clear-and-continue), not just a vague acknowledgment?
