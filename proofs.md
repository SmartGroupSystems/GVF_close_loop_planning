# Theoretical Proofs

This document provides detailed proofs for the theoretical results presented in  
*"SwordRiding: Unified Navigation Framework for Quadrotors in Unknown Complex Environments via Online Guiding Vector Fields."*

## Lemma 1: Convergence of the Guiding Vector Field

**Statement.**  
Let $\mathcal{P} \subset \mathbb{R}^n$ be a smooth path. Suppose there exists a mapping operator $\Pi$ that assigns to each point $\xi \in \mathcal{P}$ a pair of normalized vectors $(\boldsymbol{t}(\xi),\boldsymbol{n}(\xi))$, where $\boldsymbol{t}(\xi)$ is tangent to $\mathcal{P}$ and $\boldsymbol{n}(\xi)$ is linearly independent of $\boldsymbol{t}(\xi)$. Consider the guiding vector field
\[
\chi(\xi) \;=\; \boldsymbol{t}(\xi) \;+\; k(\xi)\,\boldsymbol{n}(\xi), \qquad k(\xi) > 0.
\]
Under standard smoothness and Lipschitz continuity assumptions on $\Pi$ and $k(\cdot)$, the integral curves of $\chi$ asymptotically converge to $\mathcal{P}$.

**Proof.**  
We outline a standard Lyapunov argument using the (signed) Euclidean distance to $\mathcal{P}$.  
Let $U_\rho$ be a tubular neighborhood of $\mathcal{P}$ such that for any $x \in U_\rho$ the closest-point projection $\Pi(x) \in \mathcal{P}$ is uniquely defined and smooth (this holds for a $C^2$ embedded curve for sufficiently small $\rho$). Define the distance function
\[
d(x) \;=\; \operatorname{dist}(x,\mathcal{P}), \qquad x \in U_\rho,
\]
which is $C^1$ on $U_\rho \setminus \mathcal{P}$, with $\nabla d(x)$ orthogonal to the tangent space $T_{\Pi(x)}\mathcal{P}$ and $\|\nabla d(x)\|=1$ almost everywhere. Extend the field off the path by composing the geometric primitives at the projected point:
\[
\boldsymbol{t}(x) \;:=\; \boldsymbol{t}(\Pi(x)), 
\quad
\boldsymbol{n}(x) \;:=\; \boldsymbol{n}(\Pi(x)),
\quad
\chi(x) \;:=\; \boldsymbol{t}(x) \;+\; k(x)\,\boldsymbol{n}(x),
\]
with $k(\cdot)$ locally Lipschitz and $k(x)\ge k_{\min}>0$ on $U_\rho$.

Consider the Lyapunov function $V(x)=\tfrac12 d(x)^2$. Along any trajectory $\dot x=\chi(x)$ starting in $U_\rho$,
\[
\dot V(x) 
= \nabla V(x)^\top \dot x
= d(x)\,\nabla d(x)^\top \big(\boldsymbol{t}(x)+k(x)\,\boldsymbol{n}(x)\big)
= d(x)\,\underbrace{\nabla d(x)^\top \boldsymbol{t}(x)}_{=\,0}
\;+\; d(x)\,k(x)\,\nabla d(x)^\top \boldsymbol{n}(x).
\]
By construction, $\boldsymbol{t}(x)$ is tangent to $\mathcal{P}$ at $\Pi(x)$ while $\nabla d(x)$ is normal to $T_{\Pi(x)}\mathcal{P}$, hence $\nabla d(x)^\top \boldsymbol{t}(x)=0$.  
Choose the orientation of $\boldsymbol{n}$ so that it is aligned with the inward normal; then $\nabla d(x)^\top \boldsymbol{n}(x) \le -c_0$ for some $c_0 \in (0,1]$ in $U_\rho$ (for exact distance, $c_0=1$ almost everywhere). Therefore
\[
\dot V(x) \;\le\; -\,k_{\min}\,c_0\, d(x) \;\le\; 0,
\]
with strict negativity for $x\notin\mathcal{P}$. Hence $V$ is strictly decreasing away from $\mathcal{P}$, implying that trajectories remain in $U_\rho$ and $d(x(t))\to 0$ as $t\to\infty$. Standard LaSalle-type arguments (with local Lipschitz $\chi$ ensuring existence/uniqueness) yield asymptotic convergence of integral curves to $\mathcal{P}$. $\square$

*Notes.* The proof only requires (i) a well-defined closest-point projection $\Pi$ in a tubular neighborhood, (ii) smooth/Lipschitz regularity of the geometric primitives and $k(\cdot)$, and (iii) the orthogonality of $\boldsymbol{t}$ to the normal direction encoded by $\nabla d$. These are satisfied for smooth paths and the construction used in the paper’s GVF synthesis around a discretized trajectory.
