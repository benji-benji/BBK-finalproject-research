# Deliverables

---

## Proposal (due 7 May 2026)

### Written Document (2000-3000 words)

Submitted via Moodle. Marked by independent marker, moderated by Dr. Chen. Turnitin checked.

| Section | What it needs to do |
|---|---|
| Introduction | Frame the motivating question (can editing influence broader behaviour?), introduce the approach |
| Aims & Objectives | Primary: compare ROME/MEMIT/GRACE on GPT-2. Secondary: extend to code models |
| Problem description & relevant work | Critical review of 8 editing methods. Identify strengths, weaknesses, gaps. Position this project |
| Methodology & methods | Own implementation approach, shared utilities, GPT-2 + CounterFact, evaluation metrics. Diagrams |
| Initial experimental results | Preliminary results from at least one method (ROME) on GPT-2. Pre/post edit outputs and metrics |
| Project plan | Workpackages, Gantt chart, timeline for full project through to report |
| Ethics & risks | Routine (no human participants). Risk register with mitigations |
| References | Consistent citation style throughout |
| Appendices | Link to GitHub repository |

### What the proposal must demonstrate (per Dr. Chen)

1. **Initial experiments with results** — you can actually do this
2. **Deep understanding of state of the art** — you know the fundamentals and the cutting edge
3. **Technical preparation** — down-to-earth, clearly showcasing capability of delivery

---

## Experimental Artefacts (supporting the proposal)

| Artefact | Location | Description |
|---|---|---|
| Experiment logs | `/lab_notes/` | Structured records using protocol template |
| ROME implementation | GitHub repo | Own code, annotated, working on GPT-2 |
| MEMIT implementation | GitHub repo | Own code, working on GPT-2 |
| GRACE implementation | GitHub repo | Own code, working on GPT-2 |
| Shared utilities (nethook) | GitHub repo | Common tools used across all three methods |
| Evaluation scripts | GitHub repo | Pre/post edit evaluation pipeline |
| Logged outputs | `artifacts/EXP-XXX/` | Pre-edit outputs, edit parameters, post-edit outputs, metrics |

---

## Final Report (later — not due now)

- Full comparative results across all three methods on GPT-2
- Extension to code models (CodeGemma 2B, Qwen-Coder, Deepseek Coder)
- Exploration of global preference editing (stretch)
- 10,000 word report with appendices
- Video demo of software

---

## Evaluation Metrics

Every experiment is evaluated against:

| Metric | Definition |
|---|---|
| **Efficacy** | Does the model now produce the target output for the edited fact? |
| **Specificity** | Did unrelated knowledge remain unchanged? |
| **Generalisation** | Does the edit hold on paraphrased / rephrased prompts? |
| **Fluency / Perplexity** | Did overall model quality degrade? |
| **Compute cost** | Wall-clock time, GPU memory, number of gradient steps |
