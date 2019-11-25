---
layout: post
title: DEPA - How to build products that deliver continuous customer value.
category: product
research: false
image: assets/images/posts/product/depalogo.png
featured: true
travel_featured: false
description: A process named DEPA helps us increase our throughput and probability of building the 'right' thing. We use this process to deliver layers of innovation and customer value.
location: Toronto, Ontario, Canada
topstory: false
---

During the early years, we wasted Engineering cycles on inconsequential features. We wasted cycles on the whim of the founders (including mine). Opinions ‘trumped’ data in the name of speed. Often, the highest-ranking person in the room won. Pretty dumb.

For a 40 person team, with little in funding, taking on competitors like Google and Sharethrough (\$45m raised, a staff of 150+), we needed to be better. Our sense was good, but not good enough. I’d guess that we wasted as much as a third of our product investments. There was a way to do it better.

So, I built an internal process and named it DEPA. The process helped us move fast, but not haphazardly. Most importantly, the process helped us increase our chances of maximizing customer and business value. It reduced the risk of wasted cycles, which was important in a competitive market. We couldn't throw money at the problem, so we had to out-execute. And we did.

In this post, I describe what DEPA is. At a high level, it feels simple. That's a sign of something that works. I’d love to hear why DEPA might, or might not be relevant for you (find me on twitter, @pratik_rathod).

A bit of context: My experience with DEPA is in operating in a B2B organization, building a direct-sold monetization platform for the top media companies globally (Oath, Conde Nast, News Corp, and many more). Like most enterprise solutions, we had many personas using the platform. Our platform not only serviced external customers but also internal ones. That is, we built features for external stakeholders and internal service providers.

# DEPA

DEPA stands for:
Discovery
Exploration
Productization
Adoption

Let's go 'depar' (terrible, but I had to do it).

## D: Discovery

During this phase, we _intake_ ideas, problems, and opportunities. We measure _impact_, using data and evidence. We _prioritize_ based on the impact score and alignment with our product vision. We also have an active conversation with our stakeholders (i.e. does the impact score pass the 'gut' test and align with our vision).

Our intake process pulls in data in 5 ways:

1. **Customer Interaction**: Either through direct, or indirect means, we learn about our customers. We use pattern recognition while reading Slack and Salesforce channels. This helps us have a pulse on what customers are saying.
2. **Customer Support**: These channels help us better understand what short-term pain-points are.
3. **Hack Days**: These events are fantastic at answering the question of "what's possible". I love engineering-led innovation.
4. **Internal Teams**: A product-request inbox provides an avenue for our internal teams to raise problems and solutions.
5. **Industry Publications**: These tell us what the market is talking about and caring about. This is an invaluable resource.

Once we have an understanding of the problem, we can work it up with a simple spreadsheet and scoring system. The analysis includes:

- Context classification (between small, medium, or larger)
- Current customers impacted (number, or by name)
- Possible customers impacted (number, or by name)
- High-value-partners impacted (of the top customers, who is affected?)
- Frequency of problem (how often does this problem or opportunity surface)
- Degree of pain when the problem occurs (high, medium, or low)
- Revenue impact or opportunity (try to estimate the revenue impact, in dollars)
- Alignment with strategic goals this quarter.

We weigh each of these factors and come up with a score. This is what we called 'impact'.

Prioritization has three inputs:

1. **Strategic Goals**: Where do we want to move the needle?
2. **Impact Score**: See above.
3. **Gut Test**: An active conversation with your cross-functional team helping answer: What is the data not seeing?

The active conversation, in particular, helps us include intuition. Intuition is another important data point but it can be dangerous. Be aware of each stakeholder's goals and perspectives.

## E: Exploration

As a product owner, we must be rooted in the customer problem. Then, during the exploration phase, we work up possible solutions (including partnerships).

In this step, we're not finished until we have explored as many solutions as possible. Optionality is our friend.

