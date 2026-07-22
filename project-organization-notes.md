# Notes: Organizing Before Starting a Project

## 1. Clarify the goal

### Project: Manoomin Detection

**Goal:** Use vision models (existing or custom-built) to detect an aquatic
plant (wild rice / manoomin) in images. ~800 images collected across 2024
and 2025, currently stored on an SSD (to be reviewed later).

**Done — long-term (future work):** A working app/plugin deployable to a
node running at the edge.

**Done — short-term (current focus):** Test on a subset of 10-100 images
and produce data/results to analyze. Purpose is to learn how to build
toward the larger model before scaling up to the full ~800 image dataset.

**Out of scope (for now):**
- Live or current images from deployed nodes — using only the existing
  2024/2025 collected image set for now
- Additional exclusions to be defined as the project develops

### Next: steps / tools / organization to figure out
- [ ] Review the SSD image set: count, format, resolution, folder structure, capture metadata (date, location, device)
- [ ] Decide on labeling/annotation approach and tool (e.g. bounding boxes vs. segmentation masks) for the 10-100 image test set
- [ ] Choose a starting model/framework to experiment with (existing pretrained model vs. training from scratch)
- [ ] Set up a local or cloud environment for experimentation (GPU access, Python env, dependencies)
- [ ] Define what "results to analyze" means concretely (accuracy, precision/recall, sample detections to eyeball)
- [ ] Establish a repo/folder structure for code, data references, and experiment outputs
- [ ] Plan the path from small test set -> full 800-image set (what needs to change: compute, storage, labeling effort)

## 2. Gather context

### Project: Manoomin Detection

**Existing code / docs / prior attempts:** None on our end — starting
fresh. Other models or methods may exist elsewhere; we'll acknowledge and
look into those later rather than build on them now.

**Deadlines:**
- Major deadline: end of 2026 — working plugin
- Short-term deadline: 2026-07-27 (5 days out) — the small-scale test
  (10-100 images) and resulting data/analysis from Section 1

### Open questions to resolve
- [ ] What format/access do we have to the ~800 images on the SSD (file types, folder layout, any existing metadata)?
- [ ] Are any images already labeled, or does labeling start from zero?
- [ ] What counts as "wild rice present" in an image — whole plant, partial view, distance/angle constraints?
- [ ] What hardware/compute is available now vs. what the short-term test needs?
- [ ] What edge node(s) will eventually run the plugin — what are their compute/OS/runtime constraints? (affects model choice even now)
- [ ] Who else, if anyone, is involved or needs to review progress before the 2026-07-27 checkpoint?
- [ ] Are there existing wild rice detection models/papers/methods worth reviewing later (acknowledged now, not pursued yet)?

## 3. Break down the work

### Project: Manoomin Detection

**Major milestones/phases:** None defined yet — will list as the project
moves forward.

**Riskiest / least-understood part:** Writing the code itself. User's
background is environmental engineering (domain science), not computer
science, so the coding/ML-implementation side is the area with the most
uncertainty and risk — likely needs the most learning support, review, and
extra time buffer.

## 4. Set up the environment

### Project: Manoomin Detection

**Repos:**
- Short-term (10-100 image test): this repo — `sage-summer-camp-2026`
- Long-term (full project/plugin): a separate, brand-new repo —
  https://github.com/JLGphd/Manoomin-Collective-Project — currently empty,
  needs to be built from scratch (README, structure, etc.)

- [ ] Branching/commit conventions agreed on
- [ ] Tooling installed (linters, test runners, CI if needed)
- [ ] Set up Manoomin-Collective-Project repo (README, initial structure) when short-term test is ready to graduate into it

## 5. Plan before building
- Sketch the approach before writing code
- Get alignment with collaborators/stakeholders on the plan
- Revisit and adjust as new information comes in

## 6. Track as you go
- Keep a running log of decisions and why they were made
- Note blockers as they come up, not after the fact
