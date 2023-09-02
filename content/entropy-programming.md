---
title: Entropy, Programming, and Refactoring a Bloody Filter Component
tags:
  - programming
  - react
  - productivity
  - sappling
drafts: true
---
*Whats the point: It's much harder to write simple programs than hard ones. Like sand on a beach, there are many more configurations that look random than those that look ordered. Likewise there are many configurations of a program that, while achieving the stated goal of the program are messy rather than clean. Cleanliness is a virtue - it's easier to reason at the time, avoiding bugs and making it easier to test. It's also easier to reason about later making it easier to maintain, refactor and extend. The point of this piece is to tell a story of a real refactoring, done poorly, painfully and slowly in the hope that I/we can learn something about the nature of good code*

Story time - look at the filter component from Stackfix Expert dashboard. It has evolved from complex to less complex. 

In the space of possible programs that satisfy the specification (map inputs to correct outputs) there are 

Discovering rules and special cases in the rules as you go:

> Another issue is that if we just have a flat list of `subcategoryIds` we have no knowledge of their relationship to a parent category. So I think we need some kind of lookup that can be used to do 2 things:
> 	1. Select/deselect relevant subcategories when a parent category is toggled (trivial to solve - on change of parent, children must match)
> 	2. Select/deselect relevant categories when a certain state of subcategories are toggled (all on/all off/some on)
> 
> (2) Is is harder: one might think the best approach here is to get the `categoryId` from the toggled option then go through the list of all options and determine what to do, where the **logic** would be:
> 	1. any conflict between this option's new value and siblings == parent off
> 	2. no conflict between this option's new value and siblings == parent same as sibling
> 
> **But wait, isn't 1 a special case of 2?**
> Let's image 2 sibling subcategories (1 off and 1 on). We know from rule 2.1 the parent should be OFF because the siblings are in conflict. If we switch the parent ON then rule 1 mandates how we solve the conflict - both must come on.

This sort of state machine thinking often leads to a much more concise rule set. It would be good to formalise how we think about this such that we can write the most terse, testable and reliable code that mandates the expected behaviour. Thinking in terms of states is helpful, indeed it's one of the best ways to get unstuck, although there are [[unstuck-programming|many more]].

**State:**
children: on/off[]

**Oracle:**
children -> parent relationship (maybe this is already stored in the children, maybe not. Not really important It's not state b/c it can't change. It's just background information. This should be cached outside of any state update)

**State Changes (actions):**
- Turn parent on 
- Turn parent off
- Turn child on
- Turn child off
*This is absolutely everything that can happen*

So between the state changes (actions), and the state, we have a complete picture of everything that can happen. 

The goal is to radically simplify the state and the actions -- *this is where I'd include some example of going from the v1 filter to v2 filter to v3 filter*
- v1 was on main branch fri 1st sept < 6pm
- v2 was on branch stac-933/sync-url-params-and-state in the `Filter.tsx` component
- v3 was on branch stac-933/sync-url-params-and-state in the `ProductFilter.tsx` component
- *Best place to find all this will be PR `#94`*

^ View each version as a progression in those 3 things - where did we simplify state, oracle and/or state changes?

### General Rules
1. Have as few states as possible. Derive state if you can
	1. e.g. parent category state is just a function of the child state
2. In service of (1), move information out of state and into the oracle / derived state
3. Reduce the number of actions. Look to compress the action space to encompass special/limit cases. Having simple state will help with this. Maybe special cases are as a result of trying to do too much with state that should be derived





