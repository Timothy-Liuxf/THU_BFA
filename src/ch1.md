# 度量空间

> 以下内容由 DeepSeek v3.2 Speciale 辅助整理

## 1. 度量空间的定义及例子

### 定义（度量）
设 $X$ 为集合，$d: X \times X \to \mathbb{R}$ 是映射。若满足以下四条公理：

1. **非负性**：$\forall x, y \in X, d(x, y) \ge 0$；
2. **非退化性**：$d(x, y) = 0 \iff x = y$；
3. **对称性**：$\forall x, y \in X, d(x, y) = d(y, x)$；
4. **三角不等式**：$\forall x, y, z \in X, d(x, z) \le d(x, y) + d(y, z)$，

则称 $d$ 是 $X$ 上的一个**度量**（或距离），并称序对 $(X, d)$ 为**度量空间**。在不引起混淆时，也简称 $X$ 为度量空间。

若 $Y \subset X$，则 $d$ 限制在 $Y \times Y$ 上也是 $Y$ 上的度量，此时 $(Y, d|_{Y \times Y})$ 称为 $(X, d)$ 的**子空间**。

### 常见例子
- **数集**：$A \subset \mathbb{K}$，$d(x, y)=|x-y|$。
- **$\mathbb{K}^n$ 上的 $p$-度量**：对 $1 \le p < \infty$，$d_p( \boldsymbol{x}, \boldsymbol{y}) = \left( \sum_{i=1}^n |x_i - y_i|^p \right)^{1/p}$；$p= \infty$ 时，$d_ \infty( \boldsymbol{x}, \boldsymbol{y}) = \max_{1 \le i \le n} |x_i - y_i|$。
- **连续函数空间**：$C[a, b]$ 上定义 $d_ \infty(f, g)= \max_{t \in[a, b]}|f(t)-g(t)|$。
- **离散度量空间**：$d(x, y)= \begin{cases}0, & x=y \\ 1, & x \ne y \end{cases}$。
- **数列空间**：
  - $s$：所有数列，$d(x, y)= \sum_{n=1}^ \infty \frac{1}{2^n} \frac{|x_n-y_n|}{1+|x_n-y_n|}$；
  - $\ell^ \infty$：有界数列，$d_ \infty(x, y)= \sup_{n \ge1}|x_n-y_n|$；
  - $\ell^p$（$1 \le p< \infty$）：$p$-阶可和数列，$d_p(x, y)= \left( \sum_{n=1}^ \infty |x_n-y_n|^p \right)^{1/p}$。
- **乘积空间**：$(X_1, d_1), (X_2, d_2)$ 的乘积 $X_1 \times X_2$ 上可定义 $d_ \infty((x_1, x_2), (y_1, y_2))= \max\{d_1(x_1, y_1), d_2(x_2, y_2)\}$。

### Hölder 不等式和 Minkowski 不等式
**定理 1.1 (Hölder 不等式)** 设 $1<p, q< \infty$ 且 $\frac{1}{p}+ \frac{1}{q}=1$，$x=\{x_n\} \in \ell^p$，$y=\{y_n\} \in \ell^q$，则 $\{x_n y_n\} \in \ell^1$ 且
$$
 \sum_{n=1}^ \infty |x_n y_n| \le \left( \sum_{n=1}^ \infty |x_n|^p \right)^{1/p} \left( \sum_{n=1}^ \infty |y_n|^q \right)^{1/q}.
$$
当 $p=1, q= \infty$ 时也有类似不等式：若 $x \in \ell^1, y \in \ell^ \infty$，则
$$
 \sum_{n=1}^ \infty |x_n y_n| \le \left( \sum_{n=1}^ \infty |x_n| \right) \sup_{n \ge1}|y_n|.
$$

**定理 1.2 (Minkowski 不等式)** 设 $1 \le p< \infty$，$x=\{x_n\}, y=\{y_n\} \in \ell^p$，则
$$
 \left( \sum_{n=1}^ \infty |x_n+y_n|^p \right)^{1/p} \le \left( \sum_{n=1}^ \infty |x_n|^p \right)^{1/p} + \left( \sum_{n=1}^ \infty |y_n|^p \right)^{1/p}.
$$
Minkowski 不等式保证了 $d_p$ 满足三角不等式，从而 $( \ell^p, d_p)$ 是度量空间。

