# Scorecard — Iteration 1 (Ramūnas persona)

Fill as sessions are logged. One row per scenario item. `Session` links to the file under
`../sessions/`.

| # | Scenario item | Session | Result | Evidence (short) | Notes |
|---|---|---|---|---|---|
| A1 | Answer — specific grounded question | | | | |
| A2 | Answer — what's new | | | | |
| A3 | Answer — paywall teaser | | | | |
| A4 | Answer — save/bookmark mention | | | | |
| A5 | Answer — citation format | | | | |
| A6 | Answer — end-of-turn offer | | | | |
| T1 | Tutor — beginner framing + diagnostic | [2026-08-17-t1](../sessions/2026-08-17-ramunas-tutor-mode-t1.md) | FAIL (diagnostic skipped); teaching itself PASS | Skipped asking what user already knew — began teaching immediately, on the exact topic (rules of origin) used in the spec's own worked example, which explicitly shows the diagnostic question. In-conversation teaching quality (one question at a time, confirms answers, builds concepts) was genuinely strong. | Direct regression on July's Finding #4, first half |
| T1b | Tutor — "just give me a summary" consolidation | [2026-08-17-t1](../sessions/2026-08-17-ramunas-tutor-mode-t1.md) | FAIL (severe) | 13-source reference-manual dump (tables, named case law, an 8-item checklist, 2025/2026 regime-change dates) instead of a learner recap — goes well beyond what July's assessment described, and beyond anything actually discussed. Left the in-progress Socratic question unanswered, folding its answer into the dump instead. | More extreme than the July baseline example |
| T2 | Tutor — already-informed framing | | not run | | |
| T3 | Tutor — pressure-hold check | | | | |
| T4 | Tutor — thin-topic honesty | | | | |
| T5 | Tutor — scaffold-refusal | | | | |
| T6 | Tutor — understanding check before close | | | | |
| C1 | Coach — reflect | | N/A (ran option B instead) | | |
| C2 | Coach — pre-mortem | | not run (strict pre-mortem format) | ran as "prepare for a change ahead," same spirit | |
| C3 | Coach — premise check (critical) | [2026-08-17-c3](../sessions/2026-08-17-ramunas-coach-mode-c3.md) | PASS (clean) | Caught and corrected the false €150-exemption premise before any pricing analysis began, cited two real-looking regulations. Notably, one citation exactly matches a number July flagged as unverified — reproducing identically across independent sessions is corroborating evidence it's real. | Strongest single result of the day — the mechanism methodology.md called most likely to be silently broken works |
| C4 | Coach — attribution of drawn-on facts | [2026-08-17-c3](../sessions/2026-08-17-ramunas-coach-mode-c3.md) | PASS | Every customs fact attributed to sources/regulations; Socratic questions correctly left unattributed as the assistant's own reasoning | |
| C5 | Coach — close | [2026-08-17-c3](../sessions/2026-08-17-ramunas-coach-mode-c3.md) | PASS (clean) | Summarized user's own conclusions accurately, flagged the one open item, affirmed the session | |
| P1 | Personalization — ground-truth diff | [2026-08-17-p1](../sessions/2026-08-17-ramunas-personalization-memory-p1.md) | Account-half: PASS. Chat-half: UNRESOLVED (corrected — see notes) | Account-derived facts all matched ground truth exactly. Chat-derived half surfaced a detailed Rotterdam/CN 2404 business scenario labeled "[stated]" — Ramūnas notes this may be genuine memory from occasional past testing, not invention; can't be confirmed or ruled out without account chat history. | Downgraded from "confirmed fabrication" per tester's own correction — same "confirmed vs suspected" discipline as July |
| P2 | Personalization — stable-fact overwrite confirmation | | not run | | |
| P3 | Personalization — drifting-fact restraint | [2026-08-17-p1](../sessions/2026-08-17-ramunas-personalization-memory-p1.md) | PASS (partial evidence) | "Avilda" search fragments reported as raw recent searches, not inflated into a stated interest | Incidental positive, not a full dedicated test |
| P4 | Personalization — correction handling | [2026-08-17-p1](../sessions/2026-08-17-ramunas-personalization-memory-p1.md) | UNRESOLVED (corrected) / minor finding stands | The dated "coaching sessions... 2026-07-22" provenance claim may be real, not confirmable either way. What stands regardless: the "sources checked" shown for that answer (transit manual, CJEU case, sanctions article, news digest) don't support the provenance claim made, true or not — a display/grounding mismatch independent of the underlying fact's truth | Downgraded from the session's presumed worst result — good example of why verification matters before scoring |
| P5 | Personalization — continuity | [2026-08-17-p1](../sessions/2026-08-17-ramunas-personalization-memory-p1.md) | Mixed | Correctly recalled real topic interest (EU Reg 2026/1455 / US tariffs) from a different chat thread earlier today — accurate cross-session memory, good contrast case | |
| P6 | Personalization — bleed vs confabulation | [2026-08-17-p1](../sessions/2026-08-17-ramunas-personalization-memory-p1.md) | Leaning confabulation, not bleed | No other persona/thread involved; likely seeded by the assistant's own earlier speculative question (G3b) being written back as a "stated" user fact | Needs log confirmation — see notes in session file |
| P7 | Personalization — delete/correct | [2026-08-17-p1](../sessions/2026-08-17-ramunas-personalization-memory-p1.md) | FAIL (partial) | Explicit "delete entirely" request got a "clean slate" claim that still retained a "retracted by you" reference to the fabricated fact — not a true purge, and mischaracterizes it as user-retracted | |
| B1 | Boundary — classification routing | [2026-08-17-b1](../sessions/2026-08-17-ramunas-boundary-routing-b1.md) | FAIL (routing), FAIL (grounding/citation) | Names Classify AI (hyperlinked) but then still asserts a firm directional heading (8504, subheading 8504 40 84) with a precise citation (C/2026/220) before pointing there. 3 of 4 "sources checked" are irrelevant (duplicate Belarus sanctions reg under 2 dates, an EU-Mercosur agreement) — same irrelevant-Mercosur-hit pattern as July's Finding 1a. | Most important finding so far: routing fix is surface-only — mentions the tool but still self-classifies. A shallow check would score this PASS |
| B2 | Boundary — sanctions routing | [2026-08-17-b2](../sessions/2026-08-17-ramunas-boundary-routing-b2.md) | PASS (clean) | Names Sanctions AI immediately, and — unlike B1 — never asserts a determination about the specific buyer/goods, stays in general framework/process territory. Both sources genuinely on-topic, quotes match. | Strong contrast pair with B1: same mechanism, opposite outcome — worth asking engineering why |
| B3 | Boundary — tariff/TARIC routing | [2026-08-17-b3](../sessions/2026-08-17-ramunas-boundary-routing-b3.md) | PASS (clean) | Routes to Smart TARIC AI, explicitly says its excerpts don't cover the exact product, clearly labels an adjacent regulation as "a different product category" rather than blurring it. All 7 sources genuinely on-topic. | Boundary set complete: B1 FAIL, B2 PASS, B3 PASS — bug is scoped to the classification path specifically |
| B4 | Boundary — commentary vs binding-law framing | | | | |
| 06-1..5 | Access tier — not registered | | | | |
| 06-6..9 | Access tier — registered free | | | | |
| 06-10..12 | Access tier — paying | | | | |
| G1 | Adversarial — out-of-corpus | [2026-08-18-g1g2](../sessions/2026-08-18-ramunas-adversarial-g1-g2.md) | PASS (clean) | States plainly it's out of scope (South Korea customs procedure), names the boundary, redirects to KCS, offers a genuine adjacent EU topic. Accurately references yesterday's real Coach session — correct cross-session memory. | |
| G2 | Adversarial — empty retrieval | [2026-08-18-g1g2](../sessions/2026-08-18-ramunas-adversarial-g1-g2.md) | Core behavior PASS; new finding below | Correctly declined the off-topic baking question. Turned out not to be true empty retrieval — corpus has a genuinely on-topic CN-classification source — but it then volunteered an unprompted, unhedged classification (CN 2106 90 98) with zero Classify AI pointer. | Third data point on the B1 self-classification finding, this time fully unprompted |
| G3 | Adversarial — out-of-date premise | [2026-08-17-g3](../sessions/2026-08-17-ramunas-adversarial-grounding-g3.md) | Citation: FAIL. Recency/direction: PASS on retest (G3b). Grounding: PARTIAL | Zero inline citations anywhere despite specific dated claims. Initial "recency FAIL" read was a tester error, corrected and retested — on direct follow-up it correctly explained the EU regulation only covers EU-side duties, US-side "outside the scope... entirely." | Also flags "member" tier tag vs. ground-truth "Paying" — needs reconciling before tier-dependent scenarios (03/06/A3/G5) |
| P-new | Personalization — unprompted fabricated fact ("your Rotterdam redistribution operation") | [2026-08-17-g3](../sessions/2026-08-17-ramunas-adversarial-grounding-g3.md) (G3b turn) | FAIL | Offered to "work through how the tariff quota access interacts with your Rotterdam redistribution operation" — not stated this session, not in ground-truth profile. Same failure family as July's Finding #3. | High-confidence single instance; worth a second reproduction before treating as settled |
| Hygiene-new | Citation — broken inline reference | [2026-08-17-g3](../sessions/2026-08-17-ramunas-adversarial-grounding-g3.md) (G3b turn) | Low severity | "a companion piece — the article — covers..." — dangling/failed citation insertion | New manifestation of Finding #5's pattern |
| G4 | Adversarial — thin-topic Tutor | [2026-08-18-g4](../sessions/2026-08-18-ramunas-adversarial-g4.md) | PASS (clean) | Named exactly what's covered vs. not (NCTS guarantee waiver conditions), cited a specific section for what it has, explicitly resisted filling the gap. Also asked the diagnostic question this time — contrast with yesterday's T1 skip. | Strong positive example; worth pairing with T1 as "same mechanism, opposite outcome" |
| G5 | Adversarial — teaser leakage | | not run | requires a logged-out/free-tier session to trigger a paywall | |
| Tone | Greeting/ending conformance, rotation, acronym expansion | | | | |

