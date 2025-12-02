# 习题 5.6

设 $A: \ell^2 \rightarrow \ell^2$ 定义为
$$
A\left(x_1, x_2, x_3, \cdots\right)=\left(x_2, x_3, x_4, \cdots\right).
$$
若 $|\lambda|=1$, 此时 $\lambda$ 还是 $A$ 的特征值吗?

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**解答**

若 $|\lambda|=1$，则 $\lambda$ 不是 $A$ 的特征值。证明如下：

设 $x = (x_1, x_2, x_3, \dots) \in \ell^2$ 满足 $A x = \lambda x$，即
$$
(x_2, x_3, x_4, \dots) = \lambda (x_1, x_2, x_3, \dots).
$$
比较分量得 $x_{n+1} = \lambda x_n$ 对任意 $n \ge 1$ 成立。递推可得
$$
x_n = \lambda^{n-1} x_1 \qquad (n \ge 1).
$$
于是
$$
\|x\|_2^2 = \sum_{n=1}^{\infty} |x_n|^2 = |x_1|^2 \sum_{n=1}^{\infty} |\lambda|^{2(n-1)}.
$$
若 $|\lambda| = 1$，则 $\sum_{n=1}^{\infty} |\lambda|^{2(n-1)} = \sum_{n=1}^{\infty} 1$ 发散，故要使级数收敛必须 $x_1 = 0$，从而 $x_n = 0$ 对所有 $n$ 成立，即 $x = 0$。因此不存在非零的 $x \in \ell^2$ 满足 $A x = \lambda x$，$\lambda$ 不是 $A$ 的特征值。
