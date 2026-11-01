---
type: textbook-section
tags: [reinforcement-learning, textbook-section]
created: 2026-10-31
section: "D"
title: "Preliminaries for Gradient Descent"
source_file: "4 - Appendix.pdf"
source_commit: "60f6c1a56ddd2e3a823dddf0d831f9fd1518c8bd"
source_sha256: "46438b9eb8b866b308d6790fcaa5bb2edb0b8b6bddd38ef424bfc1299e4f86d3"
pdf_pages: "23-26"
book_pages: "259-262"
verification: "Text extracted from appendix pages 23-26; strong-convexity description and descent inequality were visually checked on pages 24 and 26. The full proof was not independently verified; a counterexample to the stated variable-step conclusion is included."
---

# Appendix D Preliminaries for Gradient Descent

[Source: Appendix D, printed pages 259–262](../../../4%20-%20Appendix.pdf#page=23). The same descent idea reappears with noisy gradients in stochastic approximation. Here the gradient is exact and the optimization is unconstrained.

## A step changes both position and objective

Suppose the objective is $f(x)=x^2/2$, minimized at $x^*=0$. Its derivative is $f'(x)=x$. From $x_0=4$, gradient descent with fixed step size $\alpha=1/2$ gives

$$
x_{k+1}=x_k-\alpha f'(x_k)=\tfrac12x_k.
$$

Thus $x_1=2$, $x_2=1$ and $f(x_0)=8$, $f(x_1)=2$, $f(x_2)=1/2$. Each step moves halfway toward 0. With $\alpha=3/2$, the update is $x_{k+1}=-x_k/2$: it overshoots the minimizer on each step but its distance still halves. With $\alpha=2.1$, the factor becomes $-1.1$, so the magnitude grows. The direction is locally downhill, but the step size determines where the update lands.

In several dimensions, with $x\in\mathbb R^n$ and learning rate $\alpha_k>0$, the update is

$$
x_{k+1}=x_k-\alpha_k\nabla f(x_k).
$$

The gradient $\nabla f(x_k)$ contains the partial derivatives at the current point; $-\nabla f(x_k)$ gives the direction of steepest local decrease in the Euclidean norm. The step length is $\alpha_k\|\nabla f(x_k)\|$.

## Three properties that play different roles

A set is convex if it contains the line segment between any two of its points. On a convex domain, a differentiable convex function lies above its tangent plane:

$$
f(y)\ge f(x)+\nabla f(x)^\top(y-x).
$$

**Strong convexity** adds a uniform quadratic lower bound with $\mu>0$:

$$
f(y)\ge f(x)+\nabla f(x)^\top(y-x)+\tfrac\mu2\|y-x\|^2.
$$

**$L$-smoothness** bounds the change in gradient: $\|\nabla f(y)-\nabla f(x)\|\le L\|y-x\|$. For a twice differentiable function on an open convex domain, the book expresses strong convexity and smooth convexity via $\mu I\preceq\nabla^2 f(x)\preceq LI$. The lower bound controls a minimum curvature, while the upper bound controls the maximum curvature relevant to safe steps.

Strict convexity is weaker than strong convexity. For instance, $f(x)=x^4$ is strictly convex on $\mathbb R$, but $f''(0)=0$, so it has no global positive uniform Hessian lower bound. Printed page 260 uses “strongly convex or strictly convex” for the stronger condition; they should be distinguished.

## Derive the descent bound

For an $L$-smooth function, the descent lemma gives

$$
f(y)\le f(x)+\nabla f(x)^\top(y-x)+\frac L2\|y-x\|^2.
$$

Substitute $y=x_{k+1}$ and $y-x_k=-\alpha_k\nabla f(x_k)$:

$$
\begin{aligned}
f(x_{k+1})
&\le f(x_k)-\alpha_k\|\nabla f(x_k)\|^2
 +\frac{L\alpha_k^2}{2}\|\nabla f(x_k)\|^2\\
&=f(x_k)-\alpha_k\left(1-\frac{L\alpha_k}{2}\right)\|\nabla f(x_k)\|^2.
\end{aligned}
$$

If $0<\alpha_k<2/L$, the coefficient being subtracted is positive. Hence each step is nonincreasing in objective value. For the quadratic example $L=1$, the range is $0<\alpha<2$, matching the three calculated outcomes above.

## From descent to convergence: check the learning-rate schedule

The descent bound alone does not say the limit of the objective equals the minimum. Printed page 262 draws that conclusion under the pointwise condition $0<\alpha_k<2/L$; a variable schedule can satisfy it while spending too little total step length.

Take $f(x)=x^2/2$, $x_1\ne0$, and $\alpha_k=2^{-(k+1)}$ for $k\ge1$. Each $\alpha_k$ is in $(0,2)$, but

$$
x_k=x_1\prod_{j=1}^{k-1}(1-\alpha_j)
\quad\longrightarrow\quad
x_1\prod_{j=1}^{\infty}(1-\alpha_j)\ne0.
$$

The infinite product is positive because the positive step sizes are summable and below 1. The objective decreases to a value above the minimum. In the book's last inference, the product of a step-dependent coefficient and $\|\nabla f(x_k)\|^2$ can go to zero because the coefficient vanishes.

For comparison, suppose $f$ is $\mu$-strongly convex and $L$-smooth on $\mathbb R^n$, and choose a fixed $\alpha\in(0,2/L)$. Strong convexity gives

$$
f(x)-f(x^*)\le\frac{\|\nabla f(x)\|^2}{2\mu}.
$$

One way to see this is to minimize the strong-convexity lower bound over $y$, yielding $f(x^*)\ge f(x)-\|\nabla f(x)\|^2/(2\mu)$. Put $c=\alpha(1-L\alpha/2)>0$ in the descent bound. Then

$$
f(x_{k+1})-f(x^*)\le(1-2\mu c)[f(x_k)-f(x^*)].
$$

Here $0\le1-2\mu c<1$, so objective gaps converge geometrically to zero. Strong convexity then bounds the squared distance to $x^*$ by a constant times the objective gap, giving $x_k\to x^*$. Different variable-step schedules need their own convergence conditions.

## Try it

1. For $f(x)=x^2/2$, calculate two steps from $x_0=4$ using $\alpha=3/2$. Does the objective decrease?
2. Derive the factor multiplying $\|\nabla f(x_k)\|^2$ after inserting the gradient step into the descent lemma.
3. Why does a product $\alpha_k\|\nabla f(x_k)\|^2\to0$ not guarantee that the gradient tends to zero?
4. Compare $x^2$ and $x^4$ near zero: which has a positive global lower Hessian bound, and what does that say about strong convexity?

**Hints:** For 1, use $x_{k+1}=(1-\alpha)x_k$. For 3, consider a coefficient that itself approaches zero.
