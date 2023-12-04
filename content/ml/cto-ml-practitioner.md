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

# TODO/To-Read

## ML Practitioner
- [ ] start here - [Intro to Large Language Models - Andrej Karpathy](https://www.youtube.com/watch?v=zjkBMFhNj_g)
- [ ] [[Greg Brockman]] Blog Posts
	- [ ] https://blog.gregbrockman.com/how-i-became-a-machine-learning-practitioner
	- [ ] https://blog.gregbrockman.com/its-time-to-become-an-ml-engineer
	- *Q: where does he draw the distinction between the 2 paths?*
- [ ] [Full Stack Machine Learning - YT Playlist](https://www.youtube.com/watch?v=WuB9K-P3JBU&list=PLV1JDFUtrXpHtsRmTUeOuzFA3yLie5KZR)
- [ ] Review [Prompt Engineering Guide](https://www.promptingguide.ai/techniques/rag)

## ML Research 
- [ ] Attention is all you need
- [ ] http://neuralnetworksanddeeplearning.com/
- [ ] https://www.deeplearningbook.org/
- [ ] [[Andrej Karpathy]]'s micrograd lecture series
- [ ] [Reinforcement Learning](https://spinningup.openai.com/en/latest/) (from OpenAI)
- [ ] Fun Resources 
	- [ ] [Interactive LLM Inference Visualisation](https://bbycroft.net/llm)
	- [ ] [Rainbow Array Alegbra](https://math.tali.link/rainbow-array-algebra/#introduction) - similar to the above but more generic - how to think graphically about array ops.
	- [ ] [Attention in Transformers](http://bactra.org/notebooks/nn-attention-and-transformers.html)
## Both 
- [ ] [A Hacker's Guide to Language Models - Jeremy Howard](https://www.youtube.com/watch?v=jkrNMKz9pWU&t=1905s)


# Research Notes
[Intro to Large Language Models](https://www.youtube.com/watch?v=zjkBMFhNj_g)
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