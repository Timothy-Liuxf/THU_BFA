# 习题 3.5

设 $X$ 为内积空间 $, x, y \in X$. 求证下述命题相互等价:

(1) $x \perp y$;

(2) 任取 $\alpha \in \mathbb{K},\|x+\alpha y\| \geq\|x\|$;

(3) 任取 $\alpha \in \mathbb{K},\|x+\alpha y\|=\|x-\alpha y\|$.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

设 $X$ 为内积空间，内积记为 $\langle\cdot,\cdot\rangle$，范数为 $\|\cdot\|$。对任意 $x,y\in X$，由内积性质可得
$$
\begin{aligned}
\|x+\alpha y\|^2 &= \|x\|^2 + |\alpha|^2\|y\|^2 + 2\operatorname{Re}\bigl(\alpha\langle y,x\rangle\bigr), \\
\|x-\alpha y\|^2 &= \|x\|^2 + |\alpha|^2\|y\|^2 - 2\operatorname{Re}\bigl(\alpha\langle y,x\rangle\bigr).
\end{aligned}
$$

---

**1. $(1)\Rightarrow(2)$ 和 $(1)\Rightarrow(3)$**

若 $x\perp y$，则 $\langle x,y\rangle=0$，从而 $\langle y,x\rangle=0$，代入上式得
$$
\|x+\alpha y\|^2 = \|x-\alpha y\|^2 = \|x\|^2 + |\alpha|^2\|y\|^2.
$$
因此对任意 $\alpha\in\mathbb{K}$ 有 $\|x+\alpha y\|\ge\|x\|$ 且 $\|x+\alpha y\|=\|x-\alpha y\|$，即 (2) 和 (3) 成立。

---

**2. $(2)\Rightarrow(1)$**

假设对任意 $\alpha\in\mathbb{K}$ 有 $\|x+\alpha y\|\ge\|x\|$。若 $y=0$，则 $\langle x,y\rangle=0$ 显然成立；下设 $y\neq0$。由展开式得
$$
|\alpha|^2\|y\|^2 + 2\operatorname{Re}\bigl(\alpha\langle y,x\rangle\bigr) \ge 0,\qquad\forall\alpha\in\mathbb{K}.
$$
记 $c=\langle y,x\rangle$。若 $c\neq0$，取 $\alpha=-t\,\bar c$（$t>0$），代入上式得
$$
t^2|c|^2\|y\|^2 - 2t|c|^2 \ge 0 \;\Longrightarrow\; |c|^2\bigl(t^2\|y\|^2-2t\bigr)\ge 0.
$$
由于 $|c|^2>0$，故 $t^2\|y\|^2-2t\ge0$ 对所有 $t>0$ 成立。但取 $0<t<2/\|y\|^2$ 时 $t^2\|y\|^2-2t<0$，矛盾。因此 $c=0$，即 $\langle y,x\rangle=0$，从而 $\langle x,y\rangle=0$，亦即 $x\perp y$。

---

**3. $(3)\Rightarrow(1)$**

假设对任意 $\alpha\in\mathbb{K}$ 有 $\|x+\alpha y\|=\|x-\alpha y\|$。平方后相减得
$$
4\operatorname{Re}\bigl(\alpha\langle y,x\rangle\bigr)=0,\qquad\forall\alpha\in\mathbb{K},
$$
即 $\operatorname{Re}\bigl(\alpha\langle y,x\rangle\bigr)=0$ 对所有 $\alpha$ 成立。特别地，取 $\alpha=\langle y,x\rangle$，则
$$
\operatorname{Re}\bigl(|\langle y,x\rangle|^2\bigr)=|\langle y,x\rangle|^2=0,
$$
故 $\langle y,x\rangle=0$，从而 $\langle x,y\rangle=0$，即 $x\perp y$。

---

综上，命题 (1)、(2)、(3) 相互等价。
