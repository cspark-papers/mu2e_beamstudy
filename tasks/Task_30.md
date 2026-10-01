# Task 30 — Quantify the results from existing output data (requires a scope decision)

Status: Blocked — awaiting author authorization  
Priority: P1  
Owner: Author decision, then author or editor  
Depends on: 27  
Source: `reviews/review2.md` major concern 1 and improvement item 3; `reviews/review1.md` concerns 2–3

## Scope boundary

`tasks/README.md` currently prohibits new ripple-suppression metrics, loss fractions, uncertainty estimates, and quantitative conclusions inferred from raster plots. Computing metrics from the **original output files** (not from images, and without new simulations) is a scope change. **It requires explicit author authorization, recorded in `tasks/README.md` and REVIEW, before any work starts.**

## Candidate quantities (each from existing outputs only)

- **Feedback:** rms spill fluctuation or duty factor, with and without feedback, over a stated window, plus the ripple spectrum. Both reviews ask what practical improvement is established, and under which reproducible conditions.
- **Transit times:** per-stage particle counts, medians and percentiles, and the fraction beyond the displayed window.
- **Scattering:** returned-sample size and weights, and the statistical uncertainty of the 43% fraction with its exact denominator.

## Work (only after authorization)

1. Define each metric before computing it: window, normalization, and estimator. Compute from the original files with a script kept outside the manuscript, and record inputs and outputs in REVIEW.
2. Add the metrics to the results with their definitions. Do not alter figures unless Task 29 is authorized.
3. Re-check the abstract, Discussion, Conclusions, and highlights against the new numbers.

## Acceptance criteria

- [ ] Authorization is recorded, and every metric is traceable to an original output file and a script.
- [ ] No metric is derived from rasterized figures.
- [ ] Uncertainties are stated where a sample size exists; both builds pass.

## If not authorized

Keep the qualitative results. Review 2 rates the paper's prospects at PRAB as low without such numbers; carry this into Task 31.

## Completion record

Pending.
