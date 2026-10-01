# Manuscript improvement tasks

Created: 2026-09-29. Status: Tasks 02–25 are complete; Task 26 is Todo following the two reviews dated 2026-10-01 (22–23, then 24–26). Follow-up Tasks 18–21 came from the updated-manuscript review dated 2026-09-30. Submission also awaits the author actions listed in REVIEW.md. Tasks 11–17 were added on 2026-09-29 after an earlier manuscript review.

## Objective and boundaries

Improve the journal submission quality of `beamstudy-mod.tex` using the existing results and all eight current figures (14 image assets). The author's latest instruction is binding: **no new simulations; use the figures as they are**. `Task_01.md` preserves the original request and is unchanged.

- Do not run Synergia2, MARS, RK4 particle tracking, parameter scans, convergence studies, or new controller tests. Do not create additional simulation results.
- Do not add, replace, regenerate, retouch, crop, digitize, relabel, or remove scientific figures or panels. Preserve image bytes, panel content, and aspect ratios. Caption wording, TeX sizing, spacing, and placement may improve.
- Use the manuscript, reference drafts, prior publication, existing review records, and any already available original documentation. Missing metadata is not permission to invent settings or require another run. Narrow the affected claim, explain the limitation, and record the author question.
- No new uncertainty estimates, ripple-suppression metrics, loss fractions, or quantitative conclusions inferred from raster plots. Arithmetic and checks of printed algebra are allowed; they are not new beam simulations.
- Build and inspect the manuscript as a document. Do not claim that compilation validates the science or guarantees journal acceptance.
- Do not stage, commit, or push. Supply a proposed commit message for each change batch.

## Ordered backlog

Priority P1 means scientific interpretation and narrative; P2 means presentation and submission checks. Tasks 02–25 are **Done**; Task 26 is **Todo**. Dependencies indicate a sensible editorial order, not permission to start additional calculations.

| Task | Status | Priority | Deliverable | Depends on |
| --- | --- | --- | --- | --- |
| [01 — Original request and repository setup](Task_01.md) | Reference | — | Original manuscript-improvement request, direct TeX editing authorization, repository guidance, and commit-message format | None |
| [02 — Contribution and narrative](Task_02.md) | Done | P1 | Clear problem, contribution, abstract, introduction, and conclusion | None |
| [03 — Methods and configuration](Task_03.md) | Done | P1 | Concise case definitions with known/unknown settings distinguished | 02 |
| [04 — Theory and notation](Task_04.md) | Done | P1 | Consistent equations, coordinates, units, and model scope | 03 |
| [05 — RFKO interpretation](Task_05.md) | Done | P1 | Evidence-led feedback and chromaticity discussion | 03, 04 |
| [06 — Transit-time interpretation](Task_06.md) | Done | P1 | Precise tune-step protocol and supported comparison | 03, 04 |
| [07 — Scattering interpretation](Task_07.md) | Done | P1 | Transparent handoff and conditional-loss discussion | 03, 04 |
| [08 — Existing figures and captions](Task_08.md) | Done | P2 | Self-contained captions and readable layout with unchanged images | 05, 06, 07 |
| [09 — References and submission metadata](Task_09.md) | Done | P2 | Verified attribution and a short author-only checklist | 02, 03 |
| [11 — Figure–text discrepancies](Task_11.md) | Done | P1 | Text and captions that match the plotted content; open questions for undocumented plot elements | 03, 04 |
| [12 — Numerical and unit consistency](Task_12.md) | Done | P1 | Cross-checked table values, emittance/acceptance conventions, consistent units | 03 |
| [13 — Structure and synthesis discussion](Task_13.md) | Done | P1 | RFKO studies placed together, specific headings, a Discussion built from existing results | 05, 06, 07, 11 |
| [14 — Literature positioning](Task_14.md) | Done | P1 | Verified related-work context beyond the prior article | 02 |
| [15 — Limitations and prose economy](Task_15.md) | Done | P2 | Each scope limit stated once in full; concise results paragraphs | 13 |
| [16 — Submission front matter](Task_16.md) | Done | P2 | Running head, contents decision, highlights, declaration checklist | 09, 13 |
| [17 — Build, bibliography structure, docs](Task_17.md) | Done | P2 | README/REVIEW match the BibTeX build; merged bib entries split | None |
| [10 — Final editorial and document checks](Task_10.md) | Done | P2 | Compiled, visually inspected revision and readiness report | 02–09, 11–17 |
| [18 — RFKO diagnostic and causal consistency](Task_18.md) | Done | P1 | Conditional action-density interpretation; coherent/chromatic/space-charge distinctions; bounded chromaticity claims | 04, 05, 11 |
| [19 — Sampling and response-time interpretation](Task_19.md) | Done | P1 | Correct rotating-frame statement; separate timing cadence, phase-space interpretation, and feedback-delay inference | 04, 06, 13 |
| [20 — Scattering coordinates and encounters](Task_20.md) | Done | P1 | Separate local scattering from transported coordinates and displayed returns from repeated physical encounters | 07, 11; coordinate with 19 |
| [21 — Bibliography syntax and current review status](Task_21.md) | Done | P2 | Remove two stray braces, correct citation count, reconcile current summaries, and validate follow-up edits | 17; final summary after 18–20 |
| [22 — Setup provenance and uncertainty](Task_22.md) | Done | P1 | Align update-rate, bandwidth, acceptance, particle-selection, and nominal/input statements | 03, 12, 18–20 |
| [23 — Readability after the follow-up edits](Task_23.md) | Done | P2 | Remove repetition, separate observations from interpretation, and clarify horizontal-coordinate summaries | 18–22 |
| [24 — Residual attribution and scope slips](Task_24.md) | Done | P1 | Space charge only where documented; PID citation; reference-group branch attribution; observational Fig. 1 caption; two remaining long paragraphs | 22, 23 |
| [25 — Provenance table for undocumented settings](Task_25.md) | Done | P2 | One case-by-case table of unspecified settings replacing repeated "not documented" prose, with every disclosure preserved | 22, 23, 24 |
| [26 — Layout, bibliography, and style](Task_26.md) | Todo | P2 | Table 1 placement, MARS15 capitalization (primary source checked), single TDR link, Acknowledgments numbering decision | None |

