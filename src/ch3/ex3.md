# 习题 3.3

若 $X$ 为有限维线性空间, $\left\{e_1, e_2, \cdots, e_n\right\}$ 为 $X$ 的 Hamel 基. 求证: $X$ 上的内积由
$$
\gamma_{i j}=\left\langle e_{i}, e_{j}\right\rangle, \quad 1 \leq i, j \leq n
$$
唯一确定. 问: 能以完全任意方式选取 $\gamma_{i j}$ 吗?

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**证明**：设 $X$ 是有限维线性空间，$\dim X = n$，$\{e_1,\dots,e_n\}$ 是 $X$ 的一组 Hamel 基。对任意 $x,y\in X$，存在唯一坐标 $x=\sum_{i=1}^n \alpha_i e_i$，$y=\sum_{j=1}^n \beta_j e_j$（$\alpha_i,\beta_j\in\mathbb{F}$，$\mathbb{F}=\mathbb{R}$ 或 $\mathbb{C}$）。由内积的线性与共轭线性（实情形为双线性），
$$
\langle x,y\rangle = \Big\langle\sum_{i=1}^n \alpha_i e_i,\sum_{j=1}^n \beta_j e_j\Big\rangle = \sum_{i=1}^n\sum_{j=1}^n \alpha_i \overline{\beta_j}\,\langle e_i,e_j\rangle.
$$
因此，一旦知道所有 $\gamma_{ij}=\langle e_i,e_j\rangle$，则任意两个向量的内积均可通过上式算出，故 $X$ 上的内积由 $\gamma_{ij}$ 唯一确定。

**能否任意选取 $\gamma_{ij}$？**  
不能。因为内积必须满足公理，从而 $\gamma_{ij}$ 必须满足：

1. **共轭对称性**：$\langle e_i,e_j\rangle = \overline{\langle e_j,e_i\rangle}$，即 $\gamma_{ij} = \overline{\gamma_{ji}}$；
2. **正定性**：对任意不全为零的 $c_1,\dots,c_n\in\mathbb{F}$，有
   $$
   \sum_{i,j=1}^n \gamma_{ij}\,c_i\overline{c_j} > 0.
   $$

换言之，矩阵 $G=(\gamma_{ij})$ 必须是 **Hermitian 正定矩阵**（实情形为对称正定矩阵）。  
反之，若给定矩阵 $G$ 满足上述条件，则通过
$$
\langle x,y\rangle = \sum_{i,j=1}^n \gamma_{ij}\,\alpha_i\overline{\beta_j}
$$
定义的二元函数是 $X$ 上的一个内积，且满足 $\langle e_i,e_j\rangle = \gamma_{ij}$。因此 $\gamma_{ij}$ 不能完全任意，必须满足 Hermitian 正定性。
