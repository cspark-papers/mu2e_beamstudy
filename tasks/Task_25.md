# Task 25 — Consolidate undocumented-setting disclosures into a provenance table

Status: Todo  
Priority: P2  
Depends on: 22, 23, 24  
Review date: 2026-10-01

## Scope

`beamstudy-mod.tex`: all reader-facing "not documented" statements in the body and captions, Table 2 (`table:cases`; numbered Table 3 before the Section 2 rewrite), and `sec:limits`. This is a presentation change. Every disclosure must remain visible to the reader.

## Finding

The body now contains 24 occurrences of "not documented", 8 of them in figure captions, in addition to the cases-table caption and §7.4. Each disclosure is accurate, and the AGENTS rules require that missing methodology not be concealed. Repeated in running prose, however, they read as a list of gaps and will draw referee attention away from the results. A journal reader is better served by one authoritative place that states what the archived simulation records do and do not specify, case by case, with brief pointers elsewhere.

## Work

- Add a compact table, for example in an appendix or as an extension of the cases table (`table:cases`), listing for each case the settings that the available records do not specify:
  - spill normalization and controller gains, update interval, and delay;
  - selection and arrival criteria, integration step, and detection cadence;
  - the return mapping, tracking duration, extraction criterion, and sample weights;
  - emittance and action definitions and references;
  - chirp bandwidths;
  - plot overlays, legends, and axis units.

  Use the REVIEW "Case metadata status" and author-check rows as the source; include nothing those rows do not support.
- Replace repeated prose disclosures with a short qualifier and a pointer to the table where the disclosure is not needed to read the local sentence correctly.
- Keep in each caption only what a reader of that figure alone needs (for example, undocumented overlays or axis normalization).
- Keep in place every disclosure beside a number or claim that depends on it, such as the 43% denominator and the ripple-amplitude convention.
- Record before and after counts in REVIEW.

## Acceptance criteria

- [ ] Every undocumented setting disclosed before the edit is still disclosed, either in the table or locally.
- [ ] The conditional 43% fraction, the ripple-amplitude convention, and the action-diagnostic reference remain qualified where they are used.
- [ ] The count of reader-facing "not documented" phrases falls substantially, with the reduction recorded.
- [ ] Figures and reported values are unchanged; the rebuilt PDF is checked.

## If the author recovers metadata first

Any setting documented from the original files should be stated as a fact, with its source recorded in REVIEW, and removed from the table. This task does not require that recovery.

## Completion record

Pending. Findings recorded only; the manuscript has not been edited for this task.
