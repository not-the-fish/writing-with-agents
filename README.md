# Writing With Agents

A working example of how to set up a writing project for collaboration with AI coding agents — without letting them write for you.

This repo contains the actual scaffolding from a real writer's project (Erika Salomon), stripped of the drafts. The files in `.cursor/rules/` and `_meta/` are not a sanitized template; they are what one writer arrived at after a few weeks of using the system. Read them as one example, not the right answer.

## What's here

| Path | What it is |
|---|---|
| `.cursor/rules/` | Behavioral rules that shape agent default behavior in the example. Cursor-flavored, but the *content* of each rule is portable to any agent front-end. |
| `_meta/voice_and_style.md` | A living profile of the writer's voice — influences, signature moves, tonal range across registers, known weaknesses, aspirations. Co-developed with an agent through close reading of existing drafts. |
| `_meta/audience_and_goals.md` | Who the writing is for, by content type, and what success looks like. |
| `_meta/rubrics/` | Six evaluation rubrics (ideation, structure, prose, voice, memoir, fact checking) used to scope editorial feedback. |
| `_meta/workflow_guide.md` | The example writer's own internal guide to working with their agents. Project-specific, but useful as a reference. |
| `_meta/project_log.md` | A running log of decisions and milestones. |
| `docs/philosophy.md` | Why the project is shaped this way. Read first. |
| `docs/setup.md` | How to bootstrap your own version, with copy-pasteable prompts. |
| `docs/evolving.md` | How to keep the system honest as your writing changes. |

## The core idea, in one paragraph

AI agents are good at observing patterns, asking questions, and applying explicit criteria. They are bad at sounding like you. So: use them for the work they're good at (research, editorial feedback, surfacing patterns in your own writing) and refuse to let them do the work they aren't (drafting prose on your behalf). The `.cursor/rules/` files encode that refusal as the agent's default behavior. The `_meta/` files give the agent the context it needs to be useful: what your voice sounds like, what you're trying to do, what "good" means for each kind of piece.

## Tool notes

The example was built in [Cursor](https://cursor.com), which is why the rules live in `.cursor/rules/` as `.mdc` files with frontmatter. The pattern works in any agentic coding front-end. Translation:

| In Cursor | In Claude Code | In a generic agent setup |
|---|---|---|
| `.cursor/rules/core.mdc` (with `alwaysApply: true`) | `CLAUDE.md` at repo root, or `AGENTS.md` | `AGENTS.md` at repo root |
| `.cursor/rules/editor.mdc` (with `globs:` for scoping) | A section in `CLAUDE.md`, or a separate file referenced from it | A separate markdown file referenced from `AGENTS.md` |
| `@_meta/voice_and_style.md` mention in chat | "Read `_meta/voice_and_style.md` before responding" in the prompt | Same — explicit instruction in the prompt |

See [docs/setup.md](docs/setup.md) for a fuller mapping and the file contents that go in each location.

## Where to start

1. Read [docs/philosophy.md](docs/philosophy.md) — the why.
2. Skim `.cursor/rules/core.mdc` and `_meta/voice_and_style.md` — see what one real instance looks like.
3. Read [docs/setup.md](docs/setup.md) — bootstrap your own.
4. Come back to [docs/evolving.md](docs/evolving.md) after a few weeks of use.
