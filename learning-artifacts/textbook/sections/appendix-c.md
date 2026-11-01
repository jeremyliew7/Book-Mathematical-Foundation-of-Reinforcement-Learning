---
type: textbook-section
tags: [reinforcement-learning, textbook-section]
created: 2026-10-31
section: "C"
title: "Convergence of Sequences"
source_file: "4 - Appendix.pdf"
source_commit: "60f6c1a56ddd2e3a823dddf0d831f9fd1518c8bd"
source_sha256: "46438b9eb8b866b308d6790fcaa5bb2edb0b8b6bddd38ef424bfc1299e4f86d3"
pdf_pages: "15-21"
book_pages: "251-257"
verification: "Text extracted from appendix pages 15-21; Theorems C.2 and C.3 were visually checked on pages 17 and 20. Other proofs were not independently verified. A counterexample to the printed statement of Theorem C.3 is included."
---

# Appendix C Convergence of Sequences

[Source: Appendix C, printed pages 251–257](../../../4%20-%20Appendix.pdf#page=15). This chapter connects the modes of stochastic convergence in [Appendix B](appendix-b.md) with conditions one can check in an iterative algorithm. The examples use limits, nonnegative series, and conditional expectation.

## A sequence can converge while moving up and down

Consider $x_k=1+(-1)^k2^{-k}$ for $k\ge1$. The first four values are $0.5,1.25,0.875,1.0625$. This sequence is nonnegative and alternates above and below 1. How can a convergence argument tolerate those increases?

The book's Theorem C.2 gives one answer. For any real $z$, let $z^+=\max(z,0)$ and $z^-=\min(z,0)$. For a nonnegative sequence, if its total positive movement is finite,

$$
\sum_{k=1}^{\infty}(x_{k+1}-x_k)^+<\infty,
$$

then the sequence converges. To see why, split its changes into cumulative rises and falls:

$$
S_k^+=\sum_{i=1}^{k-1}(x_{i+1}-x_i)^+,
\quad
S_k^-=\sum_{i=1}^{k-1}(x_{i+1}-x_i)^-,
\quad x_k=x_1+S_k^++S_k^-.
$$

1. $S_k^+$ is nondecreasing and bounded above by the finite total of all rises, so it converges.
2. $S_k^-$ is nonincreasing. Since $x_k\ge0$, it satisfies $S_k^-\ge-x_1-S_k^+$, giving it a finite lower bound. It also converges.
3. The expression for $x_k$ is a sum of three convergent quantities; therefore $x_k$ converges.

For our example,

$$
(x_{k+1}-x_k)^+\le |x_{k+1}-x_k|\le 2^{-(k+1)}+2^{-k}.
$$

The right-hand side is summable, so the theorem applies. Here the explicit formula also shows the limit is 1; the general criterion guarantees a limit without naming it.

A useful corollary is $x_{k+1}\le x_k+\eta_k$, with $x_k,\eta_k\ge0$ and $\sum_k\eta_k<\infty$: each rise is at most $\eta_k$. By contrast, individual changes approaching zero do not suffice. Harmonic partial sums $h_k=\sum_{i=1}^k1/i$ have $h_{k+1}-h_k=1/(k+1)\to0$ yet diverge.

## Martingales: statements about conditional averages

Let $\mathcal F_k$ represent the information available through time $k$, and let $X_k$ be integrable and determined by that information. The conditional drift is $E[X_{k+1}-X_k\mid\mathcal F_k]$:

| Process | Conditional drift | Consequence for means |
| --- | --- | --- |
| Martingale | $=0$ | $E[X_{k+1}]=E[X_k]$ |
| Submartingale | $\ge0$ | $E[X_{k+1}]\ge E[X_k]$ |
| Supermartingale | $\le0$ | $E[X_{k+1}]\le E[X_k]$ |

The equalities and inequalities for conditional expectations hold almost surely. A filtration is an increasing collection of information sets $\mathcal F_1\subseteq\mathcal F_2\subseteq\cdots$; the realized history generates such information.

**Worked example.** Let $X_0=0$ and $X_{k+1}=X_k+Z_{k+1}$, where each new $Z_{k+1}$ is independent of the past and equals $+1$ or $-1$ with probability $1/2$ each. Then

$$
E[X_{k+1}\mid\mathcal F_k]
=X_k+E[Z_{k+1}\mid\mathcal F_k]
=X_k+\tfrac12(1)+\tfrac12(-1)=X_k.
$$

The position is a martingale even though a particular path moves on every step. Adding a constant $c>0$ to each increment changes the conditional drift to $c$, producing a submartingale.

## The extra condition behind convergence

A process classification does not on its own guarantee a finite pathwise limit. In particular, Theorem C.3 on printed page 256 states that every submartingale or supermartingale converges almost surely to a finite variable. Take the deterministic process $X_k=k$: it is integrable at each $k$, and $E[X_{k+1}\mid\mathcal F_k]=k+1\ge X_k$, so it is a submartingale. Yet $X_k\to+\infty$.

One useful sufficient result is: **a nonnegative supermartingale converges almost surely to a finite random variable**. The nonnegativity and supermartingale conditions both need checking. Other martingale convergence theorems use their own integrability or boundedness conditions.

The book's Theorem C.4 gives a further route for a nonnegative adapted integrable process. With $\Delta_k=X_{k+1}-X_k$ and $A_k=\{E[\Delta_k\mid\mathcal F_k]\ge0\}$, it requires the sum $\sum_k E[\Delta_k\mathbf1_{A_k}]$ to be finite. This controls accumulated *positive conditional drift*, rather than the realized positive increments on each individual path. The cited theorem's proof is beyond this companion.

## Try it

1. Show that $x_k=1+(-1)^k2^{-k}$ is nonnegative and identify its first positive increment.
2. For a nonnegative sequence with $x_{k+1}\le x_k+3^{-k}$, identify a summable upper bound on the positive increments.
3. If the random walk increments take $+1$ with probability $0.6$ and $-1$ with probability $0.4$, compute the conditional drift and classify the process.
4. Why does $X_k=k$ test a claim about *finite* almost-sure convergence even though the process itself is deterministic?

**Hints:** For 2, compare $(x_{k+1}-x_k)^+$ with $3^{-k}$. For 3, compute the expected next increment given the past.
