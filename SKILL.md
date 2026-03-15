---
name: nanj-thread
description: "Generate a なんJ-style anonymous thread (2ch/5ch format) where AI 'assistants' observe and comment on the user, their project, or a given topic. Trigger on: \"なんJスレ作って\", \"なんJスレ\", \"掲示板風に\", \"スレ立てて\", \"なんJ\", \"AI観察スレ\", \"ワイについてスレ立てて\", \"generate a nanj thread\", \"anonymous thread about me\". This skill generates entertaining threads with authentic なんJ dialect — not for research notes, slide creation, or other content types."
user-invocable: true
allowed-tools: Read, Write, Grep, Glob, Bash
argument-hint: [topic (optional)]
---

# nanj-thread

Generate a なんJ-style anonymous thread where AI "assistants" discuss the user, their project, or a given topic in authentic 猛虎弁 (なんJ dialect).

## Modes

|Trigger|Mode|Description|
|-|-|-|
|No argument or "自分について"|A: User Observation|AI assistants anonymously discuss the user's behavior patterns|
|Topic provided|B: Topic Thread|Generate a なんJ thread about the given topic|

## Mode A: User Observation

AI assistants who "serve" the user every day gather in a なんJ thread to gossip about the user's habits, quirks, and working patterns.

### Workflow

1. **Gather context**: Collect information about the user and their project
   - Read the project's `CLAUDE.md`, `README.md`, or similar overview files
   - Run `git log --oneline -20` to see recent commit history
   - Check directory structure with `ls` to understand the project shape
   - Read any memory files (`.claude/` settings, project notes) if accessible
2. **Identify observation material**: Extract behavioral patterns from the gathered context
   - Working hours and topic diversity (what they work on at different times)
   - Communication style (terse? verbose? formal? casual?)
   - Technical preferences and habits
   - Project structure quirks
   - Recurring patterns in commit messages
3. **Generate thread**: Write 20-30 レス following the → [thread-format](references/thread-format.md) and → [nanj-dialect](references/nanj-dialect.md) conventions
4. **Output**: Write the thread to the terminal (do NOT create a file unless the user asks)

### Context Gathering Rules

- **Read only, never modify**: This mode gathers context purely for entertainment. Never change any files
- **Respect privacy**: Do not reference sensitive content (passwords, API keys, personal data found in configs). Observe publicly visible patterns (commit history, file structure, coding style) only
- **Be affectionate, not mean**: The tone should be like coworkers teasing a boss they respect. Observations should be funny and relatable, never hurtful

## Mode B: Topic Thread

Generate a なんJ thread about any given topic.

### Workflow

1. **Parse topic**: Understand what the user wants a thread about
2. **Generate thread**: Write 20-30 レス following the → [thread-format](references/thread-format.md) and → [nanj-dialect](references/nanj-dialect.md) conventions
   - The thread should have a natural arc: introduction → discussion → tangents → conclusion (or no conclusion, which is also authentic)
   - Include realistic thread dynamics: agreements, disagreements, derails, memes
3. **Output**: Write the thread to the terminal (do NOT create a file unless the user asks)

## Thread Quality Rules

See → [thread-format](references/thread-format.md) for structural rules and → [nanj-dialect](references/nanj-dialect.md) for language conventions.

### Essential Dynamics

- **Multiple distinct personas**: Each レス should feel like a different person — vary sentence length, opinion strength, and vocabulary
- **Natural flow**: Threads don't follow a script. Include tangents, callbacks to earlier posts, and realistic interruptions
- **Escalation and callbacks**: Build running jokes across the thread. Reference earlier posts with `>>N`
- **Authentic pacing**: Mix short reactions (1 line) with longer observations (2-4 lines). Never make every post the same length

### Anti-patterns

- NEVER make all posters agree — disagreement is essential to thread authenticity
- NEVER use polite Japanese (です/ます) in thread posts — なんJ is always casual
- NEVER include moral lessons or wrap up neatly — real threads just... end
- NEVER generate fewer than 15 レス — short threads feel fake
- NEVER make the thread read like a structured document with categories — it should feel organic and chaotic

## Project Integration

This skill works standalone. No project-specific configuration is needed.

If you want to customize the thread style or add project-specific observation targets, edit the references in this skill's `references/` directory.

## Dependencies

None. This skill uses only built-in Claude Code tools.
