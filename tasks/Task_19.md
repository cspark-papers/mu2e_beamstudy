# Task 19 — Separate sampling, resonance motion, and feedback-delay evidence

Status: Todo  
Priority: P1  
Depends on: 04, 06, 13  
Review date: 2026-09-30

## Scope

`beamstudy-mod.tex`: `sec:model`, `sec:arrival`, `sec:rfko1`, `sec:chain`, abstract, Conclusions, and the transit-time highlights. Source line numbers refer to the reviewed version.

Follow `tasks/README.md`: printed algebra and existing records only; no tracking, new timing distributions, parameter scans, or controller tests. This is a follow-up to the completed theory and transit-time edits.

## Findings

1. **The rotating-frame description implies stationarity even with nonlinear drive.** Line 196 says a particle exactly on resonance is stationary when observed once per turn. The rotating frame removes the linear resonant rotation, but the printed Hamiltonian still contains the cubic drive. Directly in Eq. `eqn:motion`, setting `epsilon=0` leaves `dX/dtau = 3S(X^2-X'^2)/4` and `dX'/dtau = -3SXX'/2`, generally nonzero. Qualify stationarity as the unperturbed linear motion, not the full resonantly driven motion. This finding follows from the manuscript's own equations; no simulation is needed.
2. **Three-turn output sampling is not independent evidence for physical quantization of arrival times.** Line 360 says reduced-model trajectories are recorded every three turns. Line 362 attributes the discrete timing levels in both calculations to a physical return to the septum side every third turn. Without knowing whether arrival was checked every integration step, every turn, or only at output, the reduced-model levels could also reflect sampling. A time-axis conversion `n=3*tau` does not establish an arrival-detection cadence. Preserve the visible levels but separate observation, sampling, and the possible resonance interpretation.
3. **Starting horizontal position alone does not establish a trajectory's branch or closest saddle approach.** Line 362 labels particles between two vertical lines as already on the outgoing branch and says particles on the far side must pass an unstable fixed point. The plot displays only starting horizontal coordinate versus time, while line 364 correctly says transit depends on the full initial phase-space coordinates. Retain these pathway explanations only as interpretations of the selected shell, unless existing two-coordinate records establish them; a vertical fixed-point marker alone does not do so.
4. **A finite tune-step diagnostic is promoted to an explanation of the RFKO controller.** Lines 316, 366, and 427–429 transfer its arrival-time range and stage trend to the RFKO response, and say this explains why proportional-only control oscillated and the derivative term helped. The manuscript separately states that the configurations, particle selections, controller gains, and transfer functions are not matched or documented. The selected distributions can motivate a delay mechanism, but cannot establish the actual RFKO loop's delay or the cause of its spikes/oscillations. Likewise, larger displayed late-stage maxima in a truncated, changing sample do not establish a general law that the effective loop delay grows throughout extraction.

## Work and fallback

- Correct the rotating-frame sentence using the existing equations, without changing the Hamiltonian or generating trajectories.
- Distinguish integration step, output interval, arrival detection, and the three-turn time unit. Ask for existing arrival-detection documentation; if unavailable, explicitly leave the origin of the discrete levels unresolved.
- State the observed coordinate/time and stage trends; label phase-space pathways and long-time explanations as qualitative interpretations where the initial momentum or full trajectory is not shown.
- Present the tune-step-to-feedback connection as a plausible mechanism across separate cases. Keep the demonstrated feedback observation separate from the proposed cause of its residual fluctuations.
- Propagate this scope to the abstract, Discussion, Conclusions, and highlights. Record any unresolved detection and selection questions under the existing transit/controller checks in `REVIEW.md` when implementing the task.

## Acceptance criteria

- [ ] Stationarity is not attributed to all particles at zero detuning with nonzero resonance drive.
- [ ] Neither output cadence nor time rescaling is treated as proof of a physical arrival-time interval.
- [ ] Branch membership is not deduced from one coordinate alone.
- [ ] The tune-step sample is not presented as a measured RFKO transfer function or a demonstrated cause of controller behavior.
- [ ] The observed stage dependence remains scoped to the displayed, finite diagnostic; all scientific images and results remain unchanged.

## Completion record

Pending. Findings recorded only; the manuscript has not been edited for this task.
