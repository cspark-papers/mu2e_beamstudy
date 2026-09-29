# Manuscript review and revision record

Reviewed: 2026-09-29. Active source: `beamstudy-mod.tex`.

This is a substantive editorial and internal-consistency revision, not a rerun of the simulations. The supplied figures and reported numerical results are preserved. The manuscript is improved but still requires the author/data checks below before journal submission.

## Revision based on the complete prior publication

The author subsequently supplied the published 11-page article. It has now been read in full and visually inspected. `PRIOR_WORK_COMPARISON.md` records the section/page evidence and figure comparison.

- Reframed the title, abstract, introduction, and conclusions around the follow-up topics actually left open by the prior publication: RFKO response, transit-time diagnostics, and subsequent transport of septum-scattered particles. The published work explicitly excludes RFKO from its tracking results.
- Added a baseline/scope section and a comparison table. Attributed the published solver grid, kick count, tune-ramp segmentation, and initialization correctly without silently importing them into unverified current inputs.
- Made the 100 micrometre published foil versus 50 micrometre current scattering specification explicit. Distinguished the published 35 pi mm mrad normalized acceptance from the current 20 pi mm mrad RFKO-test acceptance and from the initial emittance.
- Attributed the published open-loop spill result and quoted 1.2% geometric loss fraction. Removed the unsourced below-approximately-2% current interception statement. Neither the prior full-beam loss nor its projected factor 1.5–3 RFKO improvement is treated as a demonstrated result of the present calculations.
- Added the geometric action definition and an algebraic relation between the prior angle–action and current complex-Hamiltonian phase conventions. The figure diagnostics still require their original normalization metadata.
- Updated the MARS report authorship/year to the metadata in the publication's Ref. [19], including N. Mokhov, with provenance explicitly recorded. The original internal report has not been inspected.
- Compared all 14 prior numbered figures with current figure content. No identical complete numbered figure was identified; raw-data provenance, including any reused feed-forward baseline in the RFKO plot, remains an author check.
- Recorded inconsistent published angular-spread and spill-metric descriptions and the visual mismatch between the Fig. 14(d) total-loss curve and its quoted 1.2% caption. These were not silently resolved or propagated as new quantitative findings.

## First revision changes (retained history)

- Rewrote the title, abstract, introduction, results discussion, and conclusions around the evidence actually presented. Removed claims of new dynamic-bump optimization because this manuscript contains no corresponding results section; identified that work as context from the companion study.
- Corrected the missing cube in the complex-conjugate Hamiltonian term to `ig*(a*)^3`, restoring a real Hamiltonian and consistency with the real-coordinate expression. Defined normalized coordinates and clarified that `X'` is a momentum coordinate.
- Made `S = -12 sqrt(2) pi |g|` explicit for the stated phase `Psi = pi`. The prior expression involving the sign of tune detuning agrees only on the below-resonance branch used here. Removed the explicit sextupole sum, whose phase convention was not sufficiently defined; the resonance-driving coefficient is now introduced with its source. The implementation convention and effective coefficient remain reproducibility questions.
- Used `tau = n/3` for the continuous three-turn variable and separated it from physical time. Corrected the revolution time from approximately 1.6 to 1.69 microseconds using the tabulated momentum and circumference. Removed the claim that a short three-turn interval proves adiabaticity.
- Corrected stable/unstable fixed-point terminology. Removed the unsupported universal inverse-distance law for transit time and the unique attribution of model discrepancies to space charge. Removed claims that reduced-model phase-space shapes validate material scattering or extraction efficiency.
- Distinguished emittance growth from centroid motion. Corrected the conclusion's reversal of the role of chromaticity. The fixed-tune RFKO test has no resonance drive and cannot directly demonstrate extraction.
- Distinguished primary interception from subsequent loss of a selected scattered-particle sample. Preserved the reported approximately 43% conditional loss and the below-approximately-2% interception estimate without combining them into a total loss.
- Checked all 14 used PNG assets. Corrected the beam-fraction/spill diagnostic descriptions, the incomplete arrival-time caption, the emittance-versus-growth-rate label, the plotted phase-space coordinates, and the septum coordinate sign in the beam-loss plot (approximately -11 mm).
- Preserved all table values, replacing undefined Tp/Mp notation with explicit proton counts. The original 31.5 million protons per extracted pulse is consistent with 10^12 / 31,795; it was not a numerical error.
- Repaired the absent `sec:tune` cross-reference. Restored `HB10`, `wcm`, and `pid` bibliography entries and added a Synergia methods citation. Replaced the outdated companion-paper submission status with its published 2026 record. Recovered internal MARS/monitor references from `modeling.tex`, explicitly marking their provenance and verification status.
- Fixed the email field and institution spelling, removed the table of contents and forced page break, simplified unused packages, and retained the existing single-column, line-numbered review layout.

## Author/data checks before submission

