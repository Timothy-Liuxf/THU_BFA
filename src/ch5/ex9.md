# 习题 5.9

设 $A, B \in B(X), \lambda \in \rho(A) \bigcap \rho(B)$. 求证:
$$
R(\lambda, A)-R(\lambda, B)=R(\lambda, A)(B-A) R(\lambda, B).
$$

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**证明**：采用预解式的定义 $R(\lambda, A) = (A - \lambda I)^{-1}$（此时 $\lambda \in \rho(A)$ 当且仅当 $A-\lambda I$ 可逆）。由于 $A, B \in B(X)$ 且 $\lambda \in \rho(A) \cap \rho(B)$，则 $R(\lambda, A)$ 和 $R(\lambda, B)$ 均为有界线性算子。

由逆算子的性质，
$$
(B - \lambda I) R(\lambda, B) = I, \qquad R(\lambda, A) (A - \lambda I) = I.
$$

考虑
$$
\begin{aligned}
R(\lambda, A) - R(\lambda, B)
&= R(\lambda, A) \bigl((B - \lambda I) R(\lambda, B)\bigr) - \bigl(R(\lambda, A) (A - \lambda I)\bigr) R(\lambda, B) \\
&= R(\lambda, A) (B - \lambda I) R(\lambda, B) - R(\lambda, A) (A - \lambda I) R(\lambda, B).
\end{aligned}
$$

提取公因式 $R(\lambda, A)$ 和 $R(\lambda, B)$，得
$$
R(\lambda, A) - R(\lambda, B) = R(\lambda, A) \bigl[(B - \lambda I) - (A - \lambda I)\bigr] R(\lambda, B).
$$

因为 $(B - \lambda I) - (A - \lambda I) = B - A$，所以
$$
R(\lambda, A) - R(\lambda, B) = R(\lambda, A) (B - A) R(\lambda, B).
$$

这就完成了证明。