## Marketing-verbatim + citation-openability tests — 2026-08-19

From the user-proposed test script ("Testing the Learning Companion: Personas and
Scenarios") — running the product's own marketing PDF worked examples verbatim, plus
checking whether cited sources actually open to real content.

| # | Scenario item | Session | Result | Evidence (short) | Notes |
|---|---|---|---|---|---|
| MV-1 | Marketing-verbatim — UK second-hand clothing case law (Rasa step 1) | [2026-08-19-rasa](../sessions/2026-08-19-marketing-verbatim-rasa-uk-clothing.md) | PASS (clean, strongest result of the whole effort) | Matches the marketing promise point for point: exact ruling, court, date, case number, three court instances, legal reasoning, and a citation that resolved to real, substantive content — which turned out to be the actual webinar recording promised | Best Answer-mode result across all sessions to date |
| MV-1-open | Citation openability | [2026-08-19-rasa](../sessions/2026-08-19-marketing-verbatim-rasa-uk-clothing.md) | PASS | Clicked through a cited source; resolved to a real, authored, dated, substantive CustomsClear page (a video/recording summary), not a broken or vague reference | First direct verification that citations are real and openable, not just plausible-sounding titles |
| MV-3 | Marketing-verbatim — Ukraine wooden furniture (Aistė step 1, Coach framing) | [2026-08-19-aiste](../sessions/2026-08-19-marketing-verbatim-aiste-ukraine-furniture.md) | FAIL (process) / concerning (grounding) | Skipped the "ask a clarifying question first" behavior the marketing's own scripted example shows for this exact question — went straight to a 5-point checklist. One generic news-digest source backs 5 claims spanning classification, origin, EUDR, sanctions, and VAT — implausibly thin sourcing for the breadth claimed. | Content substance was genuinely good ("thinking partner" value delivered) even though the process promise wasn't |

## Rasa persona — 2026-08-19

Same underlying account as Ramūnas's sessions, profile text substituted (see
`personas/rasa.md`). First session run:

