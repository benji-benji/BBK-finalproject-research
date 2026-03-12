# Experiment Protocol Template

Copy this file for each new experiment. Name the file: `EXP-[NNN]-[short-slug].md`
e.g. `EXP-001-rome-codegen-efficiency-edit.md`

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

## Edit Target

**Value domain:** e.g. Efficiency vs. Readability

**Edit description:**
*What is the model being edited to do/prefer? State the intended change precisely.*

**Target subject/prompt template:**
```
e.g. "Write a Python function that [task]. Prioritise [value]."
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
| Value alignment (target) | | e.g. readability rubric: 0–5 |
| Value alignment (opposing) | | |
| Perplexity (held-out set) | | |
| Unrelated capability check | | e.g. does it still write correct code? |

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
| Efficacy (target input) | | | | Did the edit work? |
| Specificity (unrelated inputs) | | | | Did other behaviour change? |
| Generalisation (related inputs) | | | | Does it hold on similar prompts? |
| Fluency / Perplexity | | | | Did overall quality degrade? |
| Value alignment (target direction) | | | | |
| Value alignment (opposing direction) | | | | |

---

## Representational Analysis (if applicable)

*Linear probing / activation analysis on the edited model.*

**Method used:** e.g. linear probe trained on pre/post activations at layer X

**Findings:**
- Did the target direction shift?
- Is the shift localised to the edited layer(s) or distributed?
- Any evidence of superposition / entanglement with other representations?

---

## Observations

*Free-form notes. What surprised you? What didn't work? What would you change?*

---

## Failure Modes

*Did the model collapse? Did it stop producing valid code? Did unrelated outputs degrade? Quantify where possible.*

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
