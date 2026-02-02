# DevMark - Development Notes

## The Problem
Working on 5+ projects a week, losing track of where you left off.

## Core Concept
A bookmark for your development work. Save state when leaving, restore context when returning.

## Key Challenge
**Discipline requirement** - developers won't remember to save. Need automation.

---

## Automation Approaches (Privacy-Respecting)

### Chosen Approaches:
1. **Git hooks** - Auto-log on commit (zero effort)
2. **Inactivity detector** - Gentle prompt after no activity (optional)
3. **Terminal exit hook** - Quick save on exit (optional)

### Rejected:
- Clipboard watching (too invasive, feels like spyware)

---

## MVP Features

1. `devmark init` - Initialize in a project, install git hook
2. `devmark save "message"` - Manual bookmark save
3. `devmark status` - Show current bookmark + recent activity
4. `devmark log` - Full history
5. `devmark ask "question"` - AI query about project

---

## Data Model

```
projects: id, name, path, last_accessed, bookmark_message
entries: id, project_id, timestamp, type (commit|save|todo), content
todos: id, project_id, task, done, priority
```

---

## Implementation Order

1. Storage layer (SQLite)
2. Git hook installation
3. Basic CLI (init, save, status)
4. AI integration
5. Cross-project features (projects, week)

---

## Related Project
- Fridgprompt - Prompt vault for vibe coders
- Both could share automation layer in future
