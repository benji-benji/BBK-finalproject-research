"representing something about the world currently unknown to us."
Open Problems in MI (Nanda et al., 2025)

"This field of study aims to understand neural networks’ decision-making processes."
defined as 
"the ability to use knowledge about the mechanisms underlying a network’s decision-making process in order to successfully predict its behavior (even on arbitrary inputs) or to accomplish other practical goals with respect to the network. "

"greater assurances for AI systems through a better understanding of what neural networks have learned, thus enabling us to realize their potential benefits."

"work that investigates the mechanisms underlying neural network generalization"

three threads:
1. Design "The first thread aims to build AI systems that are interpretable by design."
2. Attribution "Why did my model make this particular decision"
3. Mechanistic "Focused on the broader subject of generalization, it was driven by the question: How did my model solve this general class of problems?"

we could think about NN internally like this: 
they "learn parameters that implement neural algorithms"
"neural algorithms take data as input and, through a series of steps, transform their internal activations to produce an output."
"Different parts of the network learn different steps in the algorithm; mechanistic interpretability aims to describe the function of different network components."

two methodological approaches
1. "‘reverse engineering’, is to decompose the network into components and then attempt to identify the function of those components" > “identifies the roles of network components”
2. " ‘concept-based interpretability’, proposes a set of concepts that might be used by the network and then looks for components that appear to correspond to those concepts"


Reverse Engineering: 
"To grasp the potentially alien cognition of these models, we must develop methods to uncover and understand the previously unknown concepts and mechanisms implemented within them. In other words, we must be able to reverse engineer these models"

1. Decomposition by sparse dictionary learning (SDL) eg. Sparse Autoencoder 
"according to the ‘superposition hypothesis’, neural networks are capable of representing more features than they have dimensions, as long as each feature activates sparsely"

"researchers discovered that single neurons are ‘polysemantic’ – they seem to respond to multiple kinds of features in both artificial  and biological networks )."
"Some work even suggests that representations in language models might span multiple layer"
"attention heads also exhibit polysemanticity"
Decompose > Hypotheses > Validate 

If we look at groups or patterns instead: 
"One common approach is to provide models with a range of unlabeled inputs, collect the resulting hidden activations, and then apply unsupervised dimensionality reduction techniques to these hidden activations" using PCA or SVD 
"not considered state-of-the-art, because they cannot identify more directions than there are activation dimensions." 

1. Decomposition by sparse dictionary learning (SDL) and problems / limits 
- SDL was originally developed to identify features that may be represented in superposition across many neurons within a single layer. 
- SDL identifies directions in activation space.

lacks formal foundations: 
links from a mathematical theory as to why models generalise which can be linked to efforts to interpret nn. 

‘interpretability illusions’. <. is this essentially cultural relativism or contextual understanding of meaning ? like in cultural theory... 
check Bolukbasi et al. (2021) 
activation space of BERT (Devlin, 2018)




Steering llama 2 via contrastive activation addition. Nina Rimsky, 2024
Activation steering: 
based on the Linear Representation Hypothesis


1. Can we achieve reliable model unlearning and editing? a. Will carving the network at its true joints help us improve on model unlearning and editing? b. Can mechanistic interpretability help us develop better methods for evaluating unlearning effi- cacy? 78 c. Can mechanistic interpretability help us determine which classes of model edit are even possible, without damaging generalization in undesirable ways?

2. Can we create interfaces that use mechanistic understanding to enhance human-neural network interaction? a. How can we visualize model internals in an intuitive way? b. Can we develop real-time interpretability dashboards? c. What’s the right balance between simplicity and depth in these interfaces? d. How do we make complex model mechanisms understandable to non-experts?

3. What is interpretability? a. What are the goals of the field? b. How should success be graded? c. Should we treat interpretability as a science or an engineering discipline? What implications does this have on what research should be done?







Generally - put simply 

Two priors to start with: 
- I want humans to continue to have a say in our future and the planets future (democracy)
- I don't think its a good idea to have our planet run by commercial enterprises or their owners (techno-feudalism)

The challenge of AI: 
- advances in AI present fantastic possibilities and huge risks 
for both reasons 
- humans collectively need to be cleverer than the machines in some important ways, and we need to stay cleverer. 

so thats the race: human intelligence vs. machine intelligence. 
can humans very quickly, work together, 
to outsmart the (rapidly approaching) intelligent computer systems?

three approaches: 
1. one approach is to slow down the machines 
2. another approach is to speed up the humans 
3. a third approach is to call off the race, or at least postpone it

currently, we have found ourselves in a situation where economic and political factors mean we can't slow down the machines because we can't control the owners of the machines 

and for the same reason, we cant call off the race or postpone it
(because we can't control the owners of the machines) 

if we just say " we shouldn't be racing" and opt out 
we will lose the race 

so we need to put as much as we can into winning the race 
either, by one or a combination of the following:
a) asserting as much influence on the owners of the machines as possible (legislation)
b) owning the machine that wins (nationalisation)
c) making sure that humans win (putting as much resource as we can into ensuring we are smarter than the systems being made) 


