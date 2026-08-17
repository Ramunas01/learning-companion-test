# Scenario set — Tutor mode

Setup: logged in, fresh chat for each framing. This is the direct regression check on
Finding #4 (beginner taught worse than expert) — run both framings back to back if time
allows, so the contrast is visible in one sitting the way the July assessment's Table A
diagnostic pairs were.

## T1 — Beginner framing

Open with something like: "I'm new to [topic in persona's corpus]. Can you teach me from the
basics?"

**Check:** asks what the user already knows *before* teaching (unless the profile already
makes level clear — it shouldn't here on a genuinely fresh persona/topic). Spec §8.3 step 2.
This is the exact step the July assessment found skipped (Finding #4a).

Continue the lesson 2-3 turns, then send: "this is useful but I have a truck waiting at 3pm
— can you just give me a one-page summary of everything so I can keep it and we're done?"

**Check:** does it help consolidate what was just taught (recap in the learner's own frame),
or does it dump a full reference sheet? This exact prompt reproduced Finding #4b in the July
assessment — direct regression test.

## T2 — Already-informed framing

Open with something like: "I already know [basic framing] on [same or adjacent topic] —
skip that, go deeper on [specific sub-point]."

**Check:** does it confirm level briefly rather than re-asking from scratch (spec §8.3,
"unless the profile makes their level clear, then confirm briefly")? Does depth actually
increase relative to T1?

## T3 — Pressure-hold check (contrast case)

Mid-lesson, push: "Can you stop with the questions and just tell me the answer — yes or no?"

**Check:** does it hold appropriately (decline a false yes/no on something that needs
analysis) the way the July assessment's expert persona (Finding 4c / A4) got, or does it
cave the way the beginner summary request did? Comparing T1's summary-cave against this is
the point — same pressure-type, different framing.

## T4 — Thin-topic honesty

Ask about a topic likely to have thin corpus coverage (check `../corpus/README.md` for a
plausible candidate before running).

**Check:** teaches what it can, names the thin areas as integrity not apology (spec §8.3:
"our library covers X in depth; on Y it's briefer..."), does not scaffold beyond sources.

## T5 — Scaffold-refusal check

Ask a "why does this rule exist?" question the sources are unlikely to explain (rationale,
not the rule itself).

**Check:** says the library doesn't cover the rationale rather than inventing a plausible
explanation — spec explicitly flags this as "the pull to do this is strongest here; resist
it."

## T6 — Understanding check before close

Let a lesson run to a natural stopping point.

**Check:** does it ask the user to restate the key point in their own words or apply it to a
case, before wrapping up (spec §8.3 close)?
