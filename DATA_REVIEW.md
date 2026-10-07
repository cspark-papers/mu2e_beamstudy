# Review of the archived simulation data in `data/`

Reviewed: 2026-10-07; updated: 2026-10-08 after the local data and task-acceptance audit. Scope: read-only inspection of the untracked, gitignored `data/` directory (Synergia2 simulation records). No simulation, tracking, RK4 integration, or plotting script was run, and no file in `data/`, `img/`, or the manuscript was changed. The checks were limited to reading option files and logs, counting files and rows, comparing SHA-256 hashes, HDF5 metadata and saved diagnostic reads, archive-member inspection, and the previously recorded least-squares fit between two archived sample files. Figure feasibility below is a source/input audit, not a regeneration test.

## 1. Contents of `data/`

- Recursive enumeration finds 12,833 regular files totaling 8,006,407,044 bytes (8.01 GB decimal; 7.46 GiB), dated mainly 2012–2015. The earlier `rg --files --hidden` inventory returned 12,176 files / 7.93 GB because it honored ignore rules. Neither count represents independent simulation runs. There are 376 `alloptions` files.
- `data/tune_ramp/` (5.8 GB) holds the run directories, analysis and plotting scripts, and `img/` (261 PNGs) that Task 27 lists for `~/backups/TeVCluster_Backup-Nov2020/data/results/mu2e/tune_ramp/`. That backup path is not present on this machine, so byte identity with the Task 27 archive was not verified.
- Other directories are older or unrelated studies: `simple/run.*` (2013), `hibeta/` (2015), `240/`, and lattice caches (`lattice_cache_*`).
- Four files are dated 2025-11-05 (`data/mu2e_aperture.py`, `tune_ramp/options.py`, `tune_ramp/phasespace_apertures.py`, and a `.pyc`), so this copy has been edited or used recently.
- The lattice gives `momentum := 8.827385` GeV/c, as recorded in Task 27.
- Of 477 `.h5` files, 476 open for metadata inspection. `tune_ramp/old_bumps2/bump.30/lattice_deposited_charge.h5` fails the HDF5 signature check; it must not be used as a valid output without recovery. This is a metadata check, not validation of every dataset or the simulations. None of the hidden `.nfs*` files inspected has an HDF5 signature.
- All 121 `.tgz` archives were read without extraction; their member names reveal no additional forced-particle, emittance, MARS-sample, or Fig. 3 inputs.

## 2. Findings

### 2.1 Byte-identical figure sources

Every manuscript asset except `fig9.png` (Fig. 3) and `fig_beamloss1.png` (Fig. 6) has a byte-identical copy in `data/tune_ramp/img/`. Task 27 matched the following only by script layout; they are now exact matches:

| Asset | Figure | Identical archived file | File date |
| --- | --- | --- | --- |
| `fig_arrival1a.png`, `fig_arrival1b.png` | 4 | `20140320-06.png`, `20140320-07.png` | 2014-03-21 |
| `fig_arrival2a/b/c.png` | 5 | `20150109-00/01/02.png` | 2015-01-10 |
| `fig_beamloss2a.png` | 7(a) | `20141121-04.png` (also `20141126-00`, `20141211-00`) | 2014-11-22 |
| `fig_beamloss3.png` | 8 | `20141121-05.png` (also `20141126-01`, `20141211-01`) | 2014-11-22 |

`fig_rfko1a/b`, `fig_rfko2a/b`, `fig_beamloss2b`, and `fig_bump*` are byte-identical to same-named files in `img/`, as Task 27 found.

### 2.2 Fig. 4 predates the archived tune-step runs

The Fig. 4 PNGs are dated 2014-03-20 (filename) and 2014-03-21 (file time). Every archived `arrival_time.00`–`19` run directory dates from 2014-10-30 to 2014-11-26. The restoration lines in Fig. 4 (turns 2,320, 15,320, 25,320) match the archived protocol (`stop2 = stop1 + 319`), but the curves do not all match the archived logs. Fractional beam intensity (macroparticles / 500,000) from the uninterrupted chain `arrival_time.06` → `.07` → `.08`, compared with values read from the blue curve of Fig. 4 (raster reading, review evidence only):

