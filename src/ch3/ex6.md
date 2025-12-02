# 习题 3.6

设 $X$ 为内积空间, $x \in X, M \subset X$ 为非空子集, 且 $x \perp M$. 求证: $x \perp \overline{\operatorname{span}(M)}$.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**证明**：由于 $x \perp M$，即对任意 $y \in M$ 有 $\langle x, y \rangle = 0$。

首先证明 $x \perp \operatorname{span}(M)$。任取 $v \in \operatorname{span}(M)$，则存在有限个 $y_1,\dots,y_n \in M$ 和标量 $\alpha_1,\dots,\alpha_n \in \mathbb{K}$（$\mathbb{K}$ 为实数域或复数域）使得 $v = \sum_{i=1}^n \alpha_i y_i$。由内积在第二个变量上的线性性可得
$$
\langle x, v \rangle = \Big\langle x, \sum_{i=1}^n \alpha_i y_i \Big\rangle = \sum_{i=1}^n \alpha_i \langle x, y_i \rangle = 0.
$$
故 $x$ 与 $\operatorname{span}(M)$ 中任意向量正交。

其次证明 $x \perp \overline{\operatorname{span}(M)}$。任取 $z \in \overline{\operatorname{span}(M)}$，则存在序列 $\{z_n\} \subset \operatorname{span}(M)$ 使得 $\lim_{n\to\infty} z_n = z$。对每个 $n$ 有 $\langle x, z_n \rangle = 0$。由内积的连续性（或直接由 Cauchy–Schwarz 不等式）
$$
|\langle x, z_n \rangle - \langle x, z \rangle| = |\langle x, z_n - z \rangle| \le \|x\|\,\|z_n - z\| \to 0 \quad (n\to\infty),
$$
所以 $\langle x, z \rangle = \lim_{n\to\infty} \langle x, z_n \rangle = 0$。因此 $x \perp z$。

综上，$x \perp \overline{\operatorname{span}(M)}$。
