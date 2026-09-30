# Task 16 — Prepare submission front matter and supporting items

Status: Done  
Priority: P2  
Depends on: Task 09 (journal choice); Task 13

## Scope

Title-page material, running head, contents block, highlights, cover letter draft, and declaration checklist.

Follow `tasks/README.md`: no new simulations or results; preserve every scientific figure and panel unchanged. Edit the active manuscript directly when executing this task. Record substantive changes in `REVIEW.md`.

## Problem to address

Several items outside the manuscript body are unfinished or inconsistent. Task 09 covers bibliographic accuracy and the author declarations; this task covers the rest of the submission package.

## Work

- **Running head.** `\shorttitle` reads "Particle dynamics during slow resonant extraction," which no longer matches the title. Derive a short title from the current title.
- **Contents block.** The companion-format conversion restored `\tableofcontents` and a page break. Journals normally do not accept a contents list in a research article. Confirm with the author that it is only for internal review, and remove it or switch it off for the submission build.
- **Highlights.** Elsevier journals (the `cas-sc` class family) usually ask for 3–5 highlights of at most 85 characters each. Draft them from existing findings only, with the 43% qualifier included if that number is used, and confirm the requirement for the chosen journal.
- **Keywords.** Check them against the journal's rules; consider "slow extraction," "transit time," and "septum scattering."
- **Declarations checklist.** Add to the Task 09 checklist:
  - CRediT author statement;
  - competing interests;
  - data availability (the plotting data and input decks are not in this repository);
  - funding statement consistency: the acknowledgment cites the Fermilab operating contract while the author is now at Korea University, so ask whether Korean funding also applies;
  - the publisher's policy on declaring AI-assisted writing, which Elsevier currently requires to be disclosed.

  Do not write any declaration on the author's behalf.
- **Cover letter.** Draft it only if the author asks. It should state the relationship to the NET 2026 article plainly, so that editors do not suspect duplicate publication.
- **Figure resolution.** Record the journal's minimum resolution and compare it with the existing assets (the MARS image is 475×419 pixels). Report the gap; do not upsample.

## Acceptance criteria

- [x] The running head matches the title.
- [x] The submission build has no contents block, or the author has chosen to keep it.
- [x] Highlights, if drafted, contain only supported findings and meet the length limit.
- [x] Declarations are listed as author actions, and none is invented.
- [x] Every journal-specific rule cites that journal's current official guide.

## If evidence is unavailable

Without a named journal, prepare generic Elsevier items and mark every journal-specific requirement as pending.

## Completion record

Completed: 2026-10-01.

- Running head now matches the title ("RFKO, transit times, and septum scattering in Mu2e extraction").
- The contents list and page break are kept for the author-requested review layout. `\SubmissionBuild` omits them for submission (documented in the README; verified at 22 pages).
- Keywords sharpened to six specific terms.
- Drafted `highlights.txt` (five bullets, 77–85 characters, no acronyms, from existing findings only) for author approval.
- Added commented placeholders before the references for CRediT, competing interests, data availability, and the AI declaration, with Elsevier's template and placement rule. No declaration was written.
- Recorded Elsevier's artwork rules (300/500/1000 dpi; lettering at least 7 pt) against the existing assets: none complies, and originals are needed. No cover letter was drafted, because none was requested.
- All Elsevier-wide rules are cited to Elsevier's official pages (REVIEW). Journal-specific rules remain pending until a journal is named.
