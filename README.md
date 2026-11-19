```
 ██████╗  ██████╗  ██████╗  ███████╗     ██╗      ███████╗  █████╗  ██████╗  ███╗   ██╗ ███████╗ ██████╗
██╔════╝ ██╔═══██╗ ██╔══██╗ ██╔════╝     ██║      ██╔════╝ ██╔══██╗ ██╔══██╗ ████╗  ██║ ██╔════╝ ██╔══██╗
██║      ██║   ██║ ██║  ██║ █████╗       ██║      █████╗   ███████║ ██████╔╝ ██╔██╗ ██║ █████╗   ██████╔╝
██║      ██║   ██║ ██║  ██║ ██╔══╝       ██║      ██╔══╝   ██╔══██║ ██╔══██╗ ██║╚██╗██║ ██╔══╝   ██╔══██╗
╚██████╗ ╚██████╔╝ ██████╔╝ ███████╗     ███████╗ ███████╗ ██║  ██║ ██║  ██║ ██║ ╚████║ ███████╗ ██║  ██║
 ╚═════╝  ╚═════╝  ╚═════╝  ╚══════╝     ╚══════╝ ╚══════╝ ╚═╝  ╚═╝ ╚═╝  ╚═╝ ╚═╝  ╚═══╝ ╚══════╝ ╚═╝  ╚═╝
                              ▶  L E A R N - B Y - D O I N G   S K I L L  ◀
```

An agent skill for Claude Code and Codex that turns code changes into lessons:
explanations, step-by-step guidance, quizzes, and reviews of the code you write yourself.

> [!IMPORTANT]
> **Requirements**
> - A coding agent that supports skills — Claude Code, Codex, or others supported by the `skills` CLI
> - `npx` (Node.js) — to install with the `skills` CLI
> - Git access to this private repo — SSH key or `gh auth login`
>
> No other dependencies. The skill is plain Markdown instructions, and it never edits your files unless you ask it to.

## Install

Install into the coding agents on your machine with the [`skills`](https://github.com/vercel-labs/skills) CLI. It asks which agents to install into, and whether to install globally or just for the current project:

```sh
npx skills add git@github.com:pedrotalaia/code-learner.git
```

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

- How the agent works: [SKILL.md](skills/learn-by-doing/SKILL.md)
- Verification guide: [references/verification.md](skills/learn-by-doing/references/verification.md)
