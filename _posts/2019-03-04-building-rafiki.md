---
layout: post
title: Building Rafiki - A Chatbot
category: build
research: false
topstory: true
image: assets/images/posts/rafiki/rafiki_doc.jpeg
featured: false
travel_featured: false
description: Conversational AI is how we scale personalization.
location: Toronto, Ontario
---

I launched [Rafiki as a chatbot](/build/2019/03/03/rafiki-a-lifestyle-concierge.html). I was focused on solving for accessibility and I think browsing the web, logging in, and submitting tasks is cumbersome. Chat feels better, easier.

Building this was really fun. I loved chatting with Rafiki (who says you can't be friends with a bot?). As a user, the chat experience was magical. It was all in my natural language, in an app I understand deeply (messaging). I think we've just scratched the surface with conversational AI. To build this, I used DialogFlow, Twillio, and NodeJS.

### The Channels:

I started building on Facebook Messenger, but found that it wasn't 'native' enough. My clients, all over 30 years old and in Canada, weren't engaged there. They were engaged on SMS, Whatsapp, and email. I decided to move to SMS, using Twilio's API to get started.

I think of messaging channels in a hierarchical manner, based on form and function of the message. Some platforms were better for tasks (e.g. SMS), and others were better for information (e.g. email, web links).

![MessagingHierarchy]({{site.url}}/assets/images/posts/rafiki/rafiki_hierarchy.png)

### The experience on SMS

I found most chatbots fall short in two areas:

- Conversing with customers when the task goes off-script.
- Working with [Occam's razor](https://fs.blog/2017/05/mental-model-occams-razor/) -- appropriately simplifying the message.

The way I solved for a conversation going 'off-script' was for easy escalation to a live agent. That way, as a service, we were always available and accessible for the customer. They were never left hanging (see: white-glove service). We educated users actively, and destigmitized escalating to a live-agent if needed.

Early on, about 30% of tasks were escalated. About half of those were because the bot didn't understand the user's message. This helped me refine the conversation. The other half of escalations were due to 'unsupported' tasks - those that the service couldn't execute on just yet.

### Content Architecture

I solved for creating clearly articulated messages in two ways: message-design, and referencing. I designed text messages for scanning and quick reference. Here's an example:

![MessageExample]({{site.url}}/assets/images/posts/rafiki/rafiki_doc.jpeg)

Then I created reference links for content that didn't fit well inside a text. For example, we planned date nights for a few of our users. All of the links were obviously mobile-first. Clearly laying out information on mobile is what I've done for over a decade. Here's an example of what we did for a couple in Etobicoke, Ontario:

![DateExample]({{site.url}}/assets/images/posts/rafiki/date_plan.jpg)

### Engineering A Conversation

Overall, I spent a tonne of time on product, and learned a lot about how conversational AI works in the wild. Here are some of the Engineering and product highlights:

- **Conversational AI** - Developing with conversational AI, using DialogFlow. It was really fun to see this come alive. DialogFlow has tonnes of examples to get started. I found managing entity detection difficult as the number of supported tasks increased. I often had to revisit re-organizing entities.
- **SMS and Facebook as channels** - Developing with Twilio as an interface for SMS is incredibly easy (and powerful from a product perspective). I found SMS to have the highest read and reply rates. It was easier to ignore Facebook messages for users.
- **AWS** - Honestly, at first, this was incredibly difficult for me to figure out. I understood the web stack, but couldn't find a really simple explanation of each component and how to get up and running really quickly. There were a couple of blogs I used (linked below). I'm much better now, and can get running within a couple of hours, but it took over a week the first time I launched on AWS. I think heroku is worth using if you're just getting started and testing. It feels easier to manage for starter projects.
