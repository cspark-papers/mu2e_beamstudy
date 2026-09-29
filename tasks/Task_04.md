# Task 04 — Polish theory, notation, and dimensional consistency

Status: Todo  
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

- [ ] Equations are internally consistent and all symbols used in the interpretation are defined.
- [ ] The turn/time conversion is consistent with the tabulated beam and ring values.
- [ ] Hamiltonian consistency is not described as validation of historical simulation code.
- [ ] Original plot axes are preserved and their known coordinate conventions are explained.
- [ ] No new trajectory, analytic performance prediction, or figure is generated.

## If evidence is unavailable

Leave diagnostic normalization explicitly unresolved where necessary and use qualitative interpretation. A correct theoretical definition alone does not establish the plotted scale.

## Completion record

Pending. Record changed sections, checks performed, and unresolved author questions here before marking Done.
