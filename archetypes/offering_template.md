---
title: '{{ replace .File.ContentBaseName "-" " " | title }}'
date: '{{ .Date }}'
draft: true
image: "img/butterswords_icon.svg"
description: ""
tagline: ""
price: ""
cta_primary_label: "Get Started"
cta_primary_url: ""
cta_secondary_label: "Contact Us"
cta_secondary_url: "/contact/"
tags: []
categories: []
weight: 100
---

<!--
OFFERING TEMPLATE — a polished pitch page for a product or service.

  hugo new --kind offering_template content/offerings/my-offering.md

`layouts/offerings/single.html` renders the tagline, price badge, and
CTA buttons above and below the content automatically from the front
matter fields above — there's nothing to add in the body for those.

  - cta_primary_url   -> external sales portal / checkout / booking
                         link. Leave blank to hide that button.
  - cta_secondary_url -> already points at the internal /contact/
                         page; change or clear it to hide that button.

Delete this comment block before publishing.
-->

## The Problem

What pain, risk, or gap does the reader have right now? Be concrete —
this is what justifies everything that follows.

## The Offering

What you're proposing as the fix. Describe it plainly, in terms of
outcomes for the reader, not features for their own sake.

## What's Included

- Feature or deliverable one
- Feature or deliverable two
- Feature or deliverable three

## Pricing

<!-- Delete this section if pricing is custom/quote-based. -->

Describe pricing tiers, a flat rate, or "contact for a quote."

## FAQ

<!-- Delete if not needed. -->

**Question one?**
Answer.

**Question two?**
Answer.

## Closing

Reiterate the value and make the next step obvious — repeat whichever
CTA fits (external sales portal or the contact page above).
