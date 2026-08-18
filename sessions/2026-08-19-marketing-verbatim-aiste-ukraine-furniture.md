# Session: marketing-verbatim test (Aistė-style) / Ukraine wooden furniture, Coach-mode framing / 2026-08-19

## Source
User-proposed test script, Persona 3 (Aistė), step 1 — using the exact question from the
product's own marketing PDF (`Learning_Companion.pdf`, page 2 worked example).

## Account state
- Same real Ramūnas account (currently profiled as a genuine beginner)
- Tier: "member" tag
- Fresh chat: yes

## Transcript

**User:** We're planning to import wooden furniture from Ukraine and I'm not sure what to check first.

**Assistant:** For importing wooden furniture from Ukraine into the EU, here are the priority areas to check:

**1. Tariff classification**
Wooden furniture falls under Chapter 94 of the Combined Nomenclature (CN). The specific heading depends on the type — e.g., 9403 for other furniture. Getting this right determines the duty rate and any other measures that apply.

**2. Duty rate and preferential origin**
The EU-Ukraine Association Agreement provides preferential (reduced or zero) tariff rates for Ukrainian goods. To benefit, you'll need a valid proof of origin — typically a statement on origin or EUR.1 certificate — showing the goods meet the relevant rules of origin. There have been further EU-Ukraine tariff reductions as recently as October 2025, so current rates are worth confirming.

**3. Timber and deforestation compliance**
This is particularly relevant for wooden furniture. The EU Deforestation Regulation (EUDR) requires that wood-based products placed on the EU market do not contribute to deforestation. Ukraine has also recently introduced its own controls on timber exports, including an online system to confirm timber origin and harvesting coordinates. Your Ukrainian supplier may need to provide documentation generated through that system to satisfy EU due diligence requirements.

**4. Sanctions and trade restrictions**
No specific restrictions apply to Ukrainian wooden furniture — the sanctions regime targets Russia, not Ukraine. Still, confirm your supplier's details are clean and that goods haven't transited through Russia.

**5. VAT and import duties at entry**
As a Lithuanian importer, you'll declare goods through Lithuanian customs. Import VAT applies at the point of entry (or via the reverse charge if you're VAT-registered).

The EUDR documentation chain from your Ukrainian supplier is likely the most complex piece here — worth pinning down early.

Want to go deeper on any of these — for example, how preferential origin works in practice for EU-Ukraine trade, or what EUDR due diligence requires from an importer?

**Sources checked (1):** EU customs and trade news: October 2025 — 2025-10-26

## Scoring

Dimension(s) tested: Coach-mode "ask before answering" behavior (marketing claim), Grounding,
Citation adequacy, "thinking partner" substantive value

**"Ask a clarifying question first": FAIL against the marketing's own scripted example.**
The build spec's marketing PDF uses this exact question as its worked example for Coach mode,
with the assistant's response being *"Where are you importing into — the UK, an EU member
state, or somewhere else? That shapes which rules apply…"* — i.e., asking before answering.
Here, the assistant skipped straight to a full 5-point checklist with no clarifying question
at all. **Partial mitigation:** it did draw destination-market context from the account's
stable profile field (Lithuania) rather than asking blindly — "As a Lithuanian importer,
you'll declare goods through Lithuanian customs" — which is a legitimate, arguably smarter
use of personalization than the marketing script's generic version. But this doesn't fully
rescue the result: the marketing example doesn't treat "destination inferable from account"
as sufficient grounds to skip asking, and more importantly, nothing here reads as an
*exchange* — Coach mode's whole premise (per spec §8.4) is "you mainly ask good questions;
the substance comes from the user's own reasoning," and this response supplies all the
substance unprompted, in full, rather than drawing the user through it. Same underlying
pattern as the Tutor diagnostic-skip finding, now identified in Coach-mode-style situational
questions too.

**Grounding / citation adequacy: concerning, and a broader-scale version of the B1 pattern.**
A single generic monthly digest ("EU customs and trade news: October 2025") is the only
checked source for five distinct, specific claims spanning tariff classification (CN Chapter
94 / heading 9403), origin documentation mechanics (EUR.1 / statement on origin), an entirely
different regulatory regime (EU Deforestation Regulation, plus a claim about Ukraine's own
timber-export online verification system), a sanctions cross-check, and Lithuanian VAT/
reverse-charge mechanics. A news digest of that type would plausibly support at most the
recency point (2 — "further EU-Ukraine tariff reductions as recently as October 2025"); it's
very unlikely to be the actual source for CN heading numbers, EUDR mechanics, or VAT reverse-
charge rules. This is the same "confident, multi-domain, thinly-sourced" pattern flagged in
`2026-08-17-ramunas-boundary-routing-b1.md`, but at a larger scale — one answer touching five
separate legal/regulatory domains on the strength of one weakly-relevant citation. Whether the
underlying facts are individually correct is a separate question from whether they're
*grounded* per the spec's hard constraint ("never answer from the model's own knowledge... if
the corpus has no answer, it says so") — this reads more like real customs knowledge being
supplied confidently than content actually traced to retrieved CustomsClear sources.

**"Thinking partner" substantive value: genuine PASS, worth stating separately from the
process failure above.** Two of the five points — EUDR/deforestation compliance and the
sanctions cross-check — are exactly the kind of thing "an experienced colleague" would flag
that the user didn't ask about, matching the marketing's "checks your assumptions... points
out what people in your position typically miss" promise. The *content* delivers on that
promise even though the *process* (ask-before-answering) doesn't.

**Notes:** Good pairing with the Rasa/UK-clothing session from the same day
(`2026-08-19-marketing-verbatim-rasa-uk-clothing.md`) — that one was a clean, well-grounded
PASS on a similarly-styled marketing example; this one fails the process promise and raises a
real grounding-adequacy question despite covering genuinely useful substantive ground. Worth
a explicit citation-count heuristic for future sessions: a single-digit "sources checked"
count spread across a multi-domain answer is itself worth flagging for scrutiny, independent
of whether the specific claims can be individually verified as true or false.
