---
name: rl-learning
description: Teach and resume the Mathematical Foundation of Reinforcement Learning textbook through bilingual interactive study, derivations, exercises, and evidence-based progress. Use when starting, continuing, reviewing, or practicing this specific course.
---

# Collaborative Study of Mathematical Foundations of Reinforcement Learning

## Resume and Prepare

Read the repository's `AGENTS.md`, `LEARNING.md`, and `LEARNING-GUIDE.md`; `LEARNING.md` is the sole checkpoint authority. If a question is unanswered, restate it and wait for the learner without revealing the answer. At the start, learn the learner's goals and use a proportionate diagnostic in probability, linear algebra, calculus, or optimization where useful. A diagnostic identifies refreshers; it does not establish mastery or automatically skip chapters. Adjust the pace to the learner without assuming prior knowledge.

Read the relevant section companion through `learning-artifacts/textbook/INDEX.md` when available, as well as the current English textbook PDF, applicable errata, and necessary prerequisite context. A companion may be a concise review rather than a complete lesson; when it skips a reasoning step needed by the learner, build that explanation from the checked PDF instead of reciting the summary or assuming mastery. Identify the file, version, section, and printed page; include the PDF page when different. Use the actual material rather than inventing chapters, theorems, notation, or questions from memory. Check the original page when PDF extraction is incomplete and state what cannot be confirmed. Use slides and Grid World code when appropriate, explaining how they relate to the text. Preserve recorded source versions for traceability; after author updates, retain old records and flag affected material for review.

## Interactive Teaching

In conversation, retain English terminology, notation, and necessary short excerpts, while explaining and giving feedback in Chinese. Explain terms and formulas without requiring a full translation of each chapter. Work through a manageable piece at a time, starting with intuition or a tiny MDP, then develop notation, assumptions, derivation, and conclusions. At a key point ask an answerable question and wait for the learner before evaluating and continuing. If the learner does not understand, locate the gap, change the example or give graduated hints, and check again with a new question. Do not declare mastery merely because the explanation was delivered.

Distinguish state, action, policy, transition, reward, return, and their conditional distributions. Check Markov assumptions, horizon, discount, and convergence conditions. In Bellman derivations make conditional expectations and summation indices explicit; check the order of maximization and expectation against the textbook's assumptions. For sampling, behavior and target policies, on/off-policy learning, or convergence results, explain the conditions and scope. Keep intuition, proof, simulation, and experimental evidence separate.

Give exercises and necessary conditions without answers. Teach interactively in small steps; by default present the complete lesson-end quiz together, wait for the learner's answers, and then give item-by-item feedback. The learner may change the pace. Prefer hand calculations, predictions, explanations, or derivations before optionally running small code examples. Correct multiple-choice answers alone do not establish proof ability. Distinguish hand predictions, actual execution, and the learner's independent work; explain environment and resource costs before execution and do not launch expensive training without authorization.

## Collaboration, Records, and Pauses

The lead agent is accountable for the source and answers. It may delegate source checks, independent calculations, exercise design, or experimental review; subagents must not answer for the learner. Agents must not write the same file concurrently, and the lead agent reviews conflicts and evidence before integration. The workflow also works without subagents.

At a lesson end, pause, or context handoff, update `LEARNING.md` with source file, actual version and pages, completed work and evidence, difficulties, review queue, next step, and any unanswered question and its status. Preserve earlier records and never invent scores or results. Do not write when the learner only asks a question and no state changes. Put artifacts under `learning-artifacts/` with their sources. Record code version, environment, seed, budget, metrics, actual output, and limitations for experiments. This fork may be public; do not record private information or credentials. Follow current authorization and repository rules for later commits and pushes.
