# Review of the archived simulation data in `data/`

Reviewed: 2026-10-07. Scope: read-only inspection of the untracked, gitignored `data/` directory (Synergia2 simulation records). No simulation, tracking, RK4 integration, or plotting script was run, and no file in `data/`, `img/`, or the manuscript was changed. The checks were limited to reading option files and logs, counting files and rows, comparing SHA-256 hashes, and one least-squares fit between two archived sample files.

## 1. Contents of `data/`

- 7.5 GB, about 12,800 files, dated mainly 2012–2015 (218 files from 2012, 1,351 from 2013, 8,707 from 2014, 2,552 from 2015, 1 from 2016).
- `data/tune_ramp/` (5.8 GB) holds the run directories, analysis and plotting scripts, and `img/` (261 PNGs) that Task 27 lists for `~/backups/TeVCluster_Backup-Nov2020/data/results/mu2e/tune_ramp/`. That backup path is not present on this machine, so byte identity with the Task 27 archive was not verified.
- Other directories are older or unrelated studies: `simple/run.*` (2013), `hibeta/` (2015), `240/`, and lattice caches (`lattice_cache_*`).
- Four files are dated 2025-11-05 (`data/mu2e_aperture.py`, `tune_ramp/options.py`, `tune_ramp/phasespace_apertures.py`, and a `.pyc`), so this copy has been edited or used recently.
- The lattice gives `momentum := 8.827385` GeV/c, as recorded in Task 27.

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

Conclusion: the runs plotted in Fig. 4 are not among the archived records. The Task 29 statement that plotting data "survive at most for Fig. 4 (`arrival_time.*`…)" needs to be corrected.

### 2.3 Fixed-tune runs (Figs. 1–2)

| Runs | C_x | Power | Last turn | ε at turn 20,000 |
| --- | --- | --- | --- | --- |
| `growth.00`, `.01` | 0, 1 | 25 W, no RFKO | 20,000 | 0.2839, 0.2840 |
| `growth.02`, `.03` | 0, 1 | 25 W, linear chirp | 20,000 | 0.2860, 0.4091 |
| `growth.04`, `.05` | 0, 1 | 500 W | 20,000 | (incomplete), 2.2206 |
| `growth.06`, `.07` | 0, 1 | 500 W | no `emittance.dat` | — |
| `agrowth.04`, `.05` (2014-05-21) | 0, 1 | 500 W | 20,000 | 0.3014, 2.2206 |
| `old_growth/growth.06`–`.11` (2014-05-17) | 0, 1 | 25 / 500 W | 10,000 | — |

All use `norm_emit = 16π` and `max_turns ≤ 20001`. The plotted curves run to 30,000 turns and reach about 2.45 at turn 20,000, so the plotted runs are still missing.

### 2.4 Ripple and feedback (Fig. 3)

- No `mu2e_spill.h5` file exists anywhere in `data/` (the input of `mu2e_spill_rfko.py`, which plots spill rate with quadrupole ripple).
- All 301 ramp modules (`ramp_modules.py`, `profile_ramp_modules.py`) set `A = 0.000`; the 120 profile-test modules also initialize the gains `gp`, `gi`, `gd` to zero.
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

| Fig. | Asset(s) | Data in `data/` | Regenerable with identical content? |
| --- | --- | --- | --- |
| 1 | `fig_rfko1a/b` | PNGs identical. Archived fixed-tune runs stop at turn 20,000 and differ from the plot (2.22 vs ~2.45) | **No.** Plotted runs missing |
| 2 | `fig_rfko2a/b` | PNGs identical; same missing runs as Fig. 1 | **No** |
| 3 | `fig9.png` | No spill files; ripple A = 0 and zero gains in every module | **No** |
| 4 | `fig_arrival1a/b` | PNGs identical but dated 2014-03-20; archived runs are Oct–Nov 2014; top panel matches the logs, middle and bottom do not | **No.** Plotted runs missing; replotting the Nov 2014 runs would change the figure's data |
| 5 | `fig_arrival2a/b/c` | PNGs identical; run directories have `extracted.dat` and `kicked1_1.dat`, but `mu2e_transit_time2.py` needs `mu2e_forced_particles_*.h5` (none in `data/`) and RK4 re-integration | **No** |
| 6 | `fig_beamloss1` | MARS image only; no copy in `data/` | **No** |
| 7(a) | `fig_beamloss2a` | PNG identical and the initial sample present; the next three turns come from `mu2e_forced_particles_*.h5` of the deleted `mars.*` runs | **No.** Only the initial distribution survives |
| 7(b) | `fig_beamloss2b` | PNG identical; the loss map needs `lattice_deposited_charge.h5` from the missing ring-tracking run | **No** |
| 8 | `fig_beamloss3` | PNG identical; input sample and `mu2e_mars_tracking.py` (with Twiss, \|g\|, δ written into it) present | **Only conditionally.** Requires a five-turn RK4 integration of the reduced model, excluded by the project rules; Task 27 found the figure matches only a variant of the script, so identical output is not guaranteed |

Even with author authorization, only Fig. 8 is technically reachable, and only by lifting the RK4 exclusion. The resolution and lettering shortfall (118–261 dpi, lettering about 3.5–8 pt) cannot be repaired from the archive and remains a submission blocker unless the editor accepts the supplied figures.

## 4. Effect on the task backlog

| Task | Status after this inspection |
| --- | --- |
| 27, 28 | Already Done. Task 27 needs an addendum: `data/` as a local archive copy, the new byte-identical matches (Sec. 2.1), the recovered affine map (Sec. 2.5), and the confirmation of the 2,402 selection. |
| 29 | Can be closed through its fallback ("If not authorized or data are unavailable"), not its acceptance criteria: the data rule out regeneration regardless of authorization. Its feasibility table must first be corrected for Fig. 4 (and the same statement in REVIEW.md). |
| 30 | Cannot be completed. Feedback metrics have no outputs; transit-time statistics need the missing particle dumps. Only the binomial uncertainty of the 43% fraction is computable (n = 2,402, √(0.43 × 0.57 / 2402) ≈ 1.0%), and it still needs author authorization. Otherwise close through the "If not authorized" fallback and keep the results qualitative. |
| 31, 32 | Not done; author decisions (venue, declarations, cover letter). The findings feed Task 31: figures cannot be fixed and quantitative metrics are unavailable. |
| 33 | Not done; depends on 30 and 31. The §6 mapping paragraph of `beamstudy-mod.tex` can already be updated with the recovered map (Sec. 2.5). |
| 34 | Not done, partly progressed: `tasks/TODO.md` is now tracked, but `reviews/review1.md` still contains its text twice and `AGENTS.md` does not mention `reviews/`. |

## 5. Pending author decisions

1. Record these findings in REVIEW.md (Task 27 addendum, Fig. 4 correction), close Task 29 through its fallback, update the §6 mapping paragraph, and refresh README and the task index.
2. Task 30: authorize the 43% binomial uncertainty, or close the task through its fallback.
3. Whether `data/` (untracked, gitignored) should be listed as an archive location in README and REVIEW.md.
