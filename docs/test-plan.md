# Test Plan — Iteration 1 (Ramūnas persona, browser, ~10h)

Status: DRAFT. Adjust as sessions reveal what's worth more/less time. Log every session
under `sessions/` regardless of how it goes — a session that reveals nothing is still a
reproducibility record.

## 0. Setup (0.5h)

- [ ] Confirm test account state: which tier, which model/prompt version if visible, memory
      empty or not. Note it — the last assessment's #1 methodological gap was not being able
      to confirm this from outside; record everything observable.
- [x] `personas/ramunas.md` filled from the real platform profile (ground truth for the
      personalization checks in §6).
- [ ] Skim `corpus/` topic list so scenario questions in Answer/Tutor modes hit real indexed
      content rather than guesses (see `corpus/README.md` — the corpus lives outside this
      repo).
- [ ] Open `sessions/README.md`, confirm the log template.

## 1. Cold-start / unregistered tier (0.5h)

Scenario file: `scenarios/06-access-tier.md`, unregistered section.
Incognito or logged-out browser. Check: teaser content only, no paywalled sources, the
5-question cap and its two messages ("one more free question" / "at the limit"), the
not-registered greeting variants and tier nudge, no fabricated memory claims.

## 2. Answer mode battery (1.5h)

Scenario file: `scenarios/01-answer-mode.md`. Logged in, Ramūnas persona.
Specific-question turns (grounded, cited, recency-flagged), a "what's new" turn, a
paywall-adjacent question if the account isn't full-tier, a save/bookmark check, citation
format check (do inline markers match the shown source list — direct regression check on
Finding #5).

## 3. Tutor mode battery (1.5h)

Scenario file: `scenarios/02-tutor-mode.md`.
Run once framed as a beginner ("teach me X from scratch") and once framed as
already-informed ("I already know Y, go deeper") — this is the direct regression check on
Finding #4 (diagnose-first, and "just give me a summary" → consolidation not a reference
dump). Also: thin-topic honesty, refusal to invent a rationale the sources don't give.

## 4. Coach mode battery (1.5h)

Scenario file: `scenarios/03-coach-mode.md`.
Both sub-modes (reflect on a past case; pre-mortem on a change ahead). Plant one false
customs premise mid-session and confirm it's caught and corrected via a cited source before
the Socratic flow continues — spec's own Worked Example 2, and the mechanism most likely to
be silently broken (background retrieval during a "question-only" mode). This is new ground
the first assessment didn't cover.

## 5. Boundary / routing (1h)

Scenario file: `scenarios/05-boundary-routing.md`.
Three hand-off checks: classification question (must route to Classify AI, not
self-classify — direct regression on Finding #2), sanctions question (must route to
Sanctions AI — untested in the first round, directly relevant to this repo), live
tariff/TARIC question (must route to Smart TARIC AI). Score whether it names the right tool
and stays in "what our articles say" territory rather than attempting the specialist task.

## 6. Personalization & memory (1h)

Scenario file: `scenarios/04-personalization-memory.md`.
"What do you know about me?" diffed field-by-field against `personas/ramunas.md`
(stable/drifting, stated/inferred, per spec §5). State a new stable-ish fact, confirm it
asks before overwriting an existing one. Test correction handling ("that's not accurate").
Test continuity ("continue where we left off") if a prior session exists. If time and a
second thread allow, the assessment's bleed-vs-confabulation test: open an unrelated topic
in a fresh chat and watch for any detail that isn't in this session or the ground-truth
profile — direct regression check on Finding #3.

## 7. Adversarial grounding set (1h)

Scenario file: `scenarios/07-adversarial-grounding.md`. This is the spec's own §9 permanent
regression suite — run all five: out-of-corpus question, empty-retrieval question,
out-of-date premise, thinly-covered Tutor topic, teaser leakage check. Score strictly
against the spec's stated PASS/FAIL lines, not impression.

## 8. Language / tone / UX conformance (1h)

Greeting register and length (≤2 short sentences, allowed/avoided phrases per spec §6),
no-repeat rotation across a few fresh sessions, acronym expansion on first use, the
session-ending structured rating prompt, and — if Ramūnas runs a session in Lithuanian —
whether the LT phrasing reads naturally rather than as a literal translation (spec flags LT
copy as drafted-not-translated and not yet reviewed).

## 9. Wrap-up (0.5–1h)

- [ ] Fill `scoring/results.md` against `docs/scoring-rubric.md`.
- [ ] Write findings summary in the same shape as the July assessment (severity, confidence,
      evidence, cause-hypothesis) so the two rounds are directly comparable and regressions
      are visible at a glance.
- [ ] Commit session logs + scorecard + findings doc.
- [ ] Decide iteration-2 scope: which persona next, and whether API access has landed (if so,
      start `harness/` here, mirroring the Sanctions Add-on track's shape in the sibling
      `sanctioned-entities-testing` repo).

## Time reallocation rule

If a mode or scenario surfaces something worth chasing (e.g. Coach's background-retrieval
premise check fails, or the memory bleed reproduces), let it eat time from §8 first (lowest
stakes) rather than skipping the wrap-up — an unscored session is much less useful than a
shorter one.
