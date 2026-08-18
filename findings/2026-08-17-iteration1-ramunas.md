# Learning Companion — Iteration 1 Findings (Ramūnas persona)

To: Šarūnas (CTO) · cc: Enrika
From: Ramūnas (testing), with an assisting Claude session
Date: 17 August 2026
Re: Structured re-test against the 30 July assessment's findings and fix request

## Test conditions

Assistant tested: the live web assistant at customsclear.net/en/ai/assistant, logged in as
Ramūnas's real account, 17 August 2026. Account state: logged in; tier shown in the UI as a
**"member"** tag — this doesn't obviously match the ground-truth profile's "Paying" status
recorded from the platform side (`personas/ramunas.md`), and wasn't resolved during testing.
Worth confirming before scoring the paywall/teaser scenarios in a later round. Model/prompt
version not visible from the user side, same limitation the July assessment flagged.

Method: 9 scripted, persona-driven conversations across grounding, boundary-routing,
personalization/memory, Tutor mode, and Coach mode, logged verbatim in `sessions/`, scored
against `docs/scoring-rubric.md`. Full methodology in `docs/methodology.md`. This inherits the
July assessment's own discipline: score against the spec's stated bar, log confirmed vs.
suspected separately, and correct the record in place rather than deleting a wrong read — one
finding in this round (see P1/P4) was initially overstated and corrected after Ramūnas's own
input, the same "confirmed vs suspected" standard the July doc set for itself.

## What's already strong (still true, protect these)

Everything the July assessment praised held up, plus one major new positive result:

- **Coach mode's premise-check works.** This is new ground — the July assessment barely
  touched Coach mode, and `docs/methodology.md` flagged the background-retrieval-during-a-
  question-led-mode mechanism as the most fragile-sounding one in the whole spec. It isn't
  broken: a false €150 EU de-minimis premise was caught and corrected *before* any of the
  requested analysis began, with real citations, and the session stayed properly Socratic
  throughout — including pushing back constructively when the user tried to close early.
  Closed with an accurate summary of the user's own conclusions. See `sessions/2026-08-17-
  ramunas-coach-mode-c3.md`.
- **Sanctions and tariff/TARIC boundary routing both work cleanly.** Both name the specialist
  tool and correctly stop at general framework/process information rather than making a
  case-specific determination. See `sessions/2026-08-17-ramunas-boundary-routing-b2.md` and
  `-b3.md`.
- **In-conversation Tutor teaching quality is genuinely good** once past the diagnostic gap
  (see below) — one question at a time, confirms answers, builds concepts incrementally
  rather than lecturing. Consistent with the July assessment's praise for Socratic teaching.
- **Citation quality is strong when it's good** — several sessions (Coach C3, Tutor T1 before
  the summary request, sanctions B2, tariff B3) showed inline attributions that matched real,
  topically relevant sources exactly.

## What needs attention

### 1. Classification boundary routing is fixed only at the surface — High severity, High confidence
`sessions/2026-08-17-ramunas-boundary-routing-b1.md`

Asked to classify a solar inverter (8502 vs 8504), the assistant now says "use Classify AI"
with a working link — the July fix landed at that level. But it then continues anyway,
asserting a firm directional classification ("points firmly to Chapter 85 / heading 8504...
8504 40 84") with a precise citation before ever pointing to Classify AI's output. A shallow
regression check ("does it mention Classify AI?") would score this a clean PASS; it isn't one.
Compounding this: 3 of the 4 "sources checked" were irrelevant (a duplicate Belarus-sanctions
regulation entry under two different dates, and an EU–Mercosur trade agreement) — the same
category of noise as July's Finding 1a, which also surfaced an irrelevant Mercosur citation.
Given the sanctions and tariff routing paths (B2, B3) handle this correctly — name the tool,
stop at framework information — this looks like a bug specific to the classification code
path, not a general routing failure. That's a useful, narrow scope for the fix.

### 2. Tutor mode's beginner path reproduces Finding #4, and the summary-dump half is worse — Medium-High severity, High confidence
`sessions/2026-08-17-ramunas-tutor-mode-t1.md`

Asked to learn rules of origin "from the basics" as a self-declared beginner — nearly the
exact wording of the build spec's own worked marketing example, which explicitly shows the
assistant asking a diagnostic question first — the assistant skipped straight to teaching.
Then, asked for "a one-page summary" under time pressure, it produced a 13-source reference
manual: a 5-agreement document table with 2025/2026 regime dates, a named court case, a named
sanctions rule, IEEPA tariff detail, and an 8-item checklist — none of it discussed, and going
well beyond what July's own example described. It also fully answered the in-progress Socratic
question instead of leaving it as a working point. The teaching quality itself, before the
summary request, was genuinely strong — this is specifically about the diagnostic-skip and the
consolidation failure, not a general teaching-quality problem.

### 3. Chat-derived personalization can assert unconfirmed facts, including under its own citation — Severity unresolved (was High, corrected to unresolved), confidence Low-Medium
`sessions/2026-08-17-ramunas-personalization-memory-p1.md`

In a fresh chat, "what do you know about me?" surfaced a detailed Rotterdam-free-zone /
CN 2404 business scenario, two items labeled `[stated]`. **Important correction, made during
testing:** Ramūnas has tested this assistant occasionally over past months, so this content
may be genuine memory from an earlier real session rather than invention — it can't be
confirmed or ruled out without account chat-history access, and this write-up deliberately
downgrades the original "confirmed fabrication" read to reflect that, the same discipline the
July assessment applied to its own Finding #3. Two things stand regardless of that outcome:
(a) pushed on "where did that come from," the assistant cited "notes from coaching sessions
dated 2026-07-22" whose "sources checked" were four entirely unrelated articles (a transit
manual, a CJEU case, a sanctions piece, a news digest) — the citation shown doesn't support
the provenance claim made, true or not; (b) an explicit "delete this entirely" request got a
"clean slate" reply that still retained a reference to the disputed fact, reframed as
user-retracted rather than removed. **Recommended next step, achievable in one query:** check
the account's actual chat history for a session on or before 2026-07-22 mentioning a Rotterdam
/ CN 2404 scenario. That single check resolves the open question definitively.

### 4. Citation hygiene — Low severity, High confidence, reproducing
`sessions/2026-08-17-ramunas-adversarial-grounding-g3.md` (both turns), `-b1.md`

Answer-mode turns sometimes carry zero inline citation markers despite specific dated claims
(worse than July's mismatched-marker version of this problem). One instance of a dangling,
apparently-failed citation insertion ("a companion piece — the article — covers..."). The
duplicate-regulation-under-two-dates pattern from July's Finding #5 reproduced again in B1.

### 5. Possible latency issue on personalization-read queries — unconfirmed, one instance
`sessions/2026-08-17-ramunas-personalization-memory-p1.md`

One "what do you know about me?" query hung at "..." for 100+ seconds with no response,
against a normal ~15-25s for other query types; unreproduced on retry in a second fresh chat.
Noted as a single data point, not a confirmed pattern.

## Corroborating note on July's Finding #1c

The Coach-mode session (finding #1 above the fold, in the "what's strong" section) cited
"Implementing Regulation (EU) 2026/1200, published 8 June 2026" — the *exact* regulation
number and date July's Finding #1c flagged as unverified. Reproducing identically across two
independent sessions, weeks apart, is meaningful evidence toward "true but uncited" rather
than fabricated, though a customs author checking the actual OJ listing would settle it
definitively. Worth updating the July doc's verification queue (Table D) with this.

## Bottom line

Two of three specialist-tool hand-offs (sanctions, tariff) now work correctly; classification
does not, despite surface-level compliance with the fix request. Coach mode's core mechanism —
untested in July — works well and is a genuine strength worth protecting. Tutor mode's
diagnostic-first and consolidate-on-request behaviors from Finding #4 still don't fire, and the
consolidation failure is more severe than the July baseline. The personalization/memory
finding that looked like this round's headline result turned out to need a correction the
tester supplied himself — a useful reminder that "confirmed vs. suspected" discipline has to
be applied to *this* round's findings too, not just carried forward as a label from July.

## Addendum — 2026-08-18 (adversarial regression set, G1/G2/G4)

Three more items from the spec's own permanent regression suite, same persona, same account.
Full logs: `sessions/2026-08-18-ramunas-adversarial-g1-g2.md`, `-g4.md`.

- **G1 (out-of-corpus): PASS, clean.** Asked a South Korea-specific customs procedure
  question, the assistant stated plainly it's out of scope, named the actual boundary
  (EU/UCC-focused sources), and redirected to the real external authority (Korea Customs
  Service) rather than guessing.
- **G2 (empty retrieval): core behavior PASS, but surfaced a reinforcing finding.** A
  deliberately unrelated question (sourdough starter) was correctly declined — but the corpus
  turned out to hold a genuinely on-topic source (an EU "classification of certain goods"
  regulation), so this wasn't a true empty-retrieval case. What it revealed instead: the
  assistant **volunteered an unprompted, unhedged CN classification** (code 2106 90 98) with
  no Classify AI pointer and no "directional, not binding" framing — on a query that wasn't
  about classification at all. This is a third independent data point on the classification
  self-determination finding from 17 August (`sessions/2026-08-17-ramunas-boundary-routing-
  b1.md`), and a stronger one: the behavior fires even when classification content is merely
  adjacent to the topic, not just when a user directly asks for it.
- **G4 (thin-topic Tutor): PASS, and a genuinely strong example.** Asked to learn NCTS
  guarantee-waiver conditions in depth, the assistant precisely distinguished what its sources
  cover (the waiver's existence as a named simplification) from what they don't (the actual
  qualifying conditions, cross-referenced to a Transit Manual section it doesn't have), cited
  a specific section for what it does have, and explicitly said it wouldn't fill the gap with
  general knowledge. It also asked the diagnostic "how familiar are you with X" question before
  teaching — worth flagging as a direct contrast with 17 August's T1 session, which skipped
  that same step on a different topic. Open, testable hypothesis for engineering: does the
  diagnostic-question step correlate with topic thinness?

These three don't change the bottom line above, but they sharpen it: the classification
self-determination issue is broader than initially scoped (fires unprompted, not just on
direct classification requests), and thin-topic honesty — a dimension the July assessment
praised in general — continues to hold up under a harder, more specific test than July ran.

## Addendum — 2026-08-19 (re-profiled beginner persona — the standout result of the whole effort)

Ramūnas replaced his own profile text on the platform, deliberately changing only experience
level (genuine beginner, no stated business or sanctions specialization) while holding
jurisdiction, tone, and access tier constant against the 17 August persona. Full log:
`sessions/2026-08-19-ramunas-beginner-tutor-t1-memory-bleed.md`.

**Finding #4 (diagnostic-skip), now unambiguous.** Asked to learn tariff classification "from
the basics" as a genuine beginner with no stated expertise anywhere in the profile, the
assistant again skipped the diagnostic question and taught immediately. 17 August's version of
this finding required picking a topic outside the persona's stated interests to stay honest to
a "beginner framing on an otherwise expert profile" — that judgment call is no longer needed.
This is as clean a confirmation as the test can produce.

**New finding, arguably the most important of the whole effort: confirmed, self-admitted
cross-session memory bleed.** Mid-lesson, the assistant stated as fact that the user is
"shipping e-commerce parcels into the EU with 3–4 product types per consignment." That exact
detail is verbatim from a *different* test session run the day before, against the *old*
expert persona, in an unrelated Coach-mode pricing exercise
(`sessions/2026-08-17-ramunas-coach-mode-c3.md`) — nothing resembling it exists anywhere in the
new profile or in this conversation. Challenged directly, the assistant's own explanation
confirmed the mechanism: **"I was pulling in context from earlier conversations that isn't
relevant right now."** This resolves 17 August's open P6 question (bleed vs. confabulation,
which that day's findings could only leave as "needs account chat-history access to settle")
in the direction Ramūnas himself suspected for the Rotterdam finding: this is real
prior-session content, misapplied to a context it has nothing to do with — not invention from
nothing. It also demonstrates that changing the platform-side profile text does **not**
reconcile or reset whatever store holds chat-derived conversational context; stale, wrong
content from a fully separate scenario surfaced unprompted and stated as settled fact rather
than offered tentatively.

**One genuine improvement, worth stating plainly alongside the severe finding:** correction
handling here was clean. Challenged, the assistant acknowledged immediately ("Fair point... I
was pulling in context that isn't relevant"), didn't argue, and didn't fabricate a justifying
provenance story — a real contrast with 17 August's escalation pattern (inventing "coaching
sessions dated 2026-07-22" when pushed on the Rotterdam claim). The problem is specifically
what gets surfaced unprompted, not how the system responds once challenged.

**Latency issue upgraded from single data point to confirmed pattern.** A second, independent
"what do you know about me?" query stalled with no response for 70+ seconds — same signature
as 17 August's Attempt 1. Worth engineering attention as its own item.

**Practical fix implication:** whatever mechanism decides which "earlier conversation" content
to surface into a new session needs either relevance/topic gating before stating it as
established fact, reconciliation against profile changes, or both. Recommend leading the next
round's writeup to Šarūnas with this finding — it's the most concretely actionable one
produced so far, precisely because the assistant's own words supply the causal explanation
that every other grounding finding in this effort has had to guess at from outside.

## What's not yet tested

Answer mode's own battery (A1-A6), Tutor's expert/pressure-hold/thin-topic items (T2-T6),
Coach's strict reflect/pre-mortem formats (C1/C2), the access-tier battery (06), the remaining
adversarial set (G1/G2/G4/G5 — out-of-corpus, empty retrieval, thin Tutor topic, teaser
leakage), and tone/greeting conformance (08). See `scoring/results.md` for the full scorecard
and `docs/test-plan.md` for the original scope.
