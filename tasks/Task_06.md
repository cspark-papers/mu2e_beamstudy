# Task 06 — Clarify the tune-step and transit-time evidence

Status: Done  
Priority: P1  
Depends on: Tasks 03 and 04

## Scope

`sec:arrival` and figures `fig:arrival1` and `fig:arrival2`.

Follow `tasks/README.md`: no new simulations or results; preserve every scientific figure and panel unchanged. Edit the active manuscript directly when executing this task. Record substantive changes in `REVIEW.md`.

## Problem to address

Elapsed time after a finite tune step can include particles already in transit. Differences between full tracking and the reduced model do not isolate a single physical cause.

## Work

- State the pause/restoration sequence, the early/middle/late stages, the stated initial sample, and the approximate 300-turn pause and 500-turn observation interval consistently.
- Distinguish an ideal single-particle instability-to-septum time from the diagnostic’s elapsed time after restoration. Identify any unconfirmed selection or start-time detail without inventing it.
- Explain the circulating-population traces, spill bursts, scatter points, and marginal distributions using the existing figures.
- Link long delays qualitatively to slow passage near hyperbolic fixed points; remove any residual universal inverse-distance claim.
- Explain the model differences without attributing all discrepancies to space charge. State that the finite observation window limits interpretation of tails.
- Relate the observed spread of arrival times to delayed beam response, without extracting a new delay constant or controller bandwidth.

## Acceptance criteria

- [x] Time origins, pause/restoration turns, and observation intervals are not conflated.
- [x] The ideal transit concept and measured diagnostic are distinguished.
- [x] No unsupported percentiles, fitted tail law, missing-tail correction, or causal isolation is introduced.
- [x] The RK4 model is described as a reduced interpretation, not a validated substitute for the full lattice.
- [x] No matched space-charge or longer-duration run is required.

## If evidence is unavailable

Explicitly describe the available diagnostic and its limits. Retain questions about restoration, selection, and particle counts in REVIEW; do not construct replacement distributions.

## Completion record

Completed: 2026-09-29.

- Separated the ideal transit time from the diagnostic elapsed time after the common restoration step, and flagged the undocumented selection and arrival criteria.
- Stated the protocol consistently and linked the stages to the shrinking stable region (Eq. 6). Explained burst size and delay (Fig. 2) and the histogram roles, discrete levels, and stage trends (Fig. 3).
- Restated the mechanism positively (passage near unstable fixed points) without the inverse-distance law, kept the space-charge attribution non-unique, and added the observation-window caveat.
- Added the spill-regulation implication (spread of arrival times leads to a gradual response) without a delay constant or transfer function.
- Build succeeded (20 pages); labels are unique, all references resolve, and pages 9–13 were inspected. Image hashes are unchanged. The pixel check for the discrete levels is recorded only in REVIEW.
