# Mu2e beam-study manuscript

This repository contains a journal manuscript on particle dynamics during third-integer resonant extraction from Fermilab's Delivery Ring for Mu2e. It covers RFKO spill feedback, transit-time calculations, septum-scattered particle tracking, and chromaticity-dependent RFKO excitation.

## Files

| Path | Purpose |
| --- | --- |
| `beamstudy-mod.tex` | Active submission manuscript using Elsevier's `cas-sc` class. |
| `beamstudy-mod.bib` | Active manuscript references, formatted with `elsarticle-num`. |
| `img/` | Existing PNG figure assets, including figures retained from earlier drafts. |
| `beamstudy.tex` | Reference draft; not automatically synchronized with the active manuscript. |
| `modeling.tex` | Companion/reference draft; also contains provenance for internal report citations. |
| `REVIEW.md` | Revision record, evidence checks, and remaining author/data questions. |
| `PRIOR_WORK_COMPARISON.md` | Page-by-page evidence map, figure comparison, and configuration differences relative to the supplied prior publication. |
| `tasks/README.md` | Prioritized editorial tasks using existing results and unchanged figures; tracked task documents. |
| `AGENTS.md` | Editing, validation, and version-control instructions. |
| `.gitignore` | Excludes generated LaTeX products. |

The active source uses `beamstudy-mod.bib` and the `elsarticle-num` bibliography style, matching the companion manuscript `../mu2e_modeling-submission/mu2e_modeling.tex`. `latexmk` runs BibTeX automatically. The repository does not contain the lattice/input decks, original particle samples, controller code, or plotting scripts needed to reproduce the simulations. Compiling this repository reproduces the manuscript, not the scientific calculations.

## Build

Use a TeX distribution providing `pdflatex`, `bibtex`, `latexmk`, the Elsevier `cas-sc` class (`els-cas-templates`), the `elsarticle-num.bst` style, and the packages declared in the manuscript. The existing `subfigure` package is retained for compatibility. No package installation is needed when these dependencies are already available.

Run from the repository root. This example keeps generated files in a new temporary directory:

```bash
build_dir=$(mktemp -d "${TMPDIR:-/tmp}/mu2e-beamstudy.XXXXXX")
latexmk -pdf -interaction=nonstopmode -halt-on-error \
  -outdir="$build_dir" beamstudy-mod.tex
```

The resulting PDF is `$build_dir/beamstudy-mod.pdf`. If `latexmk` is unavailable, use the following sequence from the repository root:

```bash
pdflatex -interaction=nonstopmode -halt-on-error -output-directory="$build_dir" beamstudy-mod.tex
bibtex "$build_dir/beamstudy-mod"
pdflatex -interaction=nonstopmode -halt-on-error -output-directory="$build_dir" beamstudy-mod.tex
pdflatex -interaction=nonstopmode -halt-on-error -output-directory="$build_dir" beamstudy-mod.tex
```

Inspect the final log for unresolved references. Retain the build directory until the PDF has been reviewed.

For optional visual verification with Poppler:

```bash
pdftoppm -r 120 -png "$build_dir/beamstudy-mod.pdf" "$build_dir/page"
```

Check for undefined citations/references, overfull boxes, clipped content, illegible figure text, and misplaced captions. The checked-in source follows the companion manuscript's A4 single-column review layout: title/abstract/keywords followed by contents, a page break before the main text, double spacing, line numbers, and numbered `elsarticle-num` references. This author-requested format match does not establish compliance with a target journal's current submission rules. BibTeX reports empty-year warnings for the combined PIMMS entry (the two part-specific years remain in its text) and the undated internal monitor reports; no dates have been invented.

## Submission status

The September 2026 revision improves the prose, theory conventions, evidence qualifications, captions, and references. A second revision based on the complete prior publication identifies RFKO response, tune-step transit times, and post-interception scattering transport as the follow-up topics. A new manuscript table distinguishes shared parameters from differing foil thicknesses and acceptances. No new simulation results were added. Consult `REVIEW.md` and `PRIOR_WORK_COMPARISON.md` before submission: geometry, controller details, numerical convergence, particle-sample definitions, and diagnostic normalizations still need confirmation from the original calculations.

The citation to the companion tracking paper now uses its published record: Nuclear Engineering and Technology 58 (2026), 104097, DOI [10.1016/j.net.2025.104097](https://doi.org/10.1016/j.net.2025.104097). This does not select a target journal for the present manuscript.

## Current editorial plan

The author has requested journal-quality improvement with **no new simulations and the existing figures as is**. The local backlog in `tasks/README.md` contains ordered Tasks 02–17, with scope, acceptance criteria, and a fallback for missing evidence. Tasks 11–17 were added after a manuscript review on 2026-09-29. It covers the narrative, methods, theory, results, captions/layout, references, and final document checks. `tasks/Task_01.md` remains the original request.

Missing scientific evidence is handled through transparent limitations and narrower claims, not new runs. Figures may be sized and placed more clearly in TeX, but their image content is unchanged. Earlier requests for convergence runs, matched simulations, or replacement plots are outside this plan. Task 02 is complete: the title, abstract, introduction, scope discussion, and conclusion have been revised and the 16-page PDF checked. Task 03 is complete: Sec. 2 now separates shared parameters, published-only settings, and five individually defined simulation cases (new Table 3); the PDF is 17 pages. Task 04 is complete: the reduced-model section defines its independent variable, symbols, units, action–emittance conventions, and unstable fixed points. Task 11 is complete: figure descriptions now match the plotted content, and undocumented plot elements and the apparent ~360 Hz spill modulation are flagged for the author (PDF now 18 pages). Task 05 is complete: both RFKO sections now move from setup to observation, physical interpretation, and implication (PDF now 19 pages). Task 06 is complete: the transit-time section separates the ideal transit time from the tune-step diagnostic and explains both figures (PDF now 20 pages). Task 07 is complete: the scattering section presents a numbered interception–MARS–ring-tracking workflow and a denominator-explicit, endpoint-qualified 43% result. Task 08 is complete: captions are self-contained, Fig. 2 is enlarged, float order follows first references, and the asset inventory and resolution limits are recorded (PDF now 21 pages). Task 13 is complete: sections now run baseline → model → RFKO (mechanism, then feedback) → transit times → scattering → Discussion → Conclusions (PDF now 22 pages). Task 15 is complete: each scope limit is stated once in full (Sec. 2.1, §7.3, and the new §7.4 "Scope of the evidence"), and hedging fell by about 30%. Task 12 is complete: the beam momentum is corrected to 8.889 GeV/c (8 GeV kinetic energy per the Mu2e TDR, consistent with Bρ = 29.650 T m), all derived numbers are verified, and units use siunitx. Task 14 is complete: eight primary-source-verified references now position the work against RFKO, spill-quality, septum-loss, and current Mu2e spill-regulation literature (PDF now 23 pages). Tasks 09, 10, 16, and 17 remain pending; see the task index and `REVIEW.md` for the completion record. The task files are tracked in Git; `.gitignore` no longer excludes `tasks/`.

## Working rules

Edit `beamstudy-mod.tex` directly, preserve scientific provenance, and record substantive changes in `REVIEW.md`. Do not commit or push changes. Supply a proposed commit message with a subject, explanatory paragraph, and a `Files:` list, as specified in `AGENTS.md`.
