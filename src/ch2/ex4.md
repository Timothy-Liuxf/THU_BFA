# 习题 2.4

给定闭区间 $[a, b]$, 考虑所有次数小于等于 $n$ 的实系数多项式所构成的集合 $X$. 证明: 在通常多项式的加法和多项式与实数的乘法运算下, $X$ 为实线性空间. 求 $X$ 的一个 Hamel 基. 若多项式的系数取复数, 证明: 相应的多项式集合 $Y$ 是复线性空间. $X$ 是 $Y$ 的线性子空间吗?

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**解答**

---

### 1. $X$ 为实线性空间

设 $X = \{ p : [a,b] \to \mathbb{R} \mid p(x)=a_0 + a_1 x + \cdots + a_n x^n,\ a_i\in\mathbb{R} \}$，即所有次数不超过 $n$ 的实系数多项式构成的集合。在通常的多项式加法与实数数乘下：
- 加法：$(p+q)(x) = p(x)+q(x)$，
- 数乘：$(\lambda p)(x) = \lambda p(x),\ \lambda\in\mathbb{R}$。

验证线性空间的公理：

* **封闭性**：对任意 $p,q\in X$，设 $p(x)=\sum_{k=0}^n a_k x^k,\ q(x)=\sum_{k=0}^n b_k x^k$，则 $(p+q)(x)=\sum_{k=0}^n (a_k+b_k)x^k$，系数 $a_k+b_k\in\mathbb{R}$，且次数不超过 $n$，故 $p+q\in X$。对任意 $\lambda\in\mathbb{R}$，$(\lambda p)(x)=\sum_{k=0}^n (\lambda a_k)x^k$，系数 $\lambda a_k\in\mathbb{R}$，次数不变，故 $\lambda p\in X$。

* **加法结合律、交换律**：多项式的加法满足结合律与交换律，因此成立。

* **零元**：零多项式 $0(x)=0$（系数全为零）属于 $X$，且对任意 $p\in X$ 有 $p+0=p$。

* **负元**：对任意 $p(x)=\sum_{k=0}^n a_k x^k$，取 $-p(x)=\sum_{k=0}^n (-a_k)x^k\in X$，满足 $p+(-p)=0$。

* **数乘结合律**：$\alpha(\beta p)=(\alpha\beta)p$ 由实数乘法结合律保证。

* **数乘单位元**：$1\cdot p = p$。

* **分配律**：$\lambda(p+q)=\lambda p+\lambda q$，$(\lambda+\mu)p=\lambda p+\mu p$，由多项式运算性质直接得到。

所有公理成立，因此 $X$ 是一个实线性空间。

---

### 2. $X$ 的一个 Hamel 基

取向量组 $\{1, x, x^2, \dots, x^n\}$。  
* **线性无关性**：若 $\sum_{k=0}^n c_k x^k = 0$（恒为零多项式），则所有系数 $c_k = 0$。  
* **张成空间**：任意 $p\in X$ 可写为 $p(x)=\sum_{k=0}^n a_k x^k$，即被该组线性表出。  

故 $\{1, x, x^2, \dots, x^n\}$ 构成 $X$ 的一组 Hamel 基。空间 $X$ 的维数为 $n+1$。

---

### 3. $Y$ 为复线性空间

设 $Y = \{ p : [a,b] \to \mathbb{C} \mid p(x)=b_0 + b_1 x + \cdots + b_n x^n,\ b_i\in\mathbb{C} \}$，即次数不超过 $n$ 的复系数多项式集合。加法与数乘的定义同上，但数乘的标量取自 $\mathbb{C}$。  

封闭性：系数之和、复数倍仍为复数，故 $p+q\in Y$，$\lambda p\in Y$。线性空间的其他公理与实数情形完全相同，因为复数集 $\mathbb{C}$ 也是一个域，且多项式运算满足相应性质。因此 $Y$ 是一个复线性空间。

---

### 4. $X$ 是否为 $Y$ 的线性子空间？

$X\subset Y$（实系数多项式可视为系数虚部为零的复系数多项式）。然而，$Y$ 是复线性空间，其数乘标量域为 $\mathbb{C}$。要成为 $Y$ 的（复）线性子空间，$X$ 必须对复数数乘封闭，即  
$$
\forall \lambda\in\mathbb{C},\ \forall p\in X,\quad \lambda p \in X.
$$  
取 $\lambda = i$（虚数单位），$p(x)=1\in X$，则 $(i\cdot1)(x)=i$，其系数为虚数，故 $i\notin X$。因此 $X$ 对复数数乘不封闭，从而 $X$ **不是** $Y$ 的线性子空间。

---

**注**：若将 $Y$ 视为实线性空间（限制数乘于实数），则 $X$ 是 $Y$ 的一个实线性子空间，但原题中 $Y$ 定义为复线性空间，故按通常意义不成立。
