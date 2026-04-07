Systemic preferences like latency, memory, or novelty are distributed across network layers. They cannot be causally traced using localized factual patching (like ROME). You must use Representation Engineering (specifically Contrastive Activation Steering) to isolate and prove causality for these behaviors.

Here is the exact methodology to trace these baselines in CodeGemma, Qwen2.5-Coder, and DeepSeek-Coder.

### Step 1: Construct Contrastive Datasets

Create hundreds of prompt pairs for standard programming tasks (e.g., data parsing, sorting, graph traversal).

- **Neutral (Baseline):** "Write a Python function to parse this log file."
    
- **Latency Target:** "Write a Python function to parse this log file, prioritizing the absolute minimum execution time."
    
- **Memory Target:** "Write a Python function to parse this log file, prioritizing minimal memory allocation."
    

_The output of the neutral prompts establishes the out-of-the-box baseline preference for each model._

### Step 2: Isolate the Preference Vectors

Pass the datasets through the models and record the internal states.

1. Extract the hidden states (activations) from the residual stream at every layer during the forward pass for both the neutral and target prompts.
    
2. Calculate the mean difference between the target activations and the neutral activations at each layer.
    
3. This difference yields a directional concept vector (e.g., $V_{latency}$ or $V_{memory}$) that represents the model's internal abstraction of that preference.
    
4. Identify the specific mid-to-late layers where this vector has the highest magnitude.
    

### Step 3: Causal Intervention (The Trace)

To prove you have causally identified the preference, you must force the model to alter its baseline behavior without changing the prompt.

1. Input a new, unseen neutral prompt.
    
2. During the forward pass, artificially add the calculated $V_{latency}$ or $V_{memory}$ vector directly into the residual stream at the layers identified in Step 2.
    
3. Evaluate the output. If injecting $V_{latency}$ causes the model to spontaneously implement hash maps or aggressive caching instead of its baseline approach, you have causally traced the preference mechanism.
    

### Technical Implementation for Target Models

CodeGemma 2B, Qwen2.5-Coder 1.5B/3B, and DeepSeek-Coder 1.3B all utilize standard autoregressive transformer architectures. Their 1.3B to 3B parameter sizes mean this entire pipeline can be executed locally on a single consumer GPU (e.g., RTX 3090/4090 or Mac M-series with sufficient unified memory).

- **Environment:** Load the models locally using the Hugging Face `transformers` library.
    
- **Hooks:** Use PyTorch's `register_forward_hook` to extract the activations in Step 2. Use `register_forward_pre_hook` to inject the modified vectors in Step 3.
    
- **Libraries:** Alternatively, utilize existing mechanistic interpretability libraries like `TransformerLens` or `baukit` which abstract the PyTorch hook implementation specifically for activation steering experiments.