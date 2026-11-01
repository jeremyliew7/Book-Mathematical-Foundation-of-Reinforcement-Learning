---
type: textbook-section
tags: [reinforcement-learning, textbook-section]
created: 2026-10-31
section: "B"
title: "Measure-Theoretic Probability Theory"
source_file: "4 - Appendix.pdf"
source_commit: "60f6c1a56ddd2e3a823dddf0d831f9fd1518c8bd"
source_sha256: "46438b9eb8b866b308d6790fcaa5bb2edb0b8b6bddd38ef424bfc1299e4f86d3"
pdf_pages: "7-13"
book_pages: "243-249"
verification: "Visually inspected Appendix B PDF pages 7–13, including conditional expectation and convergence definitions; identified a source caveat on the CDF continuity-point condition. Examples and exercises are original."
---

# Appendix B Measure-Theoretic Probability Theory

[Source: Appendix B, printed pages 243–249](../../../4%20-%20Appendix.pdf#page=7). Begin with [Appendix A](appendix-a.md) for finite probability and conditional expectation. This chapter explains how information and limits are expressed when outcomes form a larger space.

## Outcomes, events, and observable information

Imagine rolling a fair die once. The sample space is $\Omega=\{1,2,3,4,5,6\}$; one outcome $\omega$ is the actual face. Suppose the observer only learns whether the face exceeds 3. Their available events are

$$
\mathcal F=\{\varnothing,\Omega,\{1,2,3\},\{4,5,6\}\}.
$$

The set $\mathcal F$ is a **sigma-algebra**: it contains $\Omega$, is closed under complements, and is closed under countable unions. Its events encode the questions the observer can answer. The probability measure $P$ assigns those events probabilities; for example, $P(\{4,5,6\})=1/2$.

The indicator $Y(\omega)=\mathbf1_{\{4,5,6\}}(\omega)$ is observable from $\mathcal F$: it is 1 for a face above 3 and 0 otherwise. Moreover,

$$
E[Y]=0P(Y=0)+1P(Y=1)=P(\{4,5,6\})=\tfrac12.
$$

Under this coarse information, the exact face $X(\omega)=\omega$ is not $\mathcal F$-measurable: the event $\{X\le1\}=\{1\}$ is absent from $\mathcal F$. To model knowledge of the exact face, enlarge the sigma-algebra to all subsets of $\Omega$. This concrete contrast explains why a probability model specifies both outcomes and observable events.

## Conditional expectation is an information-based estimate

Now take the full die probability space and let $X$ be the face, $Y=\mathbf1_{\{X>3\}}$. Given $Y=0$, the face is uniformly distributed over $1,2,3$, so $E[X\mid Y=0]=2$. Given $Y=1$, it is uniform over $4,5,6$, so $E[X\mid Y=1]=5$.

Consequently the random variable $E[X\mid Y]$ is 2 when $Y=0$ and 5 when $Y=1$. Before $Y$ is known, it can take either value. Averaging it gives

$$
E[E[X\mid Y]]=\tfrac12(2)+\tfrac12(5)=3.5=E[X].
$$

This is the law of total expectation. A fixed conditional mean need not equal the unconditional mean: here $E[X\mid Y=1]=5$, not $3.5$. On printed page 247, a sentence in the proof can be read as asserting equality for each fixed $y$; the subsequent weighted average gives the correct identity.

More generally, $E[X\mid Y]$ is defined up to equality with probability one, for integrable $X$. It is determined by the information in $Y$. If $g(Y)$ and the relevant products are integrable, $E[Xg(Y)\mid Y]=g(Y)E[X\mid Y]$: once $Y$ is known, its function is known as well.

## What does convergence of random quantities mean?

Let $X_k$ be a sequence of random variables and $X$ a proposed limit. These definitions answer different questions:

- **Almost surely:** the set of outcomes on which $X_k(\omega)\to X(\omega)$ has probability 1. Follow each path through time, then assess the set of successful paths.
- **In probability:** for every $\varepsilon>0$, $P(|X_k-X|>\varepsilon)\to0$. At each time, measure the chance of a noticeable error.
- **In $L^r$**, $r\ge1$: $E[|X_k-X|^r]\to0$, assuming the relevant moments exist. This controls the size of errors as well as their probabilities.
- **In distribution:** $P(X_k\le a)\to P(X\le a)$ at every continuity point $a$ of the limiting cumulative distribution function (CDF).

Almost-sure convergence implies convergence in probability; $L^r$ convergence implies convergence in probability; convergence in probability implies convergence in distribution. These arrows require the usual shared-space setup for the first three notions.

### Why the distinction matters: rare, large errors

Let $X_k=k$ with probability $1/k$ and 0 otherwise, and let $X=0$. For any fixed $\varepsilon>0$, once $k>\varepsilon$,

$$
P(|X_k-X|>\varepsilon)=\frac1k\longrightarrow0,
\qquad E[|X_k-X|]=k\frac1k=1.
$$

Thus $X_k\to0$ in probability, while convergence in $L^1$ fails. The bad outcomes become rarer, but their size compensates exactly. Which outcomes are shared across times affects pathwise convergence, so the one-time distributions alone do not determine almost-sure convergence.

### Why CDF continuity points matter

For deterministic $X_k=1/k$ and $X=0$, the values converge. At $a=0$, however, $P(X_k\le0)=0$ while $P(X\le0)=1$. The limit CDF jumps at 0; convergence in distribution only requires CDF convergence at its continuity points. Printed page 249 states the condition at all real points, which this example shows is too strong.

## Try it

1. With the die information $\mathcal F$ above, is the event “the face is 2” observable? Explain using membership in $\mathcal F$.
2. Calculate $E[\mathbf1_{\{X>3\}}X\mid Y]$ separately for $Y=0$ and $Y=1$.
3. Change the rare error example to $P(X_k=k)=1/k^2$. Determine its probability of error and its expected absolute error.
4. Explain why a CDF jump can cause a mismatch at the jump even when deterministic values converge.

**Hints:** For 2, $\mathbf1_{\{X>3\}}=Y$. For 3, multiply the magnitude by the probability.
