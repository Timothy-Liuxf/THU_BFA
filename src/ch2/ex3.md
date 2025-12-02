# 习题 2.3

设 $X, Y$ 为线性空间, $T: X \rightarrow Y$ 为线性算子且为单射. 求证: $\left\{x_1, x_2, \cdots, x_n\right\}$ 在 $X$ 中线性无关当且仅当 $\left\{T x_1, T x_2, \cdots, T x_n\right\}$ 在 $Y$ 中线性无关.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**证明**：

（必要性）假设 $\{x_1, x_2, \dots, x_n\}$ 在 $X$ 中线性无关。设标量 $\alpha_1,\dots,\alpha_n$ 满足 $\sum_{i=1}^n \alpha_i T x_i = 0$。由 $T$ 的线性性，
$$
T\bigg(\sum_{i=1}^n \alpha_i x_i\bigg) = \sum_{i=1}^n \alpha_i T x_i = 0.
$$
因为 $T$ 是单射，其核 $\ker T = \{0\}$，故 $\sum_{i=1}^n \alpha_i x_i = 0$。再利用 $\{x_i\}$ 的线性无关性，得 $\alpha_1 = \cdots = \alpha_n = 0$。因此 $\{T x_1, \dots, T x_n\}$ 线性无关。

（充分性）假设 $\{T x_1, T x_2, \dots, T x_n\}$ 在 $Y$ 中线性无关。设标量 $\alpha_1,\dots,\alpha_n$ 满足 $\sum_{i=1}^n \alpha_i x_i = 0$。应用 $T$ 得
$$
T\bigg(\sum_{i=1}^n \alpha_i x_i\bigg) = \sum_{i=1}^n \alpha_i T x_i = T(0) = 0.
$$
由 $\{T x_i\}$ 的线性无关性，必有 $\alpha_1 = \cdots = \alpha_n = 0$。故 $\{x_1, \dots, x_n\}$ 线性无关。

综上，命题得证。$\square$
