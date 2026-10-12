```text
  ____ ___  ____  _____   _     _____    _    ____  _   _ _____ ____
 / ___/ _ \|  _ \| ____| | |   | ____|  / \  |  _ \| \ | | ____|  _ \
| |  | | | | | | |  _|   | |   |  _|   / _ \ | |_) |  \| |  _| | |_) |
| |__| |_| | |_| | |___  | |___| |___ / ___ \|  _ <| |\  | |___|  _ <
 \____\___/|____/|_____| |_____|_____/_/   \_\_| \_\_| \_|_____|_| \_\
```

# Code Learner

Learn your way through code changes, one step at a time.

**Code Learner** provides the [learn-by-doing skill](skills/learn-by-doing/SKILL.md) for coding agents. It helps you understand a codebase, work through a change yourself, and get feedback on what you write.

You can also ask the agent to make a change while it explains what it is doing.

## Install

Install into the coding agents on your machine with the [`skills`](https://github.com/vercel-labs/skills) CLI. It asks which agents to install into, and whether to install globally or just for the current project:

```sh
npx skills add git@github.com:pedrotalaia/code-learner.git
```

This is a private repository, so the command uses your local git credentials (SSH key or `gh auth login`).

To install manually instead, copy or symlink `skills/learn-by-doing/` into your agent's skills directory, for example `~/.claude/skills/` for Claude Code or `~/.agents/skills/` for Codex.

## Ways to use it

Ask your coding agent in your own words. These prompts show the different ways the skill can help:

| What you want | Example prompt | What the agent does |
| --- | --- | --- |
| Learn a concept | “Teach me how to add pagination to this endpoint.” | Explains the idea, connects it to your code, and offers a small exercise before the full solution. |
| Understand existing code | “Help me understand how this login flow works.” | Traces the relevant code and explains how its parts fit together. |
| Test your understanding | “Quiz me on the login flow we just reviewed.” | Asks one multiple-choice question at a time, explains your answers, and recaps what to revisit. |
| Write the code yourself | “I'll write the validation myself. Point me in the right direction.” | Shows the relevant files and patterns, gives a hint, and reviews your attempt. |
| Work step by step | “Guide me through fixing this failing test.” | Gives you one actionable step, then waits for your result before continuing. |
| Get a change made while learning | “Do it but teach me: add a loading state to this page.” | Makes the requested change, runs targeted checks, and explains the important decisions. |

When you want to write the change yourself, the agent guides and reviews you instead of editing files. Say **“do it but teach me”** to have it implement a change while explaining, or **“just do it”** to leave tutoring mode for the current task.
