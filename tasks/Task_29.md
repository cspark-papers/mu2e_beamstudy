# Task 29 — Bring the figures to publication standard (requires a scope decision)

Status: Blocked — recorded as a submission blocker (author decision, 2026-10-01)  
Priority: P1  
Owner: Author decision, then author or editor  
Depends on: 27 (original plotting data or scripts)  
Source: `reviews/review2.md` major concern 3 and improvement item 2; `reviews/review1.md` secondary issues; Tasks 08 and 16 records

## Scope boundary

`AGENTS.md` and `tasks/README.md` currently forbid redrawing, regenerating, relabeling, or replacing figures. **This task cannot start until the author explicitly authorizes regeneration from original plotting data**, and that authorization is recorded in `tasks/README.md` and REVIEW. Regenerating a plot from its original data is not a new simulation, but it does change figure files.

## Findings

- All 14 assets print at 118–261 dpi, against Elsevier's 1000 dpi for line art. In-image lettering is about 3.5–8 pt, against a 7 pt minimum. The MARS image is 475×419 pixels.
- Several plot elements are undefined: the orange lines and red circle (Figs. 7(a) and 8), the loss-map markers and axes (Fig. 7(b)), the MARS axis units (Fig. 6), and the hatted centroid axes (Fig. 1(b)). The overlapping tick labels in Figs. 3 and 4 are baked into the images.

## Work (only after authorization)

1. From the original data or scripts recovered in Task 27, re-export each figure as vector or ≥1000 dpi, with readable labels, units, legends, and defined overlays. Panel content and data must be identical: no new runs, no digitizing from the PNGs.
2. Record provenance for each figure (script, data file, date) in REVIEW. Update captions only where the regenerated figure defines a previously undocumented element.
3. Keep the original PNGs in the repository history; replace them in `img/` only as authorized.

## Acceptance criteria

- [ ] Written authorization is recorded before any figure file changes.
- [ ] Each regenerated figure is traceable to original data, with identical content, and meets Elsevier's resolution and lettering rules.
- [ ] Captions, Appendix A, and the Task 08 inventory are updated; both builds pass.

## If not authorized or data are unavailable

Record the figures as a submission blocker for Elsevier production, and keep the current captions and disclosures.

## Completion record

2026-10-01: When asked, the author chose to record the figures as a submission blocker and **did not authorize** any figure change. No figure file, caption, or TeX line changed.

A read-only feasibility check against the Task 27 archive found the following:

| Figure | Original data | Regenerable without new computation |
| --- | --- | --- |
| Figs. 1–2 | Plotted 30,000-turn runs not found (related 20,000-turn runs differ) | No |
| Fig. 3 | Ripple/feedback runs not found | No |
| Fig. 4 | `arrival_time.*` run directories contain `log` and `kicked*.dat` read by `mu2e_arrival_time-05.py` | Possibly, after confirming which run directories are plotted |
| Fig. 5 | Particle dumps at the restoration turns absent; needs RK4 re-integration | No (data missing; RK4 runs excluded) |
| Fig. 6 | MARS image only | No |
| Fig. 7 | Ring-tracking run directory (`tune_ramp/mars`) absent | No |
| Fig. 8 | Input sample present; needs RK4 re-integration | No (RK4 runs excluded) |

Consequence: the 14 assets remain at 118–261 dpi with lettering of about 3.5–8 pt, below Elsevier's artwork rules (1000 dpi line art, 7 pt minimum). This is a production blocker for an Elsevier journal unless the editor accepts the figures as supplied, the missing data are found, or the author authorizes a scope change. Task 31 (venue and scope) should take it into account.
