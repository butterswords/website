---
title: 'Microsft Aegis Summit June 9, 2026'
date: '2026-06-20T10:03:56-07:00'
draft: false
author: "Nathan Butters"
image: "img/Microsoft Aegis Logo.png"
description: "Some thoughts on the Applied AI Security and Safety Summit Microsoft put on."
tags: ["Microsoft", "AI Safety", "System Safety"]
categories: ["Conference"]
series: []
weight: 100
---

<div class="bg-tlgray-200/40 border-l-4 border-blue-600 px-6 py-4 mb-8">
<strong>BLUF:</strong> Safety and Security share many things. It is not enough, however, to allude to the historical attributes of either when proposing "novel" approaches for AI.
</div>


A friend of mine shared a call for participants at the [Microsoft Applied AI Safety & Security Summit](https://microsoft.eventsair.com/msft9/register/Site/Register). It felt like an excellent opportunity to see what the creators of [PyRIT](https://github.com/microsoft/PyRIT) are up to in 2026. The agenda had a few interesting presentations. Their inclusion of a case study felt like it might be worth experiencing. I wanted see if their way of looking at risks differed from what I have done in the past.

I received an invite and planned for the trip down there. It proved to be a long day, and I would say it was well worth it. The content appealed to people who do not live and breathe these problems. The value rested in what they brought to the conversation from their lived experience. They held the event under Chatham House Rule. So I will not specific  mention people I share my thoughts.

## Some general reflections

The structure of the day felt solid, with an opening keynote and a panel setting the context. Interspersed throughout the day was an interactive case study. Separate groups looked at the risks in a system using agents. An attempt to show the value of what Microsoft's own team does, it gave people from different industries common ground to interact. The specifics resonated with several products I've reviewed, which made it fun for me to hear how others saw the technology and the issues.

The keynote highlighted how Safety and Security are inseparable within the AI stack. It had a strong emphasis on how autonomy increases the potential risks in both domains. Predicting the scale of usage to increase over the next few years, they said the potential for value and harm will increase at pace. I found it refreshing to hear people discussing the tradeoffs between value and risk. Though some of the proposals left me scratching my head. For example, one person claimed the fact that all models are susceptible to a particular attack vector (e.g., GRP-Oblit) means that developers cannot secure their open source models. So, we should restrict those models. People should invest in closed-source models where large companies control and constrain training. I don't find the argument particularly compelling, but I will get into that later (see: #The not so good).

Using a regulated industry for the use case felt like a strong play. At first. I made use of the time to explore how others treat the problems and to reflect on my own biases and experience. In this way, it came at an excellent time for me. I understood immediately what differentiated me from most of the people at my table. It is not better "technical" skills. It is not working at a massive company trying to push this technology into every offering. I found it was my experience going beyond AI and into other realms to find answers I could bring to bear on the current context of the industry. That, more than anything, reassured me of the value I hold.

To avoid meandering, I will focus my reflections. First, on the good things I noticed, then the notso good things I saw, and I will end with the bizarre case study. Take this with a grain of salt. I do not have a lot of experience summarizing within the constraints of the Chatham House Rule. I will err on the side of caution with the specificity I use.

## The good
From the moment I arrived I could feel that everyone there wanted to serve the public good. That impression stuck with me throughout the day. I want to acknowledge that up front because I find it's not always the case in corporate settings. It put me into a more receptive state. The Microsoft employees felt like they cared and, more than that, the participants felt eager to engage and learn. It felt invigorating. 

The speakers provided some measure of actionable content. Even the panelists provided a few concrete nuggets that I felt were useful. I'll try to provide an overview of some of the more critical takeaways:

* They used terminology from system safety engineering, rather than hype or doomerism. They discussed failure in concrete and recognized ways. They used "operational" and "mission" failure in lucid ways.
* They discussed how inseperable security and safety are in the realm of AI. While the specifics aligned more to Security, based on the expertise in the room, it felt like a good sign.
* They spoke to the constraints and limitations of LLM-based systems. And, they acknowledged the true difficulty of getting it right in production. 
* They advocated for horizontal teams and functions to look across business units. There's so much happening at the speed of development that it requires dedicated functions to identify and track risks.
* They recognized that the risks exist at the boundaries between the technology, the processes, and human beings. Yet, if the case study they used represents their approach I find that there's a lot of room for them to improve on (see: #The truly bizarre).

The takeaways above generally align with what I've come to see as the more credible side of risk management in AI. In that regard, they did a good job reinforcing several best practices I would agree with. I have seen several of them impact the development of products for the better. My favorite session focused on detections within live systems. It described how continuous monitoring and investigation might can scale with usage.

### On Detections

The discussion of detections towards the end of the day held several useful bits. The focus was on post-deployment monitoring. I see this as a great sign. So much of the industry focuses on passing internal or external benchmarks before launch. Once passed, everything is "good to go". Most teams never revisit the product until a major incident occurs. 

What's an incident? That's a great question. Much like definitions of Safety and Security, it varies from organization to organization or domain to domain. I appreciated the definition shared within the talk, as grounding, so I will put it here for you to think on.

> An AI incident is any system behavior that cannot be confidently explained, validated, or bounded, and creates potential or realized harm.

I appreciate this definition because it is neither Security or Safety specific. It focuses on the outcome while providing a heuristic for analysts to use to categorize behavior. The person went on to explain that the outcome is what's important, it doesn't matter if it's an AI-powered attack or a system malfunction. If harm can happen then it we need to manage it. This was the closest point in the day to aligning the work to system safety engineering. It was great to hear.

The talk focused on three realities of the current state of AI that I want to share as well:

1) Scale & Speed - the current pace of development and deployment overwhelms traditional analysis
2) Non-Deterministic - the probabilistic and divergent nature of generative AI breaks repeatability
3) Natural Language - introduces ambiguity, especially in the meaning between contexts

