# DevMark

```
  ____  _____ __     ____  __    _    ____  _  __
 |  _ \| ____\ \   / /  \/  |  / \  |  _ \| |/ /
 | | | |  _|  \ \ / /| |\/| | / _ \ | |_) | ' /
 | |_| | |___  \ V / | |  | |/ ___ \|  _ <| . \
 |____/|_____|  \_/  |_|  |_/_/   \_\_| \_\_|\_\
```

**A bookmark for your development work.**

Save your state when leaving a project. Restore your context when you return.

---

## The Problem

You work on 5 projects a week. You leave one, come back days later, and think:

*"What was I doing? Where did I leave off? What's next?"*

## The Solution

DevMark is your development bookmark. It tracks where you are, what you did, and what's next.

```
    ┌─────────────────────────┐
    │  ┌───────────────────┐  │
    │  │  BOOKMARK          │  │
    │  │ "Fixed auth bug,  │  │
    │  │  need to add      │  │
    │  │  tests next"      │  │
    │  └───────────────────┘  │
    │                         │
    │  Recent:               │
    │  - Yesterday: API work │
    │  - Monday: UI fixes    │
    └─────────────────────────┘
```

---

## Features

- **Auto-logging** via git hooks (zero effort)
- **Quick save** when you're done for the day
- **Context restore** when you return
- **AI assistant** to answer "What was I doing?"
- **Cross-project view** of your week

---

## Install

```bash
git clone https://github.com/95987-AP/DevMark.git
cd devmark
pip install -e .
```

## Quick Start

```bash
# Initialize in a project
cd your-project
devmark init

# Save your state when leaving
devmark save "Fixed login bug, need to write tests"

# When you return
devmark status           # See your bookmark
devmark ask "what's next?"  # Ask AI

# See all your projects
devmark projects
devmark week             # What you worked on this week
```

---

## Commands

| Command | Description |
|---------|-------------|
| `init` | Initialize DevMark in a project |
| `save` | Save your current state/bookmark |
| `status` | Show bookmark + recent history |
| `log` | View full history |
| `todo` | Manage project todos |
| `ask` | Ask AI about your project |
| `projects` | List all tracked projects |
| `week` | Show this week's work |

Short alias: `dm` works the same as `devmark`

---

## Automation

### Git Hook (auto-logging)

After `devmark init`, commits are automatically logged:

```
[2024-01-15 14:30] commit: "Add user authentication"
[2024-01-15 16:45] commit: "Fix login validation bug"
[2024-01-15 17:00] save: "Done for today, tests passing"
```

Zero effort. Just commit as normal.

---

## Requirements

- Python 3.10+
- [Ollama](https://ollama.ai) (optional, for AI features)

---

## Data

Stored in `~/.devmark/` (SQLite database)

---

## Part of the Vibe Coder Toolkit

Works great with [Fridgprompt](https://github.com/95987-AP/Fridgprompt) - save your prompts, bookmark your projects.

---

## Status

Early Development - Core features being built.

---

## License

MIT

---

*Built for developers who work on too many projects.*
