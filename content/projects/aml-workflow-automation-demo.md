---
title: 'AML Workflow Automation Demo'
date: '2026-06-30T10:05:03-07:00'
draft: false
image: "img/AML_DEMO_Dashboard.png"
description: "I created a demo to orchestrate AML detection workflows for a job interview."
status: "Completed"
role: "Product Manager"
org: ""
repo_url: ""
demo_url: "https://www.loom.com/embed/849be6d8995d426bae587c88f1841b50"
stack: ["Claude Code", "React JS", "Ollama", "LangGraph"]
tags: ["Demo", "Risk Management", "Fintech", "Automation", "Agents"]
categories: ["Jobs"]
weight: 100
---
## Problem Statement

A company I interviewed with tasked me to build a demo of a workflow automation tool for the AML (Anti-Money Laundring) and fraud space within financial services. They provided a few criteria for the demo and a list of deliverables for me to produce. I took the opportunity to challenge myself to use Claude Code while exploring a domain I am not intimately familiar with. The results were worth sharing.

## Solution Summary

I aimed to incorporate traditional deterministic signals, ML models, and Agents into a seamless fraud and AML detection workflow. The analyst retains control over the workflow (in the form of scenarios) to choose what is automated and how decisions will be made. The system provides opportunities to improve the quality of detection while streamlining their workflow through single run validation and back testing. Layering real-time deterministic signals and ML models, performing pattern recognition, with agents examining broader context and behavioral signals creates flexibility and scale required for any financial institution to triage and resolve issues. This context persists through the Analyst’s journey as they investigate and report their findings, enabling them to collaborate with their peers, regulators, and leads.

The team lead and compliance officers see an overview dashboard so they can monitor the current state of the risk strategy quickly. This progressive disclosure guides the leads to explore the situation and pivot analysts as necessary.

The system traces all activity for auditing purposes and supports the generation of SARs and other obligatory reports to meet regulatory and compliance needs. 

## Timeline

| Category | Deliverable / Phase | Target Date | Notes | 
| :--- | :--- | :--- | :--- |
| **START DATE** | Ideation and Research | June 15, 2026 | Gauging whether I should build a traditional wireframe or use Claude Code to make a functional demo | 
| **Phase 1** | Initial explorations | June 15, 2026 | I worked with Claude Code to see whether it could create what I wanted using just my initial ideation |
| **Phase 2** | Proper requirements development for spec-driven development | June 16, 2026 | I fleshed out my vision, user stories, and requirements with enough clarity to allow Claude to follow them |
| **Phase 3** | Iteration, QA, and clean up | June 18, 2026 | Working through the experience to identify areas where what was built deviated from specs and reconciling the build |
| **Phase 4** | Demo mapping and creation | June 19, 2026 | Creating the demo and sending it off to be reviewed |
| **END DATE** | Debrief on the demo | June 24, 2026 | Answering questions about the demo and the tradeoffs I made |

## Demo & Artifacts

<div style="position: relative; padding-bottom: 53.75%; height: 0;"><iframe src="https://www.loom.com/embed/849be6d8995d426bae587c88f1841b50" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

## Project Core

Creating a product strategy for a regulatory environment I am unfamiliar with presented a few challenges and some exciting learnings. I started by thinking through the broad scope of Anti Money Laundering (AML) in the financial services sector and then started looking up regulatory requirements, monitoring best practices, and data types to try and build a cohesive understanding of the context for analysts. I found that much of what I saw could use the same framing I have been pushing for the past few years in tech for Security and Trust & Safety. 

The demo itself required the use of Claude Code, which is not my historically preferred method, as I could not work with experts (Designers, Engineers, etc.) to build out a collaborative solution. To ensure the demo met my vision I created a specification document, which includes 10 User Stories divided into three categories: Must Achieve, Should Achieve, and Nice to Have. I also used these user stories to develop 18 specific requirements. The last five requirements were classified as stretch because they went beyond what was asked for in the success criteria set out in the take home instructions.  

The stack for the build is a React app using Tailwind CSS for flexibility and convenience. It was designed and built atop LangGraph and Ollama so I could demonstrate how the workflows function using live interactions with a model. I recognize there’s little-to-no grounding in the model, so it is meant to prove out the viability of the tech stack rather than the efficacy of LLMs. Choosing Ollama acts a demonstration for some future state where different regulatory environments require different models and where institutions wish to use on-premise models to minimize security concerns.

