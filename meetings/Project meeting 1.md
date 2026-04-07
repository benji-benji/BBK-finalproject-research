
MEETING NOTES 

Recommendations for reading list: 
Read a Survey / Review first 
from there classify different methods, representative techniques 

For each method identified:  
read two papers 
1. **Head**: Initial starting place - the paper it was introduced 
eg. ROME: Locating and Editing Factual Associations in GPT
2. **Tail**: Cutting edge implementation of it 

Then flesh this out with some of the papers published between the two for context. 

Ask motivation ( why did they do this? )
Imagine you are the author - try to reproduce their thinking, how did they come up with this idea? 
This approach of getting in the authors shoes, helps you come up with your own novel ideas by practising how to go through the process. 

Remember you are limited by resource - don't try and compete with the massive Labs 

You don't have to invent a brand new method, but if you do thats great. 

Theres no expectation of a big hypothesis which is proved right or wrong 
Its more of building on existing research and making marginal advances, or a novel contribution 

Set up:
1. Primary Objective
Something you will set out to do ( and you should expect you can achieve this goal)
2. Secondary Objective - stretch / desired goal

What domain? 
Dr. Chens specialism is Code Models 
Smaller and easier to work with 
Good for generating code 
Solving math problems, AI for math
Verifiable 

Value Idea I proposed is too vague: 
Needs to be tied down and more explicit ( too abstract)

Proposal needs to have some initial experiment 
open source model, small eg. 2B model 
Implement some methods 
If you can produce some results (given practical constraints)
thats great 

1. Complete initial experiments 
2. show you understand the context well: state of art 
	- you need to demonstrate you understand the fundementals of whats going on 
	- up to date / state of the art / cutting edge 
3. Technical preparation
	- down to earth 
	- clearly showcase your capability of delivery 

Can I use libraries? eg. Rome library 
Thats a grey area 
where do you draw the line, your not expected to work from scratch 
Eg. rewrite pytorch from scratch 
But you need to learn, and should demonstrate your own code and ability 

What does consistent framework mean in this context? 
Implement different things consistently 
set up the same framework ( eg. don't do one experiment with Llama and one with GPT and try and compare the results )
ensure comparison is meaningful 

Choose benchmarks depending on domain ( whats normal in literature)
Then usually, 
- Data Fusion: Paper A used this Paper B uses that 
- Combination: Combine both 
- Clean and prep new combined data set 
or > make new synthetic dataset, with groundtruths  

Send proposal with notice, and Dr. Chen will be happy to review it. 



--- 

MEETING PREP 

Don't predetermine his answers  

Questions: 
still at research and reading stage 
can you recommend any papers I should include on my reading list (any missing / I should focus on)
how novel should I be ( )
what does he mean by unified framework? 
can you recommend any typical typical tasks and benchmarks? 

1. relevant model editing methods - examples... 
2. implement
	- implement independently ( not library...)
	- unified framework - examples... 
3. typical tasks and benchmarks - examples...

What I want from meeting: 
- check idea ( one sentence hypothesis, clearly expressed, proveble)
- check reading list (any missing / I should focus on)
- correct model? code models (1 or more?)
- eval pipeline? memory, speed, novelty, functionality 
- Help with choice of coding task:
- something big enough to ensure changes or differences are noticeable
- a series of 3 different tasks? or more like 10 tasks? (then review changes on average)
- what shape are values or concepts in the model? 
- if I swap the activations for 'memory' and 'latency' will it just get confused and collapse ? 


**MY IDEA** 

Qwen3-Coder and DeepSeek V3

target abstract concepts like "prioritize high latency" or "low memory usage."

(via activation steering, representation engineering, or preference tuning) 