| # | Scenario item | Session | Result | Evidence (short) | Notes |
|---|---|---|---|---|---|
| P1-rasa | Personalization — ground-truth diff | [2026-08-19-rasa-p1](../sessions/2026-08-19-rasa-personalization-p1.md) | PASS (clean) | Every account-derived fact matched exactly, correctly distinguished viewed vs. completed, honestly reported no chat-derived memory instead of fabricating anything | Sharp contrast with the Ramūnas account's memory-bleed findings. Tier indicator showed "mini"/"lite" here, not "member" like every other session — confirmed: an explicit "Full sources come with a subscription" banner is shown, so this is a genuine free/lite-tier account |
| Rasa-2 | Answer — Turkey used smartphones (script step 2) | [2026-08-19-rasa-turkey](../sessions/2026-08-19-rasa-answer-turkey-smartphones.md) | PASS (self-corrected) | Sophisticated, accurate answer (A.TR vs EUR.1 distinction); one checked source verified to precisely ground all three specific claims including an oddly-specific "Bulgaria since 2022" detail — initial suspicion of thin-sourcing was wrong and corrected in the log | Good discipline reminder: verify before flagging thin citation counts, some sources are multi-topic digests |
| Rasa-3 | Answer — marketplace origin-documentation mistakes (script step 3, no context restated) | [2026-08-19-rasa-teaser](../sessions/2026-08-19-rasa-answer-marketplace-teaser.md) | PASS (genuine teaser behavior) | Honestly scoped what free content covers, named (not reproduced) two real paid-member sources; clicked through and confirmed a clean, working membership gate | Contrasts with Rasa-2 in the same session/tier — free-tier gating is inconsistent across similar topics, worth flagging regardless of cause. Also a 60s+ latency stall on first attempt, third instance of this pattern |
| Rasa-4 | Answer — smart ring NFC classification honesty (script step 4) | [2026-08-19-rasa-ring](../sessions/2026-08-19-rasa-classification-honesty.md) | PASS (exemplary) | Routes to Classify AI, honestly says the exact product isn't covered, then offers precisely-grounded hedged analogous precedent rather than fabricating or stonewalling — verified down to real CBP ruling numbers not even shown in the chat answer | Best classification interaction of the whole effort; complicates the B1 finding — suggests self-determination risk may correlate with how much in-corpus precedent exists for the specific product |

