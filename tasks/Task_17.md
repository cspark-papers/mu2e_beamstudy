# Task 17 — Fix the build, bibliography structure, and repository documentation

Status: Todo  
Priority: P2  
Depends on: None

## Scope

`README.md`, `beamstudy-mod.bib`, the preamble of `beamstudy-mod.tex`, and the task index.

Follow `tasks/README.md`: no new simulations or results; preserve every scientific figure and panel unchanged. Edit the active manuscript directly when executing this task. Record substantive changes in `REVIEW.md`.

## Problem to address

The companion-format conversion left the documentation and bibliography out of step with the source:

- `README.md` still says the source "contains its own `thebibliography`; a separate BibTeX run is not required." The manuscript now uses `\bibliography{beamstudy-mod}` with `elsarticle-num`, and REVIEW records the README as already updated, which it is not.
- `beamstudy-mod.bib` and `CLAUDE.md` (a link to `AGENTS.md`) are tracked since commit `f669ffb`, but neither appears in the README file table.
- BibTeX warns about a missing year for `pimms` and `wcm` because each key merges two separate documents: PIMMS Parts I and II, and Mu2e Documents 3627-v4 and 3625-v1. Merged entries render badly and complicate citation.
- The preamble defines `\floatpagepagefraction`, which LaTeX does not use; the real parameter is `\floatpagefraction`. The line has no effect.

## Work

- Update `README.md` for the BibTeX build: the file table, build notes (latexmk runs BibTeX automatically), and "Submission status". Correct the REVIEW statement to describe what actually happened.
- Split the `pimms` and `wcm` entries into one entry per document, each with its verified metadata (Task 09 rules apply), and update the `\cite` commands. Leave the dates of internal reports empty rather than inventing them; record the remaining warnings.
- Replace `\floatpagepagefraction` with `\floatpagefraction`, or remove the line, then check that the float placement in the rendered PDF is unchanged or better.
- Add `beamstudy-mod.bib` and `CLAUDE.md` to the README file table. Do not stage anything.
- Add Tasks 11–17 to the index in `tasks/README.md` (already done when these tasks were created) and keep their statuses current.

## Acceptance criteria

- [ ] The README build instructions reproduce the PDF from a clean temporary directory.
- [ ] BibTeX reports no merged-entry warnings; any remaining warnings concern genuinely unknown dates and are documented.
- [ ] No unused or misspelled layout macros remain, and the rendered layout has been inspected.
- [ ] REVIEW and README agree on the build procedure.

## If evidence is unavailable

If the metadata for the second document in a merged entry can't be verified, keep that document as a separate entry with only the verified fields and record the gap.

## Completion record

Pending. Record changed sections, checks performed, and unresolved author questions here before marking Done.
