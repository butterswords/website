---
title: '{{ replace .File.ContentBaseName "-" " " | title }}'
date: '{{ .Date }}'
draft: true
author: "Nathan Butters"
image: "img/butterswords_icon.svg"
description: ""
tags: []
categories: []
series: []
weight: 100
---

<!--
GENERAL BLOG TEMPLATE — use for posts that mix technical content with
personal reflection, or whenever the technical/musing split below
doesn't apply cleanly.

  hugo new --kind blog_template content/blog/DRAFT-my-post-slug.md

If a post is clearly one or the other, use the more specific archetype
instead:
  hugo new --kind blog_technical_template content/blog/my-post-slug.md
  hugo new --kind blog_musing_template content/blog/my-post-slug.md

Delete this comment block before publishing.
-->

<div class="bluf">
<strong>BLUF:</strong> One or two sentences giving the reader the
takeaway up front — what happened, what you concluded, or what you
recommend. Assume they may not read past this box.
</div>

## Introduction

Set the scene. Why are you writing this? What prompted it, and what
should the reader expect to get out of it?

## Core Content

<!-- Break this into as many headed sections as the topic needs. -->

### Section One

### Section Two

## Conclusion

Tie it back to the BLUF. What changed, what you'd do differently, or
what the reader should take away or do next.

## References

<!-- Delete if there's nothing to cite. -->

- [Title](https://example.com)
