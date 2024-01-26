---
title: "Stubs: Guardrails to Flow"
tags:
  - sapling
  - programming
  - productivity
draft: false
---
The best selling author Ryan Holiday is a prolific writer. With 17 books and a newsletter, *The Daily Stoic*, published to 200,000 subscribers daily since 2016; he clearly understands how to relentlessly produce compelling work. In his view, writing is all about momentum, a practice in which you never want to get bogged down by small details[^1]. His trick is very simple - insert an "X" any time you're unsure of a detail. This allows you to keep all your focus on the core idea you're trying to convey. The minor stuff - an exact date or the weather on a particular day - can be filled in later.

In programming we call these "X"s [stubs](https://en.wikipedia.org/wiki/Method_stub). Stubs stand in for functionality we haven't developed yet. They temporarily bear the load, letting you progress past the current point of development while remaining focused on the main goal of your program.

```js
temp = getTemperature()
if (temp < 12) {
	print('wear a coat')
}
// ... 

function getTemperature() {
	// TODO: actually fetch this value
	return 11
}
```
*`getTemperature` is a stub. We need to come along later and actually implement that part. For now we can say it's going to be some number and move on.*

Programming, much like writing or any cognitively demanding task, is done best while threading the needle between boredom and anxiety. Keeping the present task just hard enough to demand focus while being easy enough to illicit satisfaction[^2]. The parts that are too uncertain, difficult or messy should be stubbed out for the future when it's clear how they'll fit in the whole.

Becoming a more efficient and skilled programmer means getting good at identifying where and how to stub, but once you're practiced you can use it well beyond code.

## Stubs come in 2 flavours

There is a fundamental difference between the writing and code example above. In the former we're sure of the "how", but we're unsure of the "what". In the latter we're sure of the "what", but we're unsure of the "how".

1. **Boredom Reducing** - sure of how, unsure of what - "I know Ryan Holiday has written many books in an impressively short period, but I don't what the precise number is"
2. **Anxiety Reducing** - sure of what, unsure of how - "I know what this piece of code should do, but I'm not sure how to do it yet"

In the course of effortful work you'll flip between both. It's also not the case that only type 1 is useful for writing and only type 2 is useful for programming. Web developers use [Lorem Ipsum](https://www.lipsum.com/) to simulate real text while they focus on coding the layout - reducing the boredom of typing or awaiting real copy. Writers use bullet points to feel out the contours of an idea before committing to prose - reducing the anxiety of committing to exact words. Christopher Nolan famously mapped out the plot line for *Inception* on a sheet of paper while writing the screenplay, JK Rowling mapped the story arc of each Harry Potter character in a spreadsheet. These are examples of stubs as well as [[unstuck-programming#Model the problem in a different space|modelling the problem in a new space]], which is helpful to get unstuck (where stuck is the absolute end state of anxiety).

![[../assets/inception_map.png]]

## Stubs all the way up

So far we've focused on the individual task level, with stubs as guardrails protecting us from slipping out of the flow state and into boredom or anxiety. Like individuals, teams thrive when they have positive forward momentum. For that reason stubbing works as a framework for maintaining velocity in larger projects also.

Zygna (the studio behind Farmville & Words with Friends) uses dummy buttons with promotions of new features or games. If > 50% of the target audience clicks, they begin to build the real thing[^3]. They're stubbing everything that doesn't approximate demand because that's the only data point they need to push forward with confidence.

Likewise, an MVP is a stub for "real product" where a 3rd party solution, or manual genie-behind-the-curtain effort is stubbing the complexity of building the finished article. Fiverr is a platform to buy stubs for things you can't or won't do, allowing you to leverage capital for momentum.

 All of this may sound like repackaged lean startup advice and it kind of is. However, this framing highlights an often misunderstood point about being lean. The purpose of being lean is to be fast and to be focused on the things that actually matter. It's not to be lean for the sake of it, to be lean in all things, or to sacrifice the quality of things that really matter. Stubbing effectively means understanding what is demanding of your full focus and what can be delegated or outsourced. It also means understanding the shape of the hole you're trying to fill with your stub (i.e. what your lean approach should actually be testing). Finally, stubbing recognises that these things will need to be replaced at the appropriate time when focus can shift. It's not an excuse for low quality, it's a methodology for momentum. 
 
 If your data infrastructure isn't your differentiation, using Google Sheets might be ok[^4]. Stub it out and get back to the main thing, delighting your users. If you're selling tool to enterprise maybe your branding isn't *that* critical right now. Stub out a logo and colour palette with Fiverr. Push forward with energy on the things that matter and don't sacrifice the quality of those things. When you've found success with everything else you can come back and replace your stubs, by which point you'll hopefully be stubbing something completely new.


[^1]: From the excellent video ["2 years of Writing a Book in 30 Minutes"](https://youtu.be/dU7efgGEOgk?t=620)
[^2]: This is known as the ["flow channel"](https://www.researchgate.net/figure/Csikszentmihalyis-flow-channel-shows-the-relation-between-challenges-and-player-skills_fig1_322207098)
[^3]: Zynga CEO Mark Pincus on the [Masters of Scale Podcast](https://www.youtube.com/watch?v=ZrqmwHRGm60). Although not mentioned, these buttons are occasionally called "data buttons" or "ghost buttons".
[^4]: Levels.fyi did just this. Scaling to millions of users using Google Sheets as a backend - [Levels.fyi blog](https://www.levels.fyi/blog/scaling-to-millions-with-google-sheets.html)