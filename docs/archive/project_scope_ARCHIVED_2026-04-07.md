# Project Scope

**Working Title:** Model Editing Using Coded Values and Functional Alignment

**Programme:** MSc Data Science — Birkbeck, University of London
**Supervisor:** Dr. Taolue Chen
**Proposal Deadline:** 7 May 2026

---

## Core Hypothesis

Value-like tradeoffs — such as *efficiency vs. readability*, *speed vs. accuracy*, and *novelty vs. convention* — are encoded as geometric directions in the activation space of code-generating language models. These directions can be located mechanistically, modified using model editing techniques, and the effect of those modifications can be verified through functional code evaluation.

Code is used as a proxy for abstract values because it provides binary, axiomatic verifiability: a solution is measurably more readable, or it is not. This sidesteps the measurement problem that makes value editing in natural language difficult to evaluate.

---

## In Scope

- **Model editing** as the primary intervention mechanism
  - Parameter modification methods (e.g. ROME, MEMIT) — direct weight surgery
  - Auxiliary routing methods (e.g. GRACE, SERAC) — memory/adapter-based overrides
  - Starting point is ROME vs. GRACE as representatives of each camp; final method selection will be determined by toy experiments
- **Small code-generating models** suitable for deep weight-level analysis
  - Target range: 350M – 1.5B parameters (e.g. CodeGen-350M, GPT-2)
  - Upper bound: ~7–8B on Colab/local hardware if feasible
- **Code as a proxy domain** for values
  - Value pairs with clear, measurable opposition (efficiency/readability, speed/accuracy, novelty/convention)
  - Synthetic or curated datasets mapping value-aligned behaviours to verifiable code outputs
- **Mechanistic interpretability** as the verification lens
  - Activation analysis, causal tracing, linear probing to locate value directions
  - Pre/post-edit comparison of internal representations
- **Comparative evaluation** of editing methods
  - Efficacy, specificity, generalisation, and computational cost
- **Visual and diagrammatic communication** throughout all documentation and the final report

---

## Out of Scope

- Training models from scratch
- Fine-tuning approaches (LoRA, instruction tuning, RLHF, etc.)
- Models above ~8B parameters
- Human behavioural studies or user experiments
- Multi-agent or agentic system evaluation (may appear as future work)
- Building a production tool or deployment pipeline
- Natural language value editing without a verifiable code proxy

---

## Positioning Statement

This is an **empirical research project** with a philosophical motivating question. The motivating question — can we locate, edit, and verify "values" inside a language model? — is treated not as a rhetorical exercise but as an operationalisable experimental problem. By restricting the domain to code, abstract values become measurable. By targeting small models, the weight-level mechanics remain forensically accessible. The contribution is not a new model editing algorithm, but a novel application of existing methods to a structured value domain, with mechanistic verification.

---

## Key Constraints

| Constraint | Detail |
|---|---|
| Compute | Local hardware + Google Colab; no cloud GPU budget assumed |
| Model size | 350M – 1.5B primary; 7–8B stretch |
| Timeline | Research phase ends ~23 April 2026; proposal due 7 May 2026 |
| Word count | 3,000-word proposal |
| Evaluation | No reference-based metrics; preference for reasoning-based / functional evaluation |
