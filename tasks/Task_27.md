# Task 27 — Recover the essential simulation records

Status: Done  
Priority: P1 (decisive for acceptance)  
Owner: Author (record retrieval); editor (incorporation)  
Depends on: None  
Source: `reviews/review1.md` concerns 1–4 and closing recommendation; `reviews/review2.md` major concerns 1–2 and "What would most improve the odds" items 1 and 3

## Scope

The original Synergia2, MARS, and RK4 input decks, run logs, controller code, diagnostic scripts, and particle-accounting files for the five simulation cases. Incorporate recovered facts into `beamstudy-mod.tex` and shrink Appendix A (`app:records`) accordingly.

Both reviews identify this as the decisive step: "Recovering the essential records—not another round of language polishing—is the decisive step" (review 1). This is retrieval of existing documentation, not new simulation, so it is within the project's no-new-simulation boundary.

## Records to recover (from Appendix A / Table 4 and the REVIEW author checks)

| Case | Highest-value items |
| --- | --- |
| All Synergia2 cases | Lattice version; reused ramp, bump, and space-charge settings; whether space charge was on in the feedback and scattering ring-tracking cases; input-deck beam momentum |
| Ripple and feedback | Applied ripple **frequency** (60 versus ~360 Hz, see Task 28), amplitude convention, waveform, modulated quadrupoles; controller law, gains and gain schedule, update interval, delay; spill normalization; why the runs end near turn 20,000 |
| Fixed-tune RFKO | Emittance definition (rms or 95%, centroid reference); action-diagnostic reference, units, normalization; acceptance convention; chirp sweep period and bandwidth for each chromaticity; kicker calibration |
| Tune step | Selection and arrival criteria; restoration values; post-hold protocol; per-stage particle counts; transit times beyond 250 turns |
| Reduced model | Integration step and detection cadence; resonance coefficient values and phase; Twiss parameters at ESS1 |
| Septum scattering | Returned-sample size, species, and statistical weights; whether reference particles enter the 43% denominator; tracking duration; extraction criterion; C-magnet-to-ESS1 mapping; MARS version; confirmation of the 50 µm foils |

## Work

1. The author locates the records (local archives, Fermilab DocDB, collaborators) and lists what was found in REVIEW, with file provenance.
2. For each recovered item, state it in the manuscript as a fact with its source, remove the corresponding entry from Table 4, and delete the matching `AUTHOR CHECK` comment.
3. Do not infer any value not present in the records. Unrecovered items stay in Appendix A.

## Acceptance criteria

- [x] REVIEW lists each item as recovered (with provenance) or confirmed unrecoverable.
- [x] The manuscript states every recovered item as a sourced fact, and Table 4 lists only unrecovered items.
- [x] No figure or reported result changes as part of this task; any value correction is recorded with its source.
- [x] Both builds pass, with resolved references.

## If records cannot be recovered

Record that outcome in REVIEW and proceed to Task 31 (scope and venue reassessment). Review 1 warns that further qualification alone "may leave too little substantiated material for a full research article".

## Completion record

Completed: 2026-10-01 (editor part; the remaining retrieval is the author's).

- The records were found in local backups of the Fermilab cluster (`~/backups/TeVCluster_Backup-*`, `~/backups/tune_ramp`) and in `~/Work/projects/mu2e`. They include run options and logs, the Synergia2 driver and ramp modules, analysis and plotting scripts, the MARS output file, and the Synergia2 source of that period. Five figure files are byte-identical to archived plots, and Fig. 3 is identical to a figure of the 2014 draft of Ref. [2]. REVIEW ("Task 27 completed") lists every item with its file provenance and status.
- **Recovered and stated in the manuscript:**
  - simulation momentum (8.827 GeV/c), lattice file, and space-charge solver (two-dimensional, 64×64×128, 240 steps/turn);
  - the acceptance convention (geometric Courant–Snyder limit) and kicker calibration (1.1 µrad);
  - the fixed-tune emittance and action definitions (centroid-referenced), and the explanation of 0.28 (16π normalized);
  - the ripple waveform (three-phase rectified 60 Hz, 360 Hz fundamental) and the controller structure;
  - the tune-step protocol (320-turn pause, single step, hold); the selection (extraction within 180 turns, same three-turn phase) and arrival criteria;
  - the RK4 step and cadence, the resonance coefficients, and the ESS1 Twiss parameters;
  - the returned-sample size (127,975), the tracked subset (2,402), the loss denominator, the ring-tracking settings, the plot overlays, and the loss-map markers.
- **Not found:**
  - the 30,000-turn fixed-tune runs that were plotted (related 20,000-turn runs differ);
  - the ripple amplitude and gains of Fig. 3;
  - the output of the ring-tracking run (duration, reference particles);
  - the MARS input and version (foil thickness);
  - the script that converted the MARS output.
  These remain in Appendix A and in the author questions in REVIEW.
- No figure or reported result changed. The 43% value is kept; its denominator (the 2,402-particle tracked subset, according to the archived script) is the leading author question, and the abstract and highlights are unchanged pending confirmation.
- Both builds pass (27 and 26 pages); labels and references resolve; BibTeX reports 0 warnings.
