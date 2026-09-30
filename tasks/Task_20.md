# Task 20 — Qualify transported scattering coordinates and repeated encounters

Status: Todo  
Priority: P1  
Depends on: 07, 11; coordinate with 19  
Review date: 2026-09-30

## Scope

`beamstudy-mod.tex`: `sec:beamloss`, `fig:beamloss2`, `sec:lossdisc`, and related statements about septum returns. Source line numbers refer to the reviewed version.

Follow `tasks/README.md`: no new MARS or Synergia2 transport, no new encounter statistics, and no changes to figures. Preserve the conditional 43% result and the existing endpoint qualifications.

## Findings

1. **A local thin-foil argument is applied to coordinates transported from the C-magnet.** Line 402 first states that the C-magnet-to-ESS1 transformation is undocumented, then identifies the near-vertical initial line as the expected thin-foil signature because scattering changes angle but not position. The local relation `Delta(alpha*x+beta*x') = beta*Delta(x')` is valid for an angular kick at fixed position and fixed Twiss parameters at the scattering plane. It does not by itself establish the geometry of a sample after transport through two septa, magnets, and an undocumented reference transformation. Even linear transport can convert an angular change into a position change through its `R12` term. The observed vertical line is secure; its attribution to a particular physical surface or mapping needs existing provenance.
2. **Three displayed turns are generalized to repeated material encounters.** Line 402 moves from “many surviving particles” returning after three turns to “Scattered particles therefore meet the septum again every third turn.” Line 433 repeats that assertion and infers repeated extraction opportunities. Fig. 7(a) shows an initial sample and three subsequent snapshots, not an encounter history for all survivors over many turns. Returning to a similar transverse phase-space region does not by itself demonstrate a foil interception, an extraction-field crossing, or a universal three-turn recurrence for the selected scattered population.
3. **The workflow still uses survival as a stopping condition without an interval.** Line 385 says tracking continues “until each particle is lost or survives,” although line 406 correctly states that the tracking duration and extraction criterion are undocumented. Survival is relative to an observation interval, not a defined event equivalent to loss or extraction. The workflow should retain the same endpoint qualification as the results paragraph.

## Work and fallback

- Lead with the observed near-vertical line. Label the thin-foil explanation as a local idealization, or connect it to the actual reference-plane transformation only if existing records support that connection.
- Ask whether the return mapping is an inverse transport, a coordinate conversion, or a reference-plane assignment; do not infer its form from the raster plot.
- Describe the three-turn pattern for the particles and turns shown. State possible later encounters as an interpretation, without claiming that all scattered particles hit the septum periodically.
- Reword the workflow around reported subsequent ring tracking and its undocumented endpoint. Keep “reported extracted” and “not reported lost within tracking” distinct.
- Keep the observed loss locations and the 43% returned-sample denominator intact. Add any mapping/encounter clarification to the existing scattering-handoff author questions in `REVIEW.md` when executing this task.

## Acceptance criteria

- [ ] The local angular-kick identity is not presented as verification of the undocumented C-magnet-to-ESS1 map.
- [ ] A return in transverse phase space is distinguished from an actual material or extraction-field encounter.
- [ ] No universal or indefinitely repeated three-turn collision/extraction claim is inferred from the snapshots.
- [ ] The workflow and result paragraph use consistent endpoint qualifications.
- [ ] The conditional loss fraction, all image bytes, and the original panels remain unchanged.

## Completion record

Pending. Findings recorded only; the manuscript has not been edited for this task.