Tasks 05–07 cover separate results sections; their order may change. Task 11 supplies specific findings to Tasks 05–08, and Task 10 remains the final pass after Tasks 11–17. Revisit the abstract and conclusion after those sections are settled. Every task has a fallback for unavailable evidence so editorial progress does not depend on new simulations.

## Second review of 2026-10-01: Tasks 24–26

The full manuscript at revision `9b299a3` was read end to end again, after Tasks 22–23 had been recorded. Findings already captured in Tasks 22–23 were not duplicated: update interval, bandwidth wording, acceptance cross-reference, Table 3 selection, nominal momentum, the duplicated chirp sentence, the action-profile and transit paragraphs, the response-chain wording, and the distance-from-septum summaries. The remaining items are:

- **Task 24 (P1):**
  - space charge is attributed to the feedback case and to all diagnostics, although it is documented only for the tune-step and fixed-tune cases;
  - the PID citation reads as the source of the controller tests;
  - the reference-group "outgoing branch" identification rests on an undocumented overlay;
  - the `fig:rfko1` caption is causal;
  - two further paragraphs exceed 220 words, with two local wording slips.
- **Task 25 (P2):** the body uses "not documented" 24 times (8 in captions). Consolidate the disclosures into one provenance table, keeping every disclosure and the number-adjacent qualifiers.
- **Task 26 (P2):**
  - Table 1 is defined in the Introduction but discussed in Sec. 2.1;
  - `mars2` renders "Mars15", whereas the primary report title page (FERMILAB-CONF-10-518-APC, December 2010) reads "MARS15";
  - the TDR reference repeats its arXiv link;
  - Acknowledgments numbering is left as an author decision, since it matches the requested companion format.

Measurements: the abstract is 208 words. Five body paragraphs exceed 220 words (289, 271, 252, 223, 222), of which Task 23 covers the 289- and 271-word ones and the 223-word wording. Only task documentation was written; the manuscript, bibliography, highlights, figures, and drafts are unchanged by this review.

Process note: while this review was being recorded, `tasks/Task_22.md` and `tasks/Task_23.md` were briefly overwritten in the working tree, because they had been committed (`ed5a6a7`) after the review began. Both were restored unchanged from `HEAD`, and the new tasks were renumbered 24–26.

## Latest review: Tasks 22–23 (2026-10-01)

