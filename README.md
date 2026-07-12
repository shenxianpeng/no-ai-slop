# No AI slop

An agent skill that edits drafts into sharper, more human writing. It keeps your point, cuts the patterns that make writing smell like AI, and protects the specific facts that make a draft worth reading. It can also detect those patterns in any piece without rewriting it.

I write a newsletter read by 150,000 people and run every draft through this skill before it ships. It exists because AI first drafts all sound the same: Hedged, padded, and structured like a press release. This skill is the editor that fixes that.

## What it catches

All 21 patterns, with the rules and fixes in [SKILL.md](SKILL.md):

| Pattern | Smells like |
|---------|-------------|
| Binary contrasts | "It's not X. It's Y." |
| Throat-clearing openers | "Here's the thing..." |
| Faux-insight setups | "What nobody tells you..." |
| Colon reveals | "The best part: it learns." |
| Superficial analysis | "...highlighting the team's commitment" |
| Importance puffery | "marks a pivotal moment" |
| Weasel attribution | "experts agree," "studies show" |
| Fake-strong verbs | "serves as a centralized hub" |
| Synonym cycling | the agent, then the assistant, then the tool |
| Negative listing | "Not a X. Not a Y. A Z." |
| Dramatic fragmentation | "That's it. That's the whole thing." |
| Robotic rhythm | every sentence the same shape |
| Triplet addiction | "clear, concise, and compelling" |
| Audience flattery | "whether you're a founder or an exec" |
| Both-sides hedging | "powerful, but not without drawbacks" |
| Rhetorical setups | "What if I told you..." |
| Dead metaphors | "unlock," "deep dive," "landscape" |
| Fake-profound kickers | the mic-drop metaphor at the end |
| Summary-recap endings | "In conclusion..." |
| Formatting slop | emoji headings, decorative bold |
| Em dash abuse | dashes as a default rhythm crutch |

Plus a banned word list (delve, tapestry, seamless, pivotal, ever-evolving), hedging adverbs (really, genuinely, fundamentally), and filler phrases (it's worth noting, at the end of the day).

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

Any other agent: Point it at `SKILL.md`. The rules work as a system prompt for any model.

## Use

The skill has two jobs. Editing is the main one.

**1. Edit a draft.** Paste it and invoke the skill:

```
/no-ai-slop

[your draft]
```

You get back the edited draft plus a short What changed section. The skill runs an editor pass, then checks its own work against [eval.md](eval.md) before returning anything.

**2. Detect slop.** Ask whether a piece reads as AI:

```
/no-ai-slop is this AI slop?

[the text]
```

You get every pattern it found, each with the quoted line and a suggested fix. It doesn't rewrite, score the draft, or guess whether AI wrote it. AI detectors guess. Named patterns are evidence you can check yourself.

## Files

1. `SKILL.md`: The editing rules and workflow. The whole skill.
2. `eval.md`: Pass/fail checks the skill runs on its own edits.
3. `agents/openai.yaml`: Metadata so the skill shows up in app UIs.

## Who made this

I'm [Peter Yang](https://creatoreconomy.so). I led product teams at Roblox, Reddit, and Twitch for 10+ years, and now I teach busy professionals how to become AI builders. This is one skill from my personal AI operating system. The full library, including my courses and workflows, lives at [Behind the Craft](https://behindthecraft.com).

## License

MIT
