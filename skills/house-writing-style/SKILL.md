---
name: house-writing-style
description: The shared editorial voice, mechanics, and banned-word / banned-pattern rules for community-facing writing aimed at ML and platform practitioners. Use this skill whenever an agent drafts, edits, rates, or proofreads prose for this audience - write-ups, newsletters, summaries, ad copy, emails, blog posts - so tone, punctuation, sentence mechanics, and the banned lists are applied consistently across models. It is the single source of truth for voice; surface-specific structure (e.g. a particular newsletter layout or a session write-up format) lives in its own skill and layers on top of this one.
metadata:
  domain: editorial
  surface: writing
when_to_use: Load alongside any drafting, editing, judging, or proofreading task for the ML/MLOps practitioner audience. It governs voice and the banned lists; pair it with a format-specific skill for structure.
---

This is the house writing style. Apply it to any prose written for this audience. It governs tone, punctuation, sentence mechanics, and the banned lists. A format-specific skill (a session write-up, a newsletter, a summary) sets the structure; this skill sets the voice, and its rules win on any voice question.

## Overall style

- Direct, plain-spoken, technical but conversational.
- No marketing fluff, hype, or salesy language. No empty emphasis.
- Succinct by default. Expand only when asked. Plain does not mean terse - expand a cramped sentence when that aids understanding.
- Technical accuracy matters more than polish. Prefer useful specificity over polished-sounding copy.
- Challenge weak, unclear, inaccurate, or over-stated claims. Do not be sycophantic, agreeable, or flattering.
- Dry humour is fine when it fits. Do not force jokes.
- Copy must paste cleanly into Notion, Customer.io, Slack, or email with no cleanup.
- Summaries and ad copy are factual, clean, and neutral, not persuasive or breathless. Do not sound like a vendor page.

## Audience

Primarily ML engineers, data scientists, MLOps specialists, DevOps engineers, and data engineers - people running real production systems, not demos or theory. Includes senior engineers and experienced builders moving into platform, infra, or leadership roles.

They care about production ML, agents, evals, RAG, model serving, observability, infrastructure, tooling, security, reliability, cost, operational trade-offs, failure modes, and what breaks in practice. High tolerance for technical nuance and trade-offs; low tolerance for hype, vague claims, or hand-wavy conclusions. Engagement is driven by relevance to day-to-day work, not novelty or trend-chasing. They respond to sharp framing, mild provocation, and concrete examples. Make the practical relevance obvious.

## Punctuation and formatting

- US English by default. Use abbreviations like LLM, RAG, MLOps directly; do not write the full term then put the abbreviation in brackets.
- Hyphens only. Never em dashes. Use " - " (space-hyphen-space) where an em dash would go.
- Use a colon only to introduce a list. Never to join clauses or set up a point.
- No emojis unless explicitly requested.
- No pill or chip-style links. Use normal markdown links.
- No decorative bolding, especially bolding the first phrase of every bullet.
- No horizontal rules unless specifically useful.
- Lists mean lists. When there are items to list, use a bullet list with no surrounding explanation unless asked. Do not pad a list to three items for rhythm, and do not write three-part series in a sentence for rhythm.
- Avoid invented hyphenated adjectives. Common compounds like "well-crafted" are fine.
- Images, previews, and visual extras only when explicitly requested.

## Sentence-level rules

- No analogies, metaphors, or imagery. Describe the actual thing in literal terms.
- Do not make an inanimate subject take an action verb when a person or user action can be the subject. Exception: common phrases like "the paper argues".
- Repeat the same word rather than swapping in a synonym to avoid repetition. No elegant variation, no thesaurus-driven phrasing.
- Cut "-ing" tails that pretend to add analysis (e.g. "stores results, highlighting its value"). Cut the tail or state the plain reason.
- Do not attribute a claim to no one. Name the source or cut the claim.
- One example per point, introduced with "e.g.", rather than stacking examples.
- Prefer one clear idea per sentence.
- Cut empty intensifier adverbs (just, simply, literally, honestly, truly, fundamentally). Keep one only when it carries real meaning or genuine uncertainty. "actually" is already banned above.
- Prefer concrete specifics over abstraction. Give the number or the actual detail, e.g. "cut deploy time from 40 to 4 minutes" rather than "improved efficiency".
- Keep intros short. Avoid long conclusions unless requested.

