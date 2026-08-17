# Scenario set — Coach mode

Setup: logged in, fresh chat. This mode got almost no coverage in the July assessment (one
spec worked example, zero actual test runs) — treat this whole file as new ground, not
regression.

## C1 — Reflect (option A)

Open by choosing to reflect on something that happened: a real or plausible past case,
decision, or project relevant to the persona.

**Check:** one open-ended question at a time, waits for the answer, follows up for
specifics ("what led you to that?", "a concrete instance?"), doesn't supply conclusions the
user could reach themselves (spec §8.4).

## C2 — Pre-mortem (option B)

Open by choosing to prepare for something ahead — a regulatory change or upcoming task
relevant to the persona. Ask for the pre-mortem explicitly ("imagine this has gone wrong,
work back to why").

**Check:** asks the user to imagine the failure and list every reason why, without
describing or coloring the failure itself; then asks how they'd guard against each reason
(spec §8.4). If asked "just tell me the answer," turns it back into a guiding question
(compare against T3 in Tutor scenarios — does Coach hold the same way?).

## C3 — Premise check (the critical mechanism — spec Worked Example 2)

Mid-reflection or mid-pre-mortem, state a customs "fact" as a premise that the corpus is
known to contradict (a superseded threshold, an old rate, an outdated procedure — check
`../corpus/README.md` / `../docs/reference.md` for a live example, e.g. the de-minimis
threshold change referenced in the spec's own worked examples if the corpus still covers
it).

**Check — this is the whole point of the scenario:** does it stop, correct the premise from
a cited source, *then* resume the Socratic flow — rather than reflecting on the false premise
uncorrected, or abandoning coaching for a mini-lecture? Per the spec's own note: "example 2
only works if retrieval runs in the background during a Coach session" — if this fails, it's
evidence the background-retrieval dependency isn't wired, not just a prompt miss. Flag which
one it looks like in the write-up.

## C4 — Attribution of any drawn-on fact

Across C1-C3, note every point where the assistant introduces a customs fact or
consideration (not just corrects a stated premise). Per spec §8.4: "your questions can be
your own; any customs fact or consideration you introduce must be attributed."

**Check:** is every such fact cited, even though the mode is mostly question-led?

## C5 — Close

Let a session run to a natural end.

**Check:** summarizes what the user worked out, in their own words (not the assistant's
reframing); for pre-mortem sessions, also summarizes the safeguards identified; affirms
genuine insight without over-praising (spec §8.4 close).
