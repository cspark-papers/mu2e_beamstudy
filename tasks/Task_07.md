# Task 07 — Clarify scattering transport and loss accounting

Status: Done  
Priority: P1  
Depends on: Tasks 03 and 04

## Scope

`sec:beamloss` and figures `fig:beamloss1`, `fig:beamloss2`, `fig:beamloss3`.

Follow `tasks/README.md`: no new simulations or results; preserve every scientific figure and panel unchanged. Edit the active manuscript directly when executing this task. Record substantive changes in `REVIEW.md`.

## Problem to address

The approximately 43% value applies to a returned scattered-particle sample, not all injected particles. Geometry, population selection, and the limited role of the reduced-model comparison must stay clear.

## Work

- Describe the existing three-stage Synergia2–MARS–Synergia2 workflow in readable prose, distinguishing primary interception, material transport, and subsequent ring tracking.
- Keep the 50 micrometre current scattering model separate from the published 100 micrometre geometric-loss model.
- State the denominator of 43% whenever needed in the abstract, result, or conclusion; do not multiply it by 1.2% or recast it as total extraction efficiency.
- Audit the statement that the remainder survives to extraction. Retain it only to the extent supported by existing records; do not equate “not reported lost within tracking” with proven eventual extraction if endpoints are undocumented.
- Explain the added circulating reference particles and flag their inclusion in the numerical denominator as unresolved if necessary.
- Present reduced-model phase-space shearing as a qualitative mechanism. It omits material, extraction fields, and removal and cannot validate loss probability or radiation dose.

## Acceptance criteria

- [x] The sample-selection chain and conditional denominator are unambiguous.
- [x] Survival and extraction endpoints are not silently equated.
- [x] MARS illustrations do not imply zero loss at ESS2 or an inclusive secondary-particle count.
- [x] No total-beam loss, activation, dose, or corrected efficiency estimate is created.
- [x] Existing images and the reported numerical result remain intact, with unsupported interpretation narrowed.

## If evidence is unavailable

Retain the reported conditional fraction with explicit limitations. Do not invent species, weights, coordinate transformations, duration, or numerical error bars.

## Completion record

Completed: 2026-09-29.

- Rewrote `sec:beamloss` around a numbered three-stage workflow (interception, MARS transport, ring tracking), with the 50 versus 100 µm foils contrasted once.
- Added the thin-foil signature (vertical line, Δ(αx+βx') = βΔx'), the three-turn return to the septum, and the two-population V-shape. Grounded the Fig. 6 shearing in differing H_K values.
- 43% audit: the denominator is the returned sample; "extracted" is attributed to the original study, with the undocumented duration and criterion stated; reference-particle inclusion is flagged; no combination with 1.2% and no injected-beam reading. `AUTHOR CHECK` added.
- Fig. 4 caption notes the undocumented axis units.
- Build succeeded (20 pages); labels are unique, all references resolve, and pages 13–17 were inspected. Image hashes are unchanged. The Fig. 7 float position is deferred to Task 08.