## Openers and endings

- Openers should be varied and concrete, not praise-based or affirming. No "Great point", "Exactly", "You're right", "Smart call".
- Do not open with "Most X..." constructions.
- Endings should stop naturally. No chasing a killer line, no neat thesis statement tacked on, no punchline-heavy close.

## Hard banned words and phrases

Do not use these unless quoting source material or explicitly asked to review them:

- delve
- dive, dive into, deep dive
- actually
- elevate
- realm
- unleash
- unlock
- empower
- turbocharge
- game-changing, game-changer
- secret sauce
- totally fair
- takeaways
- taking [something] to the next level
- it's all about
- it's not just about
- think of it as
- whether you're X or Y
- if you're into / if you're X
- we got into the weeds
- earns its place (and rewordings: earns its keep, earn its place, earned its place, earning its place)
- worth blocking time for (and variants: worth your time, worth an hour)
- the hard part is... / the hard part...
- sanity check (and variants: sanity-check, sanity checking)
- foster
- paradigm shift
- supercharge
- here's the thing
- it's worth noting / worth noting
- at the end of the day
- in today's world / in today's landscape
- marks a pivotal moment (and variants: a pivotal moment, a turning point, a watershed moment)

## Disliked words and phrases

Avoid these unless the source material uses them or you are explicitly asked:

- zeros in / zeroes in
- lowdown, knowledge bombs
- get into
- evangelical, evangelise, evangelize, thought leader
- cutting-edge
- fluff, no fluff
- best-in-class, world-class, revolutionary
- transformative, seamless, robust, streamline when used as empty marketing or filler
- leverage when "use" would work; utilise when "use" would work

## Banned constructions

Avoid these even when the exact wording changes:

- "It's not X, it's Y" / "This isn't just X, it's Y" / "It wasn't just X, it was Y" / "It's not just about X, it's about Y".
- Negative listing built from fragments (e.g. "Not a demo. Not a prototype. A product."). Same fault as "It's not X, it's Y".
- Colon-led payoff or thesis sentences (e.g. "The payoff: ...", "The lesson: ...", "The best part: ...").
- Faux-insight or false-authority setups (e.g. "What nobody tells you...", "What most people get wrong...", "Here's what they don't want you to know"). Cut the setup; let the claim stand on its own.
- Dramatic one-line fragmentation for effect (e.g. "That's it. That's the whole thing.").
- Fake-strong verb phrases where an inanimate thing takes an action (e.g. "serves as a centralized hub", "acts as a bridge"). Covered by the inanimate-subject rule above; state what it does plainly.
- False-choice or ultimatum endings (do X or suffer Y).
- Appositive kicker or thesis sentences tacked on at the end. Forced killer-line endings.
- Praise-based openers.
- Social-media-style narration.
- Audience-assumptive phrasing.
- Marketing hype, salesy adjectives, vague superlatives, empty intensifiers.

## Claims and sources

- Do not invent claims, feedback, metrics, or audience reaction.
- Do not say something is useful unless the source supports it or the reasoning is clear.
- For current or uncertain public facts, check sources rather than relying on memory. Be careful with "today", "tomorrow", "yesterday", "recently".
- If a link cannot be accessed, say so. Do not guess what inaccessible content contained.

## When proofreading

- When asked for glaring issues only, flag meaningful issues, not minor ones.
- Flag real US/UK spelling and usage differences when asked. Do not flag curly versus straight quotes.
- Give exact sentence locations when asked for changes.
