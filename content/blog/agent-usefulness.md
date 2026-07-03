---
title: 'Starting to evaluate agent usefulness'
date: '2026-06-24T09:54:49-07:00'
draft: false
author: "Nathan Butters"
image: "img/butterswords_icon.svg"
description: "The starting point for my exploration of the question: how can I use agents?"
tags: ["Agents", "Claude", "Vibe Coding", "Spec-driven Development", "AI in Design"]
categories: ["PSA"]
series: ["How can I use Agents?"]
weight: 100
---

I recently talked with a friend and collaborator about agents and the usefulness of products such as Anthropic's Claude (incl. Cowork and Claude Code). We did not agree on much during the conversation, with me sounding very rigid and curmudgeonly and him taking on an optimistic view I did not expect. I respect this person a great deal, so as he continued to argue for the benefits and usefulness of these systems in his life I felt a desire to better understand where he was coming from. Towards the end of the conversation he gave me a blanket challenge: 

> Use agents for tasks you'd never consider using them for. See how they perform. It may not change your mind and, if it doesn't, at least then you'd be able to say you tested your biases.

Implied in his challenge was something I find very hard to do: set aside my biases to give something a proper chance when I've already made up my mind. Still, I took up the challenge and this article represents the first of a handful of pages I'll be writing on my observations from using 3rd party agents (mostly Claude), Ollama, and LangGraph to bring agents into my day-to-day. I don't know whether the findings will be consistent throughout, so I hope you understand I expect my thinking to change. I just don't know if it will be more optimistic or if I will want to pull the rip cord and eject out of tech all together.

## Overview of what I plan to do

I recognize I will have to use _AI_ when it's incorporated into products I use or that people and companies I interact with leverage it. Does that mean I have to use it for myself? What changes if I choose to use it? What changes if I don't? These questions rattle around my head all the time. They take up more space than I would like. Every time I see a new "report" or "finding" about how _AI_ is helping people, or how it's hurting them, I find myself questioning the motivations of the authors. I seek to think through who benefits from the perspective shared, who is funding the research, and how does it match with larger narratives around the technology. There are many people thinking deeply about these questions, who have more time and resources to devote to them than I do, so I will not focus on addressing them directly. I will focus, instead, on what I see as a risk management profession who has to exist in a world permeated with _AI_.

I feel a lot of friction about using agents because I don't know if they provide enough value to warrant integrating them into my life and workflows. I am working on a project to explore this more directly, using [this great paper on the uses of LLMs for assurance arguments](https://ntrs.nasa.gov/api/citations/20250001849/downloads/NASA-TM-20250001849.pdf), but for our current purposes it's critical just to note they set up 14 questions someone should have a plan to answer **BEFORE** integrating LLMs into their work. I agree with their findings and so tend to gravitate towards spending a lot of time before touching the technology thinking through my goals and expectations. My friend told me I needed to let go and focus more on discovering the usefulness of agents through their usage. He has a point. Trying a different methodology might support me putting my biases to the side.

### Tasks I've identified for exploration

| Potential Use Case | What is the tech | What I hope to do | Effort or skill required | Value to me | Outcome | My current judgment | 
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | 
| **Design a custom logo/wordmark** | Claude Cowork | Take a simple sketch I have of a wordmark and generate a logo and wordmark from it | Low | Medium | It eventually created a usable placeholder logo and wordmark | Design does not appear to be a strength of these systems, especially when making small modifications based on abstract concepts like balance | 
| **Resume rewrites for specific jobs** | Claude Cowork | Assess my resume's fit for a role and then use it, and my LinkedIn profile, to generate a role-specific resume | Low | High| It has generated a resume for each role I've used it for | The text generated feels largely made up and not reflective of my experience, no positive responses yet for modified resumes |
| **Draft a business plan** | Claude Cowork | Take a set of goals and a website and turn it into a business plan | Low | High | It provided a structured document with some rough estimates for revenue and expenses | The structure seemed find, the numbers did not match across the document |
| **Create a Mod for a video game** | Claude Cowork | Create a mod for Banner Lord 2 to add a new story and more depth | Medium | High | Unknown| Not Started |
| **Oxalate Estimator** | VLM + Agent | Estimating the amount of oxalates in food based on images, recipes, or labes | Medium | High | Initial POC showed promise but continually broke when given a recipe | Just Started|
| **Irrigation System** | Agent | Using an agent to gather upcoming weather information from the internet and determine if an automated watering system should run. | Medium | Medium | Unknown | Not Started | 
| **Triage bugs in live code** | Claude Cowork | Assisting me by identifying issues with dependencies and configuration. | Low | High | It helped me identify and resolve a bug that came about after an update to a dependency | The system appears to handle this task well |
| **Demo Creation** | Claude Cowork and Claude Code |  | Medium | High | The demo came out great | This tech is useful for mocking a front end, with custom functionality, quickly |
| **Creating an Agent** | Ollama + Copilot |  | Medium | Low | I finished the agent in the time alotted | It could be very useful, but it's also dangerous to use too much | 


Of the use cases above, three of the tasks (Triage bugs in live code, Demo creation, Creating an Agent) fall directly within what I believe agents to be useful for. I will still test them so I do not end up focusing only on peripheral use cases of the systems. The creators of this technology want people to believe it can support or replace human work across many domains. I consider this exploration an expansion of the years of risk management I've been doing in the space at a more personal level.


### Update Log

| Potential Use Case | Last Activity Date | Current Status | Notes | 
| :--- | :--- | :--- | :--- |
| **Design a custom logo/wordmark** | June 20, 2026|✅| This took me the better part of a week's worth of Claude Credits on Free Tier.|
| **Resume rewrites for specific jobs** |July 2, 2026 |✅ | I am unsure whether the changes made are useful. |
| **Draft a business plan** | May 30, 20206 |✅ | The framework was helpful, the financials... not so much. | 
| **Create a Mod for a video game** | |🆕 | | 
| **Oxalate Estimator** | |🔜 | | 
| **Irrigation System** | |🔜 | | 
| **Triage bugs in live code** | July 3, 2026 |✅ | Definitely a place worth exploring more. | 
| **Demo Creation** | June 24, 2026 |✅ | This helped me build quickly once I figured out how best to shape my own experience. | 
| **Creating an Agent** | June 2, 2026| ✅ | It's tough to code in front of people in 30 minutes, especially when they expect you to prompt Claude and then just chat... | 