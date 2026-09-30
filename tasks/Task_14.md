# Task 14 — Situate the work in the slow-extraction and RFKO literature

Status: Done  
Priority: P1  
Depends on: Task 02; coordinate with Task 09

## Scope

`sec:intro`, the relevant results paragraphs, and `beamstudy-mod.bib`.

Follow `tasks/README.md`: no new simulations or results; preserve every scientific figure and panel unchanged. Edit the active manuscript directly when executing this task. Record substantive changes in `REVIEW.md`.

## Problem to address

The manuscript cites 14 sources, and five of them are internal reports or notes (Mu2e DocDB documents, CERN and Fermilab internal notes). The introduction positions the work almost entirely against the author's own prior article. A referee will expect to see how the RFKO, transit-time, and scattering questions have been handled at other slow-extraction facilities, and where this study differs. Task 09 checks the existing citations but does not cover this gap.

## Work

- Identify, from primary sources only, the standard references for:
  - RFKO slow extraction and spill control (e.g., the original RFKO proposals and the HIMAC implementation);
  - spill ripple and transit-time effects on spill quality (e.g., PIMMS, Pullia, and more recent studies of spill quality at synchrotrons);
  - septum scattering and extraction losses (e.g., CERN SPS studies of loss reduction, and crystal or diffuser shadowing);
  - Mu2e Delivery Ring extraction and spill regulation after 2011, including conference papers by the Fermilab Mu2e and Accelerator Division groups.
- Verify each candidate's authors, title, venue, year, pages, and DOI at the publisher or an institutional archive before adding it. Record the verification URL in REVIEW. Do not add a reference from memory or from a secondary citation alone.
- Add only references that support a specific sentence, and write that sentence. Aim for one compact paragraph on related work plus targeted citations in the results. Do not pad the bibliography.
- Where a public equivalent of an internal report exists, prefer it or cite both. Leave internal-only reports labelled honestly.
- State the contribution relative to the literature, not only relative to Ref. [2], without claiming novelty that the sources do not support.

## Acceptance criteria

- [x] Every added reference is verified at a primary source, with the check recorded in REVIEW.
- [x] Each added reference supports a specific claim in the text.
- [x] The introduction states how the three studies relate to prior slow-extraction work at other facilities.
- [x] Internal reports are no longer the only support for any central claim, or that limitation is recorded.

## If evidence is unavailable

If a candidate can't be verified, leave it out and note the gap in REVIEW. Coverage that is limited but verified is preferable to broad but unverified coverage.

## Completion record

Completed: 2026-10-01.

- Added eight references, each verified at a publisher, OSTI, JACoW, or PMC record (URLs in REVIEW): Hiramoto & Nishi 1992, Noda et al. 1996, Furukawa et al. 2004, Niedermayer & Singh 2024, Velotti et al. 2019, Nagaslaev et al. 2023 (Mu2e 8 GeV shadowing), Ibrahim et al. IBIC2019 (Mu2e SRS design), and Narayanan NAPAC2025 (current PID-quadrupole regulation with RFKO still to be compared).
- Added a related-work paragraph and a literature-relative contribution statement to the Introduction, plus targeted citations in Sec. 4.2, Sec. 6, §7.1, and §7.2. Each citation supports a specific sentence.
- Recorded the remaining internal-report dependence (MARS model, wall-current monitor) in REVIEW.
- Build succeeded (23 pages, 22 references); labels are unique, all references resolve, and hashes are unchanged.
