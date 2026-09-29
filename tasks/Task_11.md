# Task 11 — Resolve figure–text discrepancies found in review

Status: Done  
Priority: P1  
Depends on: Tasks 03 and 04; feeds Tasks 05–08

## Scope

Result paragraphs and captions for `fig:fig9`, `fig:arrival1`, `fig:arrival2`, `fig:beamloss2`, `fig:beamloss3`, `fig:rfko1`, and `fig:rfko2`.

Follow `tasks/README.md`: no new simulations or results; preserve every scientific figure and panel unchanged. Edit the active manuscript directly when executing this task. Record substantive changes in `REVIEW.md`.

## Problem to address

A 2026-09-29 review inspected the image files at native resolution. It found statements that do not match the plotted content and plot elements that the text never explains. Tasks 05–08 set general caption standards, but these specific mismatches need an explicit decision. Visual readings listed below are for review only: they may justify narrowing or correcting a claim or raising an author question, but they must not appear in the manuscript as new numerical results.

## Findings to resolve

1. **Ripple frequency versus visible modulation (`img/fig9.png`, middle panel).** The dominant visible modulation repeats roughly every 1,600 turns, about 2.7 ms or of order 360 Hz. The text specifies a 60 Hz sinusoid, whose period is about 9,800 turns; only about two such periods fit in the plotted range. The modulation is also sawtooth-like rather than sinusoidal. Ask the author to confirm the ripple frequency, waveform, and turn-on time. Until then, the text should not assign the visible modulation to 60 Hz and its harmonics.
2. **Displayed spill range (`img/fig9.png`).** The horizontal axis spans about 0–20,000 turns, not the 31,795-turn spill in Table 1. State the displayed range in the caption, or record why the run ends there.
3. **Transit time versus the unstable fixed point (`img/fig_arrival2a–c.png`).** The text says transit times increase "for starting coordinates nearer the unstable fixed point." In all three panels, times increase monotonically from the septum line toward x = 0. The longest times belong to particles starting on the far side of the fixed-point line, and panel (a) shows no maximum at that line. Rewrite the observation to match the plot. A mechanism, such as a particle following the separatrix before reaching the outgoing branch, must be labelled as interpretation.
4. **"Full tracking has a broader distribution."** This holds visibly in panels (a) and (c), but in panel (b) the RK4 points (red) extend to about 240 turns, beyond the Synergia2 points. The ordering of the two calculations also varies between stages. Narrow the claim to the panels that support it.
5. **Axis ceiling versus observation window.** The transit-time axis stops at 250 turns, whereas the text describes an observation interval of about 500 turns. Record whether points beyond 250 turns exist but lie outside the axis, or whether no particle took longer. Do not imply that the tail is complete.
6. **Behaviour after restoration (`img/fig_arrival1a–b.png`).** After the burst, the paused-and-restored case (red) extracts more slowly than the uninterrupted ramp for the rest of the displayed window. Its spill stays below the blue trace, and its circulating fraction stays above it. The plots also extend about 1,000 turns past restoration, twice the stated 500-turn observation interval. Describe the persistent difference, and reconcile the interval with the text or record it as an author question. The burst also appears only after a visible delay following the purple restoration line; describe that qualitatively without extracting a delay constant.
7. **Unexplained overlays (`img/fig_beamloss2a.png`, `img/fig_beamloss3.png`).** Both panels contain a red circle, three orange straight lines forming a triangle, and a horizontal orange line near αx+βx' ≈ −4.5 mm. Neither caption explains them. Ask the author what they represent (for example, separatrix asymptotes, an aperture, or the initial beam size) and caption them only from that answer.
8. **Loss-map legend (`img/fig_beamloss2b.png`).** The map has unlabelled axes, red and orange markers, star symbols near the extraction region, and a "beam" direction arrow. The caption explains none of these. Obtain their meanings and the axis units from the author. The text's "first arc" and "middles of the straight sections" should be checked against the marker positions.
9. **Hatted coordinates (`img/fig_rfko1b.png`).** The axes read x̂ (mm) and x̂' (mrad), which the manuscript never defines, and the trajectory is sampled coarsely at an unknown interval. Define the notation only if its source is known; otherwise explain in the caption that the plotted coordinates are the centroid in the original diagnostic convention.
10. **Emittance evolution (`img/fig_rfko1a.png`).** At C_x = 1 the growth slows toward the end of the run, which could reflect the aperture removing particles; at C_x = 0 there is a slight rise. Describe these features qualitatively and link the slowing to the aperture caveat, not to a saturated diffusion process.
11. **Action-distribution range (`img/fig_rfko2a–b.png`).** The C_x = 1 distribution extends past the plotted limit √I_x = 2, and the vertical axis has an undocumented 10^7 scale factor. Mention that the plotted range truncates the tail.

## Acceptance criteria

- [x] Every finding above is either reflected in corrected text or caption wording or recorded in `REVIEW.md` as an open author question.
- [x] No visually read period, delay, width, or count is presented in the manuscript as a result.
- [x] Captions explain every plotted element whose meaning is documented; undocumented elements are flagged, not guessed.
- [x] Figure files are byte-identical before and after the task.

## If evidence is unavailable

Narrow each affected sentence to what the image unambiguously shows and keep the author question open. For the ripple frequency in particular, do not change "60 Hz" without source evidence. Flag the inconsistency so the author can resolve it before submission.

## Completion record

Completed: 2026-09-29.

- Findings 3, 4, 6, 10, and 11 were corrected in the text or captions to match the plots, qualitatively and without new numbers.
- Findings 1, 2, 5, 7, 8, and 9 were narrowed in the text and flagged in the captions or `AUTHOR CHECK` comments; they remain open author questions.
- The ripple is still given as 60 Hz. The unsupported word "sinusoidal" was removed, and the visible modulation is no longer assigned to 60 Hz harmonics. REVIEW records the pixel-trace evidence (a period of about 1,650 turns, roughly 360 Hz).
- Build succeeded (18 pages); labels are unique, all references resolve, and all pages were inspected. Image hashes are unchanged.
- See REVIEW, "Task 11 completed", for the full resolution table.