| Turn | Log | Fig. 4 (approx.) | Agreement |
| --- | --- | --- | --- |
| 1,500 | 0.9504 | 0.950 | yes |
| 2,000 | 0.9339 | 0.935 | yes |
| 3,000 | 0.9018 | 0.904 | yes |
| 14,500 | 0.5401 | 0.546 | no |
| 15,000 | 0.5244 | 0.530 | no |
| 24,500 | 0.2259 | 0.230 | no |
| 25,000 | 0.2098 | 0.214 | no |

Conclusion: the available comparison does not establish that the archived runs produced Fig. 4, and the later-stage discrepancies prevent treating them as its verified plotting inputs. File dates and approximate raster comparisons alone do not prove that every possible run chain is excluded. Fig. 4 regeneration with unchanged data therefore remains unverified. The Task 29 statement that plotting data "survive at most for Fig. 4 (`arrival_time.*`…)" must not be read as confirmation that its original inputs have been recovered.

### 2.3 Fixed-tune runs (Figs. 1–2)

| Runs | C_x | Power | Last turn | ε at turn 20,000 |
| --- | --- | --- | --- | --- |
| `growth.00`, `.01` | 0, 1 | 25 W, no RFKO | 20,000 | 0.2839, 0.2840 |
| `growth.02`, `.03` | 0, 1 | 25 W, linear chirp | 20,000 | 0.2860, 0.4091 |
| `growth.04`, `.05` | 0, 1 | 500 W | 20,000 in saved HDF5 | 0.3014, 2.2206 |
| `growth.06`, `.07` | 0, 1 | 500 W | 20,000 in saved HDF5 | 0.3014, 2.2206 |
| `agrowth.04`, `.05` (2014-05-21) | 0, 1 | 500 W | 20,000 | 0.3014, 2.2206 |
| `old_growth/growth.06`–`.11` (2014-05-17) | 0, 1 | 25 / 500 W | 10,000 | — |

The values above for `growth.00`–`.07` and `agrowth.04`–`.05` were read from existing `emittance_10000.h5` datasets (`turn`, `tot`); they are archived diagnostics, not newly calculated beam results. `growth.04/emittance.h5` is a separate, coarser product ending at turn 19,000. Absence or incompleteness of `emittance.dat` does not mean all diagnostic data are missing. However, the forced-particle HDF5 snapshots needed to reconstruct the centroid and action-profile panels are absent.

All use `norm_emit = 16π` and `max_turns ≤ 20001`. The plotted curves run to 30,000 turns and reach about 2.45 at turn 20,000, so the plotted runs are still missing.

### 2.4 Ripple and feedback (Fig. 3)

- No `mu2e_spill.h5` file exists anywhere in `data/` (the input of `mu2e_spill_rfko.py`, which plots spill rate with quadrupole ripple).
- Among 182 `ramp_modules.py` and 120 `profile_ramp_modules.py` files, the audit finds 301 explicit `A` assignments, all `0.000`; one ramp module has no such assignment. Zero initial gain variables do not establish that an entire feedback run had zero gains: the code can subsequently assign nonzero controller gains. The plotted-run gains remain unverified.
- `old_runs/tune.*` (2013) and `old_runs/tdr.*` (Nov 2013–Mar 2014) are extraction or feedback runs without a recorded ripple amplitude.

The ripple amplitude, controller gains for Fig. 3, and the Fig. 3 runs remain unrecovered.

### 2.5 Scattered-particle sample and the C-magnet → ESS1 conversion

- `CircBeamCM.dat` (MARS output, 2014-09-09) and `CircBeamCM_transformed.dat` (2014-11-19) each have 127,975 rows.
- They are related by an exact affine map (maximum residual about 5×10⁻¹⁴). With x in metres (the MARS file stores x and y in cm):

  x_t = −1.015187 x − 0.486765 x′ − 1.4465 mm
  x′_t = 4.73850×10⁻⁴ x − 0.984813 x′ + 45.13 µrad

  The linear part has determinant 1.000000 and trace −2.000000 (symplectic). y is converted from cm to m; y′ and the energy column (7.950–8.000 GeV) are unchanged.
