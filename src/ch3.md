# 内积空间和 Hilbert 空间

> 以下内容由 DeepSeek v3.2 Speciale 辅助整理

## 内积空间

### 定义（内积）
设 $X$ 为数域 $\mathbb{K}$ ($\mathbb{R}$ 或 $\mathbb{C}$) 上的线性空间，映射 $\langle\cdot, \cdot\rangle: X \times X \to \mathbb{K}$ 称为**内积**，若满足：
1. $\langle x + y, z \rangle = \langle x, z \rangle + \langle y, z \rangle$;
2. $\langle \alpha x, y \rangle = \alpha \langle x, y \rangle$;
3. $\langle x, y \rangle = \overline{\langle y, x \rangle}$;
4. $\langle x, x \rangle \ge 0$;
5. $\langle x, x \rangle = 0 \iff x = 0$.

则称 $(X,\langle\cdot, \cdot\rangle)$ 为**内积空间**。

### 性质
- 关于第二个变量共轭线性：$\langle z, \alpha x+\beta y\rangle = \overline{\alpha}\langle z, x\rangle+\overline{\beta}\langle z, y\rangle$。
- 由内积诱导范数：$\|x\| := \sqrt{\langle x, x \rangle}$ 是 $X$ 上的范数，称为**诱导范数**。

### 定理（Schwarz不等式和三角不等式）
设 $(X,\langle\cdot, \cdot\rangle)$ 是内积空间，则对任意 $x,y \in X$：
1. **Schwarz不等式**：$|\langle x, y\rangle| \le \|x\|\|y\|$，等号成立当且仅当 $x$ 与 $y$ 线性相关。
2. **三角不等式**：$\|x+y\| \le \|x\|+\|y\|$，等号成立当且仅当 $y=0$ 或 $x = c y$ ($c \ge 0$)。

### 定理（平行四边形等式和极化恒等式）
- **平行四边形等式**：$\|x+y\|^2 + \|x-y\|^2 = 2(\|x\|^2 + \|y\|^2)$。
- **极化恒等式**：
  - 若 $\mathbb{K}=\mathbb{R}$：$\langle x, y\rangle = \frac{1}{4}(\|x+y\|^2 - \|x-y\|^2)$；
  - 若 $\mathbb{K}=\mathbb{C}$：$\langle x, y\rangle = \frac{1}{4}(\|x+y\|^2 - \|x-y\|^2) + \frac{i}{4}(\|x+iy\|^2 - \|x-iy\|^2)$。

一个赋范空间 $(X,\|\cdot\|)$ 的范数可由某个内积诱导当且仅当范数满足平行四边形等式。

### 定义（Hilbert空间）
若内积空间 $X$ 在诱导范数下是完备的（即为 Banach 空间），则称 $X$ 为 **Hilbert 空间**。

### 定理（内积的连续性）
设 $X$ 是内积空间，若 $x_n \to x$, $y_n \to y$（在诱导范数下），则 $\langle x_n, y_n \rangle \to \langle x, y \rangle$。

### 定义（等距同构）
设 $X,Y$ 是内积空间，线性映射 $T: X \to Y$ 是**等距同构**，若 $T$ 是一一映射且保持内积：$\langle Tx_1, Tx_2 \rangle_Y = \langle x_1, x_2 \rangle_X$，此时称 $X$ 与 $Y$ 等距同构。

### 定理（内积空间的完备化）
任何内积空间 $X$ 都存在一个 Hilbert 空间 $\hat{X}$ 作为完备化，即存在 $\hat{X}$ 的稠密线性子空间 $Y$ 与 $X$ 等距同构，且 $\hat{X}$ 在等距同构意义下唯一。

---

## 正交补及正交投影

### 定义（正交）
设 $X$ 是内积空间，$x,y \in X$，若 $\langle x, y \rangle = 0$，则称 $x$ 与 $y$ **正交**，记作 $x \perp y$。对于子集 $M,N \subseteq X$，若 $\forall x \in M, y \in N$ 有 $x \perp y$，则称 $M$ 与 $N$ **正交**，记作 $M \perp N$。定义 $M$ 的**正交补**为
$$
M^\perp := \{ x \in X : x \perp M \}.
$$

