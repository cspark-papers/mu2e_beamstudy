# Task 03 — Make methods and configurations explicit

Status: Todo  
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

- [ ] Each present case can be identified without assuming it shares every published setting.
- [ ] Known values, prior-only values, and unresolved metadata are clearly distinguished.
- [ ] Ripple amplitude retains its documented ambiguity until source evidence resolves it.
- [ ] No invented controller law, solver version, bandwidth, particle weight, or convergence claim.
- [ ] Missing details lead to bounded interpretation, not a new-simulation task.

## If evidence is unavailable

Use the original stated setting with explicit scope, or state that the detail is not established. Preserve the author question in REVIEW. Do not silently substitute prior-paper values.

## Completion record

Pending. Record changed sections, checks performed, and unresolved author questions here before marking Done.
