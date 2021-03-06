---
layout: post
title: "Iterative Shrinkage Thresholding Algorithm (ISTA"
author: "Carlos Mendoza"
categories: math
tags: [optimization]
excerpt_separator: <!--more-->
---

## The bottom line

ISTA solves

$$
\begin{equation}
\min\limits_x \lVert Ax - b \rVert_2^2 + \lambda\lVert x \rVert_1,
\end{equation}
$$

by using the following iteration

$$
\begin{equation}
x^{k+1} = S_{\lambda}(x^k - \lambda^k\nabla f(x^*)),
\end{equation}
$$

<!--more-->

where $$S_{\lambda}$$ is the soft thresholding operator, defined as

$$
S_{\lambda}(x) = 
     \begin{cases}
       x-\lambda, &\quad x \ge \lambda\\
       0, &\quad \lvert x \rvert \le \lambda\\ \\
       x+\lambda, &\quad x \le -\lambda.\

     \end{cases}
$$

Note: More details will come later...

## Background

Note: I will write later a litte bit about the mathematical background behind this. For now,
the references I used to understand this:

[S. Boyd and L. Vandenberghe. Subgradients. 2008.][Subgradients]   
[N. Parikh and S. Boyd. Proximal algorithms. 2013.][Proximal algorithms] 


[Subgradients]: https://see.stanford.edu/materials/lsocoee364b/01-subgradients_notes.pdf
[Proximal algorithms]: https://web.stanford.edu/~boyd/papers/pdf/prox_algs.pdf 


<!--
The proximal gradient method solves the following optimization problem:

$$
\begin{equation*}
\min\limits_x f(x) + g(x)
\end{equation*}
$$

by using the following iteration:

$$
x^{k+1} = \mathbf{prox}_{\lambda g}(x^k - \lambda^k\nabla f(x^*))
$$
-->