$M^\perp$ 总是 $X$ 的闭线性子空间。

### 定义（凸集）
$X$ 的子集 $C$ 称为**凸集**，如果对任意 $x,y \in C$ 和 $\lambda \in [0,1]$，有 $\lambda x + (1-\lambda)y \in C$。

### 定理（最佳逼近存在唯一性）
设 $X$ 是内积空间，$M$ 是 $X$ 的非空凸集，且 $M$ 在 $X$ 诱导的度量下完备。则对任意 $x_0 \in X$，存在唯一的 $y_0 \in M$，使得
$$
\rho(x_0, M) = \inf_{y \in M} \|x_0 - y\| = \|x_0 - y_0\|.
$$

特别地，若 $X$ 是 Hilbert 空间，$M$ 是 $X$ 的闭凸集（例如闭线性子空间），则上述结论成立。

### 定理（正交分解定理）
设 $H$ 是 Hilbert 空间，$M$ 是 $H$ 的闭线性子空间。则对任意 $x \in H$，存在唯一的 $y \in M$ 和 $z \in M^\perp$，使得 $x = y + z$。即 $H = M \oplus M^\perp$（直和）。

同时，$y$ 是 $x$ 在 $M$ 上的最佳逼近元：$\|x - y\| = \rho(x, M)$，且 $z = x - y \perp M$。

### 正交投影
设 $H$ 是 Hilbert 空间，$M$ 是 $H$ 的闭子空间。定义映射 $P_M: H \to M$，$P_M(x) = y$，其中 $y$ 是 $x$ 在 $M$ 上的唯一最佳逼近元（正交分解中的分量）。称 $P_M$ 为 $H$ 到 $M$ 上的**正交投影算子**。

性质：
- $P_M$ 是有界线性算子，且 $\|P_M\| \le 1$，当 $M \neq \{0\}$ 时 $\|P_M\| = 1$。
- $P_M^2 = P_M$（幂等）。
- $R(P_M) = M$，$N(P_M) = M^\perp$。
- $(M^\perp)^\perp = M$。
- 若 $M$ 是 $X$ 的非空子集，则 $(\operatorname{span} M)^\perp = M^\perp = (\overline{M})^\perp$。

### 完全集
设 $X$ 是赋范空间，$M \subseteq X$。若 $\overline{\operatorname{span} M} = X$，则称 $M$ 为 $X$ 的**完全集**（即其线性张成稠密）。

定理：在 Hilbert 空间 $H$ 中，$M$ 为完全集 $\iff M^\perp = \{0\}$。

---

## 标准正交集与标准正交基

### 定义（标准正交集）
设 $X$ 是内积空间，集合 $M \subseteq X$ 称为**标准正交集**，如果满足：
- 对任意 $e \in M$，$\|e\| = 1$；
- 对任意 $e_1, e_2 \in M$，$e_1 \neq e_2$，有 $\langle e_1, e_2 \rangle = 0$。

若 $M$ 可数，则称其为**标准正交序列**；若 $M$ 有限，则称其为**标准正交组**。

标准正交集是线性无关集。

### Bessel 不等式
设 $\{e_n\}_{n=1}^\infty$ 是内积空间 $X$ 中的标准正交序列，则对任意 $x \in X$，
$$
\sum_{n=1}^\infty |\langle x, e_n \rangle|^2 \le \|x\|^2.
$$

### 定义（标准正交基）
设 $H$ 是 Hilbert 空间，$M$ 是 $H$ 的标准正交集。若 $\overline{\operatorname{span} M} = H$，则称 $M$ 为 $H$ 的一个**标准正交基**（或完全的标准正交集）。

### 定理（标准正交基的等价刻画）
设 $H$ 是 Hilbert 空间，$M$ 是 $H$ 的标准正交集，则以下条件等价：
1. $M$ 是 $H$ 的标准正交基；
2. 对任意 $x \in H$，有 $x = \sum_{e \in M} \langle x, e \rangle e$（级数按范数收敛，且至多可数项非零）；
3. 对任意 $x, y \in H$，有 $\langle x, y \rangle = \sum_{e \in M} \langle x, e \rangle \overline{\langle y, e \rangle}$；
4. 对任意 $x \in H$，有 $\|x\|^2 = \sum_{e \in M} |\langle x, e \rangle|^2$（Parseval 等式）。

