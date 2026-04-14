### Lemma: Guiding Vector Field Construction

**Lemma.**
Let $$\mathcal{P} \subset \mathbb{R}^n$$ be a smooth path, and suppose there exists a mapping operator $$\Pi$$ that assigns to each point $$\xi \in \mathcal{P}$$ a pair of normalized vectors $$(\mathbf{t}(\xi), \mathbf{n}(\xi))$$, with $$\mathbf{t}(\xi)$$ tangential to $$\mathcal{P}$$ and $$\mathbf{n}(\xi)$$ linearly independent from $$\mathbf{t}(\xi)$$.
Then one can construct a guiding vector field of the form

$$
\chi(\xi) = \mathbf{t}(\xi) + k(\xi),\mathbf{n}(\xi), \quad k(\xi) > 0,
$$

and under standard smoothness and Lipschitz continuity assumptions on $$\Pi$$ and $$k(\xi)$$, the corresponding integral curves asymptotically converge to $$\mathcal{P}$$.

---

### Proof

By the smoothness of $$\mathcal{P}$$, there exists a tubular neighborhood $$\mathcal{T}$$ of $$\mathcal{P}$$ in which the projection $$\pi:\mathcal{T}\to\mathcal{P}$$ is smooth.
For $$\xi\in\mathcal{T}$$, define

$$
d(\xi) = |\xi - \pi(\xi)|, \quad
\mathbf{e}(\xi) = \xi - \pi(\xi).
$$

Let

$$
\mathbf{n}(\xi) = -\frac{\mathbf{e}(\xi)}{|\mathbf{e}(\xi)|},
$$

so that $$\mathbf{n}(\xi) \perp \mathbf{t}(\xi)$$.
Define the potential function

$$
\phi(\xi) = \tfrac{1}{2} d(\xi)^2.
$$

Then

$$
\nabla \phi(\xi) = -d(\xi),\mathbf{n}(\xi).
$$

Choose a gain

$$
k(\xi) = \alpha(\xi)d(\xi), \quad \alpha(\xi) > 0.
$$

Thus

$$
\chi(\xi) = \mathbf{t}(\xi) + \alpha(\xi)d(\xi)\mathbf{n}(\xi)
= \mathbf{t}(\xi) - \alpha(\xi)\nabla\phi(\xi).
$$

Consider the Lyapunov function

$$
V(\xi) = \phi(\xi) = \tfrac{1}{2} d(\xi)^2.
$$

Along trajectories $$\dot{\xi} = \chi(\xi)$$, we have

$$
\dot{V}(\xi)
= \nabla\phi(\xi) \cdot \chi(\xi)
= (-d(\xi)\mathbf{n}(\xi)) \cdot (\mathbf{t}(\xi) + \alpha(\xi)d(\xi)\mathbf{n}(\xi))
= -\alpha(\xi)d(\xi)^2 \le 0,
$$

with equality only when $$d(\xi) = 0$$, i.e., $$\xi \in \mathcal{P}$$.
By LaSalle’s invariance principle, all trajectories asymptotically converge to $$\mathcal{P}$$.




### Quantitative Properties and Robustness Analysis

We further strengthen the theoretical analysis based on the above Lyapunov framework. 

---

#### **1) Quantitative convergence rate**

In the above proof, we established that

$$
\dot{V}(\xi) = -\alpha(\xi) d(\xi)^2,
$$

where

$$
V(\xi) = \tfrac{1}{2} d(\xi)^2.
$$

This can be rewritten as

$$
\dot{V}(\xi) = -2\alpha(\xi) V(\xi).
$$

Assuming that the gain satisfies

$$
\alpha(\xi) \ge \alpha_{\min} > 0,
$$

we obtain

$$
\dot{V}(\xi) \le -2\alpha_{\min} V(\xi).
$$

By the comparison lemma, it follows that

$$
V(t) \le V(0) e^{-2\alpha_{\min} t},
$$

which further implies

$$
d(t) \le d(0) e^{-\alpha_{\min} t}.
$$

Therefore, the convergence is exponential, with an explicit time constant

$$
\tau = \frac{1}{\alpha_{\min}}.
$$

---

#### **2) Region of attraction and robustness margin**

To analyze robustness, consider a perturbed system

$$
\dot{\xi} = \chi(\xi) + \mathbf{d},
$$

where $\mathbf{d}$ is a bounded disturbance.

Then the Lyapunov derivative becomes

$$
\dot{V} = \nabla \phi \cdot (\chi + \mathbf{d})
= -\alpha d^2 + \nabla \phi \cdot \mathbf{d}.
$$

Using the Cauchy–Schwarz inequality, we obtain

$$
\dot{V} \le -\alpha d^2 + d |\mathbf{d}|.
$$

This can be rewritten as

$$
\dot{V} \le -d(\alpha d - |\mathbf{d}|).
$$

Therefore, as long as

$$
|\mathbf{d}| < \alpha d,
$$

the Lyapunov function decreases.

Moreover, the system is input-to-state stable (ISS) with ultimate bound

$$
d(t) \le \frac{|\mathbf{d}|_{\max}}{\alpha}.
$$

This explicitly characterizes the robustness margin, which is directly determined by the gain parameter $\alpha$.

---

#### **3) Effect of ESDF discretization**

In practice, the gradient is computed from a discretized ESDF. Let

$$
\widehat{\nabla}\phi = \nabla\phi + \boldsymbol{\epsilon},
$$

where $\boldsymbol{\epsilon}$ denotes the discretization error.

Then

$$
\dot{V} = \nabla\phi \cdot \left(\mathbf{t} - \alpha \widehat{\nabla}\phi \right)
= -\alpha |\nabla\phi|^2 - \alpha \nabla\phi \cdot \boldsymbol{\epsilon}.
$$

This introduces a perturbation term analogous to the disturbance case.

If

$$
|\boldsymbol{\epsilon}| \le \epsilon_{\max},
$$

then the system converges to a small invariant set around the path.

Moreover, the quadratic fitting procedure used in our implementation ensures $C^1$ continuity of the gradient field, which prevents discontinuities and preserves stability.

---

#### **4) Replanning-induced field variations**

In our framework, at each replanning step, the initial state of the newly generated trajectory is chosen as a sampled point from the previous trajectory.

Furthermore, we adopt an engineering smoothing strategy: a short segment of the previous trajectory near the starting point is preserved, and the newly generated trajectory is constructed to be continuous with the previous one.

As a result, the induced guiding vector field remains smooth across replanning events, and no abrupt changes are introduced despite trajectory updates.




### Reference

- Yao W., Kapitanyuk Y. A., Cao M. (2018).  
  **Robotic Path Following in 3D Using a Guiding Vector Field.**  
  *Proceedings of the 2018 IEEE Conference on Decision and Control (CDC)*, Miami, USA, pp. 4475–4480.  
  [https://doi.org/10.1109/CDC.2018.8619528](https://doi.org/10.1109/CDC.2018.8619528)
