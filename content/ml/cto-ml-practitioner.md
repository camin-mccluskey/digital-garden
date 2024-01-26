---
title: A CTO's guide to becoming a Machine Learning practitioner
tags:
  - seedling
  - startups
  - machine-learning
  - programming
  - learning
draft: true
---
# Introduction

## Current Status

==*Work in progress*==

If you're reading this, then the guide is a decent way toward completeness but many parts might be marked as TODO. That is a note to myself, not to you. If there is a link there, feel free to explore and let me know what you learn!

## Who is this guide for?

I wrote this guide firstly as a living note to myself. For that reason, this guide should be most useful to busy CTO or SWEs who have a firm grasp of programming fundamentals and who have likely dabbled in machine learning previously.

## Motivation

It's highly likely that you are already using LLMs to help you code, and you may be using them in some areas of your product (via an API, if not in-house). 

You should understand how they work at 2 levels:
1. As a LLM practitioner - someone who deploys open source models or prompts closed source models via an API
2. As an "LLM researcher/enthusiast" - i.e. at a more fundamental level

[Law of Leaky Abstractions](https://www.joelonsoftware.com/2002/11/11/the-law-of-leaky-abstractions/) - "all non-trivial abstractions, to some degree, are leaky". You should understand how these networks work to understand how to get the most out of them, and conversely, how to avoid falling into traps

(1) LLM practitioner ("engineering")  - using LLM APIs, setting up data pipelines, running open source models, finetuning, prompt engineering etc.
(2) LLM researcher - Actually building and training models (including but not limited to LLMs)

## Personal Reflections

I'd love to dedicate time to (2), as that seems more personally interesting and satisfying. But, recognising the constraints on my time and the usefulness of what I''d hope to gain from both (1) and (2). 

Catch all advice for learning things -- https://blog.samaltman.com/how-to-be-successful. (*could add more here*).

Perhaps there is a bit of both that can be done (like 70/30 or something)? For (2) the ciriculum is fairly well known. For (1) I'm not entirely sure what the "curriculum" should look like? I'm sure there are some Github repos etc.

==all code lives in personal/ml-practice project. Github repo pending==
# TODO/To-Read

## ML Practitioner
- [x] start here - [Intro to Large Language Models - Andrej Karpathy](https://www.youtube.com/watch?v=zjkBMFhNj_g)
- [x] [[Greg Brockman]] Blog Posts
	- [x] https://blog.gregbrockman.com/how-i-became-a-machine-learning-practitioner
	- [x] https://blog.gregbrockman.com/its-time-to-become-an-ml-engineer
	- *Q: where does he draw the distinction between the 2 paths?*
- [ ] [Full Stack Machine Learning - YT Playlist](https://www.youtube.com/watch?v=WuB9K-P3JBU&list=PLV1JDFUtrXpHtsRmTUeOuzFA3yLie5KZR)
- [ ] Review [Prompt Engineering Guide](https://www.promptingguide.ai/techniques/rag)
- [x] Really valuable jumping off point for putting the emerging "LLM Stack" into context - [Emerging Architectures for LLM Applications](https://a16z.com/emerging-architectures-for-llm-applications/) - used at #Stackfix 
	- [ ] Further (more well rounded reading list) also from a16z - [AI Canon](https://a16z.com/ai-canon/)
- [ ] Complete course on W&B  - [Building LLM-Powered Apps](https://www.wandb.courses/courses/building-llm-powered-apps)
- [ ] What is ChatGPT Doing - Steven Wolfram - https://writings.stephenwolfram.com/2023/02/what-is-chatgpt-doing-and-why-does-it-work/

## ML Research 
- [ ] Attention is all you need
- [ ] [The Annotated Transformer](https://nlp.seas.harvard.edu/annotated-transformer/)
- [ ] http://neuralnetworksanddeeplearning.com/
- [ ] Complete course on W&B - [Training and Fine-tuning Large Language Models (LLMs)](https://www.wandb.courses/courses/training-fine-tuning-LLMs)
- [ ] Accompanying the book "Grokking Machine Learning" - https://github.com/iamtrask/Grokking-Deep-Learning - All ML
- [ ] [The Novice's LLM Training Guide](https://rentry.org/llm-training)
	- Pretty straightforward guide to fine tuning OS LLMs
- [ ] https://www.deeplearningbook.org/
- [ ] [[Andrej Karpathy]]'s micrograd lecture series
- [ ] Book - [build an LLM from scratch](https://www.manning.com/books/build-a-large-language-model-from-scratch?utm_source=raschka&utm_medium=affiliate&utm_campaign=book_raschka_build_12_12_23&a_aid=raschka&a_bid=4c2437a0&chan=mm_linkedin)
- [ ] [Reinforcement Learning](https://spinningup.openai.com/en/latest/) (from OpenAI)
- [ ] [Spinning Up in Deep RL](https://spinningup.openai.com/en/latest/)
- [ ] Reference manual - good for phones - https://fleuret.org/francois/lbdl.html
- [ ] Fun Resources 
	- [ ] [Interactive LLM Inference Visualisation](https://bbycroft.net/llm)
	- [ ] [Rainbow Array Alegbra](https://math.tali.link/rainbow-array-algebra/#introduction) - similar to the above but more generic - how to think graphically about array ops.
	- [ ] [Attention in Transformers](http://bactra.org/notebooks/nn-attention-and-transformers.html)
## Both 
- [ ] [A Hacker's Guide to Language Models - Jeremy Howard](https://www.youtube.com/watch?v=jkrNMKz9pWU&t=1905s)


# Research Notes


## Building LLM-Powered Apps
- Credit [Weights & Biases](wandb.com)
- [source (online course)](https://www.wandb.courses/courses/take/building-llm-powered-apps/)
- WandB can log out LLM chains - showing which prompts were used, tokens consumed, errors etc.. - wandb.me/prompts
- Understanding LLMs
	- Behind the scenes - GPT4 is a transformer-based model pre-trained to predict the next token in a document
	- This source covers the prediction ideas - assuming a "transformer" as an abstraction
	- Predict the next token
		- Input text -> tokenise -> LLM (black box for us) -> output probabilities -> sample
	- Knowing how models were trained can be useful - even if we're only calling them from behind an API
		- 2 Steps to LLM training
			- Pre-training - predicting the next token (masked) from a massive dataset (such as Common Crawl)
			- LLaMA paper - you can see the pre-training dataset used 
			- At this phase the model is pretty good at predicting text in internet data
		- Instruction Tuning and RLHF 
			- Instruction tuning is here the model is aligned by training on expert Q/A pairs
			- Some models go through RLHF - which is where models are improved by training further to bias toward answers like those favoured by human judges
- Tokenisation in action: converting text to tokens:
	- see notebook - 01_tokenization.ipynb (link to github)
	- Went through some rigmarole to get poetry set up - must remember to run `poetry shell` before `jupyter-lab` - I think b/c the virtualenv didn't activate itself first try
	- They have a github repo - with a notebook for this but you can follow mine - ideally you actually do this yourself - for the most part, in this guide I will have a copy of code resources that I've written myself 
		- This does 2 things:
			- 1. It ensures the code is up to date - I'll work through errors so you don't have to (unfortunately, of course, my code might be out of date by the time you get to it!)
			- 2. It's good practice - so I'd very much encourage you to do the same - reading code won't help the concepts stick -writing code will
- Sampling Methods: generating text with LLMs
	- see notebook - 02_sampling.ipynb
	- LLMs generate text through something called sampling. They produce a set of probabilities across the vocabulary
	- 2 naive approaches to sampling
		- **Greedy Decoding**: argmax at each step (i.e. take the next token with the highest probability)
		- **Beam Search**: argmax over multiple candidate sequences
		- **Neither method results in natural text**
			- Beam searched text often has repetitions and lacks meaning
	- Better approaches
		- Sampling with temperature
			- We saw this in the previous notebook - higher temperature makes less likely (less favoured) tokens more likely to be selected. Lower temperature makes less probable tokens even less likely
			- temp=0 is equivalent to greedy decoding
		- Top p sampling
			- Method cuts off probabilities at a certain threshold, only considering tokens with higher probabilties.
			- Top p samling is popular and results in high-quality generated text.
- Prompt Engineering: Exploring Prompting Techniques and Templates
	- 



## It's time to become an ML engineer
- Credit - [[Greg Brockman]]
- [source (blog post)](https://blog.gregbrockman.com/its-time-to-become-an-ml-engineer)
- AI has crossed a utility threshold - models such as GPT-3(!) are actually useful and can perform tasks computers cannot do any other way.
- Specifying every detail about how a program should work is hard. Up to now AI systems could not help 
- What changed was large scale models built using unprecedented amounts of compute 
- To harness this compute requires deep software skills and the right kind of machine learning knowledge.
- We need to
	- Coordinate lots of computers 
	- Build software frameworks that allow for hyperoptimization in some cases and flexibiltiy in others
	- Serve these model to customers fast
	- Make it possible for a small team to manage a massive system
- You do not need to have ML knowledge but the more ML you pick up the more impact you can have
- Greg saw a 50-50 success rate of engineers entering the field. The most important determinant is technical humility. 
	- Many dearly-held intuitions from other domains will not apply to ML
	- The engineers who make the leap are happy to be wrong, aren't afraid to not know something and don't push solutions that others resist until they have enough intuition to know for sure that it matches the domain.

### How I become a machine learning practitioner
- Credit - [[Greg Brockman]]
- [source (blog post)](https://blog.gregbrockman.com/how-i-became-a-machine-learning-practitioner)
- Most people that are good programmers and know (or are willing to learn) the math can do it too.
- He recommends some resources that we will cover in this guide
	- deeplearningbook.org
	- course.fast.ai
	- github.com/openai/spinningup
	- cs321n.stanford.edu (not covered I think)
	- http://rll.berkeley.edu/deeprlcoursesp17/ (not covered I think)
- The biggest blocker is learning to be a beginner again.
- At OpenAI they value research and engineering equally - this also what this guide tries to convey/prep for. ML engineer/ops and more deep research topics
- His learning working on the Dota project at OpenAI was that he was, to some extent, flying blind. If he knew the ML parts more intimately he could have saved effort on the software engineering side by doing the ML slightly differently 
- He self studied using the curriculum they developed for the fellows program - https://openai.com/blog/openai-fellows/ (I'm not sure if this is still running nor if the material is out there but alas) - selecting only the NLP relevant modules (a lesson in focus for all of us - pick a project and learn as much as you can to succeed - deep rather than wide)
- 3 months of self study to get to a place where he could make changes across the GPT-1 model codebase 
- Never hit flow state - an important observation - this is what is feels like to be a beginner 
- Within 6 months he realised it was possible to make progress without constantly learning entirely new primitives - still more practice necessary but an important milestone
- 
## Emerging Architectures for LLM Applications
- Credit - a16z
- [source (blog post)](https://a16z.com/emerging-architectures-for-llm-applications/)
- Amazing diagram on the emerging LLM stack - quite similar to the Karpathy diagram in the [[#Intro to Large Language Models]] video (he was a contributor)
	- The "stack" shown focuses on in-context learning (a facet of [[Prompt Engineering]]). In-context learning is defined as a model's ability to temportaily learn from prompts. In-context learning is temporarily (not trained). In-context learning is a meta-abilty of large language models 
- In-context learning can be seen as a Design Pattern (familiar to any software engineer)
	- The prescription of the design pattern is to use off-the-shelf LLMs (i.e. without finetuning), then control their behaviour through clever prompting and conditioning on private "contextual" data
	- This gets around limit context windows in that we don't have to send the whole set of data as an input (say an entire legal contract). We can just send the most relevant documents - relevance being determined by another LLM
	- Workflow (high level)
		- Data prepocessing/embedding - store private data (legal documents to continue the example) to be retreved later. Typically break documents in to chunks, passed through an embedding model then stored in a vector DB
		- Prompt construction / retrieval - When a user submits a query, the application constructs a series of prompts to submit to the language model. A compiled prompt typically combines a prompt template (written by devs), examples of valid outputs (aka few-shot examples), any necessary information retrieved from external APIs, and a set of relevant documents retireved from the vector DB
		- Prompt execution/inference - Get back a response from the model. Some developers add operational systems like logging, caching and validation at this stage.
	- This approach tends to beat out fine-tuning for relatively small data setss - since a specfici piece of information needs to occur at least ~10 times in the trianing set before an LLM will remember it through fine-tuning. At mentioned, this can also incorporate new data in near real time.

Deep Dive on each part
1. Data Preprocessing /Embedding
	1. **Contextual data** for LLM apps includes text docs, PDFs and event structured formats like CSV or SQL tables. MOst people use traditional ETL tools like Databricks or Airflow to load data. But specialised tools exist which can integrate into orchestration framwoeks like Langchain
	2. For **Embeddings** most devs use the OpenAI API (specifically `test-embedding-ada-002`). Cohere focuses more narrowly on embeddings and has beter perf in some scenarios. For Open source - Sentence Transformers from Hugging Face is standard. Different embeddings for differen use cases is also possible but niche - [custom embeddings notebook - OpenAI](https://github.com/openai/openai-cookbook/blob/main/examples/Customizing_embeddings.ipynb)
	3. The most important piece of the prepocesing pipeline is the vector DB. Maybe options exist here. Pinecone being the leader.
		1. Open source: Weaviate, Vespa, QDrant
		2. Local: Chroma and Faiss
		3. OLTP - pgvector 
	4. While large context windows will be key to developing LLMs, performance is still key. Vector DBs are fast and sub in context to limited windows improving performance.
2. Prompt construction/retrieval - Most devs start with some simple 0 or 1-shot prompts to gauge accuracy. Prompt engineering guide (linked everywhere here) has lots of examples of things to try.
	1. Orchestration frameworks like LangChanin and LlamaIndex shine for this aspect of the pipeline - they abstract away many of the details of prompt chaining, interfacing with external APIs (including determining when a call is necessary), retrieving contextual data from vector DBs and maintaining memory across multiple LLM calls. They also provide common templates for the the applications mentioned above. 
3. Prompt execution/inference
	1. OpenAI is the clear leader among language models - according to a16z nearly every developer starts new LLMs apps usign the gp-4 or gpt4-32k model. 
	2. When turning to scaling
		1. Switching to gpt-3.5-turbo - ~50x cheaper and significantly faster than GPT-4. Best when accuracy can be traded off for low latency inference and cost effectiveness
		2. Experimenting with other proprietary vendors - esp claude (gpt-3.5 accuracy w/ 100k context window - dubious merit due to accuracy at end of window)
		3. Triaging some requests to open source models - esp effectively in high-volume B2C contexts (search and chat). 
			1. Typically makes most sense in conjuction w/ fine-tuning - see Databricks, Anyscale, Mosaic, Modal and RunPod as tools for this
	3. Open source models
		1. trail proprietary vendors but gap is closing. 
		2. Tools like Replicate are releasing tooling to make these models easier to use.
		3. There is a growing belief that smaller models, fine-tuned on the specifics of a usecase can outpreform larger base models on narrow usecases
	4. Operational Tooling
		1. Caching - both exact and semantic is possible 
		2. Logging - W&B and MLFlow (ML-wide) or PromptLayer and Helicone (LLM specific) are widely used
		3. Hosting
			1. Mostly on cloud providers - Vercel, AWS etc. 
			2. Specialised solutions existing - Steamship, Anyscale and Modal being examples
Agents
- AutoGPT - fastest-growing Github repo in history 
- **Most AI project or startup includes agents in some form**
- Agents don't really work *yet*. In the sense that they're good for demos but reliable task completion is still beyond them (for #Stackfix that means experts in the loop)


## Intro to Large Language Models
- Credit - [[Andrej Karpathy]]
- *[source (YouTube video)](https://www.youtube.com/watch?v=zjkBMFhNj_g)* 
- LLMs are 2 things - parameters & some code to run the model. For example Llama-2-70b (open source) -> 500LOC C code & 140GB parameters file -> compile the C code -> point the C binary at the parameters file to run the model.
- Running the model (inference) is the easy bit. This is the forward pass of the network. The magic is in the parameters (trainng)
- Training is a computationally involved process. Training, of LLMs is basically a large chunk of the internet. For Llama-2-70B
	- ~10TB text 
	- 6,000 GPUs for 12 days (~$2M) (~1e24 flops)
	- Output: ~140GB file (so about 100x lossy compression)
- Llama-2-70B is behind SOTA by at least 10x across the board
- What is the neural network doing
	- Predicting the next word in the sequence given some context of previous words
	- There is a good intuition that prediction === compression. Next word prediction forces the neural network to lear a lot about the world.
- The network "dreams" internet documents when it performs inference. It's mimicking documents that are in the training documents.
	- However, it's very often correct (memorised) from the training set in terms of the information, even though the exact text is not in the training set. This means you're never 100% if it's hallucinating or not!
	- At this point you have "pre-trained a base model" 
- How does it work?
	- Little is known in detail
		- Billions of parameters are dispersed through the network. We know how to iteratively adjust them to make it better at prediction 
		- WE can measure that this works but we don't know how the billions of parameters collaborate to do it
		- They build and maintain some kind of knowledge database but it's not prefect - the "reversal curse" is a good example of this.
		- **Think of LLMs as mostly inscrutable artefacts, develop correspondingly sophisticated evaluations.**
- Training the Assistant (Fine-Tuning)
	- The first stage of training - predict the next word - is called "pre-training" but what we want is an assistant model.
	- The optimisation is the same (next word prediction) but we swap the dataset -- we use lots of people to come up with question and answer pairs.
	- Pre-training is high quantity, low quality. Fine-tuning is low(er) (O(100K) Q&A responses) quantity, high quality.
	- After fine-tuning you have an "assistant model"
		- The model, post this point, understands that it should respond in the style of a helpful assistant
	- Roughly: pre-training == knowledge, fine tuning == alignment
	- Pre-training a new model happens maybe once a year (GPT3 -> 3.5 -> 4). Finetuning can happen weekly where any misbehaviour (bad responses, inaccurate answers etc) can be fixed by adding or fixing Q&A pairs in the next round of fine-tuning
- There is a stage 3 of fine-tuning (optional)
	- Its is often much easier to compare answers instead of writing answers. I.e. for labellers it's much easier to pick the best haiku than it is to generate one. This is what is known as Reinforcement Learning from Human Feedback (RLHF)
- Increasingly labelling is a human-machine collaboration
	- LLMs can reference and follow the labelling instructions just as human can
		- LLMs can create drafts for humans to slice together into a final label
		- LLMs can review and critique labels based on instructions
- LLM Scaling Laws
	- Performance of LLMs is a smooth, well-behaved, predictable function of:
		- N, the number of parameters in the network
		- D,  the amount of text we train n 
	- And the trends do not show signs of topping out
	- **We can expect more intelligence "for free" by scaling**
	- In practice we don't care about this performance (next word prediction) but we find that next word prediction accuracy is correlated with things we do care about
- Modern LLMs (like GPT-4) have access to tools to take advantage of existing computing infrastructure where it's appropriate
	- Python interpreter
	- Dalle
	- Internet search
	- etc
- Multimodality
	- New language models can interact with more than text as I/O - audio, vision 
- Future Research
	- System 1/System 2 thinking
		- System 1: generate the proposals 
		- System 2: keeps track of the tree of possibilities 
		- LLMs only have a system 1
			- Words enter in a sequence and the language model outputs the next work. Every chunk of input is considered for the same amount of time and in the same way
		- We would like to convert **time into accuracy** - like a tree search in Chess, but in language
	- Self Improvement
		- AlphaGo had 2 major stages
			- 1. Learn by imitating expert human players - good but only as good as the best human in the training set
			- 2. Learn by self-improvement (reward = win the game)
		- What is the equivalent of self-improvement for language models
			- Main challenge: Lack of a reward criterion - tasks are open ended, there is no evaluation of "good". 
				- However, in narrow domains, it might be possible to self improve
	- Custom LLMs
		- There are a huge diversity of tasks people want to achieve with LLMs. 
		- The GPT app store is a starting point for this by providing the ability for users to input:
			- Custom instruction prompts
			- Uploading files for [[Retrieval Augmented Generation (RAG)]] 
- LLM OS
	- His opinion is that LLMs should be thought of as "the kernel process of an emerging operating system".
	- This process is coordinating resources for problem solving.
	- ![[Pasted image 20231202175750.png]]
	- The ecosystem of traditional OS is some part propritary () and some part open source (Linux variants)
- Security
	- Jailbreaks
		- LLMs can be fooled to overcome their safety training by augmenting context - e.g. dead grandmother 
		- Base64 encoding of query 
		- Universal Transferrable Suffix - single suffix acting like an adversarial example
		- Prompt Injection - hijacking the prompt in a way that is not obvious to the user but is parsed clearly by the model (e.g. white on white text in a scraped webpage or image)
		- Data poisoning/backdoor attacks
			- "sleeper agent" attacks
			- step 1. Attacker hides trigger phrase
			- 2. when this trigger word is encountered at test time, the model outputs become random, or changes in a specific way
		- plus many more
	- 