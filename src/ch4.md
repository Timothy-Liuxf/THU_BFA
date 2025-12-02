# 赋范空间中的基本定理

> 以下内容由 DeepSeek v3.2 Speciale 辅助整理

## Hahn-Banach 定理

### 次线性泛函
设 $X$ 为线性空间，函数 $p: X \to \mathbb{R}$ 称为**次线性泛函**，如果满足：
1. $\forall x, y \in X,\ p(x+y) \le p(x)+p(y)$；
2. $\forall x \in X,\ \alpha \ge 0,\ p(\alpha x) = \alpha p(x)$.

### 半范数
设 $X$ 为线性空间，函数 $p: X \to \mathbb{R}$ 称为**半范数**，如果满足：
1. $\forall x \in X,\ p(x) \ge 0$；
2. $\forall x, y \in X,\ p(x+y) \le p(x)+p(y)$；
3. $\forall x \in X,\ \alpha \in \mathbb{K},\ p(\alpha x) = |\alpha| p(x)$.

### 实线性空间上的 Hahn-Banach 定理
设 $X$ 为实线性空间，$p$ 为 $X$ 上的次线性泛函，$Z$ 为 $X$ 的线性子空间，$f \in Z^*$ 满足  
$$
f(x) \le p(x),\quad \forall x \in Z.
$$
则存在 $g \in X^*$ 使得 $g|_Z = f$，且  
$$
g(x) \le p(x),\quad \forall x \in X.
$$

### 复线性泛函的表示
设 $X$ 为复线性空间，$f \in X^*$，记 $f_1 = \operatorname{Re} f$，则 $f_1 \in X_{\mathbb{R}}^*$（$X$ 视为实线性空间）且  
$$
f(x) = f_1(x) - i f_1(i x),\quad \forall x \in X.
$$
反之，给定 $f_1 \in X_{\mathbb{R}}^*$，由上式定义的 $f$ 属于 $X^*$.

### 半范数控制的 Hahn-Banach 定理
设 $X$ 为 $\mathbb{R}$ 或 $\mathbb{C}$ 上的线性空间，$p$ 为 $X$ 上的半范数，$Z$ 为 $X$ 的线性子空间，$f \in Z^*$ 满足  
$$
|f(x)| \le p(x),\quad \forall x \in Z.
$$
则存在 $g \in X^*$ 使得 $g|_Z = f$，且  
$$
|g(x)| \le p(x),\quad \forall x \in X.
$$

### 赋范空间上的保范延拓定理
设 $X$ 为赋范空间，$Z$ 为 $X$ 的线性子空间，$f \in Z'$（$Z$ 上的连续线性泛函）。则存在 $g \in X'$ 使得 $g|_Z = f$，且 $\|g\| = \|f\|$.

### 非零连续线性泛函的存在性
设 $X$ 为赋范空间，$x_0 \in X$，$x_0 \neq 0$. 则存在 $f \in X'$ 使得 $\|f\| = 1$ 且 $f(x_0) = \|x_0\|$.

**推论**  
设 $X$ 为非零赋范空间，$x_0 \in X$，则  
$$
\|x_0\| = \max_{f \in X', f \neq 0} \frac{|f(x_0)|}{\|f\|} = \max_{f \in X', \|f\|\le 1} |f(x_0)|.
$$

### 共轭算子
设 $X, Y$ 为赋范空间，$T \in B(X, Y)$. 定义 $T^*: Y' \to X'$ 为  
$$
T^*(f) = f \circ T,\quad f \in Y'.
$$
则 $T^* \in B(Y', X')$，且 $\|T^*\| = \|T\|$.

### 典范映射与自反空间
定义 $J: X \to X''$ 为  
$$
J(x)(f) = f(x),\quad f \in X'.
$$
$J$ 是线性等距嵌入（$\|J(x)\| = \|x\|$），称为**典范嵌入**. 若 $J$ 是满射，则称 $X$ 为**自反空间**.

### 可分性的传递
设 $X$ 为赋范空间，若 $X'$ 可分，则 $X$ 可分.

---

## 一致有界性定理

### 一致有界性定理（共鸣定理）
设 $X$ 是 Banach 空间，$Y$ 是赋范空间，$(T_i)_{i \in I} \subset B(X, Y)$. 如果对每个 $x \in X$ 有  
$$
\sup_{i \in I} \|T_i(x)\| < \infty,
$$
则  
$$
\sup_{i \in I} \|T_i\| < \infty.
$$

---

## 强收敛与弱收敛

### 强收敛
在赋范空间 $X$ 中，序列 $(x_n)$ **强收敛**于 $x$（记作 $x_n \to x$）是指 $\|x_n - x\| \to 0$.

### 弱收敛
在赋范空间 $X$ 中，序列 $(x_n)$ **弱收敛**于 $x$（记作 $x_n \rightharpoonup x$）是指  
$$
\forall f \in X',\quad f(x_n) \to f(x).
$$

### 弱*收敛
在对偶空间 $X'$ 中，序列 $(f_n)$ **弱*收敛**于 $f$（记作 $f_n \xrightarrow{*} f$）是指  
$$
\forall x \in X,\quad f_n(x) \to f(x).
$$

---

## 开映射定理和闭图像定理

### 开映射
设 $X, Y$ 为拓扑空间，映射 $T: X \to Y$ 称为**开映射**，如果 $X$ 中任意开集 $G$ 的像 $T(G)$ 是 $Y$ 中的开集.

### 开映射定理
设 $X, Y$ 是 Banach 空间，$T \in B(X, Y)$ 为满射，则 $T$ 是开映射. 特别地，若 $T$ 是双射，则 $T^{-1} \in B(Y, X)$.

### 等价范数定理
设 $X$ 是线性空间，$\|\cdot\|_1$ 和 $\|\cdot\|_2$ 是 $X$ 上的两个范数，且 $(X, \|\cdot\|_1)$ 与 $(X, \|\cdot\|_2)$ 都是 Banach 空间. 若存在 $\alpha > 0$ 使得  
$$
\|x\|_1 \le \alpha \|x\|_2,\quad \forall x \in X,
$$
则存在 $\beta > 0$ 使得  
$$
\|x\|_2 \le \beta \|x\|_1,\quad \forall x \in X,
$$
即两个范数等价.

### 闭算子
设 $X, Y$ 为赋范空间，$T: D(T) \to Y$ 为线性算子，定义域 $D(T) \subset X$. 称 $T$ 为**闭算子**，如果其图像  
$$
G_T = \{(x, Tx): x \in D(T)\}
$$
是 $X \times Y$ 中的闭集.

### 闭图像定理
设 $X, Y$ 是 Banach 空间，$D(T) \subset X$ 是闭线性子空间，$T: D(T) \to Y$ 是闭算子，则 $T$ 是有界线性算子（即连续）.

---

## 在逼近论中的应用

（本章最后简要讨论了 Hahn-Banach 定理在逼近论中的若干应用，例如最佳逼近的存在性等.）
