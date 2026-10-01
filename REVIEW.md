# Manuscript review and revision record

Reviewed: 2026-09-29. Active source: `beamstudy-mod.tex`.

This is a substantive editorial and internal-consistency revision, not a rerun of the simulations. The supplied figures and reported numerical results are preserved. The manuscript is improved but still requires the author/data checks below before journal submission.

## Current status (2026-10-01, after Task 27)

This section is the current summary. The sections below are a chronological record, newest first after this section. Earlier status statements in them, such as the 2026-09-29 backlog section and the Task 10 readiness report, are historical and are kept as evidence.

- **Backlog:** Tasks 02–21 are complete. Tasks 18–21 came from the updated-manuscript review dated 2026-09-30.
- **Task 27 (2026-10-01):** the archived simulation records were found in local cluster backups and incorporated (see "Task 27 completed" below). Task 28 (2026-10-01) resolved all five numerical inconsistencies from the records; the 43% denominator, the simulation momentum, and the missing fixed-tune and feedback runs are now the leading author questions.
- **Open backlog (recorded 2026-10-01):** Tasks 27–34 from `reviews/review1.md` and `reviews/review2.md`: record recovery (27), numerical inconsistencies (28), publication-standard figures and quantitative metrics (29–30, blocked pending author authorization because they change the editorial boundaries), venue and scope (31), submission package (32), consolidation (33), and review-file hygiene (34). See `tasks/README.md`.
- **Follow-up backlog (recorded 2026-10-01):** Tasks 22–26 from two further reviews, all completed on 2026-10-01 of revision `9b299a3`. They are editorial corrections only (setup wording, readability, attribution and scope slips, a provenance table, small layout and bibliography fixes); see `tasks/README.md`. The current status above describes the manuscript before those edits.
- **Manuscript:** `beamstudy-mod.tex`, 27 pages in the review layout (contents on page 1) and 26 in the submission build (`\SubmissionBuild`, no contents), after Task 27. The bibliography has 24 cited entries and 0 BibTeX warnings. The only LaTeX diagnostic is the known CAS keyword-overlay box. There are 46 unique labels, all resolved.
- **Figures and drafts:** all 22 image files are unchanged since the first commit, and the reference drafts are unchanged since `c037b4e`.

### Current claim–evidence map (supersedes the Task 10 table)

| Claim | Evidence | Status after Tasks 18–20 |
| --- | --- | --- |
| Emittance growth with nonzero chromaticity; mainly coherent centroid motion at zero chromaticity | Figs. 1–2, Sec. 4.1 | Observation retained. Chromatic mixing is presented as consistent with it, with the mechanism credited to earlier simulations [ipac11]. A possible difference in the bandwidths of the plotted runs is not excluded (those runs were not located); Task 27 recovered the centroid-referenced action and emittance definitions (Task 18, Task 27). |
| PD RFKO feedback reduces visible ripple-driven modulation, with residual spikes | Fig. 3, Sec. 4.2 | Observation retained. The delay mechanism is a plausible interpretation carried across from the separate tune-step case, not a measured loop delay or demonstrated cause (Task 19). |
| Transit times range from a few to more than one hundred turns and increase with the starting distance from the septum; the longest displayed times are longer at later stages | Figs. 4–5, Sec. 5 | Observation retained. Branch membership, fixed-point passage, and the discrete-level origin (sampling or physics) are labeled as interpretations or left unresolved, and the stage dependence is scoped to the displayed, truncated diagnostic (Task 19). |
| ~43% of the returned scattered-particle sample (50 µm foils) is reported lost in ring tracking | Fig. 7, Sec. 6 | Conditional fraction retained. Task 27: the archived accounting divides by the 2,402-particle tracked subset of 127,975 returned particles; author confirmation pending before the abstract and highlights are changed. The C-magnet-to-ESS1 map is linear but its derivation is not recorded; the tracking duration is not recorded (Tasks 20, 27). |
| Chromatic mixing and transit time as links in the RFKO response chain | §7.1 | Now "plausible successive links", not a demonstrated causal chain. |

### Readiness

The manuscript is editorially complete and **not yet submission-ready**. The author actions in the Task 10 "Readiness report" still apply, together with the questions added by Tasks 18–20 to the author-check table:
- the 43% denominator (2,402 tracked versus 127,975 returned; Task 27);
- the momentum reported in Table 1 (simulations used 8.827 GeV/c; Task 27);
- the plotted fixed-tune and feedback runs, which were not among the recovered records (Task 27);
- figure resolution and lettering below Elsevier's artwork rules, which cannot be fixed from the archive; recorded as a submission blocker (Task 29);
- whether the RFKO loop delay was measured;
- later-turn encounter records of the scattered sample.
The action reference, chirp bandwidth of the related runs, RK4 step and cadence, and mapping type were recovered in Task 27.

## Companion-manuscript format conversion

Completed 2026-09-29 at the author's request, using `../mu2e_modeling-submission/mu2e_modeling.tex` as the formatting reference.

- Retained the shared `cas-sc` class with `a4paper,fleqn`, numerical `natbib` citations, first-paragraph indentation, double spacing, line numbers, and CAS title/affiliation/abstract/keyword styling.
- Matched the companion's float-fraction definitions and restored its contents block (`tocdepth=10`) followed by a page break before the main text. This supersedes the earlier decision to omit the contents for this requested format conversion.
- Moved the existing 14 bibliography entries into `beamstudy-mod.bib` and selected the companion's `elsarticle-num` style. Removed the forced page break before references to match the companion's continuous end matter. Citation keys, cited sources, known dates, report identifiers, and existing provenance caveats are retained; no fresh bibliographic verification or scientific revision was performed. The paired PIMMS parts and paired internal monitor reports remain grouped under their original keys.
- Kept the corrected email field, institution spelling, PDF-author metadata, and suppression of the empty ORCID footnote. Unused packages and revision-colored text in the companion were not needed for its layout.
- Updated README dependencies and build instructions for BibTeX. This formatting pass does not complete editorial Tasks 03–10 or select a target journal.

Validation: `latexmk` with pdfLaTeX and BibTeX completed successfully from the repository root. The 16-page PDF was rendered and visually inspected, including contents, equations, both tables, all eight figures, captions, and references. All 37 labels are unique and all reference/citation keys resolve. The only final LaTeX box warning is the previously documented 117.0831 pt CAS keyword-overlay warning; the title page has no visible overflow. BibTeX reports missing-year warnings for the combined PIMMS entry (1999 and 2000 remain attached to their respective parts) and the internal monitor reports (dates remain unknown). These are retained metadata limitations, not unresolved citations.

The manuscript body from Introduction through Acknowledgments, including all equations, tables, captions, and figure declarations, is byte-identical to the pre-conversion source. All 22 image files, both reference drafts, and the companion TeX source retain their pre-edit hashes. No simulations, new results, figure edits, staging, commits, or pushes were performed. Build files, rendered pages, and the review PDF are outside the tracked source tree in `/private/tmp/mu2e-format-3l7y9cgf/`.

## Author-directed scope and task backlog (historical, 2026-09-29)

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

## Task 29: figures recorded as a submission blocker (no figure change)

2026-10-01. Asked whether to authorize figure regeneration, the author chose to record the figures as a submission blocker; **no authorization was given**, and no figure, caption, or TeX line changed. A read-only check of the Task 27 archive shows that original plotting data survive at most for Fig. 4 (`arrival_time.*` logs and `kicked*.dat`, read by `mu2e_arrival_time-05.py`). Figs. 1–3 and 7 lack their run data, Fig. 6 is a MARS image without data, and Figs. 5 and 8 would also require re-running RK4 integrations, which the project rules exclude. All 14 assets therefore stay at 118–261 dpi with lettering of about 3.5–8 pt, below Elsevier's artwork requirements (1000 dpi line art, 7 pt lettering; Task 16 record). **Readiness impact:** this is a production blocker for an Elsevier journal unless the editor accepts the supplied figures, the missing data are recovered, or the author authorizes a scope change. Task 31 should weigh it in the venue choice.

## Task 28 completed: internal numerical inconsistencies

Completed 2026-10-01. Every item is resolved from a recorded source (Task 27 archive); none relies on reading values from raster images. The figures are unchanged.

| Item | Resolution | Source |
| --- | --- | --- |
| 1. Ripple frequency (60 vs ~360 Hz) | Resolved in Task 27 text. The 60 Hz is the line frequency; every archived ripple routine (2013 `tune.*`, 2014 profile snapshot, 2015 run modules) builds a three-phase full-wave-rectified waveform whose fundamental is 6 × 60 = 360 Hz (1/(360 Hz × 1.6949 µs) = 1,639 turns), consistent with the ~1,650-turn period of Fig. 3. No archived routine uses another frequency. **No longer a submission blocker**; the remaining gap is the amplitude A of the plotted runs (Appendix A) | `ramp_modules.py`, f0 = 60, Σ\|sin(2πf0t + 2πi/3)\| |
| 2. Initial emittance 0.28 vs 0.35 | Resolved in Task 27 text: the archived fixed-tune runs use 16π mm mrad; the driver gives ε_rms = 16/(5.991 × 9.408) = 0.2839 mm mrad (logged 0.28344); 20π would give 0.355. Task 28 adds the 16π note to the Table 1 caption. The extraction and tune-step runs (15 run directories) use 20π | `alloptions` `norm_emit`; `mu2e.py` line 1018 |
| 3. Acceptance vs 2.75 | Resolved in Task 27 text: geometric Courant–Snyder limit of 20 mm mrad (J ≤ 10 mm mrad); no contradiction | Synergia2 `aperture_operation.tcc` |
| 4. Normalized transit coordinate | Resolved in Task 27 text: X = x/√β (mm/√m), wire at −10 mm, β = 8.67–8.81 m at the restoration turns → −3.37 to −3.40; the −11 mm of Fig. 7(a) belongs to the separate ring-tracking run | `alloptions` `wire_x`; Twiss table; `test_particle.sh` |
| 5. Momentum spread | Resolved: Δp/p = 0.0016265 is the **rms** of the matched Gaussian beam, σ_δ = σ_z/β_z with σ_z = 11.92 m (40 ns rms) and β_z = 7,331.5 m, printed identically in all 11 archived logs that report it; all 19 checked runs have `bunchlen=40.0`. Table 1 row relabeled "(rms)" with a caption note; §4.1 now states the rms chromatic spread C_x σ_δ ≈ 0.0016 for C_x = 1 | `mu2e.py` lines 1392–1424; `synergia.out` |

Consistency check of the Task 27 statements: emittance conversion (βγ = 9.408 at 8.827 GeV/c), kicker kick (1.12 µrad), 360 Hz period (1,639 turns), X_w values, and |g| units (m^{−1/2}; with Δν = −0.0109 and |g| = 2.585 the separatrix half-size h = 2ε/(3S) ≈ 1.0 × 10⁻³ m^{1/2}, a vertex near 6 mm at β = 8.8 m, which is plausible) were recomputed and agree. No `AUTHOR CHECK` or Appendix A entry belonged only to these items, so none was removed; six `AUTHOR CHECK`s remain (momentum choice, MARS foil, missing fixed-tune runs, ripple amplitude, Fig. 3 run length, 43% denominator).

Validation: review build 27 pages, submission build 26; only the known keyword-box warning; BibTeX 0 warnings; 50 unique labels, all references resolved; Table 1 page rendered and inspected. `img/*`, drafts, bib, and highlights unchanged.

## Task 27 completed: simulation records recovered

Completed 2026-10-01. The search was read-only. No simulation, tracking, or figure generation was run; no archived file was modified. The records were read, and existing archived outputs were opened only to establish provenance (which run or script produced a figure).

### Where the records are

| Archive (local) | Content | Relevance |
| --- | --- | --- |
| `~/backups/TeVCluster_Backup-Nov2020/data/results/mu2e/tune_ramp/` (also in the Dec 2018 backup) | Run directories with `alloptions`, `command`, `synergia.out`, per-run `ramp_modules.py`; analysis and plotting scripts; `img/` | Fixed-tune (`growth.00`–`07`, `agrowth.04`–`05`), tune-step (`arrival_time.00`–`19`), extraction (`beamstudy.00`–`05`) runs; plotting scripts for Figs. 1, 2, 6, 7, 8 |
| `~/backups/TeVCluster_Backup-Nov2020/home/work/mu2e-simulations/` (git, last commit 2014-10-08) | Synergia2 driver `mu2e.py` (2015-01-06), `ramp_modules.py`, lattice | Emittance, aperture, RFKO conventions |
| `~/backups/TeVCluster_Backup-Nov2020/home/work/mu2e_resume/` | `test_particle.py/.sh`, `CircBeamCM*.dat` (MARS output), `test_particle.lat` | Septum-scattering ring tracking |
| `~/backups/TeVCluster_Backup-Nov2020/home/work/paper/mu2e/` (2013–2014 draft of Ref. [mu2e]) | `mu2e.tex`, `img/fig10.png` | Fig. 3 origin |
| `~/backups/tune_ramp/` (2013 runs `run.*`, `tune.*`, `tdr.*`, `bump.*`) | Feedback runs with gains | Controller history |
| `~/Work/projects/mu2e/mu2e-simulations-profile/` (git, 2014-04-11) | Profile-optimization driver snapshot | Ripple and controller code |
| `~/backups/TeVCluster_Backup-Nov2020/data/synergia2-devel/` | Synergia2 source of that period | Phase-space aperture definition |

### Figure provenance (byte comparison with SHA-256)

