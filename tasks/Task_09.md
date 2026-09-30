# Task 09 — Verify attribution and prepare submission metadata

Status: Done  
Priority: P2  
Depends on: Tasks 02 and 03

## Scope

Bibliography, prior-work attributions, title-page metadata, acknowledgments, and author-only submission questions in `REVIEW.md`.

Follow `tasks/README.md`: no new simulations or results; preserve every scientific figure and panel unchanged. Edit the active manuscript directly when executing this task. Record substantive changes in `REVIEW.md`.

## Problem to address

Publication-quality prose also requires accurate references and author-approved declarations. The target journal has not yet been specified, so its requirements cannot be assumed.

## Work

- Check citations against available primary sources, beginning with the supplied prior paper and the existing provenance record. Verify any additional bibliographic change at its primary source.
- Retain the prior article’s 2026 volume/year and DOI despite its NET2025 filename. Attribute feed-forward results, solver settings, and geometric-loss values to that article rather than the current calculations.
- Preserve honest internal-report descriptions. Do not copy conflicting metadata or claim to have inspected an inaccessible original report.
- Check citation order, completeness, relevance, author names, journal/report fields, and cross-references. Add references only where they support an actual claim.
- Consolidate author-only questions about author/affiliation details, funding, competing interests, contributions, data availability, and any image provenance into a short checklist. Do not invent declarations or sharing commitments.
- If a journal is named, check its current official instructions for article type, abstract length, declarations, and figure requirements. Otherwise retain the current class and mark journal-specific adaptation pending, without blocking the editorial work.

## Acceptance criteria

- [x] Every citation key resolves and substantive attribution is accurate to the consulted source.
- [x] Conflicting or unverified bibliographic metadata remains documented.
- [x] No fabricated declaration, authorship information, or data-access promise.
- [x] Any journal-specific rule is tied to the named journal’s official instructions.
- [x] Figure-resolution requirements, if incompatible with existing assets, are reported without modifying the figures or claiming compliance.

## If evidence is unavailable

Keep verified portions of the citation and log the missing field. Leave author declarations and journal selection pending while completing all independent edits.

## Completion record

Completed: 2026-10-01.

- Audited all 22 citations (table in REVIEW). Corrected `pullia` to the thesis title-page title (French, Lyon 1, CERN-THESIS-99-070) and `kobayashi` to the INSPIRE title ("…resonant beam ejection"). `hardt` is only partly verifiable (CDS bot wall); `mars1` and `wcm` remain honestly labeled internal reports.
- Re-checked the attribution of prior-work results and settings to Ref. [2] and of theory to its sources. The 2026 volume and DOI of Ref. [2] are retained.
- Consolidated an 11-item author-only checklist in REVIEW (authorship and acknowledgments, affiliations and ORCID, funding, CRediT, competing interests, data availability, AI-use declaration, figure provenance including the MARS plot, relationship to Ref. [2], internal references, target journal). Nothing was invented.
- No journal is named, so the class is retained and journal rules remain pending. Build succeeded (23 pages).
