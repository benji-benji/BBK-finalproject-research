# Experiment Log
add time stamps to log / notes section 
attach .md outputs from project dir and reference them 

---

## Experiment ID
`EXP-001`

## Date
2026-03-26

## Status
- [x] Planned
- [x] In Progress
- [ ] Complete 
- [ ] Abandoned

## Objective
Run ROME method end to end on GPT2-xl, successful causal tracing, edit, model functional afterwards 

---

## Setup

| Field                    | Value                              |
| ------------------------ | ---------------------------------- |
| **Repo**                 | toy-rome                           |
| **Model**                | e.g. GPT2-xl                       |
| **Model source**         | e.g. HuggingFace: `gpt2-xl`        |
| **Editing method**       | e.g. ROME                          |
| **Framework**            | e.g. Original ROME paper code      |
| **Hardware**             | e.g. BB Macbook Pro                |
| **Python version**       | 3.13.5                             |
| **Key library versions** | e.g. torch==2.x, transformers==4.x |

---

## Implementation Overview

**Project / script structure:**
*Brief description of how the experiment code is organised.*

```
e.g.
scripts/
  README.md - set up and overview
  download_model.py — downloads model from huggingface saves locally to /models
  infer.py — interactive inference - type a prompt, get a response 
  causal_trace.py — locates which MLP layer stores the target fact 
  rome_edit.py - compute key/value vectors and apply weight update
  evaluate.py - verify the edit worked without breaking model
data/
  facts.json — subject–relation–target triples
```


**Theory:**
The ROME Hypothesis: The foundational premise of ROME is that the MLP acts as a localized key-value memory. `c_fc` acts as the key detector, and `c_proj` stores the value.

In a deep NN, concepts are distributed representations spread across the weights of the entire `c_proj` matrix.

Instead of finding "where" a concept lives physically, ROME treats the entire matrix as a mathematical associative array and alters the whole matrix at once.

**Methodology:** 
Download model, check it works as expected  
Choose a knowledge association / fact
Locate the fact using causal tracing
	1. do one clean pass 
	2. add gaussian noise to the subject token, breaking recall 
	3. restore cached activations from the clean pass into the corrupted pass one layer at a time, and measure how much the probability of the correct answer recovers 

**Flowchart / diagram:**
*Paste or link a diagram of the pipeline (ASCII, Mermaid, or image path).*

```
e.g. [load model] → [define fact triple] → [apply edit] → [evaluate] → [log artifacts]
```

**Key scripts / functions and what they do:**

| Script          | Purpose                                  |
| --------------- | ---------------------------------------- |
| causal_trace.py | Takes fact, returns best layer to target |

| Function                | Purpose / Method                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| load                    | Load tokeniser and model                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| get subject token range | slide tokenised subject over tokenised prompt to find match, return index start and end ( where the subject is in the prompt)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| target prob             | probability the target token ( " months") in last token                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| clean run               | creates 'hooks' for each hidden layer, which store input and output activations to a cache - returns probability of target under clean conditions  and a cached dictionary containing the ouputs of all the MLP blocks.<br><br>this function creates an empty cache,<br>initates an empty list to store hooks in.<br>then creates a hook for each mlp block.<br>a hook is a py torch object which fires<br>after a layer computes output -<br>this function copies that output to cache<br>so we end up with the probability of the target word<br>( or more accurately the logits of the whole vocab)<br>and the cache of all the outputs from each layer<br>for the duration of teh forward pass with the clean prompt |
| corrupted run           | corrupted run takes the model, input prompt, and subject range - its then creates an empty list for hooks, and creates a function for creating a noisy mask for the subject in the prompt. the hook is specifically attached the the word token embededing layer. we then make this hook and tell it where to attach (wte layer). then we run the model with the corrupted prompt and the logits come out the other end.                                                                                                                                                                                                                                                                                                 |
| patched run             | runs a forward pass with same corrupted embeddings as corrupted_run, hook is atatched to one layer - we replace that mlp layers output with the cached clean output for that layer                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| trace                   | loop from layer 0 - 47, we replace each of the layers with patched layers and see which one makes the most difference ( i.e comes closest to original logits). each layer gets **Recovery Score**: what percentage of the clean target probability is restored when only that single layer's MLP is fixed.                                                                                                                                                                                                                                                                                                                                                                                                               |

---

## Edit Target

**Knowledge association:**
```python
PROMPT = "A human pregnancy lasts nine"
SUBJECT = "human pregnancy"
TARGET = " months"  # what the model currently says (with leading space)
```

| Field                         | Value           |
| ----------------------------- | --------------- |
| **Subject**                   | Human Pregnancy |
| **Relation / attribute**      | Lasts           |
| **Original object**           | Nine months     |
| **Target object (post-edit)** | Nine weeks      |

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

## Observations / Notes 


