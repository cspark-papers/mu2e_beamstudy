# Task 23 — Tighten the follow-up prose while preserving its qualifications

Status: Done  
Priority: P2  
Depends on: 18–22  
Review date: 2026-10-01

## Scope

`beamstudy-mod.tex`: the RFKO setup and action-profile discussion (`sec:rfko`), timing discussion (`sec:arrival`, `sec:chain`), and their summary wording. This is a focused readability pass on text expanded by Tasks 18–20, not a request to undo those scientific qualifications or repeat Task 15 across the whole paper.

## Findings and improvements

1. **The chirp coverage statement is repeated within the same setup paragraph.** Line 258 describes the linear chirp as covering the betatron tune spread, lists the two chromaticities, and then states that coverage again. Keep one statement, followed directly by the unknown-bandwidth qualification.
2. **The action-profile paragraph combines too many functions.** Line 286 contains the diagnostic-reference limitation, the mean-action decomposition, an annular-density derivation, Gaussian assumptions, several hypothetical explanations of the zero-chromaticity curves, the nonzero-chromaticity observation, and the aperture caveat. Separate the direct observations from the conditional interpretation. Give the displayed-profile comparison a short paragraph of its own; place the mathematical explanation in a separate paragraph or displayed expression if that improves readability. Keep the reference and normalization limitation beside the interpretation it qualifies. Speculative alternatives that do not help a reader interpret the figure can remain in the author-check record instead of expanding the results narrative.
3. **The timing discussion similarly mixes observation and interpretation in one large paragraph.** Line 362 combines the coordinate trend, branch interpretation, model comparison, sampling ambiguity, and stage dependence. Split it into coherent paragraphs so the reader can identify what Fig. `fig:arrival2` shows before reading why it might happen. Preserve the incomplete-tail and arrival-detection limitations.
4. **The response-chain wording repeats a comparison without a clear referent.** Line 427 says “If the RFKO-driven response has comparable transit delays, they are comparable to, and can exceed, the averaging interval.” State once that this is conditional on the RFKO case having transit delays similar to the separate tune-step case, then explain the comparison with the approximately 100-turn averaging interval. Keep the distinction between a plausible delay mechanism and a demonstrated controller diagnosis.
5. **Short summaries can describe the measured coordinate more precisely.** The abstract, Conclusions, and fourth highlight refer to a particle's “starting distance from the septum.” The plotted variable is its starting horizontal coordinate in an undocumented normalization, not its trajectory length to the septum. Prefer “starting horizontal coordinate” or “horizontal separation” as appropriate, with the trend scoped to the displayed sample. Do not introduce a distance-to-time law or imply that the unknown normalization has been recovered.

## Work

- Remove exact repetition and split paragraphs by purpose: observation, conditional interpretation, and implication.
- Preserve the content of the Task 18–20 qualifications. Shortening must not turn “consistent with,” “possible,” or “reported” into an established causal or methodological claim.
- Keep the 43% returned-sample qualification intact wherever that number appears; this task does not require editing the scattering result.
- Maintain the existing title, scientific values, equations, figure assets, and panel order. Do not set an arbitrary page-count reduction target.
- If editing a highlight, retain the documented 85-character limit and the author-approval status.
- Build both variants after the edits, inspect the affected pages, and update the latest review summary and task index to the actual state. Preserve earlier validation records as history.

## Acceptance criteria

- [x] The chirp coverage sentence appears once in the setup paragraph.
- [x] RFKO-profile and transit-time observations are easy to distinguish from their conditional interpretations.
- [x] The response-chain comparison is concise and retains its cross-case limitation.
- [x] The transit-time summaries refer to the plotted horizontal coordinate rather than an unspecified path length.
- [x] No diagnostic convention, causal conclusion, particle selection, or new result is introduced by shortening the prose.
- [x] Both builds pass; affected pages and highlights are checked, with all figures unchanged.

## Completion record

Completed: 2026-10-01.

- Removed the duplicated chirp sentence.
- Split the action-profile paragraph (definition and conditional interpretation / observations) and the transit-time paragraph (observations / labeled pathway interpretation / discrete-level origin). The speculative C_x = 0 alternatives were condensed to one sentence, with the full list kept in REVIEW.
- Rewrote the response-chain comparison as an explicit cross-case condition in its own paragraph.
- The abstract, Conclusions, and highlight 4 now refer to the starting horizontal coordinate, scoped to the displayed samples.
- Qualifier counts are preserved (hedge count 74 before and after); no new causal claim, convention, or result.
- The review-only contents list was returned to `\footnotesize` so that it stays on page 1.
- Both builds pass (24 pages; 0 BibTeX warnings; known CAS overlay only); affected pages were inspected; figures are unchanged.
