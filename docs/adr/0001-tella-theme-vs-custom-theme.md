# ADR-0001: Continue Customizing the Tella Theme vs. Build a Custom Theme

**Status:** Accepted — implemented 2026-06-21
**Date:** 2026-06-21
**Deciders:** Nathan Butters

## Context

butterswords.com is a Hugo site intended to grow from a personal site into
the public face of an LLC for system safety development. The site currently
uses the [Tella](https://github.com/opera7133/tella) theme (MIT licensed,
single maintainer "wamo"), pulled in as a git submodule at `themes/tella`.

Two new content types are needed that Tella doesn't ship a layout for:
**offerings** (productized services/pitch pages) and **projects** (past/
current work write-ups). Archetypes for these (plus a three-way split blog
archetype) were just added under `archetypes/`. Building the matching
`layouts/offerings/` and `layouts/projects/` templates is the next step,
which raises the question of whether to keep extending Tella or replace it
with a theme built from scratch.

A code review surfaced two pre-existing issues that bear on this decision:

1. **`layouts/` is a full, uncommitted shadow-copy of the theme.** Every
   file under the site-level `layouts/` directory (27 files) is byte-for-byte
   identical to its counterpart in `themes/tella/layouts/`. `git status`
   shows the entire `layouts/` directory as untracked. This isn't
   customization — it's a frozen duplicate that currently does nothing
   except risk silently diverging from the theme and masking the fact that
   no real overrides exist yet.
2. **A dead `PaperMod` theme submodule remains in the repo.** `hugo.toml`
   sets `theme = "tella"`, but `.gitmodules` still registers
   `hugo-PaperMod` (the theme used in the very first commit, before the
   switch to Tella) at a now-mismatched path (`butterswords/themes/PaperMod`
   vs. the actual `themes/PaperMod`). It contributes no functionality and
   adds noise to every `git status`/diff.

Neither issue is caused by Tella itself, but both affect the cost of
continuing with it: there's no real sunk customization to protect, which
makes switching cheaper than it might look — but it also means "customizing
Tella" hasn't actually started yet.

**Constraint:** the immediate goal is to ship a credible, professional
presence (blog, project case studies, service offerings) quickly, in
service of establishing the LLC. Time spent on theme engineering is time
not spent on content and positioning, which is what actually generates
inbound credibility or business right now.

## Decision

Continue building on Tella. Treat the two missing content types as the
actual scope of "custom" work, write only those templates, and clean up the
two pre-existing issues above before adding anything new.

## Options Considered

### Option A: Customize/extend Tella

| Dimension | Assessment |
|-----------|------------|
| Complexity | Low — theme is ~1,014 lines of layout HTML and 226 lines of hand-written CSS total; the rest is Tailwind utility classes |
| Cost | Low — SEO meta tags, social share, comments (giscus/disqus), pagination, and taxonomies already work |
| Scalability | Adequate for a personal/LLC site; Hugo's layout override model lets new sections (`offerings`, `projects`) be added without touching the rest |
| Team familiarity | High after a single read-through; small enough to fully internalize in under an hour |
| Maintenance risk | Single-maintainer upstream theme — low community support, but small enough that internalizing it is cheap; build pipeline (`css.TailwindCSS`, `hugo_stats.json` class scanning) needs a recent Hugo, already satisfied by CI pinning `hugo-version: 'latest'` |

**Pros:**
- Inherits already-working boilerplate (SEO, sharing, comments, pagination, taxonomies) for free.
- Only the genuinely missing pieces (`offerings`, `projects` layouts) need to be written — the same work either option requires.
- Site-level `layouts/` overrides mean changes are scoped to exactly what differs from the theme, not a parallel codebase.
- No license/IP friction (MIT).

**Cons:**
- Small, single-maintainer theme — no large community, fewer existing examples to lean on if something unusual comes up.
- Inherits Tella's opinions about markup/structure; deep visual departures later would mean fighting the theme rather than extending it.
- Doesn't on its own fix the shadow-copy or dead-submodule issues — those need explicit cleanup regardless.

### Option B: Build a custom theme from scratch

| Dimension | Assessment |
|-----------|------------|
| Complexity | High — every layout, partial, and content type rebuilt from zero |
| Cost | High — weeks of work reproducing functionality that already exists |
| Scalability | No inherent advantage over Option A for a site this size |
| Team familiarity | Total control, but no boilerplate to lean on |
| Maintenance risk | Single point of failure (no upstream at all) — every future bug is fully owned |

**Pros:**
- Full control over markup and design system; no upstream surprises.
- A from-scratch theme could itself function as a portfolio artifact demonstrating engineering taste — relevant for a systems-safety consultancy.
- Clean slate — no shadow-copy confusion possible by construction.

**Cons:**
- Re-derives SEO tags, social sharing, comments, pagination, and taxonomy templates that Tella already provides correctly today.
- Classic solo-builder trap: theme-engineering perfectionism substitutes for shipping the content (blog posts, case studies, offering pages) that actually builds credibility.
- Still requires standing up the same Tailwind v4 + Hugo Pipes build pipeline Tella already has working — that complexity doesn't disappear, it just moves.
- Delays the LLC-facing launch with no clear return for a personal/small-business site.

## Trade-off Analysis

The two options converge on the same near-term task: writing layouts for
`offerings` and `projects`. The real fork is whether to also discard
everything Tella already does correctly (SEO, sharing, comments,
pagination, taxonomies) and rebuild it. Given the stated constraint — ship
quickly, conserve effort for content over plumbing — there's no return on
rebuilding working infrastructure. The theme's small size (~1,000 LOC)
means the usual risk of depending on a third-party theme (opaque code,
heavy customization fights) is minimal; reading and modifying Tella in full
is a near-term task, not an open-ended one.

The shadow-copied `layouts/` directory and the dead `PaperMod` submodule are
independent of this decision and should be resolved either way — they are
currently a trap (silent drift from the theme, confusing diffs) rather than
a cost specific to Option A.

## Consequences

- **Easier:** shipping `offerings` and `projects` pages soon, since most of the surrounding site (nav, SEO, footer, taxonomies) is already solved.
- **Easier:** future content-type additions, by following the same "override only what differs" pattern established here.
- **Harder:** any future request for a visual identity that fundamentally departs from Tella's structure — that would eventually justify revisiting this ADR.
- **To revisit:** if Tella's upstream goes unmaintained for an extended period, or if the LLC's needs (e.g., a real CRM-backed lead funnel, case-study heavy marketing pages) outgrow what a "light, simple, company" theme can reasonably support.

## Action Items

1. [x] Delete the uncommitted, byte-identical shadow-copy under site-level `layouts/` — removed entirely; Hugo now falls back to `themes/tella/layouts/` for everything not explicitly overridden.
2. [x] Remove the dead `PaperMod` submodule and its `.gitmodules` entry — removed from `.gitmodules`, `.git/config`, `.git/modules/`, and the working tree. The 124 files now show as pending deletions in `git status`; staging/committing them is left to the normal git workflow.
3. [x] Build `layouts/offerings/single.html`, `layouts/offerings/list.html`, and `layouts/offerings/summary.html`, wired to the `tagline`/`price`/`cta_*` front matter fields. The archetype's body no longer hardcodes a redundant CTA block now that the layout renders real buttons above and below the content.
4. [x] Build `layouts/projects/