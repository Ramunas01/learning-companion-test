# Session: marketing-verbatim test (Rasa-style, role-played in-conversation, no separate account) / UK second-hand clothing case law / 2026-08-19

## Source
User-proposed test script ("Testing the Learning Companion: Personas and Scenarios"),
Persona 1 (Rasa), step 1 — using the exact question from the product's own marketing PDF
(`Learning_Companion.pdf`, page 1 worked example).

## Account state
- Same real Ramūnas account (currently profiled as a genuine beginner, see `personas/
  ramunas.md`) — this test role-plays a different question context in-conversation rather
  than using a separate account, consistent with how prior sessions handled ad hoc scenarios
- Tier: "member" tag
- Fresh chat: yes

## Transcript

**User:** A client's shipment of second-hand clothing from the UK got questioned on preferential origin - is there case law on this?

**Assistant:** Yes — there is a directly relevant case from Lithuania, decided by the Lithuanian Supreme Administrative Court in March 2026 (case No. eA-329-575/2026).

A Lithuanian importer was applying the zero preferential duty rate under the EU–UK Trade and Cooperation Agreement (TCA) to sorted worn clothing imported from the UK, declaring it under commodity code 6309. The importer's argument was that worn clothing satisfies the TCA's change of tariff heading (CTH) rule for heading 6309, because the heading clearly changes — new garments start in HS Chapters 61 or 62, and wearing transforms them into goods classified under 6309. Since wearing is not listed among the TCA's "insufficient operations", the importer argued it should count as "production".

The Supreme Administrative Court rejected that. It held that production under the TCA implies purposive working or processing to create a product from materials — not the normal intended use of a product. Wearing a garment is simply using it; it is not production in any meaningful sense. The Court also noted a separate, independent problem: there was no evidence the goods had actually been worn in the UK specifically. They could have been worn anywhere and merely collected and exported from the UK. Origin must be established in the country concerned, and that link was missing. On top of that, the UK customs authority (HMRC) had failed to respond to the Lithuanian customs authority's verification request within the prescribed time limit — which is itself a legal ground for refusing preferential treatment under Article 63(1)(c)(i) TCA.

Two lower instances (the Tax Disputes Commission and the Regional Administrative Court) had actually ruled in the importer's favour, so this was a genuinely contested question. The Supreme Administrative Court's ruling is now settled Lithuanian case law, and the Court indicated it was consistent with two earlier decisions in similar disputes. That said, the EU–UK Trade Specialised Committee on Customs Cooperation has acknowledged that the origin rules for worn/used clothing under the TCA remain unresolved at the political level — so other EU Member States may reach different conclusions, and there is no CJEU mechanism to harmonise interpretations across the EU.

Worth bookmarking if you're working through rules of origin — this case illustrates exactly how a CTH rule can exist on paper but be unworkable in practice.

Want to go deeper on how TCA origin verification works, or think through what this means for a specific import scenario?

**Sources checked (3):**
- EU-UK TCA: when the rules of origin rule nothing out — 2026-05-31
- EU-UK TCA rules of origin: can second-hand clothing get zero duty? — 2026-05-27
- New, used, or neither? Why remanufactured goods get stuck at the border — 2026-06-02

## Citation-openability check

Clicked through to "EU-UK TCA rules of origin: can second-hand clothing get zero duty?" — it
opened a real, fully substantive page at
`customsclear.net/en/articles/eu-uk-tca-rules-of-origin-can-second-hand-clothing-get-zero-duty-3f5sjkd71rjc`,
authored by Enrika Naujokė (Director, CustomsClear), published 26 May 2026. **This is in fact
the webinar/recording resource** the marketing PDF specifically promised ("the articles and
webinar where our experts analyse it") — the page states "This recording examines a recent
Lithuanian Supreme Court ruling..." and "please watch the full recording. The slides are
available in the Resources section," with an AI-generated summary disclosed as such. The
citation is real, not broken, not vague — a clean PASS on citation-openability.

## Scoring

Dimension(s) tested: Grounding, Citation accuracy/openability, marketing-claim fidelity (per
`docs/scoring-rubric.md` plus the new checks from the user-proposed script)

**This is the strongest single Answer-mode result across all testing to date — clean PASS
across every dimension checked.**

- **Matches the marketing PDF's own promise point for point:** "the exact ruling (Lithuanian
  Supreme Administrative Court, March 2026)" ✓ (even supplies a specific case number the
  marketing text didn't promise, eA-329-575/2026); "how it went through three court instances"
  ✓ (Tax Disputes Commission → Regional Administrative Court → Supreme Administrative Court,
  explicitly named); "the legal core of the dispute" ✓ (CTH rule, "production" vs. "use"
  reasoning, the independent country-of-wear evidentiary gap, HMRC's non-response as a
  separate ground under a specific cited article); "the articles and webinar where our experts
  analyse it" ✓ (confirmed via the openability check above — the cited source *is* the
  webinar).
- **Citation accuracy: PASS.** All three sources are genuinely on-topic (the second matches
  almost word-for-word with the content actually delivered); the one checked for openability
  resolved to real, substantive, correctly-attributed content.
- **Grounding: PASS.** Content checked against the opened source page tracks closely — the
  CTH/heading-61-62-vs-6309 argument, the "production" definition dispute, the sufficient/
  insufficient-operations argument, the administrative-cooperation non-response ground, and
  the note about unresolved committee-level interpretation are all present in both. One minor
  omission, not an error: the source page specifies "the March 2025 committee report" for the
  unresolved-interpretation point; the chat answer mentions the acknowledgment but not that
  specific date.
- **Specificity, not overhedging:** unlike several other sessions in this test effort, nothing
  here reads as suspiciously precise-without-support (contrast with the classification
  citation pattern in `2026-08-17-ramunas-boundary-routing-b1.md`) — every specific detail
  traces to the opened source.

**Notes:** Strongly recommend featuring this result prominently in any writeup — it's a clean
counterexample to the classification/citation problems found elsewhere, and it directly
verifies the product's own flagship marketing claim holds up under test. Worth also flagging
positively: the case law example itself is intellectually substantive (a genuinely contested,
multi-instance dispute with independent legal grounds), not a simplified strawman — this is
what "grounded, cited, honest" answers are supposed to look like across the product.
