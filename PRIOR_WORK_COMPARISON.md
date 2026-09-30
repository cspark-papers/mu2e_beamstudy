# Relationship to the published Mu2e tracking study

Reviewed 2026-09-29 against the complete 11-page PDF supplied by the author:

Chong Shik Park, *Tracking simulation of third-integer resonant extraction for Fermilab's Mu2e experiment*, Nuclear Engineering and Technology 58 (2026), 104097, DOI [10.1016/j.net.2025.104097](https://doi.org/10.1016/j.net.2025.104097). The article was available online on 31 December 2025. The filename's NET2025 prefix does not change the volume/year citation.

Source filename: `NET2025-Tracking Simulation of Third-Integer Resonant Extraction for Fermilab’s Mu2e Experiment.pdf`, supplied from the author's Downloads directory. Page references below use the PDF's printed page numbers, 1–11. The source PDF was read and rendered for inspection, not modified or copied into the repository.

## Scope of the follow-up manuscript

The prior article explicitly excludes RFKO from its simulations (pp. 2, 4–5) and reserves closed-loop performance for future work (pp. 5, 11). Its contributions are the feed-forward tune ramp, septum geometry and apertures, and dynamic-bump correction. The present manuscript can therefore focus on three complementary subjects: RFKO response and chromatic mixing, tune-step transit-time diagnostics, and transport of a septum-scattered sample beyond geometric interception. This is a distinction from this particular prior publication, not a claim that RFKO or the Kobayashi model is novel in the wider literature.

The current plots are not a complete demonstration of the future integrated feedback system described in the prior article. Original input decks and a common configuration are needed to establish that connection quantitatively.

## Evidence and revision map

| Prior publication location | What it establishes | Revision in `beamstudy-mod.tex` |
| --- | --- | --- |
| pp. 1–2, introduction; p. 11, conclusion | Feed-forward scope; RFKO excluded and feedback reserved for follow-up. | Rewritten title, abstract, introduction, and conclusions identify the additional particle-response studies. Dynamic-bump optimization is explicitly prior work. |
| p. 2, Table 1 | Shared ring/beam values; 100 micrometre foil thickness. | Table 1 attributes the shared values. New scope table distinguishes the current 50 micrometre scattering setup. No foil value was silently changed. |
| pp. 2–3, Sec. 2 | Hockney grid 64×64×128, 240 kicks/turn; 2.5D/3D tune-shift comparison; harmonic 4, 2.36 MHz, 10 kV. | New baseline section reports these as prior settings. They are not asserted as verified current inputs or convergence tests for spill/loss tails. |
| pp. 3–4, Secs. 3–4 | Sextupole excitation over the first 100 turns; 200-turn tune-ramp segments. | Distinguishes initialization and feed-forward segments from 100-turn chirp/feedback intervals and the 300/500-turn transit diagnostic. |
| p. 4, Sec. 4; p. 5, Fig. 5 | Spill reported within ±20% about the mean for the feed-forward case. | Cited as a prior open-loop result, not a new controller result or a newly calculated RMS metric. |
| p. 2, RFKO discussion | Expected factor 1.5–3 ripple reduction inferred from other facilities, without a Mu2e closed-loop simulation. | Explicitly identifies that factor as an expectation not tested numerically by the current qualitative traces. |
| p. 3, Eq. (1); p. 7, Eq. (6) | Angle–action Hamiltonian and geometric Courant–Snyder invariant. | Adds the action definition and an explicit phase-convention relation: with `a = sqrt(Ix) exp(-i phi_x)`, the angle–action coefficient is `g_aa = i g` for the displayed complex Hamiltonian. This is an algebraic equivalence, not a reconstruction of historical code conventions. |
| pp. 5–7, Secs. 5–6 | Geometric septum hit/cross classification and particle removal; 35 pi mm mrad normalized phase-space acceptance. | Explains how the scattering handoff addresses a different question and distinguishes the 20 pi mm mrad isolated RFKO acceptance. |
| pp. 9–10, Sec. 7.3 and Fig. 14 caption | Text reports full-beam geometric loss reduction to 1.2% with bumps. | Uses “reported/quoted” attribution. Does not compare this directly with, or multiply it by, the conditional 43% returned-sample loss. See source inconsistencies below. |
| p. 9, Fig. 13 | Spill display uses a 100-turn moving window. | Does not treat a plotting window as evidence for a physical monitor transfer function or feedback update period. |
| p. 11, Ref. [19] | Lists N. Mokhov, V. Nagaslaev, I. Rakhno, Mu2e Document 3697-v1 (2010). | Updates the MARS internal-report entry with this published metadata and records provenance in a source comment. The original DocDB report remains uninspected. |