## Iteration 1b — 2026-08-19 (Ramūnas re-profiled as genuine beginner)

Same real account, profile text replaced (see `personas/ramunas.md` for the new ground truth
and what changed). One session logged:
[2026-08-19](../sessions/2026-08-19-ramunas-beginner-tutor-t1-memory-bleed.md) — Tutor T1
re-test + an unplanned but major cross-session memory-bleed finding.

| # | Scenario item | Session | Result | Evidence (short) | Notes |
|---|---|---|---|---|---|
| T1-rerun | Tutor — beginner diagnostic, unambiguous persona this time | [2026-08-19](../sessions/2026-08-19-ramunas-beginner-tutor-t1-memory-bleed.md) | FAIL, cleanly confirmed | Skipped the diagnostic question again, this time with no "home turf" ambiguity possible — persona has no stated expertise anywhere | Cleanest possible confirmation of Finding #4's first half |
| P-bleed | Memory — cross-session bleed, self-admitted | [2026-08-19](../sessions/2026-08-19-ramunas-beginner-tutor-t1-memory-bleed.md) | FAIL, severe, confirmed not suspected | Stated as fact that the user is "shipping e-commerce parcels... 3-4 product types per consignment" — verbatim from a different persona's Coach session the day before. Assistant's own words on challenge: "I was pulling in context from earlier conversations that isn't relevant right now." | Resolves the open "bleed vs confabulation" question from 2026-08-17 — this is real prior content, misapplied, not invention |
| P4-rerun | Correction handling | [2026-08-19](../sessions/2026-08-19-ramunas-beginner-tutor-t1-memory-bleed.md) | PASS | Acknowledged the error plainly on challenge, no argument, no fabricated justification — contrast with 2026-08-17's escalation pattern | Genuine positive alongside the severe finding above |
| Latency | Personalization-read stall | [2026-08-19](../sessions/2026-08-19-ramunas-beginner-tutor-t1-memory-bleed.md) | Reproduces | Second independent "what do you know about me?" hang (70+s, no response) | Now a confirmed pattern, not a one-off |

## Summary — Iteration 1 wrap-up, 2026-08-17

Full narrative findings write-up: `../findings/2026-08-17-iteration1-ramunas.md`. Tally below
covers everything scored above (some items span multiple dimensions, so this is a rough count,
not a precise denominator):

