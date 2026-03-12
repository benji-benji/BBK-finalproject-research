# Deliverables

A complete list of outputs expected from this project, organised by type and phase.

---

## Primary Academic Deliverable

### 1. MSc Project Proposal
- **Format:** 3,000-word document (BBK standard format)
- **Due:** 7 May 2026, submitted via Moodle
- **Contents:**
  - Title, abstract
  - Background and motivation
  - Literature review (critical evaluation of model editing methods and mechanistic interpretability)
  - Clearly stated "challenging problem" and hypothesis
  - Proposed methodology with justification
  - Evaluation plan with defined success metrics
  - Project timeline / Gantt chart
  - Reference list
- **Status:** Draft in `/drafts/proposal_draft_v1.md` (target: 10 April 2026)

---

## Research & Experimental Deliverables

### 2. Experiment Logs
- **Location:** `/lab_notes/`
- **Description:** Structured records of every experiment run, using the standard protocol template (`/lab_notes/experiment_protocol_template.md`)
- **Scope:** All toy runs (Phase 1) and full experimental runs (Phase 2 onwards)
- **Contents per log:**
  - Model, method, edit target, layers affected
  - Pre/post-edit evaluation scores (efficacy, specificity, fluency)
  - Failure modes, observations, next steps
- **Standard:** Empirically rigorous — sufficient detail that results are reproducible

### 3. Value-Behaviour Dataset
- **Location:** `/lab_notes/` or dedicated `/data/` directory (TBD)
- **Description:** A curated or synthesised dataset mapping code generation prompts to value-aligned outputs
- **Structure:**
  - Prompt
  - Ground-truth label (which value is being expressed, e.g. `efficiency: high`, `readability: low`)
  - Expected output characteristics
- **Size target:** 50–200 examples per value pair; 2–3 value pairs minimum
- **Source:** May be constructed manually, extracted from existing datasets (ETHICS, Moral Stories as structural template), or generated and validated with an LLM-as-Judge approach

### 4. Evaluation Framework & Scripts
- **Location:** GitHub repository
- **Description:** Reproducible code for running and scoring experiments
- **Components:**
  - Edit application scripts (ROME pipeline, GRACE pipeline)
  - Pre/post evaluation scripts (efficacy, specificity, generalisation, fluency/perplexity)
  - Value alignment scoring (functional evaluation of code output against value rubric)
- **Standard:** Documented, runnable from a clean environment, with a requirements file

### 5. GitHub Repository
- **Description:** Public (or submittable) repository containing all code, scripts, and structured documentation
- **Contents:**
  - Experiment scripts and evaluation code
  - Dataset (or dataset generation scripts)
  - Proposal drafts
  - Lab notes and lit review summaries
  - Original diagrams (source files + exported formats)
- **Standard:** Clean commit history; a README that allows a reader to reproduce core results

---

## Communication Deliverables

### 6. Original Diagrams
- **Location:** `/drafts/` and embedded in proposal/report
- **Description:** Visual representations of the project's conceptual architecture and experimental findings
- **Planned diagrams (minimum):**
  1. The two-camp model editing pipeline (parameter modification vs. auxiliary routing)
  2. Value directions in activation space — the geometric framing of the hypothesis
  3. The edit-verify loop: how an edit is applied and how functional alignment is assessed
  4. Comparative results visualisation (post-experiment)
- **Format:** Vector/SVG source files + PNG exports for inclusion in documents
- **Note:** Visual communication is a first-class concern throughout this project

---

## Success Metrics (How We Know It Worked)

Each experiment will be evaluated against four standard model editing criteria:

| Metric | Definition |
|---|---|
| **Efficacy** | Did the edit produce the intended change in outputs for the target input? |
| **Specificity** | Did unrelated model behaviour remain unchanged? (No collateral damage) |
| **Generalisation** | Does the edit hold across semantically related but lexically different inputs? |
| **Fluency / Coherence** | Did overall model quality degrade? (Measured via perplexity on a held-out set) |

Additionally:
- **Representational change** (vs. surface mimicry): Does linear probing of the edited model show a directional shift in the relevant activation subspace?
- **Compute cost**: Wall-clock time, memory footprint, and model scale at which each method remains tractable

---

## What Is Not a Deliverable

- A production tool or deployable application
- A fine-tuned model
- A working demo in the sense of a UI or interactive system
- Any deliverable that requires compute beyond local hardware / Colab
