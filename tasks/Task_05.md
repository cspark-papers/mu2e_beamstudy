# Task 05 — Strengthen RFKO results and physical interpretation

Status: Done  
Priority: P1  
Depends on: Tasks 03 and 04

## Scope

`sec:rfko1`, `sec:rfko`, and figures `fig:fig9`, `fig:rfko1`, `fig:rfko2`.

Follow `tasks/README.md`: no new simulations or results; preserve every scientific figure and panel unchanged. Edit the active manuscript directly when executing this task. Record substantive changes in `REVIEW.md`.

## Problem to address

The feedback comparison and the fixed-tune chromaticity tests answer different questions. The narrative should connect them physically without claiming a quantitative control-system validation.

## Work

- Present each result as setup, visible observation, physical interpretation, and implication for the paper’s question.
- Explain the three spill traces and residual spikes. Describe the shown controller as proportional–derivative and avoid calling the gains optimal without documented evidence.
- Separate the prior projected factor 1.5–3 improvement from demonstrated current results. Do not derive suppression ratios, spectra, duty factors, or uncertainty from the images.
- Explain why coherent centroid motion need not imply increased emittance about the centroid. Describe the chromaticity comparison as consistent with phase mixing, within the documented case.
- Make clear that the tune 9.65 test disables resonance drive and does not directly show extraction.
- Explain that aperture removal and diagnostic normalization affect action-distribution heights. Do not claim conserved population or a calibrated diffusion rate.

## Acceptance criteria

- [x] The feedback and fixed-tune cases are clearly distinguished.
- [x] Conclusions match the visible traces without new numerical metrics.
- [x] The action diagnostic is identified accurately and unknown normalization is not concealed.
- [x] No transfer function, stability margin, optimal controller, or space-charge-only causal claim is inferred.
- [x] Interpretation is concise and positive about what the existing results support.

## If evidence is unavailable

Retain qualitative comparisons. Move unresolved gain/filter/bandwidth/calibration details to the author-check record and state only limitations needed to interpret the result.

## Completion record

Completed: 2026-09-29.

- Sec. 3: restructured as controller → three-trace observation → delayed-correction interpretation (100-turn averaging plus the transit times of Sec. 4.2) → bounded implication. PD attributed to the original study, "(not shown)" added for P-only, "most favorable" removed, and the 1.5–3 expectation kept separate.
- Sec. 5: added the dephasing and filamentation mechanism, the rigid-dipole space-charge argument, a bandwidth caveat for C_x = 0, an interpretation of Figs. 7 and 8, the identification of f(√I)/√I as phase-space density (checked by sampling), and the implication for C_x = 1 in the feedback case.
- No new numerical metric; the pixel check behind the spike-height wording is recorded only in REVIEW. Build succeeded (19 pages); labels are unique, all references resolve, and the affected pages were inspected. Image hashes are unchanged.
