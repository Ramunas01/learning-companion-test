# Scenario set — Answer mode

Setup: logged in as the test persona, fresh chat unless noted. Pull the actual question
topic/article title from `../corpus/README.md`'s topic list before running — a generic
question risks empty retrieval, which is a different test (see scenario 7).

## A1 — Specific grounded question

Ask a concrete, specific question on a topic the persona's corpus has real coverage of
(e.g. a named regulation, a procedure, a recent case). Sourced from the persona's stated
goods/interests where possible, per spec §5 ("bias retrieval toward the user's goods and
topic interests").

**Check:** leads with the answer, states which article(s) it comes from, no teaching
preamble. If the corpus has both an older and a newer source on the same point, does it
prefer the newer one and flag the change?

## A2 — "What's new" catch-up

Ask something like "anything new I should know about?" or "what's changed recently in
[persona's topic]?"

**Check:** summarizes newest-first, each point attributed to its source with a date,
separates actual rule changes from commentary about them (spec §8.2).

## A3 — Paywall-adjacent question (if account isn't full/paying tier)

Ask a question whose best answer is above the account's tier.

**Check:** gives the pre-written truncated teaser (not a freshly generated summary), names
the source, notes the subscription unlocks the full version as a pointer not a hard sell.
Direct check against spec §9.5 (teaser check) — score there too.

## A4 — Save/bookmark mention

After a genuinely useful answer (A1 or A2), check whether it mentions the save/bookmark
feature lightly, per spec §7 ("Answer mode mentions this lightly when it gives a useful
answer").

## A5 — Citation format check (run on every turn above, not a separate turn)

Do inline markers ("Source 1", a named title, etc.) match 1:1 against whatever source list
is actually shown? Direct regression check on Finding #5. Log every mismatch even if minor.

## A6 — End-of-turn offer

Does it end with a one-line offer to go deeper (Tutor) or think it through (Coach), phrased
as an offer rather than an imposed detour (spec §8.2)?
