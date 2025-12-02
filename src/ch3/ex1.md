# 习题 3.1

设 $X$ 为实内积空间, $x, y \in X$. 求证: $x \perp y$ 当且仅当勾股定理对 $x, y$ 成立, 即 $\|x+y\|^2=\|x\|^2+\|y\|^2$. 举例说明若 $X$ 为复内积空间, 则上述结论一般不成立.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**证明（实内积空间）**：

设 $X$ 是实内积空间，$x,y\in X$。

若 $x\perp y$，即 $\langle x,y\rangle=0$，则

$$
\begin{aligned}
\|x+y\|^2 &= \langle x+y, x+y\rangle \\
&= \langle x,x\rangle + \langle x,y\rangle + \langle y,x\rangle + \langle y,y\rangle \\
&= \|x\|^2 + \|y\|^2,
\end{aligned}
$$

因为实内积满足对称性 $\langle y,x\rangle=\langle x,y\rangle =0$。故勾股定理成立。

反之，若 $\|x+y\|^2=\|x\|^2+\|y\|^2$，则由展开得

$$
\|x\|^2+\|y\|^2 + 2\langle x,y\rangle = \|x\|^2+\|y\|^2,
$$

从而 $2\langle x,y\rangle=0$，即 $\langle x,y\rangle=0$，因此 $x\perp y$。

综上，在实内积空间中，$x\perp y$ 当且仅当 $\|x+y\|^2=\|x\|^2+\|y\|^2$。

**复内积空间中的反例**：

考虑 $X=\mathbb{C}$，赋予标准内积 $\langle a,b\rangle = a\,\overline{b}$。取 $x=1$, $y=i$。

计算内积：$\langle x,y\rangle = 1\cdot\overline{i} = 1\cdot(-i) = -i \neq 0$，故 $x$ 与 $y$ 不正交。

计算范数：$\|x\|^2 = |1|^2 = 1$，$\|y\|^2 = |i|^2 = 1$，$\|x+y\|^2 = |1+i|^2 = (\sqrt{2})^2 = 2$。

因此 $\|x+y\|^2 = 2 = 1+1 = \|x\|^2+\|y\|^2$，勾股定理成立。

这表明在复内积空间中，即使勾股定理成立，也不能推出 $x\perp y$，故结论一般不成立。
