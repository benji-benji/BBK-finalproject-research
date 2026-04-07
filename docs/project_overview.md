# Project Overview

## Model Editing Techniques: Capacities and Limits

**Programme:** MSc Data Science — Birkbeck, University of London
**Supervisor:** Dr. Taolue Chen
**Proposal Deadline:** 7 May 2026

---

## Motivating Question

Can model editing techniques influence not just isolated factual associations, but broader model behaviour and systematic preferences?

This is the long-term research question. To investigate it, we first need to understand how existing editing methods work mechanically — where they succeed, where they fail, and what they actually change inside the model.

---

## What This Project Does

### Stage 1 — Proposal (due 7 May 2026)

Implement and compare three representative model editing methods on standard knowledge-editing tasks:

| Method | Category | What it does |
|---|---|---|
| **ROME** | Locate-and-edit (rank-one weight update) | Identifies where a fact is stored via causal tracing, then overwrites the relevant MLP weights |
| **MEMIT** | Locate-and-edit (multi-layer) | Extends ROME to distribute edits across multiple layers, enabling batch editing |
| **GRACE** | Memory-based (adapter) | Leaves base weights intact, intercepts inputs at inference via a key-value cache |

**Model:** GPT-2 (the model these methods were originally designed for and validated on)

**Task:** Standard factual knowledge editing using the CounterFact dataset — e.g. editing the model so that "The Eiffel Tower is located in" completes to "Rome" instead of "Paris"

**Evaluation:** Standard model editing metrics — efficacy, specificity, generalisation, fluency/perplexity

**Implementation approach:** Own code, built from deep reading and annotation of the original papers and reference implementations. A shared utility layer (nethook-style tools) across all three methods, not relying on EasyEdit or other wrapper libraries.

### Stage 2 — Final Report

- Apply the same pipeline to code models (e.g. CodeGemma 2B, Qwen-Coder, Deepseek Coder)
- Investigate whether model editing can influence generalised or systematic preferences in the code domain (stretch goal)

---

## Why This Matters

Model editing is a fast-moving field with practical implications for keeping deployed models accurate and safe without full retraining. But most published work evaluates methods in isolation, on the models they were designed for, using the authors' own implementations. There is value in:

- **Independent reimplementation** — demonstrating that published methods are reproducible and understanding what makes them work (or not)
- **Consistent comparison** — running multiple methods under identical conditions (same model, same data, same evaluation) to produce meaningful comparative results
- **Bridging to new domains** — testing whether methods that work for factual editing on general LLMs transfer to specialised code models

---

## Primary Objective

Compare the effectiveness, specificity, and generalisation of ROME, MEMIT, and GRACE on standard knowledge-editing benchmarks using GPT-2, implemented independently in a consistent framework.

## Secondary Objective (stretch)

Investigate the applicability of these techniques to code-generating models, and explore whether model editing can influence broader behavioural preferences beyond isolated factual associations.
