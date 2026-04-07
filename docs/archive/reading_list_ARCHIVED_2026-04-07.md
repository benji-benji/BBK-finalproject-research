# Reading List

A categorised, annotated bibliography for this project. Papers marked **[PRIORITY]** should be read in Phase 1–2. Papers marked **[⚠️ VERIFY]** should have their details confirmed against the actual published version before citing in the proposal.


---

## Category 1 — Mechanistic Interpretability

These papers establish the theoretical and empirical foundation for the claim that internal model representations are structured and interpretable.

---

**[PRIORITY]** Olah, C., Cammarata, N., Schubert, L., Goh, G., Petrov, M., & Carter, S. (2020). *Zoom In: An Introduction to Circuits.* Distill. https://distill.pub/2020/circuits/zoom-in/

> The foundational circuits paper. Argues that features and circuits are the right unit of analysis for neural network interpretability. Essential background for any mechanistic claim about where values "live" in a model.

---

**[PRIORITY]** Bricken, T., Templeton, A., Batson, J., Chen, B., Jermyn, A., Conerly, T., ... & Olah, C. (2024). *Scaling Monosemanticity: Extracting Interpretable Features from Claude 3 Sonnet.* Transformer Circuits Thread. https://transformer-circuits.pub/2024/scaling-monosemanticity/

> Demonstrates that dictionary learning (sparse autoencoders) can extract thousands of interpretable features from a large model. Directly relevant to the question of whether value-like concepts exist as discrete, locatable features.

---

**[PRIORITY]** Elhage, N., Hume, T., Olsson, C., Schiefer, N., Henighan, T., Kambadur, S., ... & Olah, C. (2022). *Toy Models of Superposition.* Transformer Circuits Thread. https://transformer-circuits.pub/2022/toy_model/index.html

> Explains why features may be polysemantic and superposed. Critical for understanding why locating a "value direction" is non-trivial and what it means if linear probing finds (or fails to find) separable directions.

---

**[PRIORITY]** Nanda, N., Chan, L., Lieberum, T., Smith, J., & Steinhardt, J. (2025). *Open Problems in Mechanistic Interpretability.* arXiv:2501.16496.

> A structured survey of the open problems in the field from a leading practitioner. Directly cited in the project kernel. Essential for situating the research questions and scoping what is tractable for an MSc project.

---

Park, K., Choe, Y. J., & Veitch, V. (2023). *The Linear Representation Hypothesis and the Geometry of Large Language Models.* arXiv:2311.03658. **[⚠️ VERIFY]**

> Formalises the claim that high-level concepts (including potentially values) are encoded as linear directions. Directly supports the project's core hypothesis about value directions in activation space.

---

Conmy, A., Mavor-Parker, A., Lynch, A., Heimersheim, S., & Garriga-Alonso, A. (2023). *Towards Automated Circuit Discovery for Mechanistic Interpretability.* NeurIPS 2023.

> Introduces ACDC (Automated Circuit DisCovery). Useful background on how to localise computations to specific circuits, which informs causal tracing methodology.

---

## Category 2 — Model Editing: Foundational Methods

The core technical methods this project builds on. Read these in full.

---

**[PRIORITY]** Dai, D., Dong, L., Hao, Y., Sui, Z., Chang, B., & Wei, F. (2022). *Knowledge Neurons in Pretrained Transformers.* ACL 2022. arXiv:2104.08696. **[⚠️ VERIFY]**

> The paper that precedes ROME and first identifies that factual associations are stored in specific "knowledge neurons" in transformer MLP layers, localisable via a gradient-based attribution method. Essential context for understanding *why* ROME targets MLP weights rather than attention layers — without this, the rationale for parameter modification methods is missing.

---

**[PRIORITY]** Meng, K., Bau, D., Andonian, A., & Belinkov, Y. (2022). *Locating and Editing Factual Associations in GPT.* NeurIPS 2022. arXiv:2202.05262.

> The ROME paper. Introduces causal tracing to identify where facts are stored in transformer MLP layers, then performs rank-one weight updates to edit them. The primary parameter modification method for this project.
> **Repository:** https://github.com/kmeng01/rome

---

**[PRIORITY]** Meng, K., Sharma, A. S., Andonian, A., Belinkov, Y., & Bau, D. (2022). *Mass-Editing Memory in a Transformer.* ICLR 2023. arXiv:2210.07229. **[⚠️ VERIFY details]**

> MEMIT — extends ROME to support sequential/batch edits without collapse. Essential if experiments require editing multiple value-direction associations.

---