## Figure comparison

All 14 numbered figures in the prior PDF were inspected against the topics and panels used in the current manuscript. No identical complete numbered figure was identified. This is a visual/content comparison, not a raw-data provenance audit.

| Current figure / assets | Relation to the prior publication |
| --- | --- |
| RFKO three-case spill comparison, `img/fig9.png` | The prior paper's Fig. 9 is a dynamic-bump phase-space comparison, not this RFKO figure. Prior Figs. 5 and 13 show feed-forward spills; the present RFKO panel contains additional feedback/ripple cases. Possible shared underlying baseline data require author confirmation. |
| Tune-step traces and transit distributions, `fig_arrival1*`, `fig_arrival2*` | The prior article has uninterrupted-ramp intensity/spill plots, but no corresponding paused/restored-ramp transit diagnostic or particle-by-particle Synergia2/RK4 comparison. |
| MARS trajectories, returned scattered sample, and reduced-model shearing, `fig_beamloss1`, `fig_beamloss2*`, `fig_beamloss3` | The prior article cites MARS geometry work but presents geometric interception and dynamic-bump loss classifications, not this returned-sample tracking sequence. |
| Fixed-tune emittance/centroid and action distributions, `fig_rfko1*`, `fig_rfko2*` | The prior article excludes RFKO tracking. These diagnostic panels address its qualitative RFKO discussion. |
| Unused `fig_bump*` assets | These belong to the dynamic-bump material already covered by the prior publication and are not introduced as new figures in the current manuscript. |

No figure was extracted from the publication for reuse in the manuscript. Existing repository images are unchanged. The author's original plotting data remain necessary to establish panel-level provenance and generate publication-resolution figures.

## Configuration differences that must be resolved from inputs

1. **Foil thickness:** prior Table 1 and Secs. 5–7 consistently specify 100 micrometres. The current scattering draft specifies 50 micrometres. Keep the current value explicitly scoped until the MARS input confirms it; changing a manuscript number cannot update a scattering simulation.
2. **Acceptance:** the prior ring model uses a 35 pi mm mrad normalized phase-space limit. The present isolated RFKO calculation uses a stated 20 pi mm mrad acceptance whose exact normalization is not yet established. The injected beam's 20 pi mm mrad 95% normalized emittance is a third, distinct quantity.
3. **Solver and lattice inheritance:** confirm which prior lattice, mesh, solver, kick count, ramp file, septum rotation, and dynamic-bump waveform were used in each current case. A shared parameter table is not evidence that these files match.
4. **Loss denominators:** the prior 1.2% quoted loss concerns the injected beam under geometric removal. The current 43% concerns a selected scattered-particle sample. The geometry, sample weights, selection, and handoff must match before constructing any total-loss estimate.
5. **Feedback observables:** distinguish a 100-turn plot window from averaging, update rate, chirp duration, monitor latency, and particle transit time. A suppression factor needs matched time windows, normalization, bandwidth, and uncertainties.

## Inconsistencies in the prior publication not propagated as new results

- The introduction/Table 2 use an approximately 0.1 mrad final angular spread, while Sec. 7.3 and the conclusion state approximately 0.25 mrad. The new manuscript does not select either number as its own benchmark.
- Table 2 labels the spill result as roughly 20% RMS, while Sec. 4 describes an approximately ±20% range about the mean. The new manuscript cites the latter as the wording of that section and does not equate peak/range and RMS measures.
- The Fig. 14(d) purple total-loss curve visually ends near 0.02, whereas its caption and adjacent text quote 0.012. The text's allocation of optimized loss components also needs checking against the plotted legend. This observation is not a digitized correction; obtain the original plot data before a quantitative reconciliation. The new manuscript attributes 1.2% as the published quoted value, without using it to normalize the present sample.
- Ref. [9] lists a different thesis institution from the independently checked Pullia metadata used in the current manuscript. The prior reference entry was not copied wholesale. The thesis title page remains the preferred check. (Checked 2026-10-01, Task 09: Université Claude Bernard – Lyon 1, 1999; the thesis is in French, and the manuscript entry now cites its title-page title.)
- The symbols for the resonance coefficient in the prior angle–action equation and the present complex equation require phase-convention care. The new algebraic relation makes the convention explicit without claiming to resolve the implementation from published notation alone.

## Validation boundary

This revision uses the supplied publication to establish scope, attribution, and configuration differences. No new Synergia2 or MARS run was performed. `REVIEW.md` records the manuscript build and remaining author/data checks.
