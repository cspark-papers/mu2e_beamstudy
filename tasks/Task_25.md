# Task 25 — Consolidate undocumented-setting disclosures into a provenance table

Status: Done  
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

- [x] Every undocumented setting disclosed before the edit is still disclosed, either in the table or locally.
- [x] The conditional 43% fraction, the ripple-amplitude convention, and the action-diagnostic reference remain qualified where they are used.
- [x] The count of reader-facing "not documented" phrases falls substantially, with the reduction recorded.
- [x] Figures and reported values are unchanged; the rebuilt PDF is checked.

## If the author recovers metadata first

Any setting documented from the original files should be stated as a fact, with its source recorded in REVIEW, and removed from the table. This task does not require that recovery.

## Completion record

Completed: 2026-10-01.

- Added Appendix A with Table 4 (`table:records`), listing the settings and conventions missing from the records case by case, sourced only from the REVIEW author checks.
- Kept the disclosures that sit beside dependent numbers or claims, or that a reader of a single caption needs. Replaced the secondary ones with pointers to Appendix A.
- Main-body "not documented": 28 → 16 (7 in captions); broad hedge count 74 → 63. All 28 earlier disclosures were checked as preserved locally or in Table 4.
- The 43% denominator, the ripple-amplitude convention (Sec. 4.2 and Table 4), and the action-diagnostic reference (Sec. 4.1, the Fig. 2 caption, and Table 4) remain qualified where used.
- The appendix starts on its own page and is excluded from the review-only contents list. Both builds pass (25 pages; 0 BibTeX warnings; known CAS overlay only); all hashes are unchanged.
