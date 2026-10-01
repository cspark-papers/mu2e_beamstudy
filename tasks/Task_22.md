# Task 22 — Align setup statements with the documented uncertainty

Status: Todo  
Priority: P1  
Depends on: 03, 12, 18–20  
Review date: 2026-10-01

## Scope

`beamstudy-mod.tex`: `sec:baseline`, `sec:cases`, `table:param`, `table:cases`, `sec:rfko`, and `sec:arrival`. Line numbers below identify the reviewed source; use the labels if later edits move them.

Follow `tasks/README.md`: existing records and editorial corrections only, no new simulations, no figure changes, and no invented settings. The main findings of Tasks 18–20 have been addressed. This task concerns remaining differences between what individual sentences assert and what the manuscript says is known.

## Findings

1. **The controller update interval is excluded without evidence.** At line 157, the text distinguishes the approximately 100-turn signal accumulation and chirp sweep, then says “Neither of these is the controller update interval.” The controller update interval is undocumented, so the available information does not establish either equality or inequality. Distinct operations can have the same period. Say that those intervals do not specify or establish the controller update interval. This requires no new controller measurement.
2. **A possible bandwidth difference becomes an asserted difference.** At line 258, the two chromaticity cases “may differ in excitation spectrum,” and their bandwidths are undocumented. At line 288, “the undocumented difference in bandwidth” presupposes that a difference exists. Use “a possible difference” or “the undocumented bandwidths” consistently. Preserve the Task 18 limitation without implying that an unverified confounding factor has been measured.
3. **The acceptance normalization is said to be provided where it is explicitly unavailable.** At line 132, the fixed-tune acceptance is described as one “whose normalization is given in Table” `table:scope`. That table actually says “normalization not documented.” Point to the unresolved convention accurately, without supplying a geometric/normalized conversion or relabeling a figure.
4. **The case table drops the tune-step selection qualification.** The `table:cases` row at line 170 identifies the sample simply as “Particles released by the step.” Section `sec:arrival` at line 323 says this is the intended/reported selection and that already-transiting particles may also be present because the criterion is undocumented. Make the table distinguish intended selection from established sample membership, since it is meant to be a self-contained case summary. Do not invent the selection algorithm or repeat the entire caveat in the cell.
5. **Nominal parameter correction and historical simulation inputs need a clearer distinction.** Table `table:param` transparently corrects the nominal momentum to 8.889 GeV/c using the stated 8 GeV kinetic energy and rigidity. However, line 339 says the Synergia2 calculation starts with “the parameters in Table” `table:param`, without distinguishing the corrected nominal value from an independently recovered input. The arithmetic supports the nominal correction; it does not reveal which value the historical run used. Keep 8.889 and the existing disclosure, but avoid claiming that the input deck was checked. If existing records establish the run momentum, record that provenance; otherwise identify the table as nominal/reported settings with the disclosed correction.

## Work and fallback

- Correct the known/unknown wording at the locations above, keeping the supported setup information and the existing numerical values.
- Check the corresponding table cells, abstract/conclusion summaries, and current claim–evidence map for the same distinction; do not expand this into another general rewrite.
- When implementing the task, add the specific nominal-versus-run momentum question to `REVIEW.md` alongside the existing configuration checks. Reuse the existing update-rate, bandwidth, acceptance, and particle-selection questions rather than duplicating them.
- If no additional records exist, qualify the statements and complete the editorial task. No new runs or author-supplied numerical values are required for that fallback.

## Acceptance criteria

- [ ] An undocumented controller update rate is neither equated to nor excluded from the other 100-turn intervals.
- [ ] Possible bandwidth differences remain possible throughout the text.
- [ ] The acceptance cross-reference accurately reports that the normalization is undocumented.
- [ ] Table 3 and the transit-time discussion agree about intended versus confirmed particle selection.
- [ ] Corrected nominal momentum is distinguished from verified historical input, without undoing the supported nominal correction.
- [ ] Builds and cross-references pass; all figure files, panels, and reported results remain unchanged.

## Completion record

Pending. This review records the findings only; the manuscript and figures are unchanged.
