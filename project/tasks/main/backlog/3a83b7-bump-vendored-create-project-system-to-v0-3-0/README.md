# Task: bump-vendored-create-project-system-to-v0-3-0

| Field       | Value                  |
|-------------|------------------------|
| Task-type   | USER-TASK              |
| Status      | backlog             |
| Epic        | main               |
| Tags        | —               |
| Priority    | LOW           |
| Category    | workspace-mgmt           |
| Created     | 2026-11-17            |
| Completed   | —                      |
| Next-subtask-id | 0000               |

## Goal

Bump `vendor/create-project-system/` (used by `target/setup-project.sh` for target repos)
from v0.2.0 to v0.3.0, and update `vendor/create-project-system/PIN` and `vendor/README.md`.

## Context

v0.3.0 adds the generator version stamp (`GENERATOR_VERSION` in `task-config.sh`) and the
status-folder backfill (`new-epic.sh --repair`). The previous bump (commit `a04c075`, task
`15d940-target-setup-uses-generator-for-tasks`) records the procedure: re-vendor
`generate.sh` + `src/`, update PIN (tag, sha, manifest sha256) and the flag contract, then run
the bats suites.

This repo's own install moved to v0.3.0 in `9bc7d9-regenerate-task-system-to-cps-v0-3-0`.
That task did not touch the vendored copy. Check whether v0.3.0 adds a required `VERSION`
file beside `generate.sh` — the vendored copy must include it, or the generator exits.

## Subtasks

<!-- When a subtask is finished, run complete-task.sh --parent to mark it [x] before moving on. -->
<!-- subtask-list-start -->
<!-- subtask-list-end -->

## Notes

_None._
