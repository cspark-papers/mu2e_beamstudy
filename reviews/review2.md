# Referee assessment of `beamstudy-mod.tex`

Date: 2026-10-01. Revision reviewed: commit `fa56911` (after Tasks 02–26).

**Short answer:** it isn't ready to submit yet. As it stands, I'd expect **major revision or rejection** at a top accelerator journal, and **a realistic chance after revision** at an applied venue like the one that published the companion paper. The writing is now sound; the obstacles are the evidence and the figures, and editing can't fix those.

## Strengths

- **Clear, honest scope.** Every claim now matches what the figures show, and the 43% loss is properly qualified. The mechanisms are explained correctly: chromatic decoherence, slow passage near fixed points, shearing of the scattered line.
- **Sound theory.** The reduced-model section checks out algebraically; the conventions, fixed points and units are all verified.
- **Good positioning.** It ties directly to an open Mu2e design question: RFKO versus PID regulation on the quadrupoles (Narayanan, NAPAC'25).
- **The scattering study is the most original part.** Following particles past the point where they hit the septum, through MARS and back around the ring, isn't routinely done.

## Major concerns a referee will raise

1. **Everything is qualitative.** There is no number for how much feedback suppresses the ripple, no spill spectrum or duty factor, no uncertainties and no convergence study. Appendix A lists about 40 settings the records don't specify. A referee for PRAB or NIM A will ask how anyone could reproduce or judge these results, and "not documented" isn't an answer they'll accept.
2. **An unresolved internal inconsistency.** The text says the ripple is 60 Hz, but the plotted spill repeats at about 360 Hz. Two more numbers don't fit together: the starting emittance (0.28 plotted vs 0.35π mm mrad expected), and the acceptance (an rms emittance of 2.75π can't fit inside a 20π normalized acceptance). A careful referee will find these within minutes. **They must be resolved from the original files before submission.**
3. **The figures don't meet publication standards.** They print at 118–261 dpi (Elsevier requires 1000 dpi for line art), labels print at about 3.5 pt, and the MARS figure is 475×419 pixels. The orange lines, red circle and loss-map markers are unexplained, and several axes have undocumented units. Referees and production editors will both object.
4. **Limited novelty in two of the four results.** The chromaticity result essentially repeats the author's own IPAC'11 finding. Slow passage near fixed points is a known effect from Pullia's analysis. What's new is the Mu2e-specific context and the scattering transport, which is a thin novelty argument for a full article.
5. **The simulations are old.** They date from around 2010–2013, before Mu2e commissioning. A referee may ask why there's no comparison with the current spill-regulation design or with commissioning data.
6. **Overlap with the NET 2026 paper.** Same author, same machine model, overlapping period. The editor will want a clear statement that the simulations and figures are distinct; the cover letter must address this.

## Minor concerns

- **Defensive tone.** It's much improved, but the paper still reads defensively in places: 16 "not documented" remain in the main text.
- **Length.** 25 pages in review layout is long for the amount of quantitative content; a shorter paper may fare better.
- **Missing pieces:** the declarations (including AI use), data availability, and the internal-report references.

## Likelihood of acceptance (my judgement, not a prediction)

| Venue type | As is | After the fixes below |
|---|---|---|
| PRAB | Low; likely rejected for lack of quantitative evidence | Possible only with quantitative analysis |
| NIM A | Major revision at best | Moderate |
| NET (the companion paper's journal) or a similar applied journal | Major revision | Reasonable |
| Conference proceedings (IPAC/NAPAC) | Acceptable after shortening | Good |

## What would most improve the odds, using no new simulations

1. **Resolve the ripple frequency, the emittance and acceptance conventions, and the 43% denominator** from the original input files and logs.
2. **Regenerate the figures from the original plot data** at full resolution, with proper labels, legends and units. Redrawing from existing data is not a new simulation.
3. **Pull quantitative numbers from that same original data:** rms spill fluctuation or duty factor with and without feedback, the ripple spectrum, transit-time percentiles, and the particle count and weights behind the 43%. Even one or two solid numbers would change how a referee reads the paper.
4. **Pick the venue deliberately.** NET or a similar applied journal fits best. For PRAB or NIM A, consider a shorter paper centred on the scattering result.
5. **Cover letter:** state the distinction from the NET 2026 paper plainly.

**Bottom line:** the manuscript is well written and honest, but it is evidence-limited. Without access to the original simulation records, the realistic options are a shorter applied-journal or proceedings paper. If those records can be recovered, a solid applied-journal article is achievable.