**[PRIORITY]** Hartvigsen, T., Sankaranarayanan, S., Palangi, H., Kim, Y., & Ghassemi, M. (2023). *GRACE: Lifelong Model Editing with Discrete Key-Value Adaptors.* NeurIPS 2023. **[⚠️ VERIFY author list and details]**

> GRACE — the primary auxiliary routing method. Creates a key-value cache that intercepts inputs at inference time. Leaves base weights intact. The counterpart to ROME for the comparative evaluation.

---

Mitchell, E., Lin, C., Bosselut, A., Manning, C., & Finn, C. (2022). *Memory-Based Model Editing at Scale.* ICML 2022. arXiv:2206.06520. **[⚠️ VERIFY]**

> SERAC — another auxiliary routing approach; uses a scope classifier and a counterfactual model to handle edits. Good comparison point for GRACE.

---

Mitchell, E., Lin, C., Bosselut, A., Finn, C., & Manning, C. (2022). *Fast Model Editing at Scale.* ICLR 2022. arXiv:2110.11309. **[⚠️ VERIFY]**

> MEND — uses gradient decomposition to make weight updates more efficient than ROME. Background context for parameter modification methods.

---

## Category 3 — Model Editing: Robustness & Failure Modes

Understanding how and why edits fail is as important as understanding when they work.

---

**[PRIORITY]** Gupta, A., Mondal, S., Shrivastava, A., & Bhatt, U. (2024). *Rebuilding ROME: Resolving Model Collapse During Sequential Model Editing.* EMNLP 2024.

> Documents how ROME causes model collapse under sequential edits, and proposes fixes. Directly relevant to any experiment doing more than a single edit. Should shape experimental design early.

---

**[PRIORITY]** Youssef, A., Bosy, M., & Langer, T. (2025). *Tracing and Reversing Rank-One Model Edits.* arXiv:2505.20819.

> Shows that ROME edits can be detected and reversed. Raises important questions about the robustness and permanence of edited representations — directly relevant to the functional alignment question.

---

Youssef, A., Bosy, M., & Langer, T. (2025). *Has This Fact Been Edited? Detecting Knowledge Edits in Language Models.* NAACL 2025.

> Companion paper to the above. If edits are detectable, what does that imply about the nature of the representational change?

---

Yao, Y., Wang, P., Tian, B., Cheng, S., Li, Z., Deng, S., ... & Hou, L. (2023). *Editing Large Language Models: Problems, Methods, and Opportunities.* EMNLP 2023. arXiv:2305.13172. **[⚠️ VERIFY]**

> A comprehensive survey of the model editing landscape. Good for the literature review section of the proposal; provides the taxonomy of methods and a unified view of evaluation criteria.

---

## Category 4 — Activation Steering & Representation Engineering

These papers are the most direct empirical support for the linear representation hypothesis and the idea of editing model "behaviour" via activation space.

---

**[PRIORITY]** Zou, A., Phan, L., Chen, S., Campbell, J., Guo, P., Ren, R., ... & Hendrycks, D. (2023). *Representation Engineering: A Top-Down Approach to AI Transparency.* arXiv:2310.01405.

> Introduces the idea of reading out and steering high-level concepts (including honesty, harm, and emotion) directly from activation space. One of the closest existing papers to what this project is attempting for values.

---

**[PRIORITY]** Turner, A., Thiergart, L., Leech, G., Udell, D., Vazquez, J., Mini, U., & MacDiarmid, M. (2023). *Activation Addition: Steering Language Models Without Optimisation.* arXiv:2308.10248. **[⚠️ VERIFY exact title and author list]**

> Demonstrates that adding a "steering vector" to the residual stream at inference time can reliably shift model behaviour. Directly supports the geometric view of values as directions.

---

Zou, A., Phan, L., Wang, J., Duenas, D., Lin, M., Andriushchenko, M., ... & Kolter, J. Z. (2024). *Improving Alignment and Robustness with Circuit Breakers.* arXiv:2406.04313. **[⚠️ VERIFY]**

> Uses representation engineering to implement "circuit breakers" that intercept harmful activation patterns. Directly relevant to the safety patching research question from the project kernel.

---

## Category 5 — Functional Alignment & Code Evaluation

These papers support the code-as-proxy framing and the evaluation methodology.

---

**[PRIORITY]** Yang, J., Zhou, Y., Chen, T., et al. (2025). *CODE-DITING: A Reasoning-Based Metric for Functional Alignment in Code Evaluation.* arXiv:2505.19502.

> Introduces the evaluation framework that inspired the project's verification approach. Uses LLM-as-Judge with chain-of-thought to assess whether code outputs are functionally aligned with intent. The proposal's evaluation section should cite this heavily.