- `img/fig_rfko1a.png`, `fig_rfko1b.png`, `fig_rfko2a.png`, `fig_rfko2b.png` (2015-01-30) and `img/fig_beamloss2b.png` (2015-01-24) are byte-identical to files in `.../tune_ramp/img/`.
- `img/fig9.png` is byte-identical to `img/fig10.png` of the 2014 draft of Ref. [mu2e] (caption there: "Normalized spill rates in the presence of power supply ripples").
- The other figures were matched by script: `mu2e_transit_time2.py` produces the Fig. 5 layout (axis label "normalized x (mm)", axes [−4, 0] × [0, 250]); `mu2e_mars_phasespace_multi.py` produces Fig. 7(a) (axes ±60 mm, septum at −11 mm, 17.7 mm circle); Fig. 8 starts from the same MARS sample as Fig. 7(a) (identical outliers) and matches a variant of `mu2e_mars_tracking.py`.

### Item-by-item status (Task 27 table)

| Item | Status | Record and value |
| --- | --- | --- |
| Lattice version | Recovered | MAD8 `Debunch_modified_rf.lat` (J. Johnstone, 2008, modified), identical in all 2014–15 runs |
| Input-deck momentum | Recovered | 8.827385 GeV/c (KE 7.93884 GeV; `momentum :=` in the lattice; printed in every `synergia.out`). Differs from Table 1 (8.889). Manuscript now states it; Table 1 values kept pending the author's choice (AUTHOR CHECK) |
| Space-charge solver | Recovered | `spacecharge=2d` (two-dimensional open Hockney), grid 64×64×128, 240 steps/turn, map order 2, in fixed-tune and tune-step runs; `arrival_time.19` has none; MARS ring tracking `sc=0`. §2.2 "three-dimensional space charge" was therefore removed |
| Space charge in the feedback runs | Not found | Fig. 3 runs not located |
| Ripple frequency and waveform | Recovered (code) | All ripple code (2013 `tune.*`, 2014 profile snapshot): f0 = 60 Hz, r(t) = Σ_{i=0..2} |sin(2π f0 t + 2πi/3)|, then (r − 1.91133)/(1.91133 − √3); applied as k1 → k1(1 + A r) to the `tqf` tune quadrupoles only. Fundamental 6f0 = 360 Hz = 1,639 turns at T_rev = 1.6949 µs, matching the ~1,650-turn period in Fig. 3 (Task 11). Peak-to-peak 1.49A |
| Ripple amplitude A | Not found | Every one of 640 archived ramp modules has `A = 0.000`; `mu2e_quad_ripples_simple.py` (a standalone waveform plot) uses A = 0.005 but is not a run record |
| Controller law | Recovered (code) | Per-turn update; e_p = (S_ref − S_100)/S_ref with S_100 the 100-turn average; e_d from Kaiser-smoothed (window 11) 100-turn spill; G = g_p e_p (only when e_p > 0) + g_i e_i + g_d e_d, clipped at 0; feedback from turn 500; adaptive g_p ×/÷ (1 + m·cdsp) when the mean-square same-sign error exceeds 0.010; kick = G × precomputed chirp |
| Controller gains | Partly | 2013 feedback runs without ripple (`tune.01`–`05`): g_p = 0.5 (adaptive, m = 0.30), g_i = 0, g_d = 30; `tune.00`: g_p = 0.3, g_d = 4; `quad.00`: g_p = 0.3, g_d = 25. Values for Fig. 3 not recorded |
| Spill normalization; why Fig. 3 ends near 20,000 | Not found | — |
| Fixed-tune emittance definition | Recovered | `mu2e_emittance_growth_rate.py` (2015-01-29): rms geometric about the centroid, 1e6·√(Σ… ) → mm mrad, no π |
| Action diagnostic | Recovered | `mu2e_distribution_actions1.py` (2015-01-29): centroid subtracted; Courant–Snyder action at the ESS1 entrance with the last row of the Twiss table (Python index −1; β ≈ 8.67 m, a minor inconsistency recorded here only); 300 bins of √I up to √(A/2); plotted count/√I[m^{1/2}] (explains the 10^7 scale) |
| Centroid plot | Recovered | `mu2e_distribution_actions5.py`: means of x and αx + βx′; the latter is in mm although labeled mrad |
| Acceptance convention | Recovered | Driver passes `aperture_emittance` unconverted; Synergia2 `Phasespace_aperture_operation` removes a particle when (x² + (αx + βx′)²)/β > A·10⁻⁶. So 20 means a geometric CS invariant 20 mm mrad (J ≤ 10). The 35 of the extraction runs is also geometric |
| Fixed-tune runs | Partly | `growth.04`–`07` (2015-01-29; C_x = 0, 1; linear chirp; 0.5 kW; septum moved to −10 cm; sextupole ramp commented out; `fe = 0`; gain = 1): Δν = 0.01 (5.90 kHz) at both C_x; centre 0.65 f_rev = 383.5 kHz; 10⁵ macroparticles; norm_emit 16π → 0.2834 mm mrad rms. These end at turn 20,000 with C_x = 1 emittance 2.22, whereas the plotted curve is ~2.45 there and runs to 30,000, so the plotted runs were **not** located |
| Kicker calibration | Recovered | k0 = √(8·50 Ω·P)/g · L/(βc p/e) with P = 500 W, g = 6.35 cm, L = 1.4 m → 7.04 kV/m, 1.12 µrad at 8.827 GeV/c |
| Emittance 0.28 vs 0.35 (Task 28 item 2) | Resolved | Driver: ε_rms = ε_95,n / (5.991 βγ); with 16π: 0.283; with 20π: 0.354 |
| Acceptance vs 2.75 (Task 28 item 3) | Resolved | Geometric 20 mm mrad CS invariant, J ≤ 10 mm mrad; no contradiction with an rms emittance of 2.75 |
| Normalized transit coordinate (Task 28 item 4) | Resolved | X = x/√β ×10³ at the ESS1 entrance; tune-step runs have the wire at −10 mm and β = 8.67–8.81 m → X_w = −3.37 to −3.40. The −11 mm of Fig. 7(a) is the separate ring-tracking run (`test_particle.sh`, w0 = −0.0110). The inferred β ≈ 10.5 m is not needed |
| Tune-step protocol | Recovered | `arrival_time.06` (5×10⁵, 2D SC, bumps off, wire −10 mm, 2,000 turns) resumed in `.07`/`.08`; step variants freeze k1 after `stop1` (2,000, 15,000, 25,000) and set it once at `stop2 = stop1 + 319`; no later update (held to the end of the run). Resonance parameters tabulated at 2,320, 15,320, 25,320 |
| Selection and arrival criteria | Recovered | `mu2e_transit_time2.py`: exclude particles in the field region at t0; select extracted particles with 0 < t_e − t0 < 180 and (t_e − t0) mod 3 = 1; transit time t_e − t0. So the Synergia2 times are truncated at 180 turns by construction |
| Per-stage particle counts | Not extracted | Would require reading run outputs; not needed for the text |
| RK4 step and cadence | Recovered | matplotlib `rk4`, unit step in τ (three turns), ≤ 100 steps; crossing X < x_w/√β; time = 3 × step |
| Resonance coefficients | Recovered | e.g. turn 2,320: Δν = −0.0109364, |g| = 2.58512, lattice phase 0.30107 rad; turn 25,320: Δν = −0.0028860, |g| = 2.52299. The RK4 uses |g| with the Ψ = π orientation; the lattice phase (0.29–0.31 rad) is not used — an author question whether the orientation matches the Synergia2 frame at ESS1 |
| Twiss at ESS1 | Recovered | α = −1.28234 → −1.25845, β = 8.91279 → 8.67245 m over the ramp |
| Returned sample | Recovered | `CircBeamCM.dat`: 127,975 rows; x, x′, y, y′, energy column 7.950–8.000 GeV (median 8.000); no weight or species column |
| 43% denominator | Recovered (scripts) | `test_particle.py` keeps rows with transformed x > 0 → 2,402 particles; `mu2e_mars_losses.py` hard-codes `macro_particles = 2402  #127975` and divides deposits and Lambertson counts by it. dp/p set to 0 in tracking. The tracking run output (`tune_ramp/mars`) is not in the backups |
| Tracking duration; reference particles in count | Not found | `test_particle.sh`: num_turns 1000, max_turns 6 per submission (resumable); final turn count not recorded |
| C-magnet → ESS1 mapping | Partly | Plot scripts apply tmap = [[−1.10595, −8.26894], [−0.03679, −1.17930]] (det = 1.0000) to `CircBeamCM_transformed.dat`; the script that made the transformed file was not located |
| Overlays in Figs. 7(a), 8 | Recovered | Orange: separatrix lines from `separatrix_piece-wise_linear.txt`; red: 35 mm mrad acceptance, radius √(35·8.91277) = 17.7 mm |
| Loss-map markers | Recovered | `mu2e_mars_losses.py`: black > 10%, red 1–10%, orange 0–1% of 2,402; stars = septa and Lambertson; axes in metres from the lattice geometry |
| 50 µm foils | Partly | Synergia2 wire width 50 µm in all 2014–15 runs and in the ring tracking; MARS input not located |
| MARS version | Not found | — |

### Manuscript changes

- Table 1 caption: the simulation momentum, 8.827 GeV/c, is stated; tabulated values unchanged (AUTHOR CHECK).
- §2.1: lattice file, solver, grid, steps, map order, and the bumps-off tune-step ramp stated; §2.2 no longer claims 3D space charge.
- Tables 2–3 and §2.4: recovered acceptance convention, solver, tune-step protocol, tracked-sample sizes.
- §4.1 and Figs. 1–2: aperture as a geometric CS limit; kicker calibration (1.1 µrad); archived related runs and their settings, explicitly not the plotted runs; emittance and action definitions (centroid-referenced); 0.28 explained by 16π; the hatted-coordinate unit.
- §4.2: ripple routine and 360 Hz fundamental; controller structure; A and gains of Fig. 3 stated as not recorded.
- §5 and Fig. 6: selection, arrival, RK4 step, resonance parameters, coordinate normalization, 320-turn pause, hold to run end, 180-turn truncation; discrete levels explained by procedure.
- §6 and Figs. 7–8: sample sizes, tracked subset, tracking settings, denominator, mapping, overlays, loss markers.
- §2.4, §7.4, conclusions: wording aligned ("tracked part of the returned sample"); the abstract and highlights still say "returned scattered-particle sample" pending the author's confirmation of the denominator.
- Appendix A reduced to the remaining gaps.
- AUTHOR CHECKs: the old ones on momentum, foil/acceptance/settings, fixed-tune convention, ripple, 43%, and overlays were replaced. The remaining or new ones cover momentum choice, the MARS foil thickness, the missing fixed-tune runs, the ripple amplitude, the Fig. 3 run length, and the 43% denominator.

### Author questions raised by the records (highest priority first)

1. **43% denominator.** The archived accounting divides by the 2,402-particle tracked subset (1.9% of the returned 127,975). Confirm that the reported 43% refers to that subset; if so, the abstract, highlights, and conclusions should say so.
2. **Momentum.** The simulations used 8.827 GeV/c; Table 1 lists 8.889. Choose which value Table 1 reports (Bρ would become 29.445 T m, βγ 9.41).
3. **Fixed-tune runs.** The 30,000-turn runs plotted in Figs. 1–2 are missing; the related 20,000-turn runs differ numerically. Locate them, or accept the present wording.
4. **Ripple amplitude and gains of Fig. 3.** Not in any archived run.
5. **Reduced-model orientation.** The RK4 ignores the lattice resonance phase (0.29–0.31 rad); confirm that the separatrix orientation matches the Synergia2 coordinates at ESS1.
6. **Energy loss in ring tracking.** The tracking input sets dp/p = 0 for particles that lost up to 50 MeV in MARS; confirm, or state as a limitation.
7. **Feed-forward acceptance.** Ref. [mu2e] calls its 35π acceptance normalized, but the code applies it as geometric. Consider an erratum in the companion paper.

### Validation

Both builds succeeded from the repository root into scratchpad `mktemp` directories: review layout 27 pages (contents on page 1), submission build 26 pages. The only LaTeX box warning is the known 117.08 pt CAS keyword overlay; BibTeX reports 0 warnings; 50 labels are unique, and every `\ref`/`\eqref` resolves. Pages 5, 6, 10, 12, and 26 were rendered and inspected. `img/*`, `beamstudy.tex`, `modeling.tex`, `beamstudy-mod.bib`, and `highlights.txt` are unchanged (`git status`). Six `AUTHOR CHECK` comments remain. The build does not validate the simulations; the archived records establish settings and definitions, not the correctness of the results.

## Task 26 completed: layout, bibliography, and style corrections

Completed 2026-10-01. No manuscript text, value, or figure changed in this task.

- **Finding 1 (Table 1 placement):** already resolved by the author-requested Section 2 rewrite; Table 1 sits in §2.1.
- **Finding 2 (MARS15):** the `mars2` title now protects `{MARS15}`, matching the primary report's title page (FERMILAB-CONF-10-518-APC, December 2010). The entry renders "Recent MARS15 developments…". Nothing else changed.
- **Finding 3 (TDR link):** removed the `url` field from `tdr`. The reference now shows the report number and "arXiv:1501.05241" once, without a hyperlinked title or a separate URL line. The verified metadata is unchanged.
- **Finding 4 (Acknowledgments numbering):** **author decision, 2026-10-01: keep the numbered heading** ("9. Acknowledgments"), matching the companion manuscript format. Revisit only if a chosen journal requires an unnumbered heading.

