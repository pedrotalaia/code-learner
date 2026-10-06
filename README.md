# Learn by doing

A reusable coding skill for people who want to understand and apply code changes themselves.

The skill guides a coding agent to inspect relevant code, explain the change, and provide small, copy-ready steps instead of making changes on your behalf.

## Install

Install into the coding agents on your machine with the [`skills`](https://github.com/vercel-labs/skills) CLI. It asks which agents to install into, and whether to install globally or just for the current project:

```sh
npx skills add git@github.com:<your-user>/code-learner.git
```

This is a private repository, so the command uses your local git credentials (SSH key or `gh auth login`).

To install manually instead, copy or symlink `skills/learn-by-doing/` into your agent's skills directory, for example `~/.claude/skills/` for Claude Code or `~/.agents/skills/` for Codex.

## Usage

Ask for a change the way you normally would, and say that you want to apply it yourself, for example "teach me how to add pagination here". To leave tutoring mode for the current task, say "just do it".
