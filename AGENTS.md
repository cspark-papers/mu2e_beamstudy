# Repository guidance

## Scope and source of truth

- This repository contains the Mu2e beam-study manuscript and its existing figures.
- Edit `beamstudy-mod.tex` as the active submission manuscript. Direct TeX edits are authorized.
- Treat `beamstudy.tex` and `modeling.tex` as reference drafts unless the user asks to revise them.
- Read `README.md` and `REVIEW.md` before a substantial revision. Inspect the worktree and preserve existing user changes.

## Current revision boundary

- Follow the author’s latest scope: improve the manuscript using existing results and figures; no new simulations.
- Do not run new Synergia2, MARS, RK4 tracking, parameter scans, convergence studies, or controller tests. Check printed algebra and document builds without generating new scientific results.
- Preserve every existing figure file and panel as is. Caption edits and TeX sizing, spacing, and placement are allowed; do not redraw, digitize, crop, relabel, regenerate, replace, or remove figures.
- Follow `tasks/README.md` and `tasks/Task_02.md` through `tasks/Task_10.md` for the editorial backlog. Earlier review suggestions for new calculations or replacement figures are outside this revision’s scope.
- Where evidence is missing, qualify the claim and record the author question; do not invent metadata or make new simulations a completion requirement.

## Scientific editing

- Improve structure, clarity, equations, captions, references, and consistency without inventing results or simulation settings.
- Distinguish reported simulation results, analytical consequences, qualitative interpretations, and unperformed validation.
- Preserve numerical values unless a correction is supported by the source data or an explicit calculation. Record substantive corrections and assumptions in `REVIEW.md`.
- Keep the approximately 43% loss fraction conditional on the returned scattered-particle sample. Do not present it as a fraction of the circulating beam or multiply it by another loss estimate without consistent particle weights and denominators.
- Distinguish coherent centroid motion from emittance about the centroid, and use consistent coordinate, action, time, and sextupole-sign conventions.
- Verify figure descriptions against the actual images. Do not redraw or relabel scientific figures from inferred data. Prefer original plotting data and scripts when available.
- Verify bibliographic changes against primary sources. Label internal reports honestly; do not invent publication dates, DOIs, author declarations, or data-availability commitments.
- Put unresolved author questions in `REVIEW.md`; brief `AUTHOR CHECK` comments may also be left beside the relevant TeX. Do not conceal missing methodology with unsupported precision.

## Validation and outputs

- Compile from the repository root so relative `img/` paths resolve. Follow the build instructions in `README.md`.
- Require successful compilation, resolved citation/reference keys, and no duplicate labels. Inspect warnings and render the PDF to review equations, captions, tables, and page layout.
- A successful build does not validate the underlying simulations. Report the validation actually performed and remaining limitations.
- Preserve the existing figure files and reference drafts unless changes are requested. Keep temporary build and review products outside the tracked source tree.

## Version-control rule

- Do not run `git commit` or `git push` for manuscript revisions. Do not stage files unless requested.
- Whenever files change, provide a proposed commit message with a concise imperative subject, a paragraph describing the changes, and a `Files:` list with `M`, `A`, or `D` status and repository-relative paths.
- Use the actual changed files; the example supplied by the user defines the format, not the message content. Include untracked deliverable sources as proposed additions, and describe external review artifacts separately.
