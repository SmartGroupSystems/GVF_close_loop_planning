\noindent\textit{Proof.}
By the smoothness of $\mathcal P$ there exists a tubular neighborhood $\mathcal T$ of $\mathcal P$ in which the (metric) projection $\pi:\mathcal T\to \mathcal P$ is well defined and smooth. For $\xi\in\mathcal T$, let
[
d(\xi):=\operatorname{dist}(\xi,\mathcal P)=|\xi-\pi(\xi)|,\qquad
\boldsymbol e(\xi):=\xi-\pi(\xi).
]
Fix the orientation of $\boldsymbol n(\xi)$ so that it points \emph{toward} the path, i.e.
[
\boldsymbol n(\xi):=-\frac{\boldsymbol e(\xi)}{|\boldsymbol e(\xi)|}\quad\text{for }\xi\notin \mathcal P,\qquad
\boldsymbol n(\xi)\ \text{arbitrary with }|\boldsymbol n(\xi)|=1\ \text{for }\xi\in\mathcal P.
]
With this choice, $\boldsymbol n(\xi)\perp \boldsymbol t(\xi)$ and the signed “normal” direction is consistent with moving toward $\mathcal P$. Define the potential
[
\phi(\xi):=\tfrac12 d(\xi)^2.
]
It is standard that $\nabla \phi(\xi)=d(\xi)\nabla d(\xi)$ and, by construction of $\boldsymbol n$,
[
\nabla d(\xi)= -,\boldsymbol n(\xi)\quad\Longrightarrow\quad \nabla\phi(\xi)= -,d(\xi),\boldsymbol n(\xi).
]
Choose a (locally Lipschitz) gain of the form
[
k(\xi)=\alpha(\xi),d(\xi),\qquad \alpha(\xi)>0,
]
which is allowed by the hypothesis “$k(\xi)>0$” and the regularity assumed on $k$. Then the proposed guiding field can be written as
[
\chi(\xi)=\boldsymbol t(\xi)+\alpha(\xi)d(\xi),\boldsymbol n(\xi)
;=; \boldsymbol t(\xi) - \alpha(\xi),\nabla\phi(\xi).
]
This is exactly the guiding vector field structure studied in \cite{yao2018robotic}, namely a tangential component along the path plus a (scaled) negative gradient of a path–centric potential.

To see convergence directly, consider the Lyapunov function $V(\xi)=\phi(\xi)=\tfrac12 d(\xi)^2$. Along trajectories $\dot \xi=\chi(\xi)$ we have, using $\boldsymbol t\perp \boldsymbol n$ and $|\boldsymbol n|=1$,
[
\dot V(\xi);=;\nabla\phi(\xi)\cdot \chi(\xi)
=\big(-d(\xi)\boldsymbol n(\xi)\big)\cdot\big(\boldsymbol t(\xi)+\alpha(\xi)d(\xi)\boldsymbol n(\xi)\big)
=-\alpha(\xi),d(\xi)^2;\le 0,
]
with equality if and only if $d(\xi)=0$, i.e. $\xi\in\mathcal P$. Under the stated smoothness/Lipschitz assumptions on $\Pi$ and $k(\cdot)$, solutions are well-posed and remain in $\mathcal T$; thus $V$ is nonincreasing, bounded below, and LaSalle’s invariance principle implies that every trajectory approaches the largest invariant subset of ${,\xi:\dot V(\xi)=0,}=\mathcal P$, namely $\mathcal P$ itself. Hence the integral curves of $\chi$ asymptotically converge to $\mathcal P$.

Finally, since $\chi(\xi)=\boldsymbol t(\xi)-\alpha(\xi)\nabla\phi(\xi)$ matches the GVF template in \cite{yao2018robotic} (with $\phi=\tfrac12 d^2$), all convergence guarantees therein apply verbatim under the same regularity conditions. This completes the proof. \qed