当 $H$ 可分时，标准正交基至多是可数的。

### Gram-Schmidt 正交化方法
设 $\{x_n\}_{n=1}^\infty$ 是内积空间 $X$ 中的线性无关序列，则存在标准正交序列 $\{e_n\}_{n=1}^\infty$，使得对每个 $n$，
$$
\operatorname{span}\{x_1,\dots,x_n\} = \operatorname{span}\{e_1,\dots,e_n\}.
$$
构造公式：
$$
u_1 = x_1,\quad e_1 = \frac{u_1}{\|u_1\|},
$$
$$
u_n = x_n - \sum_{k=1}^{n-1} \langle x_n, e_k \rangle e_k,\quad e_n = \frac{u_n}{\|u_n\|},\quad n \ge 2.
$$

### 定理（可分 Hilbert 空间的结构）
每个可分的无穷维 Hilbert 空间 $H$ 都与 $\ell^2$ 等距同构。具体地，若 $\{e_n\}$ 是 $H$ 的一个标准正交基，则映射 $T: H \to \ell^2$ 定义为 $T(x) = (\langle x, e_n \rangle)_{n=1}^\infty$ 是一个等距同构。

---

## Hilbert 空间上有界线性泛函的表示

### Riesz 表示定理
设 $H$ 是 Hilbert 空间，$f \in H'$（$H$ 上的有界线性泛函）。则存在唯一的 $y \in H$，使得对任意 $x \in H$，
$$
f(x) = \langle x, y \rangle,
$$
并且 $\|f\| = \|y\|$。

### 共轭双线性泛函
设 $X,Y$ 是 $\mathbb{K}$ 上的线性空间，映射 $h: X \times Y \to \mathbb{K}$ 称为**共轭双线性泛函**，如果：
- 对第一个变量线性：$h(x_1+x_2, y) = h(x_1, y) + h(x_2, y)$，$h(\alpha x, y) = \alpha h(x, y)$；
- 对第二个变量共轭线性：$h(x, y_1+y_2) = h(x, y_1) + h(x, y_2)$，$h(x, \alpha y) = \overline{\alpha} h(x, y)$。

其范数定义为：
$$
\|h\| = \sup_{\substack{x \neq 0\\ y \neq 0}} \frac{|h(x, y)|}{\|x\| \|y\|}.
$$

### 定理（有界共轭双线性泛函的表示）
设 $H_1, H_2$ 是 Hilbert 空间，$h: H_1 \times H_2 \to \mathbb{K}$ 是有界共轭双线性泛函。则存在唯一的 $T \in B(H_1, H_2)$，使得对任意 $x \in H_1, y \in H_2$，
$$
h(x, y) = \langle Tx, y \rangle_{H_2},
$$
并且 $\|T\| = \|h\|$。

### 伴随算子
设 $H_1, H_2$ 是 Hilbert 空间，$T \in B(H_1, H_2)$。存在唯一的算子 $T^* \in B(H_2, H_1)$，称为 $T$ 的**伴随算子**，满足对任意 $x \in H_1, y \in H_2$，
$$
\langle Tx, y \rangle_{H_2} = \langle x, T^* y \rangle_{H_1}.
$$

性质：设 $S, T \in B(H_1, H_2)$，$R \in B(H_2, H_3)$，$\alpha \in \mathbb{K}$，则
1. $(S + T)^* = S^* + T^*$；
2. $(\alpha T)^* = \overline{\alpha} T^*$；
3. $(T^*)^* = T$；
4. $\|T^* T\| = \|T T^*\| = \|T\|^2$；
5. $T^* T = 0 \iff T = 0$；
6. $(R T)^* = T^* R^*$。

另外，正交投影算子 $P_M$ 满足 $P_M^* = P_M$（自伴）且 $P_M^2 = P_M$。
