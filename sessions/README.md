# Session logs

One file per run: `YYYY-MM-DD-persona-scenario-NN.md`, e.g.
`2026-08-17-ramunas-tutor-mode-01.md`. Log verbatim, don't paraphrase the assistant's
replies — scoring and future re-diffing depend on exact wording (citation markers, hedge
phrasing, exact claims).

## Template

```markdown
# Session: [persona] / [scenario file + item, e.g. 02-tutor-mode T1] / [date, time]

## Account state
- Tier:
- Logged in: yes/no
- Fresh chat: yes/no
- Model/prompt/tier visible from UI: [note whatever is observable, even "not visible"]

## Transcript

**User:** [verbatim]
**Assistant:** [verbatim, including any citation markers/links exactly as shown]

**User:** ...
**Assistant:** ...

## Scoring

Dimension(s) tested: [from docs/scoring-rubric.md]
Result: PASS / PARTIAL / FAIL
Evidence: [quote the specific line(s)]
Notes: [anything ambiguous, worth a second run, or needing engineering log access to settle]
```

## Discipline

- Log even a clean PASS run — a scenario with no logged run is not a tested scenario.
- Note anything odd even if off-topic for the scenario at hand (an unprompted citation
  mismatch during a Coach-mode run is still worth a line, cross-reference it in
  `scoring/results.md` under the citation dimension).
- If a run needs to be abandoned partway (browser issue, unclear UI state), log what
  happened anyway and mark it INCOMPLETE rather than deleting it.