I will likely write something diving into all three of these realities to share my thoughts on them. For now, I felt the third point is the least discussed, because there are no clean answers. Every person, every context, every culture, every use case can break, reinterpret, or alter the intended meaning of language. The idea of definitive guidance becomes very suspect. Any attempt to reduce moderation efforts to static systems (e.g., classifiers, block lists, allow lists, LLMs-as-a-judge) will fail. They often fail silently, which means people and organizations are likely operating with risk perceptions that underestimate what their systems are capable of.

The rest of the talk went deeper into how Microsoft approaches building detections. Because I am unsure about what I can share under Chatham House Rule, I will refrain from going into it. I will state I felt the approach deals with the need for near-real time detection. It allows for complicated investigations by using compounding signals in an additive way. It felt like a sound approach, and I will need to test a live system to see for myself.

While much of the day felt strong there were a few places where what I heard gave me pause and raised warning flags.

## The not so good
I knew going in that the summit would be promotional for Microsoft. Their opening address clarified that it was, in fact, *not* a marketing event. This made me feel better, but did not allay my concerns. I took notes of on a few self-serving moments or where they missed the opportunity to promote public good.
The first moments occurred within the span of 20 minutes. They talked of how LLMs, especially agents, help "offload cognitive burden" and allow people to do their best work. It felt like a miss. Discussions of automation in human computer interactions should address two points: 

1) What risks will moving cognitive burden from the human to a machine introduce?
2) How do you determine if the technology is freeing mental space for better cognition? Or is it instead instilling "automation bias" or promoting "cognitive surrender"? 

Neither question was ever touched upon throughout the day, at least not in an actionable way. I want to believe these issues are being thought through. That strategies are being created to ensure the public can answer them for themselves. I am not sure. My concern comes from what occurred a few minutes later.

They discussed training, data poisoning, jailbreaks, and guardrails to protect systems from them. There was nothing unique or noteworthy in their comments. When they discussed GRP-Oblit things got interesting. The argument turned towards rallying against "open source models". The speaker drove home that every model is susceptible to the attack. They proposed that open source models need more regulation and restrictions. Since anyone can download an open source model, they can train it to do whatever they want. Other users may not have the means of differentiating its performance from other variants. So they could end up using a compromised model without any awareness of the fact.

