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

## The one that was a proposal, not a lesson

`039-externalize-role-instructions.md` proposed extracting the ARCHITECT / IMPLEMENTOR / TESTER
prompts out of `orchestrator.py` string literals into `roles/*.md`. **It was already
implemented** — see `ai-builder/orchestrator/machines/{builder,doc}/roles/`, which is what lets
one pipeline serve both code generation and documentation generation. So it was neither a lesson
nor a pending task; it was a finished proposal that never got marked finished, and it sat in a
lessons folder describing work that was already done.

TESTER never applied: it is a Python agent class, not a prompted role, so its absence from
`roles/` is correct rather than incomplete.

What the *implementation* taught is now in the brain as
`externalized-prompts-must-be-self-contained` — agents run with a cwd outside the repo, so a
role prompt cannot reference a sibling file and every rule must be inlined. That constraint is
invisible from the proposal and only shows up once you try it.

Two shapes worth keeping from this:

- **A lesson describes something already learned; a proposal describes something not yet done.**
  Filing the second as the first is how a backlog item hides in a knowledge base and never gets
  built — or, as here, gets built and never gets closed.
- **The implementation of an idea usually knows something the idea did not.** Harvest the lesson
  *after* shipping, not from the design.

## Related, still in this repo

`learning/` holds pipeline-specific technical notes (agent cwd and context isolation, extract
don't delegate, task context ancestry). Those stayed because they only mean something inside this
codebase — they are documentation, not portable lessons.
