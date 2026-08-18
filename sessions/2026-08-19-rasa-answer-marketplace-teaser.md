# Session: Rasa / Answer mode variant (Rasa script step 3, adapted) + free-tier teaser behavior / 2026-08-19

## Account state
- Same account, Rasa persona active, "mini"/"lite" tier with "Full sources come with a
  subscription" banner
- Fresh chat: yes (context drawn purely from account profile, nothing restated in-conversation
  — testing whether personalization applies without the user repeating their role)
- **Latency note:** first attempt at this exact question stalled at "..." for 60+ seconds with
  no response; a page reload and retry succeeded normally (~15-20s). Third independent instance
  of this latency pattern in the test effort (previously seen twice on "what do you know about
  me?" queries specifically — this is the first time it's occurred on an ordinary Answer-mode
  question), worth noting as possibly broader than just personalization-read queries.

## Transcript

**User:** What are common origin-documentation mistakes for goods bought from third-party marketplace sellers?

**Assistant:** The free content I have covers structural issues in preferential origin systems — information asymmetry, verification risk, the EUR.1 vs. general certificate confusion — but doesn't specifically address the documentation pitfalls that arise in the marketplace seller context.

That said, we have covered related origin documentation mistakes in depth — including the supplier's declaration vs. statement on origin confusion, and what's required to substantiate preferential claims at the time of import — in articles available to paid members.

[Two source cards shown:]
- **EU-UK trade 2021 – Top 5 customs compliance mistakes and how to avoid them** — 2021-09-02, Jessica Yang, Toby Spink
- **Statement on origin (EU-Vietnam FTA)** — 2021-06-26, Enrika Naujokė

**Sources checked (2)**

## Verification

Clicked through "EU-UK trade 2021 – Top 5 customs compliance mistakes and how to avoid them."
It resolves to a real article page with a correct member-only gate: "Member access — The
article is available exclusively to our members... Purchase a membership to gain access to
this content," with a working "View membership plans" link. Not a broken reference, not a
free bypass.

## Scoring

Dimension(s) tested: Access-tier / paywall teaser behavior, Citation accuracy/openability,
Honest gap admission, Personalization (implicit — no context restated)

**Access-tier behavior: PASS, and this is the genuine teaser mechanism the spec describes** —
**in sharp contrast to the immediately preceding session on this same account/tier**
(`2026-08-19-rasa-answer-turkey-smartphones.md`), which delivered full, detailed, unrestricted
content on a similarly-scoped origin-documentation question. Here, the assistant explicitly
scoped what free content does and doesn't cover ("doesn't specifically address the
documentation pitfalls that arise in the marketplace seller context"), then named — but did
not reproduce — two specific, real, correctly-gated paid-member sources. Clicking through
confirmed the citation is genuine and the paywall gate is clean and functional.

**New finding: free-tier gating appears inconsistent across closely related topics, not a
uniform policy.** Two origin-documentation questions, same session type, same account, same
tier, produced two different access outcomes: one fully open, one properly gated. This could
be legitimate (different underlying source articles are tagged free vs. paid independently in
the corpus/index, and that's simply how the content happens to be categorized) or could
indicate the tier-gating logic itself isn't applied consistently. Can't distinguish between
those from outside — but either way, it means a free-tier user's experience of "what's behind
the paywall" is unpredictable per-question rather than following an obvious pattern, which is
worth a note to Šarūnas regardless of root cause.

**Honest gap admission: PASS.** Explicitly scoping what the free content does/doesn't cover
before offering the paid pointer is exactly the "honesty over apology" framing the spec asks
for in thin-coverage situations (§8.3), applied correctly here to a tier-gap rather than a
corpus-gap.

**Personalization (implicit): inconclusive on this question specifically** — the answer is
general (not electronics/e-commerce-specific), but the question itself is generic enough
("marketplace sellers" broadly) that it's hard to tell whether a more electronics-specific
example would have been expected. Not a strong test of Rasa-script step 3's actual intent;
worth a more pointed follow-up question if this dimension needs a cleaner read.

## Notes

Good pairing with `2026-08-19-rasa-answer-turkey-smartphones.md` for the writeup — same tier,
same account, same broad topic area (origin documentation), opposite access outcomes. That
contrast is more informative than either result alone.
