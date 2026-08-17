# Methodology

## What kind of thing we're testing

The Learning Companion is not a lookup tool with a right answer per query — it's a stateful,
personalized, multi-mode conversation. "Does it work" isn't a single measurable property the
way "does the matcher find this sanctioned entity" is. So the method here is different from
the census/oracle approach used for the Sanctions Add-on in the sibling
`sanctioned-entities-testing` repo:

- No ground-truth answer key to diff against for most turns.
- The thing under test is *behavior across a conversation*, not a single request/response.
- The spec (`LearningCompanion_Build_Spec.docx`) is unusually explicit for a prompt spec — it
  states PASS/FAIL bars for two worked examples and names five adversarial scenarios that
  "must pass before v1 ships" (§9). That gives us something firmer than impression to score
  against: **the assistant's own written contract**, not our own taste.

So the method is: scripted, persona-driven, multi-turn conversations, logged verbatim, scored
against explicit criteria pulled from the spec plus a second set pulled from the last
assessment's confirmed failure patterns. Two axes:

### 1. Conformance — does it do what the spec says?

Pulled directly from the build spec: mode posture (Answer = fast/no preamble, Tutor =
diagnose-then-teach, Coach = Socratic/no conclusions-supplied), the shared grounding rules
(corpus-only, cite every claim, flag recency), personalization capture rules (stable facts
confirmed before overwrite, drifting facts inferred quietly, nothing persisted before
consent), greeting/ending copy (register, length, rotation, tier nudges), access-tier
behavior (teaser not full content, cap messaging).

### 2. Trust / adversarial — does it resist known failure modes?

Two sources feed this:
- The spec's own §9 adversarial set (out-of-corpus, empty retrieval, out-of-date premise,
  thin-topic honesty, teaser leakage) — a **permanent regression suite** per the spec, meant
  to be re-run after every change. We inherit it rather than reinvent it.
- The 30 Jul assessment's five confirmed findings (confident fabrication on home-turf
  topics, self-classification instead of routing, a suspected memory bleed/confabulation,
  weaker teaching for beginners, citation-format mismatches). These are known bugs with a fix
  request already filed — this round's job on those five is **regression testing**: did the
  fix land, or does the same pattern reproduce.

## What's genuinely new in this round (not just repeating the last assessment)

- **Coach mode** was barely touched by the first assessment (one worked example in the spec,
  zero scenarios in the actual test run). It's the mode most likely to hide problems, because
  its "mostly Socratic, but must catch a false premise via background retrieval" design
  (spec §8.4, confirmed dependency in §10) is the most fragile-sounding mechanism in the whole
  spec — background retrieval firing silently during a conversation that's nominally
  question-only.
- **Sanctions AI hand-off** was never tested at all. Given this repo's existing focus, it's an
  easy and directly relevant boundary-routing check: does a sanctions-adjacent question in
  Learning Companion route out, the way classification questions are supposed to route to
  Classify AI (spec fix "Stop it doing the tools' jobs")?
- **Ground-truth-verified personalization.** The first assessment could observe *symptoms*
  of memory problems (a stated fact contradicted) but couldn't verify *accuracy* — it had no
  independent record of what the platform actually knows about a persona. We have that: a
  persona's real profile file is the ground truth a "what do you know about me?" turn gets
  diffed against, field by field, each labeled stable/drifting/stated/inferred per the spec's
  own taxonomy (§5). This is the one check this round can do that the first assessment
  structurally couldn't.
- **Bilingual conformance.** Lithuanian phrasing wasn't assessed at all in the July round.

## Multi-iteration structure

Ten hours is one persona's *breadth* pass — one pass through every mode and cross-cutting
concern, not statistical confidence on any one of them (same caveat the first assessment
gave itself: "a strong hypothesis generator, not a statistical evaluation"). Depth and
regression-over-time need repeat personas:

- **Iteration 1** (this one): single persona (Ramūnas), manual browser testing, full breadth
  across modes + cross-cutting concerns. Produces a scored findings doc in the same format as
  the July assessment, so the two are directly comparable.
- **Iteration 2+**: additional personas (deliberately contrasting — different role,
  jurisdiction, experience level, language) to probe the beginner-vs-expert asymmetry
  (Finding #4) and jurisdiction-aware answers more directly, and to re-run the regression set
  fresh (a scenario the assistant has "seen" once in this account may behave differently the
  second time — worth noting if so). Once the API is known, the adversarial/conformance
  scripts in `scenarios/` become replayable as an automated harness, the same shape as the
  Sanctions Add-on track: fixed inputs, captured raw responses, scored output.

## Persona ground rules

- Role-play stays in character for the full session — a persona is defined once in
  `personas/`, not adjusted mid-conversation to fish for a particular failure.
  Only exception: the spec's own worked examples and the assessment's reproducibility pack
  script specific pressure moments ("can you just tell me yes or no") — those are fair game
  because they test a named, specified behavior (posture under pressure), not a trick.
- Every session starts from a stated, logged account state (fresh chat vs continuing thread;
  logged in vs not; which persona) — reproducibility depends on this being explicit, the same
  discipline the assessment doc asked engineering to reciprocate with log access.
- Score against the spec's stated bar, not against what would be nice to have. Where the spec
  is silent, say so rather than inventing a bar (mirrors the assessment's "confirmed vs
  suspected" discipline).
