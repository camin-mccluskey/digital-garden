---
title: Getting Unstuck
tags:
  - programming
  - ideas
  - productivity
  - sapling
draft: false
---
Every problem I've ever encountered in programming has been soluble, even if they didn't seem that way initially. As long as the problem doesn't fundamentally violate some physical axiom of the universe, they are not only soluble, they're soluble for you. However mindset, while important, is at most half the battle.

This is a collection of techniques I find helpful for getting unstuck when thinking through hard problems, in programming and elsewhere. 

### Start with the API
What is concrete about the problem and what is an implementation detail? At the simplest level, what are your inputs and outputs? How can you break apart the possible solution steps into concrete steps or phases? [[Writing/Digital-Garden-Content/stubs|Stub]] out implementation details to retain momentum.
### Write more
Almost indiscriminately write down everything that comes to mind as you think through the problem. Pause. Edit as if you need to present your problem to someone else.

Don't take any step for granted - walk through the entire plan, start to finish, in detail. Notice the rough edges of your understanding. Move with speed but mark where you're unsure and **revisit** until clarity.
### Language Matters
Try reformulating the terms in which you are internally discussing the problem

As an example - when passing a callback to a React component I often internally voice that I'm "giving the child component the **opportunity** to call function X with the parameters it chooses". While this technique is a little harder to describe hopefully it's clear *enough* to think of examples in your own work. I find this strategy especially helpful to untangle mental abstractions that are becoming too much to hold in your head comfortably. By giving several complex elements of the problem or solution a new name you can free up bandwidth to consider more of the problem or solution.

### Model the problem in a different space 
Think through the problem graphically or pictorially. In particular take the problem into discrete state space. What possible states can there be? What determines the transition between them?

3Blue1Brown is the master of this. Watch any of his videos to understand how the same problem can be viewed through a multitude of lenses.

### Create toy examples
Strip away the particulars and find the essence of the hard thing. Solve that, then layer the complexity back on. Very practically, using something like Repl.it or CodeSandbox, to avoid even setting up your own machine.

### Remove constraints
Somewhat like the toy example but rather than removing the redundant detail, remove critical constraints like time or memory complexity. What does the beginner programmer's naive solution look like?

### Avoid the midwit solution (try the dumb one instead)
Like the naive solution except in this situation purposely seek out the most obvious solution. Ideally the one a layperson might suggest, if asked on the spot.

### Understand and internalise the [[creativity-faucet|Creativity Faucet]]
Sometimes there is a lot of gunk to clear before the water runs clear. Treat everything like a draft, don't get too attached.

#### Other Resources

- [Oblique Strategy Cards (online)](http://stoney.sb.org/eno/oblique.html)
	- The music (or more generally "creative") world has a nice concept of [Oblique Strategies](https://en.wikipedia.org/wiki/Oblique_Strategies), co-created by Brian Eno and Peter Schmidt. While not a perfect fit for getting unstuck in programming, many are surprisingly helpful 
- Books on Creativity and Systems for Thought
	- [Conceptual Blockbusting](https://www.amazon.co.uk/Conceptual-Blockbusting-Fifth-Guide-Better/dp/1541674049/ref=asc_df_1541674049/?tag=googshopuk-21&linkCode=df0&hvadid=375385640104&hvpos=&hvnetw=g&hvrand=15573525032855380342&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9044962&hvtargid=pla-814280789489&psc=1&mcid=f4d0d05d7f873b439e3305c50deec3fe&th=1&psc=1&tag=&adgrpid=76471991906&hvpone=&hvptwo=&hvadid=375385640104&hvpos=&hvnetw=g&hvrand=15573525032855380342&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9044962&hvtargid=pla-814280789489)
	- [Thinking in Systems](https://www.amazon.co.uk/Thinking-Systems-Primer-Donella-Meadows/dp/1603580557/ref=sr_1_1?crid=1FHPQTTZMZQVI&keywords=thinking+in+systems&qid=1701213142&s=books&sprefix=thinking+in+systems,stripbooks,75&sr=1-1)
	- [The Creative Act](https://www.amazon.co.uk/Creative-Act-Way-Being/dp/1838858636/ref=sr_1_1?crid=2SWV0P0MTFPQG&keywords=the+creative+act&qid=1701213166&s=books&sprefix=the+creative+act,stripbooks,86&sr=1-1)