Reviewed `beamstudy-mod.tex` at source revision `9b299a3`, including the completed Tasks 18–21, the current bibliography, highlights, and rendered manuscript. The main action-diagnostic, timing, scattering, and bibliography findings from the previous review have been addressed. Two focused follow-ups remain:

- **Task 22:** reconcile statements about undocumented controller timing, possible bandwidth differences, acceptance normalization, intended particle selection, and corrected nominal parameters versus verified historical inputs.
- **Task 23:** remove repeated setup wording, separate long observation/interpretation paragraphs, and make the transit-time summaries refer clearly to the plotted horizontal coordinate.

These tasks record editorial corrections and improvements. They do not require additional simulations or repeat the existing author-only questions about the ripple waveform, 43% denominator, image provenance, or declarations. Earlier tasks keep their recorded Done status.

Validation performed:

- Fresh review and submission builds both succeeded at 24 pages. There are 46 unique labels and 24 distinct cited bibliography entries, with no unresolved keys or BibTeX warnings. Bibliography braces are balanced. The only LaTeX diagnostic remains the previously documented CAS keyword-overlay box.
- All 24 review pages and the submission title page were visually inspected. No new clipping, missing figure panel, or layout failure was found; existing image-resolution and small-lettering limitations remain.
- All five highlights satisfy the repository's 85-character limit. This is a local formatting check, not a fresh audit of journal requirements or bibliography metadata.
- Hashes confirm that the active manuscript, bibliography, highlights, all 22 image assets, and both reference drafts are unchanged by this review. The figures also match the assets inspected at native resolution in the previous review.
- Only task documentation changed. No new scientific calculations, simulations, staging, commits, or pushes were performed. Temporary PDFs, logs, and rendered pages are in `/private/tmp/mu2e-review-oct01-93con_zs/`, outside the tracked source tree.

## Previous updated-manuscript review: Tasks 18–21

The review dated 2026-09-30 inspected the complete updated `beamstudy-mod.tex`, bibliography, all 14 referenced image assets, prior task completion records, and the current review PDF. It found residual interpretation issues, not a need for new scientific calculations. The tasks above record source locations, the distinction between observations and interpretations, actionable edits, and acceptance criteria. They leave earlier completed tasks intact and do not duplicate the already recorded ripple-frequency, controller-metadata, foil-provenance, and 43% denominator questions.

Validation performed for this review:

- Fresh review and submission builds both succeeded at 23 pages. All 46 labels are unique; all 24 distinct citation keys resolve, with zero BibTeX warnings. The two stray bibliography braces are silently ignored by the current BibTeX toolchain.
- All 23 review pages and the submission title page were rendered and inspected. No new clipping, missing panels, or float-layout defect was identified. The previously documented CAS keyword-overlay warning and source-image resolution/lettering limits remain.
- Checks of the printed equations confirm the stated fixed points and expose the unqualified zero-detuning stationarity claim recorded in Task 19. No trajectories, distributions, controller tests, or other scientific results were generated.
- Hashes confirm the active TeX, bibliography, all 22 image files, and both reference drafts are unchanged by this review. Only task documentation was edited. An existing untracked `tasks/TODO.md` was left untouched.
- Temporary builds and rendered review pages are outside the tracked source tree in `/private/tmp/mu2e-review-27mvpkui/`. Successful compilation is document validation, not simulation validation.

Tasks 18–20 can be completed by qualifying the unsupported assertions if existing records cannot resolve them. Task 21 includes the follow-up document checks and current-status update after those edits; the prior Task 10 completion remains a record of the earlier pass.

## Execution and completion

For each task, change status to In progress, make the scoped edits, and record substantive changes and unresolved questions in `REVIEW.md`. Mark Done only after its acceptance criteria pass and add a short completion note identifying the edits and checks. Missing author-only metadata can remain explicitly open; it must not be called verified. Any missing information that makes an essential result uninterpretable must remain visible in the final readiness report.

Earlier requests in `REVIEW.md` for matched simulations, convergence runs, or regenerated figures are historical scientific recommendations, outside this editing plan. Retain appropriate limitations in the paper without making those activities required tasks or promising them as submission deliverables.

The task files are now tracked in Git, and the current `.gitignore` no longer excludes `tasks/`. Task status updates are ordinary modifications. Do not stage, commit, or push them unless the author separately authorizes those actions.
