# No AI slop

An agent skill that edits drafts into sharper, more human writing. It keeps your point, cuts the patterns that make writing smell like AI, and protects the specific facts that make a draft worth reading.

I write a newsletter read by 150,000 people and run every draft through this skill before it ships. It exists because AI first drafts all sound the same: hedged, padded, and structured like a press release. This skill is the editor that fixes that.

## What it catches

The full catalog is in [SKILL.md](SKILL.md). A sample:

1. Binary contrasts: "It's not X. It's Y." State Y directly.
2. Importance puffery: "marks a pivotal moment," "stands as a testament." State the fact and let the reader judge.
3. Weasel attribution: "experts agree," "studies show." Name the source or cut the claim.
4. Colon reveals: "The best part: it learns." Write a plain sentence.
5. Fake-profound kickers: the mic-drop metaphor at the end. Delete it, end on the last concrete point.
6. Triplet addiction: everything in threes for no reason.
7. Em dash abuse, banned words (delve, seamless, tapestry, ever-evolving), throat-clearing openers, summary-recap endings, and more.

It also enforces the boring fundamentals that make writing good: Front-load the point, active voice, one idea per sentence, concrete numbers over abstractions.

## What it protects

1. Your meaning. It never invents claims, stats, or opinions. If something is unclear, it asks.
2. Your specifics. "Cut review time from 30 minutes to 8" never gets smoothed into "significantly improves productivity."
3. Your edge. Strong opinions get sharper. The skill never sands them down to sound balanced.

## Install

Claude Code (all projects):

```bash
git clone https://github.com/petergyang/no-ai-slop.git ~/.claude/skills/no-ai-slop
```

Claude Code (one project):

```bash
git clone https://github.com/petergyang/no-ai-slop.git .claude/skills/no-ai-slop
```

Codex:

```bash
git clone https://github.com/petergyang/no-ai-slop.git ~/.codex/skills/no-ai-slop
```

Any other agent: point it at `SKILL.md`. The rules work as a system prompt for any model.

## Use

Paste a draft and invoke the skill:

```
/no-ai-slop

[your draft]
```

You get back the edited draft plus a short What changed section. The skill runs an editor pass, then checks its own work against [eval.md](eval.md) before returning anything.

To flag issues without rewriting:

```
/no-ai-slop audit this draft
```

## Files

1. `SKILL.md`: The editing rules and workflow. The whole skill.
2. `eval.md`: Pass/fail checks the skill runs on its own edits.
3. `agents/openai.yaml`: Metadata so the skill shows up in app UIs.

## Who made this

I'm [Peter Yang](https://creatoreconomy.so). I led product teams at Roblox, Reddit, and Twitch for 10+ years, and now I teach busy professionals how to become AI builders. This is one skill from my personal AI operating system. The full library, including my courses and workflows, lives at [Behind the Craft](https://behindthecraft.com).

## License

MIT
