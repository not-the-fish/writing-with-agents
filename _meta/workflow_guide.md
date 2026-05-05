# Working with Agents

A practical guide to using AI agents in this writing project — when to engage them, what to ask, how to use the rubrics, and how to keep the whole system evolving.

## When to Engage Agents

### Before Writing

**Research Assistant** — for background material, source-gathering, and fact-finding before you start drafting.

> `Research the current landscape of data engineering roles at nonprofits. Consult @_meta/audience_and_goals.md for context on my audience.`

**Writing Coach** — for ideation. When you have a topic but not a frame, the coach can ask Socratic questions to help you find your angle. Pair this with the Ideation rubric to stress-test a concept before committing to a draft.

> `Read @_meta/voice_and_style.md and @creative_nonfiction/memoir/ideas.md. I want to write about my friendship with Paula but I can't find the frame. Ask me questions.`

### During Drafting

Agents are mostly off-stage here. You draft. The exception is getting unstuck:

- Ask the **Editor** for a mid-draft structural read: "I have the first half of this piece. Where does the arc seem to be heading, and where does it stall?"
- Ask the **Writing Coach** to help you figure out what the piece is trying to do: "I keep circling back to X but I don't know if it's the real subject. Ask me questions about what I'm avoiding."

### After a Draft

This is the primary moment for agent feedback. Use the **Editor** for layered evaluation — structural, prose-level, voice, factual — ideally one or two layers at a time (see "How to Use the Rubrics" below).

> `Read @creative_nonfiction/personal_essays/https_genders.md and evaluate it against @_meta/rubrics/structure.md. Focus on pacing in the final third.`

### Between Pieces

Use the **Writing Coach** for reflective work:

- Update `voice_and_style.md` after finishing a piece — did you discover new signature moves or tonal range?
- Refine rubrics that didn't capture what mattered in the last review.
- Fill in `audience_and_goals.md` (currently a skeleton).

> `Compare my voice in @archive/old_blog/posts/ with @newsletter/the_data_for_good_job_search.md. What changed? What did I lose?`

### When NOT to Engage

- When you're in flow. Don't interrupt momentum to get validation.
- When the impulse is to outsource a decision rather than sit with it. If you're asking an agent because you don't want to choose, that's a sign you need to think, not chat.
- When it would be procrastination. Agent interaction can feel productive while actually being a way to avoid the discomfort of not knowing what to say yet. Name that when it's happening.

---

## What to Ask (and What Not to Ask)

### Good Questions by Role

**Research Assistant**

- `Fact-check the claims in @newsletter/the_data_for_good_job_search.md, starting from the "Traditional Roles" section.`
- `Find 3-5 credible sources on AI adoption at nonprofits, organized by subtopic.`
- `What are the current salary ranges for data engineers at mission-driven organizations?`

**Editor**

- `Review @newsletter/the_data_for_good_job_search.md at the structural level only. Where does it lose momentum?`
- `Evaluate @creative_nonfiction/personal_essays/https_genders.md against @_meta/rubrics/voice.md — where am I hedging when I should commit?`
- `What's working well in the opening of this draft?`

**Writing Coach**

- `I'm noticing a pattern in my recent drafts where I retreat into analytical mode whenever the material gets emotionally difficult. Is that showing up in the voice profile?`
- `The Momentum criterion in @_meta/rubrics/prose.md doesn't feel right anymore — help me articulate what I actually care about.`
- `Read @_meta/voice_and_style.md. I just finished reading [author]. Here's what struck me about their prose: [observations]. Help me figure out what this means for my own aspirations.`

### Questions to Avoid

- **"Write this for me."** The cardinal rule. Agents don't generate content.
- **"What should I say here?"** This outsources the writing to the agent. Instead: "I'm trying to convey X in this section but it's not landing. What questions should I be asking myself?"
- **"Is this good?"** Too vague. Specify which dimension: Structure? Voice? Prose momentum? Point the agent at a rubric.
- **"Use all the rubrics on this draft."** Evaluating everything at once produces unfocused feedback. Pick one or two rubrics per pass.

---

## How to Use the Rubrics

Each rubric lives in `_meta/rubrics/` and maps to a stage of the writing process and a set of content types. Use them by `@`-mentioning the rubric file in your prompt and specifying which criteria to focus on.

### By Stage


| Stage                                     | Rubric            | Key Question                                                           |
| ----------------------------------------- | ----------------- | ---------------------------------------------------------------------- |
| Ideation / outlining                      | **Ideation**      | Does this concept have a frame only I would find?                      |
| After a full draft                        | **Structure**     | Does the arc carry the reader? Is the governing frame doing real work? |
| Late-stage revision                       | **Prose**         | Does this reward being read aloud?                                     |
| Any stage, especially post-draft          | **Voice**         | Does this sound like me in the right register?                         |
| Creative nonfiction drafts                | **Memoir**        | Am I being honest about myself and fair to others?                     |
| Pre-publication (newsletter/professional) | **Fact Checking** | Would every claim hold up if a reader checked my sources?              |


