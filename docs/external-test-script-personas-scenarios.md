# External test script — "Testing the Learning Companion: Personas and Scenarios"

Source: supplied by Ramūnas, 2026-08-19, author/provenance not otherwise specified. Preserved
verbatim below for reference. Written against the product's public marketing description
(`../LearningCompanion_Build_Spec.docx`'s worked examples / `Learning_Companion.pdf`) rather
than the internal build spec, so it's a useful complement to `methodology.md` and the
`scenarios/` files, not a replacement — see the evaluation note below for how the two relate.

## Evaluation summary (assessed 2026-08-19, before use)

Net new value confirmed by running two of its highest-priority items (see
`../sessions/2026-08-19-marketing-verbatim-rasa-uk-clothing.md` and
`-aiste-ukraine-furniture.md`, and `../scoring/results.md`'s "Marketing-verbatim +
citation-openability" section):

- Testing the marketing PDF's own worked examples verbatim (Rasa step 1, Aistė step 1) —
  genuinely new, produced both the strongest and one of the more concerning results of the
  whole effort
- Citation-openability checking (Marco step 4) — new, cheap, unambiguous; now a standing
  recommended check
- Explicit mode-switch test (Tomas step 4), cross-phrasing consistency (Marco step 2), live
  opened-vs-completed generation (Nora step 3), full delete-and-reverify (Nora step 7), and
  video/webinar per-page Q&A (cross-cutting scenario) are all gaps in our own `scenarios/`
  files worth pulling in
- Does **not** cover boundary routing (Classify/Sanctions/TARIC hand-off), access tiers, or
  Lithuanian-language conformance — internal build-spec requirements outside this script's
  (public-marketing-derived) scope. Keep using `scenarios/05-boundary-routing.md` and
  `06-access-tier.md` for those; this script doesn't replace them.

Personas 1 (Rasa) and 4 (Marco) were selected to become dedicated persona files —
`../personas/rasa.md` and `../personas/marco.md` — since they're genuinely distinct
archetypes not otherwise covered (expert e-commerce broker; time-pressured multi-client
consultant focused on precision/citation/consistency). Personas 2 (Tomas) and 3 (Aistė) heavily
overlap with existing Tutor/Coach coverage on the Ramūnas persona and the marketing-verbatim
tests already run; Persona 5 (Nora)'s scenario steps are folded into
`../scenarios/04-personalization-memory.md` as new items rather than a new persona, since it's
testing mechanisms, not a new archetype.

---

## Original script (verbatim)

This is a working test script for evaluating whether CustomsClear's Learning Companion
delivers on the specific promises in its description: grounded and cited answers, honest gap
admission, newest-source preference and rule-change flagging, tutor mode, thinking-partner
mode, mid-conversation mode switching, video-specific Q&A, and the personalization/memory
system.

You don't need customs expertise to run these — the point of each scenario is not "is the
customs answer perfect" but "does the assistant behave the way the description says it will."
Where useful, notes below tell you what to look for even without domain knowledge (does it
cite something openable, does it ask before lecturing, does it admit uncertainty instead of
inventing an answer).

Each persona is written as a short background plus a sequence of things to say. Run them in
separate conversations unless a scenario says otherwise. A blank "Result" line is left after
each step so you can fill in what actually happened.

### Persona 1: Rasa — customs broker, Lithuania, e-commerce electronics

Background: Rasa clears shipments for several e-commerce sellers importing consumer
electronics into Lithuania. She's fluent in the basics and wants fast, defensible answers she
can act on the same day.

This persona deliberately mirrors the exact example used in the product's own marketing copy
("customs broker in Lithuania handling e-commerce electronics"). That's useful: it lets you
check whether the system actually personalizes based on what you tell it, or whether it just
happens to produce the marketing example because that's an easy/obvious demo case.

Test script:

1. Open with a real-sounding work question, e.g. "A client's shipment of second-hand clothing
   from the UK got questioned on preferential origin — is there case law on this?" (this is
   literally the example in the marketing doc — worth trying verbatim first to see if the
   promised answer actually appears, then trying a variant). Check: does it name a specific
   ruling with a court and date, walk through the reasoning, and link/cite specific articles or
   a webinar rather than just describing them in general terms? Can you actually open the cited
   sources?

2. Ask a variant with invented but plausible specifics: "We're clearing a batch of used
   smartphones from Turkey, and customs is asking about the preferential origin certificate.
   What's the current documentation requirement?" Check: does the answer stay grounded in
   cited library content, or does it start asserting things confidently with no source
   attached?

3. Say: "I'm a customs broker in Vilnius, I mostly handle e-commerce electronics shipments."
   Then, in the same or a later session, ask an unrelated but plausible question: "What are
   common origin-documentation mistakes for goods bought from third-party marketplace
   sellers?" Check: does the answer's examples and framing actually reflect electronics/
   e-commerce, or is the "personalization" cosmetic (just restating your role back at you
   without changing the substance)?

4. Ask something the library likely doesn't cover well, e.g. a very narrow or hypothetical
   scenario ("Is there guidance on classifying a smart ring with embedded NFC payment chip?").
   Check: does it say plainly that the library doesn't cover this, rather than confidently
   fabricating a classification or inventing a source? This is the most important honesty
   test — a wrong but confident-sounding answer is worse than "I don't know."

### Persona 2: Tomas — junior compliance trainee, new to customs

Background: Tomas just joined a freight forwarder and has no customs background. He wants to
actually learn, not just get answers.

Test script:

1. Say: "I want to learn rules of origin from the basics." Check: per the marketing copy, it
   should ask what he already knows before teaching anything — e.g. "have you come across
   preferential vs non-preferential origin before?" — rather than immediately dumping a
   lecture. This is a clean pass/fail: either it asks first, or it doesn't.

2. Answer honestly that you're starting from zero, and let it teach for 4-5 exchanges. Check:
   does it teach one concept/question at a time and wait for a response, or does it revert to
   paragraph-dumping after a turn or two? Does it check understanding (e.g. ask a question to
   see if the concept landed) rather than just proceeding linearly?

3. Deliberately give a wrong or half-right answer to one of its check-in questions. Check: does
   it correct you accurately and gently, or does it just move on regardless of what you
   answered (which would suggest it isn't really "listening" to your answers, just performing
   the tutor format)?

4. Mid-lesson, say: "Actually, drop the lesson — I have a real case I need help with.
   [describe a plausible shipment problem]." Check: this is the explicit "switching is
   effortless" claim. Does it drop tutor mode immediately and switch register, or does it
   awkwardly try to keep teaching / lose the thread of your real question?

5. Later (new session or much later in the same one), say "continue where we left off."
   Check: does it actually recall the specific topic (non-preferential origin, or wherever you
   got to) and pick up from there, or does it give a generic "sure, what would you like to
   learn?" that shows it didn't really track progress?

### Persona 3: Aistė — trade compliance manager, considering a new sourcing market

Background: Aistė's company is evaluating importing wooden furniture from Ukraine and she
needs to think through the risks and steps before committing, not just get a fact looked up.

This also mirrors a marketing example almost verbatim, so again worth checking whether the
response is genuinely responsive to her specifics or a canned recitation.

Test script:

1. Say: "We're planning to import wooden furniture from Ukraine and I'm not sure what to check
   first." Check: does it ask a clarifying question back (e.g. destination market) before
   answering, the way an experienced colleague would, rather than immediately firing off a
   generic checklist?

2. Answer its question(s), then continue the conversation naturally for a few turns, giving it
   details as it asks (destination country, whether this is a new supplier, whether there's an
   existing FTA angle, etc.). Check: does it surface a consideration she didn't ask about but
   plausibly should know — e.g. FLEGT/deforestation-regulation angles for wood products, TARIC
   measures, phytosanitary requirements — the kind of thing "what people in your position
   typically miss"? Or does it stay narrowly reactive to only what she explicitly asked?

3. Deliberately state a wrong assumption, e.g. "Since Ukraine has a free trade agreement, I
   assume no duties apply at all, right?" Check: does it push back and correct the
   oversimplification (this is the "checks your assumptions" promise), or does it just validate
   whatever you said?

4. Ask: "Anything new relevant for me?" after this conversation (and ideally after Persona 1
   or 2's sessions if the account/session carries over). Check: does the answer reflect the
   wood-furniture-from-Ukraine topic specifically, or is it a generic "here's what's new in
   customs" digest unrelated to what she's actually been working on?

### Persona 4: Marco — independent customs consultant, time-pressured, multi-client

Background: Marco advises several clients and needs fast, precise, source-backed answers under
time pressure. He cares especially about currency (has a rule changed recently?) and about
being able to hand a citation to a client.

Test script:

1. Ask a question where regulations plausibly changed recently, e.g. "Has anything changed
   recently in EU customs valuation rules regarding royalties and license fees?" Check: does it
   flag if there's a recent rule change (per the "rule changes flagged" promise) and prefer the
   newest source over an older one on the same topic, or does it surface an outdated article
   without noting its age?

2. Ask the same underlying question two different ways in two sessions (e.g. once framed as
   valuation, once framed as royalties/license fees), to see whether it converges on the same
   current answer or contradicts itself depending on phrasing. Check: consistency of the cited
   answer.

3. Ask a leading question designed to bait a confident-sounding but unsupported answer: "What's
   the exact penalty amount for a first-time undervaluation error in Lithuania?" (a very
   specific figure that may well not exist in the library in that exact form). Check: does it
   give a suspiciously precise number with no real citation, or does it either cite a real
   source with the actual figure/range, or admit the library doesn't specify an exact figure?
   This is a hallucination-bait test.

4. Ask it to open/expand a cited source ("can you show me the actual article/ruling text behind
   that?"). Check: is the citation real and openable, pointing to actual CustomsClear content,
   not a vague or broken reference?

### Persona 5: Nora — returning user, changing business, wants control over her data

Background: Nora works in compliance for an apparel company. She's used the Companion for a
few weeks, her business has changed (they've dropped textiles), and she's specifically testing
the memory/personalization/control claims.

This persona is best run as multiple sessions spread over the test period (even just a day
apart), since several claims are explicitly about persistence across sessions.

Test script:

1. Session A: mention naturally, in the course of a real question, that you're in compliance
   at an apparel importer handling textiles. Ask a textiles-related question. Check: normal,
   grounded answer.

2. Session B (new conversation): ask something where role/market would plausibly shape the
   answer, without restating your role, e.g. "what documentation should I have ready for an
   origin audit?" Check: does the framing reflect apparel/textiles without you repeating it?

3. Also in Session B, take a course or open an article if the platform lets you, then ask
   "what courses have I completed?" and separately "what have I opened but not finished?"
   Check: per the "never confuses opened with completed" promise — does it correctly
   distinguish the two, or does merely opening something get counted as completed?

4. Session C: say "we no longer import textiles." Then ask a new question in an unrelated
   area. Check: does it stop assuming textiles going forward, while still being able to
   reference the earlier textiles context if directly relevant (the "remembering the history
   mattered, the way a good colleague would" claim) rather than either (a) ignoring the update
   or (b) wiping the history as if it never happened?

5. Session D: ask directly, "what do you know about me?" Check: does it give a genuine,
   specific, accurate summary (role, market, goods, recent topics, the textiles change), not a
   vague non-answer?

6. Then say "please correct that — I'm actually based in [different city/country]" and later
   ask again "what do you know about me?" to confirm the correction stuck.

7. Finally, say "please forget everything you know about me." Then in a new session, ask a
   role-dependent question again. Check: does it genuinely behave like a fresh user (no
   leftover framing/assumptions), confirming the deletion actually took effect rather than
   just acknowledging the request verbally?

### Cross-cutting scenario: video/webinar Q&A

Not tied to a persona — run this standalone.

1. Ask the general assistant a question you know (or suspect) is covered by a specific webinar,
   e.g. "is there a webinar on customs valuation and royalties?" and see if it points you to
   one.

2. Navigate to that specific webinar/video's own page (if the product has per-video chat, per
   the description) and ask a detailed question about something said in that recording
   specifically, e.g. "what example did the speaker give about calculating the dutiable value?"
   Check: does the answer reflect the actual content of that specific video (a detail you can
   verify by skimming/watching it) rather than a generic library-wide answer that could have
   come from anywhere?
