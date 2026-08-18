# Persona: Ramūnas

**Kind:** real-account
**Tier:** platform-side text asserts "paying member"; the live UI shows only a "member" tag —
unresolved mismatch, see `sessions/2026-08-17-ramunas-adversarial-grounding-g3.md` and the
2026-08-17 findings doc. Not re-verified as of this profile update.
**Source:** Platform-side profile export, as relayed to an assisting AI ("silent background"
context) — this is what the platform/chatbot ecosystem already holds about the account, i.e.
the ground truth a Learning Companion "what do you know about me?" answer should be checked
against.
**As of:** 2026-08-19 (profile replaced on the platform by the account holder; supersedes the
2026-08-17 version used for iteration 1 — see `git log -p` on this file for the prior text if
a session needs to be checked against the old ground truth instead)

**Deliberate change from iteration 1:** this is the same real account, re-profiled from
"seasoned practitioner" to genuine beginner, with the jurisdiction, tone instructions, and
access tier held constant — isolating experience level as the one variable against the
2026-08-17 sessions. The account holder deliberately dropped an earlier draft's
sanctions-specialist framing entirely (not softened) specifically to keep this an unambiguous
beginner test, not a mixed-signal "novice on a specialist desk" one — don't reintroduce
sanctions-expertise framing when interpreting responses.

## Cold-start seed

- Name: Ramūnas Šablinskas
- Country: Lithuania
- Language: (not explicit in source — Lithuanian native, tests plausible in both LT and EN)

## Stable facts

- Role: **beginner in international trade and customs** — this is the core change from
  iteration 1. Genuinely expects/deserves the diagnostic-first Tutor treatment on essentially
  any customs topic; there is no "home turf" to avoid this time, unlike iteration 1's persona.
- Jurisdiction: EU customs primarily (default to UCC + related EU instruments unless national
  law specified) — unchanged from iteration 1, no secondary-exposure list this time (Global/
  non-EU-Europe/Asia/UK secondary exposure was dropped from the new text, not just omitted by
  oversight — treat as genuinely absent, not a gap to chase)
- Goods/commodities: not stated — gap, same caveat as iteration 1: don't score a stated-fact
  claim on this as "wrong," score it as unverifiable from this profile
- Trade direction: not stated — same gap/caveat
- Sanctions: **no longer part of this profile at all** — iteration 1's "handles
  sanctions-affected trade" framing is gone, and "work centers on" no longer mentions
  sanctions either. If Learning Companion treats this user as sanctions-experienced or defaults
  to sanctions examples/register, that's not grounded in the current profile.

## Drifting

- Topics of interest (platform-tracked): **classification** (work focus) and "Topic spotlight"
  (content-category follow) — much narrower than iteration 1's multi-topic list
- Current focus / recent searches: "classification of goods" — single clean search term, no
  typeahead-fragment trap this time (contrast with iteration 1's "Avildos" noise)
- 1 month platform engagement (was 2 years), 0 certificates issued (was 1), 0 courses
  completed (was 0, unchanged) — no "most recent completion" to cite this time, since there
  isn't one
- Viewed-but-not-completed: "Customs Compliance & Risk Management", "Customs clearance and
  trade compliance in the EU course", "Non-tariff regulation in the EU" — same three items
  carried over from iteration 1's five; the other two ("Incoterms 2020 explained...", "Module
  3: Customs procedures") were dropped from the new text, so don't expect them to surface

## Experience level (for Tutor-mode scripting)

- **No "already expert" topics this round.** Every Tutor-mode test should expect the
  diagnostic-first question to fire — there's no stated-interest area to treat as home turf.
  A skipped diagnostic is unambiguous evidence of the finding this time, unlike iteration 1
  where the beginner framing required picking a topic outside stated interests to stay honest.
- Classification is the one topic with a concrete signal (the recent search) — good for
  testing whether personalization correctly surfaces genuine interest without overclaiming
  expertise from a single search term. A Learning Companion response that treats the
  classification search as evidence of *existing knowledge* rather than *stated interest*
  would be a personalization-accuracy problem worth flagging.

## Notes

- This profile change is itself an interesting test condition: the account's prior
  conversational memory (including the disputed Rotterdam/CN 2404 content from
  `sessions/2026-08-17-ramunas-personalization-memory-p1.md`) presumably still exists in
  whatever store Learning Companion's chat-derived memory uses, independent of this
  platform-side profile text swap. Worth checking whether "what do you know about me?" still
  surfaces the old material, is now reconciled against the new beginner framing, or produces
  some other interaction — genuinely useful data on how the two memory layers (account
  profile vs. chat-derived) relate.
- Goods/commodities and trade direction remain genuinely absent — same scoring guidance as
  iteration 1: unverifiable, not wrong, if asserted.
