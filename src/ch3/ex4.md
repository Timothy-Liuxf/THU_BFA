# 习题 3.4

设 $X$ 为内积空间 $, x_n, x \in X$. 求证: $x_n \rightarrow x$ 当且仅当 $\left\|x_n\right\| \rightarrow\|x\|$, 且 $\left\langle x_n, x\right\rangle \rightarrow$ $\langle x, x\rangle$.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**证明**  
（必要性）若 $x_n\to x$，则由范数的连续性有 $\|x_n\|\to\|x\|$，由内积的连续性有 $\langle x_n,x\rangle\to\langle x,x\rangle$。

（充分性）设 $\|x_n\|\to\|x\|$ 且 $\langle x_n,x\rangle\to\langle x,x\rangle$。则
$$
\begin{aligned}
\|x_n-x\|^2 &= \langle x_n-x,x_n-x\rangle \\
&= \|x_n\|^2 - \langle x_n,x\rangle - \langle x,x_n\rangle + \|x\|^2.
\end{aligned}
$$
由于 $\langle x,x_n\rangle = \overline{\langle x_n,x\rangle}$，且 $\langle x_n,x\rangle\to\langle x,x\rangle$，而 $\langle x,x\rangle$ 是实数，故 $\overline{\langle x_n,x\rangle}\to\overline{\langle x,x\rangle}=\langle x,x\rangle$。于是
$$
\|x_n-x\|^2 \to \|x\|^2 - \langle x,x\rangle - \langle x,x\rangle + \|x\|^2 = 0.
$$
因此 $x_n\to x$。
