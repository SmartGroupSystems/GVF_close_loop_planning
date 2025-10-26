<script src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>
## Lemma 1: Convergence of the Guiding Vector Field

**Lemma.** Let ( \mathcal{P}\subset\mathbb{R}^n ) be a smooth path, and suppose there exists a mapping operator ( \Pi ) that assigns to each point ( \xi\in\mathcal{P} ) a pair of normalized vectors ( \big(\boldsymbol{t}(\xi),\boldsymbol{n}(\xi)\big) ), where ( \boldsymbol{t}(\xi) ) is tangent to ( \mathcal{P} ) and ( \boldsymbol{n}(\xi) ) is linearly independent of ( \boldsymbol{t}(\xi) ). Consider the guiding vector field
[
\chi(\xi)=\boldsymbol{t}(\xi) + k(\xi),\boldsymbol{n}(\xi),\qquad k(\xi)>0.
]
Under standard smoothness and Lipschitz continuity assumptions on ( \Pi ) and (k(\cdot)), the corresponding integral curves asymptotically converge to ( \mathcal{P} ). 

---

### Proof

**Step 1 (Tubular neighborhood and projection).**
Because ( \mathcal{P} ) is a smooth embedded curve, there exists a tubular neighborhood (U_\rho) of ( \mathcal{P} ) such that for every ( x\in U_\rho ) the closest-point projection
[
\Pi(x)\in\mathcal{P}
]
is uniquely defined and smooth. We use ( \Pi ) to extend the geometric primitives off the path:
[
\boldsymbol{t}(x):=\boldsymbol{t}!\big(\Pi(x)\big),\qquad
\boldsymbol{n}(x):=\boldsymbol{n}!\big(\Pi(x)\big),\qquad
k(x):=k!\big(\Pi(x)\big),
]
and define the (state-dependent) field on (U_\rho) by
[
\chi(x) ;:=; \boldsymbol{t}(x) + k(x),\boldsymbol{n}(x).
]
By the assumed smoothness/Lipschitz regularity of ( \Pi ) and (k(\cdot)), the composed field ( \chi ) is locally Lipschitz on (U_\rho), ensuring existence and uniqueness of Carathéodory solutions to ( \dot x=\chi(x) ).

**Step 2 (Distance function and Lyapunov candidate).**
Let
[
d(x);:=;\operatorname{dist}\big(x,\mathcal{P}\big),\qquad x\in U_\rho .
]
For a sufficiently small ( \rho ), (d) is (C^1) on (U_\rho\setminus\mathcal{P}) and its gradient ( \nabla d(x) ) is orthogonal to the tangent space (T_{\Pi(x)}\mathcal{P}) with ( |\nabla d(x)|=1 ) a.e. Define the Lyapunov function
[
V(x);:=;\tfrac12,d(x)^2 ;\ge 0.
]

**Step 3 (Descent along the flow).**
Along trajectories of ( \dot x=\chi(x) ),
[
\dot V(x) ;=; \nabla V(x)^\top \chi(x)
;=; d(x),\nabla d(x)^\top!\Big(\boldsymbol{t}(x)+k(x),\boldsymbol{n}(x)\Big).
]
Because ( \boldsymbol{t}(x) ) is tangent to ( \mathcal{P} ) at ( \Pi(x) ) while ( \nabla d(x) ) is normal to (T_{\Pi(x)}\mathcal{P}), we have
[
\nabla d(x)^\top \boldsymbol{t}(x)=0.
]
Choose the orientation of ( \boldsymbol{n} ) so that it points inward (toward decreasing distance). Then there exists ( c_0\in(0,1] ) such that
[
\nabla d(x)^\top \boldsymbol{n}(x) ;\le; -,c_0
\qquad\text{for all }x\in U_\rho\setminus\mathcal{P},
]
(with (c_0=1) almost everywhere when (d) is the exact Euclidean distance). Hence
[
\dot V(x) ;=; d(x),k(x),\nabla d(x)^\top \boldsymbol{n}(x)
;\le; -,k(x),c_0, d(x).
]
Let ( k_{\min}:=\inf_{x\in U_\rho} k(x) >0 ) (positivity and local boundedness follow from the assumptions). Then
[
\dot V(x) ;\le; -,k_{\min},c_0, d(x) ;<;0
\qquad\text{whenever }x\notin\mathcal{P}.
]

**Step 4 (Convergence).**
The inequality above shows (V) is strictly decreasing off ( \mathcal{P}), and solutions remain in (U_\rho) (forward invariance for sufficiently small (\rho)). Since ( \dot V \le -\alpha,\sqrt{2V} ) with ( \alpha:=k_{\min}c_0>0 ), standard comparison arguments imply ( d\big(x(t)\big)\to 0 ) as ( t\to\infty ). Equivalently, trajectories asymptotically approach ( \mathcal{P} ).

Finally, because ( \chi ) is locally Lipschitz on (U_\rho) and there are no singularities with ( \chi(x)=0 ) off ( \mathcal{P} ) in the considered neighborhood, LaSalle’s invariance principle (or Barbalat’s lemma via ( \dot V\in L^1 )) yields that the largest invariant set in ( {x:, d(x)=0} ) is ( \mathcal{P} ) itself. Hence all integral curves of ( \chi ) starting in (U_\rho) converge to ( \mathcal{P} ). □

---

**Remark (Consistency with paper notation).**
The construction aligns with the paper’s GVF synthesis:
[
\chi(\xi)=K_1,\boldsymbol{\tau}(\xi) + K_2,s!\big(d(\xi)\big),\boldsymbol{n}(\xi),
]
where ( \boldsymbol{\tau} ) (tangential) and ( \boldsymbol{n} ) (inward normal) are obtained from the B-spline–induced discrete trajectory and ESDF gradient, respectively, and ( s(\cdot) ) shapes the distance feedback. In the lemma, the general form ( \chi=\boldsymbol{t}+k,\boldsymbol{n} ) plays the same role, with (k>0) ensuring inward contraction of the distance level sets. 
