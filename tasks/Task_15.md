# Task 15 — Consolidate limitations and tighten the prose

Status: Todo  
Priority: P2  
Depends on: Task 13

## Scope

The whole manuscript body, especially results paragraphs and captions.

Follow `tasks/README.md`: no new simulations or results; preserve every scientific figure and panel unchanged. Edit the active manuscript directly when executing this task. Record substantive changes in `REVIEW.md`.

## Problem to address

The source contains about 30 negating or hedging constructions ("does not establish", "cannot be attributed", "need not", "by themselves", and similar) in about 4,200 words. Many repeat the same boundary. For example, the 43% denominator is re-qualified in the abstract, Sec. 2, Sec. 4.3, and the conclusion, and "no suppression factor or optimum gains" appears in Sec. 3 and the conclusion. A reader has to get through several disclaimers to reach each finding, which makes the evidence look weaker than it is. Task 10 mentions reducing caveats in general; this task makes it a systematic pass.

## Work

- Inventory every limitation sentence, grouped by the boundary it states: conditional loss denominator; qualitative feedback evidence; model differences not isolated to space charge; resonance drive disabled in the fixed-tune test; normalization of the diagnostic plots; unverified inherited settings.
- Keep one full statement of each boundary, in the Sec. 2 scope passage or the Discussion from Task 13. Leave a short qualifier beside each number that needs one, such as the 43% denominator, which must stay with every use of that number. Delete the repeats.
- Rewrite result paragraphs so that each leads with the observation and its interpretation, followed by at most one scoped qualifier.
- Shorten captions that repeat body-text caveats; keep the caveats that a reader of the figure alone needs.
- Do general copy-editing: remove "the present"/"here" filler, keep terminology consistent ("transit time" versus "arrival time"; "returned sample" versus "tracked scattered-particle sample"), avoid chains of nouns, and define every acronym at first use (C-magnet, Hockney solver, 2.5D/3D).
- Recount the hedging constructions afterwards and report the before and after counts in REVIEW.

## Acceptance criteria

- [ ] Each of the scope boundaries listed above is stated fully exactly once, and every number keeps its qualifier.
- [ ] Qualifiers required by `AGENTS.md` (the 43% denominator, coherent motion versus emittance, the 50 versus 100 µm foils) remain intact.
- [ ] The hedging count falls substantially with no loss of a material limitation.
- [ ] Terminology is consistent across the text, captions, and tables.

## If evidence is unavailable

This is a pure editing task; no evidence is needed.

## Completion record

Pending. Record changed sections, checks performed, and unresolved author questions here before marking Done.
