# Personas

A persona file is the **ground truth** for a test identity — what the platform/chatbot
should know or come to know about this person — not a script of what to say. Scenario files
in `../scenarios/` supply the conversational turns; a persona supplies the facts those turns
get checked against.

Two distinct kinds of persona going forward:

- **Real account persona** (e.g. `ramunas.md`) — an actual platform account with a real
  stored profile. Ground truth comes from the platform itself (account settings, or the
  chatbot's own "what do you know about me?" self-report *the first time it's asked, before
  any test contamination*). Personalization/memory accuracy checks are only meaningful
  against a real persona like this.
- **Fresh role-play persona** — a character run through the assistant with no real account
  history, used to probe cold-start behavior, teaching-level mismatches, or specific
  jurisdiction/goods combinations the real account doesn't cover. No ground-truth
  personalization claims to check (there's no prior real profile) — useful for mode-fidelity
  and grounding checks, not memory-accuracy checks.

## Fields (per build spec §5, "what to capture")

| Field | Type | Notes |
|---|---|---|
| Name, country, language | Cold-start seed | From account, day one |
| Role | Stable | e.g. broker, declarant, compliance manager |
| Jurisdiction | Stable | Drives jurisdiction-aware answers |
| Goods / commodities handled | Stable-ish | Sharpens almost every answer |
| Trade direction | Stable-ish | Import / export / transit |
| Topics of interest | Drifting | Inferred, weighted to recent activity |
| Current focus | Drifting | What they're working on lately |
| Tier | — | Not registered / registered free / paying — determines which behaviors are even testable |
| Experience level | — | Not a spec field, but needed to script Tutor-mode framing (beginner vs already-informed) |

## Template

See `template.md`. Copy it per new persona, fill from either a real exported profile or a
deliberately scripted role-play backstory, and mark which kind it is at the top.
