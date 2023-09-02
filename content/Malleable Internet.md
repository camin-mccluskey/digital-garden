## Intro
Thoughts around how new browsers (e.g. Arc) and LLMs will empower users to get more from their software tools (and the internet writ large). 

Inspired by this [tweet](https://twitter.com/vincentmvdm/status/1658678049691385857?s=20). Where an individual has used Arc to run some JS calling GPT-3.5 to filter out tweets he didn't want to see - mostly BS thought leadership threads. 

It would be great if anyone could bend software to their will in this way. My thoughts are as follows:
	a) It's possible to modify software using natural language or learning examples for simple use-cases like this.
	b) More advanced modification will be possible in the future as LLMs advance.
	c) It still requires some understanding of what is possible on the client-side vs. the server-side and with understanding of how the web and software works at a fairly deep level.
	d) Most people will intuitively know what they "want" from their software in natural language but don't have the ability or the tools to be able to make it happen in code.
	d) The platforms that make the base tools will not willingly open up to further customisation, without a good reason to do so. So many of the more useful customisations will not be possible.

If that understanding is correct, I think it opens up a huge opportunity for tools like Stackfix, in the position we will occupy, to help our users modify and customise their tools to suit their individual needs. This is a related but distinctly different concept to "Stackfix as a Business Operating System" in that we're not saying "we use our market power to allow us to connect disparate tools together" but rather we are using that market power/position, the trust we have with customers and the relationships with vendors in order to modify an **individual tool** to better suit a user's needs.

Why Stackfix:
1. We have deep integrations with vendors and therefore access to backend APIs (for implementation, migration etc...)
2. Customers trust us and our judgement on software 
3. We can see where the sticking points are with current workflows (from implementation and training)

## Motivating example

[WeWork booking extension](https://github.com/camin-mccluskey/wework-booking-extension). That required reverse engineering the WeWork booking GraphQL API over the course of a weekend. Why should it? It took me less than a day to understand this was an annoyance with WeWork's membership platform and I knew immediately how I wanted it to be different. I could articulate exactly why it was frustrating in a single sentence. Even after building a modification layer to improve my UX the tool broke after a couple of days because WeWork changed their API.

If we have built up a relationship with WeWork as an office space vendor and we have access to their booking API to help our customers move e.g. recurring meeting room bookings from Workspace or Hubble then we could do several interesting things:
1. Offer this tool to all of our customers (like default iPhone apps)
2. Offer access to the underlying backend APIs of these tools with a natural language interface on top (like iPhone developer suite of tools - xCode, Swift etc)
3. Offer a library of user submitted customisations on top of their favourite tools (like the App Store)
   
In this way I see Stackfix as firstly a no-code tool for everything with the possibility of being an app store on top of their favourite SaaS tools.

## The Future

It won't be the case that everyone is making bespoke tools for everything, that just isn't efficient. However I could see a world in which the "base" tool is made by a company and there are enormous customisation possibilities empowered by LLMs. Stackfix could own that customisation layer. In some sense it's quite analogous to what the steady state equilibrium of the LLM market looks to be - there will be players who own the base models b/c they have access to data, talent and capital for massive training runs (OpenAI, Google etc) and a diverse set of players who customise and fine-tune the base models for specific applications in a given domain.

The key difference is that the "fine-tuning" story for LLMs is much easier to articulate. For software tools in general, up until now it has been incredibly difficult to impossible to modify the software without software development experience and access to the underlying APIs.

