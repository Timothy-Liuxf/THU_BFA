# 习题 3.9

在 $\mathbb{C}^n$ 上赋子内积
$$
\langle\boldsymbol{x}, \boldsymbol{y}\rangle=\sum_{i=1}^n x_{i} \bar{y}_{i},
$$
其中 $\boldsymbol{x}=\left(x_1, x_2, \cdots, x_n\right), \boldsymbol{y}=\left(y_1, y_2, \cdots, y_n\right) \in \mathbb{C}^n$. 考虑 $\mathbb{C}^n$ 的子集
$$
M=\left\{\left(x_1, x_2, \cdots, x_n\right) \in \mathbb{C}^n: x_1+x_2+\cdots+x_n=1\right\}.
$$
求证: $M$ 为完备凸集. 求出 $M$ 中具有最小范数的向量.

## 解答

> 解答使用 DeepSeek v3.2 Speciale 生成

**证明凸性**:  
对任意 $\boldsymbol{x},\boldsymbol{y}\in M$ 和 $t\in[0,1]$,  
$$
\sum_{i=1}^n (t x_i + (1-t)y_i) = t\sum_{i=1}^n x_i + (1-t)\sum_{i=1}^n y_i = t\cdot1 + (1-t)\cdot1 = 1,
$$  
故 $t\boldsymbol{x}+(1-t)\boldsymbol{y}\in M$, 因此 $M$ 是凸集.

**证明完备性**:  
定义线性泛函 $f:\mathbb{C}^n\to\mathbb{C}$ 为 $f(\boldsymbol{x})=\sum_{i=1}^n x_i$.  
在赋予欧几里得范数的 $\mathbb{C}^n$ 中, $f$ 是连续的.  
因为单点集 $\{1\}$ 是 $\mathbb{C}$ 中的闭集, 所以原像 $M=f^{-1}(\{1\})$ 是 $\mathbb{C}^n$ 中的闭集.  
$\mathbb{C}^n$ 是有限维内积空间, 故完备, 其闭子集 $M$ 也完备.  
所以 $M$ 是完备凸集.

**求最小范数向量**:  
对任意 $\boldsymbol{x}\in M$, 由 Cauchy–Schwarz 不等式,
$$
1 = \left|\sum_{i=1}^n x_i\right| \le \left(\sum_{i=1}^n |x_i|^2\right)^{\!1/2} \left(\sum_{i=1}^n 1^2\right)^{\!1/2} = \|\boldsymbol{x}\|\sqrt{n},
$$  
因而 $\|\boldsymbol{x}\|\ge 1/\sqrt{n}$.  
等号成立当且仅当存在常数 $\lambda\in\mathbb{C}$ 使得 $x_i = \lambda\cdot1$ 对所有 $i$ 成立, 且 $\sum x_i = \lambda n = 1$, 故 $\lambda = 1/n$.  
于是向量  
$$
\boldsymbol{x}_0 = \left(\frac{1}{n},\frac{1}{n},\cdots,\frac{1}{n}\right)
$$  
满足 $\|\boldsymbol{x}_0\| = 1/\sqrt{n}$, 且是 $M$ 中唯一具有最小范数的向量.
