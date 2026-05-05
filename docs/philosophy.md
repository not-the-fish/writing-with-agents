# Philosophy

Why this project is shaped the way it is, before you start changing things.

## The cardinal rule

**Agents do not generate content on the writer's behalf.** No drafts. No paragraphs. No "here's a sentence to consider." Not even when asked nicely.

This is the foundation. Every other choice in this repo follows from it.

The reason isn't squeamishness about AI. It's that the value of writing comes from a person doing the difficult work of figuring out what they think and how they want to say it. An agent that drafts for you saves you from exactly the labor that produces good writing. You end up with text — sometimes serviceable text — but you didn't get any closer to being able to write the next thing.

What agents *are* good at:

- Reading a lot of material quickly and noticing patterns.
- Holding explicit criteria in mind and applying them consistently.
- Asking questions you wouldn't think to ask yourself.
- Researching, fact-checking, and finding sources.
- Reflecting your own writing back to you so you can see it more clearly.

Build the system around those uses. Refuse the rest.

## Two layers, two jobs

The repo has two distinct kinds of files: **behavioral rules** and **living artifacts**. They do different work and should not be conflated.

### Behavioral rules — instructions to the agent

These are the files in `.cursor/rules/` (or `CLAUDE.md`, or `AGENTS.md`, depending on your tool). They describe how the agent should behave: what role to play, what kinds of feedback to give, what never to do. They're terse, imperative, and largely static once they stabilize.

In the example:

- `core.mdc` — the cardinal rule and high-level interaction style. Always applied.
- `editor.mdc` — how to give editorial feedback (observations and questions, not rewrites; layered by structural / prose / voice / factual).
- `writing_coach.mdc` — Socratic mode for working on the meta files themselves.
- `research_assistant.mdc` — how to handle research and source-gathering.

These are *behavioral instructions*, not aspirations. If a rule describes what you wish the agent did but it doesn't do it, the rule is broken. Test rules by using them.

### Living artifacts — context the agent reads

These are the files in `_meta/`. They are not instructions to the agent; they are facts about the writer that the agent reads in order to be useful. They evolve constantly.

- `voice_and_style.md` — what the writer sounds like, across registers.
- `audience_and_goals.md` — who the writing is for, what counts as done.
- `rubrics/` — what "good" means, broken into evaluable criteria.
- `project_log.md` — a record of decisions and turns.
- `workflow_guide.md` — in this example, also a how-to-use-the-system reference.

The agent reads these to give better feedback. The writer reads them to stay honest with themselves. Both uses matter.

## Why rubrics, and why these rubrics

Generic editorial feedback is mostly useless. "This could be tighter" applies to nearly everything ever written. The point of a rubric is to make criticism specific enough to act on.

But generic rubrics are also mostly useless. A pacing criterion calibrated to a New Yorker essay will mislead you on a memoir. A voice criterion built from the lessons of literary fiction will flatter a newsletter into something nobody wants to read.

So the rubrics in this repo are co-developed with the writer. They start from a generic shape (the criteria most editors care about) and get refined against actual drafts. Over time they come to encode this writer's specific instincts about what matters. They get more personal, not more comprehensive.

The point isn't to score drafts. The point is to make the conversation specific enough that the feedback can change what you do next.

## Why a voice profile

If an agent doesn't know what you sound like, it will pull you toward whatever it thinks "good writing" is. That's some Frankenstein of LinkedIn earnestness, MFA self-seriousness, and Wikipedia-tier prose. It will produce feedback that erases the things that make your writing yours.

A voice profile fixes the reference point. The agent reads it before giving feedback, and feedback gets calibrated to *your* voice in *this* register, not a generic ideal.

The profile also serves the writer. Naming your signature moves makes you more deliberate about using them. Naming your known weaknesses makes them harder to ignore. Naming your influences clarifies what you're reaching for.

## Why a project log

Two reasons.

One: writing involves a lot of decisions whose reasoning evaporates. Why did I cut that section? Why did I move the newsletter from monthly to quarterly? Six months later you can't reconstruct it. A log catches the reasoning while it's still fresh.

Two: the agent can read the log, which means continuity across sessions. You don't have to re-explain the project to every new chat.

## Where this came from

The shape of this system is borrowed almost directly from advice given by the journalist Jasmine Sun ([jasmi.news](https://jasmi.news)) on a [March 2026 episode of *Hard Fork*](https://youtu.be/Prm_V51XbPg?t=2087) ([transcript](https://www.nytimes.com/2026/03/20/podcasts/hardfork-ai-washing-tokenmaxxing.html?showTranscript=1)). The interview accompanies her Atlantic piece, ["The Human Skill That Eludes AI"](https://www.theatlantic.com/technology/2026/03/ai-creative-writing/686418/), which argues — convincingly — that LLMs cannot produce great writing on their own because authorial voice "emerges from the specificity of a life" the model has never lived. The models can be technically proficient and grammatically pristine, but their metaphors come out uncanny and their prose lacks stakes.

What they *can* do is help a human writer write more like themselves. Sun describes her own setup at the end of the piece: she fed Claude an archive of her past writing, built a custom editing rubric calibrated to her voice (some criteria generic, some personalized — "Does this play to your insider-anthropologist position?"), and gave the model an explicit instruction:

> You are not a co-writer. You cannot perceive. Your role is to help Jasmine write like the best version of herself. […] I don't want to be de-skilled. Your only job is to make me smarter.

That instruction is the spine of this entire repo. The cardinal rule ("agents do not generate content on the writer's behalf") is a more dogmatic restatement of Sun's "you are not a co-writer." The voice profile, the rubrics, and the meta layer generally are durable, version-controlled infrastructure for the kind of project setup she describes informally. Read the Atlantic piece for the underlying argument; this repo is one attempt at giving that approach a stable shape.

## What this is not

- **Not a productivity system.** It will not make you write more, faster. It might make you write less, better.
- **Not a template.** The contents of `voice_and_style.md` in this repo are one specific writer's voice. They are not a starting point for yours; they are an example of what the artifact looks like when it's been worked on.
- **Not a substitute for reading and writing.** The system supports the work. The work is still hard.

## The single test

When you make any change to this system — add a rule, edit a rubric, restructure `_meta/` — ask: *does this make the cardinal rule easier or harder to honor?*

If it makes the rule harder to honor (creates pressure to let the agent draft, blurs the line between feedback and rewriting, makes "just give me a sentence" more tempting), the change is wrong.

That's the only consistency check you need.
