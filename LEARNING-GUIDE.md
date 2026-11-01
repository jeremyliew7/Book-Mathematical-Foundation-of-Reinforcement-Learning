# Learning Guide

## Start and Resume

In this repository, ask an agent to "start studying the mathematical foundations of reinforcement learning" or "continue learning." The agent first reads [learning progress](LEARNING.md), checks the textbook and applicable errata, and teaches interactively in English and Chinese, a small section at a time. At the start, a light assessment of goals and probability and linear-algebra background identifies useful refreshers; it does not automatically skip chapters. On pause, the agent leaves a resumable question and source location.

To find a topic, use the [candidate section index](learning-artifacts/textbook/INDEX.md) or `rl-course-guide`. The index and third-party notes are leads; check pages and formulas against the original book.

## Learning Path

Follow the dependencies in the [table of contents](1%20-%20Table%20of%20contents.pdf) and the actual chapters:

1. [Basic concepts](3%20-%20Chapter%201%20Basic%20Concepts.pdf) → [State values and the Bellman equation](3%20-%20Chapter%202%20State%20Values%20and%20Bellman%20Equation.pdf) → [Optimal state values and the Bellman optimality equation](3%20-%20Chapter%203%20Optimal%20State%20Values%20and%20Bellman%20Optimality%20Equation.pdf).
2. [Value and policy iteration](3%20-%20Chapter%204%20Value%20Iteration%20and%20Policy%20Iteration.pdf) → [Monte Carlo methods](3%20-%20Chapter%205%20Monte%20Carlo%20Methods.pdf) → [Stochastic approximation](3%20-%20Chapter%206%20Stochastic%20Approximation.pdf).
3. [Temporal-difference methods](3%20-%20Chapter%207%20Temporal-Difference%20Methods.pdf) → [Value function methods](3%20-%20Chapter%208%20Value%20Function%20Methods.pdf) → [Policy gradient methods](3%20-%20Chapter%209%20Policy%20Gradient%20Methods.pdf) → [Actor-critic methods](3%20-%20Chapter%2010%20Actor-Critic%20Methods.pdf).

Consult the [appendix](4%20-%20Appendix.pdf), [lecture slides](Lecture%20slides/), and [Grid World code](Code%20for%20grid%20world/) when needed. The book and errata may change, so verify the version and page numbers. Begin with intuition and small examples, then derive as needed. Ask the learner to predict before checking or running an example. By default, present the lesson-end quiz as a group and give feedback after the learner answers; do not reveal answers beforehand. If the learner is stuck, offer graduated hints and check again.

## Collaboration and Artifacts

The lead agent teaches, verifies sources, and maintains the checkpoint. Other agents may independently check formulas, design exercises without leaking answers, or review experiments; the lead agent checks and integrates their results. Subagents do not answer for the learner or write the same file concurrently. Place learning artifacts in `learning-artifacts/` and record the source file, page, and commit. Distinguish hand calculations, unrun code, actual runs, and work independently completed by the learner.

To sync upstream, invoke `rl-upstream-sync` or ask to check and sync the textbook upstream. First inspect the state and changes, then review conflicts and affected learning materials. Pushing requires authorization for the current task.
