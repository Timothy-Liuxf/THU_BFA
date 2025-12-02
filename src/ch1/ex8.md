# 习题 1.8

求下述集合的闭包:
1. $\mathbb{R}$ 中的整数集 $\mathbb{Z}$;
2. $\mathbb{R}$ 中的有理数集 $\mathbb{Q}$;
3. 复平面 C 的单位开圆盘 $D=\{z \in \mathbb{C}:|z|<1\}$.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**解答**

---

### 1. $\mathbb{R}$ 中的整数集 $\mathbb{Z}$ 的闭包

$\mathbb{Z}$ 在 $\mathbb{R}$ 的标准拓扑下是闭集。因为其补集
$$
\mathbb{R}\setminus\mathbb{Z} = \bigcup_{n\in\mathbb{Z}} (n, n+1)
$$
是开区间的并集，故为开集。因此 $\mathbb{Z}$ 本身是闭的，从而闭包 $\overline{\mathbb{Z}} = \mathbb{Z}$。

---

### 2. $\mathbb{R}$ 中的有理数集 $\mathbb{Q}$ 的闭包

有理数集 $\mathbb{Q}$ 在 $\mathbb{R}$ 中稠密：对任意 $x\in\mathbb{R}$ 及任意 $\varepsilon>0$，存在有理数 $q\in\mathbb{Q}$ 使得 $|x-q|<\varepsilon$，即 $x$ 的任意邻域都包含 $\mathbb{Q}$ 中的点。因此 $\mathbb{R}$ 中每一点都是 $\mathbb{Q}$ 的聚点，故 $\overline{\mathbb{Q}} \supseteq \mathbb{R}$。另一方面，$\overline{\mathbb{Q}} \subseteq \mathbb{R}$（闭包是空间的子集），所以 $\overline{\mathbb{Q}} = \mathbb{R}$。

---

### 3. 复平面 $\mathbb{C}$ 的单位开圆盘 $D = \{z\in\mathbb{C}: |z|<1\}$ 的闭包

记闭单位圆盘 $B = \{z\in\mathbb{C}: |z|\le 1\}$。

* **$B$ 是闭集**：因为函数 $f(z)=|z|$ 连续，且 $B = f^{-1}([0,1])$，而 $[0,1]$ 是 $\mathbb{R}$ 中的闭集，故 $B$ 是闭集。
* **$D$ 在 $B$ 中稠密**：对任意 $z_0\in B$，若 $|z_0|<1$，则 $z_0\in D$；若 $|z_0|=1$，取序列 $z_n = \left(1-\frac{1}{n}\right)z_0 \in D$，则 $|z_n| = 1-\frac{1}{n} < 1$ 且 $z_n \to z_0$。因此 $B \subseteq \overline{D}$。
* **$\overline{D} \subseteq B$**：因为 $D \subseteq B$ 且 $B$ 是闭的，所以 $\overline{D} \subseteq B$。

综上，$\overline{D} = B = \{z\in\mathbb{C}: |z|\le 1\}$。

---
