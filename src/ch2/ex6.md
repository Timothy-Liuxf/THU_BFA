# 习题 2.6

考虑 $x_n \in C[0,2 \pi]$, 其中 $n \geq 1, x_n(t)=\sin (n t)$. 求证: 集合 $\left\{x_n: n \geq 1\right\}$ 线性无关.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**证明**：设 $n_1, n_2, \dots, n_k$ 是互不相同的正整数，$c_1, c_2, \dots, c_k \in \mathbb{R}$（或 $\mathbb{C}$）满足
$$
\sum_{j=1}^k c_j \sin(n_j t) = 0,\qquad \forall t\in[0,2\pi].
$$
欲证所有 $c_j = 0$。

固定某个 $i \in \{1,2,\dots,k\}$，将上式两边乘以 $\sin(n_i t)$ 并在 $[0,2\pi]$ 上积分，得
$$
0 = \int_0^{2\pi} \left( \sum_{j=1}^k c_j \sin(n_j t) \right) \sin(n_i t) \, dt = \sum_{j=1}^k c_j \int_0^{2\pi} \sin(n_j t) \sin(n_i t) \, dt.
$$
由于三角函数的正交性：
$$
\int_0^{2\pi} \sin(m t) \sin(n t) \, dt = 
\begin{cases}
0, & m \neq n, \\
\pi, & m = n \ (m,n\ge 1),
\end{cases}
$$
因此上式中只有当 $j = i$ 时积分非零，即
$$
0 = c_i \int_0^{2\pi} \sin^2(n_i t) \, dt = c_i \cdot \pi.
$$
故 $c_i = 0$。由 $i$ 的任意性知 $c_1 = c_2 = \cdots = c_k = 0$。所以 $\{\,x_n: n\ge 1\,\}$ 是线性无关集。
