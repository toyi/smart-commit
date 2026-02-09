# smart-commit

Agent Skill for AI coding assistants. This skill follows the [Agent Skills Standard](https://agentskills.io) and works with Claude Code, Cursor, Gemini Code Assist, GitHub Copilot, and other compatible tools.

Analyzes all uncommitted changes in a git repository, groups them by theme (directory, semantic content, timestamps), and creates multiple focused commits.

## Installation

```bash
npx skills add toyi/smart-commit
```

Or install globally:

```bash
npx skills add toyi/smart-commit -g
```

## Usage

- `/smart-commit` — Analyze changes and create all commits automatically
- `/smart-commit step` — Analyze changes and approve each commit one by one

## Features

- **Automatic commit grouping** — Groups changes by directory structure, semantic content, and temporal proximity
- **Hunk-level splitting** — Splits individual files across multiple commits when they contain changes belonging to different themes
- **Commit style detection** — Analyzes your recent commit history and reproduces the same message format (conventional commits, prefixed, plain, etc.)

**Triggers:** "smart commit", "organize commits", "group changes into commits"

**Example usage:**

```
/smart-commit
```

```
/smart-commit step
```

## How it works

1. **Detects your commit style** from recent history
2. **Collects all changes** (staged, unstaged, untracked, deleted, renamed)
3. **Groups files by theme** using directory paths, semantic analysis of diffs, and file timestamps
4. **Splits files at hunk level** when a single file contains changes for different themes
5. **Checks for merge conflicts** before committing
6. **Creates focused commits** either automatically or with step-by-step approval

## Safety

- Never pushes to remote — only creates local commits
- Never modifies file contents — only stages and commits existing changes
- Never adds AI attribution to commit messages
- Never runs linters or formatters

## Compatibility

This skill works with any Agent Skills Standard-compatible tool:

- Claude Code (Anthropic)
- Cursor
- Gemini Code Assist (Google)
- GitHub Copilot (Microsoft)

## License

MIT
