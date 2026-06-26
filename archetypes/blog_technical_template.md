---
title: '{{ replace .File.ContentBaseName "-" " " | title }}'
date: '{{ .Date }}'
draft: true
author: "Nathan Butters"
image: "img/butterswords_icon.svg"
description: ""
tech_stack: []
tags: []
categories: []
series: []
weight: 100
---

<!--
TECHNICAL BLOG TEMPLATE — for deep dives, build logs, write-ups of a
system, tool, or technique.

  hugo new --kind blog_technical_template content/blog/DRAFT-my-post-slug.md

Delete this comment block before publishing.
-->

<div class="bg-tlgray-200/40 border-l-4 border-blue-600 px-6 py-4 mb-8">
<strong>BLUF:</strong> What you built/tried, what happened, and the
one thing a busy engineer should remember if they stop reading here.
</div>

## Introduction

What problem or question are you addressing? Why does it matter, and
what's the reader's starting context?

## Background & Context

Prior art, constraints, or assumptions the reader needs before the
details make sense.

## Approach

What you decided to do and why — the reasoning, not just the steps.

## Implementation Details

The how. Code, configs, diagrams, commands — whatever shows the work.

```text
// example snippet placeholder
```

## Results & Analysis

What happened when you did it? Include data, screenshots, benchmarks,
or honest "it didn't work because..." findings.

## Conclusion

Restate the BLUF with the benefit of everything above. What would you
do differently next time, and what should the reader try or avoid?

## References

<!-- Delete if there's nothing to cite. -->

- [Title](https://example.com)
