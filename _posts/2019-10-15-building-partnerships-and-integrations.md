---
layout: post
title: The Partnership Scorecard - A Roadmap For Product Integrations
category: product
research: false
topstory: true
image: assets/images/posts/product/integration_roadmap.png
featured: true
travel_featured: false
description: Partnerships have long been central to our humanity. I advocate for a partnership and integration model as a central tenet to long-term product strategy.
location: Toronto, Ontario
---

These days, it's rare to find products that only leverage first-party data and services. The digital products that I've used and those that I continue to build leverage ecosystem partners to solve acute customer needs. I think leveraging ecosystem partners to provide integrated experiences leads to cleaner user experiences, privacy through complexity, and a market in which all participants grow.

At my last company (Polar), partnerships and integrations were a core concept to a strategy I helped develop. We integrated with ad servers, demand partners, and data platforms to help deliver enterprise grade software for content publishng customers. Over the last 5 years, I have led over a dozen ecosystem integrations. During this time, we made two major observations: a) There were many organizations solving adjacent problems, and b) There was a limit on time and people.

Partnerships are not new in technology - they're just tough. Like most relationships, they're difficult to navigate and track. It's why I put together the **Partnership Scorecard**. Through the integrations I've set up, I've used the scorecard to help me better understand the strength of my partnerships. If you believe that stronger partnerships lead to incredible user growth and cleaner user experiences, then this might be valuable to you also.

