# Task 26 — Small layout, bibliography, and style corrections

Status: Todo  
Priority: P2  
Depends on: None  
Review date: 2026-10-01

## Scope

Table placement, bibliography rendering, and an author style decision. Bibliography metadata changes must be verified at a primary source.

## Findings

1. **Table 1 is defined in the Introduction but first discussed in Sec. 2.1.** The `table:param` float is placed after the first Introduction paragraph, whereas the text first refers to it in `sec:baseline` ("Table~\ref{table:param} lists…"). Moving the float source to `sec:baseline` keeps the parameter table with its discussion. Check that float placement and the review-layout contents remain acceptable.
2. **The MARS15 code name is mis-capitalized in the bibliography.** The `mars2` entry renders as "Recent Mars15 developments…". The primary report (FERMILAB-CONF-10-518-APC, December 2010, title page checked 2026-10-01) reads "RECENT MARS15 DEVELOPMENTS: NUCLIDE INVENTORY, DPA AND GAS PRODUCTION". Protect the code name as `{MARS15}`; nothing else changes.
3. **The TDR entry repeats its arXiv link.** The `tdr` entry renders a hyperlinked title, an "arXiv:1501.05241" note, and a separate URL line. Keep one form (the report number plus the arXiv identifier, or the URL) according to the journal's reference style; do not change the verified metadata.
4. **Author decision: Acknowledgments numbering.** The Acknowledgments heading is numbered (Sec. 9), matching the companion manuscript format the author requested. Elsevier articles normally use an unnumbered heading (`\section*`). Ask the author, or apply when a journal is chosen; this is not an error under the current author-approved format.

## Acceptance criteria

- [ ] Table 1 appears with or after its first discussion, and the layout is checked.
- [ ] `mars2` renders "MARS15", matching the primary title page; no other metadata changes.
- [ ] The TDR reference shows its arXiv link once.
- [ ] The Acknowledgments numbering is left as is, or changed, by recorded author decision.
- [ ] Both build variants succeed with 0 BibTeX warnings and the same 24 cited keys in the same order.

## Completion record

Pending. Findings recorded only; the manuscript and bibliography have not been edited for this task.
