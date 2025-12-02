# 习题 5.5

设 $A: \ell^{\infty} \rightarrow \ell^{\infty}$ 定义为
$$
A\left(x_1, x_2, x_3, \cdots\right)=\left(x_2, x_3, x_4, \cdots\right).
$$
求证:

(1) 若 $|\lambda|>1$, 则 $\lambda \in \rho(A)$;

(2) 若 $|\lambda| \leq 1$, 则 $\lambda \in \sigma_{p}(A)$, 此时求出相应的特征空间.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**解.**
设 $A:\ell^{\infty}\to\ell^{\infty}$ 为左平移算子，即
$$
A(x_1,x_2,x_3,\dots)=(x_2,x_3,x_4,\dots).
$$
容易验证 $A$ 是线性算子且 $\|A\|=1$（取 $x=(0,1,0,0,\dots)$ 可得 $\|Ax\|_\infty=1=\|x\|_\infty$，而对任意 $x$ 有 $\|Ax\|_\infty\le\|x\|_\infty$）。

---

**(1)** 设 $|\lambda|>1$，证明 $\lambda\in\rho(A)$（预解集）。

**第一步：证明 $\lambda I-A$ 是单射。**  
若 $(\lambda I-A)x=0$，则 $\lambda x_n-x_{n+1}=0$ 对一切 $n\ge1$ 成立，即 $x_{n+1}=\lambda x_n$。递推得 $x_n=\lambda^{n-1}x_1$。若 $x_1\neq0$，则 $|x_n|=|x_1||\lambda|^{n-1}\to\infty$（因 $|\lambda|>1$），与 $x\in\ell^{\infty}$ 矛盾。故 $x_1=0$，从而 $x=0$。因此 $\lambda I-A$ 为单射。

**第二步：证明 $\lambda I-A$ 是满射且其逆有界。**  
对任意 $y=(y_1,y_2,\dots)\in\ell^{\infty}$，定义序列 $x=(x_n)$ 如下：
$$
x_n=\sum_{k=0}^{\infty}\frac{y_{n+k}}{\lambda^{k+1}},\qquad n=1,2,\dots.
$$
由于 $|\lambda|>1$，该级数绝对收敛：
$$
|x_n|\le\sum_{k=0}^{\infty}\frac{|y_{n+k}|}{|\lambda|^{k+1}}\le\|y\|_\infty\sum_{k=0}^{\infty}\frac{1}{|\lambda|^{k+1}}=\frac{\|y\|_\infty}{|\lambda|-1}.
$$
故 $x\in\ell^{\infty}$ 且 $\|x\|_\infty\le\dfrac{\|y\|_\infty}{|\lambda|-1}$。直接验证 $(\lambda I-A)x=y$：
$$
\begin{aligned}
\lambda x_n-x_{n+1}
&=\lambda\sum_{k=0}^{\infty}\frac{y_{n+k}}{\lambda^{k+1}}-\sum_{k=0}^{\infty}\frac{y_{n+1+k}}{\lambda^{k+1}}\\
&=\sum_{k=0}^{\infty}\frac{y_{n+k}}{\lambda^{k}}-\sum_{k=1}^{\infty}\frac{y_{n+k}}{\lambda^{k}}=y_n.
\end{aligned}
$$
因此 $(\lambda I-A)x=y$，$\lambda I-A$ 是满射。由构造知 $(\lambda I-A)^{-1}$ 有界且
$$
\|(\lambda I-A)^{-1}\|\le\frac{1}{|\lambda|-1}.
$$
从而 $\lambda\in\rho(A)$。

（注：亦可利用 Neumann 级数：因 $\|A/\lambda\|<1$，级数 $\sum_{k=0}^{\infty}(A/\lambda)^k$ 按范数收敛，给出 $(\lambda I-A)^{-1}=\lambda^{-1}\sum_{k=0}^{\infty}(A/\lambda)^k$。）

---

**(2)** 设 $|\lambda|\le1$，证明 $\lambda\in\sigma_p(A)$（点谱）并求特征空间。

考虑特征方程 $Ax=\lambda x$，即
$$
(x_2,x_3,x_4,\dots)=(\lambda x_1,\lambda x_2,\lambda x_3,\dots),
$$
从而 $x_{n+1}=\lambda x_n$ 对一切 $n\ge1$ 成立。递推得
$$
x_n=\lambda^{n-1}x_1,\qquad n\ge1.
$$
取 $x_1\neq0$，则序列 $x=(x_1,\lambda x_1,\lambda^2 x_1,\dots)$。当 $|\lambda|\le1$ 时，
$$
|x_n|=|x_1||\lambda|^{n-1}\le|x_1|,
$$
故 $x\in\ell^{\infty}$ 且非零。因此 $\lambda$ 是特征值，$\lambda\in\sigma_p(A)$。

特征空间由所有形如 $c\,(1,\lambda,\lambda^2,\dots)$ 的向量组成，即
$$
\operatorname{Ker}(\lambda I-A)=\{c\,v_\lambda\mid c\in\mathbb{C}\},\quad v_\lambda=(1,\lambda,\lambda^2,\dots).
$$
特别地，当 $\lambda=0$ 时，$v_0=(1,0,0,\dots)$，特征空间为 $\{c\,(1,0,0,\dots)\}$。

综上所述，结论得证。
