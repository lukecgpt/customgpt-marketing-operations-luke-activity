# Luke's Activity Log

Auto-captured daily activity log from Claude Code sessions and periodic background checks.

## Structure

```
activity-log/
  YYYY-MM-DD.csv   — one file per day
```

Each CSV row:

| Column | Description |
|--------|-------------|
| date | Date (YYYY-MM-DD) |
| time | Time of capture (HH:MM) |
| summary | High-level one-sentence description of activity |
| source | `stop_hook` (end of Claude session) or `task_scheduler` (background check) |

## How It Works

1. **Stop hook** — fires automatically when a Claude Code session ends. Captures bash history, git commits, running apps, and recent file changes. Summarizes via Claude Haiku.
2. **Windows Task Scheduler** — runs every 2 hours in the background to capture activity even when Claude is not active.

## Log Location

`~/.claude/scripts/log_activity.py`