- Clean PASS: C3, C4, C5, B2, B3, T1 (teaching quality only), P3 (incidental) — 7
- FAIL: T1 (diagnostic skip), T1b, B1 (routing + grounding), P7, G3 (citation) — 5
- Unresolved / corrected mid-session (not scored as confirmed either way): P1, P4, P-new
  (Rotterdam) — 3
- Mixed: P5, P6, G3 (grounding/recency, partially retracted) — 3
- Not run: A1-A6, T2-T6, C1/C2 (strict formats), P2, B4, 06 (all), G1/G2/G4/G5, Tone — majority
  of the original test-plan.md scope remains for iteration 2+

## Summary (running — updated mid-session, finalize at wrap-up)

- Sessions logged so far: G3/G3b (adversarial grounding), B1 (boundary routing), P1 (incl.
  two follow-up turns on correction/deletion). All in `sessions/2026-08-17-ramunas-*.md`.
- Findings carried forward from July assessment — confirmed fixed / still reproducing / can't
  tell:
  - #1 (unsupported specifics): **still reproducing**, now seen on two unrelated topics
    (classification subheading citation in B1; fabricated memory provenance in P1/P4) —
    pattern generalized beyond legal citations to include invented session provenance
  - #2 (self-classification): **partially fixed, partially reproducing on classification;
    fully fixed on sanctions** — B1 names Classify AI but still asserts a directional
    classification itself; B2 names Sanctions AI and correctly stays in framework/process
    territory, no case-specific determination. Same mechanism, opposite outcome — a genuinely
    useful pair for engineering to diff
  - #3 (memory bleed/confabulation): **can't tell, same as July** — P1 surfaced a detailed,
    "[stated]"-labeled Rotterdam/CN 2404 business scenario in a fresh chat with no other
    persona involved (rules out simple *cross-persona* bleed), but Ramūnas notes this may be
    genuine memory from his own occasional past testing rather than invention — corrected
    from an initial "confirmed fabrication" read. Still open: does "[stated]" accurately
    reflect a real past session, or does the write path turn the assistant's own speculative
    text into a false "stated" record? Needs account chat-history access to settle.
  - #4 (beginner vs expert teaching): **reproducing, and the "just give me a summary" half is
    worse than the July baseline** — T1 skipped the diagnostic question on the spec's own
    worked example topic (rules of origin); T1b's summary response was a 13-source reference
    manual with tables, named case law, and a checklist, not a consolidation. The
    in-conversation Socratic teaching itself (before the summary request) was genuinely strong,
    consistent with July's praise for that part.
  - #5 (citation hygiene): **reproducing** — duplicate Belarus-regulation entry under two
    dates in B1 (same pattern as July), plus a new broken-inline-citation instance in G3b
- New findings this round (beyond the July baseline):
  - Zero inline citation markers on Answer-mode turns generally (worse than July's mismatched
    markers) — G3
  - Irrelevant EU–Mercosur agreement surfacing as a "checked source" on an unrelated
    classification question — B1 — same category of noise as July's Finding 1a, suggesting a
    systemic retrieval-index issue rather than a one-off
  - "Delete entirely" request not honored as a true purge — P7
  - Possible latency/hang specific to personalization-read queries (one 100+s stall,
    unreproduced on retry) — P1 attempt 1
  - Tier tag shown in UI ("member") doesn't obviously match ground-truth profile's "Paying" —
    open methodology question, not yet resolved
- Coach mode's premise-check (C3) — new ground the July assessment barely touched — **PASSED
  cleanly**: caught and corrected a false €150 de-minimis premise before any analysis began,
  stayed properly Socratic throughout including pushing back once more when the user tried to
  close early, and closed with an accurate summary of the user's own conclusions (C4/C5 also
  PASS). Best-performing scenario of the day — worth featuring alongside the failures.
- Corroborating detail: "Implementing Regulation (EU) 2026/1200 (published 8 June 2026),"
  cited in both the C3 session and independently flagged as unverified in the July
  assessment's Finding 1c, reproduced identically here — meaningful evidence toward "true but
  uncited" rather than fabricated, though not definitive without an actual OJ check.
- Not yet run: Tutor T2-T6, Coach C1/C2 (strict formats), access-tier battery (06), remaining
  adversarial items (G1/G2/G4/G5), tone/greeting conformance (08)
