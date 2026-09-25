# lessons/ — moved to the second brain

**The portable lessons that used to live here are now notes under `vault/resources/` in my
second brain.** Migrated 2026-09-24. Do not add lessons to this folder.

## Why this folder existed, and why it stopped

Lesson 001 defined this as the **cross-project tier**: project repos record *what* was built,
a separate store records *how building with AI works*. That was right, and this folder honoured
it — almost every file in it was genuinely portable, which is exactly why none of it belonged in
a single project repo where nothing else could find it.

The contents were also a **fork**. They were copied from
[`ai-builder-lessons`](https://github.com/cornjacket/ai-builder-lessons) (now archived) and then
diverged: that repo grew a `038-work-log-at-task-granularity`, this copy grew a *different*
`038-agent-gaming-prompt-carve-outs` plus `039` and `040`. Lessons `001`–`037` were verified
byte-identical, so nothing was lost — but two numbering schemes had silently come apart, and the
one lesson that existed only on the remote was invisible from here.

## Where to look now

Search the brain rather than a directory:

```bash
python3 scripts/search_vault.py "<what you are trying to remember>"
```

Numbers were dropped on arrival. A number encodes sequence, which matters in a folder you scroll
and not at all in a store you query by meaning.

## What is still here

`039-externalize-role-instructions.md` — because **it is not a lesson.** It proposes extracting
the ARCHITECT / IMPLEMENTOR / TESTER role instructions out of `orchestrator.py` string literals
into `roles/*.md`. That is unimplemented work about this codebase, so it belongs in
`project/tasks/`, not in a lessons folder and not in the brain. It stays here until it is filed
as a task through the task scripts.

The general shape worth keeping: **a lesson describes something already learned; a proposal
describes something not yet done.** Filing the second as the first is how a backlog item hides
in a knowledge base and never gets built.

## Related, still in this repo

`learning/` holds pipeline-specific technical notes (agent cwd and context isolation, extract
don't delegate, task context ancestry). Those stayed because they only mean something inside this
codebase — they are documentation, not portable lessons.
