# Mu2e beam-study manuscript

This repository contains a journal manuscript on particle dynamics during third-integer resonant extraction from Fermilab's Delivery Ring for Mu2e. It covers a reduced resonance model, chromaticity-dependent RFKO excitation and RFKO spill feedback, transit times after a tune step, and the transport of septum-scattered particles, followed by a synthesis discussion.

## Files

| Path | Purpose |
| --- | --- |
| `beamstudy-mod.tex` | Active submission manuscript using Elsevier's `cas-sc` class. |
| `beamstudy-mod.bib` | Active manuscript references, formatted with `elsarticle-num`. |
| `highlights.txt` | Draft highlights (3–5 bullets, at most 85 characters) for author approval and separate upload. |
| `img/` | Existing PNG figure assets, including figures retained from earlier drafts. |
| `beamstudy.tex` | Reference draft; not automatically synchronized with the active manuscript. |
| `modeling.tex` | Companion/reference draft; also contains provenance for internal report citations. |
| `REVIEW.md` | Revision record, evidence checks, and remaining author/data questions. |
| `PRIOR_WORK_COMPARISON.md` | Page-by-page evidence map, figure comparison, and configuration differences relative to the supplied prior publication. |
| `tasks/README.md` | Prioritized editorial tasks using existing results and unchanged figures; tracked task documents. |
| `AGENTS.md` | Editing, validation, and version-control instructions. |
| `CLAUDE.md` | Symbolic link to `AGENTS.md` for agent tooling. |
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

The default build is the review layout: a contents list and a page break after the abstract, matching the companion manuscript. For a journal-submission build without them, define `\SubmissionBuild` before the class is loaded:

```bash
latexmk -pdf -interaction=nonstopmode -halt-on-error \
  -usepretex='\def\SubmissionBuild{}' \
  -outdir="$build_dir" beamstudy-mod.tex
```

For optional visual verification with Poppler:

```bash
pdftoppm -r 120 -png "$build_dir/beamstudy-mod.pdf" "$build_dir/page"
```

Check for undefined citations/references, overfull boxes, clipped content, illegible figure text, and misplaced captions. The checked-in source follows the companion manuscript's A4 single-column review layout: title/abstract/keywords followed by contents, a page break before the main text, double spacing, line numbers, and numbered `elsarticle-num` references. This author-requested format match does not establish compliance with a target journal's current submission rules. BibTeX runs without warnings. The two internal Mu2e DocDB reports (`wcm`, `rfkoreg`) are marked "n.d." (no date) because their dates could not be verified without Fermilab sign-on; no dates have been invented. The contents list is set in small type so that it stays on the title page, and it is omitted in the submission build.

## Submission status

The manuscript (23 pages in the review layout) has been revised editorially using only the existing results and figures; no new simulation was run. Since the September 2026 revisions it has:

- defined the five simulation cases separately from the published baseline (Table 3);
- made the reduced-model notation, units, and fixed points explicit;
- aligned figure descriptions with the plotted evidence;
- strengthened the physical interpretation of the RFKO, transit-time, and scattering results;
- reordered the sections, adding a Discussion with a consolidated "Scope of the evidence";
- corrected the beam momentum to 8.889 GeV/c (8 GeV kinetic energy per the Mu2e TDR, consistent with Bρ = 29.650 T m);
- added eight primary-source-verified references and audited all 22 citations.

The companion tracking paper is cited from its published record: Nuclear Engineering and Technology 58 (2026), 104097, DOI [10.1016/j.net.2025.104097](https://doi.org/10.1016/j.net.2025.104097). This does not select a target journal for the present manuscript.

Before submission, consult `REVIEW.md`:

- The author/data checks list the unresolved simulation metadata: ripple frequency (60 versus ~360 Hz), controller gains, particle selection and endpoints, and plot normalizations.
- The Task 09 author-only checklist covers acknowledgments, funding, CRediT, competing interests, data availability, AI-use disclosure, figure provenance, and the target journal.
- The Task 08 record notes that every figure asset prints below 300 dpi.

A successful build does not validate the underlying simulations.

## Current editorial plan

The author has requested journal-quality improvement with **no new simulations and the existing figures as is**. `tasks/README.md` indexes Tasks 02–17 with scope, acceptance criteria, and a fallback for missing evidence; `tasks/Task_01.md` preserves the original request. Missing scientific evidence is handled through transparent limitations and narrower claims, not new runs. Figures may be sized and placed in TeX, but their image content is unchanged.

| Status | Tasks |
| --- | --- |
| Done | 02 narrative, 03 methods, 04 theory, 05 RFKO, 06 transit times, 07 scattering, 08 captions/layout, 09 references/metadata, 11 figure–text, 12 numbers/units, 13 structure/discussion, 14 literature, 15 limitations/prose, 16 front matter, 17 build/bibliography/docs |
| Pending | 10 final editorial and document checks |

Completion notes for each task are in the task files and in `REVIEW.md`. The task files are tracked in Git.

## Working rules

Edit `beamstudy-mod.tex` directly, preserve scientific provenance, and record substantive changes in `REVIEW.md`. Do not commit or push changes. Supply a proposed commit message with a subject, explanatory paragraph, and a `Files:` list, as specified in `AGENTS.md`.
