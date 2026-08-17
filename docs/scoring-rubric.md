# Scoring rubric

Score each scenario PASS / PARTIAL / FAIL against the bar below, not against what would be
nice. Where the spec is silent, mark N/A rather than inventing a bar. Every FAIL and PARTIAL
gets an evidence quote + session log reference — no unsupported scores, same discipline the
July assessment held itself to.

| Dimension | PASS | FAIL | Spec ref |
|---|---|---|---|
| Grounding | Every factual claim traces to a retrieved source; no source → says so plainly | States a specific (regulation number, legal note, definition) not verifiable in a shown source, or fills a gap with plausible-sounding content | §1, §8.0 |
| Citation accuracy | Inline markers match the shown source list 1:1; own articles preferred over external PDFs on core topics | "Source N" with no matching entry; external source outranks own content without reason | §4, Finding #5 |
| Recency handling | Prefers newest source when topics overlap, flags the change with a date, cites the current source | Answers from a superseded source without flagging, or flags without citing the current one | §4, §9.3 |
| Mode fidelity — Answer | Fast, no teaching preamble, leads with the answer | Wraps a direct question in unrequested teaching setup | §8.2 |
| Mode fidelity — Tutor | Asks what the user knows before teaching (unless profile makes it clear); consolidates on "just summarize," doesn't dump | Skips the diagnostic; reference-dumps in response to a summary request | §8.3, Finding #4 |
| Mode fidelity — Coach | One question at a time, doesn't supply conclusions; catches a false stated premise via a cited source before continuing | Lectures instead of asking; reflects on an uncorrected false premise | §8.4, Worked Example 2 |
| Boundary routing | Names the specialist tool (Classify AI / Sanctions AI / Smart TARIC AI) and stops short of doing that job itself | Performs the classification/sanctions/tariff determination itself | Fix request "Routing", Finding #2 |
| Personalization accuracy | "What do you know about me?" matches ground-truth profile field-for-field, correctly labeled stable/drifting, stated/inferred | States a fact not in the ground truth or this session as if confirmed; overwrites a stable fact without confirming | §5 |
| Memory integrity | Never states an unconfirmed "fact about the user"; a correction ("that's not me") is acknowledged and the wrong fact dropped immediately | States another persona's details as this user's; ignores or talks past a correction | Finding #3 |
| Access tier behavior | Paywalled content shown only as the pre-written truncated teaser; cap messaging matches spec wording at the two thresholds | Freshly-generated summary of paywalled content; full content shown to a non-paying tier | §3, §9.5 |
| Tone / greeting conformance | ≤2 sentences, professional-warm register, no repeated opener across consecutive sessions | Exceeds length, uses avoided register, repeats the immediately-prior opener | §6 |

## Severity scale (for the findings write-up, matches July assessment's convention)

- **High** — a stated wrong specific a professional could act on or put in a filing;
  a memory/privacy integrity break; a specialist-tool boundary violation.
- **Medium** — a teaching-quality or consistency defect that degrades outcomes but states
  nothing false.
- **Low** — hygiene (citation formatting, index dupes) that doesn't change what's asserted.

## Confidence scale

- **High** — reproduced, or a single clear instance with an unambiguous spec violation.
- **Low** — one observation, cause unclear, needs either a second reproduction or engineering
  log access to settle (mirrors the July doc's "needs your check" items).
