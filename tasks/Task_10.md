# Task 10 — Complete the editorial pass and verify the document

Status: Todo  
Priority: P2  
Depends on: Tasks 02–09

## Scope

Complete `beamstudy-mod.tex`, its compiled PDF, `REVIEW.md`, and task completion records.

Follow `tasks/README.md`: no new simulations or results; preserve every scientific figure and panel unchanged. Edit the active manuscript directly when executing this task. Record substantive changes in `REVIEW.md`.

## Problem to address

A coherent revision needs one final pass across scientific scope, terminology, typography, and the actual rendered document. Editorial completion and submission readiness must be reported separately.

## Work

- Revisit the title, abstract, introduction, and conclusions after the results edits. Ensure each asserted finding is supported by an existing figure or equation.
- Standardize terminology, abbreviations, units, significant figures, figure/equation references, and journal-style prose. Reduce repeated caveats without deleting material limitations.
- Compile from the repository root using README instructions and a temporary output directory. Resolve citation/reference and label problems; inspect warnings rather than suppressing them indiscriminately.
- Render and inspect every PDF page: equations, tables, captions, line numbers, floats, bibliography, and page count. The existing CAS keyword-overlay warning may be documented if its visual behavior is unchanged and harmless.
- Compare the final diff and image hashes with the pre-edit state. Verify no simulation outputs, scientific image changes, or edits to reference drafts were introduced.
- Record actual checks and remaining author-only issues in REVIEW. Mark tasks Done only when their criteria pass; distinguish unresolved essential metadata from optional future research.
- Supply the revised source/PDF, concise revision summary, and proposed commit message in the established subject/paragraph/Files format. Do not stage, commit, or push.

## Acceptance criteria

- [ ] Build succeeds with resolved citations and references, unique labels, and reviewed warnings.
- [ ] Every final PDF page is visually inspected, and all existing figure content is preserved.
- [ ] No new simulation was run and no new data-dependent result was introduced.
- [ ] Final prose is consistent across sections and explicitly scopes the conditional loss and model limitations.
- [ ] REVIEW and task statuses describe work actually completed.
- [ ] Remaining author confirmations and journal-specific gaps are stated without claiming guaranteed acceptance or scientific validation from a successful build.

## If evidence is unavailable

Complete independent editorial and document checks. Report any essential unresolved method/normalization or figure-readability limitation candidly; do not mark the submission fully ready merely because the PDF compiles.

## Completion record

Pending. Record changed sections, checks performed, and unresolved author questions here before marking Done.
