# Task 34 — Review-file and repository-policy hygiene

Status: Todo  
Priority: P3  
Depends on: None  
Source: inspection of `reviews/` on 2026-10-01

## Findings

1. **`reviews/review1.md` contains its review text twice.** After the closing "No repository files were changed during the review itself." line and a blank gap, the assessment, concerns 1–5, and the conclusion are repeated with slightly different link formatting. The author should keep one copy; the file was not edited when this task was recorded.
2. **Policy mismatch.** `AGENTS.md` says to "keep temporary build and review products outside the tracked source tree", but the review reports are now tracked in `reviews/`. Decide whether the reports are deliverables, and if so, update `AGENTS.md` and the README file table to list `reviews/`.
3. `tasks/TODO.md` is present in `tasks/` but not referenced by the index. Decide whether to track and index it, or remove it. Do not delete it without author approval.

## Acceptance criteria

- [ ] `reviews/review1.md` holds a single copy of the review, by author edit or approval.
- [ ] `AGENTS.md`, README, and the actual tracked files agree on where review reports live.
- [ ] The status of `tasks/TODO.md` is recorded.

## Completion record

Pending.
