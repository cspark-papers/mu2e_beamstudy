# Task 03 — Make methods and configurations explicit

Status: Done  
Priority: P1  
Depends on: Task 02

## Scope

`sec:scope`, Tables `table:param` and `table:scope`, and methods paragraphs across the results sections.

Follow `tasks/README.md`: no new simulations or results; preserve every scientific figure and panel unchanged. Edit the active manuscript directly when executing this task. Record substantive changes in `REVIEW.md`.

## Problem to address

Common machine parameters, prior solver settings, and the individual present calculations can be mistaken for one verified common simulation configuration.

## Work

- Organize already documented methods by case: extraction feedback, paused/restored tune-step tracking, reduced Hamiltonian, MARS-to-ring return tracking, and fixed-tune RFKO.
- Distinguish shared beam parameters from settings reported only in the prior work. Do not import a solver grid, kick count, bump waveform, or lattice version into current cases without evidence.
- Keep the 50 versus 100 micrometre foil values, 20 versus 35 pi mm mrad acceptances, and initial 95% emittance separate. Preserve stated values unless an existing source supports a correction.
- Clarify that 100-turn chirp sweeps, spill averaging, diagnostic windows, and controller updates are different concepts; the 200-turn ramp segments and 300/500-turn transit protocol describe different operations.
- Describe known sample selection and tracking endpoints. List missing normalization, version, gain, latency, weighting, or integration details once in REVIEW rather than scattering author questions throughout the prose.
- Add concise definitions in the existing table or text where useful; do not create speculative parameter entries.

## Acceptance criteria

- [x] Each present case can be identified without assuming it shares every published setting.
- [x] Known values, prior-only values, and unresolved metadata are clearly distinguished.
- [x] Ripple amplitude retains its documented ambiguity until source evidence resolves it.
- [x] No invented controller law, solver version, bandwidth, particle weight, or convergence claim.
- [x] Missing details lead to bounded interpretation, not a new-simulation task.

## If evidence is unavailable

Use the original stated setting with explicit scope, or state that the detail is not established. Preserve the author question in REVIEW. Do not silently substitute prior-paper values.

## Completion record

Completed: 2026-09-29.

- Split `sec:scope` into `sec:baseline` (shared parameters; settings documented only for Ref. [2]) and `sec:cases`. Rewrote the Table 1 caption and revised Table 2 into configuration and population differences, adding space-charge and ramp/bump rows marked as not documented for the present cases.
- Added Table 3 (`table:cases`) defining the five cases by model/configuration, time structure, and sample/endpoint, using only stated settings.
- Added a paragraph separating the intervals of about 100 turns (turn-on, display window, feedback accumulation, chirp sweep) from each other, from the undocumented controller update, and from the 200-turn segments and 300/500-turn tune-step protocol.
- Kept the ripple amplitude ambiguous by quoting the original wording. Added the documented tune-step shell selection and the optimized-ramp description from `beamstudy.tex`, and the documented chirp-spectrum description for the fixed-tune test. Condensed the `AUTHOR CHECK` comments.
- Listed the missing metadata once, by case, in REVIEW ("Case metadata status").
- Build succeeded (17 pages); labels are unique, all references and citations resolve, the only box warning is the known CAS keyword overlay, and all pages were inspected. Image files, reference drafts, and the bibliography are unchanged.
