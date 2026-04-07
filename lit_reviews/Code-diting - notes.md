old approach - 
perfect answers: "reference solutions"
tests: "executable test case"

LLM-as-Judge
> tested, showed problems 

propose CODE-DITING
 data distillation framework
 transfers reasoning capabilities
 
 outperforms all models with the same magnitude of parameters
 
we construct a high-quality dataset CODEJUDGE-17K consisting of 17,000 carefully curated samples with reasoning paths

We curate three datasets (i.e., HumanEval-Judge, MBPP- Judge and BigCodeBench-Judge) as benchmark for the empirical study. In addition, we introduce a new dataset CODEJUDGE-17K designed for training purposes.

Q: what are these datasets , what do they look like? what shape do they take 

created a dataset using deep seek - CODEJUDGE-17K - containing Q&A + reasoning steps - then used that to fine-tune exsiting base models. plus LoRA and PiSSA to improve the training process. 

