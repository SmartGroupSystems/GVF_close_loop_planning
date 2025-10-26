## Lemma 1: Convergence of the Guiding Vector Field

**Lemma.** Let $\mathcal{P}\subset\mathbb{R}^n$ be a smooth path, and suppose there exists a mapping operator $\Pi$ that assigns to each point $\xi\in\mathcal{P}$ a pair of normalized vectors $(\boldsymbol{t}(\xi),\boldsymbol{n}(\xi))$, where $\boldsymbol{t}(\xi)$ is tangent to $\mathcal{P}$ and $\boldsymbol{n}(\xi)$ is linearly independent of $\boldsymbol{t}(\xi)$. Consider the guiding vector field:

$$
\chi(\xi) = \boldsymbol{t}(\xi) + k(\xi)\boldsymbol{n}(\xi), \qquad k(\xi) > 0.
$$

Under standard smoothness and Lipschitz continuity assumptions on $\Pi$ and $k(\cdot)$, the corresponding integral curves asymptotically converge to $\mathcal{P}$.

---

### Proof

**Step 1 (Tubular neighborhood and projection).**  
Because $\mathcal{P}$ is a smooth embedded curve, there exists a tubular neighborhood $U_\rho$ of $\mathcal{P}$ such that for every $x\in U_\rho$ the closest-point projection

$$
\Pi(x) \in \mathcal{P}
$$

is uniquely defined and smooth. We use $\Pi$ to extend the geometric primitives off the path:

$$
\boldsymbol{t}(x):=\boldsymbol{t}(\Pi(x)), \quad
\boldsymbol{n}(x):=\boldsymbol{n}(\Pi(x)), \quad
k(x):=k(\Pi(x)),
$$

and define the (state-dependent) field on $U_\rho$ by

$$
\chi(x) := \boldsymbol{t}(x) + k(x)\boldsymbol{n}(x).
$$

By the assumed smoothness/Lipschitz regularity of $\Pi$ and $k(\cdot)$, the composed field $\chi$ is locally Lipschitz on $U_\rho$, ensuring existence and uniqueness of Carathéodory solutions to $\dot x = \chi(x)$.

**Step 2 (Distance function and Lyapunov candidate).**  
Let

$$
d(x) := \mathrm{dist}(x, \mathcal{P}), \quad x \in U_\rho.
$$

For a sufficiently small $\rho$, $d$ is $C^1$ on $U_\rho\setminus\mathcal{P}$ and its gradient $\nabla d(x)$ is orthogonal to the tangent space $T_{\Pi(x)}\mathcal{P}$ with $\|\nabla d(x)\|=1$. Define the Lyapunov function:

$$
V(x) := \tfrac{1}{2} d(x)^2 \ge 0.
$$

**Step 3 (Descent along the flow).**  
Along trajectories of $\dot x=\chi(x)$,

$$
\dot V(x) = \nabla V(x)^\top \chi(x)
= d(x)\,\nabla d(x)^\top(\boldsymbol{t}(x)+k(x)\boldsymbol{n}(x)).
$$

Because $\boldsymbol{t}(x)$ is tangent to $\mathcal{P}$ while $\nabla d(x)$ is normal to $T_{\Pi(x)}\mathcal{P}$, we have

$$
\nabla d(x)^\top \boldsymbol{t}(x)=0.
$$

Choose $\boldsymbol{n}$ pointing inward (toward decreasing distance). Then there exists $c_0\in(0,1]$ such that

$$
\nabla d(x)^\top \boldsymbol{n}(x) \le -c_0, \quad x\in U_\rho\setminus\mathcal{P}.
$$

Hence

$$
\dot V(x) = d(x)k(x)\nabla d(x)^\top \boldsymbol{n}(x)
\le -k(x)c_0 d(x).
$$

Let $k_{\min} := \inf_{x\in U_\rho} k(x) > 0$. Then

$$
\dot V(x) \le -k_{\min} c_0 d(x) < 0, \quad x\notin \mathcal{P}.
$$

**Step 4 (Convergence).**  
Since $\dot V \le -\alpha\sqrt{2V}$ with $\alpha:=k_{\min}c_0>0$, standard comparison arguments imply $d(x(t))\to0$ as $t\to\infty$.  
Hence trajectories asymptotically converge to $\mathcal{P}$. □

---

**Remark.**  
The construction aligns with the paper’s GVF synthesis:

$$
\chi(\xi) = K_1\boldsymbol{\tau}(\xi) + K_2 s(d(\xi))\boldsymbol{n}(\xi),
$$

where $\boldsymbol{\tau}$ (tangent) and $\boldsymbol{n}$ (normal) are obtained from the B-spline–induced discrete trajectory and ESDF gradient, respectively.  
In the lemma, $\chi=\boldsymbol{t}+k\boldsymbol{n}$ plays the same role, with $k>0$ ensuring inward contraction of distance level sets.
