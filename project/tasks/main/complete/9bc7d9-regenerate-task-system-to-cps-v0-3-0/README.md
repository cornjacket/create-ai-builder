# Task: regenerate-task-system-to-cps-v0-3-0

| Field       | Value                  |
|-------------|------------------------|
| Task-type   | USER-TASK              |
| Status | complete |
| Epic        | main               |
| Tags        | —               |
| Priority    | MED           |
| Category    | task-tooling           |
| Created     | 2026-11-17            |
| Completed | 2026-11-17 |
| Next-subtask-id | 0002 |

## Goal

Regenerate this repo's own task machinery (`project/tasks/scripts/`, `project/tasks/docs/`)
from the create-project-system **v0.3.0 tag**, and move CLAUDE.md's task commands to the
`--worktree` / `--group-by-worktree` spelling so listings stop printing deprecation warnings.

## Context

The install predates generator version stamping (it came from commit `7845243`). A dry run
on a scratch copy (dev-workspace triage `08c4f6`, 2026-11-17) showed a machinery-only change:

- 9 files change, 1 file is added (`set-field.sh`); task content, `classes.md`, `project/status/`,
  the skill and CLAUDE.md do not change.
- The 7 pipeline overlay files stay (the generator never deletes).
- `list-tasks.sh` output is identical (132 tasks); `bats tests/unit/shell` passes 49/49.

Flags: `--tasks-dir project/tasks --epic main --with-worktrees --with-projects --with-status
--with-worktree-guard --with-skill`. Do **not** pass `--inject-claude-md`: CLAUDE.md has no
`task-system` markers, so the generator would append a duplicate block.

Run the generator from `git archive v0.3.0`, not the create-project-system checkout (it is
`0.4.0-dev`). Keep `classes.md` under its old name — the scripts read it permanently.

## Subtasks

<!-- When a subtask is finished, run complete-task.sh --parent to mark it [x] before moving on. -->
<!-- subtask-list-start -->
- [x] [X-9bc7d9-0000-regenerate-machinery-from-v0-3-0-tag](X-9bc7d9-0000-regenerate-machinery-from-v0-3-0-tag/)
- [x] [X-9bc7d9-0001-update-claude-md-task-commands-to-worktree](X-9bc7d9-0001-update-claude-md-task-commands-to-worktree/)
<!-- subtask-list-end -->

## Notes

_None._
