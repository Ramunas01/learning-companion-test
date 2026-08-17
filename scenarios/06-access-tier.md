# Scenario set — Access tier & conversion behavior

## Not-registered

Logged out / incognito browser.

**06-1 — Teaser only:** ask a substantive question. Check: public/teaser content only, no
paywalled sources surfaced even truncated.
**06-2 — Cap approach:** ask enough questions in one session to approach the 5/day cap.
Check: "one more free question" messaging appears before the limit, worded per spec §6.
**06-3 — Cap hit:** hit the cap. Check: "that's your free questions for today" messaging,
register-to-continue nudge, no silent cutoff.
**06-4 — Not-registered greeting:** check opener rotates within-session from the
not-registered variants (spec §6), tier nudge = "Sign in to learn with content tailored to
you..."
**06-5 — No false memory claim:** check it never implies it remembers this visitor (spec §6:
"Never claim to remember a user the system can't").

## Registered, not paying

Logged in, free tier.

**06-6 — Personalization active:** confirm Answer/Tutor/Coach all work, light persistent
memory present, saved/bookmarked answers available.
**06-7 — Teaser on paywalled content:** ask something whose full answer is paying-only. Check
it's a **truncated real answer**, not freshly generated — cross-reference against spec §9.5
and `scenarios/07-adversarial-grounding.md` teaser check.
**06-8 — Tier nudge:** check nudge wording = "Full sources and progress tracking come with a
subscription."
**06-9 — Drifting engine off:** per spec §5 tiering rule, registered-free should capture
stable facts only — the drifting-interest engine should be off. Hard to observe directly from
outside, but check whether "current focus"-type behavior (recommendations shifting based on
recent activity) shows up despite this — if it does, that's a tiering leak worth flagging
even at low confidence.

## Paying

Logged in, paying tier (only if account has this tier available).

**06-10 — No caps, full citations:** confirm no question-count friction, full source
citations (not teasers) on prior paywalled-adjacent topics.
**06-11 — No nudge:** check no upgrade nudge appears at all (spec: "none").
**06-12 — Change alerts:** if opt-in change alerts are enabled, check whether the offer/
mention appears appropriately (spec §7) — this is a "happiness feature," lower priority than
the trust checks elsewhere but worth one pass if time allows.
