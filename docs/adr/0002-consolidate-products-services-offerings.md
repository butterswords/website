# ADR-0002: Consolidate Products, Services, and Offerings into One Content Type

**Status:** Accepted — implemented 2026-06-22
**Date:** 2026-06-22
**Deciders:** Nathan Butters

## Context

Following ADR-0001, the site grew three separate, parallel content
types for "things you sell or provide": `offerings` (built first, as
the general-purpose business pitch page for the LLC), then `products`
and `services` (added later by request, to match `bookshelf`'s
section-based pattern).

A code review while building `products`/`services` found that their
archetypes and layouts ended up structurally identical to `offerings`
— same front matter shape (`tagline`, `price`, `cta_primary_url`,
`cta_secondary_url`), same single/list/summary template logic, same
visual treatment. The only real difference was the section name and
the noun used in a couple of strings ("product" vs. "service" vs.
"offering").

At the time all three sections were empty: zero published entries in
`offerings`, `products`, or `services`, and `products`/`services`
weren't even linked in the site nav (their menu entries were already
commented out). This is the cheapest possible moment to merge them —
no content migration, no broken links, no redirects needed.

## Decision

Delete the `products` and `services` content types entirely.
`offerings` becomes the single content type for anything sold or
provided. An optional `type` front matter field (free text, e.g.
"Product" or "Service") renders as a small badge on the single page
and card, so the distinction is still visible to a reader — it's just
no longer a structural split into separate sections, archetypes, and
templates.

## Options Considered

### Option A: Keep three separate sections

**Pros:** Each type could diverge later if products and services
genuinely need different fields or layouts.
**Cons:** Three archetypes and three sets of templates to keep in
sync for content that is, today, identical in shape. Every future
field added to one (e.g. a "money-back guarantee" line) would need to
be copied into the other two by hand, or they'd silently drift apart.

### Option B: Consolidate into `offerings` with a `type` field (chosen)

**Pros:** One archetype, one set of templates, one place to add new
fields. The `type` field preserves the product/service distinction
for readers without preserving the maintenance cost of three parallel
systems. Zero cost to do now since nothing is published yet.
**Cons:** If products and services ever need genuinely different
fields (e.g. shipping info for a physical product vs. a booking
calendar for a service), `offerings` would need conditional fields
rather than two clean, separate front matters. Not a problem today;
worth revisiting if that need shows up.

## Trade-off Analysis

The deciding factor is timing: this consolidation is nearly free
right now (no content, no nav links, no inbound links to break) and
becomes more expensive the longer products/services sit around
accumulating real entries. Doing it now versus doing it after writing
a dozen product/service pages is a difference of minutes versus a
real migration.

## Consequences

- **Easier:** adding new front matter fields or layout changes to the
  pitch-page pattern — one place to change instead of three.
- **Easier:** writing new offering pages — one archetype to remember
  (`hugo new --kind offering_template content/offerings/...`) instead
  of three with near-identical fields.
- **Harder:** nothing identified yet. If products and services later
  need to diverge in structure, see Option A's con above.
- **To revisit:** if a future offering needs fields that only make
  sense for a physical product (shipping, inventory) or only for a
  service (booking/scheduling) — that's the signal to split again,
  informed by real content instead of speculation.

## Action Items

1. [x] Delete `archetypes/product_template.md` and `archetypes/service_template.md`.
2. [x] Delete `layouts/products/` and `layouts/services/` (single, list, summary for each).
3. [x] Delete `content/products/` and `content/services/` (both were just an empty `_index.md`, no entries).
4. [x] Add an optional `type` field to `archetypes/offering_template.md`, rendered as a badge in `layouts/offerings/single.html` and `summary.html`.
5. [x] Create `content/offerings/_index.md` (didn't exist before — `offerings` had backend support but no section index yet).
6. [x] Update `hugo.toml`: removed the commented-out `products`/`services` menu entries, replaced with a single commented-out `offerings` entry (still disabled until there's real content to show, matching prior convention).
7. [x] Verify end-to-end: full build confirms `/products/` and `/services/` no longer exist, `/offerings/` renders correctly with the new `type` badge, no dangling references anywhere in layouts or content.
