# 习题 3.2

设 $X$ 为内积空间 $, x, y, z \in X$. 证明 Applonius 恒等式:
$$
\|z-x\|^2+\|z-y\|^2=\frac{1}{2}\|x-y\|^2+2\left\|z-\frac{1}{2}(x+y)\right\|^2.
$$

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**证明**：设 $X$ 上的内积为 $\langle\cdot,\cdot\rangle$，诱导的范数为 $\|u\|=\sqrt{\langle u,u\rangle}$。对任意 $x,y,z\in X$，计算等式的两边。

**左边**：
$$
\begin{aligned}
\|z-x\|^2+\|z-y\|^2
&= \langle z-x,z-x\rangle+\langle z-y,z-y\rangle \\
&= \bigl(\|z\|^2-\langle z,x\rangle-\langle x,z\rangle+\|x\|^2\bigr)\\
&\quad +\bigl(\|z\|^2-\langle z,y\rangle-\langle y,z\rangle+\|y\|^2\bigr)\\
&= 2\|z\|^2+\|x\|^2+\|y\|^2-\bigl(\langle z,x\rangle+\langle x,z\rangle+\langle z,y\rangle+\langle y,z\rangle\bigr).
\end{aligned}
$$

**右边**：令 $w=z-\frac{1}{2}(x+y)$，则
$$
\begin{aligned}
\frac{1}{2}\|x-y\|^2 &=\frac{1}{2}\bigl(\|x\|^2-\langle x,y\rangle-\langle y,x\rangle+\|y\|^2\bigr),\\
2\|w\|^2 &=2\bigl\langle z-\tfrac12(x+y),\,z-\tfrac12(x+y)\bigr\rangle \\
&=2\biggl( \|z\|^2-\frac12\langle z,x+y\rangle-\frac12\langle x+y,z\rangle+\frac14\|x+y\|^2 \biggr)\\
&=2\|z\|^2-\langle z,x+y\rangle-\langle x+y,z\rangle+\frac12\|x+y\|^2\\
&=2\|z\|^2-\bigl(\langle z,x\rangle+\langle z,y\rangle\bigr)-\bigl(\langle x,z\rangle+\langle y,z\rangle\bigr)\\
&\quad +\frac12\bigl(\|x\|^2+\|y\|^2+\langle x,y\rangle+\langle y,x\rangle\bigr).
\end{aligned}
$$

将这两部分相加：
$$
\begin{aligned}
R &=\frac{1}{2}\|x-y\|^2+2\|w\|^2 \\
&=\bigl(\tfrac12\|x\|^2+\tfrac12\|y\|^2-\tfrac12\langle x,y\rangle-\tfrac12\langle y,x\rangle\bigr) \\
&\quad +\bigl(2\|z\|^2-(\langle z,x\rangle+\langle z,y\rangle)-(\langle x,z\rangle+\langle y,z\rangle)\\
&\qquad +\tfrac12\|x\|^2+\tfrac12\|y\|^2+\tfrac12\langle x,y\rangle+\tfrac12\langle y,x\rangle\bigr)\\
&=2\|z\|^2+\|x\|^2+\|y\|^2-\bigl(\langle z,x\rangle+\langle z,y\rangle+\langle x,z\rangle+\langle y,z\rangle\bigr).
\end{aligned}
$$

比较左边与右边的表达式，两者完全相同，故
$$
\|z-x\|^2+\|z-y\|^2=\frac{1}{2}\|x-y\|^2+2\left\|z-\frac{1}{2}(x+y)\right\|^2.
$$
恒等式得证。
