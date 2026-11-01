---
name: rl-upstream-sync
description: Inspect and safely synchronize this reinforcement learning textbook fork with its author upstream, including effects on personal learning materials. Use for requests to check or merge textbook updates.
---

# Sync the Textbook Upstream

Read `AGENTS.md` and `LEARNING.md` first. Check the Git root, current branch, HEAD, fetch and push addresses of `origin` and `upstream`, tracking branch, working tree, index, merge or rebase state, and concurrent activity. Do not alter another session's staging, changes, or stashes; do not automatically stash, reset, clean, switch branches, or force-push. If the state is unsafe or the target is unclear, stop and report the specific obstacle.

Fetch within the current authorization and compare `origin/main`, `upstream/main`, and local history. Inspect incoming upstream commits and their parent-child diffs; do not treat differences between two endpoint trees as the incoming change set. Review affected textbook files, errata, code, and personal learning material; use merge-tree to preflight when useful. A check-only request does not authorize a merge. When syncing is authorized and the state is safe, merge `upstream/main` into the personal main while preserving personal commits. Understand and resolve conflicts individually, preserving upstream originals and personal material rather than silently choosing one side. If intent cannot be determined, retain the conflict and explain it.

Check source files, pages, and versions of notes, exercises, and experiments for drift against the new textbook. Mark affected but unverified material for review; do not rewrite prior learning evidence or scores. Verify remotes, merge results, personal artifacts, and links. Stage only explicit paths for this task and inspect the full staged diff for credentials, private information, and generated artifacts. Commit under repository rules; push only with explicit authorization for the current task, using an ordinary push after checking target and result. Report upstream version, actual changes, validation, conflicts, and outstanding work. Fetching or a running process alone does not mean synchronization is complete.
