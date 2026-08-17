# learning-companion-test

Black-box test track for the **Learning Companion** — the conversational, RAG-grounded
tutor/assistant on customsclear.net (`/en/ai/assistant`). Sibling effort to
[`sanctioned-entities-testing`](https://github.com/Ramunas01/sanctioned-entities-testing),
which tests the deterministic Sanctions Add-on by census/oracle. This target is different in
kind — a stateful, personalized, multi-mode LLM conversation — so census methodology doesn't
apply. The method here is persona-driven scripted conversations, scored against the
assistant's own written spec and a set of known failure patterns.

## Why this exists

An independent assessment (30 Jul 2026) found the conversational/teaching design strong but
flagged five trust issues: unsupported specifics stated confidently on home-turf topics,
self-classification instead of routing to Classify AI, a possible cross-session memory
bleed, weaker teaching for beginners than experts, and citation hygiene. A fix request went
to engineering. This track is the next test round: check whether the fixes landed, and
extend coverage into what the first assessment didn't reach (Coach mode almost entirely,
Sanctions-AI hand-off, ground-truth-verified personalization accuracy).

## Method

- **Conformance** — does behavior match what the build spec explicitly specifies (mode
  posture, personalization rules, greeting/tier copy, the shared grounding rules)?
- **Trust / adversarial** — does it resist the specific failure patterns the last assessment
  found, plus the permanent regression set the spec itself mandates (§9)?

Both are run as scripted multi-turn conversations against one persona at a time, logged
verbatim, and scored against explicit pass/fail bars — not impression.

## Layout

| Dir | Contents |
|---|---|
| `docs/` | Methodology, hour-by-hour test plan, condensed spec + known-findings reference, scoring rubric |
| `personas/` | Ground-truth profile per test persona — the reference a personalization check diffs against |
| `scenarios/` | Scripted conversation sets, one file per test surface (Answer/Tutor/Coach modes, personalization/memory, boundary routing, access tiers, adversarial grounding) |
| `sessions/` | Raw logged transcripts, one file per run, timestamped |
| `scoring/` | Running scorecard against the rubric, findings write-up |
| `corpus/` | Pointer to the source article corpus used to seed test questions (lives outside this repo — see `corpus/README.md`) |

## Status

Iteration 1: browser-only, single persona (Ramūnas, ground truth in `personas/ramunas.md`),
manual. API interface not yet known — once it is, `scenarios/` scripts become replayable
against an automated harness the same way the Sanctions Add-on track works, rather than by
hand each time.

Working locally: this repo is also cloned at
`/home/ramunas/projects/learning-companion-test` in WSL, alongside the source article corpus
at `/home/ramunas/projects/esperanto-lexicon-corpus` — useful for scenario-writing sessions
that need real corpus topics (see `corpus/README.md`).

See `docs/methodology.md` for the vision, `docs/test-plan.md` for the hour-by-hour plan.
