# 习题 4.9

考虑 $c_0$ 的线性子空间 $M=\left\{\left\{x_n\right\} \in c_0: \sum_{n=1}^{\infty} \frac{x_n}{2^n}=0\right\}$. 求证: 任取 $x \notin M, x$ 在 $M$ 中无最佳逼近元.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**证明.** 定义线性泛函 $f:c_0\to\mathbb{C}$（或 $\mathbb{R}$）为
$$
f(x)=\sum_{n=1}^{\infty}\frac{x_n}{2^n},\qquad x=(x_n)\in c_0.
$$
因为 $\sum_{n=1}^\infty2^{-n}=1$，对任意 $x\in c_0$ 有
$$
|f(x)|\le\sum_{n=1}^\infty\frac{|x_n|}{2^n}\le\|x\|_\infty\sum_{n=1}^\infty\frac{1}{2^n}=\|x\|_\infty,
$$
故 $f$ 连续且 $\|f\|\le 1$。取 $x^{(N)}=(1,\dots,1,0,0,\dots)$（前 $N$ 项为 $1$），则 $\|x^{(N)}\|_\infty=1$，且
$$
f(x^{(N)})=\sum_{n=1}^N\frac{1}{2^n}=1-\frac{1}{2^N}\to 1\quad(N\to\infty),
$$
所以 $\|f\|=1$。

设 $M=\ker f=\{x\in c_0:f(x)=0\}$，则 $M$ 是 $c_0$ 的闭线性子空间。任取 $x\notin M$，记 $d=\inf_{z\in M}\|x-z\|_\infty$。下面证明 $d=|f(x)|$。

*下界*：对任意 $z\in M$，$f(z)=0$，于是
$$
|f(x)|=|f(x)-f(z)|=|f(x-z)|\le\|f\|\cdot\|x-z\|_\infty=\|x-z\|_\infty,
$$
故 $d\ge|f(x)|$。

*上界*：对每个 $N\in\mathbb{N}$，令 $u_N=(1,\dots,1,0,0,\dots)$（前 $N$ 项为 $1$），则 $\|u_N\|_\infty=1$ 且 $f(u_N)=1-2^{-N}>0$。取
$$
z_N=x-\frac{f(x)}{f(u_N)}\,u_N,
$$
则 $f(z_N)=f(x)-\frac{f(x)}{f(u_N)}f(u_N)=0$，即 $z_N\in M$。于是
$$
\|x-z_N\|_\infty=\left\|\frac{f(x)}{f(u_N)}u_N\right\|_\infty=\frac{|f(x)|}{f(u_N)}\to|f(x)|\quad(N\to\infty),
$$
因此 $d\le|f(x)|$。综上 $d=|f(x)|$。

现假设存在 $z\in M$ 使 $\|x-z\|_\infty=d$。令 $y=x-z$，则 $f(y)=f(x)\neq0$，且 $\|y\|_\infty=d=|f(y)|$。记 $\alpha=f(y)$，$d=|\alpha|>0$，并记 $w_n=2^{-n}$，则 $\sum_{n=1}^\infty w_n=1$，$w_n>0$，且
$$
\alpha=f(y)=\sum_{n=1}^\infty w_n y_n,\qquad \|y\|_\infty=|\alpha|.
$$
于是
$$
|\alpha|=\Bigl|\sum_{n=1}^\infty w_n y_n\Bigr|\le\sum_{n=1}^\infty w_n|y_n|\le\|y\|_\infty\sum_{n=1}^\infty w_n=|\alpha|.
$$
故两个不等式均取等号。

由第一个等号 $|\sum w_n y_n|=\sum w_n|y_n|$ 可知，存在常数 $\theta\in\mathbb{R}$ 使得 $e^{-i\theta}y_n=|y_n|$ 对所有 $n$ 成立（即所有 $y_n$ 具有相同的辐角）；特别地，在实数情形下所有 $y_n$ 同号。

由第二个等号 $\sum w_n|y_n|=\|y\|_\infty\sum w_n$，并注意到 $|y_n|\le\|y\|_\infty=|\alpha|$ 且 $w_n>0$，若存在某个 $k$ 使 $|y_k|<|\alpha|$，则
$$
\sum_{n=1}^\infty w_n|y_n|<|\alpha|\sum_{n=1}^\infty w_n=|\alpha|,
$$
矛盾。因此对一切 $n$，$|y_n|=|\alpha|$。

结合两点，得 $y_n=|\alpha| e^{i\theta}$（实数情形为 $y_n=\pm|\alpha|$ 且符号一致），即 $y$ 为常数序列。但 $y\in c_0$ 要求 $\lim_{n\to\infty}y_n=0$，这与 $|\alpha|>0$ 矛盾。

因此假设不成立，不存在 $z\in M$ 使得 $\|x-z\|_\infty=d$，即 $x$ 在 $M$ 中无最佳逼近元。∎
