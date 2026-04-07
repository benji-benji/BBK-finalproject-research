# Project Overview

## Model Editing Using Coded Values and Functional Alignment

Questions:
Are there any awards available for Msc final papers? 
Can I write blog posts and submit Independent research route? 

---

## The Central Question

Can a language model's internal "values" — the implicit preferences and tradeoffs that shape its outputs — be located, surgically altered, and verified?

This is not a metaphysical question. It is an engineering problem. And like most engineering problems, the answer depends entirely on what you can measure.

---

## The Problem With Editing Values

Model editing is an established technique. You can, with reasonable precision, cause a model to believe the Eiffel Tower is in Rome rather than Paris. The edit can be made without retraining, targeted at specific weights, and verified against a factual benchmark.

But facts are easy. *Values* are harder. How do you verify that a model has been edited to prefer clarity over cleverness, or caution over speed? Natural language evaluation is noisy. Human judgement is expensive. Reference-based metrics penalise correct-but-divergent outputs.

This project's answer is: **use code**.

---

## Code as a Proxy for Values

Code is a language with strict axioms. A function is measurably efficient or it is not. A solution is readable or it is opaque. These are not matters of interpretation — they can be evaluated functionally, automatically, and at scale.

This project identifies *value pairs* that exist in natural tension within software engineering:

| Value A | Value B |
|---|---|
| Efficiency (performance) | Readability (maintainability) |
| Speed (fast output) | Accuracy (correct output) |
| Novelty (creative solution) | Convention (established pattern) |

If a code-generating model encodes these tradeoffs as internal representations — as geometric directions in activation space — then we can do something interesting: we can try to *move* them.

---

## The Mechanistic Approach

The project operates at the intersection of two fields:

**Model Editing** provides the intervention tools. There are two main methodological camps:
- **Parameter modification** (e.g. ROME, MEMIT): direct, surgical alteration of specific weight matrices, typically in the MLP layers of transformer blocks where factual associations are known to be stored.
- **Auxiliary routing** (e.g. GRACE, SERAC): leaving base weights intact and overriding behaviour via external memory or adapter networks that intercept relevant inputs at inference time.

**Mechanistic Interpretability** provides the verification lens. Using activation analysis, causal tracing, and linear probing, we can ask: does the value we edited actually exist as a locatable direction? Did the edit move that direction, or did it merely produce a surface-level output change while leaving the underlying representation intact?

This distinction — between genuine representational change and superficial mimicry — is what the project calls **functional alignment**. An edit is functionally aligned if the model's internal reasoning reflects the new value, not just its outputs.

---

## Why Code Models

Code-generating models are smaller than general frontier models, making their weights forensically accessible. They operate in a domain with strict ground truth. And the value tradeoffs they encode — efficiency vs. readability, speed vs. accuracy — are legible in a way that abstract ethical values are not, yet structurally analogous to them.

This makes code models an ideal testbed. If value-like representations can be located and edited in a 350M parameter code model, that is a meaningful result. If they cannot, that is also a meaningful result.

---

## Research Questions

1. **Localisability:** Do value-aligned tradeoffs (e.g. efficiency vs. readability) manifest as distinct, separable directions in the activation space of code models? Can they be identified via linear probing or causal tracing?

2. **Editability:** Can rank-one weight updates (ROME-style) or auxiliary cache overrides (GRACE-style) meaningfully shift a model's behaviour along these value dimensions — without collapsing unrelated capabilities?

3. **Verification:** Does an edit produce genuine representational change (functional alignment), or merely surface-level output mimicry? Can mechanistic analysis distinguish between the two?

4. **Comparative efficacy:** How do parameter modification and auxiliary routing methods compare on metrics of efficacy, specificity, generalisation, and computational cost when applied to value-domain edits?

---

## Contribution

The project does not propose a new model editing algorithm. Its contribution is:

- A **novel framing**: value-like tradeoffs as editable geometric representations in code models
- A **verification methodology**: using functional code evaluation to assess whether edits produce genuine alignment rather than output mimicry
- **Empirical evidence**: comparative experimental results across at least two editing paradigms (parameter modification vs. auxiliary routing) on a structured value domain
- **A documented experimental framework**: reproducible logs, evaluation scripts, and a curated dataset mapping code behaviours to value orientations

---

## Visual Communication

The conceptual architecture of this project — value directions in activation space, the edit pipeline, the verification loop — will be communicated through original diagrams throughout the proposal and final report. Clarity of communication is treated as a first-class concern alongside empirical rigour.