Validation: the bibliography diff is exactly the two intended lines. Both variants were rebuilt fresh: 25 pages each, 0 BibTeX warnings, 24 entries with the same keys in the same order as before, and only the known CAS overlay box. The rendered references were checked. All 26 figure, draft, manuscript, and highlight hashes are unchanged.

## Task 25 completed: undocumented-setting disclosures consolidated in Appendix A

Completed 2026-10-01. Presentation only; every disclosure is retained and no value, figure, or bibliography entry changed.

- **New Appendix A** ("Settings not specified in the available simulation records", label `app:records`) with Table 4 (`table:records`). It lists, by case (all Synergia2 cases, fixed-tune RFKO, ripple and feedback, tune step, reduced model, septum scattering), every setting or plot convention that the available records do not specify. It is built only from the existing REVIEW author-check rows and case-metadata status. It also makes visible several items that previously appeared only in REVIEW or `AUTHOR CHECK` comments: the 20,000-turn run length, the restoration values, the Twiss parameters, the coefficient phase convention, the MARS version, and whether transit times beyond 250 turns occurred.
- **Kept in place (13 main-body occurrences)**, because a number or claim depends on them or a reader of that figure alone needs them:
  - the inherited-settings statement (§2.1);
  - the 20π acceptance normalization (§2.4) and three comparison-table cells;
  - the bandwidth confound (Sec. 4.1);
  - the transit-time selection and arrival criteria (Sec. 5);
  - the C-magnet-to-ESS1 mapping and the 43% endpoints (Sec. 6);
  - the caption notes on emittance definition, action diagnostic, spill normalization, transit-axis normalization, MARS axis units, overlays, and loss-map legend.
- **Replaced by pointers to Appendix A (about 10):**
  - the controller update interval, the Table 2 caption and tune-step cell;
  - the centroid sampling interval in the Fig. 1 caption;
  - controller gains and comparison criterion, the post-hold protocol, the integration step and detection cadence, and the scattering-workflow endpoint (now "discussed below");
  - the duplicate overlay note (now "see the figure caption");
  - in §7.1, controller gains and delay, plus the gain-schedule rationale (now "for reasons the records do not state");
  - in §7.4, the action-reference and plot-convention lists.
- **Counts.** Main-body "not documented" fell from 28 to 16 (7 in captions); the broad hedge count from 74 to 63. Every disclosure from before the edit appears either locally or in Table 4; all 28 were checked individually.
- **Layout.**
  - The appendix starts on a new page so that Table 4 stays with its heading, before the references. In the review layout it is kept out of the contents list (`\addtocontents{toc}{…tocdepth 0}`), so the contents remain on page 1.
  - Both builds are 25 pages (previously 24) and pass with 0 BibTeX warnings and only the known CAS overlay; pages 23–25 were inspected.
  - There are 50 unique labels, all resolved, and all 26 figure, draft, bibliography, and highlight hashes are unchanged.

## Follow-up: Section 2 rewritten as "Simulation methods" (author request, 2026-10-01)

The author found the Section 2 title ("Published baseline and simulation cases") unsuitable for a journal paper and asked for the section to be checked and, if needed, rewritten.

**Problems found.** The title and the subsection title "Shared parameters and published settings" read as review language. The section never described the machine, the extraction hardware, or the simulation codes, which appeared only in passing in the Introduction. It contained meta-commentary ("Several intervals of about 100 turns occur in this paper…", "We therefore do not assume…"). Table 1 was defined in the Introduction rather than with its discussion (Task 26, finding 1).

**New structure** (labels `sec:scope`, `sec:baseline`, and `sec:cases` kept so that existing references resolve; `sec:codes` and `sec:comparison` added):
- **§2.1 Machine and beam.** The extraction hardware, taken from Ref. [2] and checked against its text: two harmonic-sextupole circuits of three sextupoles each, three tune-control quadrupoles near the middle of each straight section, two electrostatic septa, one Lambertson magnet, one C-magnet, and the chromaticity sextupole families. This subsection now holds Table 1 and states the Ref. [2] settings, with the existing statement that their reuse in the present cases and any convergence study are undocumented.
- **§2.2 Simulation codes.** Synergia2 (three-dimensional space charge, included only in the cases marked in the cases table; aperture models; the dedicated ESS1 septum aperture), MARS ([mars2] with the channel model of [mars1]), and the reduced model with RK4 (now defined here, at first use).
- **§2.3 Simulation cases.** A short overview with the case table, and the distinct time structures stated as method facts. The undocumented controller update interval is kept.
- **§2.4 Comparison with the feed-forward study.** The 50 versus 100 µm foils, the three 20π/20π/35π mm mrad quantities, the comparison table (headers "Ref. [2]" and "This work"), and the loss-population statement.

**Other changes.**
- The Introduction's "three models" paragraph was shortened to point to §2.2, and the roadmap sentence was updated.
- Cross-references moved with the content: the RFKO-acceptance pointer and the two 43% pointers now go to §2.4, while the §7.4 inherited-settings pointer stays at §2.1.
- Captions were rewritten in journal style. Tables are numbered in order of appearance, so the cases table is now **Table 2** and the comparison table **Table 3**; all in-text references use `\ref`. The README and pending-task numbering was updated.
- Bibliography numbering shifted, because Synergia2 is now first cited in §2.2. All 24 entries are still cited.

**Preserved.** No number, setting, or disclosure was removed: the undocumented reuse of published settings, the convergence statement, the acceptance normalization, the controller update interval, the conditional 43%, and the `AUTHOR CHECK` comment. The broad hedge count is unchanged or lower (see Task 25 for consolidation).

**Validation.** Both variants were rebuilt fresh: 24 pages each, 0 BibTeX warnings, 24 bibliography entries, and only the known CAS overlay box. The review contents stay on page 1. Pages 3–6 were inspected. All 26 figure, draft, bibliography, and highlight hashes are unchanged.

## Task 24 completed: residual attribution and scope slips

Completed 2026-10-01. Wording and paragraph structure only; no value, figure, or bibliography metadata changed.

- **Space charge only where documented (finding 1).** The reference drafts give no evidence that the feedback case included space charge; the companion's "with space charge" statement refers to the feed-forward study.
  - Sec. 4.2: "in this space-charge tracking model" became "in this Synergia2 tracking case".
  - Introduction: "at high space charge" became "with space charge included in the fixed-tune and tune-step tracking".
  - Whether the feedback and scattering ring-tracking cases included space charge remains an author question (Task 03 metadata status).
- **PID citation (finding 2).** "Controllers based on PID feedback were investigated [pid]" became "The original study investigated PID controllers, a standard feedback scheme [pid]". Ref. [pid] now supports only the concept.
- **Reference-group branch (finding 3).** Now attributed: "According to the original analysis, after three turns the added reference group follows the outgoing separatrix branch…". A new sentence notes that in Fig. 7(a) the branch can be identified only through the orange overlays, whose definition is not documented.
- **Fig. 1 caption (finding 4).** "Nonzero chromaticity gives greater emittance growth…" became "With nonzero chromaticity, emittance growth is greater and centroid excursions are smaller."
- **Paragraphs and wording (finding 5).** The Fig. 4 paragraph (252 words) was split into burst behavior and post-restoration behavior. The Fig. 7(a) paragraph (222 words) was split into the initial line with its mapping caveat and the three-turn evolution. The second "therefore" became "thus", and "at that turn" became "at the restoration turn". The longest body paragraph is now 195 words, so none exceeds 200 after Tasks 23–24.
- **Counts.** "Not documented" rose from 27 to 28 (the new overlay caveat), and the broad hedge count from 74 to 75. Task 25 consolidates these disclosures.

Validation: both variants were rebuilt fresh, 24 pages each; the review contents stay on page 1. Both have 0 BibTeX warnings, and the only box warning is the known CAS overlay. Pages 12, 15, and 20 were inspected. All 26 figure, draft, bibliography, and highlight hashes are unchanged. The space-charge question for the feedback and scattering cases was added to the "Geometry and inherited baseline" author check.

## Task 23 completed: follow-up prose tightened without losing qualifications

Completed 2026-10-01. Wording and paragraph structure only; no claim, number, figure, or citation changed.

- **Chirp coverage (finding 1).** The repeated "The chirp is described as covering the betatron tune spread" was removed. The setup now names the two chromaticities, describes the chirp once, and follows directly with the space-charge and bandwidth qualification.
- **Action profiles (finding 2).** The 271-word paragraph is now two. The first gives the diagnostic, its undocumented reference, the conditional annulus/Gaussian interpretation, and why the reference matters. The second gives the observed C_x = 0 and C_x = 1 profiles. The three speculative explanations of the C_x = 0 coincidence were reduced to one sentence: the records do not establish whether it reflects a centroid-referenced diagnostic or differently sampled turns. The full list remains in the REVIEW author checks (Task 18).
- **Transit times (finding 3).** The 289-word paragraph is now three: observations (coordinate trend, model comparison, stage trend); pathway interpretations, explicitly labeled because only the starting x is plotted; and the discrete levels with their unresolved sampling-or-physics origin.
- **Response chain (finding 4).** "comparable … comparable" became "If the RFKO case has transit delays similar to those of the separate tune-step case, these delays are comparable to or longer than the averaging interval". The conditional interpretation now starts its own paragraph, and the cross-case limitation is unchanged.
- **Summaries (finding 5).**
  - Abstract: "increasing as the starting horizontal coordinate lies farther from the septum in the displayed samples".
  - Conclusions: "In the displayed samples, the delays increase as the starting horizontal coordinate lies farther from the septum".
  - Highlight 4: "Transit time grew as the starting horizontal coordinate lay farther from the septum" (83 characters; still needs author approval).
- **Layout.** The longer abstract pushed the review contents onto page 2, so the review-only contents list is set in `\footnotesize` again. The submission build is unaffected.

**Qualifier preservation.** The counts are unchanged for "not documented" (27), "consistent with" (16), "possible" (4), "may" (10), "undocumented" (5), "conditional" (5), the 43% mentions (8), and `\cite` (53). Small shifts are rewordings: a "plausible interpretation" and "do not distinguish" became "pathways are interpretations" and "do not establish whether". The broad hedge count is unchanged at 74. The paragraphs over 200 words are now only the 252- and 222-word ones assigned to Task 24.

Validation: review build 24 pages, with the contents on page 1 and the Introduction on page 2. Submission build 24 pages. Both have 0 BibTeX warnings, and the only box warning is the known CAS overlay. Pages 1, 11, 16, and 22 were inspected. All 25 figure, draft, and bibliography hashes are unchanged.

## Task 22 completed: setup statements aligned with documented uncertainty

Completed 2026-10-01 with editorial corrections only; no value, figure, or result changed.

- **Update interval (finding 1).** "Neither of these is the controller update interval" became "Neither establishes the controller update interval, which is not documented". The interval is now neither equated with nor excluded from the 100-turn accumulation and chirp sweep.
- **Bandwidth (finding 2).** The two places that presupposed a difference now say "a possible difference between the two cases' undocumented bandwidths" (Sec. 4.1 implication) and "a possible difference in the undocumented excitation bandwidths" (Conclusions); the current claim–evidence map was aligned. All other uses already said "may differ" or "not excluded".
- **Acceptance (finding 3).** "whose normalization is given in Table 2" became "whose normalization is not documented (Table 2)", in agreement with the table.
- **Table 3 selection (finding 4).** The tune-step sample cell now reads "Particles reported as released by the step (selection criterion not documented; Sec. 5)".
- **Nominal versus run momentum (finding 5).**
  - The Table 1 caption now states that 8.889 GeV/c is a correction of the nominal value and that the momentum used in the original simulation inputs has not been checked.
  - Sec. 5 now says the calculation uses "the nominal parameters of Table 1", noting that the input-deck momentum was not checked against the corrected entry. The supported correction is kept.
  - The question was added to the "Geometry and inherited baseline" author-check row.

Validation: both variants were rebuilt in fresh directories (review and submission, 24 pages each; contents on page 1 in review only). Both have 0 BibTeX warnings, and the only box warning is the known CAS overlay. Pages 2 and 6 (Tables 1 and 3) were inspected. All 26 tracked figure, draft, bibliography, and highlight hashes are unchanged.

## Task 21 completed: bibliography syntax and current review summaries

Completed 2026-10-01. No manuscript text, result, figure, or reference draft was changed.

- **Bibliography.** Removed two unmatched inter-entry closing braces from `beamstudy-mod.bib`, after `pimms2` and after `rfkoreg`. They were introduced by the Task 17 entry split and silently ignored by BibTeX. A brace-depth scan now finds no stray braces. The generated `.bbl` is byte-identical to the pre-fix build, so all 24 keys, their metadata, and the citation order are unchanged.
- **Current versus historical summaries.**
  - Added a dated "Current status" section at the top of this file, with an updated claim–evidence map reflecting the Task 18–20 narrowing and an extended readiness list.
  - Relabeled the 2026-09-29 backlog section as historical.
  - Added a note marking the Task 10 claim–evidence map as superseded; its readiness list remains valid.
  - No earlier record, count, or date was altered. The "22 references" heading of the Task 09 audit describes that revision.
- **README.** The current citation statement reads "24 entries after splitting", replacing "audited all 22 citations". The page count is now 24, the follow-up narrowing is listed, the Done row covers 02–21, and the readiness pointers include "Current status".
- **Task index.** The header and summary now report all Tasks 02–21 complete.

