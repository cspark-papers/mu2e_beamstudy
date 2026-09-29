# Task 12 — Audit numerical and unit consistency

Status: Todo  
Priority: P1  
Depends on: Task 03; coordinate with Task 04

## Scope

Table `table:param`, every printed number and unit in the text, and the unit conventions implied by the figure axes.

Follow `tasks/README.md`: no new simulations or results; preserve every scientific figure and panel unchanged. Edit the active manuscript directly when executing this task. Record substantive changes in `REVIEW.md`.

## Problem to address

Printed algebra has been checked (REVIEW), but the tabulated beam parameters have not been cross-checked against each other or against the plotted scales. The review arithmetic below found one probable table inconsistency and two convention questions. Only arithmetic from printed values is used; nothing is inferred as a new result.

## Findings to resolve

1. **Momentum versus rigidity.** A proton with 8 GeV kinetic energy has p = 8.8889 GeV/c and Bρ = 29.650 T m. The table's Bρ = 29.650 T m matches that value, but its momentum of 8.886 GeV/c gives Bρ = 29.641 T m. Check the prior publication's Table 1 and the Mu2e TDR. If they give 8.889 GeV/c (or 8 GeV kinetic energy), correct the momentum and record the correction. Otherwise keep the value and record the inconsistency. The revolution time is insensitive to this difference: it remains 1.69 µs.
2. **Initial emittance versus Fig. 7(a).** For 20π mm mrad normalized 95% emittance, assuming a Gaussian with ε95 ≈ 6 ε_rms and βγ = 9.474, the rms geometric emittance is about 0.35π mm mrad. The C_x = 0 curve in Fig. 7(a) starts near 0.28π mm mrad. Ask the author which emittance definition the diagnostic uses, including any centroid subtraction, distribution truncation, or matching. Do not relabel the plot, and do not claim that the numbers agree.
3. **Acceptance convention.** A normalized 20π mm mrad acceptance corresponds to about 2.1π mm mrad geometric. The C_x = 1 rms emittance in Fig. 7(a) reaches about 2.75π mm mrad, which a hard aperture of that geometric size could not allow. This suggests that the diagnostic acceptance, or the plotted emittance, uses a different convention. Add this to the existing acceptance question in REVIEW; it strengthens the case for the "conversion convention requires confirmation" entry in Table 2.
4. **Normalized coordinate scale.** The septum line lies at about −3.4 in "normalized x (mm)" in Fig. 3 but at x ≈ −11 mm in Fig. 5(a). If the plots use X = x/√β, this implies β ≈ 10 m at the observation point, assuming β in metres. Ask for the Twiss parameters at ESS1 and the plotting normalization. Do not state β in the manuscript without a source.
5. **Table hygiene.** Add a unit or "—" for protons per spill and the dimensionless rows. State whether Δp/p = 0.0016 is rms, a half-width, or a full width (an existing REVIEW question). Consider adding the revolution time (1.69 µs) and revolution frequency (0.590 MHz): these are derived from tabulated values and consistent with h = 4 and 2.36 MHz. Mark any such row as derived.
6. **Consistent number style.** Apply one style throughout: `\num`/`\SI` from `siunitx` (already loaded but hardly used), thin-space thousands separators, and "π mm mrad" formatting. Keep "µm", "µs", and "µrad" consistent between text and tables.

## Acceptance criteria

- [ ] Every derived number in the text reproduces from the tabulated values within its printed precision; any exception is recorded.
- [ ] Any corrected value is backed by a source or an explicit calculation recorded in REVIEW.
- [ ] Unit and convention questions that can't be answered from existing sources are listed once in REVIEW, not scattered through the prose.
- [ ] Figure axes are unchanged.

## If evidence is unavailable

Keep the printed value, add an `AUTHOR CHECK` comment beside it, and record the arithmetic in REVIEW.

## Completion record

Pending. Record changed sections, checks performed, and unresolved author questions here before marking Done.
