# Session: Marco / consistency-across-phrasing (script step 2) — EU valuation, royalties/license fees / 2026-08-19

## Account state
- Same account, Marco persona active, "mini"/"lite" tier
- Two fresh chats, same underlying question, two phrasings, per the script's own method

## Phrasing A ("valuation" framing — the literal script step 1 wording)

**User:** Has anything changed recently in EU customs valuation rules regarding royalties and license fees?

**Assistant:** The ground has shifted here — there's been meaningful CJEU case law activity on royalties and the "condition of sale" test, alongside updated guidance from the Commission. Here are 10 articles covering recent developments in EU customs valuation of royalties and licence fees.

[Bare list of 10 article title/date/author cards follows, no prose synthesis, no dates called out, not sorted newest-first — dates range 2020-01-31 through 2024-01-07, with two 2020 articles shown first. Full list: Adjustment of transaction value by including royalties and license fees (2020-01-31); Royalties and customs value: CJEU clarification to Bulgarian courts (2020-09-25); Customs valuation and transfer pricing – understanding similarities and differences (I) (2023-12-17); Impact of the war in the Middle East on customs valuation (2024-01-07); New version of European Commission's Guidance on Customs Valuation (2020-10-31); Customs valuation – the particularities of different countries (2023-08-06); Customs valuation and transfer pricing (II) (2023-12-17); Focus of the CJEU: exclusive distribution compensation and customs value (2021-01-06); Compendium of customs valuation 2021 (2021-10-30); Do you swear to tell the truth? Israeli "importer's affidavit" (2023-03-26)]

No inline citations, no specific case name or article number, no explicit "what changed"
content beyond the one-line opener.

## Phrasing B ("royalty/license fee" framing — same underlying question)

**User:** We're dealing with royalty and license fee payments on imported goods - has the EU customs treatment of these changed recently?

**Assistant:** The core legal framework hasn't changed — Articles 70–71 UCC and the Implementing Regulation still govern the inclusion of royalties in customs value, with the two-limb test (relatedness to the goods; condition of sale) remaining the operative standard.

What has evolved is the case law interpreting that framework. The CJEU's ruling in C-76/19 (the Bulgarian electronic kits case) sharpened the "sufficiently close link" analysis: the Court confirmed that royalties paid for know-how used only to complete a licensed product — where the imported components are sourced freely from multiple suppliers not predetermined by the licensor — do not automatically have a close enough link to those imported goods to warrant inclusion in customs value. The mere fact of incorporation into a finished product isn't sufficient. That's a useful precedent for clients where royalties attach to finished-goods output rather than to the imported inputs themselves.

The second limb — condition of sale — also received attention: where royalties are paid to a third party (rather than directly to the seller), the analysis under Commentary No. 11 of the Customs Code Committee requires establishing both a relationship between that third party and the seller, and that the third party is actually capable of ensuring imports are conditional on the royalty payment. Both prongs need to be satisfied.

We have covered royalties and customs value in several articles available to paid members, including analysis of the CJEU's clarification to Bulgarian courts, the Commission's updated Guidance on Customs Valuation, and broader transaction value adjustment methodology.

[3 source cards shown, "Click to expand" for more]

Want me to work through how C-76/19 applies to a specific client scenario?

**Sources checked (1):** Insights from judgements of the courts — 2022-08-16

## Verification

Opened the single cited source. It is a real, substantive multi-speaker "Authors' Meeting"
article with a section "ROYALTY FEE AND CUSTOMS VALUATION" by Georgi Goranov that confirms
the C-76/19 analysis **precisely**, near-verbatim: *"the fact that know-how was necessary only
for the completion of the licensed goods meant that there was no sufficiently close link
between the royalties and the imported goods"* and the third-party/Commentary No. 11 point.
Every specific legal claim in the chat answer checks out exactly.

**However: the source is dated 16 August 2022**, discussing a CJEU ruling that predates even
that. Framed against a "has anything changed *recently*" question in a 2026-dated
conversation, presenting a 2022-vintage case-law discussion as "what has evolved" without
flagging that it isn't actually recent is a genuine, if subtler, recency-handling gap — the
content is accurate, but the implicit currency claim isn't examined or caveated.

## Scoring

Dimension(s) tested: Consistency across phrasing (new dimension), Recency handling,
Grounding, Citation accuracy

**Consistency across phrasing: FAIL — the standout finding of this session, and arguably one
of the most concrete findings of the whole effort.** The identical underlying question,
asked two different ways in separate sessions, produced qualitatively different responses:
Phrasing A returned a bare, unsorted, unsynthesized list of 10 article titles with no
specific claims, no case citations, and a vague one-line opener ("the ground has shifted").
Phrasing B returned a detailed, accurate, well-reasoned, precisely-grounded answer citing a
specific CJEU case with real legal analysis. A user's experience of this product is
materially different depending on how they happen to phrase a question with the same
underlying intent — which directly undercuts the reliability promise ("get a cited answer")
the product makes regardless of phrasing.

**Recency handling: mixed.** Phrasing A's list wasn't sorted newest-first and its claimed
"recent developments" span 2020–2024 with nothing actually current. Phrasing B's answer
correctly separated "framework unchanged" from "case law evolved" — the right *shape* of
recency reasoning — but the "evolution" it cites is itself from a 2022 source discussing an
even older case, presented without any caveat that this isn't a recent development. Neither
phrasing surfaced anything genuinely current (2025/2026) on this topic, which may mean the
corpus itself doesn't have anything newer — a legitimate "nothing new to report" case — but
neither response says that explicitly either.

**Grounding and citation accuracy on Phrasing B specifically: PASS, precisely verified.**

## Notes

Strongly recommend featuring this pairing prominently in any writeup — it's the cleanest
demonstration in this whole effort that answer quality is phrasing-dependent rather than
purely determined by information need, which is a distinct and important dimension from
"is any individual answer correct." Worth flagging to Šarūnas as its own investigation
thread: what differs in retrieval or generation between these two phrasings that produces
such different output structures (bare list vs. synthesized answer)? The list-only format
itself is also worth investigating on its own — is it a "lite" tier fallback rendering, a
retrieval-confidence threshold effect, or a random/model-dependent difference in response
format? Any of those would be a useful, specific lead for engineering.