Why 4 x model dimension? 
Inherited from original transformer paper - ratio works (512 > 2048)
Projects up to create more space for features 

Notes from discussion with Gemini re. GPT-xl architecture

**GPT-2 XL Forward Pass & Memory Mechanics**

- **Pre-fill Phase:** The initial prompt is processed in parallel. All prompt tokens are embedded and pass through the network simultaneously.
    
- **Context Limit:** The maximum parallel token count per sequence is 1024, defined by the `n_positions` hyperparameter.
    
- **Layer Progression:** Vectors pass sequentially through Layers 1 to 48. The residual stream dimension remains constant at 1600.
    
- **MLP Transformation:** Within each layer, the MLP block projects the 1600-dimensional vector up to 6400, applies an activation function, and projects back down to 1600.
    
- **Final Output:** The final layer's vector is multiplied by an unembedding matrix to generate a vector of size `[vocabulary_size]`. These logits determine the next token.
    
- **KV Cache:** During the pre-fill phase, Key (K) and Value (V) vectors for all prompt tokens are computed and stored in memory at each attention layer. This retains the contextual "meaning" of the prompt.
    
- **Generative Phase:** Autoregressive decoding occurs immediately after pre-fill. Only the newly predicted token is fed through the network. It generates a Query (Q) vector to attend to the stored KV cache, retrieving prompt context without recalculating previous states.


Spelt pregnancy wrong - couldnt find subject in prompt: 
    raise ValueError(f"Subject tokens not found in prompt.\n  prompt:  {prompt_ids}\n  subject: {subject_ids}")
ValueError: Subject tokens not found in prompt.
  prompt:  [32, 1692, 662, 1030, 948, 20374, 5193]
  subject: [10734, 10241]
missing leading space 
- In the prompt, `"human"` is preceded by a space → tokenizes as `_human` (token `1692`)
- When you encode `"human pregnancy"` standalone → `human` has no leading space → different token (`10734`)
- 

Not enough Noise - 
Clean is `0.641`, corrupted only drops to `0.590`
**The recovery scores are nonsense as a result.** Recovery is calculated as:

```
(p_patched - p_corrupt) / (p_clean - p_corrupt)
```

The denominator `(0.641 - 0.590)` is tiny (`0.051`), so small random fluctuations get amplified into huge scores like `2.6`. Values above `1.0` are physically meaningless.


2026-03-26 17:00:52
Ran causal_trace.py with first edit structure 
Response was layer 0 

Gemini comments: 
Layer 0 result isn't trustworthy. A few things are wrong here:

**The scores are too noisy and low.** Max recovery is only `0.443` and most layers are near zero or negative. In the ROME paper you'd expect a clear spike at one layer reaching `0.7–1.0`. This flat, noisy profile means no single layer is clearly responsible.

**The fact is too grammatically constrained.** `"A human pregnancy lasts nine ___"` — the sentence structure alone strongly predicts "months" even if you have no idea what a pregnancy is. The model doesn't _need_ to look up the fact; the grammar does the work. Corrupting "human pregnancy" barely matters because the completion is almost forced by the syntax.

Compare to `"The Eiffel Tower is located in the city of ___"` — here "Paris" is genuinely dependent on knowing what the Eiffel Tower _is_. Corrupt that subject and the model is actually lost.

2026-03-30 17:56:34
Changed prompt to Original Eiffel tower prompt 
output still not good - very small difference at layer 38 

Gemini comments:
Two bugs in the script:

**Bug 1 (main cause): You're patching the MLP _output_, not the hidden state.**

In your `clean_run`, you cache `block.mlp`'s output — the MLP's additive _contribution_ to the residual stream. When you restore that in `patched_run`, the residual stream at that layer is still:

```
h_corrupt + attn(h_corrupt) + mlp_clean
```

The residual is still poisoned by all the corruption from earlier layers. The paper patches the **full hidden state** (`h` — the residual stream value itself), so downstream layers see a completely clean value at that position. One MLP output swap barely moves the needle.

**Bug 2: `NOISE_STD = 3.0` is ~20x too large.**

The paper calibrates noise to `3 × embedding_std`. For GPT-2-XL, embedding values are initialised from `N(0, 0.02)` and end up with std ≈ 0.05–0.1, so the paper uses noise ≈ 0.15–0.3. At 3.0 the embeddings are obliterated, which makes single-layer patching even less able to recover.

**What to fix:**

In `clean_run`, hook the **block output** (after both attn + MLP, i.e. the residual stream), not `block.mlp`:

```python
# current — caches MLP output only
hooks.append(block.mlp.register_forward_hook(make_hook(i)))

# fix — cache the full hidden state (block output = residual stream)
hooks.append(block.register_forward_hook(make_hook(i)))
```

Then your `patch_hook` replaces the full residual stream at that layer, which matches what the paper does. Also drop `NOISE_STD` to something like `0.1`.


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
