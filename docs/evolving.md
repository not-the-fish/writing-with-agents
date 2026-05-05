# Evolving

How to keep the system honest after the initial setup. Read this after a few weeks of using the system on real writing — the signals it describes won't be visible until you have some history.

The example writer's project-internal version of this advice lives in [`_meta/workflow_guide.md`](../_meta/workflow_guide.md), which is more concrete and tied to specific files. This doc is the higher-level version: when to update what, regardless of tool or project specifics.

## The two failure modes to watch for

Almost every problem with this kind of system collapses into one of these.

### 1. The artifacts drift away from the work

The voice profile says you're direct and unhedged. Your last three drafts are full of "I suspect" and "it remains possible that." Either the profile is wrong (and needs updating) or you're drifting from your own intentions (and need to notice). Often it's both.

When the artifacts and the writing diverge, the artifacts become aspirational fiction. The agent reads them and gives feedback calibrated to a writer who no longer exists. The feedback gets less useful. You stop trusting the system. You stop using it.

The fix: re-read the artifacts against your recent work, regularly. Specifically:

- Once a quarter, or after any significant push of new writing, ask the agent to compare your recent drafts against the voice profile. Not "evaluate the drafts" — "tell me where the profile no longer matches the writing."
- Treat surprises as data. If the agent identifies a new pattern, or fails to find an old one, something has shifted. Decide whether to update the profile or the writing.

### 2. The system creates pressure to over-use it

You start running every paragraph through the editor rule. You ask for feedback on a piece three times before it's done. You spend more time talking *about* writing than writing.

This is the system as procrastination. It feels productive. It is not.

The fix: notice the pattern. If you're using the agent more than once per editorial pass on a piece, you're probably stalling. The cardinal rule has a cousin: *the agent is not a substitute for sitting with the work.* When in doubt, close the chat and write.

## Signals that something needs to change

Below are the most common signals that one of the artifacts needs work, organized by where the signal usually shows up first.

### Signals to update the voice profile

- You finish a piece and notice you did something you can't quite name. New signature move; needs to be added.
- The agent gives feedback that pushes you toward a voice you don't want. Profile is missing something — likely an aspiration or a known weakness that would calibrate the feedback differently.
- A "known weakness" no longer applies. You've grown past it. Cut or revise.
- You read someone new and it changes your sense of what you want to do. Add to influences. Note what specifically you're reaching for.
- The profile starts feeling generic when you read it. It probably is. Push it harder.

### Signals to update a rubric

- You apply the rubric to a draft and the feedback feels off — either flagging things that are fine, or missing things that are real. The criteria need sharpening.
- You keep adding the same caveat in chat ("but ignore the X criterion for this kind of piece"). That caveat belongs in the rubric, or the rubric needs to be split.
- A criterion is too generic to score. ("Is the writing good?" is not a criterion.) Specify what "good" means here, or cut.
- Two criteria collapse into the same observation in practice. Merge or differentiate.
- You feel like applying the rubric is rote. It's probably encoding patterns you've internalized; you can simplify it without losing the work it does.

### Signals to update or add a rule

- You give the same instruction at the start of every chat. ("Read the voice profile first." "Don't suggest rewrites; give observations.") Encode it.
- The agent consistently does a thing you don't want. The rule isn't strong enough, or it's missing.
- You added a rule six months ago and it never gets activated. Cut it.
- You're working on a new content type (memoir, fiction, recipes) and the existing rules don't quite fit. Consider a content-type-scoped rule.
- A rule has grown to a wall of text. Split it, or cut the parts that aren't doing work.

### Signals to update audience and goals

- You publish something and find out who actually read it. The audience description was a guess; now you have data.
- Your sense of what you're trying to do has shifted. New goal, or an old goal that no longer fits.
- A "definition of done" never gets used in practice. It was a guess. Replace it with what you actually use to decide a piece is finished.

### Signals to log

The project log is cheap to update and easy to skip. Log:

- Anything you'll want to remember the *reason* for. Cut sections, structural decisions, "I tried X and it didn't work."
- Milestones — first draft of a piece, first publication, first time the system was useful, first time it was useless.
- Meta-changes — when you updated the voice profile and why, when you added or cut a rule.
- Reading or input that changed your direction.

The log is your own. It's not for the agent's benefit, though the agent can read it if useful. Write entries the way you'd want to read them in a year.

## Cadence

Different artifacts evolve at different rates.

| Artifact | How often to revisit | Trigger |
|---|---|---|
| Voice profile | Quarterly, plus after any major piece | Major piece finished, or new strong influence read |
| Rubrics | Continuously, in small ways | Every time you apply a rubric and the feedback feels off |
| Rules | Rarely | Repeated correction or new content type |
| Audience and goals | Quarterly, plus on publication | Publishing milestone, or your sense of audience shifts |
| Project log | After each piece, plus ad-hoc | Decision worth remembering; meta-change |

The voice profile and rubrics are the most active artifacts. Rules should change least often — they're behavioral defaults, and frequent changes mean the system never settles.

## When to leave things alone

Not every misalignment is a signal to update. Sometimes:

- You're in the middle of a piece and the system feels off. The piece will tell you what it needs; don't restructure the meta layer mid-draft.
- A rule annoys you for one chat. One chat is not a pattern.
- A rubric feels harsh on a particular draft. The rubric might be right and the draft might be weaker than you wish. Sit with it before changing the rubric to be kinder.

The general principle: change the system when it's repeatedly misleading you, not when it's saying something you didn't want to hear.

## When to start over

Rare, but it happens. Signals:

- You haven't opened the system in a month and don't miss it.
- The artifacts describe a writer you no longer recognize as yourself.
- You set this up for one kind of writing and you've moved into another (essays → fiction, professional → personal).

If any of these are true, it's not a maintenance problem. It's an architecture problem. Bootstrap a new version using the [setup guide](setup.md) and treat the old artifacts as a useful archive.

## The single test, restated

Anything you change in this system should make the cardinal rule easier to honor — easier to use the agent for what it's good at (observation, questions, criteria) and harder to drift into using it for what it isn't (drafting on your behalf).

If a change makes drafting-by-agent more tempting, undo it.
