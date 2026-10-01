# Task 24 — Correct residual attribution and scope slips not covered by Tasks 22–23

Status: Done  
Priority: P1  
Depends on: 22, 23  
Review date: 2026-10-01 (second review of revision `9b299a3`)

## Scope

`beamstudy-mod.tex`: the Introduction, `sec:rfko1`, `sec:beamloss`, the `fig:rfko1` caption, and two `sec:arrival`/`sec:beamloss` results paragraphs. Line numbers refer to revision `9b299a3`; use the labels if Tasks 22–23 move the text.

Follow `tasks/README.md`: existing evidence only, no new simulations, no figure changes. This task deliberately excludes the items already recorded in Tasks 22–23 (update interval, bandwidth wording, acceptance cross-reference, Table 3 selection, nominal momentum, the duplicated chirp sentence, the action-profile and transit paragraphs, the response-chain wording, and the distance-from-septum summaries).

## Findings

1. **Space charge is attributed to cases where it is not documented.**
   - Line 318 (`sec:rfko1`) says the feedback result holds "in this space-charge tracking model". Table 3 describes the ripple-and-feedback case only as "Synergia2 extraction with tune ramp". Unlike the tune-step and fixed-tune rows, it does not state space charge, and the Task 03 case-metadata record lists the feedback case's space-charge settings as undocumented.
   - Line 118 (Introduction) describes the contribution as diagnostics "specific to the Mu2e Delivery Ring at high space charge". Space charge is documented only for the tune-step and fixed-tune cases.

   Describe the feedback result as a Synergia2 tracking result, and scope the "high space charge" phrase to the documented cases. If the original files show that the feedback case included space charge, record that provenance instead.
2. **The PID citation reads as the source of the investigation.** Line 312: "Controllers based on proportional–integral–derivative feedback were investigated~\cite{pid}." Ref. [pid] (Himel, SLAC-PUB-7398) is a general feedback reference; the controller tests were made in the original study. Attach the citation to the controller concept and attribute the investigation to the original study. Bibliography metadata is unchanged.
3. **A branch identification depends on an undocumented overlay.** Line 418 (`sec:beamloss`) states that after three turns "the added reference group follows the outgoing separatrix branch". In Fig. `fig:beamloss2a` the branch can be identified only through the orange overlay lines, which the caption calls undocumented. The statement comes from the original draft's analysis. Attribute it to that analysis or describe the observed position without naming the branch. The REVIEW-only geometric consistency check of the overlays (Task 04) supports, but does not establish, the identification.
4. **The `fig:rfko1` caption keeps causal wording.** It ends "Nonzero chromaticity gives greater emittance growth and smaller centroid excursions." Task 18 bounded this claim in the text because a possible bandwidth difference is not excluded. Make the caption observational, for example "With nonzero chromaticity, emittance growth is greater and centroid excursions are smaller", consistent with the Task 22 bandwidth wording.
5. **Two more long results paragraphs and two local wording slips.** Task 23 splits the action-profile (`sec:rfko`) and transit-time (`sec:arrival`) paragraphs. Two others also exceed 220 words (counted with TeX commands stripped):
   - the `Figure~\ref{fig:arrival1a} shows…` paragraph (252 words), which mixes burst behavior with post-restoration behavior and the protocol caveat;
   - the `Figure~\ref{fig:beamloss2a} shows…` paragraph (222 words), which mixes the initial line and mapping caveat with the three-turn evolution.

   Local wording:
   - Line 406 uses "therefore" in two consecutive sentences.
   - Line 339's "values that the uninterrupted ramp would have reached at that turn" should say "the restoration turn".

## Work and fallback

- Make the edits above without weakening any qualifier or changing a number.
- Split the two paragraphs by purpose (observation, then caveat or interpretation), matching the Task 23 approach.
- If the original records resolve finding 1, cite their provenance in REVIEW; otherwise qualify.

## Acceptance criteria

- [x] No sentence attributes space charge to a case whose records do not state it.
- [x] Ref. [pid] supports only the controller concept.
- [x] The reference-group branch statement is attributed or rephrased observationally.
- [x] The `fig:rfko1` caption is observational.
- [x] No body paragraph exceeds about 200 words, after Tasks 23 and 24 together.
- [x] Figures, reported values, and bibliography metadata are unchanged; both builds pass with resolved references.

## Completion record

Completed: 2026-10-01.

- Finding 1: space charge is now claimed only for the fixed-tune and tune-step cases (Sec. 4.2 reads "Synergia2 tracking case"; the Introduction is scoped). The drafts gave no evidence for the feedback case, and the question was added to REVIEW.
- Finding 2: "The original study investigated PID controllers, a standard feedback scheme [pid]."
- Finding 3: the reference-group branch statement is attributed to the original analysis, with the note that the branch is identifiable only through the undocumented overlays.
- Finding 4: the `fig:rfko1` caption is now observational.
- Finding 5: the Fig. 4 and Fig. 7(a) paragraphs were split; "thus" replaces the second "therefore"; "at the restoration turn" is explicit. The longest body paragraph is now 195 words.
- Both builds pass (24 pages; 0 BibTeX warnings; known CAS overlay only); pages 12, 15, and 20 were inspected; figures, values, and bibliography are unchanged.
