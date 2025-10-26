好的，以下是完全使用 `$$` 包裹公式的 **GitHub README 可渲染版本**（兼容 MathJax 渲染的 Markdown，建议放在 `README.md` 中直接使用）。
所有公式都统一改成 `$$ ... $$` 形式，避免渲染不全的问题：

---

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

This formulation matches the guiding vector field in [Yao *et al.*, 2018], hence inherits its convergence properties.
∎
