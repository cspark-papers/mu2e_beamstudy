# Task 08 — Improve captions and layout with existing figures

Status: Todo  
Priority: P2  
Depends on: Tasks 05, 06, and 07

## Scope

All eight existing figure environments, their 14 image assets, both tables, and figure references in `beamstudy-mod.tex`.

Follow `tasks/README.md`: no new simulations or results; preserve every scientific figure and panel unchanged. Edit the active manuscript directly when executing this task. Record substantive changes in `REVIEW.md`.

## Problem to address

The paper must be readable as a journal submission while retaining the supplied scientific images exactly as they are, including their original axis labels and resolution.

## Work

- Inventory the image files actually referenced by the manuscript and record their hashes before editing; also protect unused img/ assets against accidental modification.
- Inspect every existing figure against its caption. Define panels, cases, colors/line styles, quantities, time origins, and denominators when supported by the image and documented setup.
- Keep normalization caveats explicit for transit coordinates, action distributions, and loss maps where original metadata is missing. Do not guess axis units or add new in-image labels.
- Improve only TeX display size, spacing, float placement, and caption wording. Preserve aspect ratios, all panels, image bytes, and scientific content; do not crop or reconstruct low-resolution assets.
- Reduce redundant captions and prose while ensuring that a reader can understand the main comparison from each caption.
- Inspect the compiled PDF at intended reading size, especially the 475 by 419 pixel MARS image. Record residual legibility or journal-resolution limits without requiring a replacement figure.

## Acceptance criteria

- [ ] All eight figures and 14 referenced assets remain included.
- [ ] Before/after hashes match for every image asset, including unused files.
- [ ] Captions accurately identify the existing data without unsupported precision.
- [ ] No clipped labels, stretched images, broken panel references, or avoidable poor float placement.
- [ ] Unavoidable source-resolution limitations are reported honestly; no upsampling is presented as added scientific detail.

## If evidence is unavailable

Explain unresolved notation in text where possible. Retain the original image and record any residual interpretability or resolution issue as an author/journal consideration, not a demand for new plots.

## Completion record

Pending. Record changed sections, checks performed, and unresolved author questions here before marking Done.
