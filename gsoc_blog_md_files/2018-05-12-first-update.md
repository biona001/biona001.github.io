---
title: "First 2 week update"
date: 2018-05-12
permalink: /posts/2018/05/first-update
---

Hi everyone, two weeks no see.

The past 2 weeks have been the community bonding period of google summer of codes. I have made several updates in the JSOC-standup channel on slack, asked some questions on julia discourse, and wrote some code for my Ph.D advisor. My coding was not directly related to my project, but it helped me understand the codebase of [MendelBase](https://openmendel.github.io/MendelBase.jl/) and [SnpArrays](https://openmendel.github.io/SnpArrays.jl/latest/) much better, so yayyyyy.

Other than that, I probably spent a disproportionate amount of time on my current course [convex optimization](http://www.seas.ucla.edu/~vandenbe/ee236b/ee236b.html). In this respect, I thought I'd share one of the problems I did on my previous homework (hw5, which is 3.11.d in the textbook). It involves a good amount of "tricks" such as cyclic permutation of the trace operator, the Schur complement property, switching beteen vector and scalar forms of spectral decompositions, and an epigraph conversion:

**Problem:**

Let $x \in \mathbb{R}^n$ and $F(x) = F_0 + x_1F_1 + ... + x_nF_n$ with $F_i$ being symmertic $m \times m$ matrices. The domain of $f$ in each subproblem is $dom f = \{x \in \mathbb{R}^n \ | \ F(x) \text{ is positive definite}\}$. Formulate the following minimization problem as a *semi-definite program* (that is, a minimization problem with linear objective function and constraints in the form of linear matrix inequalities):

\begin{align*}
		&\text{minimize} \ \quad f(x) = E(c^TF(x)^{-1}c)
\end{align*}

where $c$ is a random vector with mean $E(c) = \bar{c}$ and covariance $E(c - \bar{c})(c - \bar{c})^T = S.$

**Solution**

Note that covariance matrices are always symmetric, so $S = Q\Lambda Q^T = \sum \lambda_i q_iq_i^T$. Using cyclic permutation of the trace operator, we have
\begin{align*}
	E(c^TF(x)^{-1}c) &= E(tr(c^TF(x)^{-1}c)) = E(tr(F(x)^{-1}cc^T)) = tr(F(x)^{-1}E(cc^T))\\
	&= tr(F(x)^{-1}S) = tr(F(x)^{-1}(\sum_{i=1}^n \lambda_iq_iq_i^T)) = tr(\sum_{i=1}^n \lambda_i F(x)^{-1} q_iq_i^T)\\
	&= \sum_{i=1}^n \lambda_iq_i^T F(x)^{-1} q_i
\end{align*}
Thus we have 
\begin{align*}
	& \begin{cases}
		&\text{minimize} \ \quad   E(c^TF(x)^{-1}c)\\
	\end{cases}
	\iff \begin{cases}
		\text{minimize} \ \quad \sum_{i=1}^n \lambda_iq_i^T F(x)^{-1} q_i  \\
	\end{cases}\\
	\iff &\begin{cases}
		&\text{minimize} \ \quad   \sum_{i=1}^n \lambda_i t\\
		&\text{subject to} \quad t \geq q_i^TF(x)^{-1}q_i
	\end{cases}
	\iff \begin{cases}
		&\text{minimize} \ \quad   \sum_{i=1}^n \lambda_i t\\
		&\text{subject to} \quad \begin{bmatrix}
			F(x) & q_i \\ q_i^T & t
		\end{bmatrix} \text{ is positive definite}
	\end{cases}\\
		\iff &\begin{cases}
		&\text{minimize} \ \quad   \sum_{i=1}^n \lambda_i t\\
		&\text{subject to} \quad 
		\begin{bmatrix}
			F_0 & 0\\
			0 & 0
		\end{bmatrix}	 + ... + x_n \begin{bmatrix}
			F_n & 0\\0 & 0
		\end{bmatrix} + t \begin{bmatrix}
			0 & 0 \\ 0 & 1
		\end{bmatrix} + \begin{bmatrix}
			0 & q_i\\ q_i^T & 0
		\end{bmatrix}
	\end{cases} 
\end{align*}
which is of the linear matrix inequality constraints we desire. Note the third if-and-only-if is by the epigraph test ($f(x)$ is a convex function $\iff$ the set $\{(x,t) \ | \ f(x) \leq t\}$ is a convex set), and the second to last if-and-only-if is by the property of Schur complement. This completes the proof. 