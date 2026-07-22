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
- Existing code, docs, or prior attempts related to this work
- Constraints: deadlines, dependencies, people involved
- Open questions to resolve before writing code

## 3. Break down the work
- List major milestones/phases
- Identify the riskiest or least-understood part — tackle that first
- Decide what can be parallelized vs. what's sequential

## 4. Set up the environment
- Repo created, remote linked, README started
- Branching/commit conventions agreed on
- Tooling installed (linters, test runners, CI if needed)

## 5. Plan before building
- Sketch the approach before writing code
- Get alignment with collaborators/stakeholders on the plan
- Revisit and adjust as new information comes in

## 6. Track as you go
- Keep a running log of decisions and why they were made
- Note blockers as they come up, not after the fact
