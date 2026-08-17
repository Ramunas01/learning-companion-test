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

## Topic manifest

Filled in from a direct read of the local corpus (2026-08-17), since this session had access
to both directories side by side. Full snippet index (one entry per article, ~260 chars each,
real dates/regulation numbers/case names visible) is at `topic-manifest-snippets.md` in this
folder — pull a concrete question from there rather than guessing.

| Topic area | File(s) | Notes |
|---|---|---|
| Law (legal acts, case law, OJ notices) | `corpus-1-law.txt` (97 chunks) | Heavy on recurring "News in brief" / weekly digest chunks (UK, Ukraine, EU) plus standalone pieces: CBAM Omnibus simplification, EU Customs Reform series (nUCC, Trust & Check Trader, importer role, Title V), several CJEU case summaries, Israeli case law (freight/storage disputes) |
| Taxes & tariffs | `corpus-2-taxes-tarriffs(taxes-and-duties).txt` (92 chunks) | CBAM (several angles), VAT/import VAT mechanics (procedure 42, fiscal representation, triangulation), anti-dumping/countervailing duties, a long-running 2025–2026 US tariff story (reciprocal tariffs, Section 232, IEEPA Supreme Court ruling, de minimis phase-out) with many dated updates — good recency-test material |
| Restrictions (non-tariff regulation) | `corpus-3-restrictions(non-tariff-regulation).txt` (98 chunks) | Russia/Belarus sanctions (heavy coverage), CBAM (overlaps with taxes-tariffs), REACH, export controls, deforestation regulation, Windsor Framework, non-tariff-measures generally |
| Customs understanding | `corpus-4-customs-understanding(customs).txt` | General/foundational customs-concept explainers — good Tutor-mode "from the basics" source |
| Rules of origin | `corpus-5-rules-of-origin(origin).txt` (80 chunks) | PEM Convention transitional rules, preferential vs non-preferential origin, post-clearance verification, supplier's declarations, BTI/BOI reliability, remanufactured-goods origin cases |
| Classification | `corpus-6-classification(classification).txt` (5 articles, titled via `Edit <title>` lines — different format from the rest) | HS 2028 revision, CN 2026 amendments, an Israeli 8502-vs-8504 electricity classification dispute, AI in classification, warehouse-modification-and-reclassification case — small file, good for boundary-routing tests (§05) since it's a close real-world analogue to the July assessment's LED-strings/9405 incident |
| Valuation | `corpus-7-valuation.txt` (51 chunks) | Includes a CJEU customs-valuation case (Lifosa, C-75/20) |

Secondary/non-core files also present locally but not part of the "7 topics": `corpus-compliance.txt`, `corpus-other.txt`, `corpus-sustainability.txt`, `corpus-tech.txt`, `corpus_customs_procedures.txt` — useful for Coach-mode or cross-cutting scenarios if the 7 core files run thin.

## Known-thin or known-absent topics (for adversarial scenario targeting)

Useful for `../scenarios/07-adversarial-grounding.md` G2/G4 — a genuinely thin or absent
topic is more reliable than a guess. Not yet empirically confirmed against the live
assistant's actual retrieval (that's a live-test step, not a corpus-read step) — these are
candidates based on what the corpus visibly does and doesn't cover:

| Topic | Status | Source |
|---|---|---|
| Non-EU/non-UK/non-Israel/non-Ukraine jurisdiction procedural detail (e.g. a specific South Korea or Japan customs procedure) | Candidate thin/absent — coverage skews EU, UK, Israel, Ukraine; scattered Canada/India/Brazil/Kenya mentions exist but are shallow | Sampled across all 6 snippet-indexed files |
| A named non-EU port/authority procedural sequence (mirrors the July assessment's own successful out-of-scope test, A3: "at Santos, ANVISA clears perishables before phytosanitary check") | Good reusable out-of-corpus probe — same shape, different specifics so it isn't literally the same question the assistant may have "seen" before | July assessment reproducibility pack |