The focus of this model is on software integrations specifically. The following is meant to compliment the [partnership canvas](https://valuechaingeneration.com/2014/10/17/the-partnership-canvas/), which does an excellent job and layering in high-level planning and goal setting. The framework below dives deeper, specifically in relation to 'Transfer Activities'.

# Integrations

First, let’s be clear on what I mean by integration: Creating customer value by transferring information (the value unit), often programmatically, with another company that is solving an adjacent problem.

There are 5 key categories to consider. In sequential order of execution:

1. **Information Transfer**  
   The value (information usually) that is being transferred.
2. **Business Relationship**  
   The depth of the business relationship ranging from API integration to economic exchange.
3. **Support Model**  
   Now that you're integrated, you'll have a broader scope of support. How do you plan to navigate this?
4. **Data Relationship**  
   What secondary data is going to be processed and made available to each other, if at all?
5. **Adoption Priority**  
   How much of a priority is driving adoption for both parties? Which marketing strategy is employed?

It’s important to note, that integrations that begin with marketing and end with integration, are often doomed to fail in a technology-driven business. I’ve seen it a few times. It starts with a press release or blog post and often stops there.

So with that, I bring to you, an integration roadmap:

![Integration Roadmap]({{site.url}}/assets/images/posts/product/integration_roadmap.png)

If each step across a category is worth a point, then you'd be able to score your integrations and get a quantitative view of the strength in the partnership.

### 1. Value transfer

Let's use an easy example of paying a friend back.

- **Manual**  
  This state is important. It shows, that even though you may not programmatically integrate, that you are indeed already integrated via a manual step that your user has to perform. (e.g. a friend giving you cash the next time they see you).
- **Assisted**  
  This step helps your users transfer data, without doing it in a completely automated fashion. As an example, this can range from producing a CSV file that they can upload into another platform, all the way to an API integration that requires user authentication and approval. There is still a manual step, but it is supported by technology. (e.g. e-transfer of money)
- **Automatic**  
  Here, the integration is truly ubiquitous, and the transfer of value is done without manual intervention (e.g. smart contracts).

### 2. Business Relationship

- **From Afar**  
  Usually an API-only integration, in this situation, you don't have any direct business or support contacts. You are interacting with a support channel at best.
- **Handshake**  
  You've met and connected with partnership stakeholders. You have a direct line to get technical and business support. You may or may not have an agreement of intent.
- **Transaction**  
  You're connected, and are paying for a service that isn't usually widely available or adopted. You continue to have direct lines of business support.

### 3. Support Level

- **Test Accounts**  
  You have a testing environment with a test account that is made available to product and QA. You've used this to understand customer interaction.
- **Information**  
  You've put up support articles that are accessible by both internal teams and external users.
- **Real-Time**  
  You've inserted alerts and tips in real-time to help your customers and internal teams stay on top of integrations and how they're managed. This often requires active logging within Engineering.

### 4. Data Relationship

- **None**  
  Interaction data is not transferred and is independently tracked.
- **Individually reported**  
  Interaction data is reported by a single party, into both the primary product, as well as the partner's product.
- **Server to server**  
  There is a server API that allows one product to pull information from another. This is often where cross-product value can be created. It's also the hardest to do right.

### 5. Adoption Priority

- **Word Of Mouth**  
  There is no external marketing other than your team sending customers to a partner as they come along.
- **Co-marketing**  
  There is marketing collateral that is co-created and shows a shared commitment to each other.
- **In-product**  
  There is a one or two-sided product integration that includes the ability to activate the partner's product.

How do you feel about this structure? How would you rate your current partnerships? Are these opportunities to deepen the commitment and entanglement to serve your customers holistically?

## Examples

Let's look at a couple examples.

### VHS vs. Betamax

First, we look at VHS, an inferior technology that gained wide adoption and ultimately dominated Betamax as a universal standard. How did they do this? Through a licensing strategy, they partnered with VCR manufacturers globally. Overnight, both VHS and its manufacturers delivered video into everyone's home. On the other hand, Sony's Betamax which operated within a closed system, failed to gain any significant traction.

![Integration Roadmap]({{site.url}}/assets/images/posts/product/integration_example_vhs.png)

### Polar and MOAT

At Polar, we built technology that allowed the company to ad serve high value content. MOAT had great founders and a solid technical team. We decided to partner very early. The relationship, both technically and from a business perspective proved to be fruitful. Our customers gained viewability metrics on all of their Polar driven ad units, allowing both of our companies and our shared customers to deliver on advertiser value.

![Integration Roadmap]({{site.url}}/assets/images/posts/product/integration_example_polar.png)

This roadmap can be used to better chart your partnership and integration strategy. I hope it helps.

## Challenges

While I wish each partnership was easy, it turns out that there are challenges at each step. The chart below mentions a few of them, and while I won't go into too much detail, it's important to create contingency plans against each negative outcome as you move along the model.

![Integration Roadmap]({{site.url}}/assets/images/posts/product/integration_challenges.png)

### Internal Challenges

There are often organizational hurdles that you must be cognizant of as it relates to seeing an integration succeed. These often come in the form of (borrowing from Blue Ocean Strategy):

- **A Cognitive Hurdle**  
  Your organization is used to doing things their way. They are rooted in building new tech.
- **Motivational Hurdle**  
  A partnership can be difficult for staff, especially as you try to finagle the integration, support, and adoption for a product and team that you don't actively participate with.
- **Resource Hurdle**  
  It is a myth to say that integrations and partnerships are technically easy. You have to actively calculate the cost and benefit with Engineering.

## FAQs

**Q: Why integrate, when we can build it ourselves?**  
I've found that if you can match with the right partner, that your time to market decreases by 80%. You also get to evaluate the use case with first-party data without having to invest in building out your solution.

**Q: Once you integrate, can you still build your proprietary product that solves a similar need?**  
I don't see why not. We did this from time to time as we felt that the existing solution didn't meet the customer's needs or ours.

**Q: Each of our customers uses X.Tool differently. How do I navigate this?**  
We let the customer decide. We kept the integration simple and allowed the customer to configure it once. What we realized is that even though every customer may use a single solution differently, the underlying data models can align. This was an easy customer success step and made the lives of our customers so easy. A one-time configuration is worth the customer's time because it'll save hours per week.

**Q: How do I find the right partner?**  
Pay attention to the market. I'll borrow lessons from Blue Ocean Strategy again:

- Restructure market boundaries: Understand how customers use products within and outside your vertical.
- Big Picture: Keep a birds-eye view to understand the broader market and how products integrate.
- Partnership Canvas: Have a look at the [partnership canvas](https://valuechaingeneration.com/2014/10/17/the-partnership-canvas/), which does a good job in understanding the goals of the partnership.
- Walk The Customer Journey: Develop your journey map and personas. You'll quickly realize what types of partnerships will create impact. Then validate the assumption with data. When you're ready to activate it, then be sure to solve 100% of the problem. Partial solutions create havoc and are rarely adopted.

All in all, integrations are an incredibly important part of the process. It creates an immense amount of business and product value, decreases time to market, and often creates competitive moats - all values of a good product.
