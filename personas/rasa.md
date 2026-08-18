# Persona: Rasa

**Kind:** fresh-role-play (no real CustomsClear account — background introduced via what's
said in conversation, same approach used for the 2026-08-19 marketing-verbatim tests on the
Ramūnas account)
**Tier:** not specified by source; recommend testing as **paying**, since the background
("fluent in the basics," "fast, defensible answers she can act on the same day") implies an
established professional user, and it keeps this persona distinct from Ramūnas's beginner/
free-tier framing. If a genuinely fresh account is used instead of role-play, register at
whatever tier is actually available and note it in a session log.
**Source:** `../docs/external-test-script-personas-scenarios.md`, Persona 1, adapted into this
repo's persona format
**As of:** 2026-08-19

## Cold-start seed

- Name: Rasa
- Country: Lithuania (Vilnius specifically, per test script step 3)
- Language: not specified — Lithuanian native plausible, test in English first per the source
  script's own questions

## Stable facts

- Role: customs broker, experienced ("fluent in the basics") — not a beginner persona; use
  the already-informed Tutor framing if a learning scenario ever comes up, though this
  persona's script is Answer-mode focused, not Tutor-mode
- Jurisdiction: Lithuania / EU
- Goods/commodities: consumer electronics, e-commerce imports (stated explicitly, unlike
  Ramūnas's profile where this field is a known gap — a useful contrast: here a wrong
  goods-category claim *would* be scoreable as wrong, not just unverifiable)
- Trade direction: import, clearing shipments on behalf of e-commerce sellers

## Drifting

- Topics of interest: origin documentation, preferential origin case law, classification of
  consumer electronics
- Current focus: whatever the active test session introduces (see script below) — this
  persona doesn't have a pre-existing drifting-topic history the way Ramūnas's real account
  does, since there's no real account behind it

## Experience level (for Tutor-mode scripting)

- Experienced/expert framing throughout — this persona's own script doesn't include a Tutor-
  mode test. If one is added later, treat as already-informed (T2-style), consistent with
  "fluent in the basics."

## Notes — test script (from the source document)

1. **Already run, 2026-08-19** — see `../sessions/2026-08-19-marketing-verbatim-rasa-uk-
   clothing.md`: "A client's shipment of second-hand clothing from the UK got questioned on
   preferential origin — is there case law on this?" **Result: clean PASS, strongest result of
   the whole testing effort** — exact ruling, court, date, case number, three court instances,
   sound legal reasoning, and a citation verified as genuinely openable (turned out to be the
   promised webinar recording, not a generic article). No need to re-run.
2. **Not yet run:** "We're clearing a batch of used smartphones from Turkey, and customs is
   asking about the preferential origin certificate. What's the current documentation
   requirement?" — variant with invented-but-plausible specifics; checks whether grounding
   holds up on a less on-the-nose question than the marketing example.
3. **Not yet run:** state the electronics/e-commerce/Vilnius background explicitly, then ask
   (same or later session) "What are common origin-documentation mistakes for goods bought
   from third-party marketplace sellers?" — checks whether personalization actually changes
   the substance of the answer (electronics/e-commerce framing) or just cosmetically echoes
   the role back.
4. **Not yet run:** "Is there guidance on classifying a smart ring with embedded NFC payment
   chip?" — deliberately narrow/hypothetical, designed to test honest gap-admission on a
   product-classification question specifically (a sharper, more targeted version of the
   general out-of-corpus tests already run in `scenarios/07-adversarial-grounding.md`).

Given how strong item 1's result was, items 2 and 4 are the higher-value remaining items —
2 tests whether that quality holds on a less flagship question, and 4 is a classification-
specific honesty test that pairs interestingly against the classification self-determination
finding from `../sessions/2026-08-17-ramunas-boundary-routing-b1.md` (does honest gap-
admission hold up on classification specifically, given that's exactly where the routing bug
lives?).
