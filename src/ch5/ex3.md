# 习题 5.3

设 $A \in B(X)$. 求证: 当 $|\lambda| \rightarrow \infty$ 时, $R(\lambda, A) \rightarrow 0$.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**证明**  
设 $A$ 是 Banach 空间 $X$ 上的有界线性算子，即 $A\in B(X)$。当 $|\lambda| > \|A\|$ 时，$\lambda I - A$ 可逆，且其逆算子（预解式）可表示为 Neumann 级数：

$$
R(\lambda, A) = (\lambda I - A)^{-1} = \frac{1}{\lambda} \sum_{n=0}^{\infty} \left( \frac{A}{\lambda} \right)^n = \sum_{n=0}^{\infty} \lambda^{-(n+1)} A^n.
$$

对上述级数取范数估计：

$$
\| R(\lambda, A) \| \le \sum_{n=0}^{\infty} |\lambda|^{-(n+1)} \| A \|^n 
= \frac{1}{|\lambda|} \sum_{n=0}^{\infty} \left( \frac{\| A \|}{|\lambda|} \right)^n 
= \frac{1}{|\lambda| - \| A \|},
$$

其中最后一步利用了几何级数求和公式，并需要 $|\lambda| > \|A\|$。当 $|\lambda| \to \infty$ 时，上式右端趋于 $0$，因此

$$
\| R(\lambda, A) \| \to 0,
$$

即 $R(\lambda, A)$ 按算子范数收敛到零算子。证毕。
