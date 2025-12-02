# 习题 1.5

设 $(X, d)$ 为度量空间, $M \subset X$ 为非空子集. 若 $x \in X$, 令
$$
\rho(x, M)=\inf_{y \in M} d(x, y).
$$
求证:

1. 任给 $x, y \in X$ 有
$$
|\rho(x, M)-\rho(y, M)| \leq d(x, y) ;
$$

2. $x \in \bar{M}$ 当且仅当 $\rho(x, M)=0$;

3. 若 $M$ 为闭集, 则 $x \notin M$ 当且仅当 $\rho(x, M)>0$.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**证明**

1. 对任意 $x, y \in X$，由下确界的定义，对任意的 $\varepsilon > 0$，存在 $z \in M$ 使得  
   $$
   d(y, z) < \rho(y, M) + \varepsilon.
   $$  
   利用三角不等式有  
   $$
   d(x, z) \le d(x, y) + d(y, z) < d(x, y) + \rho(y, M) + \varepsilon.
   $$  
   因为 $\rho(x, M) = \inf_{w \in M} d(x, w) \le d(x, z)$，故  
   $$
   \rho(x, M) < d(x, y) + \rho(y, M) + \varepsilon.
   $$  
   从而  
   $$
   \rho(x, M) - \rho(y, M) < d(x, y) + \varepsilon.
   $$  
   令 $\varepsilon \to 0^+$ 得 $\rho(x, M) - \rho(y, M) \le d(x, y)$. 交换 $x$ 与 $y$ 的位置可得  
   $$
   \rho(y, M) - \rho(x, M) \le d(x, y).
   $$  
   因此  
   $$
   |\rho(x, M) - \rho(y, M)| \le d(x, y).
   $$

2. **充分性**：若 $\rho(x, M) = 0$，则对任意 $\varepsilon > 0$ 存在 $y \in M$ 使得 $d(x, y) < \varepsilon$，即 $B(x, \varepsilon) \cap M \neq \varnothing$，故 $x$ 是 $M$ 的接触点，$x \in \overline{M}$。  
   **必要性**：若 $x \in \overline{M}$，则对任意 $\varepsilon > 0$ 存在 $y \in M$ 使得 $d(x, y) < \varepsilon$，从而 $\inf_{y \in M} d(x, y) < \varepsilon$. 由 $\varepsilon$ 的任意性知 $\rho(x, M) = 0$。  
   综上，$x \in \overline{M} \iff \rho(x, M) = 0$。

3. 因为 $M$ 是闭集，故 $M = \overline{M}$. 利用 (2) 的结论，  
   $$
   x \notin M \iff x \notin \overline{M} \iff \rho(x, M) \neq 0.
   $$  
   而 $\rho(x, M) = \inf_{y \in M} d(x, y) \ge 0$，所以 $\rho(x, M) \neq 0$ 等价于 $\rho(x, M) > 0$. 因此  
   $$
   x \notin M \iff \rho(x, M) > 0.
   $$