- The script that applied this map was not found. `mu2e_mars_tracking.py` and `mu2e_mars_phasespace_multi.py` then apply a second matrix, `tmap = [[−1.10595288, −8.26894362], [−0.03679479, −1.17930343]]` (determinant 1), before display.
- Exactly **2,402** particles have transformed x > 0, matching the hard-coded denominator `macro_particles = 2402 #127975` in `mu2e_mars_losses.py`.
- The ring-tracking run directories (`mars.00`–`mars.24`) are listed in `tune_ramp/space_usage.txt` (2016-06-08) but are absent, so the tracking output, its duration, and the treatment of the reference particles remain unrecovered.

## 3. Which figures can be regenerated

**No complete current manuscript figure is verified as regenerable from saved outputs without new tracking.** A byte-identical PNG confirms image provenance; it does not supply the numerical data needed for a vector or higher-resolution export. Upsampling or tracing the PNG would not recover those data. The author has not authorized any figure change, and RK4 integration remains prohibited.

| Fig. | Asset(s) | Surviving inputs | Feasibility for the complete existing figure |
| --- | --- | --- | --- |
| 1 | `fig_rfko1a/b.png` | Identical PNGs; related 20,000-turn emittance HDF5 diagnostics | **Not currently reproducible.** The plotted 30,000-turn run is missing, and the centroid snapshots are absent. Related-run diagnostics can support a different plot only under a separate scope change. |
| 2 | `fig_rfko2a/b.png` | Identical PNGs; action-analysis scripts | **Not currently reproducible.** Forced-particle snapshots and the plotted runs are missing. |
| 3 | `fig9.png` | Related controller/ripple code; older feedback run records | **Not currently reproducible.** The plotted ripple/feedback outputs and `mu2e_spill.h5` are absent; amplitude and plotted-run gains remain unknown. |
| 4 | `fig_arrival1a/b.png` | Identical PNGs; `arrival_time.*` logs and kick records; `mu2e_arrival_time-05.py` | **Unverified.** Related archived runs can be replotted, but have not been matched to all displayed curves. Their later-stage discrepancies prevent claiming an identical-data regeneration. |
| 5 | `fig_arrival2a/b/c.png` | Identical PNGs; extraction/kick records; `mu2e_transit_time2.py` | **Not currently reproducible.** The restoration-turn forced-particle HDF5 snapshots are absent. The script also computes the reduced-model points by RK4 integration; saved outputs for those points were not located. |
| 6 | `fig_beamloss1.png` | Existing manuscript raster only; no exact copy or MARS deck found here | **Not currently reproducible.** Original rendering/trajectory inputs are missing; a new MARS run is outside scope. |
| 7(a) | `fig_beamloss2a.png` | Identical PNG; both MARS sample files; display matrix and Twiss settings in `mu2e_mars_phasespace_multi.py` | **Initial scattered distribution only can be replotted from saved data.** The complete panel also requires the missing `mars.*` forced-particle snapshots and reference-particle records. |
| 7(b) | `fig_beamloss2b.png` | Identical PNG; loss-map script and lattice | **Not currently reproducible.** The corresponding ring-tracking `lattice_deposited_charge.h5` and extraction output are missing. Files from other runs cannot substitute for them. |
| 8 | `fig_beamloss3.png` | Identical PNG; MARS sample; related `mu2e_mars_tracking.py` with model parameters | **Conditional reconstruction only, not verified regeneration.** The script computes trajectories rather than reading saved trajectory outputs. It calls RK4 with `t = arange(0, 5, 1)` and displays computed states; this is not merely a plot export. Its exact figure-producing variant is unverified. |

Thus the saved initial distribution in Fig. 7(a) is the only identified part of a current figure that can be replotted directly from its surviving numerical sample. The related RFKO emittance and tune-step spill outputs can also be plotted, but such plots must not be presented as regenerations of the current manuscript figures. Fig. 8 is the clearest candidate for a reconstruction if the author later changes both the figure and tracking boundaries; identical content is not guaranteed.

