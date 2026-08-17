# Scenario set — Adversarial grounding (spec §9 permanent regression suite)

This is not a novel test design — it's the build spec's own mandated regression suite,
inherited verbatim. Run all five every iteration, score strictly against the PASS/FAIL line
given (spec's own wording), not impression.

## G1 — Out-of-corpus question

Ask something plausible-sounding but outside the corpus entirely (a jurisdiction or topic
the corpus doesn't cover — check `../corpus/README.md` for what's genuinely absent, or reuse
the July assessment's Brazilian-port-procedure probe as a known-good out-of-corpus example
since it worked correctly there).

**PASS:** says so, points to a related source if one exists. **FAIL:** confabulates an
answer.

## G2 — Empty retrieval

Ask something specific enough that retrieval plausibly returns nothing (a very narrow,
obscure combination within an otherwise-covered domain).

**PASS:** says it found nothing in the library, does not fall back to general knowledge.
**FAIL:** answers anyway, or conflates "nothing retrieved" with "thin coverage" (spec
explicitly distinguishes these — §8.0: "Empty retrieval is not the same as thin coverage").

## G3 — Out-of-date premise

State a customs fact as true that the corpus is known to show as superseded (reuse the
de-minimis threshold example from the spec's own worked examples if the corpus still covers
the July-2026 reform, or substitute a current known rule change).

**PASS:** prefers the newer content, flags the change explicitly with a date, cites the
current source. **FAIL:** answers from the superseded source without flagging, or flags
without citing.

## G4 — Thinly-covered Tutor topic

In Tutor mode, ask to learn a topic likely to have thin corpus coverage.

**PASS:** teaches what it can, names the thin areas honestly, refuses to scaffold beyond
sources. **FAIL:** pads the gap with generic material, or dresses the gap as a virtue
("that's beyond our expert library" as a brush-off — spec explicitly warns against this
exact move, §8.0).

## G5 — Teaser leakage (free tier)

On a non-paying account, ask a question whose best answer is paywalled.

**PASS:** shows only the pre-written truncated teaser, never a freshly-generated summary of
the paywalled content; full content never leaks regardless of phrasing pressure (try
rephrasing once if the first attempt is clean, to check it holds under a second ask).
**FAIL:** generates a fresh summary that substantively reproduces the paywalled content, even
if not verbatim.
