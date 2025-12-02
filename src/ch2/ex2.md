# 习题 2.2

设 $X$ 为 $n$ 维复线性空间, $\left\{e_1, e_2, \cdots, e_n\right\}$ 为 $X$ 的 Hamel 基, 将 $X$ 视为实线性空间 $X_{\mathbb{R}}$, 求 $X_{\mathrm{R}}$ 的 Hamel 基.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

设 \(X\) 是 \(n\) 维复线性空间，\(\{e_1,\dots,e_n\}\) 是 \(X\) 的一组基（Hamel 基）。将 \(X\) 视为实线性空间 \(X_{\mathbb{R}}\)（即只允许实数标量乘法）。则 \(X_{\mathbb{R}}\) 的一组 Hamel 基为
$$
\{e_1,\,i e_1,\; e_2,\,i e_2,\; \dots,\; e_n,\,i e_n\},
$$
其中 \(i\) 是虚数单位。此时 \(X_{\mathbb{R}}\) 的维数为 \(2n\)。

**证明**：  
任取 \(x\in X\)，由于 \(\{e_k\}\) 是复基，存在复数 \(\alpha_k = a_k + i b_k\) (\(a_k,b_k\in\mathbb{R}\)) 使得
$$
x = \sum_{k=1}^n \alpha_k e_k = \sum_{k=1}^n a_k e_k + \sum_{k=1}^n b_k (i e_k).
$$
因此 \(\{e_k, i e_k\}\) 张成 \(X_{\mathbb{R}}\)。

设实数 \(\lambda_k,\mu_k\in\mathbb{R}\) 满足
$$
\sum_{k=1}^n \bigl(\lambda_k e_k + \mu_k (i e_k)\bigr) = 0.
$$
由于 \(X\) 是复线性空间，可将上式改写为
$$
\sum_{k=1}^n (\lambda_k + i\mu_k) e_k = 0.
$$
因为 \(\{e_k\}\) 在复数域上线性无关，故 \(\lambda_k + i\mu_k = 0\) 对所有 \(k\) 成立，从而 \(\lambda_k = \mu_k = 0\)。这表明 \(\{e_k, i e_k\}\) 在实数域上线性无关。

综上，该集合是 \(X_{\mathbb{R}}\) 的一组 Hamel 基，基数为 \(2n\)。∎
