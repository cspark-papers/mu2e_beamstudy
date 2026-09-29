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

The September 2026 revision improves the prose, theory conventions, evidence qualifications, captions, and references. It does not add new simulation results. Consult `REVIEW.md` before submission: the ripple-amplitude convention, controller details, numerical convergence, particle-sample definitions, and diagnostic normalizations still need confirmation from the original calculations.

The citation to the companion tracking paper now uses its published record: Nuclear Engineering and Technology 58 (2026), 104097, DOI [10.1016/j.net.2025.104097](https://doi.org/10.1016/j.net.2025.104097). This does not select a target journal for the present manuscript.

## Working rules

Edit `beamstudy-mod.tex` directly, preserve scientific provenance, and record substantive changes in `REVIEW.md`. Do not commit or push changes. Supply a proposed commit message with a subject, explanatory paragraph, and a `Files:` list, as specified in `AGENTS.md`.
