Final pass

- Acronyms: RK4 and ESS1 were used in Table 3 and the §6 workflow list before being defined; both are now defined at first use. HIMAC and "CERN SPS" are spelled out.
- Units: the last two values (1 ms, 8 GeV) now use the same unit formatting as the rest.
- Consistency: the title, abstract, Introduction and Conclusions all describe the same scope and the same four findings in the same order.
- Claims: I checked every claim in the abstract and Conclusions against the figure or section that supports it. The mapping is in REVIEW.md.

Checks

- Builds: I ran the README commands in fresh directories, and both the review and submission versions build cleanly at 23 pages. BibTeX gives 0 warnings, and the only LaTeX warning is the known, harmless one on the title page. The submission version has no contents list and starts the Introduction on page 1.
- Source: 46 labels with no duplicates, and every reference resolves. All 24 citations match the bibliography exactly. All LaTeX environments are properly closed.
- Pages: I looked at all 23. Equations, three tables, eight figures in order, captions and references are all fine, with no clipping and no empty pages.
- Unchanged files: the 22 image files haven't changed since the repository's first commit, and both older drafts are identical to before this work started. No new simulations were run. Apart from the documented momentum correction, no scientific number changed.

Before you can submit

Full details are in REVIEW.md under "Readiness report":

1. Simulation details only you can supply. The most important is the ripple frequency: the plot suggests about 360 Hz, but the text says 60 Hz. The others:
   - the ripple amplitude convention;
   - the controller gains;
   - how particles were selected, and when they count as having reached the septum;
   - the tracking endpoints of the scattered sample, and whether the     reference particles
   - the emittance, action and acceptance conventions;                 - where the 50 µm foi
2. Figures: all fall below Elsevier's minimum resolution and label sizeyou'll need original . The origin of the MARS figure also needs confirming.                                       Declarations: acknowlcontributions (CRediT),competing interests, data availability and the AI-use disclosure.   Placeholders are in treferences.
4. Journal choice: this settles formatting, keyword limits and whether highlights in highlig
5. Internal references: decide what to do with the three internal Mu2e documents.

Seven hidden AUTHOR CHEClag these open questions; remove them once each is resolved. A successful build doesn't validate the simulations themselves.
