# Task 28 — Resolve the internal numerical inconsistencies

Status: Todo  
Priority: P1  
Depends on: 27  
Source: `reviews/review2.md` major concern 2; `reviews/review1.md` concern 3; Tasks 11 and 12 evidence in REVIEW

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

- [ ] Each item is resolved from a recorded source, or remains explicitly flagged with its arithmetic in REVIEW.
- [ ] No resolution relies on reading values from raster images.
- [ ] Figures are unchanged; both builds pass.

## If evidence is unavailable

Keep the current disclosures. Item 1 is a submission blocker: Fig. 3 cannot be described credibly while the applied frequency is unknown. Record it as such in the readiness report.

## Completion record

Pending.
