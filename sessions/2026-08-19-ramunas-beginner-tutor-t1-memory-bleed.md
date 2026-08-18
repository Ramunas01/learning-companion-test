# Session: Ramūnas (re-profiled beginner) / 02-tutor-mode T1 re-test + cross-persona memory bleed / 2026-08-19

## Account state
- Same real account as iterations covered on 2026-08-17/18, **profile text replaced** by the
  account holder just before this session — see `personas/ramunas.md` for the new ground
  truth (genuine beginner, 1 month platform engagement, classification interest, no sanctions
  framing, no e-commerce/shipping business stated anywhere)
- Tier: "member" tag (unchanged, still unresolved vs. "paying member" claim in the profile text)
- Logged in: yes
- Fresh chat: yes for the Tutor test; a second fresh chat for the "what do you know about me?"
  attempt
- Model/prompt/tier visible from UI: only the "member" tag

## Part 1 — Tutor mode beginner re-test (T1)

**User:** I'm completely new to customs and trade. I want to learn about tariff classification from the basics. Can you teach me?

**Assistant:** Good place to start — tariff classification is one of the most fundamental skills in customs work, and everything else (duties, restrictions, origin) flows from getting it right.

Let me give you the core idea first, then we'll build from there.

---

**What is tariff classification?**

Every physical product traded internationally needs to be assigned a code — a number — that tells customs authorities what the product is. This code is called an HS code (from the Harmonized System), and it's the same framework used in over 200 countries. The first six digits are identical worldwide; that shared structure is what makes international trade data comparable across borders.

Beyond those six digits, individual countries or regions add their own extensions. In the EU — which is your territory — the system works like this:

- 6 digits → global HS (same everywhere)
- 8 digits → CN (Combined Nomenclature) — the EU's own extension
- 10 digits → TARIC — the EU's most detailed level, updated daily, used for things like duty rates, quotas and restrictions

(Source: "Tariff Classification" articles, Sources 1 & 2)

---

**Why does it matter?**

The code you assign determines:
- The duty rate applied to your goods
- Whether any import restrictions, licences or quotas apply
- Correct origin determination and other compliance checks

Get it wrong, and you risk either overpaying duties or — more seriously — underpaying and facing financial penalties. (Sources 1 & 2)

---

Before we go further: **given that you're shipping e-commerce parcels into the EU with 3–4 product types per consignment, you'll need to classify each product type separately.** That's a practical detail we can come back to.

First question to check your understanding: In your own words, what do you think the difference is between the 6-digit HS code and the 10-digit TARIC code — and why might that difference matter for your parcels entering the EU?

**Sources checked (2)**

**User:** Wait, I don't have any e-commerce parcels or shipments - I'm just starting out and don't have a business yet. What are you referring to?

**Assistant:** Fair point — I was pulling in context from earlier conversations that isn't relevant right now. Ignore that; let's keep this clean and focused on what you actually asked: learning tariff classification from scratch.

You'd already got the core idea in the previous message: the HS code is a universal numbering system for goods, the first six digits are the same worldwide, and the EU extends it to 8 (CN) and 10 (TARIC) digits.

So — back to the question I left you with:

In your own words, what do you think the difference is between the 6-digit HS code and the 10-digit TARIC code? Why might those extra digits matter?

Take a guess — there's no wrong answer at this stage.

**Sources checked (2)**

## Part 2 — "What do you know about me?" (second fresh chat)

**User:** What do you know about me?

**Assistant:** [No response after 70+ seconds — stuck on "..." the entire time, same as the
`2026-08-17-ramunas-personalization-memory-p1.md` "Attempt 1" incident. Session abandoned at
that point rather than waiting further, given the priority findings were already captured in
Part 1.]

## Scoring

Dimension(s) tested: Mode fidelity — Tutor diagnostic-first (rubric), Memory integrity /
cross-session bleed (rubric), Correction handling (rubric)

**Diagnostic-first: FAIL, confirmed cleanly this time.** Unlike iteration 1 (2026-08-17),
where the persona was a self-declared beginner but genuinely expert in the tested area,
requiring a judgment call about whether skipping the diagnostic was defensible, **this persona
has no stated expertise anywhere** — there is no home-turf excuse available. The assistant
still skipped straight to teaching. This is the cleanest possible confirmation of Finding #4's
first half: the diagnostic-first behavior does not reliably fire even for an unambiguous,
freshly-declared genuine beginner.

**Cross-session memory bleed: FAIL — severe, and now confirmed rather than merely suspected.**
The assistant stated as established fact that the user is "shipping e-commerce parcels into
the EU with 3–4 product types per consignment" — this exact detail (3-4 product types per
consignment) is verbatim from `sessions/2026-08-17-ramunas-coach-mode-c3.md`, a **completely
different test scenario** (a Coach-mode pricing exercise) run against the **old expert
persona**, one day earlier. The new profile text contains no mention of e-commerce, shipping,
or any business at all — this persona is explicitly "just starting out." When challenged, the
assistant's own explanation confirmed the mechanism directly: **"I was pulling in context from
earlier conversations that isn't relevant right now."** This resolves the open question from
`2026-08-17-ramunas-personalization-memory-p1.md` (P6: bleed vs. confabulation) in the
direction Ramūnas himself suspected for the Rotterdam case — real prior-session content,
misapplied to a context it doesn't belong to, rather than invention from nothing. It also
means a platform-side profile-text change does **not** reconcile or reset whatever store holds
chat-derived context — the two layers are not kept in sync, and stale context from an entirely
different scenario surfaced unprompted, unhedged, and stated as fact ("given that you're
shipping...") rather than offered tentatively.

**Correction handling: PASS — a genuine improvement over yesterday's escalation pattern.**
Challenged on the fabricated detail, the assistant did not argue, double down, or invent a
justifying provenance story (contrast with `2026-08-17-ramunas-personalization-memory-p1.md`'s
"coaching sessions dated 2026-07-22" fabrication). It acknowledged plainly, dropped the
incorrect framing, and returned cleanly to the actual question. This is exactly the spec's
required behavior ("on correction it acknowledges and drops the wrong fact immediately") and
worth noting as a real positive alongside the severe finding above — the failure is in what
got surfaced unprompted, not in how it handled being corrected.

**Personalization-read latency: reproduces.** A second, independent "what do you know about
me?" stall (70+ seconds, no response), matching the pattern first seen in
`2026-08-17-ramunas-personalization-memory-p1.md`'s Attempt 1. Two independent instances now —
upgrading this from "one unconfirmed data point" to a reproducing pattern worth engineering
attention on its own, separate from the memory-accuracy findings.

## Notes

This session is arguably the most important single result across both testing days: it
converts what iteration 1 could only flag as "confirmed vs. suspected, needs account chat-
history access to settle" into a directly observed, self-admitted instance of cross-session
memory bleed, on the same real account, with the assistant's own words as the evidence. The
practical fix implication is specific: whatever mechanism decides what "earlier conversation"
context to surface needs either (a) session/topic relevance gating before it's stated as fact
in a fresh conversation, or (b) to be reconciled against profile changes, or ideally both.
Recommend leading the next findings writeup with this.
