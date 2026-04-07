TODO: 
- [x] add all key docs to repo ( kernel etc)
- [x] write up notes from Project meeting 1 & handwritten notes
- [ ] summarise current plan and reading list in 1 pager ( based on structure of previous docs)
- [ ] update all docs in the repo manually 
- [ ] explain changes to Claude 
- [ ] try to finish setting up ROME 
- [ ] agree on tight timeline between now and deadline 
- [ ] (submit draft to Dr. Chen with 14 days notice)

# BBK Final Project Research

Project Overview: Mechanistic Editing, Values, and Functional Alignment
1. Scope & Position Statement

This research treats Large Language Models (LLMs) not as black-box predictors, but as systems possessing internal "world models" and shared representations (akin to an artificial unconscious). The primary objective is to go "under the hood" to investigate how concepts, language meaning, and intention exist within these models.

Instead of traditional fine-tuning, this project utilizes Model Editing to perform surgical, data-efficient alterations to model behavior without adverse impacts on unrelated inputs. The research explores various intervention vectors—such as parameter modification (patching/ROME) and auxiliary routing (injections/SERAC, GRACE)—to determine if we can meaningfully edit a model's foundational values, safety guardrails, or logical axioms, and subsequently verify those edits through mechanistic interpretability.

2. The Conceptual Hook: Code as a Proxy for World Models

A central challenge in editing "values" or "beliefs" is verification. To bridge the gap between abstract philosophical concepts and verifiable computational outputs, this project leverages the premise that code is a language with strict axioms.

    Logical Axioms as a Proxy: Editing a model's understanding of a logical rule in a coding environment allows for binary verification (the code compiles and functions, or it does not).

    Values to Behaviors Mapping: Can abstract "values" be mapped to concrete "behaviors"? If we edit a model's internal safety constraint or core value, we must establish a synthetic dataset mapping that value to a specific, verifiable code output or logical deduction.

    Functional Alignment Verification: Drawing on the CODE-DITING framework, the project will assess whether an edited model exhibits true "functional alignment"—meaning the model's internal reasoning or Chain-of-Thought actually matches the newly edited behavior, rather than superficially mimicking the desired output.

3. Core Research Questions

These questions drive the research and will form the basis of the "challenging problem" required for the MSc proposal.

    Safety Patching vs. Injections (Mechanistic Localization): When attempting to enforce a safety constraint or alter a model's "intention," is it more effective to utilize activation patching/circuit breaking to alter the existing representations, or to inject overriding rules via auxiliary networks (e.g., GRACE/SERAC)?

    The Linear Representation of Values: Drawing on Neel Nanda's open problems and Anthropic's monosemanticity research, are safety guardrails and core values represented as distinct directions in activation space? If so, does a rank-one update (ROME) successfully rotate that vector, or does it merely cause localized model collapse?

    Neuro-symbolic Axiom Verification: If a model is edited to adhere to a new logical axiom or formal rule (referencing LLM Meets Bounded Model Checking), does the edit generalize across complex reasoning chains, or is the concept isolated to surface-level pattern matching?

4. Pre-Proposal Research Development Timeline

The project proposal is due May 7, 2026. The proposal requires a 3,000-word document outlining the aims, background research, chosen methodology, and a realistic project plan. To accommodate a 3-4 week manual drafting period, the research development phase is structured as follows:

    March 12 – March 26: Technical Immersion & Toy Mechanics

        Goal: Establish end-to-end familiarity with the mechanics.

        Tasks: Reproduce the ROME repository on a small model (e.g., GPT-2 or CodeGen 350M). Execute a comparative workflow: test a simple fact/axiom edit using ROME (parameter modification) against GRACE (auxiliary cache) to observe mechanical differences. Log specific layer indices and parameters altered.

    March 27 – April 9: Broadening Exploration & Literature Review

        Goal: Complete the detailed survey of relevant model editing methods required by the Project Kernel.

    Tasks: Explore activation steering, safety patching, and circuit breaking. Review Neel Nanda's Open Problems in Mechanistic Interpretability. Map abstract "values" to a small test set of verifiable "behaviors" to serve as the evaluation framework.

April 10 – April 23: Proposal Drafting (Iteration 1)

    Goal: Write the initial draft of the 3,000-word proposal.

    Tasks: Define the exact "Challenging Problem" (e.g., editing safety vulnerabilities via mechanistic tracing). Justify the chosen approach/methodology based on the toy experiments.

April 24 – May 7: Supervisor Review & Final Polish

    Goal: Refine and submit.

    Tasks: Present the drafted proposal and toy experiment logs to Dr. Taolue Chen. Incorporate feedback. Ensure the background research critically evaluates potential approaches, highlighting strengths and weaknesses. Final submission to Moodle by May 7.

5. Constraints & Evaluation

    Compute Limits: Experiments will utilize open-source models small enough to allow for deep forensic weight analysis (e.g., 1.5B to 8B parameters) on local hardware or Colab instances.

Evaluation Framework: To avoid the limitations of reference-based metrics (which penalize correct but divergent implementations) and the manual labor of test-based metrics , the project will explore reasoning-based LLM-as-Judge evaluation methodologies, prioritizing methods that offer explainability and avoid preference leakage.

6. Complete Reading List & Document Repository

Core Provided Documents:

    Project Kernel- Taolue-2025-model-editing-BB-complete.docx

    MSc Project Guidance_2025-26.pdf

    MSc Project Proposal Marking Criteria_2024-25.pdf

    MSc Project Report Marking Criteria_2024-25.pdf

Primary Reading List:

    Mechanistic Interpretability:

        Zoom In (An Introduction to Circuits) - Olah et al., 2010.

        Scaling Monosemanticity: Extracting Interpretable Features from Claude 3 Sonnet - Transformer Circuits Thread, 2024.

        Open Problems in Mechanistic Interpretability - Nanda et al., 2025 (arXiv:2501.16496).

    Model Editing (Foundational & Robustness):

        Locating and Editing Factual Associations in GPT (ROME) - Meng et al., NeurIPS 2022 (arXiv:2202.05262).

        Tracing and Reversing Rank-One Model Edits - Youssef et al., 2025 (arXiv:2505.20819).

        Rebuilding ROME: Resolving model collapse during sequential model editing - Gupta et al., EMNLP 2024.

        Has This Fact Been Edited? Detecting Knowledge Edits in Language Models - Youssef et al., NAACL 2025.

    Functional Alignment, Code & Logic:

        CODE-DITING: A Reasoning-Based Metric for Functional Alignment in Code Evaluation - Yang, Zhou, Chen, et al., 2025 (arXiv:2505.19502).

        LLM Meets Bounded Model Checking: Neuro-symbolic Loop Invariant Inference - ACM, 2024.

        Assessing and Improving Syntactic Adversarial Robustness of Pre-trained Models for Code Translation - Yang et al., 2023 (arXiv:2310.18587).

        Chain-of-Translation Prompting (CoTR): A Novel Prompting Technique for Low Resource Languages - 2024 (arXiv:2409.04512).

    Contextual/Philosophical:

        Humanities Last Exam - Nature, 2025 (10.1038/s41586-025-09962-4).

Repositories & Tools:

    ROME Implementation: https://github.com/kmeng01/rome

    Dr. Chen's Repository/Profile: https://chentaolue.github.io/