| Priority | Issue | Evidence or decision needed |
| --- | --- | --- |
| High | Geometry and inherited baseline | Confirm the 50 micrometre scattering foil against the MARS deck; the prior model consistently uses 100 micrometres. Identify the actual lattice, ramp, bump waveform, space-charge configuration, and acceptance used in each present case. The new scope table distinguishes the stated values without claiming a matched configuration. |
| High | Quadrupole ripple amplitude | The original text says both “peak-to-peak” and “±0.5%.” The revision retains ±0.5% as an amplitude provisionally. Confirm from the input whether the modulation was 0.5% amplitude (1% peak-to-peak) or 0.5% peak-to-peak. Record which quadrupoles were modulated and their relative phases. |
| High | Controller reproducibility and performance | Provide the discrete update law, proportional-gain schedule, derivative gain/filter, averaging and update intervals, latency, amplitude limits, and initial conditions. Define spill normalization and binning. Report an RMS/ripple-spectrum or duty-factor comparison with uncertainty and the relevant spill window before making quantitative suppression or optimality claims. |
| High | Transit-time sample and tune-step definition | Confirm that restoration means the uninterrupted-ramp value at the restoration turn, the exact step sizes, the start-time convention, whether already-unstable particles are excluded, the particle count at each stage, and the extraction criterion. The draft's approximately 500-turn observation interval is preserved; test for unobserved tails. |
| High | Space-charge comparison and numerical convergence | The prior publication reports a 64×64×128 Hockney grid and 240 kicks/turn; confirm the actual settings, Synergia2 version, lattice, initial distributions and integration steps for the present cases rather than assuming inheritance. Repeat otherwise matched tracking with space charge on/off. Provide RK4 step refinement and Hamiltonian conservation checks at fixed parameters. Sampling every three turns does not specify the RK4 integration step. |
| High | Scattering handoff and 43% denominator | Document MARS version/physics settings, species selected for return tracking, number and statistical weights of particles, coordinate/reference-orbit and momentum transforms, apertures, tracking duration, and extraction/loss criteria. Confirm whether the extra circulating reference particles enter the reported percentage. Do not interpret 43% as total ring loss or a radiation-dose prediction. |
| High | Emittance, action, and aperture conventions | Define geometric versus normalized emittance, rms versus 95% values, whether the diagnostic subtracts the centroid, the definition/units of `I_x`, and the normalization of `f(sqrt(I_x))`. Specify exactly how the 20 pi mm mrad acceptance is applied. The plotted values alone cannot establish these conventions. |
| High | Figure axis units | The transit-time figures say “normalized x (mm)” whereas `X=x/sqrt(beta)` has square-root-length units when beta and x use consistent length units. Recover the plotting transformation before relabeling. The loss plots use `(x, alpha x + beta x')` in mm and are not the canonical `(X,X')` pair; their captions now distinguish this. Also supply loss-map axis units/legend and MARS geometry axis units. |
| Medium | RFKO excitation settings | Provide the center-frequency/sideband convention, numerical chirp bandwidth at each chromaticity (especially Cx=0), random-phase distribution, seed policy, and kick calibration connecting 500 W with approximately 1 microradian. |
| Medium | Momentum spread | Clarify whether 0.0016 is rms, a half width, or another measure. It has not been silently relabeled rms. |
| Medium | Reduced-model coefficient | Recover the lattice-to-resonance coefficient and phase convention, observation-point Twiss parameters, and values of effective sextupole strength and tune detuning for each comparison. The algebraic correction does not prove the original numerical implementation used the same convention. |
| Medium | Internal citations and source attribution | MARS Document 3697-v1 metadata now follows the supplied publication’s Ref. [19]: N. Mokhov, V. Nagaslaev, I. Rakhno (2010). Verify the original report and confirm it is the actual calculation used. Monitor Documents 3627-v4 and 3625-v1 remain locally recovered references. Check the Pullia thesis title/institution against its title page; the prior article’s bibliography conflicts with the separately checked institution. |
| Medium | Novelty and relationship to prior publication | The complete prior article was inspected and explicitly excludes RFKO tracking. The distinct current figure topics and any possible underlying-data overlap are recorded in PRIOR_WORK_COMPARISON.md. Confirm raw-data provenance and inheritance of the optimized baseline; no claim of novelty over the wider RFKO literature is made. |
| Medium | Journal package and author declarations | Choose the target journal and check its current template, abstract length, figure-resolution requirements, data-availability statement, author contributions, competing-interest declaration, and any applicable disclosure policy. Author declarations and data-sharing commitments were not invented. |

## Sources consulted

Public bibliography/theory checks used primary publications or institutional records. The local manuscript remains the source for its own simulation results.

