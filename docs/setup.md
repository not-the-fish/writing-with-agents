# Setup

How to bootstrap your own version of this system. Plan on a few hours of focused work spread over a week or so. The system is meant to evolve, so the goal of setup is to get a usable v0, not a perfect v1.

## Before you start

You need:

- A folder of your own writing — published or unpublished, polished or rough. Five to fifteen pieces is plenty. More than thirty starts to be more than the agent can hold in one pass; pick a representative sample.
- An agentic coding tool. The example uses [Cursor](https://cursor.com), but [Claude Code](https://www.anthropic.com/claude-code), the [Cursor CLI](https://docs.cursor.com/en/cli/overview), or any chat-based agent that can read and write files in a folder will work. See [Where the rules and context files go](#where-the-rules-and-context-files-go) below.
- A willingness to push back. Every artifact the agent produces in this process is a draft for *you* to revise. The agent's first pass is never the right answer.

## Where the rules and context files go

The example puts behavioral rules in `.cursor/rules/*.mdc` because that's Cursor's convention. The same content goes elsewhere in other tools.

### Cursor

- Behavioral rules: `.cursor/rules/*.mdc`. Each file has YAML frontmatter:
  - `alwaysApply: true` for the core rule (every interaction).
  - `globs: "**/*.md"` for rules that should activate when the agent touches markdown files.
  - `description:` for rules the agent can pull in as needed.
- Context files: anywhere in the repo. Reference them in chat with `@_meta/voice_and_style.md`.

### Claude Code

- Behavioral rules: `CLAUDE.md` at the repo root. Claude Code reads this automatically. For multiple rule files, either put everything in one `CLAUDE.md` with section headings, or split into separate files and reference them from `CLAUDE.md`.
- Context files: anywhere in the repo. Reference them in prompts with explicit instructions like "Read `_meta/voice_and_style.md` before responding."

### Generic (any chat-based coding agent)

- Behavioral rules: `AGENTS.md` at the repo root. This is becoming a cross-tool convention. If the agent doesn't read it automatically, paste the contents (or an instruction to read it) at the start of each chat.
- Context files: anywhere. Always reference them by path in the prompt.

For the rest of this doc, "rules file" means whichever location your tool uses. The *content* of each rule is identical regardless of tool. You can copy `.cursor/rules/core.mdc` from this repo and paste its body into a `CLAUDE.md` or `AGENTS.md` and it will work.

## The setup sequence

Six steps, roughly in order. Don't try to do them all in one sitting. The voice profile especially benefits from sleeping on it.

### Step 1: Create the structure

```
your-writing-repo/
  .gitignore
  README.md
  [rules location for your tool]
  _meta/
    voice_and_style.md      # empty, will be seeded in step 3
    audience_and_goals.md   # empty, will be seeded in step 4
    project_log.md          # empty
    rubrics/                # populated in step 5
  [your writing folders, however you organize them]
```

You can copy `.gitignore`, the rule files, and the rubric scaffolds from this repo as starting points. Replace everything in `_meta/voice_and_style.md` and `_meta/audience_and_goals.md` — those are the previous writer's, not yours.

### Step 2: Install the cardinal rule first

Before anything else, put this rule in place. Copy the contents of [`.cursor/rules/core.mdc`](../.cursor/rules/core.mdc) (or just the prose body, without frontmatter) into your tool's rules location. Adjust the project layout table at the bottom to match your folders.

This rule does the most work. Even if you stop the setup process here and never build a single rubric, the cardinal rule alone makes the agent meaningfully more useful for writing.

### Step 3: Seed the voice profile

This is the highest-leverage step. Allow yourself an afternoon and a follow-up morning. The work happens in two passes that interleave: things the agent can observe from your drafts, and things only you can name.

Start a new chat. Have your writing folder available to the agent.

#### Pass A: what the agent observes

Some sections of the voice profile are best seeded by the agent reading your work and surfacing patterns. You couldn't see these from inside your own writing — you're too close.

**Bootstrap prompt:**

> Read everything in [folder]. Then draft sections of a voice and style profile for me, using only what you can observe from my drafts:
>
> - **Signature Moves** — specific craft moves that recur, with quoted examples
> - **Tonal Range** — how the voice shifts across content types
> - **Vocabulary Tendencies** — recurring word choices, syntactic habits, register markers
> - **Recurring Themes** — subjects and preoccupations that show up across pieces
> - **Known Weaknesses** — patterns that seem to be holding the writing back, framed as observations for me to confirm or reject
>
> Use specific quotes from my drafts as evidence. Do not generalize. Do not flatter. If you see a pattern only twice, say "I noticed this twice" rather than calling it a signature move. Do not write prose on my behalf.

What you'll get: a draft that's roughly 60% useful. The agent will catch real patterns you couldn't see. It will also miss things, overstate things, and occasionally invent things. **Revise. Don't accept.** Read every claim against your sense of the work.

#### Pass B: what only you can name

Influences and aspirations come from the writer, not the work. The agent can't see who you're reaching for. But the agent can be a useful interrogator — pressing on vague claims, asking for specifics, pulling examples from your drafts that confirm or complicate what you think you want.

The way to do this: jot in brief notes yourself, then ask the agent to push back.

**Bootstrap prompt:**

> Here are some initial notes on my Influences and Aspirations sections. They are sketchy on purpose. I want you to ask follow-up questions to help me sharpen them. For each note, you can:
>
> - Ask me to be more specific about *what* I admire (the prose? the structure? the willingness to do a particular thing?)
> - Pull examples from my own drafts where I'm reaching for the quality I'm describing — or where I'm conspicuously not — and ask whether that's deliberate.
> - Tell me when something I've said is too vague to be useful and ask a clarifying question.
> - Push back when I claim an aspiration but my drafts show no evidence I'm working toward it.
>
> Do not write the entries for me. Ask one or two questions at a time, wait for my answers, and only after I've answered should we move on.
>
> [Paste your notes. Example: "Kazuo Ishiguro — prose. Unreliable narrators. The way you can feel what the character won't say."]

This back-and-forth is where the profile actually gets sharp. The agent's questions force you to articulate things you'd otherwise leave gestural. Expect a single influence to take ten minutes of conversation before the entry is precise enough to be useful.

For an example of what this artifact looks like after several rounds, see [`_meta/voice_and_style.md`](../_meta/voice_and_style.md) in this repo. The Influences section in particular reflects multiple passes of this kind of refinement.

### Step 4: Scaffold audience and goals

This one is faster. The pattern is the same as Pass B above: you seed brief notes, the agent asks questions to refine, occasionally pulling from your drafts to challenge what you've written.

**Bootstrap prompt:**

> Help me draft an audience-and-goals document for my writing. I'll start by jotting brief notes for each of my content types; you'll ask follow-up questions to help me sharpen them.
>
> The doc should cover, for each major content type:
> - Primary audience (who specifically?)
> - What they come to my writing for
> - Publishing goals (where, how often)
> - Definition of "done" (what does ready-to-publish look like?)
>
> When I give you my initial notes, you can:
> - Ask clarifying questions (who specifically? what magazines? what does "good" mean here?)
> - Point out when my stated audience and what my drafts actually do don't match, citing specific drafts.
> - Flag inconsistencies — places where my goals for one content type seem to cut against another.
> - Note when I've left something vague enough that I'm dodging a decision.
>
> Do not write content for me. Ask one or two questions at a time and wait for my answers.
>
> [Paste your initial notes per content type.]

Expect this to surface things you haven't decided yet. That's the point. Mark anything you're unsure about with an HTML comment (`<!-- open question: ... -->`) and revisit later.

For an example, see [`_meta/audience_and_goals.md`](../_meta/audience_and_goals.md).

### Step 5: Decide which rubrics you actually need, then draft them

Don't start by copying a generic rubric set. Start by sketching what *you* think you'd want to evaluate, given your content types and goals — then ask the agent to push back before you write any rubrics in detail.

#### Pass A: scope the rubric set

**Bootstrap prompt:**

> Read `_meta/voice_and_style.md` and `_meta/audience_and_goals.md`. Here is my initial sketch of the rubrics I think I want, with one-line descriptions of what each one would evaluate:
>
> [Paste your sketch. Example: "Structure — does the piece hold together. Voice — does it sound like me. Newsletter rigor — are the claims sourced. Memoir honesty — am I being fair to the people I'm writing about."]
>
> Give me feedback on this set. Specifically:
> - Does the set make sense given the content types I write?
> - Are any of these likely to collapse into each other in practice (e.g., "structure" and "pacing" might be one rubric, not two)?
> - Are there things I should evaluate that this set is missing — patterns from my voice profile or goals that don't map onto any of these rubrics?
> - Are there rubrics that sound nice but I won't actually use? (Be specific about which content types each one would apply to.)
>
> Do not draft the rubrics yet. Just feedback on the scope.

This conversation usually trims and renames things. Some sketched rubrics get merged. Some get split. Some get dropped because they sounded reasonable but had no obvious application.

#### Pass B: draft each rubric and calibrate

Once the set is decided, draft each rubric. The example uses a Not Yet / Developing / Strong table format with four to six criteria — that's a reasonable target.

You can ask the agent to draft criteria from your voice profile and goals (since those describe what "good" means for you), then revise. Or sketch criteria yourself and have the agent suggest sharpenings. Either works; the second produces better rubrics faster if you have the time.

After drafting, calibrate against real drafts:

**Bootstrap prompt (per rubric):**

> Read `_meta/rubrics/structure.md` and `_meta/voice_and_style.md`. Then read [a recent draft I'm willing to evaluate]. Apply the rubric.
>
> Then tell me: which criteria captured something real about this draft, and which felt off or unhelpful? Be specific. If a criterion is too generic to be actionable, say so. If two criteria flagged the same thing, point that out.

Run this against one or two real drafts per rubric. After each pass, edit. Sharpen criteria that felt generic. Cut criteria that didn't surface anything useful. Add criteria for things you noticed but the rubric missed.

The rubrics in this repo went through this loop several times. Yours should too.

### Step 6: Add role-specific rules as patterns emerge

Don't pre-emptively add the editor, writing coach, and research assistant rules. Use the agent for those tasks first. When you find yourself giving the same setup instruction at the start of every editorial chat ("read the voice profile, give feedback as observations not rewrites, separate structural from prose feedback"), encode that instruction as a rule.

Each example rule in `.cursor/rules/` corresponds to a pattern that came up enough to need encoding. Yours will look different.

## A reasonable Day 1 → Week 2 cadence

Don't do this all at once.

| When | Do |
|---|---|
| Day 1, 30 min | Set up the directory structure and install the cardinal rule (steps 1–2). Use the system as-is for any writing you do that day. |
| Day 1, 2 hr | Run the voice profile Pass A prompt (agent observes patterns from your drafts). Read the agent's draft. Sleep on it. |
| Day 2, 1 hr | Revise Pass A. Then run Pass B (your notes on influences and aspirations, agent challenges and refines). |
| Day 3 | Audience and goals (step 4). |
| Day 4 | Scope the rubric set (step 5, Pass A). |
| Day 5 | Draft and calibrate one or two rubrics (step 5, Pass B). You don't need all of them on day one. |
| Week 2+ | Use the system on real writing. Add role-specific rules only when you notice yourself repeating instructions (step 6). |

## Common bootstrapping mistakes

- **Accepting the first draft of the voice profile.** It's never right. The agent will smooth your voice toward generic competence. Push back specifically on every claim.
- **Making the rubrics too comprehensive.** Six criteria per rubric is plenty. If a rubric has fifteen criteria, it's not a rubric anymore — it's a checklist that nobody will use.
- **Adding rules before patterns exist.** Rules encode tested behavior. If you're guessing at what you'll want, you'll get it wrong. Use the agent first; rule-ify second.
- **Treating `_meta/` files as fixed once written.** They're not. They're working drafts of your own self-understanding. Plan to revise.

## What v0 success looks like

After about a week of work, you should have:

- A rules file that consistently produces feedback (not rewrites) when you ask for editorial review.
- A voice profile you mostly agree with and that you'd be willing to show another reader — including Influences and Aspirations sections that say something specific.
- An audience-and-goals doc with at least one content type fully fleshed out.
- A scoped set of rubrics that fits your content types, with two or three drafted and calibrated against real drafts.
- An empty project log waiting for its first entry.

That's enough to start working. Everything else can grow.