### 广义三角不等式
由度量公理可推出：$\forall x_1, x_2, \dots, x_n \in X$，
$$
d(x_1, x_n) \le d(x_1, x_2)+d(x_2, x_3)+ \cdots+d(x_{n-1}, x_n).
$$

## 2. 开集和闭集

设 $(X, d)$ 为度量空间。

### 球
- **开球**：$B(x_0, r) = \{ x \in X \mid d(x, x_0) < r \}$，其中 $x_0 \in X$, $r>0$。
- **闭球**：$\overline{B}(x_0, r) = \{ x \in X \mid d(x, x_0) \le r \}$。
- **球面**：$S(x_0, r) = \{ x \in X \mid d(x, x_0) = r \}$。

### 内点、内部、开集
- **内点**：$x_0 \in U$ 称为 $U \subset X$ 的内点，若存在 $r>0$ 使得 $B(x_0, r) \subset U$。
- **内部**：$U^ \circ = \{ x \in U \mid x \text{ 是 } U \text{ 的内点} \}$ 称为 $U$ 的内部。
- **开集**：若 $U = U^ \circ$，则称 $U$ 是开集。

### 开集的性质
1. $\varnothing$ 和 $X$ 是开集。
2. 任意多个开集的并是开集。
3. 有限多个开集的交是开集。

### 闭集
- **闭集**：$F \subset X$ 称为闭集，如果其补集 $F^c = X \setminus F$ 是开集。

### 闭集的性质
1. $\varnothing$ 和 $X$ 是闭集。
2. 任意多个闭集的交是闭集。
3. 有限多个闭集的并是闭集。

### 聚点、导集、闭包
- **聚点**：$x_0 \in X$ 称为 $A \subset X$ 的**聚点**，如果 $\forall r>0$，有 $(B(x_0, r) \setminus\{x_0\}) \cap A \ne \varnothing$。
- **导集**：$A' = \{ x \in X \mid x \text{ 是 } A \text{ 的聚点} \}$ 称为 $A$ 的导集。
- **闭包**：$\overline{A} = A \cup A'$ 称为 $A$ 的闭包。

**定理 2.1** 设 $(X, d)$ 是度量空间，$M \subset X$，则  
1. $x \in \overline{M}$ 当且仅当存在序列 $\{x_n\} \subset M$ 使得 $x_n \to x$。  
2. $M$ 是闭集当且仅当 $M= \overline{M}$，也当且仅当对于任意收敛序列 $\{x_n\} \subset M$，若 $x_n \to x$，则 $x \in M$。  
3. $\overline{M}$ 是包含 $M$ 的最小闭集。

### 连续映射
设 $(X_1, d_1), (X_2, d_2)$ 是度量空间，映射 $T: X_1 \to X_2$。

- **连续映射**：称 $T$ 在 $x_0 \in X_1$ 处连续，若 $\forall \varepsilon>0, \exists \delta>0$，当 $d_1(x, x_0)< \delta$ 时，有 $d_2(T(x), T(x_0))< \varepsilon$。若 $T$ 在 $X_1$ 上每一点都连续，则称 $T$ 是连续映射。

连续映射的等价刻画：
- $T$ 连续 $\iff$ 对于 $X_2$ 中任意开集 $U$，其原像 $T^{-1}(U)$ 是 $X_1$ 中的开集。
- $T$ 连续 $\iff$ 对于 $X_2$ 中任意闭集 $F$，其原像 $T^{-1}(F)$ 是 $X_1$ 中的闭集。

### 稠密与可分
- **稠密**：$M \subset X$ 称为**稠密**的，如果 $\overline{M}=X$。等价地，$\forall x \in X, \forall \varepsilon>0, \exists y \in M$ 使得 $d(x, y)< \varepsilon$。
- **可分**：$X$ 称为**可分**的，如果存在可数子集 $M \subset X$ 且在 $X$ 中稠密。

**性质**：若 $X$ 可分，则其任意子空间 $Y$（赋予子空间度量）也是可分的。

## 3. 收敛性、完备性及紧性

### 收敛序列
- **收敛**：序列 $\{x_n\} \subset X$ 收敛于 $x \in X$，若 $\lim_{n \to \infty} d(x_n, x)=0$，记作 $x_n \to x$。

收敛与闭包的关系已在定理 2.1 中给出。

