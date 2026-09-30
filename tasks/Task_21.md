# Task 21 — Clean bibliography syntax and reconcile current review summaries

Status: Todo  
Priority: P2  
Depends on: 17; finish the review summary after 18–20  
Review date: 2026-09-30

## Scope

`beamstudy-mod.bib`, current-status passages in `README.md`, `REVIEW.md`, and `tasks/README.md`. Preserve historical completion records as history. This task follows the completed build/documentation work rather than reopening bibliography metadata verification.

## Findings

1. **Two unmatched closing braces remain outside BibTeX entries.** `beamstudy-mod.bib` has an extra `}` after `pimms2` at line 61 and after `rfkoreg` at line 127. The installed BibTeX ignores this inter-entry text and builds all 24 entries with zero warnings, so this is a source-hygiene defect, not a current compilation failure or lost-reference claim. A clean BibTeX log does not establish balanced source syntax.
2. **The current README undercounts the citations.** Its Submission status says “audited all 22 citations,” while the source and generated bibliography contain 24 distinct cited entries after splitting the PIMMS and internal-monitor references. Update the current count; do not retroactively alter counts attached to earlier builds.
3. **Current and historical review status are mixed.** Near the beginning of `REVIEW.md`, “Current author-directed scope and task backlog” still says only Task 02 is complete and Tasks 03–10 are planned. Later records close Tasks 02–17. The new review adds Tasks 18–21. Make the latest status easy to find and clearly identify earlier status paragraphs as historical; do not erase the earlier evidence or change recorded completion dates without provenance.

## Work

- Remove only the two stray braces and preserve every entry, key, author, date, report number, URL, and DOI.
- Reconcile current citation counts and backlog summaries with the actual files, keeping past counts and validation records attached to their original revisions.
- After Tasks 18–20 are implemented, update the current claim–evidence/readiness summary to reflect their narrowed interpretations, rather than continuing to describe the earlier review as the final editorial state.
- Rebuild review and submission variants from the repository root into fresh temporary directories. Check source structure as well as BibTeX warnings, citation coverage, unique labels, and the affected rendered pages.

## Acceptance criteria

- [ ] No unmatched inter-entry braces remain in `beamstudy-mod.bib`.
- [ ] The same 24 citation keys resolve with unchanged metadata and citation order, unless a separately authorized change is recorded.
- [ ] Current README/REVIEW/task-index summaries agree; historical records remain identifiable and intact.
- [ ] Both build variants succeed, with warnings inspected and affected pages reviewed.
- [ ] No manuscript results, reference drafts, or figures are modified as part of this cleanup.

## Completion record

Pending. The bibliography and root documentation are unchanged by the review that created this task.
