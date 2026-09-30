# Task 18 — Reconcile RFKO diagnostics and chromaticity claims

Status: Todo  
Priority: P1  
Depends on: 04, 05, 11  
Review date: 2026-09-30

## Scope

`beamstudy-mod.tex`: `sec:rfko`, `fig:rfko1`, `fig:rfko2`, and the associated claims in the Introduction, feedback subsection, Discussion, Conclusions, and `highlights.txt`. Source line numbers below refer to the reviewed version and are secondary to these labels.

Follow `tasks/README.md`: existing evidence only, no new simulations, and no changes to figure files or panels. This task addresses residual assertions introduced or retained after Tasks 04–05; it does not repeat the general request to recover diagnostic metadata.

## Findings

1. **The body assigns a reference-orbit action to a diagnostic whose reference is explicitly unknown.** At line 286, the text identifies the plotted `I_x` with Eq. `eqn:action`. The caption at line 283 says that the diagnostic's orbit-versus-centroid reference is not documented. Those statements cannot both serve as an established definition. The issue matters because Fig. 1(b) shows substantial centroid motion at zero chromaticity while the profiles in Fig. 2(a) nearly coincide. Under the printed definition, `mean(I_x) = [Var(X) + Var(X') + mean(X)^2 + mean(X')^2]/2`; coherent displacement contributes to the reference-orbit action even when the internal emittance is unchanged. The figures alone do not establish the reference, the correspondence of sampled times, or a contradiction in the simulation.
2. **The density interpretation needs its assumptions.** At line 286, the annulus argument is valid conditionally if `f(u) = dN/du`, with `u = sqrt(I_x)`. It gives an angularly averaged density: `dA = 4*pi*u*du`, so the annular mean is `f(u)/(4*pi*u)`. It does not recover a general two-dimensional density or demonstrate particle-by-particle outward diffusion. A Gaussian dependence on `u` additionally requires a centered, matched Gaussian in the stated normalized coordinates. A coherently displaced or mismatched Gaussian need not have that radial profile about the reference orbit. The caption currently calls the plots phase-space density profiles without stating this conditional interpretation.
3. **Chromatic tune spread is conflated with total incoherent tune spread.** Lines 258 and 273 describe a much smaller betatron tune spread, or effectively no tune spread, at `C_x=0`, although the case retains space charge. The absence of chromatic spread is not the absence of incoherent space-charge spread. The cited [IPAC2011 RFKO paper, especially p. 3561](https://epaper.kek.jp/IPAC2011/papers/thps058.pdf), explicitly distinguishes the coherent dipole response from incoherent space-charge motion. Retain that distinction in the explanation of the current figures.
4. **The causal summary is stronger than the case comparison.** Line 258 acknowledges that the two cases may have different excitation bandwidths. Nevertheless, lines 288, 296, 427, and 448 say that the tests show chromaticity converts the excitation or provides the required mixing; the first highlight says chromaticity “decides” the response. The observed contrast supports an interpretation consistent with chromatic mixing, but this comparison does not isolate chromaticity from an undocumented change in excitation spectrum.

## Work and fallback

- Keep the observed emittance/centroid contrast. Present the action-density interpretation conditionally until the diagnostic reference and normalization can be established from existing records.
- Describe the annular profile as an angular average under the stated assumptions; avoid using it to infer an unmeasured diffusion process or trajectory history.
- Replace zero/small total-tune-spread wording with the appropriate chromatic-spread or coherent-response statement.
- Align the Introduction, caption, Discussion, Conclusions, and highlights with the already acknowledged bandwidth confound. Preserve the established physical mechanism as an interpretation, not a uniquely demonstrated cause in these runs.
- Carry any unresolved action reference, sampling correspondence, and bandwidth questions into the existing emittance/RFKO author-check entries in `REVIEW.md` when implementing this task. Missing records do not require new runs.

## Acceptance criteria

- [ ] No unverified equality between the plotted action and Eq. `eqn:action` remains.
- [ ] The density/Jacobian argument states the required reference, angular averaging, and Gaussian assumptions.
- [ ] Space-charge and chromatic tune spreads are distinguished consistently.
- [ ] Summary claims and highlights retain the bandwidth limitation without losing the observed result.
- [ ] Images, reported values, and citation metadata are unchanged; a rebuilt PDF has resolved references.

## Completion record

Pending. Findings recorded only; the manuscript has not been edited for this task.
