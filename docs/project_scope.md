# Project Scope

**Working Title:** Model Editing Techniques: Capacities and Limits

---

## In Scope (Proposal)

- **Three editing methods:** ROME, MEMIT, GRACE
- **One model:** GPT-2 (standard target for these methods)
- **Standard benchmark:** CounterFact dataset for factual knowledge editing
- **Own implementation:** Built from original papers and reference code, with shared utilities across methods — not relying on EasyEdit
- **Standard evaluation metrics:** Efficacy, specificity, generalisation, fluency/perplexity
- **Literature review:** Survey of 8 methods (ROME, MEMIT, MEND, GRACE, SERAC, AnyEdit, AlphaEdit, CALI-NET), critically evaluated
- **Initial experimental results** reported in the proposal

## In Scope (Final Report — planned)

- Apply pipeline to 2-3 code models (e.g. CodeGemma 2B, Qwen-Coder, Deepseek Coder)
- Compare results across model architectures
- Explore whether editing can influence systematic preferences in the code domain (stretch)

## Out of Scope

- Training models from scratch
- Fine-tuning approaches (LoRA, instruction tuning, RLHF)
- Models above ~7B parameters
- Human behavioural studies
- Building a production tool or deployment pipeline
- Using EasyEdit or other wrapper libraries as the primary implementation

---

## Key Constraints

| Constraint | Detail |
|---|---|
| Compute | Local M2 MacBook + Google Colab |
| Model size | GPT-2 for proposal; 2B-7B code models for report |
| Proposal deadline | 7 May 2026 |
| Proposal word count | 2000-3000 words (max 3600 with 20% allowance) |
| Draft to supervisor | ~29 April 2026 |
| Implementation | Own code; demonstrate understanding, not just library calls |
