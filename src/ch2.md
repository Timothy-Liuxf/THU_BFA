# 赋范空间

> 以下内容由 DeepSeek v3.2 Speciale 辅助整理

## 线性空间和维数

**定义（线性空间）**  
设 $X$ 是非空集合，$\mathbb{K}$ 是实数域 $\mathbb{R}$ 或复数域 $\mathbb{C}$。在 $X$ 上定义了加法 $+$ 和数乘 $\cdot$，满足以下公理（$\forall x, y, z \in X, \ \alpha, \beta \in \mathbb{K}$）：
1. $x+y=y+x$；
2. $(x+y)+z=x+(y+z)$；
3. 存在 $0 \in X$ 使得 $x+0=0+x=x$；
4. 存在 $-x \in X$ 使得 $x+(-x)=0$；
5. $\alpha( \beta x)=( \alpha \beta)x$；
6. $1x=x$；
7. $\alpha(x+y)= \alpha x+ \alpha y$；
8. $( \alpha+ \beta)x= \alpha x+ \beta x$。

则称 $X$ 是 $\mathbb{K}$ 上的**线性空间**（或称向量空间）。

**定义（线性子空间）**  
设 $Y$ 是线性空间 $X$ 的子集。如果对任意 $x, y \in Y$ 和 $\alpha, \beta \in \mathbb{K}$ 都有 $\alpha x+ \beta y \in Y$，则称 $Y$ 是 $X$ 的**线性子空间**。

**定义（线性组合与生成子空间）**  
设 $M \subseteq X$ 非空。$M$ 中元素的有限线性组合的全体称为 $M$ 的**生成子空间**，记作 $\operatorname{span}(M)$：
$$
 \operatorname{span}(M)= \Bigl\{ \sum_{i=1}^n \alpha_i x_i:\ n \ge1, \ \alpha_i \in \mathbb{K}, \ x_i \in M \Bigr\}.
$$
它是包含 $M$ 的最小线性子空间。

**定义（线性无关与线性相关）**  
$X$ 中有限个元素 $x_1, \dots, x_n$ 称为**线性无关**，若 $\alpha_1x_1+ \cdots+ \alpha_nx_n=0$ 蕴涵 $\alpha_1= \cdots= \alpha_n=0$。否则称为**线性相关**。无限子集 $M$ 线性无关，如果它的任意有限子集线性无关。

**定义（有限维与无穷维）**  
若存在正整数 $n$ 使得 $X$ 中有 $n$ 个线性无关的向量，但任意 $n+1$ 个向量都线性相关，则称 $X$ 是**有限维**的，$n$ 称为 $X$ 的维数，记作 $\dim X=n$。如果这样的 $n$ 不存在，则称 $X$ 是**无穷维**的，记 $\dim X= \infty$。

**定义（Hamel 基）**  
设 $M$ 是 $X$ 的线性无关子集。如果 $\operatorname{span}(M)=X$，则称 $M$ 是 $X$ 的一个 **Hamel 基**。

**定理（Hamel 基存在性）**  
设 $X$ 是线性空间，$X \neq\{0\}$，$M_0$ 是 $X$ 的任意线性无关子集。则存在 $X$ 的 Hamel 基 $N$，使得 $M_0 \subseteq N$。特别地，任何非零线性空间都有 Hamel 基。

---

## 赋范空间和 Banach 空间

**定义（范数）**  
设 $X$ 是 $\mathbb{K}$ 上的线性空间。函数 $\| \cdot\|:X \to \mathbb{R}$ 称为 $X$ 上的**范数**，如果满足：
1. 非负性：$\|x\| \ge0$，$\forall x \in X$；
2. 非退化性：$\|x\|=0 \iff x=0$；
3. 齐次性：$\| \alpha x\|=| \alpha|\, \|x\|$，$\forall \alpha \in \mathbb{K}, \, x \in X$；
4. 三角不等式：$\|x+y\| \le\|x\|+\|y\|$，$\forall x, y \in X$。

有序对 $(X, \| \cdot\|)$ 称为**赋范空间**。在不引起混淆时，简称 $X$ 为赋范空间。

**诱导度量**  
对赋范空间 $(X, \| \cdot\|)$，定义 $d(x, y)=\|x-y\|$，则 $d$ 是 $X$ 上的度量，称为由范数**诱导的度量**。它具有性质：
- 平移不变性：$d(x+z, y+z)=d(x, y)$；
- 齐次性：$d( \alpha x, \alpha y)=| \alpha|\, d(x, y)$。

**定义（Banach 空间）**  
如果赋范空间 $(X, \| \cdot\|)$ 在诱导度量下是完备度量空间，则称 $X$ 为 **Banach 空间**。

**定义（线性算子）**  
设 $X, Y$ 是 $\mathbb{K}$ 上的线性空间。映射 $T:X \to Y$ 称为**线性算子**，如果
- $T(x+y)=Tx+Ty$，
- $T( \alpha x)= \alpha Tx$，
对所有 $x, y \in X, \alpha \in \mathbb{K}$ 成立。

**定义（等距同构）**  
若线性算子 $T:X \to Y$ 是双射且满足 $\|Tx\|_Y=\|x\|_X$ 对所有 $x \in X$ 成立，则称 $T$ 是**等距同构**，此时称 $X$ 与 $Y$ 等距同构。