I built the [Product Canvas](/product/2014/08/17/product-canvas.html) to help us follow something succinct, but all-encompassing. The tool helps us build a solution that aligns with the customer. Ultimately, like the Lean Canvas, it's a glorified checklist, but a checklist nonetheless.

![Product Canvas Description]({{site.url}}/assets/images/product_canvas.002.jpg)

In the exploration phase, we try to build towards the best possible solution (even if we aren't the ones to come up with it). We connect with customers and work with internal individuals to ideate, brainstorm, and breakdown. We walk through low-fidelity mock-ups and explore partnerships.

We're not done until we're proud, as a product owner, of the simplicity, ease, and value of the solution. At this point, we create higher fidelity screens to help bring it to life.

In the exploration phase, we explore solutions to a problem, landing on a strategy and approach that will be best. We create buy-in from internal and external stakeholders. Then, we ready the plan for Productization.

## P: Productization

The product canvas is our first input for the Engineering team. A walkthrough of the canvas does two things:

1. It helps Engineering understand your thought process (and provides an opportunity to challenge it and trust it).
2. It helps Engineering create customer empathy as they dig in on a new solution to build.

Before we enter the Engineering process, there is a 3-meeting transition. This might seem like overkill, but the data proves otherwise. When we didn't follow a structured process, our risk of building poorly or having a delayed project increased substantially. From a cost-benefit perspective, spending an additional 30-minutes up-front is a no-brainer.

1. **Product Overview**: Product-led walk-through of the product canvas and customer journey.
2. **Engineering Architecture**: Engineering-led walk-through of the architecture and design decisions.
3. **Engineering Breakdown**: The lead developer on the project breaks down the plan. He/she produces bite-size engineering tickets with information for implementation and testing. Your effort and time estimate will come out of this meeting.

Each step may produce more work as your colleagues see things you don't. Note, both Engineering and QA should be part of each of these meetings.

A word on Engineering processes:
I've worked with several processes in the past, but Kanban seems the most effective given how bad our estimates can be. It removes the need for up-front estimation and is completely data-driven, which I love. Like all processes, discipline provides you with the right structures. The best book I've read on the subject is by David J. Anderson and called [Kanban: Successful Evolutionary Change for Your Technology Business](https://www.goodreads.com/book/show/8086552-kanban). That said, read the book, because no single article is going to give you the context to run a process effectively.

Rather than build user stories, we provide customer journeys and screens to Engineering. This helped us ensure that the implementers understood our goals as they deconstructed the product work. We found that when Engineers created tickets, execution and efficiency increased.

During productization, there is an active conversation throughout implementation. It should never be a black box as hundreds of decisions that weren't made up-front, need to be made as we learn more through implementation and QA.

## A: Adoption

Until the adoption phase, all we have done is spend the team's time and the company's money. It's here that you begin to reap the rewards and show success. Early adoption is part of the product owner's responsibility.

The initial set of adopters will come from the same customers that we had spoken to in steps 1 and 2 (discovery and exploration). They already know that we're building something with their organization in mind. They have a vested interest to adopt it. This phase has three outcomes:

1. **Normalization**: Clear any bugs and make sure this MVP delivers value. During normalization, we have one or more Engineers bug-fixing as we drive adoption with customers.
2. **Customer Playbook**: Here we are creating the customer playbook and collateral. We provide help documentation and training guides to our account and delivery teams.
3. **Data**: We aim for a case study that we can arm the go-to-market teams with. In lieu of a case study, adoption data will do (essentially an anonymous case-study). This is under the assumption that the product is ready to scale.

Once, we've driven early adoption, are confident in the tech, and have the data, the product enters lifecycle management. This includes more features, bug fixes, and potentially sunsetting part or the entirety of the feature. You continue to monitor the data and evidence for more insights.

# Lastly

In a B2B setting, innovation is built on layers of product that create customer value. We want to increase our odds of commercial success through product investment. DEPA helps us increase our batting average, so we have a chance to make this happen.

Thanks and looking forward to sharing more.