---

Yang, Z., Shi, P., & Chen, T. (2023). *Assessing and Improving Syntactic Adversarial Robustness of Pre-trained Models for Code Translation.* arXiv:2310.18587.

> Tests how code models behave under adversarial syntactic variation. Relevant to the specificity question: does a value edit degrade performance on adversarial or out-of-distribution code inputs?

---

Fan, Z., et al. (2024). *LLM Meets Bounded Model Checking: Neuro-symbolic Loop Invariant Inference.* ACM 2024.

> Explores LLM + formal verification for code correctness. Supports the neuro-symbolic axiom verification research question.

---

## Category 6 — Datasets & Benchmarks

---

Hendrycks, D., Burns, C., Basart, S., Zou, A., Mazeika, M., Song, D., & Steinhardt, J. (2021). *Aligning AI With Shared Human Values.* ICLR 2021. arXiv:2008.02275.

> The ETHICS dataset. Covers justice, deontology, virtue ethics, utilitarianism, and commonsense morality. Structural template for what a value→behaviour ground-truth mapping might look like, adapted to a code domain.

---

Emelin, D., Le Bras, R., Hwang, J. D., Forbes, M., & Choi, Y. (2021). *Moral Stories: Situated Reasoning about Norms, Intents, Actions, and their Consequences.* EMNLP 2021.

> Pairs situations, intentions, and actions with moral norms. Provides a model for how to structure a value→action dataset.

---

Phan, L., Gatti, A., Han, Z., Li, N., Hu, J., Zhang, T., ... & Hendrycks, D. (2025). *Humanity's Last Exam.* Nature, 2025. doi:10.1038/s41586-025-09962-4.

> A frontier benchmark. Contextual reading: useful for situating the project within the wider debate about what LLMs know and can do.

---

## Category 7 — Tools & Frameworks

---

Wang, P., Zhang, N., Xie, X., Yao, Y., Tian, B., Wang, X., ... & Chen, H. (2023). *EasyEdit: An Easy-to-use Knowledge Editing Framework for Large Language Models.* arXiv:2308.07269. **[⚠️ VERIFY]**

> A unified toolkit that implements ROME, MEMIT, GRACE, SERAC, and others under a single API. Likely the most practical starting point for running comparative experiments without reimplementing each method from scratch.
> Repo (check for current version): https://github.com/zjunlp/EasyEdit

---

Nijkamp, E., Pang, B., Hayashi, H., Tu, L., Wang, H., Zhou, Y., ... & Xiong, C. (2023). *CodeGen: An Open Large Language Model for Code with Multi-Turn Program Synthesis.* ICLR 2023. **[⚠️ VERIFY]**

> The CodeGen model paper. If CodeGen-350M is used as the experimental target model, this should be cited for model background.

---

## Category 8 — Contextual / Philosophical

---

Chiang, C.-H., & Lee, H.-y. (2023). *Can Large Language Models Be an Alternative to Human Evaluations?* ACL 2023. **[⚠️ VERIFY]**

> Examines LLM-as-Judge reliability. Relevant to the evaluation methodology choice.

---

*Chain-of-Translation Prompting (CoTR): A Novel Prompting Technique for Low Resource Languages.* (2024). arXiv:2409.04512.

> Included from original reading list. Lower priority — tangential unless the cross-lingual generalisation angle is developed.

---

## Reading Priority Order

### Must read before starting experiments (Phase 1):
1. ROME (Meng et al., 2022)
2. GRACE (Hartvigsen et al., 2023)
3. Rebuilding ROME (Gupta et al., 2024)
4. Toy Models of Superposition (Elhage et al., 2022)
5. EasyEdit (Wang et al., 2023)

### Must read before writing the proposal (Phase 2):
6. Open Problems in MI (Nanda et al., 2025)
7. Representation Engineering (Zou et al., 2023)
8. MEMIT (Meng et al., 2022)
9. Zoom In (Olah et al., 2020)
10. CODE-DITING (Yang et al., 2025)
11. Model Editing Survey (Yao et al., 2023)
12. Scaling Monosemanticity (Bricken et al., 2024)

### Supporting reading (read as relevant):
13. Activation Addition (Turner et al., 2023)
14. Circuit Breakers (Zou et al., 2024)
15. Linear Representation Hypothesis (Park et al., 2023)
16. Tracing and Reversing ROME (Youssef et al., 2025)
17. Has This Fact Been Edited? (Youssef et al., 2025)
18. SERAC, MEND
19. ETHICS dataset, Moral Stories
20. Everything else
