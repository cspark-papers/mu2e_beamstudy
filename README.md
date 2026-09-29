# Mu2e beam-study manuscript

This repository contains a journal manuscript on particle dynamics during third-integer resonant extraction from Fermilab's Delivery Ring for Mu2e. It covers RFKO spill feedback, transit-time calculations, septum-scattered particle tracking, and chromaticity-dependent RFKO excitation.

## Files

| Path | Purpose |
| --- | --- |
| `beamstudy-mod.tex` | Active submission manuscript using Elsevier's `cas-sc` class. |
| `img/` | Existing PNG figure assets, including figures retained from earlier drafts. |
| `beamstudy.tex` | Reference draft; not automatically synchronized with the active manuscript. |
| `modeling.tex` | Companion/reference draft; also contains provenance for internal report citations. |
| `REVIEW.md` | Revision record, evidence checks, and remaining author/data questions. |
| `PRIOR_WORK_COMPARISON.md` | Page-by-page evidence map, figure comparison, and configuration differences relative to the supplied prior publication. |
| `tasks/README.md` | Prioritized editorial tasks using existing results and unchanged figures; currently Git-ignored local task documents. |
| `AGENTS.md` | Editing, validation, and version-control instructions. |
| `.gitignore` | Excludes generated LaTeX products and local task notes. |

The active source contains its own `thebibliography`; a separate BibTeX run is not required. The repository does not contain the lattice/input decks, original particle samples, controller code, or plotting scripts needed to reproduce the simulations. Compiling this repository reproduces the manuscript, not the scientific calculations.

## Build

Use a TeX distribution providing `pdflatex`, `latexmk`, the Elsevier `cas-sc` class (`els-cas-templates`), and the packages declared in the manuscript. The existing `subfigure` package is retained for compatibility. No package installation is needed when these dependencies are already available.

Run from the repository root. This example keeps generated files in a new temporary directory:

```bash
build_dir=$(mktemp -d "${TMPDIR:-/tmp}/mu2e-beamstudy.XXXXXX")
latexmk -pdf -interaction=nonstopmode -halt-on-error \
  -outdir="$build_dir" beamstudy-mod.tex
```

The resulting PDF is `$build_dir/beamstudy-mod.pdf`. If `latexmk` is unavailable, run `pdflatex` twice with the same output directory, then inspect the log for unresolved references. Retain the build directory until the PDF has been reviewed.

For optional visual verification with Poppler:

```bash
pdftoppm -r 120 -png "$build_dir/beamstudy-mod.pdf" "$build_dir/page"
```

Check for undefined citations/references, overfull boxes, clipped content, illegible figure text, and misplaced captions. The checked-in source uses a single-column review layout with double spacing and line numbers. Adapt journal-specific formatting only after the target journal is confirmed.

## Submission status

The September 2026 revision improves the prose, theory conventions, evidence qualifications, captions, and references. A second revision based on the complete prior publication identifies RFKO response, tune-step transit times, and post-interception scattering transport as the follow-up topics. A new manuscript table distinguishes shared parameters from differing foil thicknesses and acceptances. No new simulation results were added. Consult `REVIEW.md` and `PRIOR_WORK_COMPARISON.md` before submission: geometry, controller details, numerical convergence, particle-sample definitions, and diagnostic normalizations still need confirmation from the original calculations.

The citation to the companion tracking paper now uses its published record: Nuclear Engineering and Technology 58 (2026), 104097, DOI [10.1016/j.net.2025.104097](https://doi.org/10.1016/j.net.2025.104097). This does not select a target journal for the present manuscript.

## Current editorial plan

The author has requested journal-quality improvement with **no new simulations and the existing figures as is**. The local backlog in `tasks/README.md` contains nine ordered tasks (02–10), with scope, acceptance criteria, and a fallback for missing evidence. It covers the narrative, methods, theory, results, captions/layout, references, and final document checks. `tasks/Task_01.md` remains the original request.

Missing scientific evidence is handled through transparent limitations and narrower claims, not new runs. Figures may be sized and placed more clearly in TeX, but their image content is unchanged. Earlier requests for convergence runs, matched simulations, or replacement plots are outside this plan. Creating the backlog does not mean that its manuscript edits have been executed. The existing `.gitignore` rule for `tasks/` is preserved.

## Working rules

Edit `beamstudy-mod.tex` directly, preserve scientific provenance, and record substantive changes in `REVIEW.md`. Do not commit or push changes. Supply a proposed commit message with a subject, explanatory paragraph, and a `Files:` list, as specified in `AGENTS.md`.
