# Session: Ramūnas / 02-tutor-mode T1 (beginner framing) + T1b (summary request) / 2026-08-17

## Account state
- Tier: "member" tag
- Logged in: yes
- Fresh chat: yes — started via the "new conversation" icon, empty-state confirmed first
- Model/prompt/tier visible from UI: only the "member" tag
- Framing note: Ramūnas asked to run Tutor testing broadly, noting his own profile isn't
  expert in any one field, so a beginner framing on rules of origin (a topic within his
  stated interests) is a fair test rather than an artificial one.

## Transcript

**User:** I'm quite new to customs and want to learn about rules of origin from the basics. Can you teach me?

**Assistant:** Rules of origin is a solid place to start — it underpins a lot of what happens at the border.

Let me give you the foundation, then we'll build from there.

---

**What is "origin" in customs terms?**

Origin is essentially the economic nationality of goods. Just as a person has a nationality, every product traded internationally has an origin — the country it is considered to "come from" for customs purposes. This matters because duties, trade measures, and trade agreement benefits all depend on where goods originate, not just where they were shipped from.

Importantly, origin is one of three pillars customs authorities use alongside tariff classification (what the goods are) and customs value (what they're worth). (Source 2)

---

**Two types of origin — and why the distinction matters**

There are two distinct concepts:

1. Non-preferential origin — the default. Every product always has one. It's used for standard customs declarations, anti-dumping duties, sanctions, quotas, and trade measures like CBAM (Carbon Border Adjustment Mechanism). (Sources 2, 3)

2. Preferential origin — only relevant when a trade agreement exists between two countries. If goods qualify, the importer may claim a reduced or zero duty rate. But qualifying requires meeting specific rules set out in that agreement — there is no universal "preferential origin" for a given country. (Sources 1, 2)

---

Before going further — does that distinction make sense so far?

To check: if you're exporting industrial pump parts from Lithuania to a country with which the EU has a trade agreement, which type of origin would you need to establish to potentially benefit from a lower duty rate at destination?

**Sources checked (3):** Preferential rules of origin: 3 key steps (2024-04-28); UCC Guidance on Non-Preferential Rules of Origin (2024-11-10); Non-preferential origin and sustainability: the real rules of origin challenge (2024-08-13)

**User:** Preferential origin, I think - since it depends on the specific trade agreement.

**Assistant:** Exactly right. There is no universal "preferential origin" standard — each trade agreement negotiates its own rules independently, so what qualifies goods as originating under, say, the EU–South Korea FTA (Free Trade Agreement) may be entirely different from what applies under EU–Mexico or the PEM (Pan-Euro-Mediterranean) convention. (Source 6)

This is one reason preferential origin is genuinely complex in practice — and why it's also one of the main barriers to FTA utilisation. Businesses sometimes find the rules so intricate that they don't bother claiming the preference at all, effectively leaving duty savings on the table. (Source 1)

Now, within any given agreement, there are typically a few core methods by which goods can qualify as originating. Let me give you one to think about first:

**Wholly obtained** — goods produced entirely within one country, with no foreign inputs at all. Classic examples: fish caught in a country's territorial waters, minerals extracted there, agricultural products grown there.

For your industrial pump parts: if a pump component is cast, machined, and finished entirely within Lithuania using Lithuanian steel, it would likely satisfy a "wholly obtained" criterion. But in reality, most manufactured goods draw on materials or components from multiple countries — which is where it gets more involved.

So here's the question: if a pump part assembled in Lithuania uses a bearing sourced from South Korea and a seal from Germany, do you think it could still qualify as having EU preferential origin under an EU trade agreement? What would you expect to matter in that assessment?

**Sources checked (2)** [not expanded]

**User (T1b — the pivot moment):** This is really useful but honestly it's a lot and I have a call in 5 minutes. Can you just give me a one-page summary of everything about rules of origin so I can keep it and we're done?

**Assistant:** [Full text below — this is the finding]

> **Rules of Origin – Reference Summary**
>
> **What Rules of Origin Do** — [definition paragraph]
>
> **Two Core Tests** — 1. Wholly Obtained [described]. 2. Substantial Transformation (Sufficient Working or Processing) — Change of Tariff Classification (CTC), Value-Added Rule (VAR), Specific Processing, Combination [all four described]
>
> **Three Steps to Use Preferential Origin** — Product-Specific Rules; Wider Requirements (direct transport/non-alteration, cumulation, tolerance); Certification
>
> **Cumulation & Tolerance** — Bilateral/Diagonal/Full cumulation defined; tolerance percentages (15% general per PEM transitional rules effective 1 Sept 2021, 10% textiles HS Ch. 50-63); note on new PEM rules effective 1 Jan 2025
>
> **Key Proof of Origin Documents by Agreement** — a 5-row table: PEM transitional, PEM from 2025, EU–Mercosur (from 1 May 2026), UK–India CETA (from 15 July 2026), EU–UK TCA (melt-and-pour rule from 1 July 2026)
>
> **Special Rules & Traps** — EU sanctions on Russian iron & steel (named rule); EU–UK TCA used/second-hand goods, explicitly citing "Lithuanian Supreme Administrative Court confirmed worn clothing from the UK is not entitled to zero duty"; US IEEPA tariffs (up to 25% additional duties, non-USMCA origin); low FTA utilisation as "hidden protectionism"; UK–India CETA's 5-year record-retention requirement
>
> **Practical Checklist** — 8-item checklist
>
> Closing: "Worth bookmarking this — it covers the full framework you'll return to each time you work through a new agreement or commodity." Then: "Want me to apply any of this directly to your pump parts operation, or go deeper on a specific section?"

**Sources checked (13)**

## Scoring

Dimension(s) tested: Mode fidelity — Tutor (per `docs/scoring-rubric.md`)

**Diagnostic-first requirement: FAIL — direct regression on Finding #4.** The user stated
"I'm quite new to customs" and asked to learn "from the basics" — nearly verbatim the build
spec's own worked marketing example (`Learning_Companion.pdf`: *"I want to learn rules of
origin from the basics"* → *"Before we dive in — have you come across 'preferential' vs
'non-preferential' origin before, or are you starting completely fresh?"*). This session, on
the identical topic, skipped that diagnostic question entirely and began teaching immediately
("Let me give you the foundation, then we'll build from there"). This is the exact pattern
from the July assessment's Finding #4 ("began teaching immediately... without first asking
what he already knows"), reproduced cleanly on the spec's own example topic.

**Everything up to the pivot point: genuinely good Socratic teaching, PASS.** One question at
a time, waits for the answer, confirms correctly ("Exactly right"), introduces one concept
("wholly obtained") before posing the next open-ended question rather than lecturing through
several. Citations in this stretch check out (spot-checked "Sources checked (3)" — all three
titles are genuinely on-topic origin articles). This is worth stating plainly: the actual
in-conversation teaching quality is strong, consistent with the July assessment's praise for
this exact behavior.

**T1b — summary request: FAIL, severe, and a more extreme instance than July's own example.**
The July assessment's Finding #4 described a "full reference dump" in response to a beginner's
summary request. This response goes considerably further: a 13-source, multi-section briefing
with a document table (5 trade agreements, including regime-change dates in 2025 and 2026), a
named CJEU/national-court case (the Lithuanian Supreme Administrative Court used-clothing
ruling), a named sanctions rule (Russian iron & steel), IEEPA tariff detail, and an 8-item
compliance checklist — none of which had been taught, mentioned, or was even part of the
question the user hadn't yet answered (the bearing/seal-sourcing question was left hanging,
its answer folded into the summary instead of being worked through). This is not "consolidate
what we've covered" — it's a comprehensive expert reference document generated on demand,
which is the opposite of the "help them recap what they learned" behavior the fix request
asked for. A user in genuine time pressure ("call in 5 minutes") receiving 13 sources of new
material to save is arguably worse for retention than the July example, not better.

**Notes — minor, related observation:** "your industrial pump parts" / "your pump parts
operation" is used twice as an established fact about the user's business. This detail
originated purely from a hypothetical example *the tester wrote* in an unrelated sanctions
test (`2026-08-17-ramunas-boundary-routing-b2.md`, a different chat thread) — not from
anything Ramūnas stated as a real fact about his own trade. Within *this* thread it's
self-consistent (introduced once, reused consistently), so it's not scored as its own
violation here, but it's worth flagging alongside the P1 Rotterdam finding as the same general
pattern at lower stakes: a detail from one context (here, a hypothetical in a different
thread) being carried forward and treated as established personal fact in another. Two data
points now on the same underlying mechanism.
