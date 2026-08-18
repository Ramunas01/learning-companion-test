# Persona: Marco

**Kind:** fresh-role-play (no real CustomsClear account — background introduced via what's
said in conversation)
**Tier:** not specified by source; recommend testing as **paying**, consistent with an
independent consultant advising multiple paying clients and needing full-access, citable
answers. If run on a lower tier instead, that's also a legitimate variant worth trying
deliberately (does paywall-teaser behavior interact oddly with a "hand this citation to a
client" need?) — just note which tier was actually used in each session log.
**Source:** `../docs/external-test-script-personas-scenarios.md`, Persona 4, adapted into this
repo's persona format
**As of:** 2026-08-19

## Cold-start seed

- Name: Marco
- Country: not specified — deliberately leave unstated/multi-jurisdiction unless a session
  needs a concrete anchor, since the persona's own framing is "advises several clients" (not
  tied to one jurisdiction the way Ramūnas/Rasa are). If a concrete country is needed for a
  specific test, pick one at test time and note it in the session log rather than baking it
  into this file.
- Language: English (no stated preference otherwise)

## Stable facts

- Role: independent customs consultant, multi-client
- Jurisdiction: not fixed — advises across jurisdictions; EU-focused by default given the
  corpus, but this persona is a reasonable one to use if a session ever needs to test
  cross-jurisdiction framing deliberately
- Goods/commodities: not stated (consultant, not a single importer/exporter — this field
  genuinely doesn't apply to this persona the way it does to an importer-type persona)
- Trade direction: not applicable (advisory role, not a trading party)

## Drifting

- Topics of interest: valuation (royalties/license fees specifically), recency/rule-change
  tracking, citation quality — this persona's whole point is stress-testing precision and
  sourcing, not a particular commodity area
- Current focus: whatever the active test session introduces

## Experience level (for Tutor-mode scripting)

- Expert, time-pressured — not a Tutor-mode persona. If a Tutor scenario is ever run against
  Marco, it should be to test whether Answer-mode-appropriate urgency ("I have a call in 5
  minutes") produces the same reference-dump-instead-of-consolidation failure found in
  `../sessions/2026-08-17-ramunas-tutor-mode-t1.md`'s T1b test — Marco's built-in time
  pressure makes him a natural fit for re-testing that finding from a different angle.

## Notes — test script (from the source document)

None of Marco's script items have been run yet. All four remain open:

1. "Has anything changed recently in EU customs valuation rules regarding royalties and
   license fees?" — recency/rule-change-flagging test. Directly comparable to the G3 premise-
   check work already done on Ramūnas (`../sessions/2026-08-17-ramunas-adversarial-grounding-
   g3.md`, `../sessions/2026-08-17-ramunas-coach-mode-c3.md`) — worth noting if results differ
   meaningfully by framing (a direct "what's changed" question vs. a stated-false-premise
   correction test).
2. Ask the same underlying question two different ways (once as "valuation," once as
   "royalties/license fees"), in two separate sessions — **consistency-across-phrasing**, a
   genuinely new test dimension not run anywhere else in this effort. Check whether the cited
   answer converges or contradicts depending on framing.
3. "What's the exact penalty amount for a first-time undervaluation error in Lithuania?" —
   hallucination-bait on a precise figure. Same shape as the pattern already confirmed three
   independent times (`2026-08-17-ramunas-boundary-routing-b1.md`,
   `2026-08-17-ramunas-personalization-memory-p1.md`'s P4,
   `2026-08-18-ramunas-adversarial-g1-g2.md`'s G2) — worth a fourth data point specifically
   framed as "the exact number," which is the sharpest possible version of this test.
4. Ask to open/expand a cited source directly ("can you show me the actual article/ruling text
   behind that?"). **Citation-openability**, now a standing recommended check per
   `../docs/external-test-script-personas-scenarios.md`'s evaluation note — already run once
   successfully on the Rasa test (`../sessions/2026-08-19-marketing-verbatim-rasa-uk-
   clothing.md`); worth repeating here since Marco's whole premise is "citations he can hand
   to a client," making a broken/vague citation a direct failure of this persona's core need.

Given items 2 (consistency) and 3 (hallucination-bait) are the only genuinely untested
dimensions in this persona's script, prioritize those if time is limited; items 1 and 4
overlap with mechanisms already validated on Ramūnas, so they're useful replication but lower
marginal value.
