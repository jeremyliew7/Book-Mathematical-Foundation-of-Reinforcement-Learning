# Agent Collaboration Rules

This repository is a personal fork of an English textbook. `origin` points to the personal fork and `upstream` to the author's repository. Keep personal additions separate from upstream originals.

## Entry Points and Authority

- Before starting, continuing, or changing the learning plan, read [LEARNING.md](LEARNING.md) and the [learning guide](LEARNING-GUIDE.md), then read `.agents/skills/rl-learning/SKILL.md` for learning tasks. Read the current textbook section and check the applicable errata. Teaching must follow the actual pages, formulas, and assumptions.
- When writing or revising section companions, read the [lesson template](LESSON-TEMPLATE.md) and check each point against the textbook.
- When locating a concept, question, or formula, read `.agents/skills/rl-course-guide/SKILL.md`, search the [candidate section index](learning-artifacts/textbook/INDEX.md), and check the original PDF.
- Before syncing the author's updates, read `.agents/skills/rl-upstream-sync/SKILL.md`. Before Git operations, check the repository, branch, index, working tree, remotes, and concurrent activity. Do not automatically stash, reset, clean, force-push, or overwrite others' work.
- `LEARNING.md` is the sole authority for the course checkpoint and learning evidence. Do not infer mastery from chat history, the Vault handoff, or file timestamps. Save the actual checkpoint when pausing, ending a lesson, or changing agents; ordinary questions need no per-turn file update.
- When launched from ResHub, also follow the Vault root AGENTS. When launched from this independent repository, do not assume permission to write to the Vault. Report any needed handoff when appropriate.

## Collaboration Boundaries

- Teach in a mixture of English and Chinese: retain English terminology and source notation, and explain, derive, and give feedback in Chinese. Quote only short passages when needed with a source and page; do not require a full translation of every chapter by default.
- The learner answers for themselves. Agents may independently check the textbook, derivations, or code; the lead agent reconciles conflicts. Do not simulate learner answers or present plans as completed work. The workflow also works without subagents.
- Use actual responses, hand calculations, derivations, or execution results as evidence; label unverified conclusions. Do not skip chapters or declare mastery from a few diagnostic questions. When paused on an unanswered question, restate it on resume without revealing its answer.
- Preserve upstream books, slides, and code. Put personal notes, exercises, and experiments under `learning-artifacts/`. Do not push private information, credentials, environment files, caches, large generated artifacts, or long copies of the original text to the public fork. The upstream repository declares no license; observe applicable rights and restrictions when citing it.
- The user's authorization to commit and push the initial setup does not authorize future automatic pushes. Commit or push later work only within the current authorization; check scope and privacy first.