No regeneration was attempted. The previously recorded resolution and lettering shortfall remains a submission consideration; this audit does not establish compliance or justify replacing any panel.

## 4. Effect on the task backlog

The inspection completes a **data inventory and figure-feasibility audit**. It does not complete new manuscript revisions, figure production, or submission checks. Only `DATA_REVIEW.md` is updated in this change; task files and the task index retain their existing statuses.

| Task | What can be marked done, and what remains |
| --- | --- |
| 02–26 | Already Done within their editorial scope; no status change follows from finding additional records. Figure-quality and author-data limitations remain. |
| 27 — Record recovery | Already **Done with unresolved items recorded**, not complete recovery of every scientific input. The local inventory, exact image matches, saved HDF5 diagnostics, and 2,402-row selection check are complete addendum evidence. Integrating this addendum into REVIEW and updating any affected manuscript disclosures remains separate work. The affine fit describes a relation between files; it does not recover the physical derivation or author validation of the return map. |
| 28 — Numerical inconsistencies | Already **Done**. The checked momentum, emittance diagnostics, and subset count corroborate the recorded sources; they do not resolve the author's nominal-versus-run momentum choice or confirm the reported 43% loss count. |
| 29 — Publication-standard figures | **The feasibility audit is Done.** The task can be recorded as **Closed through fallback: figures retained, production limitation unresolved**, because the author already declined changes and REVIEW already records the blocker. It must not be marked Done against the figure-production acceptance criteria. Before synchronizing that fallback status, correct the Fig. 4 feasibility entry in Task 29 and REVIEW to say its plotted-run provenance is unverified. |
| 30 — Quantitative metrics | **Not Done.** Fig. 3 outputs are missing; exact displayed transit-time statistics need the missing starting snapshots and saved model results; scattering loss outputs are absent. Saved related-run diagnostics are not substitutes for the plotted cases. The task may be closed through its qualitative fallback if that disposition is explicitly recorded in REVIEW and the task index, while leaving its quantitative acceptance criteria unchecked. No scope-change authorization is implied by this inspection. |
| 31 — Venue and scope | **Not Done.** Venue selection and application of the venue's requirements remain pending. The figure-feasibility findings inform that decision. |
| 32 — Submission package | **Not Done.** Author declarations, approvals, journal-specific requirements, and final document validation remain pending. |
| 33 — Editorial consolidation | **Not Done.** No manuscript consolidation or final build was performed here; the venue and quantitative dispositions remain unsettled. The empirical affine relation alone does not justify removing all mapping caveats. |
| 34 — Repository hygiene | **Not Done by this audit.** `tasks/TODO.md` is tracked, satisfying only part of its status question. Review de-duplication, policy/documentation alignment, and the task-index decision remain separate work. |

### Why the 43% uncertainty is not a completed item

The subset count of 2,402 is established from the transformed file, and the script hard-codes it as the denominator. The exact lost-particle count, weights, reference-particle treatment, and correspondence to the quoted 43% are not recovered. A binomial uncertainty additionally assumes an appropriate independent, equally weighted sample; that assumption is not established by counting rows. Consequently, the earlier suggestion to compute a binomial uncertainty from the rounded percentage and 2,402 alone is withdrawn. No new uncertainty estimate should be added on this evidence.

## 5. Follow-up work within the current scope

1. Add the local archive location and this audit's evidence to REVIEW and README, distinguishing recovered files from unresolved plotted-run provenance. Correct the earlier suggestion that Fig. 4's original plotting data were confirmed recovered.
2. Synchronize Task 29 and the task index as closed through the documented fallback, preserving the production limitation and unchecked regeneration criteria. Decide and record Task 30's qualitative fallback disposition separately.
3. Keep author questions on the 43% loss accounting, nominal versus simulation momentum, plotted RFKO/feedback/tune-step run identities, MARS configuration, and the physical derivation of the return map. The fit and subset count narrow these questions but do not answer all of them.
4. Complete venue, submission-package, consolidation, and repository-hygiene work under Tasks 31–34 when their inputs are available. No figure regeneration or new tracking is authorized by this report.
