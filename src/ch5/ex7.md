# 习题 5.7

设 $A \in B(X), m \geq 1, \lambda$ 为 $A^m$ 的特征值. 求证: $\lambda$ 的某个 $m$ 次方根是 $A$ 的特征值.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**证明**：设 $x\neq 0$ 满足 $A^m x=\lambda x$，即 $(A^m-\lambda I)x=0$。考虑多项式 $p(z)=z^m-\lambda$，在复数域上可分解为
$$
p(z)=\prod_{k=1}^{m}(z-\mu_k),
$$
其中 $\mu_1,\dots,\mu_m$ 为 $\lambda$ 的 $m$ 次方根（即 $\mu_k^m=\lambda$）。将 $A$ 代入多项式，由多项式函数的演算可得
$$
p(A)=A^m-\lambda I=\prod_{k=1}^{m}(A-\mu_k I),
$$
且各因子 $(A-\mu_k I)$ 彼此可交换。

假设对于每个 $k=1,\dots,m$，算子 $(A-\mu_k I)$ 都是单射。由于它们可交换，我们归纳地证明其乘积也是单射：若 $S,T$ 单射且 $ST=TS$，则 $ST$ 单射（因为 $STx=0\Rightarrow Tx\in\ker S$，而 $S$ 单射故 $Tx=0$，又 $T$ 单射得 $x=0$）。因此 $\prod_{k=1}^{m}(A-\mu_k I)$ 为单射。但 $p(A)x=0$ 且 $x\neq 0$，这与单射性矛盾。

从而存在某个 $k$ 使得 $(A-\mu_k I)$ 不是单射，即存在非零向量 $y$ 满足 $(A-\mu_k I)y=0$，亦即 $Ay=\mu_k y$。故 $\mu_k$ 是 $A$ 的特征值，而 $\mu_k$ 是 $\lambda$ 的一个 $m$ 次方根。证毕。
