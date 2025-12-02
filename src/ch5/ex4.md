# 习题 5.4

设 $T_n, T \in B(X)$, 且 $\left\|T_n-T\right\| \rightarrow 0, \lambda_0 \in \rho(T)$. 求证: 当 $n$ 足够大时, $\lambda_0 \in \rho\left(T_n\right)$, 且 $\lim_{n \rightarrow \infty} R\left(\lambda_0, T_n\right)=R\left(\lambda_0, T\right).$

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**证明**  

设 $X$ 为 Banach 空间，$T_n, T \in B(X)$ 且 $\|T_n - T\|\to 0$。取 $\lambda_0 \in \rho(T)$，记 $A = R(\lambda_0, T) = (\lambda_0 I - T)^{-1} \in B(X)$。

**第一步：证明当 $n$ 充分大时 $\lambda_0 \in \rho(T_n)$。**  

注意到
$$
\lambda_0 I - T_n = (\lambda_0 I - T) - (T_n - T) = (\lambda_0 I - T)\bigl[I - (\lambda_0 I - T)^{-1}(T_n - T)\bigr] = (\lambda_0 I - T)\bigl[I - A (T_n - T)\bigr].
$$
因为 $\|T_n - T\|\to 0$，所以
$$
\|A(T_n - T)\| \le \|A\|\,\|T_n - T\| \to 0.
$$
故存在正整数 $N$，使得当 $n > N$ 时 $\|A(T_n - T)\| < 1$。此时算子 $I - A(T_n - T)$ 可逆，其逆由 Neumann 级数给出：
$$
\bigl[I - A(T_n - T)\bigr]^{-1} = \sum_{k=0}^{\infty} [A(T_n - T)]^k,
$$
且满足估计
$$
\bigl\|[I - A(T_n - T)]^{-1}\bigr\| \le \frac{1}{1 - \|A(T_n - T)\|}.
$$
于是 $\lambda_0 I - T_n$ 可逆，且逆算子为
$$
R(\lambda_0, T_n) = [I - A(T_n - T)]^{-1} A.
$$
因此 $\lambda_0 \in \rho(T_n)$ 对一切 $n > N$ 成立。

**第二步：证明预解式依算子范数收敛。**  

对于 $n > N$，计算
$$
\begin{aligned}
R(\lambda_0, T_n) - R(\lambda_0, T)
&= [I - A(T_n - T)]^{-1} A - A \\
&= \bigl([I - A(T_n - T)]^{-1} - I\bigr) A.
\end{aligned}
$$
利用 Neumann 级数展开，
$$
[I - A(T_n - T)]^{-1} - I = \sum_{k=1}^{\infty} [A(T_n - T)]^k.
$$
从而
$$
\begin{aligned}
\|R(\lambda_0, T_n) - R(\lambda_0, T)\|
&\le \|A\| \sum_{k=1}^{\infty} \|A(T_n - T)\|^k \\
&= \|A\| \cdot \frac{\|A(T_n - T)\|}{1 - \|A(T_n - T)\|}.
\end{aligned}
$$
当 $n\to\infty$ 时，$\|A(T_n - T)\|\to 0$，故上式右端趋于 $0$，即
$$
\lim_{n\to\infty} R(\lambda_0, T_n) = R(\lambda_0, T)
$$
在算子范数意义下成立。$\square$