While this adds some complexity to the build, it afforded me the opportunity to explore housing as much information as possible in a single experience by prioritizing the base information and allowing analysts and leads to dive deeper as they identify the need. I purposefully chose not to build a “scenario builder wizard” because I firmly believe that AI supports human expertise and should not replace it. I also focused on a single analyst, rather than multi-analyst collaboration, because I felt I was already pushing the limits of what I could learn in a week with this build. Lastly, I chose to limit scenarios to a single agent paradigm, rather than abstracting to the next level of orchestrating multiple agents, because I think building the overall experience should be approached incrementally based on the feedback received from customers rather than assuming that they can, and would want to, nest multiple workflows. 

I focus on live testing and validation because these technologies require both a quantitative and qualitative approach to building trust that you will receive appropriate results from their usage. This data is derived from real world research (“AMLNet”) to try to provide a meaningful demo that aligns to AML analyst’s actual usage.

Below are a few of the more important inputs I came up with to drive the work.

#### Assumptions
* AML can use similar workflows to security and T+S work
* Finance institutions are conservative in their adoption of ML and LLMs due to incentives and regulations
* All work should be traceable and have clear chain of custody
* Most analysts have no formal training in ML, neural networks, or language models 
* The orchestration workflow experience doesn't matter if it does not feed into other parts of the process seamlessly
* Testing on real data is necessary for trusting new scenarios and rules 

#### Pillars
* Speed of resolution
* Clarity through traceability
* Ease of use for analysts, leads, and reviewers

#### Key Capabilities
* Uses deterministic processes where possible to provide real time insight
* Detections and alerts are communicated directly in your flow of work according to their severity
* Progressive disclosure calibrated to user needs and allowing for directional exploration
* Agents provide support for human expertise, they do not replace it
* Enables a choice of models to fit the regulatory needs of each customer
* Includes an iterative testing capability, using historical data, to support new scenarios and alerts

## References

[AML Analyst 101](https://www.sanctions.io/blog/aml-analyst-101-what-they-do-and-how-to-become-one)
[Transaction Monitoring Best Practices](https://www.sanctions.io/blog/transaction-monitoring-aml-compliance-best-practices)
[AMLNet](https://zenodo.org/records/16736515) 
[FATF typology reports ](https://eurasiangroup.org/en/fatf-typology-reports)
[Anti-Money Laundering (AML) | FINRA.org](https://www.finra.org/rules-guidance/key-topics/aml)
[Office of Foreign Assets Control](https://ofac.treasury.gov/)
[History of Anti-Money Laundering Laws | FinCEN.gov](https://www.fincen.gov/resources/history-anti-money-laundering-laws)
[Bank Secrecy Act / Anti-Money Laundering (BSA/AML) | FDIC.gov](https://www.fdic.gov/banker-resource-center/bank-secrecy-act-anti-money-laundering-bsaaml)
[Top AML Scenarios Examples | sanctions.io](https://www.sanctions.io/blog/aml-scenarios-examples)
[Compilation of Award Recipient and Nominated Cases](https://www.fincen.gov/system/files/shared/Compilation-of-Award-Recipient-and-Nominated-Cases-FINAL-508C.pdf)
[What Is AML Transaction Monitoring](https://www.feedzai.com/blog/what-is-aml-transaction-monitoring/)
[AI Agents in Finance](https://litslink.com/blog/ai-agents-for-financial-services)
[SAR Escalation & MLRO Decision Workflow](https://sumsub.com/blog/suspicious-activity-reports/) — stages 6–7 specifically (escalation, filing, closure)
[FFIEC BSA/AML SAR Regulatory Requirements](https://bsaaml.ffiec.gov/manual/AssessingComplianceWithBSARegulatoryRequirements/04) — SARs (Suspicious Activity Reports)
[Key AML KPIs for FinCEN 2028 Compliance](https://www.flagright.com/post/key-aml-kpis-for-rias-fincen-compliance-rule)
[How to Tune Transaction Monitoring Rules](https://www.flagright.com/post/how-to-tune-transaction-monitoring-rules)
[Key Risk Indicators for AML](https://riskpublishing.com/key-risk-indicators-anti-money-laundering-aml/)

