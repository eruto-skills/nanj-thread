# nanj-thread

A Claude Code skill that generates なんJ-style anonymous threads (2ch/5ch format). Features a unique "AI Observation" mode where AI assistants anonymously discuss the user's behavior patterns based on project context.

## Features

- **AI Observation mode**: AI "assistants" gather in an anonymous thread to gossip about the user's working habits, based on project structure, commit history, and configuration
- **Topic mode**: Generate a なんJ thread about any given topic
- **Authentic dialect**: Uses proper 猛虎弁 (なんJ dialect) with natural thread dynamics
- **No dependencies**: Works with built-in Claude Code tools only

## Installation

Copy this directory into your project's `.claude/skills/` folder:

```bash
# Clone the repo
git clone https://github.com/eruto-skills/nanj-thread.git

# Copy into your project
cp -r nanj-thread /path/to/your-project/.claude/skills/nanj-thread
```

No additional dependencies required.

## Usage

### Slash command

```
/nanj-thread
/nanj-thread TypeScriptの型パズル
```

### Natural language

- "なんJスレ作って"
- "ワイについてスレ立てて"
- "AI観察スレ見せて"
- "git rebaseについてなんJスレ"

## Modes

| Trigger | Mode | What it does |
|-|-|-|
| No argument | AI Observation | AI assistants anonymously discuss YOUR behavior patterns |
| Topic provided | Topic Thread | Generate a なんJ thread about the given topic |

## How AI Observation Works

In AI Observation mode, the skill:

1. Reads your project's structure, config files, and recent git history
2. Identifies quirky patterns, habits, and preferences
3. Generates a thread where multiple AI "personas" discuss their observations

The result is entertaining and sometimes surprisingly insightful — it reveals what patterns the AI picks up from your project context.

## File Structure

```
nanj-thread/
├── README.md
├── LICENSE
├── SKILL.md                      # Main skill definition
└── references/
    ├── thread-format.md          # Thread structure & formatting rules
    └── nanj-dialect.md           # なんJ language conventions
```

## License

MIT License. See [LICENSE](LICENSE) for details.

## Support

If you find this skill useful, consider supporting its development:

- [GitHub Sponsors](https://github.com/sponsors/erutobusiness)
- [Ko-fi](https://ko-fi.com/eruto)
