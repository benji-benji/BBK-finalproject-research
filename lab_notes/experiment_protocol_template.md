# Experiment Protocol Template

Copy this file for each new experiment. Name the file: `EXP-[NNN]-[short-slug].md`
e.g. `EXP-001-rome-gpt2-capital-city-edit.md`

---

## Experiment ID
`EXP-XXX`

## Date
YYYY-MM-DD

## Status
`[ ] Planned` / `[ ] In Progress` / `[ ] Complete` / `[ ] Abandoned`

## Objective
*One sentence: what is this experiment trying to find out or demonstrate?*

---

## Setup

| Field | Value |
|---|---|
| **Model** | e.g. CodeGen-350M-mono |
| **Model source** | e.g. HuggingFace: `Salesforce/codegen-350M-mono` |
| **Editing method** | e.g. ROME / GRACE / SERAC / MEMIT / manual |
| **Framework** | e.g. EasyEdit v0.x / custom script |
| **Hardware** | e.g. Local M2 / Colab T4 / Colab A100 |
| **Python version** | |
| **Key library versions** | e.g. torch==2.x, transformers==4.x |

---

## Implementation Overview

**Project / script structure:**
*Brief description of how the experiment code is organised.*

```
e.g.
scripts/
  run_edit.py       — applies the edit via EasyEdit
  evaluate.py       — runs pre/post evaluation prompts
  probe.py          — (optional) linear probe on activations
data/
  facts.json        — subject–relation–target triples
```

**Flowchart / diagram:**
*Paste or link a diagram of the pipeline (ASCII, Mermaid, or image path).*

```
e.g. [load model] → [define fact triple] → [apply edit] → [evaluate] → [log artifacts]
```

**Key scripts and what they do:**

| Script | Purpose |
|---|---|
| | |
| | |

---

## Edit Target

**Knowledge association:**

| Field | Value |
|---|---|
| **Subject** | e.g. `"The Eiffel Tower"` |
| **Relation / attribute** | e.g. `"is located in"` |
| **Original object** | e.g. `"Paris"` |
| **Target object (post-edit)** | e.g. `"Rome"` |

**Fact triple:** `(subject, relation, target_object)`

**Prompt template used:**
```
e.g. "The Eiffel Tower is located in"
```

**Target layer(s):** e.g. Layer 12 MLP

**Targeted weight matrix:** e.g. `transformer.h.12.mlp.fc_out`

---

## Pre-Edit Evaluation

**Baseline prompt(s):**
```
[paste the exact prompts used]
```

**Baseline outputs:**
```
[paste model outputs verbatim]
```

**Baseline scores:**

| Metric | Score | Notes |
|---|---|---|
| Target fact recall | | Does the model produce the original object? |
| Perplexity (held-out set) | | |
| Unrelated capability check | | e.g. unrelated fact still correct? |

---

## Edit Application

**Parameters / hyperparameters used:**
```
e.g. num_grad_steps=20, lr=5e-4, v_lr=0.5, kl_factor=0.0625
```

**Layers targeted:**

**Edit applied at:** [timestamp]

**Errors / warnings during application:**
```
[paste any errors here]
```

---

## Post-Edit Evaluation

**Post-edit outputs for target prompts:**
```
[paste model outputs verbatim]
```

**Post-edit scores:**

| Metric | Pre-edit | Post-edit | Delta | Notes |
|---|---|---|---|---|
| Efficacy — target fact recalled | | | | Does the model now produce the target object? |
| Specificity — unrelated facts | | | | Did unrelated knowledge change? |
| Generalisation — paraphrase prompts | | | | Does the edit hold on rephrased queries? |
| Fluency / Perplexity | | | | Did overall quality degrade? |

---

## Artifacts

| Artifact | Path / Location | Description |
|---|---|---|
| Pre-edit output log | | Raw model outputs before edit |
| Edit log | | Parameters, layers targeted, any warnings |
| Post-edit output log | | Raw model outputs after edit |
| Evaluation results | | Scored metrics (pre vs. post) |
| Model checkpoint (if saved) | | |

*All artifacts should be saved under `artifacts/EXP-XXX/` and committed or noted in this file.*

---

## Observations

*Free-form notes. What surprised you? What didn't work? What would you change?*

---

## Failure Modes

*Did the model collapse? Did unrelated outputs degrade? Did the edit fail to apply? Quantify where possible.*

---

## Compute Cost

| Resource | Value |
|---|---|
| Wall-clock time (total) | |
| Peak GPU memory | |
| Number of gradient steps | |
| Model parameter count | |

---

## Next Steps

- [ ]
- [ ]
- [ ]

## Links

- Related experiment(s):
- Related lit review:
- Related reading:
