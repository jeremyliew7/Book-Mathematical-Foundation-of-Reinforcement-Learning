---
type: textbook-section
tags: [reinforcement-learning, textbook-section]
created: 2026-10-31
section: "A"
title: "Preliminaries for Probability Theory"
source_file: "4 - Appendix.pdf"
source_commit: "60f6c1a56ddd2e3a823dddf0d831f9fd1518c8bd"
source_sha256: "46438b9eb8b866b308d6790fcaa5bb2edb0b8b6bddd38ef424bfc1299e4f86d3"
pdf_pages: "1-5"
book_pages: "237-241"
verification: "Visually inspected Appendix A PDF pages 1–5, including definitions, conditional expectation, gradient-of-expectation and covariance; example and exercises are original. The cited gradient identity requires a fixed distribution and valid interchange."
---

# Appendix A Preliminaries for Probability Theory

[Source: Appendix A, printed pages 237–241](../../../4%20-%20Appendix.pdf#page=1). Use this chapter when a derivation averages over actions, rewards, or next states. Finite sums and elementary differentiation are sufficient for the examples below.

## One transition, several averages

Suppose an agent chooses action $A\in\{L,R\}$ with probabilities $P(L)=0.75$ and $P(R)=0.25$. A reward $X$ is either 0 or 4. Given $L$, the probability of reward 4 is $1/4$; given $R$, it is $3/4$. What reward should the agent expect before knowing its action?

A **random variable** such as $A$ or $X$ describes a quantity before a particular draw; $A=L$ and $X=4$ specify values. The **joint probability** combines both events. Multiplying each conditional probability by the action probability gives:

| Action $A$ | $X=0$ | $X=4$ | Row total |
| --- | ---: | ---: | ---: |
| $L$ | $0.75(0.75)=0.5625$ | $0.75(0.25)=0.1875$ | $0.75$ |
| $R$ | $0.25(0.25)=0.0625$ | $0.25(0.75)=0.1875$ | $0.25$ |
| Column total | $0.625$ | $0.375$ | $1$ |

For example, $P(X=4,A=L)=P(X=4\mid A=L)P(A=L)$. Summing the two entries for $X=4$ gives its **marginal** probability $0.375$. Thus $E[X]=0(0.625)+4(0.375)=1.5$.

There is a second useful route. Given $L$, the conditional mean is $E[X\mid L]=0(0.75)+4(0.25)=1$; given $R$, it is $E[X\mid R]=3$. Average those two numbers by the probability of each action:

$$
E[X]=P(L)E[X\mid L]+P(R)E[X\mid R]=0.75(1)+0.25(3)=1.5.
$$

This is the **law of total expectation**. In general, if $A$ has finitely many values and $X$ is integrable,

$$
E[X]=\sum_a P(A=a)E[X\mid A=a].
$$

Only positive-probability conditioning events are needed. The same logic can first condition on a state, then on an action and a next state; that is the averaging pattern in the Bellman equation.

## Conditional probability and dependence

For $P(A=a)>0$, $P(X=x\mid A=a)=P(X=x,A=a)/P(A=a)$. In the table above, $P(X=4\mid L)=0.25$ differs from $P(X=4)=0.375$, so action and reward are dependent. Independence would require $P(X=x,A=a)=P(X=x)P(A=a)$ for every pair.

Conditional independence asks a different question: after a given condition is known, does additional information change a distribution? The Markov model assumes a suitable conditional independence of the future from the past given the current state; merely placing states consecutively in time does not establish it.

Linearity of expectation needs no independence. From the joint law,

$$
E[X+Y]=\sum_{x,y}(x+y)p(x,y)
=\sum_x x p(x)+\sum_y y p(y)=E[X]+E[Y],
$$

provided the expectations exist. Independence becomes useful for products: if $X,Y$ are independent with finite means, $E[XY]=E[X]E[Y]$.

## Covariance and an instructive zero

For finite second moments, $\operatorname{Cov}(X,Y)=E[XY]-E[X]E[Y]$. Independent variables have zero covariance, but zero covariance alone can hide nonlinear dependence. Let $X$ be equally likely to be $-1,0,1$ and put $Y=X^2$. Then $E[X]=0$, $E[Y]=2/3$, and $E[XY]=E[X^3]=0$, so their covariance is zero. Yet knowing $X=0$ determines $Y=0$: they are dependent.

For random vector $X$ with covariance $\Sigma$ and deterministic matrix $M$, $\operatorname{Cov}(MX)=M\Sigma M^\top$. The transpose ensures the output covariance has the right dimensions.

## Differentiating an expectation

With finite support and a probability law $p(x)$ fixed as $\theta$ changes,

$$
\nabla_\theta E[f(X,\theta)]
=\nabla_\theta\sum_x p(x)f(x,\theta)
=\sum_x p(x)\nabla_\theta f(x,\theta)
=E[\nabla_\theta f(X,\theta)].
$$

When the distribution itself depends on $\theta$, the product rule adds a term:

$$
\nabla_\theta\sum_x p_\theta(x)f(x,\theta)
=\sum_x p_\theta(x)\nabla_\theta f(x,\theta)
+\sum_x f(x,\theta)\nabla_\theta p_\theta(x).
$$

For example, if $X\in\{0,1\}$ with $P_\theta(X=1)=\theta$ and $f(X,\theta)=X$, then $E_\theta[X]=\theta$ has derivative 1, while the derivative of the fixed-value function $f(x,\theta)=x$ is zero. The missing contribution comes from changing probabilities. This distinction matters for policy gradients. Infinite or continuous distributions additionally require conditions that justify interchanging differentiation and expectation.

## Try it

1. From the joint table, compute $P(L\mid X=4)$. Check the numerator and denominator separately.
2. If the reward probabilities given each action stay fixed but $P(R)$ rises, express the new $E[X]$ using conditional means.
3. For the $X,X^2$ example, compare $P(Y=0\mid X=0)$ with $P(Y=0)$.
4. In the Bernoulli example, identify which term of the product-rule derivative carries the change in distribution.

**Hints:** For 1, use the reward-4 column. For 2, the two action probabilities still sum to one. For 3, use the three equally likely values of $X$.
