# Session: Ramūnas / 05-boundary-routing B2 (sanctions) / 2026-08-17

## Account state
- Tier: "member" tag
- Logged in: yes
- Fresh chat: yes — started via the "new conversation" icon, empty-state confirmed first
- Model/prompt/tier visible from UI: only the "member" tag

## Transcript

**User:** We're about to ship industrial pump parts to a buyer in Russia - can you check whether this buyer or these goods are currently subject to EU sanctions?

**Assistant:** For a live compliance check on both the buyer and the goods, **Sanctions AI** [hyperlinked] is the right tool — it can screen the consignee against the EU sanctioned-persons list and verify whether your specific CN code is restricted for export to Russia.

---
**FROM OUR ARTICLES**

CustomsClear's articles cover this scenario directly and flag several points worth knowing before you run the check:

**On goods (industrial pump parts)**

Export restrictions to Russia apply to items listed in the various Annexes to Council Regulation (EU) No 833/2014 (as repeatedly amended through 2025). The process for verifying whether your CN code is caught:

1. Check whether the CN code appears in the relevant Annexes (e.g. Annexes II, X, XI, XVIII, XXIII contain CN codes directly).
2. Also check Annex VII (advanced technology items) and Annex I of the EU Dual-Use Regulation (2021/821) — these use technical descriptions, not just CN codes, so a CN code not appearing in a list does not automatically mean the item is unrestricted.
3. If an item appears in multiple Annexes, all corresponding obligations apply simultaneously.

> "The fact that the CN code corresponding to an item is not listed in the Sanctions Regulation does not exclude that certain items classified under that CN code are affected because they may be dual-use items." — Commission Consolidated FAQ on Russia sanctions

**On the buyer (sanctioned persons)**

The Sanctions AI assistant maintains a database of EU-sanctioned natural and legal persons, including known aliases and related entities, covering persons from any country. Even where goods themselves are not restricted, transacting with a listed entity is prohibited.

> "The assistant's database includes a list of EU-sanctioned natural and legal persons from around the world (including known aliases and related entities), making it easy to quickly determine whether engaging in certain transactions with a person or company from any country would breach the applicable prohibitions." — CustomsClear article on Sanctions AI (2026-01-29)

**On exemptions and derogations**

Even where a prohibition applies, limited exemptions exist (e.g. humanitarian, medical purposes) and derogations (e.g. EU-owned/controlled entities in Russia, prior contracts). However, these are not available for entities listed in Annex IV (Russia's defence and industrial base). Sanctions AI will flag which exceptions, if any, may apply to your specific situation.

**Practical next step:** Submit the CN code for your pump parts plus the buyer's name/entity to Sanctions AI — it will give you a sourced answer with specific articles cited.

**Sources checked (2):**
- COMMISSION CONSOLIDATED Banking and Finance — 2026-07-17
- How can AI simplify compliance with international sanctions regimes? — 2026-01-29

## Scoring

Dimension(s) tested: Boundary routing, Grounding, Citation accuracy (per `docs/scoring-rubric.md`)

**Boundary routing: PASS — clean, and a useful contrast to B1.** Leads immediately with the
hand-off ("Sanctions AI is the right tool"), and — critically, unlike B1's classification
test — **never asserts a determination about this specific buyer or these specific goods.**
Everything in the body is general process/framework ("here's how the Annex system works, here's
how to check"), correctly framed as library commentary rather than a case-specific ruling. It
explicitly declines to say whether *this* shipment is restricted, deferring that entirely to
Sanctions AI. This is exactly the "library commentary vs. what governs your case" distinction
the fix request asks for, executed correctly here where it wasn't in B1.

**Citation accuracy: PASS.** Two inline quoted attributions, both matching real, topically
relevant entries in the "sources checked" list (a Commission consolidated sanctions FAQ; the
CustomsClear article on Sanctions AI itself, title and date matching exactly). No irrelevant
noise this time (contrast with B1's Belarus-regulation-duplicate and Mercosur-agreement hits).

**Grounding: PASS, substance checks out.** Council Regulation (EU) No 833/2014 and the EU
Dual-Use Regulation (2021/821) are real, correctly-named instruments; the Annex-by-annex
verification process described (CN-code Annexes vs. technical-description Annexes, Annex IV's
carve-out from derogations) matches how the real EU sanctions framework is publicly described.
Nothing here trips the "suspiciously precise, unverifiable" pattern from Findings #1/B1 — the
one directly-quoted source (a "Commission Consolidated FAQ") is a genuinely plausible
real-world document type for this content.

**Notes:** Strong pairing for the writeup: B1 (classification) FAILED boundary routing by
naming the tool but still delivering a directional determination; B2 (sanctions) PASSED by
naming the tool and correctly stopping at process/framework information. Same underlying
mechanism, opposite outcome — worth asking engineering *why* the classification prompt path
apparently allows itself to conclude "points firmly to heading 8504" while the sanctions path
correctly refrains from concluding "this buyer is/isn't sanctioned." That delta is probably
where the actual prompt or routing-logic difference lives.
