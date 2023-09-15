---
title: Getting Unstuck
tags:
  - programming
  - ideas
  - productivity
  - sapling
draft: false
---
Every problem I've ever encountered in programming has been soluble, even if they didn't seem that way initially. As long as they don't fundamentally violate some physical axiom of the universe, they are not only soluble, they're soluble for you. However mindset, while important, is at most half the battle.

This is a collection of techniques I find helpful for getting unstuck when thinking through hard problems, in programming and elsewhere. 

1. **Start with the API**
2. **Write more** - almost indiscriminately write down everything that comes to mind as you think through the problem. Pause. Edit as if you need to present your problem to someone else
	1. Don't take any step for granted - walk through the entire plan, start to finish, in detail. Notice the rough edges of your understanding. Move with speed but mark where you're unsure and **revisit** until clarity.
3. **Language Matters** - try reformulating the terms in which you are internally discussing the problem
	1. As an example - when passing a callback to a React component I often internally voice that I'm "giving the child component the **opportunity** to call function X with the parameters it chooses". 
	3. This one is a little harder to describe - hopefully it's clear *enough* to think of examples in your own work.
	4. This is very often helpful to untangle mental abstractions that are becoming too much to hold in your head comfortably.
4. **Take the problem to a new space** - think through the problem graphically or pictorially
	1. In particular - take the problem into discrete state space. What possible states can there be? What determines the transition between them?
5. **Create a toy example first** - strip away the particulars and find the essence of the hard thing. Solve that, then layer the complexity back on. Very practically, using something like Repl.it or CodeSandbox, to avoid even setting up your own machine.
6. **Remove constraints**
	1. Somewhat like the toy example but rather than removing the redundant detail, remove critical constraints like time or memory complexity. What does the beginner programmer's naive solution look like?
7. **Avoid the midwit solution**. Try the dumb one.
	1. Like the naive solution except in this situation purposely seek out the most obvious solution. Ideally the one a layperson might suggest, if asked on the spot.
8. **Understand and internalise the [[creativity-faucet|Creativity Faucet]]** - sometimes there is a lot of gunk to clear before the water runs clear. Treat everything like a draft, don't get too attached.