### By Content Type


| Content Type            | Primary Rubrics                           | Also Consider      |
| ----------------------- | ----------------------------------------- | ------------------ |
| Newsletter              | Structure, Voice, Fact Checking           | Prose (late stage) |
| Personal essay          | Ideation, Structure, Prose, Voice         | —                  |
| Memoir                  | Ideation, Structure, Prose, Voice, Memoir | —                  |
| Business copy           | Voice, Fact Checking                      | Structure          |
| Love letters / personal | Voice                                     | —                  |


### How to Ask for Rubric-Based Feedback

Be specific. Name the rubric, and if possible, the criterion within it.

- **Focused:** `Evaluate this against the Structure rubric, specifically Pacing and Closing.`
- **Unfocused:** `Evaluate this against all the rubrics.`

One or two rubrics per editorial pass. If you need both structural and prose-level feedback, do them in separate conversations — structural first, since there's no point polishing sentences in a section that might get cut.

---

## How to Keep `_meta/` Alive

These are living documents. They should evolve as your writing does. Here's when to update each one.

### `voice_and_style.md`

Update when:

- You finish a piece and notice new signature moves, tonal shifts, or vocabulary tendencies.
- You read an author who changes how you think about your own writing (add to Influences).
- A "known weakness" no longer applies, or a new one emerges.
- Your aspirations shift.

Use the **Writing Coach** in Agent mode for these sessions — the coach can read your recent drafts against the existing profile and surface what's changed.

### `audience_and_goals.md`

This file is currently a skeleton. Fill it in, then revisit:

- Quarterly, or whenever you start a new content type.
- When your sense of audience shifts (e.g., you start publishing the newsletter and learn who's actually reading).
- When you set or hit a milestone.

### `rubrics/`

Update when:

- A rubric fails to capture what mattered in a draft review. If the feedback felt off, the rubric criteria may need sharpening.
- You develop a new instinct about what "good" means for your writing. Rubrics should get more personal over time, not more comprehensive.
- Use the Notes section at the bottom of each rubric file to track what's working and what isn't before making changes.

### `project_log.md`

Update after:

- Finishing a piece or publishing.
- Making a significant decision about direction.
- Completing a round of meta-work with the Writing Coach (updating the voice profile, refining rubrics).
- Any moment where you want to record what you were thinking and why.

---

## How to Evolve `.cursor/rules/`

The rule files in `.cursor/rules/` control how agents behave. They're behavioral instructions, not aspirations.

### When to Update a Rule

When agent behavior consistently misses the mark in a specific, repeatable way. If you find yourself correcting the same thing across multiple conversations, encode the correction as a rule.

### When to Add a New Rule

When you repeatedly give the same instruction at the start of conversations. That's a signal the instruction belongs in a rule file, not in your prompt. Possible future rules:

- A `newsletter.mdc` encoding newsletter-specific conventions (structure, tone, sourcing standards).
- An `archive.mdc` for how to use old blog posts as reference material when developing new pieces.
- Genre-specific rules as you start writing fiction or recipes.

### What to Watch For

- **The cardinal rule is the foundation.** Every rule should be compatible with "never generate content." If a new rule creates tension with that principle, the new rule is probably wrong.
- **Keep rules concise.** If a rule file is getting long, it may be trying to do too much. Split it or pare it back.
- **Rules encode tested patterns.** Don't add a rule based on a hunch about what you'll want. Use it in conversation first, confirm it works, then encode it.

---

## Cursor Quick Reference

A short reference for the Cursor features you'll use most.

### `@`-mentions

Point agents at specific files or folders to include them as context. This is the primary way to direct which rubrics, drafts, or reference material the agent should read.

- **Single file:** `@_meta/rubrics/voice.md`
- **Folder:** `@archive/old_blog/posts/`
- **Multiple files:** `@_meta/voice_and_style.md and @creative_nonfiction/memoir/ideas.md`

### Modes

- **Agent mode** — Can read and edit files. Use for Writing Coach sessions that update `_meta/` documents, or when you want the agent to help reorganize material.
- **Ask mode** — Read-only. Use for editorial feedback where you don't want the agent touching your draft. Also good for research and ideation.
- **Plan mode** — For larger structural questions where you want to think through an approach before executing. Good for planning a multi-part newsletter series, reorganizing the project structure, or scoping a new content type.

### Chat Hygiene

- **One task per chat.** Start a new chat for each distinct task — one editorial pass, one research request, one ideation session. Don't try to do ideation, drafting support, and editing all in one conversation. Context degrades and roles blur.
- **Name what you want.** Be explicit about which role you want the agent to play and what kind of feedback you're after. The rules in `.cursor/rules/` shape default behavior, but your prompt steers the conversation.

