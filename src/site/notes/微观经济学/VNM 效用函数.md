---
{"dg-publish":true,"permalink":"/微观经济学/VNM 效用函数/","tags":["金融经济学"],"created":"2024-10-12T10:25:10.000+08:00","updated":"2024-10-12T10:25:10.000+08:00"}
---

**Definition** The utility function $u:\mathcal{G}\to \mathbb{R}$ *has the expected utility property* if, for every $g\in \mathcal{G}$,
$$
u(g)=\sum\limits_{i=1}^{n}p_{i}u(a_{i})
$$
where $(p_{1}a_{1},\dots,p_{n}a_{n})$ is the simple gamble induced by $g$.

**Theorem** **Existence of a VNM Utility Function on $\mathcal{G}$**
Let preference $\succsim$ over gambles in $\mathcal{G}$ satisfy axioms G1 to G6. The there exists a utility function $u:\mathcal{G}\to \mathbb{R}$ representing $\succsim$ on $\mathcal{G}$, such that $u$ has the expected utility property.

**Theorem** **VNM Utility Functions are Unique up to Positive Affine Transformations**
Suppose that the VNM utility function $u(\cdot)$ represents $\succsim$. Then the VNM utility function, $v(\cdot)$, represents those same preferences if and only if for some scalar $\alpha$ and some scalar $\beta>0$,
$$
v(g)=\alpha+\beta u(g)
$$
for all gambles $g$.

