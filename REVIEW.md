# Manuscript review and revision record

Reviewed: 2026-09-29. Active source: `beamstudy-mod.tex`.

This is a substantive editorial and internal-consistency revision, not a rerun of the simulations. The supplied figures and reported numerical results are preserved. The manuscript is improved but still requires the author/data checks below before journal submission.

## Companion-manuscript format conversion

Completed 2026-09-29 at the author's request, using `../mu2e_modeling-submission/mu2e_modeling.tex` as the formatting reference.

- Retained the shared `cas-sc` class with `a4paper,fleqn`, numerical `natbib` citations, first-paragraph indentation, double spacing, line numbers, and CAS title/affiliation/abstract/keyword styling.
- Matched the companion's float-fraction definitions and restored its contents block (`tocdepth=10`) followed by a page break before the main text. This supersedes the earlier decision to omit the contents for this requested format conversion.
- Moved the existing 14 bibliography entries into `beamstudy-mod.bib` and selected the companion's `elsarticle-num` style. Removed the forced page break before references to match the companion's continuous end matter. Citation keys, cited sources, known dates, report identifiers, and existing provenance caveats are retained; no fresh bibliographic verification or scientific revision was performed. The paired PIMMS parts and paired internal monitor reports remain grouped under their original keys.
- Kept the corrected email field, institution spelling, PDF-author metadata, and suppression of the empty ORCID footnote. Unused packages and revision-colored text in the companion were not needed for its layout.
- Updated README dependencies and build instructions for BibTeX. This formatting pass does not complete editorial Tasks 03–10 or select a target journal.

Validation: `latexmk` with pdfLaTeX and BibTeX completed successfully from the repository root. The 16-page PDF was rendered and visually inspected, including contents, equations, both tables, all eight figures, captions, and references. All 37 labels are unique and all reference/citation keys resolve. The only final LaTeX box warning is the previously documented 117.0831 pt CAS keyword-overlay warning; the title page has no visible overflow. BibTeX reports missing-year warnings for the combined PIMMS entry (1999 and 2000 remain attached to their respective parts) and the internal monitor reports (dates remain unknown). These are retained metadata limitations, not unresolved citations.

The manuscript body from Introduction through Acknowledgments, including all equations, tables, captions, and figure declarations, is byte-identical to the pre-conversion source. All 22 image files, both reference drafts, and the companion TeX source retain their pre-edit hashes. No simulations, new results, figure edits, staging, commits, or pushes were performed. Build files, rendered pages, and the review PDF are outside the tracked source tree in `/private/tmp/mu2e-format-3l7y9cgf/`.

## Current author-directed scope and task backlog

On 2026-09-29, the author requested a task plan to improve journal submission quality using the existing figures and without new simulations. `tasks/README.md` and Tasks 02–10 now define that editorial work. The original Task 01 is preserved. Task 02 is now complete; Tasks 03–10 remain planned. The completion record below distinguishes the executed revision from the initial task-plan update.

This instruction supersedes the action requests below to repeat tracking, perform convergence studies, or obtain regenerated figures for this revision. Those entries remain a record of evidence gaps, not required new work. Address each gap using existing documentation where available; otherwise narrow the affected claim and explain the limitation. Do not invent settings, uncertainty estimates, or quantitative metrics from raster plots. Preserve figure files and panel content; improve captions and TeX layout only.

The task-plan update changes documentation only. No TeX, figures, reference drafts, or simulation results were changed, and no simulation or manuscript build was run for this documentation update. Journal-specific requirements and essential unresolved author metadata remain submission considerations even when all feasible editorial tasks are complete.

## Manuscript review and additional tasks (2026-09-29)

At the author's request, the current source was reviewed beyond the scope of Tasks 02–10. It was built to 16 pages in a temporary directory, and every page and all 14 referenced image files were inspected at native resolution. Seven new tasks (11–17) record the findings. No TeX, figure, or bibliography file was changed by this review.

Main findings requiring author input:

- **Ripple frequency (Task 11).** The dominant modulation in the middle panel of `img/fig9.png` repeats about every 1,600 turns (about 2.7 ms, of order 360 Hz), whereas the text specifies a 60 Hz sinusoid with a period of about 9,800 turns. The plot also covers only about 20,000 of the 31,795 turns. Confirm the ripple frequency, waveform, and run length.
- **Transit-time description (Task 11).** Fig. 3 shows transit times rising toward x = 0, with the longest times on the far side of the unstable-fixed-point line. This contradicts the text's "increasing times … nearer the unstable fixed point." The transit axis stops at 250 turns, against a stated 500-turn observation interval, and the tune-step traces extend about 1,000 turns past restoration.
- **Unexplained plot elements (Task 11).** The red circle and orange lines in Figs. 5(a) and 6, the loss-map markers and axes in Fig. 5(b), and the hatted centroid coordinates in Fig. 7(b) are undefined.
- **Beam parameters (Task 12).** Bρ = 29.650 T m corresponds to p = 8.889 GeV/c (8 GeV kinetic energy), not the tabulated 8.886 GeV/c, which gives 29.641 T m. For 20π mm mrad normalized 95% emittance, the expected rms geometric emittance is about 0.35π mm mrad, whereas Fig. 7(a) starts near 0.28. A normalized 20π acceptance (about 2.1π geometric) is incompatible with the rms emittance of about 2.75π reached at C_x = 1, so the acceptance or emittance convention needs confirmation.
- **Structure, literature, and prose (Tasks 13–15).** The two RFKO sections are separated by the tracking section, and the paper has no discussion section. Related work beyond the author's prior article is thin, with 5 of 14 references internal. The source contains about 30 hedging constructions that repeat the same scope limits.
- **Documentation and front matter (Tasks 16–17).** README still describes an inline `thebibliography`, contrary to the earlier statement in this file that it was updated for BibTeX. The `pimms` and `wcm` entries each merge two documents. `\floatpagepagefraction` has no effect. The running head no longer matches the title, and the contents block is unsuitable for submission.

The visual readings above are review evidence for author questions only. They are not results for the manuscript.

## Task 04 completed: theory, notation, and dimensional consistency

Completed 2026-09-29 by checking the printed algebra only. No trajectories were integrated and no figure was changed.

- **Algebra re-verified at 1,000 deterministic random points.**
  - Complex Eq. (2) → real Eq. (4): maximum residual 1.4e-14.
  - Ψ = π and ×6π scaling → Eq. (5) with ε = 6πΔν, S = −12√2π|g|: 2.3e-13.
  - Eq. (7) against central finite differences of H_K: 7.9e-10.
  - Below resonance, the linear flow is counterclockwise, confirming the text.
  - These checks confirm the displayed equations, not the historical tracking code. The relation g_aa = i g is retained from the earlier verified revision.
- **Independent variable made explicit.** The ×6π step requires Eq. (2) to use the orbital angle θ = 2πn, and the text now states this. It also gives the equivalent complex and real forms of Hamilton's equations and the relation τ = n/3 = θ/(6π). The elapsed time is written t = nT_rev = 3T_rev τ; the old symbol t_phys is dropped.
- **Symbols defined at first use:** n, θ, s, x, x', α, β, X, X' (conjugate momentum, not dX/ds), ν_x, Δν, g (units length^−1/2), Ψ, τ, and T_rev. X and X' have units of √length and I_x has units of length (for example, mm mrad). A sentence now warns that Kobayashi's ε is a tune distance, not an emittance.
- **New action–emittance paragraph:**
  - For a matched, centered beam, the rms geometric emittance equals ⟨I_x⟩.
  - The normalized emittance is larger by p/(m_p c) ≈ 9.47.
  - For a Gaussian beam, 95% of particles satisfy 2I_x ≤ 6⟨I_x⟩, which is stated as a common basis for a 95% emittance, not as the convention of Table 1.
  - Emittance about the centroid excludes coherent motion; the mean action about the reference orbit includes it.
- **New Eq. (6), label `eqn:fixedpoints`.** The unstable fixed points are (0, 4ε/3S) and (±2ε/(√3S), −2ε/3S), all at distance 4ε/(3S). The separatrix is the three straight lines X' = −2ε/(3S) and X' = 4ε/(3S) ± √3X. The stable region's linear size scales with |Δν|, since ε/S = |Δν|/(2√2|g|). Fixed-point residuals were 1.4e-14, and H_K is constant on the three lines to 1.0e-14. The Fig. 3 caption now links its "leftmost unstable fixed point" line to this equation.
- **Plot conventions explained without relabeling:**
  - Fig. 3 caption: the original "normalized x (mm)" label is kept; it would be √length for X = x/√β, and its normalization is undocumented. Transit times are in turns.
  - Fig. 5 caption: the plotted pair is √β(X, X') in mm.
  - Fig. 7 caption and text: the emittance is in the diagnostic's π mm mrad; rms versus 95% and the centroid reference are undocumented, so the comparison is qualitative.
  - Fig. 8 caption: the action units, reference, and normalization of f are undocumented.
  - The Sec. 5 action paragraph now points to Sec. 4.1 and the acceptances in Table 2.

### Evidence recorded for later tasks (not added to the manuscript)

- **Task 11:** the orange overlay lines in Figs. 5(a) and 6 match the separatrix geometry of Eq. (6), in the (x, αx+βx') coordinates, where scaling both axes by √β preserves angles.
  - The two slanted lines have slope about ±1.7, compared with ±√3.
  - They meet near (0, 8.6) mm, and the horizontal line lies near −4.3 mm, or −½ of the vertex height, as the equation requires.
  - The vertex lies on the positive-X' axis, which is consistent with ε/S > 0, that is, with Δν < 0 and the stated negative S.

  This supports, but does not confirm, the reading of these lines as the separatrix. Their caption still needs author confirmation.
- **Tasks 11 and 12:** in Fig. 7, the C_x = 0 emittance stays nearly constant while the centroid moves by millimeters. This suggests that the emittance diagnostic is computed about the centroid, but β at the observation point and the plotting units are unknown, so the question remains open.

Validation: `latexmk` with pdfLaTeX and BibTeX succeeded (17 pages, seven numbered equations). All 41 labels are unique, and every reference, equation reference, and citation resolves. The only box warning is the known CAS keyword overlay; the only BibTeX warnings are the known `pimms`/`wcm` years. Pages 7–10 and the RFKO pages were inspected; a stray empty numbered line before Eq. (5) was removed by restoring the trailing comma. All image files, both reference drafts, and the `.bib` file retain their pre-edit hashes. No simulations, staging, commits, or pushes.

## Task 03 completed: methods and configurations

Completed 2026-09-29 using the existing manuscript, the reference draft `beamstudy.tex`, the companion draft `modeling.tex`, and `PRIOR_WORK_COMPARISON.md`. No simulation was run.

- Split Sec. 2 into two subsections: "Shared parameters and published settings" (`sec:baseline`) and "Simulation cases" (`sec:cases`). The first attributes the published 100-turn sextupole turn-on, 200-turn ramp segments, and Hockney solver settings to Ref. [2] only. It states that the solver settings, lattice version, and ramp/bump reuse of the present cases are not documented.
- Rewrote the Table 1 caption. The nominal values come from the original description of the present simulations (the `beamstudy.tex` table) and match those reported in Ref. [2]. The injected-beam emittance is identified as distinct from both acceptances.
- Revised Table 2 into configuration and population differences. Rows were added for ramp/bumps and space charge (published versus not documented). The mixed "Time intervals" and "RFKO test dynamics" rows were moved to the new case table and to the text. The 50 versus 100 µm foils and the 20π versus 35π mm mrad acceptances are kept, with the acceptance normalization marked as not documented.
- Added Table 3 (`table:cases`), which defines five cases: ripple and feedback, tune step, reduced model, septum scattering, and fixed-tune RFKO. Each row gives the model, the stated configuration, the time structure, and the sample/endpoint. Its caption says that unlisted settings are undocumented and not inferred from Ref. [2].
- Added a paragraph separating the intervals of about 100 turns (published sextupole turn-on and display window, feedback accumulation, chirp sweep) from each other and from the controller update interval, which is undocumented. The same paragraph separates the 200-turn ramp segments from the 300/500-turn tune-step protocol. A redundant display-window sentence was removed from Sec. 3.
- Ripple: the text now quotes the original "±0.5% peak-to-peak" wording and states that amplitude versus peak-to-peak is not established. No value was changed.
- Tune step: from `beamstudy.tex`, the manuscript now states that transit times were recorded for particles in the narrow shell released by the step, and that the reference ramp is described as optimized. Because the selection criterion is undocumented, particles already in transit may contribute. Identity with the published ramp file is stated as undocumented.
- Fixed-tune RFKO: the chirp spectrum is described as covering the betatron tune spread, as the original states. The acceptance caveat now points to Sec. 2.1 instead of being repeated. `AUTHOR CHECK` comments were condensed.

### Case metadata status

| Case | Documented in existing records | Not documented (author input needed) |
| --- | --- | --- |
| Ripple and feedback | Synergia2 extraction with ramp; C_x = 1; linear chirp, 100-turn sweeps, random phase per sweep; 60 Hz ripple "±0.5% peak-to-peak"; about 100-turn spill accumulation; PD control with time-dependent P gain and constant D gain | Ripple amplitude convention, modulated quadrupoles and phases; gain values/schedule, derivative filter, update interval, latency, limits; spill normalization; space-charge settings; macroparticle count; visible modulation period (Task 11) |
| Tune step | 5×10^5 macroparticles; optimized ramp; pauses at 2,000/15,000/25,000 for about 300 turns; restoration then about 500-turn hold; transit times for the shell released by the step | Exact restoration values; selection criterion; per-stage particle counts; extraction criterion; identity with the published ramp file; solver settings |
| Reduced model | RK4 on Eq. (6); output every three turns; no space charge; effective sextupole strength at the restored settings (tune step) | Integration step; coefficient values and phase convention; Twiss parameters at the observation point; initial conditions for Fig. 6 |
| Septum scattering | Synergia2 ESS1 aperture (head hits and plane crossings); MARS ESS1→C-magnet with 50 µm foils; Synergia2 ring tracking of MARS output; coordinates referred back to ESS1 for display; added circulating reference particles | MARS version/physics settings; species selected; particle count and weights; coordinate transform; tracking duration; loss/extraction criteria; whether reference particles enter the 43% |
| Fixed-tune RFKO | ν_x = 9.65; resonance drive and ramp off; space charge included; C_x = 0 and 1; linear chirp with random phases, spectrum covering the tune spread; 500 W, about 1 µrad; circular 20π mm mrad aperture; 30,000 turns | Acceptance and emittance conventions; sweep period and numerical bandwidth per case; kicker calibration; seed policy; macroparticle count |

These gaps are already covered by the High and Medium rows of "Author/data checks before submission"; this table assigns them to cases. Where a detail is missing, the manuscript now narrows the claim instead of requiring a new run.

Validation: `latexmk` with pdfLaTeX and BibTeX succeeded (17 pages; previously 16, because of Table 3). All 40 labels are unique, and every `\ref`/`\eqref` target and citation resolves. The only box warning is the known 117.0831 pt CAS keyword overlay; a 7.9 pt overflow in the first draft of Table 3 was fixed by narrowing its columns. BibTeX reports only the two known missing-year warnings (`pimms`, `wcm`). All 17 pages were rendered and inspected. All 22 image files, both reference drafts, and `beamstudy-mod.bib` keep their pre-edit SHA-256 hashes. No simulations, figure edits, staging, commits, or pushes.

## Task 02 completed: contribution and narrative

Completed 2026-09-29 using the existing results and figures only.

- Revised the title, abstract, introduction, baseline/scope discussion, and conclusion. The abstract now leads with the physical question, followed by methods, observations, and bounded implications. The title uses “septum-scattered particle transport” to name the complementary transport study precisely.
- Connected RFKO feedback, chromatic mixing, and finite transit times as aspects of beam response relevant to spill regulation. Explained post-interception scattering as a complementary transport question.
- Retained attribution of feed-forward ramp, septum, and dynamic-bump optimization to the prior publication. Defined the contribution relative to that work without claiming general RFKO or resonance-model novelty.
- Consolidated recurring configuration and population limitations in the scope discussion and replaced the conclusion’s proposed matched-simulation/convergence program with a synthesis of supported findings. No new simulation is required to complete this task.
- Preserved the approximate 43% fraction as conditional on the returned scattered sample in the stated 50 micrometre geometry, separate from published full-beam geometric loss in the 100 micrometre model.

### Contribution-to-evidence check

| Narrative statement | Existing manuscript evidence | Retained boundary |
| --- | --- | --- |
| Tested feedback visibly reduces ripple-driven modulation | `fig:fig9`, existing feedback discussion | Residual spikes; no measured suppression factor or gain optimum |
| Nonzero chromaticity favors emittance growth with smaller centroid excursions | `fig:rfko1` and `fig:rfko2`, fixed-tune results | Phase-mixing interpretation; resonance drive disabled; no direct extraction metric |
| Tune-step response has long delays near unstable fixed points | `fig:arrival1`, `fig:arrival2`, reduced Hamiltonian discussion | Finite diagnostic window and model differences; no uniquely isolated space-charge cause |
| Selected septum-scattered particles undergo subsequent transport and loss | `fig:beamloss1`, `fig:beamloss2`, existing reported 43% result | Conditional sample, stated 50 micrometre foils; no total-beam loss or efficiency inference |
| Reduced resonance motion explains phase-space shearing qualitatively | `fig:beamloss3` and existing reduced-model interpretation | No material, extraction-field, or aperture-loss validation |

### Validation and remaining scope

- Compiled successfully with the existing TeX toolchain: 16 pages, eight figures, two tables, and six displayed equations.
- Checked 37 unique labels, all reference/citation keys, all 14 bibliography entries in first-citation order, and balanced named environments.
- Rendered and visually inspected all 16 pages. The only final log diagnostic is the known 117.0831 pt CAS keyword-overlay box; the title page has no visible overflow. No new manuscript-body layout warning was found. Existing image-resolution limits remain unchanged.
- Confirmed byte-identical results sections (from RFKO feedback through fixed-tune RFKO), equation/table/figure environments including captions, acknowledgments, and bibliography. All 22 img/ files and both reference drafts retain their pre-edit hashes.
- Task 02 is complete. Foil/configuration provenance, controller details, sample endpoints/weights, and plotted normalization remain unresolved author questions; Tasks 03–10 have not been executed. This is an editorial validation, not a validation of the simulations or a declaration of submission readiness.
- No new simulations, scientific figures, numerical results, staging, commits, or pushes.

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
