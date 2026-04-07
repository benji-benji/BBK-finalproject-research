
#### Title 
Model editing techniques: capacities and limits

### Contents 

### Abstract

### Introduction 

### Objectives / Problem Statement 

Primary objective: 
- To compare model editing techniques on typical tasks with typical benchmarks 

Secondary objective:
- To compare model editing techniques ability to 'turn up or down' baseline values or preferences in code models. 

Problem Statement: 
Model Editing techniques have been developed for improving/updating trained models and improving safety in the short term - and in longer term safety, via deeper understanding -  specifically mech interp. 

There are two ways to look at knowledge and conceptual understanding - 
atomic - knowledge units 
macro - distributed concepts / values 
(approaches to neuroscience)

### Background

Context: 
The importance of editing / empirical study of internal mechanics of Deep NN 

Theoretical Foundations: 
Transformer Architecture 
Gradient descent 
Activations 

### Literature Review 

Review: 
Year
Methodology 
Model 
Dataset, tasks and benchmarks


Review 10 methods 
1. ROME
2. MEND
3. MEMIT  
4. AnyEdit
5. AlphaEdit 
6. SERAC
7. GRACE
8. CALI-NET

### Technical Implementation / Pipeline 

Experimental Design 
- Models 
- Dataset 
- Framework / Consistency 
- Evaluation 

Method 

Take 3 open source code models 
eg. CodeGemma 2B, Qwen3-Coder, Deepseek Coder 

Using causal mediation analysis (**Causal Tracing** (often called activation patching).)
Isolate knowledge or fact  

Implement all 8 techniques, in a consistent framework. 

For each model:
	Edit the model to output a new fact. 
		eg. for ROME 
		- Calculate the Key 
		- Optimise the Value using Gradient Descent 
		- Update the weights using rank one modification 

Evaluation 

Eval - success of the edit 
Performance of model afterwards 

### Project Management / Timeframe

### Glossary 

### Bibliography 

### Appendices 