**定义（Schauder 基）**  
设 $X$ 是赋范空间。序列 $\{e_n\} \subset X$ 称为 $X$ 的 **Schauder 基**，如果对每个 $x \in X$，存在唯一的标量序列 $\{ \alpha_n\} \subset \mathbb{K}$，使得 $x= \sum_{n=1}^ \infty \alpha_n e_n$（级数按范数收敛）。

---

## 有限维赋范空间

**定义（等价范数）**  
设 $\| \cdot\|_1$ 和 $\| \cdot\|_2$ 是线性空间 $X$ 上的两个范数。如果存在常数 $c_1, c_2>0$，使得
$$
c_1\|x\|_1 \le\|x\|_2 \le c_2\|x\|_1, \qquad \forall x \in X, 
$$
则称 $\| \cdot\|_1$ 与 $\| \cdot\|_2$ **等价**。

**引理（线性无关组的范数下界）**  
设 $X$ 是赋范空间，$x_1, \dots, x_n \in X$ 线性无关。则存在常数 $c>0$，使得对任意 $\alpha_1, \dots, \alpha_n \in \mathbb{K}$，
$$
 \Bigl\| \sum_{i=1}^n \alpha_i x_i \Bigr\| \ge c \sum_{i=1}^n| \alpha_i|.
$$

**定理（有限维空间上范数等价）**  
有限维线性空间上的任意两个范数等价。

**推论（有限维赋范空间的完备性）**  
任何有限维赋范空间都是 Banach 空间。

**推论（有限维子空间的闭性）**  
赋范空间 $X$ 的有限维线性子空间 $Y$ 是 $X$ 的闭子集。

**定理（有限维空间中的紧性）**  
在有限维赋范空间中，子集 $M$ 是紧集当且仅当 $M$ 是有界闭集。

---

## 有界线性算子

**定义（有界线性算子）**  
设 $X, Y$ 是赋范空间，$T:X \to Y$ 是线性算子。如果存在常数 $C \ge0$，使得
$$
\|Tx\|_Y \le C\|x\|_X, \qquad \forall x \in X, 
$$
则称 $T$ 是**有界线性算子**。记 $B(X, Y)$ 为所有从 $X$ 到 $Y$ 的有界线性算子的集合。

**定义（算子范数）**  
对于 $T \in B(X, Y)$，其**算子范数**定义为
$$
\|T\|= \sup_{x \neq0} \frac{\|Tx\|_Y}{\|x\|_X}= \sup_{\|x\|_X \le1}\|Tx\|_Y= \sup_{\|x\|_X=1}\|Tx\|_Y.
$$

**定理（有界性与连续性的等价）**  
设 $X, Y$ 是赋范空间，$T:X \to Y$ 是线性算子。下列陈述等价：
1. $T$ 在 $x=0$ 处连续；
2. $T$ 在某一点连续；
3. $T$ 是连续映射；
4. $T$ 是有界线性算子。

**定理（零空间闭）**  
若 $T \in B(X, Y)$，则零空间 $N(T)=\{x \in X:Tx=0\}$ 是 $X$ 的闭线性子空间。

**定理（有界线性算子空间的完备性）**  
设 $X$ 是赋范空间，$Y$ 是 Banach 空间，则 $B(X, Y)$ 按算子范数构成 Banach 空间。

**定理（延拓定理）**  
设 $X$ 是赋范空间，$Y$ 是 Banach 空间，$X_0 \subseteq X$ 是稠密线性子空间，$T_0 \in B(X_0, Y)$。则存在唯一的 $T \in B(X, Y)$ 使得 $T|_{X_0}=T_0$，并且 $\|T\|=\|T_0\|$。

---

## 有界线性泛函及其表示

**定义（线性泛函）**  
设 $X$ 是 $\mathbb{K}$ 上的线性空间。线性算子 $f:X \to \mathbb{K}$ 称为 $X$ 上的**线性泛函**。

**定义（代数对偶空间）**  
$X$ 上所有线性泛函的集合记作 $X^*$，称为 $X$ 的**代数对偶空间**。

**定义（拓扑对偶空间 / 对偶空间 / 共轭空间）**  
设 $X$ 是赋范空间。$X$ 上所有有界线性泛函的集合 $B(X, \mathbb{K})$ 记作 $X'$，称为 $X$ 的**拓扑对偶空间**（简称**对偶空间**或**共轭空间**）。

### 常见赋范空间的对偶空间（等距同构意义下）

- $( \mathbb{K}^n, \| \cdot\|_2)' \cong( \mathbb{K}^n, \| \cdot\|_2)$；
- $( \mathbb{K}^n, \| \cdot\|_p)' \cong( \mathbb{K}^n, \| \cdot\|_q)$，其中 $1 \le p< \infty$，$\frac1p+ \frac1q=1$；
- $c_0' = \ell^1$（这里 $c_0=\{(x_n) \in \ell^ \infty: \lim x_n=0\}$，范数为 $\| \cdot\|_ \infty$）；
- $( \ell^1)' = \ell^ \infty$；
- 对于 $1<p< \infty$，$( \ell^p)' = \ell^q$，其中 $\frac1p+ \frac1q=1$。

（注：$\cong$ 表示等距同构。）