- Michelotti and Johnstone, [FERMILAB-FN-0842-APC-CD](https://lss.fnal.gov/archive/test-fn/0000/fermilab-fn-0842-apc-cd.pdf), especially the complex Hamiltonian and coordinate convention. The published expression includes `(a*)^3`.
- Park, [published companion paper](https://www.sciencedirect.com/science/article/pii/S1738573325006655), Nuclear Engineering and Technology 58 (2026), 104097; [DOI](https://doi.org/10.1016/j.net.2025.104097). Complete 11-page author-supplied PDF read and visually inspected in the second revision; see PRIOR_WORK_COMPARISON.md for scope and comparison limits.
- Nagaslaev et al., [IPAC2011 THPS058](https://epaper.kek.jp/IPAC2011/papers/thps058.pdf), pp. 3559–3561, for RFKO center frequency, bandwidth, and coherent/incoherent distinction.
- Nagaslaev et al., [FERMILAB-CONF-10-395-AD](https://lss.fnal.gov/archive/2010/conf/fermilab-conf-10-395-ad.pdf), for the missing HB2010 citation.
- Himel, [SLAC-PUB-7398](https://www.slac.stanford.edu/pubs/slacpubs/7250/slac-pub-7398.pdf), for the missing feedback reference.
- Mokhov, [FERMILAB-CONF-10-518-APC](https://lss.fnal.gov/archive/2010/conf/fermilab-conf-10-518-apc.pdf), for MARS report metadata.
- Amundson et al., [Synergia methods paper](https://www.sciencedirect.com/science/article/abs/pii/S0021999105002718), Journal of Computational Physics 211 (2006), 229–248.
- [Mu2e Technical Design Report](https://arxiv.org/abs/1501.05241), for report identity.
- PIMMS [Part I](https://cds.cern.ch/record/2858081/files/CERN-PS-99-010-DI.pdf) and [Part II](https://cds.cern.ch/record/2858080/files/CERN-PS-2000-007-DR.pdf), for report identities.
- Pullia's [institutional CV](https://www.iusspavia.it/sites/default/files/2024-06/CV%20M.Pullia.pdf) confirms the 1999 Lyon 1 doctorate; the expanded title is also cited in [Phys. Rev. Accel. Beams 26, 014402](https://journals.aps.org/prab/abstract/10.1103/PhysRevAccelBeams.26.014402). The thesis full text was not independently checked.
- `modeling.tex`, bibliography entries `mars`, `wcm`, `HB10`, and `pid`, for recovered local citation provenance.

## First-revision validation (retained history)

- Compiled successfully using installed TeX Live 2026, `latexmk` 4.87 and `cas-sc` 2.4, with 14 PDF pages. The manuscript depends on external figure files and the journal class, so validation used the complete local project rather than a standalone-document compiler.
- Checked all 34 source labels and 14 bibliography entries: no missing reference/citation keys or duplicate labels; bibliography ordered by first citation. Checked balanced named environments and absence of unexpected control characters.
- Independently evaluated the complex-to-real Hamiltonian conversion and the phase/scaling relation at 1,000 deterministic test points. Maximum conversion residual was approximately 1.1e-14. Central finite differences of the Hamiltonian agreed with both printed equations of motion within the stated numerical tolerance. This checks the displayed algebra, not the historical tracking implementation.
- Calculated a revolution time of 1.694812 microseconds from the stated momentum and circumference; 100 turns correspond to 0.169481 milliseconds. The mean population per extracted pulse is 3.14515e7, consistent with the retained rounded value.
- Rendered and visually inspected all 14 pages, including equations, tables, all figures, captions, bibliography, and page counts. Fixed CAS figure-placement syntax, enlarged the three transit-time panels, suppressed an empty ORCID field, and ensured all floats are included in the page count.
- The installed CAS class emits one 117.0831 pt overfull-box diagnostic from its intentionally zero-width keyword overlay in `Abstract`. The title-page rendering was inspected and is contained within the page; no manuscript-body overfull boxes, unresolved references, or other final-build warnings remain. No class file was modified.
- Existing raster figures remain the limiting factor for publication resolution. In particular, the MARS image is only 475 by 419 pixels; obtain a vector or higher-resolution original for submission. No scientific figure was reconstructed from inferred data.
- No new Synergia2 or MARS simulations were run. No files were staged, committed, or pushed.

## Second-revision validation

- Compiled the revised source successfully with the installed journal class and external figures; the resulting PDF has 16 pages, eight figures, two tables, and six displayed equations.
- Checked 37 unique labels and 14 bibliography entries, with no undefined citation/reference keys, no duplicate labels, ordered citations, and balanced named environments.
- Independently checked the added action definition and `g_aa = i g` coefficient conversion at 1,000 deterministic numerical test points. Maximum Hamiltonian difference was approximately 8.9e-15; this verifies the displayed relation, not historical tracking conventions.
- Rendered and inspected the revised PDF, including the new comparison table, title/abstract, equations, existing figures, and bibliography. The only final log diagnostic is the previously documented 117.0831 pt CAS keyword-overlay box; it causes no visible overflow. Table spacing warnings were fixed with ragged-right cells.
- Preserved all figure files, `AGENTS.md`, and both reference TeX drafts. No new beam simulations were run, and no files were staged, committed, or pushed.
