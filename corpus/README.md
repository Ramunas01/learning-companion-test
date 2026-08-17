# Corpus

The article corpus the Learning Companion retrieves from — used here to pick real,
in-corpus question topics for scenarios so tests hit actual indexed content rather than
guessing (an untargeted question risks accidentally testing empty-retrieval behavior instead
of the intended dimension).

**Not in this repo.** Source materials live at
`/home/ramunas/projects/esperanto-lexicon-corpus/proficiency_eval` on the local WSL machine —
a path this remote (cloud) session cannot reach. This repo itself is now also cloned locally
at `/home/ramunas/projects/learning-companion-test`, so both are reachable side by side from
a local Claude Code session or plain shell, even though not from here. Two ways to work with
that:

1. **Pull a topic manifest in** — even just article titles + topics (no full text needed for
   scenario-writing purposes) as a flat file here, so scenarios can be filled in with real
   topics from either environment.
2. **Keep scenario topic selection local** — run the scenario files as templates, filling in
   the actual question topic by hand from the WSL corpus at test time (easy now that both
   directories sit on the same machine), without ever copying the corpus itself into this
   repo.

Option 2 is the default for now (lower overhead, and the corpus is source material, not test
output — no strong reason to duplicate it here). Revisit if scenario scripts need to become
literal (e.g. for API automation replay) rather than templates a human fills in per run.

## Topic manifest (fill in — topics known to exist, by file/theme)

| Topic area | File(s) | Notes |
|---|---|---|
| | | |

## Known-thin or known-absent topics (for adversarial scenario targeting)

Useful for `../scenarios/07-adversarial-grounding.md` G2/G4 — a genuinely thin or absent
topic is more reliable than a guess.

| Topic | Status | Source |
|---|---|---|
| | | |
