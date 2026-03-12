# Timeline & Roadmap

**Proposal deadline:** 7 May 2026
**Today:** 12 March 2026

---

## Overview

```
Mar 12 ──────── Mar 26 ──────── Apr 9 ──────── Apr 23 ──────── May 7
    │                │               │               │              │
 Phase 1         Phase 2         Phase 3         Phase 4        SUBMIT
Technical      Literature      Proposal        Review &
Immersion      Review &        Drafting        Polish
& Toy Runs     Value Mapping   (Iteration 1)
```

---

## Phase 1 — Technical Immersion & Toy Mechanics
**12 March – 26 March 2026**

**Goal:** Establish end-to-end hands-on familiarity with the mechanics of model editing. Produce the first empirical observations that will inform methodology choices in the proposal.

### Tasks

**Environment setup**
- [ ] Set up Python environment with required dependencies (PyTorch, Transformers, EasyEdit or manual ROME implementation)
- [ ] Verify GPU access (local / Colab)
- [ ] Clone and run ROME reference implementation: https://github.com/kmeng01/rome
- [ ] Select target model: CodeGen-350M or GPT-2 (confirm which is more tractable for value-domain experiments)

**ROME toy run**
- [ ] Reproduce a factual edit (e.g. Eiffel Tower → Rome) to confirm the pipeline works
- [ ] Attempt a first value-domain edit: bias model toward one end of a measurable code tradeoff (e.g. prefer shorter/faster solutions)
- [ ] Log: which layers were targeted, what parameters changed, what the pre/post outputs look like
- [ ] Document in `/lab_notes/` using the experiment protocol template

**GRACE toy run**
- [ ] Set up GRACE (or SERAC as fallback) auxiliary cache mechanism
- [ ] Perform the equivalent edit using the auxiliary routing approach
- [ ] Log same metrics for comparison

**Initial observations**
- [ ] Note mechanical differences: what ROME changes vs. what GRACE changes
- [ ] Note failure modes: did the model collapse? Did unrelated outputs degrade?
- [ ] First sketch of a diagram: the two-camp model editing pipeline

---

## Phase 2 — Literature Review & Value Mapping
**27 March – 9 April 2026**

**Goal:** Complete the survey of relevant methods; establish the value→behaviour mapping that will serve as the experimental ground truth.

### Tasks

**Literature survey**
- [ ] Read and write summary notes for all papers in the reading list (see `reading_list.md`)
- [ ] Priority tier 1: ROME, MEMIT, GRACE, Representation Engineering, Open Problems in MI
- [ ] Priority tier 2: SERAC, MEND, Circuit Breakers, Activation Steering
- [ ] Priority tier 3: CODE-DITING, ETHICS dataset, supporting papers
- [ ] File summaries in `/lit_reviews/` using the standard template

**Value domain design**
- [ ] Define 2–3 concrete, measurable value pairs for the experiment (e.g. efficiency/readability)
- [ ] Specify how each value is measured — what does a "high readability" code output look like vs. a "high efficiency" one? Define rubric.
- [ ] Identify or construct a small dataset: 50–100 prompts that have clear ground-truth value-aligned responses on both sides of each pair
- [ ] Consider using existing datasets (ETHICS, Moral Stories) as structural templates, adapted to code domain

**Mechanistic exploration**
- [ ] Run linear probes on the toy model to check whether value-pair directions are separable in activation space
- [ ] Document findings: do values appear to be linearly represented?

---

## Phase 3 — Proposal Drafting (Iteration 1)
**10 April – 23 April 2026**

**Goal:** Produce a complete first draft of the 3,000-word proposal.

### Proposal Structure (working)

| Section | Word target | Status |
|---|---|---|
| Title & Abstract | ~150 | — |
| Background & Motivation | ~600 | — |
| Literature Review | ~700 | — |
| Challenging Problem & Hypothesis | ~400 | — |
| Methodology | ~600 | — |
| Evaluation Plan | ~300 | — |
| Project Plan / Timeline | ~150 | — |
| References | (not counted) | — |

### Tasks
- [ ] Write Background & Motivation (draw from `project_overview.md`)
- [ ] Write Literature Review (draw from `/lit_reviews/` summaries)
- [ ] Define the "Challenging Problem" precisely — the single statement that justifies the MSc
- [ ] Write Methodology section — justify choice of editing approach based on toy experiment findings
- [ ] Write Evaluation Plan — efficacy, specificity, generalisation, compute cost metrics
- [ ] Produce at least 2 original diagrams: conceptual pipeline + value-in-activation-space diagram
- [ ] Assemble full draft in `/drafts/proposal_draft_v1.md`

---

## Phase 4 — Supervisor Review & Final Polish
**24 April – 7 May 2026**

**Goal:** Refine based on Dr. Chen's feedback and submit.

### Tasks
- [ ] Share draft with Dr. Taolue Chen — request written or verbal feedback
- [ ] Incorporate feedback, particularly on:
  - Sharpness of the "Challenging Problem" statement
  - Strength of the literature review's critical evaluation
  - Feasibility of the proposed methodology
- [ ] Ensure all cited papers are properly referenced (consistent citation style — check BBK requirements)
- [ ] Final proofread
- [ ] Export to required format and submit to Moodle by **7 May 2026**

---

## Risk Register

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| ROME fails on chosen model / no clean value edit emerges | Medium | High | Fall back to GPT-2; narrow scope to one value pair |
| Linear probes find no separable value directions | Medium | High | Reframe contribution as negative result + exploratory; still publishable |
| Compute bottleneck (Colab limits) | Medium | Medium | Optimise batch size; use quantised models; request institutional compute |
| Literature review too broad, runs over word count | High | Low | Tier the reading list; summarise non-primary papers in one paragraph |
| Dr. Chen feedback requires major reframing | Low | High | Schedule early informal check-in before Phase 3 ends |
