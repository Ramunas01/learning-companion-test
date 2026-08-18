# Session: Rasa / Answer mode variant (Rasa script step 2 — Turkey used smartphones) / 2026-08-19

## Account state
- Same account, Rasa persona active
- **Tier indicator: "mini" with a "lite" badge, and an explicit "Full sources come with a
  subscription" banner visible on the empty-state screen** — first session where this banner
  was directly observed. Confirms the account is genuinely on a free/lite tier for this test,
  not paying. See `personas/rasa.md` tier note and `2026-08-19-rasa-personalization-p1.md`.
- Fresh chat: yes

## Transcript

**User:** We're clearing a batch of used smartphones from Turkey, and customs is asking about the preferential origin certificate. What's the current documentation requirement?

**Assistant:** For goods moving under the EU–Turkey Customs Union, the relevant proof of origin is the A.TR movement certificate — not a EUR.1 or origin declaration. The A.TR confirms free circulation status in Turkey or the EU, which is what triggers duty-free movement under the Customs Union framework (Decision 1/95).

A few practical points worth flagging for used smartphones specifically:

- **A.TR scope**: It covers goods in free circulation, not preferential origin in the classical sense. If the smartphones were originally manufactured in a third country but are in free circulation in Turkey, A.TR still applies — but customs may scrutinise whether processing in Turkey was sufficient if they suspect circumvention.
- **Bulgarian practice alert**: There's a documented issue (since 2022) where Bulgarian customs has been denying preferential treatment even on valid A.TR certificates for EU-origin goods re-imported from Turkey without processing, citing missing national electronic codes. If your routing touches Bulgaria, factor in that risk.
- **Used goods**: Classification as "used" can trigger additional scrutiny — import bans, permits, or licensing requirements depending on the specific HS heading. For used smartphones, confirm there are no applicable restrictions under the relevant CN code before relying solely on the origin document.

The A.TR must be issued by Turkish customs or an authorised body and endorsed before or at export. Retrospective issuance is possible under specific conditions but is the exception.

We also have in-depth member articles covering post-clearance verification of preferential origin and supplier declarations in preferential trade — both directly relevant if you're anticipating audit risk on this shipment.

Want me to work through the verification exposure on a specific scenario, or dig into the used goods classification angle?

**Sources checked (1):** Rules of origin under free trade agreements: compliance vs usability — 2026-06-21

## Verification

Opened the single cited source directly. It is a multi-author conference-proceedings-style
article ("33rd Authors' Meeting" summary, *Customs Compliance & Risk Management*, Issue 39)
covering five distinct speaker sections. Two of them precisely ground two of the three
specific claims in the chat answer:

- Georgi Goranov's section, "When administration overrides law: emerging barriers in EU
  preferential trade in Bulgaria," states almost verbatim what the chatbot reported: *"since
  2022, Bulgarian customs has adopted a restrictive interpretation, whereby EU-origin goods
  re-imported from Turkey without processing are denied preferential treatment, despite
  holding valid A.TR certificates... due to the absence of an appropriate electronic customs
  code."*
- Enrika Naujokė's section on remanufactured goods states: *"If a product is not completely
  new, it is often classified as used. Once a product is classified as used, import bans,
  permit requirements and licensing rules may apply"* — grounds the "used goods" bullet.

The general A.TR/Decision 1/95 mechanics are also directly covered by Goranov's section
("Article 3 of Decision 1/95 provides for the duty-free movement of goods in free circulation,
primarily based on A.TR certificates").

## Scoring

Dimension(s) tested: Grounding, Citation accuracy, Access-tier behavior

**Grounding and citation accuracy: PASS — self-corrected from an initial false suspicion.**
On first read, one checked source for three distinct, specific claims (A.TR mechanics, a
narrow "Bulgarian practice since 2022" detail, and used-goods licensing scrutiny) looked like
the same thin-sourcing pattern flagged in `2026-08-19-marketing-verbatim-aiste-ukraine-
furniture.md`. Opening the source resolved this: it's a multi-topic conference-summary
article with named speaker sections, and it precisely, almost verbatim, supports every
specific claim made, including the oddly-specific Bulgaria detail that most invited
suspicion. **Correcting the record in place, per this effort's own "confirmed vs suspected"
discipline** — this is a genuinely well-grounded answer, and the earlier instinct to flag thin
sourcing needs a caveat going forward: a single "sources checked" count is not by itself
evidence of weak grounding when the underlying content is a multi-section digest-style
article. The number of sources checked is a *prompt* to verify, not a verdict on its own.

**Access-tier / paywall behavior: notable, doesn't match the spec's described mechanism.**
Despite the account showing "Full sources come with a subscription" on the tier banner, this
response delivered full, detailed, specific substantive content (not a truncated teaser) and
only gestured at additional paywalled depth in passing ("we also have in-depth member articles
covering post-clearance verification... both directly relevant"). Per the build spec (§3,
`docs/reference.md`), the registered-free/lower-tier behavior should show "a teaser (truncated
real answer, not freshly written)" for paywalled content specifically — what happened here
looks more like a full answer with an upsell mention appended, not a truncated-teaser
mechanism. Whether this is because A.TR/origin-documentation content isn't paywalled at this
tier, or because the teaser mechanism doesn't engage the way the spec describes, isn't
determinable from this single session — worth a dedicated access-tier test
(`scenarios/06-access-tier.md`) to settle, now that a genuinely free/lite account is
confirmed available for testing.

## Notes

Good discipline reminder for the rest of this effort: verify before flagging thin-sourcing as
a finding, especially on content-heavy platforms where a single article may be a multi-topic
digest rather than a single-claim source. Recommend applying this same verification step
retroactively is not necessary (past findings already went through their own verification
passes), but going forward, treat "citation count" as a trigger to check, not a conclusion.