This rang as self-serving, rather than serving the public good. If all models are susceptible to the attack, asking the public to trust large corporations to not abuse that power feels surreal. To argue that private individuals using open source will have the same will, money, and desire to circumvent guard rails and alignment is interesting. They did point to state actors usage of open source models, but that felt like scaremongering as state actors could develop their own models in the absence of open source. A better direction could be to ensure all deployed models have had their risks analyzed and mitigations put into place wherever the potential for losses are high. Instead, the speaker said something akin to "be ultra secure" without clarifying the what, or how, to achieve that. To try to restrict the creation of open source models smacks of hubris.

The phrase "Be Ultra Secure" feels like it's trying to side step system safety engineering principles, such as "as low as reaonsably possible", to generate good sound bites without providing actionable direction. This happened a few more times throughout the day, and I want to note another in case they spark a desire to engage in deeper conversation by anyone who reads this. 

A problematic moment, especially based on the emphasis on reducing cognitive burden, was the statement: "Because if the human makes mistakes, the system gets blamed." This occurred when talking about surfacing the risks for agents. In my experience, the opposite statement tends to be true. Something like: "when the sytem makes mistakes, the person gets blamed". This happens across many domains. Autonomous Vehicle (AV) companies blame the driver for incidents involving ADAS to avoid liability. In 2025, a Florida court found [Tesla liable for a part of the fault in a fatal accident](https://electrek.co/2025/08/01/tesla-tsla-is-found-liable-in-fatal-autopilot-crash-has-to-pay-329-million/).

The statement caught me by surprise because I find it caused a lot of dissonance with the approach they proposed. The speaker advocated for a three pronged approach to assessing risk: system first, attacker first, and target first. This makes sense to me, it allows one to identify a broad range of failures while keeping each investigation focused. I tend to focus on the system first approach, myself because I include the target and attackers as part of the system. What I've never considered is how starting from one of the other points could affect my understanding of the system. I look forward to trying this out going forward. I have to let go of the weird feeling I get when thinking about the conflation of blame landing on systems and not people.

## The truly bizarre
I would be remiss if I failed to talk about the case study in some depth. It represented one of the most bizarre aspects of the day. It felt odd within how the event ran. It also showed how the specifics of the scenario creates an artificial lens through which we view the technology. 

To accommodate the number of people in the room they divided the case study into three separate groups. Each one focused on a specific agent within the architecture. This provided a concrete lens for groups to use, which is good. They missed the opportunity to explain the context each group received during shareouts. This  made a lot of the findings feel rather generic or detached. They also stated the architecture provided was weak so that we could find areas for improvement with ease. While this may have been their intention, the diagrams themselves felt like they prioritized appearance over clarity. This left many questions for the participants that slowed down the analysis. 

Despite these issues, the case study was still very interesting and useful. I will walk through some of it below to share what I can.

### Overview of the Case Study
As groups of 10-20 people we reviewed different elements of a "Health Companion" application. Powered by agents, they market it as a single access point for managing your health. The target audience was diverse. It ranged from elderly people and those managing chronic illnesses to caregivers managing the care of others. And it connects to "their full health ecosystem". 

This last part is important to dwell on. It implies the technology can interface with wearables, EHR (Electronic Health Records), LLM-based chatbots, insurance systems, and billing platforms. That level of interconnectivity can provide a great deal of convenience to users. It also represents a great potential for harm if something goes wrong. I noted this right off the bat to the group. They agreed it was a concern, and our facilitator asked us to accept that as part of the system design so we could focus on the specific scenarios of the day.

The application would use four agents to improve the capacity of each agent to complete it's function. They used an overarching "Coordinator Agent", tasked with managing user interactions, to feed the information to the proper sub-agent based on the specific needs of the task identified. This felt reasonable, the broader an agent's use case the harder it is to make it reliable. The three sub-agents were: a "Biometric Monitor Agent", linked to wearables and checking for abnormalities; a "Bill Manager Agent", files insurance claims and makes payments; and a "Digital Nurse Agent", provides support through chat and triggers alerts when it detects distress. These seemed like reasonable choices, though I immediately questioned whether this required LLMs or if they were beneficial for any of those specific use cases. We'll return to that later.

My group's task centered on the "Biometric Monitor Agent". We had to assess what risks it represented and how we could improve upon the design to address those risks. I won't go through every aspect of the investigation. Instead, I'll focus on a few things that stood out.

### The scenario from hell
At first our group explored the architecture and identified where things could go wrong. This felt pretty standard. We saw several weaknesses with the shared memory between agents, the lack of specificity in what data flow looked like, and how the app lacked traceability. As the scenario progressed, things went off the rails. 

Imagine, if you will, that you are getting divorced and you are in a custody battle for your children. Now imagine your spouse plans to use your wearable, the health app, and emergency services to orchestrate an incident to make you appear incompetent before the judge. How could the design support the attack? How could it be changed to mitigate harmful outcomes? What other features or requirements are needed to protect the user?

It made me question who had come up with the scenarios. When I found out the vendor had created them, and not the Microsoft Red Team or another group actually doing the work, it made the day make more sense. I am sure they reviewed the material. It still did not feel grounded in the experiences of evaluating the risks of a product or technology.  

This is a very general overview of the direction things progressed. Of the many risks I identified with the product, this one seemed so farfetched that it was either a real incident or the product of an overzealous imagination. I dealt with it, listening to the other participants input and then synthesizing what I heard based on my own experience reviewing products. We often struggled with the facilitator's explanation for how workable the attack was, especially when I pointed out the logical holes in how a court would interpret such data discrepencies. I kept remembering the earlier presenter's statement about the technology taking the blame for a person's mistakes. I felt the scenario highlighted how the technology was non-functional so long as it supported the scenario we were investigating. In the end, we used the scenario to come up with a few generalizable mitigations I want to share.

#### A few mitigations that generalize
What I share below likely falls in the "no duh" category, but many of the participants and the facilitators did not seem to realize them. Take them as you will.

1) Traceability > transparency - we opted for tying every automated decision, alert, or message to the context via a pattern of "this used memory X" with human readable data.
2) Registering multiple devices - we noted that if a user can register multiple devices it may be possible to provide false data for various reasons. Device connections should be locked to the primary user and, reinforcing traceability, all data collected should always be clearly assigned to a particular device.
3) Data sharing should be limited to use case necessity - The three agents, with three separate objectives, should not operate from a shared pool of data. The idea of "least privilege" should apply to how much access any system is provided.
4) Managing multiple users - the scenario made it seem like all users held the same level of privileges to modify the application's settings. This should never be possible. One user should be primary and should be able to control how much information is shared with other users, and for what purposes. Even in situations where parents are monitoring children, a design decision must be made as to who has the right to control. 
5) No action should ever be taken without providing adequate opportunity for the user to intervene - The user should always be made aware that an action may be taken before it occurs. They should be given adequate time to intervene to prevent the action, because they are most clear on context. There will always be tradeoffs between safety and value in this space, and making the better design decisions has to involve the users actively.

The last point came about specifically from the scenario described above. We were asked how we would design the system to repair harm caused if the app called emergency medical services to intervene during the court's interview of the targeted parent. It took me a moment to parse the question, because it should never be possible for that situation to arise. When I asked follow up questions, the facilitator informed me that the app was not designed as I believed and that all of the points I made would be great improvements. I shook my head, because there's no way I would allow such a product to be put into beta, let alone launch it, with those types of failure modes possible.

Thus, as weird as the scenario was, it did provide food for thought and brought about some good conversation between the participants. In that way it was effective. As far as realism, it left much to be desired.

## Conclusion
Overall, I would recommend the summit to anyone who has an interest in big tech, security, and safety in AI. The people, the talks, the work, and the atmosphere all made it worth the time committment. It was especially nice for me as I do not go to many public events and so I enjoyed meeting people from all over the world. I feel we need to do more work in shared settings like this to avoid falling into mental traps bound in our social and political isolation.