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

I launched [Rafiki as a chatbot](/products/2019/03/03/rafiki-a-lifestyle-concierge.html). I was focused on solving for accessibility and I think browsing the web, logging in, and submitting tasks is cumbersome. Chat feels better, easier.

I built Rafiki's chat interface using DialogFlow, Twillio, and NodeJS.

I used the chatbot as a conversational intake form. This was really fun. I loved chatting with Rafiki (who says you can't be friends with a bot?). As a user, the chat experience was magical. It was all in my natural language, in an app I understand deeply (messaging). I think we've just scratched the surface with conversational AI.

### The Channels:

I started with Facebook Messenger - but found that it wasn't 'native' enough. My clients, all over 30 years old and in Canada, weren't active there. They were active on SMS, Whatsapp, and email. I decided to move directly to SMS, using Twilio's API.

I think of messaging channels in a hierarchical manner, based on form and function of the message. Some platforms were better for tasks (e.g. SMS), and others were better for information (e.g. email, web links). Here's how I think about communication platforms and how we communicate.

[Find and write down the communication hierarchy here]

### The experience on SMS

I found most chatbots fall short in two areas:

- Understanding of user intent when the conversation goes off-script.
- Working with [Occam's razor](https://fs.blog/2017/05/mental-model-occams-razor/) -- appropriately simplifying the message.

The way I solved for a conversation going 'off-script' was to escalate to a live agent. That way, as a service, we could always resolve be available -- accessible for the customer. They were never left hanging (white-glove service). My scope of 'tasks' were fairly narrow and I educated users on how to escalate to a live-agent if needed.

Early on, about 30% of tasks were escalated. About half were because the bot didn't understand the user's input, which helped me make refine the technology. The other half were due to 'unsupported' tasks - those that the service couldn't execute on just yet.

I solved for creating clearly articulated messages in two ways: message-design, and referencing. I designed text messages for scanning and quick reference. Here's an example:

Then I created reference links for content that didn't fit well inside a text. For example, we planned date nights for a few of our users (don't kill us on the plan!). All of the links were obviously mobile-first. Clearly laying out information on mobile is what I've done for over a decade. Here's an example of what we did for a couple in Etobicoke, Ontario:

Overall, I spent a tonne of time on product, and learned a lot about how conversational AI works in the wild. Here are some of the Engineering and product highlights:

- **Conversation AI** - Developing with conversational AI, using DialogFlow. It was really fun to see this come alive. DialogFlow has tonnes of examples to get started. I found managing entity detection difficult as the number of supported flows increased. I often had to revisit re-organizing the entities.
- **SMS and Facebook as channels** - Developing with Twilio as an interface for SMS is incredibly easy (and powerful from a product perspective). I found SMS to have the highest read and reply rates. It was easier to ignore Facebook messages for users.
- **AWS** - Honestly, at first, this was incredibly difficult for me to figure out. I understood the web stack, but couldn't find a really simple explanation of each component and how to get up and running really quickly. There were a couple of blogs I used (linked below). I'm much better now, and can get running within a couple of hours, but it took over a week the first time I launched on AWS. I think heroku is worth using if you're just getting started and testing. It feels easier to manage for starter projects.

## Shutting it down:

Again, ultimately, I shut it down, but it was fun building a product that focused on conversational AI, and launching with TWilio and AWS.
