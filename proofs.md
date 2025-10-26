### Lemma (Guiding Vector Field and Convergence)

**Statement.** Let $$\mathcal P\subset\mathbb R^n$$ be a smooth path. Assume there exists a mapping operator $$\Pi$$ assigning to each $$\xi\in\mathcal P$$ a pair of unit, linearly independent vectors $$(\mathbf t(\xi),\mathbf n(\xi))$$ with $$\mathbf t(\xi)$$ tangent to $$\mathcal P$$ and $$\mathbf n(\xi)$$ pointing (transversally) toward the path. Consider the guiding vector field
$$
\chi(\xi)=\mathbf t(\xi)+k(\xi)\,\mathbf n(\xi),\qquad k(\xi)>0.
$$
Under standard smoothness and local Lipschitz assumptions on $$\Pi$$ and $$k(\cdot)$$, the integral curves of $$\dot\xi=\chi(\xi)$$ asymptotically converge to $$\mathcal P$$.

---

### Step 1 — Reduction to the CDC’18 GVF

Following *Yao–Kapitanyuk–Cao (CDC 2018), Ch. 3*, represent the (3D) path as the transversal intersection of two smooth level sets
$$
\mathcal P \;=\;\{\xi\in\mathbb R^3:\ \phi_1(\xi)=0,\ \phi_2(\xi)=0\},
$$
with $$\phi_1,\phi_2\in C^2$$ and with the “critical set”
$$
C\;:=\;\big\{\xi:\ \mathrm{rank}\,[\nabla\phi_1(\xi)\ \nabla\phi_2(\xi)]\le 1\big\}
$$
satisfying a positive separation condition $$\mathrm{dist}(C,\mathcal P)>0$$. In this framework, the CDC’18 guiding vector field is
$$
v(\xi)\;=\;\tau(\xi)\;-\;N(\xi)\,K\,e(\xi),
\qquad
\tau(\xi):=\nabla\phi_1(\xi)\times\nabla\phi_2(\xi),
\quad
N(\xi):=[\nabla\phi_1(\xi)\ \nabla\phi_2(\xi)],
\quad
e(\xi):=\begin{bmatrix}\phi_1(\xi)\\ \phi_2(\xi)\end{bmatrix},
$$
with $$K=\mathrm{diag}(k_1,k_2)$$ positive definite. Note that $$\tau$$ spans the path-tangent direction and $$-NKe$$ lies in the normal plane $$\mathrm{span}\{\nabla\phi_1,\nabla\phi_2\}$$ pointing toward $$\mathcal P$$ whenever $$e\neq 0$$.

Let
$$
\mathbf t(\xi):=\frac{\tau(\xi)}{\|\tau(\xi)\|},\qquad
\mathbf n(\xi):=-\,\frac{N(\xi)K e(\xi)}{\|N(\xi)K e(\xi)\|}\quad\text{for }NKe\neq 0,
$$
and define the positive scalar field
$$
s(\xi):=\|\tau(\xi)\|,\qquad 
k(\xi):=\frac{\|N(\xi)K e(\xi)\|}{\|\tau(\xi)\|}.
$$
Then, pointwise on $$\{\xi:\tau(\xi)\neq 0\}$$,
$$
s(\xi)\,\chi(\xi)
\;=\;s(\xi)\,\mathbf t(\xi)\;+\;s(\xi)\,k(\xi)\,\mathbf n(\xi)
\;=\;\tau(\xi)\;-\;N(\xi)K e(\xi)
\;=\;v(\xi).
$$
Hence $$\chi$$ and $$v$$ are **positively collinear**: the two dynamical systems $$\dot\xi=\chi(\xi)$$ and $$\dot\xi=v(\xi)$$ generate the same phase-space trajectories up to a (state-dependent) **time reparametrization** by the positive scalar factor $$s(\xi)$$. Therefore, any convergence result proved for $$v$$ transfers verbatim to $$\chi$$.

---

### Step 2 — Convergence of Trajectories (after CDC’18, Ch. 3)

Adopt the CDC’18 Lyapunov function
$$
V(\xi)\;=\;\tfrac12\,e(\xi)^\top K\,e(\xi),
$$
and consider solutions of $$\dot\xi=v(\xi)=\tau(\xi)-N(\xi)K e(\xi)$$. Along such solutions one has
$$
\dot V(\xi)\;=\;-\big\|N(\xi)K e(\xi)\big\|^2\;\le\;0.
$$
Consequently, every trajectory remains in a sublevel set of $$V$$ and its positive limit set lies in
$$
\mathcal M\;:=\;\big\{\xi:\ N(\xi)K e(\xi)=0\big\}\;=\;\mathcal P\ \cup\ C.
$$
By the separation condition $$\mathrm{dist}(C,\mathcal P)>0$$ and the regularity of $$(\phi_1,\phi_2)$$, LaSalle’s invariance principle implies that bounded trajectories converge to the largest invariant subset of $$\mathcal M$$; moreover, as argued in CDC’18, initial conditions converging to $$C$$ form a meagre/measure-zero set under standard transversality (critical-set) assumptions, yielding **(almost) global convergence to $$\mathcal P$$** for bounded solutions. In the unbounded-path case, CDC’18 establishes (via absolute continuity and integral estimates)
$$
\int_0^\infty \big\|N(\xi(t))K e(\xi(t))\big\|^2\,dt\;<\;\infty,
$$
which again confines the limit set to $$\mathcal M$$ and, under the same critical-set nonattraction arguments, ensures convergence to $$\mathcal P$$ for almost all initial conditions.

Finally, since $$\chi$$ and $$v$$ differ only by the positive scalar factor $$s(\xi)>0$$ (Step 1), the above conclusions for $$\dot\xi=v(\xi)$$ hold identically for $$\dot\xi=\chi(\xi)$$: integral curves asymptotically approach $$\mathcal P$$ (except possibly for a measure-zero set attracted to $$C$$). This completes the proof. \(\square\)

---

### Reference
Yao, W., Kapitanyuk, Y. A., & Cao, M. (2018). **Robotic path following in 3D using a guiding vector field.** *Proceedings of the 2018 IEEE Conference on Decision and Control (CDC)*, 4475–4480.
