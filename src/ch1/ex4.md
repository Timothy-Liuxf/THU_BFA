# 习题 1.4

设 $(X, d)$ 为度量空间, 令 $d_1(x, y)=\min \{1, d(x, y)\}, d_2(x, y)=\frac{d(x, y)}{1+d(x, y)}$. 求证: $d_1$ 和 $d_2$ 都是 $X$ 上的度量.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

### 1. $d_1(x,y)=\min\{1,d(x,y)\}$ 是度量

**非负性**：$d(x,y)\ge 0$，故 $\min\{1,d(x,y)\}\ge 0$。  
若 $x=y$，则 $d(x,y)=0$，从而 $d_1(x,y)=0$；反之若 $d_1(x,y)=0$，则 $\min\{1,d(x,y)\}=0$，这迫使 $d(x,y)=0$（因为 $1>0$），于是 $x=y$。

**对称性**：$d(x,y)=d(y,x)$，所以
$$
d_1(x,y)=\min\{1,d(x,y)\}=\min\{1,d(y,x)\}=d_1(y,x).
$$

**三角不等式**：需证 $d_1(x,z)\le d_1(x,y)+d_1(y,z)$。  
首先注意函数 $f(t)=\min\{1,t\}$（$t\ge 0$）是单调不减的。由 $d$ 的三角不等式：
$$
d(x,z)\le d(x,y)+d(y,z).
$$
因此
$$
d_1(x,z)=f\big(d(x,z)\big)\le f\big(d(x,y)+d(y,z)\big).
$$
下面证明对任意非负实数 $a,b$ 有
$$
f(a+b)\le f(a)+f(b).
$$
- 若 $a+b\le 1$，则 $f(a+b)=a+b$。此时必有 $a\le 1$ 且 $b\le 1$，故 $f(a)=a,\ f(b)=b$，从而 $f(a+b)=f(a)+f(b)$。
- 若 $a+b>1$，则 $f(a+b)=1$。而 $f(a)+f(b)\ge 1$ 显然成立（因为 $f(a),f(b)\ge 0$ 且至少有一项不小于 $1$ 或两项之和至少为 $1$）。严格地：若 $f(a)+f(b)<1$，则必有 $f(a)=a<1$ 且 $f(b)=b<1$，从而 $a+b<1$，与 $a+b>1$ 矛盾。故 $f(a)+f(b)\ge 1=f(a+b)$。

于是 $f(a+b)\le f(a)+f(b)$ 恒成立。取 $a=d(x,y),\ b=d(y,z)$ 得
$$
f\big(d(x,y)+d(y,z)\big)\le f\big(d(x,y)\big)+f\big(d(y,z)\big)=d_1(x,y)+d_1(y,z).
$$
结合前面不等式即得
$$
d_1(x,z)\le d_1(x,y)+d_1(y,z).
$$
综上，$d_1$ 是 $X$ 上的度量。

---

### 2. $d_2(x,y)=\dfrac{d(x,y)}{1+d(x,y)}$ 是度量

记 $\varphi(t)=\dfrac{t}{1+t}$，$t\ge 0$。显然 $\varphi(0)=0$，$\varphi(t)\ge 0$，且 $\varphi$ 严格单调递增（导数 $\varphi'(t)=\frac{1}{(1+t)^2}>0$）。

**非负性**：因 $d(x,y)\ge 0$，故 $d_2(x,y)=\varphi(d(x,y))\ge 0$。  
若 $x=y$，则 $d(x,y)=0$，从而 $d_2(x,y)=0$；若 $d_2(x,y)=0$，则 $\varphi(d(x,y))=0$，由 $\varphi$ 的性质知 $d(x,y)=0$，于是 $x=y$。

**对称性**：$d(x,y)=d(y,x)$，所以
$$
d_2(x,y)=\varphi(d(x,y))=\varphi(d(y,x))=d_2(y,x).
$$

**三角不等式**：需证 $d_2(x,z)\le d_2(x,y)+d_2(y,z)$。  
由 $d$ 的三角不等式有
$$
d(x,z)\le d(x,y)+d(y,z).
$$
因 $\varphi$ 单调递增，故
$$
d_2(x,z)=\varphi\big(d(x,z)\big)\le \varphi\big(d(x,y)+d(y,z)\big).
$$
下面证明对任意非负实数 $a,b$ 有
$$
\varphi(a+b)\le \varphi(a)+\varphi(b).
$$

直接验证差：
$$
\varphi(a)+\varphi(b)-\varphi(a+b)=\frac{a}{1+a}+\frac{b}{1+b}-\frac{a+b}{1+a+b}.
$$
计算其分子（通分后）：
$$
\begin{aligned}
&\left(\frac{a}{1+a}+\frac{b}{1+b}\right)-\frac{a+b}{1+a+b}\\
=&\ \frac{a(1+b)+b(1+a)}{(1+a)(1+b)}-\frac{a+b}{1+a+b}\\
=&\ \frac{a+b+2ab}{(1+a)(1+b)}-\frac{a+b}{1+a+b}.
\end{aligned}
$$
通分得公分母 $(1+a)(1+b)(1+a+b)$，分子为
$$
N=(a+b+2ab)(1+a+b)-(a+b)(1+a)(1+b).
$$
展开：
$$
\begin{aligned}
(a+b+2ab)(1+a+b)&=(a+b+2ab)+(a+b+2ab)(a+b)\\
&=(a+b+2ab)+(a+b)^2+2ab(a+b),\\
(a+b)(1+a)(1+b)&=(a+b)(1+a+b+ab)\\
&=(a+b)+(a+b)^2+ab(a+b).
\end{aligned}
$$
相减：
$$
N=\big[(a+b+2ab)+(a+b)^2+2ab(a+b)\big]-\big[(a+b)+(a+b)^2+ab(a+b)\big]=2ab+ab(a+b)=ab(2+a+b)\ge 0.
$$
因此 $\varphi(a)+\varphi(b)-\varphi(a+b)\ge 0$，即 $\varphi(a+b)\le \varphi(a)+\varphi(b)$，等号当且仅当 $a=0$ 或 $b=0$ 时成立。

取 $a=d(x,y),\ b=d(y,z)$，则
$$
\varphi\big(d(x,y)+d(y,z)\big)\le \varphi\big(d(x,y)\big)+\varphi\big(d(y,z)\big)=d_2(x,y)+d_2(y,z).
$$
于是
$$
d_2(x,z)\le d_2(x,y)+d_2(y,z).
$$
综上，$d_2$ 是 $X$ 上的度量。

---

因此，$d_1$ 和 $d_2$ 均为 $X$ 上的度量。
