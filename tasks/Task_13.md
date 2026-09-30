# Task 13 — Restructure the paper and add a synthesis discussion

Status: Done  
Priority: P1  
Depends on: Tasks 05, 06, 07, and 11

## Scope

Section order and headings, `sec:intro` roadmap, `sec:conclusion`, and a new discussion section built only from existing results.

Follow `tasks/README.md`: no new simulations or results; preserve every scientific figure and panel unchanged. Edit the active manuscript directly when executing this task. Record substantive changes in `REVIEW.md`.

## Problem to address

The current section structure works against the paper's main argument:

- The two RFKO studies (Sec. 3, feedback; Sec. 5, fixed-tune excitation) sit on either side of Sec. 4, although the introduction treats them as one theme. As a result, the chromatic-mixing mechanism is explained after the feedback result it helps interpret.
- Sec. 4 is titled "Particle tracking simulations," but every results section reports tracking; the heading doesn't identify the content.
- The reduced Hamiltonian (Sec. 4.1) is a method shared by the transit-time and scattering results, but it is nested inside a results section.
- The introduction lists the studies in a different order from the sections.
- The paper has no discussion section. The conclusion carries the cross-study synthesis: how chromatic mixing, finite transit times, and controller behaviour relate.

## Work

- Propose a section order to the author before moving text, and record the choice. One option: (1) Introduction; (2) Baseline, scope, and methods (current Sec. 2 plus the Task 03 case descriptions); (3) Reduced resonance model; (4) RFKO response — fixed-tune excitation, then feedback; (5) Transit times after a tune step; (6) Transport of septum-scattered particles; (7) Discussion; (8) Conclusions. Moving the fixed-tune study ahead of the feedback study lets the mechanism precede the application.
- Give each heading a descriptive, specific title.
- Write a short Discussion that links existing observations only:
  - Tune-step transit times of tens to hundreds of turns (Fig. 3's axis range) are of the same order as the 100-turn averaging interval.
  - That qualitatively supports the text's reading of proportional-only oscillations as a delayed response.
  - Chromatic mixing determines whether RFKO increases internal spread or drives coherent motion.
  - The scattered-sample result changes how losses near the septum should be interpreted.

  Present these as qualitative links; derive no delay constant, bandwidth, or gain.
- Rewrite the introduction's roadmap and the conclusion to follow the new order.
- Move text rather than rewrite it wherever possible, so that the change is easy to review. Keep all labels and update cross-references.

## Acceptance criteria

- [x] The author has approved the section order before large text moves.
- [x] The RFKO material is contiguous, and the mechanism precedes its application.
- [x] Every Discussion statement cites an existing figure, equation, or reported result, and no new number appears.
- [x] All `\ref` targets resolve and no label is duplicated after the move.
- [x] Figures still appear near their first reference.

## If evidence is unavailable

If the author prefers the current order, keep it but retitle Sec. 4, point forward from Sec. 3 to the mechanism in Sec. 5, and still add the Discussion.

## Completion record

Completed: 2026-10-01 (section order approved by the author before text moves).

- New order: Introduction → Baseline and cases → Reduced resonance model → RFKO response (4.1 fixed-tune mechanism, 4.2 feedback) → Transit times → Septum-scattered transport → Discussion → Conclusions. Headings are descriptive and `sec:tracking` was removed.
- Text was moved without rewriting (verified by a sorted-line comparison). Linking sentences, the abstract order, the introduction roadmap, the Sec. 4 introduction, and the Table 3 row order were updated.
- New Discussion: response chain (7.1), losses after interception (7.2), and the role of the reduced model (7.3), built from existing results with no new numbers. Conclusions were rewritten in the new order.
- The contents list is set in small type so that it stays on the title page.
- Build succeeded (22 pages); the 45 labels are unique, all references resolve, figures appear in order, and hashes are unchanged.
