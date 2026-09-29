# Task 04 — Polish theory, notation, and dimensional consistency

Status: Done  
Priority: P1  
Depends on: Task 03

## Scope

`sec:model`, equations `eqn:coordinates` through `eqn:motion`, and references to action, emittance, and time throughout the manuscript.

Follow `tasks/README.md`: no new simulations or results; preserve every scientific figure and panel unchanged. Edit the active manuscript directly when executing this task. Record substantive changes in `REVIEW.md`.

## Problem to address

The corrected Hamiltonian and phase conventions need a readable, internally consistent presentation, while the original plots use diagnostics whose exact normalization is not fully documented.

## Work

- Check conjugation, phase conventions, the relation g_aa = i g, the sign of S at Psi = pi, and the conversion between H and the three-turn Hamiltonian using printed algebra only.
- Define x, x-prime, X, X-prime, action, detuning, resonance strength, turn number, and physical time at first use. Keep X-prime distinct from a spatial derivative.
- Separate canonical normalized coordinates from the plotted pair (x, alpha x + beta x-prime). State square-root-length units of canonical coordinates when consistent length units are used.
- Distinguish geometric/normalized and rms/95% emittance, and centroid-relative spread from centroid motion, without asserting an unverified plotting convention.
- Simplify derivational prose while retaining enough definitions to interpret the results. Check only identities and existing arithmetic; do not integrate new trajectories.
- Explain unresolved axis conventions in captions or surrounding text without editing any pixels or inventing a conversion.

## Acceptance criteria

- [x] Equations are internally consistent and all symbols used in the interpretation are defined.
- [x] The turn/time conversion is consistent with the tabulated beam and ring values.
- [x] Hamiltonian consistency is not described as validation of historical simulation code.
- [x] Original plot axes are preserved and their known coordinate conventions are explained.
- [x] No new trajectory, analytic performance prediction, or figure is generated.

## If evidence is unavailable

Leave diagnostic normalization explicitly unresolved where necessary and use qualitative interpretation. A correct theoretical definition alone does not establish the plotted scale.

## Completion record

Completed: 2026-09-29.

- Rewrote `sec:model`. It now states the independent variable θ = 2πn required by the ×6π scaling, defines every symbol and its units at first use, adds the complex and real forms of Hamilton's equations, and warns that Kobayashi's ε is not an emittance.
- Added an action–emittance paragraph covering rms/normalized/95% conventions and centroid versus reference orbit, and a new Eq. (6) (`eqn:fixedpoints`) for the unstable fixed points and straight-line separatrix.
- Explained the plot conventions in the Fig. 3, 5, 7, and 8 captions and in the Sec. 5 text without editing any axes.
- Re-verified the printed algebra numerically (residuals ≤ 2.3e-13; 7.9e-10 for the finite-difference equations of motion). Build succeeded (17 pages); labels are unique, all references resolve, and the affected pages were inspected. Hashes of images, drafts, and the bibliography are unchanged.
- Open: the plotted normalizations (Fig. 3 axis, emittance and action diagnostics) and the Twiss parameters at the observation point remain author questions in REVIEW. Evidence for Tasks 11 and 12 is recorded there.
