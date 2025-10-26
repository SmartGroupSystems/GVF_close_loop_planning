# Theoretical Proofs

This document provides detailed proofs for the theoretical results presented in  
*"SwordRiding: Unified Navigation Framework for Quadrotors in Unknown Complex Environments via Online Guiding Vector Fields."*

---

## Lemma 1 — Convergence of the Guiding Vector Field

**Lemma.**  
Let \( \mathcal{P} \subset \mathbb{R}^n \) be a smooth path.  
Suppose there exists a mapping operator \( \Pi \) that assigns to each \( \xi \in \mathcal{P} \)  
a pair of normalized vectors \( (\mathbf{t}(\xi), \mathbf{n}(\xi)) \),  
where \( \mathbf{t}(\xi) \) is tangent to \( \mathcal{P} \) and  
\( \mathbf{n}(\xi) \) is linearly independent from \( \mathbf{t}(\xi) \).  
Then one can construct a guiding vector field
\[
\boldsymbol{\chi}(\xi) = \mathbf{t}(\xi) + k(\xi)\,\mathbf{n}(\xi), \qquad k(\xi) > 0,
\]
such that, under standard smoothness and Lipschitz-continuity assumptions on \( \Pi \) and \( k(\cdot) \),  
the integral curves of \( \dot\xi = \boldsymbol{\chi}(\xi) \) asymptotically converge to \( \mathcal{P} \).

---

## Proof (Adapted from GVF Trajectory Convergence Framework)

### 1 · Reduction to a Standard GVF Form

In our method, the operator \( \Pi \) defines for each point in the environment a tangent–normal pair  
based on the **reference trajectory** and the **Euclidean Signed Distance Field (ESDF)**:
\[
\boldsymbol{\chi}(\xi) = K_1\,\boldsymbol{\tau}(\xi) + K_2\,s\!\big(d(\xi)\big)\,\boldsymbol{n}(\xi),
\]
where

* \( \boldsymbol{\tau}(\xi) \) is the local **unit tangent** obtained from adjacent trajectory points,  
* \( \boldsymbol{n}(\xi) = -\nabla U(\xi)/\|\nabla U(\xi)\| \) is the **inward unit normal** derived from the ESDF \( U \),
* \( d(\xi) = U(\xi) \) is the **distance to the path**, and  
* \( s(\cdot) \) is a smooth **shaping function**, e.g.
  \[
  s(d) = \tanh\!\left(\frac{d}{r}\right),
  \]
  ensuring bounded feedback intensity.

Thus, \( k(\xi) = K_2\,s(d(\xi)) \!>\!0 \) and \( \mathbf{t}(\xi)=\boldsymbol{\tau}(\xi) \),  
which matches the canonical GVF structure \( \boldsymbol{\chi} = \mathbf{t} + k\,\mathbf{n} \).

---

### 2 · Assumptions and Regularity

Let the following hold (as in CDC 2018 Theorem 1):

1. **Smoothness** — \( \mathcal{P} \) is a \( C^2 \) embedded manifold,  
   and the projection \( \Pi:U_\rho\!\to\!\mathcal{P} \) is unique and \( C^1 \) in a tubular neighborhood \( U_\rho \).  
2. **Orthogonality** — \( \nabla d(\xi) \) is orthogonal to \( \mathbf{t}(\Pi(\xi)) \) and \( \|\nabla d(\xi)\| = 1 \).  
3. **Positivity** — \( k(\xi) \ge k_{\min} > 0 \) and \( s(\cdot) \) is monotone increasing.  

Under these, \( \boldsymbol{\chi}(\xi) \) is locally Lipschitz in \( U_\rho \),  
so the system \( \dot\xi = \boldsymbol{\chi}(\xi) \) admits unique integral curves.

---

### 3 · Lyapunov Function for Distance Convergence

Define the **distance function**
\[
d(\xi) := \mathrm{dist}(\xi, \mathcal{P}), \qquad V(\xi) := \tfrac{1}{2}\, d(\xi)^2.
\]

Its time derivative along system trajectories is
\[
\dot V = \nabla V^\top \boldsymbol{\chi}(\xi)
       = d(\xi)\, \nabla d(\xi)^\top \big(\mathbf{t}(\xi) + k(\xi)\mathbf{n}(\xi)\big).
\]
Since \( \nabla d^\top \mathbf{t} = 0 \), only the normal term remains:
\[
\dot V = d(\xi)\,k(\xi)\,\nabla d(\xi)^\top \mathbf{n}(\xi).
\]
By construction, \( \mathbf{n}(\xi) \) points toward decreasing \( d \);  
thus \( \nabla d^\top \mathbf{n} \le -c_0 \) for some \( c_0>0 \), yielding
\[
\dot V \le -\,k_{\min} c_0\, d(\xi) \;<\; 0 \quad \text{for } \xi\notin\mathcal{P}.
\]

---

### 4 · Asymptotic Convergence

Because \( \dot V \le -\alpha \sqrt{2V} \) with \( \alpha = k_{\min}c_0 > 0 \),
integration gives \( d(\xi(t)) \to 0 \) as \( t\to\infty \).
Using LaSalle’s invariance principle, the largest invariant set satisfying \( \dot V = 0 \)
is \( \{\xi : d(\xi)=0\} = \mathcal{P} \).  
Hence, all trajectories starting in \( U_\rho \) asymptotically converge to \( \mathcal{P} \).

---

### 5 · Interpretation for the Proposed Framework

The constructed field combines:

* **Tangential propagation** \( K_1\boldsymbol{\tau}(\xi) \) — drives motion along the reference path;  
* **Normal convergence** \( K_2 s(d)\boldsymbol{n}(\xi) \) — ensures feedback attraction to the path.

Because both directions are computed from the current state through \( U(\xi) \) and \( \Pi(\xi) \),
the controller forms a **closed-loop feedback** system robust to perturbations
(e.g., wind gusts or manual displacements).

Therefore, by the same Lyapunov argument as in the classical GVF convergence proof,
the incremental vector field proposed in this paper ensures
\[
\lim_{t\to\infty} \mathrm{dist}(\xi(t), \mathcal{P}) = 0.
\]
∎

---

*For reference, the convergence analysis parallels the approach in “Convergence of Trajectories” (IEEE CDC 2018, pp. 4475–4478),  
extended here to an operator-based and discretization-compatible guiding vector field built on ESDF geometry.*