### 柯西列与完备性
- **柯西列**：序列 $\{x_n\} \subset X$ 称为柯西列，如果 $\forall \varepsilon>0, \exists N \in \mathbb{N}$，使得当 $m, n \ge N$ 时，有 $d(x_m, x_n)< \varepsilon$。
- **完备**：若 $X$ 中每个柯西列都收敛（收敛到 $X$ 中的点），则称 $(X, d)$ 是完备的度量空间。

**定理 3.1** 设 $(X, d)$ 是完备度量空间，$Y \subset X$，则  
- 若 $(Y, d|_{Y \times Y})$ 完备，则 $Y$ 是 $X$ 中的闭集。  
- 反之，若 $Y$ 是闭集，则 $(Y, d|_{Y \times Y})$ 完备。

### 等价度量
- **等价度量**：设 $d_1$ 和 $d_2$ 是集合 $X$ 上的两个度量。如果存在常数 $c_1, c_2>0$ 使得
  $$ c_1 d_1(x, y) \le d_2(x, y) \le c_2 d_1(x, y), \quad \forall x, y \in X, $$
  则称 $d_1$ 和 $d_2$ 是**等价**的。

等价度量产生相同的开集、闭集、收敛序列和连续映射。

### 紧性
- **紧度量空间**：度量空间 $X$ 称为**紧**的，如果 $X$ 中任意序列都有收敛子列（子列收敛到 $X$ 中的点）。
- **紧集**：$M \subset X$ 称为**紧集**，如果子空间 $(M, d|_{M \times M})$ 是紧的。
- **相对紧集**：$M \subset X$ 称为**相对紧**的，如果 $\overline{M}$ 是紧集（等价地，$M$ 中任意序列都有在 $X$ 中收敛的子列）。

#### $\varepsilon$-网与完全有界性
- **$\varepsilon$-网**：设 $M \subset X$，$N \subset M$。若对任意 $x \in M$，存在 $y \in N$ 使得 $d(x, y)< \varepsilon$，即 $M \subset \bigcup_{y \in N} B(y, \varepsilon)$，则称 $N$ 是 $M$ 的一个 $\varepsilon$-网。
- **完全有界集**：$M \subset X$ 称为**完全有界**的，如果对任意 $\varepsilon>0$，存在 $M$ 的有限 $\varepsilon$-网。

完全有界集必是有界集。

**定理 3.2**（紧集的性质）设 $(X, d)$ 是度量空间。  
1. 若 $M$ 是紧集，则 $M$ 是有界闭集。  
2. 若 $X$ 是紧空间，则 $Y \subset X$ 是紧集当且仅当 $Y$ 是闭集。  
3. $M$ 相对紧 $\iff$ $\overline{M}$ 紧。  
4. $M$ 完全有界 $\iff$ $M$ 中任意序列都有柯西子列。  
5. 若 $M$ 相对紧，则 $M$ 完全有界；反之，若 $X$ 完备且 $M$ 完全有界，则 $M$ 相对紧。  
6. $M$ 是紧集当且仅当 $M$ 完备且完全有界。

### 最佳逼近元
- **最佳逼近元**：设 $M \subset X$，$x_0 \in X$。若存在 $y_0 \in M$ 使得
  $$ d(x_0, y_0) = \rho(x_0, M) := \inf_{y \in M} d(x_0, y), $$
  则称 $y_0$ 为 $x_0$ 在 $M$ 中的**最佳逼近元**。

## 4. Banach 不动点定理及其应用

### 压缩映射
- **压缩映射**：设 $(X, d)$ 是度量空间，映射 $T: X \to X$。若存在常数 $k$ 满足 $0 \le k<1$，使得
  $$ d(T(x), T(y)) \le k\, d(x, y), \quad \forall x, y \in X, $$
  则称 $T$ 是（$X$ 上的）**压缩映射**，$k$ 称为压缩系数。

### Banach 不动点定理（压缩映射原理）
**定理 4.1 (Banach 不动点定理)** 设 $(X, d)$ 是非空完备度量空间，$T: X \to X$ 是压缩映射，则 $T$ 在 $X$ 中存在唯一的不动点，即存在唯一的 $x_0 \in X$ 使得 $T(x_0)=x_0$。而且，对任意初始点 $x \in X$，迭代序列 $\{T^n(x)\}$ 收敛到 $x_0$，其中 $T^n$ 表示 $T$ 的 $n$ 次复合。

**定理 4.2** 设 $(X, d)$ 是非空完备度量空间，$T: X \to X$。若存在正整数 $m \ge 1$ 使得 $T^m$ 是压缩映射，则 $T$ 有唯一的不动点。
