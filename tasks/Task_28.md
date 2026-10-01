# Task 28 — Resolve the internal numerical inconsistencies

Status: Done  
Priority: P1  
Depends on: 27  
Source: `reviews/review2.md` major concern 2; `reviews/review1.md` concern 3; Tasks 11 and 12 evidence in REVIEW

> **Note from Task 27 (2026-10-01):** the recovered records resolve items 1–4 in the manuscript text: the ripple routine has a 360 Hz fundamental; the fixed-tune runs used a 16π normalized emittance (0.283 mm mrad rms); the aperture is a geometric 20 mm mrad Courant–Snyder limit; X = x/√β with the wire at −10 mm and β ≈ 8.7–8.9 m. What remains for this task is item 5 (Δp/p) and a consistency check of the new statements; see REVIEW, "Task 27 completed".

## Scope

`sec:rfko1`, `sec:rfko`, `sec:arrival`, the `fig:fig9`, `fig:rfko1`, and `fig:arrival2` captions, Table 1, and Appendix A.

## Findings

A careful referee will find these quickly; each is currently disclosed, not resolved.

1. **Ripple frequency.** The text gives 60 Hz, but the middle trace of Fig. 3 repeats about every 1,650 turns (~360 Hz, the 6th harmonic). A 60 Hz period is 9,834 turns.
2. **Initial emittance.** 20π mm mrad normalized 95% implies about 0.35π mm mrad rms geometric; Fig. 1(a) starts near 0.28.
3. **Acceptance convention.** A normalized 20π acceptance is about 2.1π geometric, but the C_x = 1 rms emittance reaches about 2.75π.
4. **Normalized transit coordinate.** The septum at −3.4 "normalized mm" versus x = −11 mm implies β ≈ 10.5 m if X = x/√β (Fig. 5 versus Fig. 7(a)).
5. **Momentum spread.** Is Δp/p = 0.0016 rms? IPAC2011's 0.007 chromatic spread for C_x = 1 suggests rms, but this is not established.

## Work

Using the records from Task 27, determine the correct value or convention for each item. Correct the text and captions, with the source recorded in REVIEW. Do not change any plot. Delete the corresponding `AUTHOR CHECK` comments and Appendix A entries.

## Acceptance criteria

- [x] Each item is resolved from a recorded source, or remains explicitly flagged with its arithmetic in REVIEW.
- [x] No resolution relies on reading values from raster images.
- [x] Figures are unchanged; both builds pass.

## If evidence is unavailable

Keep the current disclosures. Item 1 is a submission blocker: Fig. 3 cannot be described credibly while the applied frequency is unknown. Record it as such in the readiness report.

## Completion record

Completed: 2026-10-01.

- Items 1–4 were resolved in the manuscript text by Task 27 from the archived records and rechecked here. Item 1 is no longer a submission blocker: every archived ripple routine has a 360 Hz fundamental derived from 60 Hz three-phase rectification. Only the amplitude of the plotted runs is unrecorded.
- Item 5: Δp/p = 0.0016 is the rms of the matched beam (σ_z/β_z for the 40 ns rms bunch length; identical in all archived logs). Table 1 is relabeled with a caption note, and §4.1 gives the rms chromatic spread.
- The Table 1 caption now notes that the archived fixed-tune runs used 16π mm mrad.
- REVIEW ("Task 28 completed") records the sources and arithmetic. Both builds pass; figures are unchanged.
