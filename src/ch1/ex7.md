# 习题 1.7

设 $M$ 为度量空间 $(X, d)$ 的子集, 求证: $x \in X$ 为 $M$ 的聚点当且仅当任取 $\varepsilon>0$, 开球 $B(x, r)$ 中总有无穷多个 $M$ 中的点.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**证明**： 设 $(X,d)$ 是度量空间，$M\subset X$，$x\in X$.

---

**必要性（$\Rightarrow$）**：假设 $x$ 是 $M$ 的聚点，即对任意 $\varepsilon>0$，有 $(B(x,\varepsilon)\setminus\{x\})\cap M\neq\varnothing$. 任取 $\varepsilon>0$，要证 $B(x,\varepsilon)$ 中含有 $M$ 的无穷多个点. 用反证法.

假设 $B(x,\varepsilon)$ 中只含有 $M$ 的有限个点. 记
$$
S = \bigl(B(x,\varepsilon)\cap M\bigr)\setminus\{x\}.
$$
由于 $x$ 是聚点，必有 $S\neq\varnothing$，否则 $(B(x,\varepsilon)\setminus\{x\})\cap M=\varnothing$，矛盾. 同时 $S$ 是有限集. 令
$$
\delta = \min_{p\in S} d(x,p) > 0.
$$
取 $\varepsilon' = \frac{\delta}{2}$，则 $0<\varepsilon'<\delta\le\varepsilon$. 于是 $B(x,\varepsilon')\subset B(x,\varepsilon)$，并且对任意 $p\in S$ 有 $d(x,p)\ge\delta>\varepsilon'$，故 $p\notin B(x,\varepsilon')$. 因此
$$
\bigl(B(x,\varepsilon')\setminus\{x\}\bigr)\cap M = \varnothing,
$$
但这与 $x$ 是 $M$ 的聚点矛盾. 所以假设不成立，即 $B(x,\varepsilon)$ 中含有 $M$ 的无穷多个点.

---

**充分性（$\Leftarrow$）**：若对任意 $\varepsilon>0$，$B(x,\varepsilon)$ 中都含有 $M$ 的无穷多个点，则特别地，$B(x,\varepsilon)\setminus\{x\}$ 中也含有 $M$ 的点（因为无穷多个点不可能全是 $x$），于是
$$
(B(x,\varepsilon)\setminus\{x\})\cap M \neq\varnothing,
$$
从而 $x$ 是 $M$ 的聚点.

---

综上，命题得证.
