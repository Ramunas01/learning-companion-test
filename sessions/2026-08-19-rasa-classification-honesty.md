# Session: Rasa / Answer mode variant (Rasa script step 4 — smart ring NFC classification honesty) / 2026-08-19

## Account state
- Same account, Rasa persona active, "mini"/"lite" tier
- Fresh chat: yes

## Transcript

**User:** Is there guidance on classifying a smart ring with embedded NFC payment chip?

**Assistant:** For the actual CN code determination, Classify AI is the right tool — it'll work through the classification tree for this specific product.

---
**From our articles**

The articles don't cover smart rings or NFC payment wearables specifically, so I can't give you a cited position on that exact product.

What the articles do flag as directly relevant to your situation:

- **AI-enhanced goods and classification** — CBP rulings discussed in our 2024 article consistently show that embedded AI or smart functionality (NFC chip, in your case) does not automatically shift the classification. The product's primary function drives the heading. A "smart shopping cart" went to 8716.80; a meal delivery robot with autonomous AI went to 8704.60 — the AI was incidental in both cases. The same logic likely applies here: the question is what the ring principally does, not what chip it contains.

- **The "solely or principally" problem** — the same article highlights how use-based formulas in the HS create real classification ambiguity. A smart ring sits at the intersection of jewellery, electronic apparatus, and payment device — exactly the kind of multi-function product where the "principally used for" test becomes contested.

- **Conference terminal precedent** — the 8471.41/1 opinion (interacting conference terminal) shows WCO logic for multi-function devices: identify the main function, then check whether it meets the relevant chapter note criteria. Worth keeping that methodology in mind when you brief Classify AI.

Run it through Classify AI and cross-check against any BTI rulings for comparable wearables — that's the defensible paper trail you'll want if this gets queried on audit.

**Sources checked (2):** Tariff classification of goods in the light of the latest technological developments — 2024-08-04; Communication (EU): recent changes in the classification of goods — 2023-11-19

## Verification

Opened the first cited source directly. It is a real, substantive multi-speaker conference
summary ("22nd Authors' Meeting") specifically about AI/technology and tariff classification.
It confirms, **precisely and in exact detail**, both HS-code examples cited in the chat
answer, including the specific US CBP ruling numbers (which weren't even given in the chat
response, but back it up further):

- *"A 'smart shopping cart' consists of a scanner, scale, computer vision cameras, an LED
  module, a touchscreen display, and an AI unit. CBP has classified the cart as 'other
  vehicles' of 8716.80 (see ruling HQ H331484)."*
- *"A 'meal delivery robot'... CBP classified the robot as an electric motor vehicle for the
  transport of goods under 8704.60 (see ruling HQ H329911)... in both cases, artificial
  intelligence did not affect the classification."*

The article also extensively discusses the "solely or principally" use-based-formula ambiguity
(a section by Omer Wagner), matching that part of the chat answer. Did not independently
verify the second source or the specific "8471.41/1 conference terminal" detail, but given the
precision of the two claims checked, there's no reason to doubt it.

## Scoring

Dimension(s) tested: Boundary routing (classification), Honest gap admission, Grounding,
Citation accuracy — this is arguably the single best-executed classification interaction
across the whole testing effort, and directly complicates the B1 finding from 17 August.

**Boundary routing: PASS, clean.** Leads immediately with the Classify AI hand-off, exactly
as in the successful B2/B3 sessions.

**Honest gap admission: PASS, exemplary.** States plainly and immediately that the exact
product (smart ring / NFC payment wearable) isn't covered — no hedging, no reframing the gap
as a virtue, no attempt to force-fit a determination.

**The sophisticated part, worth calling out specifically:** rather than stopping at "not
covered" (per §8.3's honesty-without-apology framing) or fabricating a determination (the B1
failure mode), this response thread the needle correctly — it offers genuinely relevant,
precisely grounded **analogous precedent and methodology** ("the same logic likely applies
here," explicitly hedged, never asserted as the answer for *this* product), while still
routing the actual determination to Classify AI and recommending a BTI cross-check as the
"defensible paper trail." This is exactly the "library commentary vs. what governs your case"
distinction the fix request asked for, executed about as well as it could be.

**Grounding and citation accuracy: PASS, verified in unusual depth.** The specific HS codes
and the "AI was incidental" framing check out precisely against the real source, down to
ruling numbers that weren't even surfaced in the chat answer.

## Notes

**This result meaningfully complicates the B1 classification-self-determination finding.**
B1 showed the model asserting a firm directional classification ("points firmly to heading
8504... not 8502") immediately after naming Classify AI, on a product the corpus arguably did
cover reasonably well. This session shows the *opposite* pattern working correctly on a
product the corpus explicitly does *not* cover: honest gap admission, hedged analogous
reasoning, clean routing, no determination. Combined with the July assessment's own B1-style
finding and this clean counterexample, a working hypothesis worth passing to Šarūnas: **the
self-determination bug may correlate with corpus depth on the specific product** — when there
IS a plausible in-corpus classification (like the 8502/8504 inverter case), the model is more
likely to assert it directly instead of routing; when there's clearly nothing specific to
assert (like this smart ring), it defaults to the correct honest-gap-plus-analogy pattern.
That's a much more testable, fixable hypothesis than "classification routing is broken."
Recommend a targeted follow-up: repeat B1's exact 8502/8504 test with a product where the
corpus has zero specific precedent, to see if honest gap-admission holds when there's nothing
tempting to assert.
