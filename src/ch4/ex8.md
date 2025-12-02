# 习题 4.8

设 $X$ 为赋范空间, $M$ 为 $X$ 的线性子空间, $x \in X$, 求证:
$$
\rho(x, M) \geq \sup\left\{|f(x)|: f \in X^{\prime},\|f\| \leq 1,\left.f\right|_{M}=0\right\}.
$$

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**证明**：记 $d = \rho(x, M) = \inf_{y \in M} \|x - y\|$。  
任取 $f \in X'$ 满足 $\|f\|\le 1$ 且 $f|_M = 0$。对任意 $y \in M$，由于 $f(y)=0$，有  
$$
f(x) = f(x - y),
$$
从而  
$$
|f(x)| = |f(x-y)| \le \|f\|\cdot\|x-y\| \le \|x-y\|.
$$
上式对每个 $y\in M$ 都成立，故  
$$
|f(x)| \le \inf_{y\in M}\|x-y\| = d.
$$
由于 $f$ 是满足条件的任意泛函，对上式取上确界得  
$$
\sup\{|f(x)|: f\in X',\,\|f\|\le 1,\, f|_M=0\} \le d,
$$
即  
$$
\rho(x, M) \ge \sup\{|f(x)|: f\in X',\,\|f\|\le 1,\, f|_M=0\}.
$$
不等式得证。
