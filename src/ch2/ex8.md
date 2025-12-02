# 习题 2.8

设 $X$ 为赋范空间, $M$ 为 $X$ 的凸子集, 且 $M^{\circ} \neq \emptyset$. 求证: $M^{\circ}$ 为凸集, 且
$$
\overline{M^{\circ}}=\bar{M}.
$$

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**证明** (1) $M^\circ$ 是凸集.

任取 $x,y\in M^\circ$, 则存在 $r>0$ 使得 $B(x,r)\subset M$, $B(y,r)\subset M$ (取公共的 $r$). 对任意 $t\in[0,1]$, 令 $z=tx+(1-t)y$. 要证 $z\in M^\circ$. 对任意 $v\in X$ 满足 $\|v\|<r$, 有 $x+v\in B(x,r)\subset M$, $y+v\in B(y,r)\subset M$. 由 $M$ 的凸性,
$$
z+v = t(x+v)+(1-t)(y+v)\in M.
$$
故 $B(z,r)\subset M$, 即 $z$ 为 $M$ 的内点. 因此 $M^\circ$ 是凸集.

(2) 证明 $\overline{M^\circ}=\overline{M}$.

显然 $M^\circ\subset M$ 蕴含 $\overline{M^\circ}\subset\overline{M}$. 下证 $\overline{M}\subset\overline{M^\circ}$.

因 $M^\circ\neq\varnothing$, 取定 $x_0\in M^\circ$. 任取 $x\in\overline{M}$, 则存在序列 $\{y_n\}\subset M$ 使得 $y_n\to x$. 定义
$$
z_n = \Bigl(1-\frac1n\Bigr)y_n + \frac1n x_0,\quad n\in\mathbb{N}.
$$
先证每个 $z_n$ 属于 $M^\circ$. 利用如下引理：

> **引理** 设 $M$ 为凸集, $x_0\in M^\circ$, $y\in M$. 则对任意 $\lambda\in[0,1)$, 点 $w=(1-\lambda)x_0+\lambda y$ 属于 $M^\circ$.

**引理证明** 由 $x_0\in M^\circ$, 存在 $r>0$ 使得 $B(x_0,r)\subset M$. 取 $\delta=(1-\lambda)r>0$. 任取 $u\in B(w,\delta)$, 即 $\|u\|<\delta$. 令 $u'=u/(1-\lambda)$, 则 $\|u'\|=\|u\|/(1-\lambda)<r$, 故 $x_0+u'\in B(x_0,r)\subset M$. 于是
$$
w+u = (1-\lambda)x_0+\lambda y+u = (1-\lambda)\bigl(x_0+u/(1-\lambda)\bigr)+\lambda y\in M,
$$
所以 $B(w,\delta)\subset M$, 即 $w\in M^\circ$.

应用引理, 取 $\lambda=1-1/n\in[0,1)$, 则 $z_n = (1-\lambda)x_0+\lambda y_n$ 满足 $z_n\in M^\circ$. 因此 $\{z_n\}\subset M^\circ$.

再证 $z_n\to x$. 因为
$$
z_n = y_n + \frac1n(x_0-y_n),
$$
而 $y_n\to x$ 推出 $\{y_n\}$ 有界, 故 $\|z_n-y_n\|\le\frac1n(\|x_0\|+\|y_n\|)\to0$, 从而 $z_n\to x$. 因此 $x\in\overline{M^\circ}$.

综上, $\overline{M^\circ}=\overline{M}$. $\square$
