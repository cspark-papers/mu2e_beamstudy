# Journal submission readiness review

Review date: 2026-10-01. Manuscript: `beamstudy-mod.tex`.

**My assessment: the manuscript has a plausible publishable contribution, but I would not submit this version yet. My referee recommendation would be major revision. Acceptance is possible, provided the essential scientific documentation can be recovered.**

The manuscript is substantially improved. Its structure is coherent, the reduced-model conventions are clearer, and it distinguishes observations from interpretations more carefully. Separating the conditional 43% scattered-sample loss from the circulating-beam loss is particularly important. The remaining obstacles concern the evidence supporting the results more than the writing.

The subject fits specialist accelerator journals. For context, *Physical Review Accelerators and Beams* expects a significant, substantive contribution to accelerator science; topical relevance alone does not establish acceptance. [PRAB acceptance criteria](https://journals.aps.org/prab/about)

My principal concerns, in order of importance, are:

1. **Essential methods remain undocumented.**
   [Appendix A](../beamstudy-mod.tex#L484) lists missing controller settings, simulation configurations, diagnostic definitions, particle-selection rules, and tracking endpoints. Several determine the meaning of the reported results. A reader cannot adequately assess a feedback calculation without its implemented control law and gains, or a loss calculation without its sample accounting and observation interval.

   The appendix is honest and useful. However, disclosing these omissions does not resolve them. This is the strongest reason I would withhold an acceptance recommendation.

2. **The 43% loss result is still insufficiently defined for a headline quantitative conclusion.**
   [Section 6](../beamstudy-mod.tex#L422) correctly makes this fraction conditional on the returned scattered-particle sample. Nevertheless, the particle weights, sample size, inclusion of reference particles, tracking duration, and extraction criterion remain unknown.

   Those omissions prevent a reviewer from determining precisely what the percentage measures or assessing its uncertainty. I would require the existing particle accounting to be documented before accepting this number as a central result. This concern does not establish that 43% is incorrect; it establishes that the manuscript does not yet substantiate it sufficiently.

3. **The feedback result demonstrates a visual change, but not a well-characterized improvement in spill quality.**
   [Section 4.2](../beamstudy-mod.tex#L308) leaves the ripple amplitude convention and the relationship between the stated 60 Hz excitation and the faster visible modulation unresolved. The controller parameters and spill normalization are also missing.

   Figure 3 supports reduced visible periodic modulation, but residual spikes complicate any broader claim of improved spill quality. The present cautious wording is appropriate. Nevertheless, a reviewer may reasonably ask what practical improvement has been established and under which reproducible conditions.

4. **Some physical interpretations remain underdetermined.**
   The [chromaticity comparison](../beamstudy-mod.tex#L264) may also involve different excitation bandwidths, while the emittance and action diagnostics lack essential definitions. Consequently, the figures do not isolate chromaticity as the cause of their differences.

   Similarly, the tune-step results are useful diagnostics, but they do not measure the RFKO feedback-loop delay. The manuscript now acknowledges this distinction correctly. Acceptance depends on whether the narrower observations provide a sufficiently substantial contribution.

5. **The novelty is credible but incremental, and needs a stronger evidential foundation.**
   The Mu2e-specific transit-time comparisons and transport beyond septum interception distinguish this work from the preceding feed-forward study. However, RFKO phase mixing and Kobayashi resonance dynamics are established concepts. The paper's strongest contribution must therefore come from the documented Mu2e results and their practical implications. At present, missing information weakens those strongest parts.

Within your constraint of **no new simulations and unchanged figures**, the highest-value next step is to recover existing input decks, logs, diagnostic definitions, and particle-accounting records. That could resolve substantial concerns without generating new results. If those records cannot be recovered, further qualification alone may leave too little substantiated material for a full research article; a narrower paper would need reassessment.

There are also secondary submission issues: some figure labels are small, several plotted quantities remain undefined, and the author declarations are still commented placeholders. These should be completed after the central scientific questions are addressed.

I compiled the current submission variant successfully: **25 pages, resolved citations and references, 50 unique labels, and no BibTeX warnings**. I inspected rendered feedback, transit-time, scattering, and appendix pages. The known CAS box warning remains. This verifies document construction, not the simulations.

**I see a route to acceptance, but I would expect serious reviewer objections to the current version. Recovering the essential records—not another round of language polishing—is the decisive step.** No repository files were changed during the review itself.





**My assessment: the manuscript has a plausible publishable contribution, but I would not submit this version yet. My referee recommendation would be major revision. Acceptance is possible, provided the essential scientific documentation can be recovered.**

The manuscript is substantially improved. Its structure is coherent, the reduced-model conventions are clearer, and it distinguishes observations from interpretations more carefully. Separating the conditional 43% scattered-sample loss from the circulating-beam loss is particularly important. The remaining obstacles concern the evidence supporting the results more than the writing.

The subject fits specialist accelerator journals. For context, _Physical Review Accelerators and Beams_ expects a significant, substantive contribution to accelerator science; topical relevance alone does not establish acceptance. [PRAB acceptance criteria](<https://journals.aps.org/prab/about>)

My principal concerns, in order of importance, are:

1. **Essential methods remain undocumented.**  
   Appendix A (beamstudy-mod.tex:484) lists missing controller settings, simulation configurations, diagnostic definitions, particle-selection rules, and tracking endpoints. Several determine the meaning of the reported results. A reader cannot adequately assess a feedback calculation without its implemented control law and gains, or a loss calculation without its sample accounting and observation interval.

   The appendix is honest and useful. However, disclosing these omissions does not resolve them. This is the strongest reason I would withhold an acceptance recommendation.
2. **The 43% loss result is still insufficiently defined for a headline quantitative conclusion.**  
   Section 6 (beamstudy-mod.tex:422) correctly makes this fraction conditional on the returned scattered-particle sample. Nevertheless, the particle weights, sample size, inclusion of reference particles, tracking duration, and extraction criterion remain unknown.

   Those omissions prevent a reviewer from determining precisely what the percentage measures or assessing its uncertainty. I would require the existing particle accounting to be documented before accepting this number as a central result. This concern does not establish that 43% is incorrect; it establishes that the manuscript does not yet substantiate it sufficiently.
3. **The feedback result demonstrates a visual change, but not a well-characterized improvement in spill quality.**  
   Section 4.2 (beamstudy-mod.tex:308) leaves the ripple amplitude convention and the relationship between the stated 60 Hz excitation and the faster visible modulation unresolved. The controller parameters and spill normalization are also missing.

   Figure 3 supports reduced visible periodic modulation, but residual spikes complicate any broader claim of improved spill quality. The present cautious wording is appropriate. Nevertheless, a reviewer may reasonably ask what practical improvement has been established and under which reproducible conditions.
4. **Some physical interpretations remain underdetermined.**  
   The chromaticity comparison (beamstudy-mod.tex:264) may also involve different excitation bandwidths, while the emittance and action diagnostics lack essential definitions. Consequently, the figures do not isolate chromaticity as the cause of their differences.

   Similarly, the tune-step results are useful diagnostics, but they do not measure the RFKO feedback-loop delay. The manuscript now acknowledges this distinction correctly. Acceptance depends on whether the narrower observations provide a sufficiently substantial contribution.
5. **The novelty is credible but incremental, and needs a stronger evidential foundation.**  
   The Mu2e-specific transit-time comparisons and transport beyond septum interception distinguish this work from the preceding feed-forward study. However, RFKO phase mixing and Kobayashi resonance dynamics are established concepts. The paper’s strongest contribution must therefore come from the documented Mu2e results and their practical implications. At present, missing information weakens those strongest parts.

Within your constraint of **no new simulations and unchanged figures**, the highest-value next step is to recover existing input decks, logs, diagnostic definitions, and particle-accounting records. That could resolve substantial concerns without generating new results. If those records cannot be recovered, further qualification alone may leave too little substantiated material for a full research article; a narrower paper would need reassessment.

There are also secondary submission issues: some figure labels are small, several plotted quantities remain undefined, and the author declarations are still commented placeholders. These should be completed after the central scientific questions are addressed.

**I see a route to acceptance, but I would expect serious reviewer objections to the current version. Recovering the essential records—not another round of language polishing—is the decisive step.** No repository files were changed.