Validation:
- Both variants were rebuilt from the repository root into fresh `mktemp` directories. Review build: 24 pages, contents on page 1. Submission build: 24 pages, no contents.
- Both have 0 BibTeX warnings and 24 bibliography items, and the only box warning is the known CAS overlay. There are no undefined references or rerun requests.
- 46 unique labels, all resolved; 24 cited keys equal the 24 bibliography keys.
- Pages 22–24 (Discussion end, Conclusions, references) were inspected.
- All 22 image files and both reference drafts are unchanged.

## Task 20 completed: transported scattering coordinates and repeated encounters

Completed 2026-10-01 with no new transport, encounter statistics, or figure changes. The conditional 43% result and its endpoint qualifications are unchanged.

- **Thin-foil identity, local only (finding 1).** The Fig. 7(a) paragraph now leads with the observed near-vertical line and gives Δ(αx+βx') = βΔx' as a local idealization at the scattering plane with fixed Twiss parameters. Because the plotted coordinates were transported from the C-magnet and referred back by an undocumented transformation, and channel transport can convert an angle change into a position change (the R12 term), the line is stated not to verify that mapping.
- **Phase-space return, not a demonstrated encounter (finding 2).**
  - "Scattered particles therefore meet the septum again every third turn … repeated chances" became the observation that, after the three turns shown, many displayed particles lie again in the septum field region. Possible later encounters are stated as an interpretation, and the text says the snapshots do not show foil interception, extraction-field crossing, or a long-term three-turn recurrence.
  - The loss-location sentence and §7.2 were reworded to match: "may have further chances … the displayed snapshots do not establish how often individual particles encounter the septum".
- **Workflow endpoint (finding 3).** Step 3 changed from "tracked … until each particle is lost or survives" to "each particle is reported either as lost or as surviving; the tracking duration and the extraction criterion are not documented", consistent with the results paragraph, which keeps "reported extracted" distinct from "not lost within the tracked interval".
- **Author check.** Two questions were added to the "Scattering handoff and 43% denominator" row:
  - the nature of the return mapping (inverse transport, coordinate conversion, or reference-plane assignment);
  - whether later-turn encounters with the foil or field were recorded.

Validation: the build succeeded at 24 pages with the contents on page 1, 0 BibTeX warnings, and only the known CAS overlay. All references resolve, and pages 17, 18, and 21 were inspected. All 25 image, draft, and bibliography hashes are unchanged.

## Task 19 completed: sampling, resonance motion, and feedback-delay evidence

Completed 2026-10-01 from the printed equations and existing records only; no trajectory, timing distribution, or controller test was generated.

- **Rotating frame (finding 1).** The frame is now described as removing the linear resonant rotation. A new sentence states that a particle exactly on resonance is stationary only without the resonance drive. With ε = 0, Eq. (7) gives dX/dτ = (3S/4)(X² − X'²) and dX'/dτ = −(3S/2)XX', which are generally nonzero (printed-algebra check).
- **Sampling versus physics (finding 2).** The RK4 paragraph now states that the integration step and the arrival-detection cadence are undocumented. The discrete short-transit levels are reported as observed. For the reduced model they may reflect the three-turn output sampling, and a physical three-turn return to the septum side is also possible; the text states that the records do not distinguish these. The REVIEW-only pixel measurement of the levels (Task 06) is unchanged and is not cited as evidence of either origin.
- **Branch membership (finding 3).** "Already on the outgoing branch" and "must travel … past an unstable fixed point" are now labeled as interpretations, because the plot shows only the starting x, not X'. The mechanism sentence reads "can account … may contribute". §7.3 now calls the fixed-point explanation qualitative.
- **Tune-step evidence versus controller behavior (finding 4).**
  - The Sec. 4.2 interpretation, the Sec. 5 implication, and §7.1 now present the delay mechanism as plausible across separate cases. They say "if the RFKO-driven response has comparable delays", and state that the tune-step diagnostic does not measure the RFKO loop delay or establish the cause of the spikes or the P-only oscillation.
  - The "effective delay grows during the spill" claim is now conditional, with the caveat that the truncated, changing samples do not establish a general trend.
  - The Sec. 4.2 response-time sentence now says the time particles take to reach the septum is "expected to contribute".
- **Propagation.**
  - Abstract: transit times "from a few to more than one hundred turns, increasing with the starting distance from the septum"; the reduced model "reproduces these trends but differs quantitatively". The fixed-point interpretation was left to the body and Conclusions after a longer abstract pushed the review contents onto page 2.
  - Conclusions: the observed trends, the stage dependence scoped to the displayed diagnostic, and the fixed-point interpretation as the model's; the synthesis says "plausible successive links".
  - Highlight 4: changed from "Transit is slowest near unstable fixed points and lengthens as extraction proceeds" to "Transit time grew with a particle's starting distance from the septum" (69 characters).

Added to the author checks (transit and controller rows):
- the RK4 integration step and arrival-detection cadence for both codes;
- whether the RFKO loop's actual delay was measured in the original study.

Validation: build succeeded at 24 pages (previously 23, because of the text added in Tasks 18–19; page fill checked, with no sparse page other than the usual full-page Fig. 4 float). BibTeX reports 0 warnings, the only box warning is the known CAS overlay, and all references resolve. The contents remain on page 1. All 25 image, draft, and bibliography hashes are unchanged.

## Task 18 completed: RFKO diagnostics and chromaticity claims

Completed 2026-10-01 from existing evidence only; no figure, reported value, or citation metadata changed.

- **Action diagnostic no longer equated with Eq. (2).**
  - The Sec. 4.1 profile paragraph now states that the relation to Eq. (2) is not established, because the orbit-versus-centroid reference is undocumented.
  - It explains why the reference matters: about the reference orbit, ⟨I_x⟩ = [Var(X) + Var(X') + ⟨X⟩² + ⟨X'⟩²]/2, so coherent displacement contributes.
  - It lists the explanations the records cannot distinguish for the near-coincident C_x = 0 profiles despite the Fig. 1(b) excursions: a centroid-referenced diagnostic, excursions small compared with the beam size, or different sampling times.
- **Density interpretation made conditional.** It now requires a fixed reference and f(u) = dN/du with u = √I_x. The annulus area 4πu du (radius √2 u) is stated, so f(u)/u is an *angle-averaged* density. A Gaussian profile in u requires a centered, matched Gaussian beam, and a displaced or mismatched beam need not give one. "Diffusion-like" was replaced by "consistent with amplitude growth driven by the excitation", adding that the profiles do not establish the history of individual particles. The Fig. 2 caption now reads "action-distribution diagnostic … under the stated assumptions proportional to an angle-averaged phase-space density".
- **Chromatic spread distinguished from space-charge spread.** "Little tune spread" and "without a tune spread" were replaced by statements about coherent decoherence. At C_x = 0 the chromatic contribution vanishes while the space-charge spread remains. The coherent dipole mode is unaffected by the internal space-charge forces and does not decohere, per the cited IPAC2011 paper, which was checked against its text: "the coherent betatron oscillations of the beam as a whole are not affected by the internal SC forces" (p. 3560) and "At zero chromaticity coherent dipole oscillations are completely decoupled from the incoherent SC motion and therefore they never decohere" (p. 3561). The bandwidth caveat in the setup paragraph was reworded to match.
- **Causal claims bounded.** The following now say "consistent with" chromatic mixing, cite the earlier simulations [ipac11] for the mechanism, and state that the undocumented bandwidth difference is not excluded: the Introduction contribution sentence, the Sec. 4.1 figure interpretation and implication, the Sec. 4.2 back-reference, the §7.1 response chain, the §7.4 scope (which also notes the undocumented diagnostic reference), and the Conclusions. The observed emittance and centroid contrast is kept in full.
- **Highlight 1** changed from "Chromaticity decides whether knockout excitation heats a beam or moves it coherently" to "Knockout heating grew with chromaticity; without it, coherent beam motion dominated" (83 characters, observational).

Added to the author checks (Emittance/action and RFKO-settings rows):
- the reference of the action diagnostic (orbit or centroid), and whether the Fig. 1 and Fig. 2 samples correspond in time;
- the numerical chirp bandwidth at C_x = 0 and at C_x = 1.

Evidence for the open Δp/p question (Task 12), recorded here only: IPAC2011 states that C_x = 1 "corresponds to 95% chromatic tune spread approximately 0.007" for this extraction. That is consistent with Δp/p = 0.0016 being an rms value (a ±2σ full width of about 0.0064), but it does not establish the convention for the present runs.

## Task 10 completed: final editorial pass and readiness report

*Historical record of the 2026-10-01 pass before Tasks 18–21. Its claim–evidence map is superseded by the Current status section above; its readiness list remains valid and is extended there.*

Completed 2026-10-01. This closes the editorial backlog (Tasks 02–17). No simulation was run at any stage; no figure image, reference draft, or scientific number changed except the documented momentum correction (Task 12).

### Final edits in this pass

- **Acronyms now defined at first use:**
  - RK4 ("fourth-order Runge–Kutta") and ESS1 ("first electrostatic septum") first appeared in Table 3 and the Sec. 6 workflow list before their definitions; both are now defined there.
  - HIMAC is expanded (Heavy Ion Medical Accelerator in Chiba), and "CERN SPS" is written out as "CERN Super Proton Synchrotron".
- **Units:** the last two raw quantities (1 ms, 8 GeV) now use `siunitx`.
- **Title, abstract, introduction, and conclusions** were re-read against the final section order: all present the same scope and the same four findings in the same order.

### Claim–evidence map (abstract and conclusions)

| Claim | Evidence in the manuscript |
| --- | --- |
| Nonzero chromaticity gives emittance growth; zero chromaticity gives mainly coherent centroid motion | Figs. 1–2, Sec. 4.1; mechanism in Sec. 4.1 and the Sec. 3 action–emittance paragraph |
| PD RFKO feedback reduces visible ripple-driven modulation, with residual spikes | Fig. 3, Sec. 4.2 |
| Transit times range widely, are longest near unstable fixed points, and lengthen later in the spill; the reduced model reproduces the trends qualitatively | Figs. 4–5, Sec. 5; Eq. (6) |
| ~43% of the returned scattered-particle sample (50 µm foils) is lost in ring tracking, near the septa and elsewhere | Fig. 7, Sec. 6; reported value from the original study, with denominator and endpoint qualified (Secs. 2.1, 6) |
| Chromatic mixing and transit time are links in the RFKO response chain; interception is followed by loss redistribution | Sec. 7.1–7.2, built only from the results above |

### Document checks

- **Build:** the README commands were run unchanged in fresh `mktemp` directories.
  - Review build: 23 pages, with the contents on page 1.
  - Submission build (`\SubmissionBuild`): 23 pages, with no contents list and the Introduction on page 1; the references end on page 23.
- **Warnings:** the only LaTeX diagnostic is the known 117.08 pt CAS keyword-overlay box, which is visually harmless on the title page. BibTeX reports 0 warnings, with 24 entries. There are no undefined or multiply defined references and no rerun requests.
- **Source integrity:**
  - 46 labels, none duplicated, with every reference and equation reference resolved. Ten labels (subfigures, some sections, and Eq. 4) are defined but never referenced, which is harmless.
  - All 24 citation keys are present in the bibliography, and every entry is cited. All environments are balanced.
- **Visual inspection:** all 23 review pages were rendered and inspected: equations, three tables, eight figures (in numerical order, near first reference), captions, line numbers, Discussion, and references. There is no clipping, stretching, or empty page.
- **Assets:** all 22 image files are unchanged since the repository's first commit (`aeffd56`). Both reference drafts are byte-identical to the pre-backlog commit `c037b4e`.
- **Prose:** broad hedge count 50 (70 before Task 15). There are seven non-rendering `AUTHOR CHECK` comments, which record open questions and should be removed after they are resolved.

### Readiness report

**Editorially complete:** structure, theory, interpretation, captions, references, numbers and units, front matter, and build are finished within the author's no-new-simulation scope.

**Not yet ready for submission.** The following need author action; none can be resolved by editing:

1. **Essential scientific metadata** (the "Author/data checks" table and case-metadata status above):
   - the quadrupole ripple frequency and waveform: the plot suggests ~360 Hz where the text says 60 Hz (Task 11);
   - the ripple amplitude convention;
   - controller gains and the selection criterion;
   - tune-step selection and arrival criteria;
   - the scattered-sample endpoints, weights, and whether the reference particles enter the 43% denominator;
   - the emittance, action, and acceptance conventions and plot normalizations (the Task 12 arithmetic shows inconsistencies);
   - the 50 µm foil provenance.

   The ripple-frequency question in particular affects how Fig. 3 can be described.
2. **Figures:** every asset falls below Elsevier's artwork rules (1000 dpi line art; lettering at least 7 pt). Original or higher-resolution plots are needed, and the MARS figure's provenance must be confirmed (Tasks 08, 09, 16).
3. **Declarations and metadata:** acknowledgments, funding, CRediT, competing interests, data availability, and the generative-AI disclosure. Placeholders are in the source before the references; see the Task 09 checklist.
4. **Journal choice:** the article type, abstract length, keyword limit, highlights approval (`highlights.txt`), and any template change depend on it.
5. **Internal references:** decide how to handle `mars1`, `wcm`, and `rfkoreg` (DocDB, marked n.d.).

A successful build does not validate the simulations. The editorial changes improve the presentation and the scoping of existing results; they do not add evidence.

## Follow-up: final title chosen by the author (2026-10-01)

From the journal-style options offered, the author selected: **"Particle response and septum scattering in third-integer resonant extraction for Fermilab's Mu2e experiment"** (106 characters). This supersedes the 147-character title recorded below.

- The running head is now "Particle response and septum scattering in Mu2e resonant extraction".
- The title fits on two lines, so the review-layout contents list is back to `\small` type and fits on page 1.
- Validation: the build has 23 pages, the Introduction starts on page 2, BibTeX reports 0 warnings, the only box warning is the known CAS keyword overlay, and the PDF metadata title is updated.

## Follow-up: journal-style title (2026-10-01)

At the author's request, the title was revised to a conventional journal style.

- **Old:** "RFKO response, transit times, and septum-scattered particle transport in Mu2e extraction"
- **New:** "Beam response to radio-frequency knockout, transit times, and septum scattering in third-integer resonant extraction for Fermilab's Mu2e experiment" (147 characters)
- **Rationale:**
  - Acronyms are removed; "RFKO" is spelled out, following Elsevier's guidance against abbreviations in titles.
  - The title names the physical process (third-integer resonant extraction) and the facility for indexing.
  - The new wording parallels the companion article, "Tracking simulation of third-integer resonant extraction for Fermilab's Mu2e experiment" (Ref. [2]).
  - The scope is unchanged. "Septum scattering" stands for the transport and loss of septum-scattered particles, and "beam response" covers both the fixed-tune and the feedback results.
- **Running head:** changed to "Knockout response, transit times, and septum scattering in Mu2e extraction" (74 characters), which supersedes the Task 16 wording and keeps the head acronym-free.
- **Contents list:** the three-line title pushed the last two contents entries onto page 2 in the review layout, so the contents list is now set in `\footnotesize`. The submission build has no contents list and is unaffected.
- **Validation:** the review build has 23 pages; page 1 holds the title, abstract, keywords, and full contents; the Introduction starts on page 2. The only box warning is the known CAS keyword overlay, BibTeX reports 0 warnings, and the PDF metadata title is updated. No other text changed.

## Task 16 completed: submission front matter

Completed 2026-10-01. No target journal has been named, so Elsevier-wide rules were checked at Elsevier's official pages and journal-specific rules remain pending.

- **Running head.** `\shorttitle` changed from "Particle dynamics during slow resonant extraction" to "RFKO, transit times, and septum scattering in Mu2e extraction" (61 characters), matching the current title.
- **Contents list.** The review layout the author requested (contents plus a page break, matching the companion manuscript) remains the default. A submission build defined by `\SubmissionBuild` omits both:
  `latexmk -pdf -usepretex='\def\SubmissionBuild{}' beamstudy-mod.tex`
  The README documents the switch. Double spacing and line numbers are kept in both builds.
- **Keywords.** Changed from Mu2e, Resonant extraction, Spill regulation, Beam dynamics, Radio-frequency knockout to six more specific terms: Mu2e, Resonant slow extraction, Radio-frequency knockout, Spill regulation, Transit time, Septum scattering. Confirm the journal's keyword limit.
- **Highlights** (`highlights.txt`, a new file for separate upload). Five bullets of 77–85 characters, drafted only from existing findings, without acronyms, and keeping the returned-sample qualifier for 43%. Elsevier's highlights page gives "three to five" bullets of "85 characters or fewer, including spaces" and asks for no jargon or acronyms ([Elsevier highlights](https://www.elsevier.com/researcher/author/tools-and-resources/highlights)). The author must approve them.
- **Declarations.** Commented, unrendered placeholders were added immediately before the references for the CRediT statement, competing interests, data availability, and the generative-AI declaration. The last carries Elsevier's template wording and placement rule ("at the end of your manuscript, immediately before the references"; [Elsevier generative-AI policy for journals](https://www.elsevier.com/about/policies-and-standards/generative-ai-policies-for-journals)). No declaration was written; the Task 09 checklist remains the author action list.
- **Figure resolution against Elsevier artwork rules** ([artwork sizing](https://www.elsevier.com/about/policies-and-standards/author/artwork-and-media-instructions/artwork-sizing)):
  - The rules require 300 dpi for halftones, 500 dpi for combination art, and 1000 dpi for line art, with printed lettering of at least 7 pt (6 pt for sub- and superscripts). Single, 1.5, and double columns are 90, 140, and 190 mm wide.
  - The existing plots are line art. They print at 118–261 dpi, with in-image labels of about 3.5–8 pt at the review-layout widths (Task 08 inventory), so they do not meet these rules.
  - An 812-px image would reach 1000 dpi only at about 21 mm wide, below Elsevier's 30 mm minimum.
  - Compliance therefore needs the original vector or high-resolution plots. No figure was modified or upsampled, and no compliance is claimed.
- **Cover letter.** Not drafted, because the author has not asked for one. Checklist item 9 (Task 09) records the recommended statement on the relationship to Ref. [2].

Validation: both variants were built with pdfLaTeX and BibTeX.

- The review build has 23 pages, with the contents on page 1.
- The submission build (`-usepretex='\def\SubmissionBuild{}'`) has 22 pages, with no contents list and the Introduction starting on page 1.
- Both have 0 BibTeX warnings, and their only box warning is the known CAS keyword overlay.
- Title pages were inspected: the six keywords fit the article-info column, and the new running head appears on page 2.
- Image, reference-draft, and bibliography hashes are unchanged. No simulations, staging, commits, or pushes.

## Follow-up: BibTeX warnings cleared (2026-10-01)

At the author's request, the remaining two BibTeX warnings (`empty year in wcm`, `empty year in rfkoreg`) were removed without inventing dates.

- The NET 2026 paper and the IBIC2019 spill-regulation paper do not cite Mu2e Documents 3627 or 3625.
- Mu2e DocDB redirects to Fermilab single sign-on, so no date could be verified.
- Both entries now use `year = {n.d.}`, the standard "no date" marker, and render as "(n.d.)". A bibliography comment asks the author to substitute the DocDB dates.
- BibTeX now reports `warning$ -- 0`. The build is unchanged at 23 pages, and the only LaTeX box warning is the known CAS keyword overlay.

## Task 17 completed: build, bibliography structure, and repository documentation

Completed 2026-10-01.

- **Bibliography split.**
  - `pimms` became `pimms1` (CERN/PS 99-010 (DI), 1999; L. Badano et al., 9 authors) and `pimms2` (CERN/PS 2000-007 (DR), 2000; P. J. Bryant et al., 14 authors). Authorship and report numbers come from the INSPIRE records for those report numbers; the study name is protected from the style's lowercasing.
  - `wcm` became `wcm` (P. Prieto, Mu2e Document 3627-v4) and `rfkoreg` (P. Prieto, Mu2e Document 3625-v1), from `modeling.tex`, labeled as internal reports and left undated.
  - The citations were updated to `\cite{hardt,pullia,pimms1,pimms2}` and `\cite{wcm,rfkoreg}`.
  - BibTeX then warned only about the two genuinely undated internal reports (cleared in the follow-up above); the merged-entry warnings were gone. The bibliography has 24 entries.
- **Layout macros.** Removed `\def\floatpagepagefraction{1}` and `\def\textpagefraction{.001}`. Neither is a LaTeX float parameter (the real names are `\floatpagefraction` and `\textfraction`); both came from the companion template and had no effect. Their effective counterparts were not substituted, because `\floatpagefraction` = 1 would force float pages to be completely full and could defer floats. The rebuilt PDF has the same 23 pages, and every table and figure is on the same page as before (compared against the Task 09 build).
- **README.**
  - Earlier finding corrected: the README had already been updated for BibTeX in commit `f669ffb`, after the 2026-09-29 review read the pre-commit file, so the earlier statement in this file that the README was updated is accurate.
  - This task updated the opening summary to the new section order and added `CLAUDE.md` to the file table.
  - The build note now describes the remaining BibTeX warnings and the small-type contents list.
  - "Submission status" was rewritten to the current state, pointing to the author checks and checklist in this file.
  - The long task-completion paragraph was replaced with a Done/Pending table.
- The task index in `tasks/README.md` already lists Tasks 11–17.

Validation: the README's `latexmk` command, run unchanged from a clean `mktemp` directory (with `TMPDIR` set to the session scratchpad), succeeded. The result has 23 pages, 24 bibliography entries, and the only box warning is the known CAS keyword overlay. The only BibTeX warnings are the empty years of `wcm` and `rfkoreg`. Labels are unique and every reference resolves. Image and reference-draft hashes are unchanged. No simulations, staging, commits, or pushes.

## Task 09 completed: attribution and submission metadata

Completed 2026-10-01. No target journal has been named, so the `cas-sc` class is retained and journal-specific adaptation remains pending. No declaration was written on the author's behalf.

### Citation audit (22 references, first-citation order)

| Key | Status | Primary record / note |
| --- | --- | --- |
| `tdr` | Verified | TDR PDF (arXiv:1501.05241): October 2014, FERMILAB-TM-2594, first author L. Bartoszek |
| `mu2e` | Verified | Author-supplied NET PDF and DOI 10.1016/j.net.2025.104097; vol. 58 (2026) retained |
| `hardt` | Partly verified | CERN CDS record 1025914 carries the exact title; report number and date could not be read (bot wall) and remain as cited in the literature |
| `pullia` | **Corrected** | Thesis title page (INSPIRE 511446, CERN-THESIS-99-070): "Dynamique de l'éjection lente et son influence sur les lignes de transfert", Université Claude Bernard – Lyon 1, defended 25 Oct 1999. The previous English title ("Detailed dynamics of slow extraction…") is not the thesis title; the entry now gives the French title with INSPIRE's English title. This resolves the institution conflict noted in PRIOR_WORK_COMPARISON. |
| `pimms` | Verified | CERN CDS PDFs, Parts I and II (earlier revision); entry split deferred to Task 17 |
| `HB10`, `ipac11`, `pid`, `preliminary`, `mars2`, `synergia2` | Verified | Primary PDFs listed under "Sources consulted" (earlier revisions) |
| `hiramoto`, `noda`, `furukawa`, `niedermayer`, `velotti`, `crystal8gev`, `srs2019`, `srs2025` | Verified | Task 14 table |
| `kobayashi` | **Corrected** | INSPIRE record (HEACC 1967, C67-09-11, pp. 347–351): title is "Improvement of the emittance in the resonant **beam** ejection"; booktitle normalized |
| `mars1` | Internal, not inspectable | Metadata from Ref. [2], item 19; honestly labeled as an internal report |
| `wcm` | Internal, not inspectable | Recovered from `modeling.tex`; honestly labeled; year unknown (split deferred to Task 17) |

Attribution in the text was re-checked. The feed-forward ramp, septum and bump optimization, solver settings, ±20% open-loop spill, 1.2% geometric loss, 35π acceptance, 100 µm foils, and the 1.5–3 expectation are all attributed to Ref. [2]. The Hamiltonian is attributed to [preliminary] and [kobayashi], transit-time theory to [pullia], and the Hardt condition to [hardt, pullia, pimms]. Every citation key resolves.

### Author-only submission checklist (not answered by editing)

1. **Authorship and acknowledgments.** The manuscript lists a single author. `modeling.tex` thanks J. Amundson, L. Michelotti, and V. Nagaslaev; decide whether this manuscript should acknowledge contributors to the simulations, the MARS work, or the controller.
2. **Affiliations and ORCID.** Confirm the two Korea University affiliations and the "formerly Fermilab" footnote. Supply an ORCID if desired; the empty ORCID footnote is currently suppressed.
3. **Funding.** The acknowledgment cites the Fermilab operating contract (DE-AC02-07CH11359, matching the TDR's contract statement) and ComPASS/SciDAC. Confirm whether current support at Korea University, for example a national research grant, must also be acknowledged.
4. **CRediT author statement** (Elsevier practice), required by most target journals.
5. **Declaration of competing interests.**
6. **Data availability.** The input decks, particle samples, controller code, and plotting data are not in this repository. Choose a truthful statement; none has been drafted.
7. **Generative-AI use declaration.** Elsevier journals ask authors to disclose AI-assisted writing. This revision was prepared with an AI assistant, so the author should decide on and approve the wording.
8. **Figure provenance and permissions.**
   - Confirm that every figure was produced by the author for this study.
   - In particular, confirm whether the MARS trajectory plot (Fig. 6, `fig_beamloss1.png`) comes from the internal MARS report of Mokhov, Nagaslaev, and Rakhno. If it does, credit or permission is needed.
   - Confirm that no figure duplicates one in Ref. [2]; none was found visually (PRIOR_WORK_COMPARISON).
9. **Relationship to Ref. [2].** State in the cover letter that this is a follow-up with distinct simulations, to avoid a duplicate-publication concern (see Task 16).
10. **Internal references.** Some journals discourage citing non-public DocDB reports. Decide whether to keep `mars1` and `wcm` as internal reports, replace them with public equivalents if any exist, or cite them as private communications.
11. **Target journal.** Required before checking article type, abstract length, highlights, declarations format, and figure-resolution rules (see the Task 08 residuals).

Validation: `latexmk` with pdfLaTeX and BibTeX succeeded (23 pages). The corrected entries render as shown above, and the only BibTeX warnings are the known `pimms`/`wcm` years. Labels are unique and every reference resolves. Image and reference-draft hashes are unchanged. No simulations, staging, commits, or pushes.

## Task 14 completed: literature positioning

Completed 2026-10-01. Eight references were added. Each was checked at a primary record (publisher, OSTI, JACoW, or PubMed Central) before use, and each supports a specific sentence. No reference was added from memory or from a secondary citation alone.

| Key | Reference | Verified at | Supports |
| --- | --- | --- | --- |
| `hiramoto` | K. Hiramoto, M. Nishi, NIM A 322(2) (1992) 154–160, doi:10.1016/0168-9002(92)90023-W | [OSTI 6767253](https://www.osti.gov/etdeweb/biblio/6767253) | RFKO origin: amplitude growth inside a constant separatrix by transverse perturbation (Introduction) |
| `noda` | K. Noda et al. (14 authors), NIM A 374(2) (1996) 269–277, doi:10.1016/0168-9002(96)00096-4 | [OSTI 275317](https://www.osti.gov/etdeweb/biblio/275317) | HIMAC AM/FM RFKO; extraction response "within 1 ms" (Introduction) |
| `furukawa` | T. Furukawa et al., NIM A 522(3) (2004) 196–204, doi:10.1016/j.nima.2003.11.395 | [OSTI 20499458](https://www.osti.gov/etdeweb/biblio/20499458) | RFKO amplitude feedback for spill control (Introduction, Sec. 4.2) |
| `niedermayer` | P. Niedermayer, R. Singh, Sci. Rep. 14 (2024) 10310, doi:10.1038/s41598-024-60966-y | [PMC11070430](https://pmc.ncbi.nlm.nih.gov/articles/PMC11070430/) | Recent knock-out excitation optimization for spill fluctuations (Introduction) |
| `velotti` | F. M. Velotti et al. (14 authors), PRAB 22 (2019) 093502, doi:10.1103/PhysRevAccelBeams.22.093502 | [APS abstract](https://journals.aps.org/prab/abstract/10.1103/PhysRevAccelBeams.22.093502) | Septum loss limits slow-extracted flux through activation; crystal shadowing developed and prototype-tested at the SPS (Introduction, Secs. 6 and 7.2) |
| `crystal8gev` | V. Nagaslaev et al. (11 authors), NIM A 1058 (2023) 168892, doi:10.1016/j.nima.2023.168892 (FERMILAB-CONF-23-473-AD) | [OSTI 2336770](https://www.osti.gov/pages/biblio/2336770) | Mu2e 8 GeV shadowing simulations: loss reductions "between 40% and factor of three" (Introduction, Sec. 7.2) |
| `srs2019` | M. A. Ibrahim et al., Proc. IBIC2019, pp. 177–180, MOPP033, doi:10.18429/JACoW-IBIC2019-MOPP033 | [JACoW](https://proceedings.jacow.org/ibic2019/doi/JACoW-IBIC2019-MOPP033.html) | Mu2e SRS design with tune-ramp-quadrupole and RFKO loops (Introduction) |
| `srs2025` | A. Narayanan, Proc. NAPAC2025, pp. 522–524, TUP068, doi:10.18429/JACoW-NAPAC2025-TUP068 (published 28 Jan 2026) | [JACoW landing page](https://proceedings.jacow.org/napac2025/doi/jacow-napac2025-tup068/) and [PDF](https://proceedings.jacow.org/napac2025/pdf/TUP068.pdf) text | Current Mu2e simulations use PID fast-quadrupole regulation and plan to compare RFKO ("explore radio-frequency knockout (RFKO) as a fast regulator", p. 524) (Introduction, Sec. 7.1) |

Not added:
- IPAC2021 THPAB243 (verified, pp. 4281–4284), because the NAPAC2025 paper states the current status more directly.
- PRAB 26, 014402 (spill ripple with bunched beams), for which there was no specific supporting sentence.
- CERN octupole loss-reduction work, where one SPS reference suffices.

### Manuscript changes

- **Introduction:**
  - A new related-work paragraph covers the RFKO origin, HIMAC development and feedback, recent knock-out optimization, transit-time theory (existing `pullia`), and the Mu2e SRS design and status. It ends by noting that the RFKO results bear on the open RFKO-versus-quadrupole comparison for Mu2e.
  - The septum paragraph now opens with the septum-loss literature, including the Mu2e 8 GeV result.
  - The contribution statement is now given relative to both Ref. [2] and the literature (Mu2e-specific, high-space-charge diagnostics), without claiming novelty for RFKO or the resonance model.
- **Sec. 4.2:** RFKO amplitude feedback in medical synchrotrons is cited [furukawa] before the proposed Mu2e loop.
- **Sec. 6:** septum interception is identified as a principal loss and activation source [velotti].
- **Sec. 7.1:** relates chromatic mixing and transit-time spread to the planned Mu2e comparison of RFKO with PID quadrupole regulation [srs2025]. The note that a tune change also acts through transit is supported by Sec. 5.
- **Sec. 7.2:** shadowing reduces arrivals at the septum [velotti, crystal8gev], whereas this study addresses particles that are intercepted.

### Internal-report dependence (remaining limitation)

- The MARS channel model rests on Mu2e Document 3697 [mars1] (internal; cited also by the published Ref. [2]) and the public MARS15 reference [mars2].
- The wall-current spill monitor rests on internal Documents 3627/3625 [wcm].
- The public IBIC2019 paper now documents the regulation-system design, but not the monitor specifically, so it was not substituted.

No other central claim relies only on an internal report.

Validation: `latexmk` with pdfLaTeX and BibTeX succeeded (23 pages; previously 22). The bibliography has 22 entries in first-citation order. BibTeX shows only the two known missing-year warnings (`pimms`, `wcm`). Labels are unique and every reference and citation resolves. The introduction page and reference pages were inspected, and the contents still fit on page 1. All image and reference-draft hashes are unchanged. No simulations, staging, commits, or pushes.

## Task 12 completed: numerical and unit consistency

Completed 2026-10-01 using arithmetic on printed values, the local sources (`beamstudy.tex`, `modeling.tex`, and the author-supplied NET 2026 PDF), and the Mu2e TDR. No simulation was run.

### Correction made

- **Beam momentum: 8.886 → 8.889 GeV/c (Table 1).**
  - All three local tables list 8.886 (the NET table gives its unit as "GeV") beside Bρ = 29.650 T m. These are inconsistent: 8.886 GeV/c gives Bρ = 29.641 T m.
  - The Mu2e TDR ([arXiv:1501.05241](https://arxiv.org/abs/1501.05241), PDF page 273) states "Mode 2: Resonantly extracted proton beam at a kinetic energy of 8 GeV". The accelerator overview (PDF page 23) also gives Booster protons "with a kinetic energy of 8 GeV".
  - An 8 GeV kinetic energy gives p = 8.8889 GeV/c, Bρ = 29.650 T m (exactly the tabulated value), and βγ = 9.474.
  - The correction therefore meets the Task 12 criterion (a primary source plus an explicit calculation). The Table 1 caption states the change and notes that the earlier tables list 8.886. An `AUTHOR CHECK` comment records it.
  - The derived quantities are insensitive to the change: T_rev = 1.6948 µs for either value, and the RF frequency is 4 f_rev = 2.360 MHz.

### Derived-number audit (all reproduce within printed precision)

| Printed | Recomputed |
| --- | --- |
| Bρ 29.650 T m | 29.650 |
| T_rev ≈ 1.69 µs | 1.6948 µs |
| 54 ms over 31,795 turns | 53.89 ms (0.2%, rounding) |
| h = 4, 2.36 MHz | 4 f_rev = 2.3602 MHz |
| 100 turns ≈ 0.17 ms | 0.1695 ms |
| 300 turns ≈ 1% of the spill | 0.94% |
| 60 Hz period ≈ 9,830 turns | 9,834 |
| 10^12/31,795 ≈ 3.15×10^7 | 3.1451×10^7 |
| βγ ≈ 9.47 | 9.4737 |
| C_x δ of order 10^−3 | 1.6×10^−3 |

### Table and unit hygiene

- Added three derived rows to Table 1, marked †: βγ = 9.47, T_rev = 1.695 µs, and f_rev = 0.590 MHz. Dimensionless rows keep a blank unit cell, consistently.
- Converted 14 unit-bearing expressions to `siunitx` (`\SI`, `\si`): the 50 and 100 µm foils, 1 µrad, 1.69 µs, 60 Hz, 500 W, 0.17 ms, 54 ms, −11 mm, and the new rows. The micro prefix is now upright instead of an italic math µ, with uniform spacing. The π mm mrad form and the thousands commas were already consistent and are unchanged.

### Convention questions for the author (arithmetic only; nothing asserted in the manuscript)

- **Emittance versus Fig. 1(a)**, the fixed-tune emittance. A normalized 95% emittance of 20π mm mrad, with a Gaussian ε95 = 6 ε_rms, gives a geometric rms emittance of 0.352π mm mrad. The C_x = 0 curve starts near 0.28. Which definition does the diagnostic use: rms or 95%, centroid-subtracted, truncated, matched?
- **Acceptance convention.** A normalized 20π acceptance is 2.11π geometric (95%-type), yet the C_x = 1 rms emittance reaches about 2.75π. A hard aperture of that geometric size could not allow this, so either the acceptance is not a normalized 20π, or the emittance axis uses a different convention. This strengthens the existing "normalization not documented" entry in Table 2.
- **Normalized transit coordinate (Fig. 5).** The septum sits at about −3.4 in "normalized x (mm)" versus x ≈ −11 mm in Fig. 7(a). If X = x/√β with β in m, this implies β ≈ 10.5 m at the observation point. The NET values of 9.1 m and 20.1 m are matched-ellipse β functions of the extracted-beam footprint, not β at ESS1, so they do not resolve this. Please supply the Twiss parameters at ESS1 and the plot normalization.
- **Δp/p = 0.0016.** The NET text derives it from the 40 ns bunch length and the 20π emittance ("we obtain Δp/p ≈ 0.0016"), but the statistic (rms or half-width) is still not stated.

Validation: `latexmk` with pdfLaTeX and BibTeX succeeded (22 pages; `siunitx` 3.4.14). Labels are unique and every reference resolves. The only warnings are the known ones. The Table 1 page was inspected at 110 dpi. All image, reference-draft, and bibliography hashes are unchanged. No simulations, staging, commits, or pushes. The TDR PDF was downloaded only to the session scratchpad for this check.

## Task 15 completed: limitations consolidated and prose tightened

Completed 2026-10-01. This was an editorial pass only; no finding, number, or figure changed.

### Hedge count (abstract through conclusions, comment lines excluded)

| Version | Original review pattern | "not documented" | Broad hedge pattern | Words (detex, including tables) |
| --- | --- | --- | --- | --- |
| Before Task 03 (original review) | 29 | 0 | 31 | 4,230 |
| Before Task 15 | 36 | 31 | 70 | 6,896 |
| After Task 15 | 27 | 20 | 50 | 6,671 |

The broad count fell by 29% (70 → 50) and "not documented" by 35% (31 → 20). Most of the remaining negations are physics statements, not scope hedges: a rigid bunch's field "does not by itself change" the dipole frequency, timescale separation "does not guarantee" adiabaticity, a sign expression "does not define" the separatrix orientation, and removal "does not determine" a particle's fate. The rest are flags that a reader of a single caption needs.

### Where each boundary is now stated in full

| Boundary | Full statement | Short qualifiers kept |
| --- | --- | --- |
| Inherited settings and convergence | Sec. 2.1 | §7.4 pointer |
| 43% denominator | Sec. 2.1 (loss populations) | Beside every use: abstract, Table 3, Sec. 6, §7.2, §7.4, conclusions |
| Feedback evidence qualitative (no suppression factor, stability margin, or optimum gains; 1.5–3 untested) | new §7.4 "Scope of the evidence" | conclusions pointer |
| Fixed-tune tests do not measure extraction | Sec. 4.1, last paragraph | conclusions clause |
| Model differences not assigned to one cause | §7.3, now listing space charge, lattice description, and extraction-channel treatment | Sec. 5 one-line pointer |
| Undocumented plot conventions | §7.4, one list | individual captions only |

### Removed or merged repeats

- Sec. 2.2 scope sentences, replaced by a pointer to §7.4.
- The Sec. 3 "qualitative agreement does not validate" sentence, moved into §7.3.
- The Sec. 4.1 emittance-definition sentence (caption and §7.4 cover it) and the action-normalization list.
- The Sec. 4.2 "within these limits", "qualitative interpretation", and 1.5–3 sentences (now in §7.4); the scope sentence about re-establishing the ramp; and the repeated space-charge-mixing caveat, now a back-reference to Sec. 4.1.
- In Sec. 5: the ramp-identity sentence (covered in Table 2 and Sec. 2.1), the transfer-function sentence (twice; kept in §7.1), the convergence clause, and the integration-step clause. The two criterion flags were merged into one, and the caption's 250-turn note is kept only in the text.
- In Sec. 6: the marker-color flag (the caption covers it); the three endpoint and denominator flags, merged into one sentence; the "cannot be combined with 1.2%" repeat, now pointing to Sec. 2.1; and the validation disclaimer.
- Table 3 per-cell "not documented" entries (normalization, selection, species), which the caption already covers.
- The Sec. 2.1 acceptance-normalization repeat, now pointing to Table 2.
- The Fig. 7 caption, whose two flags were merged.

### Copy edits

- **Terminology:**
  - "transit time" is used for the interval, and "arrival" only for the event (arrival criterion, arrival at the septum).
  - "arrival delays" in the abstract became "long transit times".
  - "spread of arrival times" became "spread of transit times".
  - "selected sample" became "scattered-particle sample returned from MARS" or "returned sample".
- **Definitions at first use:**
  - the Hockney solver (a fast-Fourier-transform Poisson solver);
  - 2.5D solvers (a transverse field scaled by the local longitudinal density), contrasted with 3D solvers;
  - the C-magnet (downstream of the Lambertson magnet).
- **Filler removed:** "the present study/feedback test", "within these limits".
- **Abstract:** the final two sentences were tightened.

Validation: `latexmk` with pdfLaTeX and BibTeX succeeded (22 pages; the build ran slowly on the host but completed normally in five passes). Labels are unique, and every reference and citation resolves, including the new `sec:limits`. The only warnings are the known ones. All pages were rendered and the contents still fit on page 1. All image, reference-draft, and bibliography hashes are unchanged. No simulations, staging, commits, or pushes.

## Task 13 completed: structure and synthesis discussion

Completed 2026-10-01. The author approved the proposed section order before any text was moved.

- **New order:**
  1. Introduction
  2. Published baseline and simulation cases
  3. Reduced resonance model
  4. RFKO response: chromatic mixing and spill feedback
     - 4.1 Fixed-tune excitation: emittance and centroid motion
     - 4.2 Spill regulation with feedback under quadrupole ripple
  5. Transit times after a tune step
  6. Transport of septum-scattered particles
  7. Discussion (7.1 Response chain for RFKO spill regulation; 7.2 Losses after septum interception; 7.3 Role of the reduced model)
  8. Conclusions
  9. Acknowledgments

  The RFKO studies are now contiguous, with the mechanism before its application. The generic "Particle tracking simulations" heading and its label `sec:tracking` were removed, the model became a method section, and every heading is descriptive.
- **Text moved, not rewritten.** A sorted-line comparison of the pre- and post-move source differs only in the headings and the two inserted sections. All labels were kept except `sec:tracking`; `sec:rfkoresp`, `sec:discussion`, `sec:chain`, `sec:lossdisc`, and `sec:modeldisc` were added. Figures renumber automatically in the new order: Figs. 1–2 fixed-tune RFKO, 3 feedback, 4–5 tune step, 6–8 scattering.
- **Linking edits for the new order:**
  - Abstract: sentence order now puts the fixed-tune result first, and the controller is named as PD.
  - Introduction: the list of studies and the roadmap follow the new order.
  - A short introduction was added for Sec. 4.
  - The fixed-tune opening now reads as a subsection.
  - The feedback subsection now refers back to the mechanism in Sec. 4.1.
  - The model section names the sections it serves.
  - Table 3 rows follow the section order.
- **Discussion (new; existing results only, no new number):**
  - 7.1 connects chromatic conversion (Sec. 4.1), the transit-time spread (Sec. 5), and ~100-turn averaging (Sec. 4.2) into a response chain. This explains the P-only oscillation and the derivative benefit qualitatively. It notes that the delay likely changes during the spill; whether the time-dependent P gain was meant to compensate is not documented.
  - 7.2 explains that septum interception is followed by transport that moves part of the associated loss around the ring. The 43% figure is confined to the returned sample.
  - 7.3 presents the reduced model as a common mechanism for fixed-point delays and scattering shear, not as a predictor.
- **Conclusions** rewritten in the new order as four compact findings plus a synthesis sentence pointing to Sec. 7, with the scope statement retained. The 43% qualifier and the 50 versus 100 µm distinction are intact.
- **Layout:** the longer contents list overflowed by one line onto an otherwise empty page 2. `\enlargethispage` made the title-page footnotes collide with the footer and was reverted. The contents are now set in `\small`, and page 1 is clean. The contents block remains a Task 16 decision.

Validation: `latexmk` with pdfLaTeX and BibTeX succeeded (22 pages; previously 21, from the Discussion). All 45 labels are unique and every reference and citation resolves. The only warnings are the known ones. All pages were rendered: figures appear in numerical order after their first references, and the title page was inspected at reading resolution. All image, reference-draft, and bibliography hashes are unchanged. No simulations, staging, commits, or pushes.

## Task 08 completed: captions and layout with existing figures

Completed 2026-10-01. Only TeX sizing, float placement, subcaptions, and caption wording were changed; no image was edited.

### Referenced asset inventory

All 8 figures and 14 referenced assets remain included. The eight unused `img/fig_bump*.png` files (dynamic-bump material covered by Ref. [2]) are untouched. All 22 image files, both reference drafts, and the `.bib` file have identical SHA-256 hashes before and after the task (25/25 OK). The effective resolution assumes a text width of 468.33 pt (6.48 in) from the build log.

| Fig. | Asset | Pixels | SHA-256 (first 12) | Width (text widths) | Effective dpi |
| --- | --- | --- | --- | --- | --- |
| 1 | `img/fig9.png` | 812×612 | `b53cfd2d2f33` | .9 | 139 |
| 2(a) | `img/fig_arrival1a.png` | 812×612 | `85cf337b5501` | .72 | 174 |
| 2(b) | `img/fig_arrival1b.png` | 812×612 | `d7cbe19ce3bc` | .72 | 174 |
| 3(a) | `img/fig_arrival2a.png` | 800×600 | `44b66b1d0084` | .48 | 257 |
| 3(b) | `img/fig_arrival2b.png` | 800×600 | `2a442e2ffe44` | .48 | 257 |
| 3(c) | `img/fig_arrival2c.png` | 800×600 | `5d2288f247f9` | .48 | 257 |
| 4 | `img/fig_beamloss1.png` | 475×419 | `bd957a04d7aa` | .62 | 118 |
| 5(a) | `img/fig_beamloss2a.png` | 812×612 | `0efdc3bc6c39` | .48 | 261 |
| 5(b) | `img/fig_beamloss2b.png` | 812×612 | `0445dbbe3949` | .48 | 261 |
| 6 | `img/fig_beamloss3.png` | 812×612 | `d702e75301de` | .7 | 179 |
| 7(a) | `img/fig_rfko1a.png` | 812×612 | `f87b6ca861b7` | .48 | 261 |
| 7(b) | `img/fig_rfko1b.png` | 812×612 | `9f1d3077ffc1` | .48 | 261 |
| 8(a) | `img/fig_rfko2a.png` | 812×612 | `0a8e9e811a18` | .48 | 261 |
| 8(b) | `img/fig_rfko2b.png` | 812×612 | `0affe01c6172` | .48 | 261 |

### Changes

- **Fig. 2:** panels are stacked vertically at 0.72 text width instead of side by side at 0.45. Estimated in-image tick labels rise from about 3.4 pt to about 5.4 pt, at 174 dpi. The figure now occupies its own float page. Subcaption (a) was renamed "Circulating-beam fraction" to match the plotted quantity.
- **Widths:** the other paired panels went from 0.45 to 0.48, and Fig. 3 from 0.47 to 0.48. Fig. 6 went from 0.75 to 0.70 and Fig. 4 (MARS) from 0.68 to 0.62, raising their effective dpi while the MARS labels stay at about 8 pt. Aspect ratios are preserved, because only widths are set.
- **Float order:** Fig. 7 moved from directly under the Sec. 5 heading to after the setup paragraph. It previously floated ahead of the heading onto the Fig. 6 page; every figure now appears after or near its first reference.
- **Captions rewritten to be self-contained and less redundant:**
  - Fig. 1: case name, trace colors, PD control, displayed range, undocumented normalization.
  - Fig. 2: stage rows and pause turns, spill normalization, color key.
  - Fig. 3: both models, histogram roles, time origin, fixed-point equation, axis ceiling, undocumented axis normalization.
  - Fig. 4: element list, bands, undocumented units.
  - Fig. 5: coordinate relation and units, sample and reference cluster, turn colors, undocumented overlays and loss-map legend.
  - Fig. 6: vertical-line initial condition, turn colors, no fields or removal.
  - Fig. 7: resonance drive off, color and line key, undocumented emittance definition and sampling.
  - Fig. 8: now called a phase-space density profile, consistent with the Sec. 5 derivation; undocumented units and reference, 10^7 factor, truncated range, aperture removal.

### Residual limitations (author or journal considerations; no replacement figures required by this task)

- Every asset prints below 300 dpi at its displayed size (118–261 dpi). An 812-px image reaches 300 dpi only at 0.42 text width or less, and the 475×419 MARS image only at 0.24 text width. Elsevier's usual guidance of at least 300 dpi for halftones, and more for line art, would need the original vector or higher-resolution plots if a journal enforces it. No upsampling was done.
- In-image tick labels in the side-by-side panels are about 3.5 pt at print size. Some original images have overlapping tick labels at panel boundaries, for example "0.89"/"1500" in Fig. 2(a) and the "0.0"/"2.0" pairs in Fig. 1. These are baked into the pixels and remain.
- Undocumented plot elements (overlays, loss-map markers and units, MARS axis units, hatted centroid labels, emittance and action normalizations) are flagged in the captions, as recorded under Task 11.

Validation: `latexmk` with pdfLaTeX and BibTeX succeeded (21 pages; previously 20, because of the enlarged Fig. 2). Labels are unique and every reference and citation resolves. The log has no float or overfull warnings except the known CAS overlay. BibTeX shows only the two known warnings. All 21 pages were rendered; pages 11 (Fig. 2) and 18 (Figs. 7–8) were inspected at reading resolution with no clipping or stretching. No simulations, staging, commits, or pushes.

## Task 07 completed: scattering transport and loss accounting

Completed 2026-09-29 from the existing text, figures, and the reference draft `beamstudy.tex`.

- **Opening.** Rewrote the two opening paragraphs:
  - The 50 µm (present) and 100 µm (Ref. [2]) foils are contrasted once, with a pointer to Table 2.
  - The published hit/cross loss is described as motivation, not normalization.
  - Scattering is stated to change angle and hence action (Eq. 2), and the four possible fates are listed.
- **Three-stage workflow** is now a numbered list: primary interception (Synergia2 ESS1 aperture, particles removed from the primary calculation), material transport (MARS, ESS1 to C-magnet, 50 µm foils, secondaries), and ring tracking (Synergia2 on the selected MARS output recorded at the C-magnet). The undocumented species, number, and weights are stated beside the denominator. The Fig. 4 description now follows the list, and the ESS2 no-zero-loss caveat is retained.
- **Fig. 4 caption** now states that the axis units are undocumented. The native-resolution check confirmed the upper circulating band, the lower outgoing band, and the element labels.
- **Fig. 5(a) interpretation added.** The initial sample lies on a vertical line at the septum because thin-foil scattering changes angle, not position; in (x, αx+βx') coordinates an angle change Δx' is a vertical shift βΔx' (follows directly from the coordinate definition). The reference group is identified as the compact cluster at the lower end. The three-turn return to the septum region explains repeated extraction or interception chances and the losses near the septa. The undocumented C-magnet-to-ESS1 back-transformation is flagged.
- **43% audit.**
  - The denominator is now "the returned scattered-particle sample".
  - The original draft's "survived and extracted" is attributed to the original study, and the text states that the tracking duration and extraction criterion are undocumented, so "not lost within the tracked interval" and "extracted" cannot be distinguished.
  - Whether the reference particles enter the denominator is flagged.
  - The no-combination and no-injected-beam statements (1.2%) are kept in one place. An `AUTHOR CHECK` was added.
- **Shearing (Fig. 6).** A vertical line has a common X but different X' and hence different H_K (Eq. 5), so it shears. Some particles leave along the separatrix branches. The V-shape in Fig. 5(a) is identified as mixing the reference group and the scattered population. The paragraph is kept qualitative, with no validation of scattering, losses, or efficiency.

Validation: `latexmk` with pdfLaTeX and BibTeX succeeded (20 pages). Labels are unique, and every reference and citation resolves. The only warnings are the known ones. Pages 13–17 were inspected; Fig. 7 now floats onto the Fig. 6 page ahead of the Sec. 5 heading, which is left for Task 08 placement. All image, reference-draft, and bibliography hashes are unchanged. No simulations, staging, commits, or pushes.

Open for the author (existing High row, "Scattering handoff and 43% denominator"): tracking duration and extraction criterion; reference particles in the denominator; species, number, and weights; the C-magnet-to-ESS1 transformation; loss-map legend; Fig. 4 axis units.

## Task 06 completed: tune-step and transit-time evidence

Completed 2026-09-29 from the existing figures and text only.

- **Two definitions separated.** The ideal single-particle transit time (from instability to septum, with no common origin) is now distinguished from the diagnostic's elapsed time from the common restoration step. The two nearly coincide for particles released by the step. For particles already in transit, which the undocumented selection may include, the elapsed times are shorter than their full transit times. The arrival criterion is noted as undocumented for both codes.
- **Protocol stated consistently.** The pause starts at turns 2,000, 15,000, and 25,000, lasts about 300 turns, and is followed by a step to the uninterrupted-ramp values and a hold of about 500 turns. The shrinking stable region (Eq. 6) and growing fixed-point-to-septum distance are now tied to the stages. "Same initial macroparticle population" was reworded to "one simulated beam".
- **Fig. 2 explained.**
  - Burst size follows how strongly the pause suppresses extraction: the spill nearly stops at the early stage but continues at a reduced rate later. The original draft's "thicker shell" explanation is attributed to it.
  - The burst delay and duration are linked to the Fig. 3 transit-time distribution.
  - The caption now states the spill normalization (ideal uniform spill equals unity, documented in the original draft).
- **Fig. 3 explained.**
  - Caption: the top histogram shows common starting coordinates, the right histograms show per-model transit times, and times are measured from restoration.
  - Text: short times fall on discrete levels, explained by the particle returning to the septum side only every third turn. Across stages the fixed-point line moves toward x = 0, the starting coordinates concentrate there, and the longest times shown increase.
- **Mechanism restated positively.** Long times come from passing close to an unstable fixed point, and they increase at later stages. The residual mention of the rejected inverse-distance law was deleted. Model differences are still not assigned uniquely to space charge. A window caveat was added: the hold is about 500 turns and the plot ends at 250 turns, so the longest delays may be omitted.
- **Implication paragraph.** The arrival-time spread (a few turns to more than one hundred, lengthening later) makes tune or RFKO changes act gradually, which contributes to the delayed response in Sec. 3. No delay constant or transfer function is extracted.
- **Review-only pixel check** of the discrete levels. Marker blobs in the short-transit region of Fig. 3 sit near 3.2, 5.9, 9.6, 15.9, 18.4, and 22.5 turns in (a), near 3.3, 5.8, and 9.6 in (b), and near 3.3, 6.0, and 8.3 in (c), at 1.32 px per turn with markers about 4 px wide. This is roughly a 3-turn spacing within about ±1 turn of marker blur. Only "discrete levels" appears in the manuscript, with no spacing value.

Validation: `latexmk` with pdfLaTeX and BibTeX succeeded (20 pages). Labels are unique, and every reference and citation resolves. The only warnings are the known ones. Pages 9–13 were inspected. All image, reference-draft, and bibliography hashes are unchanged. No simulations, staging, commits, or pushes.

Open for the author (existing rows): the selection criterion and per-stage counts; the arrival criterion; the exact restoration values; the post-hold protocol; and whether any transit times exceeded 250 turns.

## Task 05 completed: RFKO results and interpretation

Completed 2026-09-29 using the existing figures and text only. No metric was derived for the manuscript, and no figure was changed.

- **Sec. 3 (feedback), restructured as controller → observation → interpretation → implication:**
  - Proportional-only oscillation is marked "(not shown)". The PD choice is attributed to the original study, with its comparison criterion and gains undocumented; the word "most favorable" was removed.
  - The three traces are described qualitatively: a start-up transient, small fast fluctuations without ripple, larger quasi-periodic sawtooth-like excursions with ripple, and smaller residual modulation plus isolated spikes with feedback.
  - Residual spikes and P-only oscillation are interpreted as delayed correction. The ~100-turn averaging combines with transit times ranging from a few turns to more than one hundred turns, a qualitative reading of the existing Fig. 3 axis. The derivative term is described as a standard damping means [pid].
  - The implication is stated positively and bounded; the 1.5–3 factor from Ref. [2] is kept separate as untested.
- **Sec. 5 (fixed-tune RFKO):**
  - Added the dephasing mechanism: identical kicks change only the centroid without a tune spread; a tune spread filaments the coherent motion into internal area. The chromatic spread C_x δ is of order 1e-3 for C_x = 1 (arithmetic from Table 1).
  - Stated that a rigidly displaced bunch carries its direct space-charge field with it, consistent with the finding in [ipac11].
  - Added a caveat: the chirp is said to cover the tune spread, so C_x = 0 and C_x = 1 may differ in excitation spectrum as well as in chromaticity.
  - Fig. 7 is interpreted as a wandering, random-phase coherent response at C_x = 0 and as phase mixing at C_x = 1. The "RFKO not absent at C_x = 0" point is kept, and the aperture caveat for the late slowing is retained.
  - Fig. 8 diagnostic identified: if f is the density in √I_x, then f/√I_x is proportional to the phase-space density at amplitude √(2I_x), and for a Gaussian beam it is Gaussian in √I_x. Checked by sampling 2×10^6 Gaussian particles (maximum relative deviation 1.8%, statistical).
  - Implication added: nonzero chromaticity converts excitation into growth of individual amplitudes, which is relevant near the separatrix and supports the C_x = 1 choice in Sec. 3. The resonance drive is off, so there is no extraction measure.
- **Review-only pixel check.** The Fig. 1 green trace's largest spike reaches about 1.53, against a red maximum of about 1.41 (75 px per unit, first ~700 turns excluded). This supports the wording "the largest of these slightly exceed the largest excursions without feedback". No number was added to the manuscript.

Validation: `latexmk` with pdfLaTeX and BibTeX succeeded (19 pages). Labels are unique, and every reference and citation resolves. The only warnings are the known CAS overlay and the `pimms`/`wcm` years. RFKO pages 5–7 and 15–17 were inspected. All image, reference-draft, and bibliography hashes are unchanged. No simulations, staging, commits, or pushes.

Open for the author (added to existing rows): the PD gain values and the selection criterion; the chirp bandwidth at C_x = 0 compared with C_x = 1; and the ripple-frequency question from Task 11.

## Task 11 completed: figure–text discrepancies

Completed 2026-09-29. The image files were inspected at native and 2× zoom. Pixel-level readings (listed below) were used only as evidence for author questions and do not appear in the manuscript as results. Image bytes are unchanged.

| # | Finding | Resolution in `beamstudy-mod.tex` | Still open for the author |
| --- | --- | --- | --- |
| 1 | The Fig. 1 middle trace repeats about every 1,650 turns. Evidence: autocorrelation peak r ≈ 0.7 at 1,646 turns and FFT peak at 1,590–1,650 turns, measured from the red trace pixels (axis 5,000 turns per 158 px); this is about 2.8 ms, or ~360 Hz, the 6th harmonic of 60 Hz. One 60 Hz period is 9,834 turns (from T_rev = 1.6948 µs). The original draft does not say "sinusoidal", a word introduced by an earlier revision. | Removed "sinusoidal" and stated that the waveform is unspecified. Replaced "components at harmonics" with a qualitative statement that the dominant modulation repeats several times within one 60 Hz period (about 9,830 turns, arithmetic from printed values), so the relation between waveform and spill spectrum is not established. Kept 60 Hz. Added an `AUTHOR CHECK`. | Was the ripple 60 Hz or 360 Hz, and what were its waveform, the modulated quadrupoles, and their phases? |
| 2 | The Fig. 1 axis ends at about 20,000 turns (grid calibration). | The caption states that the traces cover about the first 20,000 turns of the 31,795-turn spill, and names the trace colors. | Why do the runs end near turn 20,000? |
| 3 | Transit times rise monotonically toward x = 0, not toward the fixed-point line. | Rewrote the observation: short, matching times between the septum and the fixed-point line, rising toward x = 0, with the longest times beyond the line. Added the reduced-model mechanism (passage along the separatrix past an unstable fixed point), which follows from Eq. (6) and the flow on the separatrix sides. | — |
| 4 | "Full tracking broader" is not uniform: the reduced-model (red) points reach about 230–245 turns at the middle and late stages. | The text now says Synergia2 scatters more widely at a given coordinate and is generally slower, whereas RK4 reaches the longest times at the middle and late stages. | — |
| 5 | The axis stops at 250 turns, while the hold is about 500 turns. | The caption states the plotted limit and that points beyond it are undocumented. | Were any transit times above 250 turns? |
| 6 | After restoration, the red case extracts more slowly; the plots extend about 1,000 turns past restoration; the burst lags the restoration line. | The text describes the delay and the persistent difference (expected while the strengths are held), and states that the displayed interval exceeds the 500-turn hold and that the post-hold protocol is undocumented. | Hold length and protocol after the hold. |
| 7 | Figs. 5(a) and 6 have an unexplained orange triangle and red circle. | The captions identify the purple septum line (documented in the original draft) and flag the other overlays as undocumented. Their consistency with the Eq. (6) separatrix is recorded in the Task 04 section but not asserted in a caption. | Define the orange lines and red circle. |
| 8 | Loss-map legend and axes are missing; markers also appear in other arcs. | The caption identifies the gray beamline and beam arrow and flags the marker colors and axis units. The text attributes the "septa, first arc, mid-straight" summary to the original analysis and notes the other markers. | Marker meanings (red versus orange, stars) and axis units. |
| 9 | Fig. 7(b) uses hatted axes and coarse sampling. | The caption notes the original x̂ and x̂' labels and that the sampling interval is undocumented. | Definition of the hat notation; sampling interval. |
| 10 | At C_x = 1, emittance growth slows late in the run. | The text notes the slowing and that aperture removal may contribute. | — |
| 11 | The Fig. 8 range is truncated at √I_x = 2 and the plot carries a 10^7 scale factor. | The caption states both. | — |

Validation: `latexmk` with pdfLaTeX and BibTeX succeeded (18 pages; previously 17, from the longer captions and text). Labels are unique and every reference and citation resolves. The only warnings are the known CAS keyword overlay and the `pimms`/`wcm` years. All pages were rendered and inspected. Images, reference drafts, and the `.bib` file keep their pre-edit hashes. No simulations, staging, commits, or pushes.

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
| High | Geometry and inherited baseline | Confirm the 50 micrometre scattering foil against the MARS deck; the prior model consistently uses 100 micrometres. Identify the actual lattice, ramp, bump waveform, space-charge configuration, and acceptance used in each present case. The new scope table distinguishes the stated values without claiming a matched configuration. Also confirm the beam momentum actually used in the Synergia2 input decks; Table 1 now gives the corrected nominal 8.889 GeV/c (Task 22). State whether the ripple-and-feedback and scattering ring-tracking cases included space charge; the manuscript now claims it only for the fixed-tune and tune-step cases (Task 24). |
| High | Quadrupole ripple amplitude | The original text says both “peak-to-peak” and “±0.5%.” The revision retains ±0.5% as an amplitude provisionally. Confirm from the input whether the modulation was 0.5% amplitude (1% peak-to-peak) or 0.5% peak-to-peak. Record which quadrupoles were modulated and their relative phases. |
| High | Controller reproducibility and performance | Provide the discrete update law, proportional-gain schedule, derivative gain/filter, averaging and update intervals, latency, amplitude limits, and initial conditions. Define spill normalization and binning. Report an RMS/ripple-spectrum or duty-factor comparison with uncertainty and the relevant spill window before making quantitative suppression or optimality claims. State whether the RFKO loop's actual delay was measured; the tune-step diagnostic only motivates a delay mechanism (Task 19). |
| High | Transit-time sample and tune-step definition | Confirm that restoration means the uninterrupted-ramp value at the restoration turn, the exact step sizes, the start-time convention, whether already-unstable particles are excluded, the particle count at each stage, and the extraction criterion. The draft's approximately 500-turn observation interval is preserved; test for unobserved tails. Also state the RK4 integration step and the arrival-detection cadence in both codes; these determine whether the discrete short-transit levels are physical or sampling artifacts (Task 19). |
| High | Space-charge comparison and numerical convergence | The prior publication reports a 64×64×128 Hockney grid and 240 kicks/turn; confirm the actual settings, Synergia2 version, lattice, initial distributions and integration steps for the present cases rather than assuming inheritance. Repeat otherwise matched tracking with space charge on/off. Provide RK4 step refinement and Hamiltonian conservation checks at fixed parameters. Sampling every three turns does not specify the RK4 integration step. |
| High | Scattering handoff and 43% denominator | Document MARS version/physics settings, species selected for return tracking, number and statistical weights of particles, coordinate/reference-orbit and momentum transforms, apertures, tracking duration, and extraction/loss criteria. Confirm whether the extra circulating reference particles enter the reported percentage. Do not interpret 43% as total ring loss or a radiation-dose prediction. Also state whether the C-magnet-to-ESS1 return mapping is an inverse transport, a coordinate conversion, or a reference-plane assignment, and whether encounters of the scattered particles with the septum foil or extraction field were recorded on later turns (Task 20). |
| High | Emittance, action, and aperture conventions | Define geometric versus normalized emittance, rms versus 95% values, whether the diagnostic subtracts the centroid, the definition/units of `I_x`, and the normalization of `f(sqrt(I_x))`. Specify exactly how the 20 pi mm mrad acceptance is applied. State whether the action diagnostic of the fixed-tune profile figure is referenced to the orbit or the centroid, and whether its sampled times correspond to those of the emittance/centroid figure (Task 18). The plotted values alone cannot establish these conventions. |
| High | Figure axis units | The transit-time figures say “normalized x (mm)” whereas `X=x/sqrt(beta)` has square-root-length units when beta and x use consistent length units. Recover the plotting transformation before relabeling. The loss plots use `(x, alpha x + beta x')` in mm and are not the canonical `(X,X')` pair; their captions now distinguish this. Also supply loss-map axis units/legend and MARS geometry axis units. |
| Medium | RFKO excitation settings | Provide the center-frequency/sideband convention, numerical chirp bandwidth at each chromaticity (especially Cx=0; needed to separate chromaticity from bandwidth in the fixed-tune comparison, Task 18), random-phase distribution, seed policy, and kick calibration connecting 500 W with approximately 1 microradian. |
| Medium | Momentum spread | Clarify whether 0.0016 is rms, a half width, or another measure. It has not been silently relabeled rms. |
| Medium | Reduced-model coefficient | Recover the lattice-to-resonance coefficient and phase convention, observation-point Twiss parameters, and values of effective sextupole strength and tune detuning for each comparison. The algebraic correction does not prove the original numerical implementation used the same convention. |
| Medium | Internal citations and source attribution | MARS Document 3697-v1 metadata now follows the supplied publication’s Ref. [19]: N. Mokhov, V. Nagaslaev, I. Rakhno (2010). Verify the original report and confirm it is the actual calculation used. Monitor Documents 3627-v4 and 3625-v1 remain locally recovered references. The Pullia thesis title page was checked in Task 09 (Lyon 1, French title; entry corrected). |
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
