# Manuscript improvement tasks

Created: 2026-09-29. Status: Tasks 02–04 and 11 completed; Tasks 05–10 and 12–17 remain planned. Tasks 11–17 were added on 2026-09-29 after a manuscript review.

## Objective and boundaries

Improve the journal submission quality of `beamstudy-mod.tex` using the existing results and all eight current figures (14 image assets). The author's latest instruction is binding: **no new simulations; use the figures as they are**. `Task_01.md` preserves the original request and is unchanged.

- Do not run Synergia2, MARS, RK4 particle tracking, parameter scans, convergence studies, or new controller tests. Do not create additional simulation results.
- Do not add, replace, regenerate, retouch, crop, digitize, relabel, or remove scientific figures or panels. Preserve image bytes, panel content, and aspect ratios. Caption wording, TeX sizing, spacing, and placement may improve.
- Use the manuscript, reference drafts, prior publication, existing review records, and any already available original documentation. Missing metadata is not permission to invent settings or require another run. Narrow the affected claim, explain the limitation, and record the author question.
- No new uncertainty estimates, ripple-suppression metrics, loss fractions, or quantitative conclusions inferred from raster plots. Arithmetic and checks of printed algebra are allowed; they are not new beam simulations.
- Build and inspect the manuscript as a document. Do not claim that compilation validates the science or guarantees journal acceptance.
- Do not stage, commit, or push. Supply a proposed commit message for each change batch.

## Ordered backlog

Priority P1 means scientific interpretation and narrative; P2 means presentation and submission checks. Tasks 02–04 and 11 are **Done**; the others are **Todo**. Dependencies indicate a sensible editorial order, not permission to start additional calculations.

| Task | Status | Priority | Deliverable | Depends on |
| --- | --- | --- | --- | --- |
| [01 — Original request and repository setup](Task_01.md) | Reference | — | Original manuscript-improvement request, direct TeX editing authorization, repository guidance, and commit-message format | None |
| [02 — Contribution and narrative](Task_02.md) | Done | P1 | Clear problem, contribution, abstract, introduction, and conclusion | None |
| [03 — Methods and configuration](Task_03.md) | Done | P1 | Concise case definitions with known/unknown settings distinguished | 02 |
| [04 — Theory and notation](Task_04.md) | Done | P1 | Consistent equations, coordinates, units, and model scope | 03 |
| [05 — RFKO interpretation](Task_05.md) | Todo | P1 | Evidence-led feedback and chromaticity discussion | 03, 04 |
| [06 — Transit-time interpretation](Task_06.md) | Todo | P1 | Precise tune-step protocol and supported comparison | 03, 04 |
| [07 — Scattering interpretation](Task_07.md) | Todo | P1 | Transparent handoff and conditional-loss discussion | 03, 04 |
| [08 — Existing figures and captions](Task_08.md) | Todo | P2 | Self-contained captions and readable layout with unchanged images | 05, 06, 07 |
| [09 — References and submission metadata](Task_09.md) | Todo | P2 | Verified attribution and a short author-only checklist | 02, 03 |
| [11 — Figure–text discrepancies](Task_11.md) | Done | P1 | Text and captions that match the plotted content; open questions for undocumented plot elements | 03, 04 |
| [12 — Numerical and unit consistency](Task_12.md) | Todo | P1 | Cross-checked table values, emittance/acceptance conventions, consistent units | 03 |
| [13 — Structure and synthesis discussion](Task_13.md) | Todo | P1 | RFKO studies placed together, specific headings, a Discussion built from existing results | 05, 06, 07, 11 |
| [14 — Literature positioning](Task_14.md) | Todo | P1 | Verified related-work context beyond the prior article | 02 |
| [15 — Limitations and prose economy](Task_15.md) | Todo | P2 | Each scope limit stated once in full; concise results paragraphs | 13 |
| [16 — Submission front matter](Task_16.md) | Todo | P2 | Running head, contents decision, highlights, declaration checklist | 09, 13 |
| [17 — Build, bibliography structure, docs](Task_17.md) | Todo | P2 | README/REVIEW match the BibTeX build; merged bib entries split | None |
| [10 — Final editorial and document checks](Task_10.md) | Todo | P2 | Compiled, visually inspected revision and readiness report | 02–09, 11–17 |

Tasks 05–07 cover separate results sections; their order may change. Task 11 supplies specific findings to Tasks 05–08, and Task 10 remains the final pass after Tasks 11–17. Revisit the abstract and conclusion after those sections are settled. Every task has a fallback for unavailable evidence so editorial progress does not depend on new simulations.

## Execution and completion

For each task, change status to In progress, make the scoped edits, and record substantive changes and unresolved questions in `REVIEW.md`. Mark Done only after its acceptance criteria pass and add a short completion note identifying the edits and checks. Missing author-only metadata can remain explicitly open; it must not be called verified. Any missing information that makes an essential result uninterpretable must remain visible in the final readiness report.

Earlier requests in `REVIEW.md` for matched simulations, convergence runs, or regenerated figures are historical scientific recommendations, outside this editing plan. Retain appropriate limitations in the paper without making those activities required tasks or promising them as submission deliverables.

The task files are now tracked in Git, and the current `.gitignore` no longer excludes `tasks/`. Task status updates are ordinary modifications. Do not stage, commit, or push them unless the author separately authorizes those actions.
