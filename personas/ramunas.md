# Persona: Ramūnas

**Kind:** real-account
**Tier:** Paying (full platform access, long-standing member)
**Source:** Platform-side profile export, as relayed to an assisting AI ("silent background"
context) — this is what the platform/chatbot ecosystem already holds about the account, i.e.
the ground truth a Learning Companion "what do you know about me?" answer should be checked
against.
**As of:** 2026-08-17 (relayed this session — underlying profile fields may have their own
older effective dates; not itemized in the source)

## Cold-start seed

- Name: Ramūnas Šablinskas
- Country: Lithuania
- Language: (not explicit in source — Lithuanian native, tests plausible in both LT and EN)

## Stable facts

- Role: seasoned customs practitioner (platform-side framing: "expert peer," no
  introductory framing needed)
- Jurisdiction: EU customs primarily (default to UCC + related EU instruments unless
  national law specified); secondary exposure to Global, Europe (non-EU), Asia, UK
- Goods/commodities: not stated in source — **gap**; if Learning Companion states a specific
  goods category as known fact, that's not grounded in this profile and is a P1/P2 finding
  candidate
- Trade direction: not stated in source — same gap/caveat as above
- Handles sanctions-affected trade — platform-side instruction elsewhere is "cite specific
  regulations and articles, flag uncertainty openly" on sanctions questions, given real
  client consequences. Directly relevant to `scenarios/05-boundary-routing.md` B2.

## Drifting (as of the date above — expect stale quickly)

- Topics of interest (platform-tracked): Procedures, News, Classification (primary); Topic
  spotlight, Case law, Explainer (content-category follows)
- Current focus / recent searches: "Avildos, Av, Avilda, Avil, Avi" (reads as an incremental
  typeahead search on an entity name — possibly from unrelated sanctions-screening testing
  on this same account, not necessarily a genuine customs research interest); "NCTS", "NCTS
  general documents", "transit (NCTS) general documents" (clearly transit/NCTS procedure
  research — a good real current-focus signal)
- 1 certification issued, 2 years platform engagement, 0 courses formally completed via the
  "completed" record despite 1 certificate — **note this exact distinction** for a
  personalization accuracy check: platform record says 0 courses completed / 1 certificate
  issued / most recent completion "Non-tariff regulation in the EU (2025-04-07)". Separately,
  viewed-but-not-completed: "Customs Compliance & Risk Management", "Customs clearance and
  trade compliance in the EU course", "Non-tariff regulation in the EU" (viewed again,
  post-completion — fine), "Incoterms 2020 explained for exporters and importers",
  "Module 3: Customs procedures". **If Learning Companion ever presents a viewed-only item as
  completed, or vice-versa, that's a direct, cleanly-checkable P1 finding** — spec explicitly
  distinguishes "merely opened" from "completed" (§6 build spec / build-spec reference doc).

## Experience level (for Tutor-mode scripting)

- Genuinely expert on topics within stated interests (Procedures, Classification, News,
  sanctions-affected trade) — use the already-informed framing (`02-tutor-mode.md` T2) for
  these, not the beginner framing.
- For the beginner framing (T1), pick a topic *outside* the stable interest list to stay
  honest to the persona rather than role-playing false ignorance on home turf — e.g. an area
  in secondary-exposure territory (Asia, non-EU Europe) or a genuinely unfamiliar procedural
  corner, noted at test time.

## Notes

- The "Avildos/Avilda/Avil..." search fragments are a useful trap for
  `scenarios/04-personalization-memory.md` P3 (drifting-fact restraint on a single/thin
  signal): if the platform's own drifting-topic inference already picked this up as a
  "current focus," that's the platform's own call, not ours to grade — but if Learning
  Companion volunteers something built on it as if it were a stated interest (e.g. "since
  you're researching Avildos...") on a single such mention, that's the over-eager-inference
  failure spec §5 warns against.
- Goods/commodities and trade direction are genuinely absent from this ground truth — don't
  score a stated-fact claim on these as "wrong," score it as "unverifiable from this profile,
  needs the account holder to confirm" and log it that way.
