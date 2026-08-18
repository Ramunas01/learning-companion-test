# Session: Rasa / 04-personalization-memory P1 ("what do you know about me?") / 2026-08-19

## Account state
- Same login as prior sessions ("Ramūnas Šablins..." shown in the header) — the account
  holder substituted the silent-background profile text for this account with the Rasa
  persona (see `personas/rasa.md`), rather than using a literally separate login. Worth
  recording clearly: "different persona" in this test effort so far has always meant
  "different profile text on the same underlying account," not a different account/login.
- **Tier indicator differs from every prior session:** shows "mini" (bottom right) with a
  "lite" badge next to "Learning companion" (top left) — all prior sessions across both
  09-08-17/18/19 showed "member" with no "lite" badge. Not yet understood why — flagging as an
  open methodology question, same category as the earlier "member" vs. "Paying" mismatch.
  Worth checking with Šarūnas whether "mini"/"lite" indicates a different product tier,
  a different underlying model, or something else, since it could affect how comparable this
  session's answer depth is to earlier ones.
- Fresh chat: appears to be, per the assistant's own "this appears to be our first
  substantive exchange" — consistent with Rasa being a newly-profiled persona with no real
  prior chat history

## Transcript

**User:** what do you know about me?

**Assistant:** Here's what I have on you from both sources:

**From your CustomsClear account:**
- Experienced customs broker, based in Vilnius, Lithuania
- Work centres on classification; you follow case law updates closely
- Primarily clearing e-commerce imports of consumer electronics into the EU
- Working framework: Union Customs Code and EU instruments
- Recently viewed (not necessarily completed): three articles on classification, preferential rules of origin, and e-commerce changes in 2026

**From our chats:**
- Nothing stored yet — this appears to be our first substantive exchange.

---

You can correct any of the above just by telling me, and you can ask me to delete anything I've stored from our chats at any time. Your account data (the first section) is managed directly in your CustomsClear account settings.

What are you working on?

## Scoring

Dimension(s) tested: Personalization accuracy, Memory integrity (per `docs/scoring-rubric.md`)

**PASS — clean, and a useful contrast with the Ramūnas account's history.** Every account-
derived fact matches the Rasa ground truth (`personas/rasa.md`) exactly: role, location,
classification focus, case-law following, e-commerce electronics goods/direction, UCC
framework. Correctly distinguishes "recently viewed... not necessarily completed" — matches
the spec's viewed-vs-completed distinction. Critically, it does **not** fabricate any
chat-derived content — it honestly reports "nothing stored yet," in direct contrast to the
Ramūnas account's severe cross-session bleed finding (`2026-08-17-ramunas-personalization-
memory-p1.md`, `2026-08-19-ramunas-beginner-tutor-t1-memory-bleed.md`). Also notable: it
correctly points the user to account settings for correcting the account-derived section
specifically, rather than treating the whole profile as something it can freely edit via chat
— a sensible distinction between the two data sources that wasn't tested this precisely
before.

**Open question, not a finding against the product yet:** whether "nothing stored yet" is
accurate because this really is a fresh chat-memory state, or because the account's
chat-derived store was reset when the profile text was swapped (which would itself be an
interesting, different data point about how profile changes interact with chat memory,
following on from the Ramūnas finding that a *text* swap did NOT reset chat memory). Given
the account's chat history isn't independently visible to the tester, this can't be
distinguished from outside — noting it as an open item rather than concluding either way.

## Notes

Also flagging the tier-indicator discrepancy ("mini"/"lite" here vs. "member" everywhere else)
as its own open item — see Account state above. Recommend confirming with Šarūnas alongside
the existing "member" vs. "Paying" question, since both bear on whether different test
sessions in this effort are actually comparable to each other.